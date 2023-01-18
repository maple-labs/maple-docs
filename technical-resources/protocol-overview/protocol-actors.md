This page outlines all of the different actors in the Maple protocol and gives a short description of each of their roles.

## Pool Delegate

Pool Delegates are users that manage Pools on Maple. They earn management fees in return for evaluating potential borrowers and funding Loans with attractive risk-adjusted returns. Pool Delegates earn revenue from [origination, service and management fees](https://github.com/maple-labs/maple-core-v2/wiki/Fees) paid by borrowers and liquidity providers. In order to align incentives between the Pool Delegate and it's respective Liquidity Providers, it is required that they stake a minimum [first-loss capital amount](https://github.com/maple-labs/maple-core-v2/wiki/Pool-Delegate-Cover) (defined by the Governor) which ensures that if a Loan defaults the Pool Delegate will incur a significant loss before the Liquidity Providers.

## Liquidity Provider

Liquidity Providers (LPs) add capital to the Pools to be used to fund Loans. LPs are passive investors that want to earn yield on their capital by allowing the Pool Delegate to underwrite Borrowers and earn interest. LPs earn interest by holding ERC-4626 compliant LP tokens representing their share in the pool, which appreciates in value over time as interest is earned. LPs can choose which Pool they want to deposit their capital in based on multiple factors, such as the Pool Delegates previous performance, the Borrower verticals, and Pool Delegate management fees that are being charged.

## Borrower

Borrowers are institutions that want to borrow capital from the Maple protocol. They do so by negotiating with Pool Delegates and deploying a Loan on-chain. After agreeing on terms, a Pool Delegate can fund the Loan with funds available in their Pool. Following funding, Borrowers can draw down on these funds to commence the Loan term.

In order to drawdown on a Loan, the Borrower must post the required amount of `collateralAsset` (ERC-20 token) to satisfy the specified collateralization requirements of the loan. The loan then commences and the Borrower begins making payments as per the agreed terms of the Loan. If they fail to make payments on time, the Borrower will pay late fees during the grace period. If they fail to pay after the grace period has passed, the Loan will be considered defaulted, the collateral will be liquidated and the Loan's default will be announced publicly. After a default occurs, legal recourse will start in order to recover as much of the original value of the defaulted Loan as possible.

## Governor

The [Governor](https://github.com/maple-labs/maple-core-v2/wiki/Governor-Admin-Actions) is a governance multisig wallet that performs actions based on token holder voting. The Governor controls administrative functions in the protocol, such as managing the MapleTreasury, defining global parameters and pausing functionality.

## Security Admin

A Security Admin is an account that has the ability to call the emergency [pause function](https://github.com/maple-labs/maple-core-v2/wiki/Emergency-Protocol-Pause-Function) that can pause every function in the protocol. This is only to be used in the case of critical incident response, during which action must be taken to prevent and/or stop damage from occurring to the protocol.

## Keepers

Keepers are external actors that are incentivized to perform liquidation when needed. Anyone can be a Keeper if they so wish, but the protocol only accepts actions that are within the constraints defined by the protocol. More details on the Liquidations [page](https://github.com/maple-labs/maple-core-v2/wiki/Liquidations).
