# Test Reports

Below is an report of all smart contract level tests that are run against the protocol, in all repos.

Current number of tests in this report is: **1846 tests**.

## `maple-core-v2`

```
Running 3 tests for tests/integration/ActivatePoolManager.t.sol:ActivatePoolManagerFailureTests
[PASS] test_activatePoolManager_failIfNotGlobals() (gas: 36921)
[PASS] test_activatePoolManager_failIfNotGovernor() (gas: 21293)
[PASS] test_activatePoolManager_failIfProtocolIsPaused() (gas: 62280)
Test result: ok. 3 passed; 0 failed; finished in 17.22ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:ConvertToAssetsTests
[PASS] test_convertToAssets_multipleUsers() (gas: 421774)
[PASS] test_convertToAssets_multipleUsers_changeTotalAssets() (gas: 445427)
[PASS] test_convertToAssets_singleUser() (gas: 240854)
[PASS] test_convertToAssets_zeroTotalSupply() (gas: 12215)
Test result: ok. 4 passed; 0 failed; finished in 17.25ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:MintFailureTests
[PASS] test_mint_insufficientApproval() (gas: 306606)
[PASS] test_mint_liquidityCapExceeded() (gas: 360861)
[PASS] test_mint_notActive() (gas: 300153)
[PASS] test_mint_privatePoolInvalidRecipient() (gas: 300618)
[PASS] test_mint_privatePoolInvalidRecipient_openPoolToPublic() (gas: 276732)
[PASS] test_mint_protocolPaused() (gas: 300151)
Test result: ok. 6 passed; 0 failed; finished in 19.33ms

Running 1 test for tests/integration/BasicInterestAccrual.t.sol:BasicInterestAccrualTest
[PASS] test_basicInterestAccrual() (gas: 3504597)
Test result: ok. 1 passed; 0 failed; finished in 20.23ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:DepositWithPermitFailureTests
[PASS] test_depositWithPermit_invalidSignature() (gas: 409444)
[PASS] test_depositWithPermit_liquidityCapExceeded() (gas: 435329)
[PASS] test_depositWithPermit_notActive() (gas: 341787)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient() (gas: 342254)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 318300)
[PASS] test_depositWithPermit_protocolPaused() (gas: 346800)
Test result: ok. 6 passed; 0 failed; finished in 20.47ms

Running 1 test for tests/integration/ActivatePoolManager.t.sol:ActivatePoolManagerTests
[PASS] test_activatePoolManager() (gas: 74186)
Test result: ok. 1 passed; 0 failed; finished in 9.93ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:ConvertToSharesTests
[PASS] test_convertToShares_multipleUsers() (gas: 421805)
[PASS] test_convertToShares_multipleUsers_changeTotalAssets() (gas: 445492)
[PASS] test_convertToShares_singleUser() (gas: 240914)
[PASS] test_convertToShares_zeroTotalSupply() (gas: 12274)
Test result: ok. 4 passed; 0 failed; finished in 11.54ms

Running 3 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxDepositTests
[PASS] testDeepFuzz_maxDeposit_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 181970, ~: 181834)
[PASS] test_maxDeposit_closedPool() (gas: 186211)
[PASS] test_maxDeposit_totalAssetsIncrease() (gas: 181427)
Test result: ok. 3 passed; 0 failed; finished in 34.18ms

Running 4 tests for tests/integration/FetchValuesFomPM.t.sol:PoolManagerGetterTests
[PASS] testDeepFuzz_getEscrowParams_shouldReturnValues(uint256) (runs: 100, μ: 57771, ~: 57562)
[PASS] test_addressGetters() (gas: 37765)
[PASS] test_hasSufficientCover_insufficientCover(uint256) (runs: 100, μ: 139485, ~: 139634)
[PASS] test_hasSufficientCover_sufficientCover(uint256) (runs: 100, μ: 150787, ~: 151342)
Test result: ok. 4 passed; 0 failed; finished in 66.61ms

Running 3 tests for tests/integration/FinishCollateralLiquidation.t.sol:FinishCollateralLiquidationFailureTests
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 50743)
[PASS] test_finishCollateralLiquidation_notFinished() (gas: 638647)
[PASS] test_finishCollateralLiquidation_notPoolManager() (gas: 27033)
Test result: ok. 3 passed; 0 failed; finished in 26.92ms

Running 3 tests for tests/e2e/Regression.t.sol:RegressionTest
[PASS] test_regression_invariantUnderflow_1() (gas: 23488800)
[PASS] test_regression_underflow2() (gas: 37075715)
[PASS] test_regression_underflow3() (gas: 32102555)
Test result: ok. 3 passed; 0 failed; finished in 98.49ms

Running 2 tests for tests/integration/DepositAndMint.t.sol:DepositWithPermitTests
[PASS] testDeepFuzz_depositWithPermit_singleUser(uint256) (runs: 100, μ: 293664, ~: 293578)
[PASS] test_depositWithPermit_singleUser() (gas: 287662)
Test result: ok. 2 passed; 0 failed; finished in 88.86ms

Running 16 tests for tests/integration/Fund.t.sol:FundTests
[PASS] test_fund_failIfAmountGreaterThanLockedLiquidity() (gas: 3003700)
[PASS] test_fund_failIfInsufficientCover() (gas: 156822)
[PASS] test_fund_failIfInvalidBorrower() (gas: 85477)
[PASS] test_fund_failIfInvalidLoanManager() (gas: 56366)
[PASS] test_fund_failIfLoanActive() (gas: 915820)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 53492)
[PASS] test_fund_failIfNotPoolManager() (gas: 25840)
[PASS] test_fund_failIfPoolDoesNotApprovePM() (gas: 196199)
[PASS] test_fund_failIfPrincipalIsGreaterThanAssetBalance() (gas: 191567)
[PASS] test_fund_failIfProtocolIsPaused() (gas: 60082)
[PASS] test_fund_failIfTotalSupplyIsZero() (gas: 363017)
[PASS] test_fund_failWithExcessFunds() (gas: 571933)
[PASS] test_fund_failWithLessFundsThanRequested() (gas: 481926)
[PASS] test_fund_oneLoan() (gas: 832583)
[PASS] test_fund_twoLoans() (gas: 1371358)
[PASS] test_fund_unaccountedFunds() (gas: 862514)
Test result: ok. 16 passed; 0 failed; finished in 23.20ms

Running 6 tests for tests/integration/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 50712)
[PASS] test_removeLoanImpairment_notGovernor() (gas: 296033)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 102901)
[PASS] test_removeLoanImpairment_notLender() (gas: 20267)
[PASS] test_removeLoanImpairment_notPoolManager() (gas: 26126)
[PASS] test_removeLoanImpairment_pastDate() (gas: 381333)
Test result: ok. 6 passed; 0 failed; finished in 25.68ms

Running 3 tests for tests/integration/Redeem.t.sol:RedeemIntegrationTests
[PASS] test_redeem_oneLPWithImpairedLoan() (gas: 3130703)
[PASS] test_redeem_twoLPSWithImpairedLoanAndTriggerDefault() (gas: 3137800)
[PASS] test_redeem_twoLPsWithImpairedLoan() (gas: 3407028)
Test result: ok. 3 passed; 0 failed; finished in 25.76ms

Running 9 tests for tests/integration/RemoveShares.t.sol:RemoveSharesFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 230665)
[PASS] test_removeShares_failIfInvalidShares() (gas: 92603)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 92567)
[PASS] test_removeShares_failIfNotPool() (gas: 45477)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 21375)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 64228)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 211427)
[PASS] test_removeShares_failIfTransferFail() (gas: 155144)
[PASS] test_removeShares_failIfWithdrawalIsPending() (gas: 207519)
Test result: ok. 9 passed; 0 failed; finished in 27.29ms

Running 4 tests for tests/integration/RemoveShares.t.sol:RemoveSharesTests
[PASS] test_removeShares_pastTheRedemptionWindow() (gas: 154935)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 553502)
[PASS] test_removeShares_success() (gas: 155174)
[PASS] test_removeShares_withApproval() (gas: 214941)
Test result: ok. 4 passed; 0 failed; finished in 12.59ms

Running 5 tests for tests/integration/SetMinRatioAndSlippage.t.sol:SetMinRatioTests
[PASS] test_setMinRatio_notAuthorized() (gas: 48418)
[PASS] test_setMinRatio_notLoanManager() (gas: 96191)
[PASS] test_setMinRatio_notPoolManager() (gas: 21098)
[PASS] test_setMinRatio_withGovernor() (gas: 89960)
[PASS] test_setMinRatio_withPoolDelegate() (gas: 84116)
Test result: ok. 5 passed; 0 failed; finished in 10.03ms

Running 6 tests for tests/integration/SetMinRatioAndSlippage.t.sol:SetSlippageTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 135844)
[PASS] test_setAllowedSlippage_notAuthorized() (gas: 48440)
[PASS] test_setAllowedSlippage_notLoanManager() (gas: 96192)
[PASS] test_setAllowedSlippage_notPoolManager() (gas: 21011)
[PASS] test_setAllowedSlippage_withGovernor() (gas: 89810)
[PASS] test_setAllowedSlippage_withPoolDelegate() (gas: 84012)
Test result: ok. 6 passed; 0 failed; finished in 10.21ms

Running 5 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxMintTests
[PASS] testDeepFuzz_maxMint_exchangeRateGtOne(uint256,uint256,uint256) (runs: 100, μ: 327004, ~: 326827)
[PASS] testDeepFuzz_maxMint_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 191008, ~: 190896)
[PASS] test_maxMint_closedPool() (gas: 198903)
[PASS] test_maxMint_exchangeRateGtOne() (gas: 323914)
[PASS] test_maxMint_totalAssetsIncrease() (gas: 190600)
Test result: ok. 5 passed; 0 failed; finished in 128.06ms

Running 10 tests for tests/integration/Transfer.t.sol:TransferTests
[PASS] test_transferFrom_privatePoolInvalidLender() (gas: 426548)
[PASS] test_transferFrom_privatePoolInvalidLender_openPoolToPublic() (gas: 405576)
[PASS] test_transferFrom_protocolPaused() (gas: 325787)
[PASS] test_transferFrom_publicPool() (gas: 309819)
[PASS] test_transferFrom_publicPool_insufficientApproval() (gas: 316109)
[PASS] test_transferFrom_publicPool_noApproval() (gas: 290834)
[PASS] test_transfer_privatePoolInvalidLender() (gas: 369583)
[PASS] test_transfer_privatePoolInvalidLender_openPoolToPublic() (gas: 348633)
[PASS] test_transfer_protocolPaused() (gas: 297353)
[PASS] test_transfer_publicPool() (gas: 299172)
Test result: ok. 10 passed; 0 failed; finished in 13.82ms

Running 3 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxRedeemTests
[PASS] test_maxRedeem_lockedShares_inExitWindow() (gas: 407324)
[PASS] test_maxRedeem_lockedShares_notInExitWindow() (gas: 398532)
[PASS] test_maxRedeem_noLockedShares_notInExitWindow() (gas: 239944)
Test result: ok. 3 passed; 0 failed; finished in 11.08ms

Running 1 test for tests/fuzz/Deposit.t.sol:DepositFuzzTests
[PASS] testDeepFuzz_deposit_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 392276, ~: 413612)
Test result: ok. 1 passed; 0 failed; finished in 205.33ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:DepositFailureTests
[PASS] test_deposit_insufficientApproval() (gas: 379425)
[PASS] test_deposit_liquidityCapExceeded() (gas: 336761)
[PASS] test_deposit_notActive() (gas: 292515)
[PASS] test_deposit_privatePoolInvalidRecipient() (gas: 293002)
[PASS] test_deposit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 269094)
[PASS] test_deposit_protocolPaused() (gas: 298226)
Test result: ok. 6 passed; 0 failed; finished in 11.73ms

Running 7 tests for tests/integration/TransferPoolOwnership.t.sol:TransferPoolOwnershipTests
[PASS] test_acceptPendingPoolDelegate() (gas: 109698)
[PASS] test_acceptPendingPoolDelegate_notPendingPoolDelegate() (gas: 115693)
[PASS] test_setPendingPoolDelegate() (gas: 67374)
[PASS] test_setPendingPoolDelegate_notPD() (gas: 95989)
[PASS] test_transferOwnedPoolManager_alreadyPoolDelegate() (gas: 149344)
[PASS] test_transferOwnedPoolManager_notPoolManager() (gas: 116729)
[PASS] test_transferOwnedPoolManager_notValidPoolDelegate() (gas: 124973)
Test result: ok. 7 passed; 0 failed; finished in 17.47ms

Running 3 tests for tests/integration/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notAuthorized() (gas: 59489)
[PASS] test_triggerDefault_notFactory() (gas: 54449)
[PASS] test_triggerDefault_notPoolManager() (gas: 24797)
Test result: ok. 3 passed; 0 failed; finished in 11.73ms

Running 6 tests for tests/integration/Redeem.t.sol:RedeemTests
[PASS] testDeepFuzz_redeem_singleUser_fullLiquidity_oneToOne(uint256,uint256) (runs: 100, μ: 501952, ~: 499952)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem() (gas: 517609)
[PASS] test_redeem_singleUser_fullLiquidity_oneToOne() (gas: 514158)
[PASS] test_redeem_singleUser_noLiquidity() (gas: 3170623)
[PASS] test_redeem_singleUser_noLiquidity_notOwner() (gas: 3230695)
[PASS] test_redeem_singleUser_withApprovals() (gas: 610161)
Test result: ok. 6 passed; 0 failed; finished in 101.54ms

Running 6 tests for tests/integration/Upgrade.t.sol:LiquidationUpgradeTests
[PASS] test_upgradeLiquidator_delayNotPassed() (gas: 171407)
[PASS] test_upgradeLiquidator_durationPassed() (gas: 172192)
[PASS] test_upgradeLiquidator_governor_noTimelockNeeded() (gas: 211056)
[PASS] test_upgradeLiquidator_noTimelock() (gas: 179688)
[PASS] test_upgradeLiquidator_timelockExtended() (gas: 303809)
[PASS] test_upgradeLiquidator_timelockShortened() (gas: 304568)
Test result: ok. 6 passed; 0 failed; finished in 25.82ms

Running 3 tests for tests/integration/UnrealizedLosses.t.sol:UnrealizedLossesTests
[PASS] test_unrealizedLosses_depositWithUL() (gas: 470382)
[PASS] test_unrealizedLosses_redeemWithUL_fullLiquidity() (gas: 559916)
[PASS] test_unrealizedLosses_redeemWithUL_partialLiquidity() (gas: 3252928)
Test result: ok. 3 passed; 0 failed; finished in 15.60ms

Running 4 tests for tests/integration/Redeem.t.sol:RequestRedeemFailureTests
[PASS] test_requestRedeem_failIfAlreadyLockedShares() (gas: 310400)
[PASS] test_requestRedeem_failIfInsufficientApproval() (gas: 130165)
[PASS] test_requestRedeem_failIfNotPM() (gas: 21076)
[PASS] test_requestRedeem_failIfNotPool() (gas: 45652)
Test result: ok. 4 passed; 0 failed; finished in 13.77ms

Running 4 tests for tests/integration/DepositAndMint.t.sol:DepositTest
[PASS] testDeepFuzz_deposit_singleUser(uint256) (runs: 100, μ: 241977, ~: 241915)
[PASS] testDeepFuzz_deposit_variableExchangeRate(uint256,uint256) (runs: 100, μ: 2936078, ~: 2937737)
[PASS] test_deposit_singleUser_oneToOne() (gas: 241452)
[PASS] test_deposit_twoUsers_oneToOne() (gas: 387829)
Test result: ok. 4 passed; 0 failed; finished in 256.81ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxWithdrawTests
[PASS] testDeepFuzz_maxWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 396530, ~: 396248)
[PASS] test_maxWithdraw_lockedShares_inExitWindow() (gas: 395951)
[PASS] test_maxWithdraw_lockedShares_notInExitWindow() (gas: 392853)
[PASS] test_maxWithdraw_noLockedShares_notInExitWindow() (gas: 233163)
Test result: ok. 4 passed; 0 failed; finished in 55.86ms

Running 6 tests for tests/integration/Upgrade.t.sol:LoanManagerUpgradeTests
[PASS] test_upgradeLoanManager_delayNotPassed() (gas: 149768)
[PASS] test_upgradeLoanManager_durationPassed() (gas: 150597)
[PASS] test_upgradeLoanManager_governor_noTimelockNeeded() (gas: 181167)
[PASS] test_upgradeLoanManager_noTimelock() (gas: 158051)
[PASS] test_upgradeLoanManager_timelockExtended() (gas: 260423)
[PASS] test_upgradeLoanManager_timelockShortened() (gas: 261248)
Test result: ok. 6 passed; 0 failed; finished in 20.68ms

Running 2 tests for tests/integration/Upgrade.t.sol:GlobalsUpgradeTests
[PASS] test_upgradeGlobals() (gas: 28111)
[PASS] test_upgradeGlobals_notAdmin() (gas: 32639)
Test result: ok. 2 passed; 0 failed; finished in 21.48ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewDepositTests
[PASS] test_previewDeposit_multipleUsers() (gas: 421940)
[PASS] test_previewDeposit_multipleUsers_changeTotalAssets() (gas: 445645)
[PASS] test_previewDeposit_nonZeroTotalSupply() (gas: 241129)
[PASS] test_previewDeposit_zeroTotalSupply() (gas: 12467)
Test result: ok. 4 passed; 0 failed; finished in 11.10ms

Running 6 tests for tests/integration/Upgrade.t.sol:PoolManagerUpgradeTests
[PASS] test_upgradePoolManager_delayNotPassed() (gas: 130399)
[PASS] test_upgradePoolManager_durationPassed() (gas: 131026)
[PASS] test_upgradePoolManager_governor_noTimelockNeeded() (gas: 159840)
[PASS] test_upgradePoolManager_noTimelock() (gas: 137006)
[PASS] test_upgradePoolManager_timelockExtended() (gas: 217699)
[PASS] test_upgradePoolManager_timelockShortened() (gas: 218591)
Test result: ok. 6 passed; 0 failed; finished in 13.60ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewMintTests
[PASS] test_previewMint_multipleUsers() (gas: 422908)
[PASS] test_previewMint_multipleUsers_changeTotalAssets() (gas: 446560)
[PASS] test_previewMint_nonZeroTotalSupply() (gas: 242314)
[PASS] test_previewMint_zeroTotalSupply() (gas: 12296)
Test result: ok. 4 passed; 0 failed; finished in 11.20ms

Running 16 tests for tests/integration/Refinance.t.sol:AcceptNewTermsFailureTests
[PASS] testFail_acceptNewTerms_failIfNotValidLoanManager() (gas: 91522)
[PASS] test_acceptNewTerms_failIfDeadlineExpired() (gas: 326831)
[PASS] test_acceptNewTerms_failIfInsufficientCover() (gas: 178458)
[PASS] test_acceptNewTerms_failIfInvalidBorrower() (gas: 107201)
[PASS] test_acceptNewTerms_failIfLockedLiquidity() (gas: 409783)
[PASS] test_acceptNewTerms_failIfNotLender() (gas: 22231)
[PASS] test_acceptNewTerms_failIfNotPoolDelegate() (gas: 84108)
[PASS] test_acceptNewTerms_failIfNotPoolManager() (gas: 29550)
[PASS] test_acceptNewTerms_failIfProtocolIsPaused() (gas: 61243)
[PASS] test_acceptNewTerms_failIfRefinanceCallFails() (gas: 416693)
[PASS] test_acceptNewTerms_failIfRefinanceMismatch() (gas: 279243)
[PASS] test_acceptNewTerms_failIfTotalSupplyIsZero() (gas: 650783)
[PASS] test_acceptNewTerms_failWithFailedTransfer() (gas: 206820)
[PASS] test_acceptNewTerms_failWithInsufficientCollateral() (gas: 497454)
[PASS] test_acceptNewTerms_failWithInvalidRefinancer() (gas: 321339)
[PASS] test_acceptNewTerms_failWithUnexpectedFunds() (gas: 531997)
Test result: ok. 16 passed; 0 failed; finished in 31.75ms

Running 4 tests for tests/integration/DepositAndMint.t.sol:MintTest
[PASS] testDeepFuzz_mint_singleUser(uint256) (runs: 100, μ: 243900, ~: 243838)
[PASS] testDeepFuzz_mint_variableExchangeRate(uint256,uint256) (runs: 100, μ: 2956220, ~: 2955601)
[PASS] test_mint_singleUser_oneToOne() (gas: 243286)
[PASS] test_mint_twoUsers_OneToOne() (gas: 399736)
Test result: ok. 4 passed; 0 failed; finished in 271.68ms

Running 1 test for tests/integration/Upgrade.t.sol:UnscheduleCallTests
[PASS] test_unscheduleCall_governor() (gas: 80597)
Test result: ok. 1 passed; 0 failed; finished in 12.64ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewRedeemTests
[PASS] test_previewRedeem_invalidShares() (gas: 385704)
[PASS] test_previewRedeem_lockedShares_inExitWindow() (gas: 407876)
[PASS] test_previewRedeem_lockedShares_notInExitWindow() (gas: 390217)
[PASS] test_previewRedeem_noLockedShares_notInExitWindow() (gas: 39136)
Test result: ok. 4 passed; 0 failed; finished in 11.13ms

Running 3 tests for tests/integration/Redeem.t.sol:MultiUserRedeemTests
[PASS] test_redeem_partialLiquidity_sameCash_differentExchangeRate() (gas: 3799221)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate() (gas: 3697450)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate_exposeRounding() (gas: 5961009)
Test result: ok. 3 passed; 0 failed; finished in 24.74ms

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapDepositWithPermitTests
[PASS] testFuzz_depositWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 303343, ~: 303366)
[PASS] testFuzz_depositWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 218064, ~: 217732)
[PASS] testFuzz_depositWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 425922, ~: 425568)
[PASS] test_depositWithPermit_exactBootstrapMintAmount() (gas: 281887)
[PASS] test_depositWithPermit_gtBootstrapMintAmount() (gas: 302907)
[PASS] test_depositWithPermit_ltBootstrapMintAmount() (gas: 265708)
[PASS] test_depositWithPermit_secondDepositorGetsCorrectShares() (gas: 425140)
Test result: ok. 7 passed; 0 failed; finished in 298.32ms

Running 6 tests for tests/integration/Upgrade.t.sol:WithdrawalManagerUpgradeTests
[PASS] test_upgradeWithdrawalManager_delayNotPassed() (gas: 149863)
[PASS] test_upgradeWithdrawalManager_durationPassed() (gas: 150736)
[PASS] test_upgradeWithdrawalManager_governor_noTimelockNeeded() (gas: 181305)
[PASS] test_upgradeWithdrawalManager_noTimelock() (gas: 158124)
[PASS] test_upgradeWithdrawalManager_timelockExtended() (gas: 260742)
[PASS] test_upgradeWithdrawalManager_timelockShortened() (gas: 261545)
Test result: ok. 6 passed; 0 failed; finished in 12.27ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:MintWithPermitFailureTests
[PASS] test_mintWithPermit_insufficientPermit() (gas: 384147)
[PASS] test_mintWithPermit_liquidityCapExceeded() (gas: 461787)
[PASS] test_mintWithPermit_notActive() (gas: 350215)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient() (gas: 350747)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 326771)
[PASS] test_mintWithPermit_protocolPaused() (gas: 350448)
Test result: ok. 6 passed; 0 failed; finished in 16.92ms

Running 9 tests for tests/integration/Redeem.t.sol:RedeemFailureTests
[PASS] test_redeem_failIfNoApprove() (gas: 252041)
[PASS] test_redeem_failIfNoBalanceOnWM() (gas: 335006)
[PASS] test_redeem_failIfNoRequest() (gas: 84454)
[PASS] test_redeem_failIfNotInWindow() (gas: 283159)
[PASS] test_redeem_failIfNotPool() (gas: 46201)
[PASS] test_redeem_failIfNotPoolManager() (gas: 21593)
[PASS] test_redeem_failWithInsufficientApproval() (gas: 320956)
[PASS] test_redeem_failWithInvalidAmountOfShares() (gas: 277365)
[PASS] test_redeem_failWithZeroReceiver() (gas: 297080)
Test result: ok. 9 passed; 0 failed; finished in 16.16ms

Running 1 test for tests/integration/ValidCollateral.t.sol:ValidCollateralTests
[PASS] test_setValidCollateral_invalidCollateral() (gas: 2188403)
Test result: ok. 1 passed; 0 failed; finished in 10.27ms

Running 6 tests for tests/integration/Refinance.t.sol:RefinanceTestsSingleLoan
[PASS] test_refinance_onLateLoan_changePaymentInterval() (gas: 1155901)
[PASS] test_refinance_onLoanPaymentDueDate_changeInterestRate() (gas: 1147368)
[PASS] test_refinance_onLoanPaymentDueDate_changePaymentInterval() (gas: 1147372)
[PASS] test_refinance_onLoanPaymentDueDate_changeToAmortized() (gas: 1150232)
[PASS] test_refinance_onLoanPaymentDueDate_increasePrincipal() (gas: 1174315)
[PASS] test_refinance_skimFundAsset() (gas: 676682)
Test result: ok. 6 passed; 0 failed; finished in 33.08ms

Running 6 tests for tests/integration/Redeem.t.sol:RequestRedeemTests
[PASS] testDeepFuzz_requestRedeem(uint256,uint256) (runs: 100, μ: 420529, ~: 423734)
[PASS] test_requestRedeem() (gas: 401641)
[PASS] test_requestRedeem_refresh() (gas: 486294)
[PASS] test_requestRedeem_refresh_notOwnerAndNoApproval() (gas: 441973)
[PASS] test_requestRedeem_refresh_notOwnerWithApproval() (gas: 514094)
[PASS] test_requestRedeem_withApproval() (gas: 465456)
Test result: ok. 6 passed; 0 failed; finished in 72.63ms

Running 3 tests for tests/integration/Withdraw.t.sol:RequestWithdrawFailureTests
[PASS] test_requestWithdraw_failIfInsufficientApproval() (gas: 220505)
[PASS] test_requestWithdraw_failIfNotPM() (gas: 21031)
[PASS] test_requestWithdraw_failIfNotPool() (gas: 45673)
Test result: ok. 3 passed; 0 failed; finished in 10.42ms

Running 9 tests for tests/e2e/PoolScenarios.t.sol:PoolScenarioTests
[PASS] test_poolScenario_fundLoanAndNeverTouchIt() (gas: 9724802)
[PASS] test_poolScenario_impairLoanWithLatePaymentAndRefinance() (gas: 4560868)
[PASS] test_poolScenario_intendToWithdrawAndChangeWMToZero() (gas: 489598)
[PASS] test_poolScenario_loanWithVeryHighInterestRate() (gas: 2920079)
[PASS] test_poolScenario_loanWithZeroInterestRate() (gas: 3412107)
[PASS] test_poolScenario_loanWithZeroInterestRateAndDefaultWithCover() (gas: 2969502)
[PASS] test_poolScenarios_refinanceATwoPeriodsLateLoan() (gas: 4334329)
[PASS] test_poolScenarios_refinanceLateLoanAndDefault() (gas: 3993118)
[PASS] test_poolScenarios_stressTestAdvanceGlobalPaymentAccounting() (gas: 381497753)
Test result: ok. 9 passed; 0 failed; finished in 295.63ms

Running 12 tests for tests/integration/Liquidation.t.sol:LoanLiquidationTests
[PASS] test_loanDefault_fullCover_noCollateral_noImpairment() (gas: 2806287)
[PASS] test_loanDefault_fullCover_noCollateral_withImpairment() (gas: 2857529)
[PASS] test_loanDefault_fullCover_withCollateral_noImpairment() (gas: 3786619)
[PASS] test_loanDefault_fullCover_withCollateral_withImpairment() (gas: 3827792)
[PASS] test_loanDefault_noCover_noCollateral_noImpairment() (gas: 2724026)
[PASS] test_loanDefault_noCover_noCollateral_withImpairment() (gas: 2781721)
[PASS] test_loanDefault_noCover_withCollateral_noImpairment() (gas: 3722674)
[PASS] test_loanDefault_noCover_withCollateral_withImpairment() (gas: 3766575)
[PASS] test_loanDefault_partialCover_noCollateral_noImpairment() (gas: 2805917)
[PASS] test_loanDefault_partialCover_noCollateral_withImpairment() (gas: 2857527)
[PASS] test_loanDefault_partialCover_withCollateral_noImpairment() (gas: 3785994)
[PASS] test_loanDefault_partialCover_withCollateral_withImpairment() (gas: 3827768)
Test result: ok. 12 passed; 0 failed; finished in 43.44ms

Running 5 tests for tests/integration/LoanManagerGetters.t.sol:LoanManagerGetterTests
[PASS] test_loanManagerGetters_addresses() (gas: 80491)
[PASS] test_loanManagerGetters_liquidationInformation() (gas: 1148678)
[PASS] test_loanManagerGetters_paymentInformation() (gas: 29899)
[PASS] test_loanManagerGetters_sortedPayments() (gas: 2733985)
[PASS] test_loanManagerGetters_uints() (gas: 32956)
Test result: ok. 5 passed; 0 failed; finished in 14.07ms

Running 3 tests for tests/integration/Withdraw.t.sol:RequestWithdrawTests
[PASS] testDeepFuzz_requestWithdraw(uint256,uint256) (runs: 100, μ: 316025, ~: 318873)
[PASS] test_requestWithdraw() (gas: 296080)
[PASS] test_requestWithdraw_withApproval() (gas: 353426)
Test result: ok. 3 passed; 0 failed; finished in 63.47ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_failIfNotLoan() (gas: 26912)
[PASS] test_makePayment_failWithTransferFailed() (gas: 232519)
[PASS] test_makePayment_failWithTransferFromFailed() (gas: 139885)
Test result: ok. 3 passed; 0 failed; finished in 19.28ms

Running 2 tests for tests/integration/DepositAndMint.t.sol:MintWithPermitTests
[PASS] testDeepFuzz_mintWithPermit_singleUser(uint256) (runs: 100, μ: 296993, ~: 297001)
[PASS] test_mintWithPermit_singleUser() (gas: 290012)
Test result: ok. 2 passed; 0 failed; finished in 102.55ms

Running 1 test for tests/integration/FetchValuesFomLM.t.sol:LoanManagerAddressGetterTests
[PASS] test_addressGetters() (gas: 64064)
Test result: ok. 1 passed; 0 failed; finished in 9.68ms

Running 4 tests for tests/integration/Withdraw.t.sol:WithdrawFailureTests
[PASS] testDeepFuzz_withdraw(uint256,address,address) (runs: 100, μ: 62104, ~: 62104)
[PASS] test_withdraw_failIfNotPool() (gas: 46135)
[PASS] test_withdraw_failIfNotPoolManager() (gas: 21548)
[PASS] test_withdraw_zeroAssetInput() (gas: 63717)
Test result: ok. 4 passed; 0 failed; finished in 32.89ms

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapMintTests
[PASS] testFuzz_mint_gtBootstrapMintAmount(uint256) (runs: 100, μ: 258251, ~: 258268)
[PASS] testFuzz_mint_ltBootstrapMintAmount(uint256) (runs: 100, μ: 218798, ~: 218442)
[PASS] testFuzz_mint_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 349998, ~: 350374)
[PASS] test_mint_exactBootstrapMintAmount() (gas: 236846)
[PASS] test_mint_gtBootstrapMintAmount() (gas: 257500)
[PASS] test_mint_ltBootstrapMintAmount() (gas: 218324)
[PASS] test_mint_secondDepositorGetsCorrectShares() (gas: 349102)
Test result: ok. 7 passed; 0 failed; finished in 129.22ms

Running 1 test for tests/integration/MakePayment.t.sol:MakePaymentTestsDomainStartGtDomainEnd
[PASS] test_makePayment_domainStart_gt_domainEnd() (gas: 6343864)
Test result: ok. 1 passed; 0 failed; finished in 20.57ms

Running 3 tests for tests/integration/FetchValuesFomLM.t.sol:LoanManagerIsLiquidationActiveGetterTests
[PASS] test_isLiquidationActive_afterLiquidation() (gas: 1133751)
[PASS] test_isLiquidationActive_beforeLiquidation() (gas: 15942)
[PASS] test_isLiquidationActive_duringLiquidation() (gas: 614263)
Test result: ok. 3 passed; 0 failed; finished in 12.63ms

Running 6 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewWithdrawTests
[PASS] testDeepFuzz_previewWithdraw(uint256) (runs: 100, μ: 37241, ~: 37241)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 388540, ~: 388274)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_notInExitWindow(uint256) (runs: 100, μ: 388634, ~: 388389)
[PASS] test_previewWithdraw() (gas: 228316)
[PASS] test_previewWithdraw_zeroAssetsWithDeposit() (gas: 228361)
[PASS] test_previewWithdraw_zeroAssetsWithoutDeposit() (gas: 37000)
Test result: ok. 6 passed; 0 failed; finished in 147.56ms

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapDepositTests
[PASS] testFuzz_deposit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 269040, ~: 269074)
[PASS] testFuzz_deposit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 217028, ~: 217378)
[PASS] testFuzz_deposit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 355449, ~: 355784)
[PASS] test_deposit_exactBootstrapMintAmount() (gas: 247542)
[PASS] test_deposit_gtBootstrapMintAmount() (gas: 268284)
[PASS] test_deposit_ltBootstrapMintAmount() (gas: 216445)
[PASS] test_deposit_secondDepositorGetsCorrectShares() (gas: 354498)
Test result: ok. 7 passed; 0 failed; finished in 121.15ms

Running 1 test for tests/integration/MakePayment.t.sol:MakePaymentTestsPastDomainEnd
[PASS] test_makePayment_lateLoan3_loan1NotPaid_loan2NotPaid() (gas: 972061)
Test result: ok. 1 passed; 0 failed; finished in 19.90ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentTestsSingleLoanAmortized
[PASS] test_makePayment_earlyPayment_amortized() (gas: 741802)
[PASS] test_makePayment_latePayment_amortized() (gas: 753864)
[PASS] test_makePayment_onTimePayment_amortized() (gas: 741874)
Test result: ok. 3 passed; 0 failed; finished in 21.23ms

Running 5 tests for tests/integration/PoolAccountingViewFunctions.t.sol:TotalAssetsTests
[PASS] test_totalAssets_singleDeposit() (gas: 221563)
[PASS] test_totalAssets_singleLoanFunded() (gas: 2836318)
[PASS] test_totalAssets_singleLoanFundedWithInterest() (gas: 2868314)
[PASS] test_totalAssets_singleLoanFundedWithPayment() (gas: 3087802)
[PASS] test_totalAssets_zeroTotalSupply() (gas: 47222)
Test result: ok. 5 passed; 0 failed; finished in 30.55ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentTestsSingleLoanInterestOnly
[PASS] test_makePayment_earlyPayment_interestOnly() (gas: 713576)
[PASS] test_makePayment_latePayment_interestOnly() (gas: 722688)
[PASS] test_makePayment_onTimePayment_interestOnly() (gas: 710870)
Test result: ok. 3 passed; 0 failed; finished in 14.88ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentTestsTwoLoans
[PASS] test_makePayment_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 1441126)
[PASS] test_makePayment_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 1451832)
[PASS] test_makePayment_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 1438908)
Test result: ok. 3 passed; 0 failed; finished in 23.37ms

Running 1 test for tests/fuzz/Redeem.t.sol:RedeemFuzzTests
[PASS] testDeepFuzz_redeem_all(address[3],uint256[8]) (runs: 100, μ: 836645, ~: 851843)
Test result: ok. 1 passed; 0 failed; finished in 214.59ms

Running 1 test for tests/fuzz/Withdraw.t.sol:WithdrawFuzzTests
[PASS] testDeepFuzz_withdraw_all(address,address,address,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 337363, ~: 328891)
Test result: ok. 1 passed; 0 failed; finished in 144.49ms

Running 1 test for tests/integration/Pause.t.sol:PauseTests
[PASS] test_pauseProtocol() (gas: 1701241)
Test result: ok. 1 passed; 0 failed; finished in 17.96ms

Running 3 tests for tests/integration/Withdraw.t.sol:WithdrawScenarios
[PASS] test_withdrawals_cashInjection() (gas: 10376401)
[PASS] test_withdrawals_poorExchangeRates() (gas: 8754099)
[PASS] test_withdrawals_withUpdateAccounting() (gas: 8987456)
Test result: ok. 3 passed; 0 failed; finished in 34.30ms

Running 5 tests for tests/integration/CloseLoan.t.sol:CloseLoanTests
[PASS] test_closeLoan_failIfLoanIsLate() (gas: 112462)
[PASS] test_closeLoan_failIfNotEnoughFundsSent() (gas: 213536)
[PASS] test_closeLoan_failIfNotLoan() (gas: 26913)
[PASS] test_closeLoan_failWithInsufficientApproval() (gas: 121036)
[PASS] test_closeLoan_success() (gas: 459731)
Test result: ok. 5 passed; 0 failed; finished in 19.15ms

Running 2 tests for tests/integration/PoolAccountingViewFunctions.t.sol:BalanceOfAssetsTests
[PASS] testDeepFuzz_balanceOfAssets(uint256,uint256,uint256) (runs: 100, μ: 362499, ~: 362477)
[PASS] test_balanceOfAssets() (gas: 359140)
Test result: ok. 2 passed; 0 failed; finished in 67.79ms

Running 19 tests for tests/integration/DeployPool.t.sol:DeployPoolTests
[PASS] test_deployPool_failIfCalledLMFactoryDirectly() (gas: 26031)
[PASS] test_deployPool_failIfCalledPMFactoryDirectly() (gas: 26075)
[PASS] test_deployPool_failIfCalledWMFactoryDirectly() (gas: 26054)
[PASS] test_deployPool_failWithAssetNotAllowed() (gas: 351275)
[PASS] test_deployPool_failWithInsufficientPDApproval() (gas: 5892494)
[PASS] test_deployPool_failWithInvalidAsset() (gas: 489147)
[PASS] test_deployPool_failWithInvalidLMFactory() (gas: 75339)
[PASS] test_deployPool_failWithInvalidManagementFee() (gas: 5771587)
[PASS] test_deployPool_failWithInvalidPD() (gas: 52209)
[PASS] test_deployPool_failWithInvalidPMFactory() (gas: 70291)
[PASS] test_deployPool_failWithInvalidWMFactory() (gas: 80302)
[PASS] test_deployPool_failWithNonZeroSupplyAndZeroMigrationAdmin() (gas: 432077)
[PASS] test_deployPool_failWithOwnedPoolManager() (gas: 6186092)
[PASS] test_deployPool_failWithWindowDurationGtCycleDuration() (gas: 5663348)
[PASS] test_deployPool_failWithZeroAsset() (gas: 309577)
[PASS] test_deployPool_failWithZeroWindowDuration() (gas: 5663344)
[PASS] test_deployPool_success() (gas: 6077323)
[PASS] test_deployPool_successWithInitialSupply() (gas: 6018938)
[PASS] test_deployPool_successWithZeroMigrationAdmin() (gas: 5981602)
Test result: ok. 19 passed; 0 failed; finished in 20.16ms

Running 7 tests for tests/e2e/WithdrawManagerScenario.t.sol:WithdrawalManagerScenarioTests
[PASS] test_scenario_fundPayAndRefinanceLoanWithPartialRedemptions_removeSharesAndCloseLoan() (gas: 5071475)
[PASS] test_scenario_impairLoanAndRedeem_defaultLoanAndWithdraw() (gas: 3540247)
[PASS] test_scenario_impairLoanAndRedeem_removeImpairAndRedeem() (gas: 3943325)
[PASS] test_scenario_impairLoanAndRedeem_removeSharesRepayLoanAndRedeem() (gas: 3533565)
[PASS] test_scenario_impairLoanAndRedeem_repayLoanAndWithdraw() (gas: 3593955)
[PASS] test_scenario_impairLoanAndRedeem_startLiquidationAndRedeem_finishLiquidationAndRedeem() (gas: 4808993)
[PASS] test_scenario_multipleUsers_impairLoanAndRedeem_repayLoanAndRedeem() (gas: 21287714)
Test result: ok. 7 passed; 0 failed; finished in 92.05ms

Running 1 test for tests/fuzz/Mint.t.sol:MintFuzzTests
[PASS] testDeepFuzz_mint_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 398408, ~: 432298)
Test result: ok. 1 passed; 0 failed; finished in 208.78ms

Running 4 tests for tests/integration/ImpairLoan.t.sol:ImpairLoanFailureTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 276031)
[PASS] test_impairLoan_notAuthorized() (gas: 45630)
[PASS] test_impairLoan_notLender() (gas: 20175)
[PASS] test_impairLoan_notPoolManager() (gas: 21089)
Test result: ok. 4 passed; 0 failed; finished in 11.97ms

Running 2 tests for tests/integration/ImpairLoan.t.sol:ImpairLoanSuccessTests
[PASS] test_impairLoan_thenCancel() (gas: 848302)
[PASS] test_impairLoan_thenRepay() (gas: 858702)
Test result: ok. 2 passed; 0 failed; finished in 16.88ms

Running 3 tests for tests/integration/Liquidation.t.sol:FinishLiquidationFailureTests
[PASS] test_finishLiquidation_failIfLiquidationNotActive() (gas: 106086)
[PASS] test_finishLiquidation_failIfNotPD() (gas: 50743)
[PASS] test_finishLiquidation_failIfNotPoolManager() (gas: 26291)
Test result: ok. 3 passed; 0 failed; finished in 11.96ms

Running 2 tests for tests/integration/ImpairLoan.t.sol:ImpairAndRefinanceTests
[PASS] test_impairLoan_earlyThenRefinance() (gas: 1221649)
[PASS] test_impairLoan_lateThenRefinance() (gas: 1043861)
Test result: ok. 2 passed; 0 failed; finished in 27.20ms

Running 3 tests for tests/integration/GetLatestPrice.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice_currentPrice() (gas: 76369)
[PASS] test_getLatestPrice_manualOverride() (gas: 50332)
[PASS] test_getLatestPrice_unknownAsset() (gas: 23752)
Test result: ok. 3 passed; 0 failed; finished in 1.63s

Running 8 tests for tests/integration/GetExpectedAmount.t.sol:GetExpectedAmountTests
[PASS] test_getExpectedAmount_currentPrice() (gas: 116917)
[PASS] test_getExpectedAmount_manualOverride() (gas: 92915)
[PASS] test_getExpectedAmount_oracleNotSet() (gas: 60039)
[PASS] test_getExpectedAmount_withMinRatio() (gas: 175203)
[PASS] test_getExpectedAmount_withSlippage() (gas: 175190)
[PASS] test_getExpectedAmount_withSlippageAndMinRatio_minRatioHigher() (gas: 209452)
[PASS] test_getExpectedAmount_withSlippageAndMinRatio_slippageHigher() (gas: 209398)
[PASS] test_getExpectedAmount_zeroAmount() (gas: 116856)
Test result: ok. 8 passed; 0 failed; finished in 2.05s

Running 1 test for tests/fuzz/InterestAccrualFuzzing.t.sol:ClaimTestsSingleLoanInterestOnly
[PASS] testShallowFuzz_interestAccrual(uint256) (runs: 100, μ: 102223649, ~: 102388098)
Test result: ok. 1 passed; 0 failed; finished in 8.68s

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapMintWithPermitTests
[PASS] testFuzz_mintWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 305637, ~: 305655)
[PASS] testFuzz_mintWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 220378, ~: 220021)
[PASS] testFuzz_mintWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 438672, ~: 439027)
[PASS] test_mintWithPermit_exactBootstrapMintAmount() (gas: 284194)
[PASS] test_mintWithPermit_gtBootstrapMintAmount() (gas: 305363)
[PASS] test_mintWithPermit_ltBootstrapMintAmount() (gas: 268229)
[PASS] test_mintWithPermit_secondDepositorGetsCorrectShares() (gas: 437990)
Test result: ok. 7 passed; 0 failed; finished in 8.95s

Running 11 tests for tests/fuzz/PoolViewFunctionsFuzzTest.t.sol:PoolViewFunctionsFuzzTests
[PASS] testFuzz_convertToAssets_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 264323, ~: 264668)
[PASS] testFuzz_convertToAssets_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 10487, ~: 10254)
[PASS] testFuzz_convertToExitShares(uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 285842, ~: 285691)
[PASS] testFuzz_convertToShares_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 264318, ~: 263931)
[PASS] testFuzz_convertToShares_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 10505, ~: 10296)
[PASS] testFuzz_getTotalAssetsFromPM(uint256,uint256) (runs: 100, μ: 96694, ~: 96838)
[PASS] testFuzz_getUnrealizedLossesFromPM(uint256) (runs: 100, μ: 78759, ~: 78490)
[PASS] testFuzz_previewDeposit_whenTotalSupplyExists(uint256,uint256) (runs: 100, μ: 218325, ~: 217808)
[PASS] testFuzz_previewDeposit_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 10583, ~: 10358)
[PASS] testFuzz_previewMint_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 265234, ~: 265207)
[PASS] testFuzz_previewMint_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 10562, ~: 10273)
Test result: ok. 11 passed; 0 failed; finished in 9.05s

Running 27 tests for tests/invariants/ImpairInvariants.t.sol:ImpairInvariants
[PASS] invariant_loanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loan_A_B_loanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_poolManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_poolManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_B_F_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_M() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_N() (runs: 10, calls: 1000, reverts: 0)
Test result: ok. 27 passed; 0 failed; finished in 10.02s

Running 30 tests for tests/invariants/BasicInvariants.t.sol:BasicInvariants
[PASS] invariant_loanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loan_A_B_C_loanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_poolManager_A_totalAssetsEqCashPlusAUM() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_poolManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_B_F_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_M() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_N() (runs: 10, calls: 1000, reverts: 0)
Test result: ok. 30 passed; 0 failed; finished in 12.48s

Running 29 tests for tests/invariants/DefaultsInvariants.t.sol:DefaultsInvariants
[PASS] invariant_loanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_loan_A_B_loanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_poolManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_poolManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_B_F_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_pool_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_M() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_withdrawalManager_N() (runs: 10, calls: 1000, reverts: 0)
Test result: ok. 29 passed; 0 failed; finished in 15.19s

Running 1 test for simulations/local/BasicSimulation.t.sol:BasicSimulation
[PASS] test_basicSimulation() (gas: 24138713)
Test result: ok. 1 passed; 0 failed; finished in 18.21ms

Running 2 tests for simulations/local/MultiLoanSimulation.t.sol:MultiLoanSimulation
[PASS] test_multiLoanSimulation_earlyPayments() (gas: 44435043)
[PASS] test_multiLoanSimulation_variousPayments() (gas: 40087122)
Test result: ok. 2 passed; 0 failed; finished in 55.03ms

Running 20 tests for simulations/local/BusinessSimulations.t.sol:BusinessSimulations
[PASS] test_loanShed_happy() (gas: 148090457)
[PASS] test_loanShed_late() (gas: 148685410)
[PASS] test_loanShed_liquidation_fullCover_partiallyCollateralized_earlyImpairment() (gas: 59905987)
[PASS] test_loanShed_liquidation_fullCover_partiallyCollateralized_lateImpairment() (gas: 59924111)
[PASS] test_loanShed_liquidation_fullCover_partiallyCollateralized_noImpairment() (gas: 58534693)
[PASS] test_loanShed_liquidation_fullCover_uncollateralized_earlyImpairment() (gas: 59555479)
[PASS] test_loanShed_liquidation_fullCover_uncollateralized_lateImpairment() (gas: 59573538)
[PASS] test_loanShed_liquidation_fullCover_uncollateralized_noImpairment() (gas: 58176319)
[PASS] test_loanShed_liquidation_noCover_partiallyCollateralized_earlyImpairment() (gas: 58866657)
[PASS] test_loanShed_liquidation_noCover_partiallyCollateralized_lateImpairment() (gas: 58884737)
[PASS] test_loanShed_liquidation_noCover_partiallyCollateralized_noImpairment() (gas: 57510836)
[PASS] test_loanShed_liquidation_noCover_uncollateralized_earlyImpairment() (gas: 57507875)
[PASS] test_loanShed_liquidation_noCover_uncollateralized_lateImpairment() (gas: 57526000)
[PASS] test_loanShed_liquidation_noCover_uncollateralized_noImpairment() (gas: 56144179)
[PASS] test_loanShed_liquidation_partialCover_partiallyCollateralized_earlyImpairment() (gas: 59547968)
[PASS] test_loanShed_liquidation_partialCover_partiallyCollateralized_lateImpairment() (gas: 59566028)
[PASS] test_loanShed_liquidation_partialCover_partiallyCollateralized_noImpairment() (gas: 58180099)
[PASS] test_loanShed_liquidation_partialCover_uncollateralized_earlyImpairment() (gas: 59140871)
[PASS] test_loanShed_liquidation_partialCover_uncollateralized_lateImpairment() (gas: 59158973)
[PASS] test_loanShed_liquidation_partialCover_uncollateralized_noImpairment() (gas: 57765246)
Test result: ok. 20 passed; 0 failed; finished in 11.51s

Running 8 tests for simulations/local/BusinessSimulationMultiLoan.t.sol:BusinessSimulationsMultiLoan
[PASS] test_businessSimulationMultiLoan() (gas: 253168658)
[PASS] test_businessSimulationMultiLoan1() (gas: 137236912)
[PASS] test_businessSimulationMultiLoan2() (gas: 138230226)
[PASS] test_businessSimulationMultiLoan3() (gas: 122701669)
[PASS] test_businessSimulationMultiLoan4() (gas: 138530807)
[PASS] test_businessSimulationMultiLoan5() (gas: 101513974)
[PASS] test_businessSimulationMultiLoan6() (gas: 89079957)
[PASS] test_businessSimulationMultiLoan7() (gas: 136758495)
Test result: ok. 8 passed; 0 failed; finished in 11.69s

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV302LoansTests
[PASS] test_rollback_from_V302_loans() (gas: 2036397)
Test result: ok. 1 passed; 0 failed; finished in 92.82ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV302MigrationLoansTests
[PASS] test_rollback_from_V302_migration_loans() (gas: 1314640)
Test result: ok. 1 passed; 0 failed; finished in 108.11ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV400DebtLockersOfMigrationLoansTests
[PASS] test_rollback_from_V400_debtLockers_of_migration_loans() (gas: 1481836)
Test result: ok. 1 passed; 0 failed; finished in 99.45ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV400DebtLockersTests
[PASS] test_rollback_from_V400_debtLockers() (gas: 1687683)
Test result: ok. 1 passed; 0 failed; finished in 49.76ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV400LoansTests
[PASS] test_rollback_from_v400_loans() (gas: 4736141)
Test result: ok. 1 passed; 0 failed; finished in 601.08ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV401DebtLockersTests
[PASS] test_rollback_from_V401_debtLockers() (gas: 2600246)
Test result: ok. 1 passed; 0 failed; finished in 70.87ms

Running 1 test for simulations/mainnet/LoanUpgradeTest.t.sol:LoanUpgradeTest
[PASS] test_loanUpgrade() (gas: 10228046)
Test result: ok. 1 passed; 0 failed; finished in 90.59ms

Running 1 test for simulations/mainnet/Lifecycle.t.sol:Lifecycle
[PASS] test_simpleLifecycle() (gas: 129157472)
Test result: ok. 1 passed; 0 failed; finished in 27.44s

Running 1 test for simulations/mainnet/MigrationPreparation.t.sol:MigrationPreparationTest
[PASS] test_migrationPreparation() (gas: 1056857354)
Test result: ok. 1 passed; 0 failed; finished in 29.13s

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromSetPendingLenderTests
[PASS] test_rollback_from_setPendingLender() (gas: 2036358)
Test result: ok. 1 passed; 0 failed; finished in 1.14s

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromTransferredOwnershipOsLoansTests
[PASS] test_rollback_from_setPendingLender() (gas: 2088408)
Test result: ok. 1 passed; 0 failed; finished in 569.58ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV200LoanManagersTests
[PASS] test_rollback_from_v200_loanManagers() (gas: 1060136)
Test result: ok. 1 passed; 0 failed; finished in 557.80ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromV301LoansTests
[PASS] test_rollback_from_V301_loans() (gas: 1770258)
Test result: ok. 1 passed; 0 failed; finished in 58.04ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:RollbackFromFundedMigrationLoansTests
[PASS] test_rollback_from_funded_migration_loans() (gas: 3193135)
Test result: ok. 1 passed; 0 failed; finished in 99.03ms

Running 1 test for simulations/mainnet/LiquidityMigration.t.sol:LiquidityMigrationTests
[PASS] test_liquidityMigration_complete() (gas: 746741895)
Test result: ok. 1 passed; 0 failed; finished in 24.52s

```

