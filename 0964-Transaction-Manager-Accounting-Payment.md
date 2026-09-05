# Transaction Manager > Accounting > Payment - SAP TRM Knowledge Base (branch split)

One branch of output/kb_combined.md: exactly the same sections in the
same order, grouped by the authoritative SAP Help Portal table of
contents so a single topic fits in one upload. Sub-section labels appear
as **bold** inline markers.

Every section starts with a `> **Path:**` breadcrumb giving its full TOC
ancestry, level, PDF page, loio and portal link. Parse it by stripping the
leading `> `, splitting the rest on ` | ` (space-pipe-space), then the
**Path:** field on ` > ` (space-angle-space) -- never naively on `>`.
No TOC title contains a `>` character, so the grammar is unambiguous and
the full ancestry is always present (nothing elided).

Sections sharing a title with another page under a different parent are
numbered in the heading (e.g. `Payment Details (2 of 4)`); the breadcrumb
tells you which one you are in.

##### Payment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment | L4 | trm07 p.54 | loio `7cb80952852a9a60e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7cb80952852a9a60e10000000a44176d.html?locale=en-US)

**Use**

If transactions are concluded with a business partner that does not have a house bank account but whose bank details are known and each transaction will not be paid actively, you can generate payment requests that will be processed through the enhanced payment program. This allows you to settle transactions collectively if they have been grouped together.

**Example:**

Examples of when to use the payment program:

Several transactions are concluded with a business partner that is not a house bank;

When you post to the fixed-term deposit balance sheet account, you generate payment requests at the same time;

All transactions are managed on the payment request clearing account;

All transactions can be brought together/netted;

When the time of payment arrives, a payment run is triggered in accounting and the payment amount is posted to the bank clearing account;

A payment medium is generated at the same time, and this is passed on to the house bank;

Posting to the bank account takes place when you receive the account statement the next day.

**Features**

To trigger a payment, you can choose between two payment programs:

- 1. The standard payment program from FI settles Open Items from the accounts receivable/payable area.

- 2. The extended payment program also covers G/L accounts. Unlike the standard payment program, the open items (FI documents) are not the basis for payment but rather the Payment Requests.

###### SEPA Direct Debits in TRM

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > SEPA Direct Debits in TRM | L5 | trm07 p.55 | loio `d5ff4252ba5f1b13e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d5ff4252ba5f1b13e10000000a44176d.html?locale=en-US)

**Use**

If you make transactions in the Single European Payments Area (SEPA) and have been granted the rights to make SEPA direct debits for incoming payments from financial transactions in the Transaction Manager, you can set this up in the system by making the settings described here.

**Prerequisites**

To be able to make SEPA direct debits for incoming payments, you must first make settings in Customizing as well as in the master data.

Customizing

Under Financial Accounting (New) Accounts Receivable and Accounts Payable Business Transactions Incoming Payments Management of SEPA Mandates General Settings , you need to make the following settings:

Activate SEPA mandate management for the application Financial Accounting.

**Note:**

Treasury and Risk Management uses the same SEPA application (F Financial Accounting) as Financial Accounting and Loans Management.

Under Function Modules for Data Enhancement and Checks, you need to enter the function module FI_APAR_CUSTOMIZING_DEFAULTS in the Parameters field.

Under Other Parameters, you need to enter the function module FI_APAR_MANDATE_GEN_CONTRACTS in the column alongside the parameter Function Module for Control of Contract Types.

Under Financial Accounting (New) Accounts Receivable and Accounts Payable Business Transactions Incoming Payments Automatic Incoming Payments Payment Method/Bank Selection for Payment Program Set Up Paying Company Codes for Payment Transactions , you have to enter the Creditor Identification Number of the company code

for each of your paying company codes in the Specifications for SEPA Payments area.

Under Financial Accounting (New) Accounts Receivable and Accounts Payable Business Transactions Incoming Payments Automatic Incoming Payments Payment Method/Bank Selection for Payment Program Set Up Payment Methods for Each Country/Region for Payment Transactions , you need to ensure that a payment method for the SAP direct debit has been assigned for the country/region of the company code. For this payment method, the SEPA Mandate Required and IBAN Required indicators must be set in the Required Master Record Specifications area.

Under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Payment Management SEPA Activation per Company Code (TRM) , you also need to activate the use of SEPA functions in Treasury and Risk Management for the paying company codes.

Master Data

Customers for your business partners

For use of Treasury and Risk Management, it was previously not necessary for you to have created customers corresponding to your business partners (see also: Customer). If, however, you now want to obtain your incoming payments using SEPA direct debit, you need to have customers for your business partners in the Counterparty role.

The customer needs to be assigned to the business partner in the counterparty data on the Customer - General tab.

Methods for assigning customers to business partners:

Manual assignment using the Maintain Business Partner function (transaction BP)

Create a customer (see also: Creating a Customer Master Record) and then assign the customer to the business partner (transaction BP) in the Counterparty role on the Customer: General tab, or create the customer from the business partner data.

Using the Link Business Partner to Customer function (transaction FLBPD2)

(See also: Assignment of a Customer/Vendor)

See also: Master Data Synchronization (customer-vendor integration)

Entering Bank Details in Business Partner Master Data

On the Payment Transactions tab in the Bank Details area, you need to specify the IBAN for all bank accounts.

SEPA Mandates

On the Payment Transactions tab in the Bank Details area, you can use the FI SEPA Mandates pushbutton to display, change, or create SEPA mandates for bank accounts. See also: Maintaining Mandates in Payment Data Processing

Apart from the business partner master data, you can use the following functions for SEPA mandates: Create Mandate (transaction FSEPA_M1), Change Mandate (transaction FSEPA_M2), Display Mandate (transaction FSEPA_M3), and List of Mandates (transaction FSEPA_M4). See also: Creating, Displaying, and Changing Mandates

**Note:**

Ensure that you create the SEPA mandates for the application Financial Accounting. If the system does not show the fields Customer (= payer) and Paying Company Code (= payee) on the initial screens for these functions, you can switch to the application Financial Accounting by choosing Switch Application.

You can create a generic mandate for the business partner or a mandate that is only valid for a specific financial transaction. For this, select the contract type (such as Derivatives) in the Contract Identification area and enter the financial transaction number in the Contract ID field.

**Activities**

Using SEPA Mandates in Financial Transactions in Treasury and Risk Management

When you create or change a financial transaction (in transactions FTR_CREATE and FTR_EDIT), assign the SEPA mandate in the Mandate Reference field on the Payment Details tab in the details for incoming payments in currency EUR in the Payment area and select the payment method for SEPA direct debits. In the Control area, select With Payment Request and/or Posting to Customer.

**Note:**

If you want the payment program to net the payments of your financial transactions, you also need to enter the SEPA mandate for outgoing payments in currency EUR in the payment details because the payment program can only net payments that also match in the SEPA mandate.

###### Open Items

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Open Items | L5 | trm07 p.57 | loio `f321d553088f4308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f321d553088f4308e10000000a174cb4.html?locale=en-US)

Use

**Note:**

For information on this topic, see the FI documentation (accounts receivable and accounts payable): Executing the Payment Program and Processing Open Items.

###### Payment Requests

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Requests | L5 | trm07 p.57 | loio `16767d531efc7e0de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/16767d531efc7e0de10000000a4450e5.html?locale=en-US)

**Use**

You use this function (transaction F111) to start the Payment Program for Payment Requests. The payment program for payment requests is an additional automatic payment option in the SAP system. Unlike the standard payment program, the payments are not based on open items (customer items) but on payment requests.

**Integration**

You use the Payment Program for Payment Requests in the Money Market, Foreign Exchange, Derivatives, and Securities areas of Treasury and Risk Management and in Loans Management in the Bank Applications area.

Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market/Foreign Exchange/Securities/Derivatives Accounting Payment Payment Request


Accounting Bank Applications Loans Management Accounting Receivables/Payment Management Generate Payments Automatic Payment Transactions - Payment Request


Accounting Financial Accounting Banks Outgoings Automatic Payment Payment Requests


**Note:**

You can also use a BAdI (technical name TPM_EXT_PAYMENT_TRPR) to make payments for payment requests using another payment program (such as In-House Cash). The BAdI is available in Customizing for the Transaction Manager under General Settings Payment Management Payment Requests Customer Payment Programs .

See also:

Connection of Transaction Manager to In-House Cash

**Prerequisites**

Before you can use the Payment Program for Payment Requests, you are required to make certain settings in Customizing for the Transaction Manager (TRM) in addition to settings for configuring the payment program.

Money Market, Foreign Exchange, Derivatives, and Securities Areas

You have entered a number range for key number assignment of payment requests in Customizing for Treasury and Risk Management under Transaction Manager General Settings Payment Management Payment Requests Define Number Ranges for Payment Requests .

You have set up the planning levels for payment requests in Customizing for Cash and Liquidity Management under Master Data G/L Accounts Define Planning Levels .

You have created the clearing account in the chart of accounts and assigned it to the company code in Customizing for TRM under Transaction Manager General Settings Payment Management Payment Requests Define Clearing Account for Payment Requests .

You have set the Payment Request indicator for the individual flow types in the IMG activity Define Flow Types. This activity can be found in Customizing for the Transaction Manager in the areas Money Market, Foreign Exchange, Derivatives, and Securities. In this way, you specify whether payment requests can be generated for flow types.

You can choose from the following:

|Character|Create payment request?|
|---|---|
| |None|
|-|For outgoing payments|
|+|For incoming payments|
|X|For outgoing and incoming payments|


Notes on Generating Payment Requests in these Areas

If you want to generate payment requests for transactions with a business partner, you can define these in the standing instructions for the business partner payment details. To do this, set the Payment Request indicator in the standing instructions of the payment details and enter at least one payment method in the List of Payment Methods field. These settings are the default values for the payment details for each transaction with the business partner.

You make the final decision as to whether to generate a payment request when you actually enter the transaction. If you do not want to generate a payment request, you can overwrite the default values from the standing instructions in the payment details for the transaction.

In a transaction, one payment request is generated for each flow. If you use the functions from the Public Sector area, one payment request is generated for each account assignment.

**Note:**

In the relevant posting record, the bank clearing account is exchanged for the clearing account for payment requests. The Payment Program for Payment Requests makes the clearing posting from the clearing account for payment requests to the original bank clearing account.

Grouping Payment Requests

You can group payment requests with the payment program as long as the following fields match:

Business Area

Company Code

Business Partner

Payment Currency

Value Date: Recipient

Payee (bank details in the item)

Payment Method

Contents of the grouping fields (Grouping field and Same Direction field). The Grouping field contains the key for the Netting function, for example. In addition, you can use the Group Determination field in the payment details to specify what is entered in the Grouping field. The field may be predefined for the individual business partners when the Standing Instructions for the Payment Details were defined in the business partner master data.

The contents of the Same Direction field is also written to the Grouping field for the payment request.

You cannot make single payments.

The payment request must be released to make the payment.

No payment blocks can be set.

Example of a Payment Block

If transactions are grouped with the netting function, they can then only be paid together. If one of the transactions has already been posted but the other has not, then a payment block is set. The block is undone once the second transaction is posted in the netting transaction.

Loans Area

For more information on the settings in the "Loans" area, see Payment Request.

Other Settings

You have made the required settings for the payment program in Customizing (see Customizing the Payment Program).

Call the Payment Program for Payment Requests (transaction "F111"). Choose Environment Maintain Configuration to make your Customizing settings for the payment program.

**Activities**

To start a payment run, call the Payment Program for Payment Requests (transaction F111). The Automatic Payment Transactions for Payment Requests screen appears.

- 1. Enter a date and a payment run ID.


All information relating to the payment run is stored under these values.

- 2. Choose Edit Parameters Maintain Payment Run Parameters . The Automatic Payment Transactions: Parameters screen appears.

Enter the values for the parameters.

- 3. The Dynamic Selections function gives you the option of using other fields for selecting payment requests.
- 4. You can create an additional log by choosing Additional Log.
- 5. Save the parameters for the payment run.
- 6. To generate a proposal run or a payment run, choose Edit Proposal Schedule or Edit Payment Schedule .

Specify a starting time (or set the Immediate Start indicator) and a computer, if required.

- 7. If you create a proposal, you can display the log, payment list, and exception list. You can edit or delete the payment proposal. If you are satisfied with this payment proposal, choose Edit Payment Schedule and execute the update run.
- 8. After the payment run, the system generates the posting documents, the payment and exceptions lists, and the payment media.


**More Information**

In the documentation for the Payment Program for Payment Requests (FI-BL), see the sections on Executing the Payment Program.

###### Payment Program for Payment Requests (FI-BL)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) | L5 | trm07 p.60 | loio `5c04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5c04c5536a51204be10000000a174cb4.html?locale=en-US)

**Purpose**

The payment program for payment requests is an additional automatic payment option in the SAP system. You can use this payment program to make payments to customers and vendors, or between G/L accounts. Unlike the standard payment program, the payments are not based on open items (FI documents) but on payment requests.

**Features**

The functions of the payment program include:

Payment processing

Allows you to control the selection of the payment requests, posts and clears the corresponding documents in the system, and generates the payment media

Payments in third currencies

Update of payment data in Cash Management

###### Payment Request

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Payment Request | L6 | trm07 p.60 | loio `f003c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f003c5536a51204be10000000a174cb4.html?locale=en-US)

Definition

Document for generating payment media. The system usually generates payment requests automatically when it posts the flows due. The payments are then made individually or jointly using the payment program for payment requests.

**Use**

You can create payment requests from various applications (such as FI, Treasury, HR). They must not necessarily be linked to an accounting document. The modules for generating and changing payment requests also incorporate the Cash Management update. Since payment requests have different origins, you access the functions for generating, changing and reversing them in the applications. The same applies for the lists of "open payment requests". When a payment request is generated, the payment data (payment amounts and due dates) is already known. This data is expected by the payment program, which does not support due date calculation and cash discount processing.

If you make a payment via a G/L account, you must specify all the data relevant for the payment in the payment request. If you make a payment via customer or supplier account, you can let the payment program determine the payment control parameters, the payment method, and the bank details.

**Structure**

You can define the following payment data in the payment request:

Payer (company code)

Payment amounts and currencies (in local currency, document currency, and payment currency)

Business partner (customer, supplier, or G/L account)

Address data of the business partner and the payment recipient (alternative payment recipient and branch)

Bank data of the payment recipient and the house bank, and possible payment procedures

Other correspondence banks and intermediate banks

Due dates and value dates (the system uses the value date of the receiving bank to calculate the value date of the house bank). You make the corresponding settings in Customizing. In the Value Date section, you define the difference in days between the value date of the house bank and the partner bank (Define Diff. in Days Betw. Value Date of House/Partner Bank). You also need to specify the relevant calendar for the currency, country and region (Define Factory Calendar per Currency).

Assignment to an accounting document

Various control parameters

###### Procedure: Payment Program for Payment Requests

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Procedure: Payment Program for Payment Requests | L6 | trm07 p.61 | loio `f303c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f303c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The payment program covers the whole process of handling of payments from controlling the selection of payment requests up to the creation of payment media.

**Prerequisites**

Settings for the payment program (Customizing)

In large parts, the same Customizing functions as in the standard payment program are used. This is especially the case with control of payment medium creation, company codes, payment methods and house banks.

