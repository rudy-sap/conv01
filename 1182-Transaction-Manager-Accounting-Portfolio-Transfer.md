# Transaction Manager > Accounting > Portfolio Transfer - SAP TRM Knowledge Base (branch split)

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

##### Portfolio Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Portfolio Transfer | L4 | trm08 p.182 | loio `d40bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d40bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use the portfolio function to transfer securities positions that are differentiated by portfolio to other portfolios.

**Prerequisites**

You have defined portfolios for the respective company code in Customizing for the Transaction Manager under General Settings Organization Define Portfolio .

You have differentiated your securities positions according to portfolios. These settings are made in Customizing for the Transaction Manager by choosing General Settings Accounting Settings for Position Management Define and Assign Differentiations. . Enter the portfolio when defining a differentiation and then assign the differentiation to the respective accounting codes.

You must have defined and assigned the update types for the portfolio transfer accordingly. Make the required settings for the activities in Customizing for the Transaction Manager by choosing General Settings Accounting Portfolio Transfer Update Types .

**Features**

You can use the portfolio transfer function for individual or multiple securities positions.

You can transfer securities positions either fully or partially to other portfolios.

For each portfolio transferred, the system generates a derived business transaction that transfers the corresponding position values.

You can reverse the portfolio transfer at any time using the Reverse Portfolio Transfer function (transaction TPM83).

**Activities**

- 1. Choose Treasury and Risk Management Transaction Manager Securities Accounting Portfolio Transfer Execute Portfolio Transfer (TPM82).
- 2. Enter your selection criteria for the positions to be transferred.


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

Securities

ID number

Securities account

Securities account group

Portfolio (position)

OTC Transactions [MM, FX, OTC Derivatives, TF Transactions]

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

- 3. To transfer all the positions to a portfolio at the same time, you need to specify this portfolio as the target portfolio.
- 4. Choose Execute.
- 5. The system lists the selected positions. You can also choose to exclude individual positions from being transferred.


The system proposes that you transfer the total nominal amount or the total number of units. For partial transfers, you need to specify the amount to be transferred. Assign each position a target portfolio and then execute the transfer.

- 6. To reverse the portfolio transfer, choose Treasury and Risk Management Transaction Manager Securities Accounting Portfolio Transfer Reverse Portfolio Transfer (TPM83). The reversal process is the same as the transfer


process. However, the system displays the selected transfers instead of the positions. You do not have to make any more entries for the reversal.

