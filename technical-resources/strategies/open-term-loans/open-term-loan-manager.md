# Open Term Loan Manager

The Open Term Loan Manager is responsible for managing the accounting state of all Open Term Loans tied to it via the initial funding. This includes storing the start dates and effective issuance rates resulting from the next expected payment of each Open Term Loan, accruing interest due from a Loans operations (i.e. payments, impairments, refinances, defaults), providing the total assets under management information to the Pool. The Loan Manager also handles a Loan Payment by distributing the `fundsAsset` to the Pool and the relevant Management and Service Fees to the Treasury and Pool Delegate.

Each Pool has its own Open Term Loan Manager, which no other Pool can fund. The Pool Manager deploys it through `addStrategy` and limits it with a strategy cap, see [Pool Manager](../../pools/pool-manager.md). Full interface: [OpenTermLoanManager](../../interfaces/open-term-loan-manager.md).

## Key Terms

`issuanceRate` - Denotes how many `fundsAsset` per second the AssetsUnderManagement increases by for the Open Term Loan Manager, denoted using `1e27` decimal precision.

`domainStart` - Timestamp representing when a function was called against the Open Term Loan Manager that updated the global issuance rate.

`accountedInterest` - The interest that was accrued prior to the change in domainStart.

`unrealizedLosses` - The combination of multiple Loans principal and accrued interest at the point of impairment.

`principalOut` - The total principal lent out by the Pool to each Loan the Open Term Loan Manager funded.

`assetsUnderManagement()` - A function representing the total AUM for the Open Term Loan Manager calculated using the formula below

$$assetsUnderManagement = \sum({outstandingPrincipal_{loan}} + {outstandingInterest_{loan}})$$

where:

$$outstandingInterest = accountedInterest + \frac{issuanceRate \times (block.timestamp - domainStart)}{PRECISION}$$

and `PRECISION` is `1e27`.

## Fund

* The PoolDelegate directly calls `fund()` which sets up the accounting of the respective Loan in the LoanManager and requests funds from the Pool via the PoolManager and approves the OT-Loan to pull the funds from the LoanManager.
* The Loan Manager first checks that the Loan comes from an `OT_LOAN_FACTORY` instance and that its borrower is valid in Globals. The Pool Manager reverts with `PM:RF:STRATEGY_CAP` if the Loan Manager's `assetsUnderManagement` plus the principal would exceed its strategy cap, and the Loan reverts with `ML:F:TERMS_NOT_ACCEPTED` unless the Borrower has called `acceptLoanTerms()`.

## Refinance

* The PoolDelegate can call `proposeNewTerms()` to the Loan which will call the Loan's `proposeNewTerms()` and store the `refinanceCommitment`.
* The PoolDelegate can call `rejectNewTerms()` to the Loan which will call the Loan's `rejectNewTerms()` which will delete the `refinanceCommitment` not allowing the borrower to accept the new terms via the Loan.
* When the borrower accepts new terms as part of the refinance flow the LoanManager's `claim()` is called as the borrower pays any interest and fees due. Importantly this flow also accounts for a change in `principal` where the principal can both increase in which case funds are requested from the Pool and sent to the borrower via the Loan, or if the principal is decreased the funds are sent back to the Pool.
* In the `claim()` function, a positive principal argument indicates that amount of principal is being repaid, otherwise, if negative, it indicates that amount of principal is being requested from the Pool as part of a Refinance to increase the `principal`.

## Call / Remove Call

* The PoolDelegate directly calls `callPrincipal()` with the principal amount, this then calls the Loan's `callPrincipal()`. No state changes occur in the LoanManager.
* The same is true for `removeCall()`, which just calls the Loan's `removeCall()`. No state changes occur in the LoanManager.

## Impairment / Remove Impairment

* Both the PoolDelegate and Governor can call `impairLoan()`, which calls the Loan's `impair()` and updates the LoanManager accounting by reducing the `issuanceRate`, updates the `unrealizedLosses` with the principal and accrued interest, and stores the impairment information in the `Impairment` struct for future use.
* Both the PoolDelegate and Governor can call `removeLoanImpairment()`, but if the Loan was Impaired by the Governor only the Governor can call `removeLoanImpairment()`. This is to safeguard against a PoolDelegate canceling an Impairment the Governor has deemed necessary. In the case `removeLoanImpairment()` is called, the LoanManager accounting is updated to include the `issuanceRate` for the Loan payment and add back any interest that was expected to be accrued during this period between the impairment date and the current timestamp. Finally `removeImpairment()` is called on the Loan.

## Default

