---
description: Private GraphQL resolvers for Maple Finance Protocol
---

# Private

The private GraphQL endpoint is [https://api.maple.finance/private](https://api.maple.finance/private). The following authentication headers must be passed with each request. Please refer to the [Auth](auth.md) section to get your auth challenge and how to create a signature.

```typescript
interface AuthHeaders {
  "x-auth-message": string;
  "x-auth-signature": string;
}
```

### All Loans <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query AllLoans {
  allLoans {
    limit
    skip
    total
    list {
      _id
      owner
      borrower {
        _id
        owner
        companyName
        companyEmail
        primaryAddress
        aboutCompany
        contactName
        telegram
        discord
        website
        twitter
        createdAt
        updatedAt
      }
      requestAmount
      loanNumber
      paymentStructure
      liquidityAsset {
        address
        symbol
        decimals
        price
      }
      collateralAsset {
        address
        symbol
        decimals
        price
      }
      collateralRatio
      apr
      purpose
      termDays
      state
      contractAddress
      paymentIntervalDays
      createdAt
      updatedAt
      collateralAmount
      amountFunded
      drawdownAmount
      drawdownDate
      maturityDate
      treasuryFees
      claimableAmount
      principalOwed
      nextPayment
      nextPaymentDue
      paymentsRemaining
      numLenders
      transactionHash
      collateralSwapped
      liquidityAssetReturned
      liquidationExcess
      defaultSuffered
      pools {
        poolName
        name
        amount
        companyName
      }
      poolDelegateFunding
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
```graphql
{
  "data": {
    "allLoans": {
      "limit": 10,
      "skip": 0,
      "total": 0,
      "list": [
        {
          "_id": "611dea6cd1f92ab1b779ad44",
          "borrower": {
            "_id": "611d071d6123e9abb3a79e02",
            "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
            "companyName": "Galaxy Trading",
            "companyEmail": "Elbert_Johnson23@hotmail.com",
            "primaryAddress": "278 Boehm Hollow",
            "aboutCompany": "Dicta rerum perferendis expedita libero aspernatur rem quia autem dolores. Eos corrupti eos optio enim. Aut maxime incidunt quia. Voluptatem dolorem assumenda minima consequuntur quis saepe voluptatem excepturi ut.",
            "contactName": "Deven",
            "telegram": "http://t.me/maplefinance",
            "discord": "https://discord.com/invite/maplefinance",
            "website": "https://genoveva.biz",
            "twitter": "@maplefinance"
          },
          "requestAmount": "1000000000000",
          "loanNumber": 21628566,
          "paymentStructure": "INTEREST_ONLY",
          "liquidityAsset": {
            "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
            "symbol": "USDC",
            "decimals": 6,
            "price": null
          },
          "collateralAsset": {
            "address": "0x1fea817089ffe74d50815496d6ae15da6bc1ce41",
            "symbol": "WETH",
            "decimals": 18,
            "price": null
          },
          "collateralRatio": 1000,
          "apr": 1000,
          "purpose": "Demo Loan purpose for infra",
          "termDays": 60,
          "state": "Draft",
          "contractAddress": null,
          "paymentIntervalDays": 30,
          "collateralAmount": null,
          "defaultSuffered": null,
          "amountFunded": null,
          "drawdownAmount": null,
          "claimableAmount": null,
          "principalOwed": null,
          "nextPaymentDue": null,
          "paymentsRemaining": null,
          "numLenders": null,
          "transactionHash": null,
          "collateralSwapped": null,
          "liquidityAssetReturned": null,
          "liquidationExcess": null,
          "poolDelegateFunding": null,
          "transaction": null,
          "pools": null
        }
      ]
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Company {
  _id: String
  owner: String
  companyName: String
  companyEmail: String
  primaryAddress: String
  aboutCompany: String
  contactName: String
  telegram: String
  discord: String
  website: String
  twitter: String
  createdAt: String
  updatedAt: String
}

type Transaction {
  id: String
  timestamp: String
}

type PoolTransaction {
  poolName: String
  name: String
  amount: String
  companyName: String
}

type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type Loan {
  _id: String
  owner: String
  borrower: Company
  requestAmount: String
  loanNumber: Int
  paymentStructure: String
  liquidityAsset: Asset
  collateralAsset: Asset
  collateralRatio: Int
  apr: Int
  purpose: String
  termDays: Int
  state: String
  contractAddress: String
  paymentIntervalDays: Int
  createdAt: String
  updatedAt: String
  collateralAmount: String
  amountFunded: String
  drawdownAmount: String
  drawdownDate: String
  maturityDate: String
  treasuryFees: String
  claimableAmount: String
  principalOwed: String
  nextPayment: String
  nextPaymentDue: String
  paymentsRemaining: String
  numLenders: String
  transactionHash: String
  collateralSwapped: String
  liquidityAssetReturned: String
  liquidationExcess: String
  defaultSuffered: String
  pools: [PoolTransaction]
  poolDelegateFunding: String
  transaction: Transaction
}
```
{% endtab %}
{% endtabs %}

### My Loans <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query MyLoans {
  myLoans {
    _id
    owner
    borrower {
      _id
      owner
      companyName
      companyEmail
      primaryAddress
      aboutCompany
      contactName
      telegram
      discord
      website
      twitter
      createdAt
      updatedAt
    }
    requestAmount
    loanNumber
    paymentStructure
    liquidityAsset {
      address
      symbol
      decimals
      price
    }
    collateralAsset {
      address
      symbol
      decimals
      price
    }
    collateralRatio
    apr
    purpose
    termDays
    state
    contractAddress
    paymentIntervalDays
    createdAt
    updatedAt
    collateralAmount
    amountFunded
    drawdownAmount
    drawdownDate
    maturityDate
    treasuryFees
    claimableAmount
    principalOwed
    nextPayment
    nextPaymentDue
    paymentsRemaining
    numLenders
    transactionHash
    collateralSwapped
    liquidityAssetReturned
    liquidationExcess
    defaultSuffered
    pools {
      poolName
      name
      amount
      companyName
    }
    poolDelegateFunding
    transaction {
      id
      timestamp
    }
  }  
}
```
{% endtab %}

{% tab title="Response" %}
```graphql
{
  "data": {
    "myLoans": [
      {
        "_id": "611dea6cd1f92ab1b779ad44",
        "borrower": {
          "_id": "611d071d6123e9abb3a79e02",
          "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
          "companyName": "Galaxy Trading",
          "companyEmail": "Elbert_Johnson23@hotmail.com",
          "primaryAddress": "278 Boehm Hollow",
          "aboutCompany": "Dicta rerum perferendis expedita libero aspernatur rem quia autem dolores. Eos corrupti eos optio enim. Aut maxime incidunt quia. Voluptatem dolorem assumenda minima consequuntur quis saepe voluptatem excepturi ut.",
          "contactName": "Deven",
          "telegram": "http://t.me/maplefinance",
          "discord": "https://discord.com/invite/maplefinance",
          "website": "https://genoveva.biz",
          "twitter": "@maplefinance"
        },
        "requestAmount": "1000000000000",
        "loanNumber": 21628566,
        "paymentStructure": "INTEREST_ONLY",
        "liquidityAsset": {
          "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
          "symbol": "USDC",
          "decimals": 6,
          "price": null
        },
        "collateralAsset": {
          "address": "0x1fea817089ffe74d50815496d6ae15da6bc1ce41",
          "symbol": "WETH",
          "decimals": 18,
          "price": null
        },
        "collateralRatio": 1000,
        "apr": 1000,
        "purpose": "Demo Loan purpose for infra",
        "termDays": 60,
        "state": "Draft",
        "contractAddress": null,
        "paymentIntervalDays": 30,
        "collateralAmount": null,
        "defaultSuffered": null,
        "amountFunded": null,
        "drawdownAmount": null,
        "claimableAmount": null,
        "principalOwed": null,
        "nextPaymentDue": null,
        "paymentsRemaining": null,
        "numLenders": null,
        "transactionHash": null,
        "collateralSwapped": null,
        "liquidityAssetReturned": null,
        "liquidationExcess": null,
        "poolDelegateFunding": null,
        "transaction": null,
        "pools": null
      }
    ]
  }
}

```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Company {
  _id: String
  owner: String
  companyName: String
  companyEmail: String
  primaryAddress: String
  aboutCompany: String
  contactName: String
  telegram: String
  discord: String
  website: String
  twitter: String
  createdAt: String
  updatedAt: String
}

type Transaction {
  id: String
  timestamp: String
}

type PoolTransaction {
  poolName: String
  name: String
  amount: String
  companyName: String
}

type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type Loan {
  _id: String
  owner: String
  borrower: Company
  requestAmount: String
  loanNumber: Int
  paymentStructure: String
  liquidityAsset: Asset
  collateralAsset: Asset
  collateralRatio: Int
  apr: Int
  purpose: String
  termDays: Int
  state: String
  contractAddress: String
  paymentIntervalDays: Int
  createdAt: String
  updatedAt: String
  collateralAmount: String
  amountFunded: String
  drawdownAmount: String
  drawdownDate: String
  maturityDate: String
  treasuryFees: String
  claimableAmount: String
  principalOwed: String
  nextPayment: String
  nextPaymentDue: String
  paymentsRemaining: String
  numLenders: String
  transactionHash: String
  collateralSwapped: String
  liquidityAssetReturned: String
  liquidationExcess: String
  defaultSuffered: String
  pools: [PoolTransaction]
  poolDelegateFunding: String
  transaction: Transaction
}
```
{% endtab %}
{% endtabs %}

### Create Loan <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
mutation {
  createLoan(
    loan: {
      requestAmount: "1000000000000"
      paymentStructure: "INTEREST_ONLY"
      liquidityAsset: {
        address: "0xa3d55b520f678e7b3c6020439e387b3bcb727198"
        symbol: "USDC"
        decimals: 6
      }
      collateralAsset: {
        address: "0x1fea817089ffe74d50815496d6ae15da6bc1ce41"
        symbol: "WETH"
        decimals: 18
      }
      paymentIntervalDays: 30
      collateralRatio: 1000
      apr: 1000
      purpose: "Base loan to build second structure"
      termDays: 60
    }
  ) {
    _id
    borrower {
      _id
      owner
      companyName
      companyEmail
      primaryAddress
      aboutCompany
      contactName
      telegram
      discord
      website
      twitter
    }
    requestAmount
    loanNumber
    paymentStructure
    liquidityAsset {
      address
      symbol
      decimals
      price
    }
    collateralAsset {
      address
      symbol
      decimals
      price
    }
    collateralRatio
    apr
    purpose
    termDays
    state
    contractAddress
    paymentIntervalDays
    collateralAmount
    defaultSuffered
    amountFunded
    drawdownAmount
    claimableAmount
    principalOwed
    nextPaymentDue
    paymentsRemaining
    numLenders
    transactionHash
    collateralSwapped
    liquidityAssetReturned
    liquidationExcess
    poolDelegateFunding
    transaction {
      id
      timestamp
    }
    pools {
      poolName
      name
      amount
      companyName
    }
  }
}

```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "createLoan": {
      "_id": "611e1e6eaae9f8001210575e",
      "borrower": {
        "_id": "611e1b0daae9f80012105232",
        "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
        "companyName": "Borrower Company 1",
        "companyEmail": "borrowe@democompany.com",
        "primaryAddress": "Basic Address 1",
        "aboutCompany": "Borrower Company is a crypto trading firm",
        "contactName": "Borrower Smith",
        "telegram": null,
        "discord": null,
        "website": "https://borrower.company",
        "twitter": null
      },
      "requestAmount": "1000000000000",
      "loanNumber": 21798117,
      "paymentStructure": "INTEREST_ONLY",
      "liquidityAsset": {
        "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
        "symbol": "USDC",
        "decimals": 6,
        "price": null
      },
      "collateralAsset": {
        "address": "0x1fea817089ffe74d50815496d6ae15da6bc1ce41",
        "symbol": "WETH",
        "decimals": 18,
        "price": null
      },
      "collateralRatio": 1000,
      "apr": 1000,
      "purpose": "Base loan to build second structure",
      "termDays": 60,
      "state": "Draft",
      "contractAddress": null,
      "paymentIntervalDays": 30,
      "collateralAmount": null,
      "defaultSuffered": null,
      "amountFunded": null,
      "drawdownAmount": null,
      "claimableAmount": null,
      "principalOwed": null,
      "nextPaymentDue": null,
      "paymentsRemaining": null,
      "numLenders": null,
      "transactionHash": null,
      "collateralSwapped": null,
      "liquidityAssetReturned": null,
      "liquidationExcess": null,
      "poolDelegateFunding": null,
      "transaction": null,
      "pools": null
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Company {
  _id: String
  owner: String
  companyName: String
  companyEmail: String
  primaryAddress: String
  aboutCompany: String
  contactName: String
  telegram: String
  discord: String
  website: String
  twitter: String
  createdAt: String
  updatedAt: String
}

type Transaction {
  id: String
  timestamp: String
}

type PoolTransaction {
  poolName: String
  name: String
  amount: String
  companyName: String
}

type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type Loan {
  _id: String
  owner: String
  borrower: Company
  requestAmount: String
  loanNumber: Int
  paymentStructure: String
  liquidityAsset: Asset
  collateralAsset: Asset
  collateralRatio: Int
  apr: Int
  purpose: String
  termDays: Int
  state: String
  contractAddress: String
  paymentIntervalDays: Int
  createdAt: String
  updatedAt: String
  collateralAmount: String
  amountFunded: String
  drawdownAmount: String
  drawdownDate: String
  maturityDate: String
  treasuryFees: String
  claimableAmount: String
  principalOwed: String
  nextPayment: String
  nextPaymentDue: String
  paymentsRemaining: String
  numLenders: String
  transactionHash: String
  collateralSwapped: String
  liquidityAssetReturned: String
  liquidationExcess: String
  defaultSuffered: String
  pools: [PoolTransaction]
  poolDelegateFunding: String
  transaction: Transaction
}
```
{% endtab %}
{% endtabs %}

### Update Loan <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
mutation {
  updateLoan(
    _id: "611e1e6eaae9f8001210575e",
    loan: {
      requestAmount: "1000000000000"
      paymentStructure: "INTEREST_ONLY"
      liquidityAsset: {
        address: "0xa3d55b520f678e7b3c6020439e387b3bcb727198"
        symbol: "USDC"
        decimals: 6
      }
      collateralAsset: {
        address: "0x1fea817089ffe74d50815496d6ae15da6bc1ce41"
        symbol: "WETH"
        decimals: 18
      }
      paymentIntervalDays: 30
      collateralRatio: 1000
      apr: 1000
      purpose: "(UPDATED) Base loan to build second structure"
      termDays: 60
    }
  ) {
    _id
    borrower {
      _id
      owner
      companyName
      companyEmail
      primaryAddress
      aboutCompany
      contactName
      telegram
      discord
      website
      twitter
    }
    requestAmount
    loanNumber
    paymentStructure
    liquidityAsset {
      address
      symbol
      decimals
      price
    }
    collateralAsset {
      address
      symbol
      decimals
      price
    }
    collateralRatio
    apr
    purpose
    termDays
    state
    contractAddress
    paymentIntervalDays
    collateralAmount
    defaultSuffered
    amountFunded
    drawdownAmount
    claimableAmount
    principalOwed
    nextPaymentDue
    paymentsRemaining
    numLenders
    transactionHash
    collateralSwapped
    liquidityAssetReturned
    liquidationExcess
    poolDelegateFunding
    transaction {
      id
      timestamp
    }
    pools {
      poolName
      name
      amount
      companyName
    }
  }
}

```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "updateLoan": {
      "_id": "611e1e6eaae9f8001210575e",
      "borrower": {
        "_id": "611e1b0daae9f80012105232",
        "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
        "companyName": "Borrower Company 1",
        "companyEmail": "borrowe@democompany.com",
        "primaryAddress": "Basic Address 1",
        "aboutCompany": "Borrower Company is a crypto trading firm",
        "contactName": "Borrower Smith",
        "telegram": null,
        "discord": null,
        "website": "https://borrower.company",
        "twitter": null
      },
      "requestAmount": "1000000000000",
      "loanNumber": 21798117,
      "paymentStructure": "INTEREST_ONLY",
      "liquidityAsset": {
        "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
        "symbol": "USDC",
        "decimals": 6,
        "price": null
      },
      "collateralAsset": {
        "address": "0x1fea817089ffe74d50815496d6ae15da6bc1ce41",
        "symbol": "WETH",
        "decimals": 18,
        "price": null
      },
      "collateralRatio": 1000,
      "apr": 1000,
      "purpose": "(UPDATED) Base loan to build second structure",
      "termDays": 60,
      "state": "Draft",
      "contractAddress": null,
      "paymentIntervalDays": 30,
      "collateralAmount": null,
      "defaultSuffered": null,
      "amountFunded": null,
      "drawdownAmount": null,
      "claimableAmount": null,
      "principalOwed": null,
      "nextPaymentDue": null,
      "paymentsRemaining": null,
      "numLenders": null,
      "transactionHash": null,
      "collateralSwapped": null,
      "liquidityAssetReturned": null,
      "liquidationExcess": null,
      "poolDelegateFunding": null,
      "transaction": null,
      "pools": null
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Company {
  _id: String
  owner: String
  companyName: String
  companyEmail: String
  primaryAddress: String
  aboutCompany: String
  contactName: String
  telegram: String
  discord: String
  website: String
  twitter: String
  createdAt: String
  updatedAt: String
}

type Transaction {
  id: String
  timestamp: String
}

type PoolTransaction {
  poolName: String
  name: String
  amount: String
  companyName: String
}

type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type Loan {
  _id: String
  owner: String
  borrower: Company
  requestAmount: String
  loanNumber: Int
  paymentStructure: String
  liquidityAsset: Asset
  collateralAsset: Asset
  collateralRatio: Int
  apr: Int
  purpose: String
  termDays: Int
  state: String
  contractAddress: String
  paymentIntervalDays: Int
  createdAt: String
  updatedAt: String
  collateralAmount: String
  amountFunded: String
  drawdownAmount: String
  drawdownDate: String
  maturityDate: String
  treasuryFees: String
  claimableAmount: String
  principalOwed: String
  nextPayment: String
  nextPaymentDue: String
  paymentsRemaining: String
  numLenders: String
  transactionHash: String
  collateralSwapped: String
  liquidityAssetReturned: String
  liquidationExcess: String
  defaultSuffered: String
  pools: [PoolTransaction]
  poolDelegateFunding: String
  transaction: Transaction
}
```
{% endtab %}
{% endtabs %}

### My Pool Delegate <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query MyPoolDelegate {
  myPoolDelegate {
    _id
    owner
    name
    website
    twitter
    linkedIn
    telegram
    aboutBusiness
    allowList
    companyName
  }
}
```
{% endtab %}

{% tab title="Response" %}
```
{
  "data": {
    "myPoolDelegate": {
      "_id": "611d06e56123e9abb3a79ded",
      "owner": "0xa0b30De2833294C200a376B0e8205b9517bF431F",
      "name": "Jake Smith",
      "website": "http://jakesmith.org",
      "twitter": "@JakeSmithVentures",
      "linkedIn": "https://linkedin.com/in/JakeSmithVentures",
      "telegram": "https://t.me/jake_ventures",
      "aboutBusiness": "We are a stock brokerage firm.",
      "allowList": false,
      "companyName": "Jake Smith Ventures Inc"
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
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
```
{% endtab %}
{% endtabs %}

### Create Pool Delegate <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
mutation {
  createPoolDelegate(
    poolDelegate: {
      name: "Pool Delegate demo"
      website: "https://pooldelegate.company"
      twitter: "@pdcompany"
      aboutBusiness: "Basic Pool Delegate doing awesome stuff (UPDATED)"
      companyName: "Pool Delegate Company"
      linkedIn: "https://linkedin.com/in/PoolDelegateCompany"
      telegram: "https://t.me/PoolDelegate"
    }
  ) {
    _id
    owner
    name
    website
    twitter
    linkedIn
    telegram
    aboutBusiness
    allowList
    companyName
  }
}
```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "createPoolDelegate": {
      "_id": "611e1a3faae9f800121050cf",
      "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
      "name": "Pool Delegate demo",
      "website": "https://pooldelegate.company",
      "twitter": "@pdcompany",
      "linkedIn": "https://linkedin.com/in/PoolDelegateCompany",
      "telegram": "https://t.me/PoolDelegate",
      "aboutBusiness": "Basic Pool Delegate doing awesome stuff (UPDATED)",
      "allowList": false,
      "companyName": "Pool Delegate Company"
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
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
```
{% endtab %}
{% endtabs %}

### Update Pool Delegate <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
mutation {
  updatePoolDelegate(
    _id: "611e1a3faae9f800121050cf"
    poolDelegate: {
      name: "Pool Delegate demo"
      website: "https://pooldelegate.company"
      twitter: "@pdcompany"
      aboutBusiness: "Basic Pool Delegate doing awesome stuff (UPDATED)"
      companyName: "Pool Delegate Company"
      linkedIn: "https://linkedin.com/in/PoolDelegateCompany"
      telegram: "https://t.me/PoolDelegate"
    }
  ) {
    _id
    owner
    name
    website
    twitter
    linkedIn
    telegram
    aboutBusiness
    allowList
    companyName
  }
}

```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "updatePoolDelegate": {
      "_id": "611e1a3faae9f800121050cf",
      "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
      "name": "Pool Delegate demo",
      "website": "https://pooldelegate.company",
      "twitter": "@pdcompany",
      "linkedIn": "https://linkedin.com/in/PoolDelegateCompany",
      "telegram": "https://t.me/PoolDelegate",
      "aboutBusiness": "Basic Pool Delegate doing awesome stuff (UPDATED)",
      "allowList": true,
      "companyName": "Pool Delegate Company"
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
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
```
{% endtab %}
{% endtabs %}

### My Pools <a id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query MyPools {
  myPools {
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
      price
    }
    liquidityLocker
    stakeLocker
    liquidityCap
    stakeAsset {
      address
      symbol
      decimals
      price
    }
    stakingFee
    delegateFee
    ongoingFee
    name
    numActiveLoans
    allowedLPs
    allowedSLs
    lpApy
    farmingApy
    stakingApy
    stakeRewardsApy
    balance
    liquidity
    lockupPeriod
    stake
    currentLoaned
    totalInterestEarned
    totalFees
    stakeLockerFees
    poolDelegateFees
    myInterestEarned
    myLiquidity
    myBalance
    transactionHash
    defaultsTotal
    liquidityAssetRecoveredTotal
    poolTokenTotalSupply
    totalLoaned
    totalPrincipalRepaid
    symbol
    poolPositions {
      id
      poolTokenBalance
      poolTokensStaked
      rewardPaid
      custodyAllowance
      depositDate
      withdrawCooldown
      stake
      stakeLockerTokensStaked
      stakeRewardPaid
      stakeCustodyAllowance
      stakeDate
      unstakeCooldown
    }
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
```
{
  "data": {
    "myPools": [
      {
        "_id": "611d06e56123e9abb3a79df6",
        "poolDelegate": {
          "_id": "611d06e56123e9abb3a79ded",
          "owner": "0xa0b30De2833294C200a376B0e8205b9517bF431F",
          "name": "Jake Smith",
          "website": "http://jakesmith.org",
          "twitter": "@JakeSmithVentures",
          "linkedIn": "https://linkedin.com/in/JakeSmithVentures",
          "telegram": "https://t.me/jake_ventures",
          "aboutBusiness": "We are a stock brokerage firm.",
          "allowList": false,
          "companyName": "Jake Smith Ventures Inc"
        },
        "poolName": "Emile Pool",
        "contractAddress": null,
        "strategy": "Quasi enim possimus dolorum.",
        "createdAt": "2021-08-18T13:11:01.496Z",
        "updatedAt": "2021-08-18T13:11:01.607Z",
        "state": "Draft",
        "liquidityAsset": {
          "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
          "symbol": "USDC",
          "decimals": 6,
          "price": null
        },
        "liquidityLocker": null,
        "stakeLocker": null,
        "liquidityCap": "100000000",
        "stakeAsset": {
          "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
          "symbol": "USDC",
          "decimals": 6,
          "price": null
        },
        "stakingFee": "7938",
        "delegateFee": "3538",
        "ongoingFee": null,
        "name": null,
        "numActiveLoans": null,
        "allowedLPs": null,
        "allowedSLs": null,
        "lpApy": null,
        "farmingApy": null,
        "stakingApy": null,
        "stakeRewardsApy": null,
        "balance": null,
        "liquidity": null,
        "lockupPeriod": null,
        "stake": null,
        "currentLoaned": null,
        "totalInterestEarned": null,
        "totalFees": null,
        "stakeLockerFees": null,
        "poolDelegateFees": null,
        "myInterestEarned": null,
        "myLiquidity": null,
        "myBalance": null,
        "transactionHash": null,
        "defaultsTotal": null,
        "liquidityAssetRecoveredTotal": null,
        "poolTokenTotalSupply": null,
        "totalLoaned": null,
        "totalPrincipalRepaid": null,
        "symbol": null,
        "poolPositions": null,
        "transaction": null,
        "mplRewards": null,
        "totalPoolTokensStaked": null,
        "stakeRewards": null,
        "totalStakeLockerTokensStaked": null,
        "stakeLockerLiquidity": null,
        "stakeLockupPeriod": null,
        "openToPublic": null,
        "stakeLockerOpenToPublic": null
      },
      {
        "_id": "611d07376123e9abb3a79e17",
        "poolDelegate": {
          "_id": "611d06e56123e9abb3a79ded",
          "owner": "0xa0b30De2833294C200a376B0e8205b9517bF431F",
          "name": "Jake Smith",
          "website": "http://jakesmith.org",
          "twitter": "@JakeSmithVentures",
          "linkedIn": "https://linkedin.com/in/JakeSmithVentures",
          "telegram": "https://t.me/jake_ventures",
          "aboutBusiness": "We are a stock brokerage firm.",
          "allowList": false,
          "companyName": "Jake Smith Ventures Inc"
        },
        "poolName": "Giovanny Pool",
        "contractAddress": null,
        "strategy": "Repellat perferendis omnis voluptatum mollitia iure.",
        "createdAt": "2021-08-18T13:12:23.065Z",
        "updatedAt": "2021-08-18T13:12:23.065Z",
        "state": "Draft",
        "liquidityAsset": {
          "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
          "symbol": "USDC",
          "decimals": 6,
          "price": null
        },
        "liquidityLocker": null,
        "stakeLocker": null,
        "liquidityCap": "739869694348",
        "stakeAsset": {
          "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
          "symbol": "USDC",
          "decimals": 6,
          "price": null
        },
        "stakingFee": "1605",
        "delegateFee": "9865",
        "ongoingFee": null,
        "name": null,
        "numActiveLoans": null,
        "allowedLPs": null,
        "allowedSLs": null,
        "lpApy": null,
        "farmingApy": null,
        "stakingApy": null,
        "stakeRewardsApy": null,
        "balance": null,
        "liquidity": null,
        "lockupPeriod": null,
        "stake": null,
        "currentLoaned": null,
        "totalInterestEarned": null,
        "totalFees": null,
        "stakeLockerFees": null,
        "poolDelegateFees": null,
        "myInterestEarned": null,
        "myLiquidity": null,
        "myBalance": null,
        "transactionHash": null,
        "defaultsTotal": null,
        "liquidityAssetRecoveredTotal": null,
        "poolTokenTotalSupply": null,
        "totalLoaned": null,
        "totalPrincipalRepaid": null,
        "symbol": null,
        "poolPositions": null,
        "transaction": null,
        "mplRewards": null,
        "totalPoolTokensStaked": null,
        "stakeRewards": null,
        "totalStakeLockerTokensStaked": null,
        "stakeLockerLiquidity": null,
        "stakeLockupPeriod": null,
        "openToPublic": null,
        "stakeLockerOpenToPublic": null
      }
    ]
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
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

type Transaction {
  id: String
  timestamp: String
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

type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type MplRewards {
  id: String
  periodFinish: String
  reward: String
  rewardRate: String
  rewardsDuration: String
  paused: Boolean
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

### Create Pool

{% tabs %}
{% tab title="Request" %}
```graphql
mutation CreatePool {
  createPool(
    pool: {
      poolName: "Demo Pool Two"
      strategy: "This is a demo pool explaining about what is it for"
      liquidityAsset: {
        address: "0xa3d55b520f678e7b3c6020439e387b3bcb727198"
        symbol: "USDC"
        decimals: 6
      }
      stakeAsset: {
        address: "0x892689147ab1ccf60237696de6a028b8959561cb"
        symbol: "BPT"
        decimals: 18
      }
      liquidityCap: "10000000000000"
      delegateFee: 2000
      stakingFee: 200
    }
  ) {
    _id
    poolDelegate {
      _id
      owner
      name
      website
      twitter
      linkedIn
      telegram
      aboutBusiness
      allowList
      companyName
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
      price
    }
    liquidityLocker
    stakeLocker
    liquidityCap
    stakeAsset {
      address
      symbol
      decimals
      price
    }
    stakingFee
    delegateFee
    ongoingFee
    name
    numActiveLoans
    lpApy
    allowedLPs
    allowedSLs
    lockupPeriod
    farmingApy
    stakingApy
    stakeRewardsApy
    balance
    totalFees
    stakeLockerFees
    poolDelegateFees
    liquidity
    stake
    currentLoaned
    totalInterestEarned
    myInterestEarned
    myLiquidity
    myBalance
    defaultsTotal
    liquidityAssetRecoveredTotal
    transactionHash
    stakeLockerLiquidity
    stakeLockupPeriod
    poolPositions {
      id
      poolTokenBalance
      poolTokensStaked
      rewardPaid
      custodyAllowance
      depositDate
      withdrawCooldown
      stake
      stakeLockerTokensStaked
      stakeRewardPaid
      stakeCustodyAllowance
      stakeDate
      unstakeCooldown
    }
    mplRewards {
      id
      periodFinish
      reward
      rewardRate
      rewardsDuration
      paused
    }
    stakeRewards {
      id
      periodFinish
      reward
      rewardRate
      rewardsDuration
      paused
    }
    transaction {
      id
      timestamp
    }
    openToPublic
    stakeLockerOpenToPublic
  }
}

```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "createPool": {
      "_id": "611e2e47aae9f80012105a62",
      "poolDelegate": {
        "_id": "611e1a3faae9f800121050cf",
        "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
        "name": "Pool Delegate demo",
        "website": "https://pooldelegate.company",
        "twitter": "@pdcompany",
        "linkedIn": "https://linkedin.com/in/PoolDelegateCompany",
        "telegram": "https://t.me/PoolDelegate",
        "aboutBusiness": "Basic Pool Delegate doing awesome stuff (UPDATED)",
        "allowList": true,
        "companyName": "Pool Delegate Company"
      },
      "poolName": "Demo Pool Two",
      "contractAddress": null,
      "strategy": "This is a demo pool explaining about what is it for",
      "createdAt": "1629367879189",
      "updatedAt": "1629367879189",
      "state": "Draft",
      "liquidityAsset": {
        "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
        "symbol": "USDC",
        "decimals": 6,
        "price": null
      },
      "liquidityLocker": null,
      "stakeLocker": null,
      "liquidityCap": "10000000000000",
      "stakeAsset": {
        "address": "0x892689147ab1ccf60237696de6a028b8959561cb",
        "symbol": "BPT",
        "decimals": 18,
        "price": null
      },
      "stakingFee": "200",
      "delegateFee": "2000",
      "ongoingFee": null,
      "name": null,
      "numActiveLoans": null,
      "lpApy": null,
      "allowedLPs": null,
      "allowedSLs": null,
      "lockupPeriod": null,
      "farmingApy": null,
      "stakingApy": null,
      "stakeRewardsApy": null,
      "balance": null,
      "totalFees": null,
      "stakeLockerFees": null,
      "poolDelegateFees": null,
      "liquidity": null,
      "stake": null,
      "currentLoaned": null,
      "totalInterestEarned": null,
      "myInterestEarned": null,
      "myLiquidity": null,
      "myBalance": null,
      "defaultsTotal": null,
      "liquidityAssetRecoveredTotal": null,
      "transactionHash": null,
      "stakeLockerLiquidity": null,
      "stakeLockupPeriod": null,
      "poolPositions": null,
      "mplRewards": null,
      "stakeRewards": null,
      "transaction": null,
      "openToPublic": null,
      "stakeLockerOpenToPublic": null
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
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

type Transaction {
  id: String
  timestamp: String
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

type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type MplRewards {
  id: String
  periodFinish: String
  reward: String
  rewardRate: String
  rewardsDuration: String
  paused: Boolean
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

### Update Pool

{% tabs %}
{% tab title="Request" %}
```graphql
mutation {
  updatePool(
    _id: "611e2e47aae9f80012105a62",
    pool: {
      poolName: "Demo Pool Two UPDATED"
      strategy: "This is a demo pool explaining about what is it for"
      liquidityAsset: {
        address: "0xa3d55b520f678e7b3c6020439e387b3bcb727198"
        symbol: "USDC"
        decimals: 6
      }
      stakeAsset: {
        address: "0x892689147ab1ccf60237696de6a028b8959561cb"
        symbol: "BPT"
        decimals: 18
      }
      liquidityCap: "10000000000000"
      delegateFee: 2000
      stakingFee: 200
    }
  ) {
    _id
    poolDelegate {
      _id
      owner
      name
      website
      twitter
      linkedIn
      telegram
      aboutBusiness
      allowList
      companyName
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
      price
    }
    liquidityLocker
    stakeLocker
    liquidityCap
    stakeAsset {
      address
      symbol
      decimals
      price
    }
    stakingFee
    delegateFee
    ongoingFee
    name
    numActiveLoans
    lpApy
    allowedLPs
    allowedSLs
    lockupPeriod
    farmingApy
    stakingApy
    stakeRewardsApy
    balance
    totalFees
    stakeLockerFees
    poolDelegateFees
    liquidity
    stake
    currentLoaned
    totalInterestEarned
    myInterestEarned
    myLiquidity
    myBalance
    defaultsTotal
    liquidityAssetRecoveredTotal
    transactionHash
    stakeLockerLiquidity
    stakeLockupPeriod
    poolPositions {
      id
      poolTokenBalance
      poolTokensStaked
      rewardPaid
      custodyAllowance
      depositDate
      withdrawCooldown
      stake
      stakeLockerTokensStaked
      stakeRewardPaid
      stakeCustodyAllowance
      stakeDate
      unstakeCooldown
    }
    mplRewards {
      id
      periodFinish
      reward
      rewardRate
      rewardsDuration
      paused
    }
    stakeRewards {
      id
      periodFinish
      reward
      rewardRate
      rewardsDuration
      paused
    }
    transaction {
      id
      timestamp
    }
    openToPublic
    stakeLockerOpenToPublic
  }
}

```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "updatePool": {
      "_id": "611e2e47aae9f80012105a62",
      "poolDelegate": {
        "_id": "611e1a3faae9f800121050cf",
        "owner": null,
        "name": null,
        "website": null,
        "twitter": null,
        "linkedIn": null,
        "telegram": null,
        "aboutBusiness": null,
        "allowList": null,
        "companyName": null
      },
      "poolName": "Demo Pool Two UPDATED",
      "contractAddress": null,
      "strategy": "This is a demo pool explaining about what is it for",
      "createdAt": "1629367879189",
      "updatedAt": "1629367930318",
      "state": "Draft",
      "liquidityAsset": {
        "address": "0xa3d55b520f678e7b3c6020439e387b3bcb727198",
        "symbol": "USDC",
        "decimals": 6,
        "price": null
      },
      "liquidityLocker": null,
      "stakeLocker": null,
      "liquidityCap": "10000000000000",
      "stakeAsset": {
        "address": "0x892689147ab1ccf60237696de6a028b8959561cb",
        "symbol": "BPT",
        "decimals": 18,
        "price": null
      },
      "stakingFee": "200",
      "delegateFee": "2000",
      "ongoingFee": null,
      "name": null,
      "numActiveLoans": null,
      "lpApy": null,
      "allowedLPs": null,
      "allowedSLs": null,
      "lockupPeriod": null,
      "farmingApy": null,
      "stakingApy": null,
      "stakeRewardsApy": null,
      "balance": null,
      "totalFees": null,
      "stakeLockerFees": null,
      "poolDelegateFees": null,
      "liquidity": null,
      "stake": null,
      "currentLoaned": null,
      "totalInterestEarned": null,
      "myInterestEarned": null,
      "myLiquidity": null,
      "myBalance": null,
      "defaultsTotal": null,
      "liquidityAssetRecoveredTotal": null,
      "transactionHash": null,
      "stakeLockerLiquidity": null,
      "stakeLockupPeriod": null,
      "poolPositions": null,
      "mplRewards": null,
      "stakeRewards": null,
      "transaction": null,
      "openToPublic": null,
      "stakeLockerOpenToPublic": null
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
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

type Transaction {
  id: String
  timestamp: String
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

type Asset {
  address: String
  symbol: String
  decimals: Int
  price: Float
}

type MplRewards {
  id: String
  periodFinish: String
  reward: String
  rewardRate: String
  rewardsDuration: String
  paused: Boolean
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

### My Company

{% tabs %}
{% tab title="Request" %}
```graphql
query MyCompany {
  myCompany {
    _id
    owner
    companyName
    companyEmail
    primaryAddress
    aboutCompany
    contactName
    telegram
    discord
    website
    twitter
    createdAt
    updatedAt
  } 
}
```
{% endtab %}

{% tab title="Response" %}
```
{
  "data": {
    "myCompany": {
      "_id": "611e1b0daae9f80012105232",
      "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
      "companyName": "Borrower Company 1",
      "companyEmail": "borrowe@democompany.com",
      "primaryAddress": "Basic Address 1",
      "aboutCompany": "Borrower Company is a crypto trading firm",
      "contactName": "Borrower Smith",
      "telegram": null,
      "discord": null,
      "website": "https://borrower.company",
      "twitter": null,
      "createdAt": "1629362957752",
      "updatedAt": "1629362957752"
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```
type Company {
  _id: String
  owner: String
  companyName: String
  companyEmail: String
  primaryAddress: String
  aboutCompany: String
  contactName: String
  telegram: String
  discord: String
  website: String
  twitter: String
  createdAt: String
  updatedAt: String
}
```
{% endtab %}
{% endtabs %}

### Create Company

{% tabs %}
{% tab title="Request" %}
```graphql
mutation CreateCompany {
  createCompany(
    company: {
      companyName: "Borrower Company 2"
      companyEmail: "borrowe@democompany.com"
      primaryAddress: "Basic Address 2"
      contactName: "Borrower Smith"
      website: "https://borrower.companies"
      aboutCompany: "Borrower 2 Company is a crypto trading firm"
    }
  ) {
    _id
    owner
    companyName
    companyEmail
    primaryAddress
    aboutCompany
    contactName
    telegram
    discord
    website
    twitter
  }
}

```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "createCompany": {
      "_id": "611e1b0daae9f80012105232",
      "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
      "companyName": "Borrower Company 1",
      "companyEmail": "borrowe@democompany.com",
      "primaryAddress": "Basic Address 1",
      "aboutCompany": "Borrower Company is a crypto trading firm",
      "contactName": "Borrower Smith",
      "telegram": null,
      "discord": null,
      "website": "https://borrower.company",
      "twitter": null
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Company {
  _id: String
  owner: String
  companyName: String
  companyEmail: String
  primaryAddress: String
  aboutCompany: String
  contactName: String
  telegram: String
  discord: String
  website: String
  twitter: String
  createdAt: String
  updatedAt: String
}
```
{% endtab %}
{% endtabs %}

### Update Company

{% tabs %}
{% tab title="Request" %}
```graphql
mutation UpdateCompany {
  updateCompany(
    _id: "611e1b0daae9f80012105232"
    company: {
      companyName: "Borrower Company 1"
      companyEmail: "borrowe@democompany.com"
      primaryAddress: "Basic Address 1"
      contactName: "Borrower Smith"
      website: "https://borrower.company"
      aboutCompany: "Borrower Company is a crypto trading firm (UPDATED)"
    }
  ) {
    _id
    owner
    companyName
    companyEmail
    primaryAddress
    aboutCompany
    contactName
    telegram
    discord
    website
    twitter
  }
}

```
{% endtab %}

{% tab title="Response" %}
```typescript
{
  "data": {
    "updateCompany": {
      "_id": "611e1b0daae9f80012105232",
      "owner": "0xa0b30De2833294C200a376B0e8205b9517bF021F",
      "companyName": "Borrower Company 1",
      "companyEmail": "borrowe@democompany.com",
      "primaryAddress": "Basic Address 1",
      "aboutCompany": "Borrower Company is a crypto trading firm (UPDATED)",
      "contactName": "Borrower Smith",
      "telegram": null,
      "discord": null,
      "website": "https://borrower.company",
      "twitter": null
    }
  }
}
```
{% endtab %}

{% tab title="Entities" %}
```graphql
type Company {
  _id: String
  owner: String
  companyName: String
  companyEmail: String
  primaryAddress: String
  aboutCompany: String
  contactName: String
  telegram: String
  discord: String
  website: String
  twitter: String
  createdAt: String
  updatedAt: String
}
```
{% endtab %}
{% endtabs %}

