# Usage Guide

## Overview

The Maple SDK simplifies interaction with Maple Protocol smart contracts on Ethereum. It supports Mainnet, Base, and Sepolia networks, with production and development environments.

There are three networks:

1. **Mainnet**: main Ethereum network.
2. **Base Mainnet**: Ethereum L2 network.
3. **Sepolia**: Ethereum test network (testnet).

Each network may have two environments:

1. **Prod**: production environment, where the official, stable versions of the contracts and subgraph, API and web applications are deployed.
2. **Dev**: development or staging environment, where new features or updates are tested before being deployed to the production environment.

Access addresses from the `addresses` object exported from `maple-js`. See a list of available contracts in `src/addresses/*.ts`.

The available combinations are:

- `mainnet-prod`: Production environment on the main Ethereum network
- `mainnet-dev`: Staging environment on the main Ethereum network
- `base-mainnet-prod`: Production environment on the Base L2 network
- `sepolia-prod`: Production environment on the Sepolia test network
- `sepolia-dev`: Development environment on the Sepolia test network

## Getting started

### Addresses

Access contract addresses using the `addresses` object:

```js
import { addresses } from '@maplelabs/maple-js';

// Returns the contract address for MapleToken on Ethereum Mainnet
const contractAddress = addresses.mainnet.MapleToken;
```

### Connecting to a Contract

To connect to a contract, you'll need its address and a signer. The `signer` should be an instance of a wallet that can sign transactions. Refer to the [ethers docs](https://docs.ethers.io/v5/) (or your choice of web3 library) for further assistance.

**Connecting to a Contract Usage**

```js
import { mapleGlobals } from '@maplelabs/maple-js';

const contractAddress = addresses.mainnet.MapleToken;
const signer = 'yourSigner';

const contract = mapleGlobals.core.connect(contractAddress, signer);
```

### Interacting with a Contract

Once connected to a contract, you can call any available methods using the `contract` instance. `maple-js` contracts use typechain, so you can see all available methods using intellisense in your IDE.

**Usage for Queries**

Basic queries can be called using the standard `await` pattern:

```js
const basicQuery = await contract.lpCooldownPeriod();
```

**Usage for Transactions**

When executing a transaction, use the `.wait()` method to resolve the Promise once the block containing your transaction has enough confirmations to be considered final:

```js
import { pool } from '@maplelabs/maple-js';

const poolContract = pool.core.connect(poolAddress, signer);
const method = await (await poolContract.deposit(depositAmount)).wait();
```
