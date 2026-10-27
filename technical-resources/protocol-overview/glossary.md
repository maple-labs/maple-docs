# Glossary

## General Concepts

| Term | Definition |
|-|-|
| `Accrual-basis yield` | Yield recognized continuously as a position in an underlying protocol grows, as in the Aave V3 and Sky strategies. Fees accrue on the growth and are harvested on the next interaction with the position. |
| `Asset` | An external ERC-20 token that is used to transfer value through the protocol (e.g., USDC, WETH, WBTC). |
| `Bootstrap mint` | A small permanent deposit that protects a share price from manipulation. On the first deposit into a Pool, the Pool mints the amount as shares to `address(0)`. When a Strategy Manager is deployed, the Strategy Delegate pays the amount and its shares are assigned to `address(0)`. While the amount is non-zero, `totalShares` never returns to zero. The amount per asset is `bootstrapMint` in Globals. |
| `Borrower` | An institution approved in Globals that borrows from a Pool through an Open Term Loan. |
| `Cash-basis yield` | Yield recognized only when cash arrives, as in the Allocation Strategy. A Managed Wallet transfers profit in through `realizeYield()` and the net amount vests over a set duration. |
| `Default` | Occurs when a Borrower fails to make a payment on a loan. Recognizes the full value of the outstanding unpaid Loan as a loss to the Pool. |
| `Exit rate` | The share price used on redemption. A Strategy Manager values redeemed shares against `assetsUnderManagement() - unrealizedLosses()` rather than gross AUM, so a Pool leaving an impaired strategy bears its share of the loss. The Pool applies the same idea to lender redemptions through `convertToExitShares()`. |
| `Funds Asset` | An asset that is added as liquidity by LPs and used to facilitate Loans to Borrowers. |
| `Governor` | The `GovernorTimelock` contract that administers Globals. Every Governor action waits for the timelock delay before it executes. |
| `Impairment` | A write-down of a position before a loss is confirmed. For a loan, the Pool Delegate or Governor sets the payment due date to now and the Pool records an unrealized loss. For a strategy, the Strategy Delegate or Operational Admin records `impairedAssets`, which the Strategy Manager reports as unrealized losses. |
| `Lender` or `Liquidity Provider (LP)` | An entity that deposits assets into a Pool and holds its ERC-4626 shares. |
| `Liquidity Bot` | A Maple-operated address registered in Globals that moves capital between Pools and strategies within the configured caps, and processes lender withdrawals on the Withdrawal Manager. |
| `Liquidity Router` | `MapleLiquidityRouter`, a contract that lets a registered bot batch funding and redemption actions across several Strategy Managers in one transaction. |
| `Loan` | A contract between Pools and Borrowers, where the Pool provides capital and the Borrower is committed to repaying on an agreed schedule with agreed terms. |
| `Loan Term` | The conditions, such as payment interval and interest rate, that are specified in a loan agreement between a Borrower and a Pool Delegate. |
| `Managed Wallet` | A Maple-operated address approved in Globals and permissioned on an Allocation Strategy to deploy capital, return it and report yield. |
| `Operational Admin` | Maple's operations multisig, set in Globals. Handles day-to-day administration such as approving delegates, activating Pool Managers and Strategy Managers and setting platform fee rates, without a timelock. |
| `Operator` | Any caller a Strategy Manager allows to move capital: the Strategy Delegate, a `LIQUIDITY_BOT` address or the `LIQUIDITY_ROUTER`. Bots lose Operator status while the Underlying Strategy is impaired, see [Liquidity Bot Actions](../admin-functions/liquidity-bot-actions.md#the-impairment-block). |
| `Pending shares` | Shares a Pool has asked to redeem from a Strategy Manager that have not yet been processed. Recorded in `pendingSharesOf` and still counted in `sharesOf` until `processRedemption()` burns them. |
| `Pool` | The ERC-4626 contract that holds Lenders' deposited assets, administered by a single Pool Delegate through its Pool Manager. |
| `Pool Delegate` | The approved entity that owns one Pool Manager. It sets the Pool's liquidity cap, fee rate and strategy caps, underwrites and funds loans, manages impairments and defaults, and can request or cancel its Pool's redemptions from a Strategy Manager. It does not fund strategies or process strategy redemptions. |
| `Pool manager cap` | The limit a Strategy Manager places on one Pool's position, `poolManagerCapOf`. Zero means unlimited, and `type(uint256).max` blocks the Pool entirely. Set by the Strategy Delegate or Operational Admin. |
| `Proxy` | An intermediary smart contract that allows upgrading contracts to newer versions. |
| `Refinance` | The process to renegotiate the terms associated with a Loan. |
| `Security Admin` | A multisig set in Globals that can pause the protocol, upgrade contracts and use the Allocation Strategy's incident controls. |
| `Strategy cap` | The limit a Pool Manager places on its own exposure to one strategy, `strategyCapOf`. `requestFunds()` reverts if the strategy's current assets plus the new amount would exceed it. Set by the Pool Delegate, Governor or Operational Admin. |
| `Strategy Delegate` | The approved entity that owns one Strategy Manager. It sets the strategy's caps and its own fee rate, manages impairments and losses, and is always an Operator. |
| `Strategy liquidity cap` | The limit on a Strategy Manager's total `assetsUnderManagement()` across all Pools, `strategyLiquidityCap`. Set by the Strategy Delegate or Operational Admin. |
| `Strategy Manager` | `MapleStrategyManager`, the contract that lets several Pools fund one Underlying Strategy. It mints non-transferable shares per Pool Manager, enforces caps and records redemption requests. It never holds assets. |
| `Underlying protocol` | The external protocol where an Underlying Strategy deploys capital, such as Aave V3 or Sky. For the Allocation Strategy, it is the Managed Wallets. |
| `Underlying Strategy` | The contract that deploys capital to an underlying protocol and reports its value, liquidity, losses and fees to its Strategy Manager. Maple has Aave V3, Sky and Allocation implementations. |

## Technical Terms

| Term | Definition |
|-|-|
| `accountedInterest` | The amount of outstanding interest that has been accounted by the Loan Manager, but not yet received. |
| `accruedInterest` | The time-dependent amount of interest represented in the Loan Manager since `domainStart`. Accrues over time according to the `issuanceRate`. |
| `assetsOf(poolManager)` | A Strategy Manager view of one Pool's position: `sharesOf[poolManager] * assetsUnderManagement() / totalShares`. The Pool Manager adds it to `totalAssets()`. |
| `assetsUnderManagement` | An Underlying Strategy's total value net of accrued fees, passed through by the Strategy Manager. For the Allocation Strategy it is `totalDeployedAssets + availableToWithdraw()`. |
| `availableToWithdraw` | How much an Underlying Strategy can pay out right now, net of accrued fees. For the Allocation Strategy it is `recordedAssets - unrealizedYield()`. |
| `bootstrapMint` | Globals mapping from asset to the bootstrap amount. The Pool mints it to address(0) on its first deposit, and the Strategy Deployer seeds each new Strategy Manager with it, which in turn assigns the resulting shares to address(0). |
| `calledPrincipal` | The amount of principal that has been called and must be returned on the next loan payment. |
| `dateCalled` | The date on which the loan was called. |
| `dateFunded` | The date on which the loan was funded. |
| `dateImpaired` | The date on which the loan was impaired. |
| `datePaid` | The date on which the loan was last paid. |
| `deployedAssetsOf` | Allocation Strategy, the assets a Managed Wallet currently holds off-contract. The sum across wallets is `totalDeployedAssets`. |
| `deploymentCapOf` | Allocation Strategy, the maximum `deployedAssetsOf` a Managed Wallet may reach. |
| `domainStart` | Defines the timestamp from which the `issuanceRate` is valid. |
| `gracePeriod` | An amount of seconds that a payment can be late before a default can be triggered on a Loan. |
| `HUNDRED_PERCENT` | `1e6` (written `100_0000` in some contracts). Every fee rate is scaled by it. |
| `impairedAssets` | Underlying Strategy, the assets recorded as impaired. Reported through `unrealizedLosses()`, capped at `assetsUnderManagement()`. |
| `isInstanceOf` | Globals allowlist keyed by an instance key and an address. Registers factories, bots, routers, underlying protocol contracts and Managed Wallets. |
| `issuanceRate` | The amount of interest per second accrued by the Loan Manager, representing the aggregate current rate of accrual of interest across all outstanding Loans. This value is scaled by `1e27` (`PRECISION`) for improved precision. |
| `lastRecordedTotalAssets` | Aave V3 and Sky strategies, the position value after the last fee harvest. Growth above it is the yield that fees accrue on. |
| `lateFeeRate` | A flat rate against principal that is charged when a Loan makes a late payment. |
| `lateInterestPremiumRate` | The rate at which to increase the interest rate by for late payments. |
| `liquidityCap` | The maximum amount of value that a Pool can manage. It can be less than the current value of the Pool, preventing additional deposits. Deposits are limited by this value, where the maximum deposit amount is the difference between the current `liquidityCap` and the current value of the Pool. |
| `noticePeriod` | The number of seconds remaining after a loan is called when the borrower is considered to be in default. |
| `ownedPoolManager`, `ownedStrategyManager` | Globals bindings from a Pool Delegate to its one Pool Manager and from a Strategy Delegate to its one Strategy Manager. |
| `pendingSharesOf`, `totalPendingShares` | Strategy Manager, shares requested for redemption per Pool Manager and in total. |
| `poolManagerCapOf` | Strategy Manager, the cap on `assetsOf(poolManager)` for one Pool. |
| `principalOut` | The aggregate amount of outstanding principal across all Loans in a given Pool. |
| `recordedAssets` | Allocation Strategy, the cash the contract accounts for holding: funding and returned assets and net yield, minus deployments and withdrawals. Balance above it is `unrecordedAssets` and can be skimmed. |
| `scheduledYieldAssets` | Allocation Strategy, the net yield vesting linearly between `yieldStart` and `yieldDeadline`. `realizedYield()` is the vested part and `unrealizedYield()` the remainder. |
| `sharesOf`, `totalShares` | Strategy Manager, shares held per Pool Manager and in total, including the bootstrap shares at `address(0)`. |
| `strategyCapOf` | Pool Manager, the cap on a Pool's exposure to one strategy or Strategy Manager. |
| `strategyDelegateFeeRate`, `strategyProtocolFeeRate` | Underlying Strategy fee rates on yield, scaled by `1e6`, paid to the Strategy Delegate and the Treasury. Their sum cannot exceed `1e6`. |
| `strategyLiquidityCap` | Strategy Manager, the cap on total `assetsUnderManagement()`. |
| `totalDeployedAssets` | Allocation Strategy, the total capital currently held by Managed Wallets. |
| `unrealizedLosses` | An amount of losses that is accounted and represented in the Pool's value, but can still be recovered. The Pool Manager sums it across loan managers and Strategy Managers. |
| `yieldCap` | Allocation Strategy, the maximum `yield` a single `realizeYield()` call may report. |
| `yieldStart`, `yieldDeadline`, `yieldLastRealized` | Allocation Strategy timestamps. Yield vests from `yieldStart` to `yieldDeadline`, and `yieldLastRealized` starts the one-hour cooldown between `realizeYield()` calls. |
