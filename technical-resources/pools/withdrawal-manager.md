# Withdrawal Manager

The queue-based `MapleWithdrawalManager` handles exits from a Pool. Lenders submit redemption requests, the contract escrows their shares in a FIFO queue, and when a request is processed it exchanges the shares for assets at the current exit rate and sends them to the owner. v7 ships v2.0.1, whose only functional change is a permission check on `removeSharesById`. Storage is unchanged, so the upgrade is an implementation swap with no migrator. Full interface: [WithdrawalManagerQueue](../interfaces/withdrawal-manager-queue.md).

### Withdrawal Request

Any user holding shares can perform a withdrawal request.

* Each withdrawal request has a unique identifier assigned to it.
* A user may have multiple active withdrawal requests at the same time. Requests are tracked per user and can be adjusted or removed by id.
* When making the request the user specifies the amount of shares that should be redeemed and that amount of shares is then transferred to the withdrawal manager where it remains in custody.
* Once the withdrawal is processed the request is deleted and the user can again make another one.
* The user can also adjust an existing withdrawal request, but only in a downwards manner (by returning some of the shares locked).
* Additionally, the pool delegate or protocol admins also have the ability to remove any withdrawal request from the queue. This is primarily for the sake of preventing abuse of the withdrawal mechanism.

_NOTE_: Withdrawal requests can only be submitted in the form of redemption requests (indicating the number of shares to redeem), `requestWithdraw()` and `withdraw()` functions are disabled.

### Withdrawal Queue (FIFO)

The withdrawal queue contains all pending withdrawal requests and maintains their ordering from first to last. Whenever the pool delegate or protocol admins process withdrawal requests, they are processed in that order (**FIFO**). This means earlier requests are processed before later requests. If there is insufficient liquidity to process all requests, only the earliest requests are processed. The remainder stay in the queue to be processed later.

### Request Processing

The pool delegate or any of the protocol admins can at any time process any amount of shares that are pending redemption. The amount of shares to be processed is specified in advance, and as many redemption requests as possible will be processed using that amount of shares. The requests are processed based on their position in the queue (first to last), and using the current exchange rate.

_NOTE_: The `processRedemptions()` function has a reentrancy guard since it performs external calls.

_NOTE_: The amount of shares must be specified and are assumed to be a reasonable amount where out of gas issues don't occur.

### Exchange Rate

When a withdrawal request is processed, the amount of assets withdrawn is calculated by converting the requested shares into assets using the current exchange rate. This means that the exchange rate for different users' withdrawal requests may vary depending on when the requests are processed. If any loan or strategy is impaired, `unrealizedLosses` lowers the value of each share until the impairment is removed or the loss is realised. A request processed while an impairment is open therefore receives fewer assets than one processed after the impairment is removed. See [Exchange Rates](exchange-rates.md).

The formula for calculating the exchange rate of shares to assets is defined as:

`exchangeRate = (totalAssets - unrealizedLosses) / totalSupply`

### Partial Redemptions

If there is insufficient liquidity available during the processing of a request, it will be processed partially (_note this is only applicable to the last request being processed in the queue_). This means that only a portion of the shares from the original withdrawal request will be redeemed. The remainder will retain their original position in the queue and may be processed again at any time. The formula for calculating the number of shares that can be redeemed is defined as follows:

`redeemableShares(user) = min(lockedShares(user), lockedShares(user) * availableAssets / requiredAssets)`

### Adjust or Cancel a Request (removeSharesById)

The request owner can reduce or cancel a specific pending request at any time before it is processed by calling `removeSharesById(requestId, sharesToRemove)`. The checks run in this order:

1. The request exists (`WM:RSBI:INVALID_REQUEST`).
2. The caller owns it (`WM:RSBI:NOT_OWNER`).
3. `sharesToRemove` is non-zero and no more than the request's shares.
4. The caller holds the `WM:removeSharesById` permission for this Pool in the Pool Permission Manager (`WM:RSBI:NOT_ALLOWED`). This check is new in v2.0.1. It brings `removeSharesById` in line with `removeShares`, which the Pool already checks against `P:removeShares`, so both ways of cancelling a request can be paused for a Pool. The check passes on a public Pool, for a Lender on the Pool's allowlist, and whenever no bitmap is configured for this function id.

