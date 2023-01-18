# Overview

The PoolDeployer contract facilitates the atomic deployment, initialization and configuration of the all contracts necessary to run a Pool:
1. `Pool`
2. `PoolManager`
3. `LoanManager`
4. `WithdrawalManager`

# Pre-Requisite Transactions

The following pre-requisite configurations are necessary in order to deploy a Pool in the Maple protocol.

1. Deploying address is a valid Pool Delegate in `MapleGlobals`.
2. `PoolManagerFactory` is a valid factory in `MapleGlobals`.
3. `LoanManagerFactory` is a valid factory in `MapleGlobals`.
4. `WithdrawalManagerFactory` is a valid factory in `MapleGlobals`.
5. `PoolManagerInitializer` is a valid initializer in `PoolManagerFactory`.
6. `LoanManagerInitializer` is a valid initializer in `LoanManagerFactory`.
7. `WithdrawalManagerInitializer` is a valid initializer in `WithdrawalManagerFactory`.
8. The Pool Delegate does not own a `Pool` already.
9. The Pool Asset is a valid asset in `MapleGlobals`.
10. The `WithdrawalManager` withdrawal window is shorter than the cycle duration.

# Pool Deployment

To deploy a Pool, `PoolDeployer` can be called with the following parameters:

* `poolManagerFactory` and `poolManagerInitializer`.
* `loanManagerFactory` and `loanManagerInitializer`.
* `withdrawalManagerFactory` and `WithdrawalManagerInitializer`.
* `asset` - The main asset that the pool denominates in.
* `name` and `symbol` for identification of the pool shares token.
* Configuration params:
  * `liquidityCap` - The maximum amount of funds asset that can be deposited in the pool
  * `managementFeeRate` - The rate of the interest that is sent to pool delegates as management fee.
  * `poolCoverAmount` - The amount of pool cover that the pool delegate is required to deposit.
  * `cycleDuration` - The duration, in seconds, of each cycle of the withdrawal manager.
  * `windowDuration` - The duration, in seconds, of the withdrawal window.
  * `initialSupply` - The initial supply of pool tokens.

# Pool Activation

Before the Pool can start accepting deposits and operating, the Governor needs to call `activatePoolManager` in Globals. This will activate the Pool. This allows the Governor to set up fee parameters, default parameters, and ensure that the requisite cover has been posted by the Pool Delegate before running the Pool.
