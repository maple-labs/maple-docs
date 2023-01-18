# Overview

The Governor is the main administrator of the protocol, and is managed by a multisig. The Governor controls administrative functions in the protocol, such as managing the MapleTreasury and defining global parameters. The main contract the Governor administers is [MapleGlobals](https://github.com/maple-labs/globals-v2/blob/main/contracts/MapleGlobals.sol) but it can also call administrative functions to manage Loans for a given Pool.

# Governor-Permissioned Functions

## Maple Globals

* `activatePoolManager`
* `setDefaultTimelockParameters`
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
* `setValidFactory`
* `setValidPoolAsset`
* `setValidPoolDelegate`
* `setValidPoolDeployer`

## PoolManager

* `finishCollateralLiquidation`
* `impairLoan`
* `removeLoanImpairment`
* `setAllowedSlippage`
* `setMinRatio`
* `triggerDefault`

## LoanManager

* `updateAccounting`

## Upgrading Contracts

The Governor is able to upgrade all upgradeable contracts in the protocol except for the Loan as the borrower is expected to upgrade the Loan implementation.
