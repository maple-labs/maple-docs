---
description: >-
  List or accept syrupUSDC & syrupUSDT as collateral or liquidity in your
  protocol.
---

# Asset Integration

syrupUSDC and syrupUSDT are ERC-4626 vault tokens on Ethereum mainnet. This page covers token addresses and three methods for obtaining pricing data.

### Token addresses

{% tabs %}
{% tab title="Mainnet" %}
<table><thead><tr><th width="171.50872802734375">Token</th><th>Address</th></tr></thead><tbody><tr><td>syrupUSDC</td><td><a href="https://etherscan.io/token/0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b">0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b</a></td></tr><tr><td>syrupUSDT</td><td><a href="https://etherscan.io/token/0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d">0x356b8d89c1e1239cbbb9de4815c39a1474d5ba7d</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Testnet (Sepolia)" %}
<table><thead><tr><th width="174.407958984375">Token</th><th>Address</th></tr></thead><tbody><tr><td>syrupUSDC</td><td><a href="https://sepolia.etherscan.io/token/0x2d8d21fee98d060655729efd7b14bc432c375ac1">0x2d8d21fee98d060655729efd7b14bc432c375ac1</a></td></tr><tr><td>syrupUSDT</td><td><a href="https://sepolia.etherscan.io/token/0x7679cbe9ae66298114ac6dac73487b63ac023c0b">0x7679cbe9ae66298114ac6dac73487b63ac023c0b</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### Pricing

#### Option 1: Smart contract (ERC-4626)

syrupUSDC and syrupUSDT use the ERC-4626 tokenized vault standard. You can query the token price directly from the contract using two functions:

1. **`convertToAssets(uint256 shares_)`** - Returns the amount of underlying assets (USDC/USDT) that would be received for a given number of shares. Use this for display purposes and general price calculations.
2. **`convertToExitAssets(uint256 shares_)`** - Returns the amount of underlying assets accounting for any unrealized losses in the pool. Use this when calculating actual redemption values.

Both tokens use 6 decimals. To get the price per token, call either function with `1000000` (1 share):

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

#### Option 2: Pyth Oracle

Pyth Network provides low-latency, high-fidelity price feeds for syrupUSDC and syrupUSDT. Pyth calculates pricing using the smart contract ERC-4626 functions.

**Feed IDs**

<table><thead><tr><th width="164.24737548828125">Token</th><th>Price Feed ID</th></tr></thead><tbody><tr><td>syrupUSDC/USDC</td><td><code>0x2ad31d1c4a85fbf2156ce57fab4104124c5ef76a6386375ecfc8da1ed5ce1486</code></td></tr><tr><td>syrupUSDT/USDT</td><td><code>0x7e10170c23d7df62d301b2ade26854200ee584f3f3b84cb2e5195adf35c5b97f</code></td></tr></tbody></table>

**Contract addresses**

<table><thead><tr><th width="156.80816650390625">Network</th><th>Pyth Contract</th></tr></thead><tbody><tr><td>Ethereum</td><td><a href="https://etherscan.io/address/0x4305fb66699c3b2702d4d05cf36551390a4c69c6">0x4305FB66699C3B2702D4d05CF36551390A4c69C6</a></td></tr><tr><td>Sepolia Testnet</td><td><a href="https://sepolia.etherscan.io/address/0xDd24F84d36BF92C65F92307595335bdFab5Bbd21">0xDd24F84d36BF92C65F92307595335bdFab5Bbd21</a></td></tr></tbody></table>

**Get price from Pyth**

{% tabs %}
{% tab title="Offchain" %}
**Offchain: Fetch price from Pyth Hermes API**

**bash**

```bash
# Get latest syrupUSDC price
curl "https://hermes.pyth.network/v2/updates/price/latest?ids[]=0x2ad31d1c4a85fbf2156ce57fab4104124c5ef76a6386375ecfc8da1ed5ce1486"
```

**javascript**

```javascript
const feedId = "0x2ad31d1c4a85fbf2156ce57fab4104124c5ef76a6386375ecfc8da1ed5ce1486";
const response = await fetch(
  `https://hermes.pyth.network/v2/updates/price/latest?ids[]=${feedId}`
);
const data = await response.json();
const priceData = data.parsed[0].price;
const price = Number(priceData.price) * Math.pow(10, priceData.expo);
```
{% endtab %}

{% tab title="Onchain" %}
**Onchain: Read price from Pyth contract**

```solidity
import "@pythnetwork/pyth-sdk-solidity/IPyth.sol";
import "@pythnetwork/pyth-sdk-solidity/PythStructs.sol";

contract MyContract {
    IPyth pyth = IPyth(0x4305FB66699C3B2702D4d05CF36551390A4c69C6);
    bytes32 constant SYRUP_USDC_FEED = 0x2ad31d1c4a85fbf2156ce57fab4104124c5ef76a6386375ecfc8da1ed5ce1486;

    function getSyrupUSDCPrice(bytes[] calldata priceUpdateData) public payable returns (int64) {
        uint fee = pyth.getUpdateFee(priceUpdateData);
        pyth.updatePriceFeeds{value: fee}(priceUpdateData);
        PythStructs.Price memory price = pyth.getPrice(SYRUP_USDC_FEED);
        return price.price;
    }
}
```
{% endtab %}
{% endtabs %}

See [Pyth documentation](https://docs.pyth.network/price-feeds/core/getting-started) for complete integration guides.

#### Option 3: CoinGecko / CoinMarketCap APIs

CoinGecko and CoinMarketCap track syrupUSDC and syrupUSDT prices via DEX pool data. These prices can fluctuate with onchain swaps, so we recommend Options 1 & 2.

* [CoinGecko API](https://docs.coingecko.com/)
* [CoinMarketCap API](https://coinmarketcap.com/api/documentation/v1/)

### Which price to use

<table><thead><tr><th width="308.9521484375">Use case</th><th>Recommended method</th></tr></thead><tbody><tr><td>DeFi protocols requiring oracle feeds</td><td>Option 1 (ERC-4626 functions) or Option 2 (Pyth)</td></tr><tr><td>Frontend display / portfolios</td><td>Option 1 (ERC-4626 functions) or Option 2 (Pyth)</td></tr><tr><td>Smart contract integrations</td><td>Option 1 (ERC-4626 functions)</td></tr></tbody></table>

### Resources & contact

* Partnerships & queries: [integrations@maple.finance](mailto:integrations@maple.finance)
* [Pyth Price Feeds](https://docs.pyth.network/price-feeds)
* [CoinGecko API](https://docs.coingecko.com/)
* [CoinMarketCap API](https://coinmarketcap.com/api/documentation/v1/)
