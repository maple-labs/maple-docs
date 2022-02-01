# Globals

MapleGlobals maintains a central source of parameters and allowlists for the Maple protocol.

\


## Constructor

Constructor function. It emits an \`Initialized\` event.

```solidity
    constructor(
        address _governor,
        address _mpl,
        address _globalAdmin
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                                 |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------------------- |
|   0   |   `_governor`  | `address` |   `address`   | Address of Governor.                                        |
|   1   |     `_mpl`     | `address` |   `address`   | Address of the ERC-2222 Maple Token for the Maple protocol. |
|   2   | `_globalAdmin` | `address` |   `address`   | Address the Global Admin.                                   |

\


## Functions

### `acceptGovernor`

Accept the Governor position. Only the Pending Governor can call this function. It emits a \`GovernorAccepted\` event.

```solidity
    function acceptGovernor()
        nonpayable;
```

\


### `defaultGracePeriod` _\[state variable]_

The amount of time a Borrower has to make a missed payment before a default can be triggered.

```solidity
    function defaultGracePeriod()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `defaultUniswapPath` _\[state variable]_

Determines the liquidation path of various assets in Loans and the Treasury. The value provided will determine whether or not to perform a bilateral or triangular swap on Uniswap. For example, \`defaultUniswapPath\[WBTC]\[USDC]\` value would indicate what asset to convert WBTC into before conversion to USDC. If \`defaultUniswapPath\[WBTC]\[USDC] == USDC\`, then the swap is bilateral and no middle asset is swapped. If \`defaultUniswapPath\[WBTC]\[USDC] == WETH\`, then swap WBTC for WETH, then WETH for USDC.

```solidity
    function defaultUniswapPath(
        address tokenA,
        address tokenB
    )
        view
        returns (
            address
        );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                |
| :---: | :------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `tokenA` | `address` |   `address`   | The address of the asset being swapped.    |
|   1   | `tokenB` | `address` |   `address`   | The address of the final asset to receive. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                               |
| :---: | :--: | :-------: | :-----------: | ----------------------------------------- |
|   0   |      | `address` |   `address`   | The intermediary asset for swaps, if any. |

\


### `fundingPeriod` _\[state variable]_

The amount of time to allow a Borrower to drawdown on their Loan after funding period ends.

```solidity
    function fundingPeriod()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `getLatestPrice`

Fetch price for asset from Chainlink oracles.

```solidity
    function getLatestPrice(
        address asset
    )
        view
        returns (
            uint256
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                      |
| :---: | :-----: | :-------: | :-----------: | -------------------------------- |
|   0   | `asset` | `address` |   `address`   | The asset to fetch the price of. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                |
| :---: | :--: | :-------: | :-----------: | -------------------------- |
|   0   |      | `uint256` |   `uint256`   | The price of asset in USD. |

\


### `getLpCooldownParams`

Returns the \`lpCooldownPeriod\` and \`lpWithdrawWindow\` as a tuple, for convenience.

```solidity
    function getLpCooldownParams()
        view
        returns (
            uint256,
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                        |
| :---: | :--: | :-------: | :-----------: | ---------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The value of \`lpCooldownPeriod\`. |
|   1   |      | `uint256` |   `uint256`   | The value of \`lpWithdrawWindow\`. |

\


### `globalAdmin` _\[state variable]_

The Global Admin of the whole network. Has the power to switch off/on the functionality of entire protocol.

```solidity
    function globalAdmin()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `governor` _\[state variable]_

The Governor responsible for management of global Maple variables.

```solidity
    function governor()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `investorFee` _\[state variable]_

The portion of drawdown that goes to the Pool Delegates and individual Lenders.

```solidity
    function investorFee()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `isValidBalancerPool` _\[state variable]_

```solidity
    function isValidBalancerPool(
        address balancerPool
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                     |
| :---: | :------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `balancerPool` | `address` |   `address`   | The address of a Balancer Pool. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                                                  |
| :---: | :--: | :----: | :-----------: | ------------------------------------------------------------ |
|   0   |      | `bool` |     `bool`    | Whether Maple has approved \`balancerPool\` for BPT staking. |

\


### `isValidCalc`

Checks that a Calculator is valid.

```solidity
    function isValidCalc(
        address calc,
        uint8 calcType
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description             |
| :---: | :--------: | :-------: | :-----------: | ----------------------- |
|   0   |   `calc`   | `address` |   `address`   | The Calculator address. |
|   1   | `calcType` |  `uint8`  |    `uint8`    | The Calculator type.    |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `isValidCollateralAsset` _\[state variable]_

```solidity
    function isValidCollateralAsset(
        address collateralAsset
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                        |
| :---: | :---------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `collateralAsset` | `address` |   `address`   | The address of a Collateral Asset. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                           |
| :---: | :--: | :----: | :-----------: | ------------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether \`collateralAsset\` is valid. |

\


### `isValidLiquidityAsset` _\[state variable]_

```solidity
    function isValidLiquidityAsset(
        address liquidityAsset
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                       |
| :---: | :--------------: | :-------: | :-----------: | --------------------------------- |
|   0   | `liquidityAsset` | `address` |   `address`   | The address of a Liquidity Asset. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                          |
| :---: | :--: | :----: | :-----------: | ------------------------------------ |
|   0   |      | `bool` |     `bool`    | Whether \`liquidityAsset\` is valid. |

\


### `isValidLoanFactory` _\[state variable]_

```solidity
    function isValidLoanFactory(
        address loanFactory
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                    |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------ |
|   0   | `loanFactory` | `address` |   `address`   | The address of a Loan Factory. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                       |
| :---: | :--: | :----: | :-----------: | --------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether \`loanFactory\` is valid. |

\


### `isValidPoolDelegate` _\[state variable]_

Prevents unauthorized/unknown addresses from creating Pools.

```solidity
    function isValidPoolDelegate(
        address poolDelegate
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                     |
| :---: | :------------: | :-------: | :-----------: | ------------------------------- |
|   0   | `poolDelegate` | `address` |   `address`   | The address of a Pool Delegate. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                        |
| :---: | :--: | :----: | :-----------: | ---------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether \`poolDelegate\` is valid. |

\


### `isValidPoolFactory` _\[state variable]_

```solidity
    function isValidPoolFactory(
        address poolFactory
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                    |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------ |
|   0   | `poolFactory` | `address` |   `address`   | The address of a Pool Factory. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                       |
| :---: | :--: | :----: | :-----------: | --------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether \`poolFactory\` is valid. |

\


### `isValidSubFactory`

Checks that a \`subFactory\` is valid as it relates to \`superFactory\`.

```solidity
    function isValidSubFactory(
        address superFactory,
        address subFactory,
        uint8 factoryType
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                                                                                                                                                                 |
| :---: | :------------: | :-------: | :-----------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|   0   | `superFactory` | `address` |   `address`   | The core factory (e.g. PoolFactory, LoanFactory).                                                                                                                                           |
|   1   |  `subFactory`  | `address` |   `address`   | The sub factory used by core factory (e.g. LiquidityLockerFactory).                                                                                                                         |
|   2   |  `factoryType` |  `uint8`  |    `uint8`    | The type expected for the subFactory. 0 = COLLATERAL\_LOCKER\_FACTORY, 1 = DEBT\_LOCKER\_FACTORY, 2 = FUNDING\_LOCKER\_FACTORY, 3 = LIQUIDITY\_LOCKER\_FACTORY, 4 = STAKE\_LOCKER\_FACTORY. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `lpCooldownPeriod` _\[state variable]_

The period (in secs) after which LPs are allowed to withdraw their funds from a Pool.

```solidity
    function lpCooldownPeriod()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `lpWithdrawWindow` _\[state variable]_

The window of time (in secs) after \`lpCooldownPeriod\` that an account has to withdraw before their intent to withdraw is invalidated.

```solidity
    function lpWithdrawWindow()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `mapleTreasury` _\[state variable]_

The MapleTreasury is the Treasury where all fees pass through for conversion, prior to distribution.

```solidity
    function mapleTreasury()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `maxSwapSlippage` _\[state variable]_

The maximum amount of slippage for Uniswap transactions.

```solidity
    function maxSwapSlippage()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `minLoanEquity` _\[state variable]_

The minimum amount of LoanFDTs required to trigger liquidations (basis points percentage of totalSupply).

```solidity
    function minLoanEquity()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `mpl` _\[state variable]_

The ERC-2222 Maple Token for the Maple protocol.

```solidity
    function mpl()
        pure
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `oracleFor` _\[state variable]_

```solidity
    function oracleFor(
        address asset
    )
        view
        returns (
            address
        );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                |
| :---: | :-----: | :-------: | :-----------: | -------------------------- |
|   0   | `asset` | `address` |   `address`   | The address of some token. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                      |
| :---: | :--: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |      | `address` |   `address`   | The Chainlink Oracle for the price of \`asset\`. |

\


### `pendingGovernor` _\[state variable]_

The Governor that is declared for governorship transfer. Must be accepted for transfer to take effect.

```solidity
    function pendingGovernor()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `protocolPaused` _\[state variable]_

Whether the functionality of the entire protocol is paused.

```solidity
    function protocolPaused()
        view
        returns (
            bool
        );
```

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `setCalc`

Sets the validity of a calculator contract. Only the Governor can call this function.

```solidity
    function setCalc(
        address calc,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                              |
| :---: | :-----: | :-------: | :-----------: | ---------------------------------------- |
|   0   |  `calc` | `address` |   `address`   | The Calculator address.                  |
|   1   | `valid` |   `bool`  |     `bool`    | The new validity status of a Calculator. |

\


### `setCollateralAsset`

Sets the validity of an asset for collateral. Only the Governor can call this function. It emits a \`CollateralAssetSet\` event.

```solidity
    function setCollateralAsset(
        address asset,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                                    |
| :---: | :-----: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `asset` | `address` |   `address`   | The asset to assign validity to.               |
|   1   | `valid` |   `bool`  |     `bool`    | The new validity status of a Collateral Asset. |

\


### `setDefaultGracePeriod`

Sets the default grace period. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setDefaultGracePeriod(
        uint256 _defaultGracePeriod
    )
        nonpayable;
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                                           |
| :---: | :-------------------: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   | `_defaultGracePeriod` | `uint256` |   `uint256`   | The new number of seconds to set the grace period to. |

\


### `setDefaultUniswapPath`

Sets the path to swap an asset through Uniswap. Only the Governor can call this function. Set to == mid to enable a bilateral swap (single path swap). Set to != mid to enable a triangular swap (multi path swap).

```solidity
    function setDefaultUniswapPath(
        address from,
        address to,
        address mid
    )
        nonpayable;
```

#### Parameters:

| Index |  Name  |    Type   | Internal Type | Description                                |
| :---: | :----: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `from` | `address` |   `address`   | The address of the asset being swapped.    |
|   1   |  `to`  | `address` |   `address`   | The address of the final asset to receive. |
|   2   |  `mid` | `address` |   `address`   | The intermediary asset for swaps, if any.  |

\


### `setFundingPeriod`

Sets the funding period. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setFundingPeriod(
        uint256 _fundingPeriod
    )
        nonpayable;
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                                |
| :---: | :--------------: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   | `_fundingPeriod` | `uint256` |   `uint256`   | The number of seconds to set the drawdown grace period to. |

\


### `setGlobalAdmin`

Sets the Global Admin. Only the Governor can call this function. It emits a \`GlobalAdminSet\` event.

```solidity
    function setGlobalAdmin(
        address newGlobalAdmin
    )
        nonpayable;
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                   |
| :---: | :--------------: | :-------: | :-----------: | ----------------------------- |
|   0   | `newGlobalAdmin` | `address` |   `address`   | The new global admin address. |

\


### `setInvestorFee`

Sets the investor fee (in basis points). Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setInvestorFee(
        uint256 _fee
    )
        nonpayable;
```

#### Parameters:

| Index |  Name  |    Type   | Internal Type | Description                |
| :---: | :----: | :-------: | :-----------: | -------------------------- |
|   0   | `_fee` | `uint256` |   `uint256`   | The fee, e.g., 50 = 0.50%. |

\


### `setLiquidityAsset`

Sets the validity of an asset for liquidity in Pools. Only the Governor can call this function. It emits a \`LiquidityAssetSet\` event.

```solidity
    function setLiquidityAsset(
        address asset,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                                         |
| :---: | :-----: | :-------: | :-----------: | --------------------------------------------------- |
|   0   | `asset` | `address` |   `address`   | The asset to assign validity to.                    |
|   1   | `valid` |   `bool`  |     `bool`    | The new validity status a Liquidity Asset in Pools. |

\


### `setLpCooldownPeriod`

Sets the Liquidity Pool cooldown period. This change will affect the existing cool down period for the LPs that already intended to withdraw. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setLpCooldownPeriod(
        uint256 newCooldownPeriod
    )
        nonpayable;
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                             |
| :---: | :-----------------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `newCooldownPeriod` | `uint256` |   `uint256`   | The new value for the cool down period. |

\


### `setLpWithdrawWindow`

Sets the Liquidity Pool withdraw window. This change will affect the existing window for the LPs that already intended to withdraw. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setLpWithdrawWindow(
        uint256 newLpWithdrawWindow
    )
        nonpayable;
```

#### Parameters:

| Index |          Name         |    Type   | Internal Type | Description                            |
| :---: | :-------------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `newLpWithdrawWindow` | `uint256` |   `uint256`   | The new value for the withdraw window. |

\


### `setMapleTreasury`

Sets the MapleTreasury. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setMapleTreasury(
        address _mapleTreasury
    )
        nonpayable;
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                  |
| :---: | :--------------: | :-------: | :-----------: | ---------------------------- |
|   0   | `_mapleTreasury` | `address` |   `address`   | A new MapleTreasury address. |

\


### `setMaxSwapSlippage`

Sets the allowed Uniswap slippage percentage, in basis points. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setMaxSwapSlippage(
        uint256 newMaxSlippage
    )
        nonpayable;
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                       |
| :---: | :--------------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   | `newMaxSlippage` | `uint256` |   `uint256`   | The new max slippage percentage (in basis points) |

\


### `setMinLoanEquity`

Sets the minimum Loan equity. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setMinLoanEquity(
        uint256 _minLoanEquity
    )
        nonpayable;
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                                                                             |
| :---: | :--------------: | :-------: | :-----------: | --------------------------------------------------------------------------------------- |
|   0   | `_minLoanEquity` | `uint256` |   `uint256`   | The new minimum percentage of Loan equity an account must have to trigger liquidations. |

\


### `setPendingGovernor`

Sets a new Pending Governor. This address can become Governor if they accept. Only the Governor can call this function. It emits a \`PendingGovernorSet\` event.

```solidity
    function setPendingGovernor(
        address _pendingGovernor
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                            |
| :---: | :----------------: | :-------: | :-----------: | -------------------------------------- |
|   0   | `_pendingGovernor` | `address` |   `address`   | The address of a new Pending Governor. |

\


### `setPoolDelegateAllowlist`

Sets the validity of a Pool Delegate (those allowed to create Pools). Only the Governor can call this function. It emits a \`PoolDelegateSet\` event.

```solidity
    function setPoolDelegateAllowlist(
        address poolDelegate,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                 |
| :---: | :------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `poolDelegate` | `address` |   `address`   | The address to manage permissions for.      |
|   1   |     `valid`    |   `bool`  |     `bool`    | The new validity status of a Pool Delegate. |

\


### `setPriceOracle`

Sets a price feed's oracle. Only the Governor can call this function. It emits a \`OracleSet\` event.

```solidity
    function setPriceOracle(
        address asset,
        address oracle
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                       |
| :---: | :------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   |  `asset` | `address` |   `address`   | The asset to update price for.                    |
|   1   | `oracle` | `address` |   `address`   | The new Oracle to use for the price of \`asset\`. |

\


### `setProtocolPause`

Sets the paused/unpaused state of the protocol. Only the Global Admin can call this function. It emits a \`ProtocolPaused\` event.

```solidity
    function setProtocolPause(
        bool pause
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |  Type  | Internal Type | Description                                                                      |
| :---: | :-----: | :----: | :-----------: | -------------------------------------------------------------------------------- |
|   0   | `pause` | `bool` |     `bool`    | A boolean flag to switch externally facing functionality in the protocol on/off. |

\


### `setStakerCooldownPeriod`

Sets the Staker cooldown period. This change will affect the existing cool down period for the Stakers that already intended to unstake. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setStakerCooldownPeriod(
        uint256 newCooldownPeriod
    )
        nonpayable;
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                             |
| :---: | :-----------------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `newCooldownPeriod` | `uint256` |   `uint256`   | The new value for the cool down period. |

\


### `setStakerUnstakeWindow`

Sets the Staker unstake window. This change will affect the existing window for the Stakers that already intended to unstake. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setStakerUnstakeWindow(
        uint256 newUnstakeWindow
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                           |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------- |
|   0   | `newUnstakeWindow` | `uint256` |   `uint256`   | The new value for the unstake window. |

\


### `setSwapOutRequired`

Sets the the minimum Pool cover required to finalize a Pool. Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setSwapOutRequired(
        uint256 amt
    )
        nonpayable;
```

#### Parameters:

| Index |  Name |    Type   | Internal Type | Description                        |
| :---: | :---: | :-------: | :-----------: | ---------------------------------- |
|   0   | `amt` | `uint256` |   `uint256`   | The new minimum swap out required. |

\


### `setTreasuryFee`

Sets the treasury fee (in basis points). Only the Governor can call this function. It emits a \`GlobalsParamSet\` event.

```solidity
    function setTreasuryFee(
        uint256 _fee
    )
        nonpayable;
```

#### Parameters:

| Index |  Name  |    Type   | Internal Type | Description                |
| :---: | :----: | :-------: | :-----------: | -------------------------- |
|   0   | `_fee` | `uint256` |   `uint256`   | The fee, e.g., 50 = 0.50%. |

\


### `setValidBalancerPool`

Sets the validity of a Balancer Pool. Only the Governor can call this function. It emits a \`BalancerPoolSet\` event.

```solidity
    function setValidBalancerPool(
        address balancerPool,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                 |
| :---: | :------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `balancerPool` | `address` |   `address`   | The address of Balancer Pool contract.      |
|   1   |     `valid`    |   `bool`  |     `bool`    | The new validity status of a Balancer Pool. |

\


### `setValidLoanFactory`

Sets the validity of a LoanFactory. Only the Governor can call this function.

```solidity
    function setValidLoanFactory(
        address loanFactory,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                 |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `loanFactory` | `address` |   `address`   | The address of a LoanFactory.               |
|   1   |    `valid`    |   `bool`  |     `bool`    | The new validity status of \`loanFactory\`. |

\


### `setValidPoolFactory`

Sets the validity of a PoolFactory. Only the Governor can call this function.

```solidity
    function setValidPoolFactory(
        address poolFactory,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                                 |
| :---: | :-----------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `poolFactory` | `address` |   `address`   | The address of a PoolFactory.               |
|   1   |    `valid`    |   `bool`  |     `bool`    | The new validity status of \`poolFactory\`. |

\


### `setValidSubFactory`

Sets the validity of \`subFactory\` as it relates to \`superFactory\`. Only the Governor can call this function.

```solidity
    function setValidSubFactory(
        address superFactory,
        address subFactory,
        bool valid
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                                                   |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------------------------------------- |
|   0   | `superFactory` | `address` |   `address`   | The core factory (e.g. PoolFactory, LoanFactory).                             |
|   1   |  `subFactory`  | `address` |   `address`   | The sub factory used by core factory (e.g. LiquidityLockerFactory).           |
|   2   |     `valid`    |   `bool`  |     `bool`    | The new validity status of \`subFactory\` within context of \`superFactory\`. |

\


### `stakerCooldownPeriod` _\[state variable]_

The period (in secs) after which Stakers are allowed to unstake their BPTs from a StakeLocker.

```solidity
    function stakerCooldownPeriod()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `stakerUnstakeWindow` _\[state variable]_

The window of time (in secs) after \`stakerCooldownPeriod\` that an account has to withdraw before their intent to unstake is invalidated.

```solidity
    function stakerUnstakeWindow()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `swapOutRequired` _\[state variable]_

The minimum amount of Pool cover that a Pool Delegate has to provide before they can finalize a Pool.

```solidity
    function swapOutRequired()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `treasuryFee` _\[state variable]_

The portion of drawdown that goes to the MapleTreasury.

```solidity
    function treasuryFee()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `validCalcs` _\[state variable]_

```solidity
    function validCalcs(
        address calc
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |  Name  |    Type   | Internal Type | Description                  |
| :---: | :----: | :-------: | :-----------: | ---------------------------- |
|   0   | `calc` | `address` |   `address`   | The address of a Calculator. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                |
| :---: | :--: | :----: | :-----------: | -------------------------- |
|   0   |      | `bool` |     `bool`    | Whether \`calc\` is valid. |

\


### `validSubFactories` _\[state variable]_

```solidity
    function validSubFactories(
        address superFactory,
        address subFactory
    )
        view
        returns (
            bool
        );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                                         |
| :---: | :------------: | :-------: | :-----------: | ------------------------------------------------------------------- |
|   0   | `superFactory` | `address` |   `address`   | The core factory (e.g. PoolFactory, LoanFactory).                   |
|   1   |  `subFactory`  | `address` |   `address`   | The sub factory used by core factory (e.g. LiquidityLockerFactory). |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                                                        |
| :---: | :--: | :----: | :-----------: | ------------------------------------------------------------------ |
|   0   |      | `bool` |     `bool`    | Whether \`subFactory\` is valid as it relates to \`superFactory\`. |

\


## Events

### `BalancerPoolSet`

Emits an event indicating the validity of a Balancer Pool was set.

```solidity
    event BalancerPoolSet(
        address balancerPool,
        bool valid
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                 |
| :---: | :------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `balancerPool` | `address` |   `address`   | The address of Balancer Pool contract.      |
|   1   |     `valid`    |   `bool`  |     `bool`    | The new validity status of a Balancer Pool. |

\


### `CollateralAssetSet`

Emits an event indicating the validity of a Collateral Asset was set.

```solidity
    event CollateralAssetSet(
        address asset,
        uint256 decimals,
        string symbol,
        bool valid
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                 |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------- |
|   0   |   `asset`  | `address` |   `address`   | The Collateral Asset to assign validity to. |
|   1   | `decimals` | `uint256` |   `uint256`   | The number of decimal places of \`asset\`.  |
|   2   |  `symbol`  |  `string` |    `string`   | The symbol of \`asset\`.                    |
|   3   |   `valid`  |   `bool`  |     `bool`    | The new validity status of \`asset\`.       |

\


### `GlobalAdminSet`

Emits an event indicating the GlobalAdmin was set.

```solidity
    event GlobalAdminSet(
        address newGlobalAdmin
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description                         |
| :---: | :--------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `newGlobalAdmin` | `address` |   `address`   | The address of the new GlobalAdmin. |

\


### `GlobalsAddressSet`

Emits an event indicating that some Governor controlled address was set.

```solidity
    event GlobalsAddressSet(
        bytes32 which,
        address addr
    );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                                 |
| :---: | :-----: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `which` | `bytes32` |   `bytes32`   | The identifier of the address that was set. |
|   1   |  `addr` | `address` |   `address`   | The address that was set.                   |

\


### `GlobalsParamSet`

Emits an event indicating that some Governor controlled parameter was set.

```solidity
    event GlobalsParamSet(
        bytes32 which,
        uint256 value
    );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                                   |
| :---: | :-----: | :-------: | :-----------: | --------------------------------------------- |
|   0   | `which` | `bytes32` |   `bytes32`   | The identifier of the parameter that was set. |
|   1   | `value` | `uint256` |   `uint256`   | The value the parameter was set to.           |

\


### `GovernorAccepted`

Emits an event indicating Governorship was accepted by a new account.

```solidity
    event GovernorAccepted(
        address governor
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                 |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `governor` | `address` |   `address`   | The account that has accepted Governorship. |

\


### `Initialized`

Emits an event indicating the MapleGlobals contract was created.

```solidity
    event Initialized();
```

\


### `LiquidityAssetSet`

Emits an event indicating the validity of a Liquidity Asset was set.

```solidity
    event LiquidityAssetSet(
        address asset,
        uint256 decimals,
        string symbol,
        bool valid
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                                |
| :---: | :--------: | :-------: | :-----------: | ------------------------------------------ |
|   0   |   `asset`  | `address` |   `address`   | The Liquidity Asset to assign validity to. |
|   1   | `decimals` | `uint256` |   `uint256`   | The number of decimal places of \`asset\`. |
|   2   |  `symbol`  |  `string` |    `string`   | The symbol of \`asset\`.                   |
|   3   |   `valid`  |   `bool`  |     `bool`    | The new validity status of \`asset\`.      |

\


### `OracleSet`

Emits an event indicating the Oracle for an asset was set.

```solidity
    event OracleSet(
        address asset,
        address oracle
    );
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                    |
| :---: | :------: | :-------: | :-----------: | ------------------------------ |
|   0   |  `asset` | `address` |   `address`   | The asset to update price for. |
|   1   | `oracle` | `address` |   `address`   | The new Oracle to use.         |

\


### `PendingGovernorSet`

Emits an event indicating a PendingGovernor was set.

```solidity
    event PendingGovernorSet(
        address pendingGovernor
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                              |
| :---: | :---------------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `pendingGovernor` | `address` |   `address`   | The address of the new Pending Governor. |

\


### `PoolDelegateSet`

Emits an event indicating the validity of a Pool Delegate was set.

```solidity
    event PoolDelegateSet(
        address poolDelegate,
        bool valid
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                        |
| :---: | :------------: | :-------: | :-----------: | -------------------------------------------------- |
|   0   | `poolDelegate` | `address` |   `address`   | The address of a Pool Delegate.                    |
|   1   |     `valid`    |   `bool`  |     `bool`    | Whether \`poolDelegate\` is a valid Pool Delegate. |

\


### `ProtocolPaused`

Emits an event indicating the protocol's paused state has been set.

```solidity
    event ProtocolPaused(
        bool pause
    );
```

#### Parameters:

| Index |   Name  |  Type  | Internal Type | Description                      |
| :---: | :-----: | :----: | :-----------: | -------------------------------- |
|   0   | `pause` | `bool` |     `bool`    | Whether the protocol was paused. |

\


### `TransferRestrictionExemptionSet`

This is unused.

```solidity
    event TransferRestrictionExemptionSet(
        address exemptedContract,
        bool valid
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description |
| :---: | :----------------: | :-------: | :-----------: | ----------- |
|   0   | `exemptedContract` | `address` |   `address`   |             |
|   1   |       `valid`      |   `bool`  |     `bool`    |             |

\
