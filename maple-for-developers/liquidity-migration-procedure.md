# Liquidity Migration Procedure

## Pre-Deployment Requirements

1. Migration Multisig becomes Pool Admin on all Pools
    - All PDs calls `setPoolAdmin(address,bool)` on their respective PoolV1s
2. Set the `investorFee` and `treasuryFee` to zero in GlobalsV1
    - Submit Gnosis Safe batch tx with `02-setInvestorFee-and-setTreasuryFee.json` as the GovernorV1
    - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the GovernorV1 Signer
3. Pay all upcoming loans
    1. Set ETH_RPC_URL locally to Tenderly fork URL `export ETH_RPC_URL=<URL>`
    2. Update `.env` file and update the block number in `migration-utils`
    3. Run `npm run generate-addresses` generate to solidity-formatted addresses
    4. Get addresses of the loans to pay from the respective `./addresses/<POOL>-loans-to-pay.txt` files in `migration-utils` and update `AddressRegistry.sol`
    5. Run `make pay-upcoming-loans` to pay all upcoming loans
    6. Run `make validate step=RemoveMaturedLoans` and delete loans that got paid from in AddressRegistry
        - This can actually be done more easily in 4.2
    7. Run `make validate step=PayAndClaimUpcomingLoans`
4. Upgrade all outstanding loans to 301
    1. Rerun `npm run generate-addresses` generate to solidity-formatted addresses
    2. Get addresses of all loans from the respective `./addresses/<POOL>-loans.txt` files in `migration-utils` and update `AddressRegistry.sol`
    3. Run `make upgrade-loans-301` to upgrade all loans to 301

<br>

## Deploy and Prep Protocol

    NOTE: Before starting
    - Set/check ETH_RPC_URL locally to Tenderly fork URL `export ETH_RPC_URL=<URL>`
    - Run `git submodule status` to confirm the tags of all submodules

5. Deploy the V2 Protocol and perform many configurations
    1. Run `make deploy` in `maple-core-v2`
    2. Run `make validate step=DeployProtocol`
    3. Run `make addresses` in `maple-core-v2`
    4. Replace null addresses with correct addresses in the broadcast file.
    5. Run `make addresses` in `maple-core-v2` again.
    6. Give the `deploy-addresses.json` file to the off-chain team.
    7. Copy the addresses from the `deploy-addresses.json` into the `.env` file and update the block number in `migration-utils`
    8. Rerun `npm run generate-addresses` generate to solidity-formatted addresses
    9. Get addresses of the lps from all `./addresses/<POOL>-lps.txt` files in `migration-utils` and update `AddressRegistry.sol`
    10. Check that `scripts/deploy-addresses-no-name.js` has no diff
    11. Run `npm run generate-jsons` to generate all JSON files
6. Temp GovernorV2 becomes governor of V2 protocol
    1. Submit Gnosis Safe batch tx with `06-acceptGovernor-on-mapleGlobalsV2.json` as the Temp GovernorV2
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=SetTemporaryGovernor`
7. Migration Multisig becomes admin for Migration Helper
    1. Submit Gnosis Safe batch tx with `07-acceptOwner-on-migrationHelper.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=SetMigrationMultisig`
8. Configure pre-existing DebtLocker and Loan factories
    1. Submit Gnosis Safe batch tx with `08-setup-dl-and-loan-factories.json` as the GovernorV1
        - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the GovernorV1 Signer
    2. Run `make validate step=RegisterDebtLockers`
    3. Run `make validate step=RegisterLoans`

<br>

## Pre-Kickoff

9. Upgrade DebtLockers of all outstanding loans to v400
    - Run `make upgrade-dls-400`
10. Claim any claimable loans across all pools
    1. Rerun `npm run generate-jsons` to generate all JSON files
    2. If there are any claimable loans (i.e. a `10-claim-loans.json` was created), claim them
        - Submit Gnosis Safe batch tx with `10-claim-loans.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask

<br>

## Kickoff

    NOTE: Before starting

    - Validate Pool Admin is correct for all PoolV1s by running `make validate step=SetPoolAdmins`
    - Ensure establishment fees are set to zero by running `make validate step=SetInvestorAndTreasuryFee`
    - Ensure all loans are paid within our tolerance, and that there are no late loans by running `make validate step=PayAndClaimUpcomingLoans`
    - Validate all loans are v301 by running `make validate step=UpgradeLoansToV301`
    - Validate all DLs are v400 by running `make validate step=UpgradeDebtLockersToV400`
    - Ensure that there are no claimable loans by running `Query subgraph`

