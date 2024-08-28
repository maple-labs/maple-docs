# FixedTermLoanManager

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


### `acceptNewTerms`

Accepts new loan terms triggering a loan refinance.

```solidity
    function acceptNewTerms(
        address loan_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_,
        uint256 principalIncrease_
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                |
| :---: | :------------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   |        `loan_`       | `address` |   `address`   | Loan to be refinanced.                     |
|   1   |     `refinancer_`    | `address` |   `address`   | The address of the refinancer.             |
|   2   |      `deadline_`     | `uint256` |   `uint256`   | The new deadline to execute the refinance. |
|   3   |       `calls_`       | `bytes[]` |   `bytes[]`   | The encoded calls to set new loan terms.   |
|   4   | `principalIncrease_` | `uint256` |   `uint256`   | The increase in principal.                 |

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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

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


### `claim`

Called by loans when payments are made, updating the accounting.

```solidity
    function claim(
        uint256 principal_,
        uint256 interest_,
        uint256 previousPaymentDueDate_,
        uint256 nextPaymentDueDate_
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |    Type   | Internal Type | Description                    |
| :---: | :-----------------------: | :-------: | :-----------: | ------------------------------ |
|   0   |        `principal_`       | `uint256` |   `uint256`   | The amount of principal paid.  |
|   1   |        `interest_`        | `uint256` |   `uint256`   | The amount of interest paid.   |
|   2   | `previousPaymentDueDate_` | `uint256` |   `uint256`   | The previous payment due date. |
|   3   |   `nextPaymentDueDate_`   | `uint256` |   `uint256`   | The new payment due date.      |

\


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

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint48` |    `uint48`   |             |

\


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

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint48` |    `uint48`   |             |

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


### `finishCollateralLiquidation`

Finishes the collateral liquidation.

```solidity
    function finishCollateralLiquidation(
        address loan_
    )
        nonpayable
        returns (
            uint256 remainingLosses_,
            uint256 platformFees_
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                              |
| :---: | :-----: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `loan_` | `address` |   `address`   | Loan that had its collateral liquidated. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                     |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `remainingLosses_` | `uint256` |   `uint256`   | The amount of remaining losses. |
|   1   |   `platformFees_`  | `uint256` |   `uint256`   | The amount of platform fees.    |

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


### `getExpectedAmount`

Gets the expected amount of an asset given the input amount.

```solidity
    function getExpectedAmount(
        address collateralAsset_,
        uint256 swapAmount_
    )
        view
        returns (
            uint256 returnAmount_
        );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                                    |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `collateralAsset_` | `address` |   `address`   | The collateral asset that is being liquidated. |
|   1   |    `swapAmount_`   | `uint256` |   `uint256`   | The swap amount of collateral asset.           |

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                               |
| :---: | :-------------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `returnAmount_` | `uint256` |   `uint256`   | The desired return amount of funds asset. |

\


### `governor`

```solidity
    function governor()
        view
        returns (
            address governor_
        );
```

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description |
| :---: | :---------: | :-------: | :-----------: | ----------- |
|   0   | `governor_` | `address` |   `address`   |             |

\


### `impairLoan`

Triggers the loan impairment for a loan.

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


### `isLiquidationActive`

Returns whether or not a liquidation is in progress.

```solidity
    function isLiquidationActive(
        address loan_
    )
        view
        returns (
            bool isActive_
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                       |
| :---: | :-----: | :-------: | :-----------: | --------------------------------- |
|   0   | `loan_` | `address` |   `address`   | The address of the loan contract. |

#### Return Values:

| Index |     Name    |  Type  | Internal Type | Description                           |
| :---: | :---------: | :----: | :-----------: | ------------------------------------- |
|   0   | `isActive_` | `bool` |     `bool`    | True if a liquidation is in progress. |

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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                                            |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------------------------ |
|   0   | `triggeredByGovernor` |   `bool`  |     `bool`    | True if the liquidation was triggered by the governor. |
|   1   |      `principal`      | `uint128` |   `uint128`   | The amount of principal to be recovered.               |
|   2   |       `interest`      | `uint120` |   `uint120`   | The amount of interest to be recovered.                |
|   3   |     `lateInterest`    | `uint256` |   `uint256`   | The amount of late interest to be recovered.           |
|   4   |     `platformFees`    |  `uint96` |    `uint96`   | The amount of platform fees owed.                      |
|   5   |      `liquidator`     | `address` |   `address`   | The address of the liquidator.                         |

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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


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

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint24` |    `uint24`   |             |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint24` |    `uint24`   |             |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index |             Name            |    Type   | Internal Type | Description                                     |
| :---: | :-------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `platformManagementFeeRate` |  `uint24` |    `uint24`   | The value for the platform management fee rate. |
|   1   | `delegateManagementFeeRate` |  `uint24` |    `uint24`   | The value for the delegate management fee rate. |
|   2   |         `startDate`         |  `uint48` |    `uint48`   | The start date of the payment.                  |
|   3   |       `paymentDueDate`      |  `uint48` |    `uint48`   | The timestamp of the payment due date.          |
|   4   |    `incomingNetInterest`    | `uint128` |   `uint128`   | The amount of incoming net interest.            |
|   5   |     `refinanceInterest`     | `uint128` |   `uint128`   | The amount of refinance interest.               |
|   6   |        `issuanceRate`       | `uint256` |   `uint256`   | The issuance rate for the loan.                 |

\


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

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint24` |    `uint24`   |             |

\


### `poolDelegate`

```solidity
    function poolDelegate()
        view
        returns (
            address poolDelegate_
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description |
| :---: | :-------------: | :-------: | :-----------: | ----------- |
|   0   | `poolDelegate_` | `address` |   `address`   |             |

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

| Index |      Name     |    Type   | Internal Type | Description                                                 |
| :---: | :-----------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   |    `loan_`    | `address` |   `address`   | The loan with the proposed new changes.                     |
|   1   | `refinancer_` | `address` |   `address`   | The refinancer to use in the refinance.                     |
|   2   |  `deadline_`  | `uint256` |   `uint256`   | The deadline by which the lender must accept the new terms. |
|   3   |    `calls_`   | `bytes[]` |   `bytes[]`   | The array of calls to be made to the refinancer.            |

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


### `setAllowedSlippage`

Sets the allowed slippage for a collateral asset liquidation.

```solidity
    function setAllowedSlippage(
        address collateralAsset_,
        uint256 allowedSlippage_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                        |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `collateralAsset_` | `address` |   `address`   | Address of a collateral asset.     |
|   1   | `allowedSlippage_` | `uint256` |   `uint256`   | New value for \`allowedSlippage\`. |

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


### `setMinRatio`

Sets the minimum ratio for a collateral asset liquidation. This ratio is expressed as a decimal representation of units of fundsAsset per unit collateralAsset in fundsAsset decimal precision.

```solidity
    function setMinRatio(
        address collateralAsset_,
        uint256 minRatio_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                    |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `collateralAsset_` | `address` |   `address`   | Address of a collateral asset. |
|   1   |     `minRatio_`    | `uint256` |   `uint256`   | New value for \`minRatio\`.    |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index |       Name       |   Type   | Internal Type | Description |
| :---: | :--------------: | :------: | :-----------: | ----------- |
|   0   |    `previous`    | `uint24` |    `uint24`   |             |
|   1   |      `next`      | `uint24` |    `uint24`   |             |
|   2   | `paymentDueDate` | `uint48` |    `uint48`   |             |

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
            uint256 platformFees_
        );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                         |
| :---: | :------------------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   |        `loan_`       | `address` |   `address`   | Loan to trigger the default.                        |
|   1   | `liquidatorFactory_` | `address` |   `address`   | Factory that will be used to deploy the liquidator. |

#### Return Values:

| Index |          Name          |    Type   | Internal Type | Description                                                                      |
| :---: | :--------------------: | :-------: | :-----------: | -------------------------------------------------------------------------------- |
|   0   | `liquidationComplete_` |   `bool`  |     `bool`    | True if the liquidation is completed in the same transaction (uncollateralized). |
|   1   |   `remainingLosses_`   | `uint256` |   `uint256`   | The amount of remaining losses.                                                  |
|   2   |     `platformFees_`    | `uint256` |   `uint256`   | The amount of platform fees.                                                     |

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


### `updateAccounting`

Updates the issuance parameters of the LoanManager, callable by the Governor and the PoolDelegate. Useful to call when \`block.timestamp\` is greater than \`domainEnd\` and the LoanManager is not accruing interest.

```solidity
    function updateAccounting()
        nonpayable;
```

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

### `AllowedSlippageSet`

Emitted when \`setAllowedSlippage\` is called.

```solidity
    event AllowedSlippageSet(
        address collateralAsset_,
        uint256 newSlippage_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                        |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `collateralAsset_` | `address` |   `address`   | Address of a collateral asset.     |
|   1   |   `newSlippage_`   | `uint256` |   `uint256`   | New value for \`allowedSlippage\`. |

\


### `FundsDistributed`

Funds have been claimed and distributed into the Pool.

```solidity
    event FundsDistributed(
        address loan_,
        uint256 principal_,
        uint256 netInterest_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                       |
| :---: | :------------: | :-------: | :-----------: | --------------------------------- |
|   0   |     `loan_`    | `address` |   `address`   | The address of the loan contract. |
|   1   |  `principal_`  | `uint256` |   `uint256`   | The amount of principal paid.     |
|   2   | `netInterest_` | `uint256` |   `uint256`   | The amount of net interest paid.  |

\


### `IssuanceParamsUpdated`

Emitted when the issuance parameters are changed.

```solidity
    event IssuanceParamsUpdated(
        uint48 domainEnd_,
        uint256 issuanceRate_,
        uint112 accountedInterest_
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                       |
| :---: | :------------------: | :-------: | :-----------: | --------------------------------- |
|   0   |     `domainEnd_`     |  `uint48` |    `uint48`   | The timestamp of the domain end.  |
|   1   |    `issuanceRate_`   | `uint256` |   `uint256`   | New value for the issuance rate.  |
|   2   | `accountedInterest_` | `uint112` |   `uint112`   | The amount of accounted interest. |

\


### `LoanTransferAdminSet`

Emitted when the loanTransferAdmin is set by the PoolDelegate.

```solidity
    event LoanTransferAdminSet(
        address loanTransferAdmin_
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                       |
| :---: | :------------------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   | `loanTransferAdmin_` | `address` |   `address`   | The address of the admin that can transfer loans. |

\


### `ManagementFeesPaid`

A fee payment was made.

```solidity
    event ManagementFeesPaid(
        address loan_,
        uint256 delegateManagementFee_,
        uint256 platformManagementFee_
    );
```

#### Parameters:

| Index |           Name           |    Type   | Internal Type | Description                                 |
| :---: | :----------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |          `loan_`         | `address` |   `address`   | The address of the loan contract.           |
|   1   | `delegateManagementFee_` | `uint256` |   `uint256`   | The amount of delegate management fee paid. |
|   2   | `platformManagementFee_` | `uint256` |   `uint256`   | The amount of platform management fee paid. |

\


### `MinRatioSet`

Emitted when \`setMinRatio\` is called.

```solidity
    event MinRatioSet(
        address collateralAsset_,
        uint256 newMinRatio_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                    |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `collateralAsset_` | `address` |   `address`   | Address of a collateral asset. |
|   1   |   `newMinRatio_`   | `uint256` |   `uint256`   | New value for \`minRatio\`.    |

\


### `PaymentAdded`

Emitted when a payment is removed from the LoanManager payments array.

```solidity
    event PaymentAdded(
        address loan_,
        uint256 paymentId_,
        uint256 platformManagementFeeRate_,
        uint256 delegateManagementFeeRate_,
        uint256 startDate_,
        uint256 nextPaymentDueDate_,
        uint256 netRefinanceInterest_,
        uint256 newRate_
    );
```

#### Parameters:

| Index |             Name             |    Type   | Internal Type | Description                                     |
| :---: | :--------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   |            `loan_`           | `address` |   `address`   | The address of the loan.                        |
|   1   |         `paymentId_`         | `uint256` |   `uint256`   | The payment ID of the payment that was removed. |
|   2   | `platformManagementFeeRate_` | `uint256` |   `uint256`   |                                                 |
|   3   | `delegateManagementFeeRate_` | `uint256` |   `uint256`   |                                                 |
|   4   |         `startDate_`         | `uint256` |   `uint256`   |                                                 |
|   5   |     `nextPaymentDueDate_`    | `uint256` |   `uint256`   |                                                 |
|   6   |    `netRefinanceInterest_`   | `uint256` |   `uint256`   |                                                 |
|   7   |          `newRate_`          | `uint256` |   `uint256`   |                                                 |

\


### `PaymentRemoved`

Emitted when a payment is removed from the LoanManager payments array.

```solidity
    event PaymentRemoved(
        address loan_,
        uint256 paymentId_
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                     |
| :---: | :----------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   |    `loan_`   | `address` |   `address`   | The address of the loan.                        |
|   1   | `paymentId_` | `uint256` |   `uint256`   | The payment ID of the payment that was removed. |

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
        uint256 unrealizedLosses_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                          |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `unrealizedLosses_` | `uint256` |   `uint256`   | The new value for unrealized losses. |

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
