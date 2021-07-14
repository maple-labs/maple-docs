# Treasury

MapleTreasury earns revenue from Loans and distributes it to token holders and the Maple development team.

## Constructor

Instantiates the MapleTreasury contract.

```text
  constructor(
    address _mpl,
    address _fundsToken,
    address _uniswapRouter,
    address _globals
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_mpl` | `address` | `address` | The address of ERC-2222 Maple Token for the Maple protocol. |
| 1 | `_fundsToken` | `address` | `address` | The address of the \`fundsToken\` of the ERC-2222 Maple Token. |
| 2 | `_uniswapRouter` | `address` | `address` | The address of the official UniswapV2 router. |
| 3 | `_globals` | `address` | `address` | The address of an instance of MapleGlobals. |

## Functions

### convertERC20

Converts an ERC-20 asset, via Uniswap, to \`fundsToken\`. Only the Governor can call this function. It emits a \`ERC20Conversion\` event.

```text
  function convertERC20(
    address asset
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `asset` | `address` | `address` | The ERC-20 asset to convert to \`fundsToken\`. |

### distributeToHolders

Passes through the current \`fundsToken\` balance of the Treasury to Maple Token, where it can be claimed by MPL holders. Only the Governor can call this function. It emits a \`DistributedToHolders\` event.

```text
  function distributeToHolders(
  ) nonpayable
```

### fundsToken \(state variable\)

The address of the \`fundsToken\` of the ERC-2222 Maple Token.

```text
  function fundsToken(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### globals \(state variable\)

The address of an instance of MapleGlobals.

```text
  function globals(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### mpl \(state variable\)

The address of ERC-2222 Maple Token for the Maple protocol.

```text
  function mpl(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### reclaimERC20

Reclaims Treasury funds to the Governor. Only the Governor can call this function. It emits a \`ERC20Reclaimed\` event.

```text
  function reclaimERC20(
    address asset,
    uint256 amount
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `asset` | `address` | `address` | The address of the token to be reclaimed. |
| 1 | `amount` | `uint256` | `uint256` | The amount reclaimed. |

### setGlobals

Updates the MapleGlobals instance. Only the Governor can call this function. It emits a \`GlobalsSet\` event.

```text
  function setGlobals(
    address newGlobals
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newGlobals` | `address` | `address` | The address of a new MapleGlobals instance. |

### uniswapRouter \(state variable\)

The address of the official UniswapV2 router.

```text
  function uniswapRouter(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

## Events

### DistributedToHolders

Emits an event indicating that a distribution was made to token holders.

```text
  event DistributedToHolders(
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `amount` | `uint256` | `uint256` | The amount distributed to token holders. |

### ERC20Conversion

Emits an event indicating that an amount of some asset was converted to \`fundsToken\`.

```text
  event ERC20Conversion(
    address asset,
    uint256 amountIn,
    uint256 amountOut
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `asset` | `address` | `address` | The ERC-20 asset to convert to \`fundsToken\`. |
| 1 | `amountIn` | `uint256` | `uint256` | The amount of the asset being converted to \`fundsToken\`. |
| 2 | `amountOut` | `uint256` | `uint256` | The amount of \`fundsToken\` received from the conversion. |

### ERC20Reclaimed

Emits an event indicating the Governor reclaimed some token.

```text
  event ERC20Reclaimed(
    address asset,
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `asset` | `address` | `address` | The address of the token to reclaimed. |
| 1 | `amount` | `uint256` | `uint256` | The amount reclaimed. |

### GlobalsSet

Emits an event indicating the MapleGlobals instance has changed.

```text
  event GlobalsSet(
    address newGlobals
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newGlobals` | `address` | `address` | The address of a new MapleGlobals. |

