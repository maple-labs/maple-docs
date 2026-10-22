# StrategyManagerInitializer



## Functions

### `active`

Returns whether or not the strategy manager is active.

```solidity
    function active()
        view
        returns (
            bool active
        );
```

#### Return Values:

| Index |   Name   |  Type  | Internal Type | Description                             |
| :---: | :------: | :----: | :-----------: | --------------------------------------- |
|   0   | `active` | `bool` |     `bool`    | True if the strategy manager is active. |



### `configured`

Returns whether or not the strategy manager is configured.

```solidity
    function configured()
        view
        returns (
            bool configured
        );
```

#### Return Values:

| Index |     Name     |  Type  | Internal Type | Description                                 |
| :---: | :----------: | :----: | :-----------: | ------------------------------------------- |
|   0   | `configured` | `bool` |     `bool`    | True if the strategy manager is configured. |



### `pendingSharesOf`

Returns the number of pending redemption shares held by a given pool manager.

```solidity
    function pendingSharesOf(
        address poolManager
    )
        view
        returns (
            uint256 pendingSharesOf
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                  |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager. |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                                                                          |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------------------------------------------------ |
|   0   | `pendingSharesOf` | `uint256` |   `uint256`   | Number of shares the pool manager has requested to redeem but has not yet processed. |



### `pendingStrategyDelegate`

Returns the address of the pending strategy delegate.

```solidity
    function pendingStrategyDelegate()
        view
        returns (
            address pendingStrategyDelegate
        );
```

#### Return Values:

| Index |            Name           |    Type   | Internal Type | Description                                   |
| :---: | :-----------------------: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `pendingStrategyDelegate` | `address` |   `address`   | The address of the pending strategy delegate. |



### `poolManagerCapOf`

Returns the per-pool-manager maximum asset position for a given pool manager. A value of zero means no cap is set and the pool manager has no limit, and funding is bounded only by the strategy liquidity cap. A value of \`type(uint256).max\` means the pool manager is blocked entirely.

```solidity
    function poolManagerCapOf(
        address poolManager
    )
        view
        returns (
            uint256 poolManagerCapOf
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                  |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                                                                                                                    |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------------------------- |
|   0   | `poolManagerCapOf` | `uint256` |   `uint256`   | The maximum asset position the pool manager is authorized to hold. Zero means no cap, \`type(uint256).max\` means the pool manager is blocked. |



### `sharesOf`

Returns the share balance held by a given pool manager.

```solidity
    function sharesOf(
        address poolManager
    )
        view
        returns (
            uint256 sharesOf
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                  |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager. |

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                                 |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `sharesOf` | `uint256` |   `uint256`   | Number of shares owned by the pool manager. |



### `strategyDelegate`

Returns the address of the strategy delegate.

```solidity
    function strategyDelegate()
        view
        returns (
            address strategyDelegate
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                           |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `strategyDelegate` | `address` |   `address`   | The address of the strategy delegate. |



### `strategyLiquidityCap`

Returns the maximum exposure to the strategy.

```solidity
    function strategyLiquidityCap()
        view
        returns (
            uint256 strategyLiquidityCap
        );
```

#### Return Values:

| Index |          Name          |    Type   | Internal Type | Description                                                                  |
| :---: | :--------------------: | :-------: | :-----------: | ---------------------------------------------------------------------------- |
|   0   | `strategyLiquidityCap` | `uint256` |   `uint256`   | The maximum total asset position the strategy manager is authorized to hold. |



### `totalPendingShares`

Returns the total number of pending redemption shares across all pool managers.

```solidity
    function totalPendingShares()
        view
        returns (
            uint256 totalPendingShares
        );
```

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                           |
| :---: | :------------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `totalPendingShares` | `uint256` |   `uint256`   | Sum of all pending redemption shares. |



### `totalShares`

Returns the total number of shares issued by the strategy manager.

```solidity
    function totalShares()
        view
        returns (
            uint256 totalShares
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                             |
| :---: | :-----------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `totalShares` | `uint256` |   `uint256`   | Sum of all shares across pool managers. |



### `underlyingStrategy`

Returns the address of the underlying strategy contract.

```solidity
    function underlyingStrategy()
        view
        returns (
            address underlyingStrategy
        );
```

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                         |
| :---: | :------------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `underlyingStrategy` | `address` |   `address`   | Address of the underlying strategy. |



## Events

### `Initialized`

Emitted when the strategy manager proxy is initialized.

```solidity
    event Initialized(
        Parameters params
    );
```

#### Parameters:

| Index |   Name   |   Type  |                     Internal Type                    | Description                                            |
| :---: | :------: | :-----: | :--------------------------------------------------: | ------------------------------------------------------ |
|   0   | `params` | `tuple` | `struct IMapleStrategyManagerInitializer.Parameters` | Strategy manager parameters set during initialization. |



## Structs

### `Parameters`

Parameters required to initialize a strategy manager.

```solidity
    struct Parameters {
        address strategyDelegate;
    }
```

#### Members:

| Index |        Name        |    Type   | Internal Type | Description                       |
| :---: | :----------------: | :-------: | :-----------: | --------------------------------- |
|   0   | `strategyDelegate` | `address` |   `address`   | Address of the strategy delegate. |

