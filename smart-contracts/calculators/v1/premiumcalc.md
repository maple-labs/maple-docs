# PremiumCalc

PremiumCalc calculates premium fees on Loans.

<br />

## Constructor




```solidity
    constructor(
        uint256 _premiumFee
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_premiumFee` | `uint256` | `uint256` |  |


<br />


## Functions

### `calcType` _[state variable]_

The Calculator type.

```solidity
    function calcType()
        pure
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` |  |


<br />

### `getPremiumPayment` 

Calculates the premium payment for a Loan, when making a full payment.

```solidity
    function getPremiumPayment(
        address _loan
    )
        view
        returns (
            uint256 total,
            uint256 principalOwed,
            uint256 interest
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_loan` | `address` | `address` | The address of a Loan to calculate a premium payment for. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `total` | `uint256` | `uint256` |         The principal + interest. |
| 1 | `principalOwed` | `uint256` | `uint256` | The principal. |
| 2 | `interest` | `uint256` | `uint256` |      The interest. |


<br />

### `name` _[state variable]_

The Calculator name.

```solidity
    function name()
        pure
        returns (
            bytes32
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bytes32` | `bytes32` |  |


<br />

### `premiumFee` _[state variable]_

The flat percentage fee (in basis points) of principal to charge as a premium when calling a Loan.

```solidity
    function premiumFee()
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



