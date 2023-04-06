# Protocol Actors

There are three actors in the Maple Protocol ecosystem:

- Borrowers
- Lenders
- Pool Delegates

# Borrowers

- Borrowers request loans with specific terms and can provide collateral as required.
- Borrowers can drawdown loans once approved and funded.
- Borrowers are responsible for repaying the principal and interest payments through the same smart contracts.

**Code Example:**
This snippet queries the `GlobalsV2` contract to check if a given address is an authorised borrower

```js
import { providers } from "ethers";
import { addresses, mapleGlobalsV2 } from "@maplelabs/maple-js";

const RPC_ENDPOINT = "https://mainnet.infura.io/v3/{YOUR_KEY}";

async function main() {
  const contract = mapleGlobalsV2.core.connect(
    addresses["mainnet-prod"].MapleGlobalsV2,
    new providers.JsonRpcProvider(RPC_ENDPOINT)
  );

  const isBorrower = await contract.isBorrower("YOUR_ADDRESS");
  console.log({ isBorrower });
}

main();
```

# Lenders

- Lenders can deposit specific assets to certain pools.
- Lenders earn interest on their deposits as borrowers repay the loans.
- Lenders can withdraw their assets from the pool through the `WithdrawalManager` contract.

**Code Example:**

```js
import { BigNumber, providers } from "ethers";
import { addresses, poolV2, erc20 } from "@maplelabs/maple-js";

const RPC_ENDPOINT = "https://mainnet.infura.io/v3/{YOUR_KEY}";
const POOL_ADDRESS = "{POOL_ID}";

async function main() {
  const provider = new providers.JsonRpcProvider(RPC_ENDPOINT);

  const poolContract = poolV2.core.connect(POOL_ADDRESS, provider.getSigner());
  const usdcContract = erc20.core.connect(
    addresses["mainnet-prod"].USDC,
    provider.getSigner()
  );

  const account = "{YOUR_ACCOUNT}";
  const one_dollar = BigNumber.from(1000000);

  await (await usdcContract.approve(POOL_ADDRESS, one_dollar)).wait();

  await (await poolContract.deposit(one_dollar, account)).wait();
}

main();
```

# Delegates

- Delegates assess and approve/fund loan requests based on a criteria specific to each pool.
- Delegates can accept/reject refinance proposals.
- Delegates can operate various pool management utilites e.g. adjusting the liquidity cap or authorising certain lenders.

**Code Example:**
This snippet queries the `poolV2` contract to query the on-chain name of a given pool

```js
import { providers } from "ethers";
import { poolV2 } from "@maplelabs/maple-js";

const RPC_ENDPOINT = "https://mainnet.infura.io/v3/{YOUR_KEY}";

async function main() {
  const contract = poolV2.core.connect(
    "{POOL_ID}",
    new providers.JsonRpcProvider(RPC_ENDPOINT)
  );

  const name = await contract.name();
  console.log({ name });
}

main();
```
