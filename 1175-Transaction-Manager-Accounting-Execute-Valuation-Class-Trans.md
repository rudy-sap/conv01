# Transaction Manager > Accounting > Execute Valuation Class Transfer - SAP TRM Knowledge Base (branch split)

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

##### Execute Valuation Class Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Execute Valuation Class Transfer | L4 | trm08 p.164 | loio `ea0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ea0ada531198434de10000000a174cb4.html?locale=en-US)

- App ID: TPM15M


You can use this app to reassign treasury positions from one valuation class to another.

You can use the valuation class transfer function for individual or multiple positions.

**Note:**

Loan positions, however, can only be transferred individually.

You can reverse the valuation class transfer.

**Prerequisites**

You have defined and assigned the general valuation classes to the special valuation classes in the Customizing for the Transaction Manager under General Settings Accounting Settings for Position Management Define and Assign Valuation Classes . For more information, see also General and Special Valuation Classes.

You have defined and assigned the update types accordingly. Make the required settings in Customizing for the Transaction Manager by choosing General Settings Accounting Valuation Class Transfer Update Types .

There cannot be any fixed business transactions after the key date of the transfer for the positions involved, except for derived business transactions and other transfers.

**Activities**

- 1. Open the Execute Valuation Class Transfer app on SAP Fiori launchpad.
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

- 4. Specific Selections for Outgoing Position

You can select positions according to either their general valuation class or special valuation class for a particular valuation area.

- 5. Transfer Posting Parameter

Target Valuation Class

To transfer all the positions collectively to one general valuation class, you need to specify this valuation class as a target valuation class.

Key Date

Proposal Category

- 6. The system lists the selected positions. You can then choose to exclude individual positions from being transferred.
- 7. The system proposes that you transfer the total nominal amount or the total number of units. For partial transfers, you need to specify the amount to be transferred. Assign each position a target valuation class and then choose Execute to make the transfer.


**Note:**

If you use the integration with Public Sector Management, the system automatically derives the values for the fields fund, grant, functional area, and profit center from the master data records of the assigned cost center or WBS element, when you enter the cost center and the WBS element,

For more information, see also Integration with SAP Public Sector Management (PSM).

**Note:**

The only product groups displayed are those that were selected in the Product Groups area.

We recommend that you first carry out a test run. From the menu bar, choose Test Run: Transfer.

The system always displays the positions with the general valuation class. You can check which special valuation classes are in the valuation areas both before and after the transfer by choosing Special Valuation Classes in the corresponding line.

- 8. During the valuation class transfer, the units/nominals are transferred from the source position to the target position, including the position component values that are transferred proportionally by derived business transactions taking into account the transfer category of the target position management procedure. For more information, see also Transfer Category


As of the next period-end closing, the transferred position is now valuated according to the settings of the target position management procedure.

**Valuation Class Transfers in the Loans Area**

- 1. In the area menu, choose Bank Applications Loans Management Accounting Closing Operations Parallel Valuation Areas Valuation Class Transfer Execute Valuation Class Transfer (transaction TPM15).
- 2. Choose the source and target position using the special valuation classes. You can specify whether the transfer is only to be made for a selected valuation area. Once you have selected a position, the system proposes general valuation classes that are suitable for the transfer.


**Supported Device Types**

Desktop

Tablet

**Related Information**

Differentiation Terms Treasury Position General and Special Valuation Classes

###### General and Special Valuation Classes

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Execute Valuation Class Transfer > General and Special Valuation Classes | L5 | trm08 p.166 | loio `d10bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d10bda531198434de10000000a174cb4.html?locale=en-US)

General valuation classes classify financial transactions across all valuation areas.

Examples:

Short-term investments

Medium-term investments

Liabilities

Special valuation classes classify financial transactions/positions based on a valuation area.

They represent the areas of a balance sheet as well as the differentiation terms in the system.

Examples:

At Fair Value through Profit or Loss

Trading

Available for Sale (AfS)

Held to Maturity (HtM)

Liabilities

Current Assets

**Assignment**

Each general valuation class is assigned to a special valuation class which defines a subledger position.

When you enter a transaction, you specify a general valuation class and also, indirectly, the corresponding position.

**Note:**

The assignment of the (special) valuation classes to the position management procedure determines how a position is valued. Because in Customizing for the Transaction Manager under General Settings Accounting Settings for Position Management Assign Position Management Procedure , you can assign the position management procedure dependent on the valuation class.

Examples of Assignments

|Valuation Areas| |(Special) Valuation Classes|
|---|---|---|
|001|IFRS|1 At Fair Value through Profit or Loss|
|001|IFRS|2 Available for Sale|
|002|US GAAP|1 Trading|
|002|US GAAP|2 Available for Sale|
|003|Local GAAP|1 Current Assets|
|003|Local GAAP|2 Fixed Assets|


**Configuration**

You make your settings for the valuation classes in Customizing for the Transaction Manager under General Settings Accounting Settings for Position Management Define and Assign Valuation Classes .

