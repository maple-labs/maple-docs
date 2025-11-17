# AssetControllerOracle

The Asset Controller Oracle returns a price quote for converting between a deposit asset and the pool asset. It does not move tokens. The current implementation is a placeholder that always returns a 1 to 1 quote and requires both assets to have matching decimals. It will be upgraded in the future to support multiple assets with non 1 to 1 pricing.

## Functions

### `convert`

Returns a quote for converting `amountIn` of `assetIn` to `assetOut`. The placeholder returns a 1 to 1 quote and enforces identical decimals on the two assets.

```solidity
function convert(
    address assetIn,
    address assetOut,
    uint256 amountIn,
    bytes32 metadata
) external view returns (uint256 amountOut);
```

#### Parameters

| Index |    Name    |   Type   | Description |
| :---: | :--------: | :------: | ----------- |
|   0   | `assetIn`  | `address` | Asset to convert from |
|   1   | `assetOut` | `address` | Asset to convert into |
|   2   | `amountIn` | `uint256` | Amount to convert |
|   3   | `metadata` | `bytes32` | Reserved for future use |

#### Return Values

| Index |    Name     |   Type   | Description |
| :---: | :---------: | :------: | ----------- |
|   0   | `amountOut` | `uint256` | Quoted amount for the conversion |
