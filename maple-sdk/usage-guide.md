# Usage Guide

This guide will help you understand how to use the Maple SDK for various tasks, such as connecting to contracts and executing transactions.

# Overview

The Maple SDK simplifies interacting with the Maple Protocol's smart contracts on the Ethereum blockchain. It includes address mappings for each contract to facilitate deployment to different networks and environments.

There are two networks:

1. **Mainnet**: The main Ethereum network, where real-world transactions occur.
2. **Goerli**: A test network (testnet) for Ethereum, where developers can test their dApps and contracts with test tokens.

Each network has two environments:

1. **Prod**: The production environment, where the official, stable versions of the contracts and subgraph, API and web application are deployed.
2. **Dev**: The development environment, where new features or updates are tested before being deployed to the production environment.

Access addresses from the `addresses` object exported from `maple-js`. See a list of available contracts in `src/addresses/*.ts`.

The available combinations are:

- `mainnet-prod`: Production environment on the main Ethereum network
- `mainnet-dev`: Development environment on the main Ethereum network
- `goerli-prod`: Production environment on the Goerli test network
- `goerli-dev`: Development environment on the Goerli test network

# Getting Started

Access contract addresses using the `addresses` object exported from `maple-js`.

To connect to a contract, you will need a contract address and a signer (usually a wallet instance). For more information on creating a signer, refer to the [ethers documentation](https://docs.ethers.io/v5/).

```js
import { addresses, mapleGlobals } from '@maplelabs/maple-js';

const contractAddress = addresses['mainnet-prod'].MapleToken;
const signer = new providers.JsonRpcProvider(RPC_ENDPOINT);

const contract = mapleGlobals.core.connect(contractAddress, signer);
```

# Interacting with Contracts

Once you are connected to a contract, you can call any of its available methods using the `contract` instance. The `maple-js` contracts use TypeChain, enabling you to see all available methods using IntelliSense in your IDE.

**Querying Contract Data**

For basic queries, such as fetching public variables or calling view functions, you can use the standard `await` pattern:

```js
const basicQuery = await contract.lpCooldownPeriod();
```

## Executing Transactions

When executing a transaction, such as calling a state-modifying function, you should use the `.wait()` method. This will resolve the Promise once the block containing your transaction has enough confirmations to be considered final:

```js
import { poolV2 } from '@maplelabs/maple-js';

const poolContract = poolV2.core.connect(poolAddress, new providers.JsonRpcProvider(RPC_ENDPOINT));

const receipt = await (await poolContract.deposit(depositAmount, account)).wait();
```
