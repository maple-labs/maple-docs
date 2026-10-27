# Protocol Actors

Every privileged action in Maple belongs to one of the roles below. Globals records most roles and each contract reads them live, so a role change in Globals takes effect everywhere at once.

| Actor | Where the role is set | Scope |
|---|---|---|
| Lender | Pool Permission Manager allowlists | One or more Pools |
| Borrower | `MapleGlobals.setValidBorrower()` | Its own loans |
| Pool Delegate | `MapleGlobals.setValidPoolDelegate()`, owns one Pool Manager | One Pool |
| Strategy Delegate | `MapleGlobals.setValidStrategyDelegate()`, owns one Strategy Manager | One Strategy Manager and its Underlying Strategy |
| Governor | `GovernorTimelock`, the admin of Globals | Whole protocol, timelocked |
| Operational Admin | `MapleGlobals.setOperationalAdmin()` | Whole protocol, day to day |
| Security Admin | `MapleGlobals.setSecurityAdmin()` | Pauses, upgrades, incident controls |
| Liquidity Bot | `LIQUIDITY_BOT`, `LIQUIDITY_ROUTER_BOT` and `WITHDRAWAL_REDEEMER` keys in Globals | Capital movement within caps |
| Managed Wallet | `MapleGlobals.setValidMapleManagedWallet()` plus per-strategy permissions | Allocation Strategies |

## Lender

Lenders deposit a Pool's asset and hold ERC-4626 shares. Every Pool call checks the caller against the [Pool Permission Manager](../singletons/pool-permission-manager.md), so a lender needs permission for that Pool before depositing. Lenders exit by calling `requestRedeem()` and waiting for the Withdrawal Manager queue. Lenders never interact with strategies or loans directly.

## Borrower

A borrower is an institution the Governor or Operational Admin approves in Globals. Borrowers accept loan terms, draw funds, make payments and return called principal on their own Open Term Loan contracts. See [Open Term Loan](../strategies/open-term-loans/open-term-loan.md).

## Pool Delegate

A Pool Delegate owns exactly one Pool Manager and sets limits rather than moving strategy capital. In code the Pool Delegate can:

* Deploy its Pool through `MaplePoolDeployer.deployPool()`.
* Set `liquidityCap`, `delegateManagementFeeRate` and the Pool Permission Manager on the Pool Manager.
* Set a cap per attached strategy with `setStrategyCap()`. The Pool Manager refuses any funding request that would push a strategy's exposure above its cap.
* Fund, call and impair loans through the Open Term Loan Manager, and trigger a default through `PoolManager.triggerDefault()`.
* Request or cancel its own Pool's strategy redemptions with `requestRedeem()` and `cancelRedemption()` on a Strategy Manager.
* Process lender withdrawals and configure manual withdrawals on the Withdrawal Manager.

The Pool Delegate cannot fund a strategy, process a strategy redemption or attach a strategy to a configured Pool. Those powers sit with Operators and the Governor. The Pool Delegate receives the delegate service fee and delegate management fee on loan payments. See [Pool Delegate functions](../admin-functions/pool-delegate-admin-actions.md).

## Strategy Delegate

A Strategy Delegate owns exactly one Strategy Manager, which Globals enforces through `ownedStrategyManager`. The Strategy Delegate deploys the Strategy Manager and its Underlying Strategy through `MapleStrategyDeployer.deploy()` and pays the bootstrap deposit. It is always an Operator, even while the strategy is impaired. It also:

* Sets `poolManagerCapOf` per Pool and `strategyLiquidityCap` for the whole strategy, shared with the Operational Admin.
* Sets `strategyDelegateFeeRate` on the Underlying Strategy. No other role can.
* Records and removes impairments, recognizes losses and recovers a lost position, shared with the Operational Admin.
* On the Allocation Strategy, sets Managed Wallet permissions and deployment caps and cancels unrealized yield, shared with the Security Admin.

