# PoolManager

\


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

\


### `acceptPoolDelegate`

Accepts the role of pool delegate.

```solidity
    function acceptPoolDelegate()
        nonpayable;
```

\


### `active`

Returns whether or not a pool is active.

```solidity
    function active()
        view
        returns (
            bool
        );
```

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `addStrategy`

Adds a new strategy. NOTE: The PoolManager address is encoded and prepended to the extraDeploymentData.

```solidity
    function addStrategy(
        address strategyFactory_,
        bytes extraDeploymentData_
    )
        nonpayable
        returns (
            address strategy_
        );
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description                                 |
| :---: | :--------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |   `strategyFactory_`   | `address` |   `address`   | The address of the strategy factory to use. |
|   1   | `extraDeploymentData_` |  `bytes`  |    `bytes`    | The data to construct the strategy.         |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                      |
| :---: | :---------: | :-------: | :-----------: | -------------------------------- |
|   0   | `strategy_` | `address` |   `address`   | The address of the new strategy. |

\


### `asset`

Gets the address of the funds asset.

```solidity
    function asset()
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


### `canCall`

Checks if a scheduled call can be executed.

```solidity
    function canCall(
        bytes32 functionId_,
        address caller_,
        bytes data_
    )
        view
        returns (
            bool canCall_,
            string errorMessage_
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                |
| :---: | :-----------: | :-------: | :-----------: | -------------------------- |
|   0   | `functionId_` | `bytes32` |   `bytes32`   | The function to check.     |
|   1   |   `caller_`   | `address` |   `address`   | The address of the caller. |
|   2   |    `data_`    |  `bytes`  |    `bytes`    | The data of the call.      |

#### Return Values:

| Index |       Name      |   Type   | Internal Type | Description                                        |
| :---: | :-------------: | :------: | :-----------: | -------------------------------------------------- |
|   0   |    `canCall_`   |  `bool`  |     `bool`    | True if the call can be executed, false otherwise. |
|   1   | `errorMessage_` | `string` |    `string`   | The error message if the call cannot be executed.  |

\


### `completeConfiguration`

Complete the configuration.

```solidity
    function completeConfiguration()
        nonpayable;
```

\


### `configured`

Returns whether or not a pool is configured.

```solidity
    function configured()
        view
        returns (
            bool
        );
