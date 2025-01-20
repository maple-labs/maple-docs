# MapleSkyStrategyInitializer



<br />


## Functions

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

Gets the last recorded total assets.

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

### `psm` 

Returns the address of the PSM contract.

```solidity
    function psm()
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

### `savingsUsds` 

Returns the address of the savings USDS contract.

```solidity
    function savingsUsds()
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

Returns the strategy fee rate.

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

### `usds` 

Returns the address of the USDS contract.

```solidity
    function usds()
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

Emitted when the proxy contract is initialized.Only 3 parameters can be indexed.

```solidity
    event Initialized(
        address pool,
        address poolManager,
        address psm,
        address savingsUsds,
        address usds
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool` | `address` | `address` | Address of the pool contract. |
| 1 | `poolManager` | `address` | `address` | Address of the pool manager contract. |
| 2 | `psm` | `address` | `address` | Address of the psm contract. |
| 3 | `savingsUsds` | `address` | `address` | Address of the savings usds contract. |
| 4 | `usds` | `address` | `address` | Address of the usds contract. |

<br />

