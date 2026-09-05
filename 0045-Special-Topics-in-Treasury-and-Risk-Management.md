# Special Topics in Treasury and Risk Management - SAP TRM Knowledge Base (branch split)

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

### Special Topics in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management | L2 | trm01 p.91 | loio `8c9e2e5ea71e469399260e62bd354cb0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8c9e2e5ea71e469399260e62bd354cb0.html?locale=en-US)

#### Parallel Accounting in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Parallel Accounting in Treasury and Risk Management | L3 | trm01 p.91 | loio `dd50d7531a4d424de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dd50d7531a4d424de10000000a174cb4.html?locale=en-US)

Use

In Treasury and Risk Management (TRM) , you portray parallel accounting using the valuation area. You therefore have to define a valuation area for each accounting principle.

You post the valuation results separately for each valuation area. You can post the values of the valuation areas in TRM to different accounts.

See Portrayal Using Additional Accounts :

Alternatively, you can assign the valuation areas to the individual accounting principles and thereby transfer the valuation results into different ledger groups. See Portrayal Using Parallel Ledgers .

**Features**

Each valuation area provides you with various classifications that you can use to depict the valuation specifications for the individual accounting principles.

Financial Assets

You can divide your financial assets into holding categories (valuation classes), such as HTM or AFS for IFRS financial statements.

Structure of Balance Sheet Accounts

You can define the structure of your balance sheet accounts using characteristics (differentiation concepts).

Financial Products

For certain financial products, you can activate single position management ( Lot Accounting ) with different consumption sequence procedures.

You control the valuation of your balance sheet accounts using position management procedures . You can assign the position management procedures to the balance sheet accounts depending on valuation area, valuation class, and other characteristics. The position management procedure contains the legally prescribed valuation approach for valuating (such as lowest value principle or key date valuation).

**Note:**

For more information about the settings, see Transaction Manager and New General Ledger Accounting .

##### Making Settings for Parallel Ledgers

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Parallel Accounting in Treasury and Risk Management > Making Settings for Parallel Ledgers | L4 | trm01 p.92 | loio `8340d7531a4d424de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8340d7531a4d424de10000000a174cb4.html?locale=en-US)

**Use**

If you want to perform parallel accounting using parallel ledgers in Transaction Manager, you need to make some system settings in addition to the general settings.

**Prerequisites**

The following requirements and procedures are necessary if you want to use parallel ledgers in Transaction Manager:

You have made the general settings.

See under Transaction Manager and New General Ledger.

General Ledger Accounting (new) has been activated and several ledgers are deployed.

Postings in the leading ledger to customer accounts

Postings in other non-leading ledgers directly to reconciliation accounts

**Procedure**

- 1. Define new posting specifications to enable account determination for the customer and reconciliation accounts.
- 2. In Customizing, choose Treasury and Risk Management Transaction Manager General Settings Accounting Link to Other Accounting Components Define Account Determination .
- 3. Select the relevant chart of accounts.


- 4. Copy the posting specification relevant for you and change the name to the following:

- a. AXXX for posting to reconciliation accounts
- b. DXXX for posting to customer accounts


- 5. Define posting keys for general ledger postings for the posting specifications of reconciliation accounts. Assign an account symbol with posting category 2 (Subledger Posting in Payment Currency). Post to the reconciliation account defined in the customer master record.
- 6. For postings to be made to the customer account, assign an account symbol with posting category 2 (Subledger Posting in Payment Currency). Define a posting key for a posting to a customer account.
- 7. Assign update type to posting specifications (without restriction to avaluation area).


a. Assign to the relevant update types the newly defined posting specifications for postings to reconciliation accounts

(AXXX) and set the Payment Transaction indicator.

Assign the update type to posting specifications for leading valuation area(post to customer account)

Assign to the relevant update types the newly defined posting specifications for posting to customer accounts (DXXX) for the leading valuation area and set the Payment Transaction indicator.

#### Customizing Settings in DMS for TRM Documents

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Customizing Settings in DMS for TRM Documents | L3 | trm01 p.93 | loio `8e54a15002be9e04e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8e54a15002be9e04e10000000a441470.html?locale=en-US)

**Use**

Treasury and Risk Management uses Document Management (CA-DMS) in the following areas:

Correspondence Framework

Outgoing and incoming correspondences (or parts thereof) as well as temporary files are stored in DMS.

TRO (for outgoing correspondences)

TRI (for incoming correspondences)

TRT (for temporary files)

TRA (for attachments)

Hedge Accounting for Positions

Documentation of Hedging Relationships (THX)

Uploaded Retrospective Effectiveness Assessments (THE)

Trade Repository Reporting (TRR)

Outgoing and incoming trade repository notifications are stored in DMS.

TAR Trade Repository

**Note:**

See the documentation on the Customizing activities.

Activities

Make the following settings in Customizing for Document Management under Cross-Application Components Document Management for the TRM documents.

- 1. Under Control Data Define Number Ranges for Document Numbers , create different ranges and assign them to the document types.
- 2. Under General Data Define Data Carrier , create the following entry under Define Data Carrier Type "Server, Front End":

Data Carrier Type: PC

Description: Local PC

Path: %userprofile%

Set the Online checkbox

Select the entry and choose Identify Front-End Computers.

If no entries exist, choose .


Save your entries.

- 3. Under General Data Settings for Storage Systems Maintain Storage System , create the following content repositories:

THX_HDOC

Doc. Area: Document Management System

Storage Type: SAP System Database

Repository Subtype: Normal

Version No.: 0046 Content Server Version 4.6

Content Table: THXT_HDOC_DMS

TRM_MSG_CR

Doc. Area: Document Management System

Storage Type: SAP System Database

Repository Subtype: Normal

