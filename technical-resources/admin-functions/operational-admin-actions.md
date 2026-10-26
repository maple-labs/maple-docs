# Operational Admin

The Operational Admin is the address stored as `operationalAdmin` in [Maple Globals](../singletons/globals.md). The Governor appoints and replaces it with `setOperationalAdmin`. It handles routine protocol operations without the Governor's delay, and it also onboards Strategy Delegates and shares most strategy lifecycle controls with them.

## Globals

* `activatePoolManager`
* `activateStrategyManager`
* `setBootstrapMint`
* `setCanDeployFrom`
* `setValidBorrower`
* `setValidInstanceOf` (registers factories, bots, the Liquidity Router, strategy vaults and the PSM)
* `setValidMapleManagedWallet`
* `setValidPoolDelegate`
* `setValidStrategyDelegate`
* `setPlatformManagementFeeRate`, `setPlatformOriginationFeeRate`, `setPlatformServiceFeeRate`

## Pool Manager

* `setPendingPoolDelegate` (Operational Admin only, the pending delegate then calls `acceptPoolDelegate`)
* `removeStrategyManager` (Operational Admin only, and only while the Pool's position in that Strategy Manager is zero)
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setStrategyCap`
* `setPoolPermissionManager`
* `triggerDefault`

## Withdrawal Manager

* `processRedemptions`
* `processEmptyRedemptions`
* `removeRequest`
* `setManualWithdrawal`

## Strategy Manager

* `setPendingStrategyDelegate` (Operational Admin only, the pending delegate then calls `acceptStrategyDelegate`)
* `setPoolManagerCap`
* `setStrategyLiquidityCap`
* `processRedemption`

The Operational Admin is not an Operator, so it cannot call `fundStrategyManager`, `requestRedeem` or `cancelRedemption`. See [Strategy Manager](../strategies/strategy-manager.md).

## Underlying Strategies

Shared with the Strategy Delegate unless noted. On the Aave V3 and Sky strategies every function below except `recoverPosition` and `claimRewards` reverts once a loss is recognized, and `recoverPosition` reverts until one is.

All three strategies:

* `impair`
* `removeImpairment`
* `recognizeLoss`
* `setMetadata`
* `setStrategyProtocolFeeRate` (shared with the Governor, not the Strategy Delegate)

[Aave V3 Strategy](../strategies/aave-v3-strategy/README.md):

* `recoverPosition`
* `claimRewards`
* `setReferralCode`
* `setUseVirtualUnderlyingBalance` (shared with the Governor, not the Strategy Delegate)

[Sky Strategy](../strategies/sky-strategy/README.md):

* `recoverPosition`
* `setFallbackTout`
* `setReferralCode`

[Allocation Strategy](../strategies/allocation-strategy/README.md):

* `recognizeLossAndRemoveImpairment`
* `setYieldCap`
* `skim`

## Pool Permission Manager

* `configurePool`
* `setLenderAllowlist`
* `setLenderBitmaps`
* `setPermissionAdmin`
* `setPoolBitmaps`
* `setPoolPermissionLevel`
