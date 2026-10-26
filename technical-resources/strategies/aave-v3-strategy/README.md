# Aave V3 Strategy

The Aave V3 Strategy is an Underlying Strategy that supplies a Pool's capital to a single Aave V3 lending market and holds the interest-bearing aToken in return. It lets Pools earn Aave supply yield through a [Strategy Manager](../strategy-manager.md), with Maple's accounting, fee collection and loss controls wrapped around the position.

The contract is `MapleAaveV3Strategy` (`STRATEGY_TYPE = "AAVEV3"`). It targets any Aave V3-compatible market. The strategy reads the market's pool and underlying asset from the aToken itself, and a liquidity switch (`useVirtualUnderlyingBalance`) exists so it can also value positions in Aave V3 forks, such as SparkLend, that do not track reserve liquidity virtually. See [Accounting and Fees](accounting-and-fees.md).

Each strategy instance is bound to one Strategy Manager and one aToken at initialization. Neither binding can change. The Strategy Manager is the only caller that moves capital in or out, and the Pool never calls the strategy directly.

## Initialization

The [Strategy Deployer](../strategy-deployer.md) deploys the strategy as an upgradeable proxy through `MapleAaveV3StrategyFactory.createInstance()`. The factory requires `Globals.canDeploy(msg.sender)`. Upgrades follow the standard Maple proxy pattern, see [Proxies and Upgradeability](../../protocol-overview/proxies-and-upgradeability.md).

The initializer decodes a `strategyManager` address followed by an `AaveV3StrategyInitializerParams` struct.

| Parameter | Type | Description |
|---|---|---|
| `strategyManager` | `address` | The Strategy Manager this strategy serves. |
| `aaveToken` | `address` | The Aave aToken for the target reserve. The strategy derives `fundsAsset` from `UNDERLYING_ASSET_ADDRESS()` and `aavePool` from `POOL()`. |
| `strategyDelegateFeeRate` | `uint32` | Share of yield paid to the Strategy Delegate, 6 decimals (`1e6` is 100%). |
| `strategyProtocolFeeRate` | `uint32` | Share of yield paid to the Maple Treasury, 6 decimals. |
| `referralCode` | `uint16` | Aave referral code passed on every `supply()` call. |
| `useVirtualUnderlyingBalance` | `bool` | How `availableToWithdraw()` reads the reserve's free liquidity. |
| `strategyMetadata` | `string` | Optional free-form label for off-chain tooling. |

The initializer reverts unless all of the following hold:

1. `strategyManager` and `aaveToken` are non-zero.
2. `strategyDelegateFeeRate + strategyProtocolFeeRate <= 1e6`.
3. The Strategy Manager's factory is registered in Globals as a `STRATEGY_MANAGER_FACTORY`, and `strategyManager` is an instance of that factory.
4. `strategyManager.underlyingStrategy()` equals the strategy's own address. The Strategy Manager must already point at this strategy, which makes the pairing a two-sided guarantee.
5. `aaveToken` is registered in Globals as a `STRATEGY_VAULT`.
6. The derived `fundsAsset` is a valid Pool asset in Globals.

On success the initializer stores the parameters, arms the reentrancy lock and emits `Initialized(strategyManager, params)`.

## Access control

The strategy stores only the Strategy Manager address. It reads every other actor live on each call: the Strategy Delegate from `strategyManager.strategyDelegate()`, and the Governor, Operational Admin, Security Admin and Maple Treasury from Globals. Rotating any of those addresses takes effect on the strategy immediately.

| Function | Allowed callers |
|---|---|
| `fundUnderlyingStrategy` | Strategy Manager |
| `withdrawFromUnderlyingStrategy` | Strategy Manager |
| `impair` | Strategy Delegate, Operational Admin |
| `removeImpairment` | Strategy Delegate, Operational Admin |
| `recognizeLoss` | Strategy Delegate, Operational Admin |
| `recoverPosition` | Strategy Delegate, Operational Admin |
| `claimRewards` | Strategy Delegate, Operational Admin |
| `setMetadata` | Strategy Delegate, Operational Admin |
| `setReferralCode` | Strategy Delegate, Operational Admin |
| `setStrategyDelegateFeeRate` | Strategy Delegate |
| `setStrategyProtocolFeeRate` | Governor, Operational Admin |
| `setUseVirtualUnderlyingBalance` | Governor, Operational Admin |
| `multicall` | Anyone. Each inner call runs its own checks against the original caller. |
| `upgrade` | Security Admin |
| `migrate` | Factory |
| `setImplementation` | Factory |

Two modifiers apply across the table:

- `whenNotPaused` guards every state-changing function except `multicall`. Globals can pause each function selector individually, see [Emergency Protocol Pause](../../security/emergency-protocol-pause.md).
- `whenLossNotRecognized` guards every state-changing function except `recoverPosition`, `claimRewards`, `multicall` and the proxy functions. See [Impairments and Losses](impairments-and-losses.md).

## Multicall

`multicall(bytes[] data)` delegatecalls each entry back into the contract and reverts the whole batch with the first inner error. It has no access, pause or reentrancy check of its own. Each inner call runs its own checks against the original caller.

## Contract interfaces

{% content-ref url="../../interfaces/aave-v3-strategy.md" %}
[aave-v3-strategy.md](../../interfaces/aave-v3-strategy.md)
{% endcontent-ref %}

{% content-ref url="../../interfaces/aave-v3-strategy-factory.md" %}
[aave-v3-strategy-factory.md](../../interfaces/aave-v3-strategy-factory.md)
{% endcontent-ref %}

{% content-ref url="../../interfaces/aave-v3-strategy-initializer.md" %}
[aave-v3-strategy-initializer.md](../../interfaces/aave-v3-strategy-initializer.md)
{% endcontent-ref %}
