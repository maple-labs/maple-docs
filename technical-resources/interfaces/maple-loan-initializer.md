# MapleLoanInitializer



<br />


## Functions

### `decodeArguments` 

Decodes the initialization arguments for a MapleLoan.

```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address borrower_,
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
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |    The address of the borrower. |
| 1 | `feeManager_` | `address` | `address` |  The address of the entity responsible for calculating fees |
| 2 | `assets_` | `address[2]` | `address[2]` |      Array of asset addresses.                        [0]: collateralAsset,                        [1]: fundsAsset |
| 3 | `termDetails_` | `uint256[3]` | `uint256[3]` | Array of loan parameters:                        [0]: gracePeriod,                        [1]: paymentInterval,                        [2]: payments |
| 4 | `amounts_` | `uint256[3]` | `uint256[3]` |     Requested amounts:                        [0]: collateralRequired,                        [1]: principalRequested,                        [2]: endingPrincipal |
| 5 | `rates_` | `uint256[4]` | `uint256[4]` |       Rates parameters:                        [0]: interestRate,                        [1]: closingFeeRate,                        [2]: lateFeeRate,                        [3]: lateInterestPremiumRate, |
| 6 | `fees_` | `uint256[2]` | `uint256[2]` |        Array of fees:                        [0]: delegateOriginationFee,                        [1]: delegateServiceFee |


<br />

### `encodeArguments` 

Encodes the initialization arguments for a MapleLoan.

```solidity
    function encodeArguments(
        address borrower_,
        address feeManager_,
        address[2] assets_,
        uint256[3] termDetails_,
        uint256[3] amounts_,
        uint256[4] rates_,
        uint256[2] fees_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` | The address of the borrower. |
| 1 | `feeManager_` | `address` | `address` | The address of the entity responsible for calculating fees |
| 2 | `assets_` | `address[2]` | `address[2]` | Array of asset addresses.                       [0]: collateralAsset,                       [1]: fundsAsset |
| 3 | `termDetails_` | `uint256[3]` | `uint256[3]` | Array of loan parameters:                       [0]: gracePeriod,                       [1]: paymentInterval,                       [2]: payments |
| 4 | `amounts_` | `uint256[3]` | `uint256[3]` | Requested amounts:                       [0]: collateralRequired,                       [1]: principalRequested,                       [2]: endingPrincipal |
| 5 | `rates_` | `uint256[4]` | `uint256[4]` | Rates parameters:                       [0]: interestRate,                       [1]: closingFeeRate,                       [2]: lateFeeRate,                       [3]: lateInterestPremiumRate, |
| 6 | `fees_` | `uint256[2]` | `uint256[2]` | Array of fees:                       [0]: delegateOriginationFee,                       [1]: delegateServiceFee |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


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

### `Initialized`

Loan was initialized.

```solidity
    event Initialized(
        address borrower_,
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
| 1 | `feeManager_` | `address` | `address` | The address of the entity responsible for calculating fees |
| 2 | `assets_` | `address[2]` | `address[2]` | Array of asset addresses.                       [0]: collateralAsset,                       [1]: fundsAsset. |
| 3 | `termDetails_` | `uint256[3]` | `uint256[3]` | Array of loan parameters:                       [0]: gracePeriod,                       [1]: paymentInterval,                       [2]: payments, |
| 4 | `amounts_` | `uint256[3]` | `uint256[3]` | Requested amounts:                       [0]: collateralRequired,                       [1]: principalRequested,                       [2]: endingPrincipal. |
| 5 | `rates_` | `uint256[4]` | `uint256[4]` | Fee parameters:                       [0]: interestRate,                       [1]: closingFeeRate,                       [2]: lateFeeRate,                       [3]: lateInterestPremiumRate |
| 6 | `fees_` | `uint256[2]` | `uint256[2]` | Array of fees:                       [0]: delegateOriginationFee,                       [1]: delegateServiceFee |

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

### `NextPaymentDueDateRestored`

The next payment due date was restored to it&#x27;s original value, reverting the action of loan impairment.

```solidity
    event NextPaymentDueDateRestored(
        uint256 nextPaymentDueDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `nextPaymentDueDate_` | `uint256` | `uint256` | The new next payment due date. |

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

