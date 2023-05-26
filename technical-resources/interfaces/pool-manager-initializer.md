# Maple Pool Manager Initializer



<br />


## Functions

### `active`

Returns whether or not a pool is active.

```solidity
    function active()
        view
        returns (
            bool
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `asset`

Gets the address of the funds asset.

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

### `configured`

Returns whether or not a pool is configured.

```solidity
    function configured()
        view
        returns (
            bool
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `decodeArguments`



```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address poolDelegate_,
            address asset_,
            uint256 initialSupply_,
            string name_,
            string symbol_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate_` | `address` | `address` |  |
| 1 | `asset_` | `address` | `address` |  |
| 2 | `initialSupply_` | `uint256` | `uint256` |  |
| 3 | `name_` | `string` | `string` |  |
| 4 | `symbol_` | `string` | `string` |  |


<br />

### `delegateManagementFeeRate`

Gets the delegate management fee rate.

```solidity
    function delegateManagementFeeRate()
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

### `encodeArguments`



```solidity
    function encodeArguments(
        address poolDelegate_,
        address asset_,
        uint256 initialSupply_,
        string name_,
        string symbol_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate_` | `address` | `address` |  |
| 1 | `asset_` | `address` | `address` |  |
| 2 | `initialSupply_` | `uint256` | `uint256` |  |
| 3 | `name_` | `string` | `string` |  |
| 4 | `symbol_` | `string` | `string` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


<br />

### `isLoanManager`

Returns whether or not the given address is a loan manager.

```solidity
    function isLoanManager(
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

### `isValidLender`

Returns whether or not the given address is a valid lender.

```solidity
    function isValidLender(
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

### `liquidityCap`

Gets the liquidity cap for the pool.

```solidity
    function liquidityCap()
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

### `loanManagerList`

Gets the address of the loan manager in the list.

```solidity
    function loanManagerList(
        uint256
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `openToPublic`

Returns whether or not a pool is open to public deposits.

```solidity
    function openToPublic()
        view
        returns (
            bool
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `pendingPoolDelegate`

Gets the address of the pending pool delegate.

```solidity
    function pendingPoolDelegate()
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

### `pool`

Gets the address of the pool.

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

### `poolDelegate`

Gets the address of the pool delegate.

```solidity
    function poolDelegate()
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

### `poolDelegateCover`

Gets the address of the pool delegate cover.

```solidity
    function poolDelegateCover()
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

### `withdrawalManager`

Gets the address of the withdrawal manager.

```solidity
    function withdrawalManager()
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


## Events

### `Initialized`



```solidity
    event Initialized(
        address owner_,
        address asset_,
        address pool_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` |  |
| 1 | `asset_` | `address` | `address` |  |
| 2 | `pool_` | `address` | `address` |  |

<br />

