# FixedTermLoanFeeManager

Manages fee accounting and transfers for fixed‑term loans, including delegate and platform origination fees and service fees. Reads platform fee rates from Globals, computes amounts over time, and transfers proceeds to the Pool Delegate and Maple Treasury as applicable.

## Constructor

```solidity
    constructor(
        address globals_
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `globals_` | `address` |   `address`   |             |


## Functions

### `delegateOriginationFee`

Gets the delegate origination fee for the given loan.

```solidity
    function delegateOriginationFee(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |


### `delegateRefinanceServiceFee`

Gets the delegate service fee rate for the given loan.

```solidity
    function delegateRefinanceServiceFee(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |


### `delegateServiceFee`

Gets the delegate service fee rate for the given loan.

```solidity
    function delegateServiceFee(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



### `getDelegateServiceFeesForPeriod`

Gets the delegate service fee for the given loan.

```solidity
    function getDelegateServiceFeesForPeriod(
        address loan_,
        uint256 interval_
    )
        view
        returns (
            uint256 delegateServiceFee_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                           |
| :---: | :---------: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   |   `loan_`   | `address` |   `address`   | The address of the loan contract.                     |
|   1   | `interval_` | `uint256` |   `uint256`   | The time, in seconds, to get the proportional fee for |

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                                    |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `delegateServiceFee_` | `uint256` |   `uint256`   | The amount of delegate service fee to be paid. |


### `getOriginationFees`

Gets the sum of all origination fees for the given loan.

```solidity
    function getOriginationFees(
        address loan_,
        uint256 principalRequested_
    )
        view
        returns (
            uint256 originationFees_
        );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                    |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   |        `loan_`        | `address` |   `address`   | The address of the loan contract.              |
|   1   | `principalRequested_` | `uint256` |   `uint256`   | The amount of principal requested in the loan. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `originationFees_` | `uint256` |   `uint256`   | The amount of origination fees to be paid. |


### `getPlatformOriginationFee`

Gets the platform origination fee value for the given loan.

```solidity
    function getPlatformOriginationFee(
        address loan_,
        uint256 principalRequested_
    )
        view
        returns (
            uint256 platformOriginationFee_
        );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                    |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   |        `loan_`        | `address` |   `address`   | The address of the loan contract.              |
|   1   | `principalRequested_` | `uint256` |   `uint256`   | The amount of principal requested in the loan. |

#### Return Values:

| Index |            Name           |    Type   | Internal Type | Description                                        |
| :---: | :-----------------------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   | `platformOriginationFee_` | `uint256` |   `uint256`   | The amount of platform origination fee to be paid. |


### `getPlatformServiceFeeForPeriod`

Gets the delegate service fee for the given loan.

```solidity
    function getPlatformServiceFeeForPeriod(
        address loan_,
        uint256 principalRequested_,
        uint256 interval_
    )
        view
        returns (
            uint256 platformServiceFee_
        );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                           |
| :---: | :-------------------: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   |        `loan_`        | `address` |   `address`   | The address of the loan contract.                     |
|   1   | `principalRequested_` | `uint256` |   `uint256`   | The amount of principal requested in the loan.        |
|   2   |      `interval_`      | `uint256` |   `uint256`   | The time, in seconds, to get the proportional fee for |

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                                    |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `platformServiceFee_` | `uint256` |   `uint256`   | The amount of platform service fee to be paid. |


### `getServiceFeeBreakdown`

Gets the service fees for the given interval.

```solidity
    function getServiceFeeBreakdown(
        address loan_,
        uint256 numberOfPayments_
    )
        view
        returns (
            uint256 delegateServiceFee_,
            uint256 delegateRefinanceFee_,
            uint256 platformServiceFee_,
            uint256 platformRefinanceFee_
        );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                        |
| :---: | :-----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   |       `loan_`       | `address` |   `address`   | The address of the loan contract.  |
|   1   | `numberOfPayments_` | `uint256` |   `uint256`   | The number of payments being paid. |

#### Return Values:

| Index |           Name          |    Type   | Internal Type | Description                                      |
| :---: | :---------------------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |  `delegateServiceFee_`  | `uint256` |   `uint256`   | The amount of delegate service fee to be paid.   |
|   1   | `delegateRefinanceFee_` | `uint256` |   `uint256`   | The amount of delegate refinance fee to be paid. |
|   2   |  `platformServiceFee_`  | `uint256` |   `uint256`   | The amount of platform service fee to be paid.   |
|   3   | `platformRefinanceFee_` | `uint256` |   `uint256`   | The amount of platform refinance fee to be paid. |


### `getServiceFees`

Gets the service fees for the given interval.

```solidity
    function getServiceFees(
        address loan_,
        uint256 numberOfPayments_
    )
        view
        returns (
            uint256 serviceFees_
        );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                        |
| :---: | :-----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   |       `loan_`       | `address` |   `address`   | The address of the loan contract.  |
|   1   | `numberOfPayments_` | `uint256` |   `uint256`   | The number of payments being paid. |

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                                    |
| :---: | :------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `serviceFees_` | `uint256` |   `uint256`   | The amount of platform service fee to be paid. |


### `getServiceFeesForPeriod`

Gets the service fees for the given interval.

```solidity
    function getServiceFeesForPeriod(
        address loan_,
        uint256 interval_
    )
        view
        returns (
            uint256 serviceFee_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                           |
| :---: | :---------: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   |   `loan_`   | `address` |   `address`   | The address of the loan contract.                     |
|   1   | `interval_` | `uint256` |   `uint256`   | The time, in seconds, to get the proportional fee for |

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                                    |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `serviceFee_` | `uint256` |   `uint256`   | The amount of platform service fee to be paid. |


### `globals`

Gets the global contract address.

```solidity
    function globals()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |


### `payOriginationFees`

Called during \`fundLoan\`, performs fee payments to poolDelegate and treasury.

```solidity
    function payOriginationFees(
        address asset_,
        uint256 principalRequested_
    )
        nonpayable
        returns (
            uint256 feePaid_
        );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                                                    |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------------------------------------------------ |
|   0   |        `asset_`       | `address` |   `address`   | The address asset in which fees were paid.                                     |
|   1   | `principalRequested_` | `uint256` |   `uint256`   | The total amount of principal requested, which will be used to calculate fees. |

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                    |
| :---: | :--------: | :-------: | :-----------: | ------------------------------ |
|   0   | `feePaid_` | `uint256` |   `uint256`   | The total amount of fees paid. |


### `payServiceFees`

Called during \`makePayment\`, performs fee payments to the pool delegate and treasury.

```solidity
    function payServiceFees(
        address asset_,
        uint256 numberOfPayments_
    )
        nonpayable
        returns (
            uint256 feePaid_
        );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                                                 |
| :---: | :-----------------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   |       `asset_`      | `address` |   `address`   | The address asset in which fees were paid.                  |
|   1   | `numberOfPayments_` | `uint256` |   `uint256`   | The number of payments for which service fees will be paid. |

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `feePaid_` | `uint256` |   `uint256`   |             |


### `platformRefinanceServiceFee`

Gets the platform fee rate for the given loan.

```solidity
    function platformRefinanceServiceFee(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |


### `platformServiceFee`

Gets the platform fee rate for the given loan.

```solidity
    function platformServiceFee(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |


### `updateDelegateFeeTerms`

Called during loan creation or refinance, sets the fee terms.

```solidity
    function updateDelegateFeeTerms(
        uint256 delegateOriginationFee_,
        uint256 delegateServiceFee_
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |    Type   | Internal Type | Description                                        |
| :---: | :-----------------------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   | `delegateOriginationFee_` | `uint256` |   `uint256`   | The amount of delegate origination fee to be paid. |
|   1   |   `delegateServiceFee_`   | `uint256` |   `uint256`   | The amount of delegate service fee to be paid.     |


### `updatePlatformServiceFee`

Function called by loans to update the saved platform service fee rate.

```solidity
    function updatePlatformServiceFee(
        uint256 principalRequested_,
        uint256 paymentInterval_
    )
        nonpayable;
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description |
| :---: | :-------------------: | :-------: | :-----------: | ----------- |
|   0   | `principalRequested_` | `uint256` |   `uint256`   |             |
|   1   |   `paymentInterval_`  | `uint256` |   `uint256`   |             |


### `updateRefinanceServiceFees`

Called during loan refinance to save the partial service fees accrued.

```solidity
    function updateRefinanceServiceFees(
        uint256 principalRequested_,
        uint256 timeSinceLastDueDate_
    )
        nonpayable;
```

#### Parameters:

| Index |           Name          |    Type   | Internal Type | Description                                      |
| :---: | :---------------------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |  `principalRequested_`  | `uint256` |   `uint256`   | The amount of principal pre-refinance requested. |
|   1   | `timeSinceLastDueDate_` | `uint256` |   `uint256`   | The amount of time since last payment due date.  |


## Events

### `FeeTermsUpdated`

New fee terms have been set.

```solidity
    event FeeTermsUpdated(
        address loan_,
        uint256 delegateOriginationFee_,
        uint256 delegateServiceFee_
    );
```

#### Parameters:

| Index |            Name           |    Type   | Internal Type | Description                                 |
| :---: | :-----------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |          `loan_`          | `address` |   `address`   | The address of the loan contract.           |
|   1   | `delegateOriginationFee_` | `uint256` |   `uint256`   | The new value for delegate origination fee. |
|   2   |   `delegateServiceFee_`   | `uint256` |   `uint256`   | The new value for delegate service fee.     |


### `OriginationFeesPaid`

A fee payment was made.

```solidity
    event OriginationFeesPaid(
        address loan_,
        uint256 delegateOriginationFee_,
        uint256 platformOriginationFee_
    );
```

#### Parameters:

| Index |            Name           |    Type   | Internal Type | Description                                  |
| :---: | :-----------------------: | :-------: | :-----------: | -------------------------------------------- |
|   0   |          `loan_`          | `address` |   `address`   | The address of the loan contract.            |
|   1   | `delegateOriginationFee_` | `uint256` |   `uint256`   | The amount of delegate origination fee paid. |
|   2   | `platformOriginationFee_` | `uint256` |   `uint256`   | The amount of platform origination fee paid. |


### `PartialRefinanceServiceFeesUpdated`

New fee terms have been set.

```solidity
    event PartialRefinanceServiceFeesUpdated(
        address loan_,
        uint256 partialPlatformServiceFee_,
        uint256 partialDelegateServiceFee_
    );
```

#### Parameters:

| Index |             Name             |    Type   | Internal Type | Description                             |
| :---: | :--------------------------: | :-------: | :-----------: | --------------------------------------- |
|   0   |            `loan_`           | `address` |   `address`   | The address of the loan contract.       |
|   1   | `partialPlatformServiceFee_` | `uint256` |   `uint256`   | The value for the platform service fee. |
|   2   | `partialDelegateServiceFee_` | `uint256` |   `uint256`   | The value for the delegate service fee. |


### `PlatformServiceFeeUpdated`

New fee terms have been set.

```solidity
    event PlatformServiceFeeUpdated(
        address loan_,
        uint256 platformServiceFee_
    );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                 |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |        `loan_`        | `address` |   `address`   | The address of the loan contract.           |
|   1   | `platformServiceFee_` | `uint256` |   `uint256`   | The new value for the platform service fee. |


### `ServiceFeesPaid`

A fee payment was made.

```solidity
    event ServiceFeesPaid(
        address loan_,
        uint256 delegateServiceFee_,
        uint256 partialRefinanceDelegateServiceFee_,
        uint256 platformServiceFee_,
        uint256 partialRefinancePlatformServiceFee_
    );
```

#### Parameters:

| Index |                  Name                 |    Type   | Internal Type | Description                                                     |
| :---: | :-----------------------------------: | :-------: | :-----------: | --------------------------------------------------------------- |
|   0   |                `loan_`                | `address` |   `address`   | The address of the loan contract.                               |
|   1   |         `delegateServiceFee_`         | `uint256` |   `uint256`   | The amount of delegate service fee paid.                        |
|   2   | `partialRefinanceDelegateServiceFee_` | `uint256` |   `uint256`   | The amount of partial delegate service fee from refinance paid. |
|   3   |         `platformServiceFee_`         | `uint256` |   `uint256`   | The amount of platform service fee paid.                        |
|   4   | `partialRefinancePlatformServiceFee_` | `uint256` |   `uint256`   | The amount of partial platform service fee from refinance paid. |