11. Upgrade all outstanding loans from v301 to v302
    1. Submit Gnosis Safe batch tx with `11-upgrade-301-loans-to-302.json` as the Global Admin V1
        - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the Global Admin V1 Signer
    2. Run `make validate step=UpgradeLoansToV302`
12. Set Liquidity cap of all pools to 0
    1. Submit Gnosis Safe batch tx with `12-zeroLiquidityCaps.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=SetLiquidityCapsToZero`
13. Create migration loans if there is any outstanding liquidity on any pools
    1. Get LiquidityLockers' cash balances by running `make validate step=QueryLiquidityLockers`
    2. Verify balances via subgraph queries
    3. Set the respective migration loan amounts as `<POOL>-MIGRATION-LOAN-AMOUNT` in the `.env` file in `migration-utils` and confirm they correspond to the correct pools
    4. Rerun `npm run generate-jsons` to generate all JSON files
    5. If there are migration loans that need to be created (i.e. a `13-create-migration-loans.json` was created), create them:
        - Submit Gnosis Safe batch tx with `13-create-migration-loans.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    6. Get migration loan addresses from Tenderly UI events for the previous transaction
        - Run `npm run generate-addresses` as they should be found in the subgraph queries now
    7. Update loans and migration loan addresses in the  `AddressRegistry`
    8. Add loan amounts to the assertions in `CreateMigrationLoans`
    9. Run `make validate step=CreateMigrationLoans`
    10. Add the migration loan addresses to the `.env` file in `migration-utils` as `<POOL>_MIGRATION_LOAN`

<br>

## Migration Loan Funding

### Maven Permissioned Fund Migration Loan and Upgrade DebtLocker

14. Fund the Migration Loan
    1. Use the UI to fund Maven Permissioned Migration Loan
    2. Run `make validate step=FundMigrationLoans_MavenPermissioned`
15. Upgrade DebtLockers of Migration Loan, if it exists, to v400
    1. Use UI
        - If UI not possible, run `./scripts/upgrade-maven-perm-migration-loan-DL-400.sh` to upgrade Maven Permissioned Migration Loan DebtLocker
    2. Run `make validate step=UpgradeMigrationDebtLockers_MavenPermissioned`

### Maven USDC Pool V1 Fund Migration Loan and Upgrade DebtLocker

14. Fund the Migration Loan
    1. Use the UI to fund Maven USDC Migration Loan
    2. Run `make validate step=FundMigrationLoans_MavenUSDC`
15. Upgrade DebtLockers of Migration Loan, if it exists, to v400
    1. Use UI
        - If UI not possible, run `./scripts/upgrade-maven-usdc-migration-loan-DL-400.sh` to upgrade Maven USDC Migration Loan DebtLocker
    2. `make validate step=UpgradeMigrationDebtLockers_MavenUSDC`

### Maven WETH Pool V1 Fund Migration Loan and Upgrade DebtLocker

14. Fund the Migration Loan
    1. Use the UI to to fund Maven WETH Migration Loan
    2. Run `make validate step=FundMigrationLoans_MavenWETH`
15. Upgrade DebtLockers of Migration Loan, if it exists, to v400
    1. Use UI
        - If UI not possible, run `./scripts/upgrade-maven-weth-migration-loan-DL-400.sh` to upgrade Maven WETH Migration Loan DebtLocker
    2. Run `make validate step=UpgradeMigrationDebtLockers_MavenWETH`

### Orthogonal Pool V1 Fund Migration Loan and Upgrade DebtLocker

14. Fund the Migration Loan
    1. Use the UI to to fund Orthogonal Migration Loan
    2. Run `make validate step=FundMigrationLoans_Orthogonal`
15. Upgrade DebtLockers of Migration Loan, if it exists, to v400
    1. Us UI
        - If UI not possible, run `./scripts/upgrade-ortho-migration-loan-DL-400.sh` to upgrade Orthogonal Migration Loan DebtLocker
    2. Run `make validate step=UpgradeMigrationDebtLockers_Orthogonal`

### Icebreaker Pool V1 Fund Migration Loan and Upgrade DebtLocker

14. Fund the Migration Loan
    1. Use the UI to to fund Icebreaker Migration Loan
    2. Run `make validate step=FundMigrationLoans_Icebreaker`
15. Upgrade DebtLockers of Migration Loan, if it exists, to v400
    1. Use UI
        - If UI not possible, run `./scripts/upgrade-icebreaker-migration-loan-DL-400.sh` to upgrade Icebreaker Migration Loan DebtLocker
    2. Run `make validate step=UpgradeMigrationDebtLockers_Icebreaker`

<br>

## Upgrade Migration Loans

16. Upgrade Migration Loans
    1. Rerun `npm run generate-jsons` in `migration-utils`
    2. If there are migration loans, upgrade them to 302
        1. Submit Gnosis Safe batch tx with `16-upgrade-301-migration-loans-to-302.json` as the Global Admin V1
            - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the Global Admin V1 Signer
        2. Run `make validate step=UpgradeMigrationLoans`

<br>

## Pause V1 Protocol

17. Pause V1 Protocol
    1. Submit Gnosis Safe batch tx with `17-pause-v1-protocol.json` as the Global Admin V1
        - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the Global Admin V1 Signer
    2. Run `make validate step=PauseProtocol`

<br>

## Deploy PoolV2s

### Deploy Maven Permissioned Pool V2

    NOTE: Before starting

    - Confirm all pool parameters with business team in JSON and in `.env` in `migration-utils`
    - Double check PD address that is deploying the pool

18. Deploy Maven Permissioned Pool V2
    1. Run `./scripts/get-frozen-pool-state.sh` to get the cash, principalOut, total value and sum of Lps in the pool.
        - `cash` must equal 0
        - `principalOut == poolValue`
        - `poolValue` must be within a dust amount of `sumLps`
    2. Add `poolValue` to `.env` in `migration-utils` under `MAVEN_PERMISSIONED_INITIAL_SUPPLY`
    3. Rerun `npm run generate-jsons`
    4. Deploy Maven Permissioned Pool V2
        - Submit Gnosis Safe batch tx with `18-mavenPermissioned-deployPool.json` as the Maven Permissioned Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    5. Get Maven Permissioned pool, PM, LM, WM addresses
        - run `make validate step=QueryMavenPermPoolV2Addresses`
    6. Add all 3 addresses to `AddressRegistry`
    7. Add all 3 addresses to `.env` in `migration-utils` under `MAVEN_PERMISSIONED_POOL_MANAGER`, `MAVEN_PERMISSIONED_LOAN_MANAGER`, and `MAVEN_PERMISSIONED_WITHDRAWAL_MANAGER` respectively
    8. Ensure Maven Permissioned Pool has been properly deployed and configured
        - **[script TODO]**

### Deploy Maven USDC Pool V2

18. Deploy Maven USDC Pool V2
    1. Run `./scripts/get-frozen-pool-state.sh` to get the cash, principalOut, total value and sum of Lps in the pool.
        - `cash` must equal 0
        - `principalOut == poolValue`
        - `poolValue` must be within a dust amount of `sumLps`
    2. Add `poolValue` to `.env` in `migration-utils` under `MAVEN_USDC_INITIAL_SUPPLY`
    3. Rerun `npm run generate-jsons`
    4. Deploy Maven USDC Pool V2
        - Submit Gnosis Safe batch tx with `18-mavenUsdc-deployPool.json` as the Maven USDC Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    5. Get Maven USDC pool, PM, LM, WM addresses
        - run `make validate step=QueryMavenUsdcPoolV2Addresses`
    6. Add all 3 addresses to `AddressRegistry`
    7. Add all 3 values to `.env` in `migration-utils` under `MAVEN_USDC_POOL_MANAGER`, `MAVEN_USDC_LOAN_MANAGER`, and `MAVEN_USDC_WITHDRAWAL_MANAGER` respectively
    8. Ensure Maven USDC Pool has been properly deployed and configured
        - **[script TODO]**

### Deploy Maven WETH Pool V2

18. Deploy Maven WETH Pool V2
    1. Run `./scripts/get-frozen-pool-state.sh` to get the cash, principalOut, total value and sum of Lps in the pool.
        - `cash` must equal 0
        - `principalOut == poolValue`
        - `poolValue` must be within a dust amount of `sumLps`
    2. Add `poolValue` to `.env` in `migration-utils` under `MAVEN_WETH_INITIAL_SUPPLY`
    3. Rerun `npm run generate-jsons`
    4. Deploy Maven WETH Pool V2
        - Submit Gnosis Safe batch tx with `18-mavenWeth-deployPool.json` as the Maven WETH Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    5. Get Maven WETH pool, PM, LM, WM addresses
        - run `make validate step=QueryMavenWethPoolV2Addresses`
    6. Add all 3 addresses to `AddressRegistry`
    7. Add all 3 values to `.env` in `migration-utils` under `MAVEN_WETH_POOL_MANAGER`, `MAVEN_WETH_LOAN_MANAGER`, and `MAVEN_WETH_WITHDRAWAL_MANAGER` respectively
    8. Ensure Maven WETH Pool has been properly deployed and configured
        - **[script TODO]**

### Deploy Orthogonal Pool V2

18. Deploy Orthogonal Pool V2
    1. Run `./scripts/get-frozen-pool-state.sh` to get the cash, principalOut, total value and sum of Lps in the pool.
        - `cash` must equal 0
        - `principalOut == poolValue`
        - `poolValue` must be within a dust amount of `sumLps`
    2. Add `poolValue` to `.env` in `migration-utils` under `ORTHOGONAL_INITIAL_SUPPLY`
    3. Rerun `npm run generate-jsons`
    4. Deploy Orthogonal Pool V2
        - Submit Gnosis Safe batch tx with `18-orthogonal-deployPool.json` as the Orthogonal Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    5. Get Orthogonal pool, PM, LM, WM addresses
        - run `make validate step=QueryOrthogonalWethPoolV2Addresses`
    6. Add all 3 addresses to `AddressRegistry`
    7. Add all 3 values to `.env` in `migration-utils` under `ORTHOGONAL_POOL_MANAGER`, `ORTHOGONAL_LOAN_MANAGER`, and `ORTHOGONAL_WITHDRAWAL_MANAGER` respectively
    8. Ensure Orthogonal Pool has been properly deployed and configured
        - **[script TODO]**

### Deploy Icebreaker Pool V2

18. Deploy Icebreaker Pool V2
    1. Run `./scripts/get-frozen-pool-state.sh` to get the cash, principalOut, total value and sum of Lps in the pool.
        - `cash` must equal 0
        - `principalOut == poolValue`
        - `poolValue` must be within a dust amount of `sumLps`
    2. Add `poolValue` to `.env` in `migration-utils` under `ICEBREAKER_INITIAL_SUPPLY`
    3. Rerun `npm run generate-jsons`
    4. Deploy Icebreaker Pool V2
        - Submit Gnosis Safe batch tx with `18-icebreaker-deployPool.json` as the Icebreaker Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    5. Get Icebreaker pool, PM, LM, WM addresses
        - run `make validate step=QueryIcebreakerWethPoolV2Addresses`
    6. Add all 3 addresses to `AddressRegistry`
    7. Add all 3 values to `.env` in `migration-utils` under `ICEBREAKER_POOL_MANAGER`, `ICEBREAKER_LOAN_MANAGER`, and `ICEBREAKER_WITHDRAWAL_MANAGER` respectively
    8. Ensure Icebreaker Pool has been properly deployed and configured
        - **[script TODO]**

<br>

## Configure Platform Fees

19. Set platformManagementFeeRate, platformServiceFeeRate, platformOriginationFeeRate, and maxCoverLiquidationPercent
    1. Submit Gnosis Safe batch tx with `19-fee-setting.json` as the Temp GovernorV2
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask

## Add Loan to Pool V2s

20. Add all loans to all respective loan managers
    1. Rerun `npm run generate-jsons`
    2. Remove loans that were paid off manually until we can get subgraph working
    3. Submit Gnosis Safe batch tx with `20-add-loans-to-lms.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    4. Ensure all accounting is configured correctly
        - **[script TODO]**
    5. Spot check APY
        - **[TODO]**
    6. Run full lifecycle simulation
        - **[script TODO]**

