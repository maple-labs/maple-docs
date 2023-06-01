# Test Reports

Below is an report of all smart contract level tests that are run against the protocol, in all repos.

Current number of tests in this report is: **1683 tests**.

## `maple-core-v2`

```
Running 3 tests for tests/integration/ActivatePoolManager.t.sol:ActivatePoolManagerFailureTests
[PASS] test_activatePoolManager_failIfNotGlobals() (gas: 37438)
[PASS] test_activatePoolManager_failIfNotGovernor() (gas: 19239)
[PASS] test_activatePoolManager_failIfProtocolIsPaused() (gas: 71359)
Test result: ok. 3 passed; 0 failed; finished in 15.55ms

Running 4 tests for tests/integration/FinishCollateralLiquidation.t.sol:FinishCollateralLiquidationFailureTests
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 51297)
[PASS] test_finishCollateralLiquidation_notFinished() (gas: 653421)
[PASS] test_finishCollateralLiquidation_notPoolManager() (gas: 54718)
[PASS] test_finishCollateralLiquidation_whenImpaired() (gas: 288423)
Test result: ok. 4 passed; 0 failed; finished in 18.10ms

Running 1 test for tests/integration/DeployLoan.t.sol:DeployFixedTermLoanTests
[PASS] test_deployFixedTermLoan_feeManagerCheck() (gas: 902611)
Test result: ok. 1 passed; 0 failed; finished in 18.60ms

Running 5 tests for tests/integration/PoolAccountingViewFunctions.t.sol:TotalAssetsTests
[PASS] test_totalAssets_singleDeposit() (gas: 246427)
[PASS] test_totalAssets_singleLoanFunded() (gas: 1529736)
[PASS] test_totalAssets_singleLoanFundedWithInterest() (gas: 1564475)
[PASS] test_totalAssets_singleLoanFundedWithPayment() (gas: 1794288)
[PASS] test_totalAssets_zeroTotalSupply() (gas: 65301)
Test result: ok. 5 passed; 0 failed; finished in 22.24ms

Running 1 test for tests/integration/MakePayment.t.sol:MakePaymentTestsDomainStartGtDomainEnd
[PASS] test_makePayment_domainStart_gt_domainEnd() (gas: 3729409)
Test result: ok. 1 passed; 0 failed; finished in 24.32ms

Running 3 tests for tests/e2e/RefinanceScenario.t.sol:RefinanceScenariosTests
[PASS] test_impairOTL_refinanceToHigherPrincipal_oneLoanImpaired_underflow() (gas: 1293546)
[PASS] test_impairOTL_refinanceToHigherPrincipal_twoLoansImpaired() (gas: 1480056)
[PASS] test_impairOTL_refinanceToLowerPrincipal_singleLoanImpaired() (gas: 1350545)
Test result: ok. 3 passed; 0 failed; finished in 26.17ms

Running 1 test for tests/integration/ActivatePoolManager.t.sol:ActivatePoolManagerTests
[PASS] test_activatePoolManager() (gas: 83147)
Test result: ok. 1 passed; 0 failed; finished in 15.21ms

Running 1 test for tests/integration/MakePayment.t.sol:MakePaymentTestsPastDomainEnd
[PASS] test_makePayment_lateLoan3_loan1NotPaid_loan2NotPaid() (gas: 1036370)
Test result: ok. 1 passed; 0 failed; finished in 19.70ms

Running 18 tests for tests/integration/DeployPool.t.sol:DeployPoolTests
[PASS] test_deployPool_failIfCalledPMFactoryDirectly() (gas: 31166)
[PASS] test_deployPool_failIfCalledWMFactoryDirectly() (gas: 33519)
[PASS] test_deployPool_failWithAssetNotAllowed() (gas: 314528)
[PASS] test_deployPool_failWithInsufficientPDApproval() (gas: 6155769)
[PASS] test_deployPool_failWithInvalidAsset() (gas: 412345)
[PASS] test_deployPool_failWithInvalidLMFactory() (gas: 5501693)
[PASS] test_deployPool_failWithInvalidManagementFee() (gas: 6154689)
[PASS] test_deployPool_failWithInvalidPD() (gas: 45111)
[PASS] test_deployPool_failWithInvalidPMFactory() (gas: 62922)
[PASS] test_deployPool_failWithInvalidWMFactory() (gas: 67843)
[PASS] test_deployPool_failWithNonZeroSupplyAndZeroMigrationAdmin() (gas: 398031)
[PASS] test_deployPool_failWithOwnedPoolManager() (gas: 6498356)
[PASS] test_deployPool_failWithWindowDurationGtCycleDuration() (gas: 5375406)
[PASS] test_deployPool_failWithZeroAsset() (gas: 273015)
[PASS] test_deployPool_failWithZeroWindowDuration() (gas: 5375469)
[PASS] test_deployPool_success() (gas: 6424066)
[PASS] test_deployPool_successWithInitialSupply() (gas: 6363501)
[PASS] test_deployPool_successWithZeroMigrationAdmin() (gas: 6326031)
Test result: ok. 18 passed; 0 failed; finished in 26.19ms

Running 1 test for tests/e2e/PoolLifecycle.t.sol:PoolLifecycleTest
[PASS] test_poolLifecycle() (gas: 11473749)
Test result: ok. 1 passed; 0 failed; finished in 25.36ms

Running 1 test for tests/integration/BasicInterestAccrual.t.sol:BasicInterestAccrualTest
[PASS] test_basicInterestAccrual() (gas: 2408975)
Test result: ok. 1 passed; 0 failed; finished in 19.43ms

Running 9 tests for tests/integration/Fund.t.sol:FixedTermLoanManagerFundTests
[PASS] test_fund_failIfAmountGreaterThanLockedLiquidity() (gas: 1735672)
[PASS] test_fund_failIfInsufficientCover() (gas: 261795)
[PASS] test_fund_failIfLoanActive() (gas: 960840)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 56239)
[PASS] test_fund_failIfPoolDoesNotApprovePM() (gas: 284362)
[PASS] test_fund_failIfProtocolIsPaused() (gas: 59874)
[PASS] test_fund_failIfTotalSupplyIsZero() (gas: 460194)
[PASS] test_fund_oneLoan() (gas: 856865)
[PASS] test_fund_twoLoans() (gas: 1400668)
Test result: ok. 9 passed; 0 failed; finished in 32.31ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentTestsSingleLoanAmortized
[PASS] test_makePayment_earlyPayment_amortized() (gas: 791012)
[PASS] test_makePayment_latePayment_amortized() (gas: 804283)
[PASS] test_makePayment_onTimePayment_amortized() (gas: 791040)
Test result: ok. 3 passed; 0 failed; finished in 27.65ms

Running 17 tests for tests/integration/Fund.t.sol:OpenTermLoanManagerFundTests
[PASS] test_fund_insufficientCover() (gas: 378858)
[PASS] test_fund_invalidBorrower() (gas: 102273)
[PASS] test_fund_invalidLoanFactory() (gas: 88338)
[PASS] test_fund_invalidLoanInstance() (gas: 220191)
[PASS] test_fund_invalidLoanManagerFactory() (gas: 138794)
[PASS] test_fund_loanActive() (gas: 744955)
[PASS] test_fund_loanManagerApproveFailure() (gas: 453290)
[PASS] test_fund_loanNotActive() (gas: 692657)
[PASS] test_fund_loanTransferFailure() (gas: 512573)
[PASS] test_fund_lockedLiquidity() (gas: 572376)
[PASS] test_fund_notLender() (gas: 38541)
[PASS] test_fund_notLoanManager() (gas: 378332)
[PASS] test_fund_notPoolDelegate() (gas: 56262)
[PASS] test_fund_poolManagerTransferFailure() (gas: 398853)
[PASS] test_fund_protocolPause() (gas: 52061)
[PASS] test_fund_success() (gas: 651659)
[PASS] test_fund_zeroSupply() (gas: 592480)
Test result: ok. 17 passed; 0 failed; finished in 36.81ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentTestsSingleLoanInterestOnly
[PASS] test_makePayment_earlyPayment_interestOnly() (gas: 762013)
[PASS] test_makePayment_latePayment_interestOnly() (gas: 772333)
[PASS] test_makePayment_onTimePayment_interestOnly() (gas: 759351)
Test result: ok. 3 passed; 0 failed; finished in 19.42ms

Running 4 tests for tests/integration/MakePayment.t.sol:MakePaymentTestsSingleLoanOpenTerm
[PASS] test_makePayment_OT_latePayment() (gas: 719021)
[PASS] test_makePayment_OT_onTimePayment() (gas: 710731)
[PASS] test_makePayment_OT_withCall() (gas: 682948)
[PASS] test_makePayment_OT_withImpairment() (gas: 763567)
Test result: ok. 4 passed; 0 failed; finished in 21.26ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentTestsTwoLoans
[PASS] test_makePayment_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 1526790)
[PASS] test_makePayment_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 1541357)
[PASS] test_makePayment_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 1526818)
Test result: ok. 3 passed; 0 failed; finished in 27.28ms

Running 1 test for tests/fuzz/Deposit.t.sol:DepositFuzzTests
[PASS] testDeepFuzz_deposit_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 447748, ~: 472773)
Test result: ok. 1 passed; 0 failed; finished in 170.69ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:DepositFailureTests
[PASS] test_deposit_insufficientApproval() (gas: 317094)
[PASS] test_deposit_liquidityCapExceeded() (gas: 388301)
[PASS] test_deposit_notActive() (gas: 57722)
[PASS] test_deposit_privatePoolInvalidRecipient() (gas: 345967)
[PASS] test_deposit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 311031)
[PASS] test_deposit_protocolPaused() (gas: 107504)
Test result: ok. 6 passed; 0 failed; finished in 14.48ms

Running 2 tests for tests/e2e/Regression.t.sol:RegressionTest
[PASS] test_ftlRegression() (gas: 35970346)
[PASS] test_otlRegression() (gas: 60907423)
Test result: ok. 2 passed; 0 failed; finished in 289.20ms

Running 1 test for tests/fuzz/Mint.t.sol:MintFuzzTests
[PASS] testDeepFuzz_mint_all(address,address,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 462643, ~: 498675)
Test result: ok. 1 passed; 0 failed; finished in 183.89ms

Running 4 tests for tests/integration/RemoveCall.t.sol:RemoveCallFailureTests
[PASS] test_callPrincipal_notCalled() (gas: 81479)
[PASS] test_callPrincipal_notLender() (gas: 38193)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 51179)
[PASS] test_callPrincipal_paused() (gas: 52014)
Test result: ok. 4 passed; 0 failed; finished in 14.24ms

Running 3 tests for tests/integration/RemoveCall.t.sol:RemoveCallTests
[PASS] test_removeCall_impaired() (gas: 421664)
[PASS] test_removeCall_latePayment() (gas: 153833)
[PASS] test_removeCall_paymentOnTime() (gas: 155467)
Test result: ok. 3 passed; 0 failed; finished in 20.90ms

Running 1 test for tests/e2e/MultiLoanManager.sol:MultiLoanManagerTests
[PASS] test_4loans_3lps() (gas: 7302453)
Test result: ok. 1 passed; 0 failed; finished in 32.61ms

Running 5 tests for tests/integration/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 69404)
[PASS] test_removeLoanImpairment_notGovernor() (gas: 265110)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 82722)
[PASS] test_removeLoanImpairment_notLender() (gas: 37797)
[PASS] test_removeLoanImpairment_pastDate() (gas: 348360)
Test result: ok. 5 passed; 0 failed; finished in 17.07ms

Running 3 tests for tests/integration/UnrealizedLosses.t.sol:UnrealizedLossesTests
[PASS] test_unrealizedLosses_depositWithUnrealizedLosses() (gas: 470592)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_fullLiquidity() (gas: 602195)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_partialLiquidity() (gas: 1903209)
Test result: ok. 3 passed; 0 failed; finished in 21.60ms

Running 9 tests for tests/integration/RemoveShares.t.sol:RemoveSharesFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 192333)
[PASS] test_removeShares_failIfInvalidShares() (gas: 93525)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 93489)
[PASS] test_removeShares_failIfNotPool() (gas: 46054)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 19241)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 67089)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 171973)
[PASS] test_removeShares_failIfTransferFail() (gas: 157501)
[PASS] test_removeShares_failIfWithdrawalIsPending() (gas: 212306)
Test result: ok. 9 passed; 0 failed; finished in 15.43ms

Running 2 tests for tests/integration/Upgrade.t.sol:GlobalsUpgradeTests
[PASS] test_upgradeGlobals() (gas: 25931)
[PASS] test_upgradeGlobals_notAdmin() (gas: 30346)
Test result: ok. 2 passed; 0 failed; finished in 12.95ms

Running 4 tests for tests/integration/RemoveShares.t.sol:RemoveSharesTests
[PASS] test_removeShares_pastTheRedemptionWindow() (gas: 156911)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 544381)
[PASS] test_removeShares_success() (gas: 157017)
[PASS] test_removeShares_withApproval() (gas: 174430)
Test result: ok. 4 passed; 0 failed; finished in 15.65ms

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapMintWithPermitTests
[PASS] testFuzz_mintWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 380013, ~: 380287)
[PASS] testFuzz_mintWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 242869, ~: 243286)
[PASS] testFuzz_mintWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 573976, ~: 573302)
[PASS] test_mintWithPermit_exactBootstrapMintAmount() (gas: 353730)
[PASS] test_mintWithPermit_gtBootstrapMintAmount() (gas: 374429)
[PASS] test_mintWithPermit_ltBootstrapMintAmount() (gas: 286105)
[PASS] test_mintWithPermit_secondDepositorGetsCorrectShares() (gas: 568587)
Test result: ok. 7 passed; 0 failed; finished in 407.40ms

Running 6 tests for tests/integration/Upgrade.t.sol:LiquidationUpgradeTests
[PASS] test_upgradeLiquidator_delayNotPassed() (gas: 169380)
[PASS] test_upgradeLiquidator_durationPassed() (gas: 170166)
[PASS] test_upgradeLiquidator_governor_noTimelockNeeded() (gas: 208290)
[PASS] test_upgradeLiquidator_noTimelock() (gas: 177775)
[PASS] test_upgradeLiquidator_timelockExtended() (gas: 300903)
[PASS] test_upgradeLiquidator_timelockShortened() (gas: 301751)
Test result: ok. 6 passed; 0 failed; finished in 19.02ms

Running 4 tests for tests/integration/SetMinRatioAndSlippage.t.sol:SetMinRatioTests
[PASS] test_setMinRatio_notAuthorized() (gas: 57357)
[PASS] test_setMinRatio_notPoolManager() (gas: 57357)
[PASS] test_setMinRatio_withGovernor() (gas: 85497)
[PASS] test_setMinRatio_withPoolDelegate() (gas: 79675)
Test result: ok. 4 passed; 0 failed; finished in 12.99ms

Running 6 tests for tests/integration/Upgrade.t.sol:LoanManagerUpgradeTests
[PASS] test_upgradeLoanManager_delayNotPassed() (gas: 168576)
[PASS] test_upgradeLoanManager_durationPassed() (gas: 169382)
[PASS] test_upgradeLoanManager_governor_noTimelockNeeded() (gas: 195561)
[PASS] test_upgradeLoanManager_noTimelock() (gas: 177017)
[PASS] test_upgradeLoanManager_timelockExtended() (gas: 294954)
[PASS] test_upgradeLoanManager_timelockShortened() (gas: 295735)
Test result: ok. 6 passed; 0 failed; finished in 18.43ms

Running 5 tests for tests/integration/SetMinRatioAndSlippage.t.sol:SetSlippageTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 131128)
[PASS] test_setAllowedSlippage_notAuthorized() (gas: 57292)
[PASS] test_setAllowedSlippage_notPoolManager() (gas: 57358)
[PASS] test_setAllowedSlippage_withGovernor() (gas: 85480)
[PASS] test_setAllowedSlippage_withPoolDelegate() (gas: 79615)
Test result: ok. 5 passed; 0 failed; finished in 13.41ms

Running 6 tests for tests/integration/Upgrade.t.sol:PoolManagerUpgradeTests
[PASS] test_upgradePoolManager_delayNotPassed() (gas: 146996)
[PASS] test_upgradePoolManager_durationPassed() (gas: 147869)
[PASS] test_upgradePoolManager_governor_noTimelockNeeded() (gas: 174025)
[PASS] test_upgradePoolManager_noTimelock() (gas: 155457)
[PASS] test_upgradePoolManager_timelockExtended() (gas: 251991)
[PASS] test_upgradePoolManager_timelockShortened() (gas: 252750)
Test result: ok. 6 passed; 0 failed; finished in 17.61ms

Running 10 tests for tests/integration/Transfer.t.sol:TransferTests
[PASS] test_transferFrom_privatePoolInvalidLender() (gas: 366211)
[PASS] test_transferFrom_privatePoolInvalidLender_openPoolToPublic() (gas: 345220)
[PASS] test_transferFrom_protocolPaused() (gas: 310397)
[PASS] test_transferFrom_publicPool() (gas: 293991)
[PASS] test_transferFrom_publicPool_insufficientApproval() (gas: 296464)
[PASS] test_transferFrom_publicPool_noApproval() (gas: 271368)
[PASS] test_transfer_privatePoolInvalidLender() (gas: 351825)
[PASS] test_transfer_privatePoolInvalidLender_openPoolToPublic() (gas: 330879)
[PASS] test_transfer_protocolPaused() (gas: 282303)
[PASS] test_transfer_publicPool() (gas: 279820)
Test result: ok. 10 passed; 0 failed; finished in 21.23ms

Running 1 test for tests/integration/Upgrade.t.sol:UnscheduleCallTests
[PASS] test_unscheduleCall_governor() (gas: 89456)
Test result: ok. 1 passed; 0 failed; finished in 14.21ms

Running 7 tests for tests/integration/TransferPoolOwnership.t.sol:TransferPoolOwnershipTests
[PASS] test_acceptPoolDelegate() (gas: 111052)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 117564)
[PASS] test_setPendingPoolDelegate() (gas: 68174)
[PASS] test_setPendingPoolDelegate_notPD() (gas: 99288)
[PASS] test_transferOwnedPoolManager_alreadyPoolDelegate() (gas: 151722)
[PASS] test_transferOwnedPoolManager_notPoolManager() (gas: 117633)
[PASS] test_transferOwnedPoolManager_notValidPoolDelegate() (gas: 126708)
Test result: ok. 7 passed; 0 failed; finished in 14.44ms

Running 6 tests for tests/integration/Upgrade.t.sol:WithdrawalManagerUpgradeTests
[PASS] test_upgradeWithdrawalManager_delayNotPassed() (gas: 147881)
[PASS] test_upgradeWithdrawalManager_durationPassed() (gas: 148621)
[PASS] test_upgradeWithdrawalManager_governor_noTimelockNeeded() (gas: 178450)
[PASS] test_upgradeWithdrawalManager_noTimelock() (gas: 156234)
[PASS] test_upgradeWithdrawalManager_timelockExtended() (gas: 257793)
[PASS] test_upgradeWithdrawalManager_timelockShortened() (gas: 258640)
Test result: ok. 6 passed; 0 failed; finished in 15.14ms

Running 1 test for tests/integration/ValidCollateral.t.sol:ValidCollateralTests
[PASS] test_setIsCollateral_invalidCollateral() (gas: 829206)
Test result: ok. 1 passed; 0 failed; finished in 13.24ms

Running 10 tests for tests/integration/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultFailureTests
[PASS] test_triggerDefault_invalidLoanManager() (gas: 4866080)
[PASS] test_triggerDefault_notAuthorized() (gas: 53786)
[PASS] test_triggerDefault_notFactory() (gas: 54889)
[PASS] test_triggerDefault_notInDefault_boundary() (gas: 604391)
[PASS] test_triggerDefault_notLoan() (gas: 94125)
[PASS] test_triggerDefault_notPM() (gas: 443450)
[PASS] test_triggerDefault_protocolPaused_loanManager() (gas: 55221)
[PASS] test_triggerDefault_protocolPaused_poolManager() (gas: 54657)
[PASS] test_triggerDefault_repossess_notLender() (gas: 40765)
[PASS] test_triggerDefault_treasuryZeroAddress() (gas: 562196)
Test result: ok. 10 passed; 0 failed; finished in 24.53ms

Running 3 tests for tests/integration/Withdraw.t.sol:RequestWithdrawFailureTests
[PASS] test_requestWithdraw_failIfInsufficientApproval() (gas: 269773)
[PASS] test_requestWithdraw_failIfNotPM() (gas: 18940)
[PASS] test_requestWithdraw_failIfNotPool() (gas: 46216)
Test result: ok. 3 passed; 0 failed; finished in 20.22ms

Running 4 tests for tests/integration/DepositAndMint.t.sol:DepositTest
[PASS] testDeepFuzz_deposit_singleUser(uint256) (runs: 100, μ: 286075, ~: 285987)
[PASS] testDeepFuzz_deposit_variableExchangeRate(uint256,uint256) (runs: 100, μ: 1547384, ~: 1553230)
[PASS] test_deposit_singleUser_oneToOne() (gas: 281109)
[PASS] test_deposit_twoUsers_oneToOne() (gas: 400197)
Test result: ok. 4 passed; 0 failed; finished in 295.79ms

Running 8 tests for tests/integration/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultTests
[PASS] test_triggerDefault_called() (gas: 622565)
[PASS] test_triggerDefault_feesAndFullRecovery() (gas: 327367)
[PASS] test_triggerDefault_feesAndPartialRecovery() (gas: 316946)
[PASS] test_triggerDefault_impaired() (gas: 641749)
[PASS] test_triggerDefault_impaired_feesAndFullRecovery() (gas: 364520)
[PASS] test_triggerDefault_impaired_onlyFeesRecovered() (gas: 345414)
[PASS] test_triggerDefault_latePayment() (gas: 521797)
[PASS] test_triggerDefault_onlyFeesRecovered() (gas: 303560)
Test result: ok. 8 passed; 0 failed; finished in 28.54ms

Running 3 tests for tests/integration/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notAuthorized() (gas: 53830)
[PASS] test_triggerDefault_notFactory() (gas: 54867)
[PASS] test_triggerDefault_notPoolManager() (gas: 57065)
Test result: ok. 3 passed; 0 failed; finished in 14.66ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:DepositWithPermitFailureTests
[PASS] test_depositWithPermit_invalidSignature() (gas: 481691)
[PASS] test_depositWithPermit_liquidityCapExceeded() (gas: 453801)
[PASS] test_depositWithPermit_notActive() (gas: 98986)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient() (gas: 393762)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 358846)
[PASS] test_depositWithPermit_protocolPaused() (gas: 144047)
Test result: ok. 6 passed; 0 failed; finished in 17.54ms

Running 4 tests for tests/integration/CallPrincipal.t.sol:CallPrincipalTests
[PASS] test_callPrincipal_impaired() (gas: 448895)
[PASS] test_callPrincipal_latePayment() (gas: 183187)
[PASS] test_callPrincipal_notFullPrincipal() (gas: 183021)
[PASS] test_callPrincipal_paymentOnTime() (gas: 182726)
Test result: ok. 4 passed; 0 failed; finished in 16.82ms

Running 5 tests for tests/integration/CloseLoan.t.sol:CloseLoanTests
[PASS] test_closeLoan_failIfLoanIsLate() (gas: 112861)
[PASS] test_closeLoan_failIfNotEnoughFundsSent() (gas: 214370)
[PASS] test_closeLoan_failIfNotLoan() (gas: 66869)
[PASS] test_closeLoan_failWithInsufficientApproval() (gas: 123833)
[PASS] test_closeLoan_success() (gas: 490220)
Test result: ok. 5 passed; 0 failed; finished in 33.07ms

Running 3 tests for tests/integration/Withdraw.t.sol:RequestWithdrawTests
[PASS] testDeepFuzz_requestWithdraw(uint256,uint256) (runs: 100, μ: 355448, ~: 356824)
[PASS] test_requestWithdraw() (gas: 327261)
[PASS] test_requestWithdraw_withApproval() (gas: 342141)
Test result: ok. 3 passed; 0 failed; finished in 85.30ms

Running 4 tests for tests/integration/Withdraw.t.sol:WithdrawFailureTests
[PASS] testDeepFuzz_withdraw(uint256,address,address) (runs: 100, μ: 63428, ~: 63428)
[PASS] test_withdraw_failIfNotPool() (gas: 46711)
[PASS] test_withdraw_failIfNotPoolManager() (gas: 19435)
[PASS] test_withdraw_zeroAssetInput() (gas: 65063)
Test result: ok. 4 passed; 0 failed; finished in 39.85ms

Running 2 tests for tests/integration/DepositAndMint.t.sol:DepositWithPermitTests
[PASS] testDeepFuzz_depositWithPermit_singleUser(uint256) (runs: 100, μ: 331726, ~: 331666)
[PASS] test_depositWithPermit_singleUser() (gas: 326658)
Test result: ok. 2 passed; 0 failed; finished in 101.16ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:MintFailureTests
[PASS] test_mint_insufficientApproval() (gas: 320766)
[PASS] test_mint_liquidityCapExceeded() (gas: 432328)
[PASS] test_mint_notActive() (gas: 102614)
[PASS] test_mint_privatePoolInvalidRecipient() (gas: 355260)
[PASS] test_mint_privatePoolInvalidRecipient_openPoolToPublic() (gas: 320411)
[PASS] test_mint_protocolPaused() (gas: 144539)
Test result: ok. 6 passed; 0 failed; finished in 15.33ms

Running 1 test for tests/fuzz/Withdraw.t.sol:WithdrawFuzzTests
[PASS] testDeepFuzz_withdraw_all(address,address,address,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 382486, ~: 375730)
Test result: ok. 1 passed; 0 failed; finished in 117.73ms

Running 1 test for tests/integration/Withdraw.t.sol:WithdrawOnPermissionedPool
[PASS] test_withdraw_withUnwhitelistedUser() (gas: 495499)
Test result: ok. 1 passed; 0 failed; finished in 13.41ms

Running 3 tests for tests/integration/Withdraw.t.sol:WithdrawScenarios
[PASS] test_withdrawals_cashInjection() (gas: 4916241)
[PASS] test_withdrawals_poorExchangeRates() (gas: 4604105)
[PASS] test_withdrawals_withUpdateAccounting() (gas: 4577739)
Test result: ok. 3 passed; 0 failed; finished in 46.22ms

Running 7 tests for tests/e2e/WithdrawManagerScenario.t.sol:WithdrawalManagerScenarioTests
[PASS] test_scenario_fundPayAndRefinanceLoanWithPartialRedemptions_removeSharesAndCloseLoan() (gas: 3683193)
[PASS] test_scenario_impairLoanAndRedeem_defaultLoanAndWithdraw() (gas: 2556269)
[PASS] test_scenario_impairLoanAndRedeem_removeImpairAndRedeem() (gas: 2761178)
[PASS] test_scenario_impairLoanAndRedeem_removeSharesRepayLoanAndRedeem() (gas: 2553446)
[PASS] test_scenario_impairLoanAndRedeem_repayLoanAndWithdraw() (gas: 2653068)
[PASS] test_scenario_impairLoanAndRedeem_startLiquidationAndRedeem_finishLiquidationAndRedeem() (gas: 3965349)
[PASS] test_scenario_multipleUsers_impairLoanAndRedeem_repayLoanAndRedeem() (gas: 21120904)
Test result: ok. 7 passed; 0 failed; finished in 123.41ms

Running 4 tests for tests/integration/DepositAndMint.t.sol:MintTest
[PASS] testDeepFuzz_mint_singleUser(uint256) (runs: 100, μ: 289519, ~: 289475)
[PASS] testDeepFuzz_mint_variableExchangeRate(uint256,uint256) (runs: 100, μ: 1588218, ~: 1587868)
[PASS] test_mint_singleUser_oneToOne() (gas: 284553)
[PASS] test_mint_twoUsers_oneToOne() (gas: 429133)
Test result: ok. 4 passed; 0 failed; finished in 305.71ms

Running 2 tests for tests/integration/ImpairLoan.t.sol:FixedTermLoanManagerImpairSuccessTests
[PASS] test_impairLoan_thenCancel() (gas: 910562)
[PASS] test_impairLoan_thenRepay() (gas: 920517)
Test result: ok. 2 passed; 0 failed; finished in 24.45ms

Running 6 tests for tests/integration/DepositAndMint.t.sol:MintWithPermitFailureTests
[PASS] test_mintWithPermit_insufficientPermit() (gas: 484269)
[PASS] test_mintWithPermit_liquidityCapExceeded() (gas: 499104)
[PASS] test_mintWithPermit_notActive() (gas: 107063)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient() (gas: 403843)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 368950)
[PASS] test_mintWithPermit_protocolPaused() (gas: 148177)
Test result: ok. 6 passed; 0 failed; finished in 21.97ms

Running 9 tests for tests/integration/ImpairLoan.t.sol:OpenTermLoanManagerImpairTests
[PASS] testFail_impairLoan_notLoanContract() (gas: 40511)
[PASS] test_impairLoan_early() (gas: 240676)
[PASS] test_impairLoan_governorAcl() (gas: 127168)
[PASS] test_impairLoan_late() (gas: 242167)
[PASS] test_impairLoan_loanInactive() (gas: 230471)
[PASS] test_impairLoan_notAuthorized() (gas: 59339)
[PASS] test_impairLoan_notLender() (gas: 38282)
[PASS] test_impairLoan_notLoanInLoanManager() (gas: 481101)
[PASS] test_impairLoan_protocolPaused() (gas: 52060)
Test result: ok. 9 passed; 0 failed; finished in 24.91ms

Running 9 tests for tests/integration/ImpairLoan.t.sol:OpenTermLoanManagerRemoveImpairmentTests
[PASS] test_removeLoanImpairment_early() (gas: 257880)
[PASS] test_removeLoanImpairment_late() (gas: 258929)
[PASS] test_removeLoanImpairment_late_withLateImpairment() (gas: 259115)
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 72600)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 93587)
[PASS] test_removeLoanImpairment_notLender() (gas: 38326)
[PASS] test_removeLoanImpairment_notLoan() (gas: 41091)
[PASS] test_removeLoanImpairment_poolDelegateAfterGovernor() (gas: 153256)
[PASS] test_removeLoanImpairment_protocolPaused() (gas: 52060)
Test result: ok. 9 passed; 0 failed; finished in 17.64ms

Running 2 tests for tests/integration/DepositAndMint.t.sol:MintWithPermitTests
[PASS] testDeepFuzz_mintWithPermit_singleUser(uint256) (runs: 100, μ: 332126, ~: 332118)
[PASS] test_mintWithPermit_singleUser() (gas: 330709)
Test result: ok. 2 passed; 0 failed; finished in 115.25ms

Running 8 tests for tests/integration/GetExpectedAmount.t.sol:GetExpectedAmountTests
[PASS] test_getExpectedAmount_currentPrice() (gas: 114828)
[PASS] test_getExpectedAmount_manualOverride() (gas: 90915)
[PASS] test_getExpectedAmount_oracleNotSet() (gas: 57950)
[PASS] test_getExpectedAmount_withMinRatio() (gas: 164219)
[PASS] test_getExpectedAmount_withSlippage() (gas: 164182)
[PASS] test_getExpectedAmount_withSlippageAndMinRatio_minRatioHigher() (gas: 198298)
[PASS] test_getExpectedAmount_withSlippageAndMinRatio_slippageHigher() (gas: 198244)
[PASS] test_getExpectedAmount_zeroAmount() (gas: 114878)
Test result: ok. 8 passed; 0 failed; finished in 1.98s

Running 3 tests for tests/integration/GetLatestPrice.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice_currentPrice() (gas: 74324)
[PASS] test_getLatestPrice_manualOverride() (gas: 48309)
[PASS] test_getLatestPrice_unknownAsset() (gas: 21528)
Test result: ok. 3 passed; 0 failed; finished in 14.92ms

Running 1 test for tests/protocol-upgrade/GlobalsMigration.t.sol:GlobalsMigration
[PASS] test_globals_upgrade() (gas: 1063954)
Test result: ok. 1 passed; 0 failed; finished in 227.12ms

Running 1 test for tests/protocol-upgrade/FTLoanV4ToV5.t.sol:FTLoansFromV4ToV5
[PASS] test_mainnet_upgradeLoansV4ToV5() (gas: 2228289)
Test result: ok. 1 passed; 0 failed; finished in 1.27s

Running 3 tests for tests/integration/FetchValuesFromLM.t.sol:LoanManagerIsLiquidationActiveGetterTests
[PASS] test_isLiquidationActive_afterLiquidation() (gas: 1104474)
[PASS] test_isLiquidationActive_beforeLiquidation() (gas: 15920)
[PASS] test_isLiquidationActive_duringLiquidation() (gas: 628253)
Test result: ok. 3 passed; 0 failed; finished in 16.03ms

Running 4 tests for tests/integration/FetchValuesFromPM.t.sol:PoolManagerGetterTests
[PASS] testDeepFuzz_getEscrowParams_shouldReturnValues(uint256) (runs: 100, μ: 22691, ~: 22156)
[PASS] test_addressGetters() (gas: 37876)
[PASS] test_hasSufficientCover_insufficientCover(uint256) (runs: 100, μ: 141208, ~: 141922)
[PASS] test_hasSufficientCover_sufficientCover(uint256) (runs: 100, μ: 153687, ~: 153759)
Test result: ok. 4 passed; 0 failed; finished in 85.58ms

Running 2 tests for tests/integration/ImpairLoan.t.sol:FixedTermLoanManagerImpairAndRefinanceTests
[PASS] test_impairLoan_earlyThenRefinance() (gas: 1224262)
[PASS] test_impairLoan_lateThenRefinance() (gas: 987440)
Test result: ok. 2 passed; 0 failed; finished in 23.94ms

Running 4 tests for tests/integration/ImpairLoan.t.sol:FixedTermLoanManagerImpairFailureTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 252528)
[PASS] test_impairLoan_notAuthorized() (gas: 57063)
[PASS] test_impairLoan_notLender() (gas: 37816)
[PASS] test_impairLoan_protocolPaused() (gas: 52038)
Test result: ok. 4 passed; 0 failed; finished in 20.28ms

Running 12 tests for tests/integration/Liquidation.t.sol:LoanLiquidationTests
[PASS] test_loanDefault_fullCover_noCollateral_noImpairment() (gas: 1525975)
[PASS] test_loanDefault_fullCover_noCollateral_withImpairment() (gas: 1614056)
[PASS] test_loanDefault_fullCover_withCollateral_noImpairment() (gas: 2546886)
[PASS] test_loanDefault_fullCover_withCollateral_withImpairment() (gas: 2579238)
[PASS] test_loanDefault_noCover_noCollateral_noImpairment() (gas: 1427540)
[PASS] test_loanDefault_noCover_noCollateral_withImpairment() (gas: 1519800)
[PASS] test_loanDefault_noCover_withCollateral_noImpairment() (gas: 2462353)
[PASS] test_loanDefault_noCover_withCollateral_withImpairment() (gas: 2496803)
[PASS] test_loanDefault_partialCover_noCollateral_noImpairment() (gas: 1525608)
[PASS] test_loanDefault_partialCover_noCollateral_withImpairment() (gas: 1614054)
[PASS] test_loanDefault_partialCover_withCollateral_noImpairment() (gas: 2546457)
[PASS] test_loanDefault_partialCover_withCollateral_withImpairment() (gas: 2579237)
Test result: ok. 12 passed; 0 failed; finished in 54.20ms

Running 5 tests for tests/integration/LoanManagerGetters.t.sol:LoanManagerGetterTests
[PASS] test_loanManagerGetters_addresses() (gas: 21380)
[PASS] test_loanManagerGetters_liquidationInformation() (gas: 1151936)
[PASS] test_loanManagerGetters_paymentInformation() (gas: 29877)
[PASS] test_loanManagerGetters_sortedPayments() (gas: 1317035)
[PASS] test_loanManagerGetters_uints() (gas: 32847)
Test result: ok. 5 passed; 0 failed; finished in 17.91ms

Running 3 tests for tests/integration/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_failIfNotLoan() (gas: 69767)
[PASS] test_makePayment_failWithTransferFailed() (gas: 234851)
[PASS] test_makePayment_failWithTransferFromFailed() (gas: 143646)
Test result: ok. 3 passed; 0 failed; finished in 15.09ms

Running 9 tests for tests/integration/MakePayment.t.sol:MakePaymentOpenTermFailureTests
[PASS] test_makePayment_inactiveLoan() (gas: 477855)
[PASS] test_makePayment_invalidPrincipalIncrease() (gas: 55540)
[PASS] test_makePayment_notLoan() (gas: 520964)
[PASS] test_makePayment_tooLittlePrincipal() (gas: 139006)
[PASS] test_makePayment_tooMuchPrincipal() (gas: 43991)
[PASS] test_makePayment_transferFailed() (gas: 84745)
[PASS] test_makePayment_transferToPoolBoundary() (gas: 261561)
[PASS] test_makePayment_transferToPoolDelegateBoundary() (gas: 309994)
[PASS] test_makePayment_transferToTreasuryBoundary() (gas: 396694)
Test result: ok. 9 passed; 0 failed; finished in 17.19ms

Running 2 tests for tests/fuzz/OpenTermFuzz.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_otlFuzzedSetup_makePayment(uint256) (runs: 100, μ: 9983533, ~: 10025330)
[PASS] testFuzz_otlFuzzedSetup_triggerDefault(uint256) (runs: 100, μ: 9943922, ~: 10002018)
Test result: ok. 2 passed; 0 failed; finished in 4.13s

Running 2 tests for tests/fuzz/Call.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_call_otl(uint256) (runs: 100, μ: 11243289, ~: 11268937)
[PASS] testFuzz_removeCall_otl(uint256) (runs: 100, μ: 10751933, ~: 10827403)
Test result: ok. 2 passed; 0 failed; finished in 4.09s

Running 5 tests for tests/integration/CallPrincipal.t.sol:CallPrincipalFailureTests
[PASS] test_callPrincipal_invalidAmount_boundary() (gas: 516067)
[PASS] test_callPrincipal_loanActive() (gas: 56539)
[PASS] test_callPrincipal_notLender() (gas: 38696)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 51519)
[PASS] test_callPrincipal_paused() (gas: 52377)
Test result: ok. 5 passed; 0 failed; finished in 16.83ms

Running 5 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxMintTests
[PASS] testDeepFuzz_maxMint_exchangeRateGtOne(uint256,uint256,uint256) (runs: 100, μ: 382872, ~: 382779)
[PASS] testDeepFuzz_maxMint_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 226175, ~: 226193)
[PASS] test_maxMint_closedPool() (gas: 233747)
[PASS] test_maxMint_exchangeRateGtOne() (gas: 370959)
[PASS] test_maxMint_totalAssetsIncrease() (gas: 218922)
Test result: ok. 5 passed; 0 failed; finished in 123.36ms

Running 3 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxRedeemTests
[PASS] test_maxRedeem_lockedShares_inExitWindow() (gas: 430483)
[PASS] test_maxRedeem_lockedShares_notInExitWindow() (gas: 419448)
[PASS] test_maxRedeem_noLockedShares_notInExitWindow() (gas: 261862)
Test result: ok. 3 passed; 0 failed; finished in 18.31ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxWithdrawTests
[PASS] testDeepFuzz_maxWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 421631, ~: 421026)
[PASS] test_maxWithdraw_lockedShares_inExitWindow() (gas: 416311)
[PASS] test_maxWithdraw_lockedShares_notInExitWindow() (gas: 412483)
[PASS] test_maxWithdraw_noLockedShares_notInExitWindow() (gas: 255058)
Test result: ok. 4 passed; 0 failed; finished in 75.74ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewDepositTests
[PASS] test_previewDeposit_multipleUsers() (gas: 459108)
[PASS] test_previewDeposit_multipleUsers_changeTotalAssets() (gas: 482792)
[PASS] test_previewDeposit_nonZeroTotalSupply() (gas: 271995)
[PASS] test_previewDeposit_zeroTotalSupply() (gas: 12511)
Test result: ok. 4 passed; 0 failed; finished in 15.34ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewMintTests
[PASS] test_previewMint_multipleUsers() (gas: 460057)
[PASS] test_previewMint_multipleUsers_changeTotalAssets() (gas: 483760)
[PASS] test_previewMint_nonZeroTotalSupply() (gas: 273069)
[PASS] test_previewMint_zeroTotalSupply() (gas: 12363)
Test result: ok. 4 passed; 0 failed; finished in 19.17ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewRedeemTests
[PASS] test_previewRedeem_invalidShares() (gas: 405036)
[PASS] test_previewRedeem_lockedShares_inExitWindow() (gas: 439269)
[PASS] test_previewRedeem_lockedShares_notInExitWindow() (gas: 409423)
[PASS] test_previewRedeem_noLockedShares_notInExitWindow() (gas: 37023)
Test result: ok. 4 passed; 0 failed; finished in 16.16ms

Running 6 tests for tests/integration/PoolAccountingViewFunctions.t.sol:PreviewWithdrawTests
[PASS] testDeepFuzz_previewWithdraw(uint256) (runs: 100, μ: 35062, ~: 35062)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 411690, ~: 411331)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_notInExitWindow(uint256) (runs: 100, μ: 411706, ~: 411158)
[PASS] test_previewWithdraw() (gas: 250010)
[PASS] test_previewWithdraw_zeroAssetsWithDeposit() (gas: 250010)
[PASS] test_previewWithdraw_zeroAssetsWithoutDeposit() (gas: 34931)
Test result: ok. 6 passed; 0 failed; finished in 130.98ms

Running 2 tests for tests/fuzz/Impair.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_impair_otl(uint256) (runs: 100, μ: 11338100, ~: 11272555)
[PASS] testFuzz_removeImpairment_otl(uint256) (runs: 100, μ: 10757460, ~: 10757565)
Test result: ok. 2 passed; 0 failed; finished in 2.49s

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapDepositWithPermitTests
[PASS] testFuzz_depositWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 375983, ~: 376238)
[PASS] testFuzz_depositWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 240465, ~: 240370)
[PASS] testFuzz_depositWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 544231, ~: 543618)
[PASS] test_depositWithPermit_exactBootstrapMintAmount() (gas: 349790)
[PASS] test_depositWithPermit_gtBootstrapMintAmount() (gas: 370467)
[PASS] test_depositWithPermit_ltBootstrapMintAmount() (gas: 283584)
[PASS] test_depositWithPermit_secondDepositorGetsCorrectShares() (gas: 538927)
Test result: ok. 7 passed; 0 failed; finished in 386.06ms

Running 1 test for tests/fuzz/Redeem.t.sol:RedeemFuzzTests
[PASS] testDeepFuzz_redeem_all(address[3],uint256[8]) (runs: 100, μ: 879250, ~: 904449)
Test result: ok. 1 passed; 0 failed; finished in 156.66ms

Running 3 tests for tests/integration/Redeem.t.sol:RedeemIntegrationTests
[PASS] test_redeem_oneLPWithImpairedLoan() (gas: 1834085)
[PASS] test_redeem_twoLPSWithImpairedLoanAndTriggerDefault() (gas: 1981496)
[PASS] test_redeem_twoLPsWithImpairedLoan() (gas: 2149639)
Test result: ok. 3 passed; 0 failed; finished in 31.34ms

Running 3 tests for tests/invariants/OpenTermInvariants.t.sol:OpenTermInvariants
[PASS] invariant_openTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_openTermLoanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_openTermLoan_A_B_C_D_E_F_G_H_I_openTermLoanManager_A_B_C_D_F_H_I_J() (runs: 10, calls: 1000, reverts: 0)
Test result: ok. 3 passed; 0 failed; finished in 949.92ms

Running 6 tests for tests/integration/Redeem.t.sol:RedeemTests
[PASS] testDeepFuzz_redeem_singleUser_fullLiquidity_oneToOne(uint256,uint256) (runs: 100, μ: 534904, ~: 532994)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem() (gas: 545320)
[PASS] test_redeem_singleUser_fullLiquidity_oneToOne() (gas: 541745)
[PASS] test_redeem_singleUser_noLiquidity() (gas: 1812136)
[PASS] test_redeem_singleUser_noLiquidity_notOwner() (gas: 1873553)
[PASS] test_redeem_singleUser_withApprovals() (gas: 603628)
Test result: ok. 6 passed; 0 failed; finished in 119.13ms

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapMintTests
[PASS] testFuzz_mint_gtBootstrapMintAmount(uint256) (runs: 100, μ: 333890, ~: 334130)
[PASS] testFuzz_mint_ltBootstrapMintAmount(uint256) (runs: 100, μ: 244574, ~: 245067)
[PASS] testFuzz_mint_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 485784, ~: 485192)
[PASS] test_mint_exactBootstrapMintAmount() (gas: 307688)
[PASS] test_mint_gtBootstrapMintAmount() (gas: 328343)
[PASS] test_mint_ltBootstrapMintAmount() (gas: 239406)
[PASS] test_mint_secondDepositorGetsCorrectShares() (gas: 480477)
Test result: ok. 7 passed; 0 failed; finished in 223.38ms

Running 4 tests for tests/integration/Redeem.t.sol:RequestRedeemFailureTests
[PASS] test_requestRedeem_failIfAlreadyLockedShares() (gas: 314017)
[PASS] test_requestRedeem_failIfInsufficientApproval() (gas: 133372)
[PASS] test_requestRedeem_failIfNotPM() (gas: 18940)
[PASS] test_requestRedeem_failIfNotPool() (gas: 46284)
Test result: ok. 4 passed; 0 failed; finished in 13.69ms

Running 6 tests for tests/integration/Redeem.t.sol:RequestRedeemTests
[PASS] testDeepFuzz_requestRedeem(uint256,uint256) (runs: 100, μ: 453541, ~: 454646)
[PASS] test_requestRedeem() (gas: 423648)
[PASS] test_requestRedeem_refresh() (gas: 507405)
[PASS] test_requestRedeem_refresh_notOwnerAndNoApproval() (gas: 467284)
[PASS] test_requestRedeem_refresh_notOwnerWithApproval() (gas: 540348)
[PASS] test_requestRedeem_withApproval() (gas: 450797)
Test result: ok. 6 passed; 0 failed; finished in 92.28ms

Running 13 tests for tests/integration/Refinance.t.sol:AcceptNewTermsFailureTests
[PASS] testFail_acceptNewTerms_failIfNotValidLoanManager() (gas: 79196)
[PASS] test_acceptNewTerms_failIfDeadlineExpired() (gas: 216706)
[PASS] test_acceptNewTerms_failIfInsufficientCover() (gas: 269153)
[PASS] test_acceptNewTerms_failIfLockedLiquidity() (gas: 496176)
[PASS] test_acceptNewTerms_failIfNotLender() (gas: 41895)
[PASS] test_acceptNewTerms_failIfNotPoolDelegate() (gas: 60269)
[PASS] test_acceptNewTerms_failIfProtocolIsPaused() (gas: 63925)
[PASS] test_acceptNewTerms_failIfRefinanceCallFails() (gas: 343340)
[PASS] test_acceptNewTerms_failIfRefinanceMismatch() (gas: 158962)
[PASS] test_acceptNewTerms_failWithFailedTransfer() (gas: 287073)
[PASS] test_acceptNewTerms_failWithInsufficientCollateral() (gas: 616584)
[PASS] test_acceptNewTerms_failWithInvalidRefinancer() (gas: 243370)
[PASS] test_acceptNewTerms_failWithUnexpectedFunds() (gas: 607582)
Test result: ok. 13 passed; 0 failed; finished in 27.86ms

Running 3 tests for tests/integration/Refinance.t.sol:RefinanceOpenTermLoan
[PASS] test_refinance_calledLoan_withoutPrincipalChange() (gas: 791863)
[PASS] test_refinance_early_increasePrincipal() (gas: 791387)
[PASS] test_refinance_late_decreasePrincipal() (gas: 704712)
Test result: ok. 3 passed; 0 failed; finished in 21.91ms

Running 5 tests for tests/integration/Refinance.t.sol:RefinanceTestsSingleLoan
[PASS] test_refinance_onLateLoan_changePaymentInterval() (gas: 1149966)
[PASS] test_refinance_onLoanPaymentDueDate_changeInterestRate() (gas: 1140682)
[PASS] test_refinance_onLoanPaymentDueDate_changePaymentInterval() (gas: 1140598)
[PASS] test_refinance_onLoanPaymentDueDate_changeToAmortized() (gas: 1143391)
[PASS] test_refinance_onLoanPaymentDueDate_increasePrincipal() (gas: 1201983)
Test result: ok. 5 passed; 0 failed; finished in 29.09ms

Running 7 tests for tests/integration/BootstrapMintAndDeposit.t.sol:BootstrapDepositTests
[PASS] testFuzz_deposit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 330388, ~: 330711)
[PASS] testFuzz_deposit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 242539, ~: 241865)
[PASS] testFuzz_deposit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 457090, ~: 456439)
[PASS] test_deposit_exactBootstrapMintAmount() (gas: 304204)
[PASS] test_deposit_gtBootstrapMintAmount() (gas: 324901)
[PASS] test_deposit_ltBootstrapMintAmount() (gas: 237550)
[PASS] test_deposit_secondDepositorGetsCorrectShares() (gas: 451703)
Test result: ok. 7 passed; 0 failed; finished in 202.00ms

Running 2 tests for tests/integration/PoolAccountingViewFunctions.t.sol:BalanceOfAssetsTests
[PASS] testDeepFuzz_balanceOfAssets(uint256,uint256,uint256) (runs: 100, μ: 418757, ~: 418600)
[PASS] test_balanceOfAssets() (gas: 406751)
Test result: ok. 2 passed; 0 failed; finished in 92.23ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:ConvertToAssetsTests
[PASS] test_convertToAssets_multipleUsers() (gas: 458906)
[PASS] test_convertToAssets_multipleUsers_changeTotalAssets() (gas: 482592)
[PASS] test_convertToAssets_singleUser() (gas: 271654)
[PASS] test_convertToAssets_zeroTotalSupply() (gas: 12237)
Test result: ok. 4 passed; 0 failed; finished in 15.00ms

Running 4 tests for tests/integration/Pause.t.sol:PauseTests
[PASS] test_contractPause() (gas: 5714400)
[PASS] test_functionUnpauseAfterContractPause() (gas: 49477527)
[PASS] test_functionUnpauseAfterProtocolPause() (gas: 48622608)
[PASS] test_globalPause() (gas: 8601682)
Test result: ok. 4 passed; 0 failed; finished in 326.71ms

Running 4 tests for tests/integration/PoolAccountingViewFunctions.t.sol:ConvertToSharesTests
[PASS] test_convertToShares_multipleUsers() (gas: 458937)
[PASS] test_convertToShares_multipleUsers_changeTotalAssets() (gas: 482657)
[PASS] test_convertToShares_singleUser() (gas: 271802)
[PASS] test_convertToShares_zeroTotalSupply() (gas: 12274)
Test result: ok. 4 passed; 0 failed; finished in 14.94ms

Running 3 tests for tests/integration/Liquidation.t.sol:FinishLiquidationFailureTests
[PASS] test_finishLiquidation_failIfLiquidationNotActive() (gas: 102914)
[PASS] test_finishLiquidation_failIfNotPD() (gas: 51341)
[PASS] test_finishLiquidation_failIfNotPoolManager() (gas: 54784)
Test result: ok. 3 passed; 0 failed; finished in 16.04ms

Running 3 tests for tests/integration/PoolAccountingViewFunctions.t.sol:MaxDepositTests
[PASS] testDeepFuzz_maxDeposit_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 216560, ~: 216056)
[PASS] test_maxDeposit_closedPool() (gas: 220747)
[PASS] test_maxDeposit_totalAssetsIncrease() (gas: 209574)
Test result: ok. 3 passed; 0 failed; finished in 48.31ms

Running 3 tests for tests/integration/Redeem.t.sol:MultiUserRedeemTests
[PASS] test_redeem_partialLiquidity_sameCash_differentExchangeRate() (gas: 2547073)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate() (gas: 2421952)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate_exposeRounding() (gas: 4784962)
Test result: ok. 3 passed; 0 failed; finished in 32.81ms

Running 9 tests for tests/integration/Redeem.t.sol:RedeemFailureTests
[PASS] test_redeem_failIfNoApprove() (gas: 255501)
[PASS] test_redeem_failIfNoBalanceOnWM() (gas: 362618)
[PASS] test_redeem_failIfNoRequest() (gas: 85556)
[PASS] test_redeem_failIfNotInWindow() (gas: 287721)
[PASS] test_redeem_failIfNotPool() (gas: 46733)
[PASS] test_redeem_failIfNotPoolManager() (gas: 19480)
[PASS] test_redeem_failWithInsufficientApproval() (gas: 342544)
[PASS] test_redeem_failWithInvalidAmountOfShares() (gas: 282085)
[PASS] test_redeem_failWithZeroReceiver() (gas: 318774)
Test result: ok. 9 passed; 0 failed; finished in 16.75ms

Running 1 test for tests/protocol-upgrade/ProtocolUpgrade.t.sol:ProtocolUpgradeTest
[PASS] test_mainnet_upgradeProtocol() (gas: 54728112)
Test result: ok. 1 passed; 0 failed; finished in 65.90ms

Running 11 tests for tests/fuzz/PoolViewFunctionsFuzzTest.t.sol:PoolViewFunctionsFuzzTests
[PASS] testFuzz_convertToAssets_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 313443, ~: 313707)
[PASS] testFuzz_convertToAssets_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 14942, ~: 14527)
[PASS] testFuzz_convertToExitShares(uint256,uint256,uint256,uint256,uint256) (runs: 100, μ: 347527, ~: 347620)
[PASS] testFuzz_convertToShares_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 313546, ~: 313704)
[PASS] testFuzz_convertToShares_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 15170, ~: 14569)
[PASS] testFuzz_getTotalAssetsFromPM(uint256,uint256) (runs: 100, μ: 124273, ~: 124389)
[PASS] testFuzz_getUnrealizedLossesFromPM(uint256) (runs: 100, μ: 109009, ~: 108485)
[PASS] testFuzz_previewDeposit_whenTotalSupplyExists(uint256,uint256) (runs: 100, μ: 263332, ~: 263621)
[PASS] testFuzz_previewDeposit_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 15104, ~: 14609)
[PASS] testFuzz_previewMint_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 100, μ: 314317, ~: 314475)
[PASS] testFuzz_previewMint_whenTotalSupplyIsZero(uint256) (runs: 100, μ: 15005, ~: 14590)
Test result: ok. 11 passed; 0 failed; finished in 507.49ms

Running 1 test for tests/fuzz/ClosePoolFuzz.t.sol:ClosePoolFuzz
[PASS] testFuzz_fuzzedSetup_closePool(uint256) (runs: 100, μ: 20727170, ~: 20232138)
Test result: ok. 1 passed; 0 failed; finished in 6.07s

Running 11 tests for tests/e2e/PoolScenarios.t.sol:PoolScenarioTests
[PASS] testFuzz_poolScenarios_OTLWithBigPaymentInterval(uint256) (runs: 100, μ: 1045315, ~: 1045143)
[PASS] testFuzz_poolScenarios_exposeAccountedInterestDust(uint24,uint24) (runs: 100, μ: 1767997, ~: 1775886)
[PASS] testFuzz_poolScenarios_multipleOTLWithBigPaymentInterval(uint256,uint256,uint256) (runs: 100, μ: 39194405, ~: 39194708)
[PASS] test_poolScenario_fundLoanAndNeverTouchIt() (gas: 5897025)
[PASS] test_poolScenario_impairLoanWithLatePaymentAndRefinance() (gas: 2655066)
[PASS] test_poolScenario_loanWithVeryHighInterestRate() (gas: 1592445)
[PASS] test_poolScenario_loanWithZeroInterestRate() (gas: 2136350)
[PASS] test_poolScenario_loanWithZeroInterestRateAndDefaultWithCover() (gas: 1590740)
[PASS] test_poolScenarios_refinanceATwoPeriodsLateLoan() (gas: 2249891)
[PASS] test_poolScenarios_refinanceLateLoanAndDefault() (gas: 2019073)
[PASS] test_poolScenarios_stressTestAdvanceGlobalPaymentAccounting() (gas: 170615648)
Test result: ok. 11 passed; 0 failed; finished in 7.88s

Running 27 tests for tests/invariants/DefaultsInvariants.t.sol:DefaultsInvariants
[PASS] invariant_fixedTermLoanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoan_A_B_fixedTermLoanManager_M_N() (runs: 10, calls: 1000, reverts: 0)
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
Test result: ok. 27 passed; 0 failed; finished in 13.82s

Running 27 tests for tests/invariants/ImpairInvariants.t.sol:ImpairInvariants
[PASS] invariant_fixedTermLoanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoan_A_B_fixedTermLoanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
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
Test result: ok. 27 passed; 0 failed; finished in 38.19s

Running 30 tests for tests/invariants/BasicInvariants.t.sol:BasicInvariants
[PASS] invariant_fixedTermLoanManager_A() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_B() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_C() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_D() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_E() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_F() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_G() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_H() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_I() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_J() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoanManager_K() (runs: 10, calls: 1000, reverts: 0)
[PASS] invariant_fixedTermLoan_A_B_C_fixedTermLoanManager_L_M_N() (runs: 10, calls: 1000, reverts: 0)
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
Test result: ok. 30 passed; 0 failed; finished in 42.55s

Running 1 test for tests/protocol-upgrade/Lifecycles.t.sol:FixedTermLifecycle
[PASS] test_fixedTermLifecycle() (gas: 182847904)
Test result: ok. 1 passed; 0 failed; finished in 406.91s

Running 1 test for tests/protocol-upgrade/Lifecycles.t.sol:OpenTermOnboardLifecycle
[PASS] test_openTermOnboardLifecycle() (gas: 263370105)
Test result: ok. 1 passed; 0 failed; finished in 402.61s

Running 1 test for tests/protocol-upgrade/Lifecycles.t.sol:OpenAndFixedTermLifecycle
[PASS] test_openAndFixedTermLifecycle() (gas: 334090133)
Test result: ok. 1 passed; 0 failed; finished in 407.95s
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

# `fixed-term-loan (v5.0.1)`

```
Running 2 tests for tests/InitializerAndMigrator.t.sol:MapleLoanInitializerAndMigratorTests
[PASS] test_initializer_setters() (gas: 89831)
[PASS] test_migration_ratesChange() (gas: 104275)
Test result: ok. 2 passed; 0 failed; finished in 4.66ms

