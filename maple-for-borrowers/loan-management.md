---
hidden: true
---

# Loan Management

The Maple app brings every loan across every Legal Entity into one view and lets your team manage them onchain. This page covers the loan statuses you'll see and the actions you can take.

![Loans](<../.gitbook/assets/image (10).png>)

## Loan statuses

Every loan carries three layers of status:

1. **Loan Health**: collateral value relative to LTV thresholds.
2. **Interest Due**: interest payment timing.
3. **Loan State**: where the loan is in its lifecycle.

### 1. Loan Health

Loan Health is based on your LTV (loan-to-value) relative to the thresholds set in your term sheet.

* `Healthy`: LTV is below the margin call level.
* `Margin Call`: LTV has crossed the margin call level. Action required: top up collateral or pay down principal partially.
* `Liquidation`: LTV has crossed the liquidation level. Maple may liquidate a portion of your collateral to return the loan to a `Healthy` LTV.

Each loan shows the live LTV, the margin call and liquidation levels, and the trigger price for each (e.g. `SOL at $50 = Margin Call`).

![Loan Health](<../.gitbook/assets/image (11).png>)

### 2. Interest Due

* `Due [date]`: interest payment is due on this date.
* `Due today`: interest payment is due today. The payment is not yet late.
* `Overdue`: interest payment is past due. Late interest is accruing. This state appears in the Interest Accrued column.

### 3. Loan State

Loan States are based on the payment lifecycle status of the loan:

* `Accept terms`: review and accept the terms of a new loan. The terms in the app will match your term sheet.
* `Pending funding`: once terms are accepted, Maple will fund the loan.
* `Active`: all payments are up to date.
* `Repay soon`: principal repayment has been triggered and the loan call period defined in your term sheet has started. The loan principal cannot yet be repaid.
* `Repay now`: the principal repayment is due. The loan principal can now be repaid.
* `Refinance`: a refinance proposal is available on the loan. Refinancing terms can be reviewed from the Refinance tab in the loan details page.
* `Grace Period`: interest payment is past due, but the loan is still within the grace period defined in your term sheet. Late interest is accruing. It usually appears alongside `Overdue`.
* `Defaulted`: missed interest payment after the grace period expires or missed a principal repayment. Late interest is being charged. A defaulted loan can be remediated by paying the interest or the principal outstanding.

**Late interest** is charged as a premium rate above your loan's normal interest rate. It begins accruing as soon as a scheduled payment is missed.

## Loan actions

The Maple app supports 5 key actions. Interest can be paid from any wallet. All others require a wallet registered to the Legal Entity holding the loan, and a user role with action permissions.

### 1. Accept new loan

After you and the Maple team agree to terms offline and sign the term sheet, Maple proposes the loan onchain. The loan appears in the app as `Accept terms` with the proposed terms.

To accept, review the terms in the app and sign. The loan moves to `Pending funding` while Maple funds it, then to `Active` once the payment schedule begins.

### 2. Pay interest

Interest payments follow the schedule in your term sheet. The app shows the next payment, the amount, and the due date for each loan.

Click Pay interest, review the breakdown, and sign. The app calculates the amount owed. If the payment is past due, late interest accrued to date is included in the total.

### 3. Accept refinance

Refinances are initiated by Maple after offline negotiation and a term sheet amendment. The proposed new terms appear in the Maple app with a clear before and after view of what's changing (e.g. interest rate, principal, term length, and fees). Review the changes and sign to accept. The new terms take effect onchain.

Borrowers cannot initiate refinances from the app - reach out to your Maple contact to start the conversation.

### 4. Repay loan

Use Repay loan to repay principal when a loan is called. Partial repayments lower your LTV and can cure a margin call.

### 5. Curing a margin call (coming soon)

When a loan enters `Margin Call`, you have two ways to bring LTV back below the threshold:

1. **Top up collateral**: send additional collateral to your loan's collateral address. Once received, the loan returns to `Healthy`.
2. **Pay down principal**: use Repay loan to reduce principal until LTV is below the margin call level.

Maple will reach out via your usual channels (typically email) when a margin call is triggered. The time you have to cure it is defined in your term sheet.

## Fees

Maple loans carry an origination fee and ongoing service fees, defined in your term sheet. See [Fees](https://docs.maple.finance/technical-resources/protocol-overview/fees) for details.
