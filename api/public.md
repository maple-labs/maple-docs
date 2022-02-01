---
description: Public GraphQL resolvers for Maple Finance Protocol
---

# Public

The public GraphQL endpoint is [https://api.maple.finance/public](https://api.maple.finance/public)**.** No authentication headers are required.

### Maple Globals

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
      "totalLiquidity": 51395803.821317,
      "totalLiquidityCap": "630000000000000",
      "totalLiquidityProvided": "522963393430734",
      "totalLoanOriginations": "567750200000000",
      "totalInterestEarned": "9663054922043",
      "totalTreasuryFees": "1540411249998",
      "totalCurrentLoaned": "476000000000002",
      "aggregateLpApy": "939",
      "totalPools": 4,
      "totalFinalizedPools": 4,
      "totalLoans": 105,
      "totalActiveLoans": 60,
      "totalValueLocked": 57527149.74717876,
      "mpl": {
        "address": "0x33349b282065b0284d756f0577fb39c158f935e6",
        "symbol": "MPL",
        "decimals": 18,
        "price": 14530707
      },
      "liquidityAssets": [
        {
          "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
          "symbol": "USDC",
          "decimals": 6
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
        }
      ],
      "stakeAssets": [
        {
          "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
          "symbol": "BPT",
          "decimals": 18,
          "price": 10976791072
        }
      ],
      "defaultGracePeriod": 432000,
      "swapOutRequired": 100000,
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

### All Pools <a href="#maple-globals" id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  allPools {
    list {
      _id
      poolDelegate {
        _id
        owner
        name
        website
        telegram
        twitter
        linkedIn
        companyName
        aboutBusiness
        allowList
        createdAt
        updatedAt
      }
      poolName
      contractAddress
      strategy
      createdAt
      updatedAt
      state
      liquidityAsset {
        address
        symbol
        decimals
      }
      liquidityLocker
      stakeLocker
      liquidityCap
      stakeAsset {
        address
        symbol
        decimals
      }
      stakingFee
      delegateFee
      ongoingFee
      name
      numActiveLoans
      allowedLPs
      allowedSLs
      lpApy
      lendingApy
      stakingApy
      farmingApy
      stakeRewardsApy
      balance
      liquidity
      lockupPeriod
      stake
      currentLoaned
      totalLoanOriginations
      totalInterestEarned
      totalFees
      stakeLockerFees
      poolDelegateFees
      numPositions
      txCount
      transactionHash
      defaultsTotal
      liquidityAssetRecoveredTotal
      poolTokenTotalSupply
      totalLoaned
      totalPrincipalRepaid
      symbol
      transaction {
        id
        timestamp
      }
      mplRewards {
        id
        periodFinish
        reward
        rewardRate
        rewardsDuration
        paused
      }
      totalPoolTokensStaked
      stakeRewards {
        id
        periodFinish
        reward
        rewardRate
        rewardsDuration
        paused
      }
      totalStakeLockerTokensStaked
      stakeLockerLiquidity
      stakeLockupPeriod
      openToPublic
      stakeLockerOpenToPublic
    }
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "allPools": {
      "list": [
        {
          "_id": "60a48265ec0b150011480d2a",
          "poolDelegate": {
            "_id": "60a481fdec0b150011480d28",
            "owner": "0xA6cCb9483E3E7a737E3a4F5B72a1Ce51838ba122",
            "name": "Josh Green",
            "website": "https://orthogonal.trading/",
            "telegram": "",
            "twitter": "@OrthoTrading",
            "linkedIn": "",
            "companyName": "Orthogonal Trading",
            "aboutBusiness": "Orthogonal Trading exploits inefficiencies in the nascent digital asset markets by marrying a consistent positive carry arbitrage trading backbone with fat tail capture via intelligent systematic trend following and alpha-generative options strategies.",
            "allowList": true,
            "createdAt": "2021-05-19T03:11:57.680Z",
            "updatedAt": "2021-05-19T03:11:57.680Z"
          },
          "poolName": "Orthogonal Trading - USDC01",
          "contractAddress": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27",
          "strategy": "The strategy of this Pool will be to target industry-leading funds and prop trading desks. The focus will be on mitigating risk by lending to market makers and arbitrage traders to avoid taking directional risk on the prices of crypto assets. Borrowers' creditworthiness is assessed based on how they manage leverage, liquidity risk, operational risk controls, management's level of experience, their balance sheet strength and recent financial performance. Loans in the pool will generally vary between 0 and 50% collateralization and target a weighted average APY of low-to-mid teens in line with the market for stablecoin lending.",
          "createdAt": "2021-05-19T03:13:41.035Z",
          "updatedAt": "2021-12-02T16:15:33.786Z",
          "state": "Finalized",
          "liquidityAsset": {
            "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "symbol": "USDC",
            "decimals": 6
          },
          "liquidityLocker": "0xb5321058e209e0f6c1216a7c7922b6962681dd77",
          "stakeLocker": "0x12b2bbbfab2ce6789df5659e9ac27a4a91c96c5c",
          "liquidityCap": "275000000000000",
          "stakeAsset": {
            "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "1000",
          "delegateFee": "1000",
          "ongoingFee": "2000",
          "name": "Maple Pool Token",
          "numActiveLoans": "26",
          "allowedLPs": [
            "0x56221aaf897207f628cfb4cd6c1231d59de17f39",
            "0x009fdde3e654cb2495135708dc1590daefb14ea7",
            "0xc3c14f31c8db2417d1695fa6c8bebe8f2804677e",
            "0xbea07b01e8fe3936a3d206158521a87addb65cfe",
            "0xc32d7f8b71b6f79c9c2d0df200fc76fd6028d215",
            "0x79d93cbf3583e62dd3edbddd1ee1121f8b07af81",
            "0x0dbbfa0960f1c54e6039350ba2e3bf014746bdd2",
            "0x0dc874fb5260bd8749e6e98fd95d161b7605774d",
            "0x6912a141ad1566f5da7515f522bb756a5a9e85e9",
            "0xbf25f6f448f3715323c90c3e584c19d03775deb1",
            "0xf9fe05ea33742fa32cafb347920b7d53277a73dd",
            "0x7aec08ef2c0500b68df3a55a7727813ef79aeb13"
          ],
          "allowedSLs": [
            "0x04eb07c283cd6d9bf237118e2732d8b6ee5ee457",
            "0xf097c7f3b2203692427e4545b79613bd3cff66ce"
          ],
          "lpApy": "974",
          "lendingApy": "733",
          "stakingApy": "2748",
          "farmingApy": "794",
          "stakeRewardsApy": "807",
          "balance": "230123185332596",
          "liquidity": "16623185332596",
          "lockupPeriod": "7776000",
          "stake": "790583571115484189426",
          "currentLoaned": "213500000000000",
          "totalLoanOriginations": "251500200000000",
          "totalInterestEarned": "4656427627476",
          "totalFees": "701746866395",
          "stakeLockerFees": "582053453348",
          "poolDelegateFees": "1274553703306",
          "numPositions": "329",
          "txCount": "1967",
          "transactionHash": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "227892542245122000000000000",
          "totalLoaned": "251500200000000",
          "totalPrincipalRepaid": "38000200000000",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
            "timestamp": "1621394109"
          },
          "mplRewards": {
            "id": "0x7869d7a3b074b5fa484dc04798e254c9c06a5e90",
            "periodFinish": "1645799808",
            "reward": "100739000000000000000000",
            "rewardRate": "38865354938271604",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalPoolTokensStaked": "224199171478304000000000000",
          "stakeRewards": {
            "id": "0xf9d4d5a018d91e9bccc1e35ea78fcfecf4c5cbca",
            "periodFinish": "1644041537",
            "reward": "3840000000000000000000",
            "rewardRate": "1481481481481481",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "765758099037618034192",
          "stakeLockerLiquidity": "431455068116",
          "stakeLockupPeriod": "15552000",
          "openToPublic": true,
          "stakeLockerOpenToPublic": true
        },
        {
          "_id": "60e3e70cd993f30012ceae40",
          "poolDelegate": {
            "_id": "60e3e658d993f30012ceae3d",
            "owner": "0x8B4aa04E9642b387293cE6fFfA42715a9cd19f3C",
            "name": "Balder Bomans",
            "website": "https://www.maven11.com/",
            "telegram": null,
            "twitter": "@maven11capital",
            "linkedIn": "https://www.linkedin.com/company/maven11",
            "companyName": "Maven 11 Capital",
            "aboutBusiness": "Maven 11 is an Amsterdam-founded blockchain and crypto asset investment firm that invests in and supports its ventures globally. As a Pool Delegate, we are committed to a rigorous assessment of the creditworthiness of the borrowers to protect not only the financial interest of the lenders into our pool but also our own brand and reputation as well as that of the Maple protocol as a whole. What is more, by providing a substantial part of the pool cover we are financially aligned with the liquidity providers as well.  To ensure we achieve this high standard of risk management combined with yield optimization and sound portfolio management, we have put in place an experienced team of seasoned professionals from premier European financial institutions with various backgrounds in areas such as leveraged finance, securities trading and audit.",
            "allowList": true,
            "createdAt": "2021-07-06T05:12:56.335Z",
            "updatedAt": "2021-07-06T05:12:56.335Z"
          },
          "poolName": "Maven 11 - USDC 01",
          "contractAddress": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4",
          "strategy": "The strategy of this pool will be to target borrowers with capital intensive businesses supported by a strong balance sheet. The Pool Delegate will methodically build the credit history of the borrowers by starting with smaller loans. These will grow in size as PD becomes more comfortable with the counter parties. Creditworthiness is assessed based on balance sheet, recent profitability, leverage, liquidity risk, internal (risk) control systems, strength and track record of the team, among other things. The pool is USDC denominated. Collateralization ratios can vary between 0 - 100%.",
          "createdAt": "2021-07-06T05:15:56.092Z",
          "updatedAt": "2021-12-20T16:14:27.987Z",
          "state": "Finalized",
          "liquidityAsset": {
            "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "symbol": "USDC",
            "decimals": 6
          },
          "liquidityLocker": "0xaaf126daea17f689d4f1753fccb559f0bbacc49e",
          "stakeLocker": "0xbb7866435b8e5d3f6c2ea8b720c8f79db6f7c1b4",
          "liquidityCap": "200000000000000",
          "stakeAsset": {
            "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "1000",
          "delegateFee": "1000",
          "ongoingFee": "2000",
          "name": "Maple Pool Token",
          "numActiveLoans": "28",
          "allowedLPs": [
            "0xed514f9de8c06e6d1f0883a21ddcfc8f4c8d3bae",
            "0x7e2e80e8250844dd4e558f13850380d5af8f0c61",
            "0x009fdde3e654cb2495135708dc1590daefb14ea7",
            "0x2079c29be9c8095042edb95f293b5b510203d6ce",
            "0xb079f40dd951d842f688275100524c09bef9b4e2",
            "0x8ffa85a0c59cf23967eb31c060b2ca3a920276e1",
            "0x343b4f05481d70e4fc1f2be9218b1eb2f755d200",
            "0x8b4aa04e9642b387293ce6fffa42715a9cd19f3c",
            "0xc31dc3bb5bce3284a15019e8b8aeb212a091284b",
            "0xd7f87ccc655f4d771bf518345036a30fd5388366",
            "0xa7c394611a3602468ee76533693fd5405b9938d1",
            "0x8e70ca936a2f2d81cbbf1dc84aabe4213c87b8e9",
            "0xbb17f3baa12194c31f9bfbc245a669cf445bb721",
            "0xad91bae71e4569ec5ff09be170e223cc6b388ab0",
            "0x9f10c27488119744fd355d4ff6894f23f57a5222",
            "0xac727f8bae7d66a5376085768562c30edbd2a1d2",
            "0x5d7de07fd214f0ad436e808b0ffe338fca02043f",
            "0xbdca5ccb951cbace4acb7d92713e2a2d3432ac49",
            "0x439b5e3b9af606327558add370197d3a7c492d7b",
            "0xa99f8656271bd54871639d7b1d20912263cc68e0",
            "0xd711f7e1adcea92bbf0b374c229122a9b6d611b6",
            "0x1a0cb1da3ac95edabdc8e7625b241df2cd9fad1b",
            "0x2adbc63f1a72d33b8050521eca1b57d335bd9dbc",
            "0xcb218f2638185d13758592f87a0a9732a83f29f5",
            "0x1527dfc52df14067a7c5335fd848773a7e1f611a",
            "0x79a226433d0bdf56adb1389db8777f57567c7917",
            "0x2a5d4f800464007ce4a31cbc1e670e70b51810f1",
            "0x9dca7ce5ae2eb59e3896f0baf6b6424324a12022",
            "0x02ffb9b4bbc29f9a59b20c541d369c5add62a5a3",
            "0x3f60a58dbaafc585bbcd2ab7b3b20e1fa3ff4d93",
            "0xd7ec9acbf5ffbf21ccfb5c1a3d98f12fbc09fd06",
            "0x36aa7d15a2c4ceb8357aeec2cf628f1d8af7ac1a",
            "0x0111ac186c2c555fb6e61805bbaa286f680a04ff",
            "0x81ae5e24ac6b220751851b6626ea5dc1cc9d51b1",
            "0x354d6f97482c3e533bbdd3adf65570b3d172c9ad",
            "0x12f813fc88d9c27777971bcc8ac3c8334851b312",
            "0x67123c503ebd779d3a61dce56c07a7be89c993f8",
            "0x4af25d499ea9b3d064e1940258e9aac272ca8d74",
            "0x3f363da363efd11925adb2460063ece532587cbf"
          ],
          "allowedSLs": [],
          "lpApy": "970",
          "lendingApy": "702",
          "stakingApy": "2198",
          "farmingApy": "839",
          "stakeRewardsApy": "713",
          "balance": "176776480167272",
          "liquidity": "18926480167270",
          "lockupPeriod": "7776000",
          "stake": "643097421660365292562",
          "currentLoaned": "157850000000002",
          "totalLoanOriginations": "186600000000000",
          "totalInterestEarned": "3578202739772",
          "totalFees": "514539383524",
          "stakeLockerFees": "447275342407",
          "poolDelegateFees": "955650342370",
          "numPositions": "303",
          "txCount": "1742",
          "transactionHash": "0x8c80af8e064aab3fd9b8c94502afca11bbb5d75a73482cac5015ce0cfaf34786",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "174973363326888000000000000",
          "totalLoaned": "194600000000000",
          "totalPrincipalRepaid": "36749999999998",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x8c80af8e064aab3fd9b8c94502afca11bbb5d75a73482cac5015ce0cfaf34786",
            "timestamp": "1625548646"
          },
          "mplRewards": {
            "id": "0x7c57bf654bc16b0c9080f4f75ff62876f50b8259",
            "periodFinish": "1644185390",
            "reward": "79389000000000000000000",
            "rewardRate": "30628472222222222",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalPoolTokensStaked": "167263499913577999999850000",
          "stakeRewards": {
            "id": "0xe5a1cb65e7a608e778b3ccb02f7b2dfefee783b4",
            "periodFinish": "1644042099",
            "reward": "2820000000000000000000",
            "rewardRate": "1087962962962962",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "636457438503423854788",
          "stakeLockerLiquidity": "274321583520",
          "stakeLockupPeriod": "15552000",
          "openToPublic": true,
          "stakeLockerOpenToPublic": true
        },
        {
          "_id": "619247f7b09e5f0012477078",
          "poolDelegate": {
            "_id": "6191f146e45efcbe0a5f05b8",
            "owner": "0x7f3d405784e14726B3671338E0A65c65bC3fbDB1",
            "name": "Josh Green",
            "website": "https://orthogonal.trading/",
            "telegram": null,
            "twitter": "@OrthoTrading",
            "linkedIn": "https://www.linkedin.com/company/tobedetermined/",
            "companyName": "Orthogonal Trading",
            "aboutBusiness": "Orthogonal Trading exploits inefficiencies in the nascent digital asset markets by marrying a consistent positive carry arbitrage trading backbone with fat tail capture via intelligent systematic trend following and alpha-generative options strategies.",
            "allowList": true,
            "createdAt": "2021-07-06T05:12:56.335Z",
            "updatedAt": "2021-07-06T05:12:56.335Z"
          },
          "poolName": "Alameda Research - USDC",
          "contractAddress": "0x3e701d29fcb8747b5c3f88649397d88fff9bd3e9",
          "strategy": "THIS IS A PERMISSIONED POOL AND ONLY AVAILABLE FOR LENDERS THAT ARE WHITELISTED AFTER GOING THROUGH KYC/AML PROCEDURES. Alameda Research will be the sole borrower from this pool and will utilize all lending capital deposited into this pool to facilitate their market making business.",
          "createdAt": "2021-11-15T11:43:51.366Z",
          "updatedAt": "2021-12-15T18:05:27.794Z",
          "state": "Finalized",
          "liquidityAsset": {
            "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "symbol": "USDC",
            "decimals": 6
          },
          "liquidityLocker": "0x7c5a4b9108be6771161175c512344b3060327a9f",
          "stakeLocker": "0xbcaaca59abb59e331bc8e787e8134c9491a30766",
          "liquidityCap": "80000000000000",
          "stakeAsset": {
            "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "500",
          "delegateFee": "0",
          "ongoingFee": "500",
          "name": "Maple Pool Token",
          "numActiveLoans": "3",
          "allowedLPs": [
            "0xc32d7f8b71b6f79c9c2d0df200fc76fd6028d215",
            "0x2604d6955bd53475923c7f6a6b59e9427403fa6a",
            "0xa23f54e0bb57a6114d831c080823f5fe2616cf98",
            "0x0bf5ee128d559eef716172a2e535a700129d278f",
            "0x646f5f8ebc29b815d884fda60198eb6c652638e7",
            "0xd9952dc091e7cf5ec199c431c69cec8573710333",
            "0xe56466c4171ed8d2e725bc43cdc3c8b738106209",
            "0x219fd48e2ef72b8b55c2e3fe78614b350c06d6eb",
            "0x58088fa541aeb8051bd2a264201fdb6b14a106dc",
            "0xf8c7f2b098a1dfc4ae9268b46c8cff2ae41e445d",
            "0x186cf5714316f47bc59e30a850615a3f938d7d79",
            "0x009fdde3e654cb2495135708dc1590daefb14ea7",
            "0xa995910658808c859623c0fe2ff53e432a236739",
            "0x86cfdc4b540cd8b0edfcbaf5443c8def4c46945f",
            "0x9db09e422abac4bbd4013347d8d0383d9882a5c6",
            "0xa2271075900a5978fbf66c8cb14a35b68fc0deed",
            "0x652fc5b8686417bbf49f3efab8cabe0cb6b1ce05",
            "0xc39f2f40533abe3da450a57af025f24f1679d63a",
            "0xd275e5cb559d6dc236a5f8002a5f0b4c8e610701",
            "0x82886ad5e67d5142d44ed1449c2e41b988bfc0ab",
            "0x59f716e5e0deeb66832ab2cdc45dd33e361f89dd",
            "0xa6a005bb2e3a65d47bd0246654cbba1f6a2fc3a4",
            "0x4b9fb94731e733f4293a4d45c3314e955dfa185d"
          ],
          "allowedSLs": [
            "0x7f3d405784e14726b3671338e0a65c65bc3fbdb1"
          ],
          "lpApy": "850",
          "lendingApy": "625",
          "stakingApy": "27529",
          "farmingApy": "883",
          "stakeRewardsApy": "0",
          "balance": "70496138321450",
          "liquidity": "15846138321450",
          "lockupPeriod": "7776000",
          "stake": "8313000000000000000",
          "currentLoaned": "54650000000000",
          "totalLoanOriginations": "54650000000000",
          "totalInterestEarned": "511479349314",
          "totalFees": "136624999997",
          "stakeLockerFees": "26919965751",
          "poolDelegateFees": "136624999997",
          "numPositions": "18",
          "txCount": "68",
          "transactionHash": "0x7a0d9fb6704736db4a5c9afe364cdb830f3552d1ed78804474a441cf015f712f",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "70097487858724000000000000",
          "totalLoaned": "54650000000000",
          "totalPrincipalRepaid": "0",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x7a0d9fb6704736db4a5c9afe364cdb830f3552d1ed78804474a441cf015f712f",
            "timestamp": "1636976738"
          },
          "mplRewards": {
            "id": "0x5e804b9a61b3e5bf2718ea249deb13366129b7de",
            "periodFinish": "1645797458",
            "reward": "34489000000000000000000",
            "rewardRate": "13305941358024691",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalPoolTokensStaked": "68997487858724000000000000",
          "stakeRewards": {
            "id": "0x0000000000000000000000000000000000000000",
            "periodFinish": "0",
            "reward": "0",
            "rewardRate": "0",
            "rewardsDuration": "0",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "0",
          "stakeLockerLiquidity": "26919965751",
          "stakeLockupPeriod": "15552000",
          "openToPublic": false,
          "stakeLockerOpenToPublic": false
        },
        {
          "_id": "617aa85fb09e5f0012df4a8b",
          "poolDelegate": {
            "_id": "61794b13681b448f83009b9d",
            "owner": "0xD59428c62650c9d4505b01fBa9bf9469b920a66F",
            "name": "Rahul Rai",
            "website": "https://www.blocktower.com/",
            "telegram": null,
            "twitter": "@BlockTower",
            "linkedIn": "https://www.linkedin.com/company/blocktower/",
            "companyName": "BlockTower Capital",
            "aboutBusiness": "BlockTower is an institutional investment firm focused on cryptocurrency and blockchain technology. Founded in 2017 by Ari Paul (University of Chicago Endowment portfolio manager and Susquehanna International Group trader), and Matthew Goetz (Goldman Sachs executive and engineer), the firm applies professional trading, investing, and risk management to this digital asset class, and manages capital for leading LPs including Andreessen Horowitz, Union Square Ventures, and Howard Morgan, the co-founder of First Round Capital and Renaissance Technologies.",
            "allowList": true,
            "createdAt": "2021-07-06T05:12:56.335Z",
            "updatedAt": "2021-07-06T05:12:56.335Z"
          },
          "poolName": "BlockTower Capital - USDC01",
          "contractAddress": "0xd618d93676762a8e3107554d9adbff7dfd7fbf47",
          "strategy": "THIS IS A PERMISSIONED POOL AND ONLY AVAILABLE FOR LENDERS THAT ARE WHITELISTED AFTER GOING THROUGH KYC/AML PROCEDURES.",
          "createdAt": "2021-10-28T13:40:47.732Z",
          "updatedAt": "2021-12-10T15:21:19.537Z",
          "state": "Finalized",
          "liquidityAsset": {
            "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "symbol": "USDC",
            "decimals": 6
          },
          "liquidityLocker": "0x600707c2411450851a2464f20ff2a07abdeeacf1",
          "stakeLocker": "0xd9631f58f3afcd1d0e5863b31c7924a3fb79253d",
          "liquidityCap": "75000000000000",
          "stakeAsset": {
            "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "500",
          "delegateFee": "0",
          "ongoingFee": "500",
          "name": "Maple Pool Token",
          "numActiveLoans": "3",
          "allowedLPs": [
            "0xd59428c62650c9d4505b01fba9bf9469b920a66f"
          ],
          "allowedSLs": [],
          "lpApy": "1000",
          "lendingApy": "949",
          "stakingApy": "29440",
          "farmingApy": "900",
          "stakeRewardsApy": "0",
          "balance": "50000000000001",
          "liquidity": "1",
          "lockupPeriod": "15552000",
          "stake": "7300000000000000000",
          "currentLoaned": "50000000000000",
          "totalLoanOriginations": "75000000000000",
          "totalInterestEarned": "916945205481",
          "totalFees": "187499999993",
          "stakeLockerFees": "48260273970",
          "poolDelegateFees": "187499999993",
          "numPositions": "1",
          "txCount": "15",
          "transactionHash": "0x778d42cb7d796fb7c6129d4f8d3d9ee1987e479164fafae6670318141491b822",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "50000000000000000000000000",
          "totalLoaned": "75000000000000",
          "totalPrincipalRepaid": "25000000000000",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x778d42cb7d796fb7c6129d4f8d3d9ee1987e479164fafae6670318141491b822",
            "timestamp": "1636033466"
          },
          "mplRewards": {
            "id": "0xd0123f5220a36e9ec6082d83b4a11f92aa48ccd0",
            "periodFinish": "0",
            "reward": "0",
            "rewardRate": "0",
            "rewardsDuration": "0",
            "paused": false
          },
          "totalPoolTokensStaked": "0",
          "stakeRewards": {
            "id": "0x0000000000000000000000000000000000000000",
            "periodFinish": "0",
            "reward": "0",
            "rewardRate": "0",
            "rewardsDuration": "0",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "0",
          "stakeLockerLiquidity": "48260273970",
          "stakeLockupPeriod": "15552000",
          "openToPublic": false,
          "stakeLockerOpenToPublic": false
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

type MplRewards {
  id: String
  periodFinish: String
  reward: String
  rewardRate: String
  rewardsDuration: String
  paused: Boolean
}

type PoolDelegate {
  _id: String
  owner: String
  name: String
  website: String
  telegram: String
  twitter: String
  linkedIn: String
  companyName: String
  aboutBusiness: String
  allowList: Boolean
  createdAt: String
  updatedAt: String
}

type PoolPosition {
  id: String
  pool: Pool
  poolTokenBalance: String
  poolTokensStaked: String
  claimableInterest: String
  interestEarned: String
  claimableLendingReward: String
  rewardPaid: String
  custodyAllowance: String
  depositDate: String
  withdrawCooldown: String
  withdrawStatus: WithdrawalStatus
  stake: String
  stakeLockerTokensStaked: String
  claimableFees: String
  feesEarned: String
  claimableStakingReward: String
  stakeRewardPaid: String
  stakeCustodyAllowance: String
  stakeDate: String
  unstakeCooldown: String
  transaction: Transaction
}

type Pool {
  _id: String
  poolDelegate: PoolDelegate
  poolName: String
  contractAddress: String
  strategy: String
  createdAt: String
  updatedAt: String
  state: String
  liquidityAsset: Asset
  liquidityLocker: String
  stakeLocker: String
  liquidityCap: String
  stakeAsset: Asset
  stakingFee: String
  delegateFee: String
  ongoingFee: Strin
  name: String
  numActiveLoans: String
  allowedLPs: [String]
  allowedSLs: [String]
  lpApy: String
  lendingApy: String
  stakingApy: String
  farmingApy: String
  stakeRewardsApy: String
  balance: String
  liquidity: String
  lockupPeriod: String
  stake: String
  currentLoaned: String
  totalLoanOriginations: String
  totalInterestEarned: String
  totalFees: String
  stakeLockerFees: String
  poolDelegateFees: String
  numPositions: String
  txCount: String
  transactionHash: String
  defaultsTotal: String
  liquidityAssetRecoveredTotal: String
  poolTokenTotalSupply: String
  totalLoaned: String
  totalPrincipalRepaid: String
  symbol: String
  poolPositions: [PoolPosition]
  transaction: Transaction
  mplRewards: MplRewards
  totalPoolTokensStaked: String
  stakeRewards: MplRewards
  totalStakeLockerTokensStaked: String
  stakeLockerLiquidity: String
  stakeLockupPeriod: String
  openToPublic: Boolean
  stakeLockerOpenToPublic: Boolean
}
```
{% endtab %}
{% endtabs %}



### Pool Loans by Pool Contract Address <a href="#maple-globals" id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  allPoolWithdrawnLoans(
    filter: { skip: 0, limit: 10 }
    poolId: "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27"
  ) {
    list {
      apr
      collateralRatio
      drawdownDate
      requestAmount
      state
      termDays
      treasuryFees
      borrower {
        companyName
      }
      collateralAsset {
        symbol
        decimals
      }
      liquidityAsset {
        symbol
        decimals
      }
    }
    skip
    limit
    total
  }
}

```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "allPoolWithdrawnLoans": {
      "list": [
        {
          "apr": "975",
          "collateralRatio": "0",
          "drawdownDate": "1642524076",
          "requestAmount": "5000000000000",
          "state": "Active",
          "termDays": 180,
          "treasuryFees": "12500000000",
          "borrower": {
            "companyName": "Nibbio"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "975",
          "collateralRatio": "0",
          "drawdownDate": "1634048475",
          "requestAmount": "1000000000000",
          "state": "Matured",
          "termDays": 90,
          "treasuryFees": "2500000000",
          "borrower": {
            "companyName": "Akuna"
          },
          "collateralAsset": {
            "symbol": "USDC",
            "decimals": 6
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "1500",
          "collateralRatio": "0",
          "drawdownDate": "1622022806",
          "requestAmount": "2000000000000",
          "state": "Matured",
          "termDays": 90,
          "treasuryFees": "10000000000",
          "borrower": {
            "companyName": "Wintermute Trading"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "1100",
          "collateralRatio": "0",
          "drawdownDate": "1625197774",
          "requestAmount": "4000000000000",
          "state": "Matured",
          "termDays": 180,
          "treasuryFees": "20000000000",
          "borrower": {
            "companyName": "MGNR"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "1150",
          "collateralRatio": "0",
          "drawdownDate": "1638997544",
          "requestAmount": "8000000000000",
          "state": "Active",
          "termDays": 180,
          "treasuryFees": "20000000000",
          "borrower": {
            "companyName": "AP Capital"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "1100",
          "collateralRatio": "5000",
          "drawdownDate": "1636403876",
          "requestAmount": "4000000000000",
          "state": "Active",
          "termDays": 180,
          "treasuryFees": "10000000000",
          "borrower": {
            "companyName": "Framework Labs"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "1150",
          "collateralRatio": "0",
          "drawdownDate": "1634819329",
          "requestAmount": "8500000000000",
          "state": "Active",
          "termDays": 180,
          "treasuryFees": "21250000000",
          "borrower": {
            "companyName": "Folkvang"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "800",
          "collateralRatio": "2000",
          "drawdownDate": "1629341193",
          "requestAmount": "5000000000000",
          "state": "Active",
          "termDays": 180,
          "treasuryFees": "12500000000",
          "borrower": {
            "companyName": "Framework Labs"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "900",
          "collateralRatio": "0",
          "drawdownDate": "1628572380",
          "requestAmount": "4000000000000",
          "state": "Active",
          "termDays": 180,
          "treasuryFees": "10000000000",
          "borrower": {
            "companyName": "Vexil Capital"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        },
        {
          "apr": "775",
          "collateralRatio": "0",
          "drawdownDate": "1629950915",
          "requestAmount": "9500000000000",
          "state": "Active",
          "termDays": 180,
          "treasuryFees": "23750000000",
          "borrower": {
            "companyName": "Alameda Research"
          },
          "collateralAsset": {
            "symbol": "WBTC",
            "decimals": 8
          },
          "liquidityAsset": {
            "symbol": "USDC",
            "decimals": 6
          }
        }
      ],
      "skip": 0,
      "limit": 10,
      "total": 44
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

type BorrowerPublic {
  companyName: String
}

type LoanPublic {
  apr: String
  collateralRatio: String
  requestAmount: String
  drawdownDate: String
  state: String
  termDays: Int
  borrower: BorrowerPublic
  collateralAsset: Asset
  liquidityAsset: Asset
}
```
{% endtab %}
{% endtabs %}

### Pool by Contract Address <a href="#maple-globals" id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  pool(contractAddress: "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27") {
    _id
    poolDelegate {
      _id
      owner
      name
      website
      telegram
      twitter
      linkedIn
      companyName
      aboutBusiness
      allowList
      createdAt
      updatedAt
    }
    poolName
    contractAddress
    strategy
    createdAt
    updatedAt
    state
    liquidityAsset {
      address
      symbol
      decimals
    }
    liquidityLocker
    stakeLocker
    liquidityCap
    stakeAsset {
      address
      symbol
      decimals
    }
    stakingFee
    delegateFee
    ongoingFee
    name
    numActiveLoans
    allowedLPs
    allowedSLs
    lpApy
    lendingApy
    stakingApy
    farmingApy
    stakeRewardsApy
    balance
    liquidity
    lockupPeriod
    stake
    currentLoaned
    totalLoanOriginations
    totalInterestEarned
    totalFees
    stakeLockerFees
    poolDelegateFees
    transactionHash
    defaultsTotal
    liquidityAssetRecoveredTotal
    poolTokenTotalSupply
    totalLoaned
    totalPrincipalRepaid
    symbol
    transaction {
      id
      timestamp
    }
    mplRewards {
      id
      periodFinish
      reward
      rewardRate
      rewardsDuration
      paused
    }
    totalPoolTokensStaked
    stakeRewards {
      id
      periodFinish
      reward
      rewardRate
      rewardsDuration
      paused
    }
    totalStakeLockerTokensStaked
    stakeLockerLiquidity
    stakeLockupPeriod
    openToPublic
    stakeLockerOpenToPublic
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "pool": {
      "_id": "60a48265ec0b150011480d2a",
      "poolDelegate": {
        "_id": "60a481fdec0b150011480d28",
        "owner": "0xA6cCb9483E3E7a737E3a4F5B72a1Ce51838ba122",
        "name": "Josh Green",
        "website": "https://orthogonal.trading/",
        "telegram": "",
        "twitter": "@OrthoTrading",
        "linkedIn": "",
        "companyName": "Orthogonal Trading",
        "aboutBusiness": "Orthogonal Trading exploits inefficiencies in the nascent digital asset markets by marrying a consistent positive carry arbitrage trading backbone with fat tail capture via intelligent systematic trend following and alpha-generative options strategies.",
        "allowList": true,
        "createdAt": "2021-05-19T03:11:57.680Z",
        "updatedAt": "2021-05-19T03:11:57.680Z"
      },
      "poolName": "Orthogonal Trading - USDC01",
      "contractAddress": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27",
      "strategy": "The strategy of this Pool will be to target industry-leading funds and prop trading desks. The focus will be on mitigating risk by lending to market makers and arbitrage traders to avoid taking directional risk on the prices of crypto assets. Borrowers' creditworthiness is assessed based on how they manage leverage, liquidity risk, operational risk controls, management's level of experience, their balance sheet strength and recent financial performance. Loans in the pool will generally vary between 0 and 50% collateralization and target a weighted average APY of low-to-mid teens in line with the market for stablecoin lending.",
      "createdAt": "2021-05-19T03:13:41.035Z",
      "updatedAt": "2021-12-02T16:15:33.786Z",
      "state": "Finalized",
      "liquidityAsset": {
        "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "symbol": "USDC",
        "decimals": 6
      },
      "liquidityLocker": "0xb5321058e209e0f6c1216a7c7922b6962681dd77",
      "stakeLocker": "0x12b2bbbfab2ce6789df5659e9ac27a4a91c96c5c",
      "liquidityCap": "275000000000000",
      "stakeAsset": {
        "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
        "symbol": "BPT",
        "decimals": 18
      },
      "stakingFee": "1000",
      "delegateFee": "1000",
      "ongoingFee": "2000",
      "name": "Maple Pool Token",
      "numActiveLoans": "26",
      "allowedLPs": [
        "0x56221aaf897207f628cfb4cd6c1231d59de17f39",
        "0x009fdde3e654cb2495135708dc1590daefb14ea7",
        "0xc3c14f31c8db2417d1695fa6c8bebe8f2804677e",
        "0xbea07b01e8fe3936a3d206158521a87addb65cfe",
        "0xc32d7f8b71b6f79c9c2d0df200fc76fd6028d215",
        "0x79d93cbf3583e62dd3edbddd1ee1121f8b07af81",
        "0x0dbbfa0960f1c54e6039350ba2e3bf014746bdd2",
        "0x0dc874fb5260bd8749e6e98fd95d161b7605774d",
        "0x6912a141ad1566f5da7515f522bb756a5a9e85e9",
        "0xbf25f6f448f3715323c90c3e584c19d03775deb1",
        "0xf9fe05ea33742fa32cafb347920b7d53277a73dd",
        "0x7aec08ef2c0500b68df3a55a7727813ef79aeb13"
      ],
      "allowedSLs": [
        "0x04eb07c283cd6d9bf237118e2732d8b6ee5ee457",
        "0xf097c7f3b2203692427e4545b79613bd3cff66ce"
      ],
      "lpApy": "974",
      "lendingApy": "733",
      "stakingApy": "2748",
      "farmingApy": "794",
      "stakeRewardsApy": "807",
      "balance": "230123185332596",
      "liquidity": "16623185332596",
      "lockupPeriod": "7776000",
      "stake": "790583571115484189426",
      "currentLoaned": "213500000000000",
      "totalLoanOriginations": "251500200000000",
      "totalInterestEarned": "4656427627476",
      "totalFees": "701746866395",
      "stakeLockerFees": "582053453348",
      "poolDelegateFees": "1274553703306",
      "transactionHash": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
      "defaultsTotal": "0",
      "liquidityAssetRecoveredTotal": "0",
      "poolTokenTotalSupply": "227892542245122000000000000",
      "totalLoaned": "251500200000000",
      "totalPrincipalRepaid": "38000200000000",
      "symbol": "LP-MPL",
      "transaction": {
        "id": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
        "timestamp": "1621394109"
      },
      "mplRewards": {
        "id": "0x7869d7a3b074b5fa484dc04798e254c9c06a5e90",
        "periodFinish": "1645799808",
        "reward": "100739000000000000000000",
        "rewardRate": "38865354938271604",
        "rewardsDuration": "2592000",
        "paused": false
      },
      "totalPoolTokensStaked": "224199171478304000000000000",
      "stakeRewards": {
        "id": "0xf9d4d5a018d91e9bccc1e35ea78fcfecf4c5cbca",
        "periodFinish": "1644041537",
        "reward": "3840000000000000000000",
        "rewardRate": "1481481481481481",
        "rewardsDuration": "2592000",
        "paused": false
      },
      "totalStakeLockerTokensStaked": "765758099037618034192",
      "stakeLockerLiquidity": "431455068116",
      "stakeLockupPeriod": "15552000",
      "openToPublic": true,
      "stakeLockerOpenToPublic": true
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

type MplRewards {
  id: String
  periodFinish: String
  reward: String
  rewardRate: String
  rewardsDuration: String
  paused: Boolean
}

type PoolDelegate {
  _id: String
  owner: String
  name: String
  website: String
  telegram: String
  twitter: String
  linkedIn: String
  companyName: String
  aboutBusiness: String
  allowList: Boolean
  createdAt: String
  updatedAt: String
}

type PoolPosition {
  id: String
  pool: Pool
  poolTokenBalance: String
  poolTokensStaked: String
  claimableInterest: String
  interestEarned: String
  claimableLendingReward: String
  rewardPaid: String
  custodyAllowance: String
  depositDate: String
  withdrawCooldown: String
  withdrawStatus: WithdrawalStatus
  stake: String
  stakeLockerTokensStaked: String
  claimableFees: String
  feesEarned: String
  claimableStakingReward: String
  stakeRewardPaid: String
  stakeCustodyAllowance: String
  stakeDate: String
  unstakeCooldown: String
  transaction: Transaction
}

type Pool {
  _id: String
  poolDelegate: PoolDelegate
  poolName: String
  contractAddress: String
  strategy: String
  createdAt: String
  updatedAt: String
  state: String
  liquidityAsset: Asset
  liquidityLocker: String
  stakeLocker: String
  liquidityCap: String
  stakeAsset: Asset
  stakingFee: String
  delegateFee: String
  ongoingFee: Strin
  name: String
  numActiveLoans: String
  allowedLPs: [String]
  allowedSLs: [String]
  lpApy: String
  lendingApy: String
  stakingApy: String
  farmingApy: String
  stakeRewardsApy: String
  balance: String
  liquidity: String
  lockupPeriod: String
  stake: String
  currentLoaned: String
  totalLoanOriginations: String
  totalInterestEarned: String
  totalFees: String
  stakeLockerFees: String
  poolDelegateFees: String
  numPositions: String
  txCount: String
  transactionHash: String
  defaultsTotal: String
  liquidityAssetRecoveredTotal: String
  poolTokenTotalSupply: String
  totalLoaned: String
  totalPrincipalRepaid: String
  symbol: String
  poolPositions: [PoolPosition]
  transaction: Transaction
  mplRewards: MplRewards
  totalPoolTokensStaked: String
  stakeRewards: MplRewards
  totalStakeLockerTokensStaked: String
  stakeLockerLiquidity: String
  stakeLockupPeriod: String
  openToPublic: Boolean
  stakeLockerOpenToPublic: Boolean
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
      symbol
      decimals
    }
    collateralAsset {
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
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "21250000000000",
        "drawdownAmount": "21250000000000",
        "drawdownDate": "1637302881",
        "fundingDate": "1637302707",
        "maturityDate": "1645078881",
        "treasuryFees": "53125000000",
        "claimableAmount": "1",
        "principalOwed": "21250000000000",
        "nextPayment": "21398458904109",
        "nextPaymentDue": "1645078881",
        "paymentsRemaining": "1",
        "interestPaid": "296917808218",
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
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "10100000000000",
        "drawdownAmount": "10100000000000",
        "drawdownDate": "1641188899",
        "fundingDate": "1640273142",
        "maturityDate": "1648964899",
        "treasuryFees": "25250000000",
        "claimableAmount": "1",
        "principalOwed": "10100000000000",
        "nextPayment": "70561643835",
        "nextPaymentDue": "1646372899",
        "paymentsRemaining": "2",
        "interestPaid": "70561643835",
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
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "5800000000000",
        "drawdownAmount": "5800000000000",
        "drawdownDate": "1629025245",
        "fundingDate": "1628921870",
        "maturityDate": "1644577245",
        "treasuryFees": "14500000000",
        "claimableAmount": "1",
        "principalOwed": "5800000000000",
        "nextPayment": "5836945205479",
        "nextPaymentDue": "1644577245",
        "paymentsRemaining": "1",
        "interestPaid": "186573287668",
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
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "8000000000000",
        "drawdownAmount": "8000000000000",
        "drawdownDate": "1639130366",
        "fundingDate": "1638869070",
        "maturityDate": "1646906366",
        "treasuryFees": "20000000000",
        "claimableAmount": "1",
        "principalOwed": "8000000000000",
        "nextPayment": "8052602739726",
        "nextPaymentDue": "1646906366",
        "paymentsRemaining": "1",
        "interestPaid": "105205479452",
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
        "state": "Active",
        "paymentIntervalDays": 30,
        "collateralAmount": "0",
        "amountFunded": "23300000000000",
        "drawdownAmount": "23300000000000",
        "drawdownDate": "1640165336",
        "fundingDate": "1640073870",
        "maturityDate": "1647941336",
        "treasuryFees": "58250000000",
        "claimableAmount": "1",
        "principalOwed": "23300000000000",
        "nextPayment": "162780821917",
        "nextPaymentDue": "1645349336",
        "paymentsRemaining": "2",
        "interestPaid": "170919863012",
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
        "state": "Active",
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
        "nextPayment": "96164383561",
        "nextPaymentDue": "1645058638",
        "paymentsRemaining": "3",
        "interestPaid": "293301369861",
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

### Positions by Account Address

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  accountPositions(account: "0x741aa7cfb2c7bf2a1e7d4da2e3df6a56ca4131f3") {
    list {
      id
      pool {
        poolName
      }
      poolTokenBalance
      poolTokensStaked
      claimableInterest
      interestEarned
      claimableLendingReward
      rewardPaid
      custodyAllowance
      depositDate
      withdrawCooldown
      stake
      stakeLockerTokensStaked
      claimableFees
      feesEarned
      claimableStakingReward
      stakeRewardPaid
      stakeCustodyAllowance
      stakeDate
      unstakeCooldown
      transaction {
        id
        timestamp
      }
    }
    totalClaimableLendingReward
    totalClaimableStakingReward
    totalLendingApy
    totalStakingApy
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "accountPositions": {
      "list": [
        {
          "id": "0x741aa7cfb2c7bf2a1e7d4da2e3df6a56ca4131f3-0x6f6c8013f639979c84b756c7fc1500eb5af18dc4",
          "pool": {
            "poolName": "Maven 11 - USDC 01"
          },
          "poolTokenBalance": "7019529932992000000000000",
          "poolTokensStaked": "7019529932992000000000000",
          "claimableInterest": "13032042814",
          "interestEarned": "142434229865",
          "claimableLendingReward": "638282413161012244651",
          "rewardPaid": "18983618137474736123859",
          "custodyAllowance": "7019529932992000000000000",
          "depositDate": "1632271809",
          "withdrawCooldown": "0",
          "stake": "40927281295993497795",
          "stakeLockerTokensStaked": "40927281295993497795",
          "claimableFees": "2593670699",
          "feesEarned": "19303635817",
          "claimableStakingReward": "155378925135944040123",
          "stakeRewardPaid": "222027587334464892846",
          "stakeCustodyAllowance": "40927281295993497795",
          "stakeDate": "1636378047",
          "unstakeCooldown": "0",
          "transaction": {
            "id": "0xdd3e9d3dcd8718ac9b47f663cbe6c1339b83fe32c81b20b295be86646e2ff5ea",
            "timestamp": "1630537850"
          }
        },
        {
          "id": "0x741aa7cfb2c7bf2a1e7d4da2e3df6a56ca4131f3-0xfebd6f15df3b73dc4307b1d7e65d46413e710c27",
          "pool": {
            "poolName": "Orthogonal Trading - USDC01"
          },
          "poolTokenBalance": "13066137619554000000000000",
          "poolTokensStaked": "13066137619554000000000000",
          "claimableInterest": "18637085114",
          "interestEarned": "288881341403",
          "claimableLendingReward": "446903316790591861285",
          "rewardPaid": "45671255441301487940323",
          "custodyAllowance": "13066137619554000000000000",
          "depositDate": "1630537850",
          "withdrawCooldown": "0",
          "stake": "32819501643939964753",
          "stakeLockerTokensStaked": "32819501643939964753",
          "claimableFees": "5405170990",
          "feesEarned": "14984316254",
          "claimableStakingReward": "141199364952922645748",
          "stakeRewardPaid": "350018578141490053039",
          "stakeCustodyAllowance": "32819501643939964753",
          "stakeDate": "1633501814",
          "unstakeCooldown": "0",
          "transaction": {
            "id": "0x12245987bb926fc2c3f1a1f6c5ed5de202089366753e2724f5c5455b6a0de1ce",
            "timestamp": "1630537850"
          }
        }
      ],
      "totalClaimableLendingReward": "1085185729951604105936",
      "totalClaimableStakingReward": "296578290088866685871",
      "totalLendingApy": "1525",
      "totalStakingApy": "3199"
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Transaction {
  id: String
  timestamp: String
}

type Pool {
  poolName: String
}

type PoolPosition {
  id: String
  pool: Pool
  poolTokenBalance: String
  poolTokensStaked: String
  claimableInterest: String
  interestEarned: String
  claimableLendingReward: String
  rewardPaid: String
  custodyAllowance: String
  depositDate: String
  withdrawCooldown: String
  stake: String
  stakeLockerTokensStaked: String
  claimableFees: String
  feesEarned: String
  claimableStakingReward: String
  stakeRewardPaid: String
  stakeCustodyAllowance: String
  stakeDate: String
  unstakeCooldown: String
  transaction: Transaction
}

type AccountPositions {
  list: [PoolPosition]
  totalClaimableLendingReward: String
  totalClaimableStakingReward: String
  totalLendingApy: String
  totalStakingApy: String
}
```
{% endtab %}
{% endtabs %}

### Transactions by Account Address

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  accountTxes(account: "0x5ce4104c395665e68d5b09949002070aa31ffe7b") {
    id
    pool {
      poolName
    }
    amount
    symbol
    decimals
    value
    transaction {
      id
      timestamp
    }
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "accountTxes": [
      {
        "id": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4-1173",
        "pool": {
          "poolName": "Maven 11 - USDC 01"
        },
        "amount": "25000000000000",
        "symbol": "USDC",
        "decimals": 6,
        "value": "25000000000000",
        "transaction": {
          "id": "0xe2de6ac701edb138ae950885d509b20b1a9a78b0463b7873e7c4f3ef2e5fbec8",
          "timestamp": "1638439687"
        }
      },
      {
        "id": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4-1178",
        "pool": {
          "poolName": "Maven 11 - USDC 01"
        },
        "amount": "25000000000000000000000000",
        "symbol": "MPT",
        "decimals": 18,
        "value": "25000000000000",
        "transaction": {
          "id": "0x8f6f4bc984707072e727f5cfd04daba980f1db8d2db03fbb760599e8c15d56a2",
          "timestamp": "1638442299"
        }
      },
      {
        "id": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4-638",
        "pool": {
          "poolName": "Maven 11 - USDC 01"
        },
        "amount": "10000000000000",
        "symbol": "USDC",
        "decimals": 6,
        "value": "10000000000000",
        "transaction": {
          "id": "0x2510f61ca6e309935cf58d30f8875fa9c6f6ce01700bea54efe7d0ed8c70dc4d",
          "timestamp": "1633931539"
        }
      },
      {
        "id": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4-639",
        "pool": {
          "poolName": "Maven 11 - USDC 01"
        },
        "amount": "10000000000000000000000000",
        "symbol": "MPT",
        "decimals": 18,
        "value": "10000000000000",
        "transaction": {
          "id": "0x7d9a312f378defd20a79220418253b86ef945fa6e81722447b21bed59a3f5662",
          "timestamp": "1633932045"
        }
      },
      {
        "id": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27-1437",
        "pool": {
          "poolName": "Orthogonal Trading - USDC01"
        },
        "amount": "20000000000000",
        "symbol": "USDC",
        "decimals": 6,
        "value": "20000000000000",
        "transaction": {
          "id": "0xa88d2092f1eaccf6a87d31fe6e53da091f9ee45a460ec562f7c0d5c27e553a07",
          "timestamp": "1638437061"
        }
      },
      {
        "id": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27-1439",
        "pool": {
          "poolName": "Orthogonal Trading - USDC01"
        },
        "amount": "20000000000000000000000000",
        "symbol": "MPT",
        "decimals": 18,
        "value": "20000000000000",
        "transaction": {
          "id": "0x17a228165f34b369958dc31f0efe8b383eb9c25d2f84d68128b4379e552cfb13",
          "timestamp": "1638439257"
        }
      },
      {
        "id": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27-568",
        "pool": {
          "poolName": "Orthogonal Trading - USDC01"
        },
        "amount": "7999985000000",
        "symbol": "USDC",
        "decimals": 6,
        "value": "7999985000000",
        "transaction": {
          "id": "0x9788377c27866ba1684747137b2d0bf032e57a8b80644f32fd6d39a2f164cc6c",
          "timestamp": "1630512516"
        }
      },
      {
        "id": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27-569",
        "pool": {
          "poolName": "Orthogonal Trading - USDC01"
        },
        "amount": "7999985000000000000000000",
        "symbol": "MPT",
        "decimals": 18,
        "value": "7999985000000",
        "transaction": {
          "id": "0x03749fcdba5b657f27259793e0e4ef2519828ef375f30c4f4afcb426b9475444",
          "timestamp": "1630513245"
        }
      },
      {
        "id": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27-821",
        "pool": {
          "poolName": "Orthogonal Trading - USDC01"
        },
        "amount": "2000000000000",
        "symbol": "USDC",
        "decimals": 6,
        "value": "2000000000000",
        "transaction": {
          "id": "0xb0083a002d9c990fceb4a3dca87447e119c0769efa5e477d26875b5b758baf17",
          "timestamp": "1633932994"
        }
      },
      {
        "id": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27-835",
        "pool": {
          "poolName": "Orthogonal Trading - USDC01"
        },
        "amount": "2000000000000000000000000",
        "symbol": "MPT",
        "decimals": 18,
        "value": "2000000000000",
        "transaction": {
          "id": "0x559ec3e291d2c876a50d460a3d75e52a7e71a76b437b02ecfced37e5d503fa19",
          "timestamp": "1634011070"
        }
      }
    ]
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Transaction {
  id: String
  timestamp: String
}

type Pool {
  poolName: String
}

type Tx {
  id: String
  pool: Pool
  type: TxType
  amount: String
  symbol: String
  decimals: Int
  value: String
  transaction: Transaction
}
```
{% endtab %}
{% endtabs %}
