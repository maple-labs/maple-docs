# How to deposit and withdraw stake

While Stakers can claim their earned interest at any time, they must wait for their withdraw timer prior to removing their principal.&#x20;

{% hint style="info" %}
Find more info on the pool cooldown [here](https://github.com/maple-labs/maple-core/wiki/FDT-Exit-Defense-Mechanisms).
{% endhint %}

Currently the staking period (pre-cooldown period in this diagram) for a pool is set to 180 days (this is a [flexible pool parameter](../maple-protocol-v1.0.0.md#flexible-parameters)). This countdown will be visible in the Maple webapp UI. The 10 day cooldown period is a [global parameter](../maple-protocol-v1.0.0.md#global-parameters) that is in place as a security measure during withdrawal.

![Withdraw Timeline](<../../.gitbook/assets/cooldown (1).png>)

