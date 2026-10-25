# Sky Strategy

The Sky Strategy deploys Pool capital into Sky's savings system. It converts the Pool's funds asset (USDC, which Sky calls the "gem") into USDS through a Sky Peg Stability Module (PSM) and deposits that USDS into the sUSDS savings vault, where it earns the Sky Savings Rate.

`MapleSkyStrategy` is an Underlying Strategy. It takes capital from, and returns capital to, the single [Strategy Manager](../strategy-manager.md) it is bound to. Yield accrues passively as the sUSDS position appreciates, and the strategy harvests Strategy Delegate and protocol fees out of that growth whenever the position is touched.

## Initialization

The [Strategy Deployer](../strategy-deployer.md) creates the strategy as an upgradeable proxy through `MapleSkyStrategyFactory`, whose `createInstance()` requires the caller to pass `canDeploy()` on Globals. The initializer decodes a `strategyManager` address followed by a `SkyStrategyInitializerParams` struct:

| Parameter | Description |
|---|---|
| `fundsAsset` | The Pool asset the strategy accepts, for example USDC. Must equal `psm.gem()`. |
| `psm` | The Sky PSM used for every conversion between the funds asset and USDS. |
| `savingsUsds` | The sUSDS ERC-4626 vault. Its `asset()` is stored as `usds`. |
| `strategyDelegateFeeRate` | Share of yield paid to the Strategy Delegate, with 6 decimals (`1e6` is 100%). |
| `strategyProtocolFeeRate` | Share of yield paid to the Maple Treasury, same precision. |
| `referralCode` | Sky referral code passed on every `deposit()` into sUSDS. |
| `strategyMetadata` | Free-text label for off-chain tooling. |

Initialization runs once and reverts unless all of the following hold:

- `strategyManager`, `savingsUsds` and `psm` are non-zero.
- `strategyDelegateFeeRate + strategyProtocolFeeRate <= 1e6`.
- `fundsAsset` is a registered Pool asset on Globals.
- The Strategy Manager's factory is a registered `STRATEGY_MANAGER_FACTORY` instance on Globals, and the Strategy Manager is an instance of that factory.
- `strategyManager.underlyingStrategy()` already points at this strategy. The binding is checked from both sides, so the two contracts cannot be mismatched.
- `savingsUsds` is a registered `STRATEGY_VAULT` instance and `psm` is a registered `PSM` instance on Globals.
- `psm.gem() == fundsAsset` and `psm.usds() == savingsUsds.asset()`, so the PSM, the vault and the strategy agree on both tokens.
- `psm.pocket()` is non-zero. The strategy only supports LitePSM-style PSMs, which hold their gem reserves in a separate pocket address. See [available liquidity](accounting-and-fees.md#available-liquidity).

`strategyManager`, `fundsAsset`, `psm`, `savingsUsds` and `usds` cannot change after initialization.

## Access control

The strategy stores no admin addresses of its own. It reads the Strategy Delegate from `strategyManager.strategyDelegate()` and the Governor, Operational Admin, Security Admin and Treasury from Globals on every call, so rotating any of them takes effect immediately.

| Function | Allowed callers |
|---|---|
| `fundUnderlyingStrategy` | Strategy Manager |
| `withdrawFromUnderlyingStrategy` | Strategy Manager |
| `impair`, `removeImpairment`, `recognizeLoss`, `recoverPosition` | Strategy Delegate, Operational Admin |
| `setFallbackTout`, `setReferralCode`, `setMetadata` | Strategy Delegate, Operational Admin |
| `setStrategyDelegateFeeRate` | Strategy Delegate |
| `setStrategyProtocolFeeRate` | Governor, Operational Admin |
| `multicall` | Anyone. Each inner call runs its own checks against the original caller. |
| `upgrade` | Security Admin |
| `migrate`, `setImplementation` | Factory |

Every state-changing function except `multicall` can be paused through Globals (`isFunctionPaused`). Once a loss is recognized, every state-changing function except `recoverPosition`, `multicall` and the proxy functions reverts. See [Impairments and Losses](impairments-and-losses.md).

## Multicall

`multicall(bytes[] data)` delegatecalls each entry back into the contract and reverts the whole batch with the first inner error. It has no access, pause or reentrancy check of its own. Each inner call runs its own checks against the original caller.

## Contract interfaces

{% content-ref url="../../interfaces/sky-strategy.md" %}
[sky-strategy.md](../../interfaces/sky-strategy.md)
{% endcontent-ref %}

{% content-ref url="../../interfaces/sky-strategy-factory.md" %}
[sky-strategy-factory.md](../../interfaces/sky-strategy-factory.md)
{% endcontent-ref %}

{% content-ref url="../../interfaces/sky-strategy-initializer.md" %}
[sky-strategy-initializer.md](../../interfaces/sky-strategy-initializer.md)
{% endcontent-ref %}
