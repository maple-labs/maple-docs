# Open Term Loans

Open-term loans are the one strategy a Pool owns directly. The Pool Manager deploys the Open Term Loan Manager through `addStrategy` and funds it under a strategy cap, with no [Strategy Manager](../strategy-manager.md) in between. Every other strategy is shared between Pools through a Strategy Manager, see [How Pools Allocate Capital](../how-pools-allocate-capital.md). v7 adds one step to the loan itself: the borrower accepts the loan terms before the loan can be funded.

All loans in the protocol are open-term loans. Their functionality can be summarized as follows:

1. Execution of loan financing.
2. Computation of payment amounts and schedules for interest-only payments.
3. Repossession of any remaining funds in the event of a loan default.
4. Claim of interest and principal from loans.
5. Carrying out refinancing activities when a lender and borrower consent to new terms.
6. Change of loan logic via upgradeability models.

## Deployments
Loans operate as proxy contracts that link to a particular implementation. Borrowers interested in establishing loans within the Maple ecosystem must do so through the OpenTermLoanFactory contract. This contract stores details about the current version of loans and potential upgrade paths.

## Loan Creation Pre-Requisites

The following pre-requisites must be met before the creation of a Loan.

1. The Borrower must be set as valid in the MapleGlobals allowlist.
2. The Borrower must be able to deploy from the loan factory. Globals lets any valid Borrower deploy from a factory registered as a `LOAN_FACTORY` instance. Otherwise the Borrower must be allowed explicitly with `setCanDeployFrom`.
3. The asset used for the funding of the Loan must be set as valid by the Governor in MapleGlobals.
4. The Lender must be a valid instance of the Open Term Loan Manager with the same `fundsAsset`.

## Key Characteristics of Open-Term Loans
- There is no implied date by which the principal and outstanding interest need to be paid back.
- There is no collateral held by the loan contract.
- Loans are interest-only.
- Interest is prorated based on the timestamp the payment is made.
- Loans charge Service Fees only.
- The `fundsAsset` balance is paid directly to the borrower during funding, or during a refinance that increases principal.
- The Borrower must call `acceptLoanTerms()` before the Lender can fund the loan.
- Refinances are initiated by the Pool Delegate.
- Loans can be "Called", requiring the borrower to pay back some or all principal by a required date.
- A borrower can close a loan at any time by paying the full principal amount plus the associated interest and service fees.
- Loans can be `impaired()` again if they are already impaired, thereby moving (or "pushing") the `impairmentDate`.
