# Fees

## Loan Fees

Loan fees in the Maple protocol can be separated into two categories:

1. **Service Fees**: Fees paid by borrowers during loan payments, added to gross interest.
2. **Management Fees**: Fees taken as a portion of gross interest paid by Borrowers when payments are made.

All categories of fees are paid to two actors:

1. The Pool Delegate that manages the pool that has funded the Loan.
2. The `MapleTreasury` contract.

The naming convention for fees in the smart contracts is: `actorCategoryType`. So for example, `delegateManagementFeeRate` would refer to the rate (type) that is used to calculate the management fee (category) that will go to the Pool Delegate (actor).

## Open Term Loans

### Service Fees

Service fees are paid during loan payments. Service fees are calculated in the following way:

* `delegateServiceFeeRate` is a loan term that is specified on loan instantiation as an annualized rate scaled by `1e6` (the `HUNDRED_PERCENT` constant). It is a rate, not a nominal currency amount (e.g., `100_000` = 10%).
* `platformServiceFeeRate` is a Governor-settable variable in globals that is settable on a Pool level. When a loan is funded, the service fee amount to be paid is calculated using the following formula for both the delegate and platform service fees:

$$
\large \begin{align} \nonumber platformServiceFee = platformServiceFeeRate \times principal \times \frac{Interval}{oneYear} \end{align}
$$

$$
\large \begin{align} \nonumber delegateServiceFee = delegateServiceFeeRate \times principal \times \frac{Interval}{oneYear} \end{align}
$$

Both of these values are saved in storage of the Loan contract and used for all payments for a loan until it either refinances or matures.

### Refinancing of Service Fees

In the case of a refinance, three things happen with regards to service fees:

1. The `delegateServiceFeeRate` can be updated by updating the fee terms as a part of the refinance (optionally). If no change is made, the same service fee is used.
2. The platform service fee is recalculated and saved based on the resulting terms of the refinance operation and the current `platformServiceFeeRate` set in globals.

Both are done using the same formula:

$$
\large \begin{align} \nonumber platformServiceFee = platformServiceFeeRate \times principal \times \frac{Interval}{oneYear} \end{align}
$$

$$
\large \begin{align} \nonumber delegateServiceFee = delegateServiceFeeRate \times principal \times \frac{Interval}{oneYear} \end{align}
$$

3. The platform and delegate service fee amounts that have accrued between the last payment or funding (whichever is greatest) and the refinance are paid during the refinance using the following formula:

$$
\large \begin{align} \nonumber refinanceServiceFee = serviceFee \times \frac{(timestamp - \max(datePaid, dateFunded))}{paymentInterval} \end{align}
$$

## Management Fees

Management fees are paid during loan payments, after a loan's interest has moved out of the loan and into the Pool contracts. Management fees are deducted from gross interest paid by borrowers using the following formula:

$$
\large \begin{align} \nonumber managementFee = grossInterest \times managementFeeRate \end{align}
$$

The remainder of the interest (net interest) goes to the Liquidity Providers.
