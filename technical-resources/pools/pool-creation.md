# Creating a Pool

`MaplePoolDeployer` deploys and configures everything a Pool needs in one transaction: the Pool Manager (which deploys the Pool), the queue-based Withdrawal Manager, any owned strategies, and the Strategy Managers the Pool will fund. Only a Pool Delegate can call it. Full interface: [PoolDeployer](../interfaces/pool-deployer.md).

## Prerequisites

The deployment reverts unless all of the following hold in Globals.

1. The caller is a valid Pool Delegate (`isPoolDelegate`) and does not already own a Pool Manager.
2. The Pool Deployer is registered as a pool deployer (`isPoolDeployer`) and may deploy from the Withdrawal Manager factory (`canDeployFrom`).
3. `poolManagerFactory` is a `POOL_MANAGER_FACTORY` instance, `withdrawalManagerFactory` is a `WITHDRAWAL_MANAGER_QUEUE_FACTORY` instance and `poolPermissionManager` is a `POOL_PERMISSION_MANAGER` instance.
4. The Pool asset is a valid pool asset (`isPoolAsset`).
5. Each owned-strategy factory is a `STRATEGY_FACTORY` instance. Globals lets any Pool Manager deploy from such a factory without further setup.
6. Each Strategy Manager was deployed by a `STRATEGY_MANAGER_FACTORY` instance and supports the Pool asset. The [Strategy Deployer](../strategies/strategy-deployer.md) deploys Strategy Managers beforehand.
7. `initialSupply` is zero, or Globals has a migration admin to receive the initial shares.

Only queue-based Withdrawal Managers can be deployed. The cyclical variant is no longer supported.

## deployPool

```solidity
function deployPool(
    address poolManagerFactory,
    address withdrawalManagerFactory,
    PoolManagerInitParams calldata poolManagerInitParams,
    PoolConfigParams calldata poolConfigParams,
    StrategyDeployParams[] calldata strategiesParams,
    StrategyManagerParams[] calldata strategyManagersParams
) external returns (address poolManager);
```

| Struct | Field | Type | Meaning |
| --- | --- | --- | --- |
| `PoolManagerInitParams` | `asset` | `address` | The Pool asset |
|  | `initialSupply` | `uint256` | Shares minted to the migration admin at construction, normally zero |
|  | `name`, `symbol` | `string` | ERC-20 metadata of the Pool share token |
| `PoolConfigParams` | `poolPermissionManager` | `address` | The Pool Permission Manager |
|  | `delegateManagementFeeRate` | `uint256` | Delegate management fee rate, where `100_0000` is 100% |
|  | `liquidityCap` | `uint256` | Maximum `totalAssets` the Pool accepts |
| `StrategyDeployParams` (one per owned strategy) | `factory` | `address` | Strategy factory |
|  | `cap` | `uint256` | Strategy cap, zero leaves it unset |
|  | `salt` | `bytes32` | CREATE2 salt |
|  | `deploymentData` | `bytes` | Factory-specific data. The Pool Manager address is prepended automatically |
| `StrategyManagerParams` (one per Strategy Manager) | `instance` | `address` | An existing Strategy Manager |
|  | `cap` | `uint256` | Strategy cap, zero leaves it unset |

## What the transaction does

1. Deploys the Pool Manager from its factory. The initializer deploys the Pool, which approves the Pool Manager for its asset.
2. Deploys the queue Withdrawal Manager for the Pool.
3. For each `StrategyDeployParams`, calls `addStrategy` on the Pool Manager and, if `cap` is non-zero, `setStrategyCap`.
4. For each `StrategyManagerParams`, calls `addStrategyManager` and, if `cap` is non-zero, `setStrategyCap`.
5. Emits `PoolDeployed(pool, poolManager, withdrawalManager, strategies, strategyManagers)`.
6. Sets the delegate management fee rate, liquidity cap, Pool Permission Manager and Withdrawal Manager, then calls `completeConfiguration`.

Addresses are deterministic. `getPoolDeploymentAddresses`, `getQueueWithdrawalManagerAddress` and `getStrategiesAddresses` return the addresses a deployment will produce, so they can be registered or funded in advance.

## Activation

A new Pool is configured but not active, so it rejects deposits with `P:NOT_ACTIVE`. The Governor or Operational Admin calls `activatePoolManager(poolManager)` on Globals. It checks the factory and the Pool Delegate, records the Pool Manager as the delegate's owned Pool, and calls `setActive(true)` on the Pool Manager.

## After deployment

Once configured, the Pool Delegate, Governor or Operational Admin can change the liquidity cap, delegate management fee rate, Pool Permission Manager and strategy caps. Only the Governor can add strategies or Strategy Managers, only the Operational Admin can remove a Strategy Manager, and the Withdrawal Manager cannot be changed. See [Pool Manager](pool-manager.md).
