# SyrupBitcoinStrategy

## Overview

SyrupBitcoinStrategy is the active yield module for SyrupBTC. It sits between the Asset Controller and Maple Pool, deploying idle wBTC into external yield generation activities and reconciling assets back to the pool when redemptions must be serviced. 

The strategy:

- Manages **deploy** and **reconcile** calls with the Asset Controller.
- Tracks accounting for deployed capital, accrued yield, defaulted assets, and fees.
- Allows governance to mark impairments or defaults.
- Supports a linear yield schedule so operations can distribute protocol yield. 

## Deploy & Reconcile Lifecycle

1. **Deploy** (`deploy(assetOut, amountOut)`):
   - Called by the strategy manager.
   - Burns the strategy’s pool shares and instructs Asset Controller to send `amountOut` of the specified deposit asset (currently wBTC) to the strategy which are then sent to the msg.sender.
   - Emits `AssetsDeployed` and updates accounting.
   - Requires `canDeploy` permission.

2. **Reconcile** (`reconcile(assetIn, amountIn)`):
   - Strategy returns deposit assets to the controller.
   - Asset Controller mints pool assets and sends them back to the strategy, which then pushes the assets to the Pool.
   - Emits `AssetsReconciled` and updates accounting.
   - Requires `canReconcile` permission.


## Yield Scheduling

`schedule(yieldAmount, deadline)` linearly distributes pool yield over a period:

- Replaces any existing schedule—only one can be active.
- During each `deploy`/`reconcile`/`schedule` interaction the contract updates `accruedYield` and `realizedFees` based on the scheduled yield.
- Requires `canSchedule` permission (assigned via `setPermissions`).

## Governance & Admin Controls

- `setAssetController(asset, controller)`: Maps deposit assets to their controllers (needed for multi-asset support).
- `setDefault(amount)`: Writes off pool assets that cannot be recovered, emitting `AssetsDefaulted` and reducing AUM.
- `setFeeRate(feeRate)`: Adjusts protocol fee rate (scaled by 1e6). Example: `100_000` = 10%.
- `setImpairment(amount)`: Marks assets as impaired so Pool reflects potential losses.
- `setPermissions(addresses, canDeploy, canReconcile, canSchedule)`: Grants or revokes operational permissions.

## Accounting

Key view functions for monitoring:

- `accruedFees()`, `accruedYield()`: Pending amounts not yet realized.
- `assetsUnderManagement()`: Deployed assets minus impairments.
- `unrealizedLosses()`: Outstanding impairments plus defaults not yet realized.
- `yieldRate()`: Current per-second yield from the active schedule (scaled by `PRECISION`).
- `controllers(asset)`: Asset => controller mapping for future supported assets. Currently just wBTC.
- `schedules(id)`: Returns remaining yield, timestamp, and remaining duration. Currently only id 0 exists. In future we may support multiple simultaneous schedules. 

## Events

- `AccountingUpdated(uint256 deployedAssets, uint256 reconciledAssets, uint256 defaultedAssets, uint256 accruedYield, uint256 realizedFees)`
- `AssetControllerSet(address indexed asset, address indexed controller)`
- `AssetsDefaulted(uint256 amount)`
- `AssetsDeployed(address indexed asset, uint256 amount)`
- `AssetsReconciled(address indexed asset, uint256 amount)`
- `FeeRateSet(uint256 rate)`
- `ImpairmentSet(uint256 amount)`
- `PermissionsSet(address[] addresses, bool[] canDeploy, bool[] canReconcile, bool[] canSchedule)`
- `YieldScheduleUpdated(uint256 id, uint256 yield, uint32 duration)`

Each event fires alongside the state transition listed above, giving operations a detailed audit log.

## Roles & Permissions

| Actor | Capabilities |
| --- | --- |
| Deployer addresses (have `canDeploy` permission) | Call `deploy` to move assets out of the controller |
| Reconciler addresses (have `canReconcile` permission) | Call `reconcile` to return assets to the controller |
| Scheduler addresses (have `canSchedule` permission) | Call `schedule` to configure a yield distribution |
| Pool Delegate or Protocol Admins (Maple governor or operational admin) | `setDefault`, `setFeeRate`, `setImpairment`, `setAssetController` |
| Governor / Ops Admin | `setPermissions` to maintain the permission map |

## Interfaces

For full ABI details refer to  `technical-resources/interfaces/syrup-bitcoin-strategy.md`.
