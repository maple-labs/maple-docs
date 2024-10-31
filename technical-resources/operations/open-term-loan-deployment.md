# Phase 1 - Deploy New Contracts
Deploy and verify the following contracts using a single forge script:

## New PoolDeployer
1. New PoolDeployer pointing to existing mapleGlobalsProxy

## Globals and PoolManager Upgrade Contracts
1. Globals v2.0.0 implementation
2. PoolManager v2.0.0 implementation

## Fixed Term Loan Upgrade Contracts
1. MapleLoan v5.0.1 implementation
2. MapleLoanInitializer for v5.0.0 deployments
3. MapleLoanMigrator for v4.0.0 -> v5.0.0 upgrades
4. LoanManager v3.0.1 implementation

## Open Term Loan Manager Contracts
1. LoanManagerFactory
2. LoanManagerImplementation v1.0.0 implementation
3. LoanManagerInitializer for v1.0.0 deployments

## Open Term Loan Contracts
1. MapleLoanFactory
2. MapleLoanInitializer for v1.0.1 deployments
3. MapleLoanImplementation v1.0.1 implementation
4. MapleRefinancer for v1.0.1 deployments

# Phase 2 - Configuration of Protocol by Governor
This phase will be set up by the smart contracts team with JSONs and Gnosis Safe. This set of transactions will be simulated on Tenderly and validated.
This will include three main actions:
1. Upgrade Globals
2. Allowlist all relevant contracts in Globals
3. Configure factories with newest contract versions
4. Upgrade all PoolManager and LoanManager contracts
5. Set canDeploy for all existing borrowers

Details are outlined below.

## Upgrade Globals
```solidity
globals.setImplementation(newGlobalsImplementation)
```

## Allowlist All Contracts
```solidity
globals_.setValidInstanceOf("LIQUIDATOR_FACTORY",         liquidatorFactory,        true);
globals_.setValidInstanceOf("POOL_MANAGER_FACTORY",       poolManagerFactory,       true);
globals_.setValidInstanceOf("WITHDRAWAL_MANAGER_FACTORY", withdrawalManagerFactory, true);

globals_.setValidInstanceOf("FT_LOAN_FACTORY", fixedTermLoanFactory, true);
globals_.setValidInstanceOf("LOAN_FACTORY",    fixedTermLoanFactory, true);

globals_.setValidInstanceOf("OT_LOAN_FACTORY", openTermLoanFactory, true);
globals_.setValidInstanceOf("LOAN_FACTORY",    openTermLoanFactory, true);

globals_.setValidInstanceOf("FT_LOAN_MANAGER_FACTORY", fixedTermLoanManagerFactory, true);
globals_.setValidInstanceOf("LOAN_MANAGER_FACTORY",    fixedTermLoanManagerFactory, true);

globals_.setValidInstanceOf("OT_LOAN_MANAGER_FACTORY", openTermLoanManagerFactory, true);
globals_.setValidInstanceOf("LOAN_MANAGER_FACTORY",    openTermLoanManagerFactory, true);

globals_.setValidInstanceOf("FT_REFINANCER", fixedTermRefinancerV2, true);
globals_.setValidInstanceOf("REFINANCER",    fixedTermRefinancerV2, true);

globals_.setValidInstanceOf("OT_REFINANCER", openTermRefinancerV1, true);
globals_.setValidInstanceOf("REFINANCER",    openTermRefinancerV1, true);

globals_.setValidInstanceOf("FEE_MANAGER", fixedTermFeeManagerV1, true);

globals_.setCanDeployFrom(poolManagerFactory,       poolDeployerV2, true);
globals_.setCanDeployFrom(withdrawalManagerFactory, poolDeployerV2, true);

// setCanDeploy for all valid borrowers for OTL Factory
for (uint256 i; i < validBorrowers.length; ++i) {
    globals_.setCanDeployFrom(openTermLoanFactory, validBorrowers[i], true);
}
```

## Configure Factories
### Register PoolManager Version v2.0.0 and v1.0.0 -> v2.0.0 Upgrade
```solidity
poolManagerFactory.registerImplementation(200, poolManagerImplementationV200, poolManagerInitializer);
poolManagerFactory.setDefaultVersion(200);
poolManagerFactory.enableUpgradePath(100, 200, address(0));
```

### Register FixedTermLoan Version v5.0.1 and v4.0.0 -> v5.0.1 Upgrade
```solidity
fixedTermLoanFactory.registerImplementation(501, fixedTermLoanImplementationV501, fixedTermLoanInitializerV500);
fixedTermLoanFactory.setDefaultVersion(501);
fixedTermLoanFactory.enableUpgradePath(400, 501, fixedTermLoanMigratorV500);
```

### Register FixedTermLoanManager Version v3.0.1 and v2.0.0 -> v3.0.1 Upgrade
```solidity
fixedTermLoanManagerFactory.registerImplementation(301, fixedTermLoanManagerImplementationV301, fixedTermLoanManagerInitializerV300);
fixedTermLoanManagerFactory.setDefaultVersion(301);
fixedTermLoanManagerFactory.enableUpgradePath(200, 301, address(0));
```

### Register OpenTermLoan Version v1.0.1
```solidity
openTermLoanFactory.registerImplementation(101, openTermLoanImplementationV101, openTermLoanInitializerV100);
openTermLoanFactory.setDefaultVersion(101);
```

### Register OpenTermLoanManager Version v1.0.0
```solidity
openTermLoanManagerFactory.registerImplementation(100, openTermLoanManagerImplementationV100, openTermLoanManagerInitializerV100);
openTermLoanManagerFactory.setDefaultVersion(100);
```

## Upgrade all PoolManagers
Upgrade all (currently 8) outstanding PoolManager contracts.
```solidity
poolManager.upgrade(200, "0x");
```

## Upgrade all Fixed Term LoanManagers
Upgrade all (currently 8) outstanding LoanManager contracts.
```solidity
loanManager.upgrade(301, "0x");
```

This procedure contains a significant amount of function calls, so it will need to determined if it can all be performed in one transaction or will require multiple.

# Phase 3 - Security Admin Upgrades all Loans
This step will also be done with a JSON fed into a Gnosis Safe multisig, which will be simulated against Tenderly and validated by the smart contracts team before being performed on mainnet. The number of function calls will depend on the number of outstanding loans at deployment.

```solidity
loan.upgrade(501, "0x")
```

# Key Deprecation in Globals
Once the smart contracts team has deemed it safe, all old keys used for allowlisting can be set to false.
## Remove Contracts from Old Allowlist
```solidity
globals_.setValidInstanceOf("LIQUIDATOR",         liquidatorFactory,           false);
globals_.setValidInstanceOf("LOAN_MANAGER",       fixedTermLoanManagerFactory, false);
globals_.setValidInstanceOf("POOL_MANAGER",       poolManagerFactory,          false);
globals_.setValidInstanceOf("WITHDRAWAL_MANAGER", withdrawalManagerFactory,    false);
globals_.setValidInstanceOf("LOAN",               fixedTermLoanFactory,        false);

globals_.setValidPoolDeployer(poolDeployer, false);
```

# Post-Upgrade
## Adding Open Term Loan Managers
After the protocol has been deployed, the PoolDelegates can call:
```solidity
poolManager.addLoanManager(openTermLoanManagerFactory)
```
to add a new OpenTermLoanManager to their Pools if they would like to fund new Open Term Loans.