Version No.: 0046 Content Server Version 4.6

Content Table: TCORFT_MESSAGE

TARO_DOC

Doc. Area: Document Management System

Storage Type: SAP System Database

Repository Subtype: Normal

Version No.: 0046 Content Server Version 4.6

Content Table: TLRT_TARO_DMS

- 4. Under General Data Settings for Storage Systems Maintain Storage Categories , create the following categories:


THX_HDOC to which you assign the content repositoryTHX_HDOC

TRM_MSG to which you assign the content repositoryTRM_MSG_CR

TARO_DOC to which you assign the content repositoryTARO_DOC

- 5. Under General Data Define Workstation Application , you create the following workstation application:

WS Application: TRM

Description: Treasury: All Files

File Format: *.*

Appl.Icon: @9I@

Set the checkboxes Start Authorization and You cannot rename temporary files.

Save your entries.

Select the new workstation application and choose Define Workstation Application in Network.

Create the following three entries:

Save your entries.

You need to set the Start Authorization for Application indicator for the workstation application PDF Acrobat Reader, and make all the other settings for the application.

- 6. Under Control Data Define Document Types , make the following new entries under "Define Documents" for the different objects. Choose New Entries and create the following document types:


|WS Application|TRM: All Files|TRM: All Files|TRM: All Files|
|---|---|---|---|
|Data Carrier Type:|PC|PC|PC|
|Application Type:|1 (Display)|2 (Change)|3 (Print)|
|Path with Program Name:|%AUTO%|%AUTO%|%AUTO%|


|Fields|Correspondence Framework| | | |Hedge Accounting for Positions| |Trade Repository Reporting (TRR)|
|---|---|---|---|---|---|---|---|
| |TRO|TRI|TRT|TRA|THX|THE|TAR|
|Use KPro (storage in Knowledge Provider):|X|X|X|X|X|X|X|
|Status Change|X| | | |X|X| |
|Change Documents|X|X|X|X|X|X| |
|Number Assignment:|1 (Internal Number Assignment Only)|1|1|1|1|1| |


|Internal Number Range|Assign a number range.| | | | | | |
|---|---|---|---|---|---|---|---|
|External Number Range|Assign a number range.| | | | | | |
|Number Exit:|MCDOKZNR (= default entry)|MCDOKZNR|MCDOKZNR|MCDOKZNR|MCDOKZNR|MCDOKZNR|MCDOKZNR|
|Vers. No. Incr.:|0 (No Version Numbering)|0|0|0|0|0|0|
|Default Appl.:|TRM|TRM|TRM|TRM|TRM|TRM| |
|Dis. WS Applic.:|TRM|TRM|TRM|TRM|TRM|TRM| |
|In the Field Selection area, you can make the following entries:| | | | | | | |
|Class Data|- (= hide)|-|-|-|-|-|-|
|Hierarchy Indicator|-|-|-|-|-|-|-|
|Document Status|*|*|*|*|*|*|*|
|User|*|*|*|*|*|*|*|
|Authorization Group|-|-|-|-|-|-|-|
|Laboratory/Office|-|-|-|-|-|-|-|
|CAD Indicator|-|-|-|-|-|-|-|
|Superior Document|-|-|-|-|-|-|-|
|CM-Relevance|-|-|-|-|-|-|-|


Select one of the document types in each case and enter a description for the document type, in your system language, under Language-Dependent Description.

Under Define Document Status, enter the following entries for the document types with status change:

THX and THE:

- Document Status:H1

- Status:H1 Status Text:Created Status Type: Initialstatus

Set the Store checkbox.

Document Status:H2

- Status:H2




Status Text:In Release

Set the Store checkbox.

- Document Status:H3

- Status:H3 Status Text:Released

Set the Store checkbox.

Document Status:H4

- Status:H4

Status Text:Obsolete

Set the Store checkbox.

Document Status:H5

- Status:H5 Status Text:Reversed




Set the Store checkbox.

**TRO**

- Document Status:01 Status:N Status Text:New

Status Type: I Initialstatus

Set the Store checkbox.

- Document Status:02 Status:S Status Text:Sent

Set the Store checkbox.

- Status Type: S Sperrstatus

- Prev. 1: 01
- Prev. 2: 03


Document Status:03

Status:RS

Status Text:Resend requested

- Status Type: T Temporarer Status Prev. 1: 02


- Document Status:04


Status:C

Status Text:Send canceled

Abbreviation:

Status Type: S Sperrstatus

- Document Status:05 Status:A Status Text:Archived


Abbreviation:

Status Type: D Archivstatus

TAR

Document Status:H1

Status:H1

Status Text:Created

Status Type: Initialstatus

Set the Store checkbox.

**Note:**

The Customizing settings for the document types THX and THE need to be available in your system (BC set).

#### Data Access and Verifiability of Digital Documentation

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Data Access and Verifiability of Digital Documentation | L3 | trm01 p.98 | loio `bb4cc753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bb4cc753b1081d4be10000000a174cb4.html?locale=en-US)

In the area of Treasury and Risk Management, the Transaction Manager supports you by complying with the legal requirements according to the German Fiscal Code and the publication Principles of Data Access and Verifiability of Digital Documentation from the German Federal Ministry of Finance. This applies to direct access (Z1 access) and data carrier surrender (Z3 access).

#### Negative Interest

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Negative Interest | L3 | trm01 p.98 | loio `15b47fbf455a422cb4a46043c4e0b19e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/15b47fbf455a422cb4a46043c4e0b19e.html?locale=en-US)

**Use**

Treasury and Risk Management allows you to portray negative interest.

Note the points listed under "Constraints" below and check thoroughly whether all of the changes that are relevant to your business process have been made.

