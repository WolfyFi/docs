# WolfyFi NFT Lending Process

![WolfyFi - A Example for NFT Lending and Borrowing](../images/example_design_scheme.png)

The following diagram explains the step-by-step process of lending and borrowing NFTs on the WolfyFi platform, illustrating the interactions between the NFT owner (Bob), the dApp, the escrow contract, and the lender (Alice).

### Step 1: Bob Lists the NFT

- **Action:** Bob lists his NFT on the WolfyFi platform for a period of 2 weeks with a condition of 20 ETH.
- **Interaction:**
  - Bob -> dApp: List NFT with specified terms (20 ETH, 2 weeks + fee).
  - dApp -> Escrow: Lock NFT in the escrow contract.

### Step 2: Alice Accepts the Offer

- **Action:** Alice reviews and accepts the loan offer.
- **Interaction:**
  - Alice -> dApp: Accept the loan offer.
  - Alice ->> Bob: Transfer 20 ETH to Bob's wallet.

### Step 3: Bob Repays the Loan

- **Action:** At the end of the loan period, Bob repays the loan amount and additional fees directly to Alice.
- **Interaction:**
  - Bob -->> Alice: Repay the loan (20 ETH + fee).
  - dApp -> Escrow: Notify that repayment has been made.
  - Escrow -->> Bob: Return the NFT to Bob's wallet.

### Step 4: Non-Repayment Scenario

- **Action:** If Bob is unable to repay the loan within the agreed period.
- **Interaction:**
  - Bob -> dApp: Fail to repay the loan.
  - Escrow -->> Alice: Transfer the NFT to Alice's wallet.

This process ensures a secure and transparent transaction by utilizing smart contracts to manage the locking and transferring of NFTs and the exchange of ETH. It provides liquidity to NFT owners while allowing lenders to earn passive income. The step-by-step interaction flow ensures that the interests of both parties are protected throughout the transaction.

## Risk Assessment

One significant risk is the potential decline in the floor price of the NFT below the loan amount. This risk can manifest in two main ways:

### Decline in NFT Floor Price:

**Description:** If the floor price of the NFT falls below 20 ETH during the loan period, the value of the collateral may not cover the loan amount, leading to a potential loss for the lender.

**Impact:** In this scenario, the lender (Alice) may face a financial loss as the current market value of the NFT might be insufficient to recoup the 20 ETH loaned to the borrower (Bob).

### Borrower's Inability to Repay:

**Description:** If the borrower (Bob) is unable to repay the loan amount of 20 ETH plus any applicable gas fees by the end of the loan period, the NFT will be transferred to the lender (Alice).

**Impact:** While the lender will receive the NFT, if its market value has decreased below the loan amount, Alice might incur a loss as the NFT's sale would not cover the 20 ETH loan and associated costs.


## Managing These Risks

To mitigate these risks, the following strategies can be implemented:

- **Loan-to-Value (LTV) Ratio:** Set a loan amount that is a percentage of the NFT's floor price (e.g., 70%). This ensures that the loan is backed by sufficient collateral even if the NFT's value decreases.
- **Regular Market Monitoring:** Both lenders and borrowers should closely monitor the NFT market to stay informed about value fluctuations and potential risks.

By addressing these risks and implementing effective management strategies, both NFT owners and lenders can benefit from enhanced security and minimized potential losses, thereby increasing the utility and value of NFTs.
