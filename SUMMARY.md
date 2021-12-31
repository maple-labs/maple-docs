# Table of contents

* [Welcome to Maple](README.md)

## How to Participate

* [How to lend](how-to-participate/how-to-lend.md)
* [How to stake](how-to-participate/how-to-stake.md)
* [How to borrow](how-to-participate/borrowing-with-maple.md)
* [How to become a Pool Delegate](how-to-participate/earning-with-maple.md)

## Protocol

* [Maple Protocol Overview V1.0.0](protocol/maple-protocol-v1.0.0.md)
* [Pool Delegates](protocol/pool-delegates/README.md)
  * [What can I earn as a Pool Delegate?‌](protocol/pool-delegates/what-can-i-earn-as-a-pool-delegate.md)
  * [What do Pool Delegates do?](protocol/pool-delegates/what-do-pool-delegates-do.md)
  * [What criteria do Pool Delegates use to assess borrowers?](protocol/pool-delegates/what-criteria-do-pool-delegates-use-to-assess-borrowers.md)
  * [How to become a Pool Delegate](protocol/pool-delegates/how-to-become-a-pool-delegate.md)
* [Borrowers](protocol/borrowers/README.md)
  * [How to borrow on Maple](protocol/borrowers/how-can-i-borrow-on-maple.md)
  * [How do liquidations work?](protocol/borrowers/how-do-liquidations-work.md)
  * [What are the fees?](protocol/borrowers/what-are-the-fees.md)
  * [What collateral do borrowers have to put up?](protocol/borrowers/what-collateral-do-borrowers-have-to-put-up.md)
* [Lenders](protocol/liquidity-providers/README.md)
  * [How do Lending Pools work?](protocol/liquidity-providers/how-do-liquidity-pools-work.md)
  * [How can I add or withdraw liquidity?](protocol/liquidity-providers/how-can-i-add-or-withdraw-liquidity.md)
  * [How is APY calculated?](protocol/liquidity-providers/how-is-apy-calculated.md)
  * [How do liquidations work?](protocol/liquidity-providers/how-do-liquidations-work.md)
  * [What are the fees?](protocol/liquidity-providers/what-are-the-fees.md)
* [MPL Token](protocol/maple-token-holders/README.md)
  * [Governance with MPL](protocol/maple-token-holders/governance-with-mpl.md)
  * [What fees are shared with MPL holders?](protocol/maple-token-holders/what-fees-are-shared-with-mpl-holders.md)
  * [How do I stake the Maple Token?](protocol/maple-token-holders/how-do-i-stake-the-maple-token.md)
  * [How can you earn MPL rewards?](protocol/maple-token-holders/how-can-you-earn-mpl.md)
* [Staking Pool Cover](protocol/pool-cover/README.md)
  * [Why USDC:MPL?](protocol/pool-cover/why-usdc-mpl.md)
  * [How does the Staking Pool work?](protocol/pool-cover/how-does-the-insurance-pool-work.md)
  * [How to deposit and withdraw stake](protocol/pool-cover/how-to-deposit-and-withdraw-stake.md)
  * [Staking Rewards](protocol/pool-cover/staking-rewards.md)

## Smart Contracts

* [General](smart-contracts/general/README.md)
  * [Globals](smart-contracts/general/mapleglobals.md)
  * [Maple Token (MPL)](smart-contracts/general/mapletoken.md)
  * [Treasury](smart-contracts/general/mapletreasury.md)
  * [MPL Rewards](smart-contracts/general/mplrewards.md)
  * [MPL Rewards Factory](smart-contracts/general/mplrewardsfactory.md)
* [Calculators](smart-contracts/calculators/README.md)
  * [Calculator](smart-contracts/calculators/v1/calc.md)
  * [Late Fee Calculator](smart-contracts/calculators/v1/latefeecalc.md)
  * [Premium Calculator](smart-contracts/calculators/v1/premiumcalc.md)
  * [Repayment Calculator](smart-contracts/calculators/v1/repaymentcalc.md)
* [Funds Distribution Tokens \(FDTs\)](smart-contracts/funds-distribution-tokens-fdts/README.md)
  * [Basic FDT](smart-contracts/funds-distribution-tokens-fdts/basicfdt.md)
  * [Basic Funds Token FDT](smart-contracts/funds-distribution-tokens-fdts/basicfundstokenfdt.md)
  * [Extended FDT](smart-contracts/funds-distribution-tokens-fdts/extendedfdt.md)
  * [Pool FDT](smart-contracts/funds-distribution-tokens-fdts/poolfdt.md)
  * [Stake Locker FDT](smart-contracts/funds-distribution-tokens-fdts/stakelockerfdt.md)
