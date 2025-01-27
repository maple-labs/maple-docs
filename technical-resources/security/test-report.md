# Test Reports

Below is an report of all smart contract level tests that are run against the protocol, in all repos.

Current number of tests in this report is: **2888 tests**.

# `maple-core-v2`

```
Ran 7 tests for tests/integration/withdrawal-manager/queue/AddShares.t.sol:AddSharesQueueFailureTests
[PASS] test_addShares_failIfAlreadyInQueue() (gas: 345255)
[PASS] test_addShares_failIfEmptyRequest() (gas: 106092)
[PASS] test_addShares_failIfInsufficientApproval() (gas: 101091)
[PASS] test_addShares_failIfNotPool() (gas: 45861)
[PASS] test_addShares_failIfNotPoolManager() (gas: 18919)
[PASS] test_addShares_failIfProtocolIsPaused() (gas: 65881)
[PASS] test_addShares_failIfTransferFail() (gas: 115635)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 16.40ms (662.71µs CPU time)

Ran 5 tests for tests/integration/loan-manager/fixed-term/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 69416)
[PASS] test_removeLoanImpairment_notGovernor() (gas: 265224)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 82756)
[PASS] test_removeLoanImpairment_notLender() (gas: 37828)
[PASS] test_removeLoanImpairment_pastDate() (gas: 348591)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 17.33ms (544.42µs CPU time)

Ran 3 tests for tests/integration/loan/fixed-term/Liquidation.t.sol:FinishLiquidationFailureTests
[PASS] test_finishLiquidation_failIfLiquidationNotActive() (gas: 102416)
[PASS] test_finishLiquidation_failIfNotPD() (gas: 56031)
[PASS] test_finishLiquidation_failIfNotPoolManager() (gas: 54860)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 17.45ms (135.21µs CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:DepositWithPermitFailureTests
[PASS] test_depositWithPermit_invalidSignature() (gas: 530430)
[PASS] test_depositWithPermit_liquidityCapExceeded() (gas: 509179)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient() (gas: 450335)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 421625)
[PASS] test_depositWithPermit_protocolPaused() (gas: 164710)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 18.95ms (2.86ms CPU time)

Ran 2 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairAndRefinanceTests
[PASS] test_impairLoan_earlyThenRefinance() (gas: 1213560)
[PASS] test_impairLoan_lateThenRefinance() (gas: 978759)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 19.86ms (2.66ms CPU time)

Ran 2 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairSuccessTests
[PASS] test_impairLoan_thenCancel() (gas: 898638)
[PASS] test_impairLoan_thenRepay() (gas: 917948)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 20.68ms (2.14ms CPU time)

Ran 2 tests for tests/integration/pool/DepositAndMint.t.sol:MintWithPermitTests
[PASS] testDeepFuzz_mintWithPermit_singleUser(uint256) (runs: 10, μ: 352286, ~: 352286)
[PASS] test_mintWithPermit_singleUser() (gas: 350737)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 24.96ms (9.19ms CPU time)

Ran 5 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxMintTests
[PASS] testDeepFuzz_maxMint_exchangeRateGtOne(uint256,uint256,uint256) (runs: 10, μ: 447785, ~: 447785)
[PASS] testDeepFuzz_maxMint_totalAssetsIncrease(uint256,uint256) (runs: 10, μ: 277104, ~: 277044)
[PASS] test_maxMint_closedPool() (gas: 301510)
[PASS] test_maxMint_exchangeRateGtOne() (gas: 437063)
[PASS] test_maxMint_totalAssetsIncrease() (gas: 269832)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 32.18ms (15.73ms CPU time)

Ran 4 tests for tests/integration/withdrawal-manager/queue/AddShares.t.sol:AddSharesQueueTests
[PASS] test_addShares_manual() (gas: 349580)
[PASS] test_addShares_partialRequest() (gas: 307380)
[PASS] test_addShares_success() (gas: 478704)
[PASS] test_addShares_withApproval() (gas: 319647)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 16.32ms (1.21ms CPU time)

Ran 6 tests for tests/integration/withdrawal-manager/queue/RemoveRequest.t.sol:RemoveRequestFailureTests
[PASS] test_removeRequest_failIfNotGovernor() (gas: 182628)
[PASS] test_removeRequest_failIfNotInQueue() (gas: 137749)
[PASS] test_removeRequest_failIfNotOperationalAdmin() (gas: 186702)
[PASS] test_removeRequest_failIfNotPoolDelegate() (gas: 178222)
[PASS] test_removeRequest_failIfProtocolIsPaused() (gas: 54800)
[PASS] test_removeRequest_failIfTransferFail() (gas: 168406)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 16.76ms (666.67µs CPU time)

Ran 4 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairFailureTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 252596)
[PASS] test_impairLoan_notAuthorized() (gas: 56986)
[PASS] test_impairLoan_notLender() (gas: 37891)
[PASS] test_impairLoan_protocolPaused() (gas: 52118)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 16.33ms (264.21µs CPU time)

Ran 9 tests for tests/integration/loan-manager/ImpairLoan.t.sol:OpenTermLoanManagerImpairTests
[PASS] testFail_impairLoan_notLoanContract() (gas: 40542)
[PASS] test_impairLoan_early() (gas: 240697)
[PASS] test_impairLoan_governorAcl() (gas: 127239)
[PASS] test_impairLoan_late() (gas: 242188)
[PASS] test_impairLoan_loanInactive() (gas: 234308)
[PASS] test_impairLoan_notAuthorized() (gas: 59395)
[PASS] test_impairLoan_notLender() (gas: 38313)
[PASS] test_impairLoan_notLoanInLoanManager() (gas: 477738)
[PASS] test_impairLoan_protocolPaused() (gas: 52118)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 16.54ms (1.20ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/FetchValuesFromLM.t.sol:LoanManagerIsLiquidationActiveGetterTests
[PASS] test_isLiquidationActive_afterLiquidation() (gas: 1111887)
[PASS] test_isLiquidationActive_beforeLiquidation() (gas: 15920)
[PASS] test_isLiquidationActive_duringLiquidation() (gas: 627975)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 16.19ms (919.83µs CPU time)

Ran 2 tests for tests/integration/pool/DepositAndMint.t.sol:DepositWithPermitTests
[PASS] testDeepFuzz_depositWithPermit_singleUser(uint256) (runs: 10, μ: 351473, ~: 351479)
[PASS] test_depositWithPermit_singleUser() (gas: 347121)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 24.21ms (9.05ms CPU time)

Ran 3 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxRedeemTests
[PASS] test_maxRedeem_lockedShares_inExitWindow() (gas: 464329)
[PASS] test_maxRedeem_lockedShares_notInExitWindow() (gas: 453748)
[PASS] test_maxRedeem_noLockedShares_notInExitWindow() (gas: 289472)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 15.25ms (858.50µs CPU time)

Ran 4 tests for tests/integration/withdrawal-manager/queue/RemoveRequest.t.sol:RemoveRequestTests
[PASS] test_removeRequest_forManual() (gas: 347145)
[PASS] test_removeRequest_manualPartialRedemption() (gas: 481841)
[PASS] test_removeRequest_partialRedemption() (gas: 501077)
[PASS] test_removeRequest_success() (gas: 498319)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 16.54ms (1.93ms CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:MintFailureTests
[PASS] test_mint_insufficientApproval() (gas: 347358)
[PASS] test_mint_liquidityCapExceeded() (gas: 499361)
[PASS] test_mint_privatePoolInvalidRecipient() (gas: 418686)
[PASS] test_mint_privatePoolInvalidRecipient_openPoolToPublic() (gas: 390025)
[PASS] test_mint_protocolPaused() (gas: 165231)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 15.51ms (1.39ms CPU time)

Ran 9 tests for tests/integration/loan-manager/ImpairLoan.t.sol:OpenTermLoanManagerRemoveImpairmentTests
[PASS] test_removeLoanImpairment_early() (gas: 257988)
[PASS] test_removeLoanImpairment_late() (gas: 259015)
[PASS] test_removeLoanImpairment_late_withLateImpairment() (gas: 259201)
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 72656)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 93652)
[PASS] test_removeLoanImpairment_notLender() (gas: 38379)
[PASS] test_removeLoanImpairment_notLoan() (gas: 41122)
[PASS] test_removeLoanImpairment_poolDelegateAfterGovernor() (gas: 153367)
[PASS] test_removeLoanImpairment_protocolPaused() (gas: 52118)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 16.53ms (1.38ms CPU time)

Ran 14 tests for tests/integration/loan/fixed-term/Liquidation.t.sol:LoanLiquidationTests
[PASS] test_finishCollateralLiquidation_asOperationalAdmin() (gas: 2436989)
[PASS] test_loanDefault_fullCover_noCollateral_noImpairment() (gas: 1555588)
[PASS] test_loanDefault_fullCover_noCollateral_withImpairment() (gas: 1643896)
[PASS] test_loanDefault_fullCover_withCollateral_noImpairment() (gas: 2586253)
[PASS] test_loanDefault_fullCover_withCollateral_withImpairment() (gas: 2618773)
[PASS] test_loanDefault_noCover_noCollateral_noImpairment() (gas: 1447058)
[PASS] test_loanDefault_noCover_noCollateral_withImpairment() (gas: 1539130)
[PASS] test_loanDefault_noCover_withCollateral_noImpairment() (gas: 2490938)
[PASS] test_loanDefault_noCover_withCollateral_withImpairment() (gas: 2525555)
[PASS] test_loanDefault_partialCover_noCollateral_noImpairment() (gas: 1555309)
[PASS] test_loanDefault_partialCover_noCollateral_withImpairment() (gas: 1643877)
[PASS] test_loanDefault_partialCover_withCollateral_noImpairment() (gas: 2585824)
[PASS] test_loanDefault_partialCover_withCollateral_withImpairment() (gas: 2618719)
[PASS] test_setMaxCoverLiquidationPercent_asOperationalAdmin() (gas: 40433)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 36.40ms (21.75ms CPU time)

Ran 6 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxRedeemWMQueueTests
[PASS] test_maxRedeem_afterFullManualRedeem() (gas: 354894)
[PASS] test_maxRedeem_afterFullRedeem() (gas: 237107)
[PASS] test_maxRedeem_afterPartialManualRedeem() (gas: 394740)
[PASS] test_maxRedeem_afterPartialRedeem() (gas: 240687)
[PASS] test_maxRedeem_beforeRedeem() (gas: 37255)
[PASS] test_maxRedeem_notManual() (gas: 386947)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 16.35ms (1.51ms CPU time)

Ran 9 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesCyclicalFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 226630)
[PASS] test_removeShares_failIfInvalidShares() (gas: 107485)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 107449)
[PASS] test_removeShares_failIfNotPool() (gas: 45816)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 19241)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 65925)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 193894)
[PASS] test_removeShares_failIfTransferFail() (gas: 184086)
[PASS] test_removeShares_failIfWithdrawalIsPending() (gas: 246115)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 15.32ms (1.07ms CPU time)

Ran 4 tests for tests/integration/pool/FetchValuesFromPM.t.sol:PoolManagerGetterTests
[PASS] testDeepFuzz_getEscrowParams_shouldReturnValues(uint256) (runs: 10, μ: 22071, ~: 21493)
[PASS] test_addressGetters() (gas: 37488)
[PASS] test_hasSufficientCover_insufficientCover(uint256) (runs: 10, μ: 141255, ~: 140651)
[PASS] test_hasSufficientCover_sufficientCover(uint256) (runs: 10, μ: 152798, ~: 153224)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 29.18ms (14.99ms CPU time)

Ran 5 tests for tests/integration/loan-manager/fixed-term/LoanManagerGetters.t.sol:LoanManagerGetterTests
[PASS] test_loanManagerGetters_addresses() (gas: 21380)
[PASS] test_loanManagerGetters_liquidationInformation() (gas: 1157178)
[PASS] test_loanManagerGetters_paymentInformation() (gas: 29855)
[PASS] test_loanManagerGetters_sortedPayments() (gas: 1364949)
[PASS] test_loanManagerGetters_uints() (gas: 32825)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 16.79ms (1.63ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesCyclicalTests
[PASS] test_removeShares_pastTheRedemptionWindow() (gas: 175858)
[PASS] test_removeShares_prematurelyAddedShares() (gas: 459422)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 584390)
[PASS] test_removeShares_success() (gas: 176031)
[PASS] test_removeShares_withApproval() (gas: 193331)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 16.24ms (1.83ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxWithdrawTests
[PASS] testDeepFuzz_maxWithdraw_lockedShares_inExitWindow(uint256) (runs: 10, μ: 456330, ~: 456418)
[PASS] test_maxWithdraw_lockedShares_inExitWindow() (gas: 450862)
[PASS] test_maxWithdraw_lockedShares_notInExitWindow() (gas: 447147)
[PASS] test_maxWithdraw_noLockedShares_notInExitWindow() (gas: 283032)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 22.30ms (8.15ms CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_failIfNotLoan() (gas: 69766)
[PASS] test_makePayment_failWithTransferFailed() (gas: 234960)
[PASS] test_makePayment_failWithTransferFromFailed() (gas: 143722)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 15.49ms (307.63µs CPU time)

Ran 4 tests for tests/integration/loan-manager/fixed-term/FinishCollateralLiquidation.t.sol:FinishCollateralLiquidationFailureTests
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 56032)
[PASS] test_finishCollateralLiquidation_notFinished() (gas: 652534)
[PASS] test_finishCollateralLiquidation_notPoolManager() (gas: 54816)
[PASS] test_finishCollateralLiquidation_whenImpaired() (gas: 288096)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 15.93ms (614.71µs CPU time)

Ran 4 tests for tests/integration/pool/DepositAndMint.t.sol:MintTest
[PASS] testDeepFuzz_mint_singleUser(uint256) (runs: 10, μ: 315969, ~: 315844)
[PASS] testDeepFuzz_mint_variableExchangeRate(uint256,uint256) (runs: 10, μ: 1660060, ~: 1660051)
[PASS] test_mint_singleUser_oneToOne() (gas: 311547)
[PASS] test_mint_twoUsers_oneToOne() (gas: 464833)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 37.24ms (23.34ms CPU time)

Ran 8 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesQueueFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 218169)
[PASS] test_removeShares_failIfInvalidShares() (gas: 98796)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 96506)
[PASS] test_removeShares_failIfNotPool() (gas: 45749)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 19241)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 65947)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 183472)
[PASS] test_removeShares_failIfTransferFail() (gas: 181587)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 15.75ms (856.83µs CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewDepositTests
[PASS] test_previewDeposit_multipleUsers() (gas: 498799)
[PASS] test_previewDeposit_multipleUsers_changeTotalAssets() (gas: 528427)
[PASS] test_previewDeposit_nonZeroTotalSupply() (gas: 298263)
[PASS] test_previewDeposit_zeroTotalSupply() (gas: 12500)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 15.71ms (1.17ms CPU time)

Ran 9 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentOpenTermFailureTests
[PASS] test_makePayment_inactiveLoan() (gas: 474492)
[PASS] test_makePayment_invalidPrincipalIncrease() (gas: 58071)
[PASS] test_makePayment_notLoan() (gas: 517601)
[PASS] test_makePayment_tooLittlePrincipal() (gas: 139093)
[PASS] test_makePayment_tooMuchPrincipal() (gas: 44022)
[PASS] test_makePayment_transferFailed() (gas: 84776)
[PASS] test_makePayment_transferToPoolBoundary() (gas: 265697)
[PASS] test_makePayment_transferToPoolDelegateBoundary() (gas: 314118)
[PASS] test_makePayment_transferToTreasuryBoundary() (gas: 400775)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 16.47ms (1.26ms CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:MintWithPermitFailureTests
[PASS] test_mintWithPermit_insufficientPermit() (gas: 532462)
[PASS] test_mintWithPermit_liquidityCapExceeded() (gas: 551796)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient() (gas: 459744)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 431038)
[PASS] test_mintWithPermit_protocolPaused() (gas: 168817)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 17.03ms (2.81ms CPU time)

Ran 10 tests for tests/integration/loan-manager/Fund.t.sol:FixedTermLoanManagerFundTests
[PASS] test_fund_failIfAmountGreaterThanLockedLiquidity() (gas: 1793585)
[PASS] test_fund_failIfInsufficientCover() (gas: 260536)
[PASS] test_fund_failIfLoanActive() (gas: 1012488)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 56264)
[PASS] test_fund_failIfPoolDoesNotApprovePM() (gas: 283199)
[PASS] test_fund_failIfProtocolIsPaused() (gas: 59926)
[PASS] test_fund_failIfTermsNotAccepted() (gas: 315137)
[PASS] test_fund_failIfTotalSupplyIsZero() (gas: 479075)
[PASS] test_fund_oneLoan() (gas: 884514)
[PASS] test_fund_twoLoans() (gas: 1456523)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 19.88ms (4.79ms CPU time)

Ran 11 tests for tests/fuzz/HasPermission.t.sol:HasPermissionFuzzTests
[PASS] testFuzz_hasPermission_deposit(uint256,uint256,uint256,bool,uint256) (runs: 10, μ: 369133, ~: 333954)
[PASS] testFuzz_hasPermission_depositWithPermit(uint256,uint256,uint256,bool,uint256) (runs: 10, μ: 409352, ~: 464044)
[PASS] testFuzz_hasPermission_mint(uint256,uint256,uint256,bool,uint256) (runs: 10, μ: 423185, ~: 424875)
[PASS] testFuzz_hasPermission_mintWithPermit(uint256,uint256,uint256,bool,uint256) (runs: 10, μ: 389442, ~: 395199)
[PASS] testFuzz_hasPermission_redeem(uint256,uint256,uint256,bool,uint256,address) (runs: 10, μ: 793727, ~: 816672)
[PASS] testFuzz_hasPermission_removeShares(uint256,uint256,uint256,bool,uint256,uint256) (runs: 10, μ: 779797, ~: 797506)
[PASS] testFuzz_hasPermission_requestRedeem(uint256,uint256,uint256,bool,uint256) (runs: 10, μ: 590912, ~: 633845)
[PASS] testFuzz_hasPermission_requestWithdraw(uint256,uint256,uint256,bool,uint256) (runs: 10, μ: 360642, ~: 378026)
[PASS] testFuzz_hasPermission_transfer(uint256,uint256,address,uint256,bool,address,uint256,bool,uint256) (runs: 10, μ: 566513, ~: 564883)
[PASS] testFuzz_hasPermission_transferFrom(uint256,uint256,address,uint256,bool,address,uint256,bool,address,uint256) (runs: 10, μ: 574691, ~: 573041)
[PASS] testFuzz_hasPermission_withdraw(uint256,uint256,uint256,bool,uint256,address) (runs: 10, μ: 292455, ~: 292657)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 113.64ms (96.73ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesQueueTests
[PASS] test_removeShares_manual_partiallyProcessed() (gas: 722140)
[PASS] test_removeShares_partiallyProcessed() (gas: 440545)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 612912)
[PASS] test_removeShares_success() (gas: 183699)
[PASS] test_removeShares_withApproval() (gas: 200977)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 17.32ms (2.59ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewMintTests
[PASS] test_previewMint_multipleUsers() (gas: 499949)
[PASS] test_previewMint_multipleUsers_changeTotalAssets() (gas: 529556)
[PASS] test_previewMint_nonZeroTotalSupply() (gas: 299457)
[PASS] test_previewMint_zeroTotalSupply() (gas: 12355)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 15.35ms (1.17ms CPU time)

Ran 1 test for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsDomainStartGtDomainEnd
[PASS] test_makePayment_domainStart_gt_domainEnd() (gas: 3807834)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 18.66ms (4.09ms CPU time)

Ran 18 tests for tests/integration/loan-manager/Fund.t.sol:OpenTermLoanManagerFundTests
[PASS] test_fund_failIfTermsNotAccepted() (gas: 498040)
[PASS] test_fund_insufficientCover() (gas: 405693)
[PASS] test_fund_invalidBorrower() (gas: 102264)
[PASS] test_fund_invalidLoanFactory() (gas: 88294)
[PASS] test_fund_invalidLoanInstance() (gas: 220276)
[PASS] test_fund_invalidLoanManagerFactory() (gas: 138156)
[PASS] test_fund_loanActive() (gas: 778297)
[PASS] test_fund_loanManagerApproveFailure() (gas: 477533)
[PASS] test_fund_loanNotActive() (gas: 719475)
[PASS] test_fund_loanTransferFailure() (gas: 551574)
[PASS] test_fund_lockedLiquidity() (gas: 603893)
[PASS] test_fund_notLender() (gas: 38572)
[PASS] test_fund_notLoanManager() (gas: 382308)
[PASS] test_fund_notPoolDelegate() (gas: 56309)
[PASS] test_fund_poolManagerTransferFailure() (gas: 423233)
[PASS] test_fund_protocolPause() (gas: 52119)
[PASS] test_fund_success() (gas: 688564)
[PASS] test_fund_zeroSupply() (gas: 624915)
Suite result: ok. 18 passed; 0 failed; 0 skipped; finished in 19.61ms (5.01ms CPU time)

Ran 7 tests for tests/integration/withdrawal-manager/queue/SetManualWithdrawal.t.sol:SetManualWithdrawalTests
[PASS] test_setManualWithdrawal_failIfLpAlreadyInQueue() (gas: 283511)
[PASS] test_setManualWithdrawal_failIfNotProtocolAdmin() (gas: 61330)
[PASS] test_setManualWithdrawal_failIfProtocolIsPaused() (gas: 55019)
[PASS] test_setManualWithdrawal_success() (gas: 83340)
[PASS] test_setManualWithdrawal_successAsGovernor() (gas: 87679)
[PASS] test_setManualWithdrawal_successAsOperationalAdmin() (gas: 91820)
[PASS] test_setManualWithdrawal_unsetSuccess() (gas: 78691)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 14.65ms (463.25µs CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewRedeemTests
[PASS] test_previewRedeem_invalidShares() (gas: 438194)
[PASS] test_previewRedeem_lockedShares_inExitWindow() (gas: 472635)
[PASS] test_previewRedeem_lockedShares_notInExitWindow() (gas: 443677)
[PASS] test_previewRedeem_noLockedShares_notInExitWindow() (gas: 36768)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.90ms (1.00ms CPU time)

Ran 1 test for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsPastDomainEnd
[PASS] test_makePayment_lateLoan3_loan1NotPaid_loan2NotPaid() (gas: 1039666)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 17.77ms (1.20ms CPU time)

Ran 1 test for tests/integration/globals/Upgrade.t.sol:UnscheduleCallTests
[PASS] test_unscheduleCall_governor() (gas: 89288)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 14.29ms (85.21µs CPU time)

Ran 4 tests for tests/integration/loan-manager/fixed-term/SetMinRatioAndSlippage.t.sol:SetMinRatioTests
[PASS] test_setMinRatio_notAuthorized() (gas: 57413)
[PASS] test_setMinRatio_notPoolManager() (gas: 57413)
[PASS] test_setMinRatio_withGovernor() (gas: 85553)
[PASS] test_setMinRatio_withPoolDelegate() (gas: 79678)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.26ms (160.87µs CPU time)

Ran 7 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewRedeemWithQueueWMTests
[PASS] test_previewRedeem_emptyRedemption_fullLiquidity() (gas: 130143)
[PASS] test_previewRedeem_emptyRedemption_partialLiquidity() (gas: 130250)
[PASS] test_previewRedeem_fullRedemption_fullLiquidity() (gas: 130487)
[PASS] test_previewRedeem_fullRedemption_partialLiquidity() (gas: 130567)
[PASS] test_previewRedeem_insufficientShares() (gas: 38451)
[PASS] test_previewRedeem_partialRedemption_fullLiquidity() (gas: 131080)
[PASS] test_previewRedeem_partialRedemption_partialLiquidity() (gas: 131190)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 15.06ms (595.13µs CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:WithdrawalManagerUpgradeTests
[PASS] test_upgradeWithdrawalManager_delayNotPassed() (gas: 147694)
[PASS] test_upgradeWithdrawalManager_durationPassed() (gas: 148438)
[PASS] test_upgradeWithdrawalManager_governor_noTimelockNeeded() (gas: 174649)
[PASS] test_upgradeWithdrawalManager_noTimelock() (gas: 156051)
[PASS] test_upgradeWithdrawalManager_timelockExtended() (gas: 257349)
[PASS] test_upgradeWithdrawalManager_timelockShortened() (gas: 258160)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 15.32ms (928.58µs CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanAmortized
[PASS] test_makePayment_earlyPayment_amortized() (gas: 794366)
[PASS] test_makePayment_latePayment_amortized() (gas: 807637)
[PASS] test_makePayment_onTimePayment_amortized() (gas: 794394)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 17.69ms (2.54ms CPU time)

Ran 5 tests for tests/integration/loan-manager/fixed-term/SetMinRatioAndSlippage.t.sol:SetSlippageTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 131108)
[PASS] test_setAllowedSlippage_notAuthorized() (gas: 57326)
[PASS] test_setAllowedSlippage_notPoolManager() (gas: 57370)
[PASS] test_setAllowedSlippage_withGovernor() (gas: 85514)
[PASS] test_setAllowedSlippage_withPoolDelegate() (gas: 79618)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 14.31ms (227.87µs CPU time)

Ran 1 test for tests/integration/globals/ValidCollateral.t.sol:ValidCollateralTests
[PASS] test_setIsCollateral_invalidCollateral() (gas: 846163)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 14.59ms (381.17µs CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanInterestOnly
[PASS] test_makePayment_earlyPayment_interestOnly() (gas: 765432)
[PASS] test_makePayment_latePayment_interestOnly() (gas: 775752)
[PASS] test_makePayment_onTimePayment_interestOnly() (gas: 762770)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 17.56ms (2.36ms CPU time)

Ran 6 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewWithdrawTests
[PASS] testDeepFuzz_previewWithdraw(uint256) (runs: 10, μ: 34829, ~: 34829)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_inExitWindow(uint256) (runs: 10, μ: 445761, ~: 446366)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_notInExitWindow(uint256) (runs: 10, μ: 445924, ~: 446426)
[PASS] test_previewWithdraw() (gas: 277876)
[PASS] test_previewWithdraw_zeroAssetsWithDeposit() (gas: 277853)
[PASS] test_previewWithdraw_zeroAssetsWithoutDeposit() (gas: 34588)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 33.24ms (19.11ms CPU time)

Ran 8 tests for tests/integration/permission-manager/SetPoolPermissionLevel.t.sol:SetPoolPermissionLevelTests
[PASS] testFuzz_setPoolPermissionLevel(uint256,uint256) (runs: 10, μ: 112061, ~: 113855)
[PASS] testFuzz_setPoolPermissionLevel_invalidLevel(uint256) (runs: 10, μ: 47476, ~: 47413)
[PASS] testFuzz_setPoolPermissionLevel_publicPool(uint256) (runs: 10, μ: 94661, ~: 94812)
[PASS] test_setPoolPermissionLevel_anotherPoolDelegate() (gas: 79465)
[PASS] test_setPoolPermissionLevel_governor() (gas: 69295)
[PASS] test_setPoolPermissionLevel_notAuthorized() (gas: 44995)
[PASS] test_setPoolPermissionLevel_operationalAdmin() (gas: 73548)
[PASS] test_setPoolPermissionLevel_poolDelegate() (gas: 66919)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 28.18ms (14.15ms CPU time)

Ran 4 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanOpenTerm
[PASS] test_makePayment_OT_latePayment() (gas: 725028)
[PASS] test_makePayment_OT_onTimePayment() (gas: 716760)
[PASS] test_makePayment_OT_withCall() (gas: 693848)
[PASS] test_makePayment_OT_withImpairment() (gas: 769661)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 18.30ms (3.59ms CPU time)

Ran 1 test for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewWithdrawWithQueueWMTests
[PASS] testFuzz_previewWithdraw(address,bool,uint256,uint256,uint256) (runs: 10, μ: 645491, ~: 654297)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 23.97ms (10.02ms CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsTwoLoans
[PASS] test_makePayment_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 1533936)
[PASS] test_makePayment_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 1548503)
[PASS] test_makePayment_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 1534075)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 21.29ms (5.79ms CPU time)

Ran 5 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:TotalAssetsTests
[PASS] test_totalAssets_singleDeposit() (gas: 273909)
[PASS] test_totalAssets_singleLoanFunded() (gas: 1593923)
[PASS] test_totalAssets_singleLoanFundedWithInterest() (gas: 1628068)
[PASS] test_totalAssets_singleLoanFundedWithPayment() (gas: 1864162)
[PASS] test_totalAssets_zeroTotalSupply() (gas: 64619)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 17.29ms (3.12ms CPU time)

Ran 12 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolEntry_functionLevel_deposit() (gas: 417764)
[PASS] test_poolEntry_functionLevel_depositWithPermit() (gas: 465964)
[PASS] test_poolEntry_functionLevel_depositWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 420241)
[PASS] test_poolEntry_functionLevel_depositWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 383393)
[PASS] test_poolEntry_functionLevel_deposit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 373927)
[PASS] test_poolEntry_functionLevel_deposit_zeroPoolBitmap_zeroLenderBitmap() (gas: 337166)
[PASS] test_poolEntry_functionLevel_mint() (gas: 423026)
[PASS] test_poolEntry_functionLevel_mintWithPermit() (gas: 472238)
[PASS] test_poolEntry_functionLevel_mintWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 424335)
[PASS] test_poolEntry_functionLevel_mintWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 387598)
[PASS] test_poolEntry_functionLevel_mint_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 377491)
[PASS] test_poolEntry_functionLevel_mint_zeroPoolBitmap_zeroLenderBitmap() (gas: 340665)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 18.72ms (4.62ms CPU time)

Ran 1 test for tests/fuzz/Mint.t.sol:MintFuzzTests
[PASS] testDeepFuzz_mint_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 10, μ: 495562, ~: 508926)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 29.70ms (15.20ms CPU time)

Ran 12 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolEntry_poolLevel_deposit() (gas: 417879)
[PASS] test_poolEntry_poolLevel_depositWithPermit() (gas: 465946)
[PASS] test_poolEntry_poolLevel_depositWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 420238)
[PASS] test_poolEntry_poolLevel_depositWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 383476)
[PASS] test_poolEntry_poolLevel_deposit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 373988)
[PASS] test_poolEntry_poolLevel_deposit_zeroPoolBitmap_zeroLenderBitmap() (gas: 337206)
[PASS] test_poolEntry_poolLevel_mint() (gas: 423094)
[PASS] test_poolEntry_poolLevel_mintWithPermit() (gas: 472221)
[PASS] test_poolEntry_poolLevel_mintWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 424419)
[PASS] test_poolEntry_poolLevel_mintWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 387681)
[PASS] test_poolEntry_poolLevel_mint_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 377466)
[PASS] test_poolEntry_poolLevel_mint_zeroPoolBitmap_zeroLenderBitmap() (gas: 340772)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 18.92ms (4.66ms CPU time)

Ran 1 test for tests/e2e/MultiLoanManager.t.sol:MultiLoanManagerTests
[PASS] test_4loans_3lps() (gas: 7533895)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 24.96ms (9.67ms CPU time)

Ran 4 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PrivatePermissionTests
[PASS] test_poolEntry_private_deposit() (gas: 353498)
[PASS] test_poolEntry_private_depositWithPermit() (gas: 399750)
[PASS] test_poolEntry_private_mint() (gas: 356976)
[PASS] test_poolEntry_private_mintWithPermit() (gas: 403930)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 15.51ms (1.29ms CPU time)

Ran 4 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PublicPermissionTests
[PASS] test_poolEntry_public_deposit() (gas: 241759)
[PASS] test_poolEntry_public_depositWithPermit() (gas: 286065)
[PASS] test_poolEntry_public_mint() (gas: 243455)
[PASS] test_poolEntry_public_mintWithPermit() (gas: 288160)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.97ms (888.63µs CPU time)

Ran 4 tests for tests/fuzz/PoolEntryPermissionsFuzz.t.sol:PoolEntryPermissionsFuzzTests
[PASS] testFuzz_poolEntryTests_deposit(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 356649, ~: 345064)
[PASS] testFuzz_poolEntryTests_depositWithPermit(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 466985, ~: 446413)
[PASS] testFuzz_poolEntryTests_mint(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 339938, ~: 331297)
[PASS] testFuzz_poolEntryTests_mintWithPermit(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 446549, ~: 416429)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 42.67ms (28.49ms CPU time)

Ran 15 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolExit_functionLevel_redeem() (gas: 631333)
[PASS] test_poolExit_functionLevel_redeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 637501)
[PASS] test_poolExit_functionLevel_redeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 608059)
[PASS] test_poolExit_functionLevel_removeShares() (gas: 510889)
[PASS] test_poolExit_functionLevel_removeShares_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 517627)
[PASS] test_poolExit_functionLevel_removeShares_zeroPoolBitmap_zeroLenderBitmap() (gas: 488220)
[PASS] test_poolExit_functionLevel_requestRedeem() (gas: 435521)
[PASS] test_poolExit_functionLevel_requestRedeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 391753)
[PASS] test_poolExit_functionLevel_requestRedeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 354972)
[PASS] test_poolExit_functionLevel_requestWithdraw() (gas: 354338)
[PASS] test_poolExit_functionLevel_requestWithdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 310420)
[PASS] test_poolExit_functionLevel_requestWithdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 273747)
[PASS] test_poolExit_functionLevel_withdraw() (gas: 261838)
[PASS] test_poolExit_functionLevel_withdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 217202)
[PASS] test_poolExit_functionLevel_withdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 180398)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 21.38ms (6.86ms CPU time)

Ran 15 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolExit_poolLevel_redeem() (gas: 595532)
[PASS] test_poolExit_poolLevel_redeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 583641)
[PASS] test_poolExit_poolLevel_redeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 554249)
[PASS] test_poolExit_poolLevel_removeShares() (gas: 474980)
[PASS] test_poolExit_poolLevel_removeShares_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 463800)
[PASS] test_poolExit_poolLevel_removeShares_zeroPoolBitmap_zeroLenderBitmap() (gas: 434409)
[PASS] test_poolExit_poolLevel_requestRedeem() (gas: 435568)
[PASS] test_poolExit_poolLevel_requestRedeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 391728)
[PASS] test_poolExit_poolLevel_requestRedeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 354969)
[PASS] test_poolExit_poolLevel_requestWithdraw() (gas: 354430)
[PASS] test_poolExit_poolLevel_requestWithdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 310459)
[PASS] test_poolExit_poolLevel_requestWithdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 273764)
[PASS] test_poolExit_poolLevel_withdraw() (gas: 261864)
[PASS] test_poolExit_poolLevel_withdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 217220)
[PASS] test_poolExit_poolLevel_withdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 180505)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 20.91ms (6.34ms CPU time)

Ran 5 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PrivatePermissionTests
[PASS] test_poolExit_private_redeem() (gas: 531281)
[PASS] test_poolExit_private_removeShares() (gas: 411456)
[PASS] test_poolExit_private_requestRedeem() (gas: 378259)
[PASS] test_poolExit_private_requestWithdraw() (gas: 296969)
[PASS] test_poolExit_private_withdraw() (gas: 203732)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 16.07ms (1.78ms CPU time)

Ran 5 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PublicPermissionTests
[PASS] test_poolExit_public_redeem() (gas: 409387)
[PASS] test_poolExit_public_removeShares() (gas: 288557)
[PASS] test_poolExit_public_requestRedeem() (gas: 252854)
[PASS] test_poolExit_public_requestWithdraw() (gas: 176141)
[PASS] test_poolExit_public_withdraw() (gas: 82167)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 15.26ms (1.11ms CPU time)

Ran 5 tests for tests/fuzz/PoolExitPermissionsFuzz.t.sol:PoolExitPermissionsFuzzTests
[PASS] testFuzz_poolExit_redeem(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 698190, ~: 586822)
[PASS] testFuzz_poolExit_removeShares(uint256,uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 558363, ~: 483463)
[PASS] testFuzz_poolExit_requestRedeem(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 554734, ~: 559852)
[PASS] testFuzz_poolExit_requestWithdraw(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 372511, ~: 354063)
[PASS] testFuzz_poolExit_withdraw(uint256,uint256,uint256,uint256,bool) (runs: 10, μ: 473754, ~: 465404)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 49.72ms (35.54ms CPU time)

Ran 1 test for tests/e2e/PoolLifecycle.t.sol:PoolLifecycleTest
[PASS] test_poolLifecycle() (gas: 11487782)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 20.61ms (7.04ms CPU time)

Ran 2 tests for tests/fuzz/OpenTermFuzz.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_otlFuzzedSetup_makePayment(uint256) (runs: 10, μ: 10187127, ~: 10233608)
[PASS] testFuzz_otlFuzzedSetup_triggerDefault(uint256) (runs: 10, μ: 10189284, ~: 10245158)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 221.90ms (206.84ms CPU time)

Ran 1 test for tests/fuzz/ClosePoolFuzz.t.sol:ClosePoolFuzzWithWMQueue
[PASS] testFuzz_fuzzedSetup_closePool_withQueueWM(uint256) (runs: 10, μ: 23478482, ~: 22087163)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 331.73ms (316.53ms CPU time)

Ran 9 tests for tests/integration/pool/ConfigurePool.t.sol:ConfigurePoolTests
[PASS] testFuzz_configurePool(uint256,uint256,uint256[]) (runs: 10, μ: 2382883, ~: 1728793)
[PASS] test_configurePool_anotherPoolDelegate() (gas: 95064)
[PASS] test_configurePool_governor() (gas: 142160)
[PASS] test_configurePool_invalidLevel() (gas: 59083)
[PASS] test_configurePool_lengthMismatch() (gas: 84743)
[PASS] test_configurePool_notAuthorized() (gas: 60554)
[PASS] test_configurePool_operationalAdmin() (gas: 146412)
[PASS] test_configurePool_poolDelegate() (gas: 139827)
[PASS] test_configurePool_publicPool() (gas: 118811)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 29.00ms (15.37ms CPU time)

Ran 11 tests for tests/e2e/PoolScenarios.t.sol:PoolScenarioTests
[PASS] testFuzz_poolScenarios_OTLWithBigPaymentInterval(uint256) (runs: 10, μ: 1055446, ~: 1055749)
[PASS] testFuzz_poolScenarios_exposeAccountedInterestDust(uint24,uint24) (runs: 10, μ: 1786032, ~: 1793456)
[PASS] testFuzz_poolScenarios_multipleOTLWithBigPaymentInterval(uint256,uint256,uint256) (runs: 10, μ: 38832341, ~: 38832455)
[PASS] test_poolScenario_fundLoanAndNeverTouchIt() (gas: 6082173)
[PASS] test_poolScenario_impairLoanWithLatePaymentAndRefinance() (gas: 2735531)
[PASS] test_poolScenario_loanWithVeryHighInterestRate() (gas: 1647792)
[PASS] test_poolScenario_loanWithZeroInterestRate() (gas: 2200572)
[PASS] test_poolScenario_loanWithZeroInterestRateAndDefaultWithCover() (gas: 1652357)
[PASS] test_poolScenarios_refinanceATwoPeriodsLateLoan() (gas: 2325808)
[PASS] test_poolScenarios_refinanceLateLoanAndDefault() (gas: 2074176)
[PASS] test_poolScenarios_stressTestAdvanceGlobalPaymentAccounting() (gas: 175879048)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 548.19ms (532.42ms CPU time)

Ran 6 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolTransfer_functionLevel_transfer() (gas: 356123)
[PASS] test_poolTransfer_functionLevel_transferFrom() (gas: 364309)
[PASS] test_poolTransfer_functionLevel_transferFrom_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 277099)
[PASS] test_poolTransfer_functionLevel_transferFrom_zeroPoolBitmap_zeroLenderBitmaps() (gas: 207556)
[PASS] test_poolTransfer_functionLevel_transfer_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 270548)
[PASS] test_poolTransfer_functionLevel_transfer_zeroPoolBitmap_zeroLenderBitmaps() (gas: 201026)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 16.41ms (1.79ms CPU time)

Ran 6 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolTransfer_poolLevel_transfer() (gas: 356235)
[PASS] test_poolTransfer_poolLevel_transferFrom() (gas: 364400)
[PASS] test_poolTransfer_poolLevel_transferFrom_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 277153)
[PASS] test_poolTransfer_poolLevel_transferFrom_zeroPoolBitmap_zeroLenderBitmaps() (gas: 207633)
[PASS] test_poolTransfer_poolLevel_transfer_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 270602)
[PASS] test_poolTransfer_poolLevel_transfer_zeroPoolBitmap_zeroLenderBitmaps() (gas: 201125)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 16.12ms (1.75ms CPU time)

Ran 2 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PrivatePermissionTests
[PASS] test_poolTransfer_private_transfer() (gas: 294697)
[PASS] test_poolTransfer_private_transferFrom() (gas: 302065)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 14.83ms (553.00µs CPU time)

Ran 2 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PublicPermissionTests
[PASS] test_poolTransfer_public_transfer() (gas: 101967)
[PASS] test_poolTransfer_public_transferFrom() (gas: 107701)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 14.48ms (145.54µs CPU time)

Ran 2 tests for tests/fuzz/PoolTransferPermissionsFuzz.t.sol:PoolTransferPermissionsFuzzTests
[PASS] testFuzz_poolTransfer(uint256,uint256,uint256,uint256,uint256,bool,bool) (runs: 10, μ: 457679, ~: 408177)
[PASS] testFuzz_poolTransferFrom(uint256,uint256,uint256,uint256,uint256,bool,bool) (runs: 10, μ: 449783, ~: 402086)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 28.14ms (13.70ms CPU time)

Ran 15 tests for tests/fuzz/PoolViewFunctionsFuzzTest.t.sol:PoolViewFunctionsFuzzTests
[PASS] testFuzz_convertToAssets_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 10, μ: 390024, ~: 389999)
[PASS] testFuzz_convertToAssets_whenTotalSupplyIsZero(uint256) (runs: 10, μ: 14526, ~: 13922)
[PASS] testFuzz_convertToExitShares(uint256,uint256,uint256,uint256,uint256) (runs: 10, μ: 421432, ~: 421281)
[PASS] testFuzz_convertToShares_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 10, μ: 388785, ~: 387879)
[PASS] testFuzz_convertToShares_whenTotalSupplyIsZero(uint256) (runs: 10, μ: 14479, ~: 13875)
[PASS] testFuzz_getTotalAssetsFromPM(uint256,uint256) (runs: 10, μ: 122326, ~: 122352)
[PASS] testFuzz_getUnrealizedLossesFromPM(uint256) (runs: 10, μ: 106740, ~: 106287)
[PASS] testFuzz_maxDeposit(uint256,uint256) (runs: 10, μ: 345563, ~: 345323)
[PASS] testFuzz_maxMint(uint256,uint256) (runs: 10, μ: 354436, ~: 354520)
[PASS] testFuzz_maxRedeem(uint256) (runs: 10, μ: 743030, ~: 742748)
[PASS] testFuzz_maxWithdraw(uint256) (runs: 10, μ: 502636, ~: 502032)
[PASS] testFuzz_previewDeposit_whenTotalSupplyExists(uint256,uint256) (runs: 10, μ: 339916, ~: 338859)
[PASS] testFuzz_previewDeposit_whenTotalSupplyIsZero(uint256) (runs: 10, μ: 15119, ~: 15447)
[PASS] testFuzz_previewMint_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 10, μ: 389519, ~: 390326)
[PASS] testFuzz_previewMint_whenTotalSupplyIsZero(uint256) (runs: 10, μ: 14522, ~: 13918)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 138.92ms (124.33ms CPU time)

Ran 1 test for tests/fuzz/ProcessExit.t.sol:ProcessExitFuzzTests
[PASS] testFuzz_processExit(address[10],bool[10],uint256[10],uint256) (runs: 10, μ: 3848128, ~: 3711870)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 57.25ms (42.69ms CPU time)

Ran 9 tests for tests/integration/withdrawal-manager/queue/ProcessRedemptions.t.sol:ProcessRedemptionsTests
[PASS] test_processRedemptions_differentExchangeRate() (gas: 1628556)
[PASS] test_processRedemptions_lowLiquidity() (gas: 1093562)
[PASS] test_processRedemptions_manualWithDifferentExchangeRates() (gas: 1381017)
[PASS] test_processRedemptions_multipleLps() (gas: 1303152)
[PASS] test_processRedemptions_multipleManualBatched() (gas: 1864163)
[PASS] test_processRedemptions_overkill() (gas: 1426714)
[PASS] test_processRedemptions_withCancelledRequest() (gas: 1225389)
[PASS] test_processRedemptions_withImpairment() (gas: 1664100)
[PASS] test_processRedemptions_zeroShares() (gas: 58238)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 29.21ms (14.03ms CPU time)

Ran 2 tests for tests/integration/syrup-router/SyrupRouterFork.t.sol:SyrupRouterForkTests
[PASS] testFork_router_deposit() (gas: 257745)
[PASS] testFork_router_depositWithPermit() (gas: 307533)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 763.19ms (2.66ms CPU time)

Ran 3 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveClaimRewardsTests
[PASS] testFork_aaveStrategy_claimRewards_paused() (gas: 63249)
[PASS] testFork_aaveStrategy_claimRewards_success() (gas: 732099)
[PASS] testFork_aaveStrategy_claimRewards_unauthorized() (gas: 72274)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 883.02ms (2.51ms CPU time)

Ran 10 tests for tests/integration/pool/Transfer.t.sol:TransferTests
[PASS] test_transferFrom_privatePoolInvalidLender() (gas: 441913)
[PASS] test_transferFrom_privatePoolInvalidLender_openPoolToPublic() (gas: 433645)
[PASS] test_transferFrom_protocolPaused() (gas: 366054)
[PASS] test_transferFrom_publicPool() (gas: 352351)
[PASS] test_transferFrom_publicPool_insufficientApproval() (gas: 358521)
[PASS] test_transferFrom_publicPool_noApproval() (gas: 333444)
[PASS] test_transfer_privatePoolInvalidLender() (gas: 426419)
[PASS] test_transfer_privatePoolInvalidLender_openPoolToPublic() (gas: 418192)
[PASS] test_transfer_protocolPaused() (gas: 338056)
[PASS] test_transfer_publicPool() (gas: 341763)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 17.14ms (3.11ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:MultiUserRedeemTests
[PASS] test_redeem_partialLiquidity_sameCash_differentExchangeRate() (gas: 2672607)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate() (gas: 2552244)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate_exposeRounding() (gas: 5022999)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 25.55ms (11.01ms CPU time)

Ran 9 tests for tests/integration/globals/TransferPoolOwnership.t.sol:TransferPoolOwnershipTests
[PASS] test_acceptPoolDelegate() (gas: 110371)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 116699)
[PASS] test_setPendingPoolDelegate_asGovernor() (gas: 73458)
[PASS] test_setPendingPoolDelegate_asOperationalAdmin() (gas: 78719)
[PASS] test_setPendingPoolDelegate_asPoolDelegate() (gas: 67926)
[PASS] test_setPendingPoolDelegate_notPD() (gas: 109725)
[PASS] test_transferOwnedPoolManager_alreadyPoolDelegate() (gas: 150557)
[PASS] test_transferOwnedPoolManager_notPoolManager() (gas: 116996)
[PASS] test_transferOwnedPoolManager_notValidPoolDelegate() (gas: 125720)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 14.95ms (662.92µs CPU time)

Ran 9 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemFailureTests
[PASS] test_redeem_failIfNoApprove() (gas: 276394)
[PASS] test_redeem_failIfNoBalanceOnWM() (gas: 392494)
[PASS] test_redeem_failIfNoRequest() (gas: 99784)
[PASS] test_redeem_failIfNotInWindow() (gas: 312723)
[PASS] test_redeem_failIfNotPool() (gas: 46447)
[PASS] test_redeem_failIfNotPoolManager() (gas: 19414)
[PASS] test_redeem_failWithInsufficientApproval() (gas: 362231)
[PASS] test_redeem_failWithInvalidAmountOfShares() (gas: 307109)
[PASS] test_redeem_failWithZeroReceiver() (gas: 338596)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 16.31ms (2.04ms CPU time)

Ran 10 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultFailureTests
[PASS] test_triggerDefault_invalidLoanManager() (gas: 5049099)
[PASS] test_triggerDefault_notAuthorized() (gas: 58539)
[PASS] test_triggerDefault_notFactory() (gas: 54400)
[PASS] test_triggerDefault_notInDefault_boundary() (gas: 603865)
[PASS] test_triggerDefault_notLoan() (gas: 93396)
[PASS] test_triggerDefault_notPM() (gas: 439866)
[PASS] test_triggerDefault_protocolPaused_loanManager() (gas: 55301)
[PASS] test_triggerDefault_protocolPaused_poolManager() (gas: 54362)
[PASS] test_triggerDefault_repossess_notLender() (gas: 40818)
[PASS] test_triggerDefault_treasuryZeroAddress() (gas: 558002)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 16.56ms (2.16ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemIntegrationTests
[PASS] test_redeem_oneLPWithImpairedLoan() (gas: 1902120)
[PASS] test_redeem_twoLPSWithImpairedLoanAndTriggerDefault() (gas: 2038785)
[PASS] test_redeem_twoLPsWithImpairedLoan() (gas: 2226812)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 20.35ms (5.88ms CPU time)

Ran 9 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultTests
[PASS] test_triggerDefault_called() (gas: 624981)
[PASS] test_triggerDefault_feesAndFullRecovery() (gas: 330425)
[PASS] test_triggerDefault_feesAndPartialRecovery() (gas: 320004)
[PASS] test_triggerDefault_impaired() (gas: 644153)
[PASS] test_triggerDefault_impaired_feesAndFullRecovery() (gas: 367637)
[PASS] test_triggerDefault_impaired_onlyFeesRecovered() (gas: 344666)
[PASS] test_triggerDefault_latePayment() (gas: 525108)
[PASS] test_triggerDefault_onlyFeesRecovered() (gas: 306945)
[PASS] test_triggerDefault_setByOperationalAdmin() (gas: 317739)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 18.82ms (4.10ms CPU time)

Ran 3 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notAuthorized() (gas: 58583)
[PASS] test_triggerDefault_notFactory() (gas: 54378)
[PASS] test_triggerDefault_notPoolManager() (gas: 57064)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 15.05ms (120.00µs CPU time)

Ran 7 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemTests
[PASS] testDeepFuzz_redeem_singleUser_fullLiquidity_oneToOne(uint256,uint256) (runs: 10, μ: 566306, ~: 565077)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem() (gas: 578516)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem_prematureRequest() (gas: 579681)
[PASS] test_redeem_singleUser_fullLiquidity_oneToOne() (gas: 574942)
[PASS] test_redeem_singleUser_noLiquidity() (gas: 1895650)
[PASS] test_redeem_singleUser_noLiquidity_notOwner() (gas: 1961002)
[PASS] test_redeem_singleUser_withApprovals() (gas: 636556)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 29.43ms (14.85ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/UnrealizedLosses.t.sol:UnrealizedLossesTests
[PASS] test_unrealizedLosses_depositWithUnrealizedLosses() (gas: 496240)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_fullLiquidity() (gas: 625751)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_partialLiquidity() (gas: 1974478)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 17.54ms (2.47ms CPU time)

Ran 4 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RequestRedeemFailureTests
[PASS] test_requestRedeem_failIfAlreadyLockedShares() (gas: 334129)
[PASS] test_requestRedeem_failIfInsufficientApproval() (gas: 162734)
[PASS] test_requestRedeem_failIfNotPM() (gas: 18962)
[PASS] test_requestRedeem_failIfNotPool() (gas: 45998)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.43ms (415.79µs CPU time)

Ran 2 tests for tests/integration/globals/Upgrade.t.sol:GlobalsUpgradeTests
[PASS] test_upgradeGlobals() (gas: 27102)
[PASS] test_upgradeGlobals_notAdmin() (gas: 31539)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 14.91ms (56.50µs CPU time)

Ran 7 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RequestRedeemTests
[PASS] testDeepFuzz_requestRedeem(uint256,uint256) (runs: 10, μ: 487757, ~: 488060)
[PASS] test_requestRedeem() (gas: 458367)
[PASS] test_requestRedeem_premature() (gas: 461079)
[PASS] test_requestRedeem_refresh() (gas: 548424)
[PASS] test_requestRedeem_refresh_notOwnerAndNoApproval() (gas: 504508)
[PASS] test_requestRedeem_refresh_notOwnerWithApproval() (gas: 582466)
[PASS] test_requestRedeem_withApproval() (gas: 478517)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 24.07ms (10.04ms CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:LiquidationUpgradeTests
[PASS] test_upgradeLiquidator_delayNotPassed() (gas: 169237)
[PASS] test_upgradeLiquidator_durationPassed() (gas: 170005)
[PASS] test_upgradeLiquidator_governor_noTimelockNeeded() (gas: 208224)
[PASS] test_upgradeLiquidator_noTimelock() (gas: 177592)
[PASS] test_upgradeLiquidator_timelockExtended() (gas: 300504)
[PASS] test_upgradeLiquidator_timelockShortened() (gas: 301316)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 16.56ms (1.02ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/queue/RedeemQueue.t.sol:ManualRedeemTests
[PASS] test_manualRedeem_fullLiquidity() (gas: 820805)
[PASS] test_manualRedeem_insufficientLiquidity() (gas: 1153400)
[PASS] test_manualRedeem_noShares() (gas: 96364)
[PASS] test_manualRedeem_partialLiquidity() (gas: 899429)
[PASS] test_manualRedeem_tooManyShares() (gas: 504841)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 18.28ms (3.78ms CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:LoanManagerUpgradeTests
[PASS] test_upgradeLoanManager_delayNotPassed() (gas: 168504)
[PASS] test_upgradeLoanManager_durationPassed() (gas: 169292)
[PASS] test_upgradeLoanManager_governor_noTimelockNeeded() (gas: 195595)
[PASS] test_upgradeLoanManager_noTimelock() (gas: 176949)
[PASS] test_upgradeLoanManager_timelockExtended() (gas: 294665)
[PASS] test_upgradeLoanManager_timelockShortened() (gas: 295410)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 15.60ms (1.16ms CPU time)

Ran 13 tests for tests/integration/loan/Refinance.t.sol:AcceptNewTermsFailureTests
[PASS] testFail_acceptNewTerms_failIfNotValidLoanManager() (gas: 79243)
[PASS] test_acceptNewTerms_failIfDeadlineExpired() (gas: 216799)
[PASS] test_acceptNewTerms_failIfInsufficientCover() (gas: 267789)
[PASS] test_acceptNewTerms_failIfLockedLiquidity() (gas: 510535)
[PASS] test_acceptNewTerms_failIfNotLender() (gas: 41948)
[PASS] test_acceptNewTerms_failIfNotPoolDelegate() (gas: 60294)
[PASS] test_acceptNewTerms_failIfProtocolIsPaused() (gas: 63910)
[PASS] test_acceptNewTerms_failIfRefinanceCallFails() (gas: 343485)
[PASS] test_acceptNewTerms_failIfRefinanceMismatch() (gas: 158974)
[PASS] test_acceptNewTerms_failWithFailedTransfer() (gas: 283283)
[PASS] test_acceptNewTerms_failWithInsufficientCollateral() (gas: 625608)
[PASS] test_acceptNewTerms_failWithInvalidRefinancer() (gas: 243454)
[PASS] test_acceptNewTerms_failWithUnexpectedFunds() (gas: 616606)
Suite result: ok. 13 passed; 0 failed; 0 skipped; finished in 17.99ms (2.66ms CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:PoolManagerUpgradeTests
[PASS] test_upgradePoolManager_delayNotPassed() (gas: 145416)
[PASS] test_upgradePoolManager_durationPassed() (gas: 146226)
[PASS] test_upgradePoolManager_governor_noTimelockNeeded() (gas: 172439)
[PASS] test_upgradePoolManager_noTimelock() (gas: 153814)
[PASS] test_upgradePoolManager_timelockExtended() (gas: 248995)
[PASS] test_upgradePoolManager_timelockShortened() (gas: 249740)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 15.09ms (1.07ms CPU time)

Ran 3 tests for tests/integration/loan/Refinance.t.sol:RefinanceOpenTermLoan
[PASS] test_refinance_calledLoan_withoutPrincipalChange() (gas: 786078)
[PASS] test_refinance_early_increasePrincipal() (gas: 783689)
[PASS] test_refinance_late_decreasePrincipal() (gas: 699052)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 18.10ms (2.72ms CPU time)

Ran 5 tests for tests/integration/loan/Refinance.t.sol:RefinanceTestsSingleLoan
[PASS] test_refinance_onLateLoan_changePaymentInterval() (gas: 1156115)
[PASS] test_refinance_onLoanPaymentDueDate_changeInterestRate() (gas: 1146809)
[PASS] test_refinance_onLoanPaymentDueDate_changePaymentInterval() (gas: 1146747)
[PASS] test_refinance_onLoanPaymentDueDate_changeToAmortized() (gas: 1149563)
[PASS] test_refinance_onLoanPaymentDueDate_increasePrincipal() (gas: 1199312)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 22.36ms (7.01ms CPU time)

Ran 3 tests for tests/e2e/RefinanceScenario.t.sol:RefinanceScenariosTests
[PASS] test_impairOTL_refinanceToHigherPrincipal_oneLoanImpaired_underflow() (gas: 1307353)
[PASS] test_impairOTL_refinanceToHigherPrincipal_twoLoansImpaired() (gas: 1492885)
[PASS] test_impairOTL_refinanceToLowerPrincipal_singleLoanImpaired() (gas: 1365352)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 19.48ms (4.91ms CPU time)

Ran 4 tests for tests/integration/globals/GetLatestPrice.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice_currentPrice() (gas: 77842)
[PASS] test_getLatestPrice_manualOverride() (gas: 48319)
[PASS] test_getLatestPrice_stalePrice() (gas: 106094)
[PASS] test_getLatestPrice_unknownAsset() (gas: 21578)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.09s (848.96µs CPU time)

Ran 8 tests for tests/integration/loan-manager/fixed-term/GetExpectedAmount.t.sol:GetExpectedAmountTests
[PASS] testFork_getExpectedAmount_currentPrice() (gas: 116426)
[PASS] testFork_getExpectedAmount_manualOverride() (gas: 90938)
[PASS] testFork_getExpectedAmount_oracleNotSet() (gas: 57989)
[PASS] testFork_getExpectedAmount_withMinRatio() (gas: 165901)
[PASS] testFork_getExpectedAmount_withSlippage() (gas: 165820)
[PASS] testFork_getExpectedAmount_withSlippageAndMinRatio_minRatioHigher() (gas: 200020)
[PASS] testFork_getExpectedAmount_withSlippageAndMinRatio_slippageHigher() (gas: 200011)
[PASS] testFork_getExpectedAmount_zeroAmount() (gas: 116411)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 1.14s (3.94ms CPU time)

Ran 1 test for tests/e2e/GlobalPermission.t.sol:GlobalPermissionTests
[PASS] test_e2e_globalPermission() (gas: 1987900)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 18.22ms (2.35ms CPU time)

Ran 1 test for tests/invariants/Regression.t.sol:WithdrawalManagerQueueInvariants
[PASS] test_regression_invariants() (gas: 53506851)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 64.42ms (48.59ms CPU time)

Ran 4 tests for tests/integration/loan-manager/open-term/RemoveCall.t.sol:RemoveCallFailureTests
[PASS] test_callPrincipal_notCalled() (gas: 81557)
[PASS] test_callPrincipal_notLender() (gas: 38246)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 51226)
[PASS] test_callPrincipal_paused() (gas: 52117)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 15.39ms (147.92µs CPU time)

Ran 3 tests for tests/integration/loan-manager/open-term/RemoveCall.t.sol:RemoveCallTests
[PASS] test_removeCall_impaired() (gas: 417937)
[PASS] test_removeCall_latePayment() (gas: 153839)
[PASS] test_removeCall_paymentOnTime() (gas: 155473)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 15.86ms (898.92µs CPU time)

Ran 9 tests for tests/integration/pool/AddStrategy.t.sol:AddStrategyTests
[PASS] test_addStrategy_invalidAsset() (gas: 252665)
[PASS] test_addStrategy_invalidFactory() (gas: 50109)
[PASS] test_addStrategy_invalidStrategy() (gas: 260844)
[PASS] test_addStrategy_multipleStrategies() (gas: 1786147)
[PASS] test_addStrategy_noExtraArguments_withPoolDelegate() (gas: 404635)
[PASS] test_addStrategy_notAuthorized() (gas: 54247)
[PASS] test_addStrategy_paused() (gas: 52916)
[PASS] test_addStrategy_withExtraArguments_withGovernor() (gas: 641222)
[PASS] test_addStrategy_withExtraArguments_withOperationalAdmin() (gas: 547092)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 1.31s (105.32ms CPU time)

Ran 5 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyDeactivateStrategyTests
[PASS] testFork_deactivateStrategy_active() (gas: 817530)
[PASS] testFork_deactivateStrategy_impaired() (gas: 838838)
[PASS] testFork_deactivateStrategy_inactive() (gas: 94975)
[PASS] testFork_deactivateStrategy_notAdmin() (gas: 137884)
[PASS] testFork_deactivateStrategy_protocolPaused() (gas: 56907)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.34s (204.32ms CPU time)

Ran 2 tests for tests/health-checkers/HealthCheckersTests.t.sol:HealthCheckerMainnetTests
[PASS] testFork_lpHealthChecker_mainnet() (gas: 1811074)
[PASS] testFork_protocolHealthChecker_mainnet() (gas: 778875)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.40s (328.78ms CPU time)

Ran 9 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveSetStrategyFeeTests
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfBiggerThanHundredPercent() (gas: 64145)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfDeactivated() (gas: 97508)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfImpaired() (gas: 97552)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 66575)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfPaused() (gas: 59485)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withGovernor_fromNonZeroToZeroFeeRate() (gas: 804183)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withGovernor_unfundedStrategy() (gas: 304467)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withOperationalAdmin_withWithdrawal() (gas: 922155)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withPoolDelegate_fundedStrategy() (gas: 712177)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 977.65ms (109.42ms CPU time)

Ran 9 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyImpairTests
[PASS] testFork_aaveStrategy_impair_failIfAlreadyImpaired() (gas: 105144)
[PASS] testFork_aaveStrategy_impair_failIfNotProtocolAdmin() (gas: 64064)
[PASS] testFork_aaveStrategy_impair_failIfPaused() (gas: 56953)
[PASS] testFork_aaveStrategy_impair_stagnant_noFees() (gas: 630933)
[PASS] testFork_aaveStrategy_impair_unfundedStrategy() (gas: 337229)
[PASS] testFork_aaveStrategy_impair_withFullLoss_strategyFees() (gas: 724917)
[PASS] testFork_aaveStrategy_impair_withGain_inactive_strategyFees() (gas: 729652)
[PASS] testFork_aaveStrategy_impair_withGain_strategyFees() (gas: 671148)
[PASS] testFork_aaveStrategy_impair_withLoss_strategyFees() (gas: 741213)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 1.46s (113.93ms CPU time)

Ran 15 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyWithdrawTests
[PASS] testFork_basicStrategy_withdraw_failIfLowAssets() (gas: 340127)
[PASS] testFork_basicStrategy_withdraw_failIfNotStrategyManager() (gas: 338459)
[PASS] testFork_basicStrategy_withdraw_failIfSlippage() (gas: 359169)
[PASS] testFork_basicStrategy_withdraw_failIfZeroAmount() (gas: 335056)
[PASS] testFork_basicStrategy_withdraw_failWhenPaused() (gas: 346403)
[PASS] testFork_basicStrategy_withdraw_failWithFullLoss() (gas: 429332)
[PASS] testFork_basicStrategy_withdraw_noFeesWithYield() (gas: 566735)
[PASS] testFork_basicStrategy_withdraw_noFeesWithYieldFullWithdrawal() (gas: 535899)
[PASS] testFork_basicStrategy_withdraw_whileDeactivated() (gas: 529152)
[PASS] testFork_basicStrategy_withdraw_whileImpaired() (gas: 579937)
[PASS] testFork_basicStrategy_withdraw_withFeesAndYield() (gas: 582995)
[PASS] testFork_basicStrategy_withdraw_withFeesAndYieldFullWithdrawal() (gas: 552207)
[PASS] testFork_basicStrategy_withdraw_withFeesRoundedToZeroAndYield() (gas: 527600)
[PASS] testFork_basicStrategy_withdraw_withLoss() (gas: 579832)
[PASS] testFork_basicStrategy_withdraw_withPoolDelegate_noFeesSameBlock() (gas: 507114)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 1.46s (217.52ms CPU time)

Ran 19 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveReactivateTests
[PASS] testFork_aaveStrategy_reactivate_failIfAlreadyActive() (gas: 129561)
[PASS] testFork_aaveStrategy_reactivate_failIfNotProtocolAdmin() (gas: 121726)
[PASS] testFork_aaveStrategy_reactivate_failIfPaused() (gas: 82760)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromImpaired_withAccountingUpdate() (gas: 627513)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromImpaired_withoutAccountingUpdate() (gas: 623345)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromInactive_withAccountingUpdate() (gas: 613616)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromInactive_withoutAccountingUpdate() (gas: 613914)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromImpaired_withAccountingUpdate() (gas: 334289)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromImpaired_withoutAccountingUpdate() (gas: 329618)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromInactive_withAccountingUpdate() (gas: 318990)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromInactive_withoutAccountingUpdate() (gas: 314407)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromImpaired_withAccountingUpdate() (gas: 653294)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromImpaired_withoutAccountingUpdate() (gas: 650208)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromInactive_withAccountingUpdate() (gas: 632583)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromInactive_withoutAccountingUpdate() (gas: 631891)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromImpaired_withAccountingUpdate() (gas: 723990)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromImpaired_withoutAccountingUpdate() (gas: 718725)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromInactive_withAccountingUpdate() (gas: 707117)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromInactive_withoutAccountingUpdate() (gas: 701765)
Suite result: ok. 19 passed; 0 failed; 0 skipped; finished in 593.06ms (230.95ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:ConvertToAssetsTests
[PASS] test_convertToAssets_multipleUsers() (gas: 498505)
[PASS] test_convertToAssets_multipleUsers_changeTotalAssets() (gas: 528156)
[PASS] test_convertToAssets_singleUser() (gas: 298058)
[PASS] test_convertToAssets_zeroTotalSupply() (gas: 12229)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 15.78ms (1.17ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositTests
[PASS] testFuzz_deposit_gtBootstrapMintAmount(uint256) (runs: 10, μ: 353129, ~: 353216)
[PASS] testFuzz_deposit_ltBootstrapMintAmount(uint256) (runs: 10, μ: 256727, ~: 256879)
[PASS] testFuzz_deposit_secondDepositorGetsCorrectShares(uint256) (runs: 10, μ: 489025, ~: 488572)
[PASS] test_deposit_exactBootstrapMintAmount() (gas: 327314)
[PASS] test_deposit_gtBootstrapMintAmount() (gas: 348055)
[PASS] test_deposit_ltBootstrapMintAmount() (gas: 251696)
[PASS] test_deposit_secondDepositorGetsCorrectShares() (gas: 484485)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 37.02ms (22.51ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:ConvertToSharesTests
[PASS] test_convertToShares_multipleUsers() (gas: 498588)
[PASS] test_convertToShares_multipleUsers_changeTotalAssets() (gas: 528238)
[PASS] test_convertToShares_singleUser() (gas: 298096)
[PASS] test_convertToShares_zeroTotalSupply() (gas: 12289)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 15.93ms (1.16ms CPU time)

Ran 3 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxDepositTests
[PASS] testDeepFuzz_maxDeposit_totalAssetsIncrease(uint256,uint256) (runs: 10, μ: 268636, ~: 268837)
[PASS] test_maxDeposit_closedPool() (gas: 289576)
[PASS] test_maxDeposit_totalAssetsIncrease() (gas: 261202)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 20.76ms (6.71ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositWithPermitTests
[PASS] testFuzz_depositWithPermit_gtBootstrapMintAmount(uint256) (runs: 10, μ: 392091, ~: 392098)
[PASS] testFuzz_depositWithPermit_ltBootstrapMintAmount(uint256) (runs: 10, μ: 252445, ~: 251846)
[PASS] testFuzz_depositWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 10, μ: 563154, ~: 563059)
[PASS] test_depositWithPermit_exactBootstrapMintAmount() (gas: 366285)
[PASS] test_depositWithPermit_gtBootstrapMintAmount() (gas: 386945)
[PASS] test_depositWithPermit_ltBootstrapMintAmount() (gas: 296344)
[PASS] test_depositWithPermit_secondDepositorGetsCorrectShares() (gas: 558350)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 47.60ms (32.35ms CPU time)

Ran 9 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyDeactivateTests
[PASS] testFork_basicStrategy_deactivate_failIfAlreadyInactive() (gas: 100296)
[PASS] testFork_basicStrategy_deactivate_failIfNotProtocolAdmin() (gas: 64022)
[PASS] testFork_basicStrategy_deactivate_failIfPaused() (gas: 56930)
[PASS] testFork_basicStrategy_deactivate_stagnant_noFees() (gas: 476119)
[PASS] testFork_basicStrategy_deactivate_unfundedStrategy() (gas: 242285)
[PASS] testFork_basicStrategy_deactivate_withFullLoss_strategyFees() (gas: 526288)
[PASS] testFork_basicStrategy_deactivate_withGain_impaired_strategyFees() (gas: 614681)
[PASS] testFork_basicStrategy_deactivate_withGain_strategyFees() (gas: 535139)
[PASS] testFork_basicStrategy_deactivate_withLoss_strategyFees() (gas: 566926)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 434.38ms (9.16ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintTests
[PASS] testFuzz_mint_gtBootstrapMintAmount(uint256) (runs: 10, μ: 356358, ~: 356509)
[PASS] testFuzz_mint_ltBootstrapMintAmount(uint256) (runs: 10, μ: 257861, ~: 257759)
[PASS] testFuzz_mint_secondDepositorGetsCorrectShares(uint256) (runs: 10, μ: 516936, ~: 517390)
[PASS] test_mint_exactBootstrapMintAmount() (gas: 330693)
[PASS] test_mint_gtBootstrapMintAmount() (gas: 351326)
[PASS] test_mint_ltBootstrapMintAmount() (gas: 253413)
[PASS] test_mint_secondDepositorGetsCorrectShares() (gas: 511813)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 37.49ms (22.80ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintWithPermitTests
[PASS] testFuzz_mintWithPermit_gtBootstrapMintAmount(uint256) (runs: 10, μ: 395774, ~: 395774)
[PASS] testFuzz_mintWithPermit_ltBootstrapMintAmount(uint256) (runs: 10, μ: 254891, ~: 255338)
[PASS] testFuzz_mintWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 10, μ: 591279, ~: 591812)
[PASS] test_mintWithPermit_exactBootstrapMintAmount() (gas: 369900)
[PASS] test_mintWithPermit_gtBootstrapMintAmount() (gas: 390582)
[PASS] test_mintWithPermit_ltBootstrapMintAmount() (gas: 298551)
[PASS] test_mintWithPermit_secondDepositorGetsCorrectShares() (gas: 586235)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 47.11ms (32.73ms CPU time)

Ran 2 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:SetBootstrapMintTests
[PASS] test_setBootstrapMint_failIfNotOperationalAdmin() (gas: 21602)
[PASS] test_setBootstrapMint_success_asOperationalAdmin() (gas: 40351)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 14.32ms (63.38µs CPU time)

Ran 9 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyDeactivateTests
[PASS] testFork_aaveStrategy_deactivate_failIfAlreadyInactive() (gas: 100251)
[PASS] testFork_aaveStrategy_deactivate_failIfNotProtocolAdmin() (gas: 63999)
[PASS] testFork_aaveStrategy_deactivate_failIfPaused() (gas: 56885)
[PASS] testFork_aaveStrategy_deactivate_stagnant_noFees() (gas: 617035)
[PASS] testFork_aaveStrategy_deactivate_unfundedStrategy() (gas: 321886)
[PASS] testFork_aaveStrategy_deactivate_withFullLoss_strategyFees() (gas: 709662)
[PASS] testFork_aaveStrategy_deactivate_withGain_impaired_strategyFees() (gas: 729675)
[PASS] testFork_aaveStrategy_deactivate_withGain_strategyFees() (gas: 652941)
[PASS] testFork_aaveStrategy_deactivate_withLoss_strategyFees() (gas: 724854)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 220.54ms (113.41ms CPU time)

Ran 12 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyWithdrawTests
[PASS] testFork_aaveStrategy_withdraw_failIfLowAssets() (gas: 103984)
[PASS] testFork_aaveStrategy_withdraw_failIfNotStrategyManager() (gas: 61775)
[PASS] testFork_aaveStrategy_withdraw_failIfZeroAmount() (gas: 62233)
[PASS] testFork_aaveStrategy_withdraw_failWhenPaused() (gas: 56785)
[PASS] testFork_aaveStrategy_withdraw_failWithFullLoss() (gas: 341982)
[PASS] testFork_aaveStrategy_withdraw_noFeesWithYield() (gas: 486275)
[PASS] testFork_aaveStrategy_withdraw_whileDeactivated() (gas: 465843)
[PASS] testFork_aaveStrategy_withdraw_whileImpaired() (gas: 505091)
[PASS] testFork_aaveStrategy_withdraw_withFeesAndYield() (gas: 533715)
[PASS] testFork_aaveStrategy_withdraw_withFeesRoundedToZeroAndYield() (gas: 461939)
[PASS] testFork_aaveStrategy_withdraw_withLoss() (gas: 526547)
[PASS] testFork_aaveStrategy_withdraw_withPoolDelegate_noFeesSameBlock() (gas: 458149)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 216.44ms (111.00ms CPU time)

Ran 2 tests for tests/fuzz/Impair.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_impair_otl(uint256) (runs: 10, μ: 11704860, ~: 11734490)
[PASS] testFuzz_removeImpairment_otl(uint256) (runs: 10, μ: 10821449, ~: 10710497)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 223.62ms (208.02ms CPU time)

Ran 14 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyFundTests
[PASS] testFork_aaveStrategy_fund_failIfInvalidAaveToken() (gas: 91369)
[PASS] testFork_aaveStrategy_fund_failIfInvalidStrategyFactory() (gas: 153792)
[PASS] testFork_aaveStrategy_fund_failIfNotEnoughPoolLiquidity() (gas: 197366)
[PASS] testFork_aaveStrategy_fund_failIfNotStrategyManager() (gas: 61754)
[PASS] testFork_aaveStrategy_fund_failIfZeroAmount() (gas: 134742)
[PASS] testFork_aaveStrategy_fund_failWhenDeactivated() (gas: 103559)
[PASS] testFork_aaveStrategy_fund_failWhenImpaired() (gas: 103668)
[PASS] testFork_aaveStrategy_fund_failWhenPaused() (gas: 56720)
[PASS] testFork_aaveStrategy_fund_secondTimeWithFeesAndYield() (gas: 775659)
[PASS] testFork_aaveStrategy_fund_secondTimeWithFeesRoundedToZeroAndYield() (gas: 693032)
[PASS] testFork_aaveStrategy_fund_secondTimeWithLoss() (gas: 770288)
[PASS] testFork_aaveStrategy_fund_secondTimeWithNoFeesAndYield() (gas: 721532)
[PASS] testFork_aaveStrategy_fund_withPoolDelegate() (gas: 570983)
[PASS] testFork_aaveStrategy_fund_withStrategyManager() (gas: 575243)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 150.62ms (116.94ms CPU time)

Ran 4 tests for tests/integration/loan/AcceptLoanTerms.t.sol:AcceptLoanTermsFTLTests
[PASS] test_acceptLoanTerms_FTL_failIfAlreadyAccepted() (gas: 70097)
[PASS] test_acceptLoanTerms_FTL_failIfNotBorrower() (gas: 37867)
[PASS] test_acceptLoanTerms_FTL_failIfPaused() (gas: 52165)
[PASS] test_acceptLoanTerms_FTL_success() (gas: 66504)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.82ms (135.33µs CPU time)

Ran 3 tests for tests/protocol-upgrade/AddStrategy.t.sol:AddStrategyToSyrupUSDCTests
[PASS] test_addStrategy_syrupUSDC_aaveStrategy() (gas: 955192)
[PASS] test_addStrategy_syrupUSDC_doubleAaveStrategy() (gas: 1635542)
[PASS] test_addStrategy_syrupUSDC_skyStrategy() (gas: 1205478)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 347.91ms (16.84ms CPU time)

Ran 4 tests for tests/integration/loan/AcceptLoanTerms.t.sol:AcceptLoanTermsOTLTests
[PASS] test_acceptLoanTerms_OTL_failIfAlreadyAccepted() (gas: 70319)
[PASS] test_acceptLoanTerms_OTL_failIfNotBorrower() (gas: 37825)
[PASS] test_acceptLoanTerms_OTL_failIfPaused() (gas: 52232)
[PASS] test_acceptLoanTerms_OTL_success() (gas: 66622)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.42ms (135.29µs CPU time)

Ran 2 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:AutomatedPreviewRedeemWithQueueWMTests
[PASS] testFuzz_previewRedeem_notProcessed(uint256) (runs: 10, μ: 36941, ~: 36941)
[PASS] testFuzz_previewRedeem_processed(uint256) (runs: 10, μ: 306306, ~: 306306)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 26.22ms (11.70ms CPU time)

Ran 1 test for tests/integration/loan-manager/fixed-term/BasicInterestAccrual.t.sol:BasicInterestAccrualTest
[PASS] test_basicInterestAccrual() (gas: 2451763)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 16.63ms (2.40ms CPU time)

Ran 3 tests for tests/integration/globals/ActivatePoolManager.t.sol:ActivatePoolManagerFailureTests
[PASS] test_activatePoolManager_failIfNotGlobals() (gas: 37024)
[PASS] test_activatePoolManager_failIfNotGovernor() (gas: 21395)
[PASS] test_activatePoolManager_failIfProtocolIsPaused() (gas: 70714)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 13.81ms (103.29µs CPU time)

Ran 2 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:BalanceOfAssetsTests
[PASS] testDeepFuzz_balanceOfAssets(uint256,uint256,uint256) (runs: 10, μ: 453452, ~: 453352)
[PASS] test_balanceOfAssets() (gas: 441960)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 23.65ms (8.93ms CPU time)

Ran 20 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolTests
[PASS] test_deployPool_failIfCalledPMFactoryDirectly() (gas: 33430)
[PASS] test_deployPool_failIfCalledWMFactoryDirectly() (gas: 35778)
[PASS] test_deployPool_failWithAssetNotAllowed() (gas: 331771)
[PASS] test_deployPool_failWithInsufficientPDApproval() (gas: 5918560)
[PASS] test_deployPool_failWithInvalidAsset() (gas: 430091)
[PASS] test_deployPool_failWithInvalidLMFactory() (gas: 5260259)
[PASS] test_deployPool_failWithInvalidManagementFee() (gas: 5917709)
[PASS] test_deployPool_failWithInvalidPD() (gas: 59892)
[PASS] test_deployPool_failWithInvalidPMFactory() (gas: 77496)
[PASS] test_deployPool_failWithInvalidStart() (gas: 5133389)
[PASS] test_deployPool_failWithInvalidWMCyclicalFactory() (gas: 82289)
[PASS] test_deployPool_failWithNonZeroSupplyAndZeroMigrationAdmin() (gas: 415957)
[PASS] test_deployPool_failWithOwnedPoolManager() (gas: 6298009)
[PASS] test_deployPool_failWithWindowDurationGtCycleDuration() (gas: 5133274)
[PASS] test_deployPool_failWithZeroAsset() (gas: 290774)
[PASS] test_deployPool_failWithZeroWindowDuration() (gas: 5133226)
[PASS] test_deployPool_success() (gas: 6221302)
[PASS] test_deployPool_successWithInitialSupply() (gas: 6161077)
[PASS] test_deployPool_successWithZeroMigrationAdmin() (gas: 6120595)
[PASS] test_deployPool_success_validPDSetByOA() (gas: 6154486)
Suite result: ok. 20 passed; 0 failed; 0 skipped; finished in 21.46ms (8.17ms CPU time)

Ran 2 tests for tests/integration/globals/ActivatePoolManager.t.sol:ActivatePoolManagerTests
[PASS] test_activatePoolManager() (gas: 82189)
[PASS] test_activatePoolManager_asOperationalAdmin() (gas: 96516)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 13.83ms (145.75µs CPU time)

Ran 12 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolWMQueueFailureTests
[PASS] test_deployPoolWMQueue_failIfAlreadyOwned() (gas: 6386003)
[PASS] test_deployPoolWMQueue_failIfInsufficientAmount() (gas: 6057376)
[PASS] test_deployPoolWMQueue_failIfInsufficientApproval() (gas: 6057374)
[PASS] test_deployPoolWMQueue_failIfInvalidManagementFeeRate() (gas: 5982549)
[PASS] test_deployPoolWMQueue_failIfInvalidPD() (gas: 56235)
[PASS] test_deployPoolWMQueue_failIfInvalidPMFactory() (gas: 6155202)
[PASS] test_deployPoolWMQueue_failIfInvalidPPM() (gas: 6164742)
[PASS] test_deployPoolWMQueue_failIfInvalidPoolAsset() (gas: 714465)
[PASS] test_deployPoolWMQueue_failIfInvalidWMFactory() (gas: 6159995)
[PASS] test_deployPoolWMQueue_failIfInvalidWMQFactory() (gas: 75700)
[PASS] test_deployPoolWMQueue_failIfPoolAssetNotAllowed() (gas: 328092)
[PASS] test_deployPoolWMQueue_failIfSaltCollision() (gas: 17595493375392614270)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 20.26ms (6.94ms CPU time)

Ran 35 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyFundStrategyTests
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_allFees() (gas: 1183671)
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_noFees() (gas: 1083465)
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_psmFees() (gas: 1166088)
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_strategyFees() (gas: 1141110)
[PASS] testFork_fundStrategy_fundAfterGain_allFees() (gas: 1300712)
[PASS] testFork_fundStrategy_fundAfterGain_allFees_withStrategyFeesRoundedToZero() (gas: 1146233)
[PASS] testFork_fundStrategy_fundAfterGain_noFees() (gas: 1044801)
[PASS] testFork_fundStrategy_fundAfterGain_psmFees() (gas: 1127660)
[PASS] testFork_fundStrategy_fundAfterGain_strategyFees() (gas: 1257754)
[PASS] testFork_fundStrategy_fundAfterGain_strategyFeesRoundedToZero() (gas: 1103456)
[PASS] testFork_fundStrategy_fundAfterLoss_allFees() (gas: 1170813)
[PASS] testFork_fundStrategy_fundAfterLoss_noFees() (gas: 1068300)
[PASS] testFork_fundStrategy_fundAfterLoss_psmFees() (gas: 1151192)
[PASS] testFork_fundStrategy_fundAfterLoss_strategyFees() (gas: 1125980)
[PASS] testFork_fundStrategy_fundWhenStagnant_allFees() (gas: 1095891)
[PASS] testFork_fundStrategy_fundWhenStagnant_noFees() (gas: 992540)
[PASS] testFork_fundStrategy_fundWhenStagnant_psmFees() (gas: 1075284)
[PASS] testFork_fundStrategy_fundWhenStagnant_strategyFees() (gas: 1050203)
[PASS] testFork_fundStrategy_initialFund_allFees() (gas: 901195)
[PASS] testFork_fundStrategy_initialFund_noFees() (gas: 845728)
[PASS] testFork_fundStrategy_initialFund_psmFees() (gas: 879241)
[PASS] testFork_fundStrategy_initialFund_strategyFees() (gas: 852658)
[PASS] testFork_fundStrategy_insufficientCover() (gas: 480503)
[PASS] testFork_fundStrategy_insufficientLiquidity() (gas: 463945)
[PASS] testFork_fundStrategy_invalidPsm() (gas: 94026)
[PASS] testFork_fundStrategy_invalidStrategyFactory() (gas: 159542)
[PASS] testFork_fundStrategy_invalidVault() (gas: 89212)
[PASS] testFork_fundStrategy_notPoolDelegate() (gas: 764053)
[PASS] testFork_fundStrategy_notStrategyManager() (gas: 770124)
[PASS] testFork_fundStrategy_protocolPaused() (gas: 59441)
[PASS] testFork_fundStrategy_psmHalted() (gas: 212)
[PASS] testFork_fundStrategy_strategyImpaired() (gas: 103646)
[PASS] testFork_fundStrategy_strategyInactive() (gas: 103536)
[PASS] testFork_fundStrategy_zeroPrincipal() (gas: 140490)
[PASS] testFork_fundStrategy_zeroSupply() (gas: 158691)
Suite result: ok. 35 passed; 0 failed; 0 skipped; finished in 309.75ms (197.24ms CPU time)

Ran 2 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolWMQueueTests
[PASS] test_deployPoolWMQueue_success() (gas: 6233227)
[PASS] test_deployPoolWMQueue_withoutCoverAmount() (gas: 6115553)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 14.93ms (1.70ms CPU time)

Ran 1 test for tests/fuzz/Deposit.t.sol:DepositFuzzTests
[PASS] testDeepFuzz_deposit_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 10, μ: 462920, ~: 482555)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 28.15ms (13.57ms CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:DepositFailureTests
[PASS] test_deposit_insufficientApproval() (gas: 343747)
[PASS] test_deposit_liquidityCapExceeded() (gas: 457496)
[PASS] test_deposit_privatePoolInvalidRecipient() (gas: 409713)
[PASS] test_deposit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 380965)
[PASS] test_deposit_protocolPaused() (gas: 105534)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 15.76ms (1.20ms CPU time)

Ran 77 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyWithdrawFromStrategyTests
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterGain_fullWithdrawal() (gas: 1270596)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterGain_partialWithdrawal() (gas: 1263627)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterLoss_fullWithdrawal() (gas: 1155829)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterLoss_partialWithdrawal() (gas: 1167318)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_whenStagnant_fullWithdrawal() (gas: 1071552)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_whenStagnant_partialWithdrawal() (gas: 1087622)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterGain_fullWithdrawal() (gas: 1034901)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterGain_partialWithdrawal() (gas: 1027193)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterLoss_fullWithdrawal() (gas: 1058359)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterLoss_partialWithdrawal() (gas: 1050721)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_whenStagnant_fullWithdrawal() (gas: 975142)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_whenStagnant_partialWithdrawal() (gas: 971020)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterGain_fullWithdrawal() (gas: 1113356)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterGain_partialWithdrawal() (gas: 1115876)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterLoss_fullWithdrawal() (gas: 1136888)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterLoss_partialWithdrawal() (gas: 1145219)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_whenStagnant_fullWithdrawal() (gas: 1053491)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_whenStagnant_partialWithdrawal() (gas: 1065436)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterGain_fullWithdrawal() (gas: 1231886)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterGain_partialWithdrawal() (gas: 1224059)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterLoss_fullWithdrawal() (gas: 1116104)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterLoss_partialWithdrawal() (gas: 1118100)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_whenStagnant_fullWithdrawal() (gas: 1032936)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_whenStagnant_partialWithdrawal() (gas: 1038417)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterGain_fullWithdrawal() (gas: 1166478)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterGain_partialWithdrawal() (gas: 1162741)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterLoss_fullWithdrawal() (gas: 1195401)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterLoss_partialWithdrawal() (gas: 1191565)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_whenStagnant_fullWithdrawal() (gas: 1120742)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_whenStagnant_partialWithdrawal() (gas: 1121390)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterGain_fullWithdrawal() (gas: 1055443)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterGain_partialWithdrawal() (gas: 1051484)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterLoss_fullWithdrawal() (gas: 1081288)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterLoss_partialWithdrawal() (gas: 1076348)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_whenStagnant_fullWithdrawal() (gas: 1006729)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_whenStagnant_partialWithdrawal() (gas: 1006317)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterGain_fullWithdrawal() (gas: 1143838)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterGain_partialWithdrawal() (gas: 1140015)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterLoss_fullWithdrawal() (gas: 1173278)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterLoss_partialWithdrawal() (gas: 1169488)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_whenStagnant_fullWithdrawal() (gas: 1098710)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_whenStagnant_partialWithdrawal() (gas: 1099246)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterGain_fullWithdrawal() (gas: 1117853)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterGain_partialWithdrawal() (gas: 1112925)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterLoss_fullWithdrawal() (gas: 1146601)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterLoss_partialWithdrawal() (gas: 1141794)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_whenStagnant_fullWithdrawal() (gas: 1072129)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_whenStagnant_partialWithdrawal() (gas: 1071697)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterGain_fullWithdrawal() (gas: 1118575)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterGain_partialWithdrawal() (gas: 1112548)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterLoss_fullWithdrawal() (gas: 1147366)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterLoss_partialWithdrawal() (gas: 1141372)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_whenStagnant_fullWithdrawal() (gas: 1072761)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_whenStagnant_partialWithdrawal() (gas: 1071782)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterGain_fullWithdrawal() (gas: 1017759)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterGain_partialWithdrawal() (gas: 1012748)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterLoss_fullWithdrawal() (gas: 1041276)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterLoss_partialWithdrawal() (gas: 1036271)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_whenStagnant_fullWithdrawal() (gas: 965760)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_whenStagnant_partialWithdrawal() (gas: 964795)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterGain_fullWithdrawal() (gas: 1095869)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterGain_partialWithdrawal() (gas: 1089931)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterLoss_fullWithdrawal() (gas: 1125355)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterLoss_partialWithdrawal() (gas: 1119336)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_whenStagnant_fullWithdrawal() (gas: 1050617)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_whenStagnant_partialWithdrawal() (gas: 1049702)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterGain_fullWithdrawal() (gas: 1072696)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterGain_partialWithdrawal() (gas: 1067722)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterLoss_fullWithdrawal() (gas: 1099494)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterLoss_partialWithdrawal() (gas: 1093370)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_whenStagnant_fullWithdrawal() (gas: 1025045)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_whenStagnant_partialWithdrawal() (gas: 1023748)
[PASS] testFork_withdrawFromStrategy_lowAssets() (gas: 752018)
[PASS] testFork_withdrawFromStrategy_notPoolDelegate() (gas: 892067)
[PASS] testFork_withdrawFromStrategy_notStrategyManager() (gas: 898504)
[PASS] testFork_withdrawFromStrategy_protocolPaused() (gas: 59550)
[PASS] testFork_withdrawFromStrategy_zeroAssets() (gas: 62483)
Suite result: ok. 77 passed; 0 failed; 0 skipped; finished in 784.13ms (572.37ms CPU time)

Ran 4 tests for tests/integration/pool/DepositAndMint.t.sol:DepositTest
[PASS] testDeepFuzz_deposit_singleUser(uint256) (runs: 10, μ: 312482, ~: 312482)
[PASS] testDeepFuzz_deposit_variableExchangeRate(uint256,uint256) (runs: 10, μ: 1625739, ~: 1626193)
[PASS] test_deposit_singleUser_oneToOne() (gas: 308230)
[PASS] test_deposit_twoUsers_oneToOne() (gas: 437343)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 36.19ms (22.17ms CPU time)

Ran 6 tests for tests/integration/globals/OperationalAdmin.t.sol:OperationalAdminTests
[PASS] test_operationalAdminAcl_setMinCoverAmount() (gas: 50431)
[PASS] test_operationalAdminAcl_setPermissionAdmin() (gas: 68654)
[PASS] test_operationalAdminAcl_setPlatformManagementFeeRate() (gas: 52914)
[PASS] test_operationalAdminAcl_setPlatformOriginationFeeRate() (gas: 52933)
[PASS] test_operationalAdminAcl_setPlatformServiceFeeRate() (gas: 52912)
[PASS] test_operationalAdminAcl_setValidInstanceOf() (gas: 51996)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 13.65ms (194.62µs CPU time)

Ran 2 tests for tests/fuzz/Call.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_call_otl(uint256) (runs: 10, μ: 11611486, ~: 11699963)
[PASS] testFuzz_removeCall_otl(uint256) (runs: 10, μ: 10853265, ~: 10771950)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 222.93ms (207.78ms CPU time)

Ran 5 tests for tests/integration/loan/open-term/CallPrincipal.t.sol:CallPrincipalFailureTests
[PASS] test_callPrincipal_invalidAmount_boundary() (gas: 524661)
[PASS] test_callPrincipal_loanActive() (gas: 56542)
[PASS] test_callPrincipal_notLender() (gas: 38705)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 51544)
[PASS] test_callPrincipal_paused() (gas: 52435)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 15.17ms (579.00µs CPU time)

Ran 4 tests for tests/integration/loan/open-term/CallPrincipal.t.sol:CallPrincipalTests
[PASS] test_callPrincipal_impaired() (gas: 445126)
[PASS] test_callPrincipal_latePayment() (gas: 183216)
[PASS] test_callPrincipal_notFullPrincipal() (gas: 183094)
[PASS] test_callPrincipal_paymentOnTime() (gas: 182777)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 16.12ms (1.12ms CPU time)

Ran 5 tests for tests/integration/loan/fixed-term/CloseLoan.t.sol:CloseLoanTests
[PASS] test_closeLoan_failIfLoanIsLate() (gas: 112892)
[PASS] test_closeLoan_failIfNotEnoughFundsSent() (gas: 214434)
[PASS] test_closeLoan_failIfNotLoan() (gas: 66913)
[PASS] test_closeLoan_failWithInsufficientApproval() (gas: 123864)
[PASS] test_closeLoan_success() (gas: 500012)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 15.73ms (851.21µs CPU time)

Ran 5 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyImpairStrategyTests
[PASS] testFork_impairStrategy_active() (gas: 841319)
[PASS] testFork_impairStrategy_impaired() (gas: 98594)
[PASS] testFork_impairStrategy_inactive() (gas: 838840)
[PASS] testFork_impairStrategy_notAdmin() (gas: 138015)
[PASS] testFork_impairStrategy_protocolPaused() (gas: 56995)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 189.79ms (7.27ms CPU time)

Ran 16 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyFundTests
[PASS] testFork_basicStrategy_fund_failIfInvalidStrategyFactory() (gas: 142576)
[PASS] testFork_basicStrategy_fund_failIfInvalidStrategyVault() (gas: 87371)
[PASS] testFork_basicStrategy_fund_failIfNotEnoughPoolLiquidity() (gas: 174550)
[PASS] testFork_basicStrategy_fund_failIfNotEnoughSharesOut() (gas: 332820)
[PASS] testFork_basicStrategy_fund_failIfNotStrategyManager() (gas: 62091)
[PASS] testFork_basicStrategy_fund_failIfZeroAmount() (gas: 123591)
[PASS] testFork_basicStrategy_fund_failWhenDeactivated() (gas: 103959)
[PASS] testFork_basicStrategy_fund_failWhenImpaired() (gas: 103938)
[PASS] testFork_basicStrategy_fund_failWhenPaused() (gas: 57034)
[PASS] testFork_basicStrategy_fund_firstFundWithPoolDelegate() (gas: 434627)
[PASS] testFork_basicStrategy_fund_firstFundWithStrategyManager() (gas: 443731)
[PASS] testFork_basicStrategy_fund_secondFundAfterTotalLoss_withStrategyFees() (gas: 579858)
[PASS] testFork_basicStrategy_fund_secondFundWithGain_noStrategyFees() (gas: 592893)
[PASS] testFork_basicStrategy_fund_secondFundWithGain_withFeesRoundedToZero() (gas: 555230)
[PASS] testFork_basicStrategy_fund_secondFundWithGain_withStrategyFees() (gas: 608482)
[PASS] testFork_basicStrategy_fund_secondFundWithLoss_withStrategyFees() (gas: 609119)
Suite result: ok. 16 passed; 0 failed; 0 skipped; finished in 386.81ms (15.60ms CPU time)

Ran 4 tests for tests/integration/globals/Pause.t.sol:PauseTests
[PASS] test_contractPause() (gas: 5704617)
[PASS] test_functionUnpauseAfterContractPause() (gas: 48050836)
[PASS] test_functionUnpauseAfterProtocolPause() (gas: 47212119)
[PASS] test_globalPause() (gas: 8772652)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 143.18ms (126.86ms CPU time)

Ran 19 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicReactivateTests
[PASS] testFork_basicStrategy_reactivate_failIfAlreadyActive() (gas: 129562)
[PASS] testFork_basicStrategy_reactivate_failIfNotProtocolAdmin() (gas: 121702)
[PASS] testFork_basicStrategy_reactivate_failIfPaused() (gas: 82716)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromImpaired_withAccountingUpdate() (gas: 474607)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromImpaired_withoutAccountingUpdate() (gas: 481952)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromInactive_withAccountingUpdate() (gas: 471840)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromInactive_withoutAccountingUpdate() (gas: 472647)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromImpaired_withAccountingUpdate() (gas: 262155)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromImpaired_withoutAccountingUpdate() (gas: 255600)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromInactive_withAccountingUpdate() (gas: 241184)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromInactive_withoutAccountingUpdate() (gas: 234699)
[PASS] testFork_basicStrategy_reactivate_withGain_fromImpaired_withAccountingUpdate() (gas: 550229)
[PASS] testFork_basicStrategy_reactivate_withGain_fromImpaired_withoutAccountingUpdate() (gas: 542629)
[PASS] testFork_basicStrategy_reactivate_withGain_fromInactive_withAccountingUpdate() (gas: 515681)
[PASS] testFork_basicStrategy_reactivate_withGain_fromInactive_withoutAccountingUpdate() (gas: 510520)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromImpaired_withAccountingUpdate() (gas: 587908)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromImpaired_withoutAccountingUpdate() (gas: 578379)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromInactive_withAccountingUpdate() (gas: 557985)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromInactive_withoutAccountingUpdate() (gas: 548746)
Suite result: ok. 19 passed; 0 failed; 0 skipped; finished in 331.35ms (123.90ms CPU time)

Ran 23 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyReactivateStrategyTests
[PASS] testFork_reactivateStrategy_active() (gas: 66130)
[PASS] testFork_reactivateStrategy_impaired_flat_keepAccounting() (gas: 666864)
[PASS] testFork_reactivateStrategy_impaired_flat_updateAccounting() (gas: 674125)
[PASS] testFork_reactivateStrategy_impaired_gain_keepAccounting() (gas: 716931)
[PASS] testFork_reactivateStrategy_impaired_gain_updateAccounting() (gas: 727580)
[PASS] testFork_reactivateStrategy_impaired_loss_keepAccounting() (gas: 739757)
[PASS] testFork_reactivateStrategy_impaired_loss_updateAccounting() (gas: 751978)
[PASS] testFork_reactivateStrategy_impaired_new_keepAccounting() (gas: 307281)
[PASS] testFork_reactivateStrategy_impaired_new_updateAccounting() (gas: 317145)
[PASS] testFork_reactivateStrategy_impaired_totalLoss_keepAccounting() (gas: 703756)
[PASS] testFork_reactivateStrategy_impaired_totalLoss_updateAccounting() (gas: 704447)
[PASS] testFork_reactivateStrategy_inactive_flat_keepAccounting() (gas: 642773)
[PASS] testFork_reactivateStrategy_inactive_flat_updateAccounting() (gas: 649968)
[PASS] testFork_reactivateStrategy_inactive_gain_keepAccounting() (gas: 675444)
[PASS] testFork_reactivateStrategy_inactive_gain_updateAccounting() (gas: 686067)
[PASS] testFork_reactivateStrategy_inactive_loss_keepAccounting() (gas: 700699)
[PASS] testFork_reactivateStrategy_inactive_loss_updateAccounting() (gas: 712897)
[PASS] testFork_reactivateStrategy_inactive_new_keepAccounting() (gas: 276234)
[PASS] testFork_reactivateStrategy_inactive_new_updateAccounting() (gas: 285985)
[PASS] testFork_reactivateStrategy_inactive_totalLoss_keepAccounting() (gas: 666016)
[PASS] testFork_reactivateStrategy_inactive_totalLoss_updateAccounting() (gas: 674272)
[PASS] testFork_reactivateStrategy_notAdmin() (gas: 95268)
[PASS] testFork_reactivateStrategy_protocolPaused() (gas: 57352)
Suite result: ok. 23 passed; 0 failed; 0 skipped; finished in 406.23ms (141.59ms CPU time)

Ran 2 tests for tests/integration/smart-accounts/SmartAccount.t.sol:SmartAccountETHTests
[PASS] testFork_deposit_predeterminedAddressApproval() (gas: 1223200)
[PASS] testFork_withdraw() (gas: 1475943)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 326.69ms (3.50ms CPU time)

Ran 1 test for tests/fuzz/ClosePoolFuzz.t.sol:ClosePoolFuzz
[PASS] testFuzz_fuzzedSetup_closePool(uint256) (runs: 10, μ: 20019314, ~: 20239452)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 289.65ms (274.27ms CPU time)

Ran 16 tests for tests/e2e/DelayedWithdrawal.t.sol:DelayedWithdrawalStartTests
[PASS] testFuzz_removeShares_afterStart(uint256) (runs: 10, μ: 6859371, ~: 6859522)
[PASS] testFuzz_removeShares_beforeStart(uint256) (runs: 10, μ: 6916381, ~: 6916407)
[PASS] testFuzz_removeShares_nextCycle(uint256) (runs: 10, μ: 6859455, ~: 6859568)
[PASS] testFuzz_removeShares_onStart(uint256) (runs: 10, μ: 6887419, ~: 6887444)
[PASS] testFuzz_requestRedeem_afterStart(uint256) (runs: 10, μ: 6864088, ~: 6864239)
[PASS] testFuzz_requestRedeem_beforeStart(uint256) (runs: 10, μ: 6924055, ~: 6924055)
[PASS] testFuzz_requestRedeem_nextCycle(uint256) (runs: 10, μ: 6864217, ~: 6864304)
[PASS] testFuzz_requestRedeem_onStart(uint256) (runs: 10, μ: 6893580, ~: 6893606)
[PASS] testFuzz_requestWithdraw_afterStart(uint256) (runs: 10, μ: 6742462, ~: 6742462)
[PASS] testFuzz_requestWithdraw_beforeStart(uint256) (runs: 10, μ: 6742456, ~: 6742456)
[PASS] testFuzz_requestWithdraw_nextCycle(uint256) (runs: 10, μ: 6742420, ~: 6742507)
[PASS] testFuzz_requestWithdraw_onStart(uint256) (runs: 10, μ: 6742182, ~: 6742357)
[PASS] testFuzz_setExitConfig_afterStart(uint256) (runs: 10, μ: 6736477, ~: 6736528)
[PASS] testFuzz_setExitConfig_beforeStart(uint256) (runs: 10, μ: 6735893, ~: 6735944)
[PASS] testFuzz_setExitConfig_nextCycle(uint256) (runs: 10, μ: 6736222, ~: 6736548)
[PASS] testFuzz_setExitConfig_onStart(uint256) (runs: 10, μ: 6735801, ~: 6735802)
Suite result: ok. 16 passed; 0 failed; 0 skipped; finished in 284.82ms (271.33ms CPU time)

Ran 1 test for tests/integration/loan/fixed-term/DeployLoan.t.sol:DeployFixedTermLoanTests
[PASS] test_deployFixedTermLoan_feeManagerCheck() (gas: 918780)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 14.66ms (391.96µs CPU time)

Ran 9 tests for tests/integration/loan/DeployLoanByBorrower.t.sol:DeployLoanByBorrowerTests
[PASS] test_deployLoan_FTL_invalidBorrower() (gas: 688561)
[PASS] test_deployLoan_FTL_invalidInstance() (gas: 688289)
[PASS] test_deployLoan_FTL_setCanDeployFromByOA() (gas: 70432)
[PASS] test_deployLoan_FTL_success() (gas: 664788)
[PASS] test_deployLoan_FTL_validBorrowerSetByOA() (gas: 692653)
[PASS] test_deployLoan_FTL_validInstanceSetByOA() (gas: 690647)
[PASS] test_deployLoan_OTL_invalidBorrower() (gas: 528224)
[PASS] test_deployLoan_OTL_invalidInstance() (gas: 528018)
[PASS] test_deployLoan_OTL_success() (gas: 509318)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 15.92ms (1.95ms CPU time)

Ran 9 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyImpairTests
[PASS] testFork_basicStrategy_impair_failIfAlreadyImpaired() (gas: 105101)
[PASS] testFork_basicStrategy_impair_failIfNotProtocolAdmin() (gas: 64064)
[PASS] testFork_basicStrategy_impair_failIfPaused() (gas: 56907)
[PASS] testFork_basicStrategy_impair_stagnant_noFees() (gas: 489541)
[PASS] testFork_basicStrategy_impair_unfundedStrategy() (gas: 263277)
[PASS] testFork_basicStrategy_impair_withFullLoss_strategyFees() (gas: 554613)
[PASS] testFork_basicStrategy_impair_withGain_inactive_strategyFees() (gas: 614369)
[PASS] testFork_basicStrategy_impair_withGain_strategyFees() (gas: 567247)
[PASS] testFork_basicStrategy_impair_withLoss_strategyFees() (gas: 597118)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 399.47ms (9.66ms CPU time)

Ran 8 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategySetPSMTests
[PASS] testFork_setPsm_failIfNotValidInstance() (gas: 85367)
[PASS] testFork_setPsm_fundedStrategy() (gas: 836947)
[PASS] testFork_setPsm_invalidGem() (gas: 457467)
[PASS] testFork_setPsm_invalidUsds() (gas: 483879)
[PASS] testFork_setPsm_notAdmin() (gas: 340016)
[PASS] testFork_setPsm_protocolPaused() (gas: 59571)
[PASS] testFork_setPsm_unfundedStrategy() (gas: 183709)
[PASS] testFork_setPsm_zeroAddress() (gas: 56476)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 274.16ms (6.75ms CPU time)

Ran 3 tests for tests/invariants/OpenTermInvariants.t.sol:OpenTermInvariants
[PASS] statefulFuzz_openTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_openTermLoanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_openTermLoan_A_B_C_D_E_F_G_H_I_openTermLoanManager_A_B_C_D_F_H_I_J_K() (runs: 10, calls: 1000, reverts: 0)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.88s (1.86s CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawFailureTests
[PASS] testDeepFuzz_withdraw(uint256,address,address) (runs: 10, μ: 77799, ~: 77799)
[PASS] test_withdraw_failIfNotPool() (gas: 46470)
[PASS] test_withdraw_failIfNotPoolManager() (gas: 19457)
[PASS] test_withdraw_premature() (gas: 82213)
[PASS] test_withdraw_zeroAssetInput() (gas: 79434)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 19.83ms (5.34ms CPU time)

Ran 1 test for tests/fuzz/Withdraw.t.sol:WithdrawFuzzTests
[PASS] testDeepFuzz_withdraw_all(address,address,address,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 10, μ: 473137, ~: 507701)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 28.13ms (12.61ms CPU time)

Ran 1 test for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawOnPermissionedPool
[PASS] test_withdraw_withUnwhitelistedUser() (gas: 504130)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 14.72ms (466.13µs CPU time)

Ran 3 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawScenarios
[PASS] test_withdrawals_cashInjection() (gas: 5114517)
[PASS] test_withdrawals_poorExchangeRates() (gas: 4800849)
[PASS] test_withdrawals_withUpdateAccounting() (gas: 4803330)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 28.61ms (14.56ms CPU time)

Ran 3 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:RequestWithdrawFailureTests
[PASS] test_requestWithdraw_failIfInsufficientApproval() (gas: 296431)
[PASS] test_requestWithdraw_failIfNotPM() (gas: 18940)
[PASS] test_requestWithdraw_failIfNotPool() (gas: 45930)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 14.44ms (268.63µs CPU time)

Ran 4 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:RequestWithdrawTests
[PASS] testDeepFuzz_requestWithdraw(uint256,uint256) (runs: 10, μ: 385139, ~: 385165)
[PASS] test_requestWithdraw() (gas: 356904)
[PASS] test_requestWithdraw_premature() (gas: 359684)
[PASS] test_requestWithdraw_withApproval() (gas: 371689)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 21.78ms (7.81ms CPU time)

Ran 7 tests for tests/e2e/WithdrawManagerScenario.t.sol:WithdrawalManagerScenarioTests
[PASS] test_scenario_fundPayAndRefinanceLoanWithPartialRedemptions_removeSharesAndCloseLoan() (gas: 3815539)
[PASS] test_scenario_impairLoanAndRedeem_defaultLoanAndWithdraw() (gas: 2644280)
[PASS] test_scenario_impairLoanAndRedeem_removeImpairAndRedeem() (gas: 2872044)
[PASS] test_scenario_impairLoanAndRedeem_removeSharesRepayLoanAndRedeem() (gas: 2645520)
[PASS] test_scenario_impairLoanAndRedeem_repayLoanAndWithdraw() (gas: 2746787)
[PASS] test_scenario_impairLoanAndRedeem_startLiquidationAndRedeem_finishLiquidationAndRedeem() (gas: 4084214)
[PASS] test_scenario_multipleUsers_impairLoanAndRedeem_repayLoanAndRedeem() (gas: 22429930)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 71.08ms (54.54ms CPU time)

Ran 9 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicSetStrategyFeeTests
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfBiggerThanHundredPercent() (gas: 66333)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfDeactivated() (gas: 97594)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfImpaired() (gas: 97573)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 66597)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfPaused() (gas: 59505)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withGovernor_fromNonZeroToZeroFeeRate() (gas: 651788)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withGovernor_unfundedStrategy() (gas: 235786)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withOperationalAdmin_withWithdrawal() (gas: 770550)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withPoolDelegate_fundedStrategy() (gas: 591336)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 458.54ms (175.70ms CPU time)

Ran 11 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategySetStrategyFeeTests
[PASS] testFork_setStrategyFeeRate_deactivated() (gas: 97508)
[PASS] testFork_setStrategyFeeRate_impaired() (gas: 97597)
[PASS] testFork_setStrategyFeeRate_initialFeeRate_flat() (gas: 350692)
[PASS] testFork_setStrategyFeeRate_initialFeeRate_gain() (gas: 463507)
[PASS] testFork_setStrategyFeeRate_initialFeeRate_loss() (gas: 425880)
[PASS] testFork_setStrategyFeeRate_invalidFeeRate() (gas: 64188)
[PASS] testFork_setStrategyFeeRate_notAdmin() (gas: 244109)
[PASS] testFork_setStrategyFeeRate_protocolPaused() (gas: 59485)
[PASS] testFork_setStrategyFeeRate_updatedFeeRate_flat() (gas: 352870)
[PASS] testFork_setStrategyFeeRate_updatedFeeRate_gain() (gas: 688017)
[PASS] testFork_setStrategyFeeRate_updatedFeeRate_loss() (gas: 428015)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 470.27ms (16.98ms CPU time)

Ran 1 test for tests/invariants/PermissionInvariants.t.sol:PermissionInvariants
[PASS] statefulFuzz_permissionManager_A_B_C() (runs: 10, calls: 1000, reverts: 0)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.76s (1.74s CPU time)

Ran 9 tests for tests/integration/syrup-router/SyrupRouter.t.sol:SyrupRouterAuthorizeAndDepositTests
[PASS] test_authorizeAndDepositWithPermit_expiredDeadline() (gas: 24548)
[PASS] test_authorizeAndDepositWithPermit_malleable() (gas: 21376)
[PASS] test_authorizeAndDepositWithPermit_repeatedNonce() (gas: 388358)
[PASS] test_authorizeAndDepositWithPermit_success() (gas: 387138)
[PASS] test_authorizeAndDeposit_expiredDeadline() (gas: 23453)
[PASS] test_authorizeAndDeposit_malleable() (gas: 20301)
[PASS] test_authorizeAndDeposit_notPermissionAdmin() (gas: 101347)
[PASS] test_authorizeAndDeposit_repeatedNonce() (gas: 360074)
[PASS] test_authorizeAndDeposit_success() (gas: 361925)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 17.11ms (2.40ms CPU time)

Ran 50 tests for tests/integration/syrup-router/SyrupRouter.t.sol:SyrupRouterDepositsIntegrationTests
[PASS] test_depositWithPermit_functionLevel_allowListed() (gas: 509317)
[PASS] test_depositWithPermit_functionLevel_expiredDeadline() (gas: 224621)
[PASS] test_depositWithPermit_functionLevel_insufficientPermission() (gas: 279613)
[PASS] test_depositWithPermit_functionLevel_invalidSignature() (gas: 251400)
[PASS] test_depositWithPermit_functionLevel_sufficientPermission() (gas: 509972)
[PASS] test_depositWithPermit_functionLevel_zeroBitmap() (gas: 259735)
[PASS] test_depositWithPermit_functionLevel_zeroShares() (gas: 321219)
[PASS] test_depositWithPermit_poolLevel_allowListed() (gas: 507235)
[PASS] test_depositWithPermit_poolLevel_expiredDeadline() (gas: 222607)
[PASS] test_depositWithPermit_poolLevel_insufficientPermission() (gas: 277569)
[PASS] test_depositWithPermit_poolLevel_invalidSignature() (gas: 249408)
[PASS] test_depositWithPermit_poolLevel_sufficientPermission() (gas: 506028)
[PASS] test_depositWithPermit_poolLevel_zeroBitmap() (gas: 257713)
[PASS] test_depositWithPermit_poolLevel_zeroShares() (gas: 319194)
[PASS] test_depositWithPermit_private_allowListed() (gas: 416099)
[PASS] test_depositWithPermit_private_expiredDeadline() (gas: 127345)
[PASS] test_depositWithPermit_private_invalidSignature() (gas: 154081)
[PASS] test_depositWithPermit_private_unauthorized() (gas: 112998)
[PASS] test_depositWithPermit_private_zeroShares() (gas: 229809)
[PASS] test_depositWithPermit_public_expiredDeadline() (gas: 185069)
[PASS] test_depositWithPermit_public_invalidSignature() (gas: 211936)
[PASS] test_depositWithPermit_public_success() (gas: 405066)
[PASS] test_depositWithPermit_public_zeroShares() (gas: 282991)
[PASS] test_deposit_functionLevel_allowlisted() (gas: 481122)
[PASS] test_deposit_functionLevel_approval() (gas: 464534)
[PASS] test_deposit_functionLevel_infiniteApproval() (gas: 481884)
[PASS] test_deposit_functionLevel_insufficientAmount() (gas: 306090)
[PASS] test_deposit_functionLevel_insufficientApproval() (gas: 303383)
[PASS] test_deposit_functionLevel_insufficientPermission() (gas: 195811)
[PASS] test_deposit_functionLevel_zeroBitmap() (gas: 175931)
[PASS] test_deposit_functionLevel_zeroShares() (gas: 294045)
[PASS] test_deposit_poolLevel_allowlisted() (gas: 479148)
[PASS] test_deposit_poolLevel_approval() (gas: 460545)
[PASS] test_deposit_poolLevel_infiniteApproval() (gas: 477876)
[PASS] test_deposit_poolLevel_insufficientAmount() (gas: 304001)
[PASS] test_deposit_poolLevel_insufficientApproval() (gas: 301315)
[PASS] test_deposit_poolLevel_insufficientPermission() (gas: 193740)
[PASS] test_deposit_poolLevel_zeroBitmap() (gas: 173843)
[PASS] test_deposit_poolLevel_zeroShares() (gas: 292018)
[PASS] test_deposit_private_approval() (gas: 370661)
[PASS] test_deposit_private_infiniteApproval() (gas: 388038)
[PASS] test_deposit_private_insufficientAmount() (gas: 208181)
[PASS] test_deposit_private_insufficientApproval() (gas: 205495)
[PASS] test_deposit_private_unauthorized() (gas: 29162)
[PASS] test_deposit_private_zeroShares() (gas: 202679)
[PASS] test_deposit_public_approval() (gas: 359606)
[PASS] test_deposit_public_infiniteApproval() (gas: 376938)
[PASS] test_deposit_public_insufficientAmount() (gas: 200154)
[PASS] test_deposit_public_insufficientApproval() (gas: 197402)
[PASS] test_deposit_public_zeroShares() (gas: 192348)
Suite result: ok. 50 passed; 0 failed; 0 skipped; finished in 27.29ms (13.01ms CPU time)

Ran 4 tests for tests/e2e/StrategyScenarios.t.sol:StrategyScenarios
[PASS] testFork_strategy_scenario1() (gas: 2243011)
[PASS] testFork_strategy_scenario2() (gas: 2187360)
[PASS] testFork_strategy_scenario3() (gas: 2003424)
[PASS] testFork_strategy_scenario4() (gas: 2110739)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 454.53ms (61.52ms CPU time)

Ran 30 tests for tests/invariants/BasicInvariants.t.sol:BasicInvariants
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoan_A_B_C_fixedTermLoanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_poolManager_A_totalAssetsEqCashPlusAUM() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_poolManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_B_F_G_2() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_M() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_N() (runs: 10, calls: 1000, reverts: 0)
Suite result: ok. 30 passed; 0 failed; 0 skipped; finished in 9.04s (26.84s CPU time)

Ran 25 tests for tests/invariants/WithdrawalManagerQueueInvariants.t.sol:WithdrawalManagerQueueInvariants
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoan_A_B_C_fixedTermLoanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_poolManager_A_totalAssetsEqCashPlusAUM() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_poolManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_B_F_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_wmq_invariant_A_C_G_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_wmq_invariant_B_D_E_F_I() (runs: 10, calls: 1000, reverts: 0)
Suite result: ok. 25 passed; 0 failed; 0 skipped; finished in 6.70s (21.12s CPU time)

Ran 27 tests for tests/invariants/DefaultsInvariants.t.sol:DefaultsInvariants
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoan_A_B_fixedTermLoanManager_M_N_Default() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_poolManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_poolManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_B_F_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_M() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_N() (runs: 10, calls: 1000, reverts: 0)
Suite result: ok. 27 passed; 0 failed; 0 skipped; finished in 15.65s (25.90s CPU time)

Ran 27 tests for tests/invariants/ImpairInvariants.t.sol:ImpairInvariants
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoan_A_B_fixedTermLoanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_poolManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_poolManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_B_F_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_M() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_N() (runs: 10, calls: 1000, reverts: 0)
Suite result: ok. 27 passed; 0 failed; 0 skipped; finished in 16.19s (23.76s CPU time)

Ran 1 test for tests/protocol-upgrade/ValidationLifecycle.t.sol:ValidationLifecycleETH
[PASS] testFork_validationLifecycle_syrupUsdc(uint256) (runs: 10, μ: 13185253, ~: 13418635)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 131.25s (130.18s CPU time)

Ran 1 test for tests/invariants/StrategyInvariants.t.sol:StrategyInvariants
[PASS] statefulFuzz_strategy_A_B_C_D_E_F_G() (runs: 10, calls: 1000, reverts: 0)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 200.50s (200.07s CPU time)

Ran 182 test suites in 202.65s (406.95s CPU time): 1273 tests passed, 0 failed, 0 skipped (1273 total tests)

```

