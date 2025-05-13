# Lending in syrupUSDC and syrupUSDT

Simply connect your wallet, deposit funds, and start earning consistent high yield.

To deposit, visit [app.maple.finance/earn](https://app.maple.finance/earn). Choose your Commitment. Longer commitments earn greater Drips rewards. You can view your deposit in the[ Portfolio](https://app.maple.finance/earn/portfolio) page.

[Certain jurisdictions](https://maplefinance.gitbook.io/maple/legal/available-jurisdictions) are ineligible to deposit in Syrup.\


**Approvals**

The first time you lend an asset (e.g. USDC, USDT), you may be prompted to allow the contract to interact with your asset. This is a common transaction on Ethereum.\


**Technical information**

Lending into a pool requires a transaction. Once the transaction has been processed, you will be redirected to a success screen confirming the details of your transaction with links to verify the transaction on Etherscan.

When you lend into a pool you are calling the “Deposit” function on the smart contract. The function, when confirmed in your wallet, will accept your lending tokens and you will receive Pool LP (Liquidity Provider) Tokens.

Each pool contract inherits the[ ERC-4626](https://erc4626.info/) standard, also known as the “Tokenized Vault” Standard. This standard informs how the LP Tokens accrue value from borrower repayments of loans.
