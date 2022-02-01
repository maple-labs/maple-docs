# Loan Refinancer

Refinancer uses storage from a MapleLoan defined by MapleLoanInternals.

\


## Functions

### `decreasePrincipal`

Function to decrease the principal during a refinance.

```solidity
    function decreasePrincipal(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                     |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `amount_` | `uint256` |   `uint256`   | The amount of which the value will decrease by. |

\


### `increasePrincipal`

Function to increase the principal during a refinance.

```solidity
    function increasePrincipal(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                     |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `amount_` | `uint256` |   `uint256`   | The amount of which the value will increase by. |

\


### `setCollateralRequired`

Function to set the collateralRequired during a refinance.

```solidity
    function setCollateralRequired(
        uint256 collateralRequired_
    )
        nonpayable;
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                           |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `collateralRequired_` | `uint256` |   `uint256`   | The new value for collateralRequired. |

\


### `setEarlyFeeRate`

Function to set the earlyFeeRate during a refinance.

```solidity
    function setEarlyFeeRate(
        uint256 earlyFeeRate_
    )
        nonpayable;
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                     |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `earlyFeeRate_` | `uint256` |   `uint256`   | The new value for earlyFeeRate. |

\


### `setEndingPrincipal`

Function to set the endingPrincipal during a refinance.

```solidity
    function setEndingPrincipal(
        uint256 endingPrincipal_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                        |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `endingPrincipal_` | `uint256` |   `uint256`   | The new value for endingPrincipal. |

\


### `setGracePeriod`

Function to set the gracePeriod during a refinance.

```solidity
    function setGracePeriod(
        uint256 gracePeriod_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                    |
| :---: | :------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `gracePeriod_` | `uint256` |   `uint256`   | The new value for gracePeriod. |

\


### `setInterestRate`

Function to set the interestRate during a refinance.

```solidity
    function setInterestRate(
        uint256 interestRate_
    )
        nonpayable;
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                     |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `interestRate_` | `uint256` |   `uint256`   | The new value for interestRate. |

\


### `setLateFeeRate`

Function to set the lateFeeRate during a refinance.

```solidity
    function setLateFeeRate(
        uint256 lateFeeRate_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                    |
| :---: | :------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `lateFeeRate_` | `uint256` |   `uint256`   | The new value for lateFeeRate. |

\


### `setLateInterestPremium`

Function to set the lateInterestPremium during a refinance.

```solidity
    function setLateInterestPremium(
        uint256 lateInterestPremium_
    )
        nonpayable;
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description                            |
| :---: | :--------------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `lateInterestPremium_` | `uint256` |   `uint256`   | The new value for lateInterestPremium. |

\


### `setPaymentInterval`

Function to set the paymentInterval during a refinance.

```solidity
    function setPaymentInterval(
        uint256 paymentInterval_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                        |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `paymentInterval_` | `uint256` |   `uint256`   | The new value for paymentInterval. |

\


### `setPaymentsRemaining`

Function to set the paymentsRemaining during a refinance.

```solidity
    function setPaymentsRemaining(
        uint256 paymentsRemaining_
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                          |
| :---: | :------------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `paymentsRemaining_` | `uint256` |   `uint256`   | The new value for paymentsRemaining. |

\


## Events

### `CollateralRequiredSet`

A new value for collateralRequired has been set.

```solidity
    event CollateralRequiredSet(
        uint256 collateralRequired_
    );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                           |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `collateralRequired_` | `uint256` |   `uint256`   | The new value for collateralRequired. |

\


### `EarlyFeeRateSet`

A new value for earlyFeeRate has been set.

```solidity
    event EarlyFeeRateSet(
        uint256 earlyFeeRate_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                     |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `earlyFeeRate_` | `uint256` |   `uint256`   | The new value for earlyFeeRate. |

\


### `EndingPrincipalSet`

A new value for endingPrincipal has been set.

```solidity
    event EndingPrincipalSet(
        uint256 endingPrincipal_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                        |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `endingPrincipal_` | `uint256` |   `uint256`   | The new value for endingPrincipal. |

\


### `GracePeriodSet`

A new value for gracePeriod has been set.

```solidity
    event GracePeriodSet(
        uint256 gracePeriod_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                    |
| :---: | :------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `gracePeriod_` | `uint256` |   `uint256`   | The new value for gracePeriod. |

\


### `InterestRateSet`

A new value for interestRate has been set.

```solidity
    event InterestRateSet(
        uint256 interestRate_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                     |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `interestRate_` | `uint256` |   `uint256`   | The new value for interestRate. |

\


### `LateFeeRateSet`

A new value for lateFeeRate has been set.

```solidity
    event LateFeeRateSet(
        uint256 lateFeeRate_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                    |
| :---: | :------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `lateFeeRate_` | `uint256` |   `uint256`   | The new value for lateFeeRate. |

\


### `LateInterestPremiumSet`

A new value for lateInterestPremium has been set.

```solidity
    event LateInterestPremiumSet(
        uint256 lateInterestPremium_
    );
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description                            |
| :---: | :--------------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `lateInterestPremium_` | `uint256` |   `uint256`   | The new value for lateInterestPremium. |

\


### `PaymentIntervalSet`

A new value for paymentInterval has been set.

```solidity
    event PaymentIntervalSet(
        uint256 paymentInterval_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                        |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `paymentInterval_` | `uint256` |   `uint256`   | The new value for paymentInterval. |

\


### `PaymentsRemainingSet`

A new value for paymentsRemaining has been set.

```solidity
    event PaymentsRemainingSet(
        uint256 paymentsRemaining_
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                          |
| :---: | :------------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `paymentsRemaining_` | `uint256` |   `uint256`   | The new value for paymentsRemaining. |

\


### `PrincipalDecreased`

The value of the principal has been decreased.

```solidity
    event PrincipalDecreased(
        uint256 decreasedBy_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                     |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `decreasedBy_` | `uint256` |   `uint256`   | The amount of which the value was decreased by. |

\


### `PrincipalIncreased`

The value of the principal has been increased.

```solidity
    event PrincipalIncreased(
        uint256 increasedBy_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                     |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `increasedBy_` | `uint256` |   `uint256`   | The amount of which the value was increased by. |

\