Some additional functions for controlling the payment program for payment requests are provided, for example, when defining house bank accounts and G/L account determination. The user can define the number of accounts per bank, currency and payment method for settling G/L account payments (such as bank account transfers).

The payment program can be used at the same time as the standard payment program.

**Procedure**

In order to ensure clarity and to minimize the amount of work, there is a strong link to the standard payment program.

Connectivity and procedure:

Standard payment program and payment program for payment requests

[figure TRM07-F021 - Standard payment program and payment program for payment requests]

The payment run parameters are the input parameters. Here, you enter the selection conditions for selecting payment requests and the control parameters. In the case of payment transactions with suppliers and customers, you can also access control data from the master records (see Selection of Payment Requests, Grouping of Payments and Payment Method and Bank Determination).

You can firstly create a payment proposal in the payment run. In order to process the payment proposals, you use the corresponding part of the payment program. When processing the proposals, the payment procedures and banks proposed by the payment program can be changed. Items for payment can also be blocked and/or payment blocks can be lifted.

In the update run, the payment data is created directly or on the basis of a proposal run and the corresponding postings and clearings take place in the system (see Posting and Clearing).

The standard payment program functions are used for payment medium creation and management. This includes creation of the payment medium forms and data media as well as data medium exchange and check management. Alongside proposal processing and payment medium creation, large parts of standard Customizing are used. This ensures that the control parameters are clear.

###### Selection of Payment Requests (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Procedure: Payment Program for Payment Requests > Selection of Payment Requests | L7 | trm07 p.63 | loio `f603c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f603c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The grouping of all payment requests due on a certain key date takes place via selection.

**Functions**

The selection of payment requests to be settled in a payment run takes place on the basis of the payment run parameters predefined by the user and certain control parameters in the payment requests.

Examples of payment run parameters include:

Parties liable to pay (company codes)

Groups of suppliers and customers

G/L accounts

Posting date

Origin

In Customizing for bank accounting ( Financial Accounting Business Transactions Payment Transactions Payment Handling Define Global Settings ), you can establish which of the following fields are ready for input:

Customer accounts

Supplier accounts

G/L accounts

Origin

This refers to the origins of a payment request and provides information on:

where the payment request comes from

how the payment is to be processed with the payment request

who has authorization to make payments with payment requests

Example: Application components (Treasury Management)

Via further selections according to the content of the relevant table entries of the suppliers, customers and G/L account master data as well as the payment requests, you can create exact selection profiles.

Control parameters include the parameters in the payment requests such as:

Clearing still not carried out

Item due

Released for payment

###### Grouping of Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Procedure: Payment Program for Payment Requests > Grouping of Payments | L7 | trm07 p.64 | loio `f903c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f903c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

This function allows you to group together several payment requests into one payment.

**Integration**

Payment requests are settled individually if this is specified in the request or defined as such in the master record for the corresponding suppliers and/or customers.

**Prerequisites**

The grouping of several payment requests into one payment can take place if the following data correspond to each other:

Payer/payee company code and sending company code (cross-company code payment transaction)

Business area

Business partner (payment to the same supplier/customer can be offset)

Payee and/or branch

Payment currency

Value date for house bank

**Functions**

For customers and suppliers, a series of further fields from the payment request for controlling grouping can be used (e.g reference document number, document date). The grouping key is defined in the master data.

The grouping term offers a further possibility at payment request level. It can be freely set by the user.

###### Payment Method and Bank Determination

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Procedure: Payment Program for Payment Requests > Payment Method and Bank Determination | L7 | trm07 p.64 | loio `fc03c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fc03c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

For payment transactions between G/L accounts, both sets of bank details and possible payment methods must be specified explicitly in the payment request. In order to deal with the case ofclearing several requests where it is unclear whether an outgoing or incoming payment must take place, you can specify several payment methods here.

For payment transactions with customers and suppliers, the entry of bank details and payment methods in the request is not always necessary as the corresponding data from master records can be read. For bank determination, the bank data entered in the payment request is used. Otherwise, bank and payment method determination takes place as in the standard payment program.

**Functions**

Via the payment program, the necessary checks for the payment methods, house banks and also the partner banks (for suppliers and customers) are carried out.

The payment program supports all payment methods with the exception of special G/L ledger account transactions (such as payment with bill of exchange or down payment).

###### Posting and Clearing

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Procedure: Payment Program for Payment Requests > Posting and Clearing | L7 | trm07 p.65 | loio `0204c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0204c5536a51204be10000000a174cb4.html?locale=en-US)

In the payment run (update run), documents are automatically posted and open items are cleared by the payment program according to the type of payment.

[figure TRM07-F022 - For payment transactions with suppliers and customers, the simplest case is represented in example 1. The upper column describes the entry postings, the lower column describes the payment postings. When posting a request for which no accounting document has been created, the payment document alone is posted (bank subaccount to supplier) and the payment request is cleared.]

For payment transactions with suppliers and customers, the simplest case is represented in example 1. The upper column describes the entry postings, the lower column describes the payment postings. When posting a request for which no accounting document has been created, the payment document alone is posted (bank subaccount to supplier) and the payment request is cleared.

If there is a corresponding document (e.g. supplier invoice) for the request in the system, then the open item is also cleared on the subledger account. With different currencies (local, document and payment currency), possible rate differences are automatically posted to the relevant G/L account. Such a case is represented in example 2.

[figure TRM07-F023]

For G/L account payments, the respective accounts are posted directly in the general ledger. Example 3 represents the simple money transfer between two house bank accounts.

[figure TRM07-F024 - For G/L account payments, the respective accounts are posted directly in the general ledger. Example 3 represents the simple money transfer between two house bank accounts.]

In the payment requests, you enter the bank details for the creation of the payment on one side, on the other side you enter the corresponding G/L account as the payee which is to be posted to. Via control of the payment method, you can make settings so that alongside the payment order for the house bank, a payment advice note is also sent to the recipient bank via the expected incoming payments.

With cross-company code payment transactions, the payment program carries out the necessary clearing postings between the relevant company codes.

###### Customizing of the Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program | L6 | trm07 p.66 | loio `0804c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0804c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Before you can use the payment program, you need to define your house banks and accounts at your banks, the required payment methods and the necessary payment forms. The standard system has predefined payment methods and forms which you can adapt to meet your own requirements.

In large parts, you use the same Customizing functions as in the standard payment program. This is particularly the case for controlling payment medium creation, company codes, payment methods and house banks.

Some additional functions for controlling the payment program for payment requests are provided e.g. when defining house bank accounts and G/L account determination. The user can define the number of accounts per bank, currency and payment method for settling G/L account payments (e.g. bank account transfers).

**Integration**

Default values are required by the payment program if it is to automatically determine the information. However, you can also predefine this information in the payment request.

Most of the specifications are company code-dependent so that each company code can control the payment program to meet its own requirements.

**Functions**

Via Customizing of the payment program, you control:

What is to be paid.

To do this, you specify rules according to which the open items to be paid are selected and grouped for payment.

When payment is carried out.

Basically, the due date of the open items determines when payment is carried out. However, you can specify the payment deadline differently via configuration.

To whom the payment is made by specifying the payee.

How the payment is made

You determine rules used to select a payment method.

From where the payment is made. You determine rules that are used to select a bank and a bank account for the payment.

###### House Banks

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > House Banks | L7 | trm07 p.67 | loio `be03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/be03c55368511d4be10000000a174cb4.html?locale=en-US)

The banks with which your company (company code) maintains a bank account are referred to as house banks.

You define these banks in the system under a house bank key (bank ID). You store the accounts that you maintain at these banks under an account ID. For each bank account, you create a G/L account in the SAP system.

Bank master data is stored centrally in the SAP system. This includes address data and other control data, such as the SWIFT code. You require bank master data for your house banks and for your customer or supplier's banks. By specifying the country/region and a country/region-specific key, such as the bank number or the SWIFT code, you establish the connection between your house banks and the bank master data. The bank details are required for printing the payment forms.

You can find out how to create bank master data in Bank Master Data.

###### Payment Methods

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Payment Methods | L7 | trm07 p.68 | loio `0b04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0b04c5536a51204be10000000a174cb4.html?locale=en-US)

**Definition**

The payment method specifies the procedure by which payments are made, for example, check or transfer.

The following payment methods are usual for suppliers, customers and transactions between bank accounts:

|Suppliers|Customers|Bank Accounts|
|---|---|---|
|Check|Bank collection|Transfer|
|Transfer|Bank direct debit|Bank collection|
|Postal giro transfer|Refund by check| |


**Structure**

You define the payment methods in two steps:

- 1. Firstly, you make all the specifications that are required for each payment method in each country/region. This is necessary for all the payment methods used by your company in each country/region. If you have companies (company codes) in Germany, France and the USA, for example, you define the payment method Check for each country/region.
- 2. You then define the payment methods you use for each company code. When in this function, you also specify the conditions of their use.


Integration

**Note:**

The payment program for payment requests does not support payment methods portrayed via special general ledger transactions (for example, bill of exchange and bill of exchange payment request).

###### Country/Region-Specific Definitions for the Payment Method

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Payment Methods > Country/Region-Specific Definitions for the Payment Method | L8 | trm07 p.68 | loio `379bc2531bb9b44ce10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/379bc2531bb9b44ce10000000a174cb4.html?locale=en-US)

The payment methods that are used in at least one of your organization's company codes are defined as follows.

You classify a payment method by selecting the characteristics that are to apply to it. The program uses this information to determine the data required for the payment forms and data carriers.

You must also define which information from the customer/supplier master record is to be used to determine the payment method. If this information is missing from the customer/supplier master record, the payment method cannot be used.

**Example:**

In the standard system, the payment method Check (for Germany) is configured such that a check is created (classification). The street or P.O. box must be contained in the customer or supplier master record.

These specifications are supplemented with other specifications for posting the payment documents and printing the forms.

**Example:**

For the payment method Check, you specify for example that document type KA is used and the print program RFFOD_S.

All the payment medium programs are documented in detail in the language of the country/region of use. If you want to have the system list all the standard payment medium programs available, proceed as follows:

- 1. Choose System Services Reporting . Enter RFFO* and select the function Utilities Find .
- 2. Enter FORD in the Program category field and execute the search. The system will generate a list of all payment medium programs in the system. The name of each program gives you an indication of its purpose.

###### Country/Region-Specific Definitions for the Payment Method: Graphic

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Payment Methods > Country/Region-Specific Definitions for the Payment Method > Country/Region-Specific Definitions for the Payment Method: Graphic | L9 | trm07 p.69 | loio `c103c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c103c55368511d4be10000000a174cb4.html?locale=en-US)

###### Company Code Specifications for the Payment Method

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Payment Methods > Company Code Specifications for the Payment Method | L8 | trm07 p.69 | loio `c403c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c403c55368511d4be10000000a174cb4.html?locale=en-US)

The conditions under which each payment method is used must be defined for each company code that makes payments. (Company Code-Specific Definitions for the Payment Method: Graphic shows those specifications that are used for the payment method "check" in Germany).

To do this, enter a minimum and a maximum amount for a payment (1). This tells the program the value range within which the payment method can be selected by the payment program. Note that unless you specify a maximum amount, the payment method cannot be used at all. This value range does not apply if the payment method is specified in the open item.

You also specify whether the payment method can be used for foreign payment transactions. You specify whether payment is made if:

The customer or supplier is based abroad (2).

The bank to which the payment is made is based abroad (3).

You specify whether it is possible to use the payment method in question to pay in foreign currency (4) in which case any currency can be used.

You can also specify particular currencies per payment method and country/region. If this payment method is selected, payments are only processed in one of the currencies specified.

If you wish to define particular currencies, choose the function Currencies in the country/region-specific details for each payment method.

**Note:**

If the payment method allows only payments in local currency, then any foreign currencies you may have defined are ignored.

During a transition phase, both the existing local currency and the euro can be used for domestic bank transfers. To enable this, define payments in foreign currency as permitted for the payment method Bank transfer and the euro and the existing

local currency are possible currencies.

You can use a payment method such as euro bank transfer for certain currencies only.

You use foreign currency checks with pre-printed currency key (for example, USD checks) and you wish to set up a payment method with which you make payments in USD only, whereby USD is not your local currency.

You specify if the payment method should include the attribute Payment per Due Date. This indicator ensures that a payment will be created for each due date. Items to be paid are then grouped according to due date, and instead of one payment being generated, as many payments are generated as there are different due dates.

**Example:**

For the payment method "check", you do not specify any minimum amount limits since this payment method is used if other payment methods cannot be used. You must specify a maximum amount because otherwise the payment method cannot be used. The customer or supplier can be located abroad. The customer/supplier’s bank is irrelevant for check payments. Foreign payment transactions are therefore possible. Payments in foreign currencies are permitted.

###### Company Code-Specific Definitions for the Payment Method: Graphic

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Payment Methods > Company Code Specifications for the Payment Method > Company Code-Specific Definitions for the Payment Method: Graphic | L9 | trm07 p.70 | loio `c703c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c703c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F025 - Payment Method: Additional Specifications]

###### Payment Method: Additional Specifications

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Payment Method: Additional Specifications | L7 | loio `0e04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0e04c5536a51204be10000000a174cb4.html?locale=en-US)

Definiton

The payment program groups payments according to these specifications.

**Use**

You can define additional specifications (Mailstop Codes) per company code.

For each additional specification made, a separate payment will be carried out. In the payment medium programs, you can select and sort where needed according to an additional specification. Correspondence can also be sorted using this criterion.

Payment method specifications can be entered in the payment request.

**Example:**

You can use additional specifications for controlling the issuing of checks. The specification could divert checks to be sent to partner firms by interoffice mail, instead of through the postal system. Since there are different kinds of interoffice mail systems, you can designate an additional payment method specification to represent the exact system you would like to utilize. This will greatly simplify operations with multiple mail systems, since checks can be separated by additional payment method specification at the time of printing.

###### Forms

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms | L7 | trm07 p.71 | loio `ca03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ca03c55368511d4be10000000a174cb4.html?locale=en-US)

Various programs are available for printing payment forms. In some cases, the print programs are country/region-specific. You specify the program to used for a payment method when you make the country/region specifications for the payment method. This prevents the payment program from selecting the wrong print program when printing is carried out.

You also specify a name for the print job in print administration, under which the data for the payment transfer is stored temporarily.

To ensure that the programs print the forms correctly, the system specifies which data is printed in which position. The form layout is defined with SAPScript. You specify the name of the defined payment form when you make the company code specifications for the payment method (see the figure below, (1)). You also determine how many invoice items can be printed out in the part of the form which serves as the note to the payee (see the figure below, (2)). If more items are to be paid than can be listed on a form, you specify whether:

A payment advice should be printed (see the figure below, (3))

Several forms should be created (see the figure below, (4))

You also store the address data of the issuer of the form (see the figure below, (5)). This data is used by the print program.

[figure TRM07-F026 - You define the form that is used for printing a payment advice separately. You then specify this form when making the specifications for the paying company code. See Specifications for the Paying Company Code in the topic "Definition of the Paying Company Code" in Payment Program Settings.]

You define the form that is used for printing a payment advice separately. You then specify this form when making the specifications for the paying company code. See Specifications for the Paying Company Code in the topic "Definition of the Paying Company Code" in Payment Program Settings.

