# Fee Summary
Fees in the Maple protocol can be separated into three categories:
1. **Origination Fees (fixed-term only)**: Fees paid by borrowers during loan funding and refinance operations, deducted from their drawable balance of principal.
2. **Service Fees**: Fees paid by borrowers during loan payments, added to gross interest.
3. **Management Fees**: Fees taken as a portion of gross interest paid by Borrowers when payments are made.

All categories of fees are paid to two actors:
1. The Pool Delegate that manages the pool that has funded the Loan.
2. The `MapleTreasury` contract.

The naming convention for fees in the smart contracts is: `actorCategoryType`. So for example, `delegateManagementFeeRate` would refer to the rate (type) that is used to calculate the management fee (category) that will go to the Pool Delegate (actor).

# Origination Fees - fixed-term

Origination fees are paid during Loan funding and refinance operations for fixed-term Loans. Origination fees are calculated in the following way:
- `delegateOriginationFee` is a loan term that is specified on loan instantiation as a nominal amount (e.g., `1_750 USDC`).
- `platformOriginationFeeRate` is a Governor-settable variable in globals that is settable on a Pool level. When a loan is funded, the origination fee amount to be paid is calculated using the following formula:



$$
\large
\begin{align}
\nonumber platformOriginationFee = platformOriginationFeeRate \times principal \times \frac{loanTermLength}{oneYear}
\end{align}
$$



## Refinancing of Origination Fees - fixed-term

In the case of a refinance, two things happen with regards to origination fees:
1. The `delegateOriginationFee` amount can be updated by updating the fee terms as a part of the refinance (optionally). If no change is made, the same origination fee is used.
2. The `platformOriginationFee` is recalculated and saved based on the resulting terms of the refinance operation and the current `platformOriginationFeeRate` set in globals.

# Service Fees - fixed-term

Service fees are paid during loan payments. Service fees are calculated in the following way:
- `delegateServiceFee` is a loan term that is specified on loan instantiation as a nominal amount (e.g., `100 USDC`).
- `platformServiceFeeRate` is a Governor-settable variable in globals that is settable on a Pool level. When a loan is funded, the service fee amount to be paid is calculated using the following formula:



$$
\large
\begin{align}
\nonumber platformServiceFee = platformServiceFeeRate \times principal \times \frac{paymentIntervalLength}{oneYear}
\end{align}
$$



Both of these values are saved in mappings in the MapleLoanFeeManager and used for all payments for a loan until it either refinances or matures.

## Refinancing of Service Fees - fixed-term

In the case of a refinance, three things happen with regards to service fees:
1. The `delegateServiceFee` amount can be updated by updating the fee terms as a part of the refinance (optionally). If no change is made, the same service fee is used.
2. The platform service fee is recalculated and saved based on the resulting terms of the refinance operation and the current `platformServiceFeeRate` set in globals. This is done using the same formula:



$$
\large
\begin{align}
\nonumber platformServiceFee = platformServiceFeeRate \times principal \times \frac{paymentIntervalLength}{oneYear}
\end{align}
$$



3. The platform and delegate service fee amounts that have accrued between the last payment due date and the refinance are saved in the FeeManager as `platformRefinanceServiceFee` and `delegateRefinanceServiceFee` using the following formula:



$$
\large
\begin{align}
\nonumber refinanceServiceFee = serviceFee \times \frac{(timestamp - lastPaymentDueDate)}{paymentInterval}
\end{align}
$$

# Service Fees - open-term

Service fees are paid during loan payments. Service fees are calculated in the following way:
- `delegateServiceFeeRate` is a loan term that is specified on loan instantiation as a yearly rate (e.g., `100 USDC`).
- `platformServiceFeeRate` is a Governor-settable variable in globals that is settable on a Pool level. When a loan is funded,

The service fee amount to be paid is calculated using the following formula for both the delegate and platform service fees:



$$
\large
\begin{align}
\nonumber platformServiceFee = platformServiceFeeRate \times principal \times \frac{Interval}{oneYear}
\end{align}
$$

$$
\large
\begin{align}
\nonumber delegateServiceFee = delegateServiceFeeRate \times principal \times \frac{Interval}{oneYear}
\end{align}
$$



Both of these values are saved in storage of the Loan contract and used for all payments for a loan until it either refinances or matures.

## Refinancing of Service Fees - open-term

In the case of a refinance, three things happen with regards to service fees:
1. The `delegateServiceFeeRate` can be updated by updating the fee terms as a part of the refinance (optionally). If no change is made, the same service fee is used.
2. The platform service fee is recalculated and saved based on the resulting terms of the refinance operation and the current `platformServiceFeeRate` set in globals.

Both are done using the same formula:

$$
\large
\begin{align}
\nonumber platformServiceFee = platformServiceFeeRate \times principal \times \frac{Interval}{oneYear}
\end{align}
$$

$$
\large
\begin{align}
\nonumber delegateServiceFee = delegateServiceFeeRate \times principal \times \frac{Interval}{oneYear}
\end{align}
$$


3. The platform and delegate service fee amounts that have accrued between the last payment or funding (which ever is greatest) and the refinance are paid during the refinance using the following formula:


$$
\large
\begin{align}
\nonumber refinanceServiceFee = serviceFee \times \frac{(timestamp - \max(datePaid, dateFunded))}{paymentInterval}
\end{align}
$$



# Management Fees

Management fees are paid during loan payments, after a loan's interest has moved out of the loan and into the Pool contracts. Management fees are deducted from gross interest paid by borrowers using the following formula:



$$
\large
\begin{align}
\nonumber managementFee = grossInterest \times managementFeeRate
\end{align}
$$



The remainder of the interest (net interest) goes to the Liquidity Providers.

Note Management fees are treated the same for both fixed-term and open-term loans.
