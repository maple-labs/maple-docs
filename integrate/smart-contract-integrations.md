---
description: >-
  Integrate syrupUSDC & syrupUSDT via smart contracts. Lenders (your smart
  contracts) must deposit through SyrupRouter with authorization handled by
  PoolPermissionManager.
---

# Smart Contract Integrations

{% hint style="info" %}
**Step-by-step**

**Deposit:**

1. [**Determine lender authorization**](smart-contract-integrations.md#id-1.-determine-lender-authorization-onchain) (onchain via PoolPermissionManager)
2. [**Retrieve authorization signature**](smart-contract-integrations.md#id-2.-retrieve-authorization-signature) (from Maple)
3. [**Execute the deposit**](smart-contract-integrations.md#id-3.-execute-the-deposit) (authorize-and-deposit or deposit)

**Withdraw:**

1. [**Retrieve lender balance**](smart-contract-integrations.md#id-1.-retrieve-lenders-balance) (shares)
2. [**Calculate shares to redeem**](smart-contract-integrations.md#id-2.-calculate-shares-to-redeem) (full balance or convertToExitShares for partial)
3. [**Execute the withdrawal**](smart-contract-integrations.md#id-3.-execute-the-withdrawal) (requestRedeem)
{% endhint %}

## Overview

### 1. Syrup Protocol Overview

Smart contracts integrating with syrupUSDC & syrupUSDT act as lenders and must interact via `SyrupRouter`. Authorization is enforced by `PoolPermissionManager`. First-time deposits require an authorization signature; subsequent deposits can call `deposit` directly once authorized.

### 2. Syrup Addresses

All ABIs are available on GitHub: [Maple JS (ABIs)](https://github.com/maple-labs/maple-js/tree/main/src/abis)

{% tabs %}
{% tab title="Mainnet" %}
**Syrup USDC**

<table><thead><tr><th width="224.77734375">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://etherscan.io/address/0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b">0x80ac24aA929eaF5013f6436cdA2a7ba190f5Cc0b</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://etherscan.io/address/0x134cCaaA4F1e4552eC8aEcb9E4A2360dDcF8df76">0x134cCaaA4F1e4552eC8aEcb9E4A2360dDcF8df76</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://etherscan.io/address/0x1bc47a0Dd0FdaB96E9eF982fdf1F34DC6207cfE3">0x1bc47a0Dd0FdaB96E9eF982fdf1F34DC6207cfE3</a></td></tr><tr><td>USDC</td><td><a href="https://etherscan.io/address/0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48">0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48</a></td></tr></tbody></table>

**Syrup USDT**

<table><thead><tr><th width="224.82421875">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://etherscan.io/address/0x356B8d89c1e1239Cbbb9dE4815c39A1474d5BA7D">0x356B8d89c1e1239Cbbb9dE4815c39A1474d5BA7D</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://etherscan.io/address/0xF007476Bb27430795138C511F18F821e8D1e5Ee2">0xF007476Bb27430795138C511F18F821e8D1e5Ee2</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://etherscan.io/address/0x86eBDf902d800F2a82038290B6DBb2A5eE29eB8C">0x86eBDf902d800F2a82038290B6DBb2A5eE29eB8C</a></td></tr><tr><td>USDT</td><td><a href="https://etherscan.io/address/0xdAC17F958D2ee523a2206206994597C13D831ec7">0xdAC17F958D2ee523a2206206994597C13D831ec7</a></td></tr></tbody></table>

**Shared (Global)**

<table><thead><tr><th width="225.08984375">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolPermissionManager</td><td><a href="https://etherscan.io/address/0xBe10aDcE8B6E3E02Db384E7FaDA5395DD113D8b3">0xBe10aDcE8B6E3E02Db384E7FaDA5395DD113D8b3</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Sepolia" %}
**Syrup USDC**

<table><thead><tr><th width="225.015625">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://sepolia.etherscan.io/address/0x2d8D21FeE98d060655729eFD7b14bc432C375aC1">0x2d8D21FeE98d060655729eFD7b14bc432C375aC1</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://sepolia.etherscan.io/address/0x5387Ab37f93Af968920af6c0Faa6dbc52973b020">0x5387Ab37f93Af968920af6c0Faa6dbc52973b020</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://sepolia.etherscan.io/address/0x2Ff61035dE7A1550219Be12a6e9D33AA10B844B6">0x2Ff61035dE7A1550219Be12a6e9D33AA10B844B6</a></td></tr><tr><td>USDC</td><td><a href="https://sepolia.etherscan.io/address/0xC40E5D31187ae7AFC6238594765DA5873A5bB8ed">0xC40E5D31187ae7AFC6238594765DA5873A5bB8ed</a></td></tr></tbody></table>

**Syrup USDT**

<table><thead><tr><th width="224.62890625">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://sepolia.etherscan.io/address/0x7679CBe9aE66298114AC6dAC73487B63ac023c0b">0x7679CBe9aE66298114AC6dAC73487B63ac023c0b</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://sepolia.etherscan.io/address/0x0B703919cF2d30DbB18bAD6feBe8F0eA4F191918">0x0B703919cF2d30DbB18bAD6feBe8F0eA4F191918</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://sepolia.etherscan.io/address/0xbBe2Bf30b76729a4eB75bf40ceD47A58000AE1D3">0xbBe2Bf30b76729a4eB75bf40ceD47A58000AE1D3</a></td></tr><tr><td>USDT</td><td><a href="https://sepolia.etherscan.io/address/0x658DAE0F3388892692A213494E1CbB04844Df0A3">0x658DAE0F3388892692A213494E1CbB04844Df0A3</a></td></tr></tbody></table>

**Shared (Global)**

<table><thead><tr><th width="225">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolPermissionManager</td><td><a href="https://sepolia.etherscan.io/address/0xd3BAaf866ccd5AF28b3caA2b4aC92E3FAaC8432B">0xd3BAaf866ccd5AF28b3caA2b4aC92E3FAaC8432B</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### 3. Testing on Sepolia

Contact [partnerships@maple.finance](mailto:partnerships@maple.finance) for test `USDC/USDT` and access. See the Sepolia tab above for addresses.

***

## Deposit

### 1. Determine Lender Authorization (onchain)

Use `PoolPermissionManager` to verify lender authorization for a specific pool. You can derive the manager onchain from the Pool.

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IPool { function manager() external view returns (address); }
interface IPoolManager { function poolPermissionManager() external view returns (address); }
interface IPoolPermissionManager {
    function lenderBitmaps(address lender) external view returns (uint256);
    function poolBitmaps(address pool) external view returns (uint256);
}

function getPoolPermissionManager(address pool) internal view returns (address) {
    address manager = IPool(pool).manager();
    return IPoolManager(manager).poolPermissionManager();
}

function isAuthorized(address pool, address lender) internal view returns (bool) {
    address ppm = getPoolPermissionManager(pool);
    uint256 lenderBitmap = IPoolPermissionManager(ppm).lenderBitmaps(lender);
    uint256 poolBitmap   = IPoolPermissionManager(ppm).poolBitmaps(pool);
    // Authorized if XOR equals the pool bitmap
    return (lenderBitmap ^ poolBitmap) == poolBitmap;
}
```
{% endcode %}

Mainnet `PoolPermissionManager` (for reference): `0xBe10aDcE8B6E3E02Db384E7FaDA5395DD113D8b3`

### 2. Retrieve Authorization Signature

If not authorized, contact [partnerships@maple.finance](mailto:partnerships@maple.finance) to obtain:

* `bitmap`, `deadline`, `v`, `r`, `s`
* `depositData` - conventionally `"0:<integrator-name>"`, encoded as `bytes32`. Keep within 32 bytes when hex-encoded.

### 3. Execute the Deposit

Minimal SC calls (lender must hold sufficient USDC/USDT):

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IERC20 { function approve(address spender, uint256 amount) external returns (bool); }
interface ISyrupRouter {
    function deposit(uint256 amount, bytes32 depositData) external returns (uint256 shares);
    function authorizeAndDeposit(
        uint256 bitmap,
        uint256 deadline,
        uint8   v,
        bytes32 r,
        bytes32 s,
        uint256 amount,
        bytes32 depositData
    ) external returns (uint256 shares);
}

function depositAuthorized(
    address asset,
    address router,
    uint256 amount,
    bytes32 depositData
) external {
    IERC20(asset).approve(router, amount);
    ISyrupRouter(router).deposit(amount, depositData);
}

function authorizeAndDeposit(
    address asset,
    address router,
    uint256 amount,
    bytes32 depositData,
    uint256 bitmap,
    uint256 deadline,
    uint8   v,
    bytes32 r,
    bytes32 s
) external {
    IERC20(asset).approve(router, amount);
    ISyrupRouter(router).authorizeAndDeposit(bitmap, deadline, v, r, s, amount, depositData);
}
```
{% endcode %}

{% hint style="info" %}
Deposit data

* Replace `0:<integrator-name>` with your integrator identifier (e.g. `0:acme-protocol`).
* Maple will provide the final `depositData` for production.
* Must be passed as `bytes32` (32-byte hex).
{% endhint %}

***

## Withdraw

### 1. Retrieve Lender’s Balance

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IPool {
    function balanceOf(address account) external view returns (uint256);
    function convertToExitAssets(uint256 shares) external view returns (uint256);
}

function getLenderPosition(address pool, address lender) external view returns (uint256 shares, uint256 exitAssets) {
    shares     = IPool(pool).balanceOf(lender);
    exitAssets = IPool(pool).convertToExitAssets(shares);
}
```
{% endcode %}

### 2. Calculate Shares to Redeem

Use full balance for full redemption, or compute shares for a specific asset amount.

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IPool { function convertToExitShares(uint256 assets) external view returns (uint256); }

function sharesForAssets(address pool, uint256 assetAmount) external view returns (uint256) {
    return IPool(pool).convertToExitShares(assetAmount);
}
```
{% endcode %}

### 3. Execute the Withdrawal

Submit a withdrawal request to the pool.

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IPool { function requestRedeem(uint256 shares, address receiver) external returns (uint256); }

function requestWithdrawal(address pool, uint256 shares, address receiver) external {
    IPool(pool).requestRedeem(shares, receiver);
}
```
{% endcode %}

Withdrawals are processed automatically by Maple. If there is sufficient liquidity in the pool, the withdrawal will be processed within a few minutes. Expected processing time is typically less than 2 days, but it can take up to 30 days depending on available liquidity.

***

## Edge Cases

* Not authorized → use `authorizeAndDeposit` with signature
* Insufficient allowance → call `approve(router, amount)` before depositing

***

## FAQ

<details>

<summary>Why must deposits go through SyrupRouter?</summary>

Authorization and routing are enforced via \`SyrupRouter\` and \`PoolPermissionManager\`. This ensures only authorized lenders can deposit.

</details>

<details>

<summary>What is depositData and who provides it?</summary>

\`depositData\` is provided by Maple. It typically follows \`0:\` and your company name. It must be provided as a \`bytes32\` value (32-byte hex).

</details>

<details>

<summary>How do I verify lender authorization onchain?</summary>

Read `lenderBitmaps(lender)` and `poolBitmaps(pool)` in `PoolPermissionManager` and check `(lenderBitmap ^ poolBitmap) == poolBitmap`.

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
      "dripsYieldBoost": "22000"
    }
  }
}
```

In the example above, the monthly base APY is 6.72% with the Drips rewards adding an extra 2.2% on top.

</details>

<details>

<summary>How can I get the price received on redemption for syrupUSDC or syrupUSDT?</summary>

syrupUSDC and syrupUSDT are redeemed at the smart contract exchange rate at the point of processing the withdrawal, incurring no slippage.&#x20;

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
