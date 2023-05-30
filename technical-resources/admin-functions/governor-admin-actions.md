# Overview

The Governor is the main administrator of the protocol, and is managed by a multisig. The Governor controls administrative functions in the protocol, such as managing the MapleTreasury and defining global parameters. The main contract the Governor administers is [MapleGlobals](https://github.com/maple-labs/globals-v2/blob/main/contracts/MapleGlobals.sol) but it can also call administrative functions to manage Loans for a given Pool.

# Governor-Permissioned Functions

## Maple Globals

* `activatePoolManager`
* `setCanDeployFrom`
* `setContractPause`
* `setDefaultTimelockParameters`
* `setFunctionUnpause`
* `setManualOverridePrice`
* `setMapleTreasury`
* `setMaxCoverLiquidationPercent`
* `setMigrationAdmin`
* `setMigrationAdmin`
* `setMinCoverAmount`
* `setPlatformManagementFeeRate`
* `setPlatformOriginationFeeRate`
* `setPlatformServiceFeeRate`
* `setPriceOracle`
* `setSecurityAdmin`
* `setTimelockWindow`
* `setTimelockWindows`
* `setValidBorrower`
* `setValidPoolAsset`
* `setValidPoolDelegate`
* `setValidPoolDeployer`
* `setProtocolPause`

## PoolManager

* `finishCollateralLiquidation`
* `triggerDefault`

## Fixed Term LoanManager

* `setAllowedSlippage`
* `setMinRatio`
* `updateAccounting`
* `impairLoan`
* `removeLoanImpairment`

## Open Term Loan

* `skim`

## Open Term Loan Manager

* `impairLoan`
* `removeLoanImpairment`

## Upgrading Contracts

The Governor can upgrade the following contracts:
* Liquidator
* Maple Globals
* Withdrawal Manager
