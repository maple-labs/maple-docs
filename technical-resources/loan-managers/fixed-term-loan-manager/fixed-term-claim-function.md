# Claims

The `claim` function in the LoanManager is called atomically after every payment that is made against Loans. The `claim` function is designed to:

1. Consolidate and update past accounting of outstanding interest for all Loans in the LoanManager.
2. Handle accounting of the payment that was just made within the LoanManager.
3. Disburse funds from the payment to the Pool and MapleTreasury.
4. Calculate the interest accrual parameters based on the next scheduled payment in the Loan.
5. Update the global accounting formula in the LoanManager to start accruing interest into the future.

Below is a flowchart demonstrating how the claim function handles all of this logic.

<figure><img src="https://user-images.githubusercontent.com/44272939/196696564-3c8cf4b0-bbc0-48b4-99b4-2b7c92f4609e.svg" alt=""><figcaption></figcaption></figure>
