# Liquidator



<br />

## Constructor




```solidity
    constructor(
        address owner_,
        address collateralAsset_,
        address fundsAsset_,
        address auctioneer_,
        address destination_,
        address globals_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` | The address of an account that will have administrative privileges on this contract. |
| 1 | `collateralAsset_` | `address` | `address` | The address of the collateral asset being liquidated. |
| 2 | `fundsAsset_` | `address` | `address` | The address of the funds asset. |
| 3 | `auctioneer_` | `address` | `address` | The address of an Auctioneer. |
| 4 | `destination_` | `address` | `address` | The address to send funds asset after liquidation. |
| 5 | `globals_` | `address` | `address` | The address of a Maple Globals contract. |


<br />


## Functions

### `auctioneer` _[state variable]_

Getter function that returns &#x60;auctioneer&#x60;.

```solidity
    function auctioneer()
        view
        returns (
            address auctioneer_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `auctioneer_` | `address` | `address` |  |


<br />

### `collateralAsset` _[state variable]_

Getter function that returns &#x60;collateralAsset&#x60;.

```solidity
    function collateralAsset()
        view
        returns (
            address collateralAsset_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `collateralAsset_` | `address` | `address` |  |


<br />

### `destination` _[state variable]_

Getter function that returns &#x60;destination&#x60; - address that liquidated funds are sent to.

```solidity
    function destination()
        view
        returns (
            address destination_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `destination_` | `address` | `address` |  |


<br />

### `fundsAsset` _[state variable]_

Getter function that returns &#x60;fundsAsset&#x60;.

```solidity
    function fundsAsset()
        view
        returns (
            address fundsAsset_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsAsset_` | `address` | `address` |  |


<br />

### `getExpectedAmount`

Returns the expected amount to be returned from a flash loan given a certain amount of &#x60;collateralAsset&#x60;.

```solidity
    function getExpectedAmount(
        uint256 swapAmount_
    )
        nonpayable
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

### `globals` _[state variable]_

Getter function that returns &#x60;globals&#x60;.

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

### `liquidatePortion`

Flash loan function that:        1. Transfers a specified amount of &#x60;collateralAsset&#x60; to &#x60;msg.sender&#x60;.        2. Performs an arbitrary call to &#x60;msg.sender&#x60;, to trigger logic necessary to get &#x60;fundsAsset&#x60; (e.g., AMM swap).        3. Performs a &#x60;transferFrom&#x60;, taking the corresponding amount of &#x60;fundsAsset&#x60; from the user.        If the required amount of &#x60;fundsAsset&#x60; is not returned in step 3, the entire transaction reverts.

```solidity
    function liquidatePortion(
        uint256 swapAmount_,
        uint256 maxReturnAmount_,
        bytes data_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `swapAmount_` | `uint256` | `uint256` | Amount of &#x60;collateralAsset&#x60; that is to be borrowed in the flash loan. |
| 1 | `maxReturnAmount_` | `uint256` | `uint256` | Max amount of &#x60;fundsAsset&#x60; that can be returned to the liquidator contract. |
| 2 | `data_` | `bytes` | `bytes` | ABI-encoded arguments to be used in the low-level call to perform step 2. |


<br />

### `owner` _[state variable]_

Getter function that returns &#x60;owner&#x60;.

```solidity
    function owner()
        view
        returns (
            address owner_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `owner_` | `address` | `address` |  |


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

### `setAuctioneer`

Set the auctioneer contract address, which is used to pull the &#x60;getExpectedAmount&#x60;.        Can only be set by &#x60;owner&#x60;.

```solidity
    function setAuctioneer(
        address auctioneer_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `auctioneer_` | `address` | `address` | The auctioneer contract address. |


<br />


## Events

### `AuctioneerSet`

Auctioneer was set.

```solidity
    event AuctioneerSet(
        address auctioneer_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `auctioneer_` | `address` | `address` | Address of the auctioneer. |

<br />

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

