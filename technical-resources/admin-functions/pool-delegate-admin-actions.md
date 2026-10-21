# Overview

The Pool Delegate is responsible for administrating a Pool which involves funding Loans, defaulting/impairing Loans and configuring various parameters. Below is a detailed list of the functions a Pool Delegate can call.

# Pool Delegate Callable Functions

## PoolManager

* `upgrade`
* `acceptPoolDelegate`
* `addStrategy` (only before initial configuration; callable prior to `completeConfiguration`)
* `setDelegateManagementFeeRate` (only before initial configuration; callable prior to `completeConfiguration`)
* `setLiquidityCap` (only before initial configuration; callable prior to `completeConfiguration`)
* `setPoolPermissionManager` (only before initial configuration; callable prior to `completeConfiguration`)
* `setWithdrawalManager` (only before initial configuration; callable prior to `completeConfiguration`)
* `triggerDefault`

## OpenTermLoanManager

* `upgrade`
* `fund`
* `impairLoan`
* `removeLoanImpairment`

## OpenTermLoan

* `proposeNewTerms`
* `rejectNewTerms`
* `callPrincipal`
* `removeCall`

## Pool Permission Manager

* `configurePool`
* `setLenderAllowlist`
* `setLenderBitmaps`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

## Withdrawal Manager (Queue)

* `upgrade`
* `processEmptyRedemptions`
* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`
