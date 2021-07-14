# Pool

Util is a library that contains utility functions.

## Functions

### calcMinAmount

Calculates the minimum amount from a swap \(adjustable for price slippage\).

```text
  function calcMinAmount(
    IMapleGlobals globals,
    address fromAsset,
    address toAsset,
    uint256 swapAmt
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `globals` | `IMapleGlobals` | `contract IMapleGlobals` | The instance of a MapleGlobals. |
| 1 | `fromAsset` | `address` | `address` | The address of ERC-20 that will be swapped. |
| 2 | `toAsset` | `address` | `address` | The address of ERC-20 that will returned from swap. |
| 3 | `swapAmt` | `uint256` | `uint256` | The amount of \`fromAsset\` to be swapped. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The expected amount of \`toAsset\` to receive from swap based on current oracle prices. |

