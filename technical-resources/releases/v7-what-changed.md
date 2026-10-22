# v7 Release: What Changed

v7 replaces the one-pool-one-strategy model with shared strategies. A new Strategy Manager sits between Pools and an Underlying Strategy, so several Pool Managers can fund the same position and share its profit and loss in proportion to the shares they hold. This page lists what the release adds, upgrades and removes, and which Pools it upgrades.

## Summary

Before v7, a Pool Manager deployed and owned every strategy it used. In v7 a Pool Manager holds two kinds of position:

* Strategies it owns outright. After v7 the only owned strategy is the Open Term Loan Manager.
* Strategy Managers, where the Pool Manager is one of several funders. Each Strategy Manager owns one Underlying Strategy (Aave V3, Sky or Allocation) and tracks each Pool's position with internal, non-tokenised shares.

Share accounting, AUM reporting and caps live in the Strategy Manager and are the same for every strategy. Venue-specific logic lives in the Underlying Strategy, so adding a venue means writing a new Underlying Strategy. Strategy Managers only accept Pool Managers as funders, never Lenders, so KYC, permissioning and redemptions stay in the Pool contracts. See [How Pools Allocate Capital](../strategies/how-pools-allocate-capital.md) for the funding and redemption flows.

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
| `MaplePoolManager` | pool | v5.0.0 | 500 | Funds Strategy Managers as well as owned strategies. Adds `addStrategyManager()`, `removeStrategyManager()`, `setStrategyCap()` and `multicall()`. Rewrites `requestFunds()` around a per-strategy cap. `totalAssets()` and `unrealizedLosses()` read `assetsOf()` and `unrealizedLossesOf()` from Strategy Managers. `triggerDefault()` only routes to the Open Term Loan Manager. Pool Delegate Cover is removed. See [Pool Manager](../pools/pool-manager.md). |
| `MaplePoolManagerInitializer` | pool | v5.0.0 | 500 | No longer deploys a Pool Delegate Cover. The Pool is the only contract the Pool Manager creates. |
| `MaplePoolDeployer` | pool | v5.0.0 | n/a (not a proxy) | One queue-only `deployPool()` taking structs. Deploys owned strategies with caller-supplied salts and caps, and attaches existing Strategy Managers. Cyclical withdrawal managers can no longer be deployed. See [Creating a Pool](../pools/pool-creation.md). |
| `MapleWithdrawalManager` (queue) | withdrawal-manager-queue | v2.0.1 | 201 | `removeSharesById()` now also checks `hasPermission(poolManager, msg.sender, "WM:removeSharesById")` on the Pool Permission Manager and reverts with `WM:RSBI:NOT_ALLOWED`. Storage is unchanged, so the upgrade needs no migrator. Compiler moved to 0.8.34. See [Withdrawal Manager](../pools/withdrawal-manager.md). |

`MaplePoolManagerFactory` and `MapleWithdrawalManagerFactory` are unchanged and keep their mainnet addresses. `MaplePool` is recompiled under 0.8.34 with no functional change. The Pool Permission Manager, Open Term Loan and Open Term Loan Manager are not part of this release.

## Removed functionality

* **Fixed-term loans and the Fixed Term Loan Manager.** The fixed-term loan modules are no longer part of the protocol repository. The migrator removes each Fixed Term Loan Manager from `strategyList` and reverts with `PMM:NON_ZERO_AUM` if it still reports assets under management.
* **Liquidator.** The Pool Manager no longer runs collateral liquidations. `triggerDefault()` calls `triggerDefault()` on the loan's Open Term Loan Manager and emits `CollateralLiquidationFinished`. Globals keeps only a deprecated compatibility shim for the already-deployed `LiquidatorFactory`.
* **Pool Delegate Cover.** `MaplePoolDelegateCover` is deleted along with `depositCover()` and `withdrawCover()`. The storage slot is kept as `__deprecated_poolDelegateCover`, and `hasSufficientCover()` is now `pure` and returns `true` so delegate fees in the loan manager keep flowing.
* **Cyclical withdrawal manager deployments.** The Pool Deployer only deploys queue withdrawal managers, and `setWithdrawalManager()` requires a factory registered under `WITHDRAWAL_MANAGER_QUEUE_FACTORY`. Existing cyclical withdrawal managers on non-upgraded Pools keep working.
* **Legacy pool-owned Aave and Sky strategies.** The migrator removes them from the upgraded Pool Managers without a balance check, so they are drained first. Their replacements are shared Aave V3 and Sky Strategy Managers.
* `setIsStrategy()` is removed from the Pool Manager. `addStrategy()` now takes an explicit `salt` and is restricted to the Governor once the Pool Manager is configured.

## Which Pools are upgraded

The release upgrades four Pool Managers from v4.0.0 to v5.0.0 and their queue Withdrawal Managers from v2.0.0 to v2.0.1:

* syrupUSDC
* syrupUSDT
* syrupUSDG
* Secured Lending USDC

Every other mainnet Pool stays on its current Pool Manager implementation. There is no forced migration. A non-upgraded Pool keeps its cyclical withdrawal manager, fixed-term loans and cover contract, and the compatibility tests in the release repository exercise deposits, redemptions and loan actions on those Pools after the upgrade. The step-by-step procedure is on [v7 Release: Deployment and Upgrade](v7-deployment-and-upgrade.md).

## Audits

Sherlock and Cantina audited the release. The reports are listed under [Security](../security/security.md#v7-release-november-2026).

## Addresses

The v7 contracts are not yet deployed to mainnet. Addresses will be published on [Deployed Contracts](../protocol-overview/smart-contract-addresses.md) once the procedure has run.
