## Overview

The Pool Permission Manager contract simplifies permission management for lenders and pool delegates. It streamlines the management of the global allowlist, permissions specific to each pool, and criteria for accessing various functions. This can eliminates the need for manual whitelisting of new addresses for each pool if the pool opts for using the right permission level.

To set the eligibility criteria for lenders, the permissions or protocol admins utilizes the `setLenderBitmaps` function. Pool delegates can manage the criteria for accessing specific functions of a pool through the `setPoolBitmaps` function.

The Pool Permission Manager will be deployed as a singleton non-transparent-proxy similar to the Globals contract.

## Permission Levels

Pool delegates or protocol admins can modify the permission level for a specific lending pool using `setPoolPermissionLevel`. There are four permission levels that determine who can access a lending pool:

- `PRIVATE`:        This is the default permission level. It allows access only to lenders who are on the allowlist. If a lending pool is at
                    this level, lenders not on the allowlist will be denied access to the pool's functions.
- `FUNCTION_LEVEL`: At this level, access is allowed if the function-specific pool bitmaps match the criteria set. This means that lenders
                    need to meet specific function-based criteria for access. (Note if a lender is on the allowlist for the pool the
                    permission check early circuits to return true).
- `POOL_LEVEL`:     When a lending pool is at this level, access is granted if the pool bitmaps match, irrespective of specific functions.
                    In other words, if the pool-level criteria match, lenders can interact with any function within the pool. (Note if a
                    lender is on the allowlist for the pool the permission check early circuits to return true).
- `PUBLIC`:         This is the highest level of permission. A lending pool at this level provides unrestricted access to all functions.
                    Once a lending pool is set to public, it cannot be changed back to permissioned.

## Bitmaps

To manage `FUNCTION_LEVEL` and `POOL_LEVEL` permissions bitmaps are used. Each bit represents a criteria off-chain that a lender must meet in order to interact with a pool share token.

A `uint256` is used to represent the bitmaps in the `PoolPermissionManager` this allows operators to configure up to 256 unique criteria. Whilst noting this gives an upper bound of 256 as a limit and there are implementations where we could extend the available bits infinitely, we have opt-ed to stick with 256 bits for simplicity and realistically we deem this to be more then sufficient. In a future upgrade this can be extended if required.

Note: When setting the criteria via the `poolBitmaps` mapping the zero bytes key is used to denote the `POOL_LEVEL` criteria whereas the specific function Ids are used as keys for the `FUNCTION_LEVEL` criteria per pool manager.

## Access Configuration

Pool delegates or protocol administrators can modify the allowlist of lenders using the `setLenderAllowlist` function. This function enables the addition or removal of lenders from the pool's allowlist, granting tailored control over pool-specific eligibility criteria.

`configurePool` function allows pool delegates or protocol admins to set criteria for accessing specific functions within their lending pools by specifying pool-level bitmaps and function-specific bitmaps alongside the overall permission level. This has been added as a convenience function.

## Evaluating permissions

The `hasPermission` function is responsible for determining whether a lender or a group of lenders has permission to access specific functions within a lending pool. These actions can include, but are not limited to, depositing assets, withdrawing assets, or any other operations defined by the lending protocol. A complete list of functions checked can be found in the `canCall()` function of the `PoolManager`.

The `hasPermission` function evaluates whether access should be granted based on the following steps:

- Public Pool: If the lending pool is set to the `PUBLIC` permission level, the function automatically allows access. This means that lenders can freely interact with the pool, as there are no restrictions.

- Allowlist Check: If the lending pool is at the `PRIVATE` level, the function checks if the lender is on the allowlist. If the lender is on the allowlist, access is granted. If not, access is denied.

- Bitmap Matching: When operating at the `FUNCTION_LEVEL` or `POOL_LEVEL`, the function evaluates whether the lender's permissions align with the specific function (for `FUNCTION_LEVEL`) or with the entire pool (for `POOL_LEVEL`). This matching is based on the lender's bitmap and the pool's bitmap. (Note if a lender is on the allowlist for the pool the permission check early circuits to return true).

- Bitmap Matching Result: If the bitmaps match, access is granted. However, if there is no matching access is denied.

## Important Considerations

For `FUNCTION_LEVEL` and `POOL_LEVEL` permissions it's important that the bitmaps are set prior to the pool being set to the relevant permission level. This is because the `hasPermission` function will always return true if the bitmaps are not set. This is by design to allow certain functions to be permissionless such as transfers if required. 

## Invariants

```
* Pool Permission Manager
    * Invariant A: pool.permissionLevel ∈ [0, 3]
    * Invariant B: pool.bitmap ∈ [0, MAX]
    * Invariant C: lender.bitmap ∈ [0, MAX]
    * Invariant D: pool.permissionLevel == public -> permanently public
```
