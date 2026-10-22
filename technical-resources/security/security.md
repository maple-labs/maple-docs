# Security

## Audits

### December 2022 Release

The Maple protocol contracts went through 3 audits during its development for the December 2022 release, details of which you can find below. All relevant issues identified by auditors were addressed prior to the launch of V2.

| Auditor       | Report Link                                                                                                                                                                               |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Trail of Bits | [`2022-08 - Trail of Bits Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2022-december/TrailOfBits-Maple.pdf) |
| Spearbit      | [`2022-10 - Spearbit Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2022-december/Spearbit-maple.pdf)                   |
| Three Sigma   | [`2022-10 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2022-december/Three-Sigma-Maple-Finance-Dec-2022.pdf)   |




### June 2023 Release

The Maple protocol contracts went through 2 audits during its development for the June 2023 release, details of which you can find below. All relevant issues identified by auditors were addressed prior to release.

| Auditor                       | Report Link                                                                                                                                                                |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Spearbit Auditors via Cantina | [`2023-06 - Cantina Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-june/Cantina-Maple.pdf)                         |
| Three Sigma                   | [`2023-04 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-june/Three-Sigma-Maple-Finance-Jun-2023.pdf) |


### December 2023 Release

The Maple protocol contracts went through 2 audits during its development for the December 2023 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Three Sigma | [`2023-11 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-december/Three-Sigma-Maple-Finance-Dec-2023.pdf) |
| 0xMacro     | [`2023-11 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-december/0xMacro-Maple-Finance-Dec-2023.pdf)         |

### August 2024 Release

The Maple & Syrup protocol contracts went through 2 audits during its development for the August 2024 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Three Sigma | [`2024-08 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-august/Three-Sigma-Maple-Finance-Aug-2024.pdf) |
| 0xMacro     | [`2024-08 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-august/0xMacro-Maple-Finance-Aug-2024.pdf)         |
| ThreeSigma (Router) | [`2024-05 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-august/Three-Sigma-Maple-Finance-Aug-2024-Syrup.pdf) |

### December 2024 Release

The Maple & Syrup protocol contracts went through 2 audits during its development for the December 2024 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Three Sigma | [`2024-12 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-december/Three-Sigma-Maple-Finance-Dec-2024%20.pdf) |
| 0xMacro     | [`2024-12 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-december/0xMacro-Maple-Finance-Dec-2024.pdf)         |

### September 2025 Release

This release is for the Governor Timelock Contract upgrade. The Maple protocol contracts went through 2 audits during its development for the September 2025 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sherlock    | [`2025-09 - Sherlock Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2025-sept-governor-timelock/Sherlock-Maple-Finance-timelock-Sept-2025.pdf)         |
| 0xMacro     | [`2025-09 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2025-sept-governor-timelock/0xMacro-Maple-Finance-timelock-Sept-2025.pdf)         |


### November 2025 Release

The November 2025 release is for the Withdrawal Manager upgrade which introduces support to allow multiple pending requests per owner. The upgrade went through two audits by Spearbit and Sherlock. The audit reports can be seen below.

| Auditor  | Report Link |
| -------- | ----------- |
| Spearbit | [`2025-11 - Spearbit Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2025-november/Spearbit-Maple-Finance-WM-Nov-2025.pdf) |
| Sherlock | [`2025-11 - Sherlock Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2025-november/Sherlock-Maple-Finance-WM-Nov-2025.pdf) |

### January 2026 Release

The January 2026 release is for the Maple CCIP Receiver on Ethereum mainnet allowing crosschain deposits and redemptions for syrupUSDC.

