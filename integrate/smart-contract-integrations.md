---
description: >-
  Integrate syrupUSD (syrupUSDC / syrupUSDT) via smart contracts. Lenders (your
  smart contracts) must deposit through SyrupRouter with authorization handled
  by PoolPermissionManager.
---

# Smart Contract Integrations

{% hint style="info" %}
#### Step-by-step

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

Smart contracts integrating with syrupUSD act as lenders and must interact via `SyrupRouter`. Authorization is enforced by `PoolPermissionManager`. First-time deposits require an authorization signature; subsequent deposits can call `deposit` directly once authorized.

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

<table><thead><tr><th width="225.015625">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://sepolia.etherscan.io/address/0x2d8d21fee98d060655729efd7b14bc432c375ac1">0x2d8d21fee98d060655729efd7b14bc432c375ac1</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://sepolia.etherscan.io/address/0x5387ab37f93af968920af6c0faa6dbc52973b020">0x5387ab37f93af968920af6c0faa6dbc52973b020</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://sepolia.etherscan.io/address/0x2ff61035de7a1550219be12a6e9d33aa10b844b6">0x2ff61035de7a1550219be12a6e9d33aa10b844b6</a></td></tr></tbody></table>

**Syrup USDT**

<table><thead><tr><th width="224.62890625">Contract</th><th>Address</th></tr></thead><tbody><tr><td>PoolV2</td><td><a href="https://sepolia.etherscan.io/address/0x7679cbe9ae66298114ac6dac73487b63ac023c0b">0x7679cbe9ae66298114ac6dac73487b63ac023c0b</a></td></tr><tr><td>SyrupRouter</td><td><a href="https://sepolia.etherscan.io/address/0x0b703919cf2d30dbb18bad6febe8f0ea4f191918">0x0b703919cf2d30dbb18bad6febe8f0ea4f191918</a></td></tr><tr><td>WithdrawalManagerQueue</td><td><a href="https://sepolia.etherscan.io/address/0xbbe2bf30b76729a4eb75bf40ced47a58000ae1d3">0xbbe2bf30b76729a4eb75bf40ced47a58000ae1d3</a></td></tr></tbody></table>
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
* `depositData` (provided by Maple). Conventionally `"0:<integrator-name>"`, encoded as `bytes32`. Keep within 32 bytes when hex-encoded.

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

<summary>How long do withdrawals take?</summary>

Withdrawals are serviced by Maple’s automation. Expected processing time is less than 2 days, but it can take up to 30 days depending on available liquidity.

</details>

<details>

<summary>What is depositData and who provides it?</summary>

\`depositData\` is provided by Maple. It typically follows \`0:\` and must be provided as a \`bytes32\` value (32-byte hex).

</details>

<details>

<summary>How do I verify lender authorization on-chain?</summary>

Read \`lenderBitmaps(lender)\` and \`poolBitmaps(pool)\` in \`PoolPermissionManager\` and check \`(lenderBitmap ^ poolBitmap) == poolBitmap\`.

</details>
