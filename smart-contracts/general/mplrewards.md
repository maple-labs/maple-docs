# MplRewards

MplRewards Synthetix farming contract fork for liquidity mining.

<br />

## Constructor




```solidity
    constructor(
        address _rewardsToken,
        address _stakingToken,
        address _owner
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_rewardsToken` | `address` | `address` |  |
| 1 | `_stakingToken` | `address` | `address` |  |
| 2 | `_owner` | `address` | `address` |  |


<br />


## Functions

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
| 0 | `account` | `address` | `address` | The address of an account. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The balance of &#x60;account&#x60;. |


<br />

### `earned`



```solidity
    function earned(
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
| 0 |  | `uint256` | `uint256` | The rewards earned of &#x60;account&#x60;. |


<br />

### `exit`

Withdraw the entire balance and get the reward.

```solidity
    function exit()
        nonpayable;
```



<br />

### `getReward`

It emits a &#x60;RewardPaid&#x60; event if any rewards are received.

```solidity
    function getReward()
        nonpayable;
```



<br />

### `getRewardForDuration`



```solidity
    function getRewardForDuration()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The reward for a duration. |


<br />

### `lastPauseTime` _[state variable]_

The last pause time.

```solidity
    function lastPauseTime()
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

### `lastTimeRewardApplicable`



```solidity
    function lastTimeRewardApplicable()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The last time rewards were applicable. |


<br />

### `lastUpdateTime` _[state variable]_

The last update time.

```solidity
    function lastUpdateTime()
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

### `notifyRewardAmount`

Only the contract Owner may call this. It emits a &#x60;RewardAdded&#x60; event.

```solidity
    function notifyRewardAmount(
        uint256 reward
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `reward` | `uint256` | `uint256` | A reward amount. |


<br />

### `paused` _[state variable]_

Whether the contract is paused.

```solidity
    function paused()
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

### `periodFinish` _[state variable]_

The period finish.

```solidity
    function periodFinish()
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

### `recoverERC20`

Added to support recovering tokens unintentionally sent to this contract. Only the contract Owner may call this. It emits a &#x60;Recovered&#x60; event.

```solidity
    function recoverERC20(
        address tokenAddress,
        uint256 tokenAmount
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `tokenAddress` | `address` | `address` | The address of a token to recover. |
| 1 | `tokenAmount` | `uint256` | `uint256` | The amount to recover. |


<br />

### `rewardPerToken`



```solidity
    function rewardPerToken()
        view
        returns (
            uint256
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` | The reward per token. |


<br />

### `rewardPerTokenStored` _[state variable]_

The reward per token stored.

```solidity
    function rewardPerTokenStored()
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

### `rewardRate` _[state variable]_

The rewards rate.

```solidity
    function rewardRate()
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

### `rewards` _[state variable]_



```solidity
    function rewards(
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
| 0 |  | `uint256` | `uint256` | The rewards &#x60;account&#x60;. |


<br />

### `rewardsDuration` _[state variable]_

The rewards duration.

```solidity
    function rewardsDuration()
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

### `rewardsToken` _[state variable]_

The rewards token.

```solidity
    function rewardsToken()
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

### `setPaused`

Change the paused state of the contract. Only the contract Owner may call this. It emits a &#x60;PauseChanged&#x60; event.

```solidity
    function setPaused(
        bool _paused
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_paused` | `bool` | `bool` | Whether to pause the contract. |


<br />

### `setRewardsDuration`

Only the contract Owner may call this. It emits a &#x60;RewardsDurationUpdated&#x60; event.

```solidity
    function setRewardsDuration(
        uint256 _rewardsDuration
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_rewardsDuration` | `uint256` | `uint256` | The new duration for rewards. |


<br />

### `stake`

It emits a &#x60;Staked&#x60; event.

```solidity
    function stake(
        uint256 amount
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount` | `uint256` | `uint256` | An amount to stake. |


<br />

### `stakingToken` _[state variable]_

The staking token.

```solidity
    function stakingToken()
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
| 0 |  | `uint256` | `uint256` | The total supply. |


<br />

### `updatePeriodFinish`

End rewards emission earlier. Only the contract Owner may call this.

```solidity
    function updatePeriodFinish(
        uint256 timestamp
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `timestamp` | `uint256` | `uint256` | A unix timestamp to finish rewards. |


<br />

### `userRewardPerTokenPaid` _[state variable]_



```solidity
    function userRewardPerTokenPaid(
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
| 0 |  | `uint256` | `uint256` | The reward per token paid for &#x60;account&#x60;. |


<br />

### `withdraw`

It emits a &#x60;Withdrawn&#x60; event.

```solidity
    function withdraw(
        uint256 amount
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount` | `uint256` | `uint256` | An amount to withdraw. |


<br />

### `owner`

Returns the address of the current owner.

```solidity
    function owner()
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

### `renounceOwnership`

Leaves the contract without owner. It will not be possible to call &#x60;onlyOwner&#x60; functions anymore. Can only be called by the current owner. NOTE: Renouncing ownership will leave the contract without an owner, thereby removing any functionality that is only available to the owner.

```solidity
    function renounceOwnership()
        nonpayable;
```



<br />

### `transferOwnership`

Transfers ownership of the contract to a new account (&#x60;newOwner&#x60;). Can only be called by the current owner.

```solidity
    function transferOwnership(
        address newOwner
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newOwner` | `address` | `address` |  |


<br />


## Events

### `PauseChanged`

Emits an event indicating that pause state has changed.

```solidity
    event PauseChanged(
        bool isPaused
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isPaused` | `bool` | `bool` | Whether the contract is paused. |

<br />

### `Recovered`

Emits an event indicating that some token was recovered.

```solidity
    event Recovered(
        address token,
        uint256 amount
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `token` | `address` | `address` | The address of the token recovered. |
| 1 | `amount` | `uint256` | `uint256` | The amount recovered. |

<br />

### `RewardAdded`

Emits an event indicating that a reward was added.

```solidity
    event RewardAdded(
        uint256 reward
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `reward` | `uint256` | `uint256` | The amount of the added reward. |

<br />

### `RewardPaid`

Emits an event indicating that some reward was paid to an account.

```solidity
    event RewardPaid(
        address account,
        uint256 reward
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address of the account rewarded. |
| 1 | `reward` | `uint256` | `uint256` | The amount rewarded to &#x60;account&#x60;. |

<br />

### `RewardsDurationUpdated`

Emits an event indicating that the duration of the ward period has updated.

```solidity
    event RewardsDurationUpdated(
        uint256 newDuration
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newDuration` | `uint256` | `uint256` | The new duration of the rewards. |

<br />

### `Staked`

Emits an event indicating that an account has staked.

```solidity
    event Staked(
        address account,
        uint256 amount
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address of the account. |
| 1 | `amount` | `uint256` | `uint256` | The amount staked. |

<br />

### `Withdrawn`

Emits an event indicating that reward was withdrawn.

```solidity
    event Withdrawn(
        address account,
        uint256 amount
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | The address of the account. |
| 1 | `amount` | `uint256` | `uint256` | The amount withdrawn. |

<br />

### `OwnershipTransferred`


```solidity
    event OwnershipTransferred(
        address previousOwner,
        address newOwner
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `previousOwner` | `address` | `address` |  |
| 1 | `newOwner` | `address` | `address` |  |

<br />