# `erc20 (v1.0.1)`

```
Running 1 test for contracts/test/ERC20.t.sol:ERC20Invariants
[PASS] invariant_balanceSum() (runs: 256, calls: 3840, reverts: 2333)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 396.50ms

Running 14 tests for contracts/test/ERC20.t.sol:ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 85428, ~: 86353)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 257338, ~: 257338)
[PASS] test_domainSeparator() (gas: 8326)
[PASS] test_initialState() (gas: 15788)
[PASS] test_permit_badS() (gas: 31538)
[PASS] test_permit_badV() (gas: 1041107)
[PASS] test_permit_differentSpender() (gas: 58233)
[PASS] test_permit_differentVerifier() (gas: 701463)
[PASS] test_permit_earlyNonce() (gas: 58301)
[PASS] test_permit_ownerSignerMismatch() (gas: 58300)
[PASS] test_permit_replay() (gas: 90422)
[PASS] test_permit_withExpiry() (gas: 94098)
[PASS] test_permit_zeroAddress() (gas: 58231)
[PASS] test_typehash() (gas: 5566)
Test result: ok. 14 passed; 0 failed; 0 skipped; finished in 1.20s

Running 14 tests for contracts/test/ERC20.t.sol:ERC20BaseTest
[PASS] invariant_metadata() (runs: 256, calls: 3840, reverts: 2435)
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 30547, ~: 31714)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 27308, ~: 419)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 35441, ~: 35448)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 36203, ~: 38339)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 38280, ~: 38358)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 759454, ~: 758616)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 52751, ~: 54306)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 60629, ~: 61407)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 346253, ~: 354380)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 350682, ~: 355204)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 341883, ~: 341400)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 324292, ~: 323048)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 333330, ~: 333331)
Test result: ok. 14 passed; 0 failed; 0 skipped; finished in 1.60s
```

