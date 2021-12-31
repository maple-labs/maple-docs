# IMapleProxied

A Maple implementation that is to be proxied, must implement IMapleProxied.

<br />


## Functions

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

### `setImplementation`

Modifies the proxy&#x27;s implementation address.

```solidity
    function setImplementation(
        address newImplementation_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newImplementation_` | `address` | `address` | The address of an implementation contract. |


<br />

### `upgrade`

Upgrades a contract implementation to a specific version.         Access control logic critical since caller can force a selfdestruct via a malicious &#x60;migrator_&#x60; which is delegatecalled.

```solidity
    function upgrade(
        uint256 toVersion_,
        bytes arguments_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `toVersion_` | `uint256` | `uint256` | The version to upgrade to. |
| 1 | `arguments_` | `bytes` | `bytes` | Some encoded arguments to use for the upgrade. |


<br />


## Events

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

