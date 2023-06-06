# Audits

## December 2022 Release
Maple Finance V2 went through 3 audits during its development for the December 2022 release, details of which you can find below. All relevant issues identified by auditors were addressed prior to the launch of V2.

| Auditor | Report Link |
|---|---|
| Trail of Bits | [`2022-08-24 - Trail of Bits Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10246688/Maple.Finance.v2.-.Final.Report.-.Fixed.-.2022.pdf) |
| Spearbit | [`2022-10-17 - Spearbit Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10223545/Maple.Finance.v2.-.Spearbit.pdf) |
| Three Sigma | [`2022-10-24 - Three Sigma Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10223541/three-sigma_maple-finance_code-audit_v1.1.1.pdf) |

<br>

## June 2023 Release
Maple Finance V2 went through 2 audits during its development for the June 2023 release, details of which you can find below. All relevant issues identified by auditors were addressed prior to release.

| Auditor | Report Link |
|---|---|
| Spearbit Auditors via Cantina | [`2023-06-05 - Cantina Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/11667848/cantina-maple.pdf) |
| Three Sigma | [`2023-04-10 - Three Sigma Report`](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/11663546/maple-v2-audit_three-sigma_2023.pdf) |

# Bug Bounty

Maple V2 has an active bug bounty to incentive whitehat hackers to report any issues discovered in the protocol to allow for the opportunity for a patch to be made before the exploit is performed by a malicious actor. For all information related to the ongoing bug bounty for these contracts run by [Immunefi](https://immunefi.com/), please visit this [site](https://immunefi.com/bounty/maple/).

# Invariants

In order to discuss critical monitoring first its important to be clear on the invariants that are asserted which can be found below.

```
* Fixed Term Loan
   * Invariant A: collateral balance >= collateral`
   * Invariant B: fundsAsset >= drawableFunds`
   * Invariant C: `collateral >= collateralRequired * (principal - drawableFunds) / principalRequested`

* Fixed Term Loan Manager (non-liquidating)
   * Invariant A: domainStart <= domainEnd
   * Invariant B: sortedPayments is always sorted
   * Invariant C: outstandingInterest = ∑outstandingInterest(loan) (theoretical)
   * Invariant D: totalPrincipal = ∑loan.principal
   * Invariant E: issuanceRate = ∑issuanceRate(payment)
   * Invariant F: unrealizedLosses <= assetsUnderManagement
   * Invariant G: unrealizedLosses == 0
   * Invariant H: assetsUnderManagement == ∑loan.principal + ∑outstandingInterest(loan)
   * Invariant I: domainStart <= block.timestamp
   * Invariant J: if (loanManager.paymentWithEarliestDueDate != 0) then issuanceRate > 0
   * Invariant K: if (loanManager.paymentWithEarliestDueDate != 0) then domainEnd == paymentWithEarliestDueDate
   * Invariant L: refinanceInterest[payment] = loan.refinanceInterest
   * Invariant M: paymentDueDate[payment] = loan.paymentDueDate
   * Invariant N: startDate[payment] <= loan.paymentDueDate - loan.paymentInterval

* Open Term Loan
   * Invariant A: dateFunded <= datePaid, dateCalled, dateImpaired (if not zero)
   * Invariant B: datePaid <= dateImpaired (if not zero)
   * Invariant C: datePaid <= dateCalled (if not zero)
   * Invariant D: calledPrincipal <= principal
   * Invariant E: dateCalled != 0 -> calledPrincipal != 0
   * Invariant F: paymentDueDate <= defaultDate
   * Invariant G: getPaymentBreakdown == theoretical calculation

* Open Term Loan Manager
   * Invariant A: accountedInterest + accruedInterest == ∑loan.getPaymentBreakdown(block.timestamp) (minus fees)
   * Invariant B: if no payments exist: accountedInterest == 0
   * Invariant C: principalOut = ∑loan.principal
   * Invariant D: issuanceRate = ∑payment.issuanceRate
   * Invariant E: unrealizedLosses <= assetsUnderManagement
   * Invariant F: if no impairments exist: unrealizedLosses == 0
   * Invariant G: block.timestamp >= domainStart
   * Invariant H: payment.startDate == loan.dateFunded || loan.datePaid
   * Invariant I: payment.issuanceRate == theoretical calculation (minus management fees)
   * Invariant J: payment.impairedDate >= payment.startDate
   * Invariant K: assetsUnderManagement - unrealizedLosses - ∑outstandingValue(loan) ~= 0

* Pool (non-liquidating)
   * Invariant A: totalAssets > fundsAsset balance of pool
   * Invariant B: ∑balanceOfAssets == totalAssets (with rounding)
   * Invariant C: totalAssets >= totalSupply (in non-liquidating scenario)
   * Invariant D: convertToAssets(totalSupply) == totalAssets (with rounding)
   * Invariant E: convertToShares(totalAssets) == totalSupply (with rounding)
   * Invariant F: balanceOfAssets[user] >= balanceOf[user]
   * Invariant G: ∑balanceOf[user] == totalSupply
   * Invariant H: convertToExitShares == convertToShares
   * Invariant I: totalAssets == poolManager.totalAssets
   * Invariant J: unrealizedLosses == poolManager.unrealizedLosses
   * Invariant K: convertToExitShares == poolManager.convertToExitShares

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
   * Invariant M: lockedLiquidity <= pool.totalAssets
   * Invariant N: lockedLiquidity <= totalCycleShares[exitCycleId[user]] * exchangeRate
```

# Critical Monitoring

Maple Finance makes use of a custom smart contract to check invariants on-chain, using data from both smart contracts and sub-graph to assert invariants on a Loan, Pool and LP level. This is all managed using [Tenderly Web3 Actions](https://docs.tenderly.co/web3-actions/intro-to-web3-actions). Every block, all invariants are checked atomically using the deployed contract. If any of the invariants fail, a critical [Pager Duty incident](https://support.pagerduty.com/docs/incidents) is created. This will notify all on-call members of the incident response team immediately, and also includes a pre-defined escalation policy. In addition, Tenderly will use webhooks to send a message to the team's internal Slack channel with further information about how the invariant has failed.

# Informational Monitoring

Similarly to critical monitoring, Tenderly is used to notify the team whenever transactions are made against any of the protocols contracts in order to have real-time insights into protocol usage. Examples would include a Loan being funded or a Pool Delegate changing a withdrawal configuration.

Additionally all smart contracts get programmatically verified on Etherscan via the use of custom Tenderly web3 actions.

# Emergency Pause Function

In the case of a critical incident, a multisig is able to trigger a protocol pause. This function can temporarily disable almost all functions in the Maple protocol. This will allow for the incident response team to address the situation and minimize any potential harm that would be done. More information on the Emergency Pause function is outlined on this [page](../security/emergency-protocol-pause-function.md).

# Oracle/Flash Loan Protections

Maple Finance has implemented a number of protections to mitigate the risk of flash loans and front-running attacks. These protections are outlined below.

1. Chainlink Oracles - Maple Finance uses Chainlink oracles to provide price feeds for the protocol. Chainlink oracles are decentralized and provide a high level of security and reliability. In addition, Chainlink oracles are designed to be resistant to flash loan attacks since they provide price data from off-chain sources. More information on Chainlink oracles can be found [here](https://docs.chain.link/).
2. Oracle Wrappers - Maple Finance uses oracle wrappers to provide additional security and reliability to the Chainlink oracles. Oracle wrappers are designed to prevent oracle outages and oracle manipulation from causing issues in the protocol, specifically during liquidations.
3. Minimum Liquidation Price - The minimum liquidation price is a parameter that is set by the Pool Delegate. This parameter is used to prevent liquidations from occurring when the price of the collateral is too low. This is done to prevent flash loan attacks from being able to liquidate collateral at unfair prices.
4. Withdrawal Cooldowns - With withdrawal cooldowns, LPs are required to wait a certain amount of time before they can withdraw their funds. This is done to prevent flash loan attacks from being able to front-run LPs and deposit and withdraw funds to profit unfairly from discrete increases in pool value.

# Front-Running Protections
Every ERC-20 asset has a `bootstrapMint` amount that is set by the Governor. This is to prevent attackers from front-running the first depositor in a Pool to get an unfair distribution of Pool value. Outlines of this exploit can be found [here](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10223545/Maple.Finance.v2.-.Spearbit.pdf) under finding 5.1.1.
