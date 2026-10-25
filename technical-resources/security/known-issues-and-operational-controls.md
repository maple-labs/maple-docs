# Known Issues and Operational Controls

Some protocol behaviours are handled by operating procedure rather than by code. Each entry below describes the behaviour as the contracts implement it, what could go wrong, and the procedure Maple follows to prevent it. These behaviours are known and accepted, and they are out of scope for the [bug bounty](security.md#bug-bounty).

## Pools and withdrawals

### Deposits during an impairment are priced on gross assets

**Behaviour.** A Pool prices deposits with `convertToShares()` on `totalAssets()`, and exits with `convertToExitAssets()` on `totalAssets()` minus `unrealizedLosses()`. `processRedemptions()` on the Withdrawal Manager pays queued requests at the exit price when it runs.

**Risk.** A Lender who deposits while a Pool carries unrealized losses pays the gross price. The deposit raises the exit price for every other Lender, and the new Lender shares the loss if it is recognised.

**Control.** Pools price the two sides differently by design, so that no one can deposit cheaply just before an impairment is removed. See [Exchange Rates](../pools/exchange-rates.md). `unrealizedLosses()` and `convertToExitAssets()` are public, so a Lender can see an impairment before depositing. Maple accepts that a deposit made during an impairment carries this risk.

### Queued Lender withdrawals are not reserved on-chain

**Behaviour.** `MapleWithdrawalManager` computes what a request can redeem from the Pool's cash balance at processing time, and `requestFunds()` on the Pool Manager only checks the strategy cap. `lockedLiquidity()` always returns zero.

**Risk.** Funding a strategy after Lenders have queued leaves the queue partly unfilled until liquidity returns.

**Control.** Maple checks the withdrawal queue before funding strategies and processes the queue before deploying new liquidity.

### Manual withdrawals count against queue liquidity

**Behaviour.** The Pool Delegate or Operational Admin can mark a Lender for manual withdrawal with `setManualWithdrawal()`. When `processRedemptions()` reaches that Lender's request, it adds the processed shares to `manualSharesAvailable` instead of redeeming them, and the Lender redeems them later. `processRedemptions()` still requires Pool cash for every share in the batch, manual or not, and reverts with `WM:PR:LOW_LIQUIDITY` otherwise.

**Risk.** A large manual request at the head of the queue can hold up the requests behind it, even when the Pool holds enough cash for them.

**Control.** Only addresses Maple marks can withdraw manually, and Maple uses it internally and for integrations it supports. The Pool Delegate decides how to handle a manual request at the head of the queue: process it over several smaller batches, remove it with `removeRequest()`, or leave it in place.

## Permissions

### Pool permissions check the Lender, not the caller

**Behaviour.** For deposits and mints, `canCall()` on the Pool Manager checks the permission of the address that receives the shares, not the caller. For redemptions and withdrawals it checks the owner of the shares, and for transfers it checks both the sender and the recipient.

**Risk.** An address without permission can deposit into a permissioned Pool on behalf of a permitted Lender, so a Pool can receive funds from any source.

**Control.** The design lets smart contracts that manage funds for Lenders integrate with Pools. Maple runs AML and KYC checks on Lenders in permissioned Pools, monitors high-risk addresses, works directly with Circle, and can remove withdrawal requests with `removeRequest()`.

### Unset permission bitmaps allow every Lender

**Behaviour.** At `POOL_LEVEL` and `FUNCTION_LEVEL`, the Pool Permission Manager allows a Lender when `(poolBitmap & lenderBitmap) == poolBitmap`. A bitmap that has not been set is zero, which every Lender matches.

**Risk.** Switching a Pool's permission level before its bitmaps are set opens the affected functions to every Lender.

**Control.** Maple sets the bitmaps in the same transaction as the permission level change. A zero bitmap is intentional where a function should be open to everyone, such as transfers and redemptions on syrupUSDC. See [Pool Permission Manager](../singletons/pool-permission-manager.md).

### Syrup Router authorisations stay valid until their deadline

**Behaviour.** `authorizeAndDeposit()` and `authorizeAndDepositWithPermit()` on the Syrup Router take a bitmap signed by a Permission Admin and write it as the Lender's bitmap in the Pool Permission Manager. The signature covers the Lender's nonce and a deadline, and nothing ties it to the bitmap the Lender holds when it is used.

**Risk.** A Lender holding an unused signature can submit it after a Permission Admin has reduced their bitmap, which restores the signed bitmap.

**Control.** This is intended. A signature works once, because the Lender's nonce increments on use, and only until its deadline.

## Open-term loans

### Open-term loans are called before they are impaired

**Behaviour.** Any payment on an open-term loan clears an impairment, and the payment only has to include principal when the loan has been called (`makePayment()` requires `principalToReturn >= calledPrincipal`). An impaired loan that was never called can be cured with an interest-only payment. Accepting new terms with `acceptNewTerms()` also clears both a call and an impairment.

**Risk.** A Borrower clears the impairment without returning principal, and the Pool's `unrealizedLosses` drop while the exposure remains.

**Control.** The Pool Delegate calls `callPrincipal()` for the full principal before `impairLoan()`, so the next payment due is the whole loan. Maple impairs loans through the Pool Delegate only. The Governor role belongs to the Governor Timelock, which Maple does not use for impairments. Only the Pool Delegate can propose new terms, and it can reject an outstanding proposal with `rejectNewTerms()`. See [Impairments](../strategies/open-term-loans/impairments.md).

### A pending Borrower is checked when proposed, not when accepted

**Behaviour.** `setPendingBorrower()` on an open-term loan requires the new address to be a valid Borrower in Globals. `acceptBorrower()` does not check again.

**Risk.** An address removed as a Borrower between the two calls can still accept and take over the loan.

**Control.** Maple vets every Borrower through due diligence before registering it, and accepts this risk.

## Strategy Managers

### Strategy Manager redemption requests have no on-chain ordering

**Behaviour.** `requestRedeem()` records pending shares per Pool Manager. No queue or timestamp orders requests between Pools, and `processRedemption()` can settle any Pool's request in any amount.

**Risk.** A later request could be settled before an earlier one when liquidity is scarce.

**Control.** Operators process requests in the order they were made, as recorded by the `RedemptionRequested` events.

### Operators clamp exit shares because `convertToExitShares()` rounds up

**Behaviour.** `convertToExitShares()` on the Pool and the Strategy Manager rounds up, so converting an asset amount can return one share more than the holder has.

**Risk.** `requestRedeem()` reverts with `MSM:RR:INSUFFICIENT_SHARES` when the computed shares exceed the Pool's balance.

**Control.** Operators clamp the requested shares to the balance returned by `sharesOf()` minus `pendingSharesOf()` before submitting.

### Funding reverts after a strategy's assets reach zero while shares remain

**Behaviour.** `fundStrategyManager()` prices new shares with `_convertToShares()`, which divides by `assetsUnderManagement()` when `totalShares` is non-zero. After a full loss the division by zero reverts.

**Risk.** Availability only. The Strategy Manager cannot be funded again.

**Control.** Maple does not reuse a Strategy Manager after a full loss. Each Pool detaches with `removeStrategyManager()`, which succeeds because `assetsOf()` is zero, and a new Strategy Manager is deployed if the underlying protocol is used again.

### Redeeming from an impaired Strategy Manager realises the loss

**Behaviour.** `processRedemption()` pays the Pool at `convertToExitAssets()`, net of its share of `unrealizedLosses()`, and burns the Pool's shares.

**Risk.** The Pool gives up its claim on any recovery if the impairment is later removed, so a redemption during an impairment should only fund Lender withdrawals that are actually processed.

**Control.** Maple processes the Strategy Manager redemption and the Lender withdrawals it funds in one batch. While the batch runs, the Operational Admin can block Lenders from cancelling queued requests through the Pool Permission Manager, which controls access to `removeSharesById()` under the `WM:removeSharesById` function id.

### Remaining Pools absorb what an exiting Pool forfeits during an impairment

**Behaviour.** When one Pool redeems from an impaired Strategy Manager, the amount it forfeits stays in the underlying strategy. Each remaining Pool's `assetsOf()` rises by its share of that amount, and its `unrealizedLossesOf()` rises by the same amount, so its net value does not change while the impairment is active.

**Risk.** The forfeited amount raises each remaining Pool's gross `totalAssets()`, and with it the deposit price described in [Deposits during an impairment are priced on gross assets](#deposits-during-an-impairment-are-priced-on-gross-assets). If the impairment is removed, the remaining Pools keep what the exiting Pool forfeited.

**Control.** While a strategy is impaired, only the Strategy Delegate or the Operational Admin can call `processRedemption()`. Maple accepts that the remaining Pools keep the forfeited amount if the impairment is removed.

## Strategies

### Allocation Strategy yield is cancelled before the last Pool withdraws

**Behaviour.** `realizeYield()` streams net yield into the strategy's assets over a duration. Yield that vests after the last Pool has redeemed accrues to the bootstrap shares held by the zero address.

**Risk.** That yield can never be redeemed. `skim()` cannot recover it either, because it is recorded in `recordedAssets`.

**Control.** Before the final redemption is processed, the Strategy Delegate or Security Admin calls `cancelYield()` to return the unvested yield to a Managed Wallet, and `realizeYield()` is not called while no Pool holds shares.

### Aave strategy calls revert when Aave liquidity is below accrued fees

**Behaviour.** `fundUnderlyingStrategy()`, `withdrawFromUnderlyingStrategy()`, `setStrategyDelegateFeeRate()` and `setStrategyProtocolFeeRate()` on `MapleAaveV3Strategy` harvest accrued fees first by withdrawing them from Aave. When the reserve's free liquidity is below the accrued fees, Aave rejects the withdrawal and the call reverts. `availableToWithdraw()` deducts accrued fees from that liquidity, so it returns zero in the same state.

**Risk.** Availability only. Funding and redemptions for that strategy wait until utilisation falls. The liquidity that remains is owed as fees, so none of it is available to Pools. No funds are at risk, and `impair()`, `recognizeLoss()` and `recoverPosition()` do not harvest, so they remain callable.

**Control.** Maple monitors reserve utilisation and retries once liquidity returns.

### Sky strategy calls revert while the PSM is halted

**Behaviour.** While the PSM's `tout` is `type(uint256).max`, which halts its `buyGem()` path, `MapleSkyStrategy` rejects `fundUnderlyingStrategy()` with `MSS:FUS:PSM_HALTED`, `setStrategyDelegateFeeRate()` with `MSS:SSDFR:PSM_HALTED` and `setStrategyProtocolFeeRate()` with `MSS:SSPFR:PSM_HALTED`. `withdrawFromUnderlyingStrategy()`, which also harvests fees, reverts because `_usdsForGem()` overflows at the halted `tout`. If the PSM's DaiJoin is caged, `fundUnderlyingStrategy()` reverts with `MSS:FUS:DAI_JOIN_CAGED`. In either state `availableToWithdraw()` returns zero, so `processRedemption()` on the Strategy Manager reverts with `MSM:PR:NOT_ENOUGH_LIQUIDITY`.

**Risk.** Availability only. Funding, redemptions and fee rate changes for that strategy wait until the PSM resumes. `impair()`, `recognizeLoss()` and `recoverPosition()` do not harvest, so they remain callable.

**Control.** Maple monitors the PSM and retries once it resumes. See [Funding and Withdrawals](../strategies/sky-strategy/funding-and-withdrawals.md).

### Sky strategy funding has no slippage bound

**Behaviour.** `fundUnderlyingStrategy()` on `MapleSkyStrategy` sells the funds asset to the PSM with `sellGem()` and sets no minimum output. The PSM's `tin` fee reduces the USDS received, and the Strategy Manager mints shares only for the value that reaches the strategy. The strategy values its position with the PSM's `tout`, so a change to `tout` changes that value at once.

**Risk.** A positive `tin` costs the funding Pool the fee as soon as the deposit executes. Sky governance sets both `tin` and `tout`.

**Control.** A Liquidity Bot submits strategy funding, so no multisig signing window sits between building a transaction and executing it. Sky executive spells pass a public delay before they execute. Maple tracks Sky governance and decides whether to withdraw liquidity before a fee change takes effect, and does not fund the Sky strategy while `tin` is positive.

### Aave and Sky fees are measured from the last harvest

**Behaviour.** Every function on `MapleAaveV3Strategy` and `MapleSkyStrategy` that harvests fees then sets `lastRecordedTotalAssets` to the position's current value. Fees accrue only on growth above `lastRecordedTotalAssets`, and no fee is taken while the position is below it.

**Risk.** A harvest while the position is below its recorded value resets the baseline to the lower value. The Strategy Delegate and the Maple Treasury then take fees on the recovery of value the Pools had already lost.

**Control.** Maple does not fund an Aave strategy that is impaired or below its recorded value, and does not run the Sky strategy while `tin` or `tout` is positive.

### Aave and Sky strategies forfeit unharvested fees on `recognizeLoss()`

**Behaviour.** `recognizeLoss()` on `MapleAaveV3Strategy` and `MapleSkyStrategy` sets `lastRecordedTotalAssets` to zero without harvesting first, and blocks every function that would harvest afterwards. `recoverPosition()` then sends the whole remaining aToken or sUSDS balance to the Maple Treasury.

**Risk.** Fees accrued since the last harvest are not paid to the Strategy Delegate. They go to the Treasury with the recovered position.

**Control.** Where the position still has value, a redemption is processed or a fee rate is changed before `recognizeLoss()` is called. Both harvest the accrued fees first.

## Deployment and governance

### Strategy Managers and Pool Managers are created through their deployers

**Behaviour.** Until `completeConfiguration()` is called, a new Strategy Manager accepts `setUnderlyingStrategy()`, `setPoolManagerCap()` and `setStrategyLiquidityCap()` from any caller, and a new Pool Manager accepts `addStrategy()`, `addStrategyManager()`, `setWithdrawalManager()` and its other setters from any caller.

**Risk.** An instance created directly through its factory and not configured in the same transaction could be configured by anyone.

**Control.** `MapleStrategyDeployer.deploy()` and `MaplePoolDeployer` create, wire and complete configuration in one transaction. The factories only accept callers that Globals approves with `setCanDeployFrom()`, or `setValidPoolDeployer()` for the Pool Manager factory, and Maple approves only the deployer contracts for the Strategy Manager and underlying strategy factories.

### Globals holds a non-zero bootstrap amount before a Pool or strategy is deployed

**Behaviour.** A new Pool and `MapleStrategyDeployer` both read `bootstrapMint(fundsAsset)` from Globals. The Pool stores the value as its immutable `BOOTSTRAP_MINT` and skips the bootstrap mint on its first deposit if it is zero. If it is zero when a strategy is deployed, the bootstrap step is skipped and the Strategy Manager is configured with no shares.

**Risk.** The first Lender in such a Pool, or the first Pool to fund such a Strategy Manager, receives shares with no protection against share price manipulation. Setting the amount later does not fix a Pool, because `BOOTSTRAP_MINT` is immutable.

**Control.** `setBootstrapMint()` for the asset is a checklist item before the first Pool or strategy deployment for that asset, and the release upgrade tests assert the configured amount for every supported asset.

### Upgrades can change the interfaces integrations call

**Behaviour.** Maple upgrades its contracts through proxy factories, and an upgrade can change function signatures and their selectors.

**Risk.** An integration compiled against an earlier interface can revert when it calls a function whose signature has changed.

**Control.** Only the Governor can register an implementation or enable an upgrade path, and the Governor is the [Governor Timelock](../singletons/governor-timelock.md). Each upgrade is public for the timelock delay before it executes, so integrators can review it and adapt. Each integrator is responsible for its own contracts.

### Governor Timelock token withdrawals are not delayed

**Behaviour.** `ROLE_ADMIN` on the Governor Timelock proposes a token withdrawer with `setPendingTokenWithdrawer()`, the proposed address accepts with `acceptTokenWithdrawer()`, and the token withdrawer can then call `withdrawERC20Token()` for any balance. None of these calls passes through the timelock delay.

**Risk.** The role admin can move any ERC-20 the timelock holds without the delay that applies to Governor actions.

**Control.** The token withdrawer exists to rescue tokens sent to the timelock by mistake, so its actions are not delayed by design. Maple managed multisigs hold the role admin role, as [Trust Assumptions](list-of-assumptions.md) describes.
