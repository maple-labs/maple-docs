# PoolManager



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

### `acceptNewTerms` 

Accepts new loan terms triggering a loan refinance.

```solidity
    function acceptNewTerms(
        address loan_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_,
        uint256 principalIncrease_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to be refinanced. |
| 1 | `refinancer_` | `address` | `address` | The address of the refinancer. |
| 2 | `deadline_` | `uint256` | `uint256` | The new deadline to execute the refinance. |
| 3 | `calls_` | `bytes[]` | `bytes[]` | The encoded calls to set new loan terms. |
| 4 | `principalIncrease_` | `uint256` | `uint256` | The amount of principal increase. |


<br />

### `acceptPendingPoolDelegate` 

Accepts the role of pool delegate.

```solidity
    function acceptPendingPoolDelegate()
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
        address loanManager_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the new loan manager. |


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
        address,
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
| 1 | `` | `address` | `address` |  |
| 2 | `data_` | `bytes` | `bytes` | The data of the call. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `canCall_` | `bool` | `bool` |      True if the call can be executed, false otherwise. |
| 1 | `errorMessage_` | `string` | `string` | The error message if the call cannot be executed. |


<br />

### `configure` 

Configures the pool.

```solidity
    function configure(
        address loanManager_,
        address withdrawalManager_,
        uint256 liquidityCap_,
        uint256 delegateManagementFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the new loan manager. |
| 1 | `withdrawalManager_` | `address` | `address` | The address of the withdrawal manager. |
| 2 | `liquidityCap_` | `uint256` | `uint256` | The new liquidity cap. |
| 3 | `delegateManagementFeeRate_` | `uint256` | `uint256` |  |


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

### `fund` 



```solidity
    function fund(
        uint256 principal_,
        address loan_,
        address loanManager_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principal_` | `uint256` | `uint256` |  |
| 1 | `loan_` | `address` | `address` |  |
| 2 | `loanManager_` | `address` | `address` |  |


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
| 0 | `escrowShares_` | `uint256` | `uint256` |  |
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

### `impairLoan` 

Triggers the loan impairment for a loan.

```solidity
    function impairLoan(
        address loan_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to trigger the loan impairment. |


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

### `isValidLender` 

Returns whether or not the given address is a valid lender.

```solidity
    function isValidLender(
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

### `loanManagers` 

Gets the address of the loan manager for a given loan.

```solidity
    function loanManagers(
        address
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


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

### `openToPublic` 

Returns whether or not a pool is open to public deposits.

```solidity
    function openToPublic()
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



```solidity
    function processRedeem(
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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` |  |
| 1 | `owner_` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `redeemableShares_` | `uint256` | `uint256` |  |
| 1 | `resultingAssets_` | `uint256` | `uint256` |  |


<br />

### `removeLoanImpairment` 

Removes the loan impairment for a loan.

```solidity
    function removeLoanImpairment(
        address loan_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to remove the loan impairment. |


<br />

### `removeLoanManager` 

Removes a loan manager.

```solidity
    function removeLoanManager(
        address loanManager_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the new loan manager. |


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

### `requestRedeem` 

Requests a redemption of shares from the pool.

```solidity
    function requestRedeem(
        uint256 shares_,
        address owner_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `shares_` | `uint256` | `uint256` | The amount of shares to redeem. |
| 1 | `owner_` | `address` | `address` | The amount of shares sent to escrow. |


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

### `setAllowedLender` 

Sets a new lender as valid or not.

```solidity
    function setAllowedLender(
        address lender_,
        bool isValid_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lender_` | `address` | `address` | The address of the new lender. |
| 1 | `isValid_` | `bool` | `bool` | Whether the new lender is valid. |


<br />

### `setAllowedSlippage` 

Sets the allowed slippage for an asset on a loanManager.

```solidity
    function setAllowedSlippage(
        address loanManager_,
        address collateralAsset_,
        uint256 allowedSlippage_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the loanManager to set the slippage for. |
| 1 | `collateralAsset_` | `address` | `address` | The address of the collateral asset. |
| 2 | `allowedSlippage_` | `uint256` | `uint256` | The new allowed slippage. |


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

### `setMinRatio` 

Sets the minimum ratio for an asset on a loanManager.

```solidity
    function setMinRatio(
        address loanManager_,
        address collateralAsset_,
        uint256 minRatio_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the loan Manager to set the ratio for. |
| 1 | `collateralAsset_` | `address` | `address` | The address of the collateral asset. |
| 2 | `minRatio_` | `uint256` | `uint256` | The new minimum ratio to set. |


<br />

### `setOpenToPublic` 

Sets pool open to public depositors.

```solidity
    function setOpenToPublic()
        nonpayable;
```



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

### `AllowedLenderSet`

Emitted when a new allowed lender is called.

```solidity
    event AllowedLenderSet(
        address lender_,
        bool isValid_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lender_` | `address` | `address` | The address of the new lender. |
| 1 | `isValid_` | `bool` | `bool` | Whether the new lender is valid. |

<br />

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

### `LoanFunded`

Emitted when a new loan is funded.

```solidity
    event LoanFunded(
        address loan_,
        address loanManager_,
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan. |
| 1 | `loanManager_` | `address` | `address` | The address of the loan manager. |
| 2 | `amount_` | `uint256` | `uint256` | The amount funded to the loan. |

<br />

### `LoanImpaired`

Emitted when a loan impairment is triggered.

```solidity
    event LoanImpaired(
        address loan_,
        uint256 newPaymentDueDate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan. |
| 1 | `newPaymentDueDate_` | `uint256` | `uint256` | The new payment due date. |

<br />

### `LoanImpairmentRemoved`

Emitted when a loan impairment is removed.

```solidity
    event LoanImpairmentRemoved(
        address loan_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | The address of the loan. |

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

### `LoanManagerRemoved`

Emitted when a new loan manager is removed.

```solidity
    event LoanManagerRemoved(
        address loanManager_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the new loan manager. |

<br />

### `LoanRefinanced`

Emitted when a loan is refinanced.

```solidity
    event LoanRefinanced(
        address loan_,
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_,
        uint256 principalIncrease_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` | Loan to be refinanced. |
| 1 | `refinancer_` | `address` | `address` | The address of the refinancer. |
| 2 | `deadline_` | `uint256` | `uint256` | The new deadline to execute the refinance. |
| 3 | `calls_` | `bytes[]` | `bytes[]` | The encoded calls to set new loan terms. |
| 4 | `principalIncrease_` | `uint256` | `uint256` | The amount of principal increase. |

<br />

### `OpenToPublic`

Emitted when a pool is open to public.

```solidity
    event OpenToPublic();
```


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

### `PoolConfigured`

Emitted when the pool is configured the pool.

```solidity
    event PoolConfigured(
        address loanManager_,
        address withdrawalManager_,
        uint256 liquidityCap_,
        uint256 delegateManagementFeeRate_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanManager_` | `address` | `address` | The address of the new loan manager. |
| 1 | `withdrawalManager_` | `address` | `address` | The address of the withdrawal manager. |
| 2 | `liquidityCap_` | `uint256` | `uint256` | The new liquidity cap. |
| 3 | `delegateManagementFeeRate_` | `uint256` | `uint256` | The management fee rate. |

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

