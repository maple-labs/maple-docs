# MapleGlobals

MapleGlobals maintains a central source of parameters and allowlists for the Maple protocol.

<br />

## Constructor


Constructor function. It emits an &#x60;Initialized&#x60; event.

```solidity
    constructor(
        address _governor,
        address _mpl,
        address _globalAdmin
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_governor` | `address` | `address` | Address of Governor. |
| 1 | `_mpl` | `address` | `address` | Address of the ERC-2222 Maple Token for the Maple protocol. |
| 2 | `_globalAdmin` | `address` | `address` | Address the Global Admin. |


<br />


## Functions

### `acceptGovernor`

Accept the Governor position. Only the Pending Governor can call this function. It emits a &#x60;GovernorAccepted&#x60; event.

```solidity
    function acceptGovernor()
        nonpayable;
```



<br />

### `defaultGracePeriod` _[state variable]_

The amount of time a Borrower has to make a missed payment before a default can be triggered.

```solidity
    function defaultGracePeriod()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `defaultUniswapPath` _[state variable]_

Determines the liquidation path of various assets in Loans and the Treasury. The value provided will determine whether or not to perform a bilateral or triangular swap on Uniswap. For example, &#x60;defaultUniswapPath[WBTC][USDC]&#x60; value would indicate what asset to convert WBTC into before conversion to USDC. If &#x60;defaultUniswapPath[WBTC][USDC] &#x3D;&#x3D; USDC&#x60;, then the swap is bilateral and no middle asset is swapped. If &#x60;defaultUniswapPath[WBTC][USDC] &#x3D;&#x3D; WETH&#x60;, then swap WBTC for WETH, then WETH for USDC.

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `tokenA` | `address` | `address` | The address of the asset being swapped. |
| 1 | `tokenB` | `address` | `address` | The address of the final asset to receive. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The intermediary asset for swaps, if any. |


<br />

### `fundingPeriod` _[state variable]_

The amount of time to allow a Borrower to drawdown on their Loan after funding period ends.

```solidity
    function fundingPeriod()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The asset to fetch the price of. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The price of asset in USD. |


<br />

### `getLpCooldownParams`

Returns the &#x60;lpCooldownPeriod&#x60; and &#x60;lpWithdrawWindow&#x60; as a tuple, for convenience.

```solidity
    function getLpCooldownParams()
        view
        returns (
            uint256,
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The value of &#x60;lpCooldownPeriod&#x60;. |
| 1 |  | `uint256` | `uint256` | The value of &#x60;lpWithdrawWindow&#x60;. |


<br />

### `globalAdmin` _[state variable]_

The Global Admin of the whole network. Has the power to switch off/on the functionality of entire protocol.

```solidity
    function globalAdmin()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `governor` _[state variable]_

The Governor responsible for management of global Maple variables.

```solidity
    function governor()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `investorFee` _[state variable]_

The portion of drawdown that goes to the Pool Delegates and individual Lenders.

```solidity
    function investorFee()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `isValidBalancerPool` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `balancerPool` | `address` | `address` | The address of a Balancer Pool. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether Maple has approved &#x60;balancerPool&#x60; for BPT staking. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `calc` | `address` | `address` | The Calculator address. |
| 1 | `calcType` | `uint8` | `uint8` | The Calculator type. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isValidCollateralAsset` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset` | `address` | `address` | The address of a Collateral Asset. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;collateralAsset&#x60; is valid. |


<br />

### `isValidLiquidityAsset` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityAsset` | `address` | `address` | The address of a Liquidity Asset. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;liquidityAsset&#x60; is valid. |


<br />

### `isValidLoanFactory` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanFactory` | `address` | `address` | The address of a Loan Factory. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;loanFactory&#x60; is valid. |


<br />

