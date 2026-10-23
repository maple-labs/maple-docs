# Security Admin

The Security Admin is the address stored as `securityAdmin` in [Maple Globals](../singletons/globals.md), appointed by the Governor with `setSecurityAdmin`. It has three jobs: pausing, upgrading instances, and containing incidents on the Allocation Strategy. It has no say over fees, caps, impairments or capital movement.

## Globals

Shared with the Governor:

* `setProtocolPause`
* `setContractPause`
* `setFunctionUnpause`

See [Emergency Protocol Pause](../security/emergency-protocol-pause.md) for how the three switches combine.

## Upgrades

The Security Admin calls `upgrade(version, arguments)` directly on an instance. The factory then checks that the Governor has enabled the upgrade path to that version. None of these calls needs a scheduled call in Globals.

| Contract | Other callers |
|---|---|
| Pool Manager | none |
| Strategy Manager | none |
| Aave V3 Strategy | none |
| Sky Strategy | none |
| Allocation Strategy | none |
| Open Term Loan | none |
| Open Term Loan Manager | Pool Delegate, with a scheduled call |
| Withdrawal Manager | Pool Delegate, with a scheduled call |

See [Timelocked Functions](timelocks.md) for the Pool Delegate path.

## Allocation Strategy incident controls

Shared with the Strategy Delegate, on each [Allocation Strategy](../strategies/allocation-strategy/README.md):

* `cancelYield(assets, recipient)` claws back yield a Managed Wallet reported but has not yet streamed to the Pool. Passing `type(uint256).max` cancels all unrealized yield. The recipient must be a registered `MAPLE_MANAGED_WALLET`.
* `setPermissions(accounts, canDeployAssets, canReturnAssets, canRealizeYield)` can revoke every flag on any address. Granting any flag requires the address to be a registered `MAPLE_MANAGED_WALLET`.
* `setDeploymentCaps(accounts, amounts)` can set a cap of zero on any address. A non-zero cap requires a registered `MAPLE_MANAGED_WALLET`.

The Security Admin cannot call `impair`, `recognizeLoss` or any other strategy function. See [Managed Wallets](../strategies/allocation-strategy/managed-wallets.md).
