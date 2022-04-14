# Accounts

Maple protocol account data.



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
      withdrawStatus
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
          "poolTokenBalance": "16040632066769000000000000",
          "poolTokensStaked": "16040632066769000000000000",
          "claimableInterest": "9052036661",
          "interestEarned": "324288628307",
          "claimableLendingReward": "50554335233898372767",
          "rewardPaid": "28903461900849526873798",
          "custodyAllowance": "16040632066769000000000000",
          "depositDate": "1639569177",
          "withdrawCooldown": "0",
          "withdrawStatus": null,
          "stake": "40927281295993497795",
          "stakeLockerTokensStaked": "40927281295993497795",
          "claimableFees": "2196014423",
          "feesEarned": "43383602257",
          "claimableStakingReward": "0",
          "stakeRewardPaid": "422174097389281700065",
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
          "claimableInterest": "0",
          "interestEarned": "501640143810",
          "claimableLendingReward": "45749141365975727378",
          "rewardPaid": "54412255239517970216161",
          "custodyAllowance": "13066137619554000000000000",
          "depositDate": "1630537850",
          "withdrawCooldown": "0",
          "withdrawStatus": null,
          "stake": "32819501643939964753",
          "stakeLockerTokensStaked": "32819501643939964753",
          "claimableFees": "0",
          "feesEarned": "42037519726",
          "claimableStakingReward": "0",
          "stakeRewardPaid": "531738154807649367882",
          "stakeCustodyAllowance": "32819501643939964753",
          "stakeDate": "1633501814",
          "unstakeCooldown": "0",
          "transaction": {
            "id": "0x12245987bb926fc2c3f1a1f6c5ed5de202089366753e2724f5c5455b6a0de1ce",
            "timestamp": "1630537850"
          }
        }
      ],
      "totalClaimableLendingReward": "96303476599874100145",
      "totalClaimableStakingReward": "0",
      "totalLendingApy": "1285",
      "totalStakingApy": "1611"
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
  withdrawStatus: String
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

### Summary by Account Address

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  accountSummary(account: "0x741aa7cfb2c7bf2a1e7d4da2e3df6a56ca4131f3") {
    totalPoolTokenBalance
    totalPoolTokensStaked
    totalRewardPaid
    totalClaimableInterest
    totalInterestEarned
    totalStake
    totalStakeLockerTokensStaked
    totalStakeRewardPaid
    totalClaimableFees
    totalFeesEarned
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "accountSummary": {
      "totalPoolTokenBalance": "29106769686323000000000000",
      "totalPoolTokensStaked": "29106769686323000000000000",
      "totalRewardPaid": "83315717140367497089959",
      "totalClaimableInterest": "9052036661",
      "totalInterestEarned": "825928772117",
      "totalStake": "73746782939933462548",
      "totalStakeLockerTokensStaked": "73746782939933462548",
      "totalStakeRewardPaid": "953912252196931067947",
      "totalClaimableFees": "2196014423",
      "totalFeesEarned": "85421121983"
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type AccountSummary {
  totalPoolTokenBalance: String
  totalPoolTokensStaked: String
  totalRewardPaid: String
  totalClaimableInterest: String
  totalInterestEarned: String
  totalStake: String
  totalStakeLockerTokensStaked: String
  totalStakeRewardPaid: String
  totalClaimableFees: String
  totalFeesEarned: String
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
    total
    nextPage
    list {
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
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "accountTxes": {
      "total": 10,
      "nextPage": 0,
      "list": [
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
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
enum TxType {
  poolDeposit
  poolWithdraw
  poolWithdrawFunds
  stakeLockerStake
  stakeLockerUnstake
  stakeLockerWithdrawFunds
  lendingRewardsStake
  lendingRewardsWithdraw
  lendingRewardsGetReward
  stakingRewardsStake
  stakingRewardsWithdraw
  stakingRewardsGetReward
}

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

type AccountTransactions {
  list: [Tx]
  total: Int
  nextPage: Int
}
```
{% endtab %}
{% endtabs %}
