# November 2026 Release

The November 2026 release replaces the one-pool-one-strategy model with shared strategies. A new Strategy Manager sits between Pools and an Underlying Strategy, so several Pool Managers can fund the same position and share its profit and loss in proportion to the shares they hold. This page lists what the release adds, upgrades and removes, which Pools it upgrades, and the procedure that deploys the contracts and upgrades those Pools. The procedure follows the deployment script (`scripts/ModularReleaseDeployment.s.sol`) and the fork test that runs the full procedure against mainnet state (`tests/protocol-upgrade/modular-release/`) in the `maple-core-v2-private` repository.

## Summary

Before the November 2026 release, a Pool Manager deployed every strategy it used for its Pool alone. Now a Pool Manager holds two kinds of position:

* Its Open Term Loan Manager, which only that Pool funds.
* Strategy Managers, where the Pool Manager is one of several funders. Each Strategy Manager is paired with one Underlying Strategy (Aave V3, Sky or Allocation) and tracks each Pool's position with internal, non-tokenised shares.

Share accounting, AUM reporting and caps live in the Strategy Manager and are the same for every strategy. Logic specific to each underlying protocol lives in the Underlying Strategy, so adding an underlying protocol means writing a new Underlying Strategy. Strategy Managers only accept Pool Managers as funders, never Lenders, so KYC, permissioning and redemptions stay in the Pool contracts. See [How Pools Allocate Capital](../strategies/how-pools-allocate-capital.md) for the funding and redemption flows.

## New contracts

| Contract | Module | Version | Purpose |
| --- | --- | --- | --- |
| `MapleStrategyManager`, `MapleStrategyManagerFactory`, `MapleStrategyManagerInitializer` | strategy-manager | v1.0.0 | Pools capital from several Pool Managers into one Underlying Strategy and services redemption requests. See [Strategy Manager](../strategies/strategy-manager.md). |
| `MapleStrategyDeployer` | strategy-manager | v1.0.0 | Deploys a Strategy Manager and its Underlying Strategy in one transaction and performs the bootstrap funding. See [Strategy Deployer](../strategies/strategy-deployer.md). |
| `MapleLiquidityRouter` | strategy-manager | v1.0.0 | Lets a permissioned Liquidity Bot batch fund, request and process actions across Strategy Managers. See [Liquidity Router](../strategies/liquidity-router.md). |
| `MapleAaveV3Strategy`, `MapleAaveV3StrategyFactory`, `MapleAaveV3StrategyInitializer` | defi-strategies | v1.0.0 | Aave V3 and SparkLend Underlying Strategy owned by a Strategy Manager. See [Aave V3 Strategy](../strategies/aave-v3-strategy/README.md). |
| `MapleSkyStrategy`, `MapleSkyStrategyFactory`, `MapleSkyStrategyInitializer` | defi-strategies | v1.0.0 | Sky (PSM and sUSDS) Underlying Strategy owned by a Strategy Manager. See [Sky Strategy](../strategies/sky-strategy/README.md). |
| `MapleAllocationStrategy`, `MapleAllocationStrategyFactory`, `MapleAllocationStrategyInitializer` | allocation-strategy | v1.0.0 | Deploys assets to permissioned Managed Wallets under per-wallet caps and handles yield, impairment and loss recognition. See [Allocation Strategy](../strategies/allocation-strategy/README.md). |
| `MaplePoolManagerMigratorV500` | pool | v5.0.0 | One-off migrator that removes legacy strategies from existing Pool Managers during the v4 to v5 upgrade. |

## Upgraded contracts

