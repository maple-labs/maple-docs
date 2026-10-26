# Impairments and Losses

Capital held by a Managed Wallet is carried at the amount deployed until an admin writes it down. The Allocation Strategy offers a reversible impairment for capital whose recovery is in doubt, and an irreversible loss for capital confirmed gone. The Strategy Delegate or Operational Admin calls every function on this page.

## Impairing

`impair(assets)` requires `assets > 0` and adds it to `impairedAssets`. Nothing else changes. `totalDeployedAssets`, `deployedAssetsOf` and `recordedAssets` keep their values, and `assetsUnderManagement()` does not fall. The impairment surfaces only through:

```
unrealizedLosses() = min(impairedAssets, assetsUnderManagement())
```

The `min` clamp means `unrealizedLosses()` can never exceed the strategy's own AUM, however large `impairedAssets` becomes. Once AUM reaches zero, for example after a full `recognizeLoss()`, `unrealizedLosses()` reads zero even if `impairedAssets` still shows a figure.

The Strategy Manager subtracts `unrealizedLosses()` from AUM when it converts shares to assets for redemptions, so an impairment discounts what a Pool can withdraw while leaving its share count intact. See [Strategy Manager](../strategy-manager.md).

Impairment is not tied to a wallet. `impairedAssets` is one figure for the whole strategy.

## Removing an impairment

`removeImpairment(assets)` requires `assets > 0` and `assets <= impairedAssets`, then subtracts it from `impairedAssets`. Use it when the position turns out to be recoverable.

## Recognizing a loss

`recognizeLoss(assets, deployer)` writes capital off permanently. It requires `assets != 0` and `assets <= deployedAssetsOf[deployer]`, then subtracts `assets` from both `totalDeployedAssets` and `deployedAssetsOf[deployer]`.

The loss applies only against what `deployer` currently has deployed. It never touches `recordedAssets`, `scheduledYieldAssets` or `impairedAssets`. Because it reduces `totalDeployedAssets`, `assetsUnderManagement()` falls by the same amount in the same transaction, and the Pool's share price with it. The loss spreads across all Lenders immediately, with no separate realization step. It also frees room under the wallet's deployment cap.

**Example.** A wallet has `500,000` deployed. `recognizeLoss(200,000, wallet)` drops `deployedAssetsOf[wallet]` and `totalDeployedAssets` to `300,000`, and AUM falls by `200,000`.

## Resolving an impairment with a loss

When an impaired position is confirmed lost, resolve both in one transaction with `recognizeLossAndRemoveImpairment(assetsLost, assetsUnimpaired, deployer)`. It runs the loss first and then the impairment removal, each with the same checks as the standalone functions, so both amounts must be non-zero and within their respective limits.

Calling `removeImpairment()` and `recognizeLoss()` as separate transactions leaves a window in which the figures are wrong in one direction or the other. Remove the impairment first and the Pool is briefly valued as if nothing were at risk. Recognize the loss first and the same loss is counted twice, once in the lower AUM and again in `unrealizedLosses()`. The combined call avoids both.

`assetsLost` and `assetsUnimpaired` need not match. The impaired estimate and the confirmed loss can legitimately differ.

**Example.** `deployedAssetsOf[wallet] = 1,250,000` and `impairedAssets = 900,333`. `recognizeLossAndRemoveImpairment(165,000, 50,000, wallet)` leaves `deployedAssetsOf[wallet]` and `totalDeployedAssets` at `1,085,000` and `impairedAssets` at `850,333`.

## Recovering written-off assets

There is no on-chain undo for `recognizeLoss()`. Recovered capital can re-enter in one of two ways:

1. **`realizeYield()`.** The strategy treats the recovery as cash-basis yield. It pays Strategy Delegate and protocol fees on it and vests it through the yield buffer like any other yield. See [Accounting and Fees](accounting-and-fees.md).
2. **Direct distribution to affected Lenders.** The Lenders holding shares when the loss was recognized, and their share of it, can be reconstructed off-chain and paid directly, bypassing the strategy and its fees.

## Complete loss

If losses take `assetsUnderManagement()` to zero while the Strategy Manager still has shares outstanding, the Strategy Manager's `fundStrategyManager()` reverts for that strategy. Its share conversion computes `assets * totalShares / totalAssets`, and a zero `totalAssets` with non-zero `totalShares` divides by zero. Funding works again as soon as `assetsUnderManagement()` is non-zero, for example after a `realizeYield()` call.
