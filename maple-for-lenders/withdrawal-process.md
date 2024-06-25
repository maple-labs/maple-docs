# Withdrawal Process

Withdrawals from Maple are facilitated based on the type of Withdrawal Manager for each Pool; either Queue-based or Cycle-based. 

**Queue-based Withdrawals**

Queue-based Withdrawals are processed in a first-in, first-out process as liquidity becomes available. Lenders who request a withdrawal in a Queue-based pool will make one transaction to be added to the withdrawal queue.

The Pool Delegate determines when to process withdrawals, and the lent funds are sent directly to the Lenders' wallet(s), not requiring them to execute another transaction. Currently, withdrawals are processed on average in less than 24 hours.

**Cycle-based Withdrawals**

All withdrawal requests are grouped into **withdrawal cycles,** which are cyclically occurring periods of time (such as every week). By grouping users into cycles, Pool Delegates ensure that users get a prorated distribution of cash in the event of partial liquidity in the system.

During each withdrawal cycle there is a window of time during which all withdrawal requests assigned to it will be eligible for withdrawal. This **withdrawal window** is a period of time that takes place at the start of each withdrawal cycle (such as the first two days of each week). During each withdrawal window, the assets required to satisfy all withdrawals taking place in that window will be locked and not at the disposal of the pool delegate when funding new loans.

Withdrawing from protocol occurs in three steps:

1. User **submits a request** to withdraw during the current withdrawal cycle (call this Cycle 1). Users can modify or cancel their withdrawal request during this stage.
2. User **must wait for the following cycle to complete** until their request is eligible to be processed. This means that if a user submits a request to withdraw in Cycle 1, they will be eligible to withdraw during Cycle 3, after Cycle 2 has completed.
3. User **executes their withdrawal** during their eligible withdrawal window

You can find the lengths of the withdrawal cycles and windows in the pool description of the relevant pool.

If the user fails to execute their withdrawal in their allotted withdrawal window, they will have to resubmit their withdrawal request and wait at least another full cycle to conclude before withdrawing. Additionally, If there is not sufficient liquidity in the pool to service all withdrawal requests, those eligible to withdraw in that cycle will receive prorated share of the available proceeds and have the remaining funds requested for withdrawal moved to the very next withdrawal window.
