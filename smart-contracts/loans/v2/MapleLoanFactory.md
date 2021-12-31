# MapleLoanFactory

MapleLoanFactory deploys Loan instances.

<br />

## Constructor




```solidity
    constructor(
        address mapleGlobals_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `mapleGlobals_` | `address` | `address` | The address of a Maple Globals contract. |


<br />


## Functions

### `createInstance`

Deploys a new instance proxying the default implementation version, with some initialization arguments.          Uses a nonce and &#x60;msg.sender&#x60; as a salt for the CREATE2 opcode during instantiation to produce deterministic addresses.

```solidity
    function createInstance(
        bytes arguments_,
        bytes32 salt_
    )
        nonpayable
        returns (
            address instance_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `arguments_` | `bytes` | `bytes` | The initialization arguments to use for the instance deployment, if any. |
| 1 | `salt_` | `bytes32` | `bytes32` | The salt to use in the contract creation process. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `instance_` | `address` | `address` |  The address of the deployed proxy contract. |


<br />

### `defaultImplementation`

The address of an implementation for proxies.

```solidity
    function defaultImplementation()
        view
        returns (
            address defaultImplementation_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `defaultImplementation_` | `address` | `address` |  |


<br />

### `defaultVersion`

The default version.

```solidity
    function defaultVersion()
        view
        returns (
            uint256 defaultVersion_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `defaultVersion_` | `uint256` | `uint256` |  |


<br />

### `disableUpgradePath`

Disables upgrading from a version to a version of a implementation.         Only the Governor can call this function.

```solidity
    function disableUpgradePath(
        uint256 fromVersion_,
        uint256 toVersion_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fromVersion_` | `uint256` | `uint256` | The starting version of the upgrade path. |
| 1 | `toVersion_` | `uint256` | `uint256` | The destination version of the upgrade path. |


<br />

### `enableUpgradePath`

Enables upgrading from a version to a version of an implementation, with an optional migrator.         Only the Governor can call this function.

```solidity
    function enableUpgradePath(
        uint256 fromVersion_,
        uint256 toVersion_,
        address migrator_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fromVersion_` | `uint256` | `uint256` | The starting version of the upgrade path. |
| 1 | `toVersion_` | `uint256` | `uint256` | The destination version of the upgrade path. |
| 2 | `migrator_` | `address` | `address` | The address of the migrator, if any. |


<br />

### `getInstanceAddress`

Returns the deterministic address of a potential proxy, given some arguments and salt.

```solidity
    function getInstanceAddress(
        bytes arguments_,
        bytes32 salt_
    )
        view
        returns (
            address instanceAddress_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `arguments_` | `bytes` | `bytes` | The initialization arguments to be used when deploying the proxy. |
| 1 | `salt_` | `bytes32` | `bytes32` | The salt to be used when deploying the proxy. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `instanceAddress_` | `address` | `address` | The deterministic address of a potential proxy. |


<br />

### `implementationOf`

Returns the address of an implementation version.

```solidity
    function implementationOf(
        uint256 version_
    )
        view
        returns (
            address implementation_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` | The implementation version. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` | The address of the implementation. |


<br />

### `isLoan` _[state variable]_

Whether the proxy is a MapleLoan deployed by this factory.

```solidity
    function isLoan(
        address proxy_
    )
        view
        returns (
            bool isLoan_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `proxy_` | `address` | `address` | The address of the proxy contract. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `isLoan_` | `bool` | `bool` | Whether the proxy is a MapleLoan deployed by this factory. |


<br />

### `mapleGlobals`

The address of the MapleGlobals contract.

```solidity
    function mapleGlobals()
        view
        returns (
            address mapleGlobals_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `mapleGlobals_` | `address` | `address` |  |


<br />

### `migratorForPath`

Returns the address of a migrator contract for a migration path (from version, to version).          If oldVersion_ &#x3D;&#x3D; newVersion_, the migrator is an initializer.

```solidity
    function migratorForPath(
        uint256 oldVersion_,
        uint256 newVersion_
    )
        view
        returns (
            address migrator_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `oldVersion_` | `uint256` | `uint256` | The old version. |
| 1 | `newVersion_` | `uint256` | `uint256` | The new version. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `migrator_` | `address` | `address` |   The address of a migrator contract. |


<br />

### `registerImplementation`

Registers the address of an implementation contract as a version, with an optional initializer.         Only the Governor can call this function.

```solidity
    function registerImplementation(
        uint256 version_,
        address implementationAddress_,
        address initializer_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` | The version to register. |
| 1 | `implementationAddress_` | `address` | `address` | The address of the implementation. |
| 2 | `initializer_` | `address` | `address` | The address of the initializer, if any. |


<br />

### `setDefaultVersion`

Sets the default version.         Only the Governor can call this function.

```solidity
    function setDefaultVersion(
        uint256 version_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` | The implementation version to set as the default. |


<br />

### `setGlobals`

Sets the Maple Globals contract.         Only the Governor can call this function.

```solidity
    function setGlobals(
        address mapleGlobals_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `mapleGlobals_` | `address` | `address` | The address of a Maple Globals contract. |


<br />

### `upgradeEnabledForPath`

Whether the upgrade is enabled for a path from a version to another version.

```solidity
    function upgradeEnabledForPath(
        uint256 toVersion_,
        uint256 fromVersion_
    )
        view
        returns (
            bool allowed_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toVersion_` | `uint256` | `uint256` | The initial version. |
| 1 | `fromVersion_` | `uint256` | `uint256` | The destination version. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `allowed_` | `bool` | `bool` |     Whether the upgrade is enabled. |


<br />

### `upgradeInstance`

Upgrades the calling proxy contract&#x27;s implementation, with some migration arguments.

```solidity
    function upgradeInstance(
        uint256 toVersion_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toVersion_` | `uint256` | `uint256` | The implementation version to upgrade the proxy contract to. |
| 1 | `arguments_` | `bytes` | `bytes` | The migration arguments, if any. |


<br />

### `versionOf`

Returns the version of an implementation contract.

```solidity
    function versionOf(
        address implementation_
    )
        view
        returns (
            uint256 version_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `implementation_` | `address` | `address` | The address of an implementation contract. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` |        The version of the implementation contract. |


<br />


## Events

### `DefaultVersionSet`

A default version was set.

```solidity
    event DefaultVersionSet(
        uint256 version_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` | The default version. |

<br />

### `ImplementationRegistered`

A version of an implementation, at some address, was registered, with an optional initializer.

```solidity
    event ImplementationRegistered(
        uint256 version_,
        address implementationAddress_,
        address initializer_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` | The version registered. |
| 1 | `implementationAddress_` | `address` | `address` | The address of the implementation. |
| 2 | `initializer_` | `address` | `address` | The address of the initializer, if any. |

<br />

### `InstanceDeployed`

A proxy contract was deployed with some initialization arguments.

```solidity
    event InstanceDeployed(
        uint256 version_,
        address instance_,
        bytes initializationArguments_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `version_` | `uint256` | `uint256` | The version of the implementation being proxied by the deployed proxy contract. |
| 1 | `instance_` | `address` | `address` | The address of the proxy contract deployed. |
| 2 | `initializationArguments_` | `bytes` | `bytes` | The arguments used to initialize the proxy contract, if any. |

<br />

### `InstanceUpgraded`

A instance has upgraded by proxying to a new implementation, with some migration arguments.

```solidity
    event InstanceUpgraded(
        address instance_,
        uint256 fromVersion_,
        uint256 toVersion_,
        bytes migrationArguments_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `instance_` | `address` | `address` | The address of the proxy contract. |
| 1 | `fromVersion_` | `uint256` | `uint256` | The initial implementation version being proxied. |
| 2 | `toVersion_` | `uint256` | `uint256` | The new implementation version being proxied. |
| 3 | `migrationArguments_` | `bytes` | `bytes` | The arguments used to migrate, if any. |

<br />

### `MapleGlobalsSet`

The MapleGlobals was set.

```solidity
    event MapleGlobalsSet(
        address mapleGlobals_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `mapleGlobals_` | `address` | `address` | The address of a Maple Globals contract. |

<br />

### `UpgradePathDisabled`

An upgrade path was disabled, with an optional migrator contract.

```solidity
    event UpgradePathDisabled(
        uint256 fromVersion_,
        uint256 toVersion_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fromVersion_` | `uint256` | `uint256` | The starting version of the upgrade path. |
| 1 | `toVersion_` | `uint256` | `uint256` | The destination version of the upgrade path. |

<br />

### `UpgradePathEnabled`

An upgrade path was enabled, with an optional migrator contract.

```solidity
    event UpgradePathEnabled(
        uint256 fromVersion_,
        uint256 toVersion_,
        address migrator_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fromVersion_` | `uint256` | `uint256` | The starting version of the upgrade path. |
| 1 | `toVersion_` | `uint256` | `uint256` | The destination version of the upgrade path. |
| 2 | `migrator_` | `address` | `address` | The address of the migrator, if any. |

<br />

