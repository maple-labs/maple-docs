# Maple V2 Deployment

## Protocol Deployment

1. Confirm Governor address.
2. Confirm Treasury address.
3. Deploy MapleGlobalsV2 implementation address and verify on Etherscan.
4. Deploy MapleGlobalsV2 proxy address and verify on Etherscan, declaring the Governor and implementation address.
5. Deploy the Pool Deployer contract, declaring the MapleGlobalsV2 address.
6. Set values in the MapleGlobalsV2 contract with the Governor address (revisit this):
   1. `globals.setMapleTreasury(treasury);`
   2. `globals.setMigrationAdmin(migrationAdmin);`
   3. `globals.setSecurityAdmin(securityAdmin);`
   4. `globals.setValidPoolAsset(USDC, true); (Do for all assets)`
   5. `globals.setPriceOracle(USDC, 1e8); (Do for all assets`
   6. `globals.setValidPoolDeployer(address(deployer), true);`
   7. `globals.setDefaultTimelockParameters(1 weeks, 2 days);`
7. Deploy all proxy factories, implementations, and initializers, passing in MapleGlobalsV2 to the factories:
   1. Liquidator
   2. LoanManager
   3. PoolManager
   4. WithdrawalManager
   5. Ignore Loan since it has already been deployed.
8. Register implementations for all factories and set default versions:
   1. Liquidator - 100
   2. LoanManager - 100
   3. PoolManager - 100
   4. WithdrawalManager - 100
   5. Ignore Loan to avoid accidental deployments of V4 loans prior to migration.
9. Allowlist all factories in Maple Globals:
   1. Liquidator
   2. Loan
   3. LoanManager
   4. PoolManager
   5. WithdrawalManager
10. Transfer ownership of MapleGlobalsV2 to the governor.
    1.  `globals.setPendingGovernor(governor);`
    2.  `globals.acceptGovernor();`

At this stage, the following is true:
1. MapleGlobalsV2 is deployed and controlled by the governor
2. All factories are ready to deploy protocol contracts.
3. Allowed Assets are ready to be used in the protocol.
4. Oracles are configured.
5. Migration and Security admins are configured.
