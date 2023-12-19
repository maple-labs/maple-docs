# Test Reports

Below is an report of all smart contract level tests that are run against the protocol, in all repos.

Current number of tests in this report is: **2146 tests**.

## `maple-core-v2`

```
Running 1 test for tests/integration/loan/fixed-term/DeployLoan.t.sol:DeployFixedTermLoanTests
[PASS] test_deployFixedTermLoan_feeManagerCheck() (gas: 918974)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 18.53ms

Running 4 tests for tests/integration/loan-manager/open-term/RemoveCall.t.sol:RemoveCallFailureTests
[PASS] test_callPrincipal_notCalled() (gas: 81589)
[PASS] test_callPrincipal_notLender() (gas: 38259)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 51245)
[PASS] test_callPrincipal_paused() (gas: 52147)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 18.49ms

Running 3 tests for tests/integration/globals/ActivatePoolManager.t.sol:ActivatePoolManagerFailureTests
[PASS] test_activatePoolManager_failIfNotGlobals() (gas: 37482)
[PASS] test_activatePoolManager_failIfNotGovernor() (gas: 21414)
[PASS] test_activatePoolManager_failIfProtocolIsPaused() (gas: 71464)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 19.22ms

Running 2 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:SetBootstrapMintTests
[PASS] test_setBootstrapMint_failIfNotOperationalAdmin() (gas: 21623)
[PASS] test_setBootstrapMint_success_asOperationalAdmin() (gas: 40416)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 20.18ms

Running 5 tests for tests/integration/pool/DepositAndMint.t.sol:MintFailureTests
[PASS] test_mint_insufficientApproval() (gas: 349967)
[PASS] test_mint_liquidityCapExceeded() (gas: 505411)
[PASS] test_mint_privatePoolInvalidRecipient() (gas: 420370)
[PASS] test_mint_privatePoolInvalidRecipient_openPoolToPublic() (gas: 391644)
[PASS] test_mint_protocolPaused() (gas: 167023)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 20.97ms

Running 9 tests for tests/integration/loan-manager/Fund.t.sol:FixedTermLoanManagerFundTests
[PASS] test_fund_failIfAmountGreaterThanLockedLiquidity() (gas: 1773439)
[PASS] test_fund_failIfInsufficientCover() (gas: 262020)
[PASS] test_fund_failIfLoanActive() (gas: 987224)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 56283)
[PASS] test_fund_failIfPoolDoesNotApprovePM() (gas: 283788)
[PASS] test_fund_failIfProtocolIsPaused() (gas: 59962)
[PASS] test_fund_failIfTotalSupplyIsZero() (gas: 484828)
[PASS] test_fund_oneLoan() (gas: 856314)
[PASS] test_fund_twoLoans() (gas: 1400188)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 26.88ms

Running 2 tests for tests/integration/globals/ActivatePoolManager.t.sol:ActivatePoolManagerTests
[PASS] test_activatePoolManager() (gas: 83094)
[PASS] test_activatePoolManager_asOperationalAdmin() (gas: 97441)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 10.28ms

Running 9 tests for tests/integration/loan/DeployLoanByBorrower.t.sol:DeployLoanByBorrowerTests
[PASS] test_deployLoan_FTL_invalidBorrower() (gas: 688708)
[PASS] test_deployLoan_FTL_invalidInstance() (gas: 688433)
[PASS] test_deployLoan_FTL_setCanDeployFromByOA() (gas: 70531)
[PASS] test_deployLoan_FTL_success() (gas: 664895)
[PASS] test_deployLoan_FTL_validBorrowerSetByOA() (gas: 692801)
[PASS] test_deployLoan_FTL_validInstanceSetByOA() (gas: 690793)
[PASS] test_deployLoan_OTL_invalidBorrower() (gas: 528311)
[PASS] test_deployLoan_OTL_invalidInstance() (gas: 528102)
[PASS] test_deployLoan_OTL_success() (gas: 509398)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 14.73ms

Running 3 tests for tests/integration/loan-manager/open-term/RemoveCall.t.sol:RemoveCallTests
[PASS] test_removeCall_impaired() (gas: 423392)
[PASS] test_removeCall_latePayment() (gas: 153921)
[PASS] test_removeCall_paymentOnTime() (gas: 155555)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 18.36ms

Running 7 tests for tests/integration/withdrawal-manager/queue/AddShares.t.sol:AddSharesQueueFailureTests
[PASS] test_addShares_failIfAlreadyInQueue() (gas: 349587)
[PASS] test_addShares_failIfEmptyRequest() (gas: 107568)
[PASS] test_addShares_failIfInsufficientApproval() (gas: 101966)
[PASS] test_addShares_failIfNotPool() (gas: 46146)
[PASS] test_addShares_failIfNotPoolManager() (gas: 18919)
[PASS] test_addShares_failIfProtocolIsPaused() (gas: 66730)
[PASS] test_addShares_failIfTransferFail() (gas: 117207)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 12.05ms

Running 5 tests for tests/integration/loan-manager/fixed-term/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 69448)
[PASS] test_removeLoanImpairment_notGovernor() (gas: 265330)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 82788)
[PASS] test_removeLoanImpairment_notLender() (gas: 37841)
[PASS] test_removeLoanImpairment_pastDate() (gas: 348735)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 14.54ms

Running 4 tests for tests/integration/withdrawal-manager/queue/AddShares.t.sol:AddSharesQueueTests
[PASS] test_addShares_manual() (gas: 352122)
[PASS] test_addShares_partialRequest() (gas: 309903)
[PASS] test_addShares_success() (gas: 483750)
[PASS] test_addShares_withApproval() (gas: 322239)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 13.19ms

Running 17 tests for tests/integration/loan-manager/Fund.t.sol:OpenTermLoanManagerFundTests
[PASS] test_fund_insufficientCover() (gas: 406472)
[PASS] test_fund_invalidBorrower() (gas: 102333)
[PASS] test_fund_invalidLoanFactory() (gas: 88443)
[PASS] test_fund_invalidLoanInstance() (gas: 220279)
[PASS] test_fund_invalidLoanManagerFactory() (gas: 138987)
[PASS] test_fund_loanActive() (gas: 771142)
[PASS] test_fund_loanManagerApproveFailure() (gas: 480105)
[PASS] test_fund_loanNotActive() (gas: 714352)
[PASS] test_fund_loanTransferFailure() (gas: 539454)
[PASS] test_fund_lockedLiquidity() (gas: 609020)
[PASS] test_fund_notLender() (gas: 38585)
[PASS] test_fund_notLoanManager() (gas: 380942)
[PASS] test_fund_notPoolDelegate() (gas: 56328)
[PASS] test_fund_poolManagerTransferFailure() (gas: 425668)
[PASS] test_fund_protocolPause() (gas: 52149)
[PASS] test_fund_success() (gas: 678460)
[PASS] test_fund_zeroSupply() (gas: 630154)
Test result: ok. 17 passed; 0 failed; 0 skipped; finished in 27.37ms

Running 20 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolTests
[PASS] test_deployPool_failIfCalledPMFactoryDirectly() (gas: 33467)
[PASS] test_deployPool_failIfCalledWMFactoryDirectly() (gas: 35820)
[PASS] test_deployPool_failWithAssetNotAllowed() (gas: 324733)
[PASS] test_deployPool_failWithInsufficientPDApproval() (gas: 6174354)
[PASS] test_deployPool_failWithInvalidAsset() (gas: 422571)
[PASS] test_deployPool_failWithInvalidLMFactory() (gas: 5515387)
[PASS] test_deployPool_failWithInvalidManagementFee() (gas: 6173229)
[PASS] test_deployPool_failWithInvalidPD() (gas: 50314)
[PASS] test_deployPool_failWithInvalidPMFactory() (gas: 68096)
[PASS] test_deployPool_failWithInvalidStart() (gas: 5388392)
[PASS] test_deployPool_failWithInvalidWMCyclicalFactory() (gas: 73041)
[PASS] test_deployPool_failWithNonZeroSupplyAndZeroMigrationAdmin() (gas: 409080)
[PASS] test_deployPool_failWithOwnedPoolManager() (gas: 6555208)
[PASS] test_deployPool_failWithWindowDurationGtCycleDuration() (gas: 5388277)
[PASS] test_deployPool_failWithZeroAsset() (gas: 283265)
[PASS] test_deployPool_failWithZeroWindowDuration() (gas: 5388229)
[PASS] test_deployPool_success() (gas: 6476671)
[PASS] test_deployPool_successWithInitialSupply() (gas: 6416093)
[PASS] test_deployPool_successWithZeroMigrationAdmin() (gas: 6378645)
[PASS] test_deployPool_success_validPDSetByOA() (gas: 6455586)
Test result: ok. 20 passed; 0 failed; 0 skipped; finished in 24.44ms

Running 6 tests for tests/integration/withdrawal-manager/queue/RemoveRequest.t.sol:RemoveRequestFailureTests
[PASS] test_removeRequest_failIfNotGovernor() (gas: 183414)
[PASS] test_removeRequest_failIfNotInQueue() (gas: 138503)
[PASS] test_removeRequest_failIfNotOperationalAdmin() (gas: 187494)
[PASS] test_removeRequest_failIfNotPoolDelegate() (gas: 178995)
[PASS] test_removeRequest_failIfProtocolIsPaused() (gas: 54830)
[PASS] test_removeRequest_failIfTransferFail() (gas: 167336)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 12.30ms

Running 1 test for tests/integration/loan-manager/fixed-term/BasicInterestAccrual.t.sol:BasicInterestAccrualTest
[PASS] test_basicInterestAccrual() (gas: 2433347)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 14.63ms

Running 4 tests for tests/integration/withdrawal-manager/queue/RemoveRequest.t.sol:RemoveRequestTests
[PASS] test_removeRequest_forManual() (gas: 349767)
[PASS] test_removeRequest_manualPartialRedemption() (gas: 487515)
[PASS] test_removeRequest_partialRedemption() (gas: 507848)
[PASS] test_removeRequest_success() (gas: 502947)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.47ms

Running 12 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolWMQueueFailureTests
[PASS] test_deployPoolWMQueue_failIfAlreadyOwned() (gas: 6639850)
[PASS] test_deployPoolWMQueue_failIfInsufficientAmount() (gas: 6312925)
[PASS] test_deployPoolWMQueue_failIfInsufficientApproval() (gas: 6312923)
[PASS] test_deployPoolWMQueue_failIfInvalidManagementFeeRate() (gas: 6237800)
[PASS] test_deployPoolWMQueue_failIfInvalidPD() (gas: 46609)
[PASS] test_deployPoolWMQueue_failIfInvalidPMFactory() (gas: 6409042)
[PASS] test_deployPoolWMQueue_failIfInvalidPPM() (gas: 6418887)
[PASS] test_deployPoolWMQueue_failIfInvalidPoolAsset() (gas: 702810)
[PASS] test_deployPoolWMQueue_failIfInvalidWMFactory() (gas: 6413987)
[PASS] test_deployPoolWMQueue_failIfInvalidWMQFactory() (gas: 66394)
[PASS] test_deployPoolWMQueue_failIfPoolAssetNotAllowed() (gas: 321007)
[PASS] test_deployPoolWMQueue_failIfSaltCollision() (gas: 17595493375392626051)
Test result: ok. 12 passed; 0 failed; 0 skipped; finished in 23.42ms

Running 6 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolTransfer_functionLevel_transfer() (gas: 360285)
[PASS] test_poolTransfer_functionLevel_transferFrom() (gas: 368518)
[PASS] test_poolTransfer_functionLevel_transferFrom_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 279617)
[PASS] test_poolTransfer_functionLevel_transferFrom_zeroPoolBitmap_zeroLenderBitmaps() (gas: 210048)
[PASS] test_poolTransfer_functionLevel_transfer_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 273035)
[PASS] test_poolTransfer_functionLevel_transfer_zeroPoolBitmap_zeroLenderBitmaps() (gas: 203487)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.29ms

Running 9 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesCyclicalFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 229349)
[PASS] test_removeShares_failIfInvalidShares() (gas: 108740)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 108704)
[PASS] test_removeShares_failIfNotPool() (gas: 46120)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 19241)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 66774)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 197171)
[PASS] test_removeShares_failIfTransferFail() (gas: 184252)
[PASS] test_removeShares_failIfWithdrawalIsPending() (gas: 249358)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 13.60ms

Running 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxWithdrawTests
[PASS] testDeepFuzz_maxWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 457874, ~: 458329)
[PASS] test_maxWithdraw_lockedShares_inExitWindow() (gas: 453028)
[PASS] test_maxWithdraw_lockedShares_notInExitWindow() (gas: 449200)
[PASS] test_maxWithdraw_noLockedShares_notInExitWindow() (gas: 282546)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 98.51ms

Running 6 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolTransfer_poolLevel_transfer() (gas: 360397)
[PASS] test_poolTransfer_poolLevel_transferFrom() (gas: 368609)
[PASS] test_poolTransfer_poolLevel_transferFrom_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 279671)
[PASS] test_poolTransfer_poolLevel_transferFrom_zeroPoolBitmap_zeroLenderBitmaps() (gas: 210125)
[PASS] test_poolTransfer_poolLevel_transfer_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 273089)
[PASS] test_poolTransfer_poolLevel_transfer_zeroPoolBitmap_zeroLenderBitmaps() (gas: 203586)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.34ms

Running 2 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolWMQueueTests
[PASS] test_deployPoolWMQueue_success() (gas: 6489015)
[PASS] test_deployPoolWMQueue_withoutCoverAmount() (gas: 6369767)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 22.09ms

Running 2 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PrivatePermissionTests
[PASS] test_poolTransfer_private_transfer() (gas: 298157)
[PASS] test_poolTransfer_private_transferFrom() (gas: 305564)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 11.83ms

Running 5 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesCyclicalTests
[PASS] test_removeShares_pastTheRedemptionWindow() (gas: 177894)
[PASS] test_removeShares_prematurelyAddedShares() (gas: 463018)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 589692)
[PASS] test_removeShares_success() (gas: 178067)
[PASS] test_removeShares_withApproval() (gas: 195435)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 20.60ms

Running 2 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PublicPermissionTests
[PASS] test_poolTransfer_public_transfer() (gas: 102731)
[PASS] test_poolTransfer_public_transferFrom() (gas: 108488)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 11.07ms

Running 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewDepositTests
[PASS] test_previewDeposit_multipleUsers() (gas: 503657)
[PASS] test_previewDeposit_multipleUsers_changeTotalAssets() (gas: 533285)
[PASS] test_previewDeposit_nonZeroTotalSupply() (gas: 299281)
[PASS] test_previewDeposit_zeroTotalSupply() (gas: 12533)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 24.52ms

Running 8 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesQueueFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 220888)
[PASS] test_removeShares_failIfInvalidShares() (gas: 100051)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 97761)
[PASS] test_removeShares_failIfNotPool() (gas: 46053)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 19241)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 66796)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 186749)
[PASS] test_removeShares_failIfTransferFail() (gas: 181753)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 13.12ms

Running 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewMintTests
[PASS] test_previewMint_multipleUsers() (gas: 504843)
[PASS] test_previewMint_multipleUsers_changeTotalAssets() (gas: 534450)
[PASS] test_previewMint_nonZeroTotalSupply() (gas: 300511)
[PASS] test_previewMint_zeroTotalSupply() (gas: 12385)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 13.60ms

Running 5 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesQueueTests
[PASS] test_removeShares_manual_partiallyProcessed() (gas: 731780)
[PASS] test_removeShares_partiallyProcessed() (gas: 447715)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 618099)
[PASS] test_removeShares_success() (gas: 185671)
[PASS] test_removeShares_withApproval() (gas: 203017)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 16.00ms

Running 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewRedeemTests
[PASS] test_previewRedeem_invalidShares() (gas: 440377)
[PASS] test_previewRedeem_lockedShares_inExitWindow() (gas: 476007)
[PASS] test_previewRedeem_lockedShares_notInExitWindow() (gas: 445860)
[PASS] test_previewRedeem_noLockedShares_notInExitWindow() (gas: 37023)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 12.08ms

Running 7 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewRedeemWithQueueWMTests
[PASS] test_previewRedeem_emptyRedemption_fullLiquidity() (gas: 131587)
[PASS] test_previewRedeem_emptyRedemption_partialLiquidity() (gas: 131694)
[PASS] test_previewRedeem_fullRedemption_fullLiquidity() (gas: 131931)
[PASS] test_previewRedeem_fullRedemption_partialLiquidity() (gas: 132011)
[PASS] test_previewRedeem_insufficientShares() (gas: 38694)
[PASS] test_previewRedeem_partialRedemption_fullLiquidity() (gas: 132524)
[PASS] test_previewRedeem_partialRedemption_partialLiquidity() (gas: 132634)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 12.71ms

Running 7 tests for tests/integration/withdrawal-manager/queue/SetManualWithdrawal.t.sol:SetManualWithdrawalTests
[PASS] test_setManualWithdrawal_failIfLpAlreadyInQueue() (gas: 286069)
[PASS] test_setManualWithdrawal_failIfNotProtocolAdmin() (gas: 61368)
[PASS] test_setManualWithdrawal_failIfProtocolIsPaused() (gas: 55049)
[PASS] test_setManualWithdrawal_success() (gas: 83359)
[PASS] test_setManualWithdrawal_successAsGovernor() (gas: 87711)
[PASS] test_setManualWithdrawal_successAsOperationalAdmin() (gas: 91858)
[PASS] test_setManualWithdrawal_unsetSuccess() (gas: 78729)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 18.21ms

Running 4 tests for tests/integration/loan-manager/fixed-term/SetMinRatioAndSlippage.t.sol:SetMinRatioTests
[PASS] test_setMinRatio_notAuthorized() (gas: 57445)
[PASS] test_setMinRatio_notPoolManager() (gas: 57445)
[PASS] test_setMinRatio_withGovernor() (gas: 85585)
[PASS] test_setMinRatio_withPoolDelegate() (gas: 79697)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 11.04ms

Running 5 tests for tests/integration/loan-manager/fixed-term/SetMinRatioAndSlippage.t.sol:SetSlippageTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 131172)
[PASS] test_setAllowedSlippage_notAuthorized() (gas: 57358)
[PASS] test_setAllowedSlippage_notPoolManager() (gas: 57402)
[PASS] test_setAllowedSlippage_withGovernor() (gas: 85546)
[PASS] test_setAllowedSlippage_withPoolDelegate() (gas: 79637)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 11.64ms

Running 2 tests for tests/fuzz/PoolTransferPermissionsFuzz.t.sol:PoolTransferPermissionsFuzzTests
[PASS] testFuzz_poolTransfer(uint256,uint256,uint256,uint256,uint256,bool,bool) (runs: 100, μ: 483162, ~: 422625)
[PASS] testFuzz_poolTransferFrom(uint256,uint256,uint256,uint256,uint256,bool,bool) (runs: 100, μ: 470897, ~: 424239)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 154.54ms

Running 8 tests for tests/integration/permission-manager/SetPoolPermissionLevel.t.sol:SetPoolPermissionLevelTests
[PASS] testFuzz_setPoolPermissionLevel(uint256,uint256) (runs: 100, μ: 109668, ~: 112695)
[PASS] testFuzz_setPoolPermissionLevel_invalidLevel(uint256) (runs: 100, μ: 47512, ~: 47443)
[PASS] testFuzz_setPoolPermissionLevel_publicPool(uint256) (runs: 100, μ: 94675, ~: 94780)
[PASS] test_setPoolPermissionLevel_anotherPoolDelegate() (gas: 79526)
[PASS] test_setPoolPermissionLevel_governor() (gas: 69325)
[PASS] test_setPoolPermissionLevel_notAuthorized() (gas: 45031)
[PASS] test_setPoolPermissionLevel_operationalAdmin() (gas: 73584)
[PASS] test_setPoolPermissionLevel_poolDelegate() (gas: 66949)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 90.02ms

Running 1 test for tests/fuzz/Deposit.t.sol:DepositFuzzTests
[PASS] testDeepFuzz_deposit_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 463198, ~: 489455)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 179.83ms

Running 5 tests for tests/integration/pool/DepositAndMint.t.sol:DepositFailureTests
[PASS] test_deposit_insufficientApproval() (gas: 346199)
[PASS] test_deposit_liquidityCapExceeded() (gas: 461428)
[PASS] test_deposit_privatePoolInvalidRecipient() (gas: 411083)
[PASS] test_deposit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 382270)
[PASS] test_deposit_protocolPaused() (gas: 107250)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 12.32ms

Running 10 tests for tests/integration/pool/Transfer.t.sol:TransferTests
[PASS] test_transferFrom_privatePoolInvalidLender() (gas: 443262)
[PASS] test_transferFrom_privatePoolInvalidLender_openPoolToPublic() (gas: 434994)
[PASS] test_transferFrom_protocolPaused() (gas: 366380)
[PASS] test_transferFrom_publicPool() (gas: 352611)
[PASS] test_transferFrom_publicPool_insufficientApproval() (gas: 358699)
[PASS] test_transferFrom_publicPool_noApproval() (gas: 333603)
[PASS] test_transfer_privatePoolInvalidLender() (gas: 427718)
[PASS] test_transfer_privatePoolInvalidLender_openPoolToPublic() (gas: 419491)
[PASS] test_transfer_protocolPaused() (gas: 338359)
[PASS] test_transfer_publicPool() (gas: 341981)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 24.20ms

Running 9 tests for tests/integration/globals/TransferPoolOwnership.t.sol:TransferPoolOwnershipTests
[PASS] test_acceptPoolDelegate() (gas: 111145)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 117767)
[PASS] test_setPendingPoolDelegate_asGovernor() (gas: 74001)
[PASS] test_setPendingPoolDelegate_asOperationalAdmin() (gas: 79539)
[PASS] test_setPendingPoolDelegate_asPoolDelegate() (gas: 68184)
[PASS] test_setPendingPoolDelegate_notPD() (gas: 110800)
[PASS] test_transferOwnedPoolManager_alreadyPoolDelegate() (gas: 152047)
[PASS] test_transferOwnedPoolManager_notPoolManager() (gas: 117792)
[PASS] test_transferOwnedPoolManager_notValidPoolDelegate() (gas: 126955)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 19.78ms

Running 4 tests for tests/integration/pool/DepositAndMint.t.sol:MintTest
[PASS] testDeepFuzz_mint_singleUser(uint256) (runs: 100, μ: 316343, ~: 316299)
[PASS] testDeepFuzz_mint_variableExchangeRate(uint256,uint256) (runs: 100, μ: 1635199, ~: 1634954)
[PASS] test_mint_singleUser_oneToOne() (gas: 312002)
[PASS] test_mint_twoUsers_oneToOne() (gas: 468944)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 313.89ms

Running 6 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewWithdrawTests
[PASS] testDeepFuzz_previewWithdraw(uint256) (runs: 100, μ: 35084, ~: 35084)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 447688, ~: 447038)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_notInExitWindow(uint256) (runs: 100, μ: 447941, ~: 448171)
[PASS] test_previewWithdraw() (gas: 277520)
[PASS] test_previewWithdraw_zeroAssetsWithDeposit() (gas: 277497)
[PASS] test_previewWithdraw_zeroAssetsWithoutDeposit() (gas: 34843)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 177.60ms

Running 10 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultFailureTests
[PASS] test_triggerDefault_invalidLoanManager() (gas: 4866185)
[PASS] test_triggerDefault_notAuthorized() (gas: 59405)
[PASS] test_triggerDefault_notFactory() (gas: 54994)
[PASS] test_triggerDefault_notInDefault_boundary() (gas: 604171)
[PASS] test_triggerDefault_notLoan() (gas: 94274)
[PASS] test_triggerDefault_notPM() (gas: 442844)
[PASS] test_triggerDefault_protocolPaused_loanManager() (gas: 55331)
[PASS] test_triggerDefault_protocolPaused_poolManager() (gas: 54680)
[PASS] test_triggerDefault_repossess_notLender() (gas: 40831)
[PASS] test_triggerDefault_treasuryZeroAddress() (gas: 561783)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 33.33ms

Running 5 tests for tests/integration/pool/DepositAndMint.t.sol:MintWithPermitFailureTests
[PASS] test_mintWithPermit_insufficientPermit() (gas: 534329)
[PASS] test_mintWithPermit_liquidityCapExceeded() (gas: 557922)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient() (gas: 461457)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 432686)
[PASS] test_mintWithPermit_protocolPaused() (gas: 170622)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 32.69ms

Running 9 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultTests
[PASS] test_triggerDefault_called() (gas: 630186)
[PASS] test_triggerDefault_feesAndFullRecovery() (gas: 327604)
[PASS] test_triggerDefault_feesAndPartialRecovery() (gas: 317183)
[PASS] test_triggerDefault_impaired() (gas: 649393)
[PASS] test_triggerDefault_impaired_feesAndFullRecovery() (gas: 364867)
[PASS] test_triggerDefault_impaired_onlyFeesRecovered() (gas: 345692)
[PASS] test_triggerDefault_latePayment() (gas: 527631)
[PASS] test_triggerDefault_onlyFeesRecovered() (gas: 303819)
[PASS] test_triggerDefault_setByOperationalAdmin() (gas: 315175)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 20.17ms

Running 3 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notAuthorized() (gas: 59449)
[PASS] test_triggerDefault_notFactory() (gas: 54972)
[PASS] test_triggerDefault_notPoolManager() (gas: 57109)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 12.55ms

Running 3 tests for tests/integration/loan-manager/fixed-term/UnrealizedLosses.t.sol:UnrealizedLossesTests
[PASS] test_unrealizedLosses_depositWithUnrealizedLosses() (gas: 498236)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_fullLiquidity() (gas: 633465)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_partialLiquidity() (gas: 1952022)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 17.32ms

Running 2 tests for tests/integration/globals/Upgrade.t.sol:GlobalsUpgradeTests
[PASS] test_upgradeGlobals() (gas: 25953)
[PASS] test_upgradeGlobals_notAdmin() (gas: 30390)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 10.73ms

Running 6 tests for tests/integration/globals/Upgrade.t.sol:LiquidationUpgradeTests
[PASS] test_upgradeLiquidator_delayNotPassed() (gas: 169446)
[PASS] test_upgradeLiquidator_durationPassed() (gas: 170232)
[PASS] test_upgradeLiquidator_governor_noTimelockNeeded() (gas: 208334)
[PASS] test_upgradeLiquidator_noTimelock() (gas: 177819)
[PASS] test_upgradeLiquidator_timelockExtended() (gas: 300992)
[PASS] test_upgradeLiquidator_timelockShortened() (gas: 301840)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 26.74ms

Running 1 test for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewWithdrawWithQueueWMTests
[PASS] testFuzz_previewWithdraw(address,bool,uint256,uint256,uint256) (runs: 100, μ: 601804, ~: 615867)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 124.19ms

Running 6 tests for tests/integration/globals/Upgrade.t.sol:LoanManagerUpgradeTests
[PASS] test_upgradeLoanManager_delayNotPassed() (gas: 168752)
[PASS] test_upgradeLoanManager_durationPassed() (gas: 169558)
[PASS] test_upgradeLoanManager_governor_noTimelockNeeded() (gas: 195737)
[PASS] test_upgradeLoanManager_noTimelock() (gas: 177215)
[PASS] test_upgradeLoanManager_timelockExtended() (gas: 295218)
[PASS] test_upgradeLoanManager_timelockShortened() (gas: 295999)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 17.51ms

Running 6 tests for tests/integration/globals/Upgrade.t.sol:PoolManagerUpgradeTests
[PASS] test_upgradePoolManager_delayNotPassed() (gas: 147217)
[PASS] test_upgradePoolManager_durationPassed() (gas: 148045)
[PASS] test_upgradePoolManager_governor_noTimelockNeeded() (gas: 174113)
[PASS] test_upgradePoolManager_noTimelock() (gas: 155633)
[PASS] test_upgradePoolManager_timelockExtended() (gas: 252233)
[PASS] test_upgradePoolManager_timelockShortened() (gas: 253014)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 13.11ms

Running 2 tests for tests/integration/pool/DepositAndMint.t.sol:MintWithPermitTests
[PASS] testDeepFuzz_mintWithPermit_singleUser(uint256) (runs: 100, μ: 352771, ~: 352763)
[PASS] test_mintWithPermit_singleUser() (gas: 351239)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 117.23ms

Running 5 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:TotalAssetsTests
[PASS] test_totalAssets_singleDeposit() (gas: 273869)
[PASS] test_totalAssets_singleLoanFunded() (gas: 1565692)
[PASS] test_totalAssets_singleLoanFundedWithInterest() (gas: 1600408)
[PASS] test_totalAssets_singleLoanFundedWithPayment() (gas: 1836737)
[PASS] test_totalAssets_zeroTotalSupply() (gas: 65190)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 22.21ms

Running 1 test for tests/integration/globals/Upgrade.t.sol:UnscheduleCallTests
[PASS] test_unscheduleCall_governor() (gas: 89492)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 10.47ms

Running 6 tests for tests/integration/globals/Upgrade.t.sol:WithdrawalManagerUpgradeTests
[PASS] test_upgradeWithdrawalManager_delayNotPassed() (gas: 147903)
[PASS] test_upgradeWithdrawalManager_durationPassed() (gas: 148665)
[PASS] test_upgradeWithdrawalManager_governor_noTimelockNeeded() (gas: 174752)
[PASS] test_upgradeWithdrawalManager_noTimelock() (gas: 156278)
[PASS] test_upgradeWithdrawalManager_timelockExtended() (gas: 257837)
[PASS] test_upgradeWithdrawalManager_timelockShortened() (gas: 258684)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.58ms

Running 12 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolEntry_functionLevel_deposit() (gas: 422528)
[PASS] test_poolEntry_functionLevel_depositWithPermit() (gas: 470764)
[PASS] test_poolEntry_functionLevel_depositWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 424380)
[PASS] test_poolEntry_functionLevel_depositWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 387519)
[PASS] test_poolEntry_functionLevel_deposit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 378043)
[PASS] test_poolEntry_functionLevel_deposit_zeroPoolBitmap_zeroLenderBitmap() (gas: 341269)
[PASS] test_poolEntry_functionLevel_mint() (gas: 428230)
[PASS] test_poolEntry_functionLevel_mintWithPermit() (gas: 477487)
[PASS] test_poolEntry_functionLevel_mintWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 428773)
[PASS] test_poolEntry_functionLevel_mintWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 392023)
[PASS] test_poolEntry_functionLevel_mint_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 381900)
[PASS] test_poolEntry_functionLevel_mint_zeroPoolBitmap_zeroLenderBitmap() (gas: 345061)
Test result: ok. 12 passed; 0 failed; 0 skipped; finished in 20.02ms

Running 12 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolEntry_poolLevel_deposit() (gas: 422643)
[PASS] test_poolEntry_poolLevel_depositWithPermit() (gas: 470746)
[PASS] test_poolEntry_poolLevel_depositWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 424377)
[PASS] test_poolEntry_poolLevel_depositWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 387602)
[PASS] test_poolEntry_poolLevel_deposit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 378104)
[PASS] test_poolEntry_poolLevel_deposit_zeroPoolBitmap_zeroLenderBitmap() (gas: 341309)
[PASS] test_poolEntry_poolLevel_mint() (gas: 428298)
[PASS] test_poolEntry_poolLevel_mintWithPermit() (gas: 477470)
[PASS] test_poolEntry_poolLevel_mintWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 428857)
[PASS] test_poolEntry_poolLevel_mintWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 392106)
[PASS] test_poolEntry_poolLevel_mint_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 381875)
[PASS] test_poolEntry_poolLevel_mint_zeroPoolBitmap_zeroLenderBitmap() (gas: 345168)
Test result: ok. 12 passed; 0 failed; 0 skipped; finished in 20.17ms

Running 4 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PrivatePermissionTests
[PASS] test_poolEntry_private_deposit() (gas: 357252)
[PASS] test_poolEntry_private_depositWithPermit() (gas: 403527)
[PASS] test_poolEntry_private_mint() (gas: 361023)
[PASS] test_poolEntry_private_mintWithPermit() (gas: 408006)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.22ms

Running 4 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PublicPermissionTests
[PASS] test_poolEntry_public_deposit() (gas: 244180)
[PASS] test_poolEntry_public_depositWithPermit() (gas: 288496)
[PASS] test_poolEntry_public_mint() (gas: 246022)
[PASS] test_poolEntry_public_mintWithPermit() (gas: 290740)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 12.86ms

Running 4 tests for tests/integration/pool/DepositAndMint.t.sol:DepositTest
[PASS] testDeepFuzz_deposit_singleUser(uint256) (runs: 100, μ: 312862, ~: 312781)
[PASS] testDeepFuzz_deposit_variableExchangeRate(uint256,uint256) (runs: 100, μ: 1597904, ~: 1600049)
[PASS] test_deposit_singleUser_oneToOne() (gas: 308529)
[PASS] test_deposit_twoUsers_oneToOne() (gas: 440039)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 297.67ms

Running 5 tests for tests/integration/pool/DepositAndMint.t.sol:DepositWithPermitFailureTests
[PASS] test_depositWithPermit_invalidSignature() (gas: 531976)
[PASS] test_depositWithPermit_liquidityCapExceeded() (gas: 513178)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient() (gas: 451728)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 422953)
[PASS] test_depositWithPermit_protocolPaused() (gas: 166501)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 16.86ms

Running 2 tests for tests/integration/pool/DepositAndMint.t.sol:DepositWithPermitTests
[PASS] testDeepFuzz_depositWithPermit_singleUser(uint256) (runs: 100, μ: 351876, ~: 351796)
[PASS] test_depositWithPermit_singleUser() (gas: 347464)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 124.35ms

Running 3 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemIntegrationTests
[PASS] test_redeem_oneLPWithImpairedLoan() (gas: 1882545)
[PASS] test_redeem_twoLPSWithImpairedLoanAndTriggerDefault() (gas: 2031889)
[PASS] test_redeem_twoLPsWithImpairedLoan() (gas: 2217682)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 26.75ms

Running 4 tests for tests/fuzz/PoolEntryPermissionsFuzz.t.sol:PoolEntryPermissionsFuzzTests
[PASS] testFuzz_poolEntryTests_deposit(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 363382, ~: 364626)
[PASS] testFuzz_poolEntryTests_depositWithPermit(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 444055, ~: 409737)
[PASS] testFuzz_poolEntryTests_mint(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 350297, ~: 330410)
[PASS] testFuzz_poolEntryTests_mintWithPermit(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 462532, ~: 449953)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 306.13ms

Running 15 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolExit_functionLevel_redeem() (gas: 639640)
[PASS] test_poolExit_functionLevel_redeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 645563)
[PASS] test_poolExit_functionLevel_redeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 616110)
[PASS] test_poolExit_functionLevel_removeShares() (gas: 517261)
[PASS] test_poolExit_functionLevel_removeShares_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 523760)
[PASS] test_poolExit_functionLevel_removeShares_zeroPoolBitmap_zeroLenderBitmap() (gas: 494342)
[PASS] test_poolExit_functionLevel_requestRedeem() (gas: 440451)
[PASS] test_poolExit_functionLevel_requestRedeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 396035)
[PASS] test_poolExit_functionLevel_requestRedeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 359241)
[PASS] test_poolExit_functionLevel_requestWithdraw() (gas: 359350)
[PASS] test_poolExit_functionLevel_requestWithdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 314784)
[PASS] test_poolExit_functionLevel_requestWithdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 278098)
[PASS] test_poolExit_functionLevel_withdraw() (gas: 265290)
[PASS] test_poolExit_functionLevel_withdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 219998)
[PASS] test_poolExit_functionLevel_withdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 183181)
Test result: ok. 15 passed; 0 failed; 0 skipped; finished in 24.08ms

Running 7 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemTests
[PASS] testDeepFuzz_redeem_singleUser_fullLiquidity_oneToOne(uint256,uint256) (runs: 100, μ: 571178, ~: 569560)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem() (gas: 582924)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem_prematureRequest() (gas: 584088)
[PASS] test_redeem_singleUser_fullLiquidity_oneToOne() (gas: 579349)
[PASS] test_redeem_singleUser_noLiquidity() (gas: 1872685)
[PASS] test_redeem_singleUser_noLiquidity_notOwner() (gas: 1939563)
[PASS] test_redeem_singleUser_withApprovals() (gas: 641198)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 143.47ms

Running 15 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolExit_poolLevel_redeem() (gas: 603560)
[PASS] test_poolExit_poolLevel_redeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 591144)
[PASS] test_poolExit_poolLevel_redeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 561742)
[PASS] test_poolExit_poolLevel_removeShares() (gas: 481073)
[PASS] test_poolExit_poolLevel_removeShares_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 469374)
[PASS] test_poolExit_poolLevel_removeShares_zeroPoolBitmap_zeroLenderBitmap() (gas: 439973)
[PASS] test_poolExit_poolLevel_requestRedeem() (gas: 440498)
[PASS] test_poolExit_poolLevel_requestRedeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 396010)
[PASS] test_poolExit_poolLevel_requestRedeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 359238)
[PASS] test_poolExit_poolLevel_requestWithdraw() (gas: 359442)
[PASS] test_poolExit_poolLevel_requestWithdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 314823)
[PASS] test_poolExit_poolLevel_requestWithdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 278115)
[PASS] test_poolExit_poolLevel_withdraw() (gas: 265316)
[PASS] test_poolExit_poolLevel_withdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 220016)
[PASS] test_poolExit_poolLevel_withdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 183288)
Test result: ok. 15 passed; 0 failed; 0 skipped; finished in 23.39ms

Running 4 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RequestRedeemFailureTests
[PASS] test_requestRedeem_failIfAlreadyLockedShares() (gas: 338461)
[PASS] test_requestRedeem_failIfInsufficientApproval() (gas: 164465)
[PASS] test_requestRedeem_failIfNotPM() (gas: 18962)
[PASS] test_requestRedeem_failIfNotPool() (gas: 46283)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 12.62ms

Running 5 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PrivatePermissionTests
[PASS] test_poolExit_private_redeem() (gas: 538495)
[PASS] test_poolExit_private_removeShares() (gas: 416740)
[PASS] test_poolExit_private_requestRedeem() (gas: 382179)
[PASS] test_poolExit_private_requestWithdraw() (gas: 300971)
[PASS] test_poolExit_private_withdraw() (gas: 206166)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 14.50ms

Running 5 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PublicPermissionTests
[PASS] test_poolExit_public_redeem() (gas: 414969)
[PASS] test_poolExit_public_removeShares() (gas: 292217)
[PASS] test_poolExit_public_requestRedeem() (gas: 255441)
[PASS] test_poolExit_public_requestWithdraw() (gas: 178810)
[PASS] test_poolExit_public_withdraw() (gas: 83260)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 13.27ms

Running 7 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RequestRedeemTests
[PASS] testDeepFuzz_requestRedeem(uint256,uint256) (runs: 100, μ: 488191, ~: 490044)
[PASS] test_requestRedeem() (gas: 460343)
[PASS] test_requestRedeem_premature() (gas: 463055)
[PASS] test_requestRedeem_refresh() (gas: 552646)
[PASS] test_requestRedeem_refresh_notOwnerAndNoApproval() (gas: 508127)
[PASS] test_requestRedeem_refresh_notOwnerWithApproval() (gas: 586896)
[PASS] test_requestRedeem_withApproval() (gas: 480153)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 85.47ms

Running 5 tests for tests/integration/withdrawal-manager/queue/RedeemQueue.t.sol:ManualRedeemTests
[PASS] test_manualRedeem_fullLiquidity() (gas: 833876)
[PASS] test_manualRedeem_insufficientLiquidity() (gas: 1133499)
[PASS] test_manualRedeem_noShares() (gas: 97656)
[PASS] test_manualRedeem_partialLiquidity() (gas: 914424)
[PASS] test_manualRedeem_tooManyShares() (gas: 512644)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 19.46ms

Running 13 tests for tests/integration/loan/Refinance.t.sol:AcceptNewTermsFailureTests
[PASS] testFail_acceptNewTerms_failIfNotValidLoanManager() (gas: 79262)
[PASS] test_acceptNewTerms_failIfDeadlineExpired() (gas: 216948)
[PASS] test_acceptNewTerms_failIfInsufficientCover() (gas: 269257)
[PASS] test_acceptNewTerms_failIfLockedLiquidity() (gas: 516310)
[PASS] test_acceptNewTerms_failIfNotLender() (gas: 41983)
[PASS] test_acceptNewTerms_failIfNotPoolDelegate() (gas: 60313)
[PASS] test_acceptNewTerms_failIfProtocolIsPaused() (gas: 63946)
[PASS] test_acceptNewTerms_failIfRefinanceCallFails() (gas: 343621)
[PASS] test_acceptNewTerms_failIfRefinanceMismatch() (gas: 159072)
[PASS] test_acceptNewTerms_failWithFailedTransfer() (gas: 286378)
[PASS] test_acceptNewTerms_failWithInsufficientCollateral() (gas: 626676)
[PASS] test_acceptNewTerms_failWithInvalidRefinancer() (gas: 243629)
[PASS] test_acceptNewTerms_failWithUnexpectedFunds() (gas: 617674)
Test result: ok. 13 passed; 0 failed; 0 skipped; finished in 18.23ms

Running 3 tests for tests/integration/loan/Refinance.t.sol:RefinanceOpenTermLoan
[PASS] test_refinance_calledLoan_withoutPrincipalChange() (gas: 791971)
[PASS] test_refinance_early_increasePrincipal() (gas: 791245)
[PASS] test_refinance_late_decreasePrincipal() (gas: 704731)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 20.14ms

Running 5 tests for tests/integration/loan/Refinance.t.sol:RefinanceTestsSingleLoan
[PASS] test_refinance_onLateLoan_changePaymentInterval() (gas: 1156002)
[PASS] test_refinance_onLoanPaymentDueDate_changeInterestRate() (gas: 1146696)
[PASS] test_refinance_onLoanPaymentDueDate_changePaymentInterval() (gas: 1146634)
[PASS] test_refinance_onLoanPaymentDueDate_changeToAmortized() (gas: 1149450)
[PASS] test_refinance_onLoanPaymentDueDate_increasePrincipal() (gas: 1201303)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 28.43ms

Running 3 tests for tests/e2e/RefinanceScenario.t.sol:RefinanceScenariosTests
[PASS] test_impairOTL_refinanceToHigherPrincipal_oneLoanImpaired_underflow() (gas: 1294203)
[PASS] test_impairOTL_refinanceToHigherPrincipal_twoLoansImpaired() (gas: 1482479)
[PASS] test_impairOTL_refinanceToLowerPrincipal_singleLoanImpaired() (gas: 1353018)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 20.04ms

Running 8 tests for tests/integration/loan-manager/fixed-term/GetExpectedAmount.t.sol:GetExpectedAmountTests
[PASS] testFork_getExpectedAmount_currentPrice() (gas: 116647)
[PASS] testFork_getExpectedAmount_manualOverride() (gas: 90986)
[PASS] testFork_getExpectedAmount_oracleNotSet() (gas: 58026)
[PASS] testFork_getExpectedAmount_withMinRatio() (gas: 166154)
[PASS] testFork_getExpectedAmount_withSlippage() (gas: 166073)
[PASS] testFork_getExpectedAmount_withSlippageAndMinRatio_minRatioHigher() (gas: 200305)
[PASS] testFork_getExpectedAmount_withSlippageAndMinRatio_slippageHigher() (gas: 200296)
[PASS] testFork_getExpectedAmount_zeroAmount() (gas: 116632)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 1.11s

Running 4 tests for tests/integration/globals/GetLatestPrice.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice_currentPrice() (gas: 78049)
[PASS] test_getLatestPrice_manualOverride() (gas: 48353)
[PASS] test_getLatestPrice_stalePrice() (gas: 106477)
[PASS] test_getLatestPrice_unknownAsset() (gas: 21601)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 27.19ms

Running 1 test for tests/e2e/GlobalPermission.t.sol:GlobalPermissionTests
[PASS] test_e2e_globalPermission() (gas: 1893014)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 20.51ms

Running 1 test for tests/invariants/Regression.t.sol:WithdrawalManagerQueueInvariants
[PASS] test_regression_invariants() (gas: 52673687)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 110.28ms

Running 9 tests for tests/integration/withdrawal-manager/queue/ProcessRedemptions.t.sol:ProcessRedemptionsTests
[PASS] test_processRedemptions_differentExchangeRate() (gas: 1658707)
[PASS] test_processRedemptions_lowLiquidity() (gas: 1069995)
[PASS] test_processRedemptions_manualWithDifferentExchangeRates() (gas: 1403458)
[PASS] test_processRedemptions_multipleLps() (gas: 1325004)
[PASS] test_processRedemptions_multipleManualBatched() (gas: 1892758)
[PASS] test_processRedemptions_overkill() (gas: 1448503)
[PASS] test_processRedemptions_withCancelledRequest() (gas: 1243399)
[PASS] test_processRedemptions_withImpairment() (gas: 1658929)
[PASS] test_processRedemptions_zeroShares() (gas: 58257)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 45.94ms

Running 5 tests for tests/fuzz/PoolExitPermissionsFuzz.t.sol:PoolExitPermissionsFuzzTests
[PASS] testFuzz_poolExit_redeem(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 752964, ~: 589587)
[PASS] testFuzz_poolExit_removeShares(uint256,uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 654665, ~: 521008)
[PASS] testFuzz_poolExit_requestRedeem(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 542707, ~: 694119)
[PASS] testFuzz_poolExit_requestWithdraw(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 455146, ~: 381207)
[PASS] testFuzz_poolExit_withdraw(uint256,uint256,uint256,uint256,bool) (runs: 100, μ: 440707, ~: 382884)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 361.64ms

Running 3 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:MultiUserRedeemTests
[PASS] test_redeem_partialLiquidity_sameCash_differentExchangeRate() (gas: 2670985)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate() (gas: 2546046)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate_exposeRounding() (gas: 5062275)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 29.98ms

Running 9 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemFailureTests
[PASS] test_redeem_failIfNoApprove() (gas: 280250)
[PASS] test_redeem_failIfNoBalanceOnWM() (gas: 398925)
[PASS] test_redeem_failIfNoRequest() (gas: 101076)
[PASS] test_redeem_failIfNotInWindow() (gas: 317846)
[PASS] test_redeem_failIfNotPool() (gas: 46777)
[PASS] test_redeem_failIfNotPoolManager() (gas: 19414)
[PASS] test_redeem_failWithInsufficientApproval() (gas: 366976)
[PASS] test_redeem_failWithInvalidAmountOfShares() (gas: 312232)
[PASS] test_redeem_failWithZeroReceiver() (gas: 343205)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 14.79ms

Running 1 test for tests/e2e/PoolLifecycle.t.sol:PoolLifecycleTest
[PASS] test_poolLifecycle() (gas: 11645959)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 21.55ms

Running 15 tests for tests/fuzz/PoolViewFunctionsFuzzTest.t.sol:PoolViewFunctionsFuzzTests
[PASS] testFuzz_convertToAssets_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 389146, ~: 389436)
[PASS] testFuzz_convertToAssets_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 14351, ~: 13936)
[PASS] testFuzz_convertToExitShares(uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 422757, ~: 422880)
[PASS] testFuzz_convertToShares_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 389088, ~: 388454)
[PASS] testFuzz_convertToShares_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 14402, ~: 13889)
[PASS] testFuzz_getTotalAssetsFromPM(uint256,uint256) (runs: 100, μ: 122896, ~: 123101)
[PASS] testFuzz_getUnrealizedLossesFromPM(uint256) (runs: 100, μ: 108551, ~: 107917)
[PASS] testFuzz_maxDeposit(uint256,uint256) (runs: 100, μ: 348912, ~: 349059)
[PASS] testFuzz_maxMint(uint256,uint256) (runs: 100, μ: 357974, ~: 357951)
[PASS] testFuzz_maxRedeem(uint256) (runs: 100, μ: 751014, ~: 750660)
[PASS] testFuzz_maxWithdraw(uint256) (runs: 100, μ: 504673, ~: 504263)
[PASS] testFuzz_previewDeposit_whenTotalSupplyExists(uint256,uint256) (runs: 100, μ: 340446, ~: 340691)
[PASS] testFuzz_previewDeposit_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 14456, ~: 13951)
[PASS] testFuzz_previewMint_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 390186, ~: 390404)
[PASS] testFuzz_previewMint_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 14432, ~: 13932)
Test result: ok. 15 passed; 0 failed; 0 skipped; finished in 1.14s

Running 1 test for tests/protocol-upgrade/DeprecateLoanFactory.t.sol:DeprecateLoanFactoryTest
[PASS] testFork_deprecateFactory() (gas: 601551)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.08s

Running 1 test for tests/protocol-upgrade/DeprecatePoolDeployerV2.t.sol:DeprecatePoolDeployerV2TestsBASEL2
[PASS] testFork_deprecatePoolDeployerV2_BASEL2() (gas: 60558911)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 50.61ms

Running 4 tests for tests/protocol-upgrade/UpgradeTests.t.sol:UpgradeTestsBASEL2
[PASS] testFork_upgradeAssertions_BASEL2() (gas: 54385202)
[PASS] testFork_upgradeFTL_fromNewFactory_BASEL2() (gas: 60108270)
[PASS] testFork_upgradeFTL_identicalFactory() (gas: 54033807)
[PASS] testFork_upgradeToQueueWM_BASEL2() (gas: 54781071)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.14s

Running 1 test for tests/protocol-upgrade/DeprecatePoolDeployerV2.t.sol:DeprecatePoolDeployerV2TestsETH
[PASS] testFork_deprecatePoolDeployerV2_ETH() (gas: 69573533)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 368.88ms

Running 3 tests for tests/integration/loan-manager/fixed-term/FetchValuesFromLM.t.sol:LoanManagerIsLiquidationActiveGetterTests
[PASS] test_isLiquidationActive_afterLiquidation() (gas: 1104887)
[PASS] test_isLiquidationActive_beforeLiquidation() (gas: 15920)
[PASS] test_isLiquidationActive_duringLiquidation() (gas: 628534)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 15.02ms

Running 4 tests for tests/integration/pool/FetchValuesFromPM.t.sol:PoolManagerGetterTests
[PASS] testDeepFuzz_getEscrowParams_shouldReturnValues(uint256) (runs: 100, μ: 22047, ~: 21529)
[PASS] test_addressGetters() (gas: 37964)
[PASS] test_hasSufficientCover_insufficientCover(uint256) (runs: 100, μ: 141677, ~: 141177)
[PASS] test_hasSufficientCover_sufficientCover(uint256) (runs: 100, μ: 151749, ~: 152947)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 72.41ms

Running 4 tests for tests/integration/loan-manager/fixed-term/FinishCollateralLiquidation.t.sol:FinishCollateralLiquidationFailureTests
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 56983)
[PASS] test_finishCollateralLiquidation_notFinished() (gas: 653718)
[PASS] test_finishCollateralLiquidation_notPoolManager() (gas: 54784)
[PASS] test_finishCollateralLiquidation_whenImpaired() (gas: 288704)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 13.21ms

Running 1 test for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsPastDomainEnd
[PASS] test_makePayment_lateLoan3_loan1NotPaid_loan2NotPaid() (gas: 1039395)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 16.61ms

Running 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanAmortized
[PASS] test_makePayment_earlyPayment_amortized() (gas: 794011)
[PASS] test_makePayment_latePayment_amortized() (gas: 807282)
[PASS] test_makePayment_onTimePayment_amortized() (gas: 794039)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 22.00ms

Running 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanInterestOnly
[PASS] test_makePayment_earlyPayment_interestOnly() (gas: 765011)
[PASS] test_makePayment_latePayment_interestOnly() (gas: 775331)
[PASS] test_makePayment_onTimePayment_interestOnly() (gas: 762349)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 22.13ms

Running 4 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanOpenTerm
[PASS] test_makePayment_OT_latePayment() (gas: 731161)
[PASS] test_makePayment_OT_onTimePayment() (gas: 722871)
[PASS] test_makePayment_OT_withCall() (gas: 695219)
[PASS] test_makePayment_OT_withImpairment() (gas: 775817)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 17.84ms

Running 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsTwoLoans
[PASS] test_makePayment_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 1535332)
[PASS] test_makePayment_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 1549899)
[PASS] test_makePayment_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 1535471)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 30.15ms

Running 1 test for tests/fuzz/ProcessExit.t.sol:ProcessExitFuzzTests
[PASS] testFuzz_processExit(address[10],bool[10],uint256[10],uint256) (runs: 100, μ: 4036184, ~: 3965905)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 869.49ms

Running 1 test for tests/fuzz/Mint.t.sol:MintFuzzTests
[PASS] testDeepFuzz_mint_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 485097, ~: 514822)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 195.28ms

Running 1 test for tests/e2e/MultiLoanManager.t.sol:MultiLoanManagerTests
[PASS] test_4loans_3lps() (gas: 7495968)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 32.82ms

Running 11 tests for tests/fuzz/HasPermission.t.sol:HasPermissionFuzzTests
[PASS] testFuzz_hasPermission_deposit(uint256,uint256,uint256,bool,uint256) (runs: 100, μ: 396132, ~: 424043)
[PASS] testFuzz_hasPermission_depositWithPermit(uint256,uint256,uint256,bool,uint256) (runs: 100, μ: 410494, ~: 466677)
[PASS] testFuzz_hasPermission_mint(uint256,uint256,uint256,bool,uint256) (runs: 100, μ: 407479, ~: 426612)
[PASS] testFuzz_hasPermission_mintWithPermit(uint256,uint256,uint256,bool,uint256) (runs: 100, μ: 414705, ~: 469145)
[PASS] testFuzz_hasPermission_redeem(uint256,uint256,uint256,bool,uint256,address) (runs: 100, μ: 793011, ~: 808962)
[PASS] testFuzz_hasPermission_removeShares(uint256,uint256,uint256,bool,uint256,uint256) (runs: 100, μ: 784455, ~: 806036)
[PASS] testFuzz_hasPermission_requestRedeem(uint256,uint256,uint256,bool,uint256) (runs: 100, μ: 576878, ~: 638958)
[PASS] testFuzz_hasPermission_requestWithdraw(uint256,uint256,uint256,bool,uint256) (runs: 100, μ: 340382, ~: 370320)
[PASS] testFuzz_hasPermission_transfer(uint256,uint256,address,uint256,bool,address,uint256,bool,uint256) (runs: 100, μ: 557206, ~: 558142)
[PASS] testFuzz_hasPermission_transferFrom(uint256,uint256,address,uint256,bool,address,uint256,bool,address,uint256) (runs: 100, μ: 580952, ~: 582047)
[PASS] testFuzz_hasPermission_withdraw(uint256,uint256,uint256,bool,uint256,address) (runs: 100, μ: 305496, ~: 304801)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 1.21s

Running 4 tests for tests/protocol-upgrade/UpgradeTests.t.sol:UpgradeTestsETH
[PASS] testFork_upgradeAssertions_ETH() (gas: 64141463)
[PASS] testFork_upgradeFTL_fromNewFactory_ETH() (gas: 69266951)
[PASS] testFork_upgradeFTL_identicalFactory() (gas: 54415953)
[PASS] testFork_upgradeToQueueWM_ETH() (gas: 64882799)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.36s

Running 1 test for tests/integration/globals/ValidCollateral.t.sol:ValidCollateralTests
[PASS] test_setIsCollateral_invalidCollateral() (gas: 846368)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 15.02ms

Running 1 test for tests/health-checkers/HealthCheckersTests.t.sol:HealthCheckerMainnetTests
[PASS] testFork_healthChecker_mainnet() (gas: 66048664)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.28s

Running 2 tests for tests/fuzz/Call.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_call_otl(uint256) (runs: 100, μ: 11292269, ~: 11279448)
[PASS] testFuzz_removeCall_otl(uint256) (runs: 100, μ: 10814759, ~: 10858687)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.85s

Running 5 tests for tests/integration/loan/open-term/CallPrincipal.t.sol:CallPrincipalFailureTests
[PASS] test_callPrincipal_invalidAmount_boundary() (gas: 515659)
[PASS] test_callPrincipal_loanActive() (gas: 56561)
[PASS] test_callPrincipal_notLender() (gas: 38718)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 51563)
[PASS] test_callPrincipal_paused() (gas: 52465)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 13.84ms

Running 4 tests for tests/integration/loan/open-term/CallPrincipal.t.sol:CallPrincipalTests
[PASS] test_callPrincipal_impaired() (gas: 450536)
[PASS] test_callPrincipal_latePayment() (gas: 183253)
[PASS] test_callPrincipal_notFullPrincipal() (gas: 183131)
[PASS] test_callPrincipal_paymentOnTime() (gas: 182814)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 14.67ms

Running 5 tests for tests/integration/loan/fixed-term/CloseLoan.t.sol:CloseLoanTests
[PASS] test_closeLoan_failIfLoanIsLate() (gas: 112927)
[PASS] test_closeLoan_failIfNotEnoughFundsSent() (gas: 214414)
[PASS] test_closeLoan_failIfNotLoan() (gas: 66958)
[PASS] test_closeLoan_failWithInsufficientApproval() (gas: 123877)
[PASS] test_closeLoan_success() (gas: 498696)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 14.09ms

Running 4 tests for tests/integration/globals/Pause.t.sol:PauseTests
[PASS] test_contractPause() (gas: 5632566)
[PASS] test_functionUnpauseAfterContractPause() (gas: 46838006)
[PASS] test_functionUnpauseAfterProtocolPause() (gas: 46004581)
[PASS] test_globalPause() (gas: 8723787)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 256.93ms

Running 2 tests for tests/fuzz/OpenTermFuzz.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_otlFuzzedSetup_makePayment(uint256) (runs: 100, μ: 9970229, ~: 10055414)
[PASS] testFuzz_otlFuzzedSetup_triggerDefault(uint256) (runs: 100, μ: 9916502, ~: 9940619)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.68s

Running 1 test for tests/fuzz/ClosePoolFuzz.t.sol:ClosePoolFuzz
[PASS] testFuzz_fuzzedSetup_closePool(uint256) (runs: 100, μ: 21444946, ~: 21522365)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 5.74s

Running 2 tests for tests/fuzz/Impair.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_impair_otl(uint256) (runs: 100, μ: 11312113, ~: 11273788)
[PASS] testFuzz_removeImpairment_otl(uint256) (runs: 100, μ: 10760873, ~: 10761614)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.80s

Running 1 test for tests/invariants/PermissionInvariants.t.sol:PermissionInvariants
[PASS] statefulFuzz_permissionManager_A_B_C() (runs: 10, calls: 1000, reverts: 0)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 3.58s

Running 2 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:AutomatedPreviewRedeemWithQueueWMTests
[PASS] testFuzz_previewRedeem_notProcessed(uint256) (runs: 100, μ: 37196, ~: 37196)
[PASS] testFuzz_previewRedeem_processed(uint256) (runs: 100, μ: 311767, ~: 311767)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 88.54ms

Running 2 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:BalanceOfAssetsTests
[PASS] testDeepFuzz_balanceOfAssets(uint256,uint256,uint256) (runs: 100, μ: 456543, ~: 456426)
[PASS] test_balanceOfAssets() (gas: 446545)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 99.82ms

Running 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:ConvertToAssetsTests
[PASS] test_convertToAssets_multipleUsers() (gas: 503360)
[PASS] test_convertToAssets_multipleUsers_changeTotalAssets() (gas: 533011)
[PASS] test_convertToAssets_singleUser() (gas: 299073)
[PASS] test_convertToAssets_zeroTotalSupply() (gas: 12259)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 12.72ms

Running 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:ConvertToSharesTests
[PASS] test_convertToShares_multipleUsers() (gas: 503443)
[PASS] test_convertToShares_multipleUsers_changeTotalAssets() (gas: 533093)
[PASS] test_convertToShares_singleUser() (gas: 299111)
[PASS] test_convertToShares_zeroTotalSupply() (gas: 12319)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 19.05ms

Running 3 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxDepositTests
[PASS] testDeepFuzz_maxDeposit_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 271010, ~: 271186)
[PASS] test_maxDeposit_closedPool() (gas: 294348)
[PASS] test_maxDeposit_totalAssetsIncrease() (gas: 264453)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 59.62ms

Running 5 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxMintTests
[PASS] testDeepFuzz_maxMint_exchangeRateGtOne(uint256,uint256,uint256) (runs: 100, μ: 452268, ~: 452111)
[PASS] testDeepFuzz_maxMint_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 280431, ~: 280435)
[PASS] test_maxMint_closedPool() (gas: 307308)
[PASS] test_maxMint_exchangeRateGtOne() (gas: 442515)
[PASS] test_maxMint_totalAssetsIncrease() (gas: 273767)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 156.67ms

Running 3 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxRedeemTests
[PASS] test_maxRedeem_lockedShares_inExitWindow() (gas: 467178)
[PASS] test_maxRedeem_lockedShares_notInExitWindow() (gas: 456143)
[PASS] test_maxRedeem_noLockedShares_notInExitWindow() (gas: 289328)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 12.16ms

Running 6 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxRedeemWMQueueTests
[PASS] test_maxRedeem_afterFullManualRedeem() (gas: 361270)
[PASS] test_maxRedeem_afterFullRedeem() (gas: 239958)
[PASS] test_maxRedeem_afterPartialManualRedeem() (gas: 401116)
[PASS] test_maxRedeem_afterPartialRedeem() (gas: 243538)
[PASS] test_maxRedeem_beforeRedeem() (gas: 37709)
[PASS] test_maxRedeem_notManual() (gas: 393796)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.54ms

Running 11 tests for tests/e2e/PoolScenarios.t.sol:PoolScenarioTests
[PASS] testFuzz_poolScenarios_OTLWithBigPaymentInterval(uint256) (runs: 100, μ: 1048304, ~: 1048670)
[PASS] testFuzz_poolScenarios_exposeAccountedInterestDust(uint24,uint24) (runs: 100, μ: 1753125, ~: 1760679)
[PASS] testFuzz_poolScenarios_multipleOTLWithBigPaymentInterval(uint256,uint256,uint256) (runs: 100, μ: 38570040, ~: 38570330)
[PASS] test_poolScenario_fundLoanAndNeverTouchIt() (gas: 6042677)
[PASS] test_poolScenario_impairLoanWithLatePaymentAndRefinance() (gas: 2718237)
[PASS] test_poolScenario_loanWithVeryHighInterestRate() (gas: 1626372)
[PASS] test_poolScenario_loanWithZeroInterestRate() (gas: 2180623)
[PASS] test_poolScenario_loanWithZeroInterestRateAndDefaultWithCover() (gas: 1627192)
[PASS] test_poolScenarios_refinanceATwoPeriodsLateLoan() (gas: 2298933)
[PASS] test_poolScenarios_refinanceLateLoanAndDefault() (gas: 2053296)
[PASS] test_poolScenarios_stressTestAdvanceGlobalPaymentAccounting() (gas: 171641743)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 7.43s

Running 4 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairFailureTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 252682)
[PASS] test_impairLoan_notAuthorized() (gas: 57018)
[PASS] test_impairLoan_notLender() (gas: 37904)
[PASS] test_impairLoan_protocolPaused() (gas: 52148)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 12.77ms

Running 2 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairSuccessTests
[PASS] test_impairLoan_thenCancel() (gas: 901461)
[PASS] test_impairLoan_thenRepay() (gas: 918582)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 23.20ms

Running 9 tests for tests/integration/loan-manager/ImpairLoan.t.sol:OpenTermLoanManagerImpairTests
[PASS] testFail_impairLoan_notLoanContract() (gas: 40555)
[PASS] test_impairLoan_early() (gas: 240786)
[PASS] test_impairLoan_governorAcl() (gas: 127278)
[PASS] test_impairLoan_late() (gas: 242277)
[PASS] test_impairLoan_loanInactive() (gas: 230752)
[PASS] test_impairLoan_notAuthorized() (gas: 59427)
[PASS] test_impairLoan_notLender() (gas: 38326)
[PASS] test_impairLoan_notLoanInLoanManager() (gas: 477783)
[PASS] test_impairLoan_protocolPaused() (gas: 52148)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 14.42ms

Running 9 tests for tests/integration/loan-manager/ImpairLoan.t.sol:OpenTermLoanManagerRemoveImpairmentTests
[PASS] test_removeLoanImpairment_early() (gas: 258122)
[PASS] test_removeLoanImpairment_late() (gas: 259149)
[PASS] test_removeLoanImpairment_late_withLateImpairment() (gas: 259335)
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 72688)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 93697)
[PASS] test_removeLoanImpairment_notLender() (gas: 38392)
[PASS] test_removeLoanImpairment_notLoan() (gas: 41135)
[PASS] test_removeLoanImpairment_poolDelegateAfterGovernor() (gas: 153432)
[PASS] test_removeLoanImpairment_protocolPaused() (gas: 52148)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 15.22ms

Running 9 tests for tests/integration/pool/ConfigurePool.t.sol:ConfigurePoolTests
[PASS] testFuzz_configurePool(uint256,uint256,uint256[]) (runs: 100, μ: 2304431, ~: 1369220)
[PASS] test_configurePool_anotherPoolDelegate() (gas: 95125)
[PASS] test_configurePool_governor() (gas: 142190)
[PASS] test_configurePool_invalidLevel() (gas: 59113)
[PASS] test_configurePool_lengthMismatch() (gas: 84773)
[PASS] test_configurePool_notAuthorized() (gas: 60590)
[PASS] test_configurePool_operationalAdmin() (gas: 146448)
[PASS] test_configurePool_poolDelegate() (gas: 139857)
[PASS] test_configurePool_publicPool() (gas: 119190)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 328.40ms

Running 3 tests for tests/integration/loan/fixed-term/Liquidation.t.sol:FinishLiquidationFailureTests
[PASS] test_finishLiquidation_failIfLiquidationNotActive() (gas: 103041)
[PASS] test_finishLiquidation_failIfNotPD() (gas: 56982)
[PASS] test_finishLiquidation_failIfNotPoolManager() (gas: 54828)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 15.62ms

Running 14 tests for tests/integration/loan/fixed-term/Liquidation.t.sol:LoanLiquidationTests
[PASS] test_finishCollateralLiquidation_asOperationalAdmin() (gas: 2409779)
[PASS] test_loanDefault_fullCover_noCollateral_noImpairment() (gas: 1535076)
[PASS] test_loanDefault_fullCover_noCollateral_withImpairment() (gas: 1623336)
[PASS] test_loanDefault_fullCover_withCollateral_noImpairment() (gas: 2560432)
[PASS] test_loanDefault_fullCover_withCollateral_withImpairment() (gas: 2592892)
[PASS] test_loanDefault_noCover_noCollateral_noImpairment() (gas: 1425199)
[PASS] test_loanDefault_noCover_noCollateral_withImpairment() (gas: 1517565)
[PASS] test_loanDefault_noCover_withCollateral_noImpairment() (gas: 2464471)
[PASS] test_loanDefault_noCover_withCollateral_withImpairment() (gas: 2499027)
[PASS] test_loanDefault_partialCover_noCollateral_noImpairment() (gas: 1534798)
[PASS] test_loanDefault_partialCover_noCollateral_withImpairment() (gas: 1623316)
[PASS] test_loanDefault_partialCover_withCollateral_noImpairment() (gas: 2560004)
[PASS] test_loanDefault_partialCover_withCollateral_withImpairment() (gas: 2592837)
[PASS] test_setMaxCoverLiquidationPercent_asOperationalAdmin() (gas: 40498)
Test result: ok. 14 passed; 0 failed; 0 skipped; finished in 61.77ms

Running 5 tests for tests/integration/loan-manager/fixed-term/LoanManagerGetters.t.sol:LoanManagerGetterTests
[PASS] test_loanManagerGetters_addresses() (gas: 21380)
[PASS] test_loanManagerGetters_liquidationInformation() (gas: 1152403)
[PASS] test_loanManagerGetters_paymentInformation() (gas: 29855)
[PASS] test_loanManagerGetters_sortedPayments() (gas: 1334735)
[PASS] test_loanManagerGetters_uints() (gas: 32825)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 22.31ms

Running 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_failIfNotLoan() (gas: 69811)
[PASS] test_makePayment_failWithTransferFailed() (gas: 234917)
[PASS] test_makePayment_failWithTransferFromFailed() (gas: 143712)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 14.14ms

Running 9 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentOpenTermFailureTests
[PASS] test_makePayment_inactiveLoan() (gas: 474537)
[PASS] test_makePayment_invalidPrincipalIncrease() (gas: 55584)
[PASS] test_makePayment_notLoan() (gas: 517646)
[PASS] test_makePayment_tooLittlePrincipal() (gas: 139138)
[PASS] test_makePayment_tooMuchPrincipal() (gas: 44035)
[PASS] test_makePayment_transferFailed() (gas: 84789)
[PASS] test_makePayment_transferToPoolBoundary() (gas: 261647)
[PASS] test_makePayment_transferToPoolDelegateBoundary() (gas: 310080)
[PASS] test_makePayment_transferToTreasuryBoundary() (gas: 396715)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 16.74ms

Running 1 test for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsDomainStartGtDomainEnd
[PASS] test_makePayment_domainStart_gt_domainEnd() (gas: 3752761)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 21.61ms

Running 3 tests for tests/invariants/OpenTermInvariants.t.sol:OpenTermInvariants
[PASS] statefulFuzz_openTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_openTermLoanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] statefulFuzz_openTermLoan_A_B_C_D_E_F_G_H_I_openTermLoanManager_A_B_C_D_F_H_I_J_K() (runs: 10, calls: 1000, reverts: 0)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.43s

Running 6 tests for tests/integration/globals/OperationalAdmin.t.sol:OperationalAdminTests
[PASS] test_operationalAdminAcl_setMinCoverAmount() (gas: 50476)
[PASS] test_operationalAdminAcl_setPermissionAdmin() (gas: 68673)
[PASS] test_operationalAdminAcl_setPlatformManagementFeeRate() (gas: 52959)
[PASS] test_operationalAdminAcl_setPlatformOriginationFeeRate() (gas: 52978)
[PASS] test_operationalAdminAcl_setPlatformServiceFeeRate() (gas: 52957)
[PASS] test_operationalAdminAcl_setValidInstanceOf() (gas: 52055)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 10.31ms

Running 1 test for tests/fuzz/Withdraw.t.sol:WithdrawFuzzTests
[PASS] testDeepFuzz_withdraw_all(address,address,address,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 385890, ~: 387733)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 118.65ms

Running 1 test for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawOnPermissionedPool
[PASS] test_withdraw_withUnwhitelistedUser() (gas: 507145)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 11.46ms

Running 3 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawScenarios
[PASS] test_withdrawals_cashInjection() (gas: 5023015)
[PASS] test_withdrawals_poorExchangeRates() (gas: 4751370)
[PASS] test_withdrawals_withUpdateAccounting() (gas: 4749992)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 35.97ms

Running 7 tests for tests/e2e/WithdrawManagerScenario.t.sol:WithdrawalManagerScenarioTests
[PASS] test_scenario_fundPayAndRefinanceLoanWithPartialRedemptions_removeSharesAndCloseLoan() (gas: 3828403)
[PASS] test_scenario_impairLoanAndRedeem_defaultLoanAndWithdraw() (gas: 2645375)
[PASS] test_scenario_impairLoanAndRedeem_removeImpairAndRedeem() (gas: 2872307)
[PASS] test_scenario_impairLoanAndRedeem_removeSharesRepayLoanAndRedeem() (gas: 2644768)
[PASS] test_scenario_impairLoanAndRedeem_repayLoanAndWithdraw() (gas: 2747277)
[PASS] test_scenario_impairLoanAndRedeem_startLiquidationAndRedeem_finishLiquidationAndRedeem() (gas: 4092163)
[PASS] test_scenario_multipleUsers_impairLoanAndRedeem_repayLoanAndRedeem() (gas: 22738157)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 116.70ms

Running 1 test for tests/fuzz/ClosePoolFuzz.t.sol:ClosePoolFuzzWithWMQueue
[PASS] testFuzz_fuzzedSetup_closePool_withQueueWM(uint256) (runs: 100, μ: 22845597, ~: 22699523)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 6.00s

Running 1 test for tests/protocol-upgrade/ValidationLifecycle.t.sol:ValidationLifecycleForCashMgtBASEL2
[PASS] testFork_validationLifecycle_cash_USDC_BASEL2(uint256) (runs: 10, μ: 11121786, ~: 11077373)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 13.83s

Running 16 tests for tests/e2e/DelayedWithdrawal.t.sol:DelayedWithdrawalStartTests
[PASS] testFuzz_removeShares_afterStart(uint256) (runs: 100, μ: 7006865, ~: 7007050)
[PASS] testFuzz_removeShares_beforeStart(uint256) (runs: 100, μ: 7066208, ~: 7066395)
[PASS] testFuzz_removeShares_nextCycle(uint256) (runs: 100, μ: 7006910, ~: 7007096)
[PASS] testFuzz_removeShares_onStart(uint256) (runs: 100, μ: 7036025, ~: 7036202)
[PASS] testFuzz_requestRedeem_afterStart(uint256) (runs: 100, μ: 7013155, ~: 7013341)
[PASS] testFuzz_requestRedeem_beforeStart(uint256) (runs: 100, μ: 7075534, ~: 7075691)
[PASS] testFuzz_requestRedeem_nextCycle(uint256) (runs: 100, μ: 7013260, ~: 7013406)
[PASS] testFuzz_requestRedeem_onStart(uint256) (runs: 100, μ: 7043839, ~: 7043974)
[PASS] testFuzz_requestWithdraw_afterStart(uint256) (runs: 100, μ: 6887720, ~: 6887923)
[PASS] testFuzz_requestWithdraw_beforeStart(uint256) (runs: 100, μ: 6887764, ~: 6887917)
[PASS] testFuzz_requestWithdraw_nextCycle(uint256) (runs: 100, μ: 6887826, ~: 6887968)
[PASS] testFuzz_requestWithdraw_onStart(uint256) (runs: 100, μ: 6887692, ~: 6887818)
[PASS] testFuzz_setExitConfig_afterStart(uint256) (runs: 100, μ: 6878107, ~: 6878259)
[PASS] testFuzz_setExitConfig_beforeStart(uint256) (runs: 100, μ: 6877502, ~: 6877674)
[PASS] testFuzz_setExitConfig_nextCycle(uint256) (runs: 100, μ: 6878069, ~: 6878279)
[PASS] testFuzz_setExitConfig_onStart(uint256) (runs: 100, μ: 6877340, ~: 6877531)
Test result: ok. 16 passed; 0 failed; 0 skipped; finished in 4.09s

Running 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositWithPermitTests
[PASS] testFuzz_depositWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 393963, ~: 394187)
[PASS] testFuzz_depositWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 253846, ~: 254281)
[PASS] testFuzz_depositWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 569686, ~: 569127)
[PASS] test_depositWithPermit_exactBootstrapMintAmount() (gas: 368372)
[PASS] test_depositWithPermit_gtBootstrapMintAmount() (gas: 389066)
[PASS] test_depositWithPermit_ltBootstrapMintAmount() (gas: 297540)
[PASS] test_depositWithPermit_secondDepositorGetsCorrectShares() (gas: 565063)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 424.32ms

Running 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintTests
[PASS] testFuzz_mint_gtBootstrapMintAmount(uint256) (runs: 100, μ: 358457, ~: 358742)
[PASS] testFuzz_mint_ltBootstrapMintAmount(uint256) (runs: 100, μ: 259309, ~: 259685)
[PASS] testFuzz_mint_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 524612, ~: 523953)
[PASS] test_mint_exactBootstrapMintAmount() (gas: 332926)
[PASS] test_mint_gtBootstrapMintAmount() (gas: 353559)
[PASS] test_mint_ltBootstrapMintAmount() (gas: 254711)
[PASS] test_mint_secondDepositorGetsCorrectShares() (gas: 519887)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 209.45ms

Running 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintWithPermitTests
[PASS] testFuzz_mintWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 397774, ~: 398028)
[PASS] testFuzz_mintWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 255985, ~: 256428)
[PASS] testFuzz_mintWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 599028, ~: 598435)
[PASS] test_mintWithPermit_exactBootstrapMintAmount() (gas: 372146)
[PASS] test_mintWithPermit_gtBootstrapMintAmount() (gas: 392862)
[PASS] test_mintWithPermit_ltBootstrapMintAmount() (gas: 299896)
[PASS] test_mintWithPermit_secondDepositorGetsCorrectShares() (gas: 594369)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 463.17ms

Running 3 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:RequestWithdrawFailureTests
[PASS] test_requestWithdraw_failIfInsufficientApproval() (gas: 301020)
[PASS] test_requestWithdraw_failIfNotPM() (gas: 18940)
[PASS] test_requestWithdraw_failIfNotPool() (gas: 46215)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 11.94ms

Running 4 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:RequestWithdrawTests
[PASS] testDeepFuzz_requestWithdraw(uint256,uint256) (runs: 100, μ: 384895, ~: 387251)
[PASS] test_requestWithdraw() (gas: 358986)
[PASS] test_requestWithdraw_premature() (gas: 361766)
[PASS] test_requestWithdraw_withApproval() (gas: 373822)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 78.34ms

Running 5 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawFailureTests
[PASS] testDeepFuzz_withdraw(uint256,address,address) (runs: 100, μ: 78892, ~: 78892)
[PASS] test_withdraw_failIfNotPool() (gas: 46800)
[PASS] test_withdraw_failIfNotPoolManager() (gas: 19457)
[PASS] test_withdraw_premature() (gas: 83306)
[PASS] test_withdraw_zeroAssetInput() (gas: 80527)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 31.39ms

Running 1 test for tests/protocol-upgrade/ValidationLifecycle.t.sol:ValidationLifecycleBASEL2
[PASS] testFork_validationLifecycle_cashMgmtUSDCPool_BASEL2(uint256) (runs: 10, μ: 10447104, ~: 10062488)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 20.49s

Running 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositTests
[PASS] testFuzz_deposit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 355035, ~: 355293)
[PASS] testFuzz_deposit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 257280, ~: 257776)
[PASS] testFuzz_deposit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 495818, ~: 495231)
[PASS] test_deposit_exactBootstrapMintAmount() (gas: 329391)
[PASS] test_deposit_gtBootstrapMintAmount() (gas: 350132)
[PASS] test_deposit_ltBootstrapMintAmount() (gas: 252848)
[PASS] test_deposit_secondDepositorGetsCorrectShares() (gas: 491144)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 181.55ms

Running 27 tests for tests/invariants/DefaultsInvariants.t.sol:DefaultsInvariants
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
Test result: ok. 27 passed; 0 failed; 0 skipped; finished in 27.29s

Running 30 tests for tests/invariants/BasicInvariants.t.sol:BasicInvariants
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
Test result: ok. 30 passed; 0 failed; 0 skipped; finished in 40.39s

Running 2 tests for tests/protocol-upgrade/ValidationLifecycle.t.sol:ValidationLifecycleForCashMgtETH
[PASS] testFork_validationLifecycle_cash_USDC(uint256) (runs: 10, μ: 15083776, ~: 14623426)
[PASS] testFork_validationLifecycle_cash_USDT(uint256) (runs: 10, μ: 9847236, ~: 9877944)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 48.39s

Running 7 tests for tests/protocol-upgrade/ValidationLifecycle.t.sol:ValidationLifecycleETH
[PASS] testFork_validationLifecycle_aqruPool(uint256) (runs: 10, μ: 16621303, ~: 14727201)
[PASS] testFork_validationLifecycle_cashMgmtUSDCPool(uint256) (runs: 10, μ: 15813221, ~: 16686378)
[PASS] testFork_validationLifecycle_cashMgmtUSDTPool(uint256) (runs: 10, μ: 10159471, ~: 10314413)
[PASS] testFork_validationLifecycle_cicadaPool(uint256) (runs: 10, μ: 10822141, ~: 10625504)
[PASS] testFork_validationLifecycle_mapleDirectPool(uint256) (runs: 10, μ: 6927947, ~: 6927947)
[PASS] testFork_validationLifecycle_mavenPermissioned(uint256) (runs: 10, μ: 6874221, ~: 6876211)
[PASS] testFork_validationLifecycle_mavenWethPool(uint256) (runs: 10, μ: 6834593, ~: 6834593)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 60.73s

Running 25 tests for tests/invariants/WithdrawalManagerQueueInvariants.t.sol:WithdrawalManagerQueueInvariants
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
Test result: ok. 25 passed; 0 failed; 0 skipped; finished in 74.41s

Running 27 tests for tests/invariants/ImpairInvariants.t.sol:ImpairInvariants
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
Test result: ok. 27 passed; 0 failed; 0 skipped; finished in 76.74s

Running 2 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairAndRefinanceTests
[PASS] test_impairLoan_earlyThenRefinance() (gas: 1214775)
[PASS] test_impairLoan_lateThenRefinance() (gas: 978888)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 17.64ms
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

# `fixed-term-loan (v5.0.2)`

```
Running 4 tests for tests/MapleLoanFeeManager.t.sol:PayOriginationFeesTests
[PASS] test_payOriginationFees() (gas: 325744)
[PASS] test_payOriginationFees_insufficientFunds_poolDelegate() (gas: 180138)
[PASS] test_payOriginationFees_insufficientFunds_treasury() (gas: 212054)
[PASS] test_payOriginationFees_zeroTreasury() (gas: 212604)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.12ms

