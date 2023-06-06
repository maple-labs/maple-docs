# Maple Liquidator



<br />


## Functions

### `collateralAsset`

Returns the address of the collateral asset.

```solidity
    function collateralAsset()
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

### `collateralRemaining`

Returns the amount of collateral yet to be liquidated.

```solidity
    function collateralRemaining()
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

Returns the address of the funding asset.

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

### `getExpectedAmount`

Returns the expected amount to be returned from a flash loan given a certain amount of &#x60;collateralAsset&#x60;.

```solidity
    function getExpectedAmount(
        uint256 swapAmount_
    )
        view
        returns (
            uint256 expectedAmount_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `swapAmount_` | `uint256` | `uint256` | Amount of &#x60;collateralAsset&#x60; to be flash-borrowed. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `expectedAmount_` | `uint256` | `uint256` | Amount of &#x60;fundsAsset&#x60; that must be returned in the same transaction. |


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

### `liquidatePortion`

Flash loan function that:        1. Transfers a specified amount of &#x60;collateralAsset&#x60; to &#x60;msg.sender&#x60;.        2. Performs an arbitrary call to &#x60;msg.sender&#x60;, to trigger logic necessary to get &#x60;fundsAsset&#x60; (e.g., AMM swap).        3. Performs a &#x60;transferFrom&#x60;, taking the corresponding amount of &#x60;fundsAsset&#x60; from the user.        If the required amount of &#x60;fundsAsset&#x60; is not returned in step 3, the entire transaction reverts.

```solidity
    function liquidatePortion(
        uint256 collateralAmount_,
        uint256 maxReturnAmount_,
        bytes data_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAmount_` | `uint256` | `uint256` |  |
| 1 | `maxReturnAmount_` | `uint256` | `uint256` | Max amount of &#x60;fundsAsset&#x60; that can be returned to the liquidator contract. |
| 2 | `data_` | `bytes` | `bytes` | ABI-encoded arguments to be used in the low-level call to perform step 2. |


<br />

### `loanManager`

Returns the address of the loan manager contract.

```solidity
    function loanManager()
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

### `pullFunds`

Pulls a specified amount of ERC-20 tokens from the contract.        Can only be called by &#x60;owner&#x60;.

```solidity
    function pullFunds(
        address token_,
        address destination_,
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `token_` | `address` | `address` | The ERC-20 token contract address. |
| 1 | `destination_` | `address` | `address` | The destination of the transfer. |
| 2 | `amount_` | `uint256` | `uint256` | The amount to transfer. |


<br />

### `setCollateralRemaining`

Sets the initial amount of collateral to be liquidated.

```solidity
    function setCollateralRemaining(
        uint256 collateralAmount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAmount_` | `uint256` | `uint256` | The amount of collateral to be liquidated. |


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


## Events

### `FundsPulled`

Funds were withdrawn from the liquidator.

```solidity
    event FundsPulled(
        address token_,
        address destination_,
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `token_` | `address` | `address` | Address of the token that was withdrawn. |
| 1 | `destination_` | `address` | `address` | Address of where tokens were sent. |
| 2 | `amount_` | `uint256` | `uint256` | Amount of tokens that were sent. |

<br />

### `PortionLiquidated`

Portion of collateral was liquidated.

```solidity
    event PortionLiquidated(
        uint256 swapAmount_,
        uint256 returnedAmount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `swapAmount_` | `uint256` | `uint256` | Amount of collateralAsset that was liquidated. |
| 1 | `returnedAmount_` | `uint256` | `uint256` | Amount of fundsAsset that was returned. |

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

