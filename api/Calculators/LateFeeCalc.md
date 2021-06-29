# LateFeeCalc

LateFeeCalc calculates late fees on Loans.

## Constructor




```solidity
  constructor(
    uint256 _lateFee
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_lateFee` | `uint256` | `uint256` | 



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


### getLateFee 

Calculates the late fee payment for a Loan.

```solidity
  function getLateFee(
    uint256 interest
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `interest` | `uint256` | `uint256` | Amount of interest to be used to calculate late fee for.


#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | Late fee that is charged to the Borrower.


### lateFee (state variable)

The fee in basis points, charged on the payment amount.

```solidity
  function lateFee(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `uint256` | 


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




