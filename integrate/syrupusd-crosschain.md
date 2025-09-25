# syrupUSD Crosschain

syrupUSDC & syrupUSDT use Chainlink Crosschain Interoperability Protocol (CCIP) to facilitate minting, holding & redeeming on chains other than Ethereum mainnet. CCIP handles secure crosschain token movement and message delivery, so you don’t need to build a custom bridge.

## Integration paths

### 1) Offchain integrators (bridge, wallets & aggregator UIs)

If you run a bridge, wallet, or aggregator UI, use the **token** and **router** addresses per chain (below) to configure your routes and call patterns. Typically, you won’t deploy onchain contracts - your UI directs users to call the CCIP Router with the correct params.&#x20;

### 2) Onchain integrators (protocols)

If your protocol needs to bake in crosschain syrupUSDC transfers, implement CCIP send/receive flows in your smart contracts and interact with the Router on the source chain, please contact us at [partnerships@maple.finance](mailto:partnerships@maple.finance).

## syrupUSDC Mainnet: networks & addresses

{% tabs %}
{% tab title="Solana" %}
<table><thead><tr><th width="150.1875">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>AvZZF1YaZDziPY2RCK4oJrRVrbN3mTD9NL24hPeaZeUj</code></td></tr><tr><td>Router Address</td><td><code>Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C</code></td></tr><tr><td>Pool Address</td><td><code>HrTBpF3LqSxXnjnYdR4htnBLyMHNZ6eNaDZGPundvHbm</code></td></tr></tbody></table>
{% endtab %}

{% tab title="Ethereum" %}
<table><thead><tr><th width="149.6015625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b</code></td></tr><tr><td>Router Address</td><td><code>0x80226fc0Ee2b096224EeAc085Bb9a8cba1146f7D</code></td></tr><tr><td>Pool Address</td><td><code>0x20B79D39Bd44dEee4F89B1e9d0e3b945fde06491</code></td></tr></tbody></table>
{% endtab %}

{% tab title="Base" %}
<table><thead><tr><th width="149.5078125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>0x660975730059246A68521a3e2FBD4740173100f5</code></td></tr><tr><td>Router Address</td><td><code>0x881e3A65B4d4a04dD529061dd0071cf975F58bCD</code></td></tr><tr><td>Pool Address</td><td><code>0xA36955b2Bc12Aee77FF7519482D16C7B86DBe42a</code></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
<table><thead><tr><th width="150.2421875">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>0x41CA7586cC1311807B4605fBB748a3B8862b42b5</code></td></tr><tr><td>Router Address</td><td><code>0x141fa059441E0ca23ce184B6A78bafD2A517DdE8</code></td></tr><tr><td>Pool Address</td><td><code>0x660975730059246A68521a3e2FBD4740173100f5</code></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

## syrupUSDC Testnet: networks & addresses

CCIP provides two ERC-20 test tokens, so you don’t depend on third-party liquidity while testing:

* **CCIP-BnM (Burn & Mint):** deployed on each testnet; transfers are burn → mint
* **CCIP-LnM (Lock & Mint):** minted only on Ethereum Sepolia

{% tabs %}
{% tab title="Solana" %}
<table><thead><tr><th width="150.453125">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>95Er6pcK2agiTa2Jctp1BBnQtuDfX1d78XSTZKWZyXKk</code></td></tr><tr><td>Router Address</td><td><code>Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C</code></td></tr></tbody></table>
{% endtab %}

{% tab title="Ethereum" %}
<table><thead><tr><th width="149.71484375">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>0xb1206b74f612f478c12a647d12e7e822af5d8244</code></td></tr><tr><td>Router Address</td><td><code>0x0BF3dE8c5D3e8A2B34D2BEeB17ABfCeBaf363A59</code></td></tr></tbody></table>
{% endtab %}

{% tab title="Base" %}
<table><thead><tr><th width="150.140625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>0x183F67cE6CCCeaBB5D79c69C2d92e78111736B62</code></td></tr><tr><td>Router Address</td><td><code>0xD3b06cEbF099CE7DA4AcCf578aaebFDBd6e88a93</code></td></tr></tbody></table>
{% endtab %}

{% tab title="Arbitrum" %}
Not deployed on Testnet
{% endtab %}
{% endtabs %}

Find out more and acquire test tokens by visiting the [CCIP Test Tokens page](https://docs.chain.link/ccip/test-tokens).

## syrupUSDT Mainnet: networks & addresses

{% tabs %}
{% tab title="Plasma" %}
<table><thead><tr><th width="149.881103515625">Type</th><th>Address</th></tr></thead><tbody><tr><td>Token Address</td><td><code>0xC4374775489CB9C56003BF2C9b12495fC64F0771</code></td></tr><tr><td>Router Address</td><td></td></tr><tr><td>Pool Address</td><td><code>0x1d952d2f6eE86Ef4940Fa648aA7477c8fF175F09</code></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

## High-level flow

1. User picks source & destination chains in your UI or protocol flow
2. Approve syrupUSDC / syrupUSDT to the CCIP Router on the source chain (standard ERC-20 approval; Solana uses SPL program approvals)
3. Initiate CCIP transfer via the Router with destination chain selector, recipient, and amount
4. CCIP finalizes on destination chain and releases/mints syrupUSDC / syrupUSDT to the recipient

## Implementation notes

* Always call the Router listed for the source chain; don’t hit low-level endpoints directly
* Chain selectors & fees: Pull chain selectors and fee token options from the [CCIP directory](https://docs.chain.link/ccip/directory/mainnet); keep them in config
* Solana (SVM) specifics: Use the SVM Router program (`ccip_send`) and follow the [SVM API docs](https://docs.chain.link/ccip/api-reference/svm/v1.6.0/router?utm_source=chatgpt.com) for building send/receive flows
* Observability: Track the CCIP message ID from the Router response and correlate with destination events
* If you require market data streams or feeds, please see [market-data-streams-and-feeds.md](technical-resources/market-data-streams-and-feeds.md "mention")

## Resources & Contact

* Partnerships & queries: [partnerships@maple.finance](mailto:partnerships@maple.finance)
* [CCIP docs](https://docs.chain.link/ccip)
* [CCIP Directory (mainnet)](https://docs.chain.link/ccip/directory/mainnet)
* [Token page (syrupUSDC)](https://docs.chain.link/ccip/directory/mainnet/token/syrupUSDC)
* [Token page (syrupUSDT)](https://docs.chain.link/ccip/directory/mainnet/token/syrupUSDT)
* [Integration Support](https://chain.link/ccip-contact)

