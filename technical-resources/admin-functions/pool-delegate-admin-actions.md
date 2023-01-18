# Overview

The Pool Delegate is responsible for administrating a Pool which involves funding Loans, defaulting/impairing Loans and configuring various parameters. Below is a detailed list of the functions a Pool Delegate can call.

# Pool Delegate Callable Functions

## Globals

* `transferOwnedPoolManager`

## PoolManager

* `acceptNewTerms`
* `acceptPendingPoolDelegate`
* `addLoanManager`
* `finishCollateralLiquidation`
* `fund`
* `impairLoan`
* `removeLoanImpairment`
* `removeLoanManager`
* `setAllowedLender`
* `setAllowedSlippage`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setMinRatio`
* `setOpenToPublic`
* `setPendingPoolDelegate`
* `setWithdrawalManager`
* `triggerDefault`
* `withdrawCover`
* `upgrade`

## LoanManager

* `setLoanTransferAdmin`
* `updateAccounting`
* `upgrade`

## WithdrawalManager

* `setExitConfig`
* `upgrade`
