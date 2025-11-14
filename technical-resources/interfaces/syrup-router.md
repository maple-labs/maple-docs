# SyrupRouter

Lightweight router for lender integrations with Syrup pools. Provides stable entry points for first‑time authorized deposits (with optional ERC‑2612 permits) and subsequent deposits, and exposes the underlying pool, manager, and permission manager addresses.

## Functions

### `asset`

Returns the underlying asset of the ERC‑4626 vault (pool).

```solidity
    function asset()
        view
        returns (
            address asset
        );
```



### `pool`

Returns the Maple Pool (ERC‑4626 vault) address.

```solidity
    function pool()
        view
        returns (
            address pool
        );
```



### `poolManager`

Returns the Pool Manager address.

```solidity
    function poolManager()
        view
        returns (
            address poolManager
        );
```



### `poolPermissionManager`

Returns the Pool Permission Manager address.

```solidity
    function poolPermissionManager()
        view
        returns (
            address poolPermissionManager
        );
```



### `nonces`

Returns the current nonce for the owner (used in authorization signatures).

```solidity
    function nonces(
        address owner
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index |  Name  |   Type   | Internal Type | Description                |
| :---: | :----: | :------: | :-----------: | -------------------------- |
|   0   | `owner`| `address`|   `address`   | Address to get nonce for   |



### `authorizeAndDeposit`

Authorizes the lender and deposits assets.

```solidity
    function authorizeAndDeposit(
        uint256 bitmap,
        uint256 deadline,
        uint8   v,
        bytes32 r,
        bytes32 s,
        uint256 amount,
        bytes32 depositData
    )
        external
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |     Name     |   Type   | Internal Type | Description                      |
| :---: | :----------: | :------: | :-----------: | -------------------------------- |
|   0   |  `bitmap`    | `uint256`|   `uint256`   | Lender permission bitmap         |
|   1   | `deadline`   | `uint256`|   `uint256`   | Authorization expiry timestamp   |
|   2   |    `v`       |  `uint8` |    `uint8`    | ECDSA v component                |
|   3   |    `r`       | `bytes32`|   `bytes32`   | ECDSA r component                |
|   4   |    `s`       | `bytes32`|   `bytes32`   | ECDSA s component                |
|   5   |  `amount`    | `uint256`|   `uint256`   | Asset amount to deposit          |
|   6   | `depositData`| `bytes32`|   `bytes32`   | Optional deposit metadata        |



### `authorizeAndDepositWithPermit`

Authorizes the lender and deposits with an ERC‑2612 permit.

```solidity
    function authorizeAndDepositWithPermit(
        uint256 bitmap,
        uint256 authDeadline,
        uint8   authV,
        bytes32 authR,
        bytes32 authS,
        uint256 amount,
        bytes32 depositData,
        uint256 permitDeadline,
        uint8   permitV,
        bytes32 permitR,
        bytes32 permitS
    )
        external
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |      Name      |   Type   | Internal Type | Description                         |
| :---: | :------------: | :------: | :-----------: | ----------------------------------- |
|   0   |   `bitmap`     | `uint256`|   `uint256`   | Lender permission bitmap            |
|   1   | `authDeadline` | `uint256`|   `uint256`   | Authorization expiry timestamp      |
|   2   |    `authV`     |  `uint8` |    `uint8`    | Auth ECDSA v component              |
|   3   |    `authR`     | `bytes32`|   `bytes32`   | Auth ECDSA r component              |
|   4   |    `authS`     | `bytes32`|   `bytes32`   | Auth ECDSA s component              |
|   5   |   `amount`     | `uint256`|   `uint256`   | Asset amount to deposit             |
|   6   | `depositData`  | `bytes32`|   `bytes32`   | Optional deposit metadata           |
|   7   | `permitDeadline`|`uint256`|   `uint256`   | Permit expiry timestamp             |
|   8   |   `permitV`    |  `uint8` |    `uint8`    | Permit ECDSA v component            |
|   9   |   `permitR`    | `bytes32`|   `bytes32`   | Permit ECDSA r component            |
|  10   |   `permitS`    | `bytes32`|   `bytes32`   | Permit ECDSA s component            |



### `deposit`

Deposits assets when already authorized.

```solidity
    function deposit(
        uint256 amount,
        bytes32 depositData
    )
        external
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |     Name     |   Type   | Internal Type | Description               |
| :---: | :----------: | :------: | :-----------: | ------------------------- |
|   0   |  `amount`    | `uint256`|   `uint256`   | Asset amount to deposit    |
|   1   | `depositData`| `bytes32`|   `bytes32`   | Optional deposit metadata  |



### `depositWithPermit`

Deposits with an ERC‑2612 permit when already authorized.

```solidity
    function depositWithPermit(
        uint256 amount,
        uint256 deadline,
        uint8   v,
        bytes32 r,
        bytes32 s,
        bytes32 depositData
    )
        external
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |     Name     |   Type   | Internal Type | Description                      |
| :---: | :----------: | :------: | :-----------: | -------------------------------- |
|   0   |  `amount`    | `uint256`|   `uint256`   | Asset amount to deposit          |
|   1   | `deadline`   | `uint256`|   `uint256`   | Permit expiry timestamp          |
|   2   |    `v`       |  `uint8` |    `uint8`    | ECDSA v component                |
|   3   |    `r`       | `bytes32`|   `bytes32`   | ECDSA r component                |
|   4   |    `s`       | `bytes32`|   `bytes32`   | ECDSA s component                |
|   5   | `depositData`| `bytes32`|   `bytes32`   | Optional deposit metadata        |

## Events

```solidity
event DepositData(
    address indexed owner,
    uint256 amount,
    bytes32 depositData
);
```
