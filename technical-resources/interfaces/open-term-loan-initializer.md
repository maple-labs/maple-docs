# Maple Open Term Loan Initializer



<br />


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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `calledPrincipal`



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

### `dateCalled`



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` | The encoded arguments for initializing a loan. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |           The address of the borrower. |
| 1 | `lender_` | `address` | `address` |             The address of the lender. |
| 2 | `fundsAsset_` | `address` | `address` |         The address of the lent asset. |
| 3 | `principalRequested_` | `uint256` | `uint256` | The amount of principal requested. |
| 4 | `termDetails_` | `uint32[3]` | `uint32[3]` |        Array of loan parameters:                                  [0]: gracePeriod,                                  [1]: noticePeriod,                                  [2]: paymentInterval |
| 5 | `rates_` | `uint64[4]` | `uint64[4]` |              Array of rate parameters:                                  [0]: delegateServiceFeeRate,                                  [1]: interestRate,                                  [2]: lateFeeRate,                                  [3]: lateInterestPremiumRate |


<br />

### `delegateServiceFeeRate`



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` | The address of the borrower. |
| 1 | `lender_` | `address` | `address` | The address of the lender. |
| 2 | `fundsAsset_` | `address` | `address` | The address of the lent asset. |
| 3 | `principalRequested_` | `uint256` | `uint256` | The amount of principal requested. |
| 4 | `termDetails_` | `uint32[3]` | `uint32[3]` | Array of loan parameters:                                  [0]: gracePeriod,                                  [1]: noticePeriod,                                  [2]: paymentInterval |
| 5 | `rates_` | `uint64[4]` | `uint64[4]` | Array of rate parameters:                                  [0]: delegateServiceFeeRate,                                  [1]: interestRate,                                  [2]: lateFeeRate,                                  [3]: lateInterestPremiumRate |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` |  The encoded arguments for initializing a loan. |


<br />

### `fundsAsset`



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

### `gracePeriod`



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

### `interestRate`



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

### `lateFeeRate`



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

### `noticePeriod`



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

### `paymentInterval`



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

### `refinanceCommitment`



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

### `CallRemoved`



```solidity
    event CallRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` |  |
| 1 | `defaultDate_` | `uint40` | `uint40` |  |

<br />

### `Funded`



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
| 0 | `amount_` | `uint256` | `uint256` |  |
| 1 | `paymentDueDate_` | `uint40` | `uint40` |  |
| 2 | `defaultDate_` | `uint40` | `uint40` |  |

<br />

### `Impaired`



```solidity
    event Impaired(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` |  |
| 1 | `defaultDate_` | `uint40` | `uint40` |  |

<br />

### `ImpairmentRemoved`



```solidity
    event ImpairmentRemoved(
        uint40 paymentDueDate_,
        uint40 defaultDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `paymentDueDate_` | `uint40` | `uint40` |  |
| 1 | `defaultDate_` | `uint40` | `uint40` |  |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |  |
| 1 | `lender_` | `address` | `address` |  |
| 2 | `fundsAsset_` | `address` | `address` |  |
| 3 | `principalRequested_` | `uint256` | `uint256` |  |
| 4 | `termDetails_` | `uint32[3]` | `uint32[3]` |  |
| 5 | `rates_` | `uint64[4]` | `uint64[4]` |  |

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
| 0 | `lender_` | `address` | `address` |  |
| 1 | `principalPaid_` | `uint256` | `uint256` |  |
| 2 | `interestPaid_` | `uint256` | `uint256` |  |
| 3 | `lateInterestPaid_` | `uint256` | `uint256` |  |
| 4 | `delegateServiceFee_` | `uint256` | `uint256` |  |
| 5 | `platformServiceFee_` | `uint256` | `uint256` |  |
| 6 | `paymentDueDate_` | `uint40` | `uint40` |  |
| 7 | `defaultDate_` | `uint40` | `uint40` |  |

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

### `PrincipalCalled`



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
| 0 | `principalToReturn_` | `uint256` | `uint256` |  |
| 1 | `paymentDueDate_` | `uint40` | `uint40` |  |
| 2 | `defaultDate_` | `uint40` | `uint40` |  |

<br />

### `PrincipalReturned`



```solidity
    event PrincipalReturned(
        uint256 principalReturned_,
        uint256 principalRemaining_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalReturned_` | `uint256` | `uint256` |  |
| 1 | `principalRemaining_` | `uint256` | `uint256` |  |

<br />

### `Repossessed`



```solidity
    event Repossessed(
        uint256 fundsRepossessed_,
        address destination_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsRepossessed_` | `uint256` | `uint256` |  |
| 1 | `destination_` | `address` | `address` |  |

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