# `debt-locker (v4.0.0)`

```
Running 3 tests for tests/DebtLocker.t.sol:DebtLockerV4Migration
[PASS] test_acl_acceptLender() (gas: 1713915)
[PASS] test_acl_setPendingLender() (gas: 1729188)
[PASS] test_acl_upgradeToV4() (gas: 808761)
Test result: ok. 3 passed; 0 failed; finished in 4.93ms

Running 27 tests for tests/DebtLocker.t.sol:DebtLockerTests
[PASS] testFail_fundsToCaptureForNextClaim() (gas: 1147077)
[PASS] test_acceptNewTerms_withAmountIncrease(uint256) (runs: 256, μ: 1895657, ~: 1895597)
[PASS] test_acl_factory_migrate() (gas: 5874719)
[PASS] test_acl_factory_setImplementation() (gas: 5849008)
[PASS] test_acl_globalAdmin_upgrade() (gas: 6994363)
[PASS] test_acl_poolDelegate_acceptNewTerms() (gas: 1715014)
[PASS] test_acl_poolDelegate_rejectNewTerms() (gas: 1655215)
[PASS] test_acl_poolDelegate_setAllowedSlippage() (gas: 780709)
[PASS] test_acl_poolDelegate_setAuctioneer() (gas: 1960407)
[PASS] test_acl_poolDelegate_setFundsToCapture() (gas: 780744)
[PASS] test_acl_poolDelegate_setMinRatio() (gas: 780721)
[PASS] test_acl_pool_claim() (gas: 6582468)
[PASS] test_acl_pool_triggerDefault() (gas: 7355575)
[PASS] test_claim(uint256,uint256) (runs: 256, μ: 1323121, ~: 1325408)
[PASS] test_claim_liquidation_equalToPrincipal(uint256) (runs: 256, μ: 2583563, ~: 2584032)
[PASS] test_claim_liquidation_greaterThanPrincipal(uint256,uint256) (runs: 256, μ: 2585469, ~: 2585858)
[PASS] test_claim_liquidation_shortfall(uint256,uint256) (runs: 256, μ: 2632411, ~: 2716541)
[PASS] test_fundsToCaptureForNextClaim() (gas: 1176138)
[PASS] test_fundsToCaptureWhileInDefault() (gas: 2579338)
[PASS] test_getGlobals() (gas: 6944432)
[PASS] test_getPoolDelegate() (gas: 6945338)
[PASS] test_initialize_invalidCollateralAsset() (gas: 886712)
[PASS] test_initialize_invalidLiquidityAsset() (gas: 892112)
[PASS] test_isLiquidationActive() (gas: 8799893)
[PASS] test_liquidation_dos_prevention(uint256,uint256) (runs: 256, μ: 2597584, ~: 2597965)
[PASS] test_liquidation_pullFunds(uint256,uint256) (runs: 256, μ: 1965877, ~: 1966247)
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 772907)
Test result: ok. 27 passed; 0 failed; finished in 447.77ms
```

