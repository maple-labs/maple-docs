# Architecture and Flows

## Overview

SyrupBTC extends Maple Pools with Bitcoin asset support using a controller and router layer. Users deposit supported wrapped Bitcoin assets (wBTC) through the SyrupBitcoinRouter which interacts with an Asset Controller to wrap wBTC into the Pool asset and mint Pool shares. Redemptions use the queue Withdrawal Manager and are managed by the router.

Key components
- SyrupBitcoinRouter manages user deposits and redemptions and batches processing of redeem requests
- Asset Controller maintains accounting between deposit assets and the Pool asset and routes assets to strategies
- MapleBitcoinStrategy manages schedule based yield for BTC exposure
- Pool and Withdrawal Manager (Queue) provide the ERC‑4626 share accounting and FIFO exit queue

Related docs
- Router details in `technical-resources/SyrupBTC/router.md`
- Controller details in `technical-resources/SyrupBTC/controller.md`
- Invariants in `technical-resources/SyrupBTC/invariants.md`
- Bitcoin Strategy in `technical-resources/SyrupBTC/bitcoin-strategy.md`

Deposit flow
1) User calls SyrupBitcoinRouter.deposit(assetIn, amountIn, metadata, permit) with wBTC
2) Router pulls wBTC using permit if provided and interacts with the Asset Controller to wrap the wBTC asset
3) Asset Controller mints Pool assets to the router which deposits into the Pool to mint shares to the user
4) Router emits a Deposit event with amounts and metadata

Redemption flow
1) User calls Router.requestRedeem to lock shares in the Withdrawal Manager queue
2) Authorised redeemer processes the queue in FIFO using `processRedemptions` and `processEmptyRedemptions` on the Withdrawal Manager
3) Router picks up processed requests and unwraps Pool assets back to the chosen wBTC asset then transfers to the user

Roles and permissions
- Only redeemer roles can process Withdrawal Manager batches
