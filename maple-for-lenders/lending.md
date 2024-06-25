# Lending

Maple aims to make lending simple, clear and transparent.

Lending Opportunities on Maple (called Pools) are permissioned. When Lenders complete KYC, their wallets are automatically added to Maple's Global Allowlist. This means that Lenders' wallets can access every Opportunity on Maple.

**Pool Capacity**

Pool capacity limits the amount of assets which may be deposited into a pool. The Delegate controls the pool capacity, the purpose of which is to balance the amount of assets flowing into the pool with demand from borrowers for loans. If the amount you would like to lend exceeds the pool capacity, you may contact the Delegates on the Pool Management tab of the pool dashboard to request an increase in capacity.

**Approvals**

The first time you lend an asset (e.g. USDC, wETH) to a pool, you will be prompted to allow the pool contract to interact with the asset. Once you approve the asset for the first time, you will not have to approve that asset for any additional deposits. This is a common transaction on Ethereum and more details can be found [here](https://docs.ethhub.io/guides/a-straightforward-guide-erc20-tokens/).

**Technical information**

Lending into a pool requires a transaction. Once the transaction has been processed, you will be redirected to a success screen confirming the details of your transaction with links to verify the transaction on Etherscan.

Each Maple pool is a [smart contract](https://ethereum.org/en/smart-contracts/). The address of the smart contract can be found at the top left of the pool overview page as well when you are prompted to confirm the lend transaction.

When you lend into a pool you are calling the “Deposit” function on the pool smart contract. The function, when confirmed in your wallet, will accept the amount of pool assets you indicated in the UI to lend and in exchange assign to your wallet Pool LP (Liquidity Provider) Tokens.

Each pool contract inherits the [ERC 4626](https://erc4626.info/) standard, also know as the “Tokenized Vault” Standard. This standard informs how the LP Tokens accrue value from borrower repayments of loans.

For those of you interested in how Maple works at a smart contract level, the Global Allowlist works by using a collective list of the valid Maple wallets which the Pool Contracts access to determine access to each pool. If an address which is not on the Global Allowlist attempts to lend to a permissioned pool, the transaction will revert.

Another important note on permissioned pools is that sending permissioned pool LP tokens to another address will revert unless the receiving address is also on the GLobal Allowlist.
