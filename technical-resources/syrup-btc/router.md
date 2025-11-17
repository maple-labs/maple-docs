# SyrupBitcoinRouter

The SyrupBitcoinRouter is the integration point for BTC deposits and redemptions. It wraps supported Bitcoin assets into the Pool asset for deposits and unwinds redemptions after the Withdrawal Manager has processed queued requests. It is intended to be the sole public entrypoint for all SyrupBTC interactions.

Core responsibilities
- Deposit Bitcoin assets and mint Pool shares to the user
- Request redemptions and lock shares into the Withdrawal Manager
- Batch process redemption requests after the Withdrawal Manager updates the queue
- Remove or adjust pending requests on behalf of the user when permitted

Key functions
- `deposit(assetIn, amountIn, metadata, permit)` deposits a supported BTC asset and returns Pool shares to the user
- `requestRedeem(assetOut, shareAmount, metadata, permit)` locks shares for redemption into the queue
- `processRedemptions(requestIds[])` processes a batch of already processed queue entries and transfers BTC assets to users
- `removeRequests(owner, requestIds[])` removes all unprocessed shares from a set of requests
- `removeSharesById(requestId, sharesToRemove)` adjusts a single request owned by the caller
- `setFees(asset, mintFee, redemptionFee)` sets protocol fee rates for a specific deposit asset and is protocol admin gated

Events
- `Deposit` records deposits and minted shares
- `RequestRedeem` records new redemption requests
- `RedemptionProcessed` records per request settlement amounts
- `FeesSet` records fee schedule changes

Ordering and FIFO
- The Withdrawal Manager queue is strictly FIFO for request processing
- The router can process any set of requestIds that the Withdrawal Manager has already marked as processed
- Operationally we process with FIFO order at the router as well to maintain user expectations

Interfaces
- Contract interfaces are documented in `technical-resources/interfaces/syrup-bitcoin-router.md`

