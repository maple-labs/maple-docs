# Audits

Maple Finance V2 went through 3 audits during its development details of which you can find below. All relevant issues identified by auditors were addressed prior to the launch of V2.

| Auditor | Report Link |
|---|---|
| Trail of Bits | [`2022-08-24 - Trail of Bits Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10246688/Maple.Finance.v2.-.Final.Report.-.Fixed.-.2022.pdf) |
| Spearbit | [`2022-10-17 - Spearbit Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10223545/Maple.Finance.v2.-.Spearbit.pdf) |
| Three Sigma | [`2022-10-24 - Three Sigma Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10223541/three-sigma_maple-finance_code-audit_v1.1.1.pdf) |

# Bug Bounty

Maple V2 has an active bug bounty to incentive whitehat hackers to report any issues discovered in the protocol to allow for the opportunity for a patch to be made before the exploit is performed by a malicious actor. For all information related to the ongoing bug bounty for these contracts run by [Immunefi](https://immunefi.com/), please visit this [site](https://immunefi.com/bounty/maple/).

# Invariants

In order to discuss critical monitoring first its important to be clear on the invariants that are asserted which can be found below.

     * Loan
        * Invariant A: collateral balance >= _collateral
        * Invariant B: fundsAsset >= _drawableFunds

     * Loan Manager (non-liquidating)
        * Invariant A: domainStart <= domainEnd
        * Invariant B: sortedPayments is always sorted
        * Invariant C: outstandingInterest = ∑outstandingInterest(loan) (theoretical)
        * Invariant D: totalPrincipal = ∑loan.principal()
        * Invariant E: issuanceRate = ∑issuanceRate(payment)
        * Invariant F: unrealizedLosses <= assetsUnderManagement()
        * Invariant H: assetsUnderManagement == ∑loan.principal() + ∑outstandingInterest(loan)
        * Invariant I: domainStart <= block.timestamp
        * Invariant J: if (loanManager.paymentWithEarliestDueDate != 0) then issuanceRate > 0
        * Invariant K: if (loanManager.paymentWithEarliestDueDate != 0) then domainEnd == paymentWithEarliestDueDate
        * Invariant L: refinanceInterest[payment] = loan.refinanceInterest()

     * Pool (non-liquidating)
        * Invariant A: totalAssets > fundsAsset balance of pool
        * Invariant B: ∑balanceOfAssets == totalAssets (with rounding)
        * Invariant D: convertToAssets(totalSupply) == totalAssets (with rounding)
        * Invariant E: convertToShares(totalAssets) == totalSupply (with rounding)
        * Invariant G: ∑balanceOf[user] == totalSupply
        * Invariant I: totalAssets == poolManager.totalAssets()
        * Invariant J: unrealizedLosses == poolManager.unrealizedLosses()
        * Invariant K: convertToExitShares == poolManager.convertToExitShares()

     * PoolManager (non-liquidating)
        * Invariant A: totalAssets == cash + ∑assetsUnderManagement[loanManager]
        * Invariant B: hasSufficientCover == fundsAsset balance of cover > globals.minCoverAmount

     * Withdrawal Manager
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
        * Invariant M: lockedLiquidity <= pool.totalAssets()
        * Invariant N: lockedLiquidity <= totalCycleShares[exitCycleId[user]] * exchangeRate

# Critical Monitoring

Maple Finance makes use of a custom smart contract to check invariants on-chain, using data from both smart contracts and sub-graph to assert invariants on a Loan, Pool and LP level. This is all managed using [Tenderly Web3 Actions](https://docs.tenderly.co/web3-actions/intro-to-web3-actions). Every block, all invariants are checked atomically using the deployed contract. If any of the invariants fail, a critical [Pager Duty incident](https://support.pagerduty.com/docs/incidents) is created. This will notify all on-call members of the incident response team immediately, and also includes a pre-defined escalation policy. In addition, Tenderly will use webhooks to send a message to the team's internal Slack channel with further information about how the invariant has failed.

# Informational Monitoring

Similarly to critical monitoring, Tenderly is used to notify the team whenever transactions are made against any of the protocols contracts in order to have real-time insights into protocol usage. Examples would include a Loan being funded or a Pool Delegate changing a withdrawal configuration.

Additionally all smart contracts get programmatically verified on Etherscan via the use of custom Tenderly web3 actions.

# Emergency Pause Function

In the case of a critical incident, a multisig is able to trigger a protocol pause. This function can temporarily disable almost all functions in the Maple protocol. This will allow for the incident response team to address the situation and minimize any potential harm that would be done. More information on the Emergency Pause function is outlined on this [page](../security/emergency-protocol-pause-function.md).
