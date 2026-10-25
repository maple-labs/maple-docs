# Liquidity Bots

From the contracts' point of view a bot is an address registered in [Maple Globals](../singletons/globals.md) under an instance key. The Governor or Operational Admin registers it with `setValidInstanceOf`, and every call checks the key live, so revoking a bot takes effect immediately. Three keys matter.

| Key | Where it is checked | What it allows |
|---|---|---|
| `LIQUIDITY_BOT` | Strategy Manager, in the Operator check | Fund, request, cancel and process redemptions directly |
| `LIQUIDITY_ROUTER_BOT` | Liquidity Router, in `executeActions` | Batch those same four actions across many Strategy Managers |
| `WITHDRAWAL_REDEEMER` | Withdrawal Manager, in `onlyRedeemer` | Process the LP redemption queue |

## `LIQUIDITY_BOT`: direct Strategy Manager calls

The [Strategy Manager](../strategies/strategy-manager.md) resolves an Operator on every call. The check passes for the Strategy Delegate unconditionally. For any other caller it returns false if `underlyingStrategy.impairedAssets()` is non-zero, and otherwise passes when the caller is registered as `LIQUIDITY_BOT` or `LIQUIDITY_ROUTER`.

A `LIQUIDITY_BOT` can therefore call:

* `fundStrategyManager(poolManager, assetsIn, data)`
* `requestRedeem(poolManager, shares)`
* `cancelRedemption(poolManager, shares)`
* `processRedemption(poolManager, shares, data)`

It cannot set caps, accept a delegate handover or upgrade anything.

## `LIQUIDITY_ROUTER_BOT`: calls through the Liquidity Router

The [Liquidity Router](../strategies/liquidity-router.md) is a single non-upgradeable contract that batches Strategy Manager actions. Two registrations are needed: the bot as `LIQUIDITY_ROUTER_BOT`, so it may call `executeActions(actions, deadline)`, and the Router itself as `LIQUIDITY_ROUTER`, so Strategy Managers accept the Router as an Operator.

For each action the Router checks that the deadline has not passed, that the Strategy Manager came from a registered `STRATEGY_MANAGER_FACTORY`, and then calls one of `fundStrategyManager`, `requestRedeem`, `cancelRedemption` or `processRedemption`. The Strategy Manager sees the Router as `msg.sender` and applies its own Operator and cap checks, so routing through the Router never grants more than a direct `LIQUIDITY_BOT` call would.

A bot address can hold one key or both.

## The impairment block

Once an Underlying Strategy reports `impairedAssets() != 0`, both `LIQUIDITY_BOT` and `LIQUIDITY_ROUTER` callers fail the Operator check on that Strategy Manager. Only the Strategy Delegate can fund or process redemptions until the impairment is removed. On the Aave V3 and Sky strategies `recognizeLoss` also resets `impairedAssets` to zero. On the Allocation Strategy only `removeImpairment` or `recognizeLossAndRemoveImpairment` does.

## Limits that apply to every Operator call

* `PoolManager.requestFunds` rejects funding that would push the Pool's position above `strategyCapOf[strategyManager]`, which the Pool Delegate sets.
* The Strategy Manager rejects funding that would exceed `poolManagerCapOf[poolManager]` or `strategyLiquidityCap`. A `poolManagerCap` of `type(uint256).max` blocks funding from that Pool entirely.
* `processRedemption` only settles up to the Pool's pending shares and up to `availableToWithdraw()` of the Underlying Strategy.
* The Router and every Strategy Manager carry `whenNotPaused`, so the Security Admin can stop bots with a contract or protocol pause.

## `WITHDRAWAL_REDEEMER`: the LP redemption queue

The queue [Withdrawal Manager](../pools/withdrawal-manager.md) restricts its processing functions with `onlyRedeemer`, which passes for a registered `WITHDRAWAL_REDEEMER`, the Pool Delegate or the Operational Admin:

* `processRedemptions(maxSharesToProcess)` fills requests in order and reverts with `WM:PR:LOW_LIQUIDITY` if the Pool cannot cover the full amount.
* `processEmptyRedemptions(numberOfRequests)` skips cancelled requests at the head of the queue.
* `removeRequest(owner, requestIds)` returns an owner's shares.

A `WITHDRAWAL_REDEEMER` cannot call `setManualWithdrawal` or `upgrade`.
