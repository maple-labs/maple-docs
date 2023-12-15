# Overview

MapleGlobals is a singleton contract used to save system-wide parameters that all Pool must abide to, and is also used to control time-locked actions, such as upgrades and pauseablilty.

# Permissioning

The governor multisig is the primary entity allowed to change the parameters stored in MapleGlobals. The operational admin, authorized by the Governor, can modify specific parameters and Security Admin can modify pause-related parameters.

# Pausing

A more granular approach was introduced in the June 2023 release with details found [here.](../security/emergency-protocol-pause.md).

1. Global pause
2. Per contract pause
3. Per function un-pause.

# Timelock Scheduling

To perform upgrades in vital pool contracts, pool delegates need to first schedule upgrade calls in the globals contract and only after the pre-determined period has elapsed, that the actions can be triggered. More information on [timelocks](../admin-functions/timelocks.md).

# Whitelisting Instance Deployment from Factories

The governor multisig can whitelist individual addresses that can use the `createInstance` functions at each factory respectively, which is then stored in the `_canDeployFrom` storage mapping. Factories can call `globals.canDeploy(addressOfCaller)` to determine if the caller is allowed to deploy one of its instances, and the mapping itself can be queried via `globals.canDeployFrom(addressOfFactory, addressOfCaller)`.

# System Parameters

In this section, the parameters stored in the globals contract are outlined.

**Relevant Addresses**

* `MapleTreasury`
* `Governor`
* `SecurityAdmin` - Special account allowed to trigger protocol-wide pause.
* `MigrationAdmin` - Special account used during the liquidity migration.
* `OperationalAdmin` - Special account given the authority by Governor to perform a subset of operational functions.
* Factories, such as:
  * `LiquidatorFactory`
  * `FixedTermLoanFactory`
  * `OpenTermLoanFactory`
  * `FixedTermLoanManagerFactory`
  * `OpenTermLoanManagerFactory`
  * `FixedTermRefinancer`
  * `OpenTermRefinancer`
  * `FeeManager`
  * `LiquidatorFactory`
  * `PoolManagerFactory`
  * `WithdrawalManagerFactory`
* Borrowers
* Pool Delegates
* Pool assets
* Price oracles for pool assets

**Pool Specific Parameters**

* `platformManagementFeeRate`
* `platformOriginationFeeRate`
* `platformServiceFeeRate`
* `minCoverAmount`
* `maxCoverLiquidationPercent`

# Proxy Architecture

The MapleGlobals contract make use of NonTransparentProxy, instead of the transparent proxy used almost everywhere in the Maple code base. The reasoning is to add an extra layer of security, making always possible to set the implementation, even if it was previously set to the wrong address beforehand.
