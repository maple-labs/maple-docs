# Overview

For both Loan types, in the situation where a Borrower is discovered to be unable to make an upcoming payment (e.g., they are discovered to be insolvent), impairment allows the Pool to recognize a "paper loss" (`unrealizedLoss`). This is useful to prevent large liquidity events in the Pool when the Borrowers default is far enough in the future that Liquidity Providers are able to exit the Pools before they occur.

When `impairLoan` is called on the **PoolManager** contract, the principal and any expected interest due up to the `impairLoan` call is made or payment due date (which ever is earlier) is added to the Pool's `unrealizedLosses`. `unrealizedLosses` is factored into the Pool's value for withdrawals, incentivizing current Liquidity Providers to remain in the Pool until the impairment is resolved.

In addition, the payment due date of the Loan is set to either the current timestamp or the existing payment due date, whichever is earlier. This immediately puts the Borrower in arrears if they were before their payment due date, which allows the Pool Delegate to effectuate a default more quickly.

# Outcomes

When a Loan is impaired, there are three possible outcomes to resolve the impairment. All three situations result in a more favourable outcome to the Liquidity Provider than exiting immediately.

## Manual Impairment Reversion

A Loan impairment can be removed manually, meaning that the principal and owed interest are deducted from the `unrealizedLosses` and added to the `principalOut` and `accountedInterest` respectively. This is performed through a call to `removeLoanImpairment` that can be made either by the Pool Delegate or the Governor. In this situation, the Loan payment schedule reverts to its original state, and the Pool accounting reverts back to its regular state.

## Reversion by Payment or Refinance

If a Borrower is able to make a full payment according to the Loan schedule, or the Borrower and Pool Delegate reach an agreement and are able to refinance the Loan, the impairment is removed. In this case the loan state is updated normally, setting the next payment due date a full payment interval from either the refinance or the impairment date in the case of a regular payment. The Pool removed `unrealizedLosses` and continues normal operation.

## Loan Default

In the case that the Borrower is unable to make the payment, the Loan can be defaulted. This will reduce the `unrealizedLosses` value, and will realize the loss in the Pool by reducing `principalOut` and `accountedInterest` by the value tracked in the Loan. Any collateral and cover available will go towards reducing losses in the Pool.

Example scenario with an impairment [here](../pools/accounting/pool-accounting.md).

## Access Control
Both the Pool Delegate and Governor are allowed to impair a Loan at any given time. If the Governor impairs the Loan, the Pool Delegate DOES NOT have the right to revert the impairment. If the Pool Delegate impairs the Loan, the Governor DOES have the right to revert the impairment.
