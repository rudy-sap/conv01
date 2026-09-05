# Transaction Manager > Process Intragroup Trading of Securities Positions for Consolidation - SAP TRM Knowledge Base (branch split)

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

#### Process Intragroup Trading of Securities Positions for Consolidation

> **Path:** Treasury and Risk Management > Transaction Manager > Process Intragroup Trading of Securities Positions for Consolidation | L3 | trm06 p.316 | loio `4c73382e69a971d0e10000000a15822b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c73382e69a971d0e10000000a15822b.html?locale=en-US)

You can use the Intragroup Trading function to process intragroup transactions (IGTs). In this way, you can remove from the group invoice any transactions that are performed between companies within the group.

You can use Intragroup Trading to do the following:

Identify intragroup transactions and process them together

Process the transfer values of intragroup transactions

Transfer position values, gains, and losses

See also:

Overview: Intragroup Trading

Editing Intragroup Transactions

##### Overview: Intragroup Trading

> **Path:** Treasury and Risk Management > Transaction Manager > Process Intragroup Trading of Securities Positions for Consolidation > Overview: Intragroup Trading | L4 | trm06 p.316 | loio `310cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/310cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

A company comprises different subsidiaries. The subsidiary companies usually trade in securities with one another. These types of financial transactions are called intragroup transactions (IGT). Financial transactions that are made with external business partners are known as external transactions. Some accounting principles stipulate that the gains and losses from intragroup transactions are to be excluded from the consolidated financial statements.

You can display intragroup transactions with the following product categories in the system:

Stocks (010)

Investment Certificates (020)

Bonds (040)

Bond with Installment Repayment (042)

Shareholding (160)

**Integration**

The function checks the authorization object T_IGT_DEALAuthorization for Product Type/Transaction Type for IGT.

Authorization Fields

Company Code

Product Type

Financial Transaction Type

Authorization Functions

Activity

Permitted Activities

- 02 Change

- 03 Display


The following new Position Components are available for consolidated gains and losses:

- 1021Consolidated Security Gains

- 1022 Consolidated Security Losses

- 1023 Consolidated FX Gains

- 1024 Consolidated FX Losses


These position components are not included in the book value.

You can use the Subledger Position function to break down the components using the company ID and position date.

Integration with the consolidation components

One of the following components can be used for consolidation:

Consolidation (EC-CS)

To assign update types for the derived business transactions to the flow types in the consolidation system, you need to create a Customizing table.

You need to implement BAdI TPM_ACCIF_TRAC (method ACCIT_RMVCT_EXIT) in the posting interface.

Business Consolidation (SEM-BCS)

If you want to identify intragroup transactions at the level of the subgroups, you can use the business data toolset (BDT) to insert a field in the business partner data at subgroup level (Company Relationship at Subgroup Level).

To read this field and derive the intragroup transaction status from it, you can use the BAdI: Determine Company Relationship at Subgroup Level (BADI_TPM_GET_COMP_RE_TRIG).

**Prerequisites**

To recognize the transactions using the subsidiary companies, you need to indicate the subsidiaries as affiliated companies in the business partner data. To do this, you need to make the following settings in the business partner data for the subsidiaries in the Counterparty role:

On the Control tab page in the Trading Partner field, you need to enter the group-wide unique company ID of the business partner.

In the company code data on the Reporting Data in Company Code tab page in the Regulatory Reporting Data in Company Code area, you need to indicate the business partner as being an affiliated company in the Company Relationship field.

In Customizing for the Transaction Manager under General Settings Accounting Settings for Intragroup Trading

Indicate Valuation Areas as Relevant for Intragroup Trading , you must activate the indicator for intragroup trading (IGT Ind) by using the accounting code, valuation area, product category and product type criteria for the relevant areas.

**Example:**

|Company Code|Name|Valuation Area for Individual Accounts|Valuation Area for Consolidated Accounts|
|---|---|---|---|
|0001|Subsidiary 1|Valuation Area 1|Valuation Area 2|
|0002|Subsidiary 2|Valuation Area 3|Valuation Area 4|


Subsidiary 2 needs to be created as a business partner in the counterparty role. In the data for company code

- 0001, the affiliated company indicator needs to be assigned.

Subsidiary 1 needs to be created as a business partner in the counterparty role. In the data for company code

- 0002, the affiliated company indicator needs to be assigned.


Under Indicate Valuation Areas As Relevant for Intragroup Trading, you need to set the intragroup trading indicator for company code 0001 and valuation area BB2 as well as for company code 0002 and valuation area BB4.

You need to assign an appropriate company ID by choosing General Settings Accounting Settings for Intragroup Trading Dummy Company ID for Intragroup Transactions without Value Transfer .

Securities transactions identified as intragroup transactions, that are in a valuation area mapped by the company or subsidiary, need to be edited in a second step. You need to confirm or reject the intragroup status (due to a threshold value, for example).

If you confirm the status, the flows relevant for consolidation (realized gains/losses) are assigned the company ID of the counterparty.