The standard system contains pre-defined forms for the standard payment methods. You can copy them and adapt them to your requirements.

###### Specifications for the Paying Company Code

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Specifications for the Paying Company Code | L8 | trm07 p.72 | loio `cd03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd03c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F027]

###### Parts of the Form

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Parts of the Form | L8 | trm07 p.73 | loio `d003c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d003c55368511d4be10000000a174cb4.html?locale=en-US)

A payment form is not usually longer than one page. In the SAP System, the form page is divided into different windows.

The figure Payment Form Components: Graphic shows some of the text windows defined for checks in Germany. These are:

|Window|Contents|
|---|---|
|HEADER|Company specifications, such as the company name or the company logo|
|PAGE|Page number|
|INFO, INFO 2|Date, document number, your account with the vendor, clerk etc.|
|ADDRESS|Sender specifications for window envelopes and receiver address|
|MAIN|Text, line item information from the payment run and total amount|


|Window|Contents|
|---|---|
|CARRYFWD|Carry forward, starting from the second page (where form is longer than one page) form overflow|
|CHECK|Check|
|CHECKADD|Check address|
|CHECKSPL|Amount in words|
|SUMMARY|Check form summary|


You determine the windows and their position on the page when defining a form. You enter a specific text for each window. This text is referred to as a text element.

You can enter various different texts for the HEADER, ADDRESS, and FOOTER windows, and the opening/closing form in the MAIN window for each company code. See Header, Sender, and Footer Text

The MAIN window is processed in a special way. You can define several text elements for this window. The text elements allow you to enter different texts for a window, which are then printed (depending on the print data set offered by the payment program). Read Text Elements in the MAIN Window

For information that the system fills in automatically at the time of the payment run, you define symbols in the text element . These are replaced by the appropriate data when the payment form is printed. In the MAIN window (see the figure Check Forms: An Example ) you can see, for example, the document number of each open item or the cash discount amount calculated for the invoice amount. In both cases, the information is not entered in the form until the payment run takes place. Symbols were entered in the text element to represent this data.

**See also:**

Payment Run Data for the Form Printout

###### Payment Form Components: Graphic

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Parts of the Form > Payment Form Components: Graphic | L9 | trm07 p.74 | loio `d303c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d303c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F028]

###### Letter Header, Sender and Footer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Letter Header, Sender and Footer | L8 | trm07 p.75 | loio `d603c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d603c55368511d4be10000000a174cb4.html?locale=en-US)

For each of the forms in the SAP system, windows have been defined for the letter header, the sender specifications in the letter window (see the above figure) and the footer text. You can enter text in these windows in three ways. There is an example in the figure Text Elements for Special Windows : Graphic .

Since the texts for the above-mentioned windows are company code-specific, you must specify whether you are working with one or several company codes:

You can enter a fixed text in the form window text element.

You should only do this if you use the form for a single company code.

You can define a standard text for several forms.

Enter the name of the standard text in the text elements of your choice in several forms.

However, this is only makes sense if you work with one company code but want to use one text for several forms. In the figure above, the standard text "ADRS HEADER" was used, for example.

You can define standard texts for several forms, and specify (depending on the dunning area and company code involved) which text should be used in the form.

You are advised to do this if you work with several company codes that use the same form. Three steps are necessary to do this:

Create the company code-specific standard texts.

When configuring the dunning program, specify which standard text is to be used for which company code.

In the text element, enter a standard variable for the standard text (see the table below). Depending on the company-code in question, the print program replaces the variable with the name of the standard text.

The variables for the company code-specific standard texts that you specify in the text element are predefined in the system:

|Standard text for|Symbols in the Text Element|
|---|---|
|Letter header|REGUD-TXTKO|
|Sender in the letter window|REGUD-TXTAB|
|Signature line|REGUD-TXTKO|
|Footer|REGUD-TXTFU|

###### Text Elements for Special Windows: Graphic

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Letter Header, Sender and Footer > Text Elements for Special Windows: Graphic | L9 | loio `d903c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d903c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F029 - Text Elements in the Main Window]

###### Text Elements in the Main Window

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Text Elements in the Main Window | L8 | loio `dc03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dc03c55368511d4be10000000a174cb4.html?locale=en-US)

The MAIN window contains a series of text elements. Each element is indicated by /E in the format column and a number in the text area (see the figure below). The print program will then print these text elements in the form, providing they are defined in the print data set.

**Example:**

You define text for order checks and checks in the check form. If the print dataset contains information for the payment method "check", the program uses the text for checks.

The following table contains some text elements for a check form from the MAIN window.

**Text Elements in the Main Window**

| | |
|---|---|
|510-O|Text for order checks|
|510-C|Pre-numbered checks|
|510-S|Text for checks|
|515|Heading for line item information|
|525|Line item information|


By using various text elements, you can use the same basic forms for similar payment methods, differentiating them simply by inserting different text elements (specific to the payment method being used) in the MAIN window. The print program determines the correct text element on the basis of the specifications stored under the payment method being used. As an example, the figure below shows how the text elements are defined for the MAIN window in the check form.

[figure TRM07-F030 - If you want to define your own form and use text elements specific to the payment method, you should keep to the following conventions when creating the text element name:]

If you want to define your own form and use text elements specific to the payment method, you should keep to the following conventions when creating the text element name:

The first three characters are determined by the program.

These characters are followed by a hyphen.

You then specify the payment method. In the USA, for example, you could enter C for check and O for order check.

For the forms, the print program always uses the text elements that have been specified for the payment method in question. Text elements that are to be printed out for all payment methods which use this form should be entered as a three-digit number only.

The text elements that can be used for forms are already defined in the system. All that you can change for each text element is the text. You can formulate this as you wish. You can find further information in the documentation for the individual print programs.

###### Check Forms: An Example

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Check Forms: An Example | L8 | trm07 p.78 | loio `df03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/df03c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F031]

[figure TRM07-F032]

8/27/26, 2:40 AM

###### Payment Run Data for the Form Printout

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Payment Run Data for the Form Printout | L8 | trm07 p.80 | loio `e203c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e203c55368511d4be10000000a174cb4.html?locale=en-US)

The data from the payment run that you require for the form printout is provided by the payment program. The payment program stores this data in the following structures after each payment run:

REGUH

contains the information on the payment, such as the payment method, payment document number and payee. The payment program creates a REGUH record for each payment.

REGUP

contains the information on the paid items, such as the amount, cash discount and invoice document number. The payment program creates a REGUP record for each paid item in a payment.

REGUD

contains derived values that are not contained in the above-mentioned structures. These include information from the business partner bank master record, amounts with protective asterisks, or amounts without editing characters for the OCRA line. This structure is filled by the print program, and deleted after the payment transfer medium is printed.

SPELL

contains the payment amount in words.

All the fields in these structures can be used as symbols in the form. You can also transfer field contents from any of the configuration tables in the system. The prerequisite is that these are read by the appropriate print program.

For the corresponding form, text elements have been defined for the individual windows as follows:

- 1. HEADER, ADDRESS and FOOTER

For this window, company code-specific standard texts have been defined. See Text Elements for Special Windows: Graphic

(3) . The names of the texts have been specified for each window (dependent on the company code) in the configuration of the payment program. When the form is printed, the print program determines and inserts the appropriate text.

- 2. MAIN

The MAIN window contains several text elements: one text element each for the address text, the header line, the line item information and the total amount.

The document numbers, dates, currency keys and amounts are provided after the payment run. Symbols have been defined in the appropriate text elements for this data.

For example, the variable &REGUP-BELNR& has been entered for the document number and the variable &REGUPBLDAT& for the document date.

- 3. CHECK


The CHECK window contains the information that is printed on the actual check. Symbols have been defined in the text for such information from the payment run. Using these symbols, the print program determines the check number, account number, bank number and amount, for example.

###### Modifying the Forms

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Modifying the Forms | L8 | trm07 p.80 | loio `e503c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e503c55368511d4be10000000a174cb4.html?locale=en-US)

The standard system contains an appropriate country/region-specific form for every standard payment method. These forms can be copied and modified as necessary. The new form must then be allocated to the respective payment methods using the company code-dependent definitions (see Form Printing Specifications). You can change the standard texts, the position of the windows or the highlighting of individual words and letters. If you need other information from the payment run in your forms, you can insert the appropriate symbols in your text elements. This allows you to use the field contents from the structures REGUH, REGUP, REGUD SPELL and FASBE for your form. You can see which fields are contained in the above-mentioned structures using the ABAP Dictionary.

###### Form Printing Specifications

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Modifying the Forms > Form Printing Specifications | L9 | trm07 p.81 | loio `e803c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e803c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F033 - Adapting a Form]

###### Adapting a Form

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Modifying the Forms > Adapting a Form | L9 | loio `eb03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eb03c55368511d4be10000000a174cb4.html?locale=en-US)

If you cannot use the standard forms in the SAP system, you must create your own forms. You can do this by copying the standard forms and modifying them where necessary.

Carry out the following steps from the initial SAP menu:

- 1. Choose Tools Word Processing Layout Sets .
- 2. You reach the initial screen for word processing.
- 3. Specify the name of your form and select Create/Change.


- 4. Your forms should begin with the letter "Z". This is a protected name format that is not used by SAP.
- 5. A dialog box appears. Here you enter a customer development class or specify that you will be using a local private object.
- 6. You reach the display of the general definitions for the form.


From here, you can transfer specifications and text elements from another form (e.g. the SAP standard form) into your form.

To do so, choose Layout Set Copy From . Via the entry Goto you can select the required specifications for your form.

Further information about how to adapt a form can be found in the documentation for SAPScript word processing.

###### Letter Header, Sender, and Footer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Modifying the Forms > Letter Header, Sender, and Footer | L9 | trm07 p.82 | loio `ee03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ee03c55368511d4be10000000a174cb4.html?locale=en-US)

You determine your standard texts for letter header, sender and footer when you carry out the following steps from the initial SAP menu:

- 1. Select Tools Word processing Standard text .
- 2. You reach the initial screen for word processing.
- 3. Specify the name of the text and select Standard text Create/change .
- 4. You reach a screen for text entry.


Further information for changing or entering standard texts can be found in the documentation for SAPScript word processing.

You can specify the standard texts directly in the text elements if you are not using different texts for different company codes.

To specify the standard texts for each company code, carry out the following steps in Customizing for Accounts Receivable and Accounts Payable:

- 1. Choose Configure payment program .
- 2. You reach the initial screen for the configuration of the payment program.
- 3. Choose Company codes Paying .
- 4. A list of the paying company codes is displayed.
- 5. Select the company code you require.
- 6. Choose Goto Sender details .
- 7. Enter the names of the standard texts for letter header, sender and footer.
- 8. Save your entries by choosing Company codes Save .


If you use company-code-dependent standard texts, you must specify the corresponding symbols in the text element for the print program (see the table below).

Symbols for Standard Texts

|Standard text for|Symbols in the Text Element|
|---|---|
|Letter header|REGUD-TXTKO|
|Sender in the letter window|REGUD-TXTAB|


|Footer|REGUD-TXTFU|
|---|---|

###### Displaying Fields from REGUH, REGUD, and REGUP

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Modifying the Forms > Displaying Fields from REGUH, REGUD, and REGUP | L9 | trm07 p.83 | loio `f103c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f103c55368511d4be10000000a174cb4.html?locale=en-US)

In order to display the fields from the files REGUH, REGUD and REGUP, proceed from the initial SAP menu as follows:

- 1. Select Tools ABAP/4 Workbench .
- 2. Next, select Dictionary
- 3. Enter one of the above-mentioned files as an object name, select the field Table and then select Display .


The fields in the structure are displayed. The field names which you can use for the forms are in the first column.

###### Creating Variants

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Modifying the Forms > Creating Variants | L9 | trm07 p.83 | loio `f403c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f403c55368511d4be10000000a174cb4.html?locale=en-US)

You must create at least one selection variant for every print report. You specify this variant later (for the payment form print run) when entering the parameters for a payment run.

In order to define a variant proceed from the initial SAP menu as follows:

- 1. Choose System Services Reporting. The ABAP/4 Program Development screen appears.
- 2. Enter the report name, for example RFFOD__S , and then select Goto Variants .
- 3. You reach the screen for processing your variant. The report name has been transferred.
- 4. Enter a name for the new variants and select Variants Create .
- 5. The screen for entering the selection criteria and the specifications appears.
- 6. Enter your criteria and make your specifications. Then press the CONTINUE push-button.

You reach the screen for maintaining variant values. Enter a short description of the variants in the Meaning field.

- 7. Save your variant by selecting Variant Save .


**Note:**

Leave the Run date and Identification fields in your variants free. These fields are filled dynamically when the program is run.

###### Print Control

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Forms > Print Control | L8 | trm07 p.83 | loio `f703c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f703c55368511d4be10000000a174cb4.html?locale=en-US)

You can carry out a payment run for different company codes, payment methods, and business partners even though different forms or data carriers may have to be printed or created for each payment method and company code. You can specify this later by entering selection variants for the data medium print programs.

The variants contain a series of selection criteria that are used to separate the data in the print data set. Separate print jobs are created in print administration for each variant called up from a data medium print program. Each print request is displayed in print management with the form description. You can call up the print jobs individually for printing.

**Note:**

You carry out the payment run for the payment methods "check" and "order check". The payment program creates a print file for this payment run. Since each payment method uses specific forms, you define a separate selection variant for each payment method for the print program RFFOD__S. The system places a print request in print administration for each variant (see the figure below).

[figure TRM07-F034 - You define the selection variants when you configure the payment program. You can define as many variants as you require for each print program but you must define at least one.]

You define the selection variants when you configure the payment program. You can define as many variants as you require for each print program but you must define at least one.

Besides the company code and the payment method, you can use other selection criteria for each variant:

Payment document check: Only posted documents are selected for printing.

House bank: Only payments processed via the specified house bank are selected. This may be necessary, for example, if house banks require special forms or if you want to create diskettes for the data medium exchange for several banks.

Accounts: Only documents containing the specified bank account are selected.

Currency key: You use this criterion if you print forms with pre-printed currency keys. You can separate the print jobs per currency via the criterion.

Payment document number: You use this criterion, for example, if you want to print certain payment documents separately.

You make certain printing specifications for each variant. These include:

Forms to be printed: You specify which additional forms (payment advice notes or payment summaries) are printed when you use this variant. You specify the printer on which each form is printed. Alternatively, you can select Print immediately.

Number of sample printouts: With line printers, it is advisable to run at least two sample printouts to enable you to adjust the forms correctly on the printer.

Language in which the text is printed: You can specify that the addressee's language (which is entered in his/her master record) is used. Otherwise, the print program selects the language of the sender.

Currency key: If you do not already use ISO codes for your currency keys, you can specify that the ISO code is used in the printed payment forms.

You can also define variants for those programs created by the payment list, the payment proposal list, and the exception list. Variants are not absolutely necessary for these programs.

###### Control of the Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program | L7 | trm07 p.85 | loio `1104c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1104c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

For each company code using the payment program, certain basic specifications must be in place.

Since the payment program can be used for more than one company code, you must also specify the company code that is making the payment.

To control the payment program, you must specify the following in advance:

How payment requests are selected and, if necessary, grouped together for one payment

The payee

How the payment method is selected

How the bank is selected

Which forms and other data carriers are used

**Activities**

