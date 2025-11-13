# Overview

Timelocks are a mechanism to delay an action that may have significant effects. This allows any stakeholders that foresee the transaction impacting them negatively the appropriate time to react accordingly.

# Governor-Level vs Pool-Delegate Timelocks

- Governor‑privileged actions now route through a dedicated `GovernorTimelock` contract. See `technical-resources/singletons/governor-timelock.md` for roles, lifecycle, and usage.
- Pool Delegate–level timelocks (e.g., PoolManager/LoanManager/WithdrawalManager upgrades) continue to use the protocol timelock checks documented on this page.

# Affected Actions

The following actions require a timelocked execution:
* `PoolManager.upgrade()`
* `LoanManager.upgrade()`
* `WithdrawalManager.upgrade()`

# Scheduling

To perform a timelocked action Pool Delegates need to perform the following actions:
1. Call `scheduleCall()` on the `MapleGlobals` contract.
2. Wait for the predetermined time to pass.
3. Call the target contract with the same parameters.

Example:
```
Pool Delegate wants to upgrade the poolManager to v2.

1. Call `globals.scheduleCall()`, passing the PoolManager address and the "upgrade" calldata properly encoded.
2. Wait for 2 weeks.
3. Call `upgrade` directly on the PoolManager.

The PoolManager contract will perform a check against Globals to ensure the call has been properly upgraded.
```

# Configuration

Timelocks parameters are set by the `Governor` and can be changed at any time, having a retroactive effect.

Example:
```
1. Current timelock is 2 weeks
2. Actor A schedules a call to a contract.
3. After 1 week, the Governor changes the time to be 1 week.
3. A can immediately call execute the contract, since it's been 1 week since the call was scheduled.
```
