# Impairments

In the situation where a Borrower is discovered to be unable to make an upcoming payment (e.g., they are discovered to be insolvent), impairment allows the Pool to recognize a "paper loss" (`unrealizedLoss`). This is useful to prevent large liquidity events in the Pool when the Borrowers default is far enough in the future that Liquidity Providers are able to exit the Pools before they occur.

When `impairLoan` is called on the **Open Term Loan Manager** contract, the principal and the interest accrued up to the `impairLoan` call are added to the Pool's `unrealizedLosses`, and the loan's issuance rate is removed from the Loan Manager so no further interest accrues on it. `unrealizedLosses` is factored into the Pool's value for withdrawals, incentivizing current Liquidity Providers to remain in the Pool until the impairment is resolved.

In addition, the payment due date of the Loan is set to either the current timestamp or the existing payment due date, whichever is earlier. This immediately puts the Borrower in arrears if they were before their payment due date, which allows the Pool Delegate to effectuate a default more quickly.

## Outcomes

When a Loan is impaired, there are three possible outcomes to resolve the impairment. All three situations result in a more favourable outcome to the Liquidity Provider than exiting immediately.

### Manual Impairment Reversion

A Loan impairment can be removed manually. Removal deducts the principal and the interest accrued up to the impairment from `unrealizedLosses` and leaves `principalOut` unchanged. It restores the Loan's issuance rate and adds the interest accrued between the impairment and the removal to `accountedInterest`. This is performed through a call to `removeLoanImpairment` that can be made either by the Pool Delegate or the Governor. In this situation, the Loan payment schedule reverts to its original state, and the Pool accounting reverts back to its regular state.

### Reversion by Payment or Refinance

If a Borrower is able to make a full payment according to the Loan schedule, or the Borrower and Pool Delegate reach an agreement and are able to refinance the Loan, the impairment is removed. In this case the loan state is updated normally, setting the next payment due date a full payment interval from the time of the payment or refinance. The Pool removes the `unrealizedLosses` and continues normal operation.

### Loan Default

In the case that the Borrower is unable to make the payment, the Loan can be defaulted. This will reduce the `unrealizedLosses` value, and will realize the loss in the Pool by reducing `principalOut` and `accountedInterest` by the value tracked in the Loan.

Example scenario with an impairment [here](../../pools/exchange-rates.md).

## Access Control
The Pool Delegate is allowed to impair a Loan at any given time. The Governor Timelock has the rights to revert the impairment. In practice a loan is called before it is impaired, so the next payment due is the full principal. The contracts do not enforce this order. Operationally the Governor Timelock is not used to impair a loan.
