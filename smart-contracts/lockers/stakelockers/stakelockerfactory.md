# StakeLockerFactory

StakeLockerFactory instantiates StakeLockers.

<br />


## Functions

### `factoryType` _[state variable]_

The type of the factory (i.e FactoryType::STAKE_LOCKER_FACTORY).

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
        address stakeLocker
    )
        nonpayable
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `stakeLocker` | `address` | `address` | Some address. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;stakeLocker&#x60; is a StakeLocker. |


<br />

### `newLocker`

Instantiate a StakeLocker.It emits a &#x60;StakeLockerCreated&#x60; event.

```solidity
    function newLocker(
        address stakeAsset,
        address liquidityAsset
    )
        nonpayable
        returns (
            address stakeLocker
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `stakeAsset` | `address` | `address` | The address of the Stake Asset (generally Balancer Pool BPTs). |
| 1 | `liquidityAsset` | `address` | `address` | The address of the Liquidity Asset (as defined in the Pool). |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `stakeLocker` | `address` | `address` |    The address of the instantiated StakeLocker. |


<br />

### `owner` _[state variable]_



```solidity
    function owner(
        address stakeLocker
    )
        nonpayable
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `stakeLocker` | `address` | `address` | The address of a StakeLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The address of the owner of StakeLocker at &#x60;stakeLocker&#x60;. |


<br />


## Events

### `StakeLockerCreated`

Emits an event indicating a StakeLocker was created.

```solidity
    event StakeLockerCreated(
        address owner,
        address stakeLocker,
        address stakeAsset,
        address liquidityAsset,
        string name,
        string symbol
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the StakeLocker. |
| 1 | `stakeLocker` | `address` | `address` | The address of the StakeLocker. |
| 2 | `stakeAsset` | `address` | `address` | The Stake Asset this StakeLocker will escrow. |
| 3 | `liquidityAsset` | `address` | `address` | The address of the Liquidity Asset (as defined in the Pool). |
| 4 | `name` | `string` | `string` | The name of the StakeLockerFDTs. |
| 5 | `symbol` | `string` | `string` | The symbol of the StakeLockerFDTs. |

<br />