<br>

## Prepare for Airdrops

### Activate all Pool Managers

21. Activate the pool managers
    1. Submit Gnosis Safe batch tx with `21-activatePoolManagers.json` as the Temp GovernorV2
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=ActivatePools`

### Enable LPs at Maven Permissioned Pool

22. Allow lenders (including the Withdrawal Manager) given that the pool is permissioned
    1. Submit Gnosis Safe batch tx with `22-mavenPermissioned-allowlist-lps.json` as the Maven Permissioned Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=PermissionPools`

### Open the Maven USDC Pool

22. Open the pool
    1. Submit Gnosis Safe batch tx with `22-mavenUsdc-openToPublic.json` as the Maven USDC Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=OpenPools`

### Open the Maven WETH Pool

22. Open the pool
    1. Submit Gnosis Safe batch tx with `22-mavenWeth-openToPublic.json` as the Maven Weth Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=OpenPools`

### Open the Orthogonal Pool

22. Open the pool
    1. Submit Gnosis Safe batch tx with `22-orthogonal-openToPublic.json` as the Maven Orthogonal Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=OpenPools`

### Enable LPs at Icebreaker Pool

22. Allow lenders (including the Withdrawal Manager) given that the pool is permissioned
    1. Submit Gnosis Safe batch tx with `22-icebreaker-allowlist-lps.json` as the Icebreaker Temp PD
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=PermissionPools`