### `isValidPoolDelegate` _[state variable]_

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate` | `address` | `address` | The address of a Pool Delegate. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;poolDelegate&#x60; is valid. |


<br />

### `isValidPoolFactory` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolFactory` | `address` | `address` | The address of a Pool Factory. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;poolFactory&#x60; is valid. |


<br />

### `isValidSubFactory`

Checks that a &#x60;subFactory&#x60; is valid as it relates to &#x60;superFactory&#x60;.

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `superFactory` | `address` | `address` | The core factory (e.g. PoolFactory, LoanFactory). |
| 1 | `subFactory` | `address` | `address` | The sub factory used by core factory (e.g. LiquidityLockerFactory). |
| 2 | `factoryType` | `uint8` | `uint8` | The type expected for the subFactory.  0 &#x3D; COLLATERAL_LOCKER_FACTORY,  1 &#x3D; DEBT_LOCKER_FACTORY,  2 &#x3D; FUNDING_LOCKER_FACTORY,  3 &#x3D; LIQUIDITY_LOCKER_FACTORY,  4 &#x3D; STAKE_LOCKER_FACTORY.  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `lpCooldownPeriod` _[state variable]_

The period (in secs) after which LPs are allowed to withdraw their funds from a Pool.

```solidity
    function lpCooldownPeriod()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `lpWithdrawWindow` _[state variable]_

The window of time (in secs) after &#x60;lpCooldownPeriod&#x60; that an account has to withdraw before their intent to withdraw is invalidated.

```solidity
    function lpWithdrawWindow()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `mapleTreasury` _[state variable]_

The MapleTreasury is the Treasury where all fees pass through for conversion, prior to distribution.

```solidity
    function mapleTreasury()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `maxSwapSlippage` _[state variable]_

The maximum amount of slippage for Uniswap transactions.

```solidity
    function maxSwapSlippage()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `minLoanEquity` _[state variable]_

The minimum amount of LoanFDTs required to trigger liquidations (basis points percentage of totalSupply).

```solidity
    function minLoanEquity()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `mpl` _[state variable]_

The ERC-2222 Maple Token for the Maple protocol.

```solidity
    function mpl()
        pure
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `oracleFor` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The address of some token. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The Chainlink Oracle for the price of &#x60;asset&#x60;. |


<br />

### `pendingGovernor` _[state variable]_

The Governor that is declared for governorship transfer. Must be accepted for transfer to take effect.

```solidity
    function pendingGovernor()
        view
        returns (
            address
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` |  |


<br />

### `protocolPaused` _[state variable]_

Whether the functionality of the entire protocol is paused.

