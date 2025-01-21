# MapleBasicStrategyInitializer



<br />


## Functions

### `fundsAsset` 

Gets the address of the funds asset.

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

### `strategyVault` 

Returns the address of the ERC4626 compliant Vault.

```solidity
    function strategyVault()
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

Emitted when the proxy contract is initialized.

```solidity
    event Initialized(
        address pool,
        address poolManager,
        address strategyVault
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool` | `address` | `address` | Address of the pool contract. |
| 1 | `poolManager` | `address` | `address` | Address of the pool manager contract. |
| 2 | `strategyVault` | `address` | `address` | Address of the ERC4626 compliant Vault. |

<br />

