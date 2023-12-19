# Table of contents

* [Welcome to Maple](README.md)

## Maple for Lenders

* [Introduction](maple-for-lenders/introduction.md)
* [Role of the Pool Delegate](maple-for-lenders/role-of-the-pool-delegate.md)
* [Lending](maple-for-lenders/lending.md)
* [Loan Types](maple-for-lenders/loan-types.md)
* [Accessing Permissioned Pools](maple-for-lenders/accessing-permissioned-pools.md)
* [Defaults and Impairments](maple-for-lenders/defaults-and-impairments.md)
* [Risk](maple-for-lenders/risk.md)
* [Withdrawal Process](maple-for-lenders/withdrawal-process.md)

## Cash Management Pool

* [Overview](cash-management-pool/overview.md)
* [Lending](cash-management-pool/lending.md)
* [Withdrawals](cash-management-pool/withdrawals.md)
* [Risks](cash-management-pool/risks.md)

## Maple for Borrowers

* [Introduction](maple-for-borrowers/introduction.md)
* [Loan Management](maple-for-borrowers/loan-management.md)

## Maple for Pool Delegates

* [Introduction](maple-for-pool-delegates/introduction.md)
* [Fees](maple-for-pool-delegates/fees.md)

## Maple for Token Holders

* [MPL](maple-for-token-holders/mpl-token.md)
  * [What fees are shared with MPL holders?](maple-for-token-holders/what-fees-are-shared-with-mpl-holders.md)
* [MPL Migration](maple-for-token-holders/mpl-token-migration.md)
* [xMPL](maple-for-token-holders/xmpl-token.md)
  * [Governance with MPL and xMPL](maple-for-token-holders/governance-with-mpl-and-xmpl.md)

## Technical Resources

* Protocol Overview
  * [Background](technical-resources/protocol-overview/background.md)
  * [Protocol Actors](technical-resources/protocol-overview/protocol-actors.md)
  * [Smart Contract Architecture](technical-resources/protocol-overview/smart-contract-architecture.md)
  * [Glossary](technical-resources/protocol-overview/glossary.md)
  * [Smart Contract Addresses - Ethereum](technical-resources/protocol-overview/smart-contract-addresses.md)
  * [Smart Contract Addresses - Base](technical-resources/protocol-overview/smart-contract-addresses-base.md)
  * [Smart Contract Addresses - Solana](technical-resources/solana.md)
  * [Fees](technical-resources/protocol-overview/fees.md)
  * [Composability](technical-resources/protocol-overview/composability.md)
  * [Proxies and Upgradeability](technical-resources/protocol-overview/proxies-and-upgradeability.md)
* Security
  * [Security](technical-resources/security/security.md)
  * [List of Assumptions](technical-resources/security/list-of-assumptions.md)
  * [External Entry Points](technical-resources/security/external-entry-points.md)
  * [Emergency Protocol Pause](technical-resources/security/emergency-protocol-pause.md)
  * [Protocol Invariants](technical-resources/security/protocol-invariants.md)
  * [Test Report](technical-resources/security/test-report.md)
* Loans
  * [Loans](technical-resources/loans/loans.md)
  * [Fixed Term Loans](technical-resources/loans/fixed-term-loans.md)
  * [Open Term Loans](technical-resources/loans/open-term-loans.md)
  * [Refinancing](technical-resources/loans/refinancing.md)
  * [Impairments](technical-resources/loans/impairments.md)
  * [Defaults](technical-resources/loans/defaults.md)
* Pools
  * [Pools](technical-resources/pools/pools.md)
  * [Pool Creation](technical-resources/pools/pool-creation.md)
  * [PoolManager](technical-resources/pools/pool-manager.md)
  * [PoolDelegateCover](technical-resources/pools/pool-delegate-cover.md)
  * Accounting
    * [Pool Accounting](technical-resources/pools/accounting/pool-accounting.md)
    * [Pool Exchange Rates](technical-resources/pools/accounting/pool-exchange-rates.md)
* Loan Managers
  * [Fixed Term Loan Manager](technical-resources/loan-managers/fixed-term-loan-manager/)
    * [Overview](technical-resources/loan-managers/fixed-term-loan-manager/fixed-term-loan-manager.md)
    * [Claims](technical-resources/loan-managers/fixed-term-loan-manager/fixed-term-claim-function.md)
    * [Advance Payment Accounting](technical-resources/loan-managers/fixed-term-loan-manager/advance-global-payment-accounting.md)
    * [Accounting Examples](technical-resources/loan-managers/fixed-term-loan-manager/fixed-term-lm-accounting-examples.md)
  * [Open Term Loan Manager](technical-resources/loan-managers/open-term-loan-manager/open-term-loan-manager.md)
* Withdrawal Managers
  * [WithdrawalManager (Cyclical)](technical-resources/withdrawal-managers/withdrawal-manager-cyclical.md)
  * [WithdrawalManager (Queue)](technical-resources/withdrawal-managers/withdrawal-manager-queue.md)
