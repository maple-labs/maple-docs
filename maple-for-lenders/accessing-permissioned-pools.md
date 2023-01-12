# Accessing Permissioned Pools

Permissioned pools are private pools on Maple. Delegates determine the entry requirements for permissioned pools. Permissioned pools are lending vehicles for lenders who need to know that all Lenders in the pool are KYC’d and are known actors.

If you are interested in lending to one of the permissioned pools, simply visit the pool dashboard and apply to be a lender. You can also fill out the application directly [here](https://form.typeform.com/to/u3n8Q8ga). The application process will require submitting KYC information.

If you would like to reach out to a delegate directly, you may always contact them through the “Contact delegate” button found on the pool management section of the pool dashboard.

**Technical Information**

For those of you interested in how Maple works at a smart contract level, permissioned pools work by allowing the delegate to add or remove a lender to an on-chain allow list. These allow lists are local to a pool. If an address which is not on the allow list attempts to lend to a permissioned pool, the transaction will revert.

Another important note on permissioned pools is that sending permissioned pool LP tokens to another address will revert unless the receiving address is also on a pools allowlist.
