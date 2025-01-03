# Fixed Term Loans

## Accounting

### Asset Definitions

Loans manage two assets: `collateralAsset` and `fundsAsset`.

#### `fundsAsset`

This represents the ERC-20 token that is used to facilitate the funding, drawing down, and payments during a loan lifecycle. Typically this would be a stablecoin such as USDC, DAI, or USDT.

#### `collateralAsset`

This represents the ERC-20 token that is used to represent the collateral position in the loan, and can be repossessed in the event of a loan defaulting. This is usually a more speculative/volatile asset such as WBTC or WETH. However, **it is important to note that `fundsAsset` and `collateralAsset` can be the same ERC-20 (e.g., a $10m USDC loan can be collateralized with $1m of USDC).**

### Accounting with Contract State

In order to account for the amount of a given asset present in the loan that is designated for a specific purpose, there are three accounting variables used in state:

#### `drawableFunds`

Represents the amount of `fundsAsset` that can be drawn from the Loan by the Borrower.

This value is only incremented when:

* A Loan gets funded by a Lender
* A regular payment is made, sending too much `fundsAsset`. Excess gets added to `drawableFunds`
* A Loan is closed early, sending too much `fundsAsset`. Excess gets added to `drawableFunds`
* A Borrower calls `returnFunds`, adding `fundsAsset` back into the Loan to reduce outstanding principal (allows them to withdraw collateral)
* A Lender accepts new terms that result in an increase of principal

This value is only decremented when:

* The Loan is drawn down on by the Borrower
* The Loan is repossessed by the Lender (set to zero)
* A Lender accepts new terms that result in an decrease of principal

#### `collateral`

Represents the amount of `collateralAsset` that is present in the Loan, counting towards the specified collateralization ratio.

This value is only incremented when:

* The Borrower posts collateral (can be done alone or atomically during `drawdownFunds`)

This value is only decremented when:

* The Borrower removes collateral (only possible if collateralization ratio is still maintained)
* The Loan is repossessed by the Lender (set to zero)

#### `_getUnaccountedAmount`

This is a function that is used internally during function calls to account for ERC-20 tokens present in the Loan contract that have not yet been accounted for.

```solidity
function _getUnaccountedAmount(address asset_) internal view virtual returns (uint256 amount_) {
    return IERC20(asset_).balanceOf(address(this))
        - (asset_ == _collateralAsset ? _collateral : uint256(0))
        - (asset_ == _fundsAsset ? _drawableFunds : uint256(0));
}
```

This function returns the amount of a given asset in a Loan that has not yet been accounted for by the three variables outlined above. This amount is then accounted for. A good example of this is in `_postCollateral`:

```solidity
function _postCollateral() internal returns (uint256 amount_) {
    _collateral += (amount_ = _getUnaccountedAmount(_collateralAsset));
}
```

NOTE: After any function that is called when this internal function is used, `_getUnaccountedAmount` should return zero for `_collateralAsset` or `_fundsAsset` respectively, depending on which (or both) were involved in operations.

This functionality allows for both "pull" (`transferFrom`) and "push" (`transfer`) patterns to be used with ERC-20s. All external functions in the Loan support "pull" patterns, while all internal functions use the `_getUnaccountedAmount` function so that more powerful atomic actions can be performed in the future with push patterns.

An example of this would be doing one `approve` to a smart contract, and that smart contract doing the following:

* `transferFrom` all funds into smart contract
* Call `transfer` to many Loans for payment amounts
* Call `makePayment` to many Loans for payment amounts

This prevents the extra `approve` step in the smart contract, reducing gas costs and complexity.

### Collateral Ratio

Collateral is governed through an implied ratio that is declared on Loan instantiation. This ratio is between `collateralRequired` and `principalRequired`.

`principalRequired` represents the total amount of starting principal that the Loan will use for payments.

`collateralRequired` represents the corresponding minimum collateral amount that satisfies the collateral ratio when the entire `principalRequired` amount is outstanding.

This ratio is defined as `collateralRequired / principalRequired` and is denominated in `collateralAssetUnits / fundsAssetUnits`.

An example of this is a Loan for 10m USDC that is to be collateralized with 200 WBTC. The collateralization ratio is `200 WBTC / 10m USDC` or `0.00002 WBTC / USDC`.

### Collateral Maintenance

The collateral in a Loan must always satisfy the equation shown below in order to meet collateral maintenance requirements.

$$
\large \begin{align} \nonumber \frac{collateral}{outstandingPrincipal} \ge \frac{collateralRequired}{principalRequired} \end{align}
$$

where:

* `collateral` is the current `collateralAsset` accounted for in the Loan
* `outstandingPrincipal` is the current principal remaining (`principal`), minus any `drawableFunds` present in the Loan.

Rearranged, this gives us the minimum amount of `collateralAsset` that must be present in the Loan at any given time:

$$
\large \begin{align} \nonumber collateral \ge \frac{collateralRequired \times outstandingPrincipal}{principalRequired} \end{align}
$$

This means that as the `outstandingPrincipal` decreases (which it will over the course of an amortized Loan), more and more `collateralAsset` can be safely withdrawn by the Borrower, increasing capital efficiency.

It should also be noted that a Borrower can call `returnFunds` and an amount of funds back to the Loan if they would like to withdraw collateral, so long as the ratio is maintained. They will still pay interest against the same principal amount, but the Loan's collateral requirements have dropped since those added funds can be repossessed, so the outstanding principal (i.e. risk) is considered to be decreased.

## Payments

### Amortization Calculation

