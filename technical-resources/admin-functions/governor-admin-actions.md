# Governor

The Governor is the `GovernorTimelock` contract. Every function below is scheduled and executed through it, so it lands only after that contract's delay. See [Governor Timelock](../singletons/governor-timelock.md) for the proposal flow. Where a function is shared with another role, the note says so.

## Globals

Governor only:

* `setPendingGovernor`, then `acceptGovernor` (called by the pending Governor)
* `setOperationalAdmin`
* `setSecurityAdmin`
* `setMapleTreasury`
* `setMigrationAdmin`
* `setDefaultTimelockParameters`
* `setTimelockWindow`
* `setTimelockWindows`
* `unscheduleCall(caller, contract, functionId, callData)` (removes any caller's scheduled call)
* `setValidPoolAsset`
* `setImplementation` on the Globals proxy

Shared with the Operational Admin:

* `activatePoolManager`
* `activateStrategyManager`
* `setBootstrapMint`
* `setCanDeployFrom`
* `setValidBorrower`
* `setValidInstanceOf`
* `setValidMapleManagedWallet`
* `setValidPoolDelegate`
* `setValidStrategyDelegate`
* `setPlatformManagementFeeRate`, `setPlatformOriginationFeeRate`, `setPlatformServiceFeeRate`

Shared with the Security Admin:

* `setProtocolPause`
* `setContractPause`
* `setFunctionUnpause`

To let an account deploy from a factory, call `setValidInstanceOf(<FACTORY_KEY>, factory, true)` and `setCanDeployFrom(factory, account, true)`. See [Maple Globals](../singletons/globals.md).

## Pool Manager

* `addStrategy` (Governor only once the Pool is configured)
* `addStrategyManager` (Governor only once the Pool is configured)
* `setDelegateManagementFeeRate`, `setLiquidityCap`, `setStrategyCap`, `setPoolPermissionManager` (shared with the Pool Delegate and Operational Admin)
* `triggerDefault` (shared with the Pool Delegate and Operational Admin)

The Governor cannot call `upgrade` on a Pool Manager. That is the Security Admin's function.

## Open Term Loan Manager

* `impairLoan` (shared with the Pool Delegate)
* `removeLoanImpairment` (the Governor can remove any impairment, the Pool Delegate only one it made itself)

## Open Term Loan

* `skim` (shared with the borrower)

## Underlying Strategies

On each Aave V3, Sky and Allocation Strategy, shared with the Operational Admin:

* `setStrategyProtocolFeeRate` (the sum with `strategyDelegateFeeRate` must not exceed `HUNDRED_PERCENT`)
* `setUseVirtualUnderlyingBalance` (Aave V3 only)

## Pool Permission Manager

* `setPermissionAdmin` (shared with the Operational Admin)
* `setLenderBitmaps` (shared with the Operational Admin and permission admins)
* `configurePool`, `setLenderAllowlist`, `setPoolBitmaps`, `setPoolPermissionLevel` (shared with the Pool's Pool Delegate and the Operational Admin)
* `setImplementation` on the Pool Permission Manager proxy

## Proxy factories

On every `MapleProxyFactory` (Pool Manager, Withdrawal Manager, Loan, Loan Manager, Strategy Manager and each strategy factory) the Governor alone can call `registerImplementation`, `enableUpgradePath`, `disableUpgradePath`, `setDefaultVersion` and `setGlobals`. No instance can be upgraded to a version the Governor has not registered and enabled.
