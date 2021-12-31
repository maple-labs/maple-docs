# PoolLib

PoolLib is a library of utility functions used by Pool.

<br />


## Functions

### `BPTVal` 

Calculates the value of BPT in units of Liquidity Asset. Vulnerable to flash-loan attacks where the attacker can artificially inflate the BPT price by swapping a large amount  of Liquidity Asset into the Pool and swapping back after this function is called. 

```solidity
    function BPTVal(
        address _bPool,
        address liquidityAsset,
        address staker,
        address stakeLocker
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_bPool` | `address` | `address` | The address of Balancer pool. |
| 1 | `liquidityAsset` | `address` | `address` | The asset used by Pool for liquidity to fund Loans. |
| 2 | `staker` | `address` | `address` | The address that deposited BPTs to StakeLocker. |
| 3 | `stakeLocker` | `address` | `address` | The contract that escrows the  BPTs deposited by Staker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The USDC value of Staker BPTs. |


<br />

### `DL_FACTORY` 



```solidity
    function DL_FACTORY()
        view
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` |  |


<br />

### `MAX_UINT256` 



```solidity
    function MAX_UINT256()
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

### `WAD` 



```solidity
    function WAD()
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

### `calculateClaimAndPortions` 

Calculates portions of claim from DebtLocker to be used by Pool &#x60;claim&#x60; function.

```solidity
    function calculateClaimAndPortions(
        uint256[7] claimInfo,
        uint256 delegateFee,
        uint256 stakingFee
    )
        pure
        returns (
            uint256 poolDelegatePortion,
            uint256 stakeLockerPortion,
            uint256 principalClaim,
            uint256 interestClaim
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `claimInfo` | `uint256[7]` | `uint256[7]` | [0] &#x3D;&gt; Total Claimed,  [1] &#x3D;&gt; Interest Claimed,  [2] &#x3D;&gt; Principal Claimed,  [3] &#x3D;&gt; Fee Claimed,  [4] &#x3D;&gt; Excess Returned Claimed,  [5] &#x3D;&gt; Amount Recovered (from Liquidation),  [6] &#x3D;&gt; Default Suffered.  |
| 1 | `delegateFee` | `uint256` | `uint256` | The portion of interest (basis points) that goes to the Pool Delegate. |
| 2 | `stakingFee` | `uint256` | `uint256` | The portion of interest (basis points) that goes to the StakeLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegatePortion` | `uint256` | `uint256` | The total funds to send to the Pool Delegate. |
| 1 | `stakeLockerPortion` | `uint256` | `uint256` |  The total funds to send to the StakeLocker. |
| 2 | `principalClaim` | `uint256` | `uint256` |      The total principal claim. |
| 3 | `interestClaim` | `uint256` | `uint256` |       The total interest claim. |


<br />

### `fromWad` 

Converts from WAD precision to Liquidity Asset precision.

