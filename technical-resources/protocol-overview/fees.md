# Fees

Maple charges fees on loan payments and on strategy yield. Loan fees go to the Pool Delegate and the `MapleTreasury`, and strategy fees go to the Strategy Delegate and the `MapleTreasury`. Lenders receive everything that remains.

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

Service fees are charged on outstanding principal and paid with each loan payment, on top of interest. The Loan stores two annualized rates, scaled by `1e6` (the `HUNDRED_PERCENT` constant, so `100_000` is 10%). It never stores a fee amount.

* `delegateServiceFeeRate` is a loan term set when the loan is created and changes only through a refinance.
* `platformServiceFeeRate` is set per Pool in Globals by the Governor or Operational Admin. The Loan reads it from Globals when it is initialized and again on each refinance, and uses the cached value for every payment in between. A change in Globals reaches an existing loan only at its next refinance.

`fund()` records the funding date and transfers the principal. Fee amounts are computed at payment time by `getPaymentBreakdown(timestamp)`:

$$
\large \begin{align} \nonumber Interval = timestamp - \max(datePaid, dateFunded) \end{align}
$$

$$
\large \begin{align} \nonumber platformServiceFee = platformServiceFeeRate \times principal \times \frac{Interval}{oneYear} \end{align}
$$

$$
\large \begin{align} \nonumber delegateServiceFee = delegateServiceFeeRate \times principal \times \frac{Interval}{oneYear} \end{align}
$$

The same formula applies whether the payment is on time, late, called or impaired. A late payment adds late interest but does not change the service fees. `makePayment()` transfers principal returned, interest and both fees to the Loan Manager in one transfer. The Loan Manager sends the delegate service fee to the Pool Delegate and the platform service fee to the `MapleTreasury`.

On default, the Loan Manager calculates the platform service fee up to the impairment date and pays it to the `MapleTreasury` from recovered funds before the Pool receives anything. The delegate service fee is not collected on a defaulted loan.

### Refinancing of Service Fees

Open Term Loans have no maturity date, so a refinance is the only point at which service fee terms change. When the Borrower accepts new terms through `acceptNewTerms()`:

1. The Loan computes interest and both service fees accrued from the last payment or funding date up to the refinance, using the rates in force before the refinance, and settles them as part of the refinance.
2. The refinancer calls apply the new terms. `setDelegateServiceFeeRate()` updates `delegateServiceFeeRate` if it is included. Otherwise the rate is unchanged.
3. The Loan reads `platformServiceFeeRate` for the Pool from Globals again and caches it.
4. `datePaid` is set to the refinance time, so the next payment accrues from the refinance under the new rates and principal.

## Management Fees

Management fees are paid during loan payments, after a loan's interest has moved out of the loan and into the Pool contracts. Management fees are deducted from gross interest paid by borrowers using the following formula:

$$
\large \begin{align} \nonumber managementFee = grossInterest \times managementFeeRate \end{align}
$$

The remainder of the interest (net interest) goes to the Liquidity Providers.

## Strategy Fees

Each Underlying Strategy charges two fees on the yield it earns, never on principal:

1. `strategyDelegateFeeRate`, paid to the Strategy Delegate.
2. `strategyProtocolFeeRate`, paid to the `MapleTreasury`.

Both rates are scaled by `1e6` (`HUNDRED_PERCENT`), so `50_000` is 5%. Each rate must not exceed `1e6`, and the two together must not exceed `1e6`. The initializer checks the sum at deployment and both setters check it again. The Strategy Delegate sets `strategyDelegateFeeRate` through `setStrategyDelegateFeeRate()`, and the Governor or Operational Admin sets `strategyProtocolFeeRate` through `setStrategyProtocolFeeRate()`.

The Strategy Manager charges nothing. It prices Pool shares on the Underlying Strategy's `assetsUnderManagement()`, which is already net of fees. Pool management fees apply to loan interest only and never touch strategy yield.

### Aave V3 and Sky: accrual basis

These strategies earn yield continuously as the aToken balance or sUSDS value grows, so fees accrue on the growth since the last harvest:

$$
\large \begin{align} \nonumber yieldAccrued = \max(currentTotalAssets - lastRecordedTotalAssets, 0) \end{align}
$$

$$
\large \begin{align} \nonumber delegateFee = \frac{yieldAccrued \times strategyDelegateFeeRate}{1 \times 10^6} \end{align}
$$

$$
\large \begin{align} \nonumber protocolFee = \frac{yieldAccrued \times strategyProtocolFeeRate}{1 \times 10^6} \end{align}
$$

Accrued fees are withdrawn from the underlying protocol and paid out whenever a call touches the position: `fundUnderlyingStrategy()`, `withdrawFromUnderlyingStrategy()`, `setStrategyDelegateFeeRate()` and `setStrategyProtocolFeeRate()`. Each of these resets `lastRecordedTotalAssets` to the position after the harvest, so a rate change applies only to yield earned after it. Between harvests, `assetsUnderManagement()` and `availableToWithdraw()` already deduct the accrued fees, so Pools never count fee amounts as their own value. Very small accruals can round a fee down to zero. The Sky Strategy's fee-rate setters revert while Sky halts the PSM `buyGem()` path (`tout == type(uint256).max`).

### Allocation Strategy: cash basis

The Allocation Strategy earns nothing on its own. A Managed Wallet reports profit by calling `realizeYield(yield, duration, metadata)` and transferring the yield in. Fees come out of that gross amount immediately. The net yield joins `recordedAssets` at once and vests over `duration`. Until it vests, `availableToWithdraw()` and `assetsUnderManagement()` exclude it:

$$
\large \begin{align} \nonumber delegateFee = \frac{yield \times strategyDelegateFeeRate}{1 \times 10^6} \end{align}
$$

$$
\large \begin{align} \nonumber protocolFee = \frac{yield \times strategyProtocolFeeRate}{1 \times 10^6} \end{align}
$$

$$
\large \begin{align} \nonumber netYield = yield - delegateFee - protocolFee \end{align}
$$

Fees apply only to the yield passed in that call, never to yield still vesting from earlier calls. Changing a fee rate on the Allocation Strategy harvests nothing, because nothing accrues between calls.

See the accounting pages for [Aave V3](../strategies/aave-v3-strategy/accounting-and-fees.md), [Sky](../strategies/sky-strategy/accounting-and-fees.md) and the [Allocation Strategy](../strategies/allocation-strategy/accounting-and-fees.md).
