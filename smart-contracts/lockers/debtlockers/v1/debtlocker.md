# DebtLocker

DebtLocker holds custody of LoanFDT tokens.

<br />

## Constructor




```solidity
    constructor(
        address _loan,
        address _pool
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_loan` | `address` | `address` |  |
| 1 | `_pool` | `address` | `address` |  |


<br />


## Functions

### `claim` 

Claims funds distribution for Loan via LoanFDT. Only the Pool can call this function. 

```solidity
    function claim()
        nonpayable
        returns (
            uint256[7]
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256[7]` | `uint256[7]` | [0] &#x3D;&gt; Total Claimed. [1] &#x3D;&gt; Interest Claimed. [2] &#x3D;&gt; Principal Claimed. [3] &#x3D;&gt; Pool Delegate Fee Claimed. [4] &#x3D;&gt; Excess Returned Claimed. [5] &#x3D;&gt; Amount Recovered (from Liquidation). [6] &#x3D;&gt; Default Suffered. |


<br />

### `lastAmountRecovered` _[state variable]_

Then Liquidity Asset (a.k.a. loan asset) recovered from liquidation of Loan collateral.

```solidity
    function lastAmountRecovered()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `lastDefaultSuffered` _[state variable]_

The Loan total default suffered at last time &#x60;claim()&#x60; was called.

```solidity
    function lastDefaultSuffered()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `lastExcessReturned` _[state variable]_

The Loan total excess returned at last time &#x60;claim()&#x60; was called.

```solidity
    function lastExcessReturned()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `lastFeePaid` _[state variable]_

The Loan total fees paid at last time &#x60;claim()&#x60; was called.

```solidity
    function lastFeePaid()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `lastInterestPaid` _[state variable]_

The Loan total interest paid at last time &#x60;claim()&#x60; was called.

```solidity
    function lastInterestPaid()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `lastPrincipalPaid` _[state variable]_

The Loan total principal paid at last time &#x60;claim()&#x60; was called.

```solidity
    function lastPrincipalPaid()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `liquidityAsset` _[state variable]_

The Liquidity Asset this locker can claim.

```solidity
    function liquidityAsset()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `contract IERC20` |  |


<br />

### `loan` _[state variable]_

The Loan contract this locker is holding tokens for.

```solidity
    function loan()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `contract ILoanLike` |  |


<br />

### `pool` _[state variable]_

The owner of this Locker (the Pool).

```solidity
    function pool()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `triggerDefault` 

Liquidates a Loan that is held by this contract. Only the Pool can call this function. 

```solidity
    function triggerDefault()
        nonpayable;
```



<br />



