# OpenTermLoanManager

\


## Functions

### `HUNDRED_PERCENT`

Returns the value considered as the hundred percent.

```solidity
    function HUNDRED_PERCENT()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `PRECISION`

Returns the precision used for the contract.

```solidity
    function PRECISION()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint112` |   `uint112`   |             |

\


### `accruedInterest`

Gets the amount of accrued interest up until this point in time.

```solidity
    function accruedInterest()
        view
        returns (
            uint256 accruedInterest_
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                                 |
| :---: | :----------------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   | `accruedInterest_` | `uint256` |   `uint256`   | The amount of accrued interest up until this point in time. |

\


### `assetsUnderManagement`

Gets the amount of assets under the management of the contract.

```solidity
    function assetsUnderManagement()
        view
        returns (
            uint256 assetsUnderManagement_
        );
```

#### Return Values:

| Index |           Name           |    Type   | Internal Type | Description                                                |
| :---: | :----------------------: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   | `assetsUnderManagement_` | `uint256` |   `uint256`   | The amount of assets under the management of the contract. |

\


### `callPrincipal`

Calls a loan.

```solidity
    function callPrincipal(
        address loan_,
        uint256 principal_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                |
| :---: | :----------: | :-------: | :-----------: | ------------------------------------------ |
|   0   |    `loan_`   | `address` |   `address`   | Loan to be called.                         |
|   1   | `principal_` | `uint256` |   `uint256`   | Amount of principal to call the Loan with. |

\


### `claim`

Called by loans when payments are made, updating the accounting.

```solidity
    function claim(
        int256 principal_,
        uint256 interest_,
        uint256 delegateServiceFee_,
        uint256 platformServiceFee_,
        uint40 nextPaymentDueDate_
    )
        nonpayable;
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                                                                                                  |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------- |
|   0   |      `principal_`     |  `int256` |    `int256`   | The difference in principal. Positive if net principal change moves funds into pool, negative if it moves funds out of pool. |
|   1   |      `interest_`      | `uint256` |   `uint256`   | The amount of interest paid.                                                                                                 |
|   2   | `delegateServiceFee_` | `uint256` |   `uint256`   | The amount of delegate service fee paid.                                                                                     |
|   3   | `platformServiceFee_` | `uint256` |   `uint256`   | The amount of platform service fee paid.                                                                                     |
|   4   | `nextPaymentDueDate_` |  `uint40` |    `uint40`   |                                                                                                                              |

\


### `domainStart`

Gets the timestamp of the domain start.

```solidity
    function domainStart()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |

\


### `factory`

The address of the proxy factory.

```solidity
    function factory()
        view
        returns (
            address factory_
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `factory_` | `address` |   `address`   |             |

\


### `fund`

Funds a new loan.

```solidity
    function fund(
        address loan_
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description        |
| :---: | :-----: | :-------: | :-----------: | ------------------ |
|   0   | `loan_` | `address` |   `address`   | Loan to be funded. |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `impairLoan`

Triggers the impairment of a loan.

```solidity
    function impairLoan(
        address loan_
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                          |
| :---: | :-----: | :-------: | :-----------: | ------------------------------------ |
|   0   | `loan_` | `address` |   `address`   | Loan to trigger the loan impairment. |

\


### `impairmentFor`

Gets the information for an impairment.

```solidity
    function impairmentFor(
        address
    )
        view
        returns (
            uint40 impairedDate,
            bool impairedByGovernor
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index |         Name         |   Type   | Internal Type | Description                                           |
| :---: | :------------------: | :------: | :-----------: | ----------------------------------------------------- |
|   0   |    `impairedDate`    | `uint40` |    `uint40`   | The date the impairment was triggered.                |
|   1   | `impairedByGovernor` |  `bool`  |     `bool`    | True if the impairment was triggered by the governor. |

\


### `implementation`

The address of the implementation contract being proxied.

```solidity
    function implementation()
        view
        returns (
            address implementation_
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `implementation_` | `address` |   `address`   |             |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `migrate`

Modifies the proxy's storage by delegate-calling a migrator contract with some arguments. Access control logic critical since caller can force a selfdestruct via a malicious \`migrator\_\` which is delegatecalled.

```solidity
    function migrate(
        address migrator_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                      |
| :---: | :----------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |  `migrator_` | `address` |   `address`   | The address of a migrator contract.              |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | Some encoded arguments to use for the migration. |

\


### `paymentFor`

Gets the information for a payment.

```solidity
    function paymentFor(
        address
    )
        view
        returns (
            uint24 platformManagementFeeRate,
            uint24 delegateManagementFeeRate,
            uint40 startDate,
            uint168 issuanceRate
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index |             Name            |    Type   | Internal Type | Description                                     |
| :---: | :-------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `platformManagementFeeRate` |  `uint24` |    `uint24`   | The value for the platform management fee rate. |
|   1   | `delegateManagementFeeRate` |  `uint24` |    `uint24`   | The value for the delegate management fee rate. |
|   2   |         `startDate`         |  `uint40` |    `uint40`   | The start date of the payment.                  |
|   3   |        `issuanceRate`       | `uint168` |   `uint168`   | The issuance rate for the loan.                 |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint128` |   `uint128`   |             |

\


### `proposeNewTerms`

Proposes new terms for a loan.

```solidity
    function proposeNewTerms(
        address loan_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                   |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------------------- |
|   0   |    `loan_`    | `address` |   `address`   | The loan to propose new changes to.                           |
|   1   | `refinancer_` | `address` |   `address`   | The refinancer to use in the refinance.                       |
|   2   |  `deadline_`  | `uint256` |   `uint256`   | The deadline by which the borrower must accept the new terms. |
|   3   |    `calls_`   | `bytes[]` |   `bytes[]`   | The array of calls to be made to the refinancer.              |

\


### `rejectNewTerms`

Reject/cancel proposed new terms for a loan.

```solidity
    function rejectNewTerms(
        address loan_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                   |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------------------- |
|   0   |    `loan_`    | `address` |   `address`   | The loan with the proposed new changes.                       |
|   1   | `refinancer_` | `address` |   `address`   | The refinancer to use in the refinance.                       |
|   2   |  `deadline_`  | `uint256` |   `uint256`   | The deadline by which the borrower must accept the new terms. |
|   3   |    `calls_`   | `bytes[]` |   `bytes[]`   | The array of calls to be made to the refinancer.              |

\


### `removeCall`

Removes a loan call.

```solidity
    function removeCall(
        address loan_
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description              |
| :---: | :-----: | :-------: | :-----------: | ------------------------ |
|   0   | `loan_` | `address` |   `address`   | Loan to remove call for. |

\


### `removeLoanImpairment`

Removes the loan impairment for a loan.

```solidity
    function removeLoanImpairment(
        address loan_
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                         |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------- |
|   0   | `loan_` | `address` |   `address`   | Loan to remove the loan impairment. |

\


### `setImplementation`

Modifies the proxy's implementation address.

```solidity
    function setImplementation(
        address implementation_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `implementation_` | `address` |   `address`   |             |

\


### `triggerDefault`

Triggers the default of a loan.

```solidity
    function triggerDefault(
        address loan_,
        address liquidatorFactory_
    )
        nonpayable
        returns (
            bool liquidationComplete_,
            uint256 remainingLosses_,
            uint256 unrecoveredPlatformFees_
        );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                  |
| :---: | :------------------: | :-------: | :-----------: | ---------------------------- |
|   0   |        `loan_`       | `address` |   `address`   | Loan to trigger the default. |
|   1   | `liquidatorFactory_` | `address` |   `address`   |                              |

#### Return Values:

| Index |            Name            |    Type   | Internal Type | Description                                                                 |
| :---: | :------------------------: | :-------: | :-----------: | --------------------------------------------------------------------------- |
|   0   |   `liquidationComplete_`   |   `bool`  |     `bool`    |                                                                             |
|   1   |     `remainingLosses_`     | `uint256` |   `uint256`   | The amount of un-recovered principal and interest (net of management fees). |
|   2   | `unrecoveredPlatformFees_` | `uint256` |   `uint256`   | The amount of un-recovered platform fees.                                   |

\


### `triggerDefault`

Triggers the default of a loan.

```solidity
    function triggerDefault(
        address loan_
    )
        nonpayable
        returns (
            uint256 remainingLosses_,
            uint256 unrecoveredPlatformFees_
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                  |
| :---: | :-----: | :-------: | :-----------: | ---------------------------- |
|   0   | `loan_` | `address` |   `address`   | Loan to trigger the default. |

#### Return Values:

| Index |            Name            |    Type   | Internal Type | Description                                                                 |
| :---: | :------------------------: | :-------: | :-----------: | --------------------------------------------------------------------------- |
|   0   |     `remainingLosses_`     | `uint256` |   `uint256`   | The amount of un-recovered principal and interest (net of management fees). |
|   1   | `unrecoveredPlatformFees_` | `uint256` |   `uint256`   | The amount of un-recovered platform fees.                                   |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint128` |   `uint128`   |             |

\


### `upgrade`

Upgrades a contract implementation to a specific version. Access control logic critical since caller can force a selfdestruct via a malicious \`migrator\_\` which is delegatecalled.

```solidity
    function upgrade(
        uint256 version_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                    |
| :---: | :----------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   |  `version_`  | `uint256` |   `uint256`   |                                                |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | Some encoded arguments to use for the upgrade. |

\


## Events

### `AccountingStateUpdated`

Emitted when the accounting state of the loan manager is updated.

```solidity
    event AccountingStateUpdated(
        uint256 issuanceRate_,
        uint112 accountedInterest_
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                       |
| :---: | :------------------: | :-------: | :-----------: | --------------------------------- |
|   0   |    `issuanceRate_`   | `uint256` |   `uint256`   | New value for the issuance rate.  |
|   1   | `accountedInterest_` | `uint112` |   `uint112`   | The amount of accounted interest. |

\


### `ClaimedFundsDistributed`

Funds have been claimed and distributed to the Pool, Pool Delegate, and Maple Treasury.

```solidity
    event ClaimedFundsDistributed(
        address loan_,
        uint256 principal_,
        uint256 netInterest_,
        uint256 delegateManagementFee_,
        uint256 delegateServiceFee_,
        uint256 platformManagementFee_,
        uint256 platformServiceFee_
    );
```

#### Parameters:

| Index |           Name           |    Type   | Internal Type | Description                                  |
| :---: | :----------------------: | :-------: | :-----------: | -------------------------------------------- |
|   0   |          `loan_`         | `address` |   `address`   | The address of the loan contract.            |
|   1   |       `principal_`       | `uint256` |   `uint256`   | The amount of principal paid.                |
|   2   |      `netInterest_`      | `uint256` |   `uint256`   | The amount of net interest paid.             |
|   3   | `delegateManagementFee_` | `uint256` |   `uint256`   | The amount of delegate management fees paid. |
|   4   |   `delegateServiceFee_`  | `uint256` |   `uint256`   | The amount of delegate service fees paid.    |
|   5   | `platformManagementFee_` | `uint256` |   `uint256`   | The amount of platform management fees paid. |
|   6   |   `platformServiceFee_`  | `uint256` |   `uint256`   | The amount of platform service fees paid.    |

\


### `ExpectedClaim`

Funds that were expected to be claimed and distributed to the Pool and Maple Treasury.

```solidity
    event ExpectedClaim(
        address loan_,
        uint256 principal_,
        uint256 netInterest_,
        uint256 platformManagementFee_,
        uint256 platformServiceFee_
    );
```

#### Parameters:

| Index |           Name           |    Type   | Internal Type | Description                                                           |
| :---: | :----------------------: | :-------: | :-----------: | --------------------------------------------------------------------- |
|   0   |          `loan_`         | `address` |   `address`   | The address of the loan contract.                                     |
|   1   |       `principal_`       | `uint256` |   `uint256`   | The amount of principal that was expected to be paid.                 |
|   2   |      `netInterest_`      | `uint256` |   `uint256`   | The amount of net interest that was expected to be paid.              |
|   3   | `platformManagementFee_` | `uint256` |   `uint256`   | The amount of platform management fees that were expected to be paid. |
|   4   |   `platformServiceFee_`  | `uint256` |   `uint256`   | The amount of platform service fees that were expected to paid.       |

\


### `LiquidatedFundsDistributed`

Funds that were liquidated and distributed to the Pool, Maple Treasury, and Borrower.

```solidity
    event LiquidatedFundsDistributed(
        address loan_,
        uint256 toBorrower_,
        uint256 toPool_,
        uint256 toTreasury_
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                         |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------------------------- |
|   0   |    `loan_`    | `address` |   `address`   | The address of the loan contract that defaulted and was liquidated. |
|   1   | `toBorrower_` | `uint256` |   `uint256`   | The amount of recovered funds transferred to the Borrower.          |
|   2   |   `toPool_`   | `uint256` |   `uint256`   | The amount of recovered funds transferred to the Pool.              |
|   3   | `toTreasury_` | `uint256` |   `uint256`   | The amount of recovered funds transferred to the Treasury.          |

\


### `PaymentAdded`

Emitted when a payment is added to the LoanManager payments mapping.

```solidity
    event PaymentAdded(
        address loan_,
        uint256 platformManagementFeeRate_,
        uint256 delegateManagementFeeRate_,
        uint256 paymentDueDate_,
        uint256 issuanceRate_
    );
```

#### Parameters:

| Index |             Name             |    Type   | Internal Type | Description                                                                            |
| :---: | :--------------------------: | :-------: | :-----------: | -------------------------------------------------------------------------------------- |
|   0   |            `loan_`           | `address` |   `address`   | The address of the loan.                                                               |
|   1   | `platformManagementFeeRate_` | `uint256` |   `uint256`   | The amount of platform management rate that will be used for the payment distribution. |
|   2   | `delegateManagementFeeRate_` | `uint256` |   `uint256`   | The amount of delegate management rate that will be used for the payment distribution. |
|   3   |       `paymentDueDate_`      | `uint256` |   `uint256`   | The due date of the payment.                                                           |
|   4   |        `issuanceRate_`       | `uint256` |   `uint256`   | The issuance of the payment, 1e27 precision.                                           |

\


### `PaymentRemoved`

Emitted when a payment is removed from the LoanManager payments mapping.

```solidity
    event PaymentRemoved(
        address loan_
    );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description              |
| :---: | :-----: | :-------: | :-----------: | ------------------------ |
|   0   | `loan_` | `address` |   `address`   | The address of the loan. |

\


### `PrincipalOutUpdated`

Emitted when principal out is updated

```solidity
    event PrincipalOutUpdated(
        uint128 principalOut_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                      |
| :---: | :-------------: | :-------: | :-----------: | -------------------------------- |
|   0   | `principalOut_` | `uint128` |   `uint128`   | The new value for principal out. |

\


### `UnrealizedLossesUpdated`

Emitted when unrealized losses is updated.

```solidity
    event UnrealizedLossesUpdated(
        uint128 unrealizedLosses_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                          |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `unrealizedLosses_` | `uint128` |   `uint128`   | The new value for unrealized losses. |

\


### `Upgraded`

The instance was upgraded.

```solidity
    event Upgraded(
        uint256 toVersion_,
        bytes arguments_
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                    |
| :---: | :----------: | :-------: | :-----------: | ------------------------------ |
|   0   | `toVersion_` | `uint256` |   `uint256`   | The new version of the loan.   |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | The upgrade arguments, if any. |

\
