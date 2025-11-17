# SyrupBitcoinRouter

Router for depositing supported Bitcoin assets into a Maple pool and requesting redemptions back to those assets. It wraps and unwraps via an Asset Controller, interacts with the Pool for shares and assets, and keeps per request state. The router supports EIP‑2612 permits where the underlying asset or pool shares implement permit.

## Key Structs

```solidity
struct Permit {
    bool    enabled;
    uint256 deadline;
    uint8   v;
    bytes32 r;
    bytes32 s;
}
```

## Functions

### `deposit`

Wraps `assetIn`, applies a mint fee by asset, mints pool shares, and forwards shares to the caller.

```solidity
function deposit(
    address assetIn,
    uint256 amountIn,
    bytes32 metadata,
    Permit  calldata permit
) external returns (uint256 sharesMinted);
```

#### Parameters

| Index |    Name    |   Type   | Description |
| :---: | :--------: | :------: | ----------- |
|   0   | `assetIn`  | `address` | Supported Bitcoin asset to deposit |
|   1   | `amountIn` | `uint256` | Amount of asset to deposit |
|   2   | `metadata` | `bytes32` | Optional metadata emitted in `Deposit` |
|   3   |  `permit`  | `Permit`  | Optional permit to set allowance |

#### Return Values

| Index |     Name      |   Type   | Description |
| :---: | :-----------: | :------: | ----------- |
|   0   | `sharesMinted` | `uint256` | Pool shares minted and sent to caller |

### `requestRedeem`

Transfers pool shares from the caller, locks them in the Pool, records a redeem request for a supported Bitcoin `assetOut`, and returns the assigned request id.

```solidity
function requestRedeem(
    address assetOut,
    uint256 shareAmount,
    bytes32 metadata,
    Permit  calldata permit
) external returns (uint256 sharesLocked, uint256 requestId);
```

#### Parameters

| Index |     Name      |   Type   | Description |
| :---: | :-----------: | :------: | ----------- |
|   0   |  `assetOut`   | `address` | Supported Bitcoin asset to receive |
|   1   | `shareAmount` | `uint256` | Pool shares to redeem |
|   2   |  `metadata`   | `bytes32` | Optional metadata emitted in `RequestRedeem` |
|   3   |   `permit`    |  `Permit`  | Optional permit to set allowance on pool shares |

#### Return Values

| Index |     Name      |   Type   | Description |
| :---: | :-----------: | :------: | ----------- |
|   0   | `sharesLocked` | `uint256` | Shares locked in the Pool |
|   1   |  `requestId`   | `uint256` | Redemption request id |

### `processRedemptions`

Processes a batch of previously queued requests after the Withdrawal Manager has processed the queue. Unwraps pool assets, applies a redemption fee by asset, and sends resulting assets to the request owner.

```solidity
function processRedemptions(
    uint256[] calldata requestIds
) external;
```

#### Parameters

| Index |    Name    |     Type     | Description |
| :---: | :--------: | :----------: | ----------- |
|   0   | `requestIds` | `uint256[]` | List of request ids to process |

### `removeRequests`

Removes all remaining unprocessed shares from the specified requests for a given owner and returns shares back to the owner.

```solidity
function removeRequests(
    address owner,
    uint256[] calldata requestIds
) external;
```

#### Parameters

| Index |   Name   |     Type     | Description |
| :---: | :------: | :----------: | ----------- |
|   0   | `owner`  |  `address`   | Request owner |
|   1   | `requestIds` | `uint256[]` | Request ids to fully remove |

### `removeSharesById`

Reduces a single request by a number of shares and returns those shares to the caller.

```solidity
function removeSharesById(
    uint256 requestId,
    uint256 sharesToRemove
) external returns (uint256 sharesReturned);
```

#### Parameters

| Index |     Name     |   Type   | Description |
| :---: | :----------: | :------: | ----------- |
|   0   | `requestId`  | `uint256` | Request id |
|   1   | `sharesToRemove` | `uint256` | Shares to remove from the request |

#### Return Values

| Index |     Name       |   Type   | Description |
| :---: | :------------: | :------: | ----------- |
|   0   | `sharesReturned` | `uint256` | Shares transferred back to caller |

## Admin Functions

### `setAssetController`

Sets the Asset Controller for a supported asset used during wrap and unwrap operations

```solidity
function setAssetController(
    address asset,
    address controller
) external;
```

#### Parameters

| Index |   Name   |   Type   | Description |
| :---: | :------: | :------: | ----------- |
|   0   |  `asset` | `address` | Supported Bitcoin asset |
|   1   | `controller` | `address` | Asset Controller for this asset |

### `setFees`

Sets the per asset mint and redemption fee rates. Values are scaled by 1e6

```solidity
function setFees(
    address asset,
    uint256 mintFee,
    uint256 redemptionFee
) external;
```

#### Parameters

| Index |     Name      |   Type   | Description |
| :---: | :-----------: | :------: | ----------- |
|   0   |   `asset`     | `address` | Asset the fee applies to |
|   1   |  `mintFee`    | `uint256` | Fee on deposit, scaled by 1e6 |
|   2   | `redemptionFee` | `uint256` | Fee on redemption, scaled by 1e6 |

## Views

```solidity
function pool() external view returns (address);
function poolManager() external view returns (address);
function locked() external view returns (uint256);

function assetController(
    address asset
) external view returns (address);

function mintFee(
    address asset
) external view returns (uint256);

function redemptionFee(
    address asset
) external view returns (uint256);

function redeemRequests(
    uint256 requestId
) external view returns (address asset, address owner, uint256 shares);
```

## Events

Emitted when the controller address for a supported asset is set or changed

```solidity
event AssetControllerSet(
    address indexed asset,
    address indexed controller
);
```

Emitted when a user deposit is processed, pool shares are minted, and any treasury fee is applied

```solidity
event Deposit(
    address indexed receiver,
    address indexed assetIn,
    uint256 amountIn,
    uint256 feeAmount,
    uint256 poolAssetAmount,
    uint256 shareAmount,
    bytes32 metadata
);
```

Emitted when per asset mint and redemption fees are updated

```solidity
event FeesSet(
    address indexed asset,
    uint256 mintFee,
    uint256 redemptionFee
);
```

Emitted when shares are removed from a specific redeem request and returned to the owner

```solidity
event RedeemRequestSharesRemoved(
    uint256 indexed requestId,
    uint256 sharesRemoved
);
```

Emitted when a redeem request record is updated with a new shares value

```solidity
event RedeemRequestUpdated(
    uint256 indexed requestId,
    uint256 newShares
);
```

Emitted when a redeem request is settled and assets are transferred to the owner and fee to treasury

```solidity
event RedemptionProcessed(
    uint256 indexed requestId,
    address owner,
    address assetOut,
    uint256 shareAmount,
    uint256 poolAssetAmount,
    uint256 amountOut,
    uint256 feeAmount
);
```

Emitted when a new redeem request is created for an owner with the desired assetOut and share amount

```solidity
event RequestRedeem(
    address indexed owner,
    uint256 indexed requestId,
    address indexed assetOut,
    uint256 shareAmount,
    bytes32 metadata
);
```
