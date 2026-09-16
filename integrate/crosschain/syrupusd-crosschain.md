---
description: >-
  Access syrupUSDC & syrupUSDT across multiple blockchains using CCIP. Find
  contract addresses, oracles, and bridge contracts for Solana, Arbitrum, Base,
  Plasma etc.
---

# Asset Integration: Crosschain

syrupUSDC & syrupUSDT use Chainlink Crosschain Interoperability Protocol (CCIP) to facilitate bridging and holding on chains other than Ethereum mainnet. CCIP handles secure crosschain token movement and message delivery, so you don’t need to build a custom bridge.

Both tokens have 6 decimals across all chains.

## Mainnet Addresses

### syrupUSDC

{% tabs %}
{% tab title="Solana" %}
<table><thead><tr><th width="210.443603515625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://solscan.io/token/AvZZF1YaZDziPY2RCK4oJrRVrbN3mTD9NL24hPeaZeUj">AvZZF1YaZDziPY2RCK4oJrRVrbN3mTD9NL24hPeaZeUj</a></td></tr><tr><td>Pool</td><td><a href="https://solscan.io/account/HrTBpF3LqSxXnjnYdR4htnBLyMHNZ6eNaDZGPundvHbm">HrTBpF3LqSxXnjnYdR4htnBLyMHNZ6eNaDZGPundvHbm</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="210.3333740234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://arbiscan.io/token/0x41ca7586cc1311807b4605fbb748a3b8862b42b5">0x41CA7586cC1311807B4605fBB748a3B8862b42b5</a></td></tr><tr><td>Pool</td><td><a href="https://arbiscan.io/address/0x660975730059246a68521a3e2fbd4740173100f5">0x660975730059246A68521a3e2FBD4740173100f5</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Base" %}
<table><thead><tr><th width="209.73345947265625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://basescan.org/token/0x660975730059246a68521a3e2fbd4740173100f5">0x660975730059246A68521a3e2FBD4740173100f5</a></td></tr><tr><td>Pool</td><td><a href="https://basescan.org/address/0xa36955b2bc12aee77ff7519482d16c7b86dbe42a">0xA36955b2Bc12Aee77FF7519482D16C7B86DBe42a</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ink" %}
<table><thead><tr><th width="210.47833251953125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.inkonchain.com/address/0x3c23e6FB09064e9A64829Fa8FEe27Ad19A27Bfa9">0x3c23e6FB09064e9A64829Fa8FEe27Ad19A27Bfa9</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.inkonchain.com/address/0xa3361ff0d9cA1cBA31335a3280eECe47f1a08F43">0xa3361ff0d9cA1cBA31335a3280eECe47f1a08F43</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Monad" %}
<table><thead><tr><th width="210.47833251953125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://monadscan.com/address/0xaB6e5a0C3799d020c790D34F7B2C02639e238AF7">0xaB6e5a0C3799d020c790D34F7B2C02639e238AF7</a></td></tr><tr><td>Pool</td><td><a href="https://monadscan.com/address/0x4eA35565147A7A6BfDAF7e605BDCdA4BD039A540">0x4eA35565147A7A6BfDAF7e605BDCdA4BD039A540</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Tempo" %}
<table><thead><tr><th width="210.47833251953125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explore.tempo.xyz/address/0x20c0000000000000000000008191667423F70E67">0x20c0000000000000000000008191667423F70E67</a></td></tr><tr><td>Pool</td><td><a href="https://explore.tempo.xyz/address/0xEe71b1a542BeeDf2270437fDEaC190Bd9abBCB19">0xEe71b1a542BeeDf2270437fDEaC190Bd9abBCB19</a></td></tr></tbody></table>

