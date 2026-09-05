# Transaction Manager > Accounting > Period-End Closing - SAP TRM Knowledge Base (branch split)

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

##### Period-End Closing (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing | L4 | trm08 p.2 | loio `67980b1daaf449f0b9403768d2bc61ab` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/67980b1daaf449f0b9403768d2bc61ab.html?locale=en-US)

Several apps are available to suppport you during the period-end close.

Accrual/Deferral of Expenses and Revenues

Overview: Calculating NPVs in TRM

Valuation

###### Accrual/Deferral of Expenses and Revenues

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Accrual/Deferral of Expenses and Revenues | L5 | trm08 p.2 | loio `c272c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c272c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

You use the Execute Accrual/Deferral app to determine expenses and revenues from financial transactions or positions for a given period and to assign them to the correct accounting period, irrespective of when they were due.

**Integration**

Accruals and deferrals are prerequisites for period-end closing in Financial Accounting.

**Customizing**

Define Update Types and Assign Usages

You need to specify the update types required to make accruals/deferrals and assign them to the usage Accrual/Deferral.

Assign Update Types for Accrual/Deferral

Define which revenue flows can be accrued for which positions or transactions and how (which accrual/deferral procedure or method).

Accruals/deferrals are only possible for update types for interest, accrued interest, fees, and any other profit-related flows with the following attributes:

Term from

Term to

Maturity

Amount

Days calculation method (in the case of interest payments, this can be derived from the interest calculation method)

Block

Here you also specify whether a block is set for the accrual/deferral.

If you want to set a block, you can still decide whether the system displays a warning message or an error message when a conflict occurs. A conflict involves a position that has already been accrued or deferred and the necessary adjustment of the resulting accrual/deferral.

If you choose to set a block and display an error message, you can perform the activity only after reversing the accrual/deferral.

If you don’t set a block, you can simply execute the activity. The next position accrual/deferral is then adjusted.

Grouping

You can use the grouping term (defined in the Assign Update Types for Accrual/Deferral configuration activity) in the following way:

You can jointly accrue/defer (positive and negative) flows of the same update type and with different update types and different accrual deferral methods (such as linear, pro rata) for a position or financial transaction. You can do this by making the same entry in the Grouping field for update types that are to be accrued/deferred together.

Reset procedure: Profit-related flows with the same direction must have the same accrual update types. The accrual update type is chosen based on the resulting direction. If the accrual of the incoming flows is higher than the accrual of the outgoing flows, then the accrual update type for the incoming flows is used.

Example: Configuration

|Profit-Related Update Type|Accrual Update Type|Reset Update Type|
|---|---|---|
|DE1200+|AD1000|AD1001|
|DE1201+|AD1000|AD1001|
|DE1200-|AD1002|AD1003|
|DE1201-|AD1002|AD1003|


Difference procedure: Profit-related flows with the same direction must have the same accrual update types. In addition, the update type for the positive accrual of incoming flows has to be the same as the update type for offsetting (negative) accruals, and vice versa.

Example: Configuration

|Profit-Related Update Type|Positive Accrual Update Type|Negative Accrual Update Type|
|---|---|---|
|DE1200+|AD1004|AD1005|
|DE1201+|AD1004|AD1005|
|DE1200-|AD1005|AD1004|
|DE1201-|AD1005|AD1004|


However, you must make sure that update types to be jointly accrued/deferred have the same type of revenue and the same currency. Flows with different currencies are always accrued/deferred separately.

Examples:

A financial transaction has a variable interest condition with a semi-annual interest period and daily interest rate adjustment. If you execute the accruals/deferrals on a monthly basis, then only one accrual/deferral flow is created as opposed to one being created for each interest flow.

You must use the grouping term to accrue/defer interest flows with the interest categories Compound Interest Calculation and Average Compound Interest Calculation.

If you haven’t defined a grouping term, flows in a financial transaction or position that are relevant for accrual/deferral and that have different update types are accrued or deferred separately.

You need to indicate update types as being relevant for posting and define settings for account determination.

**Features**

Accrual/Deferral Procedures:

Reset Procedure

In the reset procedure, the profit-related flows are posted as affecting net income. Income is adjusted during accrual/deferral, and the amount not yet affecting net income is posted as a liability or asset. The amounts (for Accruals and Deferrals) are determined and posted on a key date before being cleared (reset). If an income statement is output in the meantime, it contains the profit or loss that occurred during the calculation period.

Difference Procedure

With the difference procedure, the profit-related flow is posted to an asset or liability item on the due date without affecting net income. These items are then accrued/deferred gradually, affecting net income by degrees.

Discounts and premiums are accrued/deferred using the difference procedure. They’re generally posted directly to the accrual accounts. The item is then written off proportionally and posted to revenues/expenses using the accrual/deferral function. The accrual/deferral amount is based on the period between the last accrual/deferral run and the key date of the current accrual. In this case, there’s no reset posting.

**Note:**

Unscheduled writebacks as a result of unscheduled repayments or partial sales are disclosed separately.

**Note:**

If the payment date (due date) for a profit-related flow is in the middle of the calculation period, then it is at this time that the accrual becomes deferred. Consequently:

If the accrual/deferral key date is before the payment/due date, the flow is accrued.

If the accrual/deferral key date is after the payment/due date, the flow is deferred.

The reset procedure meets this requirement.

A profit-related flow can’t be accrued/deferred using the difference procedure.

Accrual/Deferral Methods

Profits/losses incurred up to the key date are determined using the accrual/deferral method for each profit-related flow.

Linear

The linear accrual/deferral method is used to calculate the amounts to be accrued/deferred:

Accrual/deferral amount = Total amount x days* / total number of days*

Pro Rata

The accrual/deferral amount is calculated according to the formula used to calculate the interest flow to be accrued/deferred. The calculation is either on a linear or exponential basis.

The number of interest days is calculated on the basis of the 'calculated from' date and the accrual/deferral key date.

Complete

The income amount is accrued/deferred in its entirety, regardless of the key date. This function is required, for example, to accrue/defer dividends in accordance with US GAAP.

If the key date is before the calculation period of the profit-related flow, then accrual/deferral of the total amount is executed.

If the key date is within the calculation period of the profit-related flow (or, in the case of a difference procedure, even if the key date is after the calculation period), then the total amount is accrued/deferred.

Complete until Key Date

The income amount is accrued/deferred in its entirety until the key date.

If the key date is before the calculation period of the profit-related flow, then no accrual/deferral is made.

If the key date is within the calculation period of the profit-related flow (or, in the case of a difference procedure, even if the key date is after the calculation period), then the total amount is accrued/deferred.

Brazil Tax Calculation

This method is only required for accruals/deferrals of Brazil tax flows. The accrual/deferral amount is calculated according to the formula used to calculate Brazil taxes (such as financial operation tax (IOF) and withholding tax (IRRF)).

Pro Rata with Linear Discounting

This method is only used for Commercial Paper. The total amount is first accrued/deferred (pro rata) over the calculation period and then discounted on a linear basis. The system uses the following formula to calculate the discounting factor:

For accrual:

1 + interest rate of profit-based flow / 100 * (days in period- D) / base days

For deferral:

1 + interest rate of profit-based flow / 100 * D / base days

D is the number of days between the start of the calculation of the profit-based flow and the accrual/deferral key date.

**Note:**

The days calculation method defined for the position or the flow to be accrued/deferred is used to determine the days / total number of days. The days calculation method is derived from the interest calculation method.

Calculating the Accrual/Deferral Amount in Position Currency

The amount in time is first calculated and then applied as the basis for calculating the amount to be accrued/deferred.

[figure TRM08-F001 - Reset Procedure]

Reset Procedure

With this procedure, the accrual/deferral method selected is used to determine the amount in time for the flow to be accrued/deferred. The resulting accrual/deferral amount depends on whether the item is an accrual or a deferral. In the case of accruals, the amount in time corresponds to the accrual amount. In the case of a deferral, the deferral amount is the amount in time subtracted from the total amount of the flow.

Difference Procedure

With this procedure, the accrual/deferral method selected is used to determine the amount in timefor the flow to be accrued/deferred. This is compared with the total amounts calculated for all previous accruals/deferrals. This accrual/deferral amount is the difference resulting from both amounts.

If the accrual/deferral amount is negative, the system generates an adjustment flow (update type Offsetting Flows for Accrual/Deferral).

Converting the Accrual/Deferral Amount into Valuation Currency

The amount in time and the accrual/deferral amount are first calculated in position currency. If the position currency differs from the valuation currency, the amounts are converted into the valuation currency.

The following rates are used:

Accrual

This is translated using the market rate.

Exception: If the flow to be accrued/deferred has already been posted with the difference procedure, the system uses the rate resulting from the amounts of the flow to be accrued/deferred.*

Deferral

The system uses the rate that is derived from the amounts of the flow to be accrued/deferred.*

*The difference procedure is as follows:

The amount in time in position currency is translated into the valuation currency using the rate resulting from the amounts of the flows to be accrued/deferred. Previous accruals/deferrals are then subtracted to give the amount to be accrued/deferred in valuation currency.

The accrual/deferral amount in position currency is then translated using the current market exchange rate. This amount is then posted as an accrual/deferral.

To obtain the total amount relevant for accrual/deferral in the valuation currency, the system generates a corresponding write-up or write-down flow.

**Example:**

A profit-related flow in foreign currency is posted with the exchange rate 1.2000 on 01/02 (USD 100 / EUR 120).

Accrual/deferral occurs at a later date (12/31). On the accrual/deferral key date, the exchange rate is 1.0000. The system generates the following flows:

Accrual/deferral flow USD 100 / EUR 100

Adjustment flow (write-down) USD 0 / EUR 20

The difference procedure is as follows when you translate into the valuation currency:

The amount in time is translated into the valuation currency using the current market rate. Previous accruals/deferrals are then subtracted to produce the amount to be accrued/deferred in valuation currency.

The accrual/deferral amount in position currency is then translated using the current market exchange rate. This amount is then posted as an accrual/deferral.

To obtain the total amount relevant for accrual/deferral in the valuation currency, the system generates a corresponding write-up or write-down flow.

The difference procedure may produce inconsistencies in the accruals/deferrals accounts or the payables and receivables accounts.

Additional Notes

Accruals/deferrals can be performed according to valuation area.

For each selected position/transaction and for a given key date, the system determines the profit-related flows for which accruals or deferrals need to be created. This means all flows intended for accrual/deferral and for which the accrual/deferral key date is within the flow calculation period.

In the case of variable interest flows that have not yet been fixed, the system determines the interest rate on the basis of the planned record update strategy. If you do not want to accrue/defer non-fixed variable interest flows, set the Only Fixed Interest Flows indicator.

Variable interest flows with the interest calculation types Compound Interest Calculation and Average Compound Interest Calculation:

You must use the grouping function for positive and negative interest flows. You enable this function in the Assign Update Types for Accrual/Deferral configuration activity in your configuration environment.

For variable interest flows with the interest calculation types Compound Interest Calculation and Average Compound Interest Calculation, you must ensure that the current market data has been entered in the market data

tables, that interest rate fixing has been performed for the interest flows of OTC transactions, and that the planned record update has been performed for the interest flows of securities positions.

Depending on the accrual/deferral procedure and the type of profit-related flow, the system creates an accrual/deferral flow that controls updates to Financial Accounting.

The accrual/deferral flows can be posted directly to Financial Accounting. If you select the setting Do not post immediately, you need to post the accrual/deferral at a later stage using the Process Business Transactions function.

With the default setting, the flows are posted immediately. The Do not post immediately setting is intended for exceptional situations, such as when the posting period is not yet open in Financial Accounting.

You can perform a test run.

If you need to reverse the accrual/deferral run, you can use the Reverse Accrual/Deferral function.

**Related Information**

Execute Accrual/Deferral Reversal of Accrual/Deferral

###### Joint Accrual/Deferral of Flows (Difference Procedure)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Accrual/Deferral of Expenses and Revenues > Joint Accrual/Deferral of Flows (Difference Procedure) | L6 | trm08 p.8 | loio `bc17da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bc17da531198434de10000000a174cb4.html?locale=en-US)

**Use**

As part of the difference procedure , you can jointly accrue/defer flows with different update types for a position or financial transaction. You can do this by making the same entry in the Grouping field for update types that are to be accrued/deferred together. You make this entry in Customizing under Assign Update Types for Accrual/Deferral.

**Prerequisites**

Update types that are to be accrued/deferred jointly need to have the same type of revenue and the same currency. Flows with different currencies are always accrued/deferred separately.

**Examples**

- Example 1: Nominal interest and capitalized interest are accrued/deferred together.


|Date|Update Type| |Amounts|
|---|---|---|---|
|01/01/2005|MM1105-|Asset|100|
|01/15/2005|AD1004|Accrual/deferral|5|
|01/31/2005|MM1120+|Final repayment|100|
| |MM1200+|Nominal interest|10|
|At the time of rollover, flow MM1200+ (nominal interest) is replaced by MM1106- (capitalized interest). The interest payment and final repayment are intended to be made on 02/28/2005.| | | |
|01/01/2005|MM1105-|Asset|100|
|01/15/2005|AD1004|Accrual/deferral|5|


|Date|Update Type| |Amounts|
|---|---|---|---|
|01/31/2005|MM1106+|Capitalized interest|10|
| |AD1004|Accrual/deferral|5|
|02/15/2005|AD1004|Accrual/deferral|5.5|
|02/28/2005|MM1120+|Final repayment|110|
| |MM1200+|Nominal interest|11|


- The interest accrual/deferral on 01/31/2005 is calculated as follows:

Total revenue: 10 (MM1106-) + 0 (MM1200+, not relevant )

Total accruals/deferrals to date: 5

This results in the accrual/deferral amount 10 – 5 = 5:

- The interest accrual/deferral on 02/15/05 is calculated as follows:


Total revenue: 10 (MM1106-) + 5.5 (MM1200+, not relevant )

Total accruals/deferrals to date: 10

This results in the accrual/deferral amount 10 – 5.5 = -10:

- Example 2: Nominal interest and capitalized interest are jointly accrued/deferred whilst another profit-related flow is accrued/deferred separately.


|Date|Update Type| |Amounts|Calculation to date| |
|---|---|---|---|---|---|
|01/01/2005|MM1105-|Asset|100| | |
| |MM1301-|Charges|1.2| |12/31/05|
|01/15/2005|AD1004|Accrual (revenue)|5| | |
| |AD1015|Deferral (expense)|0.05| | |
|01/31/2005|MM1120+|Final repayment|100| | |
| |MM1200+|Nominal interest|10| | |
|At the time of rollover, flow MM1200+ (nominal interest) is replaced by MM1106- (capitalized interest). The interest payment and final repayment are intended to be made on 02/28/2005.| | | | | |
|01/01/2005|MM1105-|Asset| |100| |
| |MM1301-|Charges| |1.2|12/31/05|
|01/15/2005|AD1004|Accrual (revenue)| |5| |
| |AD1015|Deferral (expense)| |0.05| |
|01/31/2005|MM1106+|Capitalized interest| |10| |
| |AD1004|Accrual (revenue)|5| | |
| |AD1015|Deferral (expense)|0.05| | |


|Date|Update Type| |Amounts|Calculation to date| |
|---|---|---|---|---|---|
|02/28/2005|MM1120+|Final repayment| |100| |
| |MM1200+|Nominal interest|11| | |
| | | | | | |

###### Netting Accrued Interest (Reset Procedure)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Accrual/Deferral of Expenses and Revenues > Netting Accrued Interest (Reset Procedure) | L6 | trm08 p.10 | loio `b917da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b917da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Instead of posting the accrued interest relating to a bond purchase directly to the profit and loss account, the system initially posts the interest to a compensation account. The balance of this compensation account is then cleared to the profit and loss account when the next interest payment is made or when the bond is sold.

The compensation account balance is taken into account as part of accrual/deferral according to the reset procedure and for transfer postings.

**Prerequisites**

You need to make the following settings in Customizing to use this function:

- 1. You need to have selected Netting Accrued Interest under Derived Business Transactions for Interest in the relevant position management procedure by choosing Transaction Manager General Settings Accounting Settings for Position Management Define Position Management Procedure.
- 2. Assign the position management procedure to the positions by choosing Transaction Manager General Settings Accounting Settings for Position Management Assign Position Management Procedure.
- 3. Make the following assignments (possibly just for the accounting code or valuation area ) by choosing Transaction Manager General Settings Accounting Settings for Position Management Effects of the Update Types on the Position Components:

- a. Assign the update type for accrued interest received (for example, SE8701) to position change category 1021 Post Accrued Interest Received.
- b. Assign the update type for accrued interest paid (for example, SE8702) to position change category 1022 Post Accrued Interest Paid.
- c. Assign an update type for nominal interest to position change category No Position Change .


- 4. Make your settings for the accrual/deferral of positions by choosing Transaction Manager General Settings Accounting Accrual/Deferral. Choose the Reset Procedure for the positions and set the Netting indicator.
- 5. You to specify update types to clear the accrued interest. We recommend that you describe the update types as follows:

DBT_H001 Clear accrued interest paid

DBT_H003 Clear accrued interest received

- 6. You need to assign update types to clear the accrued interest paid. You do this on the Interest tab page for the appropriate position management procedure by choosing Transaction Manager General Settings Accounting Derived Business Transactions Update Types Assign Update Types for Derived Business Transactions.


Since the accrued interest position component can also be affected by a transfer posting, you need to define the required update types and assign them to the tab pages Transfer Postings (fields 65-68) and Position Outflows (fields 49 and 50).

- 7. To make the relevant settings for all the update types relevant for posting, choose Transaction Manager General Settings Accounting Link to Other Accounting Components Indicate Update Types as Relevant for Posting and Define Account Determination.


**Features**

Accrued interest is managed in the accrued interest Position Component . This component is not included in the book value.

When a bond is purchased, the accrued interest is posted to the debit side of the compensation account. The posting can also be made to the credit side (for example, if interest is paid at the start of the period). It is therefore not necessary to have two different compensation accounts.

The component is cleared when the first interest payment is made after the purchase.

When the bond is sold, the accrued interest is cleared to the profit and loss account using the "average" method. With this method, the proportion of the nominal amount sold corresponds to the proportion of the balance for the accrued interest component that has to be cleared to the profit and loss account.

When the amount of interest accrual is calculated, the system takes into account the amount in the Accrued Interest position component.

In the case of transfer postings (such as securities account transfers or account assignment reference transfers), the corresponding portion of the balance in the accrued interest component is transferred.

**Caution:**

The functions described in this document are not available for accrued interest from parallel coupons (coupons with overlapping interest periods).

**Example**

You purchase a bond in June. The accrued interest is USD 60. This results in the following postings:

Position to bank x USD

Compensation to bank 60 USD

The positions are accrued/deferred in July:

Nominal interest of USD 120 is due in December meaning revenue of USD 70 pro rata minus accrued interest of USD 60 USD posts the following amount to profit and loss:

Receivables from interest revenues to profit and loss 10 USD

###### Execute Accrual/Deferral

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Accrual/Deferral of Expenses and Revenues > Execute Accrual/Deferral | L6 | trm08 p.11 | loio `fb7eef526b709972e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fb7eef526b709972e10000000a4450e5.html?locale=en-US)

**Use**

You use this function to determine expenses and revenues from financial transactions or positions in the Transaction Manager for a given period and to assign them to the correct accounting period, irrespective of when they were actually due.

Prerequisites

You need to have the required authorizations to exercise this function.

You need to have made the required settings in Customizing.

You need to have entered the required market data to calculate the variable interest.

For more information, see also Accrual/Deferral of Expenses and Revenues.

**Features**

Accrual/Deferral Rules

There is only one accrual/deferral on any given key date for each position/financial transaction, update type, currency, and side of a transaction.

As part of the difference procedure, an accrual/deferral cannot be performed at the point in time t1 if an accrual/deferral has already been performed at the later point in time t2.

Note: With the reset procedure, an accrual/deferral can be performed at any time, but not more than one on the same key date.

The flows that are accrued/deferred are those for which the accrual/deferral key date falls within the calculation period.

Selection

General Selections

In the general selections, you specify which positions or financial transactions are checked for flows that are relevant for accrual/deferral.

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

Listed Options and Futures

SecurityClass ID No.

Futures Account

OTC Transactions

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

Special Parameters

Accrual/Deferral Key Date

The accruals/deferrals key date determines the calculation period. The system defaults to the current date (today’s date), but you can overwrite it.

Key Date for Reset

If you do not make an entry here, the reset is performed one day after the accrual/deferral key date.

Including Key Date indicator

The time at which the accrual/deferral is performed is determined using the key date and the Including Key Date indicator for the key date. Depending on whether this indicator is set, completely different flows might be identified as being relevant for accrual/deferral.

Example:

There are two interest flows: Z1 and Z2.

- Z1 is calculated from 01/01/2001 to 12/31/2001.

- Z2 is calculated from 01/01/2002 to 12/31/2002.


An accrual/deferral is performed on the key date 01/01/2002.

- 1. If the Including Key Date indicator is set, the interest flow Z2 is accrued/deferred for a calculation period of one day.
- 2. If the Including Key Date indicator is not set, the interest flow Z1 is accrued/deferred for the calculation period 01/01/2001 to 12/31/2001.


Key Date Is Month-End indicator

If the accrual/deferral key date is the last day of a month, it needs to be regarded as the month-end date for corresponding interest calculation methods.

Posting Control

FI Posting Date

The FI posting date can differ from the key date of the accrual/deferral. You enter the different FI posting date here. If you do not make an entry here, the system applies the key date of the accrual/deferral as the FI posting date.

FI Document Date

Enter a date here if you do not want the current date to be applied as the document date.

Reset FI Posting Date

This is a different date for resetting the business transaction. If you do not make an entry here, the reset is performed one day after the accrual/deferral key date.

FI Document Date

Enter a date here if you do not want the current date to be applied as the document date.

Post Immediately indicator

If you do not set this indicator, the accrual/deferral needs to be posted at a later date using the Fix, Post, Reverse Business Transactions function.

With the default setting, the flows are posted immediately. The setting for the option of not posting immediately is intended for exceptional situations, such as when the posting period is not yet open in Financial Accounting.

Test Run indicator

You can perform a test run first. In this case, the system outputs the accrual/deferral list and simulates the posting.

Execute the function.

Results

For each selected position/transaction and for a given key date, the system determines the profit-related flows for which accruals or deferrals need to be created.

The system checks whether all the flows relevant for accrual/deferral and falling before the key date have been posted. If this is not the case, the system issues a warning message. The warning message informs you that flows that are relevant for accrual/deferral and for which the due date has passed have not yet been posted and are therefore not included in the P&L statement.

The accrual/deferral function checks whether and when the flow to be accrued/deferred was posted and whether this is in accordance with the accrual/deferral currently calculated.

This check is required because how accrual/deferral amounts are calculated varies depending on the procedure used. With the reset procedure, the flow is based on the payment date, and, with the difference procedure, the Customizing settings determine whether a profit-based flow needs to be accrued or deferred.

In the following instances, the system displays warning messages or error messages (depending on the setting made in Customizing):

When the flow to be deferred has not yet been posted

When the flow to be deferred was posted on a posting date later than the deferral key date

When the flow to be accrued was posted before the accrual key date

A message is issued as part of the reset procedure.

A message is not issued as part of the difference procedure. The accrual/deferral is posted to avoid data inconsistencies in the profit and loss accounts.

Depending on the accrual/deferral procedure and the type of profit-related flow, the system creates an accrual/deferral flow that controls updates to Financial Accounting.

Output

The lists are issued using the SAP List Viewer for SAP GUI (Classic).

The system outputs the following lists:

Accruals/deferrals list

The accrual/deferral list is output after the accrual/deferral run has been performed.

For each position/financial transaction, the system displays the flows to be accrued/deferred (flow category 01: Flow to Be Accrued/Deferred) and the current accrual/deferral flow (flow category 03: Generated Accrual/Deferral Flow). In the

case of flows that are accrued/deferred using the difference procedure, the system also lists the historical accruals/deferrals (flow category 02: Existing Accrual/Deferral Flow (Difference Procedure)). You can hide these using the Accrual/Deferral: Flow Category in Log field. To do this, choose the Change Layout function. Go to the Items tab. Copy the field to the display variant and save the change made to the layout. You can now select the field in the accrual/deferral list and choose the Set Filter function.

**Note:**

In case of accumulated flow, the accrual/deferral list contains one of the following depending on the key date:

accumulated flow - if the key date is set as after the calculation period of accumulated flow

daily interest flows with update type of the accumulated flow - all other instances

SAP delivers four display variants for this list.

1SAP

Default list containing more information than the 3SAP variant (three headers, two line items)

- 2SAP (minimal list)

This list contains only one header and one line item. For each position/financial transaction, the system displays only the amounts for the flows to be accrued/deferred and the accrual/deferral flow.

- 3SAP


The 3SAP variant contains one header and two line items. The header displays data concerning the position or financial transaction to be accrued/deferred. The line items contain the flows used to calculate the accrual/deferral and the dates determined.

1FLAT (Flat Structure for Table Export)

This display variant contains only one header and one line item but displays all the information on the accrual/deferral flows.

Posting log

You use the posting log to see which postings were made. For each posting document, the log tells you the relevant number, the class (ID number), or financial transaction, as well as the G/L accounts to which postings were made, including the amount posted.

Message list

The message list displays any error messages and warning messages issued.

###### Reversal of Accrual/Deferral

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Accrual/Deferral of Expenses and Revenues > Reversal of Accrual/Deferral | L6 | trm08 p.16 | loio `aa18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aa18da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this app to reverse business transactions from the app Run Accrual/Deferral.

All flows belonging to an accrual/deferral run form a business transaction. You can, however, still reverse the accrued/deferred flows of a single class using this function without also having to reverse the accrued/deferred flows of the other classes of the business transaction.

**Features**

For accrual/deferral with reset procedure, the accrual/deferral and reset that were generated on a specific key date are reversed.

For accrual/deferral with difference procedure, all accruals/deferrals after the key date are reversed.

**Activities**

- 1. Choose Accounting Accrual/Deferral Reverse Accrual/Deferral.
- 2. Select the position or financial transaction for which you want to reverse accrual/deferral.
- 3. Enter the Accrual/Deferral Key Date .
- 4. The posting period is an optional entry. If you do not enter anything here, the current period is selected.
- 5. You must enter a reversal reason . You can choose from the reversal reasons that you defined in Customizing for the Transaction Manager under General Settings Accounting Define Reasons for Reversal .
- 6. The Test Run indicator is set as a default. If you wish to post the accrual/deferral you must deactivate the indicator.


- 7. Choose Execute.
- 8. The system displays the Accrual/Deferral Log. It lists the reversed flows. The posting log shows a list of all reversed FI documents and displays a Message List.

###### Overview: Calculating NPVs in TRM

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Overview: Calculating NPVs in TRM | L5 | trm08 p.17 | loio `7bef515413e5843ae10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7bef515413e5843ae10000000a44538d.html?locale=en-US)

In Treasury and Risk Management, you can use the following functions to calculate NPVs (or fair values):

You use the function Single Value Analysis: NPV (transaction JBRX) to calculate NPVs for your financial transactions.

See also:Single Value Analysis Using NPV Analysis (transaction JBRX)

If you want to save NPVs that you have calculated so that you can use them again later (for example, during valuation), you use the function Save NPVs (transaction TPM60). In this transaction, the system calculates the NPVs in exactly the same way as transaction JBRX and saves the results in NPV table VTVBAR.

See also:Determine Net Present Values (transaction TPM60)

You use the function Determine NPVs Including CVA and DVA (transaction TPM60CVA) to include CVA and DVA in your NPV calculation. The results are also stored in the NPV table.

See also:Determine NPVs Including CVA and DVA (transaction TPM60CVA)

In the function Maintain NPV (transaction JBNPV), you can display the NPVs stored in the NPV table (table VTVBAR). Further, you can enter NPVs manually.

With the Analyzer Information System, you can display NPVs that were calculated using the Results Database.

You use the function Key Figure Analysis (transaction AISGENKF) to calculate NPVs online for your financial transactions.

For information about how NPVs are calculated for different financial transactions, see the following documentation: Price Calculator for Financial Instruments

**Note:**

You can use the function Price Calculator for Securities (transaction JBRBPC) to calculate prices for securities. These prices are stored for further application in table ATRAS.

This program calculates prices for bonds, warrant bonds, and convertible bonds. The prices are calculated by discounting future cash flow along the yield curve. The prices are calculated for each exchange and rate type and, where applicable, updated in price table (ATRAS). In the case of unit-quoted bonds, the price is calculated in the currency of the relevant exchange. The same price calculator as in transaction JBRX is used. The program considers only bonds with a key date falling in the related term. Further, the selected exchange needs to be stored in the class master data. The system issues a list of all valid combinations of ID number, exchange, and price type, together with the prices calculated.

###### Determining Net Present Values

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Overview: Calculating NPVs in TRM > Determining Net Present Values | L6 | trm08 p.17 | loio `090dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/090dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to calculate NPVs for transactions/loans with positions in parallel valuation areas. The net present values are calculated by the Market Risk Analyzer and saved in table VTVBAR. These values can then be applied in parallel valuation.

**Integration**

See also:Overview: Calculating NPVs in TRM

**Prerequisites**

To use the this function, you need to define the evaluation type in the settings in Customizing for the Market Risk Analyzer. You need to make the settings for the reference interest rates and so on. The system calculates the NPV using the yield curve types assigned on the Market Data tab.

You can define basis spread curves and credit spread curves, assign derivation strategies in the evaluation type, and calculate NPVs on the basis of the composite curve.

See also:

Yield Curve Framework

If you also want to calculate a risk-free NPV, you need to assign risk-free yield curve types in the evaluation type on the Market Data tab and set the Risk-Free NPV indicator when you run the program.

The results are stored in the NPV table (table VTVBAR, transaction JBNPV).

**Activities**

- 1. Call the function Determine Net Present Values (transaction TPM60) in the application menu of the Treasury and Risk Management under Transaction Manager Money Market/Foreign Exchange/Derivatives/Securities Accounting

Valuation or under Financial Risk Management for Commodities Accounting Valuation .

- 2. First specify whether you want to perform the calculation for loans or for OTC transactions.
- 3. Make the following settings to select the financial transactions for which you want to perform the calculation.
- 4. Under Evaluation Parameters, make the following entries:


Currency

Evaluation Type

Key Date

Clean Price Calculation indicator

In addition to the NPV, the system calculates the clean price for the financial transaction (loans, money market transactions, or swaps).

Intrinsic Value Calculation indicator

In addition to the NPV, the system calculates the intrinsic value and the time value of the financial transaction (in the case of OTC options).

Risk-Free NPV indicator

In addition to the NPV, the system also calculates the NPV on the basis of the risk-free yield curve that is assigned in the evaluation type.

Separate NPV (In/Out) indicator

In the case of two-sided transactions, the system calculates the NPV separately for the incoming side and the outgoing side. Total NPV = Total of Incoming and Outgoing Sides indicator

- 5. In the Hedge area, you decide whether you want to run the program in the test run mode. Further, you specify the price/NPV type for OTC transactions with which the results are stored in the NPV table.

You also specify whether results with warnings are also stored.

- 6. In the Layout area, you can specify a layout variant that you have defined.

You specify whether a detailed log is created and, if so, whether the log is stored.

- 7. Run the program.