# `fixed-term-loan (v6.0.0)`

```
Ran 3 tests for tests/MapleLoan.t.sol:MapleLoanRoleTests
[PASS] test_transferBorrowerRole() (gas: 198634)
[PASS] test_transferBorrowerRole_failIfInvalidBorrower() (gas: 80422)
[PASS] test_transferLenderRole() (gas: 315711)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.37ms (371.00µs CPU time)

Ran 4 tests for tests/MapleLoanFeeManager.t.sol:PayOriginationFeesTests
[PASS] test_payOriginationFees() (gas: 330532)
[PASS] test_payOriginationFees_insufficientFunds_poolDelegate() (gas: 184926)
[PASS] test_payOriginationFees_insufficientFunds_treasury() (gas: 216842)
[PASS] test_payOriginationFees_zeroTreasury() (gas: 217392)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.64ms (522.13µs CPU time)

Ran 2 tests for tests/MapleLoanFeeManager.t.sol:GetterTests
[PASS] test_getDelegateServiceFeesForPeriod() (gas: 717302)
[PASS] test_getPlatformServiceFeeForPeriod() (gas: 1059351)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.75ms (782.17µs CPU time)

Ran 2 tests for tests/InitializerAndMigrator.t.sol:MapleLoanInitializerAndMigratorTests
[PASS] test_initializer_setters() (gas: 97720)
[PASS] test_migration_ratesChange() (gas: 116214)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.57ms (205.67µs CPU time)

Ran 1 test for tests/MapleLoanFeeManager.t.sol:PayClosingFeesTests
[PASS] test_payClosingServiceFees() (gas: 276208)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.43ms (199.38µs CPU time)

Ran 1 test for tests/MapleLoanRefinancer.t.sol:MapleLoanRefinancerMiscellaneousTests
[PASS] test_refinance_invalidRefinancer() (gas: 9107038)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 2.59ms (2.08ms CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_SkimTests
[PASS] test_skimCollateralAsset() (gas: 84661)
[PASS] test_skimFundsAsset() (gas: 84683)
[PASS] test_skim_otherAsset() (gas: 1367889)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.36ms (2.23ms CPU time)

Ran 2 tests for tests/MapleLoanFeeManager.t.sol:PayServiceFeesTests
[PASS] test_payServiceFees() (gas: 275511)
[PASS] test_payServiceFees_zeroTreasury() (gas: 233683)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.53ms (373.21µs CPU time)

Ran 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RepossessTests
[PASS] test_repossess() (gas: 151946)
[PASS] test_repossess_beforePaymentDue() (gas: 57119)
[PASS] test_repossess_collateralTransferFailed() (gas: 310751)
[PASS] test_repossess_fundsTransferFailed() (gas: 343461)
[PASS] test_repossess_onGracePeriod() (gas: 57135)
[PASS] test_repossess_onPaymentDue() (gas: 56881)
[PASS] test_repossess_withinGracePeriod() (gas: 57090)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.02ms (304.87µs CPU time)

Ran 1 test for tests/MapleLoanFeeManager.t.sol:UpdatePlatformServiceFeeTests
[PASS] test_updatePlatformServiceFee() (gas: 1848583)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.52ms (753.75µs CPU time)

Ran 1 test for tests/MapleLoanFeeManager.t.sol:UpdateDelegateFeeTermsTests
[PASS] test_updateDelegateFeeTerms() (gas: 109727)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 767.13µs (35.83µs CPU time)

Ran 4 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_AcceptLoanTerms
[PASS] test_acceptLoanTerms_failIfAlreadyAccepted() (gas: 53497)
[PASS] test_acceptLoanTerms_failIfNotBorrower() (gas: 27116)
[PASS] test_acceptLoanTerms_failIfPaused() (gas: 34044)
[PASS] test_acceptLoanTerms_success() (gas: 56654)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 921.46µs (102.00µs CPU time)

Ran 2 tests for tests/Payments.t.sol:FullyAmortizedPaymentsTests
[PASS] test_payments_fullyAmortized_case1() (gas: 1690148)
[PASS] test_payments_fullyAmortized_case2() (gas: 1690096)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 4.75ms (3.89ms CPU time)

Ran 5 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RejectNewTermsTests
[PASS] test_rejectNewTerms() (gas: 65176)
[PASS] test_rejectNewTerms_commitmentMismatch_emptyCallsArray() (gas: 75608)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedCalls() (gas: 77220)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 77134)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 729528)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 738.92µs (336.25µs CPU time)

Ran 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_AcceptNewTermsTests
[PASS] test_acceptNewTerms() (gas: 173153)
[PASS] test_acceptNewTerms_afterDeadline() (gas: 85327)
[PASS] test_acceptNewTerms_callFailed() (gas: 126231)
[PASS] test_acceptNewTerms_commitmentMismatch_emptyCallsArray() (gas: 80633)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedCalls() (gas: 82174)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 81977)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 81692)
[PASS] test_acceptNewTerms_insufficientCollateral() (gas: 349754)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 82166)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 1.70ms (814.63µs CPU time)

Ran 73 tests for tests/MapleLoan.t.sol:MapleLoanTests
[PASS] test_acceptBorrower_acl() (gas: 54137)
[PASS] test_acceptBorrower_failWhenPaused() (gas: 31258)
[PASS] test_acceptLender_acl() (gas: 52388)
[PASS] test_acceptLender_failWhenPaused() (gas: 31323)
[PASS] test_acceptNewTerms() (gas: 1615390)
[PASS] test_acceptNewTerms_acl() (gas: 1565477)
[PASS] test_acceptNewTerms_failWhenPaused() (gas: 33117)
[PASS] test_closeLoan_failWhenPaused() (gas: 32269)
[PASS] test_closeLoan_pullPatternAsBorrower() (gas: 1536652)
[PASS] test_closeLoan_pullPatternAsNonBorrower() (gas: 1539286)
[PASS] test_closeLoan_pullPatternUsingDrawable() (gas: 1552401)
[PASS] test_closeLoan_pushPatternAsBorrower() (gas: 1554197)
[PASS] test_closeLoan_pushPatternAsNonBorrower() (gas: 1554809)
[PASS] test_closeLoan_pushPatternUsingDrawable() (gas: 1519677)
[PASS] test_drawdownFunds_acl() (gas: 1478653)
[PASS] test_drawdownFunds_failWhenPaused() (gas: 32528)
[PASS] test_drawdownFunds_pullPatternForCollateral() (gas: 2937722)
[PASS] test_drawdownFunds_pushPatternForCollateral() (gas: 2916511)
[PASS] test_drawdownFunds_withoutAdditionalCollateralRequired() (gas: 2748726)
[PASS] test_excessCollateral_varyCollateral() (gas: 147809)
[PASS] test_excessCollateral_varyDrawableFunds() (gas: 131698)
[PASS] test_excessCollateral_varyPrincipal() (gas: 94632)
[PASS] test_fundLoan_failWhenPaused() (gas: 31552)
[PASS] test_fundLoan_pushPattern() (gas: 1660577)
[PASS] test_getAdditionalCollateralRequiredFor_varyAmount() (gas: 134543)
[PASS] test_getAdditionalCollateralRequiredFor_varyCollateralRequired() (gas: 118891)
[PASS] test_getAdditionalCollateralRequiredFor_varyDrawableFunds() (gas: 121492)
[PASS] test_getAdditionalCollateralRequiredFor_varyPrincipal() (gas: 142671)
[PASS] test_impairLoan() (gas: 82018)
[PASS] test_impairLoan_acl() (gas: 94698)
[PASS] test_impairLoan_failWhenPaused() (gas: 31297)
[PASS] test_impairLoan_lateLoan() (gas: 82161)
[PASS] test_makePayment_failWhenPaused() (gas: 32380)
[PASS] test_makePayment_pullPatternAsBorrower() (gas: 1599245)
[PASS] test_makePayment_pullPatternAsNonBorrower() (gas: 1601542)
[PASS] test_makePayment_pullPatternUsingDrawable() (gas: 1643797)
[PASS] test_makePayment_pushPatternAsBorrower() (gas: 1605305)
[PASS] test_makePayment_pushPatternAsNonBorrower() (gas: 1605578)
[PASS] test_makePayment_pushPatternUsingDrawable() (gas: 1611113)
[PASS] test_migrate_acl() (gas: 92884)
[PASS] test_migrate_failWhenPaused() (gas: 32454)
[PASS] test_postCollateral_failWhenPaused() (gas: 32008)
[PASS] test_postCollateral_pullPattern() (gas: 1450394)
[PASS] test_postCollateral_pushPattern() (gas: 1400032)
[PASS] test_proposeNewTerms() (gas: 111580)
[PASS] test_proposeNewTerms_acl() (gas: 132458)
[PASS] test_proposeNewTerms_failWhenPaused() (gas: 33053)
[PASS] test_proposeNewTerms_invalidDeadline() (gas: 132539)
[PASS] test_rejectNewTerms_acl() (gas: 142208)
[PASS] test_rejectNewTerms_failWhenPaused() (gas: 33073)
[PASS] test_removeCollateral_acl() (gas: 1437036)
[PASS] test_removeCollateral_failWhenPaused() (gas: 32189)
[PASS] test_removeLoanImpairment_acl() (gas: 75791)
[PASS] test_removeLoanImpairment_failWhenPaused() (gas: 31343)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 32254)
[PASS] test_removeLoanImpairment_pastDate() (gas: 54501)
[PASS] test_removeLoanImpairment_success() (gas: 61130)
[PASS] test_repossess_acl() (gas: 1418220)
[PASS] test_repossess_failWhenPaused() (gas: 32303)
[PASS] test_returnFunds_failWhenPaused() (gas: 32030)
[PASS] test_returnFunds_pullPattern() (gas: 1450525)
[PASS] test_returnFunds_pushPattern() (gas: 1400099)
[PASS] test_setImplementation_acl() (gas: 112908)
[PASS] test_setImplementation_failWhenPaused() (gas: 31787)
[PASS] test_setPendingBorrower_acl() (gas: 97821)
[PASS] test_setPendingBorrower_failWhenPaused() (gas: 31744)
[PASS] test_setPendingLender_acl() (gas: 73701)
[PASS] test_setPendingLender_failWhenPaused() (gas: 31833)
[PASS] test_skim_failWhenPaused() (gas: 32387)
[PASS] test_upgrade_acl_noAuth() (gas: 6512769)
[PASS] test_upgrade_acl_noAuth_asBorrower() (gas: 6515603)
[PASS] test_upgrade_acl_securityAdmin() (gas: 6547416)
[PASS] test_upgrade_failWhenPaused() (gas: 32122)
Suite result: ok. 73 passed; 0 failed; 0 skipped; finished in 7.60ms (6.64ms CPU time)

Ran 2 tests for tests/Payments.t.sol:InterestOnlyPaymentsTests
[PASS] test_payments_interestOnly_case1() (gas: 1705772)
[PASS] test_payments_interestOnly_case2() (gas: 1706026)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 4.70ms (3.90ms CPU time)

Ran 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceInterestTests
[PASS] test_acceptNewTerms_makePayment_withRefinanceInterest() (gas: 9368283)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.26ms (813.58µs CPU time)

Ran 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ScaledExponentTests
[PASS] test_scaledExponent_setOne() (gas: 40312)
[PASS] test_scaledExponent_setTwo() (gas: 71120)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 529.54µs (244.21µs CPU time)

Ran 3 tests for tests/MapleLoanScenarios.t.sol:MapleLoanScenariosTests
[PASS] test_scenario_fullyAmortized() (gas: 9469479)
[PASS] test_scenario_interestOnly() (gas: 9454263)
[PASS] test_scenario_lateLoanRefinanceInterest() (gas: 9142220)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 11.69ms (12.00ms CPU time)

Ran 3 tests for tests/MapleLoanV502Migrator.t.sol:MapleLoanV502MigratorTests
[PASS] test_migration_factoryChange() (gas: 2982041)
[PASS] test_migration_invalidFactory() (gas: 2957110)
[PASS] test_migration_sameFactory_noOp() (gas: 2947582)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 9.88ms (8.67ms CPU time)

Ran 2 tests for tests/Payments.t.sol:ClosingTests
[PASS] test_payments_closing_flatRate_case1() (gas: 1422444)
[PASS] test_payments_closing_flatRate_case2() (gas: 1277184)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.18ms (2.38ms CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CollateralMaintainedTests
[PASS] test_isCollateralMaintained(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 124987, ~: 125743)
[PASS] test_isCollateralMaintained_edgeCases() (gas: 194733)
[PASS] test_isCollateralMaintained_roundUp() (gas: 85461)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 16.75ms (16.35ms CPU time)

Ran 5 tests for tests/Payments.t.sol:LateRepaymentsTests
[PASS] test_payments_dailyInterestAccrual() (gas: 1067368)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case1() (gas: 1695184)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case2() (gas: 1704151)
[PASS] test_payments_lateRepayment_flatRate_case1() (gas: 1696567)
[PASS] test_payments_lateRepayment_flatRate_case2() (gas: 1692239)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 8.63ms (7.79ms CPU time)

Ran 2 tests for tests/Payments.t.sol:PartiallyAmortizedPaymentsTests
[PASS] test_payments_partiallyAmortized_case1() (gas: 1706000)
[PASS] test_payments_partiallyAmortized_case2() (gas: 1706034)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 4.59ms (3.83ms CPU time)

Ran 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ReturnFundsTests
[PASS] test_returnFunds(uint256) (runs: 257, μ: 129656, ~: 130551)
[PASS] test_returnFundsCollateralAsset() (gas: 1389958)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 35.82ms (35.50ms CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ProposeNewTermsTests
[PASS] test_proposeNewTerms(address,uint256,uint256,uint256,uint256) (runs: 257, μ: 81620, ~: 81985)
[PASS] test_proposeNewTerms_emptyArray(address,uint256) (runs: 257, μ: 38505, ~: 38867)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 83503)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 46.94ms (46.41ms CPU time)

Ran 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetNextPaymentBreakdownTests
[PASS] test_getNextPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 719732, ~: 720824)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 37.33ms (37.03ms CPU time)

Ran 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPaymentBreakdownTests
[PASS] test_getPaymentBreakdown_onePaymentFourPeriodsLate() (gas: 38327)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodBeforeDue() (gas: 35252)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodLate() (gas: 38349)
[PASS] test_getPaymentBreakdown_onePaymentOneSecondBeforeDue() (gas: 35317)
[PASS] test_getPaymentBreakdown_onePaymentThreePeriodsLate() (gas: 38282)
[PASS] test_getPaymentBreakdown_onePaymentTwoPeriodsLate() (gas: 38304)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 574.63µs (282.09µs CPU time)

Ran 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPeriodicInterestRateTests
[PASS] test_getPeriodicInterestRate() (gas: 10439)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 286.88µs (19.71µs CPU time)

Ran 10 tests for tests/MapleLoanFactory.t.sol:MapleLoanFactoryTest
[PASS] testFail_createInstance_saltAndArgumentsCollision() (gas: 1040446479)
[PASS] test_createInstance(bytes32) (runs: 257, μ: 553134, ~: 553134)
[PASS] test_createInstance_differentFundsAsset() (gas: 774574)
[PASS] test_createInstance_invalidCaller() (gas: 553933)
[PASS] test_createInstance_invalidCollateralAsset() (gas: 746625)
[PASS] test_createInstance_invalidFactory() (gas: 778503)
[PASS] test_createInstance_invalidInstance() (gas: 784465)
[PASS] test_createInstance_invalidPoolAsset() (gas: 742867)
[PASS] test_createInstance_zeroLender() (gas: 770310)
[PASS] test_isLoan_withOldFactory() (gas: 1087316)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 84.51ms (86.71ms CPU time)

Ran 11 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RemoveCollateralTests
[PASS] test_removeCollateral_cannotRemoveAnyAmountWithEncumbrances() (gas: 200417)
[PASS] test_removeCollateral_cannotRemoveFullAmountWithEncumbrances(uint256) (runs: 257, μ: 160966, ~: 160957)
[PASS] test_removeCollateral_cannotRemovePartialAmountWithEncumbrances(uint256,uint256) (runs: 257, μ: 201850, ~: 201451)
[PASS] test_removeCollateral_fullAmountWithNoEncumbrances(uint256) (runs: 257, μ: 125155, ~: 125140)
[PASS] test_removeCollateral_fullAmount_drawableFundsGtPrincipal(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 191023, ~: 191908)
[PASS] test_removeCollateral_fullAmount_noPrincipal(uint256) (runs: 257, μ: 144424, ~: 144403)
[PASS] test_removeCollateral_insufficientCollateralWithNoEncumbrances(uint256) (runs: 257, μ: 120683, ~: 121606)
[PASS] test_removeCollateral_partialAmountWithEncumbrances(uint256,uint256) (runs: 257, μ: 250075, ~: 251071)
[PASS] test_removeCollateral_partialAmountWithNoEncumbrances(uint256,uint256) (runs: 257, μ: 162616, ~: 163251)
[PASS] test_removeCollateral_sameAssetAsFundingAsset(uint256) (runs: 257, μ: 149046, ~: 149025)
[PASS] test_removeCollateral_transferFailed() (gas: 295961)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 84.91ms (199.25ms CPU time)

Ran 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_InitializeTests
[PASS] test_initialize() (gas: 8918344)
[PASS] test_initialize_invalidBorrower() (gas: 2103808)
[PASS] test_initialize_invalidEndingPrincipal() (gas: 2066954)
[PASS] test_initialize_invalidGracePeriodBoundary() (gas: 10900817)
[PASS] test_initialize_invalidOriginationFeeBoundary() (gas: 10901776)
[PASS] test_initialize_invalidPaymentInterval() (gas: 2073499)
[PASS] test_initialize_invalidPaymentsRemaining() (gas: 2073489)
[PASS] test_initialize_invalidPrincipal() (gas: 2066748)
[PASS] test_initialize_zeroBorrower() (gas: 2077540)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 3.35ms (2.86ms CPU time)

Ran 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_DrawdownFundsTests
[PASS] test_drawdownFunds_collateralNotMaintained(uint256,uint256,uint256) (runs: 257, μ: 270646, ~: 273959)
[PASS] test_drawdownFunds_insufficientDrawableFunds(uint256,uint256) (runs: 257, μ: 157611, ~: 157778)
[PASS] test_drawdownFunds_multipleDrawdowns(uint256,uint256,uint256) (runs: 257, μ: 278545, ~: 278207)
[PASS] test_drawdownFunds_postedCollateral(uint256,uint256,uint256) (runs: 257, μ: 292739, ~: 294748)
[PASS] test_drawdownFunds_transferFailed() (gas: 55640)
[PASS] test_drawdownFunds_withoutPostedCollateral(uint256,uint256) (runs: 257, μ: 198238, ~: 199184)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 157.55ms (157.05ms CPU time)

Ran 12 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetUnaccountedAmountTests
[PASS] test_getUnaccountedAmount_collateral(uint256,uint256) (runs: 257, μ: 90938, ~: 91305)
[PASS] test_getUnaccountedAmount_collateralAsset() (gas: 81295)
[PASS] test_getUnaccountedAmount_complex(uint256,uint256,uint256) (runs: 257, μ: 1391805, ~: 1392099)
[PASS] test_getUnaccountedAmount_drawableFunds(uint256,uint256) (runs: 257, μ: 90817, ~: 91174)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral(uint256,uint256,uint256,uint256) (runs: 257, μ: 172927, ~: 172822)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral_fundsAssetEqCollateralAsset(uint256,uint256,uint256) (runs: 257, μ: 119959, ~: 120134)
[PASS] test_getUnaccountedAmount_fundsAsset() (gas: 81296)
[PASS] test_getUnaccountedAmount_newFundsLtCollateral(uint256) (runs: 257, μ: 108943, ~: 108937)
[PASS] test_getUnaccountedAmount_newFundsLtDrawableFunds(uint256) (runs: 257, μ: 108973, ~: 108967)
[PASS] test_getUnaccountedAmount_randomToken() (gas: 121430)
[PASS] test_getUnaccountedAmount_withCollateral(uint256,uint256) (runs: 257, μ: 89717, ~: 89934)
[PASS] test_getUnaccountedAmount_withDrawableFunds(uint256,uint256) (runs: 257, μ: 88950, ~: 89805)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 131.51ms (131.04ms CPU time)

Ran 4 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_PostCollateralTests
[PASS] test_postCollateral_invalidCollateralAsset() (gas: 1363482)
[PASS] test_postCollateral_multiple(uint256,uint256) (runs: 257, μ: 181880, ~: 182453)
[PASS] test_postCollateral_once(uint256) (runs: 257, μ: 103614, ~: 105228)
[PASS] test_postCollateral_withUnaccountedFundsAsset() (gas: 1452457)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 56.76ms (56.46ms CPU time)

Ran 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceInterestRateTests
[PASS] test_refinance_interestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9309324, ~: 9310564)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 219.07ms (217.97ms CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePaymentIntervalTests
[PASS] test_refinance_paymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9310166, ~: 9311571)
[PASS] test_refinance_paymentInterval_zeroAmount() (gas: 9259105)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 220.10ms (220.27ms CPU time)

Ran 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceGracePeriodTests
[PASS] test_refinance_gracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9308080, ~: 9310244)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 220.49ms (219.11ms CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePaymentsRemainingTests
[PASS] test_refinance_paymentRemaining(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9310325, ~: 9312060)
[PASS] test_refinance_paymentRemaining_zeroAmount() (gas: 9259107)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 209.00ms (209.35ms CPU time)

Ran 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceCollateralRequiredTests
[PASS] test_refinance_collateralRequired(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9350901, ~: 9351232)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 255.71ms (255.11ms CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInstallmentTests
[PASS] test_getInstallment_edgeCases() (gas: 28426)
[PASS] test_getInstallment_genericFuzzing(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 18957, ~: 19197)
[PASS] test_getInstallment_withFixtures() (gas: 14280)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 10.84ms (10.55ms CPU time)

Ran 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInterestTests
[PASS] test_getInterest() (gas: 11818)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 291.63µs (22.25µs CPU time)

Ran 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetCollateralRequiredForTests
[PASS] test_getCollateralRequiredFor() (gas: 21550)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 309.71µs (44.63µs CPU time)

Ran 12 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_FundLoanTests
[PASS] test_fundLoan_approveFail() (gas: 330471)
[PASS] test_fundLoan_doubleFund(uint256) (runs: 257, μ: 282121, ~: 281816)
[PASS] test_fundLoan_fullFunding(uint256) (runs: 257, μ: 304527, ~: 304213)
[PASS] test_fundLoan_fullFundingWithExistingDrawableFunds(uint256) (runs: 257, μ: 306217, ~: 305955)
[PASS] test_fundLoan_invalidFundsAsset() (gas: 1502785)
[PASS] test_fundLoan_nextPaymentDueDateAlreadySet() (gas: 178880)
[PASS] test_fundLoan_noPaymentsRemaining() (gas: 87229)
[PASS] test_fundLoan_notLender() (gas: 27441)
[PASS] test_fundLoan_partialFunding(uint256) (runs: 257, μ: 226767, ~: 227999)
[PASS] test_fundLoan_termsNotAccepted() (gas: 31918)
[PASS] test_fundLoan_withUnaccountedCollateralAsset() (gas: 1619778)
[PASS] test_fundLoan_withoutSendingAsset() (gas: 181311)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 99.24ms (126.71ms CPU time)

Ran 1 test for tests/MapleLoanRefinancer.t.sol:MapleLoanRefinancerMultipleParameterTests
[PASS] test_refinance_multipleParameters(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9374918, ~: 9372604)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 286.48ms (286.01ms CPU time)

Ran 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetClosingPaymentBreakdownTests
[PASS] test_getClosingPaymentBreakdown(uint256,uint256,uint256) (runs: 257, μ: 8943986, ~: 8943968)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 96.03ms (95.59ms CPU time)

Ran 8 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_MakePaymentTests
[PASS] test_makePayment(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 390084, ~: 391570)
[PASS] test_makePayment_amountSmallerThanFees() (gas: 490305)
[PASS] test_makePayment_collateralNotMaintained() (gas: 874527)
[PASS] test_makePayment_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 415660, ~: 418602)
[PASS] test_makePayment_lastPaymentClearsLoan(uint256,uint256,uint256,uint256) (runs: 257, μ: 368032, ~: 368718)
[PASS] test_makePayment_noAmount() (gas: 480826)
[PASS] test_makePayment_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 394283, ~: 396115)
[PASS] test_makePayment_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 374949, ~: 375307)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 287.79ms (318.02ms CPU time)

Ran 3 tests for tests/MapleLoanRefinancer.t.sol:RefinanceFeeTests
[PASS] test_refinance_closingRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9310380, ~: 9311087)
[PASS] test_refinance_lateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9310671, ~: 9311428)
[PASS] test_refinance_lateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9330456, ~: 9331236)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 301.74ms (650.07ms CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinanceDeadlineTests
[PASS] test_refinance_afterDeadline(uint256,uint256,uint256) (runs: 257, μ: 9259911, ~: 9258858)
[PASS] test_refinance_differentDeadline(uint256,uint256,uint256) (runs: 257, μ: 9232619, ~: 9232636)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 213.66ms (402.26ms CPU time)

Ran 3 tests for tests/MapleLoanRefinancer.t.sol:RefinanceEndingPrincipalTests
[PASS] test_refinance_endingPrincipal_amortizedToInterestOnly(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9341428, ~: 9342257)
[PASS] test_refinance_endingPrincipal_failLargerThanPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9291786, ~: 9294975)
[PASS] test_refinance_endingPrincipal_interestOnlyToAmortized(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9335102, ~: 9340540)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 390.85ms (701.80ms CPU time)

Ran 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CloseLoanTests
[PASS] test_closeLoan(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 296467, ~: 296693)
[PASS] test_closeLoan_amountSmallerThanFees() (gas: 465218)
[PASS] test_closeLoan_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 362120, ~: 362168)
[PASS] test_closeLoan_latePayment(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 302895, ~: 303540)
[PASS] test_closeLoan_noAmount() (gas: 457672)
[PASS] test_closeLoan_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 304373, ~: 304870)
[PASS] test_closeLoan_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 297810, ~: 297790)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 525.92ms (263.31ms CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePrincipalRequestedTests
[PASS] test_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9388665, ~: 9389854)
[PASS] test_refinance_increasePrincipalRequestedWithInsufficientFunds(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 9323400, ~: 9323927)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 533.69ms (511.01ms CPU time)

Ran 7 tests for tests/MapleLoanRefinancer.t.sol:RefinancingFeesTerms
[PASS] testFuzz_refinance_payOriginationFees(uint256,uint256) (runs: 257, μ: 10865287, ~: 10865340)
[PASS] testFuzz_refinance_pdOriginationFeeTransferFail(uint256) (runs: 257, μ: 10777246, ~: 10777712)
[PASS] testFuzz_refinance_treasuryOriginationFeeTransferFail(uint256,uint256) (runs: 257, μ: 10791664, ~: 10791659)
[PASS] testFuzz_refinance_updateFeeTerms(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 257, μ: 10817395, ~: 10817991)
[PASS] testFuzz_refinance_updatesPlatformServiceFees(uint256) (runs: 257, μ: 10775581, ~: 10775933)
[PASS] test_refinance_updateRefinanceServiceFees() (gas: 10857774)
[PASS] test_refinance_updateRefinanceServiceFeesOnDoubleRefinance() (gas: 10960811)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 500.88ms (1.39s CPU time)

Ran 54 test suites in 541.33ms (5.11s CPU time): 266 tests passed, 0 failed, 0 skipped (266 total tests)
```