You make these specifications when:

Configuring the payment program

Entering data in the master records of your business partner

Entering data in the payment requests

Entering data for the payment run in hand

###### Company Code Specifications

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Company Code Specifications | L8 | trm07 p.86 | loio `1404c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1404c5536a51204be10000000a174cb4.html?locale=en-US)

When configuring the payment program, you specify the company codes that are involved in automatic payments and also which company code makes the payments (paying company code).

General company code specifications

For each company code using the payment program, some general information is required, i.e. information that is not specifically linked to a payment method.

In some companies, one company code carries out the payment transactions centrally on behalf of several company codes. Consequently, you must specify the paying company code for each company code. This specification is also required even if you do not make payments centrally; in this case, the paying company code you enter is identical to the company code. When carrying forward bank accounts, you can also specify paying company codes that are different to the company code.

For more information, see Cross-Company Code Payments.

**Note:**

All settings apart from the sending and paying company codes are not relevant for the payment program for payment requests.

Specifications for the paying company code

You specify how the paying company code makes the payment. For example, you specify minimum amounts for incoming and outgoing payments. The payment program only makes a payment for the company code if the payment is within the amount limits set.

You can specify further amount limits for each payment method (see Company Code-Specific Definitions for the Payment Method: Graphic (1)). The narrower range always applies.

**Note:**

The settings for bill of exchange payment are irrelevant for the payment program for payment requests.

###### Selecting Open Payment Requests

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Selecting Open Payment Requests | L8 | trm07 p.86 | loio `1704c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1704c5536a51204be10000000a174cb4.html?locale=en-US)

The payment program identifies the open payment requests and selects the items to be paid. It basically pays items as late as possible. You specify the exact time of payment when configuring the payment program.

Criteria for selecting open items: Payment program

The selection of open payment requests is determined by the following factors:

The due date of the items is basically determined by the due date and the level of urgency indicator in the payment request

For each payment run, you specify the date of the next payment run. The program uses this date to determine whether an item is to be included in the current or the next payment run.

###### Blocking Open Items

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Selecting Open Payment Requests > Blocking Open Items | L9 | trm07 p.86 | loio `fa03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fa03c55368511d4be10000000a174cb4.html?locale=en-US)

Use

You block the items that, regardless of their due date, you do not want to pay. To do this, you enter a blocking key in the item that represents the reason for blocking. If you want to block the account of a customer or supplier from payment, you enter the blocking key in their master record.

The standard system contains several blocking keys, which you can add to or change.

The payment program creates a payment proposal during the payment run. The payment is made on the basis of this payment proposal list. The blocked items are displayed separately in the list. You can process the payment proposal, and, for example, set or cancel the payment block on an item.

It is also possible to specify that a blocking key cannot be changed from the payment proposal transaction.

###### Notes on Clearing Dates

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Selecting Open Payment Requests > Notes on Clearing Dates | L9 | trm07 p.87 | loio `fd03c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fd03c55368511d4be10000000a174cb4.html?locale=en-US)

On the whole, the payment date is used as the clearing date. There exist, however, the following exceptions.

Items whose posting date comes after the posting date of the payment run will be paid, provided they are already due.

The clearing date for such payments is not the payment date, but rather the latest posting date possible. Thus any danger of the clearing date coming before the posting date is prevented in the context of paid items. Errors are avoided in this way.

###### Grouping of Payment Requests

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Grouping of Payment Requests | L8 | trm07 p.87 | loio `1a04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1a04c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Wherever possible, the payment program will always group payment requests together for payment. However, you can also specify that an individual payment (separate payment) is made for a particular item. For certain payment methods, only individual payments are possible.

The payment program can only group together open payment requests into one payment if the open items in an account have the same:

Payment currency

Payment method in the item

Bank in the item

Contents of the grouping fields

You can also settle payment requests from different company codes together as well as customer and supplier items.

Items in an account are not grouped together if you:

Make payments seperately per business area. This procedure entails separate payments being created per business area.

Wish to make individual payments.

**Note:**

Payment requests in which one or several payment methods are specified are not grouped together with items in which no payment method is specified.

###### Grouping Keys for Payment Requests

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Grouping of Payment Requests > Grouping Keys for Payment Requests | L9 | trm07 p.88 | loio `1d04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1d04c5536a51204be10000000a174cb4.html?locale=en-US)

You can use grouping keys to group together payment requests that should be paid together.

To do so, you must specify a grouping term for the payment request. Those payment requests with the same contents are grouped together for payment.

###### Cross-Company Code Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Grouping of Payment Requests > Cross-Company Code Payments | L9 | trm07 p.88 | loio `0004c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0004c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

If one company code pays centrally for others in your organization, all the open items of a customer/supplier that exist in several company codes are paid together, provided:

**Prerequisites**

You have specified the same paying company code for all participating company codes (see "General Company Code Specifications" in Company Code Specifications).

The company codes are located in the same country/region

The local currencies and where appropriate, all parallel currencies, are identical

**Features**

The paying company code is the one that settles the open items; the postings to the bank accounts and sub-accounts are made to this company code.

Either the paying or the "sending" company code (i.e. the company code against which the receivable exists) can function as the sending company code:

If the paying company code should also be displayed as the sending company code for the customer/supplier, you should specify it as a sending company code.

If you do not specify a sending company code, the system automatically takes the paying company code as such. If this is the case, the open items are grouped together in a single payment. With such a payment you cannot see from the payment transfer medium which company code owed the payable.

If you want to specify which company code owes the payable to the customer or supplier, specify this company code as the sending company code.

If you do this, all the items which have the same paying and sending company codes are grouped together for payment. A separate payment form is generated for these items.

On payment advice notes, a note is recorded stating for which company code the payment is made (for the sending company code). This is not possible in the case of other payment forms. If necessary, you can configure the payment program in such a way that a payment advice note is also printed in the case of other payment forms.

**Example:**

Company code 0001 pays additionally for company codes 0002 and 0003. Company code 0001 should be entered for itself as both paying and sending company code in this situation. For company codes 0001 and 0002, company code 0001 is the paying company code. The company codes themselves are entered as the sending company codes. This ensures that a separate payment is made for each sending company code. The sending company codes are listed in the notes in the payment advice notes.

The standard forms for the payment advice and the check with payment advice contain a separate text element for the note on the sending company code. If you define your own forms, and want such a note, you must add this text element to them.

###### Clearing Customers and Vendors

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Grouping of Payment Requests > Clearing Customers and Vendors | L9 | trm07 p.89 | loio `0304c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0304c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

If you run a vendor as a customer at the same time, you can offset the open items. Under this procedure, receivables and payables are offset against each other. If a credit balance results a payment is due. If you have a debit balance, you draw up a debit memo, providing all the other conditions for this have been fulfilled.

**Prerequisites**

You must enter the account number of the other business partner in the master record.

The Customer/Vendor field is in the general area on the Control screen.

In both master records, the option for clearing between customer and vendor accounts must be selected.

The Clrg with vend./Clrg with cust. field is in the company code-specific area.

###### Decentralized Payment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Grouping of Payment Requests > Decentralized Payment | L9 | trm07 p.89 | loio `2004c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2004c5536a51204be10000000a174cb4.html?locale=en-US)

In a head office/subsidiary relationship, the payment program pays via the head office provided that the head office is specified in the payment request.

###### Separate Payment by Business Area

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Grouping of Payment Requests > Separate Payment by Business Area | L9 | trm07 p.89 | loio `0604c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0604c55368511d4be10000000a174cb4.html?locale=en-US)

Use

You can determine that open items are paid separately by business area for every paying company code. See topic "General Company Code Specifications" in Company Code Specifications . The payment program then makes separate payments per business area.

###### Individual Payment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Grouping of Payment Requests > Individual Payment | L9 | trm07 p.89 | loio `2304c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2304c5536a51204be10000000a174cb4.html?locale=en-US)

Payment requests are paid individually if the following conditions are met:

The indicator for individual payment has been set in the payment request.

If you always wish to settle payment requests individually for a business partner, you can specify this in the company codespecific area of the master record. To do this, you mark the individual payment field.

If you wish to pay for an open item individually with a payment procedure, define this payment method for individual payment (see Company Code-Specific Definitions for the Payment Method: Graphic). This payment method must be entered in the open item that is to be paid individually.

**Example:**

You wish to pay individual items with a separate check. To do so, define a second payment method alongside the standard payment method via check. For this second payment method, you enter the same specifications and also the individual payment. You enter this payment method in the open item for which a separate check is to be issued.

###### Payee

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Payee | L8 | trm07 p.90 | loio `2604c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2604c5536a51204be10000000a174cb4.html?locale=en-US)

The payee is usually the same as the issuer of the invoice (supplier). Payment to a different payee can, however, also take place.

This is, in particular, necessary for payments between bank accounts, as no payee is defined here at present.

For this to happen, the different payee must be specified.

You enter the data (for example, name, address, and bank) in the payment request if it is to be paid to a different payee.

###### Notes on the Payment Method

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Notes on the Payment Method | L8 | trm07 p.90 | loio `2904c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2904c5536a51204be10000000a174cb4.html?locale=en-US)

You can specify payment methods in the master record or in the payment request.

Payment transactions with suppliers and customers:

In the master record, you can either

Enter a single payment method if you have fixed a certain payment method with a business partner, for example, or

Enter several payment methods from which the payment program then selects one in the payment run according to your specifications.

If you specify payment methods in open items, this overrides those from the master record.

Payment transactions between bank accounts:

In this case, the possible payment methods must always be specified in the payment request.

The payment method you wish to use must always be specified in the master record of the business partner or in the open item.

###### Selection of the Payment Method by the Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Notes on the Payment Method > Selection of the Payment Method by the Payment Program | L9 | trm07 p.90 | loio `0904c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0904c55368511d4be10000000a174cb4.html?locale=en-US)

Use

Before every payment run you must specify which payment methods may be used in the payment run. If a payment method is specified in open items or in the master record of the customer/supplier and if that payment method is permitted for that payment run, the payment program selects this payment method. The payment method in the open items takes precedence over any payment method defined in the master record.

If several payment methods are specified in the master record and none in the item, then the payment program selects a payment method. The program checks (in the sequence in which you entered them) whether each of the payment methods you specified for the payment run can be used. To be able to be used, a payment method must satisfy the following conditions (among others):

The payment method must be specified in the customer/supplier master record or open items.

The master record must contain the specifications needed for the payment method. See Country/Region-Specific Definitions for the Payment Method.

For foreign payments, the payment program checks whether the payment method in question allows payments to customers/suppliers or banks located abroad. See Company Code Specifications for the Payment Method.

In the case of payments in foreign currency the payment method must be allowed for foreign currency payments. See Company Code Specifications for the Payment Method.

The permissible minimum and maximum amounts must be adhered to for the payment amount. See Company Code Specifications for the Payment Method.

For payment, a bank permissible for the payment method under consideration is determined. Read Bank Selection to see how banks are selected for a payment method.

If one of the specified payment methods meets all the above conditions, this payment method is used. Otherwise, the program carries out all the checks for the next payment method in the list you entered.

###### Sample Payment Method Selection

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Notes on the Payment Method > Sample Payment Method Selection | L9 | trm07 p.91 | loio `0c04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0c04c55368511d4be10000000a174cb4.html?locale=en-US)

You have to settle a payable of 3,000 USD owed to a vendor. The master record of the vendor specifies that the payment methods "check" and "transfer" are allowed. No payment method is specified in the item.

During the payment run, you specify the payment methods "transfer" and "check". The following values are specified for the payment methods:

| |Transfer|Check|
|---|---|---|
|Minimum amount|5.00|0|
|Maximum amount|1,999.99|9,999,999.00|
|Foreign payment|not possible|possible|
|Specs. in master record|Bank details|none|
|Number of items per form|2|99|


The payment program checks the payment methods in the sequence you entered them during the payment run. The amount cannot be transferred as the payment amount (3,000 USD) is above the maximum amount possible for transfer (1,999.99 USD). The item can be paid by check if a suitable house bank can be determined for it. Read the topic Bank Selection

###### Bank Selection (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection | L8 | trm07 p.91 | loio `2c04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2c04c5536a51204be10000000a174cb4.html?locale=en-US)

Use

For payment transactions, you need house banks and possibly the bank details of your business partner.

House banks are the banks with which your company code maintains an account.

Depending on the payment method used, you may need the bank details of your business partner. For example, you need the bank details of your business partner for transfers but not for clearing checks. Enter the bank details of your business partner in the master records.

You can define as many bank details as you want, both for your company codes and for your business partners. You can determine which bank is selected in the following ways:

You make an explicit specification in the master record of the business partner or in the payment request. The specification in the payment request has higher priority.

For payments between bank accounts, the bank details must be specified in the payment request. Up to three intermediary banks can be specified in the payment request.

The payment program determines, according to specified rules, the most suitable house bank or the optimal combination of house bank and business partner's bank.

###### Bank Details in the Customer/Supplier Master Record

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection > Bank Details in the Customer/Supplier Master Record | L9 | trm07 p.92 | loio `0f04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f04c55368511d4be10000000a174cb4.html?locale=en-US)

Use

In the master record of the customer/supplier, you can make as many bank detail entries as you want. If the payment transactions should always be carried out by a customer/supplier's bank, only specify this bank.

If you only want to allow one house bank to carry out payment transactions with a customer/supplier, enter this bank in the master record of the customer/supplier. The correct field for this is in the company code-specific area of the master record.

###### Bank Details in the Payment Request

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection > Bank Details in the Payment Request | L9 | trm07 p.92 | loio `2f04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2f04c5536a51204be10000000a174cb4.html?locale=en-US)

You can specify the bank details of the business partner as well as up to three intermediary banks in the payment request.

For payment transactions between bank accounts, the bank details must be entered in the payment request.

###### Selecting the Bank Details of a Business Partner

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection > Selecting the Bank Details of a Business Partner | L9 | trm07 p.92 | loio `1204c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1204c55368511d4be10000000a174cb4.html?locale=en-US)

Use

If the payment method being used requires the customer/supplier’s bank details and these have not been specified, the payment program selects the bank details allowed for that method. The bank details allowed must be specified in the customer/supplier master record. The payment program selects the bank details that meet all the requirements of the payment method:

If a collection authorization is necessary for the payment method, the customer/supplier master record must contain a collection authorization for bank details.

If only bank details for banks located in the same country/region are allowed for the payment method, the payment program selects an appropriate bank.

If the payment method specifications require the bank to be a postal check office or postal giro office, the payment program selects an appropriate bank. You determine in the bank master data whether a bank is a post office bank.

If, after all the criteria have been checked, the payment program chooses several banks, it uses the first bank that fulfills all the terms. If the payment being used also requires the program to select the optimal bank for payment, further checks, involving the house banks, are necessary. For more information, see Optimizing Bank Selection.

###### Selecting the House Bank

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection > Selecting the House Bank | L9 | trm07 p.93 | loio `1504c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1504c55368511d4be10000000a174cb4.html?locale=en-US)

You specify which house banks are allowed for every payment method or, if you prefer, for both payment method and currency. You should sort this list of permissible banks in ranking order according to priority. See the figure below, ( 1) . For every combination of payment method and house bank, specify via which bank account (for example giro or foreign exchange account) the payment should be made. See the figure below, ( 2) .

