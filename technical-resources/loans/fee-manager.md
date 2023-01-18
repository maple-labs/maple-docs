# Overview

`FeeManager` is a singleton contract responsible for holding and executing fee payments for all the loans. It queries the MapleGlobals contract to calculate fees owed to the protocol ([more details here](maple-for-developers/fees.md)), as well register the delegate fees passed as parameters during the loan initialization. This contract exists as a module to allow future Loans to be able to use different fee structures with new smart contract logic.

# Fee Lifecycle

## Loan Initialization

During Loan initialization, Loans save the fees owned to the Pool Delegate and the platform. Pool Delegate fees are specified as part of the Loan terms, and platform fees are queried from Globals and are configured by the Governor on a per-pool basis.

## Funding

When the Loan is funded, the origination fees owed are paid atomically using `payOriginationFees`. At the time of funding, Globals is queried and the platform origination fees are saved using `updatePlatformServiceFee`.

## Refinancing

During funding and refinanced, loans query the FeeManager for the saved values for both treasury and delegate origination fees and then pay them, reducing the drawable amounts. This is done by calling `updatePlatformServiceFee`, and optionally `updateDelegateFeeTerms` if part of the refinance terms. In addition, the service fees accrued between the last payment due date and refinance are saved in the FeeManager to be added to the subsequent payment with `updateRefinanceServiceFees`.

## Making Payments

When payments to the loans are made, they query the FeeManager to fetch service fees owed to all parties and pay them, using the value passed by the Borrower. This is done through `payServiceFees`.
