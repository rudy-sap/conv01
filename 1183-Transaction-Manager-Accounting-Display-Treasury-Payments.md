# Transaction Manager > Accounting > Display Treasury Payments - SAP TRM Knowledge Base (branch split)

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

##### Display Treasury Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Display Treasury Payments | L4 | trm08 p.184 | loio `fdc18726553148baad0ccaf53b3515b9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fdc18726553148baad0ccaf53b3515b9.html?locale=en-US)

App ID: TPM20A

With this app, you can display a list of treasury payments for OTC transactions, listed derivatives, securities, and external accounts.

**Key Features**

You can use this app to:

Display a list of treasury payments according to your selection criteria

Navigate to the original business transaction

Display the details of each payment in a separate dialog window

Define the layout by choosing and arranging report columns

Export the list of payments to a spreadsheet

Save your selection criteria as a variant

**Procedure**

- 1. Open the Display Treasury Payments app from the SAP Fiori launchpad.
- 2. Choose the relevant product groups.
- 3. Enter the general selection criteria for the positions to be transferred:


**Note:**

If you don’t choose a product group, no treasury positions are selected.

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

External Accounts

External Account

Currency

- 4. Enter the relevant payment data, such as the payment date or payment currency.
- 5. Select whether you want to include paid and/or reversed business transactions.
- 6. Run the app.


**Supported Device Types**

Desktop

Tablet

