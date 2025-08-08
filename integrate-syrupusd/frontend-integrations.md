---
description: >-
  Enable new wallets to connect to syrupUSD via the Syrup app. Handle
  permissions and user interactions. For new wallets.
---

# Frontend Integrations

{% hint style="info" %}
Looking to enable your users to deposit into syrupUSD through your own app? See [backend-integrations.md](backend-integrations.md "mention")
{% endhint %}

## Overview

Frontend integration allows wallet providers to request whitelisting for their wallets to connect to the Syrup app. This enables users of your wallet to interact with syrupUSD directly through our interface.

## Requirements

To be eligible for the frontend integration, your wallet must meet the following criteria:

### 1. Rainbow Wallet Listing

Your wallet must be officially listed on [Rainbow Wallet](https://rainbow.me) registry. This ensures your wallet meets industry standards for security and compatibility.

### 2. Provide Connection Endpoints

Submit your wallet's connection endpoints to our team. We'll need:

* Production endpoint URL
* Any additional connection parameters

## Integration Process

### 1. Verify Rainbow Listing

Ensure your wallet appears in the Rainbow Wallet registry. If not listed, complete their submission process first.

### 2. Submit Integration Request

Contact the Maple team via [Telegram](https://t.me/maplefinance) with the following information:

* Wallet name and website
* Rainbow listing URL
* Connection endpoints
* Contact information for the integration owner

### 3. Technical Review

Our team will review your submission and may request additional information about your wallet's security practices and user base.

### 4. Whitelisting

Once approved, we'll add your wallet to our whitelist. This typically takes 3-5 business days.

### 5. Testing

After whitelisting, test the connection flow:

1. Navigate to [https://app.maple.finance/earn](https://app.maple.finance/earn)
2. Click "Connect Wallet"
3. Select your wallet from the list
4. Verify successful connection and syrupUSD interactions

## Post-Integration

Once integrated, your wallet users can:

* Connect to the Syrup app
* View syrupUSD balances
* Deposit USDC to mint syrupUSD
* Redeem syrupUSD for USDC
* Track their positions and yield

## FAQ

<details>

<summary>What is the difference between Syrup and Maple?</summary>

Syrup is the protocol - the smart contracts that power onchain lending. Maple encompasses the entities that conduct institutional lending services using this infrastructure.

**For developers:** You'll be integrating with Syrup (the protocol), while Maple handles the institutional lending operations.

</details>

<details>

<summary><strong>How long does the whitelisting process take?</strong></summary>

Typically 5-10 days after submitting all required information.

</details>

<details>

<summary><strong>Can mobile wallets integrate?</strong></summary>

Yes, as long as they're listed on Rainbow and support standard connection protocols.

</details>

<details>

<summary><strong>Do we need to implement any syrupUSD-specific features?</strong></summary>

No, standard ERC-20 token support is sufficient. syrupUSD follows the ERC-20 standard.

</details>
