# MPL Rewards

MplRewards Synthetix farming contract fork for liquidity mining.

## Constructor

```text
  constructor(
    address _rewardsToken,
    address _stakingToken,
    address _owner
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_rewardsToken` | `address` | `address` |  |
| 1 | `_stakingToken` | `address` | `address` |  |
| 2 | `_owner` | `address` | `address` |  |

## Functions

### balanceOf

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
| 0 | `account` | `address` | `address` | The address of an account. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The balance of \`account\`. |

### earned

```text
  function earned(
    address account
  ) view returns (
    uint256
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` | The address of an account. |

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The rewards earned of \`account\`. |

### exit

Withdraw the entire balance and get the reward.

```text
  function exit(
  ) nonpayable
```

### getReward

It emits a \`RewardPaid\` event if any rewards are received.

```text
  function getReward(
  ) nonpayable
```

### getRewardForDuration

```text
  function getRewardForDuration(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The reward for a duration. |

### lastPauseTime \(state variable\)

The last pause time.

```text
  function lastPauseTime(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### lastTimeRewardApplicable

```text
  function lastTimeRewardApplicable(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The last time rewards were applicable. |

### lastUpdateTime \(state variable\)

The last update time.

```text
  function lastUpdateTime(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### notifyRewardAmount

Only the contract Owner may call this. It emits a \`RewardAdded\` event.

```text
  function notifyRewardAmount(
    uint256 reward
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `reward` | `uint256` | `uint256` | A reward amount. |

### owner

Returns the address of the current owner.

```text
  function owner(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `address` |  |

### paused \(state variable\)

Whether the contract is paused.

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

### periodFinish \(state variable\)

The period finish.

```text
  function periodFinish(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### recoverERC20

Added to support recovering tokens unintentionally sent to this contract. Only the contract Owner may call this. It emits a \`Recovered\` event.

```text
  function recoverERC20(
    address tokenAddress,
    uint256 tokenAmount
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `tokenAddress` | `address` | `address` | The address of a token to recover. |
| 1 | `tokenAmount` | `uint256` | `uint256` | The amount to recover. |

### renounceOwnership

Leaves the contract without owner. It will not be possible to call \`onlyOwner\` functions anymore. Can only be called by the current owner. NOTE: Renouncing ownership will leave the contract without an owner, thereby removing any functionality that is only available to the owner.

```text
  function renounceOwnership(
  ) nonpayable
```

### rewardPerToken

```text
  function rewardPerToken(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The reward per token. |

### rewardPerTokenStored \(state variable\)

The reward per token stored.

```text
  function rewardPerTokenStored(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### rewardRate \(state variable\)

The rewards rate.

```text
  function rewardRate(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### rewards \(state variable\)

```text
  function rewards(
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
| 0 |  | `uint256` | `uint256` | The rewards \`account\`. |

### rewardsDuration \(state variable\)

The rewards duration.

```text
  function rewardsDuration(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` |  |

### rewardsToken \(state variable\)

The rewards token.

```text
  function rewardsToken(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IERC20` |  |

### setPaused

Change the paused state of the contract. Only the contract Owner may call this. It emits a \`PauseChanged\` event.

```text
  function setPaused(
    bool _paused
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_paused` | `bool` | `bool` | Whether to pause the contract. |

### setRewardsDuration

Only the contract Owner may call this. It emits a \`RewardsDurationUpdated\` event.

```text
  function setRewardsDuration(
    uint256 _rewardsDuration
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `_rewardsDuration` | `uint256` | `uint256` | The new duration for rewards. |

### stake

It emits a \`Staked\` event.

```text
  function stake(
    uint256 amount
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `amount` | `uint256` | `uint256` | An amount to stake. |

### stakingToken \(state variable\)

The staking token.

```text
  function stakingToken(
  ) view returns (
    address
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `address` | `contract IERC2258` |  |

### totalSupply

```text
  function totalSupply(
  ) view returns (
    uint256
  )
```

#### Return Values:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 |  | `uint256` | `uint256` | The total supply. |

### transferOwnership

Transfers ownership of the contract to a new account \(\`newOwner\`\). Can only be called by the current owner.

```text
  function transferOwnership(
    address newOwner
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newOwner` | `address` | `address` |  |

### updatePeriodFinish

End rewards emission earlier. Only the contract Owner may call this.

```text
  function updatePeriodFinish(
    uint256 timestamp
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `timestamp` | `uint256` | `uint256` | A unix timestamp to finish rewards. |

### userRewardPerTokenPaid \(state variable\)

```text
  function userRewardPerTokenPaid(
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
| 0 |  | `uint256` | `uint256` | The reward per token paid for \`account\`. |

### withdraw

It emits a \`Withdrawn\` event.

```text
  function withdraw(
    uint256 amount
  ) nonpayable
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `amount` | `uint256` | `uint256` | An amount to withdraw. |

## Events

### OwnershipTransferred

```text
  event OwnershipTransferred(
    address previousOwner,
    address newOwner
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `previousOwner` | `address` | `address` |  |
| 1 | `newOwner` | `address` | `address` |  |

### PauseChanged

Emits an event indicating that pause state has changed.

```text
  event PauseChanged(
    bool isPaused
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `isPaused` | `bool` | `bool` | Whether the contract is paused. |

### Recovered

Emits an event indicating that some token was recovered.

```text
  event Recovered(
    address token,
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `token` | `address` | `address` | The address of the token recovered. |
| 1 | `amount` | `uint256` | `uint256` | The amount recovered. |

### RewardAdded

Emits an event indicating that a reward was added.

```text
  event RewardAdded(
    uint256 reward
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `reward` | `uint256` | `uint256` | The amount of the added reward. |

### RewardPaid

Emits an event indicating that some reward was paid to an account.

```text
  event RewardPaid(
    address account,
    uint256 reward
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` | The address of the account rewarded. |
| 1 | `reward` | `uint256` | `uint256` | The amount rewarded to \`account\`. |

### RewardsDurationUpdated

Emits an event indicating that the duration of the ward period has updated.

```text
  event RewardsDurationUpdated(
    uint256 newDuration
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `newDuration` | `uint256` | `uint256` | The new duration of the rewards. |

### Staked

Emits an event indicating that an account has staked.

```text
  event Staked(
    address account,
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` | The address of the account. |
| 1 | `amount` | `uint256` | `uint256` | The amount staked. |

### Withdrawn

Emits an event indicating that reward was withdrawn.

```text
  event Withdrawn(
    address account,
    uint256 amount
  )
```

#### Parameters:

| Index | Name | Type | Internal Type | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | `account` | `address` | `address` | The address of the account. |
| 1 | `amount` | `uint256` | `uint256` | The amount withdrawn. |

