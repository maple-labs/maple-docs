# syrupUSDC and syrupUSDT - Risk Disclosures

### Important Notice

This document describes the material risks associated with syrupUSDC and syrupUSDT (collectively, the "SyrupUSD Tokens"). It is intended to provide a clear, consolidated overview of the risks involved in depositing into and holding SyrupUSD Tokens. This document does not constitute financial, legal, or investment advice. You should consult your own advisors before making any decision to use the SyrupUSD Tokens.

In this document, "the Issuer" refers to Maple International Operations SPC, a Segregated Portfolio Company registered in the Cayman Islands, which issues the SyrupUSD Tokens through its segregated portfolios. "The Interface Operator" refers to Syrup Ltd, which operates the interface at app.maple.finance/earn. Together, the Issuer and the Interface Operator are referred to as "the Company" where the context applies to both. "The Services" refers to the interface and related services as defined in the Interface Terms of Use.

By depositing into or holding SyrupUSD Tokens, you acknowledge that you have read, understood, and accepted the risks described in this document and in the Interface Terms of Use.

### 1. Product Overview and Nature of the SyrupUSD Tokens

#### 1.1 What are syrupUSDC and syrupUSDT?

syrupUSDC and syrupUSDT are tokenized representations of a lender's deposit in a pool of assets managed through the Maple Protocol. When you deposit USDC or USDT, you receive syrupUSDC or syrupUSDT tokens, which represent your proportional share of the pool's underlying assets. The value of these tokens accrues over time as the pool earns yield from its underlying activities.

#### 1.2 What syrupUSDC and syrupUSDT Are Not

The SyrupUSD Tokens are not stablecoins and are not backed by USDC or USDT on a one-to-one basis. They are not sponsored, endorsed, administered by, or otherwise associated with Circle Internet Financial, LLC ("Circle") or Tether Limited. The value of SyrupUSD Tokens is derived from a dynamic pool of underlying assets, including loans and other yield-generating strategies, and may fluctuate. There is no guarantee that you will be able to redeem your SyrupUSD Tokens for the amount of USDC or USDT you originally deposited.

#### 1.3 How Yield is Generated

The yield associated with SyrupUSD Tokens is generated from two primary sources:

1. Overcollateralized Lending. Interest payments on overcollateralized loans originated to institutional borrowers, governed by Master Lending Agreements with posted collateral.
2. Supporting Yield Strategies. Capital may also be allocated to supporting yield strategies, including but not limited to futures basis trading, other delta-neutral or market-neutral approaches, and liquidity provision in decentralized finance protocols.

Past performance is not indicative of future results, and yields are not guaranteed. The yield rate may vary and could be zero or negative in adverse market conditions.

### 2. Economic and Financial Risks

#### 2.1 Credit and Default Risk

SyrupUSD Tokens provide exposure to loans originated to institutional counterparties. While these loans are overcollateralized and governed by Master Lending Agreements, each loan is subject to the risk of borrower default.

**What happens if a borrower defaults?**\
If a borrower fails to make a required payment past the applicable grace period, Maple may execute a default on the loan. This will:

1. Reduce the pool's value by the amount of outstanding principal on the loan and any accrued interest.
2. Trigger the liquidation of any collateral posted against the loan, with the proceeds returned to the pool.

If the liquidated collateral does not fully cover the outstanding loan amount, the pool will incur a net loss. This loss is shared proportionally among all lenders in the pool, meaning the value of your SyrupUSD Tokens will decrease. In a severe scenario involving multiple simultaneous defaults, you could lose a substantial portion or all of your deposited principal.

#### 2.2 Impairment Risk

In addition to formal defaults, Maple has the ability to impair loans where it believes a borrower may be unable to repay, even before a technical default has occurred. Impairment is a protective mechanism designed to distribute potential losses fairly among all current lenders and prevent a "run on the pool" scenario.

**What happens when a loan is impaired?**

When a loan is impaired, its value is temporarily reduced within the pool. This has the following consequences:

* **If you withdraw during an impairment:** You will receive your capital minus the impairment loss. This loss is permanent for you, and you will have no claim to any future recoveries on that loan.
* **If you remain in the pool:** If the borrower subsequently repays, the impairment is reversed and the pool value is restored. If the borrower does not repay, the loan proceeds to default and the collateral liquidation process described above.
* **If you deposit during an impairment:** Your deposit will be affected by the existing impairment. If the loan is repaid, you will be made whole, but you will not have a claim to recoveries forfeited by lenders who withdrew during the impairment.

#### 2.3 Liquidity and Withdrawal Risk

Withdrawals from the syrupUSDC and syrupUSDT pools are facilitated via a queue-based Withdrawal Manager and are processed on a first-in, first-out basis as liquidity becomes available.

**What happens if liquidity is constrained?**

While withdrawals are currently processed on average in less than 24 hours, this is not guaranteed. In periods of high withdrawal demand or low pool liquidity (for example, if a large portion of pool assets are deployed in active loans or strategies), withdrawal processing times may be significantly longer. There is no guaranteed maximum withdrawal period.

Additionally, if a loan impairment or default occurs while your withdrawal is pending, the value of your withdrawal may be reduced to reflect the pool's diminished value.

#### 2.4 Market and Pricing Risk

The value of the collateral securing loans in the pool, and the value of assets deployed in yield strategies, are subject to market fluctuations. Rapid or significant declines in collateral value may result in undercollateralized loans, increasing the risk of loss in the event of a default. Similarly, the value of assets held in DeFi liquidity provision strategies may be affected by market movements, including impermanent loss.

**What happens if collateral value drops sharply?**

Maple employs margin call and liquidation procedures to manage collateral risk. If the value of a borrower's collateral falls below required thresholds, Maple may issue a margin call requiring the borrower to post additional collateral. If the borrower fails to do so, the collateral may be liquidated. However, in extreme market conditions, the liquidation proceeds may be insufficient to cover the outstanding loan, resulting in a loss to the pool.

### 3. Trading Strategy Risks

Capital deployed through syrupUSDC and syrupUSDT may be allocated to trading strategies, including but not limited to futures basis trading and other delta-neutral or market-neutral approaches, as well as liquidity provision in decentralized finance protocols. Such deployments carry inherent risks distinct from lending activities, including:

* **Counterparty and Exchange Risk.** The risk that a centralized exchange or trading counterparty becomes insolvent, restricts withdrawals, or experiences operational failures, resulting in a loss of funds deployed on that platform.
* **Basis Spread Compression or Inversion.** Futures basis trading strategies depend on a positive spread between spot and futures prices. If this spread compresses or inverts, the strategy may generate reduced or negative returns.
* **Forced Liquidation.** Under adverse market conditions, positions held as part of trading strategies may be forcibly liquidated by exchanges or protocols, potentially at unfavorable prices.
* **DeFi Protocol Risk.** Liquidity provision in decentralized finance protocols carries risks including smart contract vulnerabilities in the underlying protocol, liquidity constraints, and impermanent loss.

Trading strategy allocations are subject to the same governance, monitoring, and disclosure standards applicable to primary lending operations. Current allocations are transparently visible in the Liquidity section of the syrupUSDC/syrupUSDT Details page.

### 4. Smart Contract and Technical Risks

#### 4.1 Smart Contract Risk

The Maple Protocol operates through a set of smart contracts deployed on public blockchains. Smart contracts are software programs that execute automatically when certain conditions are met. While the Maple team takes smart contract security seriously and has engaged multiple independent auditors (including Spearbit, Three Sigma, and 0xMacro), no audit can guarantee the absence of vulnerabilities.

**What could go wrong?**

A vulnerability in the smart contract code could potentially be exploited by a malicious actor, resulting in the loss of funds deposited in the protocol. Smart contracts increase their risk profile with the amount of value they hold. Transactions on blockchains are generally irreversible, meaning that funds lost due to a smart contract exploit may not be recoverable.

More information on Maple's security practices and audit reports can be found in the [Security section](https://docs.maple.finance/technical-resources/security) of the Maple documentation.

#### 4.2 Oracle and Price Feed Risk

