In the protocol, we have two classifications of loans: open-term and fixed-term. Despite their notable distinctions, their underlying usage and functionality are fundamentally the same. They can be summarized as follows:

1. Execution of loan financing.
2. Withdrawal of funded amounts.
3. Management of collateral, when necessary.
4. Computation of payment quantities and timetables (capable of managing both amortized and interest-only payment formats).
5. Conducting repossessions of collateral and leftover amounts in the event of a loan default.
6. Claim of interest and principal from loans.
7. Carrying out refinancing activities when a lender and borrower consent to new terms.
8. Change of loan logic via upgradeability models.

## Deployments
Loans operate as proxy contracts that link to a particular implementation. Borrowers interested in establishing loans within the Maple ecosystem must do so through a Maple Loan Factory contract (FixedTermLoanFactory or OpenTermLoanFactory). These contracts store details about the current version of loans and potential upgrade paths.

## Loan Creation Pre-Requisites

The following pre-requisites must be met before the creation of a Loan.

1. The Borrower must be set as valid in the MapleGlobals allowlist.
2. The Borrower must be set as a valid instance deployer of the relevant factory (i.e. `globals.setCanDeployFrom`). (Only applies to Open Term Loans)
3. The asset used for the funding of the Loan must be set as valid by the Governor in MapleGlobals.
4. The asset used as collateral of the Loan must be set as valid by the Governor in MapleGlobals.
5. The Lender must be a valid instance of the respective type of [`Loan Manager`](../../loan-managers)

## Key Differences Between Open-Term/Fixed-Term Loans
- Open-Term Loans do not have an implied date for which the principal and outstanding interest need to be paid back by.
- Fixed-Term Loans may be required to have the borrower post Collateral whereas Open-Term Loans have no concept of Collateral.
- Fixed-Term Loans may be amortizing or interest-only whereas Open-Term Loans are interest only
- Fixed-Term Loans require the full interest/principal (in case of amortizing) when making a payment regardless if the payment is made before the due date whereas Open-Term Loans prorate the interest payment based on the timestamp the payment is made.
- Fixed-Term Loans can have both Origination and Service Fees whereas Open-Term Loans just have Service Fees
- Fixed-Term Loans own the `fundsAsset` balance when the Loan is funded or refinanced, or funds are returned, and track it via the `drawableFunds` accounting variable whereas Open-Term Loans do not do such accounting as the `fundsAssets` balance is directly paid to the borrower during funding (or refinance for increased principal).
- Fixed-Term Loans refinances are borrower initiated whereas for Open-Term Loans refinances are Pool Delegate initiated.
- Fixed-Term Loans can't be "Called" (i.e. require the borrower to pay back some or all principal by a required date) whereas Open-Term Loans can be called. (Note: Fixed-Term Loans can be refinanced to bring their `paymentDueDate` sooner by refinancing with a smaller `paymentInterval`).
- Closing a Fixed-Term Loan incurs a `closingRate` fee whereas a borrower can close an Open-Term Loan at any time by making a payment for the full principal amount and pay the associated interest and service fees.
- Open-Term Loans can be `impaired()` again if they are already impaired, thereby moving (or "pushing") the `impairmentDate`, whereas Fixed-Term Loans can only be Impaired when not impaired, so they must be unimpaired before being re-impaired.

## General Business Rules
- It is not possible to convert an Open Term Loan into a Fixed Term Loan, or vice versa, by any means
