# Singletons

Singletons are the protocol-wide contracts deployed once per chain. Every Pool, Strategy Manager and strategy reads its roles, allowlists, fee rates and pause state from them on each privileged call, so a change here takes effect across the protocol at once. They sit behind non-transparent proxies that the Governor upgrades directly, unlike the per-instance contracts that factories deploy.

{% content-ref url="globals.md" %}
[globals.md](globals.md)
{% endcontent-ref %}

{% content-ref url="governor-timelock.md" %}
[governor-timelock.md](governor-timelock.md)
{% endcontent-ref %}

{% content-ref url="maple-treasury.md" %}
[maple-treasury.md](maple-treasury.md)
{% endcontent-ref %}

{% content-ref url="pool-permission-manager.md" %}
[pool-permission-manager.md](pool-permission-manager.md)
{% endcontent-ref %}
