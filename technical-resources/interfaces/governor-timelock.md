# GovernorTimelock



## Constructor

```solidity
    constructor(
        address tokenWithdrawer_,
        address proposer_,
        address executor_,
        address canceller_,
        address roleAdmin_
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description |
| :---: | :----------------: | :-------: | :-----------: | ----------- |
|   0   | `tokenWithdrawer_` | `address` |   `address`   |             |
|   1   |     `proposer_`    | `address` |   `address`   |             |
|   2   |     `executor_`    | `address` |   `address`   |             |
|   3   |    `canceller_`    | `address` |   `address`   |             |
|   4   |    `roleAdmin_`    | `address` |   `address`   |             |



## Functions

### `CANCELLER_ROLE`

Returns the bytes32 representation of the canceler role. Address that has the canceler role can unschedule proposals but can not unschedule role updates.

```solidity
    function CANCELLER_ROLE()
        view
        returns (
            bytes32 cancelerRole
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description       |
| :---: | :------------: | :-------: | :-----------: | ----------------- |
|   0   | `cancelerRole` | `bytes32` |   `bytes32`   | The canceler role |



### `EXECUTOR_ROLE`

Returns the bytes32 representation of the executor role. Address that has the executor role can execute all proposals including role updates.

```solidity
    function EXECUTOR_ROLE()
        view
        returns (
            bytes32 executorRole
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description       |
| :---: | :------------: | :-------: | :-----------: | ----------------- |
|   0   | `executorRole` | `bytes32` |   `bytes32`   | The executor role |



### `MIN_DELAY`

Returns the minimum delay for a proposal

```solidity
    function MIN_DELAY()
        view
        returns (
            uint32 minDelay
        );
```

#### Return Values:

| Index |    Name    |   Type   | Internal Type | Description                      |
| :---: | :--------: | :------: | :-----------: | -------------------------------- |
|   0   | `minDelay` | `uint32` |    `uint32`   | The minimum delay for a proposal |



### `MIN_EXECUTION_WINDOW`

Returns the minimum execution window for a proposal

```solidity
    function MIN_EXECUTION_WINDOW()
        view
        returns (
            uint32 minExecutionWindow
        );
```

#### Return Values:

| Index |         Name         |   Type   | Internal Type | Description                                 |
| :---: | :------------------: | :------: | :-----------: | ------------------------------------------- |
|   0   | `minExecutionWindow` | `uint32` |    `uint32`   | The minimum execution window for a proposal |



### `PROPOSER_ROLE`

Returns the bytes32 representation of the proposer role. Address that has the proposer role can schedule proposals but can not schedule role updates.

```solidity
    function PROPOSER_ROLE()
        view
        returns (
            bytes32 proposerRole
        );
```

#### Return Values:

| Index |      Name      |    Type   | Internal Type | Description       |
| :---: | :------------: | :-------: | :-----------: | ----------------- |
|   0   | `proposerRole` | `bytes32` |   `bytes32`   | The proposer role |



### `ROLE_ADMIN`

Returns the bytes32 representation of the role admin role. Address that has the role admin role can update roles including the role admin role itself.

```solidity
    function ROLE_ADMIN()
        view
        returns (
            bytes32 roleAdmin
        );
```

#### Return Values:

| Index |     Name    |    Type   | Internal Type | Description         |
| :---: | :---------: | :-------: | :-----------: | ------------------- |
|   0   | `roleAdmin` | `bytes32` |   `bytes32`   | The role admin role |



### `acceptTokenWithdrawer`

Accepts the token withdrawer role and sets pending token withdrawer to zero address. Only the pending token withdrawer can accept the token withdrawer role.

```solidity
    function acceptTokenWithdrawer()
        nonpayable;
```



### `defaultTimelockParameters`

Returns the default timelock parameters

```solidity
    function defaultTimelockParameters()
        view
        returns (
            uint32 delay,
            uint32 executionWindow
        );
```

#### Return Values:

| Index |        Name       |   Type   | Internal Type | Description          |
| :---: | :---------------: | :------: | :-----------: | -------------------- |
|   0   |      `delay`      | `uint32` |    `uint32`   | The delay            |
|   1   | `executionWindow` | `uint32` |    `uint32`   | The execution window |



### `executeProposals`

Executes proposals. The proposalIds, targets and data arrays must have the same length.

```solidity
    function executeProposals(
        uint256[] proposalIds,
        address[] targets,
        bytes[] data
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |     Type    | Internal Type | Description                                                         |
| :---: | :-----------: | :---------: | :-----------: | ------------------------------------------------------------------- |
|   0   | `proposalIds` | `uint256[]` |  `uint256[]`  | The ids of the proposals to execute                                 |
|   1   |   `targets`   | `address[]` |  `address[]`  | The targets of the proposals                                        |
|   2   |     `data`    |  `bytes[]`  |   `bytes[]`   | The calldata of the proposals that the contract is going to execute |



### `functionTimelockParameters`

Returns the timelock parameters for a given target and function selector

```solidity
    function functionTimelockParameters(
        address target,
        bytes4 functionSelector
    )
        view
        returns (
            uint32 delay,
            uint32 executionWindow
        );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                |
| :---: | :----------------: | :-------: | :-----------: | -------------------------- |
|   0   |      `target`      | `address` |   `address`   | The target of the function |
|   1   | `functionSelector` |  `bytes4` |    `bytes4`   | The function selector      |

#### Return Values:

| Index |        Name       |   Type   | Internal Type | Description          |
| :---: | :---------------: | :------: | :-----------: | -------------------- |
|   0   |      `delay`      | `uint32` |    `uint32`   | The delay            |
|   1   | `executionWindow` | `uint32` |    `uint32`   | The execution window |



### `hasRole`

Checks if an account has a role

```solidity
    function hasRole(
        address account,
        bytes32 role
    )
        view
        returns (
            bool doesHaveRole
        );
```

#### Parameters:

| Index |    Name   |    Type   | Internal Type | Description          |
| :---: | :-------: | :-------: | :-----------: | -------------------- |
|   0   | `account` | `address` |   `address`   | The account to check |
|   1   |   `role`  | `bytes32` |   `bytes32`   | The role to check    |

#### Return Values:

| Index |      Name      |  Type  | Internal Type | Description                      |
| :---: | :------------: | :----: | :-----------: | -------------------------------- |
|   0   | `doesHaveRole` | `bool` |     `bool`    | Whether the account has the role |



### `isExecutable`

Checks if a proposal is executable

```solidity
    function isExecutable(
        uint256 proposalId
    )
        view
        returns (
            bool isExecutable
        );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description            |
| :---: | :----------: | :-------: | :-----------: | ---------------------- |
|   0   | `proposalId` | `uint256` |   `uint256`   | The id of the proposal |

#### Return Values:

| Index |      Name      |  Type  | Internal Type | Description                        |
| :---: | :------------: | :----: | :-----------: | ---------------------------------- |
|   0   | `isExecutable` | `bool` |     `bool`    | Whether the proposal is executable |



### `latestProposalId`

Returns the latest proposal id

```solidity
    function latestProposalId()
        view
        returns (
            uint256 latestProposalId
        );
```

#### Return Values:

| Index |        Name        |    Type   | Internal Type | Description            |
| :---: | :----------------: | :-------: | :-----------: | ---------------------- |
|   0   | `latestProposalId` | `uint256` |   `uint256`   | The latest proposal id |



### `pendingTokenWithdrawer`

Returns the pending token withdrawer

```solidity
    function pendingTokenWithdrawer()
        view
        returns (
            address pendingTokenWithdrawer
        );
```

#### Return Values:

| Index |           Name           |    Type   | Internal Type | Description                                 |
| :---: | :----------------------: | :-------: | :-----------: | ------------------------------------------- |
|   0   | `pendingTokenWithdrawer` | `address` |   `address`   | The address of the pending token withdrawer |



### `proposals`

Returns the proposal for a given proposal id

```solidity
    function proposals(
        uint256 proposalId
    )
        view
        returns (
            bytes32 proposalHash,
            bool isUnschedulable,
            uint32 scheduledAt,
            uint32 delayedUntil,
            uint32 validUntil
        );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description            |
| :---: | :----------: | :-------: | :-----------: | ---------------------- |
|   0   | `proposalId` | `uint256` |   `uint256`   | The id of the proposal |

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                                   |
| :---: | :---------------: | :-------: | :-----------: | --------------------------------------------- |
|   0   |   `proposalHash`  | `bytes32` |   `bytes32`   | The hash of the proposal                      |
|   1   | `isUnschedulable` |   `bool`  |     `bool`    | Whether the proposal is unschedulable         |
|   2   |   `scheduledAt`   |  `uint32` |    `uint32`   | The timestamp when the proposal was scheduled |
|   3   |   `delayedUntil`  |  `uint32` |    `uint32`   | The timestamp when the proposal was delayed   |
|   4   |    `validUntil`   |  `uint32` |    `uint32`   | The timestamp when the proposal was valid     |



### `proposeRoleUpdates`

Proposes to update roles. The role updating needs to be done through the timelock contract.

```solidity
    function proposeRoleUpdates(
        bytes32[] roles,
        address[] accounts,
        bool[] shouldGrant
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |     Type    | Internal Type | Description                          |
| :---: | :-----------: | :---------: | :-----------: | ------------------------------------ |
|   0   |    `roles`    | `bytes32[]` |  `bytes32[]`  | The roles to update                  |
|   1   |   `accounts`  | `address[]` |  `address[]`  | The accounts to update the roles for |
|   2   | `shouldGrant` |   `bool[]`  |    `bool[]`   | Whether to grant or revoke the roles |



### `scheduleProposals`

Schedules proposals. The targets and data arrays must have the same length.

```solidity
    function scheduleProposals(
        address[] targets,
        bytes[] data
    )
        nonpayable;
```

#### Parameters:

| Index |    Name   |     Type    | Internal Type | Description                                                         |
| :---: | :-------: | :---------: | :-----------: | ------------------------------------------------------------------- |
|   0   | `targets` | `address[]` |  `address[]`  | The targets of the proposals                                        |
|   1   |   `data`  |  `bytes[]`  |   `bytes[]`   | The calldata of the proposals that the contract is going to execute |



### `setDefaultTimelockParameters`

Sets the default timelock parameters

```solidity
    function setDefaultTimelockParameters(
        uint32 delay,
        uint32 executionWindow
    )
        nonpayable;
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description                      |
| :---: | :---------------: | :------: | :-----------: | -------------------------------- |
|   0   |      `delay`      | `uint32` |    `uint32`   | The new default delay            |
|   1   | `executionWindow` | `uint32` |    `uint32`   | The new default execution window |



### `setFunctionTimelockParameters`

Sets the function timelock parameters

```solidity
    function setFunctionTimelockParameters(
        address target,
        bytes4 functionSelector,
        uint32 delay,
        uint32 executionWindow
    )
        nonpayable;
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                |
| :---: | :----------------: | :-------: | :-----------: | -------------------------- |
|   0   |      `target`      | `address` |   `address`   | The target of the function |
|   1   | `functionSelector` |  `bytes4` |    `bytes4`   | The function selector      |
|   2   |       `delay`      |  `uint32` |    `uint32`   | The new delay              |
|   3   |  `executionWindow` |  `uint32` |    `uint32`   | The new execution window   |



### `setPendingTokenWithdrawer`

Sets the pending token withdrawer. Only the token withdrawer can set the pending token withdrawer.

```solidity
    function setPendingTokenWithdrawer(
        address newPendingTokenWithdrawer
    )
        nonpayable;
```

#### Parameters:

| Index |             Name            |    Type   | Internal Type | Description                                     |
| :---: | :-------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `newPendingTokenWithdrawer` | `address` |   `address`   | The address of the new pending token withdrawer |



### `tokenWithdrawer`

Returns the token withdrawer

```solidity
    function tokenWithdrawer()
        view
        returns (
            address tokenWithdrawer
        );
```

#### Return Values:

| Index |        Name       |    Type   | Internal Type | Description                         |
| :---: | :---------------: | :-------: | :-----------: | ----------------------------------- |
|   0   | `tokenWithdrawer` | `address` |   `address`   | The address of the token withdrawer |



### `unscheduleProposals`

Unschedule proposals. The proposalIds array must not contain duplicates.

```solidity
    function unscheduleProposals(
        uint256[] proposalIds
    )
        nonpayable;
```

#### Parameters:

| Index |      Name     |     Type    | Internal Type | Description                            |
| :---: | :-----------: | :---------: | :-----------: | -------------------------------------- |
|   0   | `proposalIds` | `uint256[]` |  `uint256[]`  | The ids of the proposals to unschedule |



### `updateRole`

Updates a role. The role updating needs to be done through the timelock contract.

```solidity
    function updateRole(
        bytes32 role,
        address account,
        bool grantRole
    )
        nonpayable;
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                            |
| :---: | :---------: | :-------: | :-----------: | -------------------------------------- |
|   0   |    `role`   | `bytes32` |   `bytes32`   | The role to update                     |
|   1   |  `account`  | `address` |   `address`   | The account to update the role for     |
|   2   | `grantRole` |   `bool`  |     `bool`    | Whether the role is granted or revoked |



### `withdrawERC20Token`

Withdraws tokens from the governor timelock contract. Only the token withdrawer can withdraw tokens and tokens are sent to the token withdrawer.

```solidity
    function withdrawERC20Token(
        address token,
        uint256 amount
    )
        nonpayable;
```

#### Parameters:

| Index |   Name   |    Type   | Internal Type | Description                          |
| :---: | :------: | :-------: | :-----------: | ------------------------------------ |
|   0   |  `token` | `address` |   `address`   | The address of the token to withdraw |
|   1   | `amount` | `uint256` |   `uint256`   | The amount of tokens to withdraw     |



## Events

### `DefaultTimelockSet`

Emitted when the default timelock parameters are set

```solidity
    event DefaultTimelockSet(
        uint32 delay,
        uint32 executionWindow
    );
```

#### Parameters:

| Index |        Name       |   Type   | Internal Type | Description                      |
| :---: | :---------------: | :------: | :-----------: | -------------------------------- |
|   0   |      `delay`      | `uint32` |    `uint32`   | The new default delay            |
|   1   | `executionWindow` | `uint32` |    `uint32`   | The new default execution window |



### `ERC20TokenWithdrawn`

Emitted when tokens are withdrawn from the governor timelock contract

```solidity
    event ERC20TokenWithdrawn(
        address token,
        address receiver,
        uint256 amount
    );
```

#### Parameters:

| Index |    Name    |    Type   | Internal Type | Description                               |
| :---: | :--------: | :-------: | :-----------: | ----------------------------------------- |
|   0   |   `token`  | `address` |   `address`   | The address of the token withdrawn        |
|   1   | `receiver` | `address` |   `address`   | The address of the receiver of the tokens |
|   2   |  `amount`  | `uint256` |   `uint256`   | The amount of tokens withdrawn            |



### `FunctionTimelockSet`

Emitted when the function timelock parameters are set

```solidity
    event FunctionTimelockSet(
        address target,
        bytes4 functionSelector,
        uint32 delay,
        uint32 executionWindow
    );
```

#### Parameters:

| Index |        Name        |    Type   | Internal Type | Description                |
| :---: | :----------------: | :-------: | :-----------: | -------------------------- |
|   0   |      `target`      | `address` |   `address`   | The target of the function |
|   1   | `functionSelector` |  `bytes4` |    `bytes4`   | The function selector      |
|   2   |       `delay`      |  `uint32` |    `uint32`   | The new delay              |
|   3   |  `executionWindow` |  `uint32` |    `uint32`   | The new execution window   |



### `PendingTokenWithdrawerSet`

Emitted when the pending token withdrawer is set

```solidity
    event PendingTokenWithdrawerSet(
        address newPendingTokenWithdrawer
    );
```

#### Parameters:

| Index |             Name            |    Type   | Internal Type | Description                                     |
| :---: | :-------------------------: | :-------: | :-----------: | ----------------------------------------------- |
|   0   | `newPendingTokenWithdrawer` | `address` |   `address`   | The address of the new pending token withdrawer |



### `ProposalExecuted`

Emitted when a proposal is executed

```solidity
    event ProposalExecuted(
        uint256 proposalId
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description            |
| :---: | :----------: | :-------: | :-----------: | ---------------------- |
|   0   | `proposalId` | `uint256` |   `uint256`   | The id of the proposal |



### `ProposalScheduled`

Emitted when a proposal is scheduled

```solidity
    event ProposalScheduled(
        uint256 proposalId,
        Proposal proposal
    );
```

#### Parameters:

| Index |     Name     |    Type   |            Internal Type            | Description            |
| :---: | :----------: | :-------: | :---------------------------------: | ---------------------- |
|   0   | `proposalId` | `uint256` |              `uint256`              | The id of the proposal |
|   1   |  `proposal`  |  `tuple`  | `struct IGovernorTimelock.Proposal` | The proposal           |



### `ProposalUnscheduled`

Emitted when a proposal is unscheduled

```solidity
    event ProposalUnscheduled(
        uint256 proposalId
    );
```

#### Parameters:

| Index |     Name     |    Type   | Internal Type | Description            |
| :---: | :----------: | :-------: | :-----------: | ---------------------- |
|   0   | `proposalId` | `uint256` |   `uint256`   | The id of the proposal |



### `RoleUpdated`

Emitted when a role is updated

```solidity
    event RoleUpdated(
        bytes32 role,
        address account,
        bool grantRole
    );
```

#### Parameters:

| Index |     Name    |    Type   | Internal Type | Description                            |
| :---: | :---------: | :-------: | :-----------: | -------------------------------------- |
|   0   |    `role`   | `bytes32` |   `bytes32`   | The role updated                       |
|   1   |  `account`  | `address` |   `address`   | The account updated the role for       |
|   2   | `grantRole` |   `bool`  |     `bool`    | Whether the role is granted or revoked |



### `TokenWithdrawerAccepted`

Emitted when the token withdrawer is accepted

```solidity
    event TokenWithdrawerAccepted(
        address tokenWithdrawer
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                             |
| :---: | :---------------: | :-------: | :-----------: | --------------------------------------- |
|   0   | `tokenWithdrawer` | `address` |   `address`   | The address of the new token withdrawer |



## Structs

### `Proposal`

```solidity
    struct Proposal {
        bytes32 proposalHash;
        bool isUnschedulable;
        uint32 scheduledAt;
        uint32 delayedUntil;
        uint32 validUntil;
    }
```

#### Members:

| Index |        Name       |    Type   | Internal Type | Description |
| :---: | :---------------: | :-------: | :-----------: | ----------- |
|   0   |   `proposalHash`  | `bytes32` |   `bytes32`   |             |
|   1   | `isUnschedulable` |   `bool`  |     `bool`    |             |
|   2   |   `scheduledAt`   |  `uint32` |    `uint32`   |             |
|   3   |   `delayedUntil`  |  `uint32` |    `uint32`   |             |
|   4   |    `validUntil`   |  `uint32` |    `uint32`   |             |

