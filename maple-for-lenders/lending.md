# Lending

Lending is the easiest way to earn with Maple Finance. Lenders deposit into a pool to earn interest denominated in the pool's liquidity asset. This interest is determined by the loan terms set by Maple's credit underwriting and risk management. Lenders will not need MPL tokens to participate in lending.

Lending Opportunities on Maple (called Pools) are permissioned. When Lenders complete KYC, their wallets are automatically added to Maple's Global Allowlist. This means that Lenders' wallets can access every Opportunity on Maple.

**Approvals**

The first time you lend an asset (e.g. USDC, wETH) to a pool, you will be prompted to allow the pool contract to interact with the asset. Once you approve the asset for the first time, you will not have to approve that asset for any additional deposits. This is a common transaction on Ethereum.

**Technical information**

Lending into a pool requires a transaction. Once the transaction has been processed, you will be redirected to a success screen confirming the details of your transaction with links to verify the transaction on Etherscan.

Each Maple pool is a [smart contract](https://ethereum.org/en/smart-contracts/). The address of the smart contract can be found at the top left of the pool overview page as well when you are prompted to confirm the lend transaction.

When you lend into a pool you are calling the “Deposit” function on the pool smart contract. The function, when confirmed in your wallet, will accept your lending tokens and you will receive Pool LP (Liquidity Provider) Tokens.

Each pool contract inherits the [ERC 4626](https://erc4626.info/) standard, also know as the “Tokenized Vault” Standard. This standard informs how the LP Tokens accrue value from borrower repayments of loans.

The Global Allowlist uses a collective list of the valid Maple wallets which the Pool Contracts access to determine access to each pool. If an address which is not on the Global Allowlist attempts to lend to a permissioned pool, the transaction will revert.

Another important note on permissioned pools is that sending permissioned pool LP tokens to another address will revert unless the receiving address is also on the Global Allowlist.
