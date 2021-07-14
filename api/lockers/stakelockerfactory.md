# Stake Locker Factory

StakeLockerFactory instantiates StakeLockers.

## Functions

### factoryType \(state variable\)

The type of the factory \(i.e FactoryType::STAKE\_LOCKER\_FACTORY\).

```text
  function factoryType(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### isLocker \(state variable\)

```text
  function isLocker(
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
| 0 |  | `bool` | `bool` | Whether \`stakeLocker\` is a StakeLocker. |

### newLocker

Instantiate a StakeLocker.It emits a \`StakeLockerCreated\` event.

```text
  function newLocker(
    address stakeAsset,
    address liquidityAsset
  ) nonpayable returns (
    address stakeLocker
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `stakeAsset` | `address` | `address` | The address of the Stake Asset \(generally Balancer Pool BPTs\). |
| 1 | `liquidityAsset` | `address` | `address` | The address of the Liquidity Asset \(as defined in the Pool\). |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `stakeLocker` | `address` | `address` | The address of the instantiated StakeLocker. |

### owner \(state variable\)

```text
  function owner(
    address
  ) view returns (
    address
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` | The address of the owner of StakeLocker at \`stakeLocker\`. |

## Events

### StakeLockerCreated

Emits an event indicating a StakeLocker was created.

```text
  event StakeLockerCreated(
    address owner,
    address stakeLocker,
    address stakeAsset,
    address liquidityAsset,
    string name,
    string symbol
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `owner` | `address` | `address` | The owner of the StakeLocker. |
| 1 | `stakeLocker` | `address` | `address` | The address of the StakeLocker. |
| 2 | `stakeAsset` | `address` | `address` | The Stake Asset this StakeLocker will escrow. |
| 3 | `liquidityAsset` | `address` | `address` | The address of the Liquidity Asset \(as defined in the Pool\). |
| 4 | `name` | `string` | `string` | The name of the StakeLockerFDTs. |
| 5 | `symbol` | `string` | `string` | The symbol of the StakeLockerFDTs. |