- If `sharesToRemove` equals the current request shares, the request is cancelled. Otherwise the request is decreased and remains in the queue with the original position.
- Returns `(sharesReturned, sharesRemaining)` and transfers the returned LP shares back to the owner.
- Use `requests(requestId)` or `requestsByOwner(owner)` to inspect pending requests and shares.

### Manual Requests (2 step process)

Each withdrawal request can be processed automatically (by default) or manually by calling `requestRedeem()` first then calling `redeem()`. The pool delegate or any protocol admin can enable manual requests for users who want to opt-out of automatic processing. The difference between automatic and manual requests is as follows:

* Automatic requests will be immediately redeemed on processing.
* Manual requests will be redeemed any time after processing (when the `redeem()` function is actually called). Manual withdrawal requests are primarily supported so that the protocol remains ERC-4626 compatible (**internal use only**). Automatic requests are the default and preferred way of handling withdrawals.

### Roles & Permissions

| Function | Allowed callers |
| --- | --- |
| `addShares`, `processExit`, `removeShares` | Pool Manager |
| `processRedemptions`, `processEmptyRedemptions`, `removeRequest` | A `WITHDRAWAL_REDEEMER` instance, the Pool Delegate or the Operational Admin |
| `setManualWithdrawal` | Pool Delegate or Operational Admin |
| `removeSharesById` | The request owner, with the `WM:removeSharesById` permission |
| `upgrade` | Pool Delegate through a scheduled call, or the Security Admin |

### Events & Queue Internals

- Events: `RequestCreated`, `RequestDecreased`, `RequestRemoved`, `RequestProcessed`, `ManualWithdrawalSet`, `EmptyRedemptionsProcessed`, `ManualSharesIncreased`, `ManualSharesDecreased`.
- Queue pointers: `nextRequestId` and `lastRequestId` track processing range. `processEmptyRedemptions(n)` advances `nextRequestId` over empty entries to keep processing efficient.

### Legacy Functions

For the sake of backwards compatibility with the `PoolManager`, certain functions used in the previous version of the withdrawal manager have been retained. These are as follows:

* `lockedShares()`: returns the amount of `manualSharesAvailable` (only used for manual withdrawals).
* `lockedLiquidity()`: returns zero. The v7 Pool Manager no longer reads it, because `requestFunds` enforces strategy caps instead of locked liquidity.
* `isInExitWindow()`: returns `true`, since there are no more withdrawal windows and withdrawals can be processed at any time.

### Key Assumptions

Generally a push pattern for token transfers is not recommended as it can lead to uncontrolled revert conditions. In the case of the `WithdrawalManager` this could mean issues such as the queue being blocked. This is a known issue and to address this we have added the `removeRequest()` function that can be called by the pool delegate or protocol admin to unblock the queue. Additionally:

* No tokens with callbacks will be used.
* This queue based withdrawal manager will only be used in permissioned pools, not public pools to avoid denial of service attacks.
* Extensive research will be done when onboarding new ERC20 tokens as the underlying asset.
* An LP being blacklisted by USDC/USDT is a low likelihood event due to the KYC'd nature of LPs in permissioned pools and the use of `removeRequest()` can address this issue.

To highlight the key reason to support this push pattern is to address the business need from LPs.

### Invariants

```
* Withdrawal Manager (Queue)
    * Invariant A: ∑request.shares + ∑owner.manualShares == totalShares
    * Invariant B: balanceOf(this) >= totalShares
    * Invariant C: ∀ requestId(owner) != 0 -> request.shares > 0 && request.owner == owner
    * Invariant D: nextRequestId <= lastRequestId + 1
    * Invariant E: nextRequestId != 0
    * Invariant F: requests(0) == (0, 0)
    * Invariant G: ∀ requestId[lender] ∈ [0, lastRequestId]
    * Invariant H: requestId is unique
```
