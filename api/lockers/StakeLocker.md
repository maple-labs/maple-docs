# StakeLocker

StakeLocker holds custody of stakeAsset tokens for a given Pool and earns revenue from interest.

## Constructor




```solidity
  constructor(
    address _stakeAsset,
    address _liquidityAsset,
    address _pool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_stakeAsset` | `address` | `address` | 
| 1 | `_liquidityAsset` | `address` | `address` | 
| 2 | `_pool` | `address` | `address` | 



## Functions

### accumulativeFundsOf 

Returns the amount of funds that an account has earned in total. accumulativeFundsOf(_owner) &#x3D; withdrawableFundsOf(_owner) + withdrawnFundsOf(_owner)  &#x3D; (pointsPerShare * balanceOf(_owner) + pointsCorrection[_owner]) / pointsMultiplier 

```solidity
  function accumulativeFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of funds that &#x60;_owner&#x60; has earned in total.


### accumulativeLossesOf 

Returns the amount of losses that an account has earned in total. accumulativeLossesOf(_owner) &#x3D; recognizableLossesOf(_owner) + recognizedLossesOf(_owner)  &#x3D; (lossesPerShare * balanceOf(_owner) + lossesCorrection[_owner]) / pointsMultiplier 

```solidity
  function accumulativeLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of losses that &#x60;_owner&#x60; has earned in total.


### allowance 

Returns the remaining number of tokens that &#x60;spender&#x60; will be allowed to spend on behalf of &#x60;owner&#x60; through {transferFrom}. This is zero by default. This value changes when {approve} or {transferFrom} are called.

```solidity
  function allowance(
    address owner,
    address spender
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | 
| 1 | `spender` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### allowed (state variable)



```solidity
  function allowed(
    address
  ) view returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | Whether &#x60;account&#x60; is allowed.


### approve 

Sets &#x60;amount&#x60; as the allowance of &#x60;spender&#x60; over the caller&#x27;s tokens. Returns a boolean value indicating whether the operation succeeded. IMPORTANT: Beware that changing an allowance with this method brings the risk that someone may use both the old and the new allowance by unfortunate transaction ordering. One possible solution to mitigate this race condition is to first reduce the spender&#x27;s allowance to 0 and set the desired value afterwards: https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729 Emits an {Approval} event.

```solidity
  function approve(
    address spender,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` | 
| 1 | `amount` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### balanceOf 

Returns the amount of tokens owned by &#x60;account&#x60;.

