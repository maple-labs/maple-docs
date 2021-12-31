# FundingLockerFactory

FundingLockerFactory instantiates FundingLockers.

<br />


## Functions

### `factoryType` _[state variable]_

The type of the factory (i.e FactoryType::FUNDING_LOCKER_FACTORY).

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
        address fundingLocker
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundingLocker` | `address` | `address` | Some address. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;fundingLocker&#x60; is a FundingLocker. |


<br />

### `newLocker`

Instantiates a FundingLocker. It emits a &#x60;FundingLockerCreated&#x60; event.

```solidity
    function newLocker(
        address liquidityAsset
    )
        nonpayable
        returns (
            address fundingLocker
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityAsset` | `address` | `address` | The Liquidity Asset this FundingLocker will escrow. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundingLocker` | `address` | `address` |  The address of the instantiated FundingLocker. |


<br />

### `owner` _[state variable]_



```solidity
    function owner(
        address fundingLocker
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundingLocker` | `address` | `address` | The address of a FundingLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The address of the owner of FundingLocker at &#x60;fundingLocker&#x60;. |


<br />


## Events

### `FundingLockerCreated`

Emits an event indicating a FundingLocker was created.

```solidity
    event FundingLockerCreated(
        address owner,
        address fundingLocker,
        address liquidityAsset
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the FundingLocker. |
| 1 | `fundingLocker` | `address` | `address` | The address of the FundingLocker. |
| 2 | `liquidityAsset` | `address` | `address` | The Liquidity Asset this FundingLocker will escrow. |

<br />

