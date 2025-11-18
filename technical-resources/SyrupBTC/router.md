# SyrupBitcoinRouter

## Overview

The SyrupBitcoinRouter is the sole entry point for SyrupBTC deposits and redemptions. It wraps supported wrapped Bitcoin assets (wBTC) into the pool asset on deposit, manages Withdrawal Manager queue interactions for redemption requests, and unwraps pool assets back into wBTC once the queue has processed a request. Integrators should only interact with the router—the Pool, Asset Controller, and Withdrawal Manager are permissioned behind it.

## Deposit Lifecycle

1. **User call**: `deposit(assetIn, amountIn, metadata, permit)` is invoked with a supported wBTC asset. `Permit` is optional and allows ERC-20/EIP-2612 approvals to be included.
2. **Permit and transfer**: If `permit.enabled` is true the router executes the permit before pulling tokens. The router then `transferFrom`s `amountIn` of `assetIn` from the caller.
3. **Wrap**: Router calls `AssetController.wrap(assetIn, amountIn)` to lock the wBTC and receive pool assets. Mint fees are applied per-asset if configured.
4. **Mint shares**: Router deposits pool assets into the Pool and mints shares to the recipient (caller by default). A `Deposit` event emits the asset, amount, and metadata blob for downstream indexers.

Deposits always settle immediately. All assets flow through the router, enabling consistent fee behavior and metadata logging.

## Requesting Redemptions

Redemptions are split into a **queueing** phase handled by the Withdrawal Manager and a **settlement** phase handled by the router.

1. **Lock shares**: User calls `requestRedeem(assetOut, shareAmount, metadata, permit)`. Shares are transferred from the user (permit optional) and locked in the Withdrawal Manager queue through the Pool.
2. **Request metadata**: Router records the `assetOut`, owner, and metadata in its own mappings keyed by the returned `requestId`. A `RequestRedeem` event is emitted with all relevant data.
3. **Queue semantics**: The Withdrawal Manager enforces FIFO. Users can submit multiple requests, decrease them, or have an admin remove them if needed. See `technical-resources/withdrawal-managers/withdrawal-manager-queue.md` for queue internals.

## Processing Redemptions

Once the Withdrawal Manager processes the shares, requests become eligible for settlement:

1. **Batch selection**: Authorized callers call `processRedemptions(requestIds[])` with IDs whose underlying queue entries have been processed. The router can settle in any order, but operationally follows FIFO for fairness.
2. **Unwrap and fee**: For each request the router unwraps pool assets back into the requested wBTC asset via `AssetController.unwrap`. Redemption fees (per-asset) are applied before forwarding assets to the requester.
3. **Transfer**: wBTC is sent to the original requester. The router emits `RedemptionProcessed` with the request ID, asset, amounts, and fees. Requests are then cleared from storage.

## Adjusting or Cancelling Requests

- **User initiated**: `removeSharesById(requestId, sharesToRemove)` allows the owner to decrease a pending request before it is processed. Removing the full amount cancels the request. Returned shares go back to the owner.
- **Admin initiated**: `removeRequests(owner, requestIds[])` lets a Pool Delegate or protocol admin remove abusive or stuck requests. This is a safeguard against griefing or blacklisted addresses.

All request modifications respect the Withdrawal Manager queue ordering, decreasing a request does not change its position.

## Fees

Governance configures per-asset mint and redemption fees via `setFees(asset, mintFee, redemptionFee)` (scaled by 1e6). The router multiplies the fee rate by the asset amount to compute protocol fees, forwarding them to Maple Treasury addresses defined in MapleGlobals.

## Roles and Permissions

| Role | Permissions |
| --- | --- |
| Unprivileged user | `deposit`, `requestRedeem`, `removeSharesById` |
| Pool Delegate / Operational Admin (WITHDRAWAL_REDEEMER key) | `processRedemptions`, `removeRequests`, `setFees` (if governance delegates) |
| Governor / MapleGlobals | Configure supported assets, assign router on Asset Controller, adjust fee recipients |

Permit support lets integrators bundle approval + action. For security, router entrypoints enforce `nonReentrant` guards and check MapleGlobals permissions on every call.

## Events

- `Deposit(assetIn, amountIn, sharesMinted, to, metadata)`
- `RequestRedeem(assetOut, sharesLocked, requestId, owner, metadata)`
- `RedemptionProcessed(requestId, assetOut, amountOut, feesPaid, owner)`
- `FeesSet(asset, mintFee, redemptionFee)`

Events provide complete audit trails for deposits, redemptions, and fee changes.

## Operational Notes

- **Metadata usage**: `metadata` (bytes32) can encode integrator IDs, off-chain references, or analytics tags. It is emitted in every event and stored on-chain for future processing.
- **Supported assets**: Only wBTC variants whitelisted via MapleGlobals may be deposited. Attempting to deposit or redeem unsupported assets will revert.
- **Automation**: Typical flows run `WithdrawalManager.processRedemptions` (queue) → `WithdrawalManager.processEmptyRedemptions` → `SyrupBitcoinRouter.processRedemptions`. The last step may be run multiple times to cover the batch.

## Interfaces

For full ABI details refer to `technical-resources/interfaces/syrup-bitcoin-router.md`.

