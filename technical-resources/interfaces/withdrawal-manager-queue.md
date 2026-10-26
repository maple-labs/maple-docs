# WithdrawalManager (Queue)



## Functions

### `addShares`

Add shares to the withdrawal manager.

```solidity
    function addShares(
        uint256 shares,
        address owner
    )
        nonpayable
        returns (
            uint256 lastRequestId
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                     |
| :---: | :------: | :-------: | :-----------: | ------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Amount of shares to add.        |
|   1   |  `owner` | `address` |   `address`   | Address of the owner of shares. |

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description |
| :---: | :-------------: | :-------: | :-----------: | ----------- |
|   0   | `lastRequestId` | `uint256` |   `uint256`   |             |



### `asset`

Returns the address of the underlying pool asset.

```solidity
    function asset()
        view
        returns (
            address asset
        );
```

#### Return Values:

| Index |   Name  |    Type   | Internal Type | Description                           |
| :---: | :-----: | :-------: | :-----------: | ------------------------------------- |
|   0   | `asset` | `address` |   `address`   | Address of the underlying pool asset. |



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
            address globals
        );
```

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                      |
| :---: | :-------: | :-------: | :-----------: | -------------------------------- |
|   0   | `globals` | `address` |   `address`   | Address of the globals contract. |



### `governor`

Return the address of the governor.