# `fixed-term-loan-manager (v3.0.1)`

```
Running 1 test for tests/MapleLoanManager.t.sol:AcceptNewTermsTests
[PASS] test_acceptNewTerms_invalidBorrower() (gas: 218426)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 7.82ms

Running 3 tests for tests/MapleLoanManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 32944)
[PASS] test_setImplementation_paused() (gas: 38941)
[PASS] test_setImplementation_success() (gas: 43909)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 8.07ms

Running 3 tests for tests/MapleLoanManager.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_notPoolDelegate() (gas: 40032)
[PASS] test_rejectNewTerms_paused() (gas: 38296)
[PASS] test_rejectNewTerms_success() (gas: 1112994)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 8.15ms

Running 2 tests for tests/MapleLoanManager.t.sol:ClaimTests
[PASS] test_claim_notLoan() (gas: 379687)
[PASS] test_claim_paused() (gas: 42940)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 8.22ms

Running 4 tests for tests/CreateInstanceTests.t.sol:CreateInstanceTests
[PASS] testFail_createInstance_collision() (gas: 17509)
[PASS] testFail_createInstance_notPool() (gas: 15396)
[PASS] test_createInstance_notPoolDeployer() (gas: 20637)
[PASS] test_createInstance_success_asPoolDeployer() (gas: 274766)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 9.67ms

Running 2 tests for tests/MapleLoanManager.t.sol:DistributeClaimedFunds
[PASS] test_distributeClaimedFunds_mapleTreasuryNotSet() (gas: 1406031)
[PASS] test_distributeLiquidationFunds_poolNotSet() (gas: 1342601)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.09ms

Running 4 tests for tests/MapleLoanManager.t.sol:SetMinRatio_SetterTests
[PASS] test_setMinRatio_noAuth() (gas: 43894)
[PASS] test_setMinRatio_paused() (gas: 39304)
[PASS] test_setMinRatio_success_asGovernor() (gas: 72034)
[PASS] test_setMinRatio_success_asPoolDelegate() (gas: 69263)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.25ms

Running 7 tests for tests/MapleLoanManager.t.sol:TriggerDefaultTests
[PASS] test_triggerDefault_notManager() (gas: 144235)
[PASS] test_triggerDefault_paused() (gas: 42169)
[PASS] test_triggerDefault_success_noCollateral_impaired() (gas: 251299)
[PASS] test_triggerDefault_success_noCollateral_notImpaired() (gas: 177719)
[PASS] test_triggerDefault_success_withCollateralAssetEqualToFundsAsset() (gas: 325299)
[PASS] test_triggerDefault_success_withCollateral_impaired() (gas: 436395)
[PASS] test_triggerDefault_success_withCollateral_notImpaired() (gas: 401902)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 11.09ms

Running 5 tests for tests/MapleLoanManager.t.sol:SetAllowedSlippage_SetterTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 44038)
[PASS] test_setAllowedSlippage_noAuth() (gas: 43830)
[PASS] test_setAllowedSlippage_paused() (gas: 39261)
[PASS] test_setAllowedSlippage_success_asGovernor() (gas: 72085)
[PASS] test_setAllowedSlippage_success_asPoolDelegate() (gas: 72084)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 2.02ms

Running 1 test for tests/MapleLoanManager.t.sol:ClaimDomainStartGtDomainEnd
[PASS] test_claim_domainStart_gt_domainEnd() (gas: 715050)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 12.04ms

Running 7 tests for tests/MapleLoanManager.t.sol:FundLoanTests
[PASS] test_fund() (gas: 447263)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 91335)
[PASS] test_fund_inactiveLoan() (gas: 71600)
[PASS] test_fund_invalidBorrower() (gas: 75141)
[PASS] test_fund_invalidFactory() (gas: 64138)
[PASS] test_fund_invalidLoan() (gas: 65294)
[PASS] test_fund_paused() (gas: 46859)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 11.92ms

Running 3 tests for tests/MapleLoanManager.t.sol:DistributeLiquidationFundsTests
[PASS] test_distributeLiquidationFunds_borrowerNotSet() (gas: 1188764)
[PASS] test_distributeLiquidationFunds_mapleTreasuryNotSet() (gas: 1234114)
[PASS] test_distributeLiquidationFunds_poolNotSet() (gas: 1220189)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.02ms

Running 6 tests for tests/MapleLoanManager.t.sol:SingleLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_amortized() (gas: 447371)
[PASS] test_claim_earlyPayment_interestOnly() (gas: 439922)
[PASS] test_claim_latePayment_amortized() (gas: 470153)
[PASS] test_claim_latePayment_interestOnly() (gas: 462702)
[PASS] test_claim_onTimePayment_amortized() (gas: 444599)
[PASS] test_claim_onTimePayment_interestOnly() (gas: 437216)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 5.51ms

Running 13 tests for tests/MapleLoanManager.t.sol:LoanManagerSortingTests
[PASS] test_addPaymentToList_ascendingPair() (gas: 106994)
[PASS] test_addPaymentToList_descendingPair() (gas: 106914)
[PASS] test_addPaymentToList_single() (gas: 67234)
[PASS] test_addPaymentToList_synchronizedPair() (gas: 106993)
[PASS] test_addPaymentToList_toHead() (gas: 150427)
[PASS] test_addPaymentToList_toMiddle() (gas: 151121)
[PASS] test_addPaymentToList_toTail() (gas: 151165)
[PASS] test_removePaymentFromList_earliestDueDate() (gas: 131755)
[PASS] test_removePaymentFromList_invalidPaymentId() (gas: 86775)
[PASS] test_removePaymentFromList_latestDueDate() (gas: 131489)
[PASS] test_removePaymentFromList_medianDueDate() (gas: 131823)
[PASS] test_removePaymentFromList_pair() (gas: 94915)
[PASS] test_removePaymentFromList_single() (gas: 58324)
Test result: ok. 13 passed; 0 failed; 0 skipped; finished in 4.33ms

Running 2 tests for tests/MapleLoanManager.t.sol:GetterTests
[PASS] test_accruedInterest() (gas: 43560)
[PASS] test_getAssetsUnderManagement() (gas: 50797)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.36ms

Running 5 tests for tests/MapleLoanManager.t.sol:FinishCollateralLiquidationTests
[PASS] test_finishCollateralLiquidation_callAfterTriggerDefaultOnUncollateralizedLoan() (gas: 141630)
[PASS] test_finishCollateralLiquidation_callBeforeTriggerDefault() (gas: 67166)
[PASS] test_finishCollateralLiquidation_notManager() (gas: 320152)
[PASS] test_finishCollateralLiquidation_paused() (gas: 44519)
[PASS] test_finishCollateralLiquidation_success_withCollateral() (gas: 396596)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.23ms

Running 2 tests for tests/MapleLoanManager.t.sol:UpdateAccountingFailureTests
[PASS] test_updateAccounting_notGovernor() (gas: 103379)
[PASS] test_updateAccounting_notPoolDelegate() (gas: 100586)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.33ms

Running 4 tests for tests/MapleLoanManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 36928)
[PASS] test_migrate_notFactory() (gas: 33474)
[PASS] test_migrate_paused() (gas: 39426)
[PASS] test_migrate_success() (gas: 43097)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.91ms

Running 3 tests for tests/MapleLoanManager.t.sol:TwoLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 710747)
[PASS] test_claim_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 734866)
[PASS] test_claim_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 707930)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 5.65ms

Running 2 tests for tests/MapleLoanManager.t.sol:ThreeLoanPastDomainEndClaimTests
[PASS] test_claim_loan1NotPaid_loan2NotPaid_loan3PaidLate() (gas: 411235)
[PASS] test_claim_loan3_loan1NotPaid_loan2NotPaid() (gas: 408747)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.43ms

Running 6 tests for tests/MapleLoanManager.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 43689)
[PASS] test_upgrade_notScheduled() (gas: 47551)
[PASS] test_upgrade_paused() (gas: 37258)
[PASS] test_upgrade_success_asPoolDelegate() (gas: 93407)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 82459)
[PASS] test_upgrade_upgradeFailed() (gas: 88416)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.78ms

Running 5 tests for tests/MapleLoanManager.t.sol:ImpairLoanTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 195535)
[PASS] test_impairLoan_failIfPaused() (gas: 41799)
[PASS] test_impairLoan_notAuthorized() (gas: 43512)
[PASS] test_impairLoan_success() (gas: 273187)
[PASS] test_impairLoan_success_byGovernor() (gas: 251131)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.33ms

Running 4 tests for tests/MapleLoanManager.t.sol:UpdateAccountingTests
[PASS] test_updateAccounting_afterDomainEnd() (gas: 130773)
[PASS] test_updateAccounting_afterTwoDomainEnds() (gas: 124597)
[PASS] test_updateAccounting_beforeDomainEnd() (gas: 111167)
[PASS] test_updateAccounting_failIfPaused() (gas: 39148)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.13ms

Running 6 tests for tests/MapleLoanManager.t.sol:UintCastingTests
[PASS] test_castUint112() (gas: 24508)
[PASS] test_castUint120() (gas: 24427)
[PASS] test_castUint128() (gas: 24487)
[PASS] test_castUint24() (gas: 24402)
[PASS] test_castUint48() (gas: 24445)
[PASS] test_castUint96() (gas: 24448)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 3.10ms

Running 4 tests for tests/MapleLoanManager.t.sol:RefinanceAccountingSingleLoanTests
[PASS] test_refinance_beforeLoanDueDate_interestOnly() (gas: 628420)
[PASS] test_refinance_onLatePayment_interestOnly() (gas: 631008)
[PASS] test_refinance_onLoanPaymentDueDate_interestOnly() (gas: 629143)
[PASS] test_refinance_onPaymentDueDate_amortized() (gas: 629932)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 7.88ms

Running 7 tests for tests/MapleLoanManager.t.sol:RemoveLoanImpairmentTests
[PASS] test_removeLoanImpairment_delegateNotAuthorizedToRemoveGovernors() (gas: 280563)
[PASS] test_removeLoanImpairment_failIfPaused() (gas: 46902)
[PASS] test_removeLoanImpairment_notByGovernor() (gas: 207550)
[PASS] test_removeLoanImpairment_notPoolDelegate() (gas: 203478)
[PASS] test_removeLoanImpairment_pastDueDate() (gas: 295387)
[PASS] test_removeLoanImpairment_successWithGovernor() (gas: 324999)
[PASS] test_removeLoanImpairment_successWithPD() (gas: 324023)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 12.08ms

Running 2 tests for tests/MapleLoanManager.t.sol:QueueNextPaymentTests
[PASS] testFuzz_queueNextPayment_fees(uint256,uint256) (runs: 256, μ: 214274, ~: 223454)
[PASS] test_queueNextPayment_fees() (gas: 182906)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 56.30ms

Running 1 test for tests/MapleLoanManagerFuzz.t.sol:SingleLoanClaimTests
[PASS] testFuzz_claim_latePayment_interestOnly(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 1850765, ~: 1857571)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 224.36ms
```

