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

## Strategy Fees

Each Underlying Strategy charges two fees on the yield it earns, never on principal:

1. `strategyDelegateFeeRate`, paid to the Strategy Delegate.
2. `strategyProtocolFeeRate`, paid to the `MapleTreasury`.

Both rates are scaled by `1e6` (`HUNDRED_PERCENT`), so `50_000` is 5%. Each rate must not exceed `1e6`, and the two together must not exceed `1e6`. The initializer checks the sum at deployment and both setters check it again. The Strategy Delegate sets `strategyDelegateFeeRate` through `setStrategyDelegateFeeRate()`, and the Governor or Operational Admin sets `strategyProtocolFeeRate` through `setStrategyProtocolFeeRate()`.

The Strategy Manager charges nothing. It prices Pool shares on the Underlying Strategy's `assetsUnderManagement()`, which is already net of fees. Pool management fees apply to loan interest only and never touch strategy yield.

### Aave V3 and Sky: accrual basis

These strategies earn yield continuously as the aToken balance or sUSDS value grows, so fees accrue on the growth since the last harvest:

```
yieldAccrued = currentTotalAssets - lastRecordedTotalAssets   (zero if not positive)
delegateFee  = yieldAccrued * strategyDelegateFeeRate / 1e6
protocolFee  = yieldAccrued * strategyProtocolFeeRate / 1e6
```

Accrued fees are withdrawn from the underlying protocol and paid out whenever a call touches the position: `fundUnderlyingStrategy()`, `withdrawFromUnderlyingStrategy()`, `setStrategyDelegateFeeRate()` and `setStrategyProtocolFeeRate()`. Each of these resets `lastRecordedTotalAssets` to the position after the harvest, so a rate change applies only to yield earned after it. Between harvests, `assetsUnderManagement()` and `availableToWithdraw()` already deduct the accrued fees, so Pools never count fee amounts as their own value. Very small accruals can round a fee down to zero. The Sky Strategy's fee-rate setters revert while Sky halts the PSM `buyGem()` path (`tout == type(uint256).max`).

### Allocation Strategy: cash basis

The Allocation Strategy earns nothing on its own. A Managed Wallet reports profit by calling `realizeYield(yield, duration, metadata)` and transferring the yield in. Fees come out of that gross amount immediately. The net yield joins `recordedAssets` at once and vests over `duration`. Until it vests, `availableToWithdraw()` and `assetsUnderManagement()` exclude it:

```
delegateFee = yield * strategyDelegateFeeRate / 1e6
protocolFee = yield * strategyProtocolFeeRate / 1e6
netYield    = yield - delegateFee - protocolFee
```

Fees apply only to the yield passed in that call, never to yield still vesting from earlier calls. Changing a fee rate on the Allocation Strategy harvests nothing, because nothing accrues between calls.

See the accounting pages for [Aave V3](../strategies/aave-v3-strategy/accounting-and-fees.md), [Sky](../strategies/sky-strategy/accounting-and-fees.md) and the [Allocation Strategy](../strategies/allocation-strategy/accounting-and-fees.md).
