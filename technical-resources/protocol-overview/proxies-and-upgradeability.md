# Overview
Across the protocol, many proxy contracts are used, incorporating upgradeability functionality. These contracts are deployed using the same pattern, governed by the MapleProxyFactory contract. This is a generic factory contract that deploys proxies and manages their implementations using the Governor. This patten has multiple benefits as listed below.

### Cheaper deployment of contracts
Since proxies are being deployed instead of full contracts, the gas cost of contract deployment goes down significantly. This is because the bytecode size of the proxy smart contracts is much smaller than its corresponding implementation.

### Single factory contract can manage many versions
Since the proxies are deployed from a central factory contract, this contract can be allowlisted in MapleGlobals once by the Governor, and then can be used for many versions afterwards. The Governor manages all versions that are to be used by contracts deployed by a given factory, so upgrades can only happen to implementation contracts that have been vetted by both the protocol smart contracts team and the Maple DAO.

It is also beneficial from an events perspective to use a single contract for the factory, as all creation events will come from the same address. For a new version of a contract to be used a new implementation must be deployed, and the implementation must be registered and tied to a version by the Governor. Once that is done, all subsequent contracts deployed from the factory will use that version.

# Version Management

In order to manage versions in the `MapleProxyFactory`, the following actions are performed by the Governor only:
- **Add a new version**: Once an implementation is deployed, that implementation can be registered in the context of the factory and tied to a version identifier.
- **Enable/Disable upgrade path**: If it is determined to be entirely safe to upgrade a deployed proxy instance from one implementation to another, the upgrade path can be added to the factory by the Governor. Only then can upgrades be performed by Borrowers from one version to another.
- **Set the default version**: The default version is the version that is used for all deployments of contracts. This means that if it is decided that an older version is preferable, it can be set and all new deployments will be at the old version. It also means that the factory can be paused by the Governor if the default version is set to zero, since that will return a null implementation which will prevent the deployment of new contracts.

## Proxy Deployment

Below is a diagram outlining the smart contract architecture and calls used for factories. It should be noted that the `_initialize` functionality was intentionally moved to a separate smart contract so that the same "initializer" could be used across many versions, and so that "migrators" could be used, instead of "initializers", when upgrading from one implementation to another. Effectively, an "initializer" is a very specific "migrator", in that is sets up the storage of a contract that went from _no_ implementation, to some specific implementation.

![](https://user-images.githubusercontent.com/35537333/141997215-1ffff07f-9d93-420c-bf93-9d35b8b71ec9.png)

# Proxy Upgrades

Below is a diagram outlining the process for upgrading a proxy contract.
When an upgrade is performed the following occurs:
1. Borrower calls `upgrade()` on the Proxy.
2. Proxy delegatecalls `upgrade()` to v2.0.0 implementation.
3. `upgrade()` calls the MapleLoanFactory to do `upgradeInstance()`, which checks that this is a valid upgrade path.
4. `upgradeInstance()` calls `setImplementation()` on the Proxy.
5. Proxy delegatecalls `setImplementation()` to v2.0.0 implementation, which updates the implementation address in Proxy storage at `IMPLEMENTATION_SLOT` to the v3.0.0 implementation address.
6. `upgradeInstance()` calls `migrate()` on the Proxy.
7. Proxy delegatecalls `migrate()` to the v3.0.0 implementation.
8. v3.0.0 implementation delegatecalls `migrate()` to the Migrator, which updates any storage necessary in the Proxy to finalize the upgrade.

![](https://user-images.githubusercontent.com/35537333/141996856-bf9bbb08-0935-49ad-9d58-459dc8279c14.png)

## Note on MapleLoan Implementation

The MapleLoan contract, during a refinancing, performs a `delegatecall`, which is a dangerous operation. One common concern is that someone would be able to access those functions in the implementation contract and do something like a `selfdestruct`, which would destroy all existing loans. However, this is not possible, since all functions in the Loan that perform such calls are access controlled, meaning that they would always fail being called directly in the implementation because all storage is empty. Access-control storage variables cannot be altered in the implementation itself because of the fact that Initializer contracts are used. The `initialize` functionality of the implementation is performed outside of the implementation itself.