| Auditor  | Report Link |
| -------- | ----------- |
| Dedaub | [`2025-11 - Dedaub Report`](https://github.com/maple-labs/maple-cross-chain-receiver/blob/main/audits/2025-november/Dedaub-Chainlink-Maple.pdf) |
| Sigma Prime | [`2026-01 - Sigma Prime Report`](https://github.com/maple-labs/maple-cross-chain-receiver/blob/main/audits/2026-january/SigmaPrime-Chainlink-Maple.pdf) |

### v7 Release (November 2026)

The November 2026 release replaces the one-to-one link between a Maple Pool and its strategies with shared strategies. A MaplePoolManager can now fund Strategy Managers, which combine capital from several Pool Managers into one underlying position. It does this alongside the strategies it owns directly; after the upgrade, the loans via Open Term Loan Manager remain the same.

| Auditor  | Report Link |
| -------- | ----------- |
| Sherlock | [`2026-09 - Sherlock Report`](https://drive.google.com/file/d/1WOQ8uYCD2F_ylKTc_ZjKh9myoYPV28Lw/view?usp=sharing) |
| Cantina| [`2026-10 - Cantina Report`](https://drive.google.com/file/d/1Cv1quA30NcqJFTo0JXCY9g7CNTZ47YMk/view?usp=sharing) |



## Bug Bounty

The Maple protocol has an active bug bounty to incentive whitehat hackers to report any issues discovered in the protocol to allow for the opportunity for a patch to be made before the exploit is performed by a malicious actor. For all information related to the ongoing bug bounty for these contracts run by [Immunefi](https://immunefi.com/), please visit this [site](https://immunefi.com/bounty/maple/). Behaviours listed on the [Known Issues and Operational Controls](known-issues-and-operational-controls.md) page are handled by operating procedure and are out of scope for the bounty.


## Critical Monitoring

Maple Finance makes use of a custom smart contract to check invariants on-chain, using data from both smart contracts and sub-graph to assert invariants on a Loan, Pool and LP level. This is all managed using [Tenderly Web3 Actions](https://docs.tenderly.co/web3-actions/intro-to-web3-actions). Every block, all invariants are checked atomically using the deployed contract. If any of the invariants fail, a critical [Pager Duty incident](https://support.pagerduty.com/docs/incidents) is created. This will notify all on-call members of the incident response team immediately, and also includes a pre-defined escalation policy. In addition, Tenderly will use webhooks to send a message to the team's internal Slack channel with further information about how the invariant has failed.

## Informational Monitoring

Similarly to critical monitoring, Tenderly is used to notify the team whenever transactions are made against any of the protocols contracts in order to have real-time insights into protocol usage. Examples would include a Loan being funded or a Pool Delegate changing a withdrawal configuration.

Additionally all smart contracts get programmatically verified on Etherscan via the use of custom Tenderly web3 actions.

## Emergency Pause Function

In the case of a critical incident, a multisig is able to trigger a protocol pause. This function can temporarily disable almost all functions in the Maple protocol. This will allow for the incident response team to address the situation and minimize any potential harm that would be done. More information on the Emergency Pause function is outlined on this [page](emergency-protocol-pause.md).

## Flash Loan and Front-Running Protections

No Pool or Strategy Manager reads a price oracle. The Aave V3 and Sky strategies value their positions from the balances those venues report, and open-term loans are accounted for at principal plus accrued interest, so there is no price feed to manipulate inside a transaction. Three mechanisms remove the remaining ways to profit from a sudden change in Pool value.

1. **Queue-based withdrawals.** A Lender cannot deposit and withdraw in the same transaction. `requestRedeem()` escrows the shares in the Withdrawal Manager, and the Pool Delegate, the Operational Admin or a registered redeemer processes the queue later with `processRedemptions()`. See [Withdrawal Manager](../pools/withdrawal-manager.md).
2. **Two exchange rates.** While a loan or strategy is impaired the Pool reports the expected loss as `unrealizedLosses()`. Deposits are priced with `convertToShares()` against `totalAssets()`, exits with `convertToExitShares()` against `totalAssets() - unrealizedLosses()`. A Lender who enters during an impairment pays the full price and one who exits bears their share of the pending loss, so nobody gains from timing an impairment or its removal. The Strategy Manager applies the same pair of rates to the Pool Managers that fund it through `convertToShares()` and `convertToExitShares()`. See [Exchange Rates](../pools/exchange-rates.md).
3. **Bootstrap mint.** Globals holds a `bootstrapMint` amount per asset, set by the Governor or the Operational Admin. On the first deposit into a Pool, `MaplePool` mints `BOOTSTRAP_MINT` shares to the zero address and the depositor receives the remainder. This stops an attacker from front-running the first Lender to inflate the share price, the exploit described under finding 5.1.1 of the [Spearbit 2022 report](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10223545/Maple.Finance.v2.-.Spearbit.pdf). In v7 the Strategy Deployer gives every Strategy Manager the same defence. It transfers the bootstrap amount from the Strategy Delegate into the underlying strategy, and `completeConfiguration()` records the resulting shares against the zero address, where nothing can redeem them. See [Strategy Deployer](../strategies/strategy-deployer.md).
