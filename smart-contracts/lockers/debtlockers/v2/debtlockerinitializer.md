# Debt Locker Initializer

DebtLockerInitializer is intended to initialize the storage of a DebtLocker proxy.

\


## Functions

### `decodeArguments`

```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address loan_,
            address pool_
        );
```

#### Parameters:

| Index |         Name        |   Type  | Internal Type | Description |
| :---: | :-----------------: | :-----: | :-----------: | ----------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    |             |

#### Return Values:

| Index |   Name  |    Type   | Internal Type | Description |
| :---: | :-----: | :-------: | :-----------: | ----------- |
|   0   | `loan_` | `address` |   `address`   |             |
|   1   | `pool_` | `address` |   `address`   |             |

\


### `encodeArguments`

```solidity
    function encodeArguments(
        address loan_,
        address pool_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description |
| :---: | :-----: | :-------: | :-----------: | ----------- |
|   0   | `loan_` | `address` |   `address`   |             |
|   1   | `pool_` | `address` |   `address`   |             |

#### Return Values:

| Index |         Name        |   Type  | Internal Type | Description |
| :---: | :-----------------: | :-----: | :-----------: | ----------- |
|   0   | `encodedArguments_` | `bytes` |    `bytes`    |             |

\
