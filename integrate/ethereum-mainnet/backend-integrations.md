---
description: >-
  Enable your users to deposit into syrupUSDC & syrupUSDT from your app via
  SDK/API on Ethereum mainnet. For wallets, apps, DEXes, custody solutions etc.
---

# Frontend Integration

{% hint style="info" %}
**Step-by-step**

**Deposit**:

1. [**Query the Maple API**](backend-integrations.md#id-1.-query-the-maple-api) to retrieve the necessary contract addresses.
2. [**Determine user authorization**](backend-integrations.md#id-2.-determine-user-authorization) as a Syrup lender.
3. [**Retrieve an authorization signature**](backend-integrations.md#id-3.-retrieve-authorization-signature) from the Maple API
4. [**Execute the Deposit**](backend-integrations.md#id-4.-execute-the-deposit) (authorize and deposit, or deposit only).

**Withdrawal**:

1. [**Retrieve Pool Position**](backend-integrations.md#id-1.-retrieve-pool-position) from the Maple API
2. [**Calculate Shares to Redeem**](backend-integrations.md#id-2.-calculate-shares-to-redeem) from the Pool contract
3. [**Execute the Withdrawal**](backend-integrations.md#id-3.-execute-the-withdrawal) on the Pool contract
4. [**Await Withdrawal Completion**](backend-integrations.md#id-4.-await-withdrawal-completion)
{% endhint %}

## SDK and GraphQL API

All necessary ABIs and addresses are available in the Maple SDK or via GitHub:

* [**Maple JS GitHub (ABIs)**](https://github.com/maple-labs/maple-js/tree/main/src/abis)
* [**Maple JS GitHub (Addresses)**](https://github.com/maple-labs/maple-js/tree/main/src/addresses)

Within the SDK, both ABIs and network-specific addresses are accessible. The package can also be installed and used within applications.

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

To access the necessary data, use the GraphQL API:

{% tabs %}
{% tab title="Mainnet" %}
`https://api.maple.finance/v2/graphql`
{% endtab %}

{% tab title="Sepolia" %}
`https://sepolia.api.maple.finance/v2/graphql`
{% endtab %}
{% endtabs %}

**NOTE**: In order to perform the integration in Sepolia, you'll need to contact us at [partnerships@maple.finance](mailto:partnerships@maple.finance) to receive Sepolia `USDC`/`USDT` tokens.

## Deposit

### 1. Query the Maple API

Syrup's main contract, the `SyrupRouter`, is designed to allow authorized participants to securely access the yields available in the Maple ecosystem, abstracting all the complexity of the permissioning system. Each Syrup `PoolV2` has an associated `SyrupRouter`.

{% tabs %}
{% tab title="Mainnet" %}
**syrupUSDC**

<table><thead><tr><th width="224.8125">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://etherscan.io/address/0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b">0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://etherscan.io/address/0x134cCaaA4F1e4552eC8aEcb9E4A2360dDcF8df76">0x134cCaaA4F1e4552eC8aEcb9E4A2360dDcF8df76</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://etherscan.io/address/0x1bc47a0Dd0FdaB96E9eF982fdf1F34DC6207cfE3">0x1bc47a0Dd0FdaB96E9eF982fdf1F34DC6207cfE3</a></td></tr></tbody></table>

**syrupUSDT**

<table><thead><tr><th width="224.6953125">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://etherscan.io/address/0x356B8d89c1e1239Cbbb9dE4815c39A1474d5BA7D">0x356B8d89c1e1239Cbbb9dE4815c39A1474d5BA7D</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://etherscan.io/address/0xF007476Bb27430795138C511F18F821e8D1e5Ee2">0xF007476Bb27430795138C511F18F821e8D1e5Ee2</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://etherscan.io/address/0x86eBDf902d800F2a82038290B6DBb2A5eE29eB8C">0x86eBDf902d800F2a82038290B6DBb2A5eE29eB8C</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Sepolia" %}
**syrupUSDC**

<table><thead><tr><th width="225.05078125">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://sepolia.etherscan.io/address/0x2d8d21fee98d060655729efd7b14bc432c375ac1">0x2d8d21fee98d060655729efd7b14bc432c375ac1</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://sepolia.etherscan.io/address/0x5387ab37f93af968920af6c0faa6dbc52973b020">0x5387ab37f93af968920af6c0faa6dbc52973b020</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://sepolia.etherscan.io/address/0x2ff61035de7a1550219be12a6e9d33aa10b844b6">0x2ff61035de7a1550219be12a6e9d33aa10b844b6</a></td></tr></tbody></table>

**syrupUSDT**

<table><thead><tr><th width="225.046875">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://sepolia.etherscan.io/address/0x7679cbe9ae66298114ac6dac73487b63ac023c0b">0x7679cbe9ae66298114ac6dac73487b63ac023c0b</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://sepolia.etherscan.io/address/0x0b703919cf2d30dbb18bad6febe8f0ea4f191918">0x0b703919cf2d30dbb18bad6febe8f0ea4f191918</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://sepolia.etherscan.io/address/0xbbe2bf30b76729a4eb75bf40ced47a58000ae1d3">0xbbe2bf30b76729a4eb75bf40ced47a58000ae1d3</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

Router addresses can also be accessed via the GraphQL API.

#### Example query

{% code lineNumbers="true" %}
```gql
query {
  poolV2S(where: { syrupRouter_not: null }) {
    id
    name
    asset {
      symbol
      decimals
    }
    syrupRouter {
      id
    }
    withdrawalManagerQueue {
      id
    }
    poolPermissionManager {
      id
    }
  }
}
```
{% endcode %}

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

{% code overflow="wrap" lineNumbers="true" fullWidth="false" expandable="true" %}
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
{% endcode %}

### Listen for Router DepositData events (optional)

If you want to correlate deposits off-chain, subscribe to `DepositData(address owner, uint256 amount, bytes32 depositData)` on the `syrupRouter` address returned by GraphQL. Emitters include the caller’s address, raw deposit amount, and a `bytes32` opaque identifier you pass in the `deposit` call.

### Authorization signature verification (auditors)

Maple returns an authorization signature (v/r/s) used by `authorizeAndDeposit`. The router verifies a digest constructed from `chainId`, `router address`, `owner`, `owner nonce`, `bitmap`, and `deadline`. For internal reviews, auditors can reproduce the `ecrecover` and confirm the signer is a `permissionAdmin` in `PoolPermissionManager`.

It is important to note that the query uses the `syrupRouter_not` filter to return specifically Syrup pools.

**Response Fields:**

* `poolV2S.id`: The Syrup Pool contract address.
* `poolV2S.syrupRouter.id`: The `SyrupRouter` contract address.

These addresses can then be used to interact with the `SyrupRouter` contract.

### 2. Determine User Authorization

Before depositing, check if a user is already authorized by querying the `Account` entity. This is necessary to perform a deposit.

#### Example Query

{% code lineNumbers="true" expandable="true" %}
```gql
query GetMapleAccount($accountId: ID!) {
  account(id: $accountId) {
    isSyrupLender
  }
}
```
{% endcode %}

**NOTE**: The account ID must be provided in lowercase.

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

{% code overflow="wrap" lineNumbers="true" expandable="true" %}
```typescript
import { gql, GraphQLClient } from 'graphql-request';

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
  const account = '0x123...';

  const { account: mapleAccount } = await client.request<QueryResponse>(query, {
    accountId: account.toLowerCase(),
  });

  if (mapleAccount) {
    console.log(`Can user ${account} deposit into Syrup: ${mapleAccount.isSyrupLender}`);
  } else {
    console.log('Account not found');
  }
};

main();
```
{% endcode %}

If `isSyrupLender = true`, the user is already authorized in the `Pool Permission Manager` and can deposit into Syrup pools. Otherwise, the user must perform authorization before their initial deposit.

### 3. Retrieve Authorization Signature

**Note:** This step is only required if `isSyrupLender = false` was returned in the previous step. Otherwise, continue to the next step.

The Maple Protocol is geared towards institutions and has a permissioning system that requires allowlisting for executing most functions. For pool deposits, in general, lenders need to have their wallet allowlisted in Maple's `Pool Permission Manager`. Aiming to abstract and simplify the process, the `SyrupRouter` integrates directly with the `Pool Permission Manager` to allow for valid users to self-authorize and deposit in a single transaction assuming the user meets eligibility requirements.

To retrieve the authorization signature, contact us at [partnerships@maple.finance](mailto:partnerships@maple.finance).

{% hint style="info" %}
Deposit data

* Replace `0:<integrator-name>` with your integrator identifier (e.g. `0:acme-protocol`).
* Maple will provide the final `depositData` for production.
* Must be passed as `bytes32` (32-byte hex).
{% endhint %}

### 4. Execute the Deposit

The first time an asset (e.g., `USDC`, `USDT`) is lent to Syrup, it may be necessary to allow the contract to interact with the asset. This is a common transaction on Ethereum.

Depositing into a pool requires a transaction. Once the transaction has been processed, `SyrupRouter` will accept the lending tokens and Pool LP (Liquidity Provider) tokens will be received.

Each pool contract inherits the [ERC-4626](https://erc4626.info/) standard, also known as the `Tokenized Vault` Standard. This standard informs how the LP Tokens accrue value from borrower repayments of loans.

#### `isSyrupLender = true` - User is Already Authorized

The `deposit` or `depositWithPermit` method can be called directly on `SyrupRouter`.

{% code lineNumbers="true" %}
```solidity
function deposit(uint256 assets, bytes32 depositData)
```
{% endcode %}

**NOTE**: `depositData` is an optional field that does not need to be provided.

![deposit()](https://github.com/maple-labs/syrup-router/assets/16119563/2e911fe4-cd81-4b58-a290-6809d7bba125)

#### Code example using Maple SDK for `USDC` or `USDT`.

{% tabs %}
{% tab title="USDC" %}
{% code overflow="wrap" lineNumbers="true" expandable="true" %}
```typescript
import { BigNumber, Contract, providers, utils, Wallet } from 'ethers';
import { addresses, syrupUtils } from '@maplelabs/maple-js';

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupRouter = syrupUtils.syrupRouter.connect(
    SYRUP_USDC_ROUTER_ADDRESS, // Explained how to get in previous step
    signer
  );
  const usdc = new Contract(addresses['mainnet-prod'].USDC, USDC_ABI, signer);

  const amount = BigNumber.from(1000000);

  const approveReceipt = await usdc.approve(SYRUP_USDC_ROUTER_ADDRESS, amount);
  await approveReceipt.wait();

  const depositReceipt = await syrupRouter.deposit(amount, utils.formatBytes32String('0:<integrator-name>'));
  await depositReceipt.wait();
};

main();
```
{% endcode %}
{% endtab %}

{% tab title="USDT" %}
{% code lineNumbers="true" expandable="true" %}
```typescript
import { BigNumber, Contract, providers, utils, Wallet } from 'ethers';
import { addresses, syrupUtils, environmentMocks } from '@maplelabs/maple-js';

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupRouter = syrupUtils.syrupRouter.connect(
    SYRUP_USDT_ROUTER_ADDRESS, // Explained how to get in previous step
    signer
  );

  const usdt = new Contract(addresses['mainnet-prod'].USDT, USDT_ABI, signer);

  const amount = BigNumber.from(1000000);

  const approveReceipt = await usdt.approve(SYRUP_USDT_ROUTER_ADDRESS, amount);
  await approveReceipt.wait();

  const depositReceipt = await syrupRouter.deposit(amount, utils.formatBytes32String('0:<integrator-name>'));
  await depositReceipt.wait();
};

main();
```
{% endcode %}
{% endtab %}
{% endtabs %}

Deposits into Syrup can also be made with gasless approval using `permit`. For more information, see https://eips.ethereum.org/EIPS/eip-2612.

{% code lineNumbers="true" expandable="true" %}
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
{% endcode %}

**NOTE**: `depositWithPermit` is only available for `Syrup USDC`.

![depositWithPermit()](https://github.com/maple-labs/syrup-router/assets/16119563/db8192f8-c9d3-42d9-9522-9a91df95fb5d)

#### Code example using Maple SDK

{% code overflow="wrap" lineNumbers="true" expandable="true" %}
```typescript
import { BigNumber, Contract, providers, utils, Wallet } from 'ethers';
import { addresses, syrupUtils, erc20 } from '@maplelabs/maple-js';

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupRouter = syrupUtils.syrupRouter.connect(
    SYRUP_USDC_ROUTER_ADDRESS, // Explained how to get in previous step
    signer
  );

  const usdc = new Contract(addresses['mainnet-prod'].USDC, USDC_ABI, signer);

  const amount = BigNumber.from(1000000);
  const account = await signer.getAddress();

  const deadline = Math.floor(Date.now() / 1000) + 3600;
  const nonce = await usdc.nonces(account);
  const network = await provider.getNetwork();

  // EIP-712 domain for USDC
  const domain = {
    name: await usdc.name(),
    version: '2', // "1" for Sepolia
    chainId: network.chainId,
    verifyingContract: addresses['mainnet-prod'].USDC,
  };

  // EIP-712 types for permit
  const types = {
    Permit: [
      { name: 'owner', type: 'address' },
      { name: 'spender', type: 'address' },
      { name: 'value', type: 'uint256' },
      { name: 'nonce', type: 'uint256' },
      { name: 'deadline', type: 'uint256' },
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
    utils.formatBytes32String('0:<integrator-name>')
  );
  await depositWithPermitReceipt.wait();
};

main();
```
{% endcode %}

#### `isSyrupLender = false` - User Requires Authorization

1. Retrieve a signature from the Maple API. Follow the instructions received from the team as mentioned in the step above.
2. Use the retrieved signature with the `authorizeAndDeposit` or `authorizeAndDepositWithPermit` method on `SyrupRouter`.

{% code lineNumbers="true" expandable="true" %}
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
{% endcode %}

![authAndDeposit()](https://github.com/maple-labs/syrup-router/assets/16119563/1c59065b-c1cb-4b55-9ab8-1d04ebb9fe83)

#### Code example using Maple SDK for `USDC` or `USDT`.

{% code overflow="wrap" lineNumbers="true" expandable="true" %}
```typescript
import { BigNumber, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ... // Exact same steps as regular deposit

  const { bitmap, deadline, sig } = authorize(); // Contact the Syrup team for authorization information

  const authorizeAndDepositReceipt = await syrupRouter.authorizeAndDeposit(
    bitmap,
    deadline,
    sig.v,
    sig.r,
    sig.s,
    amount,
    utils.formatBytes32String('0:<integrator-name>')
  );
  await authorizeAndDepositReceipt.wait();
};

main();
```
{% endcode %}

Deposits into Syrup can also be made with gasless approval using `permit`. For more information, see https://eips.ethereum.org/EIPS/eip-2612.

{% code lineNumbers="true" expandable="true" %}
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
{% endcode %}

**NOTE**: `authorizeAndDepositWithPermit` is only available for `Syrup USDC`.

![authAndDepositWithPermit()](https://github.com/maple-labs/syrup-router/assets/16119563/c0e4d64f-e092-46b0-9b7f-00def236ace7)

#### Code example using Maple SDK

{% code overflow="wrap" lineNumbers="true" expandable="true" %}
```typescript
import { BigNumber, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () {
  ... // Exact same steps as regular depositWithPermit

  const { bitmap, authDeadline, authSig } = authorize(); // Contact the Syrup team for authorization information

  const authorizeAndDepositWithPermitReceipt = await syrupRouter.authorizeAndDepositWithPermit(
    bitmap,
    authDeadline,
    authSig.v,
    authSig.r,
    authSig.s,
    amount,
    utils.formatBytes32String('0:<integrator-name>'),
    deadline,
    sig.v,
    sig.r,
    sig.s
  );
  await authorizeAndDepositWithPermitReceipt.wait();
}

main();
```
{% endcode %}

## Withdraw

### 1. Retrieve Pool Position

Query the Maple API for the user's pool position data using the `PoolV2Position` field in the `Account` query:

#### Data model

{% code lineNumbers="true" %}
```gql
PoolPositionV2 {
	availableBalance // The pool position in the pool asset.
	availableShares // The underlying shares representing that position.
	redeemRequested // A boolean indicating if a redeem request is active.
}
```
{% endcode %}

#### Example query

{% code lineNumbers="true" %}
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
{% endcode %}

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

{% code overflow="wrap" lineNumbers="true" expandable="true" %}
```typescript
import { gql, GraphQLClient } from 'graphql-request';

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
  const account = '0x123...';

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
    console.log('Account not found');
  }
};

main();
```
{% endcode %}

### 2. Calculate Shares to Redeem

* Withdrawal requests must be expressed in shares. Although the Maple API provides both `availableShares` and `availableBalance`, losses or impairments on the pool may affect the value of assets relative to shares.
* To ensure accuracy, convert the desired asset amount to "exit shares" using the pool contract's conversion method.
* These transactions leverage the `ERC-4626` tokenized vault standard. For more information, see https://ethereum.org/en/developers/docs/standards/tokens/erc-4626/.

#### Function signature

{% code overflow="wrap" lineNumbers="true" %}
```solidity
function convertToExitShares(uint256 assets_) external view returns (uint256 shares_);
```
{% endcode %}

#### Code example using Maple SDK

{% code lineNumbers="true" expandable="true" %}
```typescript
import { BigNumber, providers } from 'ethers';
import { poolV2 } from '@maplelabs/maple-js';

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);

  const syrupPool = poolV2.core.connect(SYRUP_USDC, provider);

  const amount = BigNumber.from(10 ** 8);

  const sharesToRedeem = await syrupPool.convertToExitShares(amount);

  console.log(`${amount.toString()} is equal to ${sharesToRedeem.toString()}`);
};

main();
```
{% endcode %}

### 3. Execute the Withdrawal

After calculating `sharesToRedeem` or fetching `availableShares`, call the `requestRedeem` method on the Pool contract to initiate the withdrawal.

#### Function signature

{% code lineNumbers="true" %}
```solidity
function requestRedeem(
	uint256 shares,   // Shares to redeem (from Step 1 or Step 2)
	address receiver  // Address to receive the assets
)
```
{% endcode %}

#### Code example using Maple SDK

{% code lineNumbers="true" expandable="true" %}
```typescript
import { BigNumber, providers, Wallet } from 'ethers';
import { poolV2 } from '@maplelabs/maple-js';

const main = async () => {
  const provider = new providers.JsonRpcProvider(RPC_URL);
  const signer = new Wallet(PRIVATE_KEY, provider);

  const syrupPool = poolV2.core.connect(SYRUP_USDC_POOL, signer);

  const account = await signer.getAddress();

  const requestRedeemReceipt = await syrupPool.requestRedeem(sharesToRedeem, account);
  await requestRedeemReceipt.wait();
};

main();
```
{% endcode %}

### 4. Await Withdrawal Completion

Withdrawals are processed automatically by Maple. If there is sufficient liquidity in the pool, the withdrawal will be processed within a few minutes. Expected processing time is typically less than 2 days, but it can take up to 30 days depending on available liquidity. The current status of the withdrawal queue can be retrieved either directly from the `WithdrawalManagerQueue` contract or through the Maple GraphQL API:

#### Example query

{% code lineNumbers="true" %}
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
{% endcode %}

#### Code example using [**graphql-request**](https://www.npmjs.com/package/graphql-request)

{% code overflow="wrap" lineNumbers="true" expandable="true" %}
```typescript
import { gql, GraphQLClient } from 'graphql-request';

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

    console.log(`Total shares in the queue ${withdrawalManagerQueue.totalShares}`);
    console.log(
      `Next request ${withdrawalManagerQueue.nextRequest.id}: ${withdrawalManagerQueue.nextRequest.shares} shares. ${withdrawalManagerQueue.nextRequest.status}`
    );
  }
};

main();
```
{% endcode %}

## Edge Cases

<details>

<summary>User Not Authorized</summary>

When attempting to use `deposit` or `depositWithPermit` and receiving the error `SR:D:NOT_AUTHORIZED`, it indicates that the account being used for deposit is not authorized in Syrup USD. To authorize the account, use `authorizeAndDeposit` or `authorizeAndDepositWithPermit`.

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String('0:<integrator-name>')
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

  const { bitmap, deadline, sig } = authorize(); // Contact the Syrup team for authorization information

  const authorizeAndDepositReceipt = await syrupRouter.authorizeAndDeposit(
    bitmap,
    deadline,
    sig.v,
    sig.r,
    sig.s,
    amount,
    utils.formatBytes32String('0:<integrator-name>')
  );
  await authorizeAndDepositReceipt.wait();
};

main();
```

</details>

<details>

<summary>Insufficient Approval</summary>

When attempting to use `deposit` or `depositWithPermit` and receiving the error `SR:D:TRANSFER_FROM_FAIL`, it indicates that `SyrupRouter` could not transfer lending tokens. Ensure that the deposit amount matches the current approval for `SyrupRouter`. If it does not, increase the approval.

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String('0:<integrator-name>')
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
    utils.formatBytes32String('0:<integrator-name>')
  );
  await depositReceipt.wait();
};

main();
```

</details>

<details>

<summary>Invalid Signature</summary>

When attempting to use `depositWithPermit` and receiving the error `ERC20:P:INVALID_SIGNATURE`, it indicates that the recovered address from the signature does not match the address attempting to deposit. Ensure that the signature is signed by the account executing the transaction.

</details>

<details>

<summary>Expired Signature</summary>

When attempting to use `depositWithPermit` and receiving the error `ERC20:P:EXPIRED`, it indicates that the permit signature has expired. Ensure that the deadline set on the signature provides sufficient time to execute the transaction.

</details>

<details>

<summary>Insufficient Gas</summary>

When transactions fail due to insufficient gas, increase the gas limit in the transaction parameters. Syrup operations require more gas than simple token transfers due to the complex authorization and routing logic.

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String('0:<integrator-name>')
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
    utils.formatBytes32String('0:<integrator-name>')
  );
  const gasLimit = gasEstimate.mul(120).div(100);

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String('0:<integrator-name>'),
    { gasLimit }
  );
  await depositReceipt.wait();
};

main();
```

</details>

<details>

<summary>Pool Deposit Limit Exceeded</summary>

When encountering error `P:DEPOSIT_GT_LIQ_CAP`, it means the deposit amount exceeds the pool's deposit limit. Check the pool's current capacity before attempting large deposits.

**Problem:**

```typescript
import { BigNumber, Contract, providers, utils, Wallet } from "ethers";
import { addresses, syrupUtils } from "@maplelabs/maple-js";

const main = async () => {
  ...

  const depositReceipt = await syrupRouter.deposit(
    amount,
    utils.formatBytes32String('0:<integrator-name>')
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
    utils.formatBytes32String('0:<integrator-name>')
  );
  await depositReceipt.wait();
};

main();
```

To perform a deposit larger than the limit, contact the Syrup team via [Telegram](https://t.me/syrupfi).

</details>

## FAQ

<details>

<summary>What is the difference between Syrup and Maple?</summary>

Syrup is the protocol - the smart contracts that power onchain lending. Maple encompasses the entities that conduct institutional lending services using this infrastructure.

**For developers:** You'll be integrating with Syrup (the protocol), while Maple handles the institutional lending operations.

</details>

<details>

<summary>What is the authorize and deposit function with permit?</summary>

The `authorizeAndDepositWithPermit` function combines three operations into a single transaction:

1. **Authorization**: Grants permission to deposit into Syrup pools (required for first-time users)
2. **Permit**: Provides gasless token approval using [EIP-2612](https://eips.ethereum.org/EIPS/eip-2612) standard
3. **Deposit**: Transfers tokens and mints pool shares

This function is ideal for first-time users who want to deposit USDC without requiring separate authorization and approval transactions. It saves gas and improves user experience by reducing the number of required transactions from three to one.

**NOTE**: Only available for USDC deposits, not USDT.

</details>

<details>

<summary>What are the permit signature parameters?</summary>

There are 5 parameters required for permit signature:

* **`owner`**: The wallet address that owns the tokens and is granting permission (typically the user's address)
* **`spender`**: The contract address receiving approval (the `SyrupRouter` contract address)
* **`value`**: The token amount in smallest units (for USDC: 6 decimals, e.g., 1000000 = 1 USDC) that the spender is allowed to spend
* **`nonce`**: A unique number preventing replay attacks (obtained by calling `nonces(address)` on the token contract). It increments with each permit signature used
* **`deadline`**: Unix timestamp when the permit expires

**Example**

```typescript
const permitMessage = {
  owner: account,
  spender: SYRUP_USDC_ROUTER_ADDRESS,
  value: '1000000', // 1 USDC
  nonce: await usdc.nonces(account),
  deadline: Math.floor(Date.now() / 1000) + 3600, // 1 hour from now
};
```

</details>

<details>

<summary>Do I need authorization for smart contract integration?</summary>

Yes, authorization is required for all Syrup deposits. Syrup protocol is built by Maple, which uses a permissioning system for institutional-grade security.

**Authorization Process**

1. Contact us at [partnerships@maple.finance](mailto:partnerships@maple.finance) for eligibility verification
2. Receive authorization signature parameters
3. Use `authorizeAndDeposit` or `authorizeAndDepositWithPermit` for first deposit
4. Subsequent deposits only need `deposit` or `depositWithPermit`

Once authorized, the permission persists across all Syrup pools and future deposits.

</details>

<details>

<summary>How do withdrawals work?</summary>

Withdrawals follow a queue-based system:

1. **Request**: Call `requestRedeem()` to enter the withdrawal queue
2. **Queue Position**: Withdrawals are processed first-in, first-out (FIFO)
3. **Processing**: When pool liquidity is available, withdrawals are automatically processed
4. **Completion**: Assets are sent directly to the wallet (no additional transaction required)

**Timeline**

* Expected processing time is typically less than 2 days
* During low liquidity periods, it may take up to 30 days
* No penalties for withdrawing, but yield stops accumulating once withdrawal is requested

</details>

<details>

<summary>How long do withdrawals take?</summary>

syrupUSDC & syrupUSDT normally have instant liquidity, but in rare cases withdrawals can take around 24h with the maximum possible time being 30 days. You can see the available funds to withdraw in the Liquidity section of the [Details page](https://app.maple.finance/earn/details).

</details>

<details>

<summary>How can I get the APY data for syrupUSDC or syrupUSDT?</summary>

Querying the GraphQL API is the simplest way to get APY data for syrupUSDC or syrupUSDT into your app.

**Example request**

```
{
  poolV2(id: "0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b") {
    name
    weeklyApy
    monthlyApy
  }
  syrupGlobals {
    dripsYieldBoost
  }
}
```

**This returns**

```
{
  "data": {
    "poolV2": {
      "name": "Syrup USDC",
      "weeklyApy": "69937809610000000000000000000",
      "monthlyApy": "67212806350000000000000000000"
    },
    "syrupGlobals": {
      "apy": "69731920498003078965054825961",
      "dripsYieldBoost": "0"
    }
  }
}
```

You can get the APY % by using the fomula: `APY % = rawValue / 1e28`

In the example above, the monthly base APY is 6.72%. Drips have been discontinued after Q4 2025 in favour of rewards distributed via Merkl for using partner products. You can discard `dripsYieldBoost` going forward. Read more: [drips-rewards.md](../../syrupusdc-usdt-for-lenders/drips-rewards.md "mention")

</details>

<details>

<summary>How can I get the price received on redemption for syrupUSDC or syrupUSDT?</summary>

syrupUSDC and syrupUSDT are redeemed at the smart contract exchange rate at the point of processing the withdrawal, incurring no slippage.

You can get the spot exchange rate for syrupUSDC to USDC or syrupUSDT to USDT by querying the GraphQL API.

**Example request**

```
{
  account(id: "0xyourwallet") {
    poolV2Positions {
      pool {
        asset {
          symbol
          decimals
        }
        id
        name
      }
      lendingBalance
      totalShares
    }
  }
}

```

**This returns**

```
{
  "data": {
    "account": {
      "poolV2Positions": [
        {
          "pool": {
            "asset": {
              "symbol": "USDC",
              "decimals": 6
            },
            "id": "0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b",
            "name": "Syrup USDC"
          },
          "lendingBalance": "3102053352414",
          "totalShares": "2742550894631"
        }
      ]
    }
  }
}
```

The ratio of `lendingBalance` / `totalShares` is the spot exchange rate.

</details>
