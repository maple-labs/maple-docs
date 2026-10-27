# PoolManager



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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



### `acceptPoolDelegate`

Accepts the role of pool delegate.

```solidity
    function acceptPoolDelegate()
        nonpayable;
```



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



### `addStrategy`

Adds a new strategy. NOTE: The PoolManager address is encoded and prepended to the extraDeploymentData.

```solidity
    function addStrategy(
        address strategyFactory,
        bytes32 salt,
        bytes extraDeploymentData
    )
        nonpayable
        returns (
            address strategy
        );
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                                   |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------------------------------- |
|   0   |   `strategyFactory`   | `address` |   `address`   | The address of the strategy factory to use.                   |
|   1   |         `salt`        | `bytes32` |   `bytes32`   | The salt used by the factory to deploy the strategy instance. |
|   2   | `extraDeploymentData` |  `bytes`  |    `bytes`    | The data to construct the strategy.                           |

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                      |
| :---: | :--------: | :-------: | :-----------: | -------------------------------- |
|   0   | `strategy` | `address` |   `address`   | The address of the new strategy. |



### `addStrategyManager`

Registers an already-deployed strategy manager with the pool. Callable by any caller while the pool manager is not yet configured (typically during deployment). Once \`completeConfiguration()\` has been called, only the governor (through its timelock) may call this function.

```solidity
    function addStrategyManager(
        address strategyManager
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                          |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `strategyManager` | `address` |   `address`   | The address of the strategy manager. |



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



### `canCall`

Checks if a scheduled call can be executed.

```solidity
    function canCall(
        bytes32 functionId,
        address caller,
        bytes data
    )
        view
        returns (
            bool canCall,
            string errorMessage
        );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                |
| :---: | :----------: | :-------: | :-----------: | -------------------------- |
|   0   | `functionId` | `bytes32` |   `bytes32`   | The function to check.     |
|   1   |   `caller`   | `address` |   `address`   | The address of the caller. |
|   2   |    `data`    |  `bytes`  |    `bytes`    | The data of the call.      |

#### Return Values:

| Index |      Name      |   Type   | Internal Type | Description                                        |
| :---: | :------------: | :------: | :-----------: | -------------------------------------------------- |
|   0   |    `canCall`   |  `bool`  |     `bool`    | True if the call can be executed, false otherwise. |
|   1   | `errorMessage` | `string` |    `string`   | The error message if the call cannot be executed.  |



### `completeConfiguration`

Complete the configuration.

```solidity
    function completeConfiguration()
        nonpayable;
```



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



### `convertToExitShares`

Returns the amount of exit shares for the input amount.

```solidity
    function convertToExitShares(
        uint256 amount
    )
        view
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description             |
| :---: | :------: | :-------: | :-----------: | ----------------------- |
|   0   | `amount` | `uint256` |   `uint256`   | Address of the account. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                         |
| :---: | :------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Amount of shares able to be exited. |



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



### `getEscrowParams`

Gets the information of escrowed shares.

```solidity
    function getEscrowParams(
        address owner,
        uint256 shares
    )
        view
        returns (
            uint256 escrowShares,
            address destination
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                     |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   |  `owner` | `address` |   `address`   | The address of the owner of the shares.         |
|   1   | `shares` | `uint256` |   `uint256`   | The amount of shares to get the information of. |

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                     |
| :---: | :------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `escrowShares` | `uint256` |   `uint256`   | The amount of escrowed shares.  |
|   1   |  `destination` | `address` |   `address`   | The address of the destination. |



### `globals`

Gets the address of the globals.

```solidity
    function globals()
        view
        returns (
            address globals
        );
```

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                 |
| :---: | :-------: | :-------: | :-----------: | --------------------------- |
|   0   | `globals` | `address` |   `address`   | The address of the globals. |



### `governor`

Gets the address of the governor.

```solidity
    function governor()
        view
        returns (
            address governor
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                  |
| :---: | :--------: | :-------: | :-----------: | ---------------------------- |
|   0   | `governor` | `address` |   `address`   | The address of the governor. |



### `hasSufficientCover`

Returns whether the pool has sufficient cover. Pool delegate cover is deprecated, so this always returns true.

```solidity
    function hasSufficientCover()
        pure
        returns (
            bool hasSufficientCover
        );
```

#### Return Values:

| Index |         Name         |  Type  | Internal Type | Description |
| :---: | :------------------: | :----: | :-----------: | ----------- |
|   0   | `hasSufficientCover` | `bool` |     `bool`    | True.       |



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



### `isStrategy`

Returns whether or not the given address is a registered strategy. These are legacy strategies set to be deprecated in future for the new modular strategies.

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



### `maxDeposit`

Gets the amount of assets that can be deposited.

```solidity
    function maxDeposit(
        address receiver
    )
        view
        returns (
            uint256 maxAssets
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                           |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `receiver` | `address` |   `address`   | The address to check the deposit for. |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `maxAssets` | `uint256` |   `uint256`   | The maximum amount assets to deposit. |



### `maxMint`

Gets the amount of shares that can be minted.

```solidity
    function maxMint(
        address receiver
    )
        view
        returns (
            uint256 maxShares
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                        |
| :---: | :--------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `receiver` | `address` |   `address`   | The address to check the mint for. |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                        |
| :---: | :---------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `maxShares` | `uint256` |   `uint256`   | The maximum amount shares to mint. |



### `maxRedeem`

Gets the amount of shares that can be redeemed.

```solidity
    function maxRedeem(
        address owner
    )
        view
        returns (
            uint256 maxShares
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                              |
| :---: | :-----: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `owner` | `address` |   `address`   | The address to check the redemption for. |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                          |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `maxShares` | `uint256` |   `uint256`   | The maximum amount shares to redeem. |



### `maxWithdraw`

Gets the amount of assets that can be withdrawn.

```solidity
    function maxWithdraw(
        address owner
    )
        view
        returns (
            uint256 maxAssets
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                            |
| :---: | :-----: | :-------: | :-----------: | -------------------------------------- |
|   0   | `owner` | `address` |   `address`   | The address to check the withdraw for. |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                            |
| :---: | :---------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `maxAssets` | `uint256` |   `uint256`   | The maximum amount assets to withdraw. |



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



### `previewRedeem`

Gets the amount of shares that can be redeemed.

```solidity
    function previewRedeem(
        address owner,
        uint256 shares
    )
        view
        returns (
            uint256 assets
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                               |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |  `owner` | `address` |   `address`   | The address to check the redemption for.  |
|   1   | `shares` | `uint256` |   `uint256`   | The amount of requested shares to redeem. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                                                |
| :---: | :------: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | The amount of assets that will be returned for \`shares\`. |



### `previewWithdraw`

Gets the amount of assets that can be redeemed.

```solidity
    function previewWithdraw(
        address owner,
        uint256 assets
    )
        view
        returns (
            uint256 shares
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                               |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |  `owner` | `address` |   `address`   | The address to check the redemption for.  |
|   1   | `assets` | `uint256` |   `uint256`   | The amount of requested shares to redeem. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                                                |
| :---: | :------: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | The amount of assets that will be returned for \`assets\`. |



### `processRedeem`

Processes a redemptions of shares for assets from the pool.

```solidity
    function processRedeem(
        uint256 shares,
        address owner,
        address sender
    )
        nonpayable
        returns (
            uint256 redeemableShares,
            uint256 resultingAssets
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                   |
| :---: | :------: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | The amount of shares to redeem.               |
|   1   |  `owner` | `address` |   `address`   | The address of the owner of the shares.       |
|   2   | `sender` | `address` |   `address`   | The address of the sender of the redeem call. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                     |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `redeemableShares` | `uint256` |   `uint256`   | The amount of shares redeemed.  |
|   1   |  `resultingAssets` | `uint256` |   `uint256`   | The amount of assets withdrawn. |



### `processWithdraw`

Processes a redemptions of shares for assets from the pool.

```solidity
    function processWithdraw(
        uint256 assets,
        address owner,
        address sender
    )
        nonpayable
        returns (
            uint256 redeemableShares,
            uint256 resultingAssets
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                     |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | The amount of assets to withdraw.               |
|   1   |  `owner` | `address` |   `address`   | The address of the owner of the shares.         |
|   2   | `sender` | `address` |   `address`   | The address of the sender of the withdraw call. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                     |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `redeemableShares` | `uint256` |   `uint256`   | The amount of shares redeemed.  |
|   1   |  `resultingAssets` | `uint256` |   `uint256`   | The amount of assets withdrawn. |



### `removeShares`

Requests a redemption of shares from the pool.

```solidity
    function removeShares(
        uint256 shares,
        address owner
    )
        nonpayable
        returns (
            uint256 sharesReturned
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                             |
| :---: | :------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | The amount of shares to redeem.         |
|   1   |  `owner` | `address` |   `address`   | The address of the owner of the shares. |

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                     |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `sharesReturned` | `uint256` |   `uint256`   | The amount of shares withdrawn. |



### `removeStrategyManager`

Removes a strategy manager from the pool and clears its strategy cap. Only callable by the operational admin after this pool manager has no assets in the strategy manager.

```solidity
    function removeStrategyManager(
        address strategyManager
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                          |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `strategyManager` | `address` |   `address`   | The address of the strategy manager. |



### `requestFunds`

Strategy can request funds from the pool via the poolManager.

```solidity
    function requestFunds(
        address destination,
        uint256 amount
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                       |
| :---: | :-----------: | :-------: | :-----------: | --------------------------------- |
|   0   | `destination` | `address` |   `address`   | The address to send the funds to. |
|   1   |    `amount`   | `uint256` |   `uint256`   | Amount to fund the strategy with. |



### `requestRedeem`

Requests a redemption of shares from the pool.

```solidity
    function requestRedeem(
        uint256 shares,
        address owner,
        address sender
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                              |
| :---: | :------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | The amount of shares to redeem.          |
|   1   |  `owner` | `address` |   `address`   | The address of the owner of the shares.  |
|   2   | `sender` | `address` |   `address`   | The address of the sender of the shares. |



### `requestWithdraw`

Requests a withdrawal of assets from the pool.

```solidity
    function requestWithdraw(
        uint256 shares,
        uint256 assets,
        address owner,
        address sender
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                              |
| :---: | :------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | The amount of shares to redeem.          |
|   1   | `assets` | `uint256` |   `uint256`   | The amount of assets to withdraw.        |
|   2   |  `owner` | `address` |   `address`   | The address of the owner of the shares.  |
|   3   | `sender` | `address` |   `address`   | The address of the sender of the shares. |



### `setActive`

Sets a the pool to be active or inactive.

```solidity
    function setActive(
        bool active
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |  Type  | Internal Type | Description                 |
| :---: | :------: | :----: | :-----------: | --------------------------- |
|   0   | `active` | `bool` |     `bool`    | Whether the pool is active. |



### `setDelegateManagementFeeRate`

Sets the value for the delegate management fee rate.

```solidity
    function setDelegateManagementFeeRate(
        uint256 delegateManagementFeeRate
    )
        nonpayable;
```

#### Parameters:

| Index |             Name            |    Type   | Internal Type | Description                                     |
| :---: | :-------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `delegateManagementFeeRate` | `uint256` |   `uint256`   | The value for the delegate management fee rate. |



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



### `setLiquidityCap`

Sets the value for liquidity cap.

```solidity
    function setLiquidityCap(
        uint256 liquidityCap
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                  |
| :---: | :------------: | :-------: | :-----------: | ---------------------------- |
|   0   | `liquidityCap` | `uint256` |   `uint256`   | The value for liquidity cap. |



### `setPendingPoolDelegate`

Sets an address as the pending pool delegate. Passing address(0) cancels a pending transfer. Can only be called by the operational admin.

```solidity
    function setPendingPoolDelegate(
        address pendingPoolDelegate
    )
        nonpayable;
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                           |
| :---: | :-------------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `pendingPoolDelegate` | `address` |   `address`   | The address of the new pool delegate. |



### `setPoolPermissionManager`

Sets the address of the pool permission manager.

```solidity
    function setPoolPermissionManager(
        address poolPermission
    )
        nonpayable;
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                 |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `poolPermission` | `address` |   `address`   | The address of the pool permission manager. |



### `setStrategyCap`

Sets the pool's AUM exposure cap to a strategy or Strategy Manager. The address must be an instance of a valid strategy or Strategy Manager factory if the cap is non-zero.

```solidity
    function setStrategyCap(
        address strategy,
        uint256 cap
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                  |
| :---: | :--------: | :-------: | :-----------: | -------------------------------------------- |
|   0   | `strategy` | `address` |   `address`   | The address of the strategy.                 |
|   1   |    `cap`   | `uint256` |   `uint256`   | The pool's AUM exposure cap to the strategy. |



### `setWithdrawalManager`

Sets the address of the withdrawal manager.

```solidity
    function setWithdrawalManager(
        address withdrawalManager
    )
        nonpayable;
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                            |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `withdrawalManager` | `address` |   `address`   | The address of the withdrawal manager. |



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



### `strategyListLength`

Returns the length of the \`strategyList\`.

```solidity
    function strategyListLength()
        view
        returns (
            uint256 strategyListLength
        );
```

#### Return Values:

| Index |         Name         |    Type   | Internal Type | Description                         |
| :---: | :------------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `strategyListLength` | `uint256` |   `uint256`   | The length of the \`strategyList\`. |



### `totalAssets`

Returns the amount of total assets.

```solidity
    function totalAssets()
        view
        returns (
            uint256 totalAssets
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                |
| :---: | :-----------: | :-------: | :-----------: | -------------------------- |
|   0   | `totalAssets` | `uint256` |   `uint256`   | Amount of of total assets. |



### `triggerDefault`

Triggers the default of a loan held by the pool's loan manager.

```solidity
    function triggerDefault(
        address loan_
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                         |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------- |
|   0   | `loan_` | `address` |   `address`   | The address of the loan to default. |



### `unrealizedLosses`

Returns the sum of unrealized losses reported by every registered strategy and strategy manager.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint256 unrealizedLosses
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                                              |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------------------------------------ |
|   0   | `unrealizedLosses` | `uint256` |   `uint256`   | Aggregate unrealized losses across all strategies and strategy managers. |



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

### `CollateralLiquidationFinished`

Emitted when a collateral liquidations is finished.

```solidity
    event CollateralLiquidationFinished(
        address indexed loan_,
        uint256 unrealizedLosses_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                      |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------- |
|   0   |       `loan_`       | `address` |   `address`   | The address of the loan.         |
|   1   | `unrealizedLosses_` | `uint256` |   `uint256`   | The amount of unrealized losses. |



### `DelegateManagementFeeRateSet`

Emitted when a new management fee rate is set.

```solidity
    event DelegateManagementFeeRateSet(
        uint256 managementFeeRate
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                        |
| :---: | :-----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `managementFeeRate` | `uint256` |   `uint256`   | The amount of management fee rate. |



### `LiquidityCapSet`

Emitted when a new liquidity cap is set.

```solidity
    event LiquidityCapSet(
        uint256 liquidityCap
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                 |
| :---: | :------------: | :-------: | :-----------: | --------------------------- |
|   0   | `liquidityCap` | `uint256` |   `uint256`   | The value of liquidity cap. |



### `PendingDelegateAccepted`

Emitted when the pending pool delegate accepts the ownership transfer.

```solidity
    event PendingDelegateAccepted(
        address indexed previousDelegate,
        address indexed newDelegate
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                           |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `previousDelegate` | `address` |   `address`   | The address of the previous delegate. |
|   1   |    `newDelegate`   | `address` |   `address`   | The address of the new delegate.      |



### `PendingDelegateSet`

Emitted when the pending pool delegate is set.

```solidity
    event PendingDelegateSet(
        address indexed previousDelegate,
        address indexed newDelegate
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                           |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `previousDelegate` | `address` |   `address`   | The address of the previous delegate. |
|   1   |    `newDelegate`   | `address` |   `address`   | The address of the new delegate.      |



### `PoolConfigurationComplete`

Emitted when the pool configuration is marked as complete.

```solidity
    event PoolConfigurationComplete();
```



### `PoolPermissionManagerSet`

Emitted when the pool permission manager is set.

```solidity
    event PoolPermissionManagerSet(
        address indexed poolPermissionManager
    );
```

#### Parameters:

| Index |           Name          |    Type   | Internal Type | Description                                 |
| :---: | :---------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `poolPermissionManager` | `address` |   `address`   | The address of the pool permission manager. |



### `RedeemProcessed`

Emitted when a redemption of shares from the pool is processed.

```solidity
    event RedeemProcessed(
        address indexed owner,
        uint256 redeemableShares,
        uint256 resultingAssets
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                      |
| :---: | :----------------: | :-------: | :-----------: | -------------------------------- |
|   0   |       `owner`      | `address` |   `address`   | The owner of the shares.         |
|   1   | `redeemableShares` | `uint256` |   `uint256`   | The amount of redeemable shares. |
|   2   |  `resultingAssets` | `uint256` |   `uint256`   | The amount of assets redeemed.   |



### `RedeemRequested`

Emitted when a redemption of shares from the pool is requested.

```solidity
    event RedeemRequested(
        address indexed owner,
        uint256 shares
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                      |
| :---: | :------: | :-------: | :-----------: | -------------------------------- |
|   0   |  `owner` | `address` |   `address`   | The owner of the shares.         |
|   1   | `shares` | `uint256` |   `uint256`   | The amount of redeemable shares. |



### `SetAsActive`

Emitted when a pool is sets to be active or inactive.

```solidity
    event SetAsActive(
        bool active
    );
```

#### Parameters:

| Index |   Name   |  Type  | Internal Type | Description                 |
| :---: | :------: | :----: | :-----------: | --------------------------- |
|   0   | `active` | `bool` |     `bool`    | Whether the pool is active. |



### `SharesRemoved`

Emitted when shares are removed from the pool.

```solidity
    event SharesRemoved(
        address indexed owner,
        uint256 shares
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                             |
| :---: | :------: | :-------: | :-----------: | --------------------------------------- |
|   0   |  `owner` | `address` |   `address`   | The address of the owner of the shares. |
|   1   | `shares` | `uint256` |   `uint256`   | The amount of shares removed.           |



### `StrategyAdded`

Emitted when a new strategy is added.

```solidity
    event StrategyAdded(
        address indexed strategy
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                      |
| :---: | :--------: | :-------: | :-----------: | -------------------------------- |
|   0   | `strategy` | `address` |   `address`   | The address of the new strategy. |



### `StrategyCapSet`

Emitted when the pool's AUM exposure cap to a strategy is set.

```solidity
    event StrategyCapSet(
        address indexed strategy,
        uint256 cap
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                  |
| :---: | :--------: | :-------: | :-----------: | -------------------------------------------- |
|   0   | `strategy` | `address` |   `address`   | The address of the strategy.                 |
|   1   |    `cap`   | `uint256` |   `uint256`   | The pool's AUM exposure cap to the strategy. |



### `StrategyManagerAdded`

Emitted when a strategy manager is registered with the pool.

```solidity
    event StrategyManagerAdded(
        address indexed strategyManager
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                          |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `strategyManager` | `address` |   `address`   | The address of the strategy manager. |



### `StrategyManagerRemoved`

Emitted when a strategy manager is removed from the pool.

```solidity
    event StrategyManagerRemoved(
        address indexed strategyManager
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                          |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `strategyManager` | `address` |   `address`   | The address of the strategy manager. |



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



### `WithdrawalManagerSet`

Emitted when the withdrawal manager is set.

```solidity
    event WithdrawalManagerSet(
        address indexed withdrawalManager
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                            |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `withdrawalManager` | `address` |   `address`   | The address of the withdrawal manager. |