###### Calculate Net Present Values - Including CVA and DVA

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Overview: Calculating NPVs in TRM > Calculate Net Present Values - Including CVA and DVA | L6 | trm08 p.19 | loio `81ff2954456b1b5de10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/81ff2954456b1b5de10000000a44538d.html?locale=en-US)

**Use**

You use this app to calculate net present values of financial transactions. You can choose to include credit and debit value adjustments in the calculation of NPVs for individual financial transactions or for netting groups.

In addition you can calculate the hedge accounting key figures for financial transactions that are assigned as hedging instruments in designated hedging relationships (P-HA) created during the Automated Exposure Item Hedging (FX Risk) process.

**Integration**

This app is delivered in addition to the function Determine Net Present Values (transaction TPM60).

The results of the calculation are stored in the NPV table at the level of the financial transactions, and you can display the results using the Enter Net Present Values app or in backend (transaction JBNPV).

See also: Overview: Calculating NPVs in TRM

**Prerequisites**

Credit and Debit Value Adjustments: Customizing

Market Data

The required current market data, such as exchange rates, interest rates, and credit spread values, must be available in the system.

**Features**

Using this function, you can include credit and debit value adjustments in the calculation of the NPVs for financial transactions and then save the NPVs in the NPV table.

You use the credit and debit value adjustment type to control how the system calculates the risk-based NPV as well as the CVA and DVA values.

If you have opted to use the Difference Method, the system applies the settings in the evaluation type to calculate the risk-based NPV and the risk-free NPV in exactly the same way as in the function Determine Net Present Values (transaction TPM60).

The risk-based NPV is determined using a yield curve matching the yield curve type assigned in the evaluation type settings on the Market Data Categories tab in the Yield Curve Types area. Credit spread curves are applied.

The risk-free NPV is determined using a risk-free yield curve matching the yield curve type assigned in the evaluation type settings on the Market Data Categories tab in the Risk-Free Yield Curve Types area.

**Note:**

If you have assigned basis spread curves, the system applies them in the calcuation of the risk-free NPV as well as the risk-based NPV.

In addition, the CVA or DVA is determined as the difference between both values and is also stored in the NPV table.

If you have opted to use the Based on Expected Exposures method, the risk-free NPV is calculated using the riskfree yield curve derived from the evaluation type. CVA and DVA values are calculated using the expected exposures. The (risk-based) NPV is calculated using the following equation:

NPV = risk-free NPV – CVA – DVA

See also: Credit and Debit Value Adjustments

The results of the calculation are stored in the NPV table. Since the results are stored in the NPV table at the level of the financial transactions, allocation needs to be used to divide the netting group results across the financial transactions of the netting group. In the NPV table, you can use the CVA/DVA Calculation pushbutton to navigate to the results of the related netting group.

**Activities**

- 1. Call the function Determine NPVs Including CVA and DVA (transaction TPM60CVA) in the application menu of the Treasury and Risk Management under Transaction Manager Money Market/Foreign Exchange/Derivatives

Accounting Valuation or under Financial Risk Management for Commodities Accounting Valuation .

- 2. Automatic Derivation of Evaluation Parameters

When this indicator is set, the system derives the following evaluation parameters from the settings in position management:

Evaluation type (from the relevant position management procedure)

CVA/DVA type (from the relevant position management procedure)

If the CVA/DVA type is not maintained in the position management procedure, CVA and DVA are not calculated and are consequently both set to zero.

Price/NPV type (from the procedures assigned as steps in the relevant position management procedure)

Valuation currency relevant for the combination of accounting code and valuation area

If a financial transaction has different sets of evaluation parameters in various valuation areas, all of them are applied.

- 3. Specify whether you want to perform the calculation for netting groups or single transactions.
- 4. Market Value Decomposition


**Note:**

When you enter specific valuation areas on the selection screen, you can restrict the calculation to these selected valuation areas.

When this indicator is set, the system calculates the decomposition of market values (spot, forward, CCBS, and other components) for selected financial transactions that are assigned as hedging instruments in designated hedging relationships (P-HA) created during the process Automated Exposure Item Hedging (FX Risk).

The calculation is made for a hedging instrument as well as for the corresponding hypothetical derivatives.

When a financial transaction is part of more than one hedging relationship, the calculation is made separately for each of the hedging relationships.

The calculation is always made for the nominal value of the financial transaction. The proportional value relevant for the specific hedging relationships is calculated within hedge accounting.

For more information see Calculation of Hedge Accounting Key Figures

- 5. Make the following settings to select the financial transactions for which you want to perform the calculation.
- 6. Under Evaluation Parameters, make the following entries:

Calculation Date

CVA/DVA Type

Evaluation Type

Currency

If you specify a currency, all values for single transactions and netting groups are calculated in this currency, and the intermediate results and final results are stored in this currency.

If you do not specify a currency, the calculation is made for single transactions in the position currency and for netting groups in the netting group currency. When the results are saved in the NPV table, the final results are translated into the position currencies of the relevant transactions, including the final results for transactions that form part of the netting group. The system calculates the intermediate results (EE, CVA /DVA ) in the netting group currency only.

Clean Price Calculation indicator

In addition to the NPV, the system calculates the clean price for the financial transaction (in the case of money market transactions or swaps).

Intrinsic Value Calculation indicator

In addition to the NPV, the system calculates the intrinsic value and the time value of the financial transaction (in the case of OTC options).

Separate NPV (In/Out) indicator

- 7. In the Hedge area, you decide whether you want to run the program in the test run mode. In the Price/NPV Type field, you specify the price/NPV type with which the results are stored in the NPV table.

Furthermore, you specify whether the system also stores results with warnings, and whether a detailed log is created and, if so, whether it is stored.

- 8. In the Layout area, you can specify for the output screens a layout variant that you have defined.
- 9. Run the program.


NG NG

**Note:**

When you have marked the Automatic Derivation of Evaluation Parameters indicator these fields are not available.

Results List

The results list contains the calculation results for all processed financial transactions and displays them as they are stored in the NPV table. In the case of financial transactions belonging to a netting group, this list also displays the relevant netting group.

When you select a line and choose the CVA/DVA Key Figures pushbutton, you navigate to the calculation details. If the selected financial transaction belongs to a netting group, the results for that netting group are displayed in the first line.

By choosing the Expected Exposures pushbutton, you can display the expected exposures used as the basis for the calculation.

When you have marked the Market Value Decomposition indicator you can choose the Hedge Accounting Key Figures pushbutton, to navigate to the calculation details, if the selected financial transaction is assigned as hedging instrument in designated hedging relationships (P-HA) created during the process Automated Exposure Item Hedging (FX Risk).

###### Credit and Debit Value Adjustments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Overview: Calculating NPVs in TRM > Calculate Net Present Values - Including CVA and DVA > Credit and Debit Value Adjustments | L7 | trm08 p.22 | loio `ef812954d8ccbb29e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ef812954d8ccbb29e10000000a44538d.html?locale=en-US)

**Definition**

A credit value adjustment (CVA) is the amount by which the risk-free NPV of a financial transaction is adjusted to reflect the probability of a default by a business partner. CVA is a positive amount. It is deducted from the risk-free NPV.

A debit value adjustment (DVA) is the amount by which the NPV of a financial transaction is adjusted to reflect the probability of a default by your own company. The absolute value of a DVA must be added to the risk-free NPV. As the DVA is defined as a negative amount, this means that the DVA needs to be subtracted from the risk-free NPV.

**Use**

You can include credit und debit value adjustments in the calculation of the NPVs for single transactions and netting groups. The results of the calculations (NPV, risk-free NPV, CVA, and DVA) are stored in the NPV table (table VTVBAR). You can consequently access them here for use in key date valuation.

The NPV of a financial transaction with the inclusion of CVA and DVA is obtained as follows:

NPV = risk-free NPV - CVA - DVA

If a financial transaction has collateral, the collateral has a risk-mitigating effect. The expected exposures are reduced, thereby leading to a reduction of the CVA/DVA values.

You use the Determine NPVs Including CVA and DVA function (transaction TPM60CVA) to include CVA and DVA values in NPV calculation

**Note:**

This function is available for the following contract types:

- 4 Foreign Exchange

- 5 Money Market

- 6 Derivatives


The CVA can also be used for the attributable amount determination for financial transactions (OTC) and bank accounts of Limit Management in the Credit Risk Analyzer. For more information, see also Attributable Amount Calculation Based on Credit Value Adjustments

**Prerequisites**

Credit and Debit Value Adjustments: Customizing

**Features**

[figure TRM08-F002 - Overview of Calculation Methods for Credit and Debit Value Adjustments]

Overview of Calculation Methods for Credit and Debit Value Adjustments

Calculation of Credit and Debit Value Adjustments

The calculation is made for single transactions in the position currency and for netting groups in the netting group currency. When the results are saved in the NPV table, the final results are translated into the position currencies of the relevant transactions, including the final results for transactions that form part of the netting group. The system calculates only the intermediate results (EE, CVA/DVA) in the netting group currency. The results at the level of the financial transactions are stored in the NPV table (table VTVBAR, transaction JBNPV). After you have run the function, the system returns the results for the netting groups in the results list. CVA and DVA can be calculated in the system in the following ways:

- CVA/DVA Calculation Method 1: Difference Method

With this method, the system first calculates the (risk-based) NPV using the yield curve stored in the evaluation type. If you have also made the settings for credit spreads, the system also takes credit spreads into account when calculating the NPV (for example, in a composite yield curve).

In this way, the system calculates the risk-free NPV with the risk-free yield curve stored in the evaluation type.

The CVA or DVA is the difference between the risk-free NPV and the (risk-based) NPV:

Risk-free NPV - NPV = CVA or DVA

- CVA/DVA Calculation Method 2: Based on Expected Exposures


**Caution:**

This method is available for single transactions only.

With this method, the system calculates the risk-free NPV on the basis of the risk-free yield curve that is assigned in the relevant evaluation type. The system calculates the CVA/DVA separately. First of all, the expected exposures for a set of future dates are calculated (or entered manually), aggregated, and weighted with the product of default probability (AWKT)

and loss given default (LGD).

**Note:**

This method can be used for single transactions and netting groups.

CVA and DVA values are calculated using the following equations:

[figure TRM08-F003 - CVA and DVA values are calculated using the following equations:]

where

LGD = loss given default

D = discount factor

t = time

EPE = expected positive exposure

ENE= expected negative exposure

PD = probability of default

C in subscript = business partner/counterparty of the transaction

I in subscript = your own company

EPE and CVA are positive

ENE and DVA are negative

The calculation of credit and debit value adjustments requires the credit spread curve for the reference entity of either the counterparty or of your own company to obtain the product AWKT*LGD as follows:

LGD*PD (t , t) = CS (t)*(t - t ) - CS (t )*(t - t )

i-1 i i i 0 i-1 i-1 0

The reference units are derived as follows:

If a business partner relationship type is entered in the evaluation type, the system first determines - for the counterparty of the transaction or for the business partner entered in the netting group - the parent group in the business partner hierarchy. If no business partner relationship is entered, the system uses the counterparty. For this business partner, the system looks for a reference entity for which the Use in Curve indicator is set. If this indicator has not been set for any reference entity, the system looks for a suitable reference entity in the assignment table (transaction RMBPRE_ASSIGN).

See also:Assign Reference Entities to Business Partners

For your own company, the system tries to find - for the company code of either the transaction or the netting group

- a reference entity for which the Use in Curve indicator is set. If no reference entity is found, the system searches for one using the default company code entered in the evaluation type.

The NPV is calculated as follows:

Risk-free NPV - CVA - DVA = NPV

Expected Exposures

You use the expected exposure type to specify the method with which the expected exposures are calculated. You can choose from the following three options:

Constant Exposure Approach

The NPV of the financial transaction is calculated for the evaluation date, based on the assumption that the NPV remains constant until the end of the term. A plus sign denotes a constant expected positive exposure (EPE), and a minus sign denotes a constant expected negative exposure (ENE).

Variable Exposure Approach

For each EE date (maturity band date), the NPV is calculated for the evaluation date using the EE date as the horizon. Depending on whether the value determined has a plus or minus sign, it is either an ENE or an EPE.

In the case of netting groups, the NPVs of the single transactions are first added together. Subsequently, the decision regarding whether ENE or EPE applies for the EE date is made for that netting group.

Manual Entry

The system does not calculate the values of the expected exposures. Instead, you enter the values manually using the Enter Expected Exposures function (transaction TPMEEM).

You use the Enter Expected Exposures function (transaction TPMEEM) to enter exposures that need to be entered manually. Further, you can use the function to display expected exposures that already exist in the system. You cannot change expected exposures determined by the system.

Allocation

After you have calculated the CVA and DVA as well as the NPVs for a netting group, the system still needs to distribute the CVA and DVA values to the single transactions of the netting group. For this, the system uses the allocation method that you have selected in the CVA/DVA type.

Gross Relative Fair Value Approach

CVA and DVA are distributed across all transactions of the netting group in proportion to the NPV (fair value) of the transactions.

Net Relative Fair Value Approach

The system proportionally distributes CVA across the transactions with a positive NPV (fair value), and DVA across those with a negative NPV (fair value).

The results are stored at the level of the financial transactions in the NPV table. By choosing the CVA/DVA Calculation pushbutton, you can display the results for the netting group.

Archiving

The entries in the NPV table (table VTVBAR), the logs (table TRPT_LOG), and the calculation results (tables FTBCVAD_CVA and FTBBCVA_EE) are archived using the archiving object TRTM_TPMTRM-TM: Positions.

###### Credit and Debit Value Adjustments: Customizing

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Overview: Calculating NPVs in TRM > Calculate Net Present Values - Including CVA and DVA > Credit and Debit Value Adjustments > Credit and Debit Value Adjustments: Customizing | L8 | trm08 p.26 | loio `c8d53554cf391f5de10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c8d53554cf391f5de10000000a44538d.html?locale=en-US)

If you would like to calculate credit and debit value adjustments on the basis of expected exposures, you need to have specified the type of expected exposures (EEs) in Customizing for Treasury and Risk Management under Basic Analyzer

Settings Valuation Settings for the Calculation of Credit and Debit Value Adjustments Define Expected Exposure Types .

You use the expected exposure type to specify the method with which the expected exposures are calculated. You can choose from the following three options:

Constant Exposure Approach

The NPV of the financial transaction is calculated for the evaluation date, based on the assumption that the NPV remains constant until the end of the term. A plus sign denotes a constant expected positive exposure (EPE), and a minus sign denotes a constant expected negative exposure (ENE).

Variable Exposure Approach

For each EE date (maturity band date), the NPV is calculated for the evaluation date using the EE date as the horizon. Depending on whether the value determined has a plus or minus sign, it is either an ENE or an EPE.

In the case of netting groups, the NPVs of the single transactions are first added together. Subsequently, the decision regarding whether ENE or EPE applies for the EE date is made for that netting group.

Manual Entry

The system does not calculate the values of the expected exposures. Instead, you enter the values manually using the Enter Expected Exposures function (transaction TPMEEM).

You can define the exposure duration / term in days for bank accounts, since financial objects for bank accounts don't have an end of term as financial transactions. Bank accounts have a current balance. You need to specify the point in time when the expected exposure drops to 0 from a CVA point of view. If you don’t specify the duration, the system uses 1 day as the default. This setting is relevant only for the CVA calculation during the attributable amount calculation of the Credit Risk Analyzer. For more information, see also Attributable Amount Calculation Based on Credit Value Adjustments

If you set the Ignore Netting Groups indicator, financial objects that are assigned to netting groups can also be processed individually.

You need to have created a credit and debit value adjustment type in Customizing for Treasury and Risk Management under Basic Analyzer Settings Valuation Settings for the Calculation of Credit and Debit Value Adjustments

Define Credit and Debit Value Adjustment Types .

In the credit and debit value adjustment type, you specify the credit and debit value adjustment calculation method. You have a choice between calculation method 1 Difference Method and calculation method 2 Based on Expected Exposures.

If you have opted for calculation method 2 Based on Expected Exposures, you then need to assign the type of expected exposures (EE type).

If you also want to perform calculations for netting groups, you need to select an allocation method. The allocation method specifies how the CVA/DVA values calculated for the netting group are distributed across the individual financial transactions of that netting group. You can use the following allocation methods:

Gross Relative Fair Value Approach

CVA and DVA are distributed across all transactions of the netting group in proportion to the NPV (fair value) of the transactions.

Net Relative Fair Value Approach

The system proportionally distributes CVA across the transactions with a positive NPV (fair value), and DVA across those with a negative NPV (fair value).

You need to have defined an evaluation type.

Depending on the CVA/DVA calculation method that you have chosen, specific settings need to be made in this evaluation type.

- CVA/DVA Calculation Method 1: Difference Method

In this case, the system calculates the NPV using the yield curve stored in the evaluation type, and it calculates the risk-free NPV using the risk-free yield curve also stored in the evaluation type. If you have also made the settings for credit spreads, the system also takes credit spreads into account when calculating the NPV (in a composite yield curve). The CVA or DVA is the difference between the risk-free NPV and the NPV.

You therefore need to make the settings for calculating the (risk-based) NPV in the evaluation type by assigning a yield curve and, if applicable, making the credit spread settings. You also need to assign a risk-free yield curve in the evaluation type. In addition, you also need to specify the exchange rate type for currency translations in the evaluation type.

- CVA/DVA Calculation Method 2: Based on Expected Exposures


In this case, the system calculates the risk-free NPV using the risk-free yield curve stored in the evaluation type.

The credit spread curves to be applied are determined using the derivation IDs assigned in the evaluation type.

See also:Deriving Credit Spread Curves

The credit spread curves determined in this way are required for the calculation of credit and debit value adjustments in order to obtain the product PD*LGD for the reference entity of the counterparty or of your own company:

LGD*PD (t , t) = CS (t)*(t - t ) - CS (t )*(t - t )

i-1 i i i 0 i-1 i-1 0

You need to specify the exchange rate type for currency translations in the evaluation type.

If you need to calculate the credit and debit value adjustments for netting groups, you need to create the netting groups in the Credit Risk Analyzer under Basic Settings Definitions Define Netting Groups .

**Note:**

Calculation of the CVA and DVA values for netting groups is implemented only for calculation method 2 Based on Expected Exposures.

Calculation of the expected exposures requires a maturity band. You define a maturity band in the area menu of the Market Risk Analyzer under Evaluation Control Define and Set Up Maturity Band (transaction JBRLZB).

**Note:**

The maturity band needs to be long enough to cover the term of the longest financial transaction but preferably not much longer: By defining a maturity band that is just long enough, you reduce the calculation runtime and save memory

space.

Within a maturity band, the distances between the grid points can vary. For example, you can first define a frequency of one month, then of one year, and then of five years - within the same maturity band. For the maturity band, you need to select a level of granularity appropriate to the structure of the financial transactions. This means that you generally need to select intervals with finer granularity for shorter terms so that any transactions due to expire shortly are also captured sufficiently. For longer terms, you can select intervals with less fine granularity.

See also:Maturity Band

###### Derive Credit Spread Curves for CVA/DVA Calculation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Overview: Calculating NPVs in TRM > Calculate Net Present Values - Including CVA and DVA > Credit and Debit Value Adjustments > Credit and Debit Value Adjustments: Customizing > Derive Credit Spread Curves for CVA/DVA Calculation | L9 | trm08 p.28 | loio `f9a77b54993a8c4ce10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f9a77b54993a8c4ce10000000a4450e5.html?locale=en-US)

For outgoing payments, the credit spread curve for your own company is used, whereas, for incoming payments, the credit spread curve of your business partner is used. Credit spread curves are derived using the reference entities. The system only considers reference entities for which the Use in Curves indicator has been set.

Determining Reference Entities

The system determines the reference entity for your own companies separately from that for business partners. In both cases, there is a standard derivation logic that you can replace using your own implementations of the BAdIs BAdI: Derive Reference Entity for Your Own Companies sowie BAdI: Derive Reference Entity for Business Partners. For this, the system first determines the derivation IDs that are assigned in the relevant evaluation type/valuation rule for derivation of the reference entities.

Reference Entities for Your Own Company

The standard implementation first searches for a reference entity for the company code of the transaction. If a reference entity is found for that company code, the system searches for a reference entity for the company code entered in the evaluation type/valuation rule.

Reference Entity for Your Business Partner (in the Counterparty role)

The standard implementation first checks the settings that you have made in the evaluation type/valuation rule on the Evaluation Control tab in the Credit Spread Curve Derivation area.

If you have not made an entry in the Business Partner Relationship Category field, the system searches for a reference entity for the business partner of the transaction.

If you have specified a relationship category in the Business Partner Relationship Category field, the system first determines which business partner is connected to business parter by means of this relationship category, and it then searches for the reference entity for that connected business partner. You can use the relationship category, for example, to valuate a business partner using the credit spread of the parent group. In this case, you would choose, in the evaluation type/valuation rule, the relationship category that is assigned to a subsidiary.

If the business partner stored in the business partner master data is not connected to another business partner by means of this relationship category, the system determines the reference entity for the business partner of the transaction.

If the system does not find any reference entities for the business partners determined in this way, it searches in the assignment table Geschaftspartner zu Referenzeinheiten zuordnen (transaction RMBPRE_ASSIGN) for reference entity that is assigned to the business partner.

[figure TRM08-F004]

Determining the Credit Spread Curve

The credit spread curve results from the credit spread curve structure assigned to the reference entity determined and from the designation "Bid" versus "Ask".

###### Enter Expected Exposures

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Overview: Calculating NPVs in TRM > Calculate Net Present Values - Including CVA and DVA > Credit and Debit Value Adjustments > Enter Expected Exposures | L8 | trm08 p.29 | loio `63d432546c741e6ee10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/63d432546c741e6ee10000000a441470.html?locale=en-US)

**Use**

You use this function to enter expected exposures that have the category Manual Entry and to display expected exposure that already exist in the system for a specific key date.

**Activities**

Entering Expected Exposures Manually

- 1. Call the function Enter Expected Exposures (transaction TPMEEM) in the application menu of the Transaction Manager under Transaction Manager Money Market/Foreign Exchange/Derivatives Accounting Valuation or under Financial Risk Management for Commodities Accounting Valuation .
- 2. In the Evaluation Parameters area, enter a date in the Effective From field and specify a type in the Expected Exposure Type.


****Note:****

The expected exposure type needs to have the EE category Manual Entry.

- 3. Run the program by choosing .
- 4. The Maintain Expected Exposures screen appears. Choose .


- 5. In the dialog box that appears, select the relevant netting group or single transaction, and then choose .


- 6. In the list that appears, enter for each EE date the amount of the expected positive exposure and the amount of the expected negative exposure (with a minus sign).
- 7. Save your entries.


**Note:**

The dates are determined on the basis of the date in the Effective From field and the maturity band assigned in the Expected Exposure Type.

Displaying Expected Exposures

- 1. Call the function Enter Expected Exposures (transaction TPMEEM) in the application menu of the Transaction Manager under Transaction Manager Money Market/Foreign Exchange/Derivatives/Commodities Accounting Valuation or under Financial Risk Management for Commodities Accounting Valuation .
- 2. Specify whether you want to display the expected exposures for single transactions or for netting groups.
- 3. In the next screen, select a netting group or a single transaction.
- 4. Enter a date in the Effective From field and specify a type in the Expected Exposure Type field.
- 5. Execute the program.

###### Enter Net Present Values

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Enter Net Present Values | L5 | trm08 p.30 | loio `030dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/030dda531198434de10000000a174cb4.html?locale=en-US)

App ID: JBNPV

With this app, you can store NPVs (net present values) for a financial transaction in the NPV table or display NPVs already stored in the system.

**Integration**

See also: Overview: Calculating NPVs in TRM

**Features**

The NPV table contains the following columns:

Contract Type

Company Code

Transaction (= Financial Transaction Number)

Contract Number (= Loan Contract Number)

Price / NPV Type

In the NPV table, you can store several net present values for an OTC transaction for the same date. These are identified by the different price/NPV types. In the course of a mark-to-market evaluation or a key date valuation, you use the price/NPV types to determine which of the stored NPVs are accessed.

Valid-From Date

Net Present Value

Currency

Clean Price

Intrinsic Value (for options)

Time Value (for options)

Risk-Free NPV

CVA (= Credit Value Adjustment)

DVA (= Debit Value Adjustment)

NPV for Incoming Side (in the case of two-sided transactions, such as swaps)

NPV for Outgoing Side (in the case of two-sided transactions, such as swaps)

If you enter values in the table manually, the following equations must be satisfied:

If CVA or DVA is filled for the NPV of an OTC transaction, the NPV key figures must satisfy the following formula:

NPV = risk-free NPV + CVA - DVA

OTC Options

If the intrinsic value or time value is filled, NPV key figures must satisfy the following formula:

NPV = intrinsic value + time value

**Activities**

- 1. Open the Enter Net Present Values app on SAP Fiori launchpad.
- 2. In the Field Selection screen, select the columns of the NPV table. You can select individual fields or select all columns by choosing . Choose .
- 3. In the next screen, you can use the following fields to restrict which data is displayed:

Contract Type

Company Code

Transaction

Contract Number

Price / NPV Type

Make the settings according to your needs. By choosing Further Selection Conditions, you can also use additional fields. Choose .

- 4. The NPVs of OTC Transactions: Overview screen appears.


The columns and data displayed correspond to the selections that you have made.

- 5. With the pushbutton, you can diplay the detailed log of the calculation for an NPV calculated by the system.
- 6. You can choose the pushbutton to switch between the display mode to the change mode.


- 7. If you have calculated the NPVs using the app Calculate Net Present Value, With CVA and DVA, you can display the calculation details for CVA/DVA as well as the risk-free key figures. To do this, select an entry and choose the CVA/DVA Calculation pushbutton. The List of CVAs/DVAs and Risk-Free Key Figures screen appears.

If the calculation was made for the single transaction, the CVA/DVA and the risk-free key figures are displayed in one line.

From here, you can select a line and then do the following:

Navigate to the relevant financial transaction

Call the Calculation Log for the risk-free key figures.

When the CVA/DVA calculation has been performed using the method Based on Expected Exposures, you can also do the following:

Call the Expected Exposures of the single transaction.

If you select a line and choose the Display Calculation Log pushbutton, you can display the calculation log for an expected exposure on that expected exposure date.


Display the CVA/DVA Calculation Log.

- 8. In the change mode, you can make manual changes to existing entries. Further, you can use the New Entries and pushbuttons to store new entries in the NPV table.
- 9. If errors occur during entry, you can choose the pushbutton to undo your changes.


- 10. Once you have made all new entries, save your entries.


The NPVs can now be used, for example, for key date valuation.

**Supported Device Types**

Desktop

Tablet

###### Enter Book Values for Manual Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Enter Book Values for Manual Valuation | L5 | trm08 p.32 | loio `b3fbad929f454a658ea38e27f27937f3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b3fbad929f454a658ea38e27f27937f3.html?locale=en-US)

App ID: TPM74

With this app, you enter new book values for treasury positions for a specific key date or display the manual entered book values.

**Integration**

After you have entered the new book values, you can start the valuation of the treasury positions using the Run Valuation app executed with the valuation category Manual Valuation With Reset or Manual Valuation Without Reset.

This valuation categories allows you to write-up or write-down a position to the book values entered in position currency and valuation currency in the Enter Book Values for Manual Valuation app, independent of the valuation rules defined.

The following valuation steps support manual valuation:

Security valuation

Foreign currency valuation

One-step price valuation

Index valuation

**Activities**

- 1. Open the Enter Book Values for Manual Valuation app on the SAP Fiori launchpad or in the area menu under Transaction Manager Money Market/Foreign Exchange/Derivatives/Securities/Trade Finance Accounting Valuation Enter Book Values for Manual Valuation (transaction TPM74).
- 2. The Field Selection screen appears. Choose one or more fields, to restrict the shown values in the app. Enter the values for the fields and choose Apply (Enter).
- 3. The Book Values for Manual Valuation table is shown.
- 4. Choose New Entries, to enter new book values for a position.


Enter the following data:

Enter the Key Date.

Enter the concrete values of the differentiating terms of the treasury position

Company Code

Valuation Area

Valuation Class

Transaction Number (for OTC transactions)

Contract Number (only relevant for Loans)

Security Class ID (for security positions)

Securities Account (for security positions)

Securities Account Group (for security positions)

Portfolio

Lot

If you use the following fields as differentiation terms for your position, you can select positions by these fields:

WBS Element

Cost Center

Profit Center

Functional Area

If you have defined your own differentiation terms (in the Define Custom Differentiation Terms configuration activity) and you use the fields as differentiation terms for your treasury positions, these fields are also available as selection criteria.

The following fields are available if Public Sector Management is used. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the journal entry:

Fund

Grant

Enter the new book values:

New Book Value Exclusive of Costs - Clean in Position Crcy (only for index-linked bonds)

New Book Value Exclusive of Costs in Position Currency

Position Currency

New Book Value Exclusive of Costs in Valuation Crcy

Valuation Currency

Save your entries.

###### Valuation (3 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation | L5 | trm08 p.34 | loio `5a19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a19c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

You use the valuation function to value the positions in the parallel valuation areas for a given key date.

The following products are valued:

Securities positions

Loan contracts

Money market transactions

OTC derivatives

Forward exchange transactions

Forward bonds

Futures

Integration

|Authorization Object|Activities|
|---|---|
|T_DEAL_PD (Product/transaction type authorization)|Activity 16 (execute) and 85 (reverse)|
|T_DEAL_PF (Portfolio authorization)|Activity 16 (execute) and 85 (reverse)|
|T_DEAL_DP (Securities account authorization)|Activity 16 (execute) and 85 (reverse)|
|T_DEAL_AG (Authorization group for customer-specific authorization checks)|Activity 16 (execute) and 85 (reverse)|


Prerequisites

Make your settings in Customizing for valuation.

Before executing a key date valuation, you also need to fulfill other prerequisites, such as updating the required price and NPV tables.

**Features**

You can perform a valuation at the end of the year or during the course of the year. If you run the valuation during the year, you can opt to have it reset afterwards.

If you perform a valuation and then have it reset, the system automatically resets the postings in the same run as the valuation itself. The key date for the reset postings is one day after the valuation key date.

When it values a position, the system follows the steps defined in the position management procedure for that position.

The following steps are available for the valuation where each step supports a particular selection of product categories. The supported product categories are described in the explanation for the individual steps or in the following list.

Amortization

One-Step Valuation

Two-Step Valuation

Security Valuation

Foreign Currency Valuation

Index Valuation

Rate Valuation for Forward Exchange Transactions (for product category 600, foreign exchange)

Swap/Margin Accrual/Deferral (for product categories 600 (foreign exchange) and 740 (forward bonds))

Swap Valuation (for product category 600, foreign exchange)

Futures Valuation

You define the order in which the steps are processed in the Position Management Procedure . Position management procedures are defined for Position Management Categories . The position management category controls the supported components for the position and delivers a preselection of valuation steps. The following position management categories with their respective preselection of valuation steps are available:

OTC derivatives (posting to P&L)

001 One-step price valuation

- 004 Security valuation

- 005 Foreign currency valuation


OTC derivatives (transfer from underlying)

001 One-step price valuation

- 004 Security valuation

- 005 Foreign currency valuation


Forward exchange transactions

004 Security valuation

- 006 Rate valuation - forward exchange transaction

- 007 Swap/Margin accrual/deferral

- 008 Swap valuation


Index-linked bonds

- 002 Amortization

- 003 Index valuation

- 004 Security valuation

- 005 Foreign currency valuation


Forwards

- 004 Security valuation

- 005 Foreign currency valuation


007 Swap/Margin accrual/deferral

Securities/loans/money market (without index-linked bonds)

- 001 One-step price valuation

- 002 Amortization


- 004 Security valuation

- 005 Foreign currency valuation


Securities/loans with installment repayment (without index-linked bonds)

- 001 One-step price valuation

- 002 Amortization


- 004 Security valuation

- 005 Foreign currency valuation


See also:

Executing Key Date Valuation

Reverse Key Date Valuation

###### Amortization

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization | L6 | trm08 p.36 | loio `6019c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6019c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

Amortization involves gains and losses, from interest-bearing financial assets or payables, being distributed over the term of the transaction.

We distinguish between the following amortization methods:

LAC (Linear Amortized Cost)

SAC (Scientific Amortized Cost)

Effective Interest Method (U.S.)

Amortization is performed at the following times:

Every time you run a key date valuation.

For each business transaction that affects a position. These amortizations are generated automatically. In case of a partial outflow (partial sale), the total position prior to the outflow is amortized before the position values (including amortization already generated) are cleared proportionately. This ensures that the amortized acquisition value displays the current value

at the time of each position change.

**Prerequisites**

In the Define Amortization Procedure Customizing activity, you can define your own amortization procedures.

**Integration**

The system supports amortization for interest-bearing financial assets or payables of the following areas:

Money market transactions

Securities

**Loans**

**Determining the Amortized Acquisition Value**

LAC (Linear Amortized Cost)

The premium or discount (the difference between the payment and the repayment amounts) is distributed over the term on a linear basis.

Example:

Basic date of the financial transaction:

|Dates|Cash Flow| |
|---|---|---|
|01/01/2021|Purchase|95,000.00|
|12/31/2021|Interest|12,000.00|
|12/31/2021|Repayment|100,000.00|


Amortization Schedule Using Calculation Category LAC

|Dates|Amortization|Amortized Acquisition Value|
|---|---|---|
|01/01/2021| |95,000.00|
|01/31/2021|416.67|95,416.67|


|Dates|Amortization|Amortized Acquisition Value|
|---|---|---|
|02/28/2021|416.67|95,833.33|
|03/31/2021|416.67|96,250.00|
|04/30/2021|416.67|96,666.67|
|05/31/2021|416.67|97,083.33|
|06/30/2021|416.67|97,500.00|
|07/31/2021|416.67|97,916.67|
|08/31/2021|416.67|98,333.33|
|09/30/2021|416.67|98,750.00|
|10/31/2021|416.67|99,166.67|
|11/30/2021|416.67|99,583.33|
|12/31/2021|416.67|100,000.00|
| |5,000.00| |


SAC (Scientific Amortized Cost)

This method is also known as the effective interest method. The amortized acquisition value of a position is determined as follows:

The system uses the effective interest rate of a cash flow to discount future payments up to the amortization key date.

The following variations on this method are supported:

Don't include interest: Interest payments aren't considered when determining the effective interest rate or when discounting future payments. The premium or discount is then distributed exponentially over the term.

Include interest, accrued interest adjustment (for securities only): The interest payments are included in the effective interest rate calculation and are also taken into account when discounting future payments. To avoid increases in the amortized acquisition value on interest dates, accrued interest is adjusted on a linear basis. If you choose this option, you also need to make interest accruals/deferrals for amortization.

Effective interest method in accordance with IAS 39: Interest payments are included in the effective interest rate calculation and are also taken into account when discounting future payments, but there's no accrued interest adjustment. Additional interest accruals and deferrals are therefore not required.

Example:

Basic date of the financial transaction:

|Dates|Cash Flow| |
|---|---|---|
|01/01/2021|Purchase|95,000.00|
|12/31/2021|Interest|12,000.00|
|12/31/2021|Repayment|100,000.00|


Effective interest rate: 17.8940000%

Amortization Schedule Using Calculation Category SAC with Interest and Accrued Interest Correction

|Dates|Discounted CF|Amortization|Accrued Interest|Amortization Without Accrued Interest|Amortized Acquisition Value (Accounting)|Interest Days|
|---|---|---|---|---|---|---|
|01/01/2021|95,000.00| | | |95,000.00| |
|01/31/2021|96,312.79|1,312.79|1,000.00|312.79|95,312.79|30|
|02/28/2021|97,643.11|2,330.32|2,000.00|330.32|95,643.11|60|
|03/31/2021|98,991.81|3,348.70|3,000.00|348.70|95,991.81|90|
|04/30/2021|100,359.13|4,367.32|4,000.00|367.32|96,359.13|120|
|05/31/2021|101,745.34|5,386.21|5,000.00|386.21|96,745.34|150|
|06/30/2021|103,150.70|6,405.36|6,000.00|405.36|97,150.70|180|
|07/31/2021|104,575.47|7,424.77|7,000.00|424.77|97,575.47|210|
|08/31/2021|106,019.92|8,444.45|8,000.00|444.45|98,019.92|240|
|09/30/2021|107,484.32|9,464.40|9,000.00|464.40|98,484.32|270|
|10/31/2021|108,968.94|10,484.63|10,000.00|484.63|98,968.94|300|
|11/30/2021|110,474.08|11,505.13|11,000.00|505.13|99,474.08|330|
|12/31/2021|112,000.00|12,525.92|12,000.00|525.92|100,000.00|360|
| | | | |5,000.00| | |


Effective Interest Method (U.S.)

The effective interest rate is calculated and then used to determine the amortization amount.

Calculation procedure for each amortization date:

The cash flow is calculated based on the last amortized acquisition value and date.

The interest amount of the periods is calculated.

The effective interest rate is calculated.

Amortization is calculated for each period in the following way:

- 1. Applying the effective interest rate to the previous amortized acquisition value.
- 2. Deducting the interest for the period from the calculated amount.


The amortization amount is added to the previous amortized acquisition value and results in the new amortized acquisition value.

At maturity of the treasury position, the amortized acquisition value is equal to the nominal amount.

Example:

Basic date of the financial transaction:

|Dates|Cash Flow| |
|---|---|---|
|01/01/2021|Purchase|95,000.00|
|12/31/2021|Interest|12,000.00|
|12/31/2021|Repayment|100,000.00|


Effective Interest Rate: 17.4861322%

Amortization Schedule Using Calculation Category Effective Interest Method (U.S.)

|Dates|Periodic Interest|Amortization|Net Amortization|Carrying|
|---|---|---|---|---|
|01/01/2021| | | |95,000.00|
|01/31/2021|1,000.00|1,384.32|384.32|95,384.32|
|02/28/2021|1,000.00|1,389.92|389.92|95,774.24|
|03/31/2021|1,000.00|1,395.60|395.60|96,169.84|
|04/30/2021|1,000.00|1,401.37|401.37|96,571.21|
|05/31/2021|1,000.00|1,407.21|407.21|96,978.42|
|06/30/2021|1,000.00|1,413.15|413.15|97,391.57|
|07/31/2021|1,000.00|1,419.17|419.17|97,810.74|
|08/31/2021|1,000.00|1,425.28|425.28|98,236.02|
|09/30/2021|1,000.00|1,431.47|431.47|98,667.49|
|10/31/2021|1,000.00|1,437.76|437.76|99,105.25|
|11/30/2021|1,000.00|1,444.14|444.14|99,549.39|
|12/31/2021|1,000.00|1,450.61|450.61|100,000.00|
| | | |5,000.00| |


The difference between the old amortized acquisition value and the new amortized acquisition value is the write-up or write-down amount in position currency. This is then translated to the valuation currency using the book exchange rate. Flows are generated for the write-up or write-down amount. The system selects an update type based on the gross/net indicator.

**Gross/Net Procedure**

You can make the following field settings for the net or gross procedure in the configuration activity Define Amortization Procedure:

If you use the net procedure, the position is posted with its acquisition value (book value = acquisition value) and is amortized over the remaining term (book value = acquisition value + amortization).

If you use the gross procedure, the premium/discount for the position is posted as accrued/deferred assets/liabilities (book value = acquisition value + premium/discount). During amortization, the premium/discount is written back over the remaining term affecting net income (book value = acquisition value + premium/discount + amortizations).

Net; Separate Balance Sheet Accounts for Amortization

Negative and positive amortizations for a position caused by changes to the position, transfer postings, or key date valuations are posted to offsetting accounts in Financial Accounting. After the amortizations have been posted, the balance of both accounts is automatically compared for this position. If both accounts show a balance for this position, the account with the lower balance is cleared via the account with the higher balance by an adjustment flow.

Gross; Premium/Discount Not Included in Book Value

This is a special gross procedure case. The premium/discount is posted and written back over the remaining term affecting net income, but the book value doesn't contain the premium/discount (book value = acquisition value + amortizations). This ensures that the amount of the foreign currency write-up/down is the same for one position in different valuation areas.

Gross; Separate Accounts for Accruals/Deferrals

With the gross procedure, postings are made to the accruals/deferrals account. Which account depends on whether a premium or discount exists. If you choose this procedure, the system uses adjustment flows to make sure that, at any time, only one of the two accrual/deferral accounts displays a balance other than zero. In this way, the accrued/deferred assets can show balances on the debit side and the accrued/deferred liabilities can only show balances on the credit side.

The write-up or write-down amount in position currency is then translated to valuation currency using the book exchange rate. Flows are generated for the write-up or write-down amount. The system selects an update type based on the gross/net indicator.

**More Information**

Amortization with Issue Spread / Negotiation Spread

Amortization According to LAC and SAC

###### Amortization According to LAC and SAC

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC | L7 | trm08 p.41 | loio `6319c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6319c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

During amortization, the system determines the new amortized acquisition value of a position. If you have determined amortization for a position management procedure, the system executes amortization in the following cases:

When valuating the position

Derived business transactions:

For position inflows and outflows

For all other business transactions that change the amortized acquisition value (purchase value + capitalized costs

+ amortizations) or the nominal value.

On each amortization date, the system always executes amortization for the total position.

Note:

For a partial outflow, the system first takes into account the total position for amortization, in other words, the position before the partial outflow occurred. The proportional book value of the partial position is then cleared.

You can calculate the amortized acquisition value according to the Linear Amortized Cost (LAC) procedure or the Scientific Amortized Cost (SAC) procedure.

**Features**

LAC Procedure

This procedure uses a linear amortization process. Planned profit is distributed equally over the term. This calculation method assumes that the value of the positions is based on a constant annual amortization rate.

[figure TRM08-F010 - This procedure uses a linear amortization process. Planned profit is distributed equally over the term. This calculation method assumes that the value of the positions is based on a constant annual amortization rate.]

BP = new book rate

new

BP = old book rate

old

D = Duration in days between the last and the current amortization

a

D = Duration in days between the last amortization and the final maturity date

a

SAC Procedure

This calculation procedure is based on an exponential amortization rate. The system first calculates an effective interest rate and then uses this to discount future flows up to the amortization key date.

To calculate the effective interest rate and amortization, the system does not consider the entire cash flow of the position but instead uses the amortized acquisition value on the last amortization date to generate a new cash flow internally. This new cash flow is then used to calculate amortization. Besides an inflow at the last time of amortization, the internal cash flow only covers condition-based planned flows (therefore no sales, unscheduled repayments or changes in capital).

The system determines the difference from the newly calculated and previous amortized acquisition values and uses this amount to generate a write-up or write-down. The system uses the position currency to determine the values mentioned above. The writeup or write-down amount is then translated at the book exchange rate into the valuation currency.

The following setting options are available for the SAC procedure:

Do not include interest

See also: SAC Procedure Without Interest

Include interest, with accrued interest adjustment (securities)

See also: SAC Including Interest and Accrued Interest Adjustment

Cash flow method in accordance with IAS39 (Include interest, without accrued interest adjustment)

See also: SAC Procedure Including Interest (Cash flow method in accordance with IAS39)

For more information, see Customizing for the Transaction Manager under General Settings Accounting Settings for Position Management Key Date Valuation Define Amortization Procedure .

See also:

Position Management Procedure

Derived Business Transactions

###### SAC Procedure Without Interest

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC > SAC Procedure Without Interest | L8 | trm08 p.43 | loio `950bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/950bda531198434de10000000a174cb4.html?locale=en-US)

The SAC calculation is based on the cash flow of the position to be valued.The system proceeds as follows:

The system determines the key date of the last amortization or the key date of the last quantity-based position change (inflow/outflow). Only one inflow is shifted to a zero position, otherwise amortization would have already occurred.

The system determines the amortized acquisition value and the nominal value for the key date. These values are then used to generate a hypothetical purchase or payment.

Based on the hypothetical purchase and the conditions defined, the system then determines the cash flow (future repayment flows or payments). Interest, and revenues or charges entered manually, are not included in the cash flow. The cash flow contains only the initial purchase and the repayment flows.

Example

|Flow|Date|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|1stPurchase|06/01/00|1,000,000|700,000|
|2ndPurchase|06/15/00|500,000|375,000|
|1stSale|11/01/00|100,000|65,000|
|Interest|12/31/00| |56,000|
|2ndSale|03/01/01|1,400,000|1,260,000|


Conditions

Interest is calculated and paid annually on December 31.

The final repayment is for December 31, 2001 (100% repayment price).

Interest calculation method 360/360 is used.

**Amortization on 06/15/00 (Second Purchase)**

The nominal amount is 1,000,000. This does not include the second purchase. The calculation is based on the first purchase. This inflow generates the cash flow for amortization (without interest):

|Date|Nominal Amount|Amount in Position Currency|
|---|---|---|
|06/01/00|1,000,000|700,000|
|12/31/01|1,000,000|1,000,000|


The effective interest rate of the cash flow is 25.2658870%.

**Note:**

This calculation is based on an approximation method. To prove that the effective interest rate is correct, proceed as follows:

After interest factors have been determined for the individual flows, they are then discounted.

If the net present value of the cash flow is zero, the effective interest rate used is correct.

The amortization value (amortized acquisition costs) is the total of the net present values of the individual flows with the position date after the key date (05/15/00). In this case, only repayment is relevant. The amortization value is 706,159.

A write-up of 706,159 - 700,000 = 6,159 is generated as the amortization flow.The amortized acquisition costs for 06/15/00 amount to 1,081,159:

|Amount|Activity|
|---|---|
|700,000|Post purchase value on 06/01/00|
|+ 6,159|Positive amortization on 06/15/00|
|+ 365,000|Post purchase value on 06/15/00|
|= 1,081,159|Amortized acquisition costs on 06/15/00 (including inflow and amortization)|


**Amortization on 11/01/00 (First Sale)**

The nominal amount is 1,500,000. This does not include the second purchase. The amortized acquisition costs on 11/01/00 (excluding the 2nd Sale) is 1,081,159 (total of purchases and amortizations before the key date 11/01/00).

An artificial position inflow is generated for the key date of the last position change (06/15/05 in this case). This generates the condition-based cash flow relevant for amortization.

|Date|Activity|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|06/15/00|Inflow|1,500,000|1,081,159|
|12/31/01|Outflow|1,500,000|1,000,000|


The effective interest rate of these flows is 23.6155121%.

- The total of the net present values of the flows after 11/01/05 determines an amortization value of 1,171,312. A write-up of 1,171,312


- 1,081,159 = 90,153 is generated as the amortization flow of the derived business transaction. The amortized acquisition costs for 11/01/00 amount to 1,093,225.

|Amount|Activity|
|---|---|
|1,081,159|Amortized acquisition costs on 06/15/00|
|+ 90,153|Amortization on 11/01/00|
|- 71,667|Translation: amortization (1/15 of 1,075,000)|
|= 1,093,225|Amortized acquisition costs on 11/01/00 (including all flows)|


**Key Date Valuation for 12/29/00 (Including Sale)**

The nominal amount is 1,400,000. The calculation is based on the first sale. The amortized acquisition costs for 12/29/00 amount to 1,093,225. This includes all flows occurring before the key date (inflows, outflows, translations).

An artificial position inflow is generated for the key date of the last position change (11/01/05 in this case). This generates the condition-based cash flow relevant for amortization.

|Date|Activity|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|11/01/00|Inflow|1,400,000|1,093,225|
|12/31/01|Outflow|1,500,000|1,400,000|


The effective interest rate of these flows is 23.6155121%.

- The total of the net present values of the flows after 12/29/00 results in an amortization value of 1,131,211. A write-up of 1,131,211 1,093,225 = 37,986 is generated as the amortization flow as part of the key date valuation on 12/29/00.


**Key Date Valuation for 01/03/01 (Including Amortization)**

The nominal amount is 1,400,000. The calculation is based on the first sale. The amortized acquisition costs for 01/03/01 amount to 1,131,211.

An artificial position inflow is generated for the key date of the last position change (12/29/00 in this case). This generates the condition-based cash flow relevant for amortization.

|Date|Activity|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|12/29/00|Inflow|1,400,000|1,131,211|
|12/31/01|Outflow|1,400,000|1,400,000|


The effective interest rate of these flows is 23.6155121%.

The total of the net present values of the flows after 01/03/01 results in an amortization value of 1,133,879. A write-up of 1,133,879

- 1,131,211 = 2,668 is generated as the amortization flow as part of the key date valuation on 01/03/01.

###### SAC Procedure Including Interest

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC > SAC Procedure Including Interest | L8 | trm08 p.45 | loio `980bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/980bda531198434de10000000a174cb4.html?locale=en-US)

(Cash flow method in accordance with IAS39)

Example

Initial Data

|Date|Flow|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|06/01/00|1st Purchase|1,000,000|700,000|
|06/15/00|2nd Purchase|500,000|375,000|
|11/01/00|1st Sale|100,000|65,000|
|12/31/00|Interest| |56,000|
|03/01/01|2nd Sale|1,400,000|1,260,000|


Conditions

Interest is calculated and paid annually on December 31.

The final repayment is for December 31, 2001 (100% repayment price).

Interest calculation method 360/360 is used.

|Amortization Key Date|Effective Interest Rate|
|---|---|
|06/15/00|32.502713|
|11/01/00|30.767301|


**Note:**

We have specified only the effective interest rates to demonstrate the matter clearly. To clarify the differences between the amortization methods, we will only analyze the key date valuations for December 29, 2000 and January 3, 2001.

Key Date Valuation for 12/29/00 (Including Amortization)

1. The nominal amount is 1,400,000. The calculation is based on the first sale.The amortized acquisition costs for 12/29/00 amount to 1,118,297. An artificial position inflow is generated for the key date of the last position change (11/01/00 in this case). This generates the cash flow relevant for amortization. Interest rate flows are also generated.

|Position Date|Flow|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|11/01/00|Inflow|1,400,000|+ 1,118,296|
|12/31/00|Interest| |56,000|
|12/31/01|Interest| |56,000|
|12/31/01|Outflow|1,400,000|- 1,400,000|


- 1. The effective interest rate of the cash flow is 30.7673016%.

Note: This calculation is based on an approximation method. To prove that the effective interest rate is correct, proceed as follows:

After interest factors have been determined for the individual flows, they are then discounted. If the net present value of the cash flow is zero, the effective interest rate used is correct.

- 2. The total of the net present values of the flows after 12/29/00 (two interest flows and repayment) determines an amortization value of 1,167,687. A write-up of 1,167,687 - 1,118,297 = 49,390 is generated as an amortization flow as part of the key date valuation.


Key Date Valuation for 01/03/01 (Including Amortization)

1. The nominal amount is 1,400,000. The calculation is based on the key date valuation for December 29, 2000.The amortized acquisition costs for 01/03/01 amount to 1,167,687. An artificial position inflow is generated for the last position change (key date valuation for 12/29/00 in this case). This generates the cash flow relevant for amortization. Interest rate flows are also generated.

|Position Date|Flow|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|12/29/00|Inflow|1,400,000|+ 1,167,686|
|12/31/00|Interest| |56,000|
|12/31/01|Interest| |56,000|
|12/31/01|Outflow|1,400,000|- 1,400,000|


- 1. The effective interest rate of the cash flow is 30.7673016%.

Note: This calculation is based on an approximation method. To prove that the effective interest rate is correct, proceed as follows:

After interest factors have been determined for the individual flows, they are then discounted. If the net present value of the cash flow is zero, the effective interest rate used is correct.

- 2. The total of the net present values of the flows after 01/03/00 (interest flows and repayment) determines an amortization value of 1,115,089. A write-down of 1,167,687 - 1,115,089 = 52,598is generated as an amortization flow as part of the key date valuation. Since the interest flow from 12/31/00 is paid (realized) before the amortization key date, it is no longer included in the position.
- 3. The book value (or the amortization) is reduced and leads to a write-down. The amortization curve is therefore no longer continuous; instead it jumps when the interest flows occur.



**Note:**

These jumps can be avoided by offsetting the interest payment (or the accrual/deferral) to the same FI account. Alternatively, you can use the cash flow method with accrued interest adjustment. With this method, the amortization amount is adjusted (reduced or increased) using the accrued interest amount This prevents the jumps resulting from write-downs.

###### Example: Effective Interest Method (Cash Flow Method)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC > SAC Procedure Including Interest > Example: Effective Interest Method (Cash Flow Method) | L9 | trm08 p.47 | loio `830bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/830bda531198434de10000000a174cb4.html?locale=en-US)

Amortized acquisition costs are calculated using the effective interest method, in accordance with IAS 39. Using the effective interest rate, the expected cash flows are discounted over the entire lifecycle of the financial asset. The effective interest rate calculation includes all directly attributable transaction costs - charges, premiums, discounts, reductions, and other payments

received or made.

Example

A purchases a financial asset with a remaining term of five years at a market value of 1,000 (including transaction costs). The financial asset has a nominal value of 1,250 and interest is calculated annually at 4.7% (1,250 * 0.047 = 59).

According to the contract, the debtor has the right to make the repayment in advance, for which no charges are levied. A first assumes that the debtor will not repay in advance.

To split the interest income and discount into constant amounts over the term of the financial asset, an annual effective interest rate of 10% is applied, based on the book value.

The following table shows the amortized acquisition costs, interest income, and cash flows of the financial asset for the individual reporting timeframes:

|Year|Amortized Acquisition Costs at Start of Year (Book Values)(a)|Effective Interest Rate (10%) Write-Up:b=a x 10%|Cash Flows(c)|Amortized Acquisition Costs at Year-End(d = a+b-c)|
|---|---|---|---|---|
|01|1,000|100|59|1,041|
|02|1,041|104|59|1,086|
|03|1,086|109|59|1,136|
|04|1,136|113|59|1,190|
|05|1,190|119|1,250 + 59|-|


At the start of the year 2003, A re-estimates the cash flows. A assumes that 50% of the amount credited (625) is repaid in advance at the end of 2003 and that the other half is repaid at the end of the term.

According to IAS 39.AG8, the book value of the financial asset in 2003 is adjusted so that the effective interest rate does not change (1,086 + 52 = 1,138). The new book value is included in the 2003 opening balance. The original effective interest rate of 10% applies to the subsequent years. The difference amount of 52 (1,138 – 1,086) is entered in the profit and loss statement for the year 2003.

The values in the following table take into account the re-estimation.

|Year|Amortized Acquisition Costs at Start of Year (Book Values)(a)|Effective Interest Rate (10%)Write-Up:(b=a x 10%)|Cash Flows(c)|Amortized Acquisition Costs at Year-End(d = a+b-c)|
|---|---|---|---|---|
|01|1,000|100|59|1,041|
|02|1,041|104|59|1,086|
|03|1,086 + 52|114|625 + 59|568|
|04|568|57|30|595|
|05|595|60|625 + 30|-|


If the value of the financial asset decreases at the end of the year 2004, for example, depreciation is calculated from the difference between the nominal value (595) and the net present value of the expected cash flows (discounted using the original effective interest rate of 10%).

###### SAC Including Interest and Accrued Interest Adjustment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC > SAC Including Interest and Accrued Interest Adjustment | L8 | trm08 p.48 | loio `9b0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9b0bda531198434de10000000a174cb4.html?locale=en-US)

Example

**Initial Data**

|Date|Flow|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|06/01/00|1st Purchase|1,000,000|700,000|


|Date|Flow|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|0615/00|2nd Purchase|500,000|375,000|
|11/01/00|1st Sale|100,000|65,000|
|12/31/00|Interest| |56,000|
|03/01/01|2nd Sale|1,400,000|1,260,000|


Conditions

Interest is calculated and paid annually on December 31.

The final repayment is for December 31, 2001 (100% repayment price).

Interest calculation method 360/360 is used.

|Amortization Key Date|Effective Interest Rate|
|---|---|
|06/15/00|30.4741056|
|11/01/00|28.7343312|


**Note:**

We have specified only the effective interest rates to demonstrate the matter clearly. The amortization calculations on 06/15/00 and 11/01/00 are not described here.

**Key Date Valuation for 12/29/00 (Including Amortization)**

1. The nominal amount is 1,400,000. The calculation is based on the first sale.The amortized acquisition costs for 12/29/00 amount to 1,091,257. An artificial position inflow is generated for the key date of the last position change (11/01/00 in this case). This generates the cash flow relevant for amortization. The amortization amount is adjusted by the accrued interest amount.

|Position Date|Flow|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|11/01/00|Inflow|1,400,000|+ 1,091,257|
|11/01/00|Accrued interest| |- 46,822|
|12/31/00|Interest| |56,000|
|12/31/01|Interest| |56,000|
|12/31/01| |1,400,000|- 1,400,000|


1. Coupon relevant for accrued interest on 11/01/00:

Calculation from: 01/01/00

Calculation to: 11/01/00

Number of days: 301

Coupon/Interest amount:56,000

Accrued interest amount:56,000 x 301/360 = 46,822

- 2. The effective interest rate of the cash flow is 28.7343310%.

Note: This calculation is based on an approximation method. To prove that the effective interest rate is correct, proceed as follows:

After interest factors have been determined for the individual flows, they are then discounted. If the net present value of the cash flow is zero, the effective interest rate used is correct.

- 3. The total of the net present values of the flows after 12/29/00 (two interest flows and repayment) determines an amortization value of 1,185,347. Accrued interest is calculated on the amortization key date (12/29/00) to adjust the amortization amount.
- 4. Coupon relevant for accrued interest on 12/29/00:

Calculation from: 01/01/00

Calculation to: 12/29/00

Number of days: 358

Coupon/Interest amount:56,000

Accrued interest amount:56,000 x 358/360 = 55,689

- 5. On 12/29/00, the amortization amount (net present value) is 1,185,347 – 55,689 = 1,129,658. This results in a write-up of 1,129,658 – 1,091,257 = 38,401 on 12/29/00.


**Key Date Valuation for 01/03/01 (Including Amortization)**

1. The nominal amount is 1,400,000. The calculation is based on the key date valuation for December 29, 2000.The amortized acquisition costs for 01/03/01 amount to 1,129,658. An artificial position inflow is generated for the key date of the last position change (12/29/00 in this case). This generates the cash flow relevant for amortization. The amortization amount is adjusted by the accrued interest amount.

|Position Date|Flow|Nominal Amount|Amount in Position Currency|
|---|---|---|---|
|12/29/00|Inflow|1,400,000|+ 1,129,658|
|12/29/00|Accrued interest| |- 55,689|
|12/31/00|Interest| |56,000|
|12/31/01|Interest| |56,000|
|12/31/01|Outflow|1,400,000|- 1,400,000|


- 1. Coupon relevant for accrued interest on 12/29/00:


Calculation from: 01/01/00

Calculation to: 12/29/00

Number of days: 358

Coupon/Interest amount:56,000

Accrued interest amount:56,000 x 358/360 = 55,689

- 2. The effective interest rate of the cash flow is 28.7343310%.

Note: This calculation is based on an approximation method. To prove that the effective interest rate is correct, proceed as follows:

After interest factors have been determined for the individual flows, they are then discounted. If the net present value of the cash flow is zero, the effective interest rate used is correct.

- 3. The total of the net present values of the flows after 01/03/01 (interest flows and repayment) determines an amortization value of 1132,500. Accrued interest is calculated on the amortization key date (01/03/01) to adjust the amortization amount.
- 4. Coupon relevant for accrued interest on 01/01/01:

Calculation from: 01/01/01

Calculation to: 01/03/01

Number of days: 2

Coupon/Interest amount:56,000

Accrued interest amount:56,000 x 2/360 = 311

- 5. On 01/03/01, the amortization amount (net present value) is 1,132,600 – 311 = 1,132,288. This results in a write-up of 1,132,288 – 1,129,658 = 2,630 on 01/03/01. In contrast to the method in IAS 39, there is no write-down.

###### Amortization for Money Market Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC > Amortization for Money Market Transactions | L8 | trm08 p.51 | loio `f922a52da1cf44249375b79cdca61213` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f922a52da1cf44249375b79cdca61213.html?locale=en-US)

**Use**

As for the Securities and Loans areas, the amortization function in the Money Market area is used to distribute planned revenue over the term of a money market transaction.

**Integration**

The function corresponds for the most part to the amortization function for securites and loans.

**Prerequisites**

In Customizing for the Transaction Manager, you have made the required settings in the following activities:

- 1. Choose Money Market Transaction Management Transaction Types Define Transaction Types and double-click on the line for the selected product type. Set the indicator Permit Premium/Discount.
- 2. Choose General Settings Accounting Settings for Position Management Key Date Valuation Define Amortization Procedure . Double-click on the amortization procedure and make your settings.


**Note:**

You can use this indicator with the selected product type to specify nominal amounts that differ from the payment amount.

**Note:**

The field entries for Amortization to and Other Components do not affect how the amortization procedure is run for money market transactions. This also applies to the field Treatment of Effective Interest Rate. In this case, the system uses the standard setting 0 Immediate Adjustment of Effective Interest Rate

Field Include Interest: The value 1 Include interest, accrued interest adjustment (securities only) has the same impact as value 2 Effective interest method according to IAS39.

- 3. Choose General Settings Accounting Settings for Position Management Define Position Management Procedure . Double-click on a position management procedure. Specify the pre-defined amortization procedure as the valuation step.
- 4. Choose General Settings Accounting Settings for Position Management Assign Position Management Procedure and make the required settings.
- 5. Choose General Settings Key Date Valuation Update Types Assign Update Types for Valuation and make the required settings.
- 6. Choose General Settings Accounting Derived Business Transactions Update Types Assign Update Types for Derived Business Transactions and make the required settings.


**Features**

The amortization calculation depends mainly on the calculation category selected for the amortization procedure. The system executes the amortization function for each business transaction that changes the position and for each key date valuation.

**Note:**

For fixed-term deposits that can be rolled over, amortization is based only on the business transactions that are in the same rollover period as the amortization key date.

LAC (Linear Method):

The system calculates the amortized acquisition value A of a money market position for key date S as follows:

The system determines the amortized acquisition value A1 for the previous amortization key date S1 (position change or valuation). For the end of term S2, the system uses the last repayment date or the end of the current rollover period in the case of fixed-term deposits with rollover. For the end value E of the amortization curve, the nominal value for the previous amortization key date is used. The following calculation rules apply:

A = A + (E-A ) x (S S ) / (S S )

- 1 1 1 2 1
- 1 2 1 1


(S - S ) and (S - S ) describe the duration between the dates. The difference amount (A - A ) is used to generate a write-up or write-down flow. The system translates the amount of this flow into valuation currency using the book exchange rate of the money market position.

SAC (Effective Interest Method):

To amortize a position on a selected key date, the system first determines the corresponding effective interest rate and then recalculates the cash flow since the last amortization date. To do this, the system generates condition-based flows (interest flows and repayment flows) from this date. The previous cash flow up to and including the last amortization date is replaced by a fictitious inflow equal to the amortized acquisition value of the position on this date. The system uses the effective interest from the (internal) cash flow to discount future flows up to the amortization key date. This determines the new amortized acquisition value of the position.

The system includes interest flows during the effective interest calculation and when discounting, based on your settings for the amortization procedure. Accrued interest is not adjusted. Based on the difference between the new amortized acquisition value and the value on the last amortization key date, the system generates a write-up or write-down flow. The system translates the amount of this flow into valuation currency using the book exchange rate of the money market position.

**Note:**

