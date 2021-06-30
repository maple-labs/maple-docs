# FundingLockerFactory

FundingLockerFactory instantiates FundingLockers.


## Functions

### factoryType (state variable)

The type of the factory (i.e FactoryType::FUNDING_LOCKER_FACTORY).

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
| 0 |  | `bool` | `bool` | Whether &#x60;fundingLocker&#x60; is a FundingLocker.


### newLocker 

Instantiates a FundingLocker. It emits a &#x60;FundingLockerCreated&#x60; event. 

```solidity
  function newLocker(
    address liquidityAsset
  ) nonpayable returns (
    address fundingLocker
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityAsset` | `address` | `address` | The Liquidity Asset this FundingLocker will escrow.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundingLocker` | `address` | `address` |  The address of the instantiated FundingLocker.


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
| 0 |  | `address` | `address` | The address of the owner of FundingLocker at &#x60;fundingLocker&#x60;.



## Events

### FundingLockerCreated

Emits an event indicating a FundingLocker was created.
```solidity
  event FundingLockerCreated(
    address owner,
    address fundingLocker,
    address liquidityAsset
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the FundingLocker.
| 1 | `fundingLocker` | `address` | `address` | The address of the FundingLocker.
| 2 | `liquidityAsset` | `address` | `address` | The Liquidity Asset this FundingLocker will escrow.

