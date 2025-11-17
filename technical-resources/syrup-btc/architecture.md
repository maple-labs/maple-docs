# Architecture and Flows

## Overview

SyrupBTC extends Maple Pools with Bitcoin asset support using a controller and router layer. Users deposit supported Bitcoin assets through the SyrupBitcoinRouter which interacts with an Asset Controller to wrap BTC assets into the Pool asset and mint Pool shares. Redemptions use the queue Withdrawal Manager and are orchestrated by the router for a smooth user experience.

Key components
- SyrupBitcoinRouter manages user deposits and redemptions and batches processing of redeem requests
- Asset Controller maintains accounting between deposit assets and the Pool asset and routes assets to strategies
- MapleBitcoinStrategy manages schedule based yield for BTC exposure
- Pool and Withdrawal Manager (Queue) provide the ERC‑4626 share accounting and FIFO exit queue

High level properties
- BTC deposit and redemption through a single router entry point
- FIFO fairness from the Withdrawal Manager while allowing the router to orchestrate batch processing
- Clear separation of concerns between user integration, asset routing, and strategy management

Related docs
- Router details in `technical-resources/syrup-btc/router.md`
- Controller details in `technical-resources/syrup-btc/controller.md`
- Invariants in `technical-resources/syrup-btc/invariants.md`
- Bitcoin Strategy in `technical-resources/strategies/bitcoin-strategy.md`

Deposit flow
1) User calls SyrupBitcoinRouter.deposit(assetIn, amountIn, metadata, permit)
2) Router pulls tokens using permit if provided and interacts with the Asset Controller to wrap the BTC asset
3) Asset Controller mints Pool assets to the router which deposits into the Pool to mint shares to the user
4) Router emits a Deposit event with amounts and metadata

Redemption flow
1) User calls Pool.requestRedeem or Router.requestRedeem to lock shares in the Withdrawal Manager queue
2) Pool Delegate or operational admin processes the queue in FIFO using `processRedemptions` and `processEmptyRedemptions` on the Withdrawal Manager
3) Router picks up processed requests and unwraps Pool assets back to the chosen BTC asset then transfers to the user

Ordering guarantees
- The Withdrawal Manager enforces FIFO ordering of queued requests
- The router can process already processed requests in any order after the Withdrawal Manager updates the queue state
- Operationally we process router tasks in FIFO for fairness and predictability

Roles and permissions
- Only redeemer roles can process Withdrawal Manager batches
- Router batching functions are permissioned per contract and environment to prevent abuse
