# Total Pool Value (`totalAssets`)

Total pool value is represented using `totalAssets`.

This value is calculated using the following equation:

<p align="center"> $$ totalAssets = cash + \sum{assetsUnderManagement_{loanManager}} $$ </p>

where:

<br/>

$$ assetsUnderManagement = \sum({outstandingPrincipal_{loan}} + {outstandingInterest_{loan}}) $$
<br/>

where:

<br/>

$$ outstandingInterest(t) = accountedInterest + issuanceRate \times (t - domainStart) $$
<br/>

where:

<br/>

$$ domainStart \le t \le domainEnd $$
<br/>

The relationship between the Pool, PoolManager, and LoanManagers regarding value representation is shown in the diagram below.

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196053069-88046d8c-7489-4a02-9a83-27406eac1b93.svg" height="500" />
</p>

# Unrealized Losses

`unrealizedLosses` is an accounting variable that represents a "paper loss". The Pool Delegate and Governor both have the ability the "impair" a loan, setting the payment due date to the current timestamp (putting the loan into arrears) and representing a paper loss in the pool. `unrealizedLosses` is also incremented during an active collateral liquidation in a Loan. `unrealizedLosses` is used to prevent large liquidity events in situations where it is public knowledge that a Pool with incur a loss in the future.

In the case that $unrealizedLosses \gt 0$, there are two exchange rates that are maintained, one for deposits and one for withdrawals. This is to prevent malicious depositors from taking advantage of a situation where they know they paper loss will be removed. Consider a situation where there is a single loan outstanding for $900k with $10k of outstanding interest, and there is 100k of cash in the pool. The `totalSupply` of LP tokens is 1m. In this situation, the effective exchange rate is:

<br/>

$$
\large
\begin{align}
\nonumber exchangeRate &= \frac{totalAssets}{totalSupply} \\
\nonumber exchangeRate &= \frac{900000 + 100000 + 10000}{1000000} \\
\nonumber exchangeRate &= 1.01
\end{align}
$$
<br/>

After impairing the loan, `unrealizedLosses` gets set to 910k. Now, with `unrealizedLosses` considered, the exchange rate becomes:

<br/>

$$
\large
\begin{align}
\nonumber exchangeRate &= \frac{totalAssets}{totalSupply} \\
\nonumber exchangeRate &= \frac{900000 + 100000 + 10000 - 910000}{1000000} \\
\nonumber exchangeRate &= 0.1
\end{align}
$$
<br/>

Without the two exchange rate model, a depositor could deposit $1m at a 0.1 exchange rate and get 10m shares. Once `unrealizedLosses` was removed, their shares would be worth $10.1m.

For this reason, two exchange rates are maintained during an unrealizedLosses scenario. This accomplishes two things:
1. Discourages withdrawals - LPs are incentivized to wait until the loan either:
  1. Defaults - Cover and collateral will increase exchange rate
  2. Pays back - The original exchange rate is restored.
2. Discourages deposits - During a scenario where a default is imminent, it is in future LPs' best interest to wait until the borrower either defaults or pays back their loan before entering the pool.
