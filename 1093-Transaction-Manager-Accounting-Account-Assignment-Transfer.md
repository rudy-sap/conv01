# Transaction Manager > Accounting > Account Assignment Transfer - SAP TRM Knowledge Base (branch split)

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

##### Account Assignment Transfer (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Account Assignment Transfer | L4 | trm01 p.56 | loio `3a59393494a14c4da2f5247b2f4ee7b2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3a59393494a14c4da2f5247b2f4ee7b2.html?locale=en-US)

With this app, you can transfer the units/nominals of a treasury position to another position with different account assignments (such as cost center, WBS element, functional area, profit center). In this internal transfer, the position component values are transferred proportionally according to the transfer category of the target position management procedure.

The account assignment transfer is a position transfer. You can only execute the function if you use at least one of the following account assignments to differentiate your treasury positions:

Cost center

WBS element

Functional area

Profit center

**Note:**

If you have activated Public Sector Management and use the fund and grant account assignments as differentiation criteria for your treasury positions, the account assignment transfer can also be used to transfer a treasury position from one fund to another or from one grant to another.

For more information, see also Differentiation Terms.

**Key Features**

This app provides the following key features:

You can transfer positions to another account assignment, such as a fund, grant, cost center, WBS element, functional area, or profit center for treasury positions. You can either execute the account assignment transfer as an internal transfer or as an external transfer:

Internal transfer

The usual way to perform an account assignment transfer for treasury positions is an internal transfer. During the internal account assignment transfer, the units/nominals are transferred from the source position to the target position, including the position component values that are transferred proportionally by derived business transactions taking into account the transfer category of the target position management procedure. For more information, see also Transfer Category.

External transfer

If you treat the account assignment transfer as an external transfer, the transfer is executed in the same way as a sale from the source position and a purchase to the target position. In this case, the realized gains and losses are

calculated. If the Calculate Accrued Interest indicator is set when the account assignment transfer is executed, accrued interest is also calculated.

You can also transfer partial positions.

You can enter the incoming or outgoing payment amounts in position currency.

**Customizing**

In the Customizing of Treasury and Risk Management, you must make the following settings:

Define Update Types and Assign Usages

Define the update types for the position outflow and the position inflow of the account assignment transfer and assign them to the Account Assignment Transfer usage.

Assign Update Types for Account Assignment Transfer

You must assign update types for the internal and for the external account assignment transfer in the Assign Update Types for Account Assignment Transfer Customizing activity that is available in the Customizing of the Transaction Manager under General Settings Accounting Account Assignment Transfer .

For the internal account assignment transfer, you must assign update types for both the position outflow and the position inflow.

For the external account assignment transfer, you must assign update types for the Main Flows and the Accrued Interest Flows:

For the Main Flows, you enter update types for the following cases:

Asset: Position Outflow

Asset: Position Inflow

Liability: Position Outflow

Liability: Position Inflow

For the Accrued Interest Flows, you enter update types for the following cases:

Asset: Position Outflow

Asset: Position Inflow

Liability: Position Outflow

Liability: Position Inflow

You also must choose the exchange rate type for currency conversions.

Set Effects of Update Types on Position Components

**Procedure**

- 1. Open the Account Assignment Transfer app.
- 2. By choosing one or more product groups, you can select the positions for these groups.

In addition to selecting the product groups, you can use the general selections to select the individual positions.

- 3. Enter the selection criteria for the positions to be transferred:


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

You can restrict the selection further using the following product-group-dependent fields.

**Note:**

The only product groups displayed are those that were selected in the Product Groups area.

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

- 4. Enter the key date for the position transfer. By default, the current date is entered in this field.
- 5. Set the External Transfer indicator, if you want to execute the transfer like a sale from the source position and a purchase in the target position. In this case, the realized profits and losses (and accrued interests if the Calculate Accrued Interest indicator is set) are calculated. The following indicators are available for the external account assignment transfer:

You can set the Key Date Is Month End indicator. If you selected this indicator and if the relevant date is the last day of the month, that date is regarded as the month end for corresponding interest calculation methods.

The Calculate Accrued Interest indicator, controls whether to calculate accrued interest for the transfer posting.

If the indicator is set, the system calculates accrued interest. This applies to interest-bearing instruments, such as bonds and also money market transactions or interest rate swaps.

The Including Key Date indicator controls whether or not the key date is within the time period in question.

The indicators are set by default. You can change the default setting.

- 6. Specify the concrete values for the differentiation terms of the target positions if they apply to all the selected positions.
- 7. All the selected positions are displayed on the following screen. On this screen, you can exclude other positions from being transferred. You can also change the nominal amount or specify whether only a partial position is transferred.
- 8. Choose Execute. The system displays a list of all the selected positions with their status and indicates whether the positions were successfully transferred. To view any error messages, click on the status icon. To display the posting log, choose Messages and Log.


**Note:**

We recommend that you first execute a test run. The system then displays the transfer log for the test run. Choose Back and execute the update run.

Reversing the Account Assignment Transfer

Use the Reverse Account Assignment Transfer to reverse an account assignment transfer.

###### Reverse Account Assignment Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Account Assignment Transfer > Reverse Account Assignment Transfer | L5 | trm07 p.159 | loio `5686bd9bc87c49d98e0fd7dcfc78fff6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5686bd9bc87c49d98e0fd7dcfc78fff6.html?locale=en-US)

You use this app to reverse an account assignment transfer.

For more information, see also Account Assignment Transfer.

**Activities**

- 1. Specify a product group.
- 2. Specify the key date of the account assignment transfer to be reversed.
- 3. Specify the reason for reversal.
- 4. You can enter a specific FI reversal date or FI reversal period.
- 5. You can run the account assignment transfer as a test run.
- 6. Run the report.
- 7. The system displays the selected transfers instead of the positions.
- 8. Perform the reversal.


**Result**

The account assignment transfer is reversed.

