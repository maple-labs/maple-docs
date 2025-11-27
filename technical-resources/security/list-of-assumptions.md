# List of Assumptions

This page outlines all assumptions that have been made by the smart contracts team in relation to smart contract security and trust models.

#### 1. All external calls to contracts that are part of the Maple Protocol System can be assumed to be non-reentrant.

Since all contracts that are deployed as part of the Maple protocol are developed by the Maple smart contracts team and are externally audited before deployment, it can be assumed that the contracts are both non-reentrant and non-malicious.

#### 2. All external calls to ERC-20 contracts can be assumed to be non-reentrant.

This assumption is made since all tokens that are used in the Maple protocol have to be added to the protocol allowlist, in the MapleGlobals contract. This means that the smart contracts team will audit the ERC-20 contracts and ensure that reentrancy is impossible.

#### 3. Pool Delegates are trusted actors.

Pool Delegates have to go through a KYC process and have to get onboarded to the Maple protocol by the Governor. They have a public reputation to protect, and are incentivized to act in the protocol's best interest to grow their pool's size. Liquidity Providers and Stakers are inherently trusting a Pool Delegate with their funds when they enter a Maple Pool. This means that they are trusting the Pool Delegate to handle funds and liquidation proceedings in a trusted manner.

#### 4. Oracle prices from Chainlink are considered to be reasonably accurate and frequently updated.

Since the oracle price is used in the liquidation module, it is assumed that these prices are accurate and cannot be exploited (e.g., flash loan oracle manipulation is impossible with an offchain oracle source).

#### 5. The Governor & Operational Admin are trusted actors.

Governor control is exercised via the on‑chain `GovernorTimelock`, whose controlling roles (e.g., proposer, executor, role admin) are held by Maple managed multisigs. 

The Operational Admin is also a multisig controlled by Maple managed multisigs.

#### 6. Loans are expected to be instantiated with reasonable terms.

During the fuzz testing process, it was discovered that certain overflow conditions can occur in the amortization calculation of the loan, but only at "unreasonable" upper bounds (E.g., 100-year loans with 1 year payment intervals at 100% APR, for >$10b).

#### 7. Pool Delegates don't try to prevent withdrawals.

It's known that, in theory, withdrawal managers can be configured to unreasonable terms, for example, making the withdrawal window 1 second, or the cycle duration to be large,or pool delegates can set the withdrawal manager address to an invalid address. However, it's understood that pool delegates are trusted actors and they are working to making the pool well functioning.
