# Risk

Maple is a technology services provider. Use of the Maple Protocol involves risks, including but not limited to Smart Contract Risk, Default Risk, and Risk of Loss.

### Admin Controls

The Maple DAO has administrative controls over certain aspects of the protocol. The upgradeability mechanism allows for the Maple DAO to specify new versions of smart contracts that have been approved for use. These upgrades can only be performed by the relevant actor (e.g., PoolDelegate can upgrade Pools, Borrower can upgrade Loans). This ensures two things, one that the DAO cannot behave directly maliciously and two that the Pool Delegate and Borrower cannot upgrade to a malicious version of the smart contract. They can only perform upgrades to contracts that have been approved by the Maple DAO.

In addition, the Maple DAO has the ability to introduce timelock requirements to sensitive functions that a PoolDelegate can call, such as setting new withdrawal cooldown parameters. This ensures that the Pool Delegate cannot maliciously change the withdrawal cooldown parameters to a undesirably high value, which would allow them to hold LPs' funds for a longer period of time.

### Contagion Risk

As with all pools on Maple, the Cash Management Pool represents a distinct smart contract and Lenders are ringfenced from credit risk in other pools on the Maple platform. Although certain borrowers on the Maple platform experienced credit events in the aftermath of 2022, Maple's infrastructure consistently performed as designed and any losses were confined to their respective pools.

### Smart Contract Risk

Smart contracts increase their risk profile with the amount of value they hold. The Maple team takes this threat very seriously and has audited the protocol code both internally and externally. The most recent version of the smart contracts has been audited by [Spearbit](https://spearbit.com/), [Three Sigma](https://threesigma.xyz/labs/code-audits) and [Trail of Bits](https://www.trailofbits.com/).

### Default Risk

Maple is not a lender, but the Maple Protocol facilitates undercollateralized lending, and undercollateralized lending by nature carries a risk of defaults. Traditionally, lenders take borrowers through an underwriting process to mitigate this risk. Lending protocols available in DeFi today, such as Aave and Compound, require overcollateralization in order to prevent defaults from occurring.

The Maple Protocol enables more capital efficient, undercollateralized lending to occur by allowing Pool Delegates to use their own rigorous underwriting system in determining the creditworthiness of borrowers. If a borrower defaults, however, there may be a significant or complete loss of assets.

### Risk of Loss

Holding, lending, or borrowing digital assets involves a substantial degree of risk, including the risk of complete loss of those assets.
