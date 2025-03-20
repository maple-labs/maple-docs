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

### FixedTermLoan

* `closeLoan`
* `makePayment`
* `postCollateral`
* `returnFunds`
* `skim`

### OpenTermLoan

* `makePayment`

### Globals

* `scheduleCall` - Although publicly callable, only calls scheduled by Governor and PoolDelegates can have state changing capabilities.
* `unscheduleCall`

### Liquidator

* `liquidatePortion` - Used by keepers to perform liquidations.

### PoolManager

* `depositCover`

# Permissioned Functions

### FixedTermLoan

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Borrower Permissioned Functions**

* `acceptBorrower`
* `drawdownFunds`
* `proposeNewTerms`
* `rejectNewTerms`
* `removeCollateral`
* `setPendingBorrower`

**Lender Permissioned Functions**

* `acceptLender`
* `acceptNewTerms`
* `fundLoan`
* `impairLoan`
* `rejectNewTerms`
* `removeLoanImpairment`
* `repossess`
* `setPendingLender`

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

* `finishCollateralLiquidation`
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
* `addStrategy`
* `finishCollateralLiquidation`
* `setAllowedLender`
* `setDelegateManagementFeeRate`
* `setIsStrategy`
* `setLiquidityCap`
* `setOpenToPublic`
* `setPendingPoolDelegate`
* `triggerDefault`
* `withdrawCover`

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

### FixedTermLoanManager

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Governor Permissioned Functions**

* `impairLoan`
* `removeLoanImpairment`
* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`

**Security Admin Permissioned Functions**

* `upgrade`

**Pool Delegate Permissioned Functions**

* `acceptNewTerms`
* `fund`
* `impairLoan`
* `rejectNewTerms`
* `removeLoanImpairment`
* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`

**Pool Manager Permissioned Functions**

* `finishCollateralLiquidation`
* `triggerDefault`

**Loan Permissioned Functions**

* `claim`

### WithdrawalManager (Cyclical)

**Governor only functionality**

* `setExitConfig`

**Operational Admin only functionality**

* `setExitConfig`

**Pool Delegate only functionality**

* `setExitConfig`

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

### Aave Strategy

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Governor Permissioned Functions**

* `claimRewards`
* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`

**Operational Admin Permissioned Functions**

* `claimRewards`
* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`

**Pool Delegate Permissioned Functions**

* `claimRewards`
* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`

### Basic Strategy

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Governor Permissioned Functions**

* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`

**Operational Admin Permissioned Functions**

* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`

**Pool Delegate Permissioned Functions**

* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`

### Sky Strategy

**Factory Permissioned Functions**

* `migrate`
* `setImplementation`

**Security Admin Permissioned Functions**

* `upgrade`

**Governor Permissioned Functions**

* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setPsm`
* `setStrategyFeeRate`

**Operational Admin Permissioned Functions**

* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setPsm`
* `setStrategyFeeRate`

**Pool Delegate Permissioned Functions**

* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setPsm`
* `setStrategyFeeRate`