Running 4 tests for tests/MapleLoanFeeManager.t.sol:PayOriginationFeesTests
[PASS] test_payOriginationFees() (gas: 304424)
[PASS] test_payOriginationFees_insufficientFunds_poolDelegate() (gas: 167097)
[PASS] test_payOriginationFees_insufficientFunds_treasury() (gas: 197140)
[PASS] test_payOriginationFees_zeroTreasury() (gas: 198162)
Test result: ok. 4 passed; 0 failed; finished in 4.98ms

Running 3 tests for tests/MapleLoan.t.sol:MapleLoanRoleTests
[PASS] test_transferBorrowerRole() (gas: 180471)
[PASS] test_transferBorrowerRole_failIfInvalidBorrower() (gas: 77496)
[PASS] test_transferLenderRole() (gas: 291194)
Test result: ok. 3 passed; 0 failed; finished in 5.16ms

Running 1 test for tests/Refinancer.t.sol:RefinancerInterestTests
[PASS] test_acceptNewTerms_makePayment_withRefinanceInterest() (gas: 5405192)
Test result: ok. 1 passed; 0 failed; finished in 5.90ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RepossessTests
[PASS] test_repossess() (gas: 143815)
[PASS] test_repossess_beforePaymentDue() (gas: 54249)
[PASS] test_repossess_collateralTransferFailed() (gas: 207861)
[PASS] test_repossess_fundsTransferFailed() (gas: 238417)
[PASS] test_repossess_onGracePeriod() (gas: 54256)
[PASS] test_repossess_onPaymentDue() (gas: 54115)
[PASS] test_repossess_withinGracePeriod() (gas: 54211)
Test result: ok. 7 passed; 0 failed; finished in 7.33ms

