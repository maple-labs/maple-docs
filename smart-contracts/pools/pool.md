# Pool

Pool maintains all accounting and functionality related to Pools.

\


## Constructor

Constructor for a Pool. It emits a \`PoolStateChanged\` event.

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

| Index |        Name       |    Type   | Internal Type | Description                                                       |
| :---: | :---------------: | :-------: | :-----------: | ----------------------------------------------------------------- |
|   0   |  `_poolDelegate`  | `address` |   `address`   | Address that has manager privileges of the Pool.                  |
|   1   | `_liquidityAsset` | `address` |   `address`   | Asset used to fund the Pool, It gets escrowed in LiquidityLocker. |
|   2   |   `_stakeAsset`   | `address` |   `address`   | Asset escrowed in StakeLocker.                                    |
|   3   |    `_slFactory`   | `address` |   `address`   | Factory used to instantiate the StakeLocker.                      |
|   4   |    `_llFactory`   | `address` |   `address`   | Factory used to instantiate the LiquidityLocker.                  |
|   5   |   `_stakingFee`   | `uint256` |   `uint256`   | Fee that Stakers earn on interest, in basis points.               |
|   6   |   `_delegateFee`  | `uint256` |   `uint256`   | Fee that the Pool Delegate earns on interest, in basis points.    |
|   7   |  `_liquidityCap`  | `uint256` |   `uint256`   | Max amount of Liquidity Asset accepted by the Pool.               |
|   8   |       `name`      |  `string` |    `string`   | Name of Pool token.                                               |
|   9   |      `symbol`     |  `string` |    `string`   | Symbol of Pool token.                                             |

\


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

| Index |        Name       |    Type   | Internal Type | Description                                         |
| :---: | :---------------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   |      `_bPool`     | `address` |   `address`   | The address of Balancer pool.                       |
|   1   | `_liquidityAsset` | `address` |   `address`   | The asset used by Pool for liquidity to fund Loans. |
|   2   |     `_staker`     | `address` |   `address`   | The address that deposited BPTs to StakeLocker.     |
|   3   |   `_stakeLocker`  | `address` |   `address`   | Escrows BPTs deposited by Staker.                   |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                |
| :---: | :--: | :-------: | :-----------: | -------------------------- |
|   0   |      | `uint256` |   `uint256`   | USDC value of staker BPTs. |

\


### `DL_FACTORY` _\[state variable]_

The factory type of \`DebtLockerFactory\`.

```solidity
    function DL_FACTORY()
        pure
        returns (
            uint8
        );
```

#### Return Values:

| Index | Name |   Type  | Internal Type | Description |
| :---: | :--: | :-----: | :-----------: | ----------- |
|   0   |      | `uint8` |    `uint8`    |             |

\


### `accumulativeFundsOf`

Returns the amount of funds that an account has earned in total. accumulativeFundsOf(\_owner) = withdrawableFundsOf(\_owner) + withdrawnFundsOf(\_owner) = (pointsPerShare \* balanceOf(\_owner) + pointsCorrection\[\_owner]) / pointsMultiplier

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

| Index |   Name   |    Type   | Internal Type | Description                    |
| :---: | :------: | :-------: | :-----------: | ------------------------------ |
|   0   | `_owner` | `address` |   `address`   | The address of a token holder. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                               |
| :---: | :--: | :-------: | :-----------: | --------------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount of funds that \`\_owner\` has earned in total. |

\


### `accumulativeLossesOf`

Returns the amount of losses that an account has earned in total. accumulativeLossesOf(\_owner) = recognizableLossesOf(\_owner) + recognizedLossesOf(\_owner) = (lossesPerShare \* balanceOf(\_owner) + lossesCorrection\[\_owner]) / pointsMultiplier

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

| Index |   Name   |    Type   | Internal Type | Description                    |
| :---: | :------: | :-------: | :-----------: | ------------------------------ |
|   0   | `_owner` | `address` |   `address`   | The address of a token holder. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                                |
| :---: | :--: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount of losses that \`\_owner\` has earned in total. |

\


### `allowance`

Returns the remaining number of tokens that \`spender\` will be allowed to spend on behalf of \`owner\` through {transferFrom}. This is zero by default. This value changes when {approve} or {transferFrom} are called.

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

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   |  `owner`  | `address` |   `address`   |             |
|   1   | `spender` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `allowedLiquidityProviders` _\[state variable]_

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

| Index |         Name        |    Type   | Internal Type | Description                         |
| :---: | :-----------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of a LiquidityProvider. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                                                 |
| :---: | :--: | :----: | :-----------: | ----------------------------------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether \`liquidityProvider\` has early access to the Pool. |

\


### `approve`

Sets \`amount\` as the allowance of \`spender\` over the caller's tokens. Returns a boolean value indicating whether the operation succeeded. IMPORTANT: Beware that changing an allowance with this method brings the risk that someone may use both the old and the new allowance by unfortunate transaction ordering. One possible solution to mitigate this race condition is to first reduce the spender's allowance to 0 and set the desired value afterwards: https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729 Emits an {Approval} event. Requirements: - \`spender\` cannot be the zero address.

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

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   | `spender` | `address` |   `address`   |             |
|   1   |  `amount` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `balanceOf`

Returns the amount of tokens owned by \`account\`.

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

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   | `account` | `address` |   `address`   |             |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `cancelWithdraw`

Cancels an initiated withdrawal by resetting the account's withdraw cooldown. It emits a \`Cooldown\` event.

```solidity
    function cancelWithdraw()
        nonpayable;
