# Accessing Pools

Lending Opportunities on Maple (called Pools) are permissioned. When Lenders complete KYC, their wallets are automatically added to Maple's Global Allowlist. This means that Lenders' wallets can access every Opportunity on Maple.

**Technical Information**

For those of you interested in how Maple works at a smart contract level, the Global Allowlist works by using a collective list of the valid Maple wallets which the Pool Contracts access to determine access to each pool. If an address which is not on the Global Allowlist attempts to lend to a permissioned pool, the transaction will revert.

Another important note on permissioned pools is that sending permissioned pool LP tokens to another address will revert unless the receiving address is also on the GLobal Allowlist.
