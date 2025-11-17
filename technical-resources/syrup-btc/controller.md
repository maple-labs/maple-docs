# Controller Module

The controller module coordinates asset accounting and strategy routing for SyrupBTC.

Asset Controller
- Tracks two views of balances per deposit asset
  - `depositAssets(asset)` amount of deposit assets held by the controller
  - `poolAssets(asset)` amount of Pool assets that back a deposit asset
- Wrap and unwrap
  - `wrap(assetIn, amountIn)` pulls deposit assets and mints Pool assets for the router
  - `unwrap(asset, amountOut)` burns Pool assets and returns deposit assets to the router
- Strategy integration
  - `deploy` moves deposit assets into strategies and burns Pool assets accordingly
  - `reconcile` pulls deposit assets back and mints Pool assets accordingly
- Permissions and configuration
  - `setAssets` whitelists capabilities per asset for wrap, unwrap, deploy, reconcile
  - `setOracle`, `setRouter`, and `setStrategies` wire dependencies

Invariants
See `technical-resources/security/protocol-invariants.md` for the SyrupBTC and controller invariants

Interfaces
- Contract interfaces are documented in `technical-resources/interfaces/asset-controller.md`
