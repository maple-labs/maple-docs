# Overview

The MPL V2 contract includes a simple upgradability mechanism to provide a safeguard for unknown future use cases. The chosen pattern for upgradability is the [NonTransparentProxy](https://github.com/maple-labs/non-transparent-proxy) pattern, which has already been audited and used by the existing Globals contract. Due to the contained nature of MPL V2 a decision was made to not import the NTP directly, but rather just copy the functions over, most of them without functionality changes.

Notable changes from the NTP for the `MapleTokenProxy` are:
- The updated constructor logic.
- The use of a `GLOBALS_SLOT` in place of an `ADMIN_SLOT` because to change the implementation of the NTP a call needs to be scheduled in the MapleGlobals contract.

## Proxied Changes
In order to use the existing ERC20 as an implementation for a proxied contract, some small changes were made to it:

- **Constructor removal**
Having a constructor in an implementation contract doesn't make much sense as the actual storage used will be the proxy's one.

- **Immutable modifier**
Since the constructor was removed, the next step needed was to change the `decimals` variable from an `immutable` to a editable storage variable, to ensure that the proxied contracts could correctly reference it.

- **Making it abstract**
The resulting contract was marked as abstract, to make signify that it's incomplete and inheriting contracts need to implement functions to correctly return `name`, `symbol` and `decimal`.

The gist of the difference between the two version of the token can be seen [here](https://www.diffchecker.com/tbN1DhN8/)

