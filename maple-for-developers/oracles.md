# Overview
Oracle price feeds used in the Maple protocol to determine auction pricing for collateral liquidations in the `getExpectedAmount` function in the LoanManager.

Oracles for given assets are set using `Globals.setPriceOracle()`. For the majority of assets this will be Chainlink oracle wrappers, for USDC it will be a constant USD oracle. Oracle wrappers have the capability to provide a manual price in the event of an oracle outage, using the security multisig. In all other cases, it will simply pass through the value from `getLatestPrice` in the Chainlink oracle.