* The PoolManager can call `triggerDefault()` on the LoanManager. The entry point to triggering a default is the PoolManager.
* Note the interface for `triggerDefault(address loan_, address liquidatorFactory_)` takes in a `liquidatorFactory` address, which is ignored for the execution in the Open-Term LoanManager since Open-Term Loans have no collateral. The PoolManager passes the zero address.
* The natural progression of all defaults is for the Loan to be impaired first, such that the calculation during the default process to occur from the same station Loan accounting state. Thus, `triggerDefault()` performs steps to account for the Loan's impairment first, if it has already not been impaired, as part of the `triggerDefault()` flow.
* Global accounting is updated to update the `principalOut`, `accountedInterest` and `unrealizedLosses`.
* Any recovered fees from the Loan are distributed to the Pool and Treasury with any `remainingLosses` passed back to the `PoolManager.triggerDefault()`.

## Fees

* Service fees are passed into the `claim()` function and are paid out to the platform and delegate respectively.
* Management fees are calculated as part of the `claim()` function flow using the stored `managementFeeRate` in the `Payment` struct.

## Accounting

The Open Term Loan Manager handles accounting for Open Term Loans by being aware of the incoming payment expected. When a Loan is Funded or a Payment is made the payment information is stored in a payment struct containing the `platformManagementFeeRate`, `delegateManagementFeeRate`, `startDate` and `issuanceRate`. The fee rates are snapshots of the global variables at the time, whereas the latter 2 are Loan specific. The global `issuanceRate` is then adjusted and interest accrued prior gets added to the `accountedInterest`, thus updating the accounting state globally.

Note that interest keeps accruing in the Open Term Loan Manager as there is no notion of a `domainEnd`. The assumption is that the Pool Delegate will act to Impair or Default a Open Term Loan in order to make the necessary accounting updates to adjust the issuance rate and stop accruing interest on a Loan where a payment is no longer expected.

## Accounting Example

The example below shows how the accounting state changes when a Loan makes interest payments. It assumes the Pool only has Open-Term Loans via the Open-Term LoanManager.

During each payment, accounting state in the Pool contracts is changed in the following way:

1. Outstanding Interest (which is a combination of `accountedInterest` & `accruedInterest()`) is decreased by the interest the payment accrued since its start date, not by the amount paid. Any late interest paid adds to cash without first accruing in Outstanding Interest.
2. `domainStart` is updated to the current timestamp.
3. `issuanceRate` is updated based on the resulting state. While principal remains, the Loan Manager queues the Loan's next payment, so the Loan keeps accruing interest.
4. Cash in the pool increases.

**Note 1**: Only interest is being paid in the example, so outstanding principal (`principalOut`) remains constant.

**Note 2**: For the purpose of simplicity, `issuanceRate` is represented as $units/day$ in the equations below. In reality, it is represented as $units \times 1e27 / second$.

**Note 3**: The diagram below is not to scale.

**Note 4**: The example assumes zero management fees, so the Pool receives all the interest paid.

### Example: Single Loan - Early Payment

In this example a single Loan with 1,000,000 units of principal is funded on day 0 with a 10-day payment interval. The interest due on day 10, the payment due date, would have been 5000 units of `fundsAsset`, so the payment's `issuanceRate` is 500. The Loan makes an early payment two days before the payment is due, so the interest amount is prorated and only 4000 units of interest.

It can be seen during the first payment transaction on day 8 that the accounting gets updated as follows:

$$
\begin{align} outstandingInterest &= 500 \times 8 - 4000 = 0 \\ issuanceRate &= \frac{5000}{18-8} = 500 \\ domainStart &= 8 \\ cash &= 0 + 4000 = 4000 \\ totalAssets &= principalOut + cash + outstandingInterest = 1{,}004{,}000 \\ \end{align}
$$

Note for Open-Term Loans that the new payment due date after a payment made is exactly `block.timestamp` + `paymentInterval` so in this case the new payment due date for payment 2 is day 18. The second payment is made on day 18 below is how the account gets updated:

$$
\begin{align} outstandingInterest &= 500 \times (18 - 8) - 5000 = 0 \\ issuanceRate &= \frac{5000}{28-18} = 500 \\ domainStart &= 18 \\ cash &= 4000 + 5000 = 9000 \\ totalAssets &= principalOut + cash + outstandingInterest = 1{,}009{,}000 \\ \end{align}
$$

The principal is still outstanding after day 18, so the Loan Manager queues payment 3, due on day 28, and interest keeps accruing at 500 per day.

<div align="center"><img src="https://user-images.githubusercontent.com/59924029/227527364-750466fc-caf5-44e2-936c-f386f4bfd865.svg" alt="" height="1000"></div>
