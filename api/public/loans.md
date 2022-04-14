# Loans

Maple protocol loan data.

### Loans by Pool Address

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  allLoans(poolContractAddress: "0xe5D0Ef77AED07C302634dC370537126A2CD26590") {
    limit
    skip
    total
    list {
      id
      version
      requestAmount
      liquidityAsset {
        id
        symbol
        decimals
      }
      collateralAsset {
        id
        symbol
        decimals
      }
      collateralRatio
      collateralRequired
      apr
      interestRate
      termDays
      state
      paymentIntervalDays
      collateralAmount
      amountFunded
      drawdownAmount
      drawdownDate
      fundingDate
      maturityDate
      treasuryFees
      claimableAmount
      principalOwed
      nextPayment
      nextPaymentDue
      paymentsRemaining
      interestPaid
      numLenders
      collateralSwapped
      liquidityAssetReturned
      liquidationExcess
      defaultSuffered
      transaction {
        id
        timestamp
      }
    }
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "allLoans": {
      "limit": 1000,
      "skip": 0,
      "total": 2,
      "list": [
        {
          "id": "0xb3b10d10a7fdb7cd7f406f55f136b54593400f56",
          "version": 200,
          "requestAmount": "2500000000000",
          "liquidityAsset": {
            "id": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "symbol": "USDC",
            "decimals": 6
          },
          "collateralAsset": {
            "id": "0x2260fac5e5542a773aa44fbcfedf7c193bc2c599",
            "symbol": "WBTC",
            "decimals": 8
          },
          "collateralRatio": 0,
          "collateralRequired": "0",
          "apr": 1100,
          "interestRate": "110000000000000000",
          "termDays": 90,
          "state": "Unfunded",
          "paymentIntervalDays": 30,
          "collateralAmount": "0",
          "amountFunded": "0",
          "drawdownAmount": "0",
          "drawdownDate": "0",
          "fundingDate": "0",
          "maturityDate": "0",
          "treasuryFees": "0",
          "claimableAmount": "0",
          "principalOwed": "0",
          "nextPayment": "0",
          "nextPaymentDue": "0",
          "paymentsRemaining": "3",
          "interestPaid": "0",
          "numLenders": "0",
          "collateralSwapped": "0",
          "liquidityAssetReturned": "0",
          "liquidationExcess": "0",
          "defaultSuffered": "0",
          "transaction": {
            "id": "0x9fae31e59da4ec187807414b7c0096da1d0ba453b7773f78fef8c30dbea1f165",
            "timestamp": "1649704249"
          }
        },
        {
          "id": "0xd7761d259fd87427202d78392cefc02f14b17f3c",
          "version": 100,
          "requestAmount": "3000000000000",
          "liquidityAsset": {
            "id": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "symbol": "USDC",
            "decimals": 6
          },
          "collateralAsset": {
            "id": "0x2260fac5e5542a773aa44fbcfedf7c193bc2c599",
            "symbol": "WBTC",
            "decimals": 8
          },
          "collateralRatio": 0,
          "collateralRequired": "0",
          "apr": 1075,
          "interestRate": "107500000000000000",
          "termDays": 90,
          "state": "Expired",
          "paymentIntervalDays": 30,
          "collateralAmount": "0",
          "amountFunded": "0",
          "drawdownAmount": "0",
          "drawdownDate": "0",
          "fundingDate": "0",
          "maturityDate": "0",
          "treasuryFees": "0",
          "claimableAmount": "0",
          "principalOwed": "0",
          "nextPayment": "0",
          "nextPaymentDue": "0",
          "paymentsRemaining": "0",
          "interestPaid": "0",
          "numLenders": "0",
          "collateralSwapped": "0",
          "liquidityAssetReturned": "0",
          "liquidationExcess": "0",
          "defaultSuffered": "0",
          "transaction": {
            "id": "0x73a98ffa50670023bb450bacde1ed1ea225e0aa2d0e453965f7ea666fc6f659c",
            "timestamp": "1632401361"
          }
        }
      ]
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

type Transaction {
  id: String
  timestamp: String
}

type Loan {
  id: String
  version: Int
  requestAmount: String
  liquidityAsset: Asset
  collateralAsset: Asset
  collateralRatio: Int
  collateralRequired: String
  apr: Int
  interestRate: String
  termDays: Int
  state: String
  paymentIntervalDays: Int
  collateralAmount: String
  amountFunded: String
  drawdownAmount: String
  drawdownDate: String
  fundingDate: String
  maturityDate: String
  treasuryFees: String
  claimableAmount: String
  principalOwed: String
  nextPayment: String
  nextPaymentDue: String
  paymentsRemaining: String
  interestPaid: String
  numLenders: String
  collateralSwapped: String
  liquidityAssetReturned: String
  liquidationExcess: String
  defaultSuffered: String
  transaction: Transaction
}
```
{% endtab %}
{% endtabs %}

### Loans by Borrower Address

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  loans(ethereumAddress: "0xe5D0Ef77AED07C302634dC370537126A2CD26590") {
    id
    version
    requestAmount
    liquidityAsset {
      id
      symbol
      decimals
    }
    collateralAsset {
      id
      symbol
      decimals
    }
    collateralRatio
    collateralRequired
    apr
    interestRate
    termDays
    state
    paymentIntervalDays
    collateralAmount
    amountFunded
    drawdownAmount
    drawdownDate
    fundingDate
    maturityDate
    treasuryFees
    claimableAmount
    principalOwed
    nextPayment
    nextPaymentDue
    paymentsRemaining
    interestPaid
    numLenders
    collateralSwapped
    liquidityAssetReturned
    liquidationExcess
    defaultSuffered
    transaction {
      id
      timestamp
    }
    fundingPool {
      poolName
    }
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "loans": [
      {
        "id": "0x148aa09731baf7eceaeb1513e2d6c794fa9b23fb",
        "version": 200,
        "requestAmount": "19423790000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 850,
        "interestRate": "85000000000000000",
        "termDays": 90,
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "19423790000000",
        "drawdownAmount": "19376374666055",
        "drawdownDate": "1644142308",
        "fundingDate": "1643626954",
        "maturityDate": "1651402954",
        "treasuryFees": "31610222630",
        "claimableAmount": "0",
        "principalOwed": "19423790000000",
        "nextPayment": "19559490450684",
        "nextPaymentDue": "1651402954",
        "paymentsRemaining": "1",
        "interestPaid": "271400901368",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x170edd80a81bb05a1126b4b533c5ef8795af54b77369d76652059a5c70c85466",
          "timestamp": "1643615475"
        },
        "fundingPool": {
          "poolName": "Alameda Research - USDC"
        }
      },
      {
        "id": "0x1dff8b506943278669fb1480b06b102451bb4be8",
        "version": 200,
        "requestAmount": "77770000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 725,
        "interestRate": "72500000000000000",
        "termDays": 90,
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "77770000000000",
        "drawdownAmount": "77580155972604",
        "drawdownDate": "1647919512",
        "fundingDate": "1647919354",
        "maturityDate": "1655695354",
        "treasuryFees": "126562684931",
        "claimableAmount": "0",
        "principalOwed": "77770000000000",
        "nextPayment": "463423972602",
        "nextPaymentDue": "1650511354",
        "paymentsRemaining": "3",
        "interestPaid": "0",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x90b7cfb72707a8f0f842df919572b9f03f93802aac4fb68b33749d32b9717b3b",
          "timestamp": "1647919219"
        },
        "fundingPool": {
          "poolName": "Alameda Research - USDC"
        }
      },
      {
        "id": "0x2599d9124a2db4eda337a15c3dde53a06a606c2f",
        "version": 200,
        "requestAmount": "47250000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 750,
        "interestRate": "75000000000000000",
        "termDays": 90,
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "47250000000000",
        "drawdownAmount": "47134658219180",
        "drawdownDate": "1645799183",
        "fundingDate": "1645154666",
        "maturityDate": "1652930666",
        "treasuryFees": "76894520547",
        "claimableAmount": "0",
        "principalOwed": "47250000000000",
        "nextPayment": "291267123287",
        "nextPaymentDue": "1650338666",
        "paymentsRemaining": "2",
        "interestPaid": "291267123287",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0xaa77f60294d45f98517347553ed13b55c30c12fdfade86cfa4f7df0011501541",
          "timestamp": "1645147979"
        },
        "fundingPool": {
          "poolName": "Alameda Research - USDC"
        }
      },
      {
        "id": "0x3b8345c3a7d254d24dadfee2b0a9575116e25679",
        "version": 100,
        "requestAmount": "21250000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 850,
        "interestRate": "85000000000000000",
        "termDays": 90,
        "state": "Matured",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "21250000000000",
        "drawdownAmount": "21250000000000",
        "drawdownDate": "1637302881",
        "fundingDate": "1637302707",
        "maturityDate": "1645078881",
        "treasuryFees": "53125000000",
        "claimableAmount": "1",
        "principalOwed": "0",
        "nextPayment": "0",
        "nextPaymentDue": "0",
        "paymentsRemaining": "0",
        "interestPaid": "445376712327",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x8fdd3dcc35f92bb33f54bb952551cdd52b6851e734f521bf46703a3f8a9f472e",
          "timestamp": "1637302682"
        },
        "fundingPool": {
          "poolName": "Alameda Research - USDC"
        }
      },
      {
        "id": "0x5233a1feef2480fa9f8c7eca0d4dc6e59c0d099b",
        "version": 200,
        "requestAmount": "20000000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 750,
        "interestRate": "75000000000000000",
        "termDays": 90,
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "20000000000000",
        "drawdownAmount": "19951178082193",
        "drawdownDate": "1645801250",
        "fundingDate": "1645800417",
        "maturityDate": "1653576417",
        "treasuryFees": "32547945205",
        "claimableAmount": "0",
        "principalOwed": "20000000000000",
        "nextPayment": "123287671232",
        "nextPaymentDue": "1650984417",
        "paymentsRemaining": "2",
        "interestPaid": "123287671232",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0xc1ed49b4ec7437a4bb98703fc26ce5d9d63188524029477a3542fe88deb805d2",
          "timestamp": "1645800200"
        },
        "fundingPool": {
          "poolName": "Maven 11 - USDC 01"
        }
      },
      {
        "id": "0x59d3421c0862af616f92091b55c7938a2437c43b",
        "version": 100,
        "requestAmount": "10100000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 850,
        "interestRate": "85000000000000000",
        "termDays": 90,
        "state": "Matured",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "10100000000000",
        "drawdownAmount": "10100000000000",
        "drawdownDate": "1641188899",
        "fundingDate": "1640273142",
        "maturityDate": "1648964899",
        "treasuryFees": "25250000000",
        "claimableAmount": "1",
        "principalOwed": "0",
        "nextPayment": "0",
        "nextPaymentDue": "0",
        "paymentsRemaining": "0",
        "interestPaid": "211684931505",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x8ab5c1c0cf18adfa3f63576e40f735868f11b3dd369c9f4946db4349857bfb9f",
          "timestamp": "1640257243"
        },
        "fundingPool": {
          "poolName": "Alameda Research - USDC"
        }
      },
      {
        "id": "0x630b503fa7febcf4478933f732ec1cdeaabbf3eb",
        "version": 100,
        "requestAmount": "5800000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 775,
        "interestRate": "77500000000000000",
        "termDays": 180,
        "state": "Matured",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "5800000000000",
        "drawdownAmount": "5800000000000",
        "drawdownDate": "1629025245",
        "fundingDate": "1628921870",
        "maturityDate": "1644577245",
        "treasuryFees": "14500000000",
        "claimableAmount": "1",
        "principalOwed": "0",
        "nextPayment": "0",
        "nextPaymentDue": "0",
        "paymentsRemaining": "0",
        "interestPaid": "223518493147",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0xbde2fb8c823e626c3faaed353f2e2574d925010e3b26ae163eaa9e03c1a80eac",
          "timestamp": "1628921084"
        },
        "fundingPool": {
          "poolName": "Orthogonal Trading - USDC01"
        }
      },
      {
        "id": "0x6d2ca97efa28c302720f5d2d7cf665c51b70ef0f",
        "version": 100,
        "requestAmount": "8000000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 800,
        "interestRate": "80000000000000000",
        "termDays": 90,
        "state": "Matured",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "8000000000000",
        "drawdownAmount": "8000000000000",
        "drawdownDate": "1639130366",
        "fundingDate": "1638869070",
        "maturityDate": "1646906366",
        "treasuryFees": "20000000000",
        "claimableAmount": "1",
        "principalOwed": "0",
        "nextPayment": "0",
        "nextPaymentDue": "0",
        "paymentsRemaining": "0",
        "interestPaid": "157808219178",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x9a9120bc4c4a9cb395b9e75b555d8c0b4f1268d32bf896ba9564a3c521829f51",
          "timestamp": "1638863028"
        },
        "fundingPool": {
          "poolName": "Maven 11 - USDC 01"
        }
      },
      {
        "id": "0x722fe8e1683a412f40e6546b6c4b939417caf9a7",
        "version": 100,
        "requestAmount": "23300000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 850,
        "interestRate": "85000000000000000",
        "termDays": 90,
        "state": "Matured",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "23300000000000",
        "drawdownAmount": "23300000000000",
        "drawdownDate": "1640165336",
        "fundingDate": "1640073870",
        "maturityDate": "1647941336",
        "treasuryFees": "58250000000",
        "claimableAmount": "1",
        "principalOwed": "0",
        "nextPayment": "0",
        "nextPaymentDue": "0",
        "paymentsRemaining": "0",
        "interestPaid": "496481506846",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0xb5951f08c1ff92a1929babaee5de9208d0afbdc0feec7188a4d37c3c9bbb8d36",
          "timestamp": "1640071470"
        },
        "fundingPool": {
          "poolName": "Alameda Research - USDC"
        }
      },
      {
        "id": "0x8467b6cf172a33bb35343651f4dcf3d8ea77404f",
        "version": 100,
        "requestAmount": "5800000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 775,
        "interestRate": "77500000000000000",
        "termDays": 180,
        "state": "Expired",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "0",
        "drawdownAmount": "0",
        "drawdownDate": "0",
        "fundingDate": "0",
        "maturityDate": "0",
        "treasuryFees": "0",
        "claimableAmount": "0",
        "principalOwed": "0",
        "nextPayment": "0",
        "nextPaymentDue": "0",
        "paymentsRemaining": "0",
        "interestPaid": "0",
        "numLenders": "0",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x9f70aefd74da86fbffb700ae7fb5ab967088a39c60097a72f1d95ef9c386a398",
          "timestamp": "1628921084"
        },
        "fundingPool": null
      },
      {
        "id": "0xbd23294f556f74083359c1afa4d352044eeaafd6",
        "version": 200,
        "requestAmount": "10000000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 850,
        "interestRate": "85000000000000000",
        "termDays": 180,
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "10000000000000",
        "drawdownAmount": "9951178082193",
        "drawdownDate": "1644409640",
        "fundingDate": "1644244758",
        "maturityDate": "1659796758",
        "treasuryFees": "32547945205",
        "claimableAmount": "0",
        "principalOwed": "10000000000000",
        "nextPayment": "69863013698",
        "nextPaymentDue": "1652020758",
        "paymentsRemaining": "4",
        "interestPaid": "139726027396",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x6b4926623a09c594457be13f51d422775d42f15cfe0f7ae89e99f391a229061d",
          "timestamp": "1644142512"
        },
        "fundingPool": {
          "poolName": "Orthogonal Trading - USDC01"
        }
      },
      {
        "id": "0xd4f36a5f89c2598589ab4432c2d873a18c9662d6",
        "version": 100,
        "requestAmount": "12000000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 975,
        "interestRate": "97500000000000000",
        "termDays": 180,
        "state": "Repayment Due",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "12000000000000",
        "drawdownAmount": "12000000000000",
        "drawdownDate": "1634690638",
        "fundingDate": "1634637461",
        "maturityDate": "1650242638",
        "treasuryFees": "30000000000",
        "claimableAmount": "1",
        "principalOwed": "12000000000000",
        "nextPayment": "12096164383561",
        "nextPaymentDue": "1650242638",
        "paymentsRemaining": "1",
        "interestPaid": "485630136983",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0x39a94d82243a9524af8771f13ba0fc9a08145bdf590ef2a11654d87309b4898b",
          "timestamp": "1634627937"
        },
        "fundingPool": {
          "poolName": "Maven 11 - USDC 01"
        }
      },
      {
        "id": "0xe8a6a46f8d50d029824dad5e0e7d580def6edf76",
        "version": 100,
        "requestAmount": "2000000000000",
        "liquidityAsset": {
          "symbol": "USDC",
          "decimals": 6
        },
        "collateralAsset": {
          "symbol": "WBTC",
          "decimals": 8
        },
        "collateralRatio": 0,
        "collateralRequired": "0",
        "apr": 1500,
        "interestRate": "150000000000000000",
        "termDays": 90,
        "state": "Matured",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "2000000000000",
        "drawdownAmount": "2000000000000",
        "drawdownDate": "1622088304",
        "fundingDate": "1621988209",
        "maturityDate": "1629864304",
        "treasuryFees": "10000000000",
        "claimableAmount": "1",
        "principalOwed": "0",
        "nextPayment": "0",
        "nextPaymentDue": "0",
        "paymentsRemaining": "0",
        "interestPaid": "73972602738",
        "numLenders": "1",
        "collateralSwapped": "0",
        "liquidityAssetReturned": "0",
        "liquidationExcess": "0",
        "defaultSuffered": "0",
        "transaction": {
          "id": "0xa9c95ddab23f2493163ab45dbdbded49b1209d2692f82a2d46b118da2041dca2",
          "timestamp": "1621947817"
        },
        "fundingPool": {
          "poolName": "Orthogonal Trading - USDC01"
        }
      }
    ]
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

type Transaction {
  id: String
  timestamp: String
}

type Pool {
  poolName: String
}

type Loan {
  id: String
  version: Int
  requestAmount: String
  liquidityAsset: Asset
  collateralAsset: Asset
  collateralRatio: Int
  collateralRequired: String
  apr: Int
  interestRate: String
  termDays: Int
  state: String
  paymentIntervalDays: Int
  collateralAmount: String
  amountFunded: String
  drawdownAmount: String
  drawdownDate: String
  fundingDate: String
  maturityDate: String
  treasuryFees: String
  claimableAmount: String
  principalOwed: String
  nextPayment: String
  nextPaymentDue: String
  paymentsRemaining: String
  interestPaid: String
  numLenders: String
  collateralSwapped: String
  liquidityAssetReturned: String
  liquidationExcess: String
  defaultSuffered: String
  transaction: Transaction
  fundingPool: Pool
}
```
{% endtab %}
{% endtabs %}
