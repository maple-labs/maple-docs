# Pool

The Pool contract is the core unit that keeps tracks of liquidity provider shares and funds, including token transfer capabilities. It's the only necessary contract for Lenders to interact with and it contains all necessary functions to enter and exit positions. It is an immutable contract that contains the minimum necessary logic to allow for a high degree of flexibility in future development of the protocol. The November 2026 release changes only the compiler version of `MaplePool`, its behaviour is unchanged. Full interface: [Pool](../interfaces/pool.md).

The pool contract is an implementation of a Tokenized Vault Standard ([ERC-4626](https://erc4626.info/)), implementing the full interface defined in the [specification](https://eips.ethereum.org/EIPS/eip-4626).

### Call Checks & Permissions

The Pool checks deposits, exits and transfers through a `checkCall` modifier that calls `PoolManager.canCall(functionId, caller, args)`. `canCall` asks the `PoolPermissionManager` whether one or two addresses hold the permission for the function id, and its config (allowlist/bitmaps/levels) decides the answer. The checked address depends on the function:

* `P:deposit`, `P:depositWithPermit`, `P:mint`, `P:mintWithPermit`: the receiver.
* `P:redeem`, `P:requestRedeem`, `P:removeShares`: the owner of the shares.
* `P:transfer`, `P:transferFrom`: the account sending the shares and the recipient.

`approve`, `increaseAllowance`, `decreaseAllowance` and `permit` do not run `checkCall`.

## Permits

As a convenience, Pools implements the `depositWithPermit` and `mintWithPermit` that allows users to deposit performing a single transaction and not needing to approve tokens beforehand. This is an extension of the current ERC-4626 vault standard.

## Maple Specific Behaviors

Although Pools were built to be maximally compliant with the tokenized vault standard, a few behavioral exceptions were necessary to adhere to Maple's use case.

## Withdrawals

`withdraw` and `requestWithdraw` always revert. The Pool Manager rejects them with `PM:PW:NOT_ENABLED` and `PM:RW:NOT_ENABLED`. Lenders exit by calling `requestRedeem` with the number of shares they would like to exit with, and the Withdrawal Manager then processes the redemption.

## Redeem

In order to exit from a Pool, an LP calls `requestRedeem`. This function moves the LP's shares to another contract and subjects them to the specific withdrawal mechanism. More details on the current WithdrawalManager mechanism are included [here](withdrawal-manager.md).

When the WithdrawalManager processes the request, it redeems the shares and sends the funds asset directly to the user. A user set to manual withdrawal instead calls `redeem` after processing to burn their LP shares for cash.

**NOTE:** View functions, like `maxRedeem`, `maxWithdraw`, `previewRedeem` and `previewWithdraw`, returns values compliant to the withdrawal mechanism, meaning if that a given user is not allowed to redeem at the current time, it'll return `0`. If the user is able to redeem, it'll return the redeemable amount.

## Removing Shares

This function can be used if a `requestRedeem` was previously called, but the users wants to cancel the request and get their shares back. Note that this function is also subjected to the specific withdrawal logic defined in the WithdrawalManager in use.

## Bootstrap Mint

Pools may be initialized with a one-time `BOOTSTRAP_MINT` to seed supply for arithmetic stability. The first mint operation effectively receives `shares - BOOTSTRAP_MINT` and an event is emitted. This is expected and has no ongoing effect after initialization.
