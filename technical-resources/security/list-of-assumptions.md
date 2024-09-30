# List of Assumptions

This page outlines all assumptions that have been made by the smart contracts team in relation to smart contract security and trust models.

#### 1. All external calls to contracts that are part of the Maple Protocol System can be assumed to be non-reentrant.

Since all contracts that are deployed as part of the Maple protocol are developed by the Maple smart contracts team and are externally audited before deployment, it can be assumed that the contracts are both non-reentrant and non-malicious.

#### 2. All external calls to ERC-20 contracts can be assumed to be non-reentrant.

This assumption is made since all tokens that are used in the Maple protocol have to be added to the protocol allowlist, in the MapleGlobals contract. This means that the smart contracts team will audit the ERC-20 contracts and ensure that reentrancy is impossible.

#### 3. Oracle prices from Chainlink are considered to be reasonably accurate and frequently updated.

Since the oracle price is used in the liquidation module, it is assumed that these prices are accurate and cannot be exploited (e.g., flash loan oracle manipulation is impossible with an offchain oracle source).

#### 4. The Governor & Operational Admin are trusted actors.

The Governor multisig is held by founders and partners of the protocol, that are heavily incentivized to act in the protocol's best interest. Likewise the Operational Admin is held by the Maple team, which is also heavily incentivized to act in the protocol's best interest.

#### 5. Loans are expected to be instantiated with reasonable terms.

During the fuzz testing process, it was discovered that certain overflow conditions can occur in the amortization calculation of the loan, but only at "unreasonable" upper bounds (E.g., 100-year loans with 1 year payment intervals at 100% APR, for >$10b).
