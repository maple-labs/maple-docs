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
<table><thead><tr><th width="229.61029052734375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://solscan.io/token/AvZZF1YaZDziPY2RCK4oJrRVrbN3mTD9NL24hPeaZeUj">AvZZF1YaZDziPY2RCK4oJrRVrbN3mTD9NL24hPeaZeUj</a></td></tr><tr><td>Pool</td><td><a href="https://solscan.io/account/HrTBpF3LqSxXnjnYdR4htnBLyMHNZ6eNaDZGPundvHbm">HrTBpF3LqSxXnjnYdR4htnBLyMHNZ6eNaDZGPundvHbm</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr><tr><td>Price Feed (syrupUSDC/USDC)</td><td><a href="https://solscan.io/account/3TP6aEQ1VEt4VhwkpzccjVfvJUnvUDkziQ7pLFvZxir5">3TP6aEQ1VEt4VhwkpzccjVfvJUnvUDkziQ7pLFvZxir5</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="230.1944580078125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://arbiscan.io/token/0x41ca7586cc1311807b4605fbb748a3b8862b42b5">0x41CA7586cC1311807B4605fBB748a3B8862b42b5</a></td></tr><tr><td>Pool</td><td><a href="https://arbiscan.io/address/0x660975730059246a68521a3e2fbd4740173100f5">0x660975730059246A68521a3e2FBD4740173100f5</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr><tr><td>Price Feed (syrupUSDC/USDC)</td><td><a href="https://arbiscan.io/address/0xF8722c901675C4F2F7824E256B8A6477b2c105FB">0xF8722c901675C4F2F7824E256B8A6477b2c105FB</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Base" %}
<table><thead><tr><th width="230.497314453125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://basescan.org/token/0x660975730059246a68521a3e2fbd4740173100f5">0x660975730059246A68521a3e2FBD4740173100f5</a></td></tr><tr><td>Pool</td><td><a href="https://basescan.org/address/0xa36955b2bc12aee77ff7519482d16c7b86dbe42a">0xA36955b2Bc12Aee77FF7519482D16C7B86DBe42a</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr><tr><td>Price Feed (syrupUSDC/USDC)</td><td><a href="https://basescan.org/address/0x311D3A3faA1d5939c681E33C2CDAc041FF388EB2">0x311D3A3faA1d5939c681E33C2CDAc041FF388EB2</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ink" %}
<table><thead><tr><th width="229.8880615234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.inkonchain.com/address/0x3c23e6FB09064e9A64829Fa8FEe27Ad19A27Bfa9">0x3c23e6FB09064e9A64829Fa8FEe27Ad19A27Bfa9</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.inkonchain.com/address/0xa3361ff0d9cA1cBA31335a3280eECe47f1a08F43">0xa3361ff0d9cA1cBA31335a3280eECe47f1a08F43</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Monad" %}
<table><thead><tr><th width="229.8880615234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://monadscan.com/address/0xaB6e5a0C3799d020c790D34F7B2C02639e238AF7">0xaB6e5a0C3799d020c790D34F7B2C02639e238AF7</a></td></tr><tr><td>Pool</td><td><a href="https://monadscan.com/address/0x4eA35565147A7A6BfDAF7e605BDCdA4BD039A540">0x4eA35565147A7A6BfDAF7e605BDCdA4BD039A540</a></td></tr><tr><td>Receiver (Mint/Redeem)</td><td><a href="https://etherscan.io/address/0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4">0x02B6A75c5D1F430F0614dc5AC8aD5F9D35fbA2c4</a></td></tr><tr><td>Price Feed (syrupUSDC/USDC)</td><td><a href="https://monadscan.com/address/0xaeC21ef8f7aA33687c647BFEDaA8CD7F7855973F">0xaeC21ef8f7aA33687c647BFEDaA8CD7F7855973F</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Tempo" %}
<table><thead><tr><th width="229.57122802734375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explore.tempo.xyz/address/0x20c0000000000000000000008191667423F70E67">0x20c0000000000000000000008191667423F70E67</a></td></tr><tr><td>Pool</td><td><a href="https://explore.tempo.xyz/address/0xEe71b1a542BeeDf2270437fDEaC190Bd9abBCB19">0xEe71b1a542BeeDf2270437fDEaC190Bd9abBCB19</a></td></tr><tr><td>Price Feed (syrupUSDC/USD)</td><td><a href="https://explore.tempo.xyz/address/0x14150E642cA7392e33bB5F0141c131c1e5Ac1D10">0x14150E642cA7392e33bB5F0141c131c1e5Ac1D10</a></td></tr></tbody></table>

