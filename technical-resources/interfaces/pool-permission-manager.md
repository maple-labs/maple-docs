# Maple Pool Permission Manager



<br />


## Functions

### `admin`

Returns the proxy&#x27;s admin address.

```solidity
    function admin()
        view
        returns (
            address admin_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `admin_` | `address` | `address` | The address of the admin. |


<br />

### `configurePool`

Configures the permissions of a pool.

```solidity
    function configurePool(
        address poolManager_,
        uint256 permissionLevel_,
        bytes32[] functionIds_,
        uint256[] poolBitmaps_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |  |
| 1 | `permissionLevel_` | `uint256` | `uint256` |  |
| 2 | `functionIds_` | `bytes32[]` | `bytes32[]` |  |
| 3 | `poolBitmaps_` | `uint256[]` | `uint256[]` |  |


<br />

### `globals`

Returns the address of the &#x60;MapleGlobals&#x60; contract.

```solidity
    function globals()
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

### `hasPermission`

Checks if the lender has permission to interact with a pool.          The function identifier defines the function to check the permission for.

```solidity
    function hasPermission(
        address poolManager_,
        address[] lenders_,
        bytes32 functionId_
    )
        view
        returns (
            bool hasPermission_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |  |
| 1 | `lenders_` | `address[]` | `address[]` |  |
| 2 | `functionId_` | `bytes32` | `bytes32` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `hasPermission_` | `bool` | `bool` |  |


<br />

### `hasPermission`

Checks if the lender has permission to interact with a pool.          The function identifier defines the function to check the permission for.

```solidity
    function hasPermission(
        address poolManager_,
        address lender_,
        bytes32 functionId_
    )
        view
        returns (
            bool hasPermission_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |  |
| 1 | `lender_` | `address` | `address` |  |
| 2 | `functionId_` | `bytes32` | `bytes32` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `hasPermission_` | `bool` | `bool` |  |


<br />

### `implementation`

Returns the proxy&#x27;s implementation address.

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
| 0 | `implementation_` | `address` | `address` | The address of the implementation. |


<br />

### `lenderAllowlist`

Checks if a pool has allowlisted a lender.

```solidity
    function lenderAllowlist(
        address,
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `lenderBitmaps`

Returns the permission bitmap of a lender.

```solidity
    function lenderBitmaps(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `permissionAdmins`

Checks if the account is a permission admin.

```solidity
    function permissionAdmins(
        address
    )
        view
        returns (
            bool
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `bool` | `bool` |  |


<br />

### `permissionLevels`

Returns the permission level of a pool.          Permission levels: private (0), function-level (1), pool-level (2), public (3)

```solidity
    function permissionLevels(
        address
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `poolBitmaps`

Returns a function-specific pool permission bitmap. Return the pool-level permission bitmap if the function identifier is zero.

```solidity
    function poolBitmaps(
        address,
        bytes32
    )
        view
        returns (
            uint256
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `` | `address` | `address` |  |
| 1 | `` | `bytes32` | `bytes32` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 |  | `uint256` | `uint256` |  |


<br />

### `setLenderAllowlist`

Sets the allowlist status of one or more lenders.

```solidity
    function setLenderAllowlist(
        address poolManager_,
        address[] lenders_,
        bool[] booleans_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |  |
| 1 | `lenders_` | `address[]` | `address[]` |  |
| 2 | `booleans_` | `bool[]` | `bool[]` |  |


<br />

### `setLenderBitmaps`

Sets the permission bitmaps of one or more lenders.

```solidity
    function setLenderBitmaps(
        address[] lenders_,
        uint256[] bitmaps_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lenders_` | `address[]` | `address[]` |  |
| 1 | `bitmaps_` | `uint256[]` | `uint256[]` |  |


<br />

### `setPermissionAdmin`

Sets the permission admin status of an account.

```solidity
    function setPermissionAdmin(
        address permissionAdmin_,
        bool isPermissionAdmin_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `permissionAdmin_` | `address` | `address` |  |
| 1 | `isPermissionAdmin_` | `bool` | `bool` |  |


<br />

### `setPoolBitmaps`

Sets the permission bitmaps of a pool.

```solidity
    function setPoolBitmaps(
        address poolManager_,
        bytes32[] functionIds_,
        uint256[] bitmaps_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |  |
| 1 | `functionIds_` | `bytes32[]` | `bytes32[]` |  |
| 2 | `bitmaps_` | `uint256[]` | `uint256[]` |  |


<br />

### `setPoolPermissionLevel`

Sets the permission level of a pool.          Permission levels: private (0), function-level (1), pool-level (2), public (3)          NOTE: Bitmaps must be set before setting the permission level to function-level (1) or pool-level (2).                Otherwise, the pool will be permissionless by default to un-set lenders.

```solidity
    function setPoolPermissionLevel(
        address poolManager_,
        uint256 permissionLevel_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager_` | `address` | `address` |  |
| 1 | `permissionLevel_` | `uint256` | `uint256` |  |


<br />


## Events

### `LenderAllowlistSet`

Emitted when the lender allowlist is updated.

```solidity
    event LenderAllowlistSet(
        address poolManager,
        address[] lenders,
        bool[] booleans
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager` | `address` | `address` | Address of the pool manager. |
| 1 | `lenders` | `address[]` | `address[]` | List of lender addresses to set the allowlist for. |
| 2 | `booleans` | `bool[]` | `bool[]` | List of boolean values. |

<br />

### `LenderBitmapsSet`

Emitted when lender bitmaps are updated.

```solidity
    event LenderBitmapsSet(
        address[] lenders,
        uint256[] bitmaps
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `lenders` | `address[]` | `address[]` | List of lender addresses to set the bitmaps for. |
| 1 | `bitmaps` | `uint256[]` | `uint256[]` | List of permission bitmaps. |

<br />

### `PermissionAdminSet`

Emitted when a permission admin has been updated.

```solidity
    event PermissionAdminSet(
        address account,
        bool isAdmin
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `account` | `address` | `address` | Address of the updated account. |
| 1 | `isAdmin` | `bool` | `bool` | &#x60;true&#x60; if the account is a permission admin, &#x60;false&#x60; if not. |

<br />

### `PoolBitmapsSet`

Emitted when pool bitmaps are updated.

```solidity
    event PoolBitmapsSet(
        address poolManager,
        bytes32[] functionIds,
        uint256[] bitmaps
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager` | `address` | `address` | Address of the pool manager. |
| 1 | `functionIds` | `bytes32[]` | `bytes32[]` | List of function identifiers to set the bitmaps for. |
| 2 | `bitmaps` | `uint256[]` | `uint256[]` | List of permission bitmaps. |

<br />

### `PoolPermissionLevelSet`

Emitted when the permission level of a pool is updated.

```solidity
    event PoolPermissionLevelSet(
        address poolManager,
        uint256 permissionLevel
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `poolManager` | `address` | `address` | Address of the pool manager. |
| 1 | `permissionLevel` | `uint256` | `uint256` | Pool permission level. |

<br />

