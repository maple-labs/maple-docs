# OpenTermLoanRefinancer



## Functions

### `borrower`

```solidity
    function borrower()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `calledPrincipal`

```solidity
    function calledPrincipal()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



### `dateCalled`

```solidity
    function dateCalled()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `dateFunded`

```solidity
    function dateFunded()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `dateImpaired`

```solidity
    function dateImpaired()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `datePaid`

```solidity
    function datePaid()
        view
        returns (
            uint40
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint40` |    `uint40`   |             |



### `decreasePrincipal`

Function to decrease the principal during a refinance.

```solidity
    function decreasePrincipal(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                     |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `amount_` | `uint256` |   `uint256`   | The amount of which the value will decrease by. |



### `delegateServiceFeeRate`

```solidity
    function delegateServiceFeeRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `fundsAsset`

```solidity
    function fundsAsset()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `gracePeriod`

```solidity
    function gracePeriod()
        view
        returns (
            uint32
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint32` |    `uint32`   |             |



### `increasePrincipal`

Function to increase the principal during a refinance.

```solidity
    function increasePrincipal(
        uint256 amount_
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description                                     |
| :---: | :-------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `amount_` | `uint256` |   `uint256`   | The amount of which the value will increase by. |



### `interestRate`

```solidity
    function interestRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `lateFeeRate`

```solidity
    function lateFeeRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `lateInterestPremiumRate`

```solidity
    function lateInterestPremiumRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `lender`

```solidity
    function lender()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `noticePeriod`

```solidity
    function noticePeriod()
        view
        returns (
            uint32
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint32` |    `uint32`   |             |



### `paymentInterval`

```solidity
    function paymentInterval()
        view
        returns (
            uint32
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint32` |    `uint32`   |             |



### `pendingBorrower`

```solidity
    function pendingBorrower()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `pendingLender`

```solidity
    function pendingLender()
        view
        returns (
            address
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `address` |   `address`   |             |



### `platformServiceFeeRate`

```solidity
    function platformServiceFeeRate()
        view
        returns (
            uint64
        );
```

#### Return Values:

| Index | Name |   Type   | Internal Type | Description |
| :---: | :--: | :------: | :-----------: | ----------- |
|   0   |      | `uint64` |    `uint64`   |             |



### `principal`

```solidity
    function principal()
        view
        returns (
            uint256
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `uint256` |   `uint256`   |             |



### `refinanceCommitment`

```solidity
    function refinanceCommitment()
        view
        returns (
            bytes32
        );
```

#### Return Values:

| Index | Name |    Type   | Internal Type | Description |
| :---: | :--: | :-------: | :-----------: | ----------- |
|   0   |      | `bytes32` |   `bytes32`   |             |



### `setDelegateServiceFeeRate`

Function to set the delegateServiceFeeRate during a refinance. The rate is denominated in 1e18 units.

```solidity
    function setDelegateServiceFeeRate(
        uint64 delegateServiceFeeRate_
    )
        nonpayable;
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                               |
| :---: | :-----------------------: | :------: | :-----------: | ----------------------------------------- |
|   0   | `delegateServiceFeeRate_` | `uint64` |    `uint64`   | The new value for delegateServiceFeeRate. |



### `setGracePeriod`

Function to set the gracePeriod during a refinance.

```solidity
    function setGracePeriod(
        uint32 gracePeriod_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |   Type   | Internal Type | Description                    |
| :---: | :------------: | :------: | :-----------: | ------------------------------ |
|   0   | `gracePeriod_` | `uint32` |    `uint32`   | The new value for gracePeriod. |



### `setInterestRate`

Function to set the interestRate during a refinance. The interest rate is measured with 18 decimals of precision.

```solidity
    function setInterestRate(
        uint64 interestRate_
    )
        nonpayable;
```

#### Parameters:

| Index |       Name      |   Type   | Internal Type | Description                     |
| :---: | :-------------: | :------: | :-----------: | ------------------------------- |
|   0   | `interestRate_` | `uint64` |    `uint64`   | The new value for interestRate. |



### `setLateFeeRate`

Function to set the lateFeeRate during a refinance.

```solidity
    function setLateFeeRate(
        uint64 lateFeeRate_
    )
        nonpayable;
```

#### Parameters:

| Index |      Name      |   Type   | Internal Type | Description                    |
| :---: | :------------: | :------: | :-----------: | ------------------------------ |
|   0   | `lateFeeRate_` | `uint64` |    `uint64`   | The new value for lateFeeRate. |



### `setLateInterestPremiumRate`

Function to set the lateInterestPremiumRate during a refinance.

```solidity
    function setLateInterestPremiumRate(
        uint64 lateInterestPremiumRate_
    )
        nonpayable;
```

#### Parameters:

| Index |            Name            |   Type   | Internal Type | Description                                |
| :---: | :------------------------: | :------: | :-----------: | ------------------------------------------ |
|   0   | `lateInterestPremiumRate_` | `uint64` |    `uint64`   | The new value for lateInterestPremiumRate. |



### `setNoticePeriod`

Function to set the noticePeriod during a refinance.

```solidity
    function setNoticePeriod(
        uint32 noticePeriod_
    )
        nonpayable;
```

#### Parameters:

| Index |       Name      |   Type   | Internal Type | Description                     |
| :---: | :-------------: | :------: | :-----------: | ------------------------------- |
|   0   | `noticePeriod_` | `uint32` |    `uint32`   | The new value for noticePeriod. |



### `setPaymentInterval`

Function to set the paymentInterval during a refinance. The interval is denominated in seconds.

```solidity
    function setPaymentInterval(
        uint32 paymentInterval_
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |   Type   | Internal Type | Description                        |
| :---: | :----------------: | :------: | :-----------: | ---------------------------------- |
|   0   | `paymentInterval_` | `uint32` |    `uint32`   | The new value for paymentInterval. |



## Events

### `DelegateServiceFeeRateSet`

The value for the service fee rate for the PoolDelegate (1e18 units).

```solidity
    event DelegateServiceFeeRateSet(
        uint64 delegateServiceFeeRate_
    );
```

#### Parameters:

| Index |            Name           |   Type   | Internal Type | Description                               |
| :---: | :-----------------------: | :------: | :-----------: | ----------------------------------------- |
|   0   | `delegateServiceFeeRate_` | `uint64` |    `uint64`   | The new value for delegateServiceFeeRate. |



### `GracePeriodSet`

A new value for gracePeriod has been set.

```solidity
    event GracePeriodSet(
        uint256 gracePeriod_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                    |
| :---: | :------------: | :-------: | :-----------: | ------------------------------ |
|   0   | `gracePeriod_` | `uint256` |   `uint256`   | The new value for gracePeriod. |



### `InterestRateSet`

A new value for interestRate has been set.

```solidity
    event InterestRateSet(
        uint64 interestRate_
    );
```

#### Parameters:

| Index |       Name      |   Type   | Internal Type | Description                     |
| :---: | :-------------: | :------: | :-----------: | ------------------------------- |
|   0   | `interestRate_` | `uint64` |    `uint64`   | The new value for interestRate. |



### `LateFeeRateSet`

A new value for lateFeeRate has been set.

```solidity
    event LateFeeRateSet(
        uint64 lateFeeRate_
    );
```

#### Parameters:

| Index |      Name      |   Type   | Internal Type | Description                    |
| :---: | :------------: | :------: | :-----------: | ------------------------------ |
|   0   | `lateFeeRate_` | `uint64` |    `uint64`   | The new value for lateFeeRate. |



### `LateInterestPremiumRateSet`

A new value for lateInterestPremiumRate has been set.

```solidity
    event LateInterestPremiumRateSet(
        uint64 lateInterestPremiumRate_
    );
```

#### Parameters:

| Index |            Name            |   Type   | Internal Type | Description                                |
| :---: | :------------------------: | :------: | :-----------: | ------------------------------------------ |
|   0   | `lateInterestPremiumRate_` | `uint64` |    `uint64`   | The new value for lateInterestPremiumRate. |



### `NoticePeriodSet`

A new value for noticePeriod has been set.

```solidity
    event NoticePeriodSet(
        uint256 noticePeriod_
    );
```

#### Parameters:

| Index |       Name      |    Type   | Internal Type | Description                      |
| :---: | :-------------: | :-------: | :-----------: | -------------------------------- |
|   0   | `noticePeriod_` | `uint256` |   `uint256`   | The new value for noticedPeriod. |



### `PaymentIntervalSet`

A new value for paymentInterval has been set.

```solidity
    event PaymentIntervalSet(
        uint256 paymentInterval_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                        |
| :---: | :----------------: | :-------: | :-----------: | ---------------------------------- |
|   0   | `paymentInterval_` | `uint256` |   `uint256`   | The new value for paymentInterval. |



### `PrincipalDecreased`

The value of the principal has been decreased.

```solidity
    event PrincipalDecreased(
        uint256 decreasedBy_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                     |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `decreasedBy_` | `uint256` |   `uint256`   | The amount of which the value was decreased by. |



### `PrincipalIncreased`

The value of the principal has been increased.

```solidity
    event PrincipalIncreased(
        uint256 increasedBy_
    );
```

#### Parameters:

| Index |      Name      |    Type   | Internal Type | Description                                     |
| :---: | :------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `increasedBy_` | `uint256` |   `uint256`   | The amount of which the value was increased by. |

