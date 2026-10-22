# Admin Functions

Every privileged function in v7 checks `msg.sender` against a role read from [Maple Globals](../singletons/globals.md) or a delegate stored on the instance. The matrix shows which roles reach which contracts. The role pages below list the exact functions and the conditions attached to them.

| Role | Globals | Pool Manager | Withdrawal Manager | Open Term Loan Manager | Strategy Manager | Underlying Strategies | Liquidity Router |
|---|---|---|---|---|---|---|---|
| Governor | Roles, allowlists, fees, timelock windows, pauses, proxy upgrade | Attach strategies and Strategy Managers, pool settings and caps, trigger default | | Impair and un-impair loans | | Protocol fee rate, Aave V3 virtual balance flag | |
| Operational Admin | Delegates, allowlists, fees, bootstrap amounts, activation | Pool settings and caps, detach a Strategy Manager, propose a new Pool Delegate, trigger default | Process the queue, remove requests, manual withdrawal flags | | Caps, process redemptions, propose a new Strategy Delegate | Impairments, losses, recovery, metadata, protocol fee rate | |
| Security Admin | Pause and unpause | Upgrade | Upgrade, no timelock | Upgrade, no timelock | Upgrade | Upgrade, Allocation Strategy incident controls | |
| Pool Delegate | | Pool settings and strategy caps, trigger default | Process the queue, remove requests, manual withdrawal flags, timelocked upgrade | Fund, refinance, call, impair, timelocked upgrade | Request and cancel redemptions for its own Pool | | |
| Strategy Delegate | | | | | Fund, request, cancel and process redemptions, caps, accept handover | Delegate fee rate, impairments, losses, recovery, Allocation wallet permissions and caps | |
| Liquidity Bot | | | Process the queue as a `WITHDRAWAL_REDEEMER` | | Fund, request, cancel and process redemptions as a `LIQUIDITY_BOT`, blocked while impaired | | Batch the same actions as a `LIQUIDITY_ROUTER_BOT` |
| Managed Wallet | | | | | | Allocation Strategy only: deploy and return capital, report yield | |

Blank cells mean the role has no function on that contract. The Pool Permission Manager and the Open Term Loan are not columns here, but the role pages cover them.

{% content-ref url="governor-admin-actions.md" %}
[governor-admin-actions.md](governor-admin-actions.md)
{% endcontent-ref %}

{% content-ref url="operational-admin-actions.md" %}
[operational-admin-actions.md](operational-admin-actions.md)
{% endcontent-ref %}

{% content-ref url="security-admin-actions.md" %}
[security-admin-actions.md](security-admin-actions.md)
{% endcontent-ref %}

{% content-ref url="pool-delegate-admin-actions.md" %}
[pool-delegate-admin-actions.md](pool-delegate-admin-actions.md)
{% endcontent-ref %}

{% content-ref url="strategy-delegate-actions.md" %}
[strategy-delegate-actions.md](strategy-delegate-actions.md)
{% endcontent-ref %}

{% content-ref url="liquidity-bot-actions.md" %}
[liquidity-bot-actions.md](liquidity-bot-actions.md)
{% endcontent-ref %}

{% content-ref url="timelocks.md" %}
[timelocks.md](timelocks.md)
{% endcontent-ref %}
