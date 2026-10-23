---
description: >-
  List or accept syrupUSDC, syrupUSDT & syrupUSDG as collateral or liquidity in
  your protocol.
---

# Asset Integration: Ethereum Mainnet

syrupUSDC, syrupUSDT and syrupUSDG are ERC-4626 vault tokens on Ethereum mainnet. This page covers token addresses and three methods for obtaining pricing data.

### Token addresses

{% tabs %}
{% tab title="Mainnet" %}
<table><thead><tr><th width="171.50872802734375">Token</th><th>Address</th></tr></thead><tbody><tr><td>syrupUSDC</td><td><a href="https://etherscan.io/token/0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b">0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b</a></td></tr><tr><td>syrupUSDT</td><td><a href="https://etherscan.io/token/0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d">0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d</a></td></tr><tr><td>syrupUSDG</td><td><a href="https://etherscan.io/token/0x87b65c4aaffa76881f9e96f3e7ed945ddfc3cd7a">0x87b65C4aAFFA76881f9E96F3e7ED945ddFC3Cd7A</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Testnet (Sepolia)" %}
<table><thead><tr><th width="174.407958984375">Token</th><th>Address</th></tr></thead><tbody><tr><td>syrupUSDC</td><td><a href="https://sepolia.etherscan.io/token/0x2d8d21fee98d060655729efd7b14bc432c375ac1">0x2d8d21fee98d060655729efd7b14bc432c375ac1</a></td></tr><tr><td>syrupUSDT</td><td><a href="https://sepolia.etherscan.io/token/0x7679cbe9ae66298114ac6dac73487b63ac023c0b">0x7679cbe9ae66298114ac6dac73487b63ac023c0b</a></td></tr><tr><td>syrupUSDG</td><td><a href="https://sepolia.etherscan.io/token/0x0f40d60293433a64bb8da7e4dfd9d13399ed319e">0x0f40d60293433a64bb8da7e4dfd9d13399ed319e</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### Pricing

#### Option 1: Smart contract (ERC-4626)

syrupUSDC, syrupUSDT and syrupUSDG use the ERC-4626 tokenized vault standard. You can query the token price directly from the contract using two functions:

1. **`convertToAssets(uint256 shares_)`** - Returns the amount of underlying assets (USDC/USDT/USDG) that would be received for a given number of shares. Use this for display purposes and general price calculations.
2. **`convertToExitAssets(uint256 shares_)`** - Returns the amount of underlying assets accounting for any unrealized losses in the pool. Use this when calculating actual redemption values or valuing syrupUSD assets as collateral. This is the value Chainlink oracles relay (see [Pool Exchange Rates](../../technical-resources/pools/accounting/pool-exchange-rates.md)).

All three tokens use 6 decimals. To get the price per token, call either function with `1000000` (1 share):

{% tabs %}
{% tab title="Solidity" %}
```solidity
uint256 pricePerShare = ISyrupToken(syrupUSDC).convertToAssets(1000000);
```
{% endtab %}

{% tab title="Ethers" %}
```javascript
const syrupUSDC = new ethers.Contract(
  "0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b",
  ["function convertToAssets(uint256) view returns (uint256)"],
  provider
);
const price = await syrupUSDC.convertToAssets(1000000n); // 1 share
```
{% endtab %}

{% tab title="Viem" %}
```typescript
import { createPublicClient, http } from 'viem';
import { mainnet } from 'viem/chains';

const client = createPublicClient({
  chain: mainnet,
  transport: http()
});

const price = await client.readContract({
  address: '0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b',
  abi: [{ inputs: [{ type: 'uint256' }], name: 'convertToAssets', outputs: [{ type: 'uint256' }], stateMutability: 'view', type: 'function' }],
  functionName: 'convertToAssets',
  args: [1000000n]
});
```
{% endtab %}

