# WithdrawalManager (Cyclical)

\


## Functions

### `addShares`

Add shares to the withdrawal manager.

```solidity
    function addShares(
        uint256 shares_,
        address owner_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                     |
| :---: | :-------: | :-------: | :-----------: | ------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | Amount of shares to add.        |
|   1   |  `owner_` | `address` |   `address`   | Address of the owner of shares. |

\


### `asset`

Gets the asset address used in this withdrawal manager.

```solidity
    function asset()
        view
        returns (
            address asset_
        );
```

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description           |
| :---: | :------: | :-------: | :-----------: | --------------------- |
|   0   | `asset_` | `address` |   `address`   | Address of the asset. |

\


### `cycleConfigs`

Gets the configuration for a given config id.

```solidity
    function cycleConfigs(
        uint256
    )
        view
        returns (
            uint64 initialCycleId,
            uint64 initialCycleTime,
            uint64 cycleDuration,
            uint64 windowDuration
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index |        Name        |   Type   | Internal Type | Description                                                        |
| :---: | :----------------: | :------: | :-----------: | ------------------------------------------------------------------ |
|   0   |  `initialCycleId`  | `uint64` |    `uint64`   | Identifier of the first withdrawal cycle using this configuration. |
|   1   | `initialCycleTime` | `uint64` |    `uint64`   | Timestamp of the first withdrawal cycle using this configuration.  |
|   2   |   `cycleDuration`  | `uint64` |    `uint64`   | Duration of the withdrawal cycle.                                  |
|   3   |  `windowDuration`  | `uint64` |    `uint64`   | Duration of the withdrawal window.                                 |

\


### `exitCycleId`

Gets the id of the cycle that account can exit on.

```solidity
    function exitCycleId(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


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

\


### `getConfigAtId`

Gets the configuration of a given cycle id.

```solidity
    function getConfigAtId(
        uint256 cycleId_
    )
        view
        returns (
            tuple config_
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description          |
| :---: | :--------: | :-------: | :-----------: | -------------------- |
|   0   | `cycleId_` | `uint256` |   `uint256`   | The id of the cycle. |

#### Return Values:

| Index |    Name   |   Type  |                    Internal Type                    | Description                                        |
| :---: | :-------: | :-----: | :-------------------------------------------------: | -------------------------------------------------- |
|   0   | `config_` | `tuple` | `struct IMapleWithdrawalManagerStorage.CycleConfig` | The configuration info corresponding to the cycle. |

\


### `getCurrentConfig`

Gets the configuration of the current cycle id.

```solidity
    function getCurrentConfig()
        view
        returns (
            tuple config_
        );
```

#### Return Values:

| Index |    Name   |   Type  |                    Internal Type                    | Description                                        |
| :---: | :-------: | :-----: | :-------------------------------------------------: | -------------------------------------------------- |
|   0   | `config_` | `tuple` | `struct IMapleWithdrawalManagerStorage.CycleConfig` | The configuration info corresponding to the cycle. |

\


### `getCurrentCycleId`

Gets the id of the current cycle.

```solidity
    function getCurrentCycleId()
        view
        returns (
            uint256 cycleId_
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `cycleId_` | `uint256` |   `uint256`   |             |

\


### `getRedeemableAmounts`

Gets the shares and assets that are redeemable for a given user.

```solidity
    function getRedeemableAmounts(
        uint256 lockedShares_,
        address owner_
    )
        view
        returns (
            uint256 redeemableShares_,
            uint256 resultingAssets_,
            bool partialLiquidity_
        );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                           |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `lockedShares_` | `uint256` |   `uint256`   | The amount of shares that are locked. |
|   1   |     `owner_`    | `address` |   `address`   | The owner of the shares.              |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description                                                                      |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------------------------------------------------- |
|   0   | `redeemableShares_` | `uint256` |   `uint256`   | The amount of shares that are redeemable based on current liquidity.             |
|   1   |  `resultingAssets_` | `uint256` |   `uint256`   | The corresponding amount of assets that can be redeemed using the shares.        |
|   2   | `partialLiquidity_` |   `bool`  |     `bool`    | Boolean indicating if there is enough liquidity to facilitate a full redemption. |

\


### `getWindowAtId`

Gets the timestamps of the beginning and end of the withdrawal window for a given cycle.

```solidity
    function getWindowAtId(
        uint256 cycleId_
    )
        view
        returns (
            uint256 windowStart_,
            uint256 windowEnd_
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                  |
| :---: | :--------: | :-------: | :-----------: | ---------------------------- |
|   0   | `cycleId_` | `uint256` |   `uint256`   | The id of the current cycle. |

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                                                                                               |
| :---: | :------------: | :-------: | :-----------: | --------------------------------------------------------------------------------------------------------- |
|   0   | `windowStart_` | `uint256` |   `uint256`   | The timestamp of the beginning of the cycle, which is the same as the beginning of the withdrawal window. |
|   1   |  `windowEnd_`  | `uint256` |   `uint256`   | The timestamp of the end of the withdrawal window.                                                        |

\


### `getWindowStart`

Gets the timestamp of the beginning of the withdrawal window for a given cycle.

```solidity
    function getWindowStart(
        uint256 cycleId_
    )
        view
        returns (
            uint256 windowStart_
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                  |
| :---: | :--------: | :-------: | :-----------: | ---------------------------- |
|   0   | `cycleId_` | `uint256` |   `uint256`   | The id of the current cycle. |

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                                                                                               |
| :---: | :------------: | :-------: | :-----------: | --------------------------------------------------------------------------------------------------------- |
|   0   | `windowStart_` | `uint256` |   `uint256`   | The timestamp of the beginning of the cycle, which is the same as the beginning of the withdrawal window. |

\


### `globals`

Gets the address of globals.

```solidity
    function globals()
        view
        returns (
            address globals_
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description             |
| :---: | :--------: | :-------: | :-----------: | ----------------------- |
|   0   | `globals_` | `address` |   `address`   | The address of globals. |

\


### `governor`

Gets the address of the governor.

```solidity
    function governor()
        view
        returns (
            address governor_
        );
```

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                  |
| :---: | :---------: | :-------: | :-----------: | ---------------------------- |
|   0   | `governor_` | `address` |   `address`   | The address of the governor. |

\


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

\


### `isInExitWindow`

Checks if an account is included in an exit window.

```solidity
    function isInExitWindow(
        address owner_
    )
        view
        returns (
            bool isInExitWindow_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                               |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `owner_` | `address` |   `address`   | The address of the share owners to check. |

#### Return Values:

| Index |        Name       |  Type  | Internal Type | Description                                                           |
| :---: | :---------------: | :----: | :-----------: | --------------------------------------------------------------------- |
|   0   | `isInExitWindow_` | `bool` |     `bool`    | A boolean indicating whether or not the account is in an exit window. |

\


### `latestConfigId`

Gets the most recent configuration id.

```solidity
    function latestConfigId()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `lockedLiquidity`

Gets the total amount of funds that need to be locked to fulfill exits.

```solidity
    function lockedLiquidity()
        view
        returns (
            uint256 lockedLiquidity_
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                     |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `lockedLiquidity_` | `uint256` |   `uint256`   | The amount of locked liquidity. |

\


### `lockedShares`

Gets the amount of locked shares for an account.

```solidity
    function lockedShares(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


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

\


### `pool`

Gets the address of the pool associated with this withdrawal manager.

```solidity
    function pool()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `poolDelegate`

Gets the pool delegate address.

```solidity
    function poolDelegate()
        view
        returns (
            address poolDelegate_
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                   |
| :---: | :-------------: | :-------: | :-----------: | ----------------------------- |
|   0   | `poolDelegate_` | `address` |   `address`   | Address of the pool delegate. |

\


### `poolManager`

Gets the address of the pool manager associated with this withdrawal manager.

```solidity
    function poolManager()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `previewRedeem`

Gets the amount of shares that can be redeemed.

```solidity
    function previewRedeem(
        address owner_,
        uint256 shares_
    )
        view
        returns (
            uint256 redeemableShares_,
            uint256 resultingAssets_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                               |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |  `owner_` | `address` |   `address`   | The address to check the redemption for.  |
|   1   | `shares_` | `uint256` |   `uint256`   | The amount of requested shares to redeem. |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description                                                          |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------------------------------------- |
|   0   | `redeemableShares_` | `uint256` |   `uint256`   | The amount of shares that can be redeemed.                           |
|   1   |  `resultingAssets_` | `uint256` |   `uint256`   | The amount of assets that will be returned for \`redeemableShares\`. |

\


### `previewWithdraw`

Gets the amount of shares that can be withdrawn.

```solidity
    function previewWithdraw(
        address owner_,
        uint256 assets_
    )
        pure
        returns (
            uint256 redeemableAssets_,
            uint256 resultingShares_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                 |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |  `owner_` | `address` |   `address`   | The address to check the withdrawal for.    |
|   1   | `assets_` | `uint256` |   `uint256`   | The amount of requested shares to withdraw. |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description                                 |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `redeemableAssets_` | `uint256` |   `uint256`   | The amount of assets that can be withdrawn. |
|   1   |  `resultingShares_` | `uint256` |   `uint256`   | The amount of shares that will be burned.   |

\


### `processExit`

Process the exit of an account.

```solidity
    function processExit(
        uint256 requestedShares_,
        address owner_
    )
        nonpayable
        returns (
            uint256 redeemableShares_,
            uint256 resultingAssets_
        );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                                              |
| :---: | :----------------: | :-------: | :-----------: | -------------------------------------------------------- |
|   0   | `requestedShares_` | `uint256` |   `uint256`   | Amount of initially requested shares.                    |
|   1   |      `owner_`      | `address` |   `address`   | Address of the account which will be processed for exit. |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description |
| :---: | :-----------------: | :-------: | :-----------: | ----------- |
|   0   | `redeemableShares_` | `uint256` |   `uint256`   |             |
|   1   |  `resultingAssets_` | `uint256` |   `uint256`   |             |

\


### `removeShares`

Remove shares to the withdrawal manager.

```solidity
    function removeShares(
        uint256 shares_,
        address owner_
    )
        nonpayable
        returns (
            uint256 sharesReturned_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                     |
| :---: | :-------: | :-------: | :-----------: | ------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | Amount of shares to remove.     |
|   1   |  `owner_` | `address` |   `address`   | Address of the owner of shares. |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `sharesReturned_` | `uint256` |   `uint256`   |             |

\


### `setExitConfig`

Sets up a new exit configuration.

```solidity
    function setExitConfig(
        uint256 cycleDuration_,
        uint256 windowDuration_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                            |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------------------ |
|   0   |  `cycleDuration_` | `uint256` |   `uint256`   | The total duration, in seconds, of a withdrawal cycle. |
|   1   | `windowDuration_` | `uint256` |   `uint256`   | The duration, in seconds, of the withdrawal window.    |

\


### `setImplementation`

Modifies the proxy's implementation address.

```solidity
    function setImplementation(
        address implementation_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `implementation_` | `address` |   `address`   |             |

\


### `totalCycleShares`

Gets the amount of shares for a cycle.

```solidity
    function totalCycleShares(
        uint256
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `upgrade`

Upgrades a contract implementation to a specific version. Access control logic critical since caller can force a selfdestruct via a malicious \`migrator\_\` which is delegatecalled.

```solidity
    function upgrade(
        uint256 version_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                    |
| :---: | :----------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   |  `version_`  | `uint256` |   `uint256`   |                                                |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | Some encoded arguments to use for the upgrade. |

\


## Events

### `ConfigurationUpdated`

```solidity
    event ConfigurationUpdated(
        uint256 configId_,
        uint64 initialCycleId_,
        uint64 initialCycleTime_,
        uint64 cycleDuration_,
        uint64 windowDuration_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description |
| :---: | :-----------------: | :-------: | :-----------: | ----------- |
|   0   |     `configId_`     | `uint256` |   `uint256`   |             |
|   1   |  `initialCycleId_`  |  `uint64` |    `uint64`   |             |
|   2   | `initialCycleTime_` |  `uint64` |    `uint64`   |             |
|   3   |   `cycleDuration_`  |  `uint64` |    `uint64`   |             |
|   4   |  `windowDuration_`  |  `uint64` |    `uint64`   |             |

\


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

\


### `WithdrawalCancelled`

```solidity
    event WithdrawalCancelled(
        address account_
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `account_` | `address` |   `address`   |             |

\


### `WithdrawalProcessed`

```solidity
    event WithdrawalProcessed(
        address account_,
        uint256 sharesToRedeem_,
        uint256 assetsToWithdraw_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description |
| :---: | :-----------------: | :-------: | :-----------: | ----------- |
|   0   |      `account_`     | `address` |   `address`   |             |
|   1   |  `sharesToRedeem_`  | `uint256` |   `uint256`   |             |
|   2   | `assetsToWithdraw_` | `uint256` |   `uint256`   |             |

\


### `WithdrawalUpdated`

```solidity
    event WithdrawalUpdated(
        address account_,
        uint256 lockedShares_,
        uint64 windowStart_,
        uint64 windowEnd_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description |
| :---: | :-------------: | :-------: | :-----------: | ----------- |
|   0   |    `account_`   | `address` |   `address`   |             |
|   1   | `lockedShares_` | `uint256` |   `uint256`   |             |
|   2   |  `windowStart_` |  `uint64` |    `uint64`   |             |
|   3   |   `windowEnd_`  |  `uint64` |    `uint64`   |             |

\