```solidity
  function balanceOf(
    address account
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### bptLosses 

The sum of all unrecognized losses.

```solidity
  function bptLosses(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### cancelUnstake 

Cancels an initiated unstake by resetting the calling account&#x27;s unstake cooldown. It emits a &#x60;Cooldown&#x60; event. 

```solidity
  function cancelUnstake(
  ) nonpayable
```



### custodyAllowance (state variable)



```solidity
  function custodyAllowance(
    address,
    address
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 
| 1 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of StakeLockerFDTs of &#x60;account&#x60; that are &quot;locked&quot; at &#x60;custodian&#x60;.


### decimals 

Returns the number of decimals used to get its user representation. For example, if &#x60;decimals&#x60; equals &#x60;2&#x60;, a balance of &#x60;505&#x60; tokens should be displayed to a user as &#x60;5,05&#x60; (&#x60;505 / 10 ** 2&#x60;). Tokens usually opt for a value of 18, imitating the relationship between Ether and Wei. This is the value {ERC20} uses, unless {_setupDecimals} is called. NOTE: This information is only used for _display_ purposes: it in no way affects any of the arithmetic of the contract, including {IERC20-balanceOf} and {IERC20-transfer}.

```solidity
  function decimals(
  ) view returns (
    uint8
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `uint8` | 


### decreaseAllowance 

Atomically decreases the allowance granted to &#x60;spender&#x60; by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - &#x60;spender&#x60; cannot be the zero address. - &#x60;spender&#x60; must have allowance for the caller of at least &#x60;subtractedValue&#x60;.

```solidity
  function decreaseAllowance(
    address spender,
    uint256 subtractedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` | 
| 1 | `subtractedValue` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### fundsToken 

The ERC-2222 Funds Token.

```solidity
  function fundsToken(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `contract IERC20` | 


### fundsTokenBalance 

The amount of &#x60;fundsToken&#x60; (Liquidity Asset) currently present and accounted for in this contract.

```solidity
  function fundsTokenBalance(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### increaseAllowance 

Atomically increases the allowance granted to &#x60;spender&#x60; by the caller. This is an alternative to {approve} that can be used as a mitigation for problems described in {IERC20-approve}. Emits an {Approval} event indicating the updated allowance. Requirements: - &#x60;spender&#x60; cannot be the zero address.

```solidity
  function increaseAllowance(
    address spender,
    uint256 addedValue
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `spender` | `address` | `address` | 
| 1 | `addedValue` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### increaseCustodyAllowance 

Increases the custody allowance for a given Custodian corresponding to the account (&#x60;msg.sender&#x60;).It emits a &#x60;CustodyAllowanceChanged&#x60; event.It emits a &#x60;TotalCustodyAllowanceUpdated&#x60; event.

```solidity
  function increaseCustodyAllowance(
    address custodian,
    uint256 amount
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `custodian` | `address` | `address` | The address which will act as Custodian of a given amount for an account.
| 1 | `amount` | `uint256` | `uint256` | The number of additional FDTs to be custodied by the Custodian.


### intendToUnstake 

Activates the cooldown period to unstake. It can&#x27;t be called if the account is not staking. It emits a &#x60;Cooldown&#x60; event. 

```solidity
  function intendToUnstake(
  ) nonpayable
```



### isReceiveAllowed 

Returns if an account is allowed to receive a transfer. This is only possible if they have zero cooldown or they are past their unstake window. 

```solidity
  function isReceiveAllowed(
    uint256 _unstakeCooldown
  ) view returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_unstakeCooldown` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### isUnstakeAllowed 

Returns if the unstake cooldown period has passed for &#x60;msg.sender&#x60; and if they are in the unstake window.

```solidity
  function isUnstakeAllowed(
    address from
  ) view returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### liquidityAsset (state variable)

The Liquidity Asset for the Pool as well as the dividend token for StakeLockerFDT interest.

```solidity
  function liquidityAsset(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### lockupPeriod (state variable)

The number of seconds for which unstaking is not allowed.

```solidity
  function lockupPeriod(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### lossesBalance 

The amount of losses present and accounted for in this contract.

```solidity
  function lossesBalance(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### name 

Returns the name of the token.

```solidity
  function name(
  ) view returns (
    string
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` | 


### openStakeLockerToPublic 

Sets the StakeLocker as open to the public. Only the Pool Delegate can call this function. It emits a &#x60;StakeLockerOpened&#x60; event. 

```solidity
  function openStakeLockerToPublic(
  ) nonpayable
```



### openToPublic 



```solidity
  function openToPublic(
  ) view returns (
    bool
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### pause 

Triggers paused state. Halts functionality for certain functions. Only the Pool Delegate or a Pool Admin can call this function. 

```solidity
  function pause(
  ) nonpayable
```



### paused 

Returns true if the contract is paused, and false otherwise.

```solidity
  function paused(
  ) view returns (
    bool
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### pool (state variable)

The parent Pool.

```solidity
  function pool(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `address` | 


### pull 

Transfers an amount of Stake Asset to a destination account. Only the Pool can call this function. 

```solidity
  function pull(
    address dst,
    uint256 amt
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `dst` | `address` | `address` | The destination to transfer Stake Asset to.
| 1 | `amt` | `uint256` | `uint256` | The amount of Stake Asset to transfer.


### recognizableLossesOf 

Returns the amount of losses that an account can withdraw.

```solidity
  function recognizableLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of losses that &#x60;_owner&#x60; can withdraw.


### recognizedLossesOf 

Returns the amount of losses that an account has recognized.

```solidity
  function recognizedLossesOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of losses that &#x60;_owner&#x60; has recognized.


### setAllowlist 

Updates Staker status on the allowlist. Only the Pool Delegate can call this function. It emits an &#x60;AllowListUpdated&#x60; event. 

```solidity
  function setAllowlist(
    address staker,
    bool status
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of the Staker to set status for.
| 1 | `status` | `bool` | `bool` | The status of the Staker on allowlist.


### setLockupPeriod 

Sets the lockup period. Only the Pool Delegate can call this function. It emits a &#x60;LockupPeriodUpdated&#x60; event. 

```solidity
  function setLockupPeriod(
    uint256 newLockupPeriod
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newLockupPeriod` | `uint256` | `uint256` | New lockup period used to restrict unstaking.


### stake 

Handles a Staker&#x27;s depositing of an amount of Stake Asset, minting them StakeLockerFDTs. It emits a &#x60;StakeDateUpdated&#x60; event. It emits a &#x60;Stake&#x60; event. It emits a &#x60;Cooldown&#x60; event. It emits a &#x60;BalanceUpdated&#x60; event. 

```solidity
  function stake(
    uint256 amt
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | The amount of Stake Asset (BPTs) to deposit.


### stakeAsset (state variable)

The asset deposited by Stakers into this contract, for liquidation during defaults.

```solidity
  function stakeAsset(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `address` | `contract IERC20` | 


### stakeDate (state variable)



```solidity
  function stakeDate(
    address
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The effective stake date of &#x60;account&#x60;.


### symbol 

Returns the symbol of the token, usually a shorter version of the name.

```solidity
  function symbol(
  ) view returns (
    string
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `string` | `string` | 


### totalCustodyAllowance (state variable)



```solidity
  function totalCustodyAllowance(
    address
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The total amount of StakeLockerFDTs that are &quot;locked&quot; for a given account, cannot be greater than balance.


### totalSupply 

Returns the amount of tokens in existence.

```solidity
  function totalSupply(
  ) view returns (
    uint256
  )
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | 


### transfer 

Moves &#x60;amount&#x60; tokens from the caller&#x27;s account to &#x60;recipient&#x60;. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```solidity
  function transfer(
    address recipient,
    uint256 amount
  ) nonpayable returns (
    bool
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `recipient` | `address` | `address` | 
| 1 | `amount` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### transferByCustodian 

Transfers custodied StakeLockerFDTs back to the account. &#x60;from&#x60; and &#x60;to&#x60; should always be equal in this implementation. This means that the Custodian can only decrease their own allowance and unlock funds for the original owner. It emits a &#x60;CustodyTransfer&#x60; event. It emits a &#x60;CustodyAllowanceChanged&#x60; event. It emits a &#x60;TotalCustodyAllowanceUpdated&#x60; event. 

```solidity
  function transferByCustodian(
    address from,
    address to,
    uint256 amount
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` | The address which holds the StakeLockerFDTs.
| 1 | `to` | `address` | `address` | The address which will be the new owner of the amount of StakeLockerFDTs.
| 2 | `amount` | `uint256` | `uint256` | The mount of StakeLockerFDTs transferred.


### transferFrom 

Moves &#x60;amount&#x60; tokens from &#x60;sender&#x60; to &#x60;recipient&#x60; using the allowance mechanism. &#x60;amount&#x60; is then deducted from the caller&#x27;s allowance. Returns a boolean value indicating whether the operation succeeded. Emits a {Transfer} event.

```solidity
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
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `sender` | `address` | `address` | 
| 1 | `recipient` | `address` | `address` | 
| 2 | `amount` | `uint256` | `uint256` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` | 


### unpause 

Triggers unpaused state. Restores functionality for certain functions. Only the Pool Delegate or a Pool Admin can call this function.

```solidity
  function unpause(
  ) nonpayable
```



### unstake 

Handles a Staker&#x27;s withdrawing of an amount of Stake Asset, minus any losses. It also claims interest and burns StakeLockerFDTs for the calling account. It emits an &#x60;Unstake&#x60; event. It emits a &#x60;BalanceUpdated&#x60; event. 

```solidity
  function unstake(
    uint256 amt
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amt` | `uint256` | `uint256` | The amount of Stake Asset (BPTs) to withdraw.


### unstakeCooldown (state variable)



```solidity
  function unstakeCooldown(
    address
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The timestamp of when &#x60;account&#x60; called &#x60;cooldown()&#x60;.


### updateFundsReceived 

Registers a payment of funds in tokens. May be called directly after a deposit is made. Calls _updateFundsTokenBalance(), whereby the contract computes the delta of the new and previous  &#x60;fundsToken&#x60; balance and increments the total received funds (cumulative), by delta, by calling _distributeFunds().

```solidity
  function updateFundsReceived(
  ) nonpayable
```



### updateLosses 

Updates loss accounting for StakeLockerFDTs after BPTs have been burned. Only the Pool can call this function. 

```solidity
  function updateLosses(
    uint256 bptsBurned
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `bptsBurned` | `uint256` | `uint256` | The amount of BPTs that have been burned.


### updateLossesReceived 

Registers a loss. May be called directly after a shortfall after BPT burning occurs. Calls _updateLossesTokenBalance(), whereby the contract computes the delta of the new and previous  losses balance and increments the total losses (cumulative), by delta, by calling _distributeLosses(). 

```solidity
  function updateLossesReceived(
  ) nonpayable
```



### withdrawFunds 

Withdraws all claimable interest earned from the StakeLocker for an account. It emits a &#x60;BalanceUpdated&#x60; event if there are withdrawable funds. 

```solidity
  function withdrawFunds(
  ) nonpayable
```



### withdrawableFundsOf 

Returns the amount of funds that an account can withdraw.

```solidity
  function withdrawableFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of some FDT holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount funds that &#x60;_owner&#x60; can withdraw.


### withdrawnFundsOf 

Returns the amount of funds that an account has withdrawn.

```solidity
  function withdrawnFundsOf(
    address _owner
  ) view returns (
    uint256
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_owner` | `address` | `address` | The address of a token holder.


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The amount of funds that &#x60;_owner&#x60; has withdrawn.



## Events

### AllowListUpdated

Emits an event indicating that the ability of &#x60;staker&#x60; to stake before the locker is open to the public, has changed.
```solidity
  event AllowListUpdated(
    address staker,
    bool status
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of some account.
| 1 | `status` | `bool` | `bool` | Whether &#x60;staker&#x60; can stake before the locker is open to the public.

### Approval


```solidity
  event Approval(
    address owner,
    address spender,
    uint256 value
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner` | `address` | `address` | 
| 1 | `spender` | `address` | `address` | 
| 2 | `value` | `uint256` | `uint256` | 

### BalanceUpdated

Emits an event indicating some Balance was updated.
```solidity
  event BalanceUpdated(
    address staker,
    address token,
    uint256 balance
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of a Staker.
| 1 | `token` | `address` | `address` | The address of the token for which the balance of &#x60;staker&#x60; changed.
| 2 | `balance` | `uint256` | `uint256` | The new balance for &#x60;staker&#x60;.

### Cooldown

Emits an event indicating that the cooldown timestamp for a staker has changed.
```solidity
  event Cooldown(
    address staker,
    uint256 cooldown
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of a Staker.
| 1 | `cooldown` | `uint256` | `uint256` | The new cooldown timestamp for &#x60;staker&#x60;.

### CustodyAllowanceChanged

Emits an event indicating that the amount being custodied by a Custodian, on behalf of a Staker, has changed.
```solidity
  event CustodyAllowanceChanged(
    address staker,
    address custodian,
    uint256 oldAllowance,
    uint256 newAllowance
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of a Staker.
| 1 | `custodian` | `address` | `address` | The address of a Custodian.
| 2 | `oldAllowance` | `uint256` | `uint256` | The old amount of StakeLockerFDTs &#x60;custodian&#x60; had custodied on behalf of &#x60;staker&#x60;.
| 3 | `newAllowance` | `uint256` | `uint256` | The new amount of StakeLockerFDTs &#x60;custodian&#x60; has custodied on behalf of &#x60;staker&#x60;.

### CustodyTransfer

Emits an event indicating that a Custodian transferred some StakeLockerFDTs for purposes of custody.
```solidity
  event CustodyTransfer(
    address custodian,
    address from,
    address to,
    uint256 amount
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `custodian` | `address` | `address` | The address of the Custodian initiating the transfer.
| 1 | `from` | `address` | `address` | The account that owns the StakeLockerFDTs.
| 2 | `to` | `address` | `address` | The address of a Custodian taking custody of the amount.
| 3 | `amount` | `uint256` | `uint256` | The amount of StakeLockerFDTs being re-custodied.

### FundsDistributed


```solidity
  event FundsDistributed(
    address by,
    uint256 fundsDistributed
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `by` | `address` | `address` | 
| 1 | `fundsDistributed` | `uint256` | `uint256` | 

### FundsWithdrawn


```solidity
  event FundsWithdrawn(
    address by,
    uint256 fundsWithdrawn,
    uint256 totalWithdrawn
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `by` | `address` | `address` | 
| 1 | `fundsWithdrawn` | `uint256` | `uint256` | 
| 2 | `totalWithdrawn` | `uint256` | `uint256` | 

### LockupPeriodUpdated

Emits an event indicating that the stake lockup period has changed.
```solidity
  event LockupPeriodUpdated(
    uint256 lockupPeriod
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lockupPeriod` | `uint256` | `uint256` | The new stake lockup period.

### LossesCorrectionUpdated


```solidity
  event LossesCorrectionUpdated(
    address ,
    int256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 
| 1 | `` | `int256` | `int256` | 

### LossesDistributed


```solidity
  event LossesDistributed(
    address ,
    uint256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 
| 1 | `` | `uint256` | `uint256` | 

### LossesPerShareUpdated


```solidity
  event LossesPerShareUpdated(
    uint256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` | 

### LossesRecognized


```solidity
  event LossesRecognized(
    address ,
    uint256 ,
    uint256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 
| 1 | `` | `uint256` | `uint256` | 
| 2 | `` | `uint256` | `uint256` | 

### Paused


```solidity
  event Paused(
    address account
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | 

### PointsCorrectionUpdated


```solidity
  event PointsCorrectionUpdated(
    address ,
    int256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` | 
| 1 | `` | `int256` | `int256` | 

### PointsPerShareUpdated


```solidity
  event PointsPerShareUpdated(
    uint256 
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `uint256` | `uint256` | 

### Stake

Emits an event indicating &#x60;staker&#x60; has added &#x60;amount&#x60; to the total they have staked.
```solidity
  event Stake(
    address staker,
    uint256 amount
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of a Staker.
| 1 | `amount` | `uint256` | `uint256` | The additional amount staked.

### StakeDateUpdated

Emits an event indicating a that a Staker&#x27;s effective stake date has changed.
```solidity
  event StakeDateUpdated(
    address staker,
    uint256 stakeDate
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of a Staker.
| 1 | `stakeDate` | `uint256` | `uint256` | The new effective stake date.

### StakeLockerOpened

Emits an event indicating that the Stake Locker is now open to the public.
```solidity
  event StakeLockerOpened(
  )
```


### TotalCustodyAllowanceUpdated

Emits an event indicating that the total amount of StakeLockerFDTs custodied, on behalf of a Staker, by all custodians, has changed.
```solidity
  event TotalCustodyAllowanceUpdated(
    address staker,
    uint256 newTotalAllowance
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of a Staker.
| 1 | `newTotalAllowance` | `uint256` | `uint256` | The total amount of StakeLockerFDTs custodied, on behalf of &#x60;staker&#x60;, by all custodians.

### Transfer


```solidity
  event Transfer(
    address from,
    address to,
    uint256 value
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `from` | `address` | `address` | 
| 1 | `to` | `address` | `address` | 
| 2 | `value` | `uint256` | `uint256` | 

### Unpaused


```solidity
  event Unpaused(
    address account
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | 

### Unstake

Emits an event indicating &#x60;staker&#x60; has removed &#x60;amount&#x60; from the total they have staked.
```solidity
  event Unstake(
    address staker,
    uint256 amount
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `staker` | `address` | `address` | The address of a Staker.
| 1 | `amount` | `uint256` | `uint256` | The amount unstaked.