```solidity
    function fromWad(
        uint256 amt,
        uint256 liquidityAssetDecimals
    )
        pure
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | The amount to convert. |
| 1 | `liquidityAssetDecimals` | `uint256` | `uint256` | The Liquidity Asset decimal. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `getInitialStakeRequirements` 

Returns information on the stake requirements.

```solidity
    function getInitialStakeRequirements(
        IMapleGlobals globals,
        address balancerPool,
        address liquidityAsset,
        address poolDelegate,
        address stakeLocker
    )
        view
        returns (
            uint256 swapOutAmountRequired,
            uint256 currentPoolDelegateCover,
            bool enoughStakeForFinalization,
            uint256 poolAmountInRequired,
            uint256 poolAmountPresent
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `globals` | `IMapleGlobals` | `contract IMapleGlobals` | The instance of a MapleGlobals. |
| 1 | `balancerPool` | `address` | `address` | The address of Balancer pool. |
| 2 | `liquidityAsset` | `address` | `address` | The address of Liquidity Asset, to be returned from swap out. |
| 3 | `poolDelegate` | `address` | `address` | The address of Pool Delegate. |
| 4 | `stakeLocker` | `address` | `address` | The address of StakeLocker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `swapOutAmountRequired` | `uint256` | `uint256` |      The minimum amount of Liquidity Asset coverage from staking required (in Liquidity Asset units). |
| 1 | `currentPoolDelegateCover` | `uint256` | `uint256` |   The present amount of Liquidity Asset coverage from Pool Delegate stake (in Liquidity Asset units). |
| 2 | `enoughStakeForFinalization` | `bool` | `bool` | Whether enough stake is present from Pool Delegate for Pool finalization. |
| 3 | `poolAmountInRequired` | `uint256` | `uint256` |       The BPTs required for minimum Liquidity Asset coverage. |
| 4 | `poolAmountPresent` | `uint256` | `uint256` |          The current staked BPTs. |


<br />

### `getPoolSharesRequired` 

Calculates BPTs required if burning BPTs for liquidityAsset, given supplied tokenAmountOutRequired. Vulnerable to flash-loan attacks where the attacker can artificially inflate the BPT price by swapping a large amount  of liquidityAsset into the pool and swapping back after this function is called.

```solidity
    function getPoolSharesRequired(
        address _bPool,
        address liquidityAsset,
        address staker,
        address stakeLocker,
        uint256 liquidityAssetAmountRequired
    )
        view
        returns (
            uint256 poolAmountInRequired,
            uint256 stakerBalance
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_bPool` | `address` | `address` | The Balancer pool that issues the BPTs. |
| 1 | `liquidityAsset` | `address` | `address` | The swap out asset (e.g. USDC) to receive when burning BPTs. |
| 2 | `staker` | `address` | `address` | The address that deposited BPTs to stakeLocker. |
| 3 | `stakeLocker` | `address` | `address` | The contract that escrows BPTs deposited by staker. |
| 4 | `liquidityAssetAmountRequired` | `uint256` | `uint256` | The amount of liquidityAsset required to recover. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolAmountInRequired` | `uint256` | `uint256` |         The required poolAmountIn. |
| 1 | `stakerBalance` | `uint256` | `uint256` |                The poolAmountIn currently staked. |


<br />

### `getSwapOutValue` 

Calculates Liquidity Asset swap out value of staker BPT balance escrowed in StakeLocker.

```solidity
    function getSwapOutValue(
        address _bPool,
        address liquidityAsset,
        address staker,
        address stakeLocker
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_bPool` | `address` | `address` | The Balancer pool that issues the BPTs. |
| 1 | `liquidityAsset` | `address` | `address` | The Swap out asset (e.g. USDC) to receive when burning BPTs. |
| 2 | `staker` | `address` | `address` | The address that deposited BPTs to StakeLocker. |
| 3 | `stakeLocker` | `address` | `address` | The contract that escrows BPTs deposited by Staker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | liquidityAsset The swap out value of staker BPTs. |


<br />

### `getSwapOutValueLocker` 

Calculates Liquidity Asset swap out value of entire BPT balance escrowed in StakeLocker.

```solidity
    function getSwapOutValueLocker(
        address _bPool,
        address liquidityAsset,
        address stakeLocker
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_bPool` | `address` | `address` | The Balancer pool that issues the BPTs. |
| 1 | `liquidityAsset` | `address` | `address` | The swap out asset (e.g. USDC) to receive when burning BPTs. |
| 2 | `stakeLocker` | `address` | `address` | The contract that escrows BPTs deposited by Staker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | liquidityAsset The swap out value of StakeLocker BPTs. |


<br />

### `increaseCustodyAllowanceChecks` 

Performs all necessary checks for an &#x60;increaseCustodyAllowance&#x60; call.

```solidity
    function increaseCustodyAllowanceChecks(
        address custodian,
        uint256 amount,
        uint256 newTotalAllowance,
        uint256 fdtBal
    )
        pure;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `custodian` | `address` | `address` | The custodian where the funds will be locked to. |
| 1 | `amount` | `uint256` | `uint256` | The additional amount to custody. |
| 2 | `newTotalAllowance` | `uint256` | `uint256` | The new total amount in custody, for some account. |
| 3 | `fdtBal` | `uint256` | `uint256` | The the total FDT balance of some account. |


<br />

### `poolSanityChecks` 

Conducts sanity checks for Pools in the constructor.

```solidity
    function poolSanityChecks(
        IMapleGlobals globals,
        address liquidityAsset,
        address stakeAsset,
        uint256 stakingFee,
        uint256 delegateFee
    )
        view;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `globals` | `IMapleGlobals` | `contract IMapleGlobals` | The instance of a MapleGlobals. |
| 1 | `liquidityAsset` | `address` | `address` | The asset used by Pool for liquidity to fund loans. |
| 2 | `stakeAsset` | `address` | `address` | The asset escrowed in StakeLocker. |
| 3 | `stakingFee` | `uint256` | `uint256` | The fee that the Stakers earn on interest, in basis points. |
| 4 | `delegateFee` | `uint256` | `uint256` | The fee that the Pool Delegate earns on interest, in basis points. |


<br />

### `transferByCustodianChecks` 

Performs all necessary checks for a &#x60;transferByCustodian&#x60; call. From and to must always be equal. 

```solidity
    function transferByCustodianChecks(
        address from,
        address to,
        uint256 amount
    )
        pure;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` | The address of the source of funds. |
| 1 | `to` | `address` | `address` | The address of the destination of funds. |
| 2 | `amount` | `uint256` | `uint256` | The amount of funds transfer. |


<br />

### `validateDeactivation` 

Checks that the deactivation is allowed.

```solidity
    function validateDeactivation(
        IMapleGlobals globals,
        uint256 principalOut,
        address liquidityAsset
    )
        view;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `globals` | `IMapleGlobals` | `contract IMapleGlobals` | The instance of a MapleGlobals. |
| 1 | `principalOut` | `uint256` | `uint256` | The amount of funds that are already funded to Loans. |
| 2 | `liquidityAsset` | `address` | `address` | The Liquidity Asset of the Pool. |


<br />


## Events

### `DepositDateUpdated`


```solidity
    event DepositDateUpdated(
        address liquidityProvider,
        uint256 depositDate
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` |  |
| 1 | `depositDate` | `uint256` | `uint256` |  |

<br />

### `LoanFunded`


```solidity
    event LoanFunded(
        address loan,
        address debtLocker,
        uint256 amountFunded
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` |  |
| 1 | `debtLocker` | `address` | `address` |  |
| 2 | `amountFunded` | `uint256` | `uint256` |  |

<br />