| Contract | Module | Version | Factory version | What changed |
| --- | --- | --- | --- | --- |
| `MapleGlobals` | globals | v5.0.0 | n/a (`setImplementation()`) | Adds the Strategy Delegate registry: `setValidStrategyDelegate()`, `activateStrategyManager()`, `transferOwnedStrategyManager()`, `isStrategyDelegate()` and `ownedStrategyManager()`. Adds `setValidMapleManagedWallet()`, which writes the `MAPLE_MANAGED_WALLET` instance key. |
| `MaplePoolManager` | pool | v5.0.0 | 500 | Funds Strategy Managers as well as the Open Term Loan Manager. Adds `addStrategyManager()`, `removeStrategyManager()`, `setStrategyCap()` and `multicall()`. Rewrites `requestFunds()` around a per-strategy cap. `totalAssets()` and `unrealizedLosses()` read `assetsOf()` and `unrealizedLossesOf()` from Strategy Managers. `triggerDefault()` only routes to the Open Term Loan Manager. Pool Delegate Cover is removed. See [Pool Manager](../pools/pool-manager.md). |
| `MaplePoolManagerInitializer` | pool | v5.0.0 | 500 | No longer deploys a Pool Delegate Cover. The Pool is the only contract the Pool Manager creates. |
| `MaplePoolDeployer` | pool | v5.0.0 | n/a (not a proxy) | One queue-only `deployPool()` taking structs. Deploys the Open Term Loan Manager with a caller-supplied salt and cap, and attaches existing Strategy Managers. Cyclical withdrawal managers can no longer be deployed. See [Creating a Pool](../pools/pool-creation.md). |
| `MapleWithdrawalManager` (queue) | withdrawal-manager-queue | v2.0.1 | 201 | `removeSharesById()` now also checks `hasPermission(poolManager, msg.sender, "WM:removeSharesById")` on the Pool Permission Manager and reverts with `WM:RSBI:NOT_ALLOWED`. Storage is unchanged, so the upgrade needs no migrator. Compiler moved to 0.8.34. See [Withdrawal Manager](../pools/withdrawal-manager.md). |

`MaplePoolManagerFactory` and `MapleWithdrawalManagerFactory` are unchanged and keep their mainnet addresses. `MaplePool` is recompiled under 0.8.34 with no functional change. The Pool Permission Manager, Open Term Loan and Open Term Loan Manager are not part of this release.

## Removed functionality

* **Fixed-term loans and the Fixed Term Loan Manager.** The fixed-term loan modules are no longer part of the protocol repository. The migrator removes each Fixed Term Loan Manager from `strategyList` and reverts with `PMM:NON_ZERO_AUM` if it still reports assets under management.
* **Liquidator.** The Pool Manager no longer runs collateral liquidations. `triggerDefault()` calls `triggerDefault()` on the loan's Open Term Loan Manager and emits `CollateralLiquidationFinished`. Globals keeps only a deprecated compatibility shim for the already-deployed `LiquidatorFactory`.
* **Pool Delegate Cover.** `MaplePoolDelegateCover` is deleted along with `depositCover()` and `withdrawCover()`. The storage slot is kept as `__deprecated_poolDelegateCover`, and `hasSufficientCover()` is now `pure` and returns `true` so delegate fees in the loan manager keep flowing.
* **Cyclical withdrawal manager deployments.** The Pool Deployer only deploys queue withdrawal managers, and `setWithdrawalManager()` requires a factory registered under `WITHDRAWAL_MANAGER_QUEUE_FACTORY`. Existing cyclical withdrawal managers on non-upgraded Pools keep working.
* **Legacy per-Pool Aave and Sky strategies.** The migrator removes them from the upgraded Pool Managers without a balance check, so they are drained first. Their replacements are shared Aave V3 and Sky Strategy Managers.
* `setIsStrategy()` is removed from the Pool Manager. `addStrategy()` now takes an explicit `salt` and is restricted to the Governor once the Pool Manager is configured.

## Which Pools are upgraded

The release upgrades six Pool Managers from v4.0.0 to v5.0.0 and their queue Withdrawal Managers from v2.0.0 to v2.0.1:

* syrupUSDC
* syrupUSDT
* syrupUSDG
* Secured Lending USDC
* Secured Lending 2 USDC
* Secured Lending 3 USDC

