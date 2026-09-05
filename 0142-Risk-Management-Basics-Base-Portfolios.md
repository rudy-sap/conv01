# Risk Management > Basics > Base Portfolios - SAP TRM Knowledge Base (branch split)

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

##### Base Portfolios

> **Path:** Treasury and Risk Management > Risk Management > Basics > Base Portfolios | L4 | trm02 p.29 | loio `1602c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1602c55368511d4be10000000a174cb4.html?locale=en-US)

**Definition**

A base portfolio is the smallest valuation unit in structured reports for risk analysis. A base portfolio is determined for every combination of characteristic values.

Base portfolios are purely technical objects, created by the system when external data transfers take place or during financial object integration. You do not have to create this object anywhere in the system yourself, nor do you have to make assignments between the base portfolio and other objects.

**Use**

By choosing the segment characteristics, you define the sort criteria used by the system to group together transactions in base portfolios. This means that the evaluation results of those financial transactions with identical combinations of characteristic values are grouped together in one base portfolio.

Within base portfolios, cash flows for similar bank transactions can be aggregated.

###### Displaying Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Base Portfolios > Displaying Transactions | L5 | trm02 p.30 | loio `1c02c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1c02c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

This report delivers a list of all financial transaction data in your portfolio and gives an overview of the cash flows resulting from the portfolio.

**Procedure**

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Information System Single Value Analyses

Transaction View Display Transactions .

The system displays the selection screen Transaction Display.

- 2. In the tab page General Selections define the base portfolio you want to examine by entering the View and the Portfolio Hierarchy. You can restrict the analysis to one Portfolio Hierarchy Node or, by setting the relevant indicator, you can display Summarized Data Only.
- 3. You can also restrict the transactions by entering certain characteristic values in the tab page Characteristics.
- 4. Choose Execute.


**Result**

The transactions are displayed in an ALV list and sorted by object category and transaction number. In the left-hand part of the screen you are able to navigate through the portfolio hierarchy.

Possible Actions

|Action|Function|
|---|---|
| Trans.Val.|The system displays the cash flows of the transaction.|
| Display RO|The system displays the internal risk object of the transaction.|
|Selection of a transaction (by double clicking)|The system displays the master data of the transaction.|


**Note:**

You can also run the report in batch mode. Note, however, that in this case the characteristic values are shown in the header, and it is not possible to navigate to the transaction master data.

