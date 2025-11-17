# AssetController

The Asset Controller mediates between deposit assets and a pool asset. It wraps deposit assets into pool assets, unwraps pool assets back to deposit assets, supports strategy deployments and reconciliations, and gates actions per asset.

## Functions

### `wrap`

Locks deposit assets and mints pool assets to the caller. Callable by the configured router when the asset is allowed to be wrapped.

```solidity
function wrap(
    address assetIn,
    uint256 amountIn
) external returns (uint256 amountOut);
```

#### Parameters

| Index |    Name    |   Type   | Description |
| :---: | :--------: | :------: | ----------- |
|   0   | `assetIn`  | `address` | Deposit asset to wrap |
|   1   | `amountIn` | `uint256` | Amount of deposit asset to wrap |

#### Return Values

| Index |    Name    |   Type   | Description |
| :---: | :--------: | :------: | ----------- |
|   0   | `amountOut` | `uint256` | Pool assets minted |

### `unwrap`

Burns pool assets and returns deposit assets to the caller. Callable by the configured router when the asset is allowed to be unwrapped.

```solidity
function unwrap(
    address assetOut,
    uint256 burnAmount
) external returns (uint256 amountOut);
```

#### Parameters

| Index |    Name     |   Type   | Description |
| :---: | :---------: | :------: | ----------- |
|   0   | `assetOut`  | `address` | Deposit asset to return |
|   1   | `burnAmount` | `uint256` | Pool assets to burn |

#### Return Values

| Index |    Name    |   Type   | Description |
| :---: | :--------: | :------: | ----------- |
|   0   | `amountOut` | `uint256` | Deposit assets sent to caller |

### `deploy`

Burns pool assets held by a strategy and returns deposit assets to that strategy. Callable by strategies that are allowlisted.

```solidity
function deploy(
    address assetOut,
    uint256 amountOut
) external returns (uint256 amountIn);
```

#### Parameters

| Index |    Name    |   Type   | Description |
| :---: | :--------: | :------: | ----------- |
|   0   | `assetOut` | `address` | Deposit asset to withdraw |
|   1   | `amountOut` | `uint256` | Deposit assets to send to caller |

#### Return Values

| Index |   Name    |   Type   | Description |
| :---: | :-------: | :------: | ----------- |
|   0   | `amountIn` | `uint256` | Pool assets burned |

### `reconcile`

Locks deposit assets held by a strategy and mints pool assets to that strategy. Callable by strategies that are allowlisted.

```solidity
function reconcile(
    address assetIn,
    uint256 amountIn
) external returns (uint256 amountOut);
```

#### Parameters

| Index |   Name   |   Type   | Description |
| :---: | :------: | :------: | ----------- |
|   0   | `assetIn` | `address` | Deposit asset to return into the controller |
|   1   | `amountIn` | `uint256` | Deposit assets to pull from caller |

#### Return Values

| Index |    Name    |   Type   | Description |
| :---: | :--------: | :------: | ----------- |
|   0   | `amountOut` | `uint256` | Pool assets minted to caller |

## Admin Functions

### `setAssets`

Configures per asset permissions for wrap, unwrap, deploy, and reconcile. Arrays must be equal length. Each asset must be a valid `COMPOSITE_DEPOSIT_ASSET` in Globals

```solidity
function setAssets(
    address[] calldata depositAssets,
    bool[]    calldata canWrap,
    bool[]    calldata canUnwrap,
    bool[]    calldata canDeploy,
    bool[]    calldata canReconcile
) external;
```

#### Parameters

| Index |      Name       |    Type    | Description |
| :---: | :-------------: | :--------: | ----------- |
|   0   | `depositAssets` | `address[]` | Assets to configure |
|   1   |    `canWrap`    |  `bool[]`   | Flags for wrapping permission per asset |
|   2   |   `canUnwrap`   |  `bool[]`   | Flags for unwrapping permission per asset |
|   3   |   `canDeploy`   |  `bool[]`   | Flags for deploy permission per asset |
|   4   | `canReconcile`  |  `bool[]`   | Flags for reconcile permission per asset |

### `setOracle`

Sets the oracle used to quote conversions. Oracle must be a valid `CONTROLLER_ORACLE` in Globals

```solidity
function setOracle(
    address oracle
) external;
```

#### Parameters

| Index |  Name   |   Type    | Description |
| :---: | :-----: | :-------: | ----------- |
|   0   | `oracle` | `address` | Oracle contract address |

### `setRouter`

Sets the router that is authorized to call `wrap` and `unwrap`. Router must be a valid `SYRUP_BTC_ROUTER` in Globals

```solidity
function setRouter(
    address router
) external;
```

#### Parameters

| Index |  Name   |   Type    | Description |
| :---: | :-----: | :-------: | ----------- |
|   0   | `router` | `address` | Router contract address |

### `setStrategies`

Sets which addresses are strategies allowed to call `deploy` and `reconcile`. When enabling an address it must be a valid `BITCOIN_STRATEGY` in Globals

```solidity
function setStrategies(
    address[] calldata addresses,
    bool[]    calldata flags
) external;
```

#### Parameters

| Index |    Name     |     Type     | Description |
| :---: | :---------: | :----------: | ----------- |
|   0   | `addresses` | `address[]`  | Strategy addresses to update |
|   1   |  `flags`    |   `bool[]`   | Whether each address is enabled as a strategy |

## Views

```solidity
function canDeploy(
    address asset
) external view returns (bool canDeploy);

function canReconcile(
    address asset
) external view returns (bool canReconcile);

function canUnwrap(
    address asset
) external view returns (bool canUnwrap);

function canWrap(
    address asset
) external view returns (bool canWrap);

function depositAssets(
    address asset
) external view returns (uint256 balance);

function isStrategy(
    address target
) external view returns (bool isStrategy);

function locked() external view returns (uint256 locked);
function oracle() external view returns (address oracle);
function poolAsset() external view returns (address poolAsset);
function router() external view returns (address router);

function poolAssets(
    address asset
) external view returns (uint256 balance);
```

## Events

Emitted when deposit assets are deployed from the controller to a strategy and the corresponding pool assets are burned

```solidity
event AssetsDeployed(
    address indexed recipient,
    address indexed asset,
    uint256 deployed,
    uint256 burned
);
```

Emitted when deposit assets are reconciled back into the controller from a strategy and the corresponding pool assets are minted

```solidity
event AssetsReconciled(
    address indexed recipient,
    address indexed asset,
    uint256 reconciled,
    uint256 minted
);
```

Emitted when per asset permissions are updated for wrap, unwrap, deploy, and reconcile

```solidity
event AssetsSet(
    address[] assets,
    bool[]    canWrap,
    bool[]    canUnwrap,
    bool[]    canDeploy,
    bool[]    canReconcile
);
```

Emitted when pool assets are burned to return deposit assets to the router

```solidity
event AssetsUnwrapped(
    address indexed recipient,
    address indexed asset,
    uint256 unwrapped,
    uint256 burned
);
```

Emitted when deposit assets are wrapped from the router and pool assets are minted

```solidity
event AssetsWrapped(
    address indexed recipient,
    address indexed asset,
    uint256 wrapped,
    uint256 minted
);
```

Emitted when the oracle address used for pricing is updated

```solidity
event OracleSet(
    address indexed oracle
);
```

Emitted when the router address authorized to wrap and unwrap is updated

```solidity
event RouterSet(
    address indexed router
);
```

Emitted when the strategy allowlist is updated

```solidity
event StrategiesSet(
    address[] addresses,
    bool[]    flags
);
```
