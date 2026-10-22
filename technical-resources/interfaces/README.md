# Interfaces

Reference pages for the external interface of every Maple v7 contract, generated from the Solidity natspec and grouped by subsystem. Each page lists the contract's functions and events, the members it inherits from the proxy interfaces, and any structs or enums its functions use.

## Globals and Timelock

| Page                                      | Contract           | Module    |
| ----------------------------------------- | ------------------ | --------- |
| [Globals](globals.md)                     | `MapleGlobals`     | `globals` |
| [GovernorTimelock](governor-timelock.md)  | `GovernorTimelock` | `globals` |

## Pools

| Page                                                   | Contract                      | Module                    |
| ------------------------------------------------------ | ----------------------------- | ------------------------- |
| [Pool](pool.md)                                        | `MaplePool`                   | `pool`                    |
| [PoolManager](pool-manager.md)                         | `MaplePoolManager`            | `pool`                    |
| [PoolManagerFactory](pool-manager-factory.md)          | `MaplePoolManagerFactory`     | `pool`                    |
| [PoolManagerInitializer](pool-manager-initializer.md)  | `MaplePoolManagerInitializer` | `pool`                    |
| [PoolDeployer](pool-deployer.md)                       | `MaplePoolDeployer`           | `pool`                    |
| [PoolPermissionManager](pool-permission-manager.md)    | `MaplePoolPermissionManager`  | `pool-permission-manager` |

## Withdrawal Manager

| Page                                                                             | Contract                            | Module                     |
| -------------------------------------------------------------------------------- | ----------------------------------- | -------------------------- |
| [WithdrawalManager (Queue)](withdrawal-manager-queue.md)                         | `MapleWithdrawalManager`            | `withdrawal-manager-queue` |
| [WithdrawalManagerFactory (Queue)](withdrawal-manager-queue-factory.md)          | `MapleWithdrawalManagerFactory`     | `withdrawal-manager-queue` |
| [WithdrawalManagerInitializer (Queue)](withdrawal-manager-queue-initializer.md)  | `MapleWithdrawalManagerInitializer` | `withdrawal-manager-queue` |

## Open Term Loans

| Page                                                                   | Contract                      | Module                   |
| ---------------------------------------------------------------------- | ----------------------------- | ------------------------ |
| [OpenTermLoan](open-term-loan.md)                                      | `MapleLoan`                   | `open-term-loan`         |
| [OpenTermLoanFactory](open-term-loan-factory.md)                       | `MapleLoanFactory`            | `open-term-loan`         |
| [OpenTermLoanInitializer](open-term-loan-initializer.md)               | `MapleLoanInitializer`        | `open-term-loan`         |
| [OpenTermLoanRefinancer](open-term-loan-refinancer.md)                 | `MapleRefinancer`             | `open-term-loan`         |
| [OpenTermLoanManager](open-term-loan-manager.md)                       | `MapleLoanManager`            | `open-term-loan-manager` |
| [OpenTermLoanManagerFactory](open-term-loan-manager-factory.md)        | `MapleLoanManagerFactory`     | `open-term-loan-manager` |
| [OpenTermLoanManagerInitializer](open-term-loan-manager-initializer.md) | `MapleLoanManagerInitializer` | `open-term-loan-manager` |

## Modular Strategies

| Page                                                           | Contract                          | Module             |
| -------------------------------------------------------------- | --------------------------------- | ------------------ |
| [StrategyManager](strategy-manager.md)                         | `MapleStrategyManager`            | `strategy-manager` |
| [StrategyManagerFactory](strategy-manager-factory.md)          | `MapleStrategyManagerFactory`     | `strategy-manager` |
| [StrategyManagerInitializer](strategy-manager-initializer.md)  | `MapleStrategyManagerInitializer` | `strategy-manager` |
| [StrategyDeployer](strategy-deployer.md)                       | `MapleStrategyDeployer`           | `strategy-manager` |
| [LiquidityRouter](liquidity-router.md)                         | `MapleLiquidityRouter`            | `strategy-manager` |

## Aave V3 Strategy

| Page                                                         | Contract                         | Module            |
| ------------------------------------------------------------ | -------------------------------- | ----------------- |
| [AaveV3Strategy](aave-v3-strategy.md)                        | `MapleAaveV3Strategy`            | `defi-strategies` |
| [AaveV3StrategyFactory](aave-v3-strategy-factory.md)         | `MapleAaveV3StrategyFactory`     | `defi-strategies` |
| [AaveV3StrategyInitializer](aave-v3-strategy-initializer.md) | `MapleAaveV3StrategyInitializer` | `defi-strategies` |

## Sky Strategy

| Page                                                   | Contract                      | Module            |
| ------------------------------------------------------ | ----------------------------- | ----------------- |
| [SkyStrategy](sky-strategy.md)                         | `MapleSkyStrategy`            | `defi-strategies` |
| [SkyStrategyFactory](sky-strategy-factory.md)          | `MapleSkyStrategyFactory`     | `defi-strategies` |
| [SkyStrategyInitializer](sky-strategy-initializer.md)  | `MapleSkyStrategyInitializer` | `defi-strategies` |

## Allocation Strategy

| Page                                                                 | Contract                             | Module                |
| -------------------------------------------------------------------- | ------------------------------------ | --------------------- |
| [AllocationStrategy](allocation-strategy.md)                         | `MapleAllocationStrategy`            | `allocation-strategy` |
| [AllocationStrategyFactory](allocation-strategy-factory.md)          | `MapleAllocationStrategyFactory`     | `allocation-strategy` |
| [AllocationStrategyInitializer](allocation-strategy-initializer.md)  | `MapleAllocationStrategyInitializer` | `allocation-strategy` |

## Peripheral

| Page                           | Contract      | Module        |
| ------------------------------ | ------------- | ------------- |
| [SyrupRouter](syrup-router.md) | `SyrupRouter` | `syrup-utils` |
