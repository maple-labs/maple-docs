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
2. The asset used for the funding of the Loan must be set as valid by the Governor in MapleGlobals.
3. The asset used as collateral of the Loan must be set as valid by the Governor in MapleGlobals.
4. The Lender must be a valid version of the respective type of [`Loan Manager`](../../loan-managers)


## Key Differences Between Open-Term/Fixed-Term Loans
- Open-Tem do not have a due date for which the principal and outstanding interest need to be paid back by.
- Fixed-Term Loans may be required to have the borrower post Collateral whereas Open-Term Loans have no concept of Collateral.
- Fixed-Term Loans may be amortizing or interest-only whereas Open-Term Loans are interest Only
- Fixed-Term Loans require the full interest/principal(in case of amortizing) when making a payment regardless if the payment is made before the due date whereas Open-Term Loans prorate the interest payment based on the timestamp the payment is made.
- Fixed-Term Loans can have both Origination and Service Fees whereas Open-Term Loans just have Service Fees
- Fixed-Term Loans store the fundsAsset when a Loan is funded or refinanced or funds are returned in the `drawableFunds` accounting variable whereas Open-Term Loans do not do such accounting as fundsAssets are directly paid to the borrower during funding (or refinance for increased Principal). 
- Fixed-Term Loans refinances are borrower initiated whereas for Open-Term Loans refinances are Pool Delegate initiated. 
- Fixed-Term Loans can't be "Called" i.e. require the borrower to pay back the Principal in a required interval whereas Open-Term Loans can be called. (Note Fixed-Term Loans can be refinanced to bring their paymentDueDate sooner by refinancing with a smaller paymentInterval).
- Closing a Fixed-Term Loan incurs a `closingRate` fee whereas a borrower can close an Open-Term Loan at any time by making a payment for the full Principal amount and pay the associated interest and service fees.  
- Open-Term Loans can be `impaired()` again if they are already Impaired moving the `impairmentDate` whereas Fixed-Term Loans can only be Impaired once and require you to remove the Impairment before Impairing again. 

## General Business Rules
- Pool Delegate cannot change Open Term Loan to Fixed Term Loan or vice versa.
- If Pool Delegate doesn't post minimum required Cover, service and management fees are routed to the Pool and the Treasury.
