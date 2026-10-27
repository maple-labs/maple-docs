# SyrupRouter

Lightweight router for lender integrations with Syrup Pools. Provides stable entry points for first-time authorized deposits (with optional ERC-2612 permits) and subsequent deposits, and exposes the underlying Pool, Pool Manager, and Pool Permission Manager addresses.

## Functions

### `asset`

The address of the underlying asset used by the ERC-4626 Pool.

```solidity
    function asset()
        view
        returns (
            address asset
        );
```

#### Return Values:

| Index |   Name  |    Type   | Internal Type | Description                          |
| :---: | :-----: | :-------: | :-----------: | ------------------------------------ |
|   0   | `asset` | `address` |   `address`   | The address of the underlying asset. |



### `pool`

The address of the ERC-4626 Pool.

```solidity
    function pool()
        view
        returns (
            address pool
        );
```

#### Return Values:

| Index |  Name  |    Type   | Internal Type | Description                       |
| :---: | :----: | :-------: | :-----------: | --------------------------------- |
|   0   | `pool` | `address` |   `address`   | The address of the ERC-4626 Pool. |



### `poolManager`

The address of the Pool Manager.

```solidity
    function poolManager()
        view
        returns (
            address poolManager
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                      |
| :---: | :-----------: | :-------: | :-----------: | -------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | The address of the Pool Manager. |



### `poolPermissionManager`

The address of the Pool Permission Manager.

```solidity
    function poolPermissionManager()
        view
        returns (
            address poolPermissionManager
        );
```

#### Return Values:

| Index |           Name          |    Type   | Internal Type | Description                                 |
| :---: | :---------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `poolPermissionManager` | `address` |   `address`   | The address of the Pool Permission Manager. |



### `nonces`

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



### `authorizeAndDeposit`

Authorizes and deposits assets into the Pool.

```solidity
    function authorizeAndDeposit(
        uint256 bitmap_,
        uint256 deadline_,
        uint8   auth_v,
        bytes32 auth_r,
        bytes32 auth_s,
        uint256 amount_,
        bytes32 depositData_
    )
        nonpayable
        returns (
            uint256 shares_
        );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                                             |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------------------------------- |
|   0   |    `bitmap_`   | `uint256` |   `uint256`   | The bitmap of the permission.                                           |
|   1   |   `deadline_`  | `uint256` |   `uint256`   | The timestamp after which the `authorize` signature is no longer valid. |
|   2   |    `auth_v`    |  `uint8`  |    `uint8`    | ECDSA signature v component.                                            |
|   3   |    `auth_r`    | `bytes32` |   `bytes32`   | ECDSA signature r component.                                            |
|   4   |    `auth_s`    | `bytes32` |   `bytes32`   | ECDSA signature s component.                                            |
|   5   |    `amount_`   | `uint256` |   `uint256`   | The amount of assets to deposit.                                        |
|   6   | `depositData_` | `bytes32` |   `bytes32`   | Optional deposit data.                                                  |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                  |
| :---: | :-------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares minted. |



### `authorizeAndDepositWithPermit`

Authorizes and deposits assets into the Pool with an ERC-2612 `permit`.

```solidity
    function authorizeAndDepositWithPermit(
        uint256 bitmap_,
        uint256 auth_deadline_,
        uint8   auth_v,
        bytes32 auth_r,
        bytes32 auth_s,
        uint256 amount_,
        bytes32 depositData_,
        uint256 permit_deadline,
        uint8   permit_v_,
        bytes32 permit_r_,
        bytes32 permit_s_
    )
        nonpayable
        returns (
            uint256 shares_
        );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                                             |
| :---: | :---------------: | :-------: | :-----------: | ----------------------------------------------------------------------- |
|   0   |     `bitmap_`     | `uint256` |   `uint256`   | The bitmap of the permission.                                           |
|   1   |  `auth_deadline_` | `uint256` |   `uint256`   | The timestamp after which the `authorize` signature is no longer valid. |
|   2   |      `auth_v`     |  `uint8`  |    `uint8`    | ECDSA signature v component of the authorization.                       |
|   3   |      `auth_r`     | `bytes32` |   `bytes32`   | ECDSA signature r component of the authorization.                       |
|   4   |      `auth_s`     | `bytes32` |   `bytes32`   | ECDSA signature s component of the authorization.                       |
|   5   |     `amount_`     | `uint256` |   `uint256`   | The amount of assets to deposit.                                        |
|   6   |   `depositData_`  | `bytes32` |   `bytes32`   | Optional deposit data.                                                  |
|   7   | `permit_deadline` | `uint256` |   `uint256`   | The timestamp after which the `permit` signature is no longer valid.    |
|   8   |    `permit_v_`    |  `uint8`  |    `uint8`    | ECDSA signature v component of the token permit.                        |
|   9   |    `permit_r_`    | `bytes32` |   `bytes32`   | ECDSA signature r component of the token permit.                        |
|   10  |    `permit_s_`    | `bytes32` |   `bytes32`   | ECDSA signature s component of the token permit.                        |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                  |
| :---: | :-------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares minted. |



### `deposit`

Mints `shares` to the sender by depositing `assets` into the Pool.

```solidity
    function deposit(
        uint256 assets,
        bytes32 depositData
    )
        nonpayable
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                      |
| :---: | :-----------: | :-------: | :-----------: | -------------------------------- |
|   0   |    `assets`   | `uint256` |   `uint256`   | The amount of assets to deposit. |
|   1   | `depositData` | `bytes32` |   `bytes32`   | Optional deposit data.           |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                  |
| :---: | :------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | The amount of shares minted. |



### `depositWithPermit`

Does an ERC-4626 `deposit` into a Maple Pool with an ERC-2612 `permit`.

```solidity
    function depositWithPermit(
        uint256 amount,
        uint256 deadline,
        uint8   v,
        bytes32 r,
        bytes32 s,
        bytes32 depositData
    )
        nonpayable
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                          |
| :---: | :-----------: | :-------: | :-----------: | -------------------------------------------------------------------- |
|   0   |    `amount`   | `uint256` |   `uint256`   | The amount of assets to deposit.                                     |
|   1   |   `deadline`  | `uint256` |   `uint256`   | The timestamp after which the `permit` signature is no longer valid. |
|   2   |      `v`      |  `uint8`  |    `uint8`    | ECDSA signature v component.                                         |
|   3   |      `r`      | `bytes32` |   `bytes32`   | ECDSA signature r component.                                         |
|   4   |      `s`      | `bytes32` |   `bytes32`   | ECDSA signature s component.                                         |
|   5   | `depositData` | `bytes32` |   `bytes32`   | Optional deposit data.                                               |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                  |
| :---: | :------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | The amount of shares minted. |



## Events

### `DepositData`

Optional deposit data for off-chain processing.

```solidity
    event DepositData(
        address indexed owner,
        uint256 amount,
        bytes32 depositData
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                      |
| :---: | :-----------: | :-------: | :-----------: | -------------------------------- |
|   0   |    `owner`    | `address` |   `address`   | The receiver of the shares.      |
|   1   |    `amount`   | `uint256` |   `uint256`   | The amount of assets to deposit. |
|   2   | `depositData` | `bytes32` |   `bytes32`   | Optional deposit data.           |