Running 2 tests for tests/InitializerAndMigrator.t.sol:MapleLoanInitializerAndMigratorTests
[PASS] test_initializer_setters() (gas: 97498)
[PASS] test_migration_ratesChange() (gas: 116106)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.31ms

Running 2 tests for tests/MapleLoanFeeManager.t.sol:PayServiceFeesTests
[PASS] test_payServiceFees() (gas: 275443)
[PASS] test_payServiceFees_zeroTreasury() (gas: 233615)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.11ms

Running 3 tests for tests/MapleLoan.t.sol:MapleLoanRoleTests
[PASS] test_transferBorrowerRole() (gas: 198810)
[PASS] test_transferBorrowerRole_failIfInvalidBorrower() (gas: 80422)
[PASS] test_transferLenderRole() (gas: 313231)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 6.55ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:UpdateDelegateFeeTermsTests
[PASS] test_updateDelegateFeeTerms() (gas: 109727)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.76ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:UpdatePlatformServiceFeeTests
[PASS] test_updatePlatformServiceFee() (gas: 1791371)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 2.99ms

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_SkimTests
[PASS] test_skimCollateralAsset() (gas: 84683)
[PASS] test_skimFundsAsset() (gas: 84705)
[PASS] test_skim_otherAsset() (gas: 1367911)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.72ms