# `globals-v2 (v3.0.0)`

```
Running 2 tests for tests/MapleGlobals.t.sol:SetPendingGovernorTests
[PASS] test_setPendingGovernor() (gas: 49074)
[PASS] test_setPendingGovernor_notGovernor() (gas: 19193)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.15ms

Running 2 tests for tests/MapleGlobals.t.sol:SetMigrationAdminTests
[PASS] test_setMigrationAdmin() (gas: 49580)
[PASS] test_setMigrationAdmin_notGovernor() (gas: 19216)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.15ms

Running 1 test for tests/MapleGlobals.t.sol:IsValidScheduledCallTests
[PASS] test_isValidScheduledCall() (gas: 92032)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.22ms

Running 3 tests for tests/MapleGlobals.t.sol:SetMapleTreasuryTests
[PASS] test_setMapleTreasury() (gas: 49543)
[PASS] test_setMapleTreasury_notGovernor() (gas: 19173)
[PASS] test_setMapleTreasury_zeroAddressCheck() (gas: 19739)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.13ms

Running 3 tests for tests/MapleGlobals.t.sol:SetFunctionUnpauseTests
[PASS] test_setContractPause_asGovernor() (gas: 48300)
[PASS] test_setContractPause_asSecurityAdmin() (gas: 48517)
[PASS] test_setContractPause_notAuthorized() (gas: 24126)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.45ms

Running 7 tests for tests/MapleGlobals.t.sol:ActivatePoolManagerTests
[PASS] test_activatePoolManager_alreadyOwns() (gas: 55739)
[PASS] test_activatePoolManager_invalidDelegate() (gas: 79997)
[PASS] test_activatePoolManager_invalidFactory() (gas: 72400)
[PASS] test_activatePoolManager_invalidInstance() (gas: 74130)
[PASS] test_activatePoolManager_notAuthorized() (gas: 58822)
[PASS] test_activatePoolManager_success_governor() (gas: 54757)
[PASS] test_activatePoolManager_success_operationalAdmin() (gas: 56960)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 2.12ms

Running 3 tests for tests/MapleGlobals.t.sol:SetMinCoverAmountTests
[PASS] test_setMinCoverAmount_notAuthorized() (gas: 57587)
[PASS] test_setMinCoverAmount_success_governor() (gas: 50660)
[PASS] test_setMinCoverAmount_success_operationalAdmin() (gas: 79934)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.08ms

Running 4 tests for tests/MapleGlobals.t.sol:SetMaxCoverLiquidationPercentTests
[PASS] test_setMaxCoverLiquidationPercent_gt100() (gas: 55449)
[PASS] test_setMaxCoverLiquidationPercent_notAuthorized() (gas: 57527)
[PASS] test_setMaxCoverLiquidationPercent_success_governor() (gas: 50686)
[PASS] test_setMaxCoverLiquidationPercent_success_operationalAdmin() (gas: 80026)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.20ms

Running 4 tests for tests/MapleGlobals.t.sol:SetPlatformManagementFeeRateTests
[PASS] test_setPlatformManagementFeeRate_notAuthorized() (gas: 57684)
[PASS] test_setPlatformManagementFeeRate_outOfBounds() (gas: 55517)
[PASS] test_setPlatformManagementFeeRate_success_governor() (gas: 50824)
[PASS] test_setPlatformManagementFeeRate_success_operationalAdmin() (gas: 80075)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.26ms

Running 3 tests for tests/MapleGlobals.t.sol:ScheduleCallTests
[PASS] test_scheduleCal_overwrite() (gas: 83031)
[PASS] test_scheduleCall() (gas: 70187)
[PASS] test_scheduleCall_defaultState() (gas: 19347)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.23ms

Running 2 tests for tests/MapleGlobals.t.sol:SetOperationalAdminTests
[PASS] test_setOperationalAdmin() (gas: 49497)
[PASS] test_setOperationalAdmin_notGovernor() (gas: 19173)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 926.33µs

Running 3 tests for tests/MapleGlobals.t.sol:SetBootstrapMintTests
[PASS] test_setBootstrapMint_notAuthorized() (gas: 57588)
[PASS] test_setBootstrapMint_success_governor() (gas: 50723)
[PASS] test_setBootstrapMint_success_operationalAdmin() (gas: 79996)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.14ms

Running 4 tests for tests/MapleGlobals.t.sol:SetPlatformOriginationFeeRateTests
[PASS] test_setPlatformOriginationFeeRate_notAuthorized() (gas: 57659)
[PASS] test_setPlatformOriginationFeeRate_outOfBounds() (gas: 55514)
[PASS] test_setPlatformOriginationFeeRate_success_governor() (gas: 50820)
[PASS] test_setPlatformOriginationFeeRate_success_operational_admin() (gas: 80072)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.25ms

Running 6 tests for tests/MapleGlobals.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice() (gas: 79594)
[PASS] test_getLatestPrice_manualOverride() (gas: 98887)
[PASS] test_getLatestPrice_oracleNotSet() (gas: 21992)
[PASS] test_getLatestPrice_roundNotComplete() (gas: 30470)
[PASS] test_getLatestPrice_stalePrice() (gas: 97050)
[PASS] test_getLatestPrice_zeroPrice() (gas: 54245)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 1.65ms

Running 3 tests for tests/MapleGlobals.t.sol:SetContractPauseTests
[PASS] test_setContractPause_asGovernor() (gas: 43912)
[PASS] test_setContractPause_asSecurityAdmin() (gas: 45729)
[PASS] test_setContractPause_notAuthorized() (gas: 21722)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 4.37ms

Running 4 tests for tests/MapleGlobals.t.sol:SetPriceOracleTests
[PASS] test_setPriceOracle() (gas: 55975)
[PASS] test_setPriceOracle_notGovernor() (gas: 22127)
[PASS] test_setPriceOracle_zeroAddressCheck() (gas: 46311)
[PASS] test_setPriceOracle_zeroTimeCheck() (gas: 24827)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.22ms

Running 2 tests for tests/MapleGlobals.t.sol:SetDefaultTimelockParametersTests
[PASS] test_setDefaultTimelockParameters() (gas: 47300)
[PASS] test_setDefaultTimelockParameters_notGovernor() (gas: 17367)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 929.42µs

Running 3 tests for tests/MapleGlobals.t.sol:SetCanDeployFromTests
[PASS] test_setCanDeployFrom_notAuthorized() (gas: 24162)
[PASS] test_setCanDeployFrom_success_governor() (gas: 52234)
[PASS] test_setCanDeployFrom_success_operationalAdmin() (gas: 89101)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.19ms

Running 3 tests for tests/MapleGlobals.t.sol:SetValidPoolDeployer
[PASS] test_setValidDeployer_enablingNotAllowed() (gas: 22186)
[PASS] test_setValidDeployer_notGovernor() (gas: 19457)
[PASS] test_setValidDeployer_success() (gas: 25252)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.01ms

Running 3 tests for tests/MapleGlobals.t.sol:SetProtocolPauseTests
[PASS] test_setProtocolPause_asGovernor() (gas: 34529)
[PASS] test_setProtocolPause_asSecurityAdmin() (gas: 34868)
[PASS] test_setProtocolPause_notAuthorized() (gas: 19191)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.16ms

Running 3 tests for tests/MapleGlobals.t.sol:SetSecurityAdminTests
[PASS] test_setSecurityAdmin() (gas: 49553)
[PASS] test_setSecurityAdmin_notGovernor() (gas: 19241)
[PASS] test_setSecurityAdmin_zeroAddressCheck() (gas: 19850)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.02ms

Running 4 tests for tests/MapleGlobals.t.sol:TransferOwnedPoolTests
[PASS] test_transferOwnedPool() (gas: 75222)
[PASS] test_transferOwnedPool_alreadyOwns() (gas: 290775)
[PASS] test_transferOwnedPool_notPoolDelegate() (gas: 26561)
[PASS] test_transferOwnedPool_notPoolManager() (gas: 21720)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.51ms

Running 2 tests for tests/MapleGlobals.t.sol:SetValidCollateralTests
[PASS] test_setValidCollateral() (gas: 42689)
[PASS] test_setValidCollateral_notGovernor() (gas: 55354)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.98ms

Running 5 tests for tests/MapleGlobals.t.sol:UnScheduleCallTests
[PASS] test_unscheduleCall() (gas: 29896)
[PASS] test_unscheduleCall_asGovernor() (gas: 34785)
[PASS] test_unscheduleCall_asGovernor_callDataMismatch() (gas: 32370)
[PASS] test_unscheduleCall_callDataMismatch() (gas: 27438)
[PASS] test_unscheduleCall_notGovernor() (gas: 20299)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.46ms

Running 2 tests for tests/MapleGlobals.t.sol:SetValidPoolAssetTests
[PASS] test_setValidPoolAsset() (gas: 42670)
[PASS] test_setValidPoolAsset_notGovernor() (gas: 55396)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 976.42µs

Running 4 tests for tests/MapleGlobals.t.sol:SetTimelockWindowTests
[PASS] test_setTimelockWindow() (gas: 54708)
[PASS] test_setTimelockWindow_notGovernor() (gas: 20199)
[PASS] test_setTimelockWindows() (gas: 92612)
[PASS] test_setTimelockWindows_notGovernor() (gas: 23054)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.59ms

Running 2 tests for tests/MapleGlobals.t.sol:TransferGovernorTests
[PASS] test_acceptGovernor() (gas: 52192)
[PASS] test_acceptGovernor_notPendingGovernor() (gas: 16331)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.83ms

Running 7 tests for tests/MapleGlobals.t.sol:canDeployFromTests
[PASS] test_canDeployFrom_invalidFactoryAndCaller() (gas: 30350)
[PASS] test_canDeployFrom_poolManagerDeployingLoanManager() (gas: 105607)
[PASS] test_canDeployFrom_poolManagerDeployingLoanManager_WithValidFactoryAndCallerSet() (gas: 137363)
[PASS] test_canDeployFrom_validBorrowerDeploying_invalidFactoryInstance() (gas: 61759)
[PASS] test_canDeployFrom_validBorrowerDeploying_validFactoryInstanceSet() (gas: 85353)
[PASS] test_canDeployFrom_validBorrowerDeploying_withoutFactoryAndCallerSet() (gas: 91165)
[PASS] test_canDeployFrom_validFactoryAndCaller() (gas: 55397)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.91ms

Running 4 tests for tests/MapleGlobals.t.sol:SetValidPoolDelegate
[PASS] test_setValidDeployer_zeroAddress() (gas: 20041)
[PASS] test_setValidPoolDelegate_notAuthorized() (gas: 57672)
[PASS] test_setValidPoolDelegate_success_governor() (gas: 43278)
[PASS] test_setValidPoolDelegate_success_operationalAdmin() (gas: 80458)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.24ms

Running 3 tests for tests/MapleGlobals.t.sol:SetValidInstanceOfTests
[PASS] test_setValidInstanceOf_notAuthorized() (gas: 58432)
[PASS] test_setValidInstanceOf_success_governor() (gas: 44596)
[PASS] test_setValidInstanceOf_success_operationalAdmin() (gas: 81573)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.20ms

Running 3 tests for tests/MapleGlobals.t.sol:SetValidBorrowerTests
[PASS] test_setValidBorrower_notAuthorized() (gas: 57522)
[PASS] test_setValidBorrower_success_governor() (gas: 42748)
[PASS] test_setValidBorrower_success_operationalAdmin() (gas: 80205)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.03ms

Running 10 tests for tests/MapleGlobals.t.sol:IsPoolDeployerTest
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerCanDeploy() (gas: 80450)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerCannotDeploy() (gas: 59557)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerIsPoolManager() (gas: 479086)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_poolManagerNotFromValidFactory() (gas: 457564)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_poolManagerNotInstance() (gas: 457818)
[PASS] test_isPoolDeployer_invalidFactory() (gas: 21924)
[PASS] test_isPoolDeployer_poolManagerFactory_deployerCanDeploy() (gas: 82755)
[PASS] test_isPoolDeployer_poolManagerFactory_deployerCannotDeploy() (gas: 61909)
[PASS] test_isPoolDeployer_withdrawalManagerFactory_deployerCanDeploy() (gas: 85085)
[PASS] test_isPoolDeployer_withdrawalManagerFactory_deployerCannotDeploy() (gas: 64262)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 5.15ms

Running 4 tests for tests/MapleGlobals.t.sol:SetPlatformServiceFeeRateTests
[PASS] test_setPlatformServiceFeeRate_notAuthorized() (gas: 57525)
[PASS] test_setPlatformServiceFeeRate_outOfBounds() (gas: 55379)
[PASS] test_setPlatformServiceFeeRate_success_governor() (gas: 50842)
[PASS] test_setPlatformServiceFeeRate_success_operationalAdmin() (gas: 80094)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.03ms

Running 2 tests for tests/MapleGlobals.t.sol:SetManualOverridePriceTests
[PASS] test_setManualOverridePrice() (gas: 316295)
[PASS] test_setManualOverridePrice_notGovernor() (gas: 55507)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 6.38ms

Running 1 test for tests/MapleGlobals.t.sol:IsFunctionPausedTests
[PASS] test_isFunctionPaused() (gas: 259076)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 8.61ms
```

