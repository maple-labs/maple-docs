# AllocationStrategy



## Functions

### `STRATEGY_TYPE`

```solidity
    function STRATEGY_TYPE()
        view
        returns (
            string
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `string` |    `string`   |             |



### `assetsUnderManagement`

Returns the total amount of assets managed by the strategy. Includes all deployed assets and recorded assets in the strategy, but doesn't include unrealized yield.

```solidity
    function assetsUnderManagement()
        view
        returns (
            uint256 assetsUnderManagement
        );
```

#### Return Values:

| Index |           Name          |    Type   | Internal Type | Description                           |
| :---: | :---------------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `assetsUnderManagement` | `uint256` |   `uint256`   | Total assets managed by the strategy. |



### `availableToWithdraw`

Returns the amount of assets available for deployment or withdrawal. Equal to the recorded assets less the unrealized assets still sitting in the yield buffer. Assets that have not been recorded by the strategy are never available.

```solidity
    function availableToWithdraw()
        view
        returns (
            uint256 availableToWithdraw
        );
```

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                                    |
| :---: | :-------------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `availableToWithdraw` | `uint256` |   `uint256`   | Assets available for deployment or withdrawal. |



### `cancelYield`

Cancels unrealized yield from the yield buffer and transfers it to the recipient. Callable only by the strategy delegate or security admin. Already-realized yield cannot be cancelled. Remaining unrealized yield continues on its original schedule.

```solidity
    function cancelYield(
        uint256 assets,
        address recipient
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                                                                                   |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------------------------------------------------------------------------- |
|   0   |   `assets`  | `uint256` |   `uint256`   | Amount of unrealized yield to cancel. Can use \`type(uint256).max\` to cancel all remaining unrealized yield. |
|   1   | `recipient` | `address` |   `address`   | Address to receive the cancelled yield. Must be a valid managed wallet on globals.                            |



### `deployAssets`

Transfers assets from the strategy to the caller. Caller must be a valid managed wallet on MapleGlobals. Caller must have permission to deploy assets. Cannot deploy more assets than allowed by the deployment cap. Cannot deploy more assets than are currently available in the strategy.

```solidity
    function deployAssets(
        uint256 assets,
        bytes metadata
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                       |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   |  `assets`  | `uint256` |   `uint256`   | Amount of assets to deploy.                       |
|   1   | `metadata` |  `bytes`  |    `bytes`    | Optional metadata associated with the deployment. |



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



### `fundUnderlyingStrategy`

Acknowledges assets have been funded to the strategy. Callable only by the strategy manager.

```solidity
    function fundUnderlyingStrategy(
        uint256 assetsIn,
        bytes data
    )
        nonpayable
        returns (
            uint256 assetsOut
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                                  |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------------------ |
|   0   | `assetsIn` | `uint256` |   `uint256`   | Amount of assets that have been transferred to the strategy. |
|   1   |   `data`   |  `bytes`  |    `bytes`    | Unused, but reserved for future strategy-specific calldata.  |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                                                                                         |
| :---: | :---------: | :-------: | :-----------: | --------------------------------------------------------------------------------------------------- |
|   0   | `assetsOut` | `uint256` |   `uint256`   | Value of transferred assets after the funding. Equal to the amount of assets that were transferred. |



### `globals`

Returns the address of the Maple Globals contract.

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
|   0   | `globals` | `address` |   `address`   | Address of the Maple Globals contract. |



### `impair`

Increases the amount of impaired assets. Callable only by the strategy delegate or operational admin.

```solidity
    function impair(
        uint256 assets
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                 |
| :---: | :------: | :-------: | :-----------: | --------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Amount of assets to impair. |



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



### `mapleTreasury`

Returns the Maple treasury address which receives the protocol fees.

```solidity
    function mapleTreasury()
        view
        returns (
            address mapleTreasury
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                    |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `mapleTreasury` | `address` |   `address`   | Address of the Maple treasury. |



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



### `realizedYield`

Returns the current amount of yield assets that has been realized.

```solidity
    function realizedYield()
        view
        returns (
            uint256 realizedYield
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                      |
| :---: | :-------------: | :-------: | :-----------: | -------------------------------- |
|   0   | `realizedYield` | `uint256` |   `uint256`   | Amount of yield assets realized. |



### `realizeYield`

Transfers assets from the caller to the yield buffer. Caller must be a valid managed wallet on MapleGlobals. Caller must have permission to realize yield. Can only be called once per hour across all managed wallets. Zero assets is valid and only updates the duration of the yield buffer. Zero duration is valid and causes all yield to be realized immediately. Cannot realize more assets than allowed by the yield cap.

```solidity
    function realizeYield(
        uint256 assets,
        uint32 duration,
        bytes metadata
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                       |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   |  `assets`  | `uint256` |   `uint256`   | Amount of assets to realize as yield.             |
|   1   | `duration` |  `uint32` |    `uint32`   | Duration over which to realize assets in seconds. |
|   2   | `metadata` |  `bytes`  |    `bytes`    | Optional metadata associated with the yield.      |



### `recognizeLoss`

Recognizes a loss against a deployer, reducing their deployed amount and total outstanding assets. Callable only by the strategy delegate or operational admin. Cannot exceed the deployer's currently deployed amount.

```solidity
    function recognizeLoss(
        uint256 assets,
        address deployer
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                        |
| :---: | :--------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   |  `assets`  | `uint256` |   `uint256`   | Amount of assets to recognize as lost.             |
|   1   | `deployer` | `address` |   `address`   | Address of the deployer the loss is attributed to. |



### `recognizeLossAndRemoveImpairment`

Recognizes a loss and reduces an impairment simultaneously. Callable only by the strategy delegate or operational admin. Cannot exceed the deployer's currently deployed amount.

```solidity
    function recognizeLossAndRemoveImpairment(
        uint256 assetsLost,
        uint256 assetsUnimpaired,
        address deployer
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                                        |
| :---: | :----------------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   |    `assetsLost`    | `uint256` |   `uint256`   | Amount of assets to recognize as lost.             |
|   1   | `assetsUnimpaired` | `uint256` |   `uint256`   | Amount of assets to unimpair.                      |
|   2   |     `deployer`     | `address` |   `address`   | Address of the deployer the loss is attributed to. |



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



### `removeImpairment`

Decreases the amount of impaired assets. Callable only by the strategy delegate or operational admin.

```solidity
    function removeImpairment(
        uint256 assets
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                   |
| :---: | :------: | :-------: | :-----------: | ----------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Amount of assets to unimpair. |



### `returnAssets`

Transfers assets from the caller to the strategy. Caller must be a valid managed wallet on MapleGlobals. Caller must have permission to return assets. Cannot return more assets than were already deployed.

```solidity
    function returnAssets(
        uint256 assets,
        address onBehalfOf,
        bytes metadata
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                                                             |
| :---: | :----------: | :-------: | :-----------: | --------------------------------------------------------------------------------------- |
|   0   |   `assets`   | `uint256` |   `uint256`   | Amount of assets to return.                                                             |
|   1   | `onBehalfOf` | `address` |   `address`   | Address that will be credited as having returned the assets. Can be the caller address. |
|   2   |  `metadata`  |  `bytes`  |    `bytes`    | Optional metadata associated with assets being returned.                                |



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



### `setDeploymentCaps`

Sets the deployment cap for a list of managed wallets. Callable only by the strategy delegate or security admin.

```solidity
    function setDeploymentCaps(
        address[] accounts,
        uint256[] amounts
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |     Type    | Internal Type | Description                                        |
| :---: | :--------: | :---------: | :-----------: | -------------------------------------------------- |
|   0   | `accounts` | `address[]` |  `address[]`  | Managed wallets to set deployment caps for.        |
|   1   |  `amounts` | `uint256[]` |  `uint256[]`  | New deployment cap to set for each managed wallet. |



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



### `setMetadata`

Updates the metadata of the allocation strategy. Callable only by the strategy delegate or operational admin.

```solidity
    function setMetadata(
        string metadata
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |   Type   | Internal Type | Description                                     |
| :---: | :--------: | :------: | :-----------: | ----------------------------------------------- |
|   0   | `metadata` | `string` |    `string`   | Optional metadata associated with the strategy. |



### `setPermissions`

Sets permissions for a list of managed wallets. Callable only by the strategy delegate or security admin. Addresses must be valid managed wallets on MapleGlobals to receive any enabled permission.

```solidity
    function setPermissions(
        address[] accounts,
        bool[] canDeployAssets,
        bool[] canReturnAssets,
        bool[] canRealizeYield
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |     Type    | Internal Type | Description                                      |
| :---: | :---------------: | :---------: | :-----------: | ------------------------------------------------ |
|   0   |     `accounts`    | `address[]` |  `address[]`  | Managed wallets to set permissions for.          |
|   1   | `canDeployAssets` |   `bool[]`  |    `bool[]`   | Defines if each address can call deployAssets(). |
|   2   | `canReturnAssets` |   `bool[]`  |    `bool[]`   | Defines if each address can call returnAssets(). |
|   3   | `canRealizeYield` |   `bool[]`  |    `bool[]`   | Defines if each address can call realizeYield(). |



### `setStrategyDelegateFeeRate`

Sets the percentage of yield collected by the strategy delegate. Callable only by the strategy delegate. The combined strategy delegate and protocol fee rates cannot exceed 1e6.

```solidity
    function setStrategyDelegateFeeRate(
        uint32 strategyDelegateFeeRate
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                                 |
| :---: | :-----------------------: | :------: | :-----------: | ----------------------------------------------------------------------------------------------------------- |
|   0   | `strategyDelegateFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate, defined with 6 decimals of precision (1e6 == 100%). |



### `setStrategyProtocolFeeRate`

Sets the percentage of yield collected by the Maple treasury. Callable only by protocol admins. The combined strategy delegate and protocol fee rates cannot exceed 1e6.

```solidity
    function setStrategyProtocolFeeRate(
        uint32 strategyProtocolFeeRate
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                              |
| :---: | :-----------------------: | :------: | :-----------: | -------------------------------------------------------------------------------------------------------- |
|   0   | `strategyProtocolFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury, defined with 6 decimals of precision (1e6 == 100%). |



### `setYieldCap`

Sets the maximum amount of assets that can be supplied as the \`assets\` parameter of realizeYield(). Callable only by the strategy delegate or operational admin.

```solidity
    function setYieldCap(
        uint256 yieldCap
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                                              |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------------------------------ |
|   0   | `yieldCap` | `uint256` |   `uint256`   | Maximum amount of assets that can be realized as yield in a single call. |



### `skim`

Transfers all assets held by the strategy that have not been recorded to a given recipient. Callable only by the strategy delegate or operational admin. Does not affect the recorded assets, and therefore does not affect the assets under management.

```solidity
    function skim(
        address recipient
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                      |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   | `recipient` | `address` |   `address`   | Address that will receive the unrecorded assets. |



### `strategyDelegate`

Returns the strategy delegate that receives the delegate's share of accrued yield for the bound strategy manager.

```solidity
    function strategyDelegate()
        view
        returns (
            address strategyDelegate
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                       |
| :---: | :----------------: | :-------: | :-----------: | --------------------------------- |
|   0   | `strategyDelegate` | `address` |   `address`   | Address of the strategy delegate. |



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



### `unrealizedLosses`

Returns the amount of unrealized losses. Equal to the amount of impaired assets capped to the AUM of the strategy.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint256 unrealizedLosses
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                  |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------- |
|   0   | `unrealizedLosses` | `uint256` |   `uint256`   | Amount of unrealized losses. |



### `unrealizedYield`

Returns the current amount of yield assets that has not been realized.

```solidity
    function unrealizedYield()
        view
        returns (
            uint256 unrealizedYield
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                              |
| :---: | :---------------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `unrealizedYield` | `uint256` |   `uint256`   | Amount of yield assets not yet realized. |



### `unrecordedAssets`

Returns the amount of assets held by the strategy that have not been recorded. Equal to the balance of the funds asset less the recorded assets, clamping at zero.

```solidity
    function unrecordedAssets()
        view
        returns (
            uint256 unrecordedAssets
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                                        |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------------------------------ |
|   0   | `unrecordedAssets` | `uint256` |   `uint256`   | Amount of assets held by the strategy that have not been recorded. |



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



### `withdrawFromUnderlyingStrategy`

Withdraws assets from the strategy to a specific address. Callable only by the strategy manager. Only assets sitting in the allocation strategy can be withdrawn.

```solidity
    function withdrawFromUnderlyingStrategy(
        address destination,
        uint256 assets,
        bytes data
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                 |
| :---: | :-----------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   | `destination` | `address` |   `address`   | Address to send the assets to.                              |
|   1   |    `assets`   | `uint256` |   `uint256`   | Amount of assets to withdraw.                               |
|   2   |     `data`    |  `bytes`  |    `bytes`    | Unused, but reserved for future strategy-specific calldata. |



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



### `yieldCooldown`

Returns the number of seconds remaining until yield can be realized again.

```solidity
    function yieldCooldown()
        view
        returns (
            uint256 cooldown
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                                               |
| :---: | :--------: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   | `cooldown` | `uint256` |   `uint256`   | Number of seconds remaining in the yield cooldown period. |



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

### `AssetsDeployed`

Emitted when assets are deployed.

```solidity
    event AssetsDeployed(
        address deployer,
        uint256 assets,
        uint256 recordedAssets,
        bytes metadata
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                                             |
| :---: | :--------------: | :-------: | :-----------: | ----------------------------------------------------------------------- |
|   0   |    `deployer`    | `address` |   `address`   | Address that deployed the assets.                                       |
|   1   |     `assets`     | `uint256` |   `uint256`   | Amount of assets deployed.                                              |
|   2   | `recordedAssets` | `uint256` |   `uint256`   | Amount of assets recorded as held by the strategy after the deployment. |
|   3   |    `metadata`    |  `bytes`  |    `bytes`    | Optional metadata associated with the deployment.                       |



### `AssetsReturned`

Emitted when deployed assets are returned to the strategy.

```solidity
    event AssetsReturned(
        address caller,
        address onBehalfOf,
        uint256 assets,
        uint256 recordedAssets,
        bytes metadata
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                                         |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------------------------------------- |
|   0   |     `caller`     | `address` |   `address`   | Address that transferred the assets back.                           |
|   1   |   `onBehalfOf`   | `address` |   `address`   | Address to which the returned assets were credited.                 |
|   2   |     `assets`     | `uint256` |   `uint256`   | Amount of assets returned.                                          |
|   3   | `recordedAssets` | `uint256` |   `uint256`   | Amount of assets recorded as held by the strategy after the return. |
|   4   |    `metadata`    |  `bytes`  |    `bytes`    | Optional metadata associated with the repayment.                    |



### `AssetsSkimmed`

Emitted when unrecorded assets are skimmed from the strategy.

```solidity
    event AssetsSkimmed(
        address recipient,
        uint256 assets
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                               |
| :---: | :---------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `recipient` | `address` |   `address`   | Address that received the skimmed assets. |
|   1   |   `assets`  | `uint256` |   `uint256`   | Amount of assets skimmed.                 |



### `DeploymentCapSet`

Emitted when the deployment cap of a managed wallet is set.

```solidity
    event DeploymentCapSet(
        address account,
        uint256 deploymentCap
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                                |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   |    `account`    | `address` |   `address`   | Managed wallet the cap was set for.        |
|   1   | `deploymentCap` | `uint256` |   `uint256`   | New deployment cap for the managed wallet. |



### `Impaired`

Emitted when assets are impaired.

```solidity
    event Impaired(
        uint256 assets
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                          |
| :---: | :------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `assets` | `uint256` |   `uint256`   | Amount of assets that were impaired. |



### `ImpairmentRemoved`

Emitted when assets are unimpaired.

```solidity
    event ImpairmentRemoved(
        uint256 assets
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                            |
| :---: | :------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Amount of assets that were unimpaired. |



### `LossRecognized`

Emitted when a loss is recognized against a deployer.

```solidity
    event LossRecognized(
        address caller,
        address deployer,
        uint256 assets
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                        |
| :---: | :--------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   |  `caller`  | `address` |   `address`   | Address that called recognizeLoss.                 |
|   1   | `deployer` | `address` |   `address`   | Address of the deployer the loss is attributed to. |
|   2   |  `assets`  | `uint256` |   `uint256`   | Amount of assets recognized as lost.               |



### `PermissionSet`

Emitted when permissions are set for a managed wallet.

```solidity
    event PermissionSet(
        address account,
        bool canDeployAssets,
        bool canReturnAssets,
        bool canRealizeYield
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                     |
| :---: | :---------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   |     `account`     | `address` |   `address`   | Managed wallet the permissions were set for.    |
|   1   | `canDeployAssets` |   `bool`  |     `bool`    | Defines if the address can call deployAssets(). |
|   2   | `canReturnAssets` |   `bool`  |     `bool`    | Defines if the address can call returnAssets(). |
|   3   | `canRealizeYield` |   `bool`  |     `bool`    | Defines if the address can call realizeYield(). |



### `StrategyDelegateFeeRateSet`

Emitted when the strategy delegate fee rate is set.

```solidity
    event StrategyDelegateFeeRateSet(
        uint32 strategyDelegateFeeRate
    );
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                                 |
| :---: | :-----------------------: | :------: | :-----------: | ----------------------------------------------------------------------------------------------------------- |
|   0   | `strategyDelegateFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate, defined with 6 decimals of precision (1e6 == 100%). |



### `StrategyFunded`

Emitted when assets are deployed into the allocation strategy.

```solidity
    event StrategyFunded(
        address strategyManager,
        uint256 assets,
        uint256 recordedAssets
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                                          |
| :---: | :---------------: | :-------: | :-----------: | -------------------------------------------------------------------- |
|   0   | `strategyManager` | `address` |   `address`   | Address of the associated strategy manager.                          |
|   1   |      `assets`     | `uint256` |   `uint256`   | Amount of assets transferred into the allocation strategy.           |
|   2   |  `recordedAssets` | `uint256` |   `uint256`   | Amount of assets recorded as held by the strategy after the funding. |



### `StrategyMetadataSet`

Emitted when the strategy metadata is set.

```solidity
    event StrategyMetadataSet(
        string strategyMetadata
    );
```

#### Parameters:

| Index |        Name        |   Type   | Internal Type | Description                                     |
| :---: | :----------------: | :------: | :-----------: | ----------------------------------------------- |
|   0   | `strategyMetadata` | `string` |    `string`   | Optional metadata associated with the strategy. |



### `StrategyProtocolFeeRateSet`

Emitted when the strategy protocol fee rate is set.

```solidity
    event StrategyProtocolFeeRateSet(
        uint32 strategyProtocolFeeRate
    );
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                              |
| :---: | :-----------------------: | :------: | :-----------: | -------------------------------------------------------------------------------------------------------- |
|   0   | `strategyProtocolFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury, defined with 6 decimals of precision (1e6 == 100%). |



### `StrategyWithdrawn`

Emitted when assets are withdrawn from the allocation strategy.

```solidity
    event StrategyWithdrawn(
        address strategyManager,
        address destination,
        uint256 assets,
        uint256 recordedAssets
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                                             |
| :---: | :---------------: | :-------: | :-----------: | ----------------------------------------------------------------------- |
|   0   | `strategyManager` | `address` |   `address`   | Address of the associated strategy manager.                             |
|   1   |   `destination`   | `address` |   `address`   | Address that received the withdrawn assets.                             |
|   2   |      `assets`     | `uint256` |   `uint256`   | Amount of assets withdrawn from the allocation strategy.                |
|   3   |  `recordedAssets` | `uint256` |   `uint256`   | Amount of assets recorded as held by the strategy after the withdrawal. |



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



### `YieldCancelled`

Emitted when unrealized yield is cancelled from the yield buffer.

```solidity
    event YieldCancelled(
        address caller,
        address recipient,
        uint256 assets,
        uint256 recordedAssets
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                                               |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------------------------------------------- |
|   0   |     `caller`     | `address` |   `address`   | Address that cancelled the yield.                                         |
|   1   |    `recipient`   | `address` |   `address`   | Address that received the cancelled yield.                                |
|   2   |     `assets`     | `uint256` |   `uint256`   | Amount of unrealized yield cancelled.                                     |
|   3   | `recordedAssets` | `uint256` |   `uint256`   | Amount of assets recorded as held by the strategy after the cancellation. |



### `YieldCapSet`

Emitted when the yield cap is set.

```solidity
    event YieldCapSet(
        uint256 yieldCap
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                                              |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------------------------------ |
|   0   | `yieldCap` | `uint256` |   `uint256`   | Maximum amount of assets that can be realized as yield in a single call. |



### `YieldRealized`

Emitted when yield is transferred to the yield buffer.

```solidity
    event YieldRealized(
        address caller,
        uint256 unrealizedYield,
        uint256 netYield,
        uint256 delegateFee,
        uint256 protocolFee,
        uint256 recordedAssets,
        uint32 duration,
        bytes metadata
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                                              |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------------------------------------ |
|   0   |      `caller`     | `address` |   `address`   | Address that transferred the yield.                                      |
|   1   | `unrealizedYield` | `uint256` |   `uint256`   | Amount of unrealized yield carried over.                                 |
|   2   |     `netYield`    | `uint256` |   `uint256`   | Amount of net yield transferred.                                         |
|   3   |   `delegateFee`   | `uint256` |   `uint256`   | Amount of fees collected by the delegate.                                |
|   4   |   `protocolFee`   | `uint256` |   `uint256`   | Amount of fees collected by the protocol.                                |
|   5   |  `recordedAssets` | `uint256` |   `uint256`   | Amount of assets recorded as held by the strategy after the realization. |
|   6   |     `duration`    |  `uint32` |    `uint32`   | Duration over which the yield will be realized.                          |
|   7   |     `metadata`    |  `bytes`  |    `bytes`    | Optional metadata associated with the yield.                             |