Running 1 test for tests/MapleLoanRefinancer.t.sol:MapleLoanRefinancerMiscellaneousTests
[PASS] test_refinance_invalidRefinancer() (gas: 8941771)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 2.06ms

Running 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_AcceptNewTermsTests
[PASS] test_acceptNewTerms() (gas: 173043)
[PASS] test_acceptNewTerms_afterDeadline() (gas: 85217)
[PASS] test_acceptNewTerms_callFailed() (gas: 126121)
[PASS] test_acceptNewTerms_commitmentMismatch_emptyCallsArray() (gas: 80523)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedCalls() (gas: 82064)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 81867)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 81582)
[PASS] test_acceptNewTerms_insufficientCollateral() (gas: 349556)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 82056)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 3.71ms

Running 73 tests for tests/MapleLoan.t.sol:MapleLoanTests
[PASS] test_acceptBorrower_acl() (gas: 54137)
[PASS] test_acceptBorrower_failWhenPaused() (gas: 31258)
[PASS] test_acceptLender_acl() (gas: 52388)
[PASS] test_acceptLender_failWhenPaused() (gas: 31323)
[PASS] test_acceptNewTerms() (gas: 1615302)
[PASS] test_acceptNewTerms_acl() (gas: 1565235)
[PASS] test_acceptNewTerms_failWhenPaused() (gas: 33007)
[PASS] test_closeLoan_failWhenPaused() (gas: 32291)
[PASS] test_closeLoan_pullPatternAsBorrower() (gas: 1536806)
[PASS] test_closeLoan_pullPatternAsNonBorrower() (gas: 1539440)
[PASS] test_closeLoan_pullPatternUsingDrawable() (gas: 1552533)
[PASS] test_closeLoan_pushPatternAsBorrower() (gas: 1554351)
[PASS] test_closeLoan_pushPatternAsNonBorrower() (gas: 1554963)
[PASS] test_closeLoan_pushPatternUsingDrawable() (gas: 1519809)
[PASS] test_drawdownFunds_acl() (gas: 1478475)
[PASS] test_drawdownFunds_failWhenPaused() (gas: 32417)
[PASS] test_drawdownFunds_pullPatternForCollateral() (gas: 2937676)
[PASS] test_drawdownFunds_pushPatternForCollateral() (gas: 2916465)
[PASS] test_drawdownFunds_withoutAdditionalCollateralRequired() (gas: 2748747)
[PASS] test_excessCollateral_varyCollateral() (gas: 148007)
[PASS] test_excessCollateral_varyDrawableFunds() (gas: 131852)
[PASS] test_excessCollateral_varyPrincipal() (gas: 94808)
[PASS] test_fundLoan_failWhenPaused() (gas: 31552)
[PASS] test_fundLoan_pushPattern() (gas: 1636999)
[PASS] test_getAdditionalCollateralRequiredFor_varyAmount() (gas: 134587)
[PASS] test_getAdditionalCollateralRequiredFor_varyCollateralRequired() (gas: 118935)
[PASS] test_getAdditionalCollateralRequiredFor_varyDrawableFunds() (gas: 121624)
[PASS] test_getAdditionalCollateralRequiredFor_varyPrincipal() (gas: 142781)
[PASS] test_impairLoan() (gas: 82062)
[PASS] test_impairLoan_acl() (gas: 94764)
[PASS] test_impairLoan_failWhenPaused() (gas: 31319)
[PASS] test_impairLoan_lateLoan() (gas: 82205)
[PASS] test_makePayment_failWhenPaused() (gas: 32380)
[PASS] test_makePayment_pullPatternAsBorrower() (gas: 1599377)
[PASS] test_makePayment_pullPatternAsNonBorrower() (gas: 1601674)
[PASS] test_makePayment_pullPatternUsingDrawable() (gas: 1643907)
[PASS] test_makePayment_pushPatternAsBorrower() (gas: 1605437)
[PASS] test_makePayment_pushPatternAsNonBorrower() (gas: 1605710)
[PASS] test_makePayment_pushPatternUsingDrawable() (gas: 1611223)
[PASS] test_migrate_acl() (gas: 90384)
[PASS] test_migrate_failWhenPaused() (gas: 32454)
[PASS] test_postCollateral_failWhenPaused() (gas: 32008)
[PASS] test_postCollateral_pullPattern() (gas: 1450460)
[PASS] test_postCollateral_pushPattern() (gas: 1400098)
[PASS] test_proposeNewTerms() (gas: 111580)
[PASS] test_proposeNewTerms_acl() (gas: 132458)
[PASS] test_proposeNewTerms_failWhenPaused() (gas: 33053)
[PASS] test_proposeNewTerms_invalidDeadline() (gas: 132539)
[PASS] test_rejectNewTerms_acl() (gas: 142340)
[PASS] test_rejectNewTerms_failWhenPaused() (gas: 33095)
[PASS] test_removeCollateral_acl() (gas: 1436838)
[PASS] test_removeCollateral_failWhenPaused() (gas: 32079)
[PASS] test_removeLoanImpairment_acl() (gas: 75680)
[PASS] test_removeLoanImpairment_failWhenPaused() (gas: 31343)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 32254)
[PASS] test_removeLoanImpairment_pastDate() (gas: 54390)
[PASS] test_removeLoanImpairment_success() (gas: 61041)
[PASS] test_repossess_acl() (gas: 1418308)
[PASS] test_repossess_failWhenPaused() (gas: 32303)
[PASS] test_returnFunds_failWhenPaused() (gas: 32030)
[PASS] test_returnFunds_pullPattern() (gas: 1450591)
[PASS] test_returnFunds_pushPattern() (gas: 1400165)
[PASS] test_setImplementation_acl() (gas: 110452)
[PASS] test_setImplementation_failWhenPaused() (gas: 31809)
[PASS] test_setPendingBorrower_acl() (gas: 97821)
[PASS] test_setPendingBorrower_failWhenPaused() (gas: 31744)
[PASS] test_setPendingLender_acl() (gas: 73701)
[PASS] test_setPendingLender_failWhenPaused() (gas: 31833)
[PASS] test_skim_failWhenPaused() (gas: 32409)
[PASS] test_upgrade_acl_noAuth() (gas: 6375734)
[PASS] test_upgrade_acl_noAuth_asBorrower() (gas: 6378568)
[PASS] test_upgrade_acl_securityAdmin() (gas: 6410403)
[PASS] test_upgrade_failWhenPaused() (gas: 32122)
Test result: ok. 73 passed; 0 failed; 0 skipped; finished in 23.95ms

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CollateralMaintainedTests
[PASS] test_isCollateralMaintained(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 122484, ~: 125787)
[PASS] test_isCollateralMaintained_edgeCases() (gas: 195305)
[PASS] test_isCollateralMaintained_roundUp() (gas: 85571)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 38.41ms

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ProposeNewTermsTests
[PASS] test_proposeNewTerms(address,uint256,uint256,uint256,uint256) (runs: 256, μ: 81641, ~: 82007)
[PASS] test_proposeNewTerms_emptyArray(address,uint256) (runs: 256, μ: 38433, ~: 38074)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 83503)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 102.16ms

