# Smart Contract Architecture

In this section, the architecture of the Maple protocol is outlined, including the rationale behind each decision.

![Protocol Architecture](../../.gitbook/assets/SystemArchitecture.png)

## [Pool](../pools/pools.md)

The pool implements the vault standard ([ERC4626](https://erc4626.info/)) and it is intentionally kept as simple as possible, containing mostly token and deposit/withdrawal functionality. It's the only contract that LPs need to interact with to participate in the protocol. Due to immutability, some of the logic is delegated to the contract called `PoolManager`, which is the only external facing contract that the Pool interacts with.

## [PoolManager](../pools/pool-manager.md)

Pools and PoolManagers currently have a one-to-one relationship (architecturally this is allowed to change), meaning that a single Pool contract is associated with a single PoolManager and vice versa. Its main responsibility is to hold almost all of the administrative functions, as well as serve as the interface between the Pool and the other parts of the protocol architecture.

The main actors that interact with the PoolManager are the Pool Delegate, Governor, Operational Admin and other Maple contracts. No external facing actor is expected to use the Pool Manager directly. The Pool Delegate uses the PoolManager to set Pool parameters, such as liquidity cap, fees and the cap on each strategy. The PoolManager funds two kinds of strategy: the Pool's Open Term Loan Manager and shared Strategy Managers. Other contracts use the PoolManager to route calls to the Pool to perform operations such as withdrawals.

## Open Term Loan Manager (Primary yield strategy)

The Open Term Loan Manager is used to keep track of all outstanding Loan accounting for its Pool. It only interacts with and reports to a single PoolManager. The accounting is done on a separate contract and not directly on the Pool because it allows for future flexibility. It is possible to completely change the existing value accrual mechanism, or support multiple value accrual mechanisms in parallel in the future, without needing to migrate pool tokens. The Open Term Loan Manager is attached to the PoolManager as a strategy via `addStrategy` using the Open Term Loan Manager factory.

## Loans

A MapleLoan is the contract that represents the agreement between a Lender and a Borrower, defining all of the rules of the engagement. In it, all of the term details are set and enforced. This includes Loan terms, payment schedules, fee structures, and default conditions. Loans are the mechanism through which the revenue is generated for Pool Delegates and the Maple protocol, as well as yield for Liquidity Providers. All Loans in the Maple protocol are open-term Loans. See [Open Term Loans](../strategies/open-term-loans/README.md).

## Strategy Managers (Secondary yield strategy)

Pools earn yield on capital they are not lending through shared strategies. A shared strategy is two contracts. The [Strategy Manager](../strategies/strategy-manager.md) tracks each Pool's share of one position, and several Pools can fund it at once. The Underlying Strategy deploys that capital to one underlying protocol: [Aave V3](../strategies/aave-v3-strategy/README.md), [Sky](../strategies/sky-strategy/README.md), or Managed Wallets through the [Allocation Strategy](../strategies/allocation-strategy/README.md). A Strategy Manager only accepts Pool Managers as funders, and it never holds assets itself.

## Liquidity Router

The [Liquidity Router](../strategies/liquidity-router.md) lets Maple's Liquidity Bots batch funding and redemption actions across several Strategy Managers in one transaction. It holds no assets and grants no permission beyond what each Strategy Manager already allows.

## WithdrawalManager

In order to maximize capital efficiency, at any given time, the majority of the assets deposited by Liquidity Providers are directed towards funding loans and therefore, are not available to be withdrawn by LPs. Although depositors are entitled to the full value of their position, full liquidity might not be available at any given time. To address this in an equitable way, the WithdrawalManager contract is used.

Each Pool has a queue-based WithdrawalManager that processes withdrawal requests in the order they were made. See [Withdrawal Manager](../pools/withdrawal-manager.md).

## [Maple Globals](../singletons/globals.md)

MapleGlobals is a singleton contract responsible for holding protocol-wide parameters. The administrative actor of MapleGlobals is the `Governor` which can configure all the needed parameters in a central place. The `Governor` acts on behalf of the Maple DAO.

The MapleGlobals contract is also used to perform and control [time-locked](../admin-functions/timelocks.md) actions, such as smart contract upgrades, which can directly affect depositors.

## Factories

Within the Maple protocol there will be multiple instances of each contract described above, so for efficiency of deployment, a factory pattern is employed. Factories are contracts that are responsible to create new instances of specific contracts and to manage and perform upgrades. Factories are managed in an allowlist in MapleGlobals, maintained by the Governor. This allows protocol contracts to verify on-chain that contracts have been vetted by the Maple DAO. For example, a Loan Manager can check if it is funding a Loan that is part of the Maple protocol, as to avoid funding a Loan with malicious smart contract logic. Further, factories rely on MapleGlobals to determine if their caller is allowed to deploy an instance.

The [Pool Deployer](../pools/pool-creation.md) and the [Strategy Deployer](../strategies/strategy-deployer.md) use these factories to create a new Pool or shared strategy, with all of its contracts, in one transaction.