The Maple Protocol and its associated strategies may rely on oracles or price feeds to determine the value of collateral, trigger margin calls, or execute liquidations. Oracles are third-party services that provide external data (such as asset prices) to smart contracts.

**What could go wrong?**

If an oracle provides inaccurate, delayed, or manipulated price data, it could result in:

* Failure to trigger a margin call or liquidation when one is warranted, leading to undercollateralized loans.
* Incorrect liquidation of a borrower's collateral when it should not have been liquidated.
* Mispricing of assets within yield strategies, leading to suboptimal execution or losses.

#### 4.3 Dependency and Composability Risk

The SyrupUSD Tokens and the Maple Protocol interact with and depend on several external systems and assets, including:

* **Underlying Stablecoins (USDC, USDT).** The SyrupUSD Tokens are denominated in USDC and USDT, which are themselves subject to issuer risk (e.g., the risk that Circle or Tether cannot honor redemptions), regulatory risk, and the risk of de-pegging from their intended value.
* **Blockchain Infrastructure (Ethereum and others).** The protocol operates on Ethereum and other blockchains. Network congestion, high gas fees, hard forks, or consensus failures on these networks could impair the functioning of the protocol or delay transactions.
* **Third-Party DeFi Protocols.** Where capital is deployed into third-party DeFi protocols for yield strategies, the SyrupUSD Tokens inherit the risks of those protocols, including their own smart contract risks, governance risks, and operational risks.
* Bridge and Crosschain Risk. For users interacting with SyrupUSD Tokens on chains other than Ethereum (e.g., Solana, Arbitrum, Base), the crosschain mint/redeem mechanism introduces additional risks, including bridge security vulnerabilities and potential delays or failures in crosschain message passing.

A failure, exploit, or adverse event in any of these dependencies could result in a partial or total loss of funds, even if the Maple Protocol itself is functioning correctly.

### 5. Administrative and Governance Risks

#### 5.1 Admin Controls and Upgradeability

The Maple DAO has administrative controls over certain aspects of the protocol. These include:

* **Smart Contract Upgradeability.** The Maple DAO can approve new versions of smart contracts for use within the protocol. Upgrades can only be performed by the relevant authorized actor and only to versions that have been approved by the DAO. This mechanism is designed to prevent both the DAO and individual borrowers from unilaterally upgrading to malicious contract versions.
* **Parameter Changes.** The Maple DAO can modify certain protocol parameters, such as withdrawal cooldown periods. Timelock requirements may be applied to sensitive functions to ensure that changes cannot be made instantaneously, providing users with notice and the opportunity to react.

While these controls are designed to protect the protocol and its users, they also introduce the risk that administrative actions (whether well-intentioned or otherwise) could adversely affect lenders. For example, changes to withdrawal parameters could temporarily restrict your ability to withdraw funds.

#### 5.2 Multi-Signature Wallet Risk

Certain protocol functions are controlled by multi-signature wallets ("MultiSigs"). While some MultiSig signatories may be employed or engaged by the Issuer or the Interface Operator, others may be unaffiliated third parties. Neither the Issuer nor the Interface Operator can guarantee the actions or inactions of unaffiliated MultiSig members, and adverse actions by MultiSig members could impact the protocol's operation.

#### 5.3 Governance Risk

Decisions about the protocol's development, parameter settings, and strategic direction are made through governance processes. These processes carry the risk that decisions may be made that are not in the best interest of all users, or that governance mechanisms may be exploited or manipulated.

### 6. Legal and Regulatory Risks

#### 6.1 Regulatory Uncertainty

The regulatory regimes governing blockchain technologies, cryptocurrencies, and other digital assets are uncertain and evolving. New regulations or policies in any jurisdiction may materially adversely affect the utility or value of the SyrupUSD Tokens, the ability of the Issuer or the Interface Operator to continue providing the Services, or the legal status of the protocol's activities. You are encouraged to consult with your own legal and tax advisors regarding the implications of using the SyrupUSD Tokens in your jurisdiction.

#### 6.2 Jurisdictional Restrictions

