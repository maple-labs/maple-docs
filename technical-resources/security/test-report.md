# Test Reports

Below is an report of all smart contract level tests that are run against the protocol, in all repos.

Current number of tests in this report is: **4377 tests**.

## `maple-core-v2`

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewDepositTests
[PASS] test_previewDeposit_multipleUsers() (gas: 448912)
[PASS] test_previewDeposit_multipleUsers_changeTotalAssets() (gas: 471596)
[PASS] test_previewDeposit_nonZeroTotalSupply() (gas: 273218)
[PASS] test_previewDeposit_zeroTotalSupply() (gas: 10411)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 74.89ms (4.06ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewMintTests
[PASS] test_previewMint_multipleUsers() (gas: 449301)
[PASS] test_previewMint_multipleUsers_changeTotalAssets() (gas: 471980)
[PASS] test_previewMint_nonZeroTotalSupply() (gas: 273748)
[PASS] test_previewMint_zeroTotalSupply() (gas: 10296)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 55.02ms (2.87ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewRedeemTests
[PASS] test_previewRedeem_invalidShares() (gas: 401591)
[PASS] test_previewRedeem_lockedShares_inExitWindow() (gas: 424755)
[PASS] test_previewRedeem_lockedShares_notInExitWindow() (gas: 404857)
[PASS] test_previewRedeem_noLockedShares_notInExitWindow() (gas: 33887)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 30.39ms (1.81ms CPU time)

Ran 7 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewRedeemWithQueueWMTests
[PASS] test_previewRedeem_emptyRedemption_fullLiquidity() (gas: 118660)
[PASS] test_previewRedeem_emptyRedemption_partialLiquidity() (gas: 118705)
[PASS] test_previewRedeem_fullRedemption_fullLiquidity() (gas: 118938)
[PASS] test_previewRedeem_fullRedemption_partialLiquidity() (gas: 118953)
[PASS] test_previewRedeem_insufficientShares() (gas: 36106)
[PASS] test_previewRedeem_partialRedemption_fullLiquidity() (gas: 119195)
[PASS] test_previewRedeem_partialRedemption_partialLiquidity() (gas: 119243)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 32.22ms (1.80ms CPU time)

Ran 3 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveClaimRewardsTests
[PASS] testFork_aaveStrategy_claimRewards_paused() (gas: 59583)
[PASS] testFork_aaveStrategy_claimRewards_success() (gas: 701229)
[PASS] testFork_aaveStrategy_claimRewards_unauthorized() (gas: 67726)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 254.62ms (3.58ms CPU time)

Ran 6 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewWithdrawTests
[PASS] testDeepFuzz_previewWithdraw(uint256) (runs: 100, μ: 31794, ~: 31794)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 406672, ~: 406836)
[PASS] testDeepFuzz_previewWithdraw_lockedShares_notInExitWindow(uint256) (runs: 100, μ: 406724, ~: 406904)
[PASS] test_previewWithdraw() (gas: 260152)
[PASS] test_previewWithdraw_zeroAssetsWithDeposit() (gas: 260130)
[PASS] test_previewWithdraw_zeroAssetsWithoutDeposit() (gas: 31767)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 192.09ms (150.99ms CPU time)

Ran 19 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveReactivateTests
[PASS] testFork_aaveStrategy_reactivate_failIfAlreadyActive() (gas: 121708)
[PASS] testFork_aaveStrategy_reactivate_failIfNotProtocolAdmin() (gas: 114414)
[PASS] testFork_aaveStrategy_reactivate_failIfPaused() (gas: 78135)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromImpaired_withAccountingUpdate() (gas: 590450)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromImpaired_withoutAccountingUpdate() (gas: 586666)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromInactive_withAccountingUpdate() (gas: 577898)
[PASS] testFork_aaveStrategy_reactivate_stagnant_fromInactive_withoutAccountingUpdate() (gas: 578193)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromImpaired_withAccountingUpdate() (gas: 309846)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromImpaired_withoutAccountingUpdate() (gas: 305581)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromInactive_withAccountingUpdate() (gas: 296054)
[PASS] testFork_aaveStrategy_reactivate_unfunded_fromInactive_withoutAccountingUpdate() (gas: 291745)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromImpaired_withAccountingUpdate() (gas: 611156)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromImpaired_withoutAccountingUpdate() (gas: 607435)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromInactive_withAccountingUpdate() (gas: 593891)
[PASS] testFork_aaveStrategy_reactivate_withGain_fromInactive_withoutAccountingUpdate() (gas: 592442)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromImpaired_withAccountingUpdate() (gas: 683820)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromImpaired_withoutAccountingUpdate() (gas: 678853)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromInactive_withAccountingUpdate() (gas: 668271)
[PASS] testFork_aaveStrategy_reactivate_withLoss_fromInactive_withoutAccountingUpdate() (gas: 663206)
Suite result: ok. 19 passed; 0 failed; 0 skipped; finished in 164.21ms (40.57ms CPU time)

Ran 9 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveSetStrategyFeeTests
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfBiggerThanHundredPercent() (gas: 60879)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfDeactivated() (gas: 92597)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfImpaired() (gas: 92641)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 62900)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_failIfPaused() (gas: 56670)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withGovernor_fromNonZeroToZeroFeeRate() (gas: 748288)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withGovernor_unfundedStrategy() (gas: 286559)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withOperationalAdmin_withWithdrawal() (gas: 862034)
[PASS] testFork_aaveStrategy_setStrategyFeeRate_withPoolDelegate_fundedStrategy() (gas: 663929)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 138.37ms (12.22ms CPU time)

Ran 1 test for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewWithdrawWithQueueWMTests
[PASS] testFuzz_previewWithdraw(address,bool,uint256,uint256,uint256) (runs: 100, μ: 618283, ~: 649364)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 194.44ms (142.51ms CPU time)

Ran 5 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:TotalAssetsTests
[PASS] test_totalAssets_singleDeposit() (gas: 256342)
[PASS] test_totalAssets_singleLoanFunded() (gas: 1470595)
[PASS] test_totalAssets_singleLoanFundedWithInterest() (gas: 1501270)
[PASS] test_totalAssets_singleLoanFundedWithPayment() (gas: 1672159)
[PASS] test_totalAssets_zeroTotalSupply() (gas: 61877)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 37.78ms (5.72ms CPU time)

Ran 9 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyDeactivateTests
[PASS] testFork_aaveStrategy_deactivate_failIfAlreadyInactive() (gas: 94894)
[PASS] testFork_aaveStrategy_deactivate_failIfNotProtocolAdmin() (gas: 60662)
[PASS] testFork_aaveStrategy_deactivate_failIfPaused() (gas: 54408)
[PASS] testFork_aaveStrategy_deactivate_stagnant_noFees() (gas: 583833)
[PASS] testFork_aaveStrategy_deactivate_unfundedStrategy() (gas: 301517)
[PASS] testFork_aaveStrategy_deactivate_withFullLoss_strategyFees() (gas: 672061)
[PASS] testFork_aaveStrategy_deactivate_withGain_impaired_strategyFees() (gas: 678273)
[PASS] testFork_aaveStrategy_deactivate_withGain_strategyFees() (gas: 614869)
[PASS] testFork_aaveStrategy_deactivate_withLoss_strategyFees() (gas: 686558)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 139.57ms (15.30ms CPU time)

Ran 12 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolEntry_functionLevel_deposit() (gas: 375834)
[PASS] test_poolEntry_functionLevel_depositWithPermit() (gas: 416669)
[PASS] test_poolEntry_functionLevel_depositWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 375356)
[PASS] test_poolEntry_functionLevel_depositWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 341383)
[PASS] test_poolEntry_functionLevel_deposit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 335234)
[PASS] test_poolEntry_functionLevel_deposit_zeroPoolBitmap_zeroLenderBitmap() (gas: 301435)
[PASS] test_poolEntry_functionLevel_mint() (gas: 379086)
[PASS] test_poolEntry_functionLevel_mintWithPermit() (gas: 420307)
[PASS] test_poolEntry_functionLevel_mintWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 377750)
[PASS] test_poolEntry_functionLevel_mintWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 343799)
[PASS] test_poolEntry_functionLevel_mint_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 337463)
[PASS] test_poolEntry_functionLevel_mint_zeroPoolBitmap_zeroLenderBitmap() (gas: 303512)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 41.76ms (8.31ms CPU time)

Ran 12 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolEntry_poolLevel_deposit() (gas: 375919)
[PASS] test_poolEntry_poolLevel_depositWithPermit() (gas: 416643)
[PASS] test_poolEntry_poolLevel_depositWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 375317)
[PASS] test_poolEntry_poolLevel_depositWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 341430)
[PASS] test_poolEntry_poolLevel_deposit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 335237)
[PASS] test_poolEntry_poolLevel_deposit_zeroPoolBitmap_zeroLenderBitmap() (gas: 301352)
[PASS] test_poolEntry_poolLevel_mint() (gas: 379124)
[PASS] test_poolEntry_poolLevel_mintWithPermit() (gas: 420238)
[PASS] test_poolEntry_poolLevel_mintWithPermit_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 377731)
[PASS] test_poolEntry_poolLevel_mintWithPermit_zeroPoolBitmap_zeroLenderBitmap() (gas: 343868)
[PASS] test_poolEntry_poolLevel_mint_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 337402)
[PASS] test_poolEntry_poolLevel_mint_zeroPoolBitmap_zeroLenderBitmap() (gas: 303561)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 56.98ms (19.33ms CPU time)

Ran 14 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyFundTests
[PASS] testFork_aaveStrategy_fund_failIfInvalidAaveToken() (gas: 85263)
[PASS] testFork_aaveStrategy_fund_failIfInvalidStrategyFactory() (gas: 144110)
[PASS] testFork_aaveStrategy_fund_failIfNotEnoughPoolLiquidity() (gas: 186100)
[PASS] testFork_aaveStrategy_fund_failIfNotStrategyManager() (gas: 58518)
[PASS] testFork_aaveStrategy_fund_failIfZeroAmount() (gas: 127118)
[PASS] testFork_aaveStrategy_fund_failWhenDeactivated() (gas: 97451)
[PASS] testFork_aaveStrategy_fund_failWhenImpaired() (gas: 97560)
[PASS] testFork_aaveStrategy_fund_failWhenPaused() (gas: 54160)
[PASS] testFork_aaveStrategy_fund_secondTimeWithFeesAndYield() (gas: 728141)
[PASS] testFork_aaveStrategy_fund_secondTimeWithFeesRoundedToZeroAndYield() (gas: 647838)
[PASS] testFork_aaveStrategy_fund_secondTimeWithLoss() (gas: 725837)
[PASS] testFork_aaveStrategy_fund_secondTimeWithNoFeesAndYield() (gas: 673559)
[PASS] testFork_aaveStrategy_fund_withPoolDelegate() (gas: 543091)
[PASS] testFork_aaveStrategy_fund_withStrategyManager() (gas: 546179)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 161.87ms (19.86ms CPU time)

Ran 4 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PrivatePermissionTests
[PASS] test_poolEntry_private_deposit() (gas: 322053)
[PASS] test_poolEntry_private_depositWithPermit() (gas: 361984)
[PASS] test_poolEntry_private_mint() (gas: 324196)
[PASS] test_poolEntry_private_mintWithPermit() (gas: 364526)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 68.42ms (3.10ms CPU time)

Ran 4 tests for tests/integration/permission-manager/PoolEntryPermission.t.sol:PublicPermissionTests
[PASS] test_poolEntry_public_deposit() (gas: 222373)
[PASS] test_poolEntry_public_depositWithPermit() (gas: 261585)
[PASS] test_poolEntry_public_mint() (gas: 223454)
[PASS] test_poolEntry_public_mintWithPermit() (gas: 262824)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 38.28ms (2.35ms CPU time)

Ran 15 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolExit_functionLevel_redeem() (gas: 550656)
[PASS] test_poolExit_functionLevel_redeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 555599)
[PASS] test_poolExit_functionLevel_redeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 528457)
[PASS] test_poolExit_functionLevel_removeShares() (gas: 445920)
[PASS] test_poolExit_functionLevel_removeShares_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 450946)
[PASS] test_poolExit_functionLevel_removeShares_zeroPoolBitmap_zeroLenderBitmap() (gas: 423857)
[PASS] test_poolExit_functionLevel_requestRedeem() (gas: 389044)
[PASS] test_poolExit_functionLevel_requestRedeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 348469)
[PASS] test_poolExit_functionLevel_requestRedeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 314564)
[PASS] test_poolExit_functionLevel_requestWithdraw() (gas: 316437)
[PASS] test_poolExit_functionLevel_requestWithdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 275712)
[PASS] test_poolExit_functionLevel_requestWithdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 241915)
[PASS] test_poolExit_functionLevel_withdraw() (gas: 230166)
[PASS] test_poolExit_functionLevel_withdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 189348)
[PASS] test_poolExit_functionLevel_withdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 155398)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 74.74ms (23.43ms CPU time)

Ran 9 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyImpairTests
[PASS] testFork_aaveStrategy_impair_failIfAlreadyImpaired() (gas: 98119)
[PASS] testFork_aaveStrategy_impair_failIfNotProtocolAdmin() (gas: 60727)
[PASS] testFork_aaveStrategy_impair_failIfPaused() (gas: 54476)
[PASS] testFork_aaveStrategy_impair_stagnant_noFees() (gas: 596364)
[PASS] testFork_aaveStrategy_impair_unfundedStrategy() (gas: 315308)
[PASS] testFork_aaveStrategy_impair_withFullLoss_strategyFees() (gas: 685809)
[PASS] testFork_aaveStrategy_impair_withGain_inactive_strategyFees() (gas: 678250)
[PASS] testFork_aaveStrategy_impair_withGain_strategyFees() (gas: 629874)
[PASS] testFork_aaveStrategy_impair_withLoss_strategyFees() (gas: 700833)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 157.30ms (15.75ms CPU time)

Ran 15 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolExit_poolLevel_redeem() (gas: 519140)
[PASS] test_poolExit_poolLevel_redeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 510285)
[PASS] test_poolExit_poolLevel_redeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 483193)
[PASS] test_poolExit_poolLevel_removeShares() (gas: 414315)
[PASS] test_poolExit_poolLevel_removeShares_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 405683)
[PASS] test_poolExit_poolLevel_removeShares_zeroPoolBitmap_zeroLenderBitmap() (gas: 378592)
[PASS] test_poolExit_poolLevel_requestRedeem() (gas: 389041)
[PASS] test_poolExit_poolLevel_requestRedeem_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 348387)
[PASS] test_poolExit_poolLevel_requestRedeem_zeroPoolBitmap_zeroLenderBitmap() (gas: 314503)
[PASS] test_poolExit_poolLevel_requestWithdraw() (gas: 316501)
[PASS] test_poolExit_poolLevel_requestWithdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 275716)
[PASS] test_poolExit_poolLevel_requestWithdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 241896)
[PASS] test_poolExit_poolLevel_withdraw() (gas: 230164)
[PASS] test_poolExit_poolLevel_withdraw_zeroPoolBitmap_nonZeroLenderBitmap() (gas: 189309)
[PASS] test_poolExit_poolLevel_withdraw_zeroPoolBitmap_zeroLenderBitmap() (gas: 155469)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 77.94ms (22.14ms CPU time)

Ran 5 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PrivatePermissionTests
[PASS] test_poolExit_private_redeem() (gas: 463761)
[PASS] test_poolExit_private_removeShares() (gas: 359104)
[PASS] test_poolExit_private_requestRedeem() (gas: 342134)
[PASS] test_poolExit_private_requestWithdraw() (gas: 269432)
[PASS] test_poolExit_private_withdraw() (gas: 183105)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 51.99ms (10.46ms CPU time)

Ran 5 tests for tests/integration/permission-manager/PoolExitPermission.t.sol:PublicPermissionTests
[PASS] test_poolExit_public_redeem() (gas: 362452)
[PASS] test_poolExit_public_removeShares() (gas: 256339)
[PASS] test_poolExit_public_requestRedeem() (gas: 228923)
[PASS] test_poolExit_public_requestWithdraw() (gas: 160685)
[PASS] test_poolExit_public_withdraw() (gas: 74179)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 39.46ms (3.20ms CPU time)

Ran 12 tests for tests/integration/strategies/AaveStrategy.t.sol:AaveStrategyWithdrawTests
[PASS] testFork_aaveStrategy_withdraw_failIfLowAssets() (gas: 99935)
[PASS] testFork_aaveStrategy_withdraw_failIfNotStrategyManager() (gas: 58628)
[PASS] testFork_aaveStrategy_withdraw_failIfZeroAmount() (gas: 58990)
[PASS] testFork_aaveStrategy_withdraw_failWhenPaused() (gas: 54147)
[PASS] testFork_aaveStrategy_withdraw_failWithFullLoss() (gas: 328442)
[PASS] testFork_aaveStrategy_withdraw_noFeesWithYield() (gas: 460189)
[PASS] testFork_aaveStrategy_withdraw_whileDeactivated() (gas: 443542)
[PASS] testFork_aaveStrategy_withdraw_whileImpaired() (gas: 477137)
[PASS] testFork_aaveStrategy_withdraw_withFeesAndYield() (gas: 507630)
[PASS] testFork_aaveStrategy_withdraw_withFeesRoundedToZeroAndYield() (gas: 437996)
[PASS] testFork_aaveStrategy_withdraw_withLoss() (gas: 501164)
[PASS] testFork_aaveStrategy_withdraw_withPoolDelegate_noFeesSameBlock() (gas: 433941)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 213.20ms (26.47ms CPU time)

Ran 6 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:FunctionLevelPermissionTests
[PASS] test_poolTransfer_functionLevel_transfer() (gas: 311141)
[PASS] test_poolTransfer_functionLevel_transferFrom() (gas: 317196)
[PASS] test_poolTransfer_functionLevel_transferFrom_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 244061)
[PASS] test_poolTransfer_functionLevel_transferFrom_zeroPoolBitmap_zeroLenderBitmaps() (gas: 180246)
[PASS] test_poolTransfer_functionLevel_transfer_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 238769)
[PASS] test_poolTransfer_functionLevel_transfer_zeroPoolBitmap_zeroLenderBitmaps() (gas: 174953)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 48.17ms (6.62ms CPU time)

Ran 4 tests for tests/integration/loan/AcceptLoanTerms.t.sol:AcceptLoanTermsFTLTests
[PASS] test_acceptLoanTerms_FTL_failIfAlreadyAccepted() (gas: 67093)
[PASS] test_acceptLoanTerms_FTL_failIfNotBorrower() (gas: 41542)
[PASS] test_acceptLoanTerms_FTL_failIfPaused() (gas: 49625)
[PASS] test_acceptLoanTerms_FTL_success() (gas: 64451)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 68.92ms (754.38µs CPU time)

Ran 6 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PoolLevelPermissionTests
[PASS] test_poolTransfer_poolLevel_transfer() (gas: 311205)
[PASS] test_poolTransfer_poolLevel_transferFrom() (gas: 317173)
[PASS] test_poolTransfer_poolLevel_transferFrom_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 244073)
[PASS] test_poolTransfer_poolLevel_transferFrom_zeroPoolBitmap_zeroLenderBitmaps() (gas: 180281)
[PASS] test_poolTransfer_poolLevel_transfer_zeroPoolBitmap_nonZeroLenderBitmaps() (gas: 238803)
[PASS] test_poolTransfer_poolLevel_transfer_zeroPoolBitmap_zeroLenderBitmaps() (gas: 174988)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 42.75ms (5.44ms CPU time)

Ran 2 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PrivatePermissionTests
[PASS] test_poolTransfer_private_transfer() (gas: 260200)
[PASS] test_poolTransfer_private_transferFrom() (gas: 265688)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 40.74ms (1.53ms CPU time)

Ran 4 tests for tests/integration/loan/AcceptLoanTerms.t.sol:AcceptLoanTermsOTLTests
[PASS] test_acceptLoanTerms_OTL_failIfAlreadyAccepted() (gas: 67199)
[PASS] test_acceptLoanTerms_OTL_failIfNotBorrower() (gas: 41519)
[PASS] test_acceptLoanTerms_OTL_failIfPaused() (gas: 49648)
[PASS] test_acceptLoanTerms_OTL_success() (gas: 64429)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 68.73ms (782.55µs CPU time)

Ran 2 tests for tests/integration/permission-manager/PoolTransferPermission.t.sol:PublicPermissionTests
[PASS] test_poolTransfer_public_transfer() (gas: 92934)
[PASS] test_poolTransfer_public_transferFrom() (gas: 97850)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 40.02ms (634.13µs CPU time)

Ran 3 tests for tests/integration/governor-timelock/AcceptTokenWithdrawer.t.sol:AcceptTokenWithdrawerTests
[PASS] test_acceptTokenWithdrawer_revert_notAuthorized() (gas: 10661)
[PASS] test_acceptTokenWithdrawer_success() (gas: 37183)
[PASS] test_setUp() (gas: 55582)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 71.09ms (722.19µs CPU time)

Ran 8 tests for tests/integration/withdrawal-manager/queue/ProcessEmptyRedemptions.t.sol:ProcessEmptyRedemptionsQueueTests
[PASS] test_partialProcess_then_cancel_head_then_processEmptyRedemptions() (gas: 680287)
[PASS] test_processEmptyRedemptions_emptyQueue_noChange() (gas: 92195)
[PASS] test_processEmptyRedemptions_fullyProcessedQueue_noChange() (gas: 350204)
[PASS] test_processEmptyRedemptions_multipleEmptyRequests() (gas: 1047428)
[PASS] test_processEmptyRedemptions_noEmptyRequests_noChange() (gas: 666664)
[PASS] test_processEmptyRedemptions_stopsAtNonEmpty() (gas: 997404)
[PASS] test_processEmptyRedemptions_zeroRequests_reverts() (gas: 54592)
[PASS] test_processRedemptions_then_processEmptyRedemptions_skipsCancelledFront() (gas: 839272)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 93.45ms (19.42ms CPU time)

Ran 3 tests for tests/integration/globals/ActivatePoolManager.t.sol:ActivatePoolManagerFailureTests
[PASS] test_activatePoolManager_failIfNotGlobals() (gas: 35070)
[PASS] test_activatePoolManager_failIfNotGovernor() (gas: 20336)
[PASS] test_activatePoolManager_failIfProtocolIsPaused() (gas: 65909)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 40.51ms (513.17µs CPU time)

Ran 9 tests for tests/integration/withdrawal-manager/queue/ProcessRedemptions.t.sol:ProcessRedemptionsTests
[PASS] test_processRedemptions_differentExchangeRate() (gas: 1632570)
[PASS] test_processRedemptions_lowLiquidity() (gas: 1073194)
[PASS] test_processRedemptions_manualWithDifferentExchangeRates() (gas: 1440724)
[PASS] test_processRedemptions_multipleLps() (gas: 1373084)
[PASS] test_processRedemptions_multipleManualBatched() (gas: 1907312)
[PASS] test_processRedemptions_overkill() (gas: 1483334)
[PASS] test_processRedemptions_withCancelledRequest() (gas: 1316334)
[PASS] test_processRedemptions_withImpairment() (gas: 1658197)
[PASS] test_processRedemptions_zeroShares() (gas: 59645)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 102.74ms (41.20ms CPU time)

Ran 2 tests for tests/integration/globals/ActivatePoolManager.t.sol:ActivatePoolManagerTests
[PASS] test_activatePoolManager() (gas: 75498)
[PASS] test_activatePoolManager_asOperationalAdmin() (gas: 88756)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 52.63ms (564.14µs CPU time)

Ran 6 tests for tests/integration/withdrawal-manager/queue/AddShares.t.sol:AddSharesQueueFailureTests
[PASS] test_addShares_failIfEmptyRequest() (gas: 95932)
[PASS] test_addShares_failIfInsufficientApproval() (gas: 92459)
[PASS] test_addShares_failIfNotPool() (gas: 43562)
[PASS] test_addShares_failIfNotPoolManager() (gas: 18023)
[PASS] test_addShares_failIfProtocolIsPaused() (gas: 61222)
[PASS] test_addShares_failIfTransferFail() (gas: 102673)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 68.97ms (1.54ms CPU time)

Ran 6 tests for tests/integration/governor-timelock/ProposeRoleUpdates.t.sol:ProposeRoleUpdatesTests
[PASS] test_proposeRoleUpdates_revert_emptyArray() (gas: 14694)
[PASS] test_proposeRoleUpdates_revert_invalidAccountsLength() (gas: 15106)
[PASS] test_proposeRoleUpdates_revert_invalidShouldGrantLength() (gas: 15257)
[PASS] test_proposeRoleUpdates_revert_notRoleAdmin() (gas: 12256)
[PASS] test_proposeRoleUpdates_success() (gas: 154091)
[PASS] test_setUp() (gas: 55582)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 40.67ms (1.33ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/queue/AddShares.t.sol:AddSharesQueueTests
[PASS] test_addShares_manual() (gas: 385154)
[PASS] test_addShares_partialRequest() (gas: 345805)
[PASS] test_addShares_sameAddressCallingTwice() (gas: 523342)
[PASS] test_addShares_success() (gas: 559529)
[PASS] test_addShares_withApproval() (gas: 353997)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 77.50ms (8.85ms CPU time)

Ran 9 tests for tests/integration/pool/AddStrategy.t.sol:AddStrategyTests
[PASS] test_addStrategy_invalidAsset() (gas: 230970)
[PASS] test_addStrategy_invalidFactory() (gas: 46622)
[PASS] test_addStrategy_invalidStrategy() (gas: 237974)
[PASS] test_addStrategy_multipleStrategies() (gas: 1748905)
[PASS] test_addStrategy_noExtraArguments_withPoolDelegate() (gas: 387940)
[PASS] test_addStrategy_notAuthorized() (gas: 50400)
[PASS] test_addStrategy_paused() (gas: 49926)
[PASS] test_addStrategy_withExtraArguments_withGovernor() (gas: 637172)
[PASS] test_addStrategy_withExtraArguments_withOperationalAdmin() (gas: 544127)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 169.26ms (13.49ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:MultiUserRedeemTests
[PASS] test_redeem_partialLiquidity_sameCash_differentExchangeRate() (gas: 2305986)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate() (gas: 2215976)
[PASS] test_redeem_partialLiquidity_sameCash_sameExchangeRate_exposeRounding() (gas: 4367096)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 110.86ms (64.70ms CPU time)

Ran 9 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemFailureTests
[PASS] test_redeem_failIfNoApprove() (gas: 246147)
[PASS] test_redeem_failIfNoBalanceOnWM() (gas: 341276)
[PASS] test_redeem_failIfNoRequest() (gas: 91053)
[PASS] test_redeem_failIfNotInWindow() (gas: 271571)
[PASS] test_redeem_failIfNotPool() (gas: 43708)
[PASS] test_redeem_failIfNotPoolManager() (gas: 18039)
[PASS] test_redeem_failWithInsufficientApproval() (gas: 323044)
[PASS] test_redeem_failWithInvalidAmountOfShares() (gas: 268488)
[PASS] test_redeem_failWithZeroReceiver() (gas: 301075)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 83.14ms (9.62ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemIntegrationTests
[PASS] test_redeem_oneLPWithImpairedLoan() (gas: 1681933)
[PASS] test_redeem_twoLPSWithImpairedLoanAndTriggerDefault() (gas: 1780463)
[PASS] test_redeem_twoLPsWithImpairedLoan() (gas: 1924169)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 75.68ms (14.60ms CPU time)

Ran 7 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RedeemTests
[PASS] testDeepFuzz_redeem_singleUser_fullLiquidity_oneToOne(uint256,uint256) (runs: 100, μ: 504905, ~: 504581)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem() (gas: 519100)
[PASS] test_redeem_singleUser_fullLiquidity_fullRedeem_prematureRequest() (gas: 519972)
[PASS] test_redeem_singleUser_fullLiquidity_oneToOne() (gas: 516242)
[PASS] test_redeem_singleUser_noLiquidity() (gas: 1707723)
[PASS] test_redeem_singleUser_noLiquidity_notOwner() (gas: 1760711)
[PASS] test_redeem_singleUser_withApprovals() (gas: 570689)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 246.32ms (196.02ms CPU time)

Ran 4 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RequestRedeemFailureTests
[PASS] test_requestRedeem_failIfAlreadyLockedShares() (gas: 300234)
[PASS] test_requestRedeem_failIfInsufficientApproval() (gas: 148400)
[PASS] test_requestRedeem_failIfNotPM() (gas: 17852)
[PASS] test_requestRedeem_failIfNotPool() (gas: 43563)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 68.65ms (1.77ms CPU time)

Ran 1 test for tests/integration/loan-manager/fixed-term/BasicInterestAccrual.t.sol:BasicInterestAccrualTest
[PASS] test_basicInterestAccrual() (gas: 2164958)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 46.97ms (9.17ms CPU time)

Ran 7 tests for tests/integration/loan-manager/fixed-term/Redeem.t.sol:RequestRedeemTests
[PASS] testDeepFuzz_requestRedeem(uint256,uint256) (runs: 100, μ: 441642, ~: 442422)
[PASS] test_requestRedeem() (gas: 415237)
[PASS] test_requestRedeem_premature() (gas: 417762)
[PASS] test_requestRedeem_refresh() (gas: 486252)
[PASS] test_requestRedeem_refresh_notOwnerAndNoApproval() (gas: 450581)
[PASS] test_requestRedeem_refresh_notOwnerWithApproval() (gas: 511053)
[PASS] test_requestRedeem_withApproval() (gas: 440868)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 111.27ms (68.21ms CPU time)

Ran 19 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicReactivateTests
[PASS] testFork_basicStrategy_reactivate_failIfAlreadyActive() (gas: 121698)
[PASS] testFork_basicStrategy_reactivate_failIfNotProtocolAdmin() (gas: 114412)
[PASS] testFork_basicStrategy_reactivate_failIfPaused() (gas: 78091)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromImpaired_withAccountingUpdate() (gas: 441481)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromImpaired_withoutAccountingUpdate() (gas: 447523)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromInactive_withAccountingUpdate() (gas: 438621)
[PASS] testFork_basicStrategy_reactivate_stagnant_fromInactive_withoutAccountingUpdate() (gas: 439371)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromImpaired_withAccountingUpdate() (gas: 240269)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromImpaired_withoutAccountingUpdate() (gas: 234348)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromInactive_withAccountingUpdate() (gas: 221599)
[PASS] testFork_basicStrategy_reactivate_unfunded_fromInactive_withoutAccountingUpdate() (gas: 215715)
[PASS] testFork_basicStrategy_reactivate_withGain_fromImpaired_withAccountingUpdate() (gas: 509282)
[PASS] testFork_basicStrategy_reactivate_withGain_fromImpaired_withoutAccountingUpdate() (gas: 501463)
[PASS] testFork_basicStrategy_reactivate_withGain_fromInactive_withAccountingUpdate() (gas: 478737)
[PASS] testFork_basicStrategy_reactivate_withGain_fromInactive_withoutAccountingUpdate() (gas: 473190)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromImpaired_withAccountingUpdate() (gas: 547453)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromImpaired_withoutAccountingUpdate() (gas: 538552)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromInactive_withAccountingUpdate() (gas: 519761)
[PASS] testFork_basicStrategy_reactivate_withLoss_fromInactive_withoutAccountingUpdate() (gas: 511285)
Suite result: ok. 19 passed; 0 failed; 0 skipped; finished in 144.60ms (29.79ms CPU time)

Ran 6 tests for tests/integration/withdrawal-manager/queue/RedeemQueue.t.sol:ManualRedeemTests
[PASS] test_manualRedeem_fullLiquidity() (gas: 840857)
[PASS] test_manualRedeem_insufficientLiquidity() (gas: 1051586)
[PASS] test_manualRedeem_multipleRequests() (gas: 1047752)
[PASS] test_manualRedeem_noShares() (gas: 88010)
[PASS] test_manualRedeem_partialLiquidity() (gas: 905615)
[PASS] test_manualRedeem_tooManyShares() (gas: 508603)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 89.39ms (21.81ms CPU time)

Ran 13 tests for tests/integration/loan/Refinance.t.sol:AcceptNewTermsFailureTests
[PASS] test_acceptNewTerms_failIfDeadlineExpired() (gas: 196543)
[PASS] test_acceptNewTerms_failIfInsufficientCover() (gas: 247128)
[PASS] test_acceptNewTerms_failIfLockedLiquidity() (gas: 458876)
[PASS] test_acceptNewTerms_failIfNotLender() (gas: 39386)
[PASS] test_acceptNewTerms_failIfNotPoolDelegate() (gas: 57111)
[PASS] test_acceptNewTerms_failIfNotValidLoanManager() (gas: 74118)
[PASS] test_acceptNewTerms_failIfProtocolIsPaused() (gas: 59680)
[PASS] test_acceptNewTerms_failIfRefinanceCallFails() (gas: 315819)
[PASS] test_acceptNewTerms_failIfRefinanceMismatch() (gas: 145670)
[PASS] test_acceptNewTerms_failWithFailedTransfer() (gas: 254374)
[PASS] test_acceptNewTerms_failWithInsufficientCollateral() (gas: 557835)
[PASS] test_acceptNewTerms_failWithInvalidRefinancer() (gas: 222081)
[PASS] test_acceptNewTerms_failWithUnexpectedFunds() (gas: 547959)
Suite result: ok. 13 passed; 0 failed; 0 skipped; finished in 46.22ms (8.24ms CPU time)

Ran 9 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicSetStrategyFeeTests
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfBiggerThanHundredPercent() (gas: 63043)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfDeactivated() (gas: 92683)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfImpaired() (gas: 92662)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 62911)
[PASS] testFork_basicStrategy_setStrategyFeeRate_failIfPaused() (gas: 56679)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withGovernor_fromNonZeroToZeroFeeRate() (gas: 600398)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withGovernor_unfundedStrategy() (gas: 220448)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withOperationalAdmin_withWithdrawal() (gas: 707531)
[PASS] testFork_basicStrategy_setStrategyFeeRate_withPoolDelegate_fundedStrategy() (gas: 547710)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 162.63ms (14.02ms CPU time)

Ran 6 tests for tests/integration/loan/Refinance.t.sol:RefinanceOpenTermLoan
[PASS] test_refinance_calledLoan_withoutPrincipalChange() (gas: 649882)
[PASS] test_refinance_early_increasePrincipal() (gas: 653931)
[PASS] test_refinance_early_increasePrincipalWithCalledLoan() (gas: 670203)
[PASS] test_refinance_increasePrincipalMatchingPayment() (gas: 664564)
[PASS] test_refinance_increasePrincipalToDesiredAmount() (gas: 685546)
[PASS] test_refinance_late_decreasePrincipal() (gas: 584275)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 100.85ms (28.28ms CPU time)

Ran 5 tests for tests/integration/loan/Refinance.t.sol:RefinanceTestsSingleLoan
[PASS] test_refinance_onLateLoan_changePaymentInterval() (gas: 952404)
[PASS] test_refinance_onLoanPaymentDueDate_changeInterestRate() (gas: 946444)
[PASS] test_refinance_onLoanPaymentDueDate_changePaymentInterval() (gas: 946388)
[PASS] test_refinance_onLoanPaymentDueDate_changeToAmortized() (gas: 952335)
[PASS] test_refinance_onLoanPaymentDueDate_increasePrincipal() (gas: 985003)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 60.77ms (14.00ms CPU time)

Ran 4 tests for tests/integration/loan-manager/open-term/RemoveCall.t.sol:RemoveCallFailureTests
[PASS] test_callPrincipal_notCalled() (gas: 77863)
[PASS] test_callPrincipal_notLender() (gas: 36586)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 49062)
[PASS] test_callPrincipal_paused() (gas: 49338)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 31.81ms (561.42µs CPU time)

Ran 3 tests for tests/integration/loan-manager/open-term/RemoveCall.t.sol:RemoveCallTests
[PASS] test_removeCall_impaired() (gas: 347011)
[PASS] test_removeCall_latePayment() (gas: 132033)
[PASS] test_removeCall_paymentOnTime() (gas: 133912)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 38.92ms (2.70ms CPU time)

Ran 5 tests for tests/integration/loan-manager/fixed-term/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 65746)
[PASS] test_removeLoanImpairment_notGovernor() (gas: 240479)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 78563)
[PASS] test_removeLoanImpairment_notLender() (gas: 36358)
[PASS] test_removeLoanImpairment_pastDate() (gas: 313794)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 37.49ms (2.02ms CPU time)

Ran 9 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyDeactivateTests
[PASS] testFork_basicStrategy_deactivate_failIfAlreadyInactive() (gas: 94939)
[PASS] testFork_basicStrategy_deactivate_failIfNotProtocolAdmin() (gas: 60674)
[PASS] testFork_basicStrategy_deactivate_failIfPaused() (gas: 54464)
[PASS] testFork_basicStrategy_deactivate_stagnant_noFees() (gas: 445869)
[PASS] testFork_basicStrategy_deactivate_unfundedStrategy() (gas: 225461)
[PASS] testFork_basicStrategy_deactivate_withFullLoss_strategyFees() (gas: 490688)
[PASS] testFork_basicStrategy_deactivate_withGain_impaired_strategyFees() (gas: 566230)
[PASS] testFork_basicStrategy_deactivate_withGain_strategyFees() (gas: 498706)
[PASS] testFork_basicStrategy_deactivate_withLoss_strategyFees() (gas: 530595)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 185.44ms (16.98ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/queue/RemoveRequest.t.sol:RemoveRequestFailureTests
[PASS] test_removeRequest_failIfNotInQueue() (gas: 144198)
[PASS] test_removeRequest_failIfNotOperationalAdmin() (gas: 180818)
[PASS] test_removeRequest_failIfNotPoolDelegate() (gas: 177169)
[PASS] test_removeRequest_failIfProtocolIsPaused() (gas: 52361)
[PASS] test_removeRequest_failIfTransferFail() (gas: 175044)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 38.22ms (2.19ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/queue/RemoveRequest.t.sol:RemoveRequestTests
[PASS] test_removeRequest_forManual() (gas: 377830)
[PASS] test_removeRequest_manualPartialRedemption() (gas: 484423)
[PASS] test_removeRequest_partialRedemption() (gas: 506090)
[PASS] test_removeRequest_sameAddressWithMultipleRequests() (gas: 756025)
[PASS] test_removeRequest_success() (gas: 565757)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 42.88ms (8.15ms CPU time)

Ran 9 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesCyclicalFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 201384)
[PASS] test_removeShares_failIfInvalidShares() (gas: 98394)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 98358)
[PASS] test_removeShares_failIfNotPool() (gas: 43559)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 17994)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 61256)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 166820)
[PASS] test_removeShares_failIfTransferFail() (gas: 159970)
[PASS] test_removeShares_failIfWithdrawalIsPending() (gas: 220560)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 38.36ms (3.65ms CPU time)

Ran 16 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyFundTests
[PASS] testFork_basicStrategy_fund_failIfInvalidStrategyFactory() (gas: 132422)
[PASS] testFork_basicStrategy_fund_failIfInvalidStrategyVault() (gas: 81063)
[PASS] testFork_basicStrategy_fund_failIfNotEnoughPoolLiquidity() (gas: 162734)
[PASS] testFork_basicStrategy_fund_failIfNotEnoughSharesOut() (gas: 320117)
[PASS] testFork_basicStrategy_fund_failIfNotStrategyManager() (gas: 58592)
[PASS] testFork_basicStrategy_fund_failIfZeroAmount() (gas: 115520)
[PASS] testFork_basicStrategy_fund_failWhenDeactivated() (gas: 97588)
[PASS] testFork_basicStrategy_fund_failWhenImpaired() (gas: 97567)
[PASS] testFork_basicStrategy_fund_failWhenPaused() (gas: 54133)
[PASS] testFork_basicStrategy_fund_firstFundWithPoolDelegate() (gas: 408805)
[PASS] testFork_basicStrategy_fund_firstFundWithStrategyManager() (gas: 416682)
[PASS] testFork_basicStrategy_fund_secondFundAfterTotalLoss_withStrategyFees() (gas: 537759)
[PASS] testFork_basicStrategy_fund_secondFundWithGain_noStrategyFees() (gas: 545467)
[PASS] testFork_basicStrategy_fund_secondFundWithGain_withFeesRoundedToZero() (gas: 511093)
[PASS] testFork_basicStrategy_fund_secondFundWithGain_withStrategyFees() (gas: 561897)
[PASS] testFork_basicStrategy_fund_secondFundWithLoss_withStrategyFees() (gas: 564751)
Suite result: ok. 16 passed; 0 failed; 0 skipped; finished in 190.47ms (37.52ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesCyclicalTests
[PASS] test_removeShares_pastTheRedemptionWindow() (gas: 152491)
[PASS] test_removeShares_prematurelyAddedShares() (gas: 408832)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 510096)
[PASS] test_removeShares_success() (gas: 152540)
[PASS] test_removeShares_withApproval() (gas: 165963)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 47.12ms (5.34ms CPU time)

Ran 8 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesQueueFailureTests
[PASS] test_removeShares_failIfInsufficientApproval() (gas: 206414)
[PASS] test_removeShares_failIfInvalidShares() (gas: 88639)
[PASS] test_removeShares_failIfInvalidSharesWithZero() (gas: 86407)
[PASS] test_removeShares_failIfNotPool() (gas: 43559)
[PASS] test_removeShares_failIfNotPoolManager() (gas: 18048)
[PASS] test_removeShares_failIfProtocolIsPaused() (gas: 61278)
[PASS] test_removeShares_failIfRemovedTwice() (gas: 177772)
[PASS] test_removeShares_failIfTransferFail() (gas: 178217)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 39.05ms (2.94ms CPU time)

Ran 7 tests for tests/integration/withdrawal-manager/RemoveShares.t.sol:RemoveSharesQueueTests
[PASS] test_removeShare_complete_multipleRequests() (gas: 853095)
[PASS] test_removeShares_manual_partiallyProcessed() (gas: 706415)
[PASS] test_removeShares_partial_multipleRequests() (gas: 897932)
[PASS] test_removeShares_partiallyProcessed() (gas: 383266)
[PASS] test_removeShares_sameAddressCallingTwice() (gas: 616187)
[PASS] test_removeShares_success() (gas: 165505)
[PASS] test_removeShares_withApproval() (gas: 190073)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 71.20ms (24.82ms CPU time)

Ran 9 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyImpairTests
[PASS] testFork_basicStrategy_impair_failIfAlreadyImpaired() (gas: 98087)
[PASS] testFork_basicStrategy_impair_failIfNotProtocolAdmin() (gas: 60727)
[PASS] testFork_basicStrategy_impair_failIfPaused() (gas: 54441)
[PASS] testFork_basicStrategy_impair_stagnant_noFees() (gas: 457188)
[PASS] testFork_basicStrategy_impair_unfundedStrategy() (gas: 244152)
[PASS] testFork_basicStrategy_impair_withFullLoss_strategyFees() (gas: 516632)
[PASS] testFork_basicStrategy_impair_withGain_inactive_strategyFees() (gas: 565816)
[PASS] testFork_basicStrategy_impair_withGain_strategyFees() (gas: 526978)
[PASS] testFork_basicStrategy_impair_withLoss_strategyFees() (gas: 558091)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 196.35ms (33.57ms CPU time)

Ran 10 tests for tests/integration/withdrawal-manager/queue/RemoveSharesById.t.sol:RemoveSharesByIdQueueFailureTests
[PASS] test_removeSharesById_failIfInsufficientShares_requestNotProcessed() (gas: 46595)
[PASS] test_removeSharesById_failIfInsufficientShares_requestPartiallyProcessed() (gas: 302538)
[PASS] test_removeSharesById_failIfInvalidRequest() (gas: 44016)
[PASS] test_removeSharesById_failIfInvalidRequest_requestAlreadyRemoved() (gas: 135343)
[PASS] test_removeSharesById_failIfInvalidRequest_requestFullyProcessed() (gas: 278732)
[PASS] test_removeSharesById_failIfMaxUint128Exceeded() (gas: 42073)
[PASS] test_removeSharesById_failIfNoChange() (gas: 46604)
[PASS] test_removeSharesById_failIfNotOwner() (gas: 44055)
[PASS] test_removeSharesById_failIfProtocolIsPaused() (gas: 47514)
[PASS] test_removeSharesById_failIfTransferFail() (gas: 170941)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 64.34ms (5.65ms CPU time)

Ran 8 tests for tests/integration/withdrawal-manager/queue/RemoveSharesById.t.sol:RemoveSharesByIdQueueSuccessTests
[PASS] test_removeSharesById_sharesCompletelyRemoved_requestNotProcessed() (gas: 302732)
[PASS] test_removeSharesById_sharesCompletelyRemoved_requestNotProcessed_manualWithdrawal() (gas: 344293)
[PASS] test_removeSharesById_sharesCompletelyRemoved_requestPartiallyProcessed() (gas: 505068)
[PASS] test_removeSharesById_sharesCompletelyRemoved_requestPartiallyProcessed_manualWithdrawal() (gas: 479159)
[PASS] test_removeSharesById_sharesPartiallyRemoved_requestNotProcessed() (gas: 380578)
[PASS] test_removeSharesById_sharesPartiallyRemoved_requestNotProcessed_manualWithdrawal() (gas: 422139)
[PASS] test_removeSharesById_sharesPartiallyRemoved_requestPartiallyProcessed() (gas: 504789)
[PASS] test_removeSharesById_sharesPartiallyRemoved_requestPartiallyProcessed_manualWithdrawal() (gas: 478956)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 50.29ms (12.86ms CPU time)

Ran 15 tests for tests/integration/strategies/BasicStrategy.t.sol:BasicStrategyWithdrawTests
[PASS] testFork_basicStrategy_withdraw_failIfLowAssets() (gas: 322341)
[PASS] testFork_basicStrategy_withdraw_failIfNotStrategyManager() (gas: 321699)
[PASS] testFork_basicStrategy_withdraw_failIfSlippage() (gas: 339949)
[PASS] testFork_basicStrategy_withdraw_failIfZeroAmount() (gas: 318066)
[PASS] testFork_basicStrategy_withdraw_failWhenPaused() (gas: 330263)
[PASS] testFork_basicStrategy_withdraw_failWithFullLoss() (gas: 406193)
[PASS] testFork_basicStrategy_withdraw_noFeesWithYield() (gas: 528324)
[PASS] testFork_basicStrategy_withdraw_noFeesWithYieldFullWithdrawal() (gas: 496753)
[PASS] testFork_basicStrategy_withdraw_whileDeactivated() (gas: 496824)
[PASS] testFork_basicStrategy_withdraw_whileImpaired() (gas: 540565)
[PASS] testFork_basicStrategy_withdraw_withFeesAndYield() (gas: 545037)
[PASS] testFork_basicStrategy_withdraw_withFeesAndYieldFullWithdrawal() (gas: 513512)
[PASS] testFork_basicStrategy_withdraw_withFeesRoundedToZeroAndYield() (gas: 491997)
[PASS] testFork_basicStrategy_withdraw_withLoss() (gas: 544495)
[PASS] testFork_basicStrategy_withdraw_withPoolDelegate_noFeesSameBlock() (gas: 470905)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 146.32ms (29.92ms CPU time)

Ran 6 tests for tests/integration/governor-timelock/Scenarios.t.sol:GovernorTimelockScenariosTests
[PASS] test_setUp() (gas: 55666)
[PASS] test_unscheduleProposals_cancellerCanNotUnscheduleRoleUpdate() (gas: 82221)
[PASS] test_unscheduleProposals_cancellerUnschedulesMaliciousProposal() (gas: 118406)
[PASS] test_updateRoles_backupRoleAdmin_removesPrimaryRoleAdmin() (gas: 154788)
[PASS] test_upgradeWithdrawalManager() (gas: 303687)
[PASS] test_withdrawERC20Token_revert_afterChangingTokenWithdrawer() (gas: 148371)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 37.79ms (2.88ms CPU time)

Ran 7 tests for tests/integration/governor-timelock/ScheduleProposals.t.sol:ScheduleProposalsTests
[PASS] test_scheduleProposals_revert_arrayLengthMismatch() (gas: 15125)
[PASS] test_scheduleProposals_revert_emptyArray() (gas: 14254)
[PASS] test_scheduleProposals_revert_emptyTarget() (gas: 19615)
[PASS] test_scheduleProposals_revert_notProposer() (gas: 11805)
[PASS] test_scheduleProposals_revert_updateRoleNotAllowed() (gas: 85403)
[PASS] test_scheduleProposals_success_respectsDefaultTimelockAndFunctionSpecific() (gas: 212979)
[PASS] test_setUp() (gas: 55515)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 42.22ms (1.57ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositTests
[PASS] testFuzz_deposit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 321539, ~: 321601)
[PASS] testFuzz_deposit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 244823, ~: 244642)
[PASS] testFuzz_deposit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 425943, ~: 426141)
[PASS] test_deposit_exactBootstrapMintAmount() (gas: 297319)
[PASS] test_deposit_gtBootstrapMintAmount() (gas: 317551)
[PASS] test_deposit_ltBootstrapMintAmount() (gas: 241130)
[PASS] test_deposit_secondDepositorGetsCorrectShares() (gas: 422046)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 390.83ms (353.48ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositWithPermitTests
[PASS] testFuzz_depositWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 354078, ~: 354171)
[PASS] testFuzz_depositWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 234773, ~: 235028)
[PASS] testFuzz_depositWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 487217, ~: 487501)
[PASS] test_depositWithPermit_exactBootstrapMintAmount() (gas: 330001)
[PASS] test_depositWithPermit_gtBootstrapMintAmount() (gas: 350135)
[PASS] test_depositWithPermit_ltBootstrapMintAmount() (gas: 278344)
[PASS] test_depositWithPermit_secondDepositorGetsCorrectShares() (gas: 483295)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 527.15ms (494.07ms CPU time)

Ran 5 tests for tests/integration/governor-timelock/SetDefaultTimelockParameters.t.sol:SetDefaultTimelockParametersTests
[PASS] test_setDefaultTimelockParameters_revert_invalidDelay() (gas: 70753)
[PASS] test_setDefaultTimelockParameters_revert_invalidExecutionWindow() (gas: 70800)
[PASS] test_setDefaultTimelockParameters_revert_notSelf() (gas: 8737)
[PASS] test_setDefaultTimelockParameters_success() (gas: 123529)
[PASS] test_setUp() (gas: 55515)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 39.03ms (2.93ms CPU time)

Ran 8 tests for tests/integration/governor-timelock/SetFunctionTimelockParameters.t.sol:SetFunctionTimelockParametersTests
[PASS] test_setFunctionTimelockParameters_revert_invalidDefaultForDelay() (gas: 72093)
[PASS] test_setFunctionTimelockParameters_revert_invalidDefaultForExecutionWindow() (gas: 72101)
[PASS] test_setFunctionTimelockParameters_revert_invalidDelay() (gas: 73651)
[PASS] test_setFunctionTimelockParameters_revert_invalidExecutionWindow() (gas: 73615)
[PASS] test_setFunctionTimelockParameters_revert_notSelf() (gas: 11231)
[PASS] test_setFunctionTimelockParameters_success_resetFunctionTimelockBackToDefaults() (gas: 209405)
[PASS] test_setFunctionTimelockParameters_success_timelockOfUnderlyingFunctionIsRespected() (gas: 150192)
[PASS] test_setUp() (gas: 55560)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 36.95ms (2.83ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintTests
[PASS] testFuzz_mint_gtBootstrapMintAmount(uint256) (runs: 100, μ: 323541, ~: 323617)
[PASS] testFuzz_mint_ltBootstrapMintAmount(uint256) (runs: 100, μ: 246015, ~: 246256)
[PASS] testFuzz_mint_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 444618, ~: 444909)
[PASS] test_mint_exactBootstrapMintAmount() (gas: 299419)
[PASS] test_mint_gtBootstrapMintAmount() (gas: 319543)
[PASS] test_mint_ltBootstrapMintAmount() (gas: 242187)
[PASS] test_mint_secondDepositorGetsCorrectShares() (gas: 440698)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 416.75ms (346.88ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/queue/SetManualWithdrawal.t.sol:SetManualWithdrawalTests
[PASS] test_setManualWithdrawal_failIfNotProtocolAdmin() (gas: 54006)
[PASS] test_setManualWithdrawal_failIfProtocolIsPaused() (gas: 52093)
[PASS] test_setManualWithdrawal_success() (gas: 77845)
[PASS] test_setManualWithdrawal_successAsOperationalAdmin() (gas: 81572)
[PASS] test_setManualWithdrawal_unsetSuccess() (gas: 69671)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 68.41ms (979.47µs CPU time)

Ran 4 tests for tests/integration/loan-manager/fixed-term/SetMinRatioAndSlippage.t.sol:SetMinRatioTests
[PASS] test_setMinRatio_notAuthorized() (gas: 54070)
[PASS] test_setMinRatio_notPoolManager() (gas: 54025)
[PASS] test_setMinRatio_withGovernor() (gas: 81332)
[PASS] test_setMinRatio_withPoolDelegate() (gas: 76424)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 54.18ms (711.86µs CPU time)

Ran 5 tests for tests/integration/loan-manager/fixed-term/SetMinRatioAndSlippage.t.sol:SetSlippageTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 124277)
[PASS] test_setAllowedSlippage_notAuthorized() (gas: 53995)
[PASS] test_setAllowedSlippage_notPoolManager() (gas: 54016)
[PASS] test_setAllowedSlippage_withGovernor() (gas: 81293)
[PASS] test_setAllowedSlippage_withPoolDelegate() (gas: 76342)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 35.58ms (962.83µs CPU time)

Ran 3 tests for tests/integration/governor-timelock/SetPendingTokenWithdrawer.t.sol:SetPendingTokenWithdrawerTests
[PASS] test_setPendingTokenWithdrawer_revert_notTokenWithdrawer() (gas: 12776)
[PASS] test_setPendingTokenWithdrawer_success() (gas: 48186)
[PASS] test_setUp() (gas: 55560)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 37.06ms (796.88µs CPU time)

Ran 8 tests for tests/integration/permission-manager/SetPoolPermissionLevel.t.sol:SetPoolPermissionLevelTests
[PASS] testFuzz_setPoolPermissionLevel(uint256,uint256) (runs: 100, μ: 100055, ~: 104268)
[PASS] testFuzz_setPoolPermissionLevel_invalidLevel(uint256) (runs: 100, μ: 43828, ~: 43821)
[PASS] testFuzz_setPoolPermissionLevel_publicPool(uint256) (runs: 100, μ: 86857, ~: 86927)
[PASS] test_setPoolPermissionLevel_anotherPoolDelegate() (gas: 73951)
[PASS] test_setPoolPermissionLevel_governor() (gas: 65395)
[PASS] test_setPoolPermissionLevel_notAuthorized() (gas: 41471)
[PASS] test_setPoolPermissionLevel_operationalAdmin() (gas: 69202)
[PASS] test_setPoolPermissionLevel_poolDelegate() (gas: 63161)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 112.02ms (77.73ms CPU time)

Ran 7 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintWithPermitTests
[PASS] testFuzz_mintWithPermit_gtBootstrapMintAmount(uint256) (runs: 100, μ: 356312, ~: 356378)
[PASS] testFuzz_mintWithPermit_ltBootstrapMintAmount(uint256) (runs: 100, μ: 235899, ~: 236150)
[PASS] testFuzz_mintWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 100, μ: 506078, ~: 506316)
[PASS] test_mintWithPermit_exactBootstrapMintAmount() (gas: 332139)
[PASS] test_mintWithPermit_gtBootstrapMintAmount() (gas: 352295)
[PASS] test_mintWithPermit_ltBootstrapMintAmount() (gas: 279536)
[PASS] test_mintWithPermit_secondDepositorGetsCorrectShares() (gas: 502108)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 576.28ms (527.45ms CPU time)

Ran 5 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyDeactivateStrategyTests
[PASS] testFork_deactivateStrategy_active() (gas: 828755)
[PASS] testFork_deactivateStrategy_impaired() (gas: 845848)
[PASS] testFork_deactivateStrategy_inactive() (gas: 90390)
[PASS] testFork_deactivateStrategy_notAdmin() (gas: 131919)
[PASS] testFork_deactivateStrategy_protocolPaused() (gas: 54464)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 125.64ms (8.14ms CPU time)

Ran 2 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:SetBootstrapMintTests
[PASS] test_setBootstrapMint_failIfNotOperationalAdmin() (gas: 20286)
[PASS] test_setBootstrapMint_success_asOperationalAdmin() (gas: 36121)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 56.16ms (348.47µs CPU time)

Ran 5 tests for tests/integration/loan/open-term/CallPrincipal.t.sol:CallPrincipalFailureTests
[PASS] test_callPrincipal_invalidAmount_boundary() (gas: 466284)
[PASS] test_callPrincipal_loanActive() (gas: 53945)
[PASS] test_callPrincipal_notLender() (gas: 36687)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 49189)
[PASS] test_callPrincipal_paused() (gas: 49487)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 31.71ms (1.28ms CPU time)

Ran 4 tests for tests/integration/loan/open-term/CallPrincipal.t.sol:CallPrincipalTests
[PASS] test_callPrincipal_impaired() (gas: 371653)
[PASS] test_callPrincipal_latePayment() (gas: 158979)
[PASS] test_callPrincipal_notFullPrincipal() (gas: 158782)
[PASS] test_callPrincipal_paymentOnTime() (gas: 158690)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 40.19ms (3.35ms CPU time)

Ran 35 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyFundStrategyTests
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_allFees() (gas: 1167779)
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_noFees() (gas: 1073024)
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_psmFees() (gas: 1150196)
[PASS] testFork_fundStrategy_fundAfterCompleteLoss_strategyFees() (gas: 1125610)
[PASS] testFork_fundStrategy_fundAfterGain_allFees() (gas: 1281917)
[PASS] testFork_fundStrategy_fundAfterGain_allFees_withStrategyFeesRoundedToZero() (gas: 1130029)
[PASS] testFork_fundStrategy_fundAfterGain_noFees() (gas: 1034422)
[PASS] testFork_fundStrategy_fundAfterGain_psmFees() (gas: 1111918)
[PASS] testFork_fundStrategy_fundAfterGain_strategyFees() (gas: 1239254)
[PASS] testFork_fundStrategy_fundAfterGain_strategyFeesRoundedToZero() (gas: 1087485)
[PASS] testFork_fundStrategy_fundAfterLoss_allFees() (gas: 1152228)
[PASS] testFork_fundStrategy_fundAfterLoss_noFees() (gas: 1057107)
[PASS] testFork_fundStrategy_fundAfterLoss_psmFees() (gas: 1134662)
[PASS] testFork_fundStrategy_fundAfterLoss_strategyFees() (gas: 1109711)
[PASS] testFork_fundStrategy_fundWhenStagnant_allFees() (gas: 1078901)
[PASS] testFork_fundStrategy_fundWhenStagnant_noFees() (gas: 983923)
[PASS] testFork_fundStrategy_fundWhenStagnant_psmFees() (gas: 1061320)
[PASS] testFork_fundStrategy_fundWhenStagnant_strategyFees() (gas: 1036492)
[PASS] testFork_fundStrategy_initialFund_allFees() (gas: 910351)
[PASS] testFork_fundStrategy_initialFund_noFees() (gas: 851074)
[PASS] testFork_fundStrategy_initialFund_psmFees() (gas: 888397)
[PASS] testFork_fundStrategy_initialFund_strategyFees() (gas: 861921)
[PASS] testFork_fundStrategy_insufficientCover() (gas: 508458)
[PASS] testFork_fundStrategy_insufficientLiquidity() (gas: 492210)
[PASS] testFork_fundStrategy_invalidPsm() (gas: 87128)
[PASS] testFork_fundStrategy_invalidStrategyFactory() (gas: 147925)
[PASS] testFork_fundStrategy_invalidVault() (gas: 83136)
[PASS] testFork_fundStrategy_notPoolDelegate() (gas: 787827)
[PASS] testFork_fundStrategy_notStrategyManager() (gas: 792701)
[PASS] testFork_fundStrategy_protocolPaused() (gas: 56637)
[PASS] testFork_fundStrategy_psmHalted() (gas: 210)
[PASS] testFork_fundStrategy_strategyImpaired() (gas: 97571)
[PASS] testFork_fundStrategy_strategyInactive() (gas: 97461)
[PASS] testFork_fundStrategy_zeroPrincipal() (gas: 130975)
[PASS] testFork_fundStrategy_zeroSupply() (gas: 147475)
Suite result: ok. 35 passed; 0 failed; 0 skipped; finished in 292.57ms (150.45ms CPU time)

Ran 5 tests for tests/integration/loan/fixed-term/CloseLoan.t.sol:CloseLoanTests
[PASS] test_closeLoan_failIfLoanIsLate() (gas: 105411)
[PASS] test_closeLoan_failIfNotEnoughFundsSent() (gas: 195137)
[PASS] test_closeLoan_failIfNotLoan() (gas: 62529)
[PASS] test_closeLoan_failWithInsufficientApproval() (gas: 114607)
[PASS] test_closeLoan_success() (gas: 438314)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 59.46ms (3.16ms CPU time)

Ran 5 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyImpairStrategyTests
[PASS] testFork_impairStrategy_active() (gas: 847976)
[PASS] testFork_impairStrategy_impaired() (gas: 92799)
[PASS] testFork_impairStrategy_inactive() (gas: 845850)
[PASS] testFork_impairStrategy_notAdmin() (gas: 132061)
[PASS] testFork_impairStrategy_protocolPaused() (gas: 54507)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 180.88ms (9.92ms CPU time)

Ran 23 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyReactivateStrategyTests
[PASS] testFork_reactivateStrategy_active() (gas: 62635)
[PASS] testFork_reactivateStrategy_impaired_flat_keepAccounting() (gas: 625763)
[PASS] testFork_reactivateStrategy_impaired_flat_updateAccounting() (gas: 631527)
[PASS] testFork_reactivateStrategy_impaired_gain_keepAccounting() (gas: 670745)
[PASS] testFork_reactivateStrategy_impaired_gain_updateAccounting() (gas: 680783)
[PASS] testFork_reactivateStrategy_impaired_loss_keepAccounting() (gas: 695267)
[PASS] testFork_reactivateStrategy_impaired_loss_updateAccounting() (gas: 705884)
[PASS] testFork_reactivateStrategy_impaired_new_keepAccounting() (gas: 282747)
[PASS] testFork_reactivateStrategy_impaired_new_updateAccounting() (gas: 291114)
[PASS] testFork_reactivateStrategy_impaired_totalLoss_keepAccounting() (gas: 661822)
[PASS] testFork_reactivateStrategy_impaired_totalLoss_updateAccounting() (gas: 669805)
[PASS] testFork_reactivateStrategy_inactive_flat_keepAccounting() (gas: 606776)
[PASS] testFork_reactivateStrategy_inactive_flat_updateAccounting() (gas: 612496)
[PASS] testFork_reactivateStrategy_inactive_gain_keepAccounting() (gas: 636241)
[PASS] testFork_reactivateStrategy_inactive_gain_updateAccounting() (gas: 646253)
[PASS] testFork_reactivateStrategy_inactive_loss_keepAccounting() (gas: 661689)
[PASS] testFork_reactivateStrategy_inactive_loss_updateAccounting() (gas: 672305)
[PASS] testFork_reactivateStrategy_inactive_new_keepAccounting() (gas: 256612)
[PASS] testFork_reactivateStrategy_inactive_new_updateAccounting() (gas: 264844)
[PASS] testFork_reactivateStrategy_inactive_totalLoss_keepAccounting() (gas: 635303)
[PASS] testFork_reactivateStrategy_inactive_totalLoss_updateAccounting() (gas: 643543)
[PASS] testFork_reactivateStrategy_notAdmin() (gas: 85955)
[PASS] testFork_reactivateStrategy_protocolPaused() (gas: 54578)
Suite result: ok. 23 passed; 0 failed; 0 skipped; finished in 166.68ms (49.12ms CPU time)

Ran 9 tests for tests/integration/pool/ConfigurePool.t.sol:ConfigurePoolTests
[PASS] testFuzz_configurePool(uint256,uint256,uint256[]) (runs: 100, μ: 2121334, ~: 1423729)
[PASS] test_configurePool_anotherPoolDelegate() (gas: 87756)
[PASS] test_configurePool_governor() (gas: 133922)
[PASS] test_configurePool_invalidLevel() (gas: 54064)
[PASS] test_configurePool_lengthMismatch() (gas: 79399)
[PASS] test_configurePool_notAuthorized() (gas: 55270)
[PASS] test_configurePool_operationalAdmin() (gas: 137739)
[PASS] test_configurePool_poolDelegate() (gas: 131742)
[PASS] test_configurePool_publicPool() (gas: 109280)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 321.64ms (260.83ms CPU time)

Ran 8 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategySetPSMTests
[PASS] testFork_setPsm_failIfNotValidInstance() (gas: 80308)
[PASS] testFork_setPsm_fundedStrategy() (gas: 853366)
[PASS] testFork_setPsm_invalidGem() (gas: 301705)
[PASS] testFork_setPsm_invalidUsds() (gas: 327501)
[PASS] testFork_setPsm_notAdmin() (gas: 319434)
[PASS] testFork_setPsm_protocolPaused() (gas: 56706)
[PASS] testFork_setPsm_unfundedStrategy() (gas: 174844)
[PASS] testFork_setPsm_zeroAddress() (gas: 54229)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 156.37ms (7.77ms CPU time)

Ran 8 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyDeactivateStrategyTests
[PASS] testFork_deactivateStrategy_correctAumAfterDeactivation() (gas: 351799)
[PASS] testFork_deactivateStrategy_failWhenAlreadyDeactivated() (gas: 68208)
[PASS] testFork_deactivateStrategy_failWhenNotGovernor() (gas: 118018)
[PASS] testFork_deactivateStrategy_failWhenNotOperationalAdmin() (gas: 115087)
[PASS] testFork_deactivateStrategy_failWhenNotPoolDelegate() (gas: 113306)
[PASS] testFork_deactivateStrategy_failWhenProtocolPaused() (gas: 109670)
[PASS] testFork_deactivateStrategy_success() (gas: 322609)
[PASS] testFork_deactivateStrategy_successWhenAlreadyImpaired() (gas: 386596)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 126.29ms (5.33ms CPU time)

Ran 11 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategySetStrategyFeeTests
[PASS] testFork_setStrategyFeeRate_deactivated() (gas: 92586)
[PASS] testFork_setStrategyFeeRate_impaired() (gas: 92675)
[PASS] testFork_setStrategyFeeRate_initialFeeRate_flat() (gas: 321440)
[PASS] testFork_setStrategyFeeRate_initialFeeRate_gain() (gas: 420320)
[PASS] testFork_setStrategyFeeRate_initialFeeRate_loss() (gas: 394013)
[PASS] testFork_setStrategyFeeRate_invalidFeeRate() (gas: 60944)
[PASS] testFork_setStrategyFeeRate_notAdmin() (gas: 222613)
[PASS] testFork_setStrategyFeeRate_protocolPaused() (gas: 56681)
[PASS] testFork_setStrategyFeeRate_updatedFeeRate_flat() (gas: 323682)
[PASS] testFork_setStrategyFeeRate_updatedFeeRate_gain() (gas: 641198)
[PASS] testFork_setStrategyFeeRate_updatedFeeRate_loss() (gas: 396212)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 113.31ms (21.53ms CPU time)

Ran 13 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyFundTests
[PASS] testFork_coreStrategy_fund_failIfInvalidStrategyFactory() (gas: 107382)
[PASS] testFork_coreStrategy_fund_failIfInvalidStrategyVault() (gas: 79021)
[PASS] testFork_coreStrategy_fund_failIfNotEnoughPoolLiquidity() (gas: 149349)
[PASS] testFork_coreStrategy_fund_failIfNotStrategyManager() (gas: 58613)
[PASS] testFork_coreStrategy_fund_failIfZeroAmount() (gas: 90467)
[PASS] testFork_coreStrategy_fund_failWhenDeactivated() (gas: 80354)
[PASS] testFork_coreStrategy_fund_failWhenImpaired() (gas: 80421)
[PASS] testFork_coreStrategy_fund_failWhenPaused() (gas: 54132)
[PASS] testFork_coreStrategy_fund_firstFundWithPoolDelegate() (gas: 581212)
[PASS] testFork_coreStrategy_fund_firstFundWithStrategyManager() (gas: 589056)
[PASS] testFork_coreStrategy_fund_secondFundAfterTotalLoss() (gas: 745624)
[PASS] testFork_coreStrategy_fund_secondFundWithGain() (gas: 501108)
[PASS] testFork_coreStrategy_fund_secondFundWithLoss() (gas: 755256)
Suite result: ok. 13 passed; 0 failed; 0 skipped; finished in 135.66ms (15.53ms CPU time)

Ran 6 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyImpairedStrategyTests
[PASS] testFork_impairedStrategy_correctAumAfterImpairment() (gas: 441066)
[PASS] testFork_impairedStrategy_failWhenAlreadyImpaired() (gas: 66711)
[PASS] testFork_impairedStrategy_failWhenNotAdmin() (gas: 110244)
[PASS] testFork_impairedStrategy_failWhenProtocolPaused() (gas: 54479)
[PASS] testFork_impairedStrategy_success() (gas: 429528)
[PASS] testFork_impairedStrategy_successWhenAlreadyDeactivated() (gas: 408776)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 120.58ms (6.05ms CPU time)

Ran 11 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyPushAssetsTests
[PASS] testFork_coreStrategy_pushAssetsToPool_failIfNotPoolDelegate() (gas: 129158)
[PASS] testFork_coreStrategy_pushAssetsToPool_failIfNotStrategyManager() (gas: 134011)
[PASS] testFork_coreStrategy_pushAssetsToPool_failTransfer() (gas: 670701)
[PASS] testFork_coreStrategy_pushAssetsToPool_failWhenPaused() (gas: 54491)
[PASS] testFork_coreStrategy_pushAssetsToPool_successAfterAdditionalFunding() (gas: 828868)
[PASS] testFork_coreStrategy_pushAssetsToPool_successWhenDeactivated() (gas: 708105)
[PASS] testFork_coreStrategy_pushAssetsToPool_successWhenImpaired() (gas: 714232)
[PASS] testFork_coreStrategy_pushAssetsToPool_successWhenPartialWithdrawalProcessed() (gas: 776091)
[PASS] testFork_coreStrategy_pushAssetsToPool_successWhenPartialWithdrawalRequested() (gas: 719236)
[PASS] testFork_coreStrategy_pushAssetsToPool_successWhenPositiveBalance() (gas: 696476)
[PASS] testFork_coreStrategy_pushAssetsToPool_successWhenZeroBalance() (gas: 97279)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 133.97ms (19.90ms CPU time)

Ran 4 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyReactivateStrategyTests
[PASS] testFork_reactivateStrategy_aumCorrectAfterReactivation() (gas: 387110)
[PASS] testFork_reactivateStrategy_failWhenAlreadyActive() (gas: 57678)
[PASS] testFork_reactivateStrategy_failWhenNotAdmin() (gas: 86698)
[PASS] testFork_reactivateStrategy_failWhenProtocolPaused() (gas: 54456)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 116.05ms (2.56ms CPU time)

Ran 77 tests for tests/integration/strategies/SkyStrategy.t.sol:SkyStrategyWithdrawFromStrategyTests
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterGain_fullWithdrawal() (gas: 1254627)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterGain_partialWithdrawal() (gas: 1248888)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterLoss_fullWithdrawal() (gas: 1141216)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_afterLoss_partialWithdrawal() (gas: 1152051)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_whenStagnant_fullWithdrawal() (gas: 1060260)
[PASS] testFork_withdrawFromStrategy_activeStrategy_allFees_whenStagnant_partialWithdrawal() (gas: 1075573)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterGain_fullWithdrawal() (gas: 1028216)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterGain_partialWithdrawal() (gas: 1021633)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterLoss_fullWithdrawal() (gas: 1050866)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_afterLoss_partialWithdrawal() (gas: 1044348)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_whenStagnant_fullWithdrawal() (gas: 970008)
[PASS] testFork_withdrawFromStrategy_activeStrategy_noFees_whenStagnant_partialWithdrawal() (gas: 967220)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterGain_fullWithdrawal() (gas: 1100858)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterGain_partialWithdrawal() (gas: 1101626)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterLoss_fullWithdrawal() (gas: 1123573)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_afterLoss_partialWithdrawal() (gas: 1129952)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_whenStagnant_fullWithdrawal() (gas: 1042562)
[PASS] testFork_withdrawFromStrategy_activeStrategy_psmFees_whenStagnant_partialWithdrawal() (gas: 1053387)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterGain_fullWithdrawal() (gas: 1216664)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterGain_partialWithdrawal() (gas: 1210084)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterLoss_fullWithdrawal() (gas: 1103527)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_afterLoss_partialWithdrawal() (gas: 1103777)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_whenStagnant_fullWithdrawal() (gas: 1022717)
[PASS] testFork_withdrawFromStrategy_activeStrategy_strategyFees_whenStagnant_partialWithdrawal() (gas: 1027312)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterGain_fullWithdrawal() (gas: 1149019)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterGain_partialWithdrawal() (gas: 1145734)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterLoss_fullWithdrawal() (gas: 1177150)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_afterLoss_partialWithdrawal() (gas: 1173770)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_whenStagnant_fullWithdrawal() (gas: 1105473)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_allFees_whenStagnant_partialWithdrawal() (gas: 1106813)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterGain_fullWithdrawal() (gas: 1047692)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterGain_partialWithdrawal() (gas: 1044093)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterLoss_fullWithdrawal() (gas: 1070462)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_afterLoss_partialWithdrawal() (gas: 1066821)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_whenStagnant_fullWithdrawal() (gas: 998984)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_noFees_whenStagnant_partialWithdrawal() (gas: 999276)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterGain_fullWithdrawal() (gas: 1126658)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterGain_partialWithdrawal() (gas: 1123241)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterLoss_fullWithdrawal() (gas: 1155027)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_afterLoss_partialWithdrawal() (gas: 1151693)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_whenStagnant_fullWithdrawal() (gas: 1083441)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_psmFees_whenStagnant_partialWithdrawal() (gas: 1084669)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterGain_fullWithdrawal() (gas: 1101552)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterGain_partialWithdrawal() (gas: 1097098)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterLoss_fullWithdrawal() (gas: 1129507)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_afterLoss_partialWithdrawal() (gas: 1125179)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_whenStagnant_fullWithdrawal() (gas: 1058028)
[PASS] testFork_withdrawFromStrategy_impairedStrategy_strategyFees_whenStagnant_partialWithdrawal() (gas: 1058300)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterGain_fullWithdrawal() (gas: 1110928)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterGain_partialWithdrawal() (gas: 1105863)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterLoss_fullWithdrawal() (gas: 1138927)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_afterLoss_partialWithdrawal() (gas: 1133879)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_whenStagnant_fullWithdrawal() (gas: 1067315)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_allFees_whenStagnant_partialWithdrawal() (gas: 1067164)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterGain_fullWithdrawal() (gas: 1017564)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterGain_partialWithdrawal() (gas: 1013049)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterLoss_fullWithdrawal() (gas: 1040252)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_afterLoss_partialWithdrawal() (gas: 1035748)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_whenStagnant_fullWithdrawal() (gas: 967130)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_noFees_whenStagnant_partialWithdrawal() (gas: 966563)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterGain_fullWithdrawal() (gas: 1088456)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterGain_partialWithdrawal() (gas: 1083479)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterLoss_fullWithdrawal() (gas: 1116916)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_afterLoss_partialWithdrawal() (gas: 1111843)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_whenStagnant_fullWithdrawal() (gas: 1045171)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_psmFees_whenStagnant_partialWithdrawal() (gas: 1045084)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterGain_fullWithdrawal() (gas: 1067221)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterGain_partialWithdrawal() (gas: 1062752)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterLoss_fullWithdrawal() (gas: 1091858)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_afterLoss_partialWithdrawal() (gas: 1086360)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_whenStagnant_fullWithdrawal() (gas: 1020402)
[PASS] testFork_withdrawFromStrategy_inactiveStrategy_strategyFees_whenStagnant_partialWithdrawal() (gas: 1019602)
[PASS] testFork_withdrawFromStrategy_lowAssets() (gas: 770460)
[PASS] testFork_withdrawFromStrategy_notPoolDelegate() (gas: 904168)
[PASS] testFork_withdrawFromStrategy_notStrategyManager() (gas: 909648)
[PASS] testFork_withdrawFromStrategy_protocolPaused() (gas: 56746)
[PASS] testFork_withdrawFromStrategy_zeroAssets() (gas: 59028)
Suite result: ok. 77 passed; 0 failed; 0 skipped; finished in 501.97ms (400.89ms CPU time)

Ran 2 tests for tests/integration/smart-accounts/SmartAccount.t.sol:SmartAccountETHTests
[PASS] testFork_deposit_predeterminedAddressApproval() (gas: 1192065)
[PASS] testFork_withdraw() (gas: 1412574)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 166.01ms (12.35ms CPU time)

Ran 17 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyRemoveSharesByIdIntegrationTests
[PASS] test_removeSharesById_alreadyProcessedRequest() (gas: 309326)
[PASS] test_removeSharesById_cancelledRequest() (gas: 210092)
[PASS] test_removeSharesById_insufficientShares() (gas: 108042)
[PASS] test_removeSharesById_invalidOwner() (gas: 492439)
[PASS] test_removeSharesById_nonExistingRequest() (gas: 107888)
[PASS] test_removeSharesById_notAuthorized() (gas: 231250)
[PASS] test_removeSharesById_notPoolDelegate() (gas: 226396)
[PASS] test_removeSharesById_partiallyProcesedRequest_decreaseRequest() (gas: 398331)
[PASS] test_removeSharesById_partiallyProcesedRequest_removeRequest() (gas: 375764)
[PASS] test_removeSharesById_requestIdOverflow() (gas: 101395)
[PASS] test_removeSharesById_strategyPaused() (gas: 58738)
[PASS] test_removeSharesById_transferFailed() (gas: 220857)
[PASS] test_removeSharesById_unprocessedRequest_decreaseRequest() (gas: 212525)
[PASS] test_removeSharesById_unprocessedRequest_removeRequest() (gas: 190294)
[PASS] test_removeSharesById_withdrawalManagerPaused() (gas: 133245)
[PASS] test_removeSharesById_zeroRequestId() (gas: 105783)
[PASS] test_removeSharesById_zeroShares() (gas: 105800)
Suite result: ok. 17 passed; 0 failed; 0 skipped; finished in 183.50ms (23.82ms CPU time)

Ran 9 tests for tests/integration/syrup-usdc-router/SyrupRouter.t.sol:SyrupRouterAuthorizeAndDepositTests
[PASS] test_authorizeAndDepositWithPermit_expiredDeadline() (gas: 21173)
[PASS] test_authorizeAndDepositWithPermit_malleable() (gas: 18164)
[PASS] test_authorizeAndDepositWithPermit_repeatedNonce() (gas: 346869)
[PASS] test_authorizeAndDepositWithPermit_success() (gas: 347715)
[PASS] test_authorizeAndDeposit_expiredDeadline() (gas: 20950)
[PASS] test_authorizeAndDeposit_malleable() (gas: 17983)
[PASS] test_authorizeAndDeposit_notPermissionAdmin() (gas: 91345)
[PASS] test_authorizeAndDeposit_repeatedNonce() (gas: 325586)
[PASS] test_authorizeAndDeposit_success() (gas: 328677)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 58.64ms (11.11ms CPU time)

Ran 10 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyRemoveSharesIntegrationTests
[PASS] testFork_coreStrategy_removeShares_completeRemovalWithMultipleRequests() (gas: 560959)
[PASS] testFork_coreStrategy_removeShares_failIfNotStrategyManager() (gas: 288514)
[PASS] testFork_coreStrategy_removeShares_failIfZeroShares() (gas: 58993)
[PASS] testFork_coreStrategy_removeShares_failInsufficientShares() (gas: 529796)
[PASS] testFork_coreStrategy_removeShares_failWhenPaused() (gas: 56685)
[PASS] testFork_coreStrategy_removeShares_removeAllSharesSuccess() (gas: 183934)
[PASS] testFork_coreStrategy_removeShares_removePartialSharesSuccess() (gas: 206375)
[PASS] testFork_coreStrategy_removeShares_removePartialWithMultipleRequests() (gas: 550824)
[PASS] testFork_coreStrategy_removeShares_successWhenDeactivated() (gas: 201090)
[PASS] testFork_coreStrategy_removeShares_successWhenImpaired() (gas: 201113)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 175.15ms (13.66ms CPU time)

Ran 50 tests for tests/integration/syrup-usdc-router/SyrupRouter.t.sol:SyrupRouterDepositsIntegrationTests
[PASS] test_depositWithPermit_functionLevel_allowListed() (gas: 460468)
[PASS] test_depositWithPermit_functionLevel_expiredDeadline() (gas: 202683)
[PASS] test_depositWithPermit_functionLevel_insufficientPermission() (gas: 254327)
[PASS] test_depositWithPermit_functionLevel_invalidSignature() (gas: 227451)
[PASS] test_depositWithPermit_functionLevel_sufficientPermission() (gas: 463482)
[PASS] test_depositWithPermit_functionLevel_zeroBitmap() (gas: 234471)
[PASS] test_depositWithPermit_functionLevel_zeroShares() (gas: 290955)
[PASS] test_depositWithPermit_poolLevel_allowListed() (gas: 458377)
[PASS] test_depositWithPermit_poolLevel_expiredDeadline() (gas: 200638)
[PASS] test_depositWithPermit_poolLevel_insufficientPermission() (gas: 252268)
[PASS] test_depositWithPermit_poolLevel_invalidSignature() (gas: 225428)
[PASS] test_depositWithPermit_poolLevel_sufficientPermission() (gas: 459517)
[PASS] test_depositWithPermit_poolLevel_zeroBitmap() (gas: 232412)
[PASS] test_depositWithPermit_poolLevel_zeroShares() (gas: 288915)
[PASS] test_depositWithPermit_private_allowListed() (gas: 377040)
[PASS] test_depositWithPermit_private_expiredDeadline() (gas: 112628)
[PASS] test_depositWithPermit_private_invalidSignature() (gas: 137441)
[PASS] test_depositWithPermit_private_unauthorized() (gas: 100355)
[PASS] test_depositWithPermit_private_zeroShares() (gas: 206926)
[PASS] test_depositWithPermit_public_expiredDeadline() (gas: 171272)
[PASS] test_depositWithPermit_public_invalidSignature() (gas: 196128)
[PASS] test_depositWithPermit_public_success() (gas: 367990)
[PASS] test_depositWithPermit_public_zeroShares() (gas: 261030)
[PASS] test_deposit_functionLevel_allowlisted() (gas: 440259)
[PASS] test_deposit_functionLevel_approval() (gas: 425748)
[PASS] test_deposit_functionLevel_infiniteApproval() (gas: 443380)
[PASS] test_deposit_functionLevel_insufficientAmount() (gas: 286076)
[PASS] test_deposit_functionLevel_insufficientApproval() (gas: 283645)
[PASS] test_deposit_functionLevel_insufficientPermission() (gas: 180691)
[PASS] test_deposit_functionLevel_zeroBitmap() (gas: 160833)
[PASS] test_deposit_functionLevel_zeroShares() (gas: 269958)
[PASS] test_deposit_poolLevel_allowlisted() (gas: 438276)
[PASS] test_deposit_poolLevel_approval() (gas: 421738)
[PASS] test_deposit_poolLevel_infiniteApproval() (gas: 439351)
[PASS] test_deposit_poolLevel_insufficientAmount() (gas: 283972)
[PASS] test_deposit_poolLevel_insufficientApproval() (gas: 281562)
[PASS] test_deposit_poolLevel_insufficientPermission() (gas: 178605)
[PASS] test_deposit_poolLevel_zeroBitmap() (gas: 158708)
[PASS] test_deposit_poolLevel_zeroShares() (gas: 267916)
[PASS] test_deposit_private_approval() (gas: 339306)
[PASS] test_deposit_private_infiniteApproval() (gas: 356965)
[PASS] test_deposit_private_insufficientAmount() (gas: 195548)
[PASS] test_deposit_private_insufficientApproval() (gas: 193138)
[PASS] test_deposit_private_unauthorized() (gas: 26707)
[PASS] test_deposit_private_zeroShares() (gas: 185973)
[PASS] test_deposit_public_approval() (gas: 330234)
[PASS] test_deposit_public_infiniteApproval() (gas: 347848)
[PASS] test_deposit_public_insufficientAmount() (gas: 189369)
[PASS] test_deposit_public_insufficientApproval() (gas: 186893)
[PASS] test_deposit_public_zeroShares() (gas: 177535)
Suite result: ok. 50 passed; 0 failed; 0 skipped; finished in 110.07ms (37.93ms CPU time)

Ran 2 tests for tests/integration/syrup-usdc-router/SyrupRouterFork.t.sol:SyrupRouterForkTests
[PASS] testFork_router_deposit() (gas: 251237)
[PASS] testFork_router_depositWithPermit() (gas: 294468)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 82.19ms (6.23ms CPU time)

Ran 11 tests for tests/integration/strategies/CoreStrategy.t.sol:CoreStrategyRequestWithdrawFromStrategyTests
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_failIfLowAssets() (gas: 348633)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_failIfNotPoolDelegate() (gas: 599522)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_failIfNotStrategyManager() (gas: 600362)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_failIfZeroAmount() (gas: 319595)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_failWhenPaused() (gas: 331843)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_failWithFullLoss() (gas: 561353)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_failWithNoAssets() (gas: 629646)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_success() (gas: 781558)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_successAfterPartialLoss() (gas: 820201)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_successWithMultipleWithdrawals() (gas: 997270)
[PASS] testFork_coreStrategy_requestWithdrawFromStrategy_successWithPartialWithdrawal() (gas: 807880)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 177.04ms (39.86ms CPU time)

Ran 10 tests for tests/integration/pool/Transfer.t.sol:TransferTests
[PASS] test_transferFrom_privatePoolInvalidLender() (gas: 394733)
[PASS] test_transferFrom_privatePoolInvalidLender_openPoolToPublic() (gas: 388312)
[PASS] test_transferFrom_protocolPaused() (gas: 341059)
[PASS] test_transferFrom_publicPool() (gas: 322491)
[PASS] test_transferFrom_publicPool_insufficientApproval() (gas: 331502)
[PASS] test_transferFrom_publicPool_noApproval() (gas: 307603)
[PASS] test_transfer_privatePoolInvalidLender() (gas: 382636)
[PASS] test_transfer_privatePoolInvalidLender_openPoolToPublic() (gas: 376256)
[PASS] test_transfer_protocolPaused() (gas: 314573)
[PASS] test_transfer_publicPool() (gas: 313745)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 58.95ms (9.29ms CPU time)

Ran 9 tests for tests/integration/globals/TransferPoolOwnership.t.sol:TransferPoolOwnershipTests
[PASS] test_acceptPoolDelegate() (gas: 102768)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 107662)
[PASS] test_setPendingPoolDelegate_asGovernor() (gas: 70543)
[PASS] test_setPendingPoolDelegate_asOperationalAdmin() (gas: 75016)
[PASS] test_setPendingPoolDelegate_asPoolDelegate() (gas: 65912)
[PASS] test_setPendingPoolDelegate_notPD() (gas: 104200)
[PASS] test_transferOwnedPoolManager_alreadyPoolDelegate() (gas: 138355)
[PASS] test_transferOwnedPoolManager_notPoolManager() (gas: 107966)
[PASS] test_transferOwnedPoolManager_notValidPoolDelegate() (gas: 115268)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 77.46ms (5.07ms CPU time)

Ran 1 test for tests/integration/loan/fixed-term/DeployLoan.t.sol:DeployFixedTermLoanTests
[PASS] test_deployFixedTermLoan_feeManagerCheck() (gas: 848518)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 34.16ms (981.29µs CPU time)

Ran 9 tests for tests/integration/loan/DeployLoanByBorrower.t.sol:DeployLoanByBorrowerTests
[PASS] test_deployLoan_FTL_invalidBorrower() (gas: 641441)
[PASS] test_deployLoan_FTL_invalidInstance() (gas: 641189)
[PASS] test_deployLoan_FTL_setCanDeployFromByOA() (gas: 65080)
[PASS] test_deployLoan_FTL_success() (gas: 625435)
[PASS] test_deployLoan_FTL_validBorrowerSetByOA() (gas: 645493)
[PASS] test_deployLoan_FTL_validInstanceSetByOA() (gas: 643478)
[PASS] test_deployLoan_OTL_invalidBorrower() (gas: 492160)
[PASS] test_deployLoan_OTL_invalidInstance() (gas: 491985)
[PASS] test_deployLoan_OTL_success() (gas: 478061)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 38.24ms (5.43ms CPU time)

Ran 10 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultFailureTests
[PASS] test_triggerDefault_invalidLoanManager() (gas: 2846670)
[PASS] test_triggerDefault_notAuthorized() (gas: 54880)
[PASS] test_triggerDefault_notFactory() (gas: 50944)
[PASS] test_triggerDefault_notInDefault_boundary() (gas: 561567)
[PASS] test_triggerDefault_notLoan() (gas: 87796)
[PASS] test_triggerDefault_notPM() (gas: 396719)
[PASS] test_triggerDefault_protocolPaused_loanManager() (gas: 51897)
[PASS] test_triggerDefault_protocolPaused_poolManager() (gas: 51491)
[PASS] test_triggerDefault_repossess_notLender() (gas: 38749)
[PASS] test_triggerDefault_treasuryZeroAddress() (gas: 489125)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 69.47ms (6.70ms CPU time)

Ran 20 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolTests
[PASS] test_deployPool_failIfCalledPMFactoryDirectly() (gas: 31223)
[PASS] test_deployPool_failIfCalledWMFactoryDirectly() (gas: 33435)
[PASS] test_deployPool_failWithAssetNotAllowed() (gas: 300814)
[PASS] test_deployPool_failWithInsufficientPDApproval() (gas: 3889348)
[PASS] test_deployPool_failWithInvalidAsset() (gas: 391928)
[PASS] test_deployPool_failWithInvalidLMFactory() (gas: 3254123)
[PASS] test_deployPool_failWithInvalidManagementFee() (gas: 3888449)
[PASS] test_deployPool_failWithInvalidPD() (gas: 51286)
[PASS] test_deployPool_failWithInvalidPMFactory() (gas: 66611)
[PASS] test_deployPool_failWithInvalidStart() (gas: 3133594)
[PASS] test_deployPool_failWithInvalidWMCyclicalFactory() (gas: 70353)
[PASS] test_deployPool_failWithNonZeroSupplyAndZeroMigrationAdmin() (gas: 382893)
[PASS] test_deployPool_failWithOwnedPoolManager() (gas: 4226494)
[PASS] test_deployPool_failWithWindowDurationGtCycleDuration() (gas: 3133416)
[PASS] test_deployPool_failWithZeroAsset() (gas: 263415)
[PASS] test_deployPool_failWithZeroWindowDuration() (gas: 3133393)
[PASS] test_deployPool_success() (gas: 4164801)
[PASS] test_deployPool_successWithInitialSupply() (gas: 4118264)
[PASS] test_deployPool_successWithZeroMigrationAdmin() (gas: 4077408)
[PASS] test_deployPool_success_validPDSetByOA() (gas: 4100933)
Suite result: ok. 20 passed; 0 failed; 0 skipped; finished in 66.60ms (22.14ms CPU time)

Ran 9 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:OpenTermLoanTriggerDefaultTests
[PASS] test_triggerDefault_called() (gas: 511810)
[PASS] test_triggerDefault_feesAndFullRecovery() (gas: 284942)
[PASS] test_triggerDefault_feesAndPartialRecovery() (gas: 276132)
[PASS] test_triggerDefault_impaired() (gas: 530095)
[PASS] test_triggerDefault_impaired_feesAndFullRecovery() (gas: 314498)
[PASS] test_triggerDefault_impaired_onlyFeesRecovered() (gas: 303193)
[PASS] test_triggerDefault_latePayment() (gas: 438353)
[PASS] test_triggerDefault_onlyFeesRecovered() (gas: 263007)
[PASS] test_triggerDefault_setByOperationalAdmin() (gas: 272145)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 91.71ms (22.04ms CPU time)

Ran 12 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolWMQueueFailureTests
[PASS] test_deployPoolWMQueue_failIfAlreadyOwned() (gas: 4315654)
[PASS] test_deployPoolWMQueue_failIfInsufficientAmount() (gas: 4026425)
[PASS] test_deployPoolWMQueue_failIfInsufficientApproval() (gas: 4026434)
[PASS] test_deployPoolWMQueue_failIfInvalidManagementFeeRate() (gas: 3953577)
[PASS] test_deployPoolWMQueue_failIfInvalidPD() (gas: 48646)
[PASS] test_deployPoolWMQueue_failIfInvalidPMFactory() (gas: 4105922)
[PASS] test_deployPoolWMQueue_failIfInvalidPPM() (gas: 4113707)
[PASS] test_deployPoolWMQueue_failIfInvalidPoolAsset() (gas: 649187)
[PASS] test_deployPoolWMQueue_failIfInvalidWMFactory() (gas: 4109764)
[PASS] test_deployPoolWMQueue_failIfInvalidWMQFactory() (gas: 65095)
[PASS] test_deployPoolWMQueue_failIfPoolAssetNotAllowed() (gas: 298164)
[PASS] test_deployPoolWMQueue_failIfSaltCollision() (gas: 17595493375392519607)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 59.28ms (21.94ms CPU time)

Ran 3 tests for tests/integration/loan/fixed-term/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notAuthorized() (gas: 54788)
[PASS] test_triggerDefault_notFactory() (gas: 50887)
[PASS] test_triggerDefault_notPoolManager() (gas: 53810)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 65.64ms (651.98µs CPU time)

Ran 2 tests for tests/integration/pool/DeployPool.t.sol:DeployPoolWMQueueTests
[PASS] test_deployPoolWMQueue_success() (gas: 4174383)
[PASS] test_deployPoolWMQueue_withoutCoverAmount() (gas: 4076957)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 78.12ms (8.25ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/UnrealizedLosses.t.sol:UnrealizedLossesTests
[PASS] test_unrealizedLosses_depositWithUnrealizedLosses() (gas: 439023)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_fullLiquidity() (gas: 540058)
[PASS] test_unrealizedLosses_redeemWithUnrealizedLosses_partialLiquidity() (gas: 1762099)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 45.52ms (7.10ms CPU time)

Ran 5 tests for tests/integration/governor-timelock/UnscheduleProposals.t.sol:UnscheduleProposalsTests
[PASS] test_setUp() (gas: 55515)
[PASS] test_unscheduleProposals_revert_notCanceller() (gas: 11331)
[PASS] test_unscheduleProposals_revert_notUnschedulable() (gas: 87421)
[PASS] test_unscheduleProposals_revert_proposalNotFound() (gas: 16176)
[PASS] test_unscheduleProposals_success() (gas: 125804)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 38.07ms (1.16ms CPU time)

Ran 4 tests for tests/integration/governor-timelock/UpdateRole.t.sol:UpdateRoleTests
[PASS] test_setUp() (gas: 55630)
[PASS] test_updateRole_revert_notSelf() (gas: 10720)
[PASS] test_updateRole_success_grantRole() (gas: 93221)
[PASS] test_updateRole_success_revokeRole() (gas: 79559)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 66.02ms (1.16ms CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:DepositFailureTests
[PASS] test_deposit_insufficientApproval() (gas: 322888)
[PASS] test_deposit_liquidityCapExceeded() (gas: 407385)
[PASS] test_deposit_privatePoolInvalidRecipient() (gas: 374377)
[PASS] test_deposit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 352803)
[PASS] test_deposit_protocolPaused() (gas: 96578)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 35.44ms (3.34ms CPU time)

Ran 2 tests for tests/integration/globals/Upgrade.t.sol:GlobalsUpgradeTests
[PASS] test_upgradeGlobals() (gas: 25623)
[PASS] test_upgradeGlobals_notAdmin() (gas: 29194)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 44.94ms (1.11ms CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:LiquidationUpgradeTests
[PASS] test_upgradeLiquidator_delayNotPassed() (gas: 155656)
[PASS] test_upgradeLiquidator_durationPassed() (gas: 155965)
[PASS] test_upgradeLiquidator_governor_noTimelockNeeded() (gas: 196878)
[PASS] test_upgradeLiquidator_noTimelock() (gas: 164162)
[PASS] test_upgradeLiquidator_timelockExtended() (gas: 273212)
[PASS] test_upgradeLiquidator_timelockShortened() (gas: 273644)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 46.48ms (4.06ms CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:LoanManagerUpgradeTests
[PASS] test_upgradeLoanManager_delayNotPassed() (gas: 152201)
[PASS] test_upgradeLoanManager_durationPassed() (gas: 152530)
[PASS] test_upgradeLoanManager_noTimelock() (gas: 160731)
[PASS] test_upgradeLoanManager_securityAdmin_noTimelockNeeded() (gas: 182236)
[PASS] test_upgradeLoanManager_timelockExtended() (gas: 263091)
[PASS] test_upgradeLoanManager_timelockShortened() (gas: 263500)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 72.10ms (5.36ms CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:PoolManagerUpgradeTests
[PASS] test_upgradePoolManager_delayNotPassed() (gas: 131600)
[PASS] test_upgradePoolManager_durationPassed() (gas: 131898)
[PASS] test_upgradePoolManager_noTimelock() (gas: 138514)
[PASS] test_upgradePoolManager_securityAdmin_noTimelockNeeded() (gas: 160012)
[PASS] test_upgradePoolManager_timelockExtended() (gas: 219099)
[PASS] test_upgradePoolManager_timelockShortened() (gas: 219464)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 58.03ms (3.30ms CPU time)

Ran 1 test for tests/integration/globals/Upgrade.t.sol:UnscheduleCallTests
[PASS] test_unscheduleCall_governor() (gas: 82178)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 37.03ms (309.68µs CPU time)

Ran 6 tests for tests/integration/globals/Upgrade.t.sol:WithdrawalManagerUpgradeTests
[PASS] test_upgradeWithdrawalManager_delayNotPassed() (gas: 135456)
[PASS] test_upgradeWithdrawalManager_durationPassed() (gas: 135736)
[PASS] test_upgradeWithdrawalManager_noTimelock() (gas: 143360)
[PASS] test_upgradeWithdrawalManager_securityAdmin_noTimelockNeeded() (gas: 164864)
[PASS] test_upgradeWithdrawalManager_timelockExtended() (gas: 231429)
[PASS] test_upgradeWithdrawalManager_timelockShortened() (gas: 231882)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 63.64ms (7.36ms CPU time)

Ran 1 test for tests/integration/globals/ValidCollateral.t.sol:ValidCollateralTests
[PASS] test_setIsCollateral_invalidCollateral() (gas: 785878)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 40.17ms (1.09ms CPU time)

Ran 17 tests for tests/integration/withdrawal-manager/queue/ViewFunctions.t.sol:WithdrawalManagerQueueViewFunctionsAdditionalTests
[PASS] test_asset_constantAddress() (gas: 458950)
[PASS] test_factory() (gas: 15041)
[PASS] test_globals_updatesAfterFactorySetGlobals() (gas: 2800885)
[PASS] test_governor_updatesWhenGlobalsChanges() (gas: 2806103)
[PASS] test_implementation_updatesAfterUpgrade() (gas: 3261162)
[PASS] test_isInExitWindow() (gas: 12926)
[PASS] test_lockedLiquidity_constantZero() (gas: 455196)
[PASS] test_lockedShares_updatesAfterProcessing() (gas: 435214)
[PASS] test_poolDelegate_updatesAfterTransfer() (gas: 113044)
[PASS] test_poolManager_address_constant() (gas: 14947)
[PASS] test_pool_address_constant() (gas: 15016)
[PASS] test_previewRedeem_reflectsUpdatedManualShares() (gas: 452514)
[PASS] test_previewWithdraw_alwaysZero() (gas: 319013)
[PASS] test_queue_updatesAfterRequestAndProcess() (gas: 457603)
[PASS] test_requestIds_updatesAfterRequestRedeem() (gas: 319120)
[PASS] test_requests_updatesAfterAddAndRemove() (gas: 326132)
[PASS] test_securityAdmin_updatesAfterChange() (gas: 52802)
Suite result: ok. 17 passed; 0 failed; 0 skipped; finished in 51.96ms (13.86ms CPU time)

Ran 3 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:RequestWithdrawFailureTests
[PASS] test_requestWithdraw_failIfInsufficientApproval() (gas: 269088)
[PASS] test_requestWithdraw_failIfNotPM() (gas: 17863)
[PASS] test_requestWithdraw_failIfNotPool() (gas: 43540)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 53.23ms (4.92ms CPU time)

Ran 4 tests for tests/integration/pool/DepositAndMint.t.sol:DepositTest
[PASS] testDeepFuzz_deposit_singleUser(uint256) (runs: 100, μ: 284945, ~: 284945)
[PASS] testDeepFuzz_deposit_variableExchangeRate(uint256,uint256) (runs: 100, μ: 1471328, ~: 1474082)
[PASS] test_deposit_singleUser_oneToOne() (gas: 281372)
[PASS] test_deposit_twoUsers_oneToOne() (gas: 383362)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 589.13ms (534.18ms CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:DepositWithPermitFailureTests
[PASS] test_depositWithPermit_invalidSignature() (gas: 478175)
[PASS] test_depositWithPermit_liquidityCapExceeded() (gas: 445369)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient() (gas: 407626)
[PASS] test_depositWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 386011)
[PASS] test_depositWithPermit_protocolPaused() (gas: 149545)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 78.22ms (12.29ms CPU time)

Ran 4 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:RequestWithdrawTests
[PASS] testDeepFuzz_requestWithdraw(uint256,uint256) (runs: 100, μ: 348847, ~: 349267)
[PASS] test_requestWithdraw() (gas: 323055)
[PASS] test_requestWithdraw_premature() (gas: 325643)
[PASS] test_requestWithdraw_withApproval() (gas: 334852)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 233.05ms (160.65ms CPU time)

Ran 5 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawFailureTests
[PASS] testDeepFuzz_withdraw(uint256,address,address) (runs: 100, μ: 69763, ~: 69763)
[PASS] test_withdraw_failIfNotPool() (gas: 43731)
[PASS] test_withdraw_failIfNotPoolManager() (gas: 18071)
[PASS] test_withdraw_premature() (gas: 74169)
[PASS] test_withdraw_zeroAssetInput() (gas: 71610)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 118.31ms (50.67ms CPU time)

Ran 1 test for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawOnPermissionedPool
[PASS] test_withdraw_withUnwhitelistedUser() (gas: 457088)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 62.73ms (1.24ms CPU time)

Ran 2 tests for tests/integration/pool/DepositAndMint.t.sol:DepositWithPermitTests
[PASS] testDeepFuzz_depositWithPermit_singleUser(uint256) (runs: 100, μ: 317487, ~: 317485)
[PASS] test_depositWithPermit_singleUser() (gas: 313729)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 247.58ms (179.99ms CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:MintFailureTests
[PASS] test_mint_insufficientApproval() (gas: 325202)
[PASS] test_mint_liquidityCapExceeded() (gas: 435979)
[PASS] test_mint_privatePoolInvalidRecipient() (gas: 380774)
[PASS] test_mint_privatePoolInvalidRecipient_openPoolToPublic() (gas: 359264)
[PASS] test_mint_protocolPaused() (gas: 150303)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 41.38ms (3.70ms CPU time)

Ran 3 tests for tests/integration/withdrawal-manager/cyclical/Withdraw.t.sol:WithdrawScenarios
[PASS] test_withdrawals_cashInjection() (gas: 4472091)
[PASS] test_withdrawals_poorExchangeRates() (gas: 4195309)
[PASS] test_withdrawals_withUpdateAccounting() (gas: 4164279)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 108.97ms (45.32ms CPU time)

Ran 3 tests for tests/integration/governor-timelock/WithdrawERC20Token.t.sol:WithdrawERC20TokenTests
[PASS] test_setUp() (gas: 55560)
[PASS] test_withdrawERC20Token_revert_notTokenWithdrawer() (gas: 12794)
[PASS] test_withdrawERC20Token_success() (gas: 97288)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 37.00ms (1.24ms CPU time)

Ran 4 tests for tests/integration/pool/DepositAndMint.t.sol:MintTest
[PASS] testDeepFuzz_mint_singleUser(uint256) (runs: 100, μ: 287092, ~: 287092)
[PASS] testDeepFuzz_mint_variableExchangeRate(uint256,uint256) (runs: 100, μ: 1497606, ~: 1497366)
[PASS] test_mint_singleUser_oneToOne() (gas: 283397)
[PASS] test_mint_twoUsers_oneToOne() (gas: 402194)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 555.34ms (489.55ms CPU time)

Ran 5 tests for tests/integration/pool/DepositAndMint.t.sol:MintWithPermitFailureTests
[PASS] test_mintWithPermit_insufficientPermit() (gas: 479273)
[PASS] test_mintWithPermit_liquidityCapExceeded() (gas: 474033)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient() (gas: 414036)
[PASS] test_mintWithPermit_privatePoolInvalidRecipient_openPoolToPublic() (gas: 392448)
[PASS] test_mintWithPermit_protocolPaused() (gas: 152799)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 72.59ms (8.22ms CPU time)

Ran 3 tests for tests/integration/loan/fixed-term/Liquidation.t.sol:FinishLiquidationFailureTests
[PASS] test_finishLiquidation_failIfLiquidationNotActive() (gas: 98052)
[PASS] test_finishLiquidation_failIfNotPD() (gas: 52502)
[PASS] test_finishLiquidation_failIfNotPoolManager() (gas: 52309)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 42.89ms (2.77ms CPU time)

Ran 14 tests for tests/integration/loan/fixed-term/Liquidation.t.sol:LoanLiquidationTests
[PASS] test_finishCollateralLiquidation_asOperationalAdmin() (gas: 2135508)
[PASS] test_loanDefault_fullCover_noCollateral_noImpairment() (gas: 1399241)
[PASS] test_loanDefault_fullCover_noCollateral_withImpairment() (gas: 1478715)
[PASS] test_loanDefault_fullCover_withCollateral_noImpairment() (gas: 2244965)
[PASS] test_loanDefault_fullCover_withCollateral_withImpairment() (gas: 2270077)
[PASS] test_loanDefault_noCover_noCollateral_noImpairment() (gas: 1302284)
[PASS] test_loanDefault_noCover_noCollateral_withImpairment() (gas: 1383822)
[PASS] test_loanDefault_noCover_withCollateral_noImpairment() (gas: 2158238)
[PASS] test_loanDefault_noCover_withCollateral_withImpairment() (gas: 2184674)
[PASS] test_loanDefault_partialCover_noCollateral_noImpairment() (gas: 1399174)
[PASS] test_loanDefault_partialCover_noCollateral_withImpairment() (gas: 1478680)
[PASS] test_loanDefault_partialCover_withCollateral_noImpairment() (gas: 2244824)
[PASS] test_loanDefault_partialCover_withCollateral_withImpairment() (gas: 2270097)
[PASS] test_setMaxCoverLiquidationPercent_asOperationalAdmin() (gas: 36283)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 105.72ms (54.54ms CPU time)

Ran 2 tests for tests/integration/pool/DepositAndMint.t.sol:MintWithPermitTests
[PASS] testDeepFuzz_mintWithPermit_singleUser(uint256) (runs: 100, μ: 316863, ~: 316871)
[PASS] test_mintWithPermit_singleUser() (gas: 315991)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 144.67ms (107.06ms CPU time)

Ran 5 tests for tests/integration/loan-manager/fixed-term/LoanManagerGetters.t.sol:LoanManagerGetterTests
[PASS] test_loanManagerGetters_addresses() (gas: 20638)
[PASS] test_loanManagerGetters_liquidationInformation() (gas: 961343)
[PASS] test_loanManagerGetters_paymentInformation() (gas: 26663)
[PASS] test_loanManagerGetters_sortedPayments() (gas: 1251080)
[PASS] test_loanManagerGetters_uints() (gas: 30251)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 80.56ms (10.54ms CPU time)

Ran 12 tests for tests/integration/governor-timelock/ExecuteProposal.t.sol:ExecuteProposalsTests
[PASS] test_executeProposals_executionFailed_notPendingAdmin() (gas: 128228)
[PASS] test_executeProposals_revert_emptyArray() (gas: 14687)
[PASS] test_executeProposals_revert_executionFailed() (gas: 111833)
[PASS] test_executeProposals_revert_invalidData() (gas: 155496)
[PASS] test_executeProposals_revert_invalidDataLength() (gas: 15673)
[PASS] test_executeProposals_revert_invalidTargetsLength() (gas: 15099)
[PASS] test_executeProposals_revert_notExecutable() (gas: 232176)
[PASS] test_executeProposals_revert_notExecutable_failedToExecuteTheSameProposalTwice() (gas: 118828)
[PASS] test_executeProposals_revert_notExecutor() (gas: 12197)
[PASS] test_executeProposals_success() (gas: 205050)
[PASS] test_executeProposals_success_emptyData() (gas: 150877)
[PASS] test_setUp() (gas: 55652)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 43.88ms (5.93ms CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_failIfNotLoan() (gas: 65297)
[PASS] test_makePayment_failWithTransferFailed() (gas: 209606)
[PASS] test_makePayment_failWithTransferFromFailed() (gas: 131616)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 39.35ms (1.03ms CPU time)

Ran 9 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentOpenTermFailureTests
[PASS] test_makePayment_inactiveLoan() (gas: 444074)
[PASS] test_makePayment_invalidPrincipalIncrease() (gas: 52101)
[PASS] test_makePayment_notLoan() (gas: 485533)
[PASS] test_makePayment_tooLittlePrincipal() (gas: 126383)
[PASS] test_makePayment_tooMuchPrincipal() (gas: 41257)
[PASS] test_makePayment_transferFailed() (gas: 74027)
[PASS] test_makePayment_transferToPoolBoundary() (gas: 239002)
[PASS] test_makePayment_transferToPoolDelegateBoundary() (gas: 283464)
[PASS] test_makePayment_transferToTreasuryBoundary() (gas: 354885)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 46.38ms (4.23ms CPU time)

Ran 1 test for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsDomainStartGtDomainEnd
[PASS] test_makePayment_domainStart_gt_domainEnd() (gas: 3268288)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 47.03ms (10.85ms CPU time)

Ran 1 test for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsPastDomainEnd
[PASS] test_makePayment_lateLoan3_loan1NotPaid_loan2NotPaid() (gas: 850919)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 55.60ms (2.92ms CPU time)

Ran 3 tests for tests/integration/loan-manager/fixed-term/FetchValuesFromLM.t.sol:LoanManagerIsLiquidationActiveGetterTests
[PASS] test_isLiquidationActive_afterLiquidation() (gas: 886984)
[PASS] test_isLiquidationActive_beforeLiquidation() (gas: 15248)
[PASS] test_isLiquidationActive_duringLiquidation() (gas: 576664)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 45.46ms (2.50ms CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanAmortized
[PASS] test_makePayment_earlyPayment_amortized() (gas: 669928)
[PASS] test_makePayment_latePayment_amortized() (gas: 676287)
[PASS] test_makePayment_onTimePayment_amortized() (gas: 669971)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 52.30ms (6.35ms CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanInterestOnly
[PASS] test_makePayment_earlyPayment_interestOnly() (gas: 648406)
[PASS] test_makePayment_latePayment_interestOnly() (gas: 651972)
[PASS] test_makePayment_onTimePayment_interestOnly() (gas: 645782)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 49.13ms (5.62ms CPU time)

Ran 4 tests for tests/integration/pool/FetchValuesFromPM.t.sol:PoolManagerGetterTests
[PASS] testDeepFuzz_getEscrowParams_shouldReturnValues(uint256) (runs: 100, μ: 19471, ~: 19173)
[PASS] test_addressGetters() (gas: 35571)
[PASS] test_hasSufficientCover_insufficientCover(uint256) (runs: 100, μ: 131861, ~: 132415)
[PASS] test_hasSufficientCover_sufficientCover(uint256) (runs: 100, μ: 140902, ~: 141040)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 127.87ms (89.64ms CPU time)

Ran 4 tests for tests/integration/loan-manager/fixed-term/FinishCollateralLiquidation.t.sol:FinishCollateralLiquidationFailureTests
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 52525)
[PASS] test_finishCollateralLiquidation_notFinished() (gas: 598581)
[PASS] test_finishCollateralLiquidation_notPoolManager() (gas: 52243)
[PASS] test_finishCollateralLiquidation_whenImpaired() (gas: 261449)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 38.97ms (1.93ms CPU time)

Ran 4 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsSingleLoanOpenTerm
[PASS] test_makePayment_OT_latePayment() (gas: 594694)
[PASS] test_makePayment_OT_onTimePayment() (gas: 590271)
[PASS] test_makePayment_OT_withCall() (gas: 573155)
[PASS] test_makePayment_OT_withImpairment() (gas: 629232)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 72.06ms (13.38ms CPU time)

Ran 10 tests for tests/integration/loan-manager/Fund.t.sol:FixedTermLoanManagerFundTests
[PASS] test_fund_failIfAmountGreaterThanLockedLiquidity() (gas: 1634973)
[PASS] test_fund_failIfInsufficientCover() (gas: 244126)
[PASS] test_fund_failIfLoanActive() (gas: 909352)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 54070)
[PASS] test_fund_failIfPoolDoesNotApprovePM() (gas: 255969)
[PASS] test_fund_failIfProtocolIsPaused() (gas: 56674)
[PASS] test_fund_failIfTermsNotAccepted() (gas: 289351)
[PASS] test_fund_failIfTotalSupplyIsZero() (gas: 430423)
[PASS] test_fund_oneLoan() (gas: 799924)
[PASS] test_fund_twoLoans() (gas: 1299910)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 52.63ms (13.64ms CPU time)

Ran 18 tests for tests/integration/loan-manager/Fund.t.sol:OpenTermLoanManagerFundTests
[PASS] test_fund_failIfTermsNotAccepted() (gas: 457512)
[PASS] test_fund_insufficientCover() (gas: 378141)
[PASS] test_fund_invalidBorrower() (gas: 95441)
[PASS] test_fund_invalidLoanFactory() (gas: 82976)
[PASS] test_fund_invalidLoanInstance() (gas: 172811)
[PASS] test_fund_invalidLoanManagerFactory() (gas: 127592)
[PASS] test_fund_loanActive() (gas: 694836)
[PASS] test_fund_loanManagerApproveFailure() (gas: 439413)
[PASS] test_fund_loanNotActive() (gas: 642208)
[PASS] test_fund_loanTransferFailure() (gas: 505932)
[PASS] test_fund_lockedLiquidity() (gas: 544244)
[PASS] test_fund_notLender() (gas: 36746)
[PASS] test_fund_notLoanManager() (gas: 352035)
[PASS] test_fund_notPoolDelegate() (gas: 54115)
[PASS] test_fund_poolManagerTransferFailure() (gas: 387100)
[PASS] test_fund_protocolPause() (gas: 49418)
[PASS] test_fund_success() (gas: 616096)
[PASS] test_fund_zeroSupply() (gas: 565146)
Suite result: ok. 18 passed; 0 failed; 0 skipped; finished in 56.64ms (15.91ms CPU time)

Ran 3 tests for tests/integration/loan/MakePayment.t.sol:MakePaymentTestsTwoLoans
[PASS] test_makePayment_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 1287277)
[PASS] test_makePayment_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 1292917)
[PASS] test_makePayment_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 1285143)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 105.16ms (28.37ms CPU time)

Ran 4 tests for tests/integration/loan/MapleBorrowerActions.t.sol:MapleBorrowerActionsTests
[PASS] test_acceptLoanTerms_FTL() (gas: 78162)
[PASS] test_acceptLoanTerms_FTL_failIfNotBorrower() (gas: 26113)
[PASS] test_acceptLoanTerms_OTL() (gas: 78265)
[PASS] test_acceptLoanTerms_OTL_failIfNotBorrower() (gas: 26171)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 39.18ms (683.35µs CPU time)

Ran 28 tests for tests/integration/governor-timelock/MapleGlobalsFunctions.t.sol:MapleGlobalsFunctionsTests
[PASS] test_activatePoolManager() (gas: 4169639)
[PASS] test_setBootstrapMint() (gas: 102420)
[PASS] test_setCanDeployFrom() (gas: 168484)
[PASS] test_setContractPause() (gas: 161648)
[PASS] test_setDefaultTimelockParameters() (gas: 88103)
[PASS] test_setFunctionUnpause() (gas: 163792)
[PASS] test_setManualOverridePrice() (gas: 102496)
[PASS] test_setMapleTreasury() (gas: 90253)
[PASS] test_setMaxCoverLiquidationPercent() (gas: 102407)
[PASS] test_setMigrationAdmin() (gas: 90248)
[PASS] test_setMinCoverAmount() (gas: 102351)
[PASS] test_setOperationalAdmin() (gas: 90217)
[PASS] test_setPendingGovernor() (gas: 110450)
[PASS] test_setPlatformManagementFeeRate() (gas: 104001)
[PASS] test_setPlatformOriginationFeeRate() (gas: 104027)
[PASS] test_setPlatformServiceFeeRate() (gas: 104034)
[PASS] test_setPriceOracle() (gas: 105423)
[PASS] test_setProtocolPause() (gas: 144687)
[PASS] test_setSecurityAdmin() (gas: 90221)
[PASS] test_setTimelockWindow() (gas: 104725)
[PASS] test_setTimelockWindows() (gas: 134404)
[PASS] test_setUp() (gas: 55692)
[PASS] test_setValidBorrower() (gas: 161060)
[PASS] test_setValidCollateralAsset() (gas: 160951)
[PASS] test_setValidInstanceOf() (gas: 162677)
[PASS] test_setValidPoolAsset() (gas: 160934)
[PASS] test_setValidPoolDelegate() (gas: 161298)
[PASS] test_unscheduleCall() (gas: 131572)
Suite result: ok. 28 passed; 0 failed; 0 skipped; finished in 60.57ms (19.85ms CPU time)

Ran 6 tests for tests/integration/governor-timelock/MapleProxyFactoryFunctions.t.sol:MapleProxyFactoryFunctionsTests
[PASS] test_disableUpgradePath() (gas: 1776464)
[PASS] test_enabledUpgradePath() (gas: 1064050)
[PASS] test_registerImplementation() (gas: 1301690)
[PASS] test_setDefaultVersion() (gas: 2030071)
[PASS] test_setGlobals() (gas: 941324)
[PASS] test_setUp() (gas: 55563)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 60.06ms (23.16ms CPU time)

Ran 8 tests for tests/integration/loan-manager/fixed-term/GetExpectedAmount.t.sol:GetExpectedAmountTests
[PASS] testFork_getExpectedAmount_currentPrice() (gas: 109172)
[PASS] testFork_getExpectedAmount_manualOverride() (gas: 85091)
[PASS] testFork_getExpectedAmount_oracleNotSet() (gas: 54247)
[PASS] testFork_getExpectedAmount_withMinRatio() (gas: 155454)
[PASS] testFork_getExpectedAmount_withSlippage() (gas: 155427)
[PASS] testFork_getExpectedAmount_withSlippageAndMinRatio_minRatioHigher() (gas: 186306)
[PASS] testFork_getExpectedAmount_withSlippageAndMinRatio_slippageHigher() (gas: 186319)
[PASS] testFork_getExpectedAmount_zeroAmount() (gas: 109096)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 181.53ms (13.85ms CPU time)

Ran 6 tests for tests/integration/globals/OperationalAdmin.t.sol:OperationalAdminTests
[PASS] test_operationalAdminAcl_setMinCoverAmount() (gas: 47511)
[PASS] test_operationalAdminAcl_setPermissionAdmin() (gas: 64676)
[PASS] test_operationalAdminAcl_setPlatformManagementFeeRate() (gas: 49906)
[PASS] test_operationalAdminAcl_setPlatformOriginationFeeRate() (gas: 49947)
[PASS] test_operationalAdminAcl_setPlatformServiceFeeRate() (gas: 49970)
[PASS] test_operationalAdminAcl_setValidInstanceOf() (gas: 48755)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 43.38ms (917.73µs CPU time)

Ran 4 tests for tests/integration/globals/GetLatestPrice.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice_currentPrice() (gas: 74222)
[PASS] test_getLatestPrice_manualOverride() (gas: 46136)
[PASS] test_getLatestPrice_stalePrice() (gas: 100591)
[PASS] test_getLatestPrice_unknownAsset() (gas: 20443)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 166.40ms (1.16ms CPU time)

Ran 1 test for tests/integration/governor-timelock/GovernorTimelockTestBase.t.sol:GovernorTimelockTestBase
[PASS] test_setUp() (gas: 55582)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 36.52ms (255.86µs CPU time)

Ran 2 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairAndRefinanceTests
[PASS] test_impairLoan_earlyThenRefinance() (gas: 1018409)
[PASS] test_impairLoan_lateThenRefinance() (gas: 813860)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 54.99ms (12.37ms CPU time)

Ran 4 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairFailureTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 229807)
[PASS] test_impairLoan_notAuthorized() (gas: 53922)
[PASS] test_impairLoan_notLender() (gas: 36377)
[PASS] test_impairLoan_protocolPaused() (gas: 49295)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 43.35ms (1.02ms CPU time)

Ran 2 tests for tests/integration/loan-manager/ImpairLoan.t.sol:FixedTermLoanManagerImpairSuccessTests
[PASS] test_impairLoan_thenCancel() (gas: 746474)
[PASS] test_impairLoan_thenRepay() (gas: 783151)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 56.59ms (5.40ms CPU time)

Ran 9 tests for tests/integration/loan-manager/ImpairLoan.t.sol:OpenTermLoanManagerImpairTests
[PASS] test_impairLoan_early() (gas: 201755)
[PASS] test_impairLoan_governorAcl() (gas: 117487)
[PASS] test_impairLoan_late() (gas: 202410)
[PASS] test_impairLoan_loanInactive() (gas: 198946)
[PASS] test_impairLoan_notAuthorized() (gas: 56233)
[PASS] test_impairLoan_notLender() (gas: 36565)
[PASS] test_impairLoan_notLoanContract() (gas: 39028)
[PASS] test_impairLoan_notLoanInLoanManager() (gas: 447652)
[PASS] test_impairLoan_protocolPaused() (gas: 49340)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 44.12ms (3.94ms CPU time)

Ran 9 tests for tests/integration/loan-manager/ImpairLoan.t.sol:OpenTermLoanManagerRemoveImpairmentTests
[PASS] test_removeLoanImpairment_early() (gas: 207789)
[PASS] test_removeLoanImpairment_late() (gas: 208238)
[PASS] test_removeLoanImpairment_late_withLateImpairment() (gas: 208284)
[PASS] test_removeLoanImpairment_notAuthorized() (gas: 68886)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 88505)
[PASS] test_removeLoanImpairment_notLender() (gas: 36696)
[PASS] test_removeLoanImpairment_notLoan() (gas: 39045)
[PASS] test_removeLoanImpairment_poolDelegateAfterGovernor() (gas: 137159)
[PASS] test_removeLoanImpairment_protocolPaused() (gas: 49340)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 69.80ms (4.28ms CPU time)

Ran 7 tests for tests/integration/globals/Pause.t.sol:PauseTests
[PASS] test_contractPause() (gas: 10531971)
[PASS] test_functionUnpauseAfterContractPause() (gas: 44355542)
[PASS] test_functionUnpauseAfterProtocolPause() (gas: 63244352)
[PASS] test_globalPause() (gas: 14055042)
[PASS] test_poolManager_canCall_contractPause() (gas: 78225)
[PASS] test_poolManager_canCall_functionUnpauseAfterProtocolPause() (gas: 84123)
[PASS] test_poolManager_canCall_protocolPause() (gas: 76584)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 583.19ms (531.46ms CPU time)

Ran 2 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:BalanceOfAssetsTests
[PASS] testDeepFuzz_balanceOfAssets(uint256,uint256,uint256) (runs: 100, μ: 395188, ~: 395025)
[PASS] test_balanceOfAssets() (gas: 388214)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 183.58ms (145.43ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:ConvertToAssetsTests
[PASS] test_convertToAssets_multipleUsers() (gas: 448716)
[PASS] test_convertToAssets_multipleUsers_changeTotalAssets() (gas: 471404)
[PASS] test_convertToAssets_singleUser() (gas: 272996)
[PASS] test_convertToAssets_zeroTotalSupply() (gas: 10148)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 49.62ms (3.14ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:ConvertToSharesTests
[PASS] test_convertToShares_multipleUsers() (gas: 448786)
[PASS] test_convertToShares_multipleUsers_changeTotalAssets() (gas: 471417)
[PASS] test_convertToShares_singleUser() (gas: 273037)
[PASS] test_convertToShares_zeroTotalSupply() (gas: 10253)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 51.37ms (3.20ms CPU time)

Ran 3 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxDepositTests
[PASS] testDeepFuzz_maxDeposit_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 240704, ~: 240698)
[PASS] test_maxDeposit_closedPool() (gas: 250013)
[PASS] test_maxDeposit_totalAssetsIncrease() (gas: 235529)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 103.96ms (58.51ms CPU time)

Ran 2 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:AutomatedPreviewRedeemWithQueueWMTests
[PASS] testFuzz_previewRedeem_notProcessed(uint256) (runs: 100, μ: 33939, ~: 33939)
[PASS] testFuzz_previewRedeem_processed(uint256) (runs: 100, μ: 274467, ~: 274467)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 143.19ms (106.51ms CPU time)

Ran 6 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxRedeemWMQueueTests
[PASS] test_maxRedeem_afterFullManualRedeem() (gas: 316767)
[PASS] test_maxRedeem_afterFullRedeem() (gas: 224297)
[PASS] test_maxRedeem_afterPartialManualRedeem() (gas: 356591)
[PASS] test_maxRedeem_afterPartialRedeem() (gas: 228683)
[PASS] test_maxRedeem_beforeRedeem() (gas: 34469)
[PASS] test_maxRedeem_notManual() (gas: 351421)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 43.04ms (4.60ms CPU time)

Ran 4 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxWithdrawTests
[PASS] testDeepFuzz_maxWithdraw_lockedShares_inExitWindow(uint256) (runs: 100, μ: 413338, ~: 413592)
[PASS] test_maxWithdraw_lockedShares_inExitWindow() (gas: 409620)
[PASS] test_maxWithdraw_lockedShares_notInExitWindow() (gas: 407604)
[PASS] test_maxWithdraw_noLockedShares_notInExitWindow() (gas: 265417)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 120.84ms (84.59ms CPU time)

Ran 3 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxRedeemTests
[PASS] test_maxRedeem_lockedShares_inExitWindow() (gas: 418030)
[PASS] test_maxRedeem_lockedShares_notInExitWindow() (gas: 411157)
[PASS] test_maxRedeem_noLockedShares_notInExitWindow() (gas: 270560)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 37.33ms (2.28ms CPU time)

Ran 5 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:MaxMintTests
[PASS] testDeepFuzz_maxMint_exchangeRateGtOne(uint256,uint256,uint256) (runs: 100, μ: 390283, ~: 390153)
[PASS] testDeepFuzz_maxMint_totalAssetsIncrease(uint256,uint256) (runs: 100, μ: 246940, ~: 246945)
[PASS] test_maxMint_closedPool() (gas: 258343)
[PASS] test_maxMint_exchangeRateGtOne() (gas: 383310)
[PASS] test_maxMint_totalAssetsIncrease() (gas: 241820)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 244.42ms (200.51ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 8228672)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 57.27ms (7.62ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 8319540)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 46.82ms (8.18ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 8320410)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 46.30ms (8.02ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 8703114)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 48.38ms (9.61ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 8030139)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 45.34ms (7.09ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 8260940)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 45.64ms (7.07ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 8621930)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 46.97ms (8.63ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 9005267)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 48.84ms (10.46ms CPU time)

Ran 1 test for scenarios/v2/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 9489212)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 49.29ms (10.94ms CPU time)

Ran 1 test for scenarios/v3/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 22742826)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 139.08ms (75.01ms CPU time)

Ran 1 test for scenarios/v3/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 10850618)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 89.00ms (42.35ms CPU time)

Ran 1 test for scenarios/v3/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 19954478)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 115.02ms (68.83ms CPU time)

Ran 1 test for scenarios/v3/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 15043640)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 95.48ms (49.17ms CPU time)

Ran 1 test for scenarios/v3/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 17996265)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 105.49ms (58.85ms CPU time)

Ran 1 test for scenarios/v3/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 9384088)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 73.38ms (27.29ms CPU time)

Ran 1 test for scenarios/v3/Scenarios.t.sol:Scenario
[PASS] test_sim() (gas: 6876986)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 64.43ms (18.18ms CPU time)

Ran 1 test for tests/protocol-upgrade/core-strategy/MapleCoreStrategyUpgradeBase.t.sol:MapleCoreStrategyUpgradeBaseTest
[PASS] test_setUp() (gas: 178687)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 261.72ms (881.88µs CPU time)

Ran 1 test for tests/protocol-upgrade/governor-timelock/GovernorTimelockUpgradeTestsBase.t.sol:GovernorTimelockUpgradeTestsBase
[PASS] testFork_setUp_governorTimelockUpgradeTests() (gas: 48663)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 284.49ms (8.25ms CPU time)

Ran 7 tests for tests/protocol-upgrade/governor-timelock/GovernorTimelockScenariosUpgrade.t.sol:GovernorTimelockScenariosUpgradeTests
[PASS] testFork_reclaimERC20_withoutChangingGovernorOnOldGlobals() (gas: 50685)
[PASS] testFork_setUp_governorTimelockUpgradeTests() (gas: 48901)
[PASS] testFork_unscheduleProposals_cancellerCanNotUnscheduleRoleUpdate() (gas: 83364)
[PASS] testFork_unscheduleProposals_cancellerUnschedulesMaliciousProposal() (gas: 88918)
[PASS] testFork_updateRoles_backupRoleAdmin_removesPrimaryRoleAdmin() (gas: 155599)
[PASS] testFork_upgradeWithdrawalManager() (gas: 303929)
[PASS] testFork_withdrawERC20Token_afterChangingTokenWithdrawer_withNewGovernorOnOldGlobals() (gas: 279129)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 294.28ms (17.91ms CPU time)

Ran 5 tests for tests/protocol-upgrade/withdrawal-manager/Spark.t.sol:SparkFork_MainnetController_SyrupUSDC
[PASS] testFork_deposit_USDC() (gas: 359393)
[PASS] testFork_deposit_requestAndCancelRedemption_USDC() (gas: 626516)
[PASS] testFork_deposit_requestAndProcessRedemption_full_USDC() (gas: 843613)
[PASS] testFork_deposit_requestAndProcessRedemption_partial_USDC() (gas: 843612)
[PASS] testFork_deposit_requestRedemption_USDC() (gas: 658083)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 299.12ms (50.61ms CPU time)

Ran 6 tests for tests/protocol-upgrade/governor-timelock/ProxyFactoryFunctionsUpgrade.t.sol:MapleProxyFactoryFunctionsUpgradeTests
[PASS] testFork_disableUpgradePath() (gas: 1630557)
[PASS] testFork_enabledUpgradePath() (gas: 977128)
[PASS] testFork_registerImplementation() (gas: 1195063)
[PASS] testFork_setDefaultVersion() (gas: 1854744)
[PASS] testFork_setGlobals() (gas: 867977)
[PASS] testFork_setUp_governorTimelockUpgradeTests() (gas: 48733)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 314.36ms (38.23ms CPU time)

Ran 4 tests for tests/protocol-upgrade/withdrawal-manager/RemoveShares.t.sol:RemoveSharesTests
[PASS] testFork_removeShares_completeRemoval_multipleRequests() (gas: 752188)
[PASS] testFork_removeShares_partialRemoval_multipleRequests() (gas: 748903)
[PASS] testFork_removeShares_partialRemoval_oneRequest() (gas: 158577)
[PASS] testFork_removeShares_revert_zeroShares() (gas: 86643)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 347.91ms (9.23ms CPU time)

Ran 6 tests for tests/protocol-upgrade/withdrawal-manager/RemoveSharesById.t.sol:RemoveSharesByIdTests
[PASS] testFork_removeSharesById_revert_insufficientShares() (gas: 48566)
[PASS] testFork_removeSharesById_revert_invalidRequest_requestAlreadyRemoved() (gas: 48113)
[PASS] testFork_removeSharesById_revert_noChange() (gas: 48441)
[PASS] testFork_removeSharesById_revert_notOwner() (gas: 48070)
[PASS] testFork_removeSharesById_success_completeRemoval() (gas: 133973)
[PASS] testFork_removeSharesById_success_partialRemoval() (gas: 210357)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 352.06ms (9.59ms CPU time)

Ran 4 tests for tests/protocol-upgrade/withdrawal-manager/ProcessRedemptions.t.sol:ProcessRedemptionsTests
[PASS] testFork_processRedemptions_revert_lowLiquidity() (gas: 251833)
[PASS] testFork_processRedemptions_revert_zeroShares() (gas: 59081)
[PASS] testFork_processRedemptions_success_multipleRequests() (gas: 677472)
[PASS] testFork_processRedemptions_success_processAllRequests() (gas: 658828)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 352.71ms (10.37ms CPU time)

Ran 2 tests for tests/protocol-upgrade/withdrawal-manager/RequestRedeem.t.sol:RequestRedeemTests
[PASS] testFork_requestRedeem_revert_zeroShares() (gas: 92652)
[PASS] testFork_requestRedeem_success() (gas: 572314)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 353.15ms (4.58ms CPU time)

Ran 2 tests for tests/protocol-upgrade/withdrawal-manager/ManualRedemption.t.sol:ManualRedemptionTests
[PASS] testFork_manualRedemption_revert_notPoolManager() (gas: 13918)
[PASS] testFork_manualRedemption_success() (gas: 592532)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 353.41ms (4.97ms CPU time)

Ran 5 tests for tests/protocol-upgrade/withdrawal-manager/RemoveRequest.t.sol:RemoveRequestTests
[PASS] testFork_removeRequest_revert_notInQueue() (gas: 65003)
[PASS] testFork_removeRequest_revert_notOwner() (gas: 65057)
[PASS] testFork_removeRequest_revert_zeroOwner() (gas: 54646)
[PASS] testFork_removeRequest_revert_zeroRequests() (gas: 56462)
[PASS] testFork_removeRequest_success_oneRequest() (gas: 144778)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 353.05ms (8.50ms CPU time)

Ran 2 tests for tests/protocol-upgrade/governor-timelock/GovernorTimelockUpgradeProcedure.t.sol:GovernorTimelockUpgradeProcedureTests
[PASS] testFork_governorTimelock_fullUpgradeProcedure() (gas: 2285248)
[PASS] testFork_setUp_governorTimelockUpgradeTests() (gas: 48685)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 426.37ms (150.20ms CPU time)

Ran 8 tests for tests/protocol-upgrade/core-strategy/RemoveShares.t.sol:RemoveSharesTests
[PASS] test_removeShares_revert_notStrategyManager() (gas: 56481)
[PASS] test_removeShares_revert_protocolIsPaused() (gas: 62228)
[PASS] test_removeShares_revert_wmInsufficientShares_notEnoughSharesRequested() (gas: 128733)
[PASS] test_removeShares_revert_zeroShares() (gas: 55010)
[PASS] test_removeShares_success_multipleRequests_allRequestsCompletelyRemoved() (gas: 1274937)
[PASS] test_removeShares_success_multipleRequests_firstRequestPartiallyRemoved_SecondRequestCompletelyRemoved() (gas: 1364343)
[PASS] test_removeShares_success_partialRemoval_onlyOneRequest() (gas: 1132573)
[PASS] test_setUp() (gas: 178788)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 160.59ms (27.63ms CPU time)

Ran 9 tests for tests/protocol-upgrade/core-strategy/RemoveSharesById.t.sol:RemoveSharesByIdTests
[PASS] test_removeSharesById_revert_invalidRequest() (gas: 99729)
[PASS] test_removeSharesById_revert_noChange() (gas: 625184)
[PASS] test_removeSharesById_revert_notOwner() (gas: 643919)
[PASS] test_removeSharesById_revert_notStrategyManager() (gas: 56460)
[PASS] test_removeSharesById_revert_protocolIsPaused() (gas: 62226)
[PASS] test_removeSharesById_revert_wmInsufficientShares() (gas: 646549)
[PASS] test_removeSharesById_success_multipleRequests_completelyRemoveMidRequest() (gas: 1647632)
[PASS] test_removeSharesById_success_singleRequest_partialRemoval_followedByCompleteRemoval() (gas: 1097906)
[PASS] test_setUp() (gas: 178788)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 161.23ms (33.50ms CPU time)

Ran 5 tests for tests/protocol-upgrade/withdrawal-manager/ProcessEmptyRedemptions.t.sol:ProcessEmptyRedemptionsTests
[PASS] testFork_processEmptyRedemptions_revert_notRedeemer() (gas: 53673)
[PASS] testFork_processEmptyRedemptions_success_multipleRequests() (gas: 162828)
[PASS] testFork_processEmptyRedemptions_success_multipleRequests_stopsAtNonEmpty() (gas: 165208)
[PASS] testFork_processEmptyRedemptions_success_removesEntireQueue() (gas: 222642)
[PASS] testFork_processEmptyRedemptions_zeroRequests_reverts() (gas: 54083)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 213.74ms (8.47ms CPU time)

Ran 28 tests for tests/protocol-upgrade/governor-timelock/GlobalsFunctionsUpgrade.t.sol:MapleGlobalsFunctionsUpgradeTests
[PASS] testFork_activatePoolManager() (gas: 408376)
[PASS] testFork_setBootstrapMint() (gas: 100650)
[PASS] testFork_setCanDeployFrom() (gas: 166533)
[PASS] testFork_setContractPause() (gas: 159736)
[PASS] testFork_setDefaultTimelockParameters() (gas: 86338)
[PASS] testFork_setFunctionUnpause() (gas: 161794)
[PASS] testFork_setManualOverridePrice() (gas: 100722)
[PASS] testFork_setMapleTreasury() (gas: 86770)
[PASS] testFork_setMaxCoverLiquidationPercent() (gas: 100632)
[PASS] testFork_setMigrationAdmin() (gas: 100440)
[PASS] testFork_setMinCoverAmount() (gas: 100594)
[PASS] testFork_setOperationalAdmin() (gas: 86733)
[PASS] testFork_setPendingGovernor() (gas: 108427)
[PASS] testFork_setPlatformManagementFeeRate() (gas: 102169)
[PASS] testFork_setPlatformOriginationFeeRate() (gas: 102185)
[PASS] testFork_setPlatformServiceFeeRate() (gas: 102212)
[PASS] testFork_setPriceOracle() (gas: 103653)
[PASS] testFork_setProtocolPause() (gas: 142720)
[PASS] testFork_setSecurityAdmin() (gas: 86704)
[PASS] testFork_setTimelockWindow() (gas: 102932)
[PASS] testFork_setTimelockWindows() (gas: 132344)
[PASS] testFork_setUp_governorTimelockUpgradeTests() (gas: 48962)
[PASS] testFork_setValidBorrower() (gas: 159096)
[PASS] testFork_setValidCollateralAsset() (gas: 159076)
[PASS] testFork_setValidInstanceOf() (gas: 160768)
[PASS] testFork_setValidPoolAsset() (gas: 159032)
[PASS] testFork_setValidPoolDelegate() (gas: 159387)
[PASS] testFork_unscheduleCall() (gas: 127788)
Suite result: ok. 28 passed; 0 failed; 0 skipped; finished in 512.97ms (26.87ms CPU time)

Ran 1 test for tests/protocol-upgrade/withdrawal-manager/Migration.t.sol:MigrateTest
[PASS] testFork_withdrawalManagers_migrate_success() (gas: 707408)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 252.31ms (4.27ms CPU time)

Ran 1 test for tests/protocol-upgrade/governor-timelock/plasma/GovernorTimelockUpgradeTestsBasePlasma.t.sol:GovernorTimelockUpgradeTestsBasePlasma
[PASS] testFork_setUp_governorTimelockUpgradeTestsPlasma() (gas: 57594)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 232.08ms (185.67µs CPU time)

Ran 1 test for tests/protocol-upgrade/withdrawal-manager/HealthCheckers.t.sol:WithdrawalManagersUpgradeHealthCheckersTests
[PASS] testFork_withdrawalManagerUpgrade_protocolHealthChecker(uint256) (runs: 10, μ: 1541540198, ~: 1543012921)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1124.41s (1123.99s CPU time)

Ran 1 test for tests/invariants/Regression.t.sol:WithdrawalManagerQueueInvariants
[PASS] test_regression_invariants() (gas: 50709292)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 232.04ms (190.18ms CPU time)

Ran 1 test for tests/invariants/PermissionInvariants.t.sol:PermissionInvariants
[PASS] statefulFuzz_permissionManager_A_B_C() (runs: 200, calls: 50000, reverts: 0)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 303.98s (303.93s CPU time)

Ran 3 tests for tests/invariants/OpenTermInvariants.t.sol:OpenTermInvariants
[PASS] statefulFuzz_openTermLoanManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_openTermLoanManager_G() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_openTermLoan_A_B_C_D_E_F_G_H_I_openTermLoanManager_A_B_C_D_F_H_I_J_K() (runs: 200, calls: 50000, reverts: 0)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 307.99s (307.94s CPU time)

Ran 1 test for tests/invariants/StrategyInvariants.t.sol:StrategyInvariants
[PASS] statefulFuzz_strategy_A_B_C_D_E_F_G() (runs: 200, calls: 50000, reverts: 0)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1082.01s (1080.54s CPU time)

Ran 30 tests for tests/invariants/BasicInvariants.t.sol:BasicInvariants
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_F() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_G() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_H() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoanManager_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_fixedTermLoan_A_B_C_fixedTermLoanManager_L_M_N() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_poolManager_A_totalAssetsEqCashPlusAUM() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_poolManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_B_F_G_2() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_H() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_pool_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_M() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_basicInvariants_withdrawalManager_N() (runs: 200, calls: 50000, reverts: 0)
Suite result: ok. 30 passed; 0 failed; 0 skipped; finished in 1747.44s (6036.80s CPU time)

Ran 27 tests for tests/invariants/ImpairInvariants.t.sol:ImpairInvariants
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_F() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_H() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoanManager_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_fixedTermLoan_A_B_fixedTermLoanManager_L_M_N() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_poolManager_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_poolManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_B_F_G() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_pool_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_M() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_impairInvariants_withdrawalManager_N() (runs: 200, calls: 50000, reverts: 0)
Suite result: ok. 27 passed; 0 failed; 0 skipped; finished in 1747.44s (4931.19s CPU time)

Ran 25 tests for tests/invariants/WithdrawalManagerQueueInvariants.t.sol:WithdrawalManagerQueueInvariants
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_F() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_G() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_H() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoanManager_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_fixedTermLoan_A_B_C_fixedTermLoanManager_L_M_N() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_poolManager_A_totalAssetsEqCashPlusAUM() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_poolManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_B_F_G() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_H() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_pool_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_wmq_invariant_A_C_G_H() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_withdrawalManagerQueueInvariants_wmq_invariant_B_D_E_F() (runs: 200, calls: 50000, reverts: 0)
Suite result: ok. 25 passed; 0 failed; 0 skipped; finished in 3849.24s (4581.26s CPU time)

Ran 27 tests for tests/invariants/DefaultsInvariants.t.sol:DefaultsInvariants
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_F() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_H() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoanManager_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_fixedTermLoan_A_B_fixedTermLoanManager_M_N_Default() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_poolManager_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_poolManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_A() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_B_F_G() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_I() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_J() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_pool_K() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_A_F_G_H_I_J_K_L() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_B() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_C() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_D() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_E() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_M() (runs: 200, calls: 50000, reverts: 0)
[PASS] statefulFuzz_defaultsInvariants_withdrawalManager_N() (runs: 200, calls: 50000, reverts: 0)
Suite result: ok. 27 passed; 0 failed; 0 skipped; finished in 3849.24s (6318.06s CPU time)

Ran 3 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintTests
[PASS] testFuzz_mint_gtBootstrapMintAmount(uint256) (runs: 10000, μ: 356386, ~: 356535)
[PASS] testFuzz_mint_ltBootstrapMintAmount(uint256) (runs: 10000, μ: 257981, ~: 258624)
[PASS] testFuzz_mint_secondDepositorGetsCorrectShares(uint256) (runs: 10000, μ: 516736, ~: 517209)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 34.31s (34.25s CPU time)

Ran 1 test for tests/integration/pool/ConfigurePool.t.sol:ConfigurePoolTests
[PASS] testFuzz_configurePool(uint256,uint256,uint256[]) (runs: 10000, μ: 2282645, ~: 1317634)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 41.93s (41.88s CPU time)

Ran 3 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositTests
[PASS] testFuzz_deposit_gtBootstrapMintAmount(uint256) (runs: 10000, μ: 353090, ~: 353242)
[PASS] testFuzz_deposit_ltBootstrapMintAmount(uint256) (runs: 10000, μ: 256254, ~: 256861)
[PASS] testFuzz_deposit_secondDepositorGetsCorrectShares(uint256) (runs: 10000, μ: 489421, ~: 489880)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 47.26s (31.62s CPU time)

Ran 3 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapDepositWithPermitTests
[PASS] testFuzz_depositWithPermit_gtBootstrapMintAmount(uint256) (runs: 10000, μ: 391979, ~: 392115)
[PASS] testFuzz_depositWithPermit_ltBootstrapMintAmount(uint256) (runs: 10000, μ: 252710, ~: 253322)
[PASS] testFuzz_depositWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 10000, μ: 563261, ~: 563734)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 49.68s (49.62s CPU time)

Ran 2 tests for tests/integration/pool/PoolAccountingViewFunctions.t.sol:AutomatedPreviewRedeemWithQueueWMTests
[PASS] testFuzz_previewRedeem_notProcessed(uint256) (runs: 10000, μ: 36957, ~: 36957)
[PASS] testFuzz_previewRedeem_processed(uint256) (runs: 10000, μ: 316836, ~: 316836)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 12.87s (12.82s CPU time)

Ran 4 tests for tests/fuzz/PoolEntryPermissionsFuzz.t.sol:PoolEntryPermissionsFuzzTests
[PASS] testFuzz_poolEntryTests_deposit(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 345947, ~: 325568)
[PASS] testFuzz_poolEntryTests_depositWithPermit(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 443871, ~: 410417)
[PASS] testFuzz_poolEntryTests_mint(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 349940, ~: 331284)
[PASS] testFuzz_poolEntryTests_mintWithPermit(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 448864, ~: 416409)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 40.46s (40.41s CPU time)

Ran 1 test for tests/integration/pool/PoolAccountingViewFunctions.t.sol:PreviewWithdrawWithQueueWMTests
[PASS] testFuzz_previewWithdraw(address,bool,uint256,uint256,uint256) (runs: 10000, μ: 696326, ~: 688009)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 20.04s (19.99s CPU time)

Ran 3 tests for tests/integration/permission-manager/SetPoolPermissionLevel.t.sol:SetPoolPermissionLevelTests
[PASS] testFuzz_setPoolPermissionLevel(uint256,uint256) (runs: 10000, μ: 110099, ~: 111725)
[PASS] testFuzz_setPoolPermissionLevel_invalidLevel(uint256) (runs: 10000, μ: 47425, ~: 47401)
[PASS] testFuzz_setPoolPermissionLevel_publicPool(uint256) (runs: 10000, μ: 94761, ~: 94916)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 6.81s (6.76s CPU time)

Ran 5 tests for tests/fuzz/PoolExitPermissionsFuzz.t.sol:PoolExitPermissionsFuzzTests
[PASS] testFuzz_poolExit_redeem(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 728681, ~: 578010)
[PASS] testFuzz_poolExit_removeShares(uint256,uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 663393, ~: 518966)
[PASS] testFuzz_poolExit_requestRedeem(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 531396, ~: 378327)
[PASS] testFuzz_poolExit_requestWithdraw(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 449084, ~: 378481)
[PASS] testFuzz_poolExit_withdraw(uint256,uint256,uint256,uint256,bool) (runs: 10000, μ: 439608, ~: 381174)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 57.19s (57.14s CPU time)

Ran 2 tests for tests/fuzz/PoolTransferPermissionsFuzz.t.sol:PoolTransferPermissionsFuzzTests
[PASS] testFuzz_poolTransfer(uint256,uint256,uint256,uint256,uint256,bool,bool) (runs: 10000, μ: 459364, ~: 419610)
[PASS] testFuzz_poolTransferFrom(uint256,uint256,uint256,uint256,uint256,bool,bool) (runs: 10000, μ: 466800, ~: 422450)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 20.19s (20.14s CPU time)

Ran 1 test for tests/fuzz/ProcessExit.t.sol:ProcessExitFuzzTests
[PASS] testFuzz_processExit(address[10],bool[10],uint256[10],uint256) (runs: 10000, μ: 4434007, ~: 4334137)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 145.37s (145.32s CPU time)

Ran 15 tests for tests/fuzz/PoolViewFunctionsFuzzTest.t.sol:PoolViewFunctionsFuzzTests
[PASS] testFuzz_convertToAssets_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 10000, μ: 388772, ~: 389130)
[PASS] testFuzz_convertToAssets_whenTotalSupplyIsZero(uint256) (runs: 10000, μ: 14521, ~: 13922)
[PASS] testFuzz_convertToExitShares(uint256,uint256,uint256,uint256,uint256) (runs: 10000, μ: 420797, ~: 420540)
[PASS] testFuzz_convertToShares_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 10000, μ: 388765, ~: 389171)
[PASS] testFuzz_convertToShares_whenTotalSupplyIsZero(uint256) (runs: 10000, μ: 14465, ~: 13875)
[PASS] testFuzz_getTotalAssetsFromPM(uint256,uint256) (runs: 10000, μ: 122056, ~: 122352)
[PASS] testFuzz_getUnrealizedLossesFromPM(uint256) (runs: 10000, μ: 106919, ~: 106309)
[PASS] testFuzz_maxDeposit(uint256,uint256) (runs: 10000, μ: 345753, ~: 345873)
[PASS] testFuzz_maxMint(uint256,uint256) (runs: 10000, μ: 354373, ~: 354518)
[PASS] testFuzz_maxRedeem(uint256) (runs: 10000, μ: 796028, ~: 795580)
[PASS] testFuzz_maxWithdraw(uint256) (runs: 10000, μ: 573604, ~: 572997)
[PASS] testFuzz_previewDeposit_whenTotalSupplyExists(uint256,uint256) (runs: 10000, μ: 340074, ~: 340384)
[PASS] testFuzz_previewDeposit_whenTotalSupplyIsZero(uint256) (runs: 10000, μ: 14529, ~: 13936)
[PASS] testFuzz_previewMint_whenTotalSupplyExists(uint256,uint256,uint256,uint256) (runs: 10000, μ: 389727, ~: 390107)
[PASS] testFuzz_previewMint_whenTotalSupplyIsZero(uint256) (runs: 10000, μ: 14531, ~: 13940)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 51.50s (113.48s CPU time)

Ran 2 tests for tests/fuzz/Impair.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_impair_otl(uint256) (runs: 10000, μ: 11736576, ~: 11750198)
[PASS] testFuzz_removeImpairment_otl(uint256) (runs: 10000, μ: 11140868, ~: 11120730)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 388.39s (698.84s CPU time)

Ran 2 tests for tests/fuzz/Call.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_call_otl(uint256) (runs: 10000, μ: 11643120, ~: 11655327)
[PASS] testFuzz_removeCall_otl(uint256) (runs: 10000, μ: 11140281, ~: 11123466)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 425.64s (725.96s CPU time)

Ran 2 tests for tests/fuzz/OpenTermFuzz.t.sol:OpenTermLoanFuzz
[PASS] testFuzz_otlFuzzedSetup_makePayment(uint256) (runs: 10000, μ: 10369417, ~: 10362728)
[PASS] testFuzz_otlFuzzedSetup_triggerDefault(uint256) (runs: 10000, μ: 10284094, ~: 10278618)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 449.40s (631.13s CPU time)

Ran 3 tests for tests/integration/pool/BootstrapMintAndDeposit.t.sol:BootstrapMintWithPermitTests
[PASS] testFuzz_mintWithPermit_gtBootstrapMintAmount(uint256) (runs: 10000, μ: 395662, ~: 395799)
[PASS] testFuzz_mintWithPermit_ltBootstrapMintAmount(uint256) (runs: 10000, μ: 254710, ~: 255320)
[PASS] testFuzz_mintWithPermit_secondDepositorGetsCorrectShares(uint256) (runs: 10000, μ: 591118, ~: 591604)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 598.61s (52.26s CPU time)

Ran 11 tests for tests/fuzz/HasPermission.t.sol:HasPermissionFuzzTests
[PASS] testFuzz_hasPermission_deposit(uint256,uint256,uint256,bool,uint256) (runs: 10000, μ: 393323, ~: 422047)
[PASS] testFuzz_hasPermission_depositWithPermit(uint256,uint256,uint256,bool,uint256) (runs: 10000, μ: 417749, ~: 464755)
[PASS] testFuzz_hasPermission_mint(uint256,uint256,uint256,bool,uint256) (runs: 10000, μ: 396224, ~: 423809)
[PASS] testFuzz_hasPermission_mintWithPermit(uint256,uint256,uint256,bool,uint256) (runs: 10000, μ: 419275, ~: 466752)
[PASS] testFuzz_hasPermission_redeem(uint256,uint256,uint256,bool,uint256,address) (runs: 10000, μ: 784395, ~: 801158)
[PASS] testFuzz_hasPermission_removeShares(uint256,uint256,uint256,bool,uint256,uint256) (runs: 10000, μ: 782964, ~: 797601)
[PASS] testFuzz_hasPermission_requestRedeem(uint256,uint256,uint256,bool,uint256) (runs: 10000, μ: 585829, ~: 636849)
[PASS] testFuzz_hasPermission_requestWithdraw(uint256,uint256,uint256,bool,uint256) (runs: 10000, μ: 344769, ~: 367293)
[PASS] testFuzz_hasPermission_transfer(uint256,uint256,address,uint256,bool,address,uint256,bool,uint256) (runs: 10000, μ: 557645, ~: 560828)
[PASS] testFuzz_hasPermission_transferFrom(uint256,uint256,address,uint256,bool,address,uint256,bool,address,uint256) (runs: 10000, μ: 577914, ~: 577530)
[PASS] testFuzz_hasPermission_withdraw(uint256,uint256,uint256,bool,uint256,address) (runs: 10000, μ: 303590, ~: 302612)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 598.61s (182.57s CPU time)

Ran 1 test for tests/fuzz/ClosePoolFuzz.t.sol:ClosePoolFuzzWithWMQueue
[PASS] testFuzz_fuzzedSetup_closePool_withQueueWM(uint256) (runs: 10000, μ: 23132541, ~: 22941700)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 867.05s (866.98s CPU time)

Ran 1 test for tests/fuzz/ClosePoolFuzz.t.sol:ClosePoolFuzz
[PASS] testFuzz_fuzzedSetup_closePool(uint256) (runs: 10000, μ: 21782887, ~: 21567148)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 875.86s (875.80s CPU time)

Ran 3 tests for tests/e2e/PoolScenarios.t.sol:PoolScenarioTests
[PASS] testFuzz_poolScenarios_OTLWithBigPaymentInterval(uint256) (runs: 10000, μ: 1055410, ~: 1055975)
[PASS] testFuzz_poolScenarios_exposeAccountedInterestDust(uint24,uint24) (runs: 10000, μ: 1789682, ~: 1793862)
[PASS] testFuzz_poolScenarios_multipleOTLWithBigPaymentInterval(uint256,uint256,uint256) (runs: 10000, μ: 38843496, ~: 38843638)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 991.59s (1005.52s CPU time)

Ran 16 tests for tests/e2e/DelayedWithdrawal.t.sol:DelayedWithdrawalStartTests
[PASS] testFuzz_removeShares_afterStart(uint256) (runs: 10000, μ: 6864483, ~: 6864535)
[PASS] testFuzz_removeShares_beforeStart(uint256) (runs: 10000, μ: 6921347, ~: 6921396)
[PASS] testFuzz_removeShares_nextCycle(uint256) (runs: 10000, μ: 6864504, ~: 6864559)
[PASS] testFuzz_removeShares_onStart(uint256) (runs: 10000, μ: 6892372, ~: 6892423)
[PASS] testFuzz_requestRedeem_afterStart(uint256) (runs: 10000, μ: 6869180, ~: 6869230)
[PASS] testFuzz_requestRedeem_beforeStart(uint256) (runs: 10000, μ: 6928972, ~: 6929022)
[PASS] testFuzz_requestRedeem_nextCycle(uint256) (runs: 10000, μ: 6869264, ~: 6869317)
[PASS] testFuzz_requestRedeem_onStart(uint256) (runs: 10000, μ: 6898553, ~: 6898606)
[PASS] testFuzz_requestWithdraw_afterStart(uint256) (runs: 10000, μ: 6747423, ~: 6747475)
[PASS] testFuzz_requestWithdraw_beforeStart(uint256) (runs: 10000, μ: 6747509, ~: 6747558)
[PASS] testFuzz_requestWithdraw_nextCycle(uint256) (runs: 10000, μ: 6747465, ~: 6747520)
[PASS] testFuzz_requestWithdraw_onStart(uint256) (runs: 10000, μ: 6747319, ~: 6747370)
[PASS] testFuzz_setExitConfig_afterStart(uint256) (runs: 10000, μ: 6741488, ~: 6741541)
[PASS] testFuzz_setExitConfig_beforeStart(uint256) (runs: 10000, μ: 6740882, ~: 6740934)
[PASS] testFuzz_setExitConfig_nextCycle(uint256) (runs: 10000, μ: 6741509, ~: 6741561)
[PASS] testFuzz_setExitConfig_onStart(uint256) (runs: 10000, μ: 6740763, ~: 6740813)
Suite result: ok. 16 passed; 0 failed; 0 skipped; finished in 1132.57s (738.81s CPU time)

Ran 3 tests for tests/e2e/RefinanceScenario.t.sol:RefinanceScenariosTests
[PASS] test_impairOTL_refinanceToHigherPrincipal_oneLoanImpaired_underflow() (gas: 1094708)
[PASS] test_impairOTL_refinanceToHigherPrincipal_twoLoansImpaired() (gas: 1238709)
[PASS] test_impairOTL_refinanceToLowerPrincipal_singleLoanImpaired() (gas: 1144930)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 32.23ms (11.97ms CPU time)

Ran 1 test for tests/e2e/GlobalPermission.t.sol:GlobalPermissionTests
[PASS] test_e2e_globalPermission() (gas: 1853739)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 45.02ms (6.17ms CPU time)

Ran 1 test for tests/e2e/PoolLifecycle.t.sol:PoolLifecycleTest
[PASS] test_poolLifecycle() (gas: 8558288)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 51.90ms (17.81ms CPU time)

Ran 1 test for tests/e2e/MultiLoanManager.t.sol:MultiLoanManagerTests
[PASS] test_4loans_3lps() (gas: 6303154)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 60.79ms (23.37ms CPU time)

Ran 4 tests for tests/e2e/StrategyScenarios.t.sol:StrategyScenarios
[PASS] testFork_strategy_scenario1() (gas: 2231688)
[PASS] testFork_strategy_scenario2() (gas: 2143745)
[PASS] testFork_strategy_scenario3() (gas: 1983648)
[PASS] testFork_strategy_scenario4() (gas: 2099231)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 210.45ms (47.74ms CPU time)

Ran 7 tests for tests/e2e/WithdrawManagerScenario.t.sol:WithdrawalManagerScenarioTests
[PASS] test_scenario_fundPayAndRefinanceLoanWithPartialRedemptions_removeSharesAndCloseLoan() (gas: 3279489)
[PASS] test_scenario_impairLoanAndRedeem_defaultLoanAndWithdraw() (gas: 2315488)
[PASS] test_scenario_impairLoanAndRedeem_removeImpairAndRedeem() (gas: 2461182)
[PASS] test_scenario_impairLoanAndRedeem_removeSharesRepayLoanAndRedeem() (gas: 2318170)
[PASS] test_scenario_impairLoanAndRedeem_repayLoanAndWithdraw() (gas: 2406289)
[PASS] test_scenario_impairLoanAndRedeem_startLiquidationAndRedeem_finishLiquidationAndRedeem() (gas: 3480817)
[PASS] test_scenario_multipleUsers_impairLoanAndRedeem_repayLoanAndRedeem() (gas: 18922233)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 449.32ms (142.97ms CPU time)

Ran 3 tests for tests/e2e/CoreStrategyLoop.t.sol:CoreStrategyLoopTests
[PASS] test_coreStrategyLoop_v1() (gas: 7286411)
[PASS] test_coreStrategyLoop_v2() (gas: 8407155)
[PASS] test_coreStrategyLoop_v3() (gas: 8481559)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 471.32ms (361.46ms CPU time)

Ran 16 tests for tests/e2e/DelayedWithdrawal.t.sol:DelayedWithdrawalStartTests
[PASS] testFuzz_removeShares_afterStart(uint256) (runs: 100, μ: 4723262, ~: 4723281)
[PASS] testFuzz_removeShares_beforeStart(uint256) (runs: 100, μ: 4762927, ~: 4762935)
[PASS] testFuzz_removeShares_nextCycle(uint256) (runs: 100, μ: 4723258, ~: 4723294)
[PASS] testFuzz_removeShares_onStart(uint256) (runs: 100, μ: 4742744, ~: 4742779)
[PASS] testFuzz_requestRedeem_afterStart(uint256) (runs: 100, μ: 4716233, ~: 4716269)
[PASS] testFuzz_requestRedeem_beforeStart(uint256) (runs: 100, μ: 4756995, ~: 4757020)
[PASS] testFuzz_requestRedeem_nextCycle(uint256) (runs: 100, μ: 4716327, ~: 4716356)
[PASS] testFuzz_requestRedeem_onStart(uint256) (runs: 100, μ: 4736268, ~: 4736305)
[PASS] testFuzz_requestWithdraw_afterStart(uint256) (runs: 100, μ: 4634808, ~: 4634847)
[PASS] testFuzz_requestWithdraw_beforeStart(uint256) (runs: 100, μ: 4634930, ~: 4634948)
[PASS] testFuzz_requestWithdraw_nextCycle(uint256) (runs: 100, μ: 4634873, ~: 4634892)
[PASS] testFuzz_requestWithdraw_onStart(uint256) (runs: 100, μ: 4634820, ~: 4634852)
[PASS] testFuzz_setExitConfig_afterStart(uint256) (runs: 100, μ: 4642081, ~: 4642103)
[PASS] testFuzz_setExitConfig_beforeStart(uint256) (runs: 100, μ: 4641818, ~: 4641850)
[PASS] testFuzz_setExitConfig_nextCycle(uint256) (runs: 100, μ: 4642101, ~: 4642123)
[PASS] testFuzz_setExitConfig_onStart(uint256) (runs: 100, μ: 4641802, ~: 4641832)
Suite result: ok. 16 passed; 0 failed; 0 skipped; finished in 660.15ms (4.92s CPU time)

Ran 11 tests for tests/e2e/PoolScenarios.t.sol:PoolScenarioTests
[PASS] testFuzz_poolScenarios_OTLWithBigPaymentInterval(uint256) (runs: 100, μ: 956962, ~: 957169)
[PASS] testFuzz_poolScenarios_exposeAccountedInterestDust(uint24,uint24) (runs: 100, μ: 1586096, ~: 1589503)
[PASS] testFuzz_poolScenarios_multipleOTLWithBigPaymentInterval(uint256,uint256,uint256) (runs: 100, μ: 33687284, ~: 33687351)
[PASS] test_poolScenario_fundLoanAndNeverTouchIt() (gas: 5284738)
[PASS] test_poolScenario_impairLoanWithLatePaymentAndRefinance() (gas: 2316760)
[PASS] test_poolScenario_loanWithVeryHighInterestRate() (gas: 1491396)
[PASS] test_poolScenario_loanWithZeroInterestRate() (gas: 1925084)
[PASS] test_poolScenario_loanWithZeroInterestRateAndDefaultWithCover() (gas: 1478768)
[PASS] test_poolScenarios_refinanceATwoPeriodsLateLoan() (gas: 2013405)
[PASS] test_poolScenarios_refinanceLateLoanAndDefault() (gas: 1834749)
[PASS] test_poolScenarios_stressTestAdvanceGlobalPaymentAccounting() (gas: 157641795)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 6.85s (7.47s CPU time)

## erc20

Ran 14 tests for contracts/test/ERC20.t.sol:ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 86129, ~: 86370)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 257337, ~: 257338)
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
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 861.14ms (1.01s CPU time)

[PASS] invariant_balanceSum() (runs: 256, calls: 128000, reverts: 78071)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 5.45s (5.45s CPU time)

Ran 14 tests for contracts/test/ERC20.t.sol:ERC20BaseTest
[PASS] invariant_metadata() (runs: 256, calls: 128000, reverts: 80096)
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 31480, ~: 31714)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 28293, ~: 419)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 35445, ~: 35448)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 37721, ~: 38339)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 38358, ~: 38358)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 761536, ~: 758616)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 53684, ~: 54306)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 60785, ~: 61407)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 352036, ~: 354380)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 354580, ~: 355204)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 341538, ~: 341400)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 323324, ~: 323048)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 333330, ~: 333331)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 6.86s (7.37s CPU time)

Ran 3 test suites in 6.86s (13.17s CPU time): 29 tests passed, 0 failed, 0 skipped (29 total tests)


## fixed-term-loan

Ran 3 tests for tests/MapleLoan.t.sol:MapleLoanRoleTests
[PASS] test_transferBorrowerRole() (gas: 206772)
[PASS] test_transferBorrowerRole_failIfInvalidBorrower() (gas: 80439)
[PASS] test_transferLenderRole() (gas: 315711)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 5.37ms (2.14ms CPU time)

Ran 2 tests for tests/InitializerAndMigrator.t.sol:MapleLoanInitializerAndMigratorTests
[PASS] test_initializer_setters() (gas: 97720)
[PASS] test_migration_ratesChange() (gas: 116214)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 5.69ms (1.10ms CPU time)

Ran 4 tests for tests/MapleLoanFeeManager.t.sol:PayOriginationFeesTests
[PASS] test_payOriginationFees() (gas: 328032)
[PASS] test_payOriginationFees_insufficientFunds_poolDelegate() (gas: 182426)
[PASS] test_payOriginationFees_insufficientFunds_treasury() (gas: 214342)
[PASS] test_payOriginationFees_zeroTreasury() (gas: 214892)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 6.57ms (2.68ms CPU time)

[PASS] test_updatePlatformServiceFee() (gas: 1848617)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 8.84ms (6.13ms CPU time)

Ran 5 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_AcceptLoanTerms
[PASS] test_acceptLoanTerms_failIfAlreadyAccepted() (gas: 53492)
[PASS] test_acceptLoanTerms_failIfNotBorrowerOrBorrowerActions() (gas: 33868)
[PASS] test_acceptLoanTerms_failIfPaused() (gas: 34044)
[PASS] test_acceptLoanTerms_successWithBorrower() (gas: 56671)
[PASS] test_acceptLoanTerms_successWithBorrowerActions() (gas: 59202)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.76ms (691.01µs CPU time)

Ran 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_AcceptNewTermsTests
[PASS] test_acceptNewTerms() (gas: 173170)
[PASS] test_acceptNewTerms_afterDeadline() (gas: 85344)
[PASS] test_acceptNewTerms_callFailed() (gas: 126248)
[PASS] test_acceptNewTerms_commitmentMismatch_emptyCallsArray() (gas: 80650)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedCalls() (gas: 82191)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 81994)
[PASS] test_acceptNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 81709)
[PASS] test_acceptNewTerms_insufficientCollateral() (gas: 349771)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 82183)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 7.87ms (4.36ms CPU time)

[PASS] test_updateDelegateFeeTerms() (gas: 109727)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 7.81ms (438.83µs CPU time)

Ran 2 tests for tests/MapleLoanFeeManager.t.sol:PayServiceFeesTests
[PASS] test_payServiceFees() (gas: 275511)
[PASS] test_payServiceFees_zeroTreasury() (gas: 233683)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 20.36ms (5.23ms CPU time)

Ran 2 tests for tests/MapleLoanFeeManager.t.sol:GetterTests
[PASS] test_getDelegateServiceFeesForPeriod() (gas: 717302)
[PASS] test_getPlatformServiceFeeForPeriod() (gas: 1059368)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 7.45ms (4.28ms CPU time)

[PASS] test_payClosingServiceFees() (gas: 276208)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 9.01ms (3.94ms CPU time)

Ran 77 tests for tests/MapleLoan.t.sol:MapleLoanTests
[PASS] test_acceptBorrower_acl() (gas: 54102)
[PASS] test_acceptBorrower_failWhenPaused() (gas: 31214)
[PASS] test_acceptLender_acl() (gas: 52406)
[PASS] test_acceptLender_failWhenPaused() (gas: 31279)
[PASS] test_acceptNewTerms() (gas: 1615477)
[PASS] test_acceptNewTerms_acl() (gas: 1565477)
[PASS] test_acceptNewTerms_failWhenPaused() (gas: 33139)
[PASS] test_closeLoan_failWhenPaused() (gas: 32336)
[PASS] test_closeLoan_pullPatternAsBorrower() (gas: 1536630)
[PASS] test_closeLoan_pullPatternAsNonBorrower() (gas: 1539264)
[PASS] test_closeLoan_pullPatternUsingDrawable() (gas: 1552379)
[PASS] test_closeLoan_pushPatternAsBorrower() (gas: 1554175)
[PASS] test_closeLoan_pushPatternAsNonBorrower() (gas: 1554831)
[PASS] test_closeLoan_pushPatternUsingDrawable() (gas: 1519633)
[PASS] test_drawdownFunds_acl_asBorrower() (gas: 1482857)
[PASS] test_drawdownFunds_acl_asBorrowerActions() (gas: 1488669)
[PASS] test_drawdownFunds_failWhenPaused() (gas: 32506)
[PASS] test_drawdownFunds_pullPatternForCollateral() (gas: 2937756)
[PASS] test_drawdownFunds_pushPatternForCollateral() (gas: 2916501)
[PASS] test_drawdownFunds_withoutAdditionalCollateralRequired() (gas: 2748657)
[PASS] test_excessCollateral_varyCollateral() (gas: 147809)
[PASS] test_excessCollateral_varyDrawableFunds() (gas: 131676)
[PASS] test_excessCollateral_varyPrincipal() (gas: 94632)
[PASS] test_fundLoan_failWhenPaused() (gas: 31530)
[PASS] test_fundLoan_pushPattern() (gas: 1660577)
[PASS] test_getAdditionalCollateralRequiredFor_varyAmount() (gas: 134521)
[PASS] test_getAdditionalCollateralRequiredFor_varyCollateralRequired() (gas: 118958)
[PASS] test_getAdditionalCollateralRequiredFor_varyDrawableFunds() (gas: 121514)
[PASS] test_getAdditionalCollateralRequiredFor_varyPrincipal() (gas: 142693)
[PASS] test_impairLoan() (gas: 82040)
[PASS] test_impairLoan_acl() (gas: 94676)
[PASS] test_impairLoan_failWhenPaused() (gas: 31275)
[PASS] test_impairLoan_lateLoan() (gas: 82227)
[PASS] test_makePayment_failWhenPaused() (gas: 32402)
[PASS] test_makePayment_pullPatternAsBorrower() (gas: 1599267)
[PASS] test_makePayment_pullPatternAsNonBorrower() (gas: 1601609)
[PASS] test_makePayment_pullPatternUsingDrawable() (gas: 1643775)
[PASS] test_makePayment_pushPatternAsBorrower() (gas: 1605283)
[PASS] test_makePayment_pushPatternAsNonBorrower() (gas: 1605645)
[PASS] test_makePayment_pushPatternUsingDrawable() (gas: 1611135)
[PASS] test_migrate_acl() (gas: 90384)
[PASS] test_migrate_failWhenPaused() (gas: 32432)
[PASS] test_postCollateral_failWhenPaused() (gas: 31964)
[PASS] test_postCollateral_pullPattern() (gas: 1450394)
[PASS] test_postCollateral_pushPattern() (gas: 1399988)
[PASS] test_proposeNewTerms() (gas: 121002)
[PASS] test_proposeNewTerms_acl_asBorrower() (gas: 138122)
[PASS] test_proposeNewTerms_acl_asBorrowerActions() (gas: 138648)
[PASS] test_proposeNewTerms_failWhenPaused() (gas: 33053)
[PASS] test_proposeNewTerms_invalidDeadline() (gas: 132551)
[PASS] test_rejectNewTerms_acl() (gas: 197404)
[PASS] test_rejectNewTerms_failWhenPaused() (gas: 33162)
[PASS] test_removeCollateral_acl_asBorrower() (gas: 1441281)
[PASS] test_removeCollateral_acl_asBorrowerActions() (gas: 1447226)
[PASS] test_removeCollateral_failWhenPaused() (gas: 32167)
[PASS] test_removeLoanImpairment_acl() (gas: 75813)
[PASS] test_removeLoanImpairment_failWhenPaused() (gas: 31365)
[PASS] test_removeLoanImpairment_notImpaired() (gas: 32232)
[PASS] test_removeLoanImpairment_pastDate() (gas: 54479)
[PASS] test_removeLoanImpairment_success() (gas: 61130)
[PASS] test_repossess_acl() (gas: 1418198)
[PASS] test_repossess_failWhenPaused() (gas: 32369)
[PASS] test_returnFunds_failWhenPaused() (gas: 32052)
[PASS] test_returnFunds_pullPattern() (gas: 1450503)
[PASS] test_returnFunds_pushPattern() (gas: 1400010)
[PASS] test_setImplementation_acl() (gas: 110497)
[PASS] test_setImplementation_failWhenPaused() (gas: 31853)
[PASS] test_setPendingBorrower_acl_asBorrower() (gas: 102548)
[PASS] test_setPendingBorrower_acl_asBorrowerActions() (gas: 106470)
[PASS] test_setPendingBorrower_failWhenPaused() (gas: 31744)
[PASS] test_setPendingLender_acl() (gas: 73701)
[PASS] test_setPendingLender_failWhenPaused() (gas: 31789)
[PASS] test_skim_failWhenPaused() (gas: 32387)
[PASS] test_upgrade_acl_noAuth() (gas: 6588831)
[PASS] test_upgrade_acl_noAuth_asBorrower() (gas: 6591643)
[PASS] test_upgrade_acl_securityAdmin() (gas: 6623456)
[PASS] test_upgrade_failWhenPaused() (gas: 32122)
Suite result: ok. 77 passed; 0 failed; 0 skipped; finished in 42.06ms (43.23ms CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CollateralMaintainedTests
[PASS] test_isCollateralMaintained(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 125134, ~: 125743)
[PASS] test_isCollateralMaintained_edgeCases() (gas: 194733)
[PASS] test_isCollateralMaintained_roundUp() (gas: 85461)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 88.45ms (87.47ms CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ProposeNewTermsTests
[PASS] test_proposeNewTerms(address,uint256,uint256,uint256,uint256) (runs: 256, μ: 81660, ~: 82002)
[PASS] test_proposeNewTerms_emptyArray(address,uint256) (runs: 256, μ: 38534, ~: 38876)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 83520)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 220.98ms (219.65ms CPU time)

Ran 5 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RejectNewTermsTests
[PASS] test_rejectNewTerms() (gas: 65210)
[PASS] test_rejectNewTerms_commitmentMismatch_emptyCallsArray() (gas: 75642)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedCalls() (gas: 77254)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedDeadline() (gas: 77168)
[PASS] test_rejectNewTerms_commitmentMismatch_mismatchedRefinancer() (gas: 729562)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.31ms (1.90ms CPU time)

[PASS] test_getNextPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 720082, ~: 721434)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 266.73ms (265.58ms CPU time)

Ran 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetPaymentBreakdownTests
[PASS] test_getPaymentBreakdown_onePaymentFourPeriodsLate() (gas: 38327)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodBeforeDue() (gas: 35252)
[PASS] test_getPaymentBreakdown_onePaymentOnePeriodLate() (gas: 38349)
[PASS] test_getPaymentBreakdown_onePaymentOneSecondBeforeDue() (gas: 35317)
[PASS] test_getPaymentBreakdown_onePaymentThreePeriodsLate() (gas: 38282)
[PASS] test_getPaymentBreakdown_onePaymentTwoPeriodsLate() (gas: 38304)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 2.36ms (1.41ms CPU time)

[PASS] test_getPeriodicInterestRate() (gas: 10439)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.04ms (109.04µs CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetInstallmentTests
[PASS] test_getInstallment_edgeCases() (gas: 28426)
[PASS] test_getInstallment_genericFuzzing(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 18854, ~: 19125)
[PASS] test_getInstallment_withFixtures() (gas: 14280)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 72.54ms (71.53ms CPU time)

[PASS] test_getInterest() (gas: 11818)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 964.85µs (109.24µs CPU time)

Ran 9 tests for tests/MapleLoanFactory.t.sol:MapleLoanFactoryTest
[PASS] test_createInstance(bytes32) (runs: 256, μ: 553111, ~: 553111)
[PASS] test_createInstance_differentFundsAsset() (gas: 774574)
[PASS] test_createInstance_invalidCaller() (gas: 553933)
[PASS] test_createInstance_invalidCollateralAsset() (gas: 746602)
[PASS] test_createInstance_invalidFactory() (gas: 778525)
[PASS] test_createInstance_invalidInstance() (gas: 784465)
[PASS] test_createInstance_invalidPoolAsset() (gas: 742867)
[PASS] test_createInstance_zeroLender() (gas: 770287)
[PASS] test_isLoan_withOldFactory() (gas: 1087316)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 533.07ms (526.54ms CPU time)

[PASS] test_getClosingPaymentBreakdown(uint256,uint256,uint256) (runs: 256, μ: 9020008, ~: 9020028)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 598.50ms (591.31ms CPU time)

[PASS] test_getCollateralRequiredFor() (gas: 21550)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.13ms (223.02µs CPU time)

Ran 3 tests for tests/MapleLoanScenarios.t.sol:MapleLoanScenariosTests
[PASS] test_scenario_fullyAmortized() (gas: 9545692)
[PASS] test_scenario_interestOnly() (gas: 9530408)
[PASS] test_scenario_lateLoanRefinanceInterest() (gas: 9218314)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 38.67ms (28.55ms CPU time)

Ran 3 tests for tests/MapleLoanV502Migrator.t.sol:MapleLoanV502MigratorTests
[PASS] test_migration_factoryChange() (gas: 2982041)
[PASS] test_migration_invalidFactory() (gas: 2957110)
[PASS] test_migration_sameFactory_noOp() (gas: 2947582)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 10.37ms (2.74ms CPU time)

Ran 2 tests for tests/Payments.t.sol:ClosingTests
[PASS] test_payments_closing_flatRate_case1() (gas: 1422472)
[PASS] test_payments_closing_flatRate_case2() (gas: 1277212)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 17.19ms (14.04ms CPU time)

Ran 2 tests for tests/Payments.t.sol:FullyAmortizedPaymentsTests
[PASS] test_payments_fullyAmortized_case1() (gas: 1690175)
[PASS] test_payments_fullyAmortized_case2() (gas: 1690124)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 27.42ms (24.06ms CPU time)

Ran 6 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_DrawdownFundsTests
[PASS] test_drawdownFunds_collateralNotMaintained(uint256,uint256,uint256) (runs: 256, μ: 272370, ~: 273976)
[PASS] test_drawdownFunds_insufficientDrawableFunds(uint256,uint256) (runs: 256, μ: 157630, ~: 157795)
[PASS] test_drawdownFunds_multipleDrawdowns(uint256,uint256,uint256) (runs: 256, μ: 278647, ~: 278241)
[PASS] test_drawdownFunds_postedCollateral(uint256,uint256,uint256) (runs: 256, μ: 293779, ~: 294765)
[PASS] test_drawdownFunds_transferFailed() (gas: 55653)
[PASS] test_drawdownFunds_withoutPostedCollateral(uint256,uint256) (runs: 256, μ: 198354, ~: 199201)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 822.37ms (820.45ms CPU time)

Ran 2 tests for tests/Payments.t.sol:InterestOnlyPaymentsTests
[PASS] test_payments_interestOnly_case1() (gas: 1705799)
[PASS] test_payments_interestOnly_case2() (gas: 1706053)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 28.65ms (25.20ms CPU time)

Ran 3 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_SkimTests
[PASS] test_skimCollateralAsset() (gas: 84661)
[PASS] test_skimFundsAsset() (gas: 84683)
[PASS] test_skim_otherAsset() (gas: 1367889)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 7.42ms (1.21ms CPU time)

[PASS] test_refinance_invalidRefinancer() (gas: 9183149)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 5.65ms (3.01ms CPU time)

Ran 5 tests for tests/Payments.t.sol:LateRepaymentsTests
[PASS] test_payments_dailyInterestAccrual() (gas: 1067402)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case1() (gas: 1695211)
[PASS] test_payments_lateRepayment_flatRateAndDefaultRate_case2() (gas: 1704178)
[PASS] test_payments_lateRepayment_flatRate_case1() (gas: 1696594)
[PASS] test_payments_lateRepayment_flatRate_case2() (gas: 1692266)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 69.54ms (65.88ms CPU time)

Ran 2 tests for tests/Payments.t.sol:PartiallyAmortizedPaymentsTests
[PASS] test_payments_partiallyAmortized_case1() (gas: 1706028)
[PASS] test_payments_partiallyAmortized_case2() (gas: 1706061)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 39.64ms (24.54ms CPU time)

Ran 12 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_GetUnaccountedAmountTests
[PASS] test_getUnaccountedAmount_collateral(uint256,uint256) (runs: 256, μ: 90995, ~: 91305)
[PASS] test_getUnaccountedAmount_collateralAsset() (gas: 81295)
[PASS] test_getUnaccountedAmount_complex(uint256,uint256,uint256) (runs: 256, μ: 1391776, ~: 1392099)
[PASS] test_getUnaccountedAmount_drawableFunds(uint256,uint256) (runs: 256, μ: 90849, ~: 91174)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral(uint256,uint256,uint256,uint256) (runs: 256, μ: 172930, ~: 172822)
[PASS] test_getUnaccountedAmount_drawableFundsAndAndCollateral_fundsAssetEqCollateralAsset(uint256,uint256,uint256) (runs: 256, μ: 119968, ~: 120134)
[PASS] test_getUnaccountedAmount_fundsAsset() (gas: 81296)
[PASS] test_getUnaccountedAmount_newFundsLtCollateral(uint256) (runs: 256, μ: 108943, ~: 108937)
[PASS] test_getUnaccountedAmount_newFundsLtDrawableFunds(uint256) (runs: 256, μ: 108973, ~: 108967)
[PASS] test_getUnaccountedAmount_randomToken() (gas: 121430)
[PASS] test_getUnaccountedAmount_withCollateral(uint256,uint256) (runs: 256, μ: 88816, ~: 89934)
[PASS] test_getUnaccountedAmount_withDrawableFunds(uint256,uint256) (runs: 256, μ: 89170, ~: 89805)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 913.34ms (911.56ms CPU time)

Ran 9 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_InitializeTests
[PASS] test_initialize() (gas: 8994403)
[PASS] test_initialize_invalidBorrower() (gas: 2103947)
[PASS] test_initialize_invalidEndingPrincipal() (gas: 2067093)
[PASS] test_initialize_invalidGracePeriodBoundary() (gas: 10976912)
[PASS] test_initialize_invalidOriginationFeeBoundary() (gas: 10977872)
[PASS] test_initialize_invalidPaymentInterval() (gas: 2073638)
[PASS] test_initialize_invalidPaymentsRemaining() (gas: 2073628)
[PASS] test_initialize_invalidPrincipal() (gas: 2066887)
[PASS] test_initialize_zeroBorrower() (gas: 2077679)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 23.72ms (21.76ms CPU time)

Ran 11 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RemoveCollateralTests
[PASS] test_removeCollateral_cannotRemoveAnyAmountWithEncumbrances() (gas: 200434)
[PASS] test_removeCollateral_cannotRemoveFullAmountWithEncumbrances(uint256) (runs: 256, μ: 160980, ~: 160974)
[PASS] test_removeCollateral_cannotRemovePartialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 201904, ~: 202261)
[PASS] test_removeCollateral_fullAmountWithNoEncumbrances(uint256) (runs: 256, μ: 125157, ~: 125161)
[PASS] test_removeCollateral_fullAmount_drawableFundsGtPrincipal(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 191352, ~: 191925)
[PASS] test_removeCollateral_fullAmount_noPrincipal(uint256) (runs: 256, μ: 144432, ~: 144420)
[PASS] test_removeCollateral_insufficientCollateralWithNoEncumbrances(uint256) (runs: 256, μ: 120690, ~: 121623)
[PASS] test_removeCollateral_partialAmountWithEncumbrances(uint256,uint256) (runs: 256, μ: 250697, ~: 250326)
[PASS] test_removeCollateral_partialAmountWithNoEncumbrances(uint256,uint256) (runs: 256, μ: 161657, ~: 163261)
[PASS] test_removeCollateral_sameAssetAsFundingAsset(uint256) (runs: 256, μ: 149054, ~: 149042)
[PASS] test_removeCollateral_transferFailed() (gas: 295978)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 1.34s (1.33s CPU time)

Ran 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_RepossessTests
[PASS] test_repossess() (gas: 151946)
[PASS] test_repossess_beforePaymentDue() (gas: 57119)
[PASS] test_repossess_collateralTransferFailed() (gas: 310751)
[PASS] test_repossess_fundsTransferFailed() (gas: 343461)
[PASS] test_repossess_onGracePeriod() (gas: 57135)
[PASS] test_repossess_onPaymentDue() (gas: 56881)
[PASS] test_repossess_withinGracePeriod() (gas: 57090)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 5.91ms (2.05ms CPU time)

Ran 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ReturnFundsTests
[PASS] test_returnFunds(uint256) (runs: 256, μ: 129406, ~: 130551)
[PASS] test_returnFundsCollateralAsset() (gas: 1389958)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 141.74ms (140.18ms CPU time)

Ran 2 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_ScaledExponentTests
[PASS] test_scaledExponent_setOne() (gas: 40312)
[PASS] test_scaledExponent_setTwo() (gas: 71120)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.43ms (1.31ms CPU time)

[PASS] test_refinance_gracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9383458, ~: 9386113)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.25s (1.24s CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePaymentIntervalTests
[PASS] test_refinance_paymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9386937, ~: 9388376)
[PASS] test_refinance_paymentInterval_zeroAmount() (gas: 9335233)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.19s (1.19s CPU time)

[PASS] test_refinance_multipleParameters(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9452332, ~: 9449058)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.69s (1.69s CPU time)

[PASS] test_refinance_interestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9385115, ~: 9386617)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.15s (1.15s CPU time)

[PASS] test_acceptNewTerms_makePayment_withRefinanceInterest() (gas: 9444394)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 28.99ms (15.16ms CPU time)

Ran 4 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_PostCollateralTests
[PASS] test_postCollateral_invalidCollateralAsset() (gas: 1363482)
[PASS] test_postCollateral_multiple(uint256,uint256) (runs: 256, μ: 178416, ~: 182453)
[PASS] test_postCollateral_once(uint256) (runs: 256, μ: 104534, ~: 105228)
[PASS] test_postCollateral_withUnaccountedFundsAsset() (gas: 1452457)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 446.17ms (445.01ms CPU time)

Ran 8 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_MakePaymentTests
[PASS] test_makePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 390057, ~: 391499)
[PASS] test_makePayment_amountSmallerThanFees() (gas: 490322)
[PASS] test_makePayment_collateralNotMaintained() (gas: 874527)
[PASS] test_makePayment_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 417453, ~: 418668)
[PASS] test_makePayment_lastPaymentClearsLoan(uint256,uint256,uint256,uint256) (runs: 256, μ: 368044, ~: 368756)
[PASS] test_makePayment_noAmount() (gas: 480843)
[PASS] test_makePayment_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 394133, ~: 396134)
[PASS] test_makePayment_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 375270, ~: 375481)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 2.31s (2.31s CPU time)

Ran 12 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_FundLoanTests
[PASS] test_fundLoan_approveFail() (gas: 330471)
[PASS] test_fundLoan_doubleFund(uint256) (runs: 256, μ: 282110, ~: 281816)
[PASS] test_fundLoan_fullFunding(uint256) (runs: 256, μ: 304534, ~: 304213)
[PASS] test_fundLoan_fullFundingWithExistingDrawableFunds(uint256) (runs: 256, μ: 306267, ~: 305955)
[PASS] test_fundLoan_invalidFundsAsset() (gas: 1502785)
[PASS] test_fundLoan_nextPaymentDueDateAlreadySet() (gas: 178880)
[PASS] test_fundLoan_noPaymentsRemaining() (gas: 87229)
[PASS] test_fundLoan_notLender() (gas: 27441)
[PASS] test_fundLoan_partialFunding(uint256) (runs: 256, μ: 227801, ~: 227999)
[PASS] test_fundLoan_termsNotAccepted() (gas: 31918)
[PASS] test_fundLoan_withUnaccountedCollateralAsset() (gas: 1619778)
[PASS] test_fundLoan_withoutSendingAsset() (gas: 181311)
Suite result: ok. 12 passed; 0 failed; 0 skipped; finished in 2.81s (942.84ms CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePaymentsRemainingTests
[PASS] test_refinance_paymentRemaining(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9387061, ~: 9388048)
[PASS] test_refinance_paymentRemaining_zeroAmount() (gas: 9335235)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.25s (1.25s CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinancePrincipalRequestedTests
[PASS] test_refinance_increasePrincipalRequested(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9464135, ~: 9465595)
[PASS] test_refinance_increasePrincipalRequestedWithInsufficientFunds(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9399032, ~: 9399874)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.16s (3.16s CPU time)

[PASS] test_refinance_collateralRequired(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9427999, ~: 9429874)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.63s (1.63s CPU time)

Ran 2 tests for tests/MapleLoanRefinancer.t.sol:RefinanceDeadlineTests
[PASS] test_refinance_afterDeadline(uint256,uint256,uint256) (runs: 256, μ: 9335945, ~: 9334969)
[PASS] test_refinance_differentDeadline(uint256,uint256,uint256) (runs: 256, μ: 9308716, ~: 9308747)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.45s (2.65s CPU time)

Ran 3 tests for tests/MapleLoanRefinancer.t.sol:RefinanceEndingPrincipalTests
[PASS] test_refinance_endingPrincipal_amortizedToInterestOnly(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9417602, ~: 9419137)
[PASS] test_refinance_endingPrincipal_failLargerThanPrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9368668, ~: 9371329)
[PASS] test_refinance_endingPrincipal_interestOnlyToAmortized(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9411262, ~: 9416378)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.01s (3.30s CPU time)

Ran 3 tests for tests/MapleLoanRefinancer.t.sol:RefinanceFeeTests
[PASS] test_refinance_closingRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9385727, ~: 9387257)
[PASS] test_refinance_lateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9385788, ~: 9387683)
[PASS] test_refinance_lateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 9406168, ~: 9407297)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.91s (2.67s CPU time)

Ran 7 tests for tests/MapleLoanRefinancer.t.sol:RefinancingFeesTerms
[PASS] testFuzz_refinance_payOriginationFees(uint256,uint256) (runs: 256, μ: 10941438, ~: 10941451)
[PASS] testFuzz_refinance_pdOriginationFeeTransferFail(uint256) (runs: 256, μ: 10853709, ~: 10853823)
[PASS] testFuzz_refinance_treasuryOriginationFeeTransferFail(uint256,uint256) (runs: 256, μ: 10867772, ~: 10867770)
[PASS] testFuzz_refinance_updateFeeTerms(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 10892621, ~: 10894292)
[PASS] testFuzz_refinance_updatesPlatformServiceFees(uint256) (runs: 256, μ: 10851734, ~: 10852044)
[PASS] test_refinance_updateRefinanceServiceFees() (gas: 10933885)
[PASS] test_refinance_updateRefinanceServiceFeesOnDoubleRefinance() (gas: 11036939)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 4.22s (8.34s CPU time)

Ran 7 tests for tests/MapleLoanLogic.t.sol:MapleLoanLogic_CloseLoanTests
[PASS] test_closeLoan(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 296434, ~: 297091)
[PASS] test_closeLoan_amountSmallerThanFees() (gas: 465232)
[PASS] test_closeLoan_insufficientAmount(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 361903, ~: 362154)
[PASS] test_closeLoan_latePayment(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 303106, ~: 303516)
[PASS] test_closeLoan_noAmount() (gas: 457685)
[PASS] test_closeLoan_withDrawableFunds(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 304408, ~: 304472)
[PASS] test_closeLoan_withRefinanceInterest(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 297908, ~: 298225)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 5.20s (1.73s CPU time)

Ran 54 test suites in 5.22s (37.12s CPU time): 270 tests passed, 0 failed, 0 skipped (270 total tests)


## fixed-term-loan-manager

Ran 3 tests for tests/MapleLoanManager.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_notPoolDelegate() (gas: 40032)
[PASS] test_rejectNewTerms_paused() (gas: 38296)
[PASS] test_rejectNewTerms_success() (gas: 1112994)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.31ms (772.09µs CPU time)

[PASS] test_acceptNewTerms_invalidBorrower() (gas: 218426)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 4.03ms (486.13µs CPU time)

Ran 2 tests for tests/MapleLoanManager.t.sol:ClaimTests
[PASS] test_claim_notLoan() (gas: 379687)
[PASS] test_claim_paused() (gas: 42940)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 4.84ms (998.07µs CPU time)

Ran 7 tests for tests/MapleLoanManager.t.sol:FundLoanTests
[PASS] test_fund() (gas: 447263)
[PASS] test_fund_failIfNotPoolDelegate() (gas: 91335)
[PASS] test_fund_inactiveLoan() (gas: 71600)
[PASS] test_fund_invalidBorrower() (gas: 75141)
[PASS] test_fund_invalidFactory() (gas: 64138)
[PASS] test_fund_invalidLoan() (gas: 65294)
[PASS] test_fund_paused() (gas: 46859)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 5.90ms (2.97ms CPU time)

Ran 2 tests for tests/MapleLoanManager.t.sol:DistributeClaimedFunds
[PASS] test_distributeClaimedFunds_mapleTreasuryNotSet() (gas: 1406031)
[PASS] test_distributeLiquidationFunds_poolNotSet() (gas: 1342601)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.70ms (1.10ms CPU time)

Ran 13 tests for tests/MapleLoanManager.t.sol:LoanManagerSortingTests
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
Suite result: ok. 13 passed; 0 failed; 0 skipped; finished in 9.25ms (6.31ms CPU time)

Ran 2 tests for tests/MapleLoanManager.t.sol:GetterTests
[PASS] test_accruedInterest() (gas: 43560)
[PASS] test_getAssetsUnderManagement() (gas: 50797)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 4.64ms (744.46µs CPU time)

Ran 4 tests for tests/MapleLoanManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 36928)
[PASS] test_migrate_notFactory() (gas: 33474)
[PASS] test_migrate_paused() (gas: 39426)
[PASS] test_migrate_success() (gas: 43097)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.99ms (697.76µs CPU time)

Ran 3 tests for tests/MapleLoanManager.t.sol:DistributeLiquidationFundsTests
[PASS] test_distributeLiquidationFunds_borrowerNotSet() (gas: 1188764)
[PASS] test_distributeLiquidationFunds_mapleTreasuryNotSet() (gas: 1234114)
[PASS] test_distributeLiquidationFunds_poolNotSet() (gas: 1220189)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 6.96ms (4.33ms CPU time)

Ran 2 tests for tests/MapleLoanManager.t.sol:UpdateAccountingFailureTests
[PASS] test_updateAccounting_notGovernor() (gas: 103379)
[PASS] test_updateAccounting_notPoolDelegate() (gas: 100586)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.80ms (599.46µs CPU time)

Ran 7 tests for tests/MapleLoanManager.t.sol:TriggerDefaultTests
[PASS] test_triggerDefault_notManager() (gas: 144235)
[PASS] test_triggerDefault_paused() (gas: 42169)
[PASS] test_triggerDefault_success_noCollateral_impaired() (gas: 251299)
[PASS] test_triggerDefault_success_noCollateral_notImpaired() (gas: 177719)
[PASS] test_triggerDefault_success_withCollateralAssetEqualToFundsAsset() (gas: 325299)
[PASS] test_triggerDefault_success_withCollateral_impaired() (gas: 436395)
[PASS] test_triggerDefault_success_withCollateral_notImpaired() (gas: 401902)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 15.21ms (7.04ms CPU time)

Ran 5 tests for tests/MapleLoanManager.t.sol:FinishCollateralLiquidationTests
[PASS] test_finishCollateralLiquidation_callAfterTriggerDefaultOnUncollateralizedLoan() (gas: 141630)
[PASS] test_finishCollateralLiquidation_callBeforeTriggerDefault() (gas: 67166)
[PASS] test_finishCollateralLiquidation_notManager() (gas: 320152)
[PASS] test_finishCollateralLiquidation_paused() (gas: 44519)
[PASS] test_finishCollateralLiquidation_success_withCollateral() (gas: 396596)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 7.38ms (3.45ms CPU time)

Ran 7 tests for tests/MapleLoanManager.t.sol:RemoveLoanImpairmentTests
[PASS] test_removeLoanImpairment_delegateNotAuthorizedToRemoveGovernors() (gas: 280563)
[PASS] test_removeLoanImpairment_failIfPaused() (gas: 46902)
[PASS] test_removeLoanImpairment_notByGovernor() (gas: 207550)
[PASS] test_removeLoanImpairment_notPoolDelegate() (gas: 203478)
[PASS] test_removeLoanImpairment_pastDueDate() (gas: 295387)
[PASS] test_removeLoanImpairment_successWithGovernor() (gas: 324999)
[PASS] test_removeLoanImpairment_successWithPD() (gas: 324023)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 17.56ms (6.23ms CPU time)

Ran 5 tests for tests/MapleLoanManager.t.sol:ImpairLoanTests
[PASS] test_impairLoan_alreadyImpaired() (gas: 195535)
[PASS] test_impairLoan_failIfPaused() (gas: 41799)
[PASS] test_impairLoan_notAuthorized() (gas: 43512)
[PASS] test_impairLoan_success() (gas: 273187)
[PASS] test_impairLoan_success_byGovernor() (gas: 251131)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 10.62ms (7.09ms CPU time)

Ran 4 tests for tests/MapleLoanManager.t.sol:UpdateAccountingTests
[PASS] test_updateAccounting_afterDomainEnd() (gas: 130773)
[PASS] test_updateAccounting_afterTwoDomainEnds() (gas: 124597)
[PASS] test_updateAccounting_beforeDomainEnd() (gas: 111167)
[PASS] test_updateAccounting_failIfPaused() (gas: 39148)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 6.66ms (2.20ms CPU time)

Ran 5 tests for tests/MapleLoanManager.t.sol:SetAllowedSlippage_SetterTests
[PASS] test_setAllowedSlippage_invalidSlippage() (gas: 44038)
[PASS] test_setAllowedSlippage_noAuth() (gas: 43830)
[PASS] test_setAllowedSlippage_paused() (gas: 39261)
[PASS] test_setAllowedSlippage_success_asGovernor() (gas: 72085)
[PASS] test_setAllowedSlippage_success_asPoolDelegate() (gas: 72084)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.34ms (791.64µs CPU time)

Ran 6 tests for tests/MapleLoanManager.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 43689)
[PASS] test_upgrade_notScheduled() (gas: 47551)
[PASS] test_upgrade_paused() (gas: 37258)
[PASS] test_upgrade_success_asPoolDelegate() (gas: 93407)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 82459)
[PASS] test_upgrade_upgradeFailed() (gas: 88416)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 8.38ms (1.87ms CPU time)

[PASS] test_claim_domainStart_gt_domainEnd() (gas: 715050)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 30.19ms (26.34ms CPU time)

Ran 3 tests for tests/MapleLoanManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 32944)
[PASS] test_setImplementation_paused() (gas: 38941)
[PASS] test_setImplementation_success() (gas: 43909)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 9.16ms (464.47µs CPU time)

Ran 4 tests for tests/MapleLoanManager.t.sol:SetMinRatio_SetterTests
[PASS] test_setMinRatio_noAuth() (gas: 43894)
[PASS] test_setMinRatio_paused() (gas: 39304)
[PASS] test_setMinRatio_success_asGovernor() (gas: 72034)
[PASS] test_setMinRatio_success_asPoolDelegate() (gas: 69263)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.50ms (686.79µs CPU time)

Ran 4 tests for tests/MapleLoanManager.t.sol:RefinanceAccountingSingleLoanTests
[PASS] test_refinance_beforeLoanDueDate_interestOnly() (gas: 628420)
[PASS] test_refinance_onLatePayment_interestOnly() (gas: 631008)
[PASS] test_refinance_onLoanPaymentDueDate_interestOnly() (gas: 629143)
[PASS] test_refinance_onPaymentDueDate_amortized() (gas: 629932)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 23.16ms (15.99ms CPU time)

Ran 6 tests for tests/MapleLoanManager.t.sol:UintCastingTests
[PASS] test_castUint112() (gas: 24508)
[PASS] test_castUint120() (gas: 24427)
[PASS] test_castUint128() (gas: 24487)
[PASS] test_castUint24() (gas: 24402)
[PASS] test_castUint48() (gas: 24445)
[PASS] test_castUint96() (gas: 24448)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 17.70ms (775.46µs CPU time)

Ran 3 tests for tests/MapleLoanManager.t.sol:TwoLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_interestOnly_onTimePayment_interestOnly() (gas: 710747)
[PASS] test_claim_latePayment_interestOnly_onTimePayment_interestOnly() (gas: 734866)
[PASS] test_claim_onTimePayment_interestOnly_onTimePayment_interestOnly() (gas: 707930)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 26.91ms (12.26ms CPU time)

Ran 6 tests for tests/MapleLoanManager.t.sol:SingleLoanAtomicClaimTests
[PASS] test_claim_earlyPayment_amortized() (gas: 447371)
[PASS] test_claim_earlyPayment_interestOnly() (gas: 439922)
[PASS] test_claim_latePayment_amortized() (gas: 470153)
[PASS] test_claim_latePayment_interestOnly() (gas: 462702)
[PASS] test_claim_onTimePayment_amortized() (gas: 444599)
[PASS] test_claim_onTimePayment_interestOnly() (gas: 437216)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 15.73ms (12.63ms CPU time)

Ran 2 tests for tests/MapleLoanManager.t.sol:ThreeLoanPastDomainEndClaimTests
[PASS] test_claim_loan1NotPaid_loan2NotPaid_loan3PaidLate() (gas: 411235)
[PASS] test_claim_loan3_loan1NotPaid_loan2NotPaid() (gas: 408747)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 15.25ms (5.42ms CPU time)

Ran 2 tests for tests/MapleLoanManager.t.sol:QueueNextPaymentTests
[PASS] testFuzz_queueNextPayment_fees(uint256,uint256) (runs: 256, μ: 214795, ~: 223454)
[PASS] test_queueNextPayment_fees() (gas: 182906)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 114.89ms (112.69ms CPU time)

[PASS] testFuzz_claim_latePayment_interestOnly(uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 1854099, ~: 1858350)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 416.77ms (410.22ms CPU time)

Ran 28 test suites in 440.91ms (795.37ms CPU time): 110 tests passed, 1 failed, 0 skipped (111 total tests)

## globals

Ran 3 tests for tests/GovernorTimelock/AcceptTokenWithdrawer.t.sol:AcceptTokenWithdrawerTests
[PASS] test_acceptTokenWithdrawer_revert_notPendingTokenWithdrawer() (gas: 40612)
[PASS] test_acceptTokenWithdrawer_success() (gas: 35529)
[PASS] test_deployment() (gas: 45168)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.38ms (430.40µs CPU time)

[PASS] test_deployment() (gas: 45145)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 1.66ms (300.18µs CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:TransferGovernorTests
[PASS] test_acceptGovernor() (gas: 51092)
[PASS] test_acceptGovernor_notPendingGovernor() (gas: 16293)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.78ms (456.96µs CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:SetPlatformOriginationFeeRateTests
[PASS] test_setPlatformOriginationFeeRate_notAuthorized() (gas: 57711)
[PASS] test_setPlatformOriginationFeeRate_outOfBounds() (gas: 55567)
[PASS] test_setPlatformOriginationFeeRate_success_governor() (gas: 50507)
[PASS] test_setPlatformOriginationFeeRate_success_operational_admin() (gas: 79708)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.22ms (704.02µs CPU time)

Ran 5 tests for tests/GovernorTimelock/SetDefaultTimelockParameters.t.sol:SetDefaultTimelockParametersTests
[PASS] test_deployment() (gas: 45168)
[PASS] test_setDefaultTimelockParameters_revert_invalidDelay() (gas: 12452)
[PASS] test_setDefaultTimelockParameters_revert_invalidExecutionWindow() (gas: 12468)
[PASS] test_setDefaultTimelockParameters_revert_notSelf() (gas: 9787)
[PASS] test_setDefaultTimelockParameters_success() (gas: 21926)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 2.22ms (796.29µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetValidBorrowerTests
[PASS] test_setValidBorrower_notAuthorized() (gas: 57407)
[PASS] test_setValidBorrower_success_governor() (gas: 42256)
[PASS] test_setValidBorrower_success_operationalAdmin() (gas: 79758)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.47ms (305.47µs CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:SetValidCollateralTests
[PASS] test_setValidCollateral() (gas: 42197)
[PASS] test_setValidCollateral_notGovernor() (gas: 55240)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.46ms (322.45µs CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:SetPlatformServiceFeeRateTests
[PASS] test_setPlatformServiceFeeRate_notAuthorized() (gas: 57577)
[PASS] test_setPlatformServiceFeeRate_outOfBounds() (gas: 55432)
[PASS] test_setPlatformServiceFeeRate_success_governor() (gas: 50529)
[PASS] test_setPlatformServiceFeeRate_success_operationalAdmin() (gas: 79730)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.06ms (572.90µs CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:TransferOwnedPoolTests
[PASS] test_transferOwnedPool() (gas: 74382)
[PASS] test_transferOwnedPool_alreadyOwns() (gas: 286162)
[PASS] test_transferOwnedPool_notPoolDelegate() (gas: 26491)
[PASS] test_transferOwnedPool_notPoolManager() (gas: 21659)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.75ms (720.00µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetCanDeployFromTests
[PASS] test_setCanDeployFrom_notAuthorized() (gas: 24097)
[PASS] test_setCanDeployFrom_success_governor() (gas: 51684)
[PASS] test_setCanDeployFrom_success_operationalAdmin() (gas: 88617)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.16ms (598.67µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetValidInstanceOfTests
[PASS] test_setValidInstanceOf_notAuthorized() (gas: 58309)
[PASS] test_setValidInstanceOf_success_governor() (gas: 44086)
[PASS] test_setValidInstanceOf_success_operationalAdmin() (gas: 81113)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.92ms (575.80µs CPU time)

Ran 5 tests for tests/GovernorTimelock/GovernorTimelockScenarios.t.sol:GovernorTimelockScenariosTests
[PASS] test_deployment() (gas: 45190)
[PASS] test_executeProposals_revert_unscheduledProposal() (gas: 98500)
[PASS] test_proposeRoleUpdates_unsuccessfulUnschedule() (gas: 109355)
[PASS] test_setFunctionTimelockParameters_respectsDelayOfFunction() (gas: 388223)
[PASS] test_updateTimelockConfig_success_fullProposalCycle() (gas: 170017)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 4.67ms (2.83ms CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:SetPriceOracleTests
[PASS] test_setPriceOracle() (gas: 55546)
[PASS] test_setPriceOracle_notGovernor() (gas: 22063)
[PASS] test_setPriceOracle_zeroAddressCheck() (gas: 46110)
[PASS] test_setPriceOracle_zeroTimeCheck() (gas: 24834)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.06ms (490.72µs CPU time)

Ran 6 tests for tests/MapleGlobals.t.sol:GetLatestPriceTests
[PASS] test_getLatestPrice() (gas: 79036)
[PASS] test_getLatestPrice_manualOverride() (gas: 98140)
[PASS] test_getLatestPrice_oracleNotSet() (gas: 21410)
[PASS] test_getLatestPrice_roundNotComplete() (gas: 30122)
[PASS] test_getLatestPrice_stalePrice() (gas: 96392)
[PASS] test_getLatestPrice_zeroPrice() (gas: 53879)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 3.38ms (1.28ms CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetContractPauseTests
[PASS] test_setContractPause_asGovernor() (gas: 43413)
[PASS] test_setContractPause_asSecurityAdmin() (gas: 45229)
[PASS] test_setContractPause_notAuthorized() (gas: 21664)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.30ms (506.49µs CPU time)

Ran 5 tests for tests/MapleGlobals.t.sol:UnScheduleCallTests
[PASS] test_unscheduleCall() (gas: 29441)
[PASS] test_unscheduleCall_asGovernor() (gas: 34316)
[PASS] test_unscheduleCall_asGovernor_callDataMismatch() (gas: 32089)
[PASS] test_unscheduleCall_callDataMismatch() (gas: 27171)
[PASS] test_unscheduleCall_notGovernor() (gas: 20231)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.36ms (1.65ms CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:SetValidPoolAssetTests
[PASS] test_setValidPoolAsset() (gas: 42178)
[PASS] test_setValidPoolAsset_notGovernor() (gas: 55282)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.62ms (330.84µs CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:SetDefaultTimelockParametersTests
[PASS] test_setDefaultTimelockParameters() (gas: 47573)
[PASS] test_setDefaultTimelockParameters_notGovernor() (gas: 17478)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.02ms (223.19µs CPU time)

Ran 8 tests for tests/GovernorTimelock/SetFunctionTimelockParameters.t.sol:SetFunctionTimelockParametersTests
[PASS] test_deployment() (gas: 45190)
[PASS] test_setFunctionTimelockParameters_resetToDefaults_success() (gas: 41330)
[PASS] test_setFunctionTimelockParameters_revert_invalidDefaultForDelay() (gas: 10636)
[PASS] test_setFunctionTimelockParameters_revert_invalidDefaultForExecutionWindow() (gas: 10575)
[PASS] test_setFunctionTimelockParameters_revert_invalidDelay() (gas: 15249)
[PASS] test_setFunctionTimelockParameters_revert_invalidExecutionWindow() (gas: 15276)
[PASS] test_setFunctionTimelockParameters_revert_notSelf() (gas: 12575)
[PASS] test_setFunctionTimelockParameters_success() (gas: 45507)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 8.84ms (7.20ms CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:SetValidPoolDelegate
[PASS] test_setValidDeployer_zeroAddress() (gas: 19972)
[PASS] test_setValidPoolDelegate_notAuthorized() (gas: 57553)
[PASS] test_setValidPoolDelegate_success_governor() (gas: 42773)
[PASS] test_setValidPoolDelegate_success_operationalAdmin() (gas: 80005)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.11ms (647.00µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetFunctionUnpauseTests
[PASS] test_setContractPause_asGovernor() (gas: 47780)
[PASS] test_setContractPause_asSecurityAdmin() (gas: 47996)
[PASS] test_setContractPause_notAuthorized() (gas: 24064)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.26ms (558.42µs CPU time)

Ran 7 tests for tests/MapleGlobals.t.sol:canDeployFromTests
[PASS] test_canDeployFrom_invalidFactoryAndCaller() (gas: 29969)
[PASS] test_canDeployFrom_poolManagerDeployingLoanManager() (gas: 104525)
[PASS] test_canDeployFrom_poolManagerDeployingLoanManager_WithValidFactoryAndCallerSet() (gas: 136223)
[PASS] test_canDeployFrom_validBorrowerDeploying_invalidFactoryInstance() (gas: 61321)
[PASS] test_canDeployFrom_validBorrowerDeploying_validFactoryInstanceSet() (gas: 84862)
[PASS] test_canDeployFrom_validBorrowerDeploying_withoutFactoryAndCallerSet() (gas: 90615)
[PASS] test_canDeployFrom_validFactoryAndCaller() (gas: 54970)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 4.56ms (1.58ms CPU time)

Ran 7 tests for tests/MapleGlobals.t.sol:ActivatePoolManagerTests
[PASS] test_activatePoolManager_alreadyOwns() (gas: 54737)
[PASS] test_activatePoolManager_invalidDelegate() (gas: 78896)
[PASS] test_activatePoolManager_invalidFactory() (gas: 71451)
[PASS] test_activatePoolManager_invalidInstance() (gas: 73119)
[PASS] test_activatePoolManager_notAuthorized() (gas: 58266)
[PASS] test_activatePoolManager_success_governor() (gas: 53907)
[PASS] test_activatePoolManager_success_operationalAdmin() (gas: 56109)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 6.77ms (1.76ms CPU time)

Ran 3 tests for tests/GovernorTimelock/SetPendingTokenWithdrawer.sol:SetPendingTokenWithdrawerTests
[PASS] test_deployment() (gas: 45168)
[PASS] test_setPendingTokenWithdrawer_revert_notTokenWithdrawer() (gas: 13747)
[PASS] test_setPendingTokenWithdrawer_success() (gas: 47241)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.55ms (930.80µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetProtocolPauseTests
[PASS] test_setProtocolPause_asGovernor() (gas: 33963)
[PASS] test_setProtocolPause_asSecurityAdmin() (gas: 34300)
[PASS] test_setProtocolPause_notAuthorized() (gas: 19139)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 7.93ms (482.23µs CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:SetManualOverridePriceTests
[PASS] test_setManualOverridePrice() (gas: 310430)
[PASS] test_setManualOverridePrice_notGovernor() (gas: 55560)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.04ms (397.15µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetSecurityAdminTests
[PASS] test_setSecurityAdmin() (gas: 49178)
[PASS] test_setSecurityAdmin_notGovernor() (gas: 19187)
[PASS] test_setSecurityAdmin_zeroAddressCheck() (gas: 19784)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.71ms (283.60µs CPU time)

Ran 10 tests for tests/GovernorTimelock/ExecuteProposals.t.sol:ExecuteProposalsTests
[PASS] test_deployment() (gas: 45168)
[PASS] test_executeProposals_executionFailed() (gas: 294196)
[PASS] test_executeProposals_revert_emptyArray() (gas: 15873)
[PASS] test_executeProposals_revert_invalidData() (gas: 321804)
[PASS] test_executeProposals_revert_invalidDataLength() (gas: 17754)
[PASS] test_executeProposals_revert_invalidTargetsLength() (gas: 16903)
[PASS] test_executeProposals_revert_notExecutable() (gas: 365428)
[PASS] test_executeProposals_revert_notExecutor() (gas: 13176)
[PASS] test_executeProposals_revert_notFound() (gas: 25131)
[PASS] test_executeProposals_success() (gas: 313971)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 16.09ms (14.34ms CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetValidPoolDeployer
[PASS] test_setValidDeployer_enablingNotAllowed() (gas: 22121)
[PASS] test_setValidDeployer_notGovernor() (gas: 19399)
[PASS] test_setValidDeployer_success() (gas: 25193)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.63ms (215.60µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetMapleTreasuryTests
[PASS] test_setMapleTreasury() (gas: 49168)
[PASS] test_setMapleTreasury_notGovernor() (gas: 19119)
[PASS] test_setMapleTreasury_zeroAddressCheck() (gas: 19673)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.61ms (279.11µs CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:SetMaxCoverLiquidationPercentTests
[PASS] test_setMaxCoverLiquidationPercent_gt100() (gas: 55502)
[PASS] test_setMaxCoverLiquidationPercent_notAuthorized() (gas: 57579)
[PASS] test_setMaxCoverLiquidationPercent_success_governor() (gas: 50373)
[PASS] test_setMaxCoverLiquidationPercent_success_operationalAdmin() (gas: 79662)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.04ms (552.03µs CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:SetOperationalAdminTests
[PASS] test_setOperationalAdmin() (gas: 49126)
[PASS] test_setOperationalAdmin_notGovernor() (gas: 19119)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.51ms (194.93µs CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:SetPendingGovernorTests
[PASS] test_setPendingGovernor() (gas: 48704)
[PASS] test_setPendingGovernor_notGovernor() (gas: 19139)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.53ms (196.03µs CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:SetTimelockWindowTests
[PASS] test_setTimelockWindow() (gas: 54440)
[PASS] test_setTimelockWindow_notGovernor() (gas: 20301)
[PASS] test_setTimelockWindows() (gas: 91506)
[PASS] test_setTimelockWindows_notGovernor() (gas: 22958)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.14ms (712.81µs CPU time)

Ran 2 tests for tests/MapleGlobals.t.sol:SetMigrationAdminTests
[PASS] test_setMigrationAdmin() (gas: 49209)
[PASS] test_setMigrationAdmin_notGovernor() (gas: 19162)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.50ms (173.46µs CPU time)

Ran 3 tests for tests/GovernorTimelock/UpdateRole.t.sol:UpdateRoleTests
[PASS] test_deployment() (gas: 45190)
[PASS] test_updateRole_revert_notSelf() (gas: 12011)
[PASS] test_updateRole_success() (gas: 37946)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 2.46ms (839.93µs CPU time)

[PASS] test_isValidScheduledCall() (gas: 90994)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 2.04ms (405.83µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetMinCoverAmountTests
[PASS] test_setMinCoverAmount_notAuthorized() (gas: 57639)
[PASS] test_setMinCoverAmount_success_governor() (gas: 50347)
[PASS] test_setMinCoverAmount_success_operationalAdmin() (gas: 79570)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.88ms (443.58µs CPU time)

Ran 5 tests for tests/GovernorTimelock/UnscheduleProposal.t.sol:UnscheduleProposalsTests
[PASS] test_deployment() (gas: 45168)
[PASS] test_unscheduleProposals_revert_notCanceller() (gas: 11825)
[PASS] test_unscheduleProposals_revert_notUnschedulable() (gas: 176226)
[PASS] test_unscheduleProposals_revert_proposalNotFound() (gas: 17175)
[PASS] test_unscheduleProposals_success() (gas: 289131)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 6.62ms (4.82ms CPU time)

Ran 4 tests for tests/GovernorTimelock/WithdrawERC20Token.t.sol:WithdrawERC20TokenTests
[PASS] test_deployment() (gas: 45168)
[PASS] test_withdrawERC20Token_revert_notTokenWithdrawer() (gas: 13872)
[PASS] test_withdrawERC20Token_revert_transferFailed() (gas: 23345)
[PASS] test_withdrawERC20Token_success() (gas: 51794)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.01ms (524.47µs CPU time)

Ran 6 tests for tests/GovernorTimelock/ProposeRoleUpdates.t.sol:ProposeRoleUpdatesTests
[PASS] test_deployment() (gas: 45168)
[PASS] test_proposeRoleUpdates_revert_emptyArray() (gas: 15864)
[PASS] test_proposeRoleUpdates_revert_invalidAccountsLength() (gas: 16938)
[PASS] test_proposeRoleUpdates_revert_invalidShouldGrantLength() (gas: 17297)
[PASS] test_proposeRoleUpdates_revert_notRoleAdmin() (gas: 13211)
[PASS] test_proposeRoleUpdates_success() (gas: 196970)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 8.17ms (4.12ms CPU time)

[PASS] test_isFunctionPaused() (gas: 256932)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 9.57ms (1.37ms CPU time)

Ran 4 tests for tests/MapleGlobals.t.sol:SetPlatformManagementFeeRateTests
[PASS] test_setPlatformManagementFeeRate_notAuthorized() (gas: 57736)
[PASS] test_setPlatformManagementFeeRate_outOfBounds() (gas: 55570)
[PASS] test_setPlatformManagementFeeRate_success_governor() (gas: 50511)
[PASS] test_setPlatformManagementFeeRate_success_operationalAdmin() (gas: 79711)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.27ms (648.80µs CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:SetBootstrapMintTests
[PASS] test_setBootstrapMint_notAuthorized() (gas: 57640)
[PASS] test_setBootstrapMint_success_governor() (gas: 50410)
[PASS] test_setBootstrapMint_success_operationalAdmin() (gas: 79632)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.82ms (578.19µs CPU time)

Ran 7 tests for tests/GovernorTimelock/ScheduleProposals.t.sol:ScheduleProposalsTests
[PASS] test_deployment() (gas: 45190)
[PASS] test_scheduleProposals_revert_arrayLengthMismatch() (gas: 16710)
[PASS] test_scheduleProposals_revert_emptyArray() (gas: 15237)
[PASS] test_scheduleProposals_revert_emptyTarget() (gas: 21390)
[PASS] test_scheduleProposals_revert_notProposer() (gas: 12539)
[PASS] test_scheduleProposals_revert_updateRoleNotAllowed() (gas: 191197)
[PASS] test_scheduleProposals_success() (gas: 385500)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 4.89ms (3.29ms CPU time)

Ran 10 tests for tests/MapleGlobals.t.sol:IsPoolDeployerTest
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerCanDeploy() (gas: 79356)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerCannotDeploy() (gas: 58509)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_deployerIsPoolManager() (gas: 470261)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_poolManagerNotFromValidFactory() (gas: 449418)
[PASS] test_isPoolDeployer_fixedTermLoanFactory_poolManagerNotInstance() (gas: 446083)
[PASS] test_isPoolDeployer_invalidFactory() (gas: 21731)
[PASS] test_isPoolDeployer_poolManagerFactory_deployerCanDeploy() (gas: 81656)
[PASS] test_isPoolDeployer_poolManagerFactory_deployerCannotDeploy() (gas: 60856)
[PASS] test_isPoolDeployer_withdrawalManagerFactory_deployerCanDeploy() (gas: 83981)
[PASS] test_isPoolDeployer_withdrawalManagerFactory_deployerCannotDeploy() (gas: 63204)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 5.30ms (5.44ms CPU time)

Ran 3 tests for tests/MapleGlobals.t.sol:ScheduleCallTests
[PASS] test_scheduleCal_overwrite() (gas: 82503)
[PASS] test_scheduleCall() (gas: 69746)
[PASS] test_scheduleCall_defaultState() (gas: 19157)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 7.21ms (475.64µs CPU time)

Ran 47 test suites in 73.51ms (168.54ms CPU time): 181 tests passed, 0 failed, 0 skipped (181 total tests)


## open-term-loan

Ran 2 tests for tests/IsInDefault.t.sol:DefaultDatesTests
[PASS] test_isInDefault_successBoundary() (gas: 37730)
[PASS] test_isInDefault_zeroDefaultDate() (gas: 10353)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 885.73µs (172.00µs CPU time)

Ran 3 tests for tests/AcceptLender.t.sol:AcceptLenderTests
[PASS] test_acceptLender_notPendingLender() (gas: 48654)
[PASS] test_acceptLender_paused() (gas: 46191)
[PASS] test_acceptLender_success() (gas: 57255)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.49ms (454.68µs CPU time)

Ran 3 tests for tests/AcceptBorrower.t.sol:AcceptBorrowerTests
[PASS] test_acceptBorrower_notPendingBorrower() (gas: 48700)
[PASS] test_acceptBorrower_paused() (gas: 46171)
[PASS] test_acceptBorrower_success() (gas: 57205)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.50ms (437.73µs CPU time)

Ran 5 tests for tests/AcceptLoanTerms.t.sol:AcceptLoanTermsTests
[PASS] test_acceptLoanTerms_alreadyAccepted() (gas: 51466)
[PASS] test_acceptLoanTerms_notBorrower() (gas: 30608)
[PASS] test_acceptLoanTerms_paused() (gas: 46188)
[PASS] test_acceptLoanTerms_success_asBorrower() (gas: 54182)
[PASS] test_acceptLoanTerms_success_asBorrowerActions() (gas: 83840)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 2.03ms (643.93µs CPU time)

Ran 5 tests for tests/MakePayment.t.sol:MakePaymentFailureTests
[PASS] test_makePayment_insufficientForCalled() (gas: 107447)
[PASS] test_makePayment_insufficientForTotalTransferFromCaller() (gas: 1528232)
[PASS] test_makePayment_notFunded() (gas: 26551)
[PASS] test_makePayment_paused() (gas: 47580)
[PASS] test_makePayment_returningTooMuch() (gas: 86036)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 3.79ms (2.46ms CPU time)

Ran 7 tests for tests/Fund.t.sol:FundTests
[PASS] testFuzz_fund_success() (gas: 1615271)
[PASS] test_fund_loanActive() (gas: 54349)
[PASS] test_fund_loanClosed() (gas: 35145)
[PASS] test_fund_notLender() (gas: 25850)
[PASS] test_fund_paused() (gas: 46958)
[PASS] test_fund_revertingTransfer() (gas: 1521294)
[PASS] test_fund_termsNotAccepted() (gas: 30270)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 11.08ms (9.67ms CPU time)

Ran 4 tests for tests/AcceptNewTerms.t.sol:AcceptNewTerms
[PASS] test_acceptNewTerms_earlyRefinance() (gas: 448435)
[PASS] test_acceptNewTerms_principalDecrease() (gas: 462776)
[PASS] test_acceptNewTerms_principalDecreaseToZero() (gas: 450855)
[PASS] test_acceptNewTerms_principalIncrease() (gas: 483196)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 30.37ms (27.94ms CPU time)

Ran 7 tests for tests/AcceptNewTerms.t.sol:AcceptNewTermsFailure
[PASS] test_acceptNewTerms_expiredCommitmentBoundary() (gas: 3065516)
[PASS] test_acceptNewTerms_invalidRefinancer() (gas: 56353)
[PASS] test_acceptNewTerms_mismatchedCommitment() (gas: 37323)
[PASS] test_acceptNewTerms_notBorrower() (gas: 32449)
[PASS] test_acceptNewTerms_paused() (gas: 48030)
[PASS] test_acceptNewTerms_refinancerRevert() (gas: 101411)
[PASS] test_acceptNewTerms_transferRevert() (gas: 1307795)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 3.58ms (1.97ms CPU time)

Ran 3 tests for tests/AcceptNewTerms.t.sol:AcceptNewTermsPrincipalChangeTests
[PASS] test_acceptNewTerms_payInterestAndIncreasePrincipalForBorrower() (gas: 479092)
[PASS] test_acceptNewTerms_payInterestWithExactPrincipalIncrease() (gas: 439815)
[PASS] test_acceptNewTerms_payInterestWithSingleWeiFromBorrower() (gas: 465431)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 21.24ms (19.16ms CPU time)

[PASS] testFuzz_defaultDates(uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 75359, ~: 75768)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 167.29ms (166.57ms CPU time)

Ran 4 tests for tests/Getter.t.sol:GetterTests
[PASS] test_factory_getter() (gas: 10390)
[PASS] test_globals_getter() (gas: 16099)
[PASS] test_isCalled_getter() (gas: 30978)
[PASS] test_isImpaied_getter() (gas: 31028)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 1.59ms (266.82µs CPU time)

Ran 5 tests for tests/SetPendingBorrower.t.sol:SetPendingBorrowerTests
[PASS] test_setPendingBorrower_invalidBorrower() (gas: 35821)
[PASS] test_setPendingBorrower_notBorrower() (gas: 33388)
[PASS] test_setPendingBorrower_paused() (gas: 48992)
[PASS] test_setPendingBorrower_success_asBorrowerActions() (gas: 113092)
[PASS] test_setPendingBorrower_success_asCurrentBorrower() (gas: 85328)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 5.23ms (893.80µs CPU time)

Ran 3 tests for tests/SetPendingLender.t.sol:SetPendingLenderTests
[PASS] test_setPendingLender_notLender() (gas: 27797)
[PASS] test_setPendingLender_paused() (gas: 48858)
[PASS] test_setPendingLender_success() (gas: 77832)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.61ms (364.34µs CPU time)

Ran 7 tests for tests/Skim.t.sol:SkimTests
[PASS] test_skim_borrower() (gas: 1484553)
[PASS] test_skim_governor() (gas: 1482416)
[PASS] test_skim_noTokenToSkim() (gas: 1334560)
[PASS] test_skim_notBorrower() (gas: 31226)
[PASS] test_skim_paused() (gas: 32445)
[PASS] test_skim_revertingToken() (gas: 1411761)
[PASS] test_skim_zeroAddress() (gas: 24154)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 7.22ms (5.24ms CPU time)

Ran 4 tests for tests/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 28661)
[PASS] test_upgrade_noAuth_asBorrower() (gas: 31292)
[PASS] test_upgrade_paused() (gas: 49820)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 234737)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.64ms (1.19ms CPU time)

[PASS] test_migrate_success() (gas: 54203)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 3.19ms (182.37µs CPU time)

Ran 7 tests for tests/ProposeNewTerms.t.sol:ProposeNewTermsTests
[PASS] test_proposeNewTerms_deadlineBoundary() (gas: 113070)
[PASS] test_proposeNewTerms_emptyCalls() (gas: 63920)
[PASS] test_proposeNewTerms_invalidRefinancer() (gas: 39638)
[PASS] test_proposeNewTerms_notFunded() (gas: 33631)
[PASS] test_proposeNewTerms_notLender() (gas: 26902)
[PASS] test_proposeNewTerms_paused() (gas: 48009)
[PASS] test_proposeNewTerms_success() (gas: 116203)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 3.06ms (1.56ms CPU time)

Ran 4 tests for tests/RemoveCall.t.sol:RemoveCallTests
[PASS] testFuzz_removeCall_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 107792, ~: 108512)
[PASS] test_removeCall_notCalled() (gas: 30471)
[PASS] test_removeCall_notLender() (gas: 25614)
[PASS] test_removeCall_paused() (gas: 46720)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 196.21ms (194.82ms CPU time)

[PASS] testFuzz_dueDates(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 70122, ~: 70365)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 222.18ms (221.47ms CPU time)

Ran 11 tests for tests/GetPaymentBreakdown.t.sol:GetPaymentBreakdownTests
[PASS] testFuzz_getPaymentBreakdown(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 295774, ~: 286969)
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
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 243.72ms (242.78ms CPU time)

Ran 6 tests for tests/RejectNewTerms.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_mismatchedCommitment() (gas: 34615)
[PASS] test_rejectNewTerms_notBorrowerNorLender() (gas: 36724)
[PASS] test_rejectNewTerms_paused() (gas: 50099)
[PASS] test_rejectNewTerms_success_asBorrower() (gas: 47689)
[PASS] test_rejectNewTerms_success_asBorrowerActions() (gas: 77427)
[PASS] test_rejectNewTerms_success_asLender() (gas: 55335)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 3.05ms (1.18ms CPU time)

Ran 6 tests for tests/Repossess.t.sol:RepossessTests
[PASS] test_repossess_notInDefault() (gas: 57125)
[PASS] test_repossess_notLender() (gas: 28094)
[PASS] test_repossess_paused() (gas: 49155)
[PASS] test_repossess_revertingToken() (gas: 1428999)
[PASS] test_repossess_success() (gas: 1621055)
[PASS] test_repossess_success_noTransfer() (gas: 1474883)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 11.63ms (9.59ms CPU time)

Ran 3 tests for tests/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 23720)
[PASS] test_setImplementation_paused() (gas: 46810)
[PASS] test_setImplementation_success() (gas: 93403)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.26ms (313.99µs CPU time)

Ran 4 tests for tests/Impair.t.sol:ImpairTests
[PASS] testFuzz_impair_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 105918, ~: 106477)
[PASS] test_impair_loanNotFunded() (gas: 30539)
[PASS] test_impair_notLender() (gas: 25614)
[PASS] test_impair_paused() (gas: 46743)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 262.08ms (260.74ms CPU time)

Ran 3 tests for tests/Migrate.t.sol:MigrateTests
[PASS] test_migrate_notFactory() (gas: 24454)
[PASS] test_migrate_paused() (gas: 47455)
[PASS] test_migrate_success() (gas: 71013)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.37ms (367.13µs CPU time)

Ran 11 tests for tests/Initializer.t.sol:InitializerTests
[PASS] test_initialize_differentFundsAsset() (gas: 115879)
[PASS] test_initialize_invalidBorrower() (gas: 57213)
[PASS] test_initialize_invalidFundsAsset() (gas: 60950)
[PASS] test_initialize_invalidLenderFactory() (gas: 1760572)
[PASS] test_initialize_invalidLenderFactoryInstance() (gas: 1790211)
[PASS] test_initialize_invalidNoticePeriod() (gas: 22386)
[PASS] test_initialize_invalidPaymentInterval() (gas: 22435)
[PASS] test_initialize_invalidPrincipal() (gas: 22274)
[PASS] test_initialize_success() (gas: 301929)
[PASS] test_initialize_zeroBorrower() (gas: 28478)
[PASS] test_initialize_zeroLender() (gas: 60694)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 7.67ms (4.34ms CPU time)

Ran 6 tests for tests/CallPrincipal.t.sol:CallPrincipalTests
[PASS] testFuzz_callPrincipal_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 137506, ~: 138147)
[PASS] test_callPrincipal_insufficientPrincipalToReturn() (gas: 52434)
[PASS] test_callPrincipal_loanNotFunded() (gas: 30993)
[PASS] test_callPrincipal_notLender() (gas: 26067)
[PASS] test_callPrincipal_paused() (gas: 47151)
[PASS] test_callPrincipal_principalToReturnBoundary() (gas: 106826)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 312.89ms (312.50ms CPU time)

Ran 4 tests for tests/RemoveImpairment.t.sol:RemoveImpairmentTests
[PASS] testFuzz_removeImpairment_success(uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 103019, ~: 103593)
[PASS] test_removeImpairment_notImpaired() (gas: 30536)
[PASS] test_removeImpairment_notLender() (gas: 25634)
[PASS] test_removeImpairment_paused() (gas: 46719)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 228.19ms (227.28ms CPU time)

Ran 2 tests for tests/Factory.t.sol:FactoryTests
[PASS] test_createInstance(bytes32) (runs: 256, μ: 442869, ~: 442869)
[PASS] test_createInstance_cannotDeploy(bytes32) (runs: 256, μ: 44453, ~: 44453)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 799.96ms (435.14ms CPU time)

Ran 10 tests for tests/Refinancer.t.sol:RefinancerTests
[PASS] test_refinancer_decreasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144680, ~: 146339)
[PASS] test_refinancer_increasePrincipal(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144358, ~: 146222)
[PASS] test_refinancer_multipleCalls_refinance(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 176963, ~: 177900)
[PASS] test_refinancer_setDelegateServiceFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143063, ~: 144773)
[PASS] test_refinancer_setGracePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 143160, ~: 145005)
[PASS] test_refinancer_setInterestRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144498, ~: 146400)
[PASS] test_refinancer_setLateFeeRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144066, ~: 145312)
[PASS] test_refinancer_setLateInterestPremiumRate(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144281, ~: 146209)
[PASS] test_refinancer_setNoticePeriod(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144919, ~: 146550)
[PASS] test_refinancer_setPaymentInterval(uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256,uint256) (runs: 256, μ: 144594, ~: 146263)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 605.89ms (2.94s CPU time)

[PASS] testFuzz_makePayment(uint256,uint256,uint256,uint256) (runs: 256, μ: 564617, ~: 572090)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 876.36ms (864.85ms CPU time)

Ran 31 test suites in 882.81ms (4.04s CPU time): 143 tests passed, 0 failed, 0 skipped (143 total tests)


## open-term-loan-manager

Ran 4 tests for tests/Call.t.sol:CallPrincipalTests
[PASS] test_callPrincipal_notLoan() (gas: 36801)
[PASS] test_callPrincipal_notPoolDelegate() (gas: 33939)
[PASS] test_callPrincipal_paused() (gas: 49258)
[PASS] test_callPrincipal_success() (gas: 219567)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 2.12ms (655.13µs CPU time)

Ran 6 tests for tests/DistributeLiquidationFunds.t.sol:DistributeLiquidationFundsFailureTests
[PASS] test_distributeLiquidationFunds_transferBorrower() (gas: 62615)
[PASS] test_distributeLiquidationFunds_transferPool() (gas: 96332)
[PASS] test_distributeLiquidationFunds_transferTreasury() (gas: 135887)
[PASS] test_distributeLiquidationFunds_zeroBorrower() (gas: 31964)
[PASS] test_distributeLiquidationFunds_zeroPool() (gas: 63616)
[PASS] test_distributeLiquidationFunds_zeroTreasury() (gas: 103186)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 3.29ms (1.24ms CPU time)

Ran 3 tests for tests/ImpairLoan.t.sol:ImpairLoanLimitTests
[PASS] test_impairLoan_accountedInterestLimit() (gas: 334688)
[PASS] test_impairLoan_impairmentDateLimit() (gas: 276295)
[PASS] test_impairLoan_unrealizedLossesLimit() (gas: 321500)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.63ms (1.74ms CPU time)

Ran 4 tests for tests/Call.t.sol:RemoveCallTests
[PASS] test_removeCall_notLoan() (gas: 36510)
[PASS] test_removeCall_notPoolDelegate() (gas: 33647)
[PASS] test_removeCall_paused() (gas: 49012)
[PASS] test_removeCall_success() (gas: 163392)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.15ms (569.69µs CPU time)

Ran 4 tests for tests/ImpairLoan.t.sol:ImpairLoanSuccessTests
[PASS] test_impairLoan_acl_governor() (gas: 86453)
[PASS] test_impairLoan_acl_poolDelegate() (gas: 94367)
[PASS] test_impairLoan_success() (gas: 237556)
[PASS] test_impairLoan_success_alreadyImpaired() (gas: 301460)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 5.36ms (3.32ms CPU time)

Ran 7 tests for tests/Claim.t.sol:ClaimFailureTests
[PASS] test_claim_invalidState1() (gas: 61971)
[PASS] test_claim_invalidState2() (gas: 61982)
[PASS] test_claim_invalidState3() (gas: 62006)
[PASS] test_claim_invalidState4() (gas: 85800)
[PASS] test_claim_notLoan() (gas: 29726)
[PASS] test_claim_notPaused() (gas: 30908)
[PASS] test_claim_reentrancy() (gas: 210)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 3.11ms (1.01ms CPU time)

Ran 6 tests for tests/CreateInstance.t.sol:CreateInstanceTests
[PASS] test_createInstance_cannotDeploy() (gas: 20830)
[PASS] test_createInstance_invalidFactory() (gas: 208565)
[PASS] test_createInstance_invalidInstance() (gas: 214446)
[PASS] test_createInstance_revertIfCollision() (gas: 1040439035)
[PASS] test_createInstance_revertIfnotPool() (gas: 193001)
[PASS] test_createInstance_success() (gas: 301735)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 6.77ms (2.69ms CPU time)

Ran 9 tests for tests/Fund.t.sol:FundFailureTests
[PASS] test_fund_failedApproval() (gas: 305098)
[PASS] test_fund_fundingMismatch() (gas: 249481)
[PASS] test_fund_inactiveLoan() (gas: 137835)
[PASS] test_fund_invalidBorrower() (gas: 111961)
[PASS] test_fund_invalidFactory() (gas: 52687)
[PASS] test_fund_invalidLoan() (gas: 85086)
[PASS] test_fund_notPoolDelegate() (gas: 36527)
[PASS] test_fund_paused() (gas: 46877)
[PASS] test_fund_reentrancy() (gas: 3063037)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 7.14ms (5.29ms CPU time)

Ran 4 tests for tests/RejectNewTerms.t.sol:RejectNewTermsTests
[PASS] test_rejectNewTerms_notLoan() (gas: 37807)
[PASS] test_rejectNewTerms_notPoolDelegate() (gas: 34945)
[PASS] test_rejectNewTerms_paused() (gas: 50263)
[PASS] test_rejectNewTerms_success() (gas: 370039)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 11.18ms (9.47ms CPU time)

Ran 6 tests for tests/DistributeClaimedFunds.t.sol:DistributeClaimedFundsFailureTests
[PASS] test_distributeClaimFunds_platformTransfer() (gas: 114619)
[PASS] test_distributeClaimFunds_poolTransfer() (gas: 66853)
[PASS] test_distributeClaimFunds_zeroDelegate() (gas: 74958)
[PASS] test_distributeClaimFunds_zeroPool() (gas: 34186)
[PASS] test_distributeClaimFunds_zeroPoolDelegate() (gas: 61369)
[PASS] test_distributeClaimFunds_zeroTreasury() (gas: 81969)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 7.54ms (1.26ms CPU time)

Ran 4 tests for tests/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentFailureTests
[PASS] test_removeLoanImpairment_noAuth() (gas: 109665)
[PASS] test_removeLoanImpairment_notLoan() (gas: 30665)
[PASS] test_removeLoanImpairment_paused() (gas: 31780)
[PASS] test_removeLoanImpairment_poolDelegateAfterGovernor() (gas: 104416)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 9.18ms (6.26ms CPU time)

Ran 4 tests for tests/ProposeNewTerms.t.sol:ProposeNewTermsTests
[PASS] test_proposeNewTerms_notLoan() (gas: 40572)
[PASS] test_proposeNewTerms_notPoolDelegate() (gas: 37665)
[PASS] test_proposeNewTerms_paused() (gas: 53073)
[PASS] test_proposeNewTerms_success() (gas: 370106)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.40ms (1.61ms CPU time)

Ran 3 tests for tests/RemoveLoanImpairment.t.sol:RemoveLoanImpairmentSuccessTests
[PASS] test_removeLoanImpairment_acl_governor_success() (gas: 86417)
[PASS] test_removeLoanImpairment_success() (gas: 232231)
[PASS] test_removeLoanImpairment_success_alreadyUnimpaired() (gas: 298844)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 9.12ms (2.43ms CPU time)

Ran 3 tests for tests/ImpairLoan.t.sol:ImpairLoanFailureTests
[PASS] test_impairLoan_notLoan() (gas: 30688)
[PASS] test_impairLoan_notPoolDelegateOrGovernor() (gas: 62776)
[PASS] test_impairLoan_paused() (gas: 31824)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 9.54ms (407.08µs CPU time)

Ran 3 tests for tests/TriggerDefault.t.sol:TriggerDefaultFailureTests
[PASS] test_triggerDefault_notLoan() (gas: 29045)
[PASS] test_triggerDefault_notPoolDelegate() (gas: 52388)
[PASS] test_triggerDefault_paused() (gas: 47303)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 5.91ms (372.22µs CPU time)

Ran 2 tests for tests/TriggerDefault.t.sol:TriggerDefaultSuccessTests
[PASS] test_triggerDefault_success_impaired() (gas: 127694)
[PASS] test_triggerDefault_success_notImpaired() (gas: 144035)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 8.73ms (1.79ms CPU time)

Ran 5 tests for tests/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 36587)
[PASS] test_upgrade_notScheduled() (gas: 38973)
[PASS] test_upgrade_paused() (gas: 47166)
[PASS] test_upgrade_success_asPoolDelegate() (gas: 267440)
[PASS] test_upgrade_success_asSecurityAdmin() (gas: 242666)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 7.32ms (1.85ms CPU time)

[PASS] testFuzz_updateUnrealizedLosses(uint256,int256) (runs: 256, μ: 44652, ~: 45552)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 77.25ms (76.22ms CPU time)

Ran 10 tests for tests/Claim.t.sol:ClaimTests
[PASS] test_claim() (gas: 292994)
[PASS] test_claim_closingLoan() (gas: 254851)
[PASS] test_claim_impaired() (gas: 296699)
[PASS] test_claim_impaired_requestingPrincipal() (gas: 369089)
[PASS] test_claim_impaired_returningPrincipal() (gas: 334817)
[PASS] test_claim_payInterestWithPrincipalIncrease_exactAmount() (gas: 341478)
[PASS] test_claim_payInterestWithPrincipalIncrease_oneWeiExtra() (gas: 391956)
[PASS] test_claim_requestingPrincipalIncrease() (gas: 391921)
[PASS] test_claim_returnMorePrincipal() (gas: 294676)
[PASS] test_claim_returningPrincipal() (gas: 306530)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 97.78ms (23.24ms CPU time)

[PASS] testFuzz_updatePrincipalOut(uint256,int256) (runs: 256, μ: 44598, ~: 45406)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 89.19ms (88.52ms CPU time)

[PASS] testFuzz_updateInterestAccounting(uint256,uint256,uint256,int256,int256) (runs: 256, μ: 89190, ~: 89181)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 140.81ms (140.00ms CPU time)

[PASS] testFuzz_distributeLiquidationFunds(uint256,uint256,uint256,uint256) (runs: 256, μ: 169821, ~: 166179)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 184.97ms (174.79ms CPU time)

[PASS] testFuzz_distributeClaimFunds(int256,uint256,uint256,uint256,bool) (runs: 256, μ: 187628, ~: 180805)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 197.30ms (195.27ms CPU time)

Ran 5 tests for tests/Fund.t.sol:FundSuccessTests
[PASS] testFuzz_fund_multipleLoans(uint256) (runs: 256, μ: 75219957, ~: 73863533)
[PASS] test_fund_managementFeeRateLimits() (gas: 3269304)
[PASS] test_fund_paymentIssuanceRateLimit() (gas: 3356610)
[PASS] test_fund_principalLimit() (gas: 3463308)
[PASS] test_fund_startDateAndDomainStartLimit() (gas: 3390474)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 5.06s (5.07s CPU time)

Ran 24 test suites in 5.08s (5.96s CPU time): 97 tests passed, 0 failed, 0 skipped (97 total tests)


## pool

Ran 3 tests for tests/MaplePool.t.sol:ConstructorTests
[PASS] test_constructor_invalidApproval() (gas: 6027789)
[PASS] test_constructor_invalidDecimals() (gas: 5934729)
[PASS] test_constructor_zeroManager() (gas: 5509190)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 4.71ms (3.15ms CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:DepositCoverTests
[PASS] test_depositCover_insufficientApproval() (gas: 109188)
[PASS] test_depositCover_paused() (gas: 51524)
[PASS] test_depositCover_success() (gas: 94787)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 7.03ms (1.01ms CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:UpgradeTests
[PASS] test_upgrade_noAuth() (gas: 35289)
[PASS] test_upgrade_notScheduled() (gas: 37596)
[PASS] test_upgrade_paused() (gas: 51998)
[PASS] test_upgrade_successWithPoolDelegate() (gas: 103678)
[PASS] test_upgrade_successWithSecurityAdmin() (gas: 100271)
[PASS] test_upgrade_upgradeFailed() (gas: 94539)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 10.30ms (2.67ms CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30457)
[PASS] test_setImplementation_paused() (gas: 53650)
[PASS] test_setImplementation_success() (gas: 40907)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 10.74ms (464.13µs CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:SetIsStrategy_SetterTests
[PASS] test_setIsStrategy_invalidLM() (gas: 720609)
[PASS] test_setIsStrategy_notPoolDelegate() (gas: 41664)
[PASS] test_setIsStrategy_paused() (gas: 53929)
[PASS] test_setIsStrategy_successWithPoolDelegate() (gas: 60972)
[PASS] test_setIsStrategy_success_asGovernor() (gas: 67804)
[PASS] test_setIsStrategy_success_asOperationalAdmin() (gas: 74634)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 8.75ms (1.66ms CPU time)

Ran 7 tests for tests/MaplePoolManager.t.sol:WithdrawCoverTests
[PASS] test_withdrawCover_noRequirement() (gas: 97315)
[PASS] test_withdrawCover_notPoolDelegate() (gas: 157700)
[PASS] test_withdrawCover_paused() (gas: 54737)
[PASS] test_withdrawCover_success() (gas: 151779)
[PASS] test_withdrawCover_success_zeroRecipient() (gas: 151612)
[PASS] test_withdrawCover_tryWithdrawBelowRequired() (gas: 200456)
[PASS] test_withdrawCover_withdrawMoreThanBalance() (gas: 83424)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 12.72ms (2.55ms CPU time)

Ran 10 tests for tests/MaplePoolManager.t.sol:FinishCollateralLiquidation
[PASS] test_finishCollateralLiquidation_notAuthorized() (gas: 208697)
[PASS] test_finishCollateralLiquidation_paused() (gas: 36639)
[PASS] test_finishCollateralLiquidation_success_coverLeftOver() (gas: 282420)
[PASS] test_finishCollateralLiquidation_success_exceedMaxCoverLiquidationPercentAmount() (gas: 279117)
[PASS] test_finishCollateralLiquidation_success_fullCoverLiquidation_preexistingLoss() (gas: 283947)
[PASS] test_finishCollateralLiquidation_success_noCoverLeftOver() (gas: 262497)
[PASS] test_finishCollateralLiquidation_success_noCover_asGovernor() (gas: 244105)
[PASS] test_finishCollateralLiquidation_success_noCover_asOperationalAdmin() (gas: 252404)
[PASS] test_finishCollateralLiquidation_success_noCover_asPoolDelegate() (gas: 237140)
[PASS] test_finishCollateralLiquidation_success_noRemainingLossAfterCollateralLiquidation() (gas: 246062)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 18.75ms (9.01ms CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:SetLiquidityCap_SetterTests
[PASS] test_setLiquidityCap_notPoolDelegate() (gas: 46154)
[PASS] test_setLiquidityCap_paused() (gas: 54278)
[PASS] test_setLiquidityCap_success_asGovernor() (gas: 66844)
[PASS] test_setLiquidityCap_success_asOperationalAdmin() (gas: 72386)
[PASS] test_setLiquidityCap_success_asPoolDelegate() (gas: 64138)
[PASS] test_setLiquidityCap_success_whenNotConfigured() (gas: 52084)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 11.67ms (3.92ms CPU time)

Ran 7 tests for tests/MaplePoolManagerFactory.t.sol:PoolManagerFactoryFailureTest
[PASS] test_createInstance_failWithActivePoolDelegate() (gas: 268952)
[PASS] test_createInstance_failWithDisallowedAsset() (gas: 250599)
[PASS] test_createInstance_failWithInvalidPoolDelegate() (gas: 239071)
[PASS] test_createInstance_failWithNonERC20Asset() (gas: 246529)
[PASS] test_createInstance_failWithZeroAddressPoolDelegate() (gas: 195499)
[PASS] test_createInstance_failWithZeroAdmin() (gas: 5201197)
[PASS] test_createInstance_notPoolDeployer() (gas: 4904692)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 13.41ms (5.98ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:HandleCoverTests
[PASS] test_handleCover_feesAndSomeLosses() (gas: 126670)
[PASS] test_handleCover_fullCoverage() (gas: 146582)
[PASS] test_handleCover_halfCoverage() (gas: 153452)
[PASS] test_handleCover_noCover() (gas: 67529)
[PASS] test_handleCover_onlyFees() (gas: 114749)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 9.34ms (2.67ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:SetPendingPoolDelegate_SetterTests
[PASS] test_setPendingPoolDelegate_asGovernor_success() (gas: 66408)
[PASS] test_setPendingPoolDelegate_asOperationalAdmin_success() (gas: 71861)
[PASS] test_setPendingPoolDelegate_asPoolDelegate_success() (gas: 61887)
[PASS] test_setPendingPoolDelegate_notPoolDelegateOrProtocolAdmins() (gas: 41362)
[PASS] test_setPendingPoolDelegate_paused() (gas: 56294)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 10.48ms (1.25ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:SetWithdrawalManager_SetterTests
[PASS] test_setWithdrawalManager_configured() (gas: 37274)
[PASS] test_setWithdrawalManager_invalidFactory() (gas: 72838)
[PASS] test_setWithdrawalManager_invalidInstance() (gas: 52003)
[PASS] test_setWithdrawalManager_paused() (gas: 56404)
[PASS] test_setWithdrawalManager_success_asPoolDelegate() (gas: 52089)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 9.72ms (1.11ms CPU time)

[PASS] test_createInstance() (gas: 5010625)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 13.18ms (5.77ms CPU time)

Ran 6 tests for tests/MaplePoolManager.t.sol:TriggerDefault
[PASS] test_triggerDefault_invalidFactory() (gas: 117070)
[PASS] test_triggerDefault_notAuthorized() (gas: 48967)
[PASS] test_triggerDefault_paused() (gas: 41742)
[PASS] test_triggerDefault_success_asGovernor() (gas: 85794)
[PASS] test_triggerDefault_success_asOperationalAdmin() (gas: 93798)
[PASS] test_triggerDefault_success_asPoolDelegate() (gas: 81376)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.78ms (4.19ms CPU time)

Ran 2 tests for tests/MaplePoolManagerMigrator.t.sol:MaplePoolManagerMigratorTests
[PASS] test_migrator_failure() (gas: 99097)
[PASS] test_migrator_success() (gas: 157785)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 20.97ms (1.41ms CPU time)

Ran 4 tests for tests/MaplePoolManager.t.sol:MaxDepositTests
[PASS] test_maxDeposit_liquidityCap() (gas: 196685)
[PASS] test_maxDeposit_liquidityCap(address,address,uint256,uint256) (runs: 256, μ: 136313, ~: 136425)
[PASS] test_maxDeposit_withPermission() (gas: 89205)
[PASS] test_maxDeposit_withoutPermission() (gas: 81430)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 159.85ms (150.92ms CPU time)

Ran 7 tests for tests/MaplePool.t.sol:ConvertToAssetsTests
[PASS] testFuzz_convertToAssets(uint256,uint256,uint256) (runs: 256, μ: 188632, ~: 189249)
[PASS] test_convertToAssets_decreasedExchangeRate() (gas: 183675)
[PASS] test_convertToAssets_increasedExchangeRate() (gas: 183676)
[PASS] test_convertToAssets_initialExchangeRate() (gas: 183631)
[PASS] test_convertToAssets_initialState() (gas: 23222)
[PASS] test_convertToAssets_prematureYield() (gas: 43166)
[PASS] test_convertToAssets_worthlessShares() (gas: 163751)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 248.42ms (239.23ms CPU time)

Ran 7 tests for tests/MaplePool.t.sol:PreviewMintTests
[PASS] testFuzz_previewMint(uint256,uint256,uint256) (runs: 256, μ: 192356, ~: 193578)
[PASS] test_previewMint_decreasedExchangeRate() (gas: 184987)
[PASS] test_previewMint_increasedExchangeRate() (gas: 184987)
[PASS] test_previewMint_initialExchangeRate() (gas: 185032)
[PASS] test_previewMint_initialState() (gas: 23368)
[PASS] test_previewMint_prematureYield() (gas: 43247)
[PASS] test_previewMint_worthlessShares() (gas: 165063)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 270.07ms (264.88ms CPU time)

Ran 8 tests for tests/MaplePool.t.sol:RedeemTests
[PASS] test_redeem_checkCall() (gas: 83076)
[PASS] test_redeem_insufficientAmount() (gas: 66669)
[PASS] test_redeem_insufficientApprove() (gas: 142433)
[PASS] test_redeem_reentrancy() (gas: 145936)
[PASS] test_redeem_success() (gas: 140985)
[PASS] test_redeem_success_differentUser() (gas: 176995)
[PASS] test_redeem_zeroAssets() (gas: 98332)
[PASS] test_redeem_zeroShares() (gas: 53739)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 20.80ms (4.02ms CPU time)

Ran 4 tests for tests/MaplePool.t.sol:RemoveSharesTests
[PASS] test_removeShares_checkCall() (gas: 54421)
[PASS] test_removeShares_failWithoutApproval() (gas: 33201)
[PASS] test_removeShares_insufficientApproval() (gas: 72758)
[PASS] test_removeShares_withApproval() (gas: 49885)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 8.67ms (1.10ms CPU time)

Ran 6 tests for tests/MaplePool.t.sol:RequestRedeemTests
[PASS] test_requestRedeem_checkCall() (gas: 82551)
[PASS] test_requestRedeem_failWithoutApproval() (gas: 35469)
[PASS] test_requestRedeem_insufficientApproval() (gas: 107325)
[PASS] test_requestRedeem_withApproval() (gas: 77312)
[PASS] test_requestRedeem_zeroShares() (gas: 71251)
[PASS] test_requestRedeem_zeroSharesAndNotOwnerAndNoAllowance() (gas: 45966)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.19ms (1.92ms CPU time)

Ran 7 tests for tests/MaplePool.t.sol:ConvertToSharesTests
[PASS] testFuzz_convertToShares(uint256,uint256,uint256) (runs: 256, μ: 187262, ~: 189415)
[PASS] test_convertToShares_decreasedExchangeRate() (gas: 183670)
[PASS] test_convertToShares_increasedExchangeRate() (gas: 183712)
[PASS] test_convertToShares_initialExchangeRate() (gas: 183669)
[PASS] test_convertToShares_initialState() (gas: 23302)
[PASS] test_convertToShares_prematureYield() (gas: 43248)
[PASS] test_convertToShares_worthlessShares() (gas: 170960)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 350.73ms (329.96ms CPU time)

Ran 5 tests for tests/MaplePool.t.sol:RequestWithdraw
[PASS] testFuzz_requestWithdraw_failNotEnabled(uint256) (runs: 256, μ: 92740, ~: 93678)
[PASS] test_requestWithdraw_checkCall() (gas: 82617)
[PASS] test_requestWithdraw_failWithoutApproval() (gas: 45049)
[PASS] test_requestWithdraw_insufficientApproval() (gas: 125876)
[PASS] test_requestWithdraw_withApproval_failNotEnabled() (gas: 86172)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 208.31ms (174.39ms CPU time)

Ran 4 tests for tests/MaplePool.t.sol:ConvertToExitAssetsTests
[PASS] testFuzz_convertToExitAssets(uint256,uint256,uint256,uint256) (runs: 256, μ: 212844, ~: 213604)
[PASS] testFuzz_convertToExitAssets_zeroSupply(uint256) (runs: 256, μ: 8622, ~: 8622)
[PASS] test_convertToExitAssets() (gas: 233940)
[PASS] test_convertToExitAssets_zeroSupply() (gas: 13685)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 371.75ms (359.21ms CPU time)

Ran 3 tests for tests/MaplePool.t.sol:WithdrawTests
[PASS] testFuzz_withdraw_failNotEnabled(uint256) (runs: 256, μ: 33332, ~: 33332)
[PASS] test_withdraw_checkCall() (gas: 83054)
[PASS] test_withdraw_failNotEnabled() (gas: 33201)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 93.50ms (87.42ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:MaxMintTests
[PASS] testFuzz_maxMint_liquidityCap(address,address,uint256,uint256,uint256) (runs: 256, μ: 252092, ~: 251773)
[PASS] test_maxMint_liquidityCap_exchangeRateGtOne() (gas: 312997)
[PASS] test_maxMint_liquidityCap_exchangeRateOneToOne() (gas: 345305)
[PASS] test_maxMint_withPermission() (gas: 262557)
[PASS] test_maxMint_withoutPermission() (gas: 251091)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 430.65ms (391.89ms CPU time)

Ran 3 tests for tests/MaplePoolDelegateCover.t.sol:MaplePoolDelegateCoverTests
[PASS] test_moveFunds_badTransfer() (gas: 61203)
[PASS] test_moveFunds_notManager() (gas: 52195)
[PASS] test_moveFunds_success() (gas: 61763)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 9.08ms (5.64ms CPU time)

Ran 6 tests for tests/MaplePool.t.sol:DepositTests
[PASS] testFuzz_deposit_badApprove(uint256) (runs: 256, μ: 167616, ~: 167469)
[PASS] testFuzz_deposit_insufficientBalance(uint256) (runs: 256, μ: 170982, ~: 170413)
[PASS] test_deposit_checkCall() (gas: 134081)
[PASS] test_deposit_reentrancy() (gas: 186312)
[PASS] test_deposit_zeroReceiver() (gas: 111219)
[PASS] test_deposit_zeroShares() (gas: 111266)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 309.83ms (295.18ms CPU time)

Ran 2 tests for tests/MaplePoolManager.t.sol:MaxWithdrawTests
[PASS] testFuzz_maxWithdraw(address) (runs: 256, μ: 17623, ~: 17623)
[PASS] test_maxWithdraw() (gas: 17294)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 42.49ms (30.34ms CPU time)

Ran 6 tests for tests/MaplePoolDeployer.t.sol:MaplePoolDeployerTests
[PASS] test_deployPool_invalidPoolDelegate() (gas: 154104)
[PASS] test_deployPool_mismatchingArrays() (gas: 153814)
[PASS] test_deployPool_success_withCoverRequired_cyclicalWM() (gas: 5844643)
[PASS] test_deployPool_success_withCoverRequired_queueWM() (gas: 5833486)
[PASS] test_deployPool_success_withoutCoverRequired_cyclicalWM() (gas: 5781416)
[PASS] test_deployPool_transferFailed() (gas: 5677198)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 40.12ms (24.07ms CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 34102)
[PASS] test_migrate_invalidPoolDelegateCover() (gas: 39204)
[PASS] test_migrate_notFactory() (gas: 30954)
[PASS] test_migrate_paused() (gas: 54124)
[PASS] test_migrate_success() (gas: 42249)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 14.65ms (871.03µs CPU time)

Ran 4 tests for tests/MaplePoolManager.t.sol:AcceptPoolDelegate_SetterTests
[PASS] test_acceptPoolDelegate_globalsTransferFails() (gas: 61264)
[PASS] test_acceptPoolDelegate_notPendingPoolDelegate() (gas: 29878)
[PASS] test_acceptPoolDelegate_paused() (gas: 53768)
[PASS] test_acceptPoolDelegate_success() (gas: 53416)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 16.57ms (711.63µs CPU time)

Ran 5 tests for tests/MaplePoolManager.t.sol:ProcessRedeemTests
[PASS] test_processRedeem_noApproval() (gas: 47228)
[PASS] test_processRedeem_notWithdrawalManager() (gas: 36460)
[PASS] test_processRedeem_paused() (gas: 52589)
[PASS] test_processRedeem_success() (gas: 44048)
[PASS] test_processRedeem_success_notSender() (gas: 81793)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 14.81ms (1.61ms CPU time)

Ran 10 tests for tests/MaplePoolManager.t.sol:RequestFundsTests
[PASS] test_requestFunds_insufficientCoverBoundary() (gas: 227392)
[PASS] test_requestFunds_invalidFactory() (gas: 51339)
[PASS] test_requestFunds_invalidInstance() (gas: 57275)
[PASS] test_requestFunds_lockedLiquidityBoundary() (gas: 252885)
[PASS] test_requestFunds_notLM() (gas: 57966)
[PASS] test_requestFunds_paused() (gas: 36946)
[PASS] test_requestFunds_success() (gas: 126667)
[PASS] test_requestFunds_zeroAddress() (gas: 82347)
[PASS] test_requestFunds_zeroPrincipal() (gas: 45067)
[PASS] test_requestFunds_zeroSupply() (gas: 67365)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 34.27ms (16.92ms CPU time)

Ran 8 tests for tests/MaplePoolManager.t.sol:AddStrategy_SetterTests
[PASS] test_addStrategy_aumFailure() (gas: 273254)
[PASS] test_addStrategy_invalidFactory() (gas: 43824)
[PASS] test_addStrategy_notPoolDelegate() (gas: 51348)
[PASS] test_addStrategy_paused() (gas: 42306)
[PASS] test_addStrategy_success_asGovernor() (gas: 251424)
[PASS] test_addStrategy_success_asOperationalAdmin() (gas: 255782)
[PASS] test_addStrategy_success_asPoolDelegate() (gas: 246876)
[PASS] test_addStrategy_success_whenNotConfigured() (gas: 234863)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 55.34ms (37.08ms CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:SetActive_SetterTests
[PASS] test_setActive_notGlobals() (gas: 33257)
[PASS] test_setActive_paused() (gas: 52165)
[PASS] test_setActive_success() (gas: 48165)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 28.10ms (4.84ms CPU time)

Ran 7 tests for tests/MaplePoolManager.t.sol:SetDelegateManagementFeeRate_SetterTests
[PASS] test_setDelegateManagementFeeRate_notPoolDelegate() (gas: 48107)
[PASS] test_setDelegateManagementFeeRate_oob() (gas: 76141)
[PASS] test_setDelegateManagementFeeRate_paused() (gas: 56208)
[PASS] test_setDelegateManagementFeeRate_success_asGovernor() (gas: 68867)
[PASS] test_setDelegateManagementFeeRate_success_asOperationalAdmin() (gas: 74365)
[PASS] test_setDelegateManagementFeeRate_success_asPoolDelegate() (gas: 66262)
[PASS] test_setDelegateManagementFeeRate_success_whenNotConfigured() (gas: 54207)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 31.04ms (11.07ms CPU time)

Ran 26 tests for tests/MaplePoolManager.t.sol:CanCallTests
[PASS] test_canCall_depositWithPermit_lenderNotAllowed() (gas: 103752)
[PASS] test_canCall_depositWithPermit_liquidityCapExceeded() (gas: 87905)
[PASS] test_canCall_depositWithPermit_notActive() (gas: 49761)
[PASS] test_canCall_deposit_lenderNotAllowed() (gas: 102783)
[PASS] test_canCall_deposit_liquidityCapExceeded() (gas: 87478)
[PASS] test_canCall_deposit_notActive() (gas: 48997)
[PASS] test_canCall_invalidFunctionId() (gas: 43359)
[PASS] test_canCall_mintWithPermit_lenderNotAllowed() (gas: 122554)
[PASS] test_canCall_mintWithPermit_liquidityCapExceeded() (gas: 100495)
[PASS] test_canCall_mintWithPermit_notActive() (gas: 72918)
[PASS] test_canCall_mint_lenderNotAllowed() (gas: 121352)
[PASS] test_canCall_mint_liquidityCapExceeded() (gas: 99677)
[PASS] test_canCall_mint_notActive() (gas: 72077)
[PASS] test_canCall_paused_redeem() (gas: 51914)
[PASS] test_canCall_paused_removeShares() (gas: 51958)
[PASS] test_canCall_paused_requestRedeem() (gas: 51958)
[PASS] test_canCall_paused_requestWithdraw() (gas: 51893)
[PASS] test_canCall_paused_transfer() (gas: 51937)
[PASS] test_canCall_paused_withdraw() (gas: 51980)
[PASS] test_canCall_redeem() (gas: 41164)
[PASS] test_canCall_removeShares() (gas: 40655)
[PASS] test_canCall_requestRedeem() (gas: 40642)
[PASS] test_canCall_requestWithdraw() (gas: 40721)
[PASS] test_canCall_transferFrom_recipientNotAllowed() (gas: 92746)
[PASS] test_canCall_transfer_recipientNotAllowed() (gas: 91885)
[PASS] test_canCall_withdraw() (gas: 41144)
Suite result: ok. 26 passed; 0 failed; 0 skipped; finished in 87.67ms (63.31ms CPU time)

Ran 3 tests for tests/MaplePoolManager.t.sol:CompleteConfigurationTests
[PASS] test_completeConfiguration_alreadyConfigured() (gas: 34571)
[PASS] test_completeConfiguration_paused() (gas: 50988)
[PASS] test_completeConfiguration_success() (gas: 32142)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 41.38ms (558.26µs CPU time)

Ran 10 tests for tests/MaplePool.t.sol:DepositWithPermitTests
[PASS] testFuzz_depositWithPermit_insufficientBalance(uint256) (runs: 256, μ: 219840, ~: 219334)
[PASS] test_depositWithPermit_badNonce() (gas: 136062)
[PASS] test_depositWithPermit_checkCall() (gas: 154588)
[PASS] test_depositWithPermit_notStakerSignature() (gas: 137914)
[PASS] test_depositWithPermit_pastDeadline() (gas: 107731)
[PASS] test_depositWithPermit_reentrancy() (gas: 235115)
[PASS] test_depositWithPermit_replay() (gas: 241103)
[PASS] test_depositWithPermit_zeroAddress() (gas: 107184)
[PASS] test_depositWithPermit_zeroReceiver() (gas: 160129)
[PASS] test_depositWithPermit_zeroShares() (gas: 140380)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 563.76ms (541.63ms CPU time)

Ran 7 tests for tests/MaplePool.t.sol:PreviewDepositTests
[PASS] testFuzz_previewDeposit(uint256,uint256,uint256) (runs: 256, μ: 186986, ~: 189412)
[PASS] test_previewDeposit_decreasedExchangeRate() (gas: 183880)
[PASS] test_previewDeposit_increasedExchangeRate() (gas: 183902)
[PASS] test_previewDeposit_initialExchangeRate() (gas: 183904)
[PASS] test_previewDeposit_initialState() (gas: 23514)
[PASS] test_previewDeposit_prematureYield() (gas: 43437)
[PASS] test_previewDeposit_worthlessShares() (gas: 171083)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 166.69ms (154.98ms CPU time)

Ran 6 tests for tests/MaplePool.t.sol:MintTests
[PASS] testFuzz_mint_badApprove(uint256) (runs: 256, μ: 167858, ~: 167536)
[PASS] testFuzz_mint_insufficientBalance(uint256) (runs: 256, μ: 170986, ~: 170437)
[PASS] test_mint_checkCall() (gas: 136391)
[PASS] test_mint_reentrancy() (gas: 186358)
[PASS] test_mint_zeroReceiver() (gas: 111287)
[PASS] test_mint_zeroShares() (gas: 111378)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 412.69ms (393.84ms CPU time)

Ran 11 tests for tests/MaplePool.t.sol:MintWithPermitTests
[PASS] testFuzz_mintWithPermit_insufficientBalance(uint256) (runs: 256, μ: 220326, ~: 219806)
[PASS] test_mintWithPermit_badNonce() (gas: 140701)
[PASS] test_mintWithPermit_checkCall() (gas: 155087)
[PASS] test_mintWithPermit_insufficientPermit() (gas: 102421)
[PASS] test_mintWithPermit_notStakerSignature() (gas: 142515)
[PASS] test_mintWithPermit_pastDeadline() (gas: 112329)
[PASS] test_mintWithPermit_reentrancy() (gas: 235616)
[PASS] test_mintWithPermit_replay() (gas: 265508)
[PASS] test_mintWithPermit_zeroAddress() (gas: 111734)
[PASS] test_mintWithPermit_zeroReceiver() (gas: 160502)
[PASS] test_mintWithPermit_zeroShares() (gas: 160703)
Suite result: ok. 11 passed; 0 failed; 0 skipped; finished in 393.32ms (393.48ms CPU time)

Ran 7 tests for tests/MaplePoolMintFrontrunTests.t.sol:MaplePoolMintFrontrunTests
[PASS] testFuzz_depositFrontRun_honestOnePercentHarm(uint256) (runs: 256, μ: 6946126, ~: 6946505)
[PASS] testFuzz_depositFrontRun_honestTenPercentHarm(uint256) (runs: 256, μ: 6946123, ~: 6946506)
[PASS] testFuzz_depositFrontRun_theftThwarted(uint256) (runs: 256, μ: 6954652, ~: 6954762)
[PASS] test_depositFrontRun_theft() (gas: 6906977)
[PASS] test_depositFrontRun_theftReverted() (gas: 6855007)
[PASS] test_depositFrontRun_theftThwarted() (gas: 6952346)
[PASS] test_depositFrontRun_zeroShares() (gas: 6895180)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 1.84s (2.54s CPU time)

Ran 14 tests for tests/ERC20.t.sol:Pool_ERC20PermitTest
[PASS] testFuzz_permit(uint256) (runs: 256, μ: 95838, ~: 96157)
[PASS] testFuzz_permit_multiple(bytes32) (runs: 256, μ: 374236, ~: 374237)
[PASS] test_domainSeparator() (gas: 12213)
[PASS] test_initialState() (gas: 20878)
[PASS] test_permit_badS() (gas: 36122)
[PASS] test_permit_badV() (gas: 2071353)
[PASS] test_permit_differentSpender() (gas: 64699)
[PASS] test_permit_differentVerifier() (gas: 1192833)
[PASS] test_permit_earlyNonce() (gas: 64918)
[PASS] test_permit_ownerSignerMismatch() (gas: 64877)
[PASS] test_permit_replay() (gas: 102897)
[PASS] test_permit_withExpiry() (gas: 113609)
[PASS] test_permit_zeroAddress() (gas: 64684)
[PASS] test_typehash() (gas: 8906)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 2.52s (2.57s CPU time)

Ran 14 tests for tests/ERC20.t.sol:Pool_ERC20Test
[PASS] invariant_metadata() (runs: 256, calls: 128000, reverts: 69721)
[PASS] testFuzz_approve(address,uint256) (runs: 256, μ: 36960, ~: 37271)
[PASS] testFuzz_burn(address,uint256,uint256) (runs: 256, μ: 32536, ~: 2094)
[PASS] testFuzz_decreaseAllowance_infiniteApproval(address,uint256) (runs: 256, μ: 45931, ~: 45931)
[PASS] testFuzz_decreaseAllowance_nonInfiniteApproval(address,uint256,uint256) (runs: 256, μ: 50202, ~: 50151)
[PASS] testFuzz_increaseAllowance(address,uint256,uint256) (runs: 256, μ: 50267, ~: 50204)
[PASS] testFuzz_metadata(string,string,uint8) (runs: 256, μ: 1285517, ~: 1288546)
[PASS] testFuzz_mint(address,uint256) (runs: 256, μ: 59618, ~: 59929)
[PASS] testFuzz_transfer(address,uint256) (runs: 256, μ: 82865, ~: 83021)
[PASS] testFuzz_transferFrom(address,uint256,uint256) (runs: 256, μ: 516689, ~: 517187)
[PASS] testFuzz_transferFrom_infiniteApproval(address,uint256) (runs: 256, μ: 519785, ~: 519941)
[PASS] testFuzz_transferFrom_insufficientAllowance(address,uint256) (runs: 256, μ: 508441, ~: 508237)
[PASS] testFuzz_transferFrom_insufficientBalance(address,uint256) (runs: 256, μ: 489789, ~: 489653)
[PASS] testFuzz_transfer_insufficientBalance(address,uint256) (runs: 256, μ: 498827, ~: 498828)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 16.37s (18.20s CPU time)

Ran 46 test suites in 16.40s (25.35s CPU time): 292 tests passed, 0 failed, 0 skipped (292 total tests)


## pool-permission-manager

[PASS] test_fallback_noCode() (gas: 27165)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 3.09ms (251.57µs CPU time)

Ran 4 tests for tests/unit/SetPermisionAdmin.t.sol:SetPermissionAdminTests
[PASS] test_setPermissionAdmin_protocolPaused() (gas: 29220)
[PASS] test_setPermissionAdmin_success() (gas: 56673)
[PASS] test_setPermissionAdmin_success_operationalAdmin() (gas: 59970)
[PASS] test_setPermissionAdmin_unauthorized() (gas: 28863)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.04ms (552.96µs CPU time)

Ran 2 tests for tests/unit/Initialize.t.sol:InitializeTests
[PASS] test_initializer_notGovernor() (gas: 21620)
[PASS] test_initializer_success() (gas: 43137)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 2.30ms (313.43µs CPU time)

Ran 8 tests for tests/unit/SetLenderAllowlist.t.sol:SetLenderAllowlistTests
[PASS] test_setLenderAllowlist_batch() (gas: 248434)
[PASS] test_setLenderAllowlist_empty() (gas: 40724)
[PASS] test_setLenderAllowlist_mismatch() (gas: 85836)
[PASS] test_setLenderAllowlist_protocolPaused() (gas: 39426)
[PASS] test_setLenderAllowlist_success_governor() (gas: 162474)
[PASS] test_setLenderAllowlist_success_operationalAdmin() (gas: 165792)
[PASS] test_setLenderAllowlist_success_poolDelegate() (gas: 160095)
[PASS] test_setLenderAllowlist_unauthorized() (gas: 55362)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 6.75ms (2.94ms CPU time)

Ran 2 tests for tests/unit/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_success() (gas: 2901617)
[PASS] test_setImplementation_unauthorized() (gas: 11612)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 3.42ms (360.38µs CPU time)

Ran 8 tests for tests/unit/SetLenderBitmaps.t.sol:SetLenderBitmapsTests
[PASS] test_setLenderBitmaps_batch() (gas: 304199)
[PASS] test_setLenderBitmaps_empty() (gas: 32799)
[PASS] test_setLenderBitmaps_mismatch() (gas: 77936)
[PASS] test_setLenderBitmaps_protocolPaused() (gas: 34012)
[PASS] test_setLenderBitmaps_success() (gas: 153072)
[PASS] test_setLenderBitmaps_success_asGovernor() (gas: 155539)
[PASS] test_setLenderBitmaps_success_asOperationalAdmin() (gas: 158881)
[PASS] test_setLenderBitmaps_unauthorized() (gas: 35877)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 15.27ms (3.56ms CPU time)

Ran 8 tests for tests/unit/SetPoolBitmaps.t.sol:SetPoolBitmapsTests
[PASS] test_setPoolBitmaps_batch() (gas: 386761)
[PASS] test_setPoolBitmaps_empty() (gas: 37691)
[PASS] test_setPoolBitmaps_mismatch() (gas: 82725)
[PASS] test_setPoolBitmaps_protocolPaused() (gas: 36527)
[PASS] test_setPoolBitmaps_success_governor() (gas: 160814)
[PASS] test_setPoolBitmaps_success_operationalAdmin() (gas: 164156)
[PASS] test_setPoolBitmaps_success_poolDelegate() (gas: 158504)
[PASS] test_setPoolBitmaps_unauthorized() (gas: 52353)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 101.80ms (3.63ms CPU time)

Ran 8 tests for tests/unit/SetPoolPermissionLevel.t.sol:SetPoolPermissionLevelTests
[PASS] testFuzz_setPoolPermissionLevel(uint256,uint256) (runs: 256, μ: 73301, ~: 77387)
[PASS] test_setPoolPermissionLevel_invalid() (gas: 34833)
[PASS] test_setPoolPermissionLevel_protocolPaused() (gas: 31346)
[PASS] test_setPoolPermissionLevel_public() (gas: 64124)
[PASS] test_setPoolPermissionLevel_success_governor() (gas: 63625)
[PASS] test_setPoolPermissionLevel_success_operationalAdmin() (gas: 66986)
[PASS] test_setPoolPermissionLevel_success_poolDelegate() (gas: 61246)
[PASS] test_setPoolPermissionLevel_unauthorized() (gas: 47259)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 126.39ms (125.99ms CPU time)

Ran 9 tests for tests/unit/ConfigurePool.t.sol:ConfigurePoolTests
[PASS] test_configurePool_invalid() (gas: 40201)
[PASS] test_configurePool_lengthMismatch() (gas: 85219)
[PASS] test_configurePool_noFunctionIds() (gas: 40253)
[PASS] test_configurePool_protocolPaused() (gas: 36780)
[PASS] test_configurePool_public() (gas: 69601)
[PASS] test_configurePool_success_governor() (gas: 190727)
[PASS] test_configurePool_success_operationalAdmin() (gas: 194003)
[PASS] test_configurePool_success_poolDelegate() (gas: 188373)
[PASS] test_configurePool_unauthorized() (gas: 52693)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 130.08ms (2.19ms CPU time)

Ran 22 tests for tests/unit/HasPermission.t.sol:HasPermissionTests
[PASS] testFuzz_hasPermission_functionLevel_multiLender_whitelisted(address[]) (runs: 256, μ: 6876862, ~: 6463854)
[PASS] testFuzz_hasPermission_multiLender_private_whitelisted(address,address[],bytes32) (runs: 256, μ: 7152130, ~: 6968816)
[PASS] testFuzz_hasPermission_multiLender_public_(address,address[],bytes32) (runs: 256, μ: 214905, ~: 207924)
[PASS] testFuzz_hasPermission_private_unauthorized(address,address,bytes32) (runs: 256, μ: 17811, ~: 17811)
[PASS] testFuzz_hasPermission_private_whitelisted(address,address,bytes32) (runs: 256, μ: 162940, ~: 162940)
[PASS] testFuzz_hasPermission_public(address,address,bytes32) (runs: 256, μ: 65200, ~: 65200)
[PASS] test_hasPermission_functionLevel_match() (gas: 274433)
[PASS] test_hasPermission_functionLevel_mismatch() (gas: 274488)
[PASS] test_hasPermission_functionLevel_whitelisted() (gas: 190750)
[PASS] test_hasPermission_functionLevel_zeroFunctionBitmap_zeroLenderBitmap() (gas: 70352)
[PASS] test_hasPermission_functionLevel_zeroLenderBitmap() (gas: 193505)
[PASS] test_hasPermission_multiLender_functionLevel(address[]) (runs: 256, μ: 9965895, ~: 9504754)
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
Suite result: ok. 22 passed; 0 failed; 0 skipped; finished in 3.51s (10.95s CPU time)

Ran 10 test suites in 3.52s (3.90s CPU time): 72 tests passed, 0 failed, 0 skipped (72 total tests)


## strategies

Ran 3 tests for tests/unit/SetImplementation.t.sol:MapleBasicStrategySetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30369)
[PASS] test_setImplementation_protocolPaused() (gas: 36338)
[PASS] test_setImplementation_success() (gas: 42162)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 4.81ms (554.36µs CPU time)

Ran 6 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyDeactivateStrategyTests
[PASS] test_deactivateStrategy_failIfAlreadyInactive() (gas: 67346)
[PASS] test_deactivateStrategy_failIfNotProtocolAdmin() (gas: 146213)
[PASS] test_deactivateStrategy_failReentrancy() (gas: 20739)
[PASS] test_deactivateStrategy_failWhenPaused() (gas: 38954)
[PASS] test_deactivateStrategy_successWhenActive() (gas: 68247)
[PASS] test_deactivateStrategy_successWhenImpaired() (gas: 68313)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 5.96ms (1.46ms CPU time)

Ran 4 tests for tests/unit/AaveStrategy.t.sol:ClaimRewardsTests
[PASS] test_claimRewards_failIfNotProtocolAdmin() (gas: 163050)
[PASS] test_claimRewards_failReentrancy() (gas: 30962)
[PASS] test_claimRewards_failWhenPaused() (gas: 49132)
[PASS] test_claimRewards_success() (gas: 82923)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 6.05ms (1.63ms CPU time)

Ran 14 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyAccrueFeesTests
[PASS] test_accrueFees_minimumGain_realisticFeeRate() (gas: 103409)
[PASS] test_accrueFees_minimumGain_zeroFeeRate() (gas: 80876)
[PASS] test_accrueFees_minimumLoss_realisticFeeRate() (gas: 102785)
[PASS] test_accrueFees_minimumLoss_zeroFeeRate() (gas: 80911)
[PASS] test_accrueFees_normalGain_maximumFeeRate() (gas: 124170)
[PASS] test_accrueFees_normalGain_minimumFeeRate() (gas: 124371)
[PASS] test_accrueFees_normalGain_realisticFeeRate() (gas: 126692)
[PASS] test_accrueFees_normalGain_zeroFeeRate() (gas: 82997)
[PASS] test_accrueFees_normalLoss_realisticFeeRate() (gas: 104842)
[PASS] test_accrueFees_normalLoss_zeroFeeRate() (gas: 82943)
[PASS] test_accrueFees_totalLoss_realisticFeeRate() (gas: 82704)
[PASS] test_accrueFees_totalLoss_zeroFeeRate() (gas: 60806)
[PASS] test_accrueFees_unfundedStrategy_realisticFeeRate() (gas: 60784)
[PASS] test_accrueFees_unfundedStrategy_zeroFeeRate() (gas: 38954)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 8.03ms (2.62ms CPU time)

Ran 8 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyFundStrategyTests
[PASS] test_fundStrategy_successWithPoolDelegate() (gas: 130164)
[PASS] test_fundStrategy_successWithStrategyManager() (gas: 133299)
[PASS] test_fund_failIfImpaired() (gas: 70260)
[PASS] test_fund_failIfInactive() (gas: 70260)
[PASS] test_fund_failIfInvalidAavePool() (gas: 68255)
[PASS] test_fund_failIfNonManager() (gas: 56897)
[PASS] test_fund_failReentrancy() (gas: 23183)
[PASS] test_fund_failWhenPaused() (gas: 41418)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 9.50ms (2.16ms CPU time)

Ran 6 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyImpairStrategyTests
[PASS] test_impairStrategy_failIfAlreadyImpaired() (gas: 46838)
[PASS] test_impairStrategy_failIfNotProtocolAdmin() (gas: 113236)
[PASS] test_impairStrategy_failReentrancy() (gas: 17164)
[PASS] test_impairStrategy_failWhenPaused() (gas: 33855)
[PASS] test_impairStrategy_successWhenActive() (gas: 47469)
[PASS] test_impairStrategy_successWhenInactive() (gas: 47449)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 15.30ms (1.37ms CPU time)

Ran 3 tests for tests/unit/SetImplementation.t.sol:MapleCoreStrategySetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30391)
[PASS] test_setImplementation_protocolPaused() (gas: 36360)
[PASS] test_setImplementation_success() (gas: 42118)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 6.11ms (1.36ms CPU time)

Ran 6 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyImpairStrategyTests
[PASS] test_impairStrategy_failIfAlreadyImpaired() (gas: 67279)
[PASS] test_impairStrategy_failIfNotProtocolAdmin() (gas: 146143)
[PASS] test_impairStrategy_failReentrancy() (gas: 20695)
[PASS] test_impairStrategy_failWhenPaused() (gas: 38844)
[PASS] test_impairStrategy_successWhenActive() (gas: 68268)
[PASS] test_impairStrategy_successWhenInactive() (gas: 68248)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 5.71ms (1.37ms CPU time)

Ran 3 tests for tests/unit/SetImplementation.t.sol:MapleSkyStrategySetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30369)
[PASS] test_setImplementation_protocolPaused() (gas: 36338)
[PASS] test_setImplementation_success() (gas: 42098)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 5.25ms (519.74µs CPU time)

Ran 8 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyReactivateStrategyTests
[PASS] test_reactivateStrategy_failIfAlreadyActive() (gas: 45817)
[PASS] test_reactivateStrategy_failIfNotProtocolAdmin() (gas: 120733)
[PASS] test_reactivateStrategy_failReentrancy() (gas: 21136)
[PASS] test_reactivateStrategy_failWhenPaused() (gas: 39306)
[PASS] test_reactivateStrategy_successWhenImpaired_withAccountingUpdate() (gas: 65062)
[PASS] test_reactivateStrategy_successWhenImpaired_withoutAccountingUpdate() (gas: 53963)
[PASS] test_reactivateStrategy_successWhenInactive_withAccountingUpdate() (gas: 65063)
[PASS] test_reactivateStrategy_successWhenInactive_withoutAccountingUpdate() (gas: 53941)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 7.73ms (2.33ms CPU time)

Ran 18 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategySetStrategyFeeRateTests
[PASS] test_setStrategyFeeRate_failIfImpaired() (gas: 69873)
[PASS] test_setStrategyFeeRate_failIfInactive() (gas: 69873)
[PASS] test_setStrategyFeeRate_failReentrancy() (gas: 23203)
[PASS] test_setStrategyFeeRate_failWhenInvalidStrategyFeeRate() (gas: 46041)
[PASS] test_setStrategyFeeRate_failWhenNotAdmin() (gas: 51915)
[PASS] test_setStrategyFeeRate_failWhenPaused() (gas: 41440)
[PASS] test_setStrategyFeeRate_normalGain_1e6() (gas: 154092)
[PASS] test_setStrategyFeeRate_normalGain_realisticFeeRate() (gas: 156636)
[PASS] test_setStrategyFeeRate_normalGain_zeroFeeRate() (gas: 146396)
[PASS] test_setStrategyFeeRate_normalLoss_realisticFeeRate() (gas: 148362)
[PASS] test_setStrategyFeeRate_normalLoss_zeroFeeRate() (gas: 146411)
[PASS] test_setStrategyFeeRate_successWithGovernor() (gas: 88634)
[PASS] test_setStrategyFeeRate_successWithOperationalAdmin() (gas: 92919)
[PASS] test_setStrategyFeeRate_successWithPoolDelegate() (gas: 84104)
[PASS] test_setStrategyFeeRate_totalLoss_realisticFeeRate() (gas: 103963)
[PASS] test_setStrategyFeeRate_totalLoss_zeroFeeRate() (gas: 103962)
[PASS] test_setStrategyFeeRate_unfundedStrategy_realisticFeeRate() (gas: 103986)
[PASS] test_setStrategyFeeRate_unfundedStrategy_zeroFeeRate() (gas: 102011)
Suite result: ok. 18 passed; 0 failed; 0 skipped; finished in 9.88ms (5.13ms CPU time)

Ran 6 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyAccrueFeesTests
[PASS] test_accrueFees_strategyFeeOneHundredPercent() (gas: 212580)
[PASS] test_accrueFees_strategyFeeRoundedDown() (gas: 128010)
[PASS] test_accrueFees_totalAssetsDecreased() (gas: 84611)
[PASS] test_accrueFees_totalAssetsIncreased() (gas: 211910)
[PASS] test_accrueFees_zeroStrategyFeeRateAndNoChangeInTotalAssets() (gas: 43936)
[PASS] test_accrueFees_zeroStrategyFeeRate_totalAssetsIncreased() (gas: 112186)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 13.45ms (3.12ms CPU time)

Ran 7 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyPushAssetsToPoolTests
[PASS] test_pushAssetsToPool_failERC20Transfer() (gas: 59225)
[PASS] test_pushAssetsToPool_paused() (gas: 33855)
[PASS] test_pushAssetsToPool_reentrancy() (gas: 17164)
[PASS] test_pushAssetsToPool_successWhenImpaired() (gas: 95894)
[PASS] test_pushAssetsToPool_successWhenInactive() (gas: 95873)
[PASS] test_pushAssetsToPool_successWithStrategyManager() (gas: 87557)
[PASS] test_pushAssetsToPool_unauthorized() (gas: 49333)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 32.71ms (23.40ms CPU time)

Ran 6 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyDeactivateStrategyTests
[PASS] test_deactivateStrategy_failIfAlreadyInactive() (gas: 63903)
[PASS] test_deactivateStrategy_failIfNotProtocolAdmin() (gas: 138360)
[PASS] test_deactivateStrategy_failReentrancy() (gas: 17274)
[PASS] test_deactivateStrategy_failWhenPaused() (gas: 33965)
[PASS] test_deactivateStrategy_successWhenActive() (gas: 64344)
[PASS] test_deactivateStrategy_successWhenImpaired() (gas: 64410)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 10.66ms (1.40ms CPU time)

Ran 6 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyDeactivateStrategyTests
[PASS] test_deactivateStrategy_failIfAlreadyInactive() (gas: 46839)
[PASS] test_deactivateStrategy_failIfNotProtocolAdmin() (gas: 113060)
[PASS] test_deactivateStrategy_failReentrancy() (gas: 17142)
[PASS] test_deactivateStrategy_failWhenPaused() (gas: 33899)
[PASS] test_deactivateStrategy_successWhenActive() (gas: 47382)
[PASS] test_deactivateStrategy_successWhenImpaired() (gas: 47448)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 6.63ms (1.44ms CPU time)

Ran 6 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyReactivateStrategyTests
[PASS] test_reactivateStrategy_failIfAlreadyActive() (gas: 46880)
[PASS] test_reactivateStrategy_failIfNotProtocolAdmin() (gas: 113145)
[PASS] test_reactivateStrategy_failReentrancy() (gas: 17098)
[PASS] test_reactivateStrategy_failWhenPaused() (gas: 33921)
[PASS] test_reactivateStrategy_successWhenImpaired_withAccountingUpdate() (gas: 84956)
[PASS] test_reactivateStrategy_successWhenInactive_withAccountingUpdate() (gas: 84957)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.53ms (9.50ms CPU time)

Ran 8 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyFundTests
[PASS] test_fund_failIfImpaired() (gas: 64862)
[PASS] test_fund_failIfInactive() (gas: 64862)
[PASS] test_fund_failIfInvalidStrategyVault() (gas: 59154)
[PASS] test_fund_failIfNonManager() (gas: 49843)
[PASS] test_fund_failReentrancy() (gas: 4117637)
[PASS] test_fund_failWhenPaused() (gas: 34452)
[PASS] test_fund_successWithPoolDelegate() (gas: 115688)
[PASS] test_fund_successWithStrategyManager() (gas: 118867)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 12.44ms (6.86ms CPU time)

Ran 10 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyFundStrategyTests
[PASS] test_fundStrategy_with_max_value() (gas: 128645)
[PASS] test_fundStrategy_with_zero_amount() (gas: 100268)
[PASS] test_fund_failIfImpaired() (gas: 47842)
[PASS] test_fund_failIfInactive() (gas: 47820)
[PASS] test_fund_failIfNotStrategyManager() (gas: 49865)
[PASS] test_fund_failInvalidStrategyVault() (gas: 54962)
[PASS] test_fund_failReentrancy() (gas: 17675)
[PASS] test_fund_failWhenPaused() (gas: 34452)
[PASS] test_fund_successWithPoolDelegate() (gas: 133955)
[PASS] test_fund_successWithStrategyManager() (gas: 141918)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 9.88ms (2.98ms CPU time)

Ran 6 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyDeactivateStrategyTests
[PASS] test_deactivateStrategy_failIfAlreadyInactive() (gas: 63837)
[PASS] test_deactivateStrategy_failIfNotProtocolAdmin() (gas: 138220)
[PASS] test_deactivateStrategy_failReentrancy() (gas: 17230)
[PASS] test_deactivateStrategy_failWhenPaused() (gas: 33943)
[PASS] test_deactivateStrategy_successWhenActive() (gas: 64323)
[PASS] test_deactivateStrategy_successWhenImpaired() (gas: 64389)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 6.18ms (1.25ms CPU time)

Ran 6 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyImpairStrategyTests
[PASS] test_impairStrategy_failIfAlreadyImpaired() (gas: 63836)
[PASS] test_impairStrategy_failIfNotProtocolAdmin() (gas: 138290)
[PASS] test_impairStrategy_failReentrancy() (gas: 17230)
[PASS] test_impairStrategy_failWhenPaused() (gas: 33855)
[PASS] test_impairStrategy_successWhenActive() (gas: 64365)
[PASS] test_impairStrategy_successWhenInactive() (gas: 64345)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 9.29ms (1.52ms CPU time)

Ran 4 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyRemoveSharesByIdTests
[PASS] test_removeSharesById_failIfNotAuthorized() (gas: 54227)
[PASS] test_removeSharesById_failReentrancy() (gas: 24683)
[PASS] test_removeSharesById_failWhenPaused() (gas: 41351)
[PASS] test_removeSharesById_success() (gas: 62059)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 11.03ms (4.74ms CPU time)

Ran 9 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyFundStrategyTests
[PASS] test_fund_failIfImpaired() (gas: 65188)
[PASS] test_fund_failIfInactive() (gas: 65166)
[PASS] test_fund_failIfNotStrategyManager() (gas: 50257)
[PASS] test_fund_failInvalidStrategyVault() (gas: 57303)
[PASS] test_fund_failMinimumSharesOut() (gas: 65060)
[PASS] test_fund_failReentrancy() (gas: 18111)
[PASS] test_fund_failWhenPaused() (gas: 34844)
[PASS] test_fund_successWithPoolDelegate() (gas: 140398)
[PASS] test_fund_successWithStrategyManager() (gas: 148361)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 7.57ms (2.60ms CPU time)

Ran 8 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyReactivateStrategyTests
[PASS] test_reactivateStrategy_failIfAlreadyActive() (gas: 42349)
[PASS] test_reactivateStrategy_failIfNotProtocolAdmin() (gas: 110817)
[PASS] test_reactivateStrategy_failReentrancy() (gas: 17646)
[PASS] test_reactivateStrategy_failWhenPaused() (gas: 34292)
[PASS] test_reactivateStrategy_successWhenImpaired_withAccountingUpdate() (gas: 79964)
[PASS] test_reactivateStrategy_successWhenImpaired_withoutAccountingUpdate() (gas: 49559)
[PASS] test_reactivateStrategy_successWhenInactive_withAccountingUpdate() (gas: 79965)
[PASS] test_reactivateStrategy_successWhenInactive_withoutAccountingUpdate() (gas: 49537)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 10.95ms (2.44ms CPU time)

Ran 6 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyImpairStrategyTests
[PASS] test_impairStrategy_failIfAlreadyImpaired() (gas: 63748)
[PASS] test_impairStrategy_failIfNotProtocolAdmin() (gas: 138079)
[PASS] test_impairStrategy_failReentrancy() (gas: 17164)
[PASS] test_impairStrategy_failWhenPaused() (gas: 33811)
[PASS] test_impairStrategy_successWhenActive() (gas: 64322)
[PASS] test_impairStrategy_successWhenInactive() (gas: 64302)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 10.90ms (6.33ms CPU time)

Ran 6 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyRemoveSharesTests
[PASS] test_removeShares_failIfNotStrategyManager() (gas: 49886)
[PASS] test_removeShares_failReentrancy() (gas: 17696)
[PASS] test_removeShares_failWhenPaused() (gas: 34451)
[PASS] test_removeShares_successWithMaximum() (gas: 48220)
[PASS] test_removeShares_successWithMinimum() (gas: 48577)
[PASS] test_removeShares_zeroAmount() (gas: 39252)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 8.54ms (1.17ms CPU time)

Ran 8 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyReactivateStrategyTests
[PASS] test_reactivateStrategy_failIfAlreadyActive() (gas: 42305)
[PASS] test_reactivateStrategy_failIfNotProtocolAdmin() (gas: 110729)
[PASS] test_reactivateStrategy_failReentrancy() (gas: 17624)
[PASS] test_reactivateStrategy_failWhenPaused() (gas: 34292)
[PASS] test_reactivateStrategy_successWhenImpaired_withAccountingUpdate() (gas: 64559)
[PASS] test_reactivateStrategy_successWhenImpaired_withoutAccountingUpdate() (gas: 49538)
[PASS] test_reactivateStrategy_successWhenInactive_withAccountingUpdate() (gas: 64560)
[PASS] test_reactivateStrategy_successWhenInactive_withoutAccountingUpdate() (gas: 49516)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 10.36ms (2.14ms CPU time)

Ran 8 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyRequestWithdrawFromStrategyTests
[PASS] test_requestWithdrawFromStrategy_failIfNotStrategyManager() (gas: 51883)
[PASS] test_requestWithdrawFromStrategy_failIfZeroAssets() (gas: 39296)
[PASS] test_requestWithdrawFromStrategy_failReentrancy() (gas: 3463628)
[PASS] test_requestWithdrawFromStrategy_failWhenPaused() (gas: 36339)
[PASS] test_requestWithdrawFromStrategy_successWhenImpaired() (gas: 110367)
[PASS] test_requestWithdrawFromStrategy_successWhenInactive() (gas: 71998)
[PASS] test_requestWithdrawFromStrategy_successWithPoolDelegate() (gas: 105895)
[PASS] test_requestWithdrawFromStrategy_successWithStrategyManager() (gas: 107397)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 9.77ms (3.60ms CPU time)

Ran 8 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategySetPsmTests
[PASS] test_setPsm_failIfInvalidGem() (gas: 57288)
[PASS] test_setPsm_failIfInvalidUsds() (gas: 60369)
[PASS] test_setPsm_failIfNotProtocolAdmin() (gas: 331573)
[PASS] test_setPsm_failIfNotValidInstance() (gas: 69928)
[PASS] test_setPsm_failIfZeroAddress() (gas: 38783)
[PASS] test_setPsm_failReentrancy() (gas: 19844)
[PASS] test_setPsm_failWhenPaused() (gas: 36579)
[PASS] test_setPsm_success() (gas: 174068)
Suite result: ok. 8 passed; 0 failed; 0 skipped; finished in 22.06ms (14.98ms CPU time)

Ran 9 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategySetStrategyFeeRateTests
[PASS] test_setStrategyFeeRate_failIfImpaired() (gas: 64342)
[PASS] test_setStrategyFeeRate_failIfInactive() (gas: 64299)
[PASS] test_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 162957)
[PASS] test_setStrategyFeeRate_failInvalidStrategyFeeRate() (gas: 43296)
[PASS] test_setStrategyFeeRate_failReentrancy() (gas: 17739)
[PASS] test_setStrategyFeeRate_failWhenPaused() (gas: 34452)
[PASS] test_setStrategyFeeRate_nonZeroPriorFeeRate_totalAssetsIncreased() (gas: 172859)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRateAndTotalAssets() (gas: 87207)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRate_totalAssetsIncreased() (gas: 158638)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 15.10ms (3.35ms CPU time)

Ran 9 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyWithdrawFromStrategyTests
[PASS] test_withdrawFromStrategy_failIfLowAssets() (gas: 65578)
[PASS] test_withdrawFromStrategy_failIfNonManager() (gas: 56850)
[PASS] test_withdrawFromStrategy_failIfZeroAssets() (gas: 44198)
[PASS] test_withdrawFromStrategy_failReentrancy() (gas: 23224)
[PASS] test_withdrawFromStrategy_failWhenPaused() (gas: 41374)
[PASS] test_withdrawFromStrategy_successWhenImpaired() (gas: 102820)
[PASS] test_withdrawFromStrategy_successWhenInactive() (gas: 102821)
[PASS] test_withdrawFromStrategy_successWithPoolDelegate() (gas: 94801)
[PASS] test_withdrawFromStrategy_successWithStrategyManager() (gas: 98024)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 8.42ms (2.48ms CPU time)

Ran 10 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategySetStrategyFeeRateTests
[PASS] test_setStrategyFeeRate_failIfImpaired() (gas: 64386)
[PASS] test_setStrategyFeeRate_failIfInactive() (gas: 64431)
[PASS] test_setStrategyFeeRate_failIfNotProtocolAdmin() (gas: 189163)
[PASS] test_setStrategyFeeRate_failInvalidStrategyFeeRate() (gas: 41107)
[PASS] test_setStrategyFeeRate_failReentrancy() (gas: 17783)
[PASS] test_setStrategyFeeRate_failWhenPaused() (gas: 34474)
[PASS] test_setStrategyFeeRate_nonZeroPriorFeeRate_totalAssetsIncreasedWithTout() (gas: 263450)
[PASS] test_setStrategyFeeRate_nonZeroPriorFeeRate_totalAssetsIncreasedWithZeroTout() (gas: 252817)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRateAndTotalAssetsAndZeroTout() (gas: 105388)
[PASS] test_setStrategyFeeRate_zeroPriorFeeRate_totalAssetsIncreasedWithTout() (gas: 186699)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 21.12ms (7.14ms CPU time)

Ran 7 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyAccrueFeesTests
[PASS] test_accrueFees_strategyFeeOneHundredPercent() (gas: 127646)
[PASS] test_accrueFees_strategyFeeRoundedDown() (gas: 101126)
[PASS] test_accrueFees_totalAssetsDecreased() (gas: 63252)
[PASS] test_accrueFees_totalAssetsIncreased() (gas: 124915)
[PASS] test_accrueFees_zeroStrategyFeeRateAndNoChangeInTotalAssets() (gas: 30829)
[PASS] test_accrueFees_zeroStrategyFeeRate_totalAssetsIncreased() (gas: 84552)
[PASS] test_accrueFees_zeroStrategyFeeRate_totalAssetsUnchanged() (gas: 105865)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 8.94ms (2.62ms CPU time)

Ran 10 tests for tests/unit/CreateInstance.t.sol:MapleCoreStrategyCreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 415205)
[PASS] test_createInstance_invalidPoolManagerFactory() (gas: 185268)
[PASS] test_createInstance_invalidPoolManagerInstance() (gas: 181940)
[PASS] test_createInstance_invalidStrategyAsset() (gas: 830708)
[PASS] test_createInstance_invalidVaultFactory() (gas: 234693)
[PASS] test_createInstance_invalidVaultInstance() (gas: 201127)
[PASS] test_createInstance_invalidWithdrawalManagerFactory() (gas: 279560)
[PASS] test_createInstance_invalidWithdrawalManagerInstance() (gas: 217722)
[PASS] test_createInstance_success() (gas: 421493)
[PASS] test_createInstance_zeroPool() (gas: 157593)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 17.01ms (11.75ms CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MapleBasicStrategyMigrateTests
[PASS] test_migrate_internalFailure() (gas: 34308)
[PASS] test_migrate_notFactory() (gas: 30803)
[PASS] test_migrate_protocolPaused() (gas: 36774)
[PASS] test_migrate_success() (gas: 41443)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 6.05ms (674.99µs CPU time)

Ran 10 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyWithdrawFromStrategyTests
[PASS] test_withdrawFromStrategy_failIfLowAssets() (gas: 67739)
[PASS] test_withdrawFromStrategy_failIfNotStrategyManager() (gas: 52125)
[PASS] test_withdrawFromStrategy_failIfSlippage() (gas: 75689)
[PASS] test_withdrawFromStrategy_failIfZeroAssets() (gas: 39517)
[PASS] test_withdrawFromStrategy_failReentrancy() (gas: 3223776)
[PASS] test_withdrawFromStrategy_failWhenPaused() (gas: 36715)
[PASS] test_withdrawFromStrategy_successWhenImpaired() (gas: 95306)
[PASS] test_withdrawFromStrategy_successWhenInactive() (gas: 95307)
[PASS] test_withdrawFromStrategy_successWithPoolDelegate() (gas: 96013)
[PASS] test_withdrawFromStrategy_successWithStrategyManager() (gas: 97625)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 11.73ms (6.90ms CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MapleAaveStrategyMigrateTests
[PASS] test_migrate_internalFailure() (gas: 34308)
[PASS] test_migrate_notFactory() (gas: 30803)
[PASS] test_migrate_protocolPaused() (gas: 36774)
[PASS] test_migrate_success() (gas: 41487)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 8.50ms (656.25µs CPU time)

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
[PASS] test_poolDelegate() (gas: 23891)
[PASS] test_poolManager() (gas: 18315)
[PASS] test_securityAdmin() (gas: 29567)
[PASS] test_strategyState() (gas: 16092)
[PASS] test_strategyType() (gas: 15198)
[PASS] test_treasury() (gas: 29525)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 5.70ms (1.27ms CPU time)

Ran 10 tests for tests/unit/CreateInstance.t.sol:MapleSkyStrategyCreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 513632)
[PASS] test_createInstance_invalidFactory() (gas: 199223)
[PASS] test_createInstance_invalidGemPSM() (gas: 210310)
[PASS] test_createInstance_invalidInstance() (gas: 195855)
[PASS] test_createInstance_invalidPSM() (gas: 163477)
[PASS] test_createInstance_invalidSavingsUsds() (gas: 163355)
[PASS] test_createInstance_invalidUsdsPSM() (gas: 213371)
[PASS] test_createInstance_nonAuthorizedPSM() (gas: 199179)
[PASS] test_createInstance_success() (gas: 525588)
[PASS] test_createInstance_zeroPool() (gas: 163321)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 24.90ms (16.93ms CPU time)

Ran 7 tests for tests/unit/CreateInstance.t.sol:MapleAaveStrategyCreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 31209)
[PASS] test_createInstance_invalidPoolManagerFactory() (gas: 196191)
[PASS] test_createInstance_invalidPoolManagerInstance() (gas: 192841)
[PASS] test_createInstance_success() (gas: 422021)
[PASS] test_createInstance_underlyingAssetMismatch() (gas: 203244)
[PASS] test_createInstance_zeroAaveToken() (gas: 162993)
[PASS] test_createInstance_zeroPool() (gas: 162936)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 14.96ms (9.26ms CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MapleCoreStrategyMigrateTests
[PASS] test_migrate_internalFailure() (gas: 34330)
[PASS] test_migrate_notFactory() (gas: 30825)
[PASS] test_migrate_protocolPaused() (gas: 36796)
[PASS] test_migrate_success() (gas: 41509)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 16.60ms (4.80ms CPU time)

Ran 6 tests for tests/unit/CreateInstance.t.sol:MapleBasicStrategyCreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 381850)
[PASS] test_createInstance_invalidFactory() (gas: 185311)
[PASS] test_createInstance_invalidInstance() (gas: 181943)
[PASS] test_createInstance_invalidStrategyAsset() (gas: 836139)
[PASS] test_createInstance_success() (gas: 388119)
[PASS] test_createInstance_zeroPool() (gas: 157572)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.46ms (9.52ms CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MapleSkyStrategyMigrateTests
[PASS] test_migrate_internalFailure() (gas: 34330)
[PASS] test_migrate_notFactory() (gas: 30825)
[PASS] test_migrate_protocolPaused() (gas: 36796)
[PASS] test_migrate_success() (gas: 41553)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 10.86ms (1.21ms CPU time)

Ran 3 tests for tests/unit/SetImplementation.t.sol:MapleAaveStrategySetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30369)
[PASS] test_setImplementation_protocolPaused() (gas: 36338)
[PASS] test_setImplementation_success() (gas: 42141)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 15.44ms (960.76µs CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:MapleAaveStrategyUpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 123773)
[PASS] test_upgrade_notScheduled() (gas: 43201)
[PASS] test_upgrade_notSecurityAdmin() (gas: 117313)
[PASS] test_upgrade_protocolPaused() (gas: 35117)
[PASS] test_upgrade_success() (gas: 106458)
[PASS] test_upgrade_upgradeFailed() (gas: 90521)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 13.83ms (2.80ms CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:MapleBasicStrategyUpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 123597)
[PASS] test_upgrade_notScheduled() (gas: 43157)
[PASS] test_upgrade_notSecurityAdmin() (gas: 117137)
[PASS] test_upgrade_protocolPaused() (gas: 35073)
[PASS] test_upgrade_success() (gas: 99320)
[PASS] test_upgrade_upgradeFailed() (gas: 90257)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 13.94ms (6.96ms CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:MapleCoreStrategyUpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 123595)
[PASS] test_upgrade_notScheduled() (gas: 43178)
[PASS] test_upgrade_notSecurityAdmin() (gas: 117135)
[PASS] test_upgrade_protocolPaused() (gas: 35094)
[PASS] test_upgrade_success() (gas: 99209)
[PASS] test_upgrade_upgradeFailed() (gas: 90234)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 8.25ms (2.99ms CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:MapleSkyStrategyUpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 123621)
[PASS] test_upgrade_notScheduled() (gas: 43201)
[PASS] test_upgrade_notSecurityAdmin() (gas: 117161)
[PASS] test_upgrade_protocolPaused() (gas: 35117)
[PASS] test_upgrade_success() (gas: 99214)
[PASS] test_upgrade_upgradeFailed() (gas: 90237)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 11.14ms (3.49ms CPU time)

Ran 9 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyWithdrawTests
[PASS] test_withdrawFromStrategy_failIfLowAssets() (gas: 71774)
[PASS] test_withdrawFromStrategy_failIfZeroAssets() (gas: 39228)
[PASS] test_withdraw_failReentrancy() (gas: 4119499)
[PASS] test_withdraw_failsIfNotStrategyManager() (gas: 51749)
[PASS] test_withdraw_failsIfProtocolPaused() (gas: 41724)
[PASS] test_withdraw_successWhenImpaired() (gas: 111890)
[PASS] test_withdraw_successWhenInactive() (gas: 111869)
[PASS] test_withdraw_successWithPoolDelegate() (gas: 119737)
[PASS] test_withdraw_successWithStrategyManager() (gas: 124441)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 16.74ms (4.18ms CPU time)

Ran 3 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyUnrealizedLossesTests
[PASS] testFuzz_unrealizedLosses_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 100756, ~: 101110)
[PASS] testFuzz_unrealizedLosses_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 129740, ~: 130651)
[PASS] testFuzz_unrealizedLosses_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 120725, ~: 121010)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.07s (1.28s CPU time)

Ran 3 tests for tests/unit/AaveStrategy.t.sol:MapleAaveStrategyAssetsUnderManagementTests
[PASS] testFuzz_assetsUnderManagement_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 107283, ~: 108233)
[PASS] testFuzz_assetsUnderManagement_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 127319, ~: 128155)
[PASS] testFuzz_assetsUnderManagement_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 120805, ~: 121094)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.11s (1.37s CPU time)

Ran 27 tests for tests/unit/SkyStrategy.t.sol:MapleSkyStrategyViewFunctionTests
[PASS] testFuzz_assetsUnderManagement_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 143927, ~: 144074)
[PASS] testFuzz_assetsUnderManagement_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 164010, ~: 164862)
[PASS] testFuzz_assetsUnderManagement_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 140230, ~: 140647)
[PASS] testFuzz_unrealizedLosses_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 120474, ~: 120707)
[PASS] testFuzz_unrealizedLosses_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 166877, ~: 166844)
[PASS] testFuzz_unrealizedLosses_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 140361, ~: 140629)
[PASS] test_assetsUnderManagement_strategyFundedAndZeroFeeAndZeroTout() (gas: 92997)
[PASS] test_assetsUnderManagement_strategyFundedAndZeroFeeWithTout() (gas: 96663)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndLossAndTout() (gas: 141387)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndLossAndZeroTout() (gas: 137677)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndTotalAssetsIncreasedAndAndTout() (gas: 145956)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndTotalAssetsIncreasedAndZeroTout() (gas: 138499)
[PASS] test_assetsUnderManagement_strategyNotFunded() (gas: 39240)
[PASS] test_factory() (gas: 13375)
[PASS] test_fundsAsset() (gas: 13386)
[PASS] test_globals() (gas: 18944)
[PASS] test_governor() (gas: 24641)
[PASS] test_implementation() (gas: 13462)
[PASS] test_locked() (gas: 11065)
[PASS] test_pool() (gas: 13320)
[PASS] test_poolDelegate() (gas: 19026)
[PASS] test_poolManager() (gas: 13295)
[PASS] test_savingsUsds() (gas: 13403)
[PASS] test_securityAdmin() (gas: 24591)
[PASS] test_strategyState() (gas: 11072)
[PASS] test_strategyType() (gas: 10282)
[PASS] test_treasury() (gas: 24637)
Suite result: ok. 27 passed; 0 failed; 0 skipped; finished in 1.28s (2.65s CPU time)

Ran 23 tests for tests/unit/BasicStrategy.t.sol:MapleBasicStrategyViewFunctionTests
[PASS] testFuzz_assetsUnderManagement_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 107558, ~: 108270)
[PASS] testFuzz_assetsUnderManagement_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 127303, ~: 128083)
[PASS] testFuzz_assetsUnderManagement_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 116973, ~: 117325)
[PASS] testFuzz_unrealizedLosses_strategyActive(uint256,uint256,uint256) (runs: 1000, μ: 96985, ~: 97341)
[PASS] testFuzz_unrealizedLosses_strategyImpaired(uint256,uint256,uint256) (runs: 1000, μ: 127421, ~: 128297)
[PASS] testFuzz_unrealizedLosses_strategyInactive(uint256,uint256,uint256) (runs: 1000, μ: 116842, ~: 117196)
[PASS] test_assetsUnderManagement_strategyFundedAndZeroFee() (gas: 57886)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndLoss() (gas: 100565)
[PASS] test_assetsUnderManagement_strategyFundedWithFeeAndTotalAssetsIncreased() (gas: 101364)
[PASS] test_assetsUnderManagement_strategyNotFunded() (gas: 27763)
[PASS] test_factory() (gas: 13397)
[PASS] test_fundsAsset() (gas: 13297)
[PASS] test_globals() (gas: 19032)
[PASS] test_governor() (gas: 24641)
[PASS] test_implementation() (gas: 13440)
[PASS] test_locked() (gas: 10955)
[PASS] test_pool() (gas: 13365)
[PASS] test_poolDelegate() (gas: 18981)
[PASS] test_poolManager() (gas: 13317)
[PASS] test_securityAdmin() (gas: 24569)
[PASS] test_strategyType() (gas: 10304)
[PASS] test_strategyVault() (gas: 13384)
[PASS] test_treasury() (gas: 24702)
Suite result: ok. 23 passed; 0 failed; 0 skipped; finished in 1.44s (2.14s CPU time)

Ran 26 tests for tests/unit/CoreStrategy.t.sol:MapleCoreStrategyViewFunctionTests
[PASS] testFuzz_assetsUnderManagement_strategyActive(uint256,uint256,uint256,uint256) (runs: 1000, μ: 272974, ~: 272908)
[PASS] testFuzz_assetsUnderManagement_strategyImpaired(uint256,uint256,uint256,uint256) (runs: 1000, μ: 275668, ~: 276874)
[PASS] testFuzz_assetsUnderManagement_strategyInactive(uint256,uint256,uint256,uint256) (runs: 1000, μ: 255994, ~: 256187)
[PASS] testFuzz_unrealizedLosses_strategyActive(uint256) (runs: 1000, μ: 47445, ~: 47010)
[PASS] testFuzz_unrealizedLosses_strategyImpaired(uint256) (runs: 1000, μ: 80567, ~: 80313)
[PASS] testFuzz_unrealizedLosses_strategyInactive(uint256) (runs: 1000, μ: 50025, ~: 49723)
[PASS] test_assetsUnderManagement_strategyFunded() (gas: 71368)
[PASS] test_assetsUnderManagement_strategyFundedAndCash() (gas: 255661)
[PASS] test_assetsUnderManagement_strategyFundedWithSharesOnWithdrawalQueue() (gas: 208798)
[PASS] test_assetsUnderManagement_strategyFundedWithSharesOnWithdrawalQueueAndCash() (gas: 208786)
[PASS] test_assetsUnderManagement_strategyFundedWithSharesOnWithdrawalQueue_multiple_requests() (gas: 258633)
[PASS] test_assetsUnderManagement_strategyFundedWithTotalAssetsIncreased() (gas: 71345)
[PASS] test_assetsUnderManagement_strategyNotFunded() (gas: 44588)
[PASS] test_factory() (gas: 13441)
[PASS] test_fundsAsset() (gas: 13296)
[PASS] test_globals() (gas: 18988)
[PASS] test_governor() (gas: 24597)
[PASS] test_implementation() (gas: 13374)
[PASS] test_locked() (gas: 10932)
[PASS] test_pool() (gas: 13320)
[PASS] test_poolDelegate() (gas: 18894)
[PASS] test_poolManager() (gas: 13361)
[PASS] test_securityAdmin() (gas: 24525)
[PASS] test_strategyType() (gas: 10303)
[PASS] test_strategyVault() (gas: 13405)
[PASS] test_treasury() (gas: 24636)
Suite result: ok. 26 passed; 0 failed; 0 skipped; finished in 1.62s (2.46s CPU time)

Ran 71 test suites in 1.75s (7.40s CPU time): 545 tests passed, 0 failed, 0 skipped (545 total tests)


## syrup-utils

Ran 2 tests for tests/unit/MapleBorrowerActions.t.sol:MapleBorrowerActionsTests
[PASS] test_acceptLoanTerms() (gas: 24480)
[PASS] test_acceptLoanTerms_notBorrower() (gas: 22166)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 969.44µs (202.23µs CPU time)

Ran 4 tests for tests/unit/MapleRouter.t.sol:SkimTests
[PASS] test_skim_notAdmin() (gas: 30155)
[PASS] test_skim_success() (gas: 103644)
[PASS] test_skim_zeroAddress() (gas: 28542)
[PASS] test_skim_zero_amount() (gas: 36763)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 3.65ms (755.36µs CPU time)

Ran 4 tests for tests/unit/MapleRouter.t.sol:SetRouterFunctionSelectorWhitelistTests
[PASS] test_setAllowedRouterFunction_emitsEvent() (gas: 53067)
[PASS] test_setAllowedRouterFunction_notAdmin() (gas: 28044)
[PASS] test_setAllowedRouterFunction_removeMultipleFunctions() (gas: 88464)
[PASS] test_setAllowedRouterFunction_setMultipleFunctions() (gas: 91947)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.36ms (1.37ms CPU time)

Ran 7 tests for tests/unit/MapleRouter.t.sol:SetAllowedAssetsTests
[PASS] test_setAllowedAssets_addAsset() (gas: 159144)
[PASS] test_setAllowedAssets_addMultipleAssets() (gas: 214131)
[PASS] test_setAllowedAssets_lengthMismatch() (gas: 124302)
[PASS] test_setAllowedAssets_noAssets() (gas: 36861)
[PASS] test_setAllowedAssets_notAdmin() (gas: 120421)
[PASS] test_setAllowedAssets_removeAsset() (gas: 237388)
[PASS] test_setAllowedAssets_updateAssets() (gas: 334948)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 5.64ms (2.69ms CPU time)

Ran 3 tests for tests/unit/MapleRouter.t.sol:setAllowedAllowanceHolderTests
[PASS] test_setAllowedAllowanceHolder_notAdmin() (gas: 27809)
[PASS] test_setAllowedAllowanceHolder_updated() (gas: 58630)
[PASS] test_setAllowedAllowanceHolder_zeroAddress() (gas: 28358)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.28ms (470.86µs CPU time)

Ran 3 tests for tests/unit/MapleRouter.t.sol:SetAssetWhitelistingTests
[PASS] test_setAssetWhitelisting_identical() (gas: 34699)
[PASS] test_setAssetWhitelisting_notAdmin() (gas: 25196)
[PASS] test_setAssetWhitelisting_updated() (gas: 37481)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 3.47ms (613.01µs CPU time)

Ran 2 tests for tests/unit/MapleRouter.t.sol:DepositWithAlternativeAllowanceHolderTests
[PASS] test_deposit_allowance_holder_is_router() (gas: 439040)
[PASS] test_deposit_different_allowance_holder_than_router() (gas: 562275)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 6.45ms (3.62ms CPU time)

[PASS] test_constructor() (gas: 1201715)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 4.78ms (779.73µs CPU time)

Ran 6 tests for tests/unit/MplUserActions.t.sol:MplUserActionsRedeemAndMigrateAndStakeTests
[PASS] testFuzz_redeemAndMigrateAndStake() (gas: 166)
[PASS] test_redeemAndMigrateAndStake_differentReceiver() (gas: 384123)
[PASS] test_redeemAndMigrateAndStake_insufficientApproval() (gas: 51534)
[PASS] test_redeemAndMigrateAndStake_insufficientBalance() (gas: 68079)
[PASS] test_redeemAndMigrateAndStake_sameReceiver() (gas: 403570)
[PASS] test_redeemAndMigrateAndStake_zeroAmount() (gas: 14700)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.78ms (12.78ms CPU time)

Ran 4 tests for tests/unit/MapleRouter.t.sol:IsAssetAllowedTests
[PASS] test_isAssetAllowed_allAllowed() (gas: 27441)
[PASS] test_isAssetAllowed_allAllowedAgain() (gas: 235075)
[PASS] test_isAssetAllowed_multipleAllowed() (gas: 221837)
[PASS] test_isAssetAllowed_oneAllowed() (gas: 175678)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 9.46ms (1.58ms CPU time)

Ran 24 tests for tests/unit/MapleRouter.t.sol:DepositFailureTests
[PASS] test_deposit_approvalFailed() (gas: 227881)
[PASS] test_deposit_approveFail() (gas: 419921)
[PASS] test_deposit_emptyCalldata() (gas: 197062)
[PASS] test_deposit_expiredAuthorization() (gas: 357941)
[PASS] test_deposit_insufficientApproval() (gas: 121809)
[PASS] test_deposit_insufficientBalance() (gas: 173335)
[PASS] test_deposit_invalidAsset() (gas: 93367)
[PASS] test_deposit_invalidFactory() (gas: 88227)
[PASS] test_deposit_invalidInstance() (gas: 89280)
[PASS] test_deposit_invalidPermit() (gas: 131871)
[PASS] test_deposit_invalidSignature() (gas: 386344)
[PASS] test_deposit_malleableSignature_v1() (gas: 357865)
[PASS] test_deposit_malleableSignature_v2() (gas: 353636)
[PASS] test_deposit_maximumSlippage() (gas: 196253)
[PASS] test_deposit_notAllowedAllowanceHolder() (gas: 215612)
[PASS] test_deposit_notAllowedRouterFunction() (gas: 209843)
[PASS] test_deposit_notPermissionAdmin() (gas: 395607)
[PASS] test_deposit_slippageFailed() (gas: 358022)
[PASS] test_deposit_swapFailed() (gas: 271657)
[PASS] test_deposit_swapReentrancy() (gas: 67749)
[PASS] test_deposit_zeroAddressAsset() (gas: 86308)
[PASS] test_deposit_zeroAddressPoolManager() (gas: 63346)
[PASS] test_deposit_zeroAddressRouter() (gas: 196219)
[PASS] test_deposit_zeroAmount() (gas: 71614)
Suite result: ok. 24 passed; 0 failed; 0 skipped; finished in 22.34ms (18.18ms CPU time)

Ran 5 tests for tests/integration/MplUserActions.t.sol:MigrateAndStakeTests
[PASS] test_integration_migrateAndStake_insufficientApproval() (gas: 91272)
[PASS] test_integration_migrateAndStake_insufficientBalance() (gas: 53190)
[PASS] test_integration_migrateAndStake_migratorInactive() (gas: 79190)
[PASS] test_integration_migrateAndStake_success() (gas: 486154)
[PASS] test_integration_migrateAndStake_zeroAmount() (gas: 14612)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 25.50ms (9.53ms CPU time)

Ran 6 tests for tests/unit/MplUserActions.t.sol:MplUserActionsRedeemAndMigrateAndStakeWithPermitTests
[PASS] test_redeemAndMigrateAndStakeWithPermit_expiredDeadline() (gas: 45250)
[PASS] test_redeemAndMigrateAndStakeWithPermit_insufficientBalance() (gas: 115633)
[PASS] test_redeemAndMigrateAndStakeWithPermit_invalidSignature() (gas: 73348)
[PASS] test_redeemAndMigrateAndStakeWithPermit_malleable() (gas: 44711)
[PASS] test_redeemAndMigrateAndStakeWithPermit_success() (gas: 431573)
[PASS] test_redeemAndMigrateAndStakeWithPermit_zeroAmount() (gas: 39555)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 9.59ms (7.71ms CPU time)

Ran 6 tests for tests/unit/MplUserActions.t.sol:MplUserActionsMigrateAndStakeTests
[PASS] testFuzz_migrateAndStake() (gas: 187)
[PASS] test_migrateAndStake_differentReceiver() (gas: 372800)
[PASS] test_migrateAndStake_insufficientApproval() (gas: 53903)
[PASS] test_migrateAndStake_insufficientBalance() (gas: 70447)
[PASS] test_migrateAndStake_sameReceiver() (gas: 383619)
[PASS] test_migrateAndStake_zeroAmount() (gas: 14678)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 13.29ms (10.83ms CPU time)

Ran 7 tests for tests/integration/MplUserActions.t.sol:RedeemAndMigrateAndStakeWithPermitTests
[PASS] test_integration_redeemAndMigrateAndStakeWithPermit_expiredDeadline() (gas: 45353)
[PASS] test_integration_redeemAndMigrateAndStakeWithPermit_insufficientBalance() (gas: 267786)
[PASS] test_integration_redeemAndMigrateAndStakeWithPermit_invalidSignature() (gas: 73504)
[PASS] test_integration_redeemAndMigrateAndStakeWithPermit_malleable() (gas: 44924)
[PASS] test_integration_redeemAndMigrateAndStakeWithPermit_migratorInactive() (gas: 290944)
[PASS] test_integration_redeemAndMigrateAndStakeWithPermit_success() (gas: 642664)
[PASS] test_integration_redeemAndMigrateAndStakeWithPermit_zeroAmount() (gas: 39608)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 32.08ms (14.93ms CPU time)

Ran 6 tests for tests/unit/MplUserActions.t.sol:MplUserActionsRedeemAndMigrateWithPermitTests
[PASS] test_redeemAndMigrateWithPermit_expiredDeadline() (gas: 45204)
[PASS] test_redeemAndMigrateWithPermit_insufficientBalance() (gas: 115545)
[PASS] test_redeemAndMigrateWithPermit_invalidSignature() (gas: 73305)
[PASS] test_redeemAndMigrateWithPermit_malleable() (gas: 44753)
[PASS] test_redeemAndMigrateWithPermit_success() (gas: 371698)
[PASS] test_redeemAndMigrateWithPermit_zeroAmount() (gas: 39557)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 10.46ms (8.35ms CPU time)

Ran 6 tests for tests/unit/MplUserActions.t.sol:MplUserActionsRedeemAndMigrateTests
[PASS] testFuzz_redeemAndMigrate() (gas: 188)
[PASS] test_redeemAndMigrate_differentReceiver() (gas: 324225)
[PASS] test_redeemAndMigrate_insufficientApproval() (gas: 51557)
[PASS] test_redeemAndMigrate_insufficientBalance() (gas: 68146)
[PASS] test_redeemAndMigrate_sameReceiver() (gas: 339715)
[PASS] test_redeemAndMigrate_zeroAmount() (gas: 14721)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 17.32ms (10.73ms CPU time)

Ran 7 tests for tests/integration/MplUserActions.t.sol:MigrateAndStakeWithPermitTests
[PASS] test_integration_migrateAndStakeWithPermit_expiredDeadline() (gas: 40007)
[PASS] test_integration_migrateAndStakeWithPermit_insufficientBalance() (gas: 93084)
[PASS] test_integration_migrateAndStakeWithPermit_invalidSignature() (gas: 65194)
[PASS] test_integration_migrateAndStakeWithPermit_malleable() (gas: 65412)
[PASS] test_integration_migrateAndStakeWithPermit_migratorInactive() (gas: 119126)
[PASS] test_integration_migrateAndStakeWithPermit_success() (gas: 526122)
[PASS] test_integration_migrateAndStakeWithPermit_zeroAmount() (gas: 35525)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 34.27ms (17.26ms CPU time)

Ran 6 tests for tests/unit/MplUserActions.t.sol:MplUserActionsMigrateAndStakeWithPermitTests
[PASS] test_migrateAndStakeWithPermit_expiredDeadline() (gas: 45284)
[PASS] test_migrateAndStakeWithPermit_insufficientBalance() (gas: 117835)
[PASS] test_migrateAndStakeWithPermit_invalidSignature() (gas: 73360)
[PASS] test_migrateAndStakeWithPermit_malleable() (gas: 44745)
[PASS] test_migrateAndStakeWithPermit_success() (gas: 420152)
[PASS] test_migrateAndStakeWithPermit_zeroAmount() (gas: 39511)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 36.95ms (20.16ms CPU time)

Ran 5 tests for tests/integration/MplUserActions.t.sol:RedeemAndMigrateAndStakeTests
[PASS] test_integration_redeemAndMigrateAndStake_insufficientApproval() (gas: 217309)
[PASS] test_integration_redeemAndMigrateAndStake_insufficientBalance() (gas: 220179)
[PASS] test_integration_redeemAndMigrateAndStake_migratorInactive() (gas: 252913)
[PASS] test_integration_redeemAndMigrateAndStake_success() (gas: 604574)
[PASS] test_integration_redeemAndMigrateAndStake_zeroAmount() (gas: 14655)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 28.37ms (13.11ms CPU time)

Ran 10 tests for tests/unit/MapleRouter.t.sol:DepositSuccessTests
[PASS] test_deposit_withAll() (gas: 743730)
[PASS] test_deposit_withAuth() (gas: 438356)
[PASS] test_deposit_withIgnoredPermit() (gas: 387059)
[PASS] test_deposit_withPermit() (gas: 414133)
[PASS] test_deposit_withPermitAndAuth() (gas: 579040)
[PASS] test_deposit_withPermitAndSwap() (gas: 591329)
[PASS] test_deposit_withSwap() (gas: 483578)
[PASS] test_deposit_withSwapAndAuth() (gas: 610688)
[PASS] test_deposit_withSwap_withDust() (gas: 479235)
[PASS] test_deposit_withoutAnySwap() (gas: 275634)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 65.34ms (80.31ms CPU time)

Ran 5 tests for tests/integration/MplUserActions.t.sol:RedeemAndMigrateTests
[PASS] test_integration_redeemAndMigrate_insufficientApproval() (gas: 217331)
[PASS] test_integration_redeemAndMigrate_insufficientBalance() (gas: 220201)
[PASS] test_integration_redeemAndMigrate_migratorInactive() (gas: 252912)
[PASS] test_integration_redeemAndMigrate_success() (gas: 495878)
[PASS] test_integration_redeemAndMigrate_zeroAmount() (gas: 14677)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 33.35ms (13.57ms CPU time)

Ran 2 tests for tests/unit/SyrupRateProvider.t.sol:SyrupRateProviderTests
[PASS] test_constructor_success() (gas: 181883)
[PASS] test_getRate() (gas: 25875)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 1.25ms (246.82µs CPU time)

Ran 6 tests for tests/integration/SyrupDrip.t.sol:AllocateIntegrationTests
[PASS] test_allocate_expiredDeadline_governor() (gas: 28041)
[PASS] test_allocate_expiredDeadline_operationalAdmin() (gas: 32035)
[PASS] test_allocate_invalidMaxId() (gas: 109384)
[PASS] test_allocate_notAuthorized() (gas: 31232)
[PASS] test_allocate_success_governor() (gas: 105419)
[PASS] test_allocate_success_operationalAdmin() (gas: 109435)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 18.92ms (1.08ms CPU time)

Ran 5 tests for tests/unit/SyrupDrip.t.sol:SyrupDripReclaimTests
[PASS] test_reclaim_notAuthorized() (gas: 22481)
[PASS] test_reclaim_success_governor() (gas: 68905)
[PASS] test_reclaim_success_operationalAdmin() (gas: 71901)
[PASS] test_reclaim_transferFail() (gas: 31656)
[PASS] test_reclaim_zeroAmount() (gas: 20178)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 11.09ms (7.24ms CPU time)

Ran 7 tests for tests/integration/MplUserActions.t.sol:RedeemAndMigrateWithPermitTests
[PASS] test_integration_redeemAndMigrateWithPermit_expiredDeadline() (gas: 45329)
[PASS] test_integration_redeemAndMigrateWithPermit_insufficientBalance() (gas: 267719)
[PASS] test_integration_redeemAndMigrateWithPermit_invalidSignature() (gas: 73483)
[PASS] test_integration_redeemAndMigrateWithPermit_malleable() (gas: 44879)
[PASS] test_integration_redeemAndMigrateWithPermit_migratorInactive() (gas: 290944)
[PASS] test_integration_redeemAndMigrateWithPermit_success() (gas: 533951)
[PASS] test_integration_redeemAndMigrateWithPermit_zeroAmount() (gas: 39586)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 33.61ms (9.99ms CPU time)

[PASS] test_constructor() (gas: 1453582)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 4.05ms (416.11µs CPU time)

Ran 6 tests for tests/unit/SyrupDrip.t.sol:SyrupDripAllocateTests
[PASS] test_allocate_expiredDeadline_governor() (gas: 22429)
[PASS] test_allocate_expiredDeadline_operationalAdmin() (gas: 25467)
[PASS] test_allocate_invalidMaxId() (gas: 100748)
[PASS] test_allocate_notAuthorized() (gas: 24669)
[PASS] test_allocate_success_governor() (gas: 99807)
[PASS] test_allocate_success_operationalAdmin() (gas: 102867)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 9.97ms (797.88µs CPU time)

[PASS] test_scenario_drip() (gas: 741512)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 48.52ms (6.56ms CPU time)

Ran 22 tests for tests/unit/SyrupRouter.t.sol:SyrupRouterTests
[PASS] test_authorizeAndDepositWithPermit_expired() (gas: 21827)
[PASS] test_authorizeAndDepositWithPermit_malleable() (gas: 18722)
[PASS] test_authorizeAndDepositWithPermit_notPermissionAdmin() (gas: 77190)
[PASS] test_authorizeAndDepositWithPermit_success() (gas: 292699)
[PASS] test_authorizeAndDeposit_expired() (gas: 20754)
[PASS] test_authorizeAndDeposit_malleable() (gas: 17647)
[PASS] test_authorizeAndDeposit_notPermissionAdmin() (gas: 74817)
[PASS] test_authorizeAndDeposit_success() (gas: 236939)
[PASS] test_constructor_approveFails() (gas: 91197)
[PASS] test_constructor_success() (gas: 1583289)
[PASS] test_depositWithPermit_expiredDeadline() (gas: 43633)
[PASS] test_depositWithPermit_invalidSignature() (gas: 72412)
[PASS] test_depositWithPermit_notAuthorized() (gas: 107757)
[PASS] test_depositWithPermit_skipPermit() (gas: 205116)
[PASS] test_depositWithPermit_success() (gas: 230579)
[PASS] test_depositWithPermit_transferFails() (gas: 186071)
[PASS] test_depositWithPermit_transferFromFails_insufficientAmount() (gas: 125860)
[PASS] test_deposit_notAuthorized() (gas: 27447)
[PASS] test_deposit_success() (gas: 189128)
[PASS] test_deposit_transferFails() (gas: 141618)
[PASS] test_deposit_transferFromFails_insufficientAmount() (gas: 47419)
[PASS] test_deposit_transferFromFails_insufficientApproval() (gas: 58932)
Suite result: ok. 22 passed; 0 failed; 0 skipped; finished in 34.86ms (45.82ms CPU time)

Ran 5 tests for tests/integration/SyrupDrip.t.sol:ReclaimIntegrationTest
[PASS] test_reclaim_notAuthorized() (gas: 29044)
[PASS] test_reclaim_success_governor() (gas: 81079)
[PASS] test_reclaim_success_operationalAdmin() (gas: 85031)
[PASS] test_reclaim_transferFail() (gas: 40411)
[PASS] test_reclaim_zeroAmount() (gas: 25790)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 31.54ms (13.11ms CPU time)

Ran 14 tests for tests/integration/SyrupDrip.t.sol:ClaimIntegrationTests
[PASS] test_claim_alreadyClaimed() (gas: 103506)
[PASS] test_claim_expiredDeadline() (gas: 33983)
[PASS] test_claim_invalidProof_account() (gas: 35733)
[PASS] test_claim_invalidProof_amount() (gas: 35897)
[PASS] test_claim_invalidProof_id() (gas: 35886)
[PASS] test_claim_invalidProof_proof() (gas: 39332)
[PASS] test_claim_success_duplicateId() (gas: 150434)
[PASS] test_claim_success_multipleClaims() (gas: 204801)
[PASS] test_claim_success_multipleInstances() (gas: 173403)
[PASS] test_claim_success_multipleSlots() (gas: 239228)
[PASS] test_claim_success_singleClaim() (gas: 129758)
[PASS] test_claim_success_updatedAllocation() (gas: 256856)
[PASS] test_claim_success_zeroAmount() (gas: 100440)
[PASS] test_claim_transferFail() (gas: 79478)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 69.52ms (50.57ms CPU time)

Ran 15 tests for tests/unit/SyrupDrip.t.sol:SyrupDripClaimAndStakeTests
[PASS] testFuzz_claimAndStake(uint256) (runs: 1000, μ: 305473, ~: 305001)
[PASS] test_claimAndStake_alreadyClaimed() (gas: 215006)
[PASS] test_claimAndStake_expiredDeadline() (gas: 34563)
[PASS] test_claimAndStake_fullStake() (gas: 273568)
[PASS] test_claimAndStake_invalidProof_account() (gas: 36289)
[PASS] test_claimAndStake_invalidProof_amount() (gas: 36499)
[PASS] test_claimAndStake_invalidProof_id() (gas: 36465)
[PASS] test_claimAndStake_invalidProof_proof() (gas: 39889)
[PASS] test_claimAndStake_invalidStakeAmount() (gas: 26927)
[PASS] test_claimAndStake_partialStake() (gas: 299155)
[PASS] test_claimAndStake_success_multipleClaims() (gas: 419237)
[PASS] test_claimAndStake_success_multipleInstances() (gas: 355103)
[PASS] test_claimAndStake_transferFail() (gas: 72786)
[PASS] test_claimAndStake_transferToStakeFail() (gas: 188212)
[PASS] test_claimAndStake_zeroStakeAmount() (gas: 26740)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 2.56s (2.59s CPU time)

Ran 14 tests for tests/unit/SyrupDrip.t.sol:SyrupDripClaimTests
[PASS] test_claim_alreadyClaimed() (gas: 100384)
[PASS] test_claim_expiredDeadline() (gas: 33983)
[PASS] test_claim_invalidProof_account() (gas: 35733)
[PASS] test_claim_invalidProof_amount() (gas: 35897)
[PASS] test_claim_invalidProof_id() (gas: 35886)
[PASS] test_claim_invalidProof_proof() (gas: 39332)
[PASS] test_claim_success_duplicateId() (gas: 149334)
[PASS] test_claim_success_multipleClaims() (gas: 209697)
[PASS] test_claim_success_multipleInstances() (gas: 180877)
[PASS] test_claim_success_multipleSlots() (gas: 244128)
[PASS] test_claim_success_singleClaim() (gas: 128654)
[PASS] test_claim_success_updatedAllocation() (gas: 263378)
[PASS] test_claim_success_zeroAmount() (gas: 97958)
[PASS] test_claim_transferFail() (gas: 72204)
Suite result: ok. 14 passed; 0 failed; 0 skipped; finished in 2.60s (27.19ms CPU time)

Ran 15 tests for tests/integration/SyrupDrip.t.sol:ClaimAndStakeIntegrationTest
[PASS] testFuzz_claimAndStake(uint256) (runs: 1000, μ: 313456, ~: 312944)
[PASS] test_claimAndStake_alreadyClaimed() (gas: 218027)
[PASS] test_claimAndStake_expiredDeadline() (gas: 34563)
[PASS] test_claimAndStake_fullStake() (gas: 282609)
[PASS] test_claimAndStake_invalidProof_account() (gas: 36289)
[PASS] test_claimAndStake_invalidProof_amount() (gas: 36499)
[PASS] test_claimAndStake_invalidProof_id() (gas: 36465)
[PASS] test_claimAndStake_invalidProof_proof() (gas: 39889)
[PASS] test_claimAndStake_invalidStakeAmount() (gas: 26927)
[PASS] test_claimAndStake_partialStake() (gas: 308818)
[PASS] test_claimAndStake_success_multipleClaims() (gas: 433483)
[PASS] test_claimAndStake_success_multipleInstances() (gas: 366147)
[PASS] test_claimAndStake_transferFail() (gas: 80060)
[PASS] test_claimAndStake_transferToStakeFail() (gas: 195387)
[PASS] test_claimAndStake_zeroStakeAmount() (gas: 26740)
Suite result: ok. 15 passed; 0 failed; 0 skipped; finished in 2.63s (2.63s CPU time)

Ran 41 test suites in 2.71s (8.46s CPU time): 242 tests passed, 6 failed, 0 skipped (248 total tests)


## withdrawal-manager-queue

Ran 3 tests for tests/unit/MapleWithdrawalManagerMigrator.t.sol:WithdrawalManagerMigrateTests
[PASS] test_migrate_notFactory() (gas: 31188)
[PASS] test_migrate_protocolPaused() (gas: 37166)
[PASS] test_migrate_success_xxx() (gas: 684975)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 5.39ms (1.12ms CPU time)

Ran 5 tests for tests/unit/CreateInstance.t.sol:CreateInstanceTests
[PASS] test_createInstance_invalidCaller() (gas: 312348)
[PASS] test_createInstance_invalidFactory() (gas: 185844)
[PASS] test_createInstance_invalidInstance() (gas: 187024)
[PASS] test_createInstance_success() (gas: 311984)
[PASS] test_createInstance_zeroPool() (gas: 162747)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 6.94ms (2.41ms CPU time)

Ran 4 tests for tests/unit/Migrate.t.sol:MigrateTests
[PASS] test_migrate_internalFailure() (gas: 34693)
[PASS] test_migrate_notFactory() (gas: 31166)
[PASS] test_migrate_protocolPaused() (gas: 37166)
[PASS] test_migrate_success() (gas: 41020)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.71ms (598.71µs CPU time)

Ran 3 tests for tests/unit/RemoveSharesById.t.sol:RemoveSharesByIdSuccessTests
[PASS] test_removeSharesById_decrease() (gas: 297027)
[PASS] test_removeSharesById_multipleLPsWithMultipleRequests() (gas: 916084)
[PASS] test_removeSharesById_remove_request() (gas: 235653)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 10.62ms (6.15ms CPU time)

Ran 4 tests for tests/unit/PreviewRedeem.t.sol:PreviewRedeemTests
[PASS] test_previewRedeem_complete() (gas: 72722)
[PASS] test_previewRedeem_notProcessed() (gas: 21118)
[PASS] test_previewRedeem_partial() (gas: 89589)
[PASS] test_previewRedeem_tooManyShares() (gas: 44164)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 8.01ms (641.53µs CPU time)

Ran 9 tests for tests/unit/ProcessEmptyRedemptions.t.sol:ProcessEmptyRedemptionsSuccessTests
[PASS] test_processEmptyRedemptions_chunkProcessing() (gas: 1135048)
[PASS] test_processEmptyRedemptions_emptyQueueNoStateChange() (gas: 44215)
[PASS] test_processEmptyRedemptions_fullyProcessedQueueNoStateChange() (gas: 253610)
[PASS] test_processEmptyRedemptions_multipleEmptyRequests() (gas: 653049)
[PASS] test_processEmptyRedemptions_noEmptyRequests() (gas: 498840)
[PASS] test_processEmptyRedemptions_operationalAdmin() (gas: 242789)
[PASS] test_processEmptyRedemptions_poolDelegate() (gas: 252141)
[PASS] test_processEmptyRedemptions_redeemer() (gas: 245564)
[PASS] test_processEmptyRedemptions_stopsAtNonEmptyRequest() (gas: 702437)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 13.44ms (10.87ms CPU time)

Ran 4 tests for tests/unit/SetManualWithdrawal.t.sol:SetManualWithdrawalTests
[PASS] test_setManualWithdrawal_governotNotAllowed() (gas: 46121)
[PASS] test_setManualWithdrawal_notPoolDelegateOrOpsAdmin() (gas: 43468)
[PASS] test_setManualWithdrawal_protocolPaused() (gas: 37033)
[PASS] test_setManualWithdrawal_success() (gas: 73217)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 4.30ms (735.16µs CPU time)

Ran 16 tests for tests/unit/ProcessRedemptions.t.sol:ProcessRedemptionsTests
[PASS] test_processRedemptions_automatic_complete() (gas: 218520)
[PASS] test_processRedemptions_automatic_overkill() (gas: 231470)
[PASS] test_processRedemptions_automatic_partial() (gas: 301136)
[PASS] test_processRedemptions_bot() (gas: 78963)
[PASS] test_processRedemptions_governorNotAllowed() (gas: 52717)
[PASS] test_processRedemptions_lowLiquidity() (gas: 90734)
[PASS] test_processRedemptions_manual_complete() (gas: 248524)
[PASS] test_processRedemptions_manual_multipleLps_multiple_requests() (gas: 715937)
[PASS] test_processRedemptions_manual_multiple_requests() (gas: 358748)
[PASS] test_processRedemptions_manual_overkill() (gas: 263055)
[PASS] test_processRedemptions_manual_partial() (gas: 339489)
[PASS] test_processRedemptions_multiple() (gas: 369099)
[PASS] test_processRedemptions_notRedeemer() (gas: 49995)
[PASS] test_processRedemptions_poolDelegate() (gas: 76172)
[PASS] test_processRedemptions_protocolPaused() (gas: 36590)
[PASS] test_processRedemptions_zeroShares() (gas: 47407)
Suite result: ok. 16 passed; 0 failed; 0 skipped; finished in 25.15ms (20.59ms CPU time)

Ran 5 tests for tests/unit/SortedArray/Push.t.sol:PushTests
[PASS] test_push_failed_outOfOrder() (gas: 83535)
[PASS] test_push_failed_valueExists() (gas: 81436)
[PASS] test_push_failed_zeroValue() (gas: 11498)
[PASS] test_push_multipleValues_inOrder() (gas: 201721)
[PASS] test_push_singleValue() (gas: 83080)
Suite result: ok. 5 passed; 0 failed; 0 skipped; finished in 993.37µs (669.85µs CPU time)

Ran 3 tests for tests/unit/SortedArray/Remove.t.sol:RemoveTests
[PASS] test_remove_failed_valueNotExists() (gas: 11502)
[PASS] test_remove_multipleValues() (gas: 175044)
[PASS] test_remove_singleValue() (gas: 64156)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 1.06ms (705.46µs CPU time)

Ran 9 tests for tests/unit/ProcessExit.t.sol:ProcessExitTests
[PASS] test_processExit_automatic() (gas: 50973)
[PASS] test_processExit_manual_complete() (gas: 339259)
[PASS] test_processExit_manual_partial() (gas: 305388)
[PASS] test_processExit_noShares() (gas: 46623)
[PASS] test_processExit_notEnoughLiquidity() (gas: 281552)
[PASS] test_processExit_notPoolManager() (gas: 21515)
[PASS] test_processExit_tooManyShares() (gas: 50939)
[PASS] test_processExit_tooManyShares_notProcessed() (gas: 201532)
[PASS] test_processExit_transferFail() (gas: 294066)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 7.37ms (3.37ms CPU time)

Ran 4 tests for tests/unit/ProcessEmptyRedemptions.t.sol:ProcessEmptyRedemptionsFailureTests
[PASS] test_processEmptyRedemptions_governorNotAllowed() (gas: 45645)
[PASS] test_processEmptyRedemptions_notRedeemer() (gas: 45690)
[PASS] test_processEmptyRedemptions_protocolPaused() (gas: 37277)
[PASS] test_processEmptyRedemptions_zeroRequests() (gas: 42417)
Suite result: ok. 4 passed; 0 failed; 0 skipped; finished in 13.57ms (755.29µs CPU time)

Ran 6 tests for tests/unit/Upgrade.t.sol:UpgradeTests
[PASS] test_upgrade_notPoolDelegate() (gas: 125129)
[PASS] test_upgrade_notScheduled() (gas: 43911)
[PASS] test_upgrade_notSecurityAdmin() (gas: 116893)
[PASS] test_upgrade_protocolPaused() (gas: 35529)
[PASS] test_upgrade_success() (gas: 101099)
[PASS] test_upgrade_upgradeFailed() (gas: 92969)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 10.30ms (5.59ms CPU time)

Ran 6 tests for tests/unit/RemoveRequest.t.sol:RemoveRequestTests
[PASS] test_removeRequest_failedTransfer() (gas: 258500)
[PASS] test_removeRequest_multiple_requests_success() (gas: 504917)
[PASS] test_removeRequest_notAuthorized() (gas: 51939)
[PASS] test_removeRequest_notInQueue() (gas: 42504)
[PASS] test_removeRequest_protocolPaused() (gas: 37391)
[PASS] test_removeRequest_success() (gas: 263732)
Suite result: ok. 6 passed; 0 failed; 0 skipped; finished in 14.58ms (10.07ms CPU time)

Ran 9 tests for tests/unit/RemoveSharesById.t.sol:RemoveSharesByIdFailureTests
[PASS] test_removeSharesById_insufficientShares() (gas: 257548)
[PASS] test_removeSharesById_invalidRequest() (gas: 38778)
[PASS] test_removeSharesById_maxUint128Exceeded() (gas: 36884)
[PASS] test_removeSharesById_noChange() (gas: 257492)
[PASS] test_removeSharesById_notOwner() (gas: 257318)
[PASS] test_removeSharesById_protocolPaused() (gas: 38089)
[PASS] test_removeSharesById_requestAlreadyRemoved() (gas: 239292)
[PASS] test_removeSharesById_transferFail() (gas: 254599)
[PASS] test_removeSharesById_zeroRequestId() (gas: 41452)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 6.54ms (2.50ms CPU time)

Ran 9 tests for tests/unit/RemoveShares.t.sol:RemoveSharesTests
[PASS] test_removeShares_decreaseOnly() (gas: 238267)
[PASS] test_removeShares_emptyRequest() (gas: 21981)
[PASS] test_removeShares_failedTransfer() (gas: 239568)
[PASS] test_removeShares_notInQueue() (gas: 33299)
[PASS] test_removeShares_notPoolManager() (gas: 19216)
[PASS] test_removeShares_success_cancelAllRequests() (gas: 460622)
[PASS] test_removeShares_success_cancelRequest() (gas: 232357)
[PASS] test_removeShares_success_decreaseRequest() (gas: 291746)
[PASS] test_removeShares_success_partial_multipleRequests() (gas: 482843)
Suite result: ok. 9 passed; 0 failed; 0 skipped; finished in 11.32ms (5.75ms CPU time)

Ran 3 tests for tests/unit/SetImplementation.t.sol:SetImplementationTests
[PASS] test_setImplementation_notFactory() (gas: 30726)
[PASS] test_setImplementation_protocolPaused() (gas: 36746)
[PASS] test_setImplementation_success() (gas: 41679)
Suite result: ok. 3 passed; 0 failed; 0 skipped; finished in 5.30ms (460.77µs CPU time)

[PASS] test_processRedemptions_complex() (gas: 886492)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 17.95ms (5.58ms CPU time)

Ran 7 tests for tests/unit/AddShares.t.sol:AddSharesTests
[PASS] test_addShares_emptyRequest() (gas: 22003)
[PASS] test_addShares_failedTransfer() (gas: 197319)
[PASS] test_addShares_multiple_requests() (gas: 369979)
[PASS] test_addShares_newRequestAddedToQueue() (gas: 243606)
[PASS] test_addShares_newRequestAddedToQueue_manual() (gas: 268012)
[PASS] test_addShares_notPoolManager() (gas: 19325)
[PASS] test_addShares_success() (gas: 420040)
Suite result: ok. 7 passed; 0 failed; 0 skipped; finished in 45.79ms (28.20ms CPU time)

Ran 10 tests for tests/unit/ViewFunctions.t.sol:ViewFunctionsTests
[PASS] testFuzz_isInExitWindow(address) (runs: 256, μ: 11801, ~: 11801)
[PASS] test_asset() (gas: 21045)
[PASS] test_globals() (gas: 21066)
[PASS] test_governor() (gas: 26809)
[PASS] test_lockedLiquidity() (gas: 10960)
[PASS] test_lockedShares(address,uint256) (runs: 256, μ: 36379, ~: 36457)
[PASS] test_previewWithdraw(address,uint256) (runs: 256, μ: 12580, ~: 12580)
[PASS] test_requests_by_owner() (gas: 746657)
[PASS] test_requests_by_requestId() (gas: 731015)
[PASS] test_securityAdmin() (gas: 26876)
Suite result: ok. 10 passed; 0 failed; 0 skipped; finished in 37.28ms (79.16ms CPU time)

[PASS] testFuzz_removeShares(address[10],uint256[10],uint256[10]) (runs: 256, μ: 553896, ~: 538295)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 402.86ms (397.75ms CPU time)

[PASS] testFuzz_addShares(uint256[10],address[10]) (runs: 256, μ: 1884370, ~: 1884890)
Suite result: ok. 1 passed; 0 failed; 0 skipped; finished in 811.44ms (807.31ms CPU time)

Ran 2 tests for tests/integration/EndToEndTests.t.sol:EndToEndTests
[PASS] testFuzz_fullFLow_fixedExchangeRate(address[10],bool[10],uint256[10]) (runs: 256, μ: 2662144, ~: 2669480)
[PASS] test_e2e_fullFlow() (gas: 823046)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 930.57ms (930.78ms CPU time)

Ran 23 test suites in 932.72ms (2.40s CPU time): 124 tests passed, 0 failed, 0 skipped (124 total tests)