If you use the Public Sector Management component, you can specify different funds or grants for individual flows in a money market transaction. You can also divide a flow into various funds or grants. Note that the system calculates the cash flow at the level of the entire transaction rather than subledger position level, as the basis for the SAC amortization calculation. The cash flow of the whole transaction is distributed proportionately in the amortization calculation to the respective subledger positions, based on the nominal amounts. This means that transaction flows that do not affect the subledger position due to different funds or grants, will in fact have an impact on amortization for the subledger position. To avoid this happening, you should choose only one fund or grant for each money market transaction.

**Activities**

You do not need to make any settings other than those in Customizing for the Transaction Manager. The system automatically generates amortization flows for each business transaction affecting the position. You can also specify that amortization is carried out on each key date valuation.

**Example**

Example: Premium/Discount for an Interest Rate Instrument

Example: Discount for a Fixed-Term Deposit with Rollover

###### Example: Premium/Discount for an Interest Rate Instrument

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC > Amortization for Money Market Transactions > Example: Premium/Discount for an Interest Rate Instrument | L9 | trm08 p.53 | loio `18ecf6b0668449b2a13cddb41370254a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/18ecf6b0668449b2a13cddb41370254a.html?locale=en-US)

Initial Data

The following cash flow applies to an interest rate instrument (product category 550) with installment repayment:

|No.|Date|Business Transaction|Nominal Amount|Payment Amount|
|---|---|---|---|---|
|1|01/01/x1|Increase|1000|900|
|2|07/01/x1|Reduction|500|500|
|3|01/01/x2|Nominal Interest Rate| |10|
|4|01/01/x2|Nominal Interest Rate| |5|
|5|01/01/x2|Installment Repayment|250|250|
|6|01/01/x3|Nominal Interest Rate| |5|
|7|01/01/x3|Installment Repayment|250|250|


For this transaction, you have specified flows 1 and 2 that affect the capital structure. You have chosen the interest calculation method 7 360/360. You have agreed upon an annual installment repayment of 250.

You have specified that the system is to manage this transaction in position management using the position management category 8 -Securities/Loans/Money Market with Installment Repayment.

You have defined the SAC Net amortization procedure and the Effective Interest Method In Accordance with IAS 39.

You have set the indicator Amortization for Installment Repayments.

Flows in Position Management

After you have created the transaction, the system lists the following flows in position management (transaction Position Flow List

- TPM13):

|Nr.|Date|Update Type|Nominal Amount|Amount in Position Currency|
|---|---|---|---|---|
|1|01/01/x1|Asset / Increase|1000|900|
|2|07/01/x1|Asset / Reduction|500|500|
|3|07/01/x1|Positive amortization| |37,08|
|4|07/01/x1|Translation purchase value| |450|
|5|07/01/x1|Translation amortization| |18,54|
|6|07/01/x1|Security price gain| |31,46|
|7|01/01/x2|Asset / Nominal Interest| |10|
|8|01/01/x2|Asset / Nominal Interest| |5|
|9|01/01/x2|Asset / Installment Repayment|250|250|
|10|01/01/x2|Positive amortization| |10,66|
|11|01/01/x3|Asset / Nominal Interest| |5|
|12|01/01/x3|Asset / Installment Repayment|250|250|
|13|01/01/x3|Positive amortization| |20,80|
|14|01/01/x3|Translation purchase value| |450|
|15|01/01/x3|Translation amortization| |50|
|16|01/01/x3|Translation repayment| |500|


The system uses flow 2 (capital reduction) to generate amortization (flow 3) which is calculated as follows:

The position should be amortized before the reduction in capital. Therefore the system recalculates the cash flow based on the conditions and by only taking into account the increase on 01/01/x1. This results in the following flows:

- 1. Increase on 01/01/x1 at an amount of 900 and nominal amount of 1000
- 2. Nominal interest on 01/01/x2 at an amount of 20
- 3. Installment repayment on 01/01/x2 with nominal amount of 250 and amount of 250
- 4. Nominal interest on 01/01/x3 amounting to 15


- 5. Installment repayment on 01/01/x2 with nominal amount of 250 and amount of 250
- 6. Final repayment on 01/01/x3 with a nominal amount of 500 and an amount of 500


The effective interest rate of this cash flow is 8.41 percent (AIBD/ISMA). The flows that are discounted after 01/07/x1 to the amortization key date on 01/07/x1 determine the new amortized acquisition value of 937.08. This leads to a write-up of 37.08 = 937.08 – 900 (flow 3).

Due to flows 2 through 6, the amortized acquisition value on 07/01/x1 is 468.54 = 900 + 37.08 – 450 – 18.54.

The next time amortization occurs is with the installment repayment on 01/01/x2 (flow 9). The system selects the flows up to the last amortization key date on 07/01/x1. It then recalculates the cash flow, based on these flows and the conditions. The flows that occurred prior to the last amortization key date are then replaced by an inflow which correspondes to the amortized acquisition value of the position for this date. This results in the following flows:

- 1. Increase on 07/01/x1 with a nominal amount of 500 and amount of 468.54
- 2. Nominal interest on 01/01/x2 at an amount of 10
- 3. Nominal interest on 01/01/x2 at an amount of 5
- 4. Installment repayment on 01/01/x2 with nominal amount of 250 and amount of 250
- 5. Nominal interest on 01/01/x3 amounting to 5
- 6. Installment repayment on 01/01/x2 with nominal amount of 250 and amount of 250


The effective interest rate of this cash flow is 11.25 percent (AIBD/ISMA). The deduction of the flows on and after 01/01/x2 to the amortization key date 01/01/x2 result in the new amortized acquisition value of 479.20. Neither of the interest flows on 01/01/x2 are taken into account for the deduction since there were considered at the time of amortization. The new amortized acquisition value leads to a write-up of 10.66 = 479.20 – 468.54 (flow 10).

Based on flows 9 though 10, the amortized acquisition value on 01/01/x2 is 229.20 = 468.54 – 250 + 10.66.

The next time amortization occurs on 01/01/x3, the following internal flows are used:

- 1. Increase on 01/01/x2 with a nominal amount of 250 and amount of 229.20
- 2. Nominal interest on 01/01/x3 amounting to 5
- 3. Installment repayment on 01/01/x2 with nominal amount of 250 and amount of 250


The effective interest rate is 11.26 percent (AIBD/ISMA). The new amortized acquisition value is 250 and leads to a write-up of 20.80 = 250 – 229.20 (flow 13).

**Note:**

Amortization on the key date 12/31/x1 would result in an amortized acquisition value of 494.20 and therefore positive amortization of 25.66. The amortization for the installment repayment on 01/01/x2 would then have produced negative amortization with a value of 15, which corresponds to the interest payments on 01/01/x2.

###### Example: Discount for a Fixed-Term Deposit with Rollover

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization According to LAC and SAC > Amortization for Money Market Transactions > Example: Discount for a Fixed-Term Deposit with Rollover | L9 | trm08 p.53 | loio `900e4c10c9cf4454845bca627f476937` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/900e4c10c9cf4454845bca627f476937.html?locale=en-US)

Initial Data

The following cash flow applies to a fixed-term deposit (product category 510):

|Number|Date|Business Transaction|Nominal Amount|Payment Amount|
|---|---|---|---|---|
|1|01/01/x1|Increase|1000|900|
|2|07/01/x1|Reduction|500|500|
|3|01/01/x2|Nominal interest rate| |10|
|4|01/01/x2|Nominal interest rate| |5|
|5|01/01/x2|Rollover|0|0|
|6|01/01/x3|Nominal interest rate| |10|
|7|01/01/x3|Final Repayment|500|500|


For this transaction, you have specified flows 1 and 2 that affect the capital structure. You have chosen the interest calculation method 7 360/360.

You have specified that the system is to manage this transaction in position management using the position management category 1 Securities/Loans/Money Market/Listed Options, Normal Style.

You have defined the SAC Net amortization procedure and the Effective Interest Method In Accordance with IAS 39.

Flows in Position Management

Once you have created and rolled over the transaction, the system lists the following flows in position management (transaction Position Flow ListTPM13):

|Number|Date|Update Type|Nominal Amount|Amount in Position Currency|
|---|---|---|---|---|
|1|01/01/x1|Asset / Increase|1000|900|
|2|07/01/x1|Asset / Reduction|500|500|
|3|07/01/x1|Positive amortization| |58,13|
|4|07/01/x1|Translation purchase value| |450|
|5|07/01/x1|Translation amortization| |29,07|
|6|07/01/x1|Security price gain| |20,93|
|7|01/01/x2|Asset / Nominal Interest| |10|
|8|01/01/x2|Asset / Nominal Interest| |5|
|9|01/01/x2|Asset / Increase|0|0|
|10|01/01/x2|Positive amortization| |20,94|
|11|01/01/x3|Asset / Nominal Interest| |10|
|12|01/01/x3|Asset / Final repayment|500|500|
|13|01/01/x3|Translation purchase value| |450|
|14|01/01/x3|Translation amortization| |50|


The term of the transaction is divided into two rollover periods. Amortization is always based on the business transactions in the rollover periods, which also include the amortization key date.

The system uses flow 2 (capital reduction) for amortization (flow 3). The system calculates amortization in the following way:

The position needs to be amortized before the reduction in capital. Therefore the system recalculates the cash flow based on the conditions and by only taking into account the increase on 01/01/x1. This results in the following flows:

- 1. Increase on 01/01/x1 at an amount of 900 and nominal amount of 1000
- 2. Repayment on 01/01/x2 at an amount of 1000 and nominal amount of 1000
- 3. Nominal interest on 01/01/x2 at an amount of 20


The effective interest rate of this cash flow is 13.33 percent (AIBD/ISMA). The repayment discount on 01/01/x2 which amounts to 1000 as well as the interest flow on 01/01/x2 with a value of 20 up to the amortization key date on 07/01x1 produce the new amortized acquisition value of 958.13. The write-down amount is 58.13 = 958.13 900 (flow 3). The system uses flows 2 to 6 to calculate the amortized acquisition value on 07/01x1 as follows: 479.06 = 900 + 58.13 450 29.07.The next amortization is made with the rollover (flow 9). The system generates an internal cash flow comprising the following flows:

- 1. Increase on 07/01x1 at an amount of 479.06 (the amortized acquisition value of the position on 07/01x1) and nominal amount of 500
- 2. Repayment on 01/01/x2 at an amount of 500 and nominal amount of 500
- 3. Nominal interest on 01/01/x2 at an amount of 5
- 4. Nominal interest on 01/01/x2 at an amount of 10


The effective interest rate of this cash flow is 15.57 percent (AIBD/ISMA). The repayment discount of 500 on 01/01x2 to 01/01x2 is the new amortized acquisition value of 500. Neither of the interest flows are taken into account for the discount on the repayment since they were considered on the amortization key date on 01/01x2. This leads to a write-up of 20.94 = 500 479.06. On 01/01x2, the amortized acquisition value is now 500. There is no write-up or write-down on 01/01x3 since the new and old amortized acqusition values match.Once again, the interest flow is not taken into account when the deposit is discounted since it is assumed it was considered at the time of amortization.

If amortization were to be included in the key date valuation on 07/01x2, it would produce an internal cash flow with the following flows:

- 1. Increase on 01/01x2 at an amount of 500 and nominal amount of 500
- 2. Repayment on 01/01x3 at an amount of 500 and nominal amount of 500
- 3. Nominal interest on 01/01x3 with a value of 10


The effective interest rate would be 2.0 percent (AIBD/ISMA). The discount on the repayment from 01/01x3 with a value of 500 together with the interest flow of 10 on 01/01x3 up to the amortization key date on 07/01x2 would result in a new amortized acquisition value of 504.97. The write-up amount would be 4.97 = 504.97 500. There would be a write-down of 4.97 for the installment repayment on 01/01x2.

###### Amortization at Key Date Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization at Key Date Valuation | L7 | trm08 p.57 | loio `920bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/920bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

To calculate amortization at the time of key date valuation, the following information applies:

Amortization occurs in parallel position management according to the incremental procedure. At the time of the last amortization, the system generates a fictitious (hypothetical) purchase. The fictitious purchase and all future repayments form the cash flow. At the time of amortization, the future repayments are discounted by the system at the internal rate of return.

The system does not adjust the accrued interest for the fictitious purchase because the internal rate of return would be incorrect.

The system also takes into account interest due between the last business transaction, when amortization occurred (purchase, sale, repayment, valuation), and the amortization key date (when the fictitious purchase is generated).

**Example**

|Date|Flow|Nominal Amount|Amount in Position Currency|Note|
|---|---|---|---|---|
|01.01.01|Purchase|100|80|1.|
|01.07.01|Key date amortization| |4,305|2.|
|01.01.02|Interest| |5|3.|
|01.07.02|Key date amortization| |9,965|4.|
|01.01.03|Interest| |5|3.|
|01.01.03|Repayment|100|80| |
| |Amortization| |5,73|5.|


- 1. A purchase is made at a rate of 80%. The discount is 20%.
- 2. Calculation of amortization:

Since the fictitious purchase and real purchase do not correspond, the system determines the internal rate of return in the same way as for the non-incremental procedure. The internal rate of return is 1.17732.

Discounting of the relevant flows after the amortization key date results in the following amortized purchase price amount: 5 / 1,17732 ** 0,5 + 105 / 1,17732 ** 1,5 = 86,8054

Taking the accrued interest correction into consideration results in the following amortization amount: 86,8054 80 5 * 180 / 360 = 4,3054

- 3. The interest rate is 5%.
- 4. Calculation of amortization:


The amortized acquisition value is regarded as the fictitious purchase value. This is increased by the accrued interest: 80 +

- 4.3054 + 2.5 = 86.8054The accrued interest adjustment amount of the last amortization corresponds to the accrued interest of the fictitious purchase.

The equation 5 / (1 + i) ** 0.5 + 105 / (1 + i) ** 1.5 = 86.8054 determines the new internal rate of return of 0.17732.

Discounting of the relevant flows after the amortization due date results in the following amortized purchase price amount: 105 / 1,17732 ** 0,5 = 96,771

The amortization amount is determined by subtracting the accrued interest and the amortized acquisition value from the purchase price: 96.771 (80 + 4.3054) 2.5 = 9.9656

- 5. Calculation of amortization:


The amortized acquisition value is regarded as the fictitious purchase value. This is increased by the accrued interest adjustment:

80 + 4,3054 + 9,9656 + 2,50 = 96,771

The equation 105 / (1 + i) ** 0.5 = 96.771 determines the new internal rate of return of 0.17732.

Discounting of the relevant flows after the amortization due date results in the following amortized purchase price amount: 105 / 1,17732 ** 0 = 105

Amortization is determined by subtracting the accrued interest and amortized acquisition value: 105 (80 + 4,305 + 9,965) 5 * 360 / 360 = 5,73

###### Amortization After a Partial Outflow

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization After a Partial Outflow | L7 | trm08 p.59 | loio `890bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/890bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

In this example, a partial outflow occurs in addition to key date valuation.

**Example**

|Date|Flow|Nominal Amount|Amount in Position Currency|Note|
|---|---|---|---|---|
|01.01.01|Purchase|100|80|1.|
|01.07.01|Key date amortization| |4,3054|2.|
|01.01.02|Interest| |5|3.|
|01.04.02|Partial outflow|25|20|4.|
| |Translation purchase value| |20|5.|
| |Amortization| |7,3456|6.|
| |Translation amortization| |2,9128|7.|
| |Price losses| |-2,9128|8.|
|01.07.02|Key date amortization| |1,9647|9.|
|01.01.03|Interest| |3,75|10.|
|01.01.03|Repayment|75|75| |
| |Translation purchase value| |60|11.|
| |Amortization| |4,2973|12.|
| |Translation amortization| |15|13.|


- 1. A purchase is made at a rate of 80%. There is 20% discount.
- 2. Calculation of amortization:


Since the fictitious purchase and real purchase do not correspond, the system determines the internal rate of return in the same way as for the non-incremental procedure. The internal rate of return is 1.17732.

Discounting of the relevant flows after the amortization key date results in the following amortized purchase price amount:

5 / 1,17732 ** 0,5 + 105 / 1,17732 ** 1,5 = 86,8054

Taking the accrued interest correction into consideration results in the following amortization amount:

86,8054 80 5 * 180 / 360 = 4,3054

- 3. The interest rate is 5%.
- 4. A sale with a nominal value of 25 is made at a rate of 80%.
- 5. The system clears the purchase value on a pro rata basis using translation: 80 * 25 / 100 = 20 80 * 25 / 100 = 20
- 6. Calculation of amortization:

The amortized acquisition value is regarded as the fictitious purchase value. This is increased by the accrued interest adjustment: 80 + 4.3054 + 2.50 = 86.8054 80 + 4,3054 + 2,50 = 86,8054

The equation 5 / (1 + i) ** 0.5 + 105 / (1 + i) ** 1.5 = 86.8054 contains the new internal rate of return. This amounts to 0.17732.

Discounting of the relevant flows after the amortization due date results in the following amortized purchase price amount:105 / 1,17732 ** (270 / 360) = 92,9006. The following interest is accrued for the period 01/01/02 to 04/01/02: 5 * 90 / 360 = 1.25 5 * 90 / 360 = 1,25

The amortization amount is determined by subtracting the accrued interest and the amortized acquisition value from the discounted future flows: 92.9006 (80 + 4.3054) 1.25 = 7.3456 92,9006 (80 + 4,3054) 1,25 = 7,3456

- 7. The system clears the cumulative amortization value proportionately: 4.3054 + 7.3456) * 20/ 80 = 2.9128. 4,3054 + 7,3456) * 20/ 80 = 2,9128

The net present value is calculated as follows: 80 + 4.3054 + 7.3456) * 60 / 80 = 68.7383. 80 + 4,3054 + 7,3456) * 60 / 80

= 68,7383

This value includes the proportionate accrued interest adjustment: 1.25 * 60 / 80 = 0.9375. 1,25 * 60 / 80 = 0,9375

- 8. Rate differences are determined by subtracting the translation from the outflow revenue: 20 20 2.9128 = -2.9128. 20 20 2.9128 = -2,9128

Price/rate losses occur since the outflow revenue is lower than the amortized outflow amount.

- 9. Calculation of amortization:


The amortized acquisition value is regarded as the fictitious purchase value which may be increased by the accrued interest of the fictitious purchase (or the proportionate accrued interest of the last amortization): 68.738 + 3.75 * 90 / 360 = 68.738 + 0.9375 = 69.67575 68,738 + 3,75 * 90 / 360 = 68,738 + 0,9375 = 69,67575

The equation 75 + 3.75) / (1 + i) ** 0.75 = 69.67575 contains the new internal rate of return. This amounts to 0.17732.

The following amortized acquisition value is determined by discounting the relevant flows after the amortization key date: 78.75 / 1.17732 ** 0.5 = 72.5777 78,75 / 1,17732 ** 0,5 = 72,5777

Amortization is determined by subtracting the old amortized acquisition value and the accrued interest adjustment from the new acquisition value: 97.21110 - 90 2.5 = 4.721110 72,5777 68,738 3,75 * 180 / 360 = 1,9647

The new amortized acquisition value is determined as follows: 72.5777 3.75 * 180 / 360 = 70.7027

- 10. The system calculates the interest for the remaining nominal value of 75.
- 11. The remaining purchase value is determined by 80 20 (partial outflow 04/01/02) = 60. The system clears this value using translation.
- 12. Calculation of amortization:

The amortized acquisition value is regarded as the fictitious purchase value. This is increased by the accrued interest adjustment: 80 + 4.3054 + 2.50 = 86.8054 70,7027 + 3,75 * 180 / 360 = 72,5777

The equation 78.75 / (1 + i) ** 0.5 = 72.5777 contains the new internal rate of return. This amounts to 0.17732.

The following amortized acquisition value is determined by discounting the relevant flows after the amortization key date: 78.75 / 1.17732 ** 0 = 78.75 78,75 / 1,17732 ** 0 = 78,75

Amortization is determined as follows: 78.75 70.7027 3.75 * 360 / 360 = 4.2973 78,75 70,7027 3,75 * 360 / 360 = 4,2973

- 13. The system clears the cumulative amortization amounting to 1.9647.


This is calculated in the following way:

4.3054 (key date amortization 07/01/01) + 7.3456 (amortization 04/01/02) 2.9128 (translation of amortization 04/01/02) + 1.9647 (key date amortization 07/01/02) + 4.2973 (remaining amortization until maturity) = 15.

This amortization amount is also determined by calculating total amortization of the remaining purchase value: (100- 25) * (100% - 80%) = 15. (100- 25) * (100% - 80%) = 15

The component chart shows the effects of the individual business transactions:

|Date|Flow|Nominal Amount|Purchase Value|Amortization|Settlement|
|---|---|---|---|---|---|
|01.01.01|Purchase|100|80|0|0|
|01.01.01|Component position|100|80|0|0|
|01.07.01|Key date amortization|0|0|4,3054|0|
|01.01.01|Component position|100|80|4,3054|0|
|01.04.02|Partial outflow|- 25|0|0|-20|
| |Translation purchase value|0|-20|0|20|
| |Amortization|0|0|7,3456|0|
| |Translation amortization|0|0|-2,9128|2,9128|
| |Exchange rate differences|0|0|0|-2,9128|
|01.04.02|Component position|75|60|8,7383|0|
|01.07.02|Key date amortization|0|0|1,9647|0|
|01.07.02|Component position|75|60|10,7030|0|
|01.01.03|Repayment|-75|0|0|-75|


|Date|Flow|Nominal Amount|Purchase Value|Amortization|Settlement|
|---|---|---|---|---|---|
| |Translation purchase value|0|-60|0|60|
| |Amortization|0|0|4,2973|0|
| |Translation amortization|0|0|-15|15|
|01.01.03|Component position|0|0|0|-0,0003|

###### Amortization After an Outflow and Partial Inflow

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization After an Outflow and Partial Inflow | L7 | trm08 p.62 | loio `8c0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8c0bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

If a partial inflow occurs immediately after an outflow, the incremental amortization procedure only considers the partial inflow on a pro rata basis when determining the internal rate of return. In the case of the non-incremental procedure, however, the partial inflow is included completely in the calculation.

**Note:**

Amortization takes place no more than once a day.

**Example**

|Date|Flow|Nominal Amount|Amount in Position Currency|Note|
|---|---|---|---|---|
|01.01.01|Purchase|100|80| |
|31.12.01|Sale|100|80|1.|
| |Translation purchase value| |80|2.|
| |Amortization| |9,1856|3.|
| |Translation amortization| |9,1856|4.|
|01.01.02|Purchase|100|90|5.|
| |Amortization| |0|6.|
|01.07.02|Key date amortization| |4,721110|7.|
|01.01.03|Interest| |5| |
|01.01.03|Repayment|100|100| |
| |Translation purchase value| |90| |


- 1. After being purchased, the total position is then resold at a rate of 80%.
- 2. The total purchase value, amounting to 80, is then cleared using translation.


- 3. Calculation of amortization:

Since the fictitious purchase and real purchase do not correspond, the system determines the internal rate of return in the same way as for the non-incremental procedure.

Discounting of the relevant flows after the amortization key date results in the following amortized purchase price amount: 5 / 1,17732 ** 0,5 + 105 / 1,17732 ** 1,5 = 86,8054

Taking the accrued interest correction into consideration results in the following amortization amount:

86,8054 80 5 * 180 / 360 = 4,3054

This results in the following amortization amount:

89,1856 80 = 9,1856

- 4. The system clears the amortization amount completely using translation.
- 5. A purchase with a nominal amount of 100 is made at a rate of 90%.
- 6. Since the book value is up-to-date on the purchase date, amortization is not triggered on this day.
- 7. Calculation of amortization:


Since the amortized acquisition value was previously zero without accrued interest adjustment, the purchase value on 01/01/02 amounting to 90 is regarded as the fictitious purchase value.

The equation 105 / (1 + i) = 90 contains the new internal rate of return. This produces an amount of 0.166667.

Discounting of the relevant flows after the amortization due date results in the following amortized purchase price amount:

105 / 1,166667 ** 0,5 = 97,21110

Amortization is determined by subtracting the old amortized acquisition value and the accrued interest adjustment from the new acquisition value:97.21110 - 90 2.5 = 4.721110 97,21110 - 90 2,5 = 4,721110

**Note:**

Non-Incremental Procedure:

If you use the non-incremental procedure, the internal rate of return is contained in the equation -80 + (90 -5) / (1 + i) + (200 +

10) / (1+ i) ** 2. This rate is based on amortization on the key date 07/01/02. The internal rate of return is 0.173809.

The net present value is calculated as follows: 105 / 1,173809 90 2,5 = 4,14

###### Amortization After Migration from the Operative Valuation Area

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization After Migration from the Operative Valuation Area | L7 | trm08 p.63 | loio `8f0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8f0bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

One difference between the amortization procedures is that, in the case of the incremental procedure, all the business transactions that affect the position lead to amortization, whilst the non-incremental procedure only amortizes outflows. This difference only applies to flows that affect a position. It does not affect key date amortization.

In the case of migration and the conversion from the non-incremental SAC procedure to the incremental procedure, the following should be taken into consideration:

After migration, the system executes various amortization processes, depending on whether amortization occurred for a further key date after the last business transaction affecting the position.

**Example**

The non-incremental SAC procedure is used first. Conversion to the incremental procedure then occurs immediately after key date amortization on 07/01/02. Key date amortization occurs again on 10/01/02.

In the following example, there is no key date amortization on 07/01/02:

|Date|Flow|Nominal Amount|Amount in Position Currency|Note|
|---|---|---|---|---|
|01.01.01|Purchase|100|80| |
|01.07.01|Key date amortization| |4,3054|1.|
|01.01.02|Interest| |5| |
|01.04.02|Partial outflow|25|20| |
| |Translation purchase value| |20| |
| |Amortization| |1,8364|2.|
| |Translation amortization| |2,9129|3.|
| |Price losses| |-2,9128|4.|
|01.10.02|Key date amortization| |8,2215|5.|
|01.01.03|Interest| |3,75| |
|01.01.03|Repayment|75|75| |
| |Translation purchase value| |60| |
| |Amortization| |3,5495|6.|
| |Translation amortization| |15,000| |


- 1. As there is only one purchase, the non-incremental procedure generates the same internal rate of return and therefore the same key date amortization as the incremental SAC method.
- 2. In the case of a sale, only the outgoing portion of the position is amortized with the non-incremental procedure: 7.3456 * 25 / 100 = 1.8364 7,3456 * 25 / 100 = 1,8364
- 3. The system uses translation to clear the portion of key date amortization amounts corresponding to the outflow, and the current amortization amount: 4.3054 * 25 / 100 + 1.8364 = 2.9128 4,3054 * 25 / 100 + 1,8364 = 2,9128
- 4. The rate gain/loss is determined by subtracting the translation amounts from the outflow revenue: 20 20 2.9128 = -2.9128 20 20 2,9128 = -2,9128
- 5. Calculating key date amortization:


After migration, the incremental SAC method is used.

The amortized acquisition value on 04/01/02 is regarded as the fictitious purchase value. This is increased by the accrued interest adjustment: 80 (original purchase value) - 20 (translation purchase value on 04/01/02) + 4.3054

+ 1.8364 2.9128 + 3.75* 270 / 360 = 66.0415

The equation 78.75 / (1 + i) ** 0.75 = 66.0415 contains the new internal rate of return. This produces an amount of 0.26448.

Discounting of the relevant flows after the amortization due date results in the following amortized purchase price amount: 78,75 / 1,26448 ** 0,25 = 74,2630

Amortization is determined by subtracting the accrued interest from the amortized acquisition value: 74.2630 63.229 3.75 * 270 / 360 = 8.2215 74,2630 63,229 3,75 * 270 / 360 = 8,2215

- 6. Amortization is determined by subtracting the accrued interest from the previously amortized acquisition value: 75 (74.2630 3.75 * 270 / 360) = 3.5495 75 (74,2630 3,75 * 270 / 360) = 3,5495


**Note:**

Since amortization takes place on a coupon date, interest and accrued interest cancel each other out.

In the following example, key date amortization occurs immediately before migration:

|Date|Flow|Nominal Amount|Amount in Position Currency|Note|
|---|---|---|---|---|
|01.01.01|Purchase|100|80| |
|01.07.01|Key date amortization| |4,3054| |
|01.01.02|Interest| |5| |
|01.04.02|Partial outflow|25|20| |
| |Translation purchase value| |20| |
| |Amortization| |1,8364| |
| |Translation amortization| |2,9129| |
| |Price losses| |-2,9128| |
|01.07.02|Key date amortization| |7,4737|1.|
|01.10.02|Key date amortization| |2,0857|2.|
|01.01.03|Interest| |3,75| |
|01.01.03|Repayment|75|75| |
| |Translation purchase value| |60| |
| |Amortization| |1,8364|3.|


- 1. Calculating key date amortization:


Only one purchase was made so the internal rate of return stays the same at 0.17732.

The following amortized acquisition value is determined by discounting the incoming payments on 01/01/003: 78.75 / 1.17732 ** 0.5 = 72.5777 78,75 / 1,17732 ** 0,5 = 72,5777

Amortization is determined by subtracting the accrued interest adjustment amount from the previously amortized acquisition value: 72.5777 63.229 3.75 / 2 = 7.4737 72,5777 63,229 3,75 / 2 = 7,4737

- 2. Calculating key date amortization:

After migration, the SAC method is used.

The amortized acquisition value on 07/01/02 is taken to be the fictitious purchase value. This is increased by the accrued interest adjustment: 72.5777 (discounted incoming payments) 3.75 / 2 (accrued interest adjustment) + 3.75 / 2 (accrued interest adjustment) = 72.5777

The equation 78.75 / (1 + i) ** 0.5 = 72.5777 contains the new internal rate of return. This amount is 0.17732. The internal rate of return stays the same due to key date amortization occurring before migration.

Discounting of the relevant flows after the amortization due date results in the following amortized purchase price amount: 78,75 / 1,17732 ** 0,25 = 75,6009.

Amortization is determined by subtracting the accrued interest from the amortized acquisition value: 75.6009 (72.5777 3.75 / 2) 3.75 * 270 / 360 = 75.6009 72.5777 3.75 / 4 = 2.0857

- 3. Amortization is determined by subtracting the accrued interest from the previously amortized acquisition value: 75 (75.6009 3.75 * 270 / 360) = 2.2116


**Note:**

Since amortization takes place on a coupon date, interest and accrued interest cancel each other out.

**Result**

If key date amortization does not occur before the migration, the amortization curve after migration will be steeper. The difference is not completely cleared by the first amortization after migration.

###### Amortization in the Case of a Changing Nominal Interest Rate

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization in the Case of a Changing Nominal Interest Rate | L7 | trm08 p.66 | loio `860bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/860bda531198434de10000000a174cb4.html?locale=en-US)

If interest is taken into account during amortization and the nominal interest rate is variable, the amortized acquisition value may temporarily exceed the final repayment amount, even if it is issued below par.

If the issue is above par, the amortized acquisition value may temporarily be less than the repayment amount.

The effect is shown in the following example.

A bond is purchased on 01/01/01 with a variable interest rate of 99%.

The following interest payments are made:

- 01/01/02: 3.0 %
- 01/01/03: 4.0 %
- 01/01/04: 5.0 %


Repayment occurs on 01/01/04 at 100%.

The internal rate of return is 4.334%. This is determined by discounting the future interest payments and repayments, based on the net present value and the interest:

[figure TRM08-F012]

The calculation of the individual amortized acquisition values produces the following graphical trend:

[figure TRM08-F013 - In the selected period, the amortized acquisition value of the bond exceeds the repayment rate of 100%.]

In the selected period, the amortized acquisition value of the bond exceeds the repayment rate of 100%.

