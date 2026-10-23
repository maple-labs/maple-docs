# Managed Wallets

A Managed Wallet is a Maple-operated address that an Allocation Strategy releases capital to. It is not a protocol contract. Once assets leave the strategy through `deployAssets()`, the contract has no custody of them and no on-chain view of what happens to them until the wallet returns them or an admin writes them off.

## Two permission gates

A wallet must pass two independent checks before it can act on a given strategy. Every wallet entry point (`deployAssets()`, `returnAssets()`, `realizeYield()`) re-checks both on each call, so revoking either one cuts access immediately.

### 1. Protocol allowlist on Globals

`MapleGlobals` keeps the allowlist under the `MAPLE_MANAGED_WALLET` instance key. The Governor or Operational Admin calls `setValidMapleManagedWallet(wallet, isValid)`, which writes the flag through `setValidInstanceOf()`. The same callers both grant and revoke. The flag is protocol-wide: a wallet approved here is a valid Managed Wallet for every Allocation Strategy, not just one.

### 2. Permission flags on the strategy

Each strategy stores `permissions[wallet]`, three booleans that map one to one onto the wallet functions:

| Flag              | Allows           |
| ----------------- | ---------------- |
| `canDeployAssets` | `deployAssets()` |
| `canReturnAssets` | `returnAssets()` |
| `canRealizeYield` | `realizeYield()` |

The Strategy Delegate or Security Admin sets them with `setPermissions(accounts, canDeployAssets, canReturnAssets, canRealizeYield)`. The call takes parallel arrays of equal, non-zero length and, for each account, requires at least one flag to change. It serves both the initial grant and every later update, so a delegate can enable or revoke any subset of the three flags.

Setting any flag to `true` requires the account to be on the Globals allowlist at that moment. A **total revoke** (all three `false`) is always allowed. This lets a delegate clear a wallet's local flags after Globals has already delisted it, so stale `true` flags cannot be left on a delisted wallet.

## Deployment caps

`deploymentCapOf[wallet]` is a ceiling on `deployedAssetsOf[wallet]` at any point in time, not a lifetime total. Room under the cap frees up as the wallet returns assets or has losses recognized against it. The default cap is zero, so a wallet cannot deploy anything until a cap is set.

The Strategy Delegate or Security Admin sets caps with `setDeploymentCaps(accounts, amounts)`. The call requires equal, non-zero length arrays and, for each account, a value different from the current cap. A non-zero cap requires the account to be on the Globals allowlist. A cap of `0` can be set on any address, mirroring the total-revoke exception above.

Caps limit how much of a strategy's capital sits with one wallet and, if a wallet is compromised, how much is at risk.

## Deploying assets

A permitted wallet pulls capital with `deployAssets(assets, metadata)`. The call reverts unless:

* the caller holds `canDeployAssets`,
* `assets` is greater than zero,
* `assets` does not exceed `availableToWithdraw()`,
* `deployedAssetsOf[caller] + assets` does not exceed `deploymentCapOf[caller]`.

On success the strategy adds `assets` to `totalDeployedAssets` and `deployedAssetsOf[caller]`, subtracts it from `recordedAssets`, and transfers the funds asset to the caller. Capital moves from one bucket to the other, so `assetsUnderManagement()` does not change.

`deployAssets()` and `withdrawFromUnderlyingStrategy()` draw from the same `availableToWithdraw()` figure, with no reservation between them. See [Funding and Withdrawals](funding-and-withdrawals.md).

**Example.** The strategy holds `recordedAssets = 1,000,000`. A wallet with a cap of `1,000,000` and nothing deployed calls `deployAssets(400,000)`. The strategy sends it `400,000`. `recordedAssets` falls to `600,000`, and `totalDeployedAssets` and `deployedAssetsOf[wallet]` rise to `400,000`.

## Returning assets

A permitted wallet returns capital by approving the strategy on the funds asset and calling `returnAssets(assets, onBehalfOf, metadata)`. The call reverts unless:

* the caller holds `canReturnAssets`,
* `assets` is not zero,
* `assets` does not exceed `deployedAssetsOf[onBehalfOf]`.

On success the strategy subtracts `assets` from `totalDeployedAssets` and `deployedAssetsOf[onBehalfOf]`, adds it to `recordedAssets`, and pulls the funds asset from the caller.

`onBehalfOf` is the address credited and does not need any permission or allowlist entry. The caller needs `canReturnAssets` only. One Managed Wallet can therefore repay what another deployed, which is also how a wallet that has been delisted on Globals gets its outstanding balance back into the strategy.

`returnAssets()` only accepts principal. Anything above `deployedAssetsOf[onBehalfOf]` must come in through `realizeYield()`, described on [Accounting and Fees](accounting-and-fees.md).

**Example.** A wallet has `deployedAssetsOf = 400,000` and returns `300,000` on its own behalf. The strategy pulls `300,000`. `deployedAssetsOf[wallet]` and `totalDeployedAssets` fall to `100,000`, and `recordedAssets` rises by `300,000`.

## Metadata

The `metadata` argument on `deployAssets()`, `returnAssets()` and `realizeYield()` is not stored. The strategy emits it as-is on `AssetsDeployed`, `AssetsReturned` and `YieldRealized`, so indexers can attribute a movement to a specific trade at no storage cost. It is separate from the strategy-wide `strategyMetadata` string set with `setMetadata()`.
