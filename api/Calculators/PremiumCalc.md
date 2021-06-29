# PremiumCalc

PremiumCalc calculates premium fees on Loans.

## Constructor




```solidity
  constructor(
    uint256 _premiumFee
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_premiumFee` | `uint256` | `uint256` | 



## Functions

### calcType (state variable)

The Calculator type.

```solidity
  function calcType(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint8` | 


### getPremiumPayment 

Calculates the premium payment for a Loan, when making a full payment.

```solidity
  function getPremiumPayment(
    address _loan
  ) view returns (
    uint256 total,
    uint256 principalOwed,
    uint256 interest
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_loan` | `address` | `address` | The address of a Loan to calculate a premium payment for.


#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 | `total` | `uint256` |         The principal + interest.
| 1 | `principalOwed` | `uint256` | The principal.
| 2 | `interest` | `uint256` |      The interest.


### name (state variable)

The Calculator name.

```solidity
  function name(
  ) view returns (
    bytes32
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bytes32` | 


### premiumFee (state variable)

The flat percentage fee (in basis points) of principal to charge as a premium when calling a Loan.

```solidity
  function premiumFee(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 




