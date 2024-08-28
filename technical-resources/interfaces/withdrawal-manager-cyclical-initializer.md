# WithdrawalManagerInitializer (Cyclical)

\


## Functions

### `cycleConfigs`

Gets the configuration for a given config id.

```solidity
    function cycleConfigs(
        uint256
    )
        view
        returns (
            uint64 initialCycleId,
            uint64 initialCycleTime,
            uint64 cycleDuration,
            uint64 windowDuration
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index |        Name        |   Type   | Internal Type | Description                                                        |
| :---: | :----------------: | :------: | :-----------: | ------------------------------------------------------------------ |
|   0   |  `initialCycleId`  | `uint64` |    `uint64`   | Identifier of the first withdrawal cycle using this configuration. |
|   1   | `initialCycleTime` | `uint64` |    `uint64`   | Timestamp of the first withdrawal cycle using this configuration.  |
|   2   |   `cycleDuration`  | `uint64` |    `uint64`   | Duration of the withdrawal cycle.                                  |
|   3   |  `windowDuration`  | `uint64` |    `uint64`   | Duration of the withdrawal window.                                 |

\


### `decodeArguments`

```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address pool_,
            uint256 startTime_,
            uint256 cycleDuration_,
            uint256 windowDuration_
        );
```

#### Parameters:

| Index |         Name        |   Type  | Internal Type | Description |
| :---: | :-----------------: | :-----: | :-----------: | ----------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    |             |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   |      `pool_`      | `address` |   `address`   |             |
|   1   |    `startTime_`   | `uint256` |   `uint256`   |             |
|   2   |  `cycleDuration_` | `uint256` |   `uint256`   |             |
|   3   | `windowDuration_` | `uint256` |   `uint256`   |             |

\


### `encodeArguments`

```solidity
    function encodeArguments(
        address pool_,
        uint256 startTime_,
        uint256 cycleDuration_,
        uint256 windowDuration_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   |      `pool_`      | `address` |   `address`   |             |
|   1   |    `startTime_`   | `uint256` |   `uint256`   |             |
|   2   |  `cycleDuration_` | `uint256` |   `uint256`   |             |
|   3   | `windowDuration_` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index |         Name        |   Type  | Internal Type | Description |
| :---: | :-----------------: | :-----: | :-----------: | ----------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    |             |

\


### `exitCycleId`

Gets the id of the cycle that account can exit on.

```solidity
    function exitCycleId(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `latestConfigId`

Gets the most recent configuration id.

```solidity
    function latestConfigId()
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


### `lockedShares`

Gets the amount of locked shares for an account.

```solidity
    function lockedShares(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `pool`

Gets the address of the pool associated with this withdrawal manager.

```solidity
    function pool()
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


### `poolManager`

Gets the address of the pool manager associated with this withdrawal manager.

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


### `totalCycleShares`

Gets the amount of shares for a cycle.

```solidity
    function totalCycleShares(
        uint256
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


## Events

### `ConfigurationUpdated`

Emitted when the withdrawal configuration is updated.

```solidity
    event ConfigurationUpdated(
        uint256 configId_,
        uint64 initialCycleId_,
        uint64 initialCycleTime_,
        uint64 cycleDuration_,
        uint64 windowDuration_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                                                                                 |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------------------------------------------------------------- |
|   0   |     `configId_`     | `uint256` |   `uint256`   | The identifier of the configuration.                                                        |
|   1   |  `initialCycleId_`  |  `uint64` |    `uint64`   | The identifier of the withdrawal cycle when the configuration takes effect.                 |
|   2   | `initialCycleTime_` |  `uint64` |    `uint64`   | The timestamp of the beginning of the withdrawal cycle when the configuration takes effect. |
|   3   |   `cycleDuration_`  |  `uint64` |    `uint64`   | The new duration of the withdrawal cycle.                                                   |
|   4   |  `windowDuration_`  |  `uint64` |    `uint64`   | The new duration of the withdrawal window.                                                  |

\


### `Initialized`

```solidity
    event Initialized(
        address pool_,
        uint256 cycleDuration_,
        uint256 windowDuration_
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   |      `pool_`      | `address` |   `address`   |             |
|   1   |  `cycleDuration_` | `uint256` |   `uint256`   |             |
|   2   | `windowDuration_` | `uint256` |   `uint256`   |             |

\


### `WithdrawalCancelled`

Emitted when a withdrawal request is cancelled.

```solidity
    event WithdrawalCancelled(
        address account_
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                                         |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------------------------- |
|   0   | `account_` | `address` |   `address`   | Address of the account whose withdrawal request has been cancelled. |

\


### `WithdrawalProcessed`

Emitted when a withdrawal request is processed.

```solidity
    event WithdrawalProcessed(
        address account_,
        uint256 sharesToRedeem_,
        uint256 assetsToWithdraw_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                                                 |
| :---: | :-----------------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   |      `account_`     | `address` |   `address`   | Address of the account processing their withdrawal request. |
|   1   |  `sharesToRedeem_`  | `uint256` |   `uint256`   | Amount of shares that the account will redeem.              |
|   2   | `assetsToWithdraw_` | `uint256` |   `uint256`   | Amount of assets that will be withdrawn from the pool.      |

\


### `WithdrawalUpdated`

Emitted when a withdrawal request is updated.

```solidity
    event WithdrawalUpdated(
        address account_,
        uint256 lockedShares_,
        uint64 windowStart_,
        uint64 windowEnd_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                                                            |
| :---: | :-------------: | :-------: | :-----------: | ---------------------------------------------------------------------- |
|   0   |    `account_`   | `address` |   `address`   | Address of the account whose request has been updated.                 |
|   1   | `lockedShares_` | `uint256` |   `uint256`   | Total amount of shares the account has locked.                         |
|   2   |  `windowStart_` |  `uint64` |    `uint64`   | Time when the withdrawal window for the withdrawal request will begin. |
|   3   |   `windowEnd_`  |  `uint64` |    `uint64`   | Time when the withdrawal window for the withdrawal request will end.   |

\
