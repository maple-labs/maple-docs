# Pool

Pool maintains all accounting and functionality related to Pools.

<br />

## Constructor


Constructor for a Pool. It emits a &#x60;PoolStateChanged&#x60; event.

```solidity
    constructor(
        address _poolDelegate,
        address _liquidityAsset,
        address _stakeAsset,
        address _slFactory,
        address _llFactory,
        uint256 _stakingFee,
        uint256 _delegateFee,
        uint256 _liquidityCap,
        string name,
        string symbol
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_poolDelegate` | `address` | `address` | Address that has manager privileges of the Pool. |
| 1 | `_liquidityAsset` | `address` | `address` | Asset used to fund the Pool, It gets escrowed in LiquidityLocker. |
| 2 | `_stakeAsset` | `address` | `address` | Asset escrowed in StakeLocker. |
| 3 | `_slFactory` | `address` | `address` | Factory used to instantiate the StakeLocker. |
| 4 | `_llFactory` | `address` | `address` | Factory used to instantiate the LiquidityLocker. |
| 5 | `_stakingFee` | `uint256` | `uint256` | Fee that Stakers earn on interest, in basis points. |
| 6 | `_delegateFee` | `uint256` | `uint256` | Fee that the Pool Delegate earns on interest, in basis points. |
| 7 | `_liquidityCap` | `uint256` | `uint256` | Max amount of Liquidity Asset accepted by the Pool. |
| 8 | `name` | `string` | `string` | Name of Pool token. |
| 9 | `symbol` | `string` | `string` | Symbol of Pool token. |


<br />


## Functions

### `BPTVal`

Calculates the value of BPT in units of Liquidity Asset.

