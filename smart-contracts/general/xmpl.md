# xMPL

\


## Constructor

```solidity
    constructor(
        string name_,
        string symbol_,
        address owner_,
        address asset_,
        uint256 precision_
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description              |
| :---: | :----------: | :-------: | :-----------: | ------------------------ |
|   0   |    `name_`   |  `string` |    `string`   | The name of the token.   |
|   1   |   `symbol_`  |  `string` |    `string`   | The symbol of the token. |
|   2   |   `owner_`   | `address` |   `address`   |                          |
|   3   |   `asset_`   | `address` |   `address`   |                          |
|   4   | `precision_` | `uint256` |   `uint256`   |                          |

\


## Functions

### `MINIMUM_MIGRATION_DELAY` _\[state variable]_

Get the minimum delay that a scheduled transaction needs in order to be executed.

```solidity
    function MINIMUM_MIGRATION_DELAY()
        pure
        returns (
            uint256 minimumMigrationDelay_
        );
```

#### Return Values:

| Index |           Name           |    Type   | Internal Type | Description           |
| :---: | :----------------------: | :-------: | :-----------: | --------------------- |
|   0   | `minimumMigrationDelay_` | `uint256` |   `uint256`   | The delay in seconds. |

\


### `PERMIT_TYPEHASH` _\[state variable]_

Returns the permit type hash.

```solidity
    function PERMIT_TYPEHASH()
        view
        returns (
            bytes32 permitTypehash_
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description           |
| :---: | :---------------: | :-------: | :-----------: | --------------------- |
|   0   | `permitTypehash_` | `bytes32` |   `bytes32`   | The permit type hash. |

\


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

| Index |        Name        |    Type   | Internal Type | Description                     |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `domainSeparator_` | `bytes32` |   `bytes32`   | The signature domain separator. |

\


### `allowance` _\[state variable]_

Returns the allowance that one account has given another over their tokens.

```solidity
    function allowance(
        address owner_,
        address spender_
    )
        view
        returns (
            uint256 allowance_
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                            |
| :---: | :--------: | :-------: | :-----------: | -------------------------------------- |
|   0   |  `owner_`  | `address` |   `address`   | Account that tokens are approved from. |
|   1   | `spender_` | `address` |   `address`   | Account that tokens are approved for.  |

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description                                                     |
| :---: | :----------: | :-------: | :-----------: | --------------------------------------------------------------- |
|   0   | `allowance_` | `uint256` |   `uint256`   | Allowance that one account has given another over their tokens. |

\


### `asset` _\[state variable]_

The address of the underlying asset used by the Vault. MUST be a contract that implements the ERC-20 standard. MUST NOT revert.

```solidity
    function asset()
        view
        returns (
            address asset_
        );
```

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                          |
| :---: | :------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `asset_` | `address` |   `address`   | The address of the underlying asset. |

\


### `balanceOf` _\[state variable]_

Returns the amount of tokens owned by a given account.

```solidity
    function balanceOf(
        address account_
    )
        view
        returns (
            uint256 balance_
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                   |
| :---: | :--------: | :-------: | :-----------: | ----------------------------- |
|   0   | `account_` | `address` |   `address`   | Account that owns the tokens. |

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                                |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `balance_` | `uint256` |   `uint256`   | Amount of tokens owned by a given account. |

\


### `decimals` _\[state variable]_

Returns the decimal precision used by the token.

```solidity
    function decimals()
        view
        returns (
            uint8 decimals_
        );
```

#### Return Values:

| Index |     Name    |   Type  | Internal Type | Description                              |
| :---: | :---------: | :-----: | :-----------: | ---------------------------------------- |
|   0   | `decimals_` | `uint8` |    `uint8`    | The decimal precision used by the token. |

\


### `freeAssets` _\[state variable]_

The total amount of the underlying asset that is currently unlocked and is not time-dependent. Analogous to the y-intercept in a linear function.

```solidity
    function freeAssets()
        view
        returns (
            uint256 freeAssets_
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description |
| :---: | :-----------: | :-------: | :-----------: | ----------- |
|   0   | `freeAssets_` | `uint256` |   `uint256`   |             |

\


### `issuanceRate` _\[state variable]_

The rate of issuance of the vesting schedule that is currently active. Denominated as the amount of underlying assets vesting per second.

```solidity
    function issuanceRate()
        view
        returns (
            uint256 issuanceRate_
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description |
| :---: | :-------------: | :-------: | :-----------: | ----------- |
|   0   | `issuanceRate_` | `uint256` |   `uint256`   |             |

\


### `lastUpdated` _\[state variable]_

The timestamp of when the linear function was last recalculated. Analogous to t0 in a linear function.

```solidity
    function lastUpdated()
        view
        returns (
            uint256 lastUpdated_
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description |
| :---: | :------------: | :-------: | :-----------: | ----------- |
|   0   | `lastUpdated_` | `uint256` |   `uint256`   |             |

\


### `name` _\[state variable]_

Returns the name of the token.

```solidity
    function name()
        view
        returns (
            string name_
        );
```

#### Return Values:

| Index |   Name  |   Type   | Internal Type | Description            |
| :---: | :-----: | :------: | :-----------: | ---------------------- |
|   0   | `name_` | `string` |    `string`   | The name of the token. |

\


### `nonces` _\[state variable]_

Returns the nonce for the given owner.

```solidity
    function nonces(
        address owner_
    )
        view
        returns (
            uint256 nonce_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                       |
| :---: | :------: | :-------: | :-----------: | --------------------------------- |
|   0   | `owner_` | `address` |   `address`   | The address of the owner account. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                    |
| :---: | :------: | :-------: | :-----------: | ------------------------------ |
|   0   | `nonce_` | `uint256` |   `uint256`   | The nonce for the given owner. |

\


### `owner` _\[state variable]_

The address of the account that is allowed to update the vesting schedule.

```solidity
    function owner()
        view
        returns (
            address owner_
        );
```

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description |
| :---: | :------: | :-------: | :-----------: | ----------- |
|   0   | `owner_` | `address` |   `address`   |             |

\


### `pendingOwner` _\[state variable]_

The next owner, nominated by the current owner.

```solidity
    function pendingOwner()
        view
        returns (
            address pendingOwner_
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description |
| :---: | :-------------: | :-------: | :-----------: | ----------- |
|   0   | `pendingOwner_` | `address` |   `address`   |             |

\


### `precision` _\[state variable]_

The precision at which the issuance rate is measured.

```solidity
    function precision()
        view
        returns (
            uint256 precision_
        );
```

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description |
| :---: | :----------: | :-------: | :-----------: | ----------- |
|   0   | `precision_` | `uint256` |   `uint256`   |             |

\


### `scheduledMigrationTimestamp` _\[state variable]_

Get the timestamp that a migration is scheduled for.

```solidity
    function scheduledMigrationTimestamp()
        view
        returns (
            uint256 scheduledMigrationTimestamp_
        );
```

#### Return Values:

| Index |              Name              |    Type   | Internal Type | Description                     |
| :---: | :----------------------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `scheduledMigrationTimestamp_` | `uint256` |   `uint256`   | The timestamp of the migration. |

\


### `scheduledMigrator` _\[state variable]_

The address of the migrator contract to be used during the scheduled migration.

```solidity
    function scheduledMigrator()
        view
        returns (
            address scheduledMigrator_
        );
```

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                  |
| :---: | :------------------: | :-------: | :-----------: | ---------------------------- |
|   0   | `scheduledMigrator_` | `address` |   `address`   | The address of the migrator. |

\


### `scheduledNewAsset` _\[state variable]_

The address of the new asset token to be migrated to during the scheduled migration.

```solidity
    function scheduledNewAsset()
        view
        returns (
            address scheduledNewAsset_
        );
```

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                         |
| :---: | :------------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `scheduledNewAsset_` | `address` |   `address`   | The address of the new asset token. |

\


### `symbol` _\[state variable]_

Returns the symbol of the token.

```solidity
    function symbol()
        view
        returns (
            string symbol_
        );
```

#### Return Values:

| Index |    Name   |   Type   | Internal Type | Description              |
| :---: | :-------: | :------: | :-----------: | ------------------------ |
|   0   | `symbol_` | `string` |    `string`   | The symbol of the token. |

\


### `totalSupply` _\[state variable]_

Returns the total amount of tokens in existence.

```solidity
    function totalSupply()
        view
        returns (
            uint256 totalSupply_
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                              |
| :---: | :------------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `totalSupply_` | `uint256` |   `uint256`   | The total amount of tokens in existence. |

\


### `vestingPeriodFinish` _\[state variable]_

The end of the current vesting schedule.

```solidity
    function vestingPeriodFinish()
        view
        returns (
            uint256 vestingPeriodFinish_
        );
```

#### Return Values:

| Index |          Name          |    Type   | Internal Type | Description |
| :---: | :--------------------: | :-------: | :-----------: | ----------- |
|   0   | `vestingPeriodFinish_` | `uint256` |   `uint256`   |             |

\


### `acceptOwnership`

Sets the pending owner as the new owner. Can be called only by the pending owner, and only after their nomination by the current owner.

```solidity
    function acceptOwnership()
        nonpayable;
```

\


### `approve`

Function that allows one account to set the allowance of another account over their tokens. Emits an {Approval} event.

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

| Index |    Name    |    Type   | Internal Type | Description                               |
| :---: | :--------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `spender_` | `address` |   `address`   | Account that tokens are approved for.     |
|   1   |  `amount_` | `uint256` |   `uint256`   | Amount of tokens that have been approved. |

#### Return Values:

| Index |    Name    |  Type  | Internal Type | Description                                         |
| :---: | :--------: | :----: | :-----------: | --------------------------------------------------- |
|   0   | `success_` | `bool` |     `bool`    | Boolean indicating whether the operation succeeded. |

\


### `balanceOfAssets`

Returns the amount of underlying assets owned by the specified account.

```solidity
    function balanceOfAssets(
        address account_
    )
        view
        returns (
            uint256 assets_
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description             |
| :---: | :--------: | :-------: | :-----------: | ----------------------- |
|   0   | `account_` | `address` |   `address`   | Address of the account. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description             |
| :---: | :-------: | :-------: | :-----------: | ----------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | Amount of assets owned. |

\


### `cancelMigration`

Cancel the scheduled migration

```solidity
    function cancelMigration()
        nonpayable;
```

\


### `convertToAssets`

The amount of \`assets\_\` the \`shares\_\` are currently equivalent to. MUST NOT be inclusive of any fees that are charged against assets in the Vault. MUST NOT reflect slippage or other on-chain conditions when performing the actual exchange. MUST NOT show any variations depending on the caller. MUST NOT revert.

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

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares to convert. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of equivalent assets. |

\


### `convertToShares`

The amount of \`shares\_\` the \`assets\_\` are currently equivalent to. MUST NOT be inclusive of any fees that are charged against assets in the Vault. MUST NOT reflect slippage or other on-chain conditions when performing the actual exchange. MUST NOT show any variations depending on the caller. MUST NOT revert.

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

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets to convert. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of equivalent shares. |

\


### `decreaseAllowance`

Function that allows one account to decrease the allowance of another account over their tokens. Emits an {Approval} event.

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

| Index |         Name        |    Type   | Internal Type | Description                           |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------- |
|   0   |      `spender_`     | `address` |   `address`   | Account that tokens are approved for. |
|   1   | `subtractedAmount_` | `uint256` |   `uint256`   | Amount to decrease approval by.       |

#### Return Values:

| Index |    Name    |  Type  | Internal Type | Description                                         |
| :---: | :--------: | :----: | :-----------: | --------------------------------------------------- |
|   0   | `success_` | `bool` |     `bool`    | Boolean indicating whether the operation succeeded. |

\


### `deposit`

Mints \`shares\_\` to \`receiver\_\` by depositing \`assets\_\` into the Vault. MUST emit the {Deposit} event. MUST revert if all of the assets cannot be deposited (due to insufficient approval, deposit limits, slippage, etc).

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

| Index |     Name    |    Type   | Internal Type | Description                      |
| :---: | :---------: | :-------: | :-----------: | -------------------------------- |
|   0   |  `assets_`  | `uint256` |   `uint256`   | The amount of assets to deposit. |
|   1   | `receiver_` | `address` |   `address`   | The receiver of the shares.      |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                  |
| :---: | :-------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares minted. |

\


### `depositWithPermit`

Does a ERC4626 \`deposit\` with a ERC-2612 \`permit\`.

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

| Index |     Name    |    Type   | Internal Type | Description                                                            |
| :---: | :---------: | :-------: | :-----------: | ---------------------------------------------------------------------- |
|   0   |  `assets_`  | `uint256` |   `uint256`   | The amount of \`asset\` to deposit.                                    |
|   1   | `receiver_` | `address` |   `address`   | The receiver of the shares.                                            |
|   2   | `deadline_` | `uint256` |   `uint256`   | The timestamp after which the \`permit\` signature is no longer valid. |
|   3   |     `v_`    |  `uint8`  |    `uint8`    | ECDSA signature v component.                                           |
|   4   |     `r_`    | `bytes32` |   `bytes32`   | ECDSA signature r component.                                           |
|   5   |     `s_`    | `bytes32` |   `bytes32`   | ECDSA signature s component.                                           |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                  |
| :---: | :-------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares minted. |

\


### `increaseAllowance`

Function that allows one account to increase the allowance of another account over their tokens. Emits an {Approval} event.

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

| Index |      Name      |    Type   | Internal Type | Description                           |
| :---: | :------------: | :-------: | :-----------: | ------------------------------------- |
|   0   |   `spender_`   | `address` |   `address`   | Account that tokens are approved for. |
|   1   | `addedAmount_` | `uint256` |   `uint256`   | Amount to increase approval by.       |

#### Return Values:

| Index |    Name    |  Type  | Internal Type | Description                                         |
| :---: | :--------: | :----: | :-----------: | --------------------------------------------------- |
|   0   | `success_` | `bool` |     `bool`    | Boolean indicating whether the operation succeeded. |

\


### `maxDeposit`

Maximum amount of \`assets\_\` that can be deposited on behalf of the \`receiver\_\` through a \`deposit\` call. MUST return a limited value if the receiver is subject to any limits, or the maximum value otherwise. MUST NOT revert.

```solidity
    function maxDeposit(
        address receiver_
    )
        view
        returns (
            uint256 assets_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                 |
| :---: | :---------: | :-------: | :-----------: | --------------------------- |
|   0   | `receiver_` | `address` |   `address`   | The receiver of the assets. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                         |
| :---: | :-------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The maximum amount of assets that can be deposited. |

\


### `maxMint`

Maximum amount of \`shares\_\` that can be minted on behalf of the \`receiver\_\` through a \`mint\` call. MUST return a limited value if the receiver is subject to any limits, or the maximum value otherwise. MUST NOT revert.

```solidity
    function maxMint(
        address receiver_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                 |
| :---: | :---------: | :-------: | :-----------: | --------------------------- |
|   0   | `receiver_` | `address` |   `address`   | The receiver of the shares. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                      |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   | `shares_` | `uint256` |   `uint256`   | The maximum amount of shares that can be minted. |

\


### `maxRedeem`

Maximum amount of \`shares\_\` that can be redeemed from the \`owner\_\` through a \`redeem\` call. MUST return a limited value if the owner is subject to any limits, or the total amount of owned shares otherwise. MUST NOT revert.

```solidity
    function maxRedeem(
        address owner_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description              |
| :---: | :------: | :-------: | :-----------: | ------------------------ |
|   0   | `owner_` | `address` |   `address`   | The owner of the shares. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                        |
| :---: | :-------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The maximum amount of shares that can be redeemed. |

\


### `maxWithdraw`

Maximum amount of \`assets\_\` that can be withdrawn from the \`owner\_\` through a \`withdraw\` call. MUST return a limited value if the owner is subject to any limits, or the total amount of owned assets otherwise. MUST NOT revert.

```solidity
    function maxWithdraw(
        address owner_
    )
        view
        returns (
            uint256 assets_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description              |
| :---: | :------: | :-------: | :-----------: | ------------------------ |
|   0   | `owner_` | `address` |   `address`   | The owner of the assets. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                         |
| :---: | :-------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The maximum amount of assets that can be withdrawn. |

\


### `mint`

Mints \`shares\_\` to \`receiver\_\` by depositing \`assets\_\` into the Vault. MUST emit the {Deposit} event. MUST revert if all of shares cannot be minted (due to insufficient approval, deposit limits, slippage, etc).

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

| Index |     Name    |    Type   | Internal Type | Description                   |
| :---: | :---------: | :-------: | :-----------: | ----------------------------- |
|   0   |  `shares_`  | `uint256` |   `uint256`   | The amount of shares to mint. |
|   1   | `receiver_` | `address` |   `address`   | The receiver of the shares.   |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                     |
| :---: | :-------: | :-------: | :-----------: | ------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets deposited. |

\


### `mintWithPermit`

Does a ERC4626 \`mint\` with a ERC-2612 \`permit\`.

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

| Index |     Name     |    Type   | Internal Type | Description                                                            |
| :---: | :----------: | :-------: | :-----------: | ---------------------------------------------------------------------- |
|   0   |   `shares_`  | `uint256` |   `uint256`   | The amount of \`shares\` to mint.                                      |
|   1   |  `receiver_` | `address` |   `address`   | The receiver of the shares.                                            |
|   2   | `maxAssets_` | `uint256` |   `uint256`   | The maximum amount of assets that can be taken, as per the permit.     |
|   3   |  `deadline_` | `uint256` |   `uint256`   | The timestamp after which the \`permit\` signature is no longer valid. |
|   4   |     `v_`     |  `uint8`  |    `uint8`    | ECDSA signature v component.                                           |
|   5   |     `r_`     | `bytes32` |   `bytes32`   | ECDSA signature r component.                                           |
|   6   |     `s_`     | `bytes32` |   `bytes32`   | ECDSA signature s component.                                           |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                     |
| :---: | :-------: | :-------: | :-----------: | ------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of shares deposited. |

\


### `performMigration`

Perform a migration of the asset.

```solidity
    function performMigration()
        nonpayable;
```

\


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

| Index |     Name    |    Type   | Internal Type | Description                                 |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |   `owner_`  | `address` |   `address`   | Owner address that signed the permit.       |
|   1   |  `spender_` | `address` |   `address`   | Spender of the permit.                      |
|   2   |  `amount_`  | `uint256` |   `uint256`   | Permit approval spend limit.                |
|   3   | `deadline_` | `uint256` |   `uint256`   | Deadline after which the permit is invalid. |
|   4   |     `v_`    |  `uint8`  |    `uint8`    | ECDSA signature v component.                |
|   5   |     `r_`    | `bytes32` |   `bytes32`   | ECDSA signature r component.                |
|   6   |     `s_`    | `bytes32` |   `bytes32`   | ECDSA signature s component.                |

\


### `previewDeposit`

Allows an on-chain or off-chain user to simulate the effects of their deposit at the current block, given current on-chain conditions. MUST return as close to and no more than the exact amount of shares that would be minted in a \`deposit\` call in the same transaction. MUST NOT account for deposit limits like those returned from \`maxDeposit\` and should always act as though the deposit would be accepted. MUST NOT revert.

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

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets to deposit. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares that would be minted. |

\


### `previewMint`

Allows an on-chain or off-chain user to simulate the effects of their mint at the current block, given current on-chain conditions. MUST return as close to and no fewer than the exact amount of assets that would be deposited in a \`mint\` call in the same transaction. MUST NOT account for mint limits like those returned from \`maxMint\` and should always act as though the minting would be accepted. MUST NOT revert.

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

| Index |    Name   |    Type   | Internal Type | Description                   |
| :---: | :-------: | :-------: | :-----------: | ----------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares to mint. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                   |
| :---: | :-------: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets that would be deposited. |

\


### `previewRedeem`

Allows an on-chain or off-chain user to simulate the effects of their redemption at the current block, given current on-chain conditions. MUST return as close to and no more than the exact amount of assets that would be withdrawn in a \`redeem\` call in the same transaction. MUST NOT account for redemption limits like those returned from \`maxRedeem\` and should always act as though the redemption would be accepted. MUST NOT revert.

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

| Index |    Name   |    Type   | Internal Type | Description                     |
| :---: | :-------: | :-------: | :-----------: | ------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares to redeem. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                   |
| :---: | :-------: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets that would be withdrawn. |

\


### `previewWithdraw`

Allows an on-chain or off-chain user to simulate the effects of their withdrawal at the current block, given current on-chain conditions. MUST return as close to and no fewer than the exact amount of shares that would be burned in a \`withdraw\` call in the same transaction. MUST NOT account for withdrawal limits like those returned from \`maxWithdraw\` and should always act as though the withdrawal would be accepted. MUST NOT revert.

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

| Index |    Name   |    Type   | Internal Type | Description                       |
| :---: | :-------: | :-------: | :-----------: | --------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets to withdraw. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                  |
| :---: | :-------: | :-------: | :-----------: | -------------------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares that would be redeemed. |

\


### `redeem`

Burns \`shares\_\` from \`owner\_\` and sends \`assets\_\` to \`receiver\_\`. MUST emit the {Withdraw} event. MUST revert if all of the shares cannot be redeemed (due to insufficient shares, withdrawal limits, slippage, etc).

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

| Index |     Name    |    Type   | Internal Type | Description                     |
| :---: | :---------: | :-------: | :-----------: | ------------------------------- |
|   0   |  `shares_`  | `uint256` |   `uint256`   | The amount of shares to redeem. |
|   1   | `receiver_` | `address` |   `address`   | The receiver of the assets.     |
|   2   |   `owner_`  | `address` |   `address`   | The owner of the shares.        |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets sent to the receiver. |

\


### `scheduleMigration`

Schedule a migration to be executed after a delay.

```solidity
    function scheduleMigration(
        address migrator_,
        address newAsset_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `migrator_` | `address` |   `address`   | The address of the migrator contract. |
|   1   | `newAsset_` | `address` |   `address`   | The address of the new asset token.   |

\


### `setPendingOwner`

Sets a new address as the pending owner.

```solidity
    function setPendingOwner(
        address pendingOwner_
    )
        nonpayable;
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                              |
| :---: | :-------------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `pendingOwner_` | `address` |   `address`   | The address of the next potential owner. |

\


### `totalAssets`

Total amount of the underlying asset that is managed by the Vault. SHOULD include compounding that occurs from any yields. MUST NOT revert.

```solidity
    function totalAssets()
        view
        returns (
            uint256 totalAssets_
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                                   |
| :---: | :------------: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `totalAssets_` | `uint256` |   `uint256`   | The total amount of assets the Vault manages. |

\


### `transfer`

Moves an amount of tokens from \`msg.sender\` to a specified account. Emits a {Transfer} event.

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

| Index |     Name     |    Type   | Internal Type | Description                            |
| :---: | :----------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `recipient_` | `address` |   `address`   | Account that receives tokens.          |
|   1   |   `amount_`  | `uint256` |   `uint256`   | Amount of tokens that are transferred. |

#### Return Values:

| Index |    Name    |  Type  | Internal Type | Description                                         |
| :---: | :--------: | :----: | :-----------: | --------------------------------------------------- |
|   0   | `success_` | `bool` |     `bool`    | Boolean indicating whether the operation succeeded. |

\


### `transferFrom`

Moves a pre-approved amount of tokens from a sender to a specified account. Emits a {Transfer} event. Emits an {Approval} event.

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

| Index |     Name     |    Type   | Internal Type | Description                            |
| :---: | :----------: | :-------: | :-----------: | -------------------------------------- |
|   0   |   `owner_`   | `address` |   `address`   | Account that tokens are moving from.   |
|   1   | `recipient_` | `address` |   `address`   | Account that receives tokens.          |
|   2   |   `amount_`  | `uint256` |   `uint256`   | Amount of tokens that are transferred. |

#### Return Values:

| Index |    Name    |  Type  | Internal Type | Description                                         |
| :---: | :--------: | :----: | :-----------: | --------------------------------------------------- |
|   0   | `success_` | `bool` |     `bool`    | Boolean indicating whether the operation succeeded. |

\


### `updateVestingSchedule`

Updates the current vesting formula based on the amount of total unvested funds in the contract and the new \`vestingPeriod\_\`.

```solidity
    function updateVestingSchedule(
        uint256 vestingPeriod_
    )
        nonpayable
        returns (
            uint256 issuanceRate_,
            uint256 freeAssets_
        );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                                                                    |
| :---: | :--------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------------------- |
|   0   | `vestingPeriod_` | `uint256` |   `uint256`   | The amount of time over which all currently unaccounted underlying assets will be vested over. |

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                                            |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------------------------------ |
|   0   | `issuanceRate_` | `uint256` |   `uint256`   | The new issuance rate.                                 |
|   1   |  `freeAssets_`  | `uint256` |   `uint256`   | The new amount of underlying assets that are unlocked. |

\


### `withdraw`

Burns \`shares\_\` from \`owner\_\` and sends \`assets\_\` to \`receiver\_\`. MUST emit the {Withdraw} event. MUST revert if all of the assets cannot be withdrawn (due to insufficient assets, withdrawal limits, slippage, etc).

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

| Index |     Name    |    Type   | Internal Type | Description                       |
| :---: | :---------: | :-------: | :-----------: | --------------------------------- |
|   0   |  `assets_`  | `uint256` |   `uint256`   | The amount of assets to withdraw. |
|   1   | `receiver_` | `address` |   `address`   | The receiver of the assets.       |
|   2   |   `owner_`  | `address` |   `address`   | The owner of the assets.          |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                 |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares burned from the owner. |

\


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

| Index |    Name    |    Type   | Internal Type | Description                               |
| :---: | :--------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |  `owner_`  | `address` |   `address`   | Account that tokens are approved from.    |
|   1   | `spender_` | `address` |   `address`   | Account that tokens are approved for.     |
|   2   |  `amount_` | `uint256` |   `uint256`   | Amount of tokens that have been approved. |

\


### `Deposit`

\`caller\_\` has exchanged \`assets\_\` for \`shares\_\` and transferred them to \`owner\_\`. MUST be emitted when assets are deposited via the \`deposit\` or \`mint\` methods.

```solidity
    event Deposit(
        address caller_,
        address owner_,
        uint256 assets_,
        uint256 shares_
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                                    |
| :---: | :-------: | :-------: | :-----------: | -------------------------------------------------------------- |
|   0   | `caller_` | `address` |   `address`   | The caller of the function that emitted the \`Deposit\` event. |
|   1   |  `owner_` | `address` |   `address`   | The owner of the shares.                                       |
|   2   | `assets_` | `uint256` |   `uint256`   | The amount of assets deposited.                                |
|   3   | `shares_` | `uint256` |   `uint256`   | The amount of shares minted.                                   |

\


### `MigrationCancelled`

Notifies that a scheduled migration was cancelled.

```solidity
    event MigrationCancelled();
```

\


### `MigrationPerformed`

Notifies that a scheduled migration was executed.

```solidity
    event MigrationPerformed(
        address fromAsset_,
        address toAsset_,
        uint256 amount_
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                           |
| :---: | :----------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `fromAsset_` | `address` |   `address`   | The address of the old asset.         |
|   1   |  `toAsset_`  | `address` |   `address`   | The address of new asset migrated to. |
|   2   |   `amount_`  | `uint256` |   `uint256`   | The amount of tokens migrated.        |

\


### `MigrationScheduled`

Notifies that migration was scheduled.

```solidity
    event MigrationScheduled(
        address fromAsset_,
        address toAsset_,
        address migrator_,
        uint256 migrationTime_
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                       |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   |   `fromAsset_`   | `address` |   `address`   | The current asset address.                        |
|   1   |    `toAsset_`    | `address` |   `address`   | The address of the asset to be migrated to.       |
|   2   |    `migrator_`   | `address` |   `address`   | The address of the migrator contract.             |
|   3   | `migrationTime_` | `uint256` |   `uint256`   | The earliest time the migration is scheduled for. |

\


### `OwnershipAccepted`

\`newOwner\_\` has accepted the transferral of RDT ownership from \`previousOwner\_\`.

```solidity
    event OwnershipAccepted(
        address previousOwner_,
        address newOwner_
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description             |
| :---: | :--------------: | :-------: | :-----------: | ----------------------- |
|   0   | `previousOwner_` | `address` |   `address`   | The previous RDT owner. |
|   1   |    `newOwner_`   | `address` |   `address`   | The new RDT owner.      |

\


### `PendingOwnerSet`

\`owner\_\` has set the new pending owner of RDT to \`pendingOwner\_\`.

```solidity
    event PendingOwnerSet(
        address owner_,
        address pendingOwner_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                |
| :---: | :-------------: | :-------: | :-----------: | -------------------------- |
|   0   |     `owner_`    | `address` |   `address`   | The current RDT owner.     |
|   1   | `pendingOwner_` | `address` |   `address`   | The new pending RDT owner. |

\


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

| Index |     Name     |    Type   | Internal Type | Description                                  |
| :---: | :----------: | :-------: | :-----------: | -------------------------------------------- |
|   0   |   `owner_`   | `address` |   `address`   | Account that tokens have moved from.         |
|   1   | `recipient_` | `address` |   `address`   | Account that tokens have moved to.           |
|   2   |   `amount_`  | `uint256` |   `uint256`   | Amount of tokens that have been transferred. |

\


### `VestingScheduleUpdated`

\`owner\_\` has updated the RDT vesting schedule to end at \`vestingPeriodFinish\_\`, with an issuance rate of \`issuanceRate\_\`.

```solidity
    event VestingScheduleUpdated(
        address owner_,
        uint256 vestingPeriodFinish_,
        uint256 issuanceRate_
    );
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description                                                         |
| :---: | :--------------------: | :-------: | :-----------: | ------------------------------------------------------------------- |
|   0   |        `owner_`        | `address` |   `address`   | The current RDT owner.                                              |
|   1   | `vestingPeriodFinish_` | `uint256` |   `uint256`   | When the unvested balance will finish vesting.                      |
|   2   |     `issuanceRate_`    | `uint256` |   `uint256`   | The new issuance rate of \`asset\` until \`vestingPeriodFinish\_\`. |

\


### `Withdraw`

\`caller\_\` has exchanged \`shares\_\`, owned by \`owner\_\`, for \`assets\_\`, and transferred them to \`receiver\_\`. MUST be emitted when assets are withdrawn via the \`withdraw\` or \`redeem\` methods.

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

| Index |     Name    |    Type   | Internal Type | Description                                                     |
| :---: | :---------: | :-------: | :-----------: | --------------------------------------------------------------- |
|   0   |  `caller_`  | `address` |   `address`   | The caller of the function that emitted the \`Withdraw\` event. |
|   1   | `receiver_` | `address` |   `address`   | The receiver of the assets.                                     |
|   2   |   `owner_`  | `address` |   `address`   | The owner of the shares.                                        |
|   3   |  `assets_`  | `uint256` |   `uint256`   | The amount of assets withdrawn.                                 |
|   4   |  `shares_`  | `uint256` |   `uint256`   | The amount of shares burned.                                    |

\