_Note: syrupUSDC on Tempo is a_ [_TIP-20 token_](https://docs.tempo.xyz/protocol/tip20/overview)_. Bridging works the same via CCIP._
{% endtab %}

{% tab title="Robinhood" %}
<table><thead><tr><th width="229.8880615234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://robinhoodchain.blockscout.com/address/0xC6a4854eeB493224d5f9485E12Dd3A81f22EEE14">0xC6a4854eeB493224d5f9485E12Dd3A81f22EEE14</a></td></tr><tr><td>Pool</td><td><a href="https://robinhoodchain.blockscout.com/address/0x50056397CF6ccF50D1748e95c32EC361951ee6F9">0x50056397CF6ccF50D1748e95c32EC361951ee6F9</a></td></tr><tr><td>Price Feed (syrupUSDC/USDC)</td><td><a href="https://robinhoodchain.blockscout.com/address/0x6317f016FA3e312C4625dee51d32b43a223011f8">0x6317f016FA3e312C4625dee51d32b43a223011f8</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Arc" %}
<table><thead><tr><th width="230.33941650390625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.arc.io/token/0x0dc6b79f3c3854e4d74514fd4d29be6c96beee39">0x0dC6b79F3c3854E4d74514fD4d29BE6c96Beee39</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.arc.io/token/0x6be14E674f741faa78da2fEcF00870C8B753A0BB">0x6be14E674f741faa78da2fEcF00870C8B753A0BB</a></td></tr><tr><td>Price Feed (syrupUSDC/USDC)</td><td><a href="https://explorer.arc.io/address/0x46c87ABb22510DE522121BE80adbB0Ca05Fb14E4">0x46c87ABb22510DE522121BE80adbB0Ca05Fb14E4</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### syrupUSDT

{% tabs %}
{% tab title="Plasma" %}
<table><thead><tr><th width="229.9896240234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://plasmascan.to/address/0xC4374775489CB9C56003BF2C9b12495fC64F0771">0xC4374775489CB9C56003BF2C9b12495fC64F0771</a></td></tr><tr><td>Pool</td><td><a href="https://plasmascan.to/address/0x1d952d2f6ee86ef4940fa648aa7477c8ff175f09">0x1d952d2f6eE86Ef4940Fa648aA7477c8fF175F09</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://plasmascan.to/address/0x2efff88747eb5a3ff00d4d8d0f0800e306c0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr><tr><td>Price Feed (syrupUSDT/USDT)</td><td><a href="https://plasmascan.to/address/0x89a0e204591Fce2611e89CA7634c12B400d347fe">0x89a0e204591Fce2611e89CA7634c12B400d347fe</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Mantle" %}
<table><thead><tr><th width="230.41058349609375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://mantlescan.xyz/token/0x051665f2455116e929b9972c36d23070f5054ce0">0x051665f2455116e929b9972c36d23070f5054ce0</a></td></tr><tr><td>Pool</td><td><a href="https://mantlescan.xyz/address/0x0aA145a62153190B8f0D3cA00c441e451529f755">0x0aA145a62153190B8f0D3cA00c441e451529f755</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://mantlescan.xyz/address/0x2efff88747eb5a3ff00d4d8d0f0800e306c0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr><tr><td>Price Feed (syrupUSDT/USDT)</td><td><a href="https://mantlescan.xyz/address/0xdDEaeAdF319bd363120Af02fBdb1e2C5A3Ce172a">0xdDEaeAdF319bd363120Af02fBdb1e2C5A3Ce172a</a></td></tr></tbody></table>
{% endtab %}

{% tab title="BNB" %}
<table><thead><tr><th width="229.9505615234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://bscscan.com/token/0x8E9d4cEa39299323FE8eda678cAD449718556c4e">0x8E9d4cEa39299323FE8eda678cAD449718556c4e</a></td></tr><tr><td>Pool</td><td><a href="https://bscscan.com/address/0xEAA7E1f805747ae29d5618b568d1b044A8b37A01">0xEAA7E1f805747ae29d5618b568d1b044A8b37A01</a></td></tr><tr><td>Price Feed (syrupUSDT/USDT)</td><td><a href="https://bscscan.com/address/0xac9962aAb7b8fe63fA3A5065c22D4Dd700B1C658">0xac9962aAb7b8fe63fA3A5065c22D4Dd700B1C658</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ink" %}
<table><thead><tr><th width="229.51220703125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.inkonchain.com/address/0x8A76fe7fA6da27f85a626c5C53730B38D13603d7">0x8A76fe7fA6da27f85a626c5C53730B38D13603d7</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.inkonchain.com/address/0x543164a51401a468B6Fee3F7db27a30871448ff5">0x543164a51401a468B6Fee3F7db27a30871448ff5</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://explorer.inkonchain.com/address/0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr><tr><td>Price Feed (syrupUSDT/USDT)</td><td><a href="https://explorer.inkonchain.com/address/0x8B4EF9c2B61fdfd0c45d9897C923822aEfe10B85">0x8B4EF9c2B61fdfd0c45d9897C923822aEfe10B85</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### syrupUSDG

{% tabs %}
{% tab title="Robinhood" %}
<table><thead><tr><th width="229.8880615234375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://robinhoodchain.blockscout.com/address/0x40858070814a57FdF33a613ae84fE0a8b4a874f7">0x40858070814a57FdF33a613ae84fE0a8b4a874f7</a></td></tr><tr><td>Pool</td><td><a href="https://robinhoodchain.blockscout.com/address/0x01FA676ECC8662E6923fdF06bA5278A96ccD725c">0x01FA676ECC8662E6923fdF06bA5278A96ccD725c</a></td></tr><tr><td>Price Feed (syrupUSDG/USDG)</td><td><a href="https://robinhoodchain.blockscout.com/address/0xDd194C66aDcb422F188a04434e4824D70c151cF0">0xDd194C66aDcb422F188a04434e4824D70c151cF0</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Solana" %}
<table><thead><tr><th width="229.53826904296875">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.solana.com/address/CYB6WRi2YuV4Ui6q1dieP5Raev6ah7qftGsQAxJiZo8f">CYB6WRi2YuV4Ui6q1dieP5Raev6ah7qftGsQAxJiZo8f</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.solana.com/address/H1w3zL4yJKqHXut3dHvFQVCbjmYt5DZ3ioZcZrYZZD11">H1w3zL4yJKqHXut3dHvFQVCbjmYt5DZ3ioZcZrYZZD11</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="229.9678955078125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://arbiscan.io/address/0xE1B0dC5A21b10f1634fBfbE9976fBA2Ee2e1c762">0xE1B0dC5A21b10f1634fBfbE9976fBA2Ee2e1c762</a></td></tr><tr><td>Pool</td><td><a href="https://arbiscan.io/address/0x5355292a5C36C4094B93fB62aA1FEFCa6e28b75f#code">0x5355292a5C36C4094B93fB62aA1FEFCa6e28b75f</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Ink" %}
<table><thead><tr><th width="229.98095703125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token</td><td><a href="https://explorer.inkonchain.com/address/0xeBE9ed66eFe0948D0c1B72b0157Fc17733667018">0xeBE9ed66eFe0948D0c1B72b0157Fc17733667018</a></td></tr><tr><td>Pool</td><td><a href="https://explorer.inkonchain.com/address/0x376d6f0e7718B6F5642D92F13ca516c8B4f5A91F">0x376d6f0e7718B6F5642D92F13ca516c8B4f5A91F</a></td></tr><tr><td>Token Admin (Timelock)</td><td><a href="https://explorer.inkonchain.com/address/0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b">0x2eFFf88747EB5a3FF00d4d8d0f0800E306C0426b</a></td></tr><tr><td>Price Feed (syrupUSDG/USDG)</td><td><a href="https://explorer.inkonchain.com/address/0xbc9E6Fa14945C6f486d17e0aF4f982d63310Ee35">0xbc9E6Fa14945C6f486d17e0aF4f982d63310Ee35</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

Price Feeds are onchain contracts that Chainlink updates on a set heartbeat. They can be read directly. To consume Price Feeds, use the Chainlink docs:

1. [Price Feeds Addresses](https://docs.chain.link/data-feeds/price-feeds/addresses)
2. [Consuming Data Feeds](https://docs.chain.link/data-feeds/getting-started)

### **Price Streams**

Price Streams deliver low-latency signed price reports offchain that your contract verifies onchain when consumed.

<table><thead><tr><th width="149.64227294921875">Price Stream</th><th>Address / Link</th></tr></thead><tbody><tr><td>syrupUSDC/USDC</td><td><a href="https://data.chain.link/streams/syrupusdc-usdc-exchangerate-streams">0x000721629eb23678e5c52595523785ae4e0ef470ca8a1cb7e894edcfa03dcfe9</a></td></tr><tr><td>syrupUSDG/USDG</td><td><a href="https://data.chain.link/streams/syrupusdg-usdg-exchangerate-streams">0x0007f1bf39f52bb9fc4c0a87fe2d1de5e8105a2d3899ca09051082337cc44d91</a></td></tr></tbody></table>

To consume Price Streams, use the Chainlink Docs:

* [Streams Addresses](https://data.chain.link/streams)
* [Streams integration (EVM)](https://docs.chain.link/data-streams/tutorials/evm-onchain-report-verification)
* [Streams integration (Solana)](https://docs.chain.link/data-streams/tutorials/solana-onchain-report-verification)

## Testnet Addresses

CCIP provides two ERC-20 test tokens, so you don’t depend on third-party liquidity while testing:

* **CCIP-BnM (Burn & Mint):** deployed on each testnet; transfers are burn → mint
* **CCIP-LnM (Lock & Mint):** minted only on Ethereum Sepolia

Find out more and acquire test tokens by visiting the [CCIP Test Tokens page](https://docs.chain.link/ccip/test-tokens) and the addresses of tokens available via the [CCIP Testnet Directory](https://docs.chain.link/ccip/directory/testnet).

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
* [Token page (syrupUSDG)](https://docs.chain.link/ccip/directory/mainnet/token/syrupUSDG)
* [Integration Support](https://chain.link/ccip-contact)
