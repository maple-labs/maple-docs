# PoolDeployer



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

### `deployPool`

Deploys a pool along with its dependencies and atomically completes configuration. NOTE: The PoolManager address is encoded and prepended to the strategyDeploymentData.

```solidity
    function deployPool(
        address poolManagerFactory,
        address withdrawalManagerFactory,
        PoolManagerInitParams poolManagerInitParams,
        PoolConfigParams poolConfigParams,
        StrategyDeployParams[] strategiesParams,
        StrategyManagerParams[] strategyManagersParams
    )
        nonpayable
        returns (
            address poolManager
        );
```

#### Parameters:

| Index |            Name            |    Type   |           Internal Type          | Description                                                                          |
| :---: | :------------------------: | :-------: | :------------------------------: | ------------------------------------------------------------------------------------ |
|   0   |    `poolManagerFactory`    | `address` |             `address`            | The address of the PoolManager factory to use.                                       |
|   1   | `withdrawalManagerFactory` | `address` |             `address`            | The address of the queue WithdrawalManager factory to use.                           |
|   2   |   `poolManagerInitParams`  |  `tuple`  |  `struct PoolManagerInitParams`  | Initial parameters for the PoolManager (asset, name, symbol, initialSupply).         |
|   3   |     `poolConfigParams`     |  `tuple`  |     `struct PoolConfigParams`    | Pool configuration (poolPermissionManager, liquidityCap, delegateManagementFeeRate). |
|   4   |     `strategiesParams`     | `tuple[]` |  `struct StrategyDeployParams[]` | Strategies to deploy and register on the PoolManager (with optional caps).           |
|   5   |  `strategyManagersParams`  | `tuple[]` | `struct StrategyManagerParams[]` | Pre-deployed StrategyManagers to register on the PoolManager (with optional caps).   |

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                              |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | The address of the deployed PoolManager. |



### `getPoolDeploymentAddresses`

Gets the addresses that would result from a deployment.

```solidity
    function getPoolDeploymentAddresses(
        address poolManagerFactory,
        address poolDelegate,
        address asset,
        uint256 initialSupply,
        string name,
        string symbol
    )
        view
        returns (
            address poolManager,
            address pool
        );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                                |
| :---: | :------------------: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   | `poolManagerFactory` | `address` |   `address`   | The address of the PoolManager factory to use.             |
|   1   |    `poolDelegate`    | `address` |   `address`   | The address of the PoolDelegate that will deploy the Pool. |
|   2   |        `asset`       | `address` |   `address`   | The address of the asset to use.                           |
|   3   |    `initialSupply`   | `uint256` |   `uint256`   | The initial supply of the Pool.                            |
|   4   |        `name`        |  `string` |    `string`   | The name of the Pool.                                      |
|   5   |       `symbol`       |  `string` |    `string`   | The symbol of the Pool.                                    |

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                                                    |
| :---: | :-----------: | :-------: | :-----------: | -------------------------------------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | The address of the PoolManager contract that will be deployed. |
|   1   |     `pool`    | `address` |   `address`   | The address of the Pool contract that will be deployed.        |



### `getQueueWithdrawalManagerAddress`

Gets the address of the Queue Withdrawal Manager that would result from a deployment.

```solidity
    function getQueueWithdrawalManagerAddress(
        address withdrawalManagerFactory,
        address pool,
        address poolManager
    )
        view
        returns (
            address withdrawalManager
        );
```

#### Parameters:

| Index |            Name            |    Type   | Internal Type | Description                                          |
| :---: | :------------------------: | :-------: | :-----------: | ---------------------------------------------------- |
|   0   | `withdrawalManagerFactory` | `address` |   `address`   | The address of the WithdrawalManager factory to use. |
|   1   |           `pool`           | `address` |   `address`   | The address of the Pool to use.                      |
|   2   |        `poolManager`       | `address` |   `address`   | The address of the PoolManager to use.               |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description                                                          |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------------------------------------- |
|   0   | `withdrawalManager` | `address` |   `address`   | The address of the WithdrawalManager contract that will be deployed. |



### `getStrategiesAddresses`

Gets the addresses of the Strategies that would result from a deployment.

```solidity
    function getStrategiesAddresses(
        address poolManager,
        address[] strategyFactories,
        bytes[] strategyDeploymentData,
        bytes32[] strategySalts
    )
        view
        returns (
            address[] strategies
        );
