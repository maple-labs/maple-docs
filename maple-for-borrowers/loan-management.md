---
hidden: true
---

# Loan Management

The Maple app brings every loan across every Legal Entity into one view and lets your team manage them onchain. This page covers the loan statuses you'll see and the actions you can take.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## Loan statuses

Every loan carries two layers of status: a **Loan Health** status driven by collateral value, and a **Loan State** that appears when there is a payment issue.

### Loan Health

Loan Health is based on your LTV (loan-to-value) relative to the thresholds set in your term sheet.

* `Healthy` - LTV is below the margin call level
* `Margin Call` - LTV has crossed the margin call level. Action required: top up collateral or pay down principal partially
* `Liquidation` - LTV has crossed the liquidation level. Maple may liquidate a portion of your collateral to return the loan to a healthy LTV

Each loan shows the live LTV, the margin call and liquidation levels, and the trigger price for each (e.g. `SOL at $50 = Margin Call`).

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### Loan State

Loan States appear when there is a payment issue:

* `Grace Period` - interest is past due but still within the grace period defined in your term sheet. No late interest is charged yet
* `Overdue` - you are past due on an interest payment beyond the interest grace period. Late interest is now charged. This appears in the Interest accrued column
* `Defaulted` - you missed an interest payment or a final principal repayment. Late interest is being charged. Defaulted loans can still be actioned (paid down or repaid in full)

**Late interest** is charged as a premium rate above your loan's normal interest rate. It begins accruing after the grace period expires.

## Loan actions

The Maple app supports 5 key actions. Interest can be paid from any wallet. All others require a wallet registered to the Legal Entity holding the loan, and a user role with action permissions (see [Account Management](https://docs.maple.finance/maple-for-borrowers/account-management)).&#x20;

### 1. Accept new loan

After you and the Maple team agree to terms offline and sign the term sheet, Maple proposes the loan onchain. The loan appears in the Maple app as `Pending Funding` with the proposed terms.

To accept, review the terms in the app and sign. Once accepted, Maple funds the loan and the payment schedule begins.

### 2. Pay interest

Interest payments follow the schedule in your term sheet. The app shows the next payment, the amount and the due date for each loan.

Click `Pay interest`, review the breakdown and sign. The app calculates the amount owed. If the payment is past the grace period, late interest accrued to date is included in the total.

### 3. Accept refinance

Refinances are initiated by Maple after offline negotiation and a term sheet amendment. The proposed new terms appear in the Maple app with a clear before → after view of what's changing (e.g. interest rate, principal, term length, fees etc). Review the changes and sign to accept. The new terms take effect onchain.&#x20;

Borrowers cannot initiate refinances from the app - reach out to your Maple contact to start the conversation.

### 4. Repay loan

Principal can be paid down at any time after the loan is called either by you or Maple. Reducing principal lowers your LTV and is one way to cure a margin call.

### 5. Curing a margin call (coming soon)

When a loan enters `Margin Call`, you have two ways to bring LTV back below the threshold:

1. **Top up collateral** - send additional collateral to your loan's collateral address. Once received, the loan returns to `Healthy`&#x20;
2. **Pay down principal** - use `Repay loan` to reduce principal until LTV is below the margin call level

Maple will reach out via your usual channels (Telegram and email) when a margin call is triggered. The time you have to cure it is defined in your term sheet.

## Fees

Maple loans carry an origination fee and ongoing service fees, defined in your term sheet. See [Fees](https://docs.maple.finance/technical-resources/protocol-overview/fees) for details.