Note also that you need to make some settings in Customizing. If you use reference interest rates outside of Treasury and Risk Management (such as your own add-on programs), you need to check whether there could be problems there with negative interest rates.

**Note:**

Activating the Soft Modification for Portraying Short Sales / Short Positions

If you would also like to pay off short positions, you need to activate the soft modification 1633648 in accordance with SAP Note 732499 . Then activate SAP Note 1633648 in method IF_JBR_SOFT_MODIFICATIONS~IS_ACTIVE of class ZCL_SOFT_MODIFICATIONS_CUST using the CASE bar (see Activating a New SAP Note in delivery note 732499). Delivery note 732499 also contains information about the principle of a soft modification.

In the case of a short sale of a bond, negative repayments can occur (in other words, the repayment causes the position to be increased). The new functions also allow such cases to be portrayed.

**Prerequisites**

To activate the functions for negative interest, you need to set the Sign indicator for the domain AZINSSATZ on the Definition tab in the ABAP Dictionary (transaction SE11).

**Note:**

The change to the domain should not usually cause any database conversions. However, activation can be timeconsuming because a large number of fields use this domain.

The domain is located in the application basis (SAP_ABA) and is used beyond the confines of Treasury and Risk Management.

From Basis Release SAP_ABA 732, the Sign indicator is already set, so you can leave the default setting as it is.

In Customizing for the Transaction Manager, you need to create, assign, and set up update types (for example, account determination) for negative interest flows (as well as for any negative repayment flows).

For the accrual/deferral of negative interest, you can decide whether the negative and positive interest payments are accrued/deferred separately, or whether netting is performed for the negative and positive interest payments:

Separate Accruals/Deferrals for Negative and Positive Interest Payments

For this, you need to go to Customizing for accruals/deferrals and assign the relevant update types for negative and positive interest payments as profit-related flows for accruals/deferrals. Since the sign of a flow is not considered for accruals/deferrals, you need to define alternative update types for the accrual/deferral of negative interest payments. In this way, the accrual/deferral for positive interest payments is posted using a revenue account, and the accrual/deferral for negative interest payments is posted using an expense account.

Netting Negative and Positive Interest Payments on the Same Revenue Account

In Customizing, choose Transaction Manager General Settings Accounting Accrual/Deferral Update Types Assign Update Types for Accrual/Deferral . Select the relevant area and then choose Update Rules from the hierarchy on the left.

Enter the update type for the negative interest payment in the settings for the accrual/deferral of the positive interest payment in the Accrual/Deferral: Update Type for Expense Flow field.

The prerequisite for this is that the update types for positive and negative interest payments are posted using the same revenue account (account determination).

**Features**

You can enter negative interest in the interest tables.

In the class data (transaction FWZZ), you can create bonds with negative interest flows and repayment flows. Interest payments and redemption payments can be paid and posted in the usual way.

You can enter negative interest rates in all interest-related financial transactions.

Amortization (in accordance with LAC and SAC) considers negative interest payments and redemption payments.

The accrual/deferral of expenses and revenues (transaction TPM44) can handle negative and positive interest payments separately, or perform netting for positive and negative interest payments and then accrue them using a revenue account.

Considering Negative Interest in the Market Risk Analyzer

Yield Curves

The mathematical basis for constructing interest curves (in particular for bootstrapping) is left unchanged, even when interest rates are negative at one or more grid points.

Negative interest can lead to discount factors that are greater than one.

The system does not support interest rates that are less than or equal to -100%, nor does it support discount factors that are greater than or equal to 10.

Statistics Calculator

If the Logarithmed element type is stored as the statistics type, the statistics calculator handles the sign change of the interest rate as missing market data. This is because the logarithm would otherwise have to be calculated from a negative number, which does not make mathematical sense.

Value at Risk

For the VaR calculation using historic simulation, sign changes for interest rates are also handled as missing market data.

Money Market Transactions

Negative interest can be included in the calculation of the net present value of money market transactions.

Swaps

Negative interest can be included in the calculation of the net present value of interest rate swaps and crosscurrency interest rate swaps. For this, negative interest is supported on the fixed side of the transaction as well as on the variable side.

Forward Rate Agreements

Negative interest can be included in the calculation of the net present value of forward rate agreements. For this, both the fixed interest rate and the reference interest rate can become negative.

Floors, Caps, and Swaptions

The net present value of floors, caps, and swaptions can also be determined for negative forward rates. This is possible by extending the definition area of the Black-Scholes model for option prices. In such cases, the price calculator issues a warning message with explanatory documentation.

If, however, the interest on the fixed side of the underlying of an option is also set as negative, meaning that the strike in the Black-Scholes model is negative, valuation is not possible using the Black-Scholes model.

When negative interest is processed, it is irrelevant whether the interest was entered explicitly as negative, whether it became negative as a result of a shift, or whether it was caused by forward calculation in the case of plummeting interest curves.

**Constraints**

When scenarios (transaction TV21) are entered in the Market Risk Analyzer, negative interest is not supported.

The net present value calculation for bonds with negative interest in the Market Risk Analyzer is not supported.

Transactions cannot be created for a short position if redemption payments are still planned before the date of the position change.