```solidity
    function protocolPaused()
        view
        returns (
            bool
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `calc` | `address` | `address` | The Calculator address. |
| 1 | `valid` | `bool` | `bool` | The new validity status of a Calculator. |


<br />

### `setCollateralAsset`

Sets the validity of an asset for collateral. Only the Governor can call this function. It emits a &#x60;CollateralAssetSet&#x60; event.

```solidity
    function setCollateralAsset(
        address asset,
        bool valid
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The asset to assign validity to. |
| 1 | `valid` | `bool` | `bool` | The new validity status of a Collateral Asset. |


<br />

### `setDefaultGracePeriod`

Sets the default grace period. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setDefaultGracePeriod(
        uint256 _defaultGracePeriod
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_defaultGracePeriod` | `uint256` | `uint256` | The new number of seconds to set the grace period to. |


<br />

### `setDefaultUniswapPath`

Sets the path to swap an asset through Uniswap. Only the Governor can call this function. Set to &#x3D;&#x3D; mid to enable a bilateral swap (single path swap). Set to !&#x3D; mid to enable a triangular swap (multi path swap).

```solidity
    function setDefaultUniswapPath(
        address from,
        address to,
        address mid
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` | The address of the asset being swapped. |
| 1 | `to` | `address` | `address` | The address of the final asset to receive. |
| 2 | `mid` | `address` | `address` | The intermediary asset for swaps, if any. |


<br />

### `setFundingPeriod`

Sets the funding period. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setFundingPeriod(
        uint256 _fundingPeriod
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_fundingPeriod` | `uint256` | `uint256` | The number of seconds to set the drawdown grace period to. |


<br />

### `setGlobalAdmin`

Sets the Global Admin. Only the Governor can call this function. It emits a &#x60;GlobalAdminSet&#x60; event.

```solidity
    function setGlobalAdmin(
        address newGlobalAdmin
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newGlobalAdmin` | `address` | `address` | The new global admin address. |


<br />

### `setInvestorFee`

Sets the investor fee (in basis points). Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setInvestorFee(
        uint256 _fee
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_fee` | `uint256` | `uint256` | The fee, e.g., 50 &#x3D; 0.50%. |


<br />

### `setLiquidityAsset`

Sets the validity of an asset for liquidity in Pools. Only the Governor can call this function. It emits a &#x60;LiquidityAssetSet&#x60; event.

```solidity
    function setLiquidityAsset(
        address asset,
        bool valid
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The asset to assign validity to. |
| 1 | `valid` | `bool` | `bool` | The new validity status a Liquidity Asset in Pools. |


<br />

### `setLpCooldownPeriod`

Sets the Liquidity Pool cooldown period. This change will affect the existing cool down period for the LPs that already intended to withdraw. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setLpCooldownPeriod(
        uint256 newCooldownPeriod
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newCooldownPeriod` | `uint256` | `uint256` | The new value for the cool down period. |


<br />

### `setLpWithdrawWindow`

Sets the Liquidity Pool withdraw window. This change will affect the existing window for the LPs that already intended to withdraw. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setLpWithdrawWindow(
        uint256 newLpWithdrawWindow
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newLpWithdrawWindow` | `uint256` | `uint256` | The new value for the withdraw window. |


<br />

### `setMapleTreasury`

Sets the MapleTreasury. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setMapleTreasury(
        address _mapleTreasury
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_mapleTreasury` | `address` | `address` | A new MapleTreasury address. |


<br />

### `setMaxSwapSlippage`

Sets the allowed Uniswap slippage percentage, in basis points. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setMaxSwapSlippage(
        uint256 newMaxSlippage
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newMaxSlippage` | `uint256` | `uint256` | The new max slippage percentage (in basis points) |


<br />

### `setMinLoanEquity`

Sets the minimum Loan equity. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setMinLoanEquity(
        uint256 _minLoanEquity
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_minLoanEquity` | `uint256` | `uint256` | The new minimum percentage of Loan equity an account must have to trigger liquidations. |


<br />

### `setPendingGovernor`

Sets a new Pending Governor. This address can become Governor if they accept. Only the Governor can call this function. It emits a &#x60;PendingGovernorSet&#x60; event.

```solidity
    function setPendingGovernor(
        address _pendingGovernor
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_pendingGovernor` | `address` | `address` | The address of a new Pending Governor. |


<br />

### `setPoolDelegateAllowlist`

Sets the validity of a Pool Delegate (those allowed to create Pools). Only the Governor can call this function. It emits a &#x60;PoolDelegateSet&#x60; event.

```solidity
    function setPoolDelegateAllowlist(
        address poolDelegate,
        bool valid
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate` | `address` | `address` | The address to manage permissions for. |
| 1 | `valid` | `bool` | `bool` | The new validity status of a Pool Delegate. |


<br />

### `setPriceOracle`

Sets a price feed&#x27;s oracle. Only the Governor can call this function. It emits a &#x60;OracleSet&#x60; event.

```solidity
    function setPriceOracle(
        address asset,
        address oracle
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The asset to update price for. |
| 1 | `oracle` | `address` | `address` | The new Oracle to use for the price of &#x60;asset&#x60;. |


<br />

### `setProtocolPause`

Sets the paused/unpaused state of the protocol. Only the Global Admin can call this function. It emits a &#x60;ProtocolPaused&#x60; event.

```solidity
    function setProtocolPause(
        bool pause
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pause` | `bool` | `bool` | A boolean flag to switch externally facing functionality in the protocol on/off. |


<br />

### `setStakerCooldownPeriod`

Sets the Staker cooldown period. This change will affect the existing cool down period for the Stakers that already intended to unstake. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setStakerCooldownPeriod(
        uint256 newCooldownPeriod
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newCooldownPeriod` | `uint256` | `uint256` | The new value for the cool down period. |


<br />

### `setStakerUnstakeWindow`

Sets the Staker unstake window. This change will affect the existing window for the Stakers that already intended to unstake. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setStakerUnstakeWindow(
        uint256 newUnstakeWindow
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newUnstakeWindow` | `uint256` | `uint256` | The new value for the unstake window. |


<br />

### `setSwapOutRequired`

Sets the the minimum Pool cover required to finalize a Pool. Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setSwapOutRequired(
        uint256 amt
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | The new minimum swap out required. |


<br />

### `setTreasuryFee`

Sets the treasury fee (in basis points). Only the Governor can call this function. It emits a &#x60;GlobalsParamSet&#x60; event.

```solidity
    function setTreasuryFee(
        uint256 _fee
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_fee` | `uint256` | `uint256` | The fee, e.g., 50 &#x3D; 0.50%. |


<br />

### `setValidBalancerPool`

Sets the validity of a Balancer Pool. Only the Governor can call this function. It emits a &#x60;BalancerPoolSet&#x60; event.

```solidity
    function setValidBalancerPool(
        address balancerPool,
        bool valid
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `balancerPool` | `address` | `address` | The address of Balancer Pool contract. |
| 1 | `valid` | `bool` | `bool` | The new validity status of a Balancer Pool. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loanFactory` | `address` | `address` | The address of a LoanFactory. |
| 1 | `valid` | `bool` | `bool` | The new validity status of &#x60;loanFactory&#x60;. |


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolFactory` | `address` | `address` | The address of a PoolFactory. |
| 1 | `valid` | `bool` | `bool` | The new validity status of &#x60;poolFactory&#x60;. |


<br />

### `setValidSubFactory`

Sets the validity of &#x60;subFactory&#x60; as it relates to &#x60;superFactory&#x60;. Only the Governor can call this function.

```solidity
    function setValidSubFactory(
        address superFactory,
        address subFactory,
        bool valid
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `superFactory` | `address` | `address` | The core factory (e.g. PoolFactory, LoanFactory). |
| 1 | `subFactory` | `address` | `address` | The sub factory used by core factory (e.g. LiquidityLockerFactory). |
| 2 | `valid` | `bool` | `bool` | The new validity status of &#x60;subFactory&#x60; within context of &#x60;superFactory&#x60;. |


<br />

### `stakerCooldownPeriod` _[state variable]_

The period (in secs) after which Stakers are allowed to unstake their BPTs from a StakeLocker.

```solidity
    function stakerCooldownPeriod()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `stakerUnstakeWindow` _[state variable]_

The window of time (in secs) after &#x60;stakerCooldownPeriod&#x60; that an account has to withdraw before their intent to unstake is invalidated.

```solidity
    function stakerUnstakeWindow()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `swapOutRequired` _[state variable]_

The minimum amount of Pool cover that a Pool Delegate has to provide before they can finalize a Pool.

```solidity
    function swapOutRequired()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `treasuryFee` _[state variable]_

The portion of drawdown that goes to the MapleTreasury.

```solidity
    function treasuryFee()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `validCalcs` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `calc` | `address` | `address` | The address of a Calculator. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;calc&#x60; is valid. |


<br />

### `validSubFactories` _[state variable]_



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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `superFactory` | `address` | `address` | The core factory (e.g. PoolFactory, LoanFactory). |
| 1 | `subFactory` | `address` | `address` | The sub factory used by core factory (e.g. LiquidityLockerFactory). |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;subFactory&#x60; is valid as it relates to &#x60;superFactory&#x60;. |


<br />


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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `balancerPool` | `address` | `address` | The address of Balancer Pool contract. |
| 1 | `valid` | `bool` | `bool` | The new validity status of a Balancer Pool. |

<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The Collateral Asset to assign validity to. |
| 1 | `decimals` | `uint256` | `uint256` | The number of decimal places of &#x60;asset&#x60;. |
| 2 | `symbol` | `string` | `string` | The symbol of &#x60;asset&#x60;. |
| 3 | `valid` | `bool` | `bool` | The new validity status of &#x60;asset&#x60;. |

<br />

### `GlobalAdminSet`

Emits an event indicating the GlobalAdmin was set.

```solidity
    event GlobalAdminSet(
        address newGlobalAdmin
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newGlobalAdmin` | `address` | `address` | The address of the new GlobalAdmin. |

<br />

### `GlobalsAddressSet`

Emits an event indicating that some Governor controlled address was set.

```solidity
    event GlobalsAddressSet(
        bytes32 which,
        address addr
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `which` | `bytes32` | `bytes32` | The identifier of the address that was set. |
| 1 | `addr` | `address` | `address` | The address that was set. |

<br />

### `GlobalsParamSet`

Emits an event indicating that some Governor controlled parameter was set.

```solidity
    event GlobalsParamSet(
        bytes32 which,
        uint256 value
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `which` | `bytes32` | `bytes32` | The identifier of the parameter that was set. |
| 1 | `value` | `uint256` | `uint256` | The value the parameter was set to. |

<br />

### `GovernorAccepted`

Emits an event indicating Governorship was accepted by a new account.

```solidity
    event GovernorAccepted(
        address governor
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `governor` | `address` | `address` | The account that has accepted Governorship. |

<br />

### `Initialized`

Emits an event indicating the MapleGlobals contract was created.

```solidity
    event Initialized();
```


<br />

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
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The Liquidity Asset to assign validity to. |
| 1 | `decimals` | `uint256` | `uint256` | The number of decimal places of &#x60;asset&#x60;. |
| 2 | `symbol` | `string` | `string` | The symbol of &#x60;asset&#x60;. |
| 3 | `valid` | `bool` | `bool` | The new validity status of &#x60;asset&#x60;. |

<br />

### `OracleSet`

Emits an event indicating the Oracle for an asset was set.

```solidity
    event OracleSet(
        address asset,
        address oracle
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `asset` | `address` | `address` | The asset to update price for. |
| 1 | `oracle` | `address` | `address` | The new Oracle to use. |

<br />

### `PendingGovernorSet`

Emits an event indicating a PendingGovernor was set.

```solidity
    event PendingGovernorSet(
        address pendingGovernor
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pendingGovernor` | `address` | `address` | The address of the new Pending Governor. |

<br />

### `PoolDelegateSet`

Emits an event indicating the validity of a Pool Delegate was set.

```solidity
    event PoolDelegateSet(
        address poolDelegate,
        bool valid
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate` | `address` | `address` | The address of a Pool Delegate. |
| 1 | `valid` | `bool` | `bool` | Whether &#x60;poolDelegate&#x60; is a valid Pool Delegate. |

<br />

### `ProtocolPaused`

Emits an event indicating the protocol&#x27;s paused state has been set.

```solidity
    event ProtocolPaused(
        bool pause
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pause` | `bool` | `bool` | Whether the protocol was paused. |

<br />

### `TransferRestrictionExemptionSet`

This is unused.

```solidity
    event TransferRestrictionExemptionSet(
        address exemptedContract,
        bool valid
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `exemptedContract` | `address` | `address` |  |
| 1 | `valid` | `bool` | `bool` |  |

<br />

