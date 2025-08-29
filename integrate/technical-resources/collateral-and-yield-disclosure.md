# Collateral & Yield Disclosure

All the data shown in the [Maple Open Access Details](https://app.maple.finance/earn/details) Page is available via API.

## Get Details Data Programmatically&#x20;

Query the [Maple GraphQL API](https://api.maple.finance/v2/graphql) for a detailed breakdown of AUM, APY, loans and collateral:

```graphql
{
  syrupGlobals {
    collateralRatio
    collateralValue
    loansValue
    # WEEK | MONTH | YEAR
    aumTimeSeries(range: WEEK) {
      timestamp
      assetsUsd
      assetsInStrategiesUsd
      loansUsd
      collateralUsd
    }
    # WEEK | MONTH | YEAR
    apyTimeSeries(range: YEAR) {
      timestamp
      apy
      boostApy
      coreApy
      usdBenchmarkApy
    }
  }
}
```

## Calculations

`AUM` = `loansUsd` + `assetsUsd` + `assetsInStrategiesUsd` + `collateralUsd`&#x20;

`collateralRatio` = `collateralValue` ÷ `loansValue`

`apy` = `coreApy` + `boostApy`&#x20;

## API Fields & Calculations

<table><thead><tr><th width="199.6531982421875">AUM Time Series Field</th><th width="189.533935546875">Example raw value</th><th width="169.8284912109375">Parsing</th><th>Parsed value</th></tr></thead><tbody><tr><td><code>timestamp</code></td><td><code>1753142400</code></td><td><code>timestamp * 1000</code></td><td>Tue, 22 Jul 2025</td></tr><tr><td><code>assetsUsd</code></td><td><code>25244993430500</code></td><td>8 decimals</td><td>$252,449</td></tr><tr><td><code>assetsInStrategiesUsd</code></td><td><code>179322260822400</code></td><td>8 decimals</td><td>$1.8M</td></tr><tr><td><code>loansUsd</code></td><td><code>84946501100000000</code></td><td>8 decimals</td><td>$849.5M</td></tr><tr><td><code>collateralUsd</code></td><td><code>141683063371031490</code></td><td>8 decimals</td><td>$1.4B</td></tr></tbody></table>

<table><thead><tr><th width="199.68927001953125">APY Time Series Field</th><th width="190.0164794921875">Example raw value</th><th width="170.471435546875">Parsing</th><th>Parsed value</th></tr></thead><tbody><tr><td><code>timestamp</code></td><td><code>1753142400</code></td><td><code>timestamp * 1000</code></td><td>Tue, 22 Jul 2025</td></tr><tr><td><code>apy</code></td><td><code>249098664347445580210603714885</code></td><td>30 decimals</td><td>24.9%</td></tr><tr><td><code>boostApy</code></td><td><code>135000000000000000000000000000</code></td><td>30 decimals</td><td>13.5%</td></tr><tr><td><code>coreApy</code></td><td><code>114098664347445580210603714885</code></td><td>30 decimals</td><td>11.4%</td></tr><tr><td><code>usdBenchmarkApy</code></td><td><code>103200000000000000000000000000</code></td><td>30 decimals</td><td>10.3%</td></tr></tbody></table>

<table><thead><tr><th width="199.68841552734375">Root Field (Collat. ratio)</th><th width="190.1441650390625">Example raw value</th><th width="170.033447265625">Parsing</th><th>Parsed value</th></tr></thead><tbody><tr><td><code>collateralRatio</code></td><td><code>147387147</code></td><td>8 decimals</td><td>147.4%</td></tr><tr><td><code>collateralValue</code></td><td><code>1332876094058522</code></td><td>6 decimals</td><td>$1.3B</td></tr><tr><td><code>loansValue</code></td><td><code>904336721000000</code></td><td>6 decimals</td><td>$904.3M</td></tr></tbody></table>
