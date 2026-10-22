# Smart Contract Deployments & Upgrade Procedure for Strategies Release

The following contracts will be deployed with the relevant release tags.

* [Maple Globals](https://github.com/maple-labs/globals-v2/blob/main/contracts/MapleGlobals.sol) instance with updated logic.
* [Pool Manager Implementation](https://github.com/maple-labs/pool-v2/blob/main/contracts/MaplePoolManager.sol) instance with updated logic.
* [Pool Manager Initializer](https://github.com/maple-labs/pool-v2/blob/main/contracts/proxy/MaplePoolManagerInitializer.sol) instance with updated compiler.
* [Pool Deployer](https://github.com/maple-labs/pool-v2/blob/main/contracts/MaplePoolDeployer.sol) instance with updated logic.
* 3 instances of the new contract [Maple Strategy Factory](https://github.com/maple-labs/maple-strategies/blob/main/contracts/proxy/MapleStrategyFactory.sol). Each one will be used for `Aave`, `Sky` and `Basic` strategies.
* New contract [Maple Aave Strategy Initializer](https://github.com/maple-labs/maple-strategies/blob/main/contracts/proxy/aaveStrategy/MapleAaveStrategyInitializer.sol)
* New contract [Maple Aave Strategy Implementation](https://github.com/maple-labs/maple-strategies/blob/main/contracts/MapleAaveStrategy.sol)
* New contract [Maple Basic Strategy Initializer](https://github.com/maple-labs/maple-strategies/blob/main/contracts/proxy/basicStrategy/MapleBasicStrategyInitializer.sol)
* New contract [Maple Basic Strategy Implementation](https://github.com/maple-labs/maple-strategies/blob/main/contracts/MapleBasicStrategy.sol)
* New contract [Maple Sky Strategy Initializer](https://github.com/maple-labs/maple-strategies/blob/main/contracts/proxy/skyStrategy/MapleSkyStrategyInitializer.sol)
* New contract [Maple Sky Strategy Implementation](https://github.com/maple-labs/maple-strategies/blob/main/contracts/MapleSkyStrategy.sol)

# Upgrade procedure

## Setting up Pool Manager
The following transactions will be made to the `PoolManagerFactory` by the `GOVERNOR`
1. `registerImplementation(400, <newly deployed PM>, <newly deployed PM Initializer>)`
2. `enableUpgradePath(300, 400, address(0))`
3. `enableUpgradePath(301, 400, address(0))`
4. `setDefaultVersion(400)`

After that, on each Pool Manager that will be upgraded, the following function will be called:
1. `upgrade(400, "")` by `PoolDelegate/SecurityAdmin`

The list of pools that will have their pool manager upgraded are:
```
* AQRU
* Cash Management USDC
* Blue Chip Secured Lending USDC
* High Yield Corporate Loan USDC
* High Yield Corporate Loan WETH
* High Yield Secured Lending - USDC
* Syrup USDC
* syrup USDT
```

## Setting up strategies
For each of the 3 instances of `MapleStrategyFactory` deployed, the following transactions will be made by `GOVERNOR`:
1. `registerImplementation(100, <aave/basic/sky strategyImplementation>, <aave/basic/sky strategyInitializer>)`
2. `setDefaultVersion(100)`

## Setting up Globals
Following transactions will be made by the `GOVERNOR` or `OPERATIONAL ADMIN`

### Upgrade Globals via Governor
1. `setImplementation(<newly deployed MapleGlobals implementation>`)

### Set Valid Instance Keys via Operational Admin
2. `setValidInstanceOf("STRATEGY_FACTORY", fixedTermLoanManagerFactory, true)`
3. `setValidInstanceOf("STRATEGY_FACTORY", openTermLoanManagerFactory, true)`
4. `setValidInstanceOf("STRATEGY_FACTORY", basicStrategyFactory, true)`
5. `setValidInstanceOf("STRATEGY_FACTORY", aaveStrategyFactory, true)`
6. `setValidInstanceOf("STRATEGY_FACTORY", skyStrategyFactory, true)`
7. `setValidInstanceOf("STRATEGY_VAULT", aToken(USDC), true)`
8. `setValidInstanceOf("STRATEGY_VAULT", aToken(USDT), true)`
9. `setValidInstanceOf("STRATEGY_VAULT", sUSDS, true)`
10. `setValidInstanceOf("PSM", usdsLitePSM, true)`

## Attaching Strategies
For each PoolManager of syrupUSDC, syrupUSDT and High-Yield Secured that needs a given strategy added, the following function will be called by the `OPERATIONAL ADMIN`
1. `addStrategy(<aave/basic/sky strategyFactory>, <aave/basic/sky initializer data>)`.

## Strategy Manager Bot
Set Key in Globals to allow Bot to manage strategy positions.
1. `setValidInstanceOf("STRATEGY_MANAGER", <turnkey_bot_address>, true)`
