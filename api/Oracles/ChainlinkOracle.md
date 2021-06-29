# ChainlinkOracle

ChainlinkOracle is a wrapper contract for Chainlink oracle price feeds that allows for manual price feed overrides.

## Constructor


Creates a new Chainlink based oracle.

```solidity
  constructor(
    address _aggregator,
    address _assetAddress,
    address _owner
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_aggregator` | `address` | `address` | Address of Chainlink aggregator.
| 1 | `_assetAddress` | `address` | `address` | Address of currency (0x0 for ETH).
| 2 | `_owner` | `address` | `address` | Address of the owner of the contract.



## Functions

### assetAddress (state variable)

The address of the asset token contract.

```solidity
  function assetAddress(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### changeAggregator 

Updates the aggregator address to &#x60;aggregator&#x60;. Only the contract Owner can call this function. It emits a &#x60;ChangeAggregatorFeed&#x60; event. 

```solidity
  function changeAggregator(
    address aggregator
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `aggregator` | `address` | `address` | The address of a Chainlink aggregator.


### getAssetAddress 



```solidity
  function getAssetAddress(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | The address of the oracled currency (0x0 for ETH).


### getDenomination 



```solidity
  function getDenomination(
  ) pure returns (
    bytes32
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bytes32` | The denomination of the price.


### getLatestPrice 



```solidity
  function getLatestPrice(
  ) view returns (
    int256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `int256` | The latest price.


### globals (state variable)

The MapleGlobals.

```solidity
  function globals(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### manualOverride (state variable)

Whether the price is manually overridden.

```solidity
  function manualOverride(
  ) view returns (
    bool
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bool` | 


### manualPrice (state variable)

The manually overridden price.

```solidity
  function manualPrice(
  ) view returns (
    int256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `int256` | 


### owner 

Returns the address of the current owner.

```solidity
  function owner(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### priceFeed (state variable)

The Chainlink Aggregator V3 price feed.

```solidity
  function priceFeed(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### renounceOwnership 

Leaves the contract without owner. It will not be possible to call &#x60;onlyOwner&#x60; functions anymore. Can only be called by the current owner. NOTE: Renouncing ownership will leave the contract without an owner, thereby removing any functionality that is only available to the owner.

```solidity
  function renounceOwnership(
  ) nonpayable
```



### setManualOverride 

Sets manual override, allowing for manual price setting. Only the contract Owner can call this function. It emits a &#x60;SetManualOverride&#x60; event. 

```solidity
  function setManualOverride(
    bool _override
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_override` | `bool` | `bool` | Whether manual override price should be used.


### setManualPrice 

Sets a manual price. Only the contract Owner can call this function. This can only be used if manualOverride &#x3D;&#x3D; true. It emits a &#x60;SetManualPrice&#x60; event. 

```solidity
  function setManualPrice(
    int256 _price
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_price` | `int256` | `int256` | Price to set.


### transferOwnership 

Transfers ownership of the contract to a new account (&#x60;newOwner&#x60;). Can only be called by the current owner.

```solidity
  function transferOwnership(
    address newOwner
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newOwner` | `address` | `address` | 



## Events

### ChangeAggregatorFeed

Emits an event indicating that the price feed aggregator has changed from &#x60;_oldMedianizer&#x60; to &#x60;_newMedianizer&#x60;.
```solidity
  event ChangeAggregatorFeed(
    address _newMedianizer,
    address _oldMedianizer
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_newMedianizer` | `address` | `address` | The new price feed aggregator.
| 1 | `_oldMedianizer` | `address` | `address` | The old price feed aggregator.

### OwnershipTransferred


```solidity
  event OwnershipTransferred(
    address previousOwner,
    address newOwner
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousOwner` | `address` | `address` | 
| 1 | `newOwner` | `address` | `address` | 

### SetManualOverride

Emits an event indicating whether manual price overriding is enabled.
```solidity
  event SetManualOverride(
    bool _override
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_override` | `bool` | `bool` | The state of manual price overriding.

### SetManualPrice

Emits an event indicating that the price has been updated manually from &#x60;_oldPrice&#x60; to &#x60;_newPrice&#x60;.
```solidity
  event SetManualPrice(
    int256 _oldPrice,
    int256 _newPrice
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_oldPrice` | `int256` | `int256` | The old price.
| 1 | `_newPrice` | `int256` | `int256` | The new price.