_Note: syrupUSDC on Tempo is a_ [_TIP-20 token_](https://docs.tempo.xyz/protocol/tip20/overview)_. Bridging works the same via CCIP._
{% endtab %}

{% tab title="Arc" %}
<table><thead><tr><th width="210.47833251953125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.arc.io/token/0x0dc6b79f3c3854e4d74514fd4d29be6c96beee39">0x0dC6b79F3c3854E4d74514fD4d29BE6c96Beee39</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.arc.io/token/0x6be14E674f741faa78da2fEcF00870C8B753A0BB">0x6be14E674f741faa78da2fEcF00870C8B753A0BB</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### syrupUSDT

{% tabs %}
{% tab title="Plasma" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://plasmascan.to/address/0xC4374775489CB9C56003BF2C9b12495fC64F0771">0xC4374775489CB9C56003BF2C9b12495fC64F0771</a></td></tr><tr><td>Pool</td><td><a href="https://plasmascan.to/address/0x1d952d2f6ee86ef4940fa648aa7477c8ff175f09">0x1d952d2f6eE86Ef4940Fa648aA7477c8fF175F09</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://plasmascan.to/address/0x2efff88747eb5a3ff00d4d8d0f0800e306c0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Mantle" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://mantlescan.xyz/token/0x051665f2455116e929b9972c36d23070f5054ce0">0x051665f2455116e929b9972c36d23070f5054ce0</a></td></tr><tr><td>Pool</td><td><a href="https://mantlescan.xyz/address/0x0aA145a62153190B8f0D3cA00c441e451529f755">0x0aA145a62153190B8f0D3cA00c441e451529f755</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://mantlescan.xyz/address/0x2efff88747eb5a3ff00d4d8d0f0800e306c0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr></tbody></table>
{% endtab %}

{% tab title="BNB" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://bscscan.com/token/0x8E9d4cEa39299323FE8eda678cAD449718556c4e">0x8E9d4cEa39299323FE8eda678cAD449718556c4e</a></td></tr><tr><td>Pool</td><td><a href="https://bscscan.com/address/0xEAA7E1f805747ae29d5618b568d1b044A8b37A01">0xEAA7E1f805747ae29d5618b568d1b044A8b37A01</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ink" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.inkonchain.com/address/0x8A76fe7fA6da27f85a626c5C53730B38D13603d7">0x8A76fe7fA6da27f85a626c5C53730B38D13603d7</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.inkonchain.com/address/0x543164a51401a468B6Fee3F7db27a30871448ff5">0x543164a51401a468B6Fee3F7db27a30871448ff5</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://explorer.inkonchain.com/address/0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### syrupUSDG

{% tabs %}
{% tab title="Solana" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.solana.com/address/CYB6WRi2YuV4Ui6q1dieP5Raev6ah7qftGsQAxJiZo8f">CYB6WRi2YuV4Ui6q1dieP5Raev6ah7qftGsQAxJiZo8f</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.solana.com/address/H1w3zL4yJKqHXut3dHvFQVCbjmYt5DZ3ioZcZrYZZD11">H1w3zL4yJKqHXut3dHvFQVCbjmYt5DZ3ioZcZrYZZD11</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://arbiscan.io/address/0xE1B0dC5A21b10f1634fBfbE9976fBA2Ee2e1c762">0xE1B0dC5A21b10f1634fBfbE9976fBA2Ee2e1c762</a></td></tr><tr><td>Pool</td><td><a href="https://arbiscan.io/address/0x5355292a5C36C4094B93fB62aA1FEFCa6e28b75f#code">0x5355292a5C36C4094B93fB62aA1FEFCa6e28b75f</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ink" %}
<table><thead><tr><th width="209.6771240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.inkonchain.com/address/0xeBE9ed66eFe0948D0c1B72b0157Fc17733667018">0xeBE9ed66eFe0948D0c1B72b0157Fc17733667018</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.inkonchain.com/address/0x376d6f0e7718B6F5642D92F13ca516c8B4f5A91F">0x376d6f0e7718B6F5642D92F13ca516c8B4f5A91F</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://explorer.inkonchain.com/address/0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

To consume Price Feeds and Data Streams, use the Chainlink docs:

1. [Price Feeds Addresses](https://docs.chain.link/data-feeds/price-feeds/addresses)
2. [Consuming Data Feeds](https://docs.chain.link/data-feeds/getting-started)
3. [Data Streams integration (EVM)](https://docs.chain.link/data-streams/tutorials/evm-onchain-report-verification)
4. [Data Streams integration (Solana)](https://docs.chain.link/data-streams/tutorials/solana-onchain-report-verification)

## Testnet Addresses

CCIP provides two ERC-20 test tokens, so you don’t depend on third-party liquidity while testing:

* **CCIP-BnM (Burn & Mint):** deployed on each testnet; transfers are burn → mint
* **CCIP-LnM (Lock & Mint):** minted only on Ethereum Sepolia

Find out more and acquire test tokens by visiting the [CCIP Test Tokens page](https://docs.chain.link/ccip/test-tokens) and the addresses of tokens available via the [CCIP Testnet Directory](https://docs.chain.link/ccip/directory/testnet).





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
