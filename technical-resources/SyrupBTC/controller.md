# SyrupBTC Asset Controller

## Overview

The Asset Controller converts between wBTC deposit assets, the pool asset, and downstream strategies:

- **Wrapping / Unwrapping**: Locks incoming wBTC and mints pool assets for the router, then burns pool assets and returns wBTC on redemption.
- **Strategy Routing**: Deploys idle deposit assets into strategies (e.g., SyrupBitcoinStrategy) and reconciles them back into pool assets.
- **Permissions**: Enforces what assets can be wrapped, deployed, or reconciled, and which addresses are allowed to call those functions.
- **Oracle Integration**: Queries the AssetControllerOracle to convert between assets (Currently 1:1 conversion only).

Every deposit and redemption goes through the router, which in turn calls the Asset Controller. Strategies call it directly when moving funds.

## Wrapping Deposits

When the router calls `wrap(assetIn, amountIn)`:

1. Access control ensures the caller is the configured router and that wrapping is enabled for `assetIn`.
2. Deposit assets are pulled from the router (router must `approve` beforehand).
3. The controller consults `AssetControllerOracle` for the conversion rate (currently  1:1 for wBTC).
4. Pool assets are minted to the router and `poolAssets(assetIn)` increases accordingly.
5. `AssetsWrapped` event records recipient, asset, amount wrapped, and pool assets minted.

## Unwrapping for Redemptions

`unwrap(assetOut, burnAmount)` reverses the process:

1. Verifies caller is the router and `assetOut` is authorized for unwrapping.
2. Burns `burnAmount` pool assets supplied by the router.
3. Uses the oracle to determine deposit asset amount due (currently 1:1).
4. Transfers deposit assets to the router and emits `AssetsUnwrapped`.

## Strategy Deploy & Reconcile

- **Deploy** (`deploy(assetOut, amountOut)`): Called by allowlisted strategies. Burns pool assets and transfers `amountOut` deposit assets so those assets can be used ot generate yield. Emits `AssetsDeployed` and ensures per-asset permissions allow deployments.
- **Reconcile** (`reconcile(assetIn, amountIn)`): Called by strategies returning funds. Transfers deposit assets from the strategy back into the controller, mints pool assets, and emits `AssetsReconciled`. Only allowlisted strategies can reconcile.

## Permissions & Configuration

Key configuration calls (Governor / operational admin only):

- `setAssets(assets[], canWrap[], canUnwrap[], canDeploy[], canReconcile[])`: Per-asset capability matrix. Used to add new wrapped assets or freeze actions during incidents.
- `setRouter(address router)`: Points to the active SyrupBitcoinRouter.
- `setStrategies(addresses[], flags[])`: Allowlist of contracts that may call deploy/reconcile. Typically the Maple strategy instances.
- `setOracle(address oracle)`: Upgrades the pricing oracle. Future deployments can support stables or other Bitcoin wrappers with different decimals.

Every permission change emits events.

## Roles

| Actor | Capabilities |
| --- | --- |
| Router | `wrap`, `unwrap` (only for assets with `canWrap/canUnwrap` true) |
| Strategies (allowlisted) | `deploy`, `reconcile` when the corresponding `canDeploy/canReconcile` flags are true |
| Governor / Operational Admin | `setAssets`, `setStrategies`, `setOracle`, `setRouter` |
| External users | No direct access—must interact through the router or strategy interfaces |

## Events

- `AssetsWrapped(recipient, asset, wrapped, minted)`
- `AssetsUnwrapped(recipient, asset, unwrapped, burned)`
- `AssetsDeployed(recipient, asset, deployed, burned)`
- `AssetsReconciled(recipient, asset, reconciled, minted)`
- `AssetsSet(assets[], canWrap[], canUnwrap[], canDeploy[], canReconcile[])`
- `StrategiesSet(addresses[], flags[])`
- `RouterSet(router)`
- `OracleSet(oracle)`

## Interfaces

For full ABI details refer to  `technical-resources/interfaces/asset-controller.md`. 
