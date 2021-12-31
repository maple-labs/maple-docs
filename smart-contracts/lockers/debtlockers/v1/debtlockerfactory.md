# DebtLockerFactory

DebtLockerFactory instantiates DebtLockers.

<br />


## Functions

### `factoryType` _[state variable]_

The type of the factory (i.e FactoryType::DEBT_LOCKER_FACTORY).

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
        address debtLocker
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `debtLocker` | `address` | `address` | Some address. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;debtLocker&#x60; is a DebtLocker. |


<br />

### `newLocker`

Instantiates a DebtLocker. It emits a &#x60;DebtLockerCreated&#x60; event.

```solidity
    function newLocker(
        address loan
    )
        nonpayable
        returns (
            address debtLocker
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The Loan this DebtLocker will be tied to. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `debtLocker` | `address` | `address` | The address of the instantiated DebtLocker. |


<br />

### `owner` _[state variable]_



```solidity
    function owner(
        address debtLocker
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `debtLocker` | `address` | `address` | The address of a DebtLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The address of the owner of DebtLocker at &#x60;debtLocker&#x60;. |


<br />


## Events

### `DebtLockerCreated`

Emits an event indicating a DebtLocker was created.

```solidity
    event DebtLockerCreated(
        address owner,
        address debtLocker,
        address loan
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the DebtLocker. |
| 1 | `debtLocker` | `address` | `address` | The address of the DebtLocker. |
| 2 | `loan` | `address` | `address` | The Loan tied to the DebtLocker. |

<br />

