This page outlines all of the different actors in the Maple protocol and gives a short description of each of their roles.

## Pool Delegate

A Pool Delegate is an address used to administer a pool. The Pool Delegate address configures pool parameters, manages strategies, and performs loan administration as permitted by protocol roles. Management fees compensate the pool administration function.

## Liquidity Provider

Liquidity Providers (LPs) add capital to the Pools to be used to fund strategies. LPs are lenders that want to earn yield on their capital by allowing Maple Direct to underwrite strategies and earn interest. LPs earn interest by holding ERC-4626 compliant LP tokens representing their share in the pool, which appreciates in value over time as interest is earned. LPs can choose which Pool they want to deposit their capital in based on multiple factors, such as the historical performance and underlying collateral.&#x20;

## Borrowers

The primary Maple strategies are loans for institutions (borrowers) that want to borrow capital from the Maple protocol. After agreeing terms with Maple, a Pool Delegate address can fund the loan with funds available in the pool.


## Governor

The [Governor](../admin-functions/governor-admin-actions.md) is a governance multisig wallet that performs actions based on token holder voting. The Governor controls administrative functions in the protocol, such as managing the MapleTreasury, defining global parameters and pausing functionality.

## Security Admin

A Security Admin is an account that has the ability to call the emergency [pause function](../security/emergency-protocol-pause-function.md) that can pause every function in the protocol. This is only to be used in the case of critical incident response, during which action must be taken to prevent and/or stop damage from occurring to the protocol.

## Operational Admin

The Operational Admin is endowed with the authority to execute a subset of operational functions essential for the routine management of the protocol. It possesses limited powers compared to the Governor, ensuring a balance between operational efficiency and security.

## Keepers

Keepers are external actors that are incentivized to perform liquidation when needed. Anyone can be a Keeper if they so wish, but the protocol only accepts actions that are within the constraints defined by the protocol. More details on the Liquidations [page](../loans/defaults.md).
