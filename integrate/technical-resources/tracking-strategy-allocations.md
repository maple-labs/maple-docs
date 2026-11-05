---
description: >-
  Add Maple strategy allocations to your tracking. Query each Pool's position in
  each strategy, its value and the yield it earns from the Maple GraphQL API.
---

# Tracking Strategy Allocations

Maple Pools such as syrupUSDC, syrupUSDT and syrupUSDG deploy capital in two ways: overcollateralized loans, and strategies. A strategy deploys part of a Pool's liquidity into a venue such as U.S. Treasuries, Aave V3, Sky or DeFi markets. If you track Maple Pools as a partner, add strategies to your tracking so you get a complete picture of all allocations.

## What changes for your tracking

{% hint style="info" %}
**Total AUM from the API does not change.** The AUM figures the API already returns include capital in strategies, so a dashboard that reads AUM keeps working without changes.

**Loans and collateral no longer add up to AUM on their own.** Part of each Pool's capital now sits in strategies rather than in loans. If you rebuild AUM from the underlying loans and their collateral, add the strategy allocations to close the gap.
{% endhint %}

AUM breaks down into four parts:

`AUM` = `loansUsd` + `collateralUsd` + `assetsUsd` + `assetsInStrategiesUsd`

| Component | What it is | Where to get it |
| --- | --- | --- |
| `loansUsd` | Principal outstanding on active loans | `syrupGlobals.aumTimeSeries`, or `openTermLoans` / `nativeLoans` per loan |
| `collateralUsd` | USD value of collateral posted against those loans | `syrupGlobals.aumTimeSeries`, or `poolCollaterals` per Pool |
| `assetsUsd` | Cash held by the Pools | `syrupGlobals.aumTimeSeries`, or `poolV2.assets` per Pool |
| `assetsInStrategiesUsd` | Capital the Pools have allocated to strategies | `syrupGlobals.aumTimeSeries`, or the sum of `currentValue` over a Pool's strategy positions |

The per-strategy and per-Pool detail behind `assetsInStrategiesUsd` is described below.

## How strategies are structured

* **Strategy Manager.** Each strategy runs through its own Strategy Manager contract on Ethereum mainnet. One Strategy Manager can serve several Pools, so syrupUSDC and syrupUSDT can hold positions in the same strategy.
* **Positions.** A position is one Pool's stake in one strategy. Its `currentValue` is the live onchain value of that Pool's share, in the Pool asset's decimals.
* **Strategy types.** `strategyType` is `Allocation`, `Aave` (Aave V3) or `Sky`. An Allocation strategy's onchain `metadata` gives its category: `U.S. Treasuries`, `DeFi`, `DEX LP` or `Maple Trading`. Aave V3 and Sky strategies count as `DeFi`.
* **Active strategies.** Filter on `active: true` to return only the strategies in use.

For how the contracts work, see [How Pools Allocate Capital](../../technical-resources/strategies/how-pools-allocate-capital.md).

## Example queries

All queries run against the public Maple GraphQL API at `https://api.maple.finance/v2/graphql` and need no authentication. Addresses sent to the API must be lowercase.

| Pool | `poolId` |
| --- | --- |
| syrupUSDC | `0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b` |
| syrupUSDT | `0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d` |
| syrupUSDG | `0x87b65c4aaffa76881f9e96f3e7ed945ddfc3cd7a` |

{% hint style="warning" %}
Example responses on this page are illustrative. Values, positions and strategy states will differ from what the API returns.
{% endhint %}

### AUM breakdown, including strategies

Returns daily AUM split into loans, collateral, cash and strategies. Use it to reconcile the headline AUM against the loan book.

{% tabs %}
{% tab title="Query" %}
```graphql
query AumBreakdown {
  syrupGlobals {
    # WEEK | MONTH | YEAR
    aumTimeSeries(range: WEEK) {
      timestamp              # unix seconds
      loansUsd               # 8 decimals
      collateralUsd          # 8 decimals
      assetsUsd              # 8 decimals, Pool cash
      assetsInStrategiesUsd  # 8 decimals, capital allocated to strategies
    }
  }
}
```
{% endtab %}

