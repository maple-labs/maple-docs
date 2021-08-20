# LoanFactory

LoanFactory instantiates Loans.

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

### CL\_FACTORY \(state variable\)

The Factory type of \`CollateralLockerFactory\`.

```text
  function CL_FACTORY(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### FL\_FACTORY \(state variable\)

The Factory type of \`FundingLockerFactory\`.

```text
  function FL_FACTORY(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### INTEREST\_CALC\_TYPE \(state variable\)

The Calc type of \`RepaymentCalc\`.

```text
  function INTEREST_CALC_TYPE(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### LATEFEE\_CALC\_TYPE \(state variable\)

The Calc type of \`LateFeeCalc\`.

```text
  function LATEFEE_CALC_TYPE(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### PREMIUM\_CALC\_TYPE \(state variable\)

The Calc type of \`PremiumCalc\`.

```text
  function PREMIUM_CALC_TYPE(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### createLoan

Create a new Loan. It emits a \`LoanCreated\` event.

```text
  function createLoan(
    address liquidityAsset,
    address collateralAsset,
    address flFactory,
    address clFactory,
    uint256[5] specs,
    address[3] calcs
  ) nonpayable returns (
    address loanAddress
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `liquidityAsset` | `address` | `address` | The asset the Loan will raise funding in. |
| 1 | `collateralAsset` | `address` | `address` | The asset the Loan will use as collateral. |
| 2 | `flFactory` | `address` | `address` | The factory to instantiate a FundingLocker from. |
| 3 | `clFactory` | `address` | `address` | The factory to instantiate a CollateralLocker from. |
| 4 | `specs` | `uint256[5]` | `uint256[5]` | The specifications for the Loan.  \[0\] =&gt; apr,  \[1\] =&gt; termDays,  \[2\] =&gt; paymentIntervalDays,  \[3\] =&gt; requestAmount,  \[4\] =&gt; collateralRatio. |
| 5 | `calcs` | `address[3]` | `address[3]` | The calculators used for the Loan.  \[0\] =&gt; repaymentCalc,  \[1\] =&gt; lateFeeCalc,  \[2\] =&gt; premiumCalc. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `loanAddress` | `address` | `address` | Address of the instantiated Loan. |

### globals \(state variable\)

The instance of the MapleGlobals.

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

### isLoan \(state variable\)

```text
  function isLoan(
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
| 0 |  | `bool` | `bool` | Whether \`loan\` is a Loan. |

### loanFactoryAdmins \(state variable\)

```text
  function loanFactoryAdmins(
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
| 0 |  | `bool` | `bool` | Whether \`admin\` has permission to do certain operations in case of disaster management. |

### loans \(state variable\)

```text
  function loans(
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
| 0 |  | `address` | `address` | The address of the Loan at \`index\`. |

### loansCreated \(state variable\)

The incrementor for number of Loans created.

```text
  function loansCreated(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### pause

Triggers paused state. Halts functionality for certain functions. Only the Governor or a LoanFactory Admin can call this function.

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

### setGlobals

Sets MapleGlobals. Only the Governor can call this function.

```text
  function setGlobals(
    address newGlobals
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newGlobals` | `address` | `address` | Address of new MapleGlobals. |

### setLoanFactoryAdmin

Sets a LoanFactory Admin. Only the Governor can call this function.It emits a \`LoanFactoryAdminSet\` event.

```text
  function setLoanFactoryAdmin(
    address loanFactoryAdmin,
    bool allowed
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `loanFactoryAdmin` | `address` | `address` | An address being allowed or disallowed as a LoanFactory Admin. |
| 1 | `allowed` | `bool` | `bool` | The status of \`loanFactoryAdmin\` as an Admin. |

### unpause

Triggers unpaused state. Restores functionality for certain functions. Only the Governor or a LoanFactory Admin can call this function.

```text
  function unpause(
  ) nonpayable
```

## Events

### LoanCreated

Emits an event indicating a Loan was created.

```text
  event LoanCreated(
    address loan,
    address borrower,
    address liquidityAsset,
    address collateralAsset,
    address collateralLocker,
    address fundingLocker,
    uint256[5] specs,
    address[3] calcs,
    string name,
    string symbol
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `loan` | `address` | `address` | The address of the Loan. |
| 1 | `borrower` | `address` | `address` | The Borrower. |
| 2 | `liquidityAsset` | `address` | `address` | The asset the Loan will raise funding in. |
| 3 | `collateralAsset` | `address` | `address` | The asset the Loan will use as collateral. |
| 4 | `collateralLocker` | `address` | `address` | The address of the Collateral Locker. |
| 5 | `fundingLocker` | `address` | `address` | The address of the Funding Locker. |
| 6 | `specs` | `uint256[5]` | `uint256[5]` | The specifications for the Loan.  \[0\] =&gt; apr,  \[1\] =&gt; termDays,  \[2\] =&gt; paymentIntervalDays,  \[3\] =&gt; requestAmount,  \[4\] =&gt; collateralRatio. |
| 7 | `calcs` | `address[3]` | `address[3]` | The calculators used for the Loan.  \[0\] =&gt; repaymentCalc,  \[1\] =&gt; lateFeeCalc,  \[2\] =&gt; premiumCalc. |
| 8 | `name` | `string` | `string` | The name of the Loan FDTs. |
| 9 | `symbol` | `string` | `string` | The symbol of the Loan FDTs. |

### LoanFactoryAdminSet

Emits an event indicating a LoanFactoryAdmin was allowed.

```text
  event LoanFactoryAdminSet(
    address loanFactoryAdmin,
    bool allowed
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `loanFactoryAdmin` | `address` | `address` | The address of a LoanFactoryAdmin. |
| 1 | `allowed` | `bool` | `bool` | Whether \`loanFactoryAdmin\` is allowed as an admin of the LoanFactory. |

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

