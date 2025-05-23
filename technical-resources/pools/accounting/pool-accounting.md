# Pool Accounting

## Total Pool Value (`totalAssets`)

Total pool value is represented using `totalAssets`.

This value is calculated using the following equation:

$$
\begin{align} \nonumber totalAssets = cash + \sum{assetsUnderManagement_{strategies}} \end{align}
$$

where:

$$
\begin{align} \nonumber assetsUnderManagement = \sum\Big({outstandingPrincipal_{loan}} + {outstandingInterest_{loan}}\Big) \end{align}
$$

where:

$$
\begin{align} \nonumber outstandingInterest(t) = accountedInterest + issuanceRate \times (t - domainStart) \end{align}
$$

The relationship between the Pool, PoolManager, and LoanManagers regarding value representation is shown in the diagram below.

<div align="center"><img src="https://github.com/user-attachments/assets/4b64a334-57c5-4746-bbbc-f9d6c41e7940" alt="" height="500"></div>

## Unrealized Losses

`unrealizedLosses` is an accounting variable that represents a "paper loss". The Pool Delegate and Governor both have the ability to "impair" a strategy and represent a paper loss in the pool. `unrealizedLosses` is also incremented during an active collateral liquidation in a Loan. `unrealizedLosses` is used to prevent large liquidity events in situations where it is public knowledge that a Pool will incur a loss in the future.

In the case the unrealizedLosses > 0, there are two exchange rates that are maintained, one for deposits and one for withdrawals. This is to prevent malicious depositors from taking advantage of a situation where they know that paper loss will be removed. Consider a situation where there is a single loan outstanding for $900k with $10k of outstanding interest, and there is 100k of cash in the pool. The `totalSupply` of LP tokens is 1m. In this situation, the effective exchange rate is:

$$
\large \begin{align} \nonumber exchangeRate &= \frac{totalAssets}{totalSupply} \\ \nonumber exchangeRate &= \frac{900000 + 100000 + 10000}{1000000} \\ \nonumber exchangeRate &= 1.01 \end{align}
$$

After impairing the loan, `unrealizedLosses` gets set to 910k. Now, with `unrealizedLosses` considered, the exchange rate becomes:

$$
\large \begin{align} \nonumber exchangeRate &= \frac{totalAssets}{totalSupply} \\ \nonumber exchangeRate &= \frac{900000 + 100000 + 10000 - 910000}{1000000} \\ \nonumber exchangeRate &= 0.1 \end{align}
$$

Without the two exchange rate model, a depositor could deposit $1m at a 0.1 exchange rate and get 10m shares. Once `unrealizedLosses` was removed, their shares would be worth $10.1m.

For this reason, two exchange rates are maintained during an unrealizedLosses scenario. This accomplishes two things:

1. Discourages withdrawals - LPs are incentivized to wait until the strategy either:
2. Defaults - Cover and collateral will increase exchange rate
3. Pays back - The original exchange rate is restored.
4. Discourages deposits - During a scenario where a default is imminent, it is in future LPs' best interest to wait until the borrower either defaults or pays back their loan before entering the pool.
