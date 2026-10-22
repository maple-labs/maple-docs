# Known Issues and Operational Controls

Some protocol behaviours are handled by operating procedure rather than by code. Each entry below describes the behaviour as the contracts implement it, what could go wrong, and the procedure Maple follows to prevent it. These behaviours are known and accepted, and they are out of scope for the [bug bounty](security.md#bug-bounty).

### Open-term loans are called before they are impaired

**Behaviour.** Any payment on an open-term loan clears an impairment, and the payment only has to include principal when the loan has been called (`makePayment()` requires `principalToReturn >= calledPrincipal`). An impaired loan that was never called can be cured with an interest-only payment.

**Risk.** A Borrower clears the impairment without returning principal, and the Pool's `unrealizedLosses` drop while the exposure remains.

**Control.** The Pool Delegate calls `callPrincipal()` for the full principal before `impairLoan()`, so the next payment due is the whole loan. See [Impairments](../strategies/open-term-loans/impairments.md).

### Allocation Strategy yield is cancelled before the last Pool withdraws

**Behaviour.** `realizeYield()` streams net yield into the strategy's assets over a duration. Yield that vests after the last Pool has redeemed accrues to the bootstrap shares held by the zero address.

**Risk.** That yield can never be redeemed. `skim()` cannot recover it either, because it is recorded in `recordedAssets`.

**Control.** Before the final redemption is processed, the Strategy Delegate or Security Admin calls `cancelYield()` to return the unvested yield to a Managed Wallet, and `realizeYield()` is not called while no Pool holds shares.

### Legacy Aave and Sky strategies are drained before a Pool is migrated

**Behaviour.** `MaplePoolManagerMigratorV500` removes every strategy that is not an Open Term Loan Manager from `strategyList`. It requires zero `assetsUnderManagement()` only for fixed-term loan managers.

**Risk.** Assets left in a pool-owned Aave or Sky strategy drop out of `totalAssets()` at migration and the Pool's share price falls.

**Control.** The migration runbook withdraws every legacy strategy to zero and checks the balance before the Pool Manager upgrade is executed. See [v7 Deployment and Upgrade](../releases/v7-deployment-and-upgrade.md).

### Strategy Managers and Pool Managers are created through their deployers

**Behaviour.** Until `completeConfiguration()` is called, a new Strategy Manager accepts `setUnderlyingStrategy()`, `setPoolManagerCap()` and `setStrategyLiquidityCap()` from any caller, and a new Pool Manager accepts `addStrategy()`, `addStrategyManager()`, `setWithdrawalManager()` and its other setters from any caller.

**Risk.** An instance created directly through its factory and not configured in the same transaction could be configured by anyone.

**Control.** `MapleStrategyDeployer.deploy()` and `MaplePoolDeployer` create, wire and complete configuration in one transaction. The factories only accept callers that Globals approves with `setCanDeployFrom()`, or `setValidPoolDeployer()` for the Pool Manager factory, and Maple approves only the deployer contracts for the Strategy Manager and underlying strategy factories.

### Globals holds a non-zero bootstrap amount before a strategy is deployed

**Behaviour.** `MapleStrategyDeployer` reads `bootstrapMint(fundsAsset)` from Globals. If it is zero the bootstrap step is skipped and the Strategy Manager is configured with no shares.

**Risk.** The first Pool to fund the Strategy Manager receives all shares at one asset per share, with no protection against share price manipulation.

**Control.** `setBootstrapMint()` for the asset is a checklist item before the first strategy deployment for that asset, and the release upgrade tests assert the configured amount for every supported asset.

### Strategy Manager redemption requests have no on-chain ordering

**Behaviour.** `requestRedeem()` records pending shares per Pool Manager. No queue or timestamp orders requests between Pools, and `processRedemption()` can settle any Pool's request in any amount.

**Risk.** A later request could be settled before an earlier one when liquidity is scarce.

**Control.** Operators process requests in the order they were made, as recorded by the `RedemptionRequested` events.

### Queued Lender withdrawals are not reserved on-chain

**Behaviour.** `MapleWithdrawalManager` computes what a request can redeem from the Pool's cash balance at processing time, and `requestFunds()` on the Pool Manager only checks the strategy cap. `lockedLiquidity()` always returns zero.

**Risk.** Funding a strategy after Lenders have queued leaves the queue partly unfilled until liquidity returns.

**Control.** Maple checks the withdrawal queue before funding strategies and processes the queue before deploying new liquidity.

### Operators clamp exit shares because `convertToExitShares()` rounds up

**Behaviour.** `convertToExitShares()` on the Pool and the Strategy Manager rounds up, so converting an asset amount can return one share more than the holder has.

**Risk.** `requestRedeem()` reverts with `MSM:RR:INSUFFICIENT_SHARES` when the computed shares exceed the Pool's balance.

**Control.** Operators clamp the requested shares to the balance returned by `sharesOf()` minus `pendingSharesOf()` before submitting.

### Aave strategy calls revert at 100% utilisation

**Behaviour.** `fundUnderlyingStrategy()`, `withdrawFromUnderlyingStrategy()`, `setStrategyDelegateFeeRate()` and `setStrategyProtocolFeeRate()` on `MapleAaveV3Strategy` harvest accrued fees first by withdrawing them from Aave. When the reserve has no free liquidity, Aave rejects the withdrawal and the call reverts. `availableToWithdraw()` returns zero in the same state.

**Risk.** Availability only. Funding and redemptions for that strategy wait until utilisation falls. No funds are at risk, and `impair()`, `recognizeLoss()` and `recoverPosition()` do not harvest, so they remain callable.

**Control.** Maple monitors reserve utilisation and retries once liquidity returns.

### Sky strategy calls revert while the PSM is halted

**Behaviour.** While the PSM's `tout` is `type(uint256).max`, which halts its `buyGem()` path, `MapleSkyStrategy` rejects `fundUnderlyingStrategy()` with `MSS:FUS:PSM_HALTED`, `setStrategyDelegateFeeRate()` with `MSS:SSDFR:PSM_HALTED` and `setStrategyProtocolFeeRate()` with `MSS:SSPFR:PSM_HALTED`. `withdrawFromUnderlyingStrategy()`, which also harvests fees, reverts because `_usdsForGem()` overflows at the halted `tout`. If the PSM's DaiJoin is caged, `fundUnderlyingStrategy()` reverts with `MSS:FUS:DAI_JOIN_CAGED`. In either state `availableToWithdraw()` returns zero, so `processRedemption()` on the Strategy Manager reverts with `MSM:PR:NOT_ENOUGH_LIQUIDITY`.

**Risk.** Availability only. Funding, redemptions and fee rate changes for that strategy wait until the PSM resumes. `impair()`, `recognizeLoss()` and `recoverPosition()` do not harvest, so they remain callable.

**Control.** Maple monitors the PSM and retries once it resumes. See [Funding and Withdrawals](../strategies/sky-strategy/funding-and-withdrawals.md).

### Funding reverts after a strategy's assets reach zero while shares remain

**Behaviour.** `fundStrategyManager()` prices new shares with `_convertToShares()`, which divides by `assetsUnderManagement()` when `totalShares` is non-zero. After a full loss the division by zero reverts.

**Risk.** Availability only. The Strategy Manager cannot be funded again.

**Control.** Maple does not reuse a Strategy Manager after a full loss. Each Pool detaches with `removeStrategyManager()`, which succeeds because `assetsOf()` is zero, and a new Strategy Manager is deployed if the venue is used again.

### Aave and Sky strategies forfeit unharvested fees on `recognizeLoss()`

**Behaviour.** `recognizeLoss()` on `MapleAaveV3Strategy` and `MapleSkyStrategy` sets `lastRecordedTotalAssets` to zero without harvesting first, and blocks every function that would harvest afterwards. `recoverPosition()` then sends the whole remaining aToken or sUSDS balance to the Maple Treasury.

**Risk.** Fees accrued since the last harvest are not paid to the Strategy Delegate. They go to the Treasury with the recovered position.

**Control.** Where the position still has value, a redemption is processed or a fee rate is changed before `recognizeLoss()` is called. Both harvest the accrued fees first.

### Redeeming from an impaired Strategy Manager realises the loss

**Behaviour.** `processRedemption()` pays the Pool at `convertToExitAssets()`, net of its share of `unrealizedLosses()`, and burns the Pool's shares.

**Risk.** The Pool gives up its claim on any recovery if the impairment is later removed, so a redemption during an impairment should only fund Lender withdrawals that are actually processed.

**Control.** Maple processes the Strategy Manager redemption and the Lender withdrawals it funds in one batch. While the batch runs, the Operational Admin can block Lenders from cancelling queued requests through the Pool Permission Manager, which gates `removeSharesById()` under the `WM:removeSharesById` function id.