```

\


### `claim`

Claims available funds for the Loan through a specified DebtLockerFactory. Only the Pool Delegate or a Pool Admin can call this function. It emits two \`BalanceUpdated\` events. It emits a \`Claim\` event.

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

| Index |     Name    |    Type   | Internal Type | Description                            |
| :---: | :---------: | :-------: | :-----------: | -------------------------------------- |
|   0   |    `loan`   | `address` |   `address`   | The address of the loan to claim from. |
|   1   | `dlFactory` | `address` |   `address`   | The address of the DebtLockerFactory.  |

#### Return Values:

| Index |     Name    |     Type     | Internal Type | Description                                                                                                                                                                                                                                                         |
| :---: | :---------: | :----------: | :-----------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|   0   | `claimInfo` | `uint256[7]` |  `uint256[7]` | The claim details. \[0] => Total amount claimed, \[1] => Interest portion claimed, \[2] => Principal portion claimed, \[3] => Fee portion claimed, \[4] => Excess portion claimed, \[5] => Recovered portion claimed (from liquidations), \[6] => Default suffered. |

\


### `custodyAllowance` _\[state variable]_

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

| Index |     Name    |    Type   | Internal Type | Description                 |
| :---: | :---------: | :-------: | :-----------: | --------------------------- |
|   0   |  `account`  | `address` |   `address`   | The address of an account.  |
|   1   | `custodian` | `address` |   `address`   | The address of a custodian. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                                               |
| :---: | :--: | :-------: | :-----------: | ------------------------------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount of PoolFDTs of \`account\` that are "locked" at \`custodian\`. |

\


### `deactivate`

Triggers deactivation, permanently shutting down the Pool. Must have less than 100 USD worth of Liquidity Asset \`principalOut\`. Only the Pool Delegate can call this function. It emits a \`PoolStateChanged\` event.

```solidity
    function deactivate()
        nonpayable;
```

\


### `debtLockers` _\[state variable]_

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

| Index |         Name        |    Type   | Internal Type | Description                         |
| :---: | :-----------------: | :-------: | :-----------: | ----------------------------------- |
|   0   |        `loan`       | `address` |   `address`   | The address of a Loan.              |
|   1   | `debtLockerFactory` | `address` |   `address`   | The address of a DebtLockerFactory. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                                                        |
| :---: | :--: | :-------: | :-----------: | ---------------------------------------------------------------------------------- |
|   0   |      | `address` |   `address`   | The address of the DebtLocker corresponding to \`loan\` and \`debtLockerFactory\`. |

\


### `delegateFee` _\[state variable]_

The fee the Pool Delegate earns (in basis points).

```solidity
    function delegateFee()
        pure
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `deposit`

Handles Liquidity Providers depositing of Liquidity Asset into the LiquidityLocker, minting PoolFDTs. It emits a \`DepositDateUpdated\` event. It emits a \`BalanceUpdated\` event. It emits a \`Cooldown\` event.

```solidity
    function deposit(
        uint256 amt
    )
        nonpayable;
```

#### Parameters:

| Index |  Name |    Type   | Internal Type | Description                               |
| :---: | :---: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `amt` | `uint256` |   `uint256`   | The amount of Liquidity Asset to deposit. |

\


### `depositDate` _\[state variable]_

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

| Index |    Name   |    Type   | Internal Type | Description                |
| :---: | :-------: | :-------: | :-----------: | -------------------------- |
|   0   | `account` | `address` |   `address`   | The address of an account. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                                             |
| :---: | :--: | :-------: | :-----------: | ----------------------------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The unix timestamp of the weighted average deposit date of \`account\`. |

\


### `finalize`

Finalizes the Pool, enabling deposits. Checks the amount the Pool Delegate deposited to the StakeLocker. Only the Pool Delegate can call this function. It emits a \`PoolStateChanged\` event.

```solidity
    function finalize()
        nonpayable;
