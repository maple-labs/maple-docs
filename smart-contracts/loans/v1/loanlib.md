# Loan Lib

LoanLib is a library of utility functions used by Loan.

\


## Functions

### `UNISWAP_ROUTER`

```solidity
    function UNISWAP_ROUTER()
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


### `canTriggerDefault`

Returns if a default can be triggered.

```solidity
    function canTriggerDefault(
        uint256 nextPaymentDue,
        uint256 defaultGracePeriod,
        address superFactory,
        uint256 balance,
        uint256 totalSupply
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                                                                          |
| :---: | :------------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------------------------- |
|   0   |   `nextPaymentDue`   | `uint256` |   `uint256`   | The unix timestamp of when payment is due.                                                           |
|   1   | `defaultGracePeriod` | `uint256` |   `uint256`   | The amount of time after the next payment is due that a Borrower has before a liquidation can occur. |
|   2   |    `superFactory`    | `address` |   `address`   | The factory that instantiated Loan.                                                                  |
|   3   |       `balance`      | `uint256` |   `uint256`   | The LoanFDT balance of account trying to trigger a default.                                          |
|   4   |     `totalSupply`    | `uint256` |   `uint256`   | The total supply of LoanFDT.                                                                         |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                         |
| :---: | :--: | :----: | :-----------: | ----------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether a default can be triggered. |

\


### `collateralRequiredForDrawdown`

Calculates collateral required to drawdown amount.

```solidity
    function collateralRequiredForDrawdown(
        IERC20Details collateralAsset,
        IERC20Details liquidityAsset,
        uint256 collateralRatio,
        address superFactory,
        uint256 amt
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index |        Name       |       Type      |       Internal Type      | Description                                                         |
| :---: | :---------------: | :-------------: | :----------------------: | ------------------------------------------------------------------- |
|   0   | `collateralAsset` | `IERC20Details` | `contract IERC20Details` | The IERC20 of the Collateral Asset.                                 |
|   1   |  `liquidityAsset` | `IERC20Details` | `contract IERC20Details` | The IERC20 of the Liquidity Asset.                                  |
|   2   | `collateralRatio` |    `uint256`    |         `uint256`        | The percentage of drawdown value that must be posted as collateral. |
|   3   |   `superFactory`  |    `address`    |         `address`        | The factory that instantiated Loan.                                 |
|   4   |       `amt`       |    `uint256`    |         `uint256`        | The drawdown amount.                                                |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                                                                    |
| :---: | :--: | :-------: | :-----------: | ---------------------------------------------------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount of Collateral Asset required to post in CollateralLocker for given drawdown amount. |

\


### `getFullPayment`

Returns information on full payment amount.

```solidity
    function getFullPayment(
        address repaymentCalc,
        uint256 nextPaymentDue,
        address lateFeeCalc,
        address premiumCalc
    )
        view
        returns (
            uint256 total,
            uint256 principal,
            uint256 interest
        );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   |  `repaymentCalc` | `address` |   `address`   | The address of RepaymentCalc.              |
|   1   | `nextPaymentDue` | `uint256` |   `uint256`   | The unix timestamp of when payment is due. |
|   2   |   `lateFeeCalc`  | `address` |   `address`   | The address of LateFeeCalc.                |
|   3   |   `premiumCalc`  | `address` |   `address`   | The address of PremiumCalc.                |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                                                          |
| :---: | :---------: | :-------: | :-----------: | -------------------------------------------------------------------- |
|   0   |   `total`   | `uint256` |   `uint256`   | The Principal + Interest for the full payment.                       |
|   1   | `principal` | `uint256` |   `uint256`   | The entitled principal amount needed to be paid in the full payment. |
|   2   |  `interest` | `uint256` |   `uint256`   | The entitled interest amount needed to be paid in the full payment.  |

\


### `getNextPayment`

Returns information on next payment amount.

```solidity
    function getNextPayment(
        address repaymentCalc,
        uint256 nextPaymentDue,
        address lateFeeCalc
    )
        view
        returns (
            uint256 total,
            uint256 principal,
            uint256 interest,
            uint256 _nextPaymentDue,
            bool paymentLate
        );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   |  `repaymentCalc` | `address` |   `address`   | The address of RepaymentCalc.              |
|   1   | `nextPaymentDue` | `uint256` |   `uint256`   | The unix timestamp of when payment is due. |
|   2   |   `lateFeeCalc`  | `address` |   `address`   | The address of LateFeeCalc.                |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                                                                                                                                    |
| :---: | :---------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------------------------- |
|   0   |      `total`      | `uint256` |   `uint256`   | The entitled total amount needed to be paid in the next payment (Principal + Interest only when the next payment is last payment of the Loan). |
|   1   |    `principal`    | `uint256` |   `uint256`   | The entitled principal amount needed to be paid in the next payment.                                                                           |
|   2   |     `interest`    | `uint256` |   `uint256`   | The entitled interest amount needed to be paid in the next payment.                                                                            |
|   3   | `_nextPaymentDue` | `uint256` |   `uint256`   | The payment due date.                                                                                                                          |
|   4   |   `paymentLate`   |   `bool`  |     `bool`    | Whether payment is late.                                                                                                                       |

\


### `loanSanityChecks`

Performs sanity checks on the data passed in Loan constructor.

```solidity
    function loanSanityChecks(
        IMapleGlobals globals,
        address liquidityAsset,
        address collateralAsset,
        uint256[5] specs
    )
        view;
```

#### Parameters:

| Index |        Name       |       Type      |       Internal Type      | Description                                   |
| :---: | :---------------: | :-------------: | :----------------------: | --------------------------------------------- |
|   0   |     `globals`     | `IMapleGlobals` | `contract IMapleGlobals` | The instance of a MapleGlobals.               |
|   1   |  `liquidityAsset` |    `address`    |         `address`        | The contract address of the Liquidity Asset.  |
|   2   | `collateralAsset` |    `address`    |         `address`        | The contract address of the Collateral Asset. |
|   3   |      `specs`      |   `uint256[5]`  |       `uint256[5]`       | The contains specifications for this Loan.    |

\
