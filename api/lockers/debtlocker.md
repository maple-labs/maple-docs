# Debt Locker

DebtLocker holds custody of LoanFDT tokens.

## Constructor

```text
  constructor(
    address _loan,
    address _pool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_loan` | `address` | `address` |  |
| 1 | `_pool` | `address` | `address` |  |

## Functions

### claim

Claims funds distribution for Loan via LoanFDT. Only the Pool can call this function.

```text
  function claim(
  ) nonpayable returns (
    uint256[7]
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256[7]` | `uint256[7]` | \[0\] =&gt; Total Claimed. \[1\] =&gt; Interest Claimed. \[2\] =&gt; Principal Claimed. \[3\] =&gt; Pool Delegate Fee Claimed. \[4\] =&gt; Excess Returned Claimed. \[5\] =&gt; Amount Recovered \(from Liquidation\). \[6\] =&gt; Default Suffered. |

### lastAmountRecovered \(state variable\)

Then Liquidity Asset \(a.k.a. loan asset\) recovered from liquidation of Loan collateral.

```text
  function lastAmountRecovered(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lastDefaultSuffered \(state variable\)

The Loan total default suffered at last time \`claim\(\)\` was called.

```text
  function lastDefaultSuffered(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lastExcessReturned \(state variable\)

The Loan total excess returned at last time \`claim\(\)\` was called.

```text
  function lastExcessReturned(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lastFeePaid \(state variable\)

The Loan total fees paid at last time \`claim\(\)\` was called.

```text
  function lastFeePaid(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lastInterestPaid \(state variable\)

The Loan total interest paid at last time \`claim\(\)\` was called.

```text
  function lastInterestPaid(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lastPrincipalPaid \(state variable\)

The Loan total principal paid at last time \`claim\(\)\` was called.

```text
  function lastPrincipalPaid(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### liquidityAsset \(state variable\)

The Liquidity Asset this locker can claim.

```text
  function liquidityAsset(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IERC20` |  |

### loan \(state variable\)

The Loan contract this locker is holding tokens for.

```text
  function loan(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract ILoan` |  |

### pool \(state variable\)

The owner of this Locker \(the Pool\).

```text
  function pool(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### triggerDefault

Liquidates a Loan that is held by this contract. Only the Pool can call this function.

```text
  function triggerDefault(
  ) nonpayable
```

