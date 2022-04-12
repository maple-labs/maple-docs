# MapleLoanInitializer



<br />


## Functions

### `decodeArguments`



```solidity
    function decodeArguments(
        bytes encodedArguments_
    )
        pure
        returns (
            address borrower_,
            address[2] assets_,
            uint256[3] termDetails_,
            uint256[3] amounts_,
            uint256[4] rates_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |  |
| 1 | `assets_` | `address[2]` | `address[2]` |  |
| 2 | `termDetails_` | `uint256[3]` | `uint256[3]` |  |
| 3 | `amounts_` | `uint256[3]` | `uint256[3]` |  |
| 4 | `rates_` | `uint256[4]` | `uint256[4]` |  |


<br />

### `encodeArguments`



```solidity
    function encodeArguments(
        address borrower_,
        address[2] assets_,
        uint256[3] termDetails_,
        uint256[3] amounts_,
        uint256[4] rates_
    )
        pure
        returns (
            bytes encodedArguments_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `borrower_` | `address` | `address` |  |
| 1 | `assets_` | `address[2]` | `address[2]` |  |
| 2 | `termDetails_` | `uint256[3]` | `uint256[3]` |  |
| 3 | `amounts_` | `uint256[3]` | `uint256[3]` |  |
| 4 | `rates_` | `uint256[4]` | `uint256[4]` |  |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `encodedArguments_` | `bytes` | `bytes` |  |


<br />
