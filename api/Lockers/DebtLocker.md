# DebtLocker

DebtLocker holds custody of LoanFDT tokens.

## Constructor




```solidity
  constructor(
    address _loan,
    address _pool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_loan` | `address` | `address` | 
| 1 | `_pool` | `address` | `address` | 



## Functions

### claim 

Claims funds distribution for Loan via LoanFDT. Only the Pool can call this function. 

```solidity
  function claim(
  ) nonpayable returns (
    uint256[7]
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256[7]` | [0] &#x3D;&gt; Total Claimed. [1] &#x3D;&gt; Interest Claimed. [2] &#x3D;&gt; Principal Claimed. [3] &#x3D;&gt; Pool Delegate Fee Claimed. [4] &#x3D;&gt; Excess Returned Claimed. [5] &#x3D;&gt; Amount Recovered (from Liquidation). [6] &#x3D;&gt; Default Suffered.


### lastAmountRecovered (state variable)

Then Liquidity Asset (a.k.a. loan asset) recovered from liquidation of Loan collateral.

```solidity
  function lastAmountRecovered(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


### lastDefaultSuffered (state variable)

The Loan total default suffered at last time &#x60;claim()&#x60; was called.

```solidity
  function lastDefaultSuffered(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


### lastExcessReturned (state variable)

The Loan total excess returned at last time &#x60;claim()&#x60; was called.

```solidity
  function lastExcessReturned(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


### lastFeePaid (state variable)

The Loan total fees paid at last time &#x60;claim()&#x60; was called.

```solidity
  function lastFeePaid(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


### lastInterestPaid (state variable)

The Loan total interest paid at last time &#x60;claim()&#x60; was called.

```solidity
  function lastInterestPaid(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


### lastPrincipalPaid (state variable)

The Loan total principal paid at last time &#x60;claim()&#x60; was called.

```solidity
  function lastPrincipalPaid(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


### liquidityAsset (state variable)

The Liquidity Asset this locker can claim.

```solidity
  function liquidityAsset(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### loan (state variable)

The Loan contract this locker is holding tokens for.

```solidity
  function loan(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### pool (state variable)

The owner of this Locker (the Pool).

```solidity
  function pool(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### triggerDefault 

Liquidates a Loan that is held by this contract. Only the Pool can call this function. 

```solidity
  function triggerDefault(
  ) nonpayable
```