Running 5 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RejectNewTermsTests
[PASS] test_rejectNewTerms() (gas: 65242)
[PASS] test_rejectNewTerms_commitmentMismatch_emptyCallsArray() (gas: 75630)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedCalls() (gas: 77242)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 77156)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 729550)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.60ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetNextPaymentBreakdownTests
[PASS] test_getNextPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 717577, ~: 720180)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 121.28ms

Running 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPaymentBreakdownTests
[PASS] test_getPaymentBreakdown_onePaymentFourPeriodsLate() (gas: 38349)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodBeforeDue() (gas: 35274)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodLate() (gas: 38371)
[PASS] test_getPaymentBreakdown_onePaymentOneSecondBeforeDue() (gas: 35339)
[PASS] test_getPaymentBreakdown_onePaymentThreePeriodsLate() (gas: 38304)
[PASS] test_getPaymentBreakdown_onePaymentTwoPeriodsLate() (gas: 38326)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 1.45ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPeriodicInterestRateTests
[PASS] test_getPeriodicInterestRate() (gas: 10439)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 807.29µs

Running 10 tests for tests/MapleLoanFactory.t.sol:MapleLoanFactoryTest
[PASS] testFail_createInstance_saltAndArgumentsCollision() (gas: 8937393460516746255)
[PASS] test_createInstance(bytes32) (runs: 256, μ: 553156, ~: 553156)
[PASS] test_createInstance_differentFundsAsset() (gas: 774618)
[PASS] test_createInstance_invalidCaller() (gas: 553955)
[PASS] test_createInstance_invalidCollateralAsset() (gas: 746669)
[PASS] test_createInstance_invalidFactory() (gas: 778547)
[PASS] test_createInstance_invalidInstance() (gas: 784509)
[PASS] test_createInstance_invalidPoolAsset() (gas: 742911)
[PASS] test_createInstance_zeroLender() (gas: 770354)
[PASS] test_isLoan_withOldFactory() (gas: 1087360)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 128.01ms

