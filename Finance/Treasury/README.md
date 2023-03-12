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
