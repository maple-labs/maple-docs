# DebtLocker



<br />


## Functions

### `acceptNewTerms`

Accept the new loan terms and trigger a refinance.

```solidity
    function acceptNewTerms(
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_,
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinancer_` | `address` | `address` | The address of the refinancer contract. |
| 1 | `deadline_` | `uint256` | `uint256` | The deadline of the new terms proposal. |
| 2 | `calls_` | `bytes[]` | `bytes[]` | The array of encoded data that are to be executed as delegatecalls by the refinancer. |
| 3 | `amount_` | `uint256` | `uint256` | The amount of &#x60;fundsAsset&#x60; that is to be sent to the Loan as part of the transaction. |


<br />

### `allowedSlippage`

The maximum slippage allowed during liquidations.

```solidity
    function allowedSlippage()
        view
        returns (
            uint256 allowedSlippage_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `allowedSlippage_` | `uint256` | `uint256` |  |


<br />

### `amountRecovered`

The amount in funds asset recovered during liquidations.

```solidity
    function amountRecovered()
        view
        returns (
            uint256 amountRecovered_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amountRecovered_` | `uint256` | `uint256` |  |


<br />

### `claim`

Claims funds to send to Pool. Handles funds from payments and liquidations.          Only the Pool can call this function.

```solidity
    function claim()
        nonpayable
        returns (
            uint256[7] details_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `details_` | `uint256[7]` | `uint256[7]` |              [0] &#x3D;&gt; Total Claimed.              [1] &#x3D;&gt; Interest Claimed.              [2] &#x3D;&gt; Principal Claimed.              [3] &#x3D;&gt; Pool Delegate Fees Claimed.              [4] &#x3D;&gt; Excess Returned Claimed.              [5] &#x3D;&gt; Amount Recovered (from Liquidation).              [6] &#x3D;&gt; Default Suffered. |


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

### `fundsToCapture`

Returns the amount of funds that will be captured next claim.

```solidity
    function fundsToCapture()
        view
        returns (
            uint256 fundsToCapture_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `fundsToCapture_` | `uint256` | `uint256` |  |


<br />

### `getExpectedAmount`

Returns the expected amount to be returned to the liquidator during a flash borrower liquidation.

```solidity
    function getExpectedAmount(
        uint256 swapAmount_
    )
        view
        returns (
            uint256 returnAmount_
        );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `swapAmount_` | `uint256` | `uint256` | Amount of collateralAsset being swapped. |


#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `returnAmount_` | `uint256` | `uint256` | Amount of fundsAsset that must be returned in the same transaction. |


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

### `liquidator`

The address of the liquidator.

```solidity
    function liquidator()
        view
        returns (
            address liquidator_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidator_` | `address` | `address` |  |


<br />

### `loan`

The Loan contract this locker is holding tokens for.

```solidity
    function loan()
        view
        returns (
            address loan_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `loan_` | `address` | `address` |  |


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

### `minRatio`

The minimum exchange ration between funds asset and collateral asset.

```solidity
    function minRatio()
        view
        returns (
            uint256 minRatio_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `minRatio_` | `uint256` | `uint256` |  |


<br />

### `pool`

The owner of this Locker (the Pool).

```solidity
    function pool()
        view
        returns (
            address pool_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `pool_` | `address` | `address` |  |


<br />

### `poolDelegate`

Returns the address of the Pool Delegate that has control of the DebtLocker.

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

### `principalRemainingAtLastClaim`

Returns the principal that was present at the time of last claim.

```solidity
    function principalRemainingAtLastClaim()
        view
        returns (
            uint256 principalRemainingAtLastClaim_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `principalRemainingAtLastClaim_` | `uint256` | `uint256` |  |


<br />

### `pullFundsFromLiquidator`

Allows the poolDelegate to pull some funds from liquidator contract.

```solidity
    function pullFundsFromLiquidator(
        address liquidator_,
        address token_,
        address destination_,
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `liquidator_` | `address` | `address` | The liquidator to which pull funds from. |
| 1 | `token_` | `address` | `address` | The token address of the funds. |
| 2 | `destination_` | `address` | `address` | The destination address of captured funds. |
| 3 | `amount_` | `uint256` | `uint256` | The amount to pull. |


<br />

### `rejectNewTerms`

Reject the new loan terms.

```solidity
    function rejectNewTerms(
        address refinancer_,
        uint256 deadline_,
        bytes[] calls_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `refinancer_` | `address` | `address` | The address of the refinancer contract. |
| 1 | `deadline_` | `uint256` | `uint256` | The deadline of the new terms proposal. |
| 2 | `calls_` | `bytes[]` | `bytes[]` | The array of encoded data that are to be executed as delegatecalls by the refinancer. |


<br />

### `repossessed`

Returns if the funds have been repossessed.

```solidity
    function repossessed()
        view
        returns (
            bool repossessed_
        );
```



#### Return Values:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `repossessed_` | `bool` | `bool` |  |


<br />

### `setAllowedSlippage`

Sets the allowed slippage for auctioneer (used to determine expected amount to be returned in flash loan).

```solidity
    function setAllowedSlippage(
        uint256 allowedSlippage_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `allowedSlippage_` | `uint256` | `uint256` | Basis points representation of allowed percent slippage from market price. |


<br />

### `setAuctioneer`

Sets the auctioneer contract for the liquidator.

```solidity
    function setAuctioneer(
        address auctioneer_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `auctioneer_` | `address` | `address` | Address of auctioneer contract. |


<br />

### `setFundsToCapture`

Returns the expected amount to be returned to the liquidator during a flash borrower liquidation.

```solidity
    function setFundsToCapture(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of funds that should be captured next claim. |


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

### `setMinRatio`

Sets the minimum &quot;price&quot; for auctioneer (used to determine expected amount to be returned in flash loan).

```solidity
    function setMinRatio(
        uint256 minRatio_
    )
        nonpayable;
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `minRatio_` | `uint256` | `uint256` | Price in fundsAsset precision (e.g., 10 * 10 ** 6 for $10 price for USDC). |


<br />

### `stopLiquidation`

Called by the PoolDelegate in case of a DoS, where a user transfers small amounts of collateralAsset into the Liquidator      to make &#x60;_isLiquidationActive&#x60; remain true.      CALLING THIS MAY RESULT IN RECOGNIZED LOSSES IN POOL ACCOUNTING. CONSULT MAPLE TEAM FOR GUIDANCE.

```solidity
    function stopLiquidation()
        nonpayable;
```



<br />

### `triggerDefault`

Repossesses funds and collateral from a loan and transfers them to the Liquidator.

```solidity
    function triggerDefault()
        nonpayable;
```



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

### `AllowedSlippageSet`

Emitted when &#x60;setAllowedSlippage&#x60; is called.

```solidity
    event AllowedSlippageSet(
        uint256 newSlippage_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newSlippage_` | `uint256` | `uint256` | New value for &#x60;allowedSlippage&#x60;. |

<br />

### `AuctioneerSet`

Emitted when &#x60;setAuctioneer&#x60; is called.

```solidity
    event AuctioneerSet(
        address newAuctioneer_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newAuctioneer_` | `address` | `address` | New value for &#x60;auctioneer&#x60; in Liquidator. |

<br />

### `FundsToCaptureSet`

Emitted when &#x60;fundsToCapture&#x60; is set.

```solidity
    event FundsToCaptureSet(
        uint256 amount_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `amount_` | `uint256` | `uint256` | The amount of funds that will be captured next claim. |

<br />

### `LiquidationStopped`

Emitted when &#x60;stopLiquidation&#x60; is called.

```solidity
    event LiquidationStopped();
```


<br />

### `MinRatioSet`

Emitted when &#x60;setMinRatio&#x60; is called.

```solidity
    event MinRatioSet(
        uint256 newMinRatio_
    );
```

#### Parameters:
| Index | Name | Type | Internal Type | Description |
| :---: | :--: | :--: | :-----------: | :---------- |
| 0 | `newMinRatio_` | `uint256` | `uint256` | New value for &#x60;minRatio&#x60;. |

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
