# syrupUSDC and syrupUSDT - Defaults and Impairments

### What is a default?

Defaults can be executed by Maple when a borrower has not made a payment (including non-payment or insufficient payment of principal, interest, or late fees as applicable) past the grace period on a loan. A default will:

1. Reduce the pool’s value by the amount of outstanding principal on the loan and any interest accrued.
2. Sell any collateral on the loan and increase the value of the pool to the value of the liquidated collateral.

### What is an Impairment?

The Maple platform gives Maple the ability to impair loans in the event of a potential non-payment or insufficient payment scenario, or in a scenario where a borrower has met another condition of default as articulated in the loan agreement. The impairment is designed to be used in a scenario where the borrower has not yet entered a technical default period, but Maple does not believe that the borrower will be able to repay their loan when it is due. The impairment can be put in place to better distribute potential losses to all current lenders. Impairment prevents a situation where a loan is known to be compromised (by borrower distress or otherwise), and some lenders withdraw their capital prior to the loss, leading to the remaining lenders shouldering more of the burden of the lost capital. This may be done in a situation where Maple believes they will be able to quickly recover a part or all of the loan’s value from the Borrower through collaborative efforts, restructuring, or liquidation collateral. Maple will maintain an active dialog with the Borrower to recover funds through the legal process if necessary.

### How do Impairments affect Deposits and Withdrawals?

When a loan is impaired, its value is temporarily reduced. This allows lenders who want to withdraw to access their capital with a penalty, while not fully defaulting the loan until the grace period has expired. If the Borrower is able to make the payment or repay, it will be changed to unimpaired, and the value of the pool will be restored based on the repayment.

If a lender decides to proceed with withdrawing their funds while the impairment is active, they will have a permanent impairment loss of the difference in value and will be unable to claim any returned capital in the event that there is restitution. Any future recoveries will be pro-rated to those lenders that remained in the pool.

If a new lender decided to deposit into the pool during an impairment, their lending balance will be affected by the impairment. If an impairment is able to be repaid in full, these depositors will be made whole, but will not have any claim to any forfeited recoveries by those who withdrew when the impairment was active.