Every other mainnet Pool stays on its current Pool Manager implementation. There is no forced migration. A non-upgraded Pool keeps its cyclical withdrawal manager, fixed-term loans and cover contract, and the compatibility tests in the release repository exercise deposits, redemptions and loan actions on those Pools after the upgrade. The step-by-step procedure is under [Procedure](#procedure) below.

## Audits

Sherlock and Cantina audited the release. The reports are listed under [Security](../security/security.md#november-2026-release).

## Addresses

The November 2026 release contracts are not yet deployed to mainnet. Addresses will be published on [Deployed Contracts](../protocol-overview/smart-contract-addresses.md) once the procedure has run.

## Actors

| Actor | Role in the procedure |
| --- | --- |
| Deployer | An EOA that deploys every new contract. Its nonce determines the addresses, so it submits nothing else during the procedure. |
| Governor Timelock | The Governor of `MapleGlobals`. The DAO multisig schedules proposals on it, and the Operational Admin executes them after the delay. Used only where Globals or a factory requires the Governor. See [Governor Timelock](../singletons/governor-timelock.md). |
| Operational Admin | Configures Globals, executes timelocked proposals, whitelists Strategy Delegates and Managed Wallets, activates Strategy Managers, and sets the Open Term Loan Manager caps on the upgraded Pool Managers. |
| Security Admin | Upgrades the Pool Managers and Withdrawal Managers. |
| Pool Delegate | Drains the legacy strategies of its Pool before the upgrade and sets strategy caps afterwards. |
| Strategy Delegate | One EOA per Strategy Manager. Deploys the Strategy Manager through the Strategy Deployer and administers it afterwards. |

## Prerequisites

* The Deployer holds enough ETH and compiles with the settings each module expects (0.8.34 for the new and upgraded contracts).
* Every Strategy Delegate account exists, holds at least the bootstrap amount of its strategy's asset (`1e6` units of USDC, USDT or USDG), and has approved the Strategy Deployer to spend it.
* Every Managed Wallet exists. Each Allocation Strategy gets one Managed Wallet.
* The Fixed Term Loan Managers of syrupUSDC, syrupUSDT and Secured Lending USDC report `assetsUnderManagement() == 0` and `unrealizedLosses() == 0`.
* The legacy Aave and Sky strategies of syrupUSDC, syrupUSDT and Secured Lending USDC are drained back to their Pools. The Pool Delegate calls `withdrawFromStrategy()` on each. Dust may remain, and `unrealizedLosses()` must be zero.

## Procedure

```mermaid
flowchart TD
    S1[1. Deploy contracts<br/>Deployer] --> S2[2. Configure Globals<br/>Operational Admin]
    S2 --> S3[3. Upgrade Globals and register factories<br/>Governor Timelock]
    S3 --> S4[4. Deploy and activate Strategy Managers<br/>Strategy Delegates, Operational Admin]
    S4 --> S5[5. Upgrade Pool Managers and Withdrawal Managers<br/>Security Admin, Operational Admin]
    S5 --> S6[6. Attach Strategy Managers to Pools<br/>Governor Timelock]
    S6 --> S7[7. Register Managed Wallets<br/>Operational Admin, Strategy Delegates]
    S7 --> S8[8. Set caps<br/>Pool Delegates, Strategy Delegates]
```

### 1. Deploy contracts

**Actor: Deployer**

The script deploys, in order: the `MapleGlobals` implementation, the Pool Deployer and Strategy Deployer, the Pool Manager implementation, initializer and migrator, the queue Withdrawal Manager implementation and initializer, then the factory, implementation and initializer for the Strategy Manager, Aave V3 Strategy, Sky Strategy and Allocation Strategy, and finally the Liquidity Router. Factories, deployers and the router take the existing `MapleGlobals` proxy address as their only constructor argument. The existing `MaplePoolManagerFactory` and `MapleWithdrawalManagerFactory` are reused. The full contract list with versions is under [New contracts](#new-contracts) and [Upgraded contracts](#upgraded-contracts) above.

### 2. Configure Globals

**Actor: Operational Admin**

One batch of calls on `MapleGlobals`:

* `setValidInstanceOf("STRATEGY_MANAGER_FACTORY", strategyManagerFactory, true)`
* `setValidInstanceOf("UNDERLYING_STRATEGY_FACTORY", factory, true)` for the Aave V3, Sky and Allocation Strategy factories
* `setValidInstanceOf("STRATEGY_VAULT", aUSDG, true)`. The aUSDC, aUSDT and sUSDS vaults are already registered.
* `setValidInstanceOf("LIQUIDITY_ROUTER", liquidityRouter, true)`
* `setCanDeployFrom(factory, poolDeployer, true)` for the Pool Manager and queue Withdrawal Manager factories
* `setCanDeployFrom(factory, strategyDeployer, true)` for the Strategy Manager, Aave V3, Sky and Allocation Strategy factories
* `setBootstrapMint(asset, 1e6)` for USDC, USDT and USDG. This raises the existing USDC and USDT amounts from `1e5`.

### 3. Upgrade Globals and register factories

**Actors: Governor Timelock, then Operational Admin**

The DAO multisig calls `scheduleProposals()` on the Governor Timelock with these calls. After the delay, the Operational Admin calls `executeProposals()` with the same targets and data within the execution window.

| Target | Call |
| --- | --- |
| `MapleGlobals` | `setImplementation(globalsV500Implementation)` |
| `MaplePoolManagerFactory` | `registerImplementation(500, implementation, initializer)`, `setDefaultVersion(500)`, `enableUpgradePath(400, 500, migratorV500)` |
| `MapleWithdrawalManagerFactory` | `registerImplementation(201, implementation, initializer)`, `setDefaultVersion(201)`, `enableUpgradePath(200, 201, address(0))` |
| `MapleStrategyManagerFactory` | `registerImplementation(100, implementation, initializer)`, `setDefaultVersion(100)` |
| `MapleAaveV3StrategyFactory` | `registerImplementation(100, implementation, initializer)`, `setDefaultVersion(100)` |
| `MapleSkyStrategyFactory` | `registerImplementation(100, implementation, initializer)`, `setDefaultVersion(100)` |
| `MapleAllocationStrategyFactory` | `registerImplementation(100, implementation, initializer)`, `setDefaultVersion(100)` |

The Withdrawal Manager upgrade path has no migrator because v2.0.1 changes no storage.

### 4. Deploy and activate Strategy Managers

**Actors: Operational Admin, Strategy Delegates**

1. The Operational Admin calls `setValidStrategyDelegate(delegate, true)` on `MapleGlobals` for each Strategy Delegate.
2. Each Strategy Delegate calls `deploy()` on `MapleStrategyDeployer` with the Strategy Manager factory, the Underlying Strategy factory, a liquidity cap (zero leaves it unset) and the ABI-encoded initializer parameters for that strategy type. The deployer creates the Strategy Manager, creates the Underlying Strategy, wires them together, pulls the bootstrap amount from the delegate into the Underlying Strategy and calls `completeConfiguration()`. See [Strategy Deployer](../strategies/strategy-deployer.md).
3. The Operational Admin calls `activateStrategyManager(strategyManager)` on `MapleGlobals` for each Strategy Manager. Globals records the delegate's `ownedStrategyManager` and calls `setActive(true)` on the Strategy Manager.

The release deploys these Strategy Managers. The Aave V3 and Sky Strategy Managers are optional and may be left out of the mainnet run.

| Strategy Manager | Underlying Strategy | Asset |
| --- | --- | --- |
| Aave Strategy USDC, Aave Strategy USDT, Aave Strategy USDG | Aave V3 | USDC, USDT, USDG |
| Sky Strategy USDC | Sky | USDC |
| LP DEX, Cross Pool, TBills, PYUSD | Allocation | one each for USDC, USDT and USDG |
| Spreads USDT | Allocation | USDT |

### 5. Upgrade Pool Managers and Withdrawal Managers

**Actors: Security Admin, then Operational Admin**

1. Confirm the prerequisites on the Fixed Term Loan Managers and legacy strategies still hold.
2. Call `upgrade(500, "")` on the six Pool Managers listed under [Which Pools are upgraded](#which-pools-are-upgraded). The factory runs `MaplePoolManagerMigratorV500`, which walks `strategyList` in reverse, keeps every strategy deployed from an `OT_LOAN_MANAGER_FACTORY`, requires zero AUM on anything from an `FT_LOAN_MANAGER_FACTORY`, and removes everything else, emitting `StrategyRemoved` for each. After the upgrade only the Open Term Loan Manager remains in `strategyList`. `totalAssets()` may fall by the dust left in the legacy strategies, and `unrealizedLosses()` is unchanged.
3. Call `upgrade(201, "")` on each of the six queue Withdrawal Managers. Only the implementation changes, and `totalShares()` is unchanged.
4. The Operational Admin calls `setStrategyCap(openTermLoanManager, type(uint256).max)` on each of the six Pool Managers. The cap is zero after the upgrade, and `requestFunds()` reverts with `PM:RF:STRATEGY_CAP` above the cap, so without this call the Open Term Loan Manager cannot fund loans.

### 6. Attach Strategy Managers to Pools

**Actors: Governor Timelock, then Operational Admin**

`addStrategyManager()` on a configured Pool Manager is Governor-only, so the DAO multisig schedules one `addStrategyManager(strategyManager)` call per attachment and the Operational Admin executes them after the delay. The Pool Manager checks that the Strategy Manager's factory is registered under `STRATEGY_MANAGER_FACTORY` and that the factory created it.

| Strategy Manager | syrupUSDC | syrupUSDT | syrupUSDG | Secured Lending USDC |
| --- | --- | --- | --- | --- |
| Aave Strategy (optional) | USDC | USDT | USDG | USDC |
| Sky Strategy USDC (optional) | yes | | | yes |
| LP DEX | USDC | USDT | USDG | |
| Cross Pool | USDC | USDT | USDG | |
| TBills | USDC | USDT | USDG | USDC |
| PYUSD | USDC | USDT | USDG | USDC |
| Spreads USDT | | yes | | |

syrupUSDC and Secured Lending USDC share the USDC Strategy Managers. Secured Lending 2 USDC and Secured Lending 3 USDC get no Strategy Managers, so their `strategyList` holds only their Open Term Loan Manager.

### 7. Register Managed Wallets

**Actors: Operational Admin, Strategy Delegates**

1. The Operational Admin calls `setValidMapleManagedWallet(wallet, true)` on `MapleGlobals` for each Managed Wallet. This writes the `MAPLE_MANAGED_WALLET` instance key.
2. Each Allocation Strategy's Strategy Delegate calls `setPermissions([wallet], [true], [true], [true])` on the `MapleAllocationStrategy`, granting the wallet permission to deploy assets, return assets and realize yield. See [Managed Wallets](../strategies/allocation-strategy/managed-wallets.md).

The Liquidity Router only accepts calls from accounts registered under `LIQUIDITY_ROUTER_BOT` in Globals. Registering the Liquidity Bot is a separate Operational Admin action and is not part of the tested procedure.

### 8. Set caps

Apart from the Open Term Loan Manager caps set in step 5, `strategyCapOf` on each Pool Manager and `strategyLiquidityCap` on each Strategy Manager stay at zero, which blocks funding until the delegates raise them. `deploymentCapOf` on the Allocation Strategy is also zero, which blocks Managed Wallet drawdowns. A zero `poolManagerCapOf` means no per-Pool limit. Caps can change at any time after the procedure.

| Cap | Contract and function | Allowed callers |
| --- | --- | --- |
| Per-strategy cap on a Pool | `MaplePoolManager.setStrategyCap(strategy, cap)` | Pool Delegate, Governor or Operational Admin |
| Total liquidity a Strategy Manager accepts | `MapleStrategyManager.setStrategyLiquidityCap(cap)` | Strategy Delegate or Operational Admin |
| Liquidity a Strategy Manager accepts from one Pool | `MapleStrategyManager.setPoolManagerCap(poolManager, cap)` | Strategy Delegate or Operational Admin |
| Assets a Managed Wallet may hold | `MapleAllocationStrategy.setDeploymentCaps([wallet], [cap])` | Strategy Delegate or Security Admin |

See [How Pools Allocate Capital](../strategies/how-pools-allocate-capital.md) for how the three Pool and Strategy Manager caps interact.

## Verification

The fork test asserts the following after the procedure, and the same checks apply on mainnet.

* **Globals.** The implementation slot holds the v5.0.0 implementation, the instance keys and `canDeployFrom()` grants from step 2 are set, and `bootstrapMint()` is `1e6` for USDC, USDT and USDG. Each Strategy Delegate passes `isStrategyDelegate()` and `ownedStrategyManager()` returns its Strategy Manager. Each Managed Wallet is valid under `MAPLE_MANAGED_WALLET`.
* **Factories.** `implementationOf()`, `defaultVersion()` and `upgradeEnabledForPath()` return the values registered in step 3.
* **Pool Managers and Withdrawal Managers.** `implementation()` points at the v5.0.0 and v2.0.1 implementations, `active()` and `configured()` are true, each Pool Manager returns `type(uint256).max` from `strategyCapOf(openTermLoanManager)`, and `strategyList` holds only the Open Term Loan Manager plus the attached Strategy Managers.
* **Strategy Managers.** `active()` and `configured()` are true, `sharesOf(address(0))` is within 3 units of the bootstrap amount to allow for rounding, `totalShares()` equals `sharesOf(address(0))`, `assetsUnderManagement()` is at least the bootstrap amount and `unrealizedLosses()` is zero. Each Underlying Strategy reports the factory, asset, delegate and fee rates it was deployed with.
* **End to end.** A Lender deposits into each upgraded Pool, requests a redemption and is paid out. Each Pool then funds every Strategy Manager attached to it, requests a partial redemption and receives the assets back, with `assetsOf()`, `sharesOf()`, `assetsUnderManagement()` and `totalShares()` moving by the expected amounts.
* **Non-upgraded Pools.** Lenders can still deposit, request and redeem on every Pool that stays on its old implementation, and the AQRU Pool can still fund, call, impair and refinance loans.
