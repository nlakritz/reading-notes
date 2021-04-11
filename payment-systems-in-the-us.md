# Payments Systems in the U.S. - Third Edition: A Guide for the Payments Professional
by Carol Coye Benson, Scott Loftesness, and Russ Jones

## Payment Systems

- Payment - a transfer of value
- sender -> receiver : funding -> completion

### Payment System
- Connects end parties
- Formalizes rules and processes
- Operates within a single country
    - Subject to government regulation

### Open Loop Payment System
- end parties -> bank -> payment system -> bank -> end parties
- Rapid scaling (when banks join, all of their end parties join)
- Complex
- Chain of liability
- On-us transaction - bank intermediary is same on both sides

### Closed Loop Payment System
- end parties -> payment system -> end parties
- Difficult to scale (system must sign up each end party individually)
- Simple; changes to the system don't have to propagate

### Chain of Liability Example
- Company's bank is responsible for providing a refund to the consumer's bank, regardless if they can regain received funds from the company (end party)
- Banks must follow payment system rules
- End parties must follow end-user agreements from their banks

### Core Payment Systems
- Checks
- ACH
- Cards
- Cash
- Wire transfer

### Terminology
- End party - both receivers and senders
- Provider - intermediaries like banks
- Payment system - general system like "card payment system"
- Payment network - specific system like "Mastercard payment network"

### Payment Domains
- Physical point of sale (POS)
- Remote commerce
    - Online shopping
    - Digital goods
- Bill payment
- P2P
    - Includes account-to-account (A2A) transfers by a single individual
- B2B
- Income payment
- Payment systems compete to control payment domains

### Push and Pull Flow
*Example*: End Party A -> Bank -> Payment System -> Bank -> End Party B

- Push - A is sending money to B
    - Wire transfer, direct deposit (ACH)
    - Not risky
    - Payer needs to know bank and account number of the payee
    - *Ex*: Direct desposit form on payroll contains this
- Pull - A is taking money from B
    - Checks, cards, ACH
    - Risky, subject to bouncing
    - Payee needs to know bank and account number of the payer
        - i.e., checks contain this
- Message flow is the same direction for both push and pull

### Settlement Types
- Gross settlement
    - Transactions are settled individually after being processed
    - No netting, money moves every time a transaction is processed
- Net settlement
    1. Transactions are exchanged among participants throughout the day.
    2. Netting occurs and participants are determined to be in net credit or net debit position (happens daily).
    3. Debit positions credit a settlement account.
    4. Settlement account credits all credit positions.
- Checking, cards, and ACH are **net settlement** systems
- Wire transfer is a **gross settlement** system

### Ownership and Regulation
- Bank-owned systems
    - ACH, Wire
- Non-bank-owned systems
    - Cards
- Non-owned systems
    - Cash, Checking

- The intermediaries (open loop) or end parties (closed loop) joining a system are bound by its rules
    - Contract between intermediary and end party in open loop is heavily influenced by system rules

### Operating Role Types
- Technical
    - Data formats, security
- Processing
    - Time limits
- Membership requirements
- Fees
- Payment acceptance requirements
- Dispute resolution

### Payment System Economic Models
- Direct revenue
    - Transaction fees, loan interest, monthly fees
    - Exception fees
        - Overdraft, bounced check, late payment
- Indirect revenue
    - Float, interchange

- Expenses include fixed and variable costs
- Revenue is often "ad valorem" (% of value)
    - Fee calculated as % of transaction amount
    - Interest on total balance
    - Float
- Interchange - a transaction fee between banks

### Risk Management
- Credit risk - a cardholder may fail to pay their balance
    - Extending an overdraft rather than bouncing incurs risk too
- Fraud
- Liquidity risk - the network is responsible for covering debts to banks if a bank in its network goes out of business
- Operation risk - broken machines, incorrect file formats, etc.
    - Often by third-parties, but their respective banks are ultimately liable
- Data security risk
- Reputational risk
- Regulatory risk - unclear interpretation of regulations

- Transferring money between countries requires two separate transactions (one in each country)
- Types of payment systems in other countries are similar, but popularity of each system varies

## Checks
- Clearing houses -> MICR and automation -> imaging
- MICR enables high-speed processing
- Checks are in decline
- Payee -> Deposit Bank (presenting bank) -> Clearing House -> Check Writer's Bank (paying bank) -> Check Writer
    - Check writer delivers physical check to payee to initialize chain

