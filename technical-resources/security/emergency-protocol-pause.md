
## Pre-Upgrade Pausing
In the previous version of the protocol, there was a single switch that determined whether the protocol was paused. This switch had a global effect on all functions within the protocol. The security admin was responsible for triggering the global pause.

However, while effective as an emergency shut down, this architecture posed limitations for recovery strategies to return the system to normal operations from a paused state. To illustrate this limitation, consider a scenario where a pool delegate misconfigures a parameter that affects a pool, such as setting an inappropriate liquidation rate, which allows collateral to be traded at an unwanted discount.

In such a situation, the security admin would trigger a pause, which stops all operations. However, the fix requires either the governor or the pool delegate to reset the minimum ratio, which cannot be done in a paused state. Full recovery requires the following atomic actions to be performed:

    1. The security admin calls unpause.
    2. The governor or pool delegate calls setMinRatio.
    3. The security admin calls pause to enable proper fix evaluation.
    4. The security admin calls unpause.

Even in this simple scenario, the fix is an operational challenge, as it involves multiple parties and time-sensitive procedures. Therefore, the mechanism has been redesigned to address these issues.

## Granular Pausing
Addressing the flaws described above, the pausing has 3 separate setters that control the status.

1. Global pause
2. Per contract pause
3. Per function un-pause.

### Global Pause
This structure is the same as the previous one, meaning a single switch that turns on or off the pause for the whole system, with the difference that now it can be called by either the `governor` or the `security admin`.

### Per-Contract Pause
Additionally, a flag is added to pause specific contract instances. This way, if there's a problem in an isolated contract, there's no need to lock the whole protocol while a fix is underway. This granularity allows, for example, to have a specific loan paused, but not any of the others.

### Per-Function Unpause
To help with the recovery, there's a third lever which indicates which function in a paused contract can be manually un-paused. This handles the case of "unknown unknowns", which is hard to know upfront which functions might need to be called as part of the solution.


With these three variables, the governor and security admin have a greater flexibility in dealing with emergencies, and also allows for the protocol to return to a functioning state sooner.

Back to the example where the ratio of a collateral asset is misconfigured in a pool, the new way of handling the issue:

    1. Pause the whole protocol for investigation.
    2. Turn on the `setMinRatio` function to be callable and adjust the parameter.
    3. Set the specific contract to be paused and simultaneosly unpause the rest of the system.
    4. Once the fix is assured to be comprehensible, unpause the affected contract.
