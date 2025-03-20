# Overview

For both Loan types, whenever a Borrower is no longer able to meet their obligations, the Pool Delegate and Governor have the option to trigger a default. This process realizes the Loan's losses and adjust the Pool accounting accordingly.

Every Loan has a defined payment interval which determines when payments are expected to be made by the Borrower. If the Borrower does not make a payment before the expected due date, there is a grace period during which they can make a late payment. After the grace period passes the loan is considered to be in default, and the Pool Delegate has the *option* to repossess the Loan and begin the liquidation process by calling `triggerDefault()`.

These conditions are illustrated in the diagram below.

![](https://user-images.githubusercontent.com/44272939/142062302-05d024a8-5b3e-4394-b06d-5b5149106f91.png)

# Loss Accounting

When a Loan is defaulted, the losses must be recognized in the Pool's accounting. This happens in the following steps:
1. Decrease `principalOut` by the full outstanding principal of the Loan. This will decrease `totalAssets` by the same amount.
2. Accrue all Loans' interest to the current timestamp and remove all interest that has accrued against the defaulted loan. This will reduce `totalAssets` by the full the outstanding interest amount in the defaulted Loan.
3. If the Loan has collateral, repossess it and represent the principal and interest value of the Loan as `unrealizedLosses` in the Pool.
4. If the Loan has collateral, liquidate all collateral posted against the Loan. This will increase `totalAssets` by the total amount of cash that is recovered from the liquidation.
5. Liquidate first-loss capital posted against the Pool. This will increase `totalAssets` by the total amount of cash that is recovered.

The below example will illustrate how this affects accounting in practice.

```
## Starting State

principalOut        = 10_000
outstandingInterest =    200
cash                =  3_000
unrealizedLosses    =      0
first loss capital  =    500

totalAssets = 10_000 + 200 + 3_000
            = 13_200

loan principal  = 4_000
loan interest   =   100
loan collateral =   400

## Default (Pre-Liquidation)

principalOut        = 10_000
outstandingInterest =    200
cash                =  3_000
unrealizedLosses    =  4_000 + 100
unrealizedLosses    =  4_100
first loss capital  =    500

totalAssets                    = 13_200
totalAssets - unrealizedLosses =  9_100

loan principal  = 0
loan interest   = 0
loan collateral = 0

## Default (Post-Liquidation)

principalOut        = 6_000
outstandingInterest =   100
cash                = 3_000 + 500 + 400
cash                = 3_900
unrealizedLosses    =     0
first loss capital  =     0

totalAssets =  6_000 + 100 + 3_900
totalAssets = 10_000

loan principal  = 4_000
loan interest   =   100
loan collateral =   400
```

# Fund Recovery

When a loan is defaulted, some amount of capital can be recovered through the mechanics of cover and liquidation. When that happens, the protocol enforces an order to which the funds will be directed. All liquidated collateral and cover first goes towards recovering fees owed to the protocol, after which all funds are returned to the Pool. The Pool Delegate does not recover any fees owed during a Loan default.

# First-Loss Capital (Unused)

*Note this aspect of the protocol isn't used as the Pool Delegate Cover is unused due to most pool's being managed by Maple Direct.*

Each Pool maintains a reserved amount of liquidity whose main purpose is to serve as first-loss capital in case defaults occur. This liquidity is provided by the Pool Delegate and is used to make up for the losses still remaining after the Loan collateral is liquidated. This mechanism is in place to align incentives between the Pool Delegate and LPs. An additional setting (`maxCoverLiquidationPercent`) can also be set on a per-pool basis by the Governor, which defines the maximum percentage of pool cover used when covering for losses.

# Uncollateralized Loans

In the case of an uncollateralized Loan default, no collateral auctioning procedure is required, so the default can be completed atomically. In this case, the losses owed to the platform and Pool are calculated and cover is liquidated up to the `maxCoverLiquidationPercent`. Remaining losses are represented to LPs as a decrease in `totalAssets`.

# Collateralized Loans

In the case of a collateralized Loan default, a two-step procedure must be conducted.
1. The collateral must be repossessed and put up for liquidation.
2. The liquidation must be finalized, taking the resulting funds, calculating the remaining losses and liquidating cover liquidated up to the `maxCoverLiquidationPercent`. Remaining losses are represented to LPs as a decrease in `totalAssets`.

## Collateral Liquidation Mechanism (Unused)

*Note this aspect of the protocol isn't used as collateral is held with custodians.*

The `Liquidator` is a smart contract that performs the liquidation of any ERC-20 compatible assets using flash loans. Performing liquidations is not a permissioned action, so any user can perform these steps:

1. User calls `liquidatePortion()`, specifying an amount of collateral assets that they would like to liquidate. This amount of collateral is then sent to the user.
2. An arbitrary low-level function call is made to the user, allowing the opportunity for a strategy to be implemented to convert `collateralAsset` into `fundsAsset` atomically. It should be noted that the user can be a smart contract that has a defined strategy or an EOA that simply wants to buy the collateral at a discounted rate.
3. The total amount of liquidity assets owed is calculated by calling `loanManager.getExpectedAmount()`, which uses oracle price data and any predefined discounts in order to determine the price of the collateral asset. This amount is then pulled from the user performing the liquidation, or otherwise the whole transaction reverts.

`getExpectedAmount` has two configurable parameters defined by the Pool Delegate: `allowedSlippage` and `minRatio`.
- `allowedSlippage` is the percentage from the Chainlink oracle price to use for the discounted flash loan rate.
- `minRatio` is the minimum acceptable rate to use for flash loans. This is to protect against oracle outages.

## Collateral Liquidation Example

Two ready-to-use strategies are included in the [liquidations](https://github.com/maple-labs/liquidations) repository, one to perform an AMM swap on UniswapV2, another to perform an AMM swap on Sushiswap. An end to end example is outlined below:
1. 100 WBTC is put up for liquidation, with a market value of 60,000.00 USDC per WBTC ($6m of value total).
2. The Auctioneer is set to return a 2% discounted rate on the market value of WBTC, so it returns 58,800.00 USDC per WBTC.
3. One Keeper uses the UniswapV2 strategy to liquidate 40 WBTC.
4. 40 WBTC is transferred to this Keeper, they swap 40 BTC on UniswapV2, incurring 1.5% slippage, getting 2,364,000 USDC
5. 40 WBTC at 58,800 USDC requires that 2,352,000 USDC be returned to the Liquidator.
6. Keeper is left the remaining funds, 12,000 USDC.
7. A second Keeper wants to buy the collateral outright, since they have enough USDC on hand.
8. The second Keeper simply calculates the amount required to buy the remaining 60 WBTC (3,528,000 USDC).
9. The second Keeper approves 3,528,000 USDC to the liquidator and calls `liquidatePortion` from their EOA.
10. This amount is pulled using `transferFrom`, and the 60 WBTC is sent to the second Keeper.
