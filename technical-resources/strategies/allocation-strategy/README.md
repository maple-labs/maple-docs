# Allocation Strategy

The Allocation Strategy deploys pool capital to Managed Wallets, Maple-operated addresses that put the capital to work off-chain or in other protocols, and recognizes yield on a cash basis once a wallet transfers it back into the contract. It sits behind a [Strategy Manager](../strategy-manager.md), which is the only contract that moves pool capital into or out of it.

`MapleAllocationStrategy` does five things:

* Holds pool capital it has received from its Strategy Manager (`recordedAssets`).
* Releases that capital to Managed Wallets under per-wallet permissions and deployment caps, and tracks what each wallet holds (`deployedAssetsOf`, `totalDeployedAssets`).
* Accepts returned yield into a linear-release buffer (`scheduledYieldAssets`) and pays Strategy Delegate and protocol fees on it immediately.
* Reports `assetsUnderManagement()` and `unrealizedLosses()` to the Strategy Manager, which uses them to price the Pool's position.
* Writes capital down through impairments and recognized losses.

## Initialization

`MapleAllocationStrategyFactory` deploys each strategy as an upgradeable proxy. `createInstance()` requires `MapleGlobals.canDeploy(msg.sender)` to be true for the caller, which in practice is the [Strategy Deployer](../strategy-deployer.md). The proxy pattern is described under [Proxies and Upgradeability](../../protocol-overview/proxies-and-upgradeability.md).

`MapleAllocationStrategyInitializer` runs once, through its `fallback()`, and decodes a `strategyManager` address followed by an `AllocationStrategyInitializerParams` struct:

| Parameter                 | Type      | Meaning                                                                 |
| ------------------------- | --------- | ----------------------------------------------------------------------- |
| `strategyManager`         | `address` | The Strategy Manager this strategy is bound to. It cannot change later. |
| `fundsAsset`              | `address` | The ERC-20 asset the strategy holds.                                    |
| `strategyMetadata`        | `string`  | Free-form label for off-chain tooling. Updatable with `setMetadata()`.  |
| `strategyDelegateFeeRate` | `uint32`  | Share of gross yield paid to the Strategy Delegate, where `1e6` is 100%. |
| `strategyProtocolFeeRate` | `uint32`  | Share of gross yield paid to the Maple treasury, where `1e6` is 100%.   |
| `yieldCap`                | `uint256` | Maximum `yield` a single `realizeYield()` call may bring in.            |

The initializer reverts unless all of the following hold:

* `strategyManager` is not the zero address.
* `fundsAsset` is a registered pool asset on `MapleGlobals` (`isPoolAsset`).
* The Strategy Manager's factory is a registered `STRATEGY_MANAGER_FACTORY` instance on Globals, and `strategyManager` is an instance of that factory.
* `strategyManager.underlyingStrategy()` already equals the new strategy's address. The Strategy Manager must point at this strategy before the strategy accepts the pairing, which makes the 1:1 binding a guarantee rather than a convention.
* `strategyDelegateFeeRate + strategyProtocolFeeRate` does not exceed `1e6`.

## Access control

The strategy stores only two addresses, `strategyManager` and `fundsAsset`. It reads every other actor live on each call: the Strategy Delegate from `strategyManager.strategyDelegate()`, and the Governor, Operational Admin, Security Admin and treasury from `MapleGlobals`. Rotating any of them takes effect immediately on every Allocation Strategy. A Managed Wallet must pass both an allowlist on Globals and a per-strategy permission flag, described on [Managed Wallets](managed-wallets.md).

| Function                            | Allowed callers                                                       |
| ----------------------------------- | --------------------------------------------------------------------- |
| `fundUnderlyingStrategy`            | Strategy Manager                                                      |
| `withdrawFromUnderlyingStrategy`    | Strategy Manager                                                      |
| `deployAssets`                      | Managed Wallet with `canDeployAssets`                                 |
| `returnAssets`                      | Managed Wallet with `canReturnAssets`                                 |
| `realizeYield`                      | Managed Wallet with `canRealizeYield`                                 |
| `cancelYield`                       | Strategy Delegate, Security Admin                                     |
| `impair`                            | Strategy Delegate, Operational Admin                                  |
| `removeImpairment`                  | Strategy Delegate, Operational Admin                                  |
| `recognizeLoss`                     | Strategy Delegate, Operational Admin                                  |
| `recognizeLossAndRemoveImpairment`  | Strategy Delegate, Operational Admin                                  |
| `setDeploymentCaps`                 | Strategy Delegate, Security Admin                                     |
| `setPermissions`                    | Strategy Delegate, Security Admin                                     |
| `setMetadata`                       | Strategy Delegate, Operational Admin                                  |
| `setStrategyDelegateFeeRate`        | Strategy Delegate                                                     |
| `setStrategyProtocolFeeRate`        | Governor, Operational Admin                                           |
| `setYieldCap`                       | Strategy Delegate, Operational Admin                                  |
| `skim`                              | Strategy Delegate, Operational Admin                                  |
| `multicall`                         | Anyone. Each batched call enforces its own check against the original caller. |
| `upgrade`                           | Security Admin                                                        |
| `migrate`, `setImplementation`      | Factory                                                               |

Every state-changing function except `multicall` carries `whenNotPaused`, so the Security Admin can pause any of them individually or pause the whole contract through Globals. See [Emergency Protocol Pause](../../security/emergency-protocol-pause.md).

### Multicall

`multicall(data)` runs each entry in `data` as a `delegatecall` back into the strategy and reverts the whole batch with the first inner error. Because a `delegatecall` keeps `msg.sender`, each inner function checks the address that called `multicall()`, not the strategy itself, so routing a privileged call through `multicall()` gains nothing. The reentrancy lock is taken and released per inner call, so a batch of guarded functions runs in sequence without tripping it. A typical use is impairing one position and recognizing a loss on another in one transaction.

## Pages

{% content-ref url="managed-wallets.md" %}
[managed-wallets.md](managed-wallets.md)
{% endcontent-ref %}

{% content-ref url="accounting-and-fees.md" %}
[accounting-and-fees.md](accounting-and-fees.md)
{% endcontent-ref %}

{% content-ref url="funding-and-withdrawals.md" %}
[funding-and-withdrawals.md](funding-and-withdrawals.md)
{% endcontent-ref %}

{% content-ref url="impairments-and-losses.md" %}
[impairments-and-losses.md](impairments-and-losses.md)
{% endcontent-ref %}

## Interfaces

{% content-ref url="../../interfaces/allocation-strategy.md" %}
[allocation-strategy.md](../../interfaces/allocation-strategy.md)
{% endcontent-ref %}

{% content-ref url="../../interfaces/allocation-strategy-factory.md" %}
[allocation-strategy-factory.md](../../interfaces/allocation-strategy-factory.md)
{% endcontent-ref %}

{% content-ref url="../../interfaces/allocation-strategy-initializer.md" %}
[allocation-strategy-initializer.md](../../interfaces/allocation-strategy-initializer.md)
{% endcontent-ref %}