Running 2 tests for tests/MapleLoanFeeManager.t.sol:GetterTests
[PASS] test_getDelegateServiceFeesForPeriod() (gas: 717324)
[PASS] test_getPlatformServiceFeeForPeriod() (gas: 1030475)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 4.48ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:PayClosingFeesTests
[PASS] test_payClosingServiceFees() (gas: 276172)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 4.03ms

Running 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_DrawdownFundsTests
[PASS] test_drawdownFunds_collateralNotMaintained(uint256,uint256,uint256) (runs: 256, μ: 264793, ~: 273892)
[PASS] test_drawdownFunds_insufficientDrawableFunds(uint256,uint256) (runs: 256, μ: 157533, ~: 157711)
[PASS] test_drawdownFunds_multipleDrawdowns(uint256,uint256,uint256) (runs: 256, μ: 278346, ~: 278073)
[PASS] test_drawdownFunds_postedCollateral(uint256,uint256,uint256) (runs: 256, μ: 290041, ~: 294703)
[PASS] test_drawdownFunds_transferFailed() (gas: 55568)
[PASS] test_drawdownFunds_withoutPostedCollateral(uint256,uint256) (runs: 256, μ: 194910, ~: 199139)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 329.60ms

Running 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceGracePeriodTests
[PASS] test_refinance_gracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9136901, ~: 9143499)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 434.66ms

