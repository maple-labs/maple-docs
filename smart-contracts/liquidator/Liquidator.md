# Liquidator

\


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

| Index |        Name        |    Type   | Internal Type | Description                                                                          |
| :---: | :----------------: | :-------: | :-----------: | ------------------------------------------------------------------------------------ |
|   0   |      `owner_`      | `address` |   `address`   | The address of an account that will have administrative privileges on this contract. |
|   1   | `collateralAsset_` | `address` |   `address`   | The address of the collateral asset being liquidated.                                |
|   2   |    `fundsAsset_`   | `address` |   `address`   | The address of the funds asset.                                                      |
|   3   |    `auctioneer_`   | `address` |   `address`   | The address of an Auctioneer.                                                        |
|   4   |   `destination_`   | `address` |   `address`   | The address to send funds asset after liquidation.                                   |
|   5   |     `globals_`     | `address` |   `address`   | The address of a Maple Globals contract.                                             |

\


## Functions

### `auctioneer` _\[state variable]_

Getter function that returns \`auctioneer\`.

```solidity
    function auctioneer()
        view
        returns (
            address auctioneer_
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description |
| :---: | :-----------: | :-------: | :-----------: | ----------- |
|   0   | `auctioneer_` | `address` |   `address`   |             |

\


### `collateralAsset` _\[state variable]_

Getter function that returns \`collateralAsset\`.

```solidity
    function collateralAsset()
        view
        returns (
            address collateralAsset_
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description |
| :---: | :----------------: | :-------: | :-----------: | ----------- |
|   0   | `collateralAsset_` | `address` |   `address`   |             |

\


### `destination` _\[state variable]_

Getter function that returns \`destination\` - address that liquidated funds are sent to.

```solidity
    function destination()
        view
        returns (
            address destination_
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description |
| :---: | :------------: | :-------: | :-----------: | ----------- |
|   0   | `destination_` | `address` |   `address`   |             |

\


### `fundsAsset` _\[state variable]_

Getter function that returns \`fundsAsset\`.

```solidity
    function fundsAsset()
        view
        returns (
            address fundsAsset_
        );
```

#### Return Values:

| Index |      Name     |    Type   | Internal Type | Description |
| :---: | :-----------: | :-------: | :-----------: | ----------- |
|   0   | `fundsAsset_` | `address` |   `address`   |             |

\


### `getExpectedAmount`

Returns the expected amount to be returned from a flash loan given a certain amount of \`collateralAsset\`.

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

| Index |      Name     |    Type   | Internal Type | Description                                         |
| :---: | :-----------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   | `swapAmount_` | `uint256` |   `uint256`   | Amount of \`collateralAsset\` to be flash-borrowed. |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                                                             |
| :---: | :---------------: | :-------: | :-----------: | ----------------------------------------------------------------------- |
|   0   | `expectedAmount_` | `uint256` |   `uint256`   | Amount of \`fundsAsset\` that must be returned in the same transaction. |

\


### `globals` _\[state variable]_

Getter function that returns \`globals\`.

```solidity
    function globals()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |

\


### `liquidatePortion`

Flash loan function that: 1. Transfers a specified amount of \`collateralAsset\` to \`msg.sender\`. 2. Performs an arbitrary call to \`msg.sender\`, to trigger logic necessary to get \`fundsAsset\` (e.g., AMM swap). 3. Performs a \`transferFrom\`, taking the corresponding amount of \`fundsAsset\` from the user. If the required amount of \`fundsAsset\` is not returned in step 3, the entire transaction reverts.

```solidity
    function liquidatePortion(
        uint256 swapAmount_,
        uint256 maxReturnAmount_,
        bytes data_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                                                                   |
| :---: | :----------------: | :-------: | :-----------: | ----------------------------------------------------------------------------- |
|   0   |    `swapAmount_`   | `uint256` |   `uint256`   | Amount of \`collateralAsset\` that is to be borrowed in the flash loan.       |
|   1   | `maxReturnAmount_` | `uint256` |   `uint256`   | Max amount of \`fundsAsset\` that can be returned to the liquidator contract. |
|   2   |       `data_`      |  `bytes`  |    `bytes`    | ABI-encoded arguments to be used in the low-level call to perform step 2.     |

\


### `owner` _\[state variable]_

Getter function that returns \`owner\`.

```solidity
    function owner()
        view
        returns (
            address owner_
        );
```

#### Return Values:

| Index |   Name   |    Type   | Internal Type | Description |
| :---: | :------: | :-------: | :-----------: | ----------- |
|   0   | `owner_` | `address` |   `address`   |             |

\


### `pullFunds`

Pulls a specified amount of ERC-20 tokens from the contract. Can only be called by \`owner\`.

```solidity
    function pullFunds(
        address token_,
        address destination_,
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                        |
| :---: | :------------: | :-------: | :-----------: | ---------------------------------- |
|   0   |    `token_`    | `address` |   `address`   | The ERC-20 token contract address. |
|   1   | `destination_` | `address` |   `address`   | The destination of the transfer.   |
|   2   |    `amount_`   | `uint256` |   `uint256`   | The amount to transfer.            |

\


### `setAuctioneer`

Set the auctioneer contract address, which is used to pull the \`getExpectedAmount\`. Can only be set by \`owner\`.

```solidity
    function setAuctioneer(
        address auctioneer_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                      |
| :---: | :-----------: | :-------: | :-----------: | -------------------------------- |
|   0   | `auctioneer_` | `address` |   `address`   | The auctioneer contract address. |

\


## Events

### `AuctioneerSet`

Auctioneer was set.

```solidity
    event AuctioneerSet(
        address auctioneer_
    );
```

#### Parameters:

| Index |      Name     |    Type   | Internal Type | Description                |
| :---: | :-----------: | :-------: | :-----------: | -------------------------- |
|   0   | `auctioneer_` | `address` |   `address`   | Address of the auctioneer. |

\


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

| Index |      Name      |    Type   | Internal Type | Description                              |
| :---: | :------------: | :-------: | :-----------: | ---------------------------------------- |
|   0   |    `token_`    | `address` |   `address`   | Address of the token that was withdrawn. |
|   1   | `destination_` | `address` |   `address`   | Address of where tokens were sent.       |
|   2   |    `amount_`   | `uint256` |   `uint256`   | Amount of tokens that were sent.         |

\


### `PortionLiquidated`

Portion of collateral was liquidated.

```solidity
    event PortionLiquidated(
        uint256 swapAmount_,
        uint256 returnedAmount_
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                    |
| :---: | :---------------: | :-------: | :-----------: | ---------------------------------------------- |
|   0   |   `swapAmount_`   | `uint256` |   `uint256`   | Amount of collateralAsset that was liquidated. |
|   1   | `returnedAmount_` | `uint256` |   `uint256`   | Amount of fundsAsset that was returned.        |

\
