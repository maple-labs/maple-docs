# PoolFactory

PoolFactory instantiates Pools.

## Constructor

```text
  constructor(
    address _globals
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_globals` | `address` | `address` |  |

## Functions

### LL\_FACTORY \(state variable\)

The factory type of \`LiquidityLockerFactory\`.

```text
  function LL_FACTORY(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### SL\_FACTORY \(state variable\)

The factory type of \`StakeLockerFactory\`.

```text
  function SL_FACTORY(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### createPool

Instantiates a Pool. It emits a \`PoolCreated\` event.

```text
  function createPool(
    address liquidityAsset,
    address stakeAsset,
    address slFactory,
    address llFactory,
    uint256 stakingFee,
    uint256 delegateFee,
    uint256 liquidityCap
  ) nonpayable returns (
    address poolAddress
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `liquidityAsset` | `address` | `address` | The asset escrowed in a LiquidityLocker. |
| 1 | `stakeAsset` | `address` | `address` | The asset escrowed in a StakeLocker. |
| 2 | `slFactory` | `address` | `address` | The factory to instantiate a StakeLocker from. |
| 3 | `llFactory` | `address` | `address` | The factory to instantiate a LiquidityLocker from. |
| 4 | `stakingFee` | `uint256` | `uint256` | The fee that Stakers earn on interest, in basis points. |
| 5 | `delegateFee` | `uint256` | `uint256` | The fee that the Pool Delegate earns on interest, in basis points. |
| 6 | `liquidityCap` | `uint256` | `uint256` | The amount of Liquidity Asset accepted by the Pool. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `poolAddress` | `address` | `address` | The address of the instantiated Pool. |

### globals \(state variable\)

The current MapleGlobals instance.

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

### isPool \(state variable\)

```text
  function isPool(
    address
  ) view returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` | Whether the contract at \`address\` is a Pool. |

### pause

Triggers paused state. Halts functionality for certain functions. Only the Governor or a PoolFactory Admin can call this function.

```text
  function pause(
  ) nonpayable
```

### paused

Returns true if the contract is paused, and false otherwise.

```text
  function paused(
  ) view returns (
    bool
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### poolFactoryAdmins \(state variable\)

```text
  function poolFactoryAdmins(
    address
  ) view returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` | Whether the \`poolFactoryAdmin\` has permission to do certain operations in case of disaster management |

### pools \(state variable\)

```text
  function pools(
    uint256
  ) view returns (
    address
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` | The address of the Pool at \`index\`. |

### poolsCreated \(state variable\)

The incrementor for number of Pools created.

```text
  function poolsCreated(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### setGlobals

Sets MapleGlobals instance. Only the Governor can call this function.

```text
  function setGlobals(
    address newGlobals
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newGlobals` | `address` | `address` | The address of new MapleGlobals. |

### setPoolFactoryAdmin

Sets a PoolFactory Admin. Only the Governor can call this function. It emits a \`PoolFactoryAdminSet\` event.

```text
  function setPoolFactoryAdmin(
    address poolFactoryAdmin,
    bool allowed
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `poolFactoryAdmin` | `address` | `address` | An address being allowed or disallowed as a PoolFactory Admin. |
| 1 | `allowed` | `bool` | `bool` | Whether \`poolFactoryAdmin\` is allowed as a PoolFactory Admin. |

### unpause

Triggers unpaused state. Restores functionality for certain functions. Only the Governor or a PoolFactory Admin can call this function.

```text
  function unpause(
  ) nonpayable
```

## Events

### Paused

```text
  event Paused(
    address account
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` |  |

### PoolCreated

Emits an event indicating a Pool was created.

```text
  event PoolCreated(
    address pool,
    address delegate,
    address liquidityAsset,
    address stakeAsset,
    address liquidityLocker,
    address stakeLocker,
    uint256 stakingFee,
    uint256 delegateFee,
    uint256 liquidityCap,
    string name,
    string symbol
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `pool` | `address` | `address` | The address of the Pool. |
| 1 | `delegate` | `address` | `address` | The PoolDelegate. |
| 2 | `liquidityAsset` | `address` | `address` | The asset Loans will be funded in. |
| 3 | `stakeAsset` | `address` | `address` | The asset stake will be locked in. |
| 4 | `liquidityLocker` | `address` | `address` | The address of the LiquidityLocker. |
| 5 | `stakeLocker` | `address` | `address` | The address of the StakeLocker. |
| 6 | `stakingFee` | `uint256` | `uint256` | The fee paid to the Pool Delegate on Loans. |
| 7 | `delegateFee` | `uint256` | `uint256` |  |
| 8 | `liquidityCap` | `uint256` | `uint256` | The maximum liquidity the Pool will hold. |
| 9 | `name` | `string` | `string` | The name of the Pool FDTs. |
| 10 | `symbol` | `string` | `string` | The symbol of the Pool FDTs. |

### PoolFactoryAdminSet

Emits an event indicating a PoolFactoryAdmin was allowed.

```text
  event PoolFactoryAdminSet(
    address poolFactoryAdmin,
    bool allowed
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `poolFactoryAdmin` | `address` | `address` | The address of a PoolFactoryAdmin. |
| 1 | `allowed` | `bool` | `bool` | Whether \`poolFactoryAdmin\` is allowed as an admin of the PoolFactory. |

### Unpaused

```text
  event Unpaused(
    address account
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` |  |

