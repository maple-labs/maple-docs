# LoanFactory

LoanFactory instantiates Loans.

## Constructor




```solidity
  constructor(
    address _globals
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_globals` | `address` | `address` | 



## Functions

### CL_FACTORY (state variable)

The Factory type of &#x60;CollateralLockerFactory&#x60;.

```solidity
  function CL_FACTORY(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint8` | 


### FL_FACTORY (state variable)

The Factory type of &#x60;FundingLockerFactory&#x60;.

```solidity
  function FL_FACTORY(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint8` | 


### INTEREST_CALC_TYPE (state variable)

The Calc type of &#x60;RepaymentCalc&#x60;.

```solidity
  function INTEREST_CALC_TYPE(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint8` | 


### LATEFEE_CALC_TYPE (state variable)

The Calc type of &#x60;LateFeeCalc&#x60;.

```solidity
  function LATEFEE_CALC_TYPE(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint8` | 


### PREMIUM_CALC_TYPE (state variable)

The Calc type of &#x60;PremiumCalc&#x60;.

```solidity
  function PREMIUM_CALC_TYPE(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint8` | 


### createLoan 

Create a new Loan. It emits a &#x60;LoanCreated&#x60; event. 

```solidity
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
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityAsset` | `address` | `address` | The asset the Loan will raise funding in.
| 1 | `collateralAsset` | `address` | `address` | The asset the Loan will use as collateral.
| 2 | `flFactory` | `address` | `address` | The factory to instantiate a FundingLocker from.
| 3 | `clFactory` | `address` | `address` | The factory to instantiate a CollateralLocker from.
| 4 | `specs` | `uint256[5]` | `uint256[5]` | The specifications for the Loan.  [0] &#x3D;&gt; apr,  [1] &#x3D;&gt; termDays,  [2] &#x3D;&gt; paymentIntervalDays,  [3] &#x3D;&gt; requestAmount,  [4] &#x3D;&gt; collateralRatio. 
| 5 | `calcs` | `address[3]` | `address[3]` | The calculators used for the Loan.  [0] &#x3D;&gt; repaymentCalc,  [1] &#x3D;&gt; lateFeeCalc,  [2] &#x3D;&gt; premiumCalc. 


#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 | `loanAddress` | `address` |     Address of the instantiated Loan.


### globals (state variable)

The instance of the MapleGlobals.

```solidity
  function globals(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### isLoan (state variable)



```solidity
  function isLoan(
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
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bool` | Whether &#x60;loan&#x60; is a Loan.


### loanFactoryAdmins (state variable)



```solidity
  function loanFactoryAdmins(
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
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bool` | Whether &#x60;admin&#x60; has permission to do certain operations in case of disaster management.


### loans (state variable)



```solidity
  function loans(
    uint256
  ) view returns (
    address
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | The address of the Loan at &#x60;index&#x60;.


### loansCreated (state variable)

The incrementor for number of Loans created.

```solidity
  function loansCreated(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


### pause 

Triggers paused state. Halts functionality for certain functions. Only the Governor or a LoanFactory Admin can call this function.

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
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bool` | 


### setGlobals 

Sets MapleGlobals. Only the Governor can call this function. 

```solidity
  function setGlobals(
    address newGlobals
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newGlobals` | `address` | `address` | Address of new MapleGlobals.


### setLoanFactoryAdmin 

Sets a LoanFactory Admin. Only the Governor can call this function.It emits a &#x60;LoanFactoryAdminSet&#x60; event.

```solidity
  function setLoanFactoryAdmin(
    address loanFactoryAdmin,
    bool allowed
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanFactoryAdmin` | `address` | `address` | An address being allowed or disallowed as a LoanFactory Admin.
| 1 | `allowed` | `bool` | `bool` | The status of &#x60;loanFactoryAdmin&#x60; as an Admin.


### unpause 

Triggers unpaused state. Restores functionality for certain functions. Only the Governor or a LoanFactory Admin can call this function.

```solidity
  function unpause(
  ) nonpayable
```




## Events

### LoanCreated

Emits an event indicating a Loan was created.
```solidity
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
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The address of the Loan.
| 1 | `borrower` | `address` | `address` | The Borrower.
| 2 | `liquidityAsset` | `address` | `address` | The asset the Loan will raise funding in.
| 3 | `collateralAsset` | `address` | `address` | The asset the Loan will use as collateral.
| 4 | `collateralLocker` | `address` | `address` | The address of the Collateral Locker.
| 5 | `fundingLocker` | `address` | `address` | The address of the Funding Locker.
| 6 | `specs` | `uint256[5]` | `uint256[5]` | The specifications for the Loan.  [0] &#x3D;&gt; apr,  [1] &#x3D;&gt; termDays,  [2] &#x3D;&gt; paymentIntervalDays,  [3] &#x3D;&gt; requestAmount,  [4] &#x3D;&gt; collateralRatio. 
| 7 | `calcs` | `address[3]` | `address[3]` | The calculators used for the Loan.  [0] &#x3D;&gt; repaymentCalc,  [1] &#x3D;&gt; lateFeeCalc,  [2] &#x3D;&gt; premiumCalc. 
| 8 | `name` | `string` | `string` | The name of the Loan FDTs.
| 9 | `symbol` | `string` | `string` | The symbol of the Loan FDTs.

### LoanFactoryAdminSet

Emits an event indicating a LoanFactoryAdmin was allowed.
```solidity
  event LoanFactoryAdminSet(
    address loanFactoryAdmin,
    bool allowed
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanFactoryAdmin` | `address` | `address` | The address of a LoanFactoryAdmin.
| 1 | `allowed` | `bool` | `bool` | Whether &#x60;loanFactoryAdmin&#x60; is allowed as an admin of the LoanFactory.

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

