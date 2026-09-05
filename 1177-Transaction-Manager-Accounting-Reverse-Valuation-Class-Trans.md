# Transaction Manager > Accounting > Reverse Valuation Class Transfer - SAP TRM Knowledge Base (branch split)

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

##### Reverse Valuation Class Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Reverse Valuation Class Transfer | L4 | trm08 p.167 | loio `361892ba06604829a86ef0df73e72d89` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/361892ba06604829a86ef0df73e72d89.html?locale=en-US)

- App ID: TPM16M


With this app, you can reverse a valuation class transfer.

The reversal process is the same as the transfer process. However, the system displays the selected transfers instead of the positions. You do not have to make any more entries for the reversal.

For more information, see also Execute Valuation Class Transfer

**Activities**

- 1. Open the app Reverse Valuation Class Transfer on SAP Fiori launchpad.
- 2. Product Groups

You can choose between the different product goups for which you want to change the status of derived business transaction flow:

Securities

OTC Transactns

By choosing one or more product groups, you can select the positions for these groups.

In addition to selecting the product groups, you can use the general selections to select the individual positions.

- 3. Enter the general selection criteria for the positions to be transferred:

Company Code

Choose the appropriate company code.

Product Type

If you use the following fields as differentiation terms for your position, you can select positions by these fields:

WBS Element

Cost Center

Profit Center

Functional Area

If you have defined your own differentiation terms (in the Define Custom Differentiation Terms configuration activity) and you use the fields as differentiation terms for your treasury positions, these fields are also available as selection criteria.

The following fields are available if Public Sector Management is used. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the journal entry:

Fund

Grant

- 4. Transfer Posting Parameter


**Note:**

If you use the integration with Public Sector Management, the system automatically derives the values for the fields fund, grant, functional area, and profit center from the master data records of the assigned cost center or WBS element, when you enter the cost center and the WBS element,

For more information, see also Integration with SAP Public Sector Management (PSM).

**Note:**

The only product groups displayed are those that were selected in the Product Groups area.

Key Date

Outgoing Valuation Class

Target Valuation Class

- 5. Posting Data

Enter theReason for Reversal .

Enter the FI Reversal Date.

Enter the FI Reversal Period.

Test Run

We recommend that you first carry out a test run. From the menu bar, choose Test Run: Transfer.

- 6. The system lists the selected valuation class transfers.


**Reversal of Valuation Class Transfers in the Loans Area**

- 1. In the area menu, choose Bank Applications Loans Management Accounting Closing Operations Parallel Valuation Areas Valuation Class Transfer Reverse Valuation Class Transfer (transaction TPM16).
- 2. Choose the source and target position using the special valuation classes. You can specify whether the transfer is only to be made for a selected valuation area. Once you have selected a position, the system proposes general valuation classes that are suitable for the transfer.


**Supported Device Types**

Desktop

Tablet