{% tab title="Python" %}
```python
# web3.py
from web3 import Web3

w3 = Web3(Web3.HTTPProvider("https://eth-mainnet.g.alchemy.com/v2/YOUR_KEY"))
abi = [{"inputs":[{"type":"uint256"}],"name":"convertToAssets","outputs":[{"type":"uint256"}],"stateMutability":"view","type":"function"}]
contract = w3.eth.contract(address="0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b", abi=abi)
price = contract.functions.convertToAssets(1000000).call()
```
{% endtab %}
{% endtabs %}

#### Option 2: Chainlink Oracle

Chainlink provides low-latency Price Streams for syrupUSDC, syrupUSDT and syrupUSDG on Ethereum mainnet, and exchange rate Price Feeds on other chains. Every Chainlink oracle for syrupUSD assets relays the Pool's `convertToExitAssets()` value, so it reflects impairments and realized losses. This is the oracle we recommend for lending markets and other protocols that need a price feed.

**Price Streams**

Price Streams deliver low-latency signed price reports offchain that your contract verifies onchain when consumed. The same Stream IDs work on Ethereum mainnet and every other supported chain.

<table><thead><tr><th width="149.64227294921875">Price Stream</th><th>Address / Link</th></tr></thead><tbody><tr><td>syrupUSDC/USDC</td><td><a href="https://data.chain.link/streams/syrupusdc-usdc-exchangerate-streams">0x000721629eb23678e5c52595523785ae4e0ef470ca8a1cb7e894edcfa03dcfe9</a></td></tr><tr><td>syrupUSDT/USDT</td><td><a href="https://data.chain.link/streams/syrupusdt-usdt-exchangerate-streams">0x00071ec93f578219a986e1dfbda2302551c3b86d48219f23b6351bfcac2efc55</a></td></tr><tr><td>syrupUSDG/USDG</td><td><a href="https://data.chain.link/streams/syrupusdg-usdg-exchangerate-streams">0x0007f1bf39f52bb9fc4c0a87fe2d1de5e8105a2d3899ca09051082337cc44d91</a></td></tr></tbody></table>

To consume Price Streams, use the Chainlink docs:

* [Streams Addresses](https://data.chain.link/streams)
* [Streams Integration (EVM)](https://docs.chain.link/data-streams/tutorials/evm-onchain-report-verification)

**Price Feeds**

There is no Chainlink Price Feed for syrupUSDC, syrupUSDT or syrupUSDG on Ethereum mainnet. To get the same value onchain, call `convertToExitAssets()` directly on the token contract (Option 1). Price Feed addresses for other chains are listed in [Asset Integration: Crosschain](../crosschain/syrupusd-crosschain.md#price-feeds).

For how the price is calculated, see [Pricing syrupUSD assets](../crosschain/syrupusd-crosschain.md#pricing-syrupusd-assets).

#### Option 3: CoinGecko / CoinMarketCap APIs

CoinGecko and CoinMarketCap track syrupUSDC, syrupUSDT and syrupUSDG prices via DEX pool data. These prices can fluctuate with onchain swaps, so we recommend Options 1 & 2.

* [CoinGecko API](https://docs.coingecko.com/)
* [CoinMarketCap API](https://coinmarketcap.com/api/documentation/v1/)

### Which price to use

<table><thead><tr><th width="308.9521484375">Use case</th><th>Recommended method</th></tr></thead><tbody><tr><td>DeFi protocols requiring oracle feeds</td><td>Option 1 (ERC-4626 functions) or Option 2 (Chainlink)</td></tr><tr><td>Frontend display / portfolios</td><td>Option 1 (ERC-4626 functions) or Option 2 (Chainlink)</td></tr><tr><td>Smart contract integrations</td><td>Option 1 (ERC-4626 functions)</td></tr></tbody></table>

### Resources & contact

* Partnerships & queries: [partnerships@maple.finance](mailto:partnerships@maple.finance)
* [Chainlink Data Feeds](https://docs.chain.link/data-feeds)
* [Chainlink Data Streams](https://docs.chain.link/data-streams)
* [CoinGecko API](https://docs.coingecko.com/)
* [CoinMarketCap API](https://coinmarketcap.com/api/documentation/v1/)
