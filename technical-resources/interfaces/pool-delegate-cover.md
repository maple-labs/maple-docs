# PoolDelegateCover



<br />

## Constructor




```solidity
    constructor(
        address poolManager_,
        address asset_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |  |
| 1 | `asset_` | `address` | `address` |  |


<br />


## Functions

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

### `moveFunds` 

Move funds from this address to another.

```solidity
    function moveFunds(
        uint256 amount_,
        address recipient_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount to move. |
| 1 | `recipient_` | `address` | `address` | The address of the recipient. |


<br />

### `poolManager` 

Gets the address of the pool manager.

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



