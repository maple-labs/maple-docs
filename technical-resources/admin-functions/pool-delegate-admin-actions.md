# Overview

The Pool Delegate is responsible for administrating a Pool which involves funding Loans, defaulting/impairing Loans and configuring various parameters. Below is a detailed list of the functions a Pool Delegate can call.

# Pool Delegate Callable Functions

## PoolManager

* `upgrade`
* `acceptPoolDelegate`
* `setPendingPoolDelegate`
* `addStrategy`
* `setDelegateManagementFeeRate`
* `setIsStrategy`
* `setLiquidityCap`
* `setPoolPermissionManager`
* `setWithdrawalManager` (only before initial configuration; callable prior to `completeConfiguration`)
* `finishCollateralLiquidation`
* `triggerDefault`

## FixedTermLoanManager

* `upgrade`
* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`
* `acceptNewTerms`
* `fund`
* `rejectNewTerms`
* `impairLoan`
* `removeLoanImpairment`

## OpenTermLoanManager

* `upgrade`
* `fund`
* `proposeNewTerms`
* `rejectNewTerms`
* `callPrincipal`
* `removeCall`
* `impairLoan`
* `removeLoanImpairment`

## Pool Permission Manager

* `configurePool`
* `setLenderAllowlist`
* `setLenderBitmaps`
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

* `upgrade`
* `processEmptyRedemptions`
* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`
