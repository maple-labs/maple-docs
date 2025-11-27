# Overview

The Governor is the on‑chain `GovernorTimelock` contract managed by a multisig (and other designated roles). It controls administrative functions in the protocol. See `technical-resources/singletons/governor-timelock.md` for scheduling and execution flows.


# Governor-Permissioned Functions

## Globals

* `acceptGovernor`
* `activatePoolManager`
* `setBootstrapMint`
* `setCanDeployFrom`
* `setContractPause`
* `setDefaultTimelockParameters`
* `setFunctionUnpause`
* `setManualOverridePrice`
* `setMapleTreasury`
* `setMaxCoverLiquidationPercent`
* `setMigrationAdmin`
* `setMinCoverAmount`
* `setOperationalAdmin`
* `setPendingGovernor`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setPriceOracle`
* `setProtocolPause`
* `setSecurityAdmin`
* `setTimelockWindow`
* `setTimelockWindows`
* `setValidBorrower`
* `setValidCollateralAsset`
* `setValidInstanceOf`
* `setValidPoolAsset`
* `setValidPoolDelegate`
* `setValidPoolDeployer`
* `unscheduleCall`

Note: `setValidPoolDeployer` is deprecated for enabling deployers and only supports disabling. Use `setCanDeployFrom(factory, account, true)` together with `setValidInstanceOf(<FACTORY_KEY>, factory, true)` to allow deployments.

## PoolManager

* `addStrategy`
* `finishCollateralLiquidation`
* `setDelegateManagementFeeRate`
* `setIsStrategy`
* `setLiquidityCap`
* `setPendingPoolDelegate`
* `setPoolPermissionManager`
* `setWithdrawalManager` (only before initial configuration; callable prior to `completeConfiguration`)
* `triggerDefault`

## Fixed Term LoanManager

* `impairLoan`
* `removeLoanImpairment`
* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`

## Open Term Loan

* `skim`

## Open Term Loan Manager

* `impairLoan`
* `removeLoanImpairment`

## Pool Permission Manager

* `configurePool`
* `setLenderAllowlist`
* `setLenderBitmaps`
* `setPermissionAdmin`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

## Strategies Contracts

* `claimRewards` (Aave Strategy only)
* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`
* `setPsm` (Sky Strategy only)

## Upgrading Contracts

The Governor can upgrade the following contracts:
* Globals
* Liquidator
* Withdrawal Manager
