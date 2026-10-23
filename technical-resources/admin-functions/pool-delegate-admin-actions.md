# Pool Delegate

The Pool Delegate administers one Pool. Globals records the binding in `poolDelegates`, and the Pool Manager stores the address as `poolDelegate`. In v7 the Pool Delegate no longer moves capital into strategies. It sets how much of the Pool each strategy may hold, can request or cancel its Pool's exit from a Strategy Manager, and manages open-term loans. See [Pool Manager](../pools/pool-manager.md).

## Pool Manager

* `acceptPoolDelegate` (called by the pending Pool Delegate after the Operational Admin calls `setPendingPoolDelegate`)
* `setDelegateManagementFeeRate`
* `setLiquidityCap`
* `setStrategyCap` (per strategy or Strategy Manager, enforced in `requestFunds`)
* `setPoolPermissionManager`
* `triggerDefault`

Before `completeConfiguration` is called, `addStrategy`, `addStrategyManager`, `setWithdrawalManager` and `completeConfiguration` itself have no caller check. The Pool Deployer calls them in the deployment transaction. After configuration, `addStrategy` and `addStrategyManager` become Governor only and `setWithdrawalManager` cannot be called.

The Pool Delegate cannot call `upgrade` on the Pool Manager. In v7 that is the Security Admin's function.

## Open Term Loan Manager

* `upgrade` (requires a scheduled call, see [Timelocked Functions](timelocks.md))
* `fund`
* `proposeNewTerms`
* `rejectNewTerms`
* `callPrincipal`
* `removeCall`
* `impairLoan`
* `removeLoanImpairment` (only if the Governor did not make the impairment)

The Loan Manager forwards `proposeNewTerms`, `rejectNewTerms`, `callPrincipal` and `removeCall` to the Open Term Loan, which accepts them only from its lender.

## Strategy Manager

* `requestRedeem(poolManager, shares)`
* `cancelRedemption(poolManager, shares)`

Both pass when the caller is the `poolDelegate()` of the Pool Manager named in the call. The Pool Delegate cannot call `fundStrategyManager` or `processRedemption`, so an Operator still has to settle the request. See [Strategy Manager](../strategies/strategy-manager.md).

## Pool Permission Manager

For the Pool Manager the delegate owns in Globals:

* `configurePool`
* `setLenderAllowlist`
* `setPoolBitmaps`
* `setPoolPermissionLevel`

`setLenderBitmaps` is not a Pool Delegate function. Permission admins and the protocol admins set lender bitmaps.

## Withdrawal Manager

* `upgrade` (requires a scheduled call, see [Timelocked Functions](timelocks.md))
* `processRedemptions`
* `processEmptyRedemptions`
* `removeRequest`
* `setManualWithdrawal`
