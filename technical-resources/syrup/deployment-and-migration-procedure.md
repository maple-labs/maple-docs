# Phase 1 - Deployment of contracts
The following contracts will need to be deployed, in this specific order:
|Step | Contract  | Constructor Arguments  |
| --- |---|---|
| 1 | MapleToken (Implementation)  | - |
| 2 | MapleTokenInitializer  | - |
| 3 | MapleTokenProxy (Non-Transparent-Proxy)  | globals address, implementation address(1), initializer address(2), migrator* |
| 4 | RecapitalizationModule | token address(3) |
| 5 | Migrator | mplv1 address, SYRUP address(3)* |

*There is a circular dependency between steps 3 and 5, as both depend on a contract deployed by the other. The solution to this is to rely on the deterministic addresses, which allows for computing the address that a contract will be deployed to before it actually happens. Therefore, for stage 3, using the sender key, we pre-compute the address that the Migrator will be deployed to, and pass that as a parameter.

After this step, the migrator is already able to exchange MPL V1 to SYRUP at 1:1 exchange rate.

# Phase 2: Recapitalization Module setup
To add any module to the SYRUP contract, the following transactions need to be made:

1. `Governor` should call `Globals.scheduleCall(token address, function id, encoded data)`, where:
 * `token address`: The deployed address of the `MapleTokenProxy` contract.
 * `function id`:   A bytes 32 indicating which function is being scheduled. In this case it's `"MT:ADD_MODULE"`.
 * `encoded data`:  Which can be computed using: `abi.encodeWithSelector(IMapleToken.addModule.selector, module)`

2. After the time lock period passed, the `Governor` should call `Token.addModule(module)`, where module is the Recapitalization module address.

3. The module is now able to mint tokens according to its specific business rule. However, to kickstart the issuance, an issuance window needs to be scheduled. Refer to [this documentation](technical-resources/syrup/recapitalization-module.md#scheduling) for how to do that.

4. The `Governor` needs to set an actor as `RECAPITALIZATION_CLAIMER` in Globals, using the function `setInstanceOf("RECAPITALIZATION_CLAIMER", claimer address, true)`.

# Phase 3 - Migration
![migration-diagrams](https://github.com/maple-labs/maple-docs/assets/59924029/8f81761a-1d97-4bb9-95b0-c853aea3b6ba)

The migration process leverages the migration contract, which allows for a 1:1 exchange from the old token to SYRUP. To perform the migration, the migrator token must hold 10 million units of SYRUP. 

## Standalone Migrations
Other entities can migrate performing the following steps:

1. Approve the `amount` of tokens to the `migrator` contract.
2. Call the the function `migrate(amount)`

The user should now have received exactly `amount` of SYRUP tokens. This process will be available forever, meaning that, as long as someone have MPLv1 tokens, they can always receive the 1:1 of MPLv2.

