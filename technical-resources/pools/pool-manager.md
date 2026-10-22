# Pool Manager

`MaplePoolManager` (v5.0.0 in v7) is the control contract for a Pool. It holds the Pool's configuration, records which strategies the Pool may fund and the cap on each, releases Pool cash to those strategies, aggregates `totalAssets` and `unrealizedLosses`, and routes withdrawal requests to the Withdrawal Manager. The Pool itself stays minimal and immutable, so anything that may need to change lives here. Full interface: [PoolManager](../interfaces/pool-manager.md).

## Owned strategies and attached Strategy Managers

A Pool Manager holds two kinds of position. `strategyList` holds both.

|  | Owned strategy | Strategy Manager |
| --- | --- | --- |
| Registered by | `addStrategy`, which deploys it from a `STRATEGY_FACTORY` | `addStrategyManager`, which attaches an existing instance |
| Flag | `isStrategy` | `isStrategyManager` |
| Belongs to | This Pool only | Several Pools, each holding shares |
| Reports to the Pool Manager | `assetsUnderManagement()`, `unrealizedLosses()` | `assetsOf(poolManager)`, `unrealizedLossesOf(poolManager)` |

In v7 the [Open Term Loan Manager](../strategies/open-term-loans/README.md) is the only owned strategy. Every other strategy is reached through a [Strategy Manager](../strategies/strategy-manager.md). [How Pools Allocate Capital](../strategies/how-pools-allocate-capital.md) explains the flows between them.

`addStrategy(strategyFactory, salt, extraDeploymentData)` deploys the strategy from the factory with a caller-supplied salt, prepends the Pool Manager address to the deployment data, and checks that `assetsUnderManagement()` on the new strategy does not revert.

`addStrategyManager(strategyManager)` requires that the address is not already registered as either kind, that a `STRATEGY_MANAGER_FACTORY` registered in Globals deployed it, that it supports the Pool's asset (`isAssetSupported(asset)`), and that `assetsOf(poolManager)` does not revert.

`removeStrategyManager(strategyManager)` requires the Pool's position to be zero (`assetsOf(poolManager) == 0`). It removes the address from `strategyList`, clears `isStrategyManager` and resets the cap to zero. Owned strategies cannot be removed through the Pool Manager.

## Strategy caps

`strategyCapOf[strategy]` is the most the Pool may have deployed in a strategy or Strategy Manager at any time, measured by the assets the position reports. `setStrategyCap(strategy, cap)` sets it and reverts when the value does not change. A non-zero cap can only be set on a registered strategy or Strategy Manager. A zero cap can be set on any address, which is how a cap is cleared. The default is zero, so a newly added strategy cannot draw funds until a cap is set. This is one of three caps on funding. The other two live on the Strategy Manager, see [How Pools Allocate Capital](../strategies/how-pools-allocate-capital.md).

## Funding

Strategies pull cash from the Pool through `requestFunds(destination, amount)`. The caller is the strategy or Strategy Manager. The Pool Manager:

1. Rejects a zero destination, a zero amount, and a Pool with zero `totalSupply`.
2. Checks that the caller is registered (`isStrategy` or `isStrategyManager`) and is still a valid instance of its factory, which must still be registered in Globals.
3. Checks the cap: `_assetsUnderManagement(caller) + amount <= strategyCapOf[caller]`, reverting with `PM:RF:STRATEGY_CAP`.
4. Transfers `amount` of the Pool's asset from the Pool to `destination`.

The Open Term Loan Manager passes itself as the destination. A Strategy Manager passes its Underlying Strategy, so assets never sit in the Strategy Manager. The Pool approves the Pool Manager for an unlimited amount of its asset at construction and the approval cannot be revoked, so the cap is the only limit on the transfer. The Pool Delegate cover check and the locked-liquidity check of earlier versions are gone.

## Accounting

`totalAssets` is the Pool's asset balance plus the sum of every position. `unrealizedLosses` is the sum of every position's unrealized loss, capped at `totalAssets`. For each entry in `strategyList` the Pool Manager calls `assetsOf(address(this))` and `unrealizedLossesOf(address(this))` when `isStrategyManager` is set, otherwise `assetsUnderManagement()` and `unrealizedLosses()`. [Pool Accounting](pool-accounting.md) has the formulas.

