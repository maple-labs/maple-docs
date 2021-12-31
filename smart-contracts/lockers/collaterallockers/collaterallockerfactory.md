# CollateralLockerFactory

CollateralLockerFactory instantiates CollateralLockers.

<br />


## Functions

### `factoryType` _[state variable]_

The type of the factory (i.e FactoryType::COLLATERAL_LOCKER_FACTORY).

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

### `isLocker` _[state variable]_



```solidity
    function isLocker(
        address collateralLocker
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralLocker` | `address` | `address` | Some address. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;collateralLocker&#x60; is a CollateralLocker. |


<br />

### `newLocker`

Instantiates a CollateralLocker. It emits a &#x60;CollateralLockerCreated&#x60; event.

```solidity
    function newLocker(
        address collateralAsset
    )
        nonpayable
        returns (
            address collateralLocker
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset` | `address` | `address` | The Collateral Asset this CollateralLocker will escrow. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralLocker` | `address` | `address` | The address of the instantiated CollateralLocker. |


<br />

### `owner` _[state variable]_



```solidity
    function owner(
        address collateralLocker
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralLocker` | `address` | `address` | The address of a CollateralLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The address of the owner of CollateralLocker at &#x60;collateralLocker&#x60;. |


<br />


## Events

### `CollateralLockerCreated`

Emits an event indicating a CollateralLocker was created.

```solidity
    event CollateralLockerCreated(
        address owner,
        address collateralLocker,
        address collateralAsset
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the CollateralLocker. |
| 1 | `collateralLocker` | `address` | `address` | The address of the CollateralLocker. |
| 2 | `collateralAsset` | `address` | `address` | The Collateral Asset of the CollateralLocker. |

<br />

