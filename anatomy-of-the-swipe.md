# The Anatomy of the Swipe
by Ahmed Siddiqui

## Payments Ecosystem
- Issuers and acquirers each have processors. These can be either in-house or 3rd-party.
    - Examples of issuer processors include Marqeta, Tsys, Galileo, and i2c
    - Examples of acquirer processors include Chase Patmentech, Tabapay, and Fiserv
- Card -> Merchant -> Terminal -> Acquirer Processor/Acquiring Bank -> Network -> Issuer Processor/Issuing Bank
- Transactions are initiated by an acquirer processor via a gateway or PayFac
- Square is a PayFac, and Chase Paymentech is its acquirer

## Authorization
- Initiated at the payment terminal
- Places a hold on funds or declines transaction
- Frist of a dual-message; followed by Clearing
- Authorization message can be different from Clearing message (ex: tip)
- Available balance decreases, transaction marked as "pending"

## Clearing
- Happens at end of day
- Merchant confirms transactions, possibly manually
- Factors in tips, reversals, and other adjustments

## Settlement
- Funds are actually moved from Issuing Bank to Acquiring Bank
- Fees include interchange, network fee, and acquirer fee

## Chargebacks
- Occur in cases of fraud or refund disputes
- Zero liability policy protects cardholders
- Liability falls on either the Merchant or Issuer
    - Merchant can dispute the chargeback by providing documentation that either the physical card was stolen and used, or that there was no fraud at all. Either way, this would move liability onto the Issuer.
    - If EMV was supported on the card, but the Merchant doesn't use it, then the Merchant is liable
    - If transaction is online and CVV isn't requested, then the Merchant is liable
- 3D Secure aims to reduce fraud by requiring 2-factor authentication via mobile banking app
- Card networks don't pay for chargebacks
- Basically, Merchants are only liable if they don't have a secure enough process

## Card Networks
- Open loop - Visa & Mastercard
- Closed loop - American Express & Discover
- Closed loop networks issue and acquire themselves, allowing for greater revenue per transaction, but more difficult marketing reach
- Card Rails
	- Credit (dual message) requires a signature and may be done on debit cards
		- High interchange
	- PIN Debit (single message)
		- Low interchange
	- ATM
		- No fee if same as bank; if not, user and issuer both get charged
- Durbin Amendment requires debit cards support two ATM networks

|                    | Visa               | Mastercard | Discover |
|--------------------|--------------------|------------|----------|
| PIN Debit Networks | Interlink, VisaNet | Maestro    | Pulse    |
| ATM Networks       | Plus               | Cirrus     | Pulse    |

- Fees
	- Interchange - Merchant -> Issuer
	- Network Assessment - Merchant -> Network
	- Acquiring - Merchant -> Acquirer
	- Network - Acquirer -> Network &  Issuer -> Network

## Banks
- Issue cards
	- Obtain distribution license from card networks
- Merchant acquiring
- Facilitate movement of real money
- Challenger Banks
	- Tech companies that partner with regional banks
	- Exempt from maximum interchange limits (unregulated) since small
		- Interchange is majority of revenue
- Plaid allows third-party apps to access user bank data if the user provides their bank login

## Acquiring
- Merchants have two options — a PayFac or acquiring bank

- PayFac (Square, Toast)
	- Simple hardware, lots of payment methods supported ✅
	- Analytics and inventory management software ✅
	- Fraud management service ✅
	- Sub-merchant ❌
	- Higher fixed fees per transaction (PayFac needs to make money) ❌
	- Funds availability delay ❌
	
- Merchant Acquirer
	- Company name shows up on transactions, not "Square" ✅
	- No revenue limits ✅
	- Lower fees per transaction ✅
	- Not being a sub-merchant allows for discounts ✅
	- Faster funds availability ✅
	- More paperwork ❌
	- Need to manage fraud without help ❌
	- Can still use Square hardware, but not additional services like analytics ❌
	
- Payment Service Provider (Affirm, Klarna)
	- Provides a payment gateway that supports many payment methods for online purchases
	- Similar to PayFac, but merchant is still partnered with an acquiring bank and not a sub-merchant
	- Takes a cut per transaction
	
## Issuing
- Card program structure (DoorDash)
	- Cardholder - DoorDash Driver
	- Co-Brand Partner - DoorDash
	- Card Network - Mastercard
	- Issuing Bank - Wells Fargo
	- Program Manager - Marqeta
	- Issuer Processor - Marqeta

- Co-Brand Partner
	- Responsible for marketing and distribution
	- For standard cards like Chase Debit, the Issuing Bank is also the Co-Brand Partner
	
- Program Manager
	- Responsible for card inventor, settlement, fraud management, and KYC
	
- Issuer Processor
	- Handles ISO 8583 message
	- Approves or declines transactions
	- Provides APIs to allow Doordash to monitor transactions, card activation, and approve transactions in real time
	
- Economics 
	- Network - acquiring fee + issuing fee + merchant fee
	- Program Manager - majority of interchange
	- Issuing Bank - interest on funds from Co-Brand Partner + some interchange
	- Issuer Processor - some interchange
	- Co-Brand Partner - some interchange
	
- Issuer is ultimately split into the Program Manager, Co-Brand Partner, Issuing Bank, and Issuer Processor

## KYC
- KYC for digital banks is harder than in-person
- Concerned with loading funds (money laundering), not spending for prepaid cards, probably since set-price cards aren't easy to get in bulk
- Those with thin files have trouble with KYC

## Interchange
- Affected by merchant type
	- Businesses that attract high-risk customers pay higher interchange
	- Lots of revenue decreases interchange rate
- Affected by card type
	- Commercial cards (DoorDash driver card) have higher interchange
	- Co-Branded cards (Amazon card) have lower interchange
	- Private label cards (Macys card) have no interchange and only work at one store
	- Credit card interchange > Signature Debit > PIN Debit
- PIN-less debit goes on the PIN debit rail, but puts merchant at risk of fraud liability because they aren't obtaining PIN numbers even though they should be. Ultimately, they usually save more on the lower interchange rate since fraud is pretty rare.

## Alternate Electronic Payment Methods
- ACH
    - Typically used for bill payments and direct deposit
    - Cheaper than card-based transactions
    - Ability to overdraft in cases of non-sufficient funds
    - Includes peer-to-peer through apps like Venmo
        - Since ACH is slow, Venmo will need to float money for a few days to make it appear in realtime for the end user
- Zelle
    - Allows for instant transfer between certain banks via ledger transfer
- Wire
    - Very fast, used for large amounts, huge fee
- RTP
    - Uses the same technology as wire, meant for smaller amounts, low fees

## Card Innovation
- Push-to-Card
    - Allows users to receive funds instantly into their checking account through their debit card, similar to a return reimbursement
    - Branch uses push-to-card to send employee paychecks ahead of time in the form of loans
    - Tabapay allows lenders to pull funds from borrowers instantly after giving them loans through push-to-card
        - Optimizes for lowest interchange
        - Typically pulls automatically from card that was pushed to
        - Pulls from ACH if original debit card gets frozen
- Virtual Incentives offers virtual prepaid cards
- Expense Reports
    - Since expense reports allow people to go over budget if they use their own payment card, there are companies that provide business expense cards where the business can set custom limits in real time and see live spending reports

## Every company is a payments company!

