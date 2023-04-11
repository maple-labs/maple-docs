# Protocol Actors

There are three actors in the Maple Protocol ecosystem:

- Borrowers
- Lenders
- Pool Delegates

# Borrowers

- Borrowers initiate loan requests by specifying terms and providing collateral if required.
- Borrowers draw down loans after they are approved and funded.
- Borrowers repay principal and interest through associated smart contracts.

**Code Example:**
This snippet queries the [`GlobalsV2`](https://maplefinance.gitbook.io/maple/technical-resources/protocol-overview/smart-contract-architecture#maple-globals) contract to check if a given address is an authorized borrower

```js
import { providers } from 'ethers';
import { addresses, mapleGlobalsV2 } from '@maplelabs/maple-js';

const RPC_ENDPOINT = 'https://mainnet.infura.io/v3/{YOUR_KEY}';

async function main() {
  const contract = mapleGlobalsV2.core.connect(
    addresses['mainnet-prod'].MapleGlobalsV2,
    new providers.JsonRpcProvider(RPC_ENDPOINT)
  );

  const isBorrower = await contract.isBorrower('YOUR_ADDRESS');
  console.log({ isBorrower });
}

main();
```

# Lenders

- Lenders deposit specific assets into designated pools.
- Lenders accumulate interest on deposits as borrowers repay loans.
- Lenders withdraw assets from pools using the `WithdrawalManager` contract.

**Code Example:**

```js
import { BigNumber, providers } from 'ethers';
import { addresses, poolV2, erc20 } from '@maplelabs/maple-js';

const RPC_ENDPOINT = 'https://mainnet.infura.io/v3/{YOUR_KEY}';
const POOL_ADDRESS = '{POOL_ID}';

async function main() {
  const provider = new providers.JsonRpcProvider(RPC_ENDPOINT);

  const poolContract = poolV2.core.connect(POOL_ADDRESS, provider.getSigner());
  const usdcContract = erc20.core.connect(addresses['mainnet-prod'].USDC, provider.getSigner());

  const account = '{YOUR_ACCOUNT}';
  const oneDollar = BigNumber.from(1000000);

  await (await usdcContract.approve(POOL_ADDRESS, oneDollar)).wait();

  await (await poolContract.deposit(oneDollar, account)).wait();
}

main();
```

# Delegates

- Delegates evaluate and approve/fund loan requests based on criteria specific to each pool.
- Delegates accept or reject refinance proposals.
- Delegates manage various pool utilities, such as adjusting the liquidity cap or authorizing certain lenders.

**Code Example:**
This snippet queries the `poolV2` contract to query the on-chain name of a given pool

```js
import { providers } from 'ethers';
import { poolV2 } from '@maplelabs/maple-js';

const RPC_ENDPOINT = 'https://mainnet.infura.io/v3/{YOUR_KEY}';

async function main() {
  const contract = poolV2.core.connect('{POOL_ID}', new providers.JsonRpcProvider(RPC_ENDPOINT));

  const name = await contract.name();
  console.log({ name });
}

main();
```
