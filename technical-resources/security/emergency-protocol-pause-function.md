As a security assurance for the protocol, in case of emergencies, the Governor has the ability to trigger a global pause, which stops all main actions from being executed. In this page we outline the functions that cannot be called in the event the protocol is paused. Note this document covers functions that are directly paused so if another contract calls a paused function that function is also implicitly paused, for example redemption-related functions in the Pool contract.

## LoanManager

- `upgrade()`
- `updateAccounting()`

## PoolManager

- `setImplementation()`
- `upgrade()`
- `acceptPendingPoolDelegate()`
- `setPendingPoolDelegate()`
- `setActive()`
- `setAllowedSlippage()`
- `setMinRatio()`
- `addLoanManager()`
- `removeLoanManager()`
- `setAllowedLender()`
- `setDelegateManagementFeeRate()`
- `setLiquidityCap()`
- `setOpenToPublic()`
- `setWithdrawalManager()`
- `acceptNewTerms()`
- `fund()`
- `impairLoan()`
- `removeLoanImpairment()`
- `finishCollateralLiquidation()`
- `triggerDefault()`
- `processRedeem()` - Note this means users cannot withdraw from the pool contract
- `removeShares()`  - Note if a user is in a withdrawal queue they will not be able to get their shares back
- `requestRedeem()` - Note this means users cannot be added to the withdrawal queue from the pool contract
- `depositCover()`
- `withdrawCover()`

## MapleLoan

- `upgrade()`
- `acceptBorrower()`
- `closeLoan()`
- `drawdownFunds()`
- `makePayment()`
- `postCollateral()`
- `proposeNewTerms()`
- `removeCollateral()`
- `returnFunds()`
- `setPendingBorrower()`
- `acceptLender()`
- `rejectNewTerms()`
- `skim()`

## Liquidator

- `upgrade()`
- `liquidatePortion()`

## WithdrawalManager

- `upgrade()`
- `setExitConfig()`
