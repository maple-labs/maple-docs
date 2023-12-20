# Maple Pool



<br />

## Constructor




```solidity
    constructor(
        address manager_,
        address asset_,
        address destination_,
        uint256 bootstrapMint_,
        uint256 initialSupply_,
        string name_,
        string symbol_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `manager_` | `address` | `address` |  |
| 1 | `asset_` | `address` | `address` |  |
| 2 | `destination_` | `address` | `address` |  |
| 3 | `bootstrapMint_` | `uint256` | `uint256` |  |
| 4 | `initialSupply_` | `uint256` | `uint256` |  |
| 5 | `name_` | `string` | `string` | The name of the token. |
| 6 | `symbol_` | `string` | `string` | The symbol of the token. |


<br />


## Functions

### `BOOTSTRAP_MINT`

The amount of shares that will be burned during the first deposit/mint.

```solidity
    function BOOTSTRAP_MINT()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `DOMAIN_SEPARATOR`

Returns the signature domain separator.

```solidity
    function DOMAIN_SEPARATOR()
        view
        returns (
            bytes32 domainSeparator_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `domainSeparator_` | `bytes32` | `bytes32` | The signature domain separator. |


<br />

### `PERMIT_TYPEHASH`

Returns the permit type hash.

```solidity
    function PERMIT_TYPEHASH()
        view
        returns (
            bytes32
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bytes32` | `bytes32` |  |


<br />

### `allowance`

Returns the allowance that one account has given another over their tokens.

```solidity
    function allowance(
        address,
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `approve`

Function that allows one account to set the allowance of another account over their tokens.          Emits an {Approval} event.

```solidity
    function approve(
        address spender_,
        uint256 amount_
    )
        nonpayable
        returns (
            bool success_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender_` | `address` | `address` | Account that tokens are approved for. |
| 1 | `amount_` | `uint256` | `uint256` | Amount of tokens that have been approved. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `success_` | `bool` | `bool` | Boolean indicating whether the operation succeeded. |


<br />

### `asset`

The address of the underlying asset used by the Vault.          MUST be a contract that implements the ERC-20 standard.          MUST NOT revert.

```solidity
    function asset()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `balanceOf`

Returns the amount of tokens owned by a given account.

```solidity
    function balanceOf(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `balanceOfAssets`

Returns the amount of underlying assets owned by the specified account.

```solidity
    function balanceOfAssets(
        address account_
    )
        view
        returns (
            uint256 balanceOfAssets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account_` | `address` | `address` | Address of the account. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `balanceOfAssets_` | `uint256` | `uint256` |  Amount of assets owned. |


<br />

### `convertToAssets`

The amount of &#x60;assets_&#x60; the &#x60;shares_&#x60; are currently equivalent to.          MUST NOT be inclusive of any fees that are charged against assets in the Vault.          MUST NOT reflect slippage or other on-chain conditions when performing the actual exchange.          MUST NOT show any variations depending on the caller.          MUST NOT revert.

```solidity
    function convertToAssets(
        uint256 shares_
    )
        view
        returns (
            uint256 assets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to convert. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of equivalent assets. |


<br />

### `convertToExitAssets`

Returns the amount of exit assets for the input amount.

```solidity
    function convertToExitAssets(
        uint256 shares_
    )
        view
        returns (
            uint256 assets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to convert to assets. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | Amount of assets able to be exited. |


<br />

### `convertToExitShares`

Returns the amount of exit shares for the input amount.

```solidity
    function convertToExitShares(
        uint256 amount_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | Amount of shares able to be exited. |


<br />

### `convertToShares`

The amount of &#x60;shares_&#x60; the &#x60;assets_&#x60; are currently equivalent to.          MUST NOT be inclusive of any fees that are charged against assets in the Vault.          MUST NOT reflect slippage or other on-chain conditions when performing the actual exchange.          MUST NOT show any variations depending on the caller.          MUST NOT revert.

```solidity
    function convertToShares(
        uint256 assets_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets to convert. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of equivalent shares. |


<br />

### `decimals`

Returns the decimal precision used by the token.

```solidity
    function decimals()
        view
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` |  |


<br />

### `decreaseAllowance`

Function that allows one account to decrease the allowance of another account over their tokens.          Emits an {Approval} event.

```solidity
    function decreaseAllowance(
        address spender_,
        uint256 subtractedAmount_
    )
        nonpayable
        returns (
            bool success_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender_` | `address` | `address` | Account that tokens are approved for. |
| 1 | `subtractedAmount_` | `uint256` | `uint256` | Amount to decrease approval by. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `success_` | `bool` | `bool` |          Boolean indicating whether the operation succeeded. |


<br />

### `deposit`

Mints &#x60;shares_&#x60; to &#x60;receiver_&#x60; by depositing &#x60;assets_&#x60; into the Vault.          MUST emit the {Deposit} event.          MUST revert if all of the assets cannot be deposited (due to insufficient approval, deposit limits, slippage, etc).

```solidity
    function deposit(
        uint256 assets_,
        address receiver_
    )
        nonpayable
        returns (
            uint256 shares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets to deposit. |
| 1 | `receiver_` | `address` | `address` | The receiver of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` |   The amount of shares minted. |


<br />

### `depositWithPermit`

Does a ERC4626 &#x60;deposit&#x60; with a ERC-2612 &#x60;permit&#x60;.

```solidity
    function depositWithPermit(
        uint256 assets_,
        address receiver_,
        uint256 deadline_,
        uint8 v_,
        bytes32 r_,
        bytes32 s_
    )
        nonpayable
        returns (
            uint256 shares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of &#x60;asset&#x60; to deposit. |
| 1 | `receiver_` | `address` | `address` | The receiver of the shares. |
| 2 | `deadline_` | `uint256` | `uint256` | The timestamp after which the &#x60;permit&#x60; signature is no longer valid. |
| 3 | `v_` | `uint8` | `uint8` | ECDSA signature v component. |
| 4 | `r_` | `bytes32` | `bytes32` | ECDSA signature r component. |
| 5 | `s_` | `bytes32` | `bytes32` | ECDSA signature s component. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` |   The amount of shares minted. |


<br />

### `increaseAllowance`

Function that allows one account to increase the allowance of another account over their tokens.          Emits an {Approval} event.

```solidity
    function increaseAllowance(
        address spender_,
        uint256 addedAmount_
    )
        nonpayable
        returns (
            bool success_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender_` | `address` | `address` | Account that tokens are approved for. |
| 1 | `addedAmount_` | `uint256` | `uint256` | Amount to increase approval by. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `success_` | `bool` | `bool` |     Boolean indicating whether the operation succeeded. |


<br />

### `manager`

The address of the account that is allowed to update the vesting schedule.

```solidity
    function manager()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `maxDeposit`

Maximum amount of &#x60;assets_&#x60; that can be deposited on behalf of the &#x60;receiver_&#x60; through a &#x60;deposit&#x60; call.          MUST return a limited value if the receiver is subject to any limits, or the maximum value otherwise.          MUST NOT revert.

```solidity
    function maxDeposit(
        address receiver_
    )
        view
        returns (
            uint256 maxAssets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `receiver_` | `address` | `address` | The receiver of the assets. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxAssets_` | `uint256` | `uint256` |   The maximum amount of assets that can be deposited. |


<br />

### `maxMint`

Maximum amount of &#x60;shares_&#x60; that can be minted on behalf of the &#x60;receiver_&#x60; through a &#x60;mint&#x60; call.          MUST return a limited value if the receiver is subject to any limits, or the maximum value otherwise.          MUST NOT revert.

```solidity
    function maxMint(
        address receiver_
    )
        view
        returns (
            uint256 maxShares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `receiver_` | `address` | `address` | The receiver of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxShares_` | `uint256` | `uint256` |   The maximum amount of shares that can be minted. |


<br />

### `maxRedeem`

Maximum amount of &#x60;shares_&#x60; that can be redeemed from the &#x60;owner_&#x60; through a &#x60;redeem&#x60; call.          MUST return a limited value if the owner is subject to any limits, or the total amount of owned shares otherwise.          MUST NOT revert.

```solidity
    function maxRedeem(
        address owner_
    )
        view
        returns (
            uint256 maxShares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxShares_` | `uint256` | `uint256` | The maximum amount of shares that can be redeemed. |


<br />

### `maxWithdraw`

Maximum amount of &#x60;assets_&#x60; that can be withdrawn from the &#x60;owner_&#x60; through a &#x60;withdraw&#x60; call.          MUST return a limited value if the owner is subject to any limits, or the total amount of owned assets otherwise.          MUST NOT revert.

```solidity
    function maxWithdraw(
        address owner_
    )
        view
        returns (
            uint256 maxAssets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of the assets. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxAssets_` | `uint256` | `uint256` | The maximum amount of assets that can be withdrawn. |


<br />

### `mint`

Mints &#x60;shares_&#x60; to &#x60;receiver_&#x60; by depositing &#x60;assets_&#x60; into the Vault.          MUST emit the {Deposit} event.          MUST revert if all of shares cannot be minted (due to insufficient approval, deposit limits, slippage, etc).

```solidity
    function mint(
        uint256 shares_,
        address receiver_
    )
        nonpayable
        returns (
            uint256 assets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to mint. |
| 1 | `receiver_` | `address` | `address` | The receiver of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` |   The amount of assets deposited. |


<br />

### `mintWithPermit`

Does a ERC4626 &#x60;mint&#x60; with a ERC-2612 &#x60;permit&#x60;.

```solidity
    function mintWithPermit(
        uint256 shares_,
        address receiver_,
        uint256 maxAssets_,
        uint256 deadline_,
        uint8 v_,
        bytes32 r_,
        bytes32 s_
    )
        nonpayable
        returns (
            uint256 assets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of &#x60;shares&#x60; to mint. |
| 1 | `receiver_` | `address` | `address` | The receiver of the shares. |
| 2 | `maxAssets_` | `uint256` | `uint256` | The maximum amount of assets that can be taken, as per the permit. |
| 3 | `deadline_` | `uint256` | `uint256` | The timestamp after which the &#x60;permit&#x60; signature is no longer valid. |
| 4 | `v_` | `uint8` | `uint8` | ECDSA signature v component. |
| 5 | `r_` | `bytes32` | `bytes32` | ECDSA signature r component. |
| 6 | `s_` | `bytes32` | `bytes32` | ECDSA signature s component. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` |    The amount of shares deposited. |


<br />

### `name`

Returns the name of the token.

```solidity
    function name()
        view
        returns (
            string
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` |  |


<br />

### `nonces`

Returns the nonce for the given owner.

```solidity
    function nonces(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `permit`

Approve by signature.

```solidity
    function permit(
        address owner_,
        address spender_,
        uint256 amount_,
        uint256 deadline_,
        uint8 v_,
        bytes32 r_,
        bytes32 s_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | Owner address that signed the permit. |
| 1 | `spender_` | `address` | `address` | Spender of the permit. |
| 2 | `amount_` | `uint256` | `uint256` | Permit approval spend limit. |
| 3 | `deadline_` | `uint256` | `uint256` | Deadline after which the permit is invalid. |
| 4 | `v_` | `uint8` | `uint8` | ECDSA signature v component. |
| 5 | `r_` | `bytes32` | `bytes32` | ECDSA signature r component. |
| 6 | `s_` | `bytes32` | `bytes32` | ECDSA signature s component. |


<br />

### `previewDeposit`

Allows an on-chain or off-chain user to simulate the effects of their deposit at the current block, given current on-chain conditions.          MUST return as close to and no more than the exact amount of shares that would be minted in a &#x60;deposit&#x60; call in the same transaction.          MUST NOT account for deposit limits like those returned from &#x60;maxDeposit&#x60; and should always act as though the deposit would be accepted.

```solidity
    function previewDeposit(
        uint256 assets_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets to deposit. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares that would be minted. |


<br />

### `previewMint`

Allows an on-chain or off-chain user to simulate the effects of their mint at the current block, given current on-chain conditions.          MUST return as close to and no fewer than the exact amount of assets that would be deposited in a &#x60;mint&#x60; call in the same transaction.          MUST NOT account for mint limits like those returned from &#x60;maxMint&#x60; and should always act as though the minting would be accepted.

```solidity
    function previewMint(
        uint256 shares_
    )
        view
        returns (
            uint256 assets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to mint. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets that would be deposited. |


<br />

### `previewRedeem`

Allows an on-chain or off-chain user to simulate the effects of their redemption at the current block, given current on-chain conditions.          MUST return as close to and no more than the exact amount of assets that would be withdrawn in a &#x60;redeem&#x60; call in the same transaction.          MUST NOT account for redemption limits like those returned from &#x60;maxRedeem&#x60; and should always act as though the redemption would be accepted.

```solidity
    function previewRedeem(
        uint256 shares_
    )
        view
        returns (
            uint256 assets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets that would be withdrawn. |


<br />

### `previewWithdraw`

Allows an on-chain or off-chain user to simulate the effects of their withdrawal at the current block, given current on-chain conditions.          MUST return as close to and no fewer than the exact amount of shares that would be burned in a &#x60;withdraw&#x60; call in the same transaction.          MUST NOT account for withdrawal limits like those returned from &#x60;maxWithdraw&#x60; and should always act as though the withdrawal would be accepted.

```solidity
    function previewWithdraw(
        uint256 assets_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets to withdraw. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares that would be redeemed. |


<br />

### `redeem`

Burns &#x60;shares_&#x60; from &#x60;owner_&#x60; and sends &#x60;assets_&#x60; to &#x60;receiver_&#x60;.          MUST emit the {Withdraw} event.          MUST revert if all of the shares cannot be redeemed (due to insufficient shares, withdrawal limits, slippage, etc).

```solidity
    function redeem(
        uint256 shares_,
        address receiver_,
        address owner_
    )
        nonpayable
        returns (
            uint256 assets_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `receiver_` | `address` | `address` | The receiver of the assets. |
| 2 | `owner_` | `address` | `address` | The owner of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` |   The amount of assets sent to the receiver. |


<br />

### `removeShares`

Removes shares from the withdrawal mechanism, can only be called after the beginning of the withdrawal window has passed.

```solidity
    function removeShares(
        uint256 shares_,
        address owner_
    )
        nonpayable
        returns (
            uint256 sharesReturned_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `owner_` | `address` | `address` | The owner of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `sharesReturned_` | `uint256` | `uint256` | The amount of shares withdrawn. |


<br />

### `requestRedeem`

Requests a redemption of shares from the pool.

```solidity
    function requestRedeem(
        uint256 shares_,
        address owner_
    )
        nonpayable
        returns (
            uint256 escrowedShares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `owner_` | `address` | `address` | The owner of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `escrowedShares_` | `uint256` | `uint256` | The amount of shares sent to escrow. |


<br />

### `requestWithdraw`

Requests a withdrawal of assets from the pool.

```solidity
    function requestWithdraw(
        uint256 assets_,
        address owner_
    )
        nonpayable
        returns (
            uint256 escrowedShares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets to withdraw. |
| 1 | `owner_` | `address` | `address` | The owner of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `escrowedShares_` | `uint256` | `uint256` | The amount of shares sent to escrow. |


<br />

### `symbol`

Returns the symbol of the token.

```solidity
    function symbol()
        view
        returns (
            string
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` |  |


<br />

### `totalAssets`

Total amount of the underlying asset that is managed by the Vault.          SHOULD include compounding that occurs from any yields.          MUST NOT revert.

```solidity
    function totalAssets()
        view
        returns (
            uint256 totalAssets_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `totalAssets_` | `uint256` | `uint256` | The total amount of assets the Vault manages. |


<br />

### `totalSupply`

Returns the total amount of tokens in existence.

```solidity
    function totalSupply()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `transfer`

Moves an amount of tokens from &#x60;msg.sender&#x60; to a specified account.          Emits a {Transfer} event.

```solidity
    function transfer(
        address recipient_,
        uint256 amount_
    )
        nonpayable
        returns (
            bool success_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `recipient_` | `address` | `address` | Account that receives tokens. |
| 1 | `amount_` | `uint256` | `uint256` | Amount of tokens that are transferred. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `success_` | `bool` | `bool` |   Boolean indicating whether the operation succeeded. |


<br />

### `transferFrom`

Moves a pre-approved amount of tokens from a sender to a specified account.          Emits a {Transfer} event.          Emits an {Approval} event.

```solidity
    function transferFrom(
        address owner_,
        address recipient_,
        uint256 amount_
    )
        nonpayable
        returns (
            bool success_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | Account that tokens are moving from. |
| 1 | `recipient_` | `address` | `address` | Account that receives tokens. |
| 2 | `amount_` | `uint256` | `uint256` | Amount of tokens that are transferred. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `success_` | `bool` | `bool` |   Boolean indicating whether the operation succeeded. |


<br />

### `unrealizedLosses`

Returns the amount unrealized losses.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint256 unrealizedLosses_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `unrealizedLosses_` | `uint256` | `uint256` | Amount of unrealized losses. |


<br />

### `withdraw`

Burns &#x60;shares_&#x60; from &#x60;owner_&#x60; and sends &#x60;assets_&#x60; to &#x60;receiver_&#x60;.          MUST emit the {Withdraw} event.          MUST revert if all of the assets cannot be withdrawn (due to insufficient assets, withdrawal limits, slippage, etc).

```solidity
    function withdraw(
        uint256 assets_,
        address receiver_,
        address owner_
    )
        nonpayable
        returns (
            uint256 shares_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets to withdraw. |
| 1 | `receiver_` | `address` | `address` | The receiver of the assets. |
| 2 | `owner_` | `address` | `address` | The owner of the assets. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` |   The amount of shares burned from the owner. |


<br />


## Events

### `Approval`

Emitted when one account has set the allowance of another account over their tokens.

```solidity
    event Approval(
        address owner_,
        address spender_,
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | Account that tokens are approved from. |
| 1 | `spender_` | `address` | `address` | Account that tokens are approved for. |
| 2 | `amount_` | `uint256` | `uint256` | Amount of tokens that have been approved. |

<br />

### `BootstrapMintPerformed`

Initial shares amount was minted to the zero address to prevent the first depositor frontrunning exploit.

```solidity
    event BootstrapMintPerformed(
        address caller_,
        address receiver_,
        uint256 assets_,
        uint256 shares_,
        uint256 bootStrapMintAmount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The caller of the function that emitted the &#x60;BootstrapMintPerformed&#x60; event. |
| 1 | `receiver_` | `address` | `address` | The user that was minted the shares. |
| 2 | `assets_` | `uint256` | `uint256` | The amount of assets deposited. |
| 3 | `shares_` | `uint256` | `uint256` | The amount of shares that would have been minted to the user if it was not the first deposit. |
| 4 | `bootStrapMintAmount_` | `uint256` | `uint256` | The amount of shares that was minted to the zero address to protect the first depositor. |

<br />

### `Deposit`

&#x60;caller_&#x60; has exchanged &#x60;assets_&#x60; for &#x60;shares_&#x60; and transferred them to &#x60;owner_&#x60;.         MUST be emitted when assets are deposited via the &#x60;deposit&#x60; or &#x60;mint&#x60; methods.

```solidity
    event Deposit(
        address caller_,
        address owner_,
        uint256 assets_,
        uint256 shares_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The caller of the function that emitted the &#x60;Deposit&#x60; event. |
| 1 | `owner_` | `address` | `address` | The owner of the shares. |
| 2 | `assets_` | `uint256` | `uint256` | The amount of assets deposited. |
| 3 | `shares_` | `uint256` | `uint256` | The amount of shares minted. |

<br />

### `OwnershipAccepted`

&#x60;newOwner_&#x60; has accepted the transferral of RDT ownership from &#x60;previousOwner_&#x60;.

```solidity
    event OwnershipAccepted(
        address previousOwner_,
        address newOwner_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousOwner_` | `address` | `address` | The previous RDT owner. |
| 1 | `newOwner_` | `address` | `address` | The new RDT owner. |

<br />

### `PendingOwnerSet`

&#x60;owner_&#x60; has set the new pending owner of RDT to &#x60;pendingOwner_&#x60;.

```solidity
    event PendingOwnerSet(
        address owner_,
        address pendingOwner_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The current RDT owner. |
| 1 | `pendingOwner_` | `address` | `address` | The new pending RDT owner. |

<br />

### `RedemptionRequested`

A new redemption request has been made.

```solidity
    event RedemptionRequested(
        address owner_,
        uint256 shares_,
        uint256 escrowedShares_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of shares. |
| 1 | `shares_` | `uint256` | `uint256` | The amount of shares requested to redeem. |
| 2 | `escrowedShares_` | `uint256` | `uint256` | The amount of shares actually escrowed for this withdrawal request. |

<br />

### `SharesRemoved`

Shares have been removed.

```solidity
    event SharesRemoved(
        address owner_,
        uint256 shares_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of shares. |
| 1 | `shares_` | `uint256` | `uint256` | The amount of shares requested to be removed. |

<br />

### `Transfer`

Emitted when tokens have moved from one account to another.

```solidity
    event Transfer(
        address owner_,
        address recipient_,
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | Account that tokens have moved from. |
| 1 | `recipient_` | `address` | `address` | Account that tokens have moved to. |
| 2 | `amount_` | `uint256` | `uint256` | Amount of tokens that have been transferred. |

<br />

### `Withdraw`

&#x60;caller_&#x60; has exchanged &#x60;shares_&#x60;, owned by &#x60;owner_&#x60;, for &#x60;assets_&#x60;, and transferred them to &#x60;receiver_&#x60;.         MUST be emitted when assets are withdrawn via the &#x60;withdraw&#x60; or &#x60;redeem&#x60; methods.

```solidity
    event Withdraw(
        address caller_,
        address receiver_,
        address owner_,
        uint256 assets_,
        uint256 shares_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The caller of the function that emitted the &#x60;Withdraw&#x60; event. |
| 1 | `receiver_` | `address` | `address` | The receiver of the assets. |
| 2 | `owner_` | `address` | `address` | The owner of the shares. |
| 3 | `assets_` | `uint256` | `uint256` | The amount of assets withdrawn. |
| 4 | `shares_` | `uint256` | `uint256` | The amount of shares burned. |

<br />

### `WithdrawRequested`

A new withdrawal request has been made.

```solidity
    event WithdrawRequested(
        address owner_,
        uint256 assets_,
        uint256 escrowedShares_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of shares. |
| 1 | `assets_` | `uint256` | `uint256` | The amount of assets requested to withdraw. |
| 2 | `escrowedShares_` | `uint256` | `uint256` | The amount of shares actually escrowed for this withdrawal request. |

<br />

