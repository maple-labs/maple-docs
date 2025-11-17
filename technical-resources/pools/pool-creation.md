# Overview

The PoolDeployer contract facilitates the atomic deployment and initialization of the contracts necessary to run a Pool:
* `PoolManager`, which itself deploys the `Pool` and acts as the hub for configuration and strategy attachment
* `WithdrawalManager (Queue)`

The `deployPool` function in the PoolDeployer contract handles deployment of the PoolManager/Pool, the queue‑based Withdrawal Manager, and strategy instances.

# Pre-Requisite Transactions

The following pre-requisite configurations are necessary in order to deploy a Pool in the Maple protocol.

1. Deploying address is a valid Pool Delegate in `MapleGlobals`.
2. The provided `PoolManagerFactory` is a valid factory in `MapleGlobals`.
3. The provided `WithdrawalManager (Queue) Factory` is a valid factory in `MapleGlobals`.
4. Each provided `LoanManagerFactory` is a valid factory in `MapleGlobals`.
5. The provided `PoolPermissionManager` is a valid instance in `MapleGlobals`.
6. The Pool Delegate does not own a `Pool` already.
7. The Pool Asset is a valid asset in `MapleGlobals`.
8. The required pool cover can be transferred from the Pool Delegate to the `PoolDelegateCover`.

# Pool Deployment with the queue-based Withdrawal Manager

To deploy a Pool, `PoolDeployer` can be called with the following parameters:

* `poolManagerFactory`.
* `withdrawalManagerFactory` - Address of the queue-based withdrawal manager factory (`WITHDRAWAL_MANAGER_QUEUE_FACTORY`).
* `strategyFactories` - Array of strategy factory addresses (e.g., LoanManager factory, external strategy factories).
* `strategyDeploymentData` - Strategy-specific encoded deployment data for each factory.
* `asset` - The main asset that the pool denominates in.
* `poolPermissionManager`.
* `name` and `symbol` for identification of the pool shares token.
* Configuration params:
  * `initialSupply` - The initial supply of pool tokens used during Pool deployment

Note: In the queue-based deployer, additional Pool parameters such as `liquidityCap`, `delegateManagementFeeRate`, `poolPermissionManager`, and `withdrawalManager` are set post-deployment via `PoolManager` admin functions (typically by Governor or Operational Admin) after activation.

# Pool Activation

Before the Pool can start accepting deposits and operating, the Governor or Operational Admin needs to call `activatePoolManager` in Globals. This will activate the Pool. This allows the Governor or Operational Admin to set up fee parameters, default parameters, and ensure that the requisite cover has been posted by the Pool Delegate before running the Pool.

Deprecated: The cyclical Withdrawal Manager has been deprecated. New pools should use the Withdrawal Manager (Queue).
