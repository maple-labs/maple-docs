# Providing Pool Cover

Maple creates economic security for Lenders through a Balancer pool. Participants can deposit liquidity into the [MPL:USDC 50/50 pool](https://pools.balancer.exchange/#/pool/0xc1b10e536cd611acff7a7c32a9e29ce6a02ef6ef/) on Balancer to receive BPTs. With these BPTs, participants can then decide which pool to provide first-loss capital to. Pools offer different fees and drawdowns to those staking BPTs.

MPL holders can share in the Ongoing Fees accrued to Maple by providing a first-loss reserve available to cover defaults in a Lending Pool of their choosing. MPL holders will deposit a combination of MPL and USDC into a Balancer Pool, and then post those Balancer Pool Tokens (BPTs) to a specific Lending Pool. In order to align incentives, Pool Delegates are required to issue Pool Cover to any pools they create.

In the event of liquidation and collateral shortfall, the protocol will liquidate assets provided as Pool Cover in order to cover the difference between the value of the collateral and the Loan balance.

{% hint style="info" %}
Pool Delegates stake a minimum of $100,000 worth of BPT when they establish a pool. This creates a level of security for Lenders. The amount of BPTs required to create a pool is subject to change by Maple DAO vote.&#x20;

Learn in more detail [here](https://github.com/maple-labs/maple-core/wiki/Staking).
{% endhint %}

