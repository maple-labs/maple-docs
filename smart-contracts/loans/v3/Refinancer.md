# Loan Refinancer



<br />


## Functions

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

### `setCollateralRequired`

Function to set the collateralRequired during a refinance.

```solidity
    function setCollateralRequired(
        uint256 collateralRequired_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralRequired_` | `uint256` | `uint256` | The new value for collateralRequired. |


<br />

### `setEarlyFeeRate`

Function to set the earlyFeeRate during a refinance.

```solidity
    function setEarlyFeeRate(
        uint256 earlyFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `earlyFeeRate_` | `uint256` | `uint256` | The new value for earlyFeeRate. |


<br />

### `setEndingPrincipal`

Function to set the endingPrincipal during a refinance.

```solidity
    function setEndingPrincipal(
        uint256 endingPrincipal_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `endingPrincipal_` | `uint256` | `uint256` | The new value for endingPrincipal. |


<br />

### `setGracePeriod`

Function to set the gracePeriod during a refinance.

```solidity
    function setGracePeriod(
        uint256 gracePeriod_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `gracePeriod_` | `uint256` | `uint256` | The new value for gracePeriod. |


<br />

### `setInterestRate`

Function to set the interestRate during a refinance. The interest rate is measured with 18 decimals of precision.

```solidity
    function setInterestRate(
        uint256 interestRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `interestRate_` | `uint256` | `uint256` | The new value for interestRate. |


<br />

### `setLateFeeRate`

Function to set the lateFeeRate during a refinance.

```solidity
    function setLateFeeRate(
        uint256 lateFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateFeeRate_` | `uint256` | `uint256` | The new value for lateFeeRate. |


<br />

### `setLateInterestPremium`

Function to set the lateInterestPremium during a refinance.

```solidity
    function setLateInterestPremium(
        uint256 lateInterestPremium_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateInterestPremium_` | `uint256` | `uint256` | The new value for lateInterestPremium. |


<br />

### `setPaymentInterval`

Function to set the paymentInterval during a refinance.         The interval is denominated in seconds.

```solidity
    function setPaymentInterval(
        uint256 paymentInterval_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentInterval_` | `uint256` | `uint256` | The new value for paymentInterval. |


<br />

### `setPaymentsRemaining`

Function to set the paymentsRemaining during a refinance.

```solidity
    function setPaymentsRemaining(
        uint256 paymentsRemaining_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentsRemaining_` | `uint256` | `uint256` | The new value for paymentsRemaining. |


<br />


## Events

### `CollateralRequiredSet`

A new value for collateralRequired has been set.

```solidity
    event CollateralRequiredSet(
        uint256 collateralRequired_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralRequired_` | `uint256` | `uint256` | The new value for collateralRequired. |

<br />

### `EarlyFeeRateSet`

A new value for earlyFeeRate has been set.

```solidity
    event EarlyFeeRateSet(
        uint256 earlyFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `earlyFeeRate_` | `uint256` | `uint256` | The new value for earlyFeeRate. |

<br />

### `EndingPrincipalSet`

A new value for endingPrincipal has been set.

```solidity
    event EndingPrincipalSet(
        uint256 endingPrincipal_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `endingPrincipal_` | `uint256` | `uint256` | The new value for endingPrincipal. |

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
        uint256 interestRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `interestRate_` | `uint256` | `uint256` | The new value for interestRate. |

<br />

### `LateFeeRateSet`

A new value for lateFeeRate has been set.

```solidity
    event LateFeeRateSet(
        uint256 lateFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateFeeRate_` | `uint256` | `uint256` | The new value for lateFeeRate. |

<br />

### `LateInterestPremiumSet`

A new value for lateInterestPremium has been set.

```solidity
    event LateInterestPremiumSet(
        uint256 lateInterestPremium_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateInterestPremium_` | `uint256` | `uint256` | The new value for lateInterestPremium. |

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

### `PaymentsRemainingSet`

A new value for paymentsRemaining has been set.

```solidity
    event PaymentsRemainingSet(
        uint256 paymentsRemaining_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentsRemaining_` | `uint256` | `uint256` | The new value for paymentsRemaining. |

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