###### Amortization Using Issue Spread / Negotiation Spread

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization Using Issue Spread / Negotiation Spread | L7 | trm08 p.67 | loio `6619c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6619c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

As part of this amortization procedure, the amount to be amortized is divided into issue spread and negotiation spread.

The issue spread is the difference between the repayment amount of a bond or loan, and the amount resulting from compounding the issue amount up to the purchase date (nominal amount x issue rate).

The negotiation spread is the difference between the amount that is derived from compounding the issue amount of a bond or loan (nominal amount x issue rate) to the purchase date, and the amount at which the bond or loan is sold.

[figure TRM08-F014 - Overview: Issue Spread and Negotiation Spread]

Overview: Issue Spread and Negotiation Spread

**Features**

This function can be used with the following position management categories:

Securities/Loans/Money Market without index-linked bonds

Index-Linked Bonds

Securities/Loans with Installment Repayment (without index-linked bonds)

The issue spread is cleared in accordance with the settings in the amortization procedure that uses the acquisition value that is modified by the negotiation spread. It uses the Amortization position component (1007).

The following options are available for the negotiation spread:

The negotiation spread is amortized using the straight-line method.

It uses the position componentDeferral Item,PurchaseValue(1010) and during amortization, the amount is transferred on a linear basis to the position component Amortization Using Negotiation Spread (1019).

The negotiation spread is amortized on an exponential basis as part of the amortization procedure.

It uses the position component Deferral Item for Purchase Value (1010) and during amortization, the amount is cleared on an exponential basis and transferred to the position component Amortization Using Negotiation Spread

(1019)

The negotiation spread is not amortized.

Only the issue spread is amortized. The negotiation spread uses the position component Deferral Item for Purchase Value (1010) and is written off as net income at the end of the term.

**Prerequisites**

If you want to use this amortization procedure, you must choose one of the setting options listed below. To do this, in Customizing for Treasury and Risk Management, choose Transaction Manager General Settings Accounting Settings for Position Management Key Date Valuation Define Amortization Procedure . Choose Other Components, and then one of the following options:

Negotiation Spread, Linear

Negotiation Spread, Exponential

Negotiation Spread without Amortization

###### Amortization Using the Deferral Item for the Purchase Value (Discounts/Premiums)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Amortization Using the Deferral Item for the Purchase Value (Discounts/Premiums) | L7 | trm08 p.69 | loio `af0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/af0bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Based on the issue value of a security, a yield curve can be determined from the time of issue to the time of repayment.If a security is purchased during the term, its price is usually above or below this theoretical yield curve. If you use the position component

Deferral Item for the Purchase Value, it displays the difference between the actual security purchase value and the value of the security according to the theoretical yield curve. During amortization, the deferral item for the purchase value is deducted pro rata over the remaining term using the straight line method.

The deferral item is not included in the book value nor taken into account when price/rate gains are calculated.

The deferral item for the purchase value is included in the purchase value, which means that standard amortization is based on the modified acquisition value. The deferral item for the purchase value is also deferred on a linear basis for amortization purposes.

[figure TRM08-F015 - Deferral Item, Purchase Value]

Deferral Item, Purchase Value

This position component may be positive (deferred income) or negative (deferred expenses).

For the derived business transactions for the position inflows and outflows, and the key date valuation, the system generates corresponding flows.

**Note:**

The deferral item for the purchase value is deferred with the key date valuation function and not with the accrual/deferral function.

The function can be used in both the gross and net procedures.

**Prerequisites**

The Deferral Item for the Purchase Value function is used for the position management categories Securities/Loans/Money Market Without Index-Linked Bonds and Index-Linked Bonds.

You make these settings in Customizing for Treasury and Risk Management by choosing Transaction Manager Accounting Settings for Position Management Key Date Valuation Define Amortization Procedure .

Under Other Components, in the amortization procedure, you must select Deferral Item for the Purchase Value.

**Example**

For zero bonds, it is required by law that the purchase value in the financial statement for tax purposes corresponds to the value of the issue yield curve as opposed to the purchase price paid. Zero bonds must therefore be amortized in accordance with the issue yield curve.

The difference in purchase price is managed as an accrued/deferred item and cleared equally over the term to the profit and loss account. The deferrals are cleared on an incremental basis for each position change and key date valuation.

The deferral item is not included in the book value nor taken into account when calculating price/rate gains.

- Case 1

The purchase price of a zero bond amounting to 100,000 UNI (nominal amount) at a rate of 60% is 60,000. The current market value on the issue yield curve according to SAC amortization is 70,000.

The book value is 60,000.

The deferral item for the purchase value (deferred income) is displayed for the difference in amount of 10,000 on the issue yield curve. This amount is then cleared over the term on a linear basis.

If the security is sold at a price of 60,000 directly after it has been purchased, there is a price loss of 10,000. The posting-relevant translation of the deferral item and the offsetting posting (deferred income) clear the balance on the profit and loss account.

- Case 2


[figure TRM08-F016]

###### Example: Discounts for Security Purchases (Gross Procedure)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Amortization > Example: Discounts for Security Purchases (Gross Procedure) | L7 | trm08 p.71 | loio `2d0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2d0dda531198434de10000000a174cb4.html?locale=en-US)

This example explains the gross procedure for managing premiums/discounts. You can see all the flows that arise from the purchase of a security with a 50% discount, including a key date valuation (amortization), right up to the sale of the security.

**Note:**

The update types used in the example correspond to the Customizing settings delivered with the system.

**Prerequisites**

In Customizing under Assign Position Management Procedure, you must assign a position management procedure for security positions. This procedure must specify the gross procedure for the management of premiums/discounts, and amortization for performing the key date valuations.

**Process Flow**

- 1. First the security purchase is concluded in transaction management with a discount of 50%. The system generates the following flows:

Update type SE1000 Purchase

Posting record:

Position (debit) - bank (credit) 1,000 EUR (1)

A derived business transaction is generated to post the discount.

Update type DBT_A005 Post discount

Posting record

Position (debit) - deferred income (credit) 1,000 EUR (2)

- 2. At year end, the position is amortized by way of valuation. This means a write-up of 100 EUR.

Update type V302 Amortization (Write-up)

Posting record

- Deferred income (debit) - interest revenue (credit) 100 EUR (3)

3. Sale of the position using transaction management for the amount of 1,500 EUR.

Update type SE2000 Sale

Posting record:

Balance sheet clearing (debit) - position (credit) 1,500 EUR (4a)

A derived business transaction is generated for the amortization up to the sale date.

Update type DBT_C006 Amortization

Posting record:

- Deferred income (debit) - interest revenue (credit) 100 EUR (4b)




A derived business transaction is generated to clear the discount.

Update type DBT_E019 Translation Discount

Posting record:

Deferred income (debit) - P&L (credit) 800 EUR (4c)

A derived business transaction is generated to post the realized rate loss.

Update type DBT_B003 Rate Loss

Posting record:

Realized rate losses (debit) - position (credit) 500 EUR (4d)

A translation (not relevant for posting) is generated through the clearing of the purchase value from the position component:

Update type DBT_E001 Translation Purchase Value 1,000 EUR

**Example**

[figure TRM08-F017 - Discount for Security Purchases (Gross Procedure)]

Discount for Security Purchases (Gross Procedure)

###### One-Step Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > One-Step Valuation | L6 | trm08 p.73 | loio `6919c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6919c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

The one-step valuation procedure uses the total amount in local currency as the basis for determining write-ups and write-downs, creating and reversing provisions, and disclosing unrealized gains/losses in a single step.

See also:

Two-Step Valuation

**Integration**

One-step valuation is supported for the following product categories:

|Loans:|300 Mortgage 310 Borrower’s note loan 320 Policy loan 330 General loan|
|---|---|
|Securities:|010 Stock 020 Investment certificate 030 Subscription right 040 Bond 041 Bond with redemption schedule 060 Warrant bond 070 Convertible bond 111 Index warrant 112 Equity warrant 113 Currency warrant 114 Bond warrant 160 Shareholding|
|Money market transactions:|510 Fixed-term deposit 520 Deposit at notice 530 Commercial paper 540 Cash flow transactions 550 Interest rate instrument|
|Foreign Exchange:|600 Foreign exchange|
|Derivatives:|610 Cap/Floor 620 Swap 630 FRA 760 OTC options 700 Futures|


**Features**

The procedure for determining write-ups/write-downs is as follows:

- 1. The system compares the book value of the position in valuation currency with the book value or NPV and then calculates the new book value according to the rules defined for the position management procedure.


- 2. The book value in position currency is determined at the same time.
- 3. The gain or loss for the paper is determined by first calculating the write-up or write-down amount in position currency and then translating it into the valuation currency using the book exchange rate. The write-up or writedown amount for the foreign exchange component is the difference between this value and the new book value in valuation currency.
- 4. Flows are generated for the write-up or write-down amounts:


One flow for security gains/losses

One flow for foreign exchange gains/losses

The update type depends on the +/- sign of the individual amounts and on the +/- sign of the sum of both write-up or write-down amounts in valuation currency.

This valuation step can generate reset flows.

See also:

One-Step Valuation Sequence

Valuation of Capitalized Costs

###### One-Step Valuation Sequence

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > One-Step Valuation > One-Step Valuation Sequence | L7 | trm08 p.75 | loio `6c19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6c19c55368511d4be10000000a174cb4.html?locale=en-US)

On the key date of the valuation you determine the book values, acquisition values and current values in position currency and local currency.

You compare the amounts in local currency to determine which of the three values will become the new book value (in local currency). You make this decision on the basis of the write-up/write-down rules defined in the one-step valuation principle.

You calculate the security write-up or write-down in position currency.

You multiply the security write-up or write-down by the old exchange rate (book rate) to determine the security write-up or writedown amount in local currency.

You determine the write-up/write-down amount caused by changes in the exchange rate:

- a. The total write-up/write-down amount in local currency is given by subtracting the old book value in local currency from the new book value in local currency.
- b. The write-up/write-down in the foreign currency (on the basis of changes in the exchange rate) is given by subtracting the security write-up/write-down in local currency from the total security write-up/write-down in local currency.


Summary

Notation

|BV|Book value|
|---|---|
|OBV|Old book value|
|NBV|New book value|
|AV|Acquisition value|


|KDV=|Key date value|
|---|---|
|LC =|Local currency|
|PC =|Position currency|
|SP =|Security price|
|ER =|Exchange rate|
|OER =|Old exchange rate|
|NER =|New exchange rate|
|Comparison =|Selection of the new book value according to the write-up/writedown rules|


Valuation process:

Determine the BV, AV and KDV in local currency and in position currency on the key date.

Comparethe amounts in LC. This results in the following:

→NBV (LC)

→NSP

→NER

Calculate the Security write-down amount.

NBV (PC) (=NBV(LC) x NER)

- OBV (PC)

= Security write-down (PC)

Security write-down (PC) x OER = Security write-down (LC)

Calculate the total write-down amount

NBV

- OBV

= total write-down (LC)

Calculate the foreign exchange write-down amount

Total write-down (LC)

- Security write-down in LC


= Foreign currency write-down

###### Valuation of Capitalized Costs (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > One-Step Valuation > Valuation of Capitalized Costs | L7 | trm08 p.76 | loio `6f19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6f19c55368511d4be10000000a174cb4.html?locale=en-US)

If you have opted to manage the capitalized costs separately (exclusively), they are valued separately by the key date valuation function.

The capitalized costs are either written off fully or written down proportionately, depending on your Customizing settings.

**Prerequisites**

In the Customizing activity Set the Effects of the Update Types on the Position Components you define for each update type whether costs should be managed inclusively or exclusively.

For each update type for costs to be capitalized you define the position components for managing the costs. The following position change categories are available:

- 1014 Post Costs to Cost Component [=> the costs are managed separately (exclusive)]

- 1015 Post Costs to Purchase Value Component [=> the costs are included]


You define for each security valuation procedure whether the capitalized costs for a position are written off in full or written down proportionately in Customizing under Transaction Manager General Settings Accounting Parallel Valuation Areas Settings for Position Management Valuation Define Security Valuation Procedure .

**Features**

Proportionate write-up/write-down of capitalized costs

If the costs are written up or down proportionately, the book value of the capitalized costs is adjusted in such a way that the ratio 'new book value to acquisition value' is the same for the costs and for the security.

- 1. a. New book value of the costs in PC = (new book value of the security in PC / acquisition value of the security in PC)

* acquisition value of the costs in PC

- 2. b. Valuation amount of the costs in PC = new book value of the costs in PC - old book value of the costs in PC
- 3. c. Security valuation amount for the costs in VC = valuation amount of the costs in PC * old book exchange rate.
- 4. d. New book value of the costs in VC = (new book value of the security in VC / acquisition value of the security in VC)

* costs in VC

- 5. e. Total valuation amount of the costs in VC = new book value of the costs in VC - old book value of the costs in VC
- 6. f. Forex valuation amount for the costs in VC = total valuation amount of the costs in VC - security valuation amount of the costs in VC


Notation:

PC = Position currency

VC = Valuation currency (usually the local currency)

Full write-off of capitalized costs

The new book value of the costs is set to 0 both in the position currency and in the valuation currency. The difference to the book value of the costs is the write-up/write-down amount.

###### Two-Step Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Two-Step Valuation | L6 | trm08 p.77 | loio `7219c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7219c55368511d4be10000000a174cb4.html?locale=en-US)

The following steps are available for carrying out a two-step valuation which determines the write-up / write-down amounts separately for price/rate and exchange rate.

Security Valuation

Foreign Currency Valuation

You define the sequence of the valuation steps in the position management procedure .

**Example:**

Valuation of a USD bond

This example shows how the sequence of valuation steps can affect the write-up / write-down amounts in the security and in the foreign currency.

The same bond is valuated first in the security and then in the foreign currency (position management procedure 1) and first in the foreign currency and then in the security (position management procedure 2).

|Transaction basic data (= purchase of USD bond)|Position value date: 01/01|
|---|---|
| |Nominal amount: 1,000,000 USD|
| |Price: 110%|
| |Exchange rate: 2.00 EUR/USD|
|Prices/rates on key date of valuation (02/01)|Price: 100 %|
| |Exchange rate: 1.50 EUR/USD|
|Position management procedure 1|1. Security valuation 2. Foreign currency valuation Strict lowest value principle|
|Position management procedure 2|1. Foreign currency valuation 2. Security valuation Strict lowest value principle|


[figure TRM08-F018]

|Valuation results:| |
|---|---|
|A)Position management procedure 1| |
|Security write-down amount in USD|100,000 USD|
|Write-down amounts in EUR:| |
|Security write-down|200,000 EUR|
|Foreign currency write-down|500,000 EUR|
|Total write-down amount in EUR:|700,000 EUR|
|B) Position management procedure 2| |
|Security write-down amount in USD|100,000 USD|
|Write-down amounts in EUR:| |
|Security write-down|150,000 EUR|
|Foreign currency write-down|550,000 EUR|
|Total write-down amount in EUR:|700,000 EUR|

###### Security Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Two-Step Valuation > Security Valuation | L7 | trm08 p.79 | loio `7519c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7519c55368511d4be10000000a174cb4.html?locale=en-US)

The security valuation determines gains and losses as a result of price changes.

**Integration**

Valuation of the paper is supported for the following product categories:

|Loans:|300 Mortgage 310 Borrower’s note loan 320 Policy loan 330 General loan|
|---|---|
|Securities:|010 Stock 020 Investment Fund 030 Subscription Right 040 Bond 041 Bond with Redemption Schedule 060 Warrant Bond 070 Convertible Bond 111 Index Warrant 112 Equity Warrant 113 Currency Warrant 114 Bond Warrant 160 Shareholding |
|Money market transactions:|510 Fixed-Term Deposit 520 Deposit at Notice 530 Commercial Paper 540 Cash Flow Transactions 550 Interest Rate Instrument|
|Foreign exchange:|600 FX Transaction|
|Derivatives:|610 Cap and Floor 620 Swap 630 Forward Rate Agreement 740 Forward Securities Transaction 760 OTC Options|


**Features**

Calculating the write-up / write-down amount in the security in valuation currency:

- 1. Determine the book value, the purchase value, and the market value or net present value of the position on the valuation key date.
- 2. Compare the values and select the new book value in position currency based on the write-up / write-down rules defined in the position management procedure.
- 3. The write-up / write-down amount is first calculated in position currency:


New book value of the position in position currency - Old book value of the position in position currency = Write-up / write-down amount in position currency

Conversion of the write-up / write-down amount with the book exchange rate in valuation currency.

Whereby:

Market values and NPVs

For money market transactions, FX transactions, and derivatives, the fair value is a present value that has been either calculated in market risk management or entered manually in the NPV table.

If the prices or present values are not available in the required currency, they are translated using the most recent market exchange rates available.

Book exchange rate

Depending on whether foreign currency valuation was already performed for the position, the book exchange rate used is either the old book exchange rate (the last valuation) or the new book exchange rate resulting from the preceding foreign currency valuation.

See also: Two-Step Valuation

If the NPV/Price Including Price Index indicator is selected in the security valuation procedure, the NPV/price includes the price index, in contrast to the index-clean NPV/price.

The following formulas are then used in the security valuation if the book value is used as the valuation base:

Write-up index-clean = NPV / Market index factor - Book value index-clean

Write-up in position currency = Write-up index-clean * Book index factor

Book index factor = Book value / Book value index-clean

The following formulas are then used in the security valuation if the nominal (repayment) value is used as the valuation base:

Write-up in position currency = NPV - Book value

