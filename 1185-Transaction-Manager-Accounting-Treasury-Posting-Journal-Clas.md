# Transaction Manager > Accounting > Treasury Posting Journal - Classic - SAP TRM Knowledge Base (branch split)

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

##### Treasury Posting Journal - Classic

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Treasury Posting Journal - Classic | L4 | trm08 p.187 | loio `fc07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fc07da531198434de10000000a174cb4.html?locale=en-US)

App ID: TPM120

**Use**

The Treasury Posting Journal - Classic provides detailed information about the posted flows of selected financial transactions. It displays in particular the posting type, the posting key, and the relevant accounts.

**Features**

Unlike the posting overview, only the flows that have been posted with the related accounts are shown here.

Select only posted business transaction

Select only reversed business transactions

Select posted and reversed business transactions

Define your own list layouts

**Activities**

- 1. Open the Treasury Posting Journal - Classic app on SAP Fiori launchpad or call transaction TPM20 in the area menu of the specific areas, such as money market, foreign exchange, or securities under Information System Accounting .
- 2. You select the relevant financial transactions by Product Groups and the General Selection Criteria and the specific selection criteria of the product groups.


Company Code

Choose the appropriate company code.

Valuation Area

You can restrict the selection of positions to individual valuation areas.

Product Type

Valuation Class

If you use the following fields as differentiation terms for your position, you can select positions by these fields:

WBS Element

Cost Center

Profit Center

Functional Area

If you have defined your own differentiation terms (in the Define Custom Differentiation Terms configuration activity) and you use the fields as differentiation terms for your treasury positions, these fields are also available as selection criteria.

The following fields are available if Public Sector Management is used. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the journal entry:

Fund

Grant

**Note:**

WBS element, cost center, profit center, and functional area are additional differentiation criteria available for OTC transactions and securities.

**Note:**

The only product groups displayed are those that were selected in the Product Groups area.

Securities

ID number

Securities account

Securities account group

Portfolio (position)

Listed Derivatives

SecurityClass ID No.

Futures Account

Long/Short Position

For some reports, this field isn't available.

Lot-Generating Transaction No. (not in all reports available)

For some reports, this field isn't available.

OTC Transactions (MM, FX, OTC Derivatives, TF Transactions)

Transaction number

Transaction type

Portfolio

Facility

Assignment

Internal reference

Characteristics

Finance project

Activity category

Business partner

Active status

External account

Hedging classification

**Loans**

Contract Number

External Accounts

External Account

Currency

Exposure Items

Exposure Item ID

Exposure Subitem ID

Additional Selection Criteria

Financial Transaction

Hedging Relationship Number

**Note:**

For some reports, this area isn't available.

Select from OTC Transaction.

If you set this indicator, the field for entering financial transaction numbers is no longer ready for input. The system now searches for the exposure items by the financial transactions selected using the fields in the OTC Transactions group.

**Note:**

For some reports, this indicator isn't available.

- 3. Enter your criteria to select the financial transactions you require and their related flows:


In the Posting Data area, you can select the posting flows by posting specific data, such as Business Trans. Cat., Update Type, Account Assignment Reference, Posting Category, and Account Symbol.

In the Posting Data FI area, you can select the posting flows by posting specific data of the FI, such as Posting Date, Posting Period, Fiscal Year, Reference Document, Reference Org. Unit, Reversal Date, Reversal Period, G/L Account, and Customer.

In the User Data area, you can select the flows by user data, such the Last Changed By and Last Edited On.

In the Other Selections area, you can choose whether you would like to see the posted business transactions or the reversed business transactions or both. If you choose the Reversed Business Transactions, two radio buttons are available, which allow to either display Only Reversed Postings or Original and Reversal Postings in separate lines.

If you choose Only Reversed Postings, you get the original flows, which have the posting status Reversed.

If you choose Original and Reversal Postings, system displays the original flows, which have the posting status Reversed and in addition the reversal flows, which have the posting status Reversed (Reversal).

- 4. Choose a layout.
- 5. Choose Execute.
- 6. The system displays a list of flows according to your selection criteria.


The usage to the SAP List Viewer enables you to choose your own layout for the result list of the posting journal using different characteristics and evaluations. You can save the display variants you have defined and call them up again at any time.

You can display the original business transaction.

You can jump to the document.

