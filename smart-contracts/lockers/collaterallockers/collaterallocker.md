# CollateralLocker

CollateralLocker holds custody of Collateral Asset for Loans.

<br />

## Constructor




```solidity
    constructor(
        address _collateralAsset,
        address _loan
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_collateralAsset` | `address` | `address` |  |
| 1 | `_loan` | `address` | `address` |  |


<br />


## Functions

### `collateralAsset` _[state variable]_

The address the Collateral Asset the Loan is collateralized with.

```solidity
    function collateralAsset()
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

The Loan contract address this CollateralLocker is attached to.

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

Transfers &#x60;amt&#x60; of Collateral Asset to &#x60;dst&#x60;. Only the Loan can call this function. 

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
| 0 | `dst` | `address` | `address` | The destination to transfer Collateral Asset to. |
| 1 | `amt` | `uint256` | `uint256` | The amount of Collateral Asset to transfer. |


<br />



