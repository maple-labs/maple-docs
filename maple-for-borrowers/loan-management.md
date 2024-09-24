# Loan Management

We strive to make managing your loans on Maple as simple as possible. As a Borrower there are three essential actions:

1. Creating a Loan
2. Making a Payment
3. Proposing a Refinance

**Creating a Loan**

The first step in the loan process occurs off-chain. Borrowers negotiate directly with Maple and sign legal term sheets corresponding to loan terms. After the terms are signed, the borrower creates a loan request on-chain, which is then funded by Maple Direct. The process of bringing the legal agreement on-chain is as simple as inputting key terms from your term sheet into the create loan form on the borrower page.

There are two key pieces of data to discuss upfront: the Origination Fee and the Admin Fee. Please see the [Fees](../fees/loan-management.md) section for more information.

**Making a Payment**

Borrowers can make payments anytime throughout the lifetime of the loan before the due date indicated in the borrower dashboard. Managing payments can be done using the upcoming repayments tab in the borrower interface.

Because the accounting is handled by Maple’s smart contracts, there is no need to manually enter in the payment amount. Before making a payment, the UI will give the borrower a breakdown of the payment in terms of principle, interest and fees, with an instruction to pay the total.

**Proposing a Refinance**

Borrowers may propose to refinance a loan. Normally this would occur after negotiating these terms with Maple Direct and signing an amendment to the loan terms. Refinancing allows the borrower to update loan terms such as:

* Interest Rate
* Term Length
* Principal
* Origination and Admin Fees

The UI will ask you to acknowledge the proposed changes to the loan term before they are submitted on chain for approval or rejection. Proposed terms are only valid for 48 hours after which they may no longer be approved or rejected.
