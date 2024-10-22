# Protocol Actors

This page outlines all of the different actors in the Maple protocol and gives a short description of each of their roles.

### Maple Direct

The roles previously occupied by Pool Delegates - to evaluate potential borrowers and fund loans - are now fulfilled by the Maple Direct team. During 2023, Maple brought all origination, borrower due diligence and risk management in-house with the introduction of Maple Direct as the sole delegate (external pool delegates are no longer allowed on the platform).&#x20;

### Liquidity Provider

Liquidity Providers (LPs) add capital to the Pools to be used to fund Loans. LPs are lenders that want to earn yield on their capital by allowing Maple Direct to underwrite Borrowers and earn interest. LPs earn interest by holding ERC-4626 compliant LP tokens representing their share in the pool, which appreciates in value over time as interest is earned. LPs can choose which Pool they want to deposit their capital in based on multiple factors, such as the historical performance and underlying collateral.&#x20;

### Borrower

Borrowers are institutions that want to borrow capital from the Maple protocol. After agreeing on terms, Maple can fund the Loan with funds available from liquidity providers. Following funding, Borrowers can draw down on these funds to commence the Loan term.

In order to drawdown on a Loan, the Borrower must post the required amount of `collateralAsset` (ERC-20 token) to satisfy the specified collateralization requirements of the loan. The loan then commences and the Borrower begins making payments as per the agreed terms of the Loan. If they fail to make payments on time, the Borrower will pay late fees during the grace period. If they fail to pay after the grace period has passed, the Loan will be considered defaulted, the collateral will be liquidated and the Loan's default will be announced publicly. After a default occurs, legal recourse will start in order to recover as much of the original value of the defaulted Loan as possible.

### Governor

The [Governor](broken-reference) is a governance multisig wallet that performs actions based on token holder voting. The Governor controls administrative functions in the protocol, such as managing the Maple Treasury, defining global parameters and pausing functionality.

### Security Admin

A Security Admin is an account that has the ability to call the emergency [pause function](../security/emergency-protocol-pause-function.md) that can pause every function in the protocol. This is only to be used in the case of critical incident response, during which action must be taken to prevent and/or stop damage from occurring to the protocol.

### Operational Admin

The Operational Admin is endowed with the authority to execute a subset of operational functions essential for the routine management of the protocol. It possesses limited powers compared to the Governor, ensuring a balance between operational efficiency and security.

