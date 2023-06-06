# Overview

The Governor is the main administrator of the protocol, and is managed by a multisig. The Governor controls administrative functions in the protocol, such as managing the MapleTreasury and defining global parameters. The main contract the Governor administers is [MapleGlobals](https://github.com/maple-labs/globals-v2/blob/main/contracts/MapleGlobals.sol) but it can also call administrative functions to manage Loans for a given Pool.

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

## PoolManager

* `finishCollateralLiquidation`
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

## Upgrading Contracts

The Governor can upgrade the following contracts:
* Globals
* Liquidator
* Withdrawal Manager
