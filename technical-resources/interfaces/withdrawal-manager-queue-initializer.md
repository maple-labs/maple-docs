# WithdrawalManagerInitializer (Queue)



## Functions

### `isManualWithdrawal`

Checks if an account is set to perform withdrawals manually.

```solidity
    function isManualWithdrawal(
        address account
    )
        view
        returns (
            bool isManual
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description             |
| :---: | :-------: | :-------: | :-----------: | ----------------------- |
|   0   | `account` | `address` |   `address`   | Address of the account. |

#### Return Values:

| Index |    Name    |  Type  | Internal Type | Description                                                   |
| :---: | :--------: | :----: | :-----------: | ------------------------------------------------------------- |
|   0   | `isManual` | `bool` |     `bool`    | \`true\` if the account withdraws manually, \`false\` if not. |



### `manualSharesAvailable`

Returns the amount of shares available for manual withdrawal.

```solidity
    function manualSharesAvailable(
        address owner
    )
        view
        returns (
            uint256 sharesAvailable
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                         |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------- |
|   0   | `owner` | `address` |   `address`   | The address of the owner of shares. |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                                       |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   | `sharesAvailable` | `uint256` |   `uint256`   | Amount of shares available for manual withdrawal. |



### `pool`

Returns the address of the pool contract.

```solidity
    function pool()
        view
        returns (
            address pool
        );
```

#### Return Values:

| Index |  Name  |    Type   | Internal Type | Description                   |
| :---: | :----: | :-------: | :-----------: | ----------------------------- |
|   0   | `pool` | `address` |   `address`   | Address of the pool contract. |



### `poolManager`

Returns the address of the pool manager contract.

```solidity
    function poolManager()
        view
        returns (
            address poolManager
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                           |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager contract. |



### `queue`

Returns the first and last withdrawal requests pending redemption.

```solidity
    function queue()
        view
        returns (
            uint128 nextRequestId,
            uint128 lastRequestId
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                                                       |
| :---: | :-------------: | :-------: | :-----------: | ----------------------------------------------------------------- |
|   0   | `nextRequestId` | `uint128` |   `uint128`   | Identifier of the next withdrawal request that will be processed. |
|   1   | `lastRequestId` | `uint128` |   `uint128`   | Identifier of the last created withdrawal request.                |



### `totalShares`

Returns the total amount of shares pending redemption.

```solidity
    function totalShares()
        view
        returns (
            uint256 totalShares
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                                |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `totalShares` | `uint256` |   `uint256`   | Total amount of shares pending redemption. |



### `userEscrowedShares`

Returns the amount of shares escrowed for a specific user yet to be processed.

```solidity
    function userEscrowedShares(
        address owner
    )
        view
        returns (
            uint256 escrowedShares
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                         |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------- |
|   0   | `owner` | `address` |   `address`   | The address of the owner of shares. |

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                             |
| :---: | :--------------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `escrowedShares` | `uint256` |   `uint256`   | Amount of shares escrowed for the user. |



## Events

### `Initialized`

Emitted when the withdrawal manager proxy contract is initialized.

```solidity
    event Initialized(
        address pool,
        address poolManager
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                           |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------- |
|   0   |     `pool`    | `address` |   `address`   | Address of the pool contract.         |
|   1   | `poolManager` | `address` |   `address`   | Address of the pool manager contract. |

