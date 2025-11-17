# Overview

Since the Pool contract holds the ERC-20 token logic that tracks the value of all the Liquidity Provider's positions, it was prioritized to be made immutable. In order to balance the benefits of immutability and be able to incorporate the flexibility to build into the future, a modular architecture was introduced. The PoolManager is the true "central" contract of a Pool ecosystem of contracts. The PoolManager holds all administrative functionality, aggregates all accounting information, and allows for a high degree of configuration. The PoolManager manages with the following contracts:
- Pool
- PoolDelegateCover
- WithdrawalManager
- LoanManager (can be multiple)

The relationship between the Pool and PoolManager is currently one-to-one, however due to the architecture a PoolManager could technically manage multiple ERC-4626 Pool contracts and manage their accounting. This allows for more sophisticated LP options to become available in the future if needed.

The Pool is not aware of any of the LoanManagers or the WithdrawalManager, so these contracts can be changed in the future as seen fit (can only be changeable to contracts that have been vetted by the protocol smart contracts team and the DAO).

In addition, in future iterations of the protocol, this will allow newly deployed pools to be configured from a suite of LoanManager and WithdrawalManager contracts to meet pool requirements.
# Administrative Functions

Core configuration is gated to protocol admins (Governor, Operational Admin or Pool Delegate) or only allowed prior to initial configuration.

- `setDelegateManagementFeeRate` 
- `setLiquidityCap` 
- `setPoolPermissionManager`
- `setWithdrawalManager` 
- `addStrategy` 
- `setIsStrategy` 

Additionally, the PoolManager stores relevant module addresses:
- List of `loanManagers`
- The `withdrawalManager`
- The `poolDelegateCover` contract

# Funds Asset Approval

One important thing to note is that the PoolManager contract has approval to transfer Pool cash. This is done to minimize the need for internal contract calls in a few functions like funding and refinance. The approval is done when the pool is deployed and cannot be revoked. There is a limitation on the movement of cash by the Pool Delegate, which is governed by the WithdrawalManager. The current implementation of the WithdrawalManager prevents Pool Delegates from moving cash that is currently earmarked for withdrawals.
