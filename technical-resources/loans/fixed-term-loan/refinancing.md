# Refinance Actions

Loan refinancing is defined as the revision of Loan terms, as per an agreement between the two parties involved with the Loan, the Borrower and Lender. The following actions can be performed in any permutation desired:
- Increase principal: Increases `principal`, `principalRequested`, and `drawableFunds` by a given `amount`, requires additional funds to be added by the Lender
- Set `collateralRequired`
- Set `closingRate`
- Set `endingPrincipal`: Must be less than current `principal` on Loan
- Set `gracePeriod`
- Set `interestRate`
- Set `lateFeeRate`
- Set `lateInterestPremiumRate`
- Set `paymentInterval`
- Set `paymentsRemaining`

Note that the Refinancer contract should never set the collateralAsset or fundsAsset and should never directly set `drawableFunds`, `principal` or `collateral`.

# Refinance Procedure

In order to facilitate a refinance, an agreement must be reached on-chain between the Lender and Borrower. This is performed using two functions:

### `proposeNewTerms()`

This function is called by the Borrower, passing in the smart contract address of the Refinancer contract, as well as an array of ABI-encoded function calls.

For example:
```js
bytes[] memory data = new bytes[](4);

data[0] = abi.encodeWithSignature("setCollateralRequired(uint256)", newCollateralRequired_);
data[1] = abi.encodeWithSignature("setEndingPrincipal(uint256)",    newEndingPrincipal_);
data[2] = abi.encodeWithSignature("setInterestRate(uint256)",       newInterestRate_);
data[3] = abi.encodeWithSignature("increasePrincipal(uint256)",     principalIncrease_);

loan.proposeNewTerms(address(refinancer), data);
```

This function will take the hash of these changes and the Refinancer smart contract address (`keccak256(abi.encode(refinancer_, calls_))`), and save it into storage in the Loan.

### `acceptNewTerms()`

This function is called by the Pool Delegate routing the call through the PoolManager and the appropriate LoanManager (LoanManager is the Lender in the Loan). In the call, the Pool Delegate passes in the same parameters to agree to the terms, the smart contract address of the Refinancer and the array of ABI-encoded function calls. This call is permissioned in the PoolManager to only be called by the PoolDelegate.

This function calculates the hash again (`keccak256(abi.encode(refinancer_, calls_))`) and compares it with the hash that was added to storage when `proposeNewTerms()` was called.

If the hashes match, the function calls are executed in a for loop as delegatecalls to the Refinancer contract, manipulating storage in the context of the Loan:

```js
for (uint256 i; i < calls_.length; ++i) {
    ( bool success, ) = refinancer_.delegatecall(calls_[i]);
    require(success, "MLI:ANT:FAILED");
}
```

Once all of these execute successfully, the collateral ratio is checked to make sure it is maintained, after which the refinance is considered complete.
