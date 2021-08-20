# Collateral Locker

CollateralLocker holds custody of Collateral Asset for Loans.

## Constructor

```text
  constructor(
    address _collateralAsset,
    address _loan
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_collateralAsset` | `address` | `address` |  |
| 1 | `_loan` | `address` | `address` |  |

## Functions

### collateralAsset \(state variable\)

The address the Collateral Asset the Loan is collateralized with.

```text
  function collateralAsset(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IERC20` |  |

### loan \(state variable\)

The Loan contract address this CollateralLocker is attached to.

```text
  function loan(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### pull

Transfers \`amt\` of Collateral Asset to \`dst\`. Only the Loan can call this function.

```text
  function pull(
    address dst,
    uint256 amt
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `dst` | `address` | `address` | The destination to transfer Collateral Asset to. |
| 1 | `amt` | `uint256` | `uint256` | The amount of Collateral Asset to transfer. |

