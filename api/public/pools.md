# Pools

Maple protocol pool data.

### Pools <a href="#maple-globals" id="maple-globals"></a>

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
        deckFileUrl
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
          "_id": "6225d66c1ec0bc0018a4db2a",
          "poolDelegate": {
            "_id": "6225d58970d4d9d5b48d703c",
            "owner": "0x990d11977378D4610776e6646b2cAAe543Ea4EDA",
            "name": "Balder Bomans",
            "website": "https://www.maven11.com/",
            "telegram": null,
            "twitter": "@maven11capital",
            "linkedIn": "https://www.linkedin.com/company/maven11",
            "companyName": "Maven 11 Capital",
            "aboutBusiness": "Maven 11 is an Amsterdam-founded blockchain and crypto asset investment firm that invests in and supports its ventures globally. As a Pool Delegate on Maple, our role is to assess the creditworthiness of borrowers, issue and underwrite loans, and manage interest and principal payments. This rigorous process protects the financial interest of lenders, and the reputation of all parties. To ensure financial alignment with liquidity providers, Maven 11 provides a substantial portion of pool cover, utilized as first-loss capital in case of default. \n\nTo operate at the highest standard of portfolio and risk management, an expert team from premier European financial institutions manage this pool. With backgrounds in leveraged finance, securities trading and auditing, together we ensure the pool strategy is adhered to, yields are optimised and value is created.",
            "allowList": true,
            "deckFileUrl": "https://downloads.maple.loans/pool-delegate/maven-11-capital-deck.pdf",
            "createdAt": null,
            "updatedAt": null
          },
          "poolName": "Maven 11 wETH Pool",
          "contractAddress": "0x1a066b0109545455bc771e49e6edef6303cb0a93",
          "strategy": "The strategy of this pool is to lend to borrowers with capital intensive businesses and a strong balance sheet. Maven 11 will primarily lend capital to borrowers that we already have a relationship with from operating a USDC denominated pool since July 2021. We also welcome new borrowers, and the strategy here is to start with small loans, that grow in size as the borrowers’ credit history builds. \n\nCreditworthiness is assessed based on balance sheet, recent profitability, leverage, liquidity risk, internal (risk) control systems, expertise and track record of the team, and more. The pool is wETH denominated. Collateralization ratios can vary between 0 - 100%.\n\nThe pool is open to deposits of wETH from all investors.",
          "createdAt": "2022-03-07T09:54:52.544Z",
          "updatedAt": "2022-03-07T09:57:02.823Z",
          "state": "Finalized",
          "liquidityAsset": {
            "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
            "symbol": "WETH",
            "decimals": 18
          },
          "liquidityLocker": "0x77fb4797db0c418967ba155dcf344aadeafcb250",
          "stakeLocker": "0xd5deeb06859369e42cf1906408ed6cb249e0e002",
          "liquidityCap": "14690000000000000000000",
          "stakeAsset": {
            "address": "0x30b705bfa64be9ae395bd9238efc63e9f5f8d1cc",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "1000",
          "delegateFee": "1000",
          "ongoingFee": "2000",
          "name": "Maple Pool Token",
          "numActiveLoans": "7",
          "allowedLPs": [
            "0x186cf5714316f47bc59e30a850615a3f938d7d79",
            "0xd4f072b18c7a31d50bbf1df729b68e9ace7bc0d9",
            "0xa0f75491720835b36edc92d06ddc468d201e9b73",
            "0xd37d05655d8974e3d12e23cc1be06aaf4d4aece1",
            "0xfacf46ea1e0ad2681103e726f64cfc503e9da5d6",
            "0xcc7c071d6000f98ebd009de30e5e9c387e501276",
            "0x99121c80dca4da906bccb1cc04cdd70c6ceac2ec",
            "0x73f7261cf493105202f8dcbb11c126a65703da55",
            "0x9928c2751aff664cec0a100f36bf2a31c5dcd8c7",
            "0x31c039383d787457b75d185d820d4a37ab80dad2"
          ],
          "allowedSLs": [
            "0x31c039383d787457b75d185d820d4a37ab80dad2"
          ],
          "lpApy": "487",
          "lendingApy": "390",
          "stakingApy": "2435",
          "farmingApy": "476",
          "stakeRewardsApy": "0",
          "balance": "14719791232876712323920",
          "liquidity": "10791232876712323920",
          "lockupPeriod": "7776000",
          "stake": "250066950135129777852187",
          "currentLoaned": "14709000000000000000000",
          "totalLoanOriginations": "14709000000000000000000",
          "totalInterestEarned": "29791232876712323920",
          "totalFees": "21984509589041095887",
          "stakeLockerFees": "3723904109589040490",
          "poolDelegateFees": "3723904109589040490",
          "numPositions": "37",
          "txCount": "93",
          "transactionHash": "0xfff80d0a6f562dd9e3024200344f8a762d89a17f58a99b35e9b5341aac3be2cd",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "14690000000000000000000",
          "totalLoaned": "14709000000000000000000",
          "totalPrincipalRepaid": "0",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0xfff80d0a6f562dd9e3024200344f8a762d89a17f58a99b35e9b5341aac3be2cd",
            "timestamp": "1646646985"
          },
          "mplRewards": {
            "id": "0x0a76c7913c94f2af16958fbdf9b4cf0bbdb159d8",
            "periodFinish": "1652209105",
            "reward": "2937000000000000000000",
            "rewardRate": "1133101851851851",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalPoolTokensStaked": "14689950000000000000000",
          "stakeRewards": {
            "id": "0x0000000000000000000000000000000000000000",
            "periodFinish": "0",
            "reward": "0",
            "rewardRate": "0",
            "rewardsDuration": "0",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "0",
          "stakeLockerLiquidity": "3723904109589040490",
          "stakeLockupPeriod": "15552000",
          "openToPublic": true,
          "stakeLockerOpenToPublic": false
        },
        {
          "_id": "6213d5a70f71280018713433",
          "poolDelegate": {
            "_id": "6213d41e5f22d3442939a825",
            "owner": "0x6A3528677e598B47952749b08469CE806C2524e7",
            "name": "Connor Nolan",
            "website": "https://celsius.network",
            "telegram": null,
            "twitter": "@celsiusnetwork",
            "linkedIn": null,
            "companyName": "Celsius Network",
            "aboutBusiness": "Founded in 2017, Celsius Network is the leading cryptocurrency lending and borrowing platform. Celsius helps over a million customers worldwide to find the path towards financial independence through a compounding yield service and instant low-cost loans accessible via a web and mobile app. Built on the belief that financial services should only do what is in the best interest of the customers and community, Celsius is a blockchain-based fee-free platform where membership provides access to curated financial services that are not available through traditional financial institutions. For additional information please visit https://www.celsius.network.",
            "allowList": true,
            "deckFileUrl": null,
            "createdAt": null,
            "updatedAt": null
          },
          "poolName": "Celsius wETH Pool",
          "contractAddress": "0xa1fe1b5fc23c2dab0c28d4cc09021014f30be8f1",
          "strategy": "The strategy of this Pool is to lend wETH to the most creditworthy firms within the crypto ecosystem vetted by an experienced team of dedicated Credit Officers. As a leading liquidity provider this pool will initially consist solely of Celsius’ own capital. Celsius is proud to partner with Maple and utilize its platform to expand its product offerings while maintaining industry leading credit underwriting standards. \n\nLoans in the pool target collateralization rates of 0-100% with competitive market rates of returns.",
          "createdAt": "2022-02-21T18:10:47.738Z",
          "updatedAt": "2022-02-21T18:12:54.860Z",
          "state": "Finalized",
          "liquidityAsset": {
            "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
            "symbol": "WETH",
            "decimals": 18
          },
          "liquidityLocker": "0x43a8c9e47cef561b92a93a144e50c44a308dc889",
          "stakeLocker": "0xb46be5bb19eb95b5a2b4d3b6276a2e703d6e4082",
          "liquidityCap": "20000000000000000000000",
          "stakeAsset": {
            "address": "0x30b705bfa64be9ae395bd9238efc63e9f5f8d1cc",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "0",
          "delegateFee": "0",
          "ongoingFee": "0",
          "name": "Maple Pool Token",
          "numActiveLoans": "4",
          "allowedLPs": [
            "0x6a3528677e598b47952749b08469ce806c2524e7"
          ],
          "allowedSLs": [],
          "lpApy": "374",
          "lendingApy": "374",
          "stakingApy": "0",
          "farmingApy": "0",
          "stakeRewardsApy": "0",
          "balance": "11296880000000000000001",
          "liquidity": "6880000000000000001",
          "lockupPeriod": "15552000",
          "stake": "58823500000000000000000",
          "currentLoaned": "11290000000000000000000",
          "totalLoanOriginations": "11290000000000000000000",
          "totalInterestEarned": "34778630136986297892",
          "totalFees": "15260104109589041094",
          "stakeLockerFees": "0",
          "poolDelegateFees": "0",
          "numPositions": "1",
          "txCount": "6",
          "transactionHash": "0x4d31849c372e25c599cc809f5502a5defac439da8484110117c4288d39f0eae8",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "11296880000000000000000",
          "totalLoaned": "11290000000000000000000",
          "totalPrincipalRepaid": "0",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x4d31849c372e25c599cc809f5502a5defac439da8484110117c4288d39f0eae8",
            "timestamp": "1645467144"
          },
          "mplRewards": {
            "id": "0x0000000000000000000000000000000000000000",
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
          "stakeLockerLiquidity": "0",
          "stakeLockupPeriod": "15552000",
          "openToPublic": false,
          "stakeLockerOpenToPublic": false
        },
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
            "aboutBusiness": "Orthogonal Trading is a multi-strategy cryptocurrency trading firm focused solely on the digital asset markets. Orthogonal Trading were the first Pool Delegate to launch a lending business on Maple and currently operate two pools. The team bring experience in portfolio and risk management, auditing, quantitative trading, and blockchain system development from Goldman Sachs, Morgan Stanley, B2C2 and more.  \n\nAs a Pool Delegate on Maple, our role is to assess the creditworthiness of borrowers, issue and underwrite loans, and manage interest and principal payments.",
            "allowList": true,
            "deckFileUrl": "https://downloads.maple.loans/pool-delegate/orthogonal-trading-deck.pdf",
            "createdAt": "2021-05-19T03:11:57.680Z",
            "updatedAt": "2021-05-19T03:11:57.680Z"
          },
          "poolName": "Orthogonal Trading - USDC01",
          "contractAddress": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27",
          "strategy": "The strategy of this Pool is to target industry-leading funds and prop trading desks. The focus is on mitigating risk by lending to market-makers and arbitrage traders to avoid taking directional risk on the prices of crypto assets. Borrowers' creditworthiness is assessed based on how they manage leverage, liquidity risk, operational risk controls, management's level of experience, their balance sheet strength and recent financial performance. \n\nLoans in the pool will generally vary between 0 and 50% collateralization and target a weighted average APY of low-to-mid teens in line with the market for stablecoin lending.\n\nThe pool is open to deposits of USDC from all investors.",
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
          "liquidityCap": "450000000000000",
          "stakeAsset": {
            "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "1000",
          "delegateFee": "1000",
          "ongoingFee": "2000",
          "name": "Maple Pool Token",
          "numActiveLoans": "29",
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
          "lpApy": "908",
          "lendingApy": "646",
          "stakingApy": "1589",
          "farmingApy": "682",
          "stakeRewardsApy": "0",
          "balance": "353654435880368",
          "liquidity": "47154235880368",
          "lockupPeriod": "7776000",
          "stake": "796090754990613559783",
          "currentLoaned": "306500200000000",
          "totalLoanOriginations": "455000400000000",
          "totalInterestEarned": "8942352559010",
          "totalFees": "1001188070768",
          "stakeLockerFees": "1117794069754",
          "poolDelegateFees": "1810294319712",
          "numPositions": "442",
          "txCount": "3198",
          "transactionHash": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "350118141921209000000000000",
          "totalLoaned": "455000400000000",
          "totalPrincipalRepaid": "148500200000000",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
            "timestamp": "1621394109"
          },
          "mplRewards": {
            "id": "0x7869d7a3b074b5fa484dc04798e254c9c06a5e90",
            "periodFinish": "1651073745",
            "reward": "31347000000000000000000",
            "rewardRate": "12343679231592221",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalPoolTokensStaked": "341375074380755000000000000",
          "stakeRewards": {
            "id": "0xf9d4d5a018d91e9bccc1e35ea78fcfecf4c5cbca",
            "periodFinish": "1644041537",
            "reward": "3840000000000000000000",
            "rewardRate": "1481481481481481",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "538614081474488133321",
          "stakeLockerLiquidity": "713315491638",
          "stakeLockupPeriod": "2592000",
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
            "aboutBusiness": "Maven 11 is an Amsterdam-founded blockchain and crypto asset investment firm that invests in and supports its ventures globally. As a Pool Delegate on Maple, our role is to assess the creditworthiness of borrowers, issue and underwrite loans, and manage interest and principal payments. This rigorous process protects the financial interest of liquidity providers, and the reputation of all parties. To ensure financial alignment with liquidity providers, Maven 11 provides a substantial portion of pool cover, utilized as first-loss capital in case of default. \n\nTo operate at the highest standard of portfolio and risk management, an expert team from premier European financial institutions manage this pool. With backgrounds in leveraged finance, securities trading and auditing, together we ensure the pool strategy is adhered to, yields are optimised and value is created.",
            "allowList": true,
            "deckFileUrl": "https://downloads.maple.loans/pool-delegate/maven-11-capital-deck.pdf",
            "createdAt": "2021-07-06T05:12:56.335Z",
            "updatedAt": "2021-07-06T05:12:56.335Z"
          },
          "poolName": "Maven 11 - USDC 01",
          "contractAddress": "0x6f6c8013f639979c84b756c7fc1500eb5af18dc4",
          "strategy": "The strategy of this pool is to lend to borrowers with capital intensive businesses and a strong balance sheet. Maven 11 lend to creditworthy borrowers, starting with small loans, that grow in size as the borrowers’ credit history builds. \n\nCreditworthiness is assessed based on balance sheet, recent profitability, leverage, liquidity risk, internal (risk) control systems, expertise and track record of the team, and more. The pool is USDC denominated. Collateralization ratios can vary between 0 - 100%.\n\nThe pool is open to deposits of USDC from all investors.",
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
          "liquidityCap": "350000000000000",
          "stakeAsset": {
            "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
            "symbol": "BPT",
            "decimals": 18
          },
          "stakingFee": "1000",
          "delegateFee": "1000",
          "ongoingFee": "2000",
          "name": "Maple Pool Token",
          "numActiveLoans": "34",
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
          "lpApy": "877",
          "lendingApy": "675",
          "stakingApy": "1583",
          "farmingApy": "620",
          "stakeRewardsApy": "0",
          "balance": "285259821076875",
          "liquidity": "17609821076873",
          "lockupPeriod": "7776000",
          "stake": "647968949523586213610",
          "currentLoaned": "267650000000002",
          "totalLoanOriginations": "393750000000000",
          "totalInterestEarned": "6424015890486",
          "totalFees": "818306643785",
          "stakeLockerFees": "803001986206",
          "poolDelegateFees": "1311376986169",
          "numPositions": "518",
          "txCount": "3310",
          "transactionHash": "0x8c80af8e064aab3fd9b8c94502afca11bbb5d75a73482cac5015ce0cfaf34786",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "282809830469676000000000000",
          "totalLoaned": "401750000000000",
          "totalPrincipalRepaid": "134099999999998",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x8c80af8e064aab3fd9b8c94502afca11bbb5d75a73482cac5015ce0cfaf34786",
            "timestamp": "1625548646"
          },
          "mplRewards": {
            "id": "0x7c57bf654bc16b0c9080f4f75ff62876f50b8259",
            "periodFinish": "1651938977",
            "reward": "22982000000000000000000",
            "rewardRate": "8921947608668381",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalPoolTokensStaked": "271243373642313000000000000",
          "stakeRewards": {
            "id": "0xe5a1cb65e7a608e778b3ccb02f7b2dfefee783b4",
            "periodFinish": "1644042099",
            "reward": "2820000000000000000000",
            "rewardRate": "1087962962962962",
            "rewardsDuration": "2592000",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "643930233904086221026",
          "stakeLockerLiquidity": "483013812477",
          "stakeLockupPeriod": "2592000",
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
            "aboutBusiness": "Orthogonal Trading is a multi-strategy cryptocurrency trading firm focused solely on the digital asset markets. Orthogonal Trading were the first Pool Delegate to launch a lending business on Maple and operate two pools. The team bring experience in portfolio and risk management, auditing, quantitative trading, and blockchain system development from Goldman Sachs, Morgan Stanley, B2C2 and more.  \n\nAs a Pool Delegate of this syndicated loan pool for Alameda Trading, our role is to onboard accredited non-US institutions that pass through KYC-AML procedures as liquidity providers.\n\nOrthogonal Trading, issue and underwrite loans to Alameda Research, and manage interest and principal payments.",
            "allowList": true,
            "deckFileUrl": "https://downloads.maple.loans/pool-delegate/alameda-deck.pdf",
            "createdAt": "2021-07-06T05:12:56.335Z",
            "updatedAt": "2021-07-06T05:12:56.335Z"
          },
          "poolName": "Alameda Research - USDC",
          "contractAddress": "0x3e701d29fcb8747b5c3f88649397d88fff9bd3e9",
          "strategy": "Alameda Research are the sole borrower from this pool and will utilize capital deposited to facilitate their market making business. Launched in November 2021, this permissioned lending pool plans to extend $1BN in loans to Alameda over 12 months.\n\nLiquidity providers to this pool must be accredited non-US institutions, and pass through KYC-AML procedures. Loans are issued to Alameda in tranches. Applications to deposit liquidity are always open, enquire via https://maple.finance/contact.",
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
          "liquidityCap": "150000000000000",
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
            "0x4b9fb94731e733f4293a4d45c3314e955dfa185d",
            "0x79a674901ad189feb00bc0caadefc8ba3f5a4176",
            "0xb6996b02f4883006f3855181899f15c9765eb719",
            "0x6e8635f1172f2fd6a8a1807f95899e787f5180ce",
            "0xcbeee8796715ef8507ec36a6389aed877fa56818",
            "0xd6430bda895fb3cacd0c7e4657d2c9d143794e0a",
            "0x7f3d405784e14726b3671338e0a65c65bc3fbdb1",
            "0x08bb959d826d089e07e26aa4ac9135cc308db683",
            "0x7929d31d084e08c83cd7d64bfc333937448019d3",
            "0xe2d7efe50de11c6967c6db3210c967d1d512778f",
            "0x6b6310bd7fb278c7d6a12f888a0360b44d209e33",
            "0xa4536c5df0ed277838158e78f2ccfb23cbd5d6e8",
            "0x0405e31ab5c379bcb710d34e500e009bbb79f584",
            "0x54aee715771ffb9d44c4e23ae40fca355b6270dd",
            "0x9f705ff1da72ed334f0e80f90aae5644f5cd7784"
          ],
          "allowedSLs": [
            "0x7f3d405784e14726b3671338e0a65c65bc3fbdb1"
          ],
          "lpApy": "749",
          "lendingApy": "707",
          "stakingApy": "30333",
          "farmingApy": "608",
          "stakeRewardsApy": "0",
          "balance": "145390558917227",
          "liquidity": "946768917227",
          "lockupPeriod": "7776000",
          "stake": "8313000000000000000",
          "currentLoaned": "144443790000000",
          "totalLoanOriginations": "199093790000000",
          "totalInterestEarned": "1630400616573",
          "totalFees": "254158714050",
          "stakeLockerFees": "85810558760",
          "poolDelegateFees": "136624999997",
          "numPositions": "29",
          "txCount": "198",
          "transactionHash": "0x7a0d9fb6704736db4a5c9afe364cdb830f3552d1ed78804474a441cf015f712f",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "144471425114895000000000000",
          "totalLoaned": "199093790000000",
          "totalPrincipalRepaid": "54650000000000",
          "symbol": "LP-MPL",
          "transaction": {
            "id": "0x7a0d9fb6704736db4a5c9afe364cdb830f3552d1ed78804474a441cf015f712f",
            "timestamp": "1636976738"
          },
          "mplRewards": {
            "id": "0x5e804b9a61b3e5bf2718ea249deb13366129b7de",
            "periodFinish": "1650291414",
            "reward": "5613000000000000000000",
            "rewardRate": "4640376984126984",
            "rewardsDuration": "1209600",
            "paused": false
          },
          "totalPoolTokensStaked": "143871373614895000000000000",
          "stakeRewards": {
            "id": "0x0000000000000000000000000000000000000000",
            "periodFinish": "0",
            "reward": "0",
            "rewardRate": "0",
            "rewardsDuration": "0",
            "paused": false
          },
          "totalStakeLockerTokensStaked": "0",
          "stakeLockerLiquidity": "6785022535",
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
            "aboutBusiness": "BlockTower is an institutional investment firm focused on cryptocurrency and blockchain technology. Founded in 2017 by Ari Paul (University of Chicago Endowment portfolio manager and Susquehanna International Group trader), and Matthew Goetz (Goldman Sachs executive and engineer), the firm applies professional trading, investing, and risk management to this digital asset class, and manages capital for leading LPs including Andreessen Horowitz, Union Square Ventures, and Howard Morgan, the co-founder of First Round Capital and Renaissance Technologies.\n\nAs a Pool Delegates we have two roles; onboard accredited non-US institutions that pass through KYC-AML procedures as liquidity providers, and assess the creditworthiness of borrowers, issue and underwrite loans, and manage interest and principal payments.",
            "allowList": true,
            "deckFileUrl": null,
            "createdAt": "2021-07-06T05:12:56.335Z",
            "updatedAt": "2021-07-06T05:12:56.335Z"
          },
          "poolName": "BlockTower Capital - USDC01",
          "contractAddress": "0xd618d93676762a8e3107554d9adbff7dfd7fbf47",
          "strategy": "Liquidity providers to this pool must be accredited non-US institutions, and pass through KYC-AML procedures. Expressions of interest to deposit lending capital are always open, and you should submit a request / get in touch via https://maple.finance/contact.",
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
          "numActiveLoans": "2",
          "allowedLPs": [
            "0xd59428c62650c9d4505b01fba9bf9469b920a66f"
          ],
          "allowedSLs": [],
          "lpApy": "1100",
          "lendingApy": "626",
          "stakingApy": "9955",
          "farmingApy": "401",
          "stakeRewardsApy": "0",
          "balance": "50000000000001",
          "liquidity": "20000000000001",
          "lockupPeriod": "0",
          "stake": "7300000000000000000",
          "currentLoaned": "30000000000000",
          "totalLoanOriginations": "75000000000000",
          "totalInterestEarned": "2488178082196",
          "totalFees": "187499999993",
          "stakeLockerFees": "109904109582",
          "poolDelegateFees": "187499999993",
          "numPositions": "1",
          "txCount": "19",
          "transactionHash": "0x778d42cb7d796fb7c6129d4f8d3d9ee1987e479164fafae6670318141491b822",
          "defaultsTotal": "0",
          "liquidityAssetRecoveredTotal": "0",
          "poolTokenTotalSupply": "50000000000000000000000000",
          "totalLoaned": "75000000000000",
          "totalPrincipalRepaid": "45000000000000",
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
          "stakeLockerLiquidity": "109904109582",
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