Running 12 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetUnaccountedAmountTests
[PASS] test_getUnaccountedAmount_collateral(uint256,uint256) (runs: 256, μ: 90969, ~: 91194)
[PASS] test_getUnaccountedAmount_collateralAsset() (gas: 80962)
[PASS] test_getUnaccountedAmount_complex(uint256,uint256,uint256) (runs: 256, μ: 1390610, ~: 1392054)
[PASS] test_getUnaccountedAmount_drawableFunds(uint256,uint256) (runs: 256, μ: 90893, ~: 91085)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral(uint256,uint256,uint256,uint256) (runs: 256, μ: 172945, ~: 172636)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral_fundsAssetEqCollateralAsset(uint256,uint256,uint256) (runs: 256, μ: 120183, ~: 120067)
[PASS] test_getUnaccountedAmount_fundsAsset() (gas: 80963)
[PASS] test_getUnaccountedAmount_newFundsLtCollateral(uint256) (runs: 256, μ: 108766, ~: 108715)
[PASS] test_getUnaccountedAmount_newFundsLtDrawableFunds(uint256) (runs: 256, μ: 108797, ~: 108767)
[PASS] test_getUnaccountedAmount_randomToken() (gas: 120830)
[PASS] test_getUnaccountedAmount_withCollateral(uint256,uint256) (runs: 256, μ: 86255, ~: 89823)
[PASS] test_getUnaccountedAmount_withDrawableFunds(uint256,uint256) (runs: 256, μ: 85827, ~: 89716)
Test result: ok. 12 passed; 0 failed; 0 skipped; finished in 428.65ms

Running 1 test for tests/MapleLoanRefinancer.t.sol:MapleLoanRefinancerMultipleParameterTests
[PASS] test_refinance_multipleParameters(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9211070, ~: 9208298)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 545.17ms

Running 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_InitializeTests
[PASS] test_initialize() (gas: 8781172)
[PASS] test_initialize_invalidBorrower() (gas: 2103565)
[PASS] test_initialize_invalidEndingPrincipal() (gas: 2066710)
[PASS] test_initialize_invalidGracePeriodBoundary() (gas: 10763693)
[PASS] test_initialize_invalidOriginationFeeBoundary() (gas: 10764653)
[PASS] test_initialize_invalidPaymentInterval() (gas: 2073255)
[PASS] test_initialize_invalidPaymentsRemaining() (gas: 2073245)
[PASS] test_initialize_invalidPrincipal() (gas: 2066504)
[PASS] test_initialize_zeroBorrower() (gas: 2077297)
Test result: ok. 9 passed; 0 failed; 0 skipped; finished in 7.08ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CloseLoanTests
[PASS] test_closeLoan(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 295755, ~: 296779)
[PASS] test_closeLoan_amountSmallerThanFees() (gas: 465182)
[PASS] test_closeLoan_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 361672, ~: 362112)
[PASS] test_closeLoan_latePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 301777, ~: 303124)
[PASS] test_closeLoan_noAmount() (gas: 457636)
[PASS] test_closeLoan_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 303534, ~: 304592)
[PASS] test_closeLoan_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 298117, ~: 298349)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 570.24ms

Running 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceCollateralRequiredTests
[PASS] test_refinance_collateralRequired(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9182324, ~: 9184921)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 523.06ms

Running 11 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_FundLoanTests
[PASS] test_fundLoan_approveFail() (gas: 328340)
[PASS] test_fundLoan_doubleFund(uint256) (runs: 256, μ: 279828, ~: 279510)
[PASS] test_fundLoan_fullFunding(uint256) (runs: 256, μ: 302095, ~: 301796)
[PASS] test_fundLoan_fullFundingWithExistingDrawableFunds(uint256) (runs: 256, μ: 303844, ~: 303560)
[PASS] test_fundLoan_invalidFundsAsset() (gas: 1500654)
[PASS] test_fundLoan_nextPaymentDueDateAlreadySet() (gas: 176749)
[PASS] test_fundLoan_noPaymentsRemaining() (gas: 85076)
[PASS] test_fundLoan_notLender() (gas: 27441)
[PASS] test_fundLoan_partialFunding(uint256) (runs: 256, μ: 223466, ~: 225934)
[PASS] test_fundLoan_withUnaccountedCollateralAsset() (gas: 1617536)
[PASS] test_fundLoan_withoutSendingAsset() (gas: 179180)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 284.17ms

Running 4 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_PostCollateralTests
[PASS] test_postCollateral_invalidCollateralAsset() (gas: 1363504)
[PASS] test_postCollateral_multiple(uint256,uint256) (runs: 256, μ: 169534, ~: 167464)
[PASS] test_postCollateral_once(uint256) (runs: 256, μ: 101316, ~: 105250)
[PASS] test_postCollateral_withUnaccountedFundsAsset() (gas: 1452368)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 175.52ms

Running 3 tests for tests/MapleLoanScenarios.t.sol:MapleLoanScenariosTests
[PASS] test_scenario_fullyAmortized() (gas: 9304083)
[PASS] test_scenario_interestOnly() (gas: 9289285)
[PASS] test_scenario_lateLoanRefinanceInterest() (gas: 8977266)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 8.70ms

Running 3 tests for tests/MapleLoanV502Migrator.t.sol:MapleLoanV502MigratorTests
[PASS] test_migration_factoryChange() (gas: 2982173)
[PASS] test_migration_invalidFactory() (gas: 2957176)
[PASS] test_migration_sameFactory_noOp() (gas: 2947648)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.34ms

Running 2 tests for tests/Payments.t.sol:ClosingTests
[PASS] test_payments_closing_flatRate_case1() (gas: 1399383)
[PASS] test_payments_closing_flatRate_case2() (gas: 1254176)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 5.82ms

Running 2 tests for tests/Payments.t.sol:FullyAmortizedPaymentsTests
[PASS] test_payments_fullyAmortized_case1() (gas: 1667031)
[PASS] test_payments_fullyAmortized_case2() (gas: 1666980)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 9.77ms

Running 2 tests for tests/Payments.t.sol:InterestOnlyPaymentsTests
[PASS] test_payments_interestOnly_case1() (gas: 1682655)
[PASS] test_payments_interestOnly_case2() (gas: 1682909)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 14.41ms

Running 5 tests for tests/Payments.t.sol:LateRepaymentsTests
[PASS] test_payments_dailyInterestAccrual() (gas: 1038874)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case1() (gas: 1672084)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case2() (gas: 1681033)
[PASS] test_payments_lateRepayment_flatRate_case1() (gas: 1673397)
[PASS] test_payments_lateRepayment_flatRate_case2() (gas: 1669087)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 31.40ms

Running 2 tests for tests/Payments.t.sol:PartiallyAmortizedPaymentsTests
[PASS] test_payments_partiallyAmortized_case1() (gas: 1682884)
[PASS] test_payments_partiallyAmortized_case2() (gas: 1682917)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 8.78ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetCollateralRequiredForTests
[PASS] test_getCollateralRequiredFor() (gas: 21660)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 708.21µs

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInstallmentTests
[PASS] test_getInstallment_edgeCases() (gas: 28204)
[PASS] test_getInstallment_genericFuzzing(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 18193, ~: 18299)
[PASS] test_getInstallment_withFixtures() (gas: 14169)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 43.76ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInterestTests
[PASS] test_getInterest() (gas: 11862)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 649.71µs

Running 11 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RemoveCollateralTests
[PASS] test_removeCollateral_cannotRemoveAnyAmountWithEncumbrances() (gas: 200329)
[PASS] test_removeCollateral_cannotRemoveFullAmountWithEncumbrances(uint256) (runs: 256, μ: 160902, ~: 160869)
[PASS] test_removeCollateral_cannotRemovePartialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 201841, ~: 202156)
[PASS] test_removeCollateral_fullAmountWithNoEncumbrances(uint256) (runs: 256, μ: 125103, ~: 125082)
[PASS] test_removeCollateral_fullAmount_drawableFundsGtPrincipal(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 189270, ~: 191864)
[PASS] test_removeCollateral_fullAmount_noPrincipal(uint256) (runs: 256, μ: 144361, ~: 144337)
[PASS] test_removeCollateral_insufficientCollateralWithNoEncumbrances(uint256) (runs: 256, μ: 116403, ~: 121496)
[PASS] test_removeCollateral_partialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 246609, ~: 250116)
[PASS] test_removeCollateral_partialAmountWithNoEncumbrances(uint256,uint256) (runs: 256, μ: 160224, ~: 163163)
[PASS] test_removeCollateral_sameAssetAsFundingAsset(uint256) (runs: 256, μ: 149054, ~: 148981)
[PASS] test_removeCollateral_transferFailed() (gas: 295873)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 803.52ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RepossessTests
[PASS] test_repossess() (gas: 152016)
[PASS] test_repossess_beforePaymentDue() (gas: 57141)
[PASS] test_repossess_collateralTransferFailed() (gas: 310795)
[PASS] test_repossess_fundsTransferFailed() (gas: 343505)
[PASS] test_repossess_onGracePeriod() (gas: 57157)
[PASS] test_repossess_onPaymentDue() (gas: 56903)
[PASS] test_repossess_withinGracePeriod() (gas: 57112)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.84ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetClosingPaymentBreakdownTests
[PASS] test_getClosingPaymentBreakdown(uint256,uint256,uint256) (runs: 256, μ: 8807000, ~: 8806952)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 313.32ms

Running 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ReturnFundsTests
[PASS] test_returnFunds(uint256) (runs: 256, μ: 127502, ~: 130617)
[PASS] test_returnFundsCollateralAsset() (gas: 1390024)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 62.60ms

Running 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ScaledExponentTests
[PASS] test_scaledExponent_setOne() (gas: 40312)
[PASS] test_scaledExponent_setTwo() (gas: 71120)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.19ms

Running 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceInterestRateTests
[PASS] test_refinance_interestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9141076, ~: 9144358)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 547.38ms

Running 1 test for tests/MapleLoanRefinancer.t.sol:RefinanceInterestTests
[PASS] test_acceptNewTerms_makePayment_withRefinanceInterest() (gas: 9202992)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 2.55ms

Running 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePaymentIntervalTests
[PASS] test_refinance_paymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9141272, ~: 9146341)
[PASS] test_refinance_paymentInterval_zeroAmount() (gas: 9093728)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 429.88ms

Running 2 tests for tests/MapleLoanRefinancer.t.sol:RefinanceDeadlineTests
[PASS] test_refinance_afterDeadline(uint256,uint256,uint256) (runs: 256, μ: 9093478, ~: 9093467)
[PASS] test_refinance_differentDeadline(uint256,uint256,uint256) (runs: 256, μ: 9067203, ~: 9067259)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 921.61ms

Running 3 tests for tests/MapleLoanRefinancer.t.sol:RefinanceFeeTests
[PASS] test_refinance_closingRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9140407, ~: 9145207)
[PASS] test_refinance_lateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9140740, ~: 9145205)
[PASS] test_refinance_lateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9161743, ~: 9165574)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 952.43ms

Running 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePaymentsRemainingTests
[PASS] test_refinance_paymentRemaining(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9143132, ~: 9146389)
[PASS] test_refinance_paymentRemaining_zeroAmount() (gas: 9093730)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 363.81ms

Running 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePrincipalRequestedTests
[PASS] test_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9220334, ~: 9223565)
[PASS] test_refinance_increasePrincipalRequestedWithInsufficientFunds(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9154101, ~: 9158021)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 921.40ms

Running 3 tests for tests/MapleLoanRefinancer.t.sol:RefinanceEndingPrincipalTests
[PASS] test_refinance_endingPrincipal_amortizedToInterestOnly(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9172716, ~: 9176457)
[PASS] test_refinance_endingPrincipal_failLargerThanPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9119813, ~: 9128706)
[PASS] test_refinance_endingPrincipal_interestOnlyToAmortized(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9167306, ~: 9174015)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.83s

Running 7 tests for tests/MapleLoanRefinancer.t.sol:RefinancingFeesTerms
[PASS] testFuzz_refinance_payOriginationFees(uint256,uint256) (runs: 256, μ: 10699172, ~: 10699201)
[PASS] testFuzz_refinance_pdOriginationFeeTransferFail(uint256) (runs: 256, μ: 10609988, ~: 10611573)
[PASS] testFuzz_refinance_treasuryOriginationFeeTransferFail(uint256,uint256) (runs: 256, μ: 10625460, ~: 10625520)
[PASS] testFuzz_refinance_updateFeeTerms(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 10646427, ~: 10651175)
[PASS] testFuzz_refinance_updatesPlatformServiceFees(uint256) (runs: 256, μ: 10609375, ~: 10609001)
[PASS] test_refinance_updateRefinanceServiceFees() (gas: 10691635)
[PASS] test_refinance_updateRefinanceServiceFeesOnDoubleRefinance() (gas: 10794126)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 851.16ms

Running 8 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_MakePaymentTests
[PASS] test_makePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 385177, ~: 390618)
[PASS] test_makePayment_amountSmallerThanFees() (gas: 490238)
[PASS] test_makePayment_collateralNotMaintained() (gas: 874571)
[PASS] test_makePayment_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 412898, ~: 418173)
[PASS] test_makePayment_lastPaymentClearsLoan(uint256,uint256,uint256,uint256) (runs: 256, μ: 366627, ~: 368558)
[PASS] test_makePayment_noAmount() (gas: 480759)
[PASS] test_makePayment_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 389441, ~: 395437)
[PASS] test_makePayment_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 374438, ~: 375482)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 1.41s
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

# `open-term-loan (v1.0.1)`

