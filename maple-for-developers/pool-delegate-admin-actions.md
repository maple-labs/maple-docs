# Overview

The Pool Delegate is responsible for administrating a Pool which involves funding Loans, defaulting/impairing Loans and configuring various parameters. Below is a detailed list of the functions a Pool Delegate can call. 

# Pool Delegate Callable Functions 

## Globals
* `transferOwnedPoolManager`

## PoolManager
* `setPendingPoolDelegate`
* `acceptPendingPoolDelegate`
* `addLoanManager`
* `removeLoanManager`
* `setAllowedLender`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setOpenToPublic`
* `setWithdrawalManager`
* `acceptNewTerms`
* `fund`
* `withdrawCover`
* `setAllowedSlippage`
* `setMinRatio`
* `impairLoan`
* `removeLoanImpairment`
* `finishCollateralLiquidation`
* `triggerDefault`

## LoanManager
* `updateAccounting`

## WithdrawalManager
* `setExitConfig`