### Pool by Contract Address <a href="#maple-globals" id="maple-globals"></a>

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  poolByAddress(poolAddress: "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27") {
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
      deckFileUrl
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
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "poolByAddress": {
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
        "aboutBusiness": "Orthogonal Trading is a multi-strategy cryptocurrency trading firm focused solely on the digital asset markets. Orthogonal Trading were the first Pool Delegate to launch a lending business on Maple and currently operate two pools. The team bring experience in portfolio and risk management, auditing, quantitative trading, and blockchain system development from Goldman Sachs, Morgan Stanley, B2C2 and more.  \n\nAs a Pool Delegate on Maple, our role is to assess the creditworthiness of borrowers, issue and underwrite loans, and manage interest and principal payments.",
        "allowList": true,
        "deckFileUrl": "https://downloads.maple.loans/pool-delegate/orthogonal-trading-deck.pdf",
        "createdAt": "2021-05-19T03:11:57.680Z",
        "updatedAt": "2021-05-19T03:11:57.680Z"
      },
      "poolName": "Orthogonal Trading - USDC01",
      "contractAddress": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27",
      "strategy": "The strategy of this Pool is to target industry-leading funds and prop trading desks. The focus is on mitigating risk by lending to market-makers and arbitrage traders to avoid taking directional risk on the prices of crypto assets. Borrowers' creditworthiness is assessed based on how they manage leverage, liquidity risk, operational risk controls, management's level of experience, their balance sheet strength and recent financial performance. \n\nLoans in the pool will generally vary between 0 and 50% collateralization and target a weighted average APY of low-to-mid teens in line with the market for stablecoin lending.\n\nThe pool is open to deposits of USDC from all investors.",
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
      "liquidityCap": "450000000000000",
      "stakeAsset": {
        "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
        "symbol": "BPT",
        "decimals": 18
      },
      "stakingFee": "1000",
      "delegateFee": "1000",
      "ongoingFee": "2000",
      "name": "Maple Pool Token",
      "numActiveLoans": "29",
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
      "lpApy": "908",
      "lendingApy": "646",
      "stakingApy": "1589",
      "farmingApy": "682",
      "stakeRewardsApy": "0",
      "balance": "353654435880368",
      "liquidity": "47154235880368",
      "lockupPeriod": "7776000",
      "stake": "796090754990613559783",
      "currentLoaned": "306500200000000",
      "totalLoanOriginations": "455000400000000",
      "totalInterestEarned": "8942352559010",
      "totalFees": "1001188070768",
      "stakeLockerFees": "1117794069754",
      "poolDelegateFees": "1810294319712",
      "numPositions": "442",
      "txCount": "3198",
      "transactionHash": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
      "defaultsTotal": "0",
      "liquidityAssetRecoveredTotal": "0",
      "poolTokenTotalSupply": "350118141921209000000000000",
      "totalLoaned": "455000400000000",
      "totalPrincipalRepaid": "148500200000000",
      "symbol": "LP-MPL",
      "transaction": {
        "id": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
        "timestamp": "1621394109"
      },
      "mplRewards": {
        "id": "0x7869d7a3b074b5fa484dc04798e254c9c06a5e90",
        "periodFinish": "1651073745",
        "reward": "31347000000000000000000",
        "rewardRate": "12343679231592221",
        "rewardsDuration": "2592000",
        "paused": false
      },
      "totalPoolTokensStaked": "341375074380755000000000000",
      "stakeRewards": {
        "id": "0xf9d4d5a018d91e9bccc1e35ea78fcfecf4c5cbca",
        "periodFinish": "1644041537",
        "reward": "3840000000000000000000",
        "rewardRate": "1481481481481481",
        "rewardsDuration": "2592000",
        "paused": false
      },
      "totalStakeLockerTokensStaked": "538614081474488133321",
      "stakeLockerLiquidity": "713315491638",
      "stakeLockupPeriod": "2592000",
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

### Pool by Delegate Address

{% tabs %}
{% tab title="Request" %}
```graphql
query {
  poolByDelegate(delegateAddress: "0xa6ccb9483e3e7a737e3a4f5b72a1ce51838ba122") {
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
      deckFileUrl
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
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "poolByDelegate": {
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
        "aboutBusiness": "Orthogonal Trading is a multi-strategy cryptocurrency trading firm focused solely on the digital asset markets. Orthogonal Trading were the first Pool Delegate to launch a lending business on Maple and currently operate two pools. The team bring experience in portfolio and risk management, auditing, quantitative trading, and blockchain system development from Goldman Sachs, Morgan Stanley, B2C2 and more.  \n\nAs a Pool Delegate on Maple, our role is to assess the creditworthiness of borrowers, issue and underwrite loans, and manage interest and principal payments.",
        "allowList": true,
        "deckFileUrl": "https://downloads.maple.loans/pool-delegate/orthogonal-trading-deck.pdf",
        "createdAt": "2021-05-19T03:11:57.680Z",
        "updatedAt": "2021-05-19T03:11:57.680Z"
      },
      "poolName": "Orthogonal Trading - USDC01",
      "contractAddress": "0xfebd6f15df3b73dc4307b1d7e65d46413e710c27",
      "strategy": "The strategy of this Pool is to target industry-leading funds and prop trading desks. The focus is on mitigating risk by lending to market-makers and arbitrage traders to avoid taking directional risk on the prices of crypto assets. Borrowers' creditworthiness is assessed based on how they manage leverage, liquidity risk, operational risk controls, management's level of experience, their balance sheet strength and recent financial performance. \n\nLoans in the pool will generally vary between 0 and 50% collateralization and target a weighted average APY of low-to-mid teens in line with the market for stablecoin lending.\n\nThe pool is open to deposits of USDC from all investors.",
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
      "liquidityCap": "450000000000000",
      "stakeAsset": {
        "address": "0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef",
        "symbol": "BPT",
        "decimals": 18
      },
      "stakingFee": "1000",
      "delegateFee": "1000",
      "ongoingFee": "2000",
      "name": "Maple Pool Token",
      "numActiveLoans": "29",
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
      "lpApy": "908",
      "lendingApy": "646",
      "stakingApy": "1589",
      "farmingApy": "682",
      "stakeRewardsApy": "0",
      "balance": "353654435880368",
      "liquidity": "47154235880368",
      "lockupPeriod": "7776000",
      "stake": "796090754990613559783",
      "currentLoaned": "306500200000000",
      "totalLoanOriginations": "455000400000000",
      "totalInterestEarned": "8942352559010",
      "totalFees": "1001188070768",
      "stakeLockerFees": "1117794069754",
      "poolDelegateFees": "1810294319712",
      "numPositions": "442",
      "txCount": "3198",
      "transactionHash": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
      "defaultsTotal": "0",
      "liquidityAssetRecoveredTotal": "0",
      "poolTokenTotalSupply": "350118141921209000000000000",
      "totalLoaned": "455000400000000",
      "totalPrincipalRepaid": "148500200000000",
      "symbol": "LP-MPL",
      "transaction": {
        "id": "0x9f50036d80429f5956fc8bed866915293cd24f7754dd154d8b98c5e31a49ee7c",
        "timestamp": "1621394109"
      },
      "mplRewards": {
        "id": "0x7869d7a3b074b5fa484dc04798e254c9c06a5e90",
        "periodFinish": "1651073745",
        "reward": "31347000000000000000000",
        "rewardRate": "12343679231592221",
        "rewardsDuration": "2592000",
        "paused": false
      },
      "totalPoolTokensStaked": "341375074380755000000000000",
      "stakeRewards": {
        "id": "0xf9d4d5a018d91e9bccc1e35ea78fcfecf4c5cbca",
        "periodFinish": "1644041537",
        "reward": "3840000000000000000000",
        "rewardRate": "1481481481481481",
        "rewardsDuration": "2592000",
        "paused": false
      },
      "totalStakeLockerTokensStaked": "538614081474488133321",
      "stakeLockerLiquidity": "713315491638",
      "stakeLockupPeriod": "2592000",
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
