# LoanManagerInitializer



<br />


## Functions

### `accountedInterest` 

Gets the amount of accounted interest.

```solidity
    function accountedInterest()
        view
        returns (
            uint112
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint112` | `uint112` |  |


<br />

### `allowedSlippageFor` 

Gets allowed slippage for a give collateral asset.

```solidity
    function allowedSlippageFor(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `decodeArguments` 



```solidity
    function decodeArguments(
        bytes calldata_
    )
        pure
        returns (
            address pool_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `calldata_` | `bytes` | `bytes` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool_` | `address` | `address` |  |


<br />

### `domainEnd` 

Gets the timestamp of the domain end.

```solidity
    function domainEnd()
        view
        returns (
            uint48
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint48` | `uint48` |  |


<br />

### `domainStart` 

Gets the timestamp of the domain start.

```solidity
    function domainStart()
        view
        returns (
            uint48
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint48` | `uint48` |  |


<br />

### `encodeArguments` 



```solidity
    function encodeArguments(
        address pool_
    )
        pure
        returns (
            bytes calldata_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool_` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `calldata_` | `bytes` | `bytes` |  |


<br />

### `fundsAsset` 

Gets the address of the funds asset.

```solidity
    function fundsAsset()
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

### `issuanceRate` 

Gets the current issuance rate.

```solidity
    function issuanceRate()
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

### `liquidationInfo` 

Gets the information for a liquidation.

```solidity
    function liquidationInfo(
        address
    )
        view
        returns (
            bool triggeredByGovernor,
            uint128 principal,
            uint120 interest,
            uint256 lateInterest,
            uint96 platformFees,
            address liquidator
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `triggeredByGovernor` | `bool` | `bool` | True if the liquidation was triggered by the governor. |
| 1 | `principal` | `uint128` | `uint128` |           The amount of principal to be recovered. |
| 2 | `interest` | `uint120` | `uint120` |            The amount of interest to be recovered. |
| 3 | `lateInterest` | `uint256` | `uint256` |        The amount of late interest to be recovered. |
| 4 | `platformFees` | `uint96` | `uint96` |        The amount of platform fees owed. |
| 5 | `liquidator` | `address` | `address` |          The address of the liquidator. |


<br />

### `loanTransferAdmin` 

Returns the current &#x60;loanTransferAdmin&#x60; address.

```solidity
    function loanTransferAdmin()
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

### `minRatioFor` 

Gets the minimum ratio for a collateral asset.

```solidity
    function minRatioFor(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `paymentCounter` 

Gets the payment counter.

```solidity
    function paymentCounter()
        view
        returns (
            uint24
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint24` | `uint24` |  |


<br />

### `paymentIdOf` 

Gets the payment if for the given loan.

```solidity
    function paymentIdOf(
        address
    )
        view
        returns (
            uint24
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint24` | `uint24` |  |


<br />

### `payments` 

Gets the information for a payment.

```solidity
    function payments(
        uint256
    )
        view
        returns (
            uint24 platformManagementFeeRate,
            uint24 delegateManagementFeeRate,
            uint48 startDate,
            uint48 paymentDueDate,
            uint128 incomingNetInterest,
            uint128 refinanceInterest,
            uint256 issuanceRate
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `platformManagementFeeRate` | `uint24` | `uint24` | The value for the platform management fee rate. |
| 1 | `delegateManagementFeeRate` | `uint24` | `uint24` | The value for the delegate management fee rate. |
| 2 | `startDate` | `uint48` | `uint48` |                 The start date of the payment. |
| 3 | `paymentDueDate` | `uint48` | `uint48` |            The timestamp of the payment due date. |
| 4 | `incomingNetInterest` | `uint128` | `uint128` |       The amount of incoming net interest. |
| 5 | `refinanceInterest` | `uint128` | `uint128` |         The amount of refinance interest. |
| 6 | `issuanceRate` | `uint256` | `uint256` |              The issuance rate for the loan. |


<br />

### `paymentWithEarliestDueDate` 

Gets the payment id with the earliest due date.

```solidity
    function paymentWithEarliestDueDate()
        view
        returns (
            uint24
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint24` | `uint24` |  |


<br />

### `pool` 

Gets the address of the pool.

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

### `poolManager` 

Gets the address of the pool manager.

```solidity
    function poolManager()
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

### `principalOut` 

Gets the amount of principal out.

```solidity
    function principalOut()
        view
        returns (
            uint128
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint128` | `uint128` |  |


<br />

### `sortedPayments` 

Gets the information of the sorted list.

```solidity
    function sortedPayments(
        uint256
    )
        view
        returns (
            uint24 previous,
            uint24 next,
            uint48 paymentDueDate
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previous` | `uint24` | `uint24` |  |
| 1 | `next` | `uint24` | `uint24` |  |
| 2 | `paymentDueDate` | `uint48` | `uint48` |  |


<br />

### `unrealizedLosses` 

Returns the amount unrealized losses.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint128
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint128` | `uint128` |  |


<br />


## Events

### `Initialized`



```solidity
    event Initialized(
        address pool_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool_` | `address` | `address` |  |

<br />