Running 2 tests for tests/MapleLoanFeeManager.t.sol:PayServiceFeesTests
[PASS] test_payServiceFees() (gas: 239653)
[PASS] test_payServiceFees_zeroTreasury() (gas: 209439)
Test result: ok. 2 passed; 0 failed; finished in 2.33ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:UpdateFeeTerms_SetterTests
[PASS] test_updateDelegateFeeTerms() (gas: 105747)
Test result: ok. 1 passed; 0 failed; finished in 2.19ms

Running 1 test for tests/Refinancer.t.sol:RefinancerMiscellaneousTests
[PASS] test_refinance_invalidRefinancer() (gas: 5174106)
Test result: ok. 1 passed; 0 failed; finished in 3.65ms

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_SkimTests
[PASS] test_skimCollateralAsset() (gas: 76920)
[PASS] test_skimFundsAsset() (gas: 76975)
[PASS] test_skim_otherAsset() (gas: 791886)
Test result: ok. 3 passed; 0 failed; finished in 13.20ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:UpdatePlatformServiceFeeTests
[PASS] test_updatePlatformServiceFee() (gas: 1661262)
Test result: ok. 1 passed; 0 failed; finished in 6.07ms

Running 3 tests for tests/MapleLoanScenarios.t.sol:MapleLoanScenariosTests
[PASS] test_scenario_fullyAmortized() (gas: 5387932)
[PASS] test_scenario_interestOnly() (gas: 5388054)
[PASS] test_scenario_lateLoanRefinanceInterest() (gas: 5226226)
Test result: ok. 3 passed; 0 failed; finished in 5.19ms

