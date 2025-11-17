# Open Term Loans

## Accounting

### Asset Definition

Loans manage one asset: `fundsAsset`.

#### `fundsAsset`

This represents the ERC-20 token that is used to facilitate the funding, drawing down, and payments during a loan lifecycle. Typically this would be a stablecoin such as USDC, DAI, or USDT.

### Payments

Borrowers have the flexibility to make payments, including partial principal repayments, against their loans at any given time. All fees, including service fees, along with interest, are pro-rated and calculated based on the exact time of payment or other significant actions such as loan funding or refinancing.

Payments due are comprised of `principalCalled + interest + lateInterest + delegateServiceFee + platformServiceFee`

### Interest

Interest is prorated and calculated from the relevant `startDate` till the current `block.timestamp`

$$startDate = \max(datePaid, dateFunded)$$

$$interval = block.timestamp - startDate$$

$$interest = principal * interestRate * \frac{interval}{365*86400}$$

### Late Interest

Late payments are also prorated and based on the `lateInterestPremiumRate` and `lateFeeRate`

$$lateInterval = block.timestamp - paymentDueDate$$

$$lateInterest = principal * lateInterestPremiumRate * \frac{lateInterval}{365*86400} + (principal * lateFeeRate)$$

### Delegate Service Fee

Delegate Service Fee is prorated and calculated from the relevant `startDate` till the current `block.timestamp` $$startDate = \max(datePaid, dateFunded)$$

$$interval = block.timestamp - startDate$$

$$delegateServiceFee = principal * delegateServiceFeeRate * \frac{interval}{365*86400}$$

### Platform Service Fee

Platform Service Fee is prorated and calculated from the relevant `startDate` till the current `block.timestamp` $$startDate = \max(datePaid, dateFunded)$$

$$interval = block.timestamp - startDate$$

$$platformServiceFee = principal * platformServiceFeeRate * \frac{interval}{365*86400}$$

## Due Dates

There are two virtual variables `paymentDueDate()` and `defaultDate()` that define the relevant due dates depending on if a payment is late, the loan is called, the loan is impaired, or any combination thereof. To compose these virtual variables, an internal helper function called `_dueDates()` is used.

### `_dueDates()`

Returns the due dates for `callDueDate`, `impairedDueDate` and `normalDueDate`

#### `callDueDate`

$$
\ \text{callDueDate} = \begin{cases} \text{dateCalled + noticePeriod} & \text{if } \text{dateCalled} > 0 \\ 0 & \text{if } \text{dateCalled} = 0 \end{cases} \
$$

#### `impairedDueDate`

$$
\ \text{impairedDueDate} = \begin{cases} \text{dateImpaired} & \text{if } \text{dateImpaired} > 0 \\ 0 & \text{if } \text{dateImpaired} = 0 \end{cases} \
$$

#### `normalDueDate`

$$paidOrFundedDate = \max(datePaid, dateFunded)$$

$$
\ \text{normalDueDate} = \begin{cases} \text{paidOrFundedDate + paymentInterval} & \text{if } \text{paidOrFundedDate} > 0 \\ 0 & \text{if } \text{paidOrFundedDate} = 0 \end{cases} \
$$

### `paymentDueDate()`

$$paymentDueDate = \min(callDueDate, impairedDueDate, normalDueDate)$$

### `_defaultDates()`

Returns the due dates for `callDefaultDate`, `impairedDefaultDate` and `normalDefaultDate`

#### `callDefaultDate`

$$callDefaultDate = callDueDate$$

#### `impairedDefaultDate`

$$
\ \text{impairedDefaultDate} = \begin{cases} \text{impairedDueDate + gracePeriod} & \text{if } \text{impairedDueDate} > 0 \\ 0 & \text{if } \text{impairedDueDate} = 0 \end{cases} \
$$

#### `normalDefaultDate`

$$
\ \text{normalDefaultDate} = \begin{cases} \text{normalDueDate + gracePeriod} & \text{if } \text{normalDueDate} > 0 \\ 0 & \text{if } \text{normalDueDate} = 0 \end{cases} \
$$

### `defaultDate()`

$$defaultDate = \min(callDefaultDate, impairedDefaultDate, normalDefaultDate)$$

## Loan Calls

The lender exclusively has the ability to commence a Loan Call, specifying the principal amount that must not exceed the current principal balance. In the event of partial Loan Calls, the loan continues with a reduced balance but the same terms. Conversely, a complete Loan Call leads to the loan maturing once the borrower repays. Upon a Loan Call by the lender, the borrower is obligated to settle the demanded amount within the Notice Period or risk the loan defaulting.

The lender can also withdraw a Loan Call, which reverts the payment schedule back to its original state prior to the Loan Call. If a Loan Call is made on a late loan, the lender can default the loan at the termination of either the Notice Period or the Grace Period, depending on which comes first.

It's worth noting that refinancing is considered a valid resolution to Loan Calls, with such calls being settled once the parties agree to new terms.

## Fees

Open-Term Loans have `delegateServiceFees` and `platformServiceFees` which are prorated and calculated on each payment.

## Closing Loan

If a borrower wants to close a loan, they can do so by calling `makePayment` with `principalToReturn` equal to the outstanding principal.

Note: `makePayment` is permissionless. Any address can pay on behalf of the borrower by transferring funds via `transferFrom` to the lender; typical usage is the borrower calling directly.

## Initialization Parameters

* `borrower` - The address of the borrower.
* `lender` - The address of the lender.
* `fundsAsset` - The address of asset that the loan is denominated in.
* `gracePeriod` - The amount of time that the lender needs to wait before triggering a default on a late loan.
* `noticePeriod` - The maximum amount of required for the Borrower fulfill a loan call.
* `paymentInterval` - The amount of seconds between each loan payment.
* `interestRate` - The annualized interest rate.
* `lateFeeRate` - A fee rate applied on principal amount on late payments.
* `lateInterestPremiumRate` - A premium added on top of the interest rate for late payments.
* `delegateServiceFeeRate` - A rate of funds assets that is added on every payment destined to the pool delegate.