Only the Operational Admin can start a handover with `setPendingStrategyDelegate()`, and the incoming delegate must accept. See [Strategy Delegate functions](../admin-functions/strategy-delegate-actions.md) and [Strategy Manager](../strategies/strategy-manager.md).

## Governor

The Governor is the `GovernorTimelock` contract, the admin of Globals. A multisig proposes, and every action waits for the timelock delay before execution. The Governor sets protocol-wide parameters in Globals: the Treasury, Security Admin and Operational Admin addresses, timelock windows and valid pool assets. Once a Pool is configured, only the Governor can attach a strategy with `addStrategy()` or `addStrategyManager()`. The Governor can also set strategy caps, impair loans, trigger defaults, set the protocol strategy fee rate, pause the protocol and manage factory versions. See [Governor functions](../admin-functions/governor-admin-actions.md) and [Governor Timelock](../singletons/governor-timelock.md).

## Operational Admin

The Operational Admin is Maple's operations multisig. It runs day-to-day administration without the timelock:

* Approves Pool Delegates, Strategy Delegates, borrowers, Managed Wallets, bots, routers and factories in Globals, and activates new Pool Managers and Strategy Managers.
* Sets `bootstrapMint` per asset and the platform fee rates per Pool.
* Shares the Pool Delegate's configuration powers on the Pool Manager, and alone can detach a Strategy Manager with `removeStrategyManager()` once the Pool's position in it is zero.
* Shares the Strategy Delegate's cap, impairment and loss powers, sets `strategyProtocolFeeRate` with the Governor, and can process strategy redemptions.
* Starts Pool Delegate and Strategy Delegate handovers.

It cannot set `strategyDelegateFeeRate`, fund a strategy, or change Managed Wallet permissions and deployment caps. See [Operational Admin functions](../admin-functions/operational-admin-actions.md).

## Security Admin

The Security Admin responds to incidents. With the Governor it can pause the whole protocol or a single contract and unpause a single function (see [Emergency Pause](../security/emergency-protocol-pause.md)). It is the only caller of `upgrade()` on Pool Managers, Strategy Managers and Underlying Strategies, and it can upgrade Loan Managers and Withdrawal Managers alongside the Pool Delegate. On the Allocation Strategy it shares three incident controls with the Strategy Delegate: `setPermissions()`, `setDeploymentCaps()` and `cancelYield()`. See [Security Admin functions](../admin-functions/security-admin-actions.md).

## Liquidity Bot

Liquidity Bots are Maple-operated addresses that move capital between Pools and strategies. The contracts know them only as Globals instance keys:

* `LIQUIDITY_BOT` addresses call a Strategy Manager directly.
* `LIQUIDITY_ROUTER_BOT` addresses call `MapleLiquidityRouter.executeActions()`, which batches actions across Strategy Managers. The router itself is registered as `LIQUIDITY_ROUTER`.
* `WITHDRAWAL_REDEEMER` addresses call `processRedemptions()` on a Withdrawal Manager to pay queued lender withdrawals.

A Strategy Manager treats the Strategy Delegate, a `LIQUIDITY_BOT` and the `LIQUIDITY_ROUTER` as Operators. Operators fund a strategy and request, cancel and process redemptions. Every action stays inside the strategy cap, pool manager cap and strategy liquidity cap. Bots stop as soon as the Underlying Strategy reports an impairment. See [Liquidity Bot functions](../admin-functions/liquidity-bot-actions.md#the-impairment-block) and [Liquidity Router](../strategies/liquidity-router.md).

## Managed Wallet

A Managed Wallet is a Maple-operated address that deploys capital off the Allocation Strategy contract. It must pass two checks: the `MAPLE_MANAGED_WALLET` key in Globals, set by the Governor or Operational Admin, and per-strategy `permissions` set by the Strategy Delegate or Security Admin. With the right flags it can `deployAssets()` up to its `deploymentCapOf`, `returnAssets()`, and `realizeYield()` up to `yieldCap`, subject to a one-hour cooldown shared by all wallets on that strategy. See [Managed Wallets](../strategies/allocation-strategy/managed-wallets.md).
