# Stake Locker

StakeLocker holds custody of stakeAsset tokens for a given Pool and earns revenue from interest.

## Constructor

```text
  constructor(
    address _stakeAsset,
    address _liquidityAsset,
    address _pool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_stakeAsset` | `address` | `address` |  |
| 1 | `_liquidityAsset` | `address` | `address` |  |
| 2 | `_pool` | `address` | `address` |  |

## Functions

### accumulativeFundsOf

Returns the amount of funds that an account has earned in total. accumulativeFundsOf\(\_owner\) = withdrawableFundsOf\(\_owner\) + withdrawnFundsOf\(\_owner\) = \(pointsPerShare \* balanceOf\(\_owner\) + pointsCorrection\[\_owner\]\) / pointsMultiplier

```text
  function accumulativeFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of funds that \`\_owner\` has earned in total. |

### accumulativeLossesOf

Returns the amount of losses that an account has earned in total. accumulativeLossesOf\(\_owner\) = recognizableLossesOf\(\_owner\) + recognizedLossesOf\(\_owner\) = \(lossesPerShare \* balanceOf\(\_owner\) + lossesCorrection\[\_owner\]\) / pointsMultiplier

```text
  function accumulativeLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of losses that \`\_owner\` has earned in total. |

### allowance

Returns the remaining number of tokens that \`spender\` will be allowed to spend on behalf of \`owner\` through {transferFrom}. This is zero by default. This value changes when {approve} or {transferFrom} are called.

```text
  function allowance(
    address owner,
    address spender
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `owner` | `address` | `address` |  |
| 1 | `spender` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### allowed \(state variable\)

```text
  function allowed(
    address
  ) view returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` | Whether \`account\` is allowed. |

### approve

Sets \`amount\` as the allowance of \`spender\` over the caller's tokens. Returns a boolean value indicating whether the operation succeeded. IMPORTANT: Beware that changing an allowance with this method brings the risk that someone may use both the old and the new allowance by unfortunate transaction ordering. One possible solution to mitigate this race condition is to first reduce the spender's allowance to 0 and set the desired value afterwards: [https://github.com/ethereum/EIPs/issues/20\#issuecomment-263524729](https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729) Emits an {Approval} event.

```text
  function approve(
    address spender,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `amount` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### balanceOf

Returns the amount of tokens owned by \`account\`.

```text
  function balanceOf(
    address account
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### bptLosses

The sum of all unrecognized losses.

```text
  function bptLosses(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### cancelUnstake

Cancels an initiated unstake by resetting the calling account's unstake cooldown. It emits a \`Cooldown\` event.

```text
  function cancelUnstake(
  ) nonpayable
```

### custodyAllowance \(state variable\)

```text
  function custodyAllowance(
    address,
    address
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of StakeLockerFDTs of \`account\` that are "locked" at \`custodian\`. |

### decimals

Returns the number of decimals used to get its user representation. For example, if \`decimals\` equals \`2\`, a balance of \`505\` tokens should be displayed to a user as \`5,05\` \(\`505 / 10 \*\* 2\`\). Tokens usually opt for a value of 18, imitating the relationship between Ether and Wei. This is the value {ERC20} uses, unless {_setupDecimals} is called. NOTE: This information is only used for \_display_ purposes: it in no way affects any of the arithmetic of the contract, including {IERC20-balanceOf} and {IERC20-transfer}.

```text
  function decimals(
  ) view returns (
    uint8
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint8` | `uint8` |  |

### decreaseAllowance

Atomically decreases the allowance granted to \`spender\` by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - \`spender\` cannot be the zero address. - \`spender\` must have allowance for the caller of at least \`subtractedValue\`.

```text
  function decreaseAllowance(
    address spender,
    uint256 subtractedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `subtractedValue` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### fundsToken

The ERC-2222 Funds Token.

```text
  function fundsToken(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IERC20` |  |

### fundsTokenBalance

The amount of \`fundsToken\` \(Liquidity Asset\) currently present and accounted for in this contract.

```text
  function fundsTokenBalance(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### increaseAllowance

Atomically increases the allowance granted to \`spender\` by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - \`spender\` cannot be the zero address.

```text
  function increaseAllowance(
    address spender,
    uint256 addedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `spender` | `address` | `address` |  |
| 1 | `addedValue` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### increaseCustodyAllowance

Increases the custody allowance for a given Custodian corresponding to the account \(\`msg.sender\`\).It emits a \`CustodyAllowanceChanged\` event.It emits a \`TotalCustodyAllowanceUpdated\` event.

```text
  function increaseCustodyAllowance(
    address custodian,
    uint256 amount
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `custodian` | `address` | `address` | The address which will act as Custodian of a given amount for an account. |
| 1 | `amount` | `uint256` | `uint256` | The number of additional FDTs to be custodied by the Custodian. |

### intendToUnstake

Activates the cooldown period to unstake. It can't be called if the account is not staking. It emits a \`Cooldown\` event.

```text
  function intendToUnstake(
  ) nonpayable
```

### isReceiveAllowed

Returns if an account is allowed to receive a transfer. This is only possible if they have zero cooldown or they are past their unstake window.

```text
  function isReceiveAllowed(
    uint256 _unstakeCooldown
  ) view returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_unstakeCooldown` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### isUnstakeAllowed

Returns if the unstake cooldown period has passed for \`msg.sender\` and if they are in the unstake window.

```text
  function isUnstakeAllowed(
    address from
  ) view returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `from` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### liquidityAsset \(state variable\)

The Liquidity Asset for the Pool as well as the dividend token for StakeLockerFDT interest.

```text
  function liquidityAsset(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### lockupPeriod \(state variable\)

The number of seconds for which unstaking is not allowed.

```text
  function lockupPeriod(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lossesBalance

The amount of losses present and accounted for in this contract.

```text
  function lossesBalance(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### name

Returns the name of the token.

```text
  function name(
  ) view returns (
    string
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `string` | `string` |  |

### openStakeLockerToPublic

Sets the StakeLocker as open to the public. Only the Pool Delegate can call this function. It emits a \`StakeLockerOpened\` event.

```text
  function openStakeLockerToPublic(
  ) nonpayable
```

### openToPublic

```text
  function openToPublic(
  ) view returns (
    bool
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### pause

Triggers paused state. Halts functionality for certain functions. Only the Pool Delegate or a Pool Admin can call this function.

```text
  function pause(
  ) nonpayable
```

### paused

Returns true if the contract is paused, and false otherwise.

```text
  function paused(
  ) view returns (
    bool
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### pool \(state variable\)

The parent Pool.

```text
  function pool(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### pull

Transfers an amount of Stake Asset to a destination account. Only the Pool can call this function.

```text
  function pull(
    address dst,
    uint256 amt
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `dst` | `address` | `address` | The destination to transfer Stake Asset to. |
| 1 | `amt` | `uint256` | `uint256` | The amount of Stake Asset to transfer. |

### recognizableLossesOf

Returns the amount of losses that an account can withdraw.

```text
  function recognizableLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of losses that \`\_owner\` can withdraw. |

### recognizedLossesOf

Returns the amount of losses that an account has recognized.

```text
  function recognizedLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of losses that \`\_owner\` has recognized. |

### setAllowlist

Updates Staker status on the allowlist. Only the Pool Delegate can call this function. It emits an \`AllowListUpdated\` event.

```text
  function setAllowlist(
    address staker,
    bool status
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of the Staker to set status for. |
| 1 | `status` | `bool` | `bool` | The status of the Staker on allowlist. |

### setLockupPeriod

Sets the lockup period. Only the Pool Delegate can call this function. It emits a \`LockupPeriodUpdated\` event.

```text
  function setLockupPeriod(
    uint256 newLockupPeriod
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newLockupPeriod` | `uint256` | `uint256` | New lockup period used to restrict unstaking. |

### stake

Handles a Staker's depositing of an amount of Stake Asset, minting them StakeLockerFDTs. It emits a \`StakeDateUpdated\` event. It emits a \`Stake\` event. It emits a \`Cooldown\` event. It emits a \`BalanceUpdated\` event.

```text
  function stake(
    uint256 amt
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `amt` | `uint256` | `uint256` | The amount of Stake Asset \(BPTs\) to deposit. |

### stakeAsset \(state variable\)

The asset deposited by Stakers into this contract, for liquidation during defaults.

```text
  function stakeAsset(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IERC20` |  |

### stakeDate \(state variable\)

```text
  function stakeDate(
    address
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The effective stake date of \`account\`. |

### symbol

Returns the symbol of the token, usually a shorter version of the name.

```text
  function symbol(
  ) view returns (
    string
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `string` | `string` |  |

### totalCustodyAllowance \(state variable\)

```text
  function totalCustodyAllowance(
    address
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The total amount of StakeLockerFDTs that are "locked" for a given account, cannot be greater than balance. |

### totalSupply

Returns the amount of tokens in existence.

```text
  function totalSupply(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### transfer

Moves \`amount\` tokens from the caller's account to \`recipient\`. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```text
  function transfer(
    address recipient,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `recipient` | `address` | `address` |  |
| 1 | `amount` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### transferByCustodian

Transfers custodied StakeLockerFDTs back to the account. \`from\` and \`to\` should always be equal in this implementation. This means that the Custodian can only decrease their own allowance and unlock funds for the original owner. It emits a \`CustodyTransfer\` event. It emits a \`CustodyAllowanceChanged\` event. It emits a \`TotalCustodyAllowanceUpdated\` event.

```text
  function transferByCustodian(
    address from,
    address to,
    uint256 amount
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `from` | `address` | `address` | The address which holds the StakeLockerFDTs. |
| 1 | `to` | `address` | `address` | The address which will be the new owner of the amount of StakeLockerFDTs. |
| 2 | `amount` | `uint256` | `uint256` | The mount of StakeLockerFDTs transferred. |

### transferFrom

Moves \`amount\` tokens from \`sender\` to \`recipient\` using the allowance mechanism. \`amount\` is then deducted from the caller's allowance. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```text
  function transferFrom(
    address sender,
    address recipient,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `sender` | `address` | `address` |  |
| 1 | `recipient` | `address` | `address` |  |
| 2 | `amount` | `uint256` | `uint256` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `bool` | `bool` |  |

### unpause

Triggers unpaused state. Restores functionality for certain functions. Only the Pool Delegate or a Pool Admin can call this function.

```text
  function unpause(
  ) nonpayable
```

### unstake

Handles a Staker's withdrawing of an amount of Stake Asset, minus any losses. It also claims interest and burns StakeLockerFDTs for the calling account. It emits an \`Unstake\` event. It emits a \`BalanceUpdated\` event.

```text
  function unstake(
    uint256 amt
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `amt` | `uint256` | `uint256` | The amount of Stake Asset \(BPTs\) to withdraw. |

### unstakeCooldown \(state variable\)

```text
  function unstakeCooldown(
    address
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The timestamp of when \`account\` called \`cooldown\(\)\`. |

### updateFundsReceived

Registers a payment of funds in tokens. May be called directly after a deposit is made. Calls \_updateFundsTokenBalance\(\), whereby the contract computes the delta of the new and previous \`fundsToken\` balance and increments the total received funds \(cumulative\), by delta, by calling \_distributeFunds\(\).

```text
  function updateFundsReceived(
  ) nonpayable
```

### updateLosses

Updates loss accounting for StakeLockerFDTs after BPTs have been burned. Only the Pool can call this function.

```text
  function updateLosses(
    uint256 bptsBurned
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `bptsBurned` | `uint256` | `uint256` | The amount of BPTs that have been burned. |

### updateLossesReceived

Registers a loss. May be called directly after a shortfall after BPT burning occurs. Calls \_updateLossesTokenBalance\(\), whereby the contract computes the delta of the new and previous losses balance and increments the total losses \(cumulative\), by delta, by calling \_distributeLosses\(\).

```text
  function updateLossesReceived(
  ) nonpayable
```

### withdrawFunds

Withdraws all claimable interest earned from the StakeLocker for an account. It emits a \`BalanceUpdated\` event if there are withdrawable funds.

```text
  function withdrawFunds(
  ) nonpayable
```

### withdrawableFundsOf

Returns the amount of funds that an account can withdraw.

```text
  function withdrawableFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of some FDT holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount funds that \`\_owner\` can withdraw. |

### withdrawnFundsOf

Returns the amount of funds that an account has withdrawn.

```text
  function withdrawnFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_owner` | `address` | `address` | The address of a token holder. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The amount of funds that \`\_owner\` has withdrawn. |

## Events

### AllowListUpdated

Emits an event indicating that the ability of \`staker\` to stake before the locker is open to the public, has changed.

```text
  event AllowListUpdated(
    address staker,
    bool status
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of some account. |
| 1 | `status` | `bool` | `bool` | Whether \`staker\` can stake before the locker is open to the public. |

### Approval

```text
  event Approval(
    address owner,
    address spender,
    uint256 value
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `owner` | `address` | `address` |  |
| 1 | `spender` | `address` | `address` |  |
| 2 | `value` | `uint256` | `uint256` |  |

### BalanceUpdated

Emits an event indicating some Balance was updated.

```text
  event BalanceUpdated(
    address staker,
    address token,
    uint256 balance
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of a Staker. |
| 1 | `token` | `address` | `address` | The address of the token for which the balance of \`staker\` changed. |
| 2 | `balance` | `uint256` | `uint256` | The new balance for \`staker\`. |

### Cooldown

Emits an event indicating that the cooldown timestamp for a staker has changed.

```text
  event Cooldown(
    address staker,
    uint256 cooldown
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of a Staker. |
| 1 | `cooldown` | `uint256` | `uint256` | The new cooldown timestamp for \`staker\`. |

### CustodyAllowanceChanged

Emits an event indicating that the amount being custodied by a Custodian, on behalf of a Staker, has changed.

```text
  event CustodyAllowanceChanged(
    address staker,
    address custodian,
    uint256 oldAllowance,
    uint256 newAllowance
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of a Staker. |
| 1 | `custodian` | `address` | `address` | The address of a Custodian. |
| 2 | `oldAllowance` | `uint256` | `uint256` | The old amount of StakeLockerFDTs \`custodian\` had custodied on behalf of \`staker\`. |
| 3 | `newAllowance` | `uint256` | `uint256` | The new amount of StakeLockerFDTs \`custodian\` has custodied on behalf of \`staker\`. |

### CustodyTransfer

Emits an event indicating that a Custodian transferred some StakeLockerFDTs for purposes of custody.

```text
  event CustodyTransfer(
    address custodian,
    address from,
    address to,
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `custodian` | `address` | `address` | The address of the Custodian initiating the transfer. |
| 1 | `from` | `address` | `address` | The account that owns the StakeLockerFDTs. |
| 2 | `to` | `address` | `address` | The address of a Custodian taking custody of the amount. |
| 3 | `amount` | `uint256` | `uint256` | The amount of StakeLockerFDTs being re-custodied. |

### FundsDistributed

```text
  event FundsDistributed(
    address by,
    uint256 fundsDistributed
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `by` | `address` | `address` |  |
| 1 | `fundsDistributed` | `uint256` | `uint256` |  |

### FundsWithdrawn

```text
  event FundsWithdrawn(
    address by,
    uint256 fundsWithdrawn,
    uint256 totalWithdrawn
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `by` | `address` | `address` |  |
| 1 | `fundsWithdrawn` | `uint256` | `uint256` |  |
| 2 | `totalWithdrawn` | `uint256` | `uint256` |  |

### LockupPeriodUpdated

Emits an event indicating that the stake lockup period has changed.

```text
  event LockupPeriodUpdated(
    uint256 lockupPeriod
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `lockupPeriod` | `uint256` | `uint256` | The new stake lockup period. |

### LossesCorrectionUpdated

```text
  event LossesCorrectionUpdated(
    address ,
    int256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `int256` | `int256` |  |

### LossesDistributed

```text
  event LossesDistributed(
    address ,
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `uint256` | `uint256` |  |

### LossesPerShareUpdated

```text
  event LossesPerShareUpdated(
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `uint256` | `uint256` |  |

### LossesRecognized

```text
  event LossesRecognized(
    address ,
    uint256 ,
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `uint256` | `uint256` |  |
| 2 | \`\` | `uint256` | `uint256` |  |

### Paused

```text
  event Paused(
    address account
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` |  |

### PointsCorrectionUpdated

```text
  event PointsCorrectionUpdated(
    address ,
    int256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `address` | `address` |  |
| 1 | \`\` | `int256` | `int256` |  |

### PointsPerShareUpdated

```text
  event PointsPerShareUpdated(
    uint256 
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | \`\` | `uint256` | `uint256` |  |

### Stake

Emits an event indicating \`staker\` has added \`amount\` to the total they have staked.

```text
  event Stake(
    address staker,
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of a Staker. |
| 1 | `amount` | `uint256` | `uint256` | The additional amount staked. |

### StakeDateUpdated

Emits an event indicating a that a Staker's effective stake date has changed.

```text
  event StakeDateUpdated(
    address staker,
    uint256 stakeDate
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of a Staker. |
| 1 | `stakeDate` | `uint256` | `uint256` | The new effective stake date. |

### StakeLockerOpened

Emits an event indicating that the Stake Locker is now open to the public.

```text
  event StakeLockerOpened(
  )
```

### TotalCustodyAllowanceUpdated

Emits an event indicating that the total amount of StakeLockerFDTs custodied, on behalf of a Staker, by all custodians, has changed.

```text
  event TotalCustodyAllowanceUpdated(
    address staker,
    uint256 newTotalAllowance
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of a Staker. |
| 1 | `newTotalAllowance` | `uint256` | `uint256` | The total amount of StakeLockerFDTs custodied, on behalf of \`staker\`, by all custodians. |

### Transfer

```text
  event Transfer(
    address from,
    address to,
    uint256 value
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `from` | `address` | `address` |  |
| 1 | `to` | `address` | `address` |  |
| 2 | `value` | `uint256` | `uint256` |  |

### Unpaused

```text
  event Unpaused(
    address account
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` |  |

### Unstake

Emits an event indicating \`staker\` has removed \`amount\` from the total they have staked.

```text
  event Unstake(
    address staker,
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `staker` | `address` | `address` | The address of a Staker. |
| 1 | `amount` | `uint256` | `uint256` | The amount unstaked. |

