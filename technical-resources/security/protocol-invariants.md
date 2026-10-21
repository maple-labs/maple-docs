# Protocol Invariants

```
* Open Term Loan
   * Invariant A: dateFunded <= datePaid, dateCalled, dateImpaired (if not zero)
   * Invariant B: datePaid <= dateImpaired (if not zero)
   * Invariant C: datePaid <= dateCalled (if not zero)
   * Invariant D: calledPrincipal <= principal
   * Invariant E: dateCalled != 0 -> calledPrincipal != 0
   * Invariant F: paymentDueDate() <= defaultDate()
   * Invariant G: getPaymentBreakdown == theoretical calculation

* Open Term Loan Manager
   * Invariant A: accountedInterest + accruedInterest() == ∑loan.getPaymentBreakdown(block.timestamp) (minus fees)
   * Invariant B: if no payments exist: accountedInterest == 0
   * Invariant C: principalOut = ∑loan.principal()
   * Invariant D: issuanceRate = ∑payment.issuanceRate
   * Invariant E: unrealizedLosses <= assetsUnderManagement()
   * Invariant F: if no impairments exist: unrealizedLosses == 0
   * Invariant G: block.timestamp >= domainStart
   * Invariant H: payment.startDate == loan.dateFunded() || loan.datePaid()
   * Invariant I: payment.issuanceRate == theoretical calculation (minus management fees)
   * Invariant J: payment.impairedDate >= payment.startDate
   * Invariant K: assetsUnderManagement - unrealizedLosses - ∑outstandingValue(loan) ~= 0
   * Invariant L: fundsAsset.balanceOf(OTLM) == 0
   * Invariant M: fundsAsset.allowance(OTLM, address(loan)) == 0

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
   * Invariant K: convertToExitShares == poolManager.convertToExitShares()

* PoolManager (non-liquidating)
   * Invariant A: totalAssets == cash + ∑assetsUnderManagement[strategy]
   * Invariant B: totalAssets >= unrealizedLosses

* Pool Permission Manager
   * Invariant A: pool.permissionLevel ∈ [0, 3]
   * Invariant B: pool.bitmap ∈ [0, MAX]
   * Invariant C: lender.bitmap ∈ [0, MAX]
   * Invariant D: pool.permissionLevel == public -> permanently public

* Withdrawal Manager (Queue)
   * Invariant A: ∑request.shares + ∑owner.manualShares == totalShares
   * Invariant B: balanceOf(this) >= totalShares
   * Invariant C: ∀ requestId(owner) != 0 -> request.shares > 0 && request.owner == owner
   * Invariant D: nextRequestId <= lastRequestId + 1
   * Invariant E: nextRequestId != 0
   * Invariant F: requests(0) == (0, 0)
   * Invariant G: ∀ requestId[lender] ∈ [0, lastRequestId]
   * Invariant H: requestId is unique
```