When a Loan is instantiated, the following parameters are declared and affect the payment calculations that are used in the Loan:

* `principalRequested`: Total principal amount owed on the Loan.
* `endingPrincipal`: Principal balance to be remaining at the end of the Loan (i.e. the Loan is fully amortized if this amount is zero, the Loan is interest-only if this amount is equal to `principalRequested`, and anything in between would be partially amortized).
* `interestRate`: Annualized interest rate to be used over the course of the Loan.
* `paymentInterval`: Time between payment due dates in seconds.
* `paymentsRemaining`: Total number of payments to be made over the course of the Loan.

The amortized payment schedule is calculated using a standard amortization calculation [formula](https://en.wikipedia.org/wiki/Amortization_calculator).

$$
\large \begin{align} \nonumber periodicRate = \frac{interestRate \times paymentInterval}{365 \times 24 \times 60 \times 60} \end{align}
$$

$$
\large \begin{align} \nonumber raisedRate = (1 + periodicRate)^{paymentsRemaining} \end{align}
$$

$$
\large \begin{align} \nonumber total = \frac{(principal \times raisedRate - endingPrincipal) \ periodicRate}{raisedRate - 1} \end{align}
$$

$$
\large \begin{align} \nonumber interestPortion = principal \times periodicRate \end{align}
$$

$$
\large \begin{align} \nonumber principalPortion = total - interestPortion \end{align}
$$

### Late Payments

When a payment is made after the `nextPaymentDueDate` timestamp in the Loan, it is considered late. There are two fee parameters that are used to calculate late fees:

* `lateInterestPremiumRate`: Premium on regular interest rate when payment is late (E.g., premium is 2% on 10% interest, 12% interest is paid on time that payment is late).
* `lateFeeRate`: Fee charged as a percentage of the outstanding principal at the time of payment.

Below is the calculation for a late payment, where `total` is the amount calculated in the equations above. All of the extra funds go towards interest.

$$
\large \begin{align} \nonumber totalLatePayment = total + (principal \times lateFeeRate) + defaultInterest \end{align}
$$

where:

$$
\large \begin{align} \nonumber defaultInterest = \frac{principal \times (interestRate + lateInterestPremiumRate) \times daysLate \times 86400}{365 \times 86400} \end{align}
$$

## Closing Loan

If a Borrower wants to close a Loan prematurely, they can do so by calling `closeLoan`. This will allow them to pay back their entire principal balance in one transaction. There is one fee parameter used to calculate the fees associated with this action:

* `closingRate`: Fee charged as a percentage of the outstanding principal at the time of payment.

Below is the calculation for `closeLoan` payment.

$$
\large \begin{align} \nonumber total = principal \times closingRate \end{align}
$$

## Initialization Parameters

* `borrower` - The address of the borrower.
* `lender` - The address of the lender.
* `feeManager` - The address of the entity responsible for storing and calculating loan fees. ([See here](fee-manager.md))
* `collateralAsset` - The address of the asset used as collateral.
* `fundsAsset` - The address of asset that the loan is denominated in.
* `gracePeriod` - The amount of time that the lender needs to wait before triggering a default on a late loan.\\
* `paymentInterval` - The amount of seconds between each loan payment.
* `payments` - The amount of payments in the loan term.
* `collateralRequired` - The nominal amount of the collateral asset.
* `principalRequested` - The nominal amount of principal of the fundsAsset.
* `endingPrincipal`- The expected amount of principal to be paid at the end term. This defines the amortization rate of the loan.
* `interestRate` - The annualized interest rate.
* `closingFeeRate` - The rate used to calculate closing a loan early.
* `lateFeeRate` - A fee rate applied on principal amount on late payments.
* `lateInterestPremiumRate` - A premium added on top of the interest rate for late payments.
* `delegateOriginationFee` - A nominal amount of funds asset payment on the origination to the pool delegate.
* `delegateServiceFee` - A nominal amount of funds assets that is added on every payment destined to the pool delegate.

### Parameters Constraints

* `delegateOriginationFee` <= 2.5% of principal
* `gracePeriod` >= 12 hours
* `paymentInterval` > 0
* `payments` > 0

## Fee Manager

`FeeManager` is a singleton contract responsible for holding and executing fee payments for all the loans. It queries the MapleGlobals contract to calculate fees owed to the protocol ([more details here](../protocol-overview/fees.md)), as well register the delegate fees passed as parameters during the loan initialization. This contract exists as a module to allow future Loans to be able to use different fee structures with new smart contract logic.

#### Loan Initialization

During Loan initialization, Loans save the fees owned to the Pool Delegate and the platform. Pool Delegate fees are specified as part of the Loan terms, and platform fees are queried from Globals and are configured by the Governor on a per-pool basis.

#### Funding

When the Loan is funded, the origination fees owed are paid atomically using `payOriginationFees`. At the time of funding, Globals is queried and the platform origination fees are saved using `updatePlatformServiceFee`.

#### Refinancing

During funding and refinanced, loans query the FeeManager for the saved values for both treasury and delegate origination fees and then pay them, reducing the drawable amounts. This is done by calling `updatePlatformServiceFee`, and optionally `updateDelegateFeeTerms` if part of the refinance terms. In addition, the service fees accrued between the last payment due date and refinance are saved in the FeeManager to be added to the subsequent payment with `updateRefinanceServiceFees`.

#### Making Payments

When payments to the loans are made, they query the FeeManager to fetch service fees owed to all parties and pay them, using the value passed by the Borrower. This is done through `payServiceFees`.
