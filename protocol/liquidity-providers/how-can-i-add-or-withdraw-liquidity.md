# How can I add or withdraw liquidity?

## Deposits

Liquidity Providers will be able to select [Liquidity Pools](how-do-liquidity-pools-work.md) to deposit funds. By depositing, they receive a Maple Pool Token \(MPT\) representing their share of the pool.

As Liquidity Providers earn interest, it is reinvested by the Pool, enabling interest to compound. To withdraw liquidity, Liquidity Providers can exchange their LP token for their share of capital.

{% hint style="info" %}
While your interest is always available to be reinvested by the pool to increase productivity, claiming interest and reinvesting the capital is the only way to increase your share of the pool.
{% endhint %}

## Withdraws

While LPs can claim their earned interest at any time, they must wait for their withdraw timer prior to removing their principle. 

{% hint style="info" %}
Find more info on the pool cooldown [here](https://github.com/maple-labs/maple-core/wiki/FDT-Exit-Defense-Mechanisms).
{% endhint %}

Currently the staking period \(pre-cooldown period in this diagram\) for a pool is set to 180 days \(this is a [flexible pool parameter](../maple-protocol-v1.0.0.md#flexible-parameters)\). This countdown will be visible in the Maple webapp UI. The 10 day cooldown period is a [global parameter](../maple-protocol-v1.0.0.md#global-parameters) that is in place as a security measure during withdrawal.

![Withdraw Timeline](../../.gitbook/assets/cooldown%20%281%29.png)



