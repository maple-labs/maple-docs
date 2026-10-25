# StrategyDeployer



## Constructor

```solidity
    constructor(
        address globals_
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `globals_` | `address` |   `address`   |             |



## Functions

### `deploy`

Deploys a strategy manager and underlying strategy.

```solidity
    function deploy(
        address strategyManagerFactory,
        address strategyFactory,
        uint256 strategyLiquidityCap,
        bytes strategyDeploymentData,
        bytes bootstrapFundingData
    )
        nonpayable
        returns (
            address strategyManager,
            address underlyingStrategy
        );
```

#### Parameters:

| Index |           Name           |    Type   | Internal Type | Description                                                                                                                        |
| :---: | :----------------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------------- |
|   0   | `strategyManagerFactory` | `address` |   `address`   | Address of the strategy manager factory.                                                                                           |
|   1   |     `strategyFactory`    | `address` |   `address`   | Address of the underlying strategy factory.                                                                                        |
|   2   |  `strategyLiquidityCap`  | `uint256` |   `uint256`   | Maximum total asset position the strategy manager can hold. A value of zero is left unset and can be configured later by an admin. |
|   3   | `strategyDeploymentData` |  `bytes`  |    `bytes`    | Strategy initialization data.                                                                                                      |
|   4   |  `bootstrapFundingData`  |  `bytes`  |    `bytes`    | Data forwarded to the underlying strategy when funding the bootstrap assets.                                                       |

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                                  |
| :---: | :------------------: | :-------: | :-----------: | -------------------------------------------- |
|   0   |   `strategyManager`  | `address` |   `address`   | Address of the deployed strategy manager.    |
|   1   | `underlyingStrategy` | `address` |   `address`   | Address of the deployed underlying strategy. |



### `getDeploymentAddresses`

Returns the addresses that would result from a deployment.

```solidity
    function getDeploymentAddresses(
        address strategyDelegate,
        address strategyManagerFactory,
        address strategyFactory,
        bytes strategyDeploymentData
    )
        view
        returns (
            address strategyManager,
            address underlyingStrategy
        );
```

#### Parameters:

| Index |           Name           |    Type   | Internal Type | Description                                 |
| :---: | :----------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |    `strategyDelegate`    | `address` |   `address`   | Address of the strategy delegate.           |
|   1   | `strategyManagerFactory` | `address` |   `address`   | Address of the strategy manager factory.    |
|   2   |     `strategyFactory`    | `address` |   `address`   | Address of the underlying strategy factory. |
|   3   | `strategyDeploymentData` |  `bytes`  |    `bytes`    | Strategy initialization data.               |

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                                               |
| :---: | :------------------: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   |   `strategyManager`  | `address` |   `address`   | Address of the strategy manager that will be deployed.    |
|   1   | `underlyingStrategy` | `address` |   `address`   | Address of the underlying strategy that will be deployed. |



### `globals`

Returns the address of the Maple globals contract.

```solidity
    function globals()
        view
        returns (
            address globals
        );
```

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                          |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `globals` | `address` |   `address`   | The address of the globals contract. |



## Events

### `StrategyManagerDeployed`

Emitted when a new strategy manager and its underlying strategy are deployed.

```solidity
    event StrategyManagerDeployed(
        address indexed strategyDelegate,
        address indexed strategyManager,
        address indexed underlyingStrategy
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                  |
| :---: | :------------------: | :-------: | :-----------: | -------------------------------------------- |
|   0   |  `strategyDelegate`  | `address` |   `address`   | Address of the strategy delegate.            |
|   1   |   `strategyManager`  | `address` |   `address`   | Address of the deployed strategy manager.    |
|   2   | `underlyingStrategy` | `address` |   `address`   | Address of the deployed underlying strategy. |

