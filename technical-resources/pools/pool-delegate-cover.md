# Overview (Unused)

*Note this aspect of the protocol isn't used as the Pool Delegate Cover is unused due to most pool's being managed by Maple Direct.*

`PoolDelegateCover` is responsible of holding custody of all first-loss capital posted by the Pool Delegate for a given Pool. First-loss capital exists to protect Liquidity Providers in the case of a Loan default. It is required to be posted by the Pool Delegate to ensure that they are directly financially incentivized to protect Liquidity Providers from losses.

# First-Loss Mechanism

The Governor specifies the pre-requisite amount of first-loss capital that a Pool Delegate must provide in order to operate a Pool using `setMinCoverAmount` in MapleGlobals. This amount can be adjusted continuously over the Pool's operation.

If pool cover falls below the required amount, two consequences occur:
1. The Pool Delegate can no longer fund new Loans.
2. The Pool Delegate can no longer earn management fees.

The Governor also specifies `minCoverLiquidationPercentage` in MapleGlobals. This value defines what proportion of the Pool Delegate Cover goes towards reducing losses during a default. During a default scenario, cover is liquidated up to this proportion.

## Examples

```
# Example 1

minCoverLiquidationPercentage: 20%

Cover posted   = 1000
Default amount = 500

Cover liquidated = min(1000 * 20%, 500)
                 = 200

# Example 2

minCoverLiquidationPercentage: 70%

Cover posted   = 1000
Default amount =  500

Cover liquidated = min(1000 * 70%, 500)
                 = 500
```
