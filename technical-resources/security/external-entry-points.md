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
* `Withdraw`
* `RequestRedeem`
* `RequestWithdraw`
* `Remove Shares`

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

* `scheduleCall` - Although publicly callable, only calls scheduled by Governor and PoolDelegates can have state changing capabilitiies.
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
* `removeCollateral`
* `setPendingBorrower`
* `rejectNewTerms`

**Lender Permissioned Functions**

* `acceptLender`
* `acceptNewTerms`
* `fundLoan`
* `impairLoan`
* `removeLoanImpairment`
* `repossess`
* `setPendingLender`
* `rejectNewTerms`

### Globals

**Governor Permissioned Functions**

* `acceptGovernor`
* `setPendingGovernor`
* `activatePoolManager`
* `setBootstrapMint`
* `setDefaultTimelockParameters`
* `setMapleTreasury`
* `setMigrationAdmin`
* `setPriceOracle`
* `setSecurityAdmin`
* `setContractPause`
* `setCanDeployFrom`
* `setValidBorrower`
* `setValidCollateralAsset`
* `setValidInstanceOf`
* `setValidPoolAsset`
* `setValidPoolDelegate`
* `setValidPoolDeployer`
* `setManualOverridePrice`
* `setMaxCoverLiquidationPercent`
* `setMinCoverAmount`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setTimelockWindow`
* `setTimelockWindows`

**Security Admin Permissioned Functions**

* `setContractPause`
* `setFunctionUnpause`
* `setProtocolPause`

**Pool Manager Permissioned Functions**

* `transferOwnedPoolManager`

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

* `completeConfiguration`
* `addLoanManager`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setWithdrawalManager`

**Pool Delegate Permissioned Functions**

* `acceptPoolDelegate`
* `setPendingPoolDelegate`
* `addLoanManager`
* `setAllowedLender`
* `setDelegateManagementFeeRate`
* `setIsLoanManager`
* `setLiquidityCap`
* `setOpenToPublic`
* `finishCollateralLiquidation`
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

* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`
* `impairLoan`
* `removeLoanImpairment`

**Security Admin Permissioned Functions**

* `upgrade`

**Pool Delegate Permissioned Functions**

* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`
* `acceptNewTerms`
* `fund`
* `rejectNewTerms`
* `impairLoan`
* `removeLoanImpairment`

**Pool Manager Permissioned Functions**

* `finishCollateralLiquidation`
* `triggerDefault`

**Loan Permissioned Functions**

* `claim`

### WithdrawalManager

**Pool Delegate only functionality**

* `setExitConfig`

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
* `setPendingBorrower`
* `rejectNewTerms`
* `skim`

**Lender Permissioned Functions**

* `acceptLender`
* `callPrincipal`
* `fund`
* `impair`
* `proposeNewTerms`
* `removeCall`
* `removeImpairment`
* `repossess`
* `setPendingLender`
* `rejectNewTerms`

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

* `fund`
* `proposeNewTerms`
* `rejectNewTerms`
* `callPrincipal`
* `removeCall`
* `impairLoan`
* `removeLoanImpairment`

**Pool Manager Permissioned Functions**

* `triggerDefault`

**Loan Permissioned Functions**

* `claim`
