# Maple Fixed Term Loan Manager Initializer



<br />


## Functions

### `accountedInterest`



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

Decodes the initialization arguments of a loan manager.

```solidity
    function decodeArguments(
        bytes calldata_
    )
        pure
        returns (
            address poolManager_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `calldata_` | `bytes` | `bytes` | ABI encoded address of the pool manager. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | Address of the pool manager. |


<br />

### `domainEnd`



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

Encodes the initialization arguments of a loan manager.

```solidity
    function encodeArguments(
        address poolManager_
    )
        pure
        returns (
            bytes calldata_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | Address of the pool manager. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `calldata_` | `bytes` | `bytes` |    ABI encoded address of the pool manager. |


<br />

### `fundsAsset`



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
| 0 | `triggeredByGovernor` | `bool` | `bool` |  |
| 1 | `principal` | `uint128` | `uint128` |  |
| 2 | `interest` | `uint120` | `uint120` |  |
| 3 | `lateInterest` | `uint256` | `uint256` |  |
| 4 | `platformFees` | `uint96` | `uint96` |  |
| 5 | `liquidator` | `address` | `address` |  |


<br />

### `minRatioFor`



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
| 0 | `platformManagementFeeRate` | `uint24` | `uint24` |  |
| 1 | `delegateManagementFeeRate` | `uint24` | `uint24` |  |
| 2 | `startDate` | `uint48` | `uint48` |  |
| 3 | `paymentDueDate` | `uint48` | `uint48` |  |
| 4 | `incomingNetInterest` | `uint128` | `uint128` |  |
| 5 | `refinanceInterest` | `uint128` | `uint128` |  |
| 6 | `issuanceRate` | `uint256` | `uint256` |  |


<br />

### `paymentWithEarliestDueDate`



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

### `poolManager`



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

Emitted when the loan manager is initialized.

```solidity
    event Initialized(
        address poolManager_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | Address of the associated pool manager. |

<br />

