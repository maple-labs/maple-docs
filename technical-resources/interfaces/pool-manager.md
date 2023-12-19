# Maple Pool Manager



<br />


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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `acceptPoolDelegate`

Accepts the role of pool delegate.

```solidity
    function acceptPoolDelegate()
        nonpayable;
```



<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `addLoanManager`

Adds a new loan manager.

```solidity
    function addLoanManager(
        address loanManagerFactory_
    )
        nonpayable
        returns (
            address loanManager_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManagerFactory_` | `address` | `address` | The address of the loan manager factory to use. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` |        The address of the new loan manager. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `functionId_` | `bytes32` | `bytes32` | The function to check. |
| 1 | `caller_` | `address` | `address` | The address of the caller. |
| 2 | `data_` | `bytes` | `bytes` | The data of the call. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `canCall_` | `bool` | `bool` |      True if the call can be executed, false otherwise. |
| 1 | `errorMessage_` | `string` | `string` | The error message if the call cannot be executed. |


<br />

### `completeConfiguration`

Complete the configuration.

```solidity
    function completeConfiguration()
        nonpayable;
```



<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` |  Amount of shares able to be exited. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `depositCover`

Deposits cover into the pool.

```solidity
    function depositCover(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of cover to deposit. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `factory_` | `address` | `address` |  |


<br />

### `finishCollateralLiquidation`

Finishes the collateral liquidation

```solidity
    function finishCollateralLiquidation(
        address loan_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan that had its collateral liquidated. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `shares_` | `uint256` | `uint256` | The amount of shares to get the information of. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `escrowShares_` | `uint256` | `uint256` | The amount of escrowed shares. |
| 1 | `destination_` | `address` | `address` |  The address of the destination. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `globals_` | `address` | `address` | The address of the globals. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `governor_` | `address` | `address` | The address of the governor. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `hasSufficientCover_` | `bool` | `bool` | True if pool has sufficient cover. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` |  |


<br />

### `isLoanManager`

Returns whether or not the given address is a loan manager.

```solidity
    function isLoanManager(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `loanManagerList`

Gets the address of the loan manager in the list.

```solidity
    function loanManagerList(
        uint256
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `loanManagerListLength`

Returns the length of the &#x60;loanManagerList&#x60;.

```solidity
    function loanManagerListLength()
        view
        returns (
            uint256 loanManagerListLength_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManagerListLength_` | `uint256` | `uint256` | The length of the &#x60;loanManagerList&#x60;. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `receiver_` | `address` | `address` | The address to check the deposit for. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxAssets_` | `uint256` | `uint256` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `receiver_` | `address` | `address` | The address to check the mint for. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxShares_` | `uint256` | `uint256` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The address to check the redemption for. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxShares_` | `uint256` | `uint256` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The address to check the withdraw for. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `maxAssets_` | `uint256` | `uint256` |  |


<br />

### `migrate`

Modifies the proxy&#x27;s storage by delegate-calling a migrator contract with some arguments.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function migrate(
        address migrator_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `migrator_` | `address` | `address` | The address of a migrator contract. |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the migration. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The address to check the redemption for. |
| 1 | `shares_` | `uint256` | `uint256` | The amount of requested shares to redeem. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` |  The amount of assets that will be returned for &#x60;shares_&#x60;. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The address to check the redemption for. |
| 1 | `assets_` | `uint256` | `uint256` | The amount of requested shares to redeem. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` |  The amount of assets that will be returned for &#x60;assets_&#x60;. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `owner_` | `address` | `address` | The address of the owner of the shares. |
| 2 | `sender_` | `address` | `address` | The address of the sender of the redeem call. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `redeemableShares_` | `uint256` | `uint256` | The amount of shares redeemed. |
| 1 | `resultingAssets_` | `uint256` | `uint256` |  The amount of assets withdrawn. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets_` | `uint256` | `uint256` | The amount of assets to withdraw. |
| 1 | `owner_` | `address` | `address` | The address of the owner of the shares. |
| 2 | `sender_` | `address` | `address` | The address of the sender of the withdraw call. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `redeemableShares_` | `uint256` | `uint256` | The amount of shares redeemed. |
| 1 | `resultingAssets_` | `uint256` | `uint256` |  The amount of assets withdrawn. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `owner_` | `address` | `address` | The address of the owner of the shares. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `sharesReturned_` | `uint256` | `uint256` | The amount of shares withdrawn. |


<br />

### `requestFunds`

LoanManager can request funds from the pool via the poolManager.

```solidity
    function requestFunds(
        address destination_,
        uint256 principal_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `destination_` | `address` | `address` | The address to send the funds to. |
| 1 | `principal_` | `uint256` | `uint256` | The principal amount to fund the loan with. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `owner_` | `address` | `address` | The address of the owner of the shares. |
| 2 | `sender_` | `address` | `address` | The address of the sender of the shares. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `assets_` | `uint256` | `uint256` | The amount of assets to withdraw. |
| 2 | `owner_` | `address` | `address` | The address of the owner of the shares. |
| 3 | `sender_` | `address` | `address` | The address of the sender of the shares. |


<br />

### `setActive`

Sets a the pool to be active or inactive.

```solidity
    function setActive(
        bool active_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `active_` | `bool` | `bool` | Whether the pool is active. |


<br />

### `setDelegateManagementFeeRate`

Sets the value for the delegate management fee rate.

```solidity
    function setDelegateManagementFeeRate(
        uint256 delegateManagementFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `delegateManagementFeeRate_` | `uint256` | `uint256` | The value for the delegate management fee rate. |


<br />

### `setImplementation`

Modifies the proxy&#x27;s implementation address.

```solidity
    function setImplementation(
        address implementation_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` |  |


<br />

### `setIsLoanManager`

Sets if the loanManager is valid in the isLoanManager mapping.

```solidity
    function setIsLoanManager(
        address loanManager_,
        bool isLoanManager_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the loanManager |
| 1 | `isLoanManager_` | `bool` | `bool` | Whether the loanManager is valid. |


<br />

### `setLiquidityCap`

Sets the value for liquidity cap.

```solidity
    function setLiquidityCap(
        uint256 liquidityCap_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityCap_` | `uint256` | `uint256` | The value for liquidity cap. |


<br />

### `setPendingPoolDelegate`

Sets an address as the pending pool delegate.

```solidity
    function setPendingPoolDelegate(
        address pendingPoolDelegate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingPoolDelegate_` | `address` | `address` | The address of the new pool delegate. |


<br />

### `setPoolPermissionManager`

Sets the address of the pool permission manager.

```solidity
    function setPoolPermissionManager(
        address poolPermissionManager_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolPermissionManager_` | `address` | `address` |  |


<br />

### `setWithdrawalManager`

Sets the address of the withdrawal manager.

```solidity
    function setWithdrawalManager(
        address withdrawalManager_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `withdrawalManager_` | `address` | `address` | The address of the withdrawal manager. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `totalAssets_` | `uint256` | `uint256` | Amount of of total assets. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to trigger the default. |
| 1 | `liquidatorFactory_` | `address` | `address` | Factory used to deploy the liquidator. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `unrealizedLosses_` | `uint256` | `uint256` | Amount of unrealized losses. |


<br />

### `upgrade`

Upgrades a contract implementation to a specific version.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function upgrade(
        uint256 version_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` |  |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the upgrade. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of cover to withdraw. |
| 1 | `recipient_` | `address` | `address` | The address of the recipient. |


<br />


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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan. |
| 1 | `unrealizedLosses_` | `uint256` | `uint256` | The amount of unrealized losses. |

<br />

### `CollateralLiquidationTriggered`

Emitted when a collateral liquidations is triggered.

```solidity
    event CollateralLiquidationTriggered(
        address loan_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan. |

<br />

### `CoverDeposited`

Emitted when cover is deposited.

```solidity
    event CoverDeposited(
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of cover deposited. |

<br />

### `CoverLiquidated`

Emitted when cover is liquidated in the case of a loan defaulting.

```solidity
    event CoverLiquidated(
        uint256 toTreasury_,
        uint256 toPool_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toTreasury_` | `uint256` | `uint256` | The amount of cover sent to the Treasury. |
| 1 | `toPool_` | `uint256` | `uint256` | The amount of cover sent to the Pool. |

<br />

### `CoverWithdrawn`

Emitted when cover is withdrawn.

```solidity
    event CoverWithdrawn(
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of cover withdrawn. |

<br />

### `DelegateManagementFeeRateSet`

Emitted when a new management fee rate is set.

```solidity
    event DelegateManagementFeeRateSet(
        uint256 managementFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `managementFeeRate_` | `uint256` | `uint256` | The amount of management fee rate. |

<br />

### `IsLoanManagerSet`

Emitted when a loan manager is set as valid.

```solidity
    event IsLoanManagerSet(
        address loanManager_,
        bool isLoanManager_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the loan manager. |
| 1 | `isLoanManager_` | `bool` | `bool` | Whether the loan manager is valid. |

<br />

### `LiquidityCapSet`

Emitted when a new liquidity cap is set.

```solidity
    event LiquidityCapSet(
        uint256 liquidityCap_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityCap_` | `uint256` | `uint256` | The value of liquidity cap. |

<br />

### `LoanManagerAdded`

Emitted when a new loan manager is added.

```solidity
    event LoanManagerAdded(
        address loanManager_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the new loan manager. |

<br />

### `PendingDelegateAccepted`

Emitted when the pending pool delegate accepts the ownership transfer.

```solidity
    event PendingDelegateAccepted(
        address previousDelegate_,
        address newDelegate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousDelegate_` | `address` | `address` | The address of the previous delegate. |
| 1 | `newDelegate_` | `address` | `address` | The address of the new delegate. |

<br />

### `PendingDelegateSet`

Emitted when the pending pool delegate is set.

```solidity
    event PendingDelegateSet(
        address previousDelegate_,
        address newDelegate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousDelegate_` | `address` | `address` | The address of the previous delegate. |
| 1 | `newDelegate_` | `address` | `address` | The address of the new delegate. |

<br />

### `PoolConfigurationComplete`

Emitted when the pool configuration is marked as complete.

```solidity
    event PoolConfigurationComplete();
```


<br />

### `PoolPermissionManagerSet`

Emitted when the pool permission manager is set.

```solidity
    event PoolPermissionManagerSet(
        address poolPermissionManager_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolPermissionManager_` | `address` | `address` | The address of the pool permission manager. |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of the shares. |
| 1 | `redeemableShares_` | `uint256` | `uint256` | The amount of redeemable shares. |
| 2 | `resultingAssets_` | `uint256` | `uint256` | The amount of assets redeemed. |

<br />

### `RedeemRequested`

Emitted when a redemption of shares from the pool is requested.

```solidity
    event RedeemRequested(
        address owner_,
        uint256 shares_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of the shares. |
| 1 | `shares_` | `uint256` | `uint256` | The amount of redeemable shares. |

<br />

### `SetAsActive`

Emitted when a pool is sets to be active or inactive.

```solidity
    event SetAsActive(
        bool active_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `active_` | `bool` | `bool` | Whether the pool is active. |

<br />

### `SharesRemoved`

Emitted when shares are removed from the pool.

```solidity
    event SharesRemoved(
        address owner_,
        uint256 shares_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The address of the owner of the shares. |
| 1 | `shares_` | `uint256` | `uint256` | The amount of shares removed. |

<br />

### `Upgraded`

The instance was upgraded.

```solidity
    event Upgraded(
        uint256 toVersion_,
        bytes arguments_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toVersion_` | `uint256` | `uint256` | The new version of the loan. |
| 1 | `arguments_` | `bytes` | `bytes` | The upgrade arguments, if any. |

<br />

### `WithdrawalManagerSet`

Emitted when the withdrawal manager is set.

```solidity
    event WithdrawalManagerSet(
        address withdrawalManager_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `withdrawalManager_` | `address` | `address` | The address of the withdrawal manager. |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The owner of the assets. |
| 1 | `redeemableShares_` | `uint256` | `uint256` | The amount of redeemable shares. |
| 2 | `resultingAssets_` | `uint256` | `uint256` | The amount of assets redeemed. |

<br />

