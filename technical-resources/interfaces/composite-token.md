# CompositeToken

CompositeToken is an ERC20-compatible token used in the controller system. Transfers are gated by an allow list and mint or burn can only be performed by configured Asset Controllers. Governance configures who can hold tokens and which addresses are controllers.

## Functions

### `mint`

Mints tokens to an address. Contract must not be paused. Recipient must be allowlisted when the allow list is enforced

```solidity
function mint(
    address to,
    uint256 amount
) external;
```

#### Parameters

| Index | Name |   Type   | Description |
| :---: | :--: | :------: | ----------- |
|   0   | `to` | `address` | Recipient address |
|   1   | `amount` | `uint256` | Amount to mint |

### `burn`

Burns tokens from an address. Contract must not be paused

```solidity
function burn(
    address from,
    uint256 amount
) external;
```

#### Parameters

| Index |  Name  |   Type   | Description |
| :---: | :----: | :------: | ----------- |
|   0   | `from` | `address` | Address to burn from |
|   1   | `amount` | `uint256` | Amount to burn |

## Admin Functions

### `allowAddresses`

Sets which addresses are allowed to hold tokens. Arrays must be equal length

```solidity
function allowAddresses(
    address[] calldata addresses,
    bool[]    calldata allowed
) external;
```

#### Parameters

| Index |    Name     |     Type     | Description |
| :---: | :---------: | :----------: | ----------- |
|   0   | `addresses` | `address[]`  | Addresses to update |
|   1   |  `allowed`  |   `bool[]`   | Whether each address is allowed |

### `allowAllAddresses`

Turns the allow list on or off for all addresses

```solidity
function allowAllAddresses(
    bool allowed
) external;
```

#### Parameters

| Index |   Name   |  Type  | Description |
| :---: | :------: | :----: | ----------- |
|   0   | `allowed` | `bool` | If true all addresses are allowed to hold |

### `setAssetControllers`

Sets which addresses are valid asset controllers. When enabling an address it must be a valid `ASSET_CONTROLLER` in Globals

```solidity
function setAssetControllers(
    address[] calldata addresses,
    bool[]    calldata flags
) external;
```

#### Parameters

| Index |    Name     |     Type     | Description |
| :---: | :---------: | :----------: | ----------- |
|   0   | `addresses` | `address[]`  | Addresses to update |
|   1   |  `flags`    |   `bool[]`   | Whether each address is marked as a controller |

## Views

```solidity
function allowedAddresses(
    address target
) external view returns (bool allowed);

function allAllowed() external view returns (bool allowed);

function controllers(
    address controller
) external view returns (bool isController);
```

## Events

Emitted when the allowlist is updated for a set of addresses

```solidity
event AddressesAllowed(
    address[] addresses,
    bool[]    allowed
);
```

Emitted when the contract toggles between allowing all addresses and using an allow list

```solidity
event AllAllowed(
    bool allowed
);
```

Emitted when the set of controller addresses is updated

```solidity
event AssetControllersSet(
    address[] addresses,
    bool[]    flags
);
```

Emitted when tokens are burned by a controller

```solidity
event AssetsBurned(
    address indexed from,
    uint256 amount
);
```

Emitted when tokens are minted by a controller

```solidity
event AssetsMinted(
    address indexed to,
    uint256 amount
);
```