For every account at a house bank, specify the amounts that are available for the payment run. See the figure below, ( 3) .

[figure TRM07-F035 - The payment program determines the house bank in the same sequence:]

The payment program determines the house bank in the same sequence:

- 1. First it determines the bank ID (house banks) based on the payment method and currency. If it finds no entry for the combination, it checks the bank for payment method without currency specification, if such an entry exists.
- 2. It determines the account ID on the basis of the bank ID, the payment method and the currency.


- 3. Finally, it finds out whether sufficient amounts are available for both bank ID and account ID.


During the payment run the payment program therefore attempts to determine a house bank and a bank account that has a sufficient amount available for payment. This may result in the following possibilities:

No house bank is found that fulfills all terms. The payment cannot then be made with the payment method with which the check was carried out. The checks are carried out for the next possible bank. If no bank is determined, the payment method can not be used. If another method is available, it will then be checked as well. This is noted in the log for the payment run.

One house bank only is determined. The payment is made via this house bank.

The program produces a list with house banks. The payment is made from the house bank with the highest priority according to the defined ranking order of the banks. This is not the case if payment optimization has been specified. Read the topic Optimizing Bank Selection

###### Optimizing Bank Selection

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection > Optimizing Bank Selection | L9 | trm07 p.95 | loio `1804c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1804c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

For every payment method you can specify for each company code whether the program should select the optimal bank for payment. Optimization can be by bank group or by postal code. See Company Code-Specific Definitions for the Payment Method: Graphic.

Optimization by bank group helps ensure that money is transferred from your house bank to your customer/supplier’s bank as fast as possible. In order to do this, assign a bank group (that is freely definable) to all banks in your master records.

Optimization by postal code ensures the house bank is selected according to the customer/supplier’s location.

Optimization by Bank Group

If you specify optimization according to bank groups for a payment method, the payment program selects two banks that belong to the same bank group. If several house banks come into consideration, the bank with the highest priority (ranking order) is selected. If an optimization is not possible, the optimization function does not apply.

**Example:**

In the first part of the figure below, two banks belong to the same bank group: The Bank of America belongs to the bank group BA as a house bank and also as the bank of the customer/supplier. The Bank of Chicago belongs to the bank group BC. In this case, the payment program selects the Bank of America, i.e. the bank with the higher priority. The second part of the figure shows a combination for which optimization is not possible. The payment program selects the house bank with the highest priority without taking optimization into account.

[figure TRM07-F036 - You determine which bank group a bank belongs to in the master data of the bank. You should set up the groups in such a way that the financial transactions can be processed between the banks of the same group rapidly. In Germany, for example, the banks that belong to the same giro network are assigned to the same bank group.]

You determine which bank group a bank belongs to in the master data of the bank. You should set up the groups in such a way that the financial transactions can be processed between the banks of the same group rapidly. In Germany, for example, the banks that belong to the same giro network are assigned to the same bank group.

Optimization by Postal Code

If a certain payment method specifies optimization by postal code, the payment program selects a house bank based on the postal code area of the customer/supplier. If no house bank is defined for the postal code area of the customer/supplier, or if the selected house bank cannot be used, the payment program selects the house bank with the highest priority from the priority list. In this case, optimization does not take place.

For this type of optimization, you must assign your house banks to a range of postal codes (see the figure below).

[figure TRM07-F037]

###### Check Available Amounts

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection > Check Available Amounts | L9 | trm07 p.97 | loio `3204c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3204c5536a51204be10000000a174cb4.html?locale=en-US)

The payment program checks whether the selected bank accounts have sufficient funds for payment.

For your accounts at the house banks, you can specify available amounts separately for incoming payments and outgoing payments.

For outgoing payments, you specify the size of the amount that can be paid.

For incoming payments, you specify the amount up to which such payments can be made to a bank account.

If the specified limit is exceeded, the payment program selects another bank. The specifications you make concerning available amounts determine which bank account should pay. You should ensure that these amounts are up to date before every payment run.

The payment program does not carry out amount splitting. If the amount on a bank account is not sufficient for a payment, the payment program selects another bank account. If it finds no bank account from which it can post the entire amount for a payment, it does not carry out the payment.

The payment program does not use the specified value dates. Enter the value 999 after agreement with Financial Accounting.

###### Value Dates

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Bank Selection > Value Dates | L9 | trm07 p.97 | loio `3504c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3504c5536a51204be10000000a174cb4.html?locale=en-US)

The value date must be specified in the payment request for the house bank or the bank of the business partner.

If the value date for the bank of the business partner is specified, the value date for the house bank can be calculated by the payment program for payment requests.

Under Value Date Term HBank/Pbank , you enter a time interval (in working days) for the term between the house bank and partner bank.

You enter a calendar ID under Factory Calendar for each payment currency and bank country/region.

The following procedure is followed when determining the value date:

- 1. The value date for the recipient bank is read in the payment request.


- 2. It is checked whether a Term HBank/Pbank has been entered.
- 3. The valid calendar for the recipient bank is searched for. For this, it is checked whether a calendar for the currency and country/region of the recipient bank has been defined. If this search is not successful, it is checked whether a special calendar has been defined for the currency and the country/region. Otherwise, the calendar valid for the currency is chosen.
- 4. The value date for the house bank is calculated with these entries.
- 5. Finally, the calendar valid for the house bank is determined and it is checked whether the value date is valid. If necessary, the value date is calculated again (i.e. pushed further back in time).

###### Specifications for Posting Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Specifications for Posting Payments | L8 | trm07 p.98 | loio `1b04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b04c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

The payment program posts payments and related postings such as those for tax, tax adjustments, exchange rate differences, or cash discount) automatically.

[figure TRM07-F038 - The payment program posts payments and related postings such as those for tax, tax adjustments, exchange rate differences, or cash discount) automatically.]

**Prerequisites**

To enable these postings to be made, you must first enter the following information:

The bank or bank subaccounts to be posted to

The document type to be used for posting the payments

Whether exchange rate differences are posted. For further information on configuring the payment program for exchange rate differences, see the topic Posting Exchange Rate Differences: Payment Program

###### Bank Accounts and Bank Subaccounts

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Specifications for Posting Payments > Bank Accounts and Bank Subaccounts | L9 | trm07 p.99 | loio `1e04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1e04c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

It is advisable to use bank subaccounts for posting incoming and outgoing payments.

If you do not use subaccounts, set up your standard bank accounts in the payment program configuration menu. See House Bank Selection by the Payment Program

This includes among other things the accounts for outgoing checks, outgoing transfers, incoming checks and bank collection (see the figure below).

[figure TRM07-F039 - This includes among other things the accounts for outgoing checks, outgoing transfers, incoming checks and bank collection (see the figure below).]

Using subaccounts has the following advantage: you can reconcile the balance of the account at your bank with the balance of your corresponding G/L account at any time. The subaccounts ensure that all incoming and outgoing payments are only posted to the G/L bank account when the money is actually debited from/credited to your bank account. This transfer posting from the clearing account to the bank account is made when you receive the appropriate account statement from your bank.

Bank Accounts and Bank Subaccounts: Example

**Prerequisites**

To use bank subaccounts, create subaccounts with whatever degree of differentiation you require. You can create, for example, a bank subaccount for each bank or for each bank and a group of payment methods. The charts of accounts delivered with this package provide a reference for such differentiation.

You must specify the account number so that the payment program can post to the appropriate bank subaccount (see the following figure). This posting is made on the basis of bank ID, payment method and if appropriate, currency.

[figure TRM07-F040 - Subaccounts are generally managed on an open item basis and with line item display, since you want to be able to see via these accounts at any time whether a business transaction has been completed.]

Subaccounts are generally managed on an open item basis and with line item display, since you want to be able to see via these accounts at any time whether a business transaction has been completed.

Notes on the Sort Sequence of Items in Bank Subaccounts

If bank subaccounts that are usually posted to by the payment program (for example, the account for outgoing transfers) have a special sort sequence, it is easier to process them when posting the bank statement.

The documents from the payment run contain the date and identification number (such as 19940301-ID) of the payment run in their document header text (field BKTXT ). You can have the system automatically transfer this information to the Allocation field in the line item if you define a corresponding item sorting rule and enter this in the G/L account master record.

Subsequently you can, when entering a bank statement, select via the Allocation field all the outgoing transfers from a certain payment run in order to clear them.

Posting Separately by Business Areas

If you have determined that the payments for a certain company code should be made separately per business area, then the bank posting is made to the business area of the paid items.

If you do not separate the payments by business area, you can specify that the bank postings should be made to one particular business area. To do so, specify the required business area for the bank account (see the figure above).

**Note:**

This specification is only effective if you do not already pay separately by business area.

In all other cases the postings to the bank subaccounts are carried out without reference to business areas.

###### Bank Accounts and Bank Subaccounts: Example

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Specifications for Posting Payments > Bank Accounts and Bank Subaccounts > Bank Accounts and Bank Subaccounts: Example | L10 | trm07 p.101 | loio `2104c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2104c55368511d4be10000000a174cb4.html?locale=en-US)

You settled a payable amounting to 5,000 USD by check. The payment was posted to the subaccount for outgoing checks and to the supplier account (see the figure below). The payable on the supplier account was cleared with this procedure.

[figure TRM07-F041 - After the check amount is actually debited from your bank account, you post it to the corresponding G/L bank account and select the corresponding check on the outgoing checks account (see the figure above).]

After the check amount is actually debited from your bank account, you post it to the corresponding G/L bank account and select the corresponding check on the outgoing checks account (see the figure above).

During clearing, the system posts the amount to the bank subaccount "Outgoing Checks" and clears the posted item on this account.

The check is now marked as cashed. Your G/L bank account only contains those amounts which have actually been debited from your bank account.

###### Notes on the Sort Sequence of Items in Bank Subaccounts

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Specifications for Posting Payments > Bank Accounts and Bank Subaccounts > Notes on the Sort Sequence of Items in Bank Subaccounts | L10 | trm07 p.101 | loio `2404c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2404c55368511d4be10000000a174cb4.html?locale=en-US)

If bank subaccounts that are usually posted to by the payment program (for example, the account for foreign bank transfers) have a special sort sequence, it is easier to process them when posting the bank statement.

The documents from the payment run contain, in their document header (field BKTXT), the date and identification number (for example, 19940301-ID) of the run. You can have the system automatically transfer this information to the Assignment field in the line item if you define a corresponding item sorting rule and enter this in the G/L account master record.

Subsequently, when entering a bank statement, via the Assignment field, you can select all the foreign transfers from a certain payment run in order to clear them.

###### Posting Separately by Business Area

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Specifications for Posting Payments > Bank Accounts and Bank Subaccounts > Posting Separately by Business Area | L10 | trm07 p.102 | loio `2704c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2704c55368511d4be10000000a174cb4.html?locale=en-US)

Use

If you have determined that the payments for a certain company code should be made separately per business area, then the bank posting is made to the business area of the paid items.

If you do not separate the payments by business area, you can specify that the bank postings should be made to one certain business area. To do so, specify the required business area for the bank account (see the figure above).

**Note:**

This specification is only effective if you do not already pay separately by business area.

In all other cases the postings to the bank subaccounts are carried out without reference to business areas.

###### Consistency Checks: Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Specifications for Posting Payments > Consistency Checks: Payment Program | L9 | trm07 p.102 | loio `2a04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2a04c55368511d4be10000000a174cb4.html?locale=en-US)

Use

During configuration of the payment program the checks usually carried out in the SAP System are performed. This includes a check as to whether the keys entered are defined in the system. If necessary the system issues a warning or error message.

**Example:**

You enter a document type for the payment postings that has not yet been defined. The system will issue an error message. If, however, you have specified for the bank posting a bank subaccount that has not yet been created, the system merely warns you.

After configuration of the payment program, you can have the system run a consistency check. During this, the system checks whether keys were entered during the configuration of the payment program that have since been deleted from the system.

**Example:**

You enter a business area for the bank posting. If you then delete this business area, you should also remove the corresponding entry from the payment program configuration. The consistency check shows you the appropriate key.

During the consistency check, the system runs the same checks as it did for the configuration.

You can request an additional log for the payment run. If the program did not settle certain open items, the reasons for this are detailed in this log. You can decide how to rectify the situation on the basis of this information.

###### Document Type for Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Specifications for Posting Payments > Document Type for Payments | L9 | trm07 p.102 | loio `2d04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2d04c55368511d4be10000000a174cb4.html?locale=en-US)

Use

You specify the document type which the payment program should use for posting the payments when making the country/region-specific specifications for the payment method. The document type must be defined using internal number assignment.

You can specify two document types for cross-company code payments. One document type is used for the document in the paying company code, the other for the clearing postings in the other company codes.

###### Posting Exchange Rate Differences: Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Posting Exchange Rate Differences: Payment Program | L8 | trm07 p.103 | loio `3004c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3004c55368511d4be10000000a174cb4.html?locale=en-US)

Use

Unless you specify otherwise, the payment program posts the exchange rate differences arising from foreign currency items. It does this by determining the difference between the rate at the time of posting and that when the item is paid. In order to determine the local currency amount at the time of payment, the payment program uses the exchange rates defined in the system.

If you do not want the exchange rate differences to be posted, you should specify this for the paying company code. See Specifications for the Paying Company Code . If you do so, the payment program calculates the equivalent payment amount in local currency on the basis of the local currency amounts in the paid items.

If the items to be paid have been reevaluated in the course of balance sheet preparation work, the adjustment postings to the receivables and payables accounts are reversed when the item is paid. At the same time, in order to determine the payment amount in local currency, the system also reads the valuation difference noted in the item.

**Note:**

If the payment program posts exchange rate differences, these actual exchange rate differences are noted in the cleared item. Such exchange rate differences are only temporary because the final difference can only be calculated when the bank statement is posted. It follows that you may have two exchange rate difference postings. If the payment program does not post any exchange rate differences, the cleared item does not then contain any information on realized differences. The exchange rate differences are not posted until the bank statement is posted. This method does not allow you to assign the differences to affiliated and non-affiliated companies for example. Further, it is not possible to retroactively assign the exchange rate variances to the business areas or cost centers which generated them.

###### Authorizations: Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Customizing of the Payment Program > Control of the Payment Program > Authorizations: Payment Program | L8 | trm07 p.103 | loio `3304c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3304c55368511d4be10000000a174cb4.html?locale=en-US)

You can assign authorizations for configuring and running the payment program. For further information, see under Financial Accounting Global Settings Authorization Management .

###### Execution of the Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program | L6 | trm07 p.103 | loio `3804c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3804c5536a51204be10000000a174cb4.html?locale=en-US)

The payment program is designed so that both outgoing and incoming payments can be processed. These functions are supported for payment transactions with suppliers and customers and between bank accounts (G/L accounts).

The payment program for payment requests uses the same components as the standard payment program (FI payment program) in Customizing, payment proposal processing and creation of payment media.

All the common payment procedures are in the standard system or can be set up within Customizing.

All default values used in the payment program are required in the following.

The payment program processes domestic and foreign payments for suppliers, customers and between bank accounts. It generates the payment program and provides the data for the payment medium programs. These ABAP programs print a payment list, payment forms (for example, checks) or generate data media such as magnetic tape or disk. A further possibility is the distribution of payment data to a cental system via ALE.

