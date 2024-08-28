# OpenTermLoanManagerInitializer

\


## Functions

### `accountedInterest`

```solidity
    function accountedInterest()
        view
        returns (
            uint112
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint112` |   `uint112`   |             |

\


### `decodeArguments`

```solidity
    function decodeArguments(
        bytes calldata_
    )
        pure
        returns (
            address poolManager_
        );
```

#### Parameters:

| Index |     Name    |   Type  | Internal Type | Description |
| :---: | :---------: | :-----: | :-----------: | ----------- |
|   0   | `calldata_` | `bytes` |    `bytes`    |             |

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description |
| :---: | :------------: | :-------: | :-----------: | ----------- |
|   0   | `poolManager_` | `address` |   `address`   |             |

\


### `domainStart`

```solidity
    function domainStart()
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


### `encodeArguments`

```solidity
    function encodeArguments(
        address poolManager_
    )
        pure
        returns (
            bytes calldata_
        );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description |
| :---: | :------------: | :-------: | :-----------: | ----------- |
|   0   | `poolManager_` | `address` |   `address`   |             |

#### Return Values:

| Index |     Name    |   Type  | Internal Type | Description |
| :---: | :---------: | :-----: | :-----------: | ----------- |
|   0   | `calldata_` | `bytes` |    `bytes`    |             |

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


### `impairmentFor`

```solidity
    function impairmentFor(
        address
    )
        view
        returns (
            uint40 impairedDate,
            bool impairedByGovernor
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index |         Name         |   Type   | Internal Type | Description |
| :---: | :------------------: | :------: | :-----------: | ----------- |
|   0   |    `impairedDate`    | `uint40` |    `uint40`   |             |
|   1   | `impairedByGovernor` |  `bool`  |     `bool`    |             |

\


### `issuanceRate`

```solidity
    function issuanceRate()
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


### `paymentFor`

```solidity
    function paymentFor(
        address
    )
        view
        returns (
            uint24 platformManagementFeeRate,
            uint24 delegateManagementFeeRate,
            uint40 startDate,
            uint168 issuanceRate
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index |             Name            |    Type   | Internal Type | Description |
| :---: | :-------------------------: | :-------: | :-----------: | ----------- |
|   0   | `platformManagementFeeRate` |  `uint24` |    `uint24`   |             |
|   1   | `delegateManagementFeeRate` |  `uint24` |    `uint24`   |             |
|   2   |         `startDate`         |  `uint40` |    `uint40`   |             |
|   3   |        `issuanceRate`       | `uint168` |   `uint168`   |             |

\


### `poolManager`

```solidity
    function poolManager()
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


### `principalOut`

```solidity
    function principalOut()
        view
        returns (
            uint128
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint128` |   `uint128`   |             |

\


### `unrealizedLosses`

```solidity
    function unrealizedLosses()
        view
        returns (
            uint128
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint128` |   `uint128`   |             |

\


## Events

### `Initialized`

```solidity
    event Initialized(
        address poolManager_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description |
| :---: | :------------: | :-------: | :-----------: | ----------- |
|   0   | `poolManager_` | `address` |   `address`   |             |

\
