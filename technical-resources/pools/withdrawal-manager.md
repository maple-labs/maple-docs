# Overview

The process of withdrawing assets that have been deposited into a Maple pool is managed by the `WithdrawalManager`. The `WithdrawalManager` holds custody of user's LP tokens and allows them to withdraw at specified time intervals ("**Withdrawal Window**") after waiting a minimum of a full **Withdrawal Cycle**. The purpose of this mechanism is to allow for users to get a fair distribution of cash in the event of partial liquidity in the system. This is done by grouping users into cycles so that pro-rata distributions of available cash can be performed.

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196679371-65d27dc2-5c89-40fc-88d6-55985b888221.svg" height="1000" />
</p>

# Terms

## Withdrawal Request

Users can withdraw assets they have deposited into the pool by calling `requestRedeem(n)` on the pool, where `n` is the amount of shares they want to redeem. Only one withdrawal request can be active per user at any given point in time. This request will move the users shares into the `WithdrawalManager` and update their `lockedShares` (analogous to ERC20 `balanceOf`) and their `exitCycleId`.

## Withdrawal Cycle

All withdrawal requests are grouped into withdrawal cycles, which are cyclically occurring periods of time (such as every week). Each user can manage withdrawal from within one cycle.

## Withdrawal Window

During each withdrawal cycle there is a window of time during which all withdrawal requests assigned to it will be eligible for withdrawal. This withdrawal window is a period of time that takes place at the start of each withdrawal cycle and is shorter in duration than the cycle itself (such as the first two days of each week). After the window has passed, the LP tokens within that cycle are no longer able to be used to perform redemptions.

## Withdrawal Delay

After a withdrawal request has been performed, the user will have to wait for a certain amount of time to pass before they can perform the withdrawal. If a withdrawal request has been made on cycle `n`, it will be ready for withdrawal during the withdrawal window of cycle `n+2`. This effectively means that the user will have to wait at least one full Withdrawal Cycle before being able to withdraw.

# Concepts

## Request Updates

If a user missed their withdrawal window or does not want to withdraw their shares, they can update their withdrawal request. The following options are available:
- Refresh: The withdrawal request can be resubmitted with the same amount of shares by calling `pool.requestRedeem(0)`.
- Modify: The withdrawal request can be resubmitted with a different amount of shares. The number of shares can be increased or decreased by calling `requestRedeem(n)` or `removeShares(n)` respectively.
- Cancel: The withdrawal request can be completely cancelled by removing all of the shares. This is done by calling `removeShares(n)` where `n` is the total amount of shares currently locked in the withdrawal manager.

In all cases, the withdrawal request can only be updated once it has reached the start of its withdrawal window. Additionally, the newly updated request will be made available for withdrawal only after the current and following withdrawal cycles have elapsed.

## Exchange Rate Calculation

When the actual withdrawal is performed, the amount of assets withdrawn is calculated by converting the shares requested for withdrawal into assets using the current exchange rate. This means that the exchange rate between different user's redemptions from within the `WithdrawalManager` can and will vary. In case any loans have been impaired or are in the process of liquidation the value of each share will be decreased until the impairments/liquidations are finalized. This means that performing a withdrawal during a liquidation may result in a lower amount of assets withdrawn than if the withdrawal is performed after the liquidation is finalized and some or all losses are recovered.

## Liquidity Locking

Over the duration of each withdrawal window, the total amount of assets required to satisfy all withdrawals taking place in that window will be continuously locked (using the current exchange rate). This amount of assets will remain available in the pool for the purpose of satisfying pending withdrawals and will not be at the disposal of the pool delegate when funding new loans. This mechanism ensure liquidity providers have a chance to withdraw their assets during each withdrawal window.

## Pro-rata Distribution

In case there is not enough liquidity to satisfy all withdrawals within the same window, the available amount of liquidity will be proportionally distributed between all users based on the sizes of their withdrawal requests. For instance, if there is only enough assets in the pool to satisfy 50% of the total amount of assets required for withdrawal, each user will only withdraw 50% of their requested amount. **Withdrawal requests that could not be completely fulfilled due to insufficient liquidity will also be fast forwarded to the next withdrawal cycle without any additional delays**. The formula for this distribution is:

<br/>
$$ \large redeemableShares(user) = max\Big(lockedShares(user),~~lockedShares(user) \times \frac{availableLiquidity}{totalRequestedLiquidity}\Big) $$
<br/>

where

<br/>
$$ \large totalRequestedLiquidity = totalCycleShares(currentCycle) \times exchangeRate $$
<br/>

where

<br/>
$$ \large exchangeRate = \frac{totalAssets - unrealizedLosses}{totalSupply} $$
<br/>

In a partial liquidity situation ( $availableLiquidity \lt totalRequestedLiquidity$ ) the cash will get distributed pro-rata based on how the equity of locked shares is distributed in the WithdrawalManager. The exchange rate will change over time. With no additional incoming cash, this will result in an even distribution of cash, but users that redeem when the exchange rate is higher will have to burn less shares to do so.

It can be seen in a partial liquidity scenario, using the `exchangeRate` to convert the position to cash, that **the amount of cash that each user gets will remain constant**. The only thing that changes is the amount of shares that must be burned in order to obtain that cash amount. This is assuming constant `availableLiquidity`. Over the course of a withdrawal window, Borrowers can make payments and new LPs can deposit, increasing available cash. This will increase the amount of cash that will be able to be withdrawn by the users that remain. Note that this value can never decrease (except for users withdrawing), due to the fact that the PoolDelegate cannot fund new loans with cash above the `availableLiquidity` amount.

<br/>
$$ \large redeemableCash(user) = lockedShares(user) \times \frac{availableLiquidity}{totalCycleShares(user) \times exchangeRate} \times exchangeRate $$
<br/>

Cancelling out `exchangeRate` yields:

<br/>
$$ \large redeemableCash(user) = lockedShares(user) \times \frac{availableLiquidity}{totalCycleShares(user)} $$
<br/>

Or, more intuitively:

<br/>
$$ \large redeemableCash(user) = availableLiquidity \times \frac{lockedShares(user)}{totalCycleShares(user)} $$
<br/>

