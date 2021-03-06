# Liquidity Locker

LiquidityLocker holds custody of Liquidity Asset tokens for a given Pool.

\


## Constructor

```solidity
    constructor(
        address _liquidityAsset,
        address _pool
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `_liquidityAsset` | `address` |   `address`   |             |
|   1   |      `_pool`      | `address` |   `address`   |             |

\


## Functions

### `fundLoan`

Funds a Loan using available assets in this LiquidityLocker. Only the Pool can call this function.

```solidity
    function fundLoan(
        address loan,
        address debtLocker,
        uint256 amount
    )
        nonpayable;
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description                                         |
| :---: | :----------: | :-------: | :-----------: | --------------------------------------------------- |
|   0   |    `loan`    | `address` |   `address`   | The Loan to fund.                                   |
|   1   | `debtLocker` | `address` |   `address`   | The DebtLocker that will escrow debt tokens.        |
|   2   |   `amount`   | `uint256` |   `uint256`   | The amount of Liquidity Asset to fund the Loan for. |

\


### `liquidityAsset` _\[state variable]_

The Liquidity Asset which this LiquidityLocker will escrow.

```solidity
    function liquidityAsset()
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


### `pool` _\[state variable]_

The Pool contract address that owns this LiquidityLocker.

```solidity
    function pool()
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


### `transfer`

Transfers amount of Liquidity Asset to a destination account. Only the Pool can call this function.

```solidity
    function transfer(
        address dst,
        uint256 amt
    )
        nonpayable;
```

#### Parameters:

| Index |  Name |    Type   | Internal Type | Description                                     |
| :---: | :---: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `dst` | `address` |   `address`   | The destination to transfer Liquidity Asset to. |
|   1   | `amt` | `uint256` |   `uint256`   | The amount of Liquidity Asset to transfer.      |

\
