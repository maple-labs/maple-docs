# Security

## Audits

### December 2022 Release

The Maple protocol contracts went through 3 audits during its development for the December 2022 release, details of which you can find below. All relevant issues identified by auditors were addressed prior to the launch of V2.

| Auditor       | Report Link                                                                                                                                                                               |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Trail of Bits | [`2022-08-24 - Trail of Bits Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2022-december/TrailOfBits-Maple.pdf) |
| Spearbit      | [`2022-10-17 - Spearbit Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2022-december/Spearbit-maple.pdf)                   |
| Three Sigma   | [`2022-10-24 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2022-december/Three-Sigma-Maple-Finance-Dec-2022.pdf)   |




### June 2023 Release

The Maple protocol contracts went through 2 audits during its development for the June 2023 release, details of which you can find below. All relevant issues identified by auditors were addressed prior to release.

| Auditor                       | Report Link                                                                                                                                                                |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Spearbit Auditors via Cantina | [`2023-06-05 - Cantina Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-june/Cantina-Maple.pdf)                         |
| Three Sigma                   | [`2023-04-10 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-june/Three-Sigma-Maple-Finance-Jun-2023.pdf) |


### December 2023 Release

The Maple protocol contracts went through 2 audits during its development for the December 2023 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Three Sigma | [`2023-11-06 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-december/Three-Sigma-Maple-Finance-Dec-2023.pdf) |
| 0xMacro     | [`2023-11-27 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2023-december/0xMacro-Maple-Finance-Dec-2023.pdf)         |

### August 2024 Release

The Maple & Syrup protocol contracts went through 2 audits during its development for the August 2024 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Three Sigma | [`2024-08-23 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-august/Three-Sigma-Maple-Finance-Aug-2024.pdf) |
| 0xMacro     | [`2024-08-14 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-august/0xMacro-Maple-Finance-Aug-2024.pdf)         |
| ThreeSigma (Router) | [`2024-05-23 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-august/Three-Sigma-Maple-Finance-Aug-2024-Syrup.pdf) |

### December 2024 Release

The Maple & Syrup protocol contracts went through 2 audits during its development for the December 2024 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Three Sigma | [`2024-12-10 - Three Sigma Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-december/Three-Sigma-Maple-Finance-Dec-2024%20.pdf) |
| 0xMacro     | [`2024-12-20 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2024-december/0xMacro-Maple-Finance-Dec-2024.pdf)         |

### September 2025 Release

This release is for the Governor Timelock Contract upgrade. The Maple protocol contracts went through 2 audits during its development for the September 2025 release. Details of these audits can be found below, and all relevant issues identified by auditors were addressed prior to release.

| Auditor     | Report Link                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sherlock    | [`2025-09-10 - Sherlock Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2025-sept-governor-timelock/Sherlock-Maple-Finance-timelock-Sept-2025.pdf)         |
| 0xMacro     | [`2025-09-18 - 0xMacro Report`](https://github.com/maple-labs/maple-core-v2/blob/main/audits/2025-sept-governor-timelock/0xMacro-Maple-Finance-timelock-Sept-2025.pdf)         |




## Bug Bounty

The Maple protocol has an active bug bounty to incentive whitehat hackers to report any issues discovered in the protocol to allow for the opportunity for a patch to be made before the exploit is performed by a malicious actor. For all information related to the ongoing bug bounty for these contracts run by [Immunefi](https://immunefi.com/), please visit this [site](https://immunefi.com/bounty/maple/).


## Critical Monitoring

Maple Finance makes use of a custom smart contract to check invariants on-chain, using data from both smart contracts and sub-graph to assert invariants on a Loan, Pool and LP level. This is all managed using [Tenderly Web3 Actions](https://docs.tenderly.co/web3-actions/intro-to-web3-actions). Every block, all invariants are checked atomically using the deployed contract. If any of the invariants fail, a critical [Pager Duty incident](https://support.pagerduty.com/docs/incidents) is created. This will notify all on-call members of the incident response team immediately, and also includes a pre-defined escalation policy. In addition, Tenderly will use webhooks to send a message to the team's internal Slack channel with further information about how the invariant has failed.

## Informational Monitoring

Similarly to critical monitoring, Tenderly is used to notify the team whenever transactions are made against any of the protocols contracts in order to have real-time insights into protocol usage. Examples would include a Loan being funded or a Pool Delegate changing a withdrawal configuration.

Additionally all smart contracts get programmatically verified on Etherscan via the use of custom Tenderly web3 actions.

## Emergency Pause Function

In the case of a critical incident, a multisig is able to trigger a protocol pause. This function can temporarily disable almost all functions in the Maple protocol. This will allow for the incident response team to address the situation and minimize any potential harm that would be done. More information on the Emergency Pause function is outlined on this [page](emergency-protocol-pause.md).

## Oracle/Flash Loan Protections

Maple Finance has implemented a number of protections to mitigate the risk of flash loans and front-running attacks. These protections are outlined below.

1. Chainlink Oracles - Maple Finance uses Chainlink oracles to provide price feeds for the protocol. Chainlink oracles are decentralized and provide a high level of security and reliability. In addition, Chainlink oracles are designed to be resistant to flash loan attacks since they provide price data from off-chain sources. More information on Chainlink oracles can be found [here](https://docs.chain.link/).
2. Oracle Wrappers - Maple Finance uses oracle wrappers to provide additional security and reliability to the Chainlink oracles. Oracle wrappers are designed to prevent oracle outages and oracle manipulation from causing issues in the protocol, specifically during liquidations.
3. Minimum Liquidation Price - The minimum liquidation price is a parameter that is set by the Pool Delegate. This parameter is used to prevent liquidations from occurring when the price of the collateral is too low. This is done to prevent flash loan attacks from being able to liquidate collateral at unfair prices.
4. Withdrawal Cooldowns - With withdrawal cooldowns, LPs are required to wait a certain amount of time before they can withdraw their funds. This is done to prevent flash loan attacks from being able to front-run LPs and deposit and withdraw funds to profit unfairly from discrete increases in pool value.

## Front-Running Protections

Every ERC-20 asset has a `bootstrapMint` amount that is set by the Governor. This is to prevent attackers from front-running the first depositor in a Pool to get an unfair distribution of Pool value. Outlines of this exploit can be found [here](https://docs.google.com/viewer?url=https://github.com/maple-labs/maple-v2-audits/files/10223545/Maple.Finance.v2.-.Spearbit.pdf) under finding 5.1.1.