The standard system contains payment media programs and forms for the most common payment procedures. The system can also create payments on disk. It should be noted that payment forms and payment file formats are different from country/region to country/region and also sometimes from bank to bank. You will find details about payment forms and file formats of your country/region in the country/region-specific report documentation. SAPscript tools are used to design new payment forms and adapt existing forms. You will find a description in the basis documentation.

The payment medium program stores data in SAP print management and data medium exchange data in data medium exchange management. From there, the data is retrieved seperately per form/data medium and output via printer or data medium after the relevant forms (or a disk) have been inserted.

###### Selection for the Payment Run

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Selection for the Payment Run | L7 | trm07 p.104 | loio `3b04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b04c5536a51204be10000000a174cb4.html?locale=en-US)

The following describes the criteria used by the payment program to select payment requests to be settled for the forthcoming payment run.

**Prerequisites**

All necessary Customizing settings have already been made.

**Procedure**

The payment program processes the payment requests in three steps:

- 1. It determines the payment requests to be settled and creates a proposal list.
- 2. You can process the proposal list online. Amongst other things, you can change payment methods or banks, block items or cancel payment blocks.
- 3. The payment program makes the payments based on the proposal list. Only the open payment requests contained in the proposal list are taken into consideration. The payment program posts documents, sets up the data for the form printout and for creating the data media, the payment advice note and the payment summary.
- 4. It prints the forms and creates the data media with the payment medium programs.

###### Selection of Payment Requests (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Selection for the Payment Run > Selection of Payment Requests | L8 | trm07 p.104 | loio `3e04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3e04c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The payment program determines the due payment requests and selects which items must be paid. You use the payment run parameters to determine the exact time of the payment.

**Functions**

The selection of payment requests is based on several factors:

When the item is to be paid is basically determined by the due date which is in the payment request.

Prior to the payment run, you specify the date up to which due payment requests should be selected. The program then decides whether a payment request must be taken into account in the current payment run.

Whether a receivable or a payble is involved is not critical in the selection of the items to be paid.

Payment requests with status 'urgent' are always selected.

**Note:**

As payment requests only show net payments, no cash discount terms are supported. Furthermore, no grace days are taken into account for payment transactions with vendors and customers.

###### Blocking of Payment Requests

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Selection for the Payment Run > Blocking of Payment Requests | L8 | trm07 p.105 | loio `4104c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4104c5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

You can block payment requests that are not to be paid independently of their due date.

**Activities**

Enter a blocking key that represents the blocking reason in the item.

Should the business partner's account be blocked for payment, enter the blocking key in the master record of the business partner.

###### Overview of the Payment Run Procedure

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Overview of the Payment Run Procedure | L7 | trm07 p.105 | loio `4404c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4404c5536a51204be10000000a174cb4.html?locale=en-US)

This topic gives a general overview of the precautions and processing steps that need to be taken to execute a payment run.

Planning and parameter specifications

If you have several house banks that you can use for your payment transactions and are limited to the funds available in these bank accounts, you will have to plan the cash balances available for each bank account and specify the ranking order by which the program is to use these accounts. The house bank can also be entered in the payment request. This is absolutely necessary for payments between bank accounts. In this case, this house bank is always used, independent of the ranking order or the available amounts.

Before every payment run, you need to specify which company codes, account types and accounts to include in the payment run. Furthermore, you have to enter the desired posting date, the possible payment methods and the date of the next payment run. There are also some other optional specifications that you can make.

Creating the Payment Proposal

Once the specifications for the payment run are complete, you can schedule the payment proposal by either specifying a particular start date and time or executing the run immediately. The status display shows you which step the job is currently at.

If the payment proposal is created, the system first checks the results, reading the proposal log and recording any exceptions in it.

By displaying or printing the payment proposal list or by editing the payment proposal, you can get an overview of the payments proposed by the program.

Editing the Payment Proposal

You can process the payment proposal according to accounting clerk by specifying the accounting clerk ID from the master record after accessing the function to edit the proposal.

When processing the payment proposal, you can make changes to the payment (payment method, house bank) and the items paid (block indicator, cash discount). All changes you make affect only the payment proposal. No changes are made to the original documents.

Once you have accepted the payment proposal or have finished editing it, you can schedule the payment run. The job created for the payment run will contain either only the payment program as one step or an extra step for each payment medium program and each variant. In the latter case, you need to specify which variants to use for each payment medium program prior to scheduling the payment run. In scheduling the run, you specify the desired start time and the print programs.

If you want to run only the payment program first, you can schedule the print programs for a different time in a separate job.

###### Selecting Banks and Planning Available Amounts

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Selecting Banks and Planning Available Amounts | L7 | trm07 p.106 | loio `3604c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3604c55368511d4be10000000a174cb4.html?locale=en-US)

Use

The payment program helps you to optimize your payments. To schedule your cash receipts and payments, you must:

Define the bank selection

Define the available amounts These specifications will depend on the size and structure of your organization.

Defining Bank Selection

If you have several bank accounts for the same payment method and the same currency (for example, check accounts in local currency), you can define the sequence by which the payment program is to use these bank accounts. If the funds of the first bank account are exhausted, the payment program automatically selects the second bank account, and so on.

Defining Available Amounts

You can define, per bank account, up to what amount of receipts and payments can be carried out through that account. This can be of benefit, for example, if you want to preserve the ability to pay for an item which is not made by the payment program.

Graphic

The figure Bank Selection shows how the principles of bank selection and control of available amounts work.

###### Bank Selection (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Selecting Banks and Planning Available Amounts > Bank Selection | L8 | trm07 p.106 | loio `3904c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3904c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F042]

###### Sample Bank Selection and Control of Available Amounts

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Selecting Banks and Planning Available Amounts > Sample Bank Selection and Control of Available Amounts | L8 | trm07 p.107 | loio `3c04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c04c55368511d4be10000000a174cb4.html?locale=en-US)

You want to use the payment program to pay five open items to five different suppliers:

Payment to first supplier 40,000

Payment to second supplier 30,000

Payment to third supplier 20,000

Payment to fourth supplier 7,000

Payment to fifth supplier 12,000

Sample Bank Selection

|Available Amounts for Automatic Payments|Bank A Prio 2|Bank B Prio 1|Note|
|---|---|---|---|
|Before debit memo from first customer|70,000|50,000| |
|After debit memo for first customer (40,000)|70,000|10,000|Bank B Prio 1|
|After debit memo for second customer (30,000)|40,000|10,000|Insufficient amount at bank B|


|Available Amounts for Automatic Payments|Bank A Prio 2|Bank B Prio 1|Note|
|---|---|---|---|
|After debit memo for third customer (20,000)|20,000|10,000|Insufficient amount at bank B|
|After debit memo for fourth customer (7,000)|20,000|3,000|Bank B Prio 1|
|After debit memo for fifth customer (12,000)|8,000|3,000|Insufficient amount at bank B|

###### Procedure for Controlling Bank Selection

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Selecting Banks and Planning Available Amounts > Procedure for Controlling Bank Selection | L8 | trm07 p.108 | loio `4704c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4704c5536a51204be10000000a174cb4.html?locale=en-US)

To access the entry screen for execution of the payment program for payment requests, choose Financial Accounting Treasury Treasury Management Money Market/Foreign Exchange/Derivatives/Securities Accounting Payment Payment Request .

Determining the ranking order of bank selection

- 1. Choose Environment Configuration . This takes you to the screen entitled Configuration Payment Program for Payment Requests.
- 2. Choose Configuration Standard Setting . This takes you to the screen entitled Configuration Payment Program: Initial Screen.
- 3. Choose Banks Bank Selection . You see a list of company codes for which payment methods have been defined.
- 4. Choose a company code for which you want to make your specifications.
- 5. Give the ranking order for every payment method (starting with 1) and the bank ID of the bank which is to be used for payments.


Only make an entry in the currency field if another ranking order is to apply, depending on a certain currency. If this is the case, insert corresponding entries for this currency.

Determining available sums of money for bank accounts

- 1. Choose Environment Configuration . This takes you to the screen entitled Configuration Payment Program for Payment Requests.
- 2. Choose Configuration Standard Setting . This takes you to the screen entitled Configuration Payment Program: Initial Screen.
- 3. Choose Banks Available Amounts . You see a list of company codes for which payment methods have been defined.
- 4. Choose a company code for which you wish to make your specifications.
- 5. For every bank, account and currency, enter the available sum of money in the column entitled Outgoing Payment. If there is no entry for the currency, the entry is valid in local currency.


With this, determine the maximum amount which the payment program can take from this account.

If you always have sufficient means of payments in all your bank accounts, you can enter the amount 9,999,999,999 for all banks, accounts and currencies during the setting up of the system.

###### Parameters for the Payment Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Parameters for the Payment Program | L7 | trm07 p.109 | loio `3f04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f04c55368511d4be10000000a174cb4.html?locale=en-US)

After setting the corresponding defaults, maintain the parameters for the payment run. To do this, specify, among other things, which accounts are to be settled, which payment methods are allowed, and the date of the current and the next payment run. In addition, determine the variants for the form printout and data carrier reports.

When maintaining the parameters, you can also define the payment medium variants for form printing and generating the data carrier. Alternatively, you can leave defining the payment medium programs until you plan the payment run.

Parameter maintenance involves determining the following for the payment run:

Entering Basic Data

Specifying payment medium programs

Entering Additional Specifications for a Bill of Exchange

Defining additional parameters (optional)

Additional log

Payment restrictions

Authorizations

###### Entering Basic Data

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Parameters for the Payment Program > Entering Basic Data | L8 | trm07 p.109 | loio `4a04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4a04c5536a51204be10000000a174cb4.html?locale=en-US)

**Prerequisites**

You make settings in Customizing to determine which of the following fields should appear when you enter basic data (payment parameters) and which are ready for input:

Supplier accounts

Customer accounts

G/L accounts

Creation date

Origins (for example, application component, Treasury Management)

You do this via Financial Accounting Bank Accounting Business Transactions Payment Transactions Payment Handling Define Global Settings .

If you wish to select payment requests via the origin, you must check the settings for the origin.

You do this via Financial Accounting Bank Accounting Business Transactions Payment Transactions Payment Handling Enter Origin Indicators Assign Origin for Clearing of Payments .

**Procedure**

- 1. Choose Accounting Treasury Treasury Management Money Market/Foreign Exchange/Derivatives/Securities Accounting Payment Payment Request .


Enter the planned day of execution and an ID for this parameter group. Press Enter .

You receive the message that no parameters have been entered.

- 2. To create the parameters, choose Edit Parameter Maintain .
- 3. Enter the posting date for payments and the due date for payment requests.
- 4. Enter one or several company codes or corresponding intervals.
- 5. Enter the keys of the payment methods that are to be used in this payment run.

The sequence of the keys determines which methods are used to pay open items with priority, when no particular payment method has been specified in the open item or master record.

- 6. Enter the account numbers of suppliers, customers and G/L accounts to be included in this payment run.


**Note:**

Due payment requests are not processed by the payment program after this date.

**Note:**

Payment requests for which no payment method has been specified (only possible for suppliers and customers) can be paid with various payment methods (such as check (C), transfer (T)), if they have been defined in the master record.

If you enter US in the parameters, the system first checks whether payment can take place via payment. If that is not possible (due to inconsistencies in the bank details), then the system checks whether payments can be made via check.

With payment requests for bank account payments, payment methods must always be explicitly specified.

###### Specifying the Payment Medium Program and Variants

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Parameters for the Payment Program > Specifying the Payment Medium Program and Variants | L8 | trm07 p.110 | loio `4204c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4204c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

There is one payment medium program for each payment method. This program prints the payment forms or creates the data media on disk. You can specify different payment medium programs for the payment methods you specify in the payment parameters.

**Procedure**

On the Automatic Payment Transactions screen, select the Printout/data medium tab.

Enter one or more variants for every payment medium program used to print the payment data for a payment method.

You can also specify variants for creating the payment proposal list (RFZALI00) and exception list (RFZALI10) on this screen.

You can find further information on payment medium programs and variants in Printout Control and in Creating a Payment Medium Report Variant .

###### Defining an Additional Log

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Parameters for the Payment Program > Defining an Additional Log | L8 | trm07 p.110 | loio `4504c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4504c55368511d4be10000000a174cb4.html?locale=en-US)

You can define criteria for an additional log. If you call up the log later on, the system displays the processing logic of the payment program in appropriate detail. Before doing anything, you should read the note under Checking the Log in "Creating the Payment Proposal".

The following processing steps can be logged.

Due date check

Payment method selection in all cases

Payment method selection if not successful

Payment document items

**Procedure**

For the additional log, choose the Additional log tab on the Automatic Payment Transactions screen . Click next to the corresponding option and enter the account numbers of the vendors or customers.

###### Restricting Payments: Additional Criteria

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Parameters for the Payment Program > Restricting Payments: Additional Criteria | L8 | trm07 p.111 | loio `4d04c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4d04c5536a51204be10000000a174cb4.html?locale=en-US)

You can restrict your payments according to further criteria. Maybe you would like to clear payment requests within certain postal code areas or first pay the invoices that are issued in local currency.

To do this, proceed as follows:

- 1. Choose Edit Free Selections .
- 2. Enter values for further restrictions or determine other fields to be used for restriction via Edit New Field Selection New Table Selection .
- 3. The fields can be selected after flagging via copying. All fields of the payment request and the master data for the individual account types are possible. You can select individual values and intervals that can be used or also ruled out.
- 4. Choose Selections Copy .
- 5. On the parameters screen, you now see the number of active free selections displayed.

###### Entering Authorizations

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Parameters for the Payment Program > Entering Authorizations | L8 | trm07 p.111 | loio `4804c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4804c55368511d4be10000000a174cb4.html?locale=en-US)

When entering the payment parameters, you can restrict the authorization to change the payment parameters to a limited number of users. Proceed as follows:

- 1. Choose Edit Authorized users .
- 2. Enter the SAP user names of the users to whom you are giving authorization to change the payment parameters.
- 3. To continue, choose Continue .

###### Copy Parameters

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Parameters for the Payment Program > Copy Parameters | L8 | trm07 p.111 | loio `4b04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b04c55368511d4be10000000a174cb4.html?locale=en-US)

To speed up data entry, you can copy the parameters of another payment run.

**Procedure**

1. Choose Parameters Copy .

A window appears in which you enter the run date and ID of the parameter set that you want to use as a reference.

1. Choose Continue .

The payment program automatically copies the parameters. You can overwrite individual entry fields.

###### Creating the Payment Proposal

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Creating the Payment Proposal | L7 | trm07 p.112 | loio `4e04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e04c55368511d4be10000000a174cb4.html?locale=en-US)

**Purpose**

After you have specified all parameters for the payment run, the payment proposal can be created.

The payment proposal displays the open items whose payment is proposed by the payment program (depending on its configuration). The criteria that determine the selection of the open items are described in detail in Selecting Open Items .

**Process Flow**

The figure Creating a Payment Proposal shows the theoretical procedure behind the creation of a payment proposal.

###### Creating a Payment Proposal

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Creating the Payment Proposal > Creating a Payment Proposal | L8 | trm07 p.112 | loio `5104c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5104c55368511d4be10000000a174cb4.html?locale=en-US)

[figure TRM07-F043]

