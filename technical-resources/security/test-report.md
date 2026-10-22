# Test Report

The v7 contracts are tested with Foundry in the `maple-core-v2-private` repository, which imports every protocol module as a submodule. This page describes the test suites and how to run them. Maple produces the full test output for each release.

## Test suites

Counts are taken from the v7 sources. A test is a `test`, `invariant` or `statefulFuzz` function in a `.t.sol` file.

| Suite | Path | Files | Tests | What it covers |
| --- | --- | --- | --- | --- |
| Integration | `tests/integration` | 86 | 1,293 | Each external function of each contract, including access control, pause checks and revert conditions. Grouped by contract: Pool, Pool Manager, Withdrawal Manager, Pool Permission Manager, Globals, Governor Timelock, Open Term Loan, Open Term Loan Manager, Strategy Manager, Liquidity Router, Aave V3, Sky and Allocation strategies, and the Syrup router. |
| Fuzz | `tests/fuzz` | 23 | 59 | Randomised inputs for Pool accounting, open-term loans and the three underlying strategies. |
| Invariants | `tests/invariants` | 8 | 7 | Stateful fuzzing. Handlers perform random sequences of deposits, fundings, redemptions, impairments, losses and yield, and the properties on the [Invariants](protocol-invariants.md) page are asserted after every step. |
| End-to-end | `tests/e2e` | 25 | 61 | Multi-step scenarios: deployment configurations, several Pools sharing one Strategy Manager, impairment and recovery, fee collection and rate changes, and venue outages such as a halted Sky PSM. |
| Protocol upgrade | `tests/protocol-upgrade` | 24 | 74 | Rehearsals of mainnet upgrades on a fork, including the full v7 upgrade procedure and compatibility of existing Pools after it. |
| Health checkers | `tests/health-checkers` | 2 | 9 | The health checker contracts used by [Critical Monitoring](security.md#critical-monitoring), tested against mainnet state. |
| Scenarios | `scenarios` | 1 | 1 | A runner that replays Pool and loan scenarios defined as CSV files. |

Tests named `testFork_`, and suites that extend a fork test base, run against a mainnet fork. The Aave V3 and Sky strategy tests use the live Aave and Sky contracts this way.

## Running the tests

Install the submodules and build first.

```
make install
make build
```

Each suite has a make target. Fork tests read the mainnet RPC endpoint from `ETH_RPC_URL`, and the crosschain upgrade tests read `ALCHEMY_API_KEY`.

| Command | Runs |
| --- | --- |
| `make test` | Every test under `tests/` |
| `make integration` | `tests/integration` |
| `make fuzz` | `tests/fuzz` |
| `make invariant` | `tests/invariants` |
| `make e2e` | `tests/e2e` |
| `make protocol-upgrade` | `tests/protocol-upgrade` |
| `make scenario-v2` | Every CSV scenario under `scenarios/v2` |
| `./test.sh -d tests/health-checkers` | `tests/health-checkers` |

The suite targets accept a Foundry profile. `make fuzz profile=deep` raises fuzz runs to 500 and invariant depth to 250, and `profile=super_deep` raises fuzz runs to 5,000 and invariant runs to 200.