# `liquidations (v2.0.0)`

```
Running 2 tests for contracts/test/Liquidator.t.sol:LiquidatorSetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 19869)
[PASS] test_setImplementation_success() (gas: 32829)
Test result: ok. 2 passed; 0 failed; finished in 4.34s

Running 3 tests for contracts/test/Liquidator.t.sol:LiquidatorMigrateTests
[PASS] test_migrate_internalFailure() (gas: 25780)
[PASS] test_migrate_notFactory() (gas: 20161)
[PASS] test_migrate_success() (gas: 38188)
Test result: ok. 3 passed; 0 failed; finished in 4.34s

Running 4 tests for contracts/test/Liquidator.t.sol:LiquidatorUpgradeTests
[PASS] test_upgrade_notAuthorized() (gas: 31987)
[PASS] test_upgrade_notScheduled() (gas: 40074)
[PASS] test_upgrade_withGovernor() (gas: 92010)
[PASS] test_upgrade_withPoolDelegate() (gas: 93931)
Test result: ok. 4 passed; 0 failed; finished in 4.52s

Running 3 tests for contracts/test/Liquidator.t.sol:LiquidatorPullFundsTest
[PASS] test_pullFunds_notLoanManager() (gas: 22113)
[PASS] test_pullFunds_success() (gas: 46963)
[PASS] test_pullFunds_transferFailure() (gas: 32451)
Test result: ok. 3 passed; 0 failed; finished in 4.68s

Running 1 test for contracts/test/Liquidator.t.sol:MaliciousAssetTest
[PASS] test_liquidatePortion_maliciousAsset() (gas: 78189)
Test result: ok. 1 passed; 0 failed; finished in 4.78s

Running 1 test for contracts/test/Liquidator.t.sol:LiquidatorOTCTest
[PASS] test_eoa_otc_liquidation() (gas: 603858)
Test result: ok. 1 passed; 0 failed; finished in 8.04s

Running 1 test for contracts/test/Liquidator.t.sol:ReentrantLiquidatorTest
[PASS] test_liquidator_reentrantStrategy() (gas: 240054)
Test result: ok. 1 passed; 0 failed; finished in 8.14s

Running 1 test for contracts/test/Liquidator.t.sol:LiquidatorMultipleAMMTest
[PASS] test_liquidator_multipleStrategies() (gas: 1582972)
Test result: ok. 1 passed; 0 failed; finished in 11.06s

Running 4 tests for contracts/test/LiquidatorFactory.t.sol:LiquidatorFactoryTests
[PASS] test_createInstance_invalidLoanManager() (gas: 299372)
[PASS] test_createInstance_invalidLoanManagerFactory() (gas: 298420)
[PASS] test_createInstance_success() (gas: 308489)
[PASS] test_createInstance_zeroLoanManager() (gas: 432165)
Test result: ok. 4 passed; 0 failed; finished in 7.83s

Running 2 tests for contracts/test/Liquidator.t.sol:LiquidatorUniswapTest
[PASS] test_liquidator_uniswapStrategy() (gas: 1789571)
[PASS] test_liquidator_uniswapStrategy_largeLiquidation() (gas: 5090439)
Test result: ok. 2 passed; 0 failed; finished in 12.27s

Running 2 tests for contracts/test/Liquidator.t.sol:LiquidatorSushiswapTest
[PASS] test_liquidator_sushiswapStrategy() (gas: 1798107)
[PASS] test_liquidator_sushiswapStrategy_largeLiquidation() (gas: 5119028)
Test result: ok. 2 passed; 0 failed; finished in 12.27s
```

# `open-term-loan (v2.0.0)`

```
Ran 2 tests for tests/IsInDefault.t.sol:DefaultDatesTests
[PASS] test_isInDefault_successBoundary() (gas: 37730)
[PASS] test_isInDefault_zeroDefaultDate() (gas: 10353)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 993.13µs (68.38µs CPU time)

Ran 3 tests for tests/AcceptBorrower.t.sol:AcceptBorrowerTests
[PASS] test_acceptBorrower_notPendingBorrower() (gas: 48700)
[PASS] test_acceptBorrower_paused() (gas: 46171)
[PASS] test_acceptBorrower_success() (gas: 57205)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.74ms (174.00µs CPU time)

Ran 3 tests for tests/AcceptLender.t.sol:AcceptLenderTests
[PASS] test_acceptLender_notPendingLender() (gas: 48654)
[PASS] test_acceptLender_paused() (gas: 46191)
[PASS] test_acceptLender_success() (gas: 57255)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.41ms (124.54µs CPU time)

Ran 4 tests for tests/AcceptLoanTerms.t.sol:AcceptLoanTermsTests
[PASS] test_acceptLoanTerms_alreadyAccepted() (gas: 51449)
[PASS] test_acceptLoanTerms_notBorrower() (gas: 25081)
[PASS] test_acceptLoanTerms_paused() (gas: 46188)
[PASS] test_acceptLoanTerms_success() (gas: 54143)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.93ms (131.08µs CPU time)

Ran 3 tests for tests/Migrate.t.sol:MigrateTests
[PASS] test_migrate_notFactory() (gas: 24454)
[PASS] test_migrate_paused() (gas: 47455)
[PASS] test_migrate_success() (gas: 73513)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.37ms (119.46µs CPU time)

Ran 4 tests for tests/Getter.t.sol:GetterTests
[PASS] test_factory_getter() (gas: 10390)
[PASS] test_globals_getter() (gas: 16099)
[PASS] test_isCalled_getter() (gas: 30978)
[PASS] test_isImpaied_getter() (gas: 31028)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.46ms (79.63µs CPU time)

Ran 5 tests for tests/RejectNewTerms.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_mismatchedCommitment() (gas: 34576)
[PASS] test_rejectNewTerms_notBorrowerNorLender() (gas: 31175)
[PASS] test_rejectNewTerms_paused() (gas: 50077)
[PASS] test_rejectNewTerms_success_asBorrower() (gas: 47650)
[PASS] test_rejectNewTerms_success_asLender() (gas: 49874)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 830.50µs (200.67µs CPU time)

Ran 7 tests for tests/ProposeNewTerms.t.sol:ProposeNewTermsTests
[PASS] test_proposeNewTerms_deadlineBoundary() (gas: 113070)
[PASS] test_proposeNewTerms_emptyCalls() (gas: 63920)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 39638)
[PASS] test_proposeNewTerms_notFunded() (gas: 33631)
[PASS] test_proposeNewTerms_notLender() (gas: 26902)
[PASS] test_proposeNewTerms_paused() (gas: 48009)
[PASS] test_proposeNewTerms_success() (gas: 116203)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.00ms (420.46µs CPU time)

Ran 11 tests for tests/Initializer.t.sol:InitializerTests
[PASS] test_initialize_differentFundsAsset() (gas: 118379)
[PASS] test_initialize_invalidBorrower() (gas: 59713)
[PASS] test_initialize_invalidFundsAsset() (gas: 63450)
[PASS] test_initialize_invalidLenderFactory() (gas: 1763072)
[PASS] test_initialize_invalidLenderFactoryInstance() (gas: 1792711)
[PASS] test_initialize_invalidNoticePeriod() (gas: 22386)
[PASS] test_initialize_invalidPaymentInterval() (gas: 22435)
[PASS] test_initialize_invalidPrincipal() (gas: 22274)
[PASS] test_initialize_success() (gas: 304429)
[PASS] test_initialize_zeroBorrower() (gas: 30978)
[PASS] test_initialize_zeroLender() (gas: 63194)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 1.94ms (1.01ms CPU time)

Ran 3 tests for tests/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 23720)
[PASS] test_setImplementation_paused() (gas: 46810)
[PASS] test_setImplementation_success() (gas: 95903)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 484.54µs (88.42µs CPU time)

Ran 7 tests for tests/Fund.t.sol:FundTests
[PASS] testFuzz_fund_success() (gas: 1615271)
[PASS] test_fund_loanActive() (gas: 54349)
[PASS] test_fund_loanClosed() (gas: 35145)
[PASS] test_fund_notLender() (gas: 25850)
[PASS] test_fund_paused() (gas: 46958)
[PASS] test_fund_revertingTransfer() (gas: 1521294)
[PASS] test_fund_termsNotAccepted() (gas: 30270)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.68ms (1.11ms CPU time)

Ran 4 tests for tests/AcceptNewTerms.t.sol:AcceptNewTerms
[PASS] test_acceptNewTerms_earlyRefinance() (gas: 448216)
[PASS] test_acceptNewTerms_principalDecrease() (gas: 462616)
[PASS] test_acceptNewTerms_principalDecreaseToZero() (gas: 443184)
[PASS] test_acceptNewTerms_principalIncrease() (gas: 491836)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.84ms (2.18ms CPU time)

Ran 4 tests for tests/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 28661)
[PASS] test_upgrade_noAuth_asBorrower() (gas: 31292)
[PASS] test_upgrade_paused() (gas: 49820)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 234737)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 742.42µs (256.29µs CPU time)

Ran 7 tests for tests/Skim.t.sol:SkimTests
[PASS] test_skim_borrower() (gas: 1484553)
[PASS] test_skim_governor() (gas: 1482416)
[PASS] test_skim_noTokenToSkim() (gas: 1334560)
[PASS] test_skim_notBorrower() (gas: 31226)
[PASS] test_skim_paused() (gas: 32445)
[PASS] test_skim_revertingToken() (gas: 1411761)
[PASS] test_skim_zeroAddress() (gas: 24154)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 2.14ms (1.40ms CPU time)

Ran 5 tests for tests/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_insufficientForCalled() (gas: 107447)
[PASS] test_makePayment_insufficientForTotalTransferFromCaller() (gas: 1528232)
[PASS] test_makePayment_notFunded() (gas: 26551)
[PASS] test_makePayment_paused() (gas: 47580)
[PASS] test_makePayment_returningTooMuch() (gas: 86036)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 2.47ms (1.23ms CPU time)

Ran 4 tests for tests/SetPendingBorrower.t.sol:SetPendingBorrowerTests
[PASS] test_setPendingBorrower_invalidBorrower() (gas: 35826)
[PASS] test_setPendingBorrower_notBorrower() (gas: 27861)
[PASS] test_setPendingBorrower_paused() (gas: 48925)
[PASS] test_setPendingBorrower_success() (gas: 85335)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 646.00µs (132.46µs CPU time)

Ran 3 tests for tests/SetPendingLender.t.sol:SetPendingLenderTests
[PASS] test_setPendingLender_notLender() (gas: 27797)
[PASS] test_setPendingLender_paused() (gas: 48858)
[PASS] test_setPendingLender_success() (gas: 77832)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 525.63µs (82.38µs CPU time)

Ran 6 tests for tests/Repossess.t.sol:RepossessTests
[PASS] test_repossess_notInDefault() (gas: 57125)
[PASS] test_repossess_notLender() (gas: 28094)
[PASS] test_repossess_paused() (gas: 49155)
[PASS] test_repossess_revertingToken() (gas: 1428999)
[PASS] test_repossess_success() (gas: 1621055)
[PASS] test_repossess_success_noTransfer() (gas: 1474883)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 8.20ms (7.24ms CPU time)

Ran 1 test for tests/DefaultDates.t.sol:DefaultDatesTests
[PASS] testFuzz_defaultDates(uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 75048, ~: 75161)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 37.25ms (36.10ms CPU time)

Ran 11 tests for tests/GetPaymentBreakdown.t.sol:GetPaymentBreakdownTests
[PASS] testFuzz_getPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 296322, ~: 287011)
[PASS] test_getPaymentBreakdown_fixture1() (gas: 206354)
[PASS] test_getPaymentBreakdown_fixture10() (gas: 119261)
[PASS] test_getPaymentBreakdown_fixture2() (gas: 206105)
[PASS] test_getPaymentBreakdown_fixture3() (gas: 182205)
[PASS] test_getPaymentBreakdown_fixture4() (gas: 216371)
[PASS] test_getPaymentBreakdown_fixture5() (gas: 205290)
[PASS] test_getPaymentBreakdown_fixture6() (gas: 206778)
[PASS] test_getPaymentBreakdown_fixture7() (gas: 206960)
[PASS] test_getPaymentBreakdown_fixture8() (gas: 207011)
[PASS] test_getPaymentBreakdown_fixture9() (gas: 118981)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 44.66ms (44.62ms CPU time)

Ran 4 tests for tests/Impair.t.sol:ImpairTests
[PASS] testFuzz_impair_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 105860, ~: 106402)
[PASS] test_impair_loanNotFunded() (gas: 30539)
[PASS] test_impair_notLender() (gas: 25614)
[PASS] test_impair_paused() (gas: 46743)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 48.24ms (47.05ms CPU time)

Ran 4 tests for tests/RemoveImpairment.t.sol:RemoveImpairmentTests
[PASS] testFuzz_removeImpairment_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 103092, ~: 103593)
[PASS] test_removeImpairment_notImpaired() (gas: 30536)
[PASS] test_removeImpairment_notLender() (gas: 25634)
[PASS] test_removeImpairment_paused() (gas: 46719)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 47.89ms (47.83ms CPU time)

Ran 1 test for tests/DueDates.t.sol:DueDatesTests
[PASS] testFuzz_dueDates(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 69913, ~: 70228)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 51.83ms (50.28ms CPU time)

Ran 4 tests for tests/RemoveCall.t.sol:RemoveCallTests
[PASS] testFuzz_removeCall_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 108144, ~: 108767)
[PASS] test_removeCall_notCalled() (gas: 30471)
[PASS] test_removeCall_notLender() (gas: 25614)
[PASS] test_removeCall_paused() (gas: 46720)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 53.63ms (52.23ms CPU time)

Ran 6 tests for tests/CallPrincipal.t.sol:CallPrincipalTests
[PASS] testFuzz_callPrincipal_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 136877, ~: 136845)
[PASS] test_callPrincipal_insufficientPrincipalToReturn() (gas: 52434)
[PASS] test_callPrincipal_loanNotFunded() (gas: 30993)
[PASS] test_callPrincipal_notLender() (gas: 26067)
[PASS] test_callPrincipal_paused() (gas: 47151)
[PASS] test_callPrincipal_principalToReturnBoundary() (gas: 106826)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 54.96ms (54.07ms CPU time)

Ran 2 tests for tests/Factory.t.sol:FactoryTests
[PASS] test_createInstance(bytes32) (runs: 256, μ: 442869, ~: 442869)
[PASS] test_createInstance_cannotDeploy(bytes32) (runs: 256, μ: 44461, ~: 44461)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 61.11ms (77.98ms CPU time)

Ran 10 tests for tests/Refinancer.t.sol:RefinancerTests
[PASS] test_refinancer_decreasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144707, ~: 146468)
[PASS] test_refinancer_increasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143650, ~: 144217)
[PASS] test_refinancer_multipleCalls_refinance(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 176660, ~: 177898)
[PASS] test_refinancer_setDelegateServiceFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143124, ~: 144773)
[PASS] test_refinancer_setGracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143323, ~: 144750)
[PASS] test_refinancer_setInterestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144390, ~: 146145)
[PASS] test_refinancer_setLateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144049, ~: 144932)
[PASS] test_refinancer_setLateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144265, ~: 146336)
[PASS] test_refinancer_setNoticePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144194, ~: 145039)
[PASS] test_refinancer_setPaymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144104, ~: 145825)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 88.38ms (515.09ms CPU time)

Ran 7 tests for tests/AcceptNewTerms.t.sol:AcceptNewTermsFailure
[PASS] test_acceptNewTerms_expiredCommitmentBoundary() (gas: 3081734)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 56336)
[PASS] test_acceptNewTerms_mismatchedCommitment() (gas: 37306)
[PASS] test_acceptNewTerms_notBorrower() (gas: 26922)
[PASS] test_acceptNewTerms_paused() (gas: 48030)
[PASS] test_acceptNewTerms_refinancerRevert() (gas: 101374)
[PASS] test_acceptNewTerms_transferRevert() (gas: 1294622)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 90.37ms (678.00µs CPU time)

Ran 1 test for tests/MakePayment.t.sol:MakePaymentSuccessTests
[PASS] testFuzz_makePayment(uint256,uint256,uint256,uint256) (runs: 256, μ: 565460, ~: 572092)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 152.38ms (150.79ms CPU time)

Ran 29 test suites in 154.84ms (767.12ms CPU time): 136 tests passed, 0 failed, 0 skipped (136 total tests)

```

# `open-term-loan-manager (v1.0.0)`

```
Running 4 tests for tests/Call.t.sol:RemoveCallTests
[PASS] test_removeCall_notLoan() (gas: 36510)
[PASS] test_removeCall_notPoolDelegate() (gas: 33647)
[PASS] test_removeCall_paused() (gas: 49012)
[PASS] test_removeCall_success() (gas: 163392)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.57ms

Running 4 tests for tests/Call.t.sol:CallPrincipalTests
[PASS] test_callPrincipal_notLoan() (gas: 36801)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 33939)
[PASS] test_callPrincipal_paused() (gas: 49258)
[PASS] test_callPrincipal_success() (gas: 219567)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.64ms

Running 3 tests for tests/ImpairLoan.t.sol:ImpairLoanLimitTests
[PASS] test_impairLoan_accountedInterestLimit() (gas: 334688)
[PASS] test_impairLoan_impairmentDateLimit() (gas: 276295)
[PASS] test_impairLoan_unrealizedLossesLimit() (gas: 321500)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.00ms

Running 9 tests for tests/Fund.t.sol:FundFailureTests
[PASS] test_fund_failedApproval() (gas: 304882)
[PASS] test_fund_fundingMismatch() (gas: 249262)
[PASS] test_fund_inactiveLoan() (gas: 137835)
[PASS] test_fund_invalidBorrower() (gas: 111961)
[PASS] test_fund_invalidFactory() (gas: 52687)
[PASS] test_fund_invalidLoan() (gas: 85086)
[PASS] test_fund_notPoolDelegate() (gas: 36527)
[PASS] test_fund_paused() (gas: 46877)
[PASS] test_fund_reentrancy() (gas: 3062818)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 2.93ms

Running 7 tests for tests/Claim.t.sol:ClaimFailureTests
[PASS] test_claim_invalidState1() (gas: 61971)
[PASS] test_claim_invalidState2() (gas: 61982)
[PASS] test_claim_invalidState3() (gas: 62006)
[PASS] test_claim_invalidState4() (gas: 85800)
[PASS] test_claim_notLoan() (gas: 29726)
[PASS] test_claim_notPaused() (gas: 30908)
[PASS] test_claim_reentrancy() (gas: 210)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.96ms

Running 6 tests for tests/DistributeLiquidationFunds.t.sol:DistributeLiquidationFundsFailureTests
[PASS] test_distributeLiquidationFunds_transferBorrower() (gas: 62615)
[PASS] test_distributeLiquidationFunds_transferPool() (gas: 96332)
[PASS] test_distributeLiquidationFunds_transferTreasury() (gas: 135887)
[PASS] test_distributeLiquidationFunds_zeroBorrower() (gas: 31964)
[PASS] test_distributeLiquidationFunds_zeroPool() (gas: 63616)
[PASS] test_distributeLiquidationFunds_zeroTreasury() (gas: 103186)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.03ms

Running 4 tests for tests/ImpairLoan.t.sol:ImpairLoanSuccessTests
[PASS] test_impairLoan_acl_governor() (gas: 86453)
[PASS] test_impairLoan_acl_poolDelegate() (gas: 94367)
[PASS] test_impairLoan_success() (gas: 237556)
[PASS] test_impairLoan_success_alreadyImpaired() (gas: 301460)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.28ms

Running 3 tests for tests/ImpairLoan.t.sol:ImpairLoanFailureTests
[PASS] test_impairLoan_notLoan() (gas: 30688)
[PASS] test_impairLoan_notPoolDelegateOrGovernor() (gas: 62776)
[PASS] test_impairLoan_paused() (gas: 31824)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.33ms

Running 8 tests for tests/Claim.t.sol:ClaimTests
[PASS] test_claim() (gas: 293082)
[PASS] test_claim_closingLoan() (gas: 254803)
[PASS] test_claim_impaired() (gas: 296677)
[PASS] test_claim_impaired_requestingPrincipal() (gas: 367893)
[PASS] test_claim_impaired_returningPrincipal() (gas: 334817)
[PASS] test_claim_requestingPrincipalIncrease() (gas: 390703)
[PASS] test_claim_returnMorePrincipal() (gas: 294587)
[PASS] test_claim_returningPrincipal() (gas: 306508)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 5.69ms

Running 4 tests for tests/RejectNewTerms.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_notLoan() (gas: 37807)
[PASS] test_rejectNewTerms_notPoolDelegate() (gas: 34945)
[PASS] test_rejectNewTerms_paused() (gas: 50263)
[PASS] test_rejectNewTerms_success() (gas: 370039)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 5.97ms

Running 4 tests for tests/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_noAuth() (gas: 109665)
[PASS] test_removeLoanImpairment_notLoan() (gas: 30665)
[PASS] test_removeLoanImpairment_paused() (gas: 31780)
[PASS] test_removeLoanImpairment_poolDelegateAfterGovernor() (gas: 104416)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.55ms

Running 3 tests for tests/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentSuccessTests
[PASS] test_removeLoanImpairment_acl_governor_success() (gas: 86417)
[PASS] test_removeLoanImpairment_success() (gas: 232231)
[PASS] test_removeLoanImpairment_success_alreadyUnimpaired() (gas: 298844)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.13ms

Running 6 tests for tests/DistributeClaimedFunds.t.sol:DistributeClaimedFundsFailureTests
[PASS] test_distributeClaimFunds_platformTransfer() (gas: 114619)
[PASS] test_distributeClaimFunds_poolTransfer() (gas: 66853)
[PASS] test_distributeClaimFunds_zeroDelegate() (gas: 74958)
[PASS] test_distributeClaimFunds_zeroPool() (gas: 34186)
[PASS] test_distributeClaimFunds_zeroPoolDelegate() (gas: 61369)
[PASS] test_distributeClaimFunds_zeroTreasury() (gas: 81969)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 5.04ms

Running 3 tests for tests/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notLoan() (gas: 29045)
[PASS] test_triggerDefault_notPoolDelegate() (gas: 52388)
[PASS] test_triggerDefault_paused() (gas: 47303)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.05ms

Running 2 tests for tests/TriggerDefault.t.sol:TriggerDefaultSuccessTests
[PASS] test_triggerDefault_success_impaired() (gas: 127694)
[PASS] test_triggerDefault_success_notImpaired() (gas: 144035)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.08ms

Running 6 tests for tests/CreateInstance.t.sol:CreateInstanceTests
[PASS] testFail_createInstance_collision() (gas: 8937393460516738375)
[PASS] testFail_createInstance_notPool() (gas: 189539)
[PASS] test_createInstance_cannotDeploy() (gas: 20830)
[PASS] test_createInstance_invalidFactory() (gas: 208587)
[PASS] test_createInstance_invalidInstance() (gas: 214446)
[PASS] test_createInstance_success() (gas: 301735)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 11.40ms

Running 5 tests for tests/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 36587)
[PASS] test_upgrade_notScheduled() (gas: 38973)
[PASS] test_upgrade_paused() (gas: 47166)
[PASS] test_upgrade_success_asPoolDelegate() (gas: 267440)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 242666)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.97ms

Running 4 tests for tests/ProposeNewTerms.t.sol:ProposeNewTermsTests
[PASS] test_proposeNewTerms_notLoan() (gas: 40572)
[PASS] test_proposeNewTerms_notPoolDelegate() (gas: 37665)
[PASS] test_proposeNewTerms_paused() (gas: 53073)
[PASS] test_proposeNewTerms_success() (gas: 370106)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.24ms

Running 1 test for tests/InternalFunctions.t.sol:UpdatePrincipalOutTests
[PASS] testFuzz_updatePrincipalOut(uint256,int256) (runs: 256, μ: 43923, ~: 45406)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 42.65ms

Running 1 test for tests/InternalFunctions.t.sol:UpdateUnrealizedLossesTests
[PASS] testFuzz_updateUnrealizedLosses(uint256,int256) (runs: 256, μ: 43878, ~: 45552)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 48.89ms

Running 1 test for tests/DistributeLiquidationFunds.t.sol:DistributeLiquidationFundsTests
[PASS] testFuzz_distributeLiquidationFunds(uint256,uint256,uint256,uint256) (runs: 256, μ: 164079, ~: 153939)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 82.78ms

Running 1 test for tests/InternalFunctions.t.sol:UpdateAccountingStateTests
[PASS] testFuzz_updateInterestAccounting(uint256,uint256,uint256,int256,int256) (runs: 256, μ: 89109, ~: 91269)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 82.87ms

Running 1 test for tests/DistributeClaimedFunds.t.sol:DistributeClaimedFundsTests
[PASS] testFuzz_distributeClaimFunds(int256,uint256,uint256,uint256,bool) (runs: 256, μ: 189811, ~: 182745)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 90.13ms

Running 5 tests for tests/Fund.t.sol:FundSuccessTests
[PASS] testFuzz_fund_multipleLoans(uint256) (runs: 256, μ: 73368195, ~: 88262012)
[PASS] test_fund_managementFeeRateLimits() (gas: 3269085)
[PASS] test_fund_paymentIssuanceRateLimit() (gas: 3356391)
[PASS] test_fund_principalLimit() (gas: 3462870)
[PASS] test_fund_startDateAndDomainStartLimit() (gas: 3390036)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.00s
```

# `pool-v2 (v4.0.0)`

