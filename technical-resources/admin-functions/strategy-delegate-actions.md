# Strategy Delegate

A Strategy Delegate owns exactly one Strategy Manager and the Underlying Strategy behind it. Globals records the binding in `strategyDelegates`, the Strategy Manager stores the address as `strategyDelegate`, and the strategy reads it live through `strategyManager.strategyDelegate()`. The role is trusted in the same way a Pool Delegate is. See [Strategy Manager](../strategies/strategy-manager.md).

## Lifecycle

1. The Governor or Operational Admin approves the address with `setValidStrategyDelegate`.
2. The Strategy Delegate calls `MapleStrategyDeployer.deploy()`, which requires `isStrategyDelegate(msg.sender)` and pulls the bootstrap deposit from the caller.
3. The Governor or Operational Admin calls `activateStrategyManager`. Funding is rejected until then.
4. To hand over, the Operational Admin calls `setPendingStrategyDelegate` and the new delegate calls `acceptStrategyDelegate`. The outgoing delegate does not sign anything.

A Strategy Delegate cannot be revoked while it still owns a Strategy Manager.

## Strategy Manager

The Strategy Delegate is always an Operator, even while the Underlying Strategy reports impaired assets. See [The impairment block](liquidity-bot-actions.md#the-impairment-block).

* `fundStrategyManager` (Operator)
* `requestRedeem`, `cancelRedemption` (Operator, or the Pool Delegate of the named Pool Manager)
* `processRedemption` (Operator or Operational Admin)
* `setPoolManagerCap`, `setStrategyLiquidityCap` (shared with the Operational Admin)
* `acceptStrategyDelegate` (pending Strategy Delegate only)
* `multicall` (open to anyone, each inner call re-checks the original caller)

The Strategy Delegate cannot call `upgrade`, `setPendingStrategyDelegate` or `setActive`, and cannot set `strategyCapOf` on a Pool Manager. That cap belongs to the Pool Delegate.

## Underlying Strategies

Alone:

* `setStrategyDelegateFeeRate` (the sum with `strategyProtocolFeeRate` must not exceed `HUNDRED_PERCENT`)

Shared with the Operational Admin, on all three strategies:

* `impair`
* `removeImpairment`
* `recognizeLoss`
* `setMetadata`

[Aave V3 Strategy](../strategies/aave-v3-strategy/README.md), shared with the Operational Admin:

* `recoverPosition` (only after a loss is recognized)
* `claimRewards`
* `setReferralCode`

[Sky Strategy](../strategies/sky-strategy/README.md), shared with the Operational Admin:

* `recoverPosition` (only after a loss is recognized)
* `setFallbackTout`
* `setReferralCode`

On the Aave V3 and Sky strategies every function above except `claimRewards` and `recoverPosition` reverts once `recognizeLoss` has been called.

[Allocation Strategy](../strategies/allocation-strategy/README.md), shared with the Operational Admin:

* `recognizeLossAndRemoveImpairment`
* `setYieldCap`
* `skim`

Allocation Strategy, shared with the Security Admin:

* `setPermissions`
* `setDeploymentCaps`
* `cancelYield`

The Strategy Delegate cannot set `strategyProtocolFeeRate` or `useVirtualUnderlyingBalance`. Those belong to the Governor and Operational Admin.
