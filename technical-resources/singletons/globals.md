# Maple Globals

`MapleGlobals` (v5.0.0 in v7) is the singleton that stores protocol-wide configuration: the admin roles, the Pool Delegate and Strategy Delegate registries, the instance allowlists, platform fee rates, bootstrap amounts, timelock parameters and pause switches. Every other contract reads it live on each privileged call. The full function list is in the [Globals interface](../interfaces/globals.md).

## Roles

| Role | Storage | Set by |
|---|---|---|
| Governor | proxy admin slot, read through `governor()` | `setPendingGovernor` by the Governor, then `acceptGovernor` by the pending Governor |
| Operational Admin | `operationalAdmin` | Governor, `setOperationalAdmin` |
| Security Admin | `securityAdmin` | Governor, `setSecurityAdmin` |
| Maple Treasury | `mapleTreasury` | Governor, `setMapleTreasury` |
| Migration Admin | `migrationAdmin` | Governor, `setMigrationAdmin`. Read only by the Pool Manager initializer when a Pool starts with a non-zero supply |

The Governor is the `GovernorTimelock` contract, so every Governor-only function below executes after that contract's delay. See [Governor Timelock](governor-timelock.md).

Three modifiers gate the setters: `onlyGovernor`, `onlyGovernorOrOperationalAdmin` and `onlyGovernorOrSecurityAdmin`. The [Admin Functions](../admin-functions/README.md) pages list which functions each role reaches.

## Delegate registries

Globals binds each delegate to at most one managed contract. v7 adds a Strategy Delegate registry alongside the Pool Delegate one, with the same shape.

| | Pool Delegate | Strategy Delegate |
|---|---|---|
| Storage | `poolDelegates[account]` with `isPoolDelegate` and `ownedPoolManager` | `strategyDelegates[account]` with `isStrategyDelegate` and `ownedStrategyManager` |
| Approve or revoke | `setValidPoolDelegate` | `setValidStrategyDelegate` |
| Activate the owned instance | `activatePoolManager` | `activateStrategyManager` |
| Move the binding | `transferOwnedPoolManager` | `transferOwnedStrategyManager` |
| Views | `isPoolDelegate`, `ownedPoolManager` | `isStrategyDelegate`, `ownedStrategyManager` |

The Governor or Operational Admin calls the approve and activate functions. The code enforces these rules:

* `setValidStrategyDelegate` rejects the zero address and refuses to revoke a delegate that still owns a Strategy Manager (`MG:SVSD:OWNS_STRATEGY_MANAGER`). `setValidPoolDelegate` behaves the same way for Pool Managers.
* `activateStrategyManager` checks that the Strategy Manager came from a factory registered under `STRATEGY_MANAGER_FACTORY`, that its `strategyDelegate()` is approved and owns nothing yet, then records the binding and calls `setActive(true)` on the Strategy Manager. A Strategy Manager rejects funding until this call happens.
* `transferOwnedStrategyManager(from, to)` is called by the Strategy Manager, not by an admin. `msg.sender` must be the Strategy Manager that `from` owns, and `to` must be an approved delegate that owns nothing. The Strategy Manager calls it from `acceptStrategyDelegate()`, which completes the handover that the Operational Admin starts with `setPendingStrategyDelegate()`.

The registry also gates deployment. `MapleStrategyDeployer.deploy()` and the Strategy Manager initializer both require `isStrategyDelegate(msg.sender)`, so only an approved Strategy Delegate can create a Strategy Manager. See [Strategy Deployer](../strategies/strategy-deployer.md) and [Strategy Manager](../strategies/strategy-manager.md).

## Instance allowlists

`isInstanceOf[key][address]` is a generic allowlist keyed by a `bytes32` label. The Governor or Operational Admin writes it with `setValidInstanceOf`. Contracts read it to decide whether a factory, contract or account is trusted for a given purpose. v7 contracts read these keys:

| Key | Read by | Purpose |
|---|---|---|
| `POOL_MANAGER_FACTORY` | Globals, Strategy Manager, Pool Deployer, Loan Manager and Withdrawal Manager initializers | Identifies genuine Pool Managers |
| `STRATEGY_MANAGER_FACTORY` | Globals, Pool Manager, Strategy Deployer, Liquidity Router, strategy initializers | Identifies genuine Strategy Managers |
| `UNDERLYING_STRATEGY_FACTORY` | Strategy Deployer, Strategy Manager | Factories allowed to produce the strategy behind a Strategy Manager |
| `STRATEGY_FACTORY` | Pool Manager, Globals | Factories for pool-owned strategies such as Loan Managers |
| `LIQUIDITY_BOT` | Strategy Manager | Bots that call the Strategy Manager directly |
| `LIQUIDITY_ROUTER` | Strategy Manager | The `MapleLiquidityRouter` contract |
| `LIQUIDITY_ROUTER_BOT` | Liquidity Router | Bots allowed to call `executeActions` |
| `MAPLE_MANAGED_WALLET` | Allocation Strategy | Wallets that may deploy, return and report yield on capital |
| `STRATEGY_VAULT` | Aave V3 and Sky strategies | The aToken or sUSDS vault a strategy may hold |
| `PSM` | Sky strategy | The Sky PSM used to swap in and out of USDS |
| `WITHDRAWAL_REDEEMER` | Withdrawal Manager | Bots that process the redemption queue |
| `WITHDRAWAL_MANAGER_QUEUE_FACTORY` | Pool Manager, Pool Deployer | Identifies genuine Withdrawal Managers |
| `POOL_PERMISSION_MANAGER` | Pool Manager, Pool Deployer | The Pool Permission Manager a Pool may use |
| `OT_LOAN_FACTORY`, `OT_LOAN_MANAGER_FACTORY`, `OT_REFINANCER`, `BORROWER_ACTIONS` | Open Term Loan and Loan Manager | Loan factories, refinancer and borrower helper contracts |
| `LOAN_FACTORY` | Globals | Lets valid borrowers deploy from loan factories |

`FT_LOAN_MANAGER_FACTORY`, `LIQUIDATOR_FACTORY` and `WITHDRAWAL_MANAGER_FACTORY` remain for the deprecated `isFactory` and `isPoolDeployer` views that pre-v7 factories still call.

`setValidMapleManagedWallet(wallet, isValid)` writes the `MAPLE_MANAGED_WALLET` key through `setValidInstanceOf`, so it carries the same Governor-or-Operational-Admin check and the same function grants and revokes. See [Managed Wallets](../strategies/allocation-strategy/managed-wallets.md).

## Deployment permissions

Every v7 factory checks `globals.canDeploy(msg.sender)` in `createInstance`, either directly or, for the Pool Manager Factory, through the deprecated `isPoolDeployer` view that now forwards to it. `canDeployFrom(factory, caller)` returns true when:

* `setCanDeployFrom(factory, caller, true)` has allowed the pair (Governor or Operational Admin), or
* the factory is a `LOAN_FACTORY` and the caller is a valid borrower, or
* the factory is a `STRATEGY_FACTORY` and the caller is a Pool Manager.

`setValidPoolDeployer` is deprecated and can only disable an address.

## Fees and bootstrap amounts

`setPlatformManagementFeeRate`, `setPlatformOriginationFeeRate` and `setPlatformServiceFeeRate` store a rate per Pool Manager, each capped at `HUNDRED_PERCENT` (`100_0000`). The Governor or Operational Admin sets them. Strategy protocol fee rates live on each strategy instead, see [Strategies](../strategies/README.md).

`bootstrapMint[asset]` is the permanent dead-address deposit that protects a new vault's share price. The Pool reads it once at deployment and mints that many shares to `address(0)` on the first deposit. In v7 the Strategy Deployer reads the same value: `deploy()` pulls `bootstrapMint(fundsAsset)` from the Strategy Delegate into the underlying strategy, and `completeConfiguration` records the resulting shares against `address(0)`. The value must be non-zero for an asset before its first Strategy Manager is deployed, because a Strategy Manager deployed while it is zero has no bootstrap protection.

## Timelocks

Globals holds the scheduled-call mechanism that Pool Delegates use for upgrades: `scheduleCall`, `isValidScheduledCall`, `unscheduleCall`, `setTimelockWindow`, `setTimelockWindows` and `setDefaultTimelockParameters`. In v7 only the Loan Manager and Withdrawal Manager `upgrade` functions check it. See [Timelocked Functions](../admin-functions/timelocks.md).

## Pausing

The Governor or Security Admin controls three switches:

* `setProtocolPause(bool)` pauses every contract.
* `setContractPause(contract, bool)` pauses one instance.
* `setFunctionUnpause(contract, sig, bool)` re-enables one function on a paused contract.

Contracts call `isFunctionPaused(msg.sig)` in their `whenNotPaused` modifier, which evaluates to `(protocolPaused || isContractPaused[contract]) && !isFunctionUnpaused[contract][sig]`. See [Emergency Protocol Pause](../security/emergency-protocol-pause.md).

## Parameters without a v7 consumer

`setPriceOracle`, `setManualOverridePrice` and `getLatestPrice`, the cover setters `setMinCoverAmount` and `setMaxCoverLiquidationPercent`, and `setValidCollateralAsset` remain in the contract and are still callable, but no v7 contract reads the values they set.

## Proxy

Globals uses a `NonTransparentProxy` rather than the proxy-factory pattern used elsewhere. The Governor upgrades it by calling `setImplementation` on the proxy, which stays possible even if the current implementation is broken.