```
Ran 3 tests for tests/MaplePoolDelegateCover.t.sol:MaplePoolDelegateCoverTests
[PASS] test_moveFunds_badTransfer() (gas: 61205)
[PASS] test_moveFunds_notManager() (gas: 52197)
[PASS] test_moveFunds_success() (gas: 61764)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 893.13µs (211.17µs CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:DepositCoverTests
[PASS] test_depositCover_insufficientApproval() (gas: 109202)
[PASS] test_depositCover_paused() (gas: 51528)
[PASS] test_depositCover_success() (gas: 94803)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.72ms (222.79µs CPU time)

Ran 3 tests for tests/MaplePool.t.sol:ConstructorTests
[PASS] test_constructor_invalidApproval() (gas: 6027597)
[PASS] test_constructor_invalidDecimals() (gas: 5934537)
[PASS] test_constructor_zeroManager() (gas: 5509188)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.25ms (1.34ms CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30461)
[PASS] test_setImplementation_paused() (gas: 53654)
[PASS] test_setImplementation_success() (gas: 43420)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.18ms (107.00µs CPU time)

Ran 6 tests for tests/MaplePool.t.sol:RequestRedeemTests
[PASS] test_requestRedeem_checkCall() (gas: 82624)
[PASS] test_requestRedeem_failWithoutApproval() (gas: 35411)
[PASS] test_requestRedeem_insufficientApproval() (gas: 107236)
[PASS] test_requestRedeem_withApproval() (gas: 77280)
[PASS] test_requestRedeem_zeroShares() (gas: 71219)
[PASS] test_requestRedeem_zeroSharesAndNotOwnerAndNoAllowance() (gas: 45934)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 3.96ms (677.54µs CPU time)

Ran 8 tests for tests/MaplePool.t.sol:RedeemTests
[PASS] test_redeem_checkCall() (gas: 83149)
[PASS] test_redeem_insufficientAmount() (gas: 66743)
[PASS] test_redeem_insufficientApprove() (gas: 142565)
[PASS] test_redeem_reentrancy() (gas: 146044)
[PASS] test_redeem_success() (gas: 141085)
[PASS] test_redeem_success_differentUser() (gas: 177099)
[PASS] test_redeem_zeroAssets() (gas: 98431)
[PASS] test_redeem_zeroShares() (gas: 53835)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 4.21ms (1.43ms CPU time)

Ran 7 tests for tests/MaplePoolManager.t.sol:AddStrategy_SetterTests
[PASS] test_addStrategy_invalidFactory() (gas: 43831)
[PASS] test_addStrategy_notPoolDelegate() (gas: 51357)
[PASS] test_addStrategy_paused() (gas: 42334)
[PASS] test_addStrategy_success_asGovernor() (gas: 183379)
[PASS] test_addStrategy_success_asOperationalAdmin() (gas: 187826)
[PASS] test_addStrategy_success_asPoolDelegate() (gas: 178920)
[PASS] test_addStrategy_success_whenNotConfigured() (gas: 166904)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 4.57ms (527.54µs CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:SetIsStrategy_SetterTests
[PASS] test_setIsStrategy_invalidLM() (gas: 720423)
[PASS] test_setIsStrategy_notPoolDelegate() (gas: 41669)
[PASS] test_setIsStrategy_paused() (gas: 53934)
[PASS] test_setIsStrategy_successWithPoolDelegate() (gas: 60991)
[PASS] test_setIsStrategy_success_asGovernor() (gas: 67823)
[PASS] test_setIsStrategy_success_asOperationalAdmin() (gas: 74653)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.53ms (341.71µs CPU time)

Ran 6 tests for tests/MaplePoolDeployer.t.sol:MaplePoolDeployerTests
[PASS] test_deployPool_invalidPoolDelegate() (gas: 154111)
[PASS] test_deployPool_mismatchingArrays() (gas: 153820)
[PASS] test_deployPool_success_withCoverRequired_cyclicalWM() (gas: 5841354)
[PASS] test_deployPool_success_withCoverRequired_queueWM() (gas: 5830195)
[PASS] test_deployPool_success_withoutCoverRequired_cyclicalWM() (gas: 5778120)
[PASS] test_deployPool_transferFailed() (gas: 5673847)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 5.76ms (3.19ms CPU time)

Ran 4 tests for tests/MaplePool.t.sol:RemoveSharesTests
[PASS] test_removeShares_checkCall() (gas: 54471)
[PASS] test_removeShares_failWithoutApproval() (gas: 33228)
[PASS] test_removeShares_insufficientApproval() (gas: 72817)
[PASS] test_removeShares_withApproval() (gas: 49910)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.36ms (315.92µs CPU time)

Ran 10 tests for tests/MaplePoolManager.t.sol:FinishCollateralLiquidation
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 208720)
[PASS] test_finishCollateralLiquidation_paused() (gas: 36643)
[PASS] test_finishCollateralLiquidation_success_coverLeftOver() (gas: 282459)
[PASS] test_finishCollateralLiquidation_success_exceedMaxCoverLiquidationPercentAmount() (gas: 279153)
[PASS] test_finishCollateralLiquidation_success_fullCoverLiquidation_preexistingLoss() (gas: 283987)
[PASS] test_finishCollateralLiquidation_success_noCoverLeftOver() (gas: 262536)
[PASS] test_finishCollateralLiquidation_success_noCover_asGovernor() (gas: 244138)
[PASS] test_finishCollateralLiquidation_success_noCover_asOperationalAdmin() (gas: 252437)
[PASS] test_finishCollateralLiquidation_success_noCover_asPoolDelegate() (gas: 237173)
[PASS] test_finishCollateralLiquidation_success_noRemainingLossAfterCollateralLiquidation() (gas: 246101)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 4.60ms (1.74ms CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:SetLiquidityCap_SetterTests
[PASS] test_setLiquidityCap_notPoolDelegate() (gas: 46161)
[PASS] test_setLiquidityCap_paused() (gas: 54282)
[PASS] test_setLiquidityCap_success_asGovernor() (gas: 66851)
[PASS] test_setLiquidityCap_success_asOperationalAdmin() (gas: 72393)
[PASS] test_setLiquidityCap_success_asPoolDelegate() (gas: 64148)
[PASS] test_setLiquidityCap_success_whenNotConfigured() (gas: 52091)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.01ms (197.92µs CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:CompleteConfigurationTests
[PASS] test_completeConfiguration_alreadyConfigured() (gas: 34578)
[PASS] test_completeConfiguration_paused() (gas: 50992)
[PASS] test_completeConfiguration_success() (gas: 32149)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.91ms (73.08µs CPU time)

Ran 4 tests for tests/MaplePoolManager.t.sol:AcceptPoolDelegate_SetterTests
[PASS] test_acceptPoolDelegate_globalsTransferFails() (gas: 61270)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 29882)
[PASS] test_acceptPoolDelegate_paused() (gas: 53772)
[PASS] test_acceptPoolDelegate_success() (gas: 53433)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.97ms (132.67µs CPU time)

Ran 26 tests for tests/MaplePoolManager.t.sol:CanCallTests
[PASS] test_canCall_depositWithPermit_lenderNotAllowed() (gas: 103784)
[PASS] test_canCall_depositWithPermit_liquidityCapExceeded() (gas: 87924)
[PASS] test_canCall_depositWithPermit_notActive() (gas: 52280)
[PASS] test_canCall_deposit_lenderNotAllowed() (gas: 102812)
[PASS] test_canCall_deposit_liquidityCapExceeded() (gas: 87494)
[PASS] test_canCall_deposit_notActive() (gas: 51513)
[PASS] test_canCall_invalidFunctionId() (gas: 43372)
[PASS] test_canCall_mintWithPermit_lenderNotAllowed() (gas: 122594)
[PASS] test_canCall_mintWithPermit_liquidityCapExceeded() (gas: 100518)
[PASS] test_canCall_mintWithPermit_notActive() (gas: 75441)
[PASS] test_canCall_mint_lenderNotAllowed() (gas: 121389)
[PASS] test_canCall_mint_liquidityCapExceeded() (gas: 99697)
[PASS] test_canCall_mint_notActive() (gas: 74597)
[PASS] test_canCall_paused_redeem() (gas: 51923)
[PASS] test_canCall_paused_removeShares() (gas: 51967)
[PASS] test_canCall_paused_requestRedeem() (gas: 51967)
[PASS] test_canCall_paused_requestWithdraw() (gas: 51902)
[PASS] test_canCall_paused_transfer() (gas: 51946)
[PASS] test_canCall_paused_withdraw() (gas: 51989)
[PASS] test_canCall_redeem() (gas: 41176)
[PASS] test_canCall_removeShares() (gas: 40667)
[PASS] test_canCall_requestRedeem() (gas: 40654)
[PASS] test_canCall_requestWithdraw() (gas: 40733)
[PASS] test_canCall_transferFrom_recipientNotAllowed() (gas: 92779)
[PASS] test_canCall_transfer_recipientNotAllowed() (gas: 91918)
[PASS] test_canCall_withdraw() (gas: 41156)
Suite result: ok. 26 passed; 0 failed; 0 skipped; finished in 4.25ms (1.95ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:HandleCoverTests
[PASS] test_handleCover_feesAndSomeLosses() (gas: 126686)
[PASS] test_handleCover_fullCoverage() (gas: 146598)
[PASS] test_handleCover_halfCoverage() (gas: 153469)
[PASS] test_handleCover_noCover() (gas: 67539)
[PASS] test_handleCover_onlyFees() (gas: 114764)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 2.35ms (489.79µs CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:SetPendingPoolDelegate_SetterTests
[PASS] test_setPendingPoolDelegate_asGovernor_success() (gas: 66418)
[PASS] test_setPendingPoolDelegate_asOperationalAdmin_success() (gas: 71871)
[PASS] test_setPendingPoolDelegate_asPoolDelegate_success() (gas: 61897)
[PASS] test_setPendingPoolDelegate_notPoolDelegateOrProtocolAdmins() (gas: 41366)
[PASS] test_setPendingPoolDelegate_paused() (gas: 56298)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.95ms (180.08µs CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 35295)
[PASS] test_upgrade_notScheduled() (gas: 37606)
[PASS] test_upgrade_paused() (gas: 52004)
[PASS] test_upgrade_successWithPoolDelegate() (gas: 103712)
[PASS] test_upgrade_successWithSecurityAdmin() (gas: 100298)
[PASS] test_upgrade_upgradeFailed() (gas: 94568)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.62ms (356.04µs CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:SetWithdrawalManager_SetterTests
[PASS] test_setWithdrawalManager_configured() (gas: 37281)
[PASS] test_setWithdrawalManager_invalidFactory() (gas: 72844)
[PASS] test_setWithdrawalManager_invalidInstance() (gas: 51986)
[PASS] test_setWithdrawalManager_paused() (gas: 56408)
[PASS] test_setWithdrawalManager_success_asPoolDelegate() (gas: 52099)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 5.79ms (183.38µs CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:TriggerDefault
[PASS] test_triggerDefault_invalidFactory() (gas: 117089)
[PASS] test_triggerDefault_notAuthorized() (gas: 48972)
[PASS] test_triggerDefault_paused() (gas: 41747)
[PASS] test_triggerDefault_success_asGovernor() (gas: 85805)
[PASS] test_triggerDefault_success_asOperationalAdmin() (gas: 93809)
[PASS] test_triggerDefault_success_asPoolDelegate() (gas: 81387)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.36ms (362.46µs CPU time)

Ran 3 tests for tests/MaplePool.t.sol:WithdrawTests
[PASS] testFuzz_withdraw_failNotEnabled(uint256) (runs: 256, μ: 33384, ~: 33384)
[PASS] test_withdraw_checkCall() (gas: 83127)
[PASS] test_withdraw_failNotEnabled() (gas: 33253)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 16.60ms (15.04ms CPU time)

Ran 2 tests for tests/MaplePoolManager.t.sol:MaxWithdrawTests
[PASS] testFuzz_maxWithdraw(address) (runs: 256, μ: 17619, ~: 17619)
[PASS] test_maxWithdraw() (gas: 17290)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 13.59ms (11.82ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 36613)
[PASS] test_migrate_invalidPoolDelegateCover() (gas: 41714)
[PASS] test_migrate_notFactory() (gas: 30960)
[PASS] test_migrate_paused() (gas: 54130)
[PASS] test_migrate_success() (gas: 44765)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.74ms (143.83µs CPU time)

Ran 7 tests for tests/MaplePoolManager.t.sol:WithdrawCoverTests
[PASS] test_withdrawCover_noRequirement() (gas: 97325)
[PASS] test_withdrawCover_notPoolDelegate() (gas: 157716)
[PASS] test_withdrawCover_paused() (gas: 54742)
[PASS] test_withdrawCover_success() (gas: 151796)
[PASS] test_withdrawCover_success_zeroRecipient() (gas: 151629)
[PASS] test_withdrawCover_tryWithdrawBelowRequired() (gas: 200473)
[PASS] test_withdrawCover_withdrawMoreThanBalance() (gas: 83435)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 13.21ms (1.37ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:ProcessRedeemTests
[PASS] test_processRedeem_noApproval() (gas: 49741)
[PASS] test_processRedeem_notWithdrawalManager() (gas: 36467)
[PASS] test_processRedeem_paused() (gas: 52596)
[PASS] test_processRedeem_success() (gas: 44061)
[PASS] test_processRedeem_success_notSender() (gas: 81810)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.94ms (384.25µs CPU time)

Ran 10 tests for tests/MaplePoolManager.t.sol:RequestFundsTests
[PASS] test_requestFunds_insufficientCoverBoundary() (gas: 232413)
[PASS] test_requestFunds_invalidFactory() (gas: 51345)
[PASS] test_requestFunds_invalidInstance() (gas: 59759)
[PASS] test_requestFunds_lockedLiquidityBoundary() (gas: 257903)
[PASS] test_requestFunds_notLM() (gas: 60475)
[PASS] test_requestFunds_paused() (gas: 36951)
[PASS] test_requestFunds_success() (gas: 129174)
[PASS] test_requestFunds_zeroAddress() (gas: 84852)
[PASS] test_requestFunds_zeroPrincipal() (gas: 47572)
[PASS] test_requestFunds_zeroSupply() (gas: 69871)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 2.47ms (800.58µs CPU time)

Ran 7 tests for tests/MaplePoolManagerFactory.t.sol:PoolManagerFactoryFailureTest
[PASS] test_createInstance_failWithActivePoolDelegate() (gas: 268976)
[PASS] test_createInstance_failWithDisallowedAsset() (gas: 250623)
[PASS] test_createInstance_failWithInvalidPoolDelegate() (gas: 239094)
[PASS] test_createInstance_failWithNonERC20Asset() (gas: 246552)
[PASS] test_createInstance_failWithZeroAddressPoolDelegate() (gas: 195516)
[PASS] test_createInstance_failWithZeroAdmin() (gas: 5200847)
[PASS] test_createInstance_notPoolDeployer() (gas: 4904323)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 4.16ms (1.44ms CPU time)

Ran 4 tests for tests/MaplePoolManager.t.sol:MaxDepositTests
[PASS] test_maxDeposit_liquidityCap() (gas: 196749)
[PASS] test_maxDeposit_liquidityCap(address,address,uint256,uint256) (runs: 256, μ: 136205, ~: 137002)
[PASS] test_maxDeposit_withPermission() (gas: 89223)
[PASS] test_maxDeposit_withoutPermission() (gas: 81441)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 20.82ms (19.07ms CPU time)

Ran 1 test for tests/MaplePoolManagerFactory.t.sol:PoolManagerFactoryTest
[PASS] test_createInstance() (gas: 5010269)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.45ms (335.42µs CPU time)

Ran 2 tests for tests/MaplePoolManagerMigrator.t.sol:MaplePoolManagerMigratorTests
[PASS] test_migrator_failure() (gas: 99136)
[PASS] test_migrator_success() (gas: 157835)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.00ms (235.00µs CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:SetActive_SetterTests
[PASS] test_setActive_notGlobals() (gas: 33264)
[PASS] test_setActive_paused() (gas: 52169)
[PASS] test_setActive_success() (gas: 50179)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 12.74ms (316.63µs CPU time)

Ran 7 tests for tests/MaplePoolManager.t.sol:SetDelegateManagementFeeRate_SetterTests
[PASS] test_setDelegateManagementFeeRate_notPoolDelegate() (gas: 48114)
[PASS] test_setDelegateManagementFeeRate_oob() (gas: 76149)
[PASS] test_setDelegateManagementFeeRate_paused() (gas: 56212)
[PASS] test_setDelegateManagementFeeRate_success_asGovernor() (gas: 68874)
[PASS] test_setDelegateManagementFeeRate_success_asOperationalAdmin() (gas: 74372)
[PASS] test_setDelegateManagementFeeRate_success_asPoolDelegate() (gas: 66272)
[PASS] test_setDelegateManagementFeeRate_success_whenNotConfigured() (gas: 54214)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 4.02ms (619.54µs CPU time)

Ran 7 tests for tests/MaplePool.t.sol:ConvertToSharesTests
[PASS] testFuzz_convertToShares(uint256,uint256,uint256) (runs: 256, μ: 188870, ~: 189472)
[PASS] test_convertToShares_decreasedExchangeRate() (gas: 183728)
[PASS] test_convertToShares_increasedExchangeRate() (gas: 183770)
[PASS] test_convertToShares_initialExchangeRate() (gas: 183727)
[PASS] test_convertToShares_initialState() (gas: 23328)
[PASS] test_convertToShares_prematureYield() (gas: 43273)
[PASS] test_convertToShares_worthlessShares() (gas: 171019)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 47.81ms (43.84ms CPU time)

Ran 5 tests for tests/MaplePool.t.sol:RequestWithdraw
[PASS] testFuzz_requestWithdraw_failNotEnabled(uint256) (runs: 256, μ: 92649, ~: 92087)
[PASS] test_requestWithdraw_checkCall() (gas: 82690)
[PASS] test_requestWithdraw_failWithoutApproval() (gas: 45013)
[PASS] test_requestWithdraw_insufficientApproval() (gas: 125721)
[PASS] test_requestWithdraw_withApproval_failNotEnabled() (gas: 86052)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 49.91ms (45.97ms CPU time)

Ran 6 tests for tests/MaplePool.t.sol:DepositTests
[PASS] testFuzz_deposit_badApprove(uint256) (runs: 256, μ: 167674, ~: 167502)
[PASS] testFuzz_deposit_insufficientBalance(uint256) (runs: 256, μ: 170934, ~: 170446)
[PASS] test_deposit_checkCall() (gas: 134133)
[PASS] test_deposit_reentrancy() (gas: 186348)
[PASS] test_deposit_zeroReceiver() (gas: 111249)
[PASS] test_deposit_zeroShares() (gas: 111296)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 50.05ms (47.44ms CPU time)

Ran 7 tests for tests/MaplePool.t.sol:ConvertToAssetsTests
[PASS] testFuzz_convertToAssets(uint256,uint256,uint256) (runs: 256, μ: 188606, ~: 189306)
[PASS] test_convertToAssets_decreasedExchangeRate() (gas: 183733)
[PASS] test_convertToAssets_increasedExchangeRate() (gas: 183734)
[PASS] test_convertToAssets_initialExchangeRate() (gas: 183689)
[PASS] test_convertToAssets_initialState() (gas: 23248)
[PASS] test_convertToAssets_prematureYield() (gas: 43191)
[PASS] test_convertToAssets_worthlessShares() (gas: 163810)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 51.02ms (48.65ms CPU time)

Ran 6 tests for tests/MaplePool.t.sol:MintTests
[PASS] testFuzz_mint_badApprove(uint256) (runs: 256, μ: 168067, ~: 167569)
[PASS] testFuzz_mint_insufficientBalance(uint256) (runs: 256, μ: 171067, ~: 170470)
[PASS] test_mint_checkCall() (gas: 136443)
[PASS] test_mint_reentrancy() (gas: 186394)
[PASS] test_mint_zeroReceiver() (gas: 111317)
[PASS] test_mint_zeroShares() (gas: 111408)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 57.22ms (53.02ms CPU time)

Ran 7 tests for tests/MaplePool.t.sol:PreviewDepositTests
[PASS] testFuzz_previewDeposit(uint256,uint256,uint256) (runs: 256, μ: 188445, ~: 189469)
[PASS] test_previewDeposit_decreasedExchangeRate() (gas: 183938)
[PASS] test_previewDeposit_increasedExchangeRate() (gas: 183960)
[PASS] test_previewDeposit_initialExchangeRate() (gas: 183962)
[PASS] test_previewDeposit_initialState() (gas: 23540)
[PASS] test_previewDeposit_prematureYield() (gas: 43462)
[PASS] test_previewDeposit_worthlessShares() (gas: 171142)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 52.22ms (50.90ms CPU time)

Ran 7 tests for tests/MaplePool.t.sol:PreviewMintTests
[PASS] testFuzz_previewMint(uint256,uint256,uint256) (runs: 256, μ: 193698, ~: 193635)
[PASS] test_previewMint_decreasedExchangeRate() (gas: 185045)
[PASS] test_previewMint_increasedExchangeRate() (gas: 185045)
[PASS] test_previewMint_initialExchangeRate() (gas: 185090)
[PASS] test_previewMint_initialState() (gas: 23394)
[PASS] test_previewMint_prematureYield() (gas: 43272)
[PASS] test_previewMint_worthlessShares() (gas: 165122)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 62.75ms (59.87ms CPU time)

Ran 4 tests for tests/MaplePool.t.sol:ConvertToExitAssetsTests
[PASS] testFuzz_convertToExitAssets(uint256,uint256,uint256,uint256) (runs: 256, μ: 213123, ~: 213991)
[PASS] testFuzz_convertToExitAssets_zeroSupply(uint256) (runs: 256, μ: 8623, ~: 8623)
[PASS] test_convertToExitAssets() (gas: 234179)
[PASS] test_convertToExitAssets_zeroSupply() (gas: 13689)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 51.35ms (50.22ms CPU time)

Ran 10 tests for tests/MaplePool.t.sol:DepositWithPermitTests
[PASS] testFuzz_depositWithPermit_insufficientBalance(uint256) (runs: 256, μ: 219963, ~: 219374)
[PASS] test_depositWithPermit_badNonce() (gas: 136099)
[PASS] test_depositWithPermit_checkCall() (gas: 154645)
[PASS] test_depositWithPermit_notStakerSignature() (gas: 137934)
[PASS] test_depositWithPermit_pastDeadline() (gas: 107768)
[PASS] test_depositWithPermit_reentrancy() (gas: 235158)
[PASS] test_depositWithPermit_replay() (gas: 241176)
[PASS] test_depositWithPermit_zeroAddress() (gas: 107221)
[PASS] test_depositWithPermit_zeroReceiver() (gas: 160166)
[PASS] test_depositWithPermit_zeroShares() (gas: 140417)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 99.65ms (98.84ms CPU time)

Ran 11 tests for tests/MaplePool.t.sol:MintWithPermitTests
[PASS] testFuzz_mintWithPermit_insufficientBalance(uint256) (runs: 256, μ: 220429, ~: 219846)
[PASS] test_mintWithPermit_badNonce() (gas: 140756)
[PASS] test_mintWithPermit_checkCall() (gas: 155144)
[PASS] test_mintWithPermit_insufficientPermit() (gas: 102455)
[PASS] test_mintWithPermit_notStakerSignature() (gas: 142553)
[PASS] test_mintWithPermit_pastDeadline() (gas: 112367)
[PASS] test_mintWithPermit_reentrancy() (gas: 235659)
[PASS] test_mintWithPermit_replay() (gas: 265582)
[PASS] test_mintWithPermit_zeroAddress() (gas: 111772)
[PASS] test_mintWithPermit_zeroReceiver() (gas: 160539)
[PASS] test_mintWithPermit_zeroShares() (gas: 160740)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 95.51ms (95.89ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:MaxMintTests
[PASS] testFuzz_maxMint_liquidityCap(address,address,uint256,uint256,uint256) (runs: 256, μ: 252289, ~: 252464)
[PASS] test_maxMint_liquidityCap_exchangeRateGtOne() (gas: 313099)
[PASS] test_maxMint_liquidityCap_exchangeRateOneToOne() (gas: 345436)
[PASS] test_maxMint_withPermission() (gas: 262621)
[PASS] test_maxMint_withoutPermission() (gas: 251143)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 73.94ms (74.15ms CPU time)

Ran 7 tests for tests/MaplePoolMintFrontrunTests.t.sol:MaplePoolMintFrontrunTests
[PASS] testFuzz_depositFrontRun_honestOnePercentHarm(uint256) (runs: 256, μ: 6936166, ~: 6936575)
[PASS] testFuzz_depositFrontRun_honestTenPercentHarm(uint256) (runs: 256, μ: 6936236, ~: 6936576)
[PASS] testFuzz_depositFrontRun_theftThwarted(uint256) (runs: 256, μ: 6944703, ~: 6944832)
[PASS] test_depositFrontRun_theft() (gas: 6897048)
[PASS] test_depositFrontRun_theftReverted() (gas: 6845041)
[PASS] test_depositFrontRun_theftThwarted() (gas: 6942417)
[PASS] test_depositFrontRun_zeroShares() (gas: 6885246)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 161.91ms (427.35ms CPU time)

Ran 14 tests for tests/ERC20.t.sol:Pool_ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 96003, ~: 96151)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 374346, ~: 374347)
[PASS] test_domainSeparator() (gas: 12213)
[PASS] test_initialState() (gas: 20879)
[PASS] test_permit_badS() (gas: 36133)
[PASS] test_permit_badV() (gas: 2073388)
[PASS] test_permit_differentSpender() (gas: 64710)
[PASS] test_permit_differentVerifier() (gas: 1192845)
[PASS] test_permit_earlyNonce() (gas: 64929)
[PASS] test_permit_ownerSignerMismatch() (gas: 64888)
[PASS] test_permit_replay() (gas: 102915)
[PASS] test_permit_withExpiry() (gas: 113631)
[PASS] test_permit_zeroAddress() (gas: 64695)
[PASS] test_typehash() (gas: 8906)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 633.87ms (671.56ms CPU time)

Ran 14 tests for tests/ERC20.t.sol:Pool_ERC20Test
[PASS] invariant_metadata() (runs: 256, calls: 128000, reverts: 69561)
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 37040, ~: 37274)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 30279, ~: 856)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 45937, ~: 45937)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 50639, ~: 50158)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 50308, ~: 50211)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 1290133, ~: 1288548)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 59620, ~: 59931)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 82583, ~: 83050)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 515997, ~: 517221)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 519819, ~: 519975)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 508433, ~: 508297)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 489711, ~: 489712)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 498887, ~: 498888)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 3.81s (4.04s CPU time)

Ran 46 test suites in 3.81s (5.46s CPU time): 291 tests passed, 0 failed, 0 skipped (291 total tests)
```

# `pool-permission-manager (v1.0.0)`

```
Running 1 test for tests/unit/Fallback.t.sol:FallbackTests
[PASS] test_fallback_noCode() (gas: 27165)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.22ms

Running 2 tests for tests/unit/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_success() (gas: 2901617)
[PASS] test_setImplementation_unauthorized() (gas: 11612)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.43ms

Running 2 tests for tests/unit/Initialize.t.sol:InitializeTests
[PASS] test_initializer_notGovernor() (gas: 21620)
[PASS] test_initializer_success() (gas: 43137)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.88ms

Running 4 tests for tests/unit/SetPermisionAdmin.t.sol:SetPermissionAdminTests
[PASS] test_setPermissionAdmin_protocolPaused() (gas: 29220)
[PASS] test_setPermissionAdmin_success() (gas: 56673)
[PASS] test_setPermissionAdmin_success_operationalAdmin() (gas: 59970)
[PASS] test_setPermissionAdmin_unauthorized() (gas: 28863)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.35ms

Running 9 tests for tests/unit/ConfigurePool.t.sol:ConfigurePoolTests
[PASS] test_configurePool_invalid() (gas: 40201)
[PASS] test_configurePool_lengthMismatch() (gas: 85219)
[PASS] test_configurePool_noFunctionIds() (gas: 40253)
[PASS] test_configurePool_protocolPaused() (gas: 36780)
[PASS] test_configurePool_public() (gas: 69601)
[PASS] test_configurePool_success_governor() (gas: 190727)
[PASS] test_configurePool_success_operationalAdmin() (gas: 194003)
[PASS] test_configurePool_success_poolDelegate() (gas: 188373)
[PASS] test_configurePool_unauthorized() (gas: 52693)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 2.35ms

Running 8 tests for tests/unit/SetLenderAllowlist.t.sol:SetLenderAllowlistTests
[PASS] test_setLenderAllowlist_batch() (gas: 248434)
[PASS] test_setLenderAllowlist_empty() (gas: 40724)
[PASS] test_setLenderAllowlist_mismatch() (gas: 85836)
[PASS] test_setLenderAllowlist_protocolPaused() (gas: 39426)
[PASS] test_setLenderAllowlist_success_governor() (gas: 162474)
[PASS] test_setLenderAllowlist_success_operationalAdmin() (gas: 165792)
[PASS] test_setLenderAllowlist_success_poolDelegate() (gas: 160095)
[PASS] test_setLenderAllowlist_unauthorized() (gas: 55362)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 3.03ms

Running 8 tests for tests/unit/SetPoolBitmaps.t.sol:SetPoolBitmapsTests
[PASS] test_setPoolBitmaps_batch() (gas: 386761)
[PASS] test_setPoolBitmaps_empty() (gas: 37691)
[PASS] test_setPoolBitmaps_mismatch() (gas: 82725)
[PASS] test_setPoolBitmaps_protocolPaused() (gas: 36527)
[PASS] test_setPoolBitmaps_success_governor() (gas: 160814)
[PASS] test_setPoolBitmaps_success_operationalAdmin() (gas: 164156)
[PASS] test_setPoolBitmaps_success_poolDelegate() (gas: 158504)
[PASS] test_setPoolBitmaps_unauthorized() (gas: 52353)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 2.82ms

Running 8 tests for tests/unit/SetLenderBitmaps.t.sol:SetLenderBitmapsTests
[PASS] test_setLenderBitmaps_batch() (gas: 304199)
[PASS] test_setLenderBitmaps_empty() (gas: 32799)
[PASS] test_setLenderBitmaps_mismatch() (gas: 77936)
[PASS] test_setLenderBitmaps_protocolPaused() (gas: 34012)
[PASS] test_setLenderBitmaps_success() (gas: 153072)
[PASS] test_setLenderBitmaps_success_asGovernor() (gas: 155539)
[PASS] test_setLenderBitmaps_success_asOperationalAdmin() (gas: 158881)
[PASS] test_setLenderBitmaps_unauthorized() (gas: 35877)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 1.83ms

Running 8 tests for tests/unit/SetPoolPermissionLevel.t.sol:SetPoolPermissionLevelTests
[PASS] testFuzz_setPoolPermissionLevel(uint256,uint256) (runs: 256, μ: 73156, ~: 76451)
[PASS] test_setPoolPermissionLevel_invalid() (gas: 34833)
[PASS] test_setPoolPermissionLevel_protocolPaused() (gas: 31346)
[PASS] test_setPoolPermissionLevel_public() (gas: 64124)
[PASS] test_setPoolPermissionLevel_success_governor() (gas: 63625)
[PASS] test_setPoolPermissionLevel_success_operationalAdmin() (gas: 66986)
[PASS] test_setPoolPermissionLevel_success_poolDelegate() (gas: 61246)
[PASS] test_setPoolPermissionLevel_unauthorized() (gas: 47259)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 65.87ms

Running 22 tests for tests/unit/HasPermission.t.sol:HasPermissionTests
[PASS] testFuzz_hasPermission_functionLevel_multiLender_whitelisted(address[]) (runs: 256, μ: 7784417, ~: 8102018)
[PASS] testFuzz_hasPermission_multiLender_private_whitelisted(address,address[],bytes32) (runs: 256, μ: 7478042, ~: 7393336)
[PASS] testFuzz_hasPermission_multiLender_public_(address,address[],bytes32) (runs: 256, μ: 219799, ~: 211551)
[PASS] testFuzz_hasPermission_private_unauthorized(address,address,bytes32) (runs: 256, μ: 17811, ~: 17811)
[PASS] testFuzz_hasPermission_private_whitelisted(address,address,bytes32) (runs: 256, μ: 162929, ~: 162940)
[PASS] testFuzz_hasPermission_public(address,address,bytes32) (runs: 256, μ: 65200, ~: 65200)
[PASS] test_hasPermission_functionLevel_match() (gas: 274433)
[PASS] test_hasPermission_functionLevel_mismatch() (gas: 274488)
[PASS] test_hasPermission_functionLevel_whitelisted() (gas: 190750)
[PASS] test_hasPermission_functionLevel_zeroFunctionBitmap_zeroLenderBitmap() (gas: 70352)
[PASS] test_hasPermission_functionLevel_zeroLenderBitmap() (gas: 193505)
[PASS] test_hasPermission_multiLender_functionLevel(address[]) (runs: 256, μ: 10450621, ~: 10100316)
[PASS] test_hasPermission_multiLender_noLenders() (gas: 173029)
[PASS] test_hasPermission_poolLevel_match() (gas: 254433)
[PASS] test_hasPermission_poolLevel_mismatch() (gas: 254509)
[PASS] test_hasPermission_poolLevel_multiLender_mismatch() (gas: 327610)
[PASS] test_hasPermission_poolLevel_whitelisted() (gas: 190752)
[PASS] test_hasPermission_poolLevel_zeroLenderBitmap() (gas: 173482)
[PASS] test_hasPermission_poolLevel_zeroLenderBitmap_zeroPoolBitmap() (gas: 132950)
[PASS] test_hasPermission_private_unauthorized() (gas: 23479)
[PASS] test_hasPermission_private_whitelisted() (gas: 161411)
[PASS] test_hasPermission_public_success() (gas: 63493)
Test result: ok. 22 passed; 0 failed; 0 skipped; finished in 1.44s
```

# `withdrawal-manager-cyclical (v1.1.0)`

```
Running 3 tests for tests/MapleWithdrawalManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 25056)
[PASS] test_migrate_notFactory() (gas: 19029)
[PASS] test_migrate_success() (gas: 31266)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 9.56ms

Running 4 tests for tests/MapleWithdrawalManager.t.sol:GetCurrentConfigTests
[PASS] test_getCurrentConfig_afterInitialCycle() (gas: 25645)
[PASS] test_getCurrentConfig_beforeInitialCycle() (gas: 25223)
[PASS] test_getCurrentConfig_duringInitialCycle() (gas: 25668)
[PASS] test_getCurrentConfig_onInitialCycleStart() (gas: 25451)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 9.74ms

Running 2 tests for tests/MapleWithdrawalManager.t.sol:ProcessExitWithMultipleUsers
[PASS] test_partialLiquidity_fullMoveShares() (gas: 510389)
[PASS] test_partialLiquidity_partialMoveShares_partialRemoveShares() (gas: 404772)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 10.70ms

Running 8 tests for tests/MapleWithdrawalManager.t.sol:AddSharesTests
[PASS] test_addShares_createRequest() (gas: 178087)
[PASS] test_addShares_delayedUpdate() (gas: 228940)
[PASS] test_addShares_emptyRequest() (gas: 28713)
[PASS] test_addShares_failedTransfer() (gas: 106813)
[PASS] test_addShares_increaseRequest() (gas: 217364)
[PASS] test_addShares_notPoolManager() (gas: 18962)
[PASS] test_addShares_pendingRequest() (gas: 157383)
[PASS] test_addShares_refreshRequest() (gas: 226963)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 11.23ms

Running 2 tests for tests/MapleWithdrawalManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 18633)
[PASS] test_setImplementation_success() (gas: 32125)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 9.49ms

Running 4 tests for tests/MapleWithdrawalManager.t.sol:GetCurrentCycleIdTests
[PASS] test_getCurrentCycleId_afterInitialCycle() (gas: 24420)
[PASS] test_getCurrentCycleId_beforeInitialCycle() (gas: 21377)
[PASS] test_getCurrentCycleId_duringInitialCycle() (gas: 24443)
[PASS] test_getCurrentCycleId_onInitialCycleStart() (gas: 23648)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.95ms

Running 8 tests for tests/MapleWithdrawalManager.t.sol:RemoveSharesTests
[PASS] test_removeShares_cancelRequest() (gas: 172269)
[PASS] test_removeShares_decreaseRequest() (gas: 217114)
[PASS] test_removeShares_delayedUpdate() (gas: 219091)
[PASS] test_removeShares_failedTransfer() (gas: 152811)
[PASS] test_removeShares_notPoolManager() (gas: 19238)
[PASS] test_removeShares_pendingRequest() (gas: 157676)
[PASS] test_removeShares_sharesUnderflow() (gas: 157549)
[PASS] test_removeShares_zeroShares() (gas: 157534)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 13.74ms

Running 5 tests for tests/MapleWithdrawalManager.t.sol:UpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 112306)
[PASS] test_upgrade_notScheduled() (gas: 40707)
[PASS] test_upgrade_notSecurityAdmin() (gas: 102670)
[PASS] test_upgrade_success() (gas: 91571)
[PASS] test_upgrade_upgradeFailed() (gas: 83463)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 2.79ms

Running 10 tests for tests/MapleWithdrawalManager.t.sol:ProcessExitTests
[PASS] test_processExit_fullWithdrawal_fullLiquidity() (gas: 244789)
[PASS] test_processExit_fullWithdrawal_noLiquidity() (gas: 254594)
[PASS] test_processExit_fullWithdrawal_partialLiquidity() (gas: 324523)
[PASS] test_processExit_lostShares() (gas: 244790)
[PASS] test_processExit_noRequest() (gas: 26539)
[PASS] test_processExit_notPoolManager() (gas: 19392)
[PASS] test_processExit_postWindow() (gas: 158178)
[PASS] test_processExit_preWindow() (gas: 158117)
[PASS] test_processExit_requestedSharedGtLocked() (gas: 140407)
[PASS] test_processExit_requestedSharedLtLocked() (gas: 140386)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 4.63ms

Running 8 tests for tests/MapleWithdrawalManagerFactory.t.sol:MapleWithdrawalManagerFactoryTests
[PASS] testFail_createInstance_collision() (gas: 8937393460516737262)
[PASS] test_createInstance_invalidStart() (gas: 163686)
[PASS] test_createInstance_notPoolDeployer() (gas: 262865)
[PASS] test_createInstance_safeCastOutOfBounds() (gas: 541945)
[PASS] test_createInstance_success() (gas: 256816)
[PASS] test_createInstance_windowOutOfBounds() (gas: 165776)
[PASS] test_createInstance_zeroPool() (gas: 163564)
[PASS] test_createInstance_zeroWindow() (gas: 165708)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 2.80ms

Running 5 tests for tests/MapleWithdrawalManager.t.sol:LockedLiquidityTests
[PASS] test_lockedLiquidity_afterWindow() (gas: 26955)
[PASS] test_lockedLiquidity_beforeWindow() (gas: 26905)
[PASS] test_lockedLiquidity_duringWindow() (gas: 59852)
[PASS] test_lockedLiquidity_duringWindowWithdrawal() (gas: 129235)
[PASS] test_lockedLiquidity_unrealizedLosses() (gas: 156571)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 14.42ms

Running 11 tests for tests/MapleWithdrawalManager.t.sol:SetExitConfigTests
[PASS] test_setExitConfig_addConfig() (gas: 115939)
[PASS] test_setExitConfig_complexScenario() (gas: 303873)
[PASS] test_setExitConfig_cycleDurationCastOob() (gas: 163622)
[PASS] test_setExitConfig_failWhenPaused() (gas: 121460)
[PASS] test_setExitConfig_governor() (gas: 102620)
[PASS] test_setExitConfig_notAuthorized() (gas: 43993)
[PASS] test_setExitConfig_operationalAdmin() (gas: 105849)
[PASS] test_setExitConfig_poolDelegate() (gas: 99349)
[PASS] test_setExitConfig_updateConfig() (gas: 220406)
[PASS] test_setExitConfig_windowOutOfBounds() (gas: 40308)
[PASS] test_setExitConfig_zeroWindow() (gas: 40328)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 3.58ms

Running 2 tests for tests/MapleWithdrawalManager.t.sol:ViewFunctionTests
[PASS] testFuzz_previewWithdraw_alwaysReturnsZero(address,uint256) (runs: 256, μ: 12538, ~: 12538)
[PASS] test_noLockedShares_isInExitWindowCheck() (gas: 22853)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 33.01ms
```

# `withdrawal-manager-queue (v1.0.0)`

