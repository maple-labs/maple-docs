# Contract Addresses

Maple publishes every deployed contract address in its public address registry. The registry is the source of truth, so this page links to it rather than copying addresses that can go stale.

| Chain | List of addresses |
| ----- | ----------------- |
| Ethereum Mainnet | [list](https://github.com/maple-labs/address-registry/blob/main/MapleAddressRegistryETH.md) |
| Base L2 | [list](https://github.com/maple-labs/address-registry/blob/main/MapleAddressRegistryBASEL2.md) |

{% hint style="info" %}
Addresses for the November 2026 release will be added here when it is deployed to mainnet. The registry does not yet list the Strategy Manager, Strategy Deployer, Liquidity Router, Pool Manager v5.0.0, Pool Deployer v5.0.0 or the shared Aave V3, Sky and Allocation strategies.
{% endhint %}

## Contracts in the November 2026 release

| Contract | Change |
|---|---|
| `MapleGlobals` implementation (v5.0.0) | Upgrade of the Globals singleton |
| `MaplePoolDeployer` (v5.0.0) | New deployer |
| `MaplePoolManager` implementation, initializer and `MaplePoolManagerMigratorV500` (v5.0.0) | Upgrade for existing Pool Managers |
| `MapleWithdrawalManager` queue implementation and initializer (v2.0.1) | Upgrade for existing Withdrawal Managers |
| `MapleStrategyManager` factory, implementation and initializer (v1.0.0) | New |
| `MapleStrategyDeployer` (v1.0.0) | New |
| `MapleLiquidityRouter` | New |
| `MapleAaveV3Strategy`, `MapleSkyStrategy` and `MapleAllocationStrategy` factories, implementations and initializers (v1.0.0) | New |
| One Strategy Manager and Underlying Strategy instance per shared strategy | New |

## Developer reference

Solidity source for the on-chain registries, with addresses embedded as constants:

* Ethereum: https://github.com/maple-labs/address-registry/blob/main/contracts/MapleAddressRegistryETH.sol
* Base L2: https://github.com/maple-labs/address-registry/blob/main/contracts/MapleAddressRegistryBASEL2.sol
