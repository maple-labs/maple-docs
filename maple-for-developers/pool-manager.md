# Overview

Since the Pool contract holds the ERC-20 token logic that tracks the value of all the Liquidity Provider's positions, it was prioritized to be made immutable. In order to balance the benefits of immutability and be able to incorporate the flexibility to build into the future, a modular architecture was introduced. The PoolManager is the true "central" contract of a Pool ecosystem of contracts. The PoolManager holds all administrative functionality, aggregates all accounting information, and allows for a high degree of configuration. The PoolManager manages with the following contracts:
- Pool
- LoanManager
- PoolDelegateCover
- WithdrawalManager

The relationship between the Pool and PoolManager is currently one-to-one, however due to the architecture a PoolManager could technically manage multiple ERC-4626 Pool contracts and manage their accounting. This allows for more sophisticated LP options to become available in the future if needed. 

The Pool is not aware of the LoanManager or WithdrawalManager, so these contracts can be changed in the future as seen fit (can only be changeable to contracts that have been vetted by the protocol smart contracts team and the DAO).

In addition, in future iterations of the protocol, this will allow for newly deployed Pools to be configured in a custom manner. Pool Delegates could choose from a suite of LoanManager, PoolDelegateCover, and WithdrawalManager contracts and initialize a Pool that meets the specific needs they have to run their lending business.

# Administrative Functions

Pool Delegates have permissions to alter the configuration of the PoolManager contract. All parameters that can be configured are listed below.

* `poolDelegate`: The address allowed to configure the pool and fund loans.
* `liquidityCap`: The maximum amount of funds asset that can be deposited.
* `openToPublic`: Indicates if the pool is permissioned or not.
* `delegateManagementRate`: The percentage of the interest that is paid to the Pool Delegate.

Additionally, the PoolManager also stores relevant information regarding the modules used by the pool, such as:

* List of `loanManagers`
* The `withdrawalManager`
* The `poolDelegateCover` contract.

# Funds Asset Approval

One important thing to note is that the PoolManager contract has approval to transfer Pool cash. This is done to minimize the need for internal contract calls in a few functions like funding and refinance. The approval is done when the pool is deployed and cannot be revoked. There is a limitation on the movement of cash by the Pool Delegate, which is governed by the WithdrawalManager. The current implementation of the WithdrawalManager prevents Pool Delegates from moving cash that is currently earmarked for withdrawals.
