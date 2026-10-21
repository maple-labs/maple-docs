# Overview
There are many actors that can interact with Maple's contracts, so this page serves the purpose to outline all possible entry points for each actor.

# Public Callable Functions

### Pool

**Enter and Exit Functions**

* `Deposit`
* `DepositWithPermit`
* `Mint`
* `MintWithPermit`
* `Redeem`
* `Remove Shares`
* `RequestRedeem`
* `RequestWithdraw`
* `Withdraw`

**ERC20 functions**

* `approve`
* `transfer`
* `transferFrom`

### OpenTermLoan

* `makePayment`

### Globals

* `scheduleCall` - Although publicly callable, only calls scheduled by Governor and PoolDelegates can have state changing capabilities.
* `unscheduleCall`

# Permissioned Functions

### Globals

**Governor Permissioned Functions**

* `acceptGovernor`
* `activatePoolManager`
* `setBootstrapMint`
* `setCanDeployFrom`
* `setContractPause`
* `setDefaultTimelockParameters`
* `setFunctionUnpause`
* `setManualOverridePrice`
* `setMapleTreasury`
* `setMaxCoverLiquidationPercent`
* `setMigrationAdmin`
* `setMinCoverAmount`
* `setPendingGovernor`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setPriceOracle`
* `setProtocolPause`
* `setSecurityAdmin`
* `setTimelockWindow`
* `setTimelockWindows`
* `setValidBorrower`
* `setValidCollateralAsset`
* `setValidInstanceOf`
* `setValidPoolAsset`
* `setValidPoolDelegate`
* `setValidPoolDeployer`
* `unscheduleCall`

**Security Admin Permissioned Functions**

* `setContractPause`
* `setFunctionUnpause`
* `setProtocolPause`

**Pool Manager Permissioned Functions**

* `transferOwnedPoolManager`

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

**Pool Delegate Permissioned Functions**

* `configurePool`
* `setLenderAllowlist`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

### PoolManager

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Governor Permissioned Functions**

* `triggerDefault`

**Security Admin Permissioned Functions**

* `upgrade`

**Deployer Permissioned Functions**

* `addStrategy`
* `completeConfiguration`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setWithdrawalManager`

**Pool Delegate Permissioned Functions**

* `acceptPoolDelegate`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `triggerDefault`

**Globals Permissioned Functions**

* `setActive`

**Loan Manager Permissioned Functions**

* `requestFunds`

**Pool Permissioned Functions**

* `processRedeem`
* `removeShares`
* `requestRedeem`

**Disabled Functions**

* `processWithdraw`
* `requestWithdraw`

### WithdrawalManager (Queue)

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Governor Permissioned Functions**

* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`

**Operational Admin Permission Functions**

* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`

**Pool Delegate Permissioned Functions**

* `upgrade`
* `processRedemptions`
* `removeRequest`
* `setManualWithdrawal`

**Pool Manager Permissioned Functions**

* `addShares`
* `processExit`
* `removeShares`

**Redeemer Permissioned Functions**

* `processRedemptions`
* `removeShares`

**Security Admin Permissioned Functions**

* `upgrade`

**User Callable Functions**

* `removeSharesById`

### OpenTermLoan

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Governor Permissioned Functions**

* `skim`

**Security Admin Permissioned Functions**

* `upgrade`

**Borrower Permissioned Functions**

* `acceptBorrower`
* `acceptNewTerms`
* `rejectNewTerms`
* `setPendingBorrower`
* `skim`

**Lender Permissioned Functions**

* `acceptLender`
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
* `removeLoanImpairment`

**Pool Manager Permissioned Functions**

* `triggerDefault`

**Loan Permissioned Functions**

* `claim`
