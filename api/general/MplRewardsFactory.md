# MplRewardsFactory

MplRewardsFactory instantiates MplRewards contracts.

## Constructor




```solidity
  constructor(
    address _globals
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_globals` | `address` | `address` | 



## Functions

### createMplRewards 

Instantiates a MplRewards contract. Only the Governor can call this function. It emits a &#x60;MplRewardsCreated&#x60; event. 

```solidity
  function createMplRewards(
    address rewardsToken,
    address stakingToken
  ) nonpayable returns (
    address mplRewards
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `rewardsToken` | `address` | `address` | The address of the rewards token (will always be MPL).
| 1 | `stakingToken` | `address` | `address` | The address of the staking token (token used to stake to earn rewards).  (i.e., Pool address for PoolFDT mining, StakeLocker address for staked BPT mining.) 


#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 | `mplRewards` | `address` |  The address of the instantiated MplRewards.


### globals (state variable)

The instance of MapleGlobals, used to retrieve the current Governor.

```solidity
  function globals(
  ) view returns (
    address
  )
```



#### Return Values:
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `address` | 


### isMplRewards (state variable)



```solidity
  function isMplRewards(
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
| Index | Name | Type | Description |
| :---: | :--: | :--: | :---------- |
| 0 |  | `bool` | Whether &#x60;mpeRewards&#x60; is a MplRewards contract.


### setGlobals 

Updates the MapleGlobals instance. Only the Governor can call this function. 

```solidity
  function setGlobals(
    address _globals
  ) nonpayable
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `_globals` | `address` | `address` | Address of new MapleGlobals contract.



## Events

### MplRewardsCreated

Emits an event indicating that a MplRewards contract was created.
```solidity
  event MplRewardsCreated(
    address rewardsToken,
    address stakingToken,
    address mplRewards,
    address owner
  )
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `rewardsToken` | `address` | `address` | The asset used for rewards.
| 1 | `stakingToken` | `address` | `address` | The asset used for staking.
| 2 | `mplRewards` | `address` | `address` | The address of the MplRewards contract.
| 3 | `owner` | `address` | `address` | The owner of the MplRewards.