#### Legacy Data Transfer

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Legacy Data Transfer | L3 | trm01 p.101 | loio `000dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/000dda531198434de10000000a174cb4.html?locale=en-US)

**Purpose**

If you want to repeat the implementation of the Transaction Manager (FIN-FSCM-TRM-TM) and your data (legacy data) is in a source system, you need to make sure this data is a available in the Transaction Manager for a key date.

Legacy data needs to be transferred to the system in a number of steps and can be done in various ways.

The following section describes the various processes, depending on the position type or transaction type:

OTC Transactions (product categories 510, 520, 530, 540, 550, 560, 600, 710, 712, 760, 780, 730, 770)

Securities Positions (product categories 010, 020, 030, 040, 041, 042, 060, 070, 111, 112, 113, 114, 160)

Futures (product categories 700, 750)

When you transfer legacy data to the Transaction Manager, you can use functions in Customizing specially developed for the legacy data transfer in addition to the application functions in the Transaction Manager.

On the SAP Easy Access screen, choose Tools Customizing IMG Execute Project SAP Reference IMG Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Tools Legacy Data Transfer

.


**Prerequisites**

Before you can transfer the legacy data, you must satisfy the following prerequisites:

You need to make your settings in Customizing for the Transaction Manager.

For more information, see the implementation guide (IMG) for the Transaction Manager. Refer also to the documentation for the Transaction Manager in the SAP Library.

In addition, to transfer legacy data you need to define update types and assign them to the usage legacy data transfer by choosing Define Update Types and Assign Usages. In the Customizing activity Assign Update Types for Legacy Data Transfer, you then need to assign clearing and posting update types for the individual components.

The following update types for transferring legacy data are provided in the sample Customizing delivered with the system:

- DT_C001 Legacy data transfer: Additional flow (positive)
- DT_C002 Legacy data transfer: Additional flow (negative)


- DT_C011 Legacy data transfer: Post accrual/deferral (positive)
- DT_C012 Legacy data transfer: Post accrual/deferral (negative)


- DT_T001 Legacy data transfer: Post units/nominal (positive)


- DT_T002 Legacy data transfer: Post units/nominal (negative)
- DT_T003 Legacy data transfer: Post purchase value (positive)
- DT_T004Legacy data transfer: Post purchase value (negative)
- DT_T005Legacy data transfer: Post security valuation (positive)
- DT_T006Legacy data transfer: Post security valuation (negative)
- DT_T007Legacy data transfer: Post foreign currency valuation (positive)
- DT_T008Legacy data transfer: Post foreign currency valuation (negative)


- DT_T011Legacy data transfer: Post costs (positive)
- DT_T012Legacy data transfer: Post costs (negative)


- DT_T017Legacy data transfer: Post amortization (positive)
- DT_T018Legacy data transfer: Post amortization (negative)



These update types should only be used as a guide and should not be considered as complete.

You need to define additional information for some of the update types. To do this, choose Securities Position Management Update Types Specify Update Types for Securities Account Management .

Examples from the Sample Customizing Settings

|Update Type|Additional Information|
|---|---|
|DT_C001 Legacy data transfer: Additional flow (positive)|Calculation category TF, Flow classification: Charges|
|DT_C002 Legacy data transfer: Additional flow (negative)|Calculation category TF, Flow classification: Charges|
|DT_T001 Legacy data transfer: Post units/nominal (positive)|Calculation category AA, Effective interest calculation: calculationrelevant, +/- sign|
| | |


You assign the position change categories to the update types for the valuation area-independent data by choosing General Settings Accounting Settings for Position Management Set the Effects of the Update Types on the Position Components

.


Example from the Sample Customizing Settings

|Update Type|Position Change Category|
|---|---|
|DT_T003 Legacy data transfer: Post purchase value (positive)|1011 Post purchase value|
|DT_T004 Legacy data transfer: Post purchase value (negative)|1010 Post negative purchase value|
|DT_T011 Legacy data transfer: Post costs (positive)|1015 Post costs to purchase value component|
|DT_T012 Legacy data transfer: Post costs (negative)|1010 Post negative purchase value|


You first need to indicate the update types relevant for posting by choosing General Settings Accounting Link to Other Accounting Components Indicate Update Types as Relevant for Posting . You then choose Define Account Determination to determine the relevant account. You also need to indicate flows that are relevant for posting if you do not intend to post to the general ledger during the legacy data transfer.


For more information, see the documentation for the Customizing activities.

**Process Flow**

Scenarios: Background

You already use SAP Financial Accounting (FI) and now want to implement the Transaction Manager.

The legacy data to be transferred to the Transaction Manager is already posted in Financial Accounting. This means that no postings should be made to FI during the legacy data transfer.

Both SAP Financial Accounting (FI) and the Transaction Manager are implemented.

In this case, you have the following options:

You implement both components separately (so that no postings are made to FI during the legacy data transfer to the Transaction Manager).

Even if postings are not made to FI during the legacy data transfer, a posting log is still generated using the report Indicate Flows as Posted. You can then see the accounts in the FI area to which postings would have been made to reconcile the data. This

information is required for account assignment reference transfers at a later stage. The data is also available in the posting journal (transaction TPM20).


If you have generated the other accounting components by other means only up to the transfer key date, you can post the reset business transactions (for amortization, valuations, or accruals/deferrals) by making the setting Only Update Reset Business Transactions.


Note:

When transferring legacy data to the Financial Accounting area, you can use the functions in Customizing for Financial Accounting by choosing General Ledger Accounting Data Transfer Workbench .

See also: CA - Data Transfer

The Financial Accounting area is updated when legacy data is transferred from the Transaction Manager.

If you choose this option, you need to post the transactions using the transaction posting function (TBB1) and set the FI Update indicator during the legacy data transfer.

In this case, you should make sure that the flows usually relevant for payment are not paid. Limit the validity of the payment terms in the transactions to be transferred.

The following section assumes that the FI area is not updated (with the possible exception of reset flows) when legacy data is transferred to the Transaction Manager.

OTC Transactions

Preparation

Master data entry

Creating business partners in the required roles, such as the counterparty.

Setting up transaction authorizations or other standing instructions for the business partners.

See also:

Legacy Data Transfer: Process

Valuation area-independent information such as quantity information (units, nominal amounts,) the purchase value, costs, and accrued interest is transferred by entering transactions. Create the transactions and run through the process you selected to enter transactions. However, do not post the transactions.

You now need to indicate the transaction flows as posted for all valuation areas. You use a function within the legacy data transfer to do this. In Customizing for the legacy data transfer, choose Flow Data Indicate Flows as Posted .

The flows are indicated as being posted but are not actually posted. A posting log is generated.

The remaining position components are entered in the valuation area-dependent legacy data table ( Legacy Data Transfer Flow Data Enter Valuation Area-Dependent Data for Money Market, Forex, and OTC Derivatives Transactions .)

Note: Accruals/Deferrals

If a financial transaction has two different accrual/deferral values, you need to make two entries for this transaction.

Difference Method

If you transfer accruals/deferrals according to the difference method during the legacy data transfer, you must provide update types for the accrual/deferral function so that the system recognizes that a portion has already been accrued/deferred in the next accrual/deferral run.

Proceed as follows:

Call transaction SM30.

In the Table/View field, enter TRLIC AD EX.

Choose Maintain.

Make your required settings.

Save your entries.

Reset Procedure

In the case of accruals/deferrals made according to the reset procedure, you do not have to make additional settings since accruals/deferrals that are already available in the system are not included in the next accrual/deferral calculation.

When you execute the legacy data transfer, you can use the FI Update field to update the reset business transactions. Only the reset business transactions are updated in financial accounting.

Start the legacy data transfer ( Legacy Data Transfer Flow Data Execute Data Transfer ).

Securities Positions

Preparation

Create business partners in the required roles (such as issuer or counterparty). (Determine standing instructions for transaction authorizations.)

Create classes

Create securities accounts

See also:

Master Data Entry in the Securities Area

Legacy Data Transfer: Process

The subledger position indicator needs to be created for all positions that are to be transferred. You can choose from the following two options to create the subledger position indicator:

Create the subledger position indicator using the function Create Position Indicator in the area menu for the Transaction Manager by choosing Securities Master Data Position Indicator .

Enter the subledger position indicator in the legacy data table for positions. (In Customizing for the Transaction Manager, choose General Settings Tools Legacy Data Transfer Position Data Enter Position Information for Securities .) You then start


the legacy data transfer for positions (choose Legacy Data Transfer Position Data Execute Data Transfer for Positions ).

To transfer valuation area-independent information such as quantity information, purchase value and costs, and accrued interest, you can choose between the following two options:

Enter data in the valuation area-independent legacy data table ( Legacy Data Transfer Flow Data Enter Valuation AreaIndependent Data for Securities ).

Transfer valuation area-independent information by entering transactions.

Create the transactions and run through the process you selected to enter transactions up until the Settlement status.

See also: Security Transaction

You now need to indicate the transaction flows as posted for all valuation areas. You use a function within the legacy data transfer to do this. In Customizing for the legacy data transfer, choose Flow Data Indicate Flows as Posted .

Note:

Special Feature: Lots for Securities

If lots have been generated, you can choose between two different procedures:

Valuation Area-Independent Data Using the Legacy Data Table (Securities Only)

In this case, a number must be entered in the valuation area-independent table. This number must also be defined in the corresponding entry in the valuation area-dependent table. Prior to the valuation area-dependent business transaction being distributed, the system determines the lot ID of the valuation area-independent business transaction (identified by its number) that has already been distributed. The lot ID is then written into the valuation area-independent business transaction.

Valuation Area-Independent Data Using Transactions (Securities or Futures)

In this case, no entries are made in the table with valuation area-independent data.

To identify the lot, you need to enter the transaction number of the transaction that generated the lot, in the table with valuation area-dependent information. When the corresponding business transaction is generated, it is enhanced with the lot ID.

The remaining position components are entered in the valuation area-dependent legacy data table ( Legacy Data Transfer Flow Data Enter Valuation Area-Dependent Data for Securities ).

Special Feature: Accruals/Deferrals

Difference Method

If, during the legacy data transfer, you transfer accruals/deferrals according to the difference method, you must provide update types for the accrual/deferral function so that in the accrual/deferral run, the system recognizes that a portion has already been accrued/deferred.

Proceed as follows:

Call up transaction SM30.

In the Table/View field, enter TRLIC_AD_EX1.

Choose Maintain.

Make the required settings.

Save your entries.

Reset procedure

In the case of accruals/deferrals according to the reset procedure, you do not have to make additional settings since accruals/deferrals that are already available in the system are not included in the next accrual/deferral calculation.

Start the legacy data transfer ( Legacy Data Transfer Flow Data Execute Data Transfer ).

Futures

Preparation

Create business partners

Legacy Data Transfer: Process

Enter the open transactions.

You now need to indicate the transaction flows as posted up until the start date for all valuation areas. You use a function within the legacy data transfer to do this. In Customizing for the legacy data transfer, choose Flow Data Indicate Flows as Posted .

The remaining position components are entered in the valuation area-dependent legacy data table ( Legacy Data Transfer Flow Data Enter Valuation Area-Dependent Data for Futures ).

Start the legacy data transfer ( Legacy Data Transfer Flow Data Execute Data Transfer ).

Start the initial variation margin run.

Final Tasks

After the legacy data transfer has been completed, you should reconcile the general ledger and the subledger. To do this, you can use the posting journal which provides you with all the posting information.

If you want to use regulatory reporting for the Insurance Supervisory Authority, it first needs to be activated and initialized. In Customizing for the Transaction Manager, choose General Settings Information System Regulatory Reporting Settings for the Insurance Supervisory Authority .

**Result**

All the legacy data is in the system.

#### Initialization Guide - New Valuation Areas

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Initialization Guide - New Valuation Areas | L3 | trm01 p.107 | loio `6f06da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6f06da531198434de10000000a174cb4.html?locale=en-US)

