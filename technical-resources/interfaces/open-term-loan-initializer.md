# OpenTermLoanInitializer



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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `calledPrincipal`

```solidity
    function calledPrincipal()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



### `dateCalled`

```solidity
    function dateCalled()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `dateFunded`

```solidity
    function dateFunded()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `dateImpaired`

```solidity
    function dateImpaired()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `datePaid`

```solidity
    function datePaid()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `decodeArguments`

Decodes the initialization arguments for a MapleLoan.

```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address borrower_,
            address lender_,
            address fundsAsset_,
            uint256 principalRequested_,
            uint32[3] termDetails_,
            uint64[4] rates_
        );
```

#### Parameters:

| Index |         Name        |   Type  | Internal Type | Description                                    |
| :---: | :-----------------: | :-----: | :-----------: | ---------------------------------------------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    | The encoded arguments for initializing a loan. |

#### Return Values:

| Index |          Name         |     Type    | Internal Type | Description                                                                                                                  |
| :---: | :-------------------: | :---------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------- |
|   0   |      `borrower_`      |  `address`  |   `address`   | The address of the borrower.                                                                                                 |
|   1   |       `lender_`       |  `address`  |   `address`   | The address of the lender.                                                                                                   |
|   2   |     `fundsAsset_`     |  `address`  |   `address`   | The address of the lent asset.                                                                                               |
|   3   | `principalRequested_` |  `uint256`  |   `uint256`   | The amount of principal requested.                                                                                           |
|   4   |     `termDetails_`    | `uint32[3]` |  `uint32[3]`  | Array of loan parameters: \[0]: gracePeriod, \[1]: noticePeriod, \[2]: paymentInterval                                       |
|   5   |        `rates_`       | `uint64[4]` |  `uint64[4]`  | Array of rate parameters: \[0]: delegateServiceFeeRate, \[1]: interestRate, \[2]: lateFeeRate, \[3]: lateInterestPremiumRate |



### `delegateServiceFeeRate`

```solidity
    function delegateServiceFeeRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `encodeArguments`

Encodes the initialization arguments for a MapleLoan.

