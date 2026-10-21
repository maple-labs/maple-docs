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
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setPoolPermissionManager`
* `setWithdrawalManager` (only before initial configuration; callable prior to `completeConfiguration`)
* `triggerDefault`

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

## Upgrading Contracts

The Governor can upgrade the following contracts:
* Globals
* Withdrawal Manager
