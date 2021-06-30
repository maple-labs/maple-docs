# Loan

Loan maintains all accounting and functionality related to Loans.

## Constructor


Constructor for a Loan. It emits a &#x60;LoanStateChanged&#x60; event. 

```solidity
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
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_borrower` | `address` | `address` | Will receive the funding when calling &#x60;drawdown()&#x60;. Is also responsible for repayments.
| 1 | `_liquidityAsset` | `address` | `address` | The asset the Borrower is requesting funding in.
| 2 | `_collateralAsset` | `address` | `address` | The asset provided as collateral by the Borrower.
| 3 | `_flFactory` | `address` | `address` | Factory to instantiate FundingLocker with.
| 4 | `_clFactory` | `address` | `address` | Factory to instantiate CollateralLocker with.
| 5 | `specs` | `uint256[5]` | `uint256[5]` | Contains specifications for this Loan.  [0] &#x3D;&gt; apr,  [1] &#x3D;&gt; termDays,  [2] &#x3D;&gt; paymentIntervalDays (aka PID),  [3] &#x3D;&gt; requestAmount,  [4] &#x3D;&gt; collateralRatio. 
| 6 | `calcs` | `address[3]` | `address[3]` | The calculators used for this Loan.  [0] &#x3D;&gt; repaymentCalc,  [1] &#x3D;&gt; lateFeeCalc,  [2] &#x3D;&gt; premiumCalc. 



## Functions

### accumulativeFundsOf 

Returns the amount of funds that an account has earned in total. accumulativeFundsOf(_owner) &#x3D; withdrawableFundsOf(_owner) + withdrawnFundsOf(_owner)  &#x3D; (pointsPerShare * balanceOf(_owner) + pointsCorrection[_owner]) / pointsMultiplier 