```

\


### `fundLoan`

Funds a Loan for an amount, utilizing the supplied DebtLockerFactory for DebtLockers. Only the Pool Delegate can call this function. It emits a \`LoanFunded\` event. It emits a \`BalanceUpdated\` event.

```solidity
    function fundLoan(
        address loan,
        address dlFactory,
        uint256 amt
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                      |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------------ |
|   0   |    `loan`   | `address` |   `address`   | The address of the Loan to fund.                 |
|   1   | `dlFactory` | `address` |   `address`   | The address of the DebtLockerFactory to utilize. |
|   2   |    `amt`    | `uint256` |   `uint256`   | The amount to fund the Loan.                     |

\


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

| Index | Name |    Type   | Internal Type | Description                                                                  |
| :---: | :--: | :-------: | :-----------: | ---------------------------------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The min amount of Liquidity Asset coverage from staking required.            |
|   1   |      | `uint256` |   `uint256`   | The present amount of Liquidity Asset coverage from the Pool Delegate stake. |
|   2   |      |   `bool`  |     `bool`    | Whether enough stake is present from the Pool Delegate for finalization.     |
|   3   |      | `uint256` |   `uint256`   | The staked BPTs required for minimum Liquidity Asset coverage.               |
|   4   |      | `uint256` |   `uint256`   | The current staked BPTs.                                                     |

\


### `getPoolSharesRequired`

Calculates BPTs required if burning BPTs for the Liquidity Asset, given supplied \`tokenAmountOutRequired\`.

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

| Index |               Name              |    Type   | Internal Type | Description                                              |
| :---: | :-----------------------------: | :-------: | :-----------: | -------------------------------------------------------- |
|   0   |             `_bPool`            | `address` |   `address`   | The Balancer pool that issues the BPTs.                  |
|   1   |        `_liquidityAsset`        | `address` |   `address`   | Swap out asset (e.g. USDC) to receive when burning BPTs. |
|   2   |            `_staker`            | `address` |   `address`   | The address that deposited BPTs to StakeLocker.          |
|   3   |          `_stakeLocker`         | `address` |   `address`   | Escrows BPTs deposited by Staker.                        |
|   4   | `_liquidityAssetAmountRequired` | `uint256` |   `uint256`   | The amount of Liquidity Asset required to recover.       |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                            |
| :---: | :--: | :-------: | :-----------: | -------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The \`poolAmountIn\` required.         |
|   1   |      | `uint256` |   `uint256`   | The \`poolAmountIn\` currently staked. |

\


### `increaseCustodyAllowance`

Increases the custody allowance for a given Custodian corresponding to the calling account (\`msg.sender\`). It emits a \`CustodyAllowanceChanged\` event. It emits a \`TotalCustodyAllowanceUpdated\` event.

```solidity
    function increaseCustodyAllowance(
        address custodian,
        uint256 amount
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                                               |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------------------------------------- |
|   0   | `custodian` | `address` |   `address`   | The address which will act as Custodian of a given amount for an account. |
|   1   |   `amount`  | `uint256` |   `uint256`   | The number of additional FDTs to be custodied by the Custodian.           |

\


### `intendToWithdraw`

Activates the cooldown period to withdraw. It can't be called if the account is not providing liquidity. It emits a \`Cooldown\` event.

```solidity
    function intendToWithdraw()
        nonpayable;
```

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


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

| Index |     Name     |    Type   | Internal Type | Description                                                                      |
| :---: | :----------: | :-------: | :-----------: | -------------------------------------------------------------------------------- |
|   0   | `depositAmt` | `uint256` |   `uint256`   | The amount of tokens (i.e liquidityAsset type) the account is trying to deposit. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `isPoolFinalized`

Checks that the Pool state is \`Finalized\`.

```solidity
    function isPoolFinalized()
        view
        returns (
            bool
        );
```

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                               |
| :---: | :--: | :----: | :-----------: | ----------------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether the Pool is in a Finalized state. |

\


### `liquidityAsset` _\[state variable]_

The asset deposited by Lenders into the LiquidityLocker, for funding Loans.

```solidity
    function liquidityAsset()
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


### `liquidityCap` _\[state variable]_

The amount of liquidity tokens accepted by the Pool.

```solidity
    function liquidityCap()
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


### `liquidityLocker` _\[state variable]_

The address of the asset deposited by Stakers into the StakeLocker (BPTs), for liquidation during default events.

```solidity
    function liquidityLocker()
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


### `lockupPeriod` _\[state variable]_

The period of time from an account's deposit date during which they cannot withdraw any funds.

```solidity
    function lockupPeriod()
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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `openToPublic` _\[state variable]_

Whether the Pool is open to the public for LP deposits.

```solidity
    function openToPublic()
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


### `poolAdmins` _\[state variable]_

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

| Index |     Name    |    Type   | Internal Type | Description                 |
| :---: | :---------: | :-------: | :-----------: | --------------------------- |
|   0   | `poolAdmin` | `address` |   `address`   | The address of a PoolAdmin. |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description                                                                                   |
| :---: | :--: | :----: | :-----------: | --------------------------------------------------------------------------------------------- |
|   0   |      | `bool` |     `bool`    | Whether \`poolAdmin\` has permission to do certain operations in case of disaster management. |

\


### `poolDelegate` _\[state variable]_

The Pool Delegate address, maintains full authority over the Pool.

```solidity
    function poolDelegate()
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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `poolState` _\[state variable]_

The state of the Pool.

```solidity
    function poolState()
        view
        returns (
            uint8
        );
```

#### Return Values:

| Index | Name |   Type  |    Internal Type   | Description |
| :---: | :--: | :-----: | :----------------: | ----------- |
|   0   |      | `uint8` | `enum IPool.State` |             |

\


### `principalOut` _\[state variable]_

The sum of all outstanding principal on Loans.

```solidity
    function principalOut()
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


### `reclaimERC20`

Transfers any locked funds to the Governor. Only the Governor can call this function.

```solidity
    function reclaimERC20(
        address token
    )
        nonpayable;
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description                               |
| :---: | :-----: | :-------: | :-----------: | ----------------------------------------- |
|   0   | `token` | `address` |   `address`   | The address of the token to be reclaimed. |

\


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

| Index |   Name   |    Type   | Internal Type | Description                    |
| :---: | :------: | :-------: | :-----------: | ------------------------------ |
|   0   | `_owner` | `address` |   `address`   | The address of a token holder. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                         |
| :---: | :--: | :-------: | :-----------: | --------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount of losses that \`\_owner\` can withdraw. |

\


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

| Index |   Name   |    Type   | Internal Type | Description                    |
| :---: | :------: | :-------: | :-----------: | ------------------------------ |
|   0   | `_owner` | `address` |   `address`   | The address of a token holder. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                           |
| :---: | :--: | :-------: | :-----------: | ----------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount of losses that \`\_owner\` has recognized. |

\


### `setAllowList`

Sets the account status in the Pool's allowlist. Only the Pool Delegate can call this function. It emits an \`LPStatusChanged\` event.

```solidity
    function setAllowList(
        address account,
        bool status
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                |
| :---: | :-------: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `account` | `address` |   `address`   | The address to set status for.             |
|   1   |  `status` |   `bool`  |     `bool`    | The status of an account in the allowlist. |

\


### `setLiquidityCap`

Sets the liquidity cap. Only the Pool Delegate or a Pool Admin can call this function. It emits a \`LiquidityCapSet\` event.

```solidity
    function setLiquidityCap(
        uint256 newLiquidityCap
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                  |
| :---: | :---------------: | :-------: | :-----------: | ---------------------------- |
|   0   | `newLiquidityCap` | `uint256` |   `uint256`   | The new liquidity cap value. |

\


### `setLockupPeriod`

Sets the lockup period. Only the Pool Delegate can call this function. It emits a \`LockupPeriodSet\` event.

```solidity
    function setLockupPeriod(
        uint256 newLockupPeriod
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                             |
| :---: | :---------------: | :-------: | :-----------: | ------------------------------------------------------- |
|   0   | `newLockupPeriod` | `uint256` |   `uint256`   | The new lockup period used to restrict the withdrawals. |

\


### `setOpenToPublic`

Sets whether the Pool is open to the public. Only the Pool Delegate can call this function. It emits a \`PoolOpenedToPublic\` event.

```solidity
    function setOpenToPublic(
        bool open
    )
        nonpayable;
```

#### Parameters:

| Index |  Name  |  Type  | Internal Type | Description                                            |
| :---: | :----: | :----: | :-----------: | ------------------------------------------------------ |
|   0   | `open` | `bool` |     `bool`    | Whether the Pool is open to liquidity from the public. |

\


### `setPoolAdmin`

Sets a Pool Admin. Only the Pool Delegate can call this function. It emits a \`PoolAdminSet\` event.

```solidity
    function setPoolAdmin(
        address poolAdmin,
        bool allowed
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                             |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------------------- |
|   0   | `poolAdmin` | `address` |   `address`   | An address being allowed or disallowed as a Pool Admin. |
|   1   |  `allowed`  |   `bool`  |     `bool`    | Whether \`poolAdmin\` is an admin of the Pool.          |

\


### `setStakingFee`

Sets the staking fee. Only the Pool Delegate can call this function. It emits a \`StakingFeeSet\` event.

```solidity
    function setStakingFee(
        uint256 newStakingFee
    )
        nonpayable;
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description          |
| :---: | :-------------: | :-------: | :-----------: | -------------------- |
|   0   | `newStakingFee` | `uint256` |   `uint256`   | The new staking fee. |

\


### `stakeAsset` _\[state variable]_

The address of the asset deposited by Stakers into the StakeLocker (BPTs), for liquidation during default events.

```solidity
    function stakeAsset()
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


### `stakeLocker` _\[state variable]_

The address of the StakeLocker, escrowing \`stakeAsset\`.

```solidity
    function stakeLocker()
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


### `stakingFee` _\[state variable]_

The fee Stakers earn (in basis points).

```solidity
    function stakingFee()
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


### `superFactory` _\[state variable]_

The factory that deployed this Loan.

```solidity
    function superFactory()
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


### `totalCustodyAllowance` _\[state variable]_

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

| Index |    Name   |    Type   | Internal Type | Description                |
| :---: | :-------: | :-------: | :-----------: | -------------------------- |
|   0   | `account` | `address` |   `address`   | The address of an account. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                                                                                   |
| :---: | :--: | :-------: | :-----------: | ------------------------------------------------------------------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The total amount of PoolFDTs that are "locked" for \`account\`. Cannot be greater than the account's balance. |

\


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

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |

\


### `transfer`

Moves \`amount\` tokens from the caller's account to \`recipient\`. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event. Requirements: - \`recipient\` cannot be the zero address. - the caller must have a balance of at least \`amount\`.

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

| Index |     Name    |    Type   | Internal Type | Description |
| :---: | :---------: | :-------: | :-----------: | ----------- |
|   0   | `recipient` | `address` |   `address`   |             |
|   1   |   `amount`  | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `transferByCustodian`

Transfers custodied PoolFDTs back to the account. \`from\` and \`to\` should always be equal in this implementation. This means that the Custodian can only decrease their own allowance and unlock funds for the original owner. It emits a \`CustodyTransfer\` event. It emits a \`CustodyAllowanceChanged\` event. It emits a \`TotalCustodyAllowanceUpdated\` event.

```solidity
    function transferByCustodian(
        address from,
        address to,
        uint256 amount
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                                                        |
| :---: | :------: | :-------: | :-----------: | ------------------------------------------------------------------ |
|   0   |  `from`  | `address` |   `address`   | The address which holds the PoolFDTs.                              |
|   1   |   `to`   | `address` |   `address`   | The address which will be the new owner of the amount of PoolFDTs. |
|   2   | `amount` | `uint256` |   `uint256`   | The amount of PoolFDTs transferred.                                |

\


### `transferFrom`

Moves \`amount\` tokens from \`sender\` to \`recipient\` using the allowance mechanism. \`amount\` is then deducted from the caller's allowance. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event. Emits an {Approval} event indicating the updated allowance. This is not required by the EIP. See the note at the beginning of {ERC20}. Requirements: - \`sender\` and \`recipient\` cannot be the zero address. - \`sender\` must have a balance of at least \`amount\`. - the caller must have allowance for \`\`sender\`\`'s tokens of at least \`amount\`.

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

| Index |     Name    |    Type   | Internal Type | Description |
| :---: | :---------: | :-------: | :-----------: | ----------- |
|   0   |   `sender`  | `address` |   `address`   |             |
|   1   | `recipient` | `address` |   `address`   |             |
|   2   |   `amount`  | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `triggerDefault`

Liquidates a Loan. The Pool Delegate could liquidate the Loan only when the Loan completes its grace period. The Pool Delegate can claim its proportion of recovered funds from the liquidation using the \`claim()\` function. Only the Pool Delegate can call this function.

```solidity
    function triggerDefault(
        address loan,
        address dlFactory
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                                                         |
| :---: | :---------: | :-------: | :-----------: | ----------------------------------------------------------------------------------- |
|   0   |    `loan`   | `address` |   `address`   | The address of the Loan to liquidate.                                               |
|   1   | `dlFactory` | `address` |   `address`   | The address of the DebtLockerFactory that is used to pull corresponding DebtLocker. |

\


### `updateFundsReceived`

Registers a payment of funds in tokens. May be called directly after a deposit is made. Calls \_updateFundsTokenBalance(), whereby the contract computes the delta of the new and previous \`fundsToken\` balance and increments the total received funds (cumulative), by delta, by calling \_distributeFunds().

```solidity
    function updateFundsReceived()
        nonpayable;
```

\


### `updateLossesReceived`

Registers a loss. May be called directly after a shortfall after BPT burning occurs. Calls \_updateLossesTokenBalance(), whereby the contract computes the delta of the new and previous losses balance and increments the total losses (cumulative), by delta, by calling \_distributeLosses().

```solidity
    function updateLossesReceived()
        nonpayable;
```

\


### `withdraw`

Handles Liquidity Providers withdrawing of Liquidity Asset from the LiquidityLocker, burning PoolFDTs. It emits two \`BalanceUpdated\` event.

```solidity
    function withdraw(
        uint256 amt
    )
        nonpayable;
```

#### Parameters:

| Index |  Name |    Type   | Internal Type | Description                                |
| :---: | :---: | :-------: | :-----------: | ------------------------------------------ |
|   0   | `amt` | `uint256` |   `uint256`   | The amount of Liquidity Asset to withdraw. |

\


### `withdrawCooldown` _\[state variable]_

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

| Index |         Name        |    Type   | Internal Type | Description                         |
| :---: | :-----------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of a LiquidityProvider. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                                                          |
| :---: | :--: | :-------: | :-----------: | ------------------------------------------------------------------------------------ |
|   0   |      | `uint256` |   `uint256`   | The unix timestamp of when individual LPs have notified of their intent to withdraw. |

\


### `withdrawFunds`

Withdraws all claimable interest from the LiquidityLocker for an account using \`interestSum\` accounting. It emits a \`BalanceUpdated\` event.

```solidity
    function withdrawFunds()
        nonpayable;
```

\


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

| Index |   Name   |    Type   | Internal Type | Description                     |
| :---: | :------: | :-------: | :-----------: | ------------------------------- |
|   0   | `_owner` | `address` |   `address`   | The address of some FDT holder. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                     |
| :---: | :--: | :-------: | :-----------: | ----------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount funds that \`\_owner\` can withdraw. |

\


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

| Index |   Name   |    Type   | Internal Type | Description                    |
| :---: | :------: | :-------: | :-----------: | ------------------------------ |
|   0   | `_owner` | `address` |   `address`   | The address of a token holder. |

#### Return Values:

| Index | Name |    Type   | Internal Type | Description                                         |
| :---: | :--: | :-------: | :-----------: | --------------------------------------------------- |
|   0   |      | `uint256` |   `uint256`   | The amount of funds that \`\_owner\` has withdrawn. |

\


### `decimals`

Returns the number of decimals used to get its user representation. For example, if \`decimals\` equals \`2\`, a balance of \`505\` tokens should be displayed to a user as \`5,05\` (\`505 / 10 \*\* 2\`). Tokens usually opt for a value of 18, imitating the relationship between Ether and Wei. This is the value {ERC20} uses, unless {\_setupDecimals} is called. NOTE: This information is only used for _display_ purposes: it in no way affects any of the arithmetic of the contract, including {IERC20-balanceOf} and {IERC20-transfer}.

```solidity
    function decimals()
        view
        returns (
            uint8
        );
```

#### Return Values:

| Index | Name |   Type  | Internal Type | Description |
| :---: | :--: | :-----: | :-----------: | ----------- |
|   0   |      | `uint8` |    `uint8`    |             |

\


### `decreaseAllowance`

Atomically decreases the allowance granted to \`spender\` by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - \`spender\` cannot be the zero address. - \`spender\` must have allowance for the caller of at least \`subtractedValue\`.

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

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   |     `spender`     | `address` |   `address`   |             |
|   1   | `subtractedValue` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


### `increaseAllowance`

Atomically increases the allowance granted to \`spender\` by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - \`spender\` cannot be the zero address.

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

| Index |     Name     |    Type   | Internal Type | Description |
| :---: | :----------: | :-------: | :-----------: | ----------- |
|   0   |   `spender`  | `address` |   `address`   |             |
|   1   | `addedValue` | `uint256` |   `uint256`   |             |

#### Return Values:

| Index | Name |  Type  | Internal Type | Description |
| :---: | :--: | :----: | :-----------: | ----------- |
|   0   |      | `bool` |     `bool`    |             |

\


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

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `string` |    `string`   |             |

\


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

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `string` |    `string`   |             |

\


## Events

### `Approval`

Emitted when the allowance of a \`spender\` for an \`owner\` is set by a call to {approve}. \`value\` is the new allowance.

```solidity
    event Approval(
        address owner,
        address spender,
        uint256 value
    );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description |
| :---: | :-------: | :-------: | :-----------: | ----------- |
|   0   |  `owner`  | `address` |   `address`   |             |
|   1   | `spender` | `address` |   `address`   |             |
|   2   |  `value`  | `uint256` |   `uint256`   |             |

\


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

| Index |         Name        |    Type   | Internal Type | Description                                                                      |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------------------------------------------------- |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of a Liquidity Provider.                                             |
|   1   |       `token`       | `address` |   `address`   | The address of the token for which the balance of \`liquidityProvider\` changed. |
|   2   |      `balance`      | `uint256` |   `uint256`   | The new balance for \`liquidityProvider\`.                                       |

\


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

| Index |          Name         |    Type   | Internal Type | Description                                   |
| :---: | :-------------------: | :-------: | :-----------: | --------------------------------------------- |
|   0   |         `loan`        | `address` |   `address`   | The Loan.                                     |
|   1   |       `interest`      | `uint256` |   `uint256`   | The interest.                                 |
|   2   |      `principal`      | `uint256` |   `uint256`   | The principal.                                |
|   3   |         `fee`         | `uint256` |   `uint256`   | The total fee.                                |
|   4   |  `stakeLockerPortion` | `uint256` |   `uint256`   | The portion of the fee for Stakers.           |
|   5   | `poolDelegatePortion` | `uint256` |   `uint256`   | The portion of the fee for the Pool Delegate. |

\


### `Cooldown`

Emits an event indicating a that the withdrawal cooldown for a Liquidity Provider of the Pool has updated.

```solidity
    event Cooldown(
        address liquidityProvider,
        uint256 cooldown
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                          |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of a Liquidity Provider. |
|   1   |      `cooldown`     | `uint256` |   `uint256`   | The new withdrawal cooldown.         |

\


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

| Index |         Name        |    Type   | Internal Type | Description                                                                        |
| :---: | :-----------------: | :-------: | :-----------: | ---------------------------------------------------------------------------------- |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of amount who's funds are being custodied.                             |
|   1   |     `custodian`     | `address` |   `address`   | The address of the custodian.                                                      |
|   2   |    `oldAllowance`   | `uint256` |   `uint256`   | The original total amount in custodian by \`custodian\` for \`liquidityProvider\`. |
|   3   |    `newAllowance`   | `uint256` |   `uint256`   | The updated total amount in custodian by \`custodian\` for \`liquidityProvider\`.  |

\


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

| Index |     Name    |    Type   | Internal Type | Description                                 |
| :---: | :---------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `custodian` | `address` |   `address`   | The address of the custodian.               |
|   1   |    `from`   | `address` |   `address`   | The source of funds that were custodied.    |
|   2   |     `to`    | `address` |   `address`   | The destination of funds.                   |
|   3   |   `amount`  | `uint256` |   `uint256`   | The amount of custodied tokens transferred. |

\


### `DefaultSuffered`

Emits an event indicating the one of the Pool's Loans defaulted.

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

| Index |                Name               |    Type   | Internal Type | Description                                                |
| :---: | :-------------------------------: | :-------: | :-----------: | ---------------------------------------------------------- |
|   0   |               `loan`              | `address` |   `address`   | The address of the Loan that defaulted.                    |
|   1   |         `defaultSuffered`         | `uint256` |   `uint256`   | The amount of default suffered.                            |
|   2   |            `bptsBurned`           | `uint256` |   `uint256`   | The amount of BPTs burned to recover funds.                |
|   3   |           `bptsReturned`          | `uint256` |   `uint256`   | The amount of BPTs returned to Liquidity Provider.         |
|   4   | `liquidityAssetRecoveredFromBurn` | `uint256` |   `uint256`   | The amount of Liquidity Asset recovered from burning BPTs. |

\


### `DepositDateUpdated`

Emits an event indicating a that a Liquidity Provider's effective deposit date has changed.

```solidity
    event DepositDateUpdated(
        address liquidityProvider,
        uint256 depositDate
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                          |
| :---: | :-----------------: | :-------: | :-----------: | ------------------------------------ |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of a Liquidity Provider. |
|   1   |    `depositDate`    | `uint256` |   `uint256`   | The new effective deposit date.      |

\


### `FundsDistributed`

This event emits when new funds are distributed.

```solidity
    event FundsDistributed(
        address by,
        uint256 fundsDistributed
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                                       |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------------- |
|   0   |        `by`        | `address` |   `address`   | The address of the sender that distributed funds. |
|   1   | `fundsDistributed` | `uint256` |   `uint256`   | The amount of funds received for distribution.    |

\


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

| Index |       Name       |    Type   | Internal Type | Description                                    |
| :---: | :--------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   |       `by`       | `address` |   `address`   | The address of the receiver of funds.          |
|   1   | `fundsWithdrawn` | `uint256` |   `uint256`   | The amount of funds that were withdrawn.       |
|   2   | `totalWithdrawn` | `uint256` |   `uint256`   | The total amount of funds that were withdrawn. |

\


### `LPStatusChanged`

Emits an event indicating a that a Liquidity Provider's status has changed.

```solidity
    event LPStatusChanged(
        address liquidityProvider,
        bool status
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                              |
| :---: | :-----------------: | :-------: | :-----------: | ---------------------------------------- |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of a Liquidity Provider.     |
|   1   |       `status`      |   `bool`  |     `bool`    | The new status of \`liquidityProvider\`. |

\


### `LiquidityCapSet`

Emits an event indicating a that the Liquidity Cap for the Pool was set.

```solidity
    event LiquidityCapSet(
        uint256 newLiquidityCap
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description            |
| :---: | :---------------: | :-------: | :-----------: | ---------------------- |
|   0   | `newLiquidityCap` | `uint256` |   `uint256`   | The new liquidity cap. |

\


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

| Index |      Name      |    Type   | Internal Type | Description                         |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------- |
|   0   |     `loan`     | `address` |   `address`   | The funded Loan.                    |
|   1   |  `debtLocker`  | `address` |   `address`   | The DebtLocker.                     |
|   2   | `amountFunded` | `uint256` |   `uint256`   | The amount the Loan was funded for. |

\


### `LockupPeriodSet`

Emits an event indicating a that the lockup period for the Pool was set.

```solidity
    event LockupPeriodSet(
        uint256 newLockupPeriod
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description         |
| :---: | :---------------: | :-------: | :-----------: | ------------------- |
|   0   | `newLockupPeriod` | `uint256` |   `uint256`   | The new lockup cap. |

\


### `LossesCorrectionUpdated`

```solidity
    event LossesCorrectionUpdated(
        address ,
        int256
    );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |
|   1   | \`\` |  `int256` |    `int256`   |             |

\


### `LossesDistributed`

```solidity
    event LossesDistributed(
        address ,
        uint256
    );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |
|   1   | \`\` | `uint256` |   `uint256`   |             |

\


### `LossesPerShareUpdated`

```solidity
    event LossesPerShareUpdated(
        uint256
    );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `uint256` |   `uint256`   |             |

\


### `LossesRecognized`

```solidity
    event LossesRecognized(
        address ,
        uint256 ,
        uint256
    );
```

#### Parameters:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   | \`\` | `address` |   `address`   |             |
|   1   | \`\` | `uint256` |   `uint256`   |             |
|   2   | \`\` | `uint256` |   `uint256`   |             |

\


### `PointsCorrectionUpdated`

This event emits when an account's \`pointsCorrection\` is updated.First parameter is the address of some account.Second parameter is the new value of the account's \`pointsCorrection\`.

```solidity
    event PointsCorrectionUpdated(
        address account,
        int256 pointsCorrection
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description |
| :---: | :----------------: | :-------: | :-----------: | ----------- |
|   0   |      `account`     | `address` |   `address`   |             |
|   1   | `pointsCorrection` |  `int256` |    `int256`   |             |

\


### `PointsPerShareUpdated`

This event emits when the internal \`pointsPerShare\` is updated.First, and only, parameter is the new value of the internal \`pointsPerShare\`.

```solidity
    event PointsPerShareUpdated(
        uint256 pointsPerShare
    );
```

#### Parameters:

| Index |       Name       |    Type   | Internal Type | Description |
| :---: | :--------------: | :-------: | :-----------: | ----------- |
|   0   | `pointsPerShare` | `uint256` |   `uint256`   |             |

\


### `PoolAdminSet`

Emits an event indicating a that a PoolAdmin was set.

```solidity
    event PoolAdminSet(
        address poolAdmin,
        bool allowed
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                                    |
| :---: | :---------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   | `poolAdmin` | `address` |   `address`   | The address of a PoolAdmin.                    |
|   1   |  `allowed`  |   `bool`  |     `bool`    | Whether \`poolAdmin\` is an admin of the Pool. |

\


### `PoolOpenedToPublic`

Emits an event indicating a that a Pool's openness to the public has changed.

```solidity
    event PoolOpenedToPublic(
        bool isOpen
    );
```

#### Parameters:

| Index |   Name   |  Type  | Internal Type | Description                                              |
| :---: | :------: | :----: | :-----------: | -------------------------------------------------------- |
|   0   | `isOpen` | `bool` |     `bool`    | Whether the Pool is open to the public to add liquidity. |

\


### `PoolStateChanged`

Emits an event indicating a that the state of the Pool has changed.

```solidity
    event PoolStateChanged(
        uint8 state
    );
```

#### Parameters:

| Index |   Name  |   Type  |    Internal Type   | Description                |
| :---: | :-----: | :-----: | :----------------: | -------------------------- |
|   0   | `state` | `uint8` | `enum IPool.State` | The new state of the Pool. |

\


### `StakingFeeSet`

Emits an event indicating a that the staking fee for the Pool was set.

```solidity
    event StakingFeeSet(
        uint256 newStakingFee
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                                 |
| :---: | :-------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `newStakingFee` | `uint256` |   `uint256`   | The new fee Stakers earn (in basis points). |

\


### `TotalCustodyAllowanceUpdated`

Emits an event indicating a that a Liquidity Provider's total amount in custody of custodians has changed.

```solidity
    event TotalCustodyAllowanceUpdated(
        address liquidityProvider,
        uint256 newTotalAllowance
    );
```

#### Parameters:

| Index |         Name        |    Type   | Internal Type | Description                                                          |
| :---: | :-----------------: | :-------: | :-----------: | -------------------------------------------------------------------- |
|   0   | `liquidityProvider` | `address` |   `address`   | The address of a Liquidity Provider.                                 |
|   1   | `newTotalAllowance` | `uint256` |   `uint256`   | The total amount in custody of custodians for \`liquidityProvider\`. |

\


### `Transfer`

Emitted when \`value\` tokens are moved from one account (\`from\`) to another (\`to\`). Note that \`value\` may be zero.

```solidity
    event Transfer(
        address from,
        address to,
        uint256 value
    );
```

#### Parameters:

| Index |   Name  |    Type   | Internal Type | Description |
| :---: | :-----: | :-------: | :-----------: | ----------- |
|   0   |  `from` | `address` |   `address`   |             |
|   1   |   `to`  | `address` |   `address`   |             |
|   2   | `value` | `uint256` |   `uint256`   |             |

\
