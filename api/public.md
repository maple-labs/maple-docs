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
    totalLiquidity
    totalLiquidityProvided
    totalLoanOriginations
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
      price
    }
    collateralAssets {
      address
      symbol
      decimals
      price
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
```graphql
{
  "data": {
    "mapleGlobals": {
      "totalLiquidity": 0,
      "totalLiquidityProvided": "2500000000",
      "totalLoanOriginations": "1000000000",
      "totalTreasuryFees": "5000000",
      "totalCurrentLoaned": "1",
      "aggregateLpApy": "0",
      "totalPools": 1,
      "totalFinalizedPools": 1,
      "totalLoans": 1,
      "totalActiveLoans": 0,
      "totalValueLocked": 219.9225292,
      "mpl": {
        "address": "0x9809cb0342e120365fe10ebf84f8ec5375693eb5",
        "symbol": "MPL",
        "decimals": 18,
        "price": 1207824
      },
      "liquidityAssets": [
        {
          "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
          "symbol": "USDC",
          "decimals": 6,
          "price": 100000000
        }
      ],
      "collateralAssets": [
        {
          "address": "0x1fea817089ffe74d50815496d6ae15da6bc1ce41",
          "symbol": "WETH",
          "decimals": 18,
          "price": 100000000
        },
        {
          "address": "0x7dbbaa329613ac04b4381d3d64c2adb13bd60534",
          "symbol": "DAI",
          "decimals": 18,
          "price": 100000000
        },
        {
          "address": "0xa23fac1cf3f1abb2bdd48579346653a765e31cb6",
          "symbol": "WBTC",
          "decimals": 8,
          "price": 100000000
        }
      ],
      "stakeAssets": [
        {
          "address": "0x892689147ab1ccf60237696de6a028b8959561cb",
          "symbol": "BPT",
          "decimals": 18,
          "price": 21980198020
        }
      ],
      "defaultGracePeriod": 172800,
      "swapOutRequired": 20000,
      "fundingPeriod": 432000,
      "investorFee": 25,
      "treasuryFee": 25,
      "maxSwapSlippage": 500,
      "minLoanEquity": 1000,
      "lpCooldownPeriod": 432000,
      "lpWithdrawWindow": 86400,
      "stakerUnstakeWindow": 86400,
      "stakerCooldownPeriod": 432000
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type MapleGlobals {
  totalLiquidity: Float
  totalLiquidityProvided: String
  totalLoanOriginations: String
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

### All Pools <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query AllPools {
  allPools {
    list {
      _id
      poolDelegate {
        name
        twitter
        companyName
      }
      stakingFee
      delegateFee
      ongoingFee
      name
      numActiveLoans
      lpApy
      stakingApy
      farmingApy
      stakeRewardsApy
      balance
      liquidity
      stake
      currentLoaned
      strategy
      poolName
      contractAddress
      stakeAsset {
        address
        symbol
      }
      liquidityCap
      liquidityAsset {
        address
        symbol
      }
      createdAt
    }
  }
}

```
{% endtab %}

{% tab title="Response" %}
```graphql
{
  "data": {
    "allPools": {
      "list": [
        {
          "_id": "60e3e70cd993f30012ceae40",
          "poolDelegate": {
            "name": "Balder Bomans",
            "twitter": "@maven11capital",
            "companyName": "Maven 11 Capital"
          },
          "stakingFee": "1000",
          "delegateFee": "1000",
          "ongoingFee": "2000",
          "name": "Maple Pool Token",
          "numActiveLoans": "14",
          "lpApy": "901",
          "stakingApy": "0",
          "farmingApy": "1309",
          "stakeRewardsApy": "809",
          "balance": "68716215934881",
          "liquidity": "116215934881",
          "stake": "247403831141476416291",
          "currentLoaned": "68600000000000",
          "strategy": "The strategy of this pool will be to target borrowers with capital intensive businesses supported by a strong balance sheet. The Pool Delegate will methodically build the credit history of the borrowers by starting with smaller loans. These will grow in size as PD becomes more comfortable with the counter parties. Creditworthiness is assessed based on balance sheet, recent profitability, leverage, liquidity risk, internal (risk) control systems, strength and track record of the team, among other things. The pool is USDC denominated. Collateralization ratios can vary between 0 - 100%.",
          "poolName": "Maven 11 - USDC 01",
          "contractAddress": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4",
          "stakeAsset": {
            "address": null,
            "symbol": "BPT"
          },
          "liquidityCap": "75000000000000",
          "liquidityAsset": {
            "address": null,
            "symbol": "USDC"
          },
          "createdAt": "2021-07-06T05:15:56.092Z"
        },
        {
          "_id": "60a48265ec0b150011480d2a",
          "poolDelegate": {
            "name": "Josh Green",
            "twitter": "@OrthoTrading",
            "companyName": "Orthogonal Trading"
          },
          "stakingFee": "1000",
          "delegateFee": "1000",
          "ongoingFee": "2000",
          "name": "Maple Pool Token",
          "numActiveLoans": "15",
          "lpApy": "821",
          "stakingApy": "0",
          "farmingApy": "1376",
          "stakeRewardsApy": "1371",
          "balance": "101007145602468",
          "liquidity": "3707145602468",
          "stake": "346781754665097345072",
          "currentLoaned": "97300000000000",
          "strategy": "The strategy of this Pool will be to target industry-leading funds and prop trading desks. The focus will be on mitigating risk by lending to market makers and arbitrage traders to avoid taking directional risk on the prices of crypto assets. Borrowers' creditworthiness is assessed based on how they manage leverage, liquidity risk, operational risk controls, management's level of experience, their balance sheet strength and recent financial performance. Loans in the pool will generally vary between 0 and 50% collateralization and target a weighted average APY of low-to-mid teens in line with the market for stablecoin lending.",
          "poolName": "Orthogonal Trading - USDC01",
          "contractAddress": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27",
          "stakeAsset": {
            "address": null,
            "symbol": "BPT"
          },
          "liquidityCap": "150000000000000",
          "liquidityAsset": {
            "address": null,
            "symbol": "USDC"
          },
          "createdAt": "2021-05-19T03:13:41.035Z"
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
  poolTokenBalance: String
  poolTokensStaked: String
  rewardPaid: String
  custodyAllowance: String
  depositDate: String
  withdrawCooldown: String
  stake: String
  stakeLockerTokensStaked: String
  stakeRewardPaid: String
  stakeCustodyAllowance: String
  stakeDate: String
  unstakeCooldown: String
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
  ongoingFee: String
  name: String
  numActiveLoans: String
  allowedLPs: [String]
  allowedSLs: [String]
  lpApy: String
  farmingApy: String
  stakingApy: String
  stakeRewardsApy: String
  balance: String
  liquidity: String
  lockupPeriod: String
  stake: String
  currentLoaned: String
  totalInterestEarned: String
  totalFees: String
  stakeLockerFees: String
  poolDelegateFees: String
  myInterestEarned: String
  myLiquidity: String
  myBalance: String
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



### Pool Loans <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query AllPoolWithdrawnLoans {
  allPoolWithdrawnLoans(
    filter: { skip: 0, limit: 10 }
    poolId: "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4"
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
```graphql
{
  "data": {
    "poolLoans": {
      "list": [
        {
          "apr": "1100",
          "collateralRatio": "0",
          "drawdownDate": "1626334913",
          "requestAmount": "2000000000000",
          "state": "Active",
          "termDays": 90,
          "borrower": {
            "companyName": "Orthogonal Trading"
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
          "drawdownDate": "1626329218",
          "requestAmount": "4000000000000",
          "state": "Active",
          "termDays": 90,
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
          "apr": "900",
          "collateralRatio": "0",
          "drawdownDate": "1626597309",
          "requestAmount": "4000000000000",
          "state": "Active",
          "termDays": 180,
          "borrower": {
            "companyName": "Symbolic Capital"
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
          "drawdownDate": "1627973247",
          "requestAmount": "5000000000000",
          "state": "Active",
          "termDays": 90,
          "borrower": {
            "companyName": "Parallel Capital"
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
          "apr": "1150",
          "collateralRatio": "0",
          "drawdownDate": "1626351548",
          "requestAmount": "1500000000000",
          "state": "Active",
          "termDays": 90,
          "borrower": {
            "companyName": "Apollo Capital"
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
          "apr": "950",
          "collateralRatio": "0",
          "drawdownDate": "1628418617",
          "requestAmount": "2500000000000",
          "state": "Active",
          "termDays": 90,
          "borrower": {
            "companyName": "OVEX"
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
          "apr": "900",
          "collateralRatio": "0",
          "drawdownDate": "1627664506",
          "requestAmount": "5000000000000",
          "state": "Active",
          "termDays": 180,
          "borrower": {
            "companyName": "Framework Labs"
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
          "apr": "2200",
          "collateralRatio": "0",
          "drawdownDate": "1626687544",
          "requestAmount": "250000000000",
          "state": "Active",
          "termDays": 90,
          "borrower": {
            "companyName": "Gattaca"
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
      "total": 8
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Asset {
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



### Pool by ID <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query PoolByID {
    pool(_id: "60e3e70cd993f30012ceae40") {
      _id
    	poolDelegate {
        name
        twitter
        companyName
      }
      stakingFee
      delegateFee
      ongoingFee
      name
      numActiveLoans
      lpApy
      stakingApy
      balance
      liquidity
      stake
      currentLoaned
      strategy
      poolName
      contractAddress
      stakeAsset {
        address
        symbol
      }
      liquidityCap
      liquidityAsset {
        address
        symbol
      }
      createdAt
    }
}
```
{% endtab %}

{% tab title="Response" %}
```graphql
{
  "data": {
    "pool": {
      "_id": "60e3e70cd993f30012ceae40",
      "poolDelegate": {
        "name": "Balder Bomans",
        "twitter": "@maven11capital",
        "companyName": "Maven 11 Capital"
      },
      "stakingFee": "1000",
      "delegateFee": "1000",
      "ongoingFee": "2000",
      "name": "Maple Pool Token",
      "numActiveLoans": "8",
      "lpApy": "950",
      "stakingApy": "0",
      "balance": "36297887567008",
      "liquidity": "12047887567008",
      "stake": "196336740867262850291",
      "currentLoaned": "24250000000000",
      "strategy": "The strategy of this pool will be to target borrowers with capital intensive businesses supported by a strong balance sheet. The Pool Delegate will methodically build the credit history of the borrowers by starting with smaller loans. These will grow in size as PD becomes more comfortable with the counter parties. Creditworthiness is assessed based on balance sheet, recent profitability, leverage, liquidity risk, internal (risk) control systems, strength and track record of the team, among other things. The pool is USDC denominated. Collateralization ratios can vary between 0 - 100%.",
      "poolName": "Maven 11 - USDC 01",
      "contractAddress": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4",
      "stakeAsset": {
        "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
        "symbol": "BPT"
      },
      "liquidityCap": "41500000000000",
      "liquidityAsset": {
        "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "symbol": "USDC"
      },
      "createdAt": "2021-07-06T05:15:56.092Z"
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Asset {
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
  poolTokenBalance: String
  poolTokensStaked: String
  rewardPaid: String
  custodyAllowance: String
  depositDate: String
  withdrawCooldown: String
  stake: String
  stakeLockerTokensStaked: String
  stakeRewardPaid: String
  stakeCustodyAllowance: String
  stakeDate: String
  unstakeCooldown: String
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
  ongoingFee: String
  name: String
  numActiveLoans: String
  allowedLPs: [String]
  allowedSLs: [String]
  lpApy: String
  farmingApy: String
  stakingApy: String
  stakeRewardsApy: String
  balance: String
  liquidity: String
  lockupPeriod: String
  stake: String
  currentLoaned: String
  totalInterestEarned: String
  totalFees: String
  stakeLockerFees: String
  poolDelegateFees: String
  myInterestEarned: String
  myLiquidity: String
  myBalance: String
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