- Banks aren't required to accept electronic check images, but Check 21 states that a printed copy of a check is equivalent to the original
    - A deposit bank can send an image of the check to a printer at the check writer's bank as a workaround, if the check writer's bank doesn't accept electronic checks directly
    - Most banks take electronic images though

- No single entity owns the checking system
    - Each bank chooses how to support checking
    - Banks usually join a clearing house which sets some basic rules
    - The government sets some regulations like Check 21

- Checks are bundled with everything else for consumers and small businesses
- Enterprises must pay transaction fees when **writing** checks
- Enterprises often use lockbox services when **receiving** checks
    - Physical dedicated box at post office, person there deposits
    - Fee per transaction
    - Used by utility companies

- Remote deposit capture (RDC) may be offered to both consumers and enterprises and is either bundled or has a per-transaction fee
- Merchants that accept checks must validate them at the point of payment, and pay a per-transaction fee to banks upon deposit

- NSF Risk
    - The check writer's bank charges a NSF fee
    - When a bounced check occurs, the depository bank needs to debit its customer's account, but is at risk of them spending the money already
        - They credit their customer assuming initially, that the check will not bounce
- Fraud Risk
    - Forged on valid account: check writer's bank holds risk
    - Counterfeit on non-existent account: depository bank's responsibility

- Float (gap in funds availability)
    - Considered good when bank is receiving money and holding it for some time (wire transfer)
    - Considered bad when bank is giving money to customer before receiving it (i.e., check deposit pull payment)

## ACH
- Started out as a way to have electronic transactions fully replace paper checks
- Can be either push (ACH Credit) or pull (ACH Debit)
- Originator -> ODFI -> Operator (switcher) -> RDFI -> Receiver
    - Authorization by receiver initializes chain
1. Transaction entered into system by originator (usually an enterprise).
2. Goes to originator's bank (ODFI).
3. ODFI credits or debits the originator's account.
4. Transaction is forwarded to an operator, and there are only two that exist.
5. Operator passes transaction to receiver's bank (RDFI).
6. RDFI debits or credits the receiver's account

### ACH Settlement
- Calculated by operators daily as net settlement
- Managed by the Fed using National Settlement Service
- Zero float
    - Less processing and given priority over checks

