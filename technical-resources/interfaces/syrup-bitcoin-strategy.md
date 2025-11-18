# Bitcoin Strategy

The Bitcoin Strategy manages pool exposure to supported Bitcoin assets through an Asset Controller. It deploys and reconciles assets, schedules yield distribution, supports impairments, and accrues a fee on realized yield. Rates are scaled by 1e6 where 1e6 equals 100 percent.

## Constants

```solidity
function STRATEGY_TYPE() external view returns (string memory);
function HUNDRED_PERCENT() external view returns (uint256);
function PRECISION() external view returns (uint256);
```

## Functions

### `deploy`

Burns pool assets to withdraw deposit assets to the caller by instructing the Asset Controller to deploy.

```solidity
function deploy(
    address assetOut,
    uint256 amountOut
) external;
```

#### Parameters

| Index |    Name   |   Type   | Description |
| :---: | :-------: | :------: | ----------- |
|   0   | `assetOut` | `address` | Deposit asset to receive from the controller |
|   1   | `amountOut` | `uint256` | Amount of deposit asset to withdraw |

### `reconcile`

Pulls deposit assets from the caller and wraps them into pool assets by instructing the Asset Controller to reconcile. The strategy sends the minted pool assets back to the pool.

```solidity
function reconcile(
    address assetIn,
    uint256 amountIn
) external;
```

#### Parameters

| Index |   Name   |   Type   | Description |
| :---: | :------: | :------: | ----------- |
|   0   | `assetIn` | `address` | Deposit asset to return into the controller |
|   1   | `amountIn` | `uint256` | Amount of deposit asset to wrap |

### `schedule`

Starts or clears a yield schedule which linearly accrues until the deadline. Yield rate uses `PRECISION` for accuracy.

```solidity
function schedule(
    uint256 yieldAmount,
    uint32  deadline
) external;
```

#### Parameters

| Index |     Name     |   Type   | Description |
| :---: | :----------: | :------: | ----------- |
|   0   | `yieldAmount` | `uint256` | Total pool assets to vest as yield |
|   1   |  `deadline`   |  `uint32` | Timestamp when vesting completes |

### Admin Functions

```solidity
function setAssetController(address asset, address controller) external;
function setDefault(uint256 amount) external;            // Defaults pool assets up to AUM
function setFeeRate(uint256 feeRate) external;           // feeRate <= 1e6
function setImpairment(uint256 amount) external;         // amount <= AUM
function setPermissions(
    address[] calldata addresses,
    bool[]    calldata canDeploy,
    bool[]    calldata canReconcile,
    bool[]    calldata canSchedule
) external;
```

#### Parameters: `setAssetController`

| Index |   Name   |   Type   | Description |
| :---: | :------: | :------: | ----------- |
|   0   | `asset` | `address` | Supported deposit asset |
|   1   | `controller` | `address` | Asset Controller to map to this asset |

#### Parameters: `setFeeRate`

| Index |   Name   |   Type   | Description |
| :---: | :------: | :------: | ----------- |
|   0   | `feeRate` | `uint256` | Percentage of yield captured by the protocol |

Example: `100_000` equals 10 percent

## Views

```solidity
function accruedFees() external view returns (uint256);
function accruedYield() external view returns (uint256);
function assetsUnderManagement() external view returns (uint256);
function unrealizedLosses() external view returns (uint256);
function yieldRate() external view returns (uint256);          // scaled by PRECISION
function feeRate() external view returns (uint256);            // scaled by 1e6
function controllers(address asset) external view returns (address);
function schedules(uint256 id) external view returns (uint256 remainingYield, uint32 lastUpdated, uint32 remainingDuration);
```

## Events

Emitted whenever the strategy accounting is updated after deploy, reconcile, default, or yield accrual

```solidity
event AccountingUpdated(
    uint256 deployedAssets,
    uint256 reconciledAssets,
    uint256 defaultedAssets,
    uint256 accruedYield,
    uint256 realizedFees
);
```

Emitted when the asset controller mapping for a deposit asset is changed

```solidity
event AssetControllerSet(
    address indexed asset,
    address indexed controller
);
```

Emitted when a portion of assets under management is marked as defaulted

```solidity
event AssetsDefaulted(
    uint256 amount
);
```

Emitted when deposit assets are deployed from the pool to an external recipient via the controller

```solidity
event AssetsDeployed(
    address indexed asset,
    uint256 amount
);
```

Emitted when deposit assets are reconciled back from an external source into the pool via the controller

```solidity
event AssetsReconciled(
    address indexed asset,
    uint256 amount
);
```

Emitted when the strategy fee rate on yield is updated

```solidity
event FeeRateSet(
    uint256 rate
);
```

Emitted when an impairment amount is set to reflect unrealized losses

```solidity
event ImpairmentSet(
    uint256 amount
);
```

Emitted when deploy, reconcile, and schedule permissions are set for a list of addresses

```solidity
event PermissionsSet(
    address[] addresses,
    bool[]    canDeploy,
    bool[]    canReconcile,
    bool[]    canSchedule
);
```

Emitted when the active yield schedule is updated with a new amount and duration. Currently the `id` is always zero.

```solidity
event YieldScheduleUpdated(
    uint256 id,
    uint256 yield,
    uint32  duration
);
```

