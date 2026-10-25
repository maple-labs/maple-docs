# External Entry Points

Many actors interact with Maple's contracts. This page lists every state-changing entry point, grouped by contract and by who can call it. View functions are not listed. Almost every function below also reverts while it is paused through Globals, see [Emergency Pause](emergency-protocol-pause.md).

## Public Callable Functions

### Pool

The Pool Permission Manager checks every function below except `approve`. It checks deposits and mints against the receiver, exits against the share owner, and transfers against both the sender and the recipient. `requestWithdraw` and `withdraw` always revert.

**Enter and Exit Functions**

* `deposit`
* `depositWithPermit`
* `mint`
* `mintWithPermit`
* `redeem`
* `removeShares`
* `requestRedeem`
* `requestWithdraw`
* `withdraw`

**ERC20 functions**

* `approve`
* `transfer`
* `transferFrom`

### OpenTermLoan

* `makePayment`

### Globals

* `scheduleCall` - Although publicly callable, only calls scheduled by the Governor and Pool Delegates can have state-changing effects.
* `unscheduleCall` - The caller can only unschedule calls it scheduled itself.

### PoolManager, StrategyManager, AaveV3Strategy, SkyStrategy, AllocationStrategy

* `multicall`: delegatecalls each entry back into the contract and reverts the whole batch with the first inner error. It has no access, pause or reentrancy check of its own. Each inner call runs its own checks against the original caller.

## Permissioned Functions

### Globals

**Governor Permissioned Functions**

* `acceptGovernor` (pending Governor only)
* `activatePoolManager`
* `activateStrategyManager`
* `setBootstrapMint`
* `setCanDeployFrom`
* `setContractPause`
* `setDefaultTimelockParameters`
* `setFunctionUnpause`
* `setMapleTreasury`
* `setMigrationAdmin`
* `setOperationalAdmin`
* `setPendingGovernor`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setProtocolPause`
* `setSecurityAdmin`
* `setTimelockWindow`
* `setTimelockWindows`
* `setValidBorrower`
* `setValidInstanceOf`
* `setValidMapleManagedWallet`
* `setValidPoolAsset`
* `setValidPoolDelegate`
* `setValidStrategyDelegate`
* `unscheduleCall` (any caller's scheduled call)

**Operational Admin Permissioned Functions**

* `activatePoolManager`
* `activateStrategyManager`
* `setBootstrapMint`
* `setCanDeployFrom`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setValidBorrower`
* `setValidInstanceOf`
* `setValidMapleManagedWallet`
* `setValidPoolDelegate`
* `setValidStrategyDelegate`

**Security Admin Permissioned Functions**

* `setContractPause`
* `setFunctionUnpause`
* `setProtocolPause`

**Pool Manager Permissioned Functions**

* `transferOwnedPoolManager`

**Strategy Manager Permissioned Functions**

* `transferOwnedStrategyManager`

### PoolPermissionManager

**Governor Permissioned Functions**

* `configurePool`
* `setLenderAllowlist`
* `setLenderBitmaps`
* `setPermissionAdmin`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

**Operational Admin Permissioned Functions**

* `configurePool`
* `setLenderAllowlist`
* `setLenderBitmaps`
* `setPermissionAdmin`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

**Permission Admin Permissioned Functions**

* `setLenderBitmaps`

**Pool Delegate Permissioned Functions** (for the Pool they own)

* `configurePool`
* `setLenderAllowlist`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

### PoolManager

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Governor Permissioned Functions**

* `addStrategy`
* `addStrategyManager`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setPoolPermissionManager`
* `setStrategyCap`
* `triggerDefault`

**Operational Admin Permissioned Functions**

* `removeStrategyManager`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setPendingPoolDelegate`
* `setPoolPermissionManager`
* `setStrategyCap`
* `triggerDefault`

**Pool Delegate Permissioned Functions**

* `acceptPoolDelegate` (pending Pool Delegate only)
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setPoolPermissionManager`
* `setStrategyCap`
* `triggerDefault`

**Deployer Permissioned Functions** (any caller until `completeConfiguration` is called)

* `addStrategy`
* `addStrategyManager`
* `completeConfiguration`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setPoolPermissionManager`
* `setStrategyCap`
* `setWithdrawalManager`

**Globals Permissioned Functions**

* `setActive`

**Strategy and Strategy Manager Permissioned Functions** (registered strategies and Strategy Managers, within their cap)

* `requestFunds`

**Pool Permissioned Functions**

* `processRedeem`
* `removeShares`
* `requestRedeem`

**Disabled Functions**

* `processWithdraw`
* `requestWithdraw`

### StrategyManager

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Deployer Permissioned Functions** (any caller until `completeConfiguration` is called)

* `completeConfiguration`
* `setPoolManagerCap`
* `setStrategyLiquidityCap`
* `setUnderlyingStrategy`

**Globals Permissioned Functions**

* `setActive`

**Strategy Delegate Permissioned Functions**

* `acceptStrategyDelegate` (pending Strategy Delegate only)
* `cancelRedemption`
* `fundStrategyManager`
* `processRedemption`
* `requestRedeem`
* `setPoolManagerCap`
* `setStrategyLiquidityCap`

**Operational Admin Permissioned Functions**

* `processRedemption`
* `setPendingStrategyDelegate`
* `setPoolManagerCap`
* `setStrategyLiquidityCap`

**Liquidity Bot and Liquidity Router Permissioned Functions** (addresses registered in Globals as `LIQUIDITY_BOT` or `LIQUIDITY_ROUTER`, blocked while the underlying strategy has `impairedAssets`)

