# Overview

The core of the SYRUP token is based on the audited and battle-tested [ERC20](https://github.com/maple-labs/erc20) contract. The existing ERC20 contract used for xSYRUP and all existing pools will serve as the foundation for MPL V2. The ERC20 contract provides the following functions:

### Public Functions

- `approve()`: Allows one account to set the allowance of another account over their tokens.
- `decreaseAllowance()`: Allows one account to decrease the allowance of another account over their tokens.
- `increaseAllowance()`: Allows one account to increase the allowance of another account over their tokens.
- `permit()`: Approve by signature.
- `transfer()`: Moves an amount of tokens from `msg.sender` to a specified account.
- `transferFrom()`: Moves a pre-approved amount of tokens from a sender to a specified account.

### Internal Functions

- `_mint()`: Creates new tokens for a given account and increases the total supply.
- `_burn()`: Removes tokens from an account and decreases the total supply.

### Additional Rules
At construction time, the SYRUP should do a one time mint of 10% of the supply directly to the treasury. Additionally 10 Million SYRUP will be minted to the migrator contract to facilitate a 1-1 swap from MPL V1 to SYRUP.