<br>

## Airdrop all Tokens

23. Airdrop respective Pool V2 tokens to respective sets of LPs
    1. Submit Gnosis Safe batch tx with `23-airdrops-to-lps.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=CheckLpPositions`

<br>

## Transfer Loans

24. Initiate lender transfers for all loan to respective transitional loan managers
    1. Submit Gnosis Safe batch tx with `24-setPendingLenders.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=SetPendingLenders`
25. Complete lender transfers for all loan to respective transitional loan managers
    1. Submit Gnosis Safe batch tx with `25-takeOwnershipOfLoans.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=AcceptPendingLenders`
26. Upgrade transitional loan managers (100) to loan managers (200)
    1. Submit Gnosis Safe batch tx with `26-upgrade-tlms-to-lms.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    2. Run `make validate step=UpgradeTLM`
27. Upgrade all Loans (including migration loans) from v302 to v400
    1. Submit Gnosis Safe batch tx with `27-upgrade-302-loans-to-400` as the Global Admin V1
        - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the Global Admin V1 Signer
    2. Run `make validate step=UpgradeLoansToV400`

<br>

## Close Migration Loans

28. Set globals of LoanFactory to Maple Globals V2
    1. Submit Gnosis Safe batch tx with `28-setGlobals-on-loanFactory.json` as the GovernorV1
        - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the GovernorV1 Signer
    2. Run **[script TODO]**
29. Close all migration loans
    1. Set the respective migration loan closing fee amounts as `<POOL>-_MIGRATION_LOAN_CLOSING_AMOUNT` in the `.env` file in `migration-utils` and confirm they correspond to the correct pools
    2. Rerun `npm run generate-jsons` to generate all JSON files
    3. Submit Gnosis Safe batch tx with `29-closeLoans-withFees.json` as the Migration Multisig
        - For simulation, Gnosis safe with V2 Deployer connected with Metamask
    4. Run `make validate step=CloseMigrationLoans`

<br>

## Deactivate PoolV1s

### Prepare PoolV1 Deactivation

30. Set zero price oracles and staker cooldown for deactivation
    1. Submit Gnosis Safe batch tx with `30-setPriceOracle-and-setStakerCooldownPeriod.json` as the GovernorV1
        - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the GovernorV1 Signer
    2. Run **[script TODO]**
31. Unpause V1 Protocol
    1. Submit Gnosis Safe batch tx with `31-unpause-v1-protocol.json` as the Global Admin V1
        - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the Global Admin V1 Signer
    2. Run **[script TODO]**

### Deactivation Maven Permissioned PoolV1

32. Call `deactivate()` in the Tenderly UI using the Maven Permissioned PD address
33. Call `setLockupPeriod(0)` in the Tenderly UI using the Maven Permissioned V1 PD address (Try without this next time)
34. Call `intendToUnstake()` in the Tenderly UI using the Maven Permissioned V1 PD address (will this be in the webapp?)
35. No need to do `exit()`
36. Call `unstake()` in the Tenderly UI using the Maven Permissioned V1 PD address

### Deactivation Maven USDC PoolV1

32. Call `deactivate()` in the Tenderly UI using the Maven USDC PD address
33. No need to do `setLockupPeriod(0)`
34. Call `intendToUnstake()` in the Tenderly UI using the Maven USDC V1 PD address (will this be in the webapp?)
35. Call `exit()` on the SL Rewards contract in the Tenderly UI Maven USDC V1 PD address
36. Call `unstake()` in the Tenderly UI using the Maven USDC V1 PD address

### Deactivation Maven WETH PoolV1

32. Call `deactivate()` in the Tenderly UI using the Maven WETH PD address
33. No need to do `setLockupPeriod(0)`
34. Call `intendToUnstake()` in the Tenderly UI using the Maven WETH V1 PD address (will this be in the webapp?)
35. Call `exit()` on the SL Rewards contract in the Tenderly UI Maven WETH V1 PD address
36. Call `unstake()` in the Tenderly UI using the Maven WETH V1 PD address

### Deactivation Orthogonal PoolV1

32.  Call `deactivate()` in the Tenderly UI using the Orthogonal PD address
33.  Call `setLockupPeriod(0)` in the Tenderly UI using the Orthogonal V1 PD address
34.  Call `intendToUnstake()` in the Tenderly UI using the Orthogonal V1 PD address (will this be in the webapp?)
35.  Call `exit()` on the SL Rewards contract in the Tenderly UI Orthogonal V1 PD address
36.  Call `unstake()` in the Tenderly UI using the Orthogonal V1 PD address

### Deactivation Icebreaker PoolV1

32. Call `deactivate()` in the Tenderly UI using the IcebreakerV1 PD address
33. Call `setLockupPeriod(0)` in the Tenderly UI using the IcebreakerV1 PD address
34. Call `intendToUnstake()` in the Tenderly UI using the IcebreakerV1 PD address (will this be in the webapp?)
35. No need to do `exit()`
36. Call `unstake()` in the Tenderly UI using the IcebreakerV1 PD address

<br>

## Transfer PoolV2s to Official PoolDelegate

### Enable Official PoolDelegates

37. Set validity of PoolDelegates
    - Submit Gnosis Safe batch tx with `37-setValidPoolDelegates.json` as the Temp GovernorV2
    - For simulation, Gnosis safe with V2 Deployer connected with Metamask

### Transfer Maven Permissioned Pool V2 to Official PoolDelegate

38. Set pending PoolDelegate of Maven Permissioned Pool
    - Submit Gnosis Safe batch tx with `38-mavenPermissioned-setPendingPoolDelegate.json` as the Maven Permissioned Temp PD
    - For simulation, Gnosis safe with V2 Deployer connected with Metamask
39. Final Maven Permissioned PoolDelegate calls `acceptPoolDelegate` from UI

### Transfer Maven USDC Pool V2 to Official PoolDelegate

38. Set pending PoolDelegate of Maven USDC Pool
    - Submit Gnosis Safe batch tx with `38-mavenUsdc-setPendingPoolDelegate.json` as the Maven USDC Temp PD
    - For simulation, Gnosis safe with V2 Deployer connected with Metamask
39. Final Maven USDC PoolDelegate calls `acceptPoolDelegate` from UI

### Transfer Maven WETH Pool V2 to Official PoolDelegate

38. Set pending PoolDelegate of Maven WETH Pool
    - Submit Gnosis Safe batch tx with `38-mavenWeth-setPendingPoolDelegate.json` as the Maven WETH Temp PD
    - For simulation, Gnosis safe with V2 Deployer connected with Metamask
39. Final Maven WETH PoolDelegate calls `acceptPoolDelegate` from UI

### Transfer Orthogonal Pool V2 to Official PoolDelegate

38. Set pending PoolDelegate of Orthogonal Pool
    - Submit Gnosis Safe batch tx with `38-orthogonal-setPendingPoolDelegate.json` as the Orthogonal Temp PD
    - For simulation, Gnosis safe with V2 Deployer connected with Metamask
39. Final Orthogonal PoolDelegate calls `acceptPoolDelegate` from UI

### Transfer Icebreaker Pool V2 to Official PoolDelegate

38. Set pending PoolDelegate of Icebreaker Pool
    - Submit Gnosis Safe batch tx with `38-icebreaker-setPendingPoolDelegate.json` as the Icebreaker Temp PD
    - For simulation, Gnosis safe with V2 Deployer connected with Metamask
39. Final Icebreaker PoolDelegate calls `acceptPoolDelegate` from UI

<br>

## Transfer Governorship of GlobalsV2

40. Set pending governor of GlobalsV2
    - Submit Gnosis Safe batch tx with `40-setPendingGovernor-on-mapleGlobalsV2.json` as the Temp GovernorV2
    - For simulation, Gnosis safe with V2 Deployer connected with Metamask
41. Accept governor of GlobalsV2
    - Submit Gnosis Safe batch tx with `41-acceptGovernor-on-mapleGlobalsV2.json` as the GovernorV1
    - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the GovernorV1 Signer

<br>

## Tentatively Finalize V2 Protocol

42. Set default version of Loan Factory to 400
    1. Submit Gnosis Safe batch tx with `42-loanFactory-400.json` as the GovernorV1
    - For simulation, Gnosis safe with another Google Chrome profile and use impersonator.xyz to sign in as the GovernorV1 Signer
<br>
