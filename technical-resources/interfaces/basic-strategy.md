# MapleBasicStrategy



<br />


## Functions

### `HUNDRED_PERCENT` 



```solidity
    function HUNDRED_PERCENT()
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

### `STRATEGY_TYPE` 

Returns the type of the strategy.

```solidity
    function STRATEGY_TYPE()
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

### `assetsUnderManagement` 

Returns the current amount of assets managed by the strategy.

```solidity
    function assetsUnderManagement()
        view
        returns (
            uint256 assetsUnderManagement_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assetsUnderManagement_` | `uint256` | `uint256` |  |


<br />

### `deactivateStrategy` 

Disables funding and marks all assets under management as zero.

```solidity
    function deactivateStrategy()
        nonpayable;
```



<br />

### `factory` 

The address of the proxy factory.

```solidity
    function factory()
        view
        returns (
            address factory_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `factory_` | `address` | `address` |  |


<br />

### `fundsAsset` 

Gets the address of the funds asset.

```solidity
    function fundsAsset()
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

### `fundStrategy` 

Deploys assets from the Maple pool into the strategy.         Funding can only be attempted when the strategy is active.

```solidity
    function fundStrategy(
        uint256 assetsIn_,
        uint256 minSharesOut_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assetsIn_` | `uint256` | `uint256` |  |
| 1 | `minSharesOut_` | `uint256` | `uint256` |  |


<br />

### `globals` 



```solidity
    function globals()
        view
        returns (
            address globals_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `globals_` | `address` | `address` |  |


<br />

### `governor` 



```solidity
    function governor()
        view
        returns (
            address governor_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `governor_` | `address` | `address` |  |


<br />

### `impairStrategy` 

Disables funding and marks all assets under management as unrealized losses.

```solidity
    function impairStrategy()
        nonpayable;
```



<br />

### `implementation` 

The address of the implementation contract being proxied.

```solidity
    function implementation()
        view
        returns (
            address implementation_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` |  |


<br />

### `lastRecordedTotalAssets` 

Gets the last recorded total assets.

```solidity
    function lastRecordedTotalAssets()
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

### `locked` 



```solidity
    function locked()
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

### `migrate` 

Modifies the proxy&#x27;s storage by delegate-calling a migrator contract with some arguments.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function migrate(
        address migrator_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `migrator_` | `address` | `address` | The address of a migrator contract. |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the migration. |


<br />

### `pool` 

Returns the address of the pool contract.

```solidity
    function pool()
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

### `poolDelegate` 



```solidity
    function poolDelegate()
        view
        returns (
            address poolDelegate_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolDelegate_` | `address` | `address` |  |


<br />

### `poolManager` 

Returns the address of the pool manager contract.

```solidity
    function poolManager()
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

### `reactivateStrategy` 

Resumes normal operation of the strategy.

```solidity
    function reactivateStrategy(
        bool updateAccounting_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `updateAccounting_` | `bool` | `bool` |  |


<br />

### `securityAdmin` 



```solidity
    function securityAdmin()
        view
        returns (
            address securityAdmin_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `securityAdmin_` | `address` | `address` |  |


<br />

### `setImplementation` 

Modifies the proxy&#x27;s implementation address.

```solidity
    function setImplementation(
        address implementation_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` |  |


<br />

### `setStrategyFeeRate` 

Sets a new fee rate for the strategy.          Can only be called when the strategy is active.

```solidity
    function setStrategyFeeRate(
        uint256 strategyFeeRate_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `strategyFeeRate_` | `uint256` | `uint256` |  |


<br />

### `strategyFeeRate` 

Returns the strategy fee rate.

```solidity
    function strategyFeeRate()
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

### `strategyState` 

Returns the current state of the strategy.          Can be active, inactive, or impaired.

```solidity
    function strategyState()
        view
        returns (
            uint8
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint8` | `enum StrategyState` |  |


<br />

### `strategyVault` 

Returns the address of the ERC4626 compliant Vault.

```solidity
    function strategyVault()
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

### `treasury` 



```solidity
    function treasury()
        view
        returns (
            address treasury_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `treasury_` | `address` | `address` |  |


<br />

### `unrealizedLosses` 

Returns the current amount of unrealized losses.

```solidity
    function unrealizedLosses()
        view
        returns (
            uint256 unrealizedLosses_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `unrealizedLosses_` | `uint256` | `uint256` |  |


<br />

### `upgrade` 

Upgrades a contract implementation to a specific version.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function upgrade(
        uint256 version_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` |  |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the upgrade. |


<br />

### `withdrawFromStrategy` 

Withdraw assets from the strategy back into the Maple pool.         Withdrawals can be attempted even if the strategy is impaired or inactive.

```solidity
    function withdrawFromStrategy(
        uint256 assetsOut_,
        uint256 maxSharesBurned_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assetsOut_` | `uint256` | `uint256` |  |
| 1 | `maxSharesBurned_` | `uint256` | `uint256` |  |


<br />


## Events

### `StrategyDeactivated`

Emitted when the strategy is deactivated.

```solidity
    event StrategyDeactivated();
```


<br />

### `StrategyFeeRateSet`

Emitted when the fee rate on the strategy&#x27;s yield is updated.

```solidity
    event StrategyFeeRateSet(
        uint256 feeRate
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `feeRate` | `uint256` | `uint256` | Percentage of yield that accrues to the treasury. |

<br />

### `StrategyFeesCollected`

Emitted when fees on the strategy&#x27;s yield are collected.

```solidity
    event StrategyFeesCollected(
        uint256 fees
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fees` | `uint256` | `uint256` | Amount of assets collected by the treasury. |

<br />

### `StrategyFunded`

Emitted when assets are deposited into the strategy.

```solidity
    event StrategyFunded(
        uint256 assets
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets` | `uint256` | `uint256` | Amount of assets deposited. |

<br />

### `StrategyFunded`

Emitted when assets are deposited into the strategy.

```solidity
    event StrategyFunded(
        uint256 assets,
        uint256 shares
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets` | `uint256` | `uint256` | Amount of assets deposited. |
| 1 | `shares` | `uint256` | `uint256` |  |

<br />

### `StrategyImpaired`

Emitted when the strategy is impaired.

```solidity
    event StrategyImpaired();
```


<br />

### `StrategyReactivated`

Emitted when the strategy is reactivated.

```solidity
    event StrategyReactivated(
        bool updateAccounting
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `updateAccounting` | `bool` | `bool` | Flag that defines if lastRecordedTotalAssets should be refreshed. |

<br />

### `StrategyWithdrawal`

Emitted when assets are withdrawn from the strategy.

```solidity
    event StrategyWithdrawal(
        uint256 assets
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets` | `uint256` | `uint256` | Amount of assets withdrawn. |

<br />

### `StrategyWithdrawal`

Emitted when assets are withdrawn from the strategy.

```solidity
    event StrategyWithdrawal(
        uint256 assets,
        uint256 shares
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `assets` | `uint256` | `uint256` | Amount of assets withdrawn. |
| 1 | `shares` | `uint256` | `uint256` |  |

<br />

### `Upgraded`

The instance was upgraded.

```solidity
    event Upgraded(
        uint256 toVersion_,
        bytes arguments_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toVersion_` | `uint256` | `uint256` | The new version of the loan. |
| 1 | `arguments_` | `bytes` | `bytes` | The upgrade arguments, if any. |

<br />

