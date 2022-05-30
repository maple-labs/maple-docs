# Why USDC:MPL?

The Pools currently require BPTs created from the MPL:USDC Balancer pool. The tokens in the stake locker contract must be easily liquidated in order to provide cover for Lenders in the event of a default. In order for this to happen:

1. MPL needs a liquid decentralized marketplace
2. Liquidation of MPL needs to produce the lending pool liquidity asset (USDC)

For these reasons, the MPL:USDC Balancer pool is the first pool token used to provide pool cover for the Maple protocol.&#x20;

****

{% hint style="info" %}
In addition to the reasons listed above, MPL is an ERC-2222 token that might receive USDC rewards sent by the Maple DAO Treasury in the future. In order for MPL staked in a DEX to take advantage of those rewards, they need to be paired with USDC. _MPL pools paired with another token will not be able to reap reward from a future distribution of USDC fees by the DAO._
{% endhint %}

