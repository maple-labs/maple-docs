---
description: >-
  Access syrupUSDC & syrupUSDT across multiple blockchains using CCIP. Find
  contract addresses, oracles, and bridge contracts for Solana, Arbitrum, Base,
  Plasma etc.
---

# Asset Integration

syrupUSDC & syrupUSDT use Chainlink Crosschain Interoperability Protocol (CCIP) to facilitate bridging and holding on chains other than Ethereum mainnet. CCIP handles secure crosschain token movement and message delivery, so you don’t need to build a custom bridge.

## Mainnet Addresses

### syrupUSDC&#x20;

{% tabs %}
{% tab title="Solana" %}
<table><thead><tr><th width="210.443603515625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://solscan.io/token/AvZZF1YaZDziPY2RCK4oJrRVrbN3mTD9NL24hPeaZeUj">AvZZF1YaZDziPY2RCK4oJrRVrbN3mTD9NL24hPeaZeUj</a></td></tr><tr><td>CCIP Router</td><td><a href="https://solscan.io/account/Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C">Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C</a></td></tr><tr><td>Pool</td><td><a href="https://solscan.io/account/HrTBpF3LqSxXnjnYdR4htnBLyMHNZ6eNaDZGPundvHbm">HrTBpF3LqSxXnjnYdR4htnBLyMHNZ6eNaDZGPundvHbm</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>


