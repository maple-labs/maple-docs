# December 2023 Deployment & Upgrade Procedure

### 1. Deploy All New Contracts
The first step is deploying various new contract implementations and initializing some of them. Here's a breakdown of the contracts being deployed:

| **contract** | **description** |
| :--- | :--- |
| `FixedTermLoanFactoryV2` | The new version of the fixed term loan factory |
| `FixedTermLoanImplementationV502` | The new version of the fixed term loan implementation. Identical to V501, but needed for factory migration |
| `FixedTermLoanV502Migrator` | The migrator contract for setting the new factory on deployed versions of the fixed term loan |
| `GlobalsImplementationV3` | The new version of the globals contract |
| `PoolDeployerV3` | The new version of the pool deployer contract |
| `PoolManagerImplementationV300` | The new version of the pool manager contract |
| `PoolManagerImplementationV301` | The new version of the pool manager contract. Identical to V300 but needed for allowing a migration |
| `PoolManagerInitializer` | The initializer for the pool manager contract |
| `PoolManagerMigrator` | The migrator contract for setting the new pool permission manager implementation on deployed versions of the pool manager |
| `PoolManagerWMMigrator` | The migrator contract for setting the new queue withdrawal manager implementation on deployed versions of the pool manager |
| `NonTransparentProxy (PoolPermissionManager)` | The new pool permission manager contract. This will be a non transparent proxy. |
| `PoolPermissionManagerImplementation` | The new pool permission manager contract implementation. |
| `PoolPermissionManagerInitializer` | The new pool permission manager Initializer contract. |
| `WithdrawalManagerCyclical` | The new implementation of the withdrawal manager cyclical contract |
| `WithdrawalManagerCyclicalInitializer` | The initializer for the withdrawal manager cyclical contract |
| `WithdrawalManagerQueueFactory` | The factory for creating instances of the withdrawal manager queue contract |
| `WithdrawalManagerQueue` | The new implementation of the withdrawal manager queue contract |
| `WithdrawalManagerQueueInitializer` | The initializer for the withdrawal manager queue contract |

### 2. Upgrade Globals
The Globals contract is upgraded to the new implementation (V3) deployed in the previous step. This involves pointing the proxy contract to the new implementation address.

### 3. Enable Globals Keys
This function sets various permissions and configurations in the Globals contract. It registers new valid instances, enables deployment from specific factories, and sets permission for deploying contracts. Breakdown of values:


| Function Name                 | Parameter 1                   | Parameter 2                           | Parameter 3 |
|-------------------------------|--------------------------------|---------------------------------------|-------------|
| `setValidInstanceOf`          | `"LOAN_FACTORY"`               | `fixedTermLoanFactoryV2`              | `true`      |
| `setValidInstanceOf`          | `"FT_LOAN_FACTORY"`            | `fixedTermLoanFactoryV2`              | `true`      |
| `setValidInstanceOf`          | `"POOL_PERMISSION_MANAGER"`    | `address(poolPermissionManager)`      | `true`      |
| `setValidInstanceOf`          | `"WITHDRAWAL_MANAGER_CYCLE_FACTORY"` | `withdrawalManagerFactory`         | `true`      |
| `setValidInstanceOf`          | `"WITHDRAWAL_MANAGER_QUEUE_FACTORY"` | `queueWMFactory`                   | `true`      |
| `setValidInstanceOf`          | `"WITHDRAWAL_MANAGER_FACTORY"` | `queueWMFactory`                       | `true`      |
| `setValidInstanceOf`          | `"QUEUE_POOL_MANAGER"`         | `cashManagementUSDCPoolManager`        | `true`      |
| `setValidInstanceOf`          | `"QUEUE_POOL_MANAGER"`         | `cashManagementUSDTPoolManager`        | `true`      |
| `setCanDeployFrom`            | `poolManagerFactory`           | `poolDeployerV3`                       | `true`      |
| `setCanDeployFrom`            | `withdrawalManagerFactory`     | `poolDeployerV3`                       | `true`      |
| `setCanDeployFrom`            | `queueWMFactory`               | `poolDeployerV3`                       | `true`      |


