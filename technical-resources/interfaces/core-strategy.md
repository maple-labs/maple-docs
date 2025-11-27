# Core Strategy

Maple Specific strategy that allocates pool funds into an another Maple ERC‑4626 vault. Supports funding, withdrawal requests and cancellations, pushing residual assets back to the pool, and strategy reactivation after impairment.

## Functions

### `fundStrategy`

Deploys assets from the Maple pool into the strategy (only when active).

```solidity
    function fundStrategy(
        uint256 assetsIn
    )
        external;
```

#### Parameters:

| Index |    Name    |   Type   | Internal Type | Description                     |
| :---: | :--------: | :------: | :-----------: | ------------------------------- |
|   0   | `assetsIn` | `uint256`|   `uint256`   | Amount of assets to deploy      |



### `requestWithdrawFromStrategy`

Requests withdrawal of assets back to the Maple pool.

```solidity
    function requestWithdrawFromStrategy(
        uint256 assetsOut
    )
        external;
```

#### Parameters:

| Index |    Name     |   Type   | Internal Type | Description                          |
| :---: | :---------: | :------: | :-----------: | ------------------------------------ |
|   0   | `assetsOut` | `uint256`|   `uint256`   | Amount of assets requested to redeem |



### `removeShares`

Cancels or reduces a pending withdrawal by removing shares.

```solidity
    function removeShares(
        uint256 shares
    )
        external;
```

#### Parameters:

| Index |  Name   |   Type   | Internal Type | Description                                |
| :---: | :-----: | :------: | :-----------: | ------------------------------------------ |
|   0   | `shares`| `uint256`|   `uint256`   | Amount of shares to remove from the queue  |



### `removeSharesById`

Cancels or reduces a pending withdrawal by id.

```solidity
    function removeSharesById(
        uint256 requestId,
        uint256 shares
    )
        external;
```

#### Parameters:

| Index |    Name     |   Type   | Internal Type | Description                                   |
| :---: | :---------: | :------: | :-----------: | --------------------------------------------- |
|   0   | `requestId` | `uint256`|   `uint256`   | Identifier of the withdrawal request          |
|   1   |  `shares`   | `uint256`|   `uint256`   | Amount of shares to remove from that request  |



### `pushAssetsToPool`

Pushes any held funds asset back to the pool.

```solidity
    function pushAssetsToPool()
        external;
```



### `reactivateStrategy`

Reactivates a previously impaired or deactivated strategy.

```solidity
    function reactivateStrategy()
        external;
```



### `mapleWithdrawalManager`

Returns the strategy’s configured withdrawal manager.

```solidity
    function mapleWithdrawalManager()
        view
        returns (
            address withdrawalManagerAddress
        );
```

#### Return Values:

| Index |           Name            |  Type   | Internal Type | Description                        |
| :---: | :-----------------------: | :-----: | :-----------: | ---------------------------------- |
|   0   | `withdrawalManagerAddress`| `address`|   `address`  | Address of the withdrawal manager  |

## Events

### `AssetsTransferredToPool`

```solidity
event AssetsTransferredToPool(
    address indexed fundAsset,
    address indexed pool,
    uint256 amount
);
```

### `StrategyWithdrawalRequested`

```solidity
event StrategyWithdrawalRequested(
    uint256 assetsOut,
    uint256 escrowedShares
);
```

### `StrategyWithdrawalDecreased`

```solidity
event StrategyWithdrawalDecreased(
    uint256 sharesReturned
);
```

### `StrategyWithdrawalDecreased`

```solidity
event StrategyWithdrawalDecreased(
    uint256 indexed requestId,
    uint256 sharesReturned
);
```

### `StrategyWithdrawalUpdated`

```solidity
event StrategyWithdrawalUpdated(
    uint256 oldRequestId,
    uint256 newRequestId,
    uint256 oldSharesTotal,
    uint256 newSharesTotal
);
```

### `StrategyReactivated`

```solidity
event StrategyReactivated();
```