{% tab title="Example response" %}
```json
{
  "data": {
    "syrupGlobals": {
      "aumTimeSeries": [
        {
          "timestamp": 1794268800,
          "loansUsd": "150031410306000006",
          "collateralUsd": "219618974536754703",
          "assetsUsd": "3425538528497600",
          "assetsInStrategiesUsd": "12500000000000000"
        }
      ]
    }
  }
}
```

**Reading this example:** the USD fields use 8 decimals, so the day's AUM is $1,500.3M loans + $2,196.2M collateral + $34.3M cash + $125.0M in strategies = $3,855.8M. The figures are illustrative.
{% endtab %}
{% endtabs %}

### List strategies

Returns every active strategy with its fees, caps and the Pools that hold a position in it. It is also the live list of strategy addresses.

{% tabs %}
{% tab title="Query" %}
```graphql
query Strategies {
  strategyManagers(where: { active: true }, first: 100) {
    id                    # Strategy Manager address
    meta {
      name
      venue               # where the strategy deploys, when set; null otherwise
      assets {
        symbol
      }
    }
    strategyType          # Allocation, Aave or Sky
    state                 # Active, Inactive or Impaired
    fundsAsset {
      id
      symbol
      decimals
    }
    delegateFeeRate       # 6 decimals e.g. 100000 = 10% of yield
    protocolFeeRate       # 6 decimals
    strategyLiquidityCap  # in fundsAsset decimals
    impairedAssets        # Aave V3 and Sky losses show here
    allocationStrategy {
      metadata            # onchain JSON e.g. {"category":"U.S. Treasuries"}
      yieldDeadline       # unix seconds; realized net yield vests linearly until then
    }
    positions {
      id                  # {strategy manager address}-{pool manager address}
      pool {
        id
        name
      }
      currentValue        # live onchain value of this Pool's position, in fundsAsset decimals
      poolManagerCap
      strategyCap
      unrealizedLosses
    }
  }
}
```
{% endtab %}