```
Running 2 tests for tests/IsInDefault.t.sol:DefaultDatesTests
[PASS] test_isInDefault_successBoundary() (gas: 37684)
[PASS] test_isInDefault_zeroDefaultDate() (gas: 10397)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 5.21ms

Running 4 tests for tests/Getter.t.sol:GetterTests
[PASS] test_factory_getter() (gas: 10412)
[PASS] test_globals_getter() (gas: 16121)
[PASS] test_isCalled_getter() (gas: 31044)
[PASS] test_isImpaied_getter() (gas: 31049)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 6.53ms

Running 3 tests for tests/AcceptBorrower.t.sol:AcceptBorrowerTests
[PASS] test_acceptBorrower_notPendingBorrower() (gas: 48700)
[PASS] test_acceptBorrower_paused() (gas: 46171)
[PASS] test_acceptBorrower_success() (gas: 57276)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 6.77ms

Running 5 tests for tests/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_insufficientForCalled() (gas: 107205)
[PASS] test_makePayment_insufficientForTotalTransferFromCaller() (gas: 1528122)
[PASS] test_makePayment_notFunded() (gas: 26462)
[PASS] test_makePayment_paused() (gas: 47491)
[PASS] test_makePayment_returningTooMuch() (gas: 85882)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 7.57ms

Running 3 tests for tests/AcceptLender.t.sol:AcceptLenderTests
[PASS] test_acceptLender_notPendingLender() (gas: 48654)
[PASS] test_acceptLender_paused() (gas: 46191)
[PASS] test_acceptLender_success() (gas: 57219)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.03ms

Running 6 tests for tests/Fund.t.sol:FundTests
[PASS] testFuzz_fund_success() (gas: 1612848)
[PASS] test_fund_loanActive() (gas: 52081)
[PASS] test_fund_loanClosed() (gas: 32833)
[PASS] test_fund_notLender() (gas: 25763)
[PASS] test_fund_paused() (gas: 46871)
[PASS] test_fund_revertingTransfer() (gas: 1518939)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 7.90ms

Running 7 tests for tests/AcceptNewTerms.t.sol:AcceptNewTermsFailure
[PASS] test_acceptNewTerms_expiredCommitmentBoundary() (gas: 3081976)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 56424)
[PASS] test_acceptNewTerms_mismatchedCommitment() (gas: 37350)
[PASS] test_acceptNewTerms_notBorrower() (gas: 26966)
[PASS] test_acceptNewTerms_paused() (gas: 48074)
[PASS] test_acceptNewTerms_refinancerRevert() (gas: 101462)
[PASS] test_acceptNewTerms_transferRevert() (gas: 1294754)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 3.27ms

Running 11 tests for tests/Initializer.t.sol:InitializerTests
[PASS] test_initialize_differentFundsAsset() (gas: 115879)
[PASS] test_initialize_invalidBorrower() (gas: 57213)
[PASS] test_initialize_invalidFundsAsset() (gas: 60950)
[PASS] test_initialize_invalidLenderFactory() (gas: 1760572)
[PASS] test_initialize_invalidLenderFactoryInstance() (gas: 1790211)
[PASS] test_initialize_invalidNoticePeriod() (gas: 22386)
[PASS] test_initialize_invalidPaymentInterval() (gas: 22435)
[PASS] test_initialize_invalidPrincipal() (gas: 22274)
[PASS] test_initialize_success() (gas: 301774)
[PASS] test_initialize_zeroBorrower() (gas: 28478)
[PASS] test_initialize_zeroLender() (gas: 60694)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 9.47ms

Running 4 tests for tests/RemoveImpairment.t.sol:RemoveImpairmentTests
[PASS] testFuzz_removeImpairment_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 102024, ~: 102069)
[PASS] test_removeImpairment_notImpaired() (gas: 30580)
[PASS] test_removeImpairment_notLender() (gas: 25678)
[PASS] test_removeImpairment_paused() (gas: 46763)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 74.89ms

Running 1 test for tests/DefaultDates.t.sol:DefaultDatesTests
[PASS] testFuzz_defaultDates(uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 74121, ~: 74107)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 73.46ms

Running 6 tests for tests/Repossess.t.sol:RepossessTests
[PASS] test_repossess_notInDefault() (gas: 57169)
[PASS] test_repossess_notLender() (gas: 28116)
[PASS] test_repossess_paused() (gas: 49177)
[PASS] test_repossess_revertingToken() (gas: 1429087)
[PASS] test_repossess_success() (gas: 1620879)
[PASS] test_repossess_success_noTransfer() (gas: 1474707)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 4.04ms

Running 7 tests for tests/ProposeNewTerms.t.sol:ProposeNewTermsTests
[PASS] test_proposeNewTerms_deadlineBoundary() (gas: 113114)
[PASS] test_proposeNewTerms_emptyCalls() (gas: 63942)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 39660)
[PASS] test_proposeNewTerms_notFunded() (gas: 33675)
[PASS] test_proposeNewTerms_notLender() (gas: 26924)
[PASS] test_proposeNewTerms_paused() (gas: 48031)
[PASS] test_proposeNewTerms_success() (gas: 116291)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.72ms

Running 4 tests for tests/Impair.t.sol:ImpairTests
[PASS] testFuzz_impair_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 105178, ~: 105076)
[PASS] test_impair_loanNotFunded() (gas: 30539)
[PASS] test_impair_notLender() (gas: 25614)
[PASS] test_impair_paused() (gas: 46743)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 87.80ms

Running 3 tests for tests/Migrate.t.sol:MigrateTests
[PASS] test_migrate_notFactory() (gas: 24476)
[PASS] test_migrate_paused() (gas: 47477)
[PASS] test_migrate_success() (gas: 71035)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 901.88µs

Running 3 tests for tests/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 23631)
[PASS] test_setImplementation_paused() (gas: 46721)
[PASS] test_setImplementation_success() (gas: 93336)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.47ms

Running 4 tests for tests/SetPendingBorrower.t.sol:SetPendingBorrowerTests
[PASS] test_setPendingBorrower_invalidBorrower() (gas: 35716)
[PASS] test_setPendingBorrower_notBorrower() (gas: 27751)
[PASS] test_setPendingBorrower_paused() (gas: 48815)
[PASS] test_setPendingBorrower_success() (gas: 85269)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.15ms

Running 3 tests for tests/SetPendingLender.t.sol:SetPendingLenderTests
[PASS] test_setPendingLender_notLender() (gas: 27819)
[PASS] test_setPendingLender_paused() (gas: 48880)
[PASS] test_setPendingLender_success() (gas: 77898)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.02ms

Running 4 tests for tests/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 28683)
[PASS] test_upgrade_noAuth_asBorrower() (gas: 31314)
[PASS] test_upgrade_paused() (gas: 49842)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 234759)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.31ms

Running 5 tests for tests/RejectNewTerms.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_mismatchedCommitment() (gas: 34620)
[PASS] test_rejectNewTerms_notBorrowerNorLender() (gas: 31219)
[PASS] test_rejectNewTerms_paused() (gas: 50121)
[PASS] test_rejectNewTerms_success_asBorrower() (gas: 47738)
[PASS] test_rejectNewTerms_success_asLender() (gas: 49962)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 1.38ms

Running 7 tests for tests/Skim.t.sol:SkimTests
[PASS] test_skim_borrower() (gas: 1484641)
[PASS] test_skim_governor() (gas: 1482504)
[PASS] test_skim_noTokenToSkim() (gas: 1334648)
[PASS] test_skim_notBorrower() (gas: 31270)
[PASS] test_skim_paused() (gas: 32489)
[PASS] test_skim_revertingToken() (gas: 1411849)
[PASS] test_skim_zeroAddress() (gas: 24198)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 7.38ms

Running 6 tests for tests/CallPrincipal.t.sol:CallPrincipalTests
[PASS] testFuzz_callPrincipal_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 136513, ~: 136525)
[PASS] test_callPrincipal_insufficientPrincipalToReturn() (gas: 52500)
[PASS] test_callPrincipal_loanNotFunded() (gas: 31037)
[PASS] test_callPrincipal_notLender() (gas: 26111)
[PASS] test_callPrincipal_paused() (gas: 47195)
[PASS] test_callPrincipal_principalToReturnBoundary() (gas: 106936)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 90.21ms

Running 11 tests for tests/GetPaymentBreakdown.t.sol:GetPaymentBreakdownTests
[PASS] testFuzz_getPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 288033, ~: 285367)
[PASS] test_getPaymentBreakdown_fixture1() (gas: 206243)
[PASS] test_getPaymentBreakdown_fixture10() (gas: 119128)
[PASS] test_getPaymentBreakdown_fixture2() (gas: 205994)
[PASS] test_getPaymentBreakdown_fixture3() (gas: 182050)
[PASS] test_getPaymentBreakdown_fixture4() (gas: 216260)
[PASS] test_getPaymentBreakdown_fixture5() (gas: 205135)
[PASS] test_getPaymentBreakdown_fixture6() (gas: 206645)
[PASS] test_getPaymentBreakdown_fixture7() (gas: 206827)
[PASS] test_getPaymentBreakdown_fixture8() (gas: 206878)
[PASS] test_getPaymentBreakdown_fixture9() (gas: 118848)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 105.18ms

Running 1 test for tests/DueDates.t.sol:DueDatesTests
[PASS] testFuzz_dueDates(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 69299, ~: 69517)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 79.30ms

Running 2 tests for tests/Factory.t.sol:FactoryTests
[PASS] test_createInstance(bytes32) (runs: 256, μ: 442847, ~: 442847)
[PASS] test_createInstance_cannotDeploy(bytes32) (runs: 256, μ: 44461, ~: 44461)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 158.66ms

Running 4 tests for tests/RemoveCall.t.sol:RemoveCallTests
[PASS] testFuzz_removeCall_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 107034, ~: 107085)
[PASS] test_removeCall_notCalled() (gas: 30493)
[PASS] test_removeCall_notLender() (gas: 25636)
[PASS] test_removeCall_paused() (gas: 46742)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 101.08ms

Running 10 tests for tests/Refinancer.t.sol:RefinancerTests
[PASS] test_refinancer_decreasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143511, ~: 144440)
[PASS] test_refinancer_increasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143318, ~: 143451)
[PASS] test_refinancer_multipleCalls_refinance(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 175974, ~: 176126)
[PASS] test_refinancer_setDelegateServiceFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 142497, ~: 143001)
[PASS] test_refinancer_setGracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 142621, ~: 143103)
[PASS] test_refinancer_setInterestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143690, ~: 143680)
[PASS] test_refinancer_setLateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143643, ~: 143162)
[PASS] test_refinancer_setLateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144266, ~: 144755)
[PASS] test_refinancer_setNoticePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144020, ~: 144523)
[PASS] test_refinancer_setPaymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143825, ~: 144043)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 272.97ms

Running 4 tests for tests/AcceptNewTerms.t.sol:AcceptNewTerms
[PASS] test_acceptNewTerms_earlyRefinance() (gas: 448302)
[PASS] test_acceptNewTerms_principalDecrease() (gas: 462834)
[PASS] test_acceptNewTerms_principalDecreaseToZero() (gas: 443318)
[PASS] test_acceptNewTerms_principalIncrease() (gas: 492054)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 352.11ms

Running 1 test for tests/MakePayment.t.sol:MakePaymentSuccessTests
[PASS] testFuzz_makePayment(uint256,uint256,uint256,uint256) (runs: 256, μ: 565308, ~: 571611)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 366.04ms
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

# `pool-v2 (v3.0.0)`

```
Running 3 tests for tests/MaplePoolManager.t.sol:CompleteConfigurationTests
[PASS] test_completeConfiguration_alreadyConfigured() (gas: 34924)
[PASS] test_completeConfiguration_paused() (gas: 51325)
[PASS] test_completeConfiguration_success() (gas: 32563)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 11.30ms

Running 5 tests for tests/MaplePoolDeployer.t.sol:MaplePoolDeployerTests
[PASS] test_deployPool_invalidPoolDelegate() (gas: 144987)
[PASS] test_deployPool_success_withCoverRequired() (gas: 6126248)
[PASS] test_deployPool_success_withCoverRequired_queueWM() (gas: 6112928)
[PASS] test_deployPool_success_withoutCoverRequired() (gas: 6054551)
[PASS] test_deployPool_transferFailed() (gas: 5946706)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 16.17ms

Running 3 tests for tests/MaplePoolManager.t.sol:DepositCoverTests
[PASS] test_depositCover_insufficientApproval() (gas: 110656)
[PASS] test_depositCover_paused() (gas: 51807)
[PASS] test_depositCover_success() (gas: 96933)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 5.13ms

Running 4 tests for tests/MaplePoolManager.t.sol:AcceptPoolDelegate_SetterTests
[PASS] test_acceptPoolDelegate_globalsTransferFails() (gas: 61712)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 30138)
[PASS] test_acceptPoolDelegate_paused() (gas: 54047)
[PASS] test_acceptPoolDelegate_success() (gas: 54575)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.70ms

Running 5 tests for tests/MaplePoolManager.t.sol:AddLoanManager_SetterTests
[PASS] test_addLoanManager_invalidFactory() (gas: 39619)
[PASS] test_addLoanManager_notPoolDelegate() (gas: 38047)
[PASS] test_addLoanManager_paused() (gas: 37826)
[PASS] test_addLoanManager_success_asPoolDelegate() (gas: 175026)
[PASS] test_addLoanManager_success_whenNotConfigured() (gas: 162955)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.84ms

Running 10 tests for tests/MaplePoolManager.t.sol:FinishCollateralLiquidation
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 211483)
[PASS] test_finishCollateralLiquidation_paused() (gas: 37008)
[PASS] test_finishCollateralLiquidation_success_coverLeftOver() (gas: 287212)
[PASS] test_finishCollateralLiquidation_success_exceedMaxCoverLiquidationPercentAmount() (gas: 283545)
[PASS] test_finishCollateralLiquidation_success_fullCoverLiquidation_preexistingLoss() (gas: 288669)
[PASS] test_finishCollateralLiquidation_success_noCoverLeftOver() (gas: 267290)
[PASS] test_finishCollateralLiquidation_success_noCover_asGovernor() (gas: 249242)
[PASS] test_finishCollateralLiquidation_success_noCover_asOperationalAdmin() (gas: 278022)
[PASS] test_finishCollateralLiquidation_success_noCover_asPoolDelegate() (gas: 241709)
[PASS] test_finishCollateralLiquidation_success_noRemainingLossAfterCollateralLiquidation() (gas: 250525)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 7.73ms

Running 5 tests for tests/MaplePoolManager.t.sol:HandleCoverTests
[PASS] test_handleCover_feesAndSomeLosses() (gas: 129087)
[PASS] test_handleCover_fullCoverage() (gas: 148998)
[PASS] test_handleCover_halfCoverage() (gas: 155805)
[PASS] test_handleCover_noCover() (gas: 69042)
[PASS] test_handleCover_onlyFees() (gas: 116836)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 4.45ms

Running 26 tests for tests/MaplePoolManager.t.sol:CanCallTests
[PASS] test_canCall_depositWithPermit_lenderNotAllowed() (gas: 106990)
[PASS] test_canCall_depositWithPermit_liquidityCapExceeded() (gas: 89824)
[PASS] test_canCall_depositWithPermit_notActive() (gas: 51736)
[PASS] test_canCall_deposit_lenderNotAllowed() (gas: 105429)
[PASS] test_canCall_deposit_liquidityCapExceeded() (gas: 89099)
[PASS] test_canCall_deposit_notActive() (gas: 50671)
[PASS] test_canCall_invalidFunctionId() (gas: 45036)
[PASS] test_canCall_mintWithPermit_lenderNotAllowed() (gas: 126850)
[PASS] test_canCall_mintWithPermit_liquidityCapExceeded() (gas: 102944)
[PASS] test_canCall_mintWithPermit_notActive() (gas: 75420)
[PASS] test_canCall_mint_lenderNotAllowed() (gas: 124910)
[PASS] test_canCall_mint_liquidityCapExceeded() (gas: 101751)
[PASS] test_canCall_mint_notActive() (gas: 74207)
[PASS] test_canCall_paused_redeem() (gas: 53036)
[PASS] test_canCall_paused_removeShares() (gas: 53080)
[PASS] test_canCall_paused_requestRedeem() (gas: 53080)
[PASS] test_canCall_paused_requestWithdraw() (gas: 53015)
[PASS] test_canCall_paused_transfer() (gas: 53059)
[PASS] test_canCall_paused_withdraw() (gas: 53102)
[PASS] test_canCall_redeem() (gas: 42088)
[PASS] test_canCall_removeShares() (gas: 41501)
[PASS] test_canCall_requestRedeem() (gas: 41488)
[PASS] test_canCall_requestWithdraw() (gas: 41567)
[PASS] test_canCall_transferFrom_recipientNotAllowed() (gas: 95499)
[PASS] test_canCall_transfer_recipientNotAllowed() (gas: 94484)
[PASS] test_canCall_withdraw() (gas: 42068)
Test result: ok. 26 passed; 0 failed; 0 skipped; finished in 16.82ms

Running 7 tests for tests/MaplePool.t.sol:ConvertToAssetsTests
[PASS] testFuzz_convertToAssets(uint256,uint256,uint256) (runs: 256, μ: 185650, ~: 192398)
[PASS] test_convertToAssets_decreasedExchangeRate() (gas: 185272)
[PASS] test_convertToAssets_increasedExchangeRate() (gas: 185272)
[PASS] test_convertToAssets_initialExchangeRate() (gas: 185227)
[PASS] test_convertToAssets_initialState() (gas: 23465)
[PASS] test_convertToAssets_prematureYield() (gas: 43408)
[PASS] test_convertToAssets_worthlessShares() (gas: 165350)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 93.34ms

Running 3 tests for tests/MaplePool.t.sol:WithdrawTests
[PASS] testFuzz_withdraw_failNotEnabled(uint256) (runs: 256, μ: 33901, ~: 33901)
[PASS] test_withdraw_checkCall() (gas: 83306)
[PASS] test_withdraw_failNotEnabled() (gas: 33683)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 75.07ms

Running 3 tests for tests/MaplePoolDelegateCover.t.sol:MaplePoolDelegateCoverTests
[PASS] test_moveFunds_badTransfer() (gas: 61693)
[PASS] test_moveFunds_notManager() (gas: 52400)
[PASS] test_moveFunds_success() (gas: 62620)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.49ms

Running 4 tests for tests/MaplePoolManager.t.sol:MaxDepositTests
[PASS] test_maxDeposit_liquidityCap() (gas: 202160)
[PASS] test_maxDeposit_liquidityCap(address,address,uint256,uint256) (runs: 256, μ: 136225, ~: 137821)
[PASS] test_maxDeposit_withPermission() (gas: 90878)
[PASS] test_maxDeposit_withoutPermission() (gas: 82586)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 92.70ms

Running 5 tests for tests/MaplePool.t.sol:RequestWithdraw
[PASS] testFuzz_requestWithdraw_failNotEnabled(uint256) (runs: 256, μ: 92757, ~: 93884)
[PASS] test_requestWithdraw_checkCall() (gas: 82862)
[PASS] test_requestWithdraw_failWithoutApproval() (gas: 45836)
[PASS] test_requestWithdraw_insufficientApproval() (gas: 127710)
[PASS] test_requestWithdraw_withApproval_failNotEnabled() (gas: 87136)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 121.94ms

Running 6 tests for tests/MaplePool.t.sol:DepositTests
[PASS] testFuzz_deposit_badApprove(uint256) (runs: 256, μ: 168413, ~: 169036)
[PASS] testFuzz_deposit_insufficientBalance(uint256) (runs: 256, μ: 172455, ~: 172008)
[PASS] test_deposit_checkCall() (gas: 134958)
[PASS] test_deposit_reentrancy() (gas: 187171)
[PASS] test_deposit_zeroReceiver() (gas: 111837)
[PASS] test_deposit_zeroShares() (gas: 111805)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 172.59ms

