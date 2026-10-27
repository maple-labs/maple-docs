# AaveV3Strategy



## Functions

### `HUNDRED_PERCENT`

```solidity
    function HUNDRED_PERCENT()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



### `STRATEGY_TYPE`

```solidity
    function STRATEGY_TYPE()
        view
        returns (
            string
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `string` |    `string`   |             |



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



### `assetsUnderManagement`

Returns the funds-asset equivalent of the strategy's Aave position net of accrued yield fees. Returns zero after final loss recognition.

```solidity
    function assetsUnderManagement()
        view
        returns (
            uint256 assetsUnderManagement
        );
```

#### Return Values:

| Index |           Name          |    Type   | Internal Type | Description                                                            |
| :---: | :---------------------: | :-------: | :-----------: | ---------------------------------------------------------------------- |
|   0   | `assetsUnderManagement` | `uint256` |   `uint256`   | Funds-asset equivalent currently attributable to the strategy manager. |



### `availableToWithdraw`

Returns the funds-asset amount that can be withdrawn immediately by the strategy manager, bounded by Aave's available liquidity and net of accrued yield fees that would be collected before a withdrawal. Returns zero after final loss recognition or when the Aave reserve is inactive or paused.

```solidity
    function availableToWithdraw()
        view
        returns (
            uint256 availableToWithdraw
        );
```

#### Return Values:

| Index |          Name         |    Type   | Internal Type | Description                                                          |
| :---: | :-------------------: | :-------: | :-----------: | -------------------------------------------------------------------- |
|   0   | `availableToWithdraw` | `uint256` |   `uint256`   | Funds-asset amount immediately withdrawable by the strategy manager. |



### `claimRewards`

Claims rewards from the Aave Incentives Controller to the Maple treasury. Callable only by the strategy delegate or operational admin.

```solidity
    function claimRewards(
        address[] assets,
        uint256 amount,
        address rewardToken
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |     Type    | Internal Type | Description                                                                                  |
| :---: | :-----------: | :---------: | :-----------: | -------------------------------------------------------------------------------------------- |
|   0   |    `assets`   | `address[]` |  `address[]`  | The list of assets to check eligible distributions before claiming rewards.                  |
|   1   |    `amount`   |  `uint256`  |   `uint256`   | The amount of rewards to claim. Pass max uint256 to claim the full unclaimed reward balance. |
|   2   | `rewardToken` |  `address`  |   `address`   | The address of the reward token.                                                             |



### `factory`

The address of the proxy factory.

```solidity
    function factory()
        view
        returns (
            address factory_
        );
```

#### Return Values:

| Index |    Name    |    Type   | Internal Type | Description |
| :---: | :--------: | :-------: | :-----------: | ----------- |
|   0   | `factory_` | `address` |   `address`   |             |



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



### `fundUnderlyingStrategy`

Deploys funds asset already held by this contract into Aave. Callable only by the bound strategy manager. Accrues outstanding fees before depositing and refreshes the fee-accrual baseline to the post-deposit position. Reverts after final loss recognition.

```solidity
    function fundUnderlyingStrategy(
        uint256 assetsIn,
        bytes data
    )
        nonpayable
        returns (
            uint256 deployedAssets
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                                                  |
| :---: | :--------: | :-------: | :-----------: | ---------------------------------------------------------------------------- |
|   0   | `assetsIn` | `uint256` |   `uint256`   | Amount of funds asset to deploy. Must already be held by this contract.      |
|   1   |   `data`   |  `bytes`  |    `bytes`    | Reserved for future strategy-specific calldata. Unused by the Aave strategy. |

#### Return Values:

| Index |       Name       |    Type   | Internal Type | Description                            |
| :---: | :--------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `deployedAssets` | `uint256` |   `uint256`   | Funds-asset amount deployed into Aave. |



### `globals`

Returns the address of the Maple Globals contract.

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
|   0   | `globals` | `address` |   `address`   | Address of the Maple Globals contract. |



### `impair`

Increases the asset-denominated impairment recorded for the strategy. Callable only by the strategy delegate or operational admin. Does not affect reported AUM or withdrawable assets.

```solidity
    function impair(
        uint256 assets
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                              |
| :---: | :------: | :-------: | :-----------: | -------------------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Funds-asset amount of impairment to add to the strategy. |



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



### `implementation`

The address of the implementation contract being proxied.

```solidity
    function implementation()
        view
        returns (
            address implementation_
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `implementation_` | `address` |   `address`   |             |



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



### `mapleTreasury`

Returns the Maple treasury address.

```solidity
    function mapleTreasury()
        view
        returns (
            address mapleTreasury
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                    |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `mapleTreasury` | `address` |   `address`   | Address of the Maple treasury. |



### `migrate`

Modifies the proxy's storage by delegate-calling a migrator contract with some arguments. Access control logic critical since caller can force a selfdestruct via a malicious \`migrator\_\` which is delegatecalled.

```solidity
    function migrate(
        address migrator_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                      |
| :---: | :----------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |  `migrator_` | `address` |   `address`   | The address of a migrator contract.              |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | Some encoded arguments to use for the migration. |



### `multicall`

Allows EOAs to batch admin calls.

```solidity
    function multicall(
        bytes[] data
    )
        nonpayable;
```

#### Parameters:

| Index |  Name  |    Type   | Internal Type | Description        |
| :---: | :----: | :-------: | :-----------: | ------------------ |
|   0   | `data` | `bytes[]` |   `bytes[]`   | Array of calldata. |



### `recognizeLoss`

Marks the strategy as shut down after all reasonably recoverable assets have been withdrawn. Callable only by the strategy delegate or operational admin. This is final and causes reported AUM and availability to be zero.

```solidity
    function recognizeLoss()
        nonpayable;
```



### `recoverPosition`

Recovers the remaining underlying position to the Maple treasury after final loss recognition. Callable only by the strategy delegate or operational admin.

```solidity
    function recoverPosition()
        nonpayable;
```



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



### `removeImpairment`

Decreases the asset-denominated impairment recorded for the strategy. Callable only by the strategy delegate or operational admin. Does not affect reported AUM or withdrawable assets.

```solidity
    function removeImpairment(
        uint256 assets
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                                   |
| :---: | :------: | :-------: | :-----------: | ------------------------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Funds-asset amount of impairment to remove from the strategy. |



### `securityAdmin`

Returns the address of the security admin.

```solidity
    function securityAdmin()
        view
        returns (
            address securityAdmin
        );
```

#### Return Values:

| Index |       Name      |    Type   | Internal Type | Description                    |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `securityAdmin` | `address` |   `address`   | Address of the security admin. |



### `setImplementation`

Modifies the proxy's implementation address.

```solidity
    function setImplementation(
        address newImplementation_
    )
        nonpayable;
```

#### Parameters:

| Index |         Name         |    Type   | Internal Type | Description                                |
| :---: | :------------------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `newImplementation_` | `address` |   `address`   | The address of an implementation contract. |



### `setMetadata`

Updates the metadata of the Aave V3 strategy. Callable only by the strategy delegate or operational admin.

```solidity
    function setMetadata(
        string metadata
    )
        nonpayable;
```

#### Parameters:

| Index |    Name    |   Type   | Internal Type | Description                                     |
| :---: | :--------: | :------: | :-----------: | ----------------------------------------------- |
|   0   | `metadata` | `string` |    `string`   | Optional metadata associated with the strategy. |



### `setReferralCode`

Sets the referral code used for future deposits into Aave. Callable only by the strategy delegate or operational admin.

```solidity
    function setReferralCode(
        uint16 referralCode
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |   Type   | Internal Type | Description                                   |
| :---: | :------------: | :------: | :-----------: | --------------------------------------------- |
|   0   | `referralCode` | `uint16` |    `uint16`   | Referral code used when depositing into Aave. |



### `setStrategyDelegateFeeRate`

Sets the percentage of yield collected by the strategy delegate. Callable only by the strategy delegate. Accrues outstanding fees before updating the rate. The combined strategy delegate and protocol fee rates cannot exceed 1e6.

```solidity
    function setStrategyDelegateFeeRate(
        uint32 strategyDelegateFeeRate
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                                 |
| :---: | :-----------------------: | :------: | :-----------: | ----------------------------------------------------------------------------------------------------------- |
|   0   | `strategyDelegateFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate, defined with 6 decimals of precision (1e6 == 100%). |



### `setStrategyProtocolFeeRate`

Sets the percentage of yield collected by the Maple treasury. Callable only by protocol admins. Accrues outstanding fees before updating the rate. The combined strategy delegate and protocol fee rates cannot exceed 1e6.

```solidity
    function setStrategyProtocolFeeRate(
        uint32 strategyProtocolFeeRate
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                              |
| :---: | :-----------------------: | :------: | :-----------: | -------------------------------------------------------------------------------------------------------- |
|   0   | `strategyProtocolFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury, defined with 6 decimals of precision (1e6 == 100%). |



### `setUseVirtualUnderlyingBalance`

Sets whether available liquidity is queried using getVirtualUnderlyingBalance. Callable only by protocol admins.

```solidity
    function setUseVirtualUnderlyingBalance(
        bool useVirtualUnderlyingBalance
    )
        nonpayable;
```

#### Parameters:

| Index |              Name             |  Type  | Internal Type | Description                                                               |
| :---: | :---------------------------: | :----: | :-----------: | ------------------------------------------------------------------------- |
|   0   | `useVirtualUnderlyingBalance` | `bool` |     `bool`    | Whether available liquidity is queried using getVirtualUnderlyingBalance. |



### `strategyDelegate`

Returns the strategy delegate that receives the delegate's share of accrued yield for the bound strategy manager.

```solidity
    function strategyDelegate()
        view
        returns (
            address strategyDelegate
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                       |
| :---: | :----------------: | :-------: | :-----------: | --------------------------------- |
|   0   | `strategyDelegate` | `address` |   `address`   | Address of the strategy delegate. |



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



### `unrealizedLosses`

Returns the asset-denominated unrealized losses reported for the strategy, capped by reported AUM.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint256 unrealizedLosses
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description                                                        |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------------------------------ |
|   0   | `unrealizedLosses` | `uint256` |   `uint256`   | Funds-asset amount of unrealized losses reported for the strategy. |



### `upgrade`

Upgrades a contract implementation to a specific version. Access control logic critical since caller can force a selfdestruct via a malicious \`migrator\_\` which is delegatecalled.

```solidity
    function upgrade(
        uint256 toVersion_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                    |
| :---: | :----------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `toVersion_` | `uint256` |   `uint256`   | The version to upgrade to.                     |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | Some encoded arguments to use for the upgrade. |



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



### `withdrawFromUnderlyingStrategy`

Redeems Aave aTokens back into funds asset and delivers the withdrawn assets to \`destination\`. Callable only by the bound strategy manager. Accrues outstanding fees before withdrawing and refreshes the fee-accrual baseline to the post-withdrawal position. Reverts after final loss recognition.

```solidity
    function withdrawFromUnderlyingStrategy(
        address destination,
        uint256 assets,
        bytes data
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                                                  |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------------------------------------------------------- |
|   0   | `destination` | `address` |   `address`   | Address that receives the withdrawn funds asset.                             |
|   1   |    `assets`   | `uint256` |   `uint256`   | Amount of funds asset to withdraw from Aave.                                 |
|   2   |     `data`    |  `bytes`  |    `bytes`    | Reserved for future strategy-specific calldata. Unused by the Aave strategy. |



## Events

### `Impaired`

Emitted when the strategy's impaired assets are increased.

```solidity
    event Impaired(
        uint256 assets
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                             |
| :---: | :------: | :-------: | :-----------: | ------------------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Funds-asset amount of impairment added to the strategy. |



### `ImpairmentRemoved`

Emitted when the strategy's impaired assets are decreased.

```solidity
    event ImpairmentRemoved(
        uint256 assets
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                                 |
| :---: | :------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   | `assets` | `uint256` |   `uint256`   | Funds-asset amount of impairment removed from the strategy. |



### `LossRecognized`

Emitted when the strategy is shut down after final loss recognition.

```solidity
    event LossRecognized();
```



### `PositionRecovered`

Emitted when the remaining Aave position is recovered to the Maple treasury after final loss recognition.

```solidity
    event PositionRecovered(
        uint256 shares
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                  |
| :---: | :------: | :-------: | :-----------: | ---------------------------- |
|   0   | `shares` | `uint256` |   `uint256`   | Amount of aTokens recovered. |



### `ReferralCodeSet`

Emitted when the referral code used for future deposits is set.

```solidity
    event ReferralCodeSet(
        uint16 referralCode
    );
```

#### Parameters:

| Index |      Name      |   Type   | Internal Type | Description                                   |
| :---: | :------------: | :------: | :-----------: | --------------------------------------------- |
|   0   | `referralCode` | `uint16` |    `uint16`   | Referral code used when depositing into Aave. |



### `RewardsClaimed`

Emitted when rewards are claimed from the Aave Rewards Controller.

```solidity
    event RewardsClaimed(
        address indexed rewardToken,
        uint256 amount
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                        |
| :---: | :-----------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `rewardToken` | `address` |   `address`   | The address of the reward token.   |
|   1   |    `amount`   | `uint256` |   `uint256`   | The amount of rewardToken claimed. |



### `StrategyDelegateFeeRateSet`

Emitted when the strategy delegate fee rate is set.

```solidity
    event StrategyDelegateFeeRateSet(
        uint32 strategyDelegateFeeRate
    );
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                                 |
| :---: | :-----------------------: | :------: | :-----------: | ----------------------------------------------------------------------------------------------------------- |
|   0   | `strategyDelegateFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the strategy delegate, defined with 6 decimals of precision (1e6 == 100%). |



### `StrategyFeesCollected`

Emitted once per fee-accrual cycle when yield fees are withdrawn from the underlying Aave position.

```solidity
    event StrategyFeesCollected(
        uint256 delegateFee,
        uint256 protocolFee
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                       |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   | `delegateFee` | `uint256` |   `uint256`   | Funds-asset amount paid to the strategy delegate. |
|   1   | `protocolFee` | `uint256` |   `uint256`   | Funds-asset amount paid to the Maple treasury.    |



### `StrategyFunded`

Emitted when funds asset is deployed into the underlying Aave strategy.

```solidity
    event StrategyFunded(
        address indexed strategyManager,
        uint256 assetsIn,
        uint256 deployedAssets
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                               |
| :---: | :---------------: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   | `strategyManager` | `address` |   `address`   | Address of the strategy manager that initiated the call.  |
|   1   |     `assetsIn`    | `uint256` |   `uint256`   | Amount of funds asset consumed from the strategy balance. |
|   2   |  `deployedAssets` | `uint256` |   `uint256`   | Funds-asset amount deployed into Aave.                    |



### `StrategyMetadataSet`

Emitted when the strategy metadata is set.

```solidity
    event StrategyMetadataSet(
        string strategyMetadata
    );
```

#### Parameters:

| Index |        Name        |   Type   | Internal Type | Description                                     |
| :---: | :----------------: | :------: | :-----------: | ----------------------------------------------- |
|   0   | `strategyMetadata` | `string` |    `string`   | Optional metadata associated with the strategy. |



### `StrategyProtocolFeeRateSet`

Emitted when the strategy protocol fee rate is set.

```solidity
    event StrategyProtocolFeeRateSet(
        uint32 strategyProtocolFeeRate
    );
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                                                                                              |
| :---: | :-----------------------: | :------: | :-----------: | -------------------------------------------------------------------------------------------------------- |
|   0   | `strategyProtocolFeeRate` | `uint32` |    `uint32`   | Percentage of yield collected by the Maple treasury, defined with 6 decimals of precision (1e6 == 100%). |



### `StrategyWithdrawal`

Emitted when funds asset is withdrawn from the underlying Aave strategy to a destination.

```solidity
    event StrategyWithdrawal(
        address indexed destination,
        uint256 assetsOut
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                         |
| :---: | :-----------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   | `destination` | `address` |   `address`   | Address that received the funds asset.              |
|   1   |  `assetsOut`  | `uint256` |   `uint256`   | Amount of funds asset delivered to the destination. |



### `Upgraded`

The instance was upgraded.

```solidity
    event Upgraded(
        uint256 toVersion_,
        bytes arguments_
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                    |
| :---: | :----------: | :-------: | :-----------: | ------------------------------ |
|   0   | `toVersion_` | `uint256` |   `uint256`   | The new version of the loan.   |
|   1   | `arguments_` |  `bytes`  |    `bytes`    | The upgrade arguments, if any. |



### `UseVirtualUnderlyingBalanceSet`

Emitted when the liquidity query mode is set.

```solidity
    event UseVirtualUnderlyingBalanceSet(
        bool useVirtualUnderlyingBalance
    );
```

#### Parameters:

| Index |              Name             |  Type  | Internal Type | Description                                                               |
| :---: | :---------------------------: | :----: | :-----------: | ------------------------------------------------------------------------- |
|   0   | `useVirtualUnderlyingBalance` | `bool` |     `bool`    | Whether available liquidity is queried using getVirtualUnderlyingBalance. |