Write-up index-clean = 0 (isn't calculated)

If the book value is used as the valuation base, the NPV is divided by market price index factor. Therefore, price index valuation needs to be performed before security valuation so that the book index factor equals the current market price index factor in the security valuation step. If security valuation is performed before price index valuation, the total book value after valuation is the same as when the index-clean NPV/price is applied. However, the security valuation write-up differs for the NPV or security price with and without price index.

If one of the two book values is 0, or the book values have opposing +/- signs, the book exchange rate is set to 1. For forward bonds, the book exchange rate is set to the opening bond spot price for the contract.

A flow is generated for the write-up or write-down amount.

If the +/- sign has changed compared to the totals of previous flows, a clearing flow is generated if the Clear Gains/Losses indicator is set in the definition of the security valuation procedure.

If, for example, the valuation results in the position being written down and write-up flows already exist, the system generates one flow to clear the write-ups and one flow for the remaining write-down amount. The same applies if the valuation results in a write-up offsetting previous write-downs.

This valuation step can generate reset flows.

###### Foreign Currency Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Two-Step Valuation > Foreign Currency Valuation | L7 | trm08 p.82 | loio `7b19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b19c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

This step determines the gains and losses resulting from changes in the exchange rate.

**Integration**

The exchange rate valuation is supported for the following product categories:

|Loans:|300 Mortgage 310 Borrower’s note loan 320 Policy loan 330 General loan|
|---|---|
|Securities:|010 Stock 020 Investment certificate 030 Subscription right 040 Bond 041 Bond with redemption schedule 060 Warrant bond 070 Convertible bond 111 Index warrant 112 Equity warrant 113 Currency warrant 114 Bond warrant 160 Shareholding|
|Money market transactions:|510 Fixed-term deposit 520 Deposit at notice 530 Commercial paper 540 Cash flow transactions 550 Interest rate instrument|
|Foreign exchange:|600 Foreign exchange|
|Derivatives:|610 Cap/Floor 620 Swap|


630 FRA

740 Forward bonds

760 OTC options

700 Futures (only the variation margin can be valuated)

**Features**

The foreign currency valuation can base on the following components for valuation:

Book Value

Determining the write-up/write-down amount due to rate changes in a foreign currency. The write-up / write-down amount is reported in local/valuation currency.

The purchase value (= acquisition value) and the book value of the position are determined in position and valuation currency.

The new book exchange rate is determined by comparing the following exchange rates in accordance with the rules defined in the position management procedure.

Current market FX rate

Old book FX rate

Acquisition FX rate

The foreign currency write-up/write-down amount in valuation currency is determined as follows:

(Book value of the position in position currency x New book exchange rate) - (Book value of the position in position currency x Old book exchange rate) = Foreign exchange write-up/write-down amount in valuation currency

This valuation step can only supply a foreign currency write-up or write-down amount in valuation currency.

Whereby:

Book value of the position in position currency

This is either the new book value of the position in position currency or the old book value of the position in position currency depending on whether or not a security valuation has already been carried out.

See also: Two-Step Valuation

Acquisition exchange rate

If one of the two acquisition values is 0, the acquisition exchange rate is set to 1.

Book exchange rate

If one of the two book values is 0, or the book values have opposing +/- signs, the book exchange rate is set to 1.

Flows are generated with the write-up or write-down amounts.

If the +/- sign has changed compared to the totals of previous flows, a clearing flow is generated if the Clear Gains/Losses indicator is set in the definition of the foreign currency valuation procedure. If the result of the valuation is that the position has to be written down, for example, and write-up flows already exist, the system would generate one flow to clear the write-ups, and one flow for the remaining write-down amount. The same applies if a write-up offsets previous write-downs. The flows always have 0 as the amount in position currency.

Variation Margin

If you are using the central counterparty clearing for clearing-relevant FX transactions, you can set up a foreign currency valuation step of the variation margin (managed on position component 1002 of the clearing account position) for foreign exchange transactions.

The additional valuation step is executed for a foreign exchange transaction if the position currency of the variation margin differs from the valuation currency.

Settings in Customizing:

Set Effects of Update Types on Position Components

In this Customizing activity, you must assign the position change categories 1012 Post Variation Margin and 1013 Clear Variation Margin to the update types used for transaction related positive and negative variation margin flows.

**Example:**

|Update Type|Valuation Area|Company Code|Position Change Category|
|---|---|---|---|
|EA_MTM+ CCC: Positive Variation Margin|001|0001|1012 Post Variation Margin|
|EA_MTM- CCC: Negative Variation Margin|001|0001|1013 Clear Variation Margin|


Define Foreign Currency Valuation Procedure

In this Customizing activity, you must create a foreign currency valuation procedure for the variation margin.

[figure TRM08-F019 - In this Customizing activity, you must create a foreign currency valuation procedure for the variation margin.]

- 1. Choose New Entries.
- 2. Enter an ID and a name for the new procedure.
- 3. Choose the Price/Rate Type.
- 4. Choose Variation Margin in the Comp. for Valuation field.
- 5. Choose the Write-Up Rule and the Write-Down Rule.
- 6. Save your entries.


Define Position Management Procedure

In this Customizing activity, you assign the new foreign exchange valuation procedure to the position management procedure of the relevant FX transactions.

Define Update Types and Assign Usages

In this Customizing activity, you must define new update types for the valuation flows for the new foreign exchange valuation procedure:

- V210 Variation Margin Forex Write-Up

- V211 Variation Margin Forex Write-Down


Assign the new update types to the usage Key Date Valuation.

The new update types are relevant for posting and you must define account determination for them.

Assign Update Types for Valuation

In this Customizing activity, you assign the new update types on the Foreign Crcy Valuation tab for each affected position management procedure.

[figure TRM08-F020 - In this Customizing activity, you assign the new update types on the Foreign Crcy Valuation tab for each affected position management procedure.]

Amortized Acquisition Value

Amortized Acquisition Value; only at Valuation

Hedge Adjustment

Loss/Offset Loss Allowance

Write-Off

Acquisition Value

Amortization Adjustment Loss Allowance

Acquisition Value; Only at Valuation

This valuation step can generate reset flows.

**Costs**

For more information, see also Valuation of Capitalized Costs.

Flows are generated with the write-up or write-down amounts.

If the +/- sign has changed compared to the totals of previous flows, a clearing flow is generated if the Clear Gains/Losses indicator is set in the definition of the foreign currency valuation procedure in Customizing under Transaction Manager

General Settings Accounting Parallel Valuation Areas Settings for Position Management Key Date Valuation Define

Foreign Currency Valuation Procedure . If the result of the valuation is that the position has to be written down, for example, and write-up flows already exist, the system would generate one flow to clear the write-ups, and one flow for the remaining write-down amount. The same applies if a write-up offsets former write-downs. The flows always have 0 as the amount in position currency.

This valuation step can generate reset flows.

###### Valuation of Capitalized Costs (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Two-Step Valuation > Valuation of Capitalized Costs | L7 | trm08 p.86 | loio `7550e5b5fa4f4be5897c29df4eadb1bb` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7550e5b5fa4f4be5897c29df4eadb1bb.html?locale=en-US)

**Use**

If you have opted to manage the capitalized costs separately (exclusively), they are valued separately by the key date valuation function.

The capitalized costs are either written off fully or written down proportionately, depending on your Customizing settings.

**Prerequisites**

In the Customizing activity Set the Effects of the Update Types on the Position Components you define for each update type whether costs should be managed inclusively or exclusively.

For each update type for costs to be capitalized you define the position components for managing the costs. The following position change categories are available:

- 1014 Post Costs to Cost Component [=> the costs are managed separately (exclusive)]

- 1015 Post Costs to Purchase Value Component [=> the costs are included]


You define for each security valuation procedure whether the capitalized costs for a position are written off in full or written down proportionately in Customizing under Transaction Manager General Settings Accounting Parallel Valuation Areas Settings for Position Management Valuation Define Security Valuation Procedure .

**Features**

Proportionate write-up/write-down of capitalized costs

If the costs are written up or down proportionately, the book value of the capitalized costs is adjusted in such a way that the ratio 'new book value to acquisition value' is the same for the costs and for the security.

- 1. a. New book value of the costs in PC = (new book value of the security in PC / acquisition value of the security in PC)

* acquisition value of the costs in PC

- 2. b. Valuation amount of the costs in PC = new book value of the costs in PC - old book value of the costs in PC
- 3. c. Security valuation amount for the costs in VC = valuation amount of the costs in PC * old book exchange rate.
- 4. d. New book value of the costs in VC = (new book value of the security in VC / acquisition value of the security in VC)


* costs in VC

- 5. e. Total valuation amount of the costs in VC = new book value of the costs in VC - old book value of the costs in VC
- 6. f. Forex valuation amount for the costs in VC = total valuation amount of the costs in VC - security valuation amount of the costs in VC


Notation:

PC = Position currency

VC = Valuation currency (usually the local currency)

Full write-off of capitalized costs

The new book value of the costs is set to 0 both in the position currency and in the valuation currency. The difference to the book value of the costs is the write-up/write-down amount.

###### Special Security Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Special Security Valuation | L6 | trm08 p.87 | loio `7819c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7819c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

In the special security valuation a distinction is made between the following types:

Special write-up/write-down - mandatory

Special write-up/write-down - exercised right

**Integration**

The special securities valuation is a special form of security valuation which is carried out as part of the key date valuation if certain requirements are met (see below).

The special security valuation can only be carried out as part of the valuation for securities.

See also:

Security Valuation

**Prerequisites**

Set the Allow Special Write Up/Downs for Securities indicator in Customizing under Transaction Manager -> General Settings -> Accounting -> Parallel Valuation Areas -> Settings for Position Management ->Key Date Valuation -> Define Securities Valuation Procedure.

Define update types for the special security valuation depending on the type of special valuation on the Special Valuation tab page. The update types are defined for position management procedures to which a security valuation procedure (that enables special write ups/downs) was assigned. You can find this tab page in Customizing under Transaction Manager -> General Settings -> Accounting -> Parallel Valuation Areas -> Key Date Valuation -> Update Types -> Assign Update Types for Valuation.

**Note:**

Define the update types under Transaction Manager -> General Settings -> Accounting -> Parallel Valuation Areas -> Key Date Valuation -> Update Types -> Define Update Types and assign the update types to the usage Key Date Valuation under Assign Update Type to Usages .

Since update types are relevant for posting, you must also enter posting information for the update types under Transaction Manager General Settings Accounting Parallel Valuation Areas Link to Other Accounting Components Define Account Determination.

You can enter prices for the special valuation in a separate table in the application menu under Transaction Manager Securities Accounting Valuation Price Maintenance for Special Security Valuation(transactionTPM73) .

Features

[figure TRM08-F021 - Features]

[figure TRM08-F022]

###### Enter Prices/Net Present Values for Special Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Special Security Valuation > Enter Prices/Net Present Values for Special Valuation | L7 | trm08 p.89 | loio `cc0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cc0ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

Enter a special price (for securities) here which can differ from the current market price or the net present value (for loans).

**Integration**

The values in this table are needed in order to carry out a special valuation or for recording impairments.

**Features**

The price / impairment price or net present value / impairment value is defined per position depending on the position differentiations.

Company code

Valuation area

Valuation class

Securities:

ID number

Securities account, securities account group or portfolio

Loan

Contract number

****Caution:****

For single position management

**Activities**

- 1. Enter the valuation key date for which you want to specify the prices/net present values.
- 2. Choose Execute.

###### Impairments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments | L6 | trm08 p.90 | loio `e911c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e911c753b1081d4be10000000a174cb4.html?locale=en-US)

**Purpose**

With this function you can record impairments such as required by US GAAP (SFAS 142) und IAS 39 – Financial Instruments: Recognition and Measurement for security and loan positions.

**Implementation Considerations**

Customizing for Impairments

**Integration**

The following position components are used to manage an impairment:

The original position component Impairment(1201)

The original position component Foreign Currency Impairment(1202)

The derived Position ComponentAmortized Acquisition Value contains the original position components Impairment and Foreign Currency Impairment.

The original position component FX Valuation of Amortized Acquisition Value (1011).

This original position component is included in the derived position component book value.

To record impairments, you need to make settings in Customizing.

See also:Customizing for Impairments

Once an impairment has been recorded, it needs to be taken into account in position management.

See also:Position Management for Existing Impairment .

You require the following authorizations to execute this function:

|Authorization Object|Activities|
|---|---|
|T_DEAL_PD (Product/transaction type authorization)|Activity 16 (execute) and 85 (reverse)|
|T_DEAL_PF (Portfolio authorization)|Activity 16 (execute) and 85 (reverse)|
|T_DEAL_DP (Securities account authorization)|Activity 16 (execute) and 85 (reverse)|
|T_DEAL_AG (Authorization group for customer-specific authorization checks)|Activity 16 (execute) and 85 (reverse)|


**Features**

You can record an impairment either with or without the reset function.

The following steps are carried out when you record impairments:

- 1. Amortization

If the amortization step was defined in the position management procedure for the relevant position, an amortization takes place on the impairment recording key date.

The flows for this are generated with the update types that are also used as part of a “normal” valuation.

- 2. Reset of all valuations that do not affect net income in the security

If write ups/downs not affecting net income were carried out for the position in the past (either by a key date valuation or transfer postings), these are reset.

Both amounts are taken in the position and valuation currency of the equity capital item in the security and used to generate a flow.

Two flows are generated if the amounts have different signs.

When this step has been carried out, the position has an equity capital item in the security (not affecting net income) to the amount of zero in both position and valuation currency.

If there are no write ups/downs in the security (not affecting net income) – which is the case for example for a position in the Held to Maturity category – this step is not carried out.

- 3. Reset all foreign currency valuations, without affecting profit or loss (optional)

If you want to use this reset procedure, you need to set the Reset FX Valuation indicator in the corresponding impairment procedure. You do this in Customizing by choosing Transaction Manager General Settings

Accounting Settings for Position Management Key Date Valuation Define Impairment Procedure .

If FX write ups/downs not affecting net income were carried out for the position in the past (either by a key date valuation or transfer postings), these are reset.

If there are no write ups/write downs in foreign currency (not affecting net income), this step is not carried out.

- 4. Write-down in security affecting net income

A write-down in the security affecting net income is then performed. This is calculated in position currency, taking the defined impairment price or value into account, and then converted to valuation currency on the basis of the market exchange rate or with the book exchange rate. A flow is generated from these write-down amounts, which is posted affecting net income. This special write-down is shown in the impairment position component in the financial subledger.

- 5. You can determine whether to record a foreign currency impairment.

When posting impairment, you can choose to reset the foreign exchange results recorded during the OCI valuation (equity capital.)

- 6. Foreign exchange valuation of the amortized acquisition value


This step is executed if you have assigned the steps Amortization and Foreign Currency Valuation (component to be valuated = Amortized Acquisition Value ) in the position management procedure of the relevant position.

**Note:**

The order in which the steps Security Write-Down Affecting Net Income and the FX Valuation of the Amortized Acquisition Value are executed, depends on the sequence specified for them in the position management procedure.

The update types used to generate the flows must be defined on the Impairment tab page in Customizing under Transaction Manager General Settings Accounting Key Date Valuation Update Types Assign Update Types for Valuation.

Other

Any costs managed separately or any existing valuations of costs for a position are not affected by the recording of an impairment.

The book value of a position is always displayed in both position and valuation currency. These two amounts together implicitly add up to the book exchange rate. This implied book exchange rate could change if you reset the valuations in the security not affecting net income, or write-down the security affecting net income.

An impairment for bonds often means adjusting future planned records for interest payments or repayments. For this you must manually change the conditions in the class. Note that such adjustments affect all positions of this class, which means all securities accounts and all valuation areas. Effects of such adjustments can only occur in the following cases.

Effects on the amortization as part of impairment recording. Such effects are generally not desired. When adjusting you should therefore make sure that the calculated LAC or SAC values are not affected.

The adjustments do not affect the write-down affecting net income as part of recording the impairment because the write-down was carried out as a result of a specially defined impairment rate. The same applies to the subsequent key date valuations.

An impairment for loans, in the same way as for bonds, often means adjusting future planned records for interest payments or repayments. This must also be displayed manually using changed or new conditions. Note that such adjustments affect all valuation areas. The effects of such adjustments can occur in the following cases:

Effects on the amortization as part of impairment recording. Such effects are generally not desired. When adjusting you should make sure that the calculated LAC or SAC values are not affected.

The net present value calculated by the system for a loan may be affected by the adjustments. If this net present value is used as an impairment value, this may affect the write-down affecting net income as part of impairment recording. Such effects are generally desired.

If the net present value calculated by the system for the loan as part of the key date valuation is used, subsequent key date valuations may also be affected for the reasons mentioned above (affecting the net present value). Such effects are generally desired.

Impairments that have already been recorded can be cleared again if the reason for recording them is no longer valid.

Record or Clear Impairment [transaction TPM70]

Reverse Impairment [transaction TPM71]

Enter Prices/Net Present Values for Special Valuation [transaction TPM73]

Reference Report for Impairment [transaction TPM75]

Position Management for Existing Impairment

**Constraints**

Impairments can only be recorded and managed for the product groups securities and loans .

###### Impairment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments > Impairment | L7 | trm08 p.92 | loio `ca0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ca0dda531198434de10000000a174cb4.html?locale=en-US)

Definition

An impairment is an extraordinary write-down in accordance with US GAAP and IAS accounting standards. Impairments must be recorded if a permanent reduction in the value of a position is foreseeable.

###### Position Management for Existing Impairment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments > Position Management for Existing Impairment | L7 | trm08 p.93 | loio `b90eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b90eda531198434de10000000a174cb4.html?locale=en-US)

If an impairment was recorded for a position, this has an effect on how the position is managed and the impairment must be taken into account in further position management.

Recorded impairments must be taken into account in the following business transactions. They do not affect any other business transactions.

Ratings

A position with an existing impairment is valuated in accordance with the settings in the relevant position management procedure but is not amortized. If this valuation step is defined in the position management procedure, it is suppressed when the valuation is performed and a corresponding message is generated in the valuation log.

A valuation is reset in the same way for a position with an existing impairment as for one without an impairment.

This means that write-ups are possible for the security during a future valuation of the position and that balances can be generated for the security equity item that does not affect net income.

Business transactions that result in position inflows and outflows

The following business transactions are grouped together as position outflows:

Repayment to be received

Repayment to pay

Unscheduled repayment

Sale

Nominal adjustment

Securities account outflow

In the case of position outflows, an existing impairment is cleared from the position either nominally or in proportional units.

An amortization as part of the generation of derived business transactions is suppressed if there is an existing impairment.

These business transactions are grouped together as position inflows:

- Payments (assets)

- Payments (liabilities)

- Purchase

- Nominal adjustment

- Securities account inflow


Existing impairments are not affected by position inflows. Amortization as a result of the incremental procedure is suppressed if an impairment exists.

Transfer postings

The following business transactions are grouped together as transfer postings:

Securities account transfer

Valuation class transfer

Capital transfer

In the case of transfer postings, an existing impairment is transferred to the target position either nominally or in proportional units, independent of the transfer posting category of the position management procedure of the target position. Therefore it is not possible to clear an existing impairment as part of a transfer posting. The rules of the transfer category defined for the target position apply to all other components.

If an impairment exists for a source position (target position), any amortizations that are due to be carried out are suppressed for the source position (target position). If no impairment exists for a source position (target position), any amortizations that are due to be carried out are carried out for the source position (target position).

This means that impairments may also occur for a position of the Trading category as a result of transfer postings.

Corporate actions

The following applies to the effects of corporate actions on positions with an existing impairment:

If the amortized acquisition value of a position without impairment is changed by corporate action, the amortized acquisition value including impairment must be adjusted in the same way.

The following corporate actions are supported by the system.

- Stock split

- Capital increase from retained earnings

Stock splits and capital increases from retained earnings are comparable inflows and have no effect on existing impairments.

- Capital reductions

Capital reductions do not affect existing impairments.

- Stock swap

- Transfer of new stock to old

Stock swaps and transfers of new stock to old are comparable to transfer postings. An existing impairment is transferred in proportional units from the stock position (outflowing stock or new stock to be exchanged) to the target position (inflowing stock or old stock to be exchanged). If an impairment exists for a source position (target position), any amortizations that are due to be carried out are suppressed for the source position (target position). If no impairment exists for a source position (target position), any amortizations that are due to be carried out are carried out for the source position (target position).

- Issue Currency Changeover

If the issue currency is converted, an existing impairment is converted in the same way as the other position components.

- Posting Subscription Rights

When subscription rights are posted, any impairment existing for the stock is transferred to the subscription right in the same way as for the other components.

- Other Corporate Action


The procedure is the same for other corporate actions if an impairment exists as it would be for the amortized acquisition value without impairment.

Rights

The following applies to the effects of exercising rights on positions with an existing impairment:

If exercising rights change the amortized acquisition value of a position without impairment, the amortized acquisition value including impairment must be adjusted in the same way.

The following rights are supported by the system.

- Exercise of warrant on stock (physical delivery)

- Exercise of warrant on interest (physical delivery)

- Exercise of subscription right

- Exercise of convertible bond

- Stock swap

Exercising these rights is comparable to a transfer posting. An existing impairment is transferred from the source position to the target position. If an impairment exists for a convertible bond, any amortizations that are due to be carried out are suppressed when the right is exercised.

- Exercise of warrant on stock (cash settlement)

- Exercise of warrant on interest (cash settlement)

- Exercise of warrant on index (cash settlement)

- Exercise of warrant on currency (cash settlement)

Exercising a warrant with cash settlement is dealt with in the same way as an outflow. If an impairment exists it will be cleared.

- Exercise of puttable bond

- Exercise of callable bond

Exercising a puttable or callable bond is comparable to an outflow (the bond is returned to the issuer, the rights are in the hands of the issuer (puttable) or the owner (callable)). If an impairment exists, it will be cleared. If an impairment exists, any amortization due to be carried out is suppressed.

- Detachment of warrant bond


The detachment of a warrant bond can be seen as a transfer posting with a source position (cum warrants) and two target positions (ex warrant). If an impairment exists for the warrant bond, it is transferred completely to the exwarrant. This means that the warrant bond does not carry any impairment after detachment. This procedure is similar to that for the amortization component, which is also completely transferred to the ex-warrant. All other components are distributed across the two target positions according to the relationship of the market value of the ex-warrant/market value of the cum warrant at the time of detachment. If an impairment exists for the warrant bond, any amortization due to be carried out is suppressed.

Impairment Reporting

The Transaction Manager information system is based on SAP Query. You can evaluate existing impairments in the position management reports delivered for the Transaction Manager. This is achieved using the new position component for impairments that have been carried out, which is available in position trend lists as the start, delta, and end value. The value of these components flows into the position component amortized acquisition value, which is also available in position trend lists as the start, delta, and end value.

###### Customizing Impairments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments > Customizing Impairments | L7 | trm08 p.96 | loio `7b0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b0dda531198434de10000000a174cb4.html?locale=en-US)

|IMG Activity|Settings| |
|---|---|---|
|Define Impairment Procedure (Under Transaction ManagerGeneral SettingsAccounting → Settings for Position Management → Key Date Valuation )|Creating one or more impairment procedures You can set the following indicators: -Reset Forex Valuation - Record Foreign Currency Impairment - Amortization After Impairment See also: Documentation on the IMG activity| |
|Define Position Management Procedure (Under Transaction ManagerGeneral SettingsAccounting → Settings for Position Management )|To be able to record impairments for a position the required impairment procedure must be assigned in the impairment area of the corresponding position management procedure.| |
|Define Update Types and Assign Usages (Under Transaction ManagerGeneral SettingsAccounting → Key Date Valuations → Update Types or under Transaction ManagerGeneral SettingsAccountingDerived Business TransactionsUpdate Types )|Define the required update types and assign them to usages:| |
| |Examples:| |
| |Update Type|Use|
| |V240 – Clear Impairment (Security)|9002 Key date valuation|
| |V241 – Record Impairment (Security)| |
| |V244 – Impairment (Security) – Clear positive OCI items| |
| |V245 – Impairment (Security) – Clear negative OCI items| |
| |VR240 – Clear Impairment (Security)| |
| |VR241 – Record Impairment (Security)| |
| |VR244 – Impairment (Security) – Clear positive OCI items| |
| |VR245 – Impairment (Security) – Clear negative OCI items| |
| |DBT_D027 – Clear impairment (negative)|9001 Derived business transactions|
| |DBT_D028 – Post impairment (negative)| |
| |DBT_E016 – Impairment (security) translation| |
| |DBT_F015 – Reconciliation: Pos. difference impairment (security)| |
| |DBT_F016 – Reconciliation: Neg. difference impairment (security)| |


|IMG Activity|Settings| |
|---|---|---|
| |DBT_G027 – Currency swap: Clear impairment (security)| |
| |DBT_G028 – Currency swap: Post impairment (security)| |
| |...| |
| |INI_041 – Initialization: Post impairment (security)|9000 Position initialization|
| |....| |
|Assign Update Types for Key Date Valuation (Under Transaction ManagerGeneral SettingsAccounting → Key Date Valuation → Update Types )|In this IMG activity you assign update types for the key date valuation depending on the position management procedure. You must carry out the assignment of update types for all position management procedures to which you have assigned an impairment procedure. Assign the update types for the following flows in the Special Valuation due to Impairment area on the Impairment tab page: -{}--{}-- ClearImpairment - Record Impairment - Clear Security Write-Up - Clear Security Write-Down - ClearForeign CurrencyImpairment - Record Foreign Currency Impairment - Clear Forex Write-Up - Clear Forex Write-Down In the Reset Special Valuation due to Impairment area, you assign the update types to reset the above flows.| |
|Assign Update Types for Derived Business Transactions (Under Transaction ManagerGeneral SettingsAccountingDerived Business TransactionsUpdate Types )|In this IMG activity you assign update types for the derived business transactions depending on the position management procedure. This means that you must carry out the assignment of update types for all position management procedures to which you have assigned an impairment procedure. You need to enter update types for impairments on the following tab pages: - Transfer -{}- - Pos. Outflows - Reconciliation flows - Currency swap - Intragroup (if you are using the Intragroup Trading function) | |
|Assign Update Types for Initializing Positions (Under Transaction ManagerGeneral SettingsAccountingInitialize PositionsUpdate Types )|In this IMG activity you assign the update types for all product types in the securities and loans areas for initializing positions in the impairment position component.| |


|IMG Activity|Settings| |
|---|---|---|
|Indicate Update Types as Relevant to Posting (Under Transaction ManagerGeneral SettingsAccountingLink to Other Accounting Components )|Indicate the update types that are relevant for posting.| |
| Create any new posting specifications that you have not yet used.|Enter the posting specifications here for the update types relevant for posting:| |
| |Examples:| |
| |Update Type|Posting Specifications|
| |V240 – Clear Impairment (Security)|Position to impairment|
| |V241 – Record Impairment (Security)|Impairment to position|
| |V244 – Impairment (Security) – Clear positive OCI|Unrealized price gains, security to position|
| |V245 – Impairment (Security) – Clear negative OCI|Position to unrealized price losses|
| |DBT_D027 – Clear impairment (negative)|Position to position clearing|
| |DBT_D028 – Post impairment (negative)|Position clearing to position|
| |DBT_G027 – Currency swap: Clear impairment (security)|Position to balance sheet clearing|
| |DBT_G028 – Currency swap: Post impairment (security)|Opening account, parallel VA to position|
| |.....|....|



See also:

Documentation of the IMG activities

###### Initialization of Impairments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments > Initialization of Impairments | L7 | trm08 p.98 | loio `9e0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9e0dda531198434de10000000a174cb4.html?locale=en-US)

As part of the normal initialization process you can transfer historical impairment values for an additional valuation area. To achieve this you must change the initial values proposed by the system for the individual position components.

An historical impairment must be set to the new component impairment for each position.

With the business transaction position initialization, generated in a further step, the impairment is automatically associated with its corresponding position in the financial subledger.

See also:

Initialization of Parallel Position Management

###### Record or Clear Impairment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments > Record or Clear Impairment | L7 | trm08 p.98 | loio `710eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/710eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

An impairment is recorded on the level of the security or loan position .

An impairment is recorded when a permanent decrease in value becomes known.

An impairment can be carried out at the end of the month, quarter or year as well as on other days.

**Integration**

An impairment does not include the normal valuation steps.

If an impairment is recorded for a certain point in time when a scheduled valuation is also carried out (for example at the end of the quarter) two functions must be triggered separately:

- 1. Record impairments
- 2. Execute key date valuation


**Prerequisites**

Customizing for Impairments

You can manually enter impairment rates or values using the function in Transaction Manager Securities Accounting Valuation Impairment Enter Prices/Net Present Values for Special Valuation (transaction TPM73).


Define the impairment prices (securities) or impairment values (loans) for the positions you want to record impairments for.

**Features**

Selection

Product Groups

Securities

**Loans**

By choosing one or more product groups, you can select the positions for these groups.

In addition to selecting the product groups, you can use the general selections to select the individual positions.

General Selections

You can use the following general selection criteria when selecting positions:

Company code

Choose the appropriate company code. The default company code is 0001. You can overwrite this if necessary.

Valuation area

You can restrict the selection of positions to one valuation area.

Since the product type and valuation class are valid as position criteria (differentiation terms) for all product types, you can use these to select positions.

Product type

Valuation class

You can restrict the selection further using the following product group-dependent position criteria (differentiation terms):

**Note:**

Here only the product groups selected in the Product Groups area are displayed.

Securities

ID number

Securities account

Securities account group

Portfolio

**Loans**

Contract number

Valuation parameters

Key date for impairment

Posting control

|Posting Date|Alternative FI posting date  The FI posting date should only differ from the posting date in the financial subledger in exceptional cases|
|---|---|
|Posting period|Alternative FI posting period|
|Document date|The document date shows the date on which the original document was issued|
|Test Run indicator|If you run the report in test mode first you can avoid making incorrect postings. If the indicator is not set the report is run in update mode.|


Output Control

|Display Positions indicator|If you set this indicator, a list of all positions relevant to your selection input is displayed after the report has been run. You can then return to the selection screen with the back arrow if you want to change your selection criteria or, check the positions and execute the function with .  |
|---|---|
|Layout|If you have defined a display variant you can select it here.|


|No Zero Positions indicator|If you set this indicator, the selected zero positions are not displayed.|
|---|---|


Output

A log is generated. Additionally, you can

Branch to the Valuation messages

Display all flows


Display logs and messages .



The output is displayed using the SAP List Viewer .

**Activities**

- 1. Choose Transaction Manager Securities Accounting Valuation Impairment Record or ClearImpairment [transaction TPM70].
- 2. Enter the selection criteria which the system uses to find positions for which impairments are to be recorded.
- 3. Choose the impairment category :
- 4. Enter the posting data and make any other settings you require.
- 5. Choose Execute .
- 6. The list of selected positions is displayed. If the positions were selected correctly, execute the function.
- 7. The following three steps are carried out for each position:

- a. Amortization (if defined in the position management procedure)
- b. Reset of all valuations that do not affect net income in the security
- c. Write-down in security affecting net income
- d. Write-down in security affecting net income
- e. Foreign currency impairment
- f. Foreign exchange valuation of the amortized acquisition value


- 8. The system displays logs and messages.
- 9. Make any necessary changes to the conditions in the class data or to the loan conditions.

###### Reverse Impairments

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments > Reverse Impairments | L7 | trm08 p.101 | loio `bd0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bd0ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can reverse recorded impairments per position with this function.

Reversing an impairment also reverses any derived business transactions (price gains/losses) created after the impairment that have already been posted.

**Prerequisites**

If key date valuations exist after the impairment you want to reverse, you must reverse these first.

**Features**

Selection

Product Groups

Securities

**Loans**

By choosing one or more product groups, you can select the positions for these groups.

In addition to selecting the product groups, you can use the general selections to select the individual positions.

General Selections

You can use the following general selection criteria when selecting positions:

Company code

Choose the appropriate company code. The default company code is 0001. You can overwrite this if necessary.

Valuation area

You can restrict the selection of positions to one valuation area.

Since the product type and valuation class are valid as position criteria (differentiation terms) for all product types, you can use these to select positions.

Product type

Valuation class

You can restrict the selection further using the following product group-dependent position criteria (differentiation terms):

**Note:**

Here only the product groups selected in the Product Groups area are displayed.

Securities

ID number

Securities account

Securities account group

Portfolio

**Loans**

Contract number

Valuation parameters

Key date for impairment

Posting control

|Reason for reversal|Enter the reason for reversal here for reversal functions|
|---|---|
|Posting Date|Alternative FI posting date  The FI posting date should only differ from the posting date in the financial subledger in exceptional cases|
|Posting Period|Alternative FI posting period|
|Document date|The document date shows the date on which the original document was issued|
|Test Run indicator|If you run the report in test mode first you can avoid making incorrect postings. If the indicator is not set the report is run in update mode.|


Output Control

|Display Positions indicator|If you set this indicator, a list of all positions relevant to your selection input is displayed after the report has been run. You can then return to the selection screen with the back arrow if you want to change your selection criteria or, check the positions and execute the function with . |
|---|---|
|Layout|If you have defined a display variant you can select it here.|
|No Zero Positions indicator|If you set this indicator, the selected zero positions are not displayed.|


Output

A log is generated.


The output is displayed using the SAP List Viewer (ALV): Classic .

**Activities**

- 1. Call the Reverse Impairment for Positions function (transaction TPM71).
- 2. Enter your selection criteria.
- 3. Choose Execute .
- 4. A list of selected positions may be displayed. If the positions were selected correctly, execute the function.
- 5. The system generates a posting log.

###### Reference Report for Impairment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Impairments > Reference Report for Impairment | L7 | trm08 p.103 | loio `130cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/130cda531198434de10000000a174cb4.html?locale=en-US)

Use

This reference report determines the securities positions that have a significant and/or prolonged slump in prices (market value) below the acquisition value. Especially for equity capital instruments, a significant and/or prolonged slump in prices is an indication that you need to record an impairment.

The reference report also makes it possible to transfer all or selected positions in the rate/price table for special security valuation.

**Restrictions**

The report is only provided for the Securities area.

The report compares the acquisition values with the market values. The book values are not compared with the market values.

**Prerequisites**

The security prices and exchange rates must be maintained with current data.

**Features**

Selection

General Selections

You can use the selection criteria to limit the positions to be analyzed and therefore also limit the report runtime.

The following evaluation parameters are available:

Selection period

Note:

Note that you must enter a period start and period end for the key date.

Key date reference

Here you can differentiate whether you want to select your positions according to position value date or according to posting date.

Maximum age market price (days)

If no security prices are defined on a key date in the market data table, these positions are displayed in a log. Since no calendar rule is defined, trading days, Sundays and holidays are not displayed.

You can enter a tolerance limit for the maximum age of the security prices. Provided that this limit is entered, the system only displays the positions with missing market prices that are above the tolerance limit on the key date.

For the market price determination, the system only displays prices that exist in the price table. There is no interpolation.

Price type (optional)

You use this field to control which security price type is used to determine the price. If this field is initial, the price type is used that is defined in the security valuation procedure of the selected position.

with exchange rate (opt.)

You use this field to control with which exchange rate market prices are translated from quotation currency to position currency. If this field is initial, the exchange rate calculation indicator is used that is defined in the company code additional data.

The exchange rate type is always taken from the foreign exchange valuation procedure for the translation of market prices from position currency to valuation currency.

Mean market values in position currency are not translated into valuation currency.

Selection criteria

The selection criteria enable you to analyze your positions for permanent impairment because of a significant and/or prolonged price loss. According to IAS 39, a significant and/or prolonged slump in prices is a sign of a permanent impairment for equity capital instruments. You can perform various analyses here: for a period or a date.

The system checks on each date how the market value is reacting in comparison to the respective acquisition value of the position. If a market value is not available on one day - provided that no tolerance limit has been entered in the selection screen or the date is outside the tolerance limit - information is displayed in the log. The report only works with the days that actually exist in the market price table. There is no interpolation or an assumption of a market value equal to zero.

Price loss is expressed as the relationship between market values and acquisition value.

Key Date Comparison:

This selection criteria checks how the market value in position currency on the key date reacts in relation to the acquisition value in position currency on the key date. If the market value is in a quotation currency that is not equal to the position currency, the system uses the rate type M (standard translation at average rate) for currency translation. This is only the case if this parameter is not overwritten by entries on the selection screen.

Key date comparison of market values:

This selection criteria checks whether the average market value is below one of the limits you defined in relation to the acquisition value in position currency on the key date. If the market value is in a quotation currency that is not equal to the position currency, the system uses the rate type M (standard translation at average rate) for currency translation. This is only the case if this parameter is not overwritten by entries on the selection screen.

Period comparison

This selection criteria checks whether the market value in position currency is below one of the limits you defined in relation to the acquisition value in position currency not only on the key date but permanently during the whole period. Only days are compared for which market values exist. Days for which no market values exist are not interpolated nor given the value zero. If the market value is in a quotation currency that is not equal to the position currency, the system uses the rate type M (standard translation at average rate) for currency translation. This is only the case if this parameter is not overwritten by entries on the selection screen.

Output

In addition to the standard functions in the reporting area, there is also the function for transfer for impairment. This function helps you to save the selected positions in the table for special security valuation (transaction TPM73).

If no security prices are defined on a key date in the market data table, these positions are displayed in a log. Since no calendar rule is defined, trading days, Sundays and holidays are not displayed. On the selection screen, you can enter a tolerance limit for the maximum age of the security prices. Provided that this limit is entered, the system only displays the positions with missing market prices that are above the tolerance limit on the key date.

###### Rate Valuation for Forward Exchange Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Rate Valuation for Forward Exchange Transactions | L6 | trm08 p.105 | loio `7e19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7e19c55368511d4be10000000a174cb4.html?locale=en-US)

Exchange rates

When you conclude an FX forward transaction, you enter the transaction spot rate for the purchase currency/sale currency and the transaction swap rate for the purchase currency/sale currency. In addition, the system determines the market spot rate for the purchase currency/local currency and the market swap rate for the purchase currency/local currency on the contract date. The transaction spot rate in sale currency/local currency and the transaction swap rate for the sale currency/local currency are calculated on the basis of the exchange rates for the purchase currency/local currency and the sale currency/purchase currency.

Amounts

As a result of the transaction amounts you enter (in purchase and sale currency) and the rates calculated by the system, there are three amounts (in purchase currency, sale currency and local currency), which represent the forward rates for the transaction. Likewise, there are three amounts for the transaction spot rates. The system adjusts the transaction amount that is the following currency in the currency pair 'purchase currency/sale currency'.

Example

Transaction Data

Purchase 100 USD, Sale 12,000 JPY, Spot USD/JPY = 110

Local currency EUR, Forward rate USD/EUR 1.00, Spot rate USD/EUR = 1,1

Following currency for pair USD/JPY is JPY

Forward Rates and Amounts

1 USD = 1 EUR

120 JPY = 1 EUR

=> 1 EUR = 120 JPY

100 USD; 12,000 JPY; 100 EUR

Spot Rates and Amounts

1 USD = 1.1 EUR

110 JPY = 1 EUR

=> 1 EUR = 110 JPY

100 USD; 11,000 JPY; 110 EUR

Valuation currency

If the valuation currency is the purchase currency, sale currency or local currency, the rates for forward exchange transactions are valued using the about rates and amounts. If not, the system determines the transaction spot rate and transaction swap rate for the purchase currency/valuation currency for each valuation key date and calculates the amounts according to the above rules.

Rate valuation for forward exchange transactions considers the change in the spot or forward exchange rate on the key date when compared with the spot or forward exchange rate for the transaction. There are three valuation types:

Transaction spot rate compared with the market spot rate on the valuation key date.

Transaction forward rate compared with the market forward rate on the valuation key date.

Transaction forward rate compared with the market spot rate on the valuation key date.

The system uses the spot and forward rates on the FX market to calculate the cross-rate between the purchase currency/valuation currency and the sale currency/valuation currency on the valuation key date. These rates are determined on the basis of exchange

rate types of spot rate and swap rate for purchase currency/valuation currency and sale currency/valuation currency as follows:

The system determines the FX spot rate purchase currency/valuation currency.

If this rate is quoted directly, the FX swap rate purchase currency/valuation currency is determined.

If this rate is quoted indirectly, the FX swap rate valuation currency/purchase currency is determined.

The procedure for the sales currency is the same as that for the purchase currency. Foreign exchange swap rates are only read if the system should valuate using the forward market rate on the valuation key date.

In each of the three cases the rates can be determined in the usual way ("normal") or using cross-rates ("cross"). If you use crossrates, the gain or loss associated with the purchase currency and the gain or loss associated with the sale currency are disclosed separately. If you choose "normal", the gains and losses aren't split in this way.

Normal

The forward rate for the transaction is compared to the result of the following calculation:

Transaction amount in purchase currency x Market rate on the valuation key date for purchase currency/valuation currency

– Transaction amount in sale currency x Market rate on the valuation key date for sale currency/valuation currency.

Both transaction amounts (in purchase and sale currency) are translated using the market spot or forward rates for purchase currency/valuation currency and sale currency/valuation currency in order to determine the difference.

If you use the transaction spot rate as a basis for the comparison, the system adjusts the amount in the following currency from the transaction to account for the transaction swap 'purchase currency/sale currency' and then translates the adjusted amount.

Cross

Transaction amount in purchase currency x Market rate on the valuation key date for purchase currency/valuation currency

– Amount in valuation currency

Transaction amount in valuation currency – Transaction amount in sale currency x Market rate on valuation key date for sale currency/valuation currency

(Amount in valuation currency = Amount in purchase currency x Transaction rate for purchase currency/valuation currency)

The transaction is treated as if there were two transactions:purchase currency – valuation currencyandvaluation currency – sale currency. The calculation for the purchase currency is described below. The same algorithm is used in the calculation for the sale currency.

If the comparison is based on the transaction forward rate, the transaction amount in purchase currency is calculated using the market spot or forward rate and compared with the amount in valuation currency. This is calculated by translating the transaction amount in purchase currency using the transaction forward rate 'purchase currency/valuation currency'.

If the comparison is based on the transaction spot rate, and the purchase currency is the following currency in the currency pair 'purchase currency/sale currency', the system adjusts the transaction amount in purchase currency to account for the transaction spot rate 'purchase currency/sale currency' and then translates the adjusted amount. The amount in valuation currency is calculated by translating the adjusted transaction amount in purchase currency using the transaction spot rate 'purchase currency/valuation currency'.

The difference, which is calculated in valuation currency, is translated into the position currency using the market exchange rate.

**Note:**

**Note:**

For forward exchange transactions, the system always assumes that the position currency is the same as the valuation currency. The only exception is when the valuation currency is changed during the transaction term, which is a special case.

You apply rules to these amounts in order to calculate the write-up and write-down amounts. The following rules can be used:

Write up to market value

Write up to purchase value

Don't write up

Write down to market value

Write down to purchase value

Do not write down

Flows are generated for the write-up or write-down amounts. If the +/- sign differs from earlier valuations, the system generates clearing flows. If the result of the valuation is that the position has to be written down, for example, and write-up flows already exist, the system would generate one flow to clear the write-ups, and one flow for the remaining write-down amount. The same applies if a write-up offsets previous write-downs. The write-up and write-down amounts are only disclosed in valuation currency.

###### Index Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Index Valuation | L6 | trm08 p.108 | loio `4f672e981a3a43d8e10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f672e981a3a43d8e10000000a42189c.html?locale=en-US)

Use

Index valuation is only available for index-linked bonds and price-index related interest rate instruments.

The system compares the book index value for the position with the market index value. It does this by multiplying the "clean" book value for the position in position currency with the market index. The "clean" position has been adjusted to remove the effects of index-linked price components. The difference between this value and the book value of the position in position currency is the write-up or write-down amount. This is then translated to the valuation currency using the book exchange rate. You cannot vary the procedure for this step by applying different rules.

Flows are generated for the write-up or write-down amounts. This valuation step can generate reset flows. Clearing flows, on the other, cannot be generated. The system assumes that there are no offsetting effects for an index.

**Note:**

The NPV or price used in Security Valuation can also include the price index already. If this is case, you must set the NPV/Price Including Price Index indicator, in the configuration of the security valuation procedure in the Define Security Valuation Procedure Customizing activity.

If the NPV/Price Including Price Index indicator is selected in the security valuation procedure, the NPV/price includes the price index, in contrast to the index-clean NPV/price.

The following formulas are then used in the security valuation if the book value is used as the valuation base:

Write-up index-clean = NPV / Market index factor - Book value index-clean

Write-up in position currency = Write-up index-clean * Book index factor

Book index factor = Book value / Book value index-clean

The following formulas are then used in the security valuation if the nominal (repayment) value is used as the valuation base:

Write-up in position currency = NPV - Book value

