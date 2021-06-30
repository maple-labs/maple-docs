# DebtLockerFactory

DebtLockerFactory instantiates DebtLockers.


## Functions

### factoryType (state variable)

The type of the factory (i.e FactoryType::DEBT_LOCKER_FACTORY).

```solidity
  function factoryType(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` | 


### isLocker (state variable)



```solidity
  function isLocker(
    address
  ) view returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;debtLocker&#x60; is a DebtLocker.


### newLocker 

Instantiates a DebtLocker. It emits a &#x60;DebtLockerCreated&#x60; event. 

```solidity
  function newLocker(
    address loan
  ) nonpayable returns (
    address debtLocker
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The Loan this DebtLocker will be tied to.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `debtLocker` | `address` | `address` | The address of the instantiated DebtLocker.


### owner (state variable)



```solidity
  function owner(
    address
  ) view returns (
    address
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The address of the owner of DebtLocker at &#x60;debtLocker&#x60;.



## Events

### DebtLockerCreated

Emits an event indicating a DebtLocker was created.
```solidity
  event DebtLockerCreated(
    address owner,
    address debtLocker,
    address loan
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the DebtLocker.
| 1 | `debtLocker` | `address` | `address` | The address of the DebtLocker.
| 2 | `loan` | `address` | `address` | The Loan tied to the DebtLocker.

