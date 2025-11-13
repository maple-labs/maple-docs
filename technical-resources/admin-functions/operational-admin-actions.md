# Overview

The `operationalAdmin` complements the Governor's capabilities by having the authority to execute essential operational functions for routine protocol management. The role holds limited powers compared to the Governor, ensuring a balance between operational efficiency and security.

The Governor retains the exclusive authority to appoint or replace the operationalAdmin at any time.

# Operational Admin Functions

## Globals

* `activatePoolManager`
* `setBootstrapMint`
* `setCanDeployFrom`
* `setMaxCoverLiquidationPercent`
* `setMinCoverAmount`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setValidInstanceOf`
* `setValidPoolDelegate`
* `setValidBorrower`

## Pool Manager

* `finishCollateralLiquidation`
* `setPendingPoolDelegate`
* `triggerDefault`

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

## Withdrawal Manager (Queue)

* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`
