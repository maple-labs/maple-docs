# Overview

Each Maple Pool has two exchange rates, one for deposits and one for withdrawals which can be seen in `convertToAssets`, `convertToExitAssets`, `convertToShares` and `convertToExitShares` functions.

The difference is because when withdrawing assets from a pool the protocol takes into account `unrealizedLosses` ([more info here](https://github.com/maple-labs/maple-core-v2/wiki/Pool-Accounting)) which can be thought of as a paper loss due to a Loan impairment. As a result the withdrawal exchange rate needs to take any `unrealizedLosses` into account to stop LPs front running any losses, this design makes any losses more equitable across all LPs. The reason that two exchange rates must be maintained in the case of an unrealized loss is that a new LP can take advantage of an impairment being removed by depositing right before the unrealizedLoss is reduced. This reduction results in a significant discrete increase in the exchange rate, which can be exploited by a savvy depositor. For this reason, the deposit exchange rate does not recognize the unrealized loss while the withdrawal rate does.

To highlight the difference first let us look at a deposit specific exchange rate functions `convertToShares`.

### `convertToAssets`

This exchange rate function helps an LP determine how much of the Pool Asset is required to mint a specific number of shares.

<br/>

$$ \large exchangeRate = \frac{totalAssets}{totalSupply} $$

<br/>

But note that `unrealizedLosses` is not used here.

### `convertToExitAssets`

This exchange rate function helps an LP determine how much of the Pool Assets an LP can withdraw for a specific number of shares.

<br/>

$$ \large exchangeRate = \frac{totalAssets-unrealizedLosses}{totalSupply} $$

<br/>

# Example

Below is an example of how the exchange rates work in an impair + default scenario. If one exchange rate was used during this process, a depositor could have deposited at a 0.6 exchange rate and withdrawn at a 0.8 exchange rate soon after. This would be an unfair distribution of funds as that depositor would earn a portion of the proceeds from cover and collateral liquidation as profit, rather than experiencing it as a reduction in loss.

```
# Pre-Impairment

totalAssets      = 1100
totalSupply      = 1000
unrealizedLosses =    0

Deposit  exchange rate = 1.1
Withdraw exchange rate = 1.1

# Post-Impairment (Pre-Default)

totalAssets      = 1100
totalSupply      = 1000
unrealizedLosses =  500

Deposit  exchange rate = 1.1
Withdraw exchange rate = 0.6

# Post-Default

totalAssets      =  800
totalSupply      = 1000
unrealizedLosses =    0

Deposit  exchange rate = 0.8
Withdraw exchange rate = 0.8

```
