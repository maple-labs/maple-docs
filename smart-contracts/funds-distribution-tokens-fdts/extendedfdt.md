# Extended FDT

ExtendedFDT implements the FDT functionality for accounting for losses.

## Constructor

```text
  constructor(
    string name,
    string symbol
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `name` | `string` | `string` |  |
| 1 | `symbol` | `string` | `string` |  |

## Functions

### accumulativeFundsOf

Returns the amount of funds that an account has earned in total. accumulativeFundsOf\(\_owner\) = withdrawableFundsOf\(\_owner\) + withdrawnFundsOf\(\_owner\) = \(pointsPerShare \* balanceOf\(\_owner\) + pointsCorrection\[\_owner\]\) / pointsMultiplier

```text
  function accumulativeFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of funds that \`\_owner\` has earned in total. |

### accumulativeLossesOf

Returns the amount of losses that an account has earned in total. accumulativeLossesOf\(\_owner\) = recognizableLossesOf\(\_owner\) + recognizedLossesOf\(\_owner\) = \(lossesPerShare \* balanceOf\(\_owner\) + lossesCorrection\[\_owner\]\) / pointsMultiplier

```text
  function accumulativeLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of losses that \`\_owner\` has earned in total. |

### allowance

Returns the remaining number of tokens that \`spender\` will be allowed to spend on behalf of \`owner\` through {transferFrom}. This is zero by default. This value changes when {approve} or {transferFrom} are called.

```text
  function allowance(
    address owner,
    address spender
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `owner` | `address` | `address` |  |
| 1 | `spender` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### approve

Sets \`amount\` as the allowance of \`spender\` over the caller's tokens. Returns a boolean value indicating whether the operation succeeded. IMPORTANT: Beware that changing an allowance with this method brings the risk that someone may use both the old and the new allowance by unfortunate transaction ordering. One possible solution to mitigate this race condition is to first reduce the spender's allowance to 0 and set the desired value afterwards: [https://github.com/ethereum/EIPs/issues/20\#issuecomment-263524729](https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729) Emits an {Approval} event.

```text
  function approve(
    address spender,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `amount` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### balanceOf

Returns the amount of tokens owned by \`account\`.

```text
  function balanceOf(
    address account
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### decimals

Returns the number of decimals used to get its user representation. For example, if \`decimals\` equals \`2\`, a balance of \`505\` tokens should be displayed to a user as \`5,05\` \(\`505 / 10 \*\* 2\`\). Tokens usually opt for a value of 18, imitating the relationship between Ether and Wei. This is the value {ERC20} uses, unless {_setupDecimals} is called. NOTE: This information is only used for \_display_ purposes: it in no way affects any of the arithmetic of the contract, including {IERC20-balanceOf} and {IERC20-transfer}.

```text
  function decimals(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### decreaseAllowance

Atomically decreases the allowance granted to \`spender\` by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - \`spender\` cannot be the zero address. - \`spender\` must have allowance for the caller of at least \`subtractedValue\`.

```text
  function decreaseAllowance(
    address spender,
    uint256 subtractedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `subtractedValue` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### increaseAllowance

Atomically increases the allowance granted to \`spender\` by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - \`spender\` cannot be the zero address.

```text
  function increaseAllowance(
    address spender,
    uint256 addedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `addedValue` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### name

Returns the name of the token.

```text
  function name(
  ) view returns (
    string
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `string` | `string` |  |

### recognizableLossesOf

Returns the amount of losses that an account can withdraw.

```text
  function recognizableLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of losses that \`\_owner\` can withdraw. |

### recognizedLossesOf

Returns the amount of losses that an account has recognized.

```text
  function recognizedLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of losses that \`\_owner\` has recognized. |

### symbol

Returns the symbol of the token, usually a shorter version of the name.

```text
  function symbol(
  ) view returns (
    string
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `string` | `string` |  |

### totalSupply

Returns the amount of tokens in existence.

```text
  function totalSupply(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### transfer

Moves \`amount\` tokens from the caller's account to \`recipient\`. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```text
  function transfer(
    address recipient,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `recipient` | `address` | `address` |  |
| 1 | `amount` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### transferFrom

Moves \`amount\` tokens from \`sender\` to \`recipient\` using the allowance mechanism. \`amount\` is then deducted from the caller's allowance. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```text
  function transferFrom(
    address sender,
    address recipient,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `sender` | `address` | `address` |  |
| 1 | `recipient` | `address` | `address` |  |
| 2 | `amount` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### updateFundsReceived

Registers a payment of funds in tokens. May be called directly after a deposit is made. Calls \_updateFundsTokenBalance\(\), whereby the contract computes the delta of the new and previous \`fundsToken\` balance and increments the total received funds \(cumulative\), by delta, by calling \_distributeFunds\(\).

```text
  function updateFundsReceived(
  ) nonpayable
```

### updateLossesReceived

Registers a loss. May be called directly after a shortfall after BPT burning occurs. Calls \_updateLossesTokenBalance\(\), whereby the contract computes the delta of the new and previous losses balance and increments the total losses \(cumulative\), by delta, by calling \_distributeLosses\(\).

```text
  function updateLossesReceived(
  ) nonpayable
```

### withdrawFunds

Withdraws all available funds for the calling FDT holder.

```text
  function withdrawFunds(
  ) nonpayable
```

### withdrawableFundsOf

Returns the amount of funds that an account can withdraw.

```text
  function withdrawableFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of some FDT holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount funds that \`\_owner\` can withdraw. |

### withdrawnFundsOf

Returns the amount of funds that an account has withdrawn.

```text
  function withdrawnFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of funds that \`\_owner\` has withdrawn. |

## Events

### Approval

```text
  event Approval(
    address owner,
    address spender,
    uint256 value
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `owner` | `address` | `address` |  |
| 1 | `spender` | `address` | `address` |  |
| 2 | `value` | `uint256` | `uint256` |  |

### FundsDistributed

```text
  event FundsDistributed(
    address by,
    uint256 fundsDistributed
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `by` | `address` | `address` |  |
| 1 | `fundsDistributed` | `uint256` | `uint256` |  |

### FundsWithdrawn

```text
  event FundsWithdrawn(
    address by,
    uint256 fundsWithdrawn,
    uint256 totalWithdrawn
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `by` | `address` | `address` |  |
| 1 | `fundsWithdrawn` | `uint256` | `uint256` |  |
| 2 | `totalWithdrawn` | `uint256` | `uint256` |  |

### LossesCorrectionUpdated

This event emits when an account's \`lossesCorrection\` is updated.First parameter is the address of some account.Second parameter is the new value of the account's \`lossesCorrection\`.

```text
  event LossesCorrectionUpdated(
    address ,
    int256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `int256` | `int256` |  |

### LossesDistributed

This event emits when new losses are distributed.First parameter is the address of the account that has distributed losses.Second parameter is the amount of losses received for distribution.

```text
  event LossesDistributed(
    address ,
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `uint256` | `uint256` |  |

### LossesPerShareUpdated

This event emits when the internal \`lossesPerShare\` is updated.First, and only, parameter is the new value of the internal \`lossesPerShare\`.

```text
  event LossesPerShareUpdated(
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `uint256` | `uint256` |  |

### LossesRecognized

This event emits when distributed losses are recognized by a token holder.First parameter is the address of the receiver of losses.Second parameter is the amount of losses that were recognized.Third parameter is the total amount of losses that are recognized.

```text
  event LossesRecognized(
    address ,
    uint256 ,
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `uint256` | `uint256` |  |
| 2 | \`\` | `uint256` | `uint256` |  |

### PointsCorrectionUpdated

```text
  event PointsCorrectionUpdated(
    address ,
    int256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `int256` | `int256` |  |

### PointsPerShareUpdated

```text
  event PointsPerShareUpdated(
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `uint256` | `uint256` |  |

### Transfer

```text
  event Transfer(
    address from,
    address to,
    uint256 value
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `from` | `address` | `address` |  |
| 1 | `to` | `address` | `address` |  |
| 2 | `value` | `uint256` | `uint256` |  |