For an example of this in practice, please refer to [Example 3](https://github.com/maple-labs/maple-core-v2/wiki/Withdrawal-Mechanism#example-3-partial-liquidity-changing-exchange-rate).

## Configuration Management

The Pool Delegate can update the duration of the withdrawal cycle and/or window by calling `setExitConfig()` and passing in the new parameters. This change will only take effect after the current and two following withdrawal cycles have elapsed, in order to prevent conflicts between pending and future withdrawals.

Another capability that the PD has is to change the WithdrawalManager contract. Since this contract holds custody of users' LP tokens, it is crucial that no tokes are in the contract when this occurs.

# Examples

## Example 1: Full Liquidity

In the case of full liquidity, no pro-rata calculation is necessary. Both users are able to redeem their full shares at the current exchange rate.

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196678918-7c867bf9-71c1-4f0a-8d47-8170a2f6c96d.svg" height="1000" />
</p>

## Example 2: Partial Liquidity

In the case of partial liquidity, the pro-rata calculation must be performed.

For user 1, their redeemable shares are calculated as follows and redeemed at the current exchange rate of 1.2, resulting in 48 units of `fundsAsset`. The remainder of their shares are moved to `cycle + 1`. This is important to note as this only occurs when there is partial liquidity.

<br/>

$$
\large
\begin{align}
\nonumber redeemableShares        &= lockedShares \times \frac{availableLiquidity}{totalRequestedLiquidity} \\
\nonumber totalRequestedLiquidity &= (100 + 400) \times 1.2 = 600 \\
\nonumber availableLiquidity      &= 240 \\
\nonumber redeemableShares        &= 100 \times \frac{240}{600} = 40 \\
\nonumber resultingAssets         &= 40 \times 1.2 = 48
\end{align}
$$

<br/>

For user 1, their redeemable shares are calculated as follows and redeemed at the current exchange rate of 1.2, resulting in 192 units of `fundsAsset`. The remainder of their shares are moved to `cycle + 1`. This is important to note as this only occurs when there is partial liquidity.

<br/>

$$
\large
\begin{align}
\nonumber redeemableShares        &= lockedShares \times \frac{availableLiquidity}{totalRequestedLiquidity} \\
\nonumber totalRequestedLiquidity &= 400 \times 1.2 = 480 \\
\nonumber availableLiquidity      &= 192 \\
\nonumber redeemableShares        &= 400 \times \frac{192}{480} = 160 \\
\nonumber resultingAssets         &= 160 \times 1.2 = 192
\end{align}
$$

<br/>

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196678917-e47715db-0436-4d12-886a-0fe8bfb79d26.svg" height="1000" />
</p>

## Example 3: Partial Liquidity, Changing Exchange Rate

In the case of partial liquidity, the pro-rata calculation must be performed.

For user 1, their redeemable shares are calculated as follows and redeemed at the current exchange rate of 1.2, resulting in 48 units of `fundsAsset`. The remainder of their shares are moved to `cycle + 1`. This is important to note as this only occurs when there is partial liquidity.

<br/>

$$
\large
\begin{align}
\nonumber redeemableShares        &= lockedShares \times \frac{availableLiquidity}{totalRequestedLiquidity} \\
\nonumber totalRequestedLiquidity &= (100 + 400) \times 1.2 = 600 \\
\nonumber availableLiquidity      &= 240 \\
\nonumber redeemableShares        &= 100 \times \frac{240}{600} = 40 \\
\nonumber resultingAssets         &= 10 \times 1.2 = 48
\end{align}
$$

<br/>

For user 1, their redeemable shares are calculated as follows and redeemed at the current exchange rate of 1.5, resulting in 192 units of `fundsAsset`. The remainder of their shares are moved to `cycle + 1`. Note that this yielded the same amount of cash as in Example 2, but less shares had to be burned to do so.

<br/>

$$
\large
\begin{align}
\nonumber redeemableShares        &= lockedShares \times \frac{availableLiquidity}{totalRequestedLiquidity} \\
\nonumber totalRequestedLiquidity &= 400 \times 1.5 = 600 \\
\nonumber availableLiquidity      &= 192 \\
\nonumber redeemableShares        &= 400 \times \frac{192}{600} = 128 \\
\nonumber resultingAssets         &= 128 \times 1.5 = 192
\end{align}
$$

<br/>

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/198855863-fbd0989f-412c-4ce9-b129-3546866193b2.svg" height="1000" />
</p>

## Example 4: Partial Liquidity then Full Liquidity

During a Withdrawal Window, it is possible for additional liquidity to come into the pool. In this situation, this can positively affect LPs' positions. In this example, user 1 has the same pro-rata distribution as in Example 2, but since additional liquidity was added to the system, user 2 can exit with full liquidity.

<br/>

$$
\large
\begin{align}
\nonumber redeemableShares        &= lockedShares \times \frac{availableLiquidity}{totalRequestedLiquidity} \\
\nonumber totalRequestedLiquidity &= (100 + 400) \times 1.2 = 600 \\
\nonumber availableLiquidity      &= 240 \\
\nonumber redeemableShares        &= 100 \times \frac{240}{600} = 40 \\
\end{align}
$$

<br/>

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196678915-770f092d-a1aa-4bff-9018-539934300984.svg" height="1000" />
</p>

## Example 5: Partial Liquidity then Remove Shares

During a Withdrawal Window, since users are now eligible to do so, they can remove shares from the `WithdrawalManager`. In this example user 2 removes all their shares from the system, which leaves user 1 with full liquidity.

<p align="center">
  <img src="https://user-images.githubusercontent.com/44272939/196678912-15ee6425-9618-4240-9941-be80f44b2d2f.svg" height="1000" />
</p>