```solidity
  function accumulativeFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of funds that &#x60;_owner&#x60; has earned in total.


### allowance 

Returns the remaining number of tokens that &#x60;spender&#x60; will be allowed to spend on behalf of &#x60;owner&#x60; through {transferFrom}. This is zero by default. This value changes when {approve} or {transferFrom} are called.

```solidity
  function allowance(
    address owner,
    address spender
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | 
| 1 | `spender` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### amountLiquidated (state variable)

The amount of Collateral Asset that has been liquidated after default.

```solidity
  function amountLiquidated(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### amountRecovered (state variable)

The amount of Liquidity Asset that has been recovered after default.

```solidity
  function amountRecovered(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### approve 

Sets &#x60;amount&#x60; as the allowance of &#x60;spender&#x60; over the caller&#x27;s tokens. Returns a boolean value indicating whether the operation succeeded. IMPORTANT: Beware that changing an allowance with this method brings the risk that someone may use both the old and the new allowance by unfortunate transaction ordering. One possible solution to mitigate this race condition is to first reduce the spender&#x27;s allowance to 0 and set the desired value afterwards: https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729 Emits an {Approval} event.

```solidity
  function approve(
    address spender,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` | 
| 1 | `amount` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### apr (state variable)

The APR in basis points.

```solidity
  function apr(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### balanceOf 

Returns the amount of tokens owned by &#x60;account&#x60;.

```solidity
  function balanceOf(
    address account
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### borrower (state variable)

The Borrower of this Loan, responsible for repayments.

```solidity
  function borrower(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### clFactory (state variable)

The CollateralLockerFactory.

```solidity
  function clFactory(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### collateralAsset (state variable)

The asset deposited by Borrower into the CollateralLocker, for collateralizing this Loan.

```solidity
  function collateralAsset(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `contract IERC20` | 


### collateralLocker (state variable)

The CollateralLocker that holds custody of Loan collateral.

```solidity
  function collateralLocker(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### collateralRatio (state variable)

The percentage of value of the drawdown amount to post as collateral in basis points.

```solidity
  function collateralRatio(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### collateralRequiredForDrawdown 

Calculates the collateral required to draw down amount.

```solidity
  function collateralRequiredForDrawdown(
    uint256 amt
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | The amount of the Liquidity Asset to draw down from the FundingLocker.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of the Collateral Asset required to post in the CollateralLocker for a given drawdown amount.


### createdAt (state variable)

The timestamp of when Loan was instantiated.

```solidity
  function createdAt(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### decimals 

Returns the number of decimals used to get its user representation. For example, if &#x60;decimals&#x60; equals &#x60;2&#x60;, a balance of &#x60;505&#x60; tokens should be displayed to a user as &#x60;5,05&#x60; (&#x60;505 / 10 ** 2&#x60;). Tokens usually opt for a value of 18, imitating the relationship between Ether and Wei. This is the value {ERC20} uses, unless {_setupDecimals} is called. NOTE: This information is only used for _display_ purposes: it in no way affects any of the arithmetic of the contract, including {IERC20-balanceOf} and {IERC20-transfer}.

```solidity
  function decimals(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` | 


### decreaseAllowance 

Atomically decreases the allowance granted to &#x60;spender&#x60; by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - &#x60;spender&#x60; cannot be the zero address. - &#x60;spender&#x60; must have allowance for the caller of at least &#x60;subtractedValue&#x60;.

```solidity
  function decreaseAllowance(
    address spender,
    uint256 subtractedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` | 
| 1 | `subtractedValue` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### defaultGracePeriod (state variable)

The time a Borrower has, after a payment is due, to make a payment before a liquidation can occur.

```solidity
  function defaultGracePeriod(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### defaultSuffered (state variable)

The difference between &#x60;amountRecovered&#x60; and &#x60;principalOwed&#x60; after liquidation.

```solidity
  function defaultSuffered(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### drawdown 

Draws down funding from FundingLocker, posts collateral, and transitions the Loan state from &#x60;Ready&#x60; to &#x60;Active&#x60;. Only the Borrower can call this function. It emits four &#x60;BalanceUpdated&#x60; events. It emits a &#x60;LoanStateChanged&#x60; event. It emits a &#x60;Drawdown&#x60; event. 

```solidity
  function drawdown(
    uint256 amt
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | the amount of Liquidity Asset the Borrower draws down. Remainder is returned to the Loan where it can be claimed back by LoanFDT holders.


### excessReturned (state variable)

The amount of excess that has been returned to the Lenders after the Loan drawdown.

```solidity
  function excessReturned(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### feePaid (state variable)

The amount of fees that have been paid by the Borrower since the Loan instantiation.

```solidity
  function feePaid(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### flFactory (state variable)

The FundingLockerFactory.

```solidity
  function flFactory(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### fundLoan 

Funds this Loan and mints LoanFDTs for &#x60;mintTo&#x60; (DebtLocker in the case of Pool funding). Only LiquidityLocker using valid/approved Pool can call this function. It emits a &#x60;LoanFunded&#x60; event. It emits a &#x60;BalanceUpdated&#x60; event. 

```solidity
  function fundLoan(
    address mintTo,
    uint256 amt
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `mintTo` | `address` | `address` | The address that LoanFDTs are minted to.
| 1 | `amt` | `uint256` | `uint256` | The amount to fund the Loan.


### fundingLocker (state variable)

The FundingLocker that holds custody of Loan funds before drawdown.

```solidity
  function fundingLocker(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### fundingPeriod (state variable)

The time for a Loan to be funded in seconds.

```solidity
  function fundingPeriod(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### fundsToken 

The &#x60;fundsToken&#x60; (dividends).

```solidity
  function fundsToken(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `contract IERC20` | 


### fundsTokenBalance 

The amount of &#x60;fundsToken&#x60; (Liquidity Asset) currently present and accounted for in this contract.

```solidity
  function fundsTokenBalance(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### getExpectedAmountRecovered 

Returns the expected amount of Liquidity Asset to be recovered from a liquidation based on current oracle prices.

```solidity
  function getExpectedAmountRecovered(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The minimum amount of Liquidity Asset that can be expected by swapping Collateral Asset.


### getFullPayment 

Returns the information of a full payment amount.

```solidity
  function getFullPayment(
  ) view returns (
    uint256 total,
    uint256 principal,
    uint256 interest
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `total` | `uint256` | `uint256` |     Principal and interest owed, combined.
| 1 | `principal` | `uint256` | `uint256` | Principal owed.
| 2 | `interest` | `uint256` | `uint256` |  Interest owed.


### getNextPayment 

Returns information of the next payment amount.

```solidity
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
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The entitled interest of the next payment (Principal + Interest only when the next payment is last payment of the Loan).
| 1 |  | `uint256` | `uint256` | The entitled principal amount needed to be paid in the next payment.
| 2 |  | `uint256` | `uint256` | The entitled interest amount needed to be paid in the next payment.
| 3 |  | `uint256` | `uint256` | The payment due date.
| 4 |  | `bool` | `bool` | Whether the payment is late.


### increaseAllowance 

Atomically increases the allowance granted to &#x60;spender&#x60; by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - &#x60;spender&#x60; cannot be the zero address.

```solidity
  function increaseAllowance(
    address spender,
    uint256 addedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` | 
| 1 | `addedValue` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### interestPaid (state variable)

The amount of interest that has been paid by the Borrower since the Loan instantiation.

```solidity
  function interestPaid(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### lateFeeCalc (state variable)

The LateFeeCalc for this Loan.

```solidity
  function lateFeeCalc(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### liquidationExcess (state variable)

The amount of Liquidity Asset that is to be returned to the Borrower, if &#x60;amountRecovered &gt; principalOwed&#x60;.

```solidity
  function liquidationExcess(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### liquidityAsset (state variable)

The asset deposited by Lenders into the FundingLocker, when funding this Loan.

```solidity
  function liquidityAsset(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `contract IERC20` | 


### loanAdmins (state variable)



```solidity
  function loanAdmins(
    address
  ) view returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether the &#x60;loanAdmin&#x60; has permission to do certain operations in case of disaster management.


### loanState (state variable)

The current state of this Loan, as defined in the State enum below.

```solidity
  function loanState(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `enum ILoan.State` | 


### makeFullPayment 

Makes the full payment for this Loan (a.k.a. &quot;calling&quot; the Loan). This requires the Borrower to pay a premium fee. 

```solidity
  function makeFullPayment(
  ) nonpayable
```



### makePayment 

Makes a payment for this Loan. Amounts are calculated for the Borrower. 

```solidity
  function makePayment(
  ) nonpayable
```



### name 

Returns the name of the token.

```solidity
  function name(
  ) view returns (
    string
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` | 


### nextPaymentDue (state variable)

The unix timestamp due date of the next payment.

```solidity
  function nextPaymentDue(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### pause 

Triggers paused state. Halts functionality for certain functions. Only the Borrower or a Loan Admin can call this function. 

```solidity
  function pause(
  ) nonpayable
```



### paused 

Returns true if the contract is paused, and false otherwise.

```solidity
  function paused(
  ) view returns (
    bool
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### paymentIntervalSeconds (state variable)

The time between Loan payments in seconds.

```solidity
  function paymentIntervalSeconds(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### paymentsRemaining (state variable)

The number of payments remaining on the Loan.

```solidity
  function paymentsRemaining(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### premiumCalc (state variable)

The PremiumCalc for this Loan.

```solidity
  function premiumCalc(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### principalOwed (state variable)

The amount of principal owed (initially the drawdown amount).

```solidity
  function principalOwed(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### principalPaid (state variable)

The amount of principal that has been paid by the Borrower since the Loan instantiation.

```solidity
  function principalPaid(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### reclaimERC20 

Transfers any locked funds to the Governor. Only the Governor can call this function. 

```solidity
  function reclaimERC20(
    address token
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `token` | `address` | `address` | The address of the token to be reclaimed.


### repaymentCalc (state variable)

The RepaymentCalc for this Loan.

```solidity
  function repaymentCalc(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### requestAmount (state variable)

The total requested amount for Loan.

```solidity
  function requestAmount(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### setLoanAdmin 

Sets a Loan Admin. Only the Borrower can call this function. It emits a &#x60;LoanAdminSet&#x60; event. 

```solidity
  function setLoanAdmin(
    address loanAdmin,
    bool allowed
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanAdmin` | `address` | `address` | The address being allowed or disallowed as a Loan Admin.
| 1 | `allowed` | `bool` | `bool` | The atatus of a Loan Admin.


### superFactory (state variable)

The LoanFactory that deployed this Loan.

```solidity
  function superFactory(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### symbol 

Returns the symbol of the token, usually a shorter version of the name.

```solidity
  function symbol(
  ) view returns (
    string
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` | 


### termDays (state variable)

The total length of the Loan term in days.

```solidity
  function termDays(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### totalSupply 

Returns the amount of tokens in existence.

```solidity
  function totalSupply(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### transfer 

Moves &#x60;amount&#x60; tokens from the caller&#x27;s account to &#x60;recipient&#x60;. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```solidity
  function transfer(
    address recipient,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `recipient` | `address` | `address` | 
| 1 | `amount` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### transferFrom 

Moves &#x60;amount&#x60; tokens from &#x60;sender&#x60; to &#x60;recipient&#x60; using the allowance mechanism. &#x60;amount&#x60; is then deducted from the caller&#x27;s allowance. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```solidity
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
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `sender` | `address` | `address` | 
| 1 | `recipient` | `address` | `address` | 
| 2 | `amount` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### triggerDefault 

Triggers a default if the Loan meets certain default conditions, liquidating all collateral and updating accounting. Only the an account with sufficient LoanFDTs of this Loan can call this function. It emits a &#x60;BalanceUpdated&#x60; event. It emits a &#x60;Liquidation&#x60; event. It emits a &#x60;LoanStateChanged&#x60; event. 

```solidity
  function triggerDefault(
  ) nonpayable
```



### unpause 

Triggers unpaused state. Restores functionality for certain functions. Only the Borrower or a Loan Admin can call this function. 

```solidity
  function unpause(
  ) nonpayable
```



### unwind 

Handles returning capital to the Loan, where it can be claimed back by LoanFDT holders,  if the Borrower has not drawn down on the Loan past the drawdown grace period. It emits a &#x60;LoanStateChanged&#x60; event. 

```solidity
  function unwind(
  ) nonpayable
```



### updateFundsReceived 

Registers a payment of funds in tokens. May be called directly after a deposit is made. Calls _updateFundsTokenBalance(), whereby the contract computes the delta of the new and previous  &#x60;fundsToken&#x60; balance and increments the total received funds (cumulative), by delta, by calling _distributeFunds().

```solidity
  function updateFundsReceived(
  ) nonpayable
```



### withdrawFunds 

Withdraws all available funds earned through LoanFDT for a token holder. It emits a &#x60;BalanceUpdated&#x60; event. 

```solidity
  function withdrawFunds(
  ) nonpayable
```



### withdrawableFundsOf 

Returns the amount of funds that an account can withdraw.

```solidity
  function withdrawableFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of some FDT holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount funds that &#x60;_owner&#x60; can withdraw.


### withdrawnFundsOf 

Returns the amount of funds that an account has withdrawn.

```solidity
  function withdrawnFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of funds that &#x60;_owner&#x60; has withdrawn.



## Events

### Approval


```solidity
  event Approval(
    address owner,
    address spender,
    uint256 value
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | 
| 1 | `spender` | `address` | `address` | 
| 2 | `value` | `uint256` | `uint256` | 

### BalanceUpdated

Emits an event indicating the balance for an account was updated.
```solidity
  event BalanceUpdated(
    address account,
    address token,
    uint256 balance
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address of an account.
| 1 | `token` | `address` | `address` | The token address of the asset.
| 2 | `balance` | `uint256` | `uint256` | The new balance of &#x60;token&#x60; for &#x60;account&#x60;.

### Drawdown

Emits an event indicating the some loaned amount was drawn down.
```solidity
  event Drawdown(
    uint256 drawdownAmount
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `drawdownAmount` | `uint256` | `uint256` | The amount that was drawn down.

### FundsDistributed


```solidity
  event FundsDistributed(
    address by,
    uint256 fundsDistributed
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `by` | `address` | `address` | 
| 1 | `fundsDistributed` | `uint256` | `uint256` | 

### FundsWithdrawn


```solidity
  event FundsWithdrawn(
    address by,
    uint256 fundsWithdrawn,
    uint256 totalWithdrawn
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `by` | `address` | `address` | 
| 1 | `fundsWithdrawn` | `uint256` | `uint256` | 
| 2 | `totalWithdrawn` | `uint256` | `uint256` | 

### Liquidation

Emits an event indicating the the Loan was liquidated.
```solidity
  event Liquidation(
    uint256 collateralSwapped,
    uint256 liquidityAssetReturned,
    uint256 liquidationExcess,
    uint256 defaultSuffered
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralSwapped` | `uint256` | `uint256` | The amount of Collateral Asset swapped.
| 1 | `liquidityAssetReturned` | `uint256` | `uint256` | The amount of Liquidity Asset recovered from swap.
| 2 | `liquidationExcess` | `uint256` | `uint256` | The amount of Liquidity Asset returned to borrower.
| 3 | `defaultSuffered` | `uint256` | `uint256` | The remaining losses after the liquidation.

### LoanAdminSet

Emits an event indicating the an Admin for the Loan was set.
```solidity
  event LoanAdminSet(
    address loanAdmin,
    bool allowed
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanAdmin` | `address` | `address` | The address of some Loan Admin.
| 1 | `allowed` | `bool` | `bool` | Whether &#x60;loanAdmin&#x60; is a Loan Admin for this Loan.

### LoanFunded

Emits an event indicating the Loan was funded.
```solidity
  event LoanFunded(
    address fundedBy,
    uint256 amountFunded
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundedBy` | `address` | `address` | The Pool that funded the Loan.
| 1 | `amountFunded` | `uint256` | `uint256` | The amount the Loan was funded for.

### LoanStateChanged

Emits an event indicating the state of the Loan changed.
```solidity
  event LoanStateChanged(
    uint8 state
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `state` | `uint8` | `enum ILoan.State` | The state of the Loan.

### Paused


```solidity
  event Paused(
    address account
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | 

### PaymentMade

Emits an event indicating the a payment was made for the Loan.
```solidity
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
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `totalPaid` | `uint256` | `uint256` | The total amount paid.
| 1 | `principalPaid` | `uint256` | `uint256` | The principal portion of the amount paid.
| 2 | `interestPaid` | `uint256` | `uint256` | The interest portion of the amount paid.
| 3 | `paymentsRemaining` | `uint256` | `uint256` | The amount of payment remaining.
| 4 | `principalOwed` | `uint256` | `uint256` | The outstanding principal of the Loan.
| 5 | `nextPaymentDue` | `uint256` | `uint256` | The timestamp of the due date of the next payment.
| 6 | `latePayment` | `bool` | `bool` | Whether this payment was late.

### PointsCorrectionUpdated


```solidity
  event PointsCorrectionUpdated(
    address ,
    int256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 
| 1 | `` | `int256` | `int256` | 

### PointsPerShareUpdated


```solidity
  event PointsPerShareUpdated(
    uint256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` | 

### Transfer


```solidity
  event Transfer(
    address from,
    address to,
    uint256 value
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` | 
| 1 | `to` | `address` | `address` | 
| 2 | `value` | `uint256` | `uint256` | 

### Unpaused


```solidity
  event Unpaused(
    address account
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | 

