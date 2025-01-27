## Exposing Mints and Burns

The `mint` and `burn` functions of the SYRUP contract need to be exposed only to authorized actors. While the ERC20 contract does not distinguish between different types of actors, SYRUP prefers using minting modules to enforce strict rules. The mint function in the base token will be kept simple and only include authorization checks. The control over the total supply or availability of tokens will reside with the authorized actors.

## Modules

Modules are smart contracts with pre-defined rules that can mint or burn MPL tokens. Authorized modules have a significant impact on the token and the protocol and should aim for simplicity to avoid unintended consequences. The onboarding and offboarding of modules will be performed off-chain. The SYRUP contract will store a single authorized address that can add or remove modules. This entity, such as the `Governor` multisig or another account, is assumed to act according to off-chain governance decisions. The token itself will not impose any restrictions or checks on the actions of allowing modules.

To activate the module, the following actions needed to be taken:

```
1. An off-chain proposal for adding the module was made.
2. If the proposal was passed, the allowed entity scheduled an execution in the Globals contract.
3. After the time lock period passed, the module could be added as an authorized minter.
4. According the the specific module rules, tokens can be minted or burned.
```