```solidity
    function BPTVal(
        address _bPool,
        address _liquidityAsset,
        address _staker,
        address _stakeLocker
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
| 1 | `_liquidityAsset` | `address` | `address` | The asset used by Pool for liquidity to fund Loans. |
| 2 | `_staker` | `address` | `address` | The address that deposited BPTs to StakeLocker. |
| 3 | `_stakeLocker` | `address` | `address` | Escrows BPTs deposited by Staker. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | USDC value of staker BPTs. |


<br />

### `DL_FACTORY` _[state variable]_

The factory type of &#x60;DebtLockerFactory&#x60;.

```solidity
    function DL_FACTORY()
        pure
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` |  |


<br />

### `accumulativeFundsOf`

Returns the amount of funds that an account has earned in total. accumulativeFundsOf(_owner) &#x3D; withdrawableFundsOf(_owner) + withdrawnFundsOf(_owner)  &#x3D; (pointsPerShare * balanceOf(_owner) + pointsCorrection[_owner]) / pointsMultiplier

```solidity
    function accumulativeFundsOf(
        address _owner
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of funds that &#x60;_owner&#x60; has earned in total. |


<br />

### `accumulativeLossesOf`

Returns the amount of losses that an account has earned in total. accumulativeLossesOf(_owner) &#x3D; recognizableLossesOf(_owner) + recognizedLossesOf(_owner)  &#x3D; (lossesPerShare * balanceOf(_owner) + lossesCorrection[_owner]) / pointsMultiplier

```solidity
    function accumulativeLossesOf(
        address _owner
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of losses that &#x60;_owner&#x60; has earned in total. |


<br />

### `allowance`

Returns the remaining number of tokens that &#x60;spender&#x60; will be allowed to spend on behalf of &#x60;owner&#x60; through {transferFrom}. This is zero by default. This value changes when {approve} or {transferFrom} are called.

```solidity
    function allowance(
        address owner,
        address spender
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` |  |
| 1 | `spender` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `allowedLiquidityProviders` _[state variable]_



```solidity
    function allowedLiquidityProviders(
        address liquidityProvider
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of a LiquidityProvider. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;liquidityProvider&#x60; has early access to the Pool. |


<br />

### `approve`

Sets &#x60;amount&#x60; as the allowance of &#x60;spender&#x60; over the caller&#x27;s tokens. Returns a boolean value indicating whether the operation succeeded. IMPORTANT: Beware that changing an allowance with this method brings the risk that someone may use both the old and the new allowance by unfortunate transaction ordering. One possible solution to mitigate this race condition is to first reduce the spender&#x27;s allowance to 0 and set the desired value afterwards: https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729 Emits an {Approval} event. Requirements: - &#x60;spender&#x60; cannot be the zero address.

```solidity
    function approve(
        address spender,
        uint256 amount
    )
        nonpayable
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `amount` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `balanceOf`

Returns the amount of tokens owned by &#x60;account&#x60;.

```solidity
    function balanceOf(
        address account
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `cancelWithdraw`

Cancels an initiated withdrawal by resetting the account&#x27;s withdraw cooldown. It emits a &#x60;Cooldown&#x60; event.

```solidity
    function cancelWithdraw()
        nonpayable;
```



<br />

### `claim`

Claims available funds for the Loan through a specified DebtLockerFactory. Only the Pool Delegate or a Pool Admin can call this function. It emits two &#x60;BalanceUpdated&#x60; events. It emits a &#x60;Claim&#x60; event.

```solidity
    function claim(
        address loan,
        address dlFactory
    )
        nonpayable
        returns (
            uint256[7] claimInfo
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The address of the loan to claim from. |
| 1 | `dlFactory` | `address` | `address` | The address of the DebtLockerFactory. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `claimInfo` | `uint256[7]` | `uint256[7]` | The claim details.  [0] &#x3D;&gt; Total amount claimed,  [1] &#x3D;&gt; Interest portion claimed,  [2] &#x3D;&gt; Principal portion claimed,  [3] &#x3D;&gt; Fee portion claimed,  [4] &#x3D;&gt; Excess portion claimed,  [5] &#x3D;&gt; Recovered portion claimed (from liquidations),  [6] &#x3D;&gt; Default suffered.  |


<br />

### `custodyAllowance` _[state variable]_



```solidity
    function custodyAllowance(
        address account,
        address custodian
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address of an account. |
| 1 | `custodian` | `address` | `address` | The address of a custodian. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of PoolFDTs of &#x60;account&#x60; that are &quot;locked&quot; at &#x60;custodian&#x60;. |


<br />

### `deactivate`

Triggers deactivation, permanently shutting down the Pool. Must have less than 100 USD worth of Liquidity Asset &#x60;principalOut&#x60;. Only the Pool Delegate can call this function. It emits a &#x60;PoolStateChanged&#x60; event.

```solidity
    function deactivate()
        nonpayable;
```



<br />

### `debtLockers` _[state variable]_



```solidity
    function debtLockers(
        address loan,
        address debtLockerFactory
    )
        view
        returns (
            address
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The address of a Loan. |
| 1 | `debtLockerFactory` | `address` | `address` | The address of a DebtLockerFactory. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | The address of the DebtLocker corresponding to &#x60;loan&#x60; and &#x60;debtLockerFactory&#x60;. |


<br />

### `delegateFee` _[state variable]_

The fee the Pool Delegate earns (in basis points).

```solidity
    function delegateFee()
        pure
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `deposit`

Handles Liquidity Providers depositing of Liquidity Asset into the LiquidityLocker, minting PoolFDTs. It emits a &#x60;DepositDateUpdated&#x60; event. It emits a &#x60;BalanceUpdated&#x60; event. It emits a &#x60;Cooldown&#x60; event.

```solidity
    function deposit(
        uint256 amt
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | The amount of Liquidity Asset to deposit. |


<br />

### `depositDate` _[state variable]_

Used for withdraw penalty calculation.

```solidity
    function depositDate(
        address account
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address of an account. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The unix timestamp of the weighted average deposit date of &#x60;account&#x60;. |


<br />

### `finalize`

Finalizes the Pool, enabling deposits. Checks the amount the Pool Delegate deposited to the StakeLocker. Only the Pool Delegate can call this function. It emits a &#x60;PoolStateChanged&#x60; event.

```solidity
    function finalize()
        nonpayable;
```



<br />

### `fundLoan`

Funds a Loan for an amount, utilizing the supplied DebtLockerFactory for DebtLockers. Only the Pool Delegate can call this function. It emits a &#x60;LoanFunded&#x60; event. It emits a &#x60;BalanceUpdated&#x60; event.

```solidity
    function fundLoan(
        address loan,
        address dlFactory,
        uint256 amt
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The address of the Loan to fund. |
| 1 | `dlFactory` | `address` | `address` | The address of the DebtLockerFactory to utilize. |
| 2 | `amt` | `uint256` | `uint256` | The amount to fund the Loan. |


<br />

### `getInitialStakeRequirements`

Returns information on the stake requirements.

```solidity
    function getInitialStakeRequirements()
        view
        returns (
            uint256,
            uint256,
            bool,
            uint256,
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The min amount of Liquidity Asset coverage from staking required. |
| 1 |  | `uint256` | `uint256` | The present amount of Liquidity Asset coverage from the Pool Delegate stake. |
| 2 |  | `bool` | `bool` | Whether enough stake is present from the Pool Delegate for finalization. |
| 3 |  | `uint256` | `uint256` | The staked BPTs required for minimum Liquidity Asset coverage. |
| 4 |  | `uint256` | `uint256` | The current staked BPTs. |


<br />

### `getPoolSharesRequired`

Calculates BPTs required if burning BPTs for the Liquidity Asset, given supplied &#x60;tokenAmountOutRequired&#x60;.

```solidity
    function getPoolSharesRequired(
        address _bPool,
        address _liquidityAsset,
        address _staker,
        address _stakeLocker,
        uint256 _liquidityAssetAmountRequired
    )
        view
        returns (
            uint256,
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_bPool` | `address` | `address` | The Balancer pool that issues the BPTs. |
| 1 | `_liquidityAsset` | `address` | `address` | Swap out asset (e.g. USDC) to receive when burning BPTs. |
| 2 | `_staker` | `address` | `address` | The address that deposited BPTs to StakeLocker. |
| 3 | `_stakeLocker` | `address` | `address` | Escrows BPTs deposited by Staker. |
| 4 | `_liquidityAssetAmountRequired` | `uint256` | `uint256` | The amount of Liquidity Asset required to recover. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The &#x60;poolAmountIn&#x60; required. |
| 1 |  | `uint256` | `uint256` | The &#x60;poolAmountIn&#x60; currently staked. |


<br />

### `increaseCustodyAllowance`

Increases the custody allowance for a given Custodian corresponding to the calling account (&#x60;msg.sender&#x60;). It emits a &#x60;CustodyAllowanceChanged&#x60; event. It emits a &#x60;TotalCustodyAllowanceUpdated&#x60; event.

```solidity
    function increaseCustodyAllowance(
        address custodian,
        uint256 amount
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `custodian` | `address` | `address` | The address which will act as Custodian of a given amount for an account. |
| 1 | `amount` | `uint256` | `uint256` | The number of additional FDTs to be custodied by the Custodian. |


<br />

### `intendToWithdraw`

Activates the cooldown period to withdraw. It can&#x27;t be called if the account is not providing liquidity. It emits a &#x60;Cooldown&#x60; event.

```solidity
    function intendToWithdraw()
        nonpayable;
```



<br />

### `interestBalance`

The amount of earned interest present and accounted for in this contract.

```solidity
    function interestBalance()
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

### `interestSum`

The sum of all withdrawable interest.

```solidity
    function interestSum()
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

### `isDepositAllowed`

Checks that the given deposit amount is acceptable based on current liquidityCap.

```solidity
    function isDepositAllowed(
        uint256 depositAmt
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `depositAmt` | `uint256` | `uint256` | The amount of tokens (i.e liquidityAsset type) the account is trying to deposit. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `isPoolFinalized`

Checks that the Pool state is &#x60;Finalized&#x60;.

```solidity
    function isPoolFinalized()
        view
        returns (
            bool
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether the Pool is in a Finalized state. |


<br />

### `liquidityAsset` _[state variable]_

The asset deposited by Lenders into the LiquidityLocker, for funding Loans.

```solidity
    function liquidityAsset()
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

### `liquidityCap` _[state variable]_

The amount of liquidity tokens accepted by the Pool.

```solidity
    function liquidityCap()
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

### `liquidityLocker` _[state variable]_

The address of the asset deposited by Stakers into the StakeLocker (BPTs), for liquidation during default events.

```solidity
    function liquidityLocker()
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

### `lockupPeriod` _[state variable]_

The period of time from an account&#x27;s deposit date during which they cannot withdraw any funds.

```solidity
    function lockupPeriod()
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

### `lossesBalance`

The amount of losses present and accounted for in this contract.

```solidity
    function lossesBalance()
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

### `openToPublic` _[state variable]_

Whether the Pool is open to the public for LP deposits.

```solidity
    function openToPublic()
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

### `poolAdmins` _[state variable]_



```solidity
    function poolAdmins(
        address poolAdmin
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolAdmin` | `address` | `address` | The address of a PoolAdmin. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;poolAdmin&#x60; has permission to do certain operations in case of disaster management. |


<br />

### `poolDelegate` _[state variable]_

The Pool Delegate address, maintains full authority over the Pool.

```solidity
    function poolDelegate()
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

### `poolLosses`

The sum of all unrecognized losses.

```solidity
    function poolLosses()
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

### `poolState` _[state variable]_

The state of the Pool.

```solidity
    function poolState()
        view
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `enum IPool.State` |  |


<br />

### `principalOut` _[state variable]_

The sum of all outstanding principal on Loans.

```solidity
    function principalOut()
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

### `reclaimERC20`

Transfers any locked funds to the Governor. Only the Governor can call this function.

```solidity
    function reclaimERC20(
        address token
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `token` | `address` | `address` | The address of the token to be reclaimed. |


<br />

### `recognizableLossesOf`

Returns the amount of losses that an account can withdraw.

```solidity
    function recognizableLossesOf(
        address _owner
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of losses that &#x60;_owner&#x60; can withdraw. |


<br />

### `recognizedLossesOf`

Returns the amount of losses that an account has recognized.

```solidity
    function recognizedLossesOf(
        address _owner
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of losses that &#x60;_owner&#x60; has recognized. |


<br />

### `setAllowList`

Sets the account status in the Pool&#x27;s allowlist. Only the Pool Delegate can call this function. It emits an &#x60;LPStatusChanged&#x60; event.

```solidity
    function setAllowList(
        address account,
        bool status
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address to set status for. |
| 1 | `status` | `bool` | `bool` | The status of an account in the allowlist. |


<br />

### `setLiquidityCap`

Sets the liquidity cap. Only the Pool Delegate or a Pool Admin can call this function. It emits a &#x60;LiquidityCapSet&#x60; event.

```solidity
    function setLiquidityCap(
        uint256 newLiquidityCap
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newLiquidityCap` | `uint256` | `uint256` | The new liquidity cap value. |


<br />

### `setLockupPeriod`

Sets the lockup period. Only the Pool Delegate can call this function. It emits a &#x60;LockupPeriodSet&#x60; event.

```solidity
    function setLockupPeriod(
        uint256 newLockupPeriod
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newLockupPeriod` | `uint256` | `uint256` | The new lockup period used to restrict the withdrawals. |


<br />

### `setOpenToPublic`

Sets whether the Pool is open to the public. Only the Pool Delegate can call this function. It emits a &#x60;PoolOpenedToPublic&#x60; event.

```solidity
    function setOpenToPublic(
        bool open
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `open` | `bool` | `bool` | Whether the Pool is open to liquidity from the public. |


<br />

### `setPoolAdmin`

Sets a Pool Admin. Only the Pool Delegate can call this function. It emits a &#x60;PoolAdminSet&#x60; event.

```solidity
    function setPoolAdmin(
        address poolAdmin,
        bool allowed
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolAdmin` | `address` | `address` | An address being allowed or disallowed as a Pool Admin. |
| 1 | `allowed` | `bool` | `bool` | Whether &#x60;poolAdmin&#x60; is an admin of the Pool. |


<br />

### `setStakingFee`

Sets the staking fee. Only the Pool Delegate can call this function. It emits a &#x60;StakingFeeSet&#x60; event.

```solidity
    function setStakingFee(
        uint256 newStakingFee
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newStakingFee` | `uint256` | `uint256` | The new staking fee. |


<br />

### `stakeAsset` _[state variable]_

The address of the asset deposited by Stakers into the StakeLocker (BPTs), for liquidation during default events.

```solidity
    function stakeAsset()
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

### `stakeLocker` _[state variable]_

The address of the StakeLocker, escrowing &#x60;stakeAsset&#x60;.

```solidity
    function stakeLocker()
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

### `stakingFee` _[state variable]_

The fee Stakers earn (in basis points).

```solidity
    function stakingFee()
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

### `superFactory` _[state variable]_

The factory that deployed this Loan.

```solidity
    function superFactory()
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

### `totalCustodyAllowance` _[state variable]_



```solidity
    function totalCustodyAllowance(
        address account
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address of an account. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The total amount of PoolFDTs that are &quot;locked&quot; for &#x60;account&#x60;. Cannot be greater than the account&#x27;s balance. |


<br />

### `totalSupply`

Returns the amount of tokens in existence.

```solidity
    function totalSupply()
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

### `transfer`

Moves &#x60;amount&#x60; tokens from the caller&#x27;s account to &#x60;recipient&#x60;. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event. Requirements: - &#x60;recipient&#x60; cannot be the zero address. - the caller must have a balance of at least &#x60;amount&#x60;.

```solidity
    function transfer(
        address recipient,
        uint256 amount
    )
        nonpayable
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `recipient` | `address` | `address` |  |
| 1 | `amount` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `transferByCustodian`

Transfers custodied PoolFDTs back to the account. &#x60;from&#x60; and &#x60;to&#x60; should always be equal in this implementation. This means that the Custodian can only decrease their own allowance and unlock funds for the original owner. It emits a &#x60;CustodyTransfer&#x60; event. It emits a &#x60;CustodyAllowanceChanged&#x60; event. It emits a &#x60;TotalCustodyAllowanceUpdated&#x60; event.

```solidity
    function transferByCustodian(
        address from,
        address to,
        uint256 amount
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` | The address which holds the PoolFDTs. |
| 1 | `to` | `address` | `address` | The address which will be the new owner of the amount of PoolFDTs. |
| 2 | `amount` | `uint256` | `uint256` | The amount of PoolFDTs transferred. |


<br />

### `transferFrom`

Moves &#x60;amount&#x60; tokens from &#x60;sender&#x60; to &#x60;recipient&#x60; using the allowance mechanism. &#x60;amount&#x60; is then deducted from the caller&#x27;s allowance. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event. Emits an {Approval} event indicating the updated allowance. This is not required by the EIP. See the note at the beginning of {ERC20}. Requirements: - &#x60;sender&#x60; and &#x60;recipient&#x60; cannot be the zero address. - &#x60;sender&#x60; must have a balance of at least &#x60;amount&#x60;. - the caller must have allowance for &#x60;&#x60;sender&#x60;&#x60;&#x27;s tokens of at least &#x60;amount&#x60;.

```solidity
    function transferFrom(
        address sender,
        address recipient,
        uint256 amount
    )
        nonpayable
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `sender` | `address` | `address` |  |
| 1 | `recipient` | `address` | `address` |  |
| 2 | `amount` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `triggerDefault`

Liquidates a Loan. The Pool Delegate could liquidate the Loan only when the Loan completes its grace period. The Pool Delegate can claim its proportion of recovered funds from the liquidation using the &#x60;claim()&#x60; function. Only the Pool Delegate can call this function.

```solidity
    function triggerDefault(
        address loan,
        address dlFactory
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The address of the Loan to liquidate. |
| 1 | `dlFactory` | `address` | `address` | The address of the DebtLockerFactory that is used to pull corresponding DebtLocker. |


<br />

### `updateFundsReceived`

Registers a payment of funds in tokens. May be called directly after a deposit is made. Calls _updateFundsTokenBalance(), whereby the contract computes the delta of the new and previous  &#x60;fundsToken&#x60; balance and increments the total received funds (cumulative), by delta, by calling _distributeFunds().

```solidity
    function updateFundsReceived()
        nonpayable;
```



<br />

### `updateLossesReceived`

Registers a loss. May be called directly after a shortfall after BPT burning occurs. Calls _updateLossesTokenBalance(), whereby the contract computes the delta of the new and previous  losses balance and increments the total losses (cumulative), by delta, by calling _distributeLosses().

```solidity
    function updateLossesReceived()
        nonpayable;
```



<br />

### `withdraw`

Handles Liquidity Providers withdrawing of Liquidity Asset from the LiquidityLocker, burning PoolFDTs. It emits two &#x60;BalanceUpdated&#x60; event.

```solidity
    function withdraw(
        uint256 amt
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | The amount of Liquidity Asset to withdraw. |


<br />

### `withdrawCooldown` _[state variable]_



```solidity
    function withdrawCooldown(
        address liquidityProvider
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of a LiquidityProvider. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The unix timestamp of when individual LPs have notified of their intent to withdraw. |


<br />

### `withdrawFunds`

Withdraws all claimable interest from the LiquidityLocker for an account using &#x60;interestSum&#x60; accounting. It emits a &#x60;BalanceUpdated&#x60; event.

```solidity
    function withdrawFunds()
        nonpayable;
```



<br />

### `withdrawableFundsOf`

Returns the amount of funds that an account can withdraw.

```solidity
    function withdrawableFundsOf(
        address _owner
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of some FDT holder. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount funds that &#x60;_owner&#x60; can withdraw. |


<br />

### `withdrawnFundsOf`

Returns the amount of funds that an account has withdrawn.

```solidity
    function withdrawnFundsOf(
        address _owner
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of funds that &#x60;_owner&#x60; has withdrawn. |


<br />

### `decimals`

Returns the number of decimals used to get its user representation. For example, if &#x60;decimals&#x60; equals &#x60;2&#x60;, a balance of &#x60;505&#x60; tokens should be displayed to a user as &#x60;5,05&#x60; (&#x60;505 / 10 ** 2&#x60;). Tokens usually opt for a value of 18, imitating the relationship between Ether and Wei. This is the value {ERC20} uses, unless {_setupDecimals} is called. NOTE: This information is only used for _display_ purposes: it in no way affects any of the arithmetic of the contract, including {IERC20-balanceOf} and {IERC20-transfer}.

```solidity
    function decimals()
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

### `decreaseAllowance`

Atomically decreases the allowance granted to &#x60;spender&#x60; by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - &#x60;spender&#x60; cannot be the zero address. - &#x60;spender&#x60; must have allowance for the caller of at least &#x60;subtractedValue&#x60;.

```solidity
    function decreaseAllowance(
        address spender,
        uint256 subtractedValue
    )
        nonpayable
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `subtractedValue` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `increaseAllowance`

Atomically increases the allowance granted to &#x60;spender&#x60; by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - &#x60;spender&#x60; cannot be the zero address.

```solidity
    function increaseAllowance(
        address spender,
        uint256 addedValue
    )
        nonpayable
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `addedValue` | `uint256` | `uint256` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `name`

Returns the name of the token.

```solidity
    function name()
        view
        returns (
            string
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` |  |


<br />

### `symbol`

Returns the symbol of the token, usually a shorter version of the name.

```solidity
    function symbol()
        view
        returns (
            string
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` |  |


<br />


## Events

### `Approval`

Emitted when the allowance of a &#x60;spender&#x60; for an &#x60;owner&#x60; is set by a call to {approve}. &#x60;value&#x60; is the new allowance.

```solidity
    event Approval(
        address owner,
        address spender,
        uint256 value
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` |  |
| 1 | `spender` | `address` | `address` |  |
| 2 | `value` | `uint256` | `uint256` |  |

<br />

### `BalanceUpdated`

Emits an event indicating some Balance was updated.

```solidity
    event BalanceUpdated(
        address liquidityProvider,
        address token,
        uint256 balance
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of a Liquidity Provider. |
| 1 | `token` | `address` | `address` | The address of the token for which the balance of &#x60;liquidityProvider&#x60; changed. |
| 2 | `balance` | `uint256` | `uint256` | The new balance for &#x60;liquidityProvider&#x60;. |

<br />

### `Claim`

Emits an event indicating a Loan was claimed.

```solidity
    event Claim(
        address loan,
        uint256 interest,
        uint256 principal,
        uint256 fee,
        uint256 stakeLockerPortion,
        uint256 poolDelegatePortion
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The Loan. |
| 1 | `interest` | `uint256` | `uint256` | The interest. |
| 2 | `principal` | `uint256` | `uint256` | The principal. |
| 3 | `fee` | `uint256` | `uint256` | The total fee. |
| 4 | `stakeLockerPortion` | `uint256` | `uint256` | The portion of the fee for Stakers. |
| 5 | `poolDelegatePortion` | `uint256` | `uint256` | The portion of the fee for the Pool Delegate. |

<br />

### `Cooldown`

Emits an event indicating a that the withdrawal cooldown for a Liquidity Provider of the Pool has updated.

```solidity
    event Cooldown(
        address liquidityProvider,
        uint256 cooldown
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of a Liquidity Provider. |
| 1 | `cooldown` | `uint256` | `uint256` | The new withdrawal cooldown. |

<br />

### `CustodyAllowanceChanged`

Emits an event indicating a change in the total amount in custodianship for an account.

```solidity
    event CustodyAllowanceChanged(
        address liquidityProvider,
        address custodian,
        uint256 oldAllowance,
        uint256 newAllowance
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of amount who&#x27;s funds are being custodied. |
| 1 | `custodian` | `address` | `address` | The address of the custodian. |
| 2 | `oldAllowance` | `uint256` | `uint256` | The original total amount in custodian by &#x60;custodian&#x60; for &#x60;liquidityProvider&#x60;. |
| 3 | `newAllowance` | `uint256` | `uint256` | The updated total amount in custodian by &#x60;custodian&#x60; for &#x60;liquidityProvider&#x60;. |

<br />

### `CustodyTransfer`

Emits an event indicating a transfer of funds was performed by a custodian.

```solidity
    event CustodyTransfer(
        address custodian,
        address from,
        address to,
        uint256 amount
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `custodian` | `address` | `address` | The address of the custodian. |
| 1 | `from` | `address` | `address` | The source of funds that were custodied. |
| 2 | `to` | `address` | `address` | The destination of funds. |
| 3 | `amount` | `uint256` | `uint256` | The amount of custodied tokens transferred. |

<br />

### `DefaultSuffered`

Emits an event indicating the one of the Pool&#x27;s Loans defaulted.

```solidity
    event DefaultSuffered(
        address loan,
        uint256 defaultSuffered,
        uint256 bptsBurned,
        uint256 bptsReturned,
        uint256 liquidityAssetRecoveredFromBurn
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan` | `address` | `address` | The address of the Loan that defaulted. |
| 1 | `defaultSuffered` | `uint256` | `uint256` | The amount of default suffered. |
| 2 | `bptsBurned` | `uint256` | `uint256` | The amount of BPTs burned to recover funds. |
| 3 | `bptsReturned` | `uint256` | `uint256` | The amount of BPTs returned to Liquidity Provider. |
| 4 | `liquidityAssetRecoveredFromBurn` | `uint256` | `uint256` | The amount of Liquidity Asset recovered from burning BPTs. |

<br />

### `DepositDateUpdated`

Emits an event indicating a that a Liquidity Provider&#x27;s effective deposit date has changed.

```solidity
    event DepositDateUpdated(
        address liquidityProvider,
        uint256 depositDate
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of a Liquidity Provider. |
| 1 | `depositDate` | `uint256` | `uint256` | The new effective deposit date. |

<br />

### `FundsDistributed`

This event emits when new funds are distributed.

```solidity
    event FundsDistributed(
        address by,
        uint256 fundsDistributed
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `by` | `address` | `address` | The address of the sender that distributed funds. |
| 1 | `fundsDistributed` | `uint256` | `uint256` | The amount of funds received for distribution. |

<br />

### `FundsWithdrawn`

This event emits when distributed funds are withdrawn by a token holder.

```solidity
    event FundsWithdrawn(
        address by,
        uint256 fundsWithdrawn,
        uint256 totalWithdrawn
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `by` | `address` | `address` | The address of the receiver of funds. |
| 1 | `fundsWithdrawn` | `uint256` | `uint256` | The amount of funds that were withdrawn. |
| 2 | `totalWithdrawn` | `uint256` | `uint256` | The total amount of funds that were withdrawn. |

<br />

### `LPStatusChanged`

Emits an event indicating a that a Liquidity Provider&#x27;s status has changed.

```solidity
    event LPStatusChanged(
        address liquidityProvider,
        bool status
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of a Liquidity Provider. |
| 1 | `status` | `bool` | `bool` | The new status of &#x60;liquidityProvider&#x60;. |

<br />

### `LiquidityCapSet`

Emits an event indicating a that the Liquidity Cap for the Pool was set.

```solidity
    event LiquidityCapSet(
        uint256 newLiquidityCap
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newLiquidityCap` | `uint256` | `uint256` | The new liquidity cap. |

<br />

### `LoanFunded`

Emits an event indicating a Loan was funded.

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
| 0 | `loan` | `address` | `address` | The funded Loan. |
| 1 | `debtLocker` | `address` | `address` | The DebtLocker. |
| 2 | `amountFunded` | `uint256` | `uint256` | The amount the Loan was funded for. |

<br />

### `LockupPeriodSet`

Emits an event indicating a that the lockup period for the Pool was set.

```solidity
    event LockupPeriodSet(
        uint256 newLockupPeriod
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newLockupPeriod` | `uint256` | `uint256` | The new lockup cap. |

<br />

### `LossesCorrectionUpdated`


```solidity
    event LossesCorrectionUpdated(
        address ,
        int256
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `int256` | `int256` |  |

<br />

### `LossesDistributed`


```solidity
    event LossesDistributed(
        address ,
        uint256
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `uint256` | `uint256` |  |

<br />

### `LossesPerShareUpdated`


```solidity
    event LossesPerShareUpdated(
        uint256
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` |  |

<br />

### `LossesRecognized`


```solidity
    event LossesRecognized(
        address ,
        uint256 ,
        uint256
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `uint256` | `uint256` |  |
| 2 | `` | `uint256` | `uint256` |  |

<br />

### `PointsCorrectionUpdated`

This event emits when an account&#x27;s &#x60;pointsCorrection&#x60; is updated.First parameter is the address of some account.Second parameter is the new value of the account&#x27;s &#x60;pointsCorrection&#x60;.

```solidity
    event PointsCorrectionUpdated(
        address account,
        int256 pointsCorrection
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` |  |
| 1 | `pointsCorrection` | `int256` | `int256` |  |

<br />

### `PointsPerShareUpdated`

This event emits when the internal &#x60;pointsPerShare&#x60; is updated.First, and only, parameter is the new value of the internal &#x60;pointsPerShare&#x60;.

```solidity
    event PointsPerShareUpdated(
        uint256 pointsPerShare
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pointsPerShare` | `uint256` | `uint256` |  |

<br />

### `PoolAdminSet`

Emits an event indicating a that a PoolAdmin was set.

```solidity
    event PoolAdminSet(
        address poolAdmin,
        bool allowed
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolAdmin` | `address` | `address` | The address of a PoolAdmin. |
| 1 | `allowed` | `bool` | `bool` | Whether &#x60;poolAdmin&#x60; is an admin of the Pool. |

<br />

### `PoolOpenedToPublic`

Emits an event indicating a that a Pool&#x27;s openness to the public has changed.

```solidity
    event PoolOpenedToPublic(
        bool isOpen
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isOpen` | `bool` | `bool` | Whether the Pool is open to the public to add liquidity. |

<br />

### `PoolStateChanged`

Emits an event indicating a that the state of the Pool has changed.

```solidity
    event PoolStateChanged(
        uint8 state
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `state` | `uint8` | `enum IPool.State` | The new state of the Pool. |

<br />

### `StakingFeeSet`

Emits an event indicating a that the staking fee for the Pool was set.

```solidity
    event StakingFeeSet(
        uint256 newStakingFee
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newStakingFee` | `uint256` | `uint256` | The new fee Stakers earn (in basis points). |

<br />

### `TotalCustodyAllowanceUpdated`

Emits an event indicating a that a Liquidity Provider&#x27;s total amount in custody of custodians has changed.

```solidity
    event TotalCustodyAllowanceUpdated(
        address liquidityProvider,
        uint256 newTotalAllowance
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidityProvider` | `address` | `address` | The address of a Liquidity Provider. |
| 1 | `newTotalAllowance` | `uint256` | `uint256` | The total amount in custody of custodians for &#x60;liquidityProvider&#x60;. |

<br />

### `Transfer`

Emitted when &#x60;value&#x60; tokens are moved from one account (&#x60;from&#x60;) to another (&#x60;to&#x60;). Note that &#x60;value&#x60; may be zero.

```solidity
    event Transfer(
        address from,
        address to,
        uint256 value
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` |  |
| 1 | `to` | `address` | `address` |  |
| 2 | `value` | `uint256` | `uint256` |  |

<br />