```

#### Parameters:

| Index |           Name           |     Type    | Internal Type | Description                                                   |
| :---: | :----------------------: | :---------: | :-----------: | ------------------------------------------------------------- |
|   0   |       `poolManager`      |  `address`  |   `address`   | The address of the PoolManager to use.                        |
|   1   |    `strategyFactories`   | `address[]` |  `address[]`  | An array of Strategy factories to use.                        |
|   2   | `strategyDeploymentData` |  `bytes[]`  |   `bytes[]`   | An array of bytes to use to construct the strategies.         |
|   3   |      `strategySalts`     | `bytes32[]` |  `bytes32[]`  | An array of salts used as the CREATE2 salt for each strategy. |

#### Return Values:

| Index |     Name     |     Type    | Internal Type | Description                                                    |
| :---: | :----------: | :---------: | :-----------: | -------------------------------------------------------------- |
|   0   | `strategies` | `address[]` |  `address[]`  | The addresses of the Strategy contracts that will be deployed. |



### `globals`

Gets the address of the Globals contract.

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
|   0   | `globals` | `address` |   `address`   | The address of the Globals contract. |



## Events

### `PoolDeployed`

Emitted when a new pool is deployed.

```solidity
    event PoolDeployed(
        address indexed pool,
        address indexed poolManager,
        address indexed withdrawalManager,
        address[] strategies,
        address[] strategyManagers
    );
```

#### Parameters:

| Index |         Name        |     Type    | Internal Type | Description                                                             |
| :---: | :-----------------: | :---------: | :-----------: | ----------------------------------------------------------------------- |
|   0   |        `pool`       |  `address`  |   `address`   | The address of the Pool deployed.                                       |
|   1   |    `poolManager`    |  `address`  |   `address`   | The address of the PoolManager deployed.                                |
|   2   | `withdrawalManager` |  `address`  |   `address`   | The address of the queue WithdrawalManager deployed.                    |
|   3   |     `strategies`    | `address[]` |  `address[]`  | Addresses of the Strategies deployed and registered on the PoolManager. |
|   4   |  `strategyManagers` | `address[]` |  `address[]`  | Addresses of the StrategyManagers registered on the PoolManager.        |



## Structs

### `PoolManagerInitParams`

```solidity
    struct PoolManagerInitParams {
        address asset;
        uint256 initialSupply;
        string name;
        string symbol;
    }
```

#### Members:

| Index |       Name      |    Type   | Internal Type | Description |
| :---: | :-------------: | :-------: | :-----------: | ----------- |
|   0   |     `asset`     | `address` |   `address`   |             |
|   1   | `initialSupply` | `uint256` |   `uint256`   |             |
|   2   |      `name`     |  `string` |    `string`   |             |
|   3   |     `symbol`    |  `string` |    `string`   |             |



### `PoolConfigParams`

```solidity
    struct PoolConfigParams {
        address poolPermissionManager;
        uint256 delegateManagementFeeRate;
        uint256 liquidityCap;
    }
```

#### Members:

| Index |             Name            |    Type   | Internal Type | Description |
| :---: | :-------------------------: | :-------: | :-----------: | ----------- |
|   0   |   `poolPermissionManager`   | `address` |   `address`   |             |
|   1   | `delegateManagementFeeRate` | `uint256` |   `uint256`   |             |
|   2   |        `liquidityCap`       | `uint256` |   `uint256`   |             |



### `StrategyDeployParams`

```solidity
    struct StrategyDeployParams {
        address factory;
        uint256 cap;
        bytes32 salt;
        bytes deploymentData;
    }
```

#### Members:

| Index |       Name       |    Type   | Internal Type | Description |
| :---: | :--------------: | :-------: | :-----------: | ----------- |
|   0   |     `factory`    | `address` |   `address`   |             |
|   1   |       `cap`      | `uint256` |   `uint256`   |             |
|   2   |      `salt`      | `bytes32` |   `bytes32`   |             |
|   3   | `deploymentData` |  `bytes`  |    `bytes`    |             |



### `StrategyManagerParams`

```solidity
    struct StrategyManagerParams {
        address instance;
        uint256 cap;
    }
```

#### Members:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `instance` | `address` |   `address`   |             |
|   1   |    `cap`   | `uint256` |   `uint256`   |             |

