The Open Term Loan Manager is responsible for managing the accounting state of all Open Term Loans tied to it via the initial funding. This includes storing the information for the next Payment due from an Open Term Loan, accruing interest due from a Loans payment, providing the total assets under management information to the Pool. The Loan Manager also handles a Loan Payment by distributing the `fundsAsset` to the Pool and the relevant Management and Service Fees to the Treasury and Pool Delegate.

# Key Terms

`issuanceRate` - Denotes how many `fundsAsset` per second the AssetsUnderManagement increases by for the Open Term Loan Manager, denoted using `1e27` decimal precision. 

`domainStart` - Timestamp representing when a function was called against the Open Term Loan Manager that updated the global issuance rate.

`accountedInterest` - The interest that was accrued prior to the change in domainStart.

`unrealizedLosses` - The combination of multiple Loans principal and accrued interest at the point of impairment.

`principalOut` - The total principal lent out by the Pool to each Loan the Open Term Loan Manager funded. 

`assetsUnderManagement()` - A function representing the total AUM for the Open Term Loan Manager calculated using the formula below


$$ assetsUnderManagement = \sum({outstandingPrincipal_{loan}} + {outstandingInterest_{loan}}) $$

where:

$$ outstandingInterest = accountedInterest + issuanceRate \times (block.timestamp - domainStart) $$

# Fund
- The PoolDelegate directly calls `fund()` which setups the accounting on the LoanManager and requests funds from the Pool via the PoolManager and approves the OT-Loan to pull the funds from the LoanManager. This is different from the Fixed-Term LoanManager where the funds are sent directly to the Loan for the borrower to draw from. 

# Refinance
- The PoolDelegate can call `proposeNewTerms()` to the Loan which will call the Loan's `proposeNewTerms()` and store the `refinanceCommitment` which is a hash of `keccak256(abi.encode(refinancer_, deadline_, calls_))`. 
- The PoolDelegate can call `rejectNewTerms()` to the Loan which will call the Loan's `rejectNewTerms()` which will delete the `refinanceCommitment` not allowing the borrower to accept the new terms via the Loan.
- When the borrower accepts new terms as part of the refinance flow the LoanManager's `claim()` is called as the borrower pays any interest and fees due. Importantly this flow also accounts for a change in `principal` where the principal can both increase in which case funds are requested from the Pool and sent to the borrower via the Loan, or if the principal is decreased the funds are sent back to the Pool. 
- In the `claim()` function if the principal passed is positive that means that amount of principal is being repaid otherwise if negative that means that amount of principal is being requested from the Pool as part of a Refinance to increase the `principal`. 

# Call / Remove Call
- The PoolDelegate directly `callPrincipal()` with the principal amount, this then calls the Loan's `callPrincipal()`. No state changes occur on the LoanManager. 
- The same is true for `removeCall()` which just calls the Loan's `removeCall()`. No state changes occur on the LoanManager

# Impairment / Remove Impairment 
- Both the PoolDelegate and Governor can call `impairLoan()` which calls the Loan's `impair()` and updates the LoanManager accounting by reducing the issuanceRate, updates the `unrealizedLosses` with the principal and accrued interest and stores the impairment information in the `Impairment` struct for future use. 
- Both the PoolDelegate and Governor can call `removeLoanImpairment()` but if the Loan was Impaired by the Governor only the Governor can call `removeLoanImpairment()`, this is to safeguard against any malicious use. In the case `removeLoanImpairment()` is called the LoanManager accounting is updated to include the issuanceRate for the Loan payment and add back any Interest that was expected to be accrued during this period between the Impairment date and the current timestamp. Finally `removeImpairment()` is called on the Loan. 

# Default
- The PoolManager can call `triggerDefault()` on the LoanManager. This is due to the PoolManager also needing to handle PoolCover so the decision was made to keep the entry point to `triggerDefault()` the PoolManager. 
- Note the interface for `triggerDefault(address loan_, address liquidatorFactory_)` takes in a liquidatorFactory address this is ignored for the execution in the Open-Term LoanManager and is in the interface for compatibility of the PoolManager with both Fixed/Open-Term LoanManagers. 
- As `triggerDefault()` could have many states a Loan is in prior to defaulting such as being late or Impaired the decision was made to ensure the Loan state is idempotent and is always Impaired first as part of the `triggerDefault()` flow. 
- Global accounting is updated to update the `principalOut`, `accountedInterest` and `unrealizedLosses`.
- Any recovered fees from the Loan are distributed to the Pool and Treasury with any `remainingLosses` passed back to the `PoolManager.triggerDefault()` to see if anything further can be recovered via the PoolCover.    