###### Planning a Payment Proposal

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Creating the Payment Proposal > Planning a Payment Proposal | L8 | trm07 p.113 | loio `5404c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5404c55368511d4be10000000a174cb4.html?locale=en-US)

In order to plan a payment proposal, proceed as follows:

- 1. Choose Edit Proposal Plan .
- 2. Enter the start date and time.
- 3. If the payment program is to immediately create the payment proposal, you must click in the field Start immediately.
- 4. If you want to test the payment medium programs using the dunning proposal data, select the option with print programs . This is generally only useful in the testing and configuration stages.
- 5. Choose ENTER .


****Note:****

As well as the payment medium programs you can also schedule the reports for generating the payment proposal list (RFZALI00) and the exception list (RFZALI10). The names of these reports have been entered beforehand using PRINT PROGRAMS .

The additional option With lists then appears in a pop-up window.

Status Display

The system tells you that the proposal is being processed. Each time you choose ENTER , the current status of the proposal run is displayed. Upon completion of the job, the message that the proposal run has been executed appears.

###### Checking the Log

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Creating the Payment Proposal > Checking the Log | L8 | trm07 p.114 | loio `5704c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5704c55368511d4be10000000a174cb4.html?locale=en-US)

After you have created the payment proposal, you should call up and read the log. To do this, choose Edit Proposal Display log .

The log informs you of possible configuration errors. In this case, no payment is possible. You must correct the errors, delete the payment proposal, and carry out a new payment proposal.

**Note:**

If you entered criteria for an additional log during parameter maintenance (for example, payment method selection in all cases) the log will be more extensive processing will take longer. An additional log is only to be defined in exceptional situations or for testing purposes.

###### Displaying the Payment Proposal

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Creating the Payment Proposal > Displaying the Payment Proposal | L8 | trm07 p.114 | loio `5a04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a04c55368511d4be10000000a174cb4.html?locale=en-US)

When you displaying the payment proposal, you can also gives you the capability to monitor its contents. Every payment is displayed, even if you divided processing between different accounting clerks. Following processing, you can view the payment proposal again to see which changes have been made, and by which clerks.

To display the payment proposal, choose Edit Proposal Display. To obtain a general overview of the created payments, use the functions Sort and Search.

###### Generating a Proposal List

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Creating the Payment Proposal > Generating a Proposal List | L8 | trm07 p.114 | loio `5d04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5d04c55368511d4be10000000a174cb4.html?locale=en-US)

To generate a complete proposal list, choose Edit Proposal Proposal List .

A window displaying the program name (RFZALI00) will appear. If a variant was set up, enter the variant name and choose ENTER.

You then receive a complete overview of all payments and line items.

The end of the list contains a breakdown of the payment amounts sorted by:

Business Areas

Countries/Regions

Currencies

Payment Methods

Banks

You can view this information online or print it out.

###### Evaluating the Exception List

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Creating the Payment Proposal > Evaluating the Exception List | L8 | trm07 p.115 | loio `6004c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6004c55368511d4be10000000a174cb4.html?locale=en-US)

In addition to the proposal list, you can display or print out an exception list. The exception list displays blocked items and all open items which the payment program did not propose for payment.

The exception list contains:

Blocked items

Special G/L transactions (depending on the configuration of your system)

Items that could not be settled despite being due

The reason for the exception is represented by an error number. The list includes an error text for every error reason.

To generate an exception list, choose Edit Proposal Exception list .

This brings up a window with the name of the program (RFZALI10). If you want to print the list, enter the appropriate variant name and chooseENTER.

###### Editing the Payment Proposal (Online)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Editing the Payment Proposal (Online) | L7 | trm07 p.115 | loio `6304c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6304c55368511d4be10000000a174cb4.html?locale=en-US)

Once the payment proposal is created, you can edit it online. Both payments and line items can be processed and edited.

You can divide payment proposal processing between different clerks. It is therefore possible for several people to process extensive proposal runs in parallel. You can then use the display function to track what changes were made and who made them.

All changes made when editing the payment proposal affect only the payment proposal. All changes you make affect only the payment proposal. No changes are made to the source documents.

###### Editing Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Editing the Payment Proposal (Online) > Editing Payments | L8 | trm07 p.115 | loio `6604c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6604c55368511d4be10000000a174cb4.html?locale=en-US)

You can use the following functions to help you edit payments:

Sort

Search

Change line layout

Totals display

To process payments, choose Edit Proposal Edit Proposal . The system displays a dialog box in which you can choose whether to edit every payment (all clerks) or only those for which you are responsible (clerk ID code).

The payments selected are then listed on the next screen (list level 1). One line item is displayed per payment. If there are any exceptions for an account (for example, blocked items), an additional line item appears in the list.

**Sorting Payments**

You can sort payments by certain criteria. To do this, choose Edit Sort . Choose the desired sort criteria and sequence.

You can select up to four fields as sort criteria. To do this, either enter the numbers 1 through 4 in the respective fields, or doubleclick in each field in the appropriate order (the number one will appear in the first field selected, the number two in the second, and so on).

**Searching for Payments**

You can shorten the payment list by searching for particular payments. To do this, choose Edit Find . Select the type of payment field you want to search for, for example, Amount Paid in Local Currency. In the dialog box that follows, enter the appropriate values or value ranges.

The system now searches for the payments you searched for and displays these in a list. To narrow down the number of payments still further, choose Edit Find again, and enter a further search criterion, for example, Payment Method.

**Changing the Line Layout**

To change the line layout, choose Settings Line Layout , and then select the desired line layout in the dialog box.

**Totals Display**

You can display the total of proposed payments using four summarization levels. To do this, choose Goto Display Totals . You can then select the desired summarization level.

Select the required summarization level and choose ENTER . To list the summarization levels in another sort sequence, choose Edit Sort . A window appears in which you can change the sequence of the totals display.

To enter the sequence in the respective fields, enter the numbers 1-4 manually, or place your cursor in each field and select Choose. Alternatively, enter the numbers by double-clicking in each field.

**Note:**

The standard settings for the Sort, Find, Change Line Layout, and Display Totals functions depends on your system configuration, and can be changed in Customizing.

###### Changing Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Editing the Payment Proposal (Online) > Changing Payments | L8 | trm07 p.116 | loio `6904c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6904c55368511d4be10000000a174cb4.html?locale=en-US)

In editing payments online, you can change the:

Payment method

House bank

Due date

To do this, position the cursor on the payment you want to change, and choose Edit Change . The system displays a dialog box in which you can change the payment method and house bank.

Changing the Payment Method

To change the payment method, simply enter a new indicator, and then choose Continue .

The system checks whether your entry is permissible. If it is not, an error message appears. You can only use payment methods:

Which were preset with the parameters of the payment run.

For which the necessary specifications, for example, bank details for a wire transfer, are available in the master record.

Changing the House Bank

To change the paying house bank, enter the required bank name and account ID. Then, choose Continue .

The system checks whether the selected bank was set up in Customizing. If not, an error message appears.

Changes you make are only effective once you save them.

**Note:**

When making changes to a lot of payments, you should save your data frequently. By choosing Environment Payment changes , you can display the change history and also see which changes have not yet been saved.

Changing a Payment Due Date

You can enter a new payment due date. The new date cannot be before the payment run date or - except for bill of exchange payments - be more than 30 days after the payment run.

###### Editing Line Items

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Editing the Payment Proposal (Online) > Editing Line Items | L8 | trm07 p.117 | loio `6c04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6c04c55368511d4be10000000a174cb4.html?locale=en-US)

You can edit line items for a payment or an exception list at a second list level. You can use the following functions to help you edit line items:

Sort

Search

Change line layout

To edit line items of a payment, double-click the desired payment line.

The system then displays the open items of this payment on another screen.

**Sorting Line Items**

To sort open items, choose Edit Sort . This brings up an additional window where you can sort the line items according to four criteria and define a sequence (see "Sorting Payments" in Editing Payments).

Searching for Line Items

To search for particular open items, choose Edit Find . Select a search criterion and enter the desired values or value ranges (see "Searching for Payments" in Editing Payments).

**Changing the Line Layout**

To change the line layout, choose Settings Line Layout , and select the required line layout variant. There are four variants delivered with the standard system.

**Note:**

The standard setting for the Sort, Find, Change Line Layout, and Display Totals functions depends on your system configuration. You can change it in Customizing.

###### Changing Line Items

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Editing the Payment Proposal (Online) > Changing Line Items | L8 | trm07 p.118 | loio `6f04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6f04c55368511d4be10000000a174cb4.html?locale=en-US)

In online editing of line items, you can:

Block or unblock line items

Change the cash discount amount

Assign line items to another payment

To make these changes, position the cursor on the line item you want to change, and choose Edit Change .

**Blocking/Unblocking Line Items**

To block open items for this payment run, enter a block indicator in the Payment Block field and choose Continue.

A blocked line item is indicated in the list display with an arrow (<--). This means that the open item no longer belongs to the payment. If you now display the list of payments by pressing F3 (Back), you see that the blocked line item has been transferred into the group of exceptions and the outgoing payment has been reduced by the corresponding amount.

To reset a block indicator, position the cursor on the exception list in question and select Choose. Position the cursor on the items that you want to unblock and choose Edit Change . Overwrite the block indicator in the dialog box.

**Note:**

In a payment proposal, you can set and delete only those block indicators that can be edited. Block indicators that can be edited are determined in Customizing.

**Changing the Cash Discount Amount or the Cash Discount Rate**

To change the cash discount amount, place the cursor on the Cash Discount field or the days for cash discount, and change the amount.

**Assigning Line Items to Another Payment**

You can remove line items from one payment and assign them to another one. To do this, choose Reassign in the change dialog box. If there are other payments for this account in the proposal, the system will list the payments to which you can assign the item. Select one of the displayed payment methods by selecting Choose.

You can even create a new payment for the item. To do this, choose New Payment , and enter the payment method, house bank, and account into the fields provided. If no other payment exists for the account, you will have to create a new payment to assign the item to.

After you choose Continue, the system checks whether your entries correspond to the payment program configuration. If they do not, an error message appears.

Open items you assign to another payment are indicated by an arrow (<--) in the list displayed. The arrow indicates that this item will be removed from the current payment and transferred to another, once you save the data.

If you return to the first list level from the open item display, you can see the newly added payments. These are marked with an arrow (-->) prior to saving the changes.

Changes you make become effective only if you save them.

**Blocking All Items of a Payment**

If you want to block all items of a payment, you can do this by choosing Block All.

**Note:**

When making changes to a lot of open items, you should save your data frequently. By choosing Environment Line Item Changes , you can display the change history and also see which changes are not saved yet.

###### Running the Payment and Payment Medium Programs

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs | L7 | trm07 p.119 | loio `7204c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7204c55368511d4be10000000a174cb4.html?locale=en-US)

Once you have edited and accepted the proposal, you can plan the payment run. Several programs are used in creating the payments:

The payment program creates the payment documents and prepares the data for printing the forms or creating the tape or disk.

Various payment medium programs use the data prepared by the payment program to create forms or files for the data media.

Basic Procedure

You can choose from the following options when carrying out the payments:

You can schedule just the payment program first, and then once the run is completed successfully, you can schedule the payment medium program.

Or you can schedule the payment program and the payment medium program at the same time.

Or you can execute the payment program first, and then once the run is completed successfully, you can execute the printout online.

###### Printout Control

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs > Printout Control | L8 | trm07 p.119 | loio `7504c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7504c55368511d4be10000000a174cb4.html?locale=en-US)

Use

You can carry out a payment run for different company codes, payment methods, and business partners even though different forms or data carriers may have to be printed or created for each payment method and company code. To distinguish between the different types of forms and media, you use variants in the payment medium programs.

Variants are defined when configuring the payment program. You can define as many variants as you require for each payment medium program. You have to define at least one.

The names of the payment medium programs for the individual countries/regions have the following naming conventions:

RFFO<Country/region indicator>_<Payment method>

**Example:**

The program titled RFFOUS_T generates bank transfers in ACH format for the USA.

You can find the names of the payment medium programs in the country/region-specific payment method data (in the system configuration tables).

###### Functions of the Variants

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs > Functions of the Variants | L8 | trm07 p.120 | loio `5004c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5004c5536a51204be10000000a174cb4.html?locale=en-US)

Variants contain a series of selection criteria that separate the payment dataset.

Each variant called up in a payment medium program triggers a separate print request in the output controller or creates a separate file in DME administration. Print requests are displayed in the output controller.

You can call up the print requests individually for printing.

###### Checking the Payment Log and Payment List

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs > Checking the Payment Log and Payment List | L8 | trm07 p.120 | loio `7804c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7804c55368511d4be10000000a174cb4.html?locale=en-US)

Prior to printing the forms, you should view the payment log and check over the payment list to make sure that the payment run was completed successfully.

To check the payment run, read the payment log and check the payment list before you print the forms.

To call up the payment log, choose Edit Payment Display log.

To display the payment run, choose Edit Payment Display .

You can use the search and sort functions in this display to get a quick overview of the payments. Moreover, you can display a history of the changes made to the payment proposal, which will show which clerks made which changes. To do this, choose Edit

Proposal Display.


To simply display and print the payment run, choose Edit Payment Payment list.

###### Executing the Payment Medium Programs Separately

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs > Executing the Payment Medium Programs Separately | L8 | trm07 p.120 | loio `7b04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b04c55368511d4be10000000a174cb4.html?locale=en-US)

Always ensure that the payment run and ensuing postings have been successfully completed before starting the payment medium program. In the status display, you can see how many documents were created and how many of them have already been posted.

You must have your required variants already defined in the system for the payment medium program. For more information on how to define these variants, see Creating a Payment Medium Report Variant.

The following steps describe how to execute the payment medium programs separately from the payment run. If you have already entered variants for the payment medium programs, skip to step 4 below.

- 1. Choose Edit Print Programs from the Automatic Payment Transactions screen. You then reach the screen for entering variants.
- 2. Check whether the required variants have been entered. If not, enter the variants created for the data medium exchange into the corresponding payment medium program.
- 3. Choose Parameters Save . You will again reach the Automatic Payment Transactions screen.
- 4. In the Automatic Payment Transactions screen, choose Edit Payments Schedule print... . A dialog box appears.
- 5. Enter the required start date and specify the job name.


The program will now generate, for each variant, separate files in the output controller where you select and print them separately. The numbers of the generated print requests can be found in the print run log.

- 1. Choose System Services Output controller . You will then reach a screen from which you can access the print requests. If necessary, reset the date to the print run start date.
- 2. Choose Spool request List . The next screen lists the print requests.
- 3. For each job, enter the corresponding form and position the cursor in the system on the appropriate print job. If several printer connections exist, you will be able to carry out several print jobs simultaneously by selecting them as well.
- 4. Choose Display to view the forms on your monitor.
- 5. Choose Spool request Print to print the forms.


Files may also be generated for data medium exchange. You can access DME administration via Environment DME administration . You can access further information on DME administration under Data Medium Exchange and Data Medium Administration.

###### Scheduling the Payment Program and Payment Medium Programs Jointly

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs > Scheduling the Payment Program and Payment Medium Programs Jointly | L8 | trm07 p.121 | loio `7e04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7e04c55368511d4be10000000a174cb4.html?locale=en-US)

To be able to execute the payment program and payment medium program jointly, you must have entered the payment medium program variants. You can read how to do this in Running the Payment and Payment Medium Programs .

