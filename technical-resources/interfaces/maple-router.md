# MapleRouter

Administrative and integration router supporting deposit flows with optional authorization and permits, swap‑assisted deposits via DEX aggregators, asset allowlisting, and an admin `skim` utility for recovering tokens.

## Key Structs

```solidity
    struct Authorization {
        bool    enabled;
        uint256 bitmap;
        uint256 deadline;
        uint8   v;
        bytes32 r;
        bytes32 s;
    }

    struct Permit {
        bool    enabled;
        uint256 deadline;
        uint8   v;
        bytes32 r;
        bytes32 s;
    }

    struct Swap {
        address router;
        address allowanceHolder;
        bytes   calldata_;
        uint256 minAssetsOut;
    }
```

 

## Functions

### `skim`

Skims any balance of a token to a destination (protocol admin only).

```solidity
    function skim(
        address token,
        address destination
    )
        external
        returns (
            uint256 skimmed
        );
```

#### Parameters:

| Index |    Name     |   Type   | Internal Type | Description                          |
| :---: | :---------: | :------: | :-----------: | ------------------------------------ |
|   0   |  `token`    | `address`|   `address`   | Token to skim from the router        |
|   1   | `destination`| `address`|   `address`  | Recipient of skimmed tokens          |

#### Return Values:

| Index |   Name   |   Type   | Internal Type | Description            |
| :---: | :------: | :------: | :-----------: | ---------------------- |
|   0   | `skimmed`| `uint256`|   `uint256`   | Amount of tokens sent  |


### `deposit`

Deposits assets into a Maple pool with optional authorization, permit, and swap support.

```solidity
    function deposit(
        address       poolManager,
        address       asset,
        uint256       amount,
        bytes32       metadata,
        Permit        calldata permit,
        Swap          calldata swap,
        Authorization calldata auth
    ) external;
```

#### Parameters:

| Index |     Name     |   Type    | Internal Type | Description                                                        |
| :---: | :----------: | :-------: | :-----------: | ------------------------------------------------------------------ |
|   0   | `poolManager`| `address` |   `address`   | Pool Manager of the destination pool                               |
|   1   |   `asset`    | `address` |   `address`   | Input asset to deposit (can differ from pool asset if using swap)  |
|   2   |   `amount`   | `uint256` |   `uint256`   | Amount of input asset to deposit                                   |
|   3   |  `metadata`  | `bytes32` |   `bytes32`   | Optional deposit metadata                                          |
|   4   |   `permit`   | `Permit`  |   `Permit`    | Optional ERC‑2612 permit for the input asset                       |
|   5   |    `swap`    |  `Swap`   |    `Swap`     | Optional swap details when input asset differs from pool asset     |
|   6   |    `auth`    |`Authorization`|`Authorization`| Optional authorization for first‑time depositors               |

## Events

### `AllowedAllowanceHolderSet`

```solidity
event AllowedAllowanceHolderSet(
    address indexed allowanceHolder,
    bool    indexed allowed
);
```

### `AllowedRouterFunctionSet`

```solidity
event AllowedRouterFunctionSet(
    address indexed swapRouter,
    bytes4  indexed functionSelector,
    bool    indexed allowed
);
```

### `AllowedAssetsSet`

```solidity
event AllowedAssetsSet(
    address[] assets,
    bool[]    values
);
```

### `AssetWhitelistingSet`

```solidity
event AssetWhitelistingSet(
    bool value
);
```

### `MapleRouterSwap`

```solidity
event MapleRouterSwap(
    address indexed inputAsset,
    address indexed outputAsset,
    uint256 inputAmount,
    uint256 outputAmount
);
```

### `Deposit`

```solidity
event Deposit(
    address indexed depositor,
    address indexed pool,
    uint256 assets,
    uint256 shares,
    bytes32 metadata
);
```

### `Skimmed`

```solidity
event Skimmed(
    address indexed token,
    uint256 amount,
    address indexed destination
);
```