**Purpose**

You can use the initialization process to generate new valuation areas in the Treasury subledger (Treasury Ledger).

The initialization covers the following products:

|Transactions|Securities|Loans|
|---|---|---|
|Fixed-Term Deposits|Stock|Mortgage Loans|
|Deposits at Notice|Investment Certificates|Borrower's Note Loans|
|Commercial Paper|Subscription Rights|General Loans|
|Cash Flow Transactions|Bonds| |
|Interest Rate Instruments|Redemption Bonds| |
|Spot/Forward Transactions|Convertible Bonds| |
|Caps/Floors|Warrant Bonds| |
|Swap|Warrants : Index /equity / currency / bond| |
|FRAs|Shareholdings| |
|OTC Options| | |
|Listed Options| | |
|Futures| | |


You always carry out the initialization of the Treasury Ledger (TRL Initialization) on a key date.

Business transactions are mapped for most of the product categories before the key date. They are mapped by an initial business transaction, rather than individually. This means the subledger position (TRL Position) is structured correctly for the key date. The system provides data, depending on the product group, to determine the initial business transactions.

All the flows that are to be transferred to the parallel valuation areas (TR Ledger) can be divided into:

The quantity of flows before the TRL initialization key date.

The quantity of flows after the TRL initialization key date.

This results in the following:

- 1. Exchange rate gains and valuations before the TRL initialization go into the initial business transaction on the key date. You map these flows using the update types that you defined in Customizing for the TRL initialization.
- 2. The system does not transfer valuations after the initialization key date to the new valuation areas. You must carry out this transfer yourself after the initialization. On the SAP Easy Access screen, choose Execute Valuation (transaction TPM1).
- 3. The system generates exchange rate gains and other valuation-independent flows for the business transactions after the initialization key date using the derived business transactions of the TRL. In this way the position components are used as the basis for the calculation of the initial values generated by the system (and in certain cases changed by the customers).


In order to ensure that the initial positions in the TRL cannot be changed at a later date, the system blocks all of the business transactions on the key date.

**Process Flow**

In order to initialize the parallel valuation areas, choose Initialize Parallel Valuation Areas (transaction TPM_INITIALIZE) on the SAP Easy Access screen. This transaction provides you with the following options:

Carrying out initializations for each company code, valuation area, and product group.

Splitting the transaction logic into single packages.

This ensures that you do not need to repeat the whole initialization process - just the incorrect step - if errors occur.

For an overview of the initialization process, see Schematic Initialization Process Flow.

**Procedure**

The individual product groups each have different initialization procedures.

For more information, see:

Initialization in the Area of Securities

Initialization in the Area of Loans

Initialization in the Areas Money Market, Forex and Derivatives

**Prerequisites**

The system generates proposals for the initial business transactions, based on specific data.

These proposals must be changed to meet the accounting requirements in the new valuation areas. This means that the position components (write-down, write-up, amortization) of the business transactions that were transferred to the TR Ledger need to be adjusted using the TRL initialization process. In doing this, the start values of the relevant valuation area are taken into account.

You will have to match the data from the external system if you manage your positions according to US GAAP in a different system. The positions in the TR Ledger will be managed on the basis of this data at a later stage.

The initial business transactions provided by the system are duplicated for each valuation area during the initialization process and then provisionally saved in a transparent database table. You can change this data according to the different start values (depending on the accounting principles).

You can also carry out the initialization of parallel valuation areas as a batch process. For more information, see Initialization Batch Planning.

**Result**

The values defined as start values by the initialization in parallel books are final.

##### Schematic Initialization Process Flow

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Initialization Guide - New Valuation Areas > Schematic Initialization Process Flow | L4 | trm01 p.109 | loio `b006da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b006da531198434de10000000a174cb4.html?locale=en-US)

Process flow

The main purpose of the technical TRL initialization process is to merge data extracted from the operative valuation area with data from external systems.

[figure TRM01-F019 - The main purpose of the technical TRL initialization process is to merge data extracted from the operative valuation area with data from external systems.]

##### Initialization in the Area of Securities

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Initialization Guide - New Valuation Areas > Initialization in the Area of Securities | L4 | trm01 p.109 | loio `0107da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0107da531198434de10000000a174cb4.html?locale=en-US)

Customizing

When you define a valuation area you specify the existing valuation area from which the proposal for the initial business transaction is to be determined.

In Customizing, choose Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Accounting Organization Assign Accounting Codes and Valuation Areas . The TRL initialization determines the position from the specified valuation area on the execution key date. This position is saved as the basis for the new valuation area in table TRLT_INIT_VAL_SE. The system also carries out consistency checks for the position in the initial valuation area.

Checks and Securities Account Group Assignments

This initialization step determines the position values for the operative valuation area and checks that these values are consistent. The position values are stored in database table TRLT_INIT_VAL_SE. The checks cover the following areas:

The system issues warnings if it finds short positions, positions with negative acquisition values or zero positions with book values greater or less than zero.

The system checks whether the positions match those in the quantity ledger.

If the securities account group has been defined as the differentiation factor for the parallel valuation area, the system generates securities account groups and assigns the securities accounts to these groups. It does this by analyzing the securities account groups in the operative valuation area, which may be dependent on the security ID number. You can change the securities account groups and the corresponding assignments manually.

Preparation of Legacy Data for Securities

This initialization step writes the position values determined in step 1 for the current valuation area to the database table TRLT_INIT_VAL_SE. The following positions are not transferred:

Positions with zero units and zero nominal values

Positions with product categories that have been excluded from the transfer to parallel positions in Customizing

Changing the Position Values for Securities

In this initialization step you can change the position values of the transferred positions. You can do this either manually or by means of a program.