## Defaults

The Pool Delegate, the Governor or the Operational Admin calls `triggerDefault(loan)`. The Pool Manager reads the loan's `lender()`, which is the Open Term Loan Manager, and calls `triggerDefault(loan, address(0))` on it. Open-term loans hold no collateral, so there is no liquidator and the default completes in one transaction. The Pool Manager emits `CollateralLiquidationFinished(loan, losses)`. See [Defaults](../strategies/open-term-loans/defaults.md).

## Configuration and activation

The Pool Deployer calls the setters and then `completeConfiguration()` within the deployment transaction, which sets `configured` to true. Before that, every setter is open to the caller. After it, access tightens as the table below shows. `setWithdrawalManager` only works before configuration, so a Pool's Withdrawal Manager is fixed for life.

A Pool accepts deposits only once `active` is true. The Governor or Operational Admin sets this by calling `activatePoolManager` on Globals, which records the Pool Delegate as the owner of this Pool Manager and calls `setActive(true)`. See [Creating a Pool](pool-creation.md).

## Pool Delegate transfer

The Operational Admin nominates a new Pool Delegate with `setPendingPoolDelegate`. The nominee calls `acceptPoolDelegate`, which updates `ownedPoolManager` in Globals and replaces `poolDelegate`.

## Multicall

`multicall(bytes[] data)` delegatecalls each payload into the Pool Manager itself and bubbles up any revert. It has no access control of its own. Each inner call keeps its own check. It lets an admin set several caps, or attach a Strategy Manager and cap it, in one transaction.

## Pool Delegate cover

v7 removes Pool Delegate cover. `depositCover`, `withdrawCover` and the cover contract are gone, and the storage slot is kept as `__deprecated_poolDelegateCover`. `hasSufficientCover()` remains as a `pure` function that always returns `true`, because the Open Term Loan Manager only pays delegate management fees when it is true.

## Access control

| Function | Allowed callers |
| --- | --- |
| `addStrategy` | Anyone before configuration, Governor after |
| `addStrategyManager` | Anyone before configuration, Governor after |
| `removeStrategyManager` | Operational Admin |
| `setStrategyCap` | Anyone before configuration, then Pool Delegate, Governor or Operational Admin |
| `setLiquidityCap` | Anyone before configuration, then Pool Delegate, Governor or Operational Admin |
| `setDelegateManagementFeeRate` | Anyone before configuration, then Pool Delegate, Governor or Operational Admin |
| `setPoolPermissionManager` | Anyone before configuration, then Pool Delegate, Governor or Operational Admin |
| `setWithdrawalManager` | Anyone before configuration, nobody after |
| `completeConfiguration` | Anyone, once |
| `setPendingPoolDelegate` | Operational Admin |
| `acceptPoolDelegate` | The pending Pool Delegate |
| `setActive` | Globals |
| `triggerDefault` | Pool Delegate, Governor or Operational Admin |
| `requestFunds` | A registered strategy or Strategy Manager |
| `requestRedeem`, `processRedeem`, `removeShares` | Pool |
| `multicall` | Anyone, each inner call enforces its own check |
| `upgrade` | Security Admin |

"Anyone before configuration" means the Pool Deployer in practice, because deployment and configuration happen in one transaction. Every function above except `multicall` also reverts while Globals has it paused.

## Upgrading to v5.0.0

Existing Pool Managers upgrade through `MaplePoolManagerMigratorV500`. The migrator walks `strategyList` from the end, keeps every strategy deployed from an `OT_LOAN_MANAGER_FACTORY`, and removes everything else, clearing `isStrategy` and emitting `StrategyRemoved` for each. A fixed-term loan manager must report zero `assetsUnderManagement` or the migration reverts with `PMM:NON_ZERO_AUM`. Legacy Aave and Sky strategies are removed without a balance check, so they are emptied before the upgrade. The migrator sets no cap on the kept Open Term Loan Manager, so its `strategyCapOf` is `0` and loan funding reverts with `PM:RF:STRATEGY_CAP` until a cap is set. The v7 upgrade sets it to `type(uint256).max`. Upgrading is optional. A Pool Manager that stays on its previous implementation keeps its strategies and its cyclical Withdrawal Manager.
