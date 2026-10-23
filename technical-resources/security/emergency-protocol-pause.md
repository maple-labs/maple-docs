# Emergency Pause

The Governor or Security Admin can pause the whole protocol, a single contract or everything except a named function, so an incident can be contained without blocking the fix.


## Pre-Upgrade Pausing
In the previous version of the protocol, there was a single switch that determined whether the protocol was paused. This switch had a global effect on all functions within the protocol. The security admin was responsible for triggering the global pause.

However, while effective as an emergency shut down, this architecture posed limitations for recovery strategies to return the system to normal operations from a paused state. To illustrate this limitation, consider a Pool Delegate who sets the strategy cap for a Strategy Manager far too high with `setStrategyCap()`, so the Liquidity Bots can move more of the Pool into that strategy than intended.

In such a situation, the security admin would trigger a pause, which stops all operations. However, the fix requires the Pool Delegate to lower the cap and request a redemption, which cannot be done in a paused state. Full recovery requires the following atomic actions to be performed:

    1. The security admin calls unpause.
    2. The Pool Delegate calls `setStrategyCap()` and `requestRedeem()`.

Even in this simple scenario, the fix is an operational challenge, as there is no native way to ensure the atomicity of operations and it involves multiple parties and time-sensitive procedures. Therefore, the mechanism has been redesigned to address these issues.

## Granular Pausing
Addressing the flaws described above, the pausing has 3 separate setters that control the status.

1. Global pause
2. Per contract pause
3. Per function un-pause.

### Global Pause
This structure is the same as the previous one, meaning a single switch (`setProtocolPause()`) that turns on or off the pause for the whole system, with the difference that now it can be called by either the Governor or the Security Admin.

### Per-Contract Pause
Additionally, a flag (`setContractPause()`) is added to pause specific contract instances. This way, if there's a problem in an isolated contract, there's no need to lock the whole protocol while a fix is underway. This granularity allows, for example, to have a specific loan paused, but not any of the others.

### Per-Function Unpause
To help with the recovery, there's a third lever (`setFunctionUnpause()`) which indicates which function in a paused contract can be manually un-paused. This handles the case of "unknown unknowns", which is hard to know upfront which functions might need to be called as part of the solution.

With these three variables, the governor and security admin have a greater flexibility in dealing with emergencies, and also allows for the protocol to return to a functioning state sooner.

Back to the example where a strategy cap is misconfigured on a pool, the new way of handling the issue:

    1. Pause the whole protocol with `setProtocolPause(true)` for investigation.
    2. Unpause `setStrategyCap()` on that Pool Manager with `setFunctionUnpause()` and lower the cap. Unpause `requestRedeem()` on the Strategy Manager if capital has to be recalled.
    3. Once the fix is confirmed, unpause the protocol with `setProtocolPause(false)`.

Each protocol contract checks `isFunctionPaused(msg.sig)` on Globals, which returns true when the protocol or that contract is paused and the function has not been individually unpaused.

Using the new pausing mechanism, the operational complexity is reduced and it becomes impossible to exploit the system while the fix is underway.
