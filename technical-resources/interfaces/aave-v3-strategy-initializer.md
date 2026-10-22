# AaveV3StrategyInitializer



## Functions

### `aavePool`

Returns the address of the Aave V3 pool.

```solidity
    function aavePool()
        view
        returns (
            address aavePool
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description                  |
| :---: | :--------: | :-------: | :-----------: | ---------------------------- |
|   0   | `aavePool` | `address` |   `address`   | Address of the Aave V3 pool. |



### `aaveToken`

Returns the address of the Aave token.

```solidity
    function aaveToken()
        view
        returns (
            address aaveToken
        );
```

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description                |
| :---: | :---------: | :-------: | :-----------: | -------------------------- |
|   0   | `aaveToken` | `address` |   `address`   | Address of the Aave token. |



### `fundsAsset`

Returns the address of the asset used for strategy funds.

```solidity
    function fundsAsset()
        view
        returns (
            address fundsAsset
        );
```

#### Return Values:

| Index |     Name     |    Type   | Internal Type | Description                 |
| :---: | :----------: | :-------: | :-----------: | --------------------------- |
|   0   | `fundsAsset` | `address` |   `address`   | Address of the funds asset. |



### `impairedAssets`

Returns the full asset-denominated impairment recorded for the strategy.

```solidity
    function impairedAssets()
        view
        returns (
            uint256 impairedAssets
        );
```

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                                                 |
| :---: | :--------------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   | `impairedAssets` | `uint256` |   `uint256`   | Funds-asset amount of impairment recorded for the strategy. |



### `isLossRecognized`

Returns whether a final loss has been recognized for this strategy.

```solidity
    function isLossRecognized()
        view
        returns (
            bool isLossRecognized
        );
```

#### Return Values:

| Index |        Name        |  Type  | Internal Type | Description                                                     |
| :---: | :----------------: | :----: | :-----------: | --------------------------------------------------------------- |
|   0   | `isLossRecognized` | `bool` |     `bool`    | Whether the strategy is shut down after final loss recognition. |



### `lastRecordedTotalAssets`

Returns the funds-asset equivalent of the Aave position recorded at the end of the most recent state-changing call. Used as the baseline against which yield (and therefore fees) accrue.

```solidity
    function lastRecordedTotalAssets()
        view
        returns (
            uint256 lastRecordedTotalAssets
        );
```

#### Return Values:

| Index |            Name           |    Type   | Internal Type | Description                                                           |
| :---: | :-----------------------: | :-------: | :-----------: | --------------------------------------------------------------------- |
|   0   | `lastRecordedTotalAssets` | `uint256` |   `uint256`   | Last recorded funds-asset equivalent of the strategy's Aave position. |



### `referralCode`

Returns the referral code used when depositing into Aave.

```solidity
    function referralCode()
        view
        returns (
            uint16 referralCode
        );
```

#### Return Values:

| Index |      Name      |   Type   | Internal Type | Description                                   |
| :---: | :------------: | :------: | :-----------: | --------------------------------------------- |
|   0   | `referralCode` | `uint16` |    `uint16`   | Referral code used when depositing into Aave. |



### `strategyDelegateFeeRate`

Returns the percentage of yield collected by the strategy delegate. Defined with 6 decimals of precision (1e6 == 100%).

```solidity
    function strategyDelegateFeeRate()
        view
        returns (
            uint32 strategyDelegateFeeRate
        );
```

#### Return Values:

| Index |            Name           |   Type   | Internal Type | Description                                             |
| :---: | :-----------------------: | :------: | :-----------: | ------------------------------------------------------- |
|   0   | `strategyDelegateFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate. |



### `strategyManager`

Returns the address of the strategy manager contract.

```solidity
    function strategyManager()
        view
        returns (
            address strategyManager
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                      |
| :---: | :---------------: | :-------: | :-----------: | -------------------------------- |
|   0   | `strategyManager` | `address` |   `address`   | Address of the strategy manager. |



### `strategyMetadata`

Returns arbitrary metadata associated with this instance of the Aave V3 strategy.

```solidity
    function strategyMetadata()
        view
        returns (
            string strategyMetadata
        );
```

#### Return Values:

| Index |        Name        |   Type   | Internal Type | Description                                     |
| :---: | :----------------: | :------: | :-----------: | ----------------------------------------------- |
|   0   | `strategyMetadata` | `string` |    `string`   | Optional metadata associated with the strategy. |



### `strategyProtocolFeeRate`

Returns the percentage of yield collected by the Maple treasury. Defined with 6 decimals of precision (1e6 == 100%).

```solidity
    function strategyProtocolFeeRate()
        view
        returns (
            uint32 strategyProtocolFeeRate
        );
```

#### Return Values:

| Index |            Name           |   Type   | Internal Type | Description                                          |
| :---: | :-----------------------: | :------: | :-----------: | ---------------------------------------------------- |
|   0   | `strategyProtocolFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury. |



### `useVirtualUnderlyingBalance`

Returns whether available liquidity is queried using getVirtualUnderlyingBalance. If false, available liquidity is queried using the funds-asset balance of the aToken.

```solidity
    function useVirtualUnderlyingBalance()
        view
        returns (
            bool useVirtualUnderlyingBalance
        );
```

#### Return Values:

| Index |              Name             |  Type  | Internal Type | Description                                                               |
| :---: | :---------------------------: | :----: | :-----------: | ------------------------------------------------------------------------- |
|   0   | `useVirtualUnderlyingBalance` | `bool` |     `bool`    | Whether getVirtualUnderlyingBalance is used to query available liquidity. |



## Events

### `Initialized`

Emitted when the Aave V3 strategy proxy is initialized.

```solidity
    event Initialized(
        address strategyManager,
        AaveV3StrategyInitializerParams params
    );
```

#### Parameters:

| Index |        Name       |    Type   |               Internal Type              | Description                                            |
| :---: | :---------------: | :-------: | :--------------------------------------: | ------------------------------------------------------ |
|   0   | `strategyManager` | `address` |                 `address`                | Address of the strategy manager contract.              |
|   1   |      `params`     |  `tuple`  | `struct AaveV3StrategyInitializerParams` | Aave V3 strategy parameters set during initialization. |



## Structs

### `AaveV3StrategyInitializerParams`

Parameters required to initialize an Aave V3 strategy. Initializer arguments are encoded as abi.encode(strategyManager) || abi.encode(params).

```solidity
    struct AaveV3StrategyInitializerParams {
        address aaveToken;
        uint32 strategyDelegateFeeRate;
        uint32 strategyProtocolFeeRate;
        uint16 referralCode;
        bool useVirtualUnderlyingBalance;
        string strategyMetadata;
    }
```

#### Members:

| Index |              Name             |    Type   | Internal Type | Description                                                   |
| :---: | :---------------------------: | :-------: | :-----------: | ------------------------------------------------------------- |
|   0   |          `aaveToken`          | `address` |   `address`   | Address of the Aave token.                                    |
|   1   |   `strategyDelegateFeeRate`   |  `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate.       |
|   2   |   `strategyProtocolFeeRate`   |  `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury.          |
|   3   |         `referralCode`        |  `uint16` |    `uint16`   | Referral code used when depositing into Aave.                 |
|   4   | `useVirtualUnderlyingBalance` |   `bool`  |     `bool`    | Whether to query liquidity using getVirtualUnderlyingBalance. |
|   5   |       `strategyMetadata`      |  `string` |    `string`   | Optional metadata associated with the Aave V3 strategy.       |

