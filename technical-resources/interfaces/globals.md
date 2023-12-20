# Maple Globals



<br />


## Functions

### `HUNDRED_PERCENT`



```solidity
    function HUNDRED_PERCENT()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `acceptGovernor`

Accepts the governorship if the caller is the &#x60;pendingGovernor&#x60;.

```solidity
    function acceptGovernor()
        nonpayable;
```



<br />

### `activatePoolManager`

Activates the pool manager.

```solidity
    function activatePoolManager(
        address poolManager_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager to activate. |


<br />

### `admin`

Returns the proxy&#x27;s admin address.

```solidity
    function admin()
        view
        returns (
            address admin_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `admin_` | `address` | `address` | The address of the admin. |


<br />

### `bootstrapMint`

Gets the virtualized first mint that acts as as offset to &#x60;totalAssets&#x60; and &#x60;totalSupply&#x60; for a given pool asset.

```solidity
    function bootstrapMint(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `canDeploy`

Gets whether a caller account can deploy from the factory calling this function.

```solidity
    function canDeploy(
        address caller_
    )
        view
        returns (
            bool canDeploy_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The address of the account calling the factory. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `canDeploy_` | `bool` | `bool` | Whether the account can deploy from the factory. |


<br />

### `canDeployFrom`

Gets whether a caller account can deploy from a factory.

```solidity
    function canDeployFrom(
        address factory_,
        address caller_
    )
        view
        returns (
            bool canDeployFrom_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `factory_` | `address` | `address` | The address of the factory. |
| 1 | `caller_` | `address` | `address` | The address of the account calling the factory. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `canDeployFrom_` | `bool` | `bool` | Whether the account can deploy from the factory. |


<br />

### `defaultTimelockParameters`

Gets the default timelock parameters.

```solidity
    function defaultTimelockParameters()
        view
        returns (
            uint128 delay,
            uint128 duration
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `delay` | `uint128` | `uint128` |    The default timelock delay. |
| 1 | `duration` | `uint128` | `uint128` | The default timelock duration. |


<br />

### `getLatestPrice`

Gets the latest price for an asset.

```solidity
    function getLatestPrice(
        address asset_
    )
        view
        returns (
            uint256 latestPrice_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of the asset to query. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `latestPrice_` | `uint256` | `uint256` | The latest price for the asset. |


<br />

### `governor`

Gets governor address.

```solidity
    function governor()
        view
        returns (
            address governor_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `governor_` | `address` | `address` | The address of the governor. |


<br />

### `implementation`

Returns the proxy&#x27;s implementation address.

```solidity
    function implementation()
        view
        returns (
            address implementation_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` | The address of the implementation. |


<br />

### `isBorrower`

Gets the validity of a borrower.

```solidity
    function isBorrower(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isCollateralAsset`

Gets the validity of a collateral asset.

```solidity
    function isCollateralAsset(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isContractPaused`

Gets whether a contract is uniquely paused.

```solidity
    function isContractPaused(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isFactory`

Gets the validity of a factory.

```solidity
    function isFactory(
        bytes32 factoryId_,
        address factory_
    )
        view
        returns (
            bool isFactory_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `factoryId_` | `bytes32` | `bytes32` | The address of the factory to query. |
| 1 | `factory_` | `address` | `address` | The address of the factory to query. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isFactory_` | `bool` | `bool` | A boolean indicating the validity of the factory. |


<br />

### `isFunctionPaused`

Gets whether a contract&#x27;s function is paused.

```solidity
    function isFunctionPaused(
        bytes4 sig_
    )
        view
        returns (
            bool functionIsPaused_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `sig_` | `bytes4` | `bytes4` | The function signature within the contract. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `functionIsPaused_` | `bool` | `bool` | Whether the contract&#x27;s function is paused. |


<br />

### `isFunctionPaused`

Gets whether a contract&#x27;s function is paused.

```solidity
    function isFunctionPaused(
        address contract_,
        bytes4 sig_
    )
        view
        returns (
            bool functionIsPaused_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `contract_` | `address` | `address` | The address of a contract in the protocol. |
| 1 | `sig_` | `bytes4` | `bytes4` | The function signature within the contract. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `functionIsPaused_` | `bool` | `bool` | Whether the contract&#x27;s function is paused. |


<br />

### `isFunctionUnpaused`

Gets whether a contract&#x27;s function is uniquely unpaused. A false does not imply it is paused.

```solidity
    function isFunctionUnpaused(
        address,
        bytes4
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `bytes4` | `bytes4` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isInstanceOf`

Gets wether an instance is of some instance key.

```solidity
    function isInstanceOf(
        bytes32,
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `bytes32` | `bytes32` |  |
| 1 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isPoolAsset`

Gets the validity of a pool asset.

```solidity
    function isPoolAsset(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isPoolDelegate`

Gets the validity of a pool delegate.

```solidity
    function isPoolDelegate(
        address account_
    )
        view
        returns (
            bool isPoolDelegate_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account_` | `address` | `address` | The address of the account to query. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isPoolDelegate_` | `bool` | `bool` | A boolean indicating the validity of the pool delegate. |


<br />

### `isPoolDeployer`

Gets the validity of a pool deployer.

```solidity
    function isPoolDeployer(
        address caller_
    )
        view
        returns (
            bool isPoolDeployer_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isPoolDeployer_` | `bool` | `bool` | A boolean indicating the validity of the pool deployer. |


<br />

### `isValidScheduledCall`

Checks if a call is scheduled.

```solidity
    function isValidScheduledCall(
        address caller_,
        address contract_,
        bytes32 functionId_,
        bytes callData_
    )
        view
        returns (
            bool isValid_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The contract to execute the call on. |
| 1 | `contract_` | `address` | `address` | The contract to execute the call on. |
| 2 | `functionId_` | `bytes32` | `bytes32` | The id of the function to execute. |
| 3 | `callData_` | `bytes` | `bytes` | The of the parameters to pass to the function. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isValid_` | `bool` | `bool` |    True if the call is scheduled, false otherwise. |


<br />

### `manualOverridePrice`

Gets the manual override price for an asset.

```solidity
    function manualOverridePrice(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `mapleTreasury`

Gets maple treasury address.

```solidity
    function mapleTreasury()
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

### `maxCoverLiquidationPercent`

Gets the maximum cover liquidation percent for a given pool manager.

```solidity
    function maxCoverLiquidationPercent(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `migrationAdmin`

Gets the migration admin address.

```solidity
    function migrationAdmin()
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

### `minCoverAmount`

Gets the minimum cover amount for a given pool manager.

```solidity
    function minCoverAmount(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `operationalAdmin`

Gets the operational admin address.

```solidity
    function operationalAdmin()
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

### `ownedPoolManager`

Gets the address of the owner pool manager.

```solidity
    function ownedPoolManager(
        address account_
    )
        view
        returns (
            address poolManager_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account_` | `address` | `address` | The address of the account to query. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager. |


<br />

### `pendingGovernor`

Gets the pending governor address.

```solidity
    function pendingGovernor()
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

### `platformManagementFeeRate`

Gets the platform management fee rate for a given pool manager.

```solidity
    function platformManagementFeeRate(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `platformOriginationFeeRate`

Gets the platform origination fee rate for a given pool manager.

```solidity
    function platformOriginationFeeRate(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `platformServiceFeeRate`

Gets the platform service fee rate for a given pool manager.

```solidity
    function platformServiceFeeRate(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `poolDelegates`

Gets pool delegate address information.

```solidity
    function poolDelegates(
        address
    )
        view
        returns (
            address ownedPoolManager,
            bool isPoolDelegate
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `ownedPoolManager` | `address` | `address` | The address of the pool manager owned by the pool delegate. |
| 1 | `isPoolDelegate` | `bool` | `bool` |   A boolean indication weather or not the address passed is a current pool delegate. |


<br />

### `priceOracleOf`

Gets the address and maximum delay of the oracle for the given asset.

```solidity
    function priceOracleOf(
        address
    )
        view
        returns (
            address oracle,
            uint96 maxDelay
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `oracle` | `address` | `address` |   The address of the oracle. |
| 1 | `maxDelay` | `uint96` | `uint96` | The maximum delay of the oracle. |


<br />

### `protocolPaused`

Gets the status of the protocol pause.

```solidity
    function protocolPaused()
        view
        returns (
            bool
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `scheduleCall`

Schedules a call to be executed.

```solidity
    function scheduleCall(
        address contract_,
        bytes32 functionId_,
        bytes callData_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `contract_` | `address` | `address` | The contract to execute the call on. |
| 1 | `functionId_` | `bytes32` | `bytes32` | The id of the function to execute. |
| 2 | `callData_` | `bytes` | `bytes` | The of the parameters to pass to the function. |


<br />

### `scheduledCalls`

Gets the schedule calls for the parameters.

```solidity
    function scheduledCalls(
        address,
        address,
        bytes32
    )
        view
        returns (
            uint256 timestamp,
            bytes32 dataHash
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `address` | `address` |  |
| 2 | `` | `bytes32` | `bytes32` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `timestamp` | `uint256` | `uint256` |   The timestamp of the next scheduled call. |
| 1 | `dataHash` | `bytes32` | `bytes32` |    The hash of data fot the scheduled call. |


<br />

### `securityAdmin`

Gets security admin address.

```solidity
    function securityAdmin()
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

### `setBootstrapMint`

Sets the virtualized first mint that acts as as offset to &#x60;totalAssets&#x60; and &#x60;totalSupply&#x60;         to prevent an MEV-exploit vector against the first pool depositor.

```solidity
    function setBootstrapMint(
        address asset_,
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of the pool asset. |
| 1 | `amount_` | `uint256` | `uint256` |  |


<br />

### `setCanDeployFrom`

Sets whether an account can deploying an instance from a particular factory.

```solidity
    function setCanDeployFrom(
        address factory_,
        address account_,
        bool canDeployFrom_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `factory_` | `address` | `address` | The address of the factory. |
| 1 | `account_` | `address` | `address` | The address of the account. |
| 2 | `canDeployFrom_` | `bool` | `bool` | Whether the account can deploy or not from the factory. |


<br />

### `setContractPause`

Sets whether a contract is uniquely paused.

```solidity
    function setContractPause(
        address contract_,
        bool contractPaused_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `contract_` | `address` | `address` | The address of a contract in the protocol. |
| 1 | `contractPaused_` | `bool` | `bool` | Whether the contract is uniquely paused. |


<br />

### `setDefaultTimelockParameters`

Sets the default time lock parameters.

```solidity
    function setDefaultTimelockParameters(
        uint128 defaultTimelockDelay_,
        uint128 defaultTimelockDuration_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `defaultTimelockDelay_` | `uint128` | `uint128` | The default time lock delay. |
| 1 | `defaultTimelockDuration_` | `uint128` | `uint128` | The default time lock duration. |


<br />

### `setFunctionUnpause`

Sets whether a contract&#x27;s function is uniquely unpaused. A false does not imply it is paused.

```solidity
    function setFunctionUnpause(
        address contract_,
        bytes4 sig_,
        bool functionUnpaused_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `contract_` | `address` | `address` | The address of a contract in the protocol. |
| 1 | `sig_` | `bytes4` | `bytes4` | The function signature within the contract. |
| 2 | `functionUnpaused_` | `bool` | `bool` | Whether the contract&#x27;s function is uniquely unpaused. |


<br />

### `setManualOverridePrice`

Sets the manual override price of the asset.

```solidity
    function setManualOverridePrice(
        address asset_,
        uint256 price_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of the asset to set the price for. |
| 1 | `price_` | `uint256` | `uint256` | The price of the asset. |


<br />

### `setMapleTreasury`

Sets the address of the Maple treasury.

```solidity
    function setMapleTreasury(
        address mapleTreasury_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `mapleTreasury_` | `address` | `address` | The address of the Maple treasury. |


<br />

### `setMaxCoverLiquidationPercent`

Sets the maximum cover liquidation percent for the given pool manager.

```solidity
    function setMaxCoverLiquidationPercent(
        address poolManager_,
        uint256 maxCoverLiquidationPercent_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager to set the maximum cover liquidation percent for. |
| 1 | `maxCoverLiquidationPercent_` | `uint256` | `uint256` | The maximum cover liquidation percent. |


<br />

### `setMigrationAdmin`

Sets the address of the migration admin.

```solidity
    function setMigrationAdmin(
        address migrationAdmin_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `migrationAdmin_` | `address` | `address` | The address of the migration admin. |


<br />

### `setMinCoverAmount`

Sets the minimum cover amount for the given pool manager.

```solidity
    function setMinCoverAmount(
        address poolManager_,
        uint256 minCoverAmount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager to set the minimum cover amount  for. |
| 1 | `minCoverAmount_` | `uint256` | `uint256` | The minimum cover amount. |


<br />

### `setOperationalAdmin`

Sets the address of the operational admin.

```solidity
    function setOperationalAdmin(
        address operationalAdmin_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `operationalAdmin_` | `address` | `address` | The address of the operational admin. |


<br />

### `setPendingGovernor`

Sets the pending governor.

```solidity
    function setPendingGovernor(
        address pendingGovernor_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingGovernor_` | `address` | `address` | The new pending governor. |


<br />

### `setPlatformManagementFeeRate`

Sets the platform management fee rate for the given pool manager.

```solidity
    function setPlatformManagementFeeRate(
        address poolManager_,
        uint256 platformManagementFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager to set the fee for. |
| 1 | `platformManagementFeeRate_` | `uint256` | `uint256` | The platform management fee rate. |


<br />

### `setPlatformOriginationFeeRate`

Sets the platform origination fee rate for the given pool manager.

```solidity
    function setPlatformOriginationFeeRate(
        address poolManager_,
        uint256 platformOriginationFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager to set the fee for. |
| 1 | `platformOriginationFeeRate_` | `uint256` | `uint256` | The platform origination fee rate. |


<br />

### `setPlatformServiceFeeRate`

Sets the platform service fee rate for the given pool manager.

```solidity
    function setPlatformServiceFeeRate(
        address poolManager_,
        uint256 platformServiceFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager to set the fee for. |
| 1 | `platformServiceFeeRate_` | `uint256` | `uint256` | The platform service fee rate. |


<br />

### `setPriceOracle`

Sets the price oracle for the given asset.

```solidity
    function setPriceOracle(
        address asset_,
        address oracle_,
        uint96 maxDelay_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of the asset to set the oracle for. |
| 1 | `oracle_` | `address` | `address` | The address of the oracle to set for the asset. |
| 2 | `maxDelay_` | `uint96` | `uint96` | Maximum delay set to check for stale price. |


<br />

### `setProtocolPause`

Sets the protocol pause.

```solidity
    function setProtocolPause(
        bool protocolPaused_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `protocolPaused_` | `bool` | `bool` | A boolean indicating the status of the protocol pause. |


<br />

### `setSecurityAdmin`

Sets the address of the security admin.

```solidity
    function setSecurityAdmin(
        address securityAdmin_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `securityAdmin_` | `address` | `address` | The address of the security admin. |


<br />

### `setTimelockWindow`

Sets the timelock for the given contract.

```solidity
    function setTimelockWindow(
        address contract_,
        bytes32 functionId_,
        uint128 delay_,
        uint128 duration_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `contract_` | `address` | `address` | The address of the contract to add. |
| 1 | `functionId_` | `bytes32` | `bytes32` | The id of the function. |
| 2 | `delay_` | `uint128` | `uint128` | The delay for the timelock window. |
| 3 | `duration_` | `uint128` | `uint128` | The duration for the timelock window. |


<br />

### `setTimelockWindows`

Sets the timelock for the many function ids in a contract.

```solidity
    function setTimelockWindows(
        address contract_,
        bytes32[] functionIds_,
        uint128[] delays_,
        uint128[] durations_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `contract_` | `address` | `address` | The address of the contract to add. |
| 1 | `functionIds_` | `bytes32[]` | `bytes32[]` | The ids of the functions. |
| 2 | `delays_` | `uint128[]` | `uint128[]` | The delays for the timelock window. |
| 3 | `durations_` | `uint128[]` | `uint128[]` | The durations for the timelock window. |


<br />

### `setValidBorrower`

Sets the validity of the borrower.

```solidity
    function setValidBorrower(
        address borrower_,
        bool isValid_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` | The address of the borrower to set the validity for. |
| 1 | `isValid_` | `bool` | `bool` | A boolean indicating the validity of the borrower. |


<br />

### `setValidCollateralAsset`

Sets the validity of a collateral asset.

```solidity
    function setValidCollateralAsset(
        address collateralAsset_,
        bool isValid_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` | The address of the collateral asset to set the validity for. |
| 1 | `isValid_` | `bool` | `bool` | A boolean indicating the validity of the collateral asset. |


<br />

### `setValidInstanceOf`

Sets the validity of the instance.

```solidity
    function setValidInstanceOf(
        bytes32 instanceKey_,
        address instance_,
        bool isValid_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `instanceKey_` | `bytes32` | `bytes32` | The key of the instance to set the validity for. |
| 1 | `instance_` | `address` | `address` | The address of the instance to set the validity for. |
| 2 | `isValid_` | `bool` | `bool` | Boolean indicating the validity of the instance. |


<br />

### `setValidPoolAsset`

Sets the validity of the pool asset.

```solidity
    function setValidPoolAsset(
        address poolAsset_,
        bool isValid_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolAsset_` | `address` | `address` | The address of the pool asset to set the validity for. |
| 1 | `isValid_` | `bool` | `bool` | A boolean indicating the validity of the pool asset. |


<br />

### `setValidPoolDelegate`

Sets the validity of the pool delegate.

```solidity
    function setValidPoolDelegate(
        address account_,
        bool isValid_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account_` | `address` | `address` |  |
| 1 | `isValid_` | `bool` | `bool` | A boolean indicating the validity of the pool delegate. |


<br />

### `setValidPoolDeployer`

Sets the validity of the pool deployer.

```solidity
    function setValidPoolDeployer(
        address account_,
        bool isPoolDeployer_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account_` | `address` | `address` | The address of the pool deployer to set the validity for. |
| 1 | `isPoolDeployer_` | `bool` | `bool` | A boolean indicating the validity of the pool deployer. |


<br />

### `timelockParametersOf`

Gets the time lock parameters for a given contract and function.

```solidity
    function timelockParametersOf(
        address,
        bytes32
    )
        view
        returns (
            uint128 delay,
            uint128 duration
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `bytes32` | `bytes32` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `delay` | `uint128` | `uint128` |       The time lock delay. |
| 1 | `duration` | `uint128` | `uint128` |    The time lock duration. |


<br />

### `transferOwnedPoolManager`

Transfer the ownership of the pool manager.

```solidity
    function transferOwnedPoolManager(
        address fromPoolDelegate_,
        address toPoolDelegate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fromPoolDelegate_` | `address` | `address` | The address of the pool delegate to transfer ownership from. |
| 1 | `toPoolDelegate_` | `address` | `address` | The address of the pool delegate to transfer ownership to. |


<br />

### `unscheduleCall`

Unschedules a call to be executed.

```solidity
    function unscheduleCall(
        address caller_,
        address contract_,
        bytes32 functionId_,
        bytes callData_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The contract to execute the call on. |
| 1 | `contract_` | `address` | `address` | The contract to execute the call on. |
| 2 | `functionId_` | `bytes32` | `bytes32` | The id of the function to execute. |
| 3 | `callData_` | `bytes` | `bytes` | The of the parameters to pass to the function. |


<br />

### `unscheduleCall`

Unschedules a call to be executed.

```solidity
    function unscheduleCall(
        address caller_,
        bytes32 functionId_,
        bytes callData_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The contract to execute the call on. |
| 1 | `functionId_` | `bytes32` | `bytes32` | The id of the function to execute. |
| 2 | `callData_` | `bytes` | `bytes` | The of the parameters to pass to the function. |


<br />


## Events

### `BootstrapMintSet`

A virtualized first mint that acts as as offset to &#x60;totalAssets&#x60; and &#x60;totalSupply&#x60;.

```solidity
    event BootstrapMintSet(
        address asset_,
        uint256 bootstrapMint_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of the pool asset. |
| 1 | `bootstrapMint_` | `uint256` | `uint256` | The amount of shares that will offset &#x60;totalAssets&#x60; and &#x60;totalSupply&#x60;. |

<br />

### `CallScheduled`

A time locked call has been scheduled.

```solidity
    event CallScheduled(
        address caller_,
        address contract_,
        bytes32 functionId_,
        bytes32 dataHash_,
        uint256 timestamp_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The address of the function caller. |
| 1 | `contract_` | `address` | `address` | The contract to execute the call on. |
| 2 | `functionId_` | `bytes32` | `bytes32` | The id of the function to execute. |
| 3 | `dataHash_` | `bytes32` | `bytes32` | The hash of the parameters to pass to the function. |
| 4 | `timestamp_` | `uint256` | `uint256` | The timestamp of the schedule. |

<br />

### `CallUnscheduled`

A time locked call has been unscheduled.

```solidity
    event CallUnscheduled(
        address caller_,
        address contract_,
        bytes32 functionId_,
        bytes32 dataHash_,
        uint256 timestamp_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The address of the function caller. |
| 1 | `contract_` | `address` | `address` | The contract to execute the call on. |
| 2 | `functionId_` | `bytes32` | `bytes32` | The id of the function to execute. |
| 3 | `dataHash_` | `bytes32` | `bytes32` | The hash of the parameters to pass to the function. |
| 4 | `timestamp_` | `uint256` | `uint256` | The timestamp of the schedule. |

<br />

### `CanDeployFromSet`

An account has been allowed/disallowed from deploying an instance from a particular factory.

```solidity
    event CanDeployFromSet(
        address factory_,
        address account_,
        bool canDeployFrom_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `factory_` | `address` | `address` | The address of the factory. |
| 1 | `account_` | `address` | `address` | The address of the account. |
| 2 | `canDeployFrom_` | `bool` | `bool` | Whether the account can deploy from the factory. |

<br />

### `ContractPauseSet`

The paused state for a given protocol contract was set.

```solidity
    event ContractPauseSet(
        address caller_,
        address contract_,
        bool contractPaused_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The address of the security admin or governor that performed the action. |
| 1 | `contract_` | `address` | `address` | The address of a contract in the protocol. |
| 2 | `contractPaused_` | `bool` | `bool` | Whether the contract is uniquely paused. |

<br />

### `DefaultTimelockParametersSet`

The default parameters for the time lock has been set.

```solidity
    event DefaultTimelockParametersSet(
        uint256 previousDelay_,
        uint256 currentDelay_,
        uint256 previousDuration_,
        uint256 currentDuration_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousDelay_` | `uint256` | `uint256` | The previous required delay. |
| 1 | `currentDelay_` | `uint256` | `uint256` | The newly set required delay. |
| 2 | `previousDuration_` | `uint256` | `uint256` | The previous required duration. |
| 3 | `currentDuration_` | `uint256` | `uint256` | The newly set required duration. |

<br />

### `FunctionUnpauseSet`

The paused state for a function of a given protocol contract was set.

```solidity
    event FunctionUnpauseSet(
        address caller_,
        address contract_,
        bytes4 sig_,
        bool functionUnpaused_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The address of the security admin or governor that performed the action. |
| 1 | `contract_` | `address` | `address` | The address of a contract in the protocol. |
| 2 | `sig_` | `bytes4` | `bytes4` | The function signature within the contract. |
| 3 | `functionUnpaused_` | `bool` | `bool` | Whether the contract&#x27;s function is uniquely unpaused. |

<br />

### `GovernorshipAccepted`

The governorship has been accepted.

```solidity
    event GovernorshipAccepted(
        address previousGovernor_,
        address currentGovernor_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousGovernor_` | `address` | `address` | The previous governor. |
| 1 | `currentGovernor_` | `address` | `address` | The new governor. |

<br />

### `ManualOverridePriceSet`

The price for an asset has been set.

```solidity
    event ManualOverridePriceSet(
        address asset_,
        uint256 price_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of the asset. |
| 1 | `price_` | `uint256` | `uint256` | The manually set price of the asset. |

<br />

### `MapleTreasurySet`

The address for the Maple treasury has been set.

```solidity
    event MapleTreasurySet(
        address previousMapleTreasury_,
        address currentMapleTreasury_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousMapleTreasury_` | `address` | `address` | The previous treasury. |
| 1 | `currentMapleTreasury_` | `address` | `address` | The new treasury. |

<br />

### `MaxCoverLiquidationPercentSet`

The max liquidation percent for the given pool manager has been set.

```solidity
    event MaxCoverLiquidationPercentSet(
        address poolManager_,
        uint256 maxCoverLiquidationPercent_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager. |
| 1 | `maxCoverLiquidationPercent_` | `uint256` | `uint256` | The new value for the cover liquidation percent. |

<br />

### `MigrationAdminSet`

The migration admin has been set.

```solidity
    event MigrationAdminSet(
        address previousMigrationAdmin_,
        address nextMigrationAdmin_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousMigrationAdmin_` | `address` | `address` | The previous migration admin. |
| 1 | `nextMigrationAdmin_` | `address` | `address` | The new migration admin. |

<br />

### `MinCoverAmountSet`

The minimum cover amount for the given pool manager has been set.

```solidity
    event MinCoverAmountSet(
        address poolManager_,
        uint256 minCoverAmount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager. |
| 1 | `minCoverAmount_` | `uint256` | `uint256` | The new value for the minimum cover amount. |

<br />

### `OperationalAdminSet`

The operational admin was set.

```solidity
    event OperationalAdminSet(
        address previousOperationalAdmin_,
        address currentOperationalAdmin_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousOperationalAdmin_` | `address` | `address` | The address of the previous operational admin. |
| 1 | `currentOperationalAdmin_` | `address` | `address` | The address of the new operational admin. |

<br />

### `PendingGovernorSet`

The pending governor has been set.

```solidity
    event PendingGovernorSet(
        address pendingGovernor_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingGovernor_` | `address` | `address` | The new pending governor. |

<br />

### `PlatformManagementFeeRateSet`

The platform management fee rate for the given pool manager has been set.

```solidity
    event PlatformManagementFeeRateSet(
        address poolManager_,
        uint256 platformManagementFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager. |
| 1 | `platformManagementFeeRate_` | `uint256` | `uint256` | The new value for the platform management fee rate. |

<br />

### `PlatformOriginationFeeRateSet`

The platform origination fee rate for the given pool manager has been set.

```solidity
    event PlatformOriginationFeeRateSet(
        address poolManager_,
        uint256 platformOriginationFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager. |
| 1 | `platformOriginationFeeRate_` | `uint256` | `uint256` | The new value for the origination fee rate. |

<br />

### `PlatformServiceFeeRateSet`

The platform service fee rate for the given pool manager has been set.

```solidity
    event PlatformServiceFeeRateSet(
        address poolManager_,
        uint256 platformServiceFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager. |
| 1 | `platformServiceFeeRate_` | `uint256` | `uint256` | The new value for the platform service fee rate. |

<br />

### `PoolManagerActivated`

The pool manager was activated.

```solidity
    event PoolManagerActivated(
        address poolManager_,
        address poolDelegate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` | The address of the pool manager. |
| 1 | `poolDelegate_` | `address` | `address` | The address of the pool delegate. |

<br />

### `PoolManagerOwnershipTransferred`

The ownership of the pool manager was transferred.

```solidity
    event PoolManagerOwnershipTransferred(
        address fromPoolDelegate_,
        address toPoolDelegate_,
        address poolManager_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fromPoolDelegate_` | `address` | `address` | The address of the previous pool delegate. |
| 1 | `toPoolDelegate_` | `address` | `address` | The address of the new pool delegate. |
| 2 | `poolManager_` | `address` | `address` | The address of the pool manager. |

<br />

### `PriceOracleSet`

The oracle for an asset has been set.

```solidity
    event PriceOracleSet(
        address asset_,
        address oracle_,
        uint96 maxDelay_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset_` | `address` | `address` | The address of the asset. |
| 1 | `oracle_` | `address` | `address` | The address of the oracle. |
| 2 | `maxDelay_` | `uint96` | `uint96` | The maximum delay of the oracle. |

<br />

### `ProtocolPauseSet`

The protocol pause was set to a new state.

```solidity
    event ProtocolPauseSet(
        address caller_,
        bool protocolPaused_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `caller_` | `address` | `address` | The address of the security admin or governor that performed the action. |
| 1 | `protocolPaused_` | `bool` | `bool` | The protocol paused state. |

<br />

### `SecurityAdminSet`

The security admin was set.

```solidity
    event SecurityAdminSet(
        address previousSecurityAdmin_,
        address currentSecurityAdmin_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousSecurityAdmin_` | `address` | `address` | The address of the previous security admin. |
| 1 | `currentSecurityAdmin_` | `address` | `address` | The address of the new security admin. |

<br />

### `TimelockWindowSet`

A new timelock window was set.

```solidity
    event TimelockWindowSet(
        address contract_,
        bytes32 functionId_,
        uint128 delay_,
        uint128 duration_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `contract_` | `address` | `address` | The contract to execute the call on. |
| 1 | `functionId_` | `bytes32` | `bytes32` | The id of the function to execute. |
| 2 | `delay_` | `uint128` | `uint128` | The delay of the timelock window. |
| 3 | `duration_` | `uint128` | `uint128` | The duration of the timelock window. |

<br />

### `ValidBorrowerSet`

A valid borrower was set.

```solidity
    event ValidBorrowerSet(
        address borrower_,
        bool isValid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` | The address of the borrower. |
| 1 | `isValid_` | `bool` | `bool` | The validity of the borrower. |

<br />

### `ValidCollateralAssetSet`

A valid asset was set.

```solidity
    event ValidCollateralAssetSet(
        address collateralAsset_,
        bool isValid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` | The address of the collateral asset. |
| 1 | `isValid_` | `bool` | `bool` | The validity of the collateral asset. |

<br />

### `ValidInstanceSet`

A valid instance was set.

```solidity
    event ValidInstanceSet(
        bytes32 instanceKey_,
        address instance_,
        bool isValid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `instanceKey_` | `bytes32` | `bytes32` | The key of the instance. |
| 1 | `instance_` | `address` | `address` | The address of the instance. |
| 2 | `isValid_` | `bool` | `bool` | The validity of the instance. |

<br />

### `ValidPoolAssetSet`

A valid asset was set.

```solidity
    event ValidPoolAssetSet(
        address poolAsset_,
        bool isValid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolAsset_` | `address` | `address` | The address of the asset. |
| 1 | `isValid_` | `bool` | `bool` | The validity of the asset. |

<br />

### `ValidPoolDelegateSet`

A valid pool delegate was set.

```solidity
    event ValidPoolDelegateSet(
        address account_,
        bool isValid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account_` | `address` | `address` | The address the account. |
| 1 | `isValid_` | `bool` | `bool` | The validity of the asset. |

<br />

### `ValidPoolDeployerSet`

A valid pool deployer was set.

```solidity
    event ValidPoolDeployerSet(
        address poolDeployer_,
        bool isValid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDeployer_` | `address` | `address` | The address the account. |
| 1 | `isValid_` | `bool` | `bool` | The validity of the asset. |

<br />

