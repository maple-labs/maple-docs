# Loan

Loan maintains all accounting and functionality related to Loans.

## Constructor

Constructor for a Loan. It emits a \`LoanStateChanged\` event.

```text
  constructor(
    address _borrower,
    address _liquidityAsset,
    address _collateralAsset,
    address _flFactory,
    address _clFactory,
    uint256[5] specs,
    address[3] calcs
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_borrower` | `address` | `address` | Will receive the funding when calling \`drawdown\(\)\`. Is also responsible for repayments. |
| 1 | `_liquidityAsset` | `address` | `address` | The asset the Borrower is requesting funding in. |
| 2 | `_collateralAsset` | `address` | `address` | The asset provided as collateral by the Borrower. |
| 3 | `_flFactory` | `address` | `address` | Factory to instantiate FundingLocker with. |
| 4 | `_clFactory` | `address` | `address` | Factory to instantiate CollateralLocker with. |
| 5 | `specs` | `uint256[5]` | `uint256[5]` | Contains specifications for this Loan.  \[0\] =&gt; apr,  \[1\] =&gt; termDays,  \[2\] =&gt; paymentIntervalDays \(aka PID\),  \[3\] =&gt; requestAmount,  \[4\] =&gt; collateralRatio. |
| 6 | `calcs` | `address[3]` | `address[3]` | The calculators used for this Loan.  \[0\] =&gt; repaymentCalc,  \[1\] =&gt; lateFeeCalc,  \[2\] =&gt; premiumCalc. |

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

### amountLiquidated \(state variable\)

The amount of Collateral Asset that has been liquidated after default.

```text
  function amountLiquidated(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### amountRecovered \(state variable\)

The amount of Liquidity Asset that has been recovered after default.

```text
  function amountRecovered(
  ) view returns (
    uint256
  )
```

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

### apr \(state variable\)

The APR in basis points.

```text
  function apr(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

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

### borrower \(state variable\)

The Borrower of this Loan, responsible for repayments.

```text
  function borrower(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### clFactory \(state variable\)

The CollateralLockerFactory.

```text
  function clFactory(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### collateralAsset \(state variable\)

The asset deposited by Borrower into the CollateralLocker, for collateralizing this Loan.

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

### collateralLocker \(state variable\)

The CollateralLocker that holds custody of Loan collateral.

```text
  function collateralLocker(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### collateralRatio \(state variable\)

The percentage of value of the drawdown amount to post as collateral in basis points.

```text
  function collateralRatio(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### collateralRequiredForDrawdown

Calculates the collateral required to draw down amount.

```text
  function collateralRequiredForDrawdown(
    uint256 amt
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `amt` | `uint256` | `uint256` | The amount of the Liquidity Asset to draw down from the FundingLocker. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of the Collateral Asset required to post in the CollateralLocker for a given drawdown amount. |

### createdAt \(state variable\)

The timestamp of when Loan was instantiated.

```text
  function createdAt(
  ) view returns (
    uint256
  )
```

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

### defaultGracePeriod \(state variable\)

The time a Borrower has, after a payment is due, to make a payment before a liquidation can occur.

```text
  function defaultGracePeriod(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### defaultSuffered \(state variable\)

The difference between \`amountRecovered\` and \`principalOwed\` after liquidation.

```text
  function defaultSuffered(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### drawdown

Draws down funding from FundingLocker, posts collateral, and transitions the Loan state from \`Ready\` to \`Active\`. Only the Borrower can call this function. It emits four \`BalanceUpdated\` events. It emits a \`LoanStateChanged\` event. It emits a \`Drawdown\` event.

```text
  function drawdown(
    uint256 amt
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `amt` | `uint256` | `uint256` | the amount of Liquidity Asset the Borrower draws down. Remainder is returned to the Loan where it can be claimed back by LoanFDT holders. |

### excessReturned \(state variable\)

The amount of excess that has been returned to the Lenders after the Loan drawdown.

```text
  function excessReturned(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### feePaid \(state variable\)

The amount of fees that have been paid by the Borrower since the Loan instantiation.

```text
  function feePaid(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### flFactory \(state variable\)

The FundingLockerFactory.

```text
  function flFactory(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### fundLoan

Funds this Loan and mints LoanFDTs for \`mintTo\` \(DebtLocker in the case of Pool funding\). Only LiquidityLocker using valid/approved Pool can call this function. It emits a \`LoanFunded\` event. It emits a \`BalanceUpdated\` event.

```text
  function fundLoan(
    address mintTo,
    uint256 amt
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `mintTo` | `address` | `address` | The address that LoanFDTs are minted to. |
| 1 | `amt` | `uint256` | `uint256` | The amount to fund the Loan. |

### fundingLocker \(state variable\)

The FundingLocker that holds custody of Loan funds before drawdown.

```text
  function fundingLocker(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### fundingPeriod \(state variable\)

The time for a Loan to be funded in seconds.

```text
  function fundingPeriod(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### fundsToken

The \`fundsToken\` \(dividends\).

```text
  function fundsToken(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IERC20` |  |

### fundsTokenBalance

The amount of \`fundsToken\` \(Liquidity Asset\) currently present and accounted for in this contract.

```text
  function fundsTokenBalance(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### getExpectedAmountRecovered

Returns the expected amount of Liquidity Asset to be recovered from a liquidation based on current oracle prices.

```text
  function getExpectedAmountRecovered(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The minimum amount of Liquidity Asset that can be expected by swapping Collateral Asset. |

### getFullPayment

Returns the information of a full payment amount.

```text
  function getFullPayment(
  ) view returns (
    uint256 total,
    uint256 principal,
    uint256 interest
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `total` | `uint256` | `uint256` | Principal and interest owed, combined. |
| 1 | `principal` | `uint256` | `uint256` | Principal owed. |
| 2 | `interest` | `uint256` | `uint256` | Interest owed. |

### getNextPayment

Returns information of the next payment amount.

```text
  function getNextPayment(
  ) view returns (
    uint256,
    uint256,
    uint256,
    uint256,
    bool
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The entitled interest of the next payment \(Principal + Interest only when the next payment is last payment of the Loan\). |
| 1 |  | `uint256` | `uint256` | The entitled principal amount needed to be paid in the next payment. |
| 2 |  | `uint256` | `uint256` | The entitled interest amount needed to be paid in the next payment. |
| 3 |  | `uint256` | `uint256` | The payment due date. |
| 4 |  | `bool` | `bool` | Whether the payment is late. |

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

### interestPaid \(state variable\)

The amount of interest that has been paid by the Borrower since the Loan instantiation.

```text
  function interestPaid(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lateFeeCalc \(state variable\)

The LateFeeCalc for this Loan.

```text
  function lateFeeCalc(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### liquidationExcess \(state variable\)

The amount of Liquidity Asset that is to be returned to the Borrower, if \`amountRecovered &gt; principalOwed\`.

```text
  function liquidationExcess(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### liquidityAsset \(state variable\)

The asset deposited by Lenders into the FundingLocker, when funding this Loan.

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

### loanAdmins \(state variable\)

```text
  function loanAdmins(
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
| 0 |  | `bool` | `bool` | Whether the \`loanAdmin\` has permission to do certain operations in case of disaster management. |

### loanState \(state variable\)

The current state of this Loan, as defined in the State enum below.

```text
  function loanState(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `enum ILoan.State` |  |

### makeFullPayment

Makes the full payment for this Loan \(a.k.a. "calling" the Loan\). This requires the Borrower to pay a premium fee.

```text
  function makeFullPayment(
  ) nonpayable
```

### makePayment

Makes a payment for this Loan. Amounts are calculated for the Borrower.

```text
  function makePayment(
  ) nonpayable
```

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

### nextPaymentDue \(state variable\)

The unix timestamp due date of the next payment.

```text
  function nextPaymentDue(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### pause

Triggers paused state. Halts functionality for certain functions. Only the Borrower or a Loan Admin can call this function.

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

### paymentIntervalSeconds \(state variable\)

The time between Loan payments in seconds.

```text
  function paymentIntervalSeconds(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### paymentsRemaining \(state variable\)

The number of payments remaining on the Loan.

```text
  function paymentsRemaining(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### premiumCalc \(state variable\)

The PremiumCalc for this Loan.

```text
  function premiumCalc(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### principalOwed \(state variable\)

The amount of principal owed \(initially the drawdown amount\).

```text
  function principalOwed(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### principalPaid \(state variable\)

The amount of principal that has been paid by the Borrower since the Loan instantiation.

```text
  function principalPaid(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### reclaimERC20

Transfers any locked funds to the Governor. Only the Governor can call this function.

```text
  function reclaimERC20(
    address token
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `token` | `address` | `address` | The address of the token to be reclaimed. |

### repaymentCalc \(state variable\)

The RepaymentCalc for this Loan.

```text
  function repaymentCalc(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### requestAmount \(state variable\)

The total requested amount for Loan.

```text
  function requestAmount(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### setLoanAdmin

Sets a Loan Admin. Only the Borrower can call this function. It emits a \`LoanAdminSet\` event.

```text
  function setLoanAdmin(
    address loanAdmin,
    bool allowed
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `loanAdmin` | `address` | `address` | The address being allowed or disallowed as a Loan Admin. |
| 1 | `allowed` | `bool` | `bool` | The atatus of a Loan Admin. |

### superFactory \(state variable\)

The LoanFactory that deployed this Loan.

```text
  function superFactory(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

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

### termDays \(state variable\)

The total length of the Loan term in days.

```text
  function termDays(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

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

### triggerDefault

Triggers a default if the Loan meets certain default conditions, liquidating all collateral and updating accounting. Only the an account with sufficient LoanFDTs of this Loan can call this function. It emits a \`BalanceUpdated\` event. It emits a \`Liquidation\` event. It emits a \`LoanStateChanged\` event.

```text
  function triggerDefault(
  ) nonpayable
```

### unpause

Triggers unpaused state. Restores functionality for certain functions. Only the Borrower or a Loan Admin can call this function.

```text
  function unpause(
  ) nonpayable
```

### unwind

Handles returning capital to the Loan, where it can be claimed back by LoanFDT holders, if the Borrower has not drawn down on the Loan past the drawdown grace period. It emits a \`LoanStateChanged\` event.

```text
  function unwind(
  ) nonpayable
```

### updateFundsReceived

Registers a payment of funds in tokens. May be called directly after a deposit is made. Calls \_updateFundsTokenBalance\(\), whereby the contract computes the delta of the new and previous \`fundsToken\` balance and increments the total received funds \(cumulative\), by delta, by calling \_distributeFunds\(\).

```text
  function updateFundsReceived(
  ) nonpayable
```

### withdrawFunds

Withdraws all available funds earned through LoanFDT for a token holder. It emits a \`BalanceUpdated\` event.

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

### BalanceUpdated

Emits an event indicating the balance for an account was updated.

```text
  event BalanceUpdated(
    address account,
    address token,
    uint256 balance
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` | The address of an account. |
| 1 | `token` | `address` | `address` | The token address of the asset. |
| 2 | `balance` | `uint256` | `uint256` | The new balance of \`token\` for \`account\`. |

### Drawdown

Emits an event indicating the some loaned amount was drawn down.

```text
  event Drawdown(
    uint256 drawdownAmount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `drawdownAmount` | `uint256` | `uint256` | The amount that was drawn down. |

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

### Liquidation

Emits an event indicating the the Loan was liquidated.

```text
  event Liquidation(
    uint256 collateralSwapped,
    uint256 liquidityAssetReturned,
    uint256 liquidationExcess,
    uint256 defaultSuffered
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `collateralSwapped` | `uint256` | `uint256` | The amount of Collateral Asset swapped. |
| 1 | `liquidityAssetReturned` | `uint256` | `uint256` | The amount of Liquidity Asset recovered from swap. |
| 2 | `liquidationExcess` | `uint256` | `uint256` | The amount of Liquidity Asset returned to borrower. |
| 3 | `defaultSuffered` | `uint256` | `uint256` | The remaining losses after the liquidation. |

### LoanAdminSet

Emits an event indicating the an Admin for the Loan was set.

```text
  event LoanAdminSet(
    address loanAdmin,
    bool allowed
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `loanAdmin` | `address` | `address` | The address of some Loan Admin. |
| 1 | `allowed` | `bool` | `bool` | Whether \`loanAdmin\` is a Loan Admin for this Loan. |

### LoanFunded

Emits an event indicating the Loan was funded.

```text
  event LoanFunded(
    address fundedBy,
    uint256 amountFunded
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `fundedBy` | `address` | `address` | The Pool that funded the Loan. |
| 1 | `amountFunded` | `uint256` | `uint256` | The amount the Loan was funded for. |

### LoanStateChanged

Emits an event indicating the state of the Loan changed.

```text
  event LoanStateChanged(
    uint8 state
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `state` | `uint8` | `enum ILoan.State` | The state of the Loan. |

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

### PaymentMade

Emits an event indicating the a payment was made for the Loan.

```text
  event PaymentMade(
    uint256 totalPaid,
    uint256 principalPaid,
    uint256 interestPaid,
    uint256 paymentsRemaining,
    uint256 principalOwed,
    uint256 nextPaymentDue,
    bool latePayment
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `totalPaid` | `uint256` | `uint256` | The total amount paid. |
| 1 | `principalPaid` | `uint256` | `uint256` | The principal portion of the amount paid. |
| 2 | `interestPaid` | `uint256` | `uint256` | The interest portion of the amount paid. |
| 3 | `paymentsRemaining` | `uint256` | `uint256` | The amount of payment remaining. |
| 4 | `principalOwed` | `uint256` | `uint256` | The outstanding principal of the Loan. |
| 5 | `nextPaymentDue` | `uint256` | `uint256` | The timestamp of the due date of the next payment. |
| 6 | `latePayment` | `bool` | `bool` | Whether this payment was late. |

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

