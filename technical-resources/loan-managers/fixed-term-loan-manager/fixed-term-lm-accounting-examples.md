# Overview

This section is intended to demonstrate multiple scenarios with loans to show how value is represented with `totalAssets`. During each payment, accounting state in the Fixed Term Manager contract is changed in the following way:
1. `accountedInterest` is decreased. This is because the $$ outstandingInterest $$ portion of `assetsUnderManagement` must discretely decrease when a payment is made.
2. `domainStart` is updated to the current timestamp.
3. `issuanceRate` is updated based on the resulting state.
4. `domainEnd` is set to the next earliest payment due date.
5. Cash is sent to the pool.

**Note 1**: For all of the below examples, only interest is being paid so outstanding principal (`principalOut`) remains constant.

**Note 2**: For the purpose of simplicity, `issuanceRate` is represented as $$ units/day $$ in the equations below. In reality, it is represented as $$ units \times 1e30 / second $$.

**Note 3**: None of the below diagrams are to scale.

# Example 1: Single Loan - On Time Payment

In this example, there is a single Loan that makes a payment at the exact timestamp at which the payment is due. The payment is for 5000 units of `fundsAsset`.

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 5000 \\
\nonumber issuanceRate      &= \frac{5000}{20-10} = 500 \\
\nonumber domainStart       &= 10 \\
\nonumber domainEnd         &= 20
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 5000 \\
\nonumber cash                &= cash + 5000 \\
\nonumber totalAssets         &= totalAssets \\
\end{align}
$$


Since the payment was made at the exact time that it was due, the outstanding interest exactly equaled the actual interest paid, so no discrete change in `totalAssets` is observed.

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196064820-c3189a40-4f62-46db-a5d3-8d214fb161e2.svg" height="1000" />
</p>

# Example 2: Single Loan - Early Payment

In this example, there is a single Loan that makes an early payment, two days before the payment is due. The interest due is 5000 units, but since the payment is made on day 8, only 4000 units have accrued in the LoanManager accounting.

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 4000 \\
\nonumber issuanceRate      &= \frac{5000}{20-8} = 416.67 \\
\nonumber domainStart       &= 8 \\
\nonumber domainEnd         &= 20
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 4000 \\
\nonumber cash                &= cash + 5000 \\
\nonumber totalAssets         &= totalAssets + 1000 \\
\end{align}
$$


When a payment is made early, there is a discrete increase in `totalAssets` since the cash balance in the pool increases more than the outstanding interest that was represented when the payment was made.

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196065361-ae75661e-be82-4d2a-9044-099e070b0559.svg" height="1000" />
</p>

# Example 3: Single Loan - Late Payment

In this example, there is a single Loan that makes a late payment, four days after the payment is due. The interest due is 5000 units, but since the payment is made late, there is an extra 3000 units of late interest that must be paid. In addition, since the payment is made on day 14, four days of interest (2000 units) has accrued in the second payment interval. Note that for a late payment, the issuance rate does not change.

Whenever the current timestamp is past the `domainEnd` in the LoanManager, `assetsUnderManagement` no longer accrues interest until the interest accrual formula is updated.

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 5000 + 2000 \\
\nonumber issuanceRate      &= \frac{5000 - 2000}{20-14} = \frac{3000}{6} = 500 \\
\nonumber domainStart       &= 14 \\
\nonumber domainEnd         &= 20
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 3000 \\
\nonumber cash                &= cash + 8000 \\
\nonumber totalAssets         &= totalAssets + 5000 \\
\end{align}
$$

When a payment is made late, there is a discrete increase in `totalAssets` since the interest accruing in the second interval is not represented in the accounting until a payment is made, plus late fees are added.

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196066240-f4c4002a-1d7d-464b-b2b9-62083565fbf0.svg" height="1000" />
</p>

# Example 4: Double Loan - Single On-Time Payment

In this example, there are two outstanding Loans. Loan 2 gets funded on day 5. Loan 1 makes a payment exactly on time at day 10.

When there is more than one outstanding loan, the `issuanceRate` becomes an aggregate value, representing the units of `fundsAsset` accruing against both loans simultaneously. This value gets updated from $$ IR_1 $$ to $$ IR_{1,2} $$ when Loan 2 gets funded and gets updated to $$ IR_2 $$ when Loan 1 is paid.

## Loan 2 Funding

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest + 2500 \\
\nonumber issuanceRate      &= 500 + \frac{5000}{20} = 750 \\
\nonumber domainStart       &= 5 \\
\nonumber domainEnd         &= 10
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest + 2500 \\
\nonumber cash                &= cash \\
\nonumber totalAssets         &= totalAssets \\
\end{align}
$$


## Loan 1 Payment

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 5000 \\
\nonumber issuanceRate      &= 750 - 500 = 250 \\
\nonumber domainStart       &= 10 \\
\nonumber domainEnd         &= 25
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 5000 \\
\nonumber cash                &= cash + 5000 \\
\nonumber totalAssets         &= totalAssets \\
\end{align}
$$


<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196170808-61f7eb98-ca93-4e03-96ba-49c3b60afd01.svg" height="1750" />
</p>

# Example 5: Double Loan - Multiple On Time Payments

