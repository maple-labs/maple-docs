# LiquidityLockerFactory

LiquidityLockerFactory instantiates LiquidityLockers.

<br />


## Functions

### `factoryType` _[state variable]_

The type of the factory (i.e FactoryType::LIQUIDITY_LOCKER_FACTORY).

```solidity
    function factoryType()
        pure
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` |  |


<br />

### `isLocker`



```solidity
    function isLocker(
        address liquidityLocker
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityLocker` | `address` | `address` | The address of a LiquidityLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | The address of the owner of LiquidityLocker at &#x60;liquidityLocker&#x60;. |


<br />

### `newLocker`

Instantiates a LiquidityLocker contract.It emits a &#x60;LiquidityLockerCreated&#x60; event.

```solidity
    function newLocker(
        address liquidityAsset
    )
        nonpayable
        returns (
            address liquidityLocker
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityAsset` | `address` | `address` | The Liquidity Asset this LiquidityLocker will escrow. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityLocker` | `address` | `address` | The address of the instantiated LiquidityLocker. |


<br />

### `owner` _[state variable]_



```solidity
    function owner(
        address liquidityLocker
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityLocker` | `address` | `address` | The address of a LiquidityLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The address of the owner of LiquidityLocker at &#x60;liquidityLocker&#x60;. |


<br />


## Events

### `LiquidityLockerCreated`

Emits an event indicating a LiquidityLocker was created.

```solidity
    event LiquidityLockerCreated(
        address owner,
        address liquidityLocker,
        address liquidityAsset
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the LiquidityLocker. |
| 1 | `liquidityLocker` | `address` | `address` | The address of the LiquidityLocker. |
| 2 | `liquidityAsset` | `address` | `address` | The Liquidity Asset of the LiquidityLocker. |

<br />

