Loans in the Maple protocol are deployed from a factory and initialized by Borrowers. They facilitate the following:

1. Perform Loan funding.
2. Draw down funds.
3. Manage collateral.
4. Calculate payment amounts and schedules (can handle amortized and interest-only payment structures).
5. Perform repossessions of collateral and remaining funds in a defaulted Loan.
6. Claim interest and principal from Loans.
7. Perform refinancing operations when a lender and borrower agree to new terms.
8. Upgrade Loan logic using upgradeability patterns.

# Accounting

## Asset Definitions

Loans manage two assets: `collateralAsset` and `fundsAsset`.

### `fundsAsset`

This represents the ERC-20 token that is used to facilitate the funding, drawing down, and payments during a loan lifecycle. Typically this would be a stablecoin such as USDC, DAI, or USDT.

### `collateralAsset`

This represents the ERC-20 token that is used to represent the collateral position in the loan, and can be repossessed in the event of a loan defaulting. This is usually a more speculative/volatile asset such as WBTC or WETH. However, **it is important to note that `fundsAsset` and `collateralAsset` can be the same ERC-20 (e.g., a $10m USDC loan can be collateralized with $1m of USDC).**

## Accounting with Contract State

In order to account for the amount of a given asset present in the loan that is designated for a specific purpose, there are three accounting variables used in state:

### `drawableFunds`

Represents the amount of `fundsAsset` that can be drawn from the Loan by the Borrower.

This value is only incremented when:
- A Loan gets funded by a Lender
- A regular payment is made, sending too much `fundsAsset`. Excess gets added to `drawableFunds`
- A Loan is closed early, sending too much `fundsAsset`. Excess gets added to `drawableFunds`
- A Borrower calls `returnFunds`, adding `fundsAsset` back into the Loan to reduce outstanding principal (allows them to withdraw collateral)
- A Lender accepts new terms that result in an increase of principal

This value is only decremented when:
- The Loan is drawn down on by the Borrower
- The Loan is repossessed by the Lender (set to zero)
- A Lender accepts new terms that result in an decrease of principal

### `collateral`

Represents the amount of `collateralAsset` that is present in the Loan, counting towards the specified collateralization ratio.

This value is only incremented when:
- The Borrower posts collateral (can be done alone or atomically during `drawdownFunds`)

This value is only decremented when:
- The Borrower removes collateral (only possible if collateralization ratio is still maintained)
- The Loan is repossessed by the Lender (set to zero)

### `_getUnaccountedAmount`

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
- `transferFrom` all funds into smart contract
- Call `transfer` to many Loans for payment amounts
- Call `makePayment` to many Loans for payment amounts

This prevents the extra `approve` step in the smart contract, reducing gas costs and complexity.

## Collateral Ratio

Collateral is governed through an implied ratio that is declared on Loan instantiation. This ratio is between `collateralRequired` and `principalRequired`.

`principalRequired` represents the total amount of starting principal that the Loan will use for payments.

`collateralRequired` represents the corresponding minimum collateral amount that satisfies the collateral ratio when the entire `principalRequired` amount is outstanding.

This ratio is defined as `collateralRequired / principalRequired` and is denominated in `collateralAssetUnits / fundsAssetUnits`.

An example of this is a Loan for 10m USDC that is to be collateralized with 200 WBTC.
The collateralization ratio is `200 WBTC / 10m USDC` or `0.00002 WBTC / USDC`.

## Collateral Maintenance

The collateral in a Loan must always satisfy the equation shown below in order to meet collateral maintenance requirements.



$$
\large
\begin{align}
\nonumber \frac{collateral}{outstandingPrincipal} \ge \frac{collateralRequired}{principalRequired}
\end{align}
$$



Where:
- `collateral` is the current `collateralAsset` accounted for in the Loan
- `outstandingPrincipal` is the current principal remaining (`principal`), minus any `drawableFunds` present in the Loan.

Rearranged, this gives us the minimum amount of `collateralAsset` that must be present in the Loan at any given time:



$$
\large
\begin{align}
\nonumber collateral \ge \frac{collateralRequired \times outstandingPrincipal}{principalRequired}
\end{align}
$$



This means that as the `outstandingPrincipal` decreases (which it will over the course of an amortized Loan), more and more `collateralAsset` can be safely withdrawn by the Borrower, increasing capital efficiency.

It should also be noted that a Borrower can call `returnFunds` and an amount of funds back to the Loan if they would like to withdraw collateral, so long as the ratio is maintained. They will still pay interest against the same principal amount, but the Loan's collateral requirements have dropped since those added funds can be repossessed, so the outstanding principal (i.e. risk) is considered to be decreased.

# Payments

## Amortization Calculation

When a Loan is instantiated, the following parameters are declared and affect the payment calculations that are used in the Loan:
- `principalRequested`: Total principal amount owed on the Loan.
- `endingPrincipal`: Principal balance to be remaining at the end of the Loan (i.e. the Loan is fully amortized if this amount is zero, the Loan is interest-only if this amount is equal to `principalRequested`, and anything in between would be partially amortized).
- `interestRate`: Annualized interest rate to be used over the course of the Loan.
- `paymentInterval`: Time between payment due dates in seconds.
- `paymentsRemaining`: Total number of payments to be made over the course of the Loan.

The amortized payment schedule is calculated using a standard amortization calculation [formula](https://en.wikipedia.org/wiki/Amortization_calculator).



$$
\large
\begin{align}
\nonumber periodicRate     = \frac{interestRate \times paymentInterval}{365 \times 24 \times 60 \times 60}
\end{align}
$$
$$
\large
\begin{align}
\nonumber raisedRate       = (1 + periodicRate)^{paymentsRemaining}
\end{align}
$$
$$
\large
\begin{align}
\nonumber total            = \frac{(principal \times raisedRate - endingPrincipal) \ periodicRate}{raisedRate - 1}
\end{align}
$$
$$
\large
\begin{align}
\nonumber interestPortion  = principal \times periodicRate
\end{align}
$$
$$
\large
\begin{align}
\nonumber principalPortion = total - interestPortion
\end{align}
$$



## Late Payments

When a payment is made after the `nextPaymentDueDate` timestamp in the Loan, it is considered late. There are two fee parameters that are used to calculate late fees:
- `lateInterestPremium`: Premium on regular interest rate when payment is late (E.g., premium is 2% on 10% interest, 12% interest is paid on time that payment is late).
- `lateFeeRate`: Fee charged as a percentage of the outstanding principal at the time of payment.

Below is the calculation for a late payment, where `total` is the amount calculated in the equations above. All of the extra funds go towards interest.



$$
\large
\begin{align}
\nonumber totalLatePayment &= total + (principal \times lateFeeRate) + \\
                           &\frac{principal \times (interestRate + lateInterestPremium) \times daysLate \times 86400}{365 \times 86400}
\end{align}
$$



# Closing Loan

If a Borrower wants to close a Loan prematurely, they can do so by calling `closeLoan`. This will allow them to pay back their entire principal balance in one transaction. There is one fee parameter used to calculate the fees associated with this action:
- `closingRate`: Fee charged as a percentage of the outstanding principal at the time of payment.

Below is the calculation for `closeLoan` payment.



$$
\large
\begin{align}
\nonumber total = principal \times closingRate
\end{align}
$$


