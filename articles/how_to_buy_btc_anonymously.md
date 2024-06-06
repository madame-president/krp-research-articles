# How to buy Bitcoin Anonymously

This is how I would purchase bitcoin anonymously:

## Disclaimer

This is purely educational. Remember to pay your taxes and follow your national and local laws.

## Anonymity Parameters

- `Non custodial` no third party will hold my keys
- `Non KYC ` no personal information required upon registration
- `No centralized server` to leave no trace behind on a centralized database

### Step 1

- `Tor browser ` start by using a private browser. Avoid google chrome.
- `ProtonMail` get a secure email. I use ProtonMail.
- `Telegram` for private chats and messaging.
- `Burner` use this app to create a second phone number that is not linked to your main phone number.

### Step 2

- `Bisq` download Bisq's peer-to-peer network and open-source desktop software. [Bisq](https://bisq.network) is a non-KYC, non-custodial exchange, that runs and stores all my information locally. There is no centralized server.

    - *Bisq* does not store your banking information.
    - *Bisq* only handles the BTC side of the trade.
    - *Bisq* allows me to add my own payment methods, which are stored locally.

- `Account` go to the account tab, and click *Wallet Password*. Set up your password. Click *Wallet Seed* and store your wallet recovery seed phrases.

- `Account` click *National Currency Accounts* and add a new account that will serve as payment method.

    - Select *Amazon eGift Card* as payment method because they can be purchased using cash.

### Step 3

- `Security Deposit` use this link [Bitcoin ATMs](https://coinatmradar.com/bitcoin-atm-near-me/) and go to your nearest one.

- `ATM Purchase` send your freshly purchased Bitcoin to your **Bisq** wallet. This bitcoin is to be used as security deposit.

    - *For example*, if I want to buy 0.01 bitcoin, my security deposit is 0.0025 bitcoin (25%).

### Step 4

- `Generate a new address` after every purchase, *Bisq* automatically creates a new wallet addres. I can also do it manually by clicking *Generate New Addess*.

### Step 5

- `Buy Bitcoin` go to the dashboard and select and offer that accepts Amazon eGift Cards.

- `Click click click` place the order.

## Recognizing Patterns

#### Cons

- Purchase amounts are limited.
- I have to place multiple small orders.

    - *For example*, I want to purchase a total of 20 bitcoin. The limit is 2 bitcoin. I need to place 10 different orders for 2 bitcoin each.

## Audit Implications

1. **Unusual small transactions**

    - **Audit implication**: auditors would need to scrutunize the transaction history for multiple small purchases. This can indicate attempts to stay below the thresholds, which may be flagged as unusual activity.

2. **Frequent wallet changes**

    - **Audit implication**: auditors would need to examine the history of wallet addresses to ensure they match the expected patterns and do not indicate an attempt to evade scrutiny.

3. **Cash and Cash Equivalents**

    - **Audit implication**: scrutiize any large or repetitive cash outflows. Compare them with the company's typical cash usage patterns.

4. **Investments**

    - **Audit implication**: new or unexplained entires under short-term or long-term investments are a pattern. Ensure all investments are properly documented and align with the company's strategy. Check for new accounts or instruments that might facilitate anonymous transactions.

5. **Prepaid Expenses**

    - **Audit implication**: verify the legitimacy of and purpose of significant prepaid expenses.

6. **Accounts Receivable**

    - **Audit implication**: review the accounts receivable again reports and investigate any significant changes or write-offs that lack proper documentation.

7. **Other Current Assets**

    - **Audit implication**: assess the details and purposes of these assets, ensuring they are not being use to obscure the movement of funds.

### Additional patterns to look for

- `Unexplained withdrawals or transfers`
- `Discrepancies in asset valuation`

## Suggested Audit Procedures

1. **Trend Analysis**: identify irregular patterns or deviations from the norm.

2. **Reconciliation**: ensure all transactions are accounted for and legitimate by performing detailed reconciliations of bank statements, cash flow statements, and other financial records.

3. **Substantive testing**: verify the source and destination of funds used in these transactions. *Coming soon: Substative testing scripts for excel*

4. **Verification of supporting documents**: examine supporting documentation for all significant transactions, including transaction hashes, invoices, receipts, contracts.

5. **Interview key personnel**: *if needed*, interview key personnel responsible for financial transactions and cash management.