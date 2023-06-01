# Maple Open Term Loan



<br />


## Functions

### `HUNDRED_PERCENT`

The value that represents 100%, to be easily comparable with the loan rates.

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

### `acceptBorrower`

Accept the borrower role, must be called by pendingBorrower.

```solidity
    function acceptBorrower()
        nonpayable;
```



<br />

### `acceptLender`

Accept the lender role, must be called by pendingLender.

```solidity
    function acceptLender()
        nonpayable;
```



<br />

### `acceptNewTerms`

Accept the proposed terms and trigger refinance execution.

```solidity
    function acceptNewTerms(
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    )
        nonpayable
        returns (
            bytes32 refinanceCommitment_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinancer_` | `address` | `address` | The address of the refinancer contract. |
| 1 | `deadline_` | `uint256` | `uint256` | The deadline for accepting the new terms. |
| 2 | `calls_` | `bytes[]` | `bytes[]` | The encoded arguments to be passed to refinancer. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` | The hash of the accepted refinance agreement. |


<br />

### `borrower`

The borrower of the loan, responsible for repayments.

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

The amount of principal yet to be returned to satisfy the loan call.

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

### `callPrincipal`

The lender called the loan, giving the borrower a notice period within which to return principal and pro-rata interest.

```solidity
    function callPrincipal(
        uint256 principalToReturn_
    )
        nonpayable
        returns (
            uint40 paymentDueDate_,
            uint40 defaultDate_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalToReturn_` | `uint256` | `uint256` | The minimum amount of principal the borrower must return. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` |    The new payment due date for returning the principal and pro-rate interest to the lender. |
| 1 | `defaultDate_` | `uint40` | `uint40` |       The date the loan will be in default. |


<br />

### `dateCalled`

The timestamp of the date the loan was called.

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

The timestamp of the date the loan was funded.

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

The timestamp of the date the loan was impaired.

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

The timestamp of the date the loan was last paid.

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

### `defaultDate`

The timestamp of the date the loan will be in default.

```solidity
    function defaultDate()
        view
        returns (
            uint40 paymentDefaultDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDefaultDate_` | `uint40` | `uint40` |  |


<br />

### `delegateServiceFeeRate`

The annualized delegate service fee rate.

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

### `fund`

Lend funds to the loan/borrower.

```solidity
    function fund()
        nonpayable
        returns (
            uint256 fundsLent_,
            uint40 paymentDueDate_,
            uint40 defaultDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsLent_` | `uint256` | `uint256` |      The amount funded. |
| 1 | `paymentDueDate_` | `uint40` | `uint40` | The due date of the first payment. |
| 2 | `defaultDate_` | `uint40` | `uint40` |    The timestamp of the date the loan will be in default. |


<br />

### `fundsAsset`

The address of the fundsAsset funding the loan.

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

### `getPaymentBreakdown`

Get the breakdown of the total payment needed to satisfy the next payment installment.

```solidity
    function getPaymentBreakdown(
        uint256 timestamp_
    )
        view
        returns (
            uint256 principal_,
            uint256 interest_,
            uint256 lateInterest_,
            uint256 delegateServiceFee_,
            uint256 platformServiceFee_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `timestamp_` | `uint256` | `uint256` | The timestamp that corresponds to when the payment is to be made. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` |          The portion of the total amount that will go towards principal. |
| 1 | `interest_` | `uint256` | `uint256` |           The portion of the total amount that will go towards interest fees. |
| 2 | `lateInterest_` | `uint256` | `uint256` |       The portion of the total amount that will go towards late interest fees. |
| 3 | `delegateServiceFee_` | `uint256` | `uint256` | The portion of the total amount that will go towards delegate service fees. |
| 4 | `platformServiceFee_` | `uint256` | `uint256` | The portion of the total amount that will go towards platform service fees. |


<br />

### `globals`

The Maple globals address

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
| 0 | `globals_` | `address` | `address` |  |


<br />

### `gracePeriod`

The amount of time the borrower has, after a payment is due, to make a payment before being in default.

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

### `impair`

Fast forward the payment due date to the current time.          This enables the pool delegate to force a payment (or default).

```solidity
    function impair()
        nonpayable
        returns (
            uint40 paymentDueDate_,
            uint40 defaultDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` | The new payment due date to result in the removal of the loan&#x27;s impairment status. |
| 1 | `defaultDate_` | `uint40` | `uint40` |    The timestamp of the date the loan will be in default. |


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

### `interestRate`

The annualized interest rate (APR), in units of 1e18, (i.e. 1% is 0.01e18).

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

### `isCalled`

Whether the loan is called.

```solidity
    function isCalled()
        view
        returns (
            bool isCalled_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isCalled_` | `bool` | `bool` |  |


<br />

### `isImpaired`

Whether the loan is impaired.

```solidity
    function isImpaired()
        view
        returns (
            bool isImpaired_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isImpaired_` | `bool` | `bool` |  |


<br />

### `isInDefault`

Whether the loan is in default.

```solidity
    function isInDefault()
        view
        returns (
            bool isInDefault_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isInDefault_` | `bool` | `bool` |  |


<br />

### `lateFeeRate`

The rate charged at late payments.

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

The premium over the regular interest rate applied when paying late.

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

The lender of the Loan.

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

### `makePayment`

Make a payment to the loan.

```solidity
    function makePayment(
        uint256 principalToReturn_
    )
        nonpayable
        returns (
            uint256 interest_,
            uint256 lateInterest_,
            uint256 delegateServiceFee_,
            uint256 platformServiceFee_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalToReturn_` | `uint256` | `uint256` | The amount of principal to return, to the lender to reduce future interest payments. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `interest_` | `uint256` | `uint256` |           The portion of the amount paying interest. |
| 1 | `lateInterest_` | `uint256` | `uint256` |       The portion of the amount paying late interest. |
| 2 | `delegateServiceFee_` | `uint256` | `uint256` | The portion of the amount paying delegate service fees. |
| 3 | `platformServiceFee_` | `uint256` | `uint256` | The portion of the amount paying platform service fees. |


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

### `noticePeriod`

The amount of time the borrower has, after the loan is called, to make a payment, paying back the called principal.

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

### `paymentDueDate`

The timestamp of the due date of the next payment.

```solidity
    function paymentDueDate()
        view
        returns (
            uint40 paymentDueDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` |  |


<br />

### `paymentInterval`

The specified time between loan payments.

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

The address of the pending borrower.

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

The address of the pending lender.

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

The annualized platform service fee rate.

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

The amount of principal owed (initially, the requested amount), which needs to be paid back.

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

### `proposeNewTerms`

Propose new terms for refinance.

```solidity
    function proposeNewTerms(
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    )
        nonpayable
        returns (
            bytes32 refinanceCommitment_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinancer_` | `address` | `address` | The address of the refinancer contract. |
| 1 | `deadline_` | `uint256` | `uint256` | The deadline for accepting the new terms. |
| 2 | `calls_` | `bytes[]` | `bytes[]` | The encoded arguments to be passed to refinancer. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` | The hash of the proposed refinance agreement. |


<br />

### `refinanceCommitment`

The hash of the proposed refinance agreement.

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

### `rejectNewTerms`

Nullify the current proposed terms.

```solidity
    function rejectNewTerms(
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    )
        nonpayable
        returns (
            bytes32 refinanceCommitment_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinancer_` | `address` | `address` | The address of the refinancer contract. |
| 1 | `deadline_` | `uint256` | `uint256` | The deadline for accepting the new terms. |
| 2 | `calls_` | `bytes[]` | `bytes[]` | The encoded arguments to be passed to refinancer. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` | The hash of the rejected refinance agreement. |


<br />

### `removeCall`

Remove the loan&#x27;s called status.

```solidity
    function removeCall()
        nonpayable
        returns (
            uint40 paymentDueDate_,
            uint40 defaultDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` | The restored payment due date. |
| 1 | `defaultDate_` | `uint40` | `uint40` |    The date the loan will be in default. |


<br />

### `removeImpairment`

Remove the loan impairment by restoring the original payment due date.

```solidity
    function removeImpairment()
        nonpayable
        returns (
            uint40 paymentDueDate_,
            uint40 defaultDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` | The restored payment due date. |
| 1 | `defaultDate_` | `uint40` | `uint40` |    The timestamp of the date the loan will be in default. |


<br />

### `repossess`

Repossess collateral, and any funds, for a loan in default.

```solidity
    function repossess(
        address destination_
    )
        nonpayable
        returns (
            uint256 fundsRepossessed_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `destination_` | `address` | `address` | The address where the collateral and funds asset is to be sent, if any. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsRepossessed_` | `uint256` | `uint256` | The amount of funds asset repossessed. |


<br />

### `setImplementation`

Modifies the proxy&#x27;s implementation address.

```solidity
    function setImplementation(
        address newImplementation_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newImplementation_` | `address` | `address` | The address of an implementation contract. |


<br />

### `setPendingBorrower`

Set the &#x60;pendingBorrower&#x60; to a new account.

```solidity
    function setPendingBorrower(
        address pendingBorrower_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingBorrower_` | `address` | `address` | The address of the new pendingBorrower. |


<br />

### `setPendingLender`

Set the &#x60;pendingLender&#x60; to a new account.

```solidity
    function setPendingLender(
        address pendingLender_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingLender_` | `address` | `address` | The address of the new pendingLender. |


<br />

### `skim`

Remove all available balance of a specified token.          NOTE: Open Term Loans are not designed to hold custody of tokens, so this is designed as a safety feature.

```solidity
    function skim(
        address token_,
        address destination_
    )
        nonpayable
        returns (
            uint256 skimmed_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `token_` | `address` | `address` | The address of the token contract. |
| 1 | `destination_` | `address` | `address` | The recipient of the token. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `skimmed_` | `uint256` | `uint256` |     The amount of token removed from the loan. |


<br />

### `upgrade`

Upgrades a contract implementation to a specific version.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function upgrade(
        uint256 toVersion_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toVersion_` | `uint256` | `uint256` | The version to upgrade to. |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the upgrade. |


<br />


## Events

### `BorrowerAccepted`

Borrower was accepted, and set to a new account.

```solidity
    event BorrowerAccepted(
        address borrower_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` | The address of the new borrower. |

<br />

### `CallRemoved`

The lender reverted the action of the loan being called and the payment due date was restored to it&#x27;s original value.

```solidity
    event CallRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` | The restored payment due date. |
| 1 | `defaultDate_` | `uint40` | `uint40` | The date the loan will be in default. |

<br />

### `Funded`

The loan was funded.

```solidity
    event Funded(
        uint256 amount_,
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount funded. |
| 1 | `paymentDueDate_` | `uint40` | `uint40` | The due date of the first payment. |
| 2 | `defaultDate_` | `uint40` | `uint40` | The date the loan will be in default. |

<br />

### `Impaired`

The payment due date was fast forwarded to the current time, activating the grace period.         This is emitted when the pool delegate wants to force a payment (or default).

```solidity
    event Impaired(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` | The new payment due date. |
| 1 | `defaultDate_` | `uint40` | `uint40` | The date the loan will be in default. |

<br />

### `ImpairmentRemoved`

The payment due date was restored to it&#x27;s original value, reverting the action of loan impairment.

```solidity
    event ImpairmentRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` | The restored payment due date. |
| 1 | `defaultDate_` | `uint40` | `uint40` | The date the loan will be in default. |

<br />

### `Initialized`

Loan was initialized.

```solidity
    event Initialized(
        address borrower_,
        address lender_,
        address fundsAsset_,
        uint256 principalRequested_,
        uint32[3] termDetails_,
        uint64[4] rates_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` | The address of the borrower. |
| 1 | `lender_` | `address` | `address` | The address of the lender. |
| 2 | `fundsAsset_` | `address` | `address` | The address of the lent asset. |
| 3 | `principalRequested_` | `uint256` | `uint256` | The amount of principal requested. |
| 4 | `termDetails_` | `uint32[3]` | `uint32[3]` | Array of loan parameters:                                 [0]: gracePeriod,                                 [1]: noticePeriod,                                 [2]: paymentInterval |
| 5 | `rates_` | `uint64[4]` | `uint64[4]` | Array of rate parameters:                                 [0]: delegateServiceFeeRate,                                 [1]: interestRate,                                 [2]: lateFeeRate,                                 [3]: lateInterestPremiumRate |

<br />

### `LenderAccepted`

Lender was accepted, and set to a new account.

```solidity
    event LenderAccepted(
        address lender_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lender_` | `address` | `address` | The address of the new lender. |

<br />

### `NewTermsAccepted`

The terms of the refinance proposal were accepted.

```solidity
    event NewTermsAccepted(
        bytes32 refinanceCommitment_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` | The hash of the refinancer, deadline, and calls proposed. |
| 1 | `refinancer_` | `address` | `address` | The address that will execute the refinance. |
| 2 | `deadline_` | `uint256` | `uint256` | The deadline for accepting the new terms. |
| 3 | `calls_` | `bytes[]` | `bytes[]` | The individual calls for the refinancer contract. |

<br />

### `NewTermsProposed`

A refinance was proposed.

```solidity
    event NewTermsProposed(
        bytes32 refinanceCommitment_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` | The hash of the refinancer, deadline, and calls proposed. |
| 1 | `refinancer_` | `address` | `address` | The address that will execute the refinance. |
| 2 | `deadline_` | `uint256` | `uint256` | The deadline for accepting the new terms. |
| 3 | `calls_` | `bytes[]` | `bytes[]` | The individual calls for the refinancer contract. |

<br />

### `NewTermsRejected`

The terms of the refinance proposal were rejected.

```solidity
    event NewTermsRejected(
        bytes32 refinanceCommitment_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` | The hash of the refinancer, deadline, and calls proposed. |
| 1 | `refinancer_` | `address` | `address` | The address that will execute the refinance. |
| 2 | `deadline_` | `uint256` | `uint256` | The deadline for accepting the new terms. |
| 3 | `calls_` | `bytes[]` | `bytes[]` | The individual calls for the refinancer contract. |

<br />

### `PaymentMade`

Payments were made.

```solidity
    event PaymentMade(
        address lender_,
        uint256 principalPaid_,
        uint256 interestPaid_,
        uint256 lateInterestPaid_,
        uint256 delegateServiceFee_,
        uint256 platformServiceFee_,
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lender_` | `address` | `address` | The address of the lender the payment was made to. |
| 1 | `principalPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards paying down principal. |
| 2 | `interestPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards interest. |
| 3 | `lateInterestPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards late interest. |
| 4 | `delegateServiceFee_` | `uint256` | `uint256` | The portion of the total amount that went towards delegate service fees. |
| 5 | `platformServiceFee_` | `uint256` | `uint256` | The portion of the total amount that went towards platform service fee. |
| 6 | `paymentDueDate_` | `uint40` | `uint40` | The new payment due date. |
| 7 | `defaultDate_` | `uint40` | `uint40` | The date the loan will be in default. |

<br />

### `PendingBorrowerSet`

Pending borrower was set.

```solidity
    event PendingBorrowerSet(
        address pendingBorrower_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingBorrower_` | `address` | `address` | Address that can accept the borrower role. |

<br />

### `PendingLenderSet`

Pending lender was set.

```solidity
    event PendingLenderSet(
        address pendingLender_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingLender_` | `address` | `address` | The address that can accept the lender role. |

<br />

### `PrincipalCalled`

The lender called the loan, giving the borrower a notice period within which to return principal and pro-rata interest.

```solidity
    event PrincipalCalled(
        uint256 principalToReturn_,
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalToReturn_` | `uint256` | `uint256` | The minimum amount of principal the borrower must return. |
| 1 | `paymentDueDate_` | `uint40` | `uint40` | The new payment due date. |
| 2 | `defaultDate_` | `uint40` | `uint40` | The date the loan will be in default. |

<br />

### `PrincipalReturned`

Principal was returned to lender, to close the loan or return future interest payments.

```solidity
    event PrincipalReturned(
        uint256 principalReturned_,
        uint256 principalRemaining_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalReturned_` | `uint256` | `uint256` | The amount of principal returned. |
| 1 | `principalRemaining_` | `uint256` | `uint256` | The amount of principal remaining on the loan. |

<br />

### `Repossessed`

The loan was in default and funds and collateral was repossessed by the lender.

```solidity
    event Repossessed(
        uint256 fundsRepossessed_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsRepossessed_` | `uint256` | `uint256` | The amount of funds asset repossessed. |
| 1 | `destination_` | `address` | `address` | The address of the recipient of the funds, if any. |

<br />

### `Skimmed`

Some token was removed from the loan.

```solidity
    event Skimmed(
        address token_,
        uint256 amount_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `token_` | `address` | `address` | The address of the token contract. |
| 1 | `amount_` | `uint256` | `uint256` | The amount of token remove from the loan. |
| 2 | `destination_` | `address` | `address` | The recipient of the token. |

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