```
Running 3 tests for tests/unit/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30793)
[PASS] test_setImplementation_protocolPaused() (gas: 36813)
[PASS] test_setImplementation_success() (gas: 41813)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 9.90ms

Running 4 tests for tests/unit/Migrate.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 34759)
[PASS] test_migrate_notFactory() (gas: 31232)
[PASS] test_migrate_protocolPaused() (gas: 37232)
[PASS] test_migrate_success() (gas: 41042)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 10.02ms

Running 5 tests for tests/unit/CreateInstance.t.sol:CreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 312370)
[PASS] test_createInstance_invalidFactory() (gas: 185866)
[PASS] test_createInstance_invalidInstance() (gas: 187046)
[PASS] test_createInstance_success() (gas: 311896)
[PASS] test_createInstance_zeroPool() (gas: 162769)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 11.05ms

Running 7 tests for tests/unit/RemoveShares.t.sol:RemoveSharesTests
[PASS] test_removeShares_decreaseOnly() (gas: 157647)
[PASS] test_removeShares_emptyRequest() (gas: 24196)
[PASS] test_removeShares_failedTransfer() (gas: 163875)
[PASS] test_removeShares_notInQueue() (gas: 28817)
[PASS] test_removeShares_notPoolManager() (gas: 19305)
[PASS] test_removeShares_success_cancelRequest() (gas: 171503)
[PASS] test_removeShares_success_decreaseRequest() (gas: 208298)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 11.30ms

Running 7 tests for tests/unit/AddShares.t.sol:AddSharesTests
[PASS] test_addShares_alreadyInQueue() (gas: 166698)
[PASS] test_addShares_emptyRequest() (gas: 21662)
[PASS] test_addShares_failedTransfer() (gas: 126244)
[PASS] test_addShares_newRequestAddedToQueue() (gas: 169729)
[PASS] test_addShares_newRequestAddedToQueue_manual() (gas: 194158)
[PASS] test_addShares_notPoolManager() (gas: 18962)
[PASS] test_addShares_success() (gas: 261460)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 11.88ms

Running 4 tests for tests/unit/PreviewRedeem.t.sol:PreviewRedeemTests
[PASS] test_previewRedeem_complete() (gas: 72634)
[PASS] test_previewRedeem_notProcessed() (gas: 21030)
[PASS] test_previewRedeem_partial() (gas: 89501)
[PASS] test_previewRedeem_tooManyShares() (gas: 44076)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.21ms

Running 4 tests for tests/unit/SetManualWithdrawal.t.sol:SetManualWithdrawalTests
[PASS] test_setManualWithdrawal_existingRequest() (gas: 112371)
[PASS] test_setManualWithdrawal_notProtocolAdmin() (gas: 46667)
[PASS] test_setManualWithdrawal_protocolPaused() (gas: 37011)
[PASS] test_setManualWithdrawal_success() (gas: 75326)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.51ms

Running 6 tests for tests/unit/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 125130)
[PASS] test_upgrade_notScheduled() (gas: 43889)
[PASS] test_upgrade_notSecurityAdmin() (gas: 116894)
[PASS] test_upgrade_protocolPaused() (gas: 35507)
[PASS] test_upgrade_success() (gas: 101123)
[PASS] test_upgrade_upgradeFailed() (gas: 92992)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 13.14ms

Running 5 tests for tests/unit/RemoveRequest.t.sol:RemoveRequestTests
[PASS] test_removeRequest_failedTransfer() (gas: 183885)
[PASS] test_removeRequest_notInQueue() (gas: 44932)
[PASS] test_removeRequest_notProtocolAdmin() (gas: 46494)
[PASS] test_removeRequest_protocolPaused() (gas: 36834)
[PASS] test_removeRequest_success() (gas: 189429)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.33ms

Running 1 test for tests/unit/ProcessRedemptions.t.sol:ComplexRedemptionTests
[PASS] test_processRedemptions_complex() (gas: 562489)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 2.88ms

Running 15 tests for tests/unit/ProcessRedemptions.t.sol:ProcessRedemptionsTests
[PASS] test_processRedemptions_automatic_complete() (gas: 148607)
[PASS] test_processRedemptions_automatic_overkill() (gas: 161619)
[PASS] test_processRedemptions_automatic_partial() (gas: 205883)
[PASS] test_processRedemptions_bot() (gas: 86008)
[PASS] test_processRedemptions_governor() (gas: 77480)
[PASS] test_processRedemptions_lowLiquidity() (gas: 88858)
[PASS] test_processRedemptions_manual_complete() (gas: 178327)
[PASS] test_processRedemptions_manual_overkill() (gas: 192868)
[PASS] test_processRedemptions_manual_partial() (gas: 243881)
[PASS] test_processRedemptions_multiple() (gas: 226985)
[PASS] test_processRedemptions_notRedeemer() (gas: 59530)
[PASS] test_processRedemptions_operationalAdmin() (gas: 80691)
[PASS] test_processRedemptions_poolDelegate() (gas: 74210)
[PASS] test_processRedemptions_protocolPaused() (gas: 36680)
[PASS] test_processRedemptions_zeroShares() (gas: 45553)
Test result: ok. 15 passed; 0 failed; 0 skipped; finished in 16.23ms

Running 9 tests for tests/unit/ProcessExit.t.sol:ProcessExitTests
[PASS] test_processExit_automatic() (gas: 50885)
[PASS] test_processExit_manual_complete() (gas: 196490)
[PASS] test_processExit_manual_partial() (gas: 243470)
[PASS] test_processExit_noShares() (gas: 46558)
[PASS] test_processExit_notEnoughLiquidity() (gas: 200019)
[PASS] test_processExit_notPoolManager() (gas: 21427)
[PASS] test_processExit_tooManyShares() (gas: 50874)
[PASS] test_processExit_tooManyShares_notProcessed() (gas: 127390)
[PASS] test_processExit_transferFail() (gas: 212533)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 30.67ms

Running 4 tests for tests/unit/ViewFunctions.t.sol:ViewFunctionsTests
[PASS] testFuzz_isInExitWindow(address) (runs: 256, μ: 11800, ~: 11800)
[PASS] test_lockedLiquidity() (gas: 10872)
[PASS] test_lockedShares(address,uint256) (runs: 256, μ: 36036, ~: 36347)
[PASS] test_previewWithdraw(address,uint256) (runs: 256, μ: 12581, ~: 12581)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 30.58ms

Running 1 test for tests/fuzz/RemoveSharesFuzz.t.sol:RemoveSharesFuzzTests
[PASS] testFuzz_removeShares(address[50],uint256[50],uint256[50]) (runs: 256, μ: 418428, ~: 392719)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 225.57ms

Running 2 tests for tests/integration/EndToEndTests.t.sol:EndToEndTests
[PASS] testFuzz_fullFLow_fixedExchangeRate(address[10],bool[10],uint256[10]) (runs: 256, μ: 1914629, ~: 1918432)
[PASS] test_e2e_fullFlow() (gas: 616781)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 410.03ms

Running 1 test for tests/fuzz/AddSharesFuzz.t.sol:AddSharesFuzzTests
[PASS] testFuzz_addShares(uint256[50],address[50]) (runs: 256, μ: 5034855, ~: 5957943)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.44s
```

# `maple-strategies (v1.0.0)`

```
Ran 6 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyImpairStrategyTests
[PASS] test_impairStrategy_failIfAlreadyImpaired() (gas: 67257)
[PASS] test_impairStrategy_failIfNotProtocolAdmin() (gas: 146072)
[PASS] test_impairStrategy_failReentrancy() (gas: 20695)
[PASS] test_impairStrategy_failWhenPaused() (gas: 38844)
[PASS] test_impairStrategy_successWhenActive() (gas: 68246)
[PASS] test_impairStrategy_successWhenInactive() (gas: 68226)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 1.53ms (264.71µs CPU time)

Ran 3 tests for tests/unit/SetImplementation.t.sol:MapleAaveStrategySetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30369)
[PASS] test_setImplementation_protocolPaused() (gas: 36338)
[PASS] test_setImplementation_success() (gas: 44641)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.53ms (114.83µs CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MapleAaveStrategyMigrateTests
[PASS] test_migrate_internalFailure() (gas: 36808)
[PASS] test_migrate_notFactory() (gas: 30803)
[PASS] test_migrate_protocolPaused() (gas: 36774)
[PASS] test_migrate_success() (gas: 43987)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.68ms (122.33µs CPU time)

Ran 4 tests for tests/unit/AaveStrategy.t.sol:ClaimRewardsTests
[PASS] test_claimRewards_failIfNotProtocolAdmin() (gas: 163028)
[PASS] test_claimRewards_failReentrancy() (gas: 30962)
[PASS] test_claimRewards_failWhenPaused() (gas: 49132)
[PASS] test_claimRewards_success() (gas: 82923)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.22ms (293.58µs CPU time)

Ran 6 tests for tests/unit/CreateInstance.t.sol:MapleBasicStrategyCreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 376652)
[PASS] test_createInstance_invalidFactory() (gas: 180720)
[PASS] test_createInstance_invalidInstance() (gas: 181774)
[PASS] test_createInstance_invalidStrategyAsset() (gas: 599193)
[PASS] test_createInstance_success() (gas: 383009)
[PASS] test_createInstance_zeroPool() (gas: 157484)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 1.99ms (641.75µs CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MapleBasicStrategyMigrateTests
[PASS] test_migrate_internalFailure() (gas: 36808)
[PASS] test_migrate_notFactory() (gas: 30803)
[PASS] test_migrate_protocolPaused() (gas: 36774)
[PASS] test_migrate_success() (gas: 43943)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.30ms (116.38µs CPU time)

Ran 10 tests for tests/unit/CreateInstance.t.sol:MapleSkyStrategyCreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 500588)
[PASS] test_createInstance_invalidFactory() (gas: 194631)
[PASS] test_createInstance_invalidGemPSM() (gas: 210072)
[PASS] test_createInstance_invalidInstance() (gas: 195685)
[PASS] test_createInstance_invalidPSM() (gas: 163389)
[PASS] test_createInstance_invalidSavingsUsds() (gas: 163267)
[PASS] test_createInstance_invalidUsdsPSM() (gas: 213133)
[PASS] test_createInstance_nonAuthorizedPSM() (gas: 194587)
[PASS] test_createInstance_success() (gas: 512632)
[PASS] test_createInstance_zeroPool() (gas: 163233)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 2.50ms (1.25ms CPU time)

Ran 3 tests for tests/unit/SetImplementation.t.sol:MapleSkyStrategySetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30369)
[PASS] test_setImplementation_protocolPaused() (gas: 36338)
[PASS] test_setImplementation_success() (gas: 44598)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.47ms (88.42µs CPU time)

Ran 14 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyAccrueFeesTests
[PASS] test_accrueFees_minimumGain_realisticFeeRate() (gas: 103409)
[PASS] test_accrueFees_minimumGain_zeroFeeRate() (gas: 80876)
[PASS] test_accrueFees_minimumLoss_realisticFeeRate() (gas: 102785)
[PASS] test_accrueFees_minimumLoss_zeroFeeRate() (gas: 80911)
[PASS] test_accrueFees_normalGain_maximumFeeRate() (gas: 124192)
[PASS] test_accrueFees_normalGain_minimumFeeRate() (gas: 124393)
[PASS] test_accrueFees_normalGain_realisticFeeRate() (gas: 126714)
[PASS] test_accrueFees_normalGain_zeroFeeRate() (gas: 82997)
[PASS] test_accrueFees_normalLoss_realisticFeeRate() (gas: 104842)
[PASS] test_accrueFees_normalLoss_zeroFeeRate() (gas: 82943)
[PASS] test_accrueFees_totalLoss_realisticFeeRate() (gas: 82704)
[PASS] test_accrueFees_totalLoss_zeroFeeRate() (gas: 60806)
[PASS] test_accrueFees_unfundedStrategy_realisticFeeRate() (gas: 60784)
[PASS] test_accrueFees_unfundedStrategy_zeroFeeRate() (gas: 38954)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 3.04ms (1.85ms CPU time)

Ran 6 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyAccrueFeesTests
[PASS] test_accrueFees_strategyFeeOneHundredPercent() (gas: 212337)
[PASS] test_accrueFees_strategyFeeRoundedDown() (gas: 127833)
[PASS] test_accrueFees_totalAssetsDecreased() (gas: 84411)
[PASS] test_accrueFees_totalAssetsIncreased() (gas: 211667)
[PASS] test_accrueFees_zeroStrategyFeeRateAndNoChangeInTotalAssets() (gas: 43870)
[PASS] test_accrueFees_zeroStrategyFeeRate_totalAssetsIncreased() (gas: 111942)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.86ms (1.25ms CPU time)

Ran 3 tests for tests/unit/SetImplementation.t.sol:MapleBasicStrategySetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30369)
[PASS] test_setImplementation_protocolPaused() (gas: 36338)
[PASS] test_setImplementation_success() (gas: 44662)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.96ms (116.71µs CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MapleSkyStrategyMigrateTests
[PASS] test_migrate_internalFailure() (gas: 36830)
[PASS] test_migrate_notFactory() (gas: 30825)
[PASS] test_migrate_protocolPaused() (gas: 36796)
[PASS] test_migrate_success() (gas: 44053)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.34ms (115.21µs CPU time)

Ran 8 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyReactivateStrategyTests
[PASS] test_reactivateStrategy_failIfAlreadyActive() (gas: 45795)
[PASS] test_reactivateStrategy_failIfNotProtocolAdmin() (gas: 120645)
[PASS] test_reactivateStrategy_failReentrancy() (gas: 21136)
[PASS] test_reactivateStrategy_failWhenPaused() (gas: 39306)
[PASS] test_reactivateStrategy_successWhenImpaired_withAccountingUpdate() (gas: 65040)
[PASS] test_reactivateStrategy_successWhenImpaired_withoutAccountingUpdate() (gas: 53941)
[PASS] test_reactivateStrategy_successWhenInactive_withAccountingUpdate() (gas: 65041)
[PASS] test_reactivateStrategy_successWhenInactive_withoutAccountingUpdate() (gas: 53919)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 1.80ms (351.71µs CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:MapleBasicStrategyUpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 123486)
[PASS] test_upgrade_notScheduled() (gas: 43135)
[PASS] test_upgrade_notSecurityAdmin() (gas: 117137)
[PASS] test_upgrade_protocolPaused() (gas: 35073)
[PASS] test_upgrade_success() (gas: 99209)
[PASS] test_upgrade_upgradeFailed() (gas: 90146)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 1.63ms (488.88µs CPU time)

Ran 6 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyDeactivateStrategyTests
[PASS] test_deactivateStrategy_failIfAlreadyInactive() (gas: 67324)
[PASS] test_deactivateStrategy_failIfNotProtocolAdmin() (gas: 146143)
[PASS] test_deactivateStrategy_failReentrancy() (gas: 20739)
[PASS] test_deactivateStrategy_failWhenPaused() (gas: 38954)
[PASS] test_deactivateStrategy_successWhenActive() (gas: 68225)
[PASS] test_deactivateStrategy_successWhenImpaired() (gas: 68291)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 1.30ms (242.92µs CPU time)

Ran 8 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyReactivateStrategyTests
[PASS] test_reactivateStrategy_failIfAlreadyActive() (gas: 42283)
[PASS] test_reactivateStrategy_failIfNotProtocolAdmin() (gas: 110641)
[PASS] test_reactivateStrategy_failReentrancy() (gas: 17624)
[PASS] test_reactivateStrategy_failWhenPaused() (gas: 34292)
[PASS] test_reactivateStrategy_successWhenImpaired_withAccountingUpdate() (gas: 64471)
[PASS] test_reactivateStrategy_successWhenImpaired_withoutAccountingUpdate() (gas: 49516)
[PASS] test_reactivateStrategy_successWhenInactive_withAccountingUpdate() (gas: 64472)
[PASS] test_reactivateStrategy_successWhenInactive_withoutAccountingUpdate() (gas: 49494)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 2.08ms (827.37µs CPU time)

Ran 7 tests for tests/unit/CreateInstance.t.sol:MapleAaveStrategyCreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 31121)
[PASS] test_createInstance_invalidPoolManagerFactory() (gas: 191600)
[PASS] test_createInstance_invalidPoolManagerInstance() (gas: 192672)
[PASS] test_createInstance_success() (gas: 416911)
[PASS] test_createInstance_underlyingAssetMismatch() (gas: 203040)
[PASS] test_createInstance_zeroAaveToken() (gas: 162905)
[PASS] test_createInstance_zeroPool() (gas: 162848)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.67ms (574.88µs CPU time)

Ran 8 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyFundTests
[PASS] test_fund_failIfImpaired() (gas: 64806)
[PASS] test_fund_failIfInactive() (gas: 64806)
[PASS] test_fund_failIfInvalidStrategyVault() (gas: 54676)
[PASS] test_fund_failIfNonManager() (gas: 45365)
[PASS] test_fund_failReentrancy() (gas: 4117637)
[PASS] test_fund_failWhenPaused() (gas: 34452)
[PASS] test_fund_successWithPoolDelegate() (gas: 115334)
[PASS] test_fund_successWithStrategyManager() (gas: 118479)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 5.03ms (901.62µs CPU time)

Ran 7 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyAccrueFeesTests
[PASS] test_accrueFees_strategyFeeOneHundredPercent() (gas: 127469)
[PASS] test_accrueFees_strategyFeeRoundedDown() (gas: 100949)
[PASS] test_accrueFees_totalAssetsDecreased() (gas: 63052)
[PASS] test_accrueFees_totalAssetsIncreased() (gas: 124738)
[PASS] test_accrueFees_zeroStrategyFeeRateAndNoChangeInTotalAssets() (gas: 30763)
[PASS] test_accrueFees_zeroStrategyFeeRate_totalAssetsIncreased() (gas: 84308)
[PASS] test_accrueFees_zeroStrategyFeeRate_totalAssetsUnchanged() (gas: 105621)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 2.27ms (1.06ms CPU time)

Ran 10 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyWithdrawFromStrategyTests
[PASS] test_withdrawFromStrategy_failIfLowAssets() (gas: 67573)
[PASS] test_withdrawFromStrategy_failIfNotStrategyManager() (gas: 47647)
[PASS] test_withdrawFromStrategy_failIfSlippage() (gas: 75435)
[PASS] test_withdrawFromStrategy_failIfZeroAssets() (gas: 39461)
[PASS] test_withdrawFromStrategy_failReentrancy() (gas: 3223776)
[PASS] test_withdrawFromStrategy_failWhenPaused() (gas: 36715)
[PASS] test_withdrawFromStrategy_successWhenImpaired() (gas: 95228)
[PASS] test_withdrawFromStrategy_successWhenInactive() (gas: 95229)
[PASS] test_withdrawFromStrategy_successWithPoolDelegate() (gas: 95705)
[PASS] test_withdrawFromStrategy_successWithStrategyManager() (gas: 97283)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 2.20ms (953.21µs CPU time)

Ran 9 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyWithdrawFromStrategyTests
[PASS] test_withdrawFromStrategy_failIfLowAssets() (gas: 65556)
[PASS] test_withdrawFromStrategy_failIfNonManager() (gas: 52372)
[PASS] test_withdrawFromStrategy_failIfZeroAssets() (gas: 44142)
[PASS] test_withdrawFromStrategy_failReentrancy() (gas: 23224)
[PASS] test_withdrawFromStrategy_failWhenPaused() (gas: 41374)
[PASS] test_withdrawFromStrategy_successWhenImpaired() (gas: 102764)
[PASS] test_withdrawFromStrategy_successWhenInactive() (gas: 102765)
[PASS] test_withdrawFromStrategy_successWithPoolDelegate() (gas: 94779)
[PASS] test_withdrawFromStrategy_successWithStrategyManager() (gas: 97968)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 5.24ms (1.83ms CPU time)

Ran 9 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategySetStrategyFeeRateTests
[PASS] test_setStrategyFeeRate_failIfImpaired() (gas: 64320)
[PASS] test_setStrategyFeeRate_failIfInactive() (gas: 64277)
[PASS] test_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 162473)
[PASS] test_setStrategyFeeRate_failInvalidStrategyFeeRate() (gas: 43274)
[PASS] test_setStrategyFeeRate_failReentrancy() (gas: 17739)
[PASS] test_setStrategyFeeRate_failWhenPaused() (gas: 34452)
[PASS] test_setStrategyFeeRate_nonZeroPriorFeeRate_totalAssetsIncreased() (gas: 172594)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRateAndTotalAssets() (gas: 87053)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRate_totalAssetsIncreased() (gas: 158373)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 2.20ms (1.02ms CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:MapleSkyStrategyUpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 123510)
[PASS] test_upgrade_notScheduled() (gas: 43179)
[PASS] test_upgrade_notSecurityAdmin() (gas: 117161)
[PASS] test_upgrade_protocolPaused() (gas: 35117)
[PASS] test_upgrade_success() (gas: 99103)
[PASS] test_upgrade_upgradeFailed() (gas: 90126)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 3.54ms (1.25ms CPU time)

Ran 8 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyReactivateStrategyTests
[PASS] test_reactivateStrategy_failIfAlreadyActive() (gas: 42327)
[PASS] test_reactivateStrategy_failIfNotProtocolAdmin() (gas: 110729)
[PASS] test_reactivateStrategy_failReentrancy() (gas: 17646)
[PASS] test_reactivateStrategy_failWhenPaused() (gas: 34292)
[PASS] test_reactivateStrategy_successWhenImpaired_withAccountingUpdate() (gas: 79809)
[PASS] test_reactivateStrategy_successWhenImpaired_withoutAccountingUpdate() (gas: 49537)
[PASS] test_reactivateStrategy_successWhenInactive_withAccountingUpdate() (gas: 79810)
[PASS] test_reactivateStrategy_successWhenInactive_withoutAccountingUpdate() (gas: 49515)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 2.41ms (979.59µs CPU time)

Ran 18 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategySetStrategyFeeRateTests
[PASS] test_setStrategyFeeRate_failIfImpaired() (gas: 69851)
[PASS] test_setStrategyFeeRate_failIfInactive() (gas: 69851)
[PASS] test_setStrategyFeeRate_failReentrancy() (gas: 23203)
[PASS] test_setStrategyFeeRate_failWhenInvalidStrategyFeeRate() (gas: 46019)
[PASS] test_setStrategyFeeRate_failWhenNotAdmin() (gas: 51893)
[PASS] test_setStrategyFeeRate_failWhenPaused() (gas: 41440)
[PASS] test_setStrategyFeeRate_normalGain_1e6() (gas: 154092)
[PASS] test_setStrategyFeeRate_normalGain_realisticFeeRate() (gas: 156636)
[PASS] test_setStrategyFeeRate_normalGain_zeroFeeRate() (gas: 146374)
[PASS] test_setStrategyFeeRate_normalLoss_realisticFeeRate() (gas: 148340)
[PASS] test_setStrategyFeeRate_normalLoss_zeroFeeRate() (gas: 146389)
[PASS] test_setStrategyFeeRate_successWithGovernor() (gas: 88612)
[PASS] test_setStrategyFeeRate_successWithOperationalAdmin() (gas: 92897)
[PASS] test_setStrategyFeeRate_successWithPoolDelegate() (gas: 84082)
[PASS] test_setStrategyFeeRate_totalLoss_realisticFeeRate() (gas: 103941)
[PASS] test_setStrategyFeeRate_totalLoss_zeroFeeRate() (gas: 103940)
[PASS] test_setStrategyFeeRate_unfundedStrategy_realisticFeeRate() (gas: 103964)
[PASS] test_setStrategyFeeRate_unfundedStrategy_zeroFeeRate() (gas: 101989)
Suite result: ok. 18 passed; 0 failed; 0 skipped; finished in 4.21ms (2.13ms CPU time)

Ran 6 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyDeactivateStrategyTests
[PASS] test_deactivateStrategy_failIfAlreadyInactive() (gas: 63815)
[PASS] test_deactivateStrategy_failIfNotProtocolAdmin() (gas: 138149)
[PASS] test_deactivateStrategy_failReentrancy() (gas: 17230)
[PASS] test_deactivateStrategy_failWhenPaused() (gas: 33943)
[PASS] test_deactivateStrategy_successWhenActive() (gas: 64301)
[PASS] test_deactivateStrategy_successWhenImpaired() (gas: 64367)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 4.31ms (1.89ms CPU time)

Ran 6 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyImpairStrategyTests
[PASS] test_impairStrategy_failIfAlreadyImpaired() (gas: 63814)
[PASS] test_impairStrategy_failIfNotProtocolAdmin() (gas: 138220)
[PASS] test_impairStrategy_failReentrancy() (gas: 17230)
[PASS] test_impairStrategy_failWhenPaused() (gas: 33855)
[PASS] test_impairStrategy_successWhenActive() (gas: 64343)
[PASS] test_impairStrategy_successWhenInactive() (gas: 64323)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 1.91ms (601.92µs CPU time)

Ran 15 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyViewFunctionTests
[PASS] test_aavePool() (gas: 18336)
[PASS] test_aaveToken() (gas: 18250)
[PASS] test_factory() (gas: 18373)
[PASS] test_fundsAsset() (gas: 18295)
[PASS] test_globals() (gas: 23964)
[PASS] test_governor() (gas: 29640)
[PASS] test_implementation() (gas: 16394)
[PASS] test_locked() (gas: 15953)
[PASS] test_pool() (gas: 18296)
[PASS] test_poolDelegate() (gas: 23869)
[PASS] test_poolManager() (gas: 18315)
[PASS] test_securityAdmin() (gas: 29589)
[PASS] test_strategyState() (gas: 16092)
[PASS] test_strategyType() (gas: 15198)
[PASS] test_treasury() (gas: 29547)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 1.20ms (205.63µs CPU time)

Ran 9 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyFundStrategyTests
[PASS] test_fund_failIfImpaired() (gas: 65132)
[PASS] test_fund_failIfInactive() (gas: 65110)
[PASS] test_fund_failIfNotStrategyManager() (gas: 45779)
[PASS] test_fund_failInvalidStrategyVault() (gas: 52825)
[PASS] test_fund_failMinimumSharesOut() (gas: 64838)
[PASS] test_fund_failReentrancy() (gas: 18111)
[PASS] test_fund_failWhenPaused() (gas: 34844)
[PASS] test_fund_successWithPoolDelegate() (gas: 140100)
[PASS] test_fund_successWithStrategyManager() (gas: 147995)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 2.93ms (738.84µs CPU time)

Ran 9 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyWithdrawTests
[PASS] test_withdrawFromStrategy_failIfLowAssets() (gas: 71686)
[PASS] test_withdrawFromStrategy_failIfZeroAssets() (gas: 39172)
[PASS] test_withdraw_failReentrancy() (gas: 4119499)
[PASS] test_withdraw_failsIfNotStrategyManager() (gas: 47271)
[PASS] test_withdraw_failsIfProtocolPaused() (gas: 41724)
[PASS] test_withdraw_successWhenImpaired() (gas: 111812)
[PASS] test_withdraw_successWhenInactive() (gas: 111791)
[PASS] test_withdraw_successWithPoolDelegate() (gas: 119429)
[PASS] test_withdraw_successWithStrategyManager() (gas: 124099)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 2.50ms (1.48ms CPU time)

Ran 3 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyAssetsUnderManagementTests
[PASS] testFuzz_assetsUnderManagement_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 107353, ~: 108233)
[PASS] testFuzz_assetsUnderManagement_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 127373, ~: 128155)
[PASS] testFuzz_assetsUnderManagement_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 120883, ~: 121094)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 71.93ms (179.13ms CPU time)

Ran 6 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyImpairStrategyTests
[PASS] test_impairStrategy_failIfAlreadyImpaired() (gas: 63726)
[PASS] test_impairStrategy_failIfNotProtocolAdmin() (gas: 138008)
[PASS] test_impairStrategy_failReentrancy() (gas: 17164)
[PASS] test_impairStrategy_failWhenPaused() (gas: 33811)
[PASS] test_impairStrategy_successWhenActive() (gas: 64300)
[PASS] test_impairStrategy_successWhenInactive() (gas: 64280)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 140.70ms (1.01ms CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:MapleAaveStrategyUpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 123662)
[PASS] test_upgrade_notScheduled() (gas: 43179)
[PASS] test_upgrade_notSecurityAdmin() (gas: 117313)
[PASS] test_upgrade_protocolPaused() (gas: 35117)
[PASS] test_upgrade_success() (gas: 106347)
[PASS] test_upgrade_upgradeFailed() (gas: 90410)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 146.20ms (540.17µs CPU time)

Ran 6 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyDeactivateStrategyTests
[PASS] test_deactivateStrategy_failIfAlreadyInactive() (gas: 63881)
[PASS] test_deactivateStrategy_failIfNotProtocolAdmin() (gas: 138290)
[PASS] test_deactivateStrategy_failReentrancy() (gas: 17274)
[PASS] test_deactivateStrategy_failWhenPaused() (gas: 33965)
[PASS] test_deactivateStrategy_successWhenActive() (gas: 64322)
[PASS] test_deactivateStrategy_successWhenImpaired() (gas: 64388)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 143.14ms (621.29µs CPU time)

Ran 23 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyViewFunctionTests
[PASS] testFuzz_assetsUnderManagement_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 107360, ~: 108160)
[PASS] testFuzz_assetsUnderManagement_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 127219, ~: 127173)
[PASS] testFuzz_assetsUnderManagement_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 116922, ~: 117281)
[PASS] testFuzz_unrealizedLosses_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 97000, ~: 97297)
[PASS] testFuzz_unrealizedLosses_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 127497, ~: 128187)
[PASS] testFuzz_unrealizedLosses_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 116817, ~: 117152)
[PASS] test_assetsUnderManagement_strategyFundedAndZeroFee() (gas: 57776)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndLoss() (gas: 100455)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndTotalAssetsIncreased() (gas: 101254)
[PASS] test_assetsUnderManagement_strategyNotFunded() (gas: 27697)
[PASS] test_factory() (gas: 13397)
[PASS] test_fundsAsset() (gas: 13297)
[PASS] test_globals() (gas: 19032)
[PASS] test_governor() (gas: 24641)
[PASS] test_implementation() (gas: 13440)
[PASS] test_locked() (gas: 10955)
[PASS] test_pool() (gas: 13365)
[PASS] test_poolDelegate() (gas: 18959)
[PASS] test_poolManager() (gas: 13317)
[PASS] test_securityAdmin() (gas: 24591)
[PASS] test_strategyType() (gas: 10304)
[PASS] test_strategyVault() (gas: 13384)
[PASS] test_treasury() (gas: 24724)
Suite result: ok. 23 passed; 0 failed; 0 skipped; finished in 150.59ms (770.69ms CPU time)

Ran 3 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyUnrealizedLossesTests
[PASS] testFuzz_unrealizedLosses_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 100928, ~: 101110)
[PASS] testFuzz_unrealizedLosses_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 129828, ~: 130651)
[PASS] testFuzz_unrealizedLosses_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 120832, ~: 121010)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 186.23ms (172.38ms CPU time)

Ran 8 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategySetPsmTests
[PASS] test_setPsm_failIfInvalidGem() (gas: 57266)
[PASS] test_setPsm_failIfInvalidUsds() (gas: 60347)
[PASS] test_setPsm_failIfNotProtocolAdmin() (gas: 315298)
[PASS] test_setPsm_failIfNotValidInstance() (gas: 65450)
[PASS] test_setPsm_failIfZeroAddress() (gas: 38761)
[PASS] test_setPsm_failReentrancy() (gas: 19844)
[PASS] test_setPsm_failWhenPaused() (gas: 36579)
[PASS] test_setPsm_success() (gas: 159294)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 206.30ms (1.35ms CPU time)

Ran 27 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyViewFunctionTests
[PASS] testFuzz_assetsUnderManagement_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 143871, ~: 144764)
[PASS] testFuzz_assetsUnderManagement_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 163757, ~: 163952)
[PASS] testFuzz_assetsUnderManagement_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 140270, ~: 140603)
[PASS] testFuzz_unrealizedLosses_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 120313, ~: 120663)
[PASS] testFuzz_unrealizedLosses_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 166369, ~: 166668)
[PASS] testFuzz_unrealizedLosses_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 140437, ~: 140585)
[PASS] test_assetsUnderManagement_strategyFundedAndZeroFeeAndZeroTout() (gas: 92887)
[PASS] test_assetsUnderManagement_strategyFundedAndZeroFeeWithTout() (gas: 96553)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndLossAndTout() (gas: 141277)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndLossAndZeroTout() (gas: 137567)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndTotalAssetsIncreasedAndAndTout() (gas: 145846)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndTotalAssetsIncreasedAndZeroTout() (gas: 138389)
[PASS] test_assetsUnderManagement_strategyNotFunded() (gas: 39174)
[PASS] test_factory() (gas: 13375)
[PASS] test_fundsAsset() (gas: 13386)
[PASS] test_globals() (gas: 18944)
[PASS] test_governor() (gas: 24641)
[PASS] test_implementation() (gas: 13462)
[PASS] test_locked() (gas: 11065)
[PASS] test_pool() (gas: 13320)
[PASS] test_poolDelegate() (gas: 19004)
[PASS] test_poolManager() (gas: 13295)
[PASS] test_savingsUsds() (gas: 13403)
[PASS] test_securityAdmin() (gas: 24613)
[PASS] test_strategyState() (gas: 11072)
[PASS] test_strategyType() (gas: 10282)
[PASS] test_treasury() (gas: 24659)
Suite result: ok. 27 passed; 0 failed; 0 skipped; finished in 211.44ms (955.33ms CPU time)

Ran 10 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategySetStrategyFeeRateTests
[PASS] test_setStrategyFeeRate_failIfImpaired() (gas: 64364)
[PASS] test_setStrategyFeeRate_failIfInactive() (gas: 64409)
[PASS] test_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 188679)
[PASS] test_setStrategyFeeRate_failInvalidStrategyFeeRate() (gas: 41085)
[PASS] test_setStrategyFeeRate_failReentrancy() (gas: 17783)
[PASS] test_setStrategyFeeRate_failWhenPaused() (gas: 34474)
[PASS] test_setStrategyFeeRate_nonZeroPriorFeeRate_totalAssetsIncreasedWithTout() (gas: 263119)
[PASS] test_setStrategyFeeRate_nonZeroPriorFeeRate_totalAssetsIncreasedWithZeroTout() (gas: 252486)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRateAndTotalAssetsAndZeroTout() (gas: 105234)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRate_totalAssetsIncreasedWithTout() (gas: 186434)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 205.91ms (2.06ms CPU time)

Ran 8 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyFundStrategyTests
[PASS] test_fundStrategy_successWithPoolDelegate() (gas: 130086)
[PASS] test_fundStrategy_successWithStrategyManager() (gas: 133187)
[PASS] test_fund_failIfImpaired() (gas: 70204)
[PASS] test_fund_failIfInactive() (gas: 70204)
[PASS] test_fund_failIfInvalidAavePool() (gas: 63777)
[PASS] test_fund_failIfNonManager() (gas: 52419)
[PASS] test_fund_failReentrancy() (gas: 23183)
[PASS] test_fund_failWhenPaused() (gas: 41418)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 207.63ms (332.88µs CPU time)

Ran 40 test suites in 212.26ms (1.74s CPU time): 322 tests passed, 0 failed, 0 skipped (322 total tests)

```
