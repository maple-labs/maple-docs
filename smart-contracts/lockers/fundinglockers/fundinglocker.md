# FundingLocker

FundingLocker holds custody of Liquidity Asset tokens during the funding period of a Loan.

<br />

## Constructor




```solidity
    constructor(
        address _liquidityAsset,
        address _loan
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_liquidityAsset` | `address` | `address` |  |
| 1 | `_loan` | `address` | `address` |  |


<br />


## Functions

### `drain` 

Transfers entire amount of Liquidity Asset held in escrow to the Loan. Only the Loan can call this function. 

```solidity
    function drain()
        nonpayable;
```



<br />

### `liquidityAsset` _[state variable]_

The asset the Loan was funded with.

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
| 0 |  | `address` | `address` |  |


<br />

### `loan` _[state variable]_

The Loan this FundingLocker has funded.

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
| 0 |  | `address` | `address` |  |


<br />

### `pull` 

Transfers &#x60;amt&#x60; of Liquidity Asset to &#x60;dst&#x60;. Only the Loan can call this function. 

```solidity
    function pull(
        address dst,
        uint256 amt
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `dst` | `address` | `address` | The destination to transfer Liquidity Asset to. |
| 1 | `amt` | `uint256` | `uint256` | The amount of Liquidity Asset to transfer. |


<br />


