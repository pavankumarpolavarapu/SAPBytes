### Financial Instruments

Financial Instruments are monetary contracts between parties. These contracts provide a way of capital transfer for cash, ownership, debt, equity or derivatives.

#### Over-the-counter Instruments

Over-the-counter (OTC) securities are traded without being listed on an exchange. Securities that are traded over-the-counter may be facilitated by a dealer or broker specializing in OTC markets.

##### [Money Market Instruments](https://www.investopedia.com/terms/m/moneymarket.asp)

Money Market refers to trading in short term debt investments usually characterized as low risk and low rate of returns. There are various types of investments within this category

Standard Instruments
- Fixed Term Deposits
- Deposits at Notice
- Commercial Paper
- Interest Rate Instruments

Cashflow Transactions

##### Foreign Exchange Trading Instruments

- Spot Exchange Transaction (Buy/Sale of a FX for instant delivery on a spot date)
- Forward Exchange Transaction (Buy/Sale of a FX for a future date)
- Foreign Exchange Swaps (Getting a loan in FX by finding a partner who needs a loan in local currency)
- Currency Options

##### Derivative Interest Rate Instruments

- Interest Rate Swaps
- Currency Swaps
- Cross Currency Interest Rate Swaps

##### Other OTC Instruments for Stocks

- Forwards
- Swaps
- Options


#### Listed Financial Instruments

##### Securities Account Managed Financial Instruments

- Stocks
- Bonds
- Investment Fund Units
- Warrants


##### Futures Account Managed Financial Instruments

- Futures 
- Listed Options

### Electronic Bank Statements

There are multiple standard formats in which Banks send the account statement such as CAMT, MT940, BAI2 etc. MT940 is Prior Day SWIFT Standard Statement format and MT942 is Intraday SWIFT Standard Statement format. Standard Report FF_5 transaction loads these EBS into SAP and RFEBKA96 is the program using which the loaded statement can be deleted. There's a good article here [EBS](https://blogs.sap.com/2021/01/04/all-you-need-to-know-about-electronic-bank-statement-camt-054-format/). 
These statements will be loaded into SAP at line item level and categorizing them into transaction types. Standard OT83 is the transaction using which these Transaction Type mapping and payment note will be used to interpret the external transaction
type. Based on posting rules defined for each bank transaction type the bank items are matched with the company data.

#### Sample AP Journal Entries
1. Vendor Invoice

    DEBIT   GR/IR Account

    CREDIT  Vendor Recon Account


2. Payment to Vendor

    DEBIT   Vendor Recon Account

    CREDIT  Bank Outgoing Clearing Account

3. Post EBS in SAP

    DEBIT   Bank Outgoing Clearing Account

    CREDIT  Bank Main Account


#### Sample AR Journal Entries
1. Customer Invoice

    DEBIT   Customer Recon Account

    CREDIT  Revenue Account

2. Incoming Payment from Customer

    DEBIT   Bank Incoming Clearing Account

    CREDIT  Customer Recon Account

3. Post EBS in SAP

    DEBIT   Bank Main Account

    CREDIT  Bank Incoming Clearing Account

Underlying Tables for the Statements are FEBKO, FEBEP, FEBCL, FEBRE
