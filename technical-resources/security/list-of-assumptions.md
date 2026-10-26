# Trust Assumptions

This page lists the assumptions the smart contracts team makes about trusted actors, integrated protocols and operating practice. Anything outside these assumptions is a bug and is in scope for the [bug bounty](security.md#bug-bounty).

## Core protocol assumptions

#### 1. All external calls to contracts that are part of the Maple Protocol System can be assumed to be non-reentrant.

Since all contracts that are deployed as part of the Maple protocol are developed by the Maple smart contracts team and are externally audited before deployment, it can be assumed that the contracts are both non-reentrant and non-malicious.

#### 2. All external calls to ERC-20 contracts can be assumed to be non-reentrant.

This assumption is made since all tokens that are used in the Maple protocol have to be added to the protocol allowlist, in the MapleGlobals contract. This means that the smart contracts team will audit the ERC-20 contracts and ensure that reentrancy is impossible.

#### 3. Pool Delegates are trusted actors.

Pool Delegates have to go through a KYC process and have to get onboarded to the Maple protocol by the Governor. Lenders trust a Pool Delegate with their funds when they enter a Maple Pool.

#### 4. The Governor & Operational Admin are trusted actors.

Governor control is exercised via the on‑chain `GovernorTimelock`, whose controlling roles (e.g., proposer, executor, role admin) are held by Maple managed multisigs. 

The Operational Admin is also a multisig controlled by Maple managed multisigs.

#### 5. Loans are expected to be instantiated with reasonable terms.

During the fuzz testing process, it was discovered that certain overflow conditions can occur in the amortization calculation of the loan, but only at "unreasonable" upper bounds (E.g., 100-year loans with 1 year payment intervals at 100% APR, for >$10b).

#### 6. Pool Delegates don't try to prevent withdrawals.

It's known that, in theory, withdrawal managers can be configured to unreasonable terms, for example, making the withdrawal window 1 second, or the cycle duration to be large,or pool delegates can set the withdrawal manager address to an invalid address. However, it's understood that pool delegates are trusted actors and they are working to making the pool well functioning.

## Strategy assumptions

The November 2026 release adds the Strategy Manager, Strategy Deployer, Liquidity Router, the Aave V3 and Sky strategies and the Allocation Strategy. The assumptions below are new or change scope in that release. The core assumptions above still hold.

#### 1. Calls made by Maple's own contracts are non-malicious.

These contracts are developed by the Maple smart contracts team and audited before deployment, like the rest of the protocol. Calls between them, for example a Strategy Manager calling `requestFunds()` on a Pool Manager, are trusted.

#### 2. Integrated protocols account for their positions correctly.

`MapleAaveV3Strategy` values its position as its aToken balance. `MapleSkyStrategy` values its position as the funds asset the PSM would return for `previewRedeem()` of its sUSDS balance. Neither uses an independent price oracle, so once Maple integrates an underlying protocol it trusts that protocol's own accounting.

#### 3. Strategy Delegates are trusted actors, comparable to Pool Delegates.

A Strategy Delegate owns a Strategy Manager, sets their own fee rate with `setStrategyDelegateFeeRate()`, can block any Pool from funding it with `setPoolManagerCap()`, and keeps every operating right while the underlying position is impaired. A Pool that funds a Strategy Manager trusts that delegate the way Lenders trust a Pool Delegate. The Governor or Operational Admin onboards a Strategy Delegate with `setValidStrategyDelegate()`, and `activateStrategyManager()` lets a delegate own only one Strategy Manager at a time.

#### 4. The Operational Admin does not reassign a Strategy Delegate without cause.

Only the Operational Admin can call `setPendingStrategyDelegate()`, and only the proposed address needs to call `acceptStrategyDelegate()`. The current delegate's consent is never checked. The Operational Admin is assumed to use this only to record a handover both parties have already agreed.

#### 5. Liquidity Bots and the Liquidity Router are trusted Maple infrastructure.

`fundStrategyManager()` is restricted to an Operator, meaning the Strategy Delegate or an address Globals registers as `LIQUIDITY_BOT` or `LIQUIDITY_ROUTER`. `processRedemption()` is open to Operators and the Operational Admin. The per-pool and strategy caps bound how much a bot can move, not when or in whose interest. Maple is assumed to secure the bot keys like the rest of its operational infrastructure and to run them in each Pool's interest. The contracts do stop bots from acting on an impaired strategy, see [Liquidity Bot Actions](../admin-functions/liquidity-bot-actions.md#the-impairment-block).

#### 6. Managed Wallets in the Allocation Strategy are trusted actors.

The Allocation Strategy sends funds to wallets Maple operates. A wallet must be registered in Globals as a `MAPLE_MANAGED_WALLET` by the Governor or Operational Admin before it can receive anything, and the Strategy Delegate or Security Admin then grants it permissions and a deployment cap. Once assets leave through `deployAssets()`, no lock, collateral or on-chain mechanism forces them back. Recovery depends on Maple's internal controls.

#### 7. Loss recognition on any strategy is a discretionary judgment.

The Strategy Delegate or the Operational Admin can call `impair()`, `removeImpairment()` and `recognizeLoss()` on the Aave V3, Sky and Allocation strategies at any time, with no proof, oracle input or waiting period. These actors are assumed to use that power only when a loss has genuinely occurred.

#### 8. Damage mitigation functions are used responsibly.

The Governor or Security Admin can pause the whole protocol, one contract or one function through Globals. The Strategy Delegate or Operational Admin can set a `fallbackTout` on the Sky strategy that alone determines how the position is valued while the PSM is halted. The Strategy Delegate or Security Admin can call `cancelYield()` on the Allocation Strategy to claw back yield that has not yet streamed to the Pool. These are assumed to be reserved for genuine incidents.

#### 9. Pool liquidity is not reserved for queued withdrawals.

A strategy cap limits how much a strategy can hold in total. Nothing on-chain reserves Pool cash for Lenders already in the withdrawal queue, and `requestFunds()` only checks the cap. Maple is assumed to decide when to fund strategies and process withdrawals so that Lenders are not routinely left short.

#### 10. Strategy Manager redemption requests are processed in the order they were made.

`requestRedeem()` only adds to `pendingSharesOf[poolManager]`. There is no queue, timestamp or ordering between requests from different Pools. An Operator or the Operational Admin can settle any pending request in any order and any amount up to what is pending. Operators are assumed to process requests first in, first out.

#### 11. Redemption liveness depends on Operators remaining available.

A Pool Delegate can call `requestRedeem()` and `cancelRedemption()` for their own Pool at any time, but only an Operator or the Operational Admin can call `processRedemption()`. Maple is assumed to keep enough redundancy in its bots and admin multisigs that a queued redemption can always be executed.

#### 12. The Strategy Deployer and Pool Deployer are the only path used to create Strategy Managers and Pool Managers.

Until `completeConfiguration()` is called, anyone can call `setUnderlyingStrategy()`, `setPoolManagerCap()` and `setStrategyLiquidityCap()` on a new Strategy Manager, and anyone can call `addStrategy()`, `addStrategyManager()`, `setWithdrawalManager()` and the other setters on a new Pool Manager. This is safe only because the deployers perform creation and configuration in one transaction. An instance created directly through its factory would sit open until configured.

#### 13. The bootstrap amount is set before a strategy's first real deposit.

The Strategy Deployer transfers `bootstrapMint(fundsAsset)` from the Strategy Delegate into the underlying strategy and records the resulting shares against the zero address, which protects the share price before the first Pool funds the strategy. If Globals holds zero for that asset the step is skipped and the Strategy Manager starts with no shares. Setting the amount is an operational checklist item, not something the contracts enforce.

#### 14. Bootstrap shares remain outstanding for the life of a Strategy Manager.

The shares `completeConfiguration()` records against the zero address cannot be redeemed, because `processRedemption()` only accepts a valid Pool Manager. `totalShares` therefore never returns to zero after configuration, and the share price never resets to one asset per share.
