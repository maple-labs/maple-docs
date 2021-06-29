# LiquidityLockerFactory

LiquidityLockerFactory instantiates LiquidityLockers.


## Functions

### factoryType (state variable)

The type of the factory (i.e FactoryType::LIQUIDITY_LOCKER_FACTORY).

```solidity
  function factoryType(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint8` | 


### isLocker 



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
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bool` | The address of the owner of LiquidityLocker at &#x60;liquidityLocker&#x60;.


### newLocker 

Instantiates a LiquidityLocker contract.It emits a &#x60;LiquidityLockerCreated&#x60; event.

```solidity
  function newLocker(
    address liquidityAsset
  ) nonpayable returns (
    address liquidityLocker
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityAsset` | `address` | `address` | The Liquidity Asset this LiquidityLocker will escrow.


#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 | `liquidityLocker` | `address` | The address of the instantiated LiquidityLocker.


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
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | The address of the owner of LiquidityLocker at &#x60;liquidityLocker&#x60;.



## Events

### LiquidityLockerCreated

Emits an event indicating a LiquidityLocker was created.
```solidity
  event LiquidityLockerCreated(
    address owner,
    address liquidityLocker,
    address liquidityAsset
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | The owner of the LiquidityLocker.
| 1 | `liquidityLocker` | `address` | `address` | The address of the LiquidityLocker.
| 2 | `liquidityAsset` | `address` | `address` | The Liquidity Asset of the LiquidityLocker.

