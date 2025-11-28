# WithdrawalManager (Queue)



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

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   | `shares_` | `uint256` |   `uint256`   |             |
|   1   |  `owner_` | `address` |   `address`   |             |



### `asset`

Returns the address of the underlying pool asset.

```solidity
    function asset()
        view
        returns (
            address asset_
        );
```

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description |
| :---: | :------: | :-------: | :-----------: | ----------- |
|   0   | `asset_` | `address` |   `address`   |             |



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



### `globals`

Returns the address of the globals contract.

```solidity
    function globals()
        view
        returns (
            address globals_
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `globals_` | `address` |   `address`   |             |



### `governor`

Return the address of the governor.

```solidity
    function governor()
        view
        returns (
            address governor_
        );
```

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description |
| :---: | :---------: | :-------: | :-----------: | ----------- |
|   0   | `governor_` | `address` |   `address`   |             |



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



### `isInExitWindow`

Returns if a user is able to withdraw. Required for compatibility with pool managers. NOTE: Always returns true to fulfil interface requirements.

```solidity
    function isInExitWindow(
        address owner_
    )
        pure
        returns (
            bool isInExitWindow_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                      |
| :---: | :------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   | `owner_` | `address` |   `address`   | The account to check if it's in withdraw window. |

#### Return Values:

| Index |        Name       |  Type  | Internal Type | Description                                    |
| :---: | :---------------: | :----: | :-----------: | ---------------------------------------------- |
|   0   | `isInExitWindow_` | `bool` |     `bool`    | True if the account is in the withdraw window. |



### `isManualWithdrawal`

Checks if an account is set to perform withdrawals manually.

```solidity
    function isManualWithdrawal(
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



### `lockedLiquidity`

Gets the total amount of funds that need to be locked to fulfill exits. NOTE: Always zero for this implementation.

```solidity
    function lockedLiquidity()
        pure
        returns (
            uint256 lockedLiquidity_
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                     |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `lockedLiquidity_` | `uint256` |   `uint256`   | The amount of locked liquidity. |



### `lockedShares`

Gets the amount of locked shares for an account.

```solidity
    function lockedShares(
        address owner_
    )
        view
        returns (
            uint256 lockedShares_
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                        |
| :---: | :------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `owner_` | `address` |   `address`   | The address to check the exit for. |

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                            |
| :---: | :-------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `lockedShares_` | `uint256` |   `uint256`   | The amount of manual shares available. |



### `manualSharesAvailable`

Returns the amount of shares available for manual withdrawal.

```solidity
    function manualSharesAvailable(
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



### `pool`

Returns the address of the pool contract.

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



### `poolDelegate`

Returns the address of the pool delegate.

```solidity
    function poolDelegate()
        view
        returns (
            address poolDelegate_
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description |
| :---: | :-------------: | :-------: | :-----------: | ----------- |
|   0   | `poolDelegate_` | `address` |   `address`   |             |



### `poolManager`

Returns the address of the pool manager contract.

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



### `previewRedeem`

Returns the amount of shares that can be redeemed. NOTE: The \`shares\` value is ignored.

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

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   |  `owner_` | `address` |   `address`   |             |
|   1   | `shares_` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description |
| :---: | :-----------------: | :-------: | :-----------: | ----------- |
|   0   | `redeemableShares_` | `uint256` |   `uint256`   |             |
|   1   |  `resultingAssets_` | `uint256` |   `uint256`   |             |



### `previewWithdraw`

Gets the amount of shares that can be withdrawn. NOTE: Values just passed through as withdraw is not implemented.

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



### `processExit`

Processes a withdrawal request. Uses the current exchange rate to calculate the amount of assets withdrawn.

```solidity
    function processExit(
        uint256 shares_,
        address owner_
    )
        nonpayable
        returns (
            uint256 redeemableShares_,
            uint256 resultingAssets_
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   | `shares_` | `uint256` |   `uint256`   |             |
|   1   |  `owner_` | `address` |   `address`   |             |

#### Return Values:

| Index |         Name        |    Type   | Internal Type | Description |
| :---: | :-----------------: | :-------: | :-----------: | ----------- |
|   0   | `redeemableShares_` | `uint256` |   `uint256`   |             |
|   1   |  `resultingAssets_` | `uint256` |   `uint256`   |             |



### `processRedemptions`

Processes pending redemption requests. Requests are processed in the order they were submitted. Automatic withdrawal requests will be fulfilled atomically.

```solidity
    function processRedemptions(
        uint256 maxSharesToProcess_
    )
        nonpayable;
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description |
| :---: | :-------------------: | :-------: | :-----------: | ----------- |
|   0   | `maxSharesToProcess_` | `uint256` |   `uint256`   |             |



### `queue`

Returns the first and last withdrawal requests pending redemption.

```solidity
    function queue()
        view
        returns (
            uint128 nextRequestId,
            uint128 lastRequestId
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                                                       |
| :---: | :-------------: | :-------: | :-----------: | ----------------------------------------------------------------- |
|   0   | `nextRequestId` | `uint128` |   `uint128`   | Identifier of the next withdrawal request that will be processed. |
|   1   | `lastRequestId` | `uint128` |   `uint128`   | Identifier of the last created withdrawal request.                |



### `removeRequest`

Removes a withdrawal request from the queue. Can only be called by the pool delegate.

```solidity
    function removeRequest(
        address owner_
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description |
| :---: | :------: | :-------: | :-----------: | ----------- |
|   0   | `owner_` | `address` |   `address`   |             |



### `removeShares`

Removes shares from the withdrawal manager.

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

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   | `shares_` | `uint256` |   `uint256`   |             |
|   1   |  `owner_` | `address` |   `address`   |             |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `sharesReturned_` | `uint256` |   `uint256`   |             |



### `requestIds`

Returns the request identifier of an account. Returns zero if the account does not have a withdrawal request.

```solidity
    function requestIds(
        address
    )
        view
        returns (
            uint128
        );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint128` |   `uint128`   |             |



### `requests`

Returns the owner and amount of shares associated with a withdrawal request.

```solidity
    function requests(
        uint128 requestId_
    )
        view
        returns (
            address owner_,
            uint256 shares_
        );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description |
| :---: | :----------: | :-------: | :-----------: | ----------- |
|   0   | `requestId_` | `uint128` |   `uint128`   |             |

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   |  `owner_` | `address` |   `address`   |             |
|   1   | `shares_` | `uint256` |   `uint256`   |             |



### `securityAdmin`

Returns the address of the security admin.

```solidity
    function securityAdmin()
        view
        returns (
            address securityAdmin_
        );
```

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description |
| :---: | :--------------: | :-------: | :-----------: | ----------- |
|   0   | `securityAdmin_` | `address` |   `address`   |             |



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



### `setManualWithdrawal`

Defines if an account will withdraw shares manually or automatically.

```solidity
    function setManualWithdrawal(
        address owner_,
        bool isManual_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description |
| :---: | :---------: | :-------: | :-----------: | ----------- |
|   0   |   `owner_`  | `address` |   `address`   |             |
|   1   | `isManual_` |   `bool`  |     `bool`    |             |



### `totalShares`

Returns the total amount of shares pending redemption.

```solidity
    function totalShares()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



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



## Events

### `ManualSharesDecreased`

Emitted when a manual redemption takes place.

```solidity
    event ManualSharesDecreased(
        address owner,
        uint256 sharesDecreased
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                |
| :---: | :---------------: | :-------: | :-----------: | -------------------------- |
|   0   |      `owner`      | `address` |   `address`   | Address of the account.    |
|   1   | `sharesDecreased` | `uint256` |   `uint256`   | Amount of shares redeemed. |



### `ManualSharesIncreased`

Emitted when a manual redemption is processed.

```solidity
    event ManualSharesIncreased(
        address owner,
        uint256 sharesAdded
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                      |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |    `owner`    | `address` |   `address`   | Address of the account.                          |
|   1   | `sharesAdded` | `uint256` |   `uint256`   | Amount of shares added to the redeemable amount. |



### `ManualWithdrawalSet`

Emitted when the withdrawal type of an account is updated.

```solidity
    event ManualWithdrawalSet(
        address owner,
        bool isManual
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                                         |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------------------------------- |
|   0   |   `owner`  | `address` |   `address`   | Address of the account.                                             |
|   1   | `isManual` |   `bool`  |     `bool`    | \`true\` if the withdrawal is manual, \`false\` if it is automatic. |



### `RequestCreated`

Emitted when a withdrawal request is created.

```solidity
    event RequestCreated(
        uint128 requestId,
        address owner,
        uint256 shares
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `requestId` | `uint128` |   `uint128`   | Identifier of the withdrawal request.      |
|   1   |   `owner`   | `address` |   `address`   | Address of the owner of the shares.        |
|   2   |   `shares`  | `uint256` |   `uint256`   | Amount of shares requested for redemption. |



### `RequestDecreased`

Emitted when a withdrawal request is updated.

```solidity
    event RequestDecreased(
        uint128 requestId,
        uint256 shares
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                           |
| :---: | :---------: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   | `requestId` | `uint128` |   `uint128`   | Identifier of the withdrawal request.                 |
|   1   |   `shares`  | `uint256` |   `uint256`   | Amount of shares reduced during a redemption request. |



### `RequestProcessed`

Emitted when a withdrawal request is processed.

```solidity
    event RequestProcessed(
        uint128 requestId,
        address owner,
        uint256 shares,
        uint256 assets
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `requestId` | `uint128` |   `uint128`   | Identifier of the withdrawal request. |
|   1   |   `owner`   | `address` |   `address`   | The owner of the shares.              |
|   2   |   `shares`  | `uint256` |   `uint256`   | Amount of redeemable shares.          |
|   3   |   `assets`  | `uint256` |   `uint256`   | Amount of withdrawable assets.        |



### `RequestRemoved`

Emitted when a withdrawal request is removed.

```solidity
    event RequestRemoved(
        uint128 requestId
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `requestId` | `uint128` |   `uint128`   | Identifier of the withdrawal request. |



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