{% tab title="Example response" %}
```json
{
  "data": {
    "strategyManagers": [
      {
        "id": "0xe8c04874b1332a95ba15961c5e4a13f28ba65c3c",
        "meta": { "name": "USTB Strategy (USDC)", "venue": null, "assets": [] },
        "strategyType": "Allocation",
        "state": "Active",
        "fundsAsset": {
          "id": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
          "symbol": "USDC",
          "decimals": 6
        },
        "delegateFeeRate": "0",
        "protocolFeeRate": "100000",
        "strategyLiquidityCap": "200000000000000",
        "impairedAssets": "0",
        "allocationStrategy": {
          "metadata": "{\"category\":\"U.S. Treasuries\"}",
          "yieldDeadline": "1794873600"
        },
        "positions": [
          {
            "id": "0xe8c04874b1332a95ba15961c5e4a13f28ba65c3c-0x7ad5ffa5fdf509e30186f4609c2f6269f4b6158f",
            "pool": {
              "id": "0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b",
              "name": "Syrup USDC"
            },
            "currentValue": "75000000000000",
            "poolManagerCap": "0",
            "strategyCap": "150000000000000",
            "unrealizedLosses": "0"
          }
        ]
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}

### One Pool's allocations

Returns one Pool's positions across all active strategies. The sum of `currentValue` is that Pool's capital in strategies.

{% tabs %}
{% tab title="Query" %}
```graphql
query PoolStrategyAllocations($poolId: String!) {
  strategyManagerPositions(
    where: { pool: $poolId, strategyManager_: { active: true } }
  ) {
    id
    strategyManager {
      id
      meta {
        name
      }
      strategyType
      state
    }
    currentValue      # live onchain value, in the Pool asset's decimals
    depositedAssets   # cumulative assets sent from the Pool
    withdrawnAssets   # cumulative assets returned to the Pool
    poolManagerCap
    strategyCap
    unrealizedLosses
  }
}
```

Variables:

```json
{ "poolId": "0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b" }
```
{% endtab %}

{% tab title="Example response" %}
```json
{
  "data": {
    "strategyManagerPositions": [
      {
        "id": "0xe8c04874b1332a95ba15961c5e4a13f28ba65c3c-0x7ad5ffa5fdf509e30186f4609c2f6269f4b6158f",
        "strategyManager": {
          "id": "0xe8c04874b1332a95ba15961c5e4a13f28ba65c3c",
          "meta": { "name": "USTB Strategy (USDC)" },
          "strategyType": "Allocation",
          "state": "Active"
        },
        "currentValue": "75000000000000",
        "depositedAssets": "74600000000000",
        "withdrawnAssets": "0",
        "poolManagerCap": "0",
        "strategyCap": "150000000000000",
        "unrealizedLosses": "0"
      },
      {
        "id": "0x083ae322f060777bcf5a2801c5c13a8e3ec54ec1-0x7ad5ffa5fdf509e30186f4609c2f6269f4b6158f",
        "strategyManager": {
          "id": "0x083ae322f060777bcf5a2801c5c13a8e3ec54ec1",
          "meta": { "name": "Aave V3 (USDC)" },
          "strategyType": "Aave",
          "state": "Active"
        },
        "currentValue": "50000000000000",
        "depositedAssets": "49800000000000",
        "withdrawnAssets": "0",
        "poolManagerCap": "0",
        "strategyCap": "100000000000000",
        "unrealizedLosses": "0"
      }
    ]
  }
}
```

**Reading this example:** USDC has 6 decimals, so the Pool's USTB position is worth $75.0M and its Aave V3 position $50.0M, $125.0M in strategies in total. The figures are illustrative.
{% endtab %}
{% endtabs %}

### One strategy's activity and yield

Returns one strategy's latest activity, newest first. `strategyManagerTxes` holds the flows between Pools and the strategy. `strategyTxes` holds the strategy's own operations, including `realizeYield`. The query drops `collectFees` rows with a zero `amount`.

{% tabs %}
{% tab title="Query" %}
```graphql
query StrategyActivity($strategyManager: String!) {
  strategyManagerTxes(
    where: { strategyManager: $strategyManager }
    first: 100
    orderBy: timestamp
    orderDirection: desc
  ) {
    id
    type        # fund, requestRedeem, cancelRedemption or processRedemption
    pool {
      id
      name
    }
    amount      # in `decimals`
    shares
    symbol
    decimals
    value       # USD, 6 decimals
    timestamp   # unix seconds
    transaction {
      id
    }
  }
  strategyTxes(
    where: {
      or: [
        { strategyManager: $strategyManager, type_not: collectFees }
        { strategyManager: $strategyManager, amount_gt: 0 }
      ]
    }
    first: 100
    orderBy: timestamp
    orderDirection: desc
  ) {
    id
    type        # deployAssets, returnAssets, realizeYield, collectFees and others
    amount      # realizeYield: gross of delegateFee and protocolFee
    delegateFee
    protocolFee
    duration    # realizeYield: vesting period in seconds
    symbol
    decimals
    value       # USD, 6 decimals
    timestamp
    transaction {
      id
    }
  }
}
```

Variables:

```json
{ "strategyManager": "0xe8c04874b1332a95ba15961c5e4a13f28ba65c3c" }
```
{% endtab %}

{% tab title="Example response" %}
```json
{
  "data": {
    "strategyManagerTxes": [
      {
        "id": "0x9f1c…-12",
        "type": "fund",
        "pool": {
          "id": "0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b",
          "name": "Syrup USDC"
        },
        "amount": "25000000000000",
        "shares": "24910000000000",
        "symbol": "USDC",
        "decimals": 6,
        "value": "25000000000000",
        "timestamp": "1794182400",
        "transaction": { "id": "0x9f1c…" }
      }
    ],
    "strategyTxes": [
      {
        "id": "0x4b7e…-7",
        "type": "realizeYield",
        "amount": "312500000000",
        "delegateFee": "0",
        "protocolFee": "31250000000",
        "duration": "604800",
        "symbol": "USDC",
        "decimals": 6,
        "value": "312500000000",
        "timestamp": "1794096000",
        "transaction": { "id": "0x4b7e…" }
      }
    ]
  }
}
```

**Reading this example:**

* The `fund` row shows the Pool sending $25.0M (USDC, 6 decimals) into the strategy in exchange for strategy shares.
* The `realizeYield` row reports $312,500 of gross yield. After the $31,250 protocol fee, $281,250 of net yield vests into the strategy's value over 7 days (`duration` of 604800 seconds).

The figures are illustrative.
{% endtab %}
{% endtabs %}

## How yield shows up

* **Allocation strategies** realize yield in steps through `realizeYield` transactions. `amount` is gross of `delegateFee` and `protocolFee`. The net yield vests linearly into the strategy's value until `allocationStrategy.yieldDeadline`. See [Allocation Strategy](../../technical-resources/strategies/allocation-strategy/README.md).
* **Aave V3 and Sky strategies** accrue yield continuously. Measure it from the change in `currentValue` over time. See [Aave V3 Strategy](../../technical-resources/strategies/aave-v3-strategy/README.md) and [Sky Strategy](../../technical-resources/strategies/sky-strategy/README.md).

## Units and parsing

| Field | Units | Example raw value | Parsed value |
| --- | --- | --- | --- |
| `currentValue`, `depositedAssets`, `withdrawnAssets`, caps, `amount` | Pool asset decimals (`fundsAsset.decimals`, or a transaction's `decimals`) | `1000000000` (USDC, 6 decimals) | 1,000 USDC |
| Transaction `value` | USD, 6 decimals | `1000000000` | $1,000 |
| `delegateFeeRate`, `protocolFeeRate` | 6 decimals, `1000000` = 100% | `100000` | 10% |
| `aumTimeSeries` USD fields | USD, 8 decimals | `100000000000` | $1,000 |
| `timestamp`, `yieldDeadline` | Unix seconds | `1794268800` | Tue, 10 Nov 2026 |

## Caveats

* **Strategy AUM sits slightly below onchain AUM.** A strategy's AUM is the sum of `currentValue` over its positions. Each strategy also holds bootstrap shares worth `1e6` base units (1 token) that belong to no Pool. They appear as a `fund` transaction whose `pool` is null.
* **`currentValue` is always live.** It returns the latest value and ignores the `block` argument. For history, use `aumTimeSeries` or store snapshots.
* **Losses show in two places.** Allocation strategy losses show in a position's `unrealizedLosses`. Aave V3 and Sky losses show in the Strategy Manager's `impairedAssets` and `state`, not in `unrealizedLosses`.

## Contracts and source code

* [Strategies](../../technical-resources/strategies/README.md) explains each contract, starting with [How Pools Allocate Capital](../../technical-resources/strategies/how-pools-allocate-capital.md).
* [Contract Addresses](../../technical-resources/protocol-overview/smart-contract-addresses.md) lists the deployed Strategy Manager and strategy contracts.
* [November 2026 Release](../../technical-resources/releases/november-2026-release-deployment-and-upgrade.md) covers the release that introduced shared strategies, and [Audits and Security Practices](../../technical-resources/security/security.md) lists its audits.
* The full schema is in the [Maple GraphQL API](https://studio.apollographql.com/public/maple-api/home?variant=mainnet) reference, which also has these queries saved in its "Modular Strategies" collection.

## Getting help

Email [partnerships@maple.finance](mailto:partnerships@maple.finance) with questions, or to request data the API does not expose yet.
