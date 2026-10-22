# StrategyManager



## Functions

### `acceptStrategyDelegate`

Accepts the role of strategy delegate.

```solidity
    function acceptStrategyDelegate()
        nonpayable;
```



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



### `assetsOf`

Returns the assets that belong to a given pool manager based on its share of total shares.

```solidity
    function assetsOf(
        address poolManager
    )
        view
        returns (
            uint256 assets
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                  |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                                     |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Assets currently belonging to the pool manager. |



### `assetsUnderManagement`

Returns the total assets currently under management by the underlying strategy.

```solidity
    function assetsUnderManagement()
        view
        returns (
            uint256 assetsUnderManagement
        );
```

#### Return Values:

| Index |           Name          |    Type   | Internal Type | Description                        |
| :---: | :---------------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `assetsUnderManagement` | `uint256` |   `uint256`   | The total assets under management. |



### `availableToWithdraw`

Returns the assets currently available to withdraw from the underlying strategy.

```solidity
    function availableToWithdraw()
        view
        returns (
            uint256 availableToWithdraw
        );
```

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                   |
| :---: | :-------------------: | :-------: | :-----------: | ----------------------------- |
|   0   | `availableToWithdraw` | `uint256` |   `uint256`   | Assets available to withdraw. |



### `cancelRedemption`

Cancels a previously queued redemption, reducing the pool manager's pending shares.

```solidity
    function cancelRedemption(
        address poolManager,
        uint256 shares
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                      |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------------------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager whose redemption is being cancelled. |
|   1   |    `shares`   | `uint256` |   `uint256`   | Number of pending shares to cancel.                              |



### `completeConfiguration`

Complete the configuration.

```solidity
    function completeConfiguration(
        uint256 bootstrapAssets,
        bytes bootstrapFundingData
    )
        nonpayable;
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description                                                                        |
| :---: | :--------------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------- |
|   0   |    `bootstrapAssets`   | `uint256` |   `uint256`   | Amount of assets to use to bootstrap the strategy manager.                         |
|   1   | `bootstrapFundingData` |  `bytes`  |    `bytes`    | Arbitrary data forwarded to the underlying strategy on \`fundUnderlyingStrategy\`. |



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



### `convertToAssets`

Converts shares to assets based on the current total assets and total shares.

```solidity
    function convertToAssets(
        uint256 shares
    )
        view
        returns (
            uint256 assets
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                  |
| :---: | :------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Number of shares to convert. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                             |
| :---: | :------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Number of assets converted from shares. |



### `convertToExitAssets`

Converts shares to assets using the exit rate, which subtracts unrealized losses from total assets.

```solidity
    function convertToExitAssets(
        uint256 shares
    )
        view
        returns (
            uint256 assets
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                  |
| :---: | :------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Number of shares to convert. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                                  |
| :---: | :------: | :-------: | :-----------: | -------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Number of exit assets converted from shares. |



### `convertToExitShares`

Converts assets to shares using the exit rate, which subtracts unrealized losses from total assets.

```solidity
    function convertToExitShares(
        uint256 assets
    )
        view
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                  |
| :---: | :------: | :-------: | :-----------: | ---------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Number of assets to convert. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                                  |
| :---: | :------: | :-------: | :-----------: | -------------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Number of shares converted from exit assets. |



### `convertToShares`

Converts assets to shares based on the current total assets and total shares.

```solidity
    function convertToShares(
        uint256 assets
    )
        view
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                  |
| :---: | :------: | :-------: | :-----------: | ---------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Number of assets to convert. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                             |
| :---: | :------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Number of shares converted from assets. |



### `factory`

The address of the proxy factory.

```solidity
    function factory()
        view
        returns (
            address factory_
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `factory_` | `address` |   `address`   |             |



### `fundStrategyManager`

Pulls assets from a pool manager into the underlying strategy and credits the pool manager with shares. If a non-zero cap is set for the pool manager (see \`setPoolManagerCap\`), the resulting asset position must not exceed it. A cap of zero is treated as unset and imposes no limit. A cap of \`type(uint256).max\` blocks the pool manager entirely, so any funding reverts.

```solidity
    function fundStrategyManager(
        address poolManager,
        uint256 assetsIn,
        bytes data
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                                        |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------------------------------------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager being funded.                                          |
|   1   |   `assetsIn`  | `uint256` |   `uint256`   | Amount of assets to pull from the pool.                                            |
|   2   |     `data`    |  `bytes`  |    `bytes`    | Arbitrary data forwarded to the underlying strategy on \`fundUnderlyingStrategy\`. |



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

| Index |    Name   |    Type   | Internal Type | Description                            |
| :---: | :-------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `globals` | `address` |   `address`   | Address of the Maple globals contract. |



### `implementation`

The address of the implementation contract being proxied.

```solidity
    function implementation()
        view
        returns (
            address implementation_
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `implementation_` | `address` |   `address`   |             |



### `isAssetSupported`

Returns whether the given asset is supported by the strategy manager.

```solidity
    function isAssetSupported(
        address asset
    )
        view
        returns (
            bool isSupported
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                    |
| :---: | :-----: | :-------: | :-----------: | ------------------------------ |
|   0   | `asset` | `address` |   `address`   | Address of the asset to query. |

#### Return Values:

| Index |      Name     |  Type  | Internal Type | Description                                      |
| :---: | :-----------: | :----: | :-----------: | ------------------------------------------------ |
|   0   | `isSupported` | `bool` |     `bool`    | True if the strategy manager supports \`asset\`. |



### `migrate`

Modifies the proxy's storage by delegate-calling a migrator contract with some arguments. Access control logic critical since caller can force a selfdestruct via a malicious \`migrator\_\` which is delegatecalled.

```solidity
    function migrate(
        address migrator_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                      |
| :---: | :----------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |  `migrator_` | `address` |   `address`   | The address of a migrator contract.              |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | Some encoded arguments to use for the migration. |



### `multicall`

Allows EOAs to batch admin calls.

```solidity
    function multicall(
        bytes[] data
    )
        nonpayable;
```

#### Parameters:

| Index |  Name  |    Type   | Internal Type | Description        |
| :---: | :----: | :-------: | :-----------: | ------------------ |
|   0   | `data` | `bytes[]` |   `bytes[]`   | Array of calldata. |



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



### `processRedemption`

Process a pending redemption. Withdraws from underlying strategy and sends assets directly to pool.

```solidity
    function processRedemption(
        address poolManager,
        uint256 shares,
        bytes data
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                                                |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------------------------------------------------ |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager whose redemption to process.                                   |
|   1   |    `shares`   | `uint256` |   `uint256`   | Amount of shares to process.                                                               |
|   2   |     `data`    |  `bytes`  |    `bytes`    | Arbitrary data forwarded to the underlying strategy on \`withdrawFromUnderlyingStrategy\`. |



### `requestRedeem`

Requests a redemption of shares for a pool manager. Does not reduce the pool manager's share balance until the redemption is processed.

```solidity
    function requestRedeem(
        address poolManager,
        uint256 shares
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                            |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------------ |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager requesting the redemption. |
|   1   |    `shares`   | `uint256` |   `uint256`   | Number of shares to queue for redemption.              |



### `securityAdmin`

Returns the address of the security admin.

```solidity
    function securityAdmin()
        view
        returns (
            address securityAdmin
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                    |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `securityAdmin` | `address` |   `address`   | Address of the security admin. |



### `setActive`

Sets the strategy manager to be active or inactive.

```solidity
    function setActive(
        bool active
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |  Type  | Internal Type | Description                             |
| :---: | :------: | :----: | :-----------: | --------------------------------------- |
|   0   | `active` | `bool` |     `bool`    | Whether the strategy manager is active. |



### `setImplementation`

Modifies the proxy's implementation address.

```solidity
    function setImplementation(
        address newImplementation_
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                |
| :---: | :------------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `newImplementation_` | `address` |   `address`   | The address of an implementation contract. |



### `setPendingStrategyDelegate`

Sets an address as the pending strategy delegate. Passing address(0) cancels a pending transfer.

```solidity
    function setPendingStrategyDelegate(
        address pendingStrategyDelegate
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |    Type   | Internal Type | Description                           |
| :---: | :-----------------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `pendingStrategyDelegate` | `address` |   `address`   | Address of the new strategy delegate. |



### `setPoolManagerCap`

Sets the maximum asset position a pool manager can have in the strategy manager. Setting the cap to zero unsets it, meaning the pool manager has no limit and funding is bounded only by the strategy liquidity cap. Setting the cap to \`type(uint256).max\` blocks the pool manager entirely.

```solidity
    function setPoolManagerCap(
        address poolManager,
        uint256 cap
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                                                                                                           |
| :---: | :-----------: | :-------: | :-----------: | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager whose cap is being set.                                                                                                   |
|   1   |     `cap`     | `uint256` |   `uint256`   | Maximum asset position the pool manager can have in the strategy manager. Zero means no cap, \`type(uint256).max\` means the pool manager is blocked. |



### `setStrategyLiquidityCap`

Sets the maximum total asset position the strategy manager can have.

```solidity
    function setStrategyLiquidityCap(
        uint256 cap
    )
        nonpayable;
```

#### Parameters:

| Index |  Name |    Type   | Internal Type | Description                                                 |
| :---: | :---: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   | `cap` | `uint256` |   `uint256`   | Maximum total asset position the strategy manager can have. |



### `setUnderlyingStrategy`

Sets the underlying strategy during deployment before configuration is complete.

```solidity
    function setUnderlyingStrategy(
        address underlyingStrategy
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                         |
| :---: | :------------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `underlyingStrategy` | `address` |   `address`   | Address of the underlying strategy. |



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



### `unrealizedLosses`

Returns the total unrealized losses reported by the underlying strategy, clamped to assets under management.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint256 unrealizedLosses
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                                 |
| :---: | :----------------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   | `unrealizedLosses` | `uint256` |   `uint256`   | Total unrealized losses, capped at assets under management. |



### `unrealizedLossesOf`

Returns the unrealized losses attributed to a given pool manager based on its share of total shares.

```solidity
    function unrealizedLossesOf(
        address poolManager
    )
        view
        returns (
            uint256 unrealizedLosses
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                  |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                       |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   | `unrealizedLosses` | `uint256` |   `uint256`   | Unrealized losses attributed to the pool manager. |



### `upgrade`

Upgrades a contract implementation to a specific version. Access control logic critical since caller can force a selfdestruct via a malicious \`migrator\_\` which is delegatecalled.

```solidity
    function upgrade(
        uint256 toVersion_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                    |
| :---: | :----------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `toVersion_` | `uint256` |   `uint256`   | The version to upgrade to.                     |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | Some encoded arguments to use for the upgrade. |



## Events

### `PendingStrategyDelegateAccepted`

Emitted when the pending strategy delegate accepts the ownership transfer.

```solidity
    event PendingStrategyDelegateAccepted(
        address previousStrategyDelegate,
        address newStrategyDelegate
    );
```

#### Parameters:

| Index |            Name            |    Type   | Internal Type | Description                                |
| :---: | :------------------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `previousStrategyDelegate` | `address` |   `address`   | Address of the previous strategy delegate. |
|   1   |    `newStrategyDelegate`   | `address` |   `address`   | Address of the new strategy delegate.      |



### `PendingStrategyDelegateSet`

Emitted when the pending strategy delegate is set.

```solidity
    event PendingStrategyDelegateSet(
        address pendingStrategyDelegate
    );
```

#### Parameters:

| Index |            Name           |    Type   | Internal Type | Description                               |
| :---: | :-----------------------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `pendingStrategyDelegate` | `address` |   `address`   | Address of the pending strategy delegate. |



### `PoolManagerCapSet`

Emitted when a pool manager's maximum asset position is set. Zero means no cap is set, and \`type(uint256).max\` means the pool manager is blocked entirely.

```solidity
    event PoolManagerCapSet(
        address poolManager,
        uint256 cap
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                                                                                                                              |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager whose cap was set.                                                                                                                           |
|   1   |     `cap`     | `uint256` |   `uint256`   | The maximum asset position the pool manager is authorized to hold, with Zero meaning no cap is set and type(uint256).max meaning the pool manager is completely blocked. |



### `RedemptionCancelled`

Emitted when a pending redemption is cancelled for a pool manager.

```solidity
    event RedemptionCancelled(
        address poolManager,
        uint256 sharesCancelled
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                                    |
| :---: | :---------------: | :-------: | :-----------: | -------------------------------------------------------------- |
|   0   |   `poolManager`   | `address` |   `address`   | Address of the pool manager whose pending shares were reduced. |
|   1   | `sharesCancelled` | `uint256` |   `uint256`   | Number of pending shares cancelled.                            |



### `RedemptionProcessed`

Emitted when a pending redemption is processed for a pool manager.

```solidity
    event RedemptionProcessed(
        address poolManager,
        uint256 sharesProcessed,
        uint256 assetsWithdrawn
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                              |
| :---: | :---------------: | :-------: | :-----------: | -------------------------------------------------------- |
|   0   |   `poolManager`   | `address` |   `address`   | Address of the pool manager whose shares were redeemed.  |
|   1   | `sharesProcessed` | `uint256` |   `uint256`   | Number of shares processed for redemption.               |
|   2   | `assetsWithdrawn` | `uint256` |   `uint256`   | Number of assets withdrawn from the underlying strategy. |



### `RedemptionRequested`

Emitted when a redemption is requested for a pool manager.

```solidity
    event RedemptionRequested(
        address poolManager,
        uint256 sharesRequested
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                                               |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------------------------------------- |
|   0   |   `poolManager`   | `address` |   `address`   | Address of the pool manager whose shares are being queued for redemption. |
|   1   | `sharesRequested` | `uint256` |   `uint256`   | Number of shares queued for redemption.                                   |



### `SetAsActive`

Emitted when the strategy manager is set to be active or inactive.

```solidity
    event SetAsActive(
        bool active
    );
```

#### Parameters:

| Index |   Name   |  Type  | Internal Type | Description                             |
| :---: | :------: | :----: | :-----------: | --------------------------------------- |
|   0   | `active` | `bool` |     `bool`    | Whether the strategy manager is active. |



### `StrategyLiquidityCapSet`

Emitted when the strategy manager's maximum total asset position is set.

```solidity
    event StrategyLiquidityCapSet(
        uint256 cap
    );
```

#### Parameters:

| Index |  Name |    Type   | Internal Type | Description                                                                  |
| :---: | :---: | :-------: | :-----------: | ---------------------------------------------------------------------------- |
|   0   | `cap` | `uint256` |   `uint256`   | The maximum total asset position the strategy manager is authorized to hold. |



### `StrategyManagerConfigurationComplete`

Emitted when the strategy manager configuration is marked as complete.

```solidity
    event StrategyManagerConfigurationComplete();
```



### `StrategyManagerFunded`

Emitted when a pool manager funds the strategy manager.

```solidity
    event StrategyManagerFunded(
        address poolManager,
        uint256 assetsIn,
        uint256 assetsDeposited,
        uint256 sharesMinted
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                              |
| :---: | :---------------: | :-------: | :-----------: | -------------------------------------------------------- |
|   0   |   `poolManager`   | `address` |   `address`   | Address of the pool manager that received shares.        |
|   1   |     `assetsIn`    | `uint256` |   `uint256`   | Amount of assets pulled from the pool.                   |
|   2   | `assetsDeposited` | `uint256` |   `uint256`   | Amount of assets deposited into the underlying strategy. |
|   3   |   `sharesMinted`  | `uint256` |   `uint256`   | Number of shares credited to the pool manager.           |



### `UnderlyingStrategySet`

Emitted when the underlying strategy is set.

```solidity
    event UnderlyingStrategySet(
        address underlyingStrategy
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                         |
| :---: | :------------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `underlyingStrategy` | `address` |   `address`   | Address of the underlying strategy. |



### `Upgraded`

The instance was upgraded.

```solidity
    event Upgraded(
        uint256 toVersion_,
        bytes arguments_
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                    |
| :---: | :----------: | :-------: | :-----------: | ------------------------------ |
|   0   | `toVersion_` | `uint256` |   `uint256`   | The new version of the loan.   |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | The upgrade arguments, if any. |

