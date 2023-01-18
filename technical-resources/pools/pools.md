# Overview

The Pool contract is the core unit that keeps tracks of liquidity provider shares and funds, including token transfer capabilities. It's the only necessary contract for depositors to interact with and it contains all necessary functions to enter and exit positions. It is an immutable contract that contains the minimum necessary logic to allow for a high degree of flexibility in future development of the protocol.

The pool contract is an implementation of a Tokenized Vault Standard ([ERC-4626](https://erc4626.info/)), implementing the full interface defined in the [specification](https://eips.ethereum.org/EIPS/eip-4626).

# Permits

As a convenience, Pools implements the `depositWithPermit` and `mintWithPermit` that allows users to deposit performing a single transaction and not needing to approve tokens beforehand. This is an extension of the current ERC-4626 vault standard.

# Maple Specific Behaviors

Although Pools were built to be maximally compliant with the tokenized vault standard, a few behavioral exceptions were necessary to adhere to Maple's use case, which is undercollateralized loans.

# Withdrawals

Exiting the pool by **calling `withdraw` is NOT encouraged**, as the recommended method to exit is through `redeem`. This is due to the accruing mechanism used along with the fact that the current WithdrawalManager implementation enforces that the full **share** amount withdrawn must match the amount requested for withdrawal. Since the value of the LP tokens accrues every block, the number of shares that corresponds to the withdrawal amount is continuously decreasing and will result in a different value depending on when the block is mined. It is therefore encouraged that users exit by calling `redeem` with the number of shares that they would like to exit with.

# Redeem

Due to the fact that the Maple protocol functions on partial liquidity (a capital efficient Pool will have outstanding loans and partial liquidity to fulfill withdrawals), withdrawal "cooldowns" are used to effectively and fairly manage liquidity. In order to exit from a Pool, an LP must first call `requestRedeem` before they can call `redeem`. This function moves the LP's shares to another contract and subjects them to the specific withdrawal mechanic. More details on the current WithdrawalManager mechanism are included [here](./withdrawal-manager.md).

Once the conditions contained in the WithdrawalManager are met, the users can call `redeem` and burn their LP shares for cash.

**NOTE:** View functions, like `maxRedeem`, `maxWithdraw`, `previewRedeem` and `previewWithdraw`, returns values compliant to the withdrawal mechanism, meaning if that a given user is not allowed to redeem at the current time, it'll return `0`. If the user is able to redeem, it'll return the redeemable amount.

# Removing Shares

This function can be used if a `requestRedeem` was previously called, but the users wants to cancel the request and get their shares back. Note that this function is also subjected to the specific withdrawal logic defined in the WithdrawalManager in use.
