# RepaymentCalc

RepaymentCalc calculates payment amounts on Loans.


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


### getNextPayment 

Calculates the next payment for a Loan.

```solidity
  function getNextPayment(
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
| 0 | `_loan` | `address` | `address` | The address of a Loan to calculate a payment for.


#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 | `total` | `uint256` |         The entitled interest of the next payment (Principal + Interest only when the next payment is last payment of the Loan).
| 1 | `principalOwed` | `uint256` | The entitled principal amount needed to be paid in the next payment.
| 2 | `interest` | `uint256` |      The entitled interest amount needed to be paid in the next payment.


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




