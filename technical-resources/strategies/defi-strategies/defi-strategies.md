# Overview

The Maple Strategies repository contains three secondary yield-generating strategies that can be added to a Maple Pool. These secondary strategies will be used to park capital before it is deployed to loans (Maple's primary yield-generating source) or to act as instant liquidity that can be called upon to facilitate withdrawal requests.

# Common Functionality

## Funding & Withdrawing

Each strategy has the ability to deposit pool assets into, and withdraw pool assets from, the underlying protocol.

Pool assets are pulled into the strategy contracts via `requestFunds()` in the `PoolManager` contract, following the same flow that both open-term and fixed-term Loan Managers do.

### Known Issues
- Note that a decision was made not to support redeem-style flows that allow 100% of the shares to be redeemed; as a consequence, some dust may be left in the contracts.
- There is also a known issue due when attempting withdraw the full `assetsUnderManagement()` amount of a strategy in the same block. This is due to 'fees' being withdrawn first leading to a `1 wei` round up in the `shares` or `aTokens` required resulting in remaining `shares` or `aTokens` being insufficient by `1 wei` to complete the full withdrawal. This in practice isn't a concern as the txn to withdraw the full amount won't atomically land on chain as the `assetsUnderManagement()` is read with the expectation that the yield from a strategy continues to accrue. We can also send `1 wei` less then the max withdrawal amount.

## Strategy Fees

Aave, Basic, and Sky strategies charge a performance fee on realized yield. Core strategies do not charge performance fees.

For Aave/Basic/Sky, a snapshot of total assets (`lastRecordedTotalAssets`) is taken during strategy interactions such as `fundStrategy(...)`, `withdrawFromStrategy(...)`, and `setStrategyFeeRate(...)`. On the next interaction, the delta in total assets determines the fee that is sent to the Maple Treasury.

The strategy fee is calculated using the formula:

$$
\huge
\text{strategyFee} = \dfrac{\text{yieldAccrued} \times \text{strategyFeeRate}}{1 \times 10^6}
$$

**Where:**
- $\text{yieldAccrued}$ is the total yield accrued since the last `fundStrategy(...)`, `withdrawFromStrategy(...)`, or `setStrategyFeeRate(...)` call (Aave/Basic/Sky).
- $\text{strategyFeeRate}$ is the fee rate for the strategy, which can be no greater than $1 \times 10^6$.
- $1 \times 10^6$ represents the scaling factor for 100%, declared as the constant `HUNDRED_PERCENT` in the contracts.

## Assets Under Management

The Assets Under Management (AUM) is reported at a given block as the value of the strategy in terms of the pool's underlying asset, net of fees. This calculation is unique to each strategy depending on the underlying protocol.

$$
\huge
\text{assetsUnderManagement} = \text{currentTotalAssets} - \text{currentAccruedFees}
$$

**Where:**
- $\text{currentTotalAssets}$ is the gross value of the strategy at that block, which may increase if yield is generated or decrease if there is a loss in the strategy.
- $\text{currentAccruedFees}$ is the calculated fee at that block, which is positive if the strategy has gained value since the last snapshot (`lastRecordedTotalAssets`), otherwise 0.

## Strategy States

A strategy contract can be in one of the following states:

$$
\huge
\text{Strategy State} \in \{ \text{Active},\ \text{Impaired},\ \text{Inactive} \}
$$

### Active

Refers to the default state of a strategy where it can be used to access all external functions, and it is expected that `assetsUnderManagement` is being correctly reported. This can include situations where the strategy is earning yield or even at a loss, as long as it's correctly reported and the underlying assets can be withdrawn.

Please note that when a strategy is reactivated, protocol admins may update the accounting baseline (`lastRecordedTotalAssets`) to avoid retroactive fees for the inactive/impaired period. For Aave/Basic/Sky this is controlled by a `reactivateStrategy(bool updateAccounting)` flag. NOTE: The Core strategy exposes `reactivateStrategy()` without an update‑accounting parameter.

### Impaired

The Impaired state is expected to be enabled when the `assetsUnderManagement` is being correctly reported by the underlying protocol, but there is an issue when withdrawing—for example, if you're unable to get back what is reported in `assetsUnderManagement`, or the withdrawal reverts.

While a strategy is impaired, `unrealizedLosses` is equal to `assetsUnderManagement`. As a result, when a user goes to withdraw from a Maple Pool, the `unrealizedLosses` are reduced from `totalAssets` in the pool when calculating the value of a share. This is the same mechanism used when loans are impaired.

The benefit here is that users can continue to withdraw if they wish, with the reduced share price ensuring no LP is treated unfairly. However, a strategy can be reactivated, which would cause a jump in `totalAssets` equal to the `assetsUnderManagement` being reported (by reducing `unrealizedLosses` to `0`). Therefore, communication with LPs is important to gauge if a strategy will be reactivated for example, if hacked funds are returned to the external protocol or the external protocol tops up via an insurance fund.

**Note:**
- Calling `withdrawFromStrategy()` whilst `impaired` skips any fee logic.
- If the protocol is `impaired` and there is a gain in yield resulting in fees we will set the strategy state back to `active` before withdrawing. Withdrawing when `impaired` will be reserved for when there is a loss in the strategy. This is cause if there are any fees to be accrued and the admins withdraw in an `impaired` state the fees are lost.

### Inactive

The Inactive state is to be used as a last resort, as it detaches the `assetsUnderManagement` external calls to the external protocol and returns 0. The main use case of this is if the underlying protocol starts reverting on the external calls; this would block LPs from depositing and withdrawing from a Maple Pool, as the `totalAssets` calculation in the `PoolManager` relies on the strategy reporting `assetsUnderManagement` without reverting.

A secondary use case of Inactive is also to mark a strategy to 0 if it's confirmed that funds cannot be recovered, which is akin to a default.

**Note:**
- Calling `withdrawFromStrategy()` whilst `inactive` skips any fee logic.
- It's a known issue that if the strategy is set back to `inactive` -> `active` there will be a jump in `assetsUnderManagement()` which a new depositor can arbitrage by getting shares for a lower amount of pool assets. To combat this when the `inactive` state is used on a strategy the Pool Liquidity Cap will be used to stop new deposits whilst we assess the situation.

## Deployments & Proxy Pattern

All strategies will be deployed as unique proxy instances per pool via the `MapleStrategyFactory` contract. The `MapleStrategyFactory` contract is a redeployment of a previously audited factory. The proxy pattern is further explained in the Maple Protocol Gitbook linked [here](https://maplefinance.gitbook.io/maple/technical-resources/protocol-overview/proxies-and-upgradeability).

The factories and how they fit into the Maple Protocol can further be visualized in the Updated Protocol Architecture diagram [here](https://github.com/maple-labs/maple-core-v2-private/blob/main/docs/architecture.png).

# Aave Strategy

The Aave Strategy is designed for a Maple Pool to deploy into a respective Aave V3 Pool with the same underlying asset as the Maple Pool. The strategy uses the `balanceOf(aTokenAmount)` of the rebasing aToken held by the strategy contract to report `assetsUnderManagement`.

To illustrate, please refer to the integration tests [here](https://github.com/maple-labs/maple-core-v2-private/blob/main/tests/integration/strategies/AaveStrategy.t.sol), where the Aave V3 USDC Pool is used as the yield-generating strategy.

**Notes:**
- The Aave Strategy could potentially accrue additional rewards from Aave which can be claimed using the `claimRewards()` function.

Addresses on Ethereum Mainnet that will be used for Aave Pools can be found in the address registry [here](https://github.com/maple-labs/address-registry/blob/main/MapleAddressRegistryETH.md#external-protocol-contracts).

# Sky Strategy

The Sky Strategy is designed to make use of the Sky Savings Rate (SSR) by using the Peg Stability Module (PSM). This strategy is specifically made for Maple Pools where the underlying asset is USDC, i.e., the `gem` asset on the PSM.

**Deposit Flow:**
1. USDC is pulled from the Maple Pool and swapped into USDS via the PSM.
2. USDS is deposited into sUSDS to earn the SSR.

**Withdraw Flow:**
1. sUSDS is burned to redeem USDS.
2. USDS is swapped via the PSM into USDC and returned back to the Maple Pool.

**Notes:**
- The PSM can have a fee when swapping USDC into USDS (`tin`) or when swapping USDS into USDC (`tout`).
- It's assumed that USDS and USDC are 1:1 in USD value due to the PSM allowing zero-slippage swaps (when `tin` and `tout` are 0).
- When calculating `assetsUnderManagement`, alongside netting out performance fees, any `tout` is also netted out. It is known that a deposit will result in the `assetsUnderManagement` being incremented slightly less than the deposit amount due to PSM fees if set.
- The protocol retains the ability to set a new `PSM` address in case Sky upgrades their contracts.

### Known Issues
- It is known that if the `PSM` doesn't have enough `USDC` liquidity withdrawing can fail. This will be managed by monitoring liquidity.
- It is known that if there is a positive `tin` that the pools `totalAssets()` will drop by the fee amount, whilst unlikely to use this strategy when there is a positive `tin`, it is possible for a LP to withdraw prior to the strategy being funded to then redeposit not having their shares "pay" the `tin` like all other LPs. This will be managed by monitoring the withdrawal queue which we process as user's can't unilaterally exit.
- It is also noted that is the `DaiJoin` contract is caged or if the `PSM` has halted this can cause the `assetsUnderManagement()` to revert in which case the strategy can be either set to `Inactive` or if a new `PSM` is available we can swap the `PSM`. This will be dealt on a case by case basis.
- `_gemForUsds()` can have a rounding error up to `1e12 USDS` leaving some dust in the contract, this is acceptable given the conversion needed from `1e18 -> 1e6`

Addresses on Ethereum Mainnet that will be used for Sky contracts can be found in the address registry [here](https://github.com/maple-labs/address-registry/blob/main/MapleAddressRegistryETH.md#external-protocol-contracts).

# Basic Strategy

The Basic Strategy is a generic strategy to be used with any fully ERC-4626 compliant vault. This includes any fees being included as part of the `previewRedeem()` call, as per the EIP spec [here](https://eips.ethereum.org/EIPS/eip-4626).

Each ERC-4626 compliant vault that is being considered for integration will be tested for compatibility first before being onboarded, similar to how ERC-20 tokens are vetted.

**Notes:**
- Basic Strategy adds explicit slippage bounds:
  - `fundStrategy(assetsIn, minSharesOut)` enforces a minimum shares check.
  - `withdrawFromStrategy(assetsOut, maxSharesBurned)` enforces a maximum shares burned check.
- Aave and Sky strategies use `fundStrategy(assetsIn)` and `withdrawFromStrategy(assetsOut)` without slippage parameters.
- Core Strategy uses a queue‑based withdrawal flow: `requestWithdrawFromStrategy(assetsOut)`, then `removeShares(...)`/`removeSharesById(...)` as needed, and `pushAssetsToPool()` to return funds to the Pool.
- Each ERC-4626 vault will need to be tested to ensure upon withdrawal the amount of shares required to withdraw the known assets doesn't drastically change e.g a slashing event as in this case slippage controls would be required. These controls can be added in a future upgrade if needed or a bespoke strategy contract can be implemented.

## Strategy Interfaces

- Core Strategy
  - `fundStrategy(uint256 assetsIn)`
  - `requestWithdrawFromStrategy(uint256 assetsOut)`
  - `removeShares(uint256 shares)` / `removeSharesById(uint256 requestId, uint256 shares)`
  - `pushAssetsToPool()`
  - No performance fees (STRATEGY_TYPE = "CORE").

- Basic Strategy
  - `fundStrategy(uint256 assetsIn, uint256 minSharesOut)`
  - `withdrawFromStrategy(uint256 assetsOut, uint256 maxSharesBurned)`
  - Performance fee based on `lastRecordedTotalAssets` and `strategyFeeRate` (scaled by 1e6).

- Aave Strategy
  - `fundStrategy(uint256 assetsIn)`
  - `withdrawFromStrategy(uint256 assetsOut)`
  - Performance fee based on `lastRecordedTotalAssets` and `strategyFeeRate` (scaled by 1e6).

- Sky Strategy
  - `fundStrategy(uint256 assetsIn)` (PSM swap to USDS, then ERC‑4626 deposit)
  - `withdrawFromStrategy(uint256 assetsOut)` (withdraw and PSM redeem path)
  - Performance fee based on `lastRecordedTotalAssets` and `strategyFeeRate` (scaled by 1e6).