To schedule the payment and payment medium programs jointly, proceed as follows:

- 1. Choose Edit Payments Schedule payment .
- 2. Enter the start date and time for the background job in the additional window.
- 3. Select the option With print programs .
- 4. SelectENTER .


**Note:**

The documents generated by the payment program are first saved to the log file and then posted later. This makes it possible for all documents to be available only a short time after the end of the payment run.

Some payment medium programs require information from the posted documents for form printing, with others you can switch on a check of the posted documents with parameter settings. In these cases, you must first ensure that the programs only start if all payment documents are posted. This can only be guaranteed if the payment medium programs are separately scheduled for a later point in time.

In the status display, you can see how many documents were created and how many of those have already been posted.

###### Starting the Payment Medium Programs Online

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs > Starting the Payment Medium Programs Online | L8 | trm07 p.122 | loio `8104c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8104c55368511d4be10000000a174cb4.html?locale=en-US)

In order to avoid unnecessarily burdening the system while it is up and running, you should only start payment medium programs online for

Small payment runs

Additional generation of individual payment media

Cases in which an interactive processing is required, such as error searches.

To start online printing, proceed as follows:

- 1. Choose System Services Reporting .
- 2. Enter the name of a payment medium program, for example RFFOD__S , and execute the program, with variants if necessary. You must also enter at least the payment run date and the payment run ID.
- 3. Execute the program.


On the next screen, you will find information on the generated payment media. You can go to the print administration or DME administration programs with a double-click on the output file.

###### Recognizing and Eliminating Form Printing Errors

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Running the Payment and Payment Medium Programs > Recognizing and Eliminating Form Printing Errors | L8 | trm07 p.122 | loio `8404c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8404c55368511d4be10000000a174cb4.html?locale=en-US)

Various errors can occur while printing forms, for example

Termination of Processing

The cause for program termination (i.e., the production run had not been carried out yet, the form does not exist or is not active) will be reported in the error message and in its accompanying help text.

Internal SAPScript error

Check the structure of the form. It has to be in compliance with the parameters listed in the program documentation. For example, it is not possible to generate a transfer via the check printing program, since transfers and checks have a completely different form structure.

Error Log

If errors which do not cause the payment program to terminate abnormally occur as the task is being generated, they will be listed in the error log. If such an error log is indeed generated, it must be reviewed. You then need to decide whether the error rendered the payment medium or payment advice notes invalid, and whether they need to be newly created after you have eliminated the condition that caused the error.

In background processing, the error log will be output twice, once in the job run log and once in the print job file. You can find useful information regarding these errors in the error message help texts which are output with the run log.

###### Data Medium Exchange and Data Medium Administration

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration | L7 | trm07 p.123 | loio `8704c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8704c55368511d4be10000000a174cb4.html?locale=en-US)

Use

This topic first describes the available functions in FI for generating data carriers, and second, the data medium administration functions that help in the administration of generated data carriers.

In Data Medium Exchange (DME), a file containing all payment information and corresponding to the banking rules for the country/region in question, is generated. For example, banks in Germany require MS-DOS files in DTAUS0 format for payments by domestic transfer or direct debits. For these same transactions in the USA, ACH format is needed, and BACS format is used in Great Britain.

Depending on the specifications for Data Medium Exchange in your country/region, you may be able to use various methods to store data created by the payment program:

In the SAP System (TemSe). This is the case for Germany, Austria, Switzerland, Belgium, France, the USA, and Denmark.

In the file system. This is the case for Great Britain and Norway, for example.

Not at all. In this case, you can only print forms.

###### Outputting the DME File into the SAP System

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration > Outputting the DME File into the SAP System | L8 | trm07 p.123 | loio `8a04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8a04c55368511d4be10000000a174cb4.html?locale=en-US)

Use

If required, you can store the file you have created within the SAP system (the file is stored in the TemSe rather than in the file system). This way the file cannot be accessed by unauthorized external users. You can then download the file into the user’s file system using one of the DME administration functions.

You can determine the name of the file to be created during the download when running the payment medium program: the contents of the file name parameter are stored in the administration data and are proposed when running the download.

###### Outputting the DME File into the File System

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration > Outputting the DME File into the File System | L8 | trm07 p.123 | loio `8d04c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8d04c55368511d4be10000000a174cb4.html?locale=en-US)

Use

If required, you can write the file into the file system. You can also copy the file to the PC from the file system of the application server using the download function of DME administration.

The name of the file can either be created by the system or be defined by the user. If the file name is assigned by the system, it consists of the disk format, date and time of creation and also a consecutive number. This ensures the file names in the file system are always unique. The file name assigned by the system can be taken from the payment medium program log.

If you want to assign the file name yourself, you can create a variant for data medium exchange (per house bank if required), within which you define a file name. Note that the system likewise adds a consecutive number to the file name so that the name is unique for each program run. From an organizational point of view, you should make sure that files that already exist are not overwritten.

**Note:**

If you cannot find the file using DME administration, this could be due to the following reason: The directory that was written to when the payment medium program was started (for example, in background processing), cannot be read online. You should therefore choose a directory that can be written to and read by different machines.

Due to the problems mentioned above and the effect this has on data security, it is advisable not to write data to the file system. It may be advisable, however, to use this method if the DME file is "picked up" from the file system by an external program to be passed on to the bank.

###### Creating a Payment Medium Report Variant

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration > Creating a Payment Medium Report Variant | L8 | trm07 p.124 | loio `9004c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9004c55368511d4be10000000a174cb4.html?locale=en-US)

To create a report variant for DME, proceed as follows:

- 1. Choose System Services Reporting . This takes you to the initial screen for report processing.
- 2. Enter the name of the payment medium program for which you want to create a variant and choose Goto Variants . You reach the screen for maintaining variants.
- 3. Enter a variant name and choose Variants Create .
- 4. Select the field Data medium exchange, then enter the name of the printer. This is necessary so that the system can prepare the form for the accompanying sheet that is created during DME. Also select the field Print immediately if required.
- 5. Select the field Issue payment advices (if this field exists), then enter the name of the printer. Also select the field Print immediately if required.
- 6. Select the field Print payment summary, then enter the name of the printer. Also select the field Print immediately if required.
- 7. Make an entry in the field File name (for DME) as follows:
- 8. For outputting into the file system, enter the name under which the file generated is to be stored in the file system (as long as you have elected not to have the system generate a name).

For outputting into the SAP system, enter the name which, if required, is to be proposed later when running the download.

- 9. Choose Variant Save .

###### Running the Payment Medium Program

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration > Running the Payment Medium Program | L8 | trm07 p.124 | loio `9304c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9304c55368511d4be10000000a174cb4.html?locale=en-US)

You should run the payment medium program upon successful completion of the payment run - that is, when the status information Payment Run Carried Out is displayed on the Automatic Payment Transactions screen and a message appears to say that all documents were posted. Starting from this screen, proceed as follows:

- 1. Choose Edit Print Programs . This takes you to the screen for entering variants.
- 2. For the relevant payment medium program, enter the variant entered for the DME.
- 3. Choose Parameters Save . This takes you back to the Automatic Payment Transactions screen.
- 4. Choose Edit Payment Schedule Print .
- 5. In the dialog box that appears, enter the required start time and a name for the print job.
- 6. Select Enter.

###### Data Medium Administration

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration > Data Medium Administration | L8 | trm07 p.125 | loio `a740c2531bb9b44ce10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a740c2531bb9b44ce10000000a174cb4.html?locale=en-US)

**Use**

Data medium administration (DME administration) helps you to manage the data media that you create in Financial Accounting and in Human Resources.

In the Accounts Receivable or Accounts Payable menu, choose Periodic Processing Payments . The system displays the Automatic Payment Transactions: Status screen. From here, choose Environment Payment Medium DME Administration to reach the DME administration screen.

In the Payroll country/region menus, choose Payroll Bank transfer DME management .

In the DME administration overview, the system displays all the data media created with the selection criteria you have specified. You can call up further information for each data medium. Select the required data medium.

**Features**

DME administration includes the following functions:

Displaying data medium attributes

Choose Extras DME Attributes .

The system displays the following information for the selected data medium:

Payment run ID

House bank or clearing house

Date and time of data medium creation

Responsible person

Amount paid in currency specified

Further technical data

Deleting an individual or several data media

The accompanying administrative data is deleted from the system at the same time.

Select the required data medium and then choose Edit Delete Data Medium . A confirmation prompt appears. The selected data media are deleted when you confirm this prompt.

If you wish to delete data media from several company codes, then you should use the reorganization function within the payment program.

See also:

Deleting DME Administrative Data Across Company Codes

Downloading one or more files from the SAP system or from the file system to hard drive or disk

See also:

Downloading a DME File onto Disk

Displaying the contents of a data medium on the screen or printing the contents

Choose Edit Display DME Contents from the DME administration overview screen.

**Note:**

The following functions are not available for payments from Human Resources (HR).

Displaying Documents

Choose Extras DME Attributes and then Environment Display documents and then Environment Display Documents . By selecting Choose, you branch into the selected payment document.

Displaying the transferred data after receiving and entering the account statement

To do this, choose Extras Bank Transaction Attributes from the DME administration overview screen. If your electronic account statements are processed automatically, then the system fills in the fields within the Account Statement group.

Printing the payment summary for the selected data medium

To do this, choose Extras Payment Summary from the DME administration overview screen.

Creating a payment advice note

If you do not use the automatic transfer of electronic account statements but instead enter the account statement data manually, you can simplify this work by means of payment advice notes within DME administration.

You can create a payment advice note for a specified data medium using Environment Generate Document Payment Advice . You can enter this payment advice number at a later stage when clearing the bank clearing account. During clearing, the system then only proposes those open items which belong to the payments specified in the payment advice.

You can find more information on the use of this function in Great Britain, (for the creation of a Telepay file, for example) in the documentation of report RFFODTA1.

###### Downloading a DME File onto Disk

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration > Downloading a DME File onto Disk | L8 | trm07 p.126 | loio `9604c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9604c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

The downloading function within DME administration enables you to create a copy of the data medium on your PC. This procedure is logged in the system. You can create as many duplicates of a data medium as you wish. Only the administrative data from the last download is stored in the system.

When writing a file to drives A or B, you can also assign a volume label. To print the relevant volume number onto your disk accompanying sheet when running the payment medium program, maintain the symbol &REGUD-LABEL& in the form you use for the disk accompanying sheet.

**Procedure**

1. Choose Accounting Financial Accounting Accounts Payable Periodic Processing Payments , then Environment Payment Medium DME Administration .

- 2. The system displays the DME Administration initial screen.
- 3. Enter the reference number or the paying company code and the bank country/region. You can make further selections by payment run date and identification. In the standard system, the default setting is that you want to see the payment run data which has not yet been downloaded to the PC. The fields Payment run and Data medium (not yet transferred externally) are selected.
- 4. Choose Edit Overview .
- 5. Select one or more data media and then choose Edit Download... .
- 6. The system displays a dialog box.
- 7. Enter a file name including path. If you are downloading to a disk, you can also add a volume number to the disk. Select the Volume field. The standard system proposes the number printed on the accompanying sheet. You can allocate the accompanying sheet to the correct disk at a later stage using this number. You can, however, also give the disk another name.
- 8. Choose Continue. The system may ask whether you have loaded a disk. When you confirm this, the download is carried out. If you have selected several data media to be downloaded, the system will ask you to load a new disk before each further disk is written to.


**Note:**

If the data media from the payment program are stored in the file system and not in the SAP system (TemSe), then the system already interprets this procedure as a download. You therefore only find data media created in this way in the DME administration if you choose Data medium (transmit.to external).

###### Deleting DME Administrative Data Across Company Codes

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Data Medium Exchange and Data Medium Administration > Deleting DME Administrative Data Across Company Codes | L8 | trm07 p.127 | loio `9904c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9904c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

If you do not want to delete the DME administrative data for each company code individually, you can also delete it within the reorganization of the payment run data.

**Note:**

The DME administrative data is deleted from the system without detail checks. Before a reorganization, you should make sure that the data media affected have been created and processed by the bank.

**Procedure**

- 1. Choose Accounting Financial accounting Accounts Receivable (Payable) Periodic processing Payments, and then Payment run Reorganization.
- 2. In the Reorganization dialog box, select the Delete admin.data function.

###### Archiving Object - Payment Request

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Archiving Object - Payment Request | L7 | trm07 p.127 | loio `5904c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5904c5536a51204be10000000a174cb4.html?locale=en-US)

Definition

Archiving object FI_PAYRQ consists of:

|Segment|Description|
|---|---|
|PAYRQ|Payment request|


**Use**

Payment requests are archived, deleted and reloaded with archiving object FI_PAYRQ.

###### Generating Archive Files – Payment Requests (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Archiving Object - Payment Request > Generating Archive Files – Payment Requests | L8 | trm07 p.128 | loio `5304c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5304c5536a51204be10000000a174cb4.html?locale=en-US)

**Prerequisites**

You can only archive payment requests that have been cleared.

**Procedure**

- 1. Choose Accounting Treasury and Risk Management Transaction Manager Utilities Archiving Payment Requests .

The Archive Administration: Create Archive Files screen appears.

- 2. Enter a variant name and choose Maintain.
- 3. Maintain your variants by entering the following selection criteria for the documents you want to have checked for archiving:

Company codes

The system only archives payment requests posted in the specified company codes.

Key numbers

The system only archives payment requests the lie within the interval.

Customer items

The system archives payment requests for customers.

Supplier items

The system archives payment requests for suppliers.

G/L account items

The system archives payment requests for G/L accounts.

Archiving period

The system only archives payment requests that have been in the system for longer than the specified archiving period.

- 4. Enter your selection criteria. To simulate the run, set the Test run indicator.
- 5. Choose Back.
- 6. The system asks you if you want to save the values you entered. Confirm your entries by choosing Yes.


- 7. The Save Attributes of Variant screen appears. Enter a description of your variant in the Description field.
- 8. Save your variant. Choose Back to return to the request screen for archive administration.
- 9. Maintain the start date and the spool parameters for the archiving run.
- 10. Once you have maintained the selection criteria, the start date, and the spool parameters, choose Execute.


To display an overview of the jobs you have generated, choose Goto Job Overview .

For more information on maintaining variants, see the SAP Library under SAP NetWeaver Solution Life Cycle Management Data Archiving (CA-ARC) Introduction to Data Archiving (CA-ARC) .

If all the archiving conditions are fulfilled, the system writes the archived documents to external archive files.

The system then starts a deletion program for each archive file, which imports the data to be deleted from the archive file and deletes it from the database.

###### Reloading Archived Data (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Payment > Payment Program for Payment Requests (FI-BL) > Execution of the Payment Program > Archiving Object - Payment Request > Reloading Archived Data | L8 | trm07 p.129 | loio `5604c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5604c5536a51204be10000000a174cb4.html?locale=en-US)

**Prerequisites**

You can only archive payment requests that have been cleared.

**Procedure**

- 1. Choose Treasury and Risk Management Transaction Manager Utilities Archiving Payment Requests .

Choose Goto Reload . The Archive Administration: Reload Archive Sessions screen appears.

- 2. You can enter a selection of key numbers to restrict the data reloaded.


The payment request does not carry a special indicator after the reload. It is stored in the original form, as it was before the archiving run.