To change the position values manually, change the entries in database table TRLT_INIT_VAL_SE using the data browser (transaction SE16) after executing the third initialization step.

If you want to have program-controlled changing of the position values, you can modify the function module TPM_TRL_MAINTAIN_BOOK_VAL_SE in order to transfer the position value changes to table TRLT_INIT_VAL_SE. To do this, see the instructions in the program text for the function module. Alternatively, you can create a new function module in the customer namespace using the module TPM_TRL_MAINTAIN_BOOK_VAL_SE as the copy reference. In this case, you must replace the entry for module TPM_TRL_MAINTAIN_BOOK_VAL_SE in database table TRGTS_INIT_FUNCT with the corresponding entry for the new module.

If you have the position values changed by a function module, the system makes the changes automatically as part of this third initialization step.

Generate Initial Business Transactions

The transactions and positions are now updated to the parallel valuation areas.

**Procedure**

- 1. At this point you have the option of adjusting the position management procedure and the account assignment reference for the transferred business transactions. The system takes your Customizing settings as default values.


- 2. The business transactions are now fixed and posted to the general ledger and special ledger. A posting log appears after each database commit with the business transactions posted to date.
- 3. The system generates derived business transactions for the existing business transactions and posts them if required.
- 4. The system blocks initial business transactions so that you can no longer make changes before the key date.


**Related Information**

Initialization Guide - New Valuation Areas

##### Initialization: Transactions - Money Market, Forex, Derivatives

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Initialization Guide - New Valuation Areas > Initialization: Transactions - Money Market, Forex, Derivatives | L4 | trm01 p.111 | loio `f406da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f406da531198434de10000000a174cb4.html?locale=en-US)

**Use**

For more information, see Initialization of Parallel Valuation Areas .

**Procedure**

The initialization of transactions is carried out on a key date in the same way as in the areas Securities and Loans .

The difference is that proposals for initial business transactions are not temporarily stored in a table for adjusting the start values to match the legal requirements.

Unlike the initialization for securities and loans, the key date in this case does not act as a block; meaning that you can continue to process business operations dated before the key date and can make changes to the position (such as rollovers) retrospectively.

Transactions in the areas of Money Market, Forex and Derivatives are duplicated 1:1 into the parallel valuation areas.

**Result**

Following the initialization you can adjust the book values of the transactions by means of a manual valuation to correspond to the required start values. On the SAP Easy Access screen, choose Enter Values for Manual Valuation (transaction TPM74).

The manual valuation option allows you to write-up or write-down a position to a fixed book value. You need to maintain these in the table TLVT_MANUAL_VAL in position currency and valuation currency. You can do this using a user-report or the maintenance view VALV_MANUAL_VAL. During the valuation run the system runs through the steps defined in the position management procedure, however it always writes up or writes down the position to the defined book value.

You can implement the manual valuation within the following:

Security valuation

Foreign currency valuation

One-step rate valuation

Index valuation

.

##### Initialization in the Area of Loans

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Initialization Guide - New Valuation Areas > Initialization in the Area of Loans | L4 | trm01 p.111 | loio `eb06da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eb06da531198434de10000000a174cb4.html?locale=en-US)

**Use**

For more information, see Initialization of Parallel Valuation Areas .

**Procedure**

The procedure is similar to that for Initialization in the Area of Securities . The system generates proposals for the initial business transactions, based on data in the operative valuation area.


The source valuation area that you defined in Customizing only applies to securities.

Some differencesmust be noted:

Loan data extracted from the operative valuation area is also subjected to a validation check. However here it checks if planned records exist for the positions to be transferred on the key date of the initialization.

The position values determined are extracted from the operative valuation area and written to the database table TRLT_INIT_VAL_ LO for each parallel valuation area.

Before the initialization for loans can be carried out you must assign a general valuation class to each loan contract. Each contract can then be updated per valuation area to the correct special valuation class.

Note that the initialization process includes steps that are both independent of and dependent on the company code.

##### Initialization Batch Planning

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Initialization Guide - New Valuation Areas > Initialization Batch Planning | L4 | trm01 p.112 | loio `d906da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d906da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The TRL initialization is not batch-enabled up to and including CFM 2.0. This is because the initialization was designed to enable you to manually intervene in the process:


For example, if you want to adjust the position values of the business transaction being transferred to correspond with the legal requirements of the required financial reporting procedure. Or if you want different account assignment references/position management procedures from the assignments defined in Customizing.

In SAPEnterprise you are able to schedule individual steps of the TRL initialization process as a batch job using the RTPM_TRL_INIT_BATCH report.The logs generated for each step are stored in the spool.

**Features**

The following selection parameters are available:

Product groups (securities/loans/OTC derivatives/listed derivatives)

Accounting code (= company code)

Valuation area

Initialization step

Key date (on which the initialization should be run)

Mode (update run/simulation/reversal/reversal simulation)

Reason for reversal

**Example**

No manual intervention is required during the initialization process. This means that the position components of the positions to be transferred are not adjusted. The default assignments for the account assignment references/position management procedures are transferred.

Procedure:

A batch job is defined for each initialization step (per combination of product group/accounting code/valuation area). The jobs are then scheduled as a job chain in the correct sequence.

#### Parallel Processing in the Transaction Manager

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Parallel Processing in the Transaction Manager | L3 | trm01 p.113 | loio `8d76795346efe747e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8d76795346efe747e10000000a441470.html?locale=en-US)

**Use**

To improve system performance in the following functions, you can use parallel processing:

Valuation (transaction TPM1/TPM2)

Legacy Data Transfer (transaction TPM61/TPM62/TPM63/TPM64)

Accrual/Deferral (transaction TPM44)

Update Planned Records for Securities (transaction FWUP)

Update Derived Business Transactions (transaction TPM27)

**Prerequisites**

