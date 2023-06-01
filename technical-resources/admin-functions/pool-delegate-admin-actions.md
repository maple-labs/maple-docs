# Overview

The Pool Delegate is responsible for administrating a Pool which involves funding Loans, defaulting/impairing Loans and configuring various parameters. Below is a detailed list of the functions a Pool Delegate can call.

# Pool Delegate Callable Functions

## PoolManager

* `upgrade`
* `acceptPoolDelegate`
* `setPendingPoolDelegate`
* `addLoanManager`
* `setAllowedLender`
* `setDelegateManagementFeeRate`
* `setIsLoanManager`
* `setLiquidityCap`
* `setOpenToPublic`
* `finishCollateralLiquidation`
* `triggerDefault`
* `withdrawCover`

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

## WithdrawalManager

* `upgrade`
* `setExitConfig`