Running 8 tests for tests/MaplePool.t.sol:RedeemTests
[PASS] test_redeem_checkCall() (gas: 83328)
[PASS] test_redeem_insufficientAmount() (gas: 67444)
[PASS] test_redeem_insufficientApprove() (gas: 144878)
[PASS] test_redeem_reentrancy() (gas: 147538)
[PASS] test_redeem_success() (gas: 142936)
[PASS] test_redeem_success_differentUser() (gas: 179752)
[PASS] test_redeem_zeroAssets() (gas: 99652)
[PASS] test_redeem_zeroShares() (gas: 54739)
Test result: ok. 8 passed; 0 failed; 0 skipped; finished in 4.99ms

Running 4 tests for tests/MaplePool.t.sol:RemoveSharesTests
[PASS] test_removeShares_checkCall() (gas: 54880)
[PASS] test_removeShares_failWithoutApproval() (gas: 33637)
[PASS] test_removeShares_insufficientApproval() (gas: 74171)
[PASS] test_removeShares_withApproval() (gas: 50600)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.54ms

Running 6 tests for tests/MaplePool.t.sol:RequestRedeemTests
[PASS] test_requestRedeem_checkCall() (gas: 82796)
[PASS] test_requestRedeem_failWithoutApproval() (gas: 35976)
[PASS] test_requestRedeem_insufficientApproval() (gas: 108767)
[PASS] test_requestRedeem_withApproval() (gas: 78164)
[PASS] test_requestRedeem_zeroShares() (gas: 72382)
[PASS] test_requestRedeem_zeroSharesAndNotOwnerAndNoAllowance() (gas: 46731)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 3.91ms

Running 4 tests for tests/MaplePool.t.sol:ConvertToExitAssetsTests
[PASS] testFuzz_convertToExitAssets(uint256,uint256,uint256,uint256) (runs: 256, μ: 214340, ~: 216293)
[PASS] testFuzz_convertToExitAssets_zeroSupply(uint256) (runs: 256, μ: 8774, ~: 8774)
[PASS] test_convertToExitAssets() (gas: 237225)
[PASS] test_convertToExitAssets_zeroSupply() (gas: 14027)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 104.86ms

Running 10 tests for tests/MaplePool.t.sol:DepositWithPermitTests
[PASS] testFuzz_depositWithPermit_insufficientBalance(uint256) (runs: 256, μ: 221839, ~: 221327)
[PASS] test_depositWithPermit_badNonce() (gas: 137193)
[PASS] test_depositWithPermit_checkCall() (gas: 155845)
[PASS] test_depositWithPermit_notStakerSignature() (gas: 139036)
[PASS] test_depositWithPermit_pastDeadline() (gas: 108832)
[PASS] test_depositWithPermit_reentrancy() (gas: 236472)
[PASS] test_depositWithPermit_replay() (gas: 243105)
[PASS] test_depositWithPermit_zeroAddress() (gas: 108187)
[PASS] test_depositWithPermit_zeroReceiver() (gas: 160995)
[PASS] test_depositWithPermit_zeroShares() (gas: 141235)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 206.55ms

Running 3 tests for tests/MaplePoolManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30796)
[PASS] test_setImplementation_paused() (gas: 53997)
[PASS] test_setImplementation_success() (gas: 41728)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 13.77ms

Running 4 tests for tests/MaplePoolManager.t.sol:SetIsLoanManager_SetterTests
[PASS] test_setIsLoanManager_invalidLM() (gas: 732637)
[PASS] test_setIsLoanManager_notPoolDelegate() (gas: 33108)
[PASS] test_setIsLoanManager_paused() (gas: 54283)
[PASS] test_setIsLoanManager_success() (gas: 62279)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 5.66ms

Running 4 tests for tests/MaplePoolManager.t.sol:SetLiquidityCap_SetterTests
[PASS] test_setLiquidityCap_notPoolDelegate() (gas: 37645)
[PASS] test_setLiquidityCap_paused() (gas: 54569)
[PASS] test_setLiquidityCap_success_asPoolDelegate() (gas: 64533)
[PASS] test_setLiquidityCap_success_whenNotConfigured() (gas: 52442)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.62ms

Running 5 tests for tests/MaplePoolManager.t.sol:SetPendingPoolDelegate_SetterTests
[PASS] test_setPendingPoolDelegate_asGovernor_success() (gas: 67385)
[PASS] test_setPendingPoolDelegate_asOperationalAdmin_success() (gas: 73260)
[PASS] test_setPendingPoolDelegate_asPoolDelegate_success() (gas: 62580)
[PASS] test_setPendingPoolDelegate_notPoolDelegateOrProtocolAdmins() (gas: 42265)
[PASS] test_setPendingPoolDelegate_paused() (gas: 56649)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.78ms

Running 5 tests for tests/MaplePoolManager.t.sol:SetWithdrawalManager_SetterTests
[PASS] test_setWithdrawalManager_configured() (gas: 37637)
[PASS] test_setWithdrawalManager_invalidFactory() (gas: 73652)
[PASS] test_setWithdrawalManager_invalidInstance() (gas: 52932)
[PASS] test_setWithdrawalManager_paused() (gas: 56759)
[PASS] test_setWithdrawalManager_success_asPoolDelegate() (gas: 53207)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.75ms

Running 6 tests for tests/MaplePoolManager.t.sol:TriggerDefault
[PASS] test_triggerDefault_invalidFactory() (gas: 119074)
[PASS] test_triggerDefault_notAuthorized() (gas: 49834)
[PASS] test_triggerDefault_paused() (gas: 42059)
[PASS] test_triggerDefault_success_asGovernor() (gas: 87421)
[PASS] test_triggerDefault_success_asOperationalAdmin() (gas: 115623)
[PASS] test_triggerDefault_success_asPoolDelegate() (gas: 82719)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 4.67ms

Running 6 tests for tests/MaplePoolManager.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 35769)
[PASS] test_upgrade_notScheduled() (gas: 38110)
[PASS] test_upgrade_paused() (gas: 52202)
[PASS] test_upgrade_successWithPoolDelegate() (gas: 105544)
[PASS] test_upgrade_successWithSecurityAdmin() (gas: 102090)
[PASS] test_upgrade_upgradeFailed() (gas: 96096)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 4.55ms

Running 6 tests for tests/MaplePool.t.sol:MintTests
[PASS] testFuzz_mint_badApprove(uint256) (runs: 256, μ: 168028, ~: 169102)
[PASS] testFuzz_mint_insufficientBalance(uint256) (runs: 256, μ: 172587, ~: 172031)
[PASS] test_mint_checkCall() (gas: 137267)
[PASS] test_mint_reentrancy() (gas: 187216)
[PASS] test_mint_zeroReceiver() (gas: 111904)
[PASS] test_mint_zeroShares() (gas: 111916)
Test result: ok. 6 passed; 0 failed; 0 skipped; finished in 126.35ms

Running 11 tests for tests/MaplePool.t.sol:MintWithPermitTests
[PASS] testFuzz_mintWithPermit_insufficientBalance(uint256) (runs: 256, μ: 222366, ~: 221811)
[PASS] test_mintWithPermit_badNonce() (gas: 141839)
[PASS] test_mintWithPermit_checkCall() (gas: 156266)
[PASS] test_mintWithPermit_insufficientPermit() (gas: 103105)
[PASS] test_mintWithPermit_notStakerSignature() (gas: 143644)
[PASS] test_mintWithPermit_pastDeadline() (gas: 113437)
[PASS] test_mintWithPermit_reentrancy() (gas: 236893)
[PASS] test_mintWithPermit_replay() (gas: 267660)
[PASS] test_mintWithPermit_zeroAddress() (gas: 112744)
[PASS] test_mintWithPermit_zeroReceiver() (gas: 161288)
[PASS] test_mintWithPermit_zeroShares() (gas: 161494)
Test result: ok. 11 passed; 0 failed; 0 skipped; finished in 256.14ms

Running 7 tests for tests/MaplePoolManager.t.sol:WithdrawCoverTests
[PASS] test_withdrawCover_noRequirement() (gas: 98472)
[PASS] test_withdrawCover_notPoolDelegate() (gas: 159072)
[PASS] test_withdrawCover_paused() (gas: 55035)
[PASS] test_withdrawCover_success() (gas: 153786)
[PASS] test_withdrawCover_success_zeroRecipient() (gas: 153619)
[PASS] test_withdrawCover_tryWithdrawBelowRequired() (gas: 202608)
[PASS] test_withdrawCover_withdrawMoreThanBalance() (gas: 84126)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 11.62ms

Running 7 tests for tests/MaplePoolManagerFactory.t.sol:PoolManagerFactoryFailureTest
[PASS] test_createInstance_failWithActivePoolDelegate() (gas: 275742)
[PASS] test_createInstance_failWithDisallowedAsset() (gas: 257536)
[PASS] test_createInstance_failWithInvalidPoolDelegate() (gas: 245686)
[PASS] test_createInstance_failWithNonERC20Asset() (gas: 253444)
[PASS] test_createInstance_failWithZeroAddressPoolDelegate() (gas: 201955)
[PASS] test_createInstance_failWithZeroAdmin() (gas: 5476382)
[PASS] test_createInstance_notPoolDeployer() (gas: 5173761)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 9.53ms

Running 1 test for tests/MaplePoolManagerFactory.t.sol:PoolManagerFactoryTest
[PASS] test_createInstance() (gas: 5282329)
Test result: ok. 1 passed; 0 failed; 0 skipped; finished in 2.53ms

Running 2 tests for tests/MaplePoolManagerMigrator.t.sol:MaplePoolManagerMigratorTests
[PASS] test_migrator_failure() (gas: 102194)
[PASS] test_migrator_success() (gas: 161893)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.03ms

Running 3 tests for tests/MaplePool.t.sol:ConstructorTests
[PASS] test_constructor_invalidApproval() (gas: 6330779)
[PASS] test_constructor_invalidDecimals() (gas: 6237754)
[PASS] test_constructor_zeroManager() (gas: 5794647)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.92ms

Running 4 tests for tests/MaplePoolManagerQueueMigrator.t.sol:MaplePoolManagerWMMigratorTests
[PASS] test_migrator_invalidFactory() (gas: 136827)
[PASS] test_migrator_invalidInstance() (gas: 164887)
[PASS] test_migrator_invalidPoolManager() (gas: 107952)
[PASS] test_migrator_success() (gas: 224476)
Test result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.75ms

Running 7 tests for tests/MaplePool.t.sol:ConvertToSharesTests
[PASS] testFuzz_convertToShares(uint256,uint256,uint256) (runs: 256, μ: 186566, ~: 192567)
[PASS] test_convertToShares_decreasedExchangeRate() (gas: 185266)
[PASS] test_convertToShares_increasedExchangeRate() (gas: 185309)
[PASS] test_convertToShares_initialExchangeRate() (gas: 185265)
[PASS] test_convertToShares_initialState() (gas: 23545)
[PASS] test_convertToShares_prematureYield() (gas: 43490)
[PASS] test_convertToShares_worthlessShares() (gas: 172913)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 89.96ms

Running 5 tests for tests/MaplePoolManager.t.sol:MaxMintTests
[PASS] testFuzz_maxMint_liquidityCap(address,address,uint256,uint256,uint256) (runs: 256, μ: 257547, ~: 257601)
[PASS] test_maxMint_liquidityCap_exchangeRateGtOne() (gas: 321469)
[PASS] test_maxMint_liquidityCap_exchangeRateOneToOne() (gas: 356173)
[PASS] test_maxMint_withPermission() (gas: 267667)
[PASS] test_maxMint_withoutPermission() (gas: 255261)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 168.84ms

Running 7 tests for tests/MaplePool.t.sol:PreviewDepositTests
[PASS] testFuzz_previewDeposit(uint256,uint256,uint256) (runs: 256, μ: 185215, ~: 192565)
[PASS] test_previewDeposit_decreasedExchangeRate() (gas: 185479)
[PASS] test_previewDeposit_increasedExchangeRate() (gas: 185502)
[PASS] test_previewDeposit_initialExchangeRate() (gas: 185503)
[PASS] test_previewDeposit_initialState() (gas: 23760)
[PASS] test_previewDeposit_prematureYield() (gas: 43682)
[PASS] test_previewDeposit_worthlessShares() (gas: 173039)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 111.46ms

Running 10 tests for tests/MaplePoolManager.t.sol:RequestFundsTests
[PASS] test_requestFunds_insufficientCoverBoundary() (gas: 230948)
[PASS] test_requestFunds_invalidFactory() (gas: 52134)
[PASS] test_requestFunds_invalidInstance() (gas: 58203)
[PASS] test_requestFunds_lockedLiquidityBoundary() (gas: 257033)
[PASS] test_requestFunds_notLM() (gas: 58982)
[PASS] test_requestFunds_paused() (gas: 37280)
[PASS] test_requestFunds_success() (gas: 129311)
[PASS] test_requestFunds_zeroAddress() (gas: 83859)
[PASS] test_requestFunds_zeroPrincipal() (gas: 45693)
[PASS] test_requestFunds_zeroSupply() (gas: 68381)
Test result: ok. 10 passed; 0 failed; 0 skipped; finished in 5.35ms

Running 3 tests for tests/MaplePoolManager.t.sol:SetActive_SetterTests
[PASS] test_setActive_notGlobals() (gas: 33842)
[PASS] test_setActive_paused() (gas: 52517)
[PASS] test_setActive_success() (gas: 49185)
Test result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.51ms

Running 5 tests for tests/MaplePoolManager.t.sol:SetDelegateManagementFeeRate_SetterTests
[PASS] test_setDelegateManagementFeeRate_notPoolDelegate() (gas: 39658)
[PASS] test_setDelegateManagementFeeRate_oob() (gas: 76604)
[PASS] test_setDelegateManagementFeeRate_paused() (gas: 56582)
[PASS] test_setDelegateManagementFeeRate_success_asPoolDelegate() (gas: 66697)
[PASS] test_setDelegateManagementFeeRate_success_whenNotConfigured() (gas: 54627)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.72ms

Running 5 tests for tests/MaplePoolManager.t.sol:ProcessRedeemTests
[PASS] test_processRedeem_noApproval() (gas: 48828)
[PASS] test_processRedeem_notWithdrawalManager() (gas: 36926)
[PASS] test_processRedeem_paused() (gas: 53064)
[PASS] test_processRedeem_success() (gas: 44853)
[PASS] test_processRedeem_success_notSender() (gas: 83629)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 4.11ms

Running 2 tests for tests/MaplePoolManager.t.sol:MaxWithdrawTests
[PASS] testFuzz_maxWithdraw(address) (runs: 256, μ: 17935, ~: 17935)
[PASS] test_maxWithdraw() (gas: 17601)
Test result: ok. 2 passed; 0 failed; 0 skipped; finished in 41.30ms

Running 7 tests for tests/MaplePool.t.sol:PreviewMintTests
[PASS] testFuzz_previewMint(uint256,uint256,uint256) (runs: 256, μ: 188977, ~: 197127)
[PASS] test_previewMint_decreasedExchangeRate() (gas: 186622)
[PASS] test_previewMint_increasedExchangeRate() (gas: 186622)
[PASS] test_previewMint_initialExchangeRate() (gas: 186667)
[PASS] test_previewMint_initialState() (gas: 23611)
[PASS] test_previewMint_prematureYield() (gas: 43489)
[PASS] test_previewMint_worthlessShares() (gas: 166701)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 126.16ms

Running 5 tests for tests/MaplePoolManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 34633)
[PASS] test_migrate_invalidPoolDelegateCover() (gas: 39740)
[PASS] test_migrate_notFactory() (gas: 31301)
[PASS] test_migrate_paused() (gas: 54479)
[PASS] test_migrate_success() (gas: 43244)
Test result: ok. 5 passed; 0 failed; 0 skipped; finished in 173.58ms

Running 7 tests for tests/MaplePoolMintFrontrunTests.t.sol:MaplePoolMintFrontrunTests
[PASS] testFuzz_depositFrontRun_honestOnePercentHarm(uint256) (runs: 256, μ: 7179508, ~: 7179756)
[PASS] testFuzz_depositFrontRun_honestTenPercentHarm(uint256) (runs: 256, μ: 7179547, ~: 7180012)
[PASS] testFuzz_depositFrontRun_theftThwarted(uint256) (runs: 256, μ: 7188554, ~: 7188770)
[PASS] test_depositFrontRun_theft() (gas: 7140667)
[PASS] test_depositFrontRun_theftReverted() (gas: 7085451)
[PASS] test_depositFrontRun_theftThwarted() (gas: 7186060)
[PASS] test_depositFrontRun_zeroShares() (gas: 7127383)
Test result: ok. 7 passed; 0 failed; 0 skipped; finished in 591.75ms

Running 14 tests for tests/ERC20.t.sol:Pool_ERC20Test
[PASS] invariant_metadata() (runs: 256, calls: 3840, reverts: 1905)
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 33015, ~: 33871)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 31725, ~: 52933)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 39923, ~: 39936)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 42116, ~: 43972)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 44061, ~: 44061)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 1330058, ~: 1329775)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 54926, ~: 56481)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 77610, ~: 79010)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 523879, ~: 530695)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 530325, ~: 532201)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 531996, ~: 531384)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 514536, ~: 512494)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 521807, ~: 521808)
Test result: ok. 14 passed; 0 failed; 0 skipped; finished in 1.32s

Running 14 tests for tests/ERC20.t.sol:Pool_ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 97100, ~: 98033)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 376092, ~: 376091)
[PASS] test_domainSeparator() (gas: 9265)
[PASS] test_initialState() (gas: 17445)
[PASS] test_permit_badS() (gas: 38863)
[PASS] test_permit_badV() (gas: 2113370)
[PASS] test_permit_differentSpender() (gas: 67441)
[PASS] test_permit_differentVerifier() (gas: 1236230)
[PASS] test_permit_earlyNonce() (gas: 67572)
[PASS] test_permit_ownerSignerMismatch() (gas: 67554)
[PASS] test_permit_replay() (gas: 105681)
[PASS] test_permit_withExpiry() (gas: 114182)
[PASS] test_permit_zeroAddress() (gas: 67501)
[PASS] test_typehash() (gas: 5954)
Test result: ok. 14 passed; 0 failed; 0 skipped; finished in 1.57s
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