In Customizing under Treasury and Risk Management Transaction Manager General Settings Parallel Processing Control , you specify the applications for which you want to use parallel processing. Further, you enter the control parameters for parallel


processing.

**Note:**

If you set the package size to 0 and do not set the Allow Users to Control Parallel Processing Parameters in the GUI indicator, parallel processing is deactivated for the application.

If you set the package size to 0 and set the Allow Users to Control Parallel Processing Parameters in the GUI indicator, you can activate parallel processing in the selection screen in the application by setting the package size to a value greater than zero.

If you want to deactivate parallel processing, you need to set the Parallel Processing On/Off indicator.

**Features**

Allow Users to Control Parallel Processing Parameters in the GUI

If you set this indicator for the applications Valuation, Accrual/Deferral, Update Planned Records for Securities, and Generate Derived Flows, the Customizing settings for parallel processing become visible in the transactions TPM1, TPM44, FWUP, and TPM27 (in the Multitasking Settings area), and changes can be made there to these settings.

If you do not set this indicator, parallel processing is always performed in accordance with the settings that you have made in Customizing.

This function offers the option of performing parallel processing differently, depending on the application and the data concerned. You can change the package size in the application independently of the relevant Customizing settings. You can change the number of tasks in the application; however, the upper limit that you have set in your Customizing settings is applied here. If this indicator is set and you have not activated parallel processing in Customizing, you can activate parallel processing in the application by setting the Use Multitasking indicator.

**Example:**

For the analysis, you can define two variants that apply different parallel processing settings for different company codes.

- Variant 1:

Company code: 0001

Package size: 50

- Variant 2


Company code: 0002

Package size: 10

#### Link to the Marketplace Using XI Interfaces

> **Path:** Treasury and Risk Management > Special Topics in Treasury and Risk Management > Link to the Marketplace Using XI Interfaces | L3 | trm01 p.114 | loio `190bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/190bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The Transaction Manager provides XI interfaces for automatically transferring transactions (for example, transactions concluded on an electronic marketplace).

In contrast to the existing BAPI interfaces, XI interfaces function independently of their Customizing settings, Customizing terms, and their organizational structure. It is sufficient for your business partner (a counterparty or a marketplace) to simply send you the structure characteristics of the transaction.

**Prerequisites**

SAP executes business mapping automatically as far as possible. However, user-specific mapping is also necessary (for customizable data). Four Business Add-Ins (BAdIs) exist for this purpose.

You can also use other transactions to map with the derivation tool. You can use the derivation tool to define assignments and derivation rules, without any special programming knowledge.

You use the BAdIs as follows:

When translating the external partner ID to the key in your business partner master data.

For defining terms based on your Customizing settings (for example, product types and transaction types).

The four BAdIs are located in Customizing under Transaction Manager General Settings Transaction Management External Link :

BAdI: Receive XI Message Type TreasuryDealNotification (FTR_XI_INTERFACE_MAPPING)

This gives you complete access to the TreasuryDealNotification interface or the enhancements.

BAdI: Receive Financial Transactions (General View) (FTR_XI_GENERAL_MAPPING)

This gives you access to flat structures that have already been processed. They facilitate mapping and handling.

The following XI derivation tools are also located here:

Define Mapping for General Transaction Information (to define a sequence that assigns or converts general transaction data).

Define Mapping for Spot Exchange and Forward Exchange Transactions (You can define a sequence to carry out assignments or conversions for spot exchange and forward exchange transactions).

Define Mapping for Forex Swaps (for defining a sequence to carry out assignments or conversions for foreign exchange swaps).

Define Mapping for Forex Options (You can define a sequence to carry out assignments or conversions for forex options).

**Features**

The following financial products from the Foreign Exchange Transactions area are currently supported:

Foreign Exchange Spot and Forward

Foreign Exchange Swap

Currency Options (plain vanilla)

See also:SAP XI Interface: TreasuryDealNotification

**Activities**

The received transactions are kept in different data structures during processing where they are then processed further. The following steps are carried out sequentially:

- 1. Internal SAP Step: The system converts the XI message and preassigns the EXT structures.
- 2. Call BAdI: FTR_XI_INTERFACE_MAPPING, Method MAPPING

You can implement this BAdI if, for example, you prefer the actual view of the TreasuryDealNotification message type or you have enhanced the interface with your own fields or elements.

- 3. Internal SAP Step: Default values of INT structures.
- 4. Call BAdI: FTR_XI_INTERFACE_MAPPING, Method GET_ID_TYPES: You provide SAP with the ID types to identify the business partner from the view of the provider (counterparty) or from the exchange.
- 5. Internal SAP Step: When you have informed SAP of your ID types, SAP attempts to select an existing business partner using this data and the external business partner ID included in the message.


See also:

For more information, see the business partner master data on the Identification tab page. You can then define alternative ID numbers and assign them to the ID types.

- 6. Call BAdI: FTR_XI_GENERAL_MAPPING, Method PRE_MAPPING

You can implement this BAdI so that you can, for example, perform checks and further steps that are only relevant after the business partner IDs have been converted.

- 7. Call Derivation Tool: This involves two sequences of steps:

- a. Sequence for general transaction information.
- b. Sequence to specifically map each financial product.


If you have not implemented any of these BAdIs up to now, you must convert the external partner IDs to the internal business partner IDs along with their company code (requestor), and assign a product type and transaction type. Other fields are optional.

- 8. Call BAdI: FTR_XI_GENERAL_MAPPING, Method POST_MAPPING

You can implement this BAdI so that you can, for example, perform checks and further steps that are only useful after processing in the derivation tool.

- 9. Internal SAP Step: You need to have specified all data in the required fields to create the transactions. BAPI interfaces are used to check and create the transactions.

