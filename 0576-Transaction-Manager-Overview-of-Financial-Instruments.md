# Transaction Manager > Overview of Financial Instruments - SAP TRM Knowledge Base (branch split)

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

#### Overview of Financial Instruments

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments | L3 | trm05 p.2 | loio `4c313dc4ebef3c6de10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c313dc4ebef3c6de10000000a42189c.html?locale=en-US)

The Transaction Manager offers you a wide choice of product types with which to portray and manage your financial transactions and positions. In addition to the product types found in Customizing in the standard delivery, you can define individual product types based on the product categories in Customizing for Transaction Manager.

Depending on the product type, the financial transactions run through different activities within the transaction and position management process. You can structure this process to meet your needs.

With its product type concept, the Transaction Manager offers the following advantages:

Simple data entry and administration and the use of control parameters

Flexible design of structure characteristics and conditions of financial transactions

Option of representing complex condition combinations

Guaranteed data consistency of your transactions

**Note:**

In the product type definition for financial instruments of the following product categories, you can choose Parallel Conditions in the Cash Flow Generation field:

550 Interest Rate Instrument

580 Current Account Style Instrument

610 Cap/Floor

For 610 Cap/Floor, the parallel conditions are not needed because they have only one condition, but the assignment of up to 5 calendars for the working day check is relevant.

620 Swap

In the product type definition of the Securities area, you can also make a similar setting in the product type definition. Here you can choose Parallel Interest Conditions in the Cash Flow Generation field.

This setting enables the usage of extended financial mathematic functions (New FiMa), such as parallel conditions and the assignment of up to 5 calendars for the working day check. This influences how conditions are managed and therefore how cash flow is calculated.

If you make this settings you get the Condition Details: Interest (New FiMa) screen to enter the interest conditions, this includes additional interest calculation types, such as Exponential Interest Calculation with Factors, Compound Interest Calculation, and Average Compound Interest Calculation. So, you can enter variable interest conditions with risk-free reference rates. For more information, see also Interest Calculation Types. In addition, parallel interest conditions are possible.

Overview of Product Types/Product Categories

|Money Market|Foreign Exchange|Derivatives|Securities|Trade Finance|
|---|---|---|---|---|
|Fixed-Term Deposit (product category 550, with term category Fixed-Term)|Spot/Forward Transaction (product category 600) |Forward Rate Agreements (FRAs) (product category 630) |Stocks (product category 010)|Letters of Credit (product category 850)|


|Money Market|Foreign Exchange|Derivatives|Securities|Trade Finance|
|---|---|---|---|---|
|**Note:** SAP recommends that you do not use product category 510.| | | | |
|Deposits at Notice (product category 550, which has the term category At Notice and allows you to enter interest conditions of the types Fixed, Variable, Scaled (Incremental), and Scaled (Interval).) **Note:** SAP recommends that you do not use product category 520.|FX Swap For more information, see also Create FX Swap. |Cap/Floor (product category 610)|Investment Funds (product category 020)|Bank Guarantees (product category 860)|
|Commercial Paper (product category 530)|FX Option (product category 760)|Swap (product category 620)|Subscription Rights (product category 030)| |
|Interest Rate Instrument (product category 550)|Non-Deliverable Forward (NDF) (product category 600) |Interest Rate Swap |Bonds Investment management| |
|Cash Flow Transaction (product category 540)| |Cross-Currency Interest Rate Swap |Bonds (product category 040)| |
|Facility (product category 560) Debt management| |Discount Swap|Installment Bonds (product category 042)| |
|Current Account-Style Instruments (product category 580) | |Compound Swap|Convertible Bond (product category 070)| |
| | |Total Return Swap (product category 640) |Warrant Bond (product category 060)| |


|Money Market|Foreign Exchange|Derivatives|Securities|Trade Finance|
|---|---|---|---|---|
| | |OTC Options (product category 760)|Warrant (product categories 111 Index Warrant, 112 Equity Warrant, 113 Currency Warrant, and 114 Bond Warrant) | |
| | |FX Option|Shareholdings (product category 160)| |
| | |Currency Barrier Option |Asset-Backed Securities and Mortgage-Backed Securities (product category 042) | |
| | |Swaption|Bond Issue Debt management| |
| | |Interest Rate Guarantee (IRG) | | |
| | |Security Option| | |
| | |Compound Option | | |
| | |Average Rate Option | | |
| | |Basket Option| | |
| | |Correlation Option | | |
| | |Repos with/without Collateral Transfer / Repurchase (Repo) Transaction (product category 730) | | |
| | |Listed Derivatives| | |
| | |Listed Option (product category 750)| | |


|Money Market|Foreign Exchange|Derivatives|Securities|Trade Finance|
|---|---|---|---|---|
| | |Future (product category 700)| | |
| | |Securities Lending (product category 770)| | |
| | |Forward Securities Transactions (product category 740) | | |
| | |Forward Loan Purchase (product category 790)| | |

##### Foreign Exchange (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange | L4 | trm05 p.5 | loio `4c3417a17a761a6fe10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c3417a17a761a6fe10000000a42189c.html?locale=en-US)

**Use**

Foreign exchange covers all the business processes arising from both classical currency trading and trading with OTC currency options. This process spans the whole trading process, starting from entering the transaction, processing it, and transferring the data to Financial Accounting. A range of evaluation options is also available for reporting purposes.

**Integration**

The integration of the Transaction Management functions allows you to analyze the impact of forex trading on the liquidity situation of your company as well as the resulting currency risks.

You can maintain current market data (such as exchange rates, securities prices, reference interest rates, and indexes) in a number of ways:

Manually

Market Data File Interface: You maintain the relevant data in an external application (such as Microsoft Excel), either manually or via a data provider, and then import the data into the system in an SAP-compatible format.

By transferring the market data to the system from a spreadsheet

Datafeed: You can use the datafeed link to make market data available in the system in real time.

To access the market data management functions in the application menu, choose Treasury and Risk Management Basic Functions Market Data Management . Alternatively, you can access them in the Foreign Exchange Trading area under Environment Market Data .

The figure below illustrates the transaction and position management process using a foreign exchange transaction as an example:

[figure TRM05-F001 - You access the Foreign Exchange Trading component by choosing Accounting Treasury and Risk Management Transaction Manager Foreign Exchange Trading .]

You access the Foreign Exchange Trading component by choosing Accounting Treasury and Risk Management Transaction Manager Foreign Exchange Trading .

**Features**

Trading

The trading area groups together the functions for entering foreign exchange transactions. Besides entering transactions, it also enables you to call up information about previously entered transactions or to make changes. Collective processing functions are available to help you manage your foreign exchange transactions efficiently.

Forex trading incorporates the following product types:

Spot exchange and forward exchange transactions

Forex swap transactions

OTC currency options (Overview of Product Types)

Currency options are handled in the derivatives area.

You can use the Position Monitor to obtain an overview of the current foreign currency risk in your company.

In the trading area, you can use a decentralized process to enter foreign exchange transactions from the view of the company code entering the transaction (Internal Foreign Exchange Trading).

Back Office

Once you have entered financial transactions in the trading area, you settle the transactions in the back-office area. The back office area also contains functions for checking and changing the transactions. The key aspects of postprocessing are as follows:

Entering additional transaction data, such as adding information that is relevant for back-office processing

Preparing for posting and payment, for example, by checking the accounts used

Generating correspondence in the form of internal or external confirmations

Collective processing functions are also available in the back office. The back-office also includes functions for netting transactions and for entering or editing references.

Accounting

Once you have entered the transactions in the Trading area and have checked and completed them in the Back Office area, you then submit them to accounting. The accounting area includes functions for transferring data to Financial Accounting, such as posting reports or position management postings. It also includes functions for parallel valuation.

Information System

The information system provides a range of reports for analyzing your money market transactions. The Money Market Information System is part of the Transaction Manager information system, which offers analyses and evaluations across the whole of the Treasury and Risk Management dataset.

The link to the SAP Query also allows you to define your own reports in addition to those provided by SAP. For more information, see also: Information System.

###### Define CFI Code Groups

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Define CFI Code Groups | L5 | trm05 p.7 | loio `4c5531592d164e949ba366cbaadda86e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c5531592d164e949ba366cbaadda86e.html?locale=en-US)

In this step, you define the relevant master data for the Classification of Financial Instruments (CFI) code.

**Definition**

The Classification of Financial Instruments (CFI) code is used to define and describe financial instruments as a uniform set of codes for all market participants (ISO 10962).

The CFI code consists of six alphabetical characters. These characters reflect the characteristics of a financial instrument. The first character defines the CFI category. For example, whether it is a spot or a forward transaction. The second character defines the specific CFI group within each category. The third to sixth character indicate the most important attributes in each group, such as the underlying asset or the form of delivery.

**Example:**

JFTXFP is a CFI code for an FX forward transaction (with physical delivery).

JFTXFN is a CFI code for an FX NDF transaction.

**Use**

CFI codes are used for trade repository reporting, for example for EMIR regulations. You may receive such CFI codes when you are trading financial instruments on trading platforms.

The entity CFI Code Group is used to structure the CFI code. Depending on the specific CFI group, further attributes can be assigned to define a financial instrument within each group.

You use the Define CFI Code Groups function to specify the first two characters of the CFI code and the remaining four attributes belonging to the group.

**Procedure**

- 1. Choose Define CFI Code Groups.
- 2. Choose New Entries to specify a new CFI code group.
- 3. Enter the CFI code group, CFI group text, and attribute 1 through 4.


- 4. Save you entries.


**Related Information**

Assign Attributes to CFI Code Groups

###### Assign Attributes to CFI Code Groups

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Assign Attributes to CFI Code Groups | L5 | trm05 p.8 | loio `25e31f02ba43472486b5019cac4e55c9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/25e31f02ba43472486b5019cac4e55c9.html?locale=en-US)

In this step, you assign the relevant attribute values to the CFI code groups that help to uniquely identify a financial instrument.

**Use**

The CFI attribute number helps to maintain the values that are valid for each of the six alphabetical characters of the CFI code. You can assign four values (Attribute 1 to Attribute 4) to the two-character CFI code group.

**Prerequisites**

You have defined the necessary master data with the function Define CFI Code Groups.

**Procedure**

- 1. Choose Assign Attributes to CFI Code Groups.
- 2. Choose New Entries to assign one of the four attributes to a CFI code group.
- 3. Enter the CFI code group and select the attribute number you want to assign to the relevant CFI code group.
- 4. Enter the CFI attribute value you want to assign to the attribute number.
- 5. Save you entries.


**Example:**

For an FX swap transaction (CFI group SF), you usually define the following values for Attribute 1:

A - which stands for a Spot-Forward Swap

C - which stands for a Forward-Forward Swap

- M - which stands for Miscellaneous

For Attribute2 and Attribute 3 , you may currently define the value X for Not Applicable/Undefined.

For Attribute 4 you may define the following values:

C which stands for Cash

- N which stands for Non-Deliverable


P which stands for Physical

Related Information

Define CFI Code Groups

###### Spot/Forward Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Spot/Forward Transactions | L5 | trm05 p.9 | loio `7b14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b14da531198434de10000000a174cb4.html?locale=en-US)

**Use**

With spot transactions, internationally traded currencies are bought and sold for other currencies at the spot rate. Forward transactions, on the other hand, are traded on a certain date in the future with the relevant premiums and discounts for calculating the forward rate being specified.

**Prerequisites**

Before using the transaction management functions, you have to enter master data.

You have to create your business partners, assign corresponding roles to them, and maintain the transaction authorizations. To process foreign exchange transactions, you must have defined the banks authorized as business partners in the system with the corresponding payment details.

You have to set up the standing instructions (correspondence, payment details) and release the business partner.

You also have to make the following settings in Customizing:

Define the product types (if you do not want to use one of the standard product types delivered with the system, you can define your own product types). You create financial transactions and manage positions on the basis of product types. Foreign exchange is one example of a product type.

Define the transaction types. Transaction types determine the type of transactions that can be concluded with a particular product type. They also control the transaction and position management process. Example: Spot transaction.

Define the flow types. These describe the various changes to the cash flows. Example: Sell foreign exchange.

You must assign flow types to transaction types.

For more information, see the relevant section in the Implementation Guide.

Once you have made these settings, you can enter foreign exchange transactions in the system.

###### Processing Spot/Forward Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Spot/Forward Transactions > Processing Spot/Forward Transactions | L6 | trm05 p.9 | loio `7514da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7514da531198434de10000000a174cb4.html?locale=en-US)

With spot transactions, internationally traded currencies are bought and sold for other currencies at the spot rate. Forward transactions, on the other hand, are traded on a certain date in the future with the relevant premiums and discounts for calculating the forward rate being specified.

**Procedure**

- 1. Open either the Process Spots/Forwards - Collective Processing app, the Manage Financial Transactions app, or the Process Financial Transaction app on SAP Fiori launchpad.

- 2. Select the relevant transaction. You can perform one of the following functions for spot/forward transactions.


|Function|Entries|Comments|
|---|---|---|
|Change|Choose Change. The screen for changing the basic data appears. Make any necessary changes and save the spot/forward transaction.|You can now overwrite the active entry fields or enter data in the empty fields. You can branch to the general transaction management screens using the corresponding tabs and make any necessary changes. If you make any changes to the values you entered manually in the Rate, Spot or Swap fields, the system sets these as fixed values. If you make any later changes, the values determined by the system are changed, but not the values you entered manually. You can use this function to change an activity, provided that it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are marked Flagged for Posting.|
|Display|Choose Display. The display screen for the basic data appears.|The entry fields are not active. You can use the tabs to navigate between screens and display other transaction data. You can jump to the master data for the business partner.|
|Rollover/Premature settlement|1. Choose Rollover or Premature Settlement. 2. The same screen that you use for the fast entry of swaps appears, but you can enter data only on the lefthand side of the screen (first transaction). 3. The following fields in this area automatically contain values: Currency ID, amounts, and forward rate of the transaction to be rolled over (prematurely settled). This forward rate is the spot basis for the rollover (premature settlement) and for the value date to be changed. 4. The second side (second transaction) shows you the details of the forward transaction to be rolled over, but with offsetting payment flows in the opposite direction. |More information is available in Object Links |


|Function|Entries|Comments|
|---|---|---|
| |5. To make the new entry, you only need to enter the swap rate and the changed value date. 6. You can enter the liquidity costs of a rollover for the changed spot rate separately in the Liquidity field and use them for your own evaluation reports at transaction level. | |
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. |
|History|Choose History. The system lists the activities that are active, reversed, or have been replaced by a follow-up activity. From this list, you can branch to the display for the individual activities. You also see their status and the user who processed them.|The history function displays the sequence of previous activities for a selected transaction.|
|Settle|Choose Settle. The screen for settling the contract appears. From the menu, choose the area for which you want to enter or change the settlement data. When you save a settlement activity, the system changes the activity category of the|Using the Settle Spot/Forward Transaction function, you can select a transaction to indicate that it has been processed in the back office. At this stage, you check the entries and add any missing data. When you save the transaction, the system fixes the data (actual records) and flags the transaction flows for posting.|


|Function|Entries|Comments|
|---|---|---|
| |transaction to record how it is monitored and processed in the back office area. The contract can be posted only after it has been settled.| |
|Copy **Note:** This function is available in the Manage Financial Transactions app (App ID: F6157) and Process Spots/Forwards Collective Processing app (App ID: TX06).|1. Mark the financial transaction you want to copy in the worklist. 2. Choose the Copy button. 3. The Change or Copy Forex Trans... dialog box appears. In the fields Company Code and Business Partner the values of the copied financial transaction are displayed. You can now change the company code or the business partner and choose Continue or you continue the copy process without changing these values. 4. You see the data of the new financial transaction. The data correspond with the copied transaction. 5. Make the required changes. 6. Save the financial transaction. |You can create a new spot/forward transaction by copying an existing transaction. This function enables you to fast-track the entry of a new transaction.|
|Terminate|1. Choose Terminate. 2. Make the following entries: Date Entry type Specify whether you want to enter the payment amount for the termination of FX transactions directly or calculate it using a rate. Amount Rate Flow type The flow type 1039 Termination amount (of flow category 39) is predefined and set by default. Payment date Payment amount|You can terminate FX spot or forward transactions early before their maturity. The FX spot or forward transactions must have the activity category Contract Settlement. When you save the termination activity, the system creates a Termination OTC Transaction business transaction. The Termination business transaction consists of the following flows: Close flow of the OTC transaction at termination date to clear the nominals Termination amount flow (representing the termination flow of the financial transaction) The date of both flows is the payment date entered in the Termination area of the financial transaction. If the terminated FX transaction is used as the hedging instrument in hedging relationships at the termination date, the|


|Function|Entries|Comments|
|---|---|---|
| |After you entered the relevant data the payment flow is generated, the posting status of the original buy and purchase flows is set to 0. 3. Save your entries.|termination of the FX transactions results in the immediate complete dedesignation of these hedging relationships. The hedging business transaction Termination Dedesignation is automatically created for each associated hedging relationship. For more information, see also Dedesignation by Termination |


**Supported Device Types**

Desktop

Tablet

**Related Information**

Overview of Financial Instruments

###### Non-Deliverable Forward (NDF)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Non-Deliverable Forward (NDF) | L5 | trm05 p.13 | loio `3f74f410a11d4972b362fac39c37d09e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f74f410a11d4972b362fac39c37d09e.html?locale=en-US)

**Use**

Non-deliverable forwards (NDFs) are non-listed, short-term forward exchange transactions between a rarely traded or nonconvertible currency and a readily convertible currency (typically USD) for which a cash settlement is always made on the due date (value date).

Unlike ordinary forward exchange transactions, NDFs apply a fixing date (for which the current market price is fixed) in addition to a value date. After the current price has been fixed, the difference between the agreed forward rate and the resulting settlement amount is calculated. The payment is made on the value date.

**Integration**

The system checks the following authorization object when processing NDFs:

|Authorization Object|Activities|Comments|
|---|---|---|
|T_DEAL_PD Authorization for Product|01 Create or Generate|You use this authorization object to specify|
|Types/Transaction Types|02 Change|the functions and activities that users can perform for a product type or a transaction|
| |03 Display|type within a company code.|
| |06 Delete|Usage in the Functions|
| |16 (Execute)|All transactions for transaction management (trading and back office) in|
| |38 Execute|the Transaction Manager (FSCM-TRM-TM)|
| |43 Release|that create or edit financial transactions (including BAPIs)|
| |48 Simulate| |
| |83 Counterconfirm| |


|Authorization Object|Activities|Comments|
|---|---|---|
| |85 Cancel AB Settle KI Knock In KO Knock Out KU Give Notice PR Edit Correspondence PS Edit Correspondence - Special VF Expired| |


**Prerequisites**

You need to have made the Customizing settings for NDFs. For more information, see Non-Deliverable Forward (NDF): Customizing

Master Data

To portray forward exchange transactions, you have to assign the Counterparty role to your business partners. For more information, see also Business Partner

Enter Market Data

For NDFs, you need the exchange rates of the relevant currencies as well as the swap rates. You can use the following options for entering this data:

Entering Exchange Rates Manually

Manual entry of foreign exchange swap rates in the application menu for Treasury and Risk Management under Basic Functions Market Data Management Manual Market Data Entry Currency Enter Forex Swap Rates .

Market Data Transfer from Spreadsheet

File Interface

Datafeed

**Key Features**

You can use the following functions to portray the Process Flow for a Non-Deliverable Forward (NDF):

In Transaction Management (transactions FTR_CREATE and FTR_EDIT), the functions for creating and editing nondeliverable forwards are integrated.

For more information, see:

Creating Non-Deliverable Forwards

Editing Non-Deliverable Forwards

In the case of NDFs, confirmation letters are generally issued (for example, via SWIFT with MT300 format) when the contract is signed and when fixing occurs. See also: Define Fixing References

NDFs are integrated in transaction and position management in Transaction Manager. You can use them as hedging instruments in Hedge Management. You can valuate them using key date valuation and edit them using the functions

available for OTC transactions.

The net present value of non-deliverable forwards is calculated in the Market Risk Analyzer in the same way as the net present value of ordinary forward exchange transactions. Once fixing has occurred, the net present value of the NDF is the same as the settlement amount discounted to the key date.

See also: Forward Exchange Transaction

You can analyze your NDFs using the standard reports for transaction and position management, such as the following:

Transaction Overview: Journal (transaction TJ01)

Position List (transaction TPM12)

Subledger Cash Flow (transaction TPM13)

Posting Journal (transaction TPM20)

Furthermore, you can define queries for your NDF financial transactions using the logical database FTI_LDB_DEALS.

BAPIs

The BAPIs available for BUS5600Foreign Exchange for creating and editing foreign exchange transactions can also be used for NDFs.

For fixing, you can use the NDFFixingFixing of an NDF Transaction method.

For more information, see BAPIs for the Transaction Manager.

###### Non-Deliverable Forward (NDF): Customizing

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Non-Deliverable Forward (NDF) > Non-Deliverable Forward (NDF): Customizing | L6 | trm05 p.15 | loio `d8bbd34acf794d04b27ae9968213dc48` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d8bbd34acf794d04b27ae9968213dc48.html?locale=en-US)

You need to make the following settings for non-deliverable forwards in Customizing for Transaction Manager.

Customizing for Transaction Management

In Customizing for Treasury and Risk Management under Transaction Manager Foreign Exchange Transaction Management , make the following settings:

- 1. Under Define Product Types, you first create a new product type for non-deliverable forwards with the product category 600Foreign Exchange. In the Settlement field, select Non-Deliverable Forward.
- 2. Processing Category

Under Define Transaction Types, create a transaction type for this product type. In the transaction type, assign a number range for the transactions. In the Processing Category field, assign one of the following processing categories:

Processing category 121 with theOrder - Contract - Settlement - Fixing Settlement activity chain

Processing category 120, with the Order-Contract-Fixing activity chain

Set the Automatic Posting Release indicator and/or Automatic Settlement for Counterconfirmation indicator if you want to. You can also assign a limit group and a status profile.

- 3. In the activity Assign Flow Types to Transaction Type, you need to create flow types for purchase, sale, and cash settlement, and assign these flow types to transaction rates.


Example

1000 Purchase (flow type 10Principal Increase)

1031 Cash settlement (flow type 31Cash Settlement)

2000 Sale (flow type 10Principal Increase)

0010 Charges (flow type 90Other Flow/Condition) [optional]

- 4. In the activity Define Update Types and Assign Usages, you also need to define update types that correspond to the transaction flow types already defined in the activity Define Flow Types. This reason for this is that, in the Transaction Manager, postings to Financial Accounting as well as position management use update types.

Example

FX1000+ Purchase Foreign Exchange

FX2000– Sale Foreign Exchange

FX1031+ Cash Settlement

FX1031– Cash Settlement

FX0010+ Charge Foreign Exchange Transaction [optional]

FX0010+ Charge Foreign Exchange Transaction [optional]

Furthermore, update types are also required for open/close flows.

Example

- OTC001 Open OTC Transaction

- OTC002 Close OTC Transaction


You assign the update types to the Transaction Management application.

- 5. In the activity Assign Flow Types to Update Types, you assign corresponding update types to the transaction flow types.
- 6. In the activity Assign Update Types for Position Update, you assign per product type and transaction type an update type for the open flow and an update type for the close flow.
- 7. Under Transaction Manager General Settings Transaction Management Currencies Define NonDeliverable Currencies , you specify which currencies are non-deliverable. When transactions are entered for nondeliverable forwards (NDFs), the system checks in this activity which currency among those used is the nondeliverable currency and proposes the other currency as the settlement currency. You can change the settlement currency proposed. However, settlement has to use one of the currencies involved. Settlement is not possible in a third currency.
- 8. Correspondence


**Note:**

Exception: If the non-deliverable currency is the local currency, the system proposes it as the settlement currency.

Make the necessary settings in Customizing.

Customizing for Accounting

Make the following settings under Transaction Manager General Settings Accounting Settings for Position Management :

- 1. In the activity Set the Effects of the Update Types on the Position Components, you define the value Indirect Position Change for the purchase, sale, and cash settlement update types of the NDF and the value No Position Changes for the open/close update types.

Example

FX1000+ Purchase Foreign Exchange – 1006 Indirect Position Change

FX1031+ Cash Settlement – 1006 Indirect Position Change

FX1031- Cash Settlement – 1006 Indirect Position Change

FX2000- Sale Foreign Exchange – 1006 Indirect Position Change

- OTC001 Open OTC Transaction – 1000 No Position Change
- OTC002 Close OTC Transaction – 1000 No Position Change


- 2. In the activity Key Date Valuation, you can create a special valuation procedure for NDFs.
- 3. Define a position management procedure for Non-Deliverable Forwards and assign to it the procedure that you have defined above. Then assign the position management procedure to the NDF positions.
- 4. Make the settings for the derived business transactions.

For example, you need a separate update type for posting an exchange rate gain/loss equivalent to the amount of the cash settlement at the end of the forward transaction (such as DBT_B013 Forward Exchange Transaction Gain (Standard) and DBT_B014 Forward Exchange Transaction Loss (Standard)), which you assign on the Rate Gains/Losses tab page in the Assign Update Types for Derived Business Transactions activity.

- 5. Link to Other Accounting Components


**Note:**

You can also assign an existing position management procedure to NDF positions.

**Note:**

If you use NDFs in hedging relationships, the settings that you need to make for their valuation and for the derived business transactions are more complex than those described here.

Independently of the valuation area, you use account determination to specify the accounts to which the postingrelevant update types are posted in Financial Accounting. For this, you need to set up account determination for the update types used in transaction management as well as for the posting-relevant update types of the derived business transactions.

In the context of an NDF, the posting-relevant update types are those for cash settlements, additional flows, and exchange rate gains/losses.

Example

FX1031+ Cash Settlement – 1006 Indirect Position Change

FX1031- Cash Settlement – 1006 Indirect Position Change

Additional Flows

- DBT_B013 Forward Exchange Transaction Gain (Standard)

- DBT_B014 Forward Exchange Transaction Loss (Standard)


Master Data for Currencies

Before you can enter currency exchange rates, you need to make the following settings in Customizing under Basic Functions Market Data Management Master Data Currencies :

Check Currency Codes

Define the required currency keys

Check Decimal Places for Currencies

Check Exchange Rate Types

Define the exchange rate types for your exchange rates.

Check Rate Spreads

Check Rounding Rules for Currencies

Define Translation Ratios for Currency Translation

Under Currencies Assign Calendar , you have to specify which factory calendars are valid for the different currencies.

Under Currencies Define Leading Currency , you specify which currency is the leading currency for each currency pair.

This setting is required to determine the quotation of an exchange rate when transactions are entered.

Define Fixing References

To fill all fields of the confirmation for your non-deliverable forwards via SWIFT MT300, you need to define fixing references. You assign these fixing references when you enter a transaction.

For more information, see the documentation for Customizing activities.

###### Process Flow for a Non-Deliverable Forward (NDF)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Non-Deliverable Forward (NDF) > Process Flow for a Non-Deliverable Forward (NDF) | L6 | trm05 p.18 | loio `ceef7456ef2a41aab3e74564df883197` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ceef7456ef2a41aab3e74564df883197.html?locale=en-US)

**Use**

This section describes the process flow for a non-deliverable forward. The process flow depends on the processing category that is selected in the Customizing settings for the product type; the processing category specifies the activity chain for your NDFs:

Order - Contract - Settlement - Fixing - Settlement for Fixing (processing category 121)

Order - Contract - Fixing (processing category 120)

Flows of a transaction acquire their posting status on the basis of the activity reached and other circumstances (such as whether the release function has been activated). For example, if an NDF has two posting-relevant activities and only additional flows are flagged for posting in the case of the first activity (contract or settlement), the posting status for cash settlement at this time is Activity does not allow posting. If the posting-relevant activities Fixing or Fixing Settlement are reached, cash settlement and additional flows due at this time are flagged for posting.

**Process**

|Function|AWT 121|AWT 120|Comments|
|---|---|---|---|
|Creation of a Contract| | | |


|Function|AWT 121|AWT 120|Comments|
|---|---|---|---|
|1. Create Order/Contract|X|X|When a contract is created, the following flows are generated: Open flow (status Plan, not relevant for posting) on the contract date An open flow designates the start of a transaction. A flow in the purchase currency and a flow in the sale currency in accordance with the contract data. They have the status Plan and are not relevant for posting If any additional flows have been created, they are generated. The flow for the cash settlement is created for the value date but does not contain an amount yet (status Plan, posting status: Activity does not allow posting). Close flow (status Plan, not relevant for posting) A close flow designates the end of a transaction. The flows are displayed partially in the transaction cash flow and partially in the subledger cash flow (transaction TPM13). See also: Creating Non-Deliverable Forwards (transaction FTR_CREATE) Cash flow for the transaction Subledger Cash Flow With the open flow, the NDF is created as a position. The position components of the NDF are still set to zero. Consequently, the NDF is created with an initial book value of zero. |
|2. Execute Order|X|X|Editing Non-Deliverable Forwards|
|3. Dispatching Correspondence|X|X|You can use the Correspondence Framework [available with the business function TRM, Correspondence Framework (FIN_TRM_CORR_FW)]. If you do not use the new correspondence framework, the existing correspondence functions are available. See also: Correspondence|
|4. Settle|X| |Editing Non-Deliverable Forwards|
|5. Release|X|X|Dependent on the setting in Customizing See also: Release |
|6. Post Transaction|X|X|Only relevant when there are posting-relevant additional flows such as charges. When the activity categories Settlement or Contract of the activity chain are reached and saved, the additional flows of the transaction acquire the status Flagged for Posting. The|


|Function|AWT 121|AWT 120|Comments|
|---|---|---|---|
| | | |update to the general ledger for the operative valuation area is triggered in the Accounting area with the function Execute Posting [transaction TBB1]. After the posting report has been run, the flows acquire the posting status Posted and are converted from plan records into actual records. For the parallel valuation areas, the posting is made either via the function Execute Posting mentioned above and/or the function under Accounting Transaction Fix, Post, or Reverse Business Transactions [transaction TPM10]. This depends on whether, when posting the transaction, you have only posted the operative valuation area using transaction TBB1 or you have also made postings to the parallel valuation areas. |
|During the Term of the NDF| | | |
|You can assign the NDF as a hedging instrument in a hedging relationship in Hedge Management. You can use key date valuation in the Transaction Manager to valuate the position. You can determine the net present value in the Market Risk Analyzer. | | | |
|Fixing and Cash Settlement| | | |
|1. Fixing|X|X|Editing Non-Deliverable Forwards When the activity categories Fixing Settlement or Fixing are reached and saved, the system calculates cash settlement and updates the relevant flow. The cash settlement flow acquires the status Flagged for Posting. Furthermore, the system creates a derived business transaction for the amount of the cash settlement and this business transaction posts the rate loss/gain to the profit and loss statement.|
|2. Settle|X| | |
|3. Dispatching Correspondence|X|X|See above|
|4. Post Transaction|X|X|With the function Post Transaction [transaction TBB1], posting of the clearing flow is triggered. After the posting report has been run, the flows acquire the posting status "Posted" and are converted from plan records into actual records. If additional flows are also flagged for posting at this time, they are also posted. For the parallel valuation areas, the posting is made either using transaction TBB1 or via the function under Accounting Transaction Fix, Post, or Reverse Business Transactions [transaction TPM10]. This depends on whether, when posting the transaction using transaction TBB1, you only posted the operative valuation area or you also made postings to the parallel valuation areas. It also depends on the settings that you have made in Customizing for the derived business transactions. |
|5. Fix and Post Derived Business Transactions (transaction TPM18)|X|X|Fix and Post Derived Business Transactions|

###### Creating a Non-Deliverable Forward

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Non-Deliverable Forward (NDF) > Process Flow for a Non-Deliverable Forward (NDF) > Creating a Non-Deliverable Forward | L7 | trm05 p.20 | loio `ded46c59e32d44879e2f6fa5d371bfc8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ded46c59e32d44879e2f6fa5d371bfc8.html?locale=en-US)

**Use**

This section describes how to create a non-deliverable forward (NDF).

**Prerequisites**

See also: Non-Deliverable Forward (NDF)

**Procedure**

- 1. In the application menu of the Transaction Manager, under Foreign Exchange Trading choose the function Create Financial Transaction (transaction FTR_CREATE).
- 2. Enter a company code, a product type for NDFs, a transaction type, and your business partner.
- 3. If you have specified external number assignment, you enter the key that uniquely identifies a financial transaction within a company code in the Transaction field in the External Number Assignment area. Otherwise, the system will automatically assign a number.
- 4. Enter the desired activity (Order or Contract).
- 5. Choose Create (Enter).
- 6. On the Structure tab page, you enter the transaction data:


Enter the currency pair and the rate.

Enter the Buy/Sell indicator.

Enter the traded currency and the traded amount. The opposite amount will be calculated.

Enter the Value Date.

Enter the Spot Rate.

Enter the Swap Rate.

Enter the Fixing date.

Enter the Settlement Currency.

Enter the Fix.Ref.ID. The fixing information is needed for confirmation using SWIFT MT300.

See also: Define Fixing References

**Note:**

In the activity Define Non-Deliverable Currencies, the system checks which currency is the non-deliverable currency and proposes the other currency as the settlement currency. The settlement currency is the currency in which the settlement amount is paid.

Exception: If the non-deliverable currency is the local currency, the system proposes it as the settlement currency.

You can change the settlement currency proposed. However, settlement has to use one of the currencies involved. Settlement is not possible in a third currency.

The system uses these amounts to calculate the rate and compares this rate against the current entries for currency exchange rates and foreign exchange swap rates in the market data tables. If the entered values differ

significantly from the values stored in the market data tables, the system issues a warning message. Furthermore, the current rates are displayed in the transaction.

If you specify just one amount/currency and the currency of the second amount, and enter the spot rate in the Spot field and the swap rate in the Swap field, the resulting forward price is entered automatically in the Price field (spot + swap = price) and the missing amount is calculated.

The system stores as fixed value the value that you enter manually. When the rate changes subsequently, the manually entered amount is not changed, and the other amount is recalculated.

- 7. Contract Conclusion

In this area, you can enter overall, administrative information relevant to the financial instrument:

Contract date and time

Contact person

Market identifier code (MIC)

Market identifier codes (MICs) are four-character international standard codes (ISO 10383). MICs are used to identify exchanges, trading platforms, and regulated or non-regulated markets as sources of prices and related information to facilitate automated processing (exchanges, settlement, and other automated processes).

For more information, see Market Identifier Code.

Trader

External reference

- 8. Enter the necessary data on the following tab pages:


**Note:**

You create and activate MICs in Customizing under Market Data Management Master Data Specify Market Identifier Codes .

**Note:**

If you use the financial transaction as hedging instrument within the Hedge Management and Accounting of Exposure Items process, you must enter the hedging classification and hedge request on Administration tab and if the hedged exposure item is reference based, you must assign the exposure item ID on FX Hedge Management tab. See also: Create Hedging Instruments

Administration

Here, you enter details such as the general valuation class; this assignment is used to determine the position indicator.

Additional Flows

Here, you enter the agreed charged, for example.

Payment Details

Cash Flow

Memos

Partner Assignment

Status

Analysis Parameter

Creating Data for Default Risk Limits

- 9. Save your entries.

When you save the financial transaction, the position indicator is determined automatically. If the system cannot determine the position indicator, you need to create it manually by choosing Environment Position Indicator .

- 10. To process an NDF further, you can use the function Process Financial Transaction (transaction FTR_EDIT).


**Related Information**

Processing a Non-Deliverable Forward

###### Processing a Non-Deliverable Forward

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Non-Deliverable Forward (NDF) > Process Flow for a Non-Deliverable Forward (NDF) > Processing a Non-Deliverable Forward | L7 | trm05 p.23 | loio `86eaa696502e4a5b902ec2514520cddf` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/86eaa696502e4a5b902ec2514520cddf.html?locale=en-US)

After you have created a non-deliverable forward (NDF), you can process it using the functions available under Transaction Manager Foreign Exchange Trading Process Financial Transaction (transaction FTR_EDIT).

- 1. Enter the company code.
- 2. Enter the transaction number.
- 3. Choose the relevant function for edit the NDF further:


|Function|Procedure|Comments|
|---|---|---|
|Display|1. Choose Display. 2. The display screen for the basic data appears. |The entry fields are not active. To display all data relating to the transaction, you can use the tab pages to navigate to other screens. By choosing Display Partner, you can display the master data for the business partner.|


|Function|Procedure|Comments|
|---|---|---|
|Change|1. Choose Change. 2. The screen for changing basic data appears. Make your changes and save your entries. |You can now overwrite the contents of the active input fields and complete any missing entries. Changes to the "Rate", "Spot", or "Swap" fields: If you make any changes to the values that you entered manually in the Rate, Spot, or Swap fields, the system notes these as fixed values. If you make any later changes, the values determined by the system are changed, but not the values that you entered manually. You can use this function to change an activity, provided that it is not relevant for posting.|
|Execute Order|1. Choose Execute Order. 2. Check the order data for correctness and completeness and save your entries. 3. When you save, the activity category of the transaction is changed to Contract. |With this function, any NDFs that were created as orders are converted to the activity category Contract. If processing category 120 has been defined for the product type, saving the transaction as a contract causes the flows of the transaction to be flagged for posting. (With the processing category 121, the posting flag is not set until the contract is settled.)|
|Settle|1. Choose Settle. 2. The Contract Settlement screen appears. Make your changes and save your entries. 3. When you save a settlement activity, the system changes the activity category of the transaction in order to record how it is monitored and processed in the back office area. The contract can only be posted after it has been settled. |You can use this function with the processing category 121 for settling contracts and for settling fixing. In this way, you can document in a transaction that the transaction has been processed in back office. At this stage, the system checks the financial transaction data and adds any missing data. Furthermore, when you save the transaction, the system fixes the transaction (actual records) and marks the transaction flows relevant for this activity as Flagged for Posting.|
|Fixing|1. When the agreed fixing date is reached, you perform fixing by choosing Fixing.|During fixing, the cash settlement amount is calculated and the corresponding flow is updated.|


|Function|Procedure|Comments|
|---|---|---|
| |2. Enter the fixing rate. The system automatically determines in the settlement currency the settlement amount that the fixing rate would produce. This amount is compared against the amount agreed upon in the transaction in the settlement currency. The difference is the amount for the cash settlement. 3. When all entries are correct, save your entries. |The system creates a derived business transaction for the amount of the cash settlement and this business transaction posts the rate loss/gain to the profit and loss statement.|
|Terminate|1. Choose Terminate. 2. Make the following entries: Date Entry type Specify whether you want to enter the payment amount for the termination of FX transactions directly or calculate it using a rate. Amount Rate Flow type The flow type 1039 Termination amount (of flow category 39) is predefined and set by default. Payment date Payment amount After you entered the relevant data the payment flow is generated, the posting status of the original buy and purchase flows is set to 0. 3. Save your entries. |You can terminate non-deliverable forward transactions early before their maturity. The non-deliverable forward transactions must have the activity category Contract Settlement. When you save the termination activity, the system creates a Termination OTC Transaction business transaction. The Termination business transaction consists of the following flows: Close flow of the OTC transaction at termination date to clear the nominals Termination amount flow (representing the termination flow of the financial transaction) The date of both flows is the payment date entered in the Termination area of the financial transaction. If the terminated FX transaction is used as the hedging instrument in hedging relationships at the termination date, the termination of the FX transactions results in the immediate complete dedesignation of these hedging relationships. The hedging business transaction Termination Dedesignation is automatically created for each associated hedging relationship. For more information, see also Dedesignation by Termination |
|History|1. Choose History. 2. The system lists the activities that have been activated, reversed, or replaced by a follow-up activity. From this list, you can display the individual activities. You also see |The history displays the sequence of previous activities related to a selected transaction.|


|Function|Procedure|Comments|
|---|---|---|
| |their status and the user who processed them.| |


**Note:**

To edit NDFs, you have a choice between using the function described here, Edit Financial Transaction (transaction FTR_EDIT), using the general function Collective Processing for financial transactions (transaction FTR_00), or using the function Forex: Collective Processing (transaction TX06). You can also perform fixing with the manual function Execute Fixing Transaction (transaction TXV5).

###### FX Option (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > FX Option | L5 | trm05 p.26 | loio `c757b4cb9f5845328616d59362b5464d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c757b4cb9f5845328616d59362b5464d.html?locale=en-US)

**Use**

The FX option is an option on a spot exchange transaction and is used as protection from currency fluctuations. The purchaser of a standard FX option, also known as an OTC (over the counter) option, has the right to buy a fixed amount of currency on the exercise date at a previously agreed rate. The option purchaser pays a premium for this right. The amount of the premium paid varies depending on supply and demand in the foreign exchange market. FX options are asymmetrical hedging instruments - this means that rights and obligations are unevenly distributed between the buyers and sellers. Unlike listed instruments, these options are traded directly between business partners with user-defined structure characteristics. The main difference with forward exchange transactions is that the buyer of an option has the right but not the obligation to buy or sell a certain currency amount.

**Note:**

You can assign OTC currency options both to foreign exchange and to derivative financial instruments. You can create currency options in both these areas.

**Activities**

For general information about creating a transaction, see Create Financial Transaction.

For information about creating currency options for activities in Hedge Accounting, see Reference.

**Note:**

When you create a currency option, data (hedge plan, exposure, hedged item, and hedging relationship) is generated automatically in Hedge Management for Exposures.

If you create an option in the “Derivatives” area, you can branch to the Underlying tab. Here you find the data for the underlying spot transaction.

To calculate the option premium, choose Option Price Calculator. (See also Option Price Calculator.)

###### Creating an FX Option (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > FX Option > Creating an FX Option | L6 | trm05 p.26 | loio `c06c258f11fd45aabb0e80b610f4ddc4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c06c258f11fd45aabb0e80b610f4ddc4.html?locale=en-US)

Context

The FX option is an option on a spot exchange transaction and is used as protection from currency fluctuations. The purchaser of a standard FX option, also known as an OTC (over the counter) option, has the right to buy a fixed amount of currency on the exercise date at a previously agreed rate. The option purchaser pays a premium for this right. The amount of the premium paid varies depending on supply and demand in the foreign exchange market. FX options are asymmetrical hedging instruments - this means that rights and obligations are unevenly distributed between the buyers and sellers. Unlike listed instruments, these options are traded directly between business partners with user-defined structure characteristics. The main difference with forward exchange transactions is that the buyer of an option has the right but not the obligation to buy or sell a certain currency amount.

**Procedure**

- 1. Open the Create Financial Transaction app or the Create OTC Option app on SAP Fiori launchpad.
- 2. Enter the company code, product type (such as 76A), transaction type (100 (Buy) or 200 (Sell), and the business partner. When you create a currency option, you are documenting the intention to buy or sell a currency option.
- 3. If you want to assign the transaction to a portfolio, enter a portfolio in the Limits area. Alternatively, you can enter a portfolio on the Administration tab in the Position Assignment area.
- 4. In the Activity area, choose whether you want to create the transaction as a contract or as an order.
- 5. Choose Enter to branch to the basic data screen for the option. On the Structure tab, you enter the actual transaction data for the purchase or sale.
- 6. Enter the expiry date and expiry time for the option.

The Expiry Time field is available for input only if you have assigned predefined location codes to specific times using the Define Values for Expiry Time app.

- 7. Select the exercise type (European or American) and the settlement type (Cash Settlement, Physical Exercise, Not Yet Specified).
- 8. Enter the currency pair and the strike.
- 9. Specify whether the option is a put or a call.
- 10. Enter the traded currency and the traded amount. Note: The offsetting amount is calculated by the system.
- 11. Enter the value date: This is the payment date on which the option is exercised (generally, two working days after the exercise date).
- 12. You can define the current spot rate as a spot reference in the transaction data.
- 13. The Option area contains the following fields:

Strike Price: As well as the currency keys, you also need to enter the traded amount and a rate fixed in advance (the strike price).

Value Date

- 14. In the Premium area, specify the following for the option premium:

- a. Select the premium notation (Points or Percent).
- b. Enter the points or percentage.
- c. Select the desired flow type.
- d. Select the payment date for the premium.
- e. Choose the currency in which the premium is to be paid. If this currency is one of the currencies in the currency pair for the option, the system calculates the amount automatically when you enter the percentage or points.


- 15. From here, you can branch to the entry screens for general transaction management functions. You can use the tabs to navigate between the different screens. For more information, see also Tabs.


If you use the financial transaction as hedging instrument within the Hedge Management and Accounting of Exposure Items process, you must enter the hedging classification and hedge request on Administration tab and if the hedged exposure item is reference based, you must assign the exposure item ID on FX Hedge Management tab. See also: Create Hedging Instruments

- 16. To store the transaction, choose Save.


Comment: When you conclude a transaction, the cash flow consists only of the premium. You can create both European and American types of option in the system (settlement).

###### Processing an FX Option (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > FX Option > Processing an FX Option | L6 | trm05 p.28 | loio `e687e03c06494d4b96fe10505da2b905` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e687e03c06494d4b96fe10505da2b905.html?locale=en-US)

After you have created an FX option the following functions are available for further processing of interest rate instruments.

**Use**

You can process FX options using Manage Financial Transactions, Process Financial Transaction, or Process FX Options Collective Processing apps on SAP Fori launchpad. In the area menu in back-end system, you can use the functions Process Financial Transactions (transaction FTR_EDIT) and OTC Option: Collective Processing (transaction TI91).

Functions available for processing FX options:

|Function|Entries|Comments|
|---|---|---|
|Change|Choose Change. The screen for changing the transaction structure appears. Make any necessary changes and save the financial transaction.|You can overwrite the active entry fields or enter data in the empty fields. You can use the tab pages to branch to the general transaction management screens and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are Flagged for Posting.|
|Settle|Choose Settle. The Settle screen appears. When you save a settlement activity, the system changes the activity category of the transaction to record that it is monitored and processed in the back office area. The contract can only be posted after it has been settled.|When you use the Settle function, you can indicate the financial transaction to record that it has been processed in the back office. At this stage, you check the financial transaction and add any missing data. When you save the transaction, the system fixes the transaction (actual records) and flags the transaction flows for posting.|
|Exercise|Choose Exercise. The screen for displaying the transaction data appears. In the case of cash settlement, the Cash Settlement area appears on the Structure tab.|You can only exercise an OTC option when it has reached the exercise date. When you exercise the option with cash settlement, the settlement amount is calculated on the basis of the difference|


|Function|Entries|Comments|
|---|---|---|
| |When you save the option, it is stored in the relevant activity category.|between the strike and the current market price. If the current exchange rate in market data is so that you will receive money for your purchased option the system calculates the cash settlement amount via a given exchange rate. Otherwise the system shows no amount. For a sold option this is vice versa. Your option buyer will only exercise the option when he gets money, so the system calculates only outgoing cash settlement amounts or shows no amount. In case your want to pay (or receive) money in a third currency, the calculation is not supported. Just enter the amount and currency negotiated with your counterparty. In the case of physical exercise, the system creates the underlying (spot) transaction, when you save the activity exercise settlement, see the next step.|
|Exercise settlement|Choose Exercise Settlement. When you save the option, it is stored in the relevant activity category.|In the case of physical exercise the system creates the underlying (spot) transaction when you save the activity. You have to save the automatically created sport transaction as well. At the end the financial transaction number of the underlying transactions is displayed on Structure tab of the option. In addition, you have to settle the underlying transaction as well.|
|Expiration|Choose Expiration. The screen for displaying the transaction data appears.|If the option has no value, it is deleted. As is the case with exercise, you may have to settle this expiration again, depending on the processing category.|
|Give notice|Choose Give Notice. The Give Notice on OTC Option: Initial screen appears.|When you give notice on an OTC option, the transaction remains active and is transferred to the termination activity category. When you value this transaction again, any unrealized gains and losses that have already been posted are reset.|
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the |


|Function|Entries|Comments|
|---|---|---|
| |for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.|corresponding field. Enter the key for the reversal in the Reversal Reason field.|
|Display|Choose Display. The screen for displaying the structural characteristics appears.|The entry fields are not active. You can use the tab pages to navigate between the various screens and display the other transaction data. Choose to go to the master data for the business partner.|
|Display history|Choose History. The system lists the activities that are active, reversed or have been replaced by a follow-up activity. From this list, you can branch to the display for the individual activities. You also see their status and the user who processed them.|The history function allows you to trace the activity sequence so far for the transaction you have selected.|

###### Internal Foreign Exchange Trading

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Internal Foreign Exchange Trading | L5 | trm05 p.30 | loio `1e14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1e14da531198434de10000000a174cb4.html?locale=en-US)

**Use**

This is a process for entering foreign exchange transactions locally from the view of the company code entering the transactions.

A subsidiary company can use the transaction closing function to request an exchange rate for a foreign exchange transaction (spot exchange, forward exchange, foreign exchange swap) from the head office. You can accept this exchange rate and close the transaction.

In transaction closing, the rate is automatically created from the view of the head office in the company code of the head office. You can also create this transaction in the company code of the subsidiary as a mirror transaction .

**Integration**

See Mirror Transactions .

**Prerequisites**

For more information about the prerequisites that must be fulfilled before you can use the internal foreign trading functions, see the following sections of the Implementation Guide:

Choose Foreign Exchange Transaction Management Internal Foreign Exchange Trading

- 1. Map Product Types and Transaction Types
- 2. Define Rate Mark Up/Down for Internal Foreign Exchange Trading
- 3. Assign Company Codes to Partners
- 4. You can influence the process using a BAdI for internal foreign exchange trading .


The automatic exchange rate setting function also requires a datafeed to provide real-time exchange rates and foreign exchange swap rates. The datafeed provides the data in the market data buffer (table VTB_MARKET).

**Features**

The products supported are:

Spot Exchange Transactions

Forward Exchange Transactions

Foreign Exchange Swaps

The input screen is different depending on which financial instrument you use.

You can use a BAdI to control the process flow of the transaction ( FTR_FX_INT_EXIT).This enables you to implement your own default values and validations or your own complex exchange rate adjustments.

Internal foreign exchange trading includes the following transactions:

Transaction Closing

Exchange Rate Overview

###### Transaction Closing

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Internal Foreign Exchange Trading > Transaction Closing | L6 | trm05 p.31 | loio `7214da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7214da531198434de10000000a174cb4.html?locale=en-US)

**Prerequisites**

For more information, see Internal Foreign Exchange Trading .

**Process Flow**

After you have entered the required data, this data is mirrored and presented to the central company code for an automatic check. If the checks are successful, the system provides an exchange rate for the data.

The function module FTR_REALTIME_RATE_SERVICE provides the current exchange rates from the real-time datafeed For technical details, see the system documentation. You can accept the exchange rate that the system proposes within 60 seconds.

You can influence this time period using the BAdI described in the section Internal Foreign Exchange Trading. Once the time limit has expired, you can enter another request.

The system calculates the exchange rate based on the value date you entered with the request and displays the underlying spot rate and swap rate. If the value date is the next listed “spot value date”, the system specifies only the spot rate.

In “cross transactions”, the system first tries to read the cross exchange rate or cross swap records in the market data buffer. If there is no cross exchange rate or cross swap rate, the system calculates these from the respective exchange rates/swap rates of the purchase or sales currency for the local currency of the central company code (base currency).

Once the system has calculated the exchange rate or interpolated the swap rate, you can check and modify the results in the BAdI stated above.

Using the settings in the IMG activity under Distribution of Mirror Transactions , you can mirror the transaction you have created from the central company code back to the local company code.

**Result**

See Exchange Rate Overview .

###### Exchange Rate Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Internal Foreign Exchange Trading > Exchange Rate Overview | L6 | trm05 p.32 | loio `7e14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7e14da531198434de10000000a174cb4.html?locale=en-US)

**Purpose**

In addition to entering internal foreign exchange transactions, you can also use the report Exchange Rate Overview for Internal Foreign Exchange Transactions . This gives you an overview of the current exchange rates for each currency. You can also use this report to check the Customizing and the market data for completeness.

For more information about internal foreign exchange trading, see Transaction Closing .

**Prerequisites**

For more information, see Internal Foreign Exchange Trading .

**Process flow**

Choose the company code, and as required, the base currency, reference currency, currency, and required layout.

An exchange rate overview appears with the current exchange rates valid for internal foreign exchange trading.

The fields Currency and Base Currency determine the currency pairs for which exchange rates are calculated. The field Reference Currency defines whether a third currency is to be used for the calculation.

**Example**


You want to create the exchange rate overview for a subsidiary that has a different local currency to the head office. The local currency of the subsidiary is USD, the local currency of the head office is EUR.

Entry in the general selections for the report Overview for Internal Foreign Exchange Transactions :

Company code: xxxx <Company code of subsidiary>

Base currency: USD <Local currency of subsidiary>

Reference currency: EUR <Local currency of head office>

Currency: <can remain empty>

Result :

Calculated exchange rate data for all internal listed currencies based on USD, whereby the exchange rates in the market data buffer are only available based on EUR.

###### Position Monitor

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Foreign Exchange > Position Monitor | L5 | trm05 p.33 | loio `7f757d531efc7e0de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7f757d531efc7e0de10000000a4450e5.html?locale=en-US)

**Use**

You can use the Position Monitor function in foreign exchange trading to get a quick, up-to-date overview of the current foreign currency risk from all transactions that you have created in the Transaction Manager.

You can structure the display by freely-definable time periods that suit your needs. In addition, the net present value is calculated for payment flows on the basis of the latest fair values.

**Prerequisites**

The net present values are transferred from the component Market Risk Analyzer. To use the Position Monitor function, you must make the settings for the Market Risk Analyzer in Customizing, which means that you need to define rates, yield curves, volatilities and so on. For more information, see the documentation in the Implementation Guide of the Market Risk Analyzer.

**Activities**

Selection:

Use the selection criteria to select the financial transactions to be analyzed.

Output Control:

Enter the required currency, the maturity band, and the factory calendar ID. You can define your own maturity bands to collect cash flows in periods you define.

Valuation:

If you want to perform Valuation, select the relevant indicator.

Display:

The currency items are displayed in the maturity band that you have specified. Each currency has a separate line, and each period a separate column.

If you have activated the valuation function, the cash value of the position is displayed as well as the total position per currency.

You can double-click a position segment to display the individual list of the flows contained in that segment (for example, period 07/18/2003 - 07/21/2003, currency EUR).

From this display, you can double-click to navigate to the issue structure data of the relevant transaction (for example, spot/forward transaction).

Datafeed provides the current exchange rates either in real time or asynchronously using the market data buffer.

You can use the three methods of the Business Add-In FTR_TR_POSMON to enhance the selection of the Position Monitor and indicate individual cash flows flexibly with your own criteria. You can also implement your own valuation methods.

##### Money Market Transactions (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions | L4 | trm05 p.34 | loio `37dbd7531a4d414de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/37dbd7531a4d414de10000000a174cb4.html?locale=en-US)

**Purpose**

Money market transactions are for short- to medium-term investments or borrowings using liquid assets.

**Integration**

You can implement cash management decisions in the “Money Market” area based on the liquidity surplus or deficit determined in Cash Management or in the financial status. The system records the impact transactions have on the liquidity of a company by value date, for each flow in Cash Management. To do this, the system transfers the data automatically to Cash Management. This integration simplifies the work processes involved in transaction management from entering potential transactions through to the related accounting activities. You have access to the functions for period-based accrual/deferral, key date valuation and foreign currency valuation, as well as to the profit and loss statement function.

It is also closely linked to the Financial Accounting (FI) component since all the data that is relevant for posting in the Money Market area is automatically transferred to FI.

The following graphic shows how the above-mentioned components relate to each another:

[figure TRM05-F003]

**Features**

Front Office

Traders enter the money market transactions. Besides entering transactions, they can also call up information about previously entered transactions or to make subsequent changes to existing ones. Collective processing functions are available to help you manage your transactions efficiently. You can enter the following money market transactions:

Fixed-Term Deposits

Deposits at Notice

Commercial Papers

Interest Rate Instruments

Cash Flow Transactions

Facilities

Back Office

Once financial transactions have been entered, they are settled in the back office. The key aspects of postprocessing are as follows:

Entering additional transaction data, such as adding information that is relevant for back-office processing

Preparing for posting and payment, for example, by checking the accounts used

Generating correspondence in the form of internal or external confirmations

Collective processing functions are also available in the back office. The back-office also includes functions for netting transactions and for entering or editing references.

Accounting

Once you have entered, checked, and completed the transactions, you then have submit them to Accounting for processing. The accounting area includes functions for transferring data to Financial Accounting, such as posting reports or position management postings. It also includes functions for parallel valuation.

Master Data Management

You use master data to manage transactions in the Transaction Manager.

Information System

The information system provides a range of reports for analyzing your money market transactions. The Money Market Information System is part of the Transaction Manager information system, which offers analyses and evaluations across the whole of the Treasury and Risk Management dataset.

The link to the SAP Query also allows you to define your own reports in addition to those provided by SAP.

See also:

Information System

The following graphic represents the architecture of the financial transactions.

[figure TRM05-F004 - The following graphic represents the architecture of the financial transactions.]

###### Fixed-Term Deposits

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Fixed-Term Deposits | L5 | trm05 p.36 | loio `1d07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1d07da531198434de10000000a174cb4.html?locale=en-US)

**Use**

A fixed term deposit is a money market transaction with fixed interest condition and final repayment.

The trading of fixed-term deposits (including overnight money and eurocurrency) includes transactions with fixed interest rates and an end of term arranged at the start. This includes the transaction types fixed-term deposit investment and fixed-term deposit borrowing. If the authorized business partners and corresponding payment details are already defined in the standing instructions, the required entries are restricted to the required entries in the structural characteristics. In addition to functions for entering and changing fixed-term deposits, the system also supports functions for rollovers and reversals.

You only have to define the standard interest calculation method and the calendar you want to use once, and these will then be used as default values for the transaction.

**Related Information**

Creating Fixed-Term Deposit Transactions Processing Fixed-Term Deposits

###### Creating Fixed-Term Deposit Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Fixed-Term Deposits > Creating Fixed-Term Deposit Transactions | L6 | trm05 p.37 | loio `0d10da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0d10da531198434de10000000a174cb4.html?locale=en-US)

**Procedure**

- 1. In the SAP Easy Access menu choose Treasury and Risk Management Transaction Manager Money Market Trading Create Financial Transaction
- 2. Specify the Company Code , Product Type , Transaction Type , Partner and Portfolio in the parameter settings on the initial screen.

The portfolio serves only as an evaluation characteristic.

- 3. If you are using external number assignment, enter a transaction number. If you are using internal number assignment, the system assigns the number.
- 4. Choose Enter .
- 5. This brings you to the basic data screen for the fixed-term deposit. Enter the basic data for the transaction.

You must enter at least the Amount , the term ( Start , End ), the interest structure (Percentage rate and Interest calculation method ) and the Contract Date .

Double clicking on one of the fields in the Interest Structure area of the screen takes you to the detail screen for setting the interest conditions.

- 6. Save your entries.


**Note:**

The transaction type determines whether the transaction involves accepting a fixed-term deposit (liability side transaction) or making a fixed-term deposit (asset transaction).

###### Processing Fixed-Term Deposits

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Fixed-Term Deposits > Processing Fixed-Term Deposits | L6 | trm05 p.37 | loio `2107da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2107da531198434de10000000a174cb4.html?locale=en-US)

Prerequisites

For more information, see Fixed-Term Deposit.

**Procedure**

Choose “Change Financial Transaction”. From here, you can access all the trading and processing functions for fixed-term deposits. These include the following:

|Function|Entries|Comment|
|---|---|---|
|Create|For information on creating fixed-term deposits, see Creating Fixed-Term Deposit Transactions. | |
|Change|Choose Change. The screen for changing basic data appears. You can now overwrite the active entry fields or enter data in the empty fields.|You can use the tab pages to branch to the general transaction management screens and make any necessary changes. |
|Display|Choose Display. The display screen for the structure characteristics appears. The entry fields are not active.|You can use the tab pages to navigate between the various screens and display the other data relating to the transaction. You can branch to the master data for the business partner.|
|Roll Over|Choose Roll Over. The screen for entering the basic data for the rollover appears. If you want to change the amount invested or borrowed, enter the amount and the flow type in the corresponding fields to indicate whether you want to increase or decrease the amount for the rollover. You use the For Rollover field to specify how you want to handle interest flows that are due on the rollover date. The interest can either be paid on the rollover date or capitalized, or deferred to the specified date.|You can roll over a fixed-term deposit - with changed conditions, if applicable - and keep the same transaction number. You can display the transaction activity at a particular point in time or in its historical sequence with all the corresponding information. With the memo book function, you can enter additional information for each activity. By choosing Extras → Amount Overview, you view a list of all transaction-related capital flows and interest flows sorted according to amounts that are due prior to/on the respective key date. You can add the new end of term in fast processing. When you roll over the transaction, you add a new activity to the transaction. The activity is processed in accordance with the transaction and position management control settings. You can alter the end of term of a fixed-term deposit until repayment provided that shortening the term will not effect an|


|Function|Entries|Comment|
|---|---|---|
| | |interest flow that has been released, posted or manually changed.|
|Reverse|For information about reversing money market transactions, see Reverse . | |
|History|Choose History. The system lists the activities that have been activated, reversed, or replaced by a follow-up activity. From this list, you can display the individual activities. You also see the status and the user who processed the transaction.|The history displays the sequence of previous activities related to a selected transaction.|
|Settle|Choose Settle. The Contract Settlement screen appears. Choose the area from the menu for which you want to enter or change the settlement data. When you save a settlement activity, the system changes the activity category of the transaction in order to record how it is monitored and processed in the back office area. The contract can only be posted after it has been settled.|Using the “Settle Fixed-Term Deposit" function, you can mark a transaction to document that it has been processed in the back office. At this stage, the system checks the financial transaction data and adds any missing data. Also, when you save the transaction, the system fixes the transaction (actual records) and marks the transaction flows as Flagged for Posting. For more information, see Settlement. |

###### Deposits at Notice

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Deposits at Notice | L5 | trm05 p.39 | loio `a808da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a808da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Deposits at notice are investments or borrowings without a fixed term. The deposit at notice function therefore not only includes the functions available in the fixed-term deposit area, but also a function for giving notice. This means that, in addition to entering the amounts and conditions, you enter the notice period and the interest payment date and frequency.

**Related Information**

Creating Deposits at Notice Processing Deposits at Notice

###### Creating Deposits at Notice

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Deposits at Notice > Creating Deposits at Notice | L6 | trm05 p.39 | loio `9708da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9708da531198434de10000000a174cb4.html?locale=en-US)

Deposits at notice are investments or borrowings without a fixed term. The deposit at notice function therefore not only includes the functions available in the fixed-term deposit area, but also a function for giving notice. This means that, in addition to entering the amounts and conditions, you enter the notice period and the interest payment date and frequency.

**Procedure**

- 1. Choose Create.
- 2. Enter the company code, product type, transaction type, and the business partner.

Optionally, you can make entries in the Limits area:

Currency: If you do not specify a currency when you create a financial transaction, the company code currency is applied automatically.

Portfolio: If you want to assign the transaction to a portfolio, enter a portfolio in the corresponding field.

Alternatively, you can enter a portfolio on the Administration tab in the Position Assignment area.

- 3. If you work with external number assignment, you have to enter a key for the transaction in the corresponding field, which enables it to be uniquely identified within a company code. Otherwise, the system assigns a number automatically and displays this number when you save the transaction.
- 4. Choose Enter to branch to the basic data screen for the transaction. On the Structure tab, you enter the actual transaction data for the purchase or sale.


- 5. Enter the structure data, such as the amount, term, interest structure (percentage rate, interest calculation method, frequency), and the contract data. You enter the amounts and the structure characteristics, as well as the period of notice, the payment date, and the payment frequency for interest.
- 6. To store the transaction, choose Save.
- 7. You can also branch to the entry screens for the general transaction management functions. You can use the tabs to navigate between the different screens.
- 8. For more information, see Tabs.


- 9. In the upper menu bar, you can access other functions by choosing Extras and Environment.
- 10. See also Condition Details.

- 11. For information about creating a mirror transaction, see “Mirror Transactions”.


Comments

Since the end of the term for a deposit at notice is not known until notice is given on it, the cash flow of such transactions can only be created for a certain period that can be set in the configuration. Beyond that period, the cash flow has to be periodically updated for deposits at notice on which notice has not yet been given.

In addition to entering the main flow at rollover date, you can also enter for deposits at notice other principal increases and decreases during the term, thereby allowing you to map repayment schedules, for example.

You can create a money market transaction directly as a contract. Once a transaction has acquired the transaction type Contract, it becomes legally binding.

Which activity sequence is applied depends on the processing category setting (with/without settlement) made in Customizing.

Within transaction management, you can branch from each application to the business partner management functions to create, display, and change business partners and maintain their payment details.

Each activity within transaction management (contract, back office, and so on) can be analyzed in Cash Management and Forecast.

**Related Information**

Deposits at Notice Processing Deposits at Notice Intercompany Trading Process

###### Processing Deposits at Notice

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Deposits at Notice > Processing Deposits at Notice | L6 | trm05 p.41 | loio `1a08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1a08da531198434de10000000a174cb4.html?locale=en-US)

Deposits at notice are investments or borrowings without a fixed term. The deposit at notice function therefore not only includes the functions available in the fixed-term deposit area, but also a function for giving notice. This means that, in addition to entering the amounts and conditions, you enter the notice period and the interest payment date and frequency.

**Procedure**

|Function|Entries|Comments|
|---|---|---|
|Fast data entry|Choose Fast Data Entry. A fast entry screen appears on which you enter just the key data, such as product type, transaction type, partner and structural data.|The fast entry function enables you to enter the most common transactions more quickly.|
|Create|For information on creating deposits at notice, see Creating Deposits at Notice. | |
|Change|Choose Change. The screen for changing basic data appears. You can now overwrite the active entry fields or enter data in the empty fields.|You can branch to the general transaction management screens using the corresponding tab pages and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are Flagged for Posting.|
|Display|Choose Display. The screen for displaying the structural characteristics appears. The entry fields are not active.|You can use the tab pages to navigate between the various screens and display the other transaction data. Choose to go to the master data for the business partner.|
|Roll over|Choose Roll Over. The screen for entering the basic data for the rollover appears. If the rollover is linked to a change in the amount invested or borrowed, you enter the|Here, rollover refers to an amount increase or decrease of the initial deposit at notice with changed conditions under the same transaction number if required. If you have set up the Settlement activity in Customizing, settlement must take place|


|Function|Entries|Comments|
|---|---|---|
| |Amount and the Flow type in the corresponding fields. This indicates whether the amount is an increase or decrease. You enter the rollover date for the Term in the Rollover field. You can change the other active entry fields in the Interest structure and Contract data areas.|prior to rollover.|
|Give notice|Choose Give Notice. The screen for giving notice appears. Enter the notice date in the Give Notice field.|After you enter a deposit at notice, it remains active until you terminate it using the Give Notice function.|
|Reverse|For information on reversing Money Market transactions, see Reversal. | |
|History|Choose History. The system lists the activities that are active, reversed or have been replaced by a follow-up activity. From this list, you can branch to the display for the individual activities. You also see their status and the user who processed them.|The history function displays the sequence of previous activities for a selected transaction.|
|Settle|Choose Settle. The Contract Settlement screen appears. Choose the area from the menu for which you want to enter or change the settlement data. When you save a settlement activity, the system changes the activity category of the transaction to record how it is monitored and processed in the back office area.|Using the function Settle Deposit At Notice, you can mark the transaction to indicate that it has been processed in the back office. At this stage, you check the entries and add any missing data. When you save the transaction, the system fixes the data (actual records) and flags the transaction flows for posting. For more information, see Settlement. |
|Update cash flow|Select Cash Flow Update. You now decide whether you want to perform a test run, which does not make changes to the database, or whether you want to perform an update run. The system displays an overview of the cash flows of the transactions concerned. The new flows are marked in a different color to distinguish them from the flows that already existed.|Since the end of the term of a deposit at notice is not known until notice is given on it, the cash flow of such transactions can only be created for a certain period in the future. This means that the cash flow has to be periodically updated for deposits at notice on which notice has not yet been given.|


**Related Information**

Deposits at Notice Creating Deposits at Notice

###### Commercial Paper

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Commercial Paper | L5 | trm05 p.43 | loio `1219c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1219c55368511d4be10000000a174cb4.html?locale=en-US)

**Definition**

Commercial Paper transactions are transactions on which no interest payments are made during the term of the transaction. Instead, two business partners agree on a repayment amount to be repaid to the investor by the borrower at the end of the life of the contract.

**Example**

A company requires 1 million for three months. The amount is discounted using a pre-defined yield. The company receives the discounted amount, 980,000 from an investor. At the end of the term, the company repays the full amount of 1 million.

See also:

Create Commercial Paper

Process Commercial Paper

###### Creating a Commercial Paper

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Commercial Paper > Creating a Commercial Paper | L6 | trm05 p.43 | loio `651de1b291bf41328c4ad4fab09df169` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/651de1b291bf41328c4ad4fab09df169.html?locale=en-US)

**Context**

Commercial Paper transactions are transactions on which no interest payments are made during the term of the transaction. Instead, two business partners agree on a repayment amount to be repaid to the investor by the borrower at the end of the life of the contract.

A company requires 1 million for three months. The amount is discounted using a pre-defined yield. The company receives the discounted amount, 980,000 from an investor. At the end of the term, the company repays the full amount of 1 million.

**Procedure**

- 1. Open the Create Commercial Paper app on SAP Fiori launchpad.
- 2. Enter the Company Code, Product Type, Transaction Type and the Business Partner. For product type 53A Commercial Paper the following transaction types are available:


**Note:**

For the creation of financial transactions you can also use the Manage Financial Transactions app or the Create Financial Transaction app.

|Transaction Type Number|Transaction Type Name|
|---|---|
|100|Purchase (NPV with interest)|
|101|Purchase (Nominal with interest)|
|102|Purchase (Nominal without Interest)|
|200|Sale (NPV with interest)|


|Transaction Type Number|Transaction Type Name|
|---|---|
|201|Sale (Nominal with interest)|
|202|Sale (Nominal without Interest)|


[figure TRM05-F007]

[figure TRM05-F008]

[figure TRM05-F009]

**3. You can make the following entries in the Specifications section:**

Currency

If you do not specify a currency, the system automatically uses the currency of the company code.

Portfolio

Here you specify whether a transaction should be assigned and the portfolio to which it should be assigned.

**4. If you use external number assignment, now assign a code for the transaction that identifies it uniquely within a company code. If you do not specify a value, the number will be allocated automatically by the system.**

- 5. From here, you can branch to the entry screens for general transaction management functions. You can use the tabs to navigate between the different screens.

Administration

Other Flows

Payment Details

Cash Flow

Memos

Status

Analysis Parameter (RM)

Creating Data for Default Risk Limits

- 6. Choose Enter to go to the basic data screen for the transaction. Enter or change transaction data and save your transaction. Use the buttons for detailed screen information, such as Correspondence, Conditions, or Effective Interest Rate.

To use additional functions, choose Extras and Environment from the menu.

You find the following functions in the menu under More Extras or More Environment :

Effective Interest Rate

You use this function when you process transactions in the Money Market area to calculate the internal interest flows and update these to the database. You can use the effective interest for evaluations as part of reporting.

- a. You can generate a list of financial transactions with an unknown effective interest or using specific transaction numbers.
- b. You can also choose whether to carry out a test run or an update run.
- c. Choose Execute.
- d. The system generates a calculation log.


Position Indicator

Choose Environment Position Indicator to go to the class position.

- 7. To store the transaction, choose Save.

###### Process Commercial Paper

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Commercial Paper > Process Commercial Paper | L6 | trm05 p.45 | loio `5af902380065420aae3d1ab79ed6a7f9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5af902380065420aae3d1ab79ed6a7f9.html?locale=en-US)

Commercial Paper transactions are transactions on which no interest payments are made during the term of the transaction. Instead, two business partners agree on a repayment amount to be repaid to the investor by the borrower at the end of the life of the contract.

A company requires 1 million for three months. The amount is discounted using a pre-defined yield. The company receives the discounted amount, 980,000 from an investor. At the end of the term, the company repays the full amount of 1 million.

**Key Features**

The app Process MM Transactions - Collective Processing provides the following key features for the financial instrument Commercial Paper:

|Function|Entries|Comments|
|---|---|---|
|Change|Select an entry from the list and choose the Change icon from the header bar of the app. The screen for changing basic data appears. You can now overwrite the active entry fields or enter data in the empty fields.|You can branch to the general transaction management screens using the corresponding tabs and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are flagged for posting.|
|Display|Select an entry from the list and choose the Display icon from the header bar of the app. The screen for displaying the structural characteristics appears. The entry fields are not active.|You can use the tab pages to navigate between the various screens and display the other transaction data. Choose the Display Partner icon to go to the master data for the business partner.|
|Give Notice|Select an entry from the list and choose the Give Notice icon from the header bar of the app. The screen for giving notice appears. Enter the notice date in the Give Notice field.|After you have entered a deposit at notice, it remains active until you terminate it using the Give Notice function.|


|Function|Entries|Comments|
|---|---|---|
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. |
|History|Select an entry from the list and then choose the History icon from the header bar of the app. The system lists the activities that are active, that have been reversed, or that have been replaced by a follow-up activity. From this list, you can display the individual activities. You also see their status and the user who processed them.|The history function displays the sequence of previous activities for a selected transaction.|
|Settle|Select an entry from the list and then choose the Settle icon from the header bar of the app. The Contract Settlement screen appears. When you save a settlement activity, the system changes the activity category of the transaction to record how it is monitored and processed in the back office area.|With the Settle Deposit at Notice function, you can mark the transaction to indicate that it has been processed in the back office. At this stage, you check the entries and add any missing data. When you save the transaction, the system fixes the data (actual records) and flags the transaction flows for posting.|


**Generice Features**

Set a processing indicator by selecting an entry from the list and choosing the Set Processing Indicator button in the header bar

Display the related correspondence from the processing screen of the individual financial transaction

Display the conditions of the money market transaction from the processing screen of the individual transaction

Display the effective interest rate of the transaction from the processing screen of the individual transaction

View the details of a specific money market transaction by selecting a row in the table and choosing the Details icon in the header bar

Navigate to the corresponding partner, facility, or master agreement by choosing More Goto

Export the results list to a spreadsheet by choosing More List Export Spreadsheet

Save a specific variant and/or layout according to your preferred settings

**Supported Device Types**

Desktop

###### Interest Rate Instruments

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Interest Rate Instruments | L5 | trm05 p.48 | loio `0f08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f08da531198434de10000000a174cb4.html?locale=en-US)

**Use**

An interest rate instrument is a money market transaction with additional structural characteristics, such as Fixed, Variable, Scaled (Incremental), and Scaled (Interval) interest conditions.

Interest rate instruments with term category Fixed-Term have a repayment method (for example, final repayment, installment repayment, or annuity repayment).

Interest rate instruments with term category At Notice do not have term end dates. The repayment flow is generated only when the Give Notice function is executed.

To calculate the corresponding interest receivables or payables for variable interest conditions, you must make an interest rate adjustment. See Adjust Variable Rates/Prices.

In countries/regions with a high inflation rate, it may be necessary to adjust the interest and repayment flows based on price indexes such as IGP-M, IGP-DI, IPCA, INPC, INCC, and CPI. For price-index related product types, specific functions are available:

You decide in the Customizing of the product type in the field Index Calculation, whethter the price index is applied only on the interest flows or on the interest flows and the repayment flow.

A specific area for the Index Adjustment settings is available on the Structure tab.

A Price Index Adjustment tab is available for price-index related product types, For interest rate transactions of product types related to price indexes, price index adjustments are made periodically throughout the term. This tab shows you the current values.

You can enter price index values using the function Enter Price Index Values (transaction TMDPRICEIDX).

The function Automatic Rate/Price Adjustment (transaction TJ05) supports price-index adjustments.

The index valuation is available as valuation step for index-related interest rate instruments only if the price index is also applied in the repayment. This is because the price index affects the book value in this case.

For the price index-related product types, the accrual/deferral is first calculated for the index-clean amount. The accrual/deferral is then multiplied by the price index factor that is valid on the accrual/deferral key date.

**Prerequisites**

You have to create your business partners, assign the corresponding roles to these partners, and maintain the transaction authorizations.

You have to set up the standing instructions (correspondence, payment details) and released the business partner.

Customizing

Define the product types. You create financial transactions and manage positions on the basis of product types. Here you decide on the term category of the product type. Examples of product types are:

Interest Rate Instrument

Interest Rate Instrument at Notice

In the field Index Calculation, you can choose between the following settings:

Price Index is not used

Price Index Applied on Interest

Price Index Applied on Interest and Repayments

Define the transaction types. Transaction types determine the type of transaction that can be concluded with a particular product type. They also control the transaction and position management process. Example: Investment or Borrowing transactions for an interest rate instrument.

Define the flow types. These describe the various changes to the cash flows. Example: Increase in Nominal Amount

You must assign flow types to transaction types.

Define the condition type. The condition type is used to control which structural characteristics are displayed when you create transactions. Example: Nominal Interest

Other settings are necessary for the complete process, such as settings for update types and settings for account determination. This is similar for all financial transactions managed Treasury and Risk Management.

If you are using price-index related product types, you must define the needed price indexes in the Customizing of Treasury and Risk Management under Basic Functions Market Data Management Master Data Indexes Define Price Index . Furthermore, the current values of the price indexes need to be entered into the market data table on a regular basis.

For variable-interest conditions, the relevant reference interest rates must be defined in Customizing of Treasury and Risk Management under Basic Functions Market Data Management Master Data Settings for Ref. Interest Rates and Yield Curves Define Reference Interest Rates . Further, the current values of the reference interest rates must be

entered regularly in the market data table.

**Features**

To manage interest rate instruments, you can use the standard functions and processes for entering, editing, and processing transactions, managing their status, and transferring data to Financial Accounting.

- 1. Create the interest rate instrument using the Create IR Instrument app or the Create Financial Transaction function (transaction FTR_CREATE).
- 2. Settle the interest rate instrument using the Process MM Transactions - Collective Processing app or the Process Financial Transaction function (transaction FTR_EDIT).
- 3. Post Flows


- 4. During the lifecycle of the financial transaction, the following functions need to be executed on a regular base:


Adjust variable interest rates and price indexes using the Process Automatic Adjustments - Rates/Prices app.

For more information, see also Adjust Variable Rates/Prices.

Period-end closing:

Run Valuation

Run Accrual/Deferral

For the price index-related product types, the accrual/deferral is first calculated for the index-clean amount. The accrual/deferral is then multiplied by the price index factor that is valid on the accrual/deferral key date.

The process is finished when the last repayment flow is posted.

**Related Information**

Creating an Interest Rate Instrument Processing Interest Rate Instruments

###### Creating an Interest Rate Instrument

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Interest Rate Instruments > Creating an Interest Rate Instrument | L6 | trm05 p.50 | loio `ef166c9895d64aaabb5e836fbfd985f0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ef166c9895d64aaabb5e836fbfd985f0.html?locale=en-US)

**Procedure**

- 1. Open the Create Financial Transaction (App ID: FTR_CREATE), Manage Financial Transactions (App ID: F6157) or Create IR Instrument (App ID: TM_51) app.
- 2. Enter the company code, the product type, the transaction type, and the business partner. Optionally, you can make entries in the Limits area:

Currency: If you do not specify a currency when you create a financial transaction, the company code currency is applied automatically.

Portfolio: If you want to assign the transaction to a portfolio, enter a portfolio in the corresponding field.

Alternatively, you can enter the portfolio and the master agreement on the Administration tab in the Position Assignment area.

If you work with external number assignment, you have to enter a key for the transaction in the corresponding field, which enables it to be uniquely identified within a company code. Otherwise, the system assigns a number automatically and displays this number when you save the transaction.

- 3. Choose Enter.
- 4. Enter the required data for creating the interest rate instrument on the Structure tab.
- 5. In the Invest1100 Principal Increase for 100 Investment transaction type) and the (payment) amount in a specific currency. If the nominal amount and the payment amount are not the same, you can either enter the Nominal Amount or you enter the Payment Rate(%) and the system calculates the nominal amount. In the Rounding field, specify how amounts are rounded during cash flow calculation. You can choose between rounding up, rounding down, or arithmetic rounding.
- 6. In the Term area, you enter the Start date for the interest rate instrument. In addition, you see the area, enter the flow type (automatically derived from transaction type, such as Term Category. This field is predefined for the different product types.


For product types which have the term category Fixed-Term you can enter the End date of the financial transaction.

For product types with the term category At Notice, you cannot enter an End Date for the financial transaction. Therefore the Repayment area is also not available on the Structure tab.

Set the Inclusive area, enter the flow type (automatically derived from transaction type, such as indicator, to define whether the entered start and end date are included in the term of the financial transaction.

- 7. For the price-index-related product types, the Index Adjustment area is available. Here you choose the relevant price index, define the dates for the price index adjustment, and also determine how the price index factor is calculated and applied to the flows.


Choose the price index in the Index Name field.

Base Date

The financial transaction must be updated regularly with the price index starting from the base date. Prorata calculation is performed if the issue date or payment date differ from the base date. The value of the price index on this date is taken as the basis for calculating the proportion.

**Tip:**

Enter the term start date as the base date.

Index Interpolation (IdxInterpolate)

The index interpolation method defines how interpolation is executed. Interpolation is used in cases when the index key date falls between two index fixing dates. Possible values:

(space) Without Interpolation

The last price index value corresponding to the price index fixing low date is used.

LIN Linear Interpolation

EXP Exponential Interpolation

Price Index Application (PriceIdxApply)

The price index application method determines at which stage of (interest or repayment) amount calculation the price index factor is applied. With the standard interest formula "base amount * percentage rate * day fraction", the price index factor multiplies either the base amount (Price Index Applied on Base Amount) or the final index-clean amount, result of the formula above (Price Index Applied on Index-Clean Amount). The application method is relevant due to the various rounding stages within the amount calculation.

Reference Date for Index Adjustment (IdxRelDate)

The reference date for the index adjustment is the date that is used as the basis for determining the index adjustment date. You can choose between the following dates:

Calculation date

Due date

Period end

Calculation Date

End of the first price index period, usually equal to the Interest Calculation Date.

Select the Inclusive indicator, if needed. In the case of interpolation, the inclusive indicator is important for the calculation of days for interpolation. However, even if the price index value is not interpolated, the indicator is important. In this case, the indicator has the following effects:

If the indicator is selected, the calculation date receives the low price index value from the current period.

If the indicator is not selected, the calculation date receives the low price index value from the next period.

You can enter a workday shift rule.

Every

Enter the frequency for the price index adjustment by entering a number and choosing the frequency unit.

Example: 1 Months

IdxFixDateLow and IdxFixDateHigh

The index fixing date is the date of the index value used. The low index fixing date is the lower date used in the interpolation of the index factor between the two fixing dates.

Dates for reading the values of the price index in the market data table for interpolation. Basically, it is the day when the price index value is published.

Example:

For the price index IGPM and IPCA, the IdxFixDateLow is the first day of the month.

**Tip:**

If the price index value is not interpolated, it is sufficient to enter the low index fixing date. Make sure that the low index fixing date is before the calculation date.

Example: Determination of the price index value at calculation date of the flow

Assume the price index values are always entered on the first day of a month.

The interest period is the same as the price index calculation period.

Term start is 05/01/2021.

Term end is 07/01/2021.

Interest and the price index have a monthly frequency with the calculation date 06/01/2021.

Exponential interpolation is set for the price index adjustment condition.

Price index fixing date low is 04/01/2021.

Price fixing date high is 05/01/2021.

Price index base date is 05/01/2021.

The price index factor will be interpolated as follows:

For the flows within the first period between 05/01/2021 and 06/01/2021, using the price index values on

- 04/01/2021 and 05/01/2021

- For the flow with the calculation date 05/01/2021, using the value on 04/01/2021

- For the flow with the calculation date 06/01/2021, using the value on 05/01/2021


For the flows in between, using exponential interpolation. For example, for a flow with the calculation date

- 05/10/2021 with 10 days between 05/01/2021 and 05/10/2021, and 31 days for the whole interpolation period


- between 05/01/2021 and 06/01/2021.


For the flows within the next period between 06/01/2021 and 07/01/2021, using the price index values on

- 05/01/2021 and 06/01/2021.


- For the flow with the calculation date 06/01/2021, using the value on 05/01/2021.


- For the flow with the calculation date 07/01/2021, using the value on 06/01/2021.


For the flows in between, using exponential interpolation. For example, for a flow with the calculation date

- 06/20/2021 with t20 days between 06/01/2021 and 06/20/2021, and 30 days for the whole interpolation period


- between 06/01/2021 and 07/01/2021.


In this example, there are price index adjustments with the three price index fixing dates 04/01/2021, 05/01/2021, and 06/01/2021. Fixing dates are also determined for the base date of the price index.

**Note:**

After you have determined the variable interest value and the price index value for an interest flow or repayment flow, you see both the index-clean amount of the condition flow and the payment amount of the flow, which also includes the price index adjustment.

- 8. In the Interest Structure area, you enter the settings for the interests. Interest rate instruments allow fixed and variable forms of interest calculation to be entered and performed. Besides the possibility to enter the amount of interest, it is possible in addition, to enter Scaled (Interval) and Scaled (Incremental) interest conditions. See also: Scaled Conditions

- a. Enter the Interest Cat., the Int.Calc.Method, the Percentage Rate, and the Frequency. Depending on the chosen frequency different additional fields are available. In addition, you make the settings for work day shift of the calculation day and the due date. The relevant calendar can be entered on the condition detail screen. When you enter a wirking day shift, you can set in addition the Shift Due Date Back to End of Term indicator which is only relevant for the last flow at the period end. In addition, you can set the Capitalize Interest indicator. When the indicator ist marked, each interest flow is increases the base amount of the investment and will be considered within the following interest period. You can find a more detailed description of the methods in the F1-Help for the fields.
- b. Using the Condition button, you see the Condition Overview. Mark a condition item and choose Condition Details.


- 9. In the Repayment Structure area, you can choose between installment repayment and full repayment upon maturity (final repayment).

During the creation of the financial transaction, this area is not available for product types with term category At Notice. Only when the Give Notice function is executed for the financial transactions of this product type the area is visible.

In the case of final repayments, no further entries are necessary. The system automatically sets the interest period update to Final Repayment.

If you have opted for installment repayment, the structure of the screen is changed. Enter the repayment amount and the frequency. By default, the currency in the Currency field is the same as for the interest rate instrument. In this area, you can also use the pushbutton to expand or close the repayment structure.

- 10. In the Contract Conclusion area, you enter the following data:

Close Date: Date and Time of contract close, set by system with system date.

Trader: Set by system.

Contact Person: Here you could enter the name of the contact person at the company which is the business partner of the financial transaction. If you enter a name here, you must deploy separate supplementary organizational measures to ensure that you respect the deadlines governing the storage and deletion of personal data.

Notice Period: Enter the period of notice in days or months. The period of notice is the period between termination agreement and when it comes into effect.

- 11. Enter the required payment details on the Payment Details tab page as described in Payment Details.

- 12. Check if your settings lead to the flows you expect on the Cash Flow tab.
- 13. You can also branch to the entry screens for the general transaction management functions. You can use the tab pages to navigate between the different screens. For more information, see also Tabs. For information about creating a mirror transaction, see Intercompany Trading Process.


- 14. Save your entries. Flows are generated automatically when you create a financial transaction.

###### Scaled Conditions (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Interest Rate Instruments > Creating an Interest Rate Instrument > Scaled Conditions | L7 | trm05 p.54 | loio `03625256c3469e21e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/03625256c3469e21e10000000a44538d.html?locale=en-US)

**Concept**

A scaled condition is an pricing condition that changes based on the transaction amount. For example, a large loan might have a lower interest rate than a small loan.

There are two types of scaled conditions:

Scaled (Interval)

You define different scales for the balance amount by a lower limit amount, an upper limit amount, and a corresponding interest rate. Then the balance amount is divided into scales and the corresponding interest rate is applied for the amount interval of each scale.

Scaled (Incremental)

You define scales for the balance amount by a lower limit amount, an upper limit amount, and a corresponding interest rate. Then the balance amount falls into one scale and the corresponding interest rate is applied for the total balance amount.

**Example**

|Scale|Lower Limit|Upper Limit|Percentage Rate|
|---|---|---|---|
|1|EUR 0|EUR 100|5%|
|2|EUR 100|EUR 1000|6%|
|3|EUR 1000| |7%|


The system calculates as follows if the balance is EUR 1,200.00:

Scaled (Interval)

- 1. (Upper Limit Scale 1 - Lower Limit Scale 1) x Percentage Rate Scale 1: (100 - 0) x 0.05 = EUR 5
- 2. (Upper Limit Scale 2 - Lower Limit Scale 2) x Percentage Rate Scale 2: (1,000 - 100) x 0.06 = EUR 54
- 3. (Balance - Lower Limit Scale 3) x Percentage Rate Scale 3: (1,200 - 1,000) x 0.07 = EUR 14
- 4. Total Interest = EUR 5 + EUR 54 + EUR 14 = EUR 73


Scaled (Incremental)

- 1. The system determines the scale into which the balance falls.
- 2. Balance x Percentage Rate Scale 3: 1,200 x 0.07 = EUR 84

###### Processing Interest Rate Instruments

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Interest Rate Instruments > Processing Interest Rate Instruments | L6 | trm05 p.54 | loio `2407da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2407da531198434de10000000a174cb4.html?locale=en-US)

An interest rate instrument is a money market transaction with additional structural characteristics, such as Fixed, Variable, Scaled (Incremental), and Scaled (Interval) interest conditions.

Interest rate instruments with term category Fixed-Term have a repayment method (for example, final repayment, installment repayment, or annuity repayment).

Interest rate instruments with term category At Notice do not have term end dates. The repayment flow is generated only when the Give Notice function is executed.

To calculate the corresponding interest receivables or payables for variable interest conditions, you must make an interest rate adjustment. See Adjust Variable Rates/Prices.

**Procedure**

- 1. Open the Process MM Transactions - Collective Processing app on SAP Fiori launchpad. You can also use the app Manage Financial Transactions to process transactions.
- 2. Select the interest rate instruments to be processed.


From the worklist, select a transaction and choose one of the actions listed below.

|Function|Entries|Comment|
|---|---|---|
|Change|1. Choose Change. 2. The screen for changing basic data appears. 3. You can now overwrite the active entry fields or enter data in the empty fields. |You can use the tab pages and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are Flagged for Posting. Enter nominal amount changes during the contract term such as the following: You can also use this function, for example, to enter an early repayment/partial repayment with an adjusted interest rate that is aligned with your counterparty and that is applied to the early repayment amount/partial repayment amount. See also: Premature Repayment of IR Instrument |
|Copy **Note:** This function is available in the Manage Financial Transactions app (App ID: F6157) and Process MM Transactions -|1. Choose Copy. 2. The Copy or Change Data dialog box appears. 3. In the fields Company Code and Business Partner the values of the |You can create a new interest rate transaction by copying an existing transaction (of product category Interest Rate Instrument) in Contract or Contract Settlement activity.|


|Function|Entries|Comment|
|---|---|---|
|Collective Processing app (App ID: TM00).|copied financial transaction are displayed. You can now change the company code or the business partner and choose Continue or you continue the copy process without changing these values. 4. You see the data of the new financial transaction. The data correspond to the copied transaction. The entries for the Trade Repository, Rating, and SPPI Classification on the Administration tab are not copied. If you changed the company code or business partner in the step before, only the entries in the Invest, Term, Interest Structure, and Repayment Structure areas on Structure tab, the Additional Fields area and Authorization Group field on the Administration tab, the Other Flows tab, and Memos tab is copied. 5. Make the required changes. 6. Save the financial transaction. |This function enables you to fast-track the entry of a new financial transaction. See also: Create IR Instrument |
|Display|1. Choose Display. 2. The display screen for the structure characteristics appears. 3. The entry fields are not active. |You can use the tab pages to navigate between the various screens and display the other data relating to the transaction. You can branch to the master data for the business partner.|
|Settle|1. Choose Settle. 2. Choose the area from the menu for which you want to enter or change the settlement data. 3. When you save a settlement activity, the system changes the activity category of the transaction to record how it is monitored and processed in the back office area. 4. The contract can only be posted after it has been settled. |Using the Settle Interest Rate Instrument function, you can mark the transaction to document that the executed activity (such as creation of the contract, the rollover, or the termination) has also been processed in the back office. **Note:** Whether settlement is required or not depends on the processing category of a transaction type. For example, processing category 0002 is assigned for product type 55A and transaction type 100. This processing category also|


|Function|Entries|Comment|
|---|---|---|
| | |At this stage, the system checks the financial transaction data and adds any missing data. Also, when you save the transaction, the system fixes the transaction (actual records) and marks the transaction flows as Flagged for Posting. requires the settlement of activities.|
|Roll Over|1. Choose Roll Over. 2. Enter the amount and the flow type. This indicates whether an increased or decreased amount is involved. 3. Save your entries. |You can roll over a financial transaction with changed conditions and use the same transaction number. You can display the current business transaction along with its history and detailed information. With the memo book function, you can enter additional information for each activity. By choosing Extras Amount Overview  , you can see a list of all transactionrelated capital and interest flows sorted according to amounts that are due prior to/on the respective key date. When you roll over the transaction, you add a new activity to the transaction. The activity is processed in accordance with the determined transaction and position management process. You can change the end of term of a financial transaction until repayment. You have to make sure, however, that interest flows that have already been released, posted, or manually changed are not affected by shortening the term. You can make no further changes to the lent number of units or the nominal amount. The Capitalize Interest checkbox lets you choose whether to capitalize or pay out the interest on the term end date. The At Rollover field is available once you have settled the transaction and when you roll it over. Here you can choose the handling of interest on the rollover date. **Note:** A rollover is only possible for interest rate instruments with final repayment.|


|Function|Entries|Comment|
|---|---|---|
|Give Notice (for Deposits at Notice)|1. Choose Give Notice/Terminate. 2. Enter the date for the termination in the Notice field. The system checks for the earliest termination date. To do so, it checks the following: Existence of posted/reversed flows. Existence of modified flows. Should any of these flows exist, the earliest notice/termination date is updated to reflect the end of the calculation period for these flows. 3. Save your entries. |After you have entered a deposit at notice, it remains active until you terminate it using the Give Notice function. The transactions must have the activity category Contract Settlement. When you save the termination activity, the system creates the following flows: Final repayment flow Last nominal interest flow If you terminate a fixed interest rate transaction within an interest period the last interest flow is calculated from the start date of the last period until the termination date. If you terminate a variable interest rate transaction within an interest period and the interest rate fixing has already taken place, the last interest payment for the days from the start of the period until the termination date is calculated based on the fixed interest rate. If you terminate a variable interest rate transaction within an interest period and the interest rate fixing has not already taken place, you can fix the interest rate either before or after the termination. The date of both flows is the date entered in the Notice field of the financial transaction.|
|Terminate|1. Choose Give Notice/Terminate. 2. In the Notice field, enter the date for the termination. The system compares this date with the earliest possible termination date. To do this, the following is checked: Posted/reversed flows exist for the transaction.|You can terminate interest rate instrument transactions early before their maturity in alignment with your counterparty. The transactions must have the activity category Contract Settlement. When you save the termination activity, the system creates the following flows: Final repayment flow Last nominal interest flow|


|Function|Entries|Comment|
|---|---|---|
| |There are changed flows for the transaction. If any of these kinds of flows exist, the earliest termination date is updated and set to the end date of the calculation period of these flows. 3. Save your entries. The final repayment and the last interest payment takes place at the entered date. **Note:** If the early repayment amount requires an accrued interest rate that is aligned with your counterparty, all unpaid interest for the repayment amount must be recalculated with the accrued interest rate. For more information, see also Premature Repayment of IR Instrument. |If you terminate a fixed interest rate transaction within an interest period the last interest flow is calculated from the start date of the last period until the termination date. If you terminate a variable interest rate transaction within an interest period and the interest rate fixing has already taken place, the last interest payment for the days from the start of the period until the termination date is calculated based on the fixed interest rate. If you terminate a variable interest rate transaction within an interest period and the interest rate fixing has not already taken place, you can fix the interest rate for the current interest period either before or after the termination. The date of both flows is the date entered in the Notice field of the financial transaction.|
|Reverse|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. |When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to|


|Function|Entries|Comment|
|---|---|---|
| | |release the flows before you post or reverse them.|
|History|1. Choose History. 2. The system lists the activities that have been activated, reversed, or replaced by a follow-up activity. From this list, you can display the individual activities. You also see the status and the user who processed the transaction. |The history displays the sequence of previous activities related to a selected transaction.|


**Additional Functions**

You can display the business partner from the menu by choosing More Goto Display Partner .

You can set an editing indicator.

You can save in a local file from the menu by choosing More List Export Local File .

You can save your preferred layout settings as a variant.

**Related Information**

Interest Rate Instruments Create IR Instrument

###### Premature Repayment of IR Instrument

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Interest Rate Instruments > Processing Interest Rate Instruments > Premature Repayment of IR Instrument | L7 | trm05 p.60 | loio `f99b54a4ccd44f39965f341ae958de97` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f99b54a4ccd44f39965f341ae958de97.html?locale=en-US)

Premature repayment of an interest rate instrument with accrued interest rate.

**Key Feature**

With this function, you can process premature repayment of a transaction with product type 55A Interest Rate (IR) Instrument, when the transaction is terminated earlier than the end date that is predetermined in the contract. In this case, the accrued interest rate, which is aligned with your counter-party, is needed for the early repayment of this premature transaction. Based on the accrued interest rate, all the unpaid interests are recalculated.

**Note:**

Currently, this feature is only available for the product type 55A Interest Rate (IR) Instrument.

**Process**

1. Change the end date that is predetermined in the contract.

- a. Launch the app Process MM Transactions - Collective Processing from your SAP Fiori Launchpad.
- b. Select the interest rate instruments to be processed and choose Change.


- c. In the Change Interest Rate Instrument: Structure screen, change the end date under the Structure tab.


- 2. Maintain the accrued interest rate which is aligned with your counter-party.

- a. In the Change Interest Rate Instrument: Structure screen, choose Conditions in the menu bar
- b. In the Overview of Conditions screen, select the nominal interest condition type.
- c. Choose Create Accrued Int. Cond. in the drop-down list of the Create icon.
- d. In the Condition Details screen, enter the accrued interest rate as aligned with your counter-party in the Percentage Rate.


- 3. Insert early repayment for the new end date.


- a. In the Change Interest Rate Instrument: Structure screen, click the Other Changes in Cap. Struct. button.
- b. Enter the new flow type, payment amount and payment date.
- c. Choose Copy and then Save


**Note:**

During early repayment, all unpaid interest will be recalculated based on the accrued interest rate.

**Related Information**

Interest Rate Instruments Processing Interest Rate Instruments

###### Creating Accumulating Conditions (Interest Rate Instruments)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Interest Rate Instruments > Processing Interest Rate Instruments > Creating Accumulating Conditions (Interest Rate Instruments) | L7 | trm05 p.61 | loio `cb0f05495ea24d49a3db49b886a01583` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cb0f05495ea24d49a3db49b886a01583.html?locale=en-US)

Create an accumulating condition for a nominal, parallel or follow-up interest condition in order to accumulate multiple variable flows into one. This is needed, for example, when you have daily interest adjustments due to a variable interest rate but monthly interest payments. In this case, you can create an accumulating condition for the monthly interest payment.

**Background**

If you create an interest rate adjustment condition for a transaction in order to add variable cash flows to a nominal interest condition, you can add an accumulating condition in order to reduce the number of displayed cash flows. You can also accumulate parallel and follow-up conditions.

**Procedure**

Prerequisites

You have created a transaction with variable interest, based on a reference interest rate, consisting of a nominal interest condition with a specific interval, for example monthly, and an interest rate adjustment condition with a short interval, such as daily. You now see many daily interest flows. To accumulate these flows, proceed as follows:

- 1. In the Conditions view, select the row of the condition that you want to accumulate and choose  . In the dropdown that appears choose Create Accumulating Condition.
- 2. In the popup that appears, choose the accumulating condition type you want to add. The effective from date is selected automatically.


- 3. In the Condition Details view in the Calculation Date section, make sure the accumulating condition has the same interval as the nominal interest condition. In combination with the daily interest adjustment condition, you now have a nominal interest condition with daily variable flows that are accumulated on a monthly basis.
- 4. You can now leave the Condition Details view.


Result

To see the result, navigate to the cash flows for your transaction. Here instead of the daily interest flows, you now see a single accumulated flow. Only this accumulated flow is posting-relevant.

You can right-click the accumulated flow and choose Show Accumulation Details in the context menu to open a pop-up that shows all the single flows. You can also choose the button Show/Hide Single Flows to switch between the accumulated and nonaccumulated views.

**Related Information**

Conditions Overview

###### Cash Flow Transactions (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Cash Flow Transactions | L5 | trm05 p.62 | loio `ff07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ff07da531198434de10000000a174cb4.html?locale=en-US)

**Use**

With cash flow-based transactions you can manage transactions whose structural characteristics cannot be mapped by the standard product categories. You can enter and process transactions by entering their cash flow. A cash flow is a chronological sequence of flows: you enter the term alongside the cash flow that results from the transaction structure. This enables you to map your financial transactions flexibly.

**Integration**

On the basis of this, the system not only supports the processes for entering and processing these types of transactions in the trading area, but also the processes that build on these in the back office and accounting areas.

**Features**

For more detailed information, see

Create Cash Flow Transactions

Process Cash Flow Transactions

###### Processing Cash Flow Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Cash Flow Transactions > Processing Cash Flow Transactions | L6 | trm05 p.62 | loio `0208da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0208da531198434de10000000a174cb4.html?locale=en-US)

With cash flow-based transactions you can manage transactions whose structural characteristics cannot be mapped by the standard product categories. You can enter and process transactions by entering their cash flow. A cash flow is a chronological sequence of flows: you enter the term alongside the cash flow that results from the transaction structure. This enables you to map your financial transactions flexibly.

**Procedure**

- 1. Launch the app Process MM Transactions - Collective Processing from your SAP Fiori Launchpad.
- 2. Select the cash flow transactions to be processed.


From the worklist, you can select a transaction and perform one of the functions listed below.

|Function|Entries|Comment|
|---|---|---|
|Change|1. Choose Change. 2. The screen for changing basic data appears. 3. You can now overwrite the active entry fields or enter data in the empty fields. |You can use the tab pages to branch to the general transaction management screens and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are flagged for posting.|
|Display|1. Choose Display. 2. The display screen for the structure characteristics appears. 3. The entry fields are not active. |You can use the tab pages to navigate between the various screens and display the other data relating to the transaction. You can branch to the master data for the business partner.|
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. |


|Function|Entries|Comment|
|---|---|---|
| |release the flows before you post or reverse them.| |
|History|1. Choose History. 2. The system lists the activities that have been activated, reversed, or replaced by a follow-up activity. From this list, you can display the individual activities. You also see the status and the user who processed the transaction. |The history displays the sequence of previous activities related to a selected transaction.|
|Settle|1. Choose Settle. 2. The Contract Settlement screen appears. 3. Choose the area from the menu for which you want to enter or change the settlement data. 4. When you save a settlement activity, the system changes the activity category of the transaction in order to record how it is monitored and processed in the back office area. 5. The contract can only be posted after it has been settled. |Using the Settle Cash Flow Transaction function, you can mark the transaction to document that it has been processed in the back office. At this stage, the system checks the financial transaction data and adds any missing data. Also, when you save the transaction, the system fixes the transaction (actual records) and marks the transaction flows as Flagged for Posting. This function enables you to settle financial transactions that belong to the Contract activity. The flows for the purchase/sale of transactions with status Planned acquire the status Actual. The back-office area, like the trading area, enables you to call up information on existing transactions and make changes to them at a later date. You can monitor and check transaction activities with the settlement function. You can also add any missing data, such as payment instructions or posting details.|


**Additional Functions**

You can display the business partner from the menu by choosing More Goto Display Partner .

You can set an editing indicator.

You can save in a local file from the menu by choosing More List Export Local File .

You can save your preferred layout settings as a variant.

**Supported Device Types**

Desktop

**Related Information**

Create Cash Flow Transactions Cash Flow Transactions

###### Fiduciary Deposit

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Fiduciary Deposit | L5 | trm05 p.65 | loio `34d7d968dae743108b545f6363737466` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/34d7d968dae743108b545f6363737466.html?locale=en-US)

**Use**

TThe fiduciary deposit is a cash-flow-based instrument that is used in insurance (pension) business. There are two parties involved in the financial transaction:

Depositor

Fiduciary

IIn order to reconcile the premiums received from investors, the depositor must report assets in his balance sheet. To this end, they negotiate with the fiduciary entity and the fiduciary agrees to pay a fixed cash flow to the depositor every month. This tender consists of two parts:

Repayment

Interest flows

As a rule, the duration of fiduciary deposits is 30 years or more.

The lifecycle of the fiduciary deposit is as follows:

[figure TRM05-F011]

**Prerequisites**

To enter fiduciary deposits, you first need to make the required settings in Customizing for the Transaction Manager:

- 1. Define product types. The creation of financial transactions and management of positions in the Transaction Manager is based on product types.

The system provides the product category Fiduciary Deposit. You need to create the required product types for this product category in Customizing by choosing Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Money Market Transaction Management Product Types Define Product Types .

Select New Entries.

Assign the product type a key (for example, 57A)

Assign the product type a long text up to 30 characters and a short text no longer than 10 characters.

Product Category = 570 Fiduciary Deposit

Save your entries.

- 2. Define settings for transaction management.

Choose Money Market Transaction Management Transaction Types Define Transaction Types to create at least one transaction type for transaction category 100 FD Purchase.

- 3. Define flow types by choosing Money Market Transaction Management Flow Type Define Flow Type .


The following flow types are required for Fiduciary Deposits:

1300 Outflow for flow category Outflow (Fiduciary)

1310 Inflow for flow category Inflow (Fiduciary)

- 4. Assign the required flow types to each transaction type: Money Market Transaction Management Flow Type Assign Flow Type to Transaction Type . Assign all the flow types needed to process a transaction to Transaction Type 100 FD Purchase.
- 5. Define the relevant update types and assign them to the corresponding transaction types in the Update Types section. For example:


Flow type 1300 Outflow assigned to update type MM1300 Inflow (Fiduciary Deposit)

Flow type 1310 Inflow assigned to update type MM1310 Outflow (Fiduciary Deposit)

Flow type 1320 Withdrawal assigned to update type MM1320 Withdrawal (Fiduciary Deposit)

Flow type 1330 Extension assigned to update type MM1330 Extension (Fiduciary Deposit)

You must also define settings in Customizing for managing positions for Fiduciary Deposits:

- 1. Check that the Effects of the Update Types on the Position Components are already in place: Transaction Manager General Settings Accounting Settings for Position Management Set the Effects of the Update Types on the

Position Components

- 2. To integrate Fiduciary Deposits in position management, you need to define position management procedures. To do this, choose Transaction Manager General Settings Accounting Settings for Position Management Define Position Management Procedure .

You can use the following Position Management procedures or define your own procedures with reference to:

5200 – Valuation for Fiduciary Deposit

- 3. Assign the position management procedure to a position using Transaction Manager General Settings Accounting Settings for Position Management Assign Position Management Procedure .
- 4. Assign the update types required for valuation based on the position management procedure: Transaction Manager General Settings Accounting Valuation Class Transfer Update Types Assign Update Types for Valuation Class Transfer


**Activities**

Entering a Fiduciary Deposit

- 1. In the SAP area menu, open Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market Trading Create Financial Transaction (FTR_CREATE).
- 2. Choose the Company Code.
- 3. Choose the Product Type, for example, 57A Fiduciary Deposit.
- 4. Choose the Transaction Type, for example 100.
- 5. Choose the business Partner.
- 6. Choose the ID Number.
- 7. Choose the Financial Transaction. For Fiduciary Deposit, select 20 Fiduciary Deposit.


- 8. Click Enter and the Create Fiduciary Deposit: Structure screen is displayed.
- 9. You can enter the contract details:

By clicking on the Upload Cash Flows button and selecting your Excel file to upload.

By completing the following fields:

Flow Type

Payment Amount

Payment Date

- 10. Click on the Collateral tab and enter collateral bonds if required.
- 11. Complete the remaining tab pages as required.


**Note:**

The flows need to be saved in the correct format in Excel. The format is:

Flow Type, <Blank Cell>, Payment Amount, Payment Date.

**Example:**

|1310| |1000|27.12.2007|
|---|---|---|---|
|1300| |85|27.01.2008|
|1300| |85|27.02.2008|
|1300| |85|27.03.2008|
|1300| |85|27.04.2008|
|1300| |85|27.05.2008|
|1300| |85|27.06.2008|
|1300| |85|27.07.2008|
|1300| |85|27.08.2008|
|1300| |85|27.09.2008|
|1300| |85|27.10.2008|
|1300| |85|27.11.2008|
|1300| |85|27.12.2008|


Additional Functions

|Function|Entries|Remarks|
|---|---|---|
|Change|1. Choose Money Market Trading Edit Financial Transaction |You can change all transaction data before you settle the contract.|


| |2. Enter the Company Code and Transaction number. 3. Choose Change. 4. Make your changes and save your entries. |After settling the transaction, you should only use this function to correct errors in the following data. End of term Forward price Use the appropriate function from the list below.|
|---|---|---|
|Settle|1. Choose Money Market Trading Edit Financial Transaction  2. Enter the Company Code and Transaction number. 3. Choose Settle. 4. Check the transaction data. Save the transaction if all the data is correct. | |
|Reverse|1. Choose Money Market Trading Edit Financial Transaction  2. Enter the Company Code and Transaction number. 3. Choose Reversal. |See also: Reversal |
|History|1. Choose Money Market Trading Edit Financial Transaction  2. Enter the Company Code and Transaction number. 3. Choose History. |You can view all the actions performed on the Fiduciary Deposit.|
|Adjustment| |See Fiduciary Deposit: Deal Adjustment |
|Correction|1. Choose Money Market Trading Edit Financial Transaction  2. Enter the Company Code and Transaction number. 3. Choose Correction. 4. Enter the Correction Date. 5. Change the payment amount or payment date of the cash flows for the deal as required. 6. Save the changes. | |


**More Information**

For more information, see also:

NPV for Fiduciary Deposit

Posting

###### Fiduciary Deposit: Deal Adjustment

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Fiduciary Deposit > Fiduciary Deposit: Deal Adjustment | L6 | trm05 p.70 | loio `2d453f1c12434b7d99578c829f261fac` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2d453f1c12434b7d99578c829f261fac.html?locale=en-US)

**Use**

Deal adjustment in the Fiduciary Deposit means that there is a withdrawal or extension of the Fiduciary Deposit deal. During the withdrawal the user enters the withdrawal flows. The net amount represents the Final reimbursement amount. Deal extension is similar.

You can enter the withdrawal or extension flows in two ways:

In the cash flow table on the screen two new columns are added - one for the amount and one for the direction (extended or withdrawn).

Clicking on the Upload cash flows button to upload the extension/withdrawal flows from an Excel spreadsheet.

**Note:**

The flows need to be saved in the correct format in Excel. The format is:

Flow Type, Withdrawal Amount, Extension Amount, Date.

**Example:**

|1300|EUR|4|1|27.06.2008|
|---|---|---|---|---|
|1300|EUR|3.5|2|27.07.2008|
|1300|EUR|3|3|27.08.2008|
|1300|EUR|2.5|1|27.09.2008|
|1300|EUR|5|5|27.10.2008|
|1300|EUR| |6|27.11.2008|
|1300|EUR| |7|27.12.2008|


**Activities**

To make a deal adjustment to the Fiduciary Deposit:

- 1. Choose Money Market Trading Edit Financial Transaction
- 2. Enter the Company Code and Transaction number.
- 3. Choose Adjustment.
- 4. Enter the withdrawal and extension flows where required (or upload the flows from an Excel spreadsheet).


- 5. Save your entries.

###### Current Account-Style Instruments

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Current Account-Style Instruments | L5 | trm05 p.71 | loio `12283b567733a021e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/12283b567733a021e10000000a44538d.html?locale=en-US)

**Use**

Current account-style instruments are similar to interest rate instruments. The difference between the two kinds of instrument lies in that the current account-style instruments support negative nominals while the interest rate instruments do not, and that the current account-style instruments support final repayment only whereas interest rate instruments support installment repayment and annuity repayment in addition to final repayment.

**Prerequisites**

Before you can use the Money Market component, you have to maintain master data.

You have to create your business partners , assign the corresponding roles to these partners, and maintain the transaction authorizations.

You have to set up the standing instructions (correspondence, payment details) and release the business partner.

You also have to make the following settings in Customizing:

Define the product type. (If you do not want to use one of the standard product types delivered with the system, you can define your own product types). You create financial transactions and manage positions on the basis of product types. An example of a product type in the money market area is an Interest Rate Instrument.

Define the transaction type. Transaction types determine the type of transaction that can be concluded with a particular product type. They also control the transaction and position management process. Example: Investment or Borrowing transaction for an interest rate instrument.

Define the flow type. Flow types describe the various changes to the cash flows. Example: Increase in Nominal Amount

You must assign flow types to transaction types.

Define the condition type. This setting controls which structural characteristics are displayed when you create transactions. Example: Nominal Interest

For more information, see the relevant section in the Implementation Guide.

You can then define Money Market transactions in the system.

**Features**

To manage current account-style instruments, you can use the standard functions and processes for entering, editing, and processing transactions, managing their status, and transferring data to Financial Accounting.

**Related Information**

Create Current Acct-Style Instruments Processing Current Account-Style Instruments

###### Processing Current Account-Style Instruments

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Current Account-Style Instruments > Processing Current Account-Style Instruments | L6 | trm05 p.71 | loio `bcba4a5695e2404de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bcba4a5695e2404de10000000a4450e5.html?locale=en-US)

**Prerequisites**

See Current Account-Style Instruments.

**Procedure**

Choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market Trading/Back Office From here, you can access the following trading and back office functions through Create Financial Transaction and Edit Financial Transaction:

|Function|Entries|Comments|
|---|---|---|
|Create|See Creating Current Account-Style Instruments. | |
|Change|1. Choose Change. 2. The screen for changing basic data appears. 3. You can now overwrite the active entry fields or enter data in the empty fields. |You can branch to the general transaction management screens using the corresponding Tab Pages and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are Flagged for posting.|
|Display|1. Choose Display. 2. The screen for displaying the structural characteristics appears. 3. The entry fields are not active. |You can use the tab pages to navigate between the various screens and display the other transaction data. Choose to go to the master data for the business partner. |
|Roll Over|Choose Roll Over. The screen for entering the basic data for the rollover appears. If you want to change the amount invested or borrowed, enter the Amount and the Flow type in the corresponding fields in order to indicate whether you want to increase or decrease the amount for the rollover.|You can roll over a transaction and keep the same transaction number. By choosing Extras → Amount Overview, you view a list of all transaction-related capital and interest flows sorted according to amounts that are due prior to/on the respective key date. When you roll over a transaction, you add a new activity to the transaction. The activity is processed in accordance with the transaction and position management control settings.|
|Reverse|For information on reversing Money Market transactions, see Reversal.| |


|History|1. Choose History.|The history function allows you to|
|---|---|---|
| |2. The system lists the activities that are active, reversed or have been replaced by a follow-up activity.|trace the activity sequence so far for the transaction you have selected.|
| |From this list, you can branch to the| |
| |display for the individual activities.| |
| |You also see the status and the user| |
| |who processed the transaction.| |
|Settle|1. Choose Settle.|Using the Current Account-Style|
| |2. The screen for contract settlement appears.|Instrument function, you can flag the transaction to document that it has been processed in the back|
| |3. Choose the area from the menu for|office.|
| |which you want to enter or change the settlement data.|At this stage, you check the entries and add any missing data. When|
| |4. When you save a settlement activity, the system changes the activity category of the transaction to record how it is monitored and|you save the transaction, the system fixes the data (actual records) and flags the transaction flows for posting.|
| |processed in the back office area.|For more information, see|
| |5. The contract can only be posted|Settlement.|
| |after it has been settled.| |

###### Scaled Conditions (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Current Account-Style Instruments > Scaled Conditions | L6 | trm05 p.73 | loio `10964a5ff64746f0a7653afa42d6b6fc` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/10964a5ff64746f0a7653afa42d6b6fc.html?locale=en-US)

**Concept**

A scaled condition is an pricing condition that changes based on the transaction amount. For example, a large loan might have a lower interest rate than a small loan.

There are two types of scaled conditions:

Scaled (Interval)

You define different scales for the balance amount by a lower limit amount, an upper limit amount, and a corresponding interest rate. Then the balance amount is divided into scales and the corresponding interest rate is applied for the amount interval of each scale.

Scaled (Incremental)

You define scales for the balance amount by a lower limit amount, an upper limit amount, and a corresponding interest rate. Then the balance amount falls into one scale and the corresponding interest rate is applied for the total balance amount.

**Example**

|Scale|Lower Limit|Upper Limit|Percentage Rate|
|---|---|---|---|
|1|EUR 0|EUR 100|5%|


|Scale|Lower Limit|Upper Limit|Percentage Rate|
|---|---|---|---|
|2|EUR 100|EUR 1000|6%|
|3|EUR 1000| |7%|


The system calculates as follows if the balance is EUR 1,200.00:

Scaled (Interval)

- 1. (Upper Limit Scale 1 - Lower Limit Scale 1) x Percentage Rate Scale 1: (100 - 0) x 0.05 = EUR 5
- 2. (Upper Limit Scale 2 - Lower Limit Scale 2) x Percentage Rate Scale 2: (1,000 - 100) x 0.06 = EUR 54
- 3. (Balance - Lower Limit Scale 3) x Percentage Rate Scale 3: (1,200 - 1,000) x 0.07 = EUR 14
- 4. Total Interest = EUR 5 + EUR 54 + EUR 14 = EUR 73


Scaled (Incremental)

- 1. The system determines the scale into which the balance falls.
- 2. Balance x Percentage Rate Scale 3: 1,200 x 0.07 = EUR 84

###### Condition Groups

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Current Account-Style Instruments > Condition Groups | L6 | trm05 p.74 | loio `b0c34a5695e2404de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b0c34a5695e2404de10000000a4450e5.html?locale=en-US)

Generally, there are two types of condition groups: interest condition groups and repayment condition groups.

Interest Condition Group

You can create new condition groups or add follow-up conditions into one existing condition group.

Condition group allows functionality of parallel interest.

Within one condition group, a condition is effective from its Item eff. from date until the Item eff. from date of the next follow-up condition. You can create a follow-up condition by copying an existing condition and make changes.

If you use reference interest rate in a condition group, an interest rate adjustment condition which is valid for the whole condition group is generated automatically, in which you can maintain the interest rate adjustment dates.

For product category 550 (Interest Rate Instrument), condition category 15 (Interest Capitalization), 20 (Nominal

Interest), 21 (Interest Rate Adjustment), and 27 (Accrued Interest Rate) can be available in interest condition group. For product category 580 (Current Account-Style Instrument), condition category 15 (Interest Capitalization), 20 (Nominal Interest) and 21 (Interest Rate Adjustment) can be available in interest condition group.

Repayment Condition Group

Repayment condition group is automatically generated to distinguish condition category 12 (Final Repayment), 13 (Installment Repayment), and 14 (Annuity Repayment).

Follow-up conditions can be created for installment repayment condition and annuity repayment condition.

###### Partial Right Interest Calculation

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Current Account-Style Instruments > Partial Right Interest Calculation | L6 | trm05 p.74 | loio `b5ac14577396017ee10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b5ac14577396017ee10000000a441470.html?locale=en-US)

Concept

In the Money Market area, when you define a flow type, you can specify one type of interest calculation to a flow type. By partial right interest calculation, the inflow (SBERFIMA AA) or outflow (SBERFIMA SS) generate the partial right interest (SSTCKKZ 'O'). With the partial right interest calculation, interest of each nominal increase or decrease is calculated separately with the interest rate of the nominal change date.

**Example**

There were the following three nominal changes within the period from September 10, 2009 and March 10, 2009:

- 1. A nominal increase of 100 million on September 10, 2009
- 2. A nominal decrease of 50 million on November 9, 2009
- 3. A nominal increase of 50 million on December 15, 2009


The interest of each nominal increase or decrease was calculated with the respective interest rate of the nominal change date as below:

|No.|Date From|Date To|Nominal Change Amount|Interest Calculation Base|Interest Rate|Interest Amount|
|---|---|---|---|---|---|---|
|1|09/10/2009|03/10/2010|+100,000,000.00|100,000,000.00|1.98250%|996,756.94|
|2|11/09/2009|03/10/2010|-50,000,000.00|50,000,000.00|1.84063%|309,328.10|
|3|12/15/2009|03/10/2010|+50,000,000.00|50,000,000.00|1.75250%|206,892.36|


On March 10, 2009, the total interest generated within the period should be calculated by the following formula: 996,756.94 309,328.10 + 206,892.36 = 894,321.2

###### Facilities

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Facilities | L5 | trm05 p.75 | loio `9319c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9319c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

Facilities are agreements between a lender and a borrower, which control the general conditions for a series of drawings against a credit line. The lender can give drawing authorization to several people (= borrowers), who are entitled to draw varying amounts at any time up to the total approved credit line.

You can create the following two kinds of facilities:

Bilateral Facility

Syndicated Facility

Syndicated facilities may contain multiple lines of credit. You can structure the lines of credit, either as parallel or subordinate lines of credit.

The utilization of this credit option for a facility is called a Drawing.

Conditions

The lender calculates charges for the borrower (commitment interest). The incurred fees are calculated according to different methods (see Conditions (Facilities)).

Confirmed facilities

The lender guarantees the availability of a limited credit amount at any time. The borrower has to pay a charge for this.

Unconfirmed facilities

The lender does not guarantee a credit limit. No charges are made for this.

**Features**

The functions for managing facilities include the standard functions for entering and processing them.

You can assign fixed-term deposits, deposits at notice, cash flow transactions and interest rate instruments to a facility. You specify which money market transactions can be assigned as drawings on the Rules tab.

For an overview of the financial transactions that have already been assigned to the facility, see the Profiles tab.

For more information, see alsoProcessing Facilities and Creating Facilities.

**Prerequisites**

You also have to make the following settings in Customizing:

Define the Product Type (if you do not want to use one of the standard product types delivered with the system, you can define your own product types).

**Note:**

Here you also choose the facility category, which decides for the product type whether it is used for bilateral facilities or for syndicated facilities.

Define the Transaction Type . Transaction types determine the type of transactions that can be concluded with a particular product type. They also control the transaction and position management process. Example: Grant facility (lending) or Grant facility (borrowing).

Define the Flow Type. These describe the various changes to the cash flows. Example: Facility charges: Not utilized.

You must assign flow types to transaction types.

Define the Condition Type. This setting controls which charges you can enter when you create a transaction.


The charges for a facility are represented with certain condition types. You therefore have to define Amounts equivalent to similar interest. Examples:

Facility charges: Not utilized

Facility charges: Utilized

Facility charges: Overdrawn

Facility charges: Credit line

You have to assign the condition type to the transaction type.

Maintain master data:

You have to create your Business Partners, assign the corresponding roles to these partners and maintain the transaction authorizations.

You have to set up the Standing Instructions (correspondence, payment details) and release the business partner.

For syndicated facilities, you can make the required settings under Transaction Manager Debt Management Master Data Facility Process Line of Credit .

For more information, see also Credit Line Analysis.

**Related Information**

Create Facility Creating a Syndicated Facility Conditions (Facilities) Define Credit Lines - Syndicated Facilities

###### Creating a Bilateral Facility

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Facilities > Creating a Bilateral Facility | L6 | trm05 p.77 | loio `5d240dadc7d64684b5cf38ceff900dc2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5d240dadc7d64684b5cf38ceff900dc2.html?locale=en-US)

Find out how to create a bilateral facility transaction.

Facilities are agreements between a lender and a borrower, which control the general conditions for a series of drawings against a credit line. The lender can give drawing authorization to several people (= borrowers), who are entitled to draw varying amounts at any time up to the total approved credit line. The utilization of this credit option for a facility is called a drawing. The lender calculates charges for the borrower (commitment interest). The charges that incur are calculated according to different methods.

**Procedure**

- 1. There are several ways to create a facilities transaction:

- a. Choose Create in the Manage Financial Transactions app.
- b. Open the Create Facility app on SAP Fiori launchpad.
- c. Open the Create Financial Transaction app on SAP Fiori launchpad.


- 2. Enter the Company Code and the Product Type (56A).
- 3. Define the Transaction Type (assigned or obtained for a bilateral facility) and the Partner.
- 4. You can make the following entries in the Specifications section:

Currency: If you do not specify a currency when you create a financial transaction, the system automatically uses the currency of the company code.

Portfolio: If you want to assign the transaction to a portfolio, enter the portfolio. Alternatively, you can enter the portfolio on the Administration tab.

- 5. Choose Enter to go to the basic data screen for the transaction. You enter the actual transaction data on the Structure tab.
- 6. In the General Details area, you enter the start and end dates of the term.

The Inclusive option lets you choose whether to include the start or end date in the calculation. The Exceedance Term End option lets you choose whether transactions assigned to this facility are allowed to end after the facility's term end date.

- 7. On the Profiles tab in the Overview dropdown, choose Profile: Total Credit Line. Scroll down to the Credit Line section and choose Create to enter a credit line amount and a Valid From date.


**Note:**

If you have created fee conditions for this credit line, the Valid From date must be after the relevant Effective From date in the condition for this credit line.

- 8. Choose the Conditions button and enter any fee conditions on the Overview of Conditions page. For details on how to create conditions, see Conditions (Facilities).

- 9. On the Rules tab, you can narrow down the financial transactions that can be assigned to the facility as drawings.
- 10. To save the facility, choose Save.


Comments

You can settle a facility in the Manage Financial Transactions app. Simply select the transaction and choose Settle.

Once you have settled the facility and assigned drawing objects, the Profiles tab ( Overview List: Drawing Objects ) shows an overview of drawing objects assigned to this facility.

If the transaction currency of the assigned financial transaction is different from that of the facility, then the utilization of the credit line must be converted.

You assign the drawing objects to a facility during the creation of a financial transaction on the Administration tab in the Facility field. If the transaction assigned has a different currency from the facility, enter the rate from the currency ratio table in the Exchange Rate field.

The system checks if the drawing object fulfills the conditions defined in the facility. The system updates the timedependent utilization volume of the facility and also checks if utilization limits have been exceeded. The transactions are then assigned to the facility.


You can also jump to the relevant correspondence belonging to your facility by choosing the Correspondence button ( ) in the menu bar.

**Related Information**

Creating a Syndicated Facility Conditions (Facilities) Define Credit Lines - Syndicated Facilities

###### Creating a Syndicated Facility

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Facilities > Creating a Syndicated Facility | L6 | trm05 p.78 | loio `77b7f017a32e444da3fa81956cd093a7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/77b7f017a32e444da3fa81956cd093a7.html?locale=en-US)

Find out how to create a syndicated facility transaction.

**Procedure**

- 1. There are several ways to create a facilities transaction:

- a. Choose Create in the Manage Financial Transactions app.
- b. Open the Create Facility app on SAP Fiori launchpad.
- c. Open the Create Financial Transaction app on SAP Fiori launchpad.


- 2. Enter the Company Code and the Product Type (56B).
- 3. Define the Transaction Type (obtained) and the Partner.
- 4. You can make the following entries in the Specifications section:


Currency: If you do not specify a currency when you create a financial transaction, the system automatically uses the currency of the company code.

Portfolio: If you want to assign the transaction to a portfolio, enter the portfolio. Alternatively, you can enter the portfolio on the Administration tab.

- 5. Choose Enter to go to the basic data screen for the transaction. You enter the actual transaction data on the Structure tab.
- 6. In the General Details area, you enter the start and end dates of the term.

The Inclusive option lets you choose whether to include the start or end date in the calculation. The Exceedance Term End option lets you choose whether transactions assigned to this facility are allowed to end after the facility's term end date.

- 7. In the Syndication Partner table on the Structure tab, you can assign a rank to your syndication partners for this facility. This rank is for documentation purposes and indicates which task a partner carries out. You can configure the ranks in the configuration activity Define Partner Rank.
- 8. Use the Other Lines button in the General Details section on the Structure tab to define parent lines and sublines. The credit lines available here are defined in the app Define Credit Lines - Syndicated Facilities (TCL1).
- 9. On the Profiles tab in the Overview dropdown, choose Profile: Total Credit Line. Scroll down to the Credit Line section and choose Create to enter a credit line amount and a Valid From date.
- 10. You can define different credit lines in the Credit Line section on the Profiles tab. Choose the Syndication button to open a view where you can syndicate the total credit line amount between different partners.
- 11. Choose the Conditions button and enter any fee conditions on the Overview of Conditions page. For details on how to create conditions, see Conditions (Facilities).

- 12. On the Rules tab, you can narrow down the financial transactions that can be assigned to the facility as drawings.
- 13. To save the facility, choose Save.


**Note:**

If you have created fee conditions for this credit line, the Valid From date must be after the relevant Effective From date in the condition for this credit line.

Comments

You can settle a facility in the Manage Financial Transactions app. Simply select the transaction and choose Settle.

Once you have settled the facility and assigned drawing objects, the Profiles tab ( Overview List: Drawing Objects ) shows an overview of drawing objects assigned to this facility.

If the transaction currency of the assigned financial transaction is different from that of the facility, then the utilization of the credit line must be converted.

You assign the drawing objects to a facility during the creation of a financial transaction on the Administration tab in the Facility field. If the transaction assigned has a different currency from the facility, enter the rate from the currency ratio table in the Exchange Rate field.

The system checks if the drawing object fulfills the conditions defined in the facility. The system updates the timedependent utilization volume of the facility and also checks if utilization limits have been exceeded. The transactions are then assigned to the facility.


You can also jump to the relevant correspondence belonging to your facility by choosing the Correspondence button ( ) in the menu bar.

**Related Information**

Conditions (Facilities) Define Credit Lines - Syndicated Facilities

Creating a Bilateral Facility

###### Conditions (Facilities)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Facilities > Conditions (Facilities) | L6 | trm05 p.80 | loio `4607da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4607da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The lender charges fees from the borrower for the provision of a credit facility. You can configure the conditions for these fees in the Conditions section.

**Features**

Fees are calculated periodically for a facility once this facility has been settled and drawings have been made on it.

In addition to the predelivered condition types for fees, you can define more in the configuration activity Define Condition Types - Money Market.

To create a new condition, choose Create Create Fee Condition , enter the required data and save your entries.

**Note:**

A fee adjustment condition is created automatically, if you enter a reference interest rate in the nominal fee condition.

The field Fee Calculation in the configuration activity Define Product Types - MM Transactions lets you choose whether to include drawing objects assigned to partners in the calculation of the fee for a syndicated facility.

**Interest Adjustment Conditions**

For facilities, the relevant condition type for the nominal condition is the facility fee, which is based on condition category 24 (Amounts Equivalent to Interest). You define condition types in the configuration activity Define Condition Types - Money Market.

For syndicated facilities, you can assign different fee conditions to different credit lines. For this, use the Credit Line field in the Condition Details view.

The interest rate adjustment condition for facilities is based on condition category 21 (Interest Rate Adjustment). You do not need to create the adjustment condition manually. It is created automatically, if you add a reference interest rate to the nominal fee condition.

To see the flows generated by fee conditions, go the Cash Flow tab of the facility.

**Related Information**

Create Facility Creating a Syndicated Facility Conditions (Facilities) Define Credit Lines - Syndicated Facilities

**Scaled Conditions**

Concept

A scaled condition is an pricing condition that changes based on the transaction amount. For example, a large loan might have a lower interest rate than a small loan.

There are two types of scaled conditions:

Scaled (Interval)

You define different scales for the balance amount by a lower limit amount, an upper limit amount, and a corresponding interest rate. Then the balance amount is divided into scales and the corresponding interest rate is applied for the amount interval of each scale.

Scaled (Incremental)

You define scales for the balance amount by a lower limit amount, an upper limit amount, and a corresponding interest rate. Then the balance amount falls into one scale and the corresponding interest rate is applied for the total balance amount.

**Example**

|Scale|Lower Limit|Upper Limit|Percentage Rate|
|---|---|---|---|
|1|EUR 0|EUR 100|5%|
|2|EUR 100|EUR 1000|6%|
|3|EUR 1000| |7%|


The system calculates as follows if the balance is EUR 1,200.00:

Scaled (Interval)

- 1. (Upper Limit Scale 1 - Lower Limit Scale 1) x Percentage Rate Scale 1: (100 - 0) x 0.05 = EUR 5
- 2. (Upper Limit Scale 2 - Lower Limit Scale 2) x Percentage Rate Scale 2: (1,000 - 100) x 0.06 = EUR 54
- 3. (Balance - Lower Limit Scale 3) x Percentage Rate Scale 3: (1,200 - 1,000) x 0.07 = EUR 14
- 4. Total Interest = EUR 5 + EUR 54 + EUR 14 = EUR 73


Scaled (Incremental)

- 1. The system determines the scale into which the balance falls.
- 2. Balance x Percentage Rate Scale 3: 1,200 x 0.07 = EUR 84

###### Processing Facilities

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Facilities > Processing Facilities | L6 | trm05 p.81 | loio `9707da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9707da531198434de10000000a174cb4.html?locale=en-US)

**Prerequisites**

For information on the prerequisites, see Facilities .

**Procedure**

Choose Corporate Finance Management Transaction Manager Money Market Trading Facility. From here, you can perform the following trading functions:

|Function|Entries|Comments|
|---|---|---|
|Create|For information on creating facilities, see Creating Facilities . | |
|Change|1. Choose Change. 2. The screen for changing basic data appears. 3. You can now overwrite the active entry fields or enter data in the empty fields. |You can branch to the general transaction management screens using the corresponding tab pages and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are Flagged for posting.|
|Display|1. Choose Display. 2. The screen for displaying the structural characteristics appears. 3. The entry fields are not active. |You can use the tab pages to navigate between the various screens and display the other transaction data. Choose to go to the master data for the business partner. |
|Reverse|For information on reversing money market transactions, see Reversal .| |
|History|1. Choose History. 2. The system lists the activities that are active, reversed or have been replaced by a follow-up activity. From this list, you can branch to the display for the individual activities. You also see the status and the user who processed the transaction. |The history function allows you to trace the activity sequence so far for the transaction you have selected.|

###### Calculating and Updating the Effective Interest Rate

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Facilities > Calculating and Updating the Effective Interest Rate | L6 | trm05 p.82 | loio `f107da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f107da531198434de10000000a174cb4.html?locale=en-US)

**Features**

You use this function when you process transactions in the Money Market area to calculate the internal interest flows and update these to the database. You can use the effective interest for evaluations as past of reporting.

**Prerequisites**

To use this function, you have to define an effective interest method when you define the relevant product type in Customizing.

**Activities**

- 1. Choose Money Market Tools Calculate and Update Effective Interest.
- 2. You can generate a list of financial transactions with an unknown effective interest or using specific transaction numbers.
- 3. You can also choose whether to carry out a test run or an update run.
- 4. Choose Execute.
- 5. The system generates a calculation log.

###### Date Check

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Money Market Transactions > Facilities > Date Check | L6 | trm05 p.83 | loio `1e19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1e19c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

You use the Date check function to determine whether the requested due date falls on a working day. You can also check a transaction date against two calendars.

**Features**

Before you conclude a transaction, you can use the Date check function to check that a specific date (for example, a due date) is a working day for both business partners.

**Activities**

To use the Date check utility:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Money Market Trading Utilities Date Check .
- 2. In the calendar fields , enter your calendar ID (such as US for factory calendar US standard) and your business partner’s calendar ID (such as 01 for factory calendar Germany standard).
- 3. Under the Start of Term and End of Term , enter the transaction dates you want to have checked.
- 4. Confirm your entries.


Result

If the date you have entered is not a working day in your business partner’s calendar, or a due date or fixing date is on a weekend or a holiday, the system shows the previous working day and the next working day.

##### Derivatives (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives | L4 | trm05 p.83 | loio `c015da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c015da531198434de10000000a174cb4.html?locale=en-US)

**Purpose**

The Derivatives component covers OTC derivatives such as, forward rate agreements (FRAs), OTC options, swaps and caps/floors, and listed derivatives, such as listed options and futures. This process spans the whole trading process, starting from entering the financial transaction, processing it, and transferring the data to Financial Accounting.

**Integration**

Derivatives play an important role in interest and currency management. To manage risk, it is essential that you first analyze the current situation based on up-to-date market data. This requires an aggregated examination of underlying transactions and associated hedge transactions on a comparable basis. For derivatives, and options in particular, the results in the instruments are represented as delta equivalents. Consequently, the risk analysis and the decision-making process include only the volume of all the positions examined that is actually subject to market fluctuations. In addition to analyzing the exposure and the market values, you also need to take the special nature of derivatives into account when reviewing your liquidity situation. In contrast to the classical financial instruments, derivative instruments generate cash flows that have an element of uncertainty (either the amount is uncertain or the amount and the likelihood of occurrence are uncertain) in addition to fixed cash flows. In Market Risk Management, you can display and simulate these cash flows (variable payments of a swap, options). As derivatives are dependent on variable financial market values (such as reference interest rates), access to real-time datafeed, which provides up-to-the minute market price information, is an advantage. In the Trading area, an option price calculator helps you calculate prices.

**Features**

Trading

The trading area groups together the functions for entering derivatives transactions. It also enables you to also call up information about existing transactions or make changes at a later date. Collective processing functions are available to help you manage your foreign exchange transactions efficiently.

The product categories in the OTC Derivatives area are:

Interest Rate Derivatives

Swaps (product category 620)

Interest Rate Swaps

Cross-Currency Interest Rate Swaps

Discount Swap

Compound Swap

Overnight Index Swap (Obsolete)

Caps/Floors (product category 610)

Forward Rate Agreements (FRAs) (product category 630)

Total Return Swap (product category 640)

OTC Options (product category 760)

Currency option

Currency barrier option

Swaption

Interest rate guarantee (IRG)

Security options

Compound option

Average rate option

Basket option

Correlation option

Forward (product category 780)

Repurchase (Repo) transactions (product category 730)

Securities lending (product category 770)

Forward Securities Transactions (product category 740)

Forward Loan Purchases (product category 790)

The product categories in the Listed Derivatives area are:

Listed Options(product category 750)

Futures (product category 700)

Back Office

Once you have entered financial transactions in the trading area, you settle the transactions in the back-office area. The back office area also contains functions for checking and changing the transactions. The key aspects of postprocessing are:

Entering additional transaction data, in other words, adding information that is relevant for back-office processing

Preparing for posting and payment (for example, by checking the accounts used)

Generating correspondence in the form of internal or external confirmations.

Collective processing functions are also available in the back office. The back office also includes functions for netting transactions and for entering or editing references. For more information see, also Netting and Reference.

Accounting

Once you have entered the transactions in the Trading area and checked and completed them in the Back Office area, you then submit them to accounting. The Accounting area includes functions for transferring data to Financial Accounting, such as posting reports or position management postings. It also includes functions for parallel valuation.

**Treasury Analytics**

Apps

In the Treasury Reporting business group on the SAP Fiori launchpad, you find various apps that provide you with comprehensive information about the financial status and the current status of your credit lines as well as apps that you can use to analyze your financial transactions, treasury positions, and market data.

For the available reporting funtionality of the Transaction Manager in the back end system, see also Information System.

CDS Views

In addition to the reporting apps delivered, a broad range of CDS views have been provided. Using released CDS views as a basis, you can create your own query views. CDS query views can be used by any tool that supports CDS views, such as the Analysis for Microsoft Office, Design Studio, SAP Lumira, or SAP Analytics Cloud. For more information about CDS views, see also CDS Views. To get an overview of the CDS views released for Treasury and Risk Management, see also CDS Views for Treasury and Risk

Management.

Treasury Executive Dashboard in SAP Analytics Cloud application

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the back-end system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

For more information, see also Treasury Executive Dashboard Available in SAP Analytics Cloud.

###### Interest Rate Derivatives

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives | L5 | trm05 p.86 | loio `e1c4eeff59414870b29ef5e209577def` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e1c4eeff59414870b29ef5e209577def.html?locale=en-US)

**Use**

You can use (OTC) interest rate derivatives to control liquidity in your company and to recognize, analyze, and hedge against interest rate risks.

**Prerequisites**

Before using the transaction management functions, you have to enter master data.

You have to create your business partners, assign the corresponding roles to these partners, and maintain the transaction authorizations. To process financial transactions, you need to have defined the banks that are authorized as business partners in the system with the corresponding payment details.

You need to set up the standing instructions (correspondence, payment details) and release the business partner.

You also have to make the following settings in Customizing:

Define the product types. (If you do not want to use one of the standard product types delivered with the system, you can define your own product types). You create financial transactions and manage positions on the basis of product types. Discount FRA is one example of a product type.

Define the transaction type. The transaction type determines the types of transactions that can be concluded with a particular product type. It also controls the transaction and position management process. Example: Purchase

Define the flow type. Flow types describe the various changes to the cash flows. Example: Cash Settlement

You must assign the flow type to the transaction type.

Define the condition type. This setting controls which structural characteristics are displayed when transactions are created. Example: Interest Rate Adjustment.

For more information, see the relevant section in the Implementation Guide.

You can then define financial transactions in the system.

**Features**

The product categories for interest rate derivatives are:

Swaps (product category 620)

Interest Rate Swaps

Cross-Currency Interest Rate Swaps

Discount Swap

Compound Swap

Overnight Index Swap (Obsolete) (obsolete)

For the creation of swaps with risk-free interest reference rates, see the documentation of the condition details for interest conditions and the interest calculation tyes:

Condition Details: Interest (New FIMA)

Interest Calculation Types

Caps/Floors (product category 610)

Forward Rate Agreements (FRAs) (product category 630)

###### Swaps

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Swaps | L6 | trm05 p.87 | loio `2658c7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2658c7533a661d4be10000000a174cb4.html?locale=en-US)

**Use**

A swap is an exchange of payment flows over a fixed period. You define these payment flows when you conclude a swap. However, their absolute amount may depend on future events (such as variable interest payments, where the amounts depend on the level of reference interest rates in the future). With swaps, the interest rate flows are generated according to the interest rate condition.

You use swaps to perform liquidity control in your company and to recognize, analyze, and hedge against interest rate risks.

**Prerequisites**

Customizing

Define the product types. (If you do not want to use one of the standard product types delivered with the system, you can define your own product types). You create financial transactions and manage positions on the basis of product types.

You can choose Parallel Conditions in the Cash Flow Generation field for product types for product category 620 Swap.

However, regardless of this setting, all new swap transactions are created with parallel conditions (new FiMA). This means, you have the the same Condition Details: Interest (New FiMa) screen as interest rate instruments and securities. This includes interest calculation types, such as Exponential Interest Calculation with Factors, Compound Interest Calculation, and Average Compound Interest Calculation. So, you can enter variable interest conditions with risk-free reference rates. For more information, see also Interest Calculation Types.

In addition, parallel interest conditions are possible.

Define the transaction type. The transaction type determines the types of transactions that can be concluded with a particular product type. It also controls the transaction and position management process. Example: Purchase

Define the flow type. Flow types describe the various changes to the cash flows. Example: Cash Settlement

You must assign the flow type to the transaction type.

Define the condition types and assign them to your product types using the Customizing activities available in the Customizing of the Treasury and Risk Management under Transaction Manager OTC Derivatives Transaction Management Condition Types . You decide in the Field Selection for each condition type, which fields should be hidden, optional, required or only displayed for a condition of the condition type.

[figure TRM05-F022 - Examples for Field Selection of Interest Rate and Interest Rate Adjustment Condition Types]

Examples for Field Selection of Interest Rate and Interest Rate Adjustment Condition Types

**Tip:**

Flow types and update types for business transactions of nominal changes, for the interest flows and the net payments must be defined. Only the update types then decide whether the flows are relevant for posting. For net payments, the update types for the original flows are not relevant for posting.

|Flow Type|Direction|Update Type|
|---|---|---|
|1105 Nom.Amt Incr.(Not Rel.f.Postg)|Inflow|DE1105+ Increase in Nominal Amount (Not Rel. for Posting)|
|1105 Nom.Amt Incr.(Not Rel.f.Postg)|Outflow|DE1105- Reduction in Nominal Amount (Not Rel. for Posting)|
|1115 Nom.Amt Decr.(Not Rel.f.Postg)|Inflow|DE1115+ Increase in Nominal Amount (Not Rel. for Posting)|
|1115 Nom.Amt Decr.(Not Rel.f.Postg)|Outflow|DE1115- Reduction in Nominal Amount (Not Rel. for Posting)|
|1125 Contract (Not Rel.for Posting)|Inflow|DE1125+ Contract (Not Relevant for Posting)|
|1125 Contract (Not Rel.for Posting)|Outflow|DE1125- Contract (Not Relevant for Posting)|
|1135 Install. rep.(Not Rel.f.Postg)|Inflow|DE1135+ Instalment Repayment (Not Rel. for Posting)|
|1135 Install. rep.(Not Rel.f.Postg)|Outflow|DE1135- Instalment Repayment (Not Rel. for Posting)|


|Flow Type|Direction|Update Type|
|---|---|---|
|1145 Annuity Rep. (Not Rel.f.Postg)|Inflow|DE1145+ Annuity Repayment (Not Rel. for Posting)|
|1145 Annuity Rep. (Not Rel.f.Postg)|Outflow|DE1145- Annuity Repayment (Not Rel. for Posting)|
|1205 Interest (to be netted)|Inflow|DE1205+ Interest (to be netted) Not relevant for posting|
|1205 Interest (to be netted)|Outflow|DE1205- Interest (to be netted) Not relevant for posting|
|1250 Interest (net)|Inflow|DE1250+ Interest (net)|
|1250 Interest (net)|Outflow|DE1250- Interest (net)|
|1107 Cross Curr. Swap Payment (net)|Inflow|DE11107+ Cross Curr. Swap Payment (net)|
|1107 Cross Curr. Swap Payment (net)|Outflow|DE11107- Cross Curr. Swap Payment (net)|


Important Information: When you create, for example, a cross-currency interest rate swap with net payment, the posting-relevant flow types must be exchanged with flow types that aren’t relevant for posting (all the flow types ending with 5) in the conditions of the financial transaction.

For more information, see the relevant section in the Implementation Guide.

Before you can create an interest rate derivative, you have to enter master data.

Maintain your business partner. For more information, see also Business Partner.

Set up the standing instructions for payment details and derived flows in the master data of your counterparty and release the business partner. To process financial transactions, you need to have defined the banks that are authorized as business partners in the system with the corresponding payment details.

Creating Standing Instructions for Payment Details

Derived Flows

Used, for example, to enable net payments for interest rate swaps with this business partner.

Define derivation procedures in the Define Derivation Procedures and Rules Customizing activity and you must assign the derivation procedure in the standing instructions to your business partner, if you agreed on net payments.

Examples:

NTINT Swap: Net Interests

Netting of interest flows only

NTALL Swap: Net Int. and Nom.

Separate netting of interests and nominal changes

NTTOT Swap: Net All Flows

One net payment/posting of all flows together.

For the FX rate adjustments for net payments of the cross-currency interest rate swaps, define fixing references using the Define Fixing References app. These settings are needed to identify the leading and the following currency for the needed FX rates.

**Note:**

Flow types and update types for business transactions of nominal changes, for the interest flows and the net payments must be defined. Only the update types then decide whether the flows are relevant for posting. For net payments, the update types for the original flows are not relevant for posting.

|Flow Type|Direction|Update Type|
|---|---|---|
|1105 Nom.Amt Incr.(Not Rel.f.Postg)|Inflow|DE1105+ Increase in Nominal Amount (Not Rel. for Posting)|
|1105 Nom.Amt Incr.(Not Rel.f.Postg)|Outflow|DE1105- Reduction in Nominal Amount (Not Rel. for Posting)|
|1115 Nom.Amt Decr.(Not Rel.f.Postg)|Inflow|DE1115+ Increase in Nominal Amount (Not Rel. for Posting)|
|1115 Nom.Amt Decr.(Not Rel.f.Postg)|Outflow|DE1115- Reduction in Nominal Amount (Not Rel. for Posting)|
|1125 Contract (Not Rel.for Posting)|Inflow|DE1125+ Contract (Not Relevant for Posting)|
|1125 Contract (Not Rel.for Posting)|Outflow|DE1125- Contract (Not Relevant for Posting)|
|1135 Install. rep.(Not Rel.f.Postg)|Inflow|DE1135+ Instalment Repayment (Not Rel. for Posting)|
|1135 Install. rep.(Not Rel.f.Postg)|Outflow|DE1135- Instalment Repayment (Not Rel. for Posting)|
|1145 Annuity Rep. (Not Rel.f.Postg)|Inflow|DE1145+ Annuity Repayment (Not Rel. for Posting)|
|1145 Annuity Rep. (Not Rel.f.Postg)|Outflow|DE1145- Annuity Repayment (Not Rel. for Posting)|
|1205 Interest (to be netted)|Inflow|DE1205+ Interest (to be netted) Not relevant for posting|
|1205 Interest (to be netted)|Outflow|DE1205- Interest (to be netted) Not relevant for posting|
|1250 Interest (net)|Inflow|DE1250+ Interest (net)|
|1250 Interest (net)|Outflow|DE1250- Interest (net)|
|1107 Cross Curr. Swap Payment (net)|Inflow|DE11107+ Cross Curr. Swap Payment (net)|
|1107 Cross Curr. Swap Payment (net)|Outflow|DE11107- Cross Curr. Swap Payment (net)|


Important Information: When you create, for example, a cross-currency interest rate swap with net payment, the postingrelevant flow types must be exchanged with flow types that aren’t relevant for posting (all the flow types ending with 5) in the conditions of the financial transaction.

**Features**

Depending on the type of payment flows to be exchanged, a distinction is made between interest rate swaps and CrossCurrency Interest Rate Swaps.

The following kinds of repayment methods are available:

Final repayment

Installment repayment

Annuity repayment

You can settle interest rate swaps via net payments. The netting flow is generated as derived flow and the original flows aren’t posting relevant (all the flow types ending with 5). In general, all flow types are posting relevant but the final decision on the posting relevancy is defined in the update types. You use the flow types/update types, which are posting relevant for cross-currency interest rate swaps without net payment and the flow types/update types that aren’t relevant for posting cross-currency interest rate swaps without net payments. Derivation procedures are predefined and need to be assigned to the Derived Flows of your business partners.

You can settle cross-currency interest rate swaps in one currency, including adjustment of the FX rates. Cross-currency interest rate swaps have two currencies, one for outgoing and one for incoming interests. In order to allow netting of flows in different currencies, it’s necessary to convert the amounts in one joint currency. System uses the settlement currency as the currency of the net payments. The flows are calculated in the position currency and then translated to the payment currency, which is the settlement currency. The net payments are created in settlement currency.

The original flows of the outgoing and incoming side, such as the flows representing nominal changes and the condition-based flows (for example interests and repayments) have an amount in position currency and an amount in payment currency.

The derived flows only have an amount in payment currency.

For the currency translation, you must determine an FX rate using the Create Adjustments - Rates/Prices app for the FX rate adjustments.

The Run Accrual/Deferral app allows grouping and netting of original flows with different directions and update types

Grouping and netting of original flows with different directions and update types.

Grouping in payment currency allows grouping of accruals with same settlement currency.

Prorated amount in position currency is translated to payment currency and grouped with other accruals in the same payment currency

For more information, see also Accrual/Deferral of Expenses and Revenues

You also have the option of displaying the discounted interest amounts. The discounting option can be used for both interest rate swaps and currency swaps.

For more information, see also Discount Swap.

In addition, you can create a Compound Swap . In the case of a compound swap, the interest is capitalized and paid out during and / or at the end of the term. Another available feature is the Eonia Swap, a special type of compound swap.

The flexible condition structure also enables you to map the most common swaps:

Example:

Mapping an Amortizing Swap, in other words, a swap where the nominal amount can be reduced any number of times during the term. To do this, you can use the Create nominal changes pushbutton to enter any changes during the term. This enables you to represent repayment schedules.


**Process**

- 1. Create IR Derivatives

- 2. Settle the interest rate swap using Process IR Derivatives - Collective Processing app.

- 3. During the lifecycle of the financial transaction the following functions need to be executed on a regular base:

Period-end closing:

Run Valuation

Execute Accrual/Deferral

Adjust Variable Rates/Prices

Fix, Pay and Post Flows

- 4. Use Process IR Derivatives - Collective Processing to execute the following functions if needed:

Terminate the swap

Reverse

Change

Display

- 5. The process is finished with the posting of the last repayment flow.


**Related Information**

Create IR Derivatives

###### Interest Rate Swaps

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Swaps > Interest Rate Swaps | L7 | trm05 p.92 | loio `1c15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1c15da531198434de10000000a174cb4.html?locale=en-US)

Interest rate swaps are transactions that exchange payment flows on the basis of different interest rates in the same currency. You agree on a certain term, usually over a year. An interest rate swap enables you to hedge possible interest rate risks.

Possible combinations of interest rate swaps are:

Payer

Outgoing interest payments are fixed - incoming interest payments are variable

Receiver

Incoming interest payments are fixed - outgoing interest payments are variable

Basis

Variable against variable interest payments

Fix to fix

Fixed against fixed interest payments

You can display the two cash flows for an interest rate swap either together or separately. This provides you with an overview of the incoming and outgoing payments. For swaps with a variable interest rate calculation, manual or automatic interest rate adjustments are carried out over the course of the term and the cash flow is gradually filled with the current values.

**Example:**

A company finances an existing investment with a fixed interest loan at 6.5%. The company treasurer expects falling interest rates and, therefore, agrees an interest rate swap with a bank. From this interest rate swap, the company receives a fixed interest yield of 7.25% and pays a variable rate of 6-M-EURIBOR.

The company, therefore, has the following interest rate costs:

Interest expenditure of 6.5% and 6-M-EURIBOR

Interest yield from SWAP of 7.25%

This results in interest expenditure of 6M-EURIBOR - 0.75%

###### Cross-Currency Interest Rate Swaps

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Swaps > Cross-Currency Interest Rate Swaps | L7 | trm05 p.93 | loio `1f15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1f15da531198434de10000000a174cb4.html?locale=en-US)

A currency swap is an exchange of payment flows comprising interest payments and capital payments in different currencies at an agreed exchange rate. You can use currency swaps to hedge possible currency risks. They also allow you cheaper access to the respective foreign currency markets.

In a currency swap, you exchange fixed and variable interest rates in any combination against each other. Possible combinations are:

Payer

Outgoing interest payments are fixed - incoming interest payments are variable

Receiver

Incoming interest payments are fixed - outgoing interest payments are variable

Basis

Variable against variable interest payments

Fix to fix

Fixed against fixed interest payments

Although it is not absolutely necessary to swap the nominal amounts at the start of the transaction, this provides a basis for calculating the respective interest amounts. The original amount can be swapped back again upon maturity at the original exchange rate. The necessary periodic adjustments of the reference interest rate are made either manually or automatically via a separate entry.

**Related Information**

Swaps Create IR Derivatives Process IR Derivatives - Collective Processing

###### Discount Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Swaps > Discount Swap | L7 | trm05 p.94 | loio `b215da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b215da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A discount swap differs from a standard swap in the way the interest amounts are calculated.

When you conclude a discount swap, the interest is due at the start of the interest period, and the interest amount is discounted to this date. The interest rate used for the interest calculation is also used as the discount rate.

**Use**

The discounting option can be used for both interest rate swaps and currency swaps.

Like the discount FRA, this swap variant is mainly used in Australia.

**Prerequisites**

You define the discount swap in the IMG activity Define Product Types using the product category "Swap". Set the Discount Swap indicator to have the interest calculated differently.


For more information on the interest calculation, see the F1 input help for the Discount Swap field.

In addition, you must assign a condition type in class "1" with the condition category "22 Discounting" to the transaction type you use.

See also: Swaps and Processing OTC Interest Rate Instruments .

###### Compound Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Swaps > Compound Swap | L7 | trm05 p.94 | loio `4615da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4615da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

In the case of a compound swap, the interest is capitalized and paid out during and / or at the end of the term. Whether or not the nominal amounts are swapped in the process is of no significance.

**Prerequisites**

As is the case with all swaps, the interest rate flows for a compound swap are generated according to the interest rate conditions.


In order to create a compound interest effect, you must select an interest rate condition with condition category 15 (interest capitalization) in Customizing.

The interest payment is entered as an independent time sequence. A flow is generated for each capitalized interest payment to pay the interest accrued to date, irrespective of whether this interest was already added to the nominal amount or not. Interest payment dates should therefore always coincide with interest capitalization dates.

**Structure**

Creating a compound swap

- As soon as you select an interest rate condition with condition category 15 (interest capitalization) – either by presetting the data or by choosing the condition from the detail view – the pushbutton Condition Details ) appears on the tab page.


You can use this to enter a time sequence for paying capitalized interest. You should ensure, however, that the payment dates always coincide with the interest capitalization dates. Otherwise, this will affect the nominal capital, as due interest amounts will be paid that have not been capitalized. When you save your entries, the data is checked by the system. A warning message appears if inconsistencies are found.


Another available feature is the Eonia Swap , a special type of compound swap.

###### Overnight Index Swap (Obsolete)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Swaps > Overnight Index Swap (Obsolete) | L7 | trm05 p.95 | loio `c315da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c315da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The overnight index swap is a special form of the compound swap.

**Example:**

EONIA Swap (EUR)

Federal Fund Rate Swap (USD)

In an Overnight Index Swap, a fixed interest rate is swapped for a variable one. This is based on the call money fixing of the overnight index (for example, EONIA (= EURO OverNight Index Average), Federal Fund Rate).

The overnight index swap has the following properties:

On the variable side, interest rate adjustment takes place daily, where the weekend is calculated on the same base amount and at the same interest rate as the friday payment. The interest calculated linearly is capitalized and the variable interest is not paid daily but periodically, for eyample, every 6 months (for a Federal Fund Rate swap) or every 12 months (for an EONIA swap).

However, a swap can be terminated prematurely.

Calculation of interest to be paid periodically is based on an average interest rate rounded to the number of decimal places set. This results at runtime in a difference to the exact calculation method.

[figure TRM05-F027 - Average Interest Calculation Formula]

Average Interest Calculation Formula

where:

|rf|Overnight index interest rate to be calculated|
|---|---|
|t0|Start date of the overnight index swap|
|tn|End date of the overnight index swap|
|ri|Cash call fixing at time i|


|di|Days validity for ri, normally = 1, on weekends = 3)|
|---|---|
|n|Total number of days|


The interest calculation method underlying the interest rates is the Euromethod (actual/360).

The rhythm of payments of the fixed side is the same as that of the variable side, that is, payment is periodic.

Only the difference amount flows between the fixed and variable sides on the periodic due dates.

**Integration**

For the overnight index swap, you can calculate the cash value on a particular due date by using the Market Risk Analyzer. For more information, see the price calculator information for the Overnight Index Swap.

**Activities**

You create the overnight index swap in the same way as you create a compound swap. Additionally, you must make the following settings for the term details:

Interest Term Details

Term Type: Interest Capitalization

(that is, a term type with term category Interest Capitalization)

Interest Method: act/360

Type of Interest Calculation: Linear Tax Calculation

Update

Rule: Adjusted

Frequency: 1Calendar Day

Days +/-: 1-

Due Date

Maturity: 2nd day of runtime

Working Day: Following working day

Interest Payment Terms Details

Term Type: Payment of Capitalized Interest Term Type with term category Payment of Capitalized Interest

Update

Rule: Regular

Frequency: For example, 12 (EONIA swap) or 6 (Federal Fund Rate swap) Months

Days +/-: 1-

Due Date

Maturity: 1st day of runtime

Working Day: No Shift

Valuation

Calculation Type: With Average Interest Rate

Rounding Unit: 0.0001000 (4 decimal places, relevant for the EONIA swap) or 0.0000100 (5 decimal places, relevant for the Federal Fund Rate swap)

Rounding: Commercial Rounding

Interest Rate Adjustment Term

Standard Setting

###### Caps/Floors

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Caps/Floors | L6 | trm05 p.97 | loio `db15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/db15da531198434de10000000a174cb4.html?locale=en-US)

**Use**

A cap or floor is a series of interest rate options that are exercised when the option exceeds or falls short of a certain interest rate level. Caps and floors provide you with a type of interest insurance.

**Features**

Cap:

The buyer of a cap wants to hedge against rising interest rates. He/she agrees on an upper interest rate limit with the seller and pays a premium for this. If the reference interest rate rises above this agreed upper limit, the seller reimburses the difference to the buyer of the cap. If the agreed reference interest rate is not reached, there is no settlement payment.

Floor:

A floor is traded in the same way. The buyer of a floor wants to protect against sinking interest rates and agrees upon a lower limit with the seller. The buyer pays a premium for this. He/she receives a settlement payment if the interest rate falls below this agreed lower limit.

[figure TRM05-F028]

**Activities**

1. On the initial screen, enter the following basic data for the transaction:

Company code

Product type

Transaction type

Business partner

- 1. In the Activity area, decide whether you want the transaction to be created as a Contract or an Order.
- 2. If you work with external number assignment, you must enter a key in the corresponding field in the transaction so that it can be uniquely identified within a company code. Otherwise, the system assigns the number automatically and displays this number when you save the transaction.
- 3. Choose Enter to go to the basic data screen for the transaction. On the Structure tab page enter the actual transaction data for the cap/floor.
- 4. A dialog box can appear here if you assigned several flow types to one flow category in Customizing.


**Example:**

Possible flow types for the premium of a cap: relevant for accrual/deferral or not relevant for accrual/deferral.

1. The fields listed below are either required or optional fields:

Term

Strike

Upper limit for cap / lower limit for floor

Nominal amount and currency

Choose the pushbutton to create nominal amount increases or decreases in the term. Repayment structures are created by means of nominal amount reductions. After you have changed the nominal amounts, the Create Nominal Changes pushbutton changes.


Due date

Reference interest rate

- At the scheduled interest rate adjustment, you can either enter the reference interest rate manually or let the system read the data to calculate any interest receivable that is due.


Interest calculation method

Frequency of interest rate adjustment

Premium

On the Condition Details: Option Premium screen, you can generate several premium payments by entering a frequency.

The premium of a cap/floor can be accrued/deferred in the accounting area. In order to do this, however, you need to have made certain Customizing settings (for example, indicate the flow type as relevant for accrual/deferral). To calculate the accrual/deferral period, you have to enter an interest calculation method in the detail view.

- 1. For more detailed information on the pushbuttons (interest, interest rate adjustment and option premium), see Condition Details.
- 2. To settle a cap/floor prematurely, you can use the Notice function. You have the option of giving notice for a future date. Interest rate adjustment dates that lie before the date of notice but after the contract conclusion date, do not change. The final repayment is due on the date of notice.
- 3. You can specify in Customizing whether you want the name of the trader to be displayed automatically. You can also enter additional information, such as the business partner or a reference for the business partner.
- 4. You can branch to the entry screens for the general transaction management functions. You can use the tab pages to navigate between the different screens.


**Note:**

For more information, see Tab Pages.

- 1. Additional functions are available when you choose Extras and Environment from the menu.
- 2. You can specify in Customizing whether you want the name of the trader to be displayed automatically. You can also enter additional information, such as the business partner or a reference for the business partner.


- 3. To save the basic data, choose Cap/Floor Save .


- 4. For a general explanation of the terms, see Basic Data.

###### Forward Rate Agreements (FRAs)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Interest Rate Derivatives > Forward Rate Agreements (FRAs) | L6 | trm05 p.100 | loio `f515da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f515da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use forward rate agreements to specify a fixed interest rate today for a period in the future.

Buyers of FRAs cover themselves against rising interest rates, while sellers of FRAs cover themselves against falling interest rates.

**Example:**

In 6 months time you will receive 1 million euros, which you want to invest as 3-month money. Since you are currently expecting the interest rates to fall, you arrange a FRA for 1 million euros with your bank today with a starting date in 6 months for a term of 3 months. The agreed interest rate is 5%.

If, for example, the reference interest rate on the fixing date is 4.5%, the bank has to make a settlement payment to you. If the interest rate on the fixing date is above the agreed interest rate of 5%, you have to pay the difference.

[figure TRM05-F031]

**Features**

On the day the interest rate is fixed, the system calculates the settlement payment automatically on the basis of the difference between the agreed interest rate and the reference interest rate. This amount is displayed as an incoming or outgoing payment in the cash flow.

When you define the product type in Customizing, you can create a discount FRA as well as the standard FRA. The two FRAs differ in the way in which the settlement payment is calculated.

Calculating the settlement payment for the standard FRA:

The reference interest rate is fixed on the fixing date

The interest amount is calculated automatically on the basis of the difference between the FRA rate and the reference interest rate

The interest amount is discounted automatically using the reference interest rate at the start of the hedge period

The settlement payment is displayed as the incoming or outgoing payment in the cash flow.

Calculating the settlement payment for the discount FRA:

The reference interest rate is fixed on the fixing date

The interest amount is calculated automatically both on the basis of the FRA rate and the reference interest rate

The interest amount is discounted automatically at the start of the hedge period each time with the interest rate used for calculating the interest amount

The settlement payment is calculated as the difference between the discount amounts and displayed as an incoming or outgoing payment.

**Activities**

- 1. On the initial screen, enter the following basic data for the transaction:

Company code

Product type

Transaction type

Current transaction activity (order or contract)

Business partner

- 2. Choose Enter to go to the basic data screen for the transaction. On the Structure tab page, enter the actual transaction data for the FRA.
- 3. Enter transaction data in the fields described below: The values in parentheses relate to the example given above.


- a. Term area:

Start of lead time (0 - today)

Start of hedge period (++6)

End of hedge period (++9)

- b. Interest structure area:


Base amount (1m euro = 1,000,000.00 euro)

Interest rate (5.0 - the interest rate reflects the forward yield curve)

Reference interest rate (LIB_6)

Interest calculation method (act/360)

Fixing (2-)

A "6 on 9" FRA has a contract period of 3 months with the start of term in 6 months. At this point in time, the contract is settled and paid out.

- c. Business calendar area:


Here, you enter the relevant business calendar for moving the date to a working day (such as USA).

- a. You can specify in Customizing whether you want the name of the trader to be displayed automatically. You can also enter additional information, such as the business partner or a reference for the business partner.
- b. You can branch to the entry screens for general transaction management functions. You can use the following tab pages to navigate between the different screens.


**Note:**

For more information, see Tabs.

- 4. To use additional functions, choose Extras and Environment from the menu.
- 5. To save the basic data, choose FRA Save .



For more information about options on FRAs, see Interest Rate Guarantee (IRG).

**Related Information**

Basic Data - Derivatives

###### OTC Options

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options | L5 | trm05 p.102 | loio `3115da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3115da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use options to perform liquidity control in your company and to recognize, analyze, and hedge FX risks.

The purchaser of a standard currency option, which is also known as a forex option, has the right to buy a fixed amount of currency on the exercise date at a previously agreed rate. The option purchaser pays a premium for this right. The amount of the premium paid varies depending on supply and demand in the foreign exchange market. Currency options are asymmetrical hedging instruments. This means that rights and obligations are unevenly distributed between the buyers and sellers. Unlike listed instruments, these options are traded directly between business partners with user-defined structure characteristics. The main difference with forward exchange transactions is that the buyer of an option has the right but not the obligation to buy or sell a certain currency amount.

Features

|OTC options:|Related underlying:|
|---|---|
|Standard options:| |


|OTC options:|Related underlying:|
|---|---|
|Currency Option|Spot Exchange Transaction|
|Exotic options:| |
|Currency Barrier Option|Spot Exchange Transaction with Additional Barrier|
|Swaption|Swap|
|Interest Rate Guarantee (IRG)|FRA|
|Bond Option|Security (created as a class)|
|Compound Option|Currency Option|


**Prerequisites**

Master Data

Create your business partners, assign the corresponding roles to them, and maintain the transaction authorizations. To enable financial transactions to be processed, you need to have defined the banks as authorized as business partners in the system with the corresponding payment details.

Set up the standing instructions (correspondence, payment details) and release the business partner.

Customizing

Define the product types. You can use one of the standard product types delivered with the system or you can define your own product types. You create financial transactions and manage positions on the basis of product types. Foreign exchange is one example of a product type.

You can also incorporate the related underlying transactions when you define product types. A spot exchange transaction, for example, is defined as an underlying in currency options. As a rule, underlying transactions are generated automatically upon physical exercise.

Since the underlying transaction is split into two transactions, you can enter alternative payment methods for the option.

Define the transaction types. Transaction types determine the type of transactions that can be concluded with a particular product type. They also control the transaction and position management process. You can also define how the spot rate is determined during the physical exercise of an OTC option. Purchase is one example of an OTC option.

Definition of flow types: These describe the various changes to the cash flows. Sell foreign exchange is one example of a flow type.

You must assign flow types to transaction types.

You can define which administration fields are transferred from an OTC option to the corresponding exercise transaction. To do so, use the following Customizing activity under Treasury and Risk Management Transaction Manager OTC Derivatives Transaction Management Transfer Administration Fields to Exercise Transaction

.


For more information, see the documentation in Customizing for Treasury and Risk Management.

**Related Information**

Reference

###### Creating an FX Option (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > FX Option > Creating an FX Option | L7 | trm05 p.104 | loio `1f75f42cf5244080bb1dbef2ee014837` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1f75f42cf5244080bb1dbef2ee014837.html?locale=en-US)

**Context**

The FX option is an option on a spot exchange transaction and is used as protection from currency fluctuations. The purchaser of a standard FX option, also known as an OTC (over the counter) option, has the right to buy a fixed amount of currency on the exercise date at a previously agreed rate. The option purchaser pays a premium for this right. The amount of the premium paid varies depending on supply and demand in the foreign exchange market. FX options are asymmetrical hedging instruments - this means that rights and obligations are unevenly distributed between the buyers and sellers. Unlike listed instruments, these options are traded directly between business partners with user-defined structure characteristics. The main difference with forward exchange transactions is that the buyer of an option has the right but not the obligation to buy or sell a certain currency amount.

**Procedure**

- 1. Open the Create Financial Transaction app or the Create OTC Option app on SAP Fiori launchpad.


- 2. Enter the company code, product type (such as 76A), transaction type (100 (Buy) or 200 (Sell), and the business partner. When you create a currency option, you are documenting the intention to buy or sell a currency option.
- 3. If you want to assign the transaction to a portfolio, enter a portfolio in the Limits area. Alternatively, you can enter a portfolio on the Administration tab in the Position Assignment area.
- 4. In the Activity area, choose whether you want to create the transaction as a contract or as an order.
- 5. Choose Enter to branch to the basic data screen for the option. On the Structure tab, you enter the actual transaction data for the purchase or sale.
- 6. Enter the expiry date and expiry time for the option.

The Expiry Time field is available for input only if you have assigned predefined location codes to specific times using the Define Values for Expiry Time app.

- 7. Select the exercise type (European or American) and the settlement type (Cash Settlement, Physical Exercise, Not Yet Specified).
- 8. Enter the currency pair and the strike.
- 9. Specify whether the option is a put or a call.
- 10. Enter the traded currency and the traded amount. Note: The offsetting amount is calculated by the system.
- 11. Enter the value date: This is the payment date on which the option is exercised (generally, two working days after the exercise date).
- 12. You can define the current spot rate as a spot reference in the transaction data.
- 13. The Option area contains the following fields:

Strike Price: As well as the currency keys, you also need to enter the traded amount and a rate fixed in advance (the strike price).

Value Date

- 14. In the Premium area, specify the following for the option premium:

- a. Select the premium notation (Points or Percent).
- b. Enter the points or percentage.
- c. Select the desired flow type.
- d. Select the payment date for the premium.
- e. Choose the currency in which the premium is to be paid. If this currency is one of the currencies in the currency pair for the option, the system calculates the amount automatically when you enter the percentage or points.


- 15. From here, you can branch to the entry screens for general transaction management functions. You can use the tabs to navigate between the different screens. For more information, see also Tabs.

If you use the financial transaction as hedging instrument within the Hedge Management and Accounting of Exposure Items process, you must enter the hedging classification and hedge request on Administration tab and if the hedged exposure item is reference based, you must assign the exposure item ID on FX Hedge Management tab. See also: Create Hedging Instruments

- 16. To store the transaction, choose Save.


Comment: When you conclude a transaction, the cash flow consists only of the premium. You can create both European and American types of option in the system (settlement).

###### Processing an FX Option (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > FX Option > Processing an FX Option | L7 | trm05 p.105 | loio `4fab26af6d2447a68cf6f5ad460acdc5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4fab26af6d2447a68cf6f5ad460acdc5.html?locale=en-US)

After you have created an FX option the following functions are available for further processing of interest rate instruments.

**Use**

You can process FX options using Manage Financial Transactions, Process Financial Transaction, or Process FX Options Collective Processing apps on SAP Fori launchpad. In the area menu in back-end system, you can use the functions Process Financial Transactions (transaction FTR_EDIT) and OTC Option: Collective Processing (transaction TI91).

Functions available for processing FX options:

|Function|Entries|Comments|
|---|---|---|
|Change|Choose Change. The screen for changing the transaction structure appears. Make any necessary changes and save the financial transaction.|You can overwrite the active entry fields or enter data in the empty fields. You can use the tab pages to branch to the general transaction management screens and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are Flagged for Posting.|
|Settle|Choose Settle. The Settle screen appears. When you save a settlement activity, the system changes the activity category of the transaction to record that it is monitored and processed in the back office area. The contract can only be posted after it has been settled.|When you use the Settle function, you can indicate the financial transaction to record that it has been processed in the back office. At this stage, you check the financial transaction and add any missing data. When you save the transaction, the system fixes the transaction (actual records) and flags the transaction flows for posting.|
|Exercise|Choose Exercise. The screen for displaying the transaction data appears. In the case of cash settlement, the Cash Settlement area appears on the Structure tab. When you save the option, it is stored in the relevant activity category.|You can only exercise an OTC option when it has reached the exercise date. When you exercise the option with cash settlement, the settlement amount is calculated on the basis of the difference between the strike and the current market price. If the current exchange rate in market data is so that you will receive money for your purchased option the system calculates the cash settlement amount via a given exchange rate. Otherwise the system shows no amount. For a sold option this is vice versa. Your option buyer will only exercise the option when he gets money, so the system calculates only outgoing cash settlement amounts or shows no amount.|


|Function|Entries|Comments|
|---|---|---|
| | |In case your want to pay (or receive) money in a third currency, the calculation is not supported. Just enter the amount and currency negotiated with your counterparty. In the case of physical exercise, the system creates the underlying (spot) transaction, when you save the activity exercise settlement, see the next step.|
|Exercise settlement|Choose Exercise Settlement. When you save the option, it is stored in the relevant activity category.|In the case of physical exercise the system creates the underlying (spot) transaction when you save the activity. You have to save the automatically created sport transaction as well. At the end the financial transaction number of the underlying transactions is displayed on Structure tab of the option. In addition, you have to settle the underlying transaction as well.|
|Expiration|Choose Expiration. The screen for displaying the transaction data appears.|If the option has no value, it is deleted. As is the case with exercise, you may have to settle this expiration again, depending on the processing category.|
|Give notice|Choose Give Notice. The Give Notice on OTC Option: Initial screen appears.|When you give notice on an OTC option, the transaction remains active and is transferred to the termination activity category. When you value this transaction again, any unrealized gains and losses that have already been posted are reset.|
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. |


|Function|Entries|Comments|
|---|---|---|
| |management, you may have to release the flows before you post or reverse them.| |
|Display|Choose Display. The screen for displaying the structural characteristics appears.|The entry fields are not active. You can use the tab pages to navigate between the various screens and display the other transaction data. Choose to go to the master data for the business partner.|
|Display history|Choose History. The system lists the activities that are active, reversed or have been replaced by a follow-up activity. From this list, you can branch to the display for the individual activities. You also see their status and the user who processed them.|The history function allows you to trace the activity sequence so far for the transaction you have selected.|

###### Call and Put - Explanation

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > FX Option > Call and Put - Explanation | L7 | trm05 p.108 | loio `8514da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8514da531198434de10000000a174cb4.html?locale=en-US)

Definition

When you purchase a currency option, you have the right but not the obligation to do the following:

Purchase a currency (call)

Sell a currency (put)

At a price fixed in advance

At a time fixed in advance (European option) or within a period of time fixed in advance (American option)

Against payment of a fixed premium option to the supplier

The supplier is obliged to purchase/sell on the exercise date.

[figure TRM05-F034]

###### Input Help for Call and Put

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > FX Option > Input Help for Call and Put | L7 | trm05 p.109 | loio `8814da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8814da531198434de10000000a174cb4.html?locale=en-US)

Features

This matrix provides you with an overview of the various options available for creating a currency option in your local currency.

|Transaction type|Underlying (Spot transaction)|Purchase option|Sale option|
|---|---|---|---|
|Purchase foreign currency with local currency| |Long call|Short put|
|Sell foreign currency against local currency| |Long put|Short call|


You determine the short/long positions when you enter the transaction type (when you purchase or sell the option).

You fix the call/put positions in the underlying. In doing this, you choose between two scenarios:

If one of the two currencies is the local currency, the foreign currency is used to decide whether it is a call or put.


Example: Buy USD, sell EUR, result: USD call.

If, however, you have two foreign currencies, the leading currency in the settings table determines whether you have a call or a put.


Example: You want to sell a call in a foreign currency (short call). You need to make the following entries:

Choose transaction type, Sale , in the initial screen.

Enter your Local currency in the Purchase field.

Enter the Foreign currency in the Sale field.

Exercise date, Strike and Premium sale data are further mandatory fields.

Save the Short call you have created.

For more detailed information, see Basic Data .

###### Create Collar FX Option (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > FX Option > Create Collar FX Option | L7 | trm05 p.110 | loio `ddcbd696188947038f46dc8c927e101a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ddcbd696188947038f46dc8c927e101a.html?locale=en-US)

With this app, you can create collar FX options by creating two FX options and linking them to each other. A collar FX option involves the purchase of a call option and the sale of a put option, or vice versa.

**Key Features**

This app provides the following key features:

Creation of collar FX options

Possibility to edit the two FX options forming the FX collar by choosing More OTC Option and selecting one of the following activities:

Change

Display

Exercise

Expiration

Terminate

Settle

Reverse

Displaying business partner details by choosing Display Partner

**Procedure**

- 1. Launch the Create Collar FX Option app from your SAP Fiori Launchpad.
- 2. Enter the company code, business partner, product type (76A), and the transaction type (100 Buy or 200 Sell) for both FX transactions.
- 3. If you want to, you can assign the transactions to a portfolio on the initial screen of the app.
- 4. In the Activity area, choose whether you want to create the transaction as a contract or as an order.
- 5. Choose Enter to jump to the next screen.
- 6. On the next screen, you enter the actual transaction data for the call and the put option that make up the collar FX option.


- 7. Select the Exercise Type (European or American) and the settlement (1 Physical Exercise, 2 Cash Settlement, or * Not Yet Specified) for the first transaction.
- 8. Enter the Expiry Date and Expiry Time for the first transaction.
- 9. Enter the currency pair and the strike for the first and the second transaction.
- 10. Specify whether the first transaction is a put or a call.
- 11. Enter the traded currency and the traded amount.
- 12. Enter the value date.

This is the payment date when the transaction is exercised (generally, two working days after the exercise date).

- 13. You can define the current spot rate as a spot reference in the Option area.
- 14. Specify the following for the option premium:

Select the premium notation (Points or Percentage).

Enter the percentage or points.

Select the desired flow type for both transactions.

Enter the premium amount for both transactions.

Select the payment date for the premium.

Choose the currency in which the premium is to be paid. If this currency is one of the currencies in the currency pair for the transaction, the system calculates the amount automatically when you enter the percentage or points.

- 15. Enter the following data that is relevant for both financial transactions:


**Note:**

The system automatically takes over the entries made for the first transaction to the second transaction.

**Note:**

The Expiry Time field is only available for input if you have maintained location codes in Customizing under Treasury and Risk Management Transaction Manager Correspondence General Settings Define Location Codes and have assigned them to specific times using the Define Values for Expiry Time function.

**Note:**

The system automatically sets the opposite value for the second (offsetting) transaction.

**Note:**

The offsetting amount is calculated by the system.

Parent CFI Code

The Classification of Financial Instruments (CFI) code is used for trade repository reporting, such as for EMIR regulations. The parent CFI code is used to define structured or composite financial instruments, such as FX swaps.

Parent ISIN

The International Securities Identification Number (ISIN) is used, for example, for trade repository reporting, such as for EMIR regulations. The parent ISIN is used to uniquely define structured or composite financial instruments, such as FX swaps.

- 16. Contract Conclusion

In this area, you can enter overall, administrative information relevant to the financial instrument:

Contract date and time

Contact person

Market identifier code (MIC)

Market identifier codes (MICs) are four-character international standard codes (ISO 10383). MICs are used to identify exchanges, trading platforms, and regulated or non-regulated markets as sources of prices and related information to facilitate automated processing (exchanges, settlement, and other automated processes).

For more information, see Market Identifier Code.

Trader

External reference

- 17. Save your entries.


**Note:**

You create and activate MICs in Customizing under Market Data Management Master Data Specify Market Identifier Codes .

**Supported Device Types**

Desktop

Tablet

**Related Information**

Creating an FX Option

###### Currency Barrier Option

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Currency Barrier Option | L6 | trm05 p.112 | loio `3a15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3a15da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Currency barrier options have a defined upper and lower limit (instrike or outstrike). If the market exceeds or falls below these limits, the option either becomes effective or expires depending on the option type. You enter these barriers together with the transaction data.

Using the knock-in or knock-out activities, you activate the options for exercise/expiration:

[figure TRM05-F037 - You can check the instrikes and outstrikes of currency barrier options using the Expiration/Barrier Check function. After comparing the transaction data with the relevant prices, the system proposes a transaction (knock-in, knock-out, or expiration) for procesing the transaction further.]

You can check the instrikes and outstrikes of currency barrier options using the Expiration/Barrier Check function. After comparing the transaction data with the relevant prices, the system proposes a transaction (knock-in, knock-out, or expiration) for procesing the transaction further.

You can use the Option Price Calculator to calculate market-based option prices. The option price calculator includes the agreed barriers and rebates that are paid upon expiration of the option, if required.


You cannot enter rebates in the transaction structure.

**Features**

Im Treasury and Risk Management, you can represent the basic option categories used for trading on the market. The basic categories for calls (purchase options) and for puts (sale options) include the following:

Down and Out: Option expires at or below the outstrike

Up and Out: Option expires at or above the outstrike

Down and In: Option is activated at or below the instrike

Up and In: Option is activated at or above the instrike

You can also enter double barrier options activation or expiration depends on whether the values exceed/fall below two barriers. A double barrier option knock-in becomes effective, for example, when either the upper limit is exceeded by the market or the market falls short of the lower limit.

###### Swaptions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Swaptions | L6 | trm05 p.114 | loio `3d15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3d15da531198434de10000000a174cb4.html?locale=en-US)

**Use**

A swaption is an option on a interest rate swap, which you can exercise on a certain date or within a certain period (product category 760 OTC Options using product category 620 Swap as underlying). As the buyer, you can choose whether to pay fixed interest rates or whether to receive fixed interest rates after the option has been exercised. You pay a premium to the seller for this right upon conclusion of the transaction.

The system supports you from the purchase/sale, through position management, including period-end closing, and reporting until the end of term including the exercise of the option. Risk-free rates are supported in variable interest conditions.

  Restriction

The calculation of the net present value (NPV) of this kind of swaption is not supported.

In the automatic process for the derivation of financial objects, you can set the indicator for activating the market risk analysis in the financial objects for swaptions to Inactive. In this way, the swaptions are ignored in the market risk

analysis apps such as the Calculate Market Risk Key Figures app, the Analyze NPV app (app ID: JBRX), the Sensitivity Key Figures, Single Analysis app (app ID: AISS), and the Calculate Market Risk Key Figures app (app ID: AISGENKF).

In the Calculate Net Present Values - With CVA and DVA app (app ID:TPM60CVA), we recommend that you set the selection conditions so that swaptions are not processed. If the NPV of a swaption is needed for valuation steps in the key date valuation, enter the NPVs manually in the Enter Net Present Values app.

For the calculation of limit utilization using the End-of-Day Processing app (app ID: KLNACHT) or in the integrated single transaction check for swaptions, you can either define the Customizing for the attributable amount calculation for this kind of swaptions so that the limit utilization amount is based on the nominal amount instead of on the NPV, or ignore the swaptions for the counterparty/issuer risk. To do so, set the Counterparty/Issuer Risk Active indicator to Inactive for swaptions under Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings Automatic Integration of Financial Objects in Transaction Master Data Activate/Deactivate Automatic Financial Object Integration . Then use the Update Financial Objects app to deactivate credit risk analysis

for existing financial objects for swaptions by having the financial objects updated according to the changed derivation rules.

**Prerequisites**

When you create the swaption product type, you also must maintain the swap product type as the underlying instrument.

**Process flow for swaptions**

- 1. Create a swaption.
- 2. Send and receive correspondence according to your settings for correspondence.


- 3. Settle and post the transaction. For the payment-relevant flows such as the option premium, payment requests are created and paid according to your payment process.
- 4. During period-end closing, execute key date valuation for the swaptions. If the NPV of a swaption is needed for valuation steps in the key date valuation, enter the net present values manually in the Enter Net Present Values app.
- 5. At expiry date, you either exercise or expire the swaption depending on the situation on the market.


Exercise the swaption.

- a. Open the Manage Financial Transactions app or the Process Financial Transaction app. Select the swaption and choose Exercise.

When you save the option, it is stored in the relevant activity category. The system creates the underlying transaction, when you save the activity exercise settlement.

- b. Open the Manage Financial Transactions app or the Process Financial Transaction app. Select the swaption and choose Exercise Settlement.
- c. Save the transaction.
- d. The system creates the underlying transaction.
- e. You must save the automatically created financial transaction as well. The number of the underlying transaction is now displayed on Structure tab of the option.
- f. In addition, you have to settle the underlying transaction as well.


Expire the swaption.

Open the Manage Financial Transactions app or the Process Financial Transaction app. Select the swaption and choose Exerpire. As is the case with exercise, you may have to settle this expiration again, depending on the processing category.

###### Creating a Swaption

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Swaptions > Creating a Swaption | L7 | trm05 p.115 | loio `44307cf7e650448eaedfdf4c4f45e5e0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/44307cf7e650448eaedfdf4c4f45e5e0.html?locale=en-US)

**Context**

You create a swaption using the Create Financial Transaction app or the Create OTC Option app.

- 1. Open the Create Financial Transaction app or the Create OTC Option app on SAP Fiori launchpad.
- 2. Enter the company code, product type, transaction type (100 (Buy) or 200 (Sell), and the business partner.

If you want to assign the transaction to a portfolio, enter a portfolio in the Limits area. Alternatively, you can enter a portfolio on the Administration tab in the Position Assignment area.

- 3. In the Activity area, choose whether you want to create the transaction as a contract or as an order.
- 4. Choose Enter to go to the basic data screen for the option. On the Structure tab, you enter the actual transaction data.
- 5. Enter the general data in the Option section, such as Expiry Date, Exercise Type and Settlement.
- 6. In the following, you enter the data for the underlying transaction of the option. This is either an interest rate swap or an cross-currency interest rate swap.


Enter the Term of the underlying transaction.

Enter the relevant Business Calendars for the dates of the financial transaction.

Outgoing Interest / Incoming Interest

In these areas, you define the interest conditions of the swaps:

Nominal Amount and Currency

Effective From

**Note:**

You can create an interest rate condition with a start date before the Start date of the financial transaction.

1st Due Date

Freq.Month

Enter a fixed rate or Variable Reference Interest Rate.

Int. Calc.Method

Using the Underlying button, you can switch to the entry screen for the underlying transaction. There you can use the Details button, to reach the interest condition detail screens for the outgoing and incoming interest conditions. For more information, see also Condition Details: Interest (New FIMA) screen.

Using the Conditions button, you can jump to the condition overview for the outgoing or incoming side. There you can drilldown to the condition details of the available condition items and you can create additional condition items.

In the conditions overview of the variable interest conditions, also the the related interest rate adjustment condition is available. In the Detail View: Interest Rate Adjustment, you can specify how frequently the variable interest rate is recalculated and on which day the underlying reference interest rate is set. An interest rate adjustment can be carried out at the start of the period, regularly or on specific dates, for example.For more information, see also Interest Rate Adjustment.

**Note:**

For interest rate swaps with a business partner with whom you have agreed on net payments, you must ensure that the original flows aren’t posted. To do this, go to Conditions - Outgoing Side and Conditions - Incoming Side, from where you can navigate to the condition details for all conditions. In the condition details, for example, for interest and closing, you select the condition types that are not relevant for posting.

In addition, you can change the flow types for the posting relevant nominal flows. Click the Create Nominal Changes icon next to the Nominal Amount fields and change the flow type for nominal flow to 1105.

Check the results of your entries on the cashflow tabs (Cash Flow and Incoming and Outgoing Flows).

- 7. In the Premium area, choose the flow type of the premium. Then enter the payment date, the curency and the amount of the premium.
- 8. You can change additional data on the different tabs.

For more information, see Tabs.

- 9. To store the transaction, choose Save.

###### Processing Swaptions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Swaptions > Processing Swaptions | L7 | trm05 p.116 | loio `3304110f32ee4b15a708ef7fa66aa4f5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3304110f32ee4b15a708ef7fa66aa4f5.html?locale=en-US)

Overview of the available functions for swaption in the Manage Financial Transactions, the Process Financial Transaction, or Process OTC Options - Collective Processing apps.

**It depends on the current state of the financial transaction, which of the following processing functions is available:**

|Function|Entries|Comments|
|---|---|---|
|Change|Choose Change. The screen for changing the transaction structure appears. Make any necessary changes and save the financial transaction.|You can overwrite the active entry fields or enter data in the empty fields. You can use the tabs to branch to the general transaction management screens and make any necessary changes. You can use this function to change an activity, provided that it is not relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are flagged for posting.|
|Settle|Choose Settle. The Settle screen appears. When you save a settlement activity, the system changes the activity category of the transaction to record that it is monitored and processed in the back-office area. The contract can be posted only after it has been settled.|When you use the Settle function, you can indicate the financial transaction to record that it has been processed in the back office. At this stage, you check the financial transaction and add any missing data. When you save the transaction, the system fixes the transaction (actual records) and flags the transaction flows for posting.|
|Exercise|Choose Exercise. The screen for displaying the transaction data appears.|You can exercise an OTC option only when it has reached the exercise date. If Exercise Type is European, the Exercise Date should be equal to Exercise Period. If Exercise Type is American, the Exercise Date should be earlier than or equal to Exercise Period. The system creates the underlying interest rate swap transaction when you save the activity Exercise Settlement (see the next step).|
|Exercise Settlement|After the option was exercised, choose Settle. When you save the option, it is stored with the activity category Exercise Settlement.|The system creates the underlying interest rate swap when you settle the exercised option and save the activity. You save the automatically created interest rate swap transaction as well. The financial transaction number of the underlying transactions is displayed on the Structure tab of the option. In addition, you have to settle the underlying transaction.|


|Function|Entries|Comments|
|---|---|---|
|Expiration|Choose Expiration. The screen for displaying the transaction data appears.|If no value exists for an option, the option is deleted. As is the case with exercise, you may have to settle this expiration again, depending on the processing category.|
|Give Notice|Choose Give Notice. The Give Notice on OTC Option: Initial screen appears.|When you give notice on an OTC option, the transaction remains active and is transferred to the termination activity category. When you value this transaction again, any unrealized gains and losses that have already been posted are reset.|
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. |
|Display|Choose Display. The screen for displaying the structural characteristics appears.|The entry fields are not active. You can use the tabs to navigate between the various screens and display the other transaction data. Go to the master data to navigate to the business partner.|
|Display History|Choose More History . The system lists the activities that are active, reversed, or have been replaced by a follow-up activity. From this list, you can branch to the display for the individual activities. You also see their status and the user who processed them.|The history function allows you to trace the activity sequence so far for the transaction you have selected.|


|Function|Entries|Comments|
|---|---|---|
|Terminate|1. Choose Terminate. 2. Enter the termination date in the Term.Date field. 3. Enter the payment amount for the termination flow (flow type 1390). 4. Choose Save. |You can terminate OTC options early before their maturity. The OTC options must have the activity category Contract Settlement. When you save the termination activity, the system creates a business transaction for the termination and the termination flow. The transaction is saved in activity 3 Termination.|

###### Interest Rate Guarantee (IRG)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Interest Rate Guarantee (IRG) | L6 | trm05 p.119 | loio `4015da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4015da531198434de10000000a174cb4.html?locale=en-US)

**Use**

An IRG is for an option on a Forward Rate Agreement(FRA).This option enables you to hedge against negative interest rate trends.

The seller of the option guarantees the buyer a short-term forward interest rate agreed in advance (strike price). The two variants of this option are call-on-FRA and put-on-FRA, which define the buyer’s right to either buy or sell a FRA.

**Activities**

The premium is calculated according to generally accepted conventions. To enter the transaction, you enter both the underlying instrument (that is, the underlying FRA with its structural characteristics) and the option together with the corresponding premium. Initially, the cash flow only displays the option premium that is paid or received. On the due date, the option is either exercised or expires, rendering it worthless. If the option is exercised, the cash flow displays the calculated settlement payment.

###### Security Option

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Security Option | L6 | trm05 p.119 | loio `66452bfd453b4d129dd4f3d1b53c028f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/66452bfd453b4d129dd4f3d1b53c028f.html?locale=en-US)

**Definition**

A security option is an OTC option on a security purchase or sale (product type 76J). You can buy or sell security options on purchases and sales of security classes with the following product types:

Stock

Subscription right

Bond

Index-linked bond

Money-market fund

Shareholding

**Note:**

For european and american stock options and european bond options, you can use the Calculate Net Present Values - With CVA and DVA app (app ID: TPM60CVA) to automatically calculate the net present value (NPV).

For security options with other underlying securities, you must maintain the NPV manually in the Enter Net Present Values (app ID: JBNPV) app.

**Apps for Processing Security Options**

You can create and process security options in the Manage Financial Transactions app (app ID: F6157). Alternatively, you can use the Create Financial Transaction app (app ID: FTR_CREATE) to create security options.

**Customizing for Securities Options**

Define the product type for the security option in the Customizing activity Define Product Types - OTC Derivatives and assign a product type (based on product category 712 Security as Underlying) in the Underlying area.

Define transaction types 100 Purchase and 200 Sale for security options in the Customizing activity Define Transaction Types - OTC Derivatives.

Define position-management procedures for securities options in the Customizing activity Define Position Management Procedure.

Examples:

0DFT for IFRS and US GAAP

3DNT for HGB

Define a volatility type for securities price volatilities with moneyness. You can choose this volatility type in the section Security Volatility Types in the Customizing activity Define and Set Up Evaluation Types.

You can assign security ID numbers to volatilities in the app Volatilities with Moneyness - Assign Securities ID (TMDAS_VOLANAME2CLASS). The volatilities are defined in the app Volatilities with Moneyness - Enter Values (TMDVOLANAME).

**Related Information**

OTC Options Stock Options Options on Bonds (OTC)

###### Compound Option

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Compound Option | L6 | trm05 p.120 | loio `f514da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f514da531198434de10000000a174cb4.html?locale=en-US)

**Use**

A compound option is an option on a currency option .


This is an option on an option, which means that there is also an underlying transaction (for example, a spot exchange transaction) for the related underlying transaction ( Currency Option ).

The advantage of a compound option lies in the fact that the option premium is lower than the premium for a currency option, although this does mean paying a second premium for the underlying transaction when you exercise the compound option. If, however, you do not exercise the compound option, you have paid a lower premium for a possible hedge than the one you would

have paid had you purchased the currency option immediately.

**Prerequisites**

When you create the compound option product type, you have to maintain the standard currency option product type as the underlying (see the section on defining product types in the Implementation Guide).

###### Average Rate Option

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Average Rate Option | L6 | trm05 p.121 | loio `bc16da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bc16da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Average rate options (AROs) contain the same structure data as standard currency options (or plain vanilla options). The only difference is that an average rate is used at expiry instead of the market rate for comparison with the strike price.

The average rate used is taken from an average rate table and displayed in the transaction.

**Activities**

For each transaction, one or more tables with dates and rates are maintained for the average rate option. An average rate is calculated based on these rates. All rates in the tables belong to exactly one currency pair. However, they may have different rate types.

You can use the Fix Average Rates report to determine exchange rates for calculating average rates or the Reset Average Rate Fixing to delete these rates.

###### Basket Option

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Basket Option | L6 | trm05 p.121 | loio `0115da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0115da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use the basket option if you want an option with at least two underlyings with different currencies.The basket option spot is the sum of spots of each underlying. A basket option with only one underlying is basically the same as a plain vanilla option.

**Features**

At exercise the value of the option is calculated as the difference between the market price and the strike of each single underlying (strip) of a basket option. If the result is positive, the option is in the money and the buyer of the option receives the pay out from the seller of the option.

A basket option is cheaper than the sum of all plain vanilla options because it is usually less volatile.

If a basket option is exercised all single currency puts or calls have to be exercised.

Basket options with several underlyings have the disadvantage that all currency strips have to be exercised even if one or more of them are in or out of the money.

Several plain vanilla options can be exercised per currency in respect of their moneyness on the expiration date.

The difference between a basket and several plain vanilla options occurs if correlations between the participating currencies change after inception.

Use the Fix Average Rates report to fix the rates for a basket option. The rates can be reset using Reset Average Rate Fixing

.

###### Correlation Option

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Correlation Option | L6 | trm05 p.122 | loio `8415da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8415da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The risk of changing correlations is covered by a correlation option.

This option reflects the difference in value between a basket option and the sum of all participating currency strips as plain vanilla options.

**Features**

A correlation option is cash settled and only European style.

Correlation options have some of the same data as a plain vanilla options such as contract date, exercise date, a premium cash flow and a cash settlement flow when exercised

As this option can never be settled physically it merely contains data for calculation purposes. This data should be the same as for a basket option. The option differs from a basket option only in that they have different option types.

Use the Fix Average Rates to fix the rates for the correlation option or reset the rates using Reset Average Rate Fixing .

###### Option Price Calculator (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > OTC Options > Option Price Calculator | L6 | trm05 p.122 | loio `3d16da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3d16da531198434de10000000a174cb4.html?locale=en-US)

You can use the option price calculator to calculate premiums for Standard Options and Exotic Options.

**Activities**

- 1. Open the Option Price Calculator (transaction code TXAK).

The Calculate the Premium of FX Options screen appears.

- 2. Enter the following data:

Evaluation Type

Evaluation Currency

Evaluation Date

Enter the currency pair in the fields Leading Currency and Following Currency.

Enter the end date of the exercise period in the field Exercise Period.

- 3. Press Enter . The system automatically enters the length of the term and the value date (plus 2 days after the end of the term) in the relevant fields.

- 4. By choosing Market Data button, the fields in the Market Data for Bid/Ask area are filled automatically with current values from market data tables. The exchange rate types required for this are taken from the selected evaluation type.


- 5. By choosing Swap/Forward, also the Swap field is filled automatically.
- 6. Calculating premiums

- a. On the Standard Options tab, enter the Strike in the rows Put 1, Put 2, and Put 3 or in the rows Call 1, Call 2, and Call 3.
- b. Choose the Premiums button. The system calculates the option premium in price points (bid/ask) for Europeanstyle and American-style exercise.


If you want to calculate the premiums for Exotic Options, choose the Exotic Options tab and enter the relevant data, such as the category of the option in Cat field and also the Strike, Barrier, and Rebate fields.

- 7. You can display the volatility upon which the calculation of a known option premium is based:

- a. Position the cursor on a premium.
- b. Choose the Implied Volatility button.


An additional window appears displaying the implied volatility.

You can integrate this volatility into your market data using the Copy button.

- 8. You can display a list of the sensitivities of a single premium or of all premiums.


To display the sensitivities of a single premium:

- a. Position the cursor on a premium.
- b. Choose Sensitivities button. An additional window appears showing the sensitivities of this premium.


To display the sensitivities of all premiums, choose the List button. This generates a global evaluation/list of all sensitivities.

###### Repos (Buy/Sell Back Transactions)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Repos (Buy/Sell Back Transactions) | L5 | trm05 p.123 | loio `4fae531918073359e10000000a421937` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4fae531918073359e10000000a421937.html?locale=en-US)

**Use**

With a Repo (buy/sell back transactions), you agree on the simultaneous sale of securities and their repurchase at a later date. You can use the Repo Transaction function to create both activities in one single transaction.

Whenever somebody in a market performs a repo transaction, their counterparty performs a reverse repo transaction. Consequently, a repo and a reverse repo represent the same transaction but from different perspectives:

From the seller's perspective, the transaction is a repo: a spot sale followed by a forward (re)purchase

From the buyer's perspective, the transaction is a reverse repo: a spot purchase followed by a forward (re)sale.

Overview of Participant Activities in Two Legs of a Repo/Reverse Repo

| |Repo|Reverse Repo|
|---|---|---|
|Participant|Borrower Seller Cash receiver|Lender Buyer Cash provider|
|Spot leg|Sells securities|Buys securities|


| |Repo|Reverse Repo|
|---|---|---|
|Forward leg|Buys securities|Sells securities|


**Features**

You can portray repos with or without collateral transfer, that is to say, with or without delivery of the underlying securities.

The table below outlines the key differences and similarities of the two types of repo:

|Repo WITH Collateral Transfer|Repo WITHOUT Collateral Transfer|
|---|---|
|Underlying securities are moved to the custody of the lender for the duration of the repo.|Underlying securities are not moved to the custody of the counterparty. They remain in the custody of the borrower and consequently need to be given the status Blocked.|
|Underlying securities remain in the ledgers of the borrower (regardless of whether or not they have actually changed custody).| |
|Accrued interest is received by the lender. The interest amounts are shown in the class cash flow for the securities account (in the transaction Display Class Cash Flow for Sec.Acct (TPM40)), but not in the position flow list (in the transaction Treasury Ledger: Flow List (TPM13)).|Accrued interest is received by the borrower. Since the underlying securities are not transferred and therefore remain in the custody of the borrower, interest amounts are not represented in the system for repos without collateral transfer, neither in the class cash flow for the securities account nor in the position flow list.|
|The interest installments are payable to the owner of the securities during the repo.| |
|The repo is represented as a short-term liability.| |


Process

For a demonstration of how repos are depicted in the system with and without the transfer of collateral, see the following example.

Example

When you perform a repo, you effectively sell underlying securities to a buyer while agreeing to repurchase those securities after a specified period of time (term), with the repurchase price being greater than the original sale price (original sale price plus the repo rate). In this way, the buyer is effectively a lender providing a secured cash loan at a fixed rate of interest, using the security as collateral to protect themselves against default by the seller.

If you opt for a repo with collateral transfer, the underlying securities are moved to the custody of the lender, and, for the duration of the repo, the lender – as the new owner of the securities – receives the interest coupons, part of which need to be paid to the seller as the original owner of the securities. Simultaneously the securities must be reflected in the borrower’s balance sheet. Therefore in the system the transfer is reflected only in the class cash flow for the securities account, not in the position flow list, and the interest payments are adjusted accordingly.

For an example of the calculation of accrued interest, see Accrued Interest.

If, on the other hand, you opt for a repo without collateral transfer, the underlying securities do not change custody, and you – as the owner of the securities – continue to receive the interest coupons. For this reason, the system does not calculate accrued interest. Consequently, the transfer does not appear either in the class cash flow for the securities account or in the position flow list.

See Also

For more information about cash flows, see Cash Flow for a Class in a Securities Account.

**Activities**

For more information, see the following:

Customizing for Repurchase Transactions (Repos)

Creating Repurchase Transactions (Repos)

Editing Repurchase Transactions Repos).

###### Securities Lending (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Securities Lending | L5 | trm05 p.125 | loio `ac15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ac15da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use the Securities Lending product type to create and manage securities lending transactions with a fixed and open-ended term.

**Note:**

The system only displays lending transactions. For these transactions, securities from the securities position are lent to a counterparty.

**Prerequisites**

You have created and released your business partners and assigned them roles. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Business Partners Maintain Business Partner (Transaction BP ) .

You have set up the product type (for example, fixed-term lending) in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Master Data Product Types

Define Product Types . You can create other product types in addition to the product types provided by SAP. You create financial transactions based on the product types and manage them along with the positions.

You have set up the transaction type in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Transaction Management Transaction Types Define Transaction Type . You use the financial transaction type (for example, lending) to determine which transaction types can be executed within a product type. The transaction process and position management process are based on the transaction type.

You have created the flow type (for example, lending revenue) and assigned it to a transaction type in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities

Transaction Management Flow Types (Transaction) Define Flow Types . You use the flow types to determine the type of payment flows.

You have set up the condition type (for example, the lending revenue condition) in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Master Data Product Types Condition Types Define Condition Types. .You use this setting to determine which structure characteristics are displayed when you create transactions.

Features

In addition to creating, changing, and reversing securities lending transactions, you can also enter rollover data for fixed-term transactions, and termination data for open-ended transactionsYou must define a standard interest calculation method and default values in Customizing for each product type to calculate lending revenues.

For more information, see Creating Securities Lending and Editing and Displaying Securities Lending .

###### Forward Securities Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Securities Transactions | L5 | trm05 p.126 | loio `d3a7d65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d3a7d65378024308e10000000a174cb4.html?locale=en-US)

**Purpose**

An OTC forward securities transaction is a non-standard purchase or sale agreement between two contracting parties who purchase or sell a specific quantity of a specific security at a specific amount at a future date.

Insurance companies use forward securities transactions to hedge open items, for example.

You can create forward securities transactions for the following product categories:

Stock (010)

Investment Fund (020)

Bond (040)

Shareholding (160)

You can map the life cycle of forward securities transactions from rollover, advance maturity, delivery at maturity, dividend adjustment, cash settlement, and physical delivery.

**Prerequisites**

Customizing

Define Product Types

The system provides the product category Forward Securities Transaction (740). You need to create the required product types for this product category in Customizing for the Transaction Manager under Transaction Manager OTC Derivatives/Listed Derivatives Transaction Management Product Types Define Product Types .

Define Transaction Types

You need to define the Purchase and Sale transaction types for the product types. The processing category 0001 Contract

- Settlement – Due Date is specified for the product category Forward Securities Transaction.

A forward securities transaction can run through the following activity categories:

Contract

Contract Settlement

Rollover

Rollover Settlement

###### Creating a Forward Securities Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Securities Transactions > Creating a Forward Securities Transaction | L6 | trm05 p.132 | loio `8e0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8e0cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

After contracting parties have reached an agreement, the system uses the agreed conditions to create a forward securities transaction.

Short Sale

It is also possible to sell forward securities if the quantity to be sold is not available in the position when the contract is concluded.

Prerequisite

The position lock settings must state No Lock or Lock Generates Warning.

**Prerequisites**

You need to set up a product type in Customizing for forward securities transactions.

The security involved must be defined in the system as a class.

The business partner involved must be created in the system.

For more information, see also Manage Securities Classes.

**Procedure**

- 1. Open the Create Financial Transaction function under Transaction Manager Derivatives Trading .
- 2. Specify the company code, product type, transaction type (Purchase or Sale), business partner, and ID number.
- 3. If you first select Forward Securities Transaction in the Default Entry Financial Transaction area, the input help displays only the product types and transaction types available for this product category.
- 4. Choose Create.


The following tabs are provided to help you enter the transaction data:

Structure

Here you enter the following transaction data:

Underlying Position Data

Securities Account

General Valuation Class

Portfolio

Position Date

Term

Start of Term

End of Term

To enter rollover periods, set the Poss. to Roll Over indicator. Then choose the Rollover Periods pushbutton and enter the periods that have been agreed upon.

It is still possible to roll over the transaction if the indicator has not been set.

Amounts

Number of Units

Forward Price

When the forward securities transaction is saved, the system checks whether the forward price is calculated as below. If the calculation does not match the following procedure, the system displays a warning message. However, the transaction is still saved.

Forward purchase

Forward price = spot price + costs + interest - dividend

Forward sale

Forward price = spot price - costs + interest – dividend

**Note:**

The dividend flow takes into account the actual dividend (status Active). If the actual dividend is not available, the expected dividend is taken into account.

Spot Price

Costs

Interest

Amount

The amount is calculated using the data entered.

Exercise

You set the Settlement indicator to specify either Cash Settlement or Physical Exercise. You can also set this indicator if you run the Delivery function and then select the option Not Yet Specified.

Contract

Contract Date

Contact Person

Trader

External Reference

Dividends (only forward stock transactions and investment transactions)

Dividend Plan

Here you can enter the actual and expected dividends.

It is possible to enter and change the expected dividends at any time. To enter the actual dividends, you can use the Adjust Dividend function.

Expected dividends that are within the term of the forward security transaction have the status Active. Dividends that are not within this period have the status Inactive.

Value Flow

In this area, you can enter the flow of amounts during a dividend adjustment.

- 5. Other tab pages


Administration

Other Flows

Cash Flow

Memos

Status

Analysis Parameter (RM)

Create Analysis Parameters (RM)

- 6. Save your entries.


**Result**

The system creates the forward securities transaction as a Contract. For more information about processing the forward securities transaction further, see Forward Securities Transactions.

###### Rollover of a Forward Securities Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Securities Transactions > Rollover of a Forward Securities Transaction | L6 | trm05 p.135 | loio `820cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/820cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

It is possible to roll over forward securities transactions if you specify this beforehand in the contractual agreement.

**Note:**

It is also possible to roll over only part of the transaction.

**Activities**

- 1. Choose Derivatives Trading/Back Office Processing Edit Financial Transaction.
- 2. Enter the transaction.
- 3. Choose Roll Over .

The existing end of term defined for the transaction is now set to Rollover Date . Enter the new end of term.

Enter the position date.

Update the forward price.

- 4. Save your entries.

The system creates the new Rollover activity category. The previous activity is changed from 0 active to 2 replaced .

All the flows are copied to the new activity.

A new flow (1050/1051) is created and the old main flow is set to 0 in the unit-of-production method of depreciation.

Dividend Plan

Dividends that are scheduled within the rollover period are assigned the status Active .

- 5. The rollover still needs to be settled.

**Advance Maturity**

**Use**

It is possible to bring forward or advance the maturity date of a transaction if this has been previously agreed upon with your contract partner.

**Note:**

It is also possible to advance the maturity of only part of the transaction.

**Activities**

- 1. Choose Derivatives Trading/Back Office Processing Edit Financial Transaction.
- 2. Enter the transaction.
- 3. Choose Advance Maturity .

The End of Term field is ready for input. Enter the new end of term.

Enter the position date.

Update the forward price.

- 4. Save your entries.

The system creates the new Advance Maturity activity category. The previous activity is changed from 0 active to 2 replaced .

All the flows are copied to the new activity.

A new flow (1050/1051) is created and the old main flow is set to 0 in the unit-of-production method of depreciation.

Dividend Plan

Dividends that are no longer scheduled within the term are assigned the status Inactive .

- 5. The advanced maturity transaction still needs to be settled.

###### Advance Maturity

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Securities Transactions > Advance Maturity | L6 | trm05 p.126 | loio `850cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/850cda531198434de10000000a174cb4.html?locale=en-US)

Advance Settlement

Dividend Adjustment

Corporate Action

Delivery

Special settings for forward securities transactions:

Define the underlying transaction type.

For the sale of forward securities, you need to specify the position lock settings that you require (Type of Position Lock and Reason for Lock).

**Note:**

If it is possible to sell short, you need to make the settings No Lock or Lock Generates Warning.

Define Flow Types

- 1050 Forward Purchase (position decrease)

- 1051 Forward Sale (position decrease)

- 1052 Base Flow, Forward Securities Transaction (position increase)


- 1057 Increase, Base UL, Corp.Action

- 1058 Decrease, Base UL, Corp.Action


1310 Cash Settlement (cash settlement)

Account Determination

You need to define account determination for the update types relevant for posting.

Define Position Management Procedure

To integrate forward securities transactions in position management, you need to define position management procedures. To do this, choose Transaction Manager General Settings Accounting Settings for Position Management Define Position Management Procedure .

For forward securities transactions that are settled in cash, use the position management category OTC Derivatives.

For forward securities transactions that are exercised physically, use the position management category OTC Derivatives (Transfer Posting to Underlying).

**Note:**

Up until the due date of the forward securities transaction, you can decide whether to settle in cash or via physical exercise. To do this, you assign your positions to a position management procedure using the position management category OTC Derivatives (Transfer Posting to Underlying).

Specify the step or steps for the key date valuation; the following category steps are provided:

001 One-Step Rate Valuation

- 004 Security Valuation

- 005 Foreign Currency Valuation


Select the procedure you require.

Set the Perform for Key Date Valuation indicator.

Define the valuation type for Hedge Accounting for Positions.

In the Transfer to Underlying area, you can set the following indicators:

Transfer Option Value to Underlying (OTC Derivatives)

Transfer Premium; Reverse Valuations or

Transfer Premium and Valuations (to Purch.Value Underlying)

Execute Valuation of OTC Derivatives

This indicator activates the valuation of OTC derivatives or forward securities transactions at the time of physical exercise.

Assign Position Management Procedure

You then define the rules used to assign a position management procedure to a position under Transaction Manager General Settings Accounting Settings for Position Management Assign Position Management Procedure .

Master Data

You need to define class data for the security.

For more information, see Manage Securities Classes.

You also need to define a business partner.

**Integration**

Authorization Objects

T_DEAL_PD

T_DEAL_DP

T_DEAL_PF (if using a portfolio)

T_DEAL_AG (if the authorization group has been entered)

Integration of a Forward Securities Transaction When Executing Corporate Actions

After you have executed a corporate action, the system automatically creates a new activity (Corporate Actions) for the forward securities transactions whose underlyings are affected by the corporate action. This new activity category generates the following flows:

One flow that reduces the number of units of the underlying to zero.

One flow that updates the number of units in accordance with the specification in the corporate action.

In each case, a flow for the existing due dates.

Update of the ID number

Once the corporate action has been executed, the cash flow for the forward securities transaction obtains the following flows:

Base flow

Delivery flow

Due date flow

All other flows

If the corporate action is reversed, the changes made to the forward securities transactions are also reversed and the situation prior to the corporate action being executed is restored.

Key Date Valuation

When key date valuations are run during the term of the forward securities transaction, you can also run mark-to-market valuations (price valuations).

Posting Examples:

[figure TRM05-F040 - Posting Examples:]

[figure TRM05-F041 - Hedge Accounting for Positions (P-HA)]

Hedge Accounting for Positions (P-HA)

The forward securities transactions in Hedge Accounting for Positions (P-HA) are used as hedging instruments.

**Process Flow of a Forward Securities Transaction**

[figure TRM05-F042]

**Key Features**

The following functions are provided to process forward securities transactions:

|Function|Entries|Comments|
|---|---|---|
|Create| |Creating a Forward Securities Transaction|
|Change|Choose Derivatives Trading/Back Office Processing Edit Financial Transaction . Enter the transaction number. Choose Change. Make the necessary changes and save your entries.|You can change all transaction data before you settle the contract. After settling the transaction, you should only use this function to correct errors in the following data. End of term Forward price Use the appropriate function from the list below.|
|Settle|Choose Derivatives Trading/Back Office Processing Edit Financial Transaction . Enter the transaction number.|When you save your entries, the system changes the activity category from Contract to Settlement.|


|Function|Entries|Comments|
|---|---|---|
| |Choose Settle. Check the transaction data. Save the transaction if all the data is correct.| |
|Roll Over| |See also Rollover of a Forward Securities Transaction|
|Advance Maturity| |See also: Advance Maturity|
|Adjust Dividends| |See also: Adjust Dividends|
|Deliver| |See also: Delivering a Forward Securities Transaction|
|Display|Choose Derivatives Trading/Back Office Processing Edit Financial Transaction . Enter the transaction number. Choose Display.| |
|Reverse|Choose Derivatives Trading/Back Office Processing Edit Financial Transaction . Enter the transaction number. Choose Reverse.|See also: Reversal|
|History|Choose Derivatives Trading/Back Office Processing Edit Financial Transaction . Enter the transaction number. Choose History.|The history function lists all previous activities for the transaction. You can identify the active status and all previous statuses. The system also displays the Entered By and Changed By fields as well as the Entered On and Changed On dates. You can branch to the relevant activities using the Activity pushbutton.|

###### Adjustment of Dividends

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Securities Transactions > Adjustment of Dividends | L6 | trm05 p.136 | loio `880cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/880cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The dividend amount affects the forward price of a forward securities transaction. If the paid dividends differ from the expected dividends defined in the system, you can use this function to make adjustments.

Adjustments can be made using the Dividend Adjustment activity category that is provided in the activity chain for the forward security transaction.

**Activities**

- 1. Choose Derivatives Trading/Back Office Processing Edit Financial Transaction.
- 2. Enter the Company code and the Transaction number .
- 3. Choose Adjust Dividends .
- 4. The Dividends tab page appears.


- 5. Define the actual dividends and the dividend date.
- 6. Under Value Flow , you can enter the dividend flow.

These flows are only used for information purposes in transaction management. However, they are taken into account when using the Market Risk Analyzer to determine net present value.

- 7. To change the forward price, call the Structure tab page and define a new forward price.
- 8. Save your entries.
- 9. The transaction is saved with the new data and it changes to activity category Dividend Adjustment .

###### Delivering a Forward Securities Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Securities Transactions > Delivering a Forward Securities Transaction | L6 | trm05 p.137 | loio `8b0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8b0cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

On the due date, the system delivers the forward securities transaction. The security can be delivered in two ways; via Cash Settlement or Physical Exercise.

**Activities**

- 1. Choose Derivatives Trading/Back Office Processing Edit Financial Transaction .
- 2. Enter the Company code and the Transaction number.
- 3. Choose Deliver.
- 4. On the Structure tab page in the Amounts area, enter the spot amount on the due date.
- 5. On the Structure tab page in the Exercise area, you specify whether delivery should be via Cash Settlement or Physical Exercise


**Note:**

You can assign a position management procedure under Environment Position Indicators .

Cash Settlement

Enter the Spot Maturity.

The system calculates the settlement amount. The system generates the flow for Cash Settlement and the purchase/sale flow without an amount.

Save the transaction.

Physical Exercise

Enter the Spot Maturity.

You can still change the position data if necessary.

When you save the transaction, the system generates a purchase or sale. This purchase or sale is assigned to the Contract activity category. The ID of the generated transaction is displayed in the Settlement area in the Ex. Trade field (= the financial transaction resulting from the exercise).

When the regenerated transaction has been settled and posted, the delivery of the forward securities transaction is complete.

###### Position Locks due to Sale of Forward Securities

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Securities Transactions > Position Locks due to Sale of Forward Securities | L6 | trm05 p.138 | loio `4c0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c0cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Position locks can be generated automatically when forward securities are sold, and also deleted automatically when the security is delivered.

The position lock ensures that the quantity of securities to be sold is available in the position at the time of sale. Unlike restraints on disposal , which are valid until a specific date, position locks have a Valid from date.

**Integration**

The position locks that are generated can be displayed in the transactions Editing Restraints on Disposal (TPM43) and Cash Flow for a Class in a Securities Account (TPM40).

**Prerequisites**

To define the following settings for the sale of forward securities in the Forward Securities Transactions area, choose Transaction Manager-> OTC Derivatives -> Transaction Management -> Define Transaction Types .

Type of Position Lock

The type of position lock specifies whether a lock is generated automatically when forward securities are sold, and how the system should react if the position lock is violated.

The following values are available:

No lock

Lock generates warning message

A lock is set. If the lock is violated, the system displays a warning message. The system permits violation of the lock.

Lock generates error message

A lock is set. If the lock is violated, the system displays an error message. This means that the system does not permit the violation.

If you choose this setting, it is not possible to sell short.

Reason for Lock

Choose a reason for the lock.

**Note:**

The existing reasons for locking can be defined in Customizing under Transaction Manager Securities Master Data Securities Account Management Define Locking Flags.

**Features**

If a forward securities sale is settled or changed, the system generates or adjusts a corresponding position lock.

**Note:**

If the position underlying the forward sale is not managed in the Transaction Manager , the system generates a warning message when the forward sale is specified. This informs the user that the position available in the company code, ID

number, and securities account, is not adequate for the forward sale.

The system does not generate a position lock.

However, it is still possible to save the transaction.

The position locks that are generated automatically can be monitored using the functions Editing Restraints on Disposal (TPM43) and Cash Flow for a Class in a Securities Account (TPM40).

Under Edit Restraints on Disposal, you can see the position lock that corresponds to each forward security sale that has not yet been delivered.You can use the Position Trend pushbutton to branch to a list showing the quantity changes (position increase or decrease) for this position as well as the Restraints on Disposal or Position Locks. .

See also:Editing Restraints on Disposal

In the Cash Flow for a Class in a Securities Account , you can see the position lock by displaying the cash flow for the position and then choosing the Position Trend pushbutton. The following list shows both the quantity changes (position increase and decrease) and restraints on disposal or position locks for this position.

See also:Cash Flow for a Class in a Securities Account

Deactivate Position Lock

Position locks that have been generated automatically can not be deleted manually. However, in special situations, you can remove the position lock at short notice by deactivating it. You may need to do this for a securities account transfer, for example.(Only necessary for: Type of Position Lock = Lock Generates Error Message .)

Call the transaction using Change Forward Securities Transaction [TF02] Extras Deactivate Locks . Choose Save . Now the system will display a warning message instead of an error message if the locked position is affected by a sale or securities account transfer.

If a position lock is deactivated, the user responsible for the deactivation is saved by the system in the transaction.This can be seen in the transaction under Last Changed By on the Status tab page.

If the forward securities transaction is edited again and resaved, the deactivation of the lock is automatically reversed.

The position lock enables you to use the locked position as an underlying in securities loans. However, securities lending must have been completed by the sale date.

If the forward securities transaction is delivered, the corresponding position lock is automatically deleted.

**Example**

You have a position of 1,000 units of stock B in your securities account. On 09/15, a forward sale is entered amounting to 1,000 units of stock B for 01/15. The system generates a position lock with Valid from Date : 01/15 for 1,000 position units.

The position can also be used as an underlying for a securities loan as long as lending is completed by 01/14 at the latest.

Impact of a Position Lock in Connection with Securities Lending

[figure TRM05-F043]

###### Forward Loan Purchases

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Loan Purchases | L5 | trm05 p.140 | loio `73ff06b7dcd44a6f9b7184d88a7d368c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/73ff06b7dcd44a6f9b7184d88a7d368c.html?locale=en-US)

**Definition**

A forward loan purchase (FLP) is an agreement between two parties to enter into a loan contract. The loan is not paid out directly after the agreement but at a later point in time. All the loan ingredients are fixed at the contract closure.

You use the Transaction Manager of the Treasury and Risk Management application component to manage forward loan purchases. When the time comes for the loan to be paid out, you do this using Loans Management (see under Prerequisites below).

**Prerequisites**

You need to have Loans Management (LM) installed, configured, and running in your system. For more information on this application, see the relevant documentation.

**Constraints**

Loan Types

Only loans of the following types can be purchased as forward loans:

Mortgage loans

Borrowers note loans

Policy loans

General loans

Customizing

Create the product type FLP (forward loan purchase).

In Treasury and Risk Management, you need to have a paying valuation area for which the product type is permitted for FLPs.

Integration

The table below shows how loans and forward loan purchases interact. Note that, although you must, as stated above, have LM installed and configured before you can process FLPs in your system, FLPs cannot be posted to the valuation areas of LM, hence why the Not applicable entry appears in the table. FLPs are managed in the paying valuation area of the Treasury ledger.

|Product Categories|Operative LM|Treasury Ledger Paying Valuation Area|Treasury Ledger Parallel Valuation Area 1|Treasury Ledger Parallel Valuation Area 2|Treasury Ledger Parallel Valuation Area 3|
|---|---|---|---|---|---|
|Loans|Mandatory|In the paying valuation area, the product group Loan must be excluded (Customizing).|Optional|Optional|Optional|
|Forward Loan Purchases|Not visible in loan management|Mandatory|Optional|Optional|Optional|


**Features**

In Treasury and Risk Management, forward loan purchases are processed within the Transaction Manager. For more information, see the relevant documentation.

You access the processing functions from a single transaction. To reach this in the SAP Easy Access menu, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager

Derivatives Trading Collective Processing Forward Loan Transactions .

**More Information**

For more detailed information, choose the following links:

Creating and Editing Forward Loan Purchases

Forward Loan Purchase: Collective Processing

Valuation

Delivery

Reporting on Forward Loan Purchases

###### Creating and Editing Forward Loan Purchases

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Loan Purchases > Creating and Editing Forward Loan Purchases | L6 | trm05 p.142 | loio `139422c926da415c9bd6d441cec6ca7e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/139422c926da415c9bd6d441cec6ca7e.html?locale=en-US)

**Use**

Forward loans are processed within the Transaction Manager in Treasury and Risk Management.

**Prerequisites**

Customizing in Loans Management

Access Customizing and choose SAP Banking Loans Management Transaction Management Product Types Define Product Types and create product types, if not already available, for the following product categories:

Mortgage loan

Borrower's note loan

Loan policy loan

General loan

Customizing in the Transaction Manager

A product type must be customized for forward loan purchases. To do this, access Customizing and choose Financial Supply Chain Management Treasury and Risk Management Transaction Manager OTC Derivatives Transaction Management Define Product Types .

Select Forward Loans in the Dialog Structure and ensure that a product type is listed. If it is not, create one and ensure that product category 790 is assigned to it.

Also in Customizing, you need to do the following:

Create transaction types.

Create flow types and assign them to your transaction types.

Create update types and assign them to your flow types.

The required Customizing steps are also accessed under Financial Supply Chain Management Treasury and Risk Management OTC Derivatives Transaction Management . Each step includes online documentation with detailed information on what you need to do.

**Procedure**

With customizing complete, you can create and edit your forward loan purchases.

Creating a New Forward Loan Purchase

- 1. You begin the process in Loans Management by choosing Accounting Financial Supply Chain Management Bank Applications Loans Management , then creating a loan of one of the types where FLP is permitted.


You must enter at least the following information:

Company code

Product type

Nominal amount

Start term

End term

Conditions

Check the Forward Loan Purchase flag.

- 2. Save your entries.

The system gives you a contract number.

- 3. Go to the SAP Easy Access menu and choose Treasury and Risk Management Transaction Manager Derivatives Trading Create Financial Transaction .
- 4. In the resulting screen, choose use the input help to select option 19 (Forward Loan Transaction) for the Default Entry Transaction, then press Enter.
- 5. Specify the following:

Company code

Product type: 79A

Transaction type: 100

Underlying loan

This is the number of the loan you created in Loans Management above.

- 6. Press Enter.

The tabs you require to maintain your forward loan purchase appear. Note the following:

Structure

This tab shows the data relating to the underlying contract, including the end date. You can specify a start date here, which must be earlier than the end date for the underlying contract.

Partner assignment

Use this tab to enter contact and other details for other parties to the transaction, including dates showing when they started and finished being involved in the transaction.

- 7. When you have finished, save your entries.


The system issues a transaction number.

Between the contract closure and the payout date the forward loan purchase (FLP) is a derivative financial instrument in Treasury and Risk Management.

Editing an Existing Forward Loan Purchase

- 1. Go to the SAP Easy Access menu and choose Treasury and Risk Management Transaction Manager Derivatives Trading Edit Financial Transaction .
- 2. In the resulting screen, use the input help to select option 19 (Forward Loan Transaction) for the Default Entry Transaction, then press Enter.
- 3. In the Transaction field, enter the number of the forward loan purchase you want to edit, then choose the operation you want to carry out. You can do the following:


Change the transaction

Display the transaction

Settle the transaction

Reverse the transaction

Use the link to access information on the circumstances under which you can reverse an FLP.

View the history of the transaction

###### Reversing Forward Loan Purchases

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Loan Purchases > Creating and Editing Forward Loan Purchases > Reversing Forward Loan Purchases | L7 | trm05 p.144 | loio `af3a2c55065d4645a0414456d02af7c3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/af3a2c55065d4645a0414456d02af7c3.html?locale=en-US)

**Use**

In certain circumstances, it might be necessary to reverse a forward loan purchase (FLP) . How you do this depends on the status of the FLP. The list below explains when this can be done.

**Process**

Status: Contract

In this status, the loan has not been disbursed and reversal is possible.

Status: Contract Settlement

In this status, the loan has not been disbursed and reversal is possible. Reversal sets the loan to status Contract.

Status: Delivered

In this status, the loan may or not have been disbursed.

If the loan has not been disbursed, reversal using this feature is possible and resets the FLP to status Contract or Contract Settlement.

If the loan has been disbursed, the disbursal must be reversed before the FLP can be reversed. Use transaction FNM3 to do this.

###### Forward Loan Purchase: Collective Processing

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Loan Purchases > Forward Loan Purchase: Collective Processing | L6 | trm05 p.144 | loio `1a504b033aa04336bae4f85d51c0660c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1a504b033aa04336bae4f85d51c0660c.html?locale=en-US)

**Use**

The collective processing function enables you to manage your forward loan purchases effectively by displaying a list of selected transactions and by providing the necessary processing functions.

You can use the list to do the following:

Call processing functions for forward loan purchases

Use functions from the work list

Set the Processing indicator

Use functions from the work list

The list is displayed using SAP List Viewer, meaning you can use the standard functions provided there.

**Features**

Selection

You must select at least one Current Activity Category. There is a Select All feature. The options are as follows:

Contract

Contract Settlement

Delivery

All other selections are optional.

General Selections

Company Code

Transaction Type

Product Type

Financial Transaction Type

Loan Partner

Underlying Loan ID

Dates

You can enter individual start and finish dates, or ranges of start and finish dates.

Additional Fields

Assignment

Internal Reference

Characteristics

Entered/last changed by

User

Date

Output

The list is displayed using SAP List Viewer. You can specify a layout here.

|Function|Comments or Link to Further Processing|
|---|---|
|Create|Creating and Editing Forward Loan Purchases|
|Display| |
|Change| |
|Delivery|Creating and Editing Forward Loan Purchases|


| |Delivery|
|---|---|
|Settle| |
|Reverse|Creating and Editing Forward Loan Purchases Reversing Forward Loan Purchases|
|History| |
|Underlying Loan Contract| |
|Display Partner| |
|Status Management| |
|Refresh| |
|Posting Release| |
|Set Processing Indicator| |
|Choose Detail| |


**Activities**

Proceed as follows:

- 1. Call the function by choosing Transaction Manager Derivatives Back Office Processing Collective Processing Forward Loan Purchases .
- 2. Specify your selection critera.
- 3. Choose Execute.

The system displays the collective processing lists, showing all the selected forward loan purchases.

- 4. Select the entry you want to process.
- 5. Execute the function you want to use.
- 6. When you have finished, exit Collective Processing.

###### Valuation (1 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Loan Purchases > Valuation | L6 | trm05 p.146 | loio `9a4db21ae8534e618b2968059675c62b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9a4db21ae8534e618b2968059675c62b.html?locale=en-US)

**Use**

Once created, a forward loan purchase (FLP) is a derivative whose value must be calculated at key dates during its lifetime. The resulting value, called the net present value (NPV), accurately reflects the value of the FLP in your company's accounts.

Such valuation can also take place when the FLP matures — that is, reaches its defined end date — at which point the loan contract can be disbursed as part of Loans Management processing.

**Procedure**

The procedure followed is the same as for any other loan in Loans Management. See the relevant documentation for details.

###### Delivery

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Loan Purchases > Delivery | L6 | trm05 p.147 | loio `afef147fca8442268ec594e966e47cbb` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/afef147fca8442268ec594e966e47cbb.html?locale=en-US)

**Use**

Delivery takes place when the forward loan purchase (FLP) has matured.

**Process**

You can carry out delivery from the collective processing transaction. When you have selected Delivery, entered the relevant data, and executed the program, the system displays a posting log, showing the values posted. You can then disburse the loan in Loans Management.

###### Reporting on Forward Loan Purchases

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Forward Loan Purchases > Reporting on Forward Loan Purchases | L6 | trm05 p.147 | loio `4991557524454b6ba6538867d3c38e57` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4991557524454b6ba6538867d3c38e57.html?locale=en-US)

During processing and after its completion, you can display information on the status of the forward loan purchase.

Reporting is effected in one of the following ways:

Using logical database FTI_TR_DEALS

By going to the SAP Easy Access menu and choosing Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Derivatives , then:

Position Position List , thereby accessing transaction TPM12 to display the position values


Position Trend Position Flow , thereby accessing transaction TPM13 to display the cash flow


Accounting Posting Journal , thereby accessing transaction TPM20 to display the posting journal

###### Total Return Swap (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Total Return Swap | L5 | trm05 p.147 | loio `2c38d5ed2360450b9c7e147b18805b5b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2c38d5ed2360450b9c7e147b18805b5b.html?locale=en-US)

**Use**

A total return swap in the system allows you to swap the total return of a single asset in exchange for periodic cash flows, or you can swap periodic cash flows for the total return of a single asset. The periodic cash flow is typically a floating rate, such as LIBOR

+/- a basis point spread, and a guarantee against any capital losses. With a total return swap, the total return (cash flows plus capital appreciation or depreciation) is exchanged, and not just the cash flows.

You use the Transaction Manager of the Treasury and Risk Management application component to manage total return swaps.

**Prerequisites**

To enter Total Return Swaps, you first need to make the required settings in Customizing for the Transaction Manager:

- 1. Define product types. The creation of financial transactions and management of positions in the Transaction Manager is based on Product Types.


The system provides the product category Total Return Swap . You need to create the required product types for this product category in Customizing by choosing Financial Supply Chain Management Treasury and Risk Management

Transaction Manager OTC Derivatives Transaction Management Product Types Define Product Types .

Select the OTC Swaps tab page and the New Entries.

Assign the product type a key (for example, 64A)

Assign the product type a long text up to 30 characters and a short text no longer than 10 characters.

Product Category = 640 Total Return Swap

Save your entries.

- 2. Define settings for transaction management.

Choose OTC Derivatives Transaction Management Transaction Types Define Transaction Types to create at least one transaction type for transaction category 300 Payer (fixed interest) and one for transaction category 301 Payer (variable interest).

- 3. Define flow types by choosing OTC Derivatives Transaction Management Flow Type Define Flow Type .

The following flow types are required for Total Return Swaps:

1105 Nom. Amt Incr.(Not Rel.f.Postg) for flow category 10 Principal Increase

1107 Nominal Unit Increase/Base flow increase for flow category 10 Principal Increase

1117 Nominal Unit Decrease/Base flow decrease for flow category 11 Principal Decrease

1125 Contract (Not Rel. for Posting) for flow category 12 Final Repayment

1200 Interest for flow category 20 Nominal Interest

1370 Revenue Compensation for flow category 37 Revenue Compensation

1380 Price Compensation for flow category 38 Price Compensation

- 4. Assign the required flow types to each transaction type: OTC Derivatives Transaction Management Flow Type Assign Flow Type to Transaction Type . You must include all the flow types needed to process a transaction (as defined

above)

- 5. Define the relevant update types and assign them to the corresponding transaction types in the Update Types section. For example:

Flow type 1380 Price Compensation assigned to update type DE1020+

Flow type 1380 Price Compensation assigned to update type DE1020–

Flow type 1105 Nom. Amt Incr.(Not Rel.f.Postg) assigned to update type DE1105–

Flow type 1107 Nominal Unit Increase/Base flow increase assigned to update type DE1107+

Flow type 1117 Nominal Unit Decrease/Base flow decrease assigned to update type DE1117–

Flow type 1125 Contract (Not Rel. for Posting) assigned to update type DE1125+

Flow type 1200 Interest assigned to update type DE1200+

Flow type 1370 Revenue Compensation assigned to update type DE2300

- 6. Define and assign the relevant condition types to the transaction types, for example, interest condition, final repayment condition, (for variable interests) interest adjustment condition.


You must also define settings in Customizing for managing positions for Total Return Swaps:

- 1. Check that the Effects of the Update Types on the Position Components are already in place: Transaction Manager General Settings Accounting Settings for Position Management Set the Effects of the Update Types on the


- Position Components
- 2. To integrate total return swaps in position management, you need to define position management procedures. To do this, choose Transaction Manager General Settings Accounting Settings for Position Management Define Position Management Procedure .

You can use the following Position Management procedures or define your own procedures with reference to these:

7000 – OTC Derivatives: Mark-to-Market

7100 – OTC Options: Mark-to-Market (2-Step/OCI)

- 3. Assign the position management procedure to a position using Transaction Manager General Settings Accounting Settings for Position Management Assign Position Management Procedure .
- 4. Assign the update types required for valuation based on the position management procedure: Transaction Manager General Settings Accounting Valuation Class Transfer Update Types Assign Update Types for Valuation Class Transfer


**Activities**

Entering a Total Return Swap

- 1. In the SAP area menu, open Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Derivatives Trading Create Financial Transaction (FTR_CREATE).
- 2. Choose the Company Code.
- 3. Choose the Product Type, for example, 64A Total Return Swap.
- 4. Choose the Transaction Type, for example 300 or 301.
- 5. Choose the business Partner.
- 6. Choose the ID Number.
- 7. Click Enter and the Create Total Return Swap: Structure screen is displayed.
- 8. Complete the relevant fields:

Term

Business Calendar

Contract Conclusion

- 9. Complete the Return Leg/Outgoing data:


Number of Units

Base Rate

Stock Exchange

Rate Type

Flow Type Increase

Flow Type Decrease

****Note:****

The Flow Type fields can be displayed by clicking on the Flow Types button after the initial Return Leg and Funding Leg details have been saved.

- 10. Complete the Funding Leg/Incoming data:

Nominal Amount and Currency

Effective From date

First Due Date and Frequency Month

Fixed Interest

Internal Calculation Method

- 11. Click on the Dividend tab and add a dividend flow if required.
- 12. Complete the remaining tab pages as required.


Additional Functions

|Function|Entries|Remarks|
|---|---|---|
|Change|1. Choose Derivatives Trading Edit Financial Transaction 2. Enter the Company Code and Transaction number. 3. Choose Change. 4. Make your changes and save your entries. |You can change all transaction data before you settle the contract. After settling the transaction, you should only use this function to correct errors in the following data. End of term Forward price Use the appropriate function from the list below.|
|Settle|1. Choose Derivatives Trading Edit Financial Transaction 2. Enter the Company Code and Transaction number. 3. Choose Settle. 4. Check the transaction data. Save the transaction if all the data is correct. | |
|Adjust Dividends| |See also: Adjustment of Dividends |
|Advance Maturity| |See also: Advance Maturity |


|Reverse|1. Choose Derivatives Trading Edit Financial Transaction 2. Enter the Company Code and Transaction number. 3. Choose Reversal. |See also: Reversal|
|---|---|---|
|Key Date Valuation| |See also: Valuation |
|Corporate Actions|After you have executed a corporate action, the system automatically creates a new activity (Corporate Actions) for the total return swap whose underlyings are affected by the corporate action.|See also: Corporate Actions Corporate Actions for Total Return Swap |


**More Information**

For more information, see also:

Collective Processing

NPV for Total Return Swap

Posting

###### Corporate Actions for Total Return Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Total Return Swap > Corporate Actions for Total Return Swap | L6 | trm05 p.151 | loio `92241777371a453a8f38ff2243f0b753` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/92241777371a453a8f38ff2243f0b753.html?locale=en-US)

**Use**

Corporate actions are part of position management in the securities area. They can also influence transaction management deals such as Forward Securities Transactions and Total Return Swaps (TRS). You can use this function to display changes made by the issuer to the capital structure for classes in your position. On the SAP Easy Access screen, choose Accounting Financial

Supply Chain Management Treasury and Risk Management Transaction Manager Securities Accounting Corporate Actions (transaction FWK0).

**Prerequisites**

You have made the following settings for Total Return Swaps in Customizing for the Transaction Manager. See:

Total Return Swaps

Corporate Actions

**Activities**

To process a TRS in the context of a corporate action there is a mixture of automatic steps performed by the system and of manual steps completed by the user:

Manual steps

You may adjust the base rate, nominal amount

You may adjust the dividend schedule

Automatic steps

The system adjusts the number of stocks (if required):

in the TRS itself

in the restraint on disposal

in position management

The system adjusts the security ID (if required):

in the TRS itself

in the restraint on disposal (in case of a forward sale)

**Note:**

There is no need to adjust the underlying security ID in position management (TRQ, TRL) because position management only stores the number of underlying stocks, not the security ID itself.

**Example**

In the following examples:

you have a corporate action with key date 26.06.08

you have an TRS on 100 A-Stocks

|Position Date|Security ID|Number of Stocks|
|---|---|---|
|30/05/08|A-Stock|100|


Total Return Swap

|Contract Date|Security ID|Number of stock|Base Rate|Nominal Funding Leg|End of term|
|---|---|---|---|---|---|
|01/05/08|A-Stock|100|80.00 €|8,000.00 €|01/05/09|


Stock Split

The stock split has a split ration 1:3, i.e. for each stock the stock holder gets additional three stocks. The resulting delivery structure after the corporate action is the following:

|Position Date|Security ID|Number of Stocks|
|---|---|---|
|26/06/08|A-Stock|300|


Total Return Swap

|Contract Date|Security ID|Number of stock|Base Rate|Nominal Funding Leg|End of term|
|---|---|---|---|---|---|


|01/05/08|A-Stock|300|26.666667 €|8,000.00 €|01/05/09|
|---|---|---|---|---|---|


**Note:**

Use the same method for Capital increase from retained earnings.

Stock Swap

In the stock split one A-Stock is replaced by 4 B-Stocks. The resulting delivery structure after the corporate action is the following:

|Position Date|Security ID|Number of Stocks|
|---|---|---|
|01/05/08|A-Stock|100|
|26/06/08|A-Stock|0|
|26/06/08|B-Stock|400|


Total Return Swap

|Contract Date|Security ID|Number of stock|Base Rate|Nominal Funding Leg|End of term|
|---|---|---|---|---|---|
|01/05/08|A-Stock|100|80.00 €|8,000.00 €|01/05/09|
|26/06/08|B-Stock|400|20.00 €|8,000.00 €|01/05/09|


**Note:**

Use the same method for Transfer new stock to old stock

Capital reduction

In the capital reduction 3 A-Stocks are replaced by one. The resulting delivery structure after the corporate action is the following:

|Position date|Security ID|Number of stocks|Delivered|Type of Settlement|
|---|---|---|---|---|
|26/06/08|A-Stock|33.33333|No|Not yet specified|


Total Return Swap

|Contract Date|Security ID|Number of stock|Base Rate|Nominal Funding Leg|End of term|
|---|---|---|---|---|---|
|01/05/08|A-Stock|33.33333|240.00 €|8,000.00 €|01/05/09|


Post subscription rights (SR)

As part of a normal capital increase, you must post the subscription rights for the 'old' stock in the position.

Swap Ratio: 3:1

Subscription Right Ratio: 1:1

Current Market Price: 83.00 €

Subscription price: 5.00 €

[figure TRM05-F047 - Value SR = 83.00 – 5.00 / (3:1) + 1 = 19.50 €]

Value SR = 83.00 – 5.00 / (3:1) + 1 = 19.50 €

Accounting Value of the SR = 19.50 € *85/83 = 19.9699 €

|Position date|Security ID|Number of stocks|Delivered|Type of Settlement|Old Book Value|New Book Value|
|---|---|---|---|---|---|---|
|30/05/08|A-Stock|100|No|Not yet specified|8,500 €| |
|26/06/08|A-Stock|100| | | |6,503.01 €|
|26/06/08|A-Stock Subscription Rights|100| | | |1,996.99 €|


Total Return Swap

|Contract Date|Security ID|Number of stock|Base Rate|Nominal Funding Leg|End of term|
|---|---|---|---|---|---|
|01/05/08|A-Stock|100|80.00 €|8,000.00 €|01/05/09|

###### Listed Derivatives

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Listed Derivatives | L5 | trm05 p.154 | loio `a215da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a215da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Listed options and futures are standard forward transactions that are traded on exchanges. For more information, see Futures and Listed Options.

**Prerequisites**

Creating Master Data

Maintaining Security Prices

In principle, the application recognizes neither a particular exchange nor an actual finance product. These exchanges and finance products are only introduced to the system when you make the Customizing settings.

**Activities**

The terms Purchase and Sale do not describe the increase or decrease of positions for these transactions. Instead, they define the side of the forward transaction. Positions are generated both by the purchase and the sale.

This increase and decrease of positions is represented by open and close.

The position is reduced if there is a counter transaction - offsetting transaction (closing) - with the same class and same ID. One of the two main features of an offsetting transaction is that you can leave the market at any time without needing the consent of the counterparty. This distinguishes listed options and futures in particular from options and forward transactions in the OTC area. The second characteristic is the strict standardization of the contract contents.

[figure TRM05-F048 - The position is reduced if there is a counter transaction - offsetting transaction (closing) - with the same class and same ID. One of the two main features of an offsetting transaction is that you can leave the market at any time without needing the consent of the counterparty. This distinguishes listed options and futures in particular from options and forward transactions in the OTC area. The second characteristic is the strict standardization of the contract contents.]

###### Listed Options

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Listed Derivatives > Listed Options | L6 | trm05 p.155 | loio `9f15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9f15da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A listed option is a forward transaction traded on a forward exchange, which is binding for one party. It has a standardized issue structure. You enter the standardized contract elements in the class master data. Unlike futures, the risk is not evenly distributed in this case. The purchaser (owner of long position) of an option has the right to exercise the option. The purchaser must pay the seller an option premium for this right. The supplier (writer, owner of the short position) must fulfill the conditions of the transaction if the purchaser exercises the option.

The differing risk for long and short positions influences the collateral provisions that the counterparties have to make.

There are two methods:

Normal Style

The purchaser (long) of the option bears no risk, he makes no collateral provision. For each of his long positions, he receives a contribution credit that is offset against his short positions.

The seller (short) has to pay a premium margin. This margin must offset the loss that would arise if he were to sell the position today. If the price is such that the loss of the seller rises, the seller must increase the collateral provision.

Future Style

With DTB options on the DAX future and DTB options on the BUND future and BOBL future, you do not pay the option premium immediately. More often, the daily settlement price is determined and the difference is offset directly as profit or loss. As this settlement method is the same as that for futures, it is called future style. As both sides of the transaction bear a risk, both must provide collateral.

**Structure**

By choosing Master Data Listed Derivatives Class , you can create, display, and change the following options as a class in the system:

- 1. Stock option

The purchaser of a stock option has the right to receive a fixed number of stocks of a class at a fixed price (call option) or to dispose of them (put option). If a purchaser exercises an option, the clearing house of the forward exchange assigns a supplier to the purchaser randomly. The assigned supplier is then exercised by the clearing house. Part exercise of positions is possible.

- 2. Index option

A purchaser of a stock index option has the right to buy (call option) or sell (put option) a block of stock corresponding to the index at a fixed price. Since it would not be possible to settle the security transaction when it is exercised, these types of options are usually exercised by means of a cash settlement.

- 3. Future option (bond)

When you purchase a futures option, you have the right to purchase a futures contract (call option) or sell one (put option) up to the expiration date. When exercising the option, the purchaser of a put option has a short position, and the purchaser of a call option has a long position.

With these options, the premium is not paid upon purchase. The option is settled future style.

- 4. Option on an index future


Trading of this product is currently not possible on the DTB (Deutsche Terminborse = German Forward Exchange).


Note: When you define the product type in Customizing, you specify the option category.

For more information, see also Manage Securities Classes.

**Use**

There are four basic positions:

Long call = The right to purchase the underlying from the owner of the short call position at the basis price agreed in advance. The investor hopes for increasing prices. He will exercise the option as soon as the market price exceeds the basis price as he can then purchase at below the market price.

Short call = The obligation to deliver the underlying to the owner of the long call position at the price agreed in advance. The investor hopes for prices that remain the same or fall slightly so that the option becomes worthless. The option is not exercised. The investor can collect the premium option as a yield improvement of his portfolio in the case of a covered call.

Long put = The right to deliver the underlying to the owner of the short put position at the price agreed in advance. The investor hopes for falling prices. He will exercise the option as soon as the market price falls below the basis price as he can then sell at above the market price.

Short put = The obligation to take the underlying from the owner of the long put position and to pay the basic price agreed in advance. (“Writer of a put option”). The investor hopes for prices that remain the same or increase slightly so that the

option expires worthless and he receives the option premium.

See also:

Calls and Puts - Explanation

Input Help for Calls and Puts

**Note:**

In the contract details, you specify whether a put or call is involved.

**Procedure**

Entering Basic Data

To create a listed option, you must fill the following fields:

Stock exchange (Issuer, calendar)

Dates (last trading day, maturity date, settlement date)

Tick (tick amount, tick value)

Contract details (put/call, number of units, strike amount, securities index, and so on)

Header data, such as the option category and settlement, is based on Customizing settings.

Other Tab Pages

Search Terms

Exchanges

Regulatory Reporting

User Data

Additional Functions

Check


This function checks the class for consistency. Any errors that occur here are displayed in a dialog box. The same checks are performed when you save the class.

Reset


This function is available in the change mode. It resets the class data to the status it had just after it was last saved.

References


This function lists the classes that use the current security ID number as the underlying.

Class: Reference

You can branch from the class data to the issuer data of each business partner. To do this, choose Environment Display Issuer .

You can display the change documents for the class data by choosing Environment Change Documents .

The class status is displayed at the top right-hand side of the screen. You can either change the status there or choose Edit Change Status . A class can have the status Obsolete, Inactive, or Active.

Save your entries before you leave the class data.

###### Futures

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Listed Derivatives > Futures | L6 | trm05 p.158 | loio `9c15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9c15da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A future is a forward transaction that is traded at a forward exchange and that is binding for both parties. It has a standardized issue structure. You enter the standardized contract elements in the class master data. As with all forward transactions, the price is the current daily price plus the finance costs.

**Structure**

By choosing Master Data Listed Derivatives Class , you can create, display, and change the following futures as a class in the system:

Securities futures (bonds)

Interest futures

Index futures

Stock futures

For more information, see Manage Securities Classes.

**Example:**

An investor has a position of fixed-interest bonds.

Target:

At the start of the next quarter, he requires 250,000 EUR and hopes to reach this goal by selling the bonds.

Measure:

To protect himself against price fluctuations, he has two options:

- 1. He sells the securities today at the market price and invests the money he receives in fixed-term deposits.
- 2. He holds on to the securities and sells a bond futures contract.


The price of the forward transaction at the time of conclusion of the transaction must be such that the investor is not worse off than the he would be with the first option. Otherwise, he would not enter into the transaction. This needs to be his best option at this moment in time, otherwise he would find no counterparties.

Result:

The conclusion of the forward transaction on the due date is not at the fixed forward price but at the market price valid at the time. During the term of the future, the settlement price is determined on a daily basis, and profits and losses are cleared immediately (variation margin) using this price. At term end, the sum of these cash flows corresponds to the strike price agreed.

**Procedure**

Entering Basic Data

To create a future, you must fill the following fields:

Name

Exchange (issuer, calendar)

Dates (last trading day, last working day, delivery day)

Tick (tick in % points or tick size, tick value, tick currency)

There are 3 product types in the underlying securities futures:

**Example:**

Securities futures: Underlying fictitious bond, such as bond future with nominal value 250,000. 00 Interest Calculation Method 2 Percentage Rate 6 Nominal Currency EUR Final Due Date 03.02.2026

Interest futures: Underlying reference interest rate, such as 1 month Libor with nominal value 1,000,000. 00 Interest Calculation Method 2 Interest Reference Rate EUR 03 M Mean Nominal Currency EUR

Index futures: Underlying securities index, for example DAX with Index Point Value 100.00 Currency Index Point EUR

Other Tabs

Search Terms

Exchanges

Regulatory Reporting

User Data

Additional Functions

Check


This function checks the class for consistency. Any errors that occur here are displayed in a dialog box. The same checks are performed when you save the class.

Reset


This function is available in the change mode. It resets the class data to the status it had just after it was last saved.

References


This function lists the classes that use the current security ID number as the underlying.

Class: Reference

You can branch from the class data to the issuer data of each business partner. To do this, choose Environment Display Issuer .

You can display the change documents for the class data by choosing Environment Change Documents .

The class status is displayed at the top right-hand side of the screen. You can either change the status there or choose Edit Change Status . A class can have the status Obsolete, Inactive, or Active.

For more information about position management and valuating futures, see Futures Valuation.

###### Processing Listed Options and Futures

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Derivatives > Listed Derivatives > Processing Listed Options and Futures | L6 | trm05 p.160 | loio `fe14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fe14da531198434de10000000a174cb4.html?locale=en-US)

**Prerequisites**

For more information, see Listed Derivatives.

**Procedure**

|Function|Entries|
|---|---|
|Create|1. Choose Trading Listed Transaction Create . 2. Enter the product type, transaction type, and the business partner. If you use external number assignment, you need to enter the relevant key for the transaction. This enables the transaction to be uniquely identified within a company code. If you do not specify a key, the system automatically assigns a key and returns this key when the transaction is saved. 3. You can choose to enter the transaction as an order or contract (execution). The result of order execution is the status of a binding contract. The clearing house for the forward exchange enters the contract as a counterparty for both sides. 4. See Order. 5. Specify the trader, the securities account, and information about the positions (flow type, number of items, ID number, price, or rate). 6. When you save the transaction, enter the account assignment reference. 7. The posting log “Distribution List for Listed Options and Futures” appears, which shows you how many FI documents have been posted. |
|Change/Display|1. Choose Trading Listed Transaction Change . 2. The tabs take you to the general Transaction Management views. Display the data or make the necessary changes. Save the listed transaction. 3. You can also change the activity here, provided it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are flagged for posting. |
|Reverse|1. Choose Trading Listed Transaction Reverse .|


|Function|Entries|
|---|---|
| |2. Enter the reversal reason. 3. The transaction can only be reversed when a reversal reason is specified. You can store reversal reasons in Customizing. For more information, see Reversal. |
|Settle|1. Use the “Settle Financial Transactions” function to indicate that a transaction was processed in the back office. During settlement, the system checks the financial transaction data and adds any missing data. When the transaction is saved, the data is fixed (actual records). The transaction flows acquire the status Flagged for Posting. 2. See Settlement. |

##### Securities (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities | L4 | trm05 p.161 | loio `3adbd7531a4d414de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3adbd7531a4d414de10000000a174cb4.html?locale=en-US)

**Purpose**

In the Securities area, the following processes are available:

Investing in Stocks

A stock represents a share in a stock corporation. The shareholder receives a dividend on a regular basis. For stocks, the 010 Stock product category is available, for which you can define your own product types in Customizing.

Subscription Rights

The process also covers functionality to map changes made by the issuer to the capital structure in your positions or to to map the exercise of security rights. For more information, see also Corporate Action and Exercise Rights.

Investing in Money Market Funds

An investment fund is a share in a fund that is managed by an investment trust. The owner of the share receives dividends but does not have other rights. For investment funds, the product category Investment Fund is available.

Bond Management

Bonds are interest-bearing securities that guarantee the payment of interests and the repayment at the end of term. You can create the class data for bonds using product category 040 (Bonds). In addition, specific product categories are available, such as, 042 Installment Bond, 060 Warrant Bond, and 070 Convertible Bond. You can create different kinds of bond by defining class data and the conditions accordingly:

Fixed-interest bonds

Floating-rate notes

Zero-coupon bonds

You can manage the following processes for bonds:

Issuing Bonds

Investing in Bonds

These processes cover master data management, the trading and processing of securities transactions (including the placement and redemption of issued bonds), as well as paying and posting in Financial Accounting. In addition, various functions for managing security positions and for period-end closing are available. Treasury Reporting provides you with a broad range of apps for analyzing your debts and investments in bonds.

Investing in Shareholdings

A shareholding represents a share in the equity capital of a company. In addition to other rights, the investors usually also receive a right of entitlement to profits, assets and liquidation proceeds. For shareholdings, the product category 160 Shareholding is available.

**Key Features**

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM05-F056]

Please note that image maps are not interactive in PDF outputs.

For securities, you first have to enter class data, securities account master data, and position indicators.

See also: Master Data Entry in the Securities Area

In addition, market data, such as security prices, factor values, FX rates, and interest rates, is needed.

Example: Especially factor values are needed for investment certificates with factor-based dividend conditions. Enter the dividend factor values to calculate the dividend amounts. In detail, the published factor for money market funds determines for a period (one day) the accrued dividend or daily dividend of a money market fund. The accrued dividend (which is not paid) / daily dividend for a period (one day) is calculated by units * dividend factor.

Transaction Management

A security transaction is the purchase or sale of securities (classes), representing a position inflow or outflow.

**Note:**

For the Issuing Bonds process, the specific transaction types 300 Bond-Issue: Placement and 400 Bond-Issue: Redemption are available.

A security transaction passes through the following steps: Getting a quotation, concluding the transaction, and then posting the transaction. These steps are represented in the system by the various activity categories that a transaction can have:

Order (based on a quotation)

Order Expiration (if the transaction is not concluded)

Contract (if the transaction is concluded)

Contract Settlement

[figure TRM05-F057 - Possible Activity Chains of a Security Transaction]

Possible Activity Chains of a Security Transaction

**Note:**

You can start the process by creating an order or by creating the contract.

When the contract settlement has been saved, the transaction flows are assigned the status Flagged for Posting. Open the Post Flows app in the Treasury Accounting group on the SAP Fiori launchpad and trigger the update to the general ledger. After you have executed the posting function, the transaction flows are assigned the status Posted, and are converted from planned records into actual records.

For money market funds with variable NAV (product category 020 Investment Funds), two additional processing categories are available (00003 Order - Contract - Contract Priced) and 00004 Order - Contract - Settled - Contract Priced - CP Settled). The new processing categories allow the payment of the purchase/sale amount even if the exact price and therefore the exact quantity is not known.

[figure TRM05-F058 - For money market funds with variable NAV (product category 020 Investment Funds), two additional processing categories are available (00003 Order - Contract - Contract Priced) and 00004 Order - Contract - Settled - Contract Priced - CP Settled). The new processing categories allow the payment of the purchase/sale amount even if the exact price and therefore the exact quantity is not known.]

- 1. Create the contract.

Enter the payment amount. The provisional price and quantity are determined using existing market data. Creation of the contract automatically triggers the creation of the business transactions Fund Order Payment and Purchase.

- 2. Settle the contract.

When the contract is settled, the payment flow of the Fund Order Payment business transaction is flagged for posting.

- 3. Execute the payment using the Post Flows app.
- 4. Using the Fixing function, the exact price and quantity can be entered. The Fixing updates the purchase/sale quantity flow of the Purchase business transaction.
- 5. Settle the priced contract.

The purchase flow that updates the treasury position with the exact values (with the Purchase business transaction) is now flagged for posting.

- 6. Open the Post Flows app.


The purchase flow that updates the treasury positions with the exact values (with the Purchase business transaction) is posted.

**Note:**

For the parallel valuation areas, you can make postings using either the Post Flows app or the Process Business Transactions app. This is dependent on whether you posted only the operative valuation area with the Post Flows app, or whether you also posted to all valuation areas.

Transaction Management

Functions for creating, changing, and displaying your securities transactions and other utilities, such as the Securities Account Cash Flow, for a class is available to support traders.

Once traders have created financial transactions, the Treasury Specialist - Back Office settles the transactions. The back-office functions also include functions for checking and changing the transactions. The key aspects of postprocessing are as follows:

Entering more transaction data, such as adding information that is relevant for back-office processing

Preparing for posting and payment, for example, by checking the accounts used

Generating correspondence in the form of internal or external confirmations

The Treasury Specialist - Back Office can use functions for netting transactions and for entering or editing references.

Once the transactions are created, checked, and completed, they can be posted to accounting and paid.

Position Management and Accounting

Securities Account Management

You manage the securities positions (= securities account positions) using security account management functions. The following functions are available:

Update Planned Records for Securities available on SAP Fiori launchpad in the Financial Transaction group

Posting condition-based flows (dividends and variable interest flows) using the Automatic Debit Position (Automatic Posting) app

Manual posting on the securities account level (such as custodian fees) using the Manual Debit Position (Incoming Payments) app

In addition, functions for period-end closing operations for the different valuation areas are available.

Dependent on different kinds of dividend, accruals might be needed. You can use the Run Accrual / Deferral app to accrue the profit distribution of money market funds with accrued dividend.

You can use the Run Accrual / Deferral app to accrue or defer the interest flows of your bond positions.

You can run the valuation of your security positions.

More functions for security positions on SAP Fiori launchpad in the Treasury Accounting group:

Execute Valuation Class Transfer

Transfer Account Assignment Reference

Reporting

Treasury Posting Journal - Classic

**Display Treasury Posting Journal**

Treasury Position Flows - Classic

**Display Treasury Position Flows**

Treasury Position Values - Classic

Display Treasury Position Values

Debt and Investment Analysis

Treasury Position Analysis

**Related Information**

Example: Money Market Funds

###### Master Data Entry in the Securities Area

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Master Data Entry in the Securities Area | L5 | trm05 p.165 | loio `c118da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c118da531198434de10000000a174cb4.html?locale=en-US)

**Create Business Partner Data**

In securities management, you require business partners in the roles of issuer, depository bank and counterparty.

Create the required business partners in the required roles.

Define transaction authorizations

To authorize a business partner as a counterparty for selected transactions, go to the SAP Easy Access screen and choose

Accounting Financial Supply Chain Management Treasury and Risk Management Business Partners Special Functions Standing Instructions Transaction Authorization (transaction TBI6).


Payment Details

To enter or change the payment details for business partners in the standing instructions, go to the SAP Easy Access screen and choose Accounting Financial Supply Chain Management Treasury and Risk Management Business Partners Special Functions Standing Instructions Payment Details (transaction TBI1).

If you use standing instructions in securities management, the system enters the house bank and bank clearing account of the counterparty as default values whenever you enter a transaction.

If you do not enter a counterparty with an order or you do not use standing instructions, the system determines the bank clearing account from the entries for the securities account. You have specified a house bank with the relevant bank details when you created the securities account.

For more information, see also Standing Instructions

**Create Class Master Data and Securities Account Master Data**

Manage Securities Classes

After you have entered the issuer as the business partner, you create the class master data for the security. You must create the class master data before you can add the purchase of a security to your securities position in order management.

Define portfolios

If you chose portfolios in Customizing as a differentiation term for valuation, you have to define portfolios in Customizing for Treasury and Risk Management under Basic Functions Transaction Manager General Settings Organization

Define Portfolios . When you create a securities account, you assign it to one of these existing portfolios.

Create Securities Account

You use securities accounts to manage and value your positions. You can create a securities account once you have defined the depository bank as a business partner.

**Position Indicator**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Master Data Position Indicator .

###### Stocks

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Stocks | L5 | trm05 p.166 | loio `cb0f3a4beed5487bbe128e8765a9d7d7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cb0f3a4beed5487bbe128e8765a9d7d7.html?locale=en-US)

A stock represents a share in a stock corporation. The shareholder receives a dividend on a regular basis. For stocks, the 010 Stock product category is available, for which you can define your own product types in Customizing.

**Example**

01A Stock

**Related Information**

Securities Investing in Stocks

###### Investing in Stocks

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Stocks > Investing in Stocks | L6 | trm05 p.166 | loio `9a87dbaa7f1141e4a13e540a4e38e7af` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9a87dbaa7f1141e4a13e540a4e38e7af.html?locale=en-US)

The process covers master data management, the purchase and sale of stocks, as well as paying and posting in Financial Accounting. In addition, various functions for managing securities account positions and for period-end closing are available. If the

issuer of your stocks has made changes to the capital structure, you can use the corporate actions apps to map these changes in the system. Treasury Reporting provides you with a broad range of apps for analyzing your investments in stocks.

**Investment in Stocks**

- 1. Create the class data for your stock using product type 01A Stock.

For more information, see also Manage Securities Classes.

- 2. Create an asset securities account.

For more information, see also: Manage Securities Accounts

- 3. Specify the position indicator. For more information, see also: Manage Position Indicator

- 4. Purchase a stock by creating a securities transaction with transaction type 100 (Stock-Purchase) using the Create Security Transaction app.

- 5. Settle and post the transaction. For the payment-relevant flows, payment requests are created and paid according to your payment process.
- 6. You can also post additional costs, such as securities account fees, using the Create Manual Posting app. Depending on your payment process, payment requests have been created and are processed accordingly.

- 7. The following functions are available for managing stock positions:


Period-end closing

Update security prices and FX rates in the market data table.

Accrual/Deferral of Expenses and Revenues

Run Valuation

Post dividend flows at dividend due date:

You can use either the Manual Debit Position (Incoming Payments) app or the Automatic Debit Position (Automatic Posting) app.

If the issuer of your stocks has made changes to the capital structure, you can use the corporate actions apps to map these changes in the system:

Corporate Action

Posting a Corporate Action

Reversing a Corporate Action

Sale of stocks

Create the sale transaction for the stock using transaction type 200 (Stock-Sale) in Create Security Transaction app.

Settle and post the transaction. Payment-relevant flows, such as costs, are paid according to your payment process.

###### Subscription Rights

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Subscription Rights | L5 | trm05 p.167 | loio `8718da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8718da531198434de10000000a174cb4.html?locale=en-US)

Definition

Subscription rights grant the stockholder the option of retaining the old share of capital stock when the company performs capital increases (against cash contributions and certain capital increases). For subscription rights, the 030 Subscription Right product category is available, for which you can define your own product type in Customizing. You only require subscription rights for an (ordinary) capital increase.

**Structure**

You create a subscription right for a stock in the system as a class.

**Integration**

[figure TRM05-F061 - Overview: Capital Increase]

Overview: Capital Increase

You can use the following functions to perform the individual steps within this process:

|Function|Result|
|---|---|
|Enter class master data for the new stock and the subscription right. For more information, see also Manage Securities Classes app. |The new stock and the subscription right are created as security classes in the system. The subscription right appears in the Exercise Rights app under the right category Subscription Rights.|
|Create the position indicator for the new stock and the subscription right. For more information, see also Manage Position Indicator app. |The position indicators for the new stock and the subscription right are created.|
|Use the Manage Corporate Actions app to post the subscription rights. For more information, see also Corporate action. |The subscription rights that are issued from the old stocks are in the system available as position. The old stocks position is written down by an amount equal to the accounting value of the subscription rights, and the subscription rights position is posted.|
|Purchase/sell subscription rights, if required.|The required number of subscription rights is in the position.|


|Function|Result|
|---|---|
|For more information, see also Create Security Transaction. | |
|Exercise subscription rights For more information, see also Exercise Rights. |The subscription rights are exercised and the new stocks are obtained accordingly. The new stock is posted and the corresponding positions are available.|
|Transfer new stock If the new stocks are completely equal to the old stocks, you can transfer the new stocks to the old stocks. For more information, see also Corporate action. |During the transfer posting, the ID number of the old stock is determined automatically for the new stock. The position of new stocks is no longer available and the position of the old stocks is increased accordingly.|


**Note:**

The total value of a securities account position does not change as a result of the capital increase. The subscription rights that result from the capital increase simply shift the proportional share value.

The value of the subscription right for accounting purposes (account-based value) differs from the theoretical value if the book value of the old stock is lower than its current market value. In this case, you have to determine the accounting value of the subscription right by matching its theoretical value to the book value of the old stock.

The book value of the old stocks is, on the one hand, reduced by the amount of the accounting value of the subscription rights, and, on the other hand, the subscription right is posted to the position by the same amount. This means that the total value of the positions before and after the capital increase is the same.

The adjustment flows required for the book value markdown in the old stocks position are generated automatically.

Calculation of the Theoretical Value and the Account-Based Value of the Subscription Right

[figure TRM05-F062]

**Example**

|Case a) Book value of the old stock <= Market value of the old stock| |
|---|---|
|Book value of old stock|80 EUR|
|Market value - old stock|100 EUR|
|Purchase price - new stock|50 EUR|
|Dividend discrepancy - new stock|1 EUR|
|Subscription right ratio|1:1|
|Subscription ratio|1:1|
|Theoretical value of subscription right = (100 EUR - 50 EUR - 1 EUR) / (1 + 1) = 24.5 EUR| |
|Account-based value = 24.50 EUR * (80 / 100) = 19.60 EUR| |
|Case b) Book value of the old stock > Market value of the old stock| |
|Book value of old stock|80 EUR|
|Market value - old stock|70 EUR|
|Purchase price - new stock|50 EUR|
|Dividend discrepancy - new stock|1 EUR|


|Subscription right ratio|1:1|
|---|---|
|Subscription ratio|1:1|
|Theoretical value of subscription right = (70 EUR - 50 EUR - 1 EUR) / (1 + 1) = 9.50 EUR| |
|Account-based value = Theoretical value of subscription right = 9.50 EUR| |


**Related Information**

Manage Securities Classes Exercising Subscription Rights Exercise Rights Corporate Action

###### Shareholdings

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Shareholdings | L5 | trm05 p.171 | loio `f38c8b1eff144b0ca53979ea2457ad70` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f38c8b1eff144b0ca53979ea2457ad70.html?locale=en-US)

A shareholding represents a share in the equity capital of a company. In addition to other rights, the investors usually also receive a right of entitlement to profits, assets and liquidation proceeds. For shareholdings, the product category 160 Shareholding is available.

###### Investment Funds

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Investment Funds | L5 | trm05 p.171 | loio `b27362f9b1164f3f8328d031de5216c2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b27362f9b1164f3f8328d031de5216c2.html?locale=en-US)

An investment fund is a share in a fund that is managed by an investment trust. The owner of the share receives dividends but does not have other rights. For investment funds, the product category Investment Fund is available.

Dividend payments for investment funds differ as follows: Some investment funds communicate and pay out their dividends on a monthly or annual basis, whereas others communicate their dividends, for example, daily (= accrued dividend) but pay out the sum of the accrued dividends (= accumulated dividend) monthly. To reflect these different types of dividend payment for the product category Investment Fund, it is necessary to use conditions for dividends, accrued dividends, and accumulated dividends. The amounts for the dividend flows can be entered manually on the Conditions tab in the class data of the investment fund. Alternatively, you can enter the factor values in market data tables so that the dividend amounts can be calculated from there. For these factor-based dividends, a dividend adjustment condition is also needed. The factor values for investment funds with factorbased dividend conditions need to be entered in market data tables. The dividend amount is calculated by multiplying units by the dividend factor.

**Example: Money Market Funds**

Money market funds (MMFs) are a specific kind of investment fund that often have variable factor-based dividends. The dividends can be either calculated daily (accrued dividend) but paid monthly (accumulated dividend) or calculated and paid on a monthly basis.

MMFs are deemed an instrument with lower risk and higher liquidity, with a relatively lower return. MMFs are traditionally traded at a stable 1.00 currency unit. Depending on the rules and regulations in force, MMFs are required to declare their net asset value either as variable on a daily basis or as fixed for a period.

**Prerequisites**

Investment funds belong to the Securities area and are embedded in the securities process, which requires master data entries for securities class data and securities accounts. See also:

Master Data Entry in the Securities Area

Manage Securities Classes

Basic Data: Stocks/Shareholdings/Investments

Conditions for Investment Certificates

**Processing Investment Funds**

- 1. Purchase investment funds using the Create Securities Transaction app on the SAP Fiori launchpad or in the area menu of Treasury and Risk Management under Transaction Manager Securities Trading by calling either Create Financial Transaction (transaction FTR_CREATE) or Create Securities Transaction (transaction TS01).
- 2. Complete the financial transaction data using the Process Securities Transactions - Collective Processing app on the SAP Fiori launchpad or the corresponding function in the area menu under Transaction Manager Securities Trading/Back Office (transaction TS00) and using additional functions available for financial transactions, such as correspondence, netting, and references.


**Note:**

The process flow for entering the security transaction from the creation to the posting depends on the relevant processing category. The processing categories determine which activity categories a transaction passes through. You assign the processing categories at transaction type level in Customizing by choosing Define Transaction Types. You can choose from the following processing categories:

Processing category Order - Contract (00001)

Processing category Order - Contract - Settlement (00002)

For money market funds with variable NAV (product category 020 Investment Funds), two additional processing categories are available

Processing category Order - Contract - Contract Priced (00003)

Processing category Order - Contract - Settled - Contract Priced - CP Settled (00004)

These processing categories allow the payment of the purchase/sale amount even if the exact price and therefore the exact quantity is not known.

Example: Process of investment fund purchase with processing category 00004 Order - Contract - Settled Contract Priced - CP Settled

- a. Create the contract.

Enter the payment amount. The provisional price and quantity are determined using existing market data. Creation of the contract automatically triggers the creation of the business transactions Fund Order Payment and Purchase.

- b. Settle the contract.

When the contract is settled, the payment flow of the Fund Order Payment business transaction is flagged for posting.

- c. Execute the payment using the Post Flows app.
- d. Using the Fixing function, the exact price and quantity can be entered. The Fixing updates the purchase/sale quantity flow of the Purchase business transaction.
- e. Settle the priced contract.


The purchase flow that updates the treasury position with the exact values (with the Purchase business transaction) is now flagged for posting.

f. Open the Post Flows app.

The purchase flow that updates the treasury positions with the exact values (with the Purchase business transaction) is posted.

- 3. Fix, Pay and Post Flows

- 4. Enter current market data (such as factor values (Enter Factor Values), FX rates, or interest rates) on a regular basis in the market data tables.

- 5. The securities positions (= securities account positions) are managed using the security account management function, which offers the Update Planned Records function (transaction FWUP) and a function allowing you to post condition-based flows (dividends) and manual postings on the security account level (such as custodian fees).

For the posting of condition-based flows and manual entered flows:

Automatic Debit Position and Postings - Securities Accounts: You can use this function to fix the accrued dividend flows of investment funds.

Execute Debit Position - Manual Debit Position: You use this function to post profit distribution, accumulated dividends, and manually entered flows. This function enables you to capitalize the dividend flows and change payment details.

- 6. You can also use functions for period-end closing for the different valuation areas.

For more information, see Period-End Closing.

- 7. Reporting


**Note:**

Depending on the kind of dividend, accruals might be needed. You can use the Run Accrual/Deferral app or the corresponding function in the area menu (transaction TPM44) to accrue the profit distribution of money market funds with accrued dividends.

The information system provides a range of valuations of your security positions and position trends.

Debt and Investment Analysis

**Display Treasury Position Flows**

Display Treasury Position Values

Treasury Position Analysis

**Display Treasury Posting Journal**

**Customizing**

Before you can create securities classes for investment funds and purchase investment funds, you need to perform all Customizing activities for the product types for investment funds.

In the following, not all necessary settings are mentioned; instead, specific information relevant for investment funds is provided.

Under Treasury and Risk Management Transaction Manager Securities Master Data Product Types , you find the following Customizing activities:

Define Condition Types

Define the condition types you need for the kinds of investment fund you want to buy:

Condition type for dividends (using the FiMa calculation category TD)

Condition type for accrued dividends (using the FiMa calculation category TD)

Condition type for accumulated dividends (using the FiMa calculation category PSUM)

Condition type for dividend adjustment (using FiMa calculation category ZA) referencing the dividend / accrued dividend condition type

Define Conditions Groups (such as one for common investment funds and one for money market funds) and Assign Condition Types to Condition Groups.

Define Product Types (such as one for common investment funds and one for money market funds).

**Note:**

You can make the required settings for the accrual/deferral function if you would like the accrued dividend to be visible in the P&L statement.

Under Transaction Management Transaction Types , define the transaction types you need.

Also define the required flow types and update types including posting instructions. For example, set the update types for the dividend and the accumulated dividend as relevant for posting but not the accrued dividend.

Make the required settings for the position management of securities (such as the settings in the Define and Assign Differentiations function) and for account determination.

The Customizing activity Define Factor Types is available under Treasury and Risk Management Basic Functions Market Data Management Master Data Securities .

The Customizing activity Enter Factor Values is available under Treasury and Risk Management Basic Functions

Market Data Management Manual Market Data Entry Securities, Indices, and Factors . Here you can enter the factor values. In addition, you can call the Enter Factor Values function (transaction TMDFACTORVAL) in the area menu under Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry

Securities, Indices, and Factors . Alternatively, on the SAP Fiori launchpad in the Market Data Management group, you can use Enter Factor Values app or upload the values from a spreadsheet using the Import Market Data app.

**Related Information**

Securities Master Data Entry in the Securities Area Basic Data: Stocks/Shareholdings/Investments Conditions for Investment Certificates Securities Account Create Security Transaction Process Security Transactions - Collective Processing Enter Factor Values Securities Account Management Automatic Debit Position (Automatic Posting) Manual Debit Position (Incoming Payments) Accrual/Deferral of Expenses and Revenues Editing Security Prices Manually Run Valuation

Manage Securities Classes

###### Example: Money Market Funds

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Investment Funds > Example: Money Market Funds | L6 | trm05 p.175 | loio `bfca1c5ce7734513b2f2b38cf88ea0d4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bfca1c5ce7734513b2f2b38cf88ea0d4.html?locale=en-US)

Money market funds are a specific kind of investment certificate often with variable factor-based dividends. The dividends can be either calculated daily (accrued dividend) but paid monthly (accumulated dividend) or calculated and paid in a monthly rhythm.

Money market funds (MMF) are deemed an instrument with lower risk and higher liquidity, with a relatively low return. MMFs are traditionally traded at a stable 1.00 currency unit. Depending on the rules and regulations, MMFs are required to declare their net asset value either as variable on a daily basis or fixed for a period.

You can create the securities classes for MMFs using the Manage Securities Classes app. For more information, see also Manage Securities Classes.

For ordinary MMFs, you use a product type (for product category Investment Certificates) with a dividend condition and dividend adjustment condition. The profit distribution applied is based on the condition you have defined in the class data. If you use variable profit distribution instead of a fixed amount, the dividend adjustment is used to calculate the dividend amount (units * factor value).

For MMFs that declare the earned profit at a frequency that is different from the actual profit distribution, you use another product type with accrued dividend, accumulated dividend, and dividend adjustment condition. For example, a company declares their profit from MMFs on a daily basis on their website, but makes such distributions on a monthly basis.

You use the Create Securities Transaction app to create a purchase or sale transaction and update the position in the system.

**Note:**

If you want to sell MMFs, you can first review the position of the security class in the security account using the Display Securities Account Class Positions app. The securities position on hand must be greater than or equal to the position to be sold. In this case, you can then create and process the transactions in the system.

You use the Process Security Transactions - Collective Processing app to settle the purchases or sales of investment fund shares.

For factor-based dividend conditions, you need to enter the dividend factor values in order to calculate the amounts of dividends. In detail, the published factor for MMFs determines for a period (normally one day) the accrued dividend or daily dividend of an MMF.

If you determine expenses and revenues from financial transactions or positions daily for a given period and assign them to the correct accounting period, irrespective of when they were actually due, you can use the Run Accrual / Deferral app to accrue the distribution of profits from MMFs with an accrued dividend.

To capitalize the dividend/accumulated dividend to increase the units, you use the Execute Debit Position - Manual Debit Position app. To post the accrued dividends, you can use the Automatic Debit Position and Posting - Security Accounts app.

###### Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Bonds | L5 | trm05 p.175 | loio `c13117c856e24a089551132919eec845` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c13117c856e24a089551132919eec845.html?locale=en-US)

Bonds are interest-bearing securities that guarantee the payment of interests and the repayment at the end of term. You can create the class data for bonds using product category 040 (Bonds). In addition, specific product categories are available, such as, 042 Installment Bond, 060 Warrant Bond, and 070 Convertible Bond. You can create different kinds of bond by defining class data and the conditions accordingly:

Fixed-interest bonds

Floating-rate notes

Zero-coupon bonds

You can manage the following processes for bonds:

Issuing Bonds

Investing in Bonds

These processes cover master data management, the trading and processing of securities transactions (including the placement and redemption of issued bonds), as well as paying and posting in Financial Accounting. In addition, various functions for managing security positions and for period-end closing are available. Treasury Reporting provides you with a broad range of apps for analyzing your debts and investments in bonds.

###### Issuing Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Bonds > Issuing Bonds | L6 | trm05 p.176 | loio `0eacc7531dc61d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0eacc7531dc61d4be10000000a174cb4.html?locale=en-US)

This process covers master data management, the placement and redemption of bonds issued, as well as paying and posting in Financial Accounting. In addition, various functions for managing the securities account positions and for period-end closing are available. Treasury Reporting provides you with a broad range of apps for analyzing your debts and investments in bonds.

**Process**

After you have decided to issue a bond, the following steps are available for bond issues.

- 1. Create the class data for your bond using your product type for issuing bonds. You can create different kinds of bonds, such as bonds with a fixed interest rate, floating-rate notes, or zero-coupon bonds.
- 2. Create an issuance securities account.

You can handle positions for securities issues in issuance securities accounts only. The system makes sure that issue positions cannot be transferred to asset securities accounts. It also ensures that asset positions are not transferred to an issuance securities account.

For more information, see also: Manage Securities Accounts

- 3. Specify the position indicator. For more information, see also: Manage Position Indicator

- 4. Create the placement of the bond issue using the Create Security Transaction app.

- 5. Settle and post the placement transaction. Payment-relevant flows, such as costs, are paid according to your payment process.
- 6. You can also post the issuance cost using the Create Manual Posting app. Depending on your payment process, payment requests have been created and processed.

- 7. During the term of the bond, the following functions are available:


**Note:**

You can use securities accounts for multiple issues. You use the securities account to determine standard information, such as payment methods, and to generate the cash flow.

Period-end closing

Update security prices and FX rates in the market data table.

Accrual/Deferral of Expenses and Revenues

Run Valuation

Update variable interest flows at fixing date:

Update interest rates in the market data table.

Planned Record Update

Post and pay interest flows at coupon due date:

Manual Debit Position (Incoming Payments)

Depending on your payment process, payment requests have been created and processed.

Unscheduled redemption

Create the redemption transaction using transaction type 400 (Bond Issue: Redemption) in the Create Security Transaction app.

Settle and post the redemption transaction. Payment-relevant flows, such as costs, are paid according to your payment process.

In the last year of the bond term, you can execute a valuation class transfer to transfer the position of the bond from the long-term valuation class to the short-term valuation class.

For more information, see also Execute Valuation Class Transfer

At the end of the term, post and pay the scheduled repayment flow:

Manual Debit Position (Incoming Payments)

Depending on your payment process, payment requests have been created and processed.

**Tip:**

You can assign interest rate derivatives that have already been created (swap, cap, floor) to the issue positions. You use the reference ID ICH to make this assignment. You can use this reference to display both the bond issue and the interest rate hedges in the Issue Hedge report.

The following transactions are also available for bond issues:

Issue Position (transaction TIS50)

Issue Volumes (transaction S_AEN_10000987)

Issue Charges (transaction S_AEN_10000988)

Issue Hedge (transaction S_AEN_10000989)

###### Investing in Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Bonds > Investing in Bonds | L6 | trm05 p.177 | loio `1fe1f78fca344439a1cc7c58a637e31f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1fe1f78fca344439a1cc7c58a637e31f.html?locale=en-US)

This process covers master data management, the purchase and sale of bonds, as well as making payments and postings in Financial Accounting. In addition, various functions for managing securities account positions and for period-end closing are available. Treasury Reporting provides you with a broad range of apps for analyzing your debts and investments in bonds.

**Investment in Bonds**

- 1. Create the class data for your bond using the product type for bonds, Bonds.


- 2. Create an asset securities account.

In securities accounts of this type, all positions can be managed except for issue positions.

For more information, see also: Manage Securities Accounts

- 3. Specify the position indicator. For more information, see also: Manage Position Indicator

- 4. Purchase a bond by creating a securities transaction with transaction type 100 (Bond Investment: Purchase) using the Create Security Transaction app.

- 5. Settle and post the transaction. For payment-relevant flows, payment requests are created and paid according to your payment process.
- 6. You can also post additional costs, such as securities account fees, using the Create Manual Posting app. Depending on your payment process, payment requests are created and processed accordingly.

- 7. During the term of the bond, the following functions are available:


Period-end closing

Update security prices and FX rates in the market data table.

Accrual/Deferral of Expenses and Revenues

Run Valuation

Update variable interest flows at fixing date:

Update interest rates in the market data table.

Planned Record Update

Post interest flows at coupon due date:

You can use either the Manual Debit Position (Incoming Payments) app or the Automatic Debit Position (Automatic Posting) app.

Sale of bonds before maturity

Create the sale transaction for the bond using transaction type 200 (Bond Investment: Sale) in the Create Security Transaction app.

Settle and post the transaction. Payment-relevant flows, such as costs, are paid according to your payment process.

In the last year of the bond term, you can execute a valuation class transfer to transfer the position of the bond from the long-term valuation class to the short-term valuation class.

For more information, see also Execute Valuation Class Transfer

At the end of term, post the scheduled repayment flow:

You can use either the Manual Debit Position (Incoming Payments) app or the Automatic Debit Position (Automatic Posting) app.

###### Warrants

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Bonds > Warrants | L6 | trm05 p.178 | loio `8418da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8418da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

Warrants grant the owner of the warrant the right to purchase currency amounts (currency warrants) , bonds (bond warrants), or stocks (equity warrants) at predetermined conditions within a certain period (or on a certain key date).

A special type of warrant is the index warrant, which speculates on rising or sinking prices and is settled in cash only , not in the purchase of securities.

Warrants can be either traded on their own or purchased together with a bond (bond warrant).

**Integration**

To enter data for warrants, the following product categories are available:

|Product Category|Name|
|---|---|
|111|Index Warrant|
|112|Equity Warrant|
|113|Currency Warrant|
|114|Bond Warrant|


**Note:**

To create the respective product types, go to Customizing for the Transaction Manager and choose Securities Master Data Product Types Define Product Types .

You create warrants as a class in the system. They can be purchased and sold using the transaction management functions.

When security rights are exercised, warrants are separated from warrant bonds. The system enters the exercised or expired warrants.

For more information, see also:

Warrant Bonds

Exercise Rights

Manage Securities Classes

###### Warrant Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Bonds > Warrants > Warrant Bonds | L7 | trm05 p.179 | loio `c117da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c117da531198434de10000000a174cb4.html?locale=en-US)

Definition

Warrant bonds are bonds to which one or several warrants are assigned. Warrant bonds are either traded cum (with a warrant) or ex (without a warrant).

You can exercise the corresponding warrant during the option period and trade it separately from the bond.

**Note:**

You can use the product category 060(Warrant Bond) to map warrant bonds in the standard system. To define a product type, go to Customizing for the Transaction Manager and choose Securities Master Data Product Types

Define Product Types .


You create the cum warrant bond, the corresponding warrant, and the ex warrant bond as classes. When you create a cum warrant bond, you need to have already defined the classes of the warrant and the ex warrant bond.

You can separate a warrant from the cum warrant bond and exercise a warrant or execute the expiration of the warrant. To do this, go to the SAP Easy Access screen and choose Treasury and Risk Management Transaction Manager

Securities Trading Security Right Exercise (transaction FWER). When you detach a warrant from the cum warrant bond, the warrant is then posted. At the same time, the positions of the cum warrant bond are transferred to the positions of the ex warrant bond.

See also:

Manage Securities Classes

Warrants

###### Convertible Bonds (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Bonds > Convertible Bonds | L6 | trm05 p.180 | loio `991ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/991ada531198434de10000000a174cb4.html?locale=en-US)

Definition

Convertible bonds are bonds that can be converted to stocks under specific conditions within a certain period.

**Note:**

To map convertible bonds in the system, you can use the default product category Convertible Bonds (70). To define a product type, go to Customizing for the Transaction Manager and choose Securities Master Data Product Types

Define Product Types .


You create convertible bonds as classes in the system. Make sure that the stock to which the bond is to be converted already exists as a class.

To convert positions or partial positions of a bond, go to the SAP Easy Access screen and choose Treasury and Risk Management Transaction Manager Securities Trading Security Right Exercise (transaction FWER).

**Related Information**

Manage Securities Classes

###### Asset-Backed Securities and Mortgage-Backed Securities

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities | L5 | trm05 p.180 | loio `950f6551c939d51be10000000a445394` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/950f6551c939d51be10000000a445394.html?locale=en-US)

**Use**

Asset-backed securities (ABS) and mortgage-backed securities (MBS) are securities for which payments are hedged with an asset pool. In the case of ABS, the asset pool contains receivables, whereas, in the case of MBS, the asset pool contains receivables hedged by a mortgage. ABS and MBS are generally securities repaid by installments that may change depending on how the borrows pay back the underlying loans, for example.

**Features**

Portray ABS/MBS with installments calculated using the linear calculation method.

This method assumes that the repayments are made in linear fashion and calculates the future repayment flows accordingly.

Portray ABS/MBS with installments calculated using the CPR or PSA calculation method.

This method calculates the future repayment flows on the basis of statistical parameters (such as CPR/PSA values) that you receive from your data supplier, whereby this data can change repeatedly during the term of the security.

CPR Value

The CPR value specifies the probable amount of the monthly advance repayment. The value is determined using the historic market data for similar loans. The CPR value is quoted in percent.

PSA Value

The PSA model assumes that the amount of the advance repayments of loans increases over the first 30 months before becoming constant thereafter.

You can either create ABS/MBS using the single interest condition or parallel interest condition.

ABS/MBS using the single interest condition

Since it can be the case with ABS/MBS that the issuer retrospectively makes changes to repayments that have already been made, such changes can also be portrayed.

See also:

ABS/MBS: Retrospective Changes to Repayments

It is possible to portray a period without repayments at the start of the term.

You can portray interest capitalization by also allowing factor increases for a tranche in Customizing.

To simplify entering interest flows and repayment flows, you have the option of copying the dates from the interest condition and applying them for the repayment flows (using the Int.Cond.Template indicator). For each interest flow, the system creates a corresponding repayment flow with the following dates:

Effective date of the repayment = (changed) calculation date of the interest flow

The effective date of the repayment flow is the start date of the next month in which the interest calculation date falls on the month-end date (since repayments are published on the first day of the month).

Payment date of the repayment = due date of the interest flow

If you do not want to use the interest condition as a template, you have to make the settings for the repayment condition (such as the payment frequency) separately.

You need to enter or regularly update the class data either manually using the activity Create/Change Class (transaction FWZZ) or using the following BAPIs:

BUS1076 FinancialProduct

BUS1074 RedemptionSchedSet

BUS1064 Create and Change RedemptionFactors.

**Note:**

You can also portray ABS/MBS emissions. (See also:Bond Issue).

The system does not allow you to portray the securitization of the underlying receivables.

You can also use the position management functions for loans with installment repayment from SAP Loans Management.

ABS/MBS using the parallel interest condition

You can invest in asset-backed/mortgage-backed securities (product category 042 Installment Bond) using parallel interest conditions. When activating parallel interest conditions, the cash flow is calculated by the new financial mathematics (FiMa) calculation engine, supporting risk-free interest rates.

It is possible to portray a period without repayments at the start of the term.

You can portray interest capitalization by also allowing factor increases for a tranche in configuration.

For each tranche category, you must specify the relevant payment amount calculation method in Customizing. The following methods are available:

Zero Payment Amount

Equal to Change in Nominal

Using Fraction of Issued Nominal (Fixed)

Using Fraction of Issued Nominal (Variable)

To simplify the entry of the redemption schedule, you can copy the dates from a condition and apply them to the repayment flows by selecting the corresponding condition in the Redemption Template field.

The repayment schedule is versioned.

**Caution:**

The system does not allow you to portray the securitization of the underlying receivables.

Issue of ABS/MBS is not supported.

A to-be-announced (TBA) trade for ABS/MBS is not supported.

**Prerequisites**

You need to set up the product types for ABS/MBS in Customizing. See also:ABS/MBS: Customizing

Create the security class data for the ABS/MBS using the Manage Securities Classes app.

**Related Information**

Investing in Asset-Backed Securities and Mortgage-Backed Securities

###### Investing in Asset-Backed Securities and Mortgage-Backed Securities

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities > Investing in Asset-Backed Securities and Mortgage-Backed Securities | L6 | trm05 p.182 | loio `f2b16df8be2447098c0ca4a82a5e780b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f2b16df8be2447098c0ca4a82a5e780b.html?locale=en-US)

The process covers master data management, the purchase and sale of ABS/MBS, as well as paying and posting in Financial Accounting. In addition, various functions for managing securities account positions and for period-end closing are available. Treasury Reporting provides you with a broad range of apps for analyzing your debts and investments in bonds.

Investment in ABS/MBS

- 1. Create the class data for your ABS/MBS using product type 04M Asset/Mortg.-Backed Securities. You can create ABS/MBS with a fixed interest conditions or variable interest condition (including variable interest conditions based on risk-free rates). Enter the calculation parameters for ABS/MBS relevant for the redemption schedule, and the first redemption schedule version.

During the lifetime of the ABS/MBS, you must regularly update the class data of the ABS/MBS using the Manage Securities Classes app, for example, when a redemption factor is published.

For more information, see also Manage Securities Classes

- 2. Create an asset securities account.

In securities accounts of this type, all positions can be managed except for issue positions.

For more information, see also: Manage Securities Accounts

- 3. Specify the position indicator. For more information, see also: Manage Position Indicator

- 4. Purchase an ABS/MBS by creating a securities transaction with transaction type 100 Purchase using the Create Security Transaction app.

- 5. Settle and post the transaction. For the payment-relevant flows, payment requests are created and paid according to your payment process.
- 6. You can also post additional costs, such as securities account fees, using the Create Manual Posting app. Depending on your payment process, payment requests have been created and are processed accordingly.

- 7. During the term of the ABS/MBS, the following functions are available:


**Note:**

When you enter a transaction, enter the original nominal (nominal without existing installment repayments). The system uses the class data to calculate the nominal. You can change this nominal without any restrictions.

Period-end closing

Update security prices and FX rates in the market data table.

Accrual/Deferral of Expenses and Revenues

Run Valuation

Update variable interest flows at fixing date:

Update interest rates in the market data table.

Planned Record Update

Update the redemption schedule in class data.

Post interest flows and repayment flows at due date:

You can use either the Manual Debit Position (Incoming Payments) app or the Automatic Debit Position (Automatic Posting) app, or schedule a background job using the Post Debit Position job template.

The system uses the information in the active redemption schedule version to create the flows for the installment repayment.

Sale of ABS/MBS before maturity

Create the sale transaction for the bond using transaction type 200 Sale in Create Security Transaction app.

Settle and post the transaction. Payment-relevant flows, such as costs, are paid according to your payment process.

In the last year of the ABS/MBS term, you can execute a valuation class transfer to transfer the position of the bond from the long-term valuation class to the short-term valuation class.

For more information, see also Execute Valuation Class Transfer

At the end of term, post the last scheduled repayment flow:

You can use either the Manual Debit Position (Incoming Payments) app or the Automatic Debit Position (Automatic Posting) app.

###### ABS/MBS: Customizing

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities > ABS/MBS: Customizing | L6 | trm05 p.184 | loio `cee74b521dd16b67e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cee74b521dd16b67e10000000a441470.html?locale=en-US)

SAP recommends to create different product types for ABS/MBS with single interest conditions and ABS/MBS with parallel interest conditions.

**Customizing for ABS/MBS with Single Interest Conditions**

Under Transaction Manager Securities Master Data Product Types Condition Types , first make the settings for the required product types:

Define Condition Types - Securities and Define Condition Groups

Required condition types

100 Interest (quoted in percent)

118 Repayment Rate

260 ABS/MBS Installment Repayment

263 Final Repayment

Define a condition group for ABS/MBS bonds and then assign the above condition types to this condition group.

Define Product Types - Securities

With the standard settings, the system portrays ABS and MBS with product category 042.

Create at least one product type for your ABS/MBS bonds with single interest conditions.

In the activity Assign Repayment Types to Product Types, you assign the repayment type 2 Installment to the product types for ABS/MBS.

In the activity Define Security Tranche, create tranche classifications. You can define default tranche classifications (Tranche Type: Default) and other tranche classifications that only allow interest payments (Tranche Type: IOInterest Only).

Indicator:

If you set the Allow Factor Increase indicator for a tranche classification, this allows the nominal value of the bond to increase for this tranche during the term of the security. If you do not set this indicator, only a continual reduction of the nominal value is possible.

Allow Retrospective Adjustment of Redemptions

See also:ABS/MBS: Retrospective Changes to Factors

Apply Workday Adjustment After Calendar Day Shift

Force First Redemption on First Redemption Date

See also: Date Determination Options for Interest Flows and Repayment Flows

In the activity Activate Special Conditions for ABS/MBS, you have to activate this function for product types that you want to use together with the CPR/PSA method. When you activate this function for product types, the CPR/PSA repayment conditions become available for entry of the class data (transaction FWZZ) for those product types.

Further, the function of using interest as a condition template for repayments is activated for all calculation methods, as is the option of entering interest in the redemption schedule.

We therefore recommend that you set the activation indicator for all of your ABS/MBS product types.

Under Transaction Manager Securities Position Management Securities Account Management , you make the settings for the update types for Securities Account Management in the following Customizing activities:

Define Update Types and Assign Usages

Update type SAM1180 Amortization at Update End, assignment to usage Securities Account Management

This update type is required for the change in redemption schedule. For the date preceding the effective date of the new redemption schedule, the system creates the business transaction End of Fixed Period on which amortization occurs. The previous redemption schedule is used for cash flow determination for the last time. This ensures that only one redemption schedule is valid within an amortization period.

If you want to use the function Retrospective Changes to Repayments, you need to create the following update types and assign them to the usage Securities Account Management:

SAM1180A: Inflow: Retrospective Change to Factor

SAM1180S: Outflow: Retrospective Change to Factor

SAM1180+: Adjusted Incoming Interest

SAM1180-: Adjusted Outgoing Interest

Specify Update Types for Securities Account Management

We recommend that, for the update type for installment repayments, you set the Use Calculation Date as Position Date and Generate Debit Position Flow indicators.

You also need to set the Use Calculation Date as Position Date indicator for interest update types. See also:Date Determination Options for Interest Flows and Repayment Flows

Update Type SAM1180

For amortization at update end, you need to assign classification Period End (Redemption Schedule/Termination Date) to update type SAM1180.

In the activity Set the Effects of the Update Types on the Position Components, assign Position Change Category1006 (indirect position change) to the update type.

SAM1180A: Inflow: Retrospective Change to Factor

Calculation category: AA

Relevant to Calculation

+/- sign: -

Classification: Period End (Redemption Schedule/Termination)

SAM1180S: Outflow: Retrospective Change to Factor

Calculation category: SS

Relevant to Calculation

+/- sign: +

Classification: Period End (Redemption Schedule/Termination)

SAM1180+: Adjusted Incoming Interest

Calculation category: NOOP

Direction: Incoming

Classification: Period End (Redemption Schedule/Termination)

SAM1180-: Adjusted Outgoing Interest

Calculation category: NOOP

Direction: Outgoing

Classification: Period End (Redemption Schedule/Termination)

In the following Customizing activities, make the transaction management settings for these product types:

Define Transaction Types

Define Flow Types

Assign Flow Types to Transaction Type

Define Update Types and Assign Usages

Assign Flow Types to Update Types

Assign General Valuation Class

You also make the Position Management settings in Customizing for Treasury and Risk Management under Transaction Manager General Settings Accounting Settings for Position Management .

In the position management procedure for your ABS/MBS positions, you need to use position management category 8Securities/Loans w/ Install. Repayt (w/o index-linked bonds). However, you can also use position management category 1Sec./Loans/M.Mkt/List.Opts Norm.Style.(w/o index-link.bonds) (see also: SAP Note 1666075 ).

Amortization is generally performed for position changes (purchases, sales, and transfer postings) and key date valuations. In the amortization procedure for the ABS/MBS, set the Amort. for Install. Repayment and Adjustment of Translation Flows checkboxes.

Due to changed expectations regarding future installment payments, cash flows can change. You can take such changes into account in the amortization procedure by using the following settings in the Treat.EffIntRate (SAC) field:

Adjust Effective Interest Rate Immediately (Standard)

Constant Effective Interest Rate (for reporting in accordance with IAS)

Retrospective (for reporting in accordance with US GAAP)

Make the necessary settings in the activity Define Account Determination.

**Note:**

Depending on how you have made your settings in Customizing, you may need to complete other Customizing activities, such

- as account assignment reference determination. As a rule, you need to add any new product types to any settings that you have


made dependent on the product type. Further, anywhere where you want to have alternative settings for the new product types, you also need to make these alternative settings.

**Customizing for ABS/MBS with Parallel Interest Conditions**

Configuration Activities

|Configuration Activity|Description|Details|
|---|---|---|
|Define Condition Types - Securities / Define Condition Groups|Define the relevant condition types. Define a condition group for ABS/MBS bonds and then assign the condition types to this condition group.|Required condition types 100 Interest (quoted in percent) 118 Repayment Rate 260 ABS/MBS Installment Repayment Define a condition group for ABS/MBS bonds and then assign the above condition types to this condition group.|
|Define Product Types - Sceurities|Create a product type for the ABS/MBS with parallel interest conditions with product category 042.|In the following Customizing activities, make the transaction management settings for these product types: Define Transaction Types Define Flow Types Assign Flow Types to Transaction Type Define Update Types and Assign Usages Assign Flow Types to Update Types Assign General Valuation Class|
|Assign Repayment Types to Product Types|Assign the repayment type 2 Installment to the product types for ABS/MBS.| |
|Specify Update Types for Securities Account Management| |We recommend that, for the update type for installment repayments, you set the Use Calculation Date as Position Date and Generate Debit Position Flow indicators. You also need to set the Use Calculation Date as Position Date indicator for interest update types. See also:Date Determination Options for Interest Flows and Repayment Flows |
|Define Security Tranche|Create tranche classifications.|The tranche classifications are only relevant for product types of the product category 042 Installment Bond. You assign the tranche classification to the class data of an|


|Configuration Activity|Description|Details|
|---|---|---|
| | |ABS/MBS security on the Basic Data tab in the Manage Securities Classes app. In the tranche classification, you make the following settings: You can set the Allow Factor Increase indicator. If you set the Allow Factor Increase indicator for a tranche classification, this allows the nominal value of the bond to increase during the term of the security. If you do not set this indicator, only a continual reduction of the nominal value is possible. You must choose the payment calculation method. The payment calculation method determines how the payment amount of a redemption flow is calculated. The following methods are relevant for ABS/MBS with parallel interest conditions: Zero Payment Amount In this case, the value in the principal payment field is always set to zero. You cannot change the calculated principal payment amount. Equal to Change in Nominal In this case, the value in the principal payment field is equal to the change in nominal. The change in nominal is calculated to ensure that original nominal * current face factor = current nominal is satisfied. **Note:** If you choose this setting, you must take care to post the repayments with other flows.|


|Configuration Activity|Description|Details|
|---|---|---|
| | |You cannot change the calculated principal payment amount. Using Fraction of Issued Nominal (Fixed) The payment amount for the redemption in a position is calculated by multiplying the ratio of the original position nominals to the total of the issued nominal by the total repayment amount of the redemption schedule. This can differ from the nominal change due to different rounding results. You cannot change the calculated principal payment amount. Using Fraction of Issued Nominal (Variable) The payment amount for the redemption in a position is calculated by multiplying the ratio of the original position nominals to the total of the issued nominal by the total repayment amount of the redemption schedule. This can differ from the nominal change due to different rounding results. You can manually change the calculated principal payment amount after the values have been calculated by the system. **Note:** If no payment calculation method is assigned, the system interprets this as if the value N Equal to Nominal Change were entered.|
|Classify Asset Pool|Define classifications for asset pools.|You only need asset pool classifications for product types of the product category 042 Installment Bond. You assign a asset pool classification to the class data on the Asset Pool Data tab in the Manage Securities Classes app.|


|Configuration Activity|Description|Details|
|---|---|---|
|Define Partner Ranks|Define ranks for your business partners.|The rank contains information about the task of the business partner in connection with asset-backed/mortgage-backed security.|
|Activate Special Conditions for ABS/MBS|Activate the special conditions for ABS/MBS.|You must activate this function for product types that you want to use together with the CPR/PSA method. When you activate this function for product types, the CPR/PSA repayment conditions become available for entry of the class data (transaction FWZZ) for those product types.|
|Define Update Types and Assign Usages| |We recommend that, for the update type for installment repayments, you set the Use Calculation Date as Position Date and Generate Debit Position Flow indicators. You also need to set the Use Calculation Date as Position Date indicator for interest update types. See also:Date Determination Options for Interest Flows and Repayment Flows Update type SAM1180 Amortization at Update End, assignment to usage Securities Account Management This update type is required for the change in redemption schedule. For the date preceding the effective date of the new redemption schedule, the system creates the business transaction End of Fixed Period on which amortization occurs. The previous redemption schedule is used for cash flow determination for the last time. This ensures that only one redemption schedule is valid within an amortization period.|
|Define Position Management Procedure|Define a position management procedure for your ABS/MBS positions|In the position management procedure for your ABS/MBS positions, you need to use position management category 8Securities/Loans w/ Install. Repayt (w/o index-linked bonds). However, you can also use position management category 1Sec./Loans/M.Mkt/List.Opts Norm.Style.(w/o index-link.bonds) (see also: SAP Note 1666075 ). |


|Configuration Activity|Description|Details|
|---|---|---|
|Define Amortization Procedure|Define an amortization procedure for your ABS/MBS positions|Amortization is generally performed for position changes (purchases, sales, and transfer postings) and key date valuations. In the amortization procedure for the ABS/MBS, set the Amort. for Install. Repayment and Adjustment of Translation Flows checkboxes. Due to changed expectations regarding future installment payments, cash flows can change. You can take such changes into account in the amortization procedure by using the following settings in the Treat.EffIntRate (SAC) field: Adjust Effective Interest Rate Immediately (Standard) Constant Effective Interest Rate (for reporting in accordance with IAS) Retrospective (for reporting in accordance with US GAAP)|
|Define Account Determination.|Make the necessary settings.| |

###### Redemption Schedules

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities > Redemption Schedules | L6 | trm05 p.191 | loio `0c18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0c18da531198434de10000000a174cb4.html?locale=en-US)

The following functions are available for processing redemption schedules and redemption schedules sets:

List of Redemption Schedule Sets

Delete Redemption Schedules

Delete Redemption Schedule Sets

###### Redemption Schedule Set (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities > Redemption Schedules > Redemption Schedule Set | L7 | trm05 p.192 | loio `aa1ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aa1ada531198434de10000000a174cb4.html?locale=en-US)

Definition

A redemption schedule set (RS set) contains a group of redemption schedules for a particular class. In conjunction with the ID number, the redemption schedule set identifies a specific set of redemption schedules.

**Note:**

Only relevant for ABS/MBS with single interest conditions.

**Structure**

Repayment schedule sets are uniquely identified by their key and the ID number of the class.

They consist of header data and the assigned redemption schedules.

Key header data of a redemption schedule set:

Date of first redemption

Date of last redemption

Redemption frequency

**Integration**

You assign the redemption schedule sets to the individual bonds in the class data on the Conditions tab. You enter the header data when you create the first redemption schedule for a particular class.

You can assign various redemption schedule sets to a class. If you assign only one RS set to a class, this automatically becomes the active RS set. If more than one redemption schedule set exists, you can choose which of them is to be the active set.

The cash flow for the class shows the planned records for the redemption flows. These are taken from the data for the active redemption schedule in the active redemption schedule set.

Once you have created the header data for a redemption schedule set, you can enter one or more redemption schedules.

###### Delete Redemption Schedules

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities > Redemption Schedules > Delete Redemption Schedules | L7 | trm05 p.193 | loio `f417da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f417da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to delete redemption schedules you no longer require.

**Features**

Selection

|General Selections| |
|---|---|
|ID number| |
|Product type| |
|Redemption schedule set| |
|Redemption schedule set class| |


|Redemption Schedule Data| |
|---|---|
|Effective from| |
|Entered on| |
|Entered by| |
|Last edited on| |
|Last changed by| |
|Redemption schedule| |
|First redemption date| |
|Redemption schedule file| |
|No. of redemptions| |


Output

|Output Control| |
|---|---|
|Test run|If you set this indicator, the system only performs a test run, and no redemption schedules are deleted.|
|Display redemption schedules|If this indicator is set, the display log contains all the selected redemption schedules that were deleted in the update run. This field is set as a default.|
|Layout|If you have saved a layout, you can select it in this field. The list is then structured in the way you want from the outset.|


**Activities**

- 1. Call up the function and enter selection criteria to ensure that the system only selects the redemption schedules you want to delete.
- 2. First carry out a test run.

- a. a. Do this by setting the Test Run indicator.
- b. b. Also make sure that the Display Redemption Schedules indicator is set.
- c. c. If you want to use your own display variant, choose the required layout.
- d. d. Execute the report.

The log tells you the number of redemption schedules selected. These are shown in the list.

- e. e. Check the redemption schedules selected.


If these are the correct redemption schedules, you can now start the update run. If the list contains redemption schedules that you do not want to delete, check your selection conditions. When you have corrected the selection conditions, carry out another test run.

- 3. Deactivate the Test Run indicator and perform the update run.
- 4. The system deletes the selected redemption schedules.

###### Delete Redemption Schedule Sets

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities > Redemption Schedules > Delete Redemption Schedule Sets | L7 | trm05 p.195 | loio `bb18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bb18da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to delete redemption schedule sets you no longer require

**Prerequisites**

You must delete the redemption schedules belonging to the redemption schedule sets first.

See also: Delete Redemption Schedules

**Features**

Selection

|General Selections| |
|---|---|
|ID number| |
|Product type| |
|Redemption schedule set| |
|Redemption schedule set class| |
|Additional Data| |
|First redemption| |
|Last redemption date| |
|Frequency| |
|Period indicator for expiration date| |


Output

|Output Control| |
|---|---|
|Test run|If you set this indicator, the system only performs a test run, and no redemption schedule sets are deleted.|
|Display redemption schedule sets|If this indicator is set, the display log contains all the selected redemption schedules sets that were deleted in the update run. This field is set as a default.|
|Layout|If you have saved a layout, you can select it in this field. The list is then structured in the way you want from the outset.|


**Activities**

- 1. Call up the function and enter selection criteria to ensure that the system only selects the redemption schedule sets you want to delete.


- 2. First carry out a test run.

- a. a. Do this by setting the Test Run indicator.
- b. b. Also make sure that the Display RS sets indicator is active.
- c. c. If you want to use your own display variant, choose the required layout.
- d. d. Execute the report.

The log tells you the number of redemption schedule sets selected. These are shown in the list.

- e. e. Check the redemption schedule sets selected.


If these are the correct redemption schedule sets, you can now start the update run. If the list contains redemption schedule sets that you do not want to delete, check your selection conditions. When you have corrected the selection conditions, carry out another test run.

- 3. Deactivate the Test Run indicator and perform the update run.
- 4. The system deletes the selected redemption schedule sets.

###### Display Redemption Schedule Sets

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Asset-Backed Securities and Mortgage-Backed Securities > Redemption Schedules > Display Redemption Schedule Sets | L7 | trm05 p.196 | loio `0b17da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0b17da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this report to display a list of the redemption schedule sets in the system that match your selection criteria.

You can branch from the list to the redemption schedules within each of these sets.

**Features**

Selection

SecurityClass ID No.

Redemption Sched. Set

RS Set Class

Additional Data

First redemption date

Last redemption date

Cycle

Period Indicator

Output Control

Display Sets indicator

This indicator is set as a default. If you leave it set, the system displays the redemption schedule sets in the list.

**Note:**

If you deactivate the indicator, the system only displays the number of redemption schedule sets found.

Layout

You can specify a layout to have the list displayed in the form you prefer.

Output

The list is displayed using the SAP List Viewer.

From the list display, you can call up the following functions:

Display Sets

You can use this pushbutton to branch to the overview of redemption schedule sets for a particular class. Display Class Data

You can use this pushbutton to display the class data.

You can then branch from the Conditions tab page to the overview of redemption schedule sets, where you can process the redemption schedule sets and the corresponding redemption schedules.

###### Security Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Security Transaction | L5 | trm05 p.197 | loio `cf18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cf18da531198434de10000000a174cb4.html?locale=en-US)

**Use**

A security transaction is the purchase or sale of securities (classes), representing a position inflow or outflow.

A security transaction usually passes through the following steps: Getting a quotation, concluding the transaction, and then posting the transaction. These steps are represented in the system by the various activity categories and processing categories a transaction can have.

Activity Categories

Activity category: Order (based on a quotation)

Activity category: Order Expiration (if the transaction is not concluded)

Activity category: Contract (if the transaction is concluded)

Activity category: Contract Priced (only available for processing categories 0003 and 0004)

Activity category: Settlement (this activity category can only be reached for processing category 00002)

Activity category: CP Settled (only available for processing categories 0003 and 0004)

Processing Categories

The processing categories determine which activity categories a transaction passes through. You assign the processing categories

- at transaction type level in Customizing by choosing Define Transaction Types. You can choose from the following processing categories:


Processing category Order - Contract (00001)

Processing category Order - Contract - Settlement (00002)

For money market funds with variable NAV (product category 020 Investment Funds), two additional processing categories are available

Processing category Order - Contract - Contract Priced (00003)

Processing category Order - Contract - Settled - Contract Priced - CP Settled (00004)

The processing categories allow the payment of the purchase/sale amount even if the exact price and therefore the exact quantity is not known.

Activity Chains

[figure TRM05-F065]

Overview: Overview: Possible Activity Chains for Each Processing Category

[figure TRM05-F066 - Overview: Overview: Possible Activity Chains for Each Processing Category]

When the last activity category in the chain has been saved, the transaction flows are assigned the status Flagged for posting. Choose Transaction Post [transaction TBB1] in the Accounting section of the application menu to trigger the update to the general ledger in the operative valuation area (if release is required for posting, the transaction must be released first). After you have executed the posting function, the transaction flows are assigned the status Posted, and are converted from planned records into actual records.

For the parallel valuation areas,you post using either the function Execute Posting mentioned above and/or the function under Accounting Transaction Fix, Post, or Reverse Business Transactions [transaction TPM10]. This is dependent on

two things: if you posted only the operative valuation area when you posted the transaction using transaction TBB1, or if you also posted to the parallel valuation areas; the settings you made in Customizing for Derived Business Transactions.

Posting Status

|Posting Status|Comments|
|---|---|
|Blocked for Posting|This status is assigned to the transaction flows in the following cases:|


|Posting Status|Comments|
|---|---|
| |The transaction activity is not relevant for posting. The Relevant for posting activity is the last activity in the activity chain. When you use processing category 00001, the activity relevant for posting is the Contract, and with processing category 00002, it is the Settlement. The transaction has reached the activity that is relevant for posting, but the activity has not yet been saved. Instead, it has been put on hold ( Security Transaction Hold ). The transaction flows still have planned records status, and the transaction can still be changed.|
|Flagged for Posting|If the transaction has reached the activity that is relevant for posting and has been saved, it is assigned the posting status Flagged for posting. The transaction can no longer be changed.|
|Posted|If the flows have been updated to the general ledger by the posting function, the flows are assigned the status Posted and are converted from planned records to actual records (in other words, fixed).|
|Flagged for Reversal|If you reverse a transaction that has posted flows using the Transaction Reverse function, the flows are assigned the status Flagged for reversal.|
|Reversed|If the flows that were reversed have been updated to the general ledger using the Accounting Transaction Reverse Documents function, the flows are assigned the status Reversed.|


**Integration**

The transaction management functions are in the Trading and Back Office areas of the application menu. The functions were divided between these two areas to reflect the organizational segregation of trading and back office activities.

In the trading area, you can create, change, and display security transactions, and execute security orders.

In the back office area, you can change, display and settle security transactions.

The settings you make for transactions in Customizing determine the effect they have on Cash Management.

[figure TRM05-F067 - Example: Integration of Securities Management and Cash Management]

Example: Integration of Securities Management and Cash Management

**Prerequisites**

You have to make the following Customizing settings before you can enter transactions:

Enter a number range (01) for the transactions for each company code in the securities area by choosing Define Transaction NumberRanges. The system uses this number range to assign a transaction number when you create a transaction.

Define Transaction Types

Specify the transaction types required for purchases and sales for each product type.

Flow Types (Transaction)

Create the transaction flow types for transaction management (in the Customizing activity: Define Flow Types for Transaction).

Assign the required flow types to each transaction type. You must include all the flow types needed to process a transaction. (Customizing activity: Assign Flow Types to Transaction Type).

**Example:**

Transaction type for purchasing a fixed-interest bond:

Purchase flow type

Flow type for accrued interest

Tax flow types that you may want to generate using a derivation procedure

Flow types for additional charges that may need to be entered

You can define rules for generating flows automatically (such as tax flows) in the IMG activity Define Derivation Procedures and Rules.

Make the settings for internal and external confirmation letters in the Correspondence section. You define the possible correspondence types in the IMG activity Define Correspondence Types, and specify which documents to want to generate for each transaction type and activity category in the step Define Correspondence Activities.

Define the relevant update types and assign them to the corresponding transaction types in the Update Types section:

Define Update Types and Assign Usages

Assign Transaction Flow Types to Update Types

If you use the parallel valuation areas, you must also make account determination settings for the update types.

You define the account determination for the update types in Customizing under Transaction Manager General Settings Accounting Link to Other Accounting Components Define Account Determination .

You must have created general valuation classes in Customizing for Transaction Manager. Choose Genral Settings Accounting Settings for Position Management Define and Assign Valuation Classes .

A general valuation class must be assigned to each transaction. To simplify transaction entry, you can define default values for the general valuation class assignment. In Customizing choose Securities Transaction Management Assign General Valuation Class .

You can also make settings in the following IMG activities:

By choosing Define Field Selection in Customizing for the basic functions area, you can set up the entry screens for transactions in different ways.

Define Order Limit Checks

Define Reservation Reasons

**Features**

Cash flow display

Once a transaction has reached the activity category Contract, the transaction cash flow displays the flows that result from the transaction.

Correspondence

A correspondence function is available. It enables you to generate letters of confirmation. Depending on the settings you make in Customizing, you can generate correspondence either when you conclude a contract, or when you settle it.

See also: Correspondence

Release

You can set up the system in such a way that transactions can only be posted after they have been checked by one or more other employees.

Input help for transaction entry

**Activities**

For more information on processing security transactions, see Editing a Security Transaction.

###### Editing a Security Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Security Transaction > Editing a Security Transaction | L6 | trm05 p.202 | loio `d416da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d416da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The Security Transaction unit provides an overview of the transaction management functions in the Transaction Manager. It explains central terms for transaction management and describes the process flows, while also giving you an overview of the Customizing settings involved.

The following section contains information about the prerequisites that must be fulfilled in the application before you can create a security transaction. It also provides an overview of the functions that are available for processing financial transactions.

**Prerequisites**

You must have entered the following master data before you can begin entering securities purchases and sales in transaction management:

Business partner master data for the counterparty.

Class master data for securities you wish to purchase

For more information, see Manage Securities Classes.

Securities account master data

Position indicators (You can have the position indicators determined automatically from the transaction, or you can create them manually.)

Overview: Prerequisites

[figure TRM05-F068]

**Procedure**

|Function|Entries|Remarks|
|---|---|---|
|Create|For more information, see: Creating a Security Order/Contract| |
|Change|For more information, see: Changing a Security Transaction| |
|Execute|For more information, see: Executing a Security Order|The function for executing an order transfers a security transaction from the Order activity to the Contract activity. You can add missing details and change the order data to reflect the actual transaction data. If you assigned processing category 00001 to the transaction type, the transaction is assigned the posting status Flagged for posting when you save it, and you can no longer change the data.|
|Settle|Choose Back Office Transaction Settle . For more information, see:|When you settle a transaction, you check the security transaction and add any missing data. When you save the|


| |Settling a Security Transaction|transaction, the transaction flows are assigned the status Flagged for posting. You can change the posting status of the security transaction to Blocked for posting by choosing Hold.|
|---|---|---|
|Fixing|1. Choose Back Office Edit Financial Transaction (transaction FTR_EDIT). 2. Enter the company code and the transaction number and choose Fixing. |Fixing allows you to enter the exact price and quantity for money market security transactions that are priced after payment. You can adjust the number of units and price per unit in this step. You then need to settle the contract before posting it.|
|Display|Choose Trading Transaction Display or Back Office Transaction Display   . Enter the company code and the transaction number. The system displays the data for the current activity category of the transaction.| |
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.| |
|Expiration|Choose Trading Transaction Expiration .|If the order requirements are not fulfilled, the order expires. You can represent this activity in the system using the Expiration of Security Order function.|


| | |Once you have executed the function, the Order activity becomes an Order Expiration activity.|
|---|---|---|
|Display history|Choose Trading Transaction Display History or Back Office Transaction Display History .|The history displays the sequence of previous activities related to a selected transaction.|

###### Accrued Interest

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Security Transaction > Editing a Security Transaction > Accrued Interest | L7 | trm05 p.205 | loio `786f9d9c4ba74559adf42e62d1584166` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/786f9d9c4ba74559adf42e62d1584166.html?locale=en-US)

**Example of Accrued Interest Calculation**

A bond usually has interest coupons with which the bond issuer pays interest at predetermined dates to the current bond holder. See the graphic below for an example. After the start of the interest period, the bond is sold on a given trade date from the former bond holder X to the new bond holder Y. At the end of the interest period, the full interest coupon P is paid to the new bond holder Y. However, the new bond holder Y has to pay the former bond holder X the interest amount A as accrued interest. The interest amount A corresponds to the time t1 between the start of the interest period and the trade date. The accrued interest payment forms part of the purchase/sale transaction.

The formula for calculating accrued interest (A) is the time percentage of the full interest coupon (P). This is expressed as follows:

A = P x t1 / (t1+ t2)

[figure TRM05-F071 - Calculation of Accrued Interest]

Calculation of Accrued Interest

###### Changing a Security Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Security Transaction > Editing a Security Transaction > Changing a Security Transaction | L7 | trm05 p.206 | loio `d818da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d818da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to change the current data of a security transaction if the transaction flows still have the Blocked for posting status . When you have made your changes, the security transaction stays in the activity as before.

**Example:**

If the current activity of the transaction you want to change is order , you can only transfer it to the contract activity using the Executing a Security Order function.

**Procedure**

- 1. Choose Trading Transaction ChangeorBack office Transaction Change .
- 2. Enter the Company code and the Transaction number of the transaction you want to change.
- 3. Choose (ENTER).
- 4. Enter the data you want to change.

- Structure
- Administration
- Trading Data
- Editing Other Flows for the Transaction
- Payment Details
- Cash Flow for the Transaction
- Memos
- Status


- 5. Choose Position cash flows (in the upper part of the screen) to display the cash flows for the securities account, including the transaction currently being processed. See also : Cash Flow

- 6. Save your entries.

###### Executing a Security Order

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Security Transaction > Editing a Security Transaction > Executing a Security Order | L7 | trm05 p.206 | loio `f018da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f018da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to transfer an Order activity into a Contract activity.

At this point, you can change the data in the order you have already created, or add any missing entries. You may have to adjust the security price you entered when you created the order to the market price prevailing when you executed it, for example.

**Procedure**

- 1. Choose Trading Transaction Execute.


- 2. Enter the company code and the transaction number.
- 3. Choose (ENTER).


- 4. You can change the order data and add any missing details.

- Structure
- Administration
- Trading Data
- Editing Other Flows for the Transaction
- Payment Details
- Cash Flow for the Transaction
- Memos
- Status


- 5. Choose Position cash flows (in the upper part of the screen) to display the position cash flows for the securities account in the various valuation areas, including the transaction currently being processed.


See also : Cash Flow

- 6. Save your entries.


If the contract was the last activity in the activity chain (processing category 00001) , the transaction is fixed (the flows become actual flows in the Treasury subledger). The flows are now Flagged for posting, and can be transferred to Financial Accounting using the Post Transaction function.

- 7. As long as the activity is not relevant for posting, you can change it using the Change Security Transaction function.


**Result**

The Order activity becomes a Contract activity.

###### Collective Processing: Forward securities transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Security Transaction > Collective Processing: Forward securities transaction | L6 | trm05 p.207 | loio `440cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/440cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The collective processing function makes it easier for you to manage your forward securities transactions effectively by displaying a list of selected transactions and providing the necessary processing functions.

The list enables you to:

Call processing functions for forward securities transactions

Use functions from the work list

Set Processing Indicator

The list is displayed using the SAP List Viewer meaning that you can use the standard functions provided here.

**Key Features**

Selections

You can use the following criteria to restrict the financial transactions that are provided later in the work list.

**Note:**

You need to select at least one activity category.

All other entries are optional.

Transaction Category

Purchase

Sale

Purchase and Sale are set as the default entries.

Current Activity Category

Contract

Contract Settlement

Rollover

Rollover Settlement

**Advance Maturity**

Advance Settlement

Dividend Adjustment

Corporate Action

Delivery

General Selections

Company Code

Transaction

Product Type

Financial Transaction Type

Business Partner

ID Number

Securities Account

Trader

Portfolio

External Reference

Data

Position Value Date

If there are multiple position value dates, the system finds the earliest date.

Term Start

Term End

The start and end of term are saved at the level of the activity.

Additional Fields

Assignment

Internal Reference

Characteristics

Entered/last changed by

User

Date

Output Control

Layout

The list is displayed using the SAP List Viewer. You can specify a layout.

Secondary index number

Output

You can display the worklist using the SAP List Viewer, meaning that you can use the standard functions provided here.

The columns in the list show the transaction data: The first column displays the processing indicators if you have edited a transaction from the list. You can also set the indicators manually.

You can branch from the list to the following processing functions:

|Function|Comments|
|---|---|
|Create|Creating a Forward Securities Transaction|
|Change| |
|Settle| |
|Roll Over|See also: Rollover of a Forward Securities Transaction|
|Advance Maturity|See also: Advance Maturity|
|Adjust Dividends|See also: Adjust Dividends|


|Function|Comments|
|---|---|
|Deliver|See also: Delivering a Forward Securities Transaction|
|Display| |
|Reverse|See also: Reversal|
|History|The history function lists all previous activities for the transaction. You can identify the active status and all previous statuses. The system also displays the Entered by and Changed by fields as well as the Entered on and Changed on dates. You can branch to the relevant activities using the Activity pushbutton.|
|Status Management| |
|Refresh| |
|Posting Release| |
|Set Processing Indicator| |
|Detailed Information| |


**Activities**

- 1. Call the function by choosing Transaction Manager Derivatives Back Office Processing Collective Processing Forward Securities Transactions .
- 2. Enter your selection criteria.
- 3. Choose Execute.
- 4. The system displays the collective processing list, which displays all the selected forward securities transactions.
- 5. Select the transaction that you want to process.
- 6. Execute the function you want to use.
- 7. Process other transactions or exit Collective Processing.


See also:

Forward Securities Transactions

###### Collective Processing: Securities Lending

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Securities > Security Transaction > Collective Processing: Securities Lending | L6 | trm05 p.210 | loio `1315da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1315da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function if you want to manage and edit multiple lending transactions at the same time. You can select lending transactions according to your own criteria and display them in a list along with a short summary. You can also branch from the processing list to the individual transactions to edit them or to display detailed information.

For more information, see Securities Lending

**Features**

The following single transactions functions are available:

Create Securities Lending

Change Securities Lending

Display Securities Lending

Roll Over Securities Lending

Give Notice on Securities Lending

Reverse Securities Lending

Securities Lending: Display History

Posting Release

**Activities**

Carry out the following steps to execute Collective Processing: Securities Lending.

- 1. Choose Trading Collective Processing Securities Lendingor Back Office Collective Processing.
- 2. Enter your selection criteria.
- 3. Choose Execute. The selected transactions are listed.
- 4. By double-clicking on a transaction, the Display Securities Lending: Structure screen appears , where you will find detailed information for the selected transaction.


Carry out the following steps to edit individual transactions from the generated list:

- 1. Select the row of the transaction to be edited.
- 2. Choose a processing function in the function list.
- 3. Make the relevant changes and save your entries.


Note: After leaving the editing screen you are automatically taken to the list in Collective Processing.

##### Trade Finance (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance | L4 | trm01 p.11 | loio `e07cc955c3be037ce10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e07cc955c3be037ce10000000a44147b.html?locale=en-US)

Provides you with specific financial transactions from banks and financial institutions to facilitate local and international trading. Regardless of whether you are the exporter or importer, you can map your processes for processing bank guarantees, letters of credit, and standby letters of credit.

**Integration**

The Trade Finance area is a subcomponent of the Transaction Manager and is closely integrated with other components.

You can implement cash management decisions in the Trade Finance area based on the liquidity surplus or deficit determined in Cash Management. The system records the impact that transactions have on the liquidity of a company by value date, for each flow in Cash Management. To do this, the data from Trade Finance is transferred to Cash Management automatically. This integration simplifies the work processes involved in transaction management from entering potential transactions through to the related accounting activities. The Trade Finance area comprises the functions for foreign currency valuation to calculate gains and losses.

It is also closely linked to the Financial Accounting (FI) component since all data that is relevant for posting in the Trade Finance area is automatically transferred to FI.

You can maintain current market data (exchange rates) in various ways:

Manually

Using a market data file interface: You maintain the relevant data in an external application (such as Microsoft Excel), either manually or via a data provider, and then import the data into the system in a format compatible with SAP.

By transferring the market data to the system from a spreadsheet

Datafeed: You can use the datafeed connection to make real-time market data available in the system.

To access the market data management functions in the application menu, choose Treasury and Risk Management Basic Functions Market Data Management .

To access the Trade Finance area, on the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Trade Finance .

**Features**

Trading

The Trading area contains functions for entering trade finance transactions. It also enables you to call up information on transactions or make changes at a later date. Collective processing functions are available to help you manage your transactions efficiently.

The product categories in the Trade Finance area include:

Letters of Credit

Bank Guarantee

Back Office

Once you have entered financial transactions in the Trading area, you settle them in the Back Office area, which also contains functions for checking and changing the transactions. Transaction postprocessing primarily involves:

Adding any missing transaction data that is needed to process the transaction further

Preparing for posting and payment (for example, by checking the accounts used)

The collective processing functions are also available in the Back Office area.

Accounting

Once you have entered the transactions in the Trading area and checked them and added any missing details in the Back Office area, you then need to process them for accounting purposes. The Accounting area includes functions for transferring data to Financial Accounting, such as posting reports or position management postings. It also includes functions for parallel valuation.

Master Data Management

Financial transaction processing in the Transaction Manager is based on master data.

Information System

The Information System provides a range of reports for analyzing your trade finance transactions. The Trade Finance Information System is part of the Transaction Manager Information System, which offers analyses and evaluations across the whole of the Treasury and Risk Management dataset.

###### Letters of Credit

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Letters of Credit | L5 | trm05 p.213 | loio `57dcca5501cf1d22e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/57dcca5501cf1d22e10000000a44147b.html?locale=en-US)

**Use**

A letter of credit is a document issued by a bank guaranteeing that a beneficiary will receive payment provided that certain documents have been presented to the bank as required.

Letter of credit transactions include transaction types for issuing and receiving letters of credit.

The banks (or business partners) charge additional fees based on the principal amount of a letter of credit in the issuing and receiving process and based on certain conditions. The fee calculation process takes place during all stages of the letter of credit lifecycle. The fee calculation is based on four condition types for different amounts.

For more information, see Calculating Fee Flows for Letters of Credit

In addition to creating and changing letters of credit, the system also supports functions for rollover, reversal, termination, order expiration, order execution, and presentation of documents.

**Prerequisites**

Before you can use the letter of credit transactions, you need to do the following:

Create your business partners, assign the corresponding roles to these partners and maintain the transaction authorizations.

Set up the standing instructions (correspondence, payment details) and release the business partner.

Make the required Customizing settings. For more information, see Customizing Settings for Trade Finance.

**Features**

For more detailed information, see Creating Letters of Credit, Processing Letters of Credit as an Importer,Processing Letters of Credit as an Exporter, and Calculating Fee Flows for Letters of Credit.

###### Processing Letters of Credit as an Exporter

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Letters of Credit > Processing Letters of Credit as an Exporter | L6 | trm05 p.213 | loio `503803565ae8692de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/503803565ae8692de10000000a4450e5.html?locale=en-US)

**Prerequisites**

For more information, see Letters of Credit.

**Process**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Trade Finance Trading/Back Office . From here, you can access all the trading and processing functions for letters of credit (L/C).

- 1. Create L/C contract.

After the advising bank informs the exporter of the L/C from the importer, you create a L/C contract in the system and enter all the information.

For more information on creating letters of credit, see Creating Letters of Credit.

- 2. Settle or reverse L/C contract.

If there is no problem with the L/C, you settle the L/C contract.

Otherwise, you return the L/C and reverse the L/C contract.

- 3. Create L/C presentation.

After the goods were shipped as negotiated, you create a presentation against the L/C and uploads documents as required.

For more information, see also Presentation of Documents Against Letters of Credit

- 4. Optional.

Precheck L/C presentation.

Before presenting the documents, you can check the presentation details and documents with the bank in advance.

- 5. Send L/C presentation to bank.

If all the required documents are ready, you send the presentation to the bank.

- 6. Accept L/C presentation.

After a presentation is accepted by the importer, you accept the presentation in the system.

- 7. Optional.

Create export bills negotiation.

For an accepted presentation, you can create export bills negotiation or link the presentation to an existing export bills negotiation.

- 8. Optional.

Roll over the L/C.

In case the shipment of goods or payment cannot be settled within the planned time frame, you need to negotiate with the bank and importer to adjust the L/C amount or term. You roll over the L/C, and change the L/C amount or end of term.

After reaching an agreement with the exporter on the adjustment, and negotiating with the issuing bank, you settle the rollover contract.

- 9. Optional.


**Note:**

If accepted presentations exist, the changed amount should not be less than the total accepted presentation amount.

Use the rollover function to shorten the term of the letter of credit

Open the Process Trade Finance Transactions - Collective Processing app and search for your letter of credit. Select the letter of credit from the list and choose Roll Over. Enter the rollover date and the new end date. You can move the end date of the letter of credit to an earlier date if the following prerequisites are fulfilled:

The letter of credit contains at least one presentation item.

The new end date is on or after the rollover date.

The new end date is on or after the shipping period end date.

The new end date is on or after the shipping date of all presentation items.

The new end date is on or after the presentation date of all presentation items.

There are no posted flows after the new end date.

If you save your entries the system accepts the new end date, moves the date of the business transaction to the new end date, and moves the flows to the new end date.

- 10. Optional.

Terminate L/C.

You terminate a L/C in the following scenarios:

You find that the total amount of an L/C has been paid and wants to terminate this L/C.

You find that one L/C has expired and wants to terminate this L/C.

Although one L/C has not been paid completely, you want to terminate this L/C after reaching an agreement with the importer that this L/C will not be paid any more.

- 11. Settle L/C presentation.


After the payment for a presentation is settled, you settle the presentation.

**Note:**

After a presentation is settled, no data can be changed anymore. However, if you find some mistakes later on, you can reverse the settled presentation. After reversal, the presentation becomes an accepted presentation.

**Note:**

You can reverse your action until the activity cannot be reversed anymore.

###### Processing Letters of Credit as an Importer

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Letters of Credit > Processing Letters of Credit as an Importer | L6 | trm05 p.215 | loio `92240256a0876d55e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/92240256a0876d55e10000000a4450e5.html?locale=en-US)

**Prerequisites**

For more information, see Letters of Credit.

**Process**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Trade Finance Trading/Back Office . From here, you can access all the trading and processing functions for letters of credit (letter of credit).

1. Create letter of credit order.

After the Trader reaches an agreement with the business partner regarding whether letter of credit is to be used as the settlement method, you create a letter of credit order in the system to request the letter of credit to be issued. You can also create a letter of credit contract directly.

For more information on creating letters of credit, see Creating Letters of Credit.

- 2. Execute or reverse letter of credit order.

After receiving the request for a letter of credit to be issued, you go through the letter of credit details. If the request is approved, you execute the order and ask the issuing bank to issue the letter of credit. After execution, the order becomes a contract. Otherwise, you reverse the order.

- 3. Settle or reverse letter of credit contract.

If the issuing bank approves the application for the letter of credit, you enter all the letter of credit information, such as the letter of credit number, and then settle the letter of credit contract.

Otherwise, you reverse the letter of credit contract and provide a reversal reason. Then, the letter of credit is in Order activity. After that, the Trader can either adjust the letter of credit and reopen the application process or close the application by order expiration.

- 4. Accept or reject a presentation.

After the exporter presents documents against the letter of credit, you create a presentation, and accept, reject, or accept and settle the presentation.

For more information, see also Presentation of Documents Against Letters of Credit

- 5. Optional.

Create import bill advance loan.

For an accepted presentation, you can create an import bill advance loan or link the presentation to an existing import bill advance loan.

- 6. Optional.

Roll over letter of credit.

In case the shipment of goods or payment cannot be settled within the planned time frame, you need to negotiate with the bank and exporter to adjust the letter of credit amount or term. You roll over the letter of credit, and changes the letter of credit amount or end of term.

After reaching an agreement with the exporter on the adjustment, and negotiating with the issuing bank, you settle the rollover contract.

- 7. Optional.


**Note:**

If accepted presentations exist, the changed amount should not be less than the total accepted presentation amount.

Use the rollover function to shorten the term of the letter of credit

Open the Process Trade Finance Transactions - Collective Processing app and search for your letter of credit. Select the letter of credit from the list and choose Roll Over. Enter the rollover date and the new end date. You can move the end date of the letter of credit to an earlier date if the following prerequisites are fulfilled:

The letter of credit contains at least one presentation item.

The new end date is on or after the rollover date.

The new end date is on or after the shipping period end date.

The new end date is on or after the shipping date of all presentation items.

The new end date is on or after the presentation date of all presentation items.

There are no posted flows after the new end date.

If you save your entries the system accepts the new end date, moves the date of the business transaction to the new end date, and moves the flows to the new end date.

- 8. Optional.

Terminate letter of credit.

You terminate a letter of credit in the following scenarios:

You find that the total amount of a letter of credit has been paid and wants to terminate this letter of credit.

You find that one letter of credit has expired and want to terminate this letter of credit.

Although one letter of credit has not been paid completely, you want to terminate this letter of credit after reaching an agreement with the exporter that this letter of credit will not be paid any more.

- 9. Settle letter of credit presentation.


After the payment for a presentation is settled, you settle the presentation.

**Note:**

After a presentation is settled, no data can be changed anymore. However, if you find some mistakes later on, you can reverse the settled presentation. After reversal, the presentation becomes an accepted presentation.

###### Presentation of Documents Against Letters of Credit

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Letters of Credit > Presentation of Documents Against Letters of Credit | L6 | trm05 p.217 | loio `50d8ff5503de8809e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/50d8ff5503de8809e10000000a441470.html?locale=en-US)

**Use**

In transactions where letter of credit is used for payment of goods or services, the seller needs to present certain documents to a bank to get payment after the goods or service has been delivered. The buyer may accept or reject a presentation after checking whether the presented documents meet the conditions of the letter of credit.

**Presentation Management**

You can manage the whole process of presenting documents against letters of credit.

For issuing letters of credit, you can

Create a presentation after receipt

Accept a presentation

Reject a presentation

Settle a presentation

Accept and settle a presentation

For receiving letters of credit, you can

Create a presentation for preparation

Precheck a presentation by sending the presentation details and documents to a presentation bank

Record the status of a presentation by accepting, rejecting, settling, or accepting and settling a presentation

Adjust the nominal amount of the letter of credit during the presentation process.

Open the Process Trade Finance Transactions - Collective Processing app and search for your letter of credit. Select the letter of credit from the list and choose Present. Enter a new presentation. Enter the presentation data, such as Presentation Amount, Shipping Date, and Presentation Date. To adjust the nominal amount of the letter of credit and also the presentation amount, enter the net charges amount and the correponding flow type in the fields Flow Type Charges and Net Charges Amount.

The system calculates the net presentation amount. In addition, to the net charges amount also an entered amount in the DecreaseForDiscre field is taken in to account.

The same date fields as for the existing net presentation amount are used for the nominal reduction flow.

**Financing Transactions for Accepted Presentations**

You can create financing transactions for accepted presentations, or link accepted presentations to existing financing transactions.

For issuing letters of credit, you can create an import bill advance loan or link the presentation to an import bill advance loan.

For receiving letters of credit, you can create an export bills negotiation or link the presentation to an export bills negotiation.

When you choose to create the financing transaction directly, you need to fill required information of the transaction. After the financing transaction is created, the generated transaction is displayed with its Transaction ID, and the reference relationship between the financing transaction and the current transaction is generated automatically.

You can also create a financing transaction with Product Type 55A and Transaction Type 200 in advance and then link the accepted presentation to the existing financing transaction. After that, the reference relationship between the financing transaction and the accepted presentation is generated automatically.

###### Calculating Fees for Letters of Credit

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Letters of Credit > Calculating Fees for Letters of Credit | L6 | trm05 p.218 | loio `ac5d3758e2eba107e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ac5d3758e2eba107e10000000a441470.html?locale=en-US)

**Use**

For trade finance transactions such as letters of credit and bank guarantees, a certain amount of fees are charged by the business partner during the issuing or receiving process and based on certain conditions, such as a payment rate. The fee calculation process takes place during all stages of the letter of credit lifecycle. The fee calculation for letters of credit is based on four condition types for different amounts.

You can create and maintain the fee conditions for letters of credit (L/C) using transactions Create Financial Transaction (transaction FTR_CREATE) or Edit Financial Transaction (transaction FTR_EDIT).

**Prerequisites**

Before you can calculate the fees for letter of credit transactions, you need to make the necessary Customizing settings. For more information, see Customizing Settings for Trade Finance

**Procedure**

- 1. Issue a letter of credit using transaction Create Financial Transaction (transaction FTR_CREATE). For detailed information, see Creating Letters of Credit.

- 2. Enter the required data for the letter of credit on the Create Letter of Credit: Structure tab. For more information, see Basic Data - Trade Finance.

- 3. Choose Fee Conditions to switch to the fee condition overview.
- 4. Choose Create Fee Conditions in the Overview of Conditions.
- 5. Choose a possible condition type from the list in the Possible Condition Types dialog box.
- 6. Enter the required data on the Amounts tab on the Condition Details screen.

If the fee is a fixed value, specify the condition amount on the Currency-Related Data block.

You can choose between two types of calculation method for the amount of the condition type:

- a. A percentage rate.
- b. A fixed amount for the total contract period.


This amount, however, ,is split per payment period.

If the fee is calculated based on one of the four condition types listed below, specify the percentage rate and the interest calculation method.

In this field, you specify which interest calculation method is used. The input help provides definitions of each method. (You can choose from standard interest calculation methods such as act/360, 360/360, act/365, act/366, or 365/360.)

Specify the rounding category, rounding unit, and base unit.

- 7. If the fees are paid or calculated on a regular basis, enter a calculation date and a due date on the Dates tab.


**Example:**

You pay 1200 EUR as a fee for the total amount of the L/C for a one-year contract, but the fee is paid on a monthly basis. This means that you pay a monthly fee of 100 EUR.

|Condition Type|Name of Condition Type|Description|
|---|---|---|
|1204|Fee on Total Amount|Calculated based on the total amount of the L/C|
|1205|Fee on Presented Amount|Calculated based on the total amount of the presentation|
|1206|Fee on Available Amount|Calculated based on the remaining credit amount|
|1207|Fee on Overdraft Amount|Calculated based on the over-utilized amount|


**Features**

The fee cash flows corresponding to the specific fee condition are updated when the following data is changed:

Change of total amount

There are two possible changes to the total amount:

You change the amount value directly on the Structure tab.

However, this change cannot be made if any L/C cash flows based on the total amount have already been posted.

You change the amount of the nominal increase or decrease in the dialog box.

This change cannot be made if it affects any cash flows that have already been posted.

The fee cash flows are updated automatically based on the new total amount if the total amount of the L/C is changed before the L/C has been posted.

**Example:**

A company applies to issue an L/C from January 1, 2016 to June 30, 2016 with a total amount of 1 M EUR. The fee condition is calculated with a percentage rate of 1.2% and an interest calculation method of 30/360, and it is paid monthly. Once the amount is posted, the fee cash flows are as follows:

|Date|Fee Amount|
|---|---|
|1/31/2016|1000|
|2/28/2016|1000|
|3/31/2016|1000|
|4/30/2016|1000|
|5/31/2016|1000|
|6/30/2016|1000|


If the end user increases the total amount of the L/C to 2 M EUR by adding a new nominal fee on April 1, 2016, the new fee cash flows are then as follows:

|Date|Fee Amount|
|---|---|
|1/31/2016|1000|
|2/28/2016|1000|
|3/31/2016|1000|
|4/30/2016|2000|
|5/31/2016|2000|
|6/30/2016|2000|


Change of contract term

The fee cash flows are updated automatically based on the new contract term if the contract term of the L/C is changed.

You cannot change the contract term if it affects flows that have already been posted, such as moving the end date of the contract term to before the date of the posted flows.

Change of fee condition

The fee condition can be changed and the corresponding fee cash flows are automatically updated.

You cannot change the fee condition if it affects flows that have already been posted. This means that you cannot change the percentage rate because doing so would lead to the recalculation of the posted flows.

Presentation

Fee calculation is triggered during the presentation process and presentation settlement.

When the new presentation is created, the fee cash flows are automatically updated for the fee conditions with condition type Fee on Presented Amount, Fee on Available Amount, and Fee on Overdraft Amount.

When the presentation is saved or settled, the fee cash flows with a calculation due date later than the presentation date are automatically updated.

The presentation is usually not affected by a fee cash flow that has already been posted. An error message is issued if exceptions occur.

Rollover

If an L/C is rolled over, the update of the fee cash flow is automatically triggered and the fee is calculated up to the new end date of the L/C based on the assigned fee condition.

Termination

If the termination date is after the end date of the L/C, the fee cash flows are calculated up to the end date of the L/C.

If the termination date is before the end date of the L/C, an automatic update of the fee cash flows is triggered.

If the termination date lies in the middle of the period of the L/C, the fee cash flow is only calculated up to the termination date.

**Example:**

The monthly fees for the L/C are paid at the end of each month, but the termination date is August 15. The fee is therefore calculated up to and paid on August 15.

Reversal

If you reverse your L/C, the system changes the status of the flow and of the financial transaction.

A warning message is issued in cases when a financial transaction includes posted flows (fee flows and other cash flows) to indicate that some flows will be posted after the reversal has been performed.

**More Information**

Letters of Credit

###### Bank Guarantees

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Bank Guarantees | L5 | trm05 p.221 | loio `53880d5791c45d38e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/53880d5791c45d38e10000000a44147b.html?locale=en-US)

**Use**

A bank guarantee is a pledge on the part of a bank to make good someone's debt in the event that he or she cannot pay it. This type of guarantee is essentially an agreement to stand as a cosigner on a transaction. In the event that the original party cannot follow through, the bank can be called upon to provide the payment.

Bank Guarantee transactions include transaction types for issuing and receiving bank guarantees.

The banks (or business partners) charge additional fees based on the principal amount of a bank guarantee in the issuing and receiving process and based on certain conditions. Increases and decreases in the amount of the bank guarantee are reflected in the fees. The fee calculation process takes place during all stages of the bank guarantee lifecycle.

In addition to functions for creating and changing bank guarantees, the system also supports rollover, reversal, order expiration, order execution, contract settlement, contract termination, and termination settlement.

**Prerequisites**

Before you can use the bank guarantee transactions, you need to do the following:

Create your business partners, assign the corresponding roles to these partners and maintain the transaction authorizations.

Set up the standing instructions (correspondence, payment details) and release the business partner.

Make the required Customizing settings. For more information, see Customizing Settings for Trade Finance.

**Features**

For more detailed information, see Creating Bank Guarantees, Processing Bank Guarantees as an Importer,Processing Bank Guarantees as an Exporter, and Calculating Fee Flows for Bank Guarantees.

###### Processing Bank Guarantees as an Exporter

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Bank Guarantees > Processing Bank Guarantees as an Exporter | L6 | trm05 p.222 | loio `b18bfa56ac7d6d38e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b18bfa56ac7d6d38e10000000a44147b.html?locale=en-US)

**Prerequisites**

For more information, see Bank Guarantees.

**Process**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Trade Finance Trading/Back Office . From here, you can access all the trading and processing functions for Bank Guarantees.

- 1. Create Bank Guarantee contract.

After the bank informs the exporter that a bank guarantee is received from the importer, you create a bank guarantee contract in the system and enters all the information.

For more information on creating bank guarantees, see Creating Bank Guarantees.

- 2. Settle or reverse Bank Guarantee contract.


If everything is fine for the bank guarantee, you settle the bank guarantee contract in the system.

In case of any problems about the bank guarantee contract, you reverse the bank guarantee contract and provide a reversal reason. Then, the bank guarantee is in Contract activity with status Reversed.

In case the amount or validity term of the bank guarantee needs to be changed, you roll over the Bank Guarantee, and changes the bank guarantee amount and end of term.

b. Settle bank guarantee contract rollover.

After reaching an agreement with the importer on the adjustment, and negotiating with the issuing bank, you settle the contract rollover.

4. Optional.

- a. Terminate bank guarantee contract.

If the bank guarantee is not needed or the related duties have been performed, you terminate this bank guarantee and return the bank guarantee to the bank.

- b. Settle bank guarantee contract termination.


With joint consent of the importer and the exporter, you settle the bank guarantee contract termination.

###### Processing Bank Guarantees as an Importer

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Bank Guarantees > Processing Bank Guarantees as an Importer | L6 | trm05 p.223 | loio `758afa56ac7d6d38e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/758afa56ac7d6d38e10000000a44147b.html?locale=en-US)

**Prerequisites**

For more information, see Bank Guarantees.

**Process**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Trade Finance Trading/Back Office . From here, you can access all the trading and processing functions for Bank Guarantees.

- 1. Create bank guarantee order.

After the Trader reaches an agreement with the business partner regarding whether bank guarantee is needed, you create a bank guarantee order in the system to request the bank guarantee to be issued or you create a bank guarantee contract directly.

For more information on creating bank guarantees, see Creating Bank Guarantees.

- 2. Execute or reverse bank guarantee order.

After receiving the request for a Bank Guarantee to be issued, you go through the bank guarantee details. If the request is approved, you execute the order and ask the issuing bank to issue the bank guarantee. After execution, the order becomes a contract. Otherwise, you reverse the order.

- 3. Settle or reverse bank guarantee contract.


If the issuing bank approves the application for the bank guarantee, you enter all the bank guarantee information, such as the bank guarantee number, and then settle the bank guarantee contract.

Otherwise, you reverse the bank guarantee contract and provides a reversal reason. Then, the bank guarantee is in Order activity. After that,you can either adjust the bank guarantee and reopen the application process or close the application by order expiration.

In case the amount or validity term of the bank guarantee needs to be changed, you need to negotiate with the bank and the exporter to adjust the bank guarantee amount or term. Then you roll over the bank guarantee, and change the bank guarantee amount or end of term.

b. Settle bank guarantee contract rollover.

After reaching an agreement with the exporter on the adjustment, and negotiating with the issuing bank, you settle the contract rollover.

- 5. Optional.

- a. Terminate bank guarantee contract.

If the bank gives a notification that one bank guarantee is not needed, you terminate this bank guarantee, and the consumed credit line will be released.

- b. Settle bank guarantee contract termination.


With joint consent of the exporter and the importer, you settle the bank guarantee contract termination.

- 6. Settle bank guarantee.


When you save a settlement activity, the system changes the activity category of the transaction to record how it is monitored and processed.

The contract can only be posted after it has been settled.

**Note:**

You can reverse your action to an activity until the activity cannot be reversed anymore.

You can decide whether settlement operation is done manually or automatically on confirmation when defining a transaction type.

###### Calculating Fees for Bank Guarantees

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Bank Guarantees > Calculating Fees for Bank Guarantees | L6 | trm05 p.224 | loio `895f3758e2eba107e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/895f3758e2eba107e10000000a441470.html?locale=en-US)

**Use**

For trade finance transactions such as letters of credit and bank guarantees, a certain amount of fees are charged by the business partner during the issuing or receiving process and based on certain conditions, such as a payment rate. The fee calculation process takes place during all stages of the letter of credit lifecycle. The fee calculation for letters of credit is based on four condition types for different amounts.

You can create and maintain the fee conditions for bank guarantees (BG) using transactions Create Financial Transaction (transaction FTR_CREATE) or Edit Financial Transaction (transaction FTR_EDIT).

**Prerequisites**

Before you can calculate the fees for bank guarantee transactions, you need to make the necessary Customizing settings. For more information, see Customizing Settings for Trade Finance.

**Procedure**

1. Issue a bank guarantee using transaction Create Financial Transaction (transaction FTR_CREATE). For detailed

information, see Creating Bank Guarantees.

- 2. Enter the required data for the bank guarantee on the Create Bank Guarantee: Structure tab. For more information, see Basic Data - Trade Finance.

- 3. Choose Fee Conditions to switch to the fee condition overview.
- 4. Choose Create Fee Conditions in the Overview of Conditions.
- 5. Choose a possible condition type from the list in the Possible Condition Types dialog box.

Note that for bank guarantees only the condition type 1204 is available.

- 6. Enter the required data on the Amounts tab on the Condition Details screen.

If the fee is a fixed value, specify the condition amount on the Currency-Related Data block.

You can choose between two types of calculation method for the amount of the condition type:

- a. A percentage rate.
- b. A fixed amount for the total contract period.


This amount however, is split per payment period.

If the fee is calculated based on one of the four condition types listed below, specify the percentage rate and the interest calculation method.

In this field, you specify which interest calculation method is used. The input help provides definitions of each method. (You can choose from standard interest calculation methods such as act/360, 360/360, act/365, act/366, or 365/360.)

Specify the rounding category, rounding unit, and base unit.

- 7. If the fees are paid or calculated on a regular basis, enter a calculation date and a due date on the Dates tab.


**Example:**

You pay 1200 EUR as a fee for the total amount of the BG for a one-year contract, but the fee is paid on a monthly basis. This means that you pay a monthly fee of 100 EUR.

**Features**

The fee cash flows corresponding to the specific fee condition are updated when the following data is changed:

Change of total amount

There are two possible changes to the total amount:

You change the amount value directly on the Structure tab.

However, this change cannot be made if any BG cash flows based on the total amount have already been posted.

You change the amount of the nominal increase or decrease in the dialog box.

This change cannot be made if it affects any cash flows that have already been posted.

The fee cash flows are updated automatically based on the new total amount if the total amount of the BG is changed before the BG has been posted.

**Note:**

The total amount of the BG cannot be changed after the BG has been posted. A new fee condition has to be created to increase or decrease the total amount of the BG. The fee cash flow corresponding to the new fee condition will then be updated.

Change of contract term

The fee cash flows are updated automatically based on the new contract term if the contract term of the BG is changed.

You cannot change the contract term if it affects flows that have already been posted, such as moving the end date of the contract term to before the date of the posted flows.

Change of fee condition

The fee condition can be changed and the corresponding fee cash flows are automatically updated.

You cannot change the fee condition if it affects flows that have already been posted. This means that you cannot change the percentage rate because doing so would lead to the recalculation of the posted flows.

Rollover

If a BG is rolled over, the update of the fee cash flow is automatically triggered and the fee is calculated up to the new end date of the BG based on the assigned fee condition.

Termination

The fee cash flows need to be recalculated if the end user has terminated the BG. The fee is calculated up to the termination date. The last calculation date of the fee cash flow is the termination date.

If the termination date lies in the middle of the period of the BG, the fee cash flow is only calculated up to the termination date.

**Example:**

The monthly fees for the BG are paid at the end of each month, but the termination date is August 15. The fee is therefore calculated up to and paid on August 15.

Reversal

If you reverse your BG, the system changes the status of the flow and financial transaction.

A warning message is issued in cases when a financial transaction includes posted flows (fee flows and other cash flows) to indicate that some flows will be posted after the reversal has been performed.

**More Information**

Bank Guarantees

###### Standby Letters of Credit

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Standby Letters of Credit | L5 | trm05 p.226 | loio `d5ff975756606b10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d5ff975756606b10e10000000a441470.html?locale=en-US)

**Use**

A standby letter of credit is a document issued by a bank on behalf of an applicant. It is used as "payment of last resort" in cases when the applicant fails to fulfill a contractual commitment with the party that requests the standby letter of credit.

Standby letter of credit transactions include transaction types for issuing and receiving standby letters of credit.

The banks (or business partners) charge additional fees based on the principal amount of a standby letter of credit in the issuing and receiving process and based on certain conditions. The fee calculation is based on the total amount of the standby letter of credit.

In addition to functions for creating and changing standby letters of credit, the system also supports rollover, reversal, termination, order expiration, and order execution.

**Prerequisites**

Before you can use the standby letter of credit transactions, you need to:

Create your business partners, assign the corresponding roles to these partners, and maintain the transaction authorizations.

Set up the standing instructions (correspondence, payment details) and release the business partner.

Make the required Customizing settings. For more information, see Customizing Settings for Trade Finance.

**Features**

For more detailed information, see Creating Standby Letters of Credit, Processing Standby Letters of Credit as an Importer, Processing Standby Letters of Credit as an Exporter, and Calculating Fee Flows for Standby Letters of Credit.

###### Processing Standby Letters of Credit as an Exporter

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Standby Letters of Credit > Processing Standby Letters of Credit as an Exporter | L6 | trm05 p.227 | loio `2a1a9f57c6a76b10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2a1a9f57c6a76b10e10000000a441470.html?locale=en-US)

**Prerequisites**

For more information, see Standby Letters of Credit.

**Process**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Trade Finance Trading/Back Office . From here, you can access all the trading and processing functions for standby letters of credit (SLOC).

- 1. Create standby letter of credit contract.

After the advising bank informs the exporter of the standby letter of credit from the importer, you create an standby letter of credit contract in the system and enters all the information.

For more information on creating standby letters of credit, see Creating Standby Letters of Credit.

- 2. Settle or reverse standby letter of credit contract.

If there is no problem with the standby letter of credit, you settle the standby letter of credit contract.

Otherwise, you return the standby letter of credit and reverse the standby letter of credit contract.

- 3. Optional.


Roll over standby letter of credit.

In case the shipment of goods or payment cannot be settled within the planned time frame, the two parties need to negotiate with each other and the bank to adjust the standby letter of credit amount or term. You change the standby letter of credit amount or end of term and roll over the standby letter of credit.

After reaching agreement with the importer and the bank on the adjustment, you settle the contract rollover.

###### Processing Standby Letters of Credit as an Importer

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Standby Letters of Credit > Processing Standby Letters of Credit as an Importer | L6 | trm05 p.228 | loio `f77398570b7f6b10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f77398570b7f6b10e10000000a441470.html?locale=en-US)

**Prerequisites**

For more information, see Standby Letters of Credit.

**Process**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Trade Finance Trading/Back Office . From here, you can access all the trading and processing functions for standby letters of credit (SLOC).

- 1. Create standby letter of credit order.

After the Trader reaches agreement with the business partner that an standby letter of credit is required as a guarantee for the payment, you create a standby letter of credit order in the system to request the standby letter of credit to be issued.

You can also create a standby letter of credit contract directly. A transaction becomes legally binding with the activity category Contract.

For more information on creating standby letters of credit, see Creating Standby Letters of Credit.

- 2. Execute or reverse standby letter of credit order.

After receiving the request for a standby letter of credit to be issued, you go through the standby letter of credit details. If the request is approved, you execute the order and ask the issuing bank to issue the standby letter of credit. After execution, the order becomes a contract. Otherwise, you reverse the order.

- 3. Settle or reverse standby letter of credit contract.

If the issuing bank approves the application for the standby letter of credit, you enter all the standby letter of credit information, such as the number of the standby letter of credit, and then settles the standby letter of credit contract.

Otherwise, you reverse the standby letter of credit contract and provides a reversal reason. Then, the standby letter of credit is in Order activity. After that,you can either adjust the standby letter of credit and reopen the application process or close the application by order expiration.

- 4. Optional.


Roll over standby letter of credit.

In case the shipment of goods or payment cannot be settled within the planned time frame, you need to negotiate with the exporter and bank to adjust the standby letter of credit amount or term. You change the standby letter of credit amount or end of term and roll over the standby letter of credit.

After reaching agreement with the exporter and the bank on the adjustment, you settle the rollover contract.

###### Creating Standby Letters of Credit

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Standby Letters of Credit > Creating Standby Letters of Credit | L6 | trm05 p.229 | loio `575e9857804d6c10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/575e9857804d6c10e10000000a441470.html?locale=en-US)

**Prerequisites**

See Standby Letters of Credit, Processing Standby Letters of Credit as an Importer and Processing Standby Letters of Credit as an Exporter.

**Procedure**

- 1. Choose Create.
- 2. Enter the Company Code, Product type, Transaction type and Partner.
- 3. Make the following entries in the Specifications area:

Currency: If you do not specify a currency when you create a financial transaction, the system automatically uses the currency of the company code.

Portfolio: If you want to assign the transaction to a portfolio, enter this portfolio in the corresponding field.

- 4. Decide whether the activity is an Order or a Contract.

You can create a standby letter of credit transaction directly as a contract. A transaction becomes legally binding with the activity category Contract.

- 5. If you work with External Number Assignment , you have to enter a key for the transaction in the corresponding field, which enables it to be uniquely identified within a company code. Otherwise, the system assigns a number automatically and displays this number when you save the transaction.
- 6. Choose or press Enter to go to the basic data screen for standby letters of credit.


- 7. Enter required data for the standby letter of credit on the Structure tab. For more detailed information, see Basic Data Trade Finance.

- 8. Choose to branch to the correspondence overview for this transaction. This shows the correspondence generated for the transaction and the respective correspondence status.
- 9. Choose to branch to your worklist.
- 10. Choose Documents to branch to the documents overview for this transaction.
- 11. Choose or Transaction Save to save the standby letter of credit.
- 12. You can also branch to the entry screens for the general transaction management functions. To do this, you use tab pages. For more information, refer to Tab Pages.
- 13. To use additional functions, choose Extras and Environment from the menu.

###### Calculating Fees for Standby Letters of Credit

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Standby Letters of Credit > Calculating Fees for Standby Letters of Credit | L6 | trm05 p.229 | loio `c35e3758e2eba107e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c35e3758e2eba107e10000000a441470.html?locale=en-US)

Use

For trade finance transactions such as letters of credit and bank guarantees, a certain amount of fees are charged by the business partner during the issuing or receiving process and based on certain conditions, such as a payment rate. The fee calculation process takes place during all stages of the letter of credit lifecycle. The fee calculation for letters of credit is based on four condition types for different amounts.

You can create and maintain the fee conditions for standby letters of credit (SLOC) using transactions Create Financial Transaction (transaction FTR_CREATE) or Edit Financial Transaction (transaction FTR_EDIT).

**Prerequisites**

Before you can calculate the fees for letter of credit transactions, you need to make the necessary Customizing settings. For more information, see Customizing Settings for Trade Finance

**Procedure**

- 1. Issue a standby letter of credit using transaction Create Financial Transaction (transaction FTR_CREATE). For detailed information, see Creating Standby Letters of Credit.

- 2. Enter the required data for the standby letter of credit on the Create Letter of Credit: Structure tab. For more information, see Basic Data - Trade Finance.

- 3. Choose Fee Conditions to switch to the fee condition overview.
- 4. Choose Create Fee Conditions in the Overview of Conditions.
- 5. Choose a possible condition type from the list in the Possible Condition Types dialog box.
- 6. Enter the required data on the Amounts tab on the Condition Details screen.

If the fee is a fixed value, specify the condition amount on the Currency-Related Data block.

You can choose between two types of calculation method for the amount of the condition type:

- a. A percentage rate.
- b. A fixed amount for the total contract period.


This amount, however,, is split per payment period.

If the fee is calculated based on one of the four condition types listed below, specify the percentage rate and the interest calculation method.

In this field, you specify which interest calculation method is used. The input help provides definitions of each method. (You can choose from standard interest calculation methods such as act/360, 360/360, act/365, act/366, or 365/360.)

Specify the rounding category, rounding unit, and base unit.

- 7. If the fees are paid or calculated on a regular basis, enter a calculation date and a due date on the Dates tab.


**Note:**

Note that for standby letters of credit only the condition type 1204 with profile category Total Credit Line is available.

**Example:**

You pay 1200 EUR as a fee for the total amount of the SLOC for a one-year contract, but the fee is paid on a monthly basis. This means that you pay a monthly fee of 100 EUR.

**Features**

The fee cash flows corresponding to the specific fee condition are updated when the following data is changed:

Change of total amount

There are two possible changes to the total amount:

You change the amount value directly on the Structure tab.

However, this change cannot be made if any SLOC cash flows based on the total amount have already been posted.

You change the amount of the nominal increase or decrease in the dialog box.

This change cannot be made if it affects any cash flows that have already been posted.

The fee cash flows are updated automatically based on the new total amount if the total amount of the SLOC is changed before the SLOC has been posted.

**Example:**

A company applies to issue an SLOC from January 1, 2016 to June 30, 2016 with a total amount of 1 M EUR. The fee condition is calculated with a percentage rate of 1.2% and an interest calculation method of 30/360, and it is paid monthly. Once the amount is posted, the fee cash flows are as follows:

|Date|Fee Amount|
|---|---|
|1/31/2016|1000|
|2/28/2016|1000|
|3/31/2016|1000|
|4/30/2016|1000|
|5/31/2016|1000|
|6/30/2016|1000|


If the end user increases the total amount of the SLOC to 2 M EUR by adding a new nominal fee on April 1, 2016, the new fee cash flows are then as follows:

|Date|Fee Amount|
|---|---|
|1/31/2016|1000|
|2/28/2016|1000|
|3/31/2016|1000|
|4/30/2016|2000|
|5/31/2016|2000|
|6/30/2016|2000|


Change of contract term

The fee cash flows are updated automatically based on the new contract term if the contract term of the SLOC is changed.

You cannot change the contract term if it affects flows that have already been posted, such as moving the end date of the contract term to before the date of the posted flows.

Change of fee condition

The fee condition can be changed and the corresponding fee cash flows are automatically updated.

You cannot change the fee condition if it affects flows that have already been posted. This means that you cannot change the percentage rate because doing so would lead to the recalculation of the posted flows.

Rollover

If an SLOC is rolled over, the update of the fee cash flow is automatically triggered and the fee is calculated up to the new end date of the SLOC based on the assigned fee condition.

Termination

If the termination date is after the end date of the SLOC, the fee cash flows are calculated up to the end date of the SLOC.

If the termination date is before the end date of the SLOC, an automatic update of the fee cash flows is triggered.

If the termination date lies in the middle of the period of the SLOC, the fee cash flow is only calculated up to the termination date.

**Example:**

The monthly fees for the L/C are paid at the end of each month, but the termination date is August 15. The fee is therefore calculated up to and paid on August 15.

Reversal

If you reverse your SLOC, the system changes the status of the flow and of the financial transaction.

A warning message is issued in cases when a financial transaction includes posted flows (fee flows and other cash flows) to indicate that some flows will be posted after the reversal has been performed.

**More Information**

Standby Letters of Credit

###### Customizing Settings for Trade Finance

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Customizing Settings for Trade Finance | L5 | trm05 p.232 | loio `6b0aca55c24b6d55e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6b0aca55c24b6d55e10000000a4450e5.html?locale=en-US)

Before you can use transactions in the Trade Finance area, you need to make the following Customizing settings depending on your requirements under Treasury and Risk Management Transaction Manager Trade Finance :

General Customizing settings:

Define Product Types

Define Number Ranges

Define Transaction Types

Define Flow Types

Assign Flow Types to Transaction Types

Define Condition Types

You use this Customizing activity to define the condition type for your trade finance transactions. Condition types automatically generate flows that are the basis for further processing in FI and Cash Management and for the analysis in the Market Risk Analyzer.

Assign Condition Types to Transaction Types

You use this Customizing activity to be able to completely represent a financial product in the system by assigning the necessary condition types to trade finance transactions at transaction type level.

Define Condition Types

Assign Condition Types to Transaction Types

Define Generation of Subledger Position Indicator

BAdI: Subledger Position Indicator (Account Assignment Reference)

BAdI: Subledger Position Indicator

Assign General Valuation Class

Activate Integration with SD

**Example**

Define the flow type for the net charges amount and all related settings:

In the Define Flow Types - Trade Finance Transactions Customizing, you must create a new flow type 1854 for the net charges amount, with flow category 85 Trade Finance Payment, calculation type SS Outflow (generic), which is relevant to position, relevant to posting, relevant to valuation, and relevant to P/L. In the Payment Management area, choose For outgoing and incoming payments in the Payment Request field.

In the Assign Flow Types to Transaction Types - Trade Finance Transactions Customizing, you must assign the new flow type to product type 85A Normal Letter of Credit and the transaction types 100 Issue and 200 Receive.

In the Define Update Types and Assign Usages Customizing, you must create the update types TF1854+ Net Charges and TF1854- Net Charges and assign them to the Usage Transaction Management.

In the Assign Flow Types to Update Types Customizing, you must assign the new the update types TF1854+ Net Charges and TF1854- Net Charges and to the new flow type 1854.

Kontenfindung

Customizing settings for Letters of Credit:

Define Document Types

Define Document Templates

Define Conditions for Payment and Presentation Period

Define Rejection Reasons for L/C Presentation

Customizing settings for Bank Guarantees:

Define Bank Guarantee Types

If you want to activate the integration of trade finance transactions with Credit Risk Analyzer, you also need to make the following Customizing settings under Treasury and Risk Management Credit Risk Analyzer Basic Settings Automatic Integration

of Financial Objects in Transaction Master Data Trade Finance in addition to other general settings for the Credit Risk Analyzer:

Activate Integrated Default Risk Limit Check

Derive Default Risk Control Parameters for Trade Finance

###### Blocking and Unblocking Manual Input Business Partners

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Blocking and Unblocking Manual Input Business Partners | L5 | trm05 p.234 | loio `239e9b2940bd4c4aba2cb30bc29637bf` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/239e9b2940bd4c4aba2cb30bc29637bf.html?locale=en-US)

**Use**

You use transaction FTRTDPP01 to block or unblock manual input data of business partners in the Trade Finance area, including:

<Manual Input Beneficiary>

<Manual InputAdvising Bank>

<Manual InputApplicant>

<Manual Input Issuing Bank>

**Prerequisites**

You have activated the Information Lifecycle Management (ILM) business function in the Switch Framework (transaction SFW5).

You have the required authorization.

SAP_CA_BP_DP_BLOCK (ACT:05) for blocking data

SAP_CA_BP_DP_DISPLAY (ACT: 03) for displaying blocked data

SAP_CA_BP_DP_UNBLOCK (ACT: 95) for unblocking data

You are familiar with the functions for ILM policies and have defined ILM policies for ILM objects TRTM_FTR in transaction IRMPOL.

For more information about ILM, see SAP Information Lifecycle Management.

For more information about blocking business partners, see SAP Customizing Implementation Guide Cross-Application Components Data Protection Blocking and Unblocking of Data Application-Specific Settings General Information .

###### Integration of Trade Finance with Sales

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Integration of Trade Finance with Sales | L5 | trm05 p.234 | loio `4ad228eb053c4684a7bf4d08a0de491e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ad228eb053c4684a7bf4d08a0de491e.html?locale=en-US)

The integration of Trade Finance with Sales enables you to directly retrieve available trade finance transactions and assign Trade Finance transactions to sales order items when you create a sales order in Sales. For more information, see Creating Sales Orders with Trade Finance Transactions.

**Note:**

The integration is only available when Trade Finance and Sales are implemented in the same system installation instance.

**Prerequisites**

You have activated the integration of Trade Finance with Sales by company code, product type, and transaction type in Customizng under Financial Supply Chain Management Treasury and Risk Management Transaction Manager Trade Finance

Transaction Management Activate Integration with S/4HANA Sales .

###### Creating Sales Orders with Trade Finance Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Integration of Trade Finance with Sales > Creating Sales Orders with Trade Finance Transactions | L6 | trm05 p.235 | loio `9c6195017cf44376aa63415714b93fcd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9c6195017cf44376aa63415714b93fcd.html?locale=en-US)

Trade Finance integration enables you to use trade finance transactions to guarantee the payment of your sales orders. The integration supports the following product types in Trade Finance:

Letter of credit

Standby letter of credit

Bank guarantee

**Prerequisites**

You have activated the integration of Trade Finance with SAP S/4HANA Sales by company code, product type, and transaction type in Customizing under Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Trade Finance Transaction Management Activate Integration with S/4HANA Sales .

You have checked and defined the settings in Customizing for integration of Sales with Trade Finance. For more information, see Customizing Settings for Integration with Trade Finance.

You have the authorizations to assign the trade finance transactions to your sales orders. Your PFCG role should have been configured as follows:

Transactions FTRTLC03 and FTRTBG03 are added to authorization object F_T_TRANSB.

Authorization objects T_DEAL_PD and T_DEAL_PF are granted with display authorization.

**Features**

To minimize the payment risks of your sales order, you can assign financial documents to your sales order by selecting existing trade finance transactions (for example, a letter of credit transaction) as a payment guarantee. To secure the payment, the system checks that the relevant data in the sales order and its subsequent deliveries complies with the terms in the assigned trade finance transactions. For example, the system checks that the order value does not exceed the available amount of the letter of credit transaction. For more information about what other fields the system checks between sales order and trade finance transaction for compliance, see Risk Check.

**Note:**

The system uses credit price to calculate the value of items in sales orders and deliveries for the compliance checks. To indicate the credit price for your items, you set the Subtotal field to A for the condition type or value line in the pricing procedure.

If there are any discrepancies, the system blocks the sales order or its deliveries (or interrupts the goods issue posting) until you correct the data in the sales or delivery documents, or ask a trader to correct the respective trade finance transactions.

**Note:**

By default, the system checks only sales orders for compliance. You can make settings so that the system checks subsequent deliveries as well during delivery processing (that is, including delivery creation, picking, and goods issue posting) in Customizing under Sales and Distribution Basic Functions Credit Management/Risk Management Receivables Risk Management Maintain Trade Finance Risk Control .

The trader can recheck, release, or reject blocked documents directly in the Risk Check Decision Management report. However, to enable the system to generate the necessary risk check decisions for Treasury and Risk Management, you must select the

Generate risk check decision checkbox in Customizing under Sales and Distribution Basic Functions Credit Management/Risk Management Receivables Risk Management Maintain Trade Finance Risk Control .

**Related Information**

Trade Finance

###### Risk Check

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Integration of Trade Finance with Sales > Risk Check | L6 | trm05 p.236 | loio `c4d9a8491fcd4a66873f1cd452d67663` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c4d9a8491fcd4a66873f1cd452d67663.html?locale=en-US)

If you use trade finance transactions to guarantee your sales orders, the system checks the relevant data in the sales order against the trade finance transaction for compliance.

**Prerequisites**

You create sales orders with trade finance transactions. For details, see Creating Sales Orders with Trade Finance Transactions.

**Features**

Risk checks can be triggered in the following scenarios:

The user saves a new sales order that has one or multiple trade finance transactions assigned to it.

The user saves a sales order after updating the assigned trade finance transactions or other risk-check-related fields.

The user saves a trade finance transaction after changing risk-check-related fields.

The user processes the goods delivery, including creating outbound delivery, picking, and posting goods issue.

**Note:**

By default, the system checks only sales orders against their assigned trade finance transactions for compliance. You can alter the settings so that the system also checks subsequent deliveries. You do this in Customizing under Sales and Distribution Basic Functions Credit Management/Risk Management Receivables Risk Management

Maintain Trade Finance Risk Control .

In cases where a letter of credit transaction is assigned to a sales order item, the system checks the following fields:

Activity

Only transactions in the activity Contract Settlement and Rollover Settlement, or Contract (without settlement) and Rollover (without settlement) must be assigned to sales order items. If transactions in other activities are assigned to sales order items, the risk check fails.

Applicant

The applicant of the letter of credit needs to be consistent with the payer in the sales order. If the applicant of the letter of credit is entered manually, the risk check fails.

Amount, Currency, and Tolerance

The upper limit and the additional amount for nominal flows are included in the available amount of the letter of credit transaction. The available amount (total amount - amount guaranteed for other sales order items) of the letter of credit must not be less than the sales order item amount to be guaranteed. The currency in the letter of credit must be consistent with the currency in the sales order.

Term Start and Term End

The term start date of the letter of credit must be earlier than the goods issue date of the first confirmed schedule line of the sales order item. The term end date of the letter of credit must be later than the goods issue date of the last confirmed schedule line of the sales order item.

Shipment Period

The latest shipment date must be later than the goods issue date of the last confirmed schedule line.

Partial Shipment

The setting for partial shipment for the letter of credit and the sales order item must be consistent.

Shipping Method

The shipping method specified in the letter of credit must be consistent with the shipping type specified for the sales order item.

Port of Loading, Port of Discharge, Place of Receipt, and Place of Delivery

The relevant place or port must be consistent between the letter of credit and the sales order item based on the preset mapping of the incoterms location types and trade finance locations.

In cases where a bank guarantee or standby letter of credit transaction is assigned to a sales order item, the system checks the following fields:

Activity

Only transactions in the activity Contract Settlement and Rollover Settlement, or Contract (without settlement) and Rollover (without settlement) must be assigned to the sales order items. If transactions in other activities are assigned to sales order items, the risk check fails.

Applicant

The applicant of the bank guarantee or standby letter of credit transaction must be consistent with the payer in the sales order. If the applicant of the letter of credit transaction is entered manually, the risk check fails.

Amount, Currency, and Tolerance

The upper limit and the additional amount for nominal flows need be included in the available amount of the letter of credit transaction. The available amount (total amount - amount guaranteed for other sales order items) of the bank guarantee or standby letter of credit cannot be less than the sales order item amount to be guaranteed. The currency in the bank guarantee or standby letter of credit must be consistent with the currency in the sales order.

Term Start and Term End

The term start date of the letter of credit must be earlier than the goods issue date of the first confirmed schedule line of the sales order item. The term end date of the letter of credit must be later than the goods issue date of the last confirmed schedule line of the sales order item.

When risk check is successful, the assignment relationship is updated into the corresponding trade finance transaction. If the risk check fails, the system blocks the sales order or its deliveries (or interrupts the goods issue posting) until the blocked sales or delivery documents, or the assigned trade finance transactions are corrected.

###### Consistency Check Between Trade Finance and Sales

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Integration of Trade Finance with Sales > Consistency Check Between Trade Finance and Sales | L6 | trm05 p.237 | loio `50b604e037424c5fbf6e6e6a902e4012` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/50b604e037424c5fbf6e6e6a902e4012.html?locale=en-US)

A report checks the consistency of assignment information between a sales document and the corresponding trade finance transaction. You cannot make changes directly in this report, but the results from the report can serve as a guide for further action.

You can access the report under Treasury and Risk Management Transaction Manager Trade Finance Information System Transaction Integration with S/4HANA Sales Check Consistency Report .

**Features**

To view the results of consistency risk, you can restrict the selection by key figures of the trade finance transactions or sales document. You can also choose to display the complete set of results or only the results relating to inconsistent data.

The results are displayed in the trade finance view. Different traffic lights are used for the results:

Green

The assignment information in the trade finance transaction can be matched exactly with the assignment information in the sales document.

Yellow

The assignment information in the trade finance transaction can only be partially matched with the assignment information in the sales document.

Red

The assignment information only exists in the sales document.

You can view the detailed assigment information for each trade finance transaction listed in the results. You can also navigate to the corresponding risk check decision.

###### Risk Check Decision Management

> **Path:** Treasury and Risk Management > Transaction Manager > Overview of Financial Instruments > Trade Finance > Integration of Trade Finance with Sales > Risk Check Decision Management | L6 | trm05 p.238 | loio `1714464224a44d1a89a4e41dda438177` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1714464224a44d1a89a4e41dda438177.html?locale=en-US)

You can recheck, release, or reject blocked documents directly in the Risk Check Decision Management report.

You can access the report under Treasury and Risk Management Transaction Manager Trade Finance Information System Transaction Integration with S/4HANA Sales Risk Check Decision Management .

**Prerequisites**

To enable the system to generate risk check decisions in the event of a check failure, you must select the Generate Risk Check Decision checkbox in the Customizing activity Maintain Trade Finance Risk Control under Sales and Distribution Basic Functions Credit Management/Risk Management Receivables Risk Management .

**Features**

To view the risk check decisions, you can restrict the selection using key figures of the trade finance transactions or sales document.

You can also restrict the selection by the status of the risk check decisions. The status of a risk check decision can be one of the following:

Open

The risk check decision is generated and no further actions are performed for it.

Closed

The sales document related to the risk check decision has been rechecked with a successful result. This recheck is triggered when you click the Recheck button in the report or when you change the related sales document or trade finance transaction.

Released

The sales document related to the risk check decision has been released. You set this status by clicking the Release button in the report.

Rejected

The sales document related to the risk check decision has been rejected. You set this status by clicking the Reject button in the report.

You can perform the following actions for risk check decisions in status Open:

Recheck

The risk check of the sales document related to the risk check decision selected is retriggered. If the risk check fails, a new version of the risk check details is updated into the existing risk check decision, and the status in either the sales document and the trade finance transaction is not changed. If the risk check produces a successful result, the following applies:

The sales document is unblocked with the overall credit status Approved and the overall blocked status Not Blocked.

The relevant sales order is assigned in the corresponding trade finance transaction.

The risk check decision status changes from Open to Closed.

Release

The sales document is released with a comment although discrepancies still exist. If the action is successful, the following occurs:

The sales document is unblocked with overall credit status Released and the overall blocked status Not Blocked.

The relevant sales order is assigned in the corresponding trade finance transaction.

The risk check decision status changes from Open to Released.

Reject

The sales document is rejected with a rejection reason and a comment. If the action is successful, the following occurs:

The sales document is completed with the overall status Complete, rejection status Everything Rejected, overall credit status Not Approved, and overall blocked status Blocked. No further delivery is allowed.

The rejection reason is also updated into the sales document.

The relevant sales order is assigned in the corresponding trade finance transaction.

The risk check decision status changes from Open to Rejected.

You can also click the Detail button to view the details of risk check decisions.