Running 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_AcceptNewTermsTests
[PASS] test_acceptNewTerms() (gas: 155547)
[PASS] test_acceptNewTerms_afterDeadline() (gas: 76044)
[PASS] test_acceptNewTerms_callFailed() (gas: 111555)
[PASS] test_acceptNewTerms_commitmentMismatch_emptyCallsArray() (gas: 72232)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedCalls() (gas: 73083)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 72894)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 72763)
[PASS] test_acceptNewTerms_insufficientCollateral() (gas: 315469)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 73234)
Test result: ok. 9 passed; 0 failed; finished in 3.02ms

Running 73 tests for tests/MapleLoan.t.sol:MapleLoanTests
[PASS] test_acceptBorrower_acl() (gas: 51750)
[PASS] test_acceptBorrower_failWhenPaused() (gas: 29573)
[PASS] test_acceptLender_acl() (gas: 50060)
[PASS] test_acceptLender_failWhenPaused() (gas: 29638)
[PASS] test_acceptNewTerms() (gas: 1031225)
[PASS] test_acceptNewTerms_acl() (gas: 980809)
[PASS] test_acceptNewTerms_failWhenPaused() (gas: 30347)
[PASS] test_closeLoan_failWhenPaused() (gas: 29795)
[PASS] test_closeLoan_pullPatternAsBorrower() (gas: 944772)
[PASS] test_closeLoan_pullPatternAsNonBorrower() (gas: 947793)
[PASS] test_closeLoan_pullPatternUsingDrawable() (gas: 947765)
[PASS] test_closeLoan_pushPatternAsBorrower() (gas: 961469)
[PASS] test_closeLoan_pushPatternAsNonBorrower() (gas: 962468)
[PASS] test_closeLoan_pushPatternUsingDrawable() (gas: 920680)
[PASS] test_drawdownFunds_acl() (gas: 902011)
[PASS] test_drawdownFunds_failWhenPaused() (gas: 29932)
[PASS] test_drawdownFunds_pullPatternForCollateral() (gas: 1773448)
[PASS] test_drawdownFunds_pushPatternForCollateral() (gas: 1756409)
[PASS] test_drawdownFunds_withoutAdditionalCollateralRequired() (gas: 1601570)
[PASS] test_excessCollateral_varyCollateral() (gas: 138216)
[PASS] test_excessCollateral_varyDrawableFunds() (gas: 126736)
[PASS] test_excessCollateral_varyPrincipal() (gas: 88803)
[PASS] test_fundLoan_failWhenPaused() (gas: 29705)
[PASS] test_fundLoan_pushPattern() (gas: 1051154)
[PASS] test_getAdditionalCollateralRequiredFor_varyAmount() (gas: 120528)
[PASS] test_getAdditionalCollateralRequiredFor_varyCollateralRequired() (gas: 110128)
[PASS] test_getAdditionalCollateralRequiredFor_varyDrawableFunds() (gas: 112228)
[PASS] test_getAdditionalCollateralRequiredFor_varyPrincipal() (gas: 132674)
[PASS] test_impairLoan() (gas: 78842)
[PASS] test_impairLoan_acl() (gas: 91475)
[PASS] test_impairLoan_failWhenPaused() (gas: 29634)
[PASS] test_impairLoan_lateLoan() (gas: 78870)
[PASS] test_makePayment_failWhenPaused() (gas: 29852)
[PASS] test_makePayment_pullPatternAsBorrower() (gas: 995962)
[PASS] test_makePayment_pullPatternAsNonBorrower() (gas: 998243)
[PASS] test_makePayment_pullPatternUsingDrawable() (gas: 1026547)
[PASS] test_makePayment_pushPatternAsBorrower() (gas: 997619)
[PASS] test_makePayment_pushPatternAsNonBorrower() (gas: 997898)
[PASS] test_makePayment_pushPatternUsingDrawable() (gas: 999502)
[PASS] test_migrate_acl() (gas: 86584)
[PASS] test_migrate_failWhenPaused() (gas: 30250)
[PASS] test_postCollateral_failWhenPaused() (gas: 29757)
[PASS] test_postCollateral_pullPattern() (gas: 868920)
[PASS] test_postCollateral_pushPattern() (gas: 825858)
[PASS] test_proposeNewTerms() (gas: 106373)
[PASS] test_proposeNewTerms_acl() (gas: 123901)
[PASS] test_proposeNewTerms_failWhenPaused() (gas: 30382)
[PASS] test_proposeNewTerms_invalidDeadline() (gas: 123946)
[PASS] test_rejectNewTerms_acl() (gas: 127896)
[PASS] test_rejectNewTerms_failWhenPaused() (gas: 30435)
[PASS] test_removeCollateral_acl() (gas: 861116)
[PASS] test_removeCollateral_failWhenPaused() (gas: 29756)
[PASS] test_removeLoanImpairment_acl() (gas: 72173)
[PASS] test_removeLoanImpairment_failWhenPaused() (gas: 29658)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 30656)
[PASS] test_removeLoanImpairment_pastDate() (gas: 52075)
[PASS] test_removeLoanImpairment_success() (gas: 58056)
[PASS] test_repossess_acl() (gas: 841153)
[PASS] test_repossess_failWhenPaused() (gas: 29929)
[PASS] test_returnFunds_failWhenPaused() (gas: 29790)
[PASS] test_returnFunds_pullPattern() (gas: 869007)
[PASS] test_returnFunds_pushPattern() (gas: 825914)
[PASS] test_setImplementation_acl() (gas: 107226)
[PASS] test_setImplementation_failWhenPaused() (gas: 29751)
[PASS] test_setPendingBorrower_acl() (gas: 92933)
[PASS] test_setPendingBorrower_failWhenPaused() (gas: 29686)
[PASS] test_setPendingLender_acl() (gas: 70263)
[PASS] test_setPendingLender_failWhenPaused() (gas: 29775)
[PASS] test_skim_failWhenPaused() (gas: 29939)
[PASS] test_upgrade_acl_noAuth() (gas: 3631758)
[PASS] test_upgrade_acl_noAuth_asBorrower() (gas: 3634333)
[PASS] test_upgrade_acl_securityAdmin() (gas: 3663970)
[PASS] test_upgrade_failWhenPaused() (gas: 29920)
Test result: ok. 73 passed; 0 failed; finished in 15.48ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetCollateralRequiredForTests
[PASS] test_getCollateralRequiredFor() (gas: 12282)
Test result: ok. 1 passed; 0 failed; finished in 1.29ms

Running 2 tests for tests/Payments.t.sol:ClosingTests
[PASS] test_payments_closing_flatRate_case1() (gas: 1223634)
[PASS] test_payments_closing_flatRate_case2() (gas: 1110264)
Test result: ok. 2 passed; 0 failed; finished in 4.39ms

Running 2 tests for tests/Payments.t.sol:FullyAmortizedPaymentsTests
[PASS] test_payments_fullyAmortized_case1() (gas: 1413222)
[PASS] test_payments_fullyAmortized_case2() (gas: 1413169)
Test result: ok. 2 passed; 0 failed; finished in 6.11ms

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInstallmentTests
[PASS] test_getInstallment_edgeCases() (gas: 15000)
[PASS] test_getInstallment_genericFuzzing(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 10937, ~: 11006)
[PASS] test_getInstallment_withFixtures() (gas: 8769)
Test result: ok. 3 passed; 0 failed; finished in 12.41ms

Running 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ReturnFundsTests
[PASS] test_returnFunds(uint256) (runs: 256, μ: 117286, ~: 119331)
[PASS] test_returnFundsCollateralAsset() (gas: 814157)
Test result: ok. 2 passed; 0 failed; finished in 27.79ms

Running 2 tests for tests/Payments.t.sol:InterestOnlyPaymentsTests
[PASS] test_payments_interestOnly_case1() (gas: 1429056)
[PASS] test_payments_interestOnly_case2() (gas: 1429105)
Test result: ok. 2 passed; 0 failed; finished in 6.12ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInterestTests
[PASS] test_getInterest() (gas: 7966)
Test result: ok. 1 passed; 0 failed; finished in 510.54µs

Running 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ScaledExponentTests
[PASS] test_scaledExponent_setOne() (gas: 22590)
[PASS] test_scaledExponent_setTwo() (gas: 36769)
Test result: ok. 2 passed; 0 failed; finished in 756.96µs

Running 5 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RejectNewTermsTests
[PASS] test_rejectNewTerms() (gas: 55611)
[PASS] test_rejectNewTerms_commitmentMismatch_emptyCallsArray() (gas: 67664)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedCalls() (gas: 68537)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 68468)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 467314)
Test result: ok. 5 passed; 0 failed; finished in 1.22ms

Running 2 tests for tests/Payments.t.sol:PartiallyAmortizedPaymentsTests
[PASS] test_payments_partiallyAmortized_case1() (gas: 1429072)
[PASS] test_payments_partiallyAmortized_case2() (gas: 1429107)
Test result: ok. 2 passed; 0 failed; finished in 6.22ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetNextPaymentBreakdownTests
[PASS] test_getNextPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 497823, ~: 501006)
Test result: ok. 1 passed; 0 failed; finished in 41.43ms

Running 5 tests for tests/Payments.t.sol:LateRepaymentsTests
[PASS] test_payments_dailyInterestAccrual() (gas: 942936)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case1() (gas: 1430476)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case2() (gas: 1437441)
[PASS] test_payments_lateRepayment_flatRate_case1() (gas: 1426884)
[PASS] test_payments_lateRepayment_flatRate_case2() (gas: 1424722)
Test result: ok. 5 passed; 0 failed; finished in 11.26ms

Running 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPaymentBreakdownTests
[PASS] test_getPaymentBreakdown_onePaymentFourPeriodsLate() (gas: 27674)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodBeforeDue() (gas: 26411)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodLate() (gas: 27696)
[PASS] test_getPaymentBreakdown_onePaymentOneSecondBeforeDue() (gas: 26465)
[PASS] test_getPaymentBreakdown_onePaymentThreePeriodsLate() (gas: 27629)
[PASS] test_getPaymentBreakdown_onePaymentTwoPeriodsLate() (gas: 27651)
Test result: ok. 6 passed; 0 failed; finished in 839.63µs

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPeriodicInterestRateTests
[PASS] test_getPeriodicInterestRate() (gas: 7567)
Test result: ok. 1 passed; 0 failed; finished in 525.46µs

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ProposeNewTermsTests
[PASS] test_proposeNewTerms(address,uint256,uint256,uint256,uint256) (runs: 256, μ: 70217, ~: 70333)
[PASS] test_proposeNewTerms_emptyArray(address,uint256) (runs: 256, μ: 34095, ~: 34226)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 79364)
Test result: ok. 3 passed; 0 failed; finished in 48.78ms

Running 2 tests for tests/MapleLoanFeeManager.t.sol:FeeManager_Getters
[PASS] test_getDelegateServiceFeesForPeriod() (gas: 663177)
[PASS] test_getPlatformServiceFeeForPeriod() (gas: 950007)
Test result: ok. 2 passed; 0 failed; finished in 2.26ms

Running 1 test for tests/MapleLoanFeeManager.t.sol:PayClosingFeesTests
[PASS] test_payClosingServiceFees() (gas: 252303)
Test result: ok. 1 passed; 0 failed; finished in 2.15ms

Running 8 tests for tests/MapleLoanFactory.t.sol:MapleLoanFactoryTest
[PASS] testFail_createInstance_saltAndArgumentsCollision() (gas: 8937393460516744904)
[PASS] test_createInstance(bytes32) (runs: 256, μ: 502970, ~: 502970)
[PASS] test_createInstance_differentFundsAsset() (gas: 707004)
[PASS] test_createInstance_invalidCollateralAsset() (gas: 679268)
[PASS] test_createInstance_invalidFactory() (gas: 712260)
[PASS] test_createInstance_invalidInstance() (gas: 717499)
[PASS] test_createInstance_invalidPoolAsset() (gas: 676047)
[PASS] test_createInstance_zeroLender() (gas: 691693)
Test result: ok. 8 passed; 0 failed; finished in 107.26ms

Running 11 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_FundLoanTests
[PASS] test_fundLoan_approveFail() (gas: 227089)
[PASS] test_fundLoan_doubleFund(uint256) (runs: 256, μ: 267918, ~: 267803)
[PASS] test_fundLoan_fullFunding(uint256) (runs: 256, μ: 289220, ~: 289087)
[PASS] test_fundLoan_fullFundingWithExistingDrawableFunds(uint256) (runs: 256, μ: 290388, ~: 290266)
[PASS] test_fundLoan_invalidFundsAsset() (gas: 923378)
[PASS] test_fundLoan_nextPaymentDueDateAlreadySet() (gas: 172438)
[PASS] test_fundLoan_noPaymentsRemaining() (gas: 82119)
[PASS] test_fundLoan_notLender() (gas: 25960)
[PASS] test_fundLoan_partialFunding(uint256) (runs: 256, μ: 213871, ~: 216867)
[PASS] test_fundLoan_withUnaccountedCollateralAsset() (gas: 1037312)
[PASS] test_fundLoan_withoutSendingAsset() (gas: 171239)
Test result: ok. 11 passed; 0 failed; finished in 127.49ms

Running 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CollateralMaintainedTests
[PASS] test_isCollateralMaintained(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 118602, ~: 122474)
[PASS] test_isCollateralMaintained_edgeCases() (gas: 168417)
[PASS] test_isCollateralMaintained_roundUp() (gas: 81134)
Test result: ok. 3 passed; 0 failed; finished in 12.02ms

Running 12 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetUnaccountedAmountTests
[PASS] test_getUnaccountedAmount_collateral(uint256,uint256) (runs: 256, μ: 87121, ~: 87198)
[PASS] test_getUnaccountedAmount_collateralAsset() (gas: 74375)
[PASS] test_getUnaccountedAmount_complex(uint256,uint256,uint256) (runs: 256, μ: 816927, ~: 818613)
[PASS] test_getUnaccountedAmount_drawableFunds(uint256,uint256) (runs: 256, μ: 87022, ~: 87100)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral(uint256,uint256,uint256,uint256) (runs: 256, μ: 165292, ~: 165164)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral_fundsAssetEqCollateralAsset(uint256,uint256,uint256) (runs: 256, μ: 114695, ~: 114675)
[PASS] test_getUnaccountedAmount_fundsAsset() (gas: 74365)
[PASS] test_getUnaccountedAmount_newFundsLtCollateral(uint256) (runs: 256, μ: 102087, ~: 102077)
[PASS] test_getUnaccountedAmount_newFundsLtDrawableFunds(uint256) (runs: 256, μ: 102034, ~: 102022)
[PASS] test_getUnaccountedAmount_randomToken() (gas: 107912)
[PASS] test_getUnaccountedAmount_withCollateral(uint256,uint256) (runs: 256, μ: 80951, ~: 86573)
[PASS] test_getUnaccountedAmount_withDrawableFunds(uint256,uint256) (runs: 256, μ: 82245, ~: 86455)
Test result: ok. 12 passed; 0 failed; finished in 145.00ms

Running 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_InitializeTests
[PASS] test_initialize() (gas: 5053250)
[PASS] test_initialize_invalidBorrower() (gas: 1124358)
[PASS] test_initialize_invalidEndingPrincipal() (gas: 1089287)
[PASS] test_initialize_invalidGracePeriodBoundary() (gas: 6067497)
[PASS] test_initialize_invalidOriginationFeeBoundary() (gas: 6067710)
[PASS] test_initialize_invalidPaymentInterval() (gas: 1095791)
[PASS] test_initialize_invalidPaymentsRemaining() (gas: 1095760)
[PASS] test_initialize_invalidPrincipal() (gas: 1089147)
[PASS] test_initialize_zeroBorrower() (gas: 1098706)
Test result: ok. 9 passed; 0 failed; finished in 14.88ms

Running 1 test for tests/Refinancer.t.sol:RefinancerCollateralRequiredTests
[PASS] test_refinance_collateralRequired(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5387360, ~: 5382729)
Test result: ok. 1 passed; 0 failed; finished in 319.01ms

Running 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CloseLoanTests
[PASS] test_closeLoan(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 275751, ~: 277597)
[PASS] test_closeLoan_amountSmallerThanFees() (gas: 436673)
[PASS] test_closeLoan_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 334229, ~: 334720)
[PASS] test_closeLoan_latePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 284354, ~: 285880)
[PASS] test_closeLoan_noAmount() (gas: 430815)
[PASS] test_closeLoan_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 283238, ~: 284631)
[PASS] test_closeLoan_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 278499, ~: 278525)
Test result: ok. 7 passed; 0 failed; finished in 316.19ms

Running 1 test for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetClosingPaymentBreakdownTests
[PASS] test_getClosingPaymentBreakdown(uint256,uint256,uint256) (runs: 256, μ: 5079282, ~: 5079204)
Test result: ok. 1 passed; 0 failed; finished in 194.97ms

Running 1 test for tests/Refinancer.t.sol:RefinancerMultipleParameterTests
[PASS] test_refinance_multipleParameters(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5402907, ~: 5400043)
Test result: ok. 1 passed; 0 failed; finished in 349.88ms

Running 1 test for tests/Refinancer.t.sol:RefinancerGracePeriodTests
[PASS] test_refinance_gracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5351635, ~: 5360772)
Test result: ok. 1 passed; 0 failed; finished in 284.50ms

Running 2 tests for tests/Refinancer.t.sol:RefinancerPaymentIntervalTests
[PASS] test_refinance_paymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5358587, ~: 5362055)
[PASS] test_refinance_paymentInterval_zeroAmount() (gas: 5302939)
Test result: ok. 2 passed; 0 failed; finished in 291.88ms

Running 4 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_PostCollateralTests
[PASS] test_postCollateral_invalidCollateralAsset() (gas: 790783)
[PASS] test_postCollateral_multiple(uint256,uint256) (runs: 256, μ: 148284, ~: 145680)
[PASS] test_postCollateral_once(uint256) (runs: 256, μ: 95868, ~: 100984)
[PASS] test_postCollateral_withUnaccountedFundsAsset() (gas: 877361)
Test result: ok. 4 passed; 0 failed; finished in 83.14ms

Running 8 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_MakePaymentTests
[PASS] test_makePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 352359, ~: 358432)
[PASS] test_makePayment_amountSmallerThanFees() (gas: 450322)
[PASS] test_makePayment_collateralNotMaintained() (gas: 798306)
[PASS] test_makePayment_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 366775, ~: 371181)
[PASS] test_makePayment_lastPaymentClearsLoan(uint256,uint256,uint256,uint256) (runs: 256, μ: 337857, ~: 340369)
[PASS] test_makePayment_noAmount() (gas: 442964)
[PASS] test_makePayment_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 357246, ~: 362978)
[PASS] test_makePayment_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 340840, ~: 341891)
Test result: ok. 8 passed; 0 failed; finished in 357.30ms

Running 1 test for tests/Refinancer.t.sol:RefinancerInterestRateTests
[PASS] test_refinance_interestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5357983, ~: 5361392)
Test result: ok. 1 passed; 0 failed; finished in 261.71ms

