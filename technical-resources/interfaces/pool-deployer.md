# Maple Pool Deployer



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

Deploys a pool along with its dependencies.

```solidity
    function deployPool(
        address poolManagerFactory_,
        address withdrawalManagerFactory_,
        address[] loanManagerFactories_,
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
| 2 | `loanManagerFactories_` | `address[]` | `address[]` | An array of LoanManager factories to use. |
| 3 | `asset_` | `address` | `address` | The address of the asset to use. |
| 4 | `poolPermissionManager_` | `address` | `address` | The address of the PoolPermissionManager to use. |
| 5 | `name_` | `string` | `string` | The name of the Pool. |
| 6 | `symbol_` | `string` | `string` | The symbol of the Pool. |
| 7 | `configParams_` | `uint256[4]` | `uint256[4]` | Array of uint256 config parameters. Array used to avoid stack too deep issues.                                    [0]: liquidityCap                                    [1]: delegateManagementFeeRate                                    [2]: coverAmountRequired                                    [3]: initialSupply |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the PoolManager. |


<br />

### `deployPool`

Deploys a pool along with its dependencies.

```solidity
    function deployPool(
        address poolManagerFactory_,
        address withdrawalManagerFactory_,
        address[] loanManagerFactories_,
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
| 2 | `loanManagerFactories_` | `address[]` | `address[]` | An array of LoanManager factories to use. |
| 3 | `asset_` | `address` | `address` | The address of the asset to use. |
| 4 | `poolPermissionManager_` | `address` | `address` | The address of the PoolPermissionManager to use. |
| 5 | `name_` | `string` | `string` | The name of the Pool. |
| 6 | `symbol_` | `string` | `string` | The symbol of the Pool. |
| 7 | `configParams_` | `uint256[7]` | `uint256[7]` | Array of uint256 config parameters. Array used to avoid stack too deep issues.                                    [0]: liquidityCap                                    [1]: delegateManagementFeeRate                                    [2]: coverAmountRequired                                    [3]: initialSupply |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the PoolManager. |


<br />

### `getDeploymentAddresses`

Gets the addresses that would result from a deployment.

```solidity
    function getDeploymentAddresses(
        address poolDelegate_,
        address poolManagerFactory_,
        address withdrawalManagerFactory_,
        address[] loanManagerFactories_,
        address asset_,
        string name_,
        string symbol_,
        uint256[7] configParams_
    )
        view
        returns (
            address poolManager_,
            address pool_,
            address poolDelegateCover_,
            address withdrawalManager_,
            address[] loanManagers_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate_` | `address` | `address` | The address of the PoolDelegate that will deploy the Pool. |
| 1 | `poolManagerFactory_` | `address` | `address` | The address of the PoolManager factory to use. |
| 2 | `withdrawalManagerFactory_` | `address` | `address` | The address of the WithdrawalManager factory to use. |
| 3 | `loanManagerFactories_` | `address[]` | `address[]` | An array of LoanManager factories to use. |
| 4 | `asset_` | `address` | `address` | The address of the asset to use. |
| 5 | `name_` | `string` | `string` | The name of the Pool. |
| 6 | `symbol_` | `string` | `string` | The symbol of the Pool. |
| 7 | `configParams_` | `uint256[7]` | `uint256[7]` | Array of uint256 config parameters. Array used to avoid stack too deep issues.                                    [0]: liquidityCap                                    [1]: delegateManagementFeeRate                                    [2]: coverAmountRequired                                    [3]: initialSupply |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |       The address of the PoolManager contract that will be deployed. |
| 1 | `pool_` | `address` | `address` |              The address of the Pool contract that will be deployed. |
| 2 | `poolDelegateCover_` | `address` | `address` | The address of the PoolDelegateCover contract that will be deployed. |
| 3 | `withdrawalManager_` | `address` | `address` | The address of the WithdrawalManager contract that will be deployed. |
| 4 | `loanManagers_` | `address[]` | `address[]` |      The address of the LoanManager contracts that will be deployed. |


<br />

### `getDeploymentAddresses`

Gets the addresses that would result from a deployment.

```solidity
    function getDeploymentAddresses(
        address poolDelegate_,
        address poolManagerFactory_,
        address withdrawalManagerFactory_,
        address[] loanManagerFactories_,
        address asset_,
        string name_,
        string symbol_,
        uint256[4] configParams_
    )
        view
        returns (
            address poolManager_,
            address pool_,
            address poolDelegateCover_,
            address withdrawalManager_,
            address[] loanManagers_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate_` | `address` | `address` | The address of the PoolDelegate that will deploy the Pool. |
| 1 | `poolManagerFactory_` | `address` | `address` | The address of the PoolManager factory to use. |
| 2 | `withdrawalManagerFactory_` | `address` | `address` | The address of the WithdrawalManager factory to use. |
| 3 | `loanManagerFactories_` | `address[]` | `address[]` | An array of LoanManager factories to use. |
| 4 | `asset_` | `address` | `address` | The address of the asset to use. |
| 5 | `name_` | `string` | `string` | The name of the Pool. |
| 6 | `symbol_` | `string` | `string` | The symbol of the Pool. |
| 7 | `configParams_` | `uint256[4]` | `uint256[4]` | Array of uint256 config parameters. Array used to avoid stack too deep issues.                                    [0]: liquidityCap                                    [1]: delegateManagementFeeRate                                    [2]: coverAmountRequired                                    [3]: initialSupply |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |       The address of the PoolManager contract that will be deployed. |
| 1 | `pool_` | `address` | `address` |              The address of the Pool contract that will be deployed. |
| 2 | `poolDelegateCover_` | `address` | `address` | The address of the PoolDelegateCover contract that will be deployed. |
| 3 | `withdrawalManager_` | `address` | `address` | The address of the WithdrawalManager contract that will be deployed. |
| 4 | `loanManagers_` | `address[]` | `address[]` |      The address of the LoanManager contracts that will be deployed. |


<br />

### `globals`



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
        address[] loanManagers_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool_` | `address` | `address` | The address of the Pool deployed. |
| 1 | `poolManager_` | `address` | `address` | The address of the PoolManager deployed. |
| 2 | `withdrawalManager_` | `address` | `address` | The address of the WithdrawalManager deployed. |
| 3 | `loanManagers_` | `address[]` | `address[]` | An array of the addresses of the LoanManagers deployed. |

<br />