{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="210.3333740234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://arbiscan.io/token/0x41ca7586cc1311807b4605fbb748a3b8862b42b5">0x41CA7586cC1311807B4605fBB748a3B8862b42b5</a></td></tr><tr><td>CCIP Router</td><td><a href="https://arbiscan.io/address/0x141fa059441e0ca23ce184b6a78bafd2a517dde8">0x141fa059441E0ca23ce184B6A78bafD2A517DdE8</a></td></tr><tr><td>Pool</td><td><a href="https://arbiscan.io/address/0x660975730059246a68521a3e2fbd4740173100f5">0x660975730059246A68521a3e2FBD4740173100f5</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Base" %}
<table><thead><tr><th width="209.73345947265625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://basescan.org/token/0x660975730059246a68521a3e2fbd4740173100f5">0x660975730059246A68521a3e2FBD4740173100f5</a></td></tr><tr><td>CCIP Router</td><td><a href="https://basescan.org/address/0x881e3a65b4d4a04dd529061dd0071cf975f58bcd">0x881e3A65B4d4a04dD529061dd0071cf975F58bCD</a></td></tr><tr><td>Pool</td><td><a href="https://basescan.org/address/0xa36955b2bc12aee77ff7519482d16c7b86dbe42a">0xA36955b2Bc12Aee77FF7519482D16C7B86DBe42a</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ethereum" %}
<table><thead><tr><th width="210.47833251953125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://etherscan.io/token/0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b">0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b</a></td></tr><tr><td>CCIP Router</td><td><a href="https://etherscan.io/address/0x80226fc0ee2b096224eeac085bb9a8cba1146f7d">0x80226fc0Ee2b096224EeAc085Bb9a8cba1146f7D</a></td></tr><tr><td>Pool</td><td><a href="https://etherscan.io/address/0x20b79d39bd44deee4f89b1e9d0e3b945fde06491">0x20B79D39Bd44dEee4F89B1e9d0e3b945fde06491</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### syrupUSDT

{% tabs %}
{% tab title="Plasma" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://plasmascan.to/address/0xC4374775489CB9C56003BF2C9b12495fC64F0771">0xC4374775489CB9C56003BF2C9b12495fC64F0771</a></td></tr><tr><td>CCIP Router</td><td><a href="https://plasmascan.to/address/0xcdca5d374e46a6dddab50bd2d9acb8c796ec35c3">0xcDca5D374e46A6DDDab50bD2D9acB8c796eC35C3</a></td></tr><tr><td>Pool</td><td><a href="https://plasmascan.to/address/0x1d952d2f6ee86ef4940fa648aa7477c8ff175f09">0x1d952d2f6eE86Ef4940Fa648aA7477c8fF175F09</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://plasmascan.to/address/0x2efff88747eb5a3ff00d4d8d0f0800e306c0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Mantle" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://mantlescan.xyz/token/0x051665f2455116e929b9972c36d23070f5054ce0">0x051665f2455116e929b9972c36d23070f5054ce0</a></td></tr><tr><td>CCIP Router</td><td>[To be added]</td></tr><tr><td>Pool</td><td><a href="https://mantlescan.xyz/address/0x0aA145a62153190B8f0D3cA00c441e451529f755">0x0aA145a62153190B8f0D3cA00c441e451529f755</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://mantlescan.xyz/address/0x2efff88747eb5a3ff00d4d8d0f0800e306c0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr></tbody></table>
{% endtab %}

{% tab title="BNB" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://bscscan.com/token/0x8E9d4cEa39299323FE8eda678cAD449718556c4e">0x8E9d4cEa39299323FE8eda678cAD449718556c4e</a></td></tr><tr><td>CCIP Router</td><td>[To be added]</td></tr><tr><td>Pool</td><td><a href="https://bscscan.com/address/0xEAA7E1f805747ae29d5618b568d1b044A8b37A01">0xEAA7E1f805747ae29d5618b568d1b044A8b37A01</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

## Testnet Addresses

CCIP provides two ERC-20 test tokens, so you don’t depend on third-party liquidity while testing:

* **CCIP-BnM (Burn & Mint):** deployed on each testnet; transfers are burn → mint
* **CCIP-LnM (Lock & Mint):** minted only on Ethereum Sepolia

### syrupUSDC

{% tabs %}
{% tab title="Solana" %}
<table><thead><tr><th width="210.1796875">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://sepolia.arbiscan.io/address/0xbc9A4b299741CBf2A8eD5D2078A426027C31B2A3">95Er6pcK2agiTa2Jctp1BBnQtuDfX1d78XSTZKWZyXKk</a></td></tr><tr><td>CCIP Router</td><td><a href="https://solscan.io/account/Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C?cluster=devnet">Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.solana.com/address/B3rp2RHbuZeDeSSZLXww3EbaMr1TVtn9kF2a2FAobnxi?cluster=devnet">B3rp2RHbuZeDeSSZLXww3EbaMr1TVtn9kF2a2FAobnxi</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://sepolia.etherscan.io/address/0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="210.06585693359375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://sepolia.arbiscan.io/address/0xbc9A4b299741CBf2A8eD5D2078A426027C31B2A3">0xbc9A4b299741CBf2A8eD5D2078A426027C31B2A3</a></td></tr><tr><td>CCIP Router</td><td></td></tr><tr><td>Pool</td><td><a href="https://sepolia.arbiscan.io/address/0xB2F73a7540A000b383e8a9ffb3BdEECc4709Dc4D">0xB2F73a7540A000b383e8a9ffb3BdEECc4709Dc4D</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://sepolia.etherscan.io/address/0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Base" %}
<table><thead><tr><th width="209.87152099609375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://sepolia.basescan.org/address/0x183F67cE6CCCeaBB5D79c69C2d92e78111736B62">0x183F67cE6CCCeaBB5D79c69C2d92e78111736B62</a></td></tr><tr><td>CCIP Router</td><td><a href="https://sepolia.basescan.org/address/0xD3b06cEbF099CE7DA4AcCf578aaebFDBd6e88a93">0xD3b06cEbF099CE7DA4AcCf578aaebFDBd6e88a93</a></td></tr><tr><td>Pool</td><td><a href="https://sepolia.basescan.org/address/0xB6bD6e3e56a8E28CCbE44b6442cA8b586B964Af8">0xB6bD6e3e56a8E28CCbE44b6442cA8b586B964Af8</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://sepolia.etherscan.io/address/0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ethereum" %}
<table><thead><tr><th width="209.60198974609375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://sepolia.etherscan.io/address/0xb1206B74F612F478c12A647D12E7e822AF5D8244">0xb1206b74f612f478c12a647d12e7e822af5d8244</a></td></tr><tr><td>CCIP Router</td><td><a href="https://sepolia.etherscan.io/address/0x0BF3dE8c5D3e8A2B34D2BEeB17ABfCeBaf363A59">0x0BF3dE8c5D3e8A2B34D2BEeB17ABfCeBaf363A59</a></td></tr><tr><td>Pool</td><td><a href="https://sepolia.etherscan.io/address/0x98C80d0235Eaae38200720Ae86e2D6a62b3B19c9">0x98C80d0235Eaae38200720Ae86e2D6a62b3B19c9</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

Find out more and acquire test tokens by visiting the [CCIP Test Tokens page](https://docs.chain.link/ccip/test-tokens).

## Pricing

### **Onchain Oracles**

#### SyrupUSDC/USDC

{% tabs %}
{% tab title="Solana" %}
<table><thead><tr><th width="141.67181396484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Price Oracle</td><td><a href="https://solscan.io/account/CpNyiFt84q66665Kx64bobxZuMgZ2EecrhAJs1HikS2T">CpNyiFt84q66665Kx64bobxZuMgZ2EecrhAJs1HikS2T</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="141.67181396484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Price Oracle</td><td><a href="https://arbiscan.io/address/0xF8722c901675C4F2F7824E256B8A6477b2c105FB">0xF8722c901675C4F2F7824E256B8A6477b2c105FB</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Base" %}
<table><thead><tr><th width="141.67181396484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Price Oracle</td><td><a href="https://basescan.org/address/0x311D3A3faA1d5939c681E33C2CDAc041FF388EB2">0x311D3A3faA1d5939c681E33C2CDAc041FF388EB2</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

#### SyrupUSDT/USDT

{% tabs %}
{% tab title="Plasma" %}
<table><thead><tr><th width="141.67181396484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Price Oracle</td><td><a href="https://plasmascan.to/address/0x89a0e204591fce2611e89ca7634c12b400d347fe">0x89a0e204591Fce2611e89CA7634c12B400d347fe</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Mantle" %}
<table><thead><tr><th width="141.67181396484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Price Oracle</td><td><a href="https://mantlescan.xyz/address/0xdDEaeAdF319bd363120Af02fBdb1e2C5A3Ce172a">0xdDEaeAdF319bd363120Af02fBdb1e2C5A3Ce172a</a></td></tr></tbody></table>
{% endtab %}

{% tab title="BNB" %}
<table><thead><tr><th width="141.67181396484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Price Oracle</td><td><a href="https://bscscan.com/address/0xac9962aAb7b8fe63fA3A5065c22D4Dd700B1C658">0xac9962aAb7b8fe63fA3A5065c22D4Dd700B1C658</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

Use [Chainlink's Data Feeds docs](https://docs.chain.link/data-feeds/getting-started) to consume them.

### **Data Streams**

Low latency streams work on supported chains - full list of available chains [here](https://docs.chain.link/data-streams/crypto-streams?page=1\&testnetPage=1).

{% tabs %}
{% tab title="SyrupUSDC/USDC" %}
<table><thead><tr><th width="141.67181396484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Stream Feed ID</td><td><code>0x000721629eb23678e5c52595523785ae4e0ef470ca8a1cb7e894edcfa03dcfe9</code></td></tr></tbody></table>
{% endtab %}

{% tab title="SYRUP/USD" %}
<table><thead><tr><th width="153.39501953125"></th><th></th></tr></thead><tbody><tr><td>Stream feed ID</td><td><code>0x0003e2c8ee282f518aee9efd1e14a5fd51da7a0e3207041f5db1785d0729cd1d</code></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

Use Chainlink's Data Streams docs to consume them:

* [Data Streams integration (EVM)](https://docs.chain.link/data-streams/tutorials/evm-onchain-report-verification)
* [Data Streams integration (Solana)](https://docs.chain.link/data-streams/tutorials/solana-onchain-report-verification)

## Integration paths

### 1) Offchain integrators (bridge, wallets & aggregator UIs)

If you run a bridge, wallet, or aggregator UI, use the **token** and **router** addresses per chain (below) to configure your routes and call patterns. Typically, you won’t deploy onchain contracts - your UI directs users to call the CCIP Router with the correct params.

#### High-level flow

1. User picks source & destination chains in your UI or protocol flow
2. Approve syrupUSDC / syrupUSDT to the CCIP Router on the source chain (standard ERC-20 approval; Solana uses SPL program approvals)
3. Initiate CCIP transfer via the Router with destination chain selector, recipient, and amount
4. CCIP finalizes on destination chain and releases/mints syrupUSDC / syrupUSDT to the recipient

#### Implementation notes

* Always call the CCIP Router listed for the source chain; don’t hit low-level endpoints directly
* Chain selectors & fees: Pull chain selectors and fee token options from the [CCIP directory](https://docs.chain.link/ccip/directory/mainnet); keep them in config
* Solana (SVM) specifics: Use the SVM Router program (`ccip_send`) and follow the [SVM API docs](https://docs.chain.link/ccip/api-reference/svm/v1.6.0/router?utm_source=chatgpt.com) for building send/receive flows
* Observability: Track the CCIP message ID from the Router response and correlate with destination events

### 2) Onchain integrators (protocols)

If your protocol needs to bake in crosschain syrupUSDC transfers, implement CCIP send/receive flows in your smart contracts and interact with the Router on the source chain, please contact us at [partnerships@maple.finance](mailto:partnerships@maple.finance).

## Resources & Contact

* Partnerships & queries: [partnerships@maple.finance](mailto:partnerships@maple.finance)
* [CCIP docs](https://docs.chain.link/ccip)
* [CCIP Directory (mainnet)](https://docs.chain.link/ccip/directory/mainnet)
* [Token page (syrupUSDC)](https://docs.chain.link/ccip/directory/mainnet/token/syrupUSDC)
* [Token page (syrupUSDT)](https://docs.chain.link/ccip/directory/mainnet/token/syrupUSDT)
* [Integration Support](https://chain.link/ccip-contact)
