---
hidden: true
---

# Staking Smart Contract Details

#### **Contract Overview** <a href="#contract-overview" id="contract-overview"></a>

The staking smart contract is decentralized and non-custodial, meaning no third party takes possession of, actively manages, or controls staked tokens. Further, no party holds the private keys for the staking contract; it is decentralized.

Staked SYRUP remains idle in a non-custodial, decentralized smart contract - with no third-party control or private key ownership - and can be unstaked at anytime.

The main source of revenue for the protocol comes from the collection of management and service fees. Management sees are the portion of lender interest that is taken by protocol for facilitating loan origination, and service fees are paid by the borrowers as part of their overall cost of borrowing, which includes interest.

All fees accrue on a block by block basis and paid to the protocol through the smart contracts each time a borrower interest payment is made. The fees collected by the treasury can then be used to buyback SYRUP, which can be distributed to all Stakers, along with a portion of the inflation, using the following mechanism:

<figure><img src="https://syrup.gitbook.io/~gitbook/image?url=https%3A%2F%2F3301920378-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fk2ME5rSJehBu8OHZwxXq%252Fuploads%252FnsrgxShZETl16EqHc6bv%252Fimage.png%3Falt%3Dmedia%26token%3D173b89d8-5102-42c0-acc9-9448a13c185c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f7123271&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Technical Specifications** <a href="#technical-specifications" id="technical-specifications"></a>

stSyrup implements the [ERC-4626 Tokenized Vault Standard](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-4626.md) and inherits its core functionality from Maple's [Revenue Distribution Token](https://github.com/maple-labs/revenue-distribution-token) (RDT). The [ERC-4626](https://eips.ethereum.org/EIPS/eip-4626) standard enables the creation of tokenized vaults representing shares of a single underlying ERC-20 token - in this case stSYRUP.

The RDT is Maple's implementation of the Tokenized Vault Standard. In this standard, revenue from staking rewards is distributed linearly to users that have staked their Syrup tokens.

The linear issuance mechanism means value accrues to SYRUP continuously, with no incentives to enter and exit the smart contract based on large expected distributions. Rewards are simply distributed to users continually based on their share of the staking pool. The issuance rate is the amount of SYRUP issued per second to all stakers.

More technical information regarding stSYRUP can be found in our [Github](https://github.com/maple-labs/stSyrup/wiki).

#### Calculating stSYRUP Issuance Rate <a href="#calculating-stsyrup-issuance-rate" id="calculating-stsyrup-issuance-rate"></a>

Please note the issuance rate of SYRUP rewards being distributed returned by `issuanceRate()` is scaled by 18. This means to calculate the issuance rate in SYRUP tokens per second, you must divide the issuance rate returned by `issuanceRate()` by 18.

#### **Security and Audit** <a href="#security-and-audit" id="security-and-audit"></a>

The Maple Labs team that developed the Maple and Syrup smart contracts places the highest emphasis on security. The Maple protocol contracts went through 7+ audits during its development for Maple v2, which represents the underlying infrastructure for Syrup, SYRUP token, and stSYRUP.

Audit details can be found in our [Github](https://github.com/maple-labs/mplv2?tab=readme-ov-file#audit-reports), [Gitbook](https://maplefinance.gitbook.io/maple/technical-resources/security/security) and in this [article](https://maple.finance/news/security-of-syrup).
