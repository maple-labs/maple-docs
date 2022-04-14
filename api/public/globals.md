# Globals

Maple protocol global data.

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  mapleGlobals {
    governor
    totalLiquidity
    totalLiquidityCap
    totalLiquidityProvided
    totalLoanOriginations
    totalInterestEarned
    totalTreasuryFees
    totalCurrentLoaned
    aggregateLpApy
    totalPools
    totalFinalizedPools
    totalLoans
    totalActiveLoans
    totalValueLocked
    mpl {
      address
      symbol
      decimals
      price
    }
    liquidityAssets {
      address
      symbol
      decimals
    }
    collateralAssets {
      address
      symbol
      decimals
    }
    stakeAssets {
      address
      symbol
      decimals
      price
    }
    defaultGracePeriod
    swapOutRequired
    fundingPeriod
    investorFee
    treasuryFee
    maxSwapSlippage
    minLoanEquity
    lpCooldownPeriod
    lpWithdrawWindow
    stakerUnstakeWindow
    stakerCooldownPeriod
  } 
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "mapleGlobals": {
      "governor": "0x9686328198e51479c6aa5eb87f20b09dbd1bca25",
      "totalLiquidity": 86319875.08541064,
      "totalLiquidityCap": "1118166285405588",
      "totalLiquidityProvided": "898382573876898",
      "totalLoanOriginations": "1193312656188287",
      "totalInterestEarned": "19699729009854",
      "totalTreasuryFees": "3185068631046",
      "totalCurrentLoaned": "819062456188289",
      "aggregateLpApy": "798",
      "totalPools": 6,
      "totalFinalizedPools": 6,
      "totalLoans": 164,
      "totalActiveLoans": 79,
      "totalValueLocked": 94460036.49813797,
      "mpl": {
        "address": "0x33349b282065b0284d756f0577fb39c158f935e6",
        "symbol": "MPL",
        "decimals": 18,
        "price": 59480873
      },
      "liquidityAssets": [
        {
          "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
          "symbol": "USDC",
          "decimals": 6
        },
        {
          "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
          "symbol": "WETH",
          "decimals": 18
        }
      ],
      "collateralAssets": [
        {
          "address": "0x2260fac5e5542a773aa44fbcfedf7c193bc2c599",
          "symbol": "WBTC",
          "decimals": 8
        },
        {
          "address": "0x514910771af9ca656af840dff83e8264ecf986ca",
          "symbol": "LINK",
          "decimals": 18
        },
        {
          "address": "0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9",
          "symbol": "AAVE",
          "decimals": 18
        },
        {
          "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
          "symbol": "USDC",
          "decimals": 6
        },
        {
          "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
          "symbol": "WETH",
          "decimals": 18
        }
      ],
      "stakeAssets": [
        {
          "address": "0x30b705bfa64be9ae395bd9238efc63e9f5f8d1cc",
          "symbol": "BPT",
          "decimals": 18,
          "price": 3400302
        },
        {
          "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
          "symbol": "BPT",
          "decimals": 18,
          "price": 22636277863
        }
      ],
      "defaultGracePeriod": 432000,
      "swapOutRequired": 10000,
      "fundingPeriod": 864000,
      "investorFee": 33,
      "treasuryFee": 66,
      "maxSwapSlippage": 1000,
      "minLoanEquity": 2000,
      "lpCooldownPeriod": 864000,
      "lpWithdrawWindow": 172800,
      "stakerUnstakeWindow": 172800,
      "stakerCooldownPeriod": 864000
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Asset {
  id: String
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type MapleGlobals {
  governor: String
  totalLiquidity: Float
  totalLiquidityCap: String
  totalLiquidityProvided: String
  totalLoanOriginations: String
  totalInterestEarned: String
  totalTreasuryFees: String
  totalCurrentLoaned: String
  aggregateLpApy: String
  totalPools: Float
  totalFinalizedPools: Float
  totalLoans: Float
  totalActiveLoans: Float
  totalValueLocked: Float
  mpl: Asset
  liquidityAssets: [Asset]
  collateralAssets: [Asset]
  stakeAssets: [Asset]
  defaultGracePeriod: Float
  swapOutRequired: Float
  fundingPeriod: Float
  investorFee: Float
  treasuryFee: Float
  maxSwapSlippage: Float
  minLoanEquity: Float
  lpCooldownPeriod: Float
  lpWithdrawWindow: Float
  stakerUnstakeWindow: Float
  stakerCooldownPeriod: Float
}
```
{% endtab %}
{% endtabs %}

