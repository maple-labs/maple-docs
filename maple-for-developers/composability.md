# Overview

This section contains a brief overview of certain ERC standards that have been adopted in order to allow for a greater degree of composability between the Maple protocol and the rest of the Ethereum ecosystem:

| Contract Standard | Usage |
|-|-|
| [`ERC-20`](https://eips.ethereum.org/EIPS/eip-20)     | Used by the `Pool` to facilitate fungible token interactions. |
| [`ERC-1967`](https://eips.ethereum.org/EIPS/eip-1967) | Used by all upgradeable contracts in the Maple protocol that are deployed using `MapleProxyFactory` or `NonTransparentProxy`. |
| [`ERC-2612`](https://eips.ethereum.org/EIPS/eip-2612) | Used by the `Pool` to facilitate `permit` functionality for fungible token interactions. |
| [`ERC-4626`](https://eips.ethereum.org/EIPS/eip-4626) | Used by the `Pool` to facilitate easier integrations with protocols that want to interact with yield bearing fungible tokens. |