```solidity
    function encodeArguments(
        address borrower_,
        address lender_,
        address fundsAsset_,
        uint256 principalRequested_,
        uint32[3] termDetails_,
        uint64[4] rates_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:

| Index |          Name         |     Type    | Internal Type | Description                                                                                                                  |
| :---: | :-------------------: | :---------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------- |
|   0   |      `borrower_`      |  `address`  |   `address`   | The address of the borrower.                                                                                                 |
|   1   |       `lender_`       |  `address`  |   `address`   | The address of the lender.                                                                                                   |
|   2   |     `fundsAsset_`     |  `address`  |   `address`   | The address of the lent asset.                                                                                               |
|   3   | `principalRequested_` |  `uint256`  |   `uint256`   | The amount of principal requested.                                                                                           |
|   4   |     `termDetails_`    | `uint32[3]` |  `uint32[3]`  | Array of loan parameters: \[0]: gracePeriod, \[1]: noticePeriod, \[2]: paymentInterval                                       |
|   5   |        `rates_`       | `uint64[4]` |  `uint64[4]`  | Array of rate parameters: \[0]: delegateServiceFeeRate, \[1]: interestRate, \[2]: lateFeeRate, \[3]: lateInterestPremiumRate |

#### Return Values:

| Index |         Name        |   Type  | Internal Type | Description                                    |
| :---: | :-----------------: | :-----: | :-----------: | ---------------------------------------------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    | The encoded arguments for initializing a loan. |



### `fundsAsset`

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



### `gracePeriod`

```solidity
    function gracePeriod()
        view
        returns (
            uint32
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint32` |    `uint32`   |             |



### `interestRate`

```solidity
    function interestRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `lateFeeRate`

```solidity
    function lateFeeRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `lateInterestPremiumRate`

```solidity
    function lateInterestPremiumRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `lender`

```solidity
    function lender()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `noticePeriod`

```solidity
    function noticePeriod()
        view
        returns (
            uint32
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint32` |    `uint32`   |             |



### `paymentInterval`

```solidity
    function paymentInterval()
        view
        returns (
            uint32
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint32` |    `uint32`   |             |



### `pendingBorrower`

```solidity
    function pendingBorrower()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `pendingLender`

```solidity
    function pendingLender()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `platformServiceFeeRate`

```solidity
    function platformServiceFeeRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `principal`

```solidity
    function principal()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



### `refinanceCommitment`

```solidity
    function refinanceCommitment()
        view
        returns (
            bytes32
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `bytes32` |   `bytes32`   |             |



## Events

### `BorrowerAccepted`

Borrower was accepted, and set to a new account.

```solidity
    event BorrowerAccepted(
        address indexed borrower_
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                      |
| :---: | :---------: | :-------: | :-----------: | -------------------------------- |
|   0   | `borrower_` | `address` |   `address`   | The address of the new borrower. |



### `CallRemoved`

The lender reverted the action of the loan being called and the payment due date was restored to it's original value.

```solidity
    event CallRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description                           |
| :---: | :---------------: | :------: | :-----------: | ------------------------------------- |
|   0   | `paymentDueDate_` | `uint40` |    `uint40`   | The restored payment due date.        |
|   1   |   `defaultDate_`  | `uint40` |    `uint40`   | The date the loan will be in default. |



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

| Index |        Name       |    Type   | Internal Type | Description                           |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------- |
|   0   |     `amount_`     | `uint256` |   `uint256`   | The amount funded.                    |
|   1   | `paymentDueDate_` |  `uint40` |    `uint40`   | The due date of the first payment.    |
|   2   |   `defaultDate_`  |  `uint40` |    `uint40`   | The date the loan will be in default. |



### `Impaired`

The payment due date was fast forwarded to the current time, activating the grace period. This is emitted when the pool delegate wants to force a payment (or default).

```solidity
    event Impaired(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description                           |
| :---: | :---------------: | :------: | :-----------: | ------------------------------------- |
|   0   | `paymentDueDate_` | `uint40` |    `uint40`   | The new payment due date.             |
|   1   |   `defaultDate_`  | `uint40` |    `uint40`   | The date the loan will be in default. |



### `ImpairmentRemoved`

The payment due date was restored to it's original value, reverting the action of loan impairment.

```solidity
    event ImpairmentRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description                           |
| :---: | :---------------: | :------: | :-----------: | ------------------------------------- |
|   0   | `paymentDueDate_` | `uint40` |    `uint40`   | The restored payment due date.        |
|   1   |   `defaultDate_`  | `uint40` |    `uint40`   | The date the loan will be in default. |



### `Initialized`

Loan was initialized.

```solidity
    event Initialized(
        address indexed borrower_,
        address indexed lender_,
        address indexed fundsAsset_,
        uint256 principalRequested_,
        uint32[3] termDetails_,
        uint64[4] rates_
    );
```

#### Parameters:

| Index |          Name         |     Type    | Internal Type | Description                                                                                                                  |
| :---: | :-------------------: | :---------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------- |
|   0   |      `borrower_`      |  `address`  |   `address`   | The address of the borrower.                                                                                                 |
|   1   |       `lender_`       |  `address`  |   `address`   | The address of the lender.                                                                                                   |
|   2   |     `fundsAsset_`     |  `address`  |   `address`   | The address of the lent asset.                                                                                               |
|   3   | `principalRequested_` |  `uint256`  |   `uint256`   | The amount of principal requested.                                                                                           |
|   4   |     `termDetails_`    | `uint32[3]` |  `uint32[3]`  | Array of loan parameters: \[0]: gracePeriod, \[1]: noticePeriod, \[2]: paymentInterval                                       |
|   5   |        `rates_`       | `uint64[4]` |  `uint64[4]`  | Array of rate parameters: \[0]: delegateServiceFeeRate, \[1]: interestRate, \[2]: lateFeeRate, \[3]: lateInterestPremiumRate |



### `LenderAccepted`

Lender was accepted, and set to a new account.

```solidity
    event LenderAccepted(
        address indexed lender_
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                    |
| :---: | :-------: | :-------: | :-----------: | ------------------------------ |
|   0   | `lender_` | `address` |   `address`   | The address of the new lender. |



### `LoanTermsAccepted`

The loan terms were accepted by the borrower.

```solidity
    event LoanTermsAccepted();
```



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

| Index |          Name          |    Type   | Internal Type | Description                                               |
| :---: | :--------------------: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   | `refinanceCommitment_` | `bytes32` |   `bytes32`   | The hash of the refinancer, deadline, and calls proposed. |
|   1   |      `refinancer_`     | `address` |   `address`   | The address that will execute the refinance.              |
|   2   |       `deadline_`      | `uint256` |   `uint256`   | The deadline for accepting the new terms.                 |
|   3   |        `calls_`        | `bytes[]` |   `bytes[]`   | The individual calls for the refinancer contract.         |



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

| Index |          Name          |    Type   | Internal Type | Description                                               |
| :---: | :--------------------: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   | `refinanceCommitment_` | `bytes32` |   `bytes32`   | The hash of the refinancer, deadline, and calls proposed. |
|   1   |      `refinancer_`     | `address` |   `address`   | The address that will execute the refinance.              |
|   2   |       `deadline_`      | `uint256` |   `uint256`   | The deadline for accepting the new terms.                 |
|   3   |        `calls_`        | `bytes[]` |   `bytes[]`   | The individual calls for the refinancer contract.         |



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

| Index |          Name          |    Type   | Internal Type | Description                                               |
| :---: | :--------------------: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   | `refinanceCommitment_` | `bytes32` |   `bytes32`   | The hash of the refinancer, deadline, and calls proposed. |
|   1   |      `refinancer_`     | `address` |   `address`   | The address that will execute the refinance.              |
|   2   |       `deadline_`      | `uint256` |   `uint256`   | The deadline for accepting the new terms.                 |
|   3   |        `calls_`        | `bytes[]` |   `bytes[]`   | The individual calls for the refinancer contract.         |



### `PaymentMade`

Payments were made.

```solidity
    event PaymentMade(
        address indexed lender_,
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

| Index |          Name         |    Type   | Internal Type | Description                                                              |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------------------------------------------ |
|   0   |       `lender_`       | `address` |   `address`   | The address of the lender the payment was made to.                       |
|   1   |    `principalPaid_`   | `uint256` |   `uint256`   | The portion of the total amount that went towards paying down principal. |
|   2   |    `interestPaid_`    | `uint256` |   `uint256`   | The portion of the total amount that went towards interest.              |
|   3   |  `lateInterestPaid_`  | `uint256` |   `uint256`   | The portion of the total amount that went towards late interest.         |
|   4   | `delegateServiceFee_` | `uint256` |   `uint256`   | The portion of the total amount that went towards delegate service fees. |
|   5   | `platformServiceFee_` | `uint256` |   `uint256`   | The portion of the total amount that went towards platform service fee.  |
|   6   |   `paymentDueDate_`   |  `uint40` |    `uint40`   | The new payment due date.                                                |
|   7   |     `defaultDate_`    |  `uint40` |    `uint40`   | The date the loan will be in default.                                    |



### `PendingBorrowerSet`

Pending borrower was set.

```solidity
    event PendingBorrowerSet(
        address indexed pendingBorrower_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                                |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `pendingBorrower_` | `address` |   `address`   | Address that can accept the borrower role. |



### `PendingLenderSet`

Pending lender was set.

```solidity
    event PendingLenderSet(
        address indexed pendingLender_
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                  |
| :---: | :--------------: | :-------: | :-----------: | -------------------------------------------- |
|   0   | `pendingLender_` | `address` |   `address`   | The address that can accept the lender role. |



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

| Index |         Name         |    Type   | Internal Type | Description                                               |
| :---: | :------------------: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   | `principalToReturn_` | `uint256` |   `uint256`   | The minimum amount of principal the borrower must return. |
|   1   |   `paymentDueDate_`  |  `uint40` |    `uint40`   | The new payment due date.                                 |
|   2   |    `defaultDate_`    |  `uint40` |    `uint40`   | The date the loan will be in default.                     |



### `PrincipalReturned`

Principal was returned to lender, to close the loan or return future interest payments.

```solidity
    event PrincipalReturned(
        uint256 principalReturned_,
        uint256 principalRemaining_
    );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                    |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   |  `principalReturned_` | `uint256` |   `uint256`   | The amount of principal returned.              |
|   1   | `principalRemaining_` | `uint256` |   `uint256`   | The amount of principal remaining on the loan. |



### `Repossessed`

The loan was in default and funds and collateral was repossessed by the lender.

```solidity
    event Repossessed(
        uint256 fundsRepossessed_,
        address indexed destination_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                                        |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   | `fundsRepossessed_` | `uint256` |   `uint256`   | The amount of funds asset repossessed.             |
|   1   |    `destination_`   | `address` |   `address`   | The address of the recipient of the funds, if any. |



### `Skimmed`

Some token was removed from the loan.

```solidity
    event Skimmed(
        address indexed token_,
        uint256 amount_,
        address indexed destination_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                               |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |    `token_`    | `address` |   `address`   | The address of the token contract.        |
|   1   |    `amount_`   | `uint256` |   `uint256`   | The amount of token remove from the loan. |
|   2   | `destination_` | `address` |   `address`   | The recipient of the token.               |

