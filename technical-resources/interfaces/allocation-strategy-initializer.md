# AllocationStrategyInitializer



## Functions

### `deployedAssetsOf`

Returns the amount of assets currently deployed by a managed wallet.

```solidity
    function deployedAssetsOf(
        address account
    )
        view
        returns (
            uint256 deployedAssets
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                    |
| :---: | :-------: | :-------: | :-----------: | ------------------------------ |
|   0   | `account` | `address` |   `address`   | Address of the managed wallet. |

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                                         |
| :---: | :--------------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   | `deployedAssets` | `uint256` |   `uint256`   | Amount of assets currently deployed by the address. |



### `deploymentCapOf`

Returns the deployment cap configured for a managed wallet.

```solidity
    function deploymentCapOf(
        address account
    )
        view
        returns (
            uint256 deploymentCap
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                        |
| :---: | :-------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   | `account` | `address` |   `address`   | Address of the managed wallet to read the cap for. |

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                                             |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------------------------------- |
|   0   | `deploymentCap` | `uint256` |   `uint256`   | Maximum amount of assets the managed wallet can deploy. |



### `fundsAsset`

Returns the address of the asset used by the strategy. Must be ERC-20 compatible.

```solidity
    function fundsAsset()
        view
        returns (
            address fundsAsset
        );
```

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description                                |
| :---: | :----------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `fundsAsset` | `address` |   `address`   | Address of the asset used by the strategy. |



### `impairedAssets`

Returns the total amount of impaired assets.

```solidity
    function impairedAssets()
        view
        returns (
            uint256 impairedAssets
        );
```

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                     |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `impairedAssets` | `uint256` |   `uint256`   | Total amount of impairedAssets. |



### `permissions`

Returns the permission flags for a given address.

```solidity
    function permissions(
        address account
    )
        view
        returns (
            bool canDeployAssets,
            bool canReturnAssets,
            bool canRealizeYield
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   | `account` | `address` |   `address`   | Address to read permissions for. |

#### Return Values:

| Index |        Name       |  Type  | Internal Type | Description                              |
| :---: | :---------------: | :----: | :-----------: | ---------------------------------------- |
|   0   | `canDeployAssets` | `bool` |     `bool`    | Defines if an address can deploy assets. |
|   1   | `canReturnAssets` | `bool` |     `bool`    | Defines if an address can return assets. |
|   2   | `canRealizeYield` | `bool` |     `bool`    | Defines if an address can realize yield. |



### `recordedAssets`

Returns the amount of assets recorded as held by the strategy. Comprised of the assets available to withdraw and the yield that has not vested yet. Assets transferred to the strategy outside of fundUnderlyingStrategy(), returnAssets() and realizeYield() are not recorded, and therefore are not reflected in this value.

```solidity
    function recordedAssets()
        view
        returns (
            uint256 recordedAssets
        );
```

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                                        |
| :---: | :--------------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   | `recordedAssets` | `uint256` |   `uint256`   | Amount of assets recorded as held by the strategy. |



### `scheduledYieldAssets`

Returns the total amount of assets in the yield buffer since it was last updated.

```solidity
    function scheduledYieldAssets()
        view
        returns (
            uint256 scheduledYieldAssets
        );
```

#### Return Values:

| Index |          Name          |    Type   | Internal Type | Description                                         |
| :---: | :--------------------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   | `scheduledYieldAssets` | `uint256` |   `uint256`   | Total assets in the yield buffer since last update. |



### `strategyDelegateFeeRate`

Returns the percentage of all strategy yield collected by the strategy delegate. Defined with 6 decimals of precision (1e6 == 100%).

```solidity
    function strategyDelegateFeeRate()
        view
        returns (
            uint32 strategyDelegateFeeRate
        );
```

#### Return Values:

| Index |            Name           |   Type   | Internal Type | Description                                             |
| :---: | :-----------------------: | :------: | :-----------: | ------------------------------------------------------- |
|   0   | `strategyDelegateFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate. |



### `strategyManager`

Returns the address of the strategy manager contract.

```solidity
    function strategyManager()
        view
        returns (
            address strategyManager
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                      |
| :---: | :---------------: | :-------: | :-----------: | -------------------------------- |
|   0   | `strategyManager` | `address` |   `address`   | Address of the strategy manager. |



### `strategyMetadata`

Returns arbitrary metadata associated with this instance of the allocation strategy.

```solidity
    function strategyMetadata()
        view
        returns (
            string strategyMetadata
        );
```

#### Return Values:

| Index |        Name        |   Type   | Internal Type | Description                                     |
| :---: | :----------------: | :------: | :-----------: | ----------------------------------------------- |
|   0   | `strategyMetadata` | `string` |    `string`   | Optional metadata associated with the strategy. |



### `strategyProtocolFeeRate`

Returns the percentage of all strategy yield collected by the Maple treasury. Defined with 6 decimals of precision (1e6 == 100%).

```solidity
    function strategyProtocolFeeRate()
        view
        returns (
            uint32 strategyProtocolFeeRate
        );
```

#### Return Values:

| Index |            Name           |   Type   | Internal Type | Description                                          |
| :---: | :-----------------------: | :------: | :-----------: | ---------------------------------------------------- |
|   0   | `strategyProtocolFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury. |



### `totalDeployedAssets`

Returns the total amount of assets currently deployed across all managed wallets.

```solidity
    function totalDeployedAssets()
        view
        returns (
            uint256 totalDeployedAssets
        );
```

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                                                |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   | `totalDeployedAssets` | `uint256` |   `uint256`   | Total amount of assets currently deployed by the strategy. |



### `yieldCap`

Returns the maximum amount of assets that can be supplied as the \`assets\` parameter of realizeYield().

```solidity
    function yieldCap()
        view
        returns (
            uint256 yieldCap
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                                                              |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------------------------------ |
|   0   | `yieldCap` | `uint256` |   `uint256`   | Maximum amount of assets that can be realized as yield in a single call. |



### `yieldDeadline`

Returns the timestamp when all yield assets are fully realized.

```solidity
    function yieldDeadline()
        view
        returns (
            uint32 yieldDeadline
        );
```

#### Return Values:

| Index |       Name      |   Type   | Internal Type | Description                                     |
| :---: | :-------------: | :------: | :-----------: | ----------------------------------------------- |
|   0   | `yieldDeadline` | `uint32` |    `uint32`   | Timestamp when yield assets are fully realized. |



### `yieldLastRealized`

Returns the timestamp of the last successful yield realization.

```solidity
    function yieldLastRealized()
        view
        returns (
            uint32 yieldLastRealized
        );
```

#### Return Values:

| Index |         Name        |   Type   | Internal Type | Description                                         |
| :---: | :-----------------: | :------: | :-----------: | --------------------------------------------------- |
|   0   | `yieldLastRealized` | `uint32` |    `uint32`   | Timestamp of the last successful yield realization. |



### `yieldStart`

Returns the timestamp when the yield buffer was last updated.

```solidity
    function yieldStart()
        view
        returns (
            uint32 yieldStart
        );
```

#### Return Values:

| Index |     Name     |   Type   | Internal Type | Description                                               |
| :---: | :----------: | :------: | :-----------: | --------------------------------------------------------- |
|   0   | `yieldStart` | `uint32` |    `uint32`   | Timestamp when the current yield buffer was last updated. |



## Events

### `Initialized`

Emitted when the allocation strategy proxy is initialized.

```solidity
    event Initialized(
        address strategyManager,
        AllocationStrategyInitializerParams params
    );
```

#### Parameters:

| Index |        Name       |    Type   |                 Internal Type                | Description                                               |
| :---: | :---------------: | :-------: | :------------------------------------------: | --------------------------------------------------------- |
|   0   | `strategyManager` | `address` |                   `address`                  | Address of the strategy manager contract.                 |
|   1   |      `params`     |  `tuple`  | `struct AllocationStrategyInitializerParams` | Allocation strategy parameters set during initialization. |



## Structs

### `AllocationStrategyInitializerParams`

Parameters required to initialize an allocation strategy. Initializer arguments are encoded as abi.encode(strategyManager) || abi.encode(params).

```solidity
    struct AllocationStrategyInitializerParams {
        address fundsAsset;
        string strategyMetadata;
        uint32 strategyDelegateFeeRate;
        uint32 strategyProtocolFeeRate;
        uint256 yieldCap;
    }
```

#### Members:

| Index |            Name           |    Type   | Internal Type | Description                                                              |
| :---: | :-----------------------: | :-------: | :-----------: | ------------------------------------------------------------------------ |
|   0   |        `fundsAsset`       | `address` |   `address`   | Address of the asset used by the strategy.                               |
|   1   |     `strategyMetadata`    |  `string` |    `string`   | Optional metadata associated with the allocation strategy.               |
|   2   | `strategyDelegateFeeRate` |  `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate.                  |
|   3   | `strategyProtocolFeeRate` |  `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury.                     |
|   4   |         `yieldCap`        | `uint256` |   `uint256`   | Maximum amount of assets that can be realized as yield in a single call. |

