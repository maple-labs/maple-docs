# Governor Timelock

**Overview**
- Replaces a Governor EOA with a contract-based timelock so all governor-privileged transactions execute after a delay.
- Separates responsibilities via roles and enforces a schedule → wait → execute lifecycle.
- Prevents immediate parameter and role changes. Certain meta‑changes are themselves timelocked.

**Key Roles**
- `PROPOSER_ROLE`: Schedules proposals via `scheduleProposals(...)` or `proposeRoleUpdates(...)`.
- `EXECUTOR_ROLE`: Executes queued proposals during their execution window via `executeProposals(...)`.
- `CANCELLER_ROLE`: Unschedules proposals via `unscheduleProposals(...)` (cannot unschedule role updates).
- `ROLE_ADMIN`: Proposes role changes using `proposeRoleUpdates(...)` and manages token withdrawer pending address.
- `tokenWithdrawer` (separate address): Can rescue ERC20 tokens accidentally sent to the timelock.

**Timelock Parameters**
- Defaults are set at deployment to at least `MIN_DELAY = 1 day` and `MIN_EXECUTION_WINDOW = 1 day`.
- Default parameters can be changed with `setDefaultTimelockParameters(delay, executionWindow)`. This function is `onlySelf` and must be executed via a timelocked proposal to the timelock itself.
- Per‑function overrides: `setFunctionTimelockParameters(target, selector, delay, executionWindow)` supports either both values set to zero (use defaults) or both meeting minimums. This function is `onlySelf` and must be timelocked.
- Changing a function’s timelock uses that function’s prior timelock parameters to gate the change (cannot reduce a delay instantly).

**Proposal Lifecycle**
- Schedule: `scheduleProposals(address[] targets, bytes[] data)` records proposals with `delayedUntil` and `validUntil` and computes a `proposalHash = keccak256(target, data)`.
- Role updates: Must be scheduled via `proposeRoleUpdates(bytes32[] roles, address[] accounts, bool[] shouldGrant)` (not via `scheduleProposals`). These cannot be unscheduled.
- Unschedule: `unscheduleProposals(uint256[] proposalIds)` allowed only when `isUnschedulable` is true (i.e., not role updates).
- Execute: `executeProposals(uint256[] ids, address[] targets, bytes[] data)` checks existence, timing window, and data hash, deletes the proposal, then calls the target with the exact `data`.
- Window semantics: Executable if `block.timestamp` is within `[delayedUntil, validUntil]` via `isExecutable(id)`.

**Security Notes**
- `onlySelf` gates sensitive meta‑operations (`updateRole`, timelock config), ensuring they can only be changed through the timelock.
- Binds execution to exact calldata via the stored `proposalHash`.
- Disallows scheduling to EOAs (`target.code.length > 0`).
- Role updates, once queued, cannot be unscheduled.

**Token Rescue**
- `setPendingTokenWithdrawer(new)` (ROLE_ADMIN) → `acceptTokenWithdrawer()` (new address) establishes the token withdrawer.
- `withdrawERC20Token(token, amount)` callable only by `tokenWithdrawer` to rescue funds sent to the timelock.

**Typical Workflows**
- Schedule and execute a MapleGlobals change:
  1) `scheduleProposals([globals], [abi.encodeWithSelector(globals.setPlatformServiceFeeRate.selector, newRate)])` (PROPOSER).
  2) Wait until `isExecutable(id)` returns true within the execution window.
  3) `executeProposals([id], [globals], [encodedData])` (EXECUTOR).
- Grant `EXECUTOR_ROLE` to a new account:
  1) `proposeRoleUpdates([EXECUTOR_ROLE], [newExecutor], [true])` (ROLE_ADMIN).
  2) After delay, `executeProposals([id], [timelock], [abi.encodeWithSelector(timelock.updateRole.selector, EXECUTOR_ROLE, newExecutor, true)])` (EXECUTOR).
- Set a per‑function override (e.g., extend delay for `globals.setPriceOracle`):
  1) Schedule `setFunctionTimelockParameters(globals, setPriceOracle.selector, 2 days, 1 day)` to the timelock (PROPOSER).
  2) Execute after the prior timelock for that function has elapsed (EXECUTOR).

**Events and Monitoring**
- `ProposalScheduled`, `ProposalExecuted`, `ProposalUnscheduled` for lifecycle transitions.
- `FunctionTimelockSet`, `DefaultTimelockSet` for configuration changes.
- `RoleUpdated` for access changes. `PendingTokenWithdrawerSet` and `TokenWithdrawerAccepted` for rescue admin.

**Deployment and Setup**
- Constructor arguments: `tokenWithdrawer`, `proposer`, `executor`, `canceller`, `roleAdmin`.
- Defaults initialize to minimums and can be increased later via timelocked calls.
- Recommended mapping:
  - Governance multisig: `PROPOSER_ROLE`, `EXECUTOR_ROLE`, `ROLE_ADMIN`.
  - Security/ops multisig: `CANCELLER_ROLE` (to unschedule non‑role proposals when needed).

**Context**
- This contract replaces a Governor EOA so that all governor‑privileged transactions are enforced to pass through a timelock.
- Pool Delegate–level timelocks (e.g., contract upgrades) remain documented separately. See `technical-resources/admin-functions/timelocks.md`.
