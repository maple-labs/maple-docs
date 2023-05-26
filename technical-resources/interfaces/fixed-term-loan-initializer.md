# Maple Fixed Term Loan Initializer



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
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |    The address of the borrower. |
| 1 | `lender_` | `address` | `address` |      The address of the lender. |
| 2 | `feeManager_` | `address` | `address` |  The address of the entity responsible for calculating fees. |
| 3 | `assets_` | `address[2]` | `address[2]` |      Array of asset addresses.                        [0]: collateralAsset,                        [1]: fundsAsset |
| 4 | `termDetails_` | `uint256[3]` | `uint256[3]` | Array of loan parameters:                        [0]: gracePeriod,                        [1]: paymentInterval,                        [2]: payments |
| 5 | `amounts_` | `uint256[3]` | `uint256[3]` |     Requested amounts:                        [0]: collateralRequired,                        [1]: principalRequested,                        [2]: endingPrincipal |
| 6 | `rates_` | `uint256[4]` | `uint256[4]` |       Rates parameters:                        [0]: interestRate,                        [1]: closingFeeRate,                        [2]: lateFeeRate,                        [3]: lateInterestPremiumRate, |
| 7 | `fees_` | `uint256[2]` | `uint256[2]` |        Array of fees:                        [0]: delegateOriginationFee,                        [1]: delegateServiceFee |


<br />

### `encodeArguments`

Encodes the initialization arguments for a MapleLoan.

```solidity
    function encodeArguments(
        address borrower_,
        address lender_,
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
| 1 | `lender_` | `address` | `address` | The address of the lender. |
| 2 | `feeManager_` | `address` | `address` | The address of the entity responsible for calculating fees. |
| 3 | `assets_` | `address[2]` | `address[2]` | Array of asset addresses.                       [0]: collateralAsset,                       [1]: fundsAsset |
| 4 | `termDetails_` | `uint256[3]` | `uint256[3]` | Array of loan parameters:                       [0]: gracePeriod,                       [1]: paymentInterval,                       [2]: payments |
| 5 | `amounts_` | `uint256[3]` | `uint256[3]` | Requested amounts:                       [0]: collateralRequired,                       [1]: principalRequested,                       [2]: endingPrincipal |
| 6 | `rates_` | `uint256[4]` | `uint256[4]` | Rates parameters:                       [0]: interestRate,                       [1]: closingFeeRate,                       [2]: lateFeeRate,                       [3]: lateInterestPremiumRate, |
| 7 | `fees_` | `uint256[2]` | `uint256[2]` | Array of fees:                       [0]: delegateOriginationFee,                       [1]: delegateServiceFee |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


<br />


## Events

### `BorrowerAccepted`



```solidity
    event BorrowerAccepted(
        address borrower_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |  |

<br />

### `CollateralPosted`



```solidity
    event CollateralPosted(
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` |  |

<br />

### `CollateralRemoved`



```solidity
    event CollateralRemoved(
        uint256 amount_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` |  |
| 1 | `destination_` | `address` | `address` |  |

<br />

### `Funded`



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
| 0 | `lender_` | `address` | `address` |  |
| 1 | `amount_` | `uint256` | `uint256` |  |
| 2 | `nextPaymentDueDate_` | `uint256` | `uint256` |  |

<br />

### `FundsClaimed`



```solidity
    event FundsClaimed(
        uint256 amount_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` |  |
| 1 | `destination_` | `address` | `address` |  |

<br />

### `FundsDrawnDown`



```solidity
    event FundsDrawnDown(
        uint256 amount_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` |  |
| 1 | `destination_` | `address` | `address` |  |

<br />

### `FundsReturned`



```solidity
    event FundsReturned(
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` |  |

<br />

### `ImpairmentRemoved`



```solidity
    event ImpairmentRemoved(
        uint256 nextPaymentDueDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `nextPaymentDueDate_` | `uint256` | `uint256` |  |

<br />

### `Initialized`



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
| 0 | `borrower_` | `address` | `address` |  |
| 1 | `lender_` | `address` | `address` |  |
| 2 | `feeManager_` | `address` | `address` |  |
| 3 | `assets_` | `address[2]` | `address[2]` |  |
| 4 | `termDetails_` | `uint256[3]` | `uint256[3]` |  |
| 5 | `amounts_` | `uint256[3]` | `uint256[3]` |  |
| 6 | `rates_` | `uint256[4]` | `uint256[4]` |  |
| 7 | `fees_` | `uint256[2]` | `uint256[2]` |  |

<br />

### `LenderAccepted`



```solidity
    event LenderAccepted(
        address lender_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lender_` | `address` | `address` |  |

<br />

### `LoanClosed`



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
| 0 | `principalPaid_` | `uint256` | `uint256` |  |
| 1 | `interestPaid_` | `uint256` | `uint256` |  |
| 2 | `feesPaid_` | `uint256` | `uint256` |  |

<br />

### `LoanImpaired`



```solidity
    event LoanImpaired(
        uint256 nextPaymentDueDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `nextPaymentDueDate_` | `uint256` | `uint256` |  |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` |  |
| 1 | `refinancer_` | `address` | `address` |  |
| 2 | `deadline_` | `uint256` | `uint256` |  |
| 3 | `calls_` | `bytes[]` | `bytes[]` |  |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` |  |
| 1 | `refinancer_` | `address` | `address` |  |
| 2 | `deadline_` | `uint256` | `uint256` |  |
| 3 | `calls_` | `bytes[]` | `bytes[]` |  |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinanceCommitment_` | `bytes32` | `bytes32` |  |
| 1 | `refinancer_` | `address` | `address` |  |
| 2 | `deadline_` | `uint256` | `uint256` |  |
| 3 | `calls_` | `bytes[]` | `bytes[]` |  |

<br />

### `PaymentMade`



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
| 0 | `principalPaid_` | `uint256` | `uint256` |  |
| 1 | `interestPaid_` | `uint256` | `uint256` |  |
| 2 | `fees_` | `uint256` | `uint256` |  |

<br />

### `PendingBorrowerSet`



```solidity
    event PendingBorrowerSet(
        address pendingBorrower_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingBorrower_` | `address` | `address` |  |

<br />

### `PendingLenderSet`



```solidity
    event PendingLenderSet(
        address pendingLender_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingLender_` | `address` | `address` |  |

<br />

### `Repossessed`



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
| 0 | `collateralRepossessed_` | `uint256` | `uint256` |  |
| 1 | `fundsRepossessed_` | `uint256` | `uint256` |  |
| 2 | `destination_` | `address` | `address` |  |

<br />

### `Skimmed`



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
| 0 | `token_` | `address` | `address` |  |
| 1 | `amount_` | `uint256` | `uint256` |  |
| 2 | `destination_` | `address` | `address` |  |

<br />

