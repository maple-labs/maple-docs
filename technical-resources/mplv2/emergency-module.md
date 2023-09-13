The EmergencyModule contract is designed to handle emergency situations within a protocol. It provides functionalities for burning and minting tokens under the control of the governor, as defined in the associated Globals contract.

It is not intended to be deployed, but rather just have it ready in case of any future emergency.

## Features
**Burning Tokens:** The contract allows the governor to burn a specified amount of tokens from a given address. This functionality can be used to remove tokens from circulation in emergency scenarios.

**Minting Tokens:** The governor can also mint a specified amount of tokens to the Maple Treasury address. This functionality enables the creation of new tokens in emergency situations.

Both calls can only be triggered by the Governor.