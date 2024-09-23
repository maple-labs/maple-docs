# MPL Migration

## Converting MPL to SYRUP: A Guide for MPL Holders

## Background:

* MIP-009 was voted into place by the community on 12th September 2023.
* MIP-009 approved the issuance of new tokens to the Maple Treasury via a one-time mint and a three-year emission. [Read More](https://snapshot.org/#/maple.eth/proposal/0x29fccc3bac63744a55f9671399c079594e6b8369a21502cbce52e7dce9301094).
* Subsequently, on 2nd September 2024, MIP-010 was approved.&#x20;
* MIP-010 will initiate the launch of SYRUP token, a 1 MPL to 100 SYRUP token conversion, and staking rewards. [Read More](https://snapshot.org/#/maple.eth/proposal/0x6f2a2a4fb2e80bfc2f134cd79a0ebb2a0a6c2e2d11e6a5a49db2fc7b4588a5ec).&#x20;

**Summary**:

* Maple is making arrangements with major exchanges so that MPL tokens on the exchange will automatically be converted into SYRUP with no action required from holders. We will share details relevant to each exchange ahead of the migration.
* Conversion from MPL to SYRUP is encouraged, and will enable SYRUP token holders to support the SYRUP ecosystem and accumulate more tokens through staking.

## Converting MPL to SYRUP

All MPL is eligible to convert to SYRUP in Q4 after SYRUP token launch. This includes all MPL held in wallets decentralized exchanges, smart contracts (except xMPL), and centralized exchanges not covered in the summary.&#x20;

**Hold MPLv1 in a smart contract, wallet, multisig or with a custodian? Follow these steps to convert**

1. Go to [app.maple.finance/#/mpl](app.maple.finance#/mpl).
2. Connect your wallet.
   * Safe users may use the Maple Application found in the Safe App Store.
   * Argent and other multi-sig users will need to connect to the Maple Application via Wallet Connect.
3. Approve your MPLv1 tokens: Once your wallet is connected, you'll need to authorize the use of your MPLv1 tokens for the conversion.
4. Specify the conversion amount: Enter the amount of MPLv1 tokens you wish to convert. If you'd like to convert all your MPLv1 tokens, simply select the 'max' option.
5. Wait for the conversion to complete: After confirming the conversion the migration will take place, you can monitor the progress of the transaction on etherscan.
6. Show MPLv2 in your wallet by adding the token address: 0x1915A8dE08A92b846dF7C845e140E4b0714820bd

## Hold xMPL? Follow these steps to convert

Good news, xMPL holders will not need to take any steps to convert their MPLv1 to MPLv2. All MPLv1 in the xMPL contract will be converted to MPLv2 automatically by the 25th of September.

xMPL holders will only need to add the new MPLv2 token to their wallet. To show MPLv2 in a wallet add token address: 0x1915A8dE08A92b846dF7C845e140E4b0714820bd.

## Hold MPLv1 on an exchange?

Maple has made arrangements with major exchanges so that MPLv1 tokens on the exchange will automatically be converted into MPLv2. We will share details relevant to each exchange ahead of the 25th September.

## FAQs

**Why should I migrate my MPL tokens?**

Within 3 years all MPLv1 will be converted to MPLv2. To take part in Maple governance and all future utility holders must upgrade to MPLv2. MPLv1 will be delisted on exchanges and replaced with MPLv2 trading pairs.

**Is it safe to convert MPLv1 to MPLv2?**

Maple has taken every step to ensure that it is safe to convert MPLv1 to MPLv2 at a smart contract level. Firstly, the MPLv2 contract has been audited by Spearbit via Cantina and 3Sigma. The auditors assessed the MPLv2 smart contracts and the migration process. Secondly, the new token contract has undergone formal verification, the highest standard in smart contract security, which determines that the logic and desired behavior of the smart contract is satisfactory. The audit reports are available for review here: [https://github.com/maple-labs/mplv2/tree/main/audits](https://github.com/maple-labs/mplv2/tree/main/audits).

**What if my MPLv1 is on an exchange?**

Maple is in liaison with centralized exchanges to ensure smooth transition to MPLv2 and will advise on the specific processes for different venues closer to the time. The aim is that MPLv1 tokens on exchanges will automatically be converted into MPLv2 requiring no action from holders.

**What if I hold MPL in a Sablier stream?**

MPLv1 that is streamed via Sablier will not be migrated automatically to MPLv2. The holder will have to follow the steps outlined in the 'How to Guide'.

**What if I hold MPL and xMPL?**

xMPL will be migrated over automatically, no action is required there. For MPL, follow the steps outlined in the 'How to guide'.

**How do I add MPLv2 to my wallet?**

Show MPLv2 in your wallet by adding the token address: 0x1915A8dE08A92b846dF7C845e140E4b0714820bd

**How do I vote with MPLv2 after?**

The same voting process applies for MPLv2 as for MPLv1.

**Where will MPLv1 go?**

All MPLv1 tokens will be burned and replaced by the new MPLv2 tokens.

**How long will I have to migrate from v1 to v2?**

Holders will have 3 years to complete the conversion from MPLv1 to MPLv2. Holders are encouraged to complete the conversion as soon as possible to access the value and utility of MPL. MPLv1 will have no value once this process has commenced.



To fuel the next wave of growth for Maple, MIP-010 proposes the launch of SYRUP token, conversion of MPL to SYRUP, and the introduction of SYRUP staking. This latest proposal follows on from MIP-009, which recapitalised the Maple Treasury and helped the protocol launch key growth initiatives.

As part of this launch, 1 MPL will convert to 100 SYRUP, with no dilution for existing MPL token holders. The split is expected to accelerate the distribution of SYRUP tokens, by presenting a more approachable option for the crypto ecosystem.

The launch of [Syrup.fi](http://syrup.fi/) has given the Maple community permissionless access to its core institutional lending product through DeFi. In order to share the growth of Maple and [Syrup.fi](http://syrup.fi/) with the community, Core Contributors are proposing the implementation of staking rewards.

Fee revenues generated from Maple’s and Syrup’s lending operations will be used to buy back the SYRUP token, which will form part of the token emissions that go to stakers. In the first 90 days after token launch, a fixed amount of SYRUP emissions will go to SYRUP stakers, ensuring that all early stakers are incentivised with a staking yield for participating actively in the growth of the protocol.

As part of the implementation, the Syrup protocol will mint approximately 1.15 billion SYRUP.

Annualised recapitalisation would follow the same schedule as passed in [MIP-009](https://community.maple.finance/t/mip-009-upgrade-mpl-token-design/300); all issuance from the initial schedule will also be minted as SYRUP tokens, broken down as follows:

1. 1,000,000,000 (new SYRUP supply)
2. 100,000,000 (initial 10% from inflation schedule)
3. 54,930,000 (from inflation schedule till 1st Oct 2024)

A migrator contract will be deployed to allow MPL users to convert to SYRUP, and all issuance and emissions related to [MIP-009](https://community.maple.finance/t/mip-009-upgrade-mpl-token-design/300) will also be minted as SYRUP tokens.

For token holders, the migration is simple:

* MPL holders enter the Syrup webapp and connect their wallet
* Token holders can convert directly to staked SYRUP (stSYRUP)
* stSYRUP holders immediately begin receiving staking yield

We’re excited to build on Maple and Syrup’s recent growth by strengthening and expanding the community. This proposal will help Maple reach new markets and more widely distribute the benefits of Maple’s consistent, high yield!
