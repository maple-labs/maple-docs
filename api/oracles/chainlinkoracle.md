# Chainlink Oracle

ChainlinkOracle is a wrapper contract for Chainlink oracle price feeds that allows for manual price feed overrides.

## Constructor

Creates a new Chainlink based oracle.

```text
  constructor(
    address _aggregator,
    address _assetAddress,
    address _owner
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_aggregator` | `address` | `address` | Address of Chainlink aggregator. |
| 1 | `_assetAddress` | `address` | `address` | Address of currency \(0x0 for ETH\). |
| 2 | `_owner` | `address` | `address` | Address of the owner of the contract. |

## Functions

### assetAddress \(state variable\)

The address of the asset token contract.

```text
  function assetAddress(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### changeAggregator

Updates the aggregator address to \`aggregator\`. Only the contract Owner can call this function. It emits a \`ChangeAggregatorFeed\` event.

```text
  function changeAggregator(
    address aggregator
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `aggregator` | `address` | `address` | The address of a Chainlink aggregator. |

### getAssetAddress

```text
  function getAssetAddress(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` | The address of the oracled currency \(0x0 for ETH\). |

### getDenomination

```text
  function getDenomination(
  ) pure returns (
    bytes32
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bytes32` | `bytes32` | The denomination of the price. |

### getLatestPrice

```text
  function getLatestPrice(
  ) view returns (
    int256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `int256` | `int256` | The latest price. |

### globals \(state variable\)

The MapleGlobals.

```text
  function globals(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IMapleGlobals` |  |

### manualOverride \(state variable\)

Whether the price is manually overridden.

```text
  function manualOverride(
  ) view returns (
    bool
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### manualPrice \(state variable\)

The manually overridden price.

```text
  function manualPrice(
  ) view returns (
    int256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `int256` | `int256` |  |

### owner

Returns the address of the current owner.

```text
  function owner(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### priceFeed \(state variable\)

The Chainlink Aggregator V3 price feed.

```text
  function priceFeed(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IChainlinkAggregatorV3` |  |

### renounceOwnership

Leaves the contract without owner. It will not be possible to call \`onlyOwner\` functions anymore. Can only be called by the current owner. NOTE: Renouncing ownership will leave the contract without an owner, thereby removing any functionality that is only available to the owner.

```text
  function renounceOwnership(
  ) nonpayable
```

### setManualOverride

Sets manual override, allowing for manual price setting. Only the contract Owner can call this function. It emits a \`SetManualOverride\` event.

```text
  function setManualOverride(
    bool _override
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_override` | `bool` | `bool` | Whether manual override price should be used. |

### setManualPrice

Sets a manual price. Only the contract Owner can call this function. This can only be used if manualOverride == true. It emits a \`SetManualPrice\` event.

```text
  function setManualPrice(
    int256 _price
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_price` | `int256` | `int256` | Price to set. |

### transferOwnership

Transfers ownership of the contract to a new account \(\`newOwner\`\). Can only be called by the current owner.

```text
  function transferOwnership(
    address newOwner
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newOwner` | `address` | `address` |  |

## Events

### ChangeAggregatorFeed

Emits an event indicating that the price feed aggregator has changed from \`\_oldMedianizer\` to \`\_newMedianizer\`.

```text
  event ChangeAggregatorFeed(
    address _newMedianizer,
    address _oldMedianizer
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_newMedianizer` | `address` | `address` | The new price feed aggregator. |
| 1 | `_oldMedianizer` | `address` | `address` | The old price feed aggregator. |

### OwnershipTransferred

```text
  event OwnershipTransferred(
    address previousOwner,
    address newOwner
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `previousOwner` | `address` | `address` |  |
| 1 | `newOwner` | `address` | `address` |  |

### SetManualOverride

Emits an event indicating whether manual price overriding is enabled.

```text
  event SetManualOverride(
    bool _override
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_override` | `bool` | `bool` | The state of manual price overriding. |

### SetManualPrice

Emits an event indicating that the price has been updated manually from \`\_oldPrice\` to \`\_newPrice\`.

```text
  event SetManualPrice(
    int256 _oldPrice,
    int256 _newPrice
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_oldPrice` | `int256` | `int256` | The old price. |
| 1 | `_newPrice` | `int256` | `int256` | The new price. |

