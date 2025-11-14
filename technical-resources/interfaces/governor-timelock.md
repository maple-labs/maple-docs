# GovernorTimelock

On‑chain administrative gateway for governor‑privileged actions. Enforces time‑delayed execution via scheduled proposals and per‑function timelock parameters. Manages proposer/executor/canceller roles and supports role updates through the timelock itself.


## Functions

### `CANCELLER_ROLE`

Returns the bytes32 representation of the canceller role.

```solidity
    function CANCELLER_ROLE()
        view
        returns (
            bytes32 cancelerRole
        );
```



### `EXECUTOR_ROLE`

Returns the bytes32 representation of the executor role.

```solidity
    function EXECUTOR_ROLE()
        view
        returns (
            bytes32 executorRole
        );
```



### `PROPOSER_ROLE`

Returns the bytes32 representation of the proposer role.

```solidity
    function PROPOSER_ROLE()
        view
        returns (
            bytes32 proposerRole
        );
```



### `ROLE_ADMIN`

Returns the bytes32 representation of the role admin.

```solidity
    function ROLE_ADMIN()
        view
        returns (
            bytes32 roleAdmin
        );
```



### `MIN_DELAY`

Returns the minimum allowed delay (seconds).

```solidity
    function MIN_DELAY()
        view
        returns (
            uint32
        );
```



### `MIN_EXECUTION_WINDOW`

Returns the minimum allowed execution window (seconds).

```solidity
    function MIN_EXECUTION_WINDOW()
        view
        returns (
            uint32
        );
```



### `defaultTimelockParameters`

Returns the default timelock parameters.

```solidity
    function defaultTimelockParameters()
        view
        returns (
            uint32 delay,
            uint32 executionWindow
        );
```



### `setDefaultTimelockParameters`

Sets the default timelock parameters (only via timelock itself).

```solidity
    function setDefaultTimelockParameters(
        uint32 delay,
        uint32 executionWindow
    )
        external;
```

#### Parameters:

| Index |      Name       |   Type   | Internal Type | Description                 |
| :---: | :-------------: | :------: | :-----------: | --------------------------- |
|   0   |    `delay`      | `uint32` |   `uint32`    | New default delay (seconds) |
|   1   | `executionWindow` | `uint32` |   `uint32`  | New default window (seconds) |



### `setFunctionTimelockParameters`

Sets per‑function timelock parameters (only via timelock itself).

```solidity
    function setFunctionTimelockParameters(
        address target,
        bytes4  functionSelector,
        uint32  delay,
        uint32  executionWindow
    )
        external;
```

#### Parameters:

| Index |        Name         |   Type   | Internal Type | Description                             |
| :---: | :-----------------: | :------: | :-----------: | --------------------------------------- |
|   0   |      `target`       | `address`|   `address`   | Target contract address                  |
|   1   | `functionSelector`  | `bytes4` |   `bytes4`    | Function selector                        |
|   2   |       `delay`       | `uint32` |   `uint32`    | Delay for this function (seconds)        |
|   3   |  `executionWindow`  | `uint32` |   `uint32`    | Execution window for this function       |



### `scheduleProposals`

Schedules proposals for execution after the delay.

```solidity
    function scheduleProposals(
        address[] targets,
        bytes[]   data
    )
        external;
```

#### Parameters:

| Index |   Name    |    Type    | Internal Type | Description                          |
| :---: | :-------: | :--------: | :-----------: | ------------------------------------ |
|   0   | `targets` | `address[]`|  `address[]`  | Target contract addresses to call    |
|   1   |  `data`   |  `bytes[]` |   `bytes[]`   | Encoded calldata for each target     |



### `unscheduleProposals`

Unschedules proposals by id (non‑role updates only).

```solidity
    function unscheduleProposals(
        uint256[] proposalIds
    )
        external;
```

#### Parameters:

