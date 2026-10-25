# Impairments and Losses

The Aave V3 Strategy has one counterparty, the Aave reserve, so its loss tooling is small. A reversible impairment lowers the value Lenders can exit at while the position is in doubt. A one-way `recognizeLoss()` shuts the strategy down when a loss is final.

## Impairments

The Strategy Delegate or Operational Admin writes the position down with `impair(assets)`, which adds `assets` to `impairedAssets`. `removeImpairment(assets)` reverses it. Both require `assets` to be non-zero, and `removeImpairment()` also requires `assets <= impairedAssets`. Neither touches the Aave position, `lastRecordedTotalAssets` or `assetsUnderManagement()`.

The impairment surfaces through one view:

```
unrealizedLosses() = min(impairedAssets, assetsUnderManagement())
```

The Strategy Manager subtracts `unrealizedLosses()` from AUM when it converts shares to exit assets, so redemptions price in the write-down while reported AUM stays unchanged. While `impairedAssets` is non-zero, Liquidity Bots cannot act on the Strategy Manager. See [Liquidity Bot Actions](../../admin-functions/liquidity-bot-actions.md#the-impairment-block).

## Recognising a loss

`recognizeLoss()` takes no arguments. It is an all-or-nothing shutdown of the strategy instance, not a partial write-off. The Strategy Delegate or Operational Admin calls it once, after withdrawing everything that can reasonably be recovered. It cannot be undone.

The call sets `isLossRecognized = true`, zeroes `lastRecordedTotalAssets` and `impairedAssets`, and emits `LossRecognized()`. From then on:

- `assetsUnderManagement()`, `availableToWithdraw()` and `unrealizedLosses()` return `0`.
- Fees accrued but not yet harvested are forfeited. The strategy never harvests again.
- The aTokens stay in the contract until `recoverPosition()` moves them.
- Funding, withdrawals, impairment changes and the strategy's setters revert with `MAV3S:LOSS_RECOGNIZED`.

The Strategy Manager still holds shares for each Pool against an AUM of `0`. `processRedemption()` reverts with `MSM:PR:ZERO_ASSETS` because the shares convert to no assets, and `fundStrategyManager()` reverts when it calls `fundUnderlyingStrategy()`. The Strategy Manager is finished once a loss is recognised. See [Known Issues and Operational Controls](../../security/known-issues-and-operational-controls.md).

## Recovering the position

`recoverPosition()` sends whatever remains in Aave to the Maple Treasury. The Strategy Delegate or Operational Admin can call it only after a loss is recognised, and it reverts if the strategy holds no aTokens. It transfers the strategy's entire aToken balance, the aTokens themselves rather than the underlying asset, and emits `PositionRecovered(amount)`. It can run again if the balance becomes non-zero later.

Working out which Lenders the loss affected and distributing any recovered value to them happens off-chain.

## Aave liquidity and the 100% utilisation revert

Every fee harvest withdraws from Aave. When the reserve is fully utilised, Aave's `withdraw()` reverts, and with it any strategy function that harvests: `fundUnderlyingStrategy()`, `withdrawFromUnderlyingStrategy()`, `setStrategyDelegateFeeRate()` and `setStrategyProtocolFeeRate()`. Funding reverts only when fees have accrued since the last checkpoint, because the strategy skips the Aave call when there is nothing to withdraw.

This is an availability condition, not a loss. The position keeps earning interest, `availableToWithdraw()` reports the shortfall, and the calls succeed once borrowers repay or new suppliers restore liquidity. `impair()`, `removeImpairment()`, `recognizeLoss()` and `recoverPosition()` do not harvest and remain callable throughout. See [Known Issues and Operational Controls](../../security/known-issues-and-operational-controls.md).