Running 2 tests for tests/Refinancer.t.sol:RefinancerPaymentsRemainingTests
[PASS] test_refinance_paymentRemaining(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5358661, ~: 5361961)
[PASS] test_refinance_paymentRemaining_zeroAmount() (gas: 5302930)
Test result: ok. 2 passed; 0 failed; finished in 303.77ms

Running 2 tests for tests/Refinancer.t.sol:RefinancerDeadlineTests
[PASS] test_refinance_afterDeadline(uint256,uint256,uint256) (runs: 256, μ: 5308629, ~: 5309027)
[PASS] test_refinance_differentDeadline(uint256,uint256,uint256) (runs: 256, μ: 5284481, ~: 5284511)
Test result: ok. 2 passed; 0 failed; finished in 568.61ms

Running 2 tests for tests/Refinancer.t.sol:RefinancerPrincipalRequestedTests
[PASS] test_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5420929, ~: 5423662)
[PASS] test_refinance_increasePrincipalRequestedWithInsufficientFunds(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5359959, ~: 5363392)
Test result: ok. 2 passed; 0 failed; finished in 594.81ms

Running 3 tests for tests/Refinancer.t.sol:RefinancerFeeTests
[PASS] test_refinance_closingRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5357856, ~: 5361864)
[PASS] test_refinance_lateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5357726, ~: 5361656)
[PASS] test_refinance_lateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5378206, ~: 5381823)
Test result: ok. 3 passed; 0 failed; finished in 789.69ms

Running 3 tests for tests/Refinancer.t.sol:RefinancerEndingPrincipalTests
[PASS] test_refinance_endingPrincipal_amortizedToInterestOnly(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5376151, ~: 5379438)
[PASS] test_refinance_endingPrincipal_failLargerThanPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5342019, ~: 5350410)
[PASS] test_refinance_endingPrincipal_interestOnlyToAmortized(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 5369828, ~: 5377334)
Test result: ok. 3 passed; 0 failed; finished in 482.67ms

Running 11 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RemoveCollateralTests
[PASS] test_removeCollateral_cannotRemoveAnyAmountWithEncumbrances() (gas: 191583)
[PASS] test_removeCollateral_cannotRemoveFullAmountWithEncumbrances(uint256) (runs: 256, μ: 152052, ~: 152041)
[PASS] test_removeCollateral_cannotRemovePartialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 192346, ~: 192456)
[PASS] test_removeCollateral_fullAmountWithNoEncumbrances(uint256) (runs: 256, μ: 118021, ~: 118023)
[PASS] test_removeCollateral_fullAmount_drawableFundsGtPrincipal(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 178527, ~: 180648)
[PASS] test_removeCollateral_fullAmount_noPrincipal(uint256) (runs: 256, μ: 135479, ~: 135489)
[PASS] test_removeCollateral_insufficientCollateralWithNoEncumbrances(uint256) (runs: 256, μ: 109012, ~: 115062)
[PASS] test_removeCollateral_partialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 232002, ~: 235551)
[PASS] test_removeCollateral_partialAmountWithNoEncumbrances(uint256,uint256) (runs: 256, μ: 151152, ~: 153156)
[PASS] test_removeCollateral_sameAssetAsFundingAsset(uint256) (runs: 256, μ: 138132, ~: 138113)
[PASS] test_removeCollateral_transferFailed() (gas: 191682)
Test result: ok. 11 passed; 0 failed; finished in 907.62ms

Running 7 tests for tests/Refinancer.t.sol:RefinancingFeesTerms
[PASS] testFuzz_refinance_payOriginationFees(uint256,uint256) (runs: 256, μ: 6313909, ~: 6313893)
[PASS] testFuzz_refinance_pdOriginationFeeTransferFail(uint256) (runs: 256, μ: 6237664, ~: 6239094)
[PASS] testFuzz_refinance_treasuryOriginationFeeTransferFail(uint256,uint256) (runs: 256, μ: 6249329, ~: 6249358)
[PASS] testFuzz_refinance_updateFeeTerms(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 6260486, ~: 6265317)
[PASS] testFuzz_refinance_updatesPlatformServiceFees(uint256) (runs: 256, μ: 6232180, ~: 6232317)
[PASS] test_refinance_updateRefinanceServiceFees() (gas: 6313437)
[PASS] test_refinance_updateRefinanceServiceFeesOnDoubleRefinance() (gas: 6384830)
Test result: ok. 7 passed; 0 failed; finished in 701.78ms

Running 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_DrawdownFundsTests
[PASS] test_drawdownFunds_collateralNotMaintained(uint256,uint256,uint256) (runs: 256, μ: 255403, ~: 262778)
[PASS] test_drawdownFunds_insufficientDrawableFunds(uint256,uint256) (runs: 256, μ: 152110, ~: 152181)
[PASS] test_drawdownFunds_multipleDrawdowns(uint256,uint256,uint256) (runs: 256, μ: 259980, ~: 259885)
[PASS] test_drawdownFunds_postedCollateral(uint256,uint256,uint256) (runs: 256, μ: 278738, ~: 283286)
[PASS] test_drawdownFunds_transferFailed() (gas: 52355)
[PASS] test_drawdownFunds_withoutPostedCollateral(uint256,uint256) (runs: 256, μ: 185465, ~: 189518)
Test result: ok. 6 passed; 0 failed; finished in 1.02s

```

# `fixed-term-loan-manager (v3.0.1)`

```
Running 2 tests for tests/LoanManager.t.sol:UpdateAccountingFailureTests
[PASS] test_updateAccounting_notGovernor() (gas: 97740)
[PASS] test_updateAccounting_notPoolDelegate() (gas: 95622)
Test result: ok. 2 passed; 0 failed; finished in 1.88ms

Running 1 test for tests/LoanManager.t.sol:AcceptNewTermsTests
[PASS] test_acceptNewTerms_invalidBorrower() (gas: 204711)
Test result: ok. 1 passed; 0 failed; finished in 1.84ms

Running 3 tests for tests/LoanManager.t.sol:DistributeLiquidationFundsTests
[PASS] test_distributeLiquidationFunds_borrowerNotSet() (gas: 682145)
[PASS] test_distributeLiquidationFunds_mapleTreasuryNotSet() (gas: 726119)
[PASS] test_distributeLiquidationFunds_poolNotSet() (gas: 712840)
Test result: ok. 3 passed; 0 failed; finished in 1.84ms

Running 2 tests for tests/LoanManager.t.sol:ClaimTests
[PASS] test_claim_notLoan() (gas: 349709)
[PASS] test_claim_paused() (gas: 39902)
Test result: ok. 2 passed; 0 failed; finished in 2.20ms

Running 3 tests for tests/LoanManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 31132)
[PASS] test_setImplementation_paused() (gas: 36797)
[PASS] test_setImplementation_success() (gas: 41083)
Test result: ok. 3 passed; 0 failed; finished in 2.11ms

Running 7 tests for tests/LoanManager.t.sol:FundLoanTests
[PASS] test_fund() (gas: 417732)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 89003)
[PASS] test_fund_inactiveLoan() (gas: 65518)
[PASS] test_fund_invalidBorrower() (gas: 69446)
[PASS] test_fund_invalidFactory() (gas: 59975)
[PASS] test_fund_invalidLoan() (gas: 60457)
[PASS] test_fund_paused() (gas: 44453)
Test result: ok. 7 passed; 0 failed; finished in 2.25ms

Running 4 tests for tests/CreateInstanceTests.t.sol:CreateInstanceTests
[PASS] testFail_createInstance_collision() (gas: 16089)
[PASS] testFail_createInstance_notPool() (gas: 14001)
[PASS] test_createInstance_notPoolDeployer() (gas: 19076)
[PASS] test_createInstance_success_asPoolDeployer() (gas: 260048)
Test result: ok. 4 passed; 0 failed; finished in 2.97ms

Running 3 tests for tests/LoanManager.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_notPoolDelegate() (gas: 37313)
[PASS] test_rejectNewTerms_paused() (gas: 35526)
[PASS] test_rejectNewTerms_success() (gas: 606613)
Test result: ok. 3 passed; 0 failed; finished in 3.55ms

Running 4 tests for tests/LoanManager.t.sol:SetMinRatio_SetterTests
[PASS] test_setMinRatio_noAuth() (gas: 40866)
[PASS] test_setMinRatio_paused() (gas: 36871)
[PASS] test_setMinRatio_success_asGovernor() (gas: 68179)
[PASS] test_setMinRatio_success_asPoolDelegate() (gas: 66083)
Test result: ok. 4 passed; 0 failed; finished in 1.55ms

Running 2 tests for tests/LoanManager.t.sol:DistributeClaimedFunds
[PASS] test_distributeClaimedFunds_mapleTreasuryNotSet() (gas: 884911)
[PASS] test_distributeLiquidationFunds_poolNotSet() (gas: 824987)
Test result: ok. 2 passed; 0 failed; finished in 1.73ms

Running 2 tests for tests/LoanManager.t.sol:GetterTests
[PASS] test_accruedInterest() (gas: 35284)
[PASS] test_getAssetsUnderManagement() (gas: 40617)
Test result: ok. 2 passed; 0 failed; finished in 1.64ms

Running 4 tests for tests/LoanManager.t.sol:UpdateAccountingTests
[PASS] test_updateAccounting_afterDomainEnd() (gas: 111856)
[PASS] test_updateAccounting_afterTwoDomainEnds() (gas: 105163)
[PASS] test_updateAccounting_beforeDomainEnd() (gas: 95639)
[PASS] test_updateAccounting_failIfPaused() (gas: 37152)
Test result: ok. 4 passed; 0 failed; finished in 2.62ms

Running 1 test for tests/LoanManager.t.sol:ClaimDomainStartGtDomainEnd
[PASS] test_claim_domainStart_gt_domainEnd() (gas: 627425)
Test result: ok. 1 passed; 0 failed; finished in 2.56ms

Running 5 tests for tests/LoanManager.t.sol:FinishCollateralLiquidationTests
[PASS] test_finishCollateralLiquidation_callAfterTriggerDefaultOnUncollateralizedLoan() (gas: 120405)
[PASS] test_finishCollateralLiquidation_callBeforeTriggerDefault() (gas: 62644)
[PASS] test_finishCollateralLiquidation_notManager() (gas: 286580)
[PASS] test_finishCollateralLiquidation_paused() (gas: 42051)
[PASS] test_finishCollateralLiquidation_success_withCollateral() (gas: 352686)
Test result: ok. 5 passed; 0 failed; finished in 2.62ms

Running 6 tests for tests/LoanManager.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 40856)
[PASS] test_upgrade_notScheduled() (gas: 43295)
[PASS] test_upgrade_paused() (gas: 34992)
[PASS] test_upgrade_success_asPoolDelegate() (gas: 84424)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 75528)
[PASS] test_upgrade_upgradeFailed() (gas: 79374)
Test result: ok. 6 passed; 0 failed; finished in 2.38ms

Running 5 tests for tests/LoanManager.t.sol:SetAllowedSlippage_SetterTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 41412)
[PASS] test_setAllowedSlippage_noAuth() (gas: 40792)
[PASS] test_setAllowedSlippage_paused() (gas: 36840)
[PASS] test_setAllowedSlippage_success_asGovernor() (gas: 68207)
[PASS] test_setAllowedSlippage_success_asPoolDelegate() (gas: 68206)
Test result: ok. 5 passed; 0 failed; finished in 1.61ms

Running 6 tests for tests/LoanManager.t.sol:UintCastingTests
[PASS] test_castUint112() (gas: 22068)
[PASS] test_castUint120() (gas: 21976)
[PASS] test_castUint128() (gas: 22047)
[PASS] test_castUint24() (gas: 21860)
[PASS] test_castUint48() (gas: 21892)
[PASS] test_castUint96() (gas: 22008)
Test result: ok. 6 passed; 0 failed; finished in 1.57ms

Running 5 tests for tests/LoanManager.t.sol:ImpairLoanTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 179022)
[PASS] test_impairLoan_failIfPaused() (gas: 39400)
[PASS] test_impairLoan_notAuthorized() (gas: 40751)
[PASS] test_impairLoan_success() (gas: 235326)
[PASS] test_impairLoan_success_byGovernor() (gas: 218373)
Test result: ok. 5 passed; 0 failed; finished in 2.67ms

Running 7 tests for tests/LoanManager.t.sol:RemoveLoanImpairmentTests
[PASS] test_removeLoanImpairment_delegateNotAuthorizedToRemoveGovernors() (gas: 257200)
[PASS] test_removeLoanImpairment_failIfPaused() (gas: 44495)
[PASS] test_removeLoanImpairment_notByGovernor() (gas: 189426)
[PASS] test_removeLoanImpairment_notPoolDelegate() (gas: 185986)
[PASS] test_removeLoanImpairment_pastDueDate() (gas: 268690)
[PASS] test_removeLoanImpairment_successWithGovernor() (gas: 288960)
[PASS] test_removeLoanImpairment_successWithPD() (gas: 288297)
Test result: ok. 7 passed; 0 failed; finished in 3.48ms

Running 2 tests for tests/LoanManager.t.sol:ThreeLoanPastDomainEndClaimTests
[PASS] test_claim_loan1NotPaid_loan2NotPaid_loan3PaidLate() (gas: 364554)
[PASS] test_claim_loan3_loan1NotPaid_loan2NotPaid() (gas: 363079)
Test result: ok. 2 passed; 0 failed; finished in 2.83ms

Running 3 tests for tests/LoanManager.t.sol:TwoLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 609341)
[PASS] test_claim_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 630843)
[PASS] test_claim_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 606539)
Test result: ok. 3 passed; 0 failed; finished in 7.32ms

Running 7 tests for tests/LoanManager.t.sol:TriggerDefaultTests
[PASS] test_triggerDefault_notManager() (gas: 123807)
[PASS] test_triggerDefault_paused() (gas: 39410)
[PASS] test_triggerDefault_success_noCollateral_impaired() (gas: 219767)
[PASS] test_triggerDefault_success_noCollateral_notImpaired() (gas: 150678)
[PASS] test_triggerDefault_success_withCollateralAssetEqualToFundsAsset() (gas: 291750)
[PASS] test_triggerDefault_success_withCollateral_impaired() (gas: 382197)
[PASS] test_triggerDefault_success_withCollateral_notImpaired() (gas: 358317)
Test result: ok. 7 passed; 0 failed; finished in 8.30ms

Running 13 tests for tests/LoanManager.t.sol:LoanManagerSortingTests
[PASS] test_addPaymentToList_ascendingPair() (gas: 98374)
[PASS] test_addPaymentToList_descendingPair() (gas: 98350)
[PASS] test_addPaymentToList_single() (gas: 63650)
[PASS] test_addPaymentToList_synchronizedPair() (gas: 98384)
[PASS] test_addPaymentToList_toHead() (gas: 135321)
[PASS] test_addPaymentToList_toMiddle() (gas: 135850)
[PASS] test_addPaymentToList_toTail() (gas: 135845)
[PASS] test_removePaymentFromList_earliestDueDate() (gas: 115374)
[PASS] test_removePaymentFromList_invalidPaymentId() (gas: 76816)
[PASS] test_removePaymentFromList_latestDueDate() (gas: 115163)
[PASS] test_removePaymentFromList_medianDueDate() (gas: 115457)
[PASS] test_removePaymentFromList_pair() (gas: 83196)
[PASS] test_removePaymentFromList_single() (gas: 52558)
Test result: ok. 13 passed; 0 failed; finished in 2.92ms

Running 4 tests for tests/LoanManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 34157)
[PASS] test_migrate_notFactory() (gas: 31535)
[PASS] test_migrate_paused() (gas: 37144)
[PASS] test_migrate_success() (gas: 39806)
Test result: ok. 4 passed; 0 failed; finished in 1.57ms

Running 6 tests for tests/LoanManager.t.sol:SingleLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_amortized() (gas: 396877)
[PASS] test_claim_earlyPayment_interestOnly() (gas: 389618)
[PASS] test_claim_latePayment_amortized() (gas: 417761)
[PASS] test_claim_latePayment_interestOnly() (gas: 410500)
[PASS] test_claim_onTimePayment_amortized() (gas: 394132)
[PASS] test_claim_onTimePayment_interestOnly() (gas: 386939)
Test result: ok. 6 passed; 0 failed; finished in 5.09ms

Running 4 tests for tests/LoanManager.t.sol:RefinanceAccountingSingleLoanTests
[PASS] test_refinance_beforeLoanDueDate_interestOnly() (gas: 552655)
[PASS] test_refinance_onLatePayment_interestOnly() (gas: 554416)
[PASS] test_refinance_onLoanPaymentDueDate_interestOnly() (gas: 553143)
[PASS] test_refinance_onPaymentDueDate_amortized() (gas: 554022)
Test result: ok. 4 passed; 0 failed; finished in 2.73ms

Running 2 tests for tests/LoanManager.t.sol:QueueNextPaymentTests
[PASS] testFuzz_queueNextPayment_fees(uint256,uint256) (runs: 256, μ: 198293, ~: 208661)
[PASS] test_queueNextPayment_fees() (gas: 168413)
Test result: ok. 2 passed; 0 failed; finished in 27.42ms

Running 1 test for tests/LoanManagerFuzz.t.sol:SingleLoanClaimTests
[PASS] testFuzz_claim_latePayment_interestOnly(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 1270017, ~: 1276423)
Test result: ok. 1 passed; 0 failed; finished in 152.09ms
```

# `globals-v2 (v1.0.0)`

```
Running 3 tests for tests/MapleGlobals.t.sol:SetPlatformManagementFeeRateTests
[PASS] test_setPlatformManagementFeeRate() (gas: 53049)
[PASS] test_setPlatformManagementFeeRate_notGovernor() (gas: 57698)
[PASS] test_setPlatformManagementFeeRate_outOfBounds() (gas: 57777)
Test result: ok. 3 passed; 0 failed; finished in 1.01ms

Running 2 tests for tests/MapleGlobals.t.sol:SetValidCollateralTests
[PASS] test_setValidCollateral() (gas: 44503)
[PASS] test_setValidCollateral_notGovernor() (gas: 57757)
Test result: ok. 2 passed; 0 failed; finished in 1.03ms

Running 3 tests for tests/MapleGlobals.t.sol:SetContractPauseTests
[PASS] test_setContractPause_asGovernor() (gas: 45692)
[PASS] test_setContractPause_asSecurityAdmin() (gas: 47510)
[PASS] test_setContractPause_notAuthorized() (gas: 23813)
Test result: ok. 3 passed; 0 failed; finished in 1.10ms

Running 1 test for tests/MapleGlobals.t.sol:IsValidScheduledCallTests
[PASS] test_isValidScheduledCall() (gas: 94685)
Test result: ok. 1 passed; 0 failed; finished in 1.15ms

Running 6 tests for tests/MapleGlobals.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice() (gas: 125890)
[PASS] test_getLatestPrice_manualOverride() (gas: 147520)
[PASS] test_getLatestPrice_oracleNotSet() (gas: 66383)
[PASS] test_getLatestPrice_roundNotComplete() (gas: 36963)
[PASS] test_getLatestPrice_staleData() (gas: 81545)
[PASS] test_getLatestPrice_zeroPrice() (gas: 102817)
Test result: ok. 6 passed; 0 failed; finished in 1.31ms

Running 1 test for tests/MapleGlobals.t.sol:IsFunctionPausedTests
[PASS] test_isFunctionPaused() (gas: 263649)
Test result: ok. 1 passed; 0 failed; finished in 1.46ms

Running 3 tests for tests/MapleGlobals.t.sol:SetValidPoolDeployer
[PASS] test_setValidDeployer_enablingNotAllowed() (gas: 24478)
[PASS] test_setValidDeployer_notGovernor() (gas: 21659)
[PASS] test_setValidDeployer_success() (gas: 27365)
Test result: ok. 3 passed; 0 failed; finished in 1.23ms

Running 3 tests for tests/MapleGlobals.t.sol:SetPlatformOriginationFeeRateTests
[PASS] test_setPlatformOriginationFeeRate() (gas: 52917)
[PASS] test_setPlatformOriginationFeeRate_notGovernor() (gas: 57804)
[PASS] test_setPlatformOriginationFeeRate_outOfBounds() (gas: 57817)
Test result: ok. 3 passed; 0 failed; finished in 898.04µs

Running 2 tests for tests/MapleGlobals.t.sol:SetDefaultTimelockParametersTests
[PASS] test_setDefaultTimelockParameters() (gas: 49413)
[PASS] test_setDefaultTimelockParameters_notGovernor() (gas: 19502)
Test result: ok. 2 passed; 0 failed; finished in 770.08µs