In this table, the `Function Name` column contains the name of the function being called, the `Parameter 1`, `Parameter 2`, and `Parameter 3` columns contain the parameters being passed to the function.

### 4. Add Delay to Oracles
This function sets a delay on price oracles for specific assets (WETH, WBTC) in the Globals contract.
| Asset  | Oracle                                                     | Delay   |
|--------|------------------------------------------------------------|---------|
| `weth` | [`ethUsdOracle`](https://etherscan.io/address/0x5f4eC3Df9cbd43714FE2740f5E3616155c5b8419) | `4 hours` |
| `wbtc` | [`btcUsdOracle`](https://etherscan.io/address/0xF4030086522a5bEEa4988F8cA5B36dbC97BeE88c) | `4 hours` |

### 5. Setup Factories
This function registers new implementations and default versions in various factories (PoolManager, FixedTermLoan, WithdrawalManager). It also enables upgrade paths for existing contracts to move to new implementations.

| Factory                       | Function                     | Version   | Arguments                                             |
| ----------------------------- | ---------------------------- | --------- | ----------------------------------------------------- |
| Pool Manager Factory          | `registerImplementation`     | 300       | `300, poolManagerImplementationV300, poolManagerInitializer` |
| Pool Manager Factory          | `registerImplementation`     | 301       | `301, poolManagerImplementationV301, poolManagerInitializer` |
| Pool Manager Factory          | `setDefaultVersion`          | 300       | `300`                                                 |
| Pool Manager Factory          | `enableUpgradePath`          | 200 -> 300 | `200, 300, poolManagerMigrator`                      |
| Pool Manager Factory          | `enableUpgradePath`          | 201 -> 300 | `201, 300, poolManagerMigrator`                      |
| Pool Manager Factory          | `enableUpgradePath`          | 300 -> 301 | `300, 301, poolManagerWMMigrator`                    |
| Fixed Term Loan Factory       | `registerImplementation`     | 502       | `502, fixedTermLoanImplementationV502, fixedTermLoanInitializerV500` |
| Fixed Term Loan Factory       | `enableUpgradePath`          | 501 -> 502 | `501, 502, fixedTermLoanV502Migrator`                |
| Fixed Term Loan Factory V2    | `registerImplementation`     | 502       | `502, fixedTermLoanImplementationV502, fixedTermLoanInitializerV500` |
| Fixed Term Loan Factory V2    | `setDefaultVersion`          | 502       | `502`                                                 |
| Withdrawal Manager Factory    | `registerImplementation`     | 110       | `110, cyclicalWMImplementation, cyclicalWMInitializer` |
| Withdrawal Manager Factory    | `setDefaultVersion`          | 110       | `110`                                                 |
| Queue Withdrawal Manager Factory | `registerImplementation`   | 100       | `100, queueWMImplementation, queueWMInitializer`     |
| Queue Withdrawal Manager Factory | `setDefaultVersion`        | 100       | `100`                                                 |

### 6. Setup PoolPermissionManager
The newly deployed `poolPermissionManager` is configured to match each pool configuration, including allowing all existing lenders.

### 7. Upgrade Pool Contracts
All the deployed `poolManager's` contracts will be upgraded to version 300. The upgrades are performed with security admin privileges, ensuring secure and authorized changes.

### 8. Upgrade Fixed Term Loans
All the deployed `FixedTermLoan's` contracts are upgraded to a new version using security admin privileges.

### 9. Upgrade to Queue Withdrawal Manager
The cash management pools will have their withdrawal manager migrated to the new `WithdrawalManagerQueue`.

### 10. Deprecate Fixed Term Loan Factory
This is done by setting the default version to 0 to stop new instances being deployed.

### 11. Deprecate Pool Deployer V2
By setting the flag to false for the factory instances, we prevent new pools from being deployed through Pool Deployer V2.

| Function Name               | Parameter 1                   | Parameter 2                           | Parameter 3 |
|-----------------------------|-------------------------------|---------------------------------------|-------------|
| `setCanDeployFrom`          | `poolManagerFactory`          | `poolDeployerV2`                      | `false`      |
| `setCanDeployFrom`          | `withdrawalManagerFactory`    | `poolDeployerV2`                      | `false`      |

