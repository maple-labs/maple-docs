# Maple Open Term Loan Refinancer



<br />


## Functions

### `borrower`



```solidity
    function borrower()
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

### `calledPrincipal`



```solidity
    function calledPrincipal()
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

### `dateCalled`



```solidity
    function dateCalled()
        view
        returns (
            uint40
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint40` | `uint40` |  |


<br />

### `dateFunded`



```solidity
    function dateFunded()
        view
        returns (
            uint40
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint40` | `uint40` |  |


<br />

### `dateImpaired`



```solidity
    function dateImpaired()
        view
        returns (
            uint40
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint40` | `uint40` |  |


<br />

### `datePaid`



```solidity
    function datePaid()
        view
        returns (
            uint40
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint40` | `uint40` |  |


<br />

### `decreasePrincipal`

Function to decrease the principal during a refinance.

```solidity
    function decreasePrincipal(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of which the value will decrease by. |


<br />

### `delegateServiceFeeRate`



```solidity
    function delegateServiceFeeRate()
        view
        returns (
            uint64
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint64` | `uint64` |  |


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

### `gracePeriod`



```solidity
    function gracePeriod()
        view
        returns (
            uint32
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint32` | `uint32` |  |


<br />

### `increasePrincipal`

Function to increase the principal during a refinance.

```solidity
    function increasePrincipal(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of which the value will increase by. |


<br />

### `interestRate`



```solidity
    function interestRate()
        view
        returns (
            uint64
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint64` | `uint64` |  |


<br />

### `lateFeeRate`



```solidity
    function lateFeeRate()
        view
        returns (
            uint64
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint64` | `uint64` |  |


<br />

### `lateInterestPremiumRate`



```solidity
    function lateInterestPremiumRate()
        view
        returns (
            uint64
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint64` | `uint64` |  |


<br />

### `lender`



```solidity
    function lender()
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

### `noticePeriod`



```solidity
    function noticePeriod()
        view
        returns (
            uint32
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint32` | `uint32` |  |


<br />

### `paymentInterval`



```solidity
    function paymentInterval()
        view
        returns (
            uint32
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint32` | `uint32` |  |


<br />

### `pendingBorrower`



```solidity
    function pendingBorrower()
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

### `pendingLender`



```solidity
    function pendingLender()
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

### `platformServiceFeeRate`



```solidity
    function platformServiceFeeRate()
        view
        returns (
            uint64
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint64` | `uint64` |  |


<br />

### `principal`



```solidity
    function principal()
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

### `refinanceCommitment`



```solidity
    function refinanceCommitment()
        view
        returns (
            bytes32
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bytes32` | `bytes32` |  |


<br />

### `setDelegateServiceFeeRate`

Function to set the delegateServiceFeeRate during a refinance.         The rate is denominated in 1e18 units.

```solidity
    function setDelegateServiceFeeRate(
        uint64 delegateServiceFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `delegateServiceFeeRate_` | `uint64` | `uint64` | The new value for delegateServiceFeeRate. |


<br />

### `setGracePeriod`

Function to set the gracePeriod during a refinance.

```solidity
    function setGracePeriod(
        uint32 gracePeriod_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `gracePeriod_` | `uint32` | `uint32` | The new value for gracePeriod. |


<br />

### `setInterestRate`

Function to set the interestRate during a refinance. The interest rate is measured with 18 decimals of precision.

```solidity
    function setInterestRate(
        uint64 interestRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `interestRate_` | `uint64` | `uint64` | The new value for interestRate. |


<br />

### `setLateFeeRate`

Function to set the lateFeeRate during a refinance.

```solidity
    function setLateFeeRate(
        uint64 lateFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateFeeRate_` | `uint64` | `uint64` | The new value for lateFeeRate. |


<br />

### `setLateInterestPremiumRate`

Function to set the lateInterestPremiumRate during a refinance.

```solidity
    function setLateInterestPremiumRate(
        uint64 lateInterestPremiumRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateInterestPremiumRate_` | `uint64` | `uint64` | The new value for lateInterestPremiumRate. |


<br />

### `setNoticePeriod`

Function to set the noticePeriod during a refinance.

```solidity
    function setNoticePeriod(
        uint32 noticePeriod_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `noticePeriod_` | `uint32` | `uint32` | The new value for noticePeriod. |


<br />

### `setPaymentInterval`

Function to set the paymentInterval during a refinance.         The interval is denominated in seconds.

```solidity
    function setPaymentInterval(
        uint32 paymentInterval_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentInterval_` | `uint32` | `uint32` | The new value for paymentInterval. |


<br />


## Events

### `DelegateServiceFeeRateSet`

The value for the service fee rate for the PoolDelegate (1e18 units).

```solidity
    event DelegateServiceFeeRateSet(
        uint64 delegateServiceFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `delegateServiceFeeRate_` | `uint64` | `uint64` | The new value for delegateServiceFeeRate. |

<br />

### `GracePeriodSet`

A new value for gracePeriod has been set.

```solidity
    event GracePeriodSet(
        uint256 gracePeriod_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `gracePeriod_` | `uint256` | `uint256` | The new value for gracePeriod. |

<br />

### `InterestRateSet`

A new value for interestRate has been set.

```solidity
    event InterestRateSet(
        uint64 interestRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `interestRate_` | `uint64` | `uint64` | The new value for interestRate. |

<br />

### `LateFeeRateSet`

A new value for lateFeeRate has been set.

```solidity
    event LateFeeRateSet(
        uint64 lateFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateFeeRate_` | `uint64` | `uint64` | The new value for lateFeeRate. |

<br />

### `LateInterestPremiumRateSet`

A new value for lateInterestPremiumRate has been set.

```solidity
    event LateInterestPremiumRateSet(
        uint64 lateInterestPremiumRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateInterestPremiumRate_` | `uint64` | `uint64` | The new value for lateInterestPremiumRate. |

<br />

### `NoticePeriodSet`

A new value for noticePeriod has been set.

```solidity
    event NoticePeriodSet(
        uint256 noticePeriod_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `noticePeriod_` | `uint256` | `uint256` | The new value for noticedPeriod. |

<br />

### `PaymentIntervalSet`

A new value for paymentInterval has been set.

```solidity
    event PaymentIntervalSet(
        uint256 paymentInterval_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentInterval_` | `uint256` | `uint256` | The new value for paymentInterval. |

<br />

### `PrincipalDecreased`

The value of the principal has been decreased.

```solidity
    event PrincipalDecreased(
        uint256 decreasedBy_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `decreasedBy_` | `uint256` | `uint256` | The amount of which the value was decreased by. |

<br />

### `PrincipalIncreased`

The value of the principal has been increased.

```solidity
    event PrincipalIncreased(
        uint256 increasedBy_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `increasedBy_` | `uint256` | `uint256` | The amount of which the value was increased by. |

<br />

