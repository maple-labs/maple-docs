# Timelocked Functions

A timelock delays an action with significant effects so that anyone it affects has time to react. v7 uses two mechanisms.

| Mechanism | Who it applies to | Where it is enforced |
|---|---|---|
| Governor Timelock | Every Governor function | The `GovernorTimelock` contract, which is the Governor |
| Scheduled calls in Globals | Pool Delegate upgrades | `isValidScheduledCall` in `MapleGlobals`, checked by the target contract |

## Governor Timelock

The Governor address in Globals is the `GovernorTimelock` contract. Proposals are scheduled, wait out a delay, and are executed within a window. Every function on the [Governor](governor-admin-actions.md) page is delayed this way, including `PoolManager.addStrategyManager()`, `PoolManager.addStrategy()`, role and allowlist changes in Globals, and registering upgrade paths on factories. See [Governor Timelock](../singletons/governor-timelock.md) for roles and the proposal lifecycle.

## Scheduled calls in Globals

### Affected actions

* `LoanManager.upgrade()`, function id `LM:UPGRADE`, when the Pool Delegate calls it
* `WithdrawalManager.upgrade()`, function id `WM:UPGRADE`, when the Pool Delegate calls it

The Security Admin can call both functions without a scheduled call. Only the Security Admin can call `PoolManager.upgrade()`, with no scheduled call. Strategy Managers and strategies likewise have Security Admin only upgrades with no timelock.

### How the check works

1. The Pool Delegate calls `scheduleCall(contract, functionId, callData)` on Globals. Globals stores `block.timestamp` and `keccak256(abi.encode(callData))` under the caller, contract and function id.
2. After the delay, the Pool Delegate calls the target function with the same calldata.
3. The target calls `isValidScheduledCall(msg.sender, address(this), functionId, msg.data)`. The call is valid when `block.timestamp` is within `[timestamp + delay, timestamp + delay + duration]` and the calldata hash matches.
4. The target then calls `unscheduleCall(caller, functionId, callData)` so the same schedule cannot be reused.

The delay and duration come from `timelockParametersOf[contract][functionId]`. When that entry has a zero duration, `defaultTimelockParameters` applies.

```
Pool Delegate wants to upgrade a Withdrawal Manager to version 3.

1. Call globals.scheduleCall(withdrawalManager, "WM:UPGRADE", abi.encodeCall(upgrade, (3, arguments))).
2. Wait for the delay.
3. Call withdrawalManager.upgrade(3, arguments) before the window closes.
```

### Configuration

The Governor sets the windows with `setTimelockWindow`, `setTimelockWindows` and `setDefaultTimelockParameters`. Changes apply to calls that are already scheduled, because the check reads the current parameters at execution time. The Governor can also remove any scheduled call with the four-argument `unscheduleCall(caller, contract, functionId, callData)`.
