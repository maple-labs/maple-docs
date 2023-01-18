# Assets Under Management (AUM)

The LoanManager interacts with Loans on behalf of the PoolManager and represents all the outstanding these Loans' outstanding value with the `assetsUnderManagement` function. This function returns the outstanding principal of all loans plus the outstanding interest.

<br/>

$$ \large assetsUnderManagement = outstandingPrincipal + outstandingInterest $$
<br/>

# Outstanding Principal

The outstanding principal component of AUM in the LoanManager is represented by the `principalOut` state variable. This variable is incremented and decremented based on the actions of individual Loans and is equal to the sum of principal balance on all outstanding Loans.

<br/>

$$ \large principalOut = \sum{principal_{loan}} $$
<br/>

# Outstanding Interest

## Introduction

Outstanding interest in the LoanManager has to represent the current aggregate value of the outstanding interest in all loans in the most accurate and efficient way possible. [Interest](https://github.com/maple-labs/maple-core-v2/wiki/Loans/_edit#amortization-calculation) in MapleLoans is represented as fixed amounts owed at a given date. For example, a $1m loan with 12% interest and a 30 day payment interval would be shown as:

<br/>

$$ \large interest = 1e6 \times 0.12 \times \frac{30}{365} = 9863.01 $$
<br/>

This amount of $9863.01$ would be due exactly 30 days from when the loan gets funded.

## Naive Approach

Using this information, the current value of interest in the MapleLoan at any given time can be represented with the following equation:

<br/>

$$ \large interest(t) = interestDue \times \frac{t - paymentIntervalStart}{paymentIntervalLength} $$
<br/>

So in an easier example, with a loan that expects $1000 on day 20, the value on day 9 would be:

<br/>

$$ \large interest(9) = 1000 \times \frac{9-0}{20} = 450 $$
<br/>

Expanding on this concept, the naive calculation of the outstanding interest of all loans would be:

<br/>

$$ \large interest(t) = \sum (interestDue_{loan} \times \frac{t - paymentIntervalStart_{loan}}{paymentInterval_{loan}}) $$
<br/>

## Optimized Approach (Aggregated Issuance)

In a system managing many loans at once, calculating the outstanding interest by summing the values naively is prohibitively expensive. In order to represent this value more efficiently, an alternative approach was taken. By saving the values from Loans during interactions and using them in an aggregate expression, a piecewise linear function can be constructed to represent the value of outstanding interest at any given time. This function consists of four parameters:
1. `issuanceRate`: Units of `fundsAsset` per second being earned as interest for all outstanding loans.
2. `accountedInterest`: "Snapshotted" value of outstanding interest saved at each point the function parameters are updated.
3. `domainStart`: The timestamp marking beginning of the domain in which the interest accrual expression is valid (called the "issuance domain"). Set to `block.timestamp` after each update.
4. `domainEnd`: The timestamp marking the end of the issuance domain.

The equation for outstanding interest is shown below:

<br/>

$$ \large outstandingInterest(t) = accountedInterest + issuanceRate \times (t - domainStart) $$
<br/>

Where:

<br/>

$$ \large domainStart \le t \le domainEnd $$
<br/>