If you reject the intragroup status, the system assigns the dummy company ID that was created in Customizing. You can then use this ID to identify the profit and loss flows in the consolidation system.

To generate the transactions, you must assign appropriate update types in Customizing under Transaction Manager General Settings Accounting Derived Business Transactions Update Types .

You must first define the required update types and then assign them to the Derived Business Transaction usage.

Choose Update Types for Derived Business Transactions and the Intragroup Trading tab page to make the assignments for the update types based on the position management procedure.

In the activity Transaction Manager General Settings Accounting Link to Other Accounting Components , you have to define how accounts are determined for the update types that are relevant for posting.

**Features**

Set the intragroup transaction (IGT) status.

Once you have entered and saved the transaction using either the Create Financial Transaction function or a BAPI, it is generated in each valuation area. In the valuation areas that are indicated as relevant for intragroup trading, the system

checks in the company code-dependent data of the business partner in the Counterparty role whether the business partner is indicated as an affiliated company. If the business partner is an affiliated company, the IGT status is set to 1 = Open Intragroup Transaction. If the business partner is not an affiliated company, the IGT status is not entered.

If a financial transaction has been incorrectly assigned as an intragroup transaction (due to incorrect business partner data, for example), then the transaction needs to be reversed and created again once the business partner data has been corrected.

The following IGT statuses have been defined:

Space = No intragroup transaction

- 1 = Open intragroup transaction

- 2 = Closed intragroup transaction with value transfer

- 3 = Closed intragroup transaction without value transfer


The intragroup transaction status is saved in the database for the transaction in the valuation area.

You can display the IGT status in the following functions:

Subledger Positions (transaction TPM12)

Subledger Cash Flow (transaction TPM13)

Posting Journal (transaction TPM20)

These functions are available in the following logical databases for the Transaction Manager:

FTI_TR_CASH_FLOWS

FTI_TR_DEALS

FTI_TR_PERIODS

FTI_TR_PL_CF

FTI_TR_POSITIONS

It is not possible in the logical databases to break down the components for the consolidated gains and losses based on the company ID and position date.

To remove the IGT profit and loss from the consolidated accounts without affecting the overall result, you need to clear all the realized gains and losses from the sales. This is achieved using clearing flows, which are generated for the intragroup purchases according to the gains or losses from the corresponding intragroup sales.

By doing this, the position components in the sales position are transferred to the purchase position. The position components are adjusted using derived business transactions. Only the realized profit or loss is relevant for posting.

To generate clearing flows, you can use the function Edit Intragroup Transactions (transaction TRIG_IGT) by choosing Treasury and Risk Management Transaction Manager Securities Accounting Intragroup Trading .

You can also use this function to reverse clearing flows for intragroup transactions that have already been closed and thereby reset them to open status.

##### Editing Intragroup Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Process Intragroup Trading of Securities Positions for Consolidation > Editing Intragroup Transactions | L4 | trm06 p.316 | loio `340cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/340cda531198434de10000000a174cb4.html?locale=en-US)

Use

You use this function to edit intragroup transactions (IGTs). You select IGTs and then edit them from the worklist.

You can use the following functions to edit IGTs:

Find matching pairs

Edit with value transfer

Edit without Value Transfer

Reverse (closed IGT with and without value transfer)

**Integration**

See also: Overview: Intragroup Trading

**Prerequisites**

To use the functions Edit with Value Transfer and Edit without Value Transfer, the transactions must have the IGT status Open Intragroup Transaction.

To use the Reverse function, the transactions must have the IGT status Closed Intragroup Transaction (with/Without Value Transfer).

Based on the defined processing category, the transactions must have either the activity category contract (processing category 00001) or settlement (processing category 00002).

**Activities**

- 1. Choose Transaction Manager Securities Accounting Intragroup Trading Edit Intragroup Transactions (Transaction TRIG_IGT).
- 2. Select the transactions you want to edit.

You can select the purchases and sales according to the following criteria:

Company Code

Valuation Area

Valuation Class

Product Type

Securities ID Number

Securities Account

Securities Account Group

Portfolio (Position)

Transaction Number

Position Date

- 3. Select the IKG Status of the transactions to be selected:


Open intragroup transactions

Closed with value transfer

Closed without value transfer

- 4. Choose Execute.
- 5. The system displays a worklist with all the selected intragroup transactions.
- 6. The list is displayed using the SAP List Viewer for SAP GUI (Classic).


To edit the open IGTs, you can use both the standard functions in the SAP List Viewer and the following functions:

Find Pairs

You can use this function if purchases and sales are in the same client in an SAP system.

Execute the function. The system looks for matching purchases and sales.

The matching pairs are first displayed in a numbered list in two rows. Then, the system lists the other open intragroup transactions which do not have a matching offsetting transaction.

Edit with value transfer

- Case 1: Purchases and sales in the same client in an SAP system

Select a pair (both rows) and choose Edit.

The Edit Book Values dialog box appears.

The Book Values in Position Currency are on the left and the Book Values in Valuation Currency are on the right.

The Gains/Losses area shows the realized and unrealized gains and losses that need to be posted on the purchase side to adjust the values.

