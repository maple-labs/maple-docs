# Exchange Rates

Each Maple Pool has two exchange rates, one for deposits and one for withdrawals, which can be seen in the `convertToAssets`, `convertToExitAssets`, `convertToShares` and `convertToExitShares` functions.

The difference is because when withdrawing assets from a pool the protocol takes into account `unrealizedLosses` ([more info here](pool-accounting.md)) which can be thought of as a paper loss due to a loan or strategy impairment. As a result the withdrawal exchange rate needs to take any `unrealizedLosses` into account to stop LPs front running any losses, this design makes any losses more equitable across all LPs. The reason that two exchange rates must be maintained in the case of an unrealized loss is that a new LP can take advantage of an impairment being removed by depositing right before the unrealizedLoss is reduced. This reduction results in a significant discrete increase in the exchange rate, which can be exploited by a savvy depositor. For this reason, the deposit exchange rate does not recognize the unrealized loss while the withdrawal rate does.

#### `convertToAssets`

This exchange rate function helps an LP determine how much of the Pool Asset is required to mint a specific number of shares.

$$
\large \begin{align} \nonumber exchangeRate = \frac{totalAssets}{totalSupply} \end{align}
$$

But note that `unrealizedLosses` is not used here.

#### `convertToExitAssets`

This exchange rate function helps an LP determine how much of the Pool Assets an LP can withdraw for a specific number of shares.

$$
\large \begin{align} \nonumber exchangeRate = \frac{totalAssets-unrealizedLosses}{totalSupply} \end{align}
$$

## Example: Loan Impairment

Below is an example of how the exchange rates work when a loan is impaired and the impairment is later removed. If one exchange rate was used during this process, a depositor could have deposited at a 0.6 exchange rate and withdrawn at a 1.1 exchange rate once the impairment was removed. This would be an unfair distribution of funds as that depositor would capture value belonging to the LPs who were in the pool when the loan was impaired.

```
# Pre-Impairment

totalAssets      = 1100
totalSupply      = 1000
unrealizedLosses =    0

Deposit  exchange rate = 1.1
Withdraw exchange rate = 1.1

# Post-Impairment

totalAssets      = 1100
totalSupply      = 1000
unrealizedLosses =  500

Deposit  exchange rate = 1.1
Withdraw exchange rate = 0.6

# Impairment Removed (Loan Repaid)

totalAssets      = 1100
totalSupply      = 1000
unrealizedLosses =    0

Deposit  exchange rate = 1.1
Withdraw exchange rate = 1.1

```

## Example: Strategy Loss

The same mechanism covers positions held through a [Strategy Manager](../strategies/strategy-manager.md). Here the Pool holds 400 of its 1100 `totalAssets` in an Underlying Strategy and is the only Pool funding it. The strategy records an impairment of the full position, and its Strategy Delegate later recognises the loss, after which the strategy reports zero assets.

```
# Pre-Impairment

totalAssets      = 1100   (700 in cash and loans, 400 in the strategy)
totalSupply      = 1000
unrealizedLosses =    0

Deposit  exchange rate = 1.1
Withdraw exchange rate = 1.1

# Strategy Impaired

totalAssets      = 1100
totalSupply      = 1000
unrealizedLosses =  400   (the Pool's share of the strategy's unrealized loss)

Deposit  exchange rate = 1.1
Withdraw exchange rate = 0.7

# Loss Recognised

totalAssets      =  700   (the strategy now reports 0)
totalSupply      = 1000
unrealizedLosses =    0

Deposit  exchange rate = 0.7
Withdraw exchange rate = 0.7
```

Two things differ from the loan case. The Strategy Manager splits the strategy's unrealized loss across every Pool funding it in proportion to their shares, so a Pool holding half the shares would report 200 instead of 400. And a recognised strategy loss is final: `totalAssets` drops, `unrealizedLosses` returns to zero, and both rates settle at the lower value for every Lender who stayed.
