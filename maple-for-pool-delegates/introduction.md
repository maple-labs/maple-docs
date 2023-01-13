# Introduction

Pool Delegates are funds and industry professionals with credit experience. If you'd like to explore becoming a Pool Delegate, please connect with the Maple team [here.](https://maple.finance/contact/#form)

Pool Delegates have five core responsibilities, outlined below.

#### **Create Pool and Attract Funding**

Once whitelisted, Pool Delegates complete a Pool Delegate Profile to be published alongside their Lending Pool. This profile will include their background, their strategy for the Lending Pool, and the target yield.

#### **Assess New Borrowers**

Interested Borrowers create a Request for Quote (RFQ) for a loan on Maple. The RFQs are funneled to Pool Delegates who initiate conversations on terms and due diligence requirements. This involves a review of the Borrower's reputation, management background, and fund strategy. Pool Delegates may also request Borrowers provide a statement of current positions or NAV for confidential review. The Borrower's RFQ will propose terms and the Pool Delegate may make a counter-offer.

#### **Agree Terms and Fund Loan from Pool**

Once an agreement is reached between Borrower and Pool Delegate, the Borrower will create the on-chain loan request and the Pool Delegate will be able to approve a transfer of funds from their designated Lending Pool.

Funding a loan will take idle liquidity from the pool and transfer it into the a loan contract created by a borrower. Once the loan is funded the loan will be considered to be issued and will start to accrue interest.

Note that during withdrawal windows, Delegates will not be able to fund loans if the value of the request to be withdrawn in the window and the loan amount is greater than idle pool liquidity.

#### **Manage Balance in Lending Pool**

While overseeing their Lending Pool, Pool Delegates should be mindful of maintaining a sufficient stablecoin balance in the Lending Pool to enable withdrawals by Lenders.

Borrowers with outstanding loan balances can submit refinance requests to the Delegate, who can accept or deny requests. **Accepting a Refinance Proposal** will update the loan contract parameters. It is important to note that issuance date of a refinanced loan will be the date the refinance proposal was accepted.

Delegates can also call loans back early to manage lending balance by **Declaring an Early Default.** This action will accelerate a loans payment due date to the moment the transaction has been mined. There will be a grace period that needs to pass before a default may be initiated.

#### **Assist in Special Liquidations**

If a Borrower misses their repayments, the loan can be liquidated by the Maple smart contracts after a grace period. The Delegate will also move the loan to default state, which will kick off the legal recollection process. For collateralized loans, liquidations can occur on-chain or OTC to get the best price before the proceeds are transferred back to the Lending Pool.

As part of special situations management, Delegates may declare an early default or liquidate a loan. **Liquidating a Loan** will default a loan, liquidate any collateral posted on the loan and will claim First-Loss Capital posted by the delegate up to the liquidation maximum per default (set as a percentage of First-Loss Capital).