# Fees
- Service fees are passed into the `claim()` function and are paid out to the platform and delegate respectively. It is worth noting that if the poolDelegate does not have enough cover provided the delegateServiceFees are added to the platformFees and sent to the treasury (to be later determined what to do with).
- Management fees are calculated as part of the `claim()` function flow using the stored managementFeeRate in the `Payment` struct. Similar to service fees, if the poolDelegate does not provide enough cover the delegateManagementFee is instead not deducted and the pool gets that portion of fees.  

# Accounting  
The Open Term Loan Manager handles accounting for Open Term Loans by being aware of the incoming payment expected. When a Loan if Funded or a Payment is made the payment information is stored in a payment struct containing the `platformManagementFeeRate`, `delegateManagementFeeRate`, `startDate` and `issuanceRate` with the latter 2 being Loan specific vs the global variables. The global `issuanceRate` is then adjusted and interest accrued prior gets added to the `accountedInterest` thus updating the accounting state globally. 

Note the key distinction between the Open Term Loan Manager and Fixed Term Loan Manager is that in the case of Open Term interest keeps accruing as there is no notion of a `domainEnd`, the assumption is that the Pool Delegate will act to Impair or Default a Open Term Loan in order to make the necessary accounting updates to adjust the issuance rate and stop accruing interest on a Loan where a payment is no longer expected.

# Accounting Examples
Below please find examples of how the accounting state changes based on different scenarios. The scenarios assume the Pool only has Open-Term Loans via the Open-Term LoanManager.

This section is intended to demonstrate multiple scenarios with loans to show how value is represented with `totalAssets`. During each payment, accounting state in the Pool contracts is changed in the following way:
1. Outstanding Interest (which is a combination of `accountedInterest` & `accruedInterest()`) is decreased. This is because the $outstandingInterest$ portion of `assetsUnderManagement` must discretely decrease when a payment is made.
2. `domainStart` is updated to the current timestamp.
3. `issuanceRate` is updated based on the resulting state.
4. Cash in the pool increases.

**Note 1**: For all of the below examples, only interest is being paid so outstanding principal (`principalOut`) remains constant.

**Note 2**: For the purpose of simplicity, `issuanceRate` is represented as $units/day$ in the equations below. In reality, it is represented as $units \times 1e27 / second$.

**Note 3**: None of the below diagrams are to scale.

**Note 4**: There is no notion of `domainEnd` in the Open-Term LoanManager as interest accrues till either a payment is made.

## Example 1: Single Loan - Early Payment

In this example there is a single Loan that makes an early payment, two days before the payment is due. The interest due on day 10, the payment due date, would have been 5000 units of `fundsAsset` but as the payment is made two days early the interest amount is prorated and only 4000 units of interest.

It can be seen during the first payment transaction on day 8 that the accounting gets updated as follows:

$$
\begin{align}
outstandingInterest &= outstandingInterest - 4000 \\
issuanceRate        &= \frac{5000}{18-8} = 500 \\
domainStart         &= 8 \\
cash                &= cash + 4000 \\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Note for Open-Term Loans that the new payment due date after a payment made is exactly `block.timestamp` + `paymentInterval` so in this case the new payment due date for payment 2 is day 18. The second payment is made on day 18 below is how the account gets updated:

$$
\begin{align}
outstandingInterest &= outstandingInterest - 5000 \\
issuanceRate        &= 0 \\
domainStart         &= 18 \\
cash                &= cash + 5000 \\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

<p align="center">
  <img src="https://user-images.githubusercontent.com/59924029/227527364-750466fc-caf5-44e2-936c-f386f4bfd865.svg" height="1000" />
</p>

## Example 2: Single Loan - Late Payment

In this example there is a single Loan that makes a late payment, two days after the payment was due. The interest due on day 10, the payment due date, would have been 5000 units of `fundsAssest` but as the payment is made two days late the interest amount is prorated and 6000 units of normal interest is due and 1000 units of late interest.

Note for this example we assume the `lateInterestPremiumRate` is the same as the `interestRate` and that there is zero `lateFeeRate`. 

It can be seen during the first payment transaction on day 12 that the accounting gets updated as follows:

$$
\begin{align}
lateInterest        &= 500 * 2 \\
outstandingInterest &= outstandingInterest - 7000 \\
issuanceRate        &= \frac{5000}{22-12} = 500 \\
domainStart         &= 12 \\
cash                &= cash + 7000 \\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Payment 2 is made on time and follows the same logic as [Example 1](https://github.com/maple-labs/maple-core-v2-private/wiki/Open-Term-Loan-Manager#example-1-single-loan---early-payment)

<p align="center">
  <img src="https://user-images.githubusercontent.com/59924029/227553957-9fe42cdd-5e5c-4a11-8b6d-36e6290cfc1f.svg" height="1000" />
</p>

## Example 3: Double Loan - Single Early Payment
The same first Loan as [Example 1](https://github.com/maple-labs/maple-core-v2-private/wiki/Open-Term-Loan-Manager#example-1-single-loan---early-payment) but a second Loan is funded on day 5 to demonstrate how interest is accrued with more then one Loan. 

Below demonstrates how the accounting changes on day 5 when the second loan is funded:

$$
\begin{align}
accountedInterest   &= 500 * 5 = 2500 \\
outstandingInterest &= outstandingInterest + 2500 \\
issuanceRate        &= \frac{5000}{10-0} + \frac{12000}{20-0} = 500 + 600 = 1100 \\
domainStart         &= 5 \\
cash                &= cash\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Below demonstrates how the accounting changes on day 8 when the first Loan makes an early repayment:

$$
\begin{align}
accountedInterest   &= 600 * 3 = 1800 \\
outstandingInterest &= outstandingInterest + 1800 - 4000 \\
issuanceRate        &= \frac{5000}{18-8} + \frac{12000}{20-0} = 500 + 600 = 1100 \\
domainStart         &= 8 \\
cash                &= cash + 4000\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Below demonstrates how the accounting changes on day 18 when the first Loan makes a payment on time:

$$
\begin{align}
accountedInterest   &= 600 * 10 = 6000 \\
outstandingInterest &= outstandingInterest + 6000 - 5000 \\
issuanceRate        &= \frac{12000}{20-0} = 600\\
domainStart         &= 18 \\
cash                &= cash + 5000\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Below demonstrates how the accounting changes on day 25 when the second Loan makes a payment on time:

$$
\begin{align}
outstandingInterest &= outstandingInterest - 12000 \\
issuanceRate        &= 0 \\
domainStart         &= 25 \\
cash                &= cash + 12000\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

<p align="center">
  <img src="https://user-images.githubusercontent.com/59924029/227578088-6d80c034-e264-495e-b9f6-8282b8bdcad8.svg" height="1750" />
</p>

## Example 4: Double Loan - Single Late Payment
The same first Loan as [Example 2](https://github.com/maple-labs/maple-core-v2-private/wiki/Open-Term-Loan-Manager#example-2-single-loan---late-payment) but a second Loan is funded on day 5 to demonstrate how interest is accrued with more then one Loan. 

Note for this example we assume the `lateInterestPremiumRate` is the same as the `interestRate` and that there is zero `lateFeeRate`.

Below demonstrates how the accounting changes on day 5 when the second loan is funded:

$$
\begin{align}
accountedInterest   &= 500 * 5 = 2500 \\
outstandingInterest &= outstandingInterest + 2500 \\
issuanceRate        &= \frac{5000}{10-0} + \frac{12000}{20-0} = 500 + 600 = 1100 \\
domainStart         &= 5 \\
cash                &= cash\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Below demonstrates how the accounting changes on day 12 when the first Loan makes a late repayment:

$$
\begin{align}
accountedInterest   &= 600 * 7 = 4200 \\
lateInterest        &= 500 * 2 = 1000 \\
outstandingInterest &= outstandingInterest + 4200 - 7000 \\
issuanceRate        &= \frac{5000}{22-12} + \frac{12000}{20-0} = 500 + 600 = 1100 \\
domainStart         &= 12 \\
cash                &= cash + 7000\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Below demonstrates how the accounting changes on day 22 when the first Loan makes a payment on time:

$$
\begin{align}
accountedInterest   &= 600 * 10 = 6000 \\
outstandingInterest &= outstandingInterest + 6000 - 5000 \\
issuanceRate        &= \frac{12000}{20-0} = 600\\
domainStart         &= 22 \\
cash                &= cash + 5000\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

Below demonstrates how the accounting changes on day 25 when the second Loan makes a payment on time:

$$
\begin{align}
outstandingInterest &= outstandingInterest - 12000 \\
issuanceRate        &= 0 \\
domainStart         &= 25 \\
cash                &= cash + 12000\\
totalAssets         &= `principalOut` + cash + outstandingInterest \\
\end{align}
$$

<p align="center">
  <img src="https://user-images.githubusercontent.com/59924029/227583235-0549d4e3-fb20-4a4c-930b-9b9a37471c65.svg" height="1750" />
</p>