# `erc20 (v1.0.1)`

```
Running 1 test for contracts/test/ERC20.t.sol:ERC20Invariants
[PASS] invariant_balanceSum() (runs: 256, calls: 3840, reverts: 2331)
Test result: ok. 1 passed; 0 failed; finished in 187.83ms

Running 14 tests for contracts/test/ERC20.t.sol:ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 85817, ~: 86353)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 257340, ~: 257338)
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
Test result: ok. 14 passed; 0 failed; finished in 885.91ms

Running 14 tests for contracts/test/ERC20.t.sol:ERC20BaseTest
[PASS] invariant_metadata() (runs: 256, calls: 3840, reverts: 2399)
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 30703, ~: 31714)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 27823, ~: 419)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 35435, ~: 35448)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 36505, ~: 38339)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 38358, ~: 38358)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 786502, ~: 781402)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 53217, ~: 54306)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 59230, ~: 61407)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 346420, ~: 354380)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 351306, ~: 355204)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 341073, ~: 340590)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 322652, ~: 322238)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 332520, ~: 332521)
Test result: ok. 14 passed; 0 failed; finished in 1.08s
```

# `globals-v2 (v1.0.0)`

```
Running 2 tests for tests/MapleGlobals.t.sol:SetDefaultTimelockParametersTests
[PASS] test_setDefaultTimelockParameters() (gas: 49345)
[PASS] test_setDefaultTimelockParameters_notGovernor() (gas: 19443)
Test result: ok. 2 passed; 0 failed; finished in 940.13µs

Running 2 tests for tests/MapleGlobals.t.sol:SetBootstrapMintTests
[PASS] test_setBootstrapMint() (gas: 52884)
[PASS] test_setBootstrapMint_notGovernor() (gas: 57628)
Test result: ok. 2 passed; 0 failed; finished in 956.13µs

Running 3 tests for tests/MapleGlobals.t.sol:ScheduleCallTests
[PASS] test_scheduleCal_overwrite() (gas: 85322)
[PASS] test_scheduleCall() (gas: 70297)
[PASS] test_scheduleCall_defaultState() (gas: 19324)
Test result: ok. 3 passed; 0 failed; finished in 1.14ms

Running 3 tests for tests/MapleGlobals.t.sol:SetPlatformServiceFeeRateTests
[PASS] test_setPlatformServiceFeeRate() (gas: 53003)
[PASS] test_setPlatformServiceFeeRate_notGovernor() (gas: 57743)
[PASS] test_setPlatformServiceFeeRate_outOfBounds() (gas: 57725)
Test result: ok. 3 passed; 0 failed; finished in 1.07ms

Running 3 tests for tests/MapleGlobals.t.sol:ActivatePoolTests
[PASS] test_activatePoolManager_alreadyOwns() (gas: 59714)
[PASS] test_activatePoolManager_notGovernor() (gas: 63876)
[PASS] test_activatePoolManager_success() (gas: 61931)
Test result: ok. 3 passed; 0 failed; finished in 1.15ms

Running 2 tests for tests/MapleGlobals.t.sol:SetValidFactoryTests
[PASS] test_setValidFactory() (gas: 46250)
[PASS] test_setValidFactory_notGovernor() (gas: 58545)
Test result: ok. 2 passed; 0 failed; finished in 901.50µs

Running 2 tests for tests/MapleGlobals.t.sol:SetMinCoverAmountTests
[PASS] test_setMinCoverAmount() (gas: 52822)
[PASS] test_setMinCoverAmount_notGovernor() (gas: 57605)
Test result: ok. 2 passed; 0 failed; finished in 863.54µs

Running 3 tests for tests/MapleGlobals.t.sol:SetPlatformManagementFeeRateTests
[PASS] test_setPlatformManagementFeeRate() (gas: 53003)
[PASS] test_setPlatformManagementFeeRate_notGovernor() (gas: 57703)
[PASS] test_setPlatformManagementFeeRate_outOfBounds() (gas: 57773)
Test result: ok. 3 passed; 0 failed; finished in 826.83µs

Running 3 tests for tests/MapleGlobals.t.sol:SetSecurityAdminTests
[PASS] test_setSecurityAdmin() (gas: 51795)
[PASS] test_setSecurityAdmin_notGovernor() (gas: 21339)
[PASS] test_setSecurityAdmin_zeroAddressCheck() (gas: 22075)
Test result: ok. 3 passed; 0 failed; finished in 865.00µs

Running 2 tests for tests/MapleGlobals.t.sol:SetPendingGovernorTests
[PASS] test_setPendingGovernor() (gas: 51185)
[PASS] test_setPendingGovernor_notGovernor() (gas: 21358)
Test result: ok. 2 passed; 0 failed; finished in 774.63µs

Running 3 tests for tests/MapleGlobals.t.sol:SetMaxCoverLiquidationPercentTests
[PASS] test_setMaxCoverLiquidationPercent() (gas: 52894)
[PASS] test_setMaxCoverLiquidationPercent_gt100() (gas: 57683)
[PASS] test_setMaxCoverLiquidationPercent_notGovernor() (gas: 57701)
Test result: ok. 3 passed; 0 failed; finished in 849.54µs

Running 2 tests for tests/MapleGlobals.t.sol:SetValidPoolAssetTests
[PASS] test_setValidPoolAsset() (gas: 44456)
[PASS] test_setValidPoolAsset_notGovernor() (gas: 57678)
Test result: ok. 2 passed; 0 failed; finished in 801.25µs

Running 3 tests for tests/MapleGlobals.t.sol:SetPriceOracleTests
[PASS] test_setPriceOracle() (gas: 55648)
[PASS] test_setPriceOracle_notGovernor() (gas: 23801)
[PASS] test_setPriceOracle_zeroAddressCheck() (gas: 47509)
Test result: ok. 3 passed; 0 failed; finished in 879.83µs

Running 1 test for tests/MapleGlobals.t.sol:IsValidScheduledCallTests
[PASS] test_isValidScheduledCall() (gas: 94554)
Test result: ok. 1 passed; 0 failed; finished in 2.19ms

Running 2 tests for tests/MapleGlobals.t.sol:SetManualOverridePriceTests
[PASS] test_setManualOverridePrice() (gas: 460431)
[PASS] test_setManualOverridePrice_notGovernor() (gas: 57629)
Test result: ok. 2 passed; 0 failed; finished in 1.02ms

Running 3 tests for tests/MapleGlobals.t.sol:SetPlatformOriginationFeeRateTests
[PASS] test_setPlatformOriginationFeeRate() (gas: 52911)
[PASS] test_setPlatformOriginationFeeRate_notGovernor() (gas: 57721)
[PASS] test_setPlatformOriginationFeeRate_outOfBounds() (gas: 57725)
Test result: ok. 3 passed; 0 failed; finished in 801.58µs

Running 2 tests for tests/MapleGlobals.t.sol:SetMigrationAdminTests
[PASS] test_setMigrationAdmin() (gas: 51688)
[PASS] test_setMigrationAdmin_notGovernor() (gas: 21270)
Test result: ok. 2 passed; 0 failed; finished in 717.79µs

Running 2 tests for tests/MapleGlobals.t.sol:SetProtocolPauseTests
[PASS] test_setProtocolPause() (gas: 33996)
[PASS] test_setProtocolPause_notSecurityAdmin() (gas: 18829)
Test result: ok. 2 passed; 0 failed; finished in 768.58µs

Running 2 tests for tests/MapleGlobals.t.sol:SetValidPoolDelegate
[PASS] test_setValidPoolDelegate() (gas: 44884)
[PASS] test_setValidPoolDelegate_notGovernor() (gas: 57676)
Test result: ok. 2 passed; 0 failed; finished in 786.00µs

Running 2 tests for tests/MapleGlobals.t.sol:SetValidBorrowerTests
[PASS] test_setValidBorrower() (gas: 44227)
[PASS] test_setValidBorrower_notGovernor() (gas: 57592)
Test result: ok. 2 passed; 0 failed; finished in 727.54µs

Running 2 tests for tests/MapleGlobals.t.sol:SetValidPoolDeployer
[PASS] test_setValidDeployer() (gas: 44177)
[PASS] test_setValidDeployer_notGovernor() (gas: 57590)
Test result: ok. 2 passed; 0 failed; finished in 886.25µs

Running 4 tests for tests/MapleGlobals.t.sol:SetTimelockWindowTests
[PASS] test_setTimelockWindow() (gas: 56820)
[PASS] test_setTimelockWindow_notGovernor() (gas: 22320)
[PASS] test_setTimelockWindows() (gas: 94434)
[PASS] test_setTimelockWindows_notGovernor() (gas: 25153)
Test result: ok. 4 passed; 0 failed; finished in 929.00µs

Running 4 tests for tests/MapleGlobals.t.sol:TransferOwnedPoolTests
[PASS] test_transferOwnedPool() (gas: 72441)
[PASS] test_transferOwnedPool_alreadyOwns() (gas: 203023)
[PASS] test_transferOwnedPool_notPoolDelegate() (gas: 28899)
[PASS] test_transferOwnedPool_notPoolManager() (gas: 23811)
Test result: ok. 4 passed; 0 failed; finished in 988.63µs

Running 3 tests for tests/MapleGlobals.t.sol:SetMapleTreasuryTests
[PASS] test_setMapleTreasury() (gas: 51653)
[PASS] test_setMapleTreasury_notGovernor() (gas: 21358)
[PASS] test_setMapleTreasury_zeroAddressCheck() (gas: 22050)
Test result: ok. 3 passed; 0 failed; finished in 3.43ms

Running 2 tests for tests/MapleGlobals.t.sol:TransferGovernorTests
[PASS] test_acceptGovernor() (gas: 54213)
[PASS] test_acceptGovernor_notPendingGovernor() (gas: 18489)
Test result: ok. 2 passed; 0 failed; finished in 759.92µs

Running 6 tests for tests/MapleGlobals.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice() (gas: 125934)
[PASS] test_getLatestPrice_manualOverride() (gas: 147406)
[PASS] test_getLatestPrice_oracleNotSet() (gas: 66405)
[PASS] test_getLatestPrice_roundNotComplete() (gas: 36985)
[PASS] test_getLatestPrice_staleData() (gas: 81567)
[PASS] test_getLatestPrice_zeroPrice() (gas: 102839)
Test result: ok. 6 passed; 0 failed; finished in 3.64ms

Running 2 tests for tests/MapleGlobals.t.sol:SetValidCollateralTests
[PASS] test_setValidCollateral() (gas: 44196)
[PASS] test_setValidCollateral_notGovernor() (gas: 57550)
Test result: ok. 2 passed; 0 failed; finished in 731.21µs

Running 3 tests for tests/MapleGlobals.t.sol:UnScheduleCallTests
[PASS] test_unscheduleCall() (gas: 31581)
[PASS] test_unscheduleCall_asGovernor() (gas: 36557)
[PASS] test_unscheduleCall_notGovernor() (gas: 22396)
Test result: ok. 3 passed; 0 failed; finished in 917.08µs
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

# `loan (v3.0.1)`

```
Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetCollateralRequiredForTests
[PASS] test_getCollateralRequiredFor() (gas: 11303)
Test result: ok. 1 passed; 0 failed; finished in 469.13µs

Running 2 tests for contracts/test/MapleLoan.t.sol:MapleLoanRoleTests
[PASS] test_transferBorrowerRole() (gas: 1247445)
[PASS] test_transferLenderRole() (gas: 1359334)
Test result: ok. 2 passed; 0 failed; finished in 1.62ms

Running 3 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetInstallmentTests
[PASS] test_getInstallment_edgeCases() (gas: 14432)
[PASS] test_getInstallment_genericFuzzing(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 11865, ~: 11983)
[PASS] test_getInstallment_withFixtures() (gas: 8485)
Test result: ok. 3 passed; 0 failed; finished in 11.31ms

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetInterestTests
[PASS] test_getInterest() (gas: 7724)
Test result: ok. 1 passed; 0 failed; finished in 350.50µs

Running 2 tests for contracts/test/Payments.t.sol:EarlyRepaymentsTest
[PASS] test_payments_earlyRepayment_flatRate_case1() (gas: 780488)
[PASS] test_payments_earlyRepayment_flatRate_case2() (gas: 735408)
Test result: ok. 2 passed; 0 failed; finished in 2.83ms

Running 2 tests for contracts/test/Payments.t.sol:FullyAmortizedPaymentsTest
[PASS] test_payments_fullyAmortized_case1() (gas: 832313)
[PASS] test_payments_fullyAmortized_case2() (gas: 832208)
Test result: ok. 2 passed; 0 failed; finished in 3.49ms

Running 2 tests for contracts/test/Payments.t.sol:InterestOnlyPaymentsTest
[PASS] test_payments_interestOnly_case1() (gas: 848198)
[PASS] test_payments_interestOnly_case2() (gas: 848216)
Test result: ok. 2 passed; 0 failed; finished in 3.48ms

Running 54 tests for contracts/test/MapleLoan.t.sol:MapleLoanTests
[PASS] test_acceptBorrower_acl() (gas: 39238)
[PASS] test_acceptLender_acl() (gas: 39212)
[PASS] test_acceptNewTerms_acl() (gas: 1938581)
[PASS] test_acceptNewTerms_extraFunds() (gas: 4242972)
[PASS] test_acceptNewTerms_pullPattern() (gas: 2051214)
[PASS] test_acceptNewTerms_pushPattern() (gas: 2041493)
[PASS] test_claimFunds_acl() (gas: 1690115)
[PASS] test_closeLoan_pullPatternAsBorrower() (gas: 2131041)
[PASS] test_closeLoan_pullPatternAsNonBorrower() (gas: 1637340)
[PASS] test_closeLoan_pullPatternUsingDrawable() (gas: 2960440)
[PASS] test_closeLoan_pushPatternAsBorrower() (gas: 2135839)
[PASS] test_closeLoan_pushPatternAsNonBorrower() (gas: 1642163)
[PASS] test_closeLoan_pushPatternUsingDrawable() (gas: 2893006)
[PASS] test_drawdownFunds_acl() (gas: 1783206)
[PASS] test_drawdownFunds_pullPatternForCollateral() (gas: 3532650)
[PASS] test_drawdownFunds_pushPatternForCollateral() (gas: 3487630)
[PASS] test_drawdownFunds_withoutAdditionalCollateralRequired() (gas: 3234095)
[PASS] test_excessCollateral_varyCollateral() (gas: 137668)
[PASS] test_excessCollateral_varyDrawableFunds() (gas: 126628)
[PASS] test_excessCollateral_varyPrincipal() (gas: 88749)
[PASS] test_fundLoan_pullPattern() (gas: 4103999)
[PASS] test_fundLoan_pullPatternFundsRedirect() (gas: 1852546)
[PASS] test_fundLoan_pullPatternOverFund() (gas: 4137072)
[PASS] test_fundLoan_pushPattern() (gas: 4133889)
[PASS] test_fundLoan_pushPatternExtraFundsWhileActive() (gas: 4036238)
[PASS] test_fundLoan_pushPatternExtraFundsWhileNotActive() (gas: 4057027)
[PASS] test_fundLoan_pushPatternFundsRedirect() (gas: 1807599)
[PASS] test_fundLoan_pushPatternOverFund() (gas: 4167078)
[PASS] test_getAdditionalCollateralRequiredFor_varyAmount() (gas: 119295)
[PASS] test_getAdditionalCollateralRequiredFor_varyCollateralRequired() (gas: 109340)
[PASS] test_getAdditionalCollateralRequiredFor_varyDrawableFunds() (gas: 111563)
[PASS] test_getAdditionalCollateralRequiredFor_varyPrincipal() (gas: 131954)
[PASS] test_makePayment_pullPatternAsBorrower() (gas: 2175473)
[PASS] test_makePayment_pullPatternAsNonBorrower() (gas: 1681751)
[PASS] test_makePayment_pullPatternUsingDrawable() (gas: 2990902)
[PASS] test_makePayment_pushPatternAsBorrower() (gas: 2172796)
[PASS] test_makePayment_pushPatternAsNonBorrower() (gas: 1679139)
[PASS] test_makePayment_pushPatternUsingDrawable() (gas: 2923488)
[PASS] test_migrate_acl() (gas: 62967)
[PASS] test_postCollateral_pullPattern() (gas: 1692470)
[PASS] test_postCollateral_pushPattern() (gas: 1624305)
[PASS] test_proposeNewTerms_acl() (gas: 204864)
[PASS] test_proposeNewTerms_invalidDeadline() (gas: 225808)
[PASS] test_rejectNewTerms_acl() (gas: 253665)
[PASS] test_removeCollateral_acl() (gas: 1742151)
[PASS] test_repossess_acl() (gas: 1689024)
[PASS] test_returnFunds_pullPattern() (gas: 1694613)
[PASS] test_returnFunds_pushPattern() (gas: 1626444)
[PASS] test_setBorrower_acl() (gas: 55025)
[PASS] test_setImplementation_acl() (gas: 36964)
[PASS] test_setLender_acl() (gas: 55130)
[PASS] test_skim_acl() (gas: 1699975)
[PASS] test_superFactory() (gas: 9094)
[PASS] test_upgrade_acl_globalsAdmin() (gas: 3308702)
Test result: ok. 54 passed; 0 failed; finished in 15.73ms

