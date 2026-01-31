# Failed Message Retry and Recovery

This guide explains how to identify failed crosschain messages and use MapleCCIPReceiver's retry and recovery flows. It also shows how to check message status in the Chainlink CCIP Explorer.

## Prerequisites and permissions

- `recoverFailedTokensBackToSender(messageId)` is permissionless and **payable**. Anyone can call it, but the caller must fund CCIP fees.
- `retryFailedMessage(messageId)` is permissionless and **payable**, but it does **not** use `msg.value`; it relies on the contract’s native balance to pay CCIP fees during message processing.
- `adminRescueTokens(messageId, beneficiary)` is **admin-only** and is intended as a last resort if normal recovery fails.

Both retry and recovery require the message to exist in storage and be in `FAILED` state. If the message is missing or already resolved, the call reverts.

## Finding the messageId

You can get the `messageId` from MapleCCIPReceiver event logs on the pool chain:

- `MessageReceived` emits the inbound CCIP messageId.
- `MessageFailed` emits the messageId when processing fails.
- `MessageSent` emits the messageId for outbound return transfers (shares or assets).

If you only have a transaction hash, you can search for the transaction in the CCIP Explorer or Block explorer (eg. Etherscan) and copy the messageId from the Explorer details.

## Check status in the Chainlink CCIP Explorer

The CCIP Explorer tracks crosschain messages and supports searching by message ID.

Steps:

1. Open the CCIP Explorer.
2. Paste the `messageId` into the search field.
3. Review the message status and associated source and destination transactions.

This is useful to confirm whether the CCIP transfer has been executed on the destination chain or is still pending.

## Retry delivery in the CCIP Explorer (manual execution)

If a CCIP message reaches the destination chain but execution fails (for example, due to an insufficient gas limit), Chainlink supports **manual execution** through the CCIP Explorer. This lets you override the gas limit and retry execution from the Explorer UI. The Chainlink docs describe this as “manual execution” and show the flow using the CCIP Explorer.

Use this when the Explorer indicates the message is ready for manual execution or shows a failed execution on the destination chain. For details and prerequisites, follow Chainlink’s manual execution guide https://docs.chain.link/ccip/concepts/manual-execution .

## Retry vs. recover

MapleCCIPReceiver stores failed messages and exposes two user-facing paths:

### 1) Retry processing (re-run the original logic)

Use `retryFailedMessage(messageId)` when you want the original message to be processed again.

- The function replays the original message logic.
- Fees are paid by the contract's **native balance** (not `msg.value`).
- Emits `MessageRecovered` if processing succeeds.
- If the retry still fails, the transaction reverts and the message remains in `FAILED` state.

### 2) Recover tokens back to sender

Use `recoverFailedTokensBackToSender(messageId)` to return tokens to the original sender if retry fails or is not appropriate.

- The function attempts a retry first. If the retry fails, it sends the tokens back to the sender using CCIP.
- The caller must provide enough native tokens to cover CCIP fees (`msg.value >= fees`).
- Use `estimateRecoveryFee(messageId)` to estimate the fee in native units.
- Any excess `msg.value` is refunded to the caller.
- Emits `TokensRecovered` and a `MessageSent` for the recovery transfer.

## Funding considerations

- **Retry path**: The contract must hold enough native tokens to pay CCIP fees for any outbound sends triggered during retry (for example, sending shares back after a deposit). If the contract balance is insufficient, the retry will revert with `NotEnoughBalance`.
- **Recovery path**: The caller pays fees for the return transfer. The contract approves the router for the failed message’s tokens and uses CCIP to send them back.

## Viewing failed message state on-chain

- `getFailedMessages(offset, limit)` returns failed message IDs and status.
- `getMessage(messageId)` returns the stored `Any2EVMMessage` content.
- A message can be in `FAILED` or `RESOLVED` state in the receiver's storage.

Notes:
- `getFailedMessages` only returns items still marked `FAILED` (resolved messages are filtered out).
- `getMessage` returns the full stored message, including sender and token payloads, which is used for recovery.