* Singletons
  * [Globals](technical-resources/singletons/globals.md)
  * [MapleTreasury](technical-resources/singletons/maple-treasury.md)
  * [Oracles](technical-resources/singletons/oracles.md)
  * [Pool Permission Manager](technical-resources/singletons/pool-permission-manager.md)
* Admin Functions
  * [Governor Admin Actions](technical-resources/admin-functions/governor-admin-actions.md)
  * [Pool Delegate Admin Actions](technical-resources/admin-functions/pool-delegate-admin-actions.md)
  * [Timelocks](technical-resources/admin-functions/timelocks.md)
* Operations
  * [Protocol Deployment](technical-resources/operations/protocol-deployment.md)
  * [Open Term Loan Deployment](technical-resources/operations/open-term-loan-deployment.md)
* Interfaces
  * [FixedTermLoan](technical-resources/interfaces/fixed-term-loan.md)
  * [FixedTermLoanFactory](technical-resources/interfaces/fixed-term-loan-factory.md)
  * [FixedTermLoanFeeManager](technical-resources/interfaces/fixed-term-loan-fee-manager.md)
  * [FixedTermLoanInitializer](technical-resources/interfaces/fixed-term-loan-initializer.md)
  * [FixedTermLoanManager](technical-resources/interfaces/fixed-term-loan-manager.md)
  * [FixedTermLoanManagerFactory](technical-resources/interfaces/fixed-term-loan-manager-factory.md)
  * [FixedTermLoanManagerInitializer](technical-resources/interfaces/fixed-term-loan-manager-initializer.md)
  * [FixedTermLoanRefinancer](technical-resources/interfaces/fixed-term-loan-refinancer.md)
  * [Globals](technical-resources/interfaces/globals.md)
  * [Liquidator](technical-resources/interfaces/liquidator.md)
  * [LiquidatorFactory](technical-resources/interfaces/liquidator-factory.md)
  * [LiquidatorInitializer](technical-resources/interfaces/liquidator-initializer.md)
  * [OpenTermLoan](technical-resources/interfaces/open-term-loan.md)
  * [OpenTermLoanFactory](technical-resources/interfaces/open-term-loan-factory.md)
  * [OpenTermLoanInitializer](technical-resources/interfaces/open-term-loan-initializer.md)
  * [OpenTermLoanManager](technical-resources/interfaces/open-term-loan-manager.md)
  * [OpenTermLoanManagerFactory](technical-resources/interfaces/open-term-loan-manager-factory.md)
  * [OpenTermLoanManagerInitializer](technical-resources/interfaces/open-term-loan-manager-initializer.md)
  * [OpenTermLoanRefinancer](technical-resources/interfaces/open-term-loan-refinancer.md)
  * [Pool](technical-resources/interfaces/pool.md)
  * [PoolDelegateCover](technical-resources/interfaces/pool-delegate-cover.md)
  * [PoolDeployer](technical-resources/interfaces/pool-deployer.md)
  * [PoolManager](technical-resources/interfaces/pool-manager.md)
  * [PoolManagerFactory](technical-resources/interfaces/pool-manager-factory.md)
  * [PoolManagerInitializer](technical-resources/interfaces/pool-manager-initializer.md)
  * [WithdrawalManager](technical-resources/interfaces/withdrawal-manager.md)
  * [WithdrawalManagerFactory](technical-resources/interfaces/withdrawal-manager-factory.md)
  * [WithdrawalManagerInitializer](technical-resources/interfaces/withdrawal-manager-initializer.md)
* MPLv2
  * [Architectural Overview](technical-resources/mplv2/architecture-overview.md)
  * [Base ERC20 Structure](technical-resources/mplv2/base-ERC20-structure.md)
  * [Upgradability](technical-resources/mplv2/upgradability.md)
  * [Modules](technical-resources/mplv2/modules.md)
  * [Time Locks](technical-resources/mplv2/time-locks.md)
  * [Recapitalization Module](technical-resources/mplv2/recapitalization-module.md)
  * [Emergency Module](technical-resources/mplv2/emergency-module.md)
  * [Deployment and Migration Procedure](technical-resources/mplv2/deployment-and-migration-procedure.md)
* [GraphQL API](technical-resources/graphql-api.md)
* SDK
  * [Introduction](technical-resources/sdk/introduction.md)
  * [Installation](technical-resources/sdk/installation.md)
  * [Protocol Actors](technical-resources/sdk/protocol-actors.md)
  * [Usage Guide](technical-resources/sdk/usage-guide.md)

## Troubleshooting & Support

* [Intercom](troubleshooting-and-support/intercom.md)

## Maple 1.0

* [Access to deprecated Maple 1.0](maple-1.0/maple-token-holders.md)

## Legal

* [Borrower MLA](legal/borrower-mla.md)
* [KYC](legal/kyc.md)
* [Interface Terms of Use](legal/interface-terms-of-use.md)
* [Privacy Policy](legal/privacy-policy.md)
* [MPL Token Migration T&Cs](legal/mpl-migration.md)
