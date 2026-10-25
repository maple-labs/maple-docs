# LiquidityRouter



## Constructor

```solidity
    constructor(
        address globals_
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `globals_` | `address` |   `address`   |             |



## Functions

### `executeActions`

Executes actions atomically in their listed order. Only a registered liquidity bot can call this function. The call reverts when the deadline has passed or any action fails.

```solidity
    function executeActions(
        Action[] actions,
        uint256 deadline
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |    Type   |   Internal Type   | Description                                      |
| :---: | :--------: | :-------: | :---------------: | ------------------------------------------------ |
|   0   |  `actions` | `tuple[]` | `struct Action[]` | Ordered actions to execute.                      |
|   1   | `deadline` | `uint256` |     `uint256`     | Latest timestamp at which the batch can execute. |



### `globals`

Returns the Maple globals contract used for access control and function pausing.

```solidity
    function globals()
        view
        returns (
            address globals
        );
```

#### Return Values:

| Index |    Name   |    Type   | Internal Type | Description                            |
| :---: | :-------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `globals` | `address` |   `address`   | Address of the Maple globals contract. |



## Events

### `ActionExecuted`

Emitted after an action is executed.

```solidity
    event ActionExecuted(
        uint256 actionIndex,
        ActionType indexed actionType,
        address indexed strategyManager,
        address indexed poolManager,
        uint256 amount
    );
```

#### Parameters:

| Index |        Name       |    Type   |   Internal Type   | Description                                           |
| :---: | :---------------: | :-------: | :---------------: | ----------------------------------------------------- |
|   0   |   `actionIndex`   | `uint256` |     `uint256`     | Index of the action in the batch.                     |
|   1   |    `actionType`   |  `uint8`  | `enum ActionType` | Type of action that was executed.                     |
|   2   | `strategyManager` | `address` |     `address`     | Strategy manager the action ran against.              |
|   3   |   `poolManager`   | `address` |     `address`     | Pool manager the action concerned.                    |
|   4   |      `amount`     | `uint256` |     `uint256`     | Assets for funding and shares for redemption actions. |



## Structs

### `Action`

```solidity
    struct Action {
        ActionType actionType;
        address strategyManager;
        address poolManager;
        uint256 amount;
        bytes strategyData;
    }
```

#### Members:

| Index |        Name       |    Type   |   Internal Type   | Description                                                                                                  |
| :---: | :---------------: | :-------: | :---------------: | ------------------------------------------------------------------------------------------------------------ |
|   0   |    `actionType`   |  `uint8`  | `enum ActionType` | Type of action to execute.                                                                                   |
|   1   | `strategyManager` | `address` |     `address`     | Strategy manager the action runs against.                                                                    |
|   2   |   `poolManager`   | `address` |     `address`     | Pool manager the action concerns.                                                                            |
|   3   |      `amount`     | `uint256` |     `uint256`     | Assets to fund for \`FUND_STRATEGY\`, otherwise shares. Computed off-chain by the liquidity bot.             |
|   4   |   `strategyData`  |  `bytes`  |      `bytes`      | Data forwarded to the underlying strategy on \`FUND_STRATEGY\` and \`PROCESS_REDEMPTION\`. Unused otherwise. |



## Enums

### `ActionType`

```solidity
    enum ActionType {
        FUND_STRATEGY,
        REQUEST_REDEEM,
        CANCEL_REDEMPTION,
        PROCESS_REDEMPTION
    }
```

#### Values:

| Index |         Name         | Description                                                                                                     |
| :---: | :------------------: | --------------------------------------------------------------------------------------------------------------- |
|   0   |    `FUND_STRATEGY`   | Calls \`fundStrategyManager(poolManager, amount, strategyData)\` on the strategy manager. \`amount\` is assets. |
|   1   |   `REQUEST_REDEEM`   | Calls \`requestRedeem(poolManager, amount)\` on the strategy manager. \`amount\` is shares.                     |
|   2   |  `CANCEL_REDEMPTION` | Calls \`cancelRedemption(poolManager, amount)\` on the strategy manager. \`amount\` is shares.                  |
|   3   | `PROCESS_REDEMPTION` | Calls \`processRedemption(poolManager, amount, strategyData)\` on the strategy manager. \`amount\` is shares.   |