```solidity
    function governor()
        view
        returns (
            address governor
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                       |
| :---: | :--------: | :-------: | :-----------: | --------------------------------- |
|   0   | `governor` | `address` |   `address`   | Address of the governor contract. |



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
        address owner
    )
        pure
        returns (
            bool isInExitWindow
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                                      |
| :---: | :-----: | :-------: | :-----------: | ------------------------------------------------ |
|   0   | `owner` | `address` |   `address`   | The account to check if it's in withdraw window. |

#### Return Values:

| Index |       Name       |  Type  | Internal Type | Description                                    |
| :---: | :--------------: | :----: | :-----------: | ---------------------------------------------- |
|   0   | `isInExitWindow` | `bool` |     `bool`    | True if the account is in the withdraw window. |



### `isManualWithdrawal`

Checks if an account is set to perform withdrawals manually.

```solidity
    function isManualWithdrawal(
        address account
    )
        view
        returns (
            bool isManual
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description             |
| :---: | :-------: | :-------: | :-----------: | ----------------------- |
|   0   | `account` | `address` |   `address`   | Address of the account. |

#### Return Values:

| Index |    Name    |  Type  | Internal Type | Description                                                   |
| :---: | :--------: | :----: | :-----------: | ------------------------------------------------------------- |
|   0   | `isManual` | `bool` |     `bool`    | \`true\` if the account withdraws manually, \`false\` if not. |



### `lockedLiquidity`

Gets the total amount of funds that need to be locked to fulfill exits. NOTE: Always zero for this implementation.

```solidity
    function lockedLiquidity()
        pure
        returns (
            uint256 lockedLiquidity
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                     |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `lockedLiquidity` | `uint256` |   `uint256`   | The amount of locked liquidity. |



### `lockedShares`

Gets the amount of locked shares for an account.

```solidity
    function lockedShares(
        address owner
    )
        view
        returns (
            uint256 lockedShares
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                        |
| :---: | :-----: | :-------: | :-----------: | ---------------------------------- |
|   0   | `owner` | `address` |   `address`   | The address to check the exit for. |

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                            |
| :---: | :------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `lockedShares` | `uint256` |   `uint256`   | The amount of manual shares available. |



### `manualSharesAvailable`

Returns the amount of shares available for manual withdrawal.

```solidity
    function manualSharesAvailable(
        address owner
    )
        view
        returns (
            uint256 sharesAvailable
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                         |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------- |
|   0   | `owner` | `address` |   `address`   | The address of the owner of shares. |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                                       |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   | `sharesAvailable` | `uint256` |   `uint256`   | Amount of shares available for manual withdrawal. |



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
            address pool
        );
```

#### Return Values:

| Index |  Name  |    Type   | Internal Type | Description                   |
| :---: | :----: | :-------: | :-----------: | ----------------------------- |
|   0   | `pool` | `address` |   `address`   | Address of the pool contract. |



### `poolDelegate`

Returns the address of the pool delegate.

```solidity
    function poolDelegate()
        view
        returns (
            address poolDelegate
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                   |
| :---: | :------------: | :-------: | :-----------: | ----------------------------- |
|   0   | `poolDelegate` | `address` |   `address`   | Address of the pool delegate. |



### `poolManager`

Returns the address of the pool manager contract.

```solidity
    function poolManager()
        view
        returns (
            address poolManager
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                           |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `poolManager` | `address` |   `address`   | Address of the pool manager contract. |



### `previewRedeem`

Returns the amount of shares that can be redeemed. NOTE: The \`shares\` value is ignored.

```solidity
    function previewRedeem(
        address owner,
        uint256 shares
    )
        view
        returns (
            uint256 redeemableShares,
            uint256 resultingAssets
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                 |
| :---: | :------: | :-------: | :-----------: | --------------------------- |
|   0   |  `owner` | `address` |   `address`   | Address of the share owner  |
|   1   | `shares` | `uint256` |   `uint256`   | Amount of shares to redeem. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                             |
| :---: | :----------------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `redeemableShares` | `uint256` |   `uint256`   | Amount of shares that can be redeemed.  |
|   1   |  `resultingAssets` | `uint256` |   `uint256`   | Amount of assets that can be withdrawn. |



### `previewWithdraw`

Gets the amount of shares that can be withdrawn. NOTE: Values just passed through as withdraw is not implemented.

```solidity
    function previewWithdraw(
        address owner,
        uint256 assets
    )
        pure
        returns (
            uint256 redeemableAssets,
            uint256 resultingShares
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                 |
| :---: | :------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |  `owner` | `address` |   `address`   | The address to check the withdrawal for.    |
|   1   | `assets` | `uint256` |   `uint256`   | The amount of requested shares to withdraw. |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                 |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `redeemableAssets` | `uint256` |   `uint256`   | The amount of assets that can be withdrawn. |
|   1   |  `resultingShares` | `uint256` |   `uint256`   | The amount of shares that will be burned.   |



### `processEmptyRedemptions`

Processes empty redemption requests at the front of the queue. Iterates through the queue starting from the front and advances the queue's nextRequestId for each empty request encountered. Stops when a non-empty request is found or the specified number of requests has been processed.

```solidity
    function processEmptyRedemptions(
        uint256 numberOfRequests
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                                  |
| :---: | :----------------: | :-------: | :-----------: | -------------------------------------------- |
|   0   | `numberOfRequests` | `uint256` |   `uint256`   | Maximum number of empty requests to process. |



### `processExit`

Processes a withdrawal request. Uses the current exchange rate to calculate the amount of assets withdrawn.

```solidity
    function processExit(
        uint256 shares,
        address owner
    )
        nonpayable
        returns (
            uint256 redeemableShares,
            uint256 resultingAssets
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                               |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Amount of shares that should be redeemed. |
|   1   |  `owner` | `address` |   `address`   | Address of the account to process.        |

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                              |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `redeemableShares` | `uint256` |   `uint256`   | Amount of shares that will be burned.    |
|   1   |  `resultingAssets` | `uint256` |   `uint256`   | Amount of assets that will be withdrawn. |



### `processRedemptions`

Processes pending redemption requests. Requests are processed in the order they were submitted. Automatic withdrawal requests will be fulfilled atomically.

```solidity
    function processRedemptions(
        uint256 maxSharesToProcess
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                                      |
| :---: | :------------------: | :-------: | :-----------: | ---------------------------------------------------------------- |
|   0   | `maxSharesToProcess` | `uint256` |   `uint256`   | Maximum number of shares that will be processed during the call. |



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

Removes withdrawal requests from the queue. Can only be called by the pool delegate. NOTE: Not to be used in a router based system where the router is managing user requests.

```solidity
    function removeRequest(
        address owner,
        uint256[] requestIds
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |     Type    | Internal Type | Description                                                |
| :---: | :----------: | :---------: | :-----------: | ---------------------------------------------------------- |
|   0   |    `owner`   |  `address`  |   `address`   | Address of the owner of shares.                            |
|   1   | `requestIds` | `uint256[]` |  `uint256[]`  | Array of identifiers of the withdrawal requests to remove. |



### `removeShares`

Removes shares from the withdrawal manager.

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

| Index |   Name   |    Type   | Internal Type | Description                     |
| :---: | :------: | :-------: | :-----------: | ------------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Amount of shares to remove.     |
|   1   |  `owner` | `address` |   `address`   | Address of the owner of shares. |

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                          |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `sharesReturned` | `uint256` |   `uint256`   | Amount of shares that were returned. |



### `removeSharesById`

Remove shares from a specific withdrawal request. Can only be called by the owner of the request, and only if they have permission in the pool permission manager.

```solidity
    function removeSharesById(
        uint256 requestId,
        uint256 sharesToRemove
    )
        nonpayable
        returns (
            uint256 sharesReturned,
            uint256 sharesRemaining
        );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                                 |
| :---: | :--------------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   |    `requestId`   | `uint256` |   `uint256`   | Identifier of the withdrawal request that is being updated. |
|   1   | `sharesToRemove` | `uint256` |   `uint256`   | Amount of shares to remove from the request.                |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                                |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   |  `sharesReturned` | `uint256` |   `uint256`   | Amount of shares that were returned.       |
|   1   | `sharesRemaining` | `uint256` |   `uint256`   | Amount of shares remaining in the request. |



### `requestIds`

Returns the last request id for a given owner. Function must exist for backwards compatibility with the old implementation where we supported only one request per owner.

```solidity
    function requestIds(
        address owner
    )
        view
        returns (
            uint256 requestId
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                                   |
| :---: | :-----: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `owner` | `address` |   `address`   | The account to check the last request id for. |

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                                                  |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------------------------ |
|   0   | `requestId` | `uint256` |   `uint256`   | The id of the last valid withdrawal request for the account. |



### `requests`

Returns the owner and amount of shares associated with a withdrawal request.

```solidity
    function requests(
        uint256 requestId
    )
        view
        returns (
            address owner,
            uint256 shares
        );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `requestId` | `uint256` |   `uint256`   | Identifier of the withdrawal request. |

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description                          |
| :---: | :------: | :-------: | :-----------: | ------------------------------------ |
|   0   |  `owner` | `address` |   `address`   | Address of the share owner.          |
|   1   | `shares` | `uint256` |   `uint256`   | Amount of shares pending redemption. |



### `requestsByOwner`

Returns the pending requests by owner. NOTE: This function may run out of gas if there are too many requests. Use the overload with pagination.

```solidity
    function requestsByOwner(
        address owner
    )
        view
        returns (
            uint256[] requestIds,
            uint256[] shares
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                                           |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   | `owner` | `address` |   `address`   | Address of the account to check for pending requests. |

#### Return Values:

| Index |     Name     |     Type    | Internal Type | Description                                   |
| :---: | :----------: | :---------: | :-----------: | --------------------------------------------- |
|   0   | `requestIds` | `uint256[]` |  `uint256[]`  | Array of request identifiers.                 |
|   1   |   `shares`   | `uint256[]` |  `uint256[]`  | Array of shares associated with each request. |



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



### `setManualWithdrawal`

Defines if an account will withdraw shares manually or automatically.

```solidity
    function setManualWithdrawal(
        address account,
        bool isManual
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                                                                           |
| :---: | :--------: | :-------: | :-----------: | ----------------------------------------------------------------------------------------------------- |
|   0   |  `account` | `address` |   `address`   | Address of the account.                                                                               |
|   1   | `isManual` |   `bool`  |     `bool`    | \`true\` if the account withdraws manually, \`false\` if the withdrawals are performed automatically. |



### `totalShares`

Returns the total amount of shares pending redemption.

```solidity
    function totalShares()
        view
        returns (
            uint256 totalShares
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description                                |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `totalShares` | `uint256` |   `uint256`   | Total amount of shares pending redemption. |



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



### `userEscrowedShares`

Returns the amount of shares escrowed for a specific user yet to be processed.

```solidity
    function userEscrowedShares(
        address owner
    )
        view
        returns (
            uint256 escrowedShares
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                         |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------- |
|   0   | `owner` | `address` |   `address`   | The address of the owner of shares. |

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                             |
| :---: | :--------------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `escrowedShares` | `uint256` |   `uint256`   | Amount of shares escrowed for the user. |



## Events

### `EmptyRedemptionsProcessed`

Emitted when empty redemption requests are processed.

```solidity
    event EmptyRedemptionsProcessed(
        uint256 numberOfRequestsProcessed
    );
```

#### Parameters:

| Index |             Name            |    Type   | Internal Type | Description                                   |
| :---: | :-------------------------: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `numberOfRequestsProcessed` | `uint256` |   `uint256`   | Number of empty requests that were processed. |



### `ManualSharesDecreased`

Emitted when a manual redemption takes place.

```solidity
    event ManualSharesDecreased(
        address indexed owner,
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
        uint256 indexed requestId,
        address indexed owner,
        uint256 sharesAdded
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                      |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |  `requestId`  | `uint256` |   `uint256`   | Identifier of the withdrawal request.            |
|   1   |    `owner`    | `address` |   `address`   | Address of the account.                          |
|   2   | `sharesAdded` | `uint256` |   `uint256`   | Amount of shares added to the redeemable amount. |



### `ManualWithdrawalSet`

Emitted when the withdrawal type of an account is updated.

```solidity
    event ManualWithdrawalSet(
        address indexed owner,
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
        uint256 indexed requestId,
        address indexed owner,
        uint256 shares
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `requestId` | `uint256` |   `uint256`   | Identifier of the withdrawal request.      |
|   1   |   `owner`   | `address` |   `address`   | Address of the owner of the shares.        |
|   2   |   `shares`  | `uint256` |   `uint256`   | Amount of shares requested for redemption. |



### `RequestDecreased`

Emitted when a withdrawal request is updated.

```solidity
    event RequestDecreased(
        uint256 indexed requestId,
        uint256 shares
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                           |
| :---: | :---------: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   | `requestId` | `uint256` |   `uint256`   | Identifier of the withdrawal request.                 |
|   1   |   `shares`  | `uint256` |   `uint256`   | Amount of shares reduced during a redemption request. |



### `RequestProcessed`

Emitted when a withdrawal request is processed.

```solidity
    event RequestProcessed(
        uint256 indexed requestId,
        address indexed owner,
        uint256 shares,
        uint256 assets
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `requestId` | `uint256` |   `uint256`   | Identifier of the withdrawal request. |
|   1   |   `owner`   | `address` |   `address`   | The owner of the shares.              |
|   2   |   `shares`  | `uint256` |   `uint256`   | Amount of redeemable shares.          |
|   3   |   `assets`  | `uint256` |   `uint256`   | Amount of withdrawable assets.        |



### `RequestRemoved`

Emitted when a withdrawal request is removed.

```solidity
    event RequestRemoved(
        uint256 indexed requestId
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                           |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `requestId` | `uint256` |   `uint256`   | Identifier of the withdrawal request. |



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

