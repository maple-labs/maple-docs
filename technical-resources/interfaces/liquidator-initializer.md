# LiquidatorInitializer

\


## Functions

### `collateralAsset`

Returns the address of the collateral asset.

```solidity
    function collateralAsset()
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


### `collateralRemaining`

Returns the amount of collateral yet to be liquidated.

```solidity
    function collateralRemaining()
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


### `decodeArguments`

```solidity
    function decodeArguments(
        bytes calldata_
    )
        pure
        returns (
            address loanManager_,
            address collateralAsset_,
            address fundsAsset_
        );
```

#### Parameters:

| Index |     Name    |   Type  | Internal Type | Description |
| :---: | :---------: | :-----: | :-----------: | ----------- |
|   0   | `calldata_` | `bytes` |    `bytes`    |             |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description |
| :---: | :----------------: | :-------: | :-----------: | ----------- |
|   0   |   `loanManager_`   | `address` |   `address`   |             |
|   1   | `collateralAsset_` | `address` |   `address`   |             |
|   2   |    `fundsAsset_`   | `address` |   `address`   |             |

\


### `encodeArguments`

```solidity
    function encodeArguments(
        address loanManager_,
        address collateralAsset_,
        address fundsAsset_
    )
        pure
        returns (
            bytes calldata_
        );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description |
| :---: | :----------------: | :-------: | :-----------: | ----------- |
|   0   |   `loanManager_`   | `address` |   `address`   |             |
|   1   | `collateralAsset_` | `address` |   `address`   |             |
|   2   |    `fundsAsset_`   | `address` |   `address`   |             |

#### Return Values:

| Index |     Name    |   Type  | Internal Type | Description |
| :---: | :---------: | :-----: | :-----------: | ----------- |
|   0   | `calldata_` | `bytes` |    `bytes`    |             |

\


### `fundsAsset`

Returns the address of the funding asset.

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


### `loanManager`

Returns the address of the loan manager contract.

```solidity
    function loanManager()
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
