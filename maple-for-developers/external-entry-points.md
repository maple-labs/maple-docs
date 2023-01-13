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

### Loan
* `skim`

### Globals
* `scheduleCall` - Although publicly callable, only calls scheduled by Governor and PoolDelegates can have state changing capabilitiies.

### Liquidator
* `liquidatePortion` - Used by keepers to perform liquidations.

# Permissioned Functions

### Loan
**Borrower Permissioned Functions**
* `AcceptBorrower`
* `CloseLoan`
* `DrawdownFunds`
* `MakePayments`
* `PostCollateral`
* `ProposeNewTerms`
* `RemoveCollateral`
* `ReturnFunds`
* `SetPendingBorrower`

### Globals
**Governor Permissioned Functions**
* `activatePoolManager`
* `setMapleTreasury`
* `setMigrationAdmin`
* `setPriceOracle`
* `setSecurityAdmin`
* `setDefaultTimelockParameters`
* `setMigrationAdmin`
* `setValidBorrower`
* `setValidFactory`
* `setValidPoolAsset`
* `setValidPoolDelegate`
* `setValidPoolDeployer`
* `setManualOverridePrice`
* `setMinCoverAmount`
* `setMaxCoverLiquidationPercent`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setTimelockWindow`
* `setTimelockWindows`

**Security Admin Permissioned Functions**
* `setProtocolPause`

**Pool Delegate Permissioned Functions**
* `transferOwnedPoolManager`

### PoolManager
**Pool Delegate only functionality**
* `setPendingPoolDelegate`
* `acceptPendingPoolDelegate`
* `addLoanManager`
* `removeLoanManager`
* `setAllowedLender`
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setOpenToPublic`
* `setWithdrawalManager`
* `acceptNewTerms`
* `fund`
* `withdrawCover`

**Pool Delegate and Governor Permissioned Functions**
* `setAllowedSlippage`
* `setMinRatio`
* `impairLoan`
* `removeLoanImpairment`
* `finishCollateralLiquidation`
* `triggerDefault`

### LoanManager
**Pool Delegate and Governor Permissioned Functions**
* `updateAccounting`

### WithdrawalManager
**Pool Delegate only functionality**
* `setExitConfig`