| Index |     Name      |     Type     | Internal Type | Description               |
| :---: | :-----------: | :----------: | :-----------: | ------------------------- |
|   0   | `proposalIds` | `uint256[]`  |  `uint256[]`  | IDs of proposals to cancel |



### `executeProposals`

Executes proposals within their execution window.

```solidity
    function executeProposals(
        uint256[] proposalIds,
        address[] targets,
        bytes[]   data
    )
        external;
```

#### Parameters:

| Index |     Name      |     Type     | Internal Type | Description                                |
| :---: | :-----------: | :----------: | :-----------: | ------------------------------------------ |
|   0   | `proposalIds` | `uint256[]`  |  `uint256[]`  | IDs of proposals to execute                 |
|   1   |  `targets`    | `address[]`  |  `address[]`  | Target contract addresses                   |
|   2   |    `data`     |  `bytes[]`   |   `bytes[]`   | Encoded calldata for each target            |



### `proposeRoleUpdates`

Proposes role grants/revocations (must be executed via timelock).

```solidity
    function proposeRoleUpdates(
        bytes32[] roles,
        address[] accounts,
        bool[]    shouldGrant
    )
        external;
```

#### Parameters:

| Index |     Name     |    Type    | Internal Type | Description                         |
| :---: | :----------: | :--------: | :-----------: | ----------------------------------- |
|   0   |   `roles`    | `bytes32[]`|  `bytes32[]`  | Roles to update                      |
|   1   |  `accounts`  | `address[]`|  `address[]`  | Accounts to apply role changes to    |
|   2   | `shouldGrant`|  `bool[]`  |    `bool[]`   | true to grant, false to revoke       |



### `updateRole`

Updates a role (callable only by the timelock itself during execution).

```solidity
    function updateRole(
        bytes32 role,
        address account,
        bool    grantRole
    )
        external;
```

#### Parameters:

| Index |    Name     |   Type   | Internal Type | Description               |
| :---: | :---------: | :------: | :-----------: | ------------------------- |
|   0   |   `role`    | `bytes32`|   `bytes32`   | Role identifier            |
|   1   |  `account`  | `address`|   `address`   | Account to update          |
|   2   | `grantRole` |  `bool`  |     `bool`    | true to grant, false revoke|



### `isExecutable`

Returns true if a proposalId is executable now.

```solidity
    function isExecutable(
        uint256 proposalId
    )
        view
        returns (
            bool isExecutable_
        );
```

#### Parameters:

| Index |     Name     |   Type    | Internal Type | Description                |
| :---: | :----------: | :-------: | :-----------: | -------------------------- |
|   0   | `proposalId` | `uint256` |   `uint256`   | Proposal to check timing   |

## Events

### `DefaultTimelockSet`

```solidity
event DefaultTimelockSet(
    uint32 delay,
    uint32 executionWindow
);
```

### `ERC20TokenWithdrawn`

```solidity
event ERC20TokenWithdrawn(
    address indexed token,
    address indexed receiver,
    uint256 amount
);
```

### `FunctionTimelockSet`

```solidity
event FunctionTimelockSet(
    address indexed target,
    bytes4  indexed functionSelector,
    uint32  delay,
    uint32  executionWindow
);
```

### `PendingTokenWithdrawerSet`

```solidity
event PendingTokenWithdrawerSet(
    address indexed newPendingTokenWithdrawer
);
```

### `ProposalExecuted`

```solidity
event ProposalExecuted(
    uint256 indexed proposalId
);
```

### `ProposalScheduled`

```solidity
event ProposalScheduled(
    uint256 indexed proposalId,
    Proposal proposal
);
```

### `ProposalUnscheduled`

```solidity
event ProposalUnscheduled(
    uint256 indexed proposalId
);
```

### `RoleUpdated`

```solidity
event RoleUpdated(
    bytes32 indexed role,
    address indexed account,
    bool    grantRole
);
```

### `TokenWithdrawerAccepted`

```solidity
event TokenWithdrawerAccepted(
    address indexed tokenWithdrawer
);
```