* `cancelRedemption`
* `fundStrategyManager`
* `processRedemption`
* `requestRedeem`

**Pool Delegate Permissioned Functions** (for the Pool Manager named in the call)

* `cancelRedemption`
* `requestRedeem`

### StrategyDeployer

**Strategy Delegate Permissioned Functions**

* `deploy`

### LiquidityRouter

**Liquidity Router Bot Permissioned Functions** (addresses registered in Globals as `LIQUIDITY_ROUTER_BOT`)

* `executeActions`

### AaveV3Strategy

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Strategy Manager Permissioned Functions**

* `fundUnderlyingStrategy`
* `withdrawFromUnderlyingStrategy`

**Strategy Delegate Permissioned Functions**

* `claimRewards`
* `impair`
* `recognizeLoss`
* `recoverPosition`
* `removeImpairment`
* `setMetadata`
* `setReferralCode`
* `setStrategyDelegateFeeRate`

**Operational Admin Permissioned Functions**

* `claimRewards`
* `impair`
* `recognizeLoss`
* `recoverPosition`
* `removeImpairment`
* `setMetadata`
* `setReferralCode`
* `setStrategyProtocolFeeRate`
* `setUseVirtualUnderlyingBalance`

**Governor Permissioned Functions**

* `setStrategyProtocolFeeRate`
* `setUseVirtualUnderlyingBalance`

### SkyStrategy

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Strategy Manager Permissioned Functions**

* `fundUnderlyingStrategy`
* `withdrawFromUnderlyingStrategy`

**Strategy Delegate Permissioned Functions**

* `impair`
* `recognizeLoss`
* `recoverPosition`
* `removeImpairment`
* `setFallbackTout`
* `setMetadata`
* `setReferralCode`
* `setStrategyDelegateFeeRate`

**Operational Admin Permissioned Functions**

* `impair`
* `recognizeLoss`
* `recoverPosition`
* `removeImpairment`
* `setFallbackTout`
* `setMetadata`
* `setReferralCode`
* `setStrategyProtocolFeeRate`

**Governor Permissioned Functions**

* `setStrategyProtocolFeeRate`

### AllocationStrategy

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `cancelYield`
* `setDeploymentCaps`
* `setPermissions`
* `upgrade`

**Strategy Manager Permissioned Functions**

* `fundUnderlyingStrategy`
* `withdrawFromUnderlyingStrategy`

**Managed Wallet Permissioned Functions** (addresses registered in Globals as `MAPLE_MANAGED_WALLET`, each also needing its own permission flag)

* `deployAssets`
* `realizeYield`
* `returnAssets`

**Strategy Delegate Permissioned Functions**

* `cancelYield`
* `impair`
* `recognizeLoss`
* `recognizeLossAndRemoveImpairment`
* `removeImpairment`
* `setDeploymentCaps`
* `setMetadata`
* `setPermissions`
* `setStrategyDelegateFeeRate`
* `setYieldCap`
* `skim`

**Operational Admin Permissioned Functions**

* `impair`
* `recognizeLoss`
* `recognizeLossAndRemoveImpairment`
* `removeImpairment`
* `setMetadata`
* `setStrategyProtocolFeeRate`
* `setYieldCap`
* `skim`

**Governor Permissioned Functions**

* `setStrategyProtocolFeeRate`

### WithdrawalManager (Queue)

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Pool Delegate Permissioned Functions**

* `processEmptyRedemptions`
* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`
* `upgrade` (through a scheduled call)

**Operational Admin Permissioned Functions**

* `processEmptyRedemptions`
* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`

**Redeemer Permissioned Functions** (addresses registered in Globals as `WITHDRAWAL_REDEEMER`)

* `processEmptyRedemptions`
* `processRedemptions`
* `removeRequest`

**Pool Manager Permissioned Functions**

* `addShares`
* `processExit`
* `removeShares`

**User Callable Functions** (request owner only, subject to the Pool Permission Manager)

* `removeSharesById`

### OpenTermLoan

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Governor Permissioned Functions**

* `skim`

**Security Admin Permissioned Functions**

* `upgrade`

**Borrower Permissioned Functions** (the Borrower, or an address registered in Globals as `BORROWER_ACTIONS` where noted)

* `acceptBorrower` (pending Borrower only)
* `acceptLoanTerms` (also Borrower Actions)
* `acceptNewTerms` (also Borrower Actions)
* `rejectNewTerms` (also Borrower Actions)
* `setPendingBorrower` (also Borrower Actions)
* `skim`

**Lender Permissioned Functions**

* `acceptLender` (pending Lender only)
* `callPrincipal`
* `fund`
* `impair`
* `proposeNewTerms`
* `rejectNewTerms`
* `removeCall`
* `removeImpairment`
* `repossess`
* `setPendingLender`

### OpenTermLoanManager

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Governor Permissioned Functions**

* `impairLoan`
* `removeLoanImpairment`

**Security Admin Permissioned Functions**

* `upgrade`

**Pool Delegate Permissioned Functions**

* `callPrincipal`
* `fund`
* `impairLoan`
* `proposeNewTerms`
* `rejectNewTerms`
* `removeCall`
* `removeLoanImpairment` (unless the Governor impaired the loan)
* `upgrade` (through a scheduled call)

**Pool Manager Permissioned Functions**

* `triggerDefault`

**Loan Permissioned Functions**

* `claim`
