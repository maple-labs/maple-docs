# MaplePoolDeployer



<br />

## Constructor




```solidity
    constructor(
        address globals_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `globals_` | `address` | `address` |  |


<br />


## Functions

### `deployPool` 

Deploys a pool along with its dependencies.         NOTE: The PoolManager address is encoded and prepended to the strategyDeploymentData.

```solidity
    function deployPool(
        address poolManagerFactory_,
        address withdrawalManagerFactory_,
        address[] strategyFactories_,
        bytes[] strategyDeploymentData_,
        address asset_,
        address poolPermissionManager_,
        string name_,
        string symbol_,
        uint256[7] configParams_
    )
        nonpayable
        returns (
            address poolManager_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManagerFactory_` | `address` | `address` | The address of the PoolManager factory to use. |
| 1 | `withdrawalManagerFactory_` | `address` | `address` | The address of the WithdrawalManager factory to use. |
| 2 | `strategyFactories_` | `address[]` | `address[]` | An array of Strategy factories to use. |
| 3 | `strategyDeploymentData_` | `bytes[]` | `bytes[]` | An array of bytes to use to construct the strategies. |
| 4 | `asset_` | `address` | `address` | The address of the asset to use. |
| 5 | `poolPermissionManager_` | `address` | `address` | The address of the PoolPermissionManager to use. |
| 6 | `name_` | `string` | `string` | The name of the Pool. |
| 7 | `symbol_` | `string` | `string` | The symbol of the Pool. |
| 8 | `configParams_` | `uint256[7]` | `uint256[7]` | Array of uint256 config parameters. Array used to avoid stack too deep issues.                                    [0]: liquidityCap                                    [1]: delegateManagementFeeRate                                    [2]: coverAmountRequired                                    [3]: initialSupply |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the PoolManager. |


<br />

### `deployPool` 

Deploys a pool along with its dependencies.         NOTE: The PoolManager address is encoded and prepended to the strategyDeploymentData.

```solidity
    function deployPool(
        address poolManagerFactory_,
        address withdrawalManagerFactory_,
        address[] strategyFactories_,
        bytes[] strategyDeploymentData_,
        address asset_,
        address poolPermissionManager_,
        string name_,
        string symbol_,
        uint256[4] configParams_
    )
        nonpayable
        returns (
            address poolManager_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManagerFactory_` | `address` | `address` | The address of the PoolManager factory to use. |
| 1 | `withdrawalManagerFactory_` | `address` | `address` | The address of the WithdrawalManager factory to use. |
| 2 | `strategyFactories_` | `address[]` | `address[]` | An array of Strategy factories to use. |
| 3 | `strategyDeploymentData_` | `bytes[]` | `bytes[]` | An array of bytes to use to construct the strategies. |
| 4 | `asset_` | `address` | `address` | The address of the asset to use. |
| 5 | `poolPermissionManager_` | `address` | `address` | The address of the PoolPermissionManager to use. |
| 6 | `name_` | `string` | `string` | The name of the Pool. |
| 7 | `symbol_` | `string` | `string` | The symbol of the Pool. |
| 8 | `configParams_` | `uint256[4]` | `uint256[4]` | Array of uint256 config parameters. Array used to avoid stack too deep issues.                                    [0]: liquidityCap                                    [1]: delegateManagementFeeRate                                    [2]: coverAmountRequired                                    [3]: initialSupply |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the PoolManager. |


<br />

### `getCyclicalWithdrawalManagerAddress` 

Gets the address of the Cyclical Withdrawal Manager that would result from a deployment.

```solidity
    function getCyclicalWithdrawalManagerAddress(
        address withdrawalManagerFactory_,
        address pool_,
        address poolManager_,
        uint256 startTime_,
        uint256 cycleDuration_,
        uint256 windowDuration_
    )
        view
        returns (
            address withdrawalManager_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `withdrawalManagerFactory_` | `address` | `address` | The address of the WithdrawalManager factory to use. |
| 1 | `pool_` | `address` | `address` | The address of the Pool to use. |
| 2 | `poolManager_` | `address` | `address` | The address of the PoolManager to use. |
| 3 | `startTime_` | `uint256` | `uint256` | The start time of the WithdrawalManager. |
| 4 | `cycleDuration_` | `uint256` | `uint256` | The cycle duration of the WithdrawalManager. |
| 5 | `windowDuration_` | `uint256` | `uint256` | The window duration of the WithdrawalManager. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `withdrawalManager_` | `address` | `address` |        The address of the WithdrawalManager contract that will be deployed. |


<br />

### `getPoolDeploymentAddresses` 

Gets the addresses that would result from a deployment.

```solidity
    function getPoolDeploymentAddresses(
        address poolManagerFactory_,
        address poolDelegate_,
        address asset_,
        uint256 initialSupply_,
        string name_,
        string symbol_
    )
        view
        returns (
            address poolManager_,
            address pool_,
            address poolDelegateCover_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManagerFactory_` | `address` | `address` | The address of the PoolManager factory to use. |
| 1 | `poolDelegate_` | `address` | `address` | The address of the PoolDelegate that will deploy the Pool. |
| 2 | `asset_` | `address` | `address` | The address of the asset to use. |
| 3 | `initialSupply_` | `uint256` | `uint256` | The initial supply of the Pool. |
| 4 | `name_` | `string` | `string` | The name of the Pool. |
| 5 | `symbol_` | `string` | `string` | The symbol of the Pool. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |        The address of the PoolManager contract that will be deployed. |
| 1 | `pool_` | `address` | `address` |               The address of the Pool contract that will be deployed. |
| 2 | `poolDelegateCover_` | `address` | `address` |  The address of the PoolDelegateCover contract that will be deployed. |


<br />

### `getQueueWithdrawalManagerAddress` 

Gets the address of the Queue Withdrawal Manager that would result from a deployment.

```solidity
    function getQueueWithdrawalManagerAddress(
        address withdrawalManagerFactory_,
        address pool_,
        address poolManager_
    )
        view
        returns (
            address withdrawalManager_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `withdrawalManagerFactory_` | `address` | `address` | The address of the WithdrawalManager factory to use. |
| 1 | `pool_` | `address` | `address` | The address of the Pool to use. |
| 2 | `poolManager_` | `address` | `address` | The address of the PoolManager to use. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `withdrawalManager_` | `address` | `address` |        The address of the WithdrawalManager contract that will be deployed. |


<br />

### `getStrategiesAddresses` 

Gets the addresses of the Strategies that would result from a deployment.

```solidity
    function getStrategiesAddresses(
        address poolManager_,
        address[] strategyFactories_,
        bytes[] strategyDeploymentData_
    )
        view
        returns (
            address[] strategies_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the PoolManager to use. |
| 1 | `strategyFactories_` | `address[]` | `address[]` | An array of Strategy factories to use. |
| 2 | `strategyDeploymentData_` | `bytes[]` | `bytes[]` | An array of bytes to use to construct the strategies. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `strategies_` | `address[]` | `address[]` |             The addresses of the Strategy contracts that will be deployed. |


<br />

### `globals` 

Gets the address of the Globals contract.

```solidity
    function globals()
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


## Events

### `PoolDeployed`

Emitted when a new pool is deployed.

```solidity
    event PoolDeployed(
        address pool_,
        address poolManager_,
        address withdrawalManager_,
        address[] strategies_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool_` | `address` | `address` | The address of the Pool deployed. |
| 1 | `poolManager_` | `address` | `address` | The address of the PoolManager deployed. |
| 2 | `withdrawalManager_` | `address` | `address` | The address of the WithdrawalManager deployed. |
| 3 | `strategies_` | `address[]` | `address[]` | An array of the addresses of the Strategies deployed. |

<br />

