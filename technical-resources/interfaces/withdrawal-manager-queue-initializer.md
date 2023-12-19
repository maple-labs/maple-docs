# Maple Withdrawal Manager Initializer



<br />


## Functions

### `isManualWithdrawal`

Checks if an account is set to perform withdrawals manually.

```solidity
    function isManualWithdrawal(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `manualSharesAvailable`

Returns the amount of shares available for manual withdrawal.

```solidity
    function manualSharesAvailable(
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

### `pool`

Returns the address of the pool contract.

```solidity
    function pool()
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

### `poolManager`

Returns the address of the pool manager contract.

```solidity
    function poolManager()
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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `nextRequestId` | `uint128` | `uint128` | Identifier of the next withdrawal request that will be processed. |
| 1 | `lastRequestId` | `uint128` | `uint128` | Identifier of the last created withdrawal request. |


<br />

### `requestIds`

Returns the request identifier of an account.          Returns zero if the account does not have a withdrawal request.

```solidity
    function requestIds(
        address
    )
        view
        returns (
            uint128
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint128` | `uint128` |  |


<br />

### `totalShares`

Returns the total amount of shares pending redemption.

```solidity
    function totalShares()
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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool` | `address` | `address` | Address of the pool contract. |
| 1 | `poolManager` | `address` | `address` | Address of the pool manager contract. |

<br />