The Company ID field is at the start of each row. Here you enter the company ID of the counterparty.

If you do not want to transfer the position values in the sale position, you can change the values.

If you have edited the values or you want to transfer the default values, choose the Confirm Values function.

The system generates the derived business transactions to adjust the position components and to post the gains and losses for the purchase.

The company ID of the buyer and the original date are added to the posting documents for the profitrelated flows in the sales transaction. If the derived business transaction has already been posted, it is reversed and then posted again with the refreshed data.

The intragroup transactions are assigned the IGT status Closed with Value Transfer.

The system displays a posting log and message list.

- Case 2: Only the purchase is in an SAP system


**Note:**

If you have already managed the components for consolidated gains and losses in the sales position, these components also need to be transferred and posted individually together with the company ID of the original seller.

- a. Select an intragroup transaction.


The Edit Book Values dialog box appears.

- b. The Book Values in Position Currency are on the left and the Book Values in Valuation Currency are on the right.

The book value field for the purchase is known from the transaction and is therefore the only field containing an entry. The other fields are available for you to make entries.

Enter the values for the different position components in position currency and valuation currency.

- c. In the Gains/Losses area, enter the amounts for the consolidated gains/losses and the unrealized gains/losses.

The Company ID field is at the start of each row. Here you enter the company ID of the counterparty.

- d. Once you have entered these values, choose Confirm Values.


**Note:**

You must ensure that you have received the necessary information from the company making the sale.

**Note:**

If you have already managed the components for consolidated gains and losses in the sales position, these components also need to be transferred and posted individually together with the company ID of the original seller.

In the Original Date field, enter the position value date.

In the following fields, enter the Amount in Position Currency and the Amount in Valuation Currency:

Enter the type of gain or loss. The following gain/loss types are available:

Realized Success Security

Realized Success Foreign Currency

Unrealized Success Security

Unrealized Success Foreign Currency

Unrealized Success Index

Unrealized Success Costs Security

Unrealized Success Costs Foreign Currency

Below the list, the system displays the following values resulting from the flows:

Gain (Security) in Position Currency

Price Loss (Security) in Position Currency

Price Gain (Security) in Valuation Currency

Price Loss (Security) in Valuation Currency

FX Rate Gain in Valuation Currency

FX Rate Loss in Valuation Currency

The system generates the derived business transactions to adjust the position components and to post the realized and unrealized gains and losses.

The intragroup transaction is assigned the IGT status Closed with Value Transfer.

- e. The system displays a posting log and message list.


- Case 3: Only the sale is in an SAP system


- a. Select an intragroup transaction.

The Edit Book Values dialog box appears.

- b. The system displays the Book Values in Position Currency and the Book Values in Valuation Currency.
- c. The Gains/Losses area shows the realized and unrealized gains and losses that need to be posted on the purchase side to adjust the values.

You can use the Export function to transfer the data in the table to a file for a spreadsheet program.

You can use the Print function to print the data in the table.

Transfer the data to the company making the purchase.

- d. Choose Confirm Values.


The company ID of the buyer and the original date are added to the posting documents for the profit-related flows in the sales transaction. If the derived business transaction has already been posted, it is reversed and then posted again with the refreshed data.

The intragroup transaction is assigned the IGT status Closed with Value Transfer.

The system generates a posting log.

Edit without Value Transfer

- a. Select a transaction pair or an individual transaction.
- b. Choose Edit without Value Transfer.
- c. Confirm the following dialog box.


The dummy company ID defined in Customizing and the original date are added to the posting documents for the profit-related flows in the sales transaction. If the derived business transaction has already been posted, it is reversed and then posted again with the refreshed data.

The intragroup transactions are assigned the IGT status Closed without Value Transfer.

Display Original Business Transaction

The transaction data screen appears.

Display Position Values (Sale)

If you choose to use this function, you can display the position values for an intragroup sale.

If the sale involves a partial outflow from the position, you can see the position values of the entire position.

To edit the closed IGTs, you can use both the standard functions in the SAP List Viewer and the following functions:

Find Pairs

You can use this function if purchases and sales are in the same client in an SAP system.

Execute the function. The system looks for matching purchases and sales.

The matching pairs are first displayed in a numbered list in two rows.

Reverse

You can reverse intragroup transactions that have already been closed either with or without the value transfer.

- a. Select a closed transaction pair or an individual closed transaction.
- b. Choose Reversal.
- c. Specify whether you want to execute a test run.
- d. Enter the reason for the reversal.
- e. Choose Continue.
- f. The system executes the reversal run or the test reversal run.
- g. A message list, posting log, and a reversal log are displayed.

The posting log contains the recalculated derived business transactions for the purchase or sale if they had been posted before the reversal.

- h. The intragroup transactions are assigned the IGT status Open Intragroup Transaction.


Display Original Business Transaction

The transaction data screen appears.

Display Position Values (Sale)

If you choose to use this function, you can display the position values for an intragroup sale.

If the sale involves a partial outflow from the position, you can see the position values of the entire position.

