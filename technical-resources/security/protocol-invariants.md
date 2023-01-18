# Protocol Invariants

```
* Loan
   * Invariant A: collateral balance >= _collateral`
   * Invariant B: fundsAsset >= _drawableFunds`
   * Invariant C: `_collateral >= collateralRequired_ * (principal_ - drawableFunds_) / principalRequested_`

* Loan Manager (non-liquidating)
   * Invariant A: domainStart <= domainEnd
   * Invariant B: sortedPayments is always sorted
   * Invariant C: outstandingInterest = ∑outstandingInterest(loan) (theoretical)
   * Invariant D: totalPrincipal = ∑loan.principal()
   * Invariant E: issuanceRate = ∑issuanceRate(payment)
   * Invariant F: unrealizedLosses <= assetsUnderManagement()
   * Invariant G: unrealizedLosses == 0
   * Invariant H: assetsUnderManagement == ∑loan.principal() + ∑outstandingInterest(loan)
   * Invariant I: domainStart <= block.timestamp
   * Invariant J: if (loanManager.paymentWithEarliestDueDate != 0) then issuanceRate > 0
   * Invariant K: if (loanManager.paymentWithEarliestDueDate != 0) then domainEnd == paymentWithEarliestDueDate
   * Invariant L: refinanceInterest[payment] = loan.refinanceInterest()
   * Invariant M: paymentDueDate[payment] = loan.paymentDueDate()
   * Invariant N: startDate[payment] <= loan.paymentDueDate() - loan.paymentInterval()

* Pool (non-liquidating)
   * Invariant A: totalAssets > fundsAsset balance of pool
   * Invariant B: ∑balanceOfAssets == totalAssets (with rounding)
   * Invariant C: totalAssets >= totalSupply (in non-liquidating scenario)
   * Invariant D: convertToAssets(totalSupply) == totalAssets (with rounding)
   * Invariant E: convertToShares(totalAssets) == totalSupply (with rounding)
   * Invariant F: balanceOfAssets[user] >= balanceOf[user]
   * Invariant G: ∑balanceOf[user] == totalSupply
   * Invariant H: convertToExitShares == convertToShares
   * Invariant I: totalAssets == poolManager.totalAssets()
   * Invariant J: unrealizedLosses == poolManager.unrealizedLosses()
   * Invariant K: convertToExitShares == poolManager.converToExitShares()

PoolManager (non-liquidating)
   * Invariant A: totalAssets == cash + ∑assetsUnderManagement[loanManager]
   * Invariant B: hasSufficientCover == fundsAsset balance of cover > globals.minCoverAmount

Withdrawal Manager
   * Invariant A: WM LP balance == ∑lockedShares(user)
   * Invariant B: totalCycleShares == ∑lockedShares(user)[cycle] (for all cycles)
   * Invariant C: windowStart[currentCycle] <= block.timestamp
   * Invariant D: initialCycleTime[currentConfig] <= block.timestamp
   * Invariant E: initialCycleId[currentConfig] <= currentCycle
   * Invariant F: getRedeemableAmounts.shares[owner] <= WM LP balance
   * Invariant G: getRedeemableAmounts.shares[owner] <= lockedShares[user]
   * Invariant H: getRedeemableAmounts.shares[owner] <= totalCycleShares[exitCycleId[user]]
   * Invariant I: getRedeemableAmounts.assets[owner] <= fundsAsset balance of pool
   * Invariant J: getRedeemableAmounts.assets[owner] <= totalCycleShares[exitCycleId[user]] * exchangeRate
   * Invariant K: getRedeemableAmounts.assets[owner] <= lockedShares[user] * exchangeRate
   * Invariant L: getRedeemableAmounts.partialLiquidity == (lockedShares[user] * exchangeRate < fundsAsset balance of pool)
   * Invariant M: lockedLiquidity <= fundsAsset balance of pool
   * Invariant N: lockedLiquidity <= totalCycleShares[exitCycleId[user]] * exchangeRate
```
