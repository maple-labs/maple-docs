# Accounting and Fees

The Sky Strategy holds sUSDS shares but reports everything in the Pool's funds asset. This page explains how it values those shares through the PSM, how much of that value it can return at any moment, and how it takes fees out of the growth.

## PSM fees: `tin` and `tout`

A Sky PSM swaps the gem (USDC) and USDS one for one, minus two fees that Sky sets. Both are scaled to 18 decimals (`1e18` is 100%).

| PSM call | Direction | Fee | Used by the strategy in |
|---|---|---|---|
| `sellGem(usr, gemAmount)` | Gem in, USDS out | `tin`, deducted from the USDS returned | Funding |
| `buyGem(usr, gemAmount)` | USDS in, gem out | `tout`, added to the USDS charged | Withdrawals and fee collection |

`sellGem()` mints USDS to the strategy and moves the gem into the PSM's `pocket()`. `buyGem()` pulls `gemAmount * (1 + tout)` in USDS from the strategy and sends exactly `gemAmount` of gem from the pocket to `usr`.

The strategy never reads `tin`. An entry fee simply shows up as a smaller position after funding. It reads `tout` everywhere, because every exit from the position goes through `buyGem()`. Sky halts `buyGem()` by setting `tout` to `type(uint256).max`, and halts `sellGem()` the same way with `tin`.

## Valuing the position

`assetsUnderManagement()` is the amount of funds asset the strategy could recover right now through `buyGem()`, net of accrued fees:

```
usdsValue             = savingsUsds.previewRedeem(savingsUsds.balanceOf(strategy))
currentTotalAssets    = usdsValue * 1e18 / (to18ConversionFactor * (1e18 + tout))
assetsUnderManagement = currentTotalAssets - delegateFee - protocolFee
```

`previewRedeem()` is the ERC-4626 view that converts the sUSDS balance into USDS at the vault's current rate. This number grows on its own as the Sky Savings Rate accrues. `to18ConversionFactor()` is the PSM's scaling factor from gem decimals to 18 decimals (`1e12` for USDC). Dividing by `1 + tout` deducts the exit fee up front, so AUM never shows value that a withdrawal would lose to the PSM. A change in `tout` therefore moves AUM immediately.

`assetsUnderManagement()` returns `0` once a loss is recognized. `impairedAssets` is not deducted here. It is reported through `unrealizedLosses()` instead, see [Impairments and Losses](impairments-and-losses.md).

### Fallback `tout`

Valuation reads `tout` through `_getTout()`. While the live `tout` is `type(uint256).max` (a halt), `_getTout()` substitutes `fallbackTout` so that `assetsUnderManagement()` keeps returning a finite figure instead of collapsing to zero or reverting. The Strategy Manager and every Pool share price depend on this view, so the fallback keeps them stable through a halt.

`setFallbackTout(fallbackTout)` is the only way to change the fallback. The Strategy Delegate or Operational Admin calls it, the new value must differ from the current one, and it cannot exceed `1e18` (a 100% fee). In normal operation it should mirror the live `tout`, so that valuation does not jump when a halt begins. Nothing else reads `fallbackTout`. Withdrawals and fee collection always use the live `tout`.

## Available liquidity

`availableToWithdraw()` is what the Strategy Manager can pull out in a single transaction:

```
pocketLiquidity     = fundsAsset.balanceOf(psm.pocket())
availableToWithdraw = min(currentTotalAssets, pocketLiquidity) - delegateFee - protocolFee
```

A LitePSM keeps its gem reserves at `psm.pocket()`, not on the PSM contract, which is why the initializer requires a non-zero pocket. The strategy can only redeem as much gem as the pocket holds. The function returns `0` when a loss is recognized, when `tout` is `type(uint256).max`, when the DaiJoin behind the PSM is caged (`psm.psm().daiJoin().live() != 1`), or when accrued fees are at least as large as the gross amount.

## Fee accrual

There is no fee collection function. Fees accrue on the growth of the position since the last checkpoint:

```
yieldAccrued = max(currentTotalAssets - lastRecordedTotalAssets, 0)
delegateFee  = yieldAccrued * strategyDelegateFeeRate / 1e6
protocolFee  = yieldAccrued * strategyProtocolFeeRate / 1e6
```

`assetsUnderManagement()` and `availableToWithdraw()` always subtract these fees, so readers never see value that the next harvest will remove. If the position is worth less than `lastRecordedTotalAssets`, for example after `tout` rises, both fees are zero.

The strategy harvests fees at the start of `fundUnderlyingStrategy()`, `setStrategyDelegateFeeRate()` and `setStrategyProtocolFeeRate()`, and together with the withdrawal in `withdrawFromUnderlyingStrategy()`. Each harvest makes one sUSDS `withdraw()` and one PSM `buyGem()` that pays the strategy both fees plus any withdrawal amount. It skips both calls when that total is zero. The strategy then transfers each non-zero fee, `delegateFee` to the Strategy Delegate and `protocolFee` to the Maple Treasury, and emits `StrategyFeesCollected(delegateFee, protocolFee)`, even when both are zero. The calling function then sets `lastRecordedTotalAssets` to the resulting position, which becomes the baseline for the next accrual.

Because harvesting uses the live `tout`, fees cannot be collected while the PSM is halted. See [Funding and Withdrawals](funding-and-withdrawals.md#when-the-psm-is-halted).

## Fee rates

`setStrategyDelegateFeeRate(rate)` is restricted to the Strategy Delegate. `setStrategyProtocolFeeRate(rate)` is restricted to the Governor or Operational Admin. Each requires:

- The new rate differs from the current one.
- The new rate is at most `1e6`.
- The new rate plus the other rate is at most `1e6`.

Both setters harvest at the old rate before storing the new one, so a rate change never applies retroactively. Both revert while the PSM `buyGem()` path is halted (`tout == type(uint256).max`), even when no fees have accrued, and once a loss is recognized.