* [Liquidator](smart-contracts/liquidator/liquidator.md)
* [Loans](smart-contracts/loans/README.md)
  * V1
    * [Loan Factory](smart-contracts/loans/v1/loanfactory.md)
    * [Loan](smart-contracts/loans/loan.md)
    * [Loan Lib](smart-contracts/loans/v1/loanlib.md)
  * V2
    * [Loan Factory](smart-contracts/loans/v2/mapleloanfactory.md)
    * [Loan](smart-contracts/loans/v2/mapleloan.md)
    * [Loan Initializer](smart-contracts/loans/v2/mapleloaninitializer.md)
    * [Loan Refinancer](smart-contracts/loans/v2/refinancer.md)
* [Lockers](smart-contracts/lockers/README.md)
  * [Collateral Locker Factory](smart-contracts/lockers/collaterallockers/collaterallockerfactory.md)
  * [Collateral Locker](smart-contracts/lockers/collaterallockers/collaterallocker.md)
  * Debt Locker
    * V1
      * [Debt Locker Factory](smart-contracts/lockers/debtlockers/v1/debtlockerfactory.md)
      * [Debt Locker](smart-contracts/lockers/debtlockers/v1/debtlocker.md)
    * V2
      * [Debt Locker Factory](smart-contracts/lockers/debtlockers/v2/debtlockerfactory.md)
      * [Debt Locker](smart-contracts/lockers/debtlockers/v2/debtlocker.md)
      * [Debt Locker Initializer](smart-contracts/lockers/debtlockers/v2/debtlockerinitializer.md)
  * [Funding Locker Factory](smart-contracts/lockers/fundinglockers/fundinglockerfactory.md)
  * [Funding Locker](smart-contracts/lockers/fundinglockers/fundinglocker.md)
  * [Liquidity Locker Factory](smart-contracts/lockers/liquiditylockers/liquiditylockerfactory.md)
  * [Liquidity Locker](smart-contracts/lockers/liquiditylockers/liquiditylocker.md)
  * [Stake Locker Factory](smart-contracts/lockers/stakelockers/stakelockerfactory.md)
  * [Stake Locker](smart-contracts/lockers/stakelockers/stakelocker.md)
  * [Sub Factory](smart-contracts/lockers/subfactory.md)
* [Oracles](smart-contracts/oracles/README.md)
  * [Chainlink Oracle](smart-contracts/oracles/chainlinkoracle.md)
  * [Oracle](smart-contracts/oracles/oracle.md)
  * [USD Oracle](smart-contracts/oracles/usdoracle.md)
* [Pools](smart-contracts/pools/README.md)
  * [Pool](smart-contracts/pools/pool.md)
  * [PoolFactory](smart-contracts/pools/poolfactory.md)
  * [PoolLib](smart-contracts/pools/poollib.md)
* [Proxy Factory](smart-contracts/proxyfactory/README.md)
  * [IDefaultImplementationBeacon](smart-contracts/proxyfactory/idefaultimplementationbeacon.md)
  * [IMapleProxied](smart-contracts/proxyfactory/imapleproxied.md)
  * [IProxied](smart-contracts/proxyfactory/iproxied.md)
  * [Maple Proxy Factory](smart-contracts/proxyfactory/mapleproxyfactory.md)
  * [Proxy](smart-contracts/proxyfactory/proxy.md)
* [Utils](smart-contracts/utils/README.md)
  * [Pool](smart-contracts/utils/util.md)

## API

* [Public](api/public.md)
* [Private](api/private.md)
* [Auth](api/auth.md)
* [Rates](api/rates.md)

## Archive - LBP <a id="maple-lbp"></a>

* [LBP Overview](maple-lbp/overview-1.md)
* [Frequently Asked Questions](maple-lbp/lbp-frequently-asked-questions.md)

## Additional Links and Resources <a id="additional-links"></a>

* [Risks](additional-links/risks.md)
* [Developer Documentation](https://github.com/maple-labs/maple-core)
* [Discord](https://discord.gg/Xy6sqxRhFG)
* [Blog](https://maplefinance.ghost.io/)
* [Interface Terms of Use](additional-links/interface-terms-of-use.md)
* [Privacy Policy](additional-links/privacy-policy.md)

