---
description: Query each Pool's liquidity profile from the Maple GraphQL API.
---

# Tracking Liquidity

Each Maple Pool publishes a liquidity profile showing how much of its capital can return to the Pool, and how fast. It works in three parts:

* **Sources.** The Pool's capital, from loans to strategy allocations, grouped into time windows from instant to 30+ days.
* **Interest due.** Interest borrowers owe on active loans in each window, net of management fees, on top of the sources.
* **Withdrawal queue.** Pending withdrawals, and how quickly withdrawals were processed over the last 12 months.

The profile for each Pool is on the Maple transparency page, under **Liquidity**:

* [syrupUSDC](https://maple.finance/transparency/products/syrupusdc)
* [syrupUSDT](https://maple.finance/transparency/products/syrupusdt)
* [syrupUSDG](https://maple.finance/transparency/products/syrupusdg)

The same data is available from the API through the `liquidity` field on a Pool. The transparency page rebuilds from this field every 4 hours, so it can trail the API by a few hours.

## Query

The query runs against the public Maple GraphQL API at `https://api.maple.finance/v2/graphql` and needs no authentication. Addresses sent to the API must be lowercase.

| Pool      | **poolId**                                   |
| --------- | -------------------------------------------- |
| syrupUSDC | `0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b` |
| syrupUSDT | `0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d` |
| syrupUSDG | `0x87b65c4aaffa76881f9e96f3e7ed945ddfc3cd7a` |

{% hint style="info" %}
This query can take up to around 1 minute to respond due to the amount of data. We recommend caching the result and refreshing it periodically.
{% endhint %}

### One Pool's liquidity profile

{% tabs %}
{% tab title="Query" %}
```graphql
query PoolLiquidity($poolId: ID!) {
  poolV2(id: $poolId) {
    id
    totalAssets             # in the Pool asset's decimals
    liquidity {
      sources {
        category            # idleCash, defi, dexLp, usTreasuries, trading or overcollateralizedLending
        name                # e.g. "DeFi" or "Loans · 8-30 days"
        detail              # positions behind the row, e.g. "Aave v3"; for loans, the loan count
        timing              # free-text timing for the row, e.g. "T+1 banking days"; null if none
        window              # instant, 24h, 3d, 7d, 30d or 30d+
        windowOrder         # 1 (instant) to 6 (30d+)
        loanCount           # loans or positions behind the row; null for idle cash
        amount              # in the Pool asset's decimals
        cumulativeAmount    # running total up to and including this row
        pctOfTotalAssets    # fraction of totalAssets, 0 to 1
        cumulativePct       # running total as a fraction of totalAssets
        order               # sort order, fastest first
      }
      interestDue {
        window
        windowOrder
        loanCount
        amount              # net interest due in this window alone
        cumulativeAmount
      }
      withdrawalQueue {
        pendingAmount       # waiting to be processed, in the Pool asset's decimals
        asOf                # unix seconds of the latest block reflected
        total               # withdrawals processed over the trailing 12 months
        medianMinutes       # median time to process a withdrawal
        withinMedian
        within24h           # count of withdrawals processed within 24 hours
        within3d
        within7d
        within14d
        medianPct
        within24hPct        # within24h / total, 0 to 1
        within3dPct
        within7dPct
        within14dPct
      }
    }
  }
}
```

Variables:

```json
{ "poolId": "0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d" }
```
{% endtab %}

{% tab title="Example response" %}
```json
{
  "data": {
    "poolV2": {
      "id": "0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d",
      "totalAssets": "274661274631056",
      "liquidity": {
        "sources": [
          {
            "category": "idleCash",
            "name": "Idle cash",
            "detail": "Pool contract",
            "timing": null,
            "window": "instant",
            "windowOrder": 1,
            "loanCount": null,
            "amount": "822102183837",
            "cumulativeAmount": "822102183837",
            "pctOfTotalAssets": 0.002993149273,
            "cumulativePct": 0.002993149273,
            "order": 1
          },
          {
            "category": "defi",
            "name": "DeFi",
            "detail": "Aave v3",
            "timing": null,
            "window": "instant",
            "windowOrder": 1,
            "loanCount": 1,
            "amount": "24321019200087",
            "cumulativeAmount": "25143121383924",
            "pctOfTotalAssets": 0.08854913948,
            "cumulativePct": 0.09154228875,
            "order": 2
          },
          {
            "category": "dexLp",
            "name": "DEX LP",
            "detail": "Uniswap",
            "timing": null,
            "window": "instant",
            "windowOrder": 1,
            "loanCount": 5,
            "amount": "6956010232944",
            "cumulativeAmount": "32099131616868",
            "pctOfTotalAssets": 0.02532577748,
            "cumulativePct": 0.1168680662,
            "order": 3
          },
          {
            "category": "overcollateralizedLending",
            "name": "Loans · 0-1 days",
            "detail": "2 loans",
            "timing": null,
            "window": "24h",
            "windowOrder": 2,
            "loanCount": 2,
            "amount": "65056210811711",
            "cumulativeAmount": "97155342428579",
            "pctOfTotalAssets": 0.2368597894,
            "cumulativePct": 0.3537278556,
            "order": 4
          },
          {
            "category": "usTreasuries",
            "name": "US Treasuries",
            "detail": "PYUSD, USDtb",
            "timing": "T+1 banking days",
            "window": "3d",
            "windowOrder": 3,
            "loanCount": 2,
            "amount": "20217478599364",
            "cumulativeAmount": "117372821027943",
            "pctOfTotalAssets": 0.07360877099,
            "cumulativePct": 0.4273366266,
            "order": 5
          }
        ],
        "interestDue": [
          {
            "window": "24h",
            "windowOrder": 2,
            "loanCount": 8,
            "amount": "62345586994",
            "cumulativeAmount": "62345586994"
          },
          {
            "window": "3d",
            "windowOrder": 3,
            "loanCount": 2,
            "amount": "23811766322",
            "cumulativeAmount": "86157353317"
          }
        ],
        "withdrawalQueue": {
          "pendingAmount": "0",
          "asOf": 1794226223,
          "total": 5560,
          "medianMinutes": 3.8,
          "withinMedian": 2780,
          "within24h": 5297,
          "within3d": 5522,
          "within7d": 5560,
          "within14d": 5560,
          "medianPct": 0.5,
          "within24hPct": 0.952698,
          "within3dPct": 0.993165,
          "within7dPct": 1,
          "within14dPct": 1
        }
      }
    }
  }
}
```

The response is shortened to the first five sources and the first two interest windows. Values in a live response will differ.

**Reading this example:** syrupUSDT holds 274.66M USDT (6 decimals).

* **Instant:** $32.10M, 11.7% of deposits, from idle cash, Aave v3 and Uniswap.
* **Within 24 hours:** $97.16M, 35.4%, adding two loans due to be called or mature within a day.
* **Within 3 days:** $117.37M, 42.7%, adding US Treasuries, which settle T+1 banking days.
* **Interest due:** borrowers owe $62.3K within 24 hours and $86.2K within 3 days on top of these amounts.
* **Withdrawal queue:** nothing is pending. Over the last 12 months, 5,297 of 5,560 withdrawals (95.3%) were processed within 24 hours, with a median of 3.8 minutes.
{% endtab %}
{% endtabs %}

### All syrup Pools in one request

Replace `poolV2(id: $poolId)` with `poolV2S` and filter on the Pool addresses. The selection set stays the same.

```graphql
query SyrupLiquidity {
  poolV2S(
    where: {
      id_in: [
        "0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b"
        "0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d"
        "0x87b65c4aaffa76881f9e96f3e7ed945ddfc3cd7a"
      ]
    }
  ) {
    id
    totalAssets
    liquidity {
      # same fields as above
    }
  }
}
```

## Reading the response

* **Sources** come sorted by `order`, fastest first. Each row's `cumulativeAmount` is its own `amount` plus the amounts of every row before it, and `cumulativePct` is that total as a share of `totalAssets`. The last row in a window gives the total available within that window. In the example, the last `24h` row has a `cumulativeAmount` of $97.16M, everything available within 24 hours.
* **Windows** match the bars on the transparency page:

| `window`  | `windowOrder` | Label on the transparency page |
| --------- | ------------- | ------------------------------ |
| `instant` | 1             | Instant                        |
| `24h`     | 2             | <24 hours                      |
| `3d`      | 3             | <3 days                        |
| `7d`      | 4             | <7 days                        |
| `30d`     | 5             | <30 days                       |
| `30d+`    | 6             | 30+ days                       |

* **Loans** are grouped by days to their next call or maturity, such as `Loans · 8-30 days`.
* **Row amounts** include accrued interest. Each `amount` is principal plus a share of the Pool's accrued interest, so the rows sum to `totalAssets` within a few units of rounding.
* **Interest due** is paid on top of deposits, so it adds to the amounts in `sources`. It is net of management fees and runs until each loan's principal returns, on the date its source row uses. It excludes late interest and loans under $1,000 of principal.
* **Amounts** are strings in the Pool asset's decimals: 6 for USDC, USDT and USDG. Percentages are fractions from 0 to 1.

## Getting help

Email [partnerships@maple.finance](mailto:partnerships@maple.finance) with questions.