Running 2 tests for tests/MapleGlobals.t.sol:SetValidInstanceOfTests
[PASS] test_setValidInstanceOf() (gas: 46207)
[PASS] test_setValidInstanceOf_notGovernor() (gas: 58556)
Test result: ok. 2 passed; 0 failed; finished in 1.00ms

Running 3 tests for tests/MapleGlobals.t.sol:ScheduleCallTests
[PASS] test_scheduleCal_overwrite() (gas: 85144)
[PASS] test_scheduleCall() (gas: 70164)
[PASS] test_scheduleCall_defaultState() (gas: 19280)
Test result: ok. 3 passed; 0 failed; finished in 993.96µs

Running 2 tests for tests/MapleGlobals.t.sol:TransferGovernorTests
[PASS] test_acceptGovernor() (gas: 54249)
[PASS] test_acceptGovernor_notPendingGovernor() (gas: 18423)
Test result: ok. 2 passed; 0 failed; finished in 870.92µs

Running 3 tests for tests/MapleGlobals.t.sol:SetMapleTreasuryTests
[PASS] test_setMapleTreasury() (gas: 51745)
[PASS] test_setMapleTreasury_notGovernor() (gas: 21353)
[PASS] test_setMapleTreasury_zeroAddressCheck() (gas: 22054)
Test result: ok. 3 passed; 0 failed; finished in 829.08µs

Running 2 tests for tests/MapleGlobals.t.sol:SetValidPoolAssetTests
[PASS] test_setValidPoolAsset() (gas: 44378)
[PASS] test_setValidPoolAsset_notGovernor() (gas: 57667)
Test result: ok. 2 passed; 0 failed; finished in 812.46µs

Running 3 tests for tests/MapleGlobals.t.sol:SetPlatformServiceFeeRateTests
[PASS] test_setPlatformServiceFeeRate() (gas: 52938)
[PASS] test_setPlatformServiceFeeRate_notGovernor() (gas: 57692)
[PASS] test_setPlatformServiceFeeRate_outOfBounds() (gas: 57683)
Test result: ok. 3 passed; 0 failed; finished in 846.08µs

Running 4 tests for tests/MapleGlobals.t.sol:TransferOwnedPoolTests
[PASS] test_transferOwnedPool() (gas: 77522)
[PASS] test_transferOwnedPool_alreadyOwns() (gas: 293395)
[PASS] test_transferOwnedPool_notPoolDelegate() (gas: 28877)
[PASS] test_transferOwnedPool_notPoolManager() (gas: 23789)
Test result: ok. 4 passed; 0 failed; finished in 1.24ms

Running 3 tests for tests/MapleGlobals.t.sol:SetFunctionUnpauseTests
[PASS] test_setContractPause_asGovernor() (gas: 50149)
[PASS] test_setContractPause_asSecurityAdmin() (gas: 50367)
[PASS] test_setContractPause_notAuthorized() (gas: 26326)
Test result: ok. 3 passed; 0 failed; finished in 1.02ms

Running 2 tests for tests/MapleGlobals.t.sol:SetBootstrapMintTests
[PASS] test_setBootstrapMint() (gas: 52884)
[PASS] test_setBootstrapMint_notGovernor() (gas: 57623)
Test result: ok. 2 passed; 0 failed; finished in 766.04µs

Running 3 tests for tests/MapleGlobals.t.sol:SetValidPoolDelegate
[PASS] test_setValidDeployer_zeroAddress() (gas: 22428)
[PASS] test_setValidPoolDelegate() (gas: 45049)
[PASS] test_setValidPoolDelegate_notGovernor() (gas: 57885)
Test result: ok. 3 passed; 0 failed; finished in 870.67µs

Running 3 tests for tests/MapleGlobals.t.sol:SetMaxCoverLiquidationPercentTests
[PASS] test_setMaxCoverLiquidationPercent() (gas: 52849)
[PASS] test_setMaxCoverLiquidationPercent_gt100() (gas: 57685)
[PASS] test_setMaxCoverLiquidationPercent_notGovernor() (gas: 57694)
Test result: ok. 3 passed; 0 failed; finished in 884.08µs

Running 2 tests for tests/MapleGlobals.t.sol:SetCanDeployFromTests
[PASS] test_setCanDeployFrom() (gas: 51860)
[PASS] test_setCanDeployFrom_notGovernor() (gas: 24121)
Test result: ok. 2 passed; 0 failed; finished in 831.92µs

Running 5 tests for tests/MapleGlobals.t.sol:UnScheduleCallTests
[PASS] test_unscheduleCall() (gas: 32054)
[PASS] test_unscheduleCall_asGovernor() (gas: 36876)
[PASS] test_unscheduleCall_asGovernor_callDataMismatch() (gas: 34664)
[PASS] test_unscheduleCall_callDataMismatch() (gas: 29776)
[PASS] test_unscheduleCall_notGovernor() (gas: 22412)
Test result: ok. 5 passed; 0 failed; finished in 1.11ms

Running 2 tests for tests/MapleGlobals.t.sol:SetManualOverridePriceTests
[PASS] test_setManualOverridePrice() (gas: 460567)
[PASS] test_setManualOverridePrice_notGovernor() (gas: 57800)
Test result: ok. 2 passed; 0 failed; finished in 909.67µs

Running 4 tests for tests/MapleGlobals.t.sol:SetTimelockWindowTests
[PASS] test_setTimelockWindow() (gas: 56843)
[PASS] test_setTimelockWindow_notGovernor() (gas: 22334)
[PASS] test_setTimelockWindows() (gas: 94770)
[PASS] test_setTimelockWindows_notGovernor() (gas: 25234)
Test result: ok. 4 passed; 0 failed; finished in 1.05ms

Running 3 tests for tests/MapleGlobals.t.sol:SetSecurityAdminTests
[PASS] test_setSecurityAdmin() (gas: 51733)
[PASS] test_setSecurityAdmin_notGovernor() (gas: 21354)
[PASS] test_setSecurityAdmin_zeroAddressCheck() (gas: 22099)
Test result: ok. 3 passed; 0 failed; finished in 799.04µs

Running 2 tests for tests/MapleGlobals.t.sol:SetMigrationAdminTests
[PASS] test_setMigrationAdmin() (gas: 51760)
[PASS] test_setMigrationAdmin_notGovernor() (gas: 21373)
Test result: ok. 2 passed; 0 failed; finished in 749.00µs

Running 4 tests for tests/MapleGlobals.t.sol:canDeployFromTests
[PASS] test_canDeployFrom_invalidFactoryAndCaller() (gas: 29882)
[PASS] test_canDeployFrom_poolManagerDeployingLoanManager() (gas: 105442)
[PASS] test_canDeployFrom_poolManagerDeployingLoanManager_WithValidFactoryAndCallerSet() (gas: 137137)
[PASS] test_canDeployFrom_validFactoryAndCaller() (gas: 57772)
Test result: ok. 4 passed; 0 failed; finished in 1.10ms

Running 6 tests for tests/MapleGlobals.t.sol:ActivatePoolTests
[PASS] test_activatePoolManager_alreadyOwns() (gas: 58245)
[PASS] test_activatePoolManager_invalidDelegate() (gas: 82290)
[PASS] test_activatePoolManager_invalidFactory() (gas: 74670)
[PASS] test_activatePoolManager_invalidInstance() (gas: 76434)
[PASS] test_activatePoolManager_notGovernor() (gas: 58924)
[PASS] test_activatePoolManager_success() (gas: 57010)
Test result: ok. 6 passed; 0 failed; finished in 4.29ms

Running 2 tests for tests/MapleGlobals.t.sol:SetPendingGovernorTests
[PASS] test_setPendingGovernor() (gas: 51208)
[PASS] test_setPendingGovernor_notGovernor() (gas: 21328)
Test result: ok. 2 passed; 0 failed; finished in 723.63µs

Running 2 tests for tests/MapleGlobals.t.sol:SetMinCoverAmountTests
[PASS] test_setMinCoverAmount() (gas: 52890)
[PASS] test_setMinCoverAmount_notGovernor() (gas: 57732)
Test result: ok. 2 passed; 0 failed; finished in 833.54µs

Running 2 tests for tests/MapleGlobals.t.sol:SetValidBorrowerTests
[PASS] test_setValidBorrower() (gas: 44500)
[PASS] test_setValidBorrower_notGovernor() (gas: 57757)
Test result: ok. 2 passed; 0 failed; finished in 780.42µs

Running 3 tests for tests/MapleGlobals.t.sol:SetPriceOracleTests
[PASS] test_setPriceOracle() (gas: 55826)
[PASS] test_setPriceOracle_notGovernor() (gas: 23882)
[PASS] test_setPriceOracle_zeroAddressCheck() (gas: 47779)
Test result: ok. 3 passed; 0 failed; finished in 1.64ms

Running 10 tests for tests/MapleGlobals.t.sol:IsPoolDeployerTest
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerCanDeploy() (gas: 167462)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerCannotDeploy() (gas: 144348)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerIsPoolManager() (gas: 521559)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_poolManagerNotFromValidFactory() (gas: 500015)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_poolManagerNotInstance() (gas: 500268)
[PASS] test_isPoolDeployer_invalidFactory() (gas: 24127)
[PASS] test_isPoolDeployer_poolManagerFactory_deployerCanDeploy() (gas: 169814)
[PASS] test_isPoolDeployer_poolManagerFactory_deployerCannotDeploy() (gas: 146678)
[PASS] test_isPoolDeployer_withdrawalManagerFactory_deployerCanDeploy() (gas: 172034)
[PASS] test_isPoolDeployer_withdrawalManagerFactory_deployerCannotDeploy() (gas: 148964)
Test result: ok. 10 passed; 0 failed; finished in 4.56ms

Running 3 tests for tests/MapleGlobals.t.sol:SetProtocolPauseTests
[PASS] test_setProtocolPause_asGovernor() (gas: 36668)
[PASS] test_setProtocolPause_asSecurityAdmin() (gas: 36962)
[PASS] test_setProtocolPause_notAuthorized() (gas: 21349)
Test result: ok. 3 passed; 0 failed; finished in 872.29µs
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
Running 4 tests for tests/Getter.t.sol:GetterTests
[PASS] test_factory_getter() (gas: 10066)
[PASS] test_globals_getter() (gas: 15474)
[PASS] test_isCalled_getter() (gas: 29968)
[PASS] test_isImpaied_getter() (gas: 29951)
Test result: ok. 4 passed; 0 failed; finished in 963.25µs

Running 3 tests for tests/AcceptLender.t.sol:AcceptLenderTests
[PASS] test_acceptLender_notPendingLender() (gas: 46927)
[PASS] test_acceptLender_paused() (gas: 44539)
[PASS] test_acceptLender_success() (gas: 55416)
Test result: ok. 3 passed; 0 failed; finished in 1.03ms

Running 3 tests for tests/AcceptBorrower.t.sol:AcceptBorrowerTests
[PASS] test_acceptBorrower_notPendingBorrower() (gas: 46962)
[PASS] test_acceptBorrower_paused() (gas: 44519)
[PASS] test_acceptBorrower_success() (gas: 55473)
Test result: ok. 3 passed; 0 failed; finished in 1.00ms

Running 6 tests for tests/Fund.t.sol:FundTests
[PASS] testFuzz_fund_success() (gas: 999708)
[PASS] test_fund_loanActive() (gas: 49818)
[PASS] test_fund_loanClosed() (gas: 30962)
[PASS] test_fund_notLender() (gas: 24150)
[PASS] test_fund_paused() (gas: 44918)
[PASS] test_fund_revertingTransfer() (gas: 914052)
Test result: ok. 6 passed; 0 failed; finished in 1.54ms

Running 7 tests for tests/AcceptNewTerms.t.sol:AcceptNewTermsFailure
[PASS] test_acceptNewTerms_expiredCommitmentBoundary() (gas: 1846792)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 53284)
[PASS] test_acceptNewTerms_mismatchedCommitment() (gas: 34614)
[PASS] test_acceptNewTerms_notBorrower() (gas: 24726)
[PASS] test_acceptNewTerms_paused() (gas: 45494)
[PASS] test_acceptNewTerms_refinancerRevert() (gas: 94419)
[PASS] test_acceptNewTerms_transferRevert() (gas: 742634)
Test result: ok. 7 passed; 0 failed; finished in 2.00ms

Running 5 tests for tests/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_insufficientForCalled() (gas: 99409)
[PASS] test_makePayment_insufficientForTotalTransferFromCaller() (gas: 912405)
[PASS] test_makePayment_notFunded() (gas: 24128)
[PASS] test_makePayment_paused() (gas: 44876)
[PASS] test_makePayment_returningTooMuch() (gas: 78514)
Test result: ok. 5 passed; 0 failed; finished in 2.40ms

Running 7 tests for tests/ProposeNewTerms.t.sol:ProposeNewTermsTests
[PASS] test_proposeNewTerms_deadlineBoundary() (gas: 103684)
[PASS] test_proposeNewTerms_emptyCalls() (gas: 59467)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 35915)
[PASS] test_proposeNewTerms_notFunded() (gas: 30612)
[PASS] test_proposeNewTerms_notLender() (gas: 24682)
[PASS] test_proposeNewTerms_paused() (gas: 45449)
[PASS] test_proposeNewTerms_success() (gas: 103408)
Test result: ok. 7 passed; 0 failed; finished in 1.32ms

Running 11 tests for tests/Initializer.t.sol:InitializerTests
[PASS] test_initialize_differentFundsAsset() (gas: 107703)
[PASS] test_initialize_invalidBorrower() (gas: 50859)
[PASS] test_initialize_invalidFundsAsset() (gas: 53959)
[PASS] test_initialize_invalidLenderFactory() (gas: 1102231)
[PASS] test_initialize_invalidLenderFactoryInstance() (gas: 1130847)
[PASS] test_initialize_invalidNoticePeriod() (gas: 17813)
[PASS] test_initialize_invalidPaymentInterval() (gas: 17813)
[PASS] test_initialize_invalidPrincipal() (gas: 17678)
[PASS] test_initialize_success() (gas: 282470)
[PASS] test_initialize_zeroBorrower() (gas: 23394)
[PASS] test_initialize_zeroLender() (gas: 54358)
Test result: ok. 11 passed; 0 failed; finished in 2.28ms

Running 4 tests for tests/AcceptNewTerms.t.sol:AcceptNewTerms
[PASS] test_acceptNewTerms_earlyRefinance() (gas: 406853)
[PASS] test_acceptNewTerms_principalDecrease() (gas: 417609)
[PASS] test_acceptNewTerms_principalDecreaseToZero() (gas: 394431)
[PASS] test_acceptNewTerms_principalIncrease() (gas: 445004)
Test result: ok. 4 passed; 0 failed; finished in 3.46ms

Running 2 tests for tests/IsInDefault.t.sol:DefaultDatesTests
[PASS] test_isInDefault_successBoundary() (gas: 34440)
[PASS] test_isInDefault_zeroDefaultDate() (gas: 9314)
Test result: ok. 2 passed; 0 failed; finished in 483.88µs

Running 4 tests for tests/SetPendingBorrower.t.sol:SetPendingBorrowerTests
[PASS] test_setPendingBorrower_invalidBorrower() (gas: 32831)
[PASS] test_setPendingBorrower_notBorrower() (gas: 26036)
[PASS] test_setPendingBorrower_paused() (gas: 46760)
[PASS] test_setPendingBorrower_success() (gas: 81809)
Test result: ok. 4 passed; 0 failed; finished in 924.04µs

Running 3 tests for tests/Migrate.t.sol:MigrateTests
[PASS] test_migrate_notFactory() (gas: 22659)
[PASS] test_migrate_paused() (gas: 45328)
[PASS] test_migrate_success() (gas: 69210)
Test result: ok. 3 passed; 0 failed; finished in 686.38µs

Running 3 tests for tests/SetPendingLender.t.sol:SetPendingLenderTests
[PASS] test_setPendingLender_notLender() (gas: 26093)
[PASS] test_setPendingLender_paused() (gas: 46836)
[PASS] test_setPendingLender_success() (gas: 75587)
Test result: ok. 3 passed; 0 failed; finished in 823.63µs

Running 6 tests for tests/Repossess.t.sol:RepossessTests
[PASS] test_repossess_notInDefault() (gas: 53693)
[PASS] test_repossess_notLender() (gas: 26249)
[PASS] test_repossess_paused() (gas: 46992)
[PASS] test_repossess_revertingToken() (gas: 844212)
[PASS] test_repossess_success() (gas: 997011)
[PASS] test_repossess_success_noTransfer() (gas: 885199)
Test result: ok. 6 passed; 0 failed; finished in 2.60ms

Running 7 tests for tests/Skim.t.sol:SkimTests
[PASS] test_skim_borrower() (gas: 877860)
[PASS] test_skim_governor() (gas: 875786)
[PASS] test_skim_noTokenToSkim() (gas: 762227)
[PASS] test_skim_notBorrower() (gas: 28462)
[PASS] test_skim_paused() (gas: 30052)
[PASS] test_skim_revertingToken() (gas: 830502)
[PASS] test_skim_zeroAddress() (gas: 22149)
Test result: ok. 7 passed; 0 failed; finished in 2.41ms

Running 3 tests for tests/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 21938)
[PASS] test_setImplementation_paused() (gas: 44696)
[PASS] test_setImplementation_success() (gas: 91479)
Test result: ok. 3 passed; 0 failed; finished in 688.17µs

Running 4 tests for tests/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 26270)
[PASS] test_upgrade_noAuth_asBorrower() (gas: 28691)
[PASS] test_upgrade_paused() (gas: 47489)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 225077)
Test result: ok. 4 passed; 0 failed; finished in 1.06ms

Running 5 tests for tests/RejectNewTerms.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_mismatchedCommitment() (gas: 31765)
[PASS] test_rejectNewTerms_notBorrowerNorLender() (gas: 28881)
[PASS] test_rejectNewTerms_paused() (gas: 47484)
[PASS] test_rejectNewTerms_success_asBorrower() (gas: 43590)
[PASS] test_rejectNewTerms_success_asLender() (gas: 45795)
Test result: ok. 5 passed; 0 failed; finished in 1.10ms

Running 1 test for tests/DueDates.t.sol:DueDatesTests
[PASS] testFuzz_dueDates(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 55125, ~: 55157)
Test result: ok. 1 passed; 0 failed; finished in 44.76ms

Running 1 test for tests/DefaultDates.t.sol:DefaultDatesTests
[PASS] testFuzz_defaultDates(uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 58505, ~: 58506)
Test result: ok. 1 passed; 0 failed; finished in 51.70ms

Running 4 tests for tests/RemoveImpairment.t.sol:RemoveImpairmentTests
[PASS] testFuzz_removeImpairment_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 83703, ~: 83806)
[PASS] test_removeImpairment_notImpaired() (gas: 28767)
[PASS] test_removeImpairment_notLender() (gas: 24153)
[PASS] test_removeImpairment_paused() (gas: 44898)
Test result: ok. 4 passed; 0 failed; finished in 60.08ms

Running 11 tests for tests/GetPaymentBreakdown.t.sol:GetPaymentBreakdownTests
[PASS] testFuzz_getPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 266544, ~: 265706)
[PASS] test_getPaymentBreakdown_fixture1() (gas: 187470)
[PASS] test_getPaymentBreakdown_fixture10() (gas: 114122)
[PASS] test_getPaymentBreakdown_fixture2() (gas: 187327)
[PASS] test_getPaymentBreakdown_fixture3() (gas: 174601)
[PASS] test_getPaymentBreakdown_fixture4() (gas: 202336)
[PASS] test_getPaymentBreakdown_fixture5() (gas: 196338)
[PASS] test_getPaymentBreakdown_fixture6() (gas: 197454)
[PASS] test_getPaymentBreakdown_fixture7() (gas: 197530)
[PASS] test_getPaymentBreakdown_fixture8() (gas: 197588)
[PASS] test_getPaymentBreakdown_fixture9() (gas: 113957)
Test result: ok. 11 passed; 0 failed; finished in 66.06ms

Running 4 tests for tests/Impair.t.sol:ImpairTests
[PASS] testFuzz_impair_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 85577, ~: 85688)
[PASS] test_impair_loanNotFunded() (gas: 28726)
[PASS] test_impair_notLender() (gas: 24078)
[PASS] test_impair_paused() (gas: 44889)
Test result: ok. 4 passed; 0 failed; finished in 73.66ms

