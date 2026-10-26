# Impairments and Losses

The Sky Strategy has one counterparty, Sky's savings system through one PSM. It therefore offers a reversible write-down for a position that looks doubtful, and a single, final switch that writes the whole strategy off.

## Impairments

The Strategy Delegate or Operational Admin calls `impair(assets)` to record that `assets` of the position may not be recoverable. The call adds `assets` to `impairedAssets` and emits `Impaired(assets)`. It changes nothing else. The sUSDS balance, `assetsUnderManagement()`, `availableToWithdraw()` and `lastRecordedTotalAssets` are unaffected.

Impairments reach the Pools through one view:

```
unrealizedLosses() = min(impairedAssets, assetsUnderManagement())
```

The [Strategy Manager](../strategy-manager.md) reads this value, caps it at its own AUM and apportions it to each Pool by shares. The `min()` means unrealized losses can never exceed what the strategy reports as AUM, and they fall to `0` automatically once AUM does.

`removeImpairment(assets)` reverses a write-down. The same callers may use it, `assets` must be non-zero and must not exceed `impairedAssets`. It emits `ImpairmentRemoved(assets)`.

Both functions revert once a loss is recognized.

## Recognizing a loss

`recognizeLoss()` takes no arguments. It is a one-way shutdown of the whole strategy, not a partial write-off. The Strategy Delegate or Operational Admin calls it once the recoverable part of the position has been withdrawn and the remainder is considered lost. It requires that a loss has not already been recognized.

On success the strategy:

- Sets `isLossRecognized` to `true`. Nothing ever sets it back.
- Resets `lastRecordedTotalAssets` and `impairedAssets` to `0`.
- Emits `LossRecognized()`.

It does not harvest fees first. Every other function that moves `lastRecordedTotalAssets` collects accrued fees before resetting the baseline, but `recognizeLoss()` zeroes the baseline directly. Any yield that accrued since the last harvest is never paid to the Strategy Delegate or the Treasury. Since `currentTotalAssets` reads as `0` from this point, the strategy also has no way to compute that figure later.

### Effects

From the moment `isLossRecognized` is `true`:

- `assetsUnderManagement()`, `availableToWithdraw()` and `unrealizedLosses()` return `0`, regardless of the sUSDS balance the strategy still holds.
- The Strategy Manager reports zero AUM, so every Pool's shares in it are worth zero and the loss is reflected in the Pool share prices the next time they are read.
- Funding, withdrawals, impairment changes and the strategy's setters revert with `MSS:LOSS_RECOGNIZED`.

## Recovering the position

`recoverPosition()` is the only function that requires `isLossRecognized` to be `true`. The Strategy Delegate or Operational Admin calls it to move whatever the strategy still holds to the Maple Treasury:

1. Read the strategy's sUSDS balance. Revert with `MSS:RP:ZERO_BALANCE` if it is zero.
2. Transfer the entire balance of sUSDS shares to `mapleTreasury()`.
3. Emit `PositionRecovered(shares)`.

The shares move as sUSDS. The strategy does not redeem them for USDS or convert them through the PSM, so recovery works even while the PSM is halted. In practice the call succeeds once, because the second call finds a zero balance.

Nothing on the contract can return recovered value to the Pools. Working out which Lenders bore the loss, converting the recovered sUSDS and distributing it to them is an off-chain process.
