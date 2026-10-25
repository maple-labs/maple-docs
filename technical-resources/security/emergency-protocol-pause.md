# Emergency Pause

The Governor or Security Admin can pause the whole protocol, a single contract or everything except a named function, so an incident can be contained without blocking the fix.


## Granular Pausing
Pausing has three separate setters that control the status:

1. Global pause
2. Per contract pause
3. Per function un-pause.

### Global Pause
`setProtocolPause()` turns the pause on or off for the whole protocol. The Governor or the Security Admin can call it.

### Per-Contract Pause
`setContractPause()` pauses a specific contract instance. This way, if there's a problem in an isolated contract, there's no need to lock the whole protocol while a fix is underway. This granularity allows, for example, to have a specific loan paused, but not any of the others.

### Per-Function Unpause
To help with the recovery, there's a third lever (`setFunctionUnpause()`) which indicates which function in a paused contract can be manually un-paused. This handles the case of "unknown unknowns", which is hard to know upfront which functions might need to be called as part of the solution.

With these three variables, the governor and security admin have a greater flexibility in dealing with emergencies, and also allows for the protocol to return to a functioning state sooner.

For example, if a Pool Delegate sets a Strategy Manager's cap far too high:

    1. Pause the whole protocol with `setProtocolPause(true)` for investigation.
    2. Unpause `setStrategyCap()` on that Pool Manager with `setFunctionUnpause()` and lower the cap. Unpause `requestRedeem()` on the Strategy Manager if capital has to be recalled.
    3. Once the fix is confirmed, unpause the protocol with `setProtocolPause(false)`.

Each protocol contract checks `isFunctionPaused(msg.sig)` on Globals, which returns true when the protocol or that contract is paused and the function has not been individually unpaused.

Granular pausing reduces operational complexity and stops the system from being exploited while the fix is underway.