Running 5 tests for contracts/test/Payments.t.sol:LateRepaymentsTest
[PASS] test_payments_dailyInterestAccrual() (gas: 745568)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case1() (gas: 862673)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case2() (gas: 860421)
[PASS] test_payments_lateRepayment_flatRate_case1() (gas: 845084)
[PASS] test_payments_lateRepayment_flatRate_case2() (gas: 845151)
Test result: ok. 5 passed; 0 failed; finished in 5.76ms

Running 2 tests for contracts/test/Payments.t.sol:PartiallyAmortizedPaymentsTest
[PASS] test_payments_partiallyAmortized_case1() (gas: 848189)
[PASS] test_payments_partiallyAmortized_case2() (gas: 848128)
Test result: ok. 2 passed; 0 failed; finished in 3.48ms

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ReturnFundsTests
[PASS] test_returnFunds(uint256) (runs: 256, μ: 99837, ~: 101470)
[PASS] test_returnFunds_collateralAsset() (gas: 798951)
Test result: ok. 2 passed; 0 failed; finished in 29.41ms

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ScaledExponentTests
[PASS] test_scaledExponent_setOne() (gas: 22626)
[PASS] test_scaledExponent_setTwo() (gas: 36799)
Test result: ok. 2 passed; 0 failed; finished in 549.67µs

Running 3 tests for contracts/test/MapleLoanStories.t.sol:MapleLoanStoryTests
[PASS] test_story_fullyAmortized() (gas: 3645417)
[PASS] test_story_interestOnly() (gas: 3602070)
[PASS] test_story_redirectFundsToLender() (gas: 3463409)
Test result: ok. 3 passed; 0 failed; finished in 3.97ms

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetNextPaymentBreakdownTests
[PASS] test_getNextPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 230872, ~: 234232)
Test result: ok. 1 passed; 0 failed; finished in 32.36ms

Running 6 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetPaymentBreakdownTests
[PASS] test_getPaymentBreakdown_onePaymentFourPeriodsLate() (gas: 10261)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodBeforeDue() (gas: 9079)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodLate() (gas: 10283)
[PASS] test_getPaymentBreakdown_onePaymentOneSecondBeforeDue() (gas: 9133)
[PASS] test_getPaymentBreakdown_onePaymentThreePeriodsLate() (gas: 10216)
[PASS] test_getPaymentBreakdown_onePaymentTwoPeriodsLate() (gas: 10238)
Test result: ok. 6 passed; 0 failed; finished in 544.38µs

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetEarlyPaymentBreakdownTests
[PASS] test_getEarlyPaymentBreakdown(uint256,uint256,uint256) (runs: 256, μ: 397456, ~: 403328)
Test result: ok. 1 passed; 0 failed; finished in 44.37ms

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetPeriodicInterestRateTests
[PASS] test_getPeriodicInterestRate() (gas: 7255)
Test result: ok. 1 passed; 0 failed; finished in 332.00µs

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_CollateralMaintainedTests
[PASS] test_isCollateralMaintained(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 119303, ~: 124389)
[PASS] test_isCollateralMaintained_edgeCases() (gas: 164925)
Test result: ok. 2 passed; 0 failed; finished in 16.81ms

Running 7 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_RepossessTests
[PASS] testFail_repossess_beforePaymentDue() (gas: 31036)
[PASS] testFail_repossess_onGracePeriod() (gas: 30999)
[PASS] testFail_repossess_onPaymentDue() (gas: 31002)
[PASS] testFail_repossess_withinGracePeriod() (gas: 31022)
[PASS] test_repossess() (gas: 127331)
[PASS] test_repossess_collateralTransferFailed() (gas: 230358)
[PASS] test_repossess_fundsTransferFailed() (gas: 265812)
Test result: ok. 7 passed; 0 failed; finished in 1.52ms

Running 2 tests for contracts/test/MapleLoanFactory.t.sol:MapleLoanFactoryTest
[PASS] testFail_createInstance_saltAndArgumentsCollision() (gas: 8937393460516741681)
[PASS] test_createInstance(bytes32) (runs: 256, μ: 542963, ~: 542963)
Test result: ok. 2 passed; 0 failed; finished in 63.66ms

Running 10 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_AcceptNewTermsTests
[PASS] test_acceptNewTerms() (gas: 100154)
[PASS] test_acceptNewTerms_afterDeadline() (gas: 129788)
[PASS] test_acceptNewTerms_callFailed() (gas: 155592)
[PASS] test_acceptNewTerms_commitmentMismatch_emptyCallsArray() (gas: 107931)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedCalls() (gas: 107043)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 106838)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 474387)
[PASS] test_acceptNewTerms_fuzzEstablishmentFees(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 124683, ~: 129001)
[PASS] test_acceptNewTerms_insufficientCollateral() (gas: 190800)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 114267)
Test result: ok. 10 passed; 0 failed; finished in 49.59ms

Running 3 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ClaimFundsTests
[PASS] testFail_claimFunds_insufficientClaimableFunds(uint256,uint256) (runs: 256, μ: 82131, ~: 82236)
[PASS] test_claimFunds(uint256,uint256) (runs: 256, μ: 111177, ~: 113896)
[PASS] test_claimFunds_transferFail() (gas: 38630)
Test result: ok. 3 passed; 0 failed; finished in 22.48ms

Running 4 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_PostCollateralTests
[PASS] testFail_postCollateral_invalidCollateralAsset() (gas: 74556)
[PASS] test_postCollateral_multiple(uint256,uint256) (runs: 256, μ: 124925, ~: 126706)
[PASS] test_postCollateral_once(uint256) (runs: 256, μ: 83427, ~: 87159)
[PASS] test_postCollateral_withUnaccountedFundsAsset() (gas: 865305)
Test result: ok. 4 passed; 0 failed; finished in 42.61ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceMiscellaneousTests
[PASS] testFail_refinance_invalidRefinancer() (gas: 4347193)
Test result: ok. 1 passed; 0 failed; finished in 1.51ms

Running 6 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_DrawdownFundsTests
[PASS] testFail_drawdownFunds_collateralNotMaintained(uint256,uint256,uint256) (runs: 256, μ: 200647, ~: 203368)
[PASS] testFail_drawdownFunds_insufficientDrawableFunds(uint256,uint256) (runs: 256, μ: 127655, ~: 127620)
[PASS] test_drawdownFunds_multipleDrawdowns(uint256,uint256,uint256) (runs: 256, μ: 178379, ~: 178343)
[PASS] test_drawdownFunds_postedCollateral(uint256,uint256,uint256) (runs: 256, μ: 201816, ~: 206907)
[PASS] test_drawdownFunds_transferFailed() (gas: 38736)
[PASS] test_drawdownFunds_withoutPostedCollateral(uint256,uint256) (runs: 256, μ: 160354, ~: 164568)
Test result: ok. 6 passed; 0 failed; finished in 72.52ms

Running 5 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_RejectNewTermsTests
[PASS] test_rejectNewTerms_commitmentMismatch_emptyCallsArray() (gas: 29621)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedCalls() (gas: 30406)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 30269)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 390791)
[PASS] test_rejectNewTerms_success() (gas: 26206)
Test result: ok. 5 passed; 0 failed; finished in 717.67µs

Running 4 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_InitializeTests
[PASS] test_initialize_invalidBorrower() (gas: 37979)
[PASS] test_initialize_invalidEndingPrincipal() (gas: 31626)
[PASS] test_initialize_invalidPrincipal() (gas: 31529)
[PASS] test_initialize_x() (gas: 381027)
Test result: ok. 4 passed; 0 failed; finished in 889.96µs

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ProposeNewTermsTests
[PASS] test_proposeNewTerms(address,uint256,uint256,uint256,uint256) (runs: 256, μ: 36593, ~: 36593)
[PASS] test_proposeNewTerms_emptyArray(address,uint256) (runs: 256, μ: 9857, ~: 9857)
Test result: ok. 2 passed; 0 failed; finished in 35.01ms

Running 11 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_FundLoanTests
[PASS] testFail_fundLoan_claimImmediatelyAfterFullFunding(uint256,uint256) (runs: 256, μ: 227918, ~: 227909)
[PASS] testFail_fundLoan_doubleFund(uint256) (runs: 256, μ: 231030, ~: 231015)
[PASS] testFail_fundLoan_invalidFundsAsset() (gas: 188828)
[PASS] testFail_fundLoan_partialFunding(uint256) (runs: 256, μ: 204773, ~: 206150)
[PASS] testFail_fundLoan_withInvalidLender() (gas: 5742)
[PASS] testFail_fundLoan_withoutSendingAsset() (gas: 160106)
[PASS] test_fundLoan_fullFunding(uint256) (runs: 256, μ: 256669, ~: 256655)
[PASS] test_fundLoan_nextPaymentDueDateAlreadySet() (gas: 153105)
[PASS] test_fundLoan_noPaymentsRemaining() (gas: 62511)
[PASS] test_fundLoan_overFunding(uint256,uint256) (runs: 256, μ: 236511, ~: 236486)
[PASS] test_fundLoan_withUnaccountedCollateralAsset() (gas: 1003435)
Test result: ok. 11 passed; 0 failed; finished in 149.53ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceCollateralRequiredTest
[PASS] test_refinance_collateralRequired(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4335727, ~: 4338464)
Test result: ok. 1 passed; 0 failed; finished in 233.83ms

Running 16 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetUnaccountedAmountTests
[PASS] test_getUnaccountedAmount_claimableFunds(uint256,uint256) (runs: 256, μ: 90085, ~: 89905)
[PASS] test_getUnaccountedAmount_collateral(uint256,uint256) (runs: 256, μ: 87910, ~: 87746)
[PASS] test_getUnaccountedAmount_collateralAsset() (gas: 74605)
[PASS] test_getUnaccountedAmount_complex(uint256,uint256,uint256,uint256) (runs: 256, μ: 841439, ~: 843476)
[PASS] test_getUnaccountedAmount_drawableFunds(uint256,uint256) (runs: 256, μ: 90178, ~: 89984)
[PASS] test_getUnaccountedAmount_drawableFundsAndClaimableFunds(uint256,uint256,uint256) (runs: 256, μ: 111972, ~: 112086)
[PASS] test_getUnaccountedAmount_drawableFundsAndClaimableFundsAndCollateral(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 191143, ~: 191060)
[PASS] test_getUnaccountedAmount_drawableFundsAndClaimableFundsAndCollateral_fundsAssetEqCollateralAsset(uint256,uint256,uint256,uint256) (runs: 256, μ: 139942, ~: 140013)
[PASS] test_getUnaccountedAmount_fundsAsset() (gas: 77199)
[PASS] test_getUnaccountedAmount_newFundsLtClaimableFunds(uint256) (runs: 256, μ: 101546, ~: 101519)
[PASS] test_getUnaccountedAmount_newFundsLtCollateral(uint256) (runs: 256, μ: 97098, ~: 97067)
[PASS] test_getUnaccountedAmount_newFundsLtDrawableFunds(uint256) (runs: 256, μ: 101597, ~: 101577)
[PASS] test_getUnaccountedAmount_randomToken() (gas: 131504)
[PASS] test_getUnaccountedAmount_withClaimableFunds(uint256,uint256) (runs: 256, μ: 84875, ~: 89166)
[PASS] test_getUnaccountedAmount_withCollateral(uint256,uint256) (runs: 256, μ: 81940, ~: 87018)
[PASS] test_getUnaccountedAmount_withDrawableFunds(uint256,uint256) (runs: 256, μ: 85866, ~: 89225)
Test result: ok. 16 passed; 0 failed; finished in 218.61ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceMultipleParameterTest
[PASS] test_refinance_multipleParameters(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4346809, ~: 4349888)
Test result: ok. 1 passed; 0 failed; finished in 201.04ms

Running 2 tests for contracts/test/Refinancer.t.sol:RefinanceDeadlineTests
[PASS] test_refinance_afterDeadline(uint256,uint256,uint256) (runs: 256, μ: 4262262, ~: 4268280)
[PASS] test_refinance_differentDeadline(uint256,uint256,uint256) (runs: 256, μ: 4243883, ~: 4243970)
Test result: ok. 2 passed; 0 failed; finished in 380.78ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceInterestAndFeeTests
[PASS] test_acceptNewTerms_makePayment_withFeesAndRefinanceInterest() (gas: 4748673)
Test result: ok. 1 passed; 0 failed; finished in 1.52ms

Running 8 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_MakePaymentTests
[PASS] test_makePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 319300, ~: 323404)
[PASS] test_makePayment_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 336577, ~: 340573)
[PASS] test_makePayment_lastPaymentClearsLoan(uint256,uint256,uint256,uint256) (runs: 256, μ: 301077, ~: 303426)
[PASS] test_makePayment_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 317165, ~: 321008)
[PASS] test_makePayment_withFees(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 400351, ~: 401332)
[PASS] test_makePayment_withFeesButDelegateFailures() (gas: 393841)
[PASS] test_makePayment_withFeesButTreasuryFailures() (gas: 395545)
[PASS] test_makePayment_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 308793, ~: 309750)
Test result: ok. 8 passed; 0 failed; finished in 254.88ms

Running 12 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_CloseLoanTests
[PASS] test_closeLoan(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 252975, ~: 253961)
[PASS] test_closeLoan_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 296461, ~: 296966)
[PASS] test_closeLoan_latePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 241937, ~: 243419)
[PASS] test_closeLoan_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 253694, ~: 255553)
[PASS] test_closeLoan_withFees(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 315946, ~: 316022)
[PASS] test_closeLoan_withFeesButNoDelegateAtLender() (gas: 272920)
[PASS] test_closeLoan_withFeesButNoTreasuryAtGlobals() (gas: 274476)
[PASS] test_closeLoan_withFeesButZeroDelegate() (gas: 279461)
[PASS] test_closeLoan_withFeesButZeroGlobals() (gas: 276274)
[PASS] test_closeLoan_withFeesButZeroLender() (gas: 274754)
[PASS] test_closeLoan_withFeesButZeroTreasury() (gas: 280942)
[PASS] test_closeLoan_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 256803, ~: 256852)
Test result: ok. 12 passed; 0 failed; finished in 402.53ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinancerInterestRateTest
[PASS] test_refinance_interestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4298405, ~: 4301635)
Test result: ok. 1 passed; 0 failed; finished in 258.78ms

Running 2 tests for contracts/test/Refinancer.t.sol:RefinancerPaymentIntervalTest
[PASS] test_refinance_paymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4300584, ~: 4303609)
[PASS] test_refinance_paymentInterval_zeroAmount() (gas: 4257969)
Test result: ok. 2 passed; 0 failed; finished in 167.07ms

Running 2 tests for contracts/test/Refinancer.t.sol:RefinancerPaymentRemaining
[PASS] test_refinance_paymentRemaining(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4301056, ~: 4303390)
[PASS] test_refinance_paymentRemaining_zeroAmount() (gas: 4257905)
Test result: ok. 2 passed; 0 failed; finished in 184.30ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinancerGracePeriodTest
[PASS] test_refinance_gracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4295484, ~: 4301318)
Test result: ok. 1 passed; 0 failed; finished in 164.82ms

Running 2 tests for contracts/test/Refinancer.t.sol:RefinancePrincipalRequestedTest
[PASS] testFail_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4398538, ~: 4400449)
[PASS] test_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4412018, ~: 4413828)
Test result: ok. 2 passed; 0 failed; finished in 395.46ms

Running 3 tests for contracts/test/Refinancer.t.sol:RefinancerEndingPrincipalTest
[PASS] test_refinance_endingPrincipal_amortizedToInterestOnly(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4310941, ~: 4313050)
[PASS] test_refinance_endingPrincipal_failLargerThanPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4298292, ~: 4306692)
[PASS] test_refinance_endingPrincipal_interestOnlyToAmortized(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4299102, ~: 4292908)
Test result: ok. 3 passed; 0 failed; finished in 424.19ms

Running 3 tests for contracts/test/Refinancer.t.sol:RefinancerFeeTests
[PASS] test_refinance_earlyFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4298995, ~: 4302353)
[PASS] test_refinance_lateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4298848, ~: 4302260)
[PASS] test_refinance_lateInterestPremium(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 4318927, ~: 4322333)
Test result: ok. 3 passed; 0 failed; finished in 402.53ms

Running 11 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_RemoveCollateralTests
[PASS] testFail_removeCollateral_insufficientCollateralWithNoEncumbrances(uint256) (runs: 256, μ: 80770, ~: 87300)
[PASS] test_removeCollateral_cannotRemoveAnyAmountWithEncumbrances() (gas: 164973)
[PASS] test_removeCollateral_cannotRemoveFullAmountWithEncumbrances(uint256) (runs: 256, μ: 165763, ~: 165752)
[PASS] test_removeCollateral_cannotRemovePartialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 166571, ~: 166517)
[PASS] test_removeCollateral_fullAmountWithNoEncumbrances(uint256) (runs: 256, μ: 96511, ~: 96520)
[PASS] test_removeCollateral_fullAmount_drawableFundsGtPrincipal(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 153359, ~: 155583)
[PASS] test_removeCollateral_fullAmount_noPrincipal(uint256) (runs: 256, μ: 114020, ~: 114015)
[PASS] test_removeCollateral_partialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 203081, ~: 202934)
[PASS] test_removeCollateral_partialAmountWithNoEncumbrances(uint256,uint256) (runs: 256, μ: 124084, ~: 126704)
[PASS] test_removeCollateral_sameAssetAsFundingAsset(uint256) (runs: 256, μ: 159566, ~: 159554)
[PASS] test_removeCollateral_transferFailed() (gas: 182874)
Test result: ok. 11 passed; 0 failed; finished in 567.65ms
```

# `loan (v3.0.2)`

```
Running 2 tests for contracts/test/MapleLoan.t.sol:MapleLoanRoleTests
[PASS] testFail_transferBorrowerRole() (gas: 1274620)
[PASS] testFail_transferLenderRole() (gas: 102191)
Test result: ok. 2 passed; 0 failed; finished in 1.20ms

Running 2 tests for contracts/test/Payments.t.sol:EarlyRepaymentsTest
[PASS] testFail_payments_earlyRepayment_flatRate_case1() (gas: 597050)
[PASS] testFail_payments_earlyRepayment_flatRate_case2() (gas: 577049)
Test result: ok. 2 passed; 0 failed; finished in 2.23ms

Running 5 tests for contracts/test/Payments.t.sol:LateRepaymentsTest
[PASS] testFail_payments_dailyInterestAccrual() (gas: 616854)
[PASS] testFail_payments_lateRepayment_flatRateAndDefaultRate_case1() (gas: 617519)
[PASS] testFail_payments_lateRepayment_flatRateAndDefaultRate_case2() (gas: 617326)
[PASS] testFail_payments_lateRepayment_flatRate_case1() (gas: 597390)
[PASS] testFail_payments_lateRepayment_flatRate_case2() (gas: 597407)
Test result: ok. 5 passed; 0 failed; finished in 2.41ms

Running 2 tests for contracts/test/Payments.t.sol:FullyAmortizedPaymentsTest
[PASS] testFail_payments_fullyAmortized_case1() (gas: 557637)
[PASS] testFail_payments_fullyAmortized_case2() (gas: 557626)
Test result: ok. 2 passed; 0 failed; finished in 1.59ms

Running 2 tests for contracts/test/Payments.t.sol:InterestOnlyPaymentsTest
[PASS] testFail_payments_interestOnly_case1() (gas: 577526)
[PASS] testFail_payments_interestOnly_case2() (gas: 577537)
Test result: ok. 2 passed; 0 failed; finished in 1.58ms

Running 2 tests for contracts/test/Payments.t.sol:PartiallyAmortizedPaymentsTest
[PASS] testFail_payments_partiallyAmortized_case1() (gas: 577526)
[PASS] testFail_payments_partiallyAmortized_case2() (gas: 577537)
Test result: ok. 2 passed; 0 failed; finished in 3.57ms

Running 3 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetInstallmentTests
[PASS] test_getInstallment_edgeCases() (gas: 14432)
[PASS] test_getInstallment_genericFuzzing(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 11792, ~: 11973)
[PASS] test_getInstallment_withFixtures() (gas: 8485)
Test result: ok. 3 passed; 0 failed; finished in 10.73ms

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetInterestTests
[PASS] test_getInterest() (gas: 7724)
Test result: ok. 1 passed; 0 failed; finished in 334.88µs

Running 54 tests for contracts/test/MapleLoan.t.sol:MapleLoanTests
[PASS] testFail_acceptBorrower_acl() (gas: 30609)
[PASS] testFail_acceptNewTerms_acl() (gas: 1898493)
[PASS] testFail_acceptNewTerms_extraFunds() (gas: 4230016)
[PASS] testFail_acceptNewTerms_pullPattern() (gas: 2013300)
[PASS] testFail_acceptNewTerms_pushPattern() (gas: 2050571)
[PASS] testFail_closeLoan_pullPatternAsBorrower() (gas: 2137630)
[PASS] testFail_closeLoan_pullPatternAsNonBorrower() (gas: 1641706)
[PASS] testFail_closeLoan_pullPatternUsingDrawable() (gas: 2945635)
[PASS] testFail_closeLoan_pushPatternAsBorrower() (gas: 2104259)
[PASS] testFail_closeLoan_pushPatternAsNonBorrower() (gas: 1608488)
[PASS] testFail_closeLoan_pushPatternUsingDrawable() (gas: 2852760)
[PASS] testFail_drawdownFunds_acl() (gas: 1767649)
[PASS] testFail_drawdownFunds_pullPatternForCollateral() (gas: 3530883)
[PASS] testFail_drawdownFunds_pushPatternForCollateral() (gas: 3474203)
[PASS] testFail_drawdownFunds_withoutAdditionalCollateralRequired() (gas: 3260693)
[PASS] testFail_fundLoan_pullPattern() (gas: 4032698)
[PASS] testFail_fundLoan_pullPatternFundsRedirect() (gas: 1872207)
[PASS] testFail_fundLoan_pullPatternOverFund() (gas: 4038784)
[PASS] testFail_fundLoan_pushPattern() (gas: 3975984)
[PASS] testFail_fundLoan_pushPatternExtraFundsWhileActive() (gas: 4040294)
[PASS] testFail_fundLoan_pushPatternExtraFundsWhileNotActive() (gas: 3948346)
[PASS] testFail_fundLoan_pushPatternFundsRedirect() (gas: 1815521)
[PASS] testFail_fundLoan_pushPatternOverFund() (gas: 3982316)
[PASS] testFail_makePayment_pullPatternAsBorrower() (gas: 2166659)
[PASS] testFail_makePayment_pullPatternAsNonBorrower() (gas: 1670845)
[PASS] testFail_makePayment_pullPatternUsingDrawable() (gas: 2957149)
[PASS] testFail_makePayment_pushPatternAsBorrower() (gas: 2133362)
[PASS] testFail_makePayment_pushPatternAsNonBorrower() (gas: 1637527)
[PASS] testFail_makePayment_pushPatternUsingDrawable() (gas: 2864320)
[PASS] testFail_postCollateral_pullPattern() (gas: 1694687)
[PASS] testFail_postCollateral_pushPattern() (gas: 1619305)
[PASS] testFail_proposeNewTerms_acl() (gas: 148900)
[PASS] testFail_proposeNewTerms_invalidDeadline() (gas: 194898)
[PASS] testFail_rejectNewTerms_acl() (gas: 213555)
[PASS] testFail_removeCollateral_acl() (gas: 1733731)
[PASS] testFail_repossess_acl() (gas: 1691743)
[PASS] testFail_returnFunds_pullPattern() (gas: 1694611)
[PASS] testFail_returnFunds_pushPattern() (gas: 1619363)
[PASS] testFail_setBorrower_acl() (gas: 29626)
[PASS] testFail_skim_acl() (gas: 1638929)
[PASS] test_acceptLender_acl() (gas: 39195)
[PASS] test_claimFunds_acl() (gas: 1690073)
[PASS] test_excessCollateral_varyCollateral() (gas: 137646)
[PASS] test_excessCollateral_varyDrawableFunds() (gas: 126628)
[PASS] test_excessCollateral_varyPrincipal() (gas: 88705)
[PASS] test_getAdditionalCollateralRequiredFor_varyAmount() (gas: 119340)
[PASS] test_getAdditionalCollateralRequiredFor_varyCollateralRequired() (gas: 109384)
[PASS] test_getAdditionalCollateralRequiredFor_varyDrawableFunds() (gas: 111628)
[PASS] test_getAdditionalCollateralRequiredFor_varyPrincipal() (gas: 131954)
[PASS] test_migrate_acl() (gas: 62923)
[PASS] test_setImplementation_acl() (gas: 37009)
[PASS] test_setLender_acl() (gas: 55130)
[PASS] test_superFactory() (gas: 9094)
[PASS] test_upgrade_acl_globalsAdmin() (gas: 1933502)
Test result: ok. 54 passed; 0 failed; finished in 15.69ms

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetNextPaymentBreakdownTests
[PASS] test_getNextPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 231022, ~: 234058)
Test result: ok. 1 passed; 0 failed; finished in 26.34ms

