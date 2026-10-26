# Accounting and Fees

The strategy values its position from the aToken balance that Aave reports, not from an internal ledger. This page covers the two views the Strategy Manager reads, `assetsUnderManagement()` and `availableToWithdraw()`, and how Maple's fees accrue out of the growth of that balance.

## Assets under management

Aave's aToken rebases upward as the reserve earns interest, so the strategy's aToken balance is both principal and accrued yield.

```
currentTotalAssets      = aaveToken.balanceOf(strategy)
assetsUnderManagement() = currentTotalAssets - delegateFee - protocolFee
```

`delegateFee` and `protocolFee` are the fees accrued since the last checkpoint, computed as described under [Fee accrual](#fee-accrual). The view nets them out before they are harvested, so AUM never drops when the next interaction collects them. Both `currentTotalAssets` and `assetsUnderManagement()` return `0` once a loss is recognised.

| Component | In `assetsUnderManagement()` |
|---|---|
| aToken balance (principal plus Aave interest) | Yes |
| Fees accrued since the last checkpoint | No, netted out |
| `impairedAssets` | No, reported through `unrealizedLosses()`, see [Impairments and Losses](impairments-and-losses.md) |
| Aave rewards | No, a separate token stream, see [Rewards](funding-and-withdrawals.md#rewards) |

## Available to withdraw

`availableToWithdraw()` is the amount the Strategy Manager can pull out right now. It is bounded by the reserve's free liquidity and net of accrued fees, because the next withdrawal harvests those fees from the same Aave balance.

```
aaveLiquidity         = useVirtualUnderlyingBalance
                          ? aavePool.getVirtualUnderlyingBalance(fundsAsset)
                          : fundsAsset.balanceOf(aaveToken)
grossAvailable        = min(currentTotalAssets, aaveLiquidity)
availableToWithdraw() = grossAvailable > delegateFee + protocolFee
                          ? grossAvailable - delegateFee - protocolFee
                          : 0
```

The view returns `0` without reading liquidity when:

- a loss has been recognised, or
- the Aave reserve is not withdrawable. The strategy resolves the Aave pool data provider through `aavePool.ADDRESSES_PROVIDER().getPoolDataProvider()` and requires the reserve's `isActive` flag to be set and its `getPaused()` flag to be clear. It checks only these two flags.

### Virtual underlying balance switch

Aave V3 markets track each reserve's available liquidity in a virtual accounting figure, `getVirtualUnderlyingBalance()`. Some Aave V3-compatible forks, such as SparkLend, do not expose it, and the funds asset balance held by the aToken contract is the right measure there.

`useVirtualUnderlyingBalance` selects between the two. It is set at initialization and the Governor or Operational Admin can change it with `setUseVirtualUnderlyingBalance(bool)`. The call reverts if the value does not change or if a loss has been recognised. The setting affects only `availableToWithdraw()`. It has no effect on AUM or fees.

## Fee accrual

Fees accrue continuously from the growth of the aToken balance since `lastRecordedTotalAssets`, the checkpoint the strategy saves after each harvest.

```
yieldAccrued = currentTotalAssets > lastRecordedTotalAssets
                 ? currentTotalAssets - lastRecordedTotalAssets
                 : 0
delegateFee  = yieldAccrued * strategyDelegateFeeRate / HUNDRED_PERCENT
protocolFee  = yieldAccrued * strategyProtocolFeeRate / HUNDRED_PERCENT
```

`HUNDRED_PERCENT` is `1e6`. Both fee rates have 6 decimals. A fee rounds down to `0` when `yieldAccrued * rate < 1e6`.

### Harvesting

There is no standalone function to collect fees. Four functions call the same internal routine before doing their own work:

| Function | Harvests fees |
|---|---|
| `fundUnderlyingStrategy()` | Before supplying new capital, so the deposit does not count as yield. |
| `withdrawFromUnderlyingStrategy()` | In the same Aave `withdraw()` call that serves the requested assets. |
| `setStrategyDelegateFeeRate()` | At the old rate, before the new rate applies. |
| `setStrategyProtocolFeeRate()` | At the old rate, before the new rate applies. |

The routine computes `delegateFee` and `protocolFee`, withdraws `assets + delegateFee + protocolFee` from Aave in one call (skipped when the total is zero), transfers `delegateFee` to the Strategy Delegate and `protocolFee` to the Maple Treasury, then emits `StrategyFeesCollected(delegateFee, protocolFee)`. The event fires even when both amounts are zero. The calling function then sets `lastRecordedTotalAssets` to the new aToken balance, which becomes the baseline for the next accrual.

Because harvesting withdraws from Aave, these four functions depend on the reserve having free liquidity. See [the 100% utilisation revert](impairments-and-losses.md#aave-liquidity-and-the-100-utilisation-revert).

### Fee rates

| Setter | Allowed callers |
|---|---|
| `setStrategyDelegateFeeRate(uint32)` | Strategy Delegate |
| `setStrategyProtocolFeeRate(uint32)` | Governor, Operational Admin |

Each setter requires the new rate to differ from the current one, to be at most `1e6`, and for the sum of both rates to stay at or below `1e6` given the other rate's current value. Both setters harvest at the current rates before writing the new rate, so a rate change is never retroactive. Neither can be called after a loss is recognised.
