# OpenTermLoanInitializer

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


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

\


## Events

### `BorrowerAccepted`

```solidity
    event BorrowerAccepted(
        address borrower_
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description |
| :---: | :---------: | :-------: | :-----------: | ----------- |
|   0   | `borrower_` | `address` |   `address`   |             |

\


### `CallRemoved`

```solidity
    event CallRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description |
| :---: | :---------------: | :------: | :-----------: | ----------- |
|   0   | `paymentDueDate_` | `uint40` |    `uint40`   |             |
|   1   |   `defaultDate_`  | `uint40` |    `uint40`   |             |

\


### `Funded`

```solidity
    event Funded(
        uint256 amount_,
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   |     `amount_`     | `uint256` |   `uint256`   |             |
|   1   | `paymentDueDate_` |  `uint40` |    `uint40`   |             |
|   2   |   `defaultDate_`  |  `uint40` |    `uint40`   |             |

\


### `Impaired`

```solidity
    event Impaired(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description |
| :---: | :---------------: | :------: | :-----------: | ----------- |
|   0   | `paymentDueDate_` | `uint40` |    `uint40`   |             |
|   1   |   `defaultDate_`  | `uint40` |    `uint40`   |             |

\


### `ImpairmentRemoved`

```solidity
    event ImpairmentRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description |
| :---: | :---------------: | :------: | :-----------: | ----------- |
|   0   | `paymentDueDate_` | `uint40` |    `uint40`   |             |
|   1   |   `defaultDate_`  | `uint40` |    `uint40`   |             |

\


### `Initialized`

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

| Index |          Name         |     Type    | Internal Type | Description |
| :---: | :-------------------: | :---------: | :-----------: | ----------- |
|   0   |      `borrower_`      |  `address`  |   `address`   |             |
|   1   |       `lender_`       |  `address`  |   `address`   |             |
|   2   |     `fundsAsset_`     |  `address`  |   `address`   |             |
|   3   | `principalRequested_` |  `uint256`  |   `uint256`   |             |
|   4   |     `termDetails_`    | `uint32[3]` |  `uint32[3]`  |             |
|   5   |        `rates_`       | `uint64[4]` |  `uint64[4]`  |             |

\


### `LenderAccepted`

```solidity
    event LenderAccepted(
        address lender_
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   | `lender_` | `address` |   `address`   |             |

\


### `NewTermsAccepted`

```solidity
    event NewTermsAccepted(
        bytes32 refinanceCommitment_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    );
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description |
| :---: | :--------------------: | :-------: | :-----------: | ----------- |
|   0   | `refinanceCommitment_` | `bytes32` |   `bytes32`   |             |
|   1   |      `refinancer_`     | `address` |   `address`   |             |
|   2   |       `deadline_`      | `uint256` |   `uint256`   |             |
|   3   |        `calls_`        | `bytes[]` |   `bytes[]`   |             |

\


### `NewTermsProposed`

```solidity
    event NewTermsProposed(
        bytes32 refinanceCommitment_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    );
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description |
| :---: | :--------------------: | :-------: | :-----------: | ----------- |
|   0   | `refinanceCommitment_` | `bytes32` |   `bytes32`   |             |
|   1   |      `refinancer_`     | `address` |   `address`   |             |
|   2   |       `deadline_`      | `uint256` |   `uint256`   |             |
|   3   |        `calls_`        | `bytes[]` |   `bytes[]`   |             |

\


### `NewTermsRejected`

```solidity
    event NewTermsRejected(
        bytes32 refinanceCommitment_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    );
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description |
| :---: | :--------------------: | :-------: | :-----------: | ----------- |
|   0   | `refinanceCommitment_` | `bytes32` |   `bytes32`   |             |
|   1   |      `refinancer_`     | `address` |   `address`   |             |
|   2   |       `deadline_`      | `uint256` |   `uint256`   |             |
|   3   |        `calls_`        | `bytes[]` |   `bytes[]`   |             |

\


### `PaymentMade`

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

| Index |          Name         |    Type   | Internal Type | Description |
| :---: | :-------------------: | :-------: | :-----------: | ----------- |
|   0   |       `lender_`       | `address` |   `address`   |             |
|   1   |    `principalPaid_`   | `uint256` |   `uint256`   |             |
|   2   |    `interestPaid_`    | `uint256` |   `uint256`   |             |
|   3   |  `lateInterestPaid_`  | `uint256` |   `uint256`   |             |
|   4   | `delegateServiceFee_` | `uint256` |   `uint256`   |             |
|   5   | `platformServiceFee_` | `uint256` |   `uint256`   |             |
|   6   |   `paymentDueDate_`   |  `uint40` |    `uint40`   |             |
|   7   |     `defaultDate_`    |  `uint40` |    `uint40`   |             |

\


### `PendingBorrowerSet`

```solidity
    event PendingBorrowerSet(
        address pendingBorrower_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description |
| :---: | :----------------: | :-------: | :-----------: | ----------- |
|   0   | `pendingBorrower_` | `address` |   `address`   |             |

\


### `PendingLenderSet`

```solidity
    event PendingLenderSet(
        address pendingLender_
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description |
| :---: | :--------------: | :-------: | :-----------: | ----------- |
|   0   | `pendingLender_` | `address` |   `address`   |             |

\


### `PrincipalCalled`

```solidity
    event PrincipalCalled(
        uint256 principalToReturn_,
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description |
| :---: | :------------------: | :-------: | :-----------: | ----------- |
|   0   | `principalToReturn_` | `uint256` |   `uint256`   |             |
|   1   |   `paymentDueDate_`  |  `uint40` |    `uint40`   |             |
|   2   |    `defaultDate_`    |  `uint40` |    `uint40`   |             |

\


### `PrincipalReturned`

```solidity
    event PrincipalReturned(
        uint256 principalReturned_,
        uint256 principalRemaining_
    );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description |
| :---: | :-------------------: | :-------: | :-----------: | ----------- |
|   0   |  `principalReturned_` | `uint256` |   `uint256`   |             |
|   1   | `principalRemaining_` | `uint256` |   `uint256`   |             |

\


### `Repossessed`

```solidity
    event Repossessed(
        uint256 fundsRepossessed_,
        address destination_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description |
| :---: | :-----------------: | :-------: | :-----------: | ----------- |
|   0   | `fundsRepossessed_` | `uint256` |   `uint256`   |             |
|   1   |    `destination_`   | `address` |   `address`   |             |

\


### `Skimmed`

```solidity
    event Skimmed(
        address token_,
        uint256 amount_,
        address destination_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description |
| :---: | :------------: | :-------: | :-----------: | ----------- |
|   0   |    `token_`    | `address` |   `address`   |             |
|   1   |    `amount_`   | `uint256` |   `uint256`   |             |
|   2   | `destination_` | `address` |   `address`   |             |

\