Running 6 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetPaymentBreakdownTests
[PASS] test_getPaymentBreakdown_onePaymentFourPeriodsLate() (gas: 10261)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodBeforeDue() (gas: 9079)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodLate() (gas: 10283)
[PASS] test_getPaymentBreakdown_onePaymentOneSecondBeforeDue() (gas: 9133)
[PASS] test_getPaymentBreakdown_onePaymentThreePeriodsLate() (gas: 10216)
[PASS] test_getPaymentBreakdown_onePaymentTwoPeriodsLate() (gas: 10238)
Test result: ok. 6 passed; 0 failed; finished in 506.88µs

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetPeriodicInterestRateTests
[PASS] test_getPeriodicInterestRate() (gas: 7255)
Test result: ok. 1 passed; 0 failed; finished in 319.96µs

Running 2 tests for contracts/test/MapleLoanFactory.t.sol:MapleLoanFactoryTest
[PASS] testFail_createInstance_saltAndArgumentsCollision() (gas: 8937393460516741681)
[PASS] test_createInstance(bytes32) (runs: 256, μ: 542963, ~: 542963)
Test result: ok. 2 passed; 0 failed; finished in 58.37ms

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ProposeNewTermsTests
[PASS] test_proposeNewTerms(address,uint256,uint256,uint256,uint256) (runs: 256, μ: 36593, ~: 36593)
[PASS] test_proposeNewTerms_emptyArray(address,uint256) (runs: 256, μ: 9857, ~: 9857)
Test result: ok. 2 passed; 0 failed; finished in 21.22ms

Running 5 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_RejectNewTermsTests
[PASS] test_rejectNewTerms_commitmentMismatch_emptyCallsArray() (gas: 29621)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedCalls() (gas: 30406)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 30269)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 390791)
[PASS] test_rejectNewTerms_success() (gas: 26206)
Test result: ok. 5 passed; 0 failed; finished in 749.04µs

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceMiscellaneousTests
[PASS] testFail_refinance_invalidRefinancer() (gas: 2692775)
Test result: ok. 1 passed; 0 failed; finished in 771.50µs

Running 4 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_PostCollateralTests
[PASS] testFail_postCollateral_invalidCollateralAsset() (gas: 74556)
[PASS] test_postCollateral_multiple(uint256,uint256) (runs: 256, μ: 123394, ~: 118977)
[PASS] test_postCollateral_once(uint256) (runs: 256, μ: 80862, ~: 87159)
[PASS] test_postCollateral_withUnaccountedFundsAsset() (gas: 865305)
Test result: ok. 4 passed; 0 failed; finished in 49.31ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceCollateralRequiredTest
[PASS] testFail_refinance_collateralRequired(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2695741, ~: 2698306)
Test result: ok. 1 passed; 0 failed; finished in 69.86ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinancerInterestRateTest
[PASS] testFail_refinance_interestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2694451, ~: 2697677)
Test result: ok. 1 passed; 0 failed; finished in 78.99ms

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ReturnFundsTests
[PASS] test_returnFunds(uint256) (runs: 256, μ: 98671, ~: 101470)
[PASS] test_returnFunds_collateralAsset() (gas: 798951)
Test result: ok. 2 passed; 0 failed; finished in 16.76ms

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ScaledExponentTests
[PASS] test_scaledExponent_setOne() (gas: 22626)
[PASS] test_scaledExponent_setTwo() (gas: 36799)
Test result: ok. 2 passed; 0 failed; finished in 535.67µs

Running 3 tests for contracts/test/MapleLoanStories.t.sol:MapleLoanStoryTests
[PASS] testFail_story_fullyAmortized() (gas: 2067285)
[PASS] testFail_story_interestOnly() (gas: 2053111)
[PASS] testFail_story_redirectFundsToLender() (gas: 2018086)
Test result: ok. 3 passed; 0 failed; finished in 1.88ms

Running 10 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_AcceptNewTermsTests
[PASS] test_acceptNewTerms() (gas: 100154)
[PASS] test_acceptNewTerms_afterDeadline() (gas: 129788)
[PASS] test_acceptNewTerms_callFailed() (gas: 155592)
[PASS] test_acceptNewTerms_commitmentMismatch_emptyCallsArray() (gas: 107931)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedCalls() (gas: 107043)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 106838)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 474387)
[PASS] test_acceptNewTerms_fuzzEstablishmentFees(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125239, ~: 129001)
[PASS] test_acceptNewTerms_insufficientCollateral() (gas: 190800)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 114267)
Test result: ok. 10 passed; 0 failed; finished in 48.83ms

Running 3 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_ClaimFundsTests
[PASS] testFail_claimFunds_insufficientClaimableFunds(uint256,uint256) (runs: 256, μ: 82117, ~: 81940)
[PASS] test_claimFunds(uint256,uint256) (runs: 256, μ: 110660, ~: 113896)
[PASS] test_claimFunds_transferFail() (gas: 38630)
Test result: ok. 3 passed; 0 failed; finished in 20.90ms

Running 7 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_RepossessTests
[PASS] testFail_repossess_beforePaymentDue() (gas: 31036)
[PASS] testFail_repossess_onGracePeriod() (gas: 30999)
[PASS] testFail_repossess_onPaymentDue() (gas: 31002)
[PASS] testFail_repossess_withinGracePeriod() (gas: 31022)
[PASS] test_repossess() (gas: 127331)
[PASS] test_repossess_collateralTransferFailed() (gas: 230358)
[PASS] test_repossess_fundsTransferFailed() (gas: 265812)
Test result: ok. 7 passed; 0 failed; finished in 893.08µs

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetCollateralRequiredForTests
[PASS] test_getCollateralRequiredFor() (gas: 11303)
Test result: ok. 1 passed; 0 failed; finished in 341.88µs

Running 1 test for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetEarlyPaymentBreakdownTests
[PASS] test_getEarlyPaymentBreakdown(uint256,uint256,uint256) (runs: 256, μ: 396133, ~: 403328)
Test result: ok. 1 passed; 0 failed; finished in 20.69ms

Running 2 tests for contracts/test/Refinancer.t.sol:RefinanceDeadlineTests
[PASS] testFail_refinance_afterDeadline(uint256,uint256,uint256) (runs: 256, μ: 2654725, ~: 2654718)
[PASS] testFail_refinance_differentDeadline(uint256,uint256,uint256) (runs: 256, μ: 2654735, ~: 2654740)
Test result: ok. 2 passed; 0 failed; finished in 143.05ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceInterestAndFeeTests
[PASS] testFail_acceptNewTerms_makePayment_withFeesAndRefinanceInterest() (gas: 2998402)
Test result: ok. 1 passed; 0 failed; finished in 2.01ms

Running 2 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_CollateralMaintainedTests
[PASS] test_isCollateralMaintained(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 119472, ~: 124389)
[PASS] test_isCollateralMaintained_edgeCases() (gas: 164925)
Test result: ok. 2 passed; 0 failed; finished in 13.74ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinanceMultipleParameterTest
[PASS] testFail_refinance_multipleParameters(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2697709, ~: 2698202)
Test result: ok. 1 passed; 0 failed; finished in 101.71ms

Running 11 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_FundLoanTests
[PASS] testFail_fundLoan_claimImmediatelyAfterFullFunding(uint256,uint256) (runs: 256, μ: 227934, ~: 227909)
[PASS] testFail_fundLoan_doubleFund(uint256) (runs: 256, μ: 231032, ~: 231015)
[PASS] testFail_fundLoan_invalidFundsAsset() (gas: 188828)
[PASS] testFail_fundLoan_partialFunding(uint256) (runs: 256, μ: 204294, ~: 206150)
[PASS] testFail_fundLoan_withInvalidLender() (gas: 5742)
[PASS] testFail_fundLoan_withoutSendingAsset() (gas: 160106)
[PASS] test_fundLoan_fullFunding(uint256) (runs: 256, μ: 256675, ~: 256655)
[PASS] test_fundLoan_nextPaymentDueDateAlreadySet() (gas: 153105)
[PASS] test_fundLoan_noPaymentsRemaining() (gas: 62511)
[PASS] test_fundLoan_overFunding(uint256,uint256) (runs: 256, μ: 236520, ~: 236486)
[PASS] test_fundLoan_withUnaccountedCollateralAsset() (gas: 1003435)
Test result: ok. 11 passed; 0 failed; finished in 97.96ms

Running 4 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_InitializeTests
[PASS] test_initialize_invalidBorrower() (gas: 37979)
[PASS] test_initialize_invalidEndingPrincipal() (gas: 31626)
[PASS] test_initialize_invalidPrincipal() (gas: 31529)
[PASS] test_initialize_x() (gas: 381027)
Test result: ok. 4 passed; 0 failed; finished in 858.58µs

Running 2 tests for contracts/test/Refinancer.t.sol:RefinancerPaymentIntervalTest
[PASS] testFail_refinance_paymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2696324, ~: 2698792)
[PASS] testFail_refinance_paymentInterval_zeroAmount() (gas: 2652953)
Test result: ok. 2 passed; 0 failed; finished in 79.86ms

Running 2 tests for contracts/test/Refinancer.t.sol:RefinancerPaymentRemaining
[PASS] testFail_refinance_paymentRemaining(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2696639, ~: 2698306)
[PASS] testFail_refinance_paymentRemaining_zeroAmount() (gas: 2652975)
Test result: ok. 2 passed; 0 failed; finished in 89.35ms

Running 16 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_GetUnaccountedAmountTests
[PASS] test_getUnaccountedAmount_claimableFunds(uint256,uint256) (runs: 256, μ: 90087, ~: 89905)
[PASS] test_getUnaccountedAmount_collateral(uint256,uint256) (runs: 256, μ: 87952, ~: 88113)
[PASS] test_getUnaccountedAmount_collateralAsset() (gas: 74605)
[PASS] test_getUnaccountedAmount_complex(uint256,uint256,uint256,uint256) (runs: 256, μ: 842059, ~: 843476)
[PASS] test_getUnaccountedAmount_drawableFunds(uint256,uint256) (runs: 256, μ: 90201, ~: 90351)
[PASS] test_getUnaccountedAmount_drawableFundsAndClaimableFunds(uint256,uint256,uint256) (runs: 256, μ: 111979, ~: 112086)
[PASS] test_getUnaccountedAmount_drawableFundsAndClaimableFundsAndCollateral(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 191151, ~: 191060)
[PASS] test_getUnaccountedAmount_drawableFundsAndClaimableFundsAndCollateral_fundsAssetEqCollateralAsset(uint256,uint256,uint256,uint256) (runs: 256, μ: 139949, ~: 140013)
[PASS] test_getUnaccountedAmount_fundsAsset() (gas: 77199)
[PASS] test_getUnaccountedAmount_newFundsLtClaimableFunds(uint256) (runs: 256, μ: 101553, ~: 101519)
[PASS] test_getUnaccountedAmount_newFundsLtCollateral(uint256) (runs: 256, μ: 97111, ~: 97067)
[PASS] test_getUnaccountedAmount_newFundsLtDrawableFunds(uint256) (runs: 256, μ: 101606, ~: 101577)
[PASS] test_getUnaccountedAmount_randomToken() (gas: 131504)
[PASS] test_getUnaccountedAmount_withClaimableFunds(uint256,uint256) (runs: 256, μ: 85653, ~: 89166)
[PASS] test_getUnaccountedAmount_withCollateral(uint256,uint256) (runs: 256, μ: 82414, ~: 87018)
[PASS] test_getUnaccountedAmount_withDrawableFunds(uint256,uint256) (runs: 256, μ: 85720, ~: 89225)
Test result: ok. 16 passed; 0 failed; finished in 257.40ms

Running 12 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_CloseLoanTests
[PASS] test_closeLoan(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 252465, ~: 253906)
[PASS] test_closeLoan_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 296231, ~: 297093)
[PASS] test_closeLoan_latePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 242008, ~: 243390)
[PASS] test_closeLoan_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 254328, ~: 255558)
[PASS] test_closeLoan_withFees(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 315905, ~: 316022)
[PASS] test_closeLoan_withFeesButNoDelegateAtLender() (gas: 272920)
[PASS] test_closeLoan_withFeesButNoTreasuryAtGlobals() (gas: 274476)
[PASS] test_closeLoan_withFeesButZeroDelegate() (gas: 279461)
[PASS] test_closeLoan_withFeesButZeroGlobals() (gas: 276274)
[PASS] test_closeLoan_withFeesButZeroLender() (gas: 274754)
[PASS] test_closeLoan_withFeesButZeroTreasury() (gas: 280942)
[PASS] test_closeLoan_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 256810, ~: 256852)
Test result: ok. 12 passed; 0 failed; finished in 268.92ms

Running 3 tests for contracts/test/Refinancer.t.sol:RefinancerEndingPrincipalTest
[PASS] testFail_refinance_endingPrincipal_amortizedToInterestOnly(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2694751, ~: 2697686)
[PASS] testFail_refinance_endingPrincipal_failLargerThanPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2693870, ~: 2697233)
[PASS] testFail_refinance_endingPrincipal_interestOnlyToAmortized(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2695154, ~: 2697057)
Test result: ok. 3 passed; 0 failed; finished in 270.82ms

Running 1 test for contracts/test/Refinancer.t.sol:RefinancerGracePeriodTest
[PASS] testFail_refinance_gracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2693879, ~: 2697253)
Test result: ok. 1 passed; 0 failed; finished in 73.41ms

Running 2 tests for contracts/test/Refinancer.t.sol:RefinancePrincipalRequestedTest
[PASS] testFail_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2697066, ~: 2699118)
[PASS] testFail_refinance_increasePrincipalRequested_failWithNotEnoughPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2695282, ~: 2698370)
Test result: ok. 2 passed; 0 failed; finished in 195.59ms

Running 3 tests for contracts/test/Refinancer.t.sol:RefinancerFeeTests
[PASS] testFail_refinance_earlyFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2695978, ~: 2698372)
[PASS] testFail_refinance_lateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2695838, ~: 2698306)
[PASS] testFail_refinance_lateInterestPremium(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 2696101, ~: 2698328)
Test result: ok. 3 passed; 0 failed; finished in 94.07ms

Running 6 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_DrawdownFundsTests
[PASS] testFail_drawdownFunds_collateralNotMaintained(uint256,uint256,uint256) (runs: 256, μ: 200509, ~: 203368)
[PASS] testFail_drawdownFunds_insufficientDrawableFunds(uint256,uint256) (runs: 256, μ: 127642, ~: 127620)
[PASS] test_drawdownFunds_multipleDrawdowns(uint256,uint256,uint256) (runs: 256, μ: 178373, ~: 178343)
[PASS] test_drawdownFunds_postedCollateral(uint256,uint256,uint256) (runs: 256, μ: 202248, ~: 206907)
[PASS] test_drawdownFunds_transferFailed() (gas: 38736)
[PASS] test_drawdownFunds_withoutPostedCollateral(uint256,uint256) (runs: 256, μ: 160950, ~: 164568)
Test result: ok. 6 passed; 0 failed; finished in 166.83ms

Running 11 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_RemoveCollateralTests
[PASS] testFail_removeCollateral_insufficientCollateralWithNoEncumbrances(uint256) (runs: 256, μ: 82635, ~: 87300)
[PASS] test_removeCollateral_cannotRemoveAnyAmountWithEncumbrances() (gas: 164973)
[PASS] test_removeCollateral_cannotRemoveFullAmountWithEncumbrances(uint256) (runs: 256, μ: 165777, ~: 165752)
[PASS] test_removeCollateral_cannotRemovePartialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 166576, ~: 166517)
[PASS] test_removeCollateral_fullAmountWithNoEncumbrances(uint256) (runs: 256, μ: 96505, ~: 96520)
[PASS] test_removeCollateral_fullAmount_drawableFundsGtPrincipal(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 154752, ~: 155583)
[PASS] test_removeCollateral_fullAmount_noPrincipal(uint256) (runs: 256, μ: 114005, ~: 114015)
[PASS] test_removeCollateral_partialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 203070, ~: 202934)
[PASS] test_removeCollateral_partialAmountWithNoEncumbrances(uint256,uint256) (runs: 256, μ: 125000, ~: 126704)
[PASS] test_removeCollateral_sameAssetAsFundingAsset(uint256) (runs: 256, μ: 159566, ~: 159554)
[PASS] test_removeCollateral_transferFailed() (gas: 182874)
Test result: ok. 11 passed; 0 failed; finished in 318.55ms

Running 8 tests for contracts/test/MapleLoanInternals.t.sol:MapleLoanInternals_MakePaymentTests
[PASS] test_makePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 317639, ~: 323421)
[PASS] test_makePayment_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 337354, ~: 340588)
[PASS] test_makePayment_lastPaymentClearsLoan(uint256,uint256,uint256,uint256) (runs: 256, μ: 301488, ~: 303464)
[PASS] test_makePayment_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 317630, ~: 320868)
[PASS] test_makePayment_withFees(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 401016, ~: 401604)
[PASS] test_makePayment_withFeesButDelegateFailures() (gas: 393841)
[PASS] test_makePayment_withFeesButTreasuryFailures() (gas: 395545)
[PASS] test_makePayment_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 308187, ~: 309730)
Test result: ok. 8 passed; 0 failed; finished in 154.61ms
```

# `loan (v4.0.0)`

```
Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_SkimTests
[PASS] test_skimCollateralAsset() (gas: 76728)
[PASS] test_skimFundsAsset() (gas: 76831)
[PASS] test_skim_otherAsset() (gas: 791694)
Test result: ok. 3 passed; 0 failed; finished in 1.35ms

Running 3 tests for tests/MapleLoan.t.sol:MapleLoanRoleTests
[PASS] test_transferBorrowerRole() (gas: 178279)
[PASS] test_transferBorrowerRole_failIfInvalidBorrower() (gas: 77248)
[PASS] test_transferLenderRole() (gas: 307411)
Test result: ok. 3 passed; 0 failed; finished in 1.84ms

Running 2 tests for tests/MapleLoanFeeManager.t.sol:FeeManager_Getters
[PASS] test_getDelegateServiceFeesForPeriod() (gas: 614799)
[PASS] test_getPlatformServiceFeeForPeriod() (gas: 934222)
Test result: ok. 2 passed; 0 failed; finished in 2.30ms

Running 2 tests for tests/MapleLoanFeeManager.t.sol:PayServiceFeesTests
[PASS] test_payServiceFees() (gas: 231691)
[PASS] test_payServiceFees_zeroTreasury() (gas: 210742)
Test result: ok. 2 passed; 0 failed; finished in 2.40ms

Running 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_AcceptNewTermsTests
[PASS] test_acceptNewTerms() (gas: 148497)
[PASS] test_acceptNewTerms_afterDeadline() (gas: 69520)
[PASS] test_acceptNewTerms_callFailed() (gas: 102445)
[PASS] test_acceptNewTerms_commitmentMismatch_emptyCallsArray() (gas: 65696)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedCalls() (gas: 66559)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 66370)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 66239)
[PASS] test_acceptNewTerms_insufficientCollateral() (gas: 305661)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 66710)
Test result: ok. 9 passed; 0 failed; finished in 2.52ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:UpdateFeeTerms_SetterTests
[PASS] test_updateDelegateFeeTerms() (gas: 105747)
Test result: ok. 1 passed; 0 failed; finished in 1.44ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:PayClosingFeesTests
[PASS] test_payClosingServiceFees() (gas: 250236)
Test result: ok. 1 passed; 0 failed; finished in 2.21ms

Running 2 tests for tests/MapleLoanScenarios.t.sol:MapleLoanScenariosTests
[PASS] test_scenario_fullyAmortized() (gas: 5577064)
[PASS] test_scenario_interestOnly() (gas: 5578112)
Test result: ok. 2 passed; 0 failed; finished in 4.07ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:UpdatePlatformServiceFeeTests
[PASS] test_updatePlatformServiceFee() (gas: 1637921)
Test result: ok. 1 passed; 0 failed; finished in 2.18ms

Running 4 tests for tests/MapleLoanFeeManager.t.sol:PayOriginationFeesTests
[PASS] test_payOriginationFees() (gas: 330936)
[PASS] test_payOriginationFees_insufficientFunds_poolDelegate() (gas: 193717)
[PASS] test_payOriginationFees_insufficientFunds_treasury() (gas: 223738)
[PASS] test_payOriginationFees_zeroTreasury() (gas: 224760)
Test result: ok. 4 passed; 0 failed; finished in 2.74ms

Running 1 test for tests/Refinancer.t.sol:RefinancerInterestTests
[PASS] test_acceptNewTerms_makePayment_withRefinanceInterest() (gas: 5603544)
Test result: ok. 1 passed; 0 failed; finished in 1.80ms

Running 1 test for tests/Refinancer.t.sol:RefinancerMiscellaneousTests
[PASS] test_refinance_invalidRefinancer() (gas: 5369747)
Test result: ok. 1 passed; 0 failed; finished in 1.77ms

Running 2 tests for tests/Payments.t.sol:ClosingTests
[PASS] test_payments_closing_flatRate_case1() (gas: 1204393)
[PASS] test_payments_closing_flatRate_case2() (gas: 1092460)
Test result: ok. 2 passed; 0 failed; finished in 8.64ms

