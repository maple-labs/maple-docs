# MapleAaveStrategyInitializer



<br />


## Functions

### `aavePool` 

Returns the address of the Aave pool.

```solidity
    function aavePool()
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

### `aaveToken` 

Returns the address of the Aave token.

```solidity
    function aaveToken()
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

### `fundsAsset` 

Returns the address of the underlying asset.

```solidity
    function fundsAsset()
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

### `lastRecordedTotalAssets` 

Returns the last recorded value of all assets managed by the strategy.

```solidity
    function lastRecordedTotalAssets()
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

### `locked` 



```solidity
    function locked()
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

### `pool` 

Returns the address of the underlying asset.

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

Returns the address of the Maple pool manager.

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

### `strategyFeeRate` 

Returns the percentage of the strategy&#x27;s yield collected by the Maple treasury.

```solidity
    function strategyFeeRate()
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

### `strategyState` 

Returns the current state of the strategy.          Can be active, inactive, or impaired.

```solidity
    function strategyState()
        view
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `enum StrategyState` |  |


<br />


## Events

### `Initialized`

Emitted when the proxy contract is initialized.

```solidity
    event Initialized(
        address aavePool,
        address aaveToken,
        address pool,
        address fundsAsset,
        address poolManager
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `aavePool` | `address` | `address` | Address of the Aave pool. |
| 1 | `aaveToken` | `address` | `address` | Address of the Aave token. |
| 2 | `pool` | `address` | `address` | Address of the Maple pool. |
| 3 | `fundsAsset` | `address` | `address` | Address of the underlying asset. |
| 4 | `poolManager` | `address` | `address` | Address of the Maple pool manager. |

<br />

