# Defaults

## Overview

For both Loan types, whenever a Borrower is no longer able to meet their obligations, Maple has the option to trigger a default. This process realizes the Loan's losses and adjust the Pool accounting accordingly.

Every Loan has a defined payment interval which determines when payments are expected to be made by the Borrower. If the Borrower does not make a payment before the expected due date, there is a grace period during which they can make a late payment. After the grace period passes the loan is considered to be in default, and Maple has the _option_ to repossess the Loan and begin the liquidation process by calling `triggerDefault()`.

These conditions are illustrated in the diagram below.

![](https://user-images.githubusercontent.com/44272939/142062302-05d024a8-5b3e-4394-b06d-5b5149106f91.png)

## Loss Accounting

When a Loan is defaulted, the losses must be recognized in the Pool's accounting. This happens in the following steps:

1. Decrease `principalOut` by the full outstanding principal of the Loan. This will decrease `totalAssets` by the same amount.
2. Accrue all Loans' interest to the current timestamp and remove all interest that has accrued against the defaulted loan. This will reduce `totalAssets` by the full outstanding interest amount in the defaulted Loan.
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

## Fund Recovery

When a loan is defaulted, some amount of capital can be recovered through the mechanics of cover and liquidation. When that happens, the protocol enforces an order to which the funds will be directed. All liquidated collateral and cover first goes towards recovering fees owed to the protocol, after which all funds are returned to the Pool.&#x20;
