# Usage Guide

## Overview

The Maple SDK simplifies interaction with Maple Protocol smart contracts on Ethereum. It supports Mainnet, Base, and Sepolia networks, with production and development environments. This guide provides both conceptual understanding and practical examples, including a full integration with a React application.

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

## Checking Permissions and Onboarding

Before a wallet can deposit into a Maple pool, it must have a sufficient `permissionsBitmap` set. This is automatically managed when users onboard and verify their accounts on the Maple Webapp. Once verified, all wallets added to the account will receive the necessary permissions. For Syrup pools, permissions are granted after an initial deposit through the UI.

### Onboarding and Verification

To ensure your wallet has the necessary permissions:

1. **Maple Webapp**: Onboard and verify your account at [Maple Webapp](https://app.maple.finance/). Add your wallets to the account to automatically receive the required permissions.
2. **Syrup Pools**: Make an initial deposit through the [Syrup UI](https://syrup.fi/) to set permissions.

### Querying Permissions with Subgraph

For those interested in the technical details, you can query the subgraph to check permission information. This is useful for verifying the current state of permissions.

**Example Query**

The following GraphQL query can be used to retrieve the necessary permission information for a specific pool and account:

```graphql
{
  poolV2(id: "0xc1dd3f011290f212227170f0d02f511ebf57e433") {
    permissionLevel
    poolLevelBitmap
    functionLevelBitmaps {
      id
      bitmap
    }
  }
  account(id: "0xAccountId") {
    permissionsBitmap
  }
}
```

**API Endpoint**

Use the following endpoint to execute the query: `https://api.maple.finance/v2/graphql`

**Explanation**

- **poolV2**: Retrieves pool permission details.
- **account**: Retrieves the `permissionsBitmap` for the account.

Ensure that the account's `permissionsBitmap` meets or exceeds the pool's requirements before attempting to deposit. For more details on permissions, refer to the [Pool Permission Manager documentation](technical-resources/singletons/pool-permission-manager.md).

## Example Integration with React

This section provides a practical example of how to integrate the Maple SDK into a React application. This example demonstrates connecting to a wallet, approving a token transfer, depositing into a pool, and requesting a withdrawal.

### Prerequisites

Ensure you have the following installed and set up:

- Node.js and npm
- A React application (created using `create-react-app` or similar)
- ethers v5 installed in your project
- MetaMask/Rabby extension installed in your browser
- A wallet with sufficient permissions to interact with the pool (see [Checking Permissions with Subgraph](#checking-permissions-with-subgraph))

### Step-by-Step Guide

1. **Install the Maple SDK**

   First, ensure you have the Maple SDK installed in your project:

   ```bash
   npm install @maplelabs/maple-js
   ```

2. **Set Up Your React Component**

   Below is a complete example of a React component that interacts with the Maple Protocol:

   ```typescript
   import React, { useEffect, useState } from 'react';
   import { BigNumber, ethers } from 'ethers';
   import { addresses, poolV2, environmentMocks } from '@maplelabs/maple-js';

   const PROJECT = 'mainnet-prod';
   const POOL_ADDRESS = '0xc1dd3f011290f212227170f0d02f511ebf57e433'; // Blue Chip Secured Pool
   const ONE_HUNDRED_USDC = BigNumber.from(100).mul(10 ** 6);

   async function getPoolContract(poolAddress: string) {
     const provider = new ethers.providers.Web3Provider(
       (window as any).ethereum
     );
     const signer = provider.getSigner();
     return poolV2.core.connect(poolAddress, signer);
   }

   async function getERC20Contract(erc20Address: string) {
     const provider = new ethers.providers.Web3Provider(
       (window as any).ethereum
     );
     const signer = provider.getSigner();

     return environmentMocks.erc20.connect(erc20Address, signer);
   }

   function App() {
     const [account, setAccount] = useState<string | null>(null);

     useEffect(() => {
       const connectWallet = async () => {
         if (typeof (window as any).ethereum !== 'undefined') {
           try {
             // Request account access
             const provider = new ethers.providers.Web3Provider(
               (window as any).ethereum
             );
             await provider.send('eth_requestAccounts', []);

             // Get the signer
             const signer = provider.getSigner();

             // Get the connected account
             const address = await signer.getAddress();
             setAccount(address);

             console.log('Connected account:', address);
           } catch (error) {
             console.error('Error connecting to wallet:', error);
           }
         } else {
           console.error('MetaMask is not installed!');
         }
       };

       connectWallet();
     }, []);

     const handleApprove = async () => {
       if (!account) {
         console.error('No account connected');
         return;
       }

       const erc20Contract = await getERC20Contract(addresses[PROJECT].USDC);
       const transactionResponse = await erc20Contract.approve(
         POOL_ADDRESS,
         ONE_HUNDRED_USDC
       );
       const receipt = await transactionResponse.wait();

       console.log('Transaction confirmed:', receipt);
     };

     const handleDeposit = async () => {
       if (!account) {
         console.error('No account connected');
         return;
       }

       // Connect to the pool contract
       const poolContract = await getPoolContract(POOL_ADDRESS);

       // Execute the deposit method and wait for the transaction to be mined
       const transactionResponse = await poolContract.deposit(
         ONE_HUNDRED_USDC,
         account
       );
       const receipt = await transactionResponse.wait();

       console.log('Transaction confirmed:', receipt);
     };

     const handleRequestWithdrawal = async () => {
       if (!account) {
         console.error('No account connected');
         return;
       }

       const sharesAmount = BigNumber.from(10).mul(10 ** 6);

       // Connect to the pool contract
       const poolContract = await getPoolContract(POOL_ADDRESS);

       // Execute the requestRedeem method and wait for the transaction to be mined
       const receipt = await (
         await poolContract.requestRedeem(sharesAmount, account)
       ).wait();

       console.log('Transaction confirmed:', receipt);
     };

     return (
       <div
         style={{
           display: 'flex',
           justifyContent: 'center',
           alignItems: 'center',
           height: '100vh',
         }}
       >
         <div>
           <p>Interact with Maple Protocol</p>
           <button onClick={handleApprove}>Approve</button>
           <br />
           <button onClick={handleDeposit}>Deposit</button>
           <br />
           <button onClick={handleRequestWithdrawal}>Request withdrawal</button>
         </div>
       </div>
     );
   }

   export default App;
   ```

3. **Run Your Application**

   Ensure your application is running and MetaMask or any other wallet of your choice is connected to the desired network. You can now interact with the Maple Protocol using the buttons provided in the UI.
