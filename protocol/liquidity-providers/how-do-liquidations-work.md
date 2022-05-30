# How do liquidations work?

If a borrower misses their repayment, they have a five day grace period to make the payment before their collateral can be liquidated by the Pool Delegate and repaid to the Lending Pools that funded the loan.

![Liquidation Timeline](../../.gitbook/assets/default-scheudle.png)

In case of a collateral shortfall after the liquidation, the amount can be claimed from the Balancer Pool, which contains 50:50 MPL and USDC. Balancer Pool Tokens will be redeemed on Balancer for stablecoins and distributed to the Lending Pool to cover liquidity lost.

All Borrowers enter a Master Loan Agreement during onboarding which enables legal enforcement.
