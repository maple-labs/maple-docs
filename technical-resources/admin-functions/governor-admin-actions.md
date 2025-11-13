# Overview

The Governor is the main administrator of the protocol, and is managed by a multisig. The Governor controls administrative functions in the protocol, such as managing the MapleTreasury and defining global parameters. The main contract the Governor administers is [MapleGlobals](https://github.com/maple-labs/globals-v2/blob/main/contracts/MapleGlobals.sol) but it can also call administrative functions to manage Loans for a given Pool.

Note: Governor‑privileged transactions are executed through the `GovernorTimelock`. See `technical-resources/singletons/governor-timelock.md` for scheduling and execution flows.

# Governor-Permissioned Functions

## Globals

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
* `setOperationalAdmin`
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

Note: `setValidPoolDeployer` is deprecated for enabling deployers and only supports disabling. Use `setCanDeployFrom(factory, account, true)` together with `setValidInstanceOf(<FACTORY_KEY>, factory, true)` to allow deployments.

## PoolManager

* `addStrategy`
* `finishCollateralLiquidation`
* `setDelegateManagementFeeRate`
* `setIsStrategy`
* `setLiquidityCap`
* `setPendingPoolDelegate`
* `setPoolPermissionManager`
* `setWithdrawalManager` (only before initial configuration; callable prior to `completeConfiguration`)
* `triggerDefault`

## Fixed Term LoanManager

* `impairLoan`
* `removeLoanImpairment`
* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`

## Open Term Loan

* `skim`

## Open Term Loan Manager

* `impairLoan`
* `removeLoanImpairment`

## Pool Permission Manager

* `configurePool`
* `setLenderAllowlist`
* `setLenderBitmaps`
* `setPermissionAdmin`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

## Strategies Contracts

* `claimRewards` (Aave Strategy only)
* `deactivateStrategy`
* `impairStrategy`
* `reactivateStrategy`
* `setStrategyFeeRate`
* `setPsm` (Sky Strategy only)

## Upgrading Contracts

The Governor can upgrade the following contracts:
* Globals
* Liquidator
* Withdrawal Manager
