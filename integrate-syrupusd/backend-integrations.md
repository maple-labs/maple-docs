# Backend Integrations

{% hint style="info" %}

## Programmatically deposit and withdraw from SyrupUSD

_This documentation provides guidance on integrating with the Syrup protocol to successfully deposit and withdraw from a pool._

**Deposit**:

1. [**Querying the Maple API**](#step-1---querying-the-maple-api) to retrieve the necessary contract addresses.
2. [**Determining user authorization**](#step-2---determining-user-authorization) as a Syrup lender.
3. [**Retrieving an authorization signature**](#step-3---retrieving-authorization-signature) from the Maple API
4. [**Executing contract calls**](#step-4---executing-contract-calls) (authorize and deposit, or deposit only).

**Withdrawal**:

1. [**Retrieve Position Data**](#step-1---retrieve-pool-position-data) from the Maple API
2. [**Calculate Shares to Redeem**](#step-2---calculate-shares-to-redeem) from the Pool contract
3. [**Execute the Withdrawal**](#step-3---execute-the-withdrawal) on the Pool contract
4. [**Await Withdrawal Completion**](#step-4---await-withdrawal-completion){% endhint %}

## Maple SDK and Maple GraphQL API

All necessary ABIs and addresses are available in the Maple SDK or via GitHub:

- **Maple JS GitHub (ABIs):**
  https://github.com/maple-labs/maple-js/tree/main/src/abis
- **Maple JS GitHub (Addresses):**
  https://github.com/maple-labs/maple-js/tree/main/src/addresses

Within the Maple SDK, you can access both ABIs and network-specific addresses.

You can also install the package and use it within your application.

{% tabs %}
{% tab title="npm" %}

```sh
npm install @maplelabs/maple-js
```

{% endtab %}

{% tab title="yarn" %}

```sh
yarn add @maplelabs/maple-js
```

{% endtab %}

{% tab title="pnpm" %}

```sh
pnpm add @maplelabs/maple-js
```

{% endtab %}
{% endtabs %}

To access necessary data use Maple GraphQL API:

{% tabs %}
{% tab title="Mainnet" %}
`https://api.maple.finance/v2/graphql`
{% endtab %}
{% tab title="Sepolia" %}
`https://sepolia.api.maple.finance/v2/graphql`
{% endtab %}
{% endtabs %}

**NOTE**: In order to perform integration in Sepolia you may need to message Telegram chat [https://t.me/syrupfi](https://t.me/syrupfi) to receive Sepolia `USDC`/`USDT` tokens.

## Deposit

### Step 1 - Querying the Maple API

Syrup's main contract, the `SyrupRouter`, is uniquely designed to allow authorized participants to securely access and benefit from the yields available in the Maple ecosystem, abstracting all the complexities of the permissioning system inherent to Maple. Each Syrup `PoolV2` has an associated `SyrupRouter`.

{% tabs %}
{% tab title="Mainnet" %}

#### Syrup USDC

| Contract               | Address                                                                                                               |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------- |
| PoolV2                 | [0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b](https://etherscan.io/address/0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b) |
| SyrupRouter            | [0x134cCaaA4F1e4552eC8aEcb9E4A2360dDcF8df76](https://etherscan.io/address/0x134cCaaA4F1e4552eC8aEcb9E4A2360dDcF8df76) |
| WithdrawalManagerQueue | [0x1bc47a0Dd0FdaB96E9eF982fdf1F34DC6207cfE3](https://etherscan.io/address/0x1bc47a0Dd0FdaB96E9eF982fdf1F34DC6207cfE3) |

#### Syrup USDT

| Contract               | Address                                                                                                               |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------- |
| PoolV2                 | [0x356B8d89c1e1239Cbbb9dE4815c39A1474d5BA7D](https://etherscan.io/address/0x356B8d89c1e1239Cbbb9dE4815c39A1474d5BA7D) |
| SyrupRouter            | [0xF007476Bb27430795138C511F18F821e8D1e5Ee2](https://etherscan.io/address/0xF007476Bb27430795138C511F18F821e8D1e5Ee2) |
| WithdrawalManagerQueue | [0x86eBDf902d800F2a82038290B6DBb2A5eE29eB8C](https://etherscan.io/address/0x86eBDf902d800F2a82038290B6DBb2A5eE29eB8C) |

{% endtab %}
{% tab title="Sepolia" %}

#### Syrup USDC

| Contract               | Address                                                                                                                       |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| PoolV2                 | [0x2d8d21fee98d060655729efd7b14bc432c375ac1](https://sepolia.etherscan.io/address/0x2d8d21fee98d060655729efd7b14bc432c375ac1) |
| SyrupRouter            | [0x5387ab37f93af968920af6c0faa6dbc52973b020](https://sepolia.etherscan.io/address/0x5387ab37f93af968920af6c0faa6dbc52973b020) |
| WithdrawalManagerQueue | [0x2ff61035de7a1550219be12a6e9d33aa10b844b6](https://sepolia.etherscan.io/address/0x2ff61035de7a1550219be12a6e9d33aa10b844b6) |

#### Syrup USDT

| Contract               | Address                                                                                                                       |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| PoolV2                 | [0x7679cbe9ae66298114ac6dac73487b63ac023c0b](https://sepolia.etherscan.io/address/0x7679cbe9ae66298114ac6dac73487b63ac023c0b) |
| SyrupRouter            | [0x0b703919cf2d30dbb18bad6febe8f0ea4f191918](https://sepolia.etherscan.io/address/0x0b703919cf2d30dbb18bad6febe8f0ea4f191918) |
| WithdrawalManagerQueue | [0xbbe2bf30b76729a4eb75bf40ced47a58000ae1d3](https://sepolia.etherscan.io/address/0xbbe2bf30b76729a4eb75bf40ced47a58000ae1d3) |

{% endtab %}
{% endtabs %}

You can also access addresses of routers via Maple GraphQL API.

#### Example query

```gql
query {
  poolV2S(where: { syrupRouter_not: null }) {
    id
    asset {
      symbol
    }
    syrupRouter {
      id
    }
    withdrawalManagerQueue {
      id
    }
  }
}
```

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

```typescript
import { gql, GraphQLClient } from "graphql-request";

interface MaplePoolV2 {
  id: string;
  asset: {
    symbol: string;
  };
  syrupRouter: {
    id: string;
  };
  withdrawalManagerQueue {
    id: string;
  }
}

interface QueryResponse {
  poolV2S: MaplePoolV2[];
}

const query = gql`
  query GetMaplePools {
    poolV2S(where: { syrupRouter_not: null }) {
      id
      name
      asset {
        symbol
      }
      syrupRouter {
        id
      }
      withdrawalManagerQueue {
        id
      }
    }
  }
`;
const client = new GraphQLClient(MAPLE_API_URL);

const main = async () => {
  const { poolV2S } = await client.request<QueryResponse>(query);

  for (const poolV2 of poolV2S) {
    console.log(`Pool ${poolV2.name}: SyrupRouter: ${poolV2.syrupRouter.id} WithdrawalManagerQueue: ${poolV2.withdrawalManagerQueue.id}`);
  }
};

main();
```

Important to note that the query uses the `syrupRouter_not` filter, to return specifically Syrup pools.

**Response Fields:**

- `poolV2S.id`: The Syrup Pool contract address.
- `poolV2S.syrupRouter.id`: The `SyrupRouter` contract address.

These addresses can then be used to interact with the `SyrupRouter` contract.

### Step 2 - Determining user authorization

Before depositing, check if a user is already authorized in the Syrup as this is necessary to perform a deposit. To do this, query the `Account` entity.

#### Example Query

```gql
query GetMapleAccount($accountId: ID!) {
  account(id: $accountId) {
    isSyrupLender
  }
}
```

**Note:** The account ID must be provided in lowercase.

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

```typescript
import { gql, GraphQLClient } from "graphql-request";

interface MapleAccount {
  isSyrupLender: boolean;
}

interface QueryResponse {
  account: MapleAccount;
}

const query = gql`
  query GetMapleAccount($accountId: ID!) {
    account(id: $accountId) {
      isSyrupLender
    }
  }
`;
const client = new GraphQLClient(MAPLE_API_URL);

const main = async () => {
  const account = "0x123...";

  const { account: mapleAccount } = await client.request<QueryResponse>(query, {
    accountId: account.toLowerCase(),
  });

  if (mapleAccount) {
    console.log(`Can user ${account} deposit into Syrup: ${isSyrupLender}`);
  } else {
    console.log("Account not found");
  }
};

main();
```

If `isSyrupLender = true`, the user is already authorized into `Pool Permission Manager` and can deposit into Syrup pools. Otherwise, the user must perform authorization before their initial deposit.

### Step 3 - Retrieving authorization signature

**Note:** This step is only required in case you got `isSyrupLender = false` in previous step, otherwise you can continue to next step.

The Maple Protocol is geared towards institutions and has a permissioning system that requires allowlisting for executing most functions. For pool deposits, in general, lenders need to have their wallet allowlisted in Maple's `Pool Permission Manager`. Aiming to abstract and simplify the process, the `SyrupRouter` integrates directly with the `Pool Permission Manager` to allow for valid users to self-authorize and deposit in a single transaction assuming the user meets eligibility requirements.

To retrieve authorization signature please message Telegram chat [https://t.me/syrupfi](https://t.me/syrupfi)

### Step 4 - Executing contract calls

The first time you lend an asset (e.g. `USDC`, `USDT`) to Syrup, you may need to allow the contract to interact with your asset. This is a common transaction on Ethereum.

Depositing into a pool requires a transaction. Once the transaction has been processed `SyrupRouter` will accept your lending tokens and you will receive Pool LP (Liquidity Provider) Tokens.

Each pool contract inherits the [ERC-4626](https://erc4626.info/) standard, also known as the `Tokenized Vault` Standard. This standard informs how the LP Tokens accrue value from borrower repayments of loans.

#### `isSyrupLender = true` - user is already authorized

You can directly call the `deposit` or `depositWithPermit` method on `SyrupRouter`.

```solidity
function deposit(uint256 assets, bytes32 depositData)
```

**NOTE**: `depositData` is an optional field which you will not need to provide

![deposit()](https://github.com/maple-labs/syrup-router/assets/16119563/2e911fe4-cd81-4b58-a290-6809d7bba125)

#### Code example using Maple SDK for `USDC` or `USDT`.

{% tabs %}
{% tab title="USDC" %}

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupRouter = syrupUtils.syrupRouter.connect(
    SYRUP_USDC_ROUTER_ADDRESS, // Explained how to get in previous step
    signer
  );
  const usdc = new Contract(addresses["mainnet-prod"].USDC, USDC_ABI, signer);

  const amount = BigNumber.from(1000000);

  const approveReceipt = await usdc.approve(SYRUP_USDC_ROUTER_ADDRESS, amount);
  await approveReceipt.wait();

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

{% endtab %}
{% tab title="USDT" %}

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils, environmentMocks } from "@maplelabs/maple-js";

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupRouter = syrupUtils.syrupRouter.connect(
    SYRUP_USDT_ROUTER_ADDRESS, // Explained how to get in previous step
    signer
  );

  const usdt = new Contract(addresses["mainnet-prod"].USDT, USDT_ABI, signer);

  const amount = BigNumber.from(1000000);

  const approveReceipt = await usdt.approve(SYRUP_USDT_ROUTER_ADDRESS, amount);
  await approveReceipt.wait();

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

{% endtab %}
{% endtabs %}

You can also deposit into Syrup with gasless approval `permit` for more information please have a look here - https://eips.ethereum.org/EIPS/eip-2612

```solidity
function depositWithPermit(
  uint256 amount,
  uint256 deadline,
  uint8   v,
  bytes32 r,
  bytes32 s,
  bytes32 depositData_
)
```

**NOTE**: `depositWithPermit` is only available for `Syrup USDC`

![depositWithPermit()](https://github.com/maple-labs/syrup-router/assets/16119563/db8192f8-c9d3-42d9-9522-9a91df95fb5d)

#### Code example using Maple SDK

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils, erc20 } from "@maplelabs/maple-js";

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupRouter = syrupUtils.syrupRouter.connect(
    SYRUP_USDC_ROUTER_ADDRESS, // Explained how to get in previous step
    signer
  );

  const usdc = new Contract(addresses["mainnet-prod"].USDC, USDC_ABI, signer);

  const amount = BigNumber.from(1000000);
  const account = await signer.getAddress();

  const deadline = Math.floor(Date.now() / 1000) + 3600;
  const nonce = await usdc.nonces(account);
  const network = await provider.getNetwork();

  // EIP-712 domain for USDC
  const domain = {
    name: await usdc.name(),
    version: "2", // "1" for Sepolia
    chainId: network.chainId,
    verifyingContract: addresses["mainnet-prod"].USDC,
  };

  // EIP-712 types for permit
  const types = {
    Permit: [
      { name: "owner", type: "address" },
      { name: "spender", type: "address" },
      { name: "value", type: "uint256" },
      { name: "nonce", type: "uint256" },
      { name: "deadline", type: "uint256" },
    ],
  };

  const permitMessage = {
    owner: account,
    spender: SYRUP_USDC_ROUTER_ADDRESS,
    value: amount.toString(),
    nonce: nonce.toString(),
    deadline: deadline,
  };

  const signature = await signer._signTypedData(domain, types, permitMessage);
  const sig = utils.splitSignature(signature);

  const depositWithPermitReceipt = await syrupRouter.depositWithPermit(
    amount,
    deadline,
    sig.v,
    sig.r,
    sig.s,
    utils.formatBytes32String("")
  );
  await depositWithPermitReceipt.wait();
};

main();
```

#### `isSyrupLender = false` - user requires authorization

1. Retrieve a signature from the Maple API. Follow instructions received from the team as mentioned in the step above.
2. Use the retrieved signature and the `authorizeAndDeposit` or `authorizeAndDepositWithPermit` method on `SyrupRouter`.

```solidity
function authorizeAndDeposit(
        uint256 bitmap,
        uint256 deadline,
        uint8   auth_v,
        bytes32 auth_r,
        bytes32 auth_s,
        uint256 amount,
        bytes32 depositData)
```

![authAndDeposit()](https://github.com/maple-labs/syrup-router/assets/16119563/1c59065b-c1cb-4b55-9ab8-1d04ebb9fe83)

#### Code example using Maple SDK for `USDC` or `USDT`.

```typescript
import { BigNumber, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ... // Exact same steps as regular deposit

  const { bitmap, deadline, sig } = authorize(); // Please contact us to get information about authorization

  const authorizeAndDepositReceipt = await syrupRouter.authorizeAndDeposit(
    bitmap,
    deadline,
    sig.v,
    sig.r,
    sig.s,
    amount,
    utils.formatBytes32String("")
  );
  await authorizeAndDepositReceipt.wait();
};

main();
```

You can also deposit into Syrup with gasless approval `permit` for more information please have a look here - https://eips.ethereum.org/EIPS/eip-2612

```solidity
function authorizeAndDepositWithPermit(
        uint256 bitmap,
        uint256 auth_deadline,
        uint8   auth_v,
        bytes32 auth_r,
        bytes32 auth_s,
        uint256 amount,
        bytes32 depositData,
        uint256 permit_deadline,
        uint8   permit_v,
        bytes32 permit_r,
        bytes32 permit_s
    )
```

**NOTE**: `authorizeAndDepositWithPermit` is only available for `Syrup USDC`

![authAndDepositWithPermit()](https://github.com/maple-labs/syrup-router/assets/16119563/c0e4d64f-e092-46b0-9b7f-00def236ace7)

#### Code example using Maple SDK

```typescript
import { BigNumber, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () {
  ... // Exact same steps as regular depositWithPermit

  const { bitmap, authDeadline, authSig } = authorize(); // Please contact us to get information about authorization

  const authorizeAndDepositWithPermitReceipt = await syrupRouter.authorizeAndDepositWithPermit(
    bitmap,
    authDeadline,
    authSig.v,
    authSig.r,
    authSig.s,
    amount,
    utils.formatBytes32String(''),
    deadline,
    sig.v,
    sig.r,
    sig.s
  );
  await authorizeAndDepositWithPermitReceipt.wait();
}

main();
```

## Withdrawal

### Step 1 - Retrieve Pool Position Data

Query the Maple API for the user’s pool position data using the `PoolV2Position` field on the `Account` query:

#### Data model

```gql
PoolPositionV2 {
	availableBalance // The pool position in the pool asset.
	availableShares // The underlying shares representing that position.
	redeemRequested // A boolean indicating if a redeem request is active.
}
```

#### Example query

```gql
query GetMapleAccount($accountId: ID!, $poolId: String!) {
	account(id: $accountId) {
    id
    poolV2Positions(where: { pool: $poolId }) {
      id // "$lender_address-$pool_address"
      availableBalance // Position in pool asset
      availableShares // Underlying shares
      redeemRequested // Boolean flag
      pool {
        name
      }
    }
  }
}
```

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

```typescript
import { gql, GraphQLClient } from "graphql-request";

interface MaplePoolPosition {
  id: string;
  availableBalance: string;
  availableShares: string;
  redeemRequested: boolean;
  pool: {
    name: string;
  };
}

interface MapleAccount {
  id: string;
  poolV2Positions: MaplePoolPosition[];
}

interface QueryResponse {
  account: MapleAccount;
}

const query = gql`
  query GetMapleAccount($accountId: ID!, $poolId: String!) {
    account(id: $accountId) {
      id
      poolV2Positions(where: { pool: $poolId }) {
        id
        availableBalance
        availableShares
        redeemRequested
        pool {
          name
        }
      }
    }
  }
`;
const client = new GraphQLClient(MAPLE_API_URL);

const main = async () => {
  const account = "0x123...";

  const { account: mapleAccount } = await client.request<QueryResponse>(query, {
    accountId: account.toLowerCase(),
    poolId: SYRUP_USDC,
  });

  if (mapleAccount) {
    for (const poolV2Position of mapleAccount.poolV2Positions) {
      console.log(`Pool ${poolV2Position.pool.name} position for ${account}`);
      console.log(`Available balance: ${poolV2Position.availableBalance}`);
      console.log(`Available shares: ${poolV2Position.availableShares}`);
    }
  } else {
    console.log("Account not found");
  }
};

main();
```

### Step 2 - Calculate Shares to Redeem

- Your withdrawal request must be expressed in shares. Although the Maple API provides both `availableShares` and `availableBalance`, note that losses or impairments on the pool may affect the value of your assets relative to shares.
- To ensure accuracy, convert the desired asset amount to “exit shares” using the pool contract’s conversion method:
- These transactions leverage the `ERC-4626` tokenised vault standard, which you can read more about here: https://ethereum.org/en/developers/docs/standards/tokens/erc-4626/

#### Function signature

```solidity
function convertToExitShares(uint256 assets_) external view returns (uint256 shares_);
```

#### Code example using Maple SDK

```typescript
import { BigNumber, providers } from "ethers";
import { poolV2 } from "@maplelabs/maple-js";

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);

  const syrupPool = poolV2.core.connect(SYRUP_USDC, provider);

  const amount = BigNumber.from(10 ** 8);

  const sharesToRedeem = await syrupPool.convertToExitShares(amount);

  console.log(`${amount.toString()} is equal to ${sharesToRedeem.toString()}`);
};

main();
```

### Step 3 - Execute the Withdrawal

Now that you have calculated `sharesToRedeem` or fetched `availableShares`, call the `requestRedeem` method on the Pool contract to initiate your withdrawal.

#### Function signature

```solidity
function requestRedeem(
	uint256 shares,   // Shares to redeem (from Step 1 or Step 2)
	address receiver  // Address to receive the assets
)
```

#### Code example using Maple SDK

```typescript
import { BigNumber, providers, Wallet } from "ethers";
import { poolV2 } from "@maplelabs/maple-js";

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupPool = poolV2.core.connect(SYRUP_USDC_POOL, signer);

  const account = await signer.getAddress();

  const requestRedeemReceipt = await syrupPool.requestRedeem(
    sharesToRedeem,
    account
  );
  await requestRedeemReceipt.wait();
};

main();
```

### Step 4 - Await Withdrawal Completion

Once the transaction is successful and there is sufficient liquidity in the pool, the withdrawal will be processed within a few minutes. You can get the current status of the withdrawal queue either directly from `WithdrawalManagerQueue` contract or through Maple GraphQL API:

#### Example query

```gql
query GetPoolV2Queue($id: ID!) {
  poolV2(id: $id) {
    withdrawalManagerQueue {
      totalShares
      nextRequest {
        id
        shares
        status
      }
    }
  }
}
```

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

```typescript
import { gql, GraphQLClient } from "graphql-request";

interface MapleWithdrawalManagerQueue {
  totalShares: string;
  nextRequest: {
    id: string;
    shares: string;
    status: string;
  };
}

interface MaplePool {
  withdrawalManagerQueue: MapleWithdrawalManagerQueue;
}

interface QueryResponse {
  poolV2: MaplePool;
}

const query = gql`
  query GetPoolV2Queue($poolId: ID!) {
    poolV2(id: $poolId) {
      withdrawalManagerQueue {
        totalShares
        nextRequest {
          id
          shares
          status
        }
      }
    }
  }
`;
const client = new GraphQLClient(MAPLE_API_URL);

const main = async () => {
  const { poolV2 } = await client.request<QueryResponse>(query, {
    poolId: SYRUP_USDC,
  });

  if (poolV2) {
    const { withdrawalManagerQueue } = poolV2;

    console.log(
      `Total shares in the queue ${withdrawalManagerQueue.totalShares}`
    );
    console.log(
      `Next request ${withdrawalManagerQueue.nextRequest.id}: ${withdrawalManagerQueue.nextRequest.shares} shares. ${withdrawalManagerQueue.nextRequest.status}`
    );
  }
};

main();
```

## Edge cases

### User not authorized

When you try to `deposit` or `depositWithPermit` and get error `SR:D:NOT_AUTHORIZED` it means account you are trying to deposit with is not authorized into Syrup USD. In order to authorize you need to perform `authorizeAndDeposit` or `authorizeAndDepositWithPermit`

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

**Solution:**

```typescript
import { BigNumber, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const { bitmap, deadline, sig } = authorize(); // Please contact us to get information about authorization

  const authorizeAndDepositReceipt = await syrupRouter.authorizeAndDeposit(
    bitmap,
    deadline,
    sig.v,
    sig.r,
    sig.s,
    amount,
    utils.formatBytes32String("")
  );
  await authorizeAndDepositReceipt.wait();
};

main();
```

### Insufficient approval

When you try to `deposit` or `depositWithPermit` and get error `SR:D:TRANSFER_FROM_FAIL` it means that `SyrupRouter` could not transfer lending tokens on your behalf. Make sure amount you are trying to deposit matches current approval for `SyrupRouter`, if it doesn't please increase approval.

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

**Solution:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const account = await signer.getAddress();
  const allowance = await usdc.allowance(account, SYRUP_USDC_ROUTER_ADDRESS);

  if (allowance.lt(amount)) {
    const approveReceipt = await usdc.approve(
      SYRUP_USDC_ROUTER_ADDRESS,
      amount,
    );
    await approveReceipt.wait();
  }

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

### Invalid signature

When you try to `depositWithPermit` and get error `ERC20:P:INVALID_SIGNATURE` it means that recovered address from signature is not matching address that tries to deposits. Please make sure that signature is signed by the account that executes transaction.

### Expired signature

When you try to `depositWithPermit` and get error `ERC20:P:EXPIRED` it means your permit signature is expired. Make sure that the deadline you set on the signature has enough threshold to execute the transaction.

### Insufficient gas

When transactions fail due to insufficient gas, increase the gas limit in your transaction parameters. Syrup operations require more gas than simple token transfers due to the complex authorization and routing logic.

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

**Solution:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  // Estimate gas and add 20%
  const gasEstimate = await syrupRouter.estimateGas.deposit(
    amount,
    utils.formatBytes32String("")
  );
  const gasLimit = gasEstimate.mul(120).div(100);

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String(""),
    { gasLimit }
  );
  await depositReceipt.wait();
};

main();
```

### Pool deposit limit exceeded

When you encounter error `P:DEPOSIT_GT_LIQ_CAP`, it means the deposit amount exceeds the pool's deposit limit. Check the pool's current capacity before attempting large deposits.

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

**Solution:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const account = await signer.getAddress();
  const syrupPool = poolV2.core.connect(
    SYRUP_POOL,
    signer,
  );

  const maxDeposit = await syrupPool.maxDeposit(account);

  if (maxDeposit.lt(amount)) {
    amount = maxDeposit
  }

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String("")
  );
  await depositReceipt.wait();
};

main();
```

In case you want to perform deposit larger than the limit please contact the Syrup team via [Telegram](https://t.me/syrupfi)

## FAQ

<details>

<summary>What is the authorize and deposit function with permit?</summary>

The `authorizeAndDepositWithPermit` function combines three operations into a single transaction:

1. **Authorization**: Grants permission to deposit into Syrup pools (required for first-time users)
2. **Permit**: Provides gasless token approval using [EIP-2612](https://eips.ethereum.org/EIPS/eip-2612) standard
3. **Deposit**: Transfers tokens and mints pool shares

This function is ideal for first-time users who want to deposit USDC without requiring separate authorization and approval transactions. It saves gas and improves user experience by reducing the number of required transactions from three to one.

**Note:** Only available for USDC deposits, not USDT.

</details>

<details>

<summary>What are the permit signature parameters?</summary>

There are 5 parameters required for permit signature:

- **`owner`** - The wallet address that owns the tokens and is granting permission (typically the user's address)
- **`spender`** - The contract address receiving approval (in our case it will be the `SyrupRouter` contract address)
- **`value`** - The token amount in smallest units (for USDC: 6 decimals, e.g., 1000000 = 1 USDC) that the spender is allowed to spend.
- **`nonce`** - A unique number preventing replay attacks (get by calling `nonces(address)` on the token contract). It increments with each permit signature used.
- **`deadline`** - Unix timestamp when the permit expires

**Example:**

```typescript
const permitMessage = {
  owner: account,
  spender: SYRUP_USDC_ROUTER_ADDRESS,
  value: "1000000", // 1 USDC
  nonce: await usdc.nonces(account),
  deadline: Math.floor(Date.now() / 1000) + 3600, // 1 hour from now
};
```

</details>

<details>

<summary>How do withdrawals work?</summary>

Withdrawals follow a queue-based system:

1. **Request**: Call `requestRedeem()` to enter the withdrawal queue
2. **Queue Position**: Withdrawals are processed first-in, first-out (FIFO)
3. **Processing**: When pool liquidity is available, withdrawals are automatically processed
4. **Completion**: Assets are sent directly to your wallet (no additional transaction required)

**Timeline:**

- Most withdrawals process within 24 hours
- During low liquidity periods, it may take up to 30 days
- No penalties for withdrawing, but you stop earning yield once you request withdrawal

</details>

<details>

<summary>Do I need authorization for smart contract integration?</summary>

Yes, authorization is required for all Syrup deposits. Syrup is built on Maple Protocol, which uses a permissioning system for institutional-grade security.

**Authorization process:**

1. Contact the Syrup team via [Telegram](https://t.me/syrupfi) for eligibility verification
2. Receive authorization signature parameters
3. Use `authorizeAndDeposit` or `authorizeAndDepositWithPermit` for first deposit
4. Subsequent deposits only need `deposit` or `depositWithPermit`

Once authorized, the permission persists across all Syrup pools and future deposits.

</details>