Write-up index-clean = 0 (isn't calculated)

If the book value is used as the valuation base, the NPV is divided by market price index factor. Therefore, price index valuation needs to be performed before security valuation so that the book index factor equals the current market price index factor in the security valuation step. If security valuation is performed before price index valuation, the total book value after valuation is the same as when the index-clean NPV/price is applied. However, the security valuation write-up differs for the NPV or security price with and without price index.

In the predefined valuation procedures 9011 Mark-to-Market: Clean Price Incl. Price Index (OCI), 9201 Clean Price Incl. Price Index (Write Up to Purch. Value), and 9221 Clean Price Incl. Price Index (Write dDown, No Write Up), the indicator NPV/Price Including Price Index is selected.

###### Swap/Margin Accrual

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Swap/Margin Accrual | L6 | trm08 p.109 | loio `8119c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8119c55368511d4be10000000a174cb4.html?locale=en-US)

Use

The Swap/margin accrual valuation step distributes the swap/margin amount at contract date over the term of the forward FX transaction. The resulting swap accrual amount of this valuation step is the portion of the swap amount at contract date for the number of days from contract date + 2 days to key date (incl.) in relation to the term of the transaction in days (contract date + 2 days to value date) minus the previous swap accruals.

[figure TRM08-F035 - The system first calculates the accrual amount in valuation currency and then converts it to position currency using the current market exchange rate. For forward exchange transactions, the system always assumes that the position currency is the same as the valuation currency. The only exception is if the valuation currency is changed during the transaction term, which is a special case.]

The system first calculates the accrual amount in valuation currency and then converts it to position currency using the current market exchange rate. For forward exchange transactions, the system always assumes that the position currency is the same as the valuation currency. The only exception is if the valuation currency is changed during the transaction term, which is a special case.

**Note:**

You can't vary the procedure for this step by applying different rules.

Swap

The termswapis used in conjunction with forward exchange transactions. The swap is first calculated in the following currency on the basis of the contract data, and then translated into the valuation currency using market spot exchange rate for the contract date.

Margin

The termmarginis used in conjunction with forward bonds. The margin is calculated based on the contract data in position currency.

Book exchange rate

If one of the two book values is 0, or the book values have opposing +/- signs, the book exchange rate for a forward bond is set to the opening bond spot rate for the contract.

Flows are generated for the write-up or write-down amount.

If the +/- sign differs from the total of all the earlier flows, the system generates a clearing flow.

If the result of the valuation is that the position has to be written down, for example, and write-up flows already exist, the system would generate one flow to clear the write-ups, and one flow for the remaining write-down amount. The same applies if a write-up offsets former write-downs.

This valuation step can generate reset flows.

**Example**

The following forward FX transaction is available in your system:

Purchase of 1,000,000.00 USD

Forward rate: EUR/USD 1.21

Value date: 06/15/2021

Spot rate at contract date: 1.11

Swap rate: 0.10

Contract rate: 1.21

Contract date: 12/01/2020

Valuation at 12/31/2020

|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
|Rate valuation for forward exchange transactions (with the setting spot/spot)|Contract date 12/1/2020|Spot rate 1.11|1,000,000.00 USD|900,900.90 EUR| | |
| |Key date 12/31/2020|Spot rate 1.08|1,000,000.00 USD|925,925.93 EUR| | |
| | | | |25,025.03 EUR|Rate valuation for forward exchange transactions result|V500|
| | | | |+ 0.00 EUR|Amount of previous rate valuation for forward exchange transactions| |


|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
| | | | |25,025.03 EUR|New book value after rate valuation for forward exchange transactions| |
|Swap accrual|Contract date 12/1/2020| | | | | |
| |Key date 12/31/2020|Contract rate 1.21|1,000,000.00 USD|- 826,446.28 EUR|29 days Contract date + 2 days to key date (inclusive)| |
| |Value date 06/15/2021|Spot rate at contract date 1.11|1,000,000.00 USD|+ 900,900.90 EUR|194 days Contract date + 2 days| |
| | | |=|+ 74,454.62 EUR|Swap amount at contract date| |
| | | | |11,129.81 EUR|Swap accrual Calculation: 74,454.62 EUR * 29/194 - 0 (amount of previous swap accruals)|V550|
| | | | |36,154.84 EUR|New book value after swap accrual = Book value after rate valuation for forward exchange transactions + Swap accrual| |
|Swap valuation|Contract date 12/1/2020|Swap rate 0.17720 (interpolated value)| |63,324.81 EUR|Swap amount before swap valuation = Swap amount at contract date Swap accruals (total)| |
| |Key date 12/31/2020|Spot+Swap rate 1.25720|1,000,000.00 USD|795,418,39 EUR| | |
| | |Spot rate at key date 1.08000|1,000,000.00 USD|925,925.93 EUR| | |


|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
| | | | |130,507.54 EUR|Swap amount at key date| |
| | | | |- 67,182,73 EUR|Swap valuation result = Swap amount before swap valuation Swap amount at key date|V571|
| | | | |- 31,027.89 EUR|New book value after swap valuation = Book value after swap accrual + Swap valuation result| |


**Valuation at 01/31/2021**

|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
|Rate valuation for forward exchange transactions (with the setting spot/spot)|Contract date 12/1/2020|Spot rate 1.11|1,000,000.00 USD|900,900.90 EUR| | |
| |Key date 01/31/2021|Spot rate 1.15|1,000,000.00 USD|869,565.22 EUR| | |
| | | | |- 31,335.68 EUR|Rate valuation for forward exchange transactions result|V501|
| | | | |- 25,025.03 EUR|Clear previous rate valuation for forward exchange transactions result|V502|
| | | | |- 87,388.60 EUR|New book value after rate valuation for forward exchange transactions = Old book value + Rate valuation for forward exchange transactions result - Previous rate valuation for| |


|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
| | | | | |forward exchange transactions result| |
|Swap accrual|Contract date 12/1/2020| | | | | |
| |Key date 01/31/2021|Contract rate 1.21|1,000,000.00 USD|- 826,446.28 EUR|60 days Contract date + 2 days to key date inclusive (+ 1 day)| |
| |Value date 06/15/2021|Spot rate at contract date 1.11|1,000,000.00 USD|+ 900,900.90 EUR|194 days Contract date + 2 days to value date| |
| | | |=|+ 74,454.62 EUR|Swap amount at contract date| |
| | | | |11,897.39 EUR|Swap accrual Calculation: 74,454.62 EUR * 60/194 11,129.81 EUR (amount of previous swap accruals)|V550|
| | | | |-75,491.21 EUR|New book value after swap accrual = Book value after rate valuation for forward exchange transactions + Swap accrual| |
|Swap valuation|Contract date 12/1/2020|Swap rate 0.14360 (interpolated value)| |118,610.15 EUR|Swap amount before swap valuation = Swap amount at contract date Swap accruals (total) - Previous swap valuation| |
| |Key date 01/31/2021|Spot+Swap rate 1.29360|1,000,000.00 USD|773,036,49 EUR| | |
| | |Spot rate at key date 1.15000|1,000,000.00 USD|869,565.22 EUR| | |


|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
| | | | |96,528.73 EUR|Swap amount at key date| |
| | | | |22,081,42 EUR|Swap valuation result = Swap amount before swap valuation Swap amount at key date|V571|
| | | | |- 53,409.79 EUR|New book value after swap valuation = Book value after swap accrual + Swap valuation result| |

###### Swap Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Swap Valuation | L6 | trm08 p.114 | loio `8419c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8419c55368511d4be10000000a174cb4.html?locale=en-US)

Use

The swap valuation function considers the difference between the market swap from the valuation key date to the close date and the "book swap." The book swap is the remaining swap after swap accruals and valuations.

The valuation step requires a swap rate from the valuation key date to the close date as market information.

For foreign exchange transactions using the valuation currency, the foreign currency/valuation currency swap rate is determined. This in turn is used to determine the market swap from the valuation key date to the close date in valuation currency.

The leading currency/following currency swap rate (in the currency pair purchase currency, sale currency) is determined for foreign exchange transactions that do not use the local currency. The swap rate determined in this way is used to determine the market swap from the valuation key date to the close date in following currency and then converted to valuation currency with the foreign exchange spot rate on the valuation key date.

Themarket swapis compared with thebook swap.The difference is recorded as gain/loss.

You cannot vary the procedure for this step by applying different rules.

Flows are generated for the write-up or write-down amount. If the +/- sign differs from the earlier flows, the system generates a

clearing flow. If the result of the valuation is that the position has to be written down, for example, and write-up flows already exist, the system would generate one flow to clear the write-ups, and one flow for the remaining write-down amount. The same applies if a write-up offsets previous write-downs.

The write-up and write-down amounts are only disclosed in valuation currency.

**Example**

The following forward FX transaction is available in your system:

Purchase of 1,000,000.00 USD

Forward rate: EUR/USD 1.21

Value date: 06/15/2021

Spot rate at contract date: 1.11

Swap rate: 0.10

Contract rate: 1.21

Contract date: 12/01/2020

Valuation at 12/31/2020

|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
|Rate valuation for forward exchange transactions (with the setting spot/spot)|Contract date 12/1/2020|Spot rate 1.11|1,000,000.00 USD|900,900.90 EUR| | |
| |Key date 12/31/2020|Spot rate 1.08|1,000,000.00 USD|925,925.93 EUR| | |
| | | | |25,025.03 EUR|Rate valuation for forward exchange transactions result|V500|
| | | | |+ 0.00 EUR|Amount of previous rate valuation for forward exchange transactions| |
| | | | |25,025.03 EUR|New book value after rate valuation for forward exchange transactions| |
|Swap accrual|Contract date 12/1/2020| | | | | |
| |Key date 12/31/2020|Contract rate 1.21|1,000,000.00 USD|- 826,446.28 EUR|29 days Contract date + 2 days to key date (inclusive)| |
| |Value date 06/15/2021|Spot rate at contract date 1.11|1,000,000.00 USD|+ 900,900.90 EUR|194 days Contract date + 2 days| |
| | | |=|+ 74,454.62 EUR|Swap amount at contract date| |
| | | | |11,129.81 EUR|Swap accrual|V550|


|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
| | | | | |Calculation: 74,454.62 EUR * 29/194 - 0 (amount of previous swap accruals)| |
| | | | |36,154.84 EUR|New book value after swap accrual = Book value after rate valuation for forward exchange transactions + Swap accrual| |
|Swap valuation|Contract date 12/1/2020|Swap rate 0.17720 (interpolated value)| |63,324.81 EUR|Swap amount before swap valuation = Swap amount at contract date Swap accruals (total)| |
| |Key date 12/31/2020|Spot+Swap rate 1.25720|1,000,000.00 USD|795,418,39 EUR| | |
| | |Spot rate at key date 1.08000|1,000,000.00 USD|925,925.93 EUR| | |
| | | | |130,507.54 EUR|Swap amount at key date| |
| | | | |- 67,182,73 EUR|Swap valuation result = Swap amount before swap valuation Swap amount at key date|V571|
| | | | |- 31,027.89 EUR|New book value after swap valuation = Book value after swap accrual + Swap valuation result| |


**Valuation at 01/31/2021**

|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
|Rate valuation for forward exchange transactions|Contract date 12/1/2020|Spot rate 1.11|1,000,000.00 USD|900,900.90 EUR| | |


|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
|(with the setting spot/spot)| | | | | | |
| |Key date 01/31/2021|Spot rate 1.15|1,000,000.00 USD|869,565.22 EUR| | |
| | | | |- 31,335.68 EUR|Rate valuation for forward exchange transactions result|V501|
| | | | |- 25,025.03 EUR|Clear previous rate valuation for forward exchange transactions result|V502|
| | | | |- 87,388.60 EUR|New book value after rate valuation for forward exchange transactions = Old book value + Rate valuation for forward exchange transactions result - Previous rate valuation for forward exchange transactions result| |
|Swap accrual|Contract date 12/1/2020| | | | | |
| |Key date 01/31/2021|Contract rate 1.21|1,000,000.00 USD|- 826,446.28 EUR|60 days Contract date + 2 days to key date inclusive (+ 1 day)| |
| |Value date 06/15/2021|Spot rate at contract date 1.11|1,000,000.00 USD|+ 900,900.90 EUR|194 days Contract date + 2 days to value date| |
| | | |=|+ 74,454.62 EUR|Swap amount at contract date| |
| | | | |11,897.39 EUR|Swap accrual Calculation:|V550|


|Valuation Step|Dates|Rates|Amount in PC|Amount in VC|Remarks|Update Type|
|---|---|---|---|---|---|---|
| | | | | |74,454.62 EUR * 60/194 11,129.81 EUR (amount of previous swap accruals)| |
| | | | |-75,491.21 EUR|New book value after swap accrual = Book value after rate valuation for forward exchange transactions + Swap accrual| |
|Swap valuation|Contract date 12/1/2020|Swap rate 0.14360 (interpolated value)| |118,610.15 EUR|Swap amount before swap valuation = Swap amount at contract date Swap accruals (total) - Previous swap valuation| |
| |Key date 01/31/2021|Spot+Swap rate 1.29360|1,000,000.00 USD|773,036,49 EUR| | |
| | |Spot rate at key date 1.15000|1,000,000.00 USD|869,565.22 EUR| | |
| | | | |96,528.73 EUR|Swap amount at key date| |
| | | | |22,081,42 EUR|Swap valuation result = Swap amount before swap valuation Swap amount at key date|V571|
| | | | |- 53,409.79 EUR|New book value after swap valuation = Book value after swap accrual + Swap valuation result| |


**Related Information**

Valuation

###### Futures Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Futures Valuation | L6 | trm08 p.118 | loio `8d15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8d15da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You valuate the futures balance sheet account and the variation margin balance sheet account with the execute valuation function. You can reverse using the reverse valuation function.

Rate gains/losses are posted or created in accordance with the settings for creating derived business transactions either with the post and fix or the update function. Both of these transactions can be found in the Derived Business Transactions area.

**Prerequisites**

You must make the following settings in Customizing:

Define a one-step price valuation procedure and a foreign currency valuation procedure. Choose Variation Margin as the component for valuation in the foreign currency valuation procedure.

Define a position management procedure which contains the previously defined valuation procedure. In addition, under Liability/Asset Position the system proposes Manage Assets and Liabilities Balance Sheet Account.

Update types must be redefined for the key date valuation and entered under One-step: Separate balance sheet accounts .

You will also need to enter update types for the foreign currency valuation of the variation margin under Foreign currency valuation .

You must then define relevant update types for futures under Rate gains/losses for derived business transactions.

Account determination is adjusted for all new update types. Account symbols for the asset and liabilities balance sheet account need to be defined as well as posting specifications for postings.

You can now create, valuate and resell futures positions. For the key date valuation and the closing (also partial closing) of open business transactions, flows are created and if necessary posted according to Customizing settings.


For more information, see the implementation guide (IMG) and Account Determination for Valuating Futures .

For general information about futures, see Listed Derivatives/Futures.

###### Current Portion Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Current Portion Transfer | L6 | trm08 p.119 | loio `51bc06310fcf40488a3c51203068806d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/51bc06310fcf40488a3c51203068806d.html?locale=en-US)

**Use**

The transfer of the current portion of your long-term liabilities/assets posts the amount of repayments for a treasury position that are due within a certain period (for example, within the next 12 months) to a specific G/L account for balance sheet purposes.

**Features**

The current portion transfer is executed as an additional valuation step as part of the key date valuation.

The current portion transfer posting is reset on the next day, regardless of the valuation category.

You can either transfer the Nominal Amount or the Book Value of the current portion.

The current portion in the book value is calculated as follows: In the first step, the percentage share of the nominal that is repaid to the original nominal is calculated. In the second step, this percentage is applied to the book value on the key date, which results in the book value of the current portion.

**Example**

You have two treasury ledger positions that have regular repayments every 12 months and are assigned to a long-term valuation class.

During period-end closing, you want to report the portion of the position that is due within the next 12 months* separately as a current portion.

To do this, the current portion is transferred to a different G/L account on the key date during the key date valuation.

On the next day, the system resets this posting.

The position management procedure of the treasury position remains unchanged.

**Customizing**

In the Define Current Portion Transfer Procedure Customizing activity, create a procedure for valuation category 012 Current Portion Transfer by entering the period for calculating the current portion. Also assign the exchange rate type for the currency translation for treasury positions in foreign currencies. In the Base Amount field, you decide whether you want to transfer the Nominal Amount or the Book Value of the current portion.

In addition, you can specify which exchange rate is used for the currency translation:

Book Rate (default setting)

The last book rate is used for the currency translation.

Market Rate

The exchange rate on the valuation date is used for the currency translation.

The valuation category is relevant for the following position management categories:

Securities/Loans/Money Market Transactions/Listed Options

Normal Style (Without Index-Linked Bonds), Securities/Loans with Installment Repayment (Without IndexLinked Bonds)

In the Define Position Management Procedures Customizing activity, you can assign the CPT procedure to the position management procedures for long-term treasury positions with installment repayment.

Define update types to post the current portion from the source position account to the target position account in the Define Update Types and Assign UsagesCustomizing activity and assign them to the usage Key Date Valuation.

For example:

- V800 Transfer Current Portion (Asset)

- V801 Transfer Current Portion (Liability)


- VR800 Reset Transfer Current Portion (Asset)

- VR801 Reset Transfer Current Portion (Liability)


In the Assign Update Types for Valuation Customizing activity, on the Current Portion Transfer tab, you must assign the update types for each affected position management procedure.

In the Indicate Update Types as Relevant to Posting Customizing activity, you must add the update types and set the Relevant for Posting indicator.

In the Define Account Determination for Treasury and Risk Management Customizing activity, you must define the posting specifications and assign them to the update types. This may require the definition of a new account symbol in the

Define Account Symbols configuration activity. For the new account symbol, you must assign the G/L account.

Customizing Example:

Define Account Symbols

Create account symbol 1.6 Position (Current Position) with posting category 1 Position Posting (Book Value) in Position Currency.

Here's what that looks like (English only):

[figure TRM08-F037 - Define Account Determination for Treasury and Risk Management]

Define Account Determination for Treasury and Risk Management

Create the following posting specifications:

15900 Current Portion Transfer (Asset) with document type SA, and the new account symbol 1.6 for posting key 40 and account symbol 1 for posting key 50.

Here's what that looks like (English only):

[figure TRM08-F038 - 15910 Current Portion Transfer (Liability) with document type SA, and the new account symbol 1 for posting key 40 and account symbol 1.6 for posting key 50.]

15910 Current Portion Transfer (Liability) with document type SA, and the new account symbol 1 for posting key 40 and account symbol 1.6 for posting key 50.

Here's what that looks like (English only):

[figure TRM08-F039]

Assign the posting specifications to the new update types for current portion transfer:

- V800 Transfer Current Portion (Asset): Posting specification 15900

- V801 Transfer Current Portion (Liability): Posting specification 15910


Here's what that looks like (English only):

