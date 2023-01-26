# LoanManager



<br />


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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `acceptNewTerms` 

Accepts new loan terms triggering a loan refinance.

```solidity
    function acceptNewTerms(
        address loan_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to be refinanced. |
| 1 | `refinancer_` | `address` | `address` | The address of the refinancer. |
| 2 | `deadline_` | `uint256` | `uint256` | The new deadline to execute the refinance. |
| 3 | `calls_` | `bytes[]` | `bytes[]` | The encoded calls to set new loan terms. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assetsUnderManagement_` | `uint256` | `uint256` | The amount of assets under the management of the contract. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` | The amount of principal paid. |
| 1 | `interest_` | `uint256` | `uint256` | The amount of interest paid. |
| 2 | `previousPaymentDueDate_` | `uint256` | `uint256` | The previous payment due date. |
| 3 | `nextPaymentDueDate_` | `uint256` | `uint256` | The new payment due date. |


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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `factory_` | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan that had its collateral liquidated. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `remainingLosses_` | `uint256` | `uint256` | The amount of remaining losses. |
| 1 | `platformFees_` | `uint256` | `uint256` |    The amount of platform fees. |


<br />

### `fund` 

Funds a new loan.

```solidity
    function fund(
        address loan_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to be funded. |


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

### `getAccruedInterest` 

Gets the amount of accrued interest up until this point in time.

```solidity
    function getAccruedInterest()
        view
        returns (
            uint256 accruedInterest_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `accruedInterest_` | `uint256` | `uint256` | The amount of accrued interest up until this point in time. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` | The collateral asset that is being liquidated. |
| 1 | `swapAmount_` | `uint256` | `uint256` | The swap amount of collateral asset. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `returnAmount_` | `uint256` | `uint256` |    The desired return amount of funds asset. |


<br />

### `globals` 

Gets the address of the Maple globals contract.

```solidity
    function globals()
        view
        returns (
            address globals_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `globals_` | `address` | `address` | The address of the Maple globals contract. |


<br />

### `governor` 

Gets the address of the governor contract.

```solidity
    function governor()
        view
        returns (
            address governor_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `governor_` | `address` | `address` | The address of the governor contract. |


<br />

### `impairLoan` 

Triggers the loan impairment for a loan.

```solidity
    function impairLoan(
        address loan_,
        bool isGovernor_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to trigger the loan impairment. |
| 1 | `isGovernor_` | `bool` | `bool` | True if called by the governor. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan contract. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isActive_` | `bool` | `bool` | True if a liquidation is in progress. |


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

### `mapleTreasury` 

Gets the address of the Maple treasury.

```solidity
    function mapleTreasury()
        view
        returns (
            address treasury_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `treasury_` | `address` | `address` | The address of the Maple treasury. |


<br />

### `migrate` 

Modifies the proxy&#x27;s storage by delegate-calling a migrator contract with some arguments.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function migrate(
        address migrator_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `migrator_` | `address` | `address` | The address of a migrator contract. |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the migration. |


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

### `poolDelegate` 

Gets the address of the pool delegate.

```solidity
    function poolDelegate()
        view
        returns (
            address poolDelegate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate_` | `address` | `address` | The address of the pool delegate. |


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

### `removeLoanImpairment` 

Removes the loan impairment for a loan.

```solidity
    function removeLoanImpairment(
        address loan_,
        bool isCalledByGovernor_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to remove the loan impairment. |
| 1 | `isCalledByGovernor_` | `bool` | `bool` | True if &#x60;impairLoan&#x60; was called by the governor. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` | Address of a collateral asset. |
| 1 | `allowedSlippage_` | `uint256` | `uint256` | New value for &#x60;allowedSlippage&#x60;. |


<br />

### `setImplementation` 

Modifies the proxy&#x27;s implementation address.

```solidity
    function setImplementation(
        address implementation_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` |  |


<br />

### `setMinRatio` 

Sets the minimum ratio for a collateral asset liquidation.         This ratio is expressed as a decimal representation of units of fundsAsset         per unit collateralAsset in fundsAsset decimal precision.

```solidity
    function setMinRatio(
        address collateralAsset_,
        uint256 minRatio_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` | Address of a collateral asset. |
| 1 | `minRatio_` | `uint256` | `uint256` | New value for &#x60;minRatio&#x60;. |


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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to trigger the default. |
| 1 | `liquidatorFactory_` | `address` | `address` | Factory that will be used to deploy the liquidator. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidationComplete_` | `bool` | `bool` | True if the liquidation is completed in the same transaction (uncollateralized). |
| 1 | `remainingLosses_` | `uint256` | `uint256` |     The amount of remaining losses. |
| 2 | `platformFees_` | `uint256` | `uint256` |        The amount of platform fees. |


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

### `updateAccounting` 

Updates the issuance parameters of the LoanManager, callable by the Governor and the PoolDelegate.       Useful to call when &#x60;block.timestamp&#x60; is greater than &#x60;domainEnd&#x60; and the LoanManager is not accruing interest.

```solidity
    function updateAccounting()
        nonpayable;
```



<br />

### `upgrade` 

Upgrades a contract implementation to a specific version.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function upgrade(
        uint256 version_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` |  |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the upgrade. |


<br />


## Events

### `AllowedSlippageSet`

Emitted when &#x60;setAllowedSlippage&#x60; is called.

```solidity
    event AllowedSlippageSet(
        address collateralAsset_,
        uint256 newSlippage_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` | Address of a collateral asset. |
| 1 | `newSlippage_` | `uint256` | `uint256` | New value for &#x60;allowedSlippage&#x60;. |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan contract. |
| 1 | `principal_` | `uint256` | `uint256` | The amount of principal paid. |
| 2 | `netInterest_` | `uint256` | `uint256` | The amount of net interest paid. |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `domainEnd_` | `uint48` | `uint48` | The timestamp of the domain end. |
| 1 | `issuanceRate_` | `uint256` | `uint256` | New value for the issuance rate. |
| 2 | `accountedInterest_` | `uint112` | `uint112` | The amount of accounted interest. |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan contract. |
| 1 | `delegateManagementFee_` | `uint256` | `uint256` | The amount of delegate management fee paid. |
| 2 | `platformManagementFee_` | `uint256` | `uint256` | The amount of platform management fee paid. |

<br />

### `MinRatioSet`

Emitted when &#x60;setMinRatio&#x60; is called.

```solidity
    event MinRatioSet(
        address collateralAsset_,
        uint256 newMinRatio_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` | Address of a collateral asset. |
| 1 | `newMinRatio_` | `uint256` | `uint256` | New value for &#x60;minRatio&#x60;. |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan. |
| 1 | `paymentId_` | `uint256` | `uint256` | The payment ID of the payment that was removed. |
| 2 | `platformManagementFeeRate_` | `uint256` | `uint256` |  |
| 3 | `delegateManagementFeeRate_` | `uint256` | `uint256` |  |
| 4 | `startDate_` | `uint256` | `uint256` |  |
| 5 | `nextPaymentDueDate_` | `uint256` | `uint256` |  |
| 6 | `netRefinanceInterest_` | `uint256` | `uint256` |  |
| 7 | `newRate_` | `uint256` | `uint256` |  |

<br />

### `PaymentRemoved`

Emitted when a payment is removed from the LoanManager payments array.

```solidity
    event PaymentRemoved(
        address loan_,
        uint256 paymentId_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan. |
| 1 | `paymentId_` | `uint256` | `uint256` | The payment ID of the payment that was removed. |

<br />

### `PrincipalOutUpdated`

Emitted when principal out is updated

```solidity
    event PrincipalOutUpdated(
        uint128 principalOut_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalOut_` | `uint128` | `uint128` | The new value for principal out. |

<br />

### `UnrealizedLossesUpdated`

Emitted when unrealized losses is updated.

```solidity
    event UnrealizedLossesUpdated(
        uint256 unrealizedLosses_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `unrealizedLosses_` | `uint256` | `uint256` | The new value for unrealized losses. |

<br />

### `Upgraded`

The instance was upgraded.

```solidity
    event Upgraded(
        uint256 toVersion_,
        bytes arguments_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toVersion_` | `uint256` | `uint256` | The new version of the loan. |
| 1 | `arguments_` | `bytes` | `bytes` | The upgrade arguments, if any. |

<br />

