# Loan Initializer

MapleLoanInitializer is intended to initialize the storage of a MapleLoan proxy.

\


## Functions

### `decodeArguments`

```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address borrower_,
            address[2] assets_,
            uint256[3] termDetails_,
            uint256[3] amounts_,
            uint256[4] rates_
        );
```

#### Parameters:

| Index |         Name        |   Type  | Internal Type | Description |
| :---: | :-----------------: | :-----: | :-----------: | ----------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    |             |

#### Return Values:

| Index |      Name      |     Type     | Internal Type | Description |
| :---: | :------------: | :----------: | :-----------: | ----------- |
|   0   |   `borrower_`  |   `address`  |   `address`   |             |
|   1   |    `assets_`   | `address[2]` |  `address[2]` |             |
|   2   | `termDetails_` | `uint256[3]` |  `uint256[3]` |             |
|   3   |   `amounts_`   | `uint256[3]` |  `uint256[3]` |             |
|   4   |    `rates_`    | `uint256[4]` |  `uint256[4]` |             |

\


### `encodeArguments`

```solidity
    function encodeArguments(
        address borrower_,
        address[2] assets_,
        uint256[3] termDetails_,
        uint256[3] amounts_,
        uint256[4] rates_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:

| Index |      Name      |     Type     | Internal Type | Description |
| :---: | :------------: | :----------: | :-----------: | ----------- |
|   0   |   `borrower_`  |   `address`  |   `address`   |             |
|   1   |    `assets_`   | `address[2]` |  `address[2]` |             |
|   2   | `termDetails_` | `uint256[3]` |  `uint256[3]` |             |
|   3   |   `amounts_`   | `uint256[3]` |  `uint256[3]` |             |
|   4   |    `rates_`    | `uint256[4]` |  `uint256[4]` |             |

#### Return Values:

| Index |         Name        |   Type  | Internal Type | Description |
| :---: | :-----------------: | :-----: | :-----------: | ----------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    |             |

\


## Events

### `Initialized`

The loan was initialized.

```solidity
    event Initialized(
        address borrower_,
        address[2] assets_,
        uint256[3] termDetails_,
        uint256[3] amounts_,
        uint256[4] rates_
    );
```

#### Parameters:

| Index |      Name      |     Type     | Internal Type | Description                                                                                           |
| :---: | :------------: | :----------: | :-----------: | ----------------------------------------------------------------------------------------------------- |
|   0   |   `borrower_`  |   `address`  |   `address`   | The address of the borrower.                                                                          |
|   1   |    `assets_`   | `address[2]` |  `address[2]` | Array of asset addresses. \[0]: collateralAsset, \[1]: fundsAsset.                                    |
|   2   | `termDetails_` | `uint256[3]` |  `uint256[3]` | Array of loan parameters: \[0]: gracePeriod, \[1]: paymentInterval, \[2]: payments,                   |
|   3   |   `amounts_`   | `uint256[3]` |  `uint256[3]` | Requested amounts: \[0]: collateralRequired, \[1]: principalRequested, \[2]: endingPrincipal.         |
|   4   |    `rates_`    | `uint256[4]` |  `uint256[4]` | Fee parameters: \[0]: interestRate, \[1]: earlyFeeRate, \[2]: lateFeeRate, \[3]: lateInterestPremium. |

\
