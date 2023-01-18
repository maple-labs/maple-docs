# Overview

MapleGlobals is a singleton contract used to save system-wide parameters that all Pool must abide to, and is also used to control time-locked actions, such as upgrades and pauseablilty.

# Permissioning

The governor multisig is the only entity allowed to change the parameters stored in MapleGlobals, the only exception is scheduling upgrade calls which can also be done by Pool Delegates.

# Pausing

A system-wide pause flag is stored in the MapleGlobals and, in case of an emergency, the SecurityAdmin multisig can can call `setProtocolPause()`, which immediately takes effect in all protocol contracts. This doesn't necessarily mean that all functions are disallowed, here is a [list of the unaffected functions.](../security/emergency-protocol-pause-function.md)

A more granular approach is planned to be developed in the future, that allows pausing specific parts or functionalities.

# Timelock Scheduling

To perform upgrades in vital pool contracts, pool delegates need to first schedule upgrade calls in the globals contract and only after the pre-determined period has elapsed, that the actions can be triggered. More information on [timelocks](../admin-functions/timelocks.md).

# System Parameters

In this section, the parameters stored in the globals contract are outlined.

**Relevant Addresses**

* `MapleTreasury`
* `Governor`
* `SecurityAdmin` - Special account allowed to trigger protocol-wide pause.
* `MigrationAdmin` - Special account used during the liquidity migration.
* Factories, such as:
  * `LiquidatorFactory`
  * `LoanFactory`
  * `LoanManagerFactory`
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