syrupUSDC and syrupUSDT are not available to individuals or entities in certain restricted jurisdictions, including but not limited to the United States, Australia, and other sanctioned or restricted territories. A full list of restricted jurisdictions is maintained in the [Available Jurisdictions](https://docs.maple.finance/legal/syrupusdc-and-syrupusdt-available-jurisdictions) section. Accessing or using the SyrupUSD Tokens from a restricted jurisdiction is a violation of the Terms of Use.

#### 6.3 Entity Structure

The SyrupUSD Tokens are issued through Maple International Operations SPC, a Segregated Portfolio Company registered in the Cayman Islands. The segregated portfolio structure means that the assets and liabilities of each segregated portfolio are ring-fenced by statute. Lender claims are exclusively against the assets of the specific segregated portfolio in which they have deposited, and the assets of one portfolio cannot be used to satisfy the liabilities of another. This structure is designed to protect lenders from cross-portfolio contagion, but it also means that your recourse in the event of a loss is limited to the assets within the relevant portfolio.

#### 6.4 Tax Risk

The tax treatment of transactions involving cryptocurrencies and digital assets, including the SyrupUSD Tokens, is uncertain in many jurisdictions. You are solely responsible for determining and fulfilling your tax obligations in connection with your use of the SyrupUSD Tokens.

### 7. User Responsibilities and Prohibited Conduct

#### 7.1 Assumption of Risk

By using the SyrupUSD Tokens, you represent that you have sufficient knowledge and experience in business and financial matters, including a sufficient understanding of blockchain technologies, cryptocurrencies, and decentralized finance, to evaluate the risks and benefits described in this document. You acknowledge that you bear the risks of your participation, including the risk of complete loss of your deposited assets.

The SyrupUSD Tokens are not deposits of, or guaranteed by, a bank. They are not insured by the FDIC or any other governmental agency. No advice or information obtained from the Issuer, the Interface Operator, or through the Services constitutes investment advice or a recommendation to participate.

#### 7.2 Prohibited Conduct and Market Integrity

Users of the SyrupUSD Tokens and the Maple Protocol are prohibited from engaging in any conduct that undermines the integrity or fair operation of the protocol, including but not limited to:

* **Market Manipulation.** Any attempt to artificially inflate, deflate, or otherwise manipulate the price, value, or market for the SyrupUSD Tokens, underlying assets, or collateral through wash trading, spoofing, layering, or any other deceptive or manipulative practice.
* **Exploitation of Protocol Mechanics.** Any attempt to exploit vulnerabilities, design features, or unintended behaviors in the protocol's smart contracts or infrastructure for personal gain at the expense of other users.
* **Front-Running and Sandwich Attacks.** Any use of non-public information or transaction ordering strategies to extract value from other users' transactions.
* **Circumvention of Controls.** Any attempt to circumvent jurisdictional restrictions, KYC requirements, withdrawal limits, or other controls implemented by the protocol.

Violation of these prohibitions may result in restriction of access to the Services and may be referred to relevant authorities. The Issuer and the Interface Operator each reserve the right to take any action deemed necessary to protect the integrity of the protocol and its users.

#### 7.3 No Reliance

You acknowledge that neither the Issuer nor the Interface Operator brokers trading orders on your behalf, matches orders, or offers any financial products for sale or distribution. Neither the Issuer nor the Interface Operator facilitates the execution or settlement of your transactions, which occur entirely on public distributed blockchains. All actions you take utilizing the Services are considered unsolicited, and neither the Issuer nor the Interface Operator conducts a suitability review of any such action.

### 8. Additional Information

#### 8.1 Intellectual Property Notice

Third-party trademarks, including "USDC" (a registered trademark of Circle) and "USDT" (a trademark of Tether), are the property of their respective owners. The use of such trademarks herein is for identification and descriptive purposes only and does not imply any affiliation with or endorsement by the trademark holders.

#### 8.2 Updates to This Document

This document may be updated from time to time to reflect changes in the protocol, its risk profile, or applicable regulations. It is your responsibility to review this document periodically for updates.

#### 8.3 Contact

For questions about the risks described in this document, please contact [support@maple.finance](mailto:support@maple.finance).

This document is for informational purposes only and does not constitute legal, financial, or investment advice. It is not a substitute for your own independent analysis and due diligence.<br>
