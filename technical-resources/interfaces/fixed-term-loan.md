# MapleLoan

MapleLoan implements a primitive loan with additional functionality, and is intended to be proxied.

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

Accept the proposed terms ans trigger refinance execution

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
            address borrower_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |  |


<br />

### `closeLoan` 

Repay all principal and interest and close a loan.          FUNDS SHOULD NOT BE TRANSFERRED TO THIS CONTRACT NON-ATOMICALLY. IF THEY ARE, THE BALANCE MAY BE STOLEN USING &#x60;skim&#x60;.

```solidity
    function closeLoan(
        uint256 amount_
    )
        nonpayable
        returns (
            uint256 principal_,
            uint256 interest_,
            uint256 fees_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | An amount to pull from the caller, if any. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` | The portion of the amount paying back principal. |
| 1 | `interest_` | `uint256` | `uint256` |  The portion of the amount paying interest. |
| 2 | `fees_` | `uint256` | `uint256` |      The portion of the amount paying service fees. |


<br />

### `closingRate` 

The fee rate (applied to principal) to close the loan.       This value should be configured so that it is less expensive to close a loan with more than one payment remaining, but       more expensive to close it if on the last payment.

```solidity
    function closingRate()
        view
        returns (
            uint256 closingRate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `closingRate_` | `uint256` | `uint256` |  |


<br />

### `collateral` 

The amount of collateral posted against outstanding (drawn down) principal.

```solidity
    function collateral()
        view
        returns (
            uint256 collateral_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateral_` | `uint256` | `uint256` |  |


<br />

### `collateralAsset` 

The address of the asset deposited by the borrower as collateral, if needed.

```solidity
    function collateralAsset()
        view
        returns (
            address collateralAsset_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` |  |


<br />

### `collateralRequired` 

The amount of collateral required if all of the principal required is drawn down.

```solidity
    function collateralRequired()
        view
        returns (
            uint256 collateralRequired_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralRequired_` | `uint256` | `uint256` |  |


<br />

### `drawableFunds` 

The amount of funds that have yet to be drawn down by the borrower.

```solidity
    function drawableFunds()
        view
        returns (
            uint256 drawableFunds_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `drawableFunds_` | `uint256` | `uint256` |  |


<br />

### `drawdownFunds` 

Draw down funds from the loan.

```solidity
    function drawdownFunds(
        uint256 amount_,
        address destination_
    )
        nonpayable
        returns (
            uint256 collateralPosted_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount to draw down. |
| 1 | `destination_` | `address` | `address` | The address to send the funds. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralPosted_` | `uint256` | `uint256` | The amount of additional collateral posted, if any. |


<br />

### `endingPrincipal` 

The portion of principal to not be paid down as part of payment installments,       which would need to be paid back upon final payment.       If endingPrincipal &#x3D; principal, loan is interest-only.

```solidity
    function endingPrincipal()
        view
        returns (
            uint256 endingPrincipal_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `endingPrincipal_` | `uint256` | `uint256` |  |


<br />

### `excessCollateral` 

Returns the excess collateral that can be removed.

```solidity
    function excessCollateral()
        view
        returns (
            uint256 excessCollateral_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `excessCollateral_` | `uint256` | `uint256` | The excess collateral that can be removed, if any. |


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

### `feeManager` 

The address of the contract that handles payments of fees on behalf of the loan.

```solidity
    function feeManager()
        view
        returns (
            address feeManager_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `feeManager_` | `address` | `address` |  |


<br />

### `fundLoan` 

Lend funds to the loan/borrower.

```solidity
    function fundLoan()
        nonpayable
        returns (
            uint256 fundsLent_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsLent_` | `uint256` | `uint256` | The amount funded. |


<br />

### `fundsAsset` 

The asset deposited by the lender to fund the loan.

```solidity
    function fundsAsset()
        view
        returns (
            address fundsAsset_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsAsset_` | `address` | `address` |  |


<br />

### `getAdditionalCollateralRequiredFor` 

Get the additional collateral to be posted to drawdown some amount.

```solidity
    function getAdditionalCollateralRequiredFor(
        uint256 drawdown_
    )
        view
        returns (
            uint256 collateral_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `drawdown_` | `uint256` | `uint256` | The amount desired to be drawn down. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateral_` | `uint256` | `uint256` |  |


<br />

### `getClosingPaymentBreakdown` 

Get the breakdown of the total payment needed to satisfy an early repayment to close the loan.

```solidity
    function getClosingPaymentBreakdown()
        view
        returns (
            uint256 principal_,
            uint256 interest_,
            uint256 fees_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` | The portion of the total amount that will go towards principal. |
| 1 | `interest_` | `uint256` | `uint256` |  The portion of the total amount that will go towards interest fees. |
| 2 | `fees_` | `uint256` | `uint256` |      The portion of the total amount that will go towards fees. |


<br />

### `getNextPaymentBreakdown` 

Get the breakdown of the total payment needed to satisfy the next payment installment.

```solidity
    function getNextPaymentBreakdown()
        view
        returns (
            uint256 principal_,
            uint256 interest_,
            uint256 fees_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` | The portion of the total amount that will go towards principal. |
| 1 | `interest_` | `uint256` | `uint256` |  The portion of the total amount that will go towards interest fees. |
| 2 | `fees_` | `uint256` | `uint256` |      The portion of the total amount that will go towards paying administrative fees. |


<br />

### `getNextPaymentDetailedBreakdown` 

Get the detailed breakdown of the total payment needed to satisfy the next payment installment.

```solidity
    function getNextPaymentDetailedBreakdown()
        view
        returns (
            uint256 principal_,
            uint256[3] interest_,
            uint256[2] fees_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` | The portion of the total amount that will go towards principal. |
| 1 | `interest_` | `uint256[3]` | `uint256[3]` |  The portion of the total amount that will go towards interest fees.                      [0] Interest from the payment interval.                      [1] Late interest.                      [2] Refinance interest. |
| 2 | `fees_` | `uint256[2]` | `uint256[2]` |      The portion of the total amount that will go towards paying administrative fees.                      [0] Delegate fees.                      [1] Platform fees. |


<br />

### `getRefinanceInterest` 

Get the extra interest that will be charged according to loan terms before refinance, based on a given timestamp.

```solidity
    function getRefinanceInterest(
        uint256 timestamp_
    )
        view
        returns (
            uint256 proRataInterest_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `timestamp_` | `uint256` | `uint256` | The timestamp when the new terms will be accepted. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `proRataInterest_` | `uint256` | `uint256` | The interest portion to be added in the next payment. |


<br />

### `getUnaccountedAmount` 

Get the amount on an asset that in not accounted for by the accounting variables (and thus can be skimmed).

```solidity
    function getUnaccountedAmount(
        address asset_
    )
        view
        returns (
            uint256 unaccountedAmount_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of a asset contract. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `unaccountedAmount_` | `uint256` | `uint256` | The amount that is not accounted for. |


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

### `governor` 

The address of the Maple Governor.

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
| 0 | `governor_` | `address` | `address` |  |


<br />

### `gracePeriod` 

The amount of time the borrower has, after a payment is due, to make a payment before being in default.

```solidity
    function gracePeriod()
        view
        returns (
            uint256 gracePeriod_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `gracePeriod_` | `uint256` | `uint256` |  |


<br />

### `impairLoan` 

Fast forward the next payment due date to the current time.       This enables the pool delegate to force a payment (or default).

```solidity
    function impairLoan()
        nonpayable;
```



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
            uint256 interestRate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `interestRate_` | `uint256` | `uint256` |  |


<br />

### `isImpaired` 

Return if the loan has been impaired.

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
| 0 | `isImpaired_` | `bool` | `bool` | Is the loan impaired or not. |


<br />

### `lateFeeRate` 

The rate charged at late payments.

```solidity
    function lateFeeRate()
        view
        returns (
            uint256 lateFeeRate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateFeeRate_` | `uint256` | `uint256` |  |


<br />

### `lateInterestPremiumRate` 

The premium over the regular interest rate applied when paying late.

```solidity
    function lateInterestPremiumRate()
        view
        returns (
            uint256 lateInterestPremiumRate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lateInterestPremiumRate_` | `uint256` | `uint256` |  |


<br />

### `lender` 

The lender of the Loan.

```solidity
    function lender()
        view
        returns (
            address lender_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lender_` | `address` | `address` |  |


<br />

### `makePayment` 

Make a payment to the loan.          FUNDS SHOULD NOT BE TRANSFERRED TO THIS CONTRACT NON-ATOMICALLY. IF THEY ARE, THE BALANCE MAY BE STOLEN USING &#x60;skim&#x60;.

```solidity
    function makePayment(
        uint256 amount_
    )
        nonpayable
        returns (
            uint256 principal_,
            uint256 interest_,
            uint256 fees_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | An amount to pull from the caller, if any. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` | The portion of the amount paying back principal. |
| 1 | `interest_` | `uint256` | `uint256` |  The portion of the amount paying interest fees. |
| 2 | `fees_` | `uint256` | `uint256` |      The portion of the amount paying service fees. |


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

### `nextPaymentDueDate` 

The timestamp due date of the next payment.

```solidity
    function nextPaymentDueDate()
        view
        returns (
            uint256 nextPaymentDueDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `nextPaymentDueDate_` | `uint256` | `uint256` |  |


<br />

### `originalNextPaymentDueDate` 

The saved original payment due date from a loan impairment.

```solidity
    function originalNextPaymentDueDate()
        view
        returns (
            uint256 originalNextPaymentDueDate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `originalNextPaymentDueDate_` | `uint256` | `uint256` |  |


<br />

### `paymentInterval` 

The specified time between loan payments.

```solidity
    function paymentInterval()
        view
        returns (
            uint256 paymentInterval_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentInterval_` | `uint256` | `uint256` |  |


<br />

### `paymentsRemaining` 

The number of payment installments remaining for the loan.

```solidity
    function paymentsRemaining()
        view
        returns (
            uint256 paymentsRemaining_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentsRemaining_` | `uint256` | `uint256` |  |


<br />

### `pendingBorrower` 

The address of the pending borrower.

```solidity
    function pendingBorrower()
        view
        returns (
            address pendingBorrower_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingBorrower_` | `address` | `address` |  |


<br />

### `pendingLender` 

The address of the pending lender.

```solidity
    function pendingLender()
        view
        returns (
            address pendingLender_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingLender_` | `address` | `address` |  |


<br />

### `postCollateral` 

Post collateral to the loan.          FUNDS SHOULD NOT BE TRANSFERRED TO THIS CONTRACT NON-ATOMICALLY. IF THEY ARE, THE BALANCE MAY BE STOLEN USING &#x60;skim&#x60;.

```solidity
    function postCollateral(
        uint256 amount_
    )
        nonpayable
        returns (
            uint256 collateralPosted_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | An amount to pull from the caller, if any. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralPosted_` | `uint256` | `uint256` | The amount posted. |


<br />

### `principal` 

The amount of principal owed (initially, the requested amount), which needs to be paid back.

```solidity
    function principal()
        view
        returns (
            uint256 principal_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` |  |


<br />

### `principalRequested` 

The initial principal amount requested by the borrower.

```solidity
    function principalRequested()
        view
        returns (
            uint256 principalRequested_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalRequested_` | `uint256` | `uint256` |  |


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
            bytes32 refinanceCommitment_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` |  |


<br />

### `refinanceInterest` 

Amount of unpaid interest that has accrued before a refinance was accepted.

```solidity
    function refinanceInterest()
        view
        returns (
            uint256 refinanceInterest_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceInterest_` | `uint256` | `uint256` |  |


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

### `removeCollateral` 

Remove collateral from the loan (opposite of posting collateral).

```solidity
    function removeCollateral(
        uint256 amount_,
        address destination_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount removed. |
| 1 | `destination_` | `address` | `address` | The destination to send the removed collateral. |


<br />

### `removeLoanImpairment` 

Remove the loan impairment by restoring the original payment due date.

```solidity
    function removeLoanImpairment()
        nonpayable;
```



<br />

### `repossess` 

Repossess collateral, and any funds, for a loan in default.

```solidity
    function repossess(
        address destination_
    )
        nonpayable
        returns (
            uint256 collateralRepossessed_,
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
| 0 | `collateralRepossessed_` | `uint256` | `uint256` | The amount of collateral asset repossessed. |
| 1 | `fundsRepossessed_` | `uint256` | `uint256` |      The amount of funds asset repossessed. |


<br />

### `returnFunds` 

Return funds to the loan (opposite of drawing down).          FUNDS SHOULD NOT BE TRANSFERRED TO THIS CONTRACT NON-ATOMICALLY. IF THEY ARE, THE BALANCE MAY BE STOLEN USING &#x60;skim&#x60;.

```solidity
    function returnFunds(
        uint256 amount_
    )
        nonpayable
        returns (
            uint256 fundsReturned_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | An amount to pull from the caller, if any. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsReturned_` | `uint256` | `uint256` | The amount returned. |


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

Set the pendingBorrower to a new account.

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

Set the pendingLender to a new account.

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

Remove all token that is not accounted for by the loan (i.e. not &#x60;collateral&#x60; or &#x60;drawableFunds&#x60;).

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

### `CollateralPosted`

Collateral was posted.

```solidity
    event CollateralPosted(
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of collateral posted. |

<br />

### `CollateralRemoved`

Collateral was removed.

```solidity
    event CollateralRemoved(
        uint256 amount_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of collateral removed. |
| 1 | `destination_` | `address` | `address` | The recipient of the collateral removed. |

<br />

### `Funded`

The loan was funded.

```solidity
    event Funded(
        address lender_,
        uint256 amount_,
        uint256 nextPaymentDueDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lender_` | `address` | `address` | The address of the lender. |
| 1 | `amount_` | `uint256` | `uint256` | The amount funded. |
| 2 | `nextPaymentDueDate_` | `uint256` | `uint256` | The due date of the next payment. |

<br />

### `FundsClaimed`

Funds were claimed.

```solidity
    event FundsClaimed(
        uint256 amount_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of funds claimed. |
| 1 | `destination_` | `address` | `address` | The recipient of the funds claimed. |

<br />

### `FundsDrawnDown`

Funds were drawn.

```solidity
    event FundsDrawnDown(
        uint256 amount_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of funds drawn. |
| 1 | `destination_` | `address` | `address` | The recipient of the funds drawn down. |

<br />

### `FundsReturned`

Funds were returned.

```solidity
    event FundsReturned(
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of funds returned. |

<br />

### `ImpairmentRemoved`

The loan impairment was explicitly removed (i.e. not the result of a payment or new terms acceptance).

```solidity
    event ImpairmentRemoved(
        uint256 nextPaymentDueDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `nextPaymentDueDate_` | `uint256` | `uint256` | The new next payment due date. |

<br />

### `Initialized`

Loan was initialized.

```solidity
    event Initialized(
        address borrower_,
        address lender_,
        address feeManager_,
        address[2] assets_,
        uint256[3] termDetails_,
        uint256[3] amounts_,
        uint256[4] rates_,
        uint256[2] fees_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` | The address of the borrower. |
| 1 | `lender_` | `address` | `address` | The address of the lender. |
| 2 | `feeManager_` | `address` | `address` | The address of the entity responsible for calculating fees. |
| 3 | `assets_` | `address[2]` | `address[2]` | Array of asset addresses.                       [0]: collateralAsset,                       [1]: fundsAsset. |
| 4 | `termDetails_` | `uint256[3]` | `uint256[3]` | Array of loan parameters:                       [0]: gracePeriod,                       [1]: paymentInterval,                       [2]: payments, |
| 5 | `amounts_` | `uint256[3]` | `uint256[3]` | Requested amounts:                       [0]: collateralRequired,                       [1]: principalRequested,                       [2]: endingPrincipal. |
| 6 | `rates_` | `uint256[4]` | `uint256[4]` | Fee parameters:                       [0]: interestRate,                       [1]: closingFeeRate,                       [2]: lateFeeRate,                       [3]: lateInterestPremiumRate |
| 7 | `fees_` | `uint256[2]` | `uint256[2]` | Array of fees:                       [0]: delegateOriginationFee,                       [1]: delegateServiceFee |

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

### `LoanClosed`

Loan was repaid early and closed.

```solidity
    event LoanClosed(
        uint256 principalPaid_,
        uint256 interestPaid_,
        uint256 feesPaid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards principal. |
| 1 | `interestPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards interest. |
| 2 | `feesPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards fees. |

<br />

### `LoanImpaired`

The next payment due date was fast forwarded to the current time, activating the grace period.         This is emitted when the pool delegate wants to force a payment (or default).

```solidity
    event LoanImpaired(
        uint256 nextPaymentDueDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `nextPaymentDueDate_` | `uint256` | `uint256` | The new next payment due date. |

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
        uint256 principalPaid_,
        uint256 interestPaid_,
        uint256 fees_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards principal. |
| 1 | `interestPaid_` | `uint256` | `uint256` | The portion of the total amount that went towards interest. |
| 2 | `fees_` | `uint256` | `uint256` | The portion of the total amount that went towards fees. |

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
| 0 | `pendingLender_` | `address` | `address` | Address that can accept the lender role. |

<br />

### `Repossessed`

The loan was in default and funds and collateral was repossessed by the lender.

```solidity
    event Repossessed(
        uint256 collateralRepossessed_,
        uint256 fundsRepossessed_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralRepossessed_` | `uint256` | `uint256` | The amount of collateral asset repossessed. |
| 1 | `fundsRepossessed_` | `uint256` | `uint256` | The amount of funds asset repossessed. |
| 2 | `destination_` | `address` | `address` | The recipient of the collateral and funds, if any. |

<br />

### `Skimmed`

Some token (neither fundsAsset nor collateralAsset) was removed from the loan.

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

