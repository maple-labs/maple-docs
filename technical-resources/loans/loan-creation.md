## Maple Loan Factory

Loans are proxy contracts that point to a specific implementation. Borrowers that want to create loans on the Maple ecosystem need to do so via the `MapleLoanFactory` contract, which is responsible for holding information on the current version of loans, as well the possible upgradeability paths.

## Loan Creation Pre-Requisites

The following pre-requisites must be met before the creation of a Loan.

1. The Borrower must be set as valid in the MapleGlobals allowlist.
2. The asset used for the funding of the Loan must be set as valid by the Governor in MapleGlobals.

## Loan Initialization Parameters

* `borrower` - The address of the borrower.
* `feeManager` - The address of the entity responsible for storing and calculating loan fees. ([See here](https://github.com/maple-labs/maple-core-v2/wiki/FeeManager))
* `collateralAsset` - The address of the asset used as collateral.
* `fundsAsset` - The address of asset that the loan is denominated in.
* `gracePeriod` - The amount of time that the lender needs to wait before triggering a default on a late loan.\
* `paymentInterval` - The amount of seconds between each loan payment.
* `payments` - The amount of payments in the loan term.
* `collateralRequired` - The nominal amount of the collateral asset.
* `principalRequested` - The nominal amount of principal of the fundsAsset.
* `endingPrincipal`- The expected amount of principal to be paid at the end term. This defines the amortization rate of the loan.
* `interestRate` - The annualized interest rate.
* `closingFeeRate` - The rate used to calculate closing a loan early.
* `lateFeeRate` - A fee rate applied on principal amount on late payments.
* `lateInterestPremium` - A premium added on top of the interest rate for late payments.
* `delegateOriginationFee` - A nominal amount of funds asset payment on the origination to the pool delegate.
* `delegateServiceFee` - A nominal amount of funds assets that is added on every payment destined to the pool delegate.
