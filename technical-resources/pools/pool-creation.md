# Overview

The PoolDeployer contract facilitates the atomic deployment, initialization and configuration of the all contracts necessary to run a Pool:
* `PoolManager`, which itself deploys:
  * `Pool`
  * some number of `LoanManager`s
* `WithdrawalManager` (Cyclical or Queue)

The `deployPool` function in the PoolDeployer contract is designed to handle the deployment of either cyclical or queue-based withdrawal managers, with the difference being in the configuration parameters used (the functions are overloaded).

# Pre-Requisite Transactions

The following pre-requisite configurations are necessary in order to deploy a Pool in the Maple protocol.

1. Deploying address is a valid Pool Delegate in `MapleGlobals`.
2. The provided `PoolManagerFactory` is a valid factory in `MapleGlobals`.
3. The provided `WithdrawalManagerFactory` is a valid factory in `MapleGlobals`.
4. Each provided `LoanManagerFactory` is a valid factory in `MapleGlobals`.
5. The provided `PoolPermissionManager` is a valid instance in `MapleGlobals`.
6. The Pool Delegate does not own a `Pool` already.
7. The Pool Asset is a valid asset in `MapleGlobals`.
8. The `WithdrawalManager` withdrawal window is shorter than the cycle duration for cyclical based withdrawal manager.
9. The start time for the first cycle for the cyclical based withdrawal manager is in the future.
10. The required pool cover can be transferred from the Pool Delegate to the `PoolDelegateCover`.

# Pool Deployment with the cycle based Withdrawal Manager

To deploy a Pool, `PoolDeployer` can be called with the following parameters:

* `poolManagerFactory`.
* `withdrawalManagerFactory` - Address of the cycle-based withdrawal manager factory.
* `loanManagerFactories`.
* `asset` - The main asset that the pool denominates in.
* `poolPermissionManager`.
* `name` and `symbol` for identification of the pool shares token.
* Configuration params:
  * `liquidityCap` - The maximum amount of funds asset that can be deposited in the pool
  * `managementFeeRate` - The rate of the interest that is sent to pool delegates as management fee.
  * `poolCoverAmount` - The amount of pool cover that the pool delegate is required to deposit.
  * `cycleDuration` - The duration, in seconds, of each cycle of the withdrawal manager.
  * `windowDuration` - The duration, in seconds, of the withdrawal window.
  * `initialSupply` - The initial supply of pool tokens.
  * `startTime` - The current block's timestamp, in seconds, to denote start of the withdrawal cycle.

# Pool Deployment with the queue based Withdrawal Manager

To deploy a Pool, `PoolDeployer` can be called with the following parameters:

* `poolManagerFactory`.
* `withdrawalManagerFactory` - Address of the queue-based withdrawal manager factory.
* `loanManagerFactories`.
* `asset` - The main asset that the pool denominates in.
* `poolPermissionManager`.
* `name` and `symbol` for identification of the pool shares token.
* Configuration params:
  * `liquidityCap` - The maximum amount of funds asset that can be deposited in the pool
  * `managementFeeRate` - The rate of the interest that is sent to pool delegates as management fee.
  * `poolCoverAmount` - The amount of pool cover that the pool delegate is required to deposit.
  * `initialSupply` - The initial supply of pool tokens.

# Pool Activation

Before the Pool can start accepting deposits and operating, the Governor or Operational Admin needs to call `activatePoolManager` in Globals. This will activate the Pool. This allows the Governor or Operational Admin to set up fee parameters, default parameters, and ensure that the requisite cover has been posted by the Pool Delegate before running the Pool.