Running 63 tests for tests/MapleLoan.t.sol:MapleLoanTests
[PASS] test_acceptBorrower_acl() (gas: 51371)
[PASS] test_acceptBorrower_failWhenPaused() (gas: 101366)
[PASS] test_acceptLender_acl() (gas: 49672)
[PASS] test_acceptLender_failWhenPaused() (gas: 101455)
[PASS] test_acceptNewTerms() (gas: 1017691)
[PASS] test_acceptNewTerms_acl() (gas: 954152)
[PASS] test_closeLoan_failWhenPaused() (gas: 913150)
[PASS] test_closeLoan_pullPatternAsBorrower() (gas: 941919)
[PASS] test_closeLoan_pullPatternAsNonBorrower() (gas: 945029)
[PASS] test_closeLoan_pullPatternUsingDrawable() (gas: 942668)
[PASS] test_closeLoan_pushPatternAsBorrower() (gas: 960733)
[PASS] test_closeLoan_pushPatternAsNonBorrower() (gas: 961932)
[PASS] test_closeLoan_pushPatternUsingDrawable() (gas: 915579)
[PASS] test_drawdownFunds_acl() (gas: 901480)
[PASS] test_drawdownFunds_pullPatternForCollateral() (gas: 1772500)
[PASS] test_drawdownFunds_pushPatternForCollateral() (gas: 1755440)
[PASS] test_drawdownFunds_withoutAdditionalCollateralRequired() (gas: 1601280)
[PASS] test_drawdown_failWhenPaused() (gas: 1609117)
[PASS] test_excessCollateral_varyCollateral() (gas: 137569)
[PASS] test_excessCollateral_varyDrawableFunds() (gas: 126716)
[PASS] test_excessCollateral_varyPrincipal() (gas: 88738)
[PASS] test_fundLoan_pushPattern() (gas: 1068147)
[PASS] test_getAdditionalCollateralRequiredFor_varyAmount() (gas: 119571)
[PASS] test_getAdditionalCollateralRequiredFor_varyCollateralRequired() (gas: 109758)
[PASS] test_getAdditionalCollateralRequiredFor_varyDrawableFunds() (gas: 111837)
[PASS] test_getAdditionalCollateralRequiredFor_varyPrincipal() (gas: 132086)
[PASS] test_impairLoan() (gas: 65728)
[PASS] test_impairLoan_acl() (gas: 65148)
[PASS] test_impairLoan_lateLoan() (gas: 65865)
[PASS] test_makePayment_failWhenPaused() (gas: 960020)
[PASS] test_makePayment_pullPatternAsBorrower() (gas: 989890)
[PASS] test_makePayment_pullPatternAsNonBorrower() (gas: 992238)
[PASS] test_makePayment_pullPatternUsingDrawable() (gas: 1015074)
[PASS] test_makePayment_pushPatternAsBorrower() (gas: 993422)
[PASS] test_makePayment_pushPatternAsNonBorrower() (gas: 993723)
[PASS] test_makePayment_pushPatternUsingDrawable() (gas: 988091)
[PASS] test_migrate_acl() (gas: 66770)
[PASS] test_postCollateral_failWhenPaused() (gas: 839630)
[PASS] test_postCollateral_pullPattern() (gas: 868604)
[PASS] test_postCollateral_pushPattern() (gas: 825634)
[PASS] test_proposeNewTerms() (gas: 101868)
[PASS] test_proposeNewTerms_acl() (gas: 119281)
[PASS] test_proposeNewTerms_failWhenPaused() (gas: 118273)
[PASS] test_proposeNewTerms_invalidDeadline() (gas: 119261)
[PASS] test_rejectNewTerms_acl() (gas: 127184)
[PASS] test_rejectNewTerms_failWhenPaused() (gas: 107959)
[PASS] test_removeCollateral_acl() (gas: 860493)
[PASS] test_removeCollateral_failWhenPaused() (gas: 837756)
[PASS] test_removeLoanImpairment_acl() (gas: 48525)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 17519)
[PASS] test_removeLoanImpairment_pastDate() (gas: 38913)
[PASS] test_removeLoanImpairment_success() (gas: 47559)
[PASS] test_repossess_acl() (gas: 810272)
[PASS] test_returnFunds_failWhenPaused() (gas: 839807)
[PASS] test_returnFunds_pullPattern() (gas: 868713)
[PASS] test_returnFunds_pushPattern() (gas: 825711)
[PASS] test_setImplementation_acl() (gas: 87428)
[PASS] test_setPendingBorrower_acl() (gas: 92381)
[PASS] test_setPendingBorrower_failWhenPaused() (gas: 135752)
[PASS] test_setPendingLender_acl() (gas: 43965)
[PASS] test_skim_failWhenPaused() (gas: 806853)
[PASS] test_upgrade_acl() (gas: 4417140)
[PASS] test_upgrade_failWhenPaused() (gas: 4417749)
Test result: ok. 63 passed; 0 failed; finished in 16.10ms

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CollateralMaintainedTests
[PASS] test_isCollateralMaintained(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 117747, ~: 122366)
[PASS] test_isCollateralMaintained_edgeCases() (gas: 167648)
[PASS] test_isCollateralMaintained_roundUp() (gas: 81045)
Test result: ok. 3 passed; 0 failed; finished in 13.21ms

Running 2 tests for tests/Payments.t.sol:FullyAmortizedPaymentsTests
[PASS] test_payments_fullyAmortized_case1() (gas: 1390120)
[PASS] test_payments_fullyAmortized_case2() (gas: 1390068)
Test result: ok. 2 passed; 0 failed; finished in 5.51ms

Running 2 tests for tests/Payments.t.sol:InterestOnlyPaymentsTests
[PASS] test_payments_interestOnly_case1() (gas: 1405954)
[PASS] test_payments_interestOnly_case2() (gas: 1406004)
Test result: ok. 2 passed; 0 failed; finished in 6.70ms

Running 5 tests for tests/Payments.t.sol:LateRepaymentsTests
[PASS] test_payments_dailyInterestAccrual() (gas: 925336)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case1() (gas: 1406792)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case2() (gas: 1414137)
[PASS] test_payments_lateRepayment_flatRate_case1() (gas: 1403532)
[PASS] test_payments_lateRepayment_flatRate_case2() (gas: 1401485)
Test result: ok. 5 passed; 0 failed; finished in 15.38ms

Running 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ProposeNewTermsTests
[PASS] test_proposeNewTerms(address,uint256,uint256,uint256,uint256) (runs: 256, μ: 65851, ~: 65981)
[PASS] test_proposeNewTerms_emptyArray(address,uint256) (runs: 256, μ: 34870, ~: 34998)
Test result: ok. 2 passed; 0 failed; finished in 45.44ms

Running 5 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RejectNewTermsTests
[PASS] test_rejectNewTerms() (gas: 51945)
[PASS] test_rejectNewTerms_commitmentMismatch_emptyCallsArray() (gas: 63060)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedCalls() (gas: 63945)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 63867)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 462922)
Test result: ok. 5 passed; 0 failed; finished in 1.24ms

Running 2 tests for tests/Payments.t.sol:PartiallyAmortizedPaymentsTests
[PASS] test_payments_partiallyAmortized_case1() (gas: 1405970)
[PASS] test_payments_partiallyAmortized_case2() (gas: 1406005)
Test result: ok. 2 passed; 0 failed; finished in 5.61ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RepossessTests
[PASS] test_repossess() (gas: 129711)
[PASS] test_repossess_beforePaymentDue() (gas: 40997)
[PASS] test_repossess_collateralTransferFailed() (gas: 190197)
[PASS] test_repossess_fundsTransferFailed() (gas: 220753)
[PASS] test_repossess_onGracePeriod() (gas: 41016)
[PASS] test_repossess_onPaymentDue() (gas: 40875)
[PASS] test_repossess_withinGracePeriod() (gas: 40971)
Test result: ok. 7 passed; 0 failed; finished in 1.39ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetNextPaymentBreakdownTests
[PASS] test_getNextPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 496054, ~: 499168)
Test result: ok. 1 passed; 0 failed; finished in 39.28ms

Running 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPaymentBreakdownTests
[PASS] test_getPaymentBreakdown_onePaymentFourPeriodsLate() (gas: 27231)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodBeforeDue() (gas: 26123)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodLate() (gas: 27253)
[PASS] test_getPaymentBreakdown_onePaymentOneSecondBeforeDue() (gas: 26177)
[PASS] test_getPaymentBreakdown_onePaymentThreePeriodsLate() (gas: 27186)
[PASS] test_getPaymentBreakdown_onePaymentTwoPeriodsLate() (gas: 27208)
Test result: ok. 6 passed; 0 failed; finished in 891.42µs

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPeriodicInterestRateTests
[PASS] test_getPeriodicInterestRate() (gas: 7257)
Test result: ok. 1 passed; 0 failed; finished in 589.13µs

Running 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ReturnFundsTests
[PASS] test_returnFunds(uint256) (runs: 256, μ: 115398, ~: 118857)
[PASS] test_returnFundsCollateralAsset() (gas: 813835)
Test result: ok. 2 passed; 0 failed; finished in 29.17ms

Running 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ScaledExponentTests
[PASS] test_scaledExponent_setOne() (gas: 22590)
[PASS] test_scaledExponent_setTwo() (gas: 36769)
Test result: ok. 2 passed; 0 failed; finished in 879.46µs

Running 4 tests for tests/MapleLoanFactory.t.sol:MapleLoanFactoryTest
[PASS] testFail_createInstance_saltAndArgumentsCollision() (gas: 8937393460516743399)
[PASS] test_createInstance(bytes32) (runs: 256, μ: 454437, ~: 454437)
[PASS] test_createInstance_invalidCollateralAsset() (gas: 625846)
[PASS] test_createInstance_invalidPoolAsset() (gas: 622559)
Test result: ok. 4 passed; 0 failed; finished in 66.51ms

Running 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_DrawdownFundsTests
[PASS] test_drawdownFunds_collateralNotMaintained(uint256,uint256,uint256) (runs: 256, μ: 253458, ~: 262251)
[PASS] test_drawdownFunds_insufficientDrawableFunds(uint256,uint256) (runs: 256, μ: 151916, ~: 151964)
[PASS] test_drawdownFunds_multipleDrawdowns(uint256,uint256,uint256) (runs: 256, μ: 259453, ~: 259358)
[PASS] test_drawdownFunds_postedCollateral(uint256,uint256,uint256) (runs: 256, μ: 278101, ~: 282973)
[PASS] test_drawdownFunds_transferFailed() (gas: 52167)
[PASS] test_drawdownFunds_withoutPostedCollateral(uint256,uint256) (runs: 256, μ: 182888, ~: 189313)
Test result: ok. 6 passed; 0 failed; finished in 145.75ms

Running 12 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetUnaccountedAmountTests
[PASS] test_getUnaccountedAmount_collateral(uint256,uint256) (runs: 256, μ: 87034, ~: 87134)
[PASS] test_getUnaccountedAmount_collateralAsset() (gas: 74507)
[PASS] test_getUnaccountedAmount_complex(uint256,uint256,uint256) (runs: 256, μ: 816946, ~: 818549)
[PASS] test_getUnaccountedAmount_drawableFunds(uint256,uint256) (runs: 256, μ: 87076, ~: 87144)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral(uint256,uint256,uint256,uint256) (runs: 256, μ: 165272, ~: 165144)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral_fundsAssetEqCollateralAsset(uint256,uint256,uint256) (runs: 256, μ: 114668, ~: 114611)
[PASS] test_getUnaccountedAmount_fundsAsset() (gas: 74497)
[PASS] test_getUnaccountedAmount_newFundsLtCollateral(uint256) (runs: 256, μ: 102067, ~: 102057)
[PASS] test_getUnaccountedAmount_newFundsLtDrawableFunds(uint256) (runs: 256, μ: 102121, ~: 102110)
[PASS] test_getUnaccountedAmount_randomToken() (gas: 108068)
[PASS] test_getUnaccountedAmount_withCollateral(uint256,uint256) (runs: 256, μ: 81529, ~: 86509)
[PASS] test_getUnaccountedAmount_withDrawableFunds(uint256,uint256) (runs: 256, μ: 82504, ~: 86499)
Test result: ok. 12 passed; 0 failed; finished in 143.82ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_InitializeTests
[PASS] test_initialize() (gas: 5224365)
[PASS] test_initialize_invalidBorrower() (gas: 837569)
[PASS] test_initialize_invalidEndingPrincipal() (gas: 802790)
[PASS] test_initialize_invalidPaymentInterval() (gas: 809264)
[PASS] test_initialize_invalidPaymentsRemaining() (gas: 809233)
[PASS] test_initialize_invalidPrincipal() (gas: 802650)
[PASS] test_initialize_zeroBorrower() (gas: 811961)
Test result: ok. 7 passed; 0 failed; finished in 3.45ms

Running 10 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_FundLoanTests
[PASS] test_fundLoan_approveFail() (gas: 255615)
[PASS] test_fundLoan_doubleFund(uint256) (runs: 256, μ: 297962, ~: 297853)
[PASS] test_fundLoan_fullFunding(uint256) (runs: 256, μ: 313217, ~: 313101)
[PASS] test_fundLoan_invalidFundsAsset() (gas: 951787)
[PASS] test_fundLoan_nextPaymentDueDateAlreadySet() (gas: 200951)
[PASS] test_fundLoan_noPaymentsRemaining() (gas: 110641)
[PASS] test_fundLoan_partialFunding(uint256) (runs: 256, μ: 242624, ~: 245306)
[PASS] test_fundLoan_withInvalidLender() (gas: 13171)
[PASS] test_fundLoan_withUnaccountedCollateralAsset() (gas: 1061301)
[PASS] test_fundLoan_withoutSendingAsset() (gas: 199666)
Test result: ok. 10 passed; 0 failed; finished in 85.66ms

Running 1 test for tests/Refinancer.t.sol:RefinancerCollateralRequiredTests
[PASS] test_refinance_collateralRequired(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5581220, ~: 5576215)
Test result: ok. 1 passed; 0 failed; finished in 292.97ms

Running 2 tests for tests/Refinancer.t.sol:RefinancerPaymentIntervalTests
[PASS] test_refinance_paymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5553585, ~: 5558379)
[PASS] test_refinance_paymentInterval_zeroAmount() (gas: 5474939)
Test result: ok. 2 passed; 0 failed; finished in 263.17ms

Running 1 test for tests/Refinancer.t.sol:RefinancerMultipleParameterTests
[PASS] test_refinance_multipleParameters(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5599831, ~: 5602466)
Test result: ok. 1 passed; 0 failed; finished in 335.35ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetClosingPaymentBreakdownTests
[PASS] test_getClosingPaymentBreakdown(uint256,uint256,uint256) (runs: 256, μ: 5250535, ~: 5250519)
Test result: ok. 1 passed; 0 failed; finished in 185.16ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetCollateralRequiredForTests
[PASS] test_getCollateralRequiredFor() (gas: 12282)
Test result: ok. 1 passed; 0 failed; finished in 631.21µs

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInstallmentTests
[PASS] test_getInstallment_edgeCases() (gas: 14380)
[PASS] test_getInstallment_genericFuzzing(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 10402, ~: 10531)
[PASS] test_getInstallment_withFixtures() (gas: 8459)
Test result: ok. 3 passed; 0 failed; finished in 10.59ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInterestTests
[PASS] test_getInterest() (gas: 7656)
Test result: ok. 1 passed; 0 failed; finished in 593.75µs

Running 2 tests for tests/Refinancer.t.sol:RefinancerDeadlineTests
[PASS] test_refinance_afterDeadline(uint256,uint256,uint256) (runs: 256, μ: 5487607, ~: 5481153)
[PASS] test_refinance_differentDeadline(uint256,uint256,uint256) (runs: 256, μ: 5477503, ~: 5477504)
Test result: ok. 2 passed; 0 failed; finished in 491.34ms

Running 1 test for tests/Refinancer.t.sol:RefinancerGracePeriodTests
[PASS] test_refinance_gracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5549227, ~: 5555882)
Test result: ok. 1 passed; 0 failed; finished in 248.00ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_MakePaymentTests
[PASS] test_makePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 347411, ~: 352264)
[PASS] test_makePayment_amountSmallerThanFees() (gas: 448417)
[PASS] test_makePayment_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 365966, ~: 369358)
[PASS] test_makePayment_lastPaymentClearsLoan(uint256,uint256,uint256,uint256) (runs: 256, μ: 332692, ~: 335173)
[PASS] test_makePayment_noAmount() (gas: 441059)
[PASS] test_makePayment_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 350653, ~: 356288)
[PASS] test_makePayment_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 335276, ~: 335763)
Test result: ok. 7 passed; 0 failed; finished in 334.35ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CloseLoanTests
[PASS] test_closeLoan(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 274255, ~: 275688)
[PASS] test_closeLoan_amountSmallerThanFees() (gas: 434387)
[PASS] test_closeLoan_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 333562, ~: 334096)
[PASS] test_closeLoan_latePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 282565, ~: 283746)
[PASS] test_closeLoan_noAmount() (gas: 428528)
[PASS] test_closeLoan_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 280390, ~: 282678)
[PASS] test_closeLoan_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 276625, ~: 276655)
Test result: ok. 7 passed; 0 failed; finished in 600.47ms

Running 4 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_PostCollateralTests
[PASS] test_postCollateral_invalidCollateralAsset() (gas: 790610)
[PASS] test_postCollateral_multiple(uint256,uint256) (runs: 256, μ: 145629, ~: 144780)
[PASS] test_postCollateral_once(uint256) (runs: 256, μ: 95688, ~: 100804)
[PASS] test_postCollateral_withUnaccountedFundsAsset() (gas: 877229)
Test result: ok. 4 passed; 0 failed; finished in 61.07ms

Running 2 tests for tests/Refinancer.t.sol:RefinancerPaymentsRemainingTests
[PASS] test_refinance_paymentRemaining(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5554755, ~: 5558270)
[PASS] test_refinance_paymentRemaining_zeroAmount() (gas: 5474875)
Test result: ok. 2 passed; 0 failed; finished in 306.04ms

Running 1 test for tests/Refinancer.t.sol:RefinancerInterestRateTests
[PASS] test_refinance_interestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5552516, ~: 5556641)
Test result: ok. 1 passed; 0 failed; finished in 227.67ms

Running 2 tests for tests/Refinancer.t.sol:RefinancerPrincipalRequestedTests
[PASS] test_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5613414, ~: 5616202)
[PASS] test_refinance_increasePrincipalRequestedWithInsufficientFunds(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5553549, ~: 5556092)
Test result: ok. 2 passed; 0 failed; finished in 409.59ms

Running 3 tests for tests/Refinancer.t.sol:RefinancerFeeTests
[PASS] test_refinance_closingRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5551646, ~: 5556767)
[PASS] test_refinance_lateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5553260, ~: 5556847)
[PASS] test_refinance_lateInterestPremium(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5572039, ~: 5576679)
Test result: ok. 3 passed; 0 failed; finished in 901.10ms

Running 7 tests for tests/Refinancer.t.sol:RefinancingFeesTerms
[PASS] testFuzz_refinance_payOriginationFees(uint256,uint256) (runs: 256, μ: 6511951, ~: 6512009)
[PASS] testFuzz_refinance_pdOriginationFeeTransferFail(uint256) (runs: 256, μ: 6435595, ~: 6437427)
[PASS] testFuzz_refinance_treasuryOriginationFeeTransferFail(uint256,uint256) (runs: 256, μ: 6447583, ~: 6447639)
[PASS] testFuzz_refinance_updateFeeTerms(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 6457577, ~: 6462831)
[PASS] testFuzz_refinance_updatesPlatformServiceFees(uint256) (runs: 256, μ: 6430452, ~: 6430323)
[PASS] test_refinance_updateRefinanceServiceFees() (gas: 6511532)
[PASS] test_refinance_updateRefinanceServiceFeesOnDoubleRefinance() (gas: 6577798)
Test result: ok. 7 passed; 0 failed; finished in 445.19ms

Running 3 tests for tests/Refinancer.t.sol:RefinancerEndingPrincipalTests
[PASS] test_refinance_endingPrincipal_amortizedToInterestOnly(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5569904, ~: 5572801)
[PASS] test_refinance_endingPrincipal_failLargerThanPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5536633, ~: 5545149)
[PASS] test_refinance_endingPrincipal_interestOnlyToAmortized(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5555546, ~: 5552205)
Test result: ok. 3 passed; 0 failed; finished in 736.43ms

Running 11 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RemoveCollateralTests
[PASS] test_removeCollateral_cannotRemoveAnyAmountWithEncumbrances() (gas: 191190)
[PASS] test_removeCollateral_cannotRemoveFullAmountWithEncumbrances(uint256) (runs: 256, μ: 151645, ~: 151633)
[PASS] test_removeCollateral_cannotRemovePartialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 191944, ~: 192019)
[PASS] test_removeCollateral_fullAmountWithNoEncumbrances(uint256) (runs: 256, μ: 117689, ~: 117698)
[PASS] test_removeCollateral_fullAmount_drawableFundsGtPrincipal(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 178188, ~: 180242)
[PASS] test_removeCollateral_fullAmount_noPrincipal(uint256) (runs: 256, μ: 135153, ~: 135164)
[PASS] test_removeCollateral_insufficientCollateralWithNoEncumbrances(uint256) (runs: 256, μ: 110718, ~: 114672)
[PASS] test_removeCollateral_partialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 231347, ~: 234609)
[PASS] test_removeCollateral_partialAmountWithNoEncumbrances(uint256,uint256) (runs: 256, μ: 150903, ~: 153039)
[PASS] test_removeCollateral_sameAssetAsFundingAsset(uint256) (runs: 256, μ: 137749, ~: 137745)
[PASS] test_removeCollateral_transferFailed() (gas: 191289)
Test result: ok. 11 passed; 0 failed; finished in 858.08ms
```

# `migration-helpers (v1.0.0)`

```
Running 6 tests for tests/MigrationHelper.t.sol:AdminTests
[PASS] test_acceptOwner() (gas: 43281)
[PASS] test_acceptOwner_notPendingAdmin() (gas: 47532)
[PASS] test_setGlobals() (gas: 49009)
[PASS] test_setGlobals_notAdmin() (gas: 18095)
[PASS] test_setPendingAdmin() (gas: 49030)
[PASS] test_setPendingAdmin_notAdmin() (gas: 18106)
Test result: ok. 6 passed; 0 failed; finished in 808.33µs

Running 6 tests for tests/MigrationHelper.t.sol:AddLoansToLoanManagerTests
[PASS] test_addLoansToLoanManager() (gas: 78454)
[PASS] test_addLoansToLoanManager_claimableFunds() (gas: 119605)
[PASS] test_addLoansToLoanManager_invalidLoanManager() (gas: 108286)
[PASS] test_addLoansToLoanManager_invalidPrincipal() (gas: 128603)
[PASS] test_addLoansToLoanManager_notAdmin() (gas: 93146)
[PASS] test_addLoansToLoanManager_protocolPaused() (gas: 96754)
Test result: ok. 6 passed; 0 failed; finished in 1.76ms

Running 5 tests for tests/MigrationHelper.t.sol:AirdropTokensTests
[PASS] test_airdropTokens_aboveAllowedDiff() (gas: 1298469)
[PASS] test_airdropTokens_aboveAllowedDiff_negative() (gas: 1298415)
[PASS] test_airdropTokens_exact() (gas: 467548)
[PASS] test_airdropTokens_notAdmin() (gas: 113670)
[PASS] test_airdropTokens_remaining() (gas: 468701)
Test result: ok. 5 passed; 0 failed; finished in 3.28ms

Running 14 tests for tests/MigrationHelper.t.sol:SetPendingLendersTests
[PASS] test_setPendingLenders() (gas: 185196)
[PASS] test_setPendingLenders_invalidDebtLockerPool() (gas: 392420)
[PASS] test_setPendingLenders_invalidLMFactory() (gas: 240750)
[PASS] test_setPendingLenders_invalidLoan() (gas: 401119)
[PASS] test_setPendingLenders_invalidLoanFactory() (gas: 251721)
[PASS] test_setPendingLenders_invalidLoanManager() (gas: 236923)
[PASS] test_setPendingLenders_invalidPMFactory() (gas: 221067)
[PASS] test_setPendingLenders_invalidPoolManager() (gas: 215314)
[PASS] test_setPendingLenders_notActive() (gas: 245342)
[PASS] test_setPendingLenders_notAdmin() (gas: 195909)
[PASS] test_setPendingLenders_notOwnedPM() (gas: 250175)
[PASS] test_setPendingLenders_notPoolDelegate() (gas: 250135)
[PASS] test_setPendingLenders_protocolPaused() (gas: 203772)
[PASS] test_setPendingLenders_rollback() (gas: 155909)
Test result: ok. 14 passed; 0 failed; finished in 3.24ms
```

# `pool-v2 (v1.0.0)`

```
Running 1 test for tests/LoanManager.t.sol:DistributeClaimedFunds
[PASS] test_distributeClaimedFunds_mapleTreasuryNotSet() (gas: 1067068)
Test result: ok. 1 passed; 0 failed; finished in 2.01ms

