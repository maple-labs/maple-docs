# Loan Types

Maple supports two distinct Loan types: open term and fixed term.

**Open Term Loans**

Open term loans refer to loans that are issued without an explicit maturity date, and which must be repaid in a limited time window once the Delegate "calls" the loan. By allowing Delegates to request repayment at any time, Open term loans empower Delegates to manage liquidity for Lenders and avoid long waiting queues for withdrawal requests. 

Open term loans are also flexible on the Borrower side. Borrowers can close open terms early without penalty. Open term loans give allocators and Borrowers maximal flexibility in safely managing capital and are thus a critical piece of crypto lending infrastructure. 

**Fixed Term Loans**

Fixed term loans refer to loans with an agreed-upon due date set at Loan creation (e.g. 180 days). Fixed term loans provide certainty to both allocators and Borrowers.

Both fixed and open term loans can be refinanced. However, the Delegate cannot call a fixed term loan, since these loans have specified end dates. Fixed term loans are most useful as Maple expands into the RWA space, as fixed term lending is a core primitive in traditional finance. 