### Ownership
- ACH is owned by the banks that belong to NACHA
- NACHA's role is to make rules and products
    - Not involved in processing
    - Low budget (banks don't pay them a tax)
    - No brand communication
- Government and NACHA rules cannot contradict each other
- NACHA rules bind ODFIs, RDFIs, and operators
- Contracts with ODFIs and RDFIs bind originators, receivers, and 3rd-parties

### Usage

- ACH transactions are classified by type using SECs
- Addenda records (supplemental info) may be included with transaction
- PPD Credit
    - Business to consumer (payroll)
- PPD Debit
    - Consumer to business (bill payment)
- PPD must be **pre-authorized** by consumer

#### Business-to-Business
- CCD Credit
    - Supplier payments
- CCD Debit
    - Trusted suppliers can debit their corporate customer's accounts
- CTX
    - Includes addenda records, CCD must send separately

#### Check Conversion
- An ACH transaction can be created to replace a check
    - Original check is destroyed
    - ACH debits the check writer's bank
    - Check regulation switches to ACH regulation
- ARC
    - Check is received at biller's lockbox, and converted
- POP
    - Check is received at point-of-sale and converted
- BOC
    - Similar to POP, but conversion occurs not in front of consumer, but in back office

#### One-Time Consumer Transactions
- Not preauthorized for ongoing use (unlike PPD)
- WEB Debit
    - Authorized by consumer over Internet, enters bank routing and account number
    - Bill payments and ecommerce
    - High risk
        - Another person's bank info could be entered
        - Insufficient funds (like always)
    - Used by PayPal
        - Micro-deposits used to verify consumer account ownership
- WEB Credit
    - P2P purchases
- CIE
    - One-time bill payment
- POS
    - Basically POP, but without a check

#### Miscellaneous Notes
- IAT is for international transactions
- While banks control ACH, WEB's approval was ultimately detrimental for them

### Risk
- ODFI is responsbile for legitimate authorization from the receiver
    - Often passes this responsibility to originator through contract
- NSF
- Payment disputes up to 60 days

- Main benefit of ACH is that it's cheap for everyone

### Products
- ODFIs compete for originator clients
- Fees are often low for large company originators
- Originators can purchase various service from banks and 3rd-parties
    - Payroll management
    - Lockbox services
    - Supplier payments (includes handling remittance data)
    - Retail point of sale ACH

- RDFIs charge small businesses for ACH receipt, but not consumers
- Banks are equipped to handle both incoming and outgoing ACH using the same "engine"
- Operators charge for both receipt and delivery of transactions

- Same-Day ACH
    - Requires all RDFIs to accept the transaction type ($0.052 interchange fee from ODFI to RDFI)
    - Settled by 5pm each day

- ACH is not international, so any IAT transactions must switch to a different payment system midway through transit when they leave the U.S.

- Merchants are at higher risk when accepting ACH payments than credit cards since you can have NSF bouncing
    - Advantage is that ACH is much cheaper per transaction

### Summary
- The ACH system can carry large amounts of data along with a transaction, and competes with card systems that are heavily branded

## Cards
- Card issuing - servicing consumers, more popular because more profitable
- Card acquiring - servicing merchants
- Card issuing banks often support both Visa and Mastercard

### History
- Visa and Mastercard are competing associations comprised of financial institutions
- Globally prominent and universally compatible through interoperability
- Profitable for banks to join, as they would gain access to products and global framework

- ATM networks were created by the banks and offered debit cards
- Visa and Mastercard weren't initially involved in ATM cards which required PINs
    - They soon developed "signature debit cards" to compete with the PIN cards
- ATM networks were bought from the banks by public company payment processors
- Visa and Mastercard went public

- Card payments were initially paper-based
    - Merchant accepting a card payment created and deposited a paper sales draft

### Card Types
- Charge cards
    - Non-revolving credit cards, meaning you need to pay the full balance every month
    - Annual fee
    - No spending limit
- Credit cards
    - Do not have to pay balance in full, can make minimum payments and then pay interest
    - Usually no annual fee
    - Spending limit
- *Signature and PIN debit cards are the same physical card*
- Signature debit cards
    - Authentication is based on signature comparison
    - Debit to account occurs slowly
    - Transactions carried over Visa or Mastercard networks
- PIN debit cards
    - PIN authentication
    - Debit to account occurs same day or day after
    - Transactions carried over ATM or PIN debit networks
- Prepaid cards
    - Access funds from a pre-funded account
    - Includes gift cards
    - May be open or closed loop

### Acceptance Environments
- Card-present
    - Physical use of card at terminal (fraud liability on issuer)
- Card-not-present
    - Remote purchase (fraud liability on merchant)
    - 3D Secure shifts fraud liability to issuer
- PIN debit
    - Can be non-present for certain things like bill payments, but usually must be present

### Payment Flow
- Open Loop Flow
    - Merchant -> Card Acquiring Bank -> Card Network -> Issuing Bank -> Card Holder
- Closed Loop Flow
    - Merchant -> Card Network -> Card Holder
- Purchase transaction from card holder initiates flow
- Closed loop is more efficient, but scales poorly
- Processors often assist aquiring and issuing banks

### The Physical Card
- Globally standardized
- Primary Account Number (PAN)
    - Engraved on card and encoded on magnetic stripe
    - Includes Issuer Identification Number (IIN)
        - Identifies card network and issuing bank
- Card Verification Number (CVN)
    - Encoded on magnetic stripe
    - Fights fraud, since a card clone cannot be created without first capturing the CVN from the original card
- CVN2 is the 3-digit code for online purchases and serves the same purpose as CVN

- Chip Cards
    - Not globally supported yet, but combats fraud
        - Not mandated in the U.S., but incentivized
    - EMV
        - Physical metal contacts
        - Requires PIN
    - RFID (contactless) cards
    - Cards can support EMV and RFID simultaneously

### Miscellaneous Notes
- Credit and signature debit transactions go through the card network twice, which allows for amount adjustments, like tips
    - Authorization message (instant speeds)
    - Clearing and settlement (batch at EOD)
- Debit transactions occur more often than credit, but in smaller amounts
- Both card networks and federal laws create regulation
    - Merchants follow some differing rules from card networks
    - The Fed aims to protect consumers
    - The Fed sets interchange for debit cards

### Card Network Responsibilities
- Transaction switching
- Net settlement among banks daily
- Operating and membership rules
    - Includes setting interchange fees
- Network membership management
- Branding
- Dispute resolution

### Card Network Economics
- Revenue comes from processing and brand-use fees on issuers
- Additional revenue from foreign exchange handling
- Sets interchange rules, but doesn't earn revenue from them
    - Higher interchange is attractive to issuers

### Card Interchange
- Costs of providing card payment services are primarily on issuers (merchant is paid even if cardholder fails to pay issuer + operating expenses)
- Interchange compensates issuers, balancing the system
- Acquirers pass the fees onto their merchant customers
    - Called a "merchant discount fee"
        - Also includes "acquiring markup" added onto interchange
    - Fee breakdown is more transparent for **larger merchants**
        - Called "interchange plus", passes actual interchange rather than estimating a value and setting a fixed rate

| Merchant | Acquiring Bank | Network | Issuing Bank | Cardholder | Notes |
|-|-|-|-|-|-|
| **+** |  |  |  | **-** | Purchase price set by merchant and paid by cardholder |
| **-** | **+** |  |  |  | Acquirer sets a merchant discount fee |
|  | **-** |  | **+** |  | Interchange |
|  | **-** | **+** | **-** |  | Network fees |
|  |  |  | **+** | **-** | Interest and fees |

- *Example*: $1.75 (interchange) + $0.15 (acquiring markup) + $0.10 (network fee) = $2 (total merchant discount fee)

- Interchange rates vary by merchant size, merchant type, transaction amount, and card type
- Closed loop networks don't have interchange
    - Network charges a "merchant discount fee" directly and keeps all the funds
- Merchants don't like interchange, but it's necessary to some degree, so that all payment system participants benefit

- Competition for issuance naturally leads to higher merchant fees unless there is some external control, like government

### Credit and Charge Cards
- Of Americans who have a credit card, most have four
- Chargebacks occur in cases of fraud or when a merchant doesn't fulfill their end of the deal
- Card Issuers
    - Determine card offerings
    - Recruit new cardholders
    - Manage credit risk
    - Debit collection
- Card Processors
    - Handle many tasks for issuers, especially small banks
    - Two largest are First Data and TSYS
- Economics
    - **Revenue**: interest (57%), interchange (17%), and fees (13%)
    - **Expenses**: operations (25%), chargeoffs (25%), and cost of funds (17%)
    - Cost of funds is interest or rewards that a bank pays out
    - Chargeoffs are unpaid debits
- Strategy
    - Some issuers are riskier and will lend to anyone, while others play it safe and stick to existing customers
    - Higher interchange cards result in more customer rewards which result in more spending at merchants

### Debit Cards
- Many transactions will be PIN debit at the POS, unless the consumer specifically requests signature, since it's usually cheaper for the merchant
- More popular than credit cards or checks
- KYC must be completed before a debit card can be issued
- People usually just have one debit card (with their primary bank)
- Economics
    - **Revenue**: overdraft fees (similar to NSF fees on checks), interchange, and net interest income (from reinvesting customer funds)
    - **Expenses**: operations, risk management, and reward programs
- Card Issuers
    - Hand out cards
    - Manage overdraft and collections
    - Outsource some processes to third-parties
- Signature debit networks include Visa and Mastercard
- PIN debit networks include Interlink (Visa), Maestro (Mastercard), STAR (First Data), and NYCE
- Reward programs are rare because there isn't much interchange revenue on debit cards to fund rewards
- Interchange is set by the government for large banks
- Debit card issuers must provide two unaffiliated debit networks on their cards, one signature and one PIN, or two PIN
- Some debit cards can use the ACH network to avoid interchange but there is NSF risk

### Prepaid Cards
- Draws on funds from a dedicated account
- Closed Loop
    - Store-specific, usually gift cards
- Open Loop
    - Network-branded, usable anywhere network is supported
    - *Ex*: government benefits, gift cards
    - Various fees
    - Issuing bank receives interchange

### Card Acquiring
- Merchant -> Acquiring -> Network
- Front-end acquiring functions include POS Vendor, ISO, Gateway, and Processor (required)
    - POS Vendor
        - Sells card acceptance terminals or software
    - ISO (Independent Sales Organization)
        - Alternative to POS Vendor, and offers some additional services
    - Gateway
        - Usually for ecommerce, this is similar to ISO
    - Front-end processor
        - Handles authorization messages
- Back-end acquiring functions include Processor and Acquiring Bank (both required)
    - Back-end processor
        - Handles settlement and clearing messages
        - Applies interchange
        - Forwards chargebacks and disputes to merchant
    - Acquiring Bank
        - Responsible to the network for the merchant's actions
- Economics
    - Acquiring revenue is mostly merchant discount fees which are \[interchange + x cents per transaction + y % of transaction]
    - Expenses
        - Fraud losses - merchant sells fraudulent goods and disappears, so a bank has to cover chargebacks
        - Credit exposure - airlines sell tickets ahead of time and could go out of business, allowing customers to receive refunds covered by the acquiring bank
- A payment facilitator acts as a middleman between small merchants and an acquirer
    - *Ex*: PayPal, Stripe, Square

### Card Risk Management
- Credit Risk
    - Credit bureaus aim to prevent credit risk
    - Credit cards the most, of charge and overdraftable debit cards also have it
- Fraud Risk
    - Stolen cards - signature and PIN to prevent
    - Duplicated cards - EMV to prevent
    - New cards stolen in mail - call activation to prevent
    - Accounts opened by fraudsters as ficticious or credible people
    - Unauthorized use in card-not-present purchases: AVS and CVV to prevent
    - PCI-DSS combats hacking of merchant and processor systems
        - Also, tokenization and encryption

## Cash
- Cash gets inserted into the conomy when a bank requests it from the Fed
- Fed -> Bank -> Vault/ATM -> End Party
- Merchants aren't required to accept cash (ex: airlines)
- ATMs often charge interchange to the user's bank if they are from a different bank or non-bank
    - User's bank will forward the interchange to the user
    - Other bank will also charge a surcharge directly to the user

## Wire Transfer
- Handles large transactions using real-time gross settlement (RTGS)
    - Mainly used by financial institutions and businesses
- Push payment
- Sender -> Sender's Bank -> Wire Network -> Receiver's Bank -> Receiver
- Fedwire
    - All national banks and some state banks have access
- CHIPS
    - Used by only a few banks
    - Owned by The Clearing House
    - Not RTGS, but still real time
- SWIFT
    - Global messaging system used to send payment-related requests and responses
- Wire cannot afford fraud to occur since the transaction amounts are so high
- Since only large banks handle wire transactions (sometimes for other banks), many are on-us and do not flow through the Fed or CHIPS

## System Users
- Consumers
    - Cash and checks are declining, while cards (especially debit) are increasing in popularity
    - Mobile payments are becoming more common
        - Carried out on underlying card systems
    - Convenience of debit and rewards of credit are the main factors of their success
    - Consumers expect systems to be secure, but extra security doesn't lead to extra adoption
    - Underbanked people like prepaid cards
- Merchants
    - Merchants like payment systems that increase revenue rather than decrease costs, like credit cards
    - Must comply with PCI-DSS
- Billers
    - May want to drive payments through their website for marketing purposes and to reduce paper costs
- Enterprises
    - Switching payment systems is a hassle
    - Often depend on multiple banks
    - Primarily use checks, which becomes complex to manage

## System Providers
- Banks
    - Three national banks are Bank of America, Chase, and Wells Fargo, accounting for 30% of national deposits
    - To start a bank, you need a charter
        - Non-banks can lend money or handle payments, but only a chartered bank can accept deposits into an account
    - 3rd-party processors allow small banks to compete with large ones, resulting in an unconcentrated market
    - Profit by lending, holding, and moving money (payments)
    - Interoperable
    - Adopt new technology frequently, but often layer it on top of core legacy systems
    - More risk = more potential profit  (credit cards)
- Networks
    - Provide rules, branding, and processing
    - Often overlap with "processors"
    - Seek volume to profit off fixed fees per transaction
- Processors
    - High volume, low prices for large clients (compose 70% of transactions)
    - Low volume, high prices for small clients (compose 50% of revenue)
    - Usually fixed fees per transaction
- Payment Service Providers
    - Examples include Western Union and PayPal
    - Communicate with end parties directly and may work with banks
- Ad valorem usually results in more profit than flat fees

## Payments Innovation
- Revolutionary innovation is uncommon, especially by existing companies; rather, evolutionary change occurs frequently for existing products and services
- Focus on the job that needs to get done, not the solution, and keep things simple




