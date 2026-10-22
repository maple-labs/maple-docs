# PoolManagerInitializer



## Functions

### `active`

Returns whether or not a pool is active.

```solidity
    function active()
        view
        returns (
            bool active_
        );
```

#### Return Values:

| Index |    Name   |  Type  | Internal Type | Description                 |
| :---: | :-------: | :----: | :-----------: | --------------------------- |
|   0   | `active_` | `bool` |     `bool`    | True if the pool is active. |



### `asset`

Gets the address of the funds asset.

```solidity
    function asset()
        view
        returns (
            address asset_
        );
```

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                     |
| :---: | :------: | :-------: | :-----------: | ------------------------------- |
|   0   | `asset_` | `address` |   `address`   | The address of the funds asset. |



### `configured`

Returns whether or not a pool is configured.

```solidity
    function configured()
        view
        returns (
            bool configured_
        );
```

#### Return Values:

| Index |      Name     |  Type  | Internal Type | Description                     |
| :---: | :-----------: | :----: | :-----------: | ------------------------------- |
|   0   | `configured_` | `bool` |     `bool`    | True if the pool is configured. |



### `delegateManagementFeeRate`

Gets the delegate management fee rate.

```solidity
    function delegateManagementFeeRate()
        view
        returns (
            uint256 delegateManagementFeeRate_
        );
```

#### Return Values:

| Index |             Name             |    Type   | Internal Type | Description                                     |
| :---: | :--------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `delegateManagementFeeRate_` | `uint256` |   `uint256`   | The value for the delegate management fee rate. |



### `isStrategy`

Returns whether or not the given address is a registered strategy. These are legacy strategies set to be depreciated in future for the new modular strategies.

```solidity
    function isStrategy(
        address strategy_
    )
        view
        returns (
            bool isStrategy_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                  |
| :---: | :---------: | :-------: | :-----------: | ---------------------------- |
|   0   | `strategy_` | `address` |   `address`   | The address of the strategy. |

#### Return Values:

| Index |      Name     |  Type  | Internal Type | Description                                   |
| :---: | :-----------: | :----: | :-----------: | --------------------------------------------- |
|   0   | `isStrategy_` | `bool` |     `bool`    | True if the address is a registered strategy. |



### `isStrategyManager`

Returns whether or not the given address is a registered strategy manager.

```solidity
    function isStrategyManager(
        address strategyManager_
    )
        view
        returns (
            bool isStrategyManager_
        );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                          |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `strategyManager_` | `address` |   `address`   | The address of the strategy manager. |

#### Return Values:

| Index |         Name         |  Type  | Internal Type | Description                                           |
| :---: | :------------------: | :----: | :-----------: | ----------------------------------------------------- |
|   0   | `isStrategyManager_` | `bool` |     `bool`    | True if the address is a registered strategy manager. |



### `liquidityCap`

Gets the liquidity cap for the pool.

```solidity
    function liquidityCap()
        view
        returns (
            uint256 liquidityCap_
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                     |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `liquidityCap_` | `uint256` |   `uint256`   | The liquidity cap for the pool. |



### `pendingPoolDelegate`

Gets the address of the pending pool delegate.

```solidity
    function pendingPoolDelegate()
        view
        returns (
            address pendingPoolDelegate_
        );
```

#### Return Values:

| Index |          Name          |    Type   | Internal Type | Description                               |
| :---: | :--------------------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `pendingPoolDelegate_` | `address` |   `address`   | The address of the pending pool delegate. |



### `pool`

Gets the address of the pool.

```solidity
    function pool()
        view
        returns (
            address pool_
        );
```

#### Return Values:

| Index |   Name  |    Type   | Internal Type | Description              |
| :---: | :-----: | :-------: | :-----------: | ------------------------ |
|   0   | `pool_` | `address` |   `address`   | The address of the pool. |



### `poolDelegate`

Gets the address of the pool delegate.

```solidity
    function poolDelegate()
        view
        returns (
            address poolDelegate_
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                       |
| :---: | :-------------: | :-------: | :-----------: | --------------------------------- |
|   0   | `poolDelegate_` | `address` |   `address`   | The address of the pool delegate. |



### `poolPermissionManager`

Gets the address of the pool permission manager.

```solidity
    function poolPermissionManager()
        view
        returns (
            address poolPermissionManager_
        );
```

#### Return Values:

| Index |           Name           |    Type   | Internal Type | Description                                 |
| :---: | :----------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `poolPermissionManager_` | `address` |   `address`   | The address of the pool permission manager. |



### `strategyCapOf`

Gets the pool's AUM exposure cap to a given strategy or strategy manager. The maximum amount of this pool's assets that may be deployed at any one time.

```solidity
    function strategyCapOf(
        address strategy_
    )
        view
        returns (
            uint256 cap_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                      |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   | `strategy_` | `address` |   `address`   | The address of the strategy or strategy manager. |

#### Return Values:

| Index |  Name  |    Type   | Internal Type | Description                  |
| :---: | :----: | :-------: | :-----------: | ---------------------------- |
|   0   | `cap_` | `uint256` |   `uint256`   | The pool's AUM exposure cap. |



### `strategyList`

Gets the address of the strategy in the list.

```solidity
    function strategyList(
        uint256 index_
    )
        view
        returns (
            address strategy_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                      |
| :---: | :------: | :-------: | :-----------: | -------------------------------- |
|   0   | `index_` | `uint256` |   `uint256`   | The index to get the address of. |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description              |
| :---: | :---------: | :-------: | :-----------: | ------------------------ |
|   0   | `strategy_` | `address` |   `address`   | The address in the list. |



### `withdrawalManager`

Gets the address of the withdrawal manager.

```solidity
    function withdrawalManager()
        view
        returns (
            address withdrawalManager_
        );
```

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                            |
| :---: | :------------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `withdrawalManager_` | `address` |   `address`   | The address of the withdrawal manager. |



## Events

### `Initialized`

```solidity
    event Initialized(
        address owner_,
        address asset_,
        address pool_
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description |
| :---: | :------: | :-------: | :-----------: | ----------- |
|   0   | `owner_` | `address` |   `address`   |             |
|   1   | `asset_` | `address` |   `address`   |             |
|   2   |  `pool_` | `address` |   `address`   |             |

