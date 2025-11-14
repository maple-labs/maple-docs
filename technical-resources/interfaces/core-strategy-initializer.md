# Core Strategy Initializer

Initializer for the Core Strategy proxy. Validates the pool manager and strategy vault against Globals and factory instances, ensures asset consistency, sets approvals, and emits the initialization event.

## Functions

### `decodeArguments`

Decodes initializer arguments (factory fallback calldata) into parameters.

```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address poolManager_,
            address strategyVault_
        );
```

#### Parameters:

| Index |        Name        |  Type  | Internal Type | Description                            |
| :---: | :----------------: | :----: | :-----------: | -------------------------------------- |
|   0   | `encodedArguments_`| `bytes`|    `bytes`    | ABI-encoded `(poolManager, strategyVault)` |

#### Return Values:

| Index |      Name       |  Type   | Internal Type | Description                  |
| :---: | :-------------: | :-----: | :-----------: | ---------------------------- |
|   0   | `poolManager_`  | `address`|   `address`  | Pool Manager address         |
|   1   | `strategyVault_`| `address`|   `address`  | Strategy vault (ERC-4626)    |



### `encodeArguments`

Encodes initializer arguments for deployment.

```solidity
    function encodeArguments(
        address poolManager_,
        address strategyVault_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:

| Index |      Name       |  Type   | Internal Type | Description               |
| :---: | :-------------: | :-----: | :-----------: | ------------------------- |
|   0   | `poolManager_`  | `address`|   `address`  | Pool Manager address      |
|   1   | `strategyVault_`| `address`|   `address`  | Strategy vault (ERC-4626) |

#### Return Values:

| Index |       Name        |  Type  | Internal Type | Description                                  |
| :---: | :---------------: | :----: | :-----------: | -------------------------------------------- |
|   0   | `encodedArguments_`| `bytes`|    `bytes`    | ABI-encoded initializer calldata payload      |

## Events

```solidity
    event Initialized(
        address pool_,
        address poolManager_,
        address strategyVault_
    );
```