In this example, there are two outstanding Loans. Loan 2 gets funded on day 5. Loan 1 makes a payment exactly on time at day 10. Loan 1 makes another payment exactly on time on day 20.

## Loan 2 Funding

Accounting gets updated in the same way as [Example 4](./fixed-term-lm-accounting-examples.md#loan-2-funding).

## Loan 1 Payment 1

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 5000 \\
\nonumber issuanceRate      &= 750 - 500 + 500 = 750 \\
\nonumber domainStart       &= 10 \\
\nonumber domainEnd         &= 20
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 5000 \\
\nonumber cash                &= cash + 5000 \\
\nonumber totalAssets         &= totalAssets \\
\end{align}
$$


## Loan 1 Payment 2

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 5000 \\
\nonumber issuanceRate      &= 750 - 500 = 250 \\
\nonumber domainStart       &= 20 \\
\nonumber domainEnd         &= 25
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 5000 \\
\nonumber cash                &= cash + 5000 \\
\nonumber totalAssets         &= totalAssets \\
\end{align}
$$


<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196173350-af7b3039-dac3-4828-a259-eba73edc0c11.svg" height="1750" />
</p>

# Example 6: Double Loan - Early Payment then On Time Payment

In this example, there are two outstanding loans. Loan 2 gets funded on day 5. Loan 1 makes a payment early on day 8. Loan 1 makes another payment exactly on time on day 20.

Note that it is an edge case to make payments exactly on time. The second payment is more for illustrative purposes of how aggregate issuance rates are rendered with multiple loans and payments.

In this example, there are two different aggregate issuance rates since the issuance rate for Loan 1 changes when an early payment is made.

## Loan 2 Funding

Accounting gets updated in the same way as [Example 4](./fixed-term-lm-accounting-examples.md#loan-2-funding).

## Loan 1 Payment 1

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 4000 = 750 \\
\nonumber issuanceRate      &= 750 - 500 + \frac{5000}{20 - 8} = 666.67 \\
\nonumber domainStart       &= 8 \\
\nonumber domainEnd         &= 20
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 4000 = 750 \\
\nonumber cash                &= cash + 5000 \\
\nonumber totalAssets         &= totalAssets + 1000 = 5750 \\
\end{align}
$$


## Loan 1 Payment 2

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 5000 = 4750 \\
\nonumber issuanceRate      &= 666.67 - 416.67 = 250 \\
\nonumber domainStart       &= 20 \\
\nonumber domainEnd         &= 25
\end{align}
$$


`totalAssets` accounting gets updated as follows:



$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 5000 \\
\nonumber cash                &= cash + 5000 \\
\nonumber totalAssets         &= totalAssets \\
\end{align}
$$


<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196176914-8f431911-8ed8-4508-9615-58223b7e9edf.svg" height="1750" />
</p>

# Example 7: Double Loan - Late Payment then On Time Payment

In this example, there are two outstanding Loans. Loan 2 gets funded on day 5. Loan 1 makes a payment late on day 12. Loan 1 makes another payment exactly on time on day 20.

Note that when the second payment is made, it is made after `domainEnd`. This means that the interest from Loan 1 is fully accounted for, the payment is removed from the sorted list, the issuance rate is reduced, and the interest is accrued to the current timestamp before updating the state. More details on how this works [here](advance-global-payment-accounting.md), specifically in [this](./advance-global-payment-accounting.md#example-2-call-after-domainend-before-loan-2-payment-due-date) example.

## Loan 2 Funding

Accounting gets updated in the same way as [Example 4](./fixed-term-lm-accounting-examples.md#loan-2-funding).

## Loan 1 Payment 1

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:

$$
\large
\begin{align*}
\nonumber accountedInterest &= accountedInterest - 5000 + 250 \times 2 + 500 \times 2 = 2750 \\
\nonumber issuanceRate      &= 750 - 500 + \frac{5000 - 1000}{20 - 12} = 750 - 500 + 500 = 750 \\
\nonumber domainStart       &= 12 \\
\nonumber domainEnd         &= 20
\end{align*}
$$

`totalAssets` accounting gets updated as follows:

$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 3500 = 2750 \\
\nonumber cash                &= cash + 5000 + 3000 \\
\nonumber totalAssets         &= totalAssets + 250 \times 2 + 500 \times 2 + 3000 = 10750 \\
\end{align}
$$

## Loan 1 Payment 2

It can be seen that during this transaction, outstanding interest accounting gets updated as follows:

$$
\large
\begin{align}
\nonumber accountedInterest &= accountedInterest - 5000 = 3750 \\
\nonumber issuanceRate      &= 750 - 500 = 250 \\
\nonumber domainStart       &= 20 \\
\nonumber domainEnd         &= 25
\end{align}
$$


`totalAssets` accounting gets updated as follows:

$$
\large
\begin{align}
\nonumber outstandingInterest &= outstandingInterest - 5000 = 3750 \\
\nonumber cash                &= cash + 5000 = 13000 \\
\nonumber totalAssets         &= totalAssets \\
\end{align}
$$


<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196467284-7687cd2c-f39c-4eb8-ad71-67a2f5b4fe89.svg" height="1750" />
</p>
