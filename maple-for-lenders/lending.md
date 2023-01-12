# Lending

Maple aims to make lending simple, clear and transparent.

If you are lending to a permissioned pool and have already been approved by the Delegate, lending is as simple as connecting your wallet and clicking on the “Lend” call to action displayed on the top right hand side of the pool dashboard, or in “Your Lending Stats” tile.

For non-permissioned lenders, **there are four additional factors to consider prior to depositing.**

The first is that before the transaction to lend funds proceeds, your wallet address will be scanned by anti-money laundering software. If your address is flagged, the transaction will not proceed.

The second consideration is acknowledgement of [Maple’s T\&C’s](broken-reference) for using the interface. Please make sure to review these terms before lending.

By lending, you consent to Maple’s T\&Cs as well as having your address scanned by AML software, the next step is to enter in how much you would like to lend.

The fourth and final consideration is the withdrawal times. The Maple UI will display on the pool page the maximum amount of time it takes to wait until a withdrawal can occur. Please make sure to consider this timeframe before lending. You may learn more about withdrawals [here](broken-reference).

**Pool Capacity**

Pool capacity limits the amount of assets which may be deposited into a pool. The Delegate controls the pool capacity, the purpose of which is to balance the amount of assets flowing into the pool with demand from borrowers for loans. If the amount you would like to lend exceeds the pool capacity, you may contact the Delegates on the Pool Management tab of the pool dashboard to request an increase in capacity.

**Approvals**

The first time you lend an asset (e.g. USDC, wETH) to a pool, you will be prompted to allow the pool contract to interact with the asset. Once you approve the asset for the first time, you will not have to approve that asset for any additional deposits. This is a common transaction on Ethereum and more details can be found [here](https://docs.ethhub.io/guides/a-straightforward-guide-erc20-tokens/).

**Technical information**

Lending into a pool requires a transaction. Once the transaction has been processed, you will be redirected to a success screen confirming the details of your transaction with links to verify the transaction on Etherscan.

Each Maple pool is a [smart contract](https://ethereum.org/en/smart-contracts/). The address of the smart contract can be found at the top left of the pool overview page as well when you are prompted to confirm the lend transaction.

When you lend into a pool you are calling the “Deposit” function on the pool smart contract. The function, when confirmed in your wallet, will accept the amount of pool assets you indicated in the UI to lend and in exchange assign to your wallet Pool LP (Liquidity Provider) Tokens.

Each pool contract inherits the [ERC 4626](https://erc4626.info/) standard, also know as the “Tokenized Vault” Standard. This standard informs how the LP Tokens accrue value from borrower repayments of loans.&#x20;
