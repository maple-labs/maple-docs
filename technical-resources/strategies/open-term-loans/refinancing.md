# Refinancing

Refinancing is defined as the revision of Loan terms, as per an agreement between the two parties involved with the Loan: the Borrower and Lender. The following actions can be performed in any permutation desired:
- Increase `principal`: requires additional funds to be added by the Lender
- Decrease `principal`
- Set `delegateServiceFeeRate`
- Set `gracePeriod`
- Set `noticePeriod`
- Set `interestRate`
- Set `lateFeeRate`
- Set `lateInterestPremiumRate`
- Set `paymentInterval`

Note that the Refinancer contract should never set the `fundsAsset`.

## Refinance Procedure

In order to facilitate a refinance, an agreement must be reached on-chain between the Lender and Borrower. This is performed using two functions:

### `proposeNewTerms()`

This function is called by the Lender, through the `Loan Manager`, passing in the smart contract address of the Refinancer contract, a deadline by which the terms must be accepted, and an array of ABI-encoded function calls. The Refinancer must be registered in Globals as an `OT_REFINANCER` instance and the array of calls must not be empty.

For example:
```js
bytes[] memory data = new bytes[](2);

data[0] = abi.encodeWithSignature("setInterestRate(uint64)",    newInterestRate_);
data[1] = abi.encodeWithSignature("increasePrincipal(uint256)", principalIncrease_);

loanManager.proposeNewTerms(address(loan), address(refinancer), deadline, data);
```

This function will take the hash of these changes, the deadline and the Refinancer smart contract address, and save it into storage in the Loan.

### `rejectNewTerms()`

Either party can withdraw a proposal before it is accepted. The Pool Delegate calls `rejectNewTerms()` through the Loan Manager, and the Borrower calls it on the Loan. It clears the stored commitment.

### `acceptNewTerms()`

This function is called by the other party, the Borrower, or by an address registered as a `BORROWER_ACTIONS` instance in Globals. In the call, the same parameters are passed to agree to the terms: the smart contract address of the Refinancer, the deadline and the array of ABI-encoded function calls. The call reverts if the deadline has passed.

This function calculates the hash again and compares it with the hash that was added to storage when `proposeNewTerms()` was called.

If the hashes match, the function calls are executed in a for loop as delegatecalls to the Refinancer contract, manipulating storage in the context of the Loan:

```js
for (uint256 i; i < calls_.length; ++i) {
    ( bool success, ) = refinancer_.delegatecall(calls_[i]);
    require(success, "ML:ANT:FAILED");
}
```

Once all of these execute successfully, any change in principal, along with the interest and fees accrued up to the refinance, is settled between the Borrower and Lender, after which the refinance is considered complete. Accepting new terms also clears any open loan call or impairment. A principal increase is funded through the Pool Manager, so it reverts if the Open Term Loan Manager would exceed its strategy cap.