```

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `convertToExitShares`

Returns the amount of exit shares for the input amount.

```solidity
    function convertToExitShares(
        uint256 assets_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   | `assets_` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                         |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | Amount of shares able to be exited. |

\


### `delegateManagementFeeRate`

Gets the delegate management fee rate.

```solidity
    function delegateManagementFeeRate()
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


### `depositCover`

Deposits cover into the pool.

```solidity
    function depositCover(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                     |
| :---: | :-------: | :-------: | :-----------: | ------------------------------- |
|   0   | `amount_` | `uint256` |   `uint256`   | The amount of cover to deposit. |

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


### `finishCollateralLiquidation`

Finishes the collateral liquidation

```solidity
    function finishCollateralLiquidation(
        address loan_
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                              |
| :---: | :-----: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `loan_` | `address` |   `address`   | Loan that had its collateral liquidated. |

\


### `getEscrowParams`

Gets the information of escrowed shares.

```solidity
    function getEscrowParams(
        address,
        uint256 shares_
    )
        view
        returns (
            uint256 escrowShares_,
            address destination_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                     |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   |    \`\`   | `address` |   `address`   |                                                 |
|   1   | `shares_` | `uint256` |   `uint256`   | The amount of shares to get the information of. |

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                     |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `escrowShares_` | `uint256` |   `uint256`   | The amount of escrowed shares.  |
|   1   |  `destination_` | `address` |   `address`   | The address of the destination. |

\


### `globals`

Gets the address of the globals.

```solidity
    function globals()
        view
        returns (
            address globals_
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                 |
| :---: | :--------: | :-------: | :-----------: | --------------------------- |
|   0   | `globals_` | `address` |   `address`   | The address of the globals. |

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


### `hasSufficientCover`

Returns if pool has sufficient cover.

```solidity
    function hasSufficientCover()
        view
        returns (
            bool hasSufficientCover_
        );
```

#### Return Values:

| Index |          Name         |  Type  | Internal Type | Description                        |
| :---: | :-------------------: | :----: | :-----------: | ---------------------------------- |
|   0   | `hasSufficientCover_` | `bool` |     `bool`    | True if pool has sufficient cover. |

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


### `isStrategy`

Returns whether or not the given address is a strategy.

```solidity
    function isStrategy(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `liquidityCap`

Gets the liquidity cap for the pool.

```solidity
    function liquidityCap()
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


### `maxDeposit`

Gets the amount of assets that can be deposited.

```solidity
    function maxDeposit(
        address receiver_
    )
        view
        returns (
            uint256 maxAssets_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `receiver_` | `address` |   `address`   | The address to check the deposit for. |

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description |
| :---: | :----------: | :-------: | :-----------: | ----------- |
|   0   | `maxAssets_` | `uint256` |   `uint256`   |             |

\


### `maxMint`

Gets the amount of shares that can be minted.

```solidity
    function maxMint(
        address receiver_
    )
        view
        returns (
            uint256 maxShares_
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                        |
| :---: | :---------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `receiver_` | `address` |   `address`   | The address to check the mint for. |

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description |
| :---: | :----------: | :-------: | :-----------: | ----------- |
|   0   | `maxShares_` | `uint256` |   `uint256`   |             |

\


### `maxRedeem`

Gets the amount of shares that can be redeemed.

```solidity
    function maxRedeem(
        address owner_
    )
        view
        returns (
            uint256 maxShares_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                              |
| :---: | :------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `owner_` | `address` |   `address`   | The address to check the redemption for. |

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description |
| :---: | :----------: | :-------: | :-----------: | ----------- |
|   0   | `maxShares_` | `uint256` |   `uint256`   |             |

\


### `maxWithdraw`

Gets the amount of assets that can be withdrawn.

```solidity
    function maxWithdraw(
        address owner_
    )
        view
        returns (
            uint256 maxAssets_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                            |
| :---: | :------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `owner_` | `address` |   `address`   | The address to check the withdraw for. |

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description |
| :---: | :----------: | :-------: | :-----------: | ----------- |
|   0   | `maxAssets_` | `uint256` |   `uint256`   |             |

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


### `pendingPoolDelegate`

Gets the address of the pending pool delegate.

```solidity
    function pendingPoolDelegate()
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


### `pool`

Gets the address of the pool.

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

Gets the address of the pool delegate.

```solidity
    function poolDelegate()
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


### `poolDelegateCover`

Gets the address of the pool delegate cover.

```solidity
    function poolDelegateCover()
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


### `poolPermissionManager`

Gets the address of the pool delegate cover.

```solidity
    function poolPermissionManager()
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
            uint256 assets_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                               |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |  `owner_` | `address` |   `address`   | The address to check the redemption for.  |
|   1   | `shares_` | `uint256` |   `uint256`   | The amount of requested shares to redeem. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                                  |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------------------------ |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets that will be returned for \`shares\_\`. |

\


### `previewWithdraw`

Gets the amount of assets that can be redeemed.

```solidity
    function previewWithdraw(
        address owner_,
        uint256 assets_
    )
        view
        returns (
            uint256 shares_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                               |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |  `owner_` | `address` |   `address`   | The address to check the redemption for.  |
|   1   | `assets_` | `uint256` |   `uint256`   | The amount of requested shares to redeem. |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                                                  |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------------------------ |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of assets that will be returned for \`assets\_\`. |

\


### `processRedeem`

Processes a redemptions of shares for assets from the pool.

```solidity
    function processRedeem(
        uint256 shares_,
        address owner_,
        address sender_
    )
        nonpayable
        returns (
            uint256 redeemableShares_,
            uint256 resultingAssets_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                   |
| :---: | :-------: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares to redeem.               |
|   1   |  `owner_` | `address` |   `address`   | The address of the owner of the shares.       |
|   2   | `sender_` | `address` |   `address`   | The address of the sender of the redeem call. |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description                     |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `redeemableShares_` | `uint256` |   `uint256`   | The amount of shares redeemed.  |
|   1   |  `resultingAssets_` | `uint256` |   `uint256`   | The amount of assets withdrawn. |

\


### `processWithdraw`

Processes a redemptions of shares for assets from the pool.

```solidity
    function processWithdraw(
        uint256 assets_,
        address owner_,
        address sender_
    )
        nonpayable
        returns (
            uint256 redeemableShares_,
            uint256 resultingAssets_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                     |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `assets_` | `uint256` |   `uint256`   | The amount of assets to withdraw.               |
|   1   |  `owner_` | `address` |   `address`   | The address of the owner of the shares.         |
|   2   | `sender_` | `address` |   `address`   | The address of the sender of the withdraw call. |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description                     |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `redeemableShares_` | `uint256` |   `uint256`   | The amount of shares redeemed.  |
|   1   |  `resultingAssets_` | `uint256` |   `uint256`   | The amount of assets withdrawn. |

\


### `removeShares`

Requests a redemption of shares from the pool.

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

| Index |    Name   |    Type   | Internal Type | Description                             |
| :---: | :-------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares to redeem.         |
|   1   |  `owner_` | `address` |   `address`   | The address of the owner of the shares. |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                     |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `sharesReturned_` | `uint256` |   `uint256`   | The amount of shares withdrawn. |

\


### `requestFunds`

Strategy can request funds from the pool via the poolManager.

```solidity
    function requestFunds(
        address destination_,
        uint256 principal_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                     |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `destination_` | `address` |   `address`   | The address to send the funds to.               |
|   1   |  `principal_`  | `uint256` |   `uint256`   | The principal amount to fund the strategy with. |

\


### `requestRedeem`

Requests a redemption of shares from the pool.

```solidity
    function requestRedeem(
        uint256 shares_,
        address owner_,
        address sender_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                              |
| :---: | :-------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares to redeem.          |
|   1   |  `owner_` | `address` |   `address`   | The address of the owner of the shares.  |
|   2   | `sender_` | `address` |   `address`   | The address of the sender of the shares. |

\


### `requestWithdraw`

Requests a withdrawal of assets from the pool.

```solidity
    function requestWithdraw(
        uint256 shares_,
        uint256 assets_,
        address owner_,
        address sender_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                              |
| :---: | :-------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `shares_` | `uint256` |   `uint256`   | The amount of shares to redeem.          |
|   1   | `assets_` | `uint256` |   `uint256`   | The amount of assets to withdraw.        |
|   2   |  `owner_` | `address` |   `address`   | The address of the owner of the shares.  |
|   3   | `sender_` | `address` |   `address`   | The address of the sender of the shares. |

\


### `setActive`

Sets a the pool to be active or inactive.

```solidity
    function setActive(
        bool active_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |  Type  | Internal Type | Description                 |
| :---: | :-------: | :----: | :-----------: | --------------------------- |
|   0   | `active_` | `bool` |     `bool`    | Whether the pool is active. |

\


### `setDelegateManagementFeeRate`

Sets the value for the delegate management fee rate.

```solidity
    function setDelegateManagementFeeRate(
        uint256 delegateManagementFeeRate_
    )
        nonpayable;
```

#### Parameters:

| Index |             Name             |    Type   | Internal Type | Description                                     |
| :---: | :--------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `delegateManagementFeeRate_` | `uint256` |   `uint256`   | The value for the delegate management fee rate. |

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


### `setIsStrategy`

Sets if the strategy is valid in the isStrategy mapping.

```solidity
    function setIsStrategy(
        address strategy_,
        bool isStrategy_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                    |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------ |
|   0   |  `strategy_`  | `address` |   `address`   | The address of the strategy    |
|   1   | `isStrategy_` |   `bool`  |     `bool`    | Whether the strategy is valid. |

\


### `setLiquidityCap`

Sets the value for liquidity cap.

```solidity
    function setLiquidityCap(
        uint256 liquidityCap_
    )
        nonpayable;
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                  |
| :---: | :-------------: | :-------: | :-----------: | ---------------------------- |
|   0   | `liquidityCap_` | `uint256` |   `uint256`   | The value for liquidity cap. |

\


### `setPendingPoolDelegate`

Sets an address as the pending pool delegate.

```solidity
    function setPendingPoolDelegate(
        address pendingPoolDelegate_
    )
        nonpayable;
```

#### Parameters:

| Index |          Name          |    Type   | Internal Type | Description                           |
| :---: | :--------------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `pendingPoolDelegate_` | `address` |   `address`   | The address of the new pool delegate. |

\


### `setPoolPermissionManager`

Sets the address of the pool permission manager.

```solidity
    function setPoolPermissionManager(
        address poolPermissionManager_
    )
        nonpayable;
```

#### Parameters:

| Index |           Name           |    Type   | Internal Type | Description |
| :---: | :----------------------: | :-------: | :-----------: | ----------- |
|   0   | `poolPermissionManager_` | `address` |   `address`   |             |

\


### `setWithdrawalManager`

Sets the address of the withdrawal manager.

```solidity
    function setWithdrawalManager(
        address withdrawalManager_
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                            |
| :---: | :------------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `withdrawalManager_` | `address` |   `address`   | The address of the withdrawal manager. |

\


### `strategyList`

Gets the address of the strategy in the list.

```solidity
    function strategyList(
        uint256
    )
        view
        returns (
            address
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `strategyListLength`

Returns the length of the \`strategyList\`.

```solidity
    function strategyListLength()
        view
        returns (
            uint256 strategyListLength_
        );
```

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                         |
| :---: | :-------------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `strategyListLength_` | `uint256` |   `uint256`   | The length of the \`strategyList\`. |

\


### `totalAssets`

Returns the amount of total assets.

```solidity
    function totalAssets()
        view
        returns (
            uint256 totalAssets_
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                |
| :---: | :------------: | :-------: | :-----------: | -------------------------- |
|   0   | `totalAssets_` | `uint256` |   `uint256`   | Amount of of total assets. |

\


### `triggerDefault`

Triggers the default of a loan.

```solidity
    function triggerDefault(
        address loan_,
        address liquidatorFactory_
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                            |
| :---: | :------------------: | :-------: | :-----------: | -------------------------------------- |
|   0   |        `loan_`       | `address` |   `address`   | Loan to trigger the default.           |
|   1   | `liquidatorFactory_` | `address` |   `address`   | Factory used to deploy the liquidator. |

\


### `unrealizedLosses`

Returns the amount unrealized losses.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint256 unrealizedLosses_
        );
```

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description                  |
| :---: | :-----------------: | :-------: | :-----------: | ---------------------------- |
|   0   | `unrealizedLosses_` | `uint256` |   `uint256`   | Amount of unrealized losses. |

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


### `withdrawalManager`

Gets the address of the withdrawal manager.

```solidity
    function withdrawalManager()
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


### `withdrawCover`

Withdraws cover from the pool.

```solidity
    function withdrawCover(
        uint256 amount_,
        address recipient_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                      |
| :---: | :----------: | :-------: | :-----------: | -------------------------------- |
|   0   |   `amount_`  | `uint256` |   `uint256`   | The amount of cover to withdraw. |
|   1   | `recipient_` | `address` |   `address`   | The address of the recipient.    |

\


## Events

### `CollateralLiquidationFinished`

Emitted when a collateral liquidations is finished.

```solidity
    event CollateralLiquidationFinished(
        address loan_,
        uint256 unrealizedLosses_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                      |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------- |
|   0   |       `loan_`       | `address` |   `address`   | The address of the loan.         |
|   1   | `unrealizedLosses_` | `uint256` |   `uint256`   | The amount of unrealized losses. |

\


### `CollateralLiquidationTriggered`

Emitted when a collateral liquidations is triggered.

```solidity
    event CollateralLiquidationTriggered(
        address loan_
    );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description              |
| :---: | :-----: | :-------: | :-----------: | ------------------------ |
|   0   | `loan_` | `address` |   `address`   | The address of the loan. |

\


### `CoverDeposited`

Emitted when cover is deposited.

```solidity
    event CoverDeposited(
        uint256 amount_
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                    |
| :---: | :-------: | :-------: | :-----------: | ------------------------------ |
|   0   | `amount_` | `uint256` |   `uint256`   | The amount of cover deposited. |

\


### `CoverLiquidated`

Emitted when cover is liquidated in the case of a loan defaulting.

```solidity
    event CoverLiquidated(
        uint256 toTreasury_,
        uint256 toPool_
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                               |
| :---: | :-----------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `toTreasury_` | `uint256` |   `uint256`   | The amount of cover sent to the Treasury. |
|   1   |   `toPool_`   | `uint256` |   `uint256`   | The amount of cover sent to the Pool.     |

\


### `CoverWithdrawn`

Emitted when cover is withdrawn.

```solidity
    event CoverWithdrawn(
        uint256 amount_
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                    |
| :---: | :-------: | :-------: | :-----------: | ------------------------------ |
|   0   | `amount_` | `uint256` |   `uint256`   | The amount of cover withdrawn. |

\


### `DelegateManagementFeeRateSet`

Emitted when a new management fee rate is set.

```solidity
    event DelegateManagementFeeRateSet(
        uint256 managementFeeRate_
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                        |
| :---: | :------------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `managementFeeRate_` | `uint256` |   `uint256`   | The amount of management fee rate. |

\


### `IsStrategySet`

Emitted when a strategy is set as valid.

```solidity
    event IsStrategySet(
        address strategy_,
        bool isStrategy_
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                    |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------ |
|   0   |  `strategy_`  | `address` |   `address`   | The address of the strategy.   |
|   1   | `isStrategy_` |   `bool`  |     `bool`    | Whether the strategy is valid. |

\


### `LiquidityCapSet`

Emitted when a new liquidity cap is set.

```solidity
    event LiquidityCapSet(
        uint256 liquidityCap_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                 |
| :---: | :-------------: | :-------: | :-----------: | --------------------------- |
|   0   | `liquidityCap_` | `uint256` |   `uint256`   | The value of liquidity cap. |

\


### `PendingDelegateAccepted`

Emitted when the pending pool delegate accepts the ownership transfer.

```solidity
    event PendingDelegateAccepted(
        address previousDelegate_,
        address newDelegate_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                           |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `previousDelegate_` | `address` |   `address`   | The address of the previous delegate. |
|   1   |    `newDelegate_`   | `address` |   `address`   | The address of the new delegate.      |

\


### `PendingDelegateSet`

Emitted when the pending pool delegate is set.

```solidity
    event PendingDelegateSet(
        address previousDelegate_,
        address newDelegate_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                           |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `previousDelegate_` | `address` |   `address`   | The address of the previous delegate. |
|   1   |    `newDelegate_`   | `address` |   `address`   | The address of the new delegate.      |

\


### `PoolConfigurationComplete`

Emitted when the pool configuration is marked as complete.

```solidity
    event PoolConfigurationComplete();
```

\


### `PoolPermissionManagerSet`

Emitted when the pool permission manager is set.

```solidity
    event PoolPermissionManagerSet(
        address poolPermissionManager_
    );
```

#### Parameters:

| Index |           Name           |    Type   | Internal Type | Description                                 |
| :---: | :----------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `poolPermissionManager_` | `address` |   `address`   | The address of the pool permission manager. |

\


### `RedeemProcessed`

Emitted when a redemption of shares from the pool is processed.

```solidity
    event RedeemProcessed(
        address owner_,
        uint256 redeemableShares_,
        uint256 resultingAssets_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                      |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------- |
|   0   |       `owner_`      | `address` |   `address`   | The owner of the shares.         |
|   1   | `redeemableShares_` | `uint256` |   `uint256`   | The amount of redeemable shares. |
|   2   |  `resultingAssets_` | `uint256` |   `uint256`   | The amount of assets redeemed.   |

\


### `RedeemRequested`

Emitted when a redemption of shares from the pool is requested.

```solidity
    event RedeemRequested(
        address owner_,
        uint256 shares_
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   |  `owner_` | `address` |   `address`   | The owner of the shares.         |
|   1   | `shares_` | `uint256` |   `uint256`   | The amount of redeemable shares. |

\


### `SetAsActive`

Emitted when a pool is sets to be active or inactive.

```solidity
    event SetAsActive(
        bool active_
    );
```

#### Parameters:

| Index |    Name   |  Type  | Internal Type | Description                 |
| :---: | :-------: | :----: | :-----------: | --------------------------- |
|   0   | `active_` | `bool` |     `bool`    | Whether the pool is active. |

\


### `SharesRemoved`

Emitted when shares are removed from the pool.

```solidity
    event SharesRemoved(
        address owner_,
        uint256 shares_
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                             |
| :---: | :-------: | :-------: | :-----------: | --------------------------------------- |
|   0   |  `owner_` | `address` |   `address`   | The address of the owner of the shares. |
|   1   | `shares_` | `uint256` |   `uint256`   | The amount of shares removed.           |

\


### `StrategyAdded`

Emitted when a new strategy is added.

```solidity
    event StrategyAdded(
        address strategy_
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                      |
| :---: | :---------: | :-------: | :-----------: | -------------------------------- |
|   0   | `strategy_` | `address` |   `address`   | The address of the new strategy. |

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


### `WithdrawalManagerSet`

Emitted when the withdrawal manager is set.

```solidity
    event WithdrawalManagerSet(
        address withdrawalManager_
    );
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                            |
| :---: | :------------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `withdrawalManager_` | `address` |   `address`   | The address of the withdrawal manager. |

\


### `WithdrawalProcessed`

Emitted when withdrawal of assets from the pool is processed.

```solidity
    event WithdrawalProcessed(
        address owner_,
        uint256 redeemableShares_,
        uint256 resultingAssets_
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                      |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------- |
|   0   |       `owner_`      | `address` |   `address`   | The owner of the assets.         |
|   1   | `redeemableShares_` | `uint256` |   `uint256`   | The amount of redeemable shares. |
|   2   |  `resultingAssets_` | `uint256` |   `uint256`   | The amount of assets redeemed.   |

\
