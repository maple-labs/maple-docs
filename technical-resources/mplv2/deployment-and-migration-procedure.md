# Phase 1 - Deployment of contracts
The following contracts will need to be deployed, in this specific order:
|Step | Contract  | Constructor Arguments  |
| --- |---|---|
| 1 | MapleToken (Implementation)  | - |
| 2 | MapleTokenInitializer  | - |
| 3 | MapleTokenProxy (Non-Transparent-Proxy)  | globals address, implementation address(1), initializer address(2), migrator* |
| 4 | RecapitalizationModule | token address(3) |
| 5 | Migrator | mplv1 address, mplv2 address(3)* | 

*There is a circular dependency between steps 3 and 5, as both depend on a contract deployed by the other. The solution to this is to rely on the deterministic addresses, which allows for computing the address that a contract will be deployed to before it actually happens. Therefore, for stage 3, using the sender key, we pre-compute the address that the Migrator will be deployed to, and pass that as a parameter.

After this step, the migrator is already able to exchange MPL V1 to MPL V2 at 1:1 exchange rate.

# Phase 2: Recapitalization Module setup
To add any module to the MPLv2 contract, the following transactions need to be made:

1. `Governor` should call `Globals.scheduleCall(token address, function id, encoded data)`, where:
 * `token address`: The deployed address of the `MapleTokenProxy` contract.
 * `function id`:   A bytes 32 indicating which function is being scheduled. In this case it's `"MT:ADD_MODULE"`.
 * `encoded data`:  Which can be computed using: `abi.encodeWithSelector(IMapleToken.addModule.selector, module)`

2. After the time lock period passed, the `Governor` should call `Token.addModule(module)`, where module is the Recapitalization module address.

3. The module is now able to mint tokens according to its specific business rule. However, to kickstart the issuance, an issuance window needs to be scheduled. Refer to [this documentation](technical-resources/mplv2/recapitalization-module.md#scheduling) for how to do that.

4. The `Governor` needs to set an actor as `RECAPITALIZATION_CLAIMER` in Globals, using the function `setInstanceOf("RECAPITALIZATION_CLAIMER", claimer address, true)`. 

# Phase 3 - Migration
<img src="../.gitbook/assets/migration-diagrams.png" alt="">

The migration process leverages the [migration contract](https://github.com/maple-labs/mpl-migration), which allows for a 1:1 exchange from the old token to MPL V2. To perform the migration, the migrator token must hold 10 million units of MPL V2. The migration contract can be used for both the xMPL contract and other entities.

## Standalone Migrations
Other entities can migrate performing the following steps:

1. Approve the `amount` of tokens to the `migrator` contract.
2. Call the the function `migrate(amount)`

The user should now have received exactly `amount` of MPLv2 tokens. This process will be available forever, meaning that, as long as someone have MPLv1 tokens, they can always receive the 1:1 of MPLv2.


## xMPL one time migration

This allows a seamless and safe migration for all users that have staked their MPL into the xMPL contract.

1. The first step to trigger a migration is for the contract governor to call `scheduleMigration`, which sets an execution to occur at least 10 days from the transaction time. In the meantime, all functionality in the xMPL contract remain operational.

2. During this period, any party that disagrees with the scheduled migration can withdraw their funds from the contract.

3. After the time delay, anyone can call `performMigration`, which executes the migration with the parameters set 10 days prior.

4. During the migration,the xMPL contract deposits its entire balance of MPL to the migrator contract, which includes non vested and vested funds.

5. The migrator contract takes the MPL amount and returns the exact same amount of MPLv2, with a 1:1 ratio. The MPL tokens will remain locked in the migrator contract so they cannot be migrated twice.

6. In the last step, the address defined as `asset` in xMPL contract is switched from MPLv1 to the newly migrated MPLv2 address. From that point on, all subsequent operations will be in relation to the new migrated token.

Holders of the xMPL token do not need to perform any action in order to migrate their tokens, however holders that do not interact with the xMPL contract would need to perform a migration by themselves.

For detailed information on the migration of xMPL, please refer to [this page](https://github.com/maple-labs/xmpl).
