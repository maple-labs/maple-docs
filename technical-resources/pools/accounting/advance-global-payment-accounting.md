# Overview

Whenever any interaction is made with a `Loan` from the `LoanManager`, `_advanceGlobalPaymentAccounting` is called. The purpose of this function is to account all Loans' outstanding interest and to represent the current state at the current timestamp.

For all of the below examples, the following abbreviations are used:
- $$ AI $$: `accountedInterest`
- $$ IR $$: `issuanceRate`
- $$ DS $$: `domainStart`
- $$ DE $$: `domainEnd`

For all of the below examples, $accountedInterest$ starts as the following:



$$
\large
\begin{align}
\nonumber AI_{pre-AGPA} = \Big(IR_1 \times (DE_0 - DS_0)\Big) + \Big(IR_{1+2} \times (DE_1 - DS_1)\Big)
\end{align}
$$


# Example 1: Call before `domainEnd`

In this example, the payment is made before the `domainEnd`, so no payments are removed from the sorted list.



$$
\large
\begin{align}
\nonumber AI_{post-AGPA} = AI_{pre-AGPA} + \Big(IR_{1+2+3} \times (t_{payment} - DS_2)\Big)
\end{align}
$$


![AGPA 1](https://user-images.githubusercontent.com/44272939/196194337-01360be6-04fb-402f-b064-d21faba1f62d.svg)

# Example 2: Call after `domainEnd`, before Loan 2 Payment Due Date

In this example, the payment is made after the `domainEnd`, so Loan 1 is removed from the sorted list and `domainEnd` is updated.



$$
\large
\begin{align}
\nonumber AI_{post-AGPA} = AI_{pre-AGPA} + \Big(IR_{1+2+3} \times (DE_2 - DS_2)\Big) + \Big(IR_{2+3} \times (t_{payment} - DS_3)\Big)
\end{align}
$$


![AGPA 2](https://user-images.githubusercontent.com/44272939/196194336-ce355b53-0cad-445f-a5dd-7cb34ab1865d.svg)

# Example 3: Call after `domainEnd`, before Loan 3 Payment Due Date

In this example, the payment is made after the `domainEnd` and Loan 2's payment due date, so Loans 1 and 2 are removed from the sorted list and `domainEnd` is updated.



$$
\large
\begin{align}
\nonumber AI_{post-AGPA} = &AI_{pre-AGPA} + \Big(IR_{1+2+3} \times (DE_2 - DS_2)\Big) + \\
                           &\Big(IR_{2+3} \times (DE_3 - DS_3)\Big) + \Big(IR_{3} \times (t_{payment} - DS_4)\Big)
\end{align}
$$


![AGPA 3](https://user-images.githubusercontent.com/44272939/196215192-cf45223e-fc8a-4b1e-a412-4c56ea7f9a6e.svg)

# Example 4: Call after `domainEnd`, after Loan 3 Payment Due Date

In this example, the payment is made after the `domainEnd`, Loan 2, and Loan 3's payment due dates, so Loans 1, 2 and 3 are removed from the sorted list and `domainEnd` is updated.

$$
\begin{align}
\nonumber AI_{post-AGPA} = &AI_{pre-AGPA} + \Big(IR_{1+2+3} \times (DE_2 - DS_2)\Big) + \\
                           &\Big(IR_{2+3} \times (DE_3 - DS_3)\Big) + \Big(IR_{3} \times (DE_4 - DS_4)\Big) + \Big(0 \times (t_{payment} - DS_5)\Big)
\end{align}
$$

![AGPA 4](https://user-images.githubusercontent.com/44272939/196194328-a16a052d-f9b0-4897-a0b4-225b9035d6d7.svg)
