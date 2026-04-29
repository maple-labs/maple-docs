---
description: >-
  Enable syrupUSDC deposits and withdrawals in your app via CCIP on chains other
  than Ethereum. For wallets, apps, DEXes, custody solutions etc.
---

# syrupUSDC Native Mint/Redeem

> **Deposits & withdrawals for Solana & EVM chains are only available for syrupUSDC. syrupUSDT support is coming in Q2 2026.**

{% hint style="info" %}
Step-by-step

1. [**Overview**](syrupusdc-native-mint-redeem.md#overview)
2. [**Prerequisites**](syrupusdc-native-mint-redeem.md#prerequisites)
3. [**Receiver Contract Details**](syrupusdc-native-mint-redeem.md#receiver-contract-details)
4. [**Message Structure**](syrupusdc-native-mint-redeem.md#message-structure)
5. [**Building the Message**](syrupusdc-native-mint-redeem.md#building-the-message)
6. [**Gas Estimation**](syrupusdc-native-mint-redeem.md#gas-estimation)
7. [**Fee Estimation**](syrupusdc-native-mint-redeem.md#fee-estimation)
8. [**Executing the Transaction**](syrupusdc-native-mint-redeem.md#executing-the-transaction)
9. [**Complete Code Example**](syrupusdc-native-mint-redeem.md#complete-code-example)
10. [**Message Monitoring with CCIP API**](syrupusdc-native-mint-redeem.md#message-monitoring)
11. [**Important Notes**](syrupusdc-native-mint-redeem.md#important-notes)
{% endhint %}

## Overview <a href="#overview" id="overview"></a>

Maple's receiver contract processes programmable token transfers via CCIP messages. The receiver contract handles two types of operations:

* **Deposits**: When USDC is sent to the receiver, it processes a deposit operation
* **Withdrawals**: When SyrupUSDC is sent to the receiver, it processes a withdrawal operation

This guide covers sending messages from **Solana** to **Ethereum** (testnet), but the same principles apply to EVM-to-EVM transfers with appropriate token address changes.

## Step By Step Guide

### 1. Prerequisites <a href="#prerequisites" id="prerequisites"></a>

> _This guide uses `@chainlink/ccip-sdk` v0.95. The stable v1.0 release will be available shortly._

* Node.js 20 or higher
* `@chainlink/ccip-sdk` ^0.95.0 - install via npm
* `@solana/web3.js` ^1.98.4
* `@solana/wallet-adapter-react` (for wallet integration)
* `ethers` ^6.13.4 (for EVM address conversion)
* `viem` ^2.43.5 (for EVM chain interactions)

#### Installation

```bash
npm install @chainlink/ccip-sdk@^0.95.0 @solana/web3.js @solana/wallet-adapter-react ethers viem
```

### 2. Receiver Contract Details <a href="#receiver-contract-details" id="receiver-contract-details"></a>

#### Testnet Deployment (Ethereum Sepolia)

* **Receiver Address**: `0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4`
* **Receiver Address (bytes32)**: `0x00000000000000000000000002b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4`
* **Pool Address**: `0x3EB612858EE843eBb14Df37b9Ec2c7c82B23eE2B`
* **Destination Chain**: Ethereum Sepolia
* **Chain Selector**: `16015286601757825753`

> **⚠** These addresses are for testnet only. When deploying to mainnet, you must update all addresses to be mainnet from [syrupusd-crosschain.md](syrupusd-crosschain.md "mention").

#### Token Addresses

**Solana (Devnet):**

* **USDC Mint**: `4zMMC9srt5Ri5X14GAgXhaHii3GnPAEERYPJgZJDncDU`
* **Pool Token Mint**: `6Sn78bdY12h6j5wVzeXqYrTZboKPqBtqjB4p5xsRNFaX`

**Ethereum (Sepolia Testnet):**

* **USDC**: Different from Solana - use the USDC contract address on Ethereum Sepolia
* **syrupUSDC**: Use the syrupUSDC contract address on Ethereum Sepolia

> **⚠** For EVM-to-EVM deposits and withdrawals, use the appropriate USDC or syrupUSDC addresses for the destination chain from [syrupusd-crosschain.md](syrupusd-crosschain.md "mention").

### 3. Message Structure <a href="#message-structure" id="message-structure"></a>

The Maple receiver contract expects a `UniversalMessage` struct encoded as ABI-encoded bytes:

```solidity
struct UniversalMessage {
    bytes32 universalSenderAddress;  // Solana address converted to bytes32
    address pool;                      // Pool contract address
    bytes32 metaData;                  // 32 bytes of metadata (typically zeros)
}
```

#### Field Descriptions

1. **universalSenderAddress** (`bytes32`): The Solana sender's public key converted to bytes32 format
   * Example: `2hVTZGxQZTpPjarHQsnQfnRSGSy8LPy85szn8Wy4sj5V` → `0x193b18c1b4280b6fcb542dc733cfccc3b4e56b287e04647317bdb129685854ac`
2. **pool** (`address`): The Maple pool contract address on Ethereum
   * Testnet: `0x3EB612858EE843eBb14Df37b9Ec2c7c82B23eE2B`
3. **metaData** (`bytes32`): Used to identify the source of deposits/withdrawals. Used for incentive campaigns and support. Use `0:[your protocol name]` encoded as bytes32
   * E.g. `0:maple` as bytes32
   * Default: `0x0000000000000000000000000000000000000000000000000000000000000000`

### 4. Building the Message <a href="#building-the-message" id="building-the-message"></a>

#### Step 1: Convert Solana Address to bytes32

{% code expandable="true" %}
```typescript
import { PublicKey } from "@solana/web3.js";
import { zeroPadValue } from "ethers";

function solanaToBytes32(solanaAddress: string): string {
  // Convert Solana public key to bytes32 hex string
  const publicKey = new PublicKey(solanaAddress);
  const hex = "0x" + publicKey.toBuffer().toString("hex");
  
  // Pad to 32 bytes (64 hex characters) using zeroPadValue from ethers
  return zeroPadValue(hex, 32);
}

// Example usage
const solanaAddress = "2hVTZGxQZTpPjarHQsnQfnRSGSy8LPy85szn8Wy4sj5V";
const universalSenderAddress = solanaToBytes32(solanaAddress);
// Result: 0x193b18c1b4280b6fcb542dc733cfccc3b4e56b287e04647317bdb129685854ac
```
{% endcode %}

#### Step 2: Encode the Struct

{% code expandable="true" %}
```typescript
import { encodeAbiParameters, parseAbiParameters } from "viem";

function encodeUniversalMessage(
  universalSenderAddress: string, // bytes32 hex string
  poolAddress: string,            // EVM address
  metaData: string = "0x0000000000000000000000000000000000000000000000000000000000000000"
): `0x${string}` {
  return encodeAbiParameters(
    parseAbiParameters("bytes32, address, bytes32"),
    [
      universalSenderAddress as `0x${string}`,
      poolAddress as `0x${string}`,
      metaData as `0x${string}`
    ]
  );
}

// Example usage
const universalSenderAddress = "0x193b18c1b4280b6fcb542dc733cfccc3b4e56b287e04647317bdb129685854ac";
const poolAddress = "0x3EB612858EE843eBb14Df37b9Ec2c7c82B23eE2B";
const metaData = "0x0000000000000000000000000000000000000000000000000000000000000000";

const encodedData = encodeUniversalMessage(universalSenderAddress, poolAddress, metaData);
// Result: 0x193b18c1b4280b6fcb542dc733cfccc3b4e56b287e04647317bdb129685854ac0000000000000000000000003eb612858ee843ebb14df37b9ec2c7c82b23ee2b0000000000000000000000000000000000000000000000000000000000000000
```
{% endcode %}

#### Step 3: Convert Receiver Address to bytes32

{% code expandable="true" %}
```typescript
function evmToBytes32(address: string): string {
  if (!address.startsWith("0x")) {
    address = `0x${address}`;
  }
  
  if (address.length === 42) {
    // Standard EVM address (20 bytes) - pad to 32 bytes
    return zeroPadValue(address, 32);
  }
  
  return address; // Already bytes32 format
}

// Example usage
const receiverAddress = "0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4";
const receiverBytes32 = evmToBytes32(receiverAddress);
// Result: 0x00000000000000000000000002b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4
```
{% endcode %}

### 5. Gas Estimation <a href="#gas-estimation" id="gas-estimation"></a>

> **⚠** Always use `estimateReceiveExecution` to estimate gas limits. Never hardcode gas values as they vary based on message data, token amounts, and receiver contract complexity.

Gas estimation determines how much gas is needed for the receiver contract to execute the message on the destination chain. The CCIP SDK provides accurate gas estimation through the `estimateReceiveExecution` function, which should be used for every message.

#### Using estimateReceiveExecution

{% code expandable="true" %}
```typescript
import { SolanaChain } from "@chainlink/ccip-sdk";
import { EVMChain, estimateReceiveExecution } from "@chainlink/ccip-sdk";
import { fromViemClient } from "@chainlink/ccip-sdk/viem";
import { createPublicClient, http } from "viem";

async function estimateGasLimit(
  solanaChain: SolanaChain,
  senderAddress: string,         // Solana sender address (base58 string)
  receiverAddress: string,      // Standard EVM address (20 bytes), not bytes32
  encodedData: string,
  tokenAmounts: Array<{ token: string; amount: bigint }>,
  destinationChainSelector: string
): Promise<bigint> {
  // Get destination EVM chain config
  const destinationChainConfig = {
    id: 11155111, // Ethereum Sepolia
    name: "Ethereum Sepolia",
    chainSelector: "16015286601757825753",
    routerAddress: "0x0BF3dE8c5D3e8A2B34D2BEeB17ABfCeBaf363A59",
    explorerUrl: "https://sepolia.etherscan.io",
    rpcUrl: "https://rpc.sepolia.org",
    nativeCurrency: { name: "Sepolia ETH", symbol: "ETH", decimals: 18 },
  };

  // Create destination EVM chain client
  const destClient = createPublicClient({
    chain: {
      id: destinationChainConfig.id,
      name: destinationChainConfig.name,
      nativeCurrency: destinationChainConfig.nativeCurrency,
      rpcUrls: { default: { http: [destinationChainConfig.rpcUrl] } },
      blockExplorers: { default: { name: "Explorer", url: destinationChainConfig.explorerUrl } },
    },
    transport: http(destinationChainConfig.rpcUrl),
  });

  const destEvmChain = await fromViemClient(destClient);

  // Solana router program ID
  const routerProgramId = "Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C";

  // Estimate gas
  // Note: senderAddress is required for accurate gas estimation
  const gasEstimate = await estimateReceiveExecution({
    source: solanaChain,
    dest: destEvmChain,
    routerOrRamp: routerProgramId,
    message: {
      sender: senderAddress,      // Solana sender address (required for accurate estimation)
      receiver: receiverAddress,   // Use standard EVM address (20 bytes) for gas estimation
      data: encodedData,
      tokenAmounts: tokenAmounts.length > 0 ? tokenAmounts : undefined,
    },
  });

  return BigInt(gasEstimate);
}

// Example usage
const solanaSenderAddress = "2hVTZGxQZTpPjarHQsnQfnRSGSy8LPy85szn8Wy4sj5V"; // Solana public key
const receiverAddress = "0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4"; // Standard address for estimation

const gasLimit = await estimateGasLimit(
  solanaChain,
  solanaSenderAddress,              // Solana sender address (required)
  receiverAddress,                  // Receiver address
  encodedData,
  [
    {
      token: "4zMMC9srt5Ri5X14GAgXhaHii3GnPAEERYPJgZJDncDU", // Solana USDC mint
      amount: BigInt("12345"),
    },
  ],
  "16015286601757825753" // Ethereum Sepolia chain selector
);

console.log(`Estimated gas limit: ${gasLimit.toString()}`);
// Typical result: ~604000-660000 for messages with token transfers
```
{% endcode %}

#### Always Estimate Gas

> **Critical:** Always use `estimateReceiveExecution` to estimate gas limits. Never hardcode gas values as they vary based on message data, token amounts, and receiver contract complexity.

Gas estimation may fail in rare cases (network issues, contract not deployed, etc.). If estimation fails:

1. **Retry the estimation** - Most failures are transient network issues
2. **Check receiver contract** - Ensure the receiver contract is deployed and accessible
3. **Verify parameters** - Ensure sender, receiver, and data are correctly formatted
4. **Use minimum safety value** - Only as a last resort, use a minimum value that ensures the transaction won't fail

{% code expandable="true" %}
```typescript
// Always estimate first
let gasLimit: bigint;
try {
  // SDK estimation is the preferred and most accurate method
  const gasEstimate = await estimateReceiveExecution({
    source: solanaChain,
    dest: destEvmChain,
    routerOrRamp: routerProgramId,
    message: {
      sender: senderAddress,
      receiver: receiverAddress,
      data: encodedData,
      tokenAmounts: tokenAmounts.length > 0 ? tokenAmounts : undefined,
    },
  });
  gasLimit = BigInt(gasEstimate);
  console.log(`SDK gas estimate: ${gasLimit}`);
} catch (error) {
  console.error("Gas estimation failed:", error);
  
  // Fallback should only be used as a last resort
  // Always investigate why estimation failed and prefer retrying
  const FALLBACK_GAS_LIMIT = 700000n;
  gasLimit = FALLBACK_GAS_LIMIT;
  console.warn(`Using fallback gas limit: ${gasLimit} - investigate estimation failure`);
}
```
{% endcode %}

**Important Notes:**

* **SDK gas estimation is strongly preferred** - it calculates the exact gas needed for your specific message
* Fallback values are emergency-only and may be too high or too low
* If estimation consistently fails, there may be an issue with your setup
* The fallback 700,000 gas is a conservative safety value, not a recommended value
* Always investigate why estimation failed before using fallback values

### 6. Fee Estimation <a href="#fee-estimation" id="fee-estimation"></a>

Fee estimation calculates the CCIP fee required to send the message across chains.

{% code expandable="true" %}
```typescript
import { SolanaChain } from "@chainlink/ccip-sdk";

async function estimateCCIPFee(
  solanaChain: SolanaChain,
  routerProgramId: string,
  destinationChainSelector: string,
  receiverBytes32: string,        // bytes32-padded receiver address
  encodedData: string,
  gasLimit: bigint,
  allowOutOfOrder: boolean,
  tokenAmounts: Array<{ token: string; amount: bigint }>
): Promise<bigint> {
  const message = {
    receiver: receiverBytes32,    // Use bytes32 format for actual message
    data: encodedData,
    extraArgs: {
      gasLimit: gasLimit,
      allowOutOfOrderExecution: allowOutOfOrder,
    },
    tokenAmounts: tokenAmounts.length > 0 ? tokenAmounts : undefined,
  };

  const fee = await solanaChain.getFee({
    router: routerProgramId,
    destChainSelector: BigInt(destinationChainSelector),
    message,
  });

  return fee; // Fee in lamports (1 SOL = 1e9 lamports)
}

// Example usage
const fee = await estimateCCIPFee(
  solanaChain,
  "Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C", // Router program ID
  "16015286601757825753",                          // Ethereum Sepolia
  receiverBytes32,                                 // bytes32 format
  encodedData,
  660935n,                                        // Gas limit
  true,                                           // Allow out of order
  [
    {
      token: "4zMMC9srt5Ri5X14GAgXhaHii3GnPAEERYPJgZJDncDU",
      amount: BigInt("12345"),
    },
  ]
);

console.log(`Estimated fee: ${Number(fee) / 1e9} SOL`);
```
{% endcode %}

### 7. Executing the Transaction <a href="#executing-the-transaction" id="executing-the-transaction"></a>

#### Step 1: Generate Unsigned Transaction

{% code expandable="true" %}
```typescript
import { TransactionMessage, VersionedTransaction } from "@solana/web3.js";

async function generateTransaction(
  solanaChain: SolanaChain,
  publicKey: PublicKey,
  routerProgramId: string,
  destinationChainSelector: string,
  receiverBytes32: string,
  encodedData: string,
  gasLimit: bigint,
  allowOutOfOrder: boolean,
  fee: bigint,
  tokenAmounts: Array<{ token: string; amount: bigint }>
) {
  const message = {
    receiver: receiverBytes32,
    data: encodedData,
    extraArgs: {
      gasLimit: gasLimit,
      allowOutOfOrderExecution: allowOutOfOrder,
    },
    fee: fee,
    tokenAmounts: tokenAmounts.length > 0 ? tokenAmounts : undefined,
  };

  const unsignedTx = await solanaChain.generateUnsignedSendMessage({
    sender: publicKey.toBase58(),
    router: routerProgramId,
    destChainSelector: BigInt(destinationChainSelector),
    message,
  });

  return unsignedTx;
}
```
{% endcode %}

#### Step 2: Convert to Solana Transaction

{% code expandable="true" %}
```typescript
async function convertToSolanaTransaction(
  connection: Connection,
  publicKey: PublicKey,
  unsignedTx: any
): Promise<VersionedTransaction> {
  const { instructions, lookupTables } = unsignedTx as {
    family: string;
    instructions: any[];
    lookupTables: any[];
    mainIndex: number;
  };

  // Get recent blockhash
  const { blockhash, lastValidBlockHeight } = await connection.getLatestBlockhash("confirmed");

  // Build TransactionMessage
  const transactionMessage = new TransactionMessage({
    payerKey: publicKey,
    recentBlockhash: blockhash,
    instructions: instructions,
  });

  // Compile to V0 message with lookup tables (if available)
  const messageV0 = lookupTables && lookupTables.length > 0
    ? transactionMessage.compileToV0Message(lookupTables)
    : transactionMessage.compileToV0Message();

  // Create VersionedTransaction
  return new VersionedTransaction(messageV0);
}
```
{% endcode %}

#### Step 3: Sign and Send

{% code expandable="true" %}
```typescript
async function signAndSendTransaction(
  connection: Connection,
  versionedTx: VersionedTransaction,
  signTransaction: (tx: VersionedTransaction) => Promise<VersionedTransaction>
): Promise<{ signature: string; messageId: string | null }> {
  // Sign transaction
  const signedTx = await signTransaction(versionedTx);

  // Send transaction
  const signature = await connection.sendTransaction(signedTx, {
    skipPreflight: false,
    maxRetries: 3,
  });

  // Get blockhash for confirmation
  const { blockhash, lastValidBlockHeight } = await connection.getLatestBlockhash("confirmed");

  // Confirm transaction
  await connection.confirmTransaction({
    signature,
    blockhash,
    lastValidBlockHeight,
  }, "confirmed");

  // Extract message ID from transaction logs
  await new Promise(resolve => setTimeout(resolve, 2000)); // Wait for processing

  const tx = await connection.getTransaction(signature, {
    maxSupportedTransactionVersion: 0,
    commitment: "confirmed",
  });

  let messageId: string | null = null;
  if (tx && tx.meta?.logMessages) {
    const logs = tx.meta.logMessages;
    const routerProgramId = "Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C";

    for (const log of logs) {
      if (log.startsWith("Program return:") && log.includes(routerProgramId)) {
        const parts = log.split(" ");
        if (parts.length >= 4) {
          const base64Data = parts[3];
          const returnBuffer = Buffer.from(base64Data, "base64");

          if (returnBuffer.length === 32) {
            messageId = `0x${returnBuffer.toString("hex")}`;
          } else if (returnBuffer.length >= 40) {
            const messageIdBytes = returnBuffer.subarray(8, 40);
            messageId = `0x${messageIdBytes.toString("hex")}`;
          }
          break;
        }
      }
    }
  }

  return { signature, messageId };
}
```
{% endcode %}

## Complete Code Example <a href="#complete-code-example" id="complete-code-example"></a>

Here's a complete example integrating all the steps:

{% code expandable="true" %}
```typescript
import { SolanaChain } from "@chainlink/ccip-sdk";
import { EVMChain, estimateReceiveExecution } from "@chainlink/ccip-sdk";
import { fromViemClient } from "@chainlink/ccip-sdk/viem";
import { Connection, PublicKey, TransactionMessage, VersionedTransaction } from "@solana/web3.js";
import { createPublicClient, http, encodeAbiParameters, parseAbiParameters } from "viem";
import { zeroPadValue } from "ethers";
import { useWallet, useConnection } from "@solana/wallet-adapter-react";

// Configuration
const MAPLE_CONFIG = {
  // Testnet addresses
  receiverAddress: "0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4",
  poolAddress: "0x3EB612858EE843eBb14Df37b9Ec2c7c82B23eE2B",
  destinationChainSelector: "16015286601757825753", // Ethereum Sepolia
  
  // Solana Devnet
  solanaRpcUrl: "https://api.devnet.solana.com",
  routerProgramId: "Ccip842gzYHhvdDkSyi2YVCoAWPbYJoApMFzSxQroE9C",
  sourceChainSelector: "16423721717087811551", // Solana Devnet
  
  // Token addresses
  solanaUSDC: "4zMMC9srt5Ri5X14GAgXhaHii3GnPAEERYPJgZJDncDU",
  
  // Ethereum Sepolia
  ethereumSepoliaRpcUrl: "https://rpc.sepolia.org",
};

// Helper functions
function solanaToBytes32(solanaAddress: string): string {
  const publicKey = new PublicKey(solanaAddress);
  const hex = "0x" + publicKey.toBuffer().toString("hex");
  return zeroPadValue(hex, 32);
}

function evmToBytes32(address: string): string {
  if (!address.startsWith("0x")) address = `0x${address}`;
  if (address.length === 42) return zeroPadValue(address, 32);
  return address;
}

function encodeUniversalMessage(
  universalSenderAddress: string, // bytes32 hex string
  poolAddress: string,            // EVM address
  metaData: string = "0x0000000000000000000000000000000000000000000000000000000000000000"
): `0x${string}` {
  return encodeAbiParameters(
    parseAbiParameters("bytes32, address, bytes32"),
    [
      universalSenderAddress as `0x${string}`,
      poolAddress as `0x${string}`,
      metaData as `0x${string}`
    ]
  );
}

// Main function
async function sendMapleCCIPMessage(
  solanaAddress: string,
  tokenAmount: bigint,
  signTransaction: (tx: VersionedTransaction) => Promise<VersionedTransaction>,
  connection: Connection
): Promise<{ signature: string; messageId: string | null }> {
  // 1. Initialize Solana Chain
  const solanaChain = await SolanaChain.fromUrl(MAPLE_CONFIG.solanaRpcUrl);

  // 2. Convert Solana address to bytes32
  const universalSenderAddress = solanaToBytes32(solanaAddress);

  // 3. Encode UniversalMessage struct
  const encodedData = encodeUniversalMessage(
    universalSenderAddress,
    MAPLE_CONFIG.poolAddress
  );

  // 4. Convert receiver address to bytes32
  const receiverBytes32 = evmToBytes32(MAPLE_CONFIG.receiverAddress);

  // 5. Estimate gas limit
  const destClient = createPublicClient({
    chain: {
      id: 11155111,
      name: "Ethereum Sepolia",
      nativeCurrency: { name: "Sepolia ETH", symbol: "ETH", decimals: 18 },
      rpcUrls: { default: { http: [MAPLE_CONFIG.ethereumSepoliaRpcUrl] } },
      blockExplorers: { default: { name: "Etherscan", url: "https://sepolia.etherscan.io" } },
    },
    transport: http(MAPLE_CONFIG.ethereumSepoliaRpcUrl),
  });

  const destEvmChain = await fromViemClient(destClient);

  // Always estimate gas - never hardcode values
  let gasLimit: bigint;
  try {
    const gasEstimate = await estimateReceiveExecution({
      source: solanaChain,
      dest: destEvmChain,
      routerOrRamp: MAPLE_CONFIG.routerProgramId,
      message: {
        sender: solanaAddress,                    // Solana sender address (required for accurate estimation)
        receiver: MAPLE_CONFIG.receiverAddress,  // Standard address for estimation
        data: encodedData,
        tokenAmounts: [
          {
            token: MAPLE_CONFIG.solanaUSDC,
            amount: tokenAmount,
          },
        ],
      },
    });
    gasLimit = BigInt(gasEstimate);
    console.log(`SDK gas estimate: ${gasLimit} - using SDK-provided value`);
  } catch (error) {
    // Gas estimation failed - this should be rare
    // SDK estimation is preferred; fallback is for emergency only
    console.error("Gas estimation failed:", error);
    console.warn("SDK gas estimation is preferred. Investigate why estimation failed.");
    
    // Only use fallback as last resort - this is an emergency case
    // In production, you should retry estimation or handle the error appropriately
    const FALLBACK_GAS_LIMIT = 700000n;
    gasLimit = FALLBACK_GAS_LIMIT;
    console.warn(`Using fallback gas limit: ${gasLimit} (investigate estimation failure)`);
  }

  console.log(`Gas limit: ${gasLimit.toString()}`);

  // 6. Estimate fee
  const fee = await solanaChain.getFee({
    router: MAPLE_CONFIG.routerProgramId,
    destChainSelector: BigInt(MAPLE_CONFIG.destinationChainSelector),
    message: {
      receiver: receiverBytes32,
      data: encodedData,
      extraArgs: {
        gasLimit: gasLimit,
        allowOutOfOrderExecution: true,
      },
      tokenAmounts: [
        {
          token: MAPLE_CONFIG.solanaUSDC,
          amount: tokenAmount,
        },
      ],
    },
  });

  console.log(`Fee: ${Number(fee) / 1e9} SOL`);

  // 7. Generate unsigned transaction
  const unsignedTx = await solanaChain.generateUnsignedSendMessage({
    sender: solanaAddress,
    router: MAPLE_CONFIG.routerProgramId,
    destChainSelector: BigInt(MAPLE_CONFIG.destinationChainSelector),
    message: {
      receiver: receiverBytes32,
      data: encodedData,
      extraArgs: {
        gasLimit: gasLimit,
        allowOutOfOrderExecution: true,
      },
      fee: fee,
      tokenAmounts: [
        {
          token: MAPLE_CONFIG.solanaUSDC,
          amount: tokenAmount,
        },
      ],
    },
  });

  // 8. Convert to Solana transaction
  const { instructions, lookupTables } = unsignedTx as {
    family: string;
    instructions: any[];
    lookupTables: any[];
    mainIndex: number;
  };

  const { blockhash, lastValidBlockHeight } = await connection.getLatestBlockhash("confirmed");

  const messageV0 = lookupTables && lookupTables.length > 0
    ? new TransactionMessage({
        payerKey: new PublicKey(solanaAddress),
        recentBlockhash: blockhash,
        instructions: instructions,
      }).compileToV0Message(lookupTables)
    : new TransactionMessage({
        payerKey: new PublicKey(solanaAddress),
        recentBlockhash: blockhash,
        instructions: instructions,
      }).compileToV0Message();

  const versionedTx = new VersionedTransaction(messageV0);

  // 9. Sign and send
  const signedTx = await signTransaction(versionedTx);

  const signature = await connection.sendTransaction(signedTx, {
    skipPreflight: false,
    maxRetries: 3,
  });

  await connection.confirmTransaction({
    signature,
    blockhash,
    lastValidBlockHeight,
  }, "confirmed");

  // 10. Extract message ID
  await new Promise(resolve => setTimeout(resolve, 2000));

  const tx = await connection.getTransaction(signature, {
    maxSupportedTransactionVersion: 0,
    commitment: "confirmed",
  });

  let messageId: string | null = null;
  if (tx && tx.meta?.logMessages) {
    for (const log of tx.meta.logMessages) {
      if (log.startsWith("Program return:") && log.includes(MAPLE_CONFIG.routerProgramId)) {
        const parts = log.split(" ");
        if (parts.length >= 4) {
          const base64Data = parts[3];
          const returnBuffer = Buffer.from(base64Data, "base64");

          if (returnBuffer.length === 32) {
            messageId = `0x${returnBuffer.toString("hex")}`;
          } else if (returnBuffer.length >= 40) {
            const messageIdBytes = returnBuffer.subarray(8, 40);
            messageId = `0x${messageIdBytes.toString("hex")}`;
          }
          break;
        }
      }
    }
  }

  return { signature, messageId };
}

// React hook usage example
function useMapleCCIP() {
  const { publicKey, signTransaction } = useWallet();
  const { connection } = useConnection();

  const sendMessage = async (tokenAmount: bigint) => {
    if (!publicKey || !signTransaction) {
      throw new Error("Wallet not connected");
    }

    return await sendMapleCCIPMessage(
      publicKey.toBase58(),
      tokenAmount,
      signTransaction,
      connection
    );
  };

  return { sendMessage };
}
```
{% endcode %}

## Message Monitoring via API <a href="#message-monitoring" id="message-monitoring"></a>

After sending CCIP messages, you'll want to monitor their status and display message history to users. The CCIP API provides REST endpoints for querying message transactions by sender address, receiver address, or both.

> **Note:** This is a pre-release version of the CCIP API (v2). The public release will be published soon. The Base URL of the production API will be: [https://api.ccip.cldev.cloud/v2/](https://api.ccip.cldev.cloud/v2/)

#### API Base URL (Staging)

[https://api.ccip.cldev.cloud/v2/](https://api.ccip.cldev.cloud/v2/)

#### Querying Messages

The API supports querying messages with the following filters:

* **By Receiver Address**: Find all messages sent to the Maple receiver contract
* **By Sender Address**: Find all messages sent by a specific user
* **By Both**: Find messages matching both sender and receiver

#### Basic Query Function

{% code expandable="true" %}
```typescript
const CCIP_API_BASE = "https://api.ccip.cldev.cloud/v2/";

interface NetworkInfo {
  name: string;
  chainSelector: string;
  chainId: string;
  chainFamily: "EVM" | "SVM" | "APTOS";
}

type MessageStatus = 
  | "SENT" 
  | "SOURCE_FINALIZED" 
  | "COMMITTED" 
  | "BLESSED" 
  | "VERIFYING" 
  | "VERIFIED" 
  | "SUCCESS" 
  | "FAILED";

interface MessageSearchResult {
  messageId: string;
  sender: string;
  receiver: string;
  origin?: string | null;
  status: MessageStatus;
  sourceNetworkInfo: NetworkInfo;
  destNetworkInfo: NetworkInfo;
  sendTransactionHash: string;
  sendTimestamp: string;
  receiptTransactionHash?: string | null;
  receiptTimestamp?: string | null;
  sourceTokenAddress?: string | null;
}

interface MessagesResponse {
  data: MessageSearchResult[];
  pagination: {
    limit: number;
    hasNextPage: boolean;
    cursor?: string | null;
  };
}

async function queryCCIPMessages(
  receiverAddress?: string,
  senderAddress?: string,
  limit: number = 50,
  cursor?: string | null
): Promise<MessagesResponse> {
  const params = new URLSearchParams();
  
  if (cursor) {
    params.set("cursor", cursor);
    params.set("limit", limit.toString());
  } else {
    params.set("limit", limit.toString());
    if (receiverAddress) {
      params.set("receiver", receiverAddress.toLowerCase());
    }
    if (senderAddress) {
      params.set("sender", senderAddress.toLowerCase());
    }
  }
  
  const url = `${CCIP_API_BASE}messages?${params.toString()}`;
  const response = await fetch(url, {
    headers: {
      "Accept": "application/json",
    },
  });
  
  if (!response.ok) {
    const error = await response.json().catch(() => ({
      error: "Unknown error",
      message: `HTTP ${response.status}`,
    }));
    throw new Error(error.message || error.error);
  }
  
  return await response.json();
}
```
{% endcode %}

#### Understanding Message Statuses

The API returns messages with the following status values:

* **`SENT`**: Transaction submitted and waiting for source chain confirmation
* **`SOURCE_FINALIZED`**: Transaction confirmed on source chain and ready for CCIP processing
* **`COMMITTED`**: Message committed to destination chain's commit store (CCIP v1.6 and below)
* **`BLESSED`**: Message approved by CCIP network (CCIP v1.6 and below)
* **`VERIFYING`**: Message is being verified by the CCIP network (CCIP v1.7+)
* **`VERIFIED`**: Message has been verified by the CCIP network (CCIP v1.7+)
* **`SUCCESS`**: Message successfully executed on destination chain
* **`FAILED`**: Message execution failed but can be manually retried

#### Status Display Helpers

{% code expandable="true" %}
```typescript
function getStatusLabel(status: MessageStatus): string {
  switch (status) {
    case "SENT": return "Sent";
    case "SOURCE_FINALIZED": return "Source Finalized";
    case "COMMITTED": return "Committed";
    case "BLESSED": return "Blessed";
    case "VERIFYING": return "Verifying";
    case "VERIFIED": return "Verified";
    case "SUCCESS": return "Success";
    case "FAILED": return "Failed";
    default: return "Unknown";
  }
}

function getStatusColor(status: MessageStatus): string {
  switch (status) {
    case "SUCCESS":
      return "green";
    case "FAILED":
      return "red";
    case "SENT":
    case "SOURCE_FINALIZED":
    case "COMMITTED":
    case "BLESSED":
    case "VERIFYING":
    case "VERIFIED":
      return "yellow";
    default:
      return "gray";
  }
}

function isStatusComplete(status: MessageStatus): boolean {
  return status === "SUCCESS" || status === "FAILED";
}
```
{% endcode %}

#### Best Practices

1. **Cache Results**: Cache message queries to reduce API calls
2. **Debounce Search**: Debounce user input when searching by address
3. **Handle Pagination**: Always check `hasNextPage` before loading more
4. **Error Recovery**: Implement retry logic for transient failures
5. **Status Polling**: Only poll for messages that aren't in final states (SUCCESS/FAILED)
6. **Rate Limiting**: Be mindful of API rate limits in production

## Message Information via API <a href="#ccip-api-message-info" id="ccip-api-message-info"></a>

The CCIP API provides endpoints to query detailed message information by message ID, sender address, or receiver address. This is useful for building monitoring dashboards, transaction history, and status tracking in your application.

#### API Base URL

```
https://api.ccip.cldev.cloud/v2/
```

> **Note:** This is a pre-release version of the CCIP API (v2). The public release will be published soon.

#### Get Message by Message ID

Query a specific message using its message ID:

{% code expandable="true" %}
```typescript
const CCIP_API_BASE = "https://api.ccip.cldev.cloud/v2/";

interface MessageDetails {
  messageId: string;
  sender: string;
  receiver: string;
  origin?: string | null;
  status: MessageStatus;
  sourceNetworkInfo: NetworkInfo;
  destNetworkInfo: NetworkInfo;
  sendTransactionHash: string;
  sendTimestamp: string;
  receiptTransactionHash?: string | null;
  receiptTimestamp?: string | null;
  sourceTokenAddress?: string | null;
}

async function getMessageById(messageId: string): Promise<MessageDetails> {
  // Remove 0x prefix if present
  const cleanMessageId = messageId.startsWith("0x") ? messageId.slice(2) : messageId;
  
  const url = `${CCIP_API_BASE}messages/${cleanMessageId}`;
  const response = await fetch(url, {
    headers: {
      "Accept": "application/json",
    },
  });
  
  if (!response.ok) {
    const error = await response.json().catch(() => ({
      error: "Unknown error",
      message: `HTTP ${response.status}`,
    }));
    throw new Error(error.message || error.error);
  }
  
  return await response.json();
}

// Example usage
const messageId = "0x1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef";
const message = await getMessageById(messageId);
console.log(`Message status: ${message.status}`);
console.log(`Send transaction: ${message.sendTransactionHash}`);
if (message.receiptTransactionHash) {
  console.log(`Receipt transaction: ${message.receiptTransactionHash}`);
}
```
{% endcode %}

#### Query Messages by Receiver Address

Get all messages sent to the Maple receiver contract:

{% code expandable="true" %}
```typescript
async function getMessagesByReceiver(
  receiverAddress: string,
  limit: number = 50,
  cursor?: string | null
): Promise<MessagesResponse> {
  const params = new URLSearchParams();
  
  if (cursor) {
    params.set("cursor", cursor);
    params.set("limit", limit.toString());
  } else {
    params.set("limit", limit.toString());
    params.set("receiver", receiverAddress.toLowerCase());
  }
  
  const url = `${CCIP_API_BASE}messages?${params.toString()}`;
  const response = await fetch(url, {
    headers: {
      "Accept": "application/json",
    },
  });
  
  if (!response.ok) {
    const error = await response.json().catch(() => ({
      error: "Unknown error",
      message: `HTTP ${response.status}`,
    }));
    throw new Error(error.message || error.error);
  }
  
  return await response.json();
}

// Example: Get all messages sent to Maple receiver contract
const receiverAddress = "0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4";
const result = await getMessagesByReceiver(receiverAddress);

console.log(`Found ${result.data.length} messages`);
result.data.forEach((msg) => {
  console.log(`Message ${msg.messageId}: ${msg.status}`);
});
```
{% endcode %}

#### Query Messages by Sender Address

Get all messages sent by a specific Solana address:

{% code expandable="true" %}
```typescript
async function getMessagesBySender(
  senderAddress: string,
  limit: number = 50,
  cursor?: string | null
): Promise<MessagesResponse> {
  const params = new URLSearchParams();
  
  if (cursor) {
    params.set("cursor", cursor);
    params.set("limit", limit.toString());
  } else {
    params.set("limit", limit.toString());
    // For Solana addresses, use the base58 address directly
    params.set("sender", senderAddress);
  }
  
  const url = `${CCIP_API_BASE}messages?${params.toString()}`;
  const response = await fetch(url, {
    headers: {
      "Accept": "application/json",
    },
  });
  
  if (!response.ok) {
    const error = await response.json().catch(() => ({
      error: "Unknown error",
      message: `HTTP ${response.status}`,
    }));
    throw new Error(error.message || error.error);
  }
  
  return await response.json();
}

// Example: Get all messages sent by a Solana user
const solanaSender = "2hVTZGxQZTpPjarHQsnQfnRSGSy8LPy85szn8Wy4sj5V";
const result = await getMessagesBySender(solanaSender);

console.log(`User has sent ${result.data.length} messages`);
result.data.forEach((msg) => {
  console.log(`Message ${msg.messageId} to ${msg.receiver}: ${msg.status}`);
});
```
{% endcode %}

#### Polling for Message Status Updates

Poll the API to check when a message status changes:

{% code expandable="true" %}
```typescript
async function pollMessageStatus(
  messageId: string,
  onStatusUpdate: (status: MessageStatus) => void,
  pollInterval: number = 5000, // 5 seconds
  maxAttempts: number = 120 // 10 minutes max
): Promise<MessageDetails> {
  let attempts = 0;
  
  const poll = async (): Promise<MessageDetails> => {
    attempts++;
    
    const message = await getMessageById(messageId);
    onStatusUpdate(message.status);
    
    // Stop polling if message is in final state
    if (message.status === "SUCCESS" || message.status === "FAILED") {
      return message;
    }
    
    // Stop polling if max attempts reached
    if (attempts >= maxAttempts) {
      throw new Error(`Polling timeout: Message ${messageId} did not reach final state`);
    }
    
    // Wait before next poll
    await new Promise(resolve => setTimeout(resolve, pollInterval));
    
    return poll();
  };
  
  return poll();
}

// Example usage
const messageId = "0x1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef";

pollMessageStatus(
  messageId,
  (status) => {
    console.log(`Message status updated: ${status}`);
  }
).then((message) => {
  console.log(`Message completed with status: ${message.status}`);
  if (message.receiptTransactionHash) {
    console.log(`Receipt: ${message.receiptTransactionHash}`);
  }
}).catch((error) => {
  console.error("Polling error:", error);
});
```
{% endcode %}

#### Complete Example: Message Monitoring Hook

A React hook for monitoring messages:

{% code expandable="true" %}
```typescript
import { useState, useEffect, useCallback } from "react";

function useMessageStatus(messageId: string | null) {
  const [message, setMessage] = useState<MessageDetails | null>(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState<string | null>(null);

  const fetchMessage = useCallback(async () => {
    if (!messageId) return;
    
    setLoading(true);
    setError(null);
    
    try {
      const data = await getMessageById(messageId);
      setMessage(data);
    } catch (err: any) {
      setError(err.message || "Failed to fetch message");
    } finally {
      setLoading(false);
    }
  }, [messageId]);

  useEffect(() => {
    if (!messageId) return;
    
    fetchMessage();
    
    // Poll for status updates if message is not in final state
    const interval = setInterval(() => {
      if (message && message.status !== "SUCCESS" && message.status !== "FAILED") {
        fetchMessage();
      }
    }, 5000); // Poll every 5 seconds
    
    return () => clearInterval(interval);
  }, [messageId, message, fetchMessage]);

  return { message, loading, error, refetch: fetchMessage };
}

// Usage in component
function MessageStatus({ messageId }: { messageId: string }) {
  const { message, loading, error } = useMessageStatus(messageId);
  
  if (loading) return <div>Loading message status...</div>;
  if (error) return <div>Error: {error}</div>;
  if (!message) return null;
  
  return (
    <div>
      <h3>Message Status</h3>
      <p>Status: {message.status}</p>
      <p>Send Transaction: <a href={`https://explorer.solana.com/tx/${message.sendTransactionHash}`}>{message.sendTransactionHash}</a></p>
      {message.receiptTransactionHash && (
        <p>Receipt Transaction: <a href={`https://sepolia.etherscan.io/tx/${message.receiptTransactionHash}`}>{message.receiptTransactionHash}</a></p>
      )}
    </div>
  );
}
```
{% endcode %}

#### Best Practices (Same as Monitoring)

1. **Rate Limiting**: Be mindful of API rate limits. Implement exponential backoff for retries
2. **Caching**: Cache message data to reduce API calls, especially for completed messages
3. **Polling Strategy**: Only poll messages that aren't in final states (SUCCESS/FAILED)
4. **Error Handling**: Implement retry logic for transient failures
5. **Pagination**: Use cursors for pagination when querying multiple messages
6. **Address Format**: Ensure addresses are in the correct format (lowercase for EVM, base58 for Solana)

## Important Notes <a href="#important-notes" id="important-notes"></a>

#### **Minimum Transfer Amounts**

> **⚠** Deposits and redemptions must exceed the configured fee for that token. Transactions with amounts below the fee will require manual recovery (handled by Maple).

Before sending a crosschain deposit or redemption:

1. Query the receiver contract for the current fee configuration
2. Validate the user's amount exceeds the fee
3. Display a clear error if the amount is too low

Fee amounts are configured per-token on the receiver contract. For fee queries and recovery procedures, see ​[Failed Deposit/Redemption Retry and Recovery](../../technical-resources/crosschain/failed-message-recovery.md). Maple handles these edge cases with a 24h SLA, but you can as well for faster resolution.

#### Address Format Differences

* **Gas Estimation**: Use standard EVM address format (20 bytes, 42 characters with `0x`)
  * Example: `0x02b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4`
* **Message Construction**: Use bytes32-padded address format (32 bytes, 66 characters with `0x`)
  * Example: `0x00000000000000000000000002b6a75c5d1f430f0614dc5ac8ad5f9d35fba2c4`

#### Token Transfer Behavior

* **USDC Transfer**: When USDC is sent to the receiver, it processes a **deposit** operation
* **SyrupUSDC Transfer**: When SyrupUSDC is sent to the receiver, it processes a **redemption** operation

Ensure you're sending the correct token type based on the operation you want to perform.

#### Mainnet Deployment

All addresses in this guide are for **testnet only**. Before deploying to mainnet:

1. Update receiver contract address
2. Update pool contract address
3. Update token addresses (USDC, SyrupUSDC) for mainnet
4. Update destination chain selector if using a different chain
5. Verify all addresses on mainnet explorer

All addresses are available in [syrupusd-crosschain.md](syrupusd-crosschain.md "mention").

#### Gas Estimation Best Practices

Always use `estimateReceiveExecution` to estimate gas limits. Never hardcode gas values.

**Key Points:**

* **Always estimate**: Use `estimateReceiveExecution` for every message
* **Sender required**: Include the sender address for accurate Solana-to-EVM estimation
* **API signature**: Use `estimateReceiveExecution({ source, dest, routerOrRamp, message })`
* **Validate estimates**: Check that estimates are reasonable (not zero, not extremely high)
* **Handle failures**: If estimation fails, retry before using fallback values
* **Fallback value**: 700,000 gas is a conservative fallback for emergency cases, not a recommended value

**Why estimation is important:**

* Gas requirements vary based on message data size
* SyrupUSDC Contract state can cause variable gas usage
* Other conditions can influence gas requirements

**If estimation fails:**

1. Check network connectivity
2. Verify receiver contract is deployed and accessible
3. Ensure all parameters (sender, receiver, data) are correct
4. Retry the estimation (most failures are transient)
5. Only use fallback values as a last resort

#### Out-of-Order Execution

Always set `allowOutOfOrderExecution: true`

#### Error Handling

Implement comprehensive error handling for:

* User transaction rejection
* Insufficient funds (SOL for fees, tokens for transfer)
* Network errors
* Gas estimation failures
* Transaction confirmation failures

#### Message Tracking

After sending, track your message using the CCIP Explorer:

* URL: `https://ccip.chain.link/msg/{messageId}`
* The message ID is extracted from the transaction logs after confirmation

## Resources & Contact

* Partnerships & queries: [partnerships@maple.finance](mailto:partnerships@maple.finance)
* [Technical Docs](../../technical-resources/crosschain/)
* [Integration Support](https://chain.link/ccip-contact)
* [Failed Deposit/Redemption Retry and Recovery](../../technical-resources/crosschain/failed-message-recovery.md)<br>