Running 6 tests for tests/CallPrincipal.t.sol:CallPrincipalTests
[PASS] testFuzz_callPrincipal_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 115520, ~: 115536)
[PASS] test_callPrincipal_insufficientPrincipalToReturn() (gas: 49971)
[PASS] test_callPrincipal_loanNotFunded() (gas: 28902)
[PASS] test_callPrincipal_notLender() (gas: 24242)
[PASS] test_callPrincipal_paused() (gas: 44997)
[PASS] test_callPrincipal_principalToReturnBoundary() (gas: 99106)
Test result: ok. 6 passed; 0 failed; finished in 88.51ms

Running 2 tests for tests/Factory.t.sol:FactoryTests
[PASS] test_createInstance(bytes32) (runs: 256, μ: 407780, ~: 407780)
[PASS] test_createInstance_cannotDeploy(bytes32) (runs: 256, μ: 35705, ~: 35705)
Test result: ok. 2 passed; 0 failed; finished in 95.01ms

Running 4 tests for tests/RemoveCall.t.sol:RemoveCallTests
[PASS] testFuzz_removeCall_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 87987, ~: 88054)
[PASS] test_removeCall_notCalled() (gas: 28680)
[PASS] test_removeCall_notLender() (gas: 24100)
[PASS] test_removeCall_paused() (gas: 44888)
Test result: ok. 4 passed; 0 failed; finished in 89.97ms

Running 10 tests for tests/Refinancer.t.sol:RefinancerTests
[PASS] test_refinancer_decreasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125028, ~: 125804)
[PASS] test_refinancer_increasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125543, ~: 125699)
[PASS] test_refinancer_multipleCalls_refinance(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 149160, ~: 149209)
[PASS] test_refinancer_setDelegateServiceFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 124735, ~: 124760)
[PASS] test_refinancer_setGracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 124686, ~: 124703)
[PASS] test_refinancer_setInterestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125740, ~: 125734)
[PASS] test_refinancer_setLateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125898, ~: 125972)
[PASS] test_refinancer_setLateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125861, ~: 125956)
[PASS] test_refinancer_setNoticePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125946, ~: 125852)
[PASS] test_refinancer_setPaymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125863, ~: 125767)
Test result: ok. 10 passed; 0 failed; finished in 184.92ms

Running 1 test for tests/MakePayment.t.sol:MakePaymentSuccessTests
[PASS] testFuzz_makePayment(uint256,uint256,uint256,uint256) (runs: 256, μ: 492659, ~: 496394)
Test result: ok. 1 passed; 0 failed; finished in 202.54ms
```

# `open-term-loan-manager (v1.0.0)`

```
Running 3 tests for tests/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notLoan() (gas: 26804)
[PASS] test_triggerDefault_notPoolDelegate() (gas: 48042)
[PASS] test_triggerDefault_paused() (gas: 45011)
Test result: ok. 3 passed; 0 failed; finished in 985.21µs

Running 4 tests for tests/Call.t.sol:RemoveCallTests
[PASS] test_removeCall_notLoan() (gas: 34278)
[PASS] test_removeCall_notPoolDelegate() (gas: 31694)
[PASS] test_removeCall_paused() (gas: 46986)
[PASS] test_removeCall_success() (gas: 157138)
Test result: ok. 4 passed; 0 failed; finished in 1.22ms

Running 4 tests for tests/Call.t.sol:CallPrincipalTests
[PASS] test_callPrincipal_notLoan() (gas: 34291)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 31708)
[PASS] test_callPrincipal_paused() (gas: 46965)
[PASS] test_callPrincipal_success() (gas: 210728)
Test result: ok. 4 passed; 0 failed; finished in 1.33ms

Running 4 tests for tests/RejectNewTerms.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_notLoan() (gas: 34898)
[PASS] test_rejectNewTerms_notPoolDelegate() (gas: 32318)
[PASS] test_rejectNewTerms_paused() (gas: 47585)
[PASS] test_rejectNewTerms_success() (gas: 351734)
Test result: ok. 4 passed; 0 failed; finished in 1.54ms

Running 3 tests for tests/ImpairLoan.t.sol:ImpairLoanLimitTests
[PASS] test_impairLoan_accountedInterestLimit() (gas: 317244)
[PASS] test_impairLoan_impairmentDateLimit() (gas: 263727)
[PASS] test_impairLoan_unrealizedLossesLimit() (gas: 302557)
Test result: ok. 3 passed; 0 failed; finished in 1.71ms

Running 4 tests for tests/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_noAuth() (gas: 99992)
[PASS] test_removeLoanImpairment_notLoan() (gas: 28713)
[PASS] test_removeLoanImpairment_paused() (gas: 29765)
[PASS] test_removeLoanImpairment_poolDelegateAfterGovernor() (gas: 94856)
Test result: ok. 4 passed; 0 failed; finished in 1.25ms

Running 2 tests for tests/TriggerDefault.t.sol:TriggerDefaultSuccessTests
[PASS] test_triggerDefault_success_impaired() (gas: 109439)
[PASS] test_triggerDefault_success_notImpaired() (gas: 118229)
Test result: ok. 2 passed; 0 failed; finished in 1.81ms

Running 7 tests for tests/Claim.t.sol:ClaimFailureTests
[PASS] test_claim_invalidState1() (gas: 56549)
[PASS] test_claim_invalidState2() (gas: 56560)
[PASS] test_claim_invalidState3() (gas: 56584)
[PASS] test_claim_invalidState4() (gas: 79972)
[PASS] test_claim_notLoan() (gas: 26802)
[PASS] test_claim_notPaused() (gas: 27900)
[PASS] test_claim_reentrancy() (gas: 186)
Test result: ok. 7 passed; 0 failed; finished in 1.66ms

Running 3 tests for tests/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentSuccessTests
[PASS] test_removeLoanImpairment_acl_governor_success() (gas: 80045)
[PASS] test_removeLoanImpairment_success() (gas: 209597)
[PASS] test_removeLoanImpairment_success_alreadyUnimpaired() (gas: 262693)
Test result: ok. 3 passed; 0 failed; finished in 1.80ms

Running 4 tests for tests/ImpairLoan.t.sol:ImpairLoanSuccessTests
[PASS] test_impairLoan_acl_governor() (gas: 80296)
[PASS] test_impairLoan_acl_poolDelegate() (gas: 87913)
[PASS] test_impairLoan_success() (gas: 213576)
[PASS] test_impairLoan_success_alreadyImpaired() (gas: 265104)
Test result: ok. 4 passed; 0 failed; finished in 1.86ms

Running 5 tests for tests/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 33882)
[PASS] test_upgrade_notScheduled() (gas: 35226)
[PASS] test_upgrade_paused() (gas: 45028)
[PASS] test_upgrade_success_asPoolDelegate() (gas: 255723)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 232691)
Test result: ok. 5 passed; 0 failed; finished in 1.43ms

Running 4 tests for tests/ProposeNewTerms.t.sol:ProposeNewTermsTests
[PASS] test_proposeNewTerms_notLoan() (gas: 37443)
[PASS] test_proposeNewTerms_notPoolDelegate() (gas: 34818)
[PASS] test_proposeNewTerms_paused() (gas: 50175)
[PASS] test_proposeNewTerms_success() (gas: 351813)
Test result: ok. 4 passed; 0 failed; finished in 1.53ms

Running 6 tests for tests/DistributeLiquidationFunds.t.sol:DistributeLiquidationFundsFailureTests
[PASS] test_distributeLiquidationFunds_transferBorrower() (gas: 56191)
[PASS] test_distributeLiquidationFunds_transferPool() (gas: 89171)
[PASS] test_distributeLiquidationFunds_transferTreasury() (gas: 127657)
[PASS] test_distributeLiquidationFunds_zeroBorrower() (gas: 26758)
[PASS] test_distributeLiquidationFunds_zeroPool() (gas: 57662)
[PASS] test_distributeLiquidationFunds_zeroTreasury() (gas: 96159)
Test result: ok. 6 passed; 0 failed; finished in 1.63ms

Running 6 tests for tests/CreateInstance.t.sol:CreateInstanceTests
[PASS] testFail_createInstance_collision() (gas: 8937393460516737834)
[PASS] testFail_createInstance_notPool() (gas: 176076)
[PASS] test_createInstance_cannotDeploy() (gas: 19040)
[PASS] test_createInstance_invalidFactory() (gas: 192410)
[PASS] test_createInstance_invalidInstance() (gas: 197789)
[PASS] test_createInstance_success() (gas: 283515)
Test result: ok. 6 passed; 0 failed; finished in 2.07ms

Running 9 tests for tests/Fund.t.sol:FundFailureTests
[PASS] test_fund_failedApproval() (gas: 246702)
[PASS] test_fund_fundingMismatch() (gas: 237336)
[PASS] test_fund_inactiveLoan() (gas: 130422)
[PASS] test_fund_invalidBorrower() (gas: 105614)
[PASS] test_fund_invalidFactory() (gas: 49180)
[PASS] test_fund_invalidLoan() (gas: 80264)
[PASS] test_fund_notPoolDelegate() (gas: 34629)
[PASS] test_fund_paused() (gas: 44914)
[PASS] test_fund_reentrancy() (gas: 1656022)
Test result: ok. 9 passed; 0 failed; finished in 2.17ms

Running 3 tests for tests/ImpairLoan.t.sol:ImpairLoanFailureTests
[PASS] test_impairLoan_notLoan() (gas: 28724)
[PASS] test_impairLoan_notPoolDelegateOrGovernor() (gas: 57742)
[PASS] test_impairLoan_paused() (gas: 29809)
Test result: ok. 3 passed; 0 failed; finished in 1.07ms

Running 6 tests for tests/DistributeClaimedFunds.t.sol:DistributeClaimedFundsFailureTests
[PASS] test_distributeClaimFunds_platformTransfer() (gas: 106984)
[PASS] test_distributeClaimFunds_poolTransfer() (gas: 61248)
[PASS] test_distributeClaimFunds_zeroDelegate() (gas: 68504)
[PASS] test_distributeClaimFunds_zeroPool() (gas: 29799)
[PASS] test_distributeClaimFunds_zeroPoolDelegate() (gas: 56122)
[PASS] test_distributeClaimFunds_zeroTreasury() (gas: 75552)
Test result: ok. 6 passed; 0 failed; finished in 2.46ms

Running 8 tests for tests/Claim.t.sol:ClaimTests
[PASS] test_claim() (gas: 254025)
[PASS] test_claim_closingLoan() (gas: 222510)
[PASS] test_claim_impaired() (gas: 256541)
[PASS] test_claim_impaired_requestingPrincipal() (gas: 322362)
[PASS] test_claim_impaired_returningPrincipal() (gas: 293007)
[PASS] test_claim_requestingPrincipalIncrease() (gas: 345370)
[PASS] test_claim_returnMorePrincipal() (gas: 254691)
[PASS] test_claim_returningPrincipal() (gas: 266005)
Test result: ok. 8 passed; 0 failed; finished in 3.53ms

Running 1 test for tests/InternalFunctions.t.sol:UpdateUnrealizedLossesTests
[PASS] testFuzz_updateUnrealizedLosses(uint256,int256) (runs: 256, μ: 39378, ~: 41819)
Test result: ok. 1 passed; 0 failed; finished in 20.60ms

Running 1 test for tests/InternalFunctions.t.sol:UpdatePrincipalOutTests
[PASS] testFuzz_updatePrincipalOut(uint256,int256) (runs: 256, μ: 39348, ~: 41743)
Test result: ok. 1 passed; 0 failed; finished in 25.72ms

Running 1 test for tests/InternalFunctions.t.sol:UpdateAccountingStateTests
[PASS] testFuzz_updateInterestAccounting(uint256,uint256,uint256,int256,int256) (runs: 256, μ: 76279, ~: 80103)
Test result: ok. 1 passed; 0 failed; finished in 40.78ms

Running 1 test for tests/DistributeLiquidationFunds.t.sol:DistributeLiquidationFundsTests
[PASS] testFuzz_distributeLiquidationFunds(uint256,uint256,uint256,uint256) (runs: 256, μ: 146109, ~: 135867)
Test result: ok. 1 passed; 0 failed; finished in 47.27ms

Running 1 test for tests/DistributeClaimedFunds.t.sol:DistributeClaimedFundsTests
[PASS] testFuzz_distributeClaimFunds(int256,uint256,uint256,uint256,bool) (runs: 256, μ: 167659, ~: 161113)
Test result: ok. 1 passed; 0 failed; finished in 51.97ms

Running 5 tests for tests/Fund.t.sol:FundSuccessTests
[PASS] testFuzz_fund_multipleLoans(uint256) (runs: 256, μ: 36134063, ~: 35791068)
[PASS] test_fund_managementFeeRateLimits() (gas: 1855841)
[PASS] test_fund_paymentIssuanceRateLimit() (gas: 1941545)
[PASS] test_fund_principalLimit() (gas: 2040778)
[PASS] test_fund_startDateAndDomainStartLimit() (gas: 1963343)
Test result: ok. 5 passed; 0 failed; finished in 1.98s
```

# `pool-v2 (v2.0.0)`

```
Running 3 tests for tests/Pool.t.sol:ConstructorTests
[PASS] test_constructor_invalidApproval() (gas: 3716791)
[PASS] test_constructor_invalidDecimals() (gas: 3625220)
[PASS] test_constructor_zeroManager() (gas: 3373789)
Test result: ok. 3 passed; 0 failed; finished in 1.80ms

Running 3 tests for tests/PoolManager.t.sol:CompleteConfigurationTests
[PASS] test_completeConfiguration_alreadyConfigured() (gas: 35274)
[PASS] test_completeConfiguration_paused() (gas: 51894)
[PASS] test_completeConfiguration_success() (gas: 31209)
Test result: ok. 3 passed; 0 failed; finished in 2.89ms

Running 5 tests for tests/PoolManager.t.sol:SetDelegateManagementFeeRate_SetterTests
[PASS] test_setDelegateManagementFeeRate_notPoolDelegate() (gas: 39615)
[PASS] test_setDelegateManagementFeeRate_oob() (gas: 75484)
[PASS] test_setDelegateManagementFeeRate_paused() (gas: 56624)
[PASS] test_setDelegateManagementFeeRate_success_asPoolDelegate() (gas: 66394)
[PASS] test_setDelegateManagementFeeRate_success_whenNotConfigured() (gas: 52888)
Test result: ok. 5 passed; 0 failed; finished in 2.87ms

Running 5 tests for tests/PoolManager.t.sol:SetWithdrawalManager_SetterTests
[PASS] test_setWithdrawalManager_configured() (gas: 37561)
[PASS] test_setWithdrawalManager_invalidFactory() (gas: 71501)
[PASS] test_setWithdrawalManager_invalidInstance() (gas: 50517)
[PASS] test_setWithdrawalManager_paused() (gas: 56727)
[PASS] test_setWithdrawalManager_success_asPoolDelegate() (gas: 48942)
Test result: ok. 5 passed; 0 failed; finished in 2.82ms

Running 3 tests for tests/PoolManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 31147)
[PASS] test_setImplementation_paused() (gas: 54016)
[PASS] test_setImplementation_success() (gas: 41132)
Test result: ok. 3 passed; 0 failed; finished in 2.98ms

Running 3 tests for tests/PoolManager.t.sol:DepositCoverTests
[PASS] test_depositCover_insufficientApproval() (gas: 104597)
[PASS] test_depositCover_paused() (gas: 51847)
[PASS] test_depositCover_success() (gas: 88422)
Test result: ok. 3 passed; 0 failed; finished in 4.38ms

Running 5 tests for tests/PoolManager.t.sol:TriggerDefault
[PASS] test_triggerDefault_invalidFactory() (gas: 109290)
[PASS] test_triggerDefault_notAuthorized() (gas: 44562)
[PASS] test_triggerDefault_paused() (gas: 41724)
[PASS] test_triggerDefault_success_asGovernor() (gas: 81781)
[PASS] test_triggerDefault_success_asPoolDelegate() (gas: 77760)
Test result: ok. 5 passed; 0 failed; finished in 3.22ms

Running 4 tests for tests/PoolManager.t.sol:SetIsLoanManager_SetterTests
[PASS] test_setIsLoanManager_invalidLM() (gas: 436490)
[PASS] test_setIsLoanManager_notPoolDelegate() (gas: 33373)
[PASS] test_setIsLoanManager_paused() (gas: 54185)
[PASS] test_setIsLoanManager_success() (gas: 58536)
Test result: ok. 4 passed; 0 failed; finished in 2.93ms

Running 6 tests for tests/PoolManager.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 35326)
[PASS] test_upgrade_notScheduled() (gas: 36793)
[PASS] test_upgrade_paused() (gas: 52145)
[PASS] test_upgrade_successWithPoolDelegate() (gas: 98846)
[PASS] test_upgrade_successWithSecurityAdmin() (gas: 96871)
[PASS] test_upgrade_upgradeFailed() (gas: 89960)
Test result: ok. 6 passed; 0 failed; finished in 3.76ms

Running 4 tests for tests/PoolManager.t.sol:SetLiquidityCap_SetterTests
[PASS] test_setLiquidityCap_notPoolDelegate() (gas: 37429)
[PASS] test_setLiquidityCap_paused() (gas: 54416)
[PASS] test_setLiquidityCap_success_asPoolDelegate() (gas: 64147)
[PASS] test_setLiquidityCap_success_whenNotConfigured() (gas: 50587)
Test result: ok. 4 passed; 0 failed; finished in 3.06ms

Running 9 tests for tests/PoolManager.t.sol:FinishCollateralLiquidation
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 195635)
[PASS] test_finishCollateralLiquidation_paused() (gas: 36973)
[PASS] test_finishCollateralLiquidation_success_coverLeftOver() (gas: 264360)
[PASS] test_finishCollateralLiquidation_success_exceedMaxCoverLiquidationPercentAmount() (gas: 261708)
[PASS] test_finishCollateralLiquidation_success_fullCoverLiquidation_preexistingLoss() (gas: 265536)
[PASS] test_finishCollateralLiquidation_success_noCoverLeftOver() (gas: 244427)
[PASS] test_finishCollateralLiquidation_success_noCover_asGovernor() (gas: 228094)
[PASS] test_finishCollateralLiquidation_success_noCover_asPoolDelegate() (gas: 221999)
[PASS] test_finishCollateralLiquidation_success_noRemainingLossAfterCollateralLiquidation() (gas: 229614)
Test result: ok. 9 passed; 0 failed; finished in 6.40ms

Running 3 tests for tests/PoolManager.t.sol:SetOpenToPublic_SetterTests
[PASS] test_setOpenToPublic_notPoolDelegate() (gas: 30927)
[PASS] test_setOpenToPublic_paused() (gas: 54428)
[PASS] test_setOpenToPublic_success() (gas: 41948)
Test result: ok. 3 passed; 0 failed; finished in 2.64ms

Running 7 tests for tests/PoolManager.t.sol:WithdrawCoverTests
[PASS] test_withdrawCover_noRequirement() (gas: 93719)
[PASS] test_withdrawCover_notPoolDelegate() (gas: 151941)
[PASS] test_withdrawCover_paused() (gas: 54795)
[PASS] test_withdrawCover_success() (gas: 145229)
[PASS] test_withdrawCover_success_zeroRecipient() (gas: 145054)
[PASS] test_withdrawCover_tryWithdrawBelowRequired() (gas: 191867)
[PASS] test_withdrawCover_withdrawMoreThanBalance() (gas: 81435)
Test result: ok. 7 passed; 0 failed; finished in 3.27ms

Running 3 tests for tests/PoolManager.t.sol:SetPendingPoolDelegate_SetterTests
[PASS] test_setPendingPoolDelegate_notPoolDelegate() (gas: 33215)
[PASS] test_setPendingPoolDelegate_paused() (gas: 56650)
[PASS] test_setPendingPoolDelegate_success() (gas: 62301)
Test result: ok. 3 passed; 0 failed; finished in 2.64ms

