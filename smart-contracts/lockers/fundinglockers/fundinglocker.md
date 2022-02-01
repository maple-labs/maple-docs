# Funding Locker

FundingLocker holds custody of Liquidity Asset tokens during the funding period of a Loan.

\


## Constructor

```solidity
    constructor(
        address _liquidityAsset,
        address _loan
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   | `_liquidityAsset` | `address` |   `address`   |             |
|   1   |      `_loan`      | `address` |   `address`   |             |

\


## Functions

### `drain`

Transfers entire amount of Liquidity Asset held in escrow to the Loan. Only the Loan can call this function.

```solidity
    function drain()
        nonpayable;
```

\


### `liquidityAsset` _\[state variable]_

The asset the Loan was funded with.

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


### `loan` _\[state variable]_

The Loan this FundingLocker has funded.

```solidity
    function loan()
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


### `pull`

Transfers \`amt\` of Liquidity Asset to \`dst\`. Only the Loan can call this function.

```solidity
    function pull(
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