[figure TRM08-F040 - Here's what that looks like (English only):]

- VR800 Reset Transfer Current Portion (Asset): Posting specification 15910

- VR801 Reset Transfer Current Portion (Liability): Posting specification 15900


Here's what that looks like (English only):

[figure TRM08-F041 - Here's what that looks like (English only):]

Assign the relevant G/L accounts to the new account symbol.

###### Run Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Run Valuation | L6 | trm08 p.122 | loio `094cee52f0720175e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/094cee52f0720175e10000000a44538d.html?locale=en-US)

App ID: TPM1

With this app, you can perform a key date valuation for the selected valuation-area-dependent treasury positions.

**Note:**

The app ignores the Scheduled status of the derived business transaction of the open OTC transaction.

Prerequisites

The rates, prices, and NPVs required for the valuation must be available in the price/rate and NPV tables.

For manual valuation, the new book values need to be entered in the Enter Book Values for Manual Valuation app.

All the business transactions before the valuation key date must be fixed. In other words, no business transactions affecting the position amount may have the status Scheduled before the valuation key date.

All derived business transactions have to be updated and fixed.

See also:

Update Derived Business Transactions

Post Derived Business Transactions

**Features**

Perform the key date valuation according to the settings in the relevant position management procedure. Use the following valuation categories:

Year-End Valuation

Mid-Year Valuation with Reset

Mid-Year Valuation Without Reset

Perform a manual valuation of treasury positions for which you can specify the required book values in the Enter Book Values for Manual Valuation app using the following valuation categories:

Manual Valuation Without Reset

Manual Valuation with Reset

**Activities**

- 1. Open the Run Valuation app on SAP Fiori launchpad.
- 2. Select the treasury positions.


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

If you have defined your own differentiation terms (in the Define Custom Differentiation Terms configuration activity) and you use the fields as differentiation terms for your treasury positions, these fields are also available as

selection criteria.

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

- 3. You can restrict the selected treasury positions by their position management procedure.
- 4. Enter the valuation parameters:


Enter the key date for the valuation.

Select the valuation category:

Year-End Valuation

Mid-Year Valuation with Reset

**Note:**

If you use the Mid-Year Valuation with Reset valuation category, reset flows are generated for the day following the valuation key date in addition to the valuation flows. Usually, reset flows are posted on the first day of the next month. You can therefore see the effects of the valuation only on the valuation key date.

Mid-Year Valuation Without Reset

Manual Valuation Without Reset

This valuation category allows you to write a position up/down to a fixed book value, independent of the valuation rules defined. You need to maintain these with the Enter Book Values for Manual Valuation app in position currency and valuation currency. For index-linked bonds, you also need to enter the "clean" book value. During the valuation run, the system runs through the steps defined in the position management procedure. However, it always writes the position up/down to the defined book value.

The following valuation steps support manual valuation:

Security valuation

Foreign currency valuation

One-step price valuation

Index valuation

Manual Valuation With Reset

In addition to the manual valuation flows, reset flows are generated for the day following the valuation key date. You can therefore see the effects of the valuation only on the valuation key date.

Revaluate Without Posting indicator

This indicator specifies whether a revaluation has to be performed for the selected positions. In the case of a revaluation, positions are revaluated on the basis of currently available market data. If market data was subsequently changed, the valuation result may differ from the valuation result that was already posted.

**Note:**

Revaluation is only possible in test run mode.

- 5. In the Posting Control area, you can first simulate the valuation by setting the Test Run indicator.
- 6. If you set the Display Positions indicator, the system first displays the selected positions.

If you always want to have the list displayed in a certain layout, you can specify this layout on the selection screen.

- 7. The system generates a valuation log containing all the information relating to the valuation of the individual positions.

By choosing More Local File in the menu, you can store the log locally on your system.

- 8. Result


The system has valued the selected positions and posted the corresponding valuation flows.

When you perform a key date valuation, the system sets an internal block to prevent operational business transactions that affect position amounts from being created before the valuation key date when the valuation has not been reversed previously.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Valuation Reverse Valuation Treasury Position

###### Reverse Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > Reverse Valuation | L6 | trm08 p.126 | loio `8719c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8719c55368511d4be10000000a174cb4.html?locale=en-US)

App ID: TPM2

With this app, you can reverse a valuation run.

**Activities**

- 1. Open the Reverse Valuation app on SAP Fiori launchpad.
- 2. Use the following selection criteria, to select treasury positions.


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

- 3. You can restrict the selected treasury positions by their position management procedure.
- 4. Enter the valuation key date.
- 5. Enter the Reversal reason.
- 6. Enter the following dates:

Posting Date

Posting Period

Posting Date of Reset

Posting Period of Reset

- 7. You can simulate the reversal first by setting the Test run indicator.
- 8. If you set the Display positions indicator, the system first lists the selected positions when you run the report. You can then start the reversal run from the list.
- 9. The system generates a posting log.


**Supported Device Types**

Desktop

Tablet

**Related Information**

Valuation Run Valuation

###### P-GAAP

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP | L6 | trm08 p.128 | loio `d6a7d65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d6a7d65378024308e10000000a174cb4.html?locale=en-US)

Use

When a company takes over another company (affiliated companies; holding > 50%), then the P-GAAP accounting rules apply in the consolidated financial statements.

The company that was taken over must retain the historical key figures (= Historical GAAP) (acquisition value, total profit, boo value,...) and the P-GAAP key figures (acquisition value, total profit, book value,...) for the securities in the position.

The realization of the P-GAAP requirements in position management occurs in a valuation area using the following position components for value adjustments:

- 1025 Gains value adjustment (VAD gains)

= amount by which the historical OCI gains must be adjusted by in order to get the P-GAAP value.

- 1026 losses value adjustment (VAD losses)

= amount by which the historical OCI losses must be adjusted by in order to get the P-GAAP value.

- 1027 original value adjustment


= original value adjustment of value adjustment amount only for reporting.

It is filled with the old data transfer and only adjusted with position changes proportionately.

Generally the following applies:

|P-GAAP - purchase value|= H-GAAP- purchase value + VAD|
|---|---|
|P-GAAP-OCI gains|= H-GAAP-OCI gains - VAD gains|
|P-GAAP-OCI losses|= H-GAAP-OCI losses - VAD losses|


These position components are available for the following position management categories:

001 Securities/loans/money market without index-linked bonds

008 Securities/Loans with Installment Repayment (without Index-Linked Bonds)

**Example**

The company Y (subsidiary) has the following position in the holding category Available for Sale.

Historical Key Figures According to IFRS 31.12.06

|Acquisition value|100 €|
|---|---|
|OCI (gains not affecting profit)|20 €|
|Book value|120 €|


- Company X (parent) takes over company Y on 01.01.07. The market value of the position on the takeover date is 120 €.
- Company Y must also retain the following key figures (holding category Available for Sale ).


P-GAAP Key Figures IFRS 01.01.07

|Acquisition value|120 €|
|---|---|
|OCI (gains not affecting profit)|0 €|


|Book value|120 €|
|---|---|


The following values result for the position components:

|Position component|Values|
|---|---|
|Acquisition value|100|
|OCI (gains not affecting profit)|20|
|Gains value adjustment|20|
|Original value adjustment|20|
|Book value|120|
|Calculation of P-GAAP values:| |
|Acquisition value P-GAAP|= Acquisition value + VAD = 120|
|Book value P-GAAP|= Acquisition value P-GAAP = 120|


**Integration**

You can use the function for the following product categories:

Stocks (010)

Investment certificates (020)

Bonds (040)

Bonds with installment repayment (042)

Shareholdings (160)

The position components Value adjustment gains and value adjustment losses can be used by the consolidation solutions Consolidation (EC-CS) or Business Consolidation (SEM-BCS) .

**Prerequisites**

In Customizing under Assign Update Types for Derived Business Transactions you must assign the necessary update types for mapping P-GAAP Accounting on the tab Value Adjustment .

You must enter the initial values for the new position components for the value adjustment ( value adjustment gains, value adjustment losses and original value adjustment ) using the function Old data transfer .

In Customizing under Define Amortization Procedure , you should set the flag Amortization: Value Adjustment for monetary positions.

**Features**

The P-GAAP positions are integrated in position management. The adjustment of the position components occurs automatically through the derived business transactions when you execute the functions:

Position Components for Adjustments with Valuations

Position Components for Adjustments with Position Outflows

Calculation of realized gains and losses with Intragroup trading

The corresponding proportion of VAD components of the selling company is transferred to the company doing the takeover.

The adjustment of the position components for adjustment must be executed accordingly.

Position Components for Adjustments with Impairment

Position Components for Adjustments with Transfer Postings

With all transfer business transactions (securities account transfer, portfolio transfer, valuation class transfer, corporate actions, exercise of rights), the position components for adjustment are transferred as are all other position components.

The position components are available for your individual reporting in logical databases FTI_TR_POSITIONS and FTI_TR_PERIODS .

**Activities**

- 1. Make the required settings in Customizing.
- 2. Calculate the initial values of the position components for adjustment out of the SAP system.
- 3. Bring the initial values of the position components for adjustment for all existing positions into the system using function old data transfer .

- 4. If you manage the positions as usual, the position components for adjustment are adjusted as described below under features.


**Further Notes**

The new position components for adjustment are also available in function Initialization .

If you no longer want to use the function, you can also set up an additional valuation area to fulfill the P-GAAP requirements.

Example:

Company Y creates an additional valuation area and reports the data of this new valuation area to the group.

Holding Category: Available for Sale

|Company Y|Acquisition value|OCI|Book value|Market value|
|---|---|---|---|---|
|Valuation area 1:HGAAP|100|20|120|120|
|Valuation area 2:PGAAP|120|0|120|120|


Holding Category: Held to Maturity

|Company 1|Acquisition value|Amortized acquisition value|Book value|Market value|
|---|---|---|---|---|


|Valuation area 1:HGAAP|98|99|99|102|
|---|---|---|---|---|
|Valuation area 2:PGAAP|102|102*|102|102|


* follows the rules of the position management procedure

###### Position Components for Adjustments with Valuations

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Valuations | L7 | trm08 p.132 | loio `9a0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9a0cda531198434de10000000a174cb4.html?locale=en-US)

The handling of position components for adjustments to a valuation depends on the holding category.

**Valuation of non-monetary positions**

Non-realized gains and non-realized losses are position components in the subledger of Transaction Manager .

They can be positive or negative.

The value adjustment is managed on the following position components :

Gains value adjustment

Losses value adjustment

The gains value adjustment adjusts the non-realized gains and the losses value adjustment adjusts the non-realized losses.

Note:

The gains and losses value adjustment can both be positive and negative.

Value adjustment (VAD) = Gains value adjustment + Losses value adjustment

OCI (P-GAAP) = OCI (H-GAAP) - value adjustment

Case 1 Case 2 Case 3 Case 4 Case 5 Case 6

OCI (H-GAAP) ≥ 0 OCI (H-GAAP) < 0

VAD > 0 VAD ≤ 0 VAD < 0 VAD ≥ 0

VAD ≤OCI (HGAAP)

VAD >OCI (HGAAP)

VAD ≤OCI (HGAAP)

VAD >OCI (HGAAP)

Position Components

VAD Gains VAD OCI (H-GAAP) VAD 0 VAD - OCI (HGAAP)

0

VAD losses 0 VAD - OCI (HGAAP)

0 VAD OCI (H-GAAP) VAD

Calculation of Delta VADS (Flows)

VAD Gains + VAD losses (old)

+ OCI (HGAAP) - VAD Gains (old)

+ VAD losses (old)

- VAD gains (old)

+ VAD losses (old) - OCI (HGAAP)

- VAD gains (old)

| |Case 1|Case 2|Case 3|Case 4|Case 5|Case 6|
|---|---|---|---|---|---|---|
|VAD losses|- VAD losses (old)|+ VAD Gains (old) - OCI (HGAAP)|- VAD losses (old)|+ VAD gains (old)|+ OCI (HGAAP) - VAD losses (old)|+ VAD gains (old)|
| |Example|Example|Example|Example|Example|Example|


**Valuation of monetary positions**

The maturity of the valuation of monetary positions is similar to the valuation of non-monetary positions . After the named valuation steps, a linear amortization process also takes place.

###### Example: Valuation Case 1

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Valuations > Example: Valuation Case 1 | L8 | trm08 p.133 | loio `c40cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c40cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 1:


OCI (H-GAAP) ≥ 0

VAD > 0

VAD ≤ OCI (H-GAAP)

Example Data:

VAD = 20 UNI

Unrealized gains (before valuation) = 50 UNI

Market valuation is 132 UNI, so unrealized gains of 32 UNI

|Position components|Values before valuation|Valuation| |Values after valuation|P-GAAP - Values|
|---|---|---|---|---|---|
| |(1) Depreciation|(2) VAD transfer posting| | | |
|Purchase value|100| | |100|120|
|Valuation|50|- 18| |32|12|
|Unrealized gains and losses|50|- 18| |32|12|
|Technical clearing component| | | | | |
|Consolidated gains| | | | | |
|Consolidated losses| | | | | |
|VAD Gains|20| | |20| |
|VAD losses| | | | | |


|Position components|Values before valuation|Valuation| |Values after valuation|P-GAAP - Values|
|---|---|---|---|---|---|
|Book value|150| | |132|132|
|Amortized acquisition value|100| | |100|120|

###### Example: Valuation Case 2

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Valuations > Example: Valuation Case 2 | L8 | trm08 p.134 | loio `b50cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b50cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 2:


OCI (H-GAAP) ≥ 0

VAD > 0

VAD > OCI (H-GAAP)

Example Data:

VAD: 20 UNI

Unrealized gains (before valuation): 32 UNI

Valuation at market price of 115 UNI, means unrealized gains of 15 UNI

|Position components|Book values before valuation|Valuation| |Book values after valuation|Consolidation|
|---|---|---|---|---|---|
| |(1) Depreciation|(2) VAD transfer posting| | | |
|Purchase value|100| | |100|120|
|Valuation|32|- 17| |15| |
|Unrealized gains and losses|32|- 17| |15|-5|
|Technical clearing component| | | | | |
|Consolidated gains| | | | | |
|Consolidated losses| | | | | |
|VAD Gains|20| |-5|15| |
|VAD losses| | |5|5| |
|Book value|132| | |115|115|
|Amortized acquisition value|100| | |100|120|


|Delta VAD losses|= + OCI (H-GAAP) - VAD Gains (old)|
|---|---|
| |= 15 -20|
| |= - 5|
|Delta VAD gains|= VAD Gains (old) - OCI (H-GAAP)|
| |= 20 - 5|
| |= 5|

###### Example: Valuation Case 3

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Valuations > Example: Valuation Case 3 | L8 | trm08 p.135 | loio `b80cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b80cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 3:


OCI (H-GAAP) ≥ 0

VAD ≤ 0

Example Data:

VAD = -10 UNI

Unrealized losses (before valuation) = 20 UNI

Valuation at market price of 112 UNI, means unrealized gains of 12 UNI

|Position components|Values of position components before valuation|Valuation| | |Values of position components after valuation|P-GAAP Values| |
|---|---|---|---|---|---|---|---|
| |(1) write-up|(2) write-up|(3) VAD transfer posting| | | | |
|Purchase value|100| | | |100|90| |
|Valuation|- 20|20|12| |12| | |
|Unrealized gains and losses|- 20|20|12| |12|22| |
|Technical clearing component| | | | | | | |
|Consolidated gains| | | | | | | |
|Consolidated losses| | | | | | | |


|Position components|Values of position components before valuation|Valuation| | |Values of position components after valuation|P-GAAP Values| |
|---|---|---|---|---|---|---|---|
|VAD Gains| | | |-10|- 10| | |
|VAD losses|- 10| | |10| | | |
|Book value|80| | | |112|112| |
|Amortized acquisition value|100| | | |100|90| |


|Delta VAD losses|= - VAD losses (old)|
|---|---|
| |= - (-10)|
| |= 10|
|Delta VAD gains|= VAD losses (old)|
| |= - 10|

###### Example: Valuation Case 4

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Valuations > Example: Valuation Case 4 | L8 | trm08 p.136 | loio `bb0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bb0cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 4:


OCI (H-GAAP) < 0

VAD < 0

VAD ≤ OCI (H-GAAP)

Sample values

VAD = - 10 UNI

Unrealized gains (before valuation) = 15 UNI

Valuation at market price of 87 UNI, means unrealized losses of 13 UNI

|Position components|Values of position components before valuation|Valuation| | |Values of position components after valuation|P-GAAP Values| |
|---|---|---|---|---|---|---|---|
| |(1) Depreciation|(2) Depreciation|(3) VAD transfer posting| | | | |


|Position components|Values of position components before valuation|Valuation| | |Values of position components after valuation|P-GAAP Values| |
|---|---|---|---|---|---|---|---|
|Purchase value|100| | | |100|90| |
|Valuation|15|- 15|- 13| |- 13| | |
|Unrealized gains and losses|15|- 15|- 13| |- 13|- 3| |
|Technical clearing component| | | | | | | |
|Consolidated gains| | | | | | | |
|Consolidated losses| | | | | | | |
|VAD Gains|- 10| | |10| | | |
|VAD losses| | | |- 10|- 10| | |
|Book value|115| | | |87|87| |
|Amortized acquisition value|100| | | |100|90| |


|Delta VAD losses|= + VAD gains (old)|
|---|---|
| |= + (-10)|
| |= - 10|
|Delta VAD gains|= - VAD gains (old)|
| |= - (- 10)|
| |= 10|

###### Example: Valuation Case 5

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Valuations > Example: Valuation Case 5 | L8 | trm08 p.137 | loio `be0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/be0cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 5:


OCI (H-GAAP) < 0

VAD < 0

VAD > OCI (H-GAAP)

Example Data:

VAD = - 10 UNI

Unrealized gains (before valuation) = 15 UNI

Valuation at market price of 92 UNI, means unrealized losses of 8 UNI

|Position components|Values of position components before valuation|Valuation| | |Values of position components after valuation|P-GAAP Values| |
|---|---|---|---|---|---|---|---|
| |(1) Depreciation|(2) Depreciation|(3) VAD transfer posting| | | | |
|Purchase value|100| | | |100|90| |
|Valuation|15|- 15|- 8| |- 8| | |
|Unrealized gains and losses|15|- 15|- 8| |- 8|2| |
|Technical clearing component| | | | | | | |
|Consolidated gains| | | | | | | |
|Consolidated losses| | | | | | | |
|VAD Gains|- 10| | |8|-2| | |
|VAD losses| | | |- 8|- 8| | |
|Book value|115| | | |92|92| |
|Amortized acquisition value|100| | | |100|90| |


|Delta VAD losses|= + OCI (H-GAAP) - VAD losses (old)|
|---|---|
| |= -8 - 0|
| |= - 8|
|Delta VAD gains|= + VAD losses (old) - OCI (H-GAAP)|
| |= 0 - (- 8)|
| |= 8|

###### Example: Valuation Case 6

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Valuations > Example: Valuation Case 6 | L8 | trm08 p.139 | loio `c10cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c10cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 6:


OCI (H-GAAP) < 0

VAD ≥ 0

Example Data:

VAD = 20 UNI

Unrealized gains (before valuation) = 15 UNI

Valuation at market price of 92 UNI, means unrealized losses of 8 UNI

|Position components|Values before valuation|Valuation| | |Values after valuation|P-GAAP Values| |
|---|---|---|---|---|---|---|---|
| | |(1) Depreciation|(2) Depreciation|(3) VAD transfer posting| | | |
|Purchase value|100| | | |100|120| |
|Valuation|15|- 15|- 8| |- 8| | |
|Unrealized gains and losses|15|- 15|- 8| |- 8|- 28| |
|Technical clearing component| | | | | | | |
|Consolidated gains| | | | | | | |
|Consolidated losses| | | | | | | |
|VAD Gains|15| | |- 15| | | |
|VAD losses|5| | |15|20| | |
|Book value|115| | | |92|92| |
|Amortized acquisition value|100| | | |100|120| |


|Delta VAD losses|= + VAD gains (old)|
|---|---|
| |= 15|
|Delta VAD gains|= - VAD gains (old)|


| |= - 15|
|---|---|

###### Position Components for Adjustments with Position Outflows

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Position Outflows | L7 | trm08 p.140 | loio `c70cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c70cda531198434de10000000a174cb4.html?locale=en-US)

**Calculation of realized gains and losses for non-monetary positions**

With a sale (position outflow), the value adjustment must be adjusted in proportion (as with all other position components).

The following applies:

The clearing of VAD gains adjusts the realized gains

The clearing of VAD losses adjusts the realized losses.

**Caution:**

A clearing of VAD gains and VAD losses can be both positive and negative.

**Rules for calculating the components**

Clearing VAD = clearing VAD gains + clearing VAD losses

Realized gains and losses (P-GAAP) = realized gains and losses (H-GAAP) - clearing VAD

The splitting of the clearing VAD in clearing VAD gains and clearing VAD losses follows the following algorithm:

Case 1 Case 2 Case 3 Case 4 Case 5 Case 6

Realized profit and loss statement (H-GAAP) ≥ 0 Realized profit and loss statement (HGAAP) < 0

Clearing VAD > 0 Clearing VAD ≤ 0 Clearing VAD < 0 Clearing VAD ≥ 0

Clearing VAD ≤ realized profit and loss statement (HGAAP)

Clearing VAD > realized profit and loss statement (HGAAP)

Realized profit and loss statement (HGAAP) ≤ clearing VAD

Realized profit and loss statement (HGAAP) > clearing VAD

Clearing of position components

VAD Gains - Clearing VAD Realized profit and loss statement (HGAAP)

- Clearing VAD 0 - [clearing VAD realized profit and loss statement (HGAAP)]

0

VAD losses 0 - [clearing VAD realized profit and loss statement (HGAAP)]

0 - Clearing VAD - realized profit and loss statement (HGAAP)

- Clearing VAD

| |Case 1|Case 2|Case 3|Case 4|Case 5|Case 6|
|---|---|---|---|---|---|---|
|Calculation of Delta VADS (Flows)| | | | | | |
|VAD Gains|+ VAD losses (old) * R|+ realized P&L statement (HGAAP) - VAD gains (old) * R|+ VAD losses (old) * R|- VAD gains (old) * R|+ VAD losses (old) * R realized P&L statement (HGAAP)|- VAD gains (old) * R|
|VAD losses|- VAD losses (old) * R|+ VAD gains (old) * R realized P&L statement (HGAAP)|- VAD losses (old) * R|+ VAD gains (old) * R|+ realized P&L statement (HGAAP) - VAD losses (old) * R|+ VAD gains (old) * R|
| |Example|Example|Example|Example|Example|Example|


Used abbreviation:

R = ratio = outgoing part of position / total position before sale

**Calculation of realized gains and losses for monetary positions**

If you have define the indicator Amortized Value Adjustment for a position management procedure, the system executes the amortization in the following cases:

When valuating the position

With position inflows and outflows

For all other business transactions that change the amortized acquisition value (purchase value + capitalized costs + amortizations).

There is a one to one link between the amortization procedure (SAC/LAC) and the amortization (LAC) of the value adjustment. Without the amortization procedure, no clearing of the value adjustment takes place.

###### Example: Position Outflow Case 1

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Position Outflows > Example: Position Outflow Case 1 | L8 | trm08 p.141 | loio `9d0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9d0cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 1:


Realized profit and loss statement (H-GAAP) ≥ 0

Clearing VAD > 0

Clearing VAD ≤ realized profit and loss statement (H-GAAP)

Example Data:

VAD = 20 UNI

Unrealized Gains = 50 UNI

Sell half of position (R = 0,5)

Sales price = 62 UNI

Realized Gains = 12 UNI

Clearing VAD ≤ realized profit and loss statement (H-GAAP)

|Position Components|Values before position outflow|
|---|---|
|Purchase value|100|
|Valuation|50|
|Unrealized gains and losses|50|
|Technical clearing component| |
|Consolidated gains| |
|Consolidated losses| |
|VAD Gains|20|
|VAD losses| |
|Book value|150|
|Amortized acquisition value|100|


Through the sale of triggered flows to adjust position components:

|Position components|Flows| | | | | |
|---|---|---|---|---|---|---|
| |(1): Sale:|(2) Translation (no posting)|(3) Translation (no posting)|(4) Clearing Unrealized P&L statement against position|(5) Realized gains|(6) Clearing VAD gains|
|Purchase value| |- 50| | | | |
|Valuation| | |- 25| | | |
|Unrealized gains and losses| | | |- 25| | |
|Technical clearing components|- 62|50|25|- 25|12| |
|Consolidated gains| | | | | | |
|Consolidated losses| | | | | | |
|VAD Gains| | | | | |- 10|
|VAD losses| | | | | | |
|Book value| |- 50|- 25| | | |
|Amortized acquisition value| |- 50| | | | |


Results:

|Position Components|Values after position outflow|P-GAAP - Values|
|---|---|---|
|Purchase value|50|60|
|Valuation|25| |
|Unrealized gains and losses|25|15|
|Technical clearing component| | |
|Consolidated gains| | |
|Consolidated losses| | |
|VAD Gains|10|10|
|VAD losses| | |
|Book value|75|75|
|Amortized acquisition value|50|60|


|Clearing VAD|= VAD * R = 20 * 0,5 = 10|
|---|---|
|Delta VAD (losses)|= - VAD losses (old) * R = -0 * 0,5 = 0|
|Delta VAD (gains)|= + VAD losses (old) * R = 0 * 0,5 = 0|
|Clearing VAD gains|= - Clearing VAD = -10|
|Clearing VAD losses|= 0|

###### Example: Position Outflow Case 2

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Position Outflows > Example: Position Outflow Case 2 | L8 | trm08 p.143 | loio `cd0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd0cda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 2:


Realized profit and loss statement (H-GAAP) ≥ 0

Clearing VAD > 0

Clearing VAD > realized profit and loss statement (H-GAAP)

Example Data:

VAD = 20 UNI

Unrealized Gains = 50 UNI

Sell half of position => R = 0,5

Sales price = 58 UNI

Realized Gains = 8 UNI

Clearing VAD > realized profit and loss statement (H-GAAP)

|Position Components|Values before position outflow|
|---|---|
|Purchase value|100|
|Valuation|50|
|Unrealized gains and losses|50|
|Technical clearing component| |
|Consolidated gains| |
|Consolidated losses| |
|VAD Gains|20|
|VAD losses| |
|Book value|150|
|Amortized acquisition value|100|


Through the sale of triggered flows to adjust position components:

|Position components|Flows| | | | | | | |
|---|---|---|---|---|---|---|---|---|
| |(1)|(2)|(3)|(4)|(5)|(6)|(7)|(8)|
|Purchase value| |- 50| | | | | | |
|Valuation| | |- 25| | | | | |
|Unrealized gains and losses| | | |- 25| | | | |
|Technical clearing component|- 58|50|25|- 25|8| | | |
|Consolidated gains| | | | | | | | |
|Consolidated losses| | | | | | | | |
|VAD Gains| | | | | |- 2|- 8| |


|VAD losses| | | | | |2| |- 2|
|---|---|---|---|---|---|---|---|---|
|Book value| |- 50|- 25| | | | | |
|Amortized acquisition value| |- 50| | | | | | |


- (1): Sale:
- (2) Translation (no posting)
- (3) Translation (no posting)
- (4) Clearing of Unrealized P&L against position
- (5) Realized gains
- (6) transfer posting VAD
- (7) Clearing VAD gains
- (8) Clearing VAD losses


Results:

|Position Components|Book values after sale|Consolidation|
|---|---|---|
|Purchase value|50|60|
|Valuation|25| |
|Unrealized gains and losses|25|15|
|Technical clearing component| | |
|Consolidated gains| | |
|Consolidated losses| | |
|VAD Gains|10| |
|VAD losses| | |
|Book value|75|75|
|Amortized acquisition value|50|60|


|Clearing VAD|= VAD * R = 20 * 0,5 = 10|
|---|---|
|Delta VAD (losses)|= + VAD gains (old) * R - realized P&L statement (H-GAAP) = 20 * 0,5 - 8 = 2|


|Delta VAD (gains)|= + realized P&L statement (H-GAAP) - VAD gains (old) * R = 8 - 20 * 0,5 = - 2|
|---|---|
|Clearing VAD gains|= - realized profit and loss statement (H-GAAP) = - 8|
|Clearing VAD losses|= - [clearing VAD - realized profit and loss statement (H-GAAP)] = - [10 - 8] = - 2|

###### Example: Position Outflow Case 3

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Position Outflows > Example: Position Outflow Case 3 | L8 | trm08 p.146 | loio `9d0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9d0ada531198434de10000000a174cb4.html?locale=en-US)

**Basic Data Case 3:**

Realized profit and loss statement (H-GAAP) ≥ 0

Clearing VAD ≤ 0

**Example Data:**

VAD = - 10 UNI

Unrealized losses = 20 UNI

Sell half of position => R = 0,5

Sales price = 58 UNI

Realized Gains = 8 UNI

|Position Components|Values before position outflow|
|---|---|
|Purchase value|100|
|Valuation|- 20|
|Unrealized gains and losses|- 20|
|Technical clearing component| |
|Consolidated gains| |
|Consolidated losses| |
|VAD Gains| |
|VAD losses|- 10|
|Book value|80|
|Amortized acquisition value|100|


Through the sale of triggered flows to adjust position components:

|Position components|Flows| | | | | |
|---|---|---|---|---|---|---|
| |(1): Sale:|(2) Translation (no posting)|(3) Translation (no posting)|(4) Clearing unrealized P&L statement against position|(5) Realized gains|(6) Clearing VAD losses|
|Purchase value| |- 50| | | | |
|Valuation| | |10| | | |
|Unrealized gains and losses| | | |10| | |
|Technical clearing component|- 58|50|- 10|10|8| |
|Consolidated gains| | | | | | |
|Consolidated losses| | | | | | |
|VAD Gains| | | | | | |
|VAD losses| | | | | |5|
|Book value| |- 50|10| | | |
|Amortized acquisition value| |- 50| | | | |


Results:

|Position Components|Values after position outflow|P-GAAP - Values|
|---|---|---|
|Purchase value|50|45|
|Valuation|- 10| |
|Unrealized gains and losses|- 10|- 5|
|Technical clearing component| | |
|Consolidated gains| | |
|Consolidated losses| | |
|VAD Gains| | |
|VAD losses|- 5| |
|Book value|40|40|
|Amortized acquisition value|50|45|


Clearing VAD = VAD * R

| |= - 10 * 0,5 = - 5|
|---|---|
|Delta VAD (losses)|= - VAD losses (old) * R = - (- 10) * 0,5 = 5|
|Delta VAD (gains)|= + VAD losses (old) * R = - 10 * 0,5 = - 5|
|Clearing VAD gains|= - Clearing VAD = - (-5) = 5|
|Clearing VAD losses|= 0|

###### Example: Position Outflow Case 4

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Position Outflows > Example: Position Outflow Case 4 | L8 | trm08 p.148 | loio `b90dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b90dda531198434de10000000a174cb4.html?locale=en-US)

**Basic Data Case 1:**

Realized profit and loss statement (H-GAAP) < 0

Clearing VAD < 0

Realized profit and loss statement (H-GAAP) ≤ clearing VAD

**Example Data:**

VAD = -10 UNI

Unrealized losses = 18 UNI

Sell half of position (R = 0,5)

Sales price = 42 UNI

Realized loss = 8 UNI

|Position Components|Values before position outflow|
|---|---|
|Purchase value|100|
|Valuation|- 18|
|Unrealized gains and losses|- 18|
|Technical clearing component| |
|Consolidated gains| |
|Consolidated losses| |


|VAD Gains| |
|---|---|
|VAD losses|- 10|
|Book value|82|
|Amortized acquisition value|100|


Through the sale of triggered flows to adjust position components:

|Position components|Flows| | | | | |
|---|---|---|---|---|---|---|
| |(1): Sale:|(2) Translation (no posting)|(3) Translation (no posting)|(4) ClearingUnrealized P&L statement against position|(5) Realized loss|(6) Clearing VAD gains|
|Purchase value| |- 50| | | | |
|Valuation| | |9| | | |
|Unrealized gains and losses| | | |- 9| | |
|Technical clearing component|- 42|50|- 9|9|- 8| |
|Consolidated gains| | | | | | |
|Consolidated losses| | | | | | |
|VAD Gains| | | | | | |
|VAD losses| | | | | |5|
|Book value| |- 50|- 25| | | |
|Amortized acquisition value| |- 50| | | | |


Results:

|Position Components|Book values after sale|Consolidation|
|---|---|---|
|Purchase value|50|45|
|Valuation|- 9| |
|Unrealized gains and losses|- 9|- 4|
|Technical clearing component| | |
|Consolidated gains| | |
|Consolidated losses| | |


|VAD Gains| | |
|---|---|---|
|VAD losses|- 5| |
|Book value|41|41|
|Amortized acquisition value|50|45|


|Clearing VAD|= VAD * R = - 10 * 0,5 = - 5|
|---|---|
|Delta VAD (losses)|= + VAD gains (old) * R = 0 * 0,5 = 0|
|Delta VAD (gains)|= - VAD gains (old) * R = - 0 * 0,5 = 0|
|Clearing VAD gains|= 0|
|Clearing VAD losses|= - Clearing VAD = - (-5) = 5|

###### Example: Position Outflow Case 5

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Position Outflows > Example: Position Outflow Case 5 | L8 | trm08 p.150 | loio `c30ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c30ada531198434de10000000a174cb4.html?locale=en-US)

**Basic Data Case 5:**

Realized profit and loss statement (H-GAAP) < 0

Clearing VAD < 0

Realized profit and loss statement (H-GAAP) > clearing VAD

**Example Data:**

VAD = -10 UNI

Unrealized losses = 18 UNI

Sell half of position (R = 0,5)

Sales price = 48 UNI

Realized loss = 2 UNI

|Position Components|Values before position outflow|
|---|---|


|Purchase value|100|
|---|---|
|Valuation|- 18|
|Unrealized gains and losses|- 18|
|Technical clearing component| |
|Consolidated gains| |
|Consolidated losses| |
|VAD Gains| |
|VAD losses|- 10|
|Book value|82|
|Amortized acquisition value|100|


Through the sale of triggered flows to adjust position components:

|Position components|Flows| | | | | | | |
|---|---|---|---|---|---|---|---|---|
| |(1): Sale:|(2) Translation (no posting)|(3) Translation (no posting)|(4) ClearingUnrealized P&L statement against position|(5) Realized loss|(6) transfer posting VAD|(7) Clearing VAD losses|(8) Clearing VAD gains|
|Purchase value| |- 50| | | | | | |
|Valuation| | |9| | | | | |
|Unrealized gains and losses| | | |- 9| | | | |
|Technical clearing component|- 42|50|- 9|9|- 2| | | |
|Consolidated gains| | | | | | | | |
|Consolidated losses| | | | | | | | |
|VAD Gains| | | | | |- 3| |3|
|VAD losses| | | | | |3|2| |
|Book value| |- 50|9| | | | | |
|Amortized acquisition value| |- 50| | | | | | |


Results:

|Position Components|Values after position outflow|P-GAAP - Values|
|---|---|---|
|Purchase value|50|45|
|Valuation|- 9| |
|Unrealized gains and losses|- 9|- 4|
|Technical clearing component| | |
|Consolidated gains| | |
|Consolidated losses| | |
|VAD Gains| | |
|VAD losses|- 5| |
|Book value|41|41|
|Amortized acquisition value|50|45|


|Clearing VAD|= VAD * R = - 10 * 0,5 = - 5|
|---|---|
|Delta VAD (losses)|= + VAD gains (old) * R = 0 * 0,5 = 0|
|Delta VAD (gains)|= - VAD gains (old) * R = - 0 * 0,5 = 0|
|Clearing VAD gains|= - [clearing VAD - realized profit and loss statement (H-GAAP)] = - [-5 - (-3)] = 2|
|Clearing VAD losses|= - realized profit and loss statement (H-GAAP) = - (-3) = 3|

###### Example: Position Outflow Case 6

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Position Outflows > Example: Position Outflow Case 6 | L8 | trm08 p.152 | loio `930ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/930ada531198434de10000000a174cb4.html?locale=en-US)

**Basic Data Case 6:**

Realized profit and loss statement (H-GAAP) < 0

Clearing VAD ≥ 0

**Example Data:**

VAD = 10 UNI

Unrealized Gains = 20 UNI

Sell half of position (R = 0,5)

Sales price = 48 UNI

Realized loss = 2 UNI

|Position Components|Values before position outflow|
|---|---|
|Purchase value|100|
|Valuation|20|
|Unrealized gains and losses|20|
|Technical clearing component| |
|Consolidated gains| |
|Consolidated losses| |
|VAD Gains|20|
|VAD losses| |
|Book value|120|
|Amortized acquisition value|100|


Through the sale of triggered flows to adjust position components:

|Position components|Flows| | | | | | |
|---|---|---|---|---|---|---|---|
| |(1): Sale:|(2) Translation (no posting)|(3) Translation (no posting)|(4) ClearingUnrealized P&L statement against position|(5) Realized loss|(6) transfer posting VAD|(7) Clearing VAD losses|
|Purchase value| |- 50| | | | | |
|Valuation| | |- 10| | | | |
|Unrealized gains and losses| | | |- 10| | | |
|Technical clearing component|- 48|50|10|- 10|- 2| | |
|Consolidated gains| | | | | | | |


|Consolidated losses| | | | | | | |
|---|---|---|---|---|---|---|---|
|VAD Gains| | | | | |- 5| |
|VAD losses| | | | | |5|- 5|
|Book value| |- 50|- 10| | | | |
|Amortized acquisition value| |- 50| | | | | |


**Results:**

|Position Components|Values after position outflow|P-GAAP - Values|
|---|---|---|
|Purchase value|50|55|
|Valuation|10|5|
|Unrealized gains and losses|10|5|
|Technical clearing component| | |
|Consolidated gains| | |
|Consolidated losses| | |
|VAD Gains|5| |
|VAD losses| | |
|Book value|60|60|
|Amortized acquisition value|50|55|


|Clearing VAD|= VAD * R = 10 * 0,5 =5|
|---|---|
|Delta VAD (losses)|= + VAD gains (old) * R = 10 * 0,5 = 5|
|Delta VAD (gains)|= - VAD gains (old) * R = - 10 * 0,5 = - 5|
|Clearing VAD gains|= 0|
|Clearing VAD losses|= - Clearing VAD = - 5|

###### Position Components for Adjustments with Impairment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Impairment | L7 | trm08 p.155 | loio `ca0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ca0cda531198434de10000000a174cb4.html?locale=en-US)

The clearing of the value adjustment is based on the listed acquisition costs (P-GAAP)

The clearing of the value adjustment results from the gains and losses value adjustments:

Clearing value adjustment = clearing gains value adjustment + clearing losses value adjustment

**Caution:**

A clearing of gains and losses value adjustments can be both positive and negative.

**Rules for calculating the components**

The splitting of the value adjustment follows the algorithm below:

| |Case 1|Case 2a|Case 2b|Case 3|
|---|---|---|---|---|
| |VAD > 0| | |VAD < 0|
| |ImpV ≤ AC(H-GAAP) < AC(P-GAAP)|AC(H-GAAP) < ImpV <= AC(P-GAAP)| |ImpV < AC(P-GAAP) < AC(H-GAAP)|
| | |AC(P-GAAP) - ImpV ≤ VAD losses|AC(P-GAAP) - ImpV > VAD losses| |
|Clearing of position components| | | | |
|VAD Gains|- VAD gains|0|-((AC P-GAAP - ImpV) VAD losses)|- VAD gains|
|VAD losses|- VAD losses|- (AC(P-GAAP) - ImpV)|- VAD losses|- VAD losses|


Abbreviations:

|ImpV|Impairment amount|
|---|---|
|AC|Amortized costs|
|D|Ratio (decreasing part of the position)|
|VAD|Value Adjustment|


- Condition 1 : The splitting of the value adjustments gains and losses are correct before the impairment process.

Note: this condition is guaranteed via the derived business transactions automatically.

- Condition 2: the clearing of OCI (H-GAAP) occurs at the most by the impairment - value.



This represents a change of the clearing of OCI during the impairment valuation.

###### Example: Impairment Case 1

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Impairment > Example: Impairment Case 1 | L8 | trm08 p.155 | loio `800eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/800eda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 1:


VAD > 0

ImpV ≤ AC(H-GAAP) < AC(P-GAAP)

Example Data:

VAD = 20

Unrealized gains = 15

Impairment amount (ImpV) = 92

Transaction Manager Subledger

|Position components|Values before impairment|Impairment flows| | | |Values after Impairment|Values PGAAP|
|---|---|---|---|---|---|---|---|
| | |(1) ClearingUnrealized P&L statement against position|(2) Impairment (H-GAAP)|(3) Clearing ImpairmentVAD gains|(4) Clearing ImpairmentVAD losses| | |
|Purchase value|100| | | | |100|100|
|Valuation|15|- 15| | | | | |
|Unrealized gains and losses|15|- 15| | | | | |
|Impairment| | |- 8| | | |- 8|
|Consolidated gains| | | | | | | |
|Consolidated losses| | | | | | | |
|VAD gains|15| | |- 15| | | |
|VAD losses|5| | | |- 5| | |
|Book value|115|- 15|- 8| | |92|92|
|Amortized acquisition value|100| | | | |100|92|


|Clearing impairment VAD gains|= - VAD gains|
|---|---|
| |= - 15|
|Clearing impairment VAD losses|= - VAD losses|
| |= - 5|

###### Example: Impairment Case 2a

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Impairment > Example: Impairment Case 2a | L8 | trm08 p.156 | loio `ab0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ab0ada531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 2a:


VAD > 0

AC(H-GAAP) < ImpV <= AC(P-GAAP)

AC(P-GAAP) - ImpV ≤ VAD losses

Example Data:

VAD = 20

Unrealized gains = 15

Impairment amount (ImpV) = 118

Transaction Manager Subledger

|Position components|Values before impairment|Impairment flow|Values after Impairment|Values P-GAAP|
|---|---|---|---|---|
| | |(1) Ausgleich Impairment VAD Verluste| | |
|Purchase value|100| |100|118|
|Valuation|15| |15| |
|Unrealized gains and losses|15| |15| |
|Impairment| | | | |
|Consolidated gains| | | | |
|Consolidated losses| | | | |
|VAD Gains|15| |15| |
|VAD losses|5|- 2|3| |
|Book value|115| |115|118|
|Amortized acquisition value|100| |100|118|


|Clearing impairment VAD gains|= 0|
|---|---|
|Clearing impairment VAD losses|= - (AC P-GAAP - ImpV) = - (120 - 118) = - 2|

###### Example: Impairment Case 2b

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Impairment > Example: Impairment Case 2b | L8 | trm08 p.157 | loio `6d0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6d0dda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 2b:


VAD > 0

AC(H-GAAP) < ImpV <= AC(P-GAAP)

AC(P-GAAP) - ImpV > VAD losses

Example Data:

VAD = 20

Unrealized gains = 15

Impairment amount (ImpV) = 102

Transaction Manager Subledger

|Position components|Values before impairment|Impairment flows| | |Values after Impairment|Values P-GAAP|
|---|---|---|---|---|---|---|
| | |(1) ClearingUnrealized P&L statement against position|(2) Clearing ImpairmentVAD gains|(3) Clearing ImpairmentVAD losses| | |
|Purchase value|100| | | |100|102|
|Valuation|15|- 13| | |2| |
|Unrealized gains and losses|15|- 13| | |2| |
|Impairment| | | | | | |
|Consolidated gains| | | | | | |
|Consolidated losses| | | | | | |
|VAD Gains|15| |- 13| |2| |
|VAD losses|5| | |- 5| | |
|Book value|115|- 13| | |102|102|
|Amortized acquisition value|100| | | |100|102|


|Clearing impairment VAD gains|= -((AC P-GAAP - ImpV) - VAD losses) = - ((120 - 102) -5) = - 13|
|---|---|
|Clearing impairment VAD losses|= - VAD losses = - 5|

###### Example: Impairment Case 3

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Period-End Closing > Valuation > P-GAAP > Position Components for Adjustments with Impairment > Example: Impairment Case 3 | L8 | trm08 p.158 | loio `c10dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c10dda531198434de10000000a174cb4.html?locale=en-US)

- Basic Data Case 3:


VAD < 0

ImpV < AC(P-GAAP) < AC(H-GAAP)

Example Data:

VAD = - 10

• Unrealized losses = - 20

Impairment amount = 88

Transaction Manager Subledger

|Position components|Values before impairment|Impairment flows| | |Values after Impairment|Values P-GAAP|
|---|---|---|---|---|---|---|
| | |(1) ClearingUnrealized P&L statement against position|(2) Impairment (H-GAAP)|(3) Clearing ImpairmentVAD losses| | |
|Purchase value|100| | | |100|100|
|Valuation|- 20|20| | | | |
|Unrealized gains and losses|- 20|20| | | | |
|Impairment| | |- 12| |- 12|- 12|
|Consolidated gains| | | | | | |
|Consolidated losses| | | | | | |
|VAD Gains| | | | | | |
|VAD losses|- 10| | |10| | |
|Book value|80|20|- 12| |88|88|
|Amortized acquisition value|100| | | |100|100|


|Clearing impairment VAD gains|= - VAD gains|
|---|---|
| |= 0|
|Clearing impairment VAD losses|= - VAD losses|
| |= - (- 10) = 10|

