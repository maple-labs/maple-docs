# Invariants

Properties of pools, Strategy Managers and strategies. A condition in brackets limits when a property holds. The stateful fuzz suite in `tests/invariants` asserts every property below after each randomised action, and Maple's on-chain health checkers re-check most of these properties every block, see [Critical Monitoring](security.md#critical-monitoring).

```
* Open Term Loan
   * Invariant A: dateFunded <= datePaid (if datePaid != 0)
   * Invariant B: dateFunded <= dateImpaired (if dateImpaired != 0)
   * Invariant C: dateFunded <= dateCalled (if dateCalled != 0)
   * Invariant D: datePaid <= dateImpaired (if both != 0)
   * Invariant E: datePaid <= dateCalled (if both != 0)
   * Invariant F: calledPrincipal <= principal
   * Invariant G: dateCalled == 0 <-> calledPrincipal == 0
   * Invariant H: paymentDueDate() <= defaultDate()
   * Invariant I: getPaymentBreakdown == theoretical calculation

* Open Term Loan Manager
   * Invariant A: assetsUnderManagement() ~= ∑(loan.principal() + expected net interest) (within 1e6)
   * Invariant B: assetsUnderManagement() ~= 0 (if no payments exist, within numLoans + 5,000)
   * Invariant C: principalOut = ∑loan.principal()
   * Invariant D: issuanceRate = ∑payment.issuanceRate (excluding impaired loans)
   * Invariant E: unrealizedLosses <= assetsUnderManagement() (with rounding)
   * Invariant F: if no impairments exist: unrealizedLosses == 0
   * Invariant G: block.timestamp >= domainStart
   * Invariant H: payment.startDate == loan.dateFunded() || loan.datePaid()
   * Invariant I: payment.issuanceRate == theoretical calculation (minus management fees)
   * Invariant J: impairmentFor(loan).impairmentDate >= paymentFor(loan).startDate (if impairmentDate != 0)
   * Invariant K: assetsUnderManagement - unrealizedLosses - ∑outstandingValue(loan) ~= 0
   * Invariant L: fundsAsset.balanceOf(OTLM) == 0
   * Invariant M: fundsAsset.allowance(OTLM, address(loan)) == 0

* Pool
   * Invariant A: totalAssets >= fundsAsset balance of pool
   * Invariant B: ∑balanceOfAssets == totalAssets (with rounding)
   * Invariant C: totalAssets >= totalSupply (when the Pool has no losses)
   * Invariant D: convertToAssets(totalSupply) == totalAssets (with rounding)
   * Invariant E: convertToShares(totalAssets) == totalSupply (with rounding)
   * Invariant F: balanceOfAssets[user] >= balanceOf[user] (when the Pool has no losses)
   * Invariant G: ∑balanceOf[user] == totalSupply
   * Invariant H: convertToExitShares == convertToShares (when the Pool has no losses)
   * Invariant I: totalAssets == poolManager.totalAssets()
   * Invariant J: unrealizedLosses == poolManager.unrealizedLosses()
   * Invariant K: convertToExitShares == poolManager.convertToExitShares()

* PoolManager
   * Invariant A: totalAssets == cash + ∑assetsOf(poolManager)[strategyManager] + ∑assetsUnderManagement[strategy]
   * Invariant B: unrealizedLosses <= totalAssets
   * Invariant C: totalAssets() and unrealizedLosses() never revert
   * Invariant D: isStrategy XOR isStrategyManager, ∀ strategyList entry
   * Invariant E: every strategyList address is unique

* Pool Permission Manager
   * Invariant A: pool.permissionLevel ∈ [0, 3]
   * Invariant B: pool.bitmap ∈ [0, MAX]
   * Invariant C: lender.bitmap ∈ [0, MAX]
   * Invariant D: pool.permissionLevel == public -> permanently public (enforced by the contract, not asserted by the suite)

* Withdrawal Manager
   * Invariant A: ∑request.shares + ∑owner.manualShares == totalShares
   * Invariant B: balanceOf(this) >= totalShares
   * Invariant C: ∀ requestId(owner) != 0 -> request.shares > 0 && request.owner == owner
   * Invariant D: nextRequestId <= lastRequestId + 1
   * Invariant E: nextRequestId != 0
   * Invariant F: requests(0) == (0, 0)
   * Invariant G: ∀ requestId[lender] ∈ [0, lastRequestId]
   * Invariant H: requestId is unique
   * Invariant I: ∀ owner, userEscrowedShares(owner) == ∑requestsByOwner(owner).shares
   * Invariant J: ∑owner.userEscrowedShares + ∑owner.manualSharesAvailable == totalShares
   * Invariant K: requestsByOwner lists are strictly increasing
   * Invariant L: requestsByOwner lists match active requests exactly

* Strategy Manager
   * Invariant A: assetsUnderManagement() == underlyingStrategy.assetsUnderManagement() && unrealizedLosses() == underlyingStrategy.unrealizedLosses()
   * Invariant B: unrealizedLosses() <= assetsUnderManagement()
   * Invariant C: totalShares == sharesOf(address(0)) + ∑sharesOf(poolManager)
   * Invariant D: totalPendingShares == ∑pendingSharesOf(poolManager)
   * Invariant E: pendingSharesOf(poolManager) <= sharesOf(poolManager)
   * Invariant F: totalShares >= sharesOf(address(0))
   * Invariant G: convertToExitAssets(totalShares) <= convertToAssets(totalShares)
   * Invariant H: ∑assetsOf(poolManager) <= assetsUnderManagement()
   * Invariant I: unrealizedLossesOf(address(0)) + ∑unrealizedLossesOf(poolManager) >= unrealizedLosses()

* Aave V3 Strategy
   * Invariant A: assetsUnderManagement() ~= ∑fundings + ∑yield - ∑withdrawals - ∑fees (skipped once isLossRecognized)
   * Invariant B: aToken.balanceOf(strategy) >= ∑fundings - ∑withdrawals - ∑fees (with rounding)
   * Invariant C: fundsAsset.balanceOf(strategy) == 0 (test only, a direct token transfer breaks it)
   * Invariant D: fundsAsset.allowance(strategy, aavePool) == 0
   * Invariant E: aToken.balanceOf(strategy) >= lastRecordedTotalAssets
   * Invariant F: assetsUnderManagement() >= lastRecordedTotalAssets
   * Invariant G: availableToWithdraw() <= assetsUnderManagement()
   * Invariant H: availableToWithdraw() <= aaveLiquidity
   * Invariant I: unrealizedLosses() <= assetsUnderManagement()
   * Invariant J: strategyDelegateFeeRate + strategyProtocolFeeRate <= 1e6

* Sky Strategy
   * Invariant A: assetsUnderManagement() ~= ∑fundings + ∑yield - ∑withdrawals - ∑fees (skipped once isLossRecognized)
   * Invariant B: usds.balanceOf(strategy) == fundsAsset.balanceOf(strategy) == 0 (test only, a direct token transfer breaks it)
   * Invariant C: allowance(strategy, psm) == allowance(strategy, savingsUsds) == 0
   * Invariant D: gemForUsds(usdsForGem(x)) ~= x
   * Invariant E: assetsUnderManagement() >= lastRecordedTotalAssets
   * Invariant F: availableToWithdraw() <= assetsUnderManagement()
   * Invariant G: availableToWithdraw() <= fundsAsset.balanceOf(psm.pocket())
   * Invariant H: unrealizedLosses() <= assetsUnderManagement()
   * Invariant I: strategyDelegateFeeRate + strategyProtocolFeeRate <= 1e6

* Allocation Strategy
   * Invariant A: assetsUnderManagement() == ∑fundings + ∑yield - ∑withdrawals - ∑fees - ∑losses - unrealizedYield()
   * Invariant B: fundsAsset.balanceOf(strategy) >= recordedAssets
   * Invariant C: totalDeployedAssets == ∑deployedAssetsOf(wallet)
   * Invariant D: deployedAssetsOf(wallet) == ∑deploys(wallet) - ∑returns(onBehalfOf = wallet) - ∑losses(wallet)
   * Invariant E: availableToWithdraw() <= assetsUnderManagement()
   * Invariant F: unrealizedLosses() <= assetsUnderManagement()
   * Invariant G: unrealizedYield() <= recordedAssets
   * Invariant H: unrealizedYield() <= scheduledYieldAssets
   * Invariant I: yieldLastRealized <= yieldStart <= yieldDeadline
   * Invariant J: strategyDelegateFeeRate + strategyProtocolFeeRate <= 1e6
```
