# SkyStrategyInitializer



## Functions

### `fallbackTout`

Returns the admin-maintained mirror of Sky's PSM \`tout\`, used to value the position while Sky halts the PSM \`buyGem\` path by setting the live \`tout\` to type(uint256).max.

```solidity
    function fallbackTout()
        view
        returns (
            uint256 fallbackTout
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description                                                                         |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------------------------------------------- |
|   0   | `fallbackTout` | `uint256` |   `uint256`   | PSM \`tout\` value used for valuation while the live \`tout\` is type(uint256).max. |



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

Returns the funds-asset equivalent of the underlying position recorded at the end of the most recent state-changing call. Used as the baseline against which yield (and therefore fees) accrue.

```solidity
    function lastRecordedTotalAssets()
        view
        returns (
            uint256 lastRecordedTotalAssets
        );
```

#### Return Values:

| Index |            Name           |    Type   | Internal Type | Description                                                            |
| :---: | :-----------------------: | :-------: | :-----------: | ---------------------------------------------------------------------- |
|   0   | `lastRecordedTotalAssets` | `uint256` |   `uint256`   | Last recorded funds-asset equivalent of the strategy's sUSDS position. |



### `psm`

Returns the address of the PSM contract.

```solidity
    function psm()
        view
        returns (
            address psm
        );
```

#### Return Values:

| Index |  Name |    Type   | Internal Type | Description         |
| :---: | :---: | :-------: | :-----------: | ------------------- |
|   0   | `psm` | `address` |   `address`   | Address of the PSM. |



### `referralCode`

Returns the referral code used when depositing into Sky.

```solidity
    function referralCode()
        view
        returns (
            uint16 referralCode
        );
```

#### Return Values:

| Index |      Name      |   Type   | Internal Type | Description                                  |
| :---: | :------------: | :------: | :-----------: | -------------------------------------------- |
|   0   | `referralCode` | `uint16` |    `uint16`   | Referral code used when depositing into Sky. |



### `savingsUsds`

Returns the address of the savings USDS contract.

```solidity
    function savingsUsds()
        view
        returns (
            address savingsUsds
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description              |
| :---: | :-----------: | :-------: | :-----------: | ------------------------ |
|   0   | `savingsUsds` | `address` |   `address`   | Address of savings USDS. |



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

Returns arbitrary metadata associated with this instance of the Sky strategy.

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



### `usds`

Returns the address of the USDS contract.

```solidity
    function usds()
        view
        returns (
            address usds
        );
```

#### Return Values:

| Index |  Name  |    Type   | Internal Type | Description      |
| :---: | :----: | :-------: | :-----------: | ---------------- |
|   0   | `usds` | `address` |   `address`   | Address of USDS. |



## Events

### `Initialized`

Emitted when the Sky strategy proxy is initialized.

```solidity
    event Initialized(
        address strategyManager,
        SkyStrategyInitializerParams params
    );
```

#### Parameters:

| Index |        Name       |    Type   |             Internal Type             | Description                                        |
| :---: | :---------------: | :-------: | :-----------------------------------: | -------------------------------------------------- |
|   0   | `strategyManager` | `address` |               `address`               | Address of the strategy manager contract.          |
|   1   |      `params`     |  `tuple`  | `struct SkyStrategyInitializerParams` | Sky strategy parameters set during initialization. |



## Structs

### `SkyStrategyInitializerParams`

Parameters required to initialize a Sky strategy. Initializer arguments are encoded as abi.encode(strategyManager) || abi.encode(params).

```solidity
    struct SkyStrategyInitializerParams {
        address fundsAsset;
        address psm;
        address savingsUsds;
        uint32 strategyDelegateFeeRate;
        uint32 strategyProtocolFeeRate;
        uint16 referralCode;
        string strategyMetadata;
    }
```

#### Members:

| Index |            Name           |    Type   | Internal Type | Description                                             |
| :---: | :-----------------------: | :-------: | :-----------: | ------------------------------------------------------- |
|   0   |        `fundsAsset`       | `address` |   `address`   | Address of the asset used for strategy funds.           |
|   1   |           `psm`           | `address` |   `address`   | Address of the PSM contract.                            |
|   2   |       `savingsUsds`       | `address` |   `address`   | Address of the savings USDS contract.                   |
|   3   | `strategyDelegateFeeRate` |  `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate. |
|   4   | `strategyProtocolFeeRate` |  `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury.    |
|   5   |       `referralCode`      |  `uint16` |    `uint16`   | Referral code used when depositing into Sky.            |
|   6   |     `strategyMetadata`    |  `string` |    `string`   | Optional metadata associated with the Sky strategy.     |