Running 7 tests for tests/PoolManagerFactory.t.sol:PoolManagerFactoryFailureTest
[PASS] test_createInstance_failWithActivePoolDelegate() (gas: 260052)
[PASS] test_createInstance_failWithDisallowedAsset() (gas: 241388)
[PASS] test_createInstance_failWithInvalidPoolDelegate() (gas: 231461)
[PASS] test_createInstance_failWithNonERC20Asset() (gas: 237850)
[PASS] test_createInstance_failWithZeroAddressPoolDelegate() (gas: 188281)
[PASS] test_createInstance_failWithZeroAdmin() (gas: 3373385)
[PASS] test_createInstance_notPoolDeployer() (gas: 3085731)
Test result: ok. 7 passed; 0 failed; finished in 3.11ms

Running 5 tests for tests/PoolManager.t.sol:HandleCoverTests
[PASS] test_handleCover_feesAndSomeLosses() (gas: 118022)
[PASS] test_handleCover_fullCoverage() (gas: 137924)
[PASS] test_handleCover_halfCoverage() (gas: 144082)
[PASS] test_handleCover_noCover() (gas: 63374)
[PASS] test_handleCover_onlyFees() (gas: 107786)
Test result: ok. 5 passed; 0 failed; finished in 4.74ms

Running 1 test for tests/PoolManagerFactory.t.sol:PoolManagerFactoryTest
[PASS] test_createInstance() (gas: 3228114)
Test result: ok. 1 passed; 0 failed; finished in 1.92ms

Running 2 tests for tests/PoolManager.t.sol:MaxWithdrawTests
[PASS] testFuzz_maxWithdraw(address) (runs: 256, μ: 16437, ~: 16437)
[PASS] test_maxWithdraw() (gas: 16254)
Test result: ok. 2 passed; 0 failed; finished in 14.68ms

Running 5 tests for tests/PoolManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 34165)
[PASS] test_migrate_invalidPoolDelegateCover() (gas: 39236)
[PASS] test_migrate_notFactory() (gas: 31540)
[PASS] test_migrate_paused() (gas: 54331)
[PASS] test_migrate_success() (gas: 41876)
Test result: ok. 5 passed; 0 failed; finished in 2.85ms

Running 5 tests for tests/PoolManager.t.sol:ProcessRedeemTests
[PASS] test_processRedeem_noApproval() (gas: 131637)
[PASS] test_processRedeem_notWithdrawalManager() (gas: 36471)
[PASS] test_processRedeem_paused() (gas: 52299)
[PASS] test_processRedeem_success() (gas: 42762)
[PASS] test_processRedeem_success_notSender() (gas: 164032)
Test result: ok. 5 passed; 0 failed; finished in 2.96ms

Running 10 tests for tests/PoolManager.t.sol:RequestFundsTests
[PASS] test_requestFunds_insufficientCoverBoundary() (gas: 216581)
[PASS] test_requestFunds_invalidFactory() (gas: 50401)
[PASS] test_requestFunds_invalidInstance() (gas: 55673)
[PASS] test_requestFunds_lockedLiquidityBoundary() (gas: 241719)
[PASS] test_requestFunds_notLM() (gas: 56460)
[PASS] test_requestFunds_paused() (gas: 37089)
[PASS] test_requestFunds_success() (gas: 120805)
[PASS] test_requestFunds_zeroAddress() (gas: 79935)
[PASS] test_requestFunds_zeroPrincipal() (gas: 45136)
[PASS] test_requestFunds_zeroSupply() (gas: 65334)
Test result: ok. 10 passed; 0 failed; finished in 3.96ms

Running 6 tests for tests/Pool.t.sol:DepositTests
[PASS] testFuzz_deposit_badApprove(uint256) (runs: 256, μ: 159227, ~: 160191)
[PASS] testFuzz_deposit_insufficientBalance(uint256) (runs: 256, μ: 162813, ~: 162704)
[PASS] test_deposit_checkCall() (gas: 131035)
[PASS] test_deposit_reentrancy() (gas: 181730)
[PASS] test_deposit_zeroReceiver() (gas: 109185)
[PASS] test_deposit_zeroShares() (gas: 109080)
Test result: ok. 6 passed; 0 failed; finished in 44.02ms

Running 7 tests for tests/Pool.t.sol:ConvertToSharesTests
[PASS] testFuzz_convertToShares(uint256,uint256,uint256) (runs: 256, μ: 166895, ~: 173342)
[PASS] test_convertToShares_decreasedExchangeRate() (gas: 173887)
[PASS] test_convertToShares_increasedExchangeRate() (gas: 173964)
[PASS] test_convertToShares_initialExchangeRate() (gas: 173909)
[PASS] test_convertToShares_initialState() (gas: 20774)
[PASS] test_convertToShares_prematureYield() (gas: 40697)
[PASS] test_convertToShares_worthlessShares() (gas: 161291)
Test result: ok. 7 passed; 0 failed; finished in 44.72ms

Running 3 tests for tests/PoolManager.t.sol:SetActive_SetterTests
[PASS] test_setActive_notGlobals() (gas: 33588)
[PASS] test_setActive_paused() (gas: 52460)
[PASS] test_setActive_success() (gas: 46929)
Test result: ok. 3 passed; 0 failed; finished in 2.76ms

Running 4 tests for tests/PoolManager.t.sol:MaxDepositTests
[PASS] test_maxDeposit_liquidityCap() (gas: 255241)
[PASS] test_maxDeposit_liquidityCap(address,address,uint256,uint256) (runs: 256, μ: 129627, ~: 132333)
[PASS] test_maxDeposit_privatePool() (gas: 137473)
[PASS] test_maxDeposit_publicPool() (gas: 129930)
Test result: ok. 4 passed; 0 failed; finished in 28.27ms

Running 3 tests for tests/PoolManager.t.sol:SetAllowedLender_SetterTests
[PASS] test_setAllowedLender_notPoolDelegate() (gas: 31229)
[PASS] test_setAllowedLender_paused() (gas: 52712)
[PASS] test_setAllowedLender_success() (gas: 50393)
Test result: ok. 3 passed; 0 failed; finished in 2.67ms

Running 4 tests for tests/Pool.t.sol:ConvertToExitAssetsTests
[PASS] testFuzz_convertToExitAssets(uint256,uint256,uint256,uint256) (runs: 256, μ: 194410, ~: 196851)
[PASS] testFuzz_convertToExitAssets_zeroSupply(uint256) (runs: 256, μ: 7880, ~: 7880)
[PASS] test_convertToExitAssets() (gas: 218455)
[PASS] test_convertToExitAssets_zeroSupply() (gas: 11273)
Test result: ok. 4 passed; 0 failed; finished in 48.21ms

Running 7 tests for tests/Pool.t.sol:ConvertToAssetsTests
[PASS] testFuzz_convertToAssets(uint256,uint256,uint256) (runs: 256, μ: 165031, ~: 173252)
[PASS] test_convertToAssets_decreasedExchangeRate() (gas: 173869)
[PASS] test_convertToAssets_increasedExchangeRate() (gas: 173924)
[PASS] test_convertToAssets_initialExchangeRate() (gas: 173880)
[PASS] test_convertToAssets_initialState() (gas: 20671)
[PASS] test_convertToAssets_prematureYield() (gas: 40548)
[PASS] test_convertToAssets_worthlessShares() (gas: 154014)
Test result: ok. 7 passed; 0 failed; finished in 49.57ms

Running 5 tests for tests/Pool.t.sol:RequestWithdraw
[PASS] testFuzz_requestWithdraw_failNotEnabled(uint256) (runs: 256, μ: 81576, ~: 82575)
[PASS] test_requestWithdraw_checkCall() (gas: 79285)
[PASS] test_requestWithdraw_failWithoutApproval() (gas: 42448)
[PASS] test_requestWithdraw_insufficientApproval() (gas: 113316)
[PASS] test_requestWithdraw_withApproval_failNotEnabled() (gas: 80182)
Test result: ok. 5 passed; 0 failed; finished in 42.96ms

Running 3 tests for tests/Pool.t.sol:WithdrawTests
[PASS] testFuzz_withdraw_failNotEnabled(uint256) (runs: 256, μ: 31490, ~: 31490)
[PASS] test_withdraw_checkCall() (gas: 79325)
[PASS] test_withdraw_failNotEnabled() (gas: 31365)
Test result: ok. 3 passed; 0 failed; finished in 22.76ms

Running 3 tests for tests/PoolDelegateCover.t.sol:PoolDelegateCoverTests
[PASS] test_moveFunds_badTransfer() (gas: 59699)
[PASS] test_moveFunds_notManager() (gas: 51352)
[PASS] test_moveFunds_success() (gas: 59753)
Test result: ok. 3 passed; 0 failed; finished in 417.92µs

Running 4 tests for tests/PoolDeployer.t.sol:PoolDeployerTests
[PASS] test_deployPool_invalidPoolDelegate() (gas: 131877)
[PASS] test_deployPool_success_withCoverRequired() (gas: 3910717)
[PASS] test_deployPool_success_withoutCoverRequired() (gas: 3844556)
[PASS] test_deployPool_transferFailed() (gas: 3799751)
Test result: ok. 4 passed; 0 failed; finished in 12.31ms

Running 4 tests for tests/PoolManager.t.sol:AcceptPoolDelegate_SetterTests
[PASS] test_acceptPoolDelegate_globalsTransferFails() (gas: 60882)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 30881)
[PASS] test_acceptPoolDelegate_paused() (gas: 54390)
[PASS] test_acceptPoolDelegate_success() (gas: 52221)
Test result: ok. 4 passed; 0 failed; finished in 3.50ms

Running 5 tests for tests/PoolManager.t.sol:AddLoanManager_SetterTests
[PASS] test_addLoanManager_invalidFactory() (gas: 38606)
[PASS] test_addLoanManager_notPoolDelegate() (gas: 37772)
[PASS] test_addLoanManager_paused() (gas: 37659)
[PASS] test_addLoanManager_success_asPoolDelegate() (gas: 170455)
[PASS] test_addLoanManager_success_whenNotConfigured() (gas: 156988)
Test result: ok. 5 passed; 0 failed; finished in 5.66ms

Running 32 tests for tests/PoolManager.t.sol:CanCallTests
[PASS] test_canCall_depositWithPermit_lenderNotAllowed() (gas: 115001)
[PASS] test_canCall_depositWithPermit_liquidityCapExceeded() (gas: 87022)
[PASS] test_canCall_depositWithPermit_notActive() (gas: 39421)
[PASS] test_canCall_depositWithPermit_notOpenToPublic() (gas: 96766)
[PASS] test_canCall_deposit_lenderNotAllowed() (gas: 113821)
[PASS] test_canCall_deposit_liquidityCapExceeded() (gas: 86385)
[PASS] test_canCall_deposit_notActive() (gas: 38733)
[PASS] test_canCall_deposit_notOpenToPublic() (gas: 95564)
[PASS] test_canCall_invalidFunctionId() (gas: 71747)
[PASS] test_canCall_mintWithPermit_lenderNotAllowed() (gas: 130511)
[PASS] test_canCall_mintWithPermit_liquidityCapExceeded() (gas: 98041)
[PASS] test_canCall_mintWithPermit_notActive() (gas: 60938)
[PASS] test_canCall_mintWithPermit_notOpenToPublic() (gas: 112320)
[PASS] test_canCall_mint_lenderNotAllowed() (gas: 129114)
[PASS] test_canCall_mint_liquidityCapExceeded() (gas: 97249)
[PASS] test_canCall_mint_notActive() (gas: 60120)
[PASS] test_canCall_mint_notOpenToPublic() (gas: 110899)
[PASS] test_canCall_paused_redeem() (gas: 49928)
[PASS] test_canCall_paused_removeShares() (gas: 49972)
[PASS] test_canCall_paused_requestRedeem() (gas: 49928)
[PASS] test_canCall_paused_requestWithdraw() (gas: 49951)
[PASS] test_canCall_paused_transfer() (gas: 49907)
[PASS] test_canCall_paused_withdraw() (gas: 49885)
[PASS] test_canCall_redeem() (gas: 28794)
[PASS] test_canCall_removeShares() (gas: 28586)
[PASS] test_canCall_requestRedeem() (gas: 28656)
[PASS] test_canCall_requestWithdraw() (gas: 28586)
[PASS] test_canCall_transferFrom_notOpenToPublic() (gas: 83782)
[PASS] test_canCall_transferFrom_recipientNotAllowed() (gas: 102017)
[PASS] test_canCall_transfer_notOpenToPublic() (gas: 83398)
[PASS] test_canCall_transfer_recipientNotAllowed() (gas: 101634)
[PASS] test_canCall_withdraw() (gas: 28600)
Test result: ok. 32 passed; 0 failed; finished in 13.69ms

Running 5 tests for tests/PoolManager.t.sol:MaxMintTests
[PASS] testFuzz_maxMint_liquidityCap(address,address,uint256,uint256,uint256) (runs: 256, μ: 227469, ~: 227511)
[PASS] test_maxMint_liquidityCap_exchangeRateGtOne() (gas: 370427)
[PASS] test_maxMint_liquidityCap_exchangeRateOneToOne() (gas: 391878)
[PASS] test_maxMint_privatePool() (gas: 302440)
[PASS] test_maxMint_publicPool() (gas: 289034)
Test result: ok. 5 passed; 0 failed; finished in 106.21ms

Running 11 tests for tests/Pool.t.sol:MintWithPermitTests
[PASS] testFuzz_mintWithPermit_insufficientBalance(uint256) (runs: 256, μ: 205691, ~: 205578)
[PASS] test_mintWithPermit_badNonce() (gas: 132226)
[PASS] test_mintWithPermit_checkCall() (gas: 148426)
[PASS] test_mintWithPermit_insufficientPermit() (gas: 97194)
[PASS] test_mintWithPermit_notStakerSignature() (gas: 134167)
[PASS] test_mintWithPermit_pastDeadline() (gas: 105949)
[PASS] test_mintWithPermit_reentrancy() (gas: 224468)
[PASS] test_mintWithPermit_replay() (gas: 247625)
[PASS] test_mintWithPermit_zeroAddress() (gas: 105350)
[PASS] test_mintWithPermit_zeroReceiver() (gas: 151553)
[PASS] test_mintWithPermit_zeroShares() (gas: 151670)
Test result: ok. 11 passed; 0 failed; finished in 160.89ms

Running 8 tests for tests/Pool.t.sol:RedeemTests
[PASS] test_redeem_checkCall() (gas: 79420)
[PASS] test_redeem_insufficientAmount() (gas: 64117)
[PASS] test_redeem_insufficientApprove() (gas: 174719)
[PASS] test_redeem_reentrancy() (gas: 137371)
[PASS] test_redeem_success() (gas: 131617)
[PASS] test_redeem_success_differentUser() (gas: 207596)
[PASS] test_redeem_zeroAssets() (gas: 91804)
[PASS] test_redeem_zeroShares() (gas: 48543)
Test result: ok. 8 passed; 0 failed; finished in 6.32ms

Running 4 tests for tests/Pool.t.sol:RemoveSharesTests
[PASS] test_removeShares_checkCall() (gas: 53041)
[PASS] test_removeShares_failWithoutApproval() (gas: 32568)
[PASS] test_removeShares_insufficientApproval() (gas: 65056)
[PASS] test_removeShares_withApproval() (gas: 46433)
Test result: ok. 4 passed; 0 failed; finished in 6.59ms

Running 6 tests for tests/Pool.t.sol:MintTests
[PASS] testFuzz_mint_badApprove(uint256) (runs: 256, μ: 159364, ~: 160261)
[PASS] testFuzz_mint_insufficientBalance(uint256) (runs: 256, μ: 162935, ~: 162819)
[PASS] test_mint_checkCall() (gas: 133384)
[PASS] test_mint_reentrancy() (gas: 181778)
[PASS] test_mint_zeroReceiver() (gas: 109211)
[PASS] test_mint_zeroShares() (gas: 109128)
Test result: ok. 6 passed; 0 failed; finished in 44.21ms

Running 6 tests for tests/Pool.t.sol:RequestRedeemTests
[PASS] test_requestRedeem_checkCall() (gas: 79209)
[PASS] test_requestRedeem_failWithoutApproval() (gas: 33735)
[PASS] test_requestRedeem_insufficientApproval() (gas: 96021)
[PASS] test_requestRedeem_withApproval() (gas: 71568)
[PASS] test_requestRedeem_zeroShares() (gas: 64856)
[PASS] test_requestRedeem_zeroSharesAndNotOwnerAndNoAllowance() (gas: 41676)
Test result: ok. 6 passed; 0 failed; finished in 2.84ms

Running 10 tests for tests/Pool.t.sol:DepositWithPermitTests
[PASS] testFuzz_depositWithPermit_insufficientBalance(uint256) (runs: 256, μ: 205513, ~: 205412)
[PASS] test_depositWithPermit_badNonce() (gas: 127831)
[PASS] test_depositWithPermit_checkCall() (gas: 148319)
[PASS] test_depositWithPermit_notStakerSignature() (gas: 129794)
[PASS] test_depositWithPermit_pastDeadline() (gas: 101579)
[PASS] test_depositWithPermit_reentrancy() (gas: 224399)
[PASS] test_depositWithPermit_replay() (gas: 224066)
[PASS] test_depositWithPermit_zeroAddress() (gas: 100983)
[PASS] test_depositWithPermit_zeroReceiver() (gas: 151518)
[PASS] test_depositWithPermit_zeroShares() (gas: 131763)
Test result: ok. 10 passed; 0 failed; finished in 146.53ms

Running 7 tests for tests/Pool.t.sol:PreviewDepositTests
[PASS] testFuzz_previewDeposit(uint256,uint256,uint256) (runs: 256, μ: 167750, ~: 173447)
[PASS] test_previewDeposit_decreasedExchangeRate() (gas: 174135)
[PASS] test_previewDeposit_increasedExchangeRate() (gas: 174148)
[PASS] test_previewDeposit_initialExchangeRate() (gas: 174071)
[PASS] test_previewDeposit_initialState() (gas: 20891)
[PASS] test_previewDeposit_prematureYield() (gas: 40813)
[PASS] test_previewDeposit_worthlessShares() (gas: 161373)
Test result: ok. 7 passed; 0 failed; finished in 37.04ms

Running 7 tests for tests/Pool.t.sol:PreviewMintTests
[PASS] testFuzz_previewMint(uint256,uint256,uint256) (runs: 256, μ: 169988, ~: 176548)
[PASS] test_previewMint_decreasedExchangeRate() (gas: 174519)
[PASS] test_previewMint_increasedExchangeRate() (gas: 174574)
[PASS] test_previewMint_initialExchangeRate() (gas: 174542)
[PASS] test_previewMint_initialState() (gas: 20840)
[PASS] test_previewMint_prematureYield() (gas: 40729)
[PASS] test_previewMint_worthlessShares() (gas: 154609)
Test result: ok. 7 passed; 0 failed; finished in 41.59ms

Running 7 tests for tests/PoolMintFrontrunTests.t.sol:PoolMintFrontrunTests
[PASS] testFuzz_depositFrontRun_honestOnePercentHarm(uint256) (runs: 256, μ: 4386300, ~: 4386345)
[PASS] testFuzz_depositFrontRun_honestTenPercentHarm(uint256) (runs: 256, μ: 4386313, ~: 4386346)
[PASS] testFuzz_depositFrontRun_theftThwarted(uint256) (runs: 256, μ: 4393366, ~: 4393383)
[PASS] test_depositFrontRun_theft() (gas: 4350555)
[PASS] test_depositFrontRun_theftReverted() (gas: 4310792)
[PASS] test_depositFrontRun_theftThwarted() (gas: 4395249)
[PASS] test_depositFrontRun_zeroShares() (gas: 4343739)
Test result: ok. 7 passed; 0 failed; finished in 314.17ms

Running 13 tests for tests/ERC20.t.sol:Pool_ERC20Test
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 31136, ~: 31758)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 29372, ~: 41880)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 35505, ~: 35514)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 36427, ~: 38405)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 38224, ~: 38380)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 787588, ~: 781402)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 52540, ~: 54406)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 71185, ~: 73362)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 356367, ~: 366348)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 365122, ~: 367149)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 364991, ~: 364438)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 348198, ~: 346123)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 356412, ~: 356413)
Test result: ok. 13 passed; 0 failed; finished in 337.87ms

Running 14 tests for tests/ERC20.t.sol:Pool_ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 85721, ~: 86429)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 257927, ~: 257928)
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
Test result: ok. 14 passed; 0 failed; finished in 1.10s
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