Running 2 tests for tests/LoanManager.t.sol:SetOwnershipToTests
[PASS] testFail_setOwnershipTo_notLoanTransferAdmin() (gas: 23441)
[PASS] test_setOwnershipTo_success() (gas: 41855)
Test result: ok. 2 passed; 0 failed; finished in 2.06ms

Running 1 test for tests/LoanManager.t.sol:DisburseLiquidationFundsTests
[PASS] test_disburseLiquidationFunds_mapleTreasuryNotSet() (gas: 938758)
Test result: ok. 1 passed; 0 failed; finished in 2.15ms

Running 5 tests for tests/LoanManager.t.sol:UpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 36630)
[PASS] test_upgrade_notScheduled() (gas: 41082)
[PASS] test_upgrade_success() (gas: 95569)
[PASS] test_upgrade_successWithGovernor() (gas: 70549)
[PASS] test_upgrade_upgradeFailed() (gas: 90194)
Test result: ok. 5 passed; 0 failed; finished in 2.50ms

Running 4 tests for tests/PoolManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 25388)
[PASS] test_migrate_invalidPoolDelegateCover() (gas: 30459)
[PASS] test_migrate_notFactory() (gas: 20196)
[PASS] test_migrate_success() (gas: 33114)
Test result: ok. 4 passed; 0 failed; finished in 3.10ms

Running 1 test for tests/LoanManager.t.sol:ClaimDomainStartGtDomainEnd
[PASS] test_claim_domainStart_gt_domainEnd() (gas: 601213)
Test result: ok. 1 passed; 0 failed; finished in 2.86ms

Running 5 tests for tests/PoolManager.t.sol:SetMinRatio_SetterTests
[PASS] test_setMinRatio_invalidLoanManager() (gas: 82767)
[PASS] test_setMinRatio_notAuthorized() (gas: 39375)
[PASS] test_setMinRatio_protocolPaused() (gas: 56753)
[PASS] test_setMinRatio_success_asGovernor() (gas: 61138)
[PASS] test_setMinRatio_success_asPoolDelegate() (gas: 55636)
Test result: ok. 5 passed; 0 failed; finished in 3.47ms

Running 2 tests for tests/LoanManager.t.sol:SetterTests
[PASS] test_getAccruedInterest() (gas: 35482)
[PASS] test_getAssetsUnderManagement() (gas: 40749)
Test result: ok. 2 passed; 0 failed; finished in 1.82ms

Running 4 tests for tests/LoanManagerFactory.t.sol:LoanManagerFactoryBase
[PASS] testFail_createInstance_collision() (gas: 8937393460516736725)
[PASS] testFail_createInstance_notPool() (gas: 190113)
[PASS] test_createInstance_notPoolDeployer() (gas: 245493)
[PASS] test_createInstance_success() (gas: 317062)
Test result: ok. 4 passed; 0 failed; finished in 1.61ms

Running 2 tests for tests/LoanManager.t.sol:FinishCollateralLiquidationTests
[PASS] test_finishCollateralLiquidation_notManager() (gas: 124937)
[PASS] test_finishCollateralLiquidation_success_withCollateral() (gas: 349416)
Test result: ok. 2 passed; 0 failed; finished in 2.33ms

Running 1 test for tests/LoanManager.t.sol:ClaimTests
[PASS] test_claim_notManager() (gas: 330192)
Test result: ok. 1 passed; 0 failed; finished in 1.99ms

Running 6 tests for tests/LoanManager.t.sol:TriggerDefaultTests
[PASS] test_triggerDefault_notManager() (gas: 97520)
[PASS] test_triggerDefault_success_noCollateral_impaired() (gas: 213836)
[PASS] test_triggerDefault_success_noCollateral_notImpaired() (gas: 137879)
[PASS] test_triggerDefault_success_withCollateralAssetEqualToFundsAsset() (gas: 263100)
[PASS] test_triggerDefault_success_withCollateral_impaired() (gas: 385929)
[PASS] test_triggerDefault_success_withCollateral_notImpaired() (gas: 356641)
Test result: ok. 6 passed; 0 failed; finished in 3.62ms

Running 3 tests for tests/PoolManager.t.sol:SetOpenToPublic_SetterTests
[PASS] test_setOpenToPublic_notPoolDelegate() (gas: 30658)
[PASS] test_setOpenToPublic_protocolPaused() (gas: 54208)
[PASS] test_setOpenToPublic_success() (gas: 41557)
Test result: ok. 3 passed; 0 failed; finished in 2.87ms

Running 5 tests for tests/PoolManager.t.sol:ProcessRedeemTests
[PASS] test_processRedeem_noApproval() (gas: 131314)
[PASS] test_processRedeem_notWithdrawalManager() (gas: 36223)
[PASS] test_processRedeem_protocolPaused() (gas: 57073)
[PASS] test_processRedeem_success() (gas: 42439)
[PASS] test_processRedeem_success_notSender() (gas: 163742)
Test result: ok. 5 passed; 0 failed; finished in 3.11ms

Running 4 tests for tests/PoolManager.t.sol:AcceptPendingPoolDelegate_SetterTests
[PASS] test_acceptPendingPoolDelegate_globalsTransferFails() (gas: 62705)
[PASS] test_acceptPendingPoolDelegate_notPendingPoolDelegate() (gas: 33296)
[PASS] test_acceptPendingPoolDelegate_protocolPaused() (gas: 54212)
[PASS] test_acceptPendingPoolDelegate_success() (gas: 54031)
Test result: ok. 4 passed; 0 failed; finished in 3.05ms

Running 6 tests for tests/LoanManager.t.sol:SingleLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_amortized() (gas: 393130)
[PASS] test_claim_earlyPayment_interestOnly() (gas: 385871)
[PASS] test_claim_latePayment_amortized() (gas: 413951)
[PASS] test_claim_latePayment_interestOnly() (gas: 406690)
[PASS] test_claim_onTimePayment_amortized() (gas: 390385)
[PASS] test_claim_onTimePayment_interestOnly() (gas: 383192)
Test result: ok. 6 passed; 0 failed; finished in 4.02ms

Running 3 tests for tests/PoolManager.t.sol:SetPendingPoolDelegate_SetterTests
[PASS] test_setPendingPoolDelegate_notPoolDelegate() (gas: 35531)
[PASS] test_setPendingPoolDelegate_protocolPaused() (gas: 56319)
[PASS] test_setPendingPoolDelegate_success() (gas: 61946)
Test result: ok. 3 passed; 0 failed; finished in 2.88ms

Running 2 tests for tests/LoanManager.t.sol:TakeOwnershipTests
[PASS] testFail_takeOwnership_notLoanTransferAdmin() (gas: 19934)
[PASS] test_takeOwnership_success() (gas: 37156)
Test result: ok. 2 passed; 0 failed; finished in 1.98ms

Running 3 tests for tests/LoanManager.t.sol:TwoLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 620947)
[PASS] test_claim_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 642386)
[PASS] test_claim_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 618145)
Test result: ok. 3 passed; 0 failed; finished in 4.21ms

Running 2 tests for tests/LoanManager.t.sol:FundLoanTests
[PASS] test_fund() (gas: 358286)
[PASS] test_fund_failIfNotPoolManager() (gas: 123983)
Test result: ok. 2 passed; 0 failed; finished in 11.55ms

Running 4 tests for tests/PoolManager.t.sol:AddLoanManager_SetterTests
[PASS] test_addLoanManager() (gas: 113264)
[PASS] test_addLoanManager_duplicateLM() (gas: 107217)
[PASS] test_addLoanManager_notPD() (gas: 35520)
[PASS] test_addLoanManager_protocolPaused() (gas: 56398)
Test result: ok. 4 passed; 0 failed; finished in 4.14ms

Running 6 tests for tests/LoanManager.t.sol:UintCastingTests
[PASS] test_castUint112() (gas: 22112)
[PASS] test_castUint120() (gas: 21976)
[PASS] test_castUint128() (gas: 21959)
[PASS] test_castUint24() (gas: 21906)
[PASS] test_castUint48() (gas: 21978)
[PASS] test_castUint96() (gas: 22052)
Test result: ok. 6 passed; 0 failed; finished in 1.78ms

Running 2 tests for tests/LoanManager.t.sol:ThreeLoanPastDomainEndClaimTests
[PASS] test_claim_loan1NotPaid_loan2NotPaid_loan3PaidLate() (gas: 377666)
[PASS] test_claim_loan3_loan1NotPaid_loan2NotPaid() (gas: 376189)
Test result: ok. 2 passed; 0 failed; finished in 2.70ms

Running 2 tests for tests/LoanManager.t.sol:UpdateAccountingFailureTests
[PASS] test_updateAccounting_notGovernor() (gas: 101411)
[PASS] test_updateAccounting_notPoolDelegate() (gas: 97263)
Test result: ok. 2 passed; 0 failed; finished in 1.69ms

Running 4 tests for tests/LoanManager.t.sol:ImpairLoanTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 172305)
[PASS] test_impairLoan_notManager() (gas: 177774)
[PASS] test_impairLoan_success() (gas: 232313)
[PASS] test_impairLoan_success_byGovernor() (gas: 213141)
Test result: ok. 4 passed; 0 failed; finished in 2.62ms

Running 4 tests for tests/LoanManager.t.sol:UpdateAccountingTests
[PASS] test_updateAccounting_afterDomainEnd() (gas: 112192)
[PASS] test_updateAccounting_afterTwoDomainEnds() (gas: 105379)
[PASS] test_updateAccounting_beforeDomainEnd() (gas: 95975)
[PASS] test_updateAccounting_failIfPaused() (gas: 54095)
Test result: ok. 4 passed; 0 failed; finished in 2.55ms

Running 13 tests for tests/LoanManager.t.sol:LoanManagerSortingTests
[PASS] test_addPaymentToList_ascendingPair() (gas: 98530)
[PASS] test_addPaymentToList_descendingPair() (gas: 98506)
[PASS] test_addPaymentToList_single() (gas: 63717)
[PASS] test_addPaymentToList_synchronizedPair() (gas: 98540)
[PASS] test_addPaymentToList_toHead() (gas: 135588)
[PASS] test_addPaymentToList_toMiddle() (gas: 136117)
[PASS] test_addPaymentToList_toTail() (gas: 136112)
[PASS] test_removePaymentFromList_earliestDueDate() (gas: 115594)
[PASS] test_removePaymentFromList_invalidPaymentId() (gas: 76948)
[PASS] test_removePaymentFromList_latestDueDate() (gas: 115383)
[PASS] test_removePaymentFromList_medianDueDate() (gas: 115677)
[PASS] test_removePaymentFromList_pair() (gas: 83350)
[PASS] test_removePaymentFromList_single() (gas: 52628)
Test result: ok. 13 passed; 0 failed; finished in 3.23ms

Running 3 tests for tests/PoolManager.t.sol:SetWithdrawalManager_SetterTests
[PASS] test_setWithdrawalManager() (gas: 44487)
[PASS] test_setWithdrawalManager_notPD() (gas: 35571)
[PASS] test_setWithdrawalManager_protocolPaused() (gas: 56406)
Test result: ok. 3 passed; 0 failed; finished in 8.20ms

Running 5 tests for tests/PoolManager.t.sol:UpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 31165)
[PASS] test_upgrade_notScheduled() (gas: 34617)
[PASS] test_upgrade_success() (gas: 92759)
[PASS] test_upgrade_successWithGovernor() (gas: 68748)
[PASS] test_upgrade_upgradeFailed() (gas: 83612)
Test result: ok. 5 passed; 0 failed; finished in 3.67ms

Running 32 tests for tests/PoolManager.t.sol:CanCallTests
[PASS] test_canCall_depositWithPermit_lenderNotAllowed() (gas: 114034)
[PASS] test_canCall_depositWithPermit_liquidityCapExceeded() (gas: 86220)
[PASS] test_canCall_depositWithPermit_notActive() (gas: 38878)
[PASS] test_canCall_depositWithPermit_notOpenToPublic() (gas: 95720)
[PASS] test_canCall_deposit_lenderNotAllowed() (gas: 112811)
[PASS] test_canCall_deposit_liquidityCapExceeded() (gas: 85606)
[PASS] test_canCall_deposit_notActive() (gas: 38279)
[PASS] test_canCall_deposit_notOpenToPublic() (gas: 94518)
[PASS] test_canCall_invalidFunctionId() (gas: 71504)
[PASS] test_canCall_mintWithPermit_lenderNotAllowed() (gas: 129568)
[PASS] test_canCall_mintWithPermit_liquidityCapExceeded() (gas: 97282)
[PASS] test_canCall_mintWithPermit_notActive() (gas: 60439)
[PASS] test_canCall_mintWithPermit_notOpenToPublic() (gas: 111252)
[PASS] test_canCall_mint_lenderNotAllowed() (gas: 128082)
[PASS] test_canCall_mint_liquidityCapExceeded() (gas: 96470)
[PASS] test_canCall_mint_notActive() (gas: 59665)
[PASS] test_canCall_mint_notOpenToPublic() (gas: 109853)
[PASS] test_canCall_protocolPaused_redeem() (gas: 49677)
[PASS] test_canCall_protocolPaused_removeShares() (gas: 49676)
[PASS] test_canCall_protocolPaused_requestRedeem() (gas: 49700)
[PASS] test_canCall_protocolPaused_requestWithdraw() (gas: 49677)
[PASS] test_canCall_protocolPaused_transfer() (gas: 49633)
[PASS] test_canCall_protocolPaused_withdraw() (gas: 49699)
[PASS] test_canCall_redeem() (gas: 28572)
[PASS] test_canCall_removeShares() (gas: 28342)
[PASS] test_canCall_requestRedeem() (gas: 28324)
[PASS] test_canCall_requestWithdraw() (gas: 28342)
[PASS] test_canCall_transferFrom_notOpenToPublic() (gas: 82758)
[PASS] test_canCall_transferFrom_recipientNotAllowed() (gas: 100985)
[PASS] test_canCall_transfer_notOpenToPublic() (gas: 82330)
[PASS] test_canCall_transfer_recipientNotAllowed() (gas: 100624)
[PASS] test_canCall_withdraw() (gas: 28312)
Test result: ok. 32 passed; 0 failed; finished in 6.41ms

Running 4 tests for tests/PoolManager.t.sol:RemoveLoanImpairmentTests
[PASS] test_removeLoanImpairment_notGovernor() (gas: 104754)
[PASS] test_removeLoanImpairment_notPoolDelegate() (gas: 101934)
[PASS] test_removeLoanImpairment_successCalledByGovernor() (gas: 76925)
[PASS] test_removeLoanImpairment_successCalledByPoolDelegate() (gas: 74119)
Test result: ok. 4 passed; 0 failed; finished in 12.09ms

Running 3 tests for tests/LoanManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 25386)
[PASS] test_migrate_notFactory() (gas: 20228)
[PASS] test_migrate_success() (gas: 31188)
Test result: ok. 3 passed; 0 failed; finished in 1.74ms

Running 5 tests for tests/PoolManager.t.sol:TriggerDefault
[PASS] test_triggerDefault_invalidFactory() (gas: 124841)
[PASS] test_triggerDefault_notAuthorized() (gas: 50895)
[PASS] test_triggerDefault_protocolPaused() (gas: 63654)
[PASS] test_triggerDefault_success_asGovernor() (gas: 95503)
[PASS] test_triggerDefault_success_asPoolDelegate() (gas: 91482)
Test result: ok. 5 passed; 0 failed; finished in 3.70ms

Running 4 tests for tests/PoolManager.t.sol:ConfigureTests
[PASS] test_configure_alreadyConfigured() (gas: 161075)
[PASS] test_configure_delegateManagementFeeOOB() (gas: 175489)
[PASS] test_configure_notDeployer() (gas: 180257)
[PASS] test_configure_success() (gas: 168737)
Test result: ok. 4 passed; 0 failed; finished in 3.06ms

Running 6 tests for tests/PoolManager.t.sol:RemoveLoanManager_SetterTests
[PASS] test_addLoanManager_protocolPaused() (gas: 56410)
[PASS] test_removeLoanManager_firstItem() (gas: 84370)
[PASS] test_removeLoanManager_notLM() (gas: 80459)
[PASS] test_removeLoanManager_notPD() (gas: 35564)
[PASS] test_removeLoanManager_secondItem() (gas: 84816)
[PASS] test_removeLoanManager_thirdItem() (gas: 82518)
Test result: ok. 6 passed; 0 failed; finished in 3.44ms

Running 3 tests for tests/PoolManager.t.sol:DepositCoverTests
[PASS] test_depositCover_insufficientApproval() (gas: 104153)
[PASS] test_depositCover_protocolPaused() (gas: 51637)
[PASS] test_depositCover_success() (gas: 88200)
Test result: ok. 3 passed; 0 failed; finished in 3.00ms

Running 3 tests for tests/PoolManager.t.sol:SetActive_SetterTests
[PASS] test_setActive_notGlobals() (gas: 33322)
[PASS] test_setActive_protocolPaused() (gas: 52316)
[PASS] test_setActive_success() (gas: 46539)
Test result: ok. 3 passed; 0 failed; finished in 2.91ms

Running 7 tests for tests/PoolManager.t.sol:WithdrawCoverTests
[PASS] test_withdrawCover_noRequirement() (gas: 93461)
[PASS] test_withdrawCover_notPoolDelegate() (gas: 151434)
[PASS] test_withdrawCover_protocolPaused() (gas: 54551)
[PASS] test_withdrawCover_success() (gas: 144971)
[PASS] test_withdrawCover_success_zeroRecipient() (gas: 144796)
[PASS] test_withdrawCover_tryWithdrawBelowRequired() (gas: 191351)
[PASS] test_withdrawCover_withdrawMoreThanBalance() (gas: 81177)
Test result: ok. 7 passed; 0 failed; finished in 7.57ms

Running 7 tests for tests/PoolManagerFactory.t.sol:PoolManagerFactoryFailureTest
[PASS] test_createInstance_failWithActivePoolDelegate() (gas: 262360)
[PASS] test_createInstance_failWithDisallowedAsset() (gas: 243610)
[PASS] test_createInstance_failWithInvalidPoolDelegate() (gas: 233658)
[PASS] test_createInstance_failWithNonERC20Asset() (gas: 240056)
[PASS] test_createInstance_failWithZeroAddressPoolDelegate() (gas: 190478)
[PASS] test_createInstance_failWithZeroAdmin() (gas: 3364729)
[PASS] test_createInstance_notPoolDeployer() (gas: 3085874)
Test result: ok. 7 passed; 0 failed; finished in 3.31ms

Running 9 tests for tests/PoolManager.t.sol:FinishCollateralLiquidation
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 204601)
[PASS] test_finishCollateralLiquidation_protocolPaused() (gas: 58869)
[PASS] test_finishCollateralLiquidation_success_coverLeftOver() (gas: 293788)
[PASS] test_finishCollateralLiquidation_success_exceedMaxCoverLiquidationPercentAmount() (gas: 291247)
[PASS] test_finishCollateralLiquidation_success_fullCoverLiquidation_preexistingLoss() (gas: 294871)
[PASS] test_finishCollateralLiquidation_success_noCoverLeftOver() (gas: 273855)
[PASS] test_finishCollateralLiquidation_success_noCover_asGovernor() (gas: 240410)
[PASS] test_finishCollateralLiquidation_success_noCover_asPoolDelegate() (gas: 234315)
[PASS] test_finishCollateralLiquidation_success_noRemainingLossAfterCollateralLiquidation() (gas: 241952)
Test result: ok. 9 passed; 0 failed; finished in 5.39ms

Running 3 tests for tests/PoolManager.t.sol:SetAllowedLender_SetterTests
[PASS] test_setAllowedLender_notPoolDelegate() (gas: 30945)
[PASS] test_setAllowedLender_protocolPaused() (gas: 52367)
[PASS] test_setAllowedLender_success() (gas: 50052)
Test result: ok. 3 passed; 0 failed; finished in 5.81ms

Running 1 test for tests/PoolManagerFactory.t.sol:PoolManagerFactoryTest
[PASS] test_createInstance() (gas: 3228641)
Test result: ok. 1 passed; 0 failed; finished in 2.31ms

Running 17 tests for tests/PoolManager.t.sol:FundTests
[PASS] test_acceptNewTerms_invalidInstance() (gas: 93467)
[PASS] test_fund_inactiveLoan() (gas: 79196)
[PASS] test_fund_insufficientCover() (gas: 238856)
[PASS] test_fund_invalidBorrower() (gas: 64712)
[PASS] test_fund_invalidFactory() (gas: 114450)
[PASS] test_fund_invalidLoanManager() (gas: 58363)
[PASS] test_fund_lockedLiquidity() (gas: 277978)
[PASS] test_fund_notPoolDelegate() (gas: 47799)
[PASS] test_fund_protocolPaused() (gas: 63283)
[PASS] test_fund_success() (gas: 134438)
[PASS] test_fund_success_skimUnaccountedFunds() (gas: 183826)
[PASS] test_fund_success_sufficientCover() (gas: 189255)
[PASS] test_fund_success_withExactUnaccountedAsRequired() (gas: 144853)
[PASS] test_fund_success_withLessUnaccountedThanRequired() (gas: 144668)
[PASS] test_fund_success_withMoreUnaccountedThanRequired() (gas: 144843)
[PASS] test_fund_transferFail() (gas: 114045)
[PASS] test_fund_zeroSupply() (gas: 69979)
Test result: ok. 17 passed; 0 failed; finished in 5.65ms

Running 5 tests for tests/PoolManager.t.sol:SetAllowedSlippage_SetterTests
[PASS] test_setAllowedSlippage_invalidLoanManager() (gas: 82813)
[PASS] test_setAllowedSlippage_notAuthorized() (gas: 39442)
[PASS] test_setAllowedSlippage_protocolPaused() (gas: 56731)
[PASS] test_setAllowedSlippage_success_asGovernor() (gas: 60953)
[PASS] test_setAllowedSlippage_success_asPoolDelegate() (gas: 55593)
Test result: ok. 5 passed; 0 failed; finished in 7.18ms

Running 5 tests for tests/PoolManager.t.sol:ImpairLoanTests
[PASS] test_impairLoan_notGovernor() (gas: 100468)
[PASS] test_impairLoan_notPoolDelegate() (gas: 97725)
[PASS] test_impairLoan_protocolPaused() (gas: 59014)
[PASS] test_impairLoan_successCalledByGovernor() (gas: 77780)
[PASS] test_impairLoan_successCalledByPoolDelegate() (gas: 75018)
Test result: ok. 5 passed; 0 failed; finished in 3.53ms

Running 4 tests for tests/PoolManager.t.sol:SetDelegateManagementFeeRate_SetterTests
[PASS] test_setDelegateManagementFeeRate_notPoolDelegate() (gas: 35481)
[PASS] test_setDelegateManagementFeeRate_oob() (gas: 77531)
[PASS] test_setDelegateManagementFeeRate_protocolPaused() (gas: 56381)
[PASS] test_setDelegateManagementFeeRate_success() (gas: 61059)
Test result: ok. 4 passed; 0 failed; finished in 2.96ms

Running 2 tests for tests/PoolManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 19935)
[PASS] test_setImplementation_success() (gas: 32415)
Test result: ok. 2 passed; 0 failed; finished in 9.67ms

Running 2 tests for tests/LoanManager.t.sol:QueueNextPaymentTests
[PASS] testFuzz_queueNextPayment_fees(uint256,uint256) (runs: 256, μ: 199848, ~: 208868)
[PASS] test_queueNextPayment_fees() (gas: 168620)
Test result: ok. 2 passed; 0 failed; finished in 37.48ms

Running 7 tests for tests/Pool.t.sol:PreviewDepositTests
[PASS] testFuzz_previewDeposit(uint256,uint256,uint256) (runs: 256, μ: 167680, ~: 173425)
[PASS] test_previewDeposit_decreasedExchangeRate() (gas: 174113)
[PASS] test_previewDeposit_increasedExchangeRate() (gas: 174126)
[PASS] test_previewDeposit_initialExchangeRate() (gas: 174049)
[PASS] test_previewDeposit_initialState() (gas: 20826)
[PASS] test_previewDeposit_prematureYield() (gas: 40748)
[PASS] test_previewDeposit_worthlessShares() (gas: 161390)
Test result: ok. 7 passed; 0 failed; finished in 58.74ms

Running 5 tests for tests/Pool.t.sol:RequestWithdraw
[PASS] testFuzz_requestWithdraw_failNotEnabled(uint256) (runs: 256, μ: 81607, ~: 82597)
[PASS] test_requestWithdraw_checkCall() (gas: 79432)
[PASS] test_requestWithdraw_failWithoutApproval() (gas: 42505)
[PASS] test_requestWithdraw_insufficientApproval() (gas: 113395)
[PASS] test_requestWithdraw_withApproval_failNotEnabled() (gas: 80204)
Test result: ok. 5 passed; 0 failed; finished in 44.02ms

Running 4 tests for tests/LoanManager.t.sol:RefinanceAccountingSingleLoanTests
[PASS] test_refinance_beforeLoanDueDate_interestOnly() (gas: 545476)
[PASS] test_refinance_onLatePayment_interestOnly() (gas: 547239)
[PASS] test_refinance_onLoanPaymentDueDate_interestOnly() (gas: 545964)
[PASS] test_refinance_onPaymentDueDate_amortized() (gas: 546843)
Test result: ok. 4 passed; 0 failed; finished in 4.48ms

Running 6 tests for tests/LoanManager.t.sol:RemoveLoanImpairmentTests
[PASS] test_removeLoanImpairment_calledByGovernor() (gas: 244863)
[PASS] test_removeLoanImpairment_delegateNotAuthorizedToRemoveGovernors() (gas: 252280)
[PASS] test_removeLoanImpairment_notManager() (gas: 244860)
[PASS] test_removeLoanImpairment_pastDueDate() (gas: 258161)
[PASS] test_removeLoanImpairment_successWithGovernor() (gas: 282952)
[PASS] test_removeLoanImpairment_successWithPD() (gas: 282900)
Test result: ok. 6 passed; 0 failed; finished in 3.64ms

Running 3 tests for tests/PoolManager.t.sol:SetLiquidityCap_SetterTests
[PASS] test_setLiquidityCap_notPoolDelegate() (gas: 33305)
[PASS] test_setLiquidityCap_protocolPaused() (gas: 54162)
[PASS] test_setLiquidityCap_success() (gas: 58843)
Test result: ok. 3 passed; 0 failed; finished in 13.66ms

Running 4 tests for tests/PoolManager.t.sol:MaxDepositTests
[PASS] test_maxDeposit_liquidityCap() (gas: 253945)
[PASS] test_maxDeposit_liquidityCap(address,address,uint256,uint256) (runs: 256, μ: 128402, ~: 131729)
[PASS] test_maxDeposit_privatePool() (gas: 136637)
[PASS] test_maxDeposit_publicPool() (gas: 129326)
Test result: ok. 4 passed; 0 failed; finished in 25.87ms

Running 3 tests for tests/PoolDelegateCover.t.sol:PoolDelegateCoverTests
[PASS] test_moveFunds_badTransfer() (gas: 59699)
[PASS] test_moveFunds_notManager() (gas: 51352)
[PASS] test_moveFunds_success() (gas: 59753)
Test result: ok. 3 passed; 0 failed; finished in 1.02ms

Running 3 tests for tests/LoanManager.t.sol:SetAllowedSlippage_SetterTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 22485)
[PASS] test_setAllowedSlippage_notPoolManager() (gas: 19910)
[PASS] test_setAllowedSlippage_success() (gas: 39436)
Test result: ok. 3 passed; 0 failed; finished in 1.67ms

Running 2 tests for tests/LoanManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 19935)
[PASS] test_setImplementation_success() (gas: 32479)
Test result: ok. 2 passed; 0 failed; finished in 2.21ms

Running 3 tests for tests/PoolDeployer.t.sol:PoolDeployerTests
[PASS] test_deployPool_invalidInitializers() (gas: 1968125)
[PASS] test_deployPool_invalidPoolDelegate() (gas: 1736994)
[PASS] test_deployPool_transferFailed() (gas: 2254721)
Test result: ok. 3 passed; 0 failed; finished in 3.10ms

Running 2 tests for tests/LoanManager.t.sol:SetLoanTransferAdmin_SetterTests
[PASS] testFail_setLoanTransferAdmin_notPoolDelegate() (gas: 20304)
[PASS] test_setLoanTransferAdmin_success() (gas: 43969)
Test result: ok. 2 passed; 0 failed; finished in 1.71ms

Running 4 tests for tests/PoolManager.t.sol:AcceptNewTermsTests
[PASS] test_acceptNewTerms_invalidFactory() (gas: 121825)
[PASS] test_acceptNewTerms_invalidInstance() (gas: 100804)
[PASS] test_acceptNewTerms_lockedLiquidity() (gas: 302281)
[PASS] test_acceptNewTerms_unaccountedFunds() (gas: 214211)
Test result: ok. 4 passed; 0 failed; finished in 3.98ms

Running 4 tests for tests/TransitionLoanManager.t.sol:TransitionLoanManagerAddTests
[PASS] test_add_latePayment() (gas: 363099)
[PASS] test_add_multipleLoans() (gas: 652120)
[PASS] test_add_noPayment() (gas: 43869)
[PASS] test_add_notMigrationAdmin() (gas: 35940)
Test result: ok. 4 passed; 0 failed; finished in 2.10ms

Running 2 tests for tests/LoanManager.t.sol:SetMinRatio_SetterTests
[PASS] test_setMinRatio_notPoolManager() (gas: 19907)
[PASS] test_setMinRatio_success() (gas: 39480)
Test result: ok. 2 passed; 0 failed; finished in 7.23ms

Running 3 tests for tests/Pool.t.sol:ConstructorTests
[PASS] test_constructor_invalidApproval() (gas: 3716791)
[PASS] test_constructor_invalidDecimals() (gas: 3625220)
[PASS] test_constructor_zeroManager() (gas: 3373789)
Test result: ok. 3 passed; 0 failed; finished in 4.28ms

Running 3 tests for tests/Pool.t.sol:WithdrawTests
[PASS] testFuzz_withdraw_failNotEnabled(uint256) (runs: 256, μ: 31556, ~: 31556)
[PASS] test_withdraw_checkCall() (gas: 79472)
[PASS] test_withdraw_failNotEnabled() (gas: 31431)
Test result: ok. 3 passed; 0 failed; finished in 25.95ms

Running 4 tests for tests/Pool.t.sol:ConvertToExitAssetsTests
[PASS] testFuzz_convertToExitAssets(uint256,uint256,uint256,uint256) (runs: 256, μ: 193527, ~: 196764)
[PASS] testFuzz_convertToExitAssets_zeroSupply(uint256) (runs: 256, μ: 7880, ~: 7880)
[PASS] test_convertToExitAssets() (gas: 217908)
[PASS] test_convertToExitAssets_zeroSupply() (gas: 11273)
Test result: ok. 4 passed; 0 failed; finished in 78.10ms

Running 7 tests for tests/Pool.t.sol:PreviewMintTests
[PASS] testFuzz_previewMint(uint256,uint256,uint256) (runs: 256, μ: 169488, ~: 176531)
[PASS] test_previewMint_decreasedExchangeRate() (gas: 174497)
[PASS] test_previewMint_increasedExchangeRate() (gas: 174552)
[PASS] test_previewMint_initialExchangeRate() (gas: 174520)
[PASS] test_previewMint_initialState() (gas: 20775)
[PASS] test_previewMint_prematureYield() (gas: 40664)
[PASS] test_previewMint_worthlessShares() (gas: 154587)
Test result: ok. 7 passed; 0 failed; finished in 61.07ms

Running 7 tests for tests/Pool.t.sol:ConvertToAssetsTests
[PASS] testFuzz_convertToAssets(uint256,uint256,uint256) (runs: 256, μ: 168302, ~: 173230)
[PASS] test_convertToAssets_decreasedExchangeRate() (gas: 173847)
[PASS] test_convertToAssets_increasedExchangeRate() (gas: 173902)
[PASS] test_convertToAssets_initialExchangeRate() (gas: 173858)
[PASS] test_convertToAssets_initialState() (gas: 20606)
[PASS] test_convertToAssets_prematureYield() (gas: 40483)
[PASS] test_convertToAssets_worthlessShares() (gas: 153992)
Test result: ok. 7 passed; 0 failed; finished in 43.86ms

Running 8 tests for tests/Pool.t.sol:RedeemTests
[PASS] test_redeem_checkCall() (gas: 79567)
[PASS] test_redeem_insufficientAmount() (gas: 64219)
[PASS] test_redeem_insufficientApprove() (gas: 174843)
[PASS] test_redeem_reentrancy() (gas: 137460)
[PASS] test_redeem_success() (gas: 131797)
[PASS] test_redeem_success_differentUser() (gas: 207776)
[PASS] test_redeem_zeroAssets() (gas: 91982)
[PASS] test_redeem_zeroShares() (gas: 48721)
Test result: ok. 8 passed; 0 failed; finished in 9.41ms

Running 4 tests for tests/Pool.t.sol:RemoveSharesTests
[PASS] test_removeShares_checkCall() (gas: 53098)
[PASS] test_removeShares_failWithoutApproval() (gas: 32632)
[PASS] test_removeShares_insufficientApproval() (gas: 65142)
[PASS] test_removeShares_withApproval() (gas: 46468)
Test result: ok. 4 passed; 0 failed; finished in 2.93ms

Running 6 tests for tests/Pool.t.sol:RequestRedeemTests
[PASS] test_requestRedeem_checkCall() (gas: 79356)
[PASS] test_requestRedeem_failWithoutApproval() (gas: 33858)
[PASS] test_requestRedeem_insufficientApproval() (gas: 96297)
[PASS] test_requestRedeem_withApproval() (gas: 71721)
[PASS] test_requestRedeem_zeroShares() (gas: 65009)
[PASS] test_requestRedeem_zeroSharesAndNotOwnerAndNoAllowance() (gas: 41829)
Test result: ok. 6 passed; 0 failed; finished in 3.25ms

Running 7 tests for tests/Pool.t.sol:ConvertToSharesTests
[PASS] testFuzz_convertToShares(uint256,uint256,uint256) (runs: 256, μ: 168435, ~: 173320)
[PASS] test_convertToShares_decreasedExchangeRate() (gas: 173865)
[PASS] test_convertToShares_increasedExchangeRate() (gas: 173942)
[PASS] test_convertToShares_initialExchangeRate() (gas: 173887)
[PASS] test_convertToShares_initialState() (gas: 20709)
[PASS] test_convertToShares_prematureYield() (gas: 40632)
[PASS] test_convertToShares_worthlessShares() (gas: 161308)
Test result: ok. 7 passed; 0 failed; finished in 47.23ms

Running 2 tests for tests/PoolManager.t.sol:MaxWithdrawTests
[PASS] testFuzz_maxWithdraw(address) (runs: 256, μ: 16415, ~: 16415)
[PASS] test_maxWithdraw() (gas: 16232)
Test result: ok. 2 passed; 0 failed; finished in 17.61ms

Running 10 tests for tests/Pool.t.sol:DepositWithPermitTests
[PASS] testFuzz_depositWithPermit_insufficientBalance(uint256) (runs: 256, μ: 205573, ~: 205455)
[PASS] test_depositWithPermit_badNonce() (gas: 127899)
[PASS] test_depositWithPermit_checkCall() (gas: 148376)
[PASS] test_depositWithPermit_notStakerSignature() (gas: 129862)
[PASS] test_depositWithPermit_pastDeadline() (gas: 101647)
[PASS] test_depositWithPermit_reentrancy() (gas: 224442)
[PASS] test_depositWithPermit_replay() (gas: 224177)
[PASS] test_depositWithPermit_zeroAddress() (gas: 101051)
[PASS] test_depositWithPermit_zeroReceiver() (gas: 151561)
[PASS] test_depositWithPermit_zeroShares() (gas: 131806)
Test result: ok. 10 passed; 0 failed; finished in 144.20ms

Running 1 test for tests/LoanManagerFuzz.t.sol:SingleLoanClaimTests
[PASS] testFuzz_claim_latePayment_interestOnly(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 1444731, ~: 1450517)
Test result: ok. 1 passed; 0 failed; finished in 161.76ms

Running 5 tests for tests/PoolManager.t.sol:MaxMintTests
[PASS] testFuzz_maxMint_liquidityCap(address,address,uint256,uint256,uint256) (runs: 256, μ: 226612, ~: 226576)
[PASS] test_maxMint_liquidityCap_exchangeRateGtOne() (gas: 368547)
[PASS] test_maxMint_liquidityCap_exchangeRateOneToOne() (gas: 389444)
[PASS] test_maxMint_privatePool() (gas: 300991)
[PASS] test_maxMint_publicPool() (gas: 287431)
Test result: ok. 5 passed; 0 failed; finished in 107.60ms

Running 6 tests for tests/Pool.t.sol:MintTests
[PASS] testFuzz_mint_badApprove(uint256) (runs: 256, μ: 158402, ~: 160304)
[PASS] testFuzz_mint_insufficientBalance(uint256) (runs: 256, μ: 162977, ~: 162862)
[PASS] test_mint_checkCall() (gas: 133441)
[PASS] test_mint_reentrancy() (gas: 181821)
[PASS] test_mint_zeroReceiver() (gas: 109254)
[PASS] test_mint_zeroShares() (gas: 109171)
Test result: ok. 6 passed; 0 failed; finished in 47.25ms

Running 6 tests for tests/Pool.t.sol:DepositTests
[PASS] testFuzz_deposit_badApprove(uint256) (runs: 256, μ: 159723, ~: 160234)
[PASS] testFuzz_deposit_insufficientBalance(uint256) (runs: 256, μ: 162864, ~: 162747)
[PASS] test_deposit_checkCall() (gas: 131092)
[PASS] test_deposit_reentrancy() (gas: 181773)
[PASS] test_deposit_zeroReceiver() (gas: 109228)
[PASS] test_deposit_zeroShares() (gas: 109123)
Test result: ok. 6 passed; 0 failed; finished in 50.77ms

Running 11 tests for tests/Pool.t.sol:MintWithPermitTests
[PASS] testFuzz_mintWithPermit_insufficientBalance(uint256) (runs: 256, μ: 205712, ~: 205621)
[PASS] test_mintWithPermit_badNonce() (gas: 132294)
[PASS] test_mintWithPermit_checkCall() (gas: 148483)
[PASS] test_mintWithPermit_insufficientPermit() (gas: 97237)
[PASS] test_mintWithPermit_notStakerSignature() (gas: 134235)
[PASS] test_mintWithPermit_pastDeadline() (gas: 106017)
[PASS] test_mintWithPermit_reentrancy() (gas: 224511)
[PASS] test_mintWithPermit_replay() (gas: 247736)
[PASS] test_mintWithPermit_zeroAddress() (gas: 105418)
[PASS] test_mintWithPermit_zeroReceiver() (gas: 151596)
[PASS] test_mintWithPermit_zeroShares() (gas: 151713)
Test result: ok. 11 passed; 0 failed; finished in 111.94ms

Running 7 tests for tests/PoolMintFrontrunTests.t.sol:PoolMintFrontrunTests
[PASS] testFuzz_depositFrontRun_honestOnePercentHarm(uint256) (runs: 256, μ: 4593557, ~: 4593590)
[PASS] testFuzz_depositFrontRun_honestTenPercentHarm(uint256) (runs: 256, μ: 4593554, ~: 4593591)
[PASS] testFuzz_depositFrontRun_theftThwarted(uint256) (runs: 256, μ: 4600622, ~: 4600629)
[PASS] test_depositFrontRun_theft() (gas: 4557801)
[PASS] test_depositFrontRun_theftReverted() (gas: 4518005)
[PASS] test_depositFrontRun_theftThwarted() (gas: 4602495)
[PASS] test_depositFrontRun_zeroShares() (gas: 4550984)
Test result: ok. 7 passed; 0 failed; finished in 287.43ms

Running 14 tests for tests/ERC20.t.sol:Pool_ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 85021, ~: 86429)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 257926, ~: 257928)
[PASS] test_domainSeparator() (gas: 8272)
[PASS] test_initialState() (gas: 15798)
[PASS] test_permit_badS() (gas: 31581)
[PASS] test_permit_badV() (gas: 1045940)
[PASS] test_permit_differentSpender() (gas: 58276)
[PASS] test_permit_differentVerifier() (gas: 701499)
[PASS] test_permit_earlyNonce() (gas: 58344)
[PASS] test_permit_ownerSignerMismatch() (gas: 58326)
[PASS] test_permit_replay() (gas: 90518)
[PASS] test_permit_withExpiry() (gas: 94215)
[PASS] test_permit_zeroAddress() (gas: 58291)
[PASS] test_typehash() (gas: 5644)
Test result: ok. 14 passed; 0 failed; finished in 1.01s

Running 13 tests for tests/ERC20.t.sol:Pool_ERC20Test
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 30902, ~: 31758)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 30675, ~: 57963)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 35507, ~: 35514)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 36776, ~: 38405)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 38302, ~: 38380)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 784206, ~: 781402)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 53317, ~: 54406)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 72472, ~: 73405)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 358196, ~: 366391)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 363917, ~: 367192)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 365215, ~: 364524)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 347315, ~: 346209)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 356498, ~: 356499)
Test result: ok. 13 passed; 0 failed; finished in 58.63ms
```

# `withdrawal-manager (v1.0.0)`

```
Running 2 tests for tests/WithdrawalManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 19913)
[PASS] test_setImplementation_success() (gas: 32359)
Test result: ok. 2 passed; 0 failed; finished in 1.56ms

Running 5 tests for tests/WithdrawalManager.t.sol:LockedLiquidityTests
[PASS] test_lockedLiquidity_afterWindow() (gas: 24160)
[PASS] test_lockedLiquidity_beforeWindow() (gas: 24308)
[PASS] test_lockedLiquidity_duringWindow() (gas: 52012)
[PASS] test_lockedLiquidity_duringWindowWithdrawal() (gas: 112794)
[PASS] test_lockedLiquidity_unrealizedLosses() (gas: 139340)
Test result: ok. 5 passed; 0 failed; finished in 1.87ms

Running 5 tests for tests/WithdrawalManager.t.sol:UpgradeTests
[PASS] test_upgrade_notGovernor() (gas: 98476)
[PASS] test_upgrade_notPoolDelegate() (gas: 105188)
[PASS] test_upgrade_notScheduled() (gas: 39964)
[PASS] test_upgrade_success() (gas: 85389)
[PASS] test_upgrade_upgradeFailed() (gas: 78025)
Test result: ok. 5 passed; 0 failed; finished in 2.05ms

Running 8 tests for tests/WithdrawalManager.t.sol:RemoveSharesTests
[PASS] test_removeShares_cancelRequest() (gas: 158392)
[PASS] test_removeShares_decreaseRequest() (gas: 197305)
[PASS] test_removeShares_delayedUpdate() (gas: 199326)
[PASS] test_removeShares_failedTransfer() (gas: 143338)
[PASS] test_removeShares_notPoolManager() (gas: 20150)
[PASS] test_removeShares_pendingRequest() (gas: 150155)
[PASS] test_removeShares_sharesUnderflow() (gas: 150073)
[PASS] test_removeShares_zeroShares() (gas: 150114)
Test result: ok. 8 passed; 0 failed; finished in 2.38ms

Running 6 tests for tests/WithdrawalManagerFactory.t.sol:WithdrawalManagerFactoryTests
[PASS] testFail_createInstance_collision() (gas: 8937393460516736710)
[PASS] test_createInstance_notPoolDeployer() (gas: 244781)
[PASS] test_createInstance_success() (gas: 237685)
[PASS] test_createInstance_windowOutOfBounds() (gas: 153877)
[PASS] test_createInstance_zeroPool() (gas: 151697)
[PASS] test_createInstance_zeroWindow() (gas: 153808)
Test result: ok. 6 passed; 0 failed; finished in 2.21ms

Running 8 tests for tests/WithdrawalManager.t.sol:AddSharesTests
[PASS] test_addShares_createRequest() (gas: 166450)
[PASS] test_addShares_delayedUpdate() (gas: 202821)
[PASS] test_addShares_emptyRequest() (gas: 29390)
[PASS] test_addShares_failedTransfer() (gas: 105791)
[PASS] test_addShares_increaseRequest() (gas: 191179)
[PASS] test_addShares_notPoolManager() (gas: 19955)
[PASS] test_addShares_pendingRequest() (gas: 150007)
[PASS] test_addShares_refreshRequest() (gas: 200834)
Test result: ok. 8 passed; 0 failed; finished in 2.71ms

Running 10 tests for tests/WithdrawalManager.t.sol:ProcessExitTests
[PASS] test_processExit_fullWithdrawal_fullLiquidity() (gas: 228624)
[PASS] test_processExit_fullWithdrawal_noLiquidity() (gas: 231402)
[PASS] test_processExit_fullWithdrawal_partialLiquidity() (gas: 300217)
[PASS] test_processExit_lostShares() (gas: 231652)
[PASS] test_processExit_noRequest() (gas: 27145)
[PASS] test_processExit_notPoolManager() (gas: 20109)
[PASS] test_processExit_postWindow() (gas: 150361)
[PASS] test_processExit_preWindow() (gas: 150476)
[PASS] test_processExit_requestedSharedGtLocked() (gas: 136266)
[PASS] test_processExit_requestedSharedLtLocked() (gas: 136225)
Test result: ok. 10 passed; 0 failed; finished in 2.61ms

Running 3 tests for tests/WithdrawalManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 25870)
[PASS] test_migrate_notFactory() (gas: 20229)
[PASS] test_migrate_success() (gas: 31340)
Test result: ok. 3 passed; 0 failed; finished in 3.02ms

Running 2 tests for tests/WithdrawalManager.t.sol:ProcessExitWithMultipleUsers
[PASS] test_partialLiquidity_fullMoveShares() (gas: 450006)
[PASS] test_partialLiquidity_partialMoveShares_partialRemoveShares() (gas: 360980)
Test result: ok. 2 passed; 0 failed; finished in 1.85ms

Running 9 tests for tests/WithdrawalManager.t.sol:SetExitConfigTests
[PASS] test_setExitConfig_addConfig() (gas: 103295)
[PASS] test_setExitConfig_complexScenario() (gas: 236809)
[PASS] test_setExitConfig_cycleDurationCastOob() (gas: 150038)
[PASS] test_setExitConfig_failWhenPaused() (gas: 112746)
[PASS] test_setExitConfig_governor() (gas: 122756)
[PASS] test_setExitConfig_notPoolDelegate() (gas: 120095)
[PASS] test_setExitConfig_updateConfig() (gas: 176504)
[PASS] test_setExitConfig_windowOutOfBounds() (gas: 38885)
[PASS] test_setExitConfig_zeroWindow() (gas: 38827)
Test result: ok. 9 passed; 0 failed; finished in 4.03ms

Running 2 tests for tests/WithdrawalManager.t.sol:ViewFunctionTests
[PASS] testFuzz_previewWithdraw_alwaysReturnsZero(address,uint256) (runs: 256, μ: 11105, ~: 11105)
[PASS] test_noLockedShares_isInExitWindowCheck() (gas: 20658)
Test result: ok. 2 passed; 0 failed; finished in 7.33ms
```
