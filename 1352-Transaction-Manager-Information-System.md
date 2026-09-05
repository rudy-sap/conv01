# Transaction Manager > Information System - SAP TRM Knowledge Base (branch split)

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

##### Logical Database FTI_TR_POSITIONS

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Logical Database FTI_TR_POSITIONS | L4 | trm10 p.3 | loio `d66ac7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d66ac7533a661d4be10000000a174cb4.html?locale=en-US)

**Use**

You can use this logical database to evaluate positions in SAP Treasury and Risk Management on a given key date. This enables you to analyze all the key figures and characteristics that are relevant for accounting for the specified key date.

**Integration**

This logical database is used for InfoSets in the SAP Query application.

See also:

InfoSets for the Transaction Manager

**Features**

This logical database enables you to analyze all the Position Components for the evaluation key date.

**Example**

Acquisition value

Book value

Amortization

etc.

The following key date references are available:

Value date

The key date refers to the value date of the subledger positions.

Posting Date in the Document

The key date refers to the FI posting date.

**Note:**

Position evaluation usually occurs on only one key date.

If multiple individual key dates or key date intervals are selected using the multiple selection function, SAP Query determines the positions for each individual key date. The key figures used in the query are recalculated for each individual key date and displayed in a list. You can compare key dates for a defined period.

Based on this logic, multiple selections result in considerably longer runtimes, so the number of key dates to be evaluated should be kept as small as possible.

**Example**

Position evaluation on 05/31/2005

SAP Query interprets the key date as the position value date or posting date, depending on the selected key date reference. The position calculation is based on all business transactions up to and including 05/31/05. The system calculates the position on the

key date from these business transactions. Any business transactions after the key date are not included in the key date position calculation:

| |April 2005|May 2005|June 2005|July 2005|August 2005|
|---|---|---|---|---|---|
|Business transactions with value date / posting date <= 05/31/05 are included when calculating position with month-end May 2005.| | |Business transactions with value date / posting date > 05/31/05 are included when calculating position with month-end May 2005.| | |


Moreover, accounting regulations such as IAS or US GAAP prescribe that financial assets must be subdivided into different holding categories in the balance sheet. Within these categories, unrealized gains and losses resulting from valuations may need to be treated differently depending on how they affect profit/loss:

Affecting profit/loss: Unrealized gains or losses are posted directly to the profit/loss account.

Not affecting profit/loss: Unrealized gains or losses are initially posted to a revaluation reserve. Any opposing write-ups or write-downs or (partial) outflows must be cleared against this account before they are posted to the profit/loss account.

The FTI_LDB_TR_POSITIONS logical database enables you to make a distinction between valuation results that affect the profit/loss account and those that do not.

**Note:**

The FTI_LDB_TR_POSITIONS logical database enables cross-evaluations for SAP Treasury and Risk Management and CML ( Loans ). However, the key figures available in the area of CML are restricted to accounting-based basic key figures:

Acquisition value

Book value

Valuation

Amortization

If you require more information for your CML positions, you can use the FTI_LO_POSITIONS logical database instead. This database has a range of key figures and characteristics specific to CML.

**Currencies**

In structure LDB FTI_TR_POSITIONS, each key figure is offered in different currencies:

Position currency (PC)

Local currency (LC) / Valuation currency (VC)

You define the valuation currency for each combination of parallel valuation area and accounting code and determine the currency in which positions are managed for this combination. The valuation currency can therefore be regarded as the "local currency" of the valuation area within the accounting code.

Evaluation currency

The currency in which you run an evaluation. You can define your evaluation currency. The core calculation component uses the evaluation currency for analytical operations, such as costing, controlling, and risk analysis. The evaluation currency differs from the transaction currency and the display currency.

Example:

During the NPV analysis, the system determines the net preset value in the evaluation currency.

Display currency (DC)

If the display currency is different to the original currency, the currency is translated using the translation type specified at the start of the report. The default translation type is "001", with currency translation at the average rate and today as the key date . However, you can create and use your own translation type.

**Portfolio (Position)**

You can use this field to select positions that are defined using the following differentiation terms: valuation area, special valuation class, accounting code, ID number, and portfolio.

**Business partner (commitment)**

The business partner is interpreted differently depending on the contract type:

In the case of Loans (contract type 1), selection is made based on the main borrower.

In the case of Securities (contract type 2), selection is made based on the issuer.

For all other contract types, selection is made based on the counterparty.

**Interpretation of Leading Currency**

If you set this indicator, then in the case of swap transactions (forex and forward exchange transactions, swaps) the (default) logic of the pure transaction master data is not used to fill the following key figures. Instead, those key figures with the currency reference "position currency of incoming side" now carry the value of the leading currency side (with a positive '+' sign if this is also the incoming side of the transaction, and with a negative '-' sign if it is the outgoing side of the transaction) and the other way around.

Nominal value, incoming side in position currency of incoming side

Nominal value, outgoing side in position currency of outgoing side

Net present value, incoming side in position currency of incoming side

Net present value, outgoing side in position currency of outgoing side

And the respective fields in display currency and calculation currency

The indicator has no other effects, not even on the positive/negative sign for the net present value or other values.

**Exclude Planned Data**

Planned records are not taken into account if you set this indicator.

When a selection is made using the key date reference "posting date", the indicator is irrelevant as planned records are not taken into account in this case.

**Note:**

This indicator is not supported for loans in valuation area 001.

**Securities Account / Securities Account Group**

You can select by securities account/securities account group Note that a selection according to these characteristics is only possible if a position differentiation by securities account/securities account group has been defined in the relevant valuation areas. Only then are positions “tailored” to fit these characteristics and only then is a logical data selection possible.

Relationship between selection fields Securities Account and Securities Account Group

If securities account was selected as the only differentiation criteria in a valuation area, a selection based on securities account group will not return any positions. If you leave the securities account group field empty, the system gets the relevant positions. In the report display, the Securities Account Group field is not filled.

If securities account group was selected as the only differentiation criteria in a valuation area, a selection based on securities account will not return any positions. If you leave the securities account field empty, the system gets the relevant positions. In the report display, the Securities Account field is not filled.

If both securities account and securities account group are selected as differentiation criteria, selections are based on both the securities account and securities account group, however in this case you cannot carry out a cross-securities account valuation.

You often have a scenario in which one parallel valuation area only uses the securities account group as the differentiating criterion, and a second parallel valuation area only uses the securities account. If you want to evaluate a securities account group (as defined in the securities account master data) for both valuation areas, and restrict the selection for the securities account group accordingly, no positions are selected for the valuation area that is differentiated by securities account, and vice versa. For this reason there is an indicator, Interpretation of Securities Account Group , described below.

Interpretation of Securities Account Group indicator

If you select positions by securities account group for a valuation area that is only differentiated by securities account, the system selects the securities accounts assigned to this securities account group in the securities account master data.

In the report display, the otherwise empty Securities Account Group field is filled.

**Control Risk Management (NPV) Buffer**

You can use the logical database FTI_TR_LDB_POSITIONS to calculate risk key figures (such as NPV or duration) in real time. These calculations may be very time-consuming, depending on the scope of the position. You can therefore calculate the key figures in advance and transfer them to the market data buffer using batch planning (table FTI_MARKET_VALST).

Choose one of the following methods to determine the risk key figures:

Risk management data is recalculated.

The key figures are always recalculated. The terms may be very long.

Risk management data is read from the buffer.

The system first attempts to read the key figures from the market data buffer. If the system cannot find any values, the key figure is recalculated online.

Risk management data is read from the buffer limit.

The system first determines the number of selected position records. If this number exceeds the predefined limit, the system accesses the market data buffer. If the limit is not exceeded, the key figures are recalculated.

See Performance Functions for Reporting

**Remaining Term**

The remaining term lets you see the terms of the capital investments that belong to the position. The remaining term is computed as the difference between two dates, as specified on the selection screen.

Remaining term based on key date

The report computes the difference between the end of term of the financial product and the selected key date.

Remaining term based on today

The report computes the difference between the end of term of the financial product and the current date.

Remaining term based on reference date

Here, an additional date field is shown. The report computes the difference between the end of term of the financial product and the specified reference date.

Three characteristics are available in the logical database for the output of the remaining term:

Remaining term in days

Remaining term in months

Remaining term in years

**Historical Account Assignment Reference**

If you select this indicator, the system may access historical data when evaluations are made in the past, instead of reading the current account assignment reference. For example, if an account assignment reference transfer was posted in the past, the system displays the account assignment references and G/L accounts as per the respective key date.

**Summarize Results**

Summarizing Results using Characteristics

**Hide zero records**

If this indicator is set, the data records containing key figures selected in the report definition with a key date value of zero are excluded from the report output.

##### Logical Database FTI_TR_PERIODS

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Logical Database FTI_TR_PERIODS | L4 | trm10 p.8 | loio `d96ac7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d96ac7533a661d4be10000000a174cb4.html?locale=en-US)

**Use**

You can use this database to evaluate flows in the position management area of the Transaction Manager for a given period. This enables you to analyze position trends and revenues within the selected period, including positions at the start and end of the period, on a flexible basis.

**Integration**

SAP Query comprises InfoSets that are based on this logical database.

See also:

InfoSets for the Transaction Manager

**Prerequisites**

Customizing for the Information System in the Transaction Manager

**Features**

This logical database lets you link position and flow information. This enables you to analyze position trends within the selected period on a flexible basis. The system determines the value of each key figure both at the start and the end of the selection period (key date-based position information) and calculates the corresponding delta key figure indicating the change in the position (period-based flow information). Since both types of information appear together in one list, the list display is more complex.


Therefore, when defining queries, we recommend that you also define interim totals (using the relevant characteristics and characteristic combinations) and then restrict the display to these summarized levels.

The following key date references are available:

Position Value Date

The key date refers to the value date of the subledger positions.

Posting Date in the Document

The key date refers to the FI posting date.

Each key figure is offered in different currencies:

Position currency (PC)

Local currency (LC) / Valuation currency (VC)

You define the valuation currency for each combination of parallel valuation area and accounting code and determine the currency in which positions are managed for this combination. The valuation currency can therefore be regarded as the "local currency" of the valuation area within the accounting code.

Evaluation currency

The currency in which you run an evaluation. You can define your evaluation currency. The core calculation component uses the evaluation currency for analytical operations, such as costing, controlling, and risk analysis. The evaluation currency differs from the transaction currency and the display currency.

Example:

During the NPV analysis, the system determines the net preset value in the evaluation currency.

Display currency (DC)

If the display currency is different to the original currency, the currency is translated using the translation type specified at the start of the report. The default translation type is "001", with currency translation at the average rate and today as the key date . However, you can create and use your own translation type.


Example

Period Evaluation: 04/01/05 – 06/30/05

SAP Query interprets the key date as the position value date or the posting date, depending on the key date references selected from the screen.

| |March 2005|April 2005|May 2005|June 2005|July 2005| |
|---|---|---|---|---|---|---|
| | |Evaluation period:| | | | |


An opening balance is calculated on 03/31/05. All transactions that occurred before April 1 st are part of this opening balance.

| |March 2005|April 2005|May 2005|June 2005|July 2005| |
|---|---|---|---|---|---|---|
|Business transactions with value date/posting date < 04/01/05 are used to calculate the opening balance on 03/31/05.| | | | | | |


The evaluation includes any flows that change the position and which occurred within the defined selection period.

| |March 2005|April 2005|May 2005|June 2005|July 2005| |
|---|---|---|---|---|---|---|
| | |Business transactions that occur within the selection period with value date/posting date >= 04/01/05 <=06/30/05 and cause changes to the position. Display closing balance for 30.06.05.| | | | |


Business transactions after the end of this period are not included in the selection

| |March 2005|April 2005|May 2005|June 2005|July 2005| |
|---|---|---|---|---|---|---|
| | | | | |Business transactions with value date/posting date >= 07/01/05 are not relevant for the evaluation.| |


Portfolio (position)

You can use this field to select positions that are defined using the following differentiation terms: valuation area, special valuation class, accounting code, ID number, and portfolio.

Business partner (commitment)

The business partner is interpreted differently depending on the contract type:

In the case of loans (contract type 1), selection is made based on the main borrower.

In the case of securities (contract type 2), selection is made based on the issuer.

For all other contract types, selection is made based on the counterparty.

Exclude planned data indicator

Planned records are not taken into account if you set this indicator.

When a selection is made using the key date reference "posting date", the indicator is irrelevant as planned records are not taken into account in this case.


This indicator is not supported for loans in valuation area 001.

You can select by securities account/securities account group. Note that a selection according to these characteristics is only possible if a position differentiation by securities account/securities account group has been defined in the relevant valuation areas. Only then are positions “tailored” to fit these characteristics and only then is a logical data selection possible.

Relationship between selection fields Securities Account and Securities Account Group

If securities account was selected as the only differentiation criteria in a valuation area, a selection based on securities account group will not return any positions. If you leave the securities account group field empty, the system gets the relevant positions. In the report display, the Securities Account Group field is not filled.

If securities account group was selected as the only differentiation criteria in a valuation area, a selection based on securities account will not return any positions. If you leave the securities account field empty, the system gets the relevant positions. In the report display, the Securities Account field is not filled.

If both securities account and securities account group are selected as differentiation criteria, selections are based on both the securities account and securities account group , however in this case you cannot carry out a cross-securities account valuation.

You often have a scenario in which one parallel valuation area only uses the securities account group as the differentiating criterion, and a second parallel valuation area only uses the securities account. If you want to evaluate a securities account group (as defined in the securities account master data) for both valuation areas, and restrict the selection for the securities account group accordingly, no positions are selected for the valuation area that is differentiated by securities account, and vice versa. For this reason there is an indicator, Interpretation of Securities Account Group , described below.

Interpretation of Securities Account Group indicator

If you select positions by securities account group for a valuation area that is only differentiated by securities account, the system selects the securities accounts assigned to this securities account group in the securities account master data.

In the report display, the otherwise empty Securities Account Group field is filled.

Control Risk Management (NPV) Buffer

You can use the logical database FTI_TR_LDB_POSITIONS to calculate risk key figures (such as NPV or duration) in real time. These calculations may be very time-consuming, depending on the scope of the position. You can therefore calculate the key figures in advance and transfer them to the market data buffer using batch planning (table FTI_MARKET_VALST).

Choose one of the following methods to determine the risk key figures:

Risk management data is recalculated.

The key figures are always recalculated. The terms may be very long.

Risk management data is read from the buffer.

The system first attempts to read the key figures from the market data buffer. If the system cannot find any values, the key figure is recalculated online.

Risk management data is read from the buffer limit.

The system first determines the number of selected position records. If this number exceeds the predefined limit, the system accesses the market data buffer. If the limit is not exceeded, the key figures are recalculated.

See Performance Functions for Reporting

Remaining term

The remaining term lets you see the terms of the capital investments that belong to the position. The remaining term is computed as the difference between two dates, as specified on the selection screen.

Remaining term based on key date

The report computes the difference between the end of term of the financial product and the selected key date.

Remaining term based on today

The report computes the difference between the end of term of the financial product and the current date.

Remaining term based on reference date

Here, an additional date field is shown. The report computes the difference between the end of term of the financial product and the specified reference date.

Three characteristics are available in the logical database for the output of the remaining term:

Remaining term in days

Remaining term in months

Remaining term in years

Historical account assignment reference indicator

If you select this indicator, the system may access historical data when evaluations are made in the past, instead of reading the current account assignment reference. For example, if an account assignment reference transfer was posted in the past, the system displays the account assignment references and G/L accounts as per the respective key date.

Process Reversed Flows indicator (provided in the queries based on the logical database FTI_TR_PERIODS)

When evaluating positions according to posting date, flows that were posted and reversed within a period are not displayed. Reversed flows are displayed only once when the posting is made, and not when they are reversed.

When a business transaction is reversed and the posting status is changed in the subledger from "posted"(P) to "reversed"(R), a reversal document is generated in the general ledger in addition to the original document posted. In the case of a reversal with a different posting date, substantial time and effort is required to reconcile the general ledger and subledger.

**In this case, you can use the process reversed flows indicator to generate an artificial business transaction in the subledger by duplicating the original business transaction, for the period between the original document date and the different reversal date.**

[figure TRM10-F005]

The indicator determines the entries made in the affected fields:

The posting date field contains

the posting date of the TM flow for the original flow

the reversal date of the TM flow for the reversed flow

The position value date field contains the position value date common to both flows.

The G/L Account: Debit and G/L Account Credit fields contain the (identical) flow information (not as in the case of offsetting postings where credit and debit are swapped).

The delta book value fields in their respective currencies contain the value of the flow as if it were posted and not reversed.

The posting status of the flow field contains the indicator for both flows that this flow has been reversed from the view of the TM subledger.

The new ledger posting status field contains value 2 (reversed) for the reversal flow and value 3 (generated ledger posted) for the original flow.


The indicator for processing reversed flows is not supported for Loans ( CML ) in the operative valuation area 001.

Summarize results indicator

Summarizing Results using Characteristics

Hide zero records indicator

If this indicator is set, the data records containing key figures selected in the report definition with a key date value of zero are excluded from the report output.

Only positions with flows in period indicator

If the indicator is set, only the positions with flows in the selection period are selected and displayed.

###### Summarizing Results Using Characteristics

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Logical Database FTI_TR_PERIODS > Summarizing Results Using Characteristics | L5 | trm10 p.14 | loio `251ec7531dc61d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/251ec7531dc61d4be10000000a174cb4.html?locale=en-US)

**Problem**

If the logical database FTI_TR_PERIODS is used to generate period-based position trend lists, the information for a given time (positions) has to be adequately combined with information for a given period (flows) to enable position changes to be analyzed over time.

The logical database delivers the following information to allow position changes to be displayed effectively.

|Position Information|Opening position for key date (start of period minus 1 day)|
|---|---|
|Flow Information|Business transactions within the selection period that change the opening position, for example: Purchase|


| |Sale Transfer postings Valuations|
|---|---|
|Position Information|Closing position with key date period end|


Within the query list, each business transaction that changes the initial position is displayed in a separate line. If the evaluation period covers a long period, the resulting position trend lists can be very complex and difficult to interpret.

**Proposed Solution**

It may help to use a solution that displays each position with position changes in a single line. It may make sense to summarize the data with as many characteristics as possible to achieve results with maximum summarization and a minimum number of lines.

This can be done by setting the Summarize Results indicator on the selection screen. Individual flows generated by business transactions are no longer displayed if this indicator is set. Instead, the aggregated and summarized position changes are displayed in one line. For more information, see the F1 Help documentation for the indicator.

**Example**

Period Evaluation (Not Summarized)

Along with the opening and closing positions, all business transactions that affect the position are also displayed.

[figure TRM10-F007 - Along with the opening and closing positions, all business transactions that affect the position are also displayed.]

Period Evaluation (Not Summarized)

Period Evaluation (Summarized)

Only one line with position changes is displayed per position:

[figure TRM10-F008 - Period Evaluation (Summarized)]

Period Evaluation (Summarized)

**How Is Summarization Done?**

In general, the data is summarized on the basis of all characteristics that do not appear in the query definition. These characteristics are excluded from the summarization because they are selected explicitly for display in the query definition. The system aggregates the data using all remaining characteristics.

**Example**

If the Position Value Data field is used in the query definition, it is then excluded from summarization.

|Company Code|ID Number|Position Currency|Position Value Date|Update Type|Name of Update Type|
|---|---|---|---|---|---|
|CFM1|100000|EUR|06.09.2002|SE1000|Purchase|
|CFM1|100000|EUR|12.09.2002|SE1000|Purchase|


The query delivers the following result:

|Company Code|ID Number|Position Currency|Position Value Date|Update Type|Name of Update Type|Delta No. of Units|Delta Book Value|
|---|---|---|---|---|---|---|---|
|CFM1|100000|EUR|06.09.2002|SE1000|Purchase|1000|10.000,00|
|CFM1|100000|EUR|12.09.2002|SE1000|Purchase|2000|20.000,00|


If the Position Value Date field is removed from the query definition, the system can use this field for summarization. The result of the query is then a single result line:

|Company Code|ID Number|Position Currency|Update Type|Name of Update Type|Delta No. of Units|Delta Book Value|
|---|---|---|---|---|---|---|
|CFM1|100000|EUR|SE1000|Purchase|3000|30.000,00|


**Note:**

This summarization logic applies to all characteristics. It is valid for positions as well as position changes. This means that you can use the summarization logic for position queries, that is, queries based on the logical database FTI_TR_POSITION.

Example:

To perform a cross-company-code position analysis for your book values in each securities account, you can define a query consisting of the characteristics Company Code and Securities Account and the key figure book value. If you have set the Summarize Results indicator, the display contains exactly one line per securities account, that is, exactly one book value.

Unless the Summarize Results indicator is set, you will get a separate line for each ID number with a position in a securities account.

The summarization aggregates the key figures accordingly. Be aware that the results might be incorrect in the case of certain key figures (such as the key figure Interest Rate). In addition, the summarization cannot correctly display alternative aggregating functions with SAP Query (such as the Average Is Calculated function). To evaluate key figures with more complex aggregation functions, you need to use drill-down reporting rather than SAP Query to add the characteristics for which the key figure does not aggregate trivially. This prevents summarization from being carried out (incorrectly) using these characteristics. The Display Report Type transaction (TRMS) provides you with an overview of the key figures with complex aggregation behavior.

##### Logical Database FTI_TR_PL_CF

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Logical Database FTI_TR_PL_CF | L4 | trm10 p.17 | loio `abb1c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/abb1c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

You can use the FTI_TR_PL_CF logical database (LDB) to evaluate revenues and maturities within a given period. This enables you to analyze all the revenues for the respective due date or period.


The FTI_TR_PL_CF logical database is part of LDB FTI_TR_PERIODS that was put together specifically to achieve better performance in profit/loss reporting.

**Integration**

This LDB is used for InfoSets in the SAP Query application.

See also:

InfoSets for the Transaction Manager

**Prerequisites**

You need to make your profit/loss Customizing settings.

See also:

Customizing for the Information System in the Transaction Manager

**Features**

Assign Revenues to the Positions

In position management, you can create positions according to various criteria. In the securities module, for example, you can specify whether positions should be created at the level of securities account, securities account group, portfolio, or lot (single position). The corresponding revenues therefore relate to different calculation bases.

The logical database FTI_TR_PL_CF ensures that the revenues in position management are assigned correctly to the respective positions.

You can use this field to select positions that are defined using the following differentiation terms: valuation area, special valuation class, accounting code, ID number, and portfolio.

Relationship between selection fields Securities Account and Securities Account Group

If securities account was selected as the only differentiation criteria in a valuation area, a selection based on securities account group will not return any positions. If you leave the securities account group field empty, the system gets the relevant positions. In the report display, the Securities Account Group field is not filled.

If securities account group was selected as the only differentiation criteria in a valuation area, a selection based on securities account will not return any positions. If you leave the securities account field empty, the system gets the relevant positions. In the report display, the Securities Account field is not filled.

If both securities account and securities account group are selected as differentiation criteria, selections are based on both the securities account and securities account group , however in this case you cannot carry out a cross-securities account valuation.

You often have a scenario in which one parallel valuation area only uses the securities account group as the differentiating criterion, and a second parallel valuation area only uses the securities account. If you want to evaluate a securities account group (as defined in the securities account master data) for both valuation areas, and restrict the selection for the securities account group accordingly, no positions are selected for the valuation area that is differentiated by securities account, and vice versa. For this reason there is an indicator, Interpretation of Securities Account Group , described below.

If you select positions by securities account group for a valuation area that is only differentiated by securities account, the system selects the securities accounts assigned to this securities account group in the securities account master data.

In the report display, the otherwise empty Securities Account Group field is filled.

Remaining term

The remaining term lets you see the terms of the capital investments that belong to the position. The remaining term is computed as the difference between two dates, as specified on the selection screen.

Remaining term based on key date

The report computes the difference between the end of term of the financial product and the selected key date.

Remaining term based on today

The report computes the difference between the end of term of the financial product and the current date.

Remaining term based on reference date

Here, an additional date field is shown. The report computes the difference between the end of term of the financial product and the specified reference date.

Three characteristics are available in the logical database for the output of the remaining term:

Remaining term in days

Remaining term in months

Remaining term in years

Historical account assignment reference indicator

If you select this indicator, the system may access historical data when evaluations are made in the past, instead of reading the current account assignment reference. For example, if an account assignment reference transfer was posted in the past, the system displays the account assignment references and G/L accounts as per the respective key date.

Summarize results indicator

Summarizing Results using Characteristics

Hide zero records indicator

If this indicator is set, the data records containing key figures selected in the report definition with a key date value of zero are excluded from the report output.

Only positions with flows in period indicator

If the indicator is set, only the positions with flows in the selection period are selected and displayed.

##### Logical Database FTI_TR_CASH_FLOWS

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Logical Database FTI_TR_CASH_FLOWS | L4 | trm10 p.19 | loio `df6ac7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/df6ac7533a661d4be10000000a174cb4.html?locale=en-US)

**Use**

The FTI_TR_CASH_FLOWS logical database (LDB) is used to evaluate payments in the Transaction Manager over a given period.

**Integration**

There are InfoSets in the SAP Query application that are based on this LDB.

See also:

InfoSets for the Transaction Manager

**Prerequisites**

You need to make your payment Customizing settings.

See also:

Customizing for the Information System in the Transaction Manager

**Features**

You can flexibly analyze payment flows from transaction management within a selected period.

This gives you a planning basis indicating which flows will become due in the course of any evaluation period in the future. You can distinguish between flows that affect positions (interest, interest capitalization) and those which affect profit/loss (nominal interest, dividends, and so on).

Evaluations can be made as follows:

[figure TRM10-F010 - Portfolio (position)]

Portfolio (position)

You can use this field to select positions that are defined using the following differentiation terms: valuation area, special valuation class, accounting code, ID number, and portfolio.

You can select by securities account/securities account group. Note that a selection according to these characteristics is only possible if a position differentiation by securities account/securities account group has been defined in the relevant valuation areas. Only then are positions “tailored” to fit these characteristics and only then is a logical data selection possible.

Relationship between selection fields Securities Account and Securities Account Group

If securities account was selected as the only differentiation criteria in a valuation area, a selection based on securities account group will not return any positions. If you leave the securities account group field empty, the system gets the relevant positions. In the report display, the Securities Account Group field is not filled.

If securities account group was selected as the only differentiation criteria in a valuation area, a selection based on securities account will not return any positions. If you leave the securities account field empty, the system gets the relevant positions. In the report display, the Securities Account field is not filled.

If both securities account and securities account group are selected as differentiation criteria, selections are based on both the securities account and securities account group , however in this case you cannot carry out a crosssecurities account valuation.

You often have a scenario in which one parallel valuation area only uses the securities account group as the differentiating criterion, and a second parallel valuation area only uses the securities account. If you want to evaluate a securities account group (as defined in the securities account master data) for both valuation areas, and restrict the selection for the securities account group accordingly, no positions are selected for the valuation area that is differentiated by securities account, and vice versa. For this reason there is an indicator, Interpretation of Securities Account Group , described below.

Interpretation of Securities Account Group indicator

If you select positions by securities account group for a valuation area that is only differentiated by securities account, the system selects the securities accounts assigned to this securities account group in the securities account master data.

In the report display, the otherwise empty Securities Account Group field is filled.

Remaining term

The remaining term lets you see the terms of the capital investments that belong to the position. The remaining term is computed as the difference between two dates, as specified on the selection screen.

Remaining term based on key date

The report computes the difference between the end of term of the financial product and the selected key date.

Remaining term based on today

The report computes the difference between the end of term of the financial product and the current date.

Remaining term based on reference date

Here, an additional date field is shown. The report computes the difference between the end of term of the financial product and the specified reference date.

Three characteristics are available in the logical database for the output of the remaining term:

Remaining term in days

Remaining term in months

Remaining term in years

Summarize results indicator

Summarizing Results using Characteristics

Hide zero records indicator

If this indicator is set, the data records containing key figures selected in the report definition with a key date value of zero are excluded from the report output.

##### Logical Database FTI_TR_DEALS

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Logical Database FTI_TR_DEALS | L4 | trm10 p.21 | loio `e56ac7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e56ac7533a661d4be10000000a174cb4.html?locale=en-US)

**Use**

The FTI_TR_DEALS logical database is used to evaluate financial transactions in SAP Treasury and Risk Management on a given key date. It focuses on evaluating data that originates from transaction management.

**Integration**

This LDB is used for InfoSets in the SAP Query application.

See also:

InfoSets for the Transaction Manager

**Features**

In addition to the basic transaction data, the logical database also evaluates a range of detailed information:

Transaction flows

Conditions

Formulas used in the conditions

Interest rate adjustment data

Payment data (payment details)

In the case of options, the data for the underlying and its flows

Key figures (including sensitive key figures)

The logical database FTI_TR_DEALS does not have a flat structure, but is rather hierarchically structured according to individual areas. The structure maps the foreign key relationships that exist in the underlying tables in the SAP system.

You can display many risk key figures (for the NPV, duration, or option, for example) that provide an integrated view of all the transaction data.

Evaluations based on LDB FTI_TR_DEALS are for a given date, in which the key date always refers to the position value date of the financial transaction. The system also determines the transaction status that is effective on the key date.

The key date-based selection takes into account the transaction activity effective on the key date as well as the start and end of term of a financial transaction. The flows and conditions valid for the relevant activity are selected. This type of selection is particularly relevant for OTC transactions that create the position. Listed transactions (transactions for securities, futures and listed options) do not have a term end. Transactions selected according to key date cannot provide "positions" for the valid transactions. For these types of transactions, it is useful to limit by the closing date. Due to the different characteristics of OTC transactions that create a position (with an end of term) and listed transactions (without an end of term) you should avoid combined reporting.

The key date also determines certain time-based attributes such as the current valid reference interest rate or the next fixing date. The net present value and sensitive key figures are also calculated on the key date.

You can make your selections on the basis of reference categories that reference financial transactions for different purposes.

These may include foreign exchange swaps, foreign exchange rollovers, or mirror transactions. The new 'ICH' reference category refers to issue positions and manually linked interest rate hedge transactions (such as interest rate swaps).

If you select the ICH reference category, the following special function is activated in the logical database:

In addition to selecting the financial transactions, the system also selects the corresponding class positions in the securities account. This provides you with an overview of the current securities issues and their hedge transactions.

Indicator Split Syndicate

If you set the indicator, all drawing objects (drawing transactions) in syndicated facilities are broken down (split) according to the participant behind it.

Indicator Generate Duplicate-Sided Transactions

If you leave the initial indicator blank, each transaction is displayed in reporting for the logical database as a record with the keys company code and transaction . A series of key figures is available in three versions with three currency references.

Key Figure

Key Figure Incoming Side

Key Figure Outgoing Side

An example of a key figure in three variants is the "nominal value". For all exchange transactions (swaps, FX, FX forward transactions) both side references (“key figure incoming side" and "key figure outgoing side") are filled. The key figure that does not explicitly reference a side remains empty. However, for all other non-exchange transactions, the key figures without an explicit side reference are filled.

If the indicator has been set , however, the following logic applies to exchange transactions (swaps, FX, FX forward transactions):

A record with the keys company code,transaction , and side , is generated for each side of the transaction (incoming and outgoing).

Key figures that reference a side are mapped in the key figure without an explicit side reference in which the following applies:

the "side" key is filled according to the reference to the side.

the amounts of the outgoing side with a change to the plus/minus sign are mapped to the amount that is in the key figure without explicit side references.

Key figures that cannot be assigned to a side are sometimes displayed in a third record with “no side”.

The Interpretation of Leading Currency indicator is inactive and therefore cannot be set.

Interpretation of leading currency indicator

If you set this indicator, then in the case of swap transactions (forex and forward exchange transactions, swaps) the (default) logic of the pure transaction master data is not used to fill the following key figures. Instead, those key figures with the currency reference "position currency of incoming side" now carry the value of the leading currency side (with a positive '+' sign if this is also the incoming side of the transaction, and with a negative '-' sign if it is the outgoing side of the transaction) and the other way around.

Nominal value, incoming side in position currency of incoming side

Nominal value, outgoing side in position currency of outgoing side

Net present value, incoming side in position currency of incoming side

Net present value, outgoing side in position currency of outgoing side

And the respective fields in display currency and calculation currency

The indicator has no other effects, not even on the positive/negative sign for the net present value or other values.

##### InfoSets for the Transaction Manager

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > InfoSets for the Transaction Manager | L4 | trm10 p.23 | loio `52fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/52fbc5536a51204be10000000a174cb4.html?locale=en-US)

These are special views of data sources. In other words, InfoSets specify which fields from a data source can be analyzed in queries.

InfoSets are based on logical databases. When you create an InfoSet you can select a logical database for supplying data. The number of fields in a logical database can sometimes be very high. You can moderate this by grouping fields into logical units or field groups.

**Example:**

Example

The logical database FTI_TR_POSITIONS contains a range of characteristics, attributes, and key figures, that are relevant for evaluating positions. Only one position InfoSet can be defined on the basis of this logical database. The InfoSet contains attributes and key figures that are relevant for evaluating this position. All the other fields in the logical database that are not relevant for position evaluation are not assigned to the InfoSet. When creating a query, you can only use the fields that were selected in the InfoSet.

You can assign InfoSets to different user groups. This enables the system administrator to control the extent to which individual departments or users can run evaluations using SAP Query. Each end user therefore has access to a certain selection of InfoSets that are relevant for his or her field of work (as defined by the user group).

See also:

For general information about InfoSets, see InfoSets in the SAP Query Documentation.

Additional Information for InfoSets

|Underlying Logical Database|InfoSet|
|---|---|
|FTI_TR_POSITIONS|/SAPQUERY/CFM_POSITIONS CFM - Positions|
| |/SAPQUERY/CFM_ISSUE_POS CFM - Issue positions|
| |/SAPQUERY/CFM_ABS_POS CFM - ABS MBS Positions|
| |/SAPQUERY/CFM_POS_04 CFM - Positions|
| |/SAPQUERY/CFM_POS_05 CFM - Positions|
| |/SAPQUERY/CFM_POS_06 CFM - Positions|
| |/SAPQUERY/CFM_POS_11 CFM – Postions – Simulated valuation|
| |/SAPQUERY/CFM_POS_12 CFM - Positions|
|FTI_TR_PERIODS|/SAPQUERY/CFM_PERIODS CFM - Position trend|
|FTI_TR_PL_CF|/SAPQUERY/CFM_REVENUE CFM - Revenues|
| |/SAPQUERY/CFM_REV_FCAST CFM - Revenue Forecast|
|FTI_TR_CASH_FLOWS|/SAPQUERY/CFM_MATUR_CF CFM – Due dates (payment view)|
|FTI_TR_DEALS|/SAPQUERY/CFM_ISSUE CFM - Transactions|

###### Additional Information for InfoSets

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > InfoSets for the Transaction Manager > Additional Information for InfoSets | L5 | trm10 p.24 | loio `d36ac7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d36ac7533a661d4be10000000a174cb4.html?locale=en-US)

The logical databases provide you with a large number of fields. An InfoSet not only lets you reduce or groups fields into useful units, but it also lets you enlarge the pool of available fields to obtain additional information.

Additional tables

Using additional tables you can link DDIC tables to the logical database. However, this is only possible if you can link using foreign keys.


If you require characteristics from the central master data table BUT000 in addition to the business partner attributes provided in the FTI_TR_POSITIONS logical database, you can use the common key "partner number" (PARTNR) and a table join to link the logical database to the table. All the fields in table BUT000 are then available for evaluation purposes.

Additional structures

Additional fields

If you require individual fields in a table, you should consider system performance by defining additional fields individually and then make field entries using a separate selection logic. You will require additional fields if you want to output information that is calculated on the basis of original logical database fields.


The InfoSet CFM_POSITION was created on the basis of the FTI_LDB_TR_POSITIONS logical database. The InfoSet has been enlarged by the following six additional fields that can be calculated on the basis of existing key figures (fields).

Hidden reserve

Write-down requirement

Pending gains

Pending losses

Security valuation, affecting profit/loss

FX valuation, affecting profit/loss

Market value in local currency

This information can be useful for various query evaluations.

###### InfoSet /SAPQUERY/CFM_REVENUE

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > InfoSets for the Transaction Manager > InfoSet /SAPQUERY/CFM_REVENUE | L5 | trm10 p.25 | loio `a8b1c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a8b1c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

You can use the CFM_REVENUE InfoSet to evaluate revenues earned within a given period. This enables you to analyze all the revenues for the respective due date or period.

Evaluations can be generated with the CFM_REVENUE InfoSet in the following form:

[figure TRM10-F013]

**Prerequisites**

Customizing for the Information System in the Transaction Manager

**Features**

This InfoSet is based on the FTI_TR_PL_CF logical database so that the same fields are available in both.

Additional fields

You can display all the expenses and revenues that are classified by profit/loss types in Customizing in separate columns. Three additional fields have been defined for each relevant profit/loss type (two additional fields for FX profit/loss types):

Profit/loss in position currency

Profit/loss in local currency

Profit/loss in display currency

Entries are made in the fields using GET custom coding. Choose Goto Coding GET. The code analyzes the respective profit/loss type for the individual flows and assigns it to the corresponding additional fields.

**Example:**

If the flow is assigned to P/L type 310 , the net income amount is assigned to the additional field defined for this purpose using the GET custom coding. The defined additional fields can then be used for the query definition. This enables a detailed analysis of revenues/expenses.

Example:

Expenses and revenues are assigned to the corresponding profit and loss key figures, depending on the profit/loss type assigned to each update type. In this example, the realized price gains, achieved at the time of outflow are assigned to the "realized gains securities LC / P/L C" key figures. All other revenues are displayed in the same way in separate columns.

|Product Type|P/L Type|ID Number|Due on:|Total Realized Gains Securities LC|LC|Total Realized Gains Securities P/L C|P/L C|
|---|---|---|---|---|---|---|---|
|Fixed interest sec.|Realized security price gains|444444|10/01/02|46,016.27|EUR|90,0000.00|USD|


|Product Type|P/L Type|ID Number|Due on:|Total Realized Gains Securities LC|LC|Total Realized Gains Securities P/L C|P/L C|
|---|---|---|---|---|---|---|---|
|Zero bonds|Realized security price gains|8548547|10/24/02|9,160,082.37|EUR|17,915,563.91|USD|
| | | | | | | | |


**Note:**

These settings apply to the sample Customizing settings delivered with the system. If you require different settings for the profit/loss types, the GET custom coding has to be adjusted accordingly.

**Activities**

To edit the InfoSet, choose Transaction Manager Information System Tools SAP Query MaintainInfoSets.

###### InfoSet /SAPQUERY/CFM_REV_FCAST

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > InfoSets for the Transaction Manager > InfoSet /SAPQUERY/CFM_REV_FCAST | L5 | trm10 p.27 | loio `dc6ac7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dc6ac7533a661d4be10000000a174cb4.html?locale=en-US)

**Use**

You can use the InfoSet /SAPQUERY/CFM_REV_FCAST to generate complex revenue forecasts and assign revenues to the respective due date or period. This gives you a basis for planning the inflows and outflows that will affect profit and loss in the course of any evaluation period in the future.

Evaluations can be generated in the following form:

[figure TRM10-F014 - Evaluations can be generated in the following form:]

**Prerequisites**

Customizing for the Information System in the Transaction Manager

**Features**

The InfoSets /SAPQUERY/CFM_REV_FCAST and CFM_REVENUE are both based on the FTI_TR_PL_CF logical database. Whilst the InfoSet CFM_REVENUE concentrates on analyzing the individual profit and loss types (defined in Customizing) in as much detail as possible, the main focus is on when the individual revenues become due within the selection period. In

this case, the system analyzes the individual flows and assigns them to the relevant year/quarter/month on the basis of the due date, and starting at the beginning of the specified selection period.

Additional fields

You can use the additional fields to display revenues and expenses in separate columns.

Entries are made in the fields using GET custom coding. Choose Goto Coding GET.

**Example**

The defined additional fields are filled by GET custom coding and can be used for the query definition. This enables a detailed expense/revenue forecast.

|Product Type|P/L Type|Security ID number|Total 2002|Total 2003|Total 2004|
|---|---|---|---|---|---|
|Fixed-interest sec.|Amortization|8.25% Deutsche Postbank|842.27-|0|0|
| | |8.25% Dt.Genoss.Hyp.Bank|11,465.47-|0|0|
| | |8.25% Eurohypo AG|14,231.76|0|0|
| | |8.25% Kreditanst.f.Wiederaufbau|918.54|0|0|
| | |8.25% Landwirtschaftl. Rentenbank|8,671.99-|0|0|
| | |Vivendi Environnement EO-Medium..|1,807.96|0|0|
| |Nominal Interest|3.25% Dt.Hypo Hyp.Pfbr.|0|1,462,500.00|0|
| | | |0|0|1,458,504.10|
| | |4.50% Bundesrep.Deutschl.|0|3,150,000.00|0|
| | | | | | |


**Activities**

To edit the InfoSet, choose Transaction Manager Information System Tools SAP Query MaintainInfoSets.

###### InfoSet /SAPQUERY/CFM_MATUR_CF

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > InfoSets for the Transaction Manager > InfoSet /SAPQUERY/CFM_MATUR_CF | L5 | trm10 p.28 | loio `e26ac7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e26ac7533a661d4be10000000a174cb4.html?locale=en-US)

**Use**

You can use the InfoSet CFM_MATUR_CF to analyze cash flows for a given due date or period. This gives you a planning basis indicating which flows will become due in the course of any evaluation period in the future. You can distinguish between flows that affect positions (interest, interest capitalization) and those which affect profit/loss (nominal interest, dividends, and so on).

Evaluations can be generated with the CFM_MATUR_CF InfoSet in the following form:

[figure TRM10-F015]

**Prerequisites**

Customizing for the Information System in the Transaction Manager

**Features**

The InfoSet is based on the FTI_TR_CASH_FLOWS logical database.

Additional fields

You could use CFM_MATUR_CF, for example, to analyze when flows will mature over the next four quarters and the next five years, starting at the beginning of the specified selection period.


Example: The selection period is 06/01/02 – 12/31/07. The flows are assigned to the following columns according to their due dates:

- Quarter I – 2002

- Quarter II – 2002

- Quarter III – 2002

- Quarter IV – 2002


- Year 2002

- Year 2003

- Year 2004

- Year 2005

- Year 2006

- Year 2007


An additional field, which is filled with the relevant payment amount using GET custom coding, is defined for each of these required columns: Choose Goto Coding GET.

An additional field is defined for the column heading. The column heading is dynamically determined by means of these additional fields in the query definition.

Fields with the prefix T are used to dynamically fill the column headings for the quarter or year entries. Entries are made in the additional fields using GET PL custom coding. Choose Goto Coding GET PL

The defined additional fields are filled by custom coding and can be used to define queries. This enables a detailed due-date analysis.

**Activities**

To edit the InfoSet, choose Transaction Manager Information System Tools SAP Query MaintainInfoSets.

##### Standard Queries for the Transaction Manager

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Standard Queries for the Transaction Manager | L4 | trm10 p.30 | loio `16fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/16fbc5536a51204be10000000a174cb4.html?locale=en-US)

SAP Query supports a wide range of options for defining reports (queries) and creating different report types, such as basic lists, statistics and ranked lists. Reports (queries) are simple to create. By selecting an InfoSet, you can specify which fields in the query you require for evaluations.

Several sample standard queries have been defined based on the InfoSets for the Transaction Manager. You can use these standard queries:

For immediate execution as they are

As templates for your own queries

You can use the queries delivered with the system for creating your own queries, or add further characteristics and key figures to reflect your own requirements.

However, you can only copy queries if you have change authorization.

You can copy all queries within a user group. Queries from other user groups can only be copied if the InfoSet used to define the query is assigned to both user groups.

The standard queries are located in the report structure of the Transaction Manager Information System as well as in transaction SAP Query: Start Queries (SQ00) under the user group /SAPQUERY/T1 = Queries for the TRM area.

Evaluation of positions for a given key date

|Query|Technical Name|Assigned InfoSet|Logical Database|
|---|---|---|---|
|Position Overview|CFM_POS_1|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|IAS Classification|CFM_POS_2|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Rating Analysis|CFM_POS_4|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Total Commitment|CFM_POS_12|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Country/Region Analysis|CFM_POS_5|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Accounting Overview|CFM_POS_08|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Simulated Valuation|CFM_POS_11|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Remaining Term Statistics|CFM_POS_06|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Share of Position|CFM_POS_07|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|TOP 5 – Security Items (Market Value View)|CFM_POS_09|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|
|Currency Analysis|CFM_POS_10|/SAPQUERY/CFM_POSITIONS|FTI_TR_POSITIONS|


|Query|Technical Name|Assigned InfoSet|Logical Database|
|---|---|---|---|
|Issue Position|CFM_POS_13|/SAPQUERY/CFM_ISSUE_POS|FTI_TR_POSITIONS|
|ABS MBS Positions|CFM_POS_14|/SAPQUERY/CFM_ABSMBS_POS|FTI_TR_POSITIONS|


Evaluation of flows/position trend (within a period)

|Query|Technical Name|Assigned InfoSet|Logical Database|
|---|---|---|---|
|Book Value/OCI Trend|CFM_PER_03|/SAPQUERY/CFM_PERIODS|FTI_TR_PERIODS|
|Position Trend|CFM_PER_02|/SAPQUERY/CFM_PERIODS|FTI_TR_PERIODS|
|Due Date Grid|CFM_MAT_01|/SAPQUERY/CFM_MATUR_CF|FTI_TR_CASH_FLOWS|


Evaluation of revenues/turnovers/flows due (within a period)

|Query|Technical Name|Assigned InfoSet|Logical Database|
|---|---|---|---|
|Revenues|CFM_REV_01|/SAPQUERY/CFM_REVENUE|FTI_TR_PL_CF|
|Sales Proceeds|CFM_REV_02|/SAPQUERY/CFM_REVENUE|FTI_TR_PL_CF|
|Revenue Forecast|CFM_FOR_01|/SAPQUERY/CFM_REV_FCAST|FTI_TR_PL_CF|


Issue evaluations (for a defined key date)

|Query|Technical Name|Assigned InfoSet|Logical Database|
|---|---|---|---|
|Issue Position|CFM_POS_13|/SAPQUERY/CFM_ISSUE_POS|FTI_TR_POSITIONS|
|Issue Volumes|CFM_DEAL_02|/SAPQUERY/CFM_ISSUE|FTI_TR_DEALS|
|Issue Charges|CFM_DEAL_01|/SAPQUERY/CFM_ISSUE|FTI_TR_DEALS|
|Issue Hedge|CFM_DEAL_03|/SAPQUERY/CFM_ISSUE|FTI_TR_DEALS|



Proceed as follows if you would first like to see an overview of how a certain query is structured:

- 1. Use transaction SAP Query: Start Queries (SQ00).
- 2. Select one user group and one query.
- 3. Choose Description.
- 4. This gives you an overview of general information and options for the selected query:


- a. Query title
- b. Author and user to last make changes
- c. Comments regarding the query
- d. InfoSet used to define the query
- e. Origin of the selected data
- f. Generated lists (sublists)
- g. Additional selections

###### Information about Data Selection

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Standard Queries for the Transaction Manager > Information about Data Selection | L5 | trm10 p.32 | loio `cbfac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cbfac5536a51204be10000000a174cb4.html?locale=en-US)

If Queries are defined on the basis of InfoSets, which in turn are based on logical databases, the corresponding logical database data procurement program automatically provides a selection screen.

The following data selection options are available:

Product Groups

The selection of product groups only includes positions of the respective relevant contract types.

Securities (= contract type 2)

Loans (= contract type 1)

OTC transactions (= contract types 4, 5, and 6)

Exceptions:

Product categories 700 - 750

Listed derivatives (= contract type 6)

Only product categories 700 - 750

Selections

Control Parameters

###### Product Groups (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Standard Queries for the Transaction Manager > Information about Data Selection > Product Groups | L6 | trm10 p.32 | loio `b6fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b6fac5536a51204be10000000a174cb4.html?locale=en-US)

The selection of product groups only includes positions of the respective relevant contract types.

Securities (= contract type 2)

Loans (= contract type 1)

OTC transactions (= contract types 4, 5, and 6)

Exceptions:

Product categories 700 - 750

Listed derivatives (= contract type 6)

Only product categories 700 - 750

###### Selections

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Standard Queries for the Transaction Manager > Information about Data Selection > Selections | L6 | trm10 p.32 | loio `ddfac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ddfac5536a51204be10000000a174cb4.html?locale=en-US)

The following criteria help you to delimit the positions you want to select, based on the logical database used for the report:

(Special) valuation class

The special valuation class is implicitly linked to the valuation area. If you want to carry out valuation-class specific valuations, you must enter the relevant evaluation area.

Portfolio (position)

You can use this field to select positions that are defined with the differentiation terms valuation area, special valuation class, accounting code, ID number, and portfolio.

Business partner (commitment)

The business partner is regarded differently depending on the contract type:

In the case of loans (contract type 1), selection is made based on the main borrower .

In the case of securities (contract type 2), selection is made based on the issuer .

For all other contract types, selection is made based on the counterparty .

Key date

The key date determines the evaluation period of the positions.

The following key date references are available:

Value date

The key date refers to the value date of the subledger positions.

Posting date

The key date refers to the FI posting date.

**Note:**

Position evaluation usually occurs on exactly one key date.

If multiple individual key dates or key date intervals are selected using the multiple selection function, SAP Query determines the positions for each individual key date. The key figures used in the query are recalculated for each individual key date and displayed in a list. You can compare key dates for a defined period.

Based on this logic, multiple selections result in considerably longer runtimes, so the number of key dates to be evaluated should be kept as small as possible.

Exclude plan data indicator

Planned records are not taken into account if you set this indicator.

When a selection is made using the key date reference "posting date", the indicator is irrelevant as planned records are not taken into account in this case.

**Note:**

This indicator is not supported for loans in valuation area 001.

Securities area

ID number

Securities account

Securities account group

**Note:**

You can select by securities account/securities account group. Note that a selection according to these characteristics is only possible if a position differentiation by securities account/securities account group has been defined in the relevant valuation areas. Only then are positions “tailored” to fit these characteristics and only then is a logical data selection possible.

Relationship between selection fields Securities Account and Securities Account Group

If securities account was selected as the only differentiation criteria in a valuation area, a selection based on

securities account group will not return any positions. If you leave the securities account group field empty, the system gets the relevant positions. In the report display, the Securities Account Group field is not filled.

If securities account group was selected as the only differentiation criteria in a valuation area, a selection based on securities account will not return any positions. If you leave the securities account field empty, the system gets the relevant positions. In the report display, the Securities Account field is not filled.

If both securities account and securities account group are selected as differentiation criteria, selections are based on both the securities account and securities account group , however in this case you cannot carry out a cross-securities account valuation.

You often have a scenario in which one parallel valuation area only uses the securities account group as the differentiating criterion, and a second parallel valuation area only uses the securities account. If you want to evaluate a securities account group (as defined in the securities account master data) for both valuation areas, and restrict the selection for the securities account group accordingly, no positions are selected for the valuation area that is differentiated by securities account, and vice versa. For this reason there is an indicator, Interpretation of Securities Account Group , described below.

Interpretation of Securities Account Group indicator

If you select positions by securities account group for a valuation area that is only differentiated by securities account, the system selects the securities accounts assigned to this securities account group in the securities account master data.

In the report display, the otherwise empty Securities Account Group field is filled.

Loans area

Contract number

OTC transactions area

Transaction

Portfolio

Transaction type

Master agreement

Assignment

Internal reference

Characteristics

Finance project

Interpretation of leading currency indicator

Listed Derivatives area

ID number

Futures account

See also:

Refer also to the field help.

###### Control Parameters (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Standard Queries for the Transaction Manager > Information about Data Selection > Control Parameters | L6 | trm10 p.35 | loio `adfac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/adfac5536a51204be10000000a174cb4.html?locale=en-US)

The following fields are provided in the Control Parameters area, based on the logical database used by the report:

Evaluation type

The evaluation type needs to be specified on the selection screen only if the query contains a risk key figure (for example, net present value or duration) and the risk parameters stored under the evaluation type are required to calculate the risk key figure. In such cases, the evaluation type is required. In all other cases, this field can be hidden in the selection variant.

Control Risk Management (NPV) Buffer The logical databases FTI_TR_POSITIONS and FTI_TR_PERIODS enable you to calculate risk key figures (such as NPV or duration) in real time. These calculations may be very time-consuming, depending on the scope of the position. You can therefore calculate the key figures in advance and transfer them to the market data buffer using batch planning (table FTI_MARKET_VALST).

Choose one of the following methods to determine the risk key figures:

Risk management data is recalculated.

The key figures are always recalculated.The terms may be very long.

Risk management data is read from the buffer.

The system first attempts to read the key figures from the market data buffer. If the system cannot find any values, the key figure is recalculated online.

Risk management data is read from the limit from the buffer.

The system first determines the number of selected position records. If this number exceeds the predefined limit, the system accesses the market data buffer. If the limit is not exceeded, the key figures are recalculated.

See Performance Functions for Reporting

Price type

The price type is used for determining the market value of the security. This selection parameter is only relevant for this key figure. In all other cases, this field can be hidden in the selection variant.

Display currency

The display currency needs to be specified on the selection screen only if the query contains key figures in display currency. In such cases, the system requires the entry of the display currency and the corresponding currency translation type on the selection screen. In all other cases, this field can be hidden in the selection variant.

Evaluation currency

You can use the evaluation currency to translate the results of the key figures from the Market Risk Analyzer (MRA) into a custom currency, in accordance with MRA logic.

Remaining term

The remaining term lets you see the terms of the capital investments that belong to the position. The remaining term is computed as the difference between two dates, as specified on the selection screen.

Remaining term based on key date

The report computes the difference between the end of term of the financial product and the selected key date.

Remaining term based on today

The report computes the difference between the end of term of the financial product and the current date.

Remaining term based on reference date

Here, an additional date field is shown. The report computes the difference between the end of term of the financial product and the specified reference date.

Three characteristics are available in the logical database for the output of the remaining term:

Remaining term in days

Remaining term in months

Remaining term in years

Historical account assignment reference indicator

If you select this indicator, the system may access historical data when evaluations are made in the past, instead of reading the current account assignment reference. For example, if an account assignment reference transfer was posted in the past, the system displays the account assignment references and G/L accounts as per the respective key date.

Process reversed flows indicator (only provided in queries based on the logical database FTI_TR_PERIODS.)

When evaluating positions according to posting date , flows that were posted and reversed within a period are not displayed. Reversed flows are displayed only once when the posting is made, and not when they are reversed.

When a business transaction is reversed and the posting status is changed in the subledger from "posted"(P) to "reversed" (R), a reversal document is generated in the general ledger in addition to the original document posted. In the case of a reversal with a different posting date, reconcilliation between the general ledger and subledger requires substantial effort.

In this case, you can use the process reversed flows indicator to generate an artificial business transaction in the subledger by duplicating the original business transaction, for the period between the original document date and the different reversal date.

[figure TRM10-F018 - In this case, you can use the process reversed flows indicator to generate an artificial business transaction in the subledger by duplicating the original business transaction, for the period between the original document date and the different reversal date.]

[figure TRM10-F019]

[figure TRM10-F020 - The indicator determines the entries made in the affected fields:]

The indicator determines the entries made in the affected fields:

The posting date field contains

the posting date of the TM flow for the original flow

the reversal date of the TM flow for the reversed flow

The position value date field contains the position value date common to both flows.

The G/L Account: Debit and G/L Account Credit fields contain the (identical) flow information (and not as in the case of offsetting postings where credit and debit are swapped).

The delta book value fields in their respective currencies contain the value of the flow as if it were posted and not reversed.

The posting status of the flow field contains the indicator for both flows that this flow has been reversed from the view of the TM subledger.

The new ledger posting status field contains value 2 (reversed) for the reversal flow and value 3 (generated ledger posted) for the original flow.

**Note:**

The indicator for processing reversed flows is not supported for Loans ( CML ) in the operative valuation area 001.

Summarize results indicator

Summarizing Results using Characteristics

Hide zero records indicator

If this indicator is set, the data records containing key figures selected in the report definition with a key date value of zero are excluded from the report output.

Only positions with flows in period indicator (this is not available in queries based on the logical database FTI_TR_POSITIONS.)

If the indicator is set, only the positions with flows in the selection period are selected and displayed.

See also:

Detailed F1 help for the respective fields

##### Performance Functions for Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Performance Functions for Reporting | L4 | trm10 p.38 | loio `69fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/69fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

You can use this set of functions to substantially improve the performance of the reporting tasks. The performance is enhanced by generating buffer tables that store business partner addresses and risk key figures or net present values. This makes sense if you run your SAP Query reports for several business partners, or if a lot of risk key figures or net present values have to be calculated. In particular, you can speed up processing for monthly, quarterly, and annual financial statements.

**Features**

Process Flow

- 1. You use the function Setting Parameters for Buffer Tables to define the threshold number of business partners or positions above which buffer tables should be used.

- 2. You then run your SAP Query reports.


When you start the report, the system reads the selected data from the application tables. Once it reaches the value specified in Set Parameters for Buffer Tables, it attempts to read the data from the buffer table. For example, if the value 100 was set for the business partners, the system reads the first 100 of the selected business partners from the business partner tables, and then tries to read business partner 101 onwards from the buffer table.

If the buffer table does not contain the required value, the system reads it from the application table or calculates the missing value and then writes it to the buffer table.

The following reports use the data in the buffer table without updating the entries, and add any missing data.

[figure TRM10-F021]

**Note:**

You do not need to trigger the process for filling buffer tables manually.

If you do want to fill the tables with data yourself, you will need to write a program specifically for this purpose [table FTI_BUT000_T (business partner texts), table FTI_MARKET_VALS (market values in position currency), table FTI_MARKET_VALST (market values in evaluation currency)]. Note that data is only read from the buffer table by the following components:

Transaction Manager

Market Risk Analyzer

Credit Risk Analyzer

Loans Management (CML)

- 3. Since the data in the buffer tables is not updated, you must delete the data in these tables at regular intervals, or whenever you need the data to be refreshed.


Reorganizing Business Partner Texts

Reorganizing Risk Key Figures

Reorganizing Risk Key Figures in Evaluation Currency

Table Contents

The following data is stored in table FTI_MARKET_VALS for each position:

Risk management NPV in position currency

Risk management NPV incoming side in the currency of the incoming side

Risk management NPV outgoing side in the currency of the outgoing side

Clean price in position currency

Basis point value in position currency

Position currency

Currency investment/purchase/incoming side/long

Currency borrowing/sale/outgoing side/short

Macaulay duration

Fisher-Weil duration

Convexity with 5 decimal places

st

Delta, 1 derivation of the premium based on the price of the underlying

Gamma, 2nd derivation of the premium based on the price of the underlying

st

Theta, 1 derivation of the premium, time-based

st

Vega, 1 derivation based on the volatility

The following data is stored in table FTI_MARKET_VALST for each position:

Risk management NPV in evaluation currency

Risk management NPV incoming side in evaluation currency

Risk management NPV outgoing side in evaluation currency

Clean price in evaluation currency

Basis point value in evaluation currency

Evaluation currency

The following data is stored in table FTI_BUT000_T for each business partner ID:

Name

Address data (for example, street, country/region, city, and postal code)

**Examples**

The examples below indicate how you can improve runtimes by generating the buffer table:

| |Factor|
|---|---|
|Reading business partner addresses|300 (For example, if reading a business partner text used to take 20 milliseconds, it only takes approx. 0.06 milliseconds when you use the buffer table.)|
|Calculating the net present value of:| |
|OTC transactions|1,600|
|Securities positions|3,200|
|Loans|16,000-250,000 (depending on the loan category)|

###### Setting Parameters for Buffer Tables

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Performance Functions for Reporting > Setting Parameters for Buffer Tables | L5 | trm10 p.41 | loio `e0fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e0fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

You use this function to define the threshold number of business partners or positions in the report above which buffer tables should be used.

See Performance Functions for Reporting

**Procedure**

- 1. Call up the function [transaction TRMP_PERFORMANCE_ST]. ( Path ). The ChangeView: "Control Parameters": Overview screen appears.
- 2. In the Control Parameters column, you can select the "Text Reader: Maximum Number of Business Partners" and the "Market Data (NPV): Maximum Number of Positions".
- 3. The Value for Control Parameter column contains the default values 10,000 (for business partners) and 100 (for positions).
- 4. You can change the values in the second column to meet your requirements. In doing so, bear the following in mind:


**Caution:**

With these default values, the function is essentially inactive, since the number of business partners or positions that need to be read will usually fall below this limit. The function therefore only takes effect when you enter a realistic value for your data volumes.

- a. a. If you set the value of the control parameter to 1, the system attempts to read all the data from the buffer. If no data is available in the table, the values are calculated or read from the application tables, written to the buffer table, and then read from the buffer table.
- b. b. If you enter a very high value for the control parameter (such as 1,000,000), you can expect that no data will be read from the buffer table. As a consequence, the data is always up-to-date, but there is no improvement to performance.
- c. c. The values must be entered without decimal points or commas. To enter 1 million, for example, enter 1000000.


- 5. Save your entries.

###### Reorganizing Business Partner Texts

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Performance Functions for Reporting > Reorganizing Business Partner Texts | L5 | trm10 p.42 | loio `1cfbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1cfbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

See Performance Functions for Reporting

**Procedure**

Call the function [transaction TRMP_PERFORMANCE_BP] ( path ). The Change View "Temporary Text Table for Business Partner s (Performance)" appears.

Select the data you want to delete. The following utilities are available to help you:

You can restrict the data volume by choosing Selection Criteria → By Contents . The possible selection criteria include:

Business partner

Language Key

Changed on

Changed by

...

You can select all data or a certain block of data by choosing Edit → Selections .

Choose Edit → Delete to remove the selected lines from the table.

Save your changes.

###### Reorganizing Risk Key Figures

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Performance Functions for Reporting > Reorganizing Risk Key Figures | L5 | trm10 p.42 | loio `1ffbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1ffbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

See Performance Functions for Reporting

**Procedure**

Call the function [transaction TRMP_PERFORMANCE_MV] ( path ).The Change View "Reporting: Buffer table for Market Values Position Currency " screen appears.

Select the data you want to delete. The following utilities are available to help you:

You can restrict the data volume by choosing Selection Criteria → By Contents The possible selection criteria include:

Evaluation type in Risk Management

Net present value BW

Net present value incoming side in currency of outgoing side

Net present value incoming side in currency of incoming side

Basis point value in position currency

Position currency

Valuation Area

Company Code

Clean price in position currency

Convexity

Delta

Securities account

Fisher-Weil duration

Gamma

Transaction

ID number

Macaulay duration

Futures account

Key Date

Theta

Vega (Kappa)

Contract number

Currency investment/purchase/incoming side/long

Currency borr./sale/outgoing side/short

Changed by

Changed on

You can select all data or a certain block of data by choosing Edit → Selections

Choose Edit → Delete to remove the selected lines from the table.

Save your changes.

###### Reorganizing Risk Key Figures in Evaluation Currency

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Performance Functions for Reporting > Reorganizing Risk Key Figures in Evaluation Currency | L5 | trm10 p.44 | loio `3dfbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3dfbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

See Performance Functions for Reporting

**Procedure**

- 1. Start the function [transaction TRMP_PERFORMANCE_MVT] ( path ). The Change View "Reporting: Buffer Table for Market Values – Evaluation Currency" screen appears.
- 2. Select the data you want to delete. The following utilities are available to help you:

- a. You can restrict the data volume by choosing Selection By Contents .The possible selection criteria include:

Evaluation type in Risk Management

Evaluation currency

Net present value in evaluation currency

Net present value outgoing side in evaluation currency

Net present value incoming side in evaluation currency

Basis point value in evaluation currency

Company Code

Valuation Area

Clean price in evaluation currency

Securities account

Financial transaction

Security ID number

Futures account

Key Date

Contract number

Changed by

Changed on

- b. You can select all data or a certain block of data by choosing Edit Selections .


- 3. Choose Edit Delete to remove the selected lines from the table.


- 4. Save your changes.

##### Customizing: Information System of the Transaction Manager

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Customizing: Information System of the Transaction Manager | L4 | trm10 p.45 | loio `aeb1c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aeb1c753b1081d4be10000000a174cb4.html?locale=en-US)

**Integration**

You find the following settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings .

**Features**

|Customizing Activity|Setting|
|---|---|
|General Settings TM Reporting| |
|Set Authorization Check in the Logical Databases|Specify whether the general authorization check or the authorization check for each position is active.|
|Field Deactivation for Hide Zero Records Function|The Hide Zero Records function is available in some logical databases and reports based on them. If you activate this function, then the data records in which all key figures have the value zero are hidden in the report output. In this Customizing activity, you can deactivate the Hide Zero Records field for selected key figures for the logical databases. These key figures are then excluded from the check.|
|Define Legal Basis|Define the legal basis for the clearing threshold and for trade repository reporting.|
|Assign Countries/Regions to Legal Basis|Assign to a legal basis all countries/regions that fall under the validity area of that legal basis.|
|Clearing Threshold Reporting (CTR)|This node contains the Customizing activities for the clearing threshold reporting. For more information, see also Clearing Threshold Reporting (CTR). |
|Trade Repository Reporting|This node contains the Customizing activities for the trade repository reporting. For more information, see also Trade Repository Reporting (TRR). |
|Trade Repository Reporting via External Provider Settings for External TRR Provider|Make the necessary technical settings for the trade repository reporting using an external provider.|
|FAS157| |
|FAS157: Classify Product Categories and Types into Levels|Classify financial instruments on various levels based on combinations of product category and product type.|
|FAS 157: Assign Update Types to Level 3 Categories|Assign update types to level 3 categories.|
|Revenue Classification| |
|Maintain Profit/Loss Types|Define profit/loss types to classify the various revenues and expenses at an abstract level.|


|Generate Proposals for Profit/Loss Indicator|You can use this report to fill the Customizing activity table Assign Profit/Loss Types to Update Type and Valuation Area with the update types defined in your system. You can also generate a proposal for the Profit/Loss indicator. The program generates the proposal for the Profit/Loss indicator on the basis of the account symbols defined in the system. Update types whose account determination settings contain an account symbol with the posting categories Profit-Related Posting in Position Currency or ProfitRelated Posting in Payment Currency are regarded as relevant for profit/loss.|
|---|---|
|Assign Profit/Loss Types to Update Type and Valuation Area|Assign the relevant update types to the profit/loss types, depending on the valuation area.|
|Payment Reporting| |
|Define Payment Relevance of Update Types|Specify which update types are relevant to payment and are selected using the logical database FTI_TR_CASH_FLOWS.|
|Proposal Generation for the Payment Relevance of Update Types|This report generates a proposal for the payment settings in Customizing.|
|Maintain Payment Relevance of Flow Types for Loans|Determine whether flow types from the operative loans (CML) area are relevant for payment in payment reporting.|
|Business Information Warehouse| |
|Define InfoSources for Position Initialization|In this Customizing activity, you create the InfoSources required for initializing positions (for each logical target system).|
|Define InfoSources for Delta Position|In this Customizing activity, you create the InfoSources required for deltas, such as position changes (for each logical target system).|
|Process Reversal Logic|Set this indicator if you want the system to include reversed flows during selection and processing.|
|BW Extraction Log|In this Customizing activity, you can select and view the logs that were written during data extraction.|
|Delete Time Stamp for InfoSource|If errors occur, you can delete all or individual time stamps for an InfoSource in this Customizing activity. Bear in mind that, in this case, you also need to delete all the dependent data (in all the relevant data targets).|
|Parallel Processing Control: Information System and BW Extraction|Control whether the evaluation of positions / correspondence objects in the specific functions are executed in parallel.|
|Other| |
|Parallel Processing Control: Information System and BW Extraction|Control whether the evaluation of positions / correspondence objects in the specific functions are executed in parallel.|
|Structure Report Selection|The reports delivered with the system are contained in the Transaction Manager in the following area menus: Hedge Management, Money Market, Foreign Exchange, Securities, Derivatives, Debt Management, and Information System. This Customizing activity calls the area menu maintenance screen, which you can use to edit or create your own report structures.|
|Regulatory Reporting Settings for the Insurance Supervisory Authority|This node contains the Customizing activities for the regulatory reporting settings for the Insurance Supervisory Authority.|

##### Reports

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports | L4 | trm10 p.47 | loio `64fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/64fbc5536a51204be10000000a174cb4.html?locale=en-US)

The following section contains the documentation for the standard reports that are available under Information System Transaction Manager .

###### Report Selection

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Report Selection | L5 | trm10 p.47 | loio `a8fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a8fac5536a51204be10000000a174cb4.html?locale=en-US)

**Definition**

The report selection consists of one or more report structures. Report trees are hierarchical structures containing standard reports or user-defined reports, and lists generated by reports. A system can contain an unlimited number of report structures. Each node can have an unlimited number of reports and pre-generated lists.

The following report structures exist:

|Area|Title of Area Menu|Title of Report Structure|
|---|---|---|
|Treasury and Risk Management – Transaction Manager| | |
|Hedge Management|TM Hedge Management|TM Hedge Management|
|Money Market|TMMN|TRTG|
|Foreign Exchange|TXMN|TRTV|
|Derivatives|TIMN|TRTR|
|Securities|FWMY|TRTW|
|Debt Management|CFM TM|CFM_TM|
|Information System|FZM4|TRMA|


The report structures appear in the area menus for the respective applications.

**Note:**

From a technical point of view, the report structures and the area menus are the same structures and are defined and edited in the same function ( Area Menu Maintenance ). This is why Area Menu Maintenance is listed here. (Nevertheless, to differentiate content, this document still distinguishes between area menus and report structures.)

The reports for hedge management and debt management do not have separate report structures.

The report structure for the Transaction Manager Information System (TRMA) contains all the reports for the money market , foreign exchange , derivatives and securities applications, as well as cross-application reports.

**Use**

In the IMG activity Structure Report Selection you can define your own report structures for each application and to assign reports to them. These settings are independent of the standard report structure and apply across the whole enterprise. You can use the standard report structure (or another structure) as a template for creating your user-specific structure.

**Note:**

For more information on creating, changing, and displaying report structures, see the IMG activity Structure Report Selection and the corresponding documentation .

###### Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction | L5 | trm10 p.48 | loio `2e0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2e0bda531198434de10000000a174cb4.html?locale=en-US)

Purpose

The following functions are available in this area to help you edit and manage your transactions:

Offer Overview

Offer

Transaction Overview: Journal

Change Documents for the Transaction

Alert Monitor

Deadline Monitoring: Maturity Schedule

Adjustment Schedule - Rates/Prices

Report on correspondence: Transaction Release: Work Item List

###### Offer Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Offer Overview | L6 | trm10 p.48 | loio `b007da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b007da531198434de10000000a174cb4.html?locale=en-US)

Features

This report shows you an overview of the offers made and the resulting contracts.You can configure your own overview (for example, sort according to business partner, currency, product type) This provides you with an overview of the quality of the offers and the competitiveness of the prices from individual business partners.

For more information, see Offers for forex and fixed-term deposits.

###### Offer

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Offer | L6 | trm10 p.48 | loio `aa07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aa07da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The Offer function allows you to group all the quotations from different banks that are made prior to concluding a foreign exchange or money market transaction together with a reference and store them in the system. In doing this, the system ranks the offers (for example, in the case of a forex purchase, the lowest rate has the highest valuation). Saving the offers and transaction data from different competitors allows you to analyze the quality and competitiveness of the prices of individual business partners, select the best offer, and use it to conclude a contract.

**Features**

You can use the Offer function in the Money Market area for fixed term deposits and in the Foreign Exchange area for spot exchange transactions and forward exchange transactions to create, execute, and display offers. You can then create a contract directly for the selected offer.

**Prerequisites**

You have created a specific number range for transactions with the activity category offer in Customizing and have assigned it to a transaction type. To do this in the Implementation Guide (IMG) for Treasury and Risk Management , choose Transaction Manager Money Market / Foreign Exchange Transaction Management Transaction Type Define Number Ranges or Define Transaction Types. These transactions have active status 4 .

**Activities**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market or Foreign Exchange Trading Offer.


If you enter a business partner, this must not be defined as a partner. You can enter the quoted interest rate (in the money market area) or the rate (exchange rate, spot rate, swap rate) for each counterparty. If you save the data, you do not have to create an active financial transaction in the Contract activity. When you call up the data again, you can generate a transaction with Contract status. To create an active financial transaction directly after entering the data, choose Execute .

You enter the offers with their own number range. The system creates a contract leading to transaction conclusion in the number range for the respective transaction type. The system groups together all offers and the contract with a Reference .

You can display the number of offers and the contracts that result from these with an evaluation. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market or Foreign Exchange Information System Offer Overview.

###### Transaction Overview: Journal

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Transaction Overview: Journal | L6 | trm10 p.49 | loio `3f4dc55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f4dc55368511d4be10000000a174cb4.html?locale=en-US)

Use

You can use this journal to select transactions that are concluded by certain traders or with certain business partners within a particular period. It contains key data, sorted according to date or activity category, such as business partner, term, or status. From here, you can branch to the basic data of the transaction.

To call up the journal:

- 1. Choose Information System Transaction Transaction Overview Derivatives: Journal.
- 2. The Treasury: Journal of Financial Transactions appears.


Enter the selection criteria in the corresponding fields.

**Example:**

If you want to display all the transactions you have entered for a certain product type, enter the product type in the product type field and your name in the user field.

The transactions can be sorted by date or by activity category . In the Page change area , you can specify when you want the system to start a new page. There are two variants to choose from:

Company code, product type, transaction type, date

Company code, activity category, product type, transaction type

**Note:**

Remove any selections for the Money market, Foreign exchange and Derivatives fields that do not apply. This speeds up the response times for all subsequent operations since only the transactions from the components you have selected are included.

1. Choose Program Execute .

1. The system displays the journal for the OTC transactions you selected. It contains the related key data, such as the counterparty, activity category, status and term.

Position your cursor on the transaction you require. To display the basic data for an OTC transaction and branch to further screens, double-click this transaction, or place the cursor on the required transaction and press the Choose pushbutton.

###### Change Documents for the Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Change Documents for the Transaction | L6 | trm10 p.50 | loio `b707da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b707da531198434de10000000a174cb4.html?locale=en-US)

Use

You use this report program to display the changes made for a transaction selected according to date and user.

- 1. Choose Information system Transaction Change Documents.
- 2. The Treasury: Change Documents for Transaction screen appears. Enter your selection criteria in the corresponding fields.
- 3. Choose Program Execute .
- 4. You see all the changes made to the selected transactions in a list.

###### Alert Monitor

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Alert Monitor | L6 | trm10 p.50 | loio `4f66e605cdad6e58e10000000a42189d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f66e605cdad6e58e10000000a42189d.html?locale=en-US)

Using the Alert Monitor you can display a list of pending activities in financial transaction processing and in securities account management.

**Features**

The monitored financial transaction processes include the following: release and settlement of financial transactions, payment and posting of flows, sending correspondence for financial transactions, payment and posting of cash flows, sending correspondence for financial transactions, fixing of interest rates/prices, trade repository reporting, and NDF fixing.

The monitored processes of the security account management include the following: payment and posting of conditionbased flows, sending correspondence for security account transfers, and fixing of interest rates/prices.

Each of these processes forms a separate tab.

Settlement

You can use one of the following selection parameters to select financial transactions that haven’t been settled so far and fulfill the entered criteria:

Open Days Before Contract Date field

If a financial transaction has not yet been settled n days before the contract date, a message is issued in the alert monitor.

Open Days Before End of Term field

If a financial transaction has not yet been settled n days before the end of term, a message is displayed in the alert monitor.

Release

You can use one of the following selection parameters to select financial transactions that haven’t been released so far and fulfill the entered criteria:

Transaction Release:

Open Days After Start of Term field

If a transaction is not released in the period between the start of term and these n days after the start of term, a message is displayed in the alert monitor.

Open Days Before Start of Term field

If a transaction has not yet been released n days before the start of term, a message is displayed in the alert monitor

Posting Release:

You can use one of the following selection parameters to select financial transactions that haven’t been posted so far and fulfill the entered criteria:

Open Days Before Payment Date field

If a flow has not yet been released for posting n days before the payment date, a message is displayed in the alert monitor.

Payment and Posting

On this tab, you monitor postings and payments of financial transactions and security class positions. You can find all flows of financial transactions and security class positions with a due date date that is before or the same as the date entered that has not yet been posted or paid.

You can restrict the search by the following:

Using the following checkboxes, you can exclude the check for specific areas:

Payment: Issue No Messages

Posting: Issue No Messages

SecAcctMgt: Issue No Messages

Using the available general and specific selection criteria you can further restrict the search.

Correspondence

Rate/Price Fixing

**Note:**

You make manual adjustments to interest rates and prices using Create Interest Rate/Price Adjustment (transaction TI10), and you can specify automatic adjustments using transaction Automatic Interest Rate Adjustment (transaction TJ05) or Commodity/Security Price Adjustments.

Trade Repository Reporting

The system finds trade repository objects (TAROs) that have a specific status since n or more days.

For the check TAROs Not Yet Sent, the system finds all TAROs that have the status Created, Incompletely Created, or Send Failed since n or more days after the scheduled send date.

For the check TAROs with Errors After Sending, the system finds all TAROs that have the status Rejected or Reconciliation Failed since n or more days after the send date.

NDF Fixing

Open Days Before Fixing field

The system determines all NDF transactions that are still open n days before the fixing date is reached

Termination Swap/Collar

**Processing Steps**

- 1. To start the Alert Monitor, go to the SAP Easy Access screen and, beneath the relevant product type (such as Money Market, Foreign Exchange, or Securities), choose Information System Transaction Alert Monitor (transaction FTR_ALERT).
- 2. In addition to general selection criteria (such as company code and transaction number), you can also enter specific selection criteria on corresponding tab pages. You can use report variants to make individual settings and create date fields dynamically (for example, Today minus 3 days).
- 3. When you run the Alert Monitor, you obtain a list of messages relating to open transactions, transaction flows and postings, exceeded due dates, and the relevant product types and transaction types.


**Note:**

The Alert Monitor is also available as Display Treasury Alerts app on the SAP Fiori launchpad.

**Note:**

On each tab, you can mark the Issue No Messages indicator, if you don’t want to monitor the specific area.

###### Deadline Monitoring: Maturity Schedules

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Deadline Monitoring: Maturity Schedules | L6 | trm10 p.52 | loio `4eae6b6340f8204ee10000000a421937` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4eae6b6340f8204ee10000000a421937.html?locale=en-US)

**Use**

For deadline monitoring, you can use the following maturity schedules:

Maturity Schedule: Spot/Forward Transaction (transaction TX-2)

Maturity Schedule: OTC Options (transaction TJ06)

Interest Rate/Price Adjustment Schedule (transaction TJ07)

**Features**

Maturity Schedule: Spot/Forward Transaction

The system displays the forex transactions according to the currency pairs selected, sorted by expiration date. You can choose between displaying the subtotals for incoming/outgoing totals in the different currency pairs and displaying balances by maturity date within a currency pair. In both cases, the system displays the totals of all amounts for each currency pair.

If you only specify one currency in the area of currency/rate limitation, all currency pairs involving that currency are selected.

**Example:**

If you specify EUR, the system displays combinations involving the currency EUR (such as USD/EUR or GBP/EUR). If you specify a second currency, the system only displays the selected currency pair.

The selection criterion Exchange Rate of the Forex Transaction only takes effect if you have previously entered a currency pair (leading currency and following currency).

To display the maturity schedule, proceed as follows:

- 1. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Information System Transaction Deadline Monitoring Maturity Schedule for Spot/Forward Transactions: Currencies (transaction TX-2).
- 2. Enter your selection criteria and choose Execute. The system displays the maturity schedule for all maturities in the selected period.


Maturity Schedule: OTC Options

You use this function to display all OTC options that match the selected criteria and that can be exercised in the specified period. For detailed information, you can navigate from the schedule to the display transaction for the OTC option. If an option needs to be exercised or to expire, you can call the corresponding transaction.

To display the maturity schedule, proceed as follows:

- 1. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Information System Transaction Deadline Monitoring Maturity Schedule for OTC Options (transaction TJ06).
- 2. Enter your selection criteria and choose Execute. The system displays a list of OTC options.


Interest Rate/Price Adjustment Schedule

You use this function to display the due financial transactions according to your selections for the following types of adjustment:

Interest rate adjustment

Securities price adjustment

Selection

- 1. Select the desired adjustment type.
- 2. Under General Selections, specify the company code, the fixing date, or the product type.
- 3. Depending on the adjustment type that you have selected, you can use the following additional selection fields:


You can select a reference interest rate to restrict the data displayed in the interest rate adjustment schedule.

You can use the following criteria to restrict the data displayed in the securities adjustment schedule:

Security ID

Exchange

Rate Type

###### Adjustment Schedule - Rates/Prices

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Adjustment Schedule - Rates/Prices | L6 | trm10 p.54 | loio `6be2a104fa0f4c088fb18c2f3e2b94df` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6be2a104fa0f4c088fb18c2f3e2b94df.html?locale=en-US)

With this app, you display the financial transactions due for rate/price adjustments.

The adjustment schedule gives you an overview of rate/price adjustments that have already been made and the related rates/prices and rate/price adjustment. It also tells you when the next rate/price adjustment for a particular transaction is scheduled. The following kinds of adjustments are available:

Interest Rate Adjustment

Commodity Price Adjustment

Security Price Adjustment

Foreign Exchange Rate Adjustment

Price Index Adjustment

**Key Features**

Get an overview of rate/price adjustments.

Display the schedule for next rate/price adjustments.

**Activities**

- 1. Choose Transaction Manager Information System Transaction Deadline Monitoring Rate/Price Adjustment Schedule (transaction TJ07) in the area menu of the transaction manager or open the Adjustment Schedule Rates/Prices app on SAP Fiori launchpad.
- 2. The Rate/Price Adjustment Schedule screen appears.

Enter your selection criteria in the corresponding fields.

You can enter general selections for the Company Code, the Fixing Date, or the Product Type.

In addition, specific selection criteria for the different kinds of adjustments are available.

- 3. The system displays the results for the selection criteria in an ALV list.
- 4. You can navigate to a financial transaction by selecting a row in the table and choosing the Financial Transaction button.
- 5. You can navigate to the following apps by choosing More Goto Rate/Price Adjustment in the results screen:


Create Rate/Price Adjustment

Change Rate/Price Adjustment

Reverse Rate/Price Adjustment

- 6. You can change the structure of the list display using the Change Layout pushbutton. You can add the column Rate/Price Adjustment Trigger, for example. This tells you whether the rate/price adjustment was performed manually or automatically.
- 7. You can export the results list to a spreadsheet by choosing More Interest/Price Adjustment Schedule Export Spreadsheet .


**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**Related Information**

Adjust Variable Rates/Prices

###### Transaction Release: Work Item List

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Transaction > Transaction Release: Work Item List | L6 | trm10 p.55 | loio `25d6c7533a661d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/25d6c7533a661d4be10000000a174cb4.html?locale=en-US)

Use

Here, you can display a list of the transactions that still need to be processed.

- 1. Choose Information System Transaction Transaction Release Transaction Release: Work Items, Money Market.


- 2. The Transaction Release: Work Item Overview and Status of all Transactions screen appears . Enter the selection criteria in the Transaction data and Additional data areas.
- 3. Choose Program Execute . The workflow data is read.
- 4. An overview of the status of the transactions selected is displayed. The status of a work item shows you the status of this step within the workflow.



You can also release transactions using the Release workflow.

###### Position

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position | L5 | trm10 p.55 | loio `520bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/520bda531198434de10000000a174cb4.html?locale=en-US)

Use

You can edit and manage your positions using the following functions:

Position List

Position Overview

Listed Derivatives: Position in Futures Account

Accounting Overview

Total Commitment

Portfolio Analysis of Interest-Bearing Instruments

TOP 5 - Security Items

Rating Analysis

Country/Region Analysis

Currency Analysis

IAS Classification

Simulated Valuation

Reference Report for Impairment

Issue Position

ABS MBS Positions

Position Trend:

Position Flow List

Due Date Grid

Key Date Comparison

Periodic Reporting

Position Trend

Book Value/OCI Trend

Additionally, you can use the following apps to edit and manage your positions:

**Display Treasury Position Flows**

**Display Treasury Posting Journal**

Display Treasury Position Values

###### Position Overview (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Position Overview | L6 | trm06 p.262 | loio `0dfbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0dfbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

This report provides an overview of the class positions in a securities account.

You can restrict the displayed class positions using the following selection criteria:

Company code

ID Number

Product type

Securities account

Securities account type

If you do not specify any selection criteria, the system displays all the available class positions in securities accounts across all company codes.

**Features**

You can use the indicator Do Not Display Zero Positions if you want to hide these from view.

You can branch to the following functions from this list:

Cash Flow for a Class in a Securities Account

Securities Account Position Indicator

###### Portfolio Analysis of Interest-Bearing Instruments

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Portfolio Analysis of Interest-Bearing Instruments | L6 | trm10 p.57 | loio `d4fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d4fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

This report calculates the average effective interest rate (nominal-weighted), the average nominal interest rate (nominalweighted), and the average duration (Macaulay duration and Fisher-Weil duration) for the selected interest-bearing instruments in the areas Securities, Money Market, and Loans.

The system also displays the following in the display currency: the clean price, the net present value, the nominal value, the book value, the amortized acquisition value, and the acquisition value.

**Integration**

The read modules and calculation modules in Risk Management are used to calculate the summarized key figures for the average effective interest rate (nominal-weighted), the average nominal interest rate (nominal-weighted), the average duration, the clean price, and the net present value. Consequently, the system applies the relevant market data and settings, such as the evaluation type, to perform the calculations. The financial objects in the Market Risk Analyzer are not used.

**Prerequisites**

In Customizing for the Transaction Manager, you need to have made the settings required for calculating the key figures. For example, you need to have assigned an effective interest method in the definition of the product types for money market transactions as part of the effective interest calculation.

The market values required for calculating the key figures need to have been specified in the market value tables.

In Customizing for Risk Management, you need to have made the settings required for calculating the key figures. This applies, for example, to the yield curves required.

See also: Documentation on the Market Risk Analyzer in SAP Library and the Implementation Guide (IMG).

**Features**

Selections

The interest-bearing instruments are analyzed in a valuation area on a particular key date (required entry).

You use the General Selections to select the positions or financial transactions to be evaluated. These form the portfolio that is to be evaluated. The key figures are calculated separately according to assets and liabilities, on the level of the entire portfolio for asset positions and liabilities positions as well as on the levels of the subportfolios that result from the selected key characteristics (see below).

You can only select financial transactions or positions with the following product categories:

040 Bond

042 Bond with installment repayment

060 Warrant bond

070 Convertible bond

300 Mortgage

310 Borrower's note loan

320 Policy loan

330 General loan

340 Consumer loan

360 Installment loan

370 Investor contract

510 Fixed-term deposit

520 Deposit at notice

530 Commercial paper

540 Cash flow transaction

550 Interest rate instrument

In the Control Parameters area, you make the necessary settings for calculating the key figures in risk management.

The evaluation type contains the risk parameters required for calculating the key figures (required entry).

Choose the relevant display currency and the corresponding currency translation type (required fields).

Control Risk Management (NPV) Buffer

The real-time calculation of the risk key figures, such as the net present value or duration, can be very timeconsuming depending on the volume represented by the positions. For this reason, you have the option of calculating the key figures in advance by scheduling a batch job and then transfering the results to the market data buffer.

Choose one of the following methods to determine the risk key figures:

Risk Management Data Recalculated

The key figures are always recalculated. The terms may be very long.

Risk Management Data Read from Buffer

The system first attempts to read the key figures from the market data buffer. If the system cannot find any values there, the key figure is recalculated online.

Risk Management Data Read from Buffer from Limit

The system first determines the number of selected position records. If this number exceeds the predefined limit, the system accesses the market data buffer. If the limit is not exceeded, the key figures are recalculated.

See also: Performance Functions for Reporting

You can use the Save Application Log indicator to store the error logs for this report on the database.

Selection of Key Fields for Summarized Analysis

You need to choose two of the following characteristics as summarization levels:

Interest Category

Position Currency

Product Type

Country/Region of Registered Office of Business Partner

For the financial transactions/positions (portfolio) selected using the general selections, the system separates the calculated key figures according to asset positions and liabilities positions. On these levels, the system then calculates the key figures for the subportfolios resulting from the summarization levels selected here.

Example:

- Characteristic 1 (Interest Category): Has two values (1=fixed, 2=variable)

- Characteristic 2 (Position Currency): Has three values (EUR, USD, GBP)


|Assets/Liabilities Indicator|Interest Category|Position Currency|Key Figure 1| |
|---|---|---|---|---|
|1|1|EUR|2| |
|1|1|USD|4| |
|1|1|GBP|8| |
|1|1| |6| |
|1|2|EUR|4| |
|1|2|USD|6| |
|1|2|GBP|3| |
|1|2| |5| |
|1| | |5.2| |
|2|1|EUR|6| |
|2|1|USD|7| |
|2|1|GBP|8| |
|2|1| |7.5| |
|2|2|EUR|4.3| |
|2|2|USD|6| |
|2|2|GBP|5.5| |
|2|2| |5.4| |
|2| | |6| |


Error Limits (Quality of Calculated Key Figures)

Since calculating the summarized key figures may lead to errors if the required data cannot be determined completely (a typical error originates from incomplete market data), the report immediately displays how reliable the calculated key figures are. The quality of the summarized key figures is measured by taking the ratio of the total nominal values of the positions with errors and the total of all nominal values of the portfolio (or part of the portfolio) being viewed.

On the initial screen, you need to determine the limits for displaying the quality of the key figures in the report with a green, yellow or red traffic light.

Amount Scaling

You can limit the number of digits before and after the decimal point to display the data in a manageable way.

Output

Key Figures

Average Effective Interest Rate (Nominal-Weighted)

[figure TRM10-F025 - Average Nominal Interest Rate (Nominal-Weighted)]

Average Nominal Interest Rate (Nominal-Weighted)

[figure TRM10-F026 - Average Macaulay Duration [= Portfolio Duration]]

Average Macaulay Duration [= Portfolio Duration]

[figure TRM10-F027 - Duration according to Macaulay ( ) is defined as a weighted average of the times when the payments are made. For this, the net present values of interest and redemption payments are used as weighting factors.]


Duration according to Macaulay ( ) is defined as a weighted average of the times when the payments are made. For this, the net present values of interest and redemption payments are used as weighting factors.

The duration expresses the average time (in years) that a capital investment is committed.

See also: Sensitivity Key Figures

The durations for the individual positions or financial transactions are calculated in Risk Management. This report uses the above formula to calculate the average duration.

Average Fisher-Weil Duration (Modified Duration) [= Portfolio Duration]

[figure TRM10-F029 - Average Fisher-Weil Duration (Modified Duration) [= Portfolio Duration]]


The Fisher-Weil Duration (Modified Duration) ( ) specifies the percentage change in the price of the bond when the market interest level changes by one percent. This means that the duration measures the impact on the price triggered by a change to the marginal interest rate and in this way demonstrates how sensitive the bond price is to the market interest rate.

See also: Sensitivity Key Figures

The durations for the individual positions or financial transactions are calculated in Risk Management. This report uses the above formula to calculate the average duration.

Net Present Value

The value of a financial transaction that is valid at the horizon. The net present value is determined by taking into account the market data and transaction data valid on the evaluation date and, where applicable, using this data in a special valuation model.

See also: The documentation on the Price Calculator for Financial Instruments in the Market Risk Analyzer

The individual net present values are totaled.

Clean Price

The price of a financial instrument minus accrued interest or interest to be accrued/deferred.

It is determined using the net present value calculator.

The values determined for the individual transactions or positions are totaled.

Nominal Value, Book Value, Amortized Acquisition Value, Acquisition Value

The current values in the position components for transactions/positions are read from position management and totaled accordingly.

See also: Position Components

A traffic light icon adjacent to each calculated key figure informs you of the quality of that key figure.

You can double-click a line in the report to display a list of subportfolios for that line. You then have the following options:

Display the position values of the financial transaction/position

You can call up the following information from here:

Display flows in a position up to the key date (Subledger Cash Flow)

Display securities account in a securities account group (if the securities account group has been selected as a differentiation criterion)

Display details of the position management procedure

Subledger position indicator

Securities: Detailed View (for securities positions)

Branch to the transaction data related to an OTC transaction to display, change, or edit the data in any other way.

Create a new financial transaction

The list is displayed using the SAP List Viewer for SAP GUI (Classic).

**Activities**

Choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager

Information System Reports Position Analysis of Interest-Bearing Instruments (transaction TIS20).

###### Accounting Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Accounting Overview | L6 | trm10 p.62 | loio `67fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/67fbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

This report contains all the relevant position values, including valuation and risk key figures, for the Accounting area.

**Integration**

This report is a query. It is based on InfoSet /SAPQUERY/CFM_POSITIONS, which in turn is based on the logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_08.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Total Commitment

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Total Commitment | L6 | trm10 p.63 | loio `b3fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b3fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

This report shows how the book value for each commitment partner is distributed. By selecting alternative layouts, you can view the data for each partner country/region or industry sector.

**Integration**

This report is a query. The query is based on InfoSet CFM_POSITIONS, which, in turn, is based on logical database FTI_TR_POSITIONS.

The technical name of this query is CFM_POS_12.

**Features**

Selection

Product groups

Selections

Control parameters

Output

The list is displayed using the SAP List Viewer.

See also:

SAP List Viewer for SAP GUI (Classic)

###### TOP 5 – Security Items (Market Value View)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > TOP 5 – Security Items (Market Value View) | L6 | trm10 p.64 | loio `70fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/70fbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The Query outputs the TOP 5 items for the securities area based on the market value in display currency.

**Integration**

This report is a query. The query is based on InfoSet CFM_POSITIONS, which in turn is based on logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_09.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Rating Analysis

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Rating Analysis | L6 | trm10 p.64 | loio `99fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/99fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The aim of rating analysis is to make the risks associated with financial assets transparent, and therefore comparable.

This query provides a statistical rating analysis for the securities area based on the book value and issue rating defined in the class master data.

Issuer ratings are determined by performing an integral analysis of a company, and form the basis for issue ratings.

**Prerequisites**

You need to define the ratings and the credit rating institute in Customizing by choosing Treasury and Risk Management

Basic Functions SAP Business Partner for Financial Services Settings for Financial Services General Settings Ratings/Credit Standing Credit Standing .


You have to assign the rating agency and the rating to an ID number in the class master data.

**Integration**

This report is a query. It is based onInfoSet /SAPQUERY/CFM_POS_04, which in turn, is based on logical database FTI_TR_POSITIONS.

The technical name of the query is CFM_POS_04.

**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Country/Region Analysis

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Country/Region Analysis | L6 | trm10 p.65 | loio `46fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/46fbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The statistics defined using this query give you a flexible overview of how your financial assets are distributed across various regions.

The positions are structured according to the country/region key of the commitment partner and are based on the book value in local currency. The SAP Query statistics function requires a reference currency. This means that if the local currency is not EUR, you must set the reference currency to the respective local currency.

**Integration**

This report is a query. It is based on the InfoSet /SAPQUERY/CFM_POSITIONS which in turn is based on the logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_05.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer.

See also:

SAP List Viewer for SAP GUI (Classic)

###### Share of Position (Relating to the Euro)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Share of Position (Relating to the Euro) | L6 | trm10 p.66 | loio `f8fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f8fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

This report provides a percentage overview of the various product types based on the book value and the euro.

**Integration**

This report is a query. It is based on the InfoSet /SAPQUERY/CFM_POSITIONS, which in turn is based on the logical database FTI_TR_POSITIONS.

The technical name of this query is CFM_POS_07.

**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Remaining Term Statistics

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Remaining Term Statistics | L6 | trm10 p.66 | loio `cefac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cefac5536a51204be10000000a174cb4.html?locale=en-US)

Use

The remaining term statistics report enables you to monitor the duration for which the capital for transactions and securities positions is committed.

**Integration**

This report is a query. It is based on InfoSet /SAPQUERY/CFM_POSITIONS, which in turn is based on the logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_06.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Currency Analysis

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Currency Analysis | L6 | trm10 p.67 | loio `9b30c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9b30c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

This report groups financial instruments according to position currency. The book value in local currency is used as the calculation base.

**Integration**

This report is a query. It is based on InfoSet /SAPQUERY/CFM_POSITIONS, which in turn is based on the logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_10.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### IAS Classification

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > IAS Classification | L6 | trm10 p.68 | loio `10fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/10fbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Accounting regulations such as IAS or US GAAP prescribe that financial assets must be subdivided into different holding categories in the balance sheet. Within these categories, unrealized gains and losses resulting from valuations may need to be treated differently:

Affecting profit/loss:

Unrealized gains or losses are posted directly to the profit/loss account

Not affecting profit/loss:

Unrealized gains or losses are initially posted to a revaluation reserve. Any opposing write-ups or write downs or (partial) outflows must be cleared against this account before they are posted to the profit/loss account.

The report provides an overview of the financial assets in each holding category, and lets you display valuation results that affect the profit/loss account separately from those that do not.

**Integration**

This report is a query. The query is based on InfoSet CFM_POSITIONS, which, in turn, is based on logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_2.


**Features**

Selection

Product groups

Accruals/deferrals

Control parameters

Output

The list is displayed using the SAP List Viewer.

See also: SAP List Viewer for SAP GUI (Classic)

###### Simulated Valuation

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Simulated Valuation | L6 | trm10 p.68 | loio `6dfbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6dfbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

You can use this query to simulate a valuation run for selected positions.

The report contains all the relevant position information in the Accounting area.

**Integration**

This report is a query. The query is based on InfoSet CFM_POS_11, which, in turn, is based on logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_11.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Issue Position

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Issue Position | L6 | trm10 p.69 | loio `d7fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d7fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

You use the Issue Position report (transaction TIS50) to display key figures (for example, the nominal value, book value, and net present value) of an issued securities position including redemptions on a key date. The report shows you the current position in the relevant security.

You have the option of the activities Issue and Redemption for the product categories Bond (040) and Bond with Installment Repayment (042).

You can post condition-based flows (interest and repayments) to customer accounts or with a payment request. This involves defining payment details in the securities account. You can change these details when manually posting interest and repayments.

See also: Issuing Bonds

The following transactions are also available for issued securities:

Issue Volumes

Issue Charges

Issue Hedge

###### ABS MBS Positions

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > ABS MBS Positions | L6 | trm10 p.70 | loio `9e30c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9e30c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

The report provides data on Asset-Backed Securities and Mortgage-Backed Securities positions including cumulative repayments and the original nominal amount.

**Integration**

This report is a query. It is based onInfoSet /SAPQUERY/CFM_ABSMBS_POS, which in turn, is based on logical database FTI_TR_POSITIONS.

The technical name of the query is CFM_POS_14.

**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

Position Trend

Due Date Grid

Use

The due date grid states all transactions that are due (such as the interest and repayment transactions for the selected positions) for the four quarters starting at the beginning of the selection period as well as for the subsequent five years.

**Integration**

This report is a query. The query is based on InfoSet /SAPQUERY/CFM_MATUR_CF , which, in turn, is based on logical database FTI_TR_CASH_FLOWS .

The technical name of this query is CFM_MAT_01.

**Features**

Product Groups

Selections

**Note:**

For Flow Date enter the entire evaluation period (the 5 years you want to analyze).

**Example:**

Example:

To create a due date grid for the years 2001 through 2005, enter the range from 01/01/2001 to 12/31/2005 .

Control Parameters

Here, Error Log Display has been selected and To Date has been selected for Remaining Term Based On .

Output

The list is displayed using the SAP List Viewer .

See also: SAP List Viewer for SAP GUI (Classic)

###### Key Date Comparison

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Position Trend > Key Date Comparison | L7 | trm10 p.71 | loio `fefac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fefac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The key date comparison report provides you with an overview of the positions on the assets and liabilities side of the balance sheet and of the accrued profits/losses on any two key dates as well as the corresponding percentage deviations.

Operational aspects (trading support) play a lesser role in this report.

The report is mainly for controlling purposes. It serves as a standard list that you can use as it is or as a template for creating your own reports. You can, for example, easily expand the report to display more than two key dates (time series).

**Integration**

To access the following operative transactions, choose Goto Call Up Report .

|Money market|Collective processing|
|---|---|
|Foreign exchange transactions|Collective processing|
|OTC interest rate instruments|Collective processing|
|Listed derivatives|Display order|
|Securities|Collective processing|
|Securities|Position information|


|Loans|Create|
|---|---|


**Prerequisites**

You need to have created transactions from the various TR functional areas in the system.

**Features**

It displays trading transactions from Transaction Management. The key figures delivered with the system both for assets/liabilities transactions for the key date entered are as follows:

Number of units/number of transactions

Assets:

Nominal value in currency of investment/purchase

Asset: Acquisition value in position currency

Asset: Acquisition value in local currency

Asset: Book value in position currency

Asset: Book value in local currency

Liabilities:

Nominal value in currency of investment/purchase

Liability: Acquisition value in position currency

Liability: Acquisition value in local currency

Liability: Book value in position currency

Liability: Book value in local currency

Profit/loss amounts:

Total (accrued) depreciation in position currency

Total (accrued) depreciation in local currency

Unrealized gains and losses in local currency

###### Periodic Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Position Trend > Periodic Reporting | L7 | trm10 p.72 | loio `530dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/530dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report supplies you with an overview of position changes within a certain period for selected positions.

**Features**

Product groups

General selections

###### Position Trend (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Position Trend > Position Trend | L7 | trm10 p.73 | loio `07fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/07fbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The position trend list provides an overview of the position trends both on and off the balance sheet in the Transaction Manager between two key dates specified by the user.

The report serves as a standard list that you can use as it is or as a template for creating your own reports.

**Integration**

This report is a query. The query is based on InfoSet /SAPQUERY/CFM_PERIODS, which in turn is based on logical database FTI_TR_PERIODS.

- The technical name of this query is CFM_PER_02.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer.

See also:

SAP List Viewer for SAP GUI (Classic)

###### Book Value/OCI Trend

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Position > Position Trend > Book Value/OCI Trend | L7 | trm10 p.73 | loio `e6fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e6fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Accounting regulations such as IAS or US GAAP prescribe that financial assets must be subdivided into different holding categories in the balance sheet. Within these categories, unrealized gains and losses resulting from valuations initially have to be posted to revaluation reserves (Other Comprehensive Income (OCI) component), rather than to the profit/loss account. Any opposing write-ups or write downs or (partial) outflows must be cleared against OCI before they are posted to the profit/loss account.

The report provides an overview of the changes to these OCI components for the security and foreign exchange elements of a position over the selection period.

**Integration**

This report is a query. The query is based on InfoSet CFM_PERIODS, which, in turn, is based on logical database FTI_TR_PERIODS.

- The technical name of this query is CFM_PER_03.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer.

See also:

SAP List Viewer for SAP GUI (Classic)

###### Revenue Analysis

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Revenue Analysis | L5 | trm10 p.74 | loio `42fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/42fac5536a51204be10000000a174cb4.html?locale=en-US)

###### Revenues

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Revenue Analysis > Revenues | L6 | trm10 p.74 | loio `3afbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3afbc5536a51204be10000000a174cb4.html?locale=en-US)

Use

You can use this report to analyze the revenues earned within a given evaluation period.

**Integration**

This report is a query. The query is based on InfoSet /SAPQUERY/CFM_REVENUE , which in turn is based on logical database FTI_TR_PL_CF .

- The technical name of this query is CFM_REV_01.


**Prerequisites**

Customizing for the Information System in the Transaction Manager

**Features**

Selection

Product groups

Selections

Control parameters

Output

The list is displayed using the SAP List Viewer .

See also: SAP List Viewer for SAP GUI (Classic)

###### Revenue Forecast

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Revenue Analysis > Revenue Forecast | L6 | trm10 p.75 | loio `7cfbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7cfbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

This report enables you to make a prognosis of future expenses and revenues within a particular selection period. Revenues can be displayed as aggregated values using the profit/loss type.

**Integration**

This report is a query. The query is based on InfoSet /SAPQUERY/CFM_REV_FCAST , which in turn is based on logical database FTI_TR_PL_CF .

The technical name of this query is CFM_FOR_01.

**Prerequisites**

Customizing for the Information System in the Transaction Manager

**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:SAP List Viewer for SAP GUI (Classic)

###### Sales Proceeds

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Revenue Analysis > Sales Proceeds | L6 | trm10 p.75 | loio `79fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/79fbc5536a51204be10000000a174cb4.html?locale=en-US)

Use

This query restricts the general revenue list to realized gains and losses.

**Integration**

This report is a query. The query is based on InfoSet /SAPQUERY/CFM_REVENUE , which, in turn, is based on logical database FTI_TR_PL_CF .

- The technical name of this query is CFM_REV_02.


**Prerequisites**

Customizing for the Information System in the Transaction Manager

**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer.

See also:

SAP List Viewer for SAP GUI (Classic)

###### Due Date Grid (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Revenue Analysis > Due Date Grid | L6 | trm10 p.76 | loio `93fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/93fac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The due date grid states all transactions that are due (such as the interest and repayment transactions for the selected positions) for the four quarters starting at the beginning of the selection period as well as for the subsequent five years.

**Integration**

This report is a query. The query is based on InfoSet /SAPQUERY/CFM_MATUR_CF , which, in turn, is based on logical database FTI_TR_CASH_FLOWS .

The technical name of this query is CFM_MAT_01.

**Features**

Selection

Product Groups

Selections

**Note:**

For Flow Date enter the entire evaluation period (the 5 years you want to analyze).

**Example:**

Example:

To create a due date grid for the years 2001 through 2005, enter the range from 01/01/2001 to 12/31/2005 .

Control Parameters

Here, Error Log Display has been selected and To Date has been selected for Remaining Term Based On .

Output

The list is displayed using the SAP List Viewer .

See also: SAP List Viewer for SAP GUI (Classic)

###### Risk Settings

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Risk Settings | L5 | trm10 p.77 | loio `48fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/48fac5536a51204be10000000a174cb4.html?locale=en-US)

###### Limits: Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Risk Settings > Limits: Overview | L6 | trm10 p.77 | loio `2b0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2b0eda531198434de10000000a174cb4.html?locale=en-US)

Use

You get an overview of limits for the selected limit types by running the Limits: Overview report.

**Prerequisites**

You have already created limits. For more information, see also Editing Limits.

**Features**

Selection

|Area|Selection|
|---|---|
|General Access Options|Limit Type Limit Currency Determination Procedure|
|Selection of Limits by Key Date|Valid To|


|Selection of Limits by Validity Interval|Valid From Valid To|
|---|---|
| | |


Output

The overview list displays all limits selected according to limit type.

From this overview, you can branch to the Overview of Limit Utilizations of the individual limits.

You can also branch to the business partner data from here.

You can display the overview containing data present in the system in different ways.

###### Limits: Display Changes

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Risk Settings > Limits: Display Changes | L6 | trm10 p.78 | loio `2e0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2e0eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Use this report to get an overview of the changes made to the limits for the limit types you have specified, depending on the change date and the changing user name you enter.

**Features**

Selection

|Selection ranges|What you should know|
|---|---|
|Limit type| |
|Date|Period for which you want change documents to be displayed.|
|User|The User whose change documents you want to see.|


Output

The system displays a list of Changes To Limits , sorted by limit type in ascending date order. In this list, you can look at old and new entries for limits, the person who made the changes, the change document and further information.

**Note:**

Via Edit Search For... you can search for terms in comprehensive lists.

**Activities**

- 1. Choose Basic Functions Limit Management Limits Display changes.
- 2. Enter the following ranges as selection criteria for the changes to limits:


Limit type

Date

User

3. Choose Execute .

###### Limit Utilizations: Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Risk Settings > Limit Utilizations: Overview | L6 | trm10 p.79 | loio `370eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/370eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use the Utilizations : Overview function to get an overview of limits and limit utilizations for the limit types selected relating to the key date specified.

**Prerequisites**

Structure of Limit Utilizations

**Features**

Selection

|Area|Selection Options|
|---|---|
|General access options|Limit types Currencies|
|Selection of limit utilizations|Key date of limit utilizations from ... to|


Output

You use the ABAP list viewer to output a list. This list contains the totals records for the limit utilizations sorted according to limit type and limit characteristics.

Limits that have been exceeded are shown in red.

Choose Goto Partner to branch to the partner data if the partner has been assigned to the limit type as a limit characteristic.

Choose Goto Individual Utilizations can branch to the individual utilizations for totals records. You can see the individual transactions here from which the utilizations originate. Choose Goto Transaction Details to branch to the transactions display from here.

You can display the overview containing data present in the system in different ways. For more information about editing lists, see the documentation for ABAP List Vewer.

**Activities**

- 1. Choose Limit Management Utilizations Overview . The Overview of Limit Utilizations (Totals Records) screen appears.
- 2. Enter the range for the limit type, the currencies and the key date of the evaluation as selection criteria for the limit utilizations.


- 3. Choose Execute.


Regulatory Reporting

**Clearing Threshold Reporting (CTR)**

Use

Non-financial counterparties (NFCs) of derivative financial instruments are not generally required to use a central clearing partner to process these financial transactions. However, NFCs are required to perform clearing only in cases when they have not concluded these financial transactions for risk mitigation and when the rolling average position of these transactions for a period of 30 days exceeds the specified clearing threshold values. Clearing Threshold Reporting (CTR) for Treasury and Risk Management supports NFCs in monitoring their derivative financial transactions that were not concluded for risk mitigation.

The CTR determines the rolling average position for a key date and calculates utilization from this position. If you define a warning level, the system issues a warning message once utilization reaches the warning level.

**Note:**

The system calculates the rolling average position for the relevant financial transactions of the following product categories:

Foreign Exchange Transaction (600)

Interest Rate Swap (620)

FRA (630)

Currency Option (760 with Underlying 600)

Commodity Forward (800)

You can use the BADI_TLR_THRESHOLD_CALC Key Figure Calculation for Clearing Threshold Reporting BAdI to calculate values for financial transactions of these product categories and for all other product categories.

**Prerequisites**

Customizing

First make the following settings in Customizing for Treasury and Risk Management under Transaction Manager General Settings Information System :

- 1. Define Legal Basis

Regulations and laws govern, for example, what companies need to report to authorities. In the SAP system, "legal basis" is used to refer to the regulations or laws that form the basis for reporting for companies.

**Examples**

EMIR

Dodd-Frank Act

- 2. Under Clearing Threshold Reporting, you make the following settings:


- a. Define Organizational Entities for Clearing Threshold Reporting

You perform clearing threshold reporting at the entity level. You assign a legal basis and the related company codes to the clearing threshold entity.

At this level, the system determines the key figures for clearing threshold reporting.

- b. Settings for Clearing Threshold Reporting


You make the settings in this Customizing activity for each legal basis.

For the system to be able to calculate the rolling average position and the position on the key date, you need to make some settings to determine the notional values and to translate foreign currency amounts into the clearing threshold currency. Further, you define instrument groups and assign your financial transactions to them. You specify the clearing threshold values and the warning level.

See also: See the documentation on the Customizing activities.

Master Data

In the application menu under Treasury and Risk Management Transaction Manager Information System Reports

Reporting Clearing Threshold Reporting (CTR) Define Default Values for Risk Mitigation Indicator , you make settings to automatically determine the default value for the "Risk Mitigation" indicator in a financial transaction.

See also:Defining Default Values for Risk Mitigation Indicator (transaction FTR_THRESHOLD_RM_DER)

You use the Set Risk Mitigation Indicator (transaction FTR_THRESHOLD_RM) function to set the indicator for existing financial transactions in accordance with the settings that you have made in the Defining Default Values for Risk Mitigation Indicator activity.

**Process**

After making the necessary Customizing settings, you need to ensure that, in the current Customizing settings, the Risk Mitigation indicator is set on the Administration tab in the financial transaction data for your derivative financial transactions concluded for risk mitigation. In the activity Define Default Values for Risk Mitigation Indicator, you define rules for setting the indicator automatically whenever a financial transaction is created. However, you can deactivate or set this indicator manually in the financial transaction data in cases when it has not been set automatically.

See also:Administration Tab

With the Calculate Key Figures for Clearing Threshold Report (transaction FTR_THRESHOLD_CALC) function, the system calculates and stores the rolling average position and utilization for a key date for the period of the clearing threshold period.

Further, the system calculates the position at the instrument group level on the key date at the level of the clearing threshold entity and also calculates at the level of the clearing threshold entity the utilization of the position as a percentage on the key date for each instrument group.

The Clearing Threshold Report (transaction FTR_THRESHOLD_DISP) returns the rolling average position for all instrument groups for a given key date. Where utilization has reached the warning level is designated in the report.

###### Clearing Threshold Reporting (CTR)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Clearing Threshold Reporting (CTR) | L6 | trm04 p.168 | loio `da01b850c918eb5ee10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/da01b850c918eb5ee10000000a44538d.html?locale=en-US)

Trade Repository Reporting (TRR)

###### Calculate Key Figures for Clearing Threshold Report

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Clearing Threshold Reporting (CTR) > Calculate Key Figures for Clearing Threshold Report | L7 | trm10 p.81 | loio `54c4c1506dbfe85ee10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/54c4c1506dbfe85ee10000000a44538d.html?locale=en-US)

Use

With this function, the system calculates the following key figures on a specific key date and saves the results in the database:

Rolling average position at the level of the financial transaction and instrument group, calculated at the level of the clearing threshold entity

Utilization in percent for every instrument group, calculated at the level of the clearing threshold entity

= ratio of the rolling average position of the instrument group to the clearing threshold value

Position at the instrument group level on the key date, calculated at the level of the clearing threshold entity

Utilization in percent for every instrument group on the key date, calculated at the level of the clearing threshold entity

= ratio of the position of the instrument group on the key date to the clearing threshold value

**Prerequisites**

You need to have made the settings in Customizing for Clearing Threshold Reporting (CTR) under Transaction Manager General Settings Information System Clearing Threshold Reporting (CTR) .


The "Risk Mitigation" indicator needs to have been set in all financial transactions concluded for risk mitigation.

The required foreign currency exchange rates need to have been stored in the market data tables.

**Features**

In the first step, the relevant financial transactions are determined. These are all financial transactions that are effective during the period, that belong to one of the instrument groups, and for which the Risk Mitigation indicator has not been set in the financial transaction data.

To calculate the rolling average position of a financial transaction, the system determines the nominal values of a financial transaction for each day of the clearing threshold period.

In the case of financial transactions with two sides (such as swaps and forex transactions), there are two nominal values. In the Customizing activity Settings for Clearing Threshold Scheme, you have specified in theTransactions with Two Sides: Selection Rules for Nominal Amount area how the nominal amounts are determined for these financial transactions. Under Define Calculation Rule in the Transactions with Two Sides: Selection Rules for Nominal Amount area, you find the following indicators. The indicators are prioritized.

Indicator Use Side with Scheme Currency (priority level 1)

Indicator FX: Use Traded Amount (priority level 2)

Side (outgoing or incoming) (priority level 3)

Depending on your settings, the nominal values for the product categories with two sides are determined as follows:

Foreign Exchange (600)

If the Use Side with Scheme Currency indicator is set and one side uses the currency of the legal basis, this side is applied. If neither side uses the scheme currency but the FX: Use Traded Amount indicator is set, the side with the traded amount (field VTBFHA-AMTINPUT) is applied. If this is not successful either, no nominal amount is set, and the transaction is attributed a zero.

Interest Rate Swap (620)

If the Use Side with Scheme Currency indicator is set, the relevant side is applied. If neither side uses the scheme currency or if the indicator is not set, the side entered in the Side field is applied.

For the other product categories, the nominal values are determined as follows:

FRA (630)

The nominal value is set for each day as the basis amount entered in the FRA.

Currency Option (OTC Option (760) with Underlying Foreign Exchange (600))

For foreign exchange, the nominal value is determined for the underlying (= the underlying foreign exchange transaction). This nominal value is then applied each day for the option.

Commodity Forward (800)

The nominal value is set for each day as the payment amount (VTBFHAPO-BZBETR) in the purchase flow.

Given that the rolling average position is calculated in the clearing threshold currency, the system translates nominal values in a foreign currency into the clearing threshold currency. You also specify in Customizing which foreign currency exchange rate is applied for currency translation.

The sum of the nominal values determined is then divided by the number of days in the period.

For the rolling average position of the instrument group, the system adds together the rolling average positions of the relevant financial transactions.

Utilization in percent for the instrument group expresses the share of the rolling average position of the instrument group in the clearing threshold value of the instrument group (= rolling average position of the IG / clearing threshold value of the IG * 100).

Position at the instrument group level on the key date, calculated at the level of the clearing threshold entity

The nominal values of the relevant financial transactions of an instrument group on the key date are added together.

Utilization in percent on the key date for the instrument group expresses the share of the position of the instrument group on the key date in the clearing threshold value of the instrument group (= position of the IG / clearing threshold value of the IG * 100).

**Activities**

- 1. You call the function by choosing Transaction Manager Information System Reports Reporting Clearing Threshold Reporting (CTR) Calculate Key Figures for Clearing Threshold Report (transaction FTR_THRESHOLD_CALC).
- 2. Select the clearing threshold scheme in the CTR Scheme field.
- 3. Select one or more clearing threshold entities in the fields for the CTR Entity.
- 4. Enter a key date or a period. If you enter a period, the system calculates the key figures for each day of the period.
- 5. In the Processing Options area, you can use the following checkboxes to control the function:


Test Run

By setting this checkbox, you can execute the function as a test run first.

If the test run is successful, you can execute the function as an update run by deselecting this checkbox.

Recalculate Existing Results

If you have already performed this function for the selected key date or key date period, you have to select this checkbox so that the key figures are recalculated again.

Display Results

If you select this checkbox, the system displays the Clearing Threshold Report at the end of the calculation.

If you do not select this checkbox, the system calculates the key figures for the key date(s) and saves them without displaying them. In this case, you display the results in the clearing threshold report (transaction FTR_THRESHOLD_DISP)

- 6. Execute the function.


The system calculates the key figures and saves them (in the case of an update run). If you have requested that the results are displayed, the system displays the clearing threshold report.

If required foreign currency exchange rates are missing or if other errors occur, the system issues an error log.

###### Clearing Threshold Report

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Clearing Threshold Reporting (CTR) > Clearing Threshold Report | L7 | trm10 p.84 | loio `24c5c15027b7e95ee10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/24c5c15027b7e95ee10000000a44538d.html?locale=en-US)

**Use**

The clearing threshold report returns for a given key date and for a clearing threshold entity the rolling average position for individual instrument groups as well as the utilization in percent for each instrument group.

If utilization exceeds the warning level defined in Customizing, the clearing threshold report indicates this also.

Further, you can display for any instrument group the rolling average positions of the relevant financial transactions.

**Prerequisites**

You first need to have calculated the key figures for the key date using the function Calculating Key Figures for Clearing Threshold Report (transaction FTR_THRESHOLD_CALC).

**Activities**

- 1. Choose Transaction Manager Information System Reports Reporting Clearing Threshold Reporting (CTR) Clearing Threshold Report (transaction FTR_THRESHOLD_DISP).
- 2. Select the clearing threshold scheme in the CTR Scheme field.
- 3. Select one or more clearing threshold entities in the fields for the CTR Entity.
- 4. Enter a key date or a period. If you enter a period, the system displays a clearing threshold report for each day of the period.
- 5. Execute the function.


List Output

In the header of the clearing threshold report, the system displays the clearing threshold scheme, the clearing threshold entity, and the key date. Further, an icon at the very top of the header indicates whether utilization of the different instrument groups falls below the warning levels or whether utilization has exceeded these levels in some cases.

In the lines that follow, the report displays - for each instrument group defined for the scheme - the key and the name of the instrument group, the clearing threshold value, the rolling average position of the instrument group, the resulting utilization in percent, and the clearing threshold currency.

At the end of each line, the following icons are used to denote whether utilization of the instrument group is above or below the warning level or whether the clearing threshold value has been exceeded:




When you select an instrument group in a line of the report, the financial transactions belonging to that instrument group appear in the lower part of the screen. Alongside the value with which the financial transaction was entered in the rolling average position, you find the following financial transaction data:

Company Code

Product Type

Name of the Product Type (Text)

Transaction Type

Name of the Transaction Type

Financial Transaction Number

Rolling Average Position

Clearing Threshold Currency

Transaction Structure

Business Partner

Start Date

End Date

Transaction Currency

Clearing Threshold Period

"Changed by BAdI" indicator

Instrument Group

At the end of the column, the total calculated from the rolling average positions of the individual financial transactions is displayed. This is the rolling average position of the instrument group.

You can navigate to the details of the individual financial transactions.

###### Define Default Values for Risk Mitigation Indicator

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Clearing Threshold Reporting (CTR) > Define Default Values for Risk Mitigation Indicator | L7 | trm10 p.85 | loio `aac3c15027b7e95ee10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aac3c15027b7e95ee10000000a44538d.html?locale=en-US)

**Use**

In the calculations for the clearing threshold report, the system does not consider derivative financial transactions that you have concluded to mitigate risks. The Risk Mitigation indicator is set on the Administration tab in the financial transaction data.

You use this function to define rules controlling the automatic selection of the Risk Mitigation indicator when financial transactions are created.

If this indicator is set automatically for a financial transaction for which the indicator did not need to be set, you can correct this manually in the financial transaction data.

**Activities**

- 1. Choose Transaction Manager Information System Reports Reporting Clearing Threshold Reporting (CTR) Define Default Values for Risk Mitigation Indicator (transaction FTR_THRESHOLD_RM_DER).
- 2. Choose New Entries.
- 3. You can use the following criteria to define the rules:

Company Code

Product Category

Product Type

Transaction Type

Counterparty

Commodity ID

Portfolio

At the end of a line, you can set the Risk Mitigation indicator. If you set this indicator for a line, the system sets the Risk Mitigation indicator for all new financial transactions that correspond to the selected criteria, unless there is a specific entry in the table preventing the Risk Mitigation indicator from being set for a particular transaction.

- 4. Save your entries.

###### Set Risk Mitigation Indicator

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Clearing Threshold Reporting (CTR) > Set Risk Mitigation Indicator | L7 | trm10 p.86 | loio `fae93a520a02ba02e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fae93a520a02ba02e10000000a44176d.html?locale=en-US)

**Use**

You use this program to set the Risk Mitigation indicator retrospectively in accordance with the settings made in the activity Define Default Values for Risk Mitigation Indicator.

**Prerequisites**

You need to have defined the default values for the "Risk Mitigation" indicator (transaction FTR_THRESHOLD_RM_DER).

**Activities**

- 1. Call the program under Transaction Manager Information System Reports Reporting Clearing Threshold Reporting (CTR) Set Risk Mitigation Indicator (transaction FTR_THRESHOLD_RM).
- 2. Enter selection criteria if you want to restrict execution of the function to the financial transactions of specific applications (such as foreign exchange, money market, derivatives, or company codes).
- 3. Enter the key date.
- 4. Specify whether the system first displays a list of proposals containing the financial transactions determined or whether the function sets the Risk Mitigation indicator for the financial transactions determined (by means of the Update Directly indicator).
- 5. Execute the function.
- 6. If you have opted for the list of proposals, the system displays all financial transactions (taken from the financial transactions selected on the basis of the selection criteria) that have been determined as risk-mitigating in accordance


- with the settings made in the activity Default Values for the Risk Mitigation Indicator (transaction FTR_THRESHOLD_RM_DER). Select the financial transactions for which you want to set the indicator and choose .
- 7. If you have set the Update Directly indicator, the system sets the Risk Mitigation indicator for all financial transactions (taken from the financial transactions selected on the basis of the selection criteria) that have been determined as riskmitigating in accordance with the settings made in the activity Default Values for the Risk Mitigation Indicator (transaction FTR_THRESHOLD_RM_DER).

###### Trade Repository Reporting (TRR)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) | L6 | trm10 p.87 | loio `57e92b513e422314e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/57e92b513e422314e10000000a44176d.html?locale=en-US)

**Use**

For the purposes of regulating the financial markets, companies are obliged to report their derivative financial transactions to a trade repository, in addition to the central clearing of derivative financial transactions (see also: External Accounts) or in addition to clearing threshold reporting (CTR).

The trade repository reporting functions support you in creating such trade repository messages. Once the process is complete, your trade repository messages are available as a file on the application server for transfer to the trade repository. From the application server, you can also import and interpret incoming messages for the trade repository, and store them in Document Management.

As there are various kinds of trade repository, each having their own regulations for the messages to be sent to them, the functions have flexible settings and can be enhanced in various ways. This is achieved by flexible Customizing as well as by the provision of business add-ins (BAdIs) and flexible derivation tool settings for filling the content or derived content field values of the trade repository objects.

An implementation is delivered for each of the BAdIs. You can use these and, by using the derivation tools, correct how the fields are filled or define your own BAdI implementations.

**Integration**

Use of the functions for trade repository reporting is controlled by the authorization object T_TLR_REP (Authorization for Message Type).

The messages are created from the fields of the trade repository objects. To create them, you can use the Data Medium Exchange Engine (DMEE), which enables you to create the trade repository messages in XML format.

Once created, the trade repository messages are stored in Document Management (CA-DMS).

**Features**

[figure TRM10-F037 - Overview: Trade Repository Reporting (TRR)]

Overview: Trade Repository Reporting (TRR)

Creating and Managing Trade Repository Objects as Data Carriers for Messages

After you have made the Customizing settings for Trade Repository Reporting, the system automatically creates or changes one or more trade repository objects whenever a financial transaction that needs to be reported is created or changed.

**Note:**

You can also report to the trade repository any transactions that you do not manage in the Transaction Manager. For this, you use the Enter External Transactions function. You use this function to create TAROs for the entered transactions. You then manage such TAROs in the same way as TAROs created within the Transaction Manager.

To create the trade repository object, the system - once a financial transaction has been saved - calls method FILL_CONTENT of the active BAdI implementation of the BAdI BADI_TLR_TARO_FILL_CONTENT (Fill Content for Trade Repository Object). The derivation tool is run and then, finally, method CHECK_CONTENT of the BAdI is run. The same occurs for derived content. The system first calls method FILL_DERIVED_CONTENT of the BAdI BADI_TLR_TARO_FILL_DER_CONTENT (Fill Derived Content for Trade Repository Objects). Then the derivation tool is run for the derived content, and, finally, method CHECK_CONTENT of the BAdI is run. In this way, the trade repository fields are filled with values. The check program checks the mandatory fields. If all mandatory fields have been filled and no other errors have occurred, the trade repository object is saved with the status 01 (Created). Otherwise, it acquires the status 02 (Incompletely Created).

The external trade ID is one of the mandatory fields for a TARO. Given that an external transaction may not yet have a unique trade ID at the time when the transaction is reported to the trade repository, you can - the trade repository permitting - initially report the transaction using a unique interim trade ID. Once the external trade ID is known, you need to communicate it to the trade repository. This external trade ID is then used for all subsequent reports. See also:External Trade ID and Interim Trade ID

**Note:**

However, the values determined for the derived content data are not saved persistently.

With the function Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR), you can check the trade repository object created. If you want to change the values determined, you can do so using the following functions:

Change Financial Transaction (transaction FTR_EDIT)

When you save the changes made to a financial transaction, the field values are determined for the trade repository object. When the first TARO has not yet been sent, the current TARO is updated. If the first TARO has already been sent, either one or multiple new TAROs are created, depending on the settings that you have made in Customizing (and depending on how far-reaching the changes are that you have made).

You can also manually change the field values of the TARO content by using the function Change Content in the Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR).

You can protect fields that have been changed manually to prevent their values from being overwritten by the original value. In the case of protected fields, the system notes both the original value of the field before the manual change and the changed value. If an update of the TARO content causes the original value of a protected field to be determined, the field continues to retain the manually changed value. In cases when the update of the TARO content produces a different value to the original value, the system enters the new value in the field.

When you have corrected the errors that led to the TARO being created incompletely (for example, you have made changes to the Customizing settings or you have corrected or added data in the master data of the business partner), you can use one of the following functions to update the field values of the TARO:

In the Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR) using the Complete function

Using the Update Trade Repository Objects function (transaction FTR_TARO_PROCESS)

You use the functions Accept/Reject Clearing (transaction TREA_CLEAR) and Change Counterparty of Financial Transactions (transaction TRTM_CHG_PARTNER) to replace the previous counterparty of a financial transaction with another counterparty (novation) and to create TAROs with which to report the change in counterparty to the trade repository. If, when novation is performed, the financial transaction has not yet been reported to the trade repository (and consequently there is no TARO with the status Sent for this financial transaction), only the existing TARO is updated.

If novation occurs as part of central clearing, the system creates a TARO with the action type 45 (Termination) and a TARO with the action type 10 (New), which is used to report the financial transaction with the new business partner.

If novation occurs during the Change Counterparty of Financial Transactions function, you can decide whether you send a TARO with the action types 45 (Termination) or 40 (Error). In both cases, the system creates a TARO with the action type 10 (New).

Further, it is possible in both functions to assign a new external trade ID to the financial transaction as part of novation.

In the Monitor for Trade Repository Objects, you use the Enter External Transactions function to report to the trade repository any transactions that you do not manage in the Transaction Manager.

If a trade repository needs to receive the current mark-to-market value of the notified financial transactions as well as the collateral values for your financial transactions, in separate messages, you create the necessary trade repository object using the Update Trade Repository function (transaction FTR_TARO_PROCESS).

For more information, see Update Trade Repository Objects.

Sending Trade Repository Objects

Trade repository objects with the status 01 (Created) and 04 (Send Failed) can be sent.

You have the option of sending each trade repository message in an individual file to the trade repository or sending multiple messages in combined files. When you choose the Combined Files function in the Monitor for Trade Repository Objects or in the

Send Trade Repository Objects function, the system combines into one message all selected trade repository messages that have the same company code, relate to the same trade repository, and use the same format tree. For this, you can restrict the size of the file by specifying the maximum number of messages per file in the send parameters.

When you execute the function, the system first calls the method FILL_DERIVED_CONTENT of BAdI BADI_TLR_TARO_FILL_DER_CONTENT (Fill Derived Content for Trade Repository Objects), then the derivation tool for the derived content, and finally method CHECK_CONTENT of the BAdI. The system then calls the BAdI BADI_TLR_TARO_FILE_CREATE (Create File Based on TARO Content).

The file generated as well as all files that you have assigned to the TARO as attachments are stored in Document Management.

The BAdI BADI_TLR_TARO_FILE_SEND (Send File to Trade Repository) is now called. The delivered implementation stores the trade repository message (= file) on the application server. However, you can use an implementation of your own to use alternative output channels.

If the send process has been performed successfully, the TARO acquires the status 03 (Sent). If errors occurred, the TARO acquires the status 04 (Send Failed), and no file is stored on the application server or in DMS.

See also:Send Trade Repository Messages

Importing Incoming Trade Repository Messages

With this function, incoming messages for your trade repository are uploaded from the application server to Trade Repository Reporting, the files are read, and the status of the relevant trade repository object is set accordingly.

Moreover, the imported file is stored in Document Management and assigned to the relevant trade repository object.

When you perform this function, the system calls the implementation of the BAdI BADI_TLR_TARO_INBOUND (Import Data of Incoming Messages for a TARO).

The system sets the status of the TARO depending on the content of the imported file. It can acquire one of the following statuses:

07 (Accepted)

05 (Rejected)

- 09 (Reconciled)

- 10 (Reconciliation Failed)


See also:

Importing Incoming Messages

###### Terms in Trade Repository Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Terms in Trade Repository Reporting | L7 | trm10 p.92 | loio `f6a39b51495edd0de10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f6a39b51495edd0de10000000a441470.html?locale=en-US)

Here you get more details about terms used in trade repository reporting.

|Term|Definition|
|---|---|
|Legal Basis|Regulations and laws govern, for example, what companies need to report to authorities. In the SAP system, "legal basis" is used to refer to the regulations or laws that form the basis for reporting for companies. Examples: EMIR Dodd-Frank Act|
|Trade Repository|A trade repository is the legal person who is recognized as a trade repository (for example, by ESMA) to whom you have to report your derivative financial transactions. Each trade repository has its own regulations for these messages.|
|Trade Repository Objects (TARO)|A trade repository object contains all of the data for a financial transaction that is sent using a trade repository message to the trade repository. A TARO consists of two parts: Administrative Data (TARO Admin) Content Data (TARO Content) See also:Fields of the Trade Repository Object A trade repository object always has an action type that provides information about what type of message is sent to the trade repository. The following action types are implemented in the system: 10 New This action type is used when you report a financial tranaction for the first time. 20 Modification|


|Term|Definition|
|---|---|
| |This action type is used when you report a change to a previously reported financial transaction. 21 Modification (Security Information) The trade repository object reports a change in the details about security information. 22 Modification (Other Changes) The trade repository object reports another change. 25 External Trade ID This action type is used when you subsequently report the external trade ID after having first reported the financial transaction without an external trade ID. See also:External Trade ID and Interim Trade ID 30 Valuation This action type is used when you report the current value of a financial transaction separately. You decide which action type to use in the Customizing settings for the trade repository under Transaction Manager General Settings Information System Trade Repository Reporting Define Settings for Trade Repositories , where you have selected the Update Valuation Separately setting in the Valuation Update field. The TAROs are then created by using the Update Trade Repository Objects function if you have selected the Valuation Update or Update Including Valuation and Collateral settings in the Scope of Update field. 35 Collateral This action type is used when you report the collateral of a financial transaction separately. You decide which action type to use in the Customizing settings for the trade repository under Transaction Manager General Settings Information System Trade Repository Reporting Define Settings for Trade Repositories , where you have selected the setting **Note:** In Customizing for the Trade Repository, under Transaction Manager General Settings Information System Trade Repository Reporting Define Settings for Trade Repositories , under Fields for Separate Modification, you can specify for individual fields the (internal) action type and external action type with which a change to this field is to be reported to the trade repository. When making settings here, you must ensure that you assign a field only once under either Fields for Valuation, Fields for Collateral or Fields for Separate Modification.|


|Term|Definition|
|---|---|
| |Update Collateral Separately in the Collateral Update field. The TAROs are then created by using the Update Trade Repository Objects function if you have selected the Valuation Update or Update Including Valuation and Collateral settings in the Scope of Update field. 40 Error This action type is used when the TARO reports the deletion of a message that was sent in error. 45 Termination This action type is used when a novation has been performed. Consequently, the previous transaction is terminated at the trade repository. 50 Termination at Maturity This action type is used when the TARO reports the termination of an existing contract at term end. 60 Premature Termination This action type is used when the TARO reports the premature termination of an existing contract. A TARO is created with this action type under the following circumstances: The financial transaction is terminated prematurely The financial transaction is relevant for clearing and the clearing partner has approved clearing. See also:Accepting/Rejecting a Clearing You change the counterparty in a financial transaction and you have decided to send a termination TARO. See also: Change Counterparties for Financial Transactions 70 Compression The TARO reports the compression of a contract. 80 Backloading This action type is used when the TARO reports a financial transaction that is relevant for backloading. See also: Backloading 90 Invalid **Note:** This action type is not supported.|
|Trade Repository Message|A file (for example in XML format) that is sent to the trade repository (outgoing message) or has been sent by the trade repository (incoming message).|


|Term|Definition|
|---|---|
| |You can either send each trade repository message in an individual file to the trade repository or send multiple trade repository messages in one combined file.|
|Combined File|You use a combined file to send multiple trade repository messages to a trade repository. When you choose the Combined Files function in the Monitor for Trade Repository Objects or in the function Send Trade Repository Objects, the system combines into one message all selected trade repository messages that have the same company code, relate to the same trade repository, and use the same format tree. For this, you can restrict the size of the file by specifying the maximum number of messages per file in the send parameters.|
|External Trade ID|For messages to the trade repository, a transaction needs to have an external trade ID. This external trade ID needs to be agreed upon by the counterparties and it must identify the transaction uniquely. The external trade ID is stored in the financial transaction data on the Administration tab for a specific legal basis. You use the BAdI FTR_TR_DEFAULT_TRADE_IDBAdI: Default Value for External Trade ID in Financial Transactions to determine external trade IDs when creating a financial transaction. See also: The Administration tab in the financial transaction data Update Transactions with an External Trade ID|
|Interim trade ID|The interim trade ID is used to uniquely identify a financial transaction. You can use it in messages to the trade repository as long as no external trade ID has been officially agreed upon. A precondition for this is that your trade repository allows the use of an interim trade ID. If you want this field to be filled, you need to allow use of interim trade IDs in the Customizing activity Define Settings for Trade Repositories in Customizing for Trade Repository Reporting. The system determines interim trade IDs as follows: If you use the business partner ID type FS0007: Characters 716 of the LEI (of the company code), the company code, and the transaction number are combined to produce the interim trade ID If you use a different business partner ID type: Business partner ID of the company code, the company code, and the transaction number are combined to produce the interim trade ID The system determines the interim trade ID when the transaction is saved. **Note:**|


|Term|Definition|
|---|---|
| |See also:External Trade ID and Interim Trade ID The business partner ID is read from the business partner master data of the business partner that represents the company code. You can assign business partners to company codes in the business partner data (in the Counterparty role) on the Control Data tab in the Partner Is Company Code area.|
|Backloading Cutoff Date|All financial transactions that are active on the backloading cutoff date and all financial transactions that are created after the backloading cutoff date (contract conclusion date) need to be reported to the trade repository. The actual reporting start (reporting start date) generally falls after this date. For this reason, financial transactions that need to be reported can be divided into two groups: Financial transactions that are created as of the reporting start date (contract conclusion date) and are reported to the trade repository using the regular reporting process These financial transactions are reported using a trade repository message with the action type 10New. Financial transactions that were created before the reporting start date and that need to be reported to the trade repository This group contains all financial transactions that are active on the backloading cutoff date as well as financial transactions that are created between the backloading cutoff date and the reporting start date (contract conclusion date). You can report these financial transactions to the trade repository using trade repository messages with the action type 80Backloading. To be able to create backloading messages, you need to enter the sending start date in the Customizing activity Define Settings for Trade Repositories. If you want to send backloading messages to the trade repository ahead of the official reporting start date, you need to specify a sending start date that falls before the reporting start date. Backloading-relevant financial transactions can be divided into the following groups: Financial transactions that are active on the reporting start date and that have a contract conclusion date that falls before the backloading cutoff date. Financial transactions that are active on the reporting start date and that have a contract conclusion date that falls after the backloading cutoff date. Financial transactions that end before the reporting start date but after the backloading cutoff date.|


|Term|Definition|
|---|---|
| |You enter the backloading cutoff date in the Customizing activity Define Legal Basis. You use the function Update Trade Repository Objects (transaction FTR_TARO_PROCESS) to create the trade repository objects for backloading-relevant financial transactions. In this function, you can select the different groups individually and, if you so wish, report their transactions to the trade repository on different dates. **Example:** For EMIR, the backloading cutoff date is August 16, 2012.|
|Sending Start Date|From the sending start date, the system creates trade repository objects with the action type 80Backloading for new backloadingrelevant financial transactions, and you can use the function Update Trade Repository Objects (transaction FTR_TARO_PROCESS) to create trade repository objects with the action type 80Backloading for existing backloading-relevant financial transactions. Financial transactions that are considered relevant for backloading comprise all financial transactions that are active on the backloading cutoff date and all financial transactions that are created between the backloading cutoff date and the reporting start date (contract conclusion date). If the sending start date has not yet been reached, the system does not create any trade repository objects. The sending start date is selected by you and needs to meet the following condition: Backloading cutoff date sending start date reporting start date **Note:** If you do not set the sending start date, the system creates trade repository objects for new financial transactions as of the reporting start date. You cannot create TAROs for financial transactions that already exist on the reporting start date. However, it may be useful to do so in the following circumstances: When you have already reported these financial transactions to the trade repository. When no reporting-relevant financial transactions exist before the reporting start date.|
|Reporting Start Date|The regular trade repository reporting process starts on the reporting start date. For financial transactions that are created after this date, trade repository objects with the action type 10New are created. You enter the reporting start date in the Customizing activity Define Legal Basis.|


|Term|Definition|
|---|---|
| |**Example:** For EMIR, the reporting start date is February 12, 2014.|

###### Customizing for Trade Repository Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Customizing for Trade Repository Reporting | L7 | trm10 p.98 | loio `ec8e9a51e6aadf0de10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ec8e9a51e6aadf0de10000000a441470.html?locale=en-US)

Before you can use the functions of trade repository reporting, you have to make settings in Customizing.

Under Treasury and Risk Management Transaction Manager General Settings Information System Define Legal Basis , you need to define the legal basis.

**Example:**

EMIR

Dodd-Frank Act

Under Treasury and Risk Management Transaction Manager General Settings Information System Assign Countries/Regions to Legal Basis , assign to each legal basis the countries/regions for which it is valid.

The following Customizing activities are available in the SAP reference IMG under Treasury and Risk Management Transaction Manager General Settings Information System Trade Repository Reporting :

Define Trade Repository

Define Product Classifications

Define Settings for Trade Repository

**Note:**

If you want to use logical path names, define these under SAP Customizing Implementation Guide SAP NetWeaver Application Server System Administration Platform-Independent File Names Cross-Client Maintenance of File Names and Paths .

- 1. Choose New Entries.
- 2. Enter the following two lines:
- 3. Save your entries.
- 4. Select the line FTRM_TARO_IMPORT, and choose Assignment of Physical Paths to Logical Path.


|Logical File Path|Name|
|---|---|
|FTRM_TARO_IMPORT|Import of trade repository|
|FTRM_TARO_SEND|Send to trade repository|
|FTRM_TARO_ERROR|Imported files containing errors|
|FTRM_TARO_ARCHIVE|Files that have been imported and processed successfully|


- 5. Choose New Entries, and, in the Syntax group field, enter UNIX (all Unix platforms), and, in the Physical Path field, enter /tmp/<FILENAME>.
- 6. Save your entries.
- 7. Choose Logical File Name Definition, Cross-Client.
- 8. Choose New Entries.
- 9. Create the following file names:


Logical file: FTRM_TARO_IMPORT

Name TRM: Received from trade repository

Data format DIR

Application area TR

Logical path FTRM_TARO_IMPORT

Logical file: FTRM_TARO_SEND

Name TRM: Send to trade repository

Data format DIR

Application area TR

Logical path FTRM_TARO_SEND

Logical file: FTRM_TARO_ERROR

Name TRM: Error

Data format DIR

Application area TR

Logical path FTRM_TARO_ERROR

Logical file: FTRM_TARO_ARCHIVE

Name TRM: Imported and processed successfully

Data format DIR

Application area TR

Logical path FTRM_TARO_ARCHIVE

Save your entries.

Managing Trade Repository Objects

Notes on implementation

BAdI: Fill Content for Trade Repository Object (BADI_TLR_TARO_FILL_CONTENT)

This BAdI is delivered to you with an implementation. You can use this implementation.

If you only want to fill some of the TARO field values differently, you can define rules for determining the field values in Customizing activities Determine Field Values for TARO Content Data and Determine Field Values

for TARO Derived Content Data. You can also create your own BAdI implementations for filling the field values.

BAdI: Fill Derived Content Based on TARO Content (BADI_TLR_TARO_FILL_DER_CONTENT)

This BAdI is delivered to you with an implementation. You can use this implementation.

If you only want to fill some of the TARO field values differently, you can define rules for determining the field values in Customizing activities Determine Field Values for TARO Content Data and Determine Field Values for TARO Derived Content Data. You can also create your own BAdI implementations for filling the field values.

BAdI: Create File Based on TARO Content (BADI_TLR_TARO_FILE_CREATE)

This BAdI is delivered to you with an implementation. You can use this implementation.

For the creation of XML files by the implementation, the necessary settings in the Data Medium Exchange Engine (DMEE) have been delivered.

See also: Send Trade Repository Objects and also SAP Notes 1849910 and 1853746 .

Check whether the XML messages created using the implementation delivered are accepted by your trade repository. If this proves not to be the case, you have to create your own BAdI implementation.

BAdI: Send File to Trade Repository (BADI_TLR_TARO_FILE_SEND)

This BAdI is delivered to you with an implementation. You can use this implementation.

It defines the output channel for the trade repository messages.

The system uses the default implementation to write to the application server the trade repository notification (= file) that was created using the BAdI: Create File Based on TARO Content (BADI_TLR_TARO_FILE_CREATE).

You can use this BAdI to change the system behavior and create your own implementation. In this way, you can use alternative output channels.

BAdI: Get Data from Incoming Messages for TARO (BADI_TLR_TARO_INBOUND)

This BAdI is delivered to you with an implementation. You can use this implementation.

Test whether the incoming messages are correctly interpreted by your trade repository. Should this not to be the case, you have to create your own BAdI implementation.

Determination of field values for trade repository objects

(Derviation tools)

During creation of the TAROs, the system fills the fields by calling the BAdIs BAdI: Fill Content for Trade Repository Object (BADI_TLR_TARO_FILL_CONTENT) or BAdI: Fill Derived Content Based on TARO Content (BADI_TLR_TARO_FILL_DER_CONTENT) and then by calling the derivation tools. You can also use the derivation tools to fill the fields of the TARO with values. If you are generally satisfied with how the BAdIs are implemented in the standard delivery but you would like to alter how some fields are filled, you can define rules for this.

Determine Field Values for TARO Content Data

Determine Field Values for TARO Derived Content Data

Under Treasury and Risk Management Transaction Manager General Settings Transaction Management BAdI: Default Value for External Trade ID in Financial Transactions , there is a BAdI that you can use to fill the External Trade ID field in the financial transaction data (on the Administration tab).

To store the incoming and outgoing trade repository messages in Document Management (DMS), you need to make the settings in DMS that have been delivered.

See also: Customizing Settings in DMS for TRM Documents and SAP Note 1849910

See the documentation on the Customizing activities.

###### Fields of the Trade Repository Object

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Fields of the Trade Repository Object | L7 | trm10 p.101 | loio `86d52b513e422314e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/86d52b513e422314e10000000a44176d.html?locale=en-US)

You use the fields of the trade repository object to create messages to be sent to a trade repository.

Since each trade repository has its own rules governing the creation of messages, the number of fields listed here is greater than the number of fields that would be derived from the technical description for EMIR.

The following table provides an overview of the fields of the trade repository object. For each field, you can see the corresponding field under EMIR, the meaning of the field or the expected values, and how the field is filled by the delivered implementations BADII_TLR_TARO_FILL_CONTENT and BADII_TLR_TARO_FILL_DER_CNT.

**Note:**

And since each trade repository has its own regulations, you can add more fields and use a BAdI to fill them with values. (To do this, you need to create your own BAdI implementation.) However, you can also use the derivation tools to change how the fields are filled so that the requirements for the relevant trade repository are met.

You can also use these fields to create trade repository messages using a different legal basis to EMIR. Given that a different legal basis may require different fields, you can add these fields and use a BAdI to fill them with values, or you can use the derivation tools to change how the fields are filled so that the requirements for the relevant trade repository are met.

Mandatory Fields in the Delivered Implementation:

In the delivered implementations, the check methods of the BAdIs check whether the following fields are filled. If one of the mandatory fields is not filled, the trade repository object acquires the status 02 Incompletely Created.

External Trade ID or Interim Trade ID

See also: External Trade ID and Interim Trade ID

Counterparty ID and the related ID type

Other counterparty ID and the related ID type

The Domicile Not in Validity Area of LB field must be filled.

If the broker ID is specified, the relevant identifier must also be filled.

If the beneficiary ID is specified, the relevant identifier must also be filled.

If the ID of the clearing party is specified, the relevant identifier must also be filled.

If the ID of the central counterparty is specified, the relevant identifier must also be filled.

|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|Administrative Data| | | |


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|The values in these fields are filled by SAP. You cannot change these field values. However, all of the fields can be used for the creation of trade repository messages.| | | |
|Company Code|Internal Data|Identifying a TARO Uniquely in the System|From Transaction Data|
|Transaction|Internal Data| |From Transaction Data|
|Trade Repository|Internal Data| |The trade repository is derived on the basis of the settings made in the Customizing activity Define Settings for Trade Repositories.|
|TARO Number|Internal Data| |TAROs for a financial transaction are numbered sequentially.|
|External Trade ID|Table 2, Section 2b, Field 8|A unique ID at the European level, delivered from the reporting company. If there is no unique ID, a unique code needs to be generated and agreed upon with the counterparty for that transaction.|Value from the financial transaction, Administration tab in the Trade Repository Reporting area. You can fill the field by using the BAdI FTR_TR_DEFAULT_TRADE_ID (BAdI: Default Value for External Trade ID in Financial Transaction) or enter the value manually in the financial transaction.|
|Interim Trade ID| | |The interim trade ID is used to uniquely identify a financial transaction. You can use it in messages to the trade repository as long as no external trade ID has been officially agreed upon. If you want this field to be filled, you need to allow use of interim trade IDs in the Customizing activity Define Settings for Trade Repositories in Customizing for Trade Repository Reporting. The system determines interim trade IDs as follows: If you use the business partner ID type FS0007: Characters 7-16 of the LEI (of the company code), the company|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |code, and the transaction number are combined to produce the interim trade ID If you use a different business partner ID type: Business partner ID of the company code, the company code, and the transaction number are combined to produce the interim trade ID The system determines the interim trade ID when the transaction is saved. **Note:** The business partner ID is read from the business partner master data of the business partner that represents the company code. You can assign business partners to company codes in the business partner data (in the Counterparty role) on the Control Data tab in the Partner Is Company Code area.|
|Planned Send Date|Internal Data| |The planned send date is derived from the action type of the TARO: Action Type -> Date 10 -> Contract date (from table VTBFHAZU, field DVTRAB) 20 -> Contract date (from table VTBFHAZU, field DVTRAB) 30 -> Key date of the valuation/security 35 -> Key date of the valuation/security 40 -> System date 50 -> Final maturity date|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |60 -> System date 80 -> Contract conclusion date for the transaction contract; if the contract conclusion date falls before the sending start date for the trade repository, it is set as the sending start date|
|Sending Date|Internal Data| |Filled with the date on which the TARO switches to the status Sent or on which the TARO was created.|
|Status (of the TARO)|Internal Data| |A TARO can have the following status: 01 Created 02 Incompletely Created 03 Sent 04 Send Failed 05 Rejected 06 Rejection Accepted 07 Accepted 08 Obsolete 09 Reconciled 10 Reconciliation Failed 20 Invalid See also: Status Management for Trade Repository Objects |
|Action Type|Section 2i, Field 58|N New M Change E Error C Deletion/Termination Z Compression V Valuation Update O Other |The action type explains the cause for a trade repository object: 10 New The TARO reports a derivative for the first time. 20 Change The TARO reports a change for a derivative that has already been reported. 25 External Trade ID|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |TARO reports the external trade ID by External Trade ID and Interim Trade ID 30 Valuation The TARO reports the current market value of a derivative. 35 Security The TARO reports the current value of the security for a financial transaction or the current value of the security portfolio. 40 Error The TARO is used when an error (such as an entry error) has occurred and the transaction needs to be deleted at the trade repository. 45 Notice The TARO is used when a novation has been performed. The previous transaction is declared as terminated. 50 Termination at Term End The TARO reports the end of a financial transaction upon maturity. 60 Premature Termination The TARO reports a premature termination of the financial transaction. 70 Compression Not supported 80 Backloading|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |The TARO is created by the backloading function. 90 Invalid The TARO is created during import if there is no TARO for an incoming message. The BAdI implementation derives from the action type which format tree ID is used in the Data Medium Exchange Engine (DMEE) for the XML message: For the action types 10, 20, and 25, the format tree ID TARO_XT is used. For the action type 30, the format tree ID TARO_VU is used. For the action type 35, the format tree ID TARO_CU is used. For the action types 40, 45, 50, and 60, the format tree ID TARO_TT is used. For the action type 80, the format tree ID TARO_BK is used.|
|Comment|Internal Data| |Not filled In the TARO Monitor, you can enter a comment for the TARO.|
|Investment|Internal Data| |Not filled In the TARO Monitor, you can upload a file for the TARO.|
|Contract Conclusion Date|Internal Data| |From Transaction Data|
|Time of Contract Conclusion|Internal Data| |From Transaction Data|
|Product Type|Internal Data| |From Transaction Data|
|Transaction Type|Internal Data| |From Transaction Data|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|Created By|Internal Data| |From Transaction Data|
|Creation Date|Internal Data| |From Transaction Data|
|Last Changed By|Internal Data| |From Transaction Data|
|Last Changed On|Internal Data| |From Transaction Data|
|Last Changed At|Internal Data| |From Transaction Data|
|Content Data| | | |
|Counterparty Data| | | |
|Mark-to-Market Value of the Contract|Table 1, Field 17|Mark-to-Market Value or Markto-Model Value of the Contract Test|The system reads the values from table VTVBAR. Here you can enter the MtM value manually using transaction JBNPV or calculate it using transaction TPM60.|
|Currency of the Mark-to-Market Value|Table 1, Field 18| |Currency of the Mark-to-Market Value|
|Last Valuated On (UTC)|Table 1, Field 19| |First Created On date of last valuation for the contract available in table VTVBAR.|
|Last Valuated At (UTC)|Table 1, Field 20| |Time for the date of the last valuation|
|Last Valuation Type|Table 1, Field 21|Specifies how the mark-tomarket value is determined: M Mark-to-Market O Mark-to-Model|Always filled by the system with M.|
|Collateralization|Table 1, Field 22|Provides information about whether collateralization has occurred. U Without Collateralization PC Partially Collateralized OC One-Sided Collateralization FC Fully Collateralized|Always U Without Collateralization|
|Collateral Portfolio|Table 1, Field 23|Y Yes N No|Not filled|
|Collateral Portfolio Code|Table 1, Field 24|Unique code for the collateral portfolio|Not filled|
|Collateral Value|Table 1, Field 25|Total Value of Collateral|Not filled|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|Collateral Currency|Table 1, Field 26|Currency of the Collateral Value|Not filled|
|General Data| | | |
|Counterparty| | |Contains the ID of the counterparty for the financial transaction. This field is used to read the unique ID (such as the BIC or LEI) from the business partner data. This ID is then stored in the derived content data (see under Derived Content: Other Counterparty). **Note:** In the Customizing activity Define Settings for Trade Repositories, you specify which unique ID is selected.|
|Broker| | |Contains the ID of the broker for the financial transaction. This field is used to read the unique ID (such as the BIC or LEI) from the business partner data. This ID is then stored in the derived content data (see under Derived Content: Broker ID).|
|Clearing Member| | |Filled with the internal ID of the counterparty for all financial transactions that have the clearing status Cleared. This field is used to read the unique ID (such as the BIC or LEI) from the business partner data. This ID is then stored in the derived content data (see under Derived Content: Clearing Member ID).|
|Central Clearing Partner| | |Not filled by SAP. If you want to fill this field, you need to enter the internal ID of the central clearing partner to apply this field in the derivation of the unique ID, such as the BIC or LEI, which is then stored in the derived content data (see|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |under Derived Content: Central Clearing Partner ID).|
|Contract Type Data| | | |
|Taxonomy|Table 2, Section 2a, Field 1| |Derives the value from the settings made in the Customizing activity Define Settings for Trade Repositories under Enter Taxonomies for Product Classifications.|
|Product ID 1|Table 2, Section 2a, Field 2| |Filled with the value of the superordinate product classification type of the product classification type assigned in the activity Define Settings for Trade Repositories. If you have assigned a product classification that does not have a superordinate product classification type, the value of the assigned product classification type is entered in the field.|
|Product ID 2|Table 2, Section 2a, Field 3| |Filled with the value of the product classification type assigned in the activity Define Settings for Trade Repositories. If you have assigned in this activity a product classification type that does not have a superordinate product classification type, no entry is made in this field.|
|Underlying|Table 2, Section 2a, Field 4| |Not filled|
|Notional Currency 1|Table 2, Section 2a, Field 5| |Filled with the currency of the outgoing side (if one exists). Otherwise, the field is filled with the transaction currency. Forward Exchange Transactions and Currency Options: Notional currency 1 is the currency of the transaction, appearing first in the|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |alphabetically sorted list of ISO currency codes. **Note:** In the case of a currency option, the currency is derived from the underlying.|
|Notional Currency 2|Table 2, Section 2a, Field 6| |Filled with the currency of the incoming side (if one exists). Otherwise, the field is not filled. Forward Exchange Transactions and Currency Options: Notional currency 2 is the currency of the transaction, appearing second in the alphabetical list of ISO currency codes. **Note:** In the case of a currency option, the currency is derived from the underlying.|
|Settlement Currency|Table 2, Section 2a, Field 7| |Currency of the cash settlement flow Forward Exchange Transactions and Currency Options: As the settlement currency, notional currency 1 is selected. In the case of a cash settlement (such as in the case of NDFs), the currency of the cash settlement flow is applied.|
|Transaction Data| | | |
|Asset Class|Not a field in EMIR, but may be required by trade repository| |Derives the asset class from the product type, the transaction type, and the trade repository from the settings made in Customizing for Treasury and Risk Management. Here, you define the product classifications under Transaction Manager General Settings Information System Trade Repository Reporting |


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |Define Product Classifications  . You then assign product types to the defined product classifications. In the activity Define Settings for Trade Repositories, you assign the relevant product classifications to the trade repositories.|
|Venue of Execution|Table 2, Section 2b, Field 10| |This field is filled with the stock exchange (table VTBFHAPO, field RHANDPL) if one of the following conditions is filled: The contract type of the transaction is 2 Securities. The product category of the transaction is 700 Futures. The product category of the transaction is 750 Listed Options. If the RHANDPL field is not filled in these cases, the XOFF field is filled. For all other contract types and product types, the field is filled with XXXX.|
|Compression|Table 2, Section 2b, Field 11| |Not filled|
|Price|Table 2, Section 2b, Field 12| |Security Transactions: Filled with the security price (percentage-quoted or unitquoted) of the financial transaction. Currency Options: Filled with the option premium amount. Forward Exchange Transactions: For these transaction, the price is not relevant and is filled with 0.00. See also: SAP Note 1853746 |


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|Price Quotation|Table 2, Section 2b, Field 13| |Filled with the value 100 for percentage-noted security prices Filled with the currency unit of the record (contained in the SRUNIT field) for unitquoted securities and in all other cases in which an amount has been entered in the Price field Filled with NA when the Price field has been filled with the value 0.00|
|Notional Amount|Table 2, Section 2b, Field 14|Original Nominal Amount|Filled with the original payment amount of the financial transaction. For Forward Exchange Transactions and Currency Options: Filled with the original amount in notional currency 1. [also in the case of a cash settlement (such as for NDFs)]|
|Current Notional Amount| |Current Notional Amount|Filled with the current notional amount in notional currency 1, that is, all flows that change notional amounts are considered. SAP Note 2100303 |
|Price Multiplier|Table 2, Section 2b, Field 15| |Filled with 1.|
|Quantity|Table 2, Section 2b, Field 16| |Filled with 1.|
|Advance Payment Amount|Table 2, Section 2b, Field 17| |Filled with the payment amount of another flow that was paid in advance.|
|Currency of Advance Payment Amount|Table 2, Section 2b, Field 17| |Currency in which the advance payment was made.|
|Delivery Type|Table 2, Section 2b, Field 18|Specifies how the contract was fulfilled: C Cash Settlement P Physical Exercise|Derived from "Settlement" indicator.|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | |O Optional for Counterparty| |
|Execution Date (UTC)|Table 2, Section 2b, Field 19| |Filled with the date on which the contract is concluded for the financial transaction (UTC).|
|Execution Time (UTC)|Table 2, Section 2b, Field 19| |Filled with the time at which the contract is concluded for the financial transaction (UTC).|
|Validity Date|Table 2, Section 2b, Field 20| |Filled with the start of the term for the financial transaction.|
|Maturity Date|Table 2, Section 2b, Field 21|Original maturity of the financial transaction (not the date of a premature termination/notice of the transaction)|Filled with the end of the term for the financial transaction.|
|Termination Date|Table 2, Section 2b, Field 22|Termination date of the contract. If the termination date is the same as the maturity, this field remains empty.|Filled with the OTC termination date.|
|Settlement Date|Table 2, Section 2b, Field 23| |Filled with the exercise date. Forward Exchange Transactions and Currency Options: Filled with the payment date (or, in the case of currency options, with the payment date of the underlying)|
|Master Agreement Type|Table 2, Section 2b, Field 24| |Filled with the value in the Master Agreement field (on the Administration tab).|
|Master Agreement Version|Table 2, Section 2b, Field 25|Refers to the year of the master agreement version.|The year is read from the master agreement data.|
|Transaction Reference Number| |Transaction Reference Number or Reporting Tracking Number|Can be filled with a string of up to 40 characters. Not filled in the standard implementation; you may need to fill the field with "NA" using the derivation tool.|
|Risk Mitigation/Reporting Data| | | |
|Confirmation Date (UTC)|Table 2, Section 2c, Field 26| |The date of the confirmation or counterconfirmation, depending on which is the latest.|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|Confirmation Time (UTC)|Table 2, Section 2c, Field 26| |Time relating to the date of the confirmation|
|Confirmation Means|Table 2, Section 2c, Field 27|Specifies whether and how the contract was confirmed: Y Non-electronically confirmed N Non-Confirmed E Electronically confirmed|If the confirmation date is not filled, this field is filled with the value N; otherwise, E is entered for the confirmation.|
|Clearing Data| | | |
|Clearing Obligation|Table 2, Section 2d, Field 28|Specifies whether the reported contract is subject to the clearing obligation. Y Yes N No|Derived from the clearing status of the financial transaction. If the status is 0 Not Relevant for Clearing, the field is filled with the value N; otherwise, with the value Y.|
|Cleared|Table 2, Section 2d, Field 29|Y Yes N No|Derived from the clearing status of the financial transaction. Accepted = Y|
|Clearing Date (UTC)|Table 2, Section 2d, Field 30|Time when the clearing partner accepted clearing.|Date when the clearing partner accepted clearing.|
|Clearing Time (UTC)|Table 2, Section 2d, Field 30| |Time when the clearing partner accepted clearing.|
|ID of the Central Counterparty|Table 2, Section 2d, Field 31|BIC or LEI of the Central Counterparty|Not filled|
|Intragroup|Table 2, Section 2d, Field 32|Specifies whether the transaction is an intragroup transaction. Y Yes N No|Filled with the value Y if a mirror transaction (reference type MIR) exists. Otherwise, the field is filled with the value N.|
|Interest Data| | | |
|Fixed Rate of Leg 1|Table 2, Section 2e, Field 33| |Filled with the percentage of the condition.|
|Fixed Rate of Leg 2|Table 2, Section 2e, Field 34| |Filled with the percentage of the condition.|
|Fixed Rate: Day Count|Table 2, Section 2e, Field 35| |Filled with the interest calculation method of the condition of the financial transaction.|
|Fixed Rate: Payment Frequency|Table 2, Section 2e, Field 36| |Filled with the payment frequency of the condition in|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |months or days.|
|Floating Rate: Payment Frequency|Table 2, Section 2e, Field 37| |Filled with the payment frequency of the condition in months or days.|
|Floating Rate: Reset Frequency|Table 2, Section 2e, Field 38| |Filled with the payment frequency of the interest adjustment condition in months or days.|
|Floating Rate of Leg 1|Table 2, Section 2e, Field 39| |Reference interest rate of the condition|
|Floating Rate of Leg 2|Table 2, Section 2e, Field 40| |Reference interest rate of the condition|
|Foreign Currency Data| | | |
|Currency 2|Table 2, Section 2f, Field 41| |Filled with the following currency. Forward Exchange Transactions and Currency Options: Currency 2 is derived from the alphabetically sorted list of the ISO currency codes involved in the transaction (or, in the case of currency options, it is derived from the underlying). The currency appearing second in the sorted list is selected as currency 2. In the case of a cash settlement, currency 2 is the currency that is not the settlement currency.|
|Exchange Rate 1|Table 2, Section 2f, Field 42| |Filled with the spot rate of the transaction.|
|Forward Rate|Table 2, Section 2f, Field 43| |Filled with the forward rate of the transaction.|
|Exchange Rate Basis|Table 2, Section 2f, Field 44| |The currency pair leading currency / following currency is displayed.|
|Option Data| | | |
|Option Type|Table 2, Section 2h, Field 55|Displays whether the contract is a put or a call.|Derived from the "Put/Call" indicator set for the financial transaction: 1 Put -> P|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | | |2 Call -> C|
|Option Style|Table 2, Section 2h, Field 56|Provides details about how the option is exercised: A American B Bermudan (multiple exercise times) E European S Asian |Derived from the option style of the financial transaction: 1 European -> E 2 American -> A |
|Strike Currency|Table 2, Section 2h, Field 57| |Filled with the strike currency.|
|Strike Price|Table 2, Section 2h, Field 57| |Filled with the strike amount of the option.|
|Derived Business Partner Data| | | |
|Counterparty ID|Table 1, Field 2|Identifier of the reporting company LEI or BIC or an interim entity identifier or a client code|Not filled by SAP|
|Counterparty ID Identifier| | |The abbreviation specifies which ID code applies. Examples: LEI BIC|
|ID of the Other Counterparty|Table 1, Field 3|Identifier of the other business partner LEI or BIC or an interim entity identifier or a client code|LEI, BIC, and so on, of the counterparty **Note:** In the Customizing activity Define Settings for Trade Repositories, you specify which unique ID is selected.|
|Other Counterparty ID Identifier| | |The abbreviation specifies which ID code applies. Examples: LEI BIC|
|Counterparty Name|Table 1, Field 4| |Not filled|
|Counterparty Domicile|Table 1, Field 5| |Not filled|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|Counterparty Corporate Sector|Table 1, Field 6| |Not filled|
|Counterparty Financial Sector|Table 1, Field 7|Display whether the reporting company is a financial or nonfinancial counterparty (NFC). F Financial Counterparty N Non-Financial Counterparty (NFC)|Not filled|
|Broker ID|Table 1, Field 8|If the broker involved is not a business partner.|Filled when the transaction has a partner in this role assigned on the Partner Assignment tab.|
|Identifier of the Broker ID| | |The abbreviation specifies which ID code applies. Examples: LEI BIC|
|ID of the reporting entity|Table 1, Field 9|If the entity that is required to report has delegated communication of the message to a third party, this field must be filled with the LEI or the BIC of the reporting entity.|Not filled|
|Identifier for the ID of the reporting entity| | |The abbreviation specifies which ID code applies. Examples: LEI BIC|
|Clearing Member ID|Table 1, Field 10|If the reporting entity is not a clearing member, the LEI or BIC of the relevant clearing member needs to be entered here.|The system fills this field with the counterparty of the financial transaction (= counterparty of the clearing account) for all financial transactions for which clearing has been performed.|
|Identifier of the Clearing Member ID| | |The abbreviation specifies which ID code applies. Examples: LEI BIC|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
|Beneficiary ID|Table 1, Field 11|LEI or BIC of the party subject to the rights and obligations arising from the contract when this party is not a counterparty of this contract.|Not filled|
|Identifier of the Beneficiary ID| | |The abbreviation specifies which ID code applies. Examples: LEI BIC|
|Trading Capacity|Table 1, Field 12|Specifies whether the reporting business partner has concluded the financial transaction as the principal (P) or as the agent (A).|Always filled with P.|
|Counterparty Side|Table 1, Field 13|Specifies whether the contract is a buy or a sell. B Buy S Sell |This field is filled on the basis of the value of the transaction category of the financial transaction: 100 = Buy -> B 200 = Sell -> S 300 = Issue: Placement -> B 400 = Issue: Buyback -> B 500 = Close Transaction -> S 600 = Forward -> B For Forward Exchange Transactions: The counterparty side is obtained from the sorted list of ISO currencies. The party that receives the first currency is the buyer, the other is the seller. For Currency Options: The side is determined from the transaction type: the party buying is the buyer and the other party is the seller.|
|Domicile Not in Validity Area of LB|Table 1, Field 14|Specifies whether the other counterparty is domiciled outside the EU.|Filled with N when the country/region of the other counterparty is a member state|


|Field in the Trade Repository Object|Field in EMIR|Meaning (Acc. to EMIR)|Data Filling By delivered BAdI implementations|
|---|---|---|---|
| | |Y Yes N No|the EU. Otherwise, the field is filled with the value Y. To fill the field, the system applies the settings made in the Customizing activity Assign Countries/Regions to Legal Basis.|
|Linked to Commercial Activity|Table 1, Field 15|Provides information about whether the transaction is linked directly with exercising the commercial activity or whether it is purely a financial transaction. If the reporting entity is a financial counterparty, the field must remain empty. Y Yes N No|Filled with Y in the case of financial transactions for which the Risk Mitigation indicator is set (on the Administration tab in the financial transaction). Otherwise, the field is filled with the value N.|
|Clearing Threshold|Table 1, Field 16|Provides information about whether the reporting company is above or below the clearing threshold. Y Above N Below|Not filled|
|Derived Content Data| | | |
|You can use the derived content data structures for your own fields. You can fill the fields using the BAdI and the derivation tool provided.| | | |

###### External Trade ID and Interim Trade ID

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > External Trade ID and Interim Trade ID | L7 | trm10 p.119 | loio `6eace6527676b367e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6eace6527676b367e10000000a441470.html?locale=en-US)

**External Trade ID**

For notifications to the trade repository, a transaction needs to have an external trade ID. This external trade ID needs to be agreed upon by the counterparties and it must identify the transaction uniquely.

The external trade ID is stored in the financial transaction data on the Administration tab for a specific legal basis.

You use the BAdI FTR_TR_DEFAULT_TRADE_ID (BAdI: Default Value for External Trade ID in Financial Transactions) to determine external trade IDs when creating a financial transaction.

See also:

The Administration tab in the financial transaction data

**Update Transactions with an External Trade ID**

The external trade ID is one of the mandatory fields for a TARO.

**Note:**

For foreign exchange transactions that are relevant for trade repository reporting, you can also use the Correspondence Framework to obtain the external trade ID from the counterconfirmation notification (MT300) received from your counterparty. (The prerequisite for this is that, in the Customizing activity Assign Attributes for Business Partner Groups, the Get Values from Counterconfirmation indicator is set for the business partner group in the Inbound Correspondence area.)

Validation of the External Trade ID

It may be that rules are set in a legal basis (for example, EMIR) to which the external trade ID must correspond.

If in Customizing, under Define Legal Basis, you specify a Start Date for Validation, then when you enter an external trade ID, the system uses the following functions from this date to validate the entered external trade ID:

Create and edit financial transactions (transactions FTR_CREATE and FTR_EDIT) or the corresponding BAPIs

Update transactions with an external trade ID (transaction FTR_TARO_TRADE_ID)

Import MT300 SWIFT messages (transaction FTR_IMPORT and FTR_SWIFT_IMPORT)

Manual entry of correspondence objects (transaction FTR_COCREATE)

Accept clearing (transaction TREA_CLEAR)

Change counterparty of financial transaction (transaction TRTM_CHG_PARTNER)

To do this, the BAdI BADI_TLR_TRADE_ID_CHECK (Legal-Base-Specific Checks for Trade ID) is called. For this BAdI, a standard delivery is provided, which performs the following checks:

The external trade ID can contain only numbers, letters, and the following special characters:

Colon

Period

Minus

Underscore

The special characters must not be at the start or the end of an external trade ID.

An external trade ID can only be used once; even if the associated trade was deregistered from the trade repository, this external trade ID cannot be reused.

The BAdI issues the following messages:

- Message class FTR_GUI, no. 574: External trade ID &1 not valid. Observe validation rules for &2

- Message class FTR_GUI, no. 575: External trade ID &1 already registered. No longer usable


In Customizing, under Change Message Control, you can control whether the messages are to be issued as warnings (default setting) or as error mesages.

If you set the messages as error messages, the entry process is stopped in the event of an external trade ID with errors.

**Note:**

Exception: When importing SWIFT message MT300, the assignment of the imported messages is not halted, but the external trade ID is not assigned to the trade. Without an external trade ID, the associated trade repository object is created incompletely and cannot be set. In this case, you must correct the external trade ID later.

If you set the messages as warnings, in the event of an external trade ID with errors, the trade repository object is created with the faulty external trade ID, but has Incompletely Created status.

**Interim Trade ID**

Given that an external transaction may not yet have a unique trade ID at the time when the transaction is reported to the trade repository, you can - the trade repository permitting - initially report the transaction using a unique interim trade ID.

The interim trade ID is used to uniquely identify a financial transaction. You can use it in notifications to the trade repository as long as no external trade ID has been officially agreed upon.

If you want this field to be filled, you need to allow use of interim trade IDs for the reporting company codes. You do this in the Customizing activity Define Settings for Trade Repositories in Customizing for Trade Repository Reporting.

The system determines interim trade IDs as follows:

If you use the business partner ID type FS0007:

Characters 716 of the LEI (of the company code), the company code, and the transaction number are combined to produce the interim trade ID

If you use a different business partner ID type:

Business partner ID of the company code, the company code, and the transaction number are combined to produce the interim trade ID

**Note:**

The business partner ID is read from the business partner master data of the business partner that represents the company code. You can assign business partners to company codes in the business partner data (in the Counterparty role) on the Control Data tab in the Partner Is Company Code area.

When a financial transaction that can be reported using an interim trade ID is created for the first time, the system creates an additional trade repository object with the action type 25 (External Trade ID) and this additional trade repository object is used to subsequently report the external trade ID.

Until an external trade ID is entered in the transaction, the interim trade ID is used exclusively in the related trade repository objects.

If there is no external trade ID for a transaction at the time when it is first reported, initially use the interim trade ID to report the financial transaction to the trade repository. Once the external trade ID is known, store it in the transaction. When an external trade ID is entered for a transaction that has been reported using an interim trade ID, the external trade ID and the interim trade ID are filled automatically in the trade repository object with the action type 25. In trade repository objects that have not previously been reported, the external trade ID is now filled and the interim trade ID is deleted. Send the TARO with action type 25 to the trade repository. After you have used this notification to inform the trade repository of the external trade ID, all subsequent reports then use the external trade ID.

If the external trade ID becomes known before the transaction is reported for the first time, the external trade ID is filled in the TAROs, and the interim trade ID is not used. Consequently, the transaction is reported to the trade repository using the external trade ID. The TARO with action type 25 is changed to Obsolete.

**Note:**

If in Customizing under Define Legal Basis, you have set a start date for validation for a legal basis, then the external trade ID is validated and the process for the interim trade ID is changed too. If you decided to use an interim trade ID, then one of the

processes described above is changed from the validation date in the following way:

The Interim Trade ID is now entered in the External Trade ID field.

No trade repository object with action type 25 (External Trade ID) is created.

If you receive the correct external trade ID before the first report of the financial transaction to the trade repository, you can enter it and overwrite the internally determined ID.

If you receive the correct external trade ID after the first report of the financial transaction to the trade repository, then a trade repository object with action type 40 (Error) is created automatically, first to deregister the transaction in the trade repository, then to report it with a trade repository object with action type 10 (New) with the correct external trade ID.

**Status Management for Trade Repository Objects**

[figure TRM10-F040 - Overview: TARO Status Management]

Overview: TARO Status Management

A trade repository object (TARO) always has one of the following statuses:

01Created

A trade repository object with this status has been created completely (that is, all mandatory fields are filled with a value). The TARO has not yet been sent.

You can continue to make changes to the values of the content fields for the TARO.

Possible subsequent status:

When you execute the Send function, the TARO can acquire either the status 03Sent or the status 04Sent Failed.

You can manually set the status of the TARO to 08Obsolete in the TARO monitor.

02Incompletely Created

A trade repository object has been created for a financial transaction but not all mandatory fields are filled. The TARO is incomplete.

You can continue to make changes to the values of the content fields for the TARO.

Possible subsequent status:

Add the data of the trade repository object directly in the monitor for trade repository objects or in the financial transaction data. The system checks the fields of the trade repository object again and, if all mandatory fields are now filled, the TARO acquires the status 01Created.

You can manually set the status of the TARO to 08Obsolete in the TARO monitor.

- 03Sent

The trade repository object has been sent successfully, that is, you have executed the Send function, the trade repository message was created, and the file was placed on the application server.

Possible subsequent status:

After the incoming message has been imported from the trade repository, the TARO can have one of the following statuses:

05Rejected

07Accepted

09Reconciled

- 04Send Failed


You have executed the Send function for the TARO but errors occurred during creation of the trade repository message. Consequently, no file was placed on the application server, or you have manually set this status for the TARO so as to be able to make changes and send it again.

You can continue to make changes to the values of the content fields for the TARO.

Possible subsequent status:

03Sent

You can change the content fields of the TARO and resend it. If no problems are encountered, the TARO acquires the status 03Sent.

08Obsolete

You can manually set the status of the TARO to 08Obsolete in the TARO monitor.

- 05Rejected


The trade repository has rejected the trade repository message.

Possible subsequent status:

You can manually set the TARO to one of the following statuses in the TARO monitor:

04Send Failed

If you return the TARO with this status, you can correct it and send it again.

06Rejection Accepted

08Obsolete

- 06Rejection Accepted


You have manually set the status of the TARO to Rejection Accepted.

This status is a Final Status, neither the TARO fields nor the status of the TARO can be changed.

07Accepted

The trade repository message has been entered in the trade repository. The trade repository message of the business partner has not yet arrived at the trade repository. The reconciliation is still due.

Possible subsequent status:

- 09Reconciled

- 10Reconciliation Failed


08Obsolete

You have manually set the status of the TARO to "Obsolete". This status is a Final Status, neither the TARO fields nor the status of the TARO can be changed.

- 09Reconciled

The financial transaction or a change to it has been reported successfully to the trade repository using the trade repository message, and has been reconciled there with the corresponding message of your business partner, or, if you have transferred the message for your business partner, the message was successful.

This status is a Final Status, neither the TARO fields nor the status of the TARO can be changed.

- 10Reconciliation Failed


You and your business partner have reported differing details to the trade repository.

Possible subsequent status:

09Reconciled

If the confirmation from the trade repository has occurred due to a message error by the counterparty, it is possible that, after the counterparty has reported the financial transaction correctly, the status changes to the status Reconciled after the incoming messages have been imported from the trade repository.

04Send Failed

You can manually set the status of the TARO to 04Send Failed in the TARO monitor. You can then correct the fields of the TARO and sent it again.

08Obsolete

You can manually set the status of the TARO to 08Obsolete in the TARO monitor.

20Invalid

This status is acquired by a TARO that had to be created while importing incoming messages from the trade repository because there was no TARO corresponding to the incoming message.

Possible subsequent status:

You can manually set the status of the TARO to 08Obsolete in the TARO monitor.

|Type of Status Change|Previous Status|Cause of the Change in Status|Successful?|New Status|
|---|---|---|---|---|
|Automatically| |Update of the TARO|Yes|Created|
|Automatically| |Update of the TARO|No|Incompletely Created|
|Automatically|Incompletely Created|Update of the TARO|Yes|Created|
|Automatically|Incompletely Created|Update of the TARO|No|Incompletely Created|
|Automatically|Created|Sending of the TARO|Yes|Sent|
|Automatically|Created|Sending of the TARO|No|Send Failed|
|Automatically|Send Failed|Sending of the TARO|Yes|Sent|
|Automatically|Send Failed|Sending of the TARO|No|Send Failed|
|Automatically|Sent|Import of a Confirmation Message|Yes|Accepted|
|Automatically|Sent|Import of a Confirmation Message|No|Rejected|
|Automatically|Sent|Import of a Reconciliation Message|Yes|Reconciled|
|Automatically|Sent|Import of a Reconciliation Message|No|Reconciliation Failed|
|Automatically|Accepted|Import of a Reconciliation Message|Yes|Reconciled|
|Automatically|Accepted|Import of a Reconciliation Message|No|Reconciliation Failed|
|Automatically|Reconciliation Failed|Import of a Reconciliation Message|Yes|Reconciled|
|Automatically|Reconciliation Failed|Import of a Reconciliation Message|No|Reconciliation Failed|
|Manually|Rejected|Manual Status Change in TARO Monitor| |Send Failed|
|Manually|Rejected|Manual Status Change in TARO Monitor| |Obsolete|
|Manually|Rejected|Manual Status Change in TARO Monitor| |Rejection Accepted|


|Type of Status Change|Previous Status|Cause of the Change in Status|Successful?|New Status|
|---|---|---|---|---|
|Manually|Sent|Manual Status Change in TARO Monitor| |Send Failed|
|Manually|Reconciliation Failed|Manual Status Change in TARO Monitor| |Send Failed|
|Manually|Reconciliation Failed|Manual Status Change in TARO Monitor| |Obsolete|
|Manually|Incompletely Created|Manual Status Change in TARO Monitor| |Obsolete|
|Manually|Created|Manual Status Change in TARO Monitor| |Obsolete|
|Manually|Send Failed|Manual Status Change in TARO Monitor| |Obsolete|
|Manually|Invalid|Manual Status Change in TARO Monitor| |Obsolete|

###### Status Management for Trade Repository Objects

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Status Management for Trade Repository Objects | L7 | trm10 p.90 | loio `20e82b513e422314e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/20e82b513e422314e10000000a44176d.html?locale=en-US)

Importing Reports at Period End

You use this function at the end of the period to import reports that you have received from your trade repository. As with the function for importing incoming trade repository messages, the system calls the implementation BADI_TLR_TARO_INBOUND (Import Data of Incoming Messages for a TARO). The format-specific details need to be programmed in method GET_REPORTS of the interface IF_TLR_TARO_BADI_INBOUND.

The implementation delivered can import the report D433 (Mismatched Fields) from REGIS-TR.

Importing Reports at Period End

Storage of Outgoing and Incoming Trade Repository Messages in Document Management (DMS)

All outgoing and incoming trade repository messages are stored in Document Management (DMS). There are settings that you need to make for this in DMS. See also:Customizing Settings in DMS for TRM Documents

Archiving Trade Repository Objects

TAROs for financial transactions in the Transaction Manager are archived together with the financial transactions using the archiving object TRTM_FTR.

The archiving object TRTM_TARO archives TAROs for external transactions as well as TAROs with the following action types:

30 (Valuation)

35 (Collateral)

90 (Invalid)

**Note:**

The related trade repository messages stored in Document Management (DMS) are not archived using these archiving objects.

See also:

Alert Monitor

Trade Repository Reporting has also been integrated with the Alert Monitor. You can run checks to ascertain the following:

Are there any trade repository objects that have not been sent for a specific number of days (which you specify)?

The system identifies all TAROs that have had one of the statuses Created, Incompletely Created, or Send Failed for a specific number of days.

Are there any trade repository objects that still have errors after being sent since a specific number of days (which you specify)?

The system identifies all TAROs that have had one of the statuses Rejected or Reconciliation Failed for a specific number of days.

Are there any incoming messages from the trade repository that cannot be assigned to a TARO?

The system identifies all TAROs with the status Invalid.

Are any TAROs missing?

The Alert Monitor establishes the following:

Whether TAROs are missing for a specific trade repository that may have been added recently to the settings in Customizing.

Whether a new TARO has not yet been created for a financial transaction that has been reversed at the trade repository and that needs to be reported again.

Whether backloading has not yet been performed for backloading-relevant financial transactions.

**More Information**

Key Terms in Trade Repository Reporting

Customizing for Trade Repository Reporting

**Status Management for Trade Repository Objects**

###### Monitor for Trade Repository Objects

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Monitor for Trade Repository Objects | L7 | trm10 p.127 | loio `4aea2b513e422314e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4aea2b513e422314e10000000a44176d.html?locale=en-US)

**Use**

The TARO monitor (transaction FTR_TARO_MONITOR) provides you with an overview of your trade repository objects, together with the following processing options for them:

You can call up the log for a trade repository object.

Using the Preview, you can display the trade repository message generated from the content data and also the derived content data of a TARO.

You can also display all of the files for this TARO.

You can also send TAROs with status 01Created or 04Send Failed.

You can also display all TAROs for a financial transaction.

You can reverse a financial transaction at the trade repository.

You can also manually change the field values of the content data of a trade repository object (with status 01Created, status 02Incompletely Created or 04Send Failed).

You can protect fields that have been changed manuallly to prevent their values from being overwritten by the original value. In the case of protected fields, the system notes both the original value of the field before the manual change and the changed value. If an update of the TARO content causes the original value of a protected field to be determined, the field continues to retain the manually changed value. In cases when the update of the TARO content produces a different value to the original value, the system enters the new value in the field.

To display protected fields, choose Transaction Protected Fields .

You can also trigger an update of the TARO field values using the Complete function. This can be useful if you have corrected or added data, and these changes are not yet visible in the TARO.

You can manually change the status of a trade repository object.

You can enter a comment for a TARO.

You can upload one or more files as attachments to a TARO. When the trade repository message is sent, the attachments are also stored in DMS.

Furthermore, you can enter external transactions here that you do not manage in the Transaction Manager. For the external transactions, the system also creates TAROs so that you can also use Trade Repository Reporting to report these transactions to the relevant trade repository.

See also:Enter External Transactions

**Activities**

Call up the function in the Transaction Manager application menu under Information System Reports Reporting Trade Repository Reporting Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR).

Selection

- 1. You can restrict the selection of trade repository objects using the following fields:

Trade Repository

If you need to send messages to different trade repositories, you can here single out the trade repository for which you want to see or process the TAROs.

Status

You can also restrict the selection using the status of the trade repository objects, for instance you have the option of restricting the selection to all TAROs that have been incompletely created.

Action Type

First created on

In addition, you can restrict the selection of TAROs using the following fields of the financial transactions to be reported:

Company Code

Transaction

External Trade ID

Product Type

Transaction Type

- 2. In the Sending Parameter area, you can specify in the Messages per File field the maximum number of messages in a combined file.
- 3. Execute the function.


**Note:**

You can see how many TAROs correspond to your current selection using the Number of Entries function.

You can limit the number of trade repository objects displayed using the Maximum Number Hits function. The system always displays the most recent trade repository objects. The default value of the Maximum Number Hits field is 200. You can change this value if necessary.

Output

The system displays the list of trade repository objects you selected using the SAP List Viewer for SAP GUI (Classic). The general SAP List Viewer functions are available to you in addition to the special functions for processing TAROs.

1. To edit a trade repository object, select it and then choose the function you require.

Log

You can obtain from the log the time when and the person who created or changed the TARO, and which transaction they used. The system also displays the related error log at all times.

Preview

You can see in the preview the trade repository message from which the current content data and the derived content data of the TARO would have been generated.

Files


Select a TARO. Choose File.


You can see all of the files saved for this TARO in document management. These are the files of the trade repository messages sent, the files uploaded as attachments to this TARO, and the files of the incoming messages from the trade repository.

If you select one of the files and choose , you can also view the file.

You can assign one or more files as attachments to a TARO. Choose . Select the file. The file is uploaded.


You can display the file by choosing or delete the assignment of the file to the TARO by choosing .



Send

You can also send TAROs with status 01Created or 04Send Failed.

You have the option of sending each trade repository message in an individual file to the trade repository or sending multiple trade repository messages in one combined file.

Select the trade repository objects to be sent and then choose Send Send One Message per File / Send Combined Files .

See also:Send Trade Repository Messages

Content


If you call this function, you can see all of the trade repository object fields with their current values. You can change the field values for the TARO, provided the TARO has one of the following statuses:

- 01Created

- 02Incompletely Created


04Send Failed

You can manually change only the field values of the content data. Although the field values of derived content data are also displayed here, they are not saved persistently and consequently cannot be changed. If you want to change the field value of derived content, you need to manually change the value at the location from which it is determined (such as in the business partner master data).

**Note:**

If you always want to fill a derived content field differently, you can create your own BAdI implementation, or use the derivation tool for determining the derived content fields.

Choose to make a change. Make any changes, and then them. The system asks whether you want to protect the change to the field value from being overwritten by the original value. If you opt to protect the field value, the



system notes both the original value of the field before the manual change and the changed value. If an update of the TARO content causes the original value of a protected field to be determined, the field continues to retain the manually changed value. In cases when the update of the TARO content produces a different value to the original value, the system enters the new value in the field.

Transaction

You use this function to do the following:

Navigate to the financial transaction data of the selected TARO

Display all TAROs for the financial transaction of the selected TAROs

Reverse the financial transaction at the trade repository

When you execute this function, the system creates a TARO with the action type 40Error. In this way, the financial transaction is reversed at the trade repository. All TAROs for this financial transaction that have not yet been sent acquire the status Obsolete.

Display mismatched fields for TAROs with the status Reconciliation Failed for which you have imported the report on mismatched fields using the function Import Reports at Period End

Display the protected fields for a financial transaction

Change Status To


Using this function, you can change the status of the TARO to one of the possible subsequent statuses.

See also:Status Management for Trade Repository Objects

Complete

Using this function, you can start the determination of the field values using the BAdIs and derivation tools for the selected TARO with the status 02Incompletely Created. If the process is run successfully, then the TARO status is set to 01Created, otherwise it retains the status 02Incompletely Created.

Comment


Select one or more TAROs. Choose Comment. Enter the text of your comment (maximum of 50 characters). Choose Enter. Your comment is assigned to the selected TAROs and displayed in the Comment column.


Last TAROs

When you call up the monitor, it first displays all trade repository objects for the selected financial transactions. By choosing the Latest TAROs pushbutton, you can restrict the list to the most current/latest TAROs for a financial transaction. By choosing the same pushbutton again (it is now the All TAROs pushbutton), all TAROs are displayed.


The list of trade repository objects is updated using this function.

**More Information**

Trade Repository Reporting (TRR)

Fields of the Trade Repository Object

Customizing for Trade Repository Reporting

###### Enter External Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Monitor for Trade Repository Objects > Enter External Transactions | L8 | trm10 p.131 | loio `5591a952e3d27b6ae10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5591a952e3d27b6ae10000000a423f68.html?locale=en-US)

**Use**

In the Monitor for Trade Repository Objects, you can also enter financial transactions that you do not manage in the Transaction Manager and report them to the trade repository.

**Features**

The "Get Template" function allows you to do the following:

Enter similar transactions more quickly

Make changes to external transactions that have already been reported to the trade repository

**Activities**

- 1. In the area menu, choose Trade Repository Reporting Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR).
- 2. Choose the External Transactions pushbutton. The screen for entering external transactions appears.

You enter transactions using the SAP List Viewer for SAP GUI (Classic).

- 3. Choose Insert Row.
- 4. Enter the data of the transaction.

If the data of the financial transaction is available to you in table format, you can transfer the data to the system using copy and paste (provided that the column sequences match).

- 5. Save your entries.


**Note:**

If you have previously entered an external transaction that is very similar to the new transaction that you want to enter, you can use the Get Template function to copy the data of that previous transaction so that you then only have to enter data that differs. To locate the external transaction to serve as a template, enter the external trade ID or the interim trade ID for that transaction.

The system checks the completeness of the data. The following data is checked:

Company Code

This field must be filled and the company code entered must exist in the system.

Trade Repository

This field must be filled and the trade repository entered must exist in the system.

External Trade ID or Interim Trade ID

The system checks whether one of the fields is filled. If so and the action type is New, the system also checks whether the ID is already used.

Action Type

Further, at least one other field of the content data must be filled.

- 6. Changes to an External Transaction


If changes need to be made to an external transaction, call the Enter External Transactions function again in the Monitor for Trade Repository Objects. You can now use the Get Template function to access the external transaction to be changed. Change the action type accordingly and make the necessary changes to the transaction data. Save your entries. The system now creates the trade repository object.

###### Update Trade Repository Objects

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Update Trade Repository Objects | L7 | trm10 p.132 | loio `9c2f8f517d86df0de10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9c2f8f517d86df0de10000000a441470.html?locale=en-US)

**Use**

You can execute the Update Trade Repository Objects function (transaction FTR_TARO_PROCESS) in various different ways. You select the relevant Scope of the Update for this:

Update

In this instance, the field values of the content and derived content of the trade repository object are determined again for all of the trade objects and financial transactions that you have selected, and the TARO status is set.

This function enables you to create TAROs for existing financial transactions.

Valuation Update

If, in Customizing under Define Settings for Trade Repositories, you have defined that the mark-to-market value of the financial transactions should be reported to the trade repository in a separate message, you create the TAROs for this message using this function.

The system updates only TAROs with the action type 30Valuation with the mark-to-market value of the relevant key date. The mark-to-market value must exist in the NPV table in the system (transaction JBNPV), no valuation is triggered.

Updating Collateral

If, in Customizing under Define Settings for Trade Repositories, you have specified that the value of securities of a financial transaction is reported to the trade repository in a separate message, you create the TAROs for this message using this function.

The implementation delivered for the BAdIs does not fill the fields of the TARO. If you use the delivered implementation, calling this function creates a TARO with the action type 35Collateral with the status 02Incompletely Created.

You can create your own implementation of the BAdI, use the derivation tool to define rules with which to fill the fields, or enter the values manually in the TARO Monitor.

Update with Valuation and Collateral

If you execute this function, the TAROs are updated and TAROs are also created for the valuation messages and for the collateral update.

Backloading

Select this scope if you want to create backloading TAROs.

See also:Backloading

If you select the scope Valuation Update, Collateral Update, or Update with Valuation and Collateral, the Valuation Key Date/Collateral Key Date field appears on the entry screen. You can select either the current date or a date from the past.

You either execute the function manually, or direct.

If you choose the manual option, the system first displays a list of financial transactions for which the TAROs need to be updated due to changes to their fields. You can then narrow your search to those financial transactions for which you want to update the TAROs.

If you opt for the direct processing method, the system immediately updates all of the trade repositories and financial transactions that you have selected.

**Features**

Selecting Financial Transactions

You can select the financial transactions using the following criteria:

Company code

Transaction number

Product type

Transaction type

Business partner

Active status

Term start

Term end

In the Transactions with Existing TAROs area, you can select financial transactions on the basis of the following TARO attributes:

Trade repository

Status

Action type

First created on

External trade ID

Interim trade ID

Updating TAROs

When you execute the function, the system starts by selecting the financial transactions. In the next step, the system determines the current content of the TARO and compares it against the most current TARO for the transaction. If the comparison identifies differences, either a new TARO is created or changes are made to the current TARO. If the comparison does not identify any differences, no TARO is created.

Valuation Update

If you have opted for the scope Valuation Update or Update Including Valuation, the system creates for each of the selected transactions a TARO with the action type 30Valuation. The default implementation fills the fields for the valuation as follows:

|Mark-to-Market Value of the Contract|Table 1, Field 17|Mark-to-Market Value or Markto-Model Value of the Contract Test|The system reads the values from table VTVBAR. Here you can enter the MtM value manually using transaction JBNPV or calculate it using transaction TPM60.|
|---|---|---|---|
|Currency of the Mark-to-Market Value|Table 1, Field 18| |Currency of the Mark-to-Market Value|
|Last Valuated On|Table 1, Field 19| |First Created On date of last valuation for the contract available in table VTVBAR.|
|Last Valuated At|Table 1, Field 20| |Time for the date of the last valuation|
|Last Valuation Type|Table 1, Field 21|Specifies how the mark-tomarket value is determined: M = Mark-to-Market O = Mark-to-Model|Always filled by the system with M.|


If the system cannot find a value for the key date,it creates the TARO with status 02Incompletely Created.

**Note:**

In Customizing for Trade Repository Reporting with the activity Define Settings for Trade Repositories, you can define under Fields for Valuation your own fields for updating valuation and use these for the valuation message. These fields are not applied in the case of messages for action types New, Backloading, and Change.

If you do not make any settings for the fields in Customizing, the above-mentioned fields are applied by default.

Updating Collateral

If you have opted for the scope Valuation Update or Update Including Valuation and Collateral, the system creates for each of the selected transactions a TARO with the action type 35Collateral. The default implementation does not fill the fields for the collateral. You can create your own implementation of the BAdI, use the derivation tool to define rules with which to fill the fields, or enter the values manually in the TARO Monitor.

|Collateral Value|Table 1, Field 25|Not filled|
|---|---|---|
|Value Currency|Table 1, Field 26|Not filled|
|Last Valuated On| |Not filled|
|Last Valuated At| |Not filled|
|Last Valuation Type| |Not filled|


If you manage your collateral in portfolios, you can use the BAdI method GET_COLLATERAL_PORTFOLIO of the BAdI BADI_TLR_TARO_FILL_CONTENT to determine the relevant collateral portfolio belonging to each financial transaction.

**Note:**

In Customizing for Trade Repository Reporting with the activity Define Settings for Trade Repositories, you can define under Fields for Collateral your own fields for updating collateral and use these for the collateral message. These fields are not applied in the case of messages for action types New, Backloading, and Change.

If you do not make any settings for the fields in Customizing, the above-mentioned fields are applied by default.

**More Information**

See also:

Backloading

Trade Repository Reporting (TRR)

###### Backloading

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Backloading | L7 | trm10 p.135 | loio `5c54d7524aab0026e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5c54d7524aab0026e10000000a4450e5.html?locale=en-US)

**Use**

All financial transactions that are active on the backloading cutoff date and all financial transactions that are created after the backloading cutoff date (start date) need to be reported to the trade repository.

The actual reporting start (reporting start date) generally falls after this date. For this reason, financial transactions that need to be reported can be divided into two groups:

Financial transactions that are created as of the reporting start date (start date) and are reported to the trade repository using the regular reporting process

These financial transactions are reported using a trade repository notification with the action type 10New.

Backloading-Relevant Financial Transactions

This group contains all financial transactions that are active on the backloading cutoff date as well as financial transactions that are created between the backloading cutoff date and the reporting start date (start date).

You can report these financial transactions to the trade repository using trade repository notifications with the action type 80Backloading.

Backloading-relevant financial transactions can be divided into the following groups:

Financial transactions that are active on the reporting start date and that have a start date that falls before the backloading cutoff date.

Financial transactions that are active on the reporting start date and that have a start date that falls after the backloading cutoff date.

Financial transactions that end before the reporting start date but after the backloading cutoff date.

[figure TRM10-F053 - To be able to create backloading notifications, you need to enter the sending start date in the Customizing activity Define Settings for Trade Repositories. If you want to send backloading notifications to the trade repository ahead of the official reporting start date, you need to specify a sending start date that falls before the reporting start date.]

To be able to create backloading notifications, you need to enter the sending start date in the Customizing activity Define Settings for Trade Repositories. If you want to send backloading notifications to the trade repository ahead of the official reporting start date, you need to specify a sending start date that falls before the reporting start date.

You use the function Update Trade Repository Objects (transaction FTR_TARO_PROCESS) to manually create the trade repository objects for backloading-relevant financial transactions. In this function, you can select the different groups individually and, if you so wish, report their transactions to the trade repository on different dates.

If the sending start date falls before the reporting start date, the system automatically creates backloading TAROs for financial transactions that were created between the sending start date and the reporting start date.

[figure TRM10-F054]

**Prerequisites**

To be able to use the backloading function, you need to specify the following dates in Customizing:

In the activity Define Legal Basis, specify the following dates for a legal basis:

Backloading Cutoff Date

All financial transactions that are active on the backloading cutoff date and all financial transactions that are created after the backloading cutoff date (start date) need to be reported to the trade repository.

**Example:**

For EMIR, the backloading cutoff date is August 16, 2012.

Reporting Start Date

The trade repository reporting process starts on the reporting start date. For financial transactions that are created after this date, trade repository objects with the action type 10New are created.

You enter the reporting start date in the Customizing activity Define Legal Basis. This is because this date is determined from the legal basis.

**Example:**

For EMIR, the reporting start date is February 12, 2014.

You specify the sending start date in the activity Define Settings for Trade Repositories.

From the sending start date, the system creates trade repository objects with the action type 80Backloading for new backloading-relevant financial transactions, and you can use the function Update Trade Repository Objects (transaction FTR_TARO_PROCESS) to create trade repository objects with the action type 80Backloading for existing backloadingrelevant financial transactions.

The sending start date is selected by you and needs to meet the following condition:

Backloading cutoff date ≤ sending start date ≤ reporting start date

**Note:**

If you do not set the sending start date, the system creates trade repository objects for new financial transactions as of the reporting start date. You cannot create TAROs for financial transactions that already exist on the reporting start date.

However, it may be useful to do so in the following circumstances:

When you have already reported these financial transactions to the trade repository.

When no reporting-relevant financial transactions exist before the reporting start date.

**Note:**

If you do not specify this dates in Customizing, the system creates TAROs as soon as you have completed the Customizing settings for Trade Repository Reporting (TRR).

**Features**

From the sending start date, the system creates a trade repository object with action type 80Backloading for every new financial transaction. When the reporting start date is reached, the system creates a trade repository object with the action type 10New for new financial transactions.

To create trade repository objects for backloading-relevant financial transactions that, on the sending start date, either already exist or have been completed, you use the function Update Trade Repository Objects (transaction FTR_TARO_PROCESS).

**Activities**

- 1. Call the function Update Trade Repository Objects (transaction FTR_TARO_PROCESS).
- 2. In the Scope of Update field, choose Backloading.
- 3. In the Transactions area, select the transactions for which you would like to create backloading TAROs.


You can select the different groups of backloading-relevant financial transactions individually and report them to the trade repository at a different date. Set one or more of the following checkboxes:

Active at Report. Start Date and Start Date Before Backloading Cutoff Date

**Example:**

For EMIR, these financial transactions must be reported within 90 days after the reporting start date.

Active at Report. Start Date and Start Date After Backloading Cutoff Date

**Example:**

For EMIR, these financial transactions need to be reported on the reporting start date.

Ending Before Report. Start Date but After Backloading Cutoff Date

**Example:**

For EMIR, these financial transactions must be reported within 3 years after the reporting start date.

In addition, you can use the following criteria to restrict the selection of financial transactions:

Company Code

Transaction

Product Type

Transaction Type

Business Partner

Active Status

- 4. If you have already saved a display variant for the results list, you can assign this variant in the Layout field in the Handling area.
- 5. As the processing mode, select Manual or Direct.


If you select Manual, the system displays a results list.

This list contains all selected financial transactions. At the beginning of each row, you see the status of the financial transaction. This status relates to whether the transaction has been reported to a trade repository:

Green traffic light: Completed

This status means that a TARO has already been created for that financial transaction.

Yellow traffic light: To be edited

This status means that a TARO has not yet been created for that financial transaction or that a TARO has not yet been created for all trade repositories.

Select the financial transactions for which you want to create a backloading TARO and choose Backloading.

By selecting a row and choosing Monitor, you navigate to the Monitor for Trade Repository Objects, which displays all TAROs that exist for the selected transaction.

By selecting a row and choosing Display Deal, you display the transaction.

If you choose Direct as the processing mode, the system creates a backloading TARO (with action type 80) for all selected financial transactions for which no TARO exists yet or for which a TARO does not yet exist for all trade repositories.

Result

Once the backloading TAROs have been created, they are visible in the Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR) where you can process them or send them to the trade repositories using the function Send Trade Repository Objects.

###### Send Trade Repository Objects

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Send Trade Repository Objects | L7 | trm10 p.139 | loio `db2e8f517d86df0de10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/db2e8f517d86df0de10000000a441470.html?locale=en-US)

Use

You can start sending trade repository objects either from the Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR) or by using the Sending Trade Respository Objects (transaction FTR_TARO_SEND) function.

By executing the function you start the sending process for the selected trade repository objects. When you do this, a trade repository message is created from the data of the trade repository object. As each trade repository defines the format in which it should receive the messages, trade repository reporting is designed in such a way that various formats can be supported. To create the file, you have to implement BAdI BADI_TLR_TARO_FILE_CREATECreate File Based on TARO Content. The TARO data is the import parameter of the BAdI. The output parameters are the trade repository message as a file in a character string format and the file type (for example, .XML or .txt). The BAdI implementation is called during the send process.

After creation of the trade repository message (file), the BAdI BADI_TLR_TARO_FILE_SEND is called. You use this BAdI to control the output channel used for the trade repository message. The delivered implementation of this BAdI stores the trade repository message on the application server.

**Note:**

Implementations are delivered for the BAdIs BADI_TLR_TARO_FILE_CREATE and BADI_TLR_TARO_FILE_SEND.

You can schedule this function as a background job.

**Prerequisites**

Active implementations must exist for the BAdIs BADI_TLR_TARO_FILE_CREATE and BADI_TLR_TARO_FILE_SEND.

The trade repository objects must have the status 01Created or 04Send Failed.

See also:Status Management for Trade Repository Objects

**Features**

Process flow of the sending process

When you execute the function, the system first calls the BAdI implementation for the method FILL_DERIVED_CONTENT of BAdI BADI_TLR_TARO_FILL_DER_CONTENTFill Derived Content for Trade Repository Objects, then the derivation tool for the derived content, and also method CHECK_CONTENT of the BAdI. The system then runs the implementations of the BAdIs BADI_TLR_TARO_FILE_CREATECreate File Based on TARO Content and BADI_TLR_TARO_FILE_SENDSend File to Trade Repository.

The file created using the BAdI is stored in Document Management.

The implementation of the BAdI BADI_TLR_TARO_FILE_SEND controls how the file created is handled. The delivered implementation stores the file on the application server. In trade repository reporting Customizing, you have entered the path under which the files are stored on the application server.

You can also display the created file from the monitor for trade repository objects.

Trade repository messages can be sent to the trade repository either individually or in a combined file. When you choose the Combined Files function in the Monitor for Trade Repository Objects or in the function Send Trade Repository Objects, the

system combines into one message all selected trade repository messages that have the same company code, relate to the same trade repository, and use the same format tree. For this, you can restrict the size of the file by specifying the maximum number of messages per file in the send parameters.

**Note:**

Implementation delivered

Create File

The implementation delivered creates an XML file by calling the Data Medium Exchange Engine (DMEE).

The DMEE (transaction DMEE) is a tool that you can use to create, manage or display metadata (such as format trees). You can use it to convert ABAP data to XML files. The DMEE is connected to the transport system, so that the metadata created in the DMEE can be transported to the system landscape.

To connect the trade repository object to the DMEE, the tree type TRM0 has been created (with category Outgoing File, interface type TLRS_TARO_DMEE_IF, test report R_TLR_DMEETEST_EMIR, authorization group FC12).

The following client-independent format trees are delivered for the implementation:

TARO_FT Full Termination

TARO_TT Trade Termination

TARO_XT Reported Trade

TARO_BK Reporting Backloading

TARO_VU Valuation Update

TARO_CU Collateral Update

TARO_MX Trade Modification

TARO_MX_UTITrade Modification UTI

TARO_MX_VTrade Modification Type 'V'

The BAdI implementation calls the appropriate format tree depending on the action type of the TARO, and the TARO data (in accordance with the settings in the DMEE) is converted to XML format:

|Action type|Format tree|
|---|---|
|10New|TARO_XT|
|20Modification|TARO_MX|
|21Modification (Security Information)|TARO_MX_V|
|25External Trade ID|TARO_MX_UTI|
|30Valuation|TARO_VU|
|35Collateral|TARO_CU|
|40Error|TARO_TT|
|45Notice|TARO_TT|
|50Termination upon maturity|TARO_TT|
|60Premature termination|TARO_TT|
|70Compression|Not supported|
|80Backloading|TARO_BK|


If you would like to sue other format trees for your outgoing messages, you can define format trees in the DMEE and assign them to action types in the Customizing activity Define Settings for Trade Repositories. You can use the delivered format trees as a template for your own format trees.

The delivered implementation uses the format trees that you have defined and assigned.

Additional notes:

You can also create other file types.

You are recommended to use the DMEE to create the files, but this is not mandatory.

Using report R_TLR_DMEE_TEST_EMIR, you create an XML file based on a format tree for a financial transaction. The report calls the BAdIs and the derivation tools to create the TARO, and then creates the XML file. You can check that the XML file is correct using the .XSD file of your trade repository.

Sending Files to Trade Repositories

The implementation of the BAdI BADI_TLR_TARO_FILE_SEND controls how the file created is handled.

The delivered implementation stores the file on the application server. In trade repository reporting Customizing, you have entered the path under which the files are stored on the application server.

Storage of the files created in document management

The trade repository notifications are stored together with the attachment for the TARO (if you have assigned a file to the TARO in the Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR) in Document Management (DMS).

One DMS document is created for one trade repository object (TARO), which happens when you first send the trade respository object. The trade repository message - as well as any attachment to the TARO - are assigned to this document. More files are often added to this TARO in any subsequent process (such as the incoming messages from the trade repository), which are then also assigned to the existing DMS document.

Log

A log is issued, both for test runs and production runs.

All selected trade repository objects are listed in the log. The TARO is sorted in accordance with the following criteria:

Trade repository

Company code

Transaction number

TARO number

A traffic light at the start of each line gives you information about the send status. In addition to the traffic light, the status of the trade repository object is displayed in a mouseover text.

During a test run, the traffic lights mean the following:

: The TARO was already sent successfully (status 03, 07, 09 and 10).


: The TARO has 01 or 04 status would be sent in a production run.


:


The TARO is not fit for sending (status 02, 20).

The TARO was refused (status 05, 06).

The TARO is not relevant (status 08, 20).

During a production run, the traffic lights mean the following:

: The TARO was sent successfully


: The TARO was already sent (status 03, 07, 09 and 10).


:


The TARO had 01 or 04 status and the send failed. In addition to the red traffic light, mouseover text displays Errors.

The TARO is not fit for sending (status 02, 20).

The TARO was refused (status 05, 06).

The TARO is not relevant (status 08, 20).

**Activities**

- 1. Call up the function under Transaction Manager Information System Reports Regulatory Reporting Trade Repository Reporting Send Trade Repository Objects (transaction FTR_TARO_SEND).
- 2. Select the trade repository to which you want to report.

If you do not select a trade repository, the system sends messages for all trade repositories.

- 3. Select the status/statuses of the trade repository objects.

If you do not set a status, the system sends messages for all TAROs with the send-relevant status 01Created or 04Send Failed.

- 4. Select the action type. If you do not select an action type, the system sends messages for all action types.
- 5. Specify a date for the TAROs in the First Entered On field.
- 6. You can specify the planned send date by which the TAROs are to be selected.
- 7. In the Financial Transaction area, you can use the following financial transaction data to restrict the selection of the TAROs: You can select the following attributes for the financial transactions:

Company code

Transaction number

Product type

Transaction type

External trade ID

- 8. In the Sent area, make the following settings:


Layout: You can specify a layout for the results log.

Set the Combined Files ("Combine Multiple Trade Repository Messages into One File") indicator if you want to send trade repository messages in combined files.

If you do not set this indicator, the system sends each trade repository message in an individual file.

If you set this indicator, you can then use the Max.No. Messages per File field to specify the maximum number of messages in a combined file.

Test Run indicator

You can first send the messages in a test run.

###### Importing Incoming Messages

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Importing Incoming Messages | L7 | trm10 p.144 | loio `026c8c51c6dbdd0de10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/026c8c51c6dbdd0de10000000a441470.html?locale=en-US)

**Use**

With the Importing Incoming Messages function (transaction FTR_TARO_IMPORT), the incoming messages of your trade repository are uploaded from the application server or from your local hard disk to trade repository reporting, the files being read and assigned to the corresponding TARO, the status of which is set accordingly.

The imported file is in addition saved in document management.

**Prerequisites**

The file to be imported must be in a format that can be interpreted using the implementation of BAdI BADI_TLR_TARO_INBOUND Import Data of Incoming Messages for a TARO.

The implementation delivered expects an XML file.

**Features**

The trade repository sends you messages informing you whether the message that you sent for a financial transaction has been accepted, rejected or reconciled, or whether the reconciliation, with the corresponding message from your business partner, has failed.

You can import combined files. You can upload individual files or several files simultaneously from a folder.

The BAdI implementation interprets the incoming message, and then sets the status of the TARO. A TARO can have the following statuses following the import of a message:

05Rejected

The trade repository has rejected the trade repository message.

Possible subsequent status:

You can manually set the TARO to one of the following statuses in the TARO monitor:

04Send Failed

If you return the TARO with this status, you can correct it and send it again.

06Rejection Accepted

08Obsolete

07Accepted

The trade repository message has been entered in the trade repository. The trade repository message of the business partner has not yet arrived at the trade repository. The reconciliation is still due.

Possible subsequent status:

- 09Reconciled

- 10Reconciliation Failed


- 09Reconciled

The financial transaction or a change to it has been reported successfully to the trade repository using the trade repository message, and has been reconciled there with the corresponding message of your business partner, or, if you have transferred the message for your business partner, the message was successful.

This status is a Final Status, neither the TARO fields nor the status of the TARO can be changed.

- 10Reconciliation Failed


You and your business partner have reported differing details to the trade repository.

This status is a Final Status, neither the TARO fields nor the status of the TARO can be changed.

Storage of the incoming message in document management

All trade repository messages are stored in Document Management (DMS).

One DMS document is created in DMS for one trade repository object. All of the trade repository messages (files) of this TARO are assigned to this document, plus the incoming messages.

**Note:**

If a message for which there is no corresponding TARO is imported, the system creates for that incoming message a TARO with the action type Invalid and the status Invalid.

**More Information**

Trade Repository Reporting (TRR)

Customizing for Trade Repository Reporting

###### Importing Reports at Period End

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Importing Reports at Period End | L7 | trm10 p.145 | loio `33258f538eef3e27e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/33258f538eef3e27e10000000a44538d.html?locale=en-US)

You use this function at the end of the period to import reports that you have received from your trade repository. As with the function for importing incoming trade repository messages, the system calls the implementation BADI_TLR_TARO_INBOUNDImport Data of Incoming Messages for a TARO. The format-specific details need to be programmed in method GET_REPORTS of the interface IF_TLR_TARO_BADI_INBOUND.

The implementation delivered can import the report D433Mismatched Fields and D436Inter-TR Reconciliation Mismatched Fields from REGIS-TR.

In the Monitor for Trade Repository Objects (transaction FTR_TARO_MONITOR), you can use the function Mismatched Fields to display the affected fields.

Once the TARO has acquired the status "Reconciled", information relating to the mismatched fields is deleted.

**Update Transactions with an External Trade ID**

**Use**

You use this program to update financial transactions with their external trade ID or to change the external trade ID used previously.

There are various ways with which you can assign an external trade ID to a financial transaction:

Update Database Only

In this case, the external trade ID is assigned to the transaction and is also displayed on the Administration tab in the financial transaction. However, the financial transaction does not acquire the status Changed, and no change correspondence is created.

Update Financial Transaction

In this case, the external trade ID is assigned to the transaction and is also displayed on the Administration tab in the financial transaction. The financial transaction acquires the status Changed and a change correspondence is created if this has been set up in the Customizing settings for the correspondence for changes to financial transactions.

Update Financial Transaction and TARO

In this case, the external trade ID is assigned to the transaction and is also displayed on the Administration tab in the financial transaction. The financial transaction acquires the status Changed and a change correspondence is created if this has been set up in the Customizing settings for the correspondence for changes to financial transactions. Further, this change is also applied in trade repository reporting, and either an existing TARO is updated or a new TARO is created.

Update Database and TARO

In this case, the following applies:

The external trade ID is assigned to the transaction and is also displayed on the Administration tab in the financial transaction. However, the financial transaction does not acquire the status Changed, and no change correspondence is created.

This change is also applied in trade repository reporting, and either an existing TARO is updated or a new TARO is created.

**Prerequisites**

To determine the external trade ID automatically, the BAdI: Default Value for External Trade IDs in Financial Transactions (FTR_TR_DEFAULT_TRADE_ID) is used. To determine an external trade ID automatically, you need to implement this BAdI.

If you do not implement this BAdI, you need to enter manuallly the external trade IDs for the selected transactions.

To have authorization to run the transaction, you need to have the authorization object F_T_TRANSBTreasury: Transaction Authorization assigned to your user.

**Activities**

- 1. Call up the function in the area menu for the Transaction Manager under Information System Reports Regulatory Reporting Trade Repository Reporting Update Transactions with External Trade ID (transaction FTR_TARO_TRADE_ID).
- 2. In the General Selections area, you can use the following data to restrict the selection of the financial transactions:


Company Code

Transaction

Product Category

Transaction Category

Product Type

Transaction Type

Business Partner

Transaction Currency

Term Start

Term End

External Trade ID

- 3. In the Control area, you can select the legal basis as an additional selection criterion. If you select a legal basis here, the system selects only financial transactions that are defined as relevant for reporting for that legal basis and that do not yet have an external trade ID assigned to them.

If you do not select a legal basis, the system selects all reporting-relevant transactions with an external trade ID.

By setting the Transaction with Ext. Trade ID indicator, you can include in the selection transactions that already have an external trade ID assigned to them.

You also select in this area how you would like to run the report:

Update Database Only

Update Financial Transaction

Update Financial Transaction and TARO

Update Database and TAROs

The system displays the results list using the SAP List Viewer for SAP GUI (Classic). In the Layout field, you can specify the layout variant for the results list.

- 4. Execute the function.

The system now selects the financial transactions on the basis of the selection criteria.

After the financial transactions have been selected, the BAdI: Default Value for External Trade IDs in Financial Transactions (FTR_TR_DEFAULT_TRADE_ID) is called. If you have implemented this BAdI, the system determines the external trade IDs and displays them in a worklist.

The result is displayed in a worklist. The list contains all selected financial transactions. Each row displayed in the worklist has the status Not Saved (yellow traffic light). The Legal Basis and External Trade ID columns may already contain entries as a result of the BAdI implementation; otherwise, entries can be made manually here. You also see the Existing Legal Basis and Existing External Trade ID columns, which contain the values currently stored in the transaction.

- 5. In the Legal Basis and External Trade ID columns, check the values entered automatically or enter the relevant data.


**Note:**

You can create a display variant for the columns.

You can navigate to the details of the financial transaction.

- 6. Select the rows for which you want to update values and choose .



The system updates the values in the financial transaction. The status of the row is reset and, after saving, a new status is set. A green traffic light denotes that the financial transaction was saved successfully, whereas a red traffic light denotes an error while saving. By double-clicking a red traffic light, you can display the error messages.

The Existing Legal Basis and Existing External Trade ID columns are updated and now contain the new values.

**Note:**

If you have activated validation of the specified external trade ID in Customizing for a trade repository, the external trade ID is checked. To do this, the BAdI BADI_TLR_TRADE_ID_CHECKLegal-Base-Specific Checks for Trade ID is called. The default implementation delivered performs the following checks:

The external trade ID can contain only numbers, letters, and the following special characters:

Colon

Period

Minus

Underscore

The special characters must not be at the start or the end of an external trade ID.

An external trade ID can only be used once; even if the associated trade was deregistered from the trade repository, this external trade ID cannot be reused.

The BAdI issues the following messages:

- Message class FTR_GUI, no. 574External trade ID &1 not valid. Observe validation rules for &2

- Message class FTR_GUI, no. 575External trade ID &1 already registered. No longer usable


In Customizing, under Change Message Control, you can control whether the messages are to be issued as warnings (default setting) or as error mesages.

If you set the messages as error messages, the entry process is stopped in the event of an external trade ID with errors.

If you set the messages as warnings, in the event of an external trade ID with errors, the trade repository object is created with the faulty external trade ID, but has Created with errors status.

###### Update Transactions with an External Trade ID

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting (TRR) > Update Transactions with an External Trade ID | L7 | trm10 p.92 | loio `855fae52c80b6477e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/855fae52c80b6477e10000000a441470.html?locale=en-US)

**Related Information**

Archiving Financial Transactions with TRTM_FTR Archiving Trade Repository Objects with TRTM_TARO

###### Trade Repository Reporting via External Provider (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting via External Provider | L6 | trm01 p.67 | loio `0d0586573d12ab76e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0d0586573d12ab76e10000000a441470.html?locale=en-US)

This integration scenario enables you to send an XML file containing the data of the financial transactions to your external provider VirtusaPolaris. The external provider will then transform the data to your responsible trade repository.

**Note:**

The scope of the supported financial instruments needs to be aligned with the service provider (VirtusaPolaris) and then considered in your selection criteria (e.g. product categories, transaction categories or product types).

For more information, see also Send Data of Financial Transactions to External Provider

###### Send Data of Financial Transactions to External Provider

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Trade Repository Reporting via External Provider > Send Data of Financial Transactions to External Provider | L7 | trm10 p.148 | loio `be0686573d12ab76e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/be0686573d12ab76e10000000a441470.html?locale=en-US)

**Use**

This function selects financial transactions using the logical database (LDB) FTI_TR_DEALS (see transaction SE36) and creates an XML file containing the data of the financial transactions. Then this file is saved and send to your external provider VirtusPolaris. The external provider will then transform the data to your responsible trade repository.

All financial transactions and their activities are extracted according to the selected Key Date.

**Note:**

The scope of the supported financial instruments needs to be aligned with the service provider (VirtusaPolaris) and then considered in your selection criteria (e.g. product categories, transaction categories or product types).

**Prerequisites**

In the Customizing of the Treasury and Risk Management:

Under Transaction Manager General Settings Organisation Define Company Code Additional Data :

In order to enter a trade ID into your financial transactions (on tab page Administration in the area Trade Repository) you need to allow this in this Customizing activity for the relevant company codes. Set the checkbox Allow Ext. Trade ID in the area Trade Repository Reporting.

Under Transaction Manager General Settings Information System Define Legal Basis :

Laws and regulations govern, for example, what companies have to report to authorities. The laws and regulations that a company applies are referred to as the legal basis in the SAP system. You have to define a Legal Basis.

**Example:**

When you report to a trade repository to fulfill requirements of EMIR, make the following setting:

|Legal Basis 2-digit ID|Currency|Legal Basis Long Text|Text Short Text for Legal Basis|Validation Date|
|---|---|---|---|---|
|01|EUR|EMIR|EMIR|only if needed, see the long text|


Under Transaction Manager General Settings Information System Trade Repository Reporting via External Provider Settings for External TRR Provider :

Before you can enter the settings in this Customizing activity, you have to make some additional technical settings:

Contact VirtusaPolaris to request the certificate (PSE).

Define the RFC Destination (transaction SM59).

Connection Type: G HTTP Connection to External Server

Technical Settings

Target System Settings

Target Host: fts.tradetech.se

Path Prefix:/index.php

HTTP Proxy Options

Proxy Host: proxy

Proxy Service: 8080

Proxy PW Status: is initial

See also SAP Note 662340 .

Define a SSF application in table SSFAPPLIC. Access the table maintenance using transaction SE16 and create a new entry:

APPLIC = SAPTRR

B_TOOLKIT, B_FORMAT, B_PAB, B_PROFID, B_PROFILE, B_ENCRALG = X

DESCRIPT=SAP Trade Repository Reporting by Virtusa

See also SAP Note 662340 .

Enter the application specific SSF parameter in transaction SSFA.

Security Product=SAPSECULIB

SSF-Format=PKCS7

Private Adress Book=Name of PSE

SSF Profilname=Name of PSE

SSF-Profil-ID=empty

Encryption Algorithm=DES-CBS

Distribute PSE=X

(See SAP Note 662340 .)

Import the provided PSE using transaction STRUST and save PSE under SAPTRR.

See also SAP Note 662340 .

In the Customizing Logical File Path Definition (transaction FILE) check or create a logical file path entry in the dialog structure node Logical File Path Definition for the ID FTRM_TRR_ROOT Treasury: root path for Trade Repository Service Provider. Create and check that there is an assignment made under Assignment of Physical Path to Logical Path for syntax group UNIX, physical path e.g. /tmp/<FILENAME>.

Further check or create an entry for ID FTRM_TRR_SEND Treasury: Send to Trade Repository Service Provider under node Logical File Name Definition, Cross Client. Data format is DIR, application area TR, logical path is the above mentioned FTRM_TRR_ROOT.

In this Customizing you now enter the following:

- 1. Choose New Entries.
- 2. Choose the external trade repository provider (SAP Trade Repository Reporting by Virtusa).
- 3. Enter the Destination Name.
- 4. Enter the SSF Application.


- 5. Enter the logical file name in field Logical File.
- 6. Save your entries.


**Features**

You may save your selections in different variants according to your needs, e.g.

a variant for all active financial transactions with a End of Term after the current date

a variant for reversed financial transactions (active status = 3) which are reversed recently (Entered/Changed on dates)

a variant for financial transactions which are entered or changed recently (Entered/Changed on dates)

You need to choose whether you want to keep a copy of the XML file with the extracted data of your financial transactions on your local Front-End Server (local PC/Laptop e.g. for testing) or on the Application Server (standard case) and whether you want to send the XML file to the provider: Send to Destination.

All logs can be displayed (Display Error Log) and/or stored in the application log (to be reviewed later with function Analyze Application Log (transaction SLG1), Log Triggered By transaction code FTR_TRR_DEALS_SEND).

###### Report on Voting Rights and Nominal Capital Share

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Report on Voting Rights and Nominal Capital Share | L6 | trm10 p.151 | loio `43fbc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/43fbc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Several countries/regions have legal provisions that require major shareholders to report to regulatory authorities if their share in a company exceeds or falls below certain limits.

This report determines the nominal capital share in a certain company as a percentage of the capital stock for two key dates, and the resulting number of votes in each case.

**Prerequisites**

The following information must be kept up-to-date on the Regulatory Reporting tab for the class data of the stock:

Number of stocks issued

Nominal value of the stock

Voting rights per stock

Where appropriate, the additional capital amount. The additional capital is the nominal capital of the company that is not represented by the total number of stocks.

You can use an aggregation key to group different classes that you want to value together. This may be necessary if a company has issued both common stock and preference stock, for example.

The effect of the Aggregation Key field on the calculation of the nominal capital share and the voting rights is described later on in the text.

The system automatically enters the business partner number of the issuer in the Aggregation Key field.

This field is a required entry field.

If you do not want to evaluate all the stocks from the same issuer together, enter a different aggregation key manually. Because the aggregation key is a required entry field, you cannot simply remove the value it contains. You have to overwrite

it with another value. When you assign the aggregation keys, make sure that you do not assign the same key twice.

SAP recommends that you accept the business partner number of the issuer as the aggregation key, since this number uniquely identifies the issuer. You should only use a different aggregation key in exceptional cases.

You must enter the details for stock capital and voting rights manually and keep them up-to-date. They are linked to an Effective from date. If you perform a corporate action (such as a stock split), you may need to change the data manually. You can do this by adding a new line with a new Effective from date containing the changed data.

**Features**

Selection

|General Selections| |
|---|---|
|Company code Securities account ID number|If you specify company codes, securities accounts, or ID numbers, the report performs the selection across all company codes, securities accounts, and all the relevant ID numbers.|
|Reference date Key date|Specify a reference date and a key date. The system calculates the values for both dates, as well as the differences between the reference date and the key date.|
|Limit Values| |
|Limit 1 (in percent) Limit 2 (in percent) Limit 3 (in percent) |You can specify three limit values. The limit checks are applied to all positions that have changed in the period between the reference date and the key date.|
|Summation Level of Issued Products| |
|If a position changes during the observation period, the limit check is performed for the position (summation level) specified here. A position summation level comprises the positions for one or several classes.| |
|Overall level|The system calculates the position for all company codes and securities accounts.|
|Company code level|The system calculates the position for each company code, across all securities accounts.|
|Securities account level|The system calculates the position for each securities account.|


Standard Variants

You need to create a standard variant for each group of limits ( Goto Variants Save as Variant ). For example, you could create a different variant for each country/region-specific legal requirement.

Output

For each position selected, the system calculates the nominal capital share for the position summarization level you specified.

Normal case

Nominal capital share in percent= [100 * (no. of stocks per position (level) * nominal value) / (total no. of stocks issued * nominal value)]

With additional capital

Nominal capital share in percent= [100 * (no. of stocks per position (level) * nominal value) / (total no. of stocks issued * nominal value)]

With aggregation key

Nominal capital share in percent= [100 * (no. of stocks per position (level) * nominal value) / (additional capital + (total no. of A stocks issued * nominal value of stock A) + (total no. of B stocks issued * nominal value of stock B) + ....)

where stock A, stock B, ... stand for stocks with the same aggregation key.

|Display Options| |
|---|---|
|Limit Exceeded|If you set this indicator, the report displays only positions that exceed the limit values.|
|Warning|If you set this indicator, the system displays all the positions that exceed the limit values, and warns you of the positions that fall within the limit corridor specified in the Absolute Limit Corridor Width in Percent for Warnings field.|
|All|All the positions are displayed.|
|Absolute Limit Corridor Width in Percent for Warnings|The warning corridor is applied to all the specified limits as follows: If the share value falls within the corridor (limit +/- warning corridor width) on the key date, the system displays a warning. If a limit is exceeded, or if a position falls short of a limit, this overrides the warning.|


The list is displayed using SAP List Viewer.

For more information, see also SAP List Viewer.

You can display the following columns:

ID number

Short name

Aggregation key

Limit values (limit value that was exceeded = the value specified or a multiple of the value specified)

Capital share in % on the reference date per class (depending on the display mode selected, this may be per securities account)

Capital share in % on the reference date per class (or, depending on the display mode selected, per securities account)

Share of votes in % on the reference date per class (or, depending on the display mode selected, per securities account)

Share of votes in % on the key date per class (or, depending on the display mode selected, per securities account)

Number of units on the reference date

Number of units on the key date

In addition, you can also display the following columns with details on the position, or details from the class data:

Company code

Securities account

Number of stocks issued

Nominal value

Voting rights per stock

Amount of additional stock capital

The (total) capital shares for a position in % on the reference date

The (total) capital shares for a position in % on the key date

The (total) voting right shares for a position in % on the reference date

The (total) voting right shares for a position in % on the key date

**Related Information**

Manage Securities Classes

###### IFRS 7 - Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting | L6 | trm10 p.154 | loio `d9a7d65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d9a7d65378024308e10000000a174cb4.html?locale=en-US)

Use

IFRS 7 refers to the disclosure requirements for financial instruments effective as of 2007. It replaces IAS 30 and supplements the disclosure requirements from IAS 32 to provide greater transparency in financial accounting. Using financial statements, IFRS 7 aims to gain an insight into a company's risk structure.

The basic principles need to be disclosed to identify risks arising from financial instruments and hedging transactions. IFRS 7 includes qualitative and quantitative disclosures; Qualitative disclosures cover the types of individual risks and how they arise, risk management aims and methods, and changes from the previous period. Quantitative disclosures explain individual risks and concentrations of risk. Quantitative disclosures describe credit risk (including impairment and collateral), liquidity risk (including a maturity analysis and risk management), and market risk (including sensitivity analyses).

To meet the disclosure requirements for financial instruments in accordance with IFRS 7 (effective as of 01/01/07 ), we have provided the following reports for market risk analysis. The reports take into account all the financial transactions and objects in SAP Treasury and Risk Management as well as the exposure items. For more information, see the following detailed reports:

Currency Risk

Interest Rate Risk

Interest Sensitivities

Market Values

Market Values (with Sensitivities)

Market Value Changes

Risk/Yield Analysis

###### Currency Risks

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting > Currency Risks | L7 | trm10 p.155 | loio `510cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/510cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Two reports are available for the analysis of currency risks:

Currency Risks

This report provides information on a company's currency risk. It aggregates the book values of the selected transactions in position currency and local currency. The report determines both the start value and end value of the selection period.

You can use the list to view changes to the foreign exchange position.

Currency Risks (Detail)

This report displays the book values at the start and end of the selection period for each financial transaction or position.

The list is sorted according to position currency and shows the financial transactions, from the Currency Risk report, from which the currency items are composed.

The totals lines display the aggregated values for each currency, or the total amount in local currency.

**Integration**

This report is provided for IFRS 7 reporting.

You can display the report using SAP List Viewer and the standard functions provided.

**Activities**

Currency Risks

- 1. Call the report by choosing Transaction Manager Information System Reporting IFRS 7 Currency Risks .
- 2. Select the positions or financial transaction to be evaluated in the Selections area using the criteria Company Code (mandatory entry), Valuation Area (mandatory entry), Product Category, and Product Type.
- 3. Enter the selection period.
- 4. In the Control Parameters area, you can set the indicators Display Error Log and Save Error Log.
- 5. Choose Execute.
- 6. The following columns are provided in the list:


**Caution:**

Make selections for only one valuation area.

Company Code

Position Currency

Book value in position currency at start of selection period

Book value in position currency at end of selection period

Book value in local currency at end of selection period

Local Currency

In the rows you can display the total book values for the selected financial transactions or positions using the currency and company code. The values are displayed in each case at the start and end of the selection period.

At the end of the list, the book values in position currency are aggregated using the company codes for each currency and displayed for the start and end of the selection period. The same applies to book values for the selected positions in local currency.

Currency Risks (Detail)

- 1. Call the report by choosing Transaction Manager Information System Reporting IFRS 7 Currency Risks .
- 2. Select the positions or financial transaction to be evaluated in the Selections area using the criteria Company Code (mandatory entry), Valuation Area (mandatory entry), Product Category, and Product Type.
- 3. Enter the selection period.
- 4. In the Control Parameters area, you can set the indicators Display Error Log and Save Error Log.
- 5. Choose Execute.
- 6. The system displays a list with the following columns:


**Caution:**

Make selections for only one valuation area.

Company Code

Valuation Area

(Special) Valuation Class

Product Type

Portfolio as differentiation characteristic

ID Number

Contract Number

Transaction creating the position

Securities Account

Securities Account Group

Futures account for listed options and futures

Position Currency/Transaction Currency

Book value in position currency at start of selection period

Position Currency/Transaction Currency

Book value in position currency at end of selection period

Position Currency/Transaction Currency

Local Currency

Book value in local currency at end of selection period

Local Currency

At the end of the list, the book values in position currency are aggregated using the company codes for each currency and displayed for the start and end of the selection period. The same applies to book values for the selected positions in local currency.

###### Interest Rate Risks

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting > Interest Rate Risks | L7 | trm10 p.157 | loio `540cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/540cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Two reports are provided for analyzing interest rate risk:

Interest Rate Risks

This report provides information on a company's interest rate risk.

It aggregates the book values at the start and end of the selection period for each interest category in a company code. You use the product categories to control how interest-sensitive instruments are evaluated.

Interest Rate Risk (Detail)

The detailed report displays all the selected interest-sensitive financial transactions or positions with their book values at the start and end of the selection period.

If you sort this list by interest category, you can use the report to see in detail how the items from the Interest Rate Risk report are grouped.

**Integration**

This report is provided for IFRS 7 reporting.

You can display the report using SAP List Viewer and the standard functions provided.

**Activities**

Interest Rate Risks

- 1. Call the report by choosing Transaction Manager Information System Reporting IFRS 7 Interest Rate Risks .
- 2. Select the positions or financial transaction to be evaluated in the Selections area using the criteria Company Code (mandatory entry), Valuation Area (mandatory entry), Product Category, and Product Type.
- 3. Enter the selection period.
- 4. In the Control Parameters area, you can set the indicators Display Error Log and Save Error Log.
- 5. You also enter the display currency and the corresponding currency translation type.
- 6. Choose Execute.


**Caution:**

Make selections for only one valuation area.

- 7. The list displayed contains the following columns:


Company Code

Interest Category

Display Currency

Book value at start of selection period

Book value at end of selection period

For each interest category, the system displays the sum of the book values in display currency for all the financial transactions or positions at the start and end of the selection period.

The totals line shows the scope (book value) of the interest-sensitive financial transactions in display currency at the start and end of the selection period.

Interest Rate Risks (Detail)

- 1. Call the report by choosing Transaction Manager Information System Reporting IFRS 7 Detailed Reports Interest Rate Risks (Detail) .
- 2. Select the positions or financial transaction to be evaluated in the Selections area using the criteria Company Code (mandatory entry), Valuation Area (mandatory entry), Product Category, and Product Type.
- 3. Enter the selection period.
- 4. In the Control Parameters area, you can set the indicators Display Error Log and Save Error Log.

You also enter the display currency and the corresponding currency translation type.

- 5. Choose Execute.
- 6. The system displays a list with the following columns:


**Caution:**

Make selections for only one valuation area.

Company code

Interest category

Valuation area

(Special) valuation class

Product type

Portfolio as differentiation characteristic

ID number

Contract number

Financial transaction creating the position

Securities account group

Securities account

Futures account for listed options and futures

Book value in display currency at start of selection period

Display currency

Book value in display currency at end of selection period

Display currency

The totals line shows the scope (book value) of the interest-sensitive financial transactions in display currency at the start and end of the selection period.

###### Interest Sensitivity

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting > Interest Sensitivity | L7 | trm10 p.159 | loio `5e0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5e0cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The following reports are available for the analysis of interest sensitivity.

Interest Sensitivity

The report aggregates in display currency the net present values of the financial transaction or positions. These values are calculated for the various interest categories at the start and end of the selection period based on shifts in market data or scenarios.

The system uses the product category to determine that only interest-sensitive financial transactions or positions are evaluated in the selection area.

Interest Rate Sensitivities (Detail)

The report displays the net present values of the financial transaction or positions in display currency. These values are calculated at the start and end of the selection period based on shifts in market data or scenarios.

**Prerequisites**

You first need to define market data shift rules or a scenario.

See also:

Editing Market Data Shifts

**Editing Scenarios**

**Integration**

This report is provided for IFRS 7 reporting.

You can display the report using SAP List Viewer and the standard functions provided.

**Activities**

Interest Sensitivity

- 1. Call the report by choosing Transaction Manager Information System Reporting IFRS 7 Interest Sensitivities .
- 2. Select the positions or financial transaction to be evaluated in the Selections area using the criteria Company Code (mandatory entry) and Valuation Area (mandatory entry).


**Caution:**

The system only evaluates interest-sensitive product categories.

- 3. Enter the selection period.
- 4. In the Control Parameters area, make entries in the following fields:

Evaluation Type (mandatory entry)

Market Data Shift Rule

Scenario

Control Risk Management (NPV) Buffer (mandatory entry)

Price Type and Price Calculation (Options)

Display Currency and Currency Transaction Type (mandatory entry)

Evaluation currency

You can set the indicators Display Error Log and Save Error Log.

- 5. Choose Execute.
- 6. The system displays a list with the following columns:


**Note:**

You need to select either a market data shift rule or a scenario.

Company code

Interest category

Display currency

Net present value in display currency at start of selection period

Net present value in display currency at end of selection period

The lines display the sum of the net present values in display currency for the selected financial transactions or positions. The values are calculated for the various interest categories at the start and end of the selection period, on the basis of the selected scenarios or market data shifts.

The totals line shows the total of the net present values in display currency for the start and end of the selection period, based on the selected scenario or shift in market data.

Interest Rate Sensitivities (Detail)

- 1. Call the report by choosing Transaction Manager Information System Reporting IFRS 7 Interest Sensitivities .
- 2. Select the positions or financial transaction to be evaluated in the Selections area using the criteria Company Code (mandatory entry) and Valuation Area (mandatory entry).
- 3. Enter the selection period.
- 4. In the Control Parameters area, make entries in the following fields:


**Caution:**

The system only evaluates interest-sensitive product categories.

Evaluation Type (mandatory entry)

Market Data Shift Rule

Scenario

**Note:**

You need to select either a market data shift rule or a scenario.

Control Risk Management (NPV) Buffer (mandatory entry)

Price Type and Price Calculation (Options)

Display Currency and Currency Transaction Type (mandatory entry)

Evaluation currency

You can set the indicators Display Error Log and Save Error Log.

- 5. Choose Execute.


The lines in the list display the sum of the net present values in display currency for each selected financial transaction or position. The values are calculated at the start and end of the selection period, on the basis of the selected scenarios or market data shifts.

The totals line shows the total of the net present values in display currency for the start and end of the selection period, based on the selected scenario or shift in market data.

###### Market Values

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting > Market Values | L7 | trm10 p.161 | loio `570cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/570cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The following two reports are available:

Market Values

This report displays the combined book values and net present values for the selected financial transactions for the different combinations of company code , asset/liabilities indicator , product category , and valuation class . The values are displayed in each case at the start and end of the selection period.

Market Values (Detail)

This report provides the book values and net present values for the selected financial transaction at the start and end of the selection period.

**Integration**

This report is provided for IFRS 7 Reporting .

You can display the report using the SAP List Viewer and the standard functions provided.

###### Market Values with Sensitivities

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting > Market Values with Sensitivities | L7 | trm10 p.161 | loio `5a0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a0cda531198434de10000000a174cb4.html?locale=en-US)

Use

The following reports are available:

Market Values with Sensitivities

Market Values with Sensitivities (Detail)

**Integration**

This report is provided for IFRS 7 Reporting .

You can display the report using the SAP List Viewer and the standard functions provided.

###### Market Value Changes

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting > Market Value Changes | L7 | trm10 p.162 | loio `610cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/610cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The following two reports are provided for analyzing changes in market value:

Market Value Changes

This report displays the aggregated book values, net present values (at the start and end of the selection period) and the change in net present value.

Market Value Changes (Detail)

This report displays the book values, net present values (at the start and end of the selection period) and the change in net present value for the individual transactions.

**Integration**

This report is provided for IFRS 7 Reporting .

You can display the report using the SAP List Viewer and the standard functions provided.

###### Risk/Yield Analysis

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > IFRS 7 - Reporting > Risk/Yield Analysis | L7 | trm10 p.162 | loio `640cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/640cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The following two reports display the book value and market value and the difference between them, as well as the expected yield.

The expected yield is calculated as follows:

Expected Yield = (change in net present value during period / book value)* 100

Risk/Yield Analysis

Risk/Yield Analysis (Detail)

**Integration**

This report is provided for IFRS 7 - Reporting .

You can display the report using the SAP - List Viewer and the standard functions provided.

###### Germany

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany | L6 | trm10 p.163 | loio `57fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/57fac5536a51204be10000000a174cb4.html?locale=en-US)

###### Reporting for German Foreign Trade Regulations

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Reporting for German Foreign Trade Regulations | L7 | trm10 p.163 | loio `1da35752f08afa5fe10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1da35752f08afa5fe10000000a423f68.html?locale=en-US)

Use

This report supports the requirement stipulated by the German Foreign Trade and Payments Ordinance (Außenwirtschaftsverordnung (AWV)) under which German companies have to submit reports on a monthly basis in accordance with annex Z5 and annex Z5a, page 1.

**Integration**

This report supplements the current report in Financial Accounting (FI) provided for the submission of reports in accordance with annex Z5a, page 2. You find this report on the SAP Easy Access screen under Information Systems

Accounting Financial Accounting Accounting Receivable Report Selection Regulatory Reporting Germany .

The data records are displayed in the treasury subledger.

**Prerequisites**

- 1. To ensure that the correct data is selected, note the following when you enter the business partner master data:


- a. Enter the Banks Industry Sector Indic. in the selection parameters for the reports.

All those contracts for which the business partner’s industry sector is contained in the selection parameters are then included in the Z5 report. All those contracts for which the business partner’s industry sector is not contained in the selection parameters are included accordingly in the Z5a report.

- b. The Non-Resident checkbox must be set for a business partner in the master data on the Reported Financial Data screen before the start of the contract term, otherwise the contracts are not selected.
- c. Organization relationships in business partner master data


**Note:**

Therefore, in order to ensure that data is displayed correctly it is necessary to assign the business partners to industry sectors (at least in the case of financial institutions).

In the Z5a report, the contracts with non-resident business partners are arranged based on the type of direct investment relationship. For this reason, the following values were added for the Organization Relationship field in the business partner data:

- 5 Company with Equity Held in Reporting Company (= parent company)

This value is an itemization of value 2.

- 6 Company with Equity Held by Reporting Company (= subsidiary) This value is an itemization of value 2.

- 7 Affiliated Through Common Shareholder Company (= affiliate)


This value is an itemization of value 1.

Change your entries in the business partner master data for your parent company, subsidiary, and affiliate in the Organization Relationship field under the company code-dependent Regulatory Reporting Data based on this categorization.

- 2. In Customizing for Financial Accounting (FI), you have to stipulate the following data under Enter Company Data for Foreign Trade Regulations:


- a. Company code
- b. Registration number for the Z5a report, including the check digit as assigned by the relevant state central bank
- c. Industry
- d. Federal state key in accordance with the list of keys issued by the Bundesbank
- e. Legal form in accordance with the list of keys issued by the Bundesbank
- f. Location of the recipient state central bank


**Features**

This report covers the creation of reports in accordance with annex Z5 and annex Z5a, page 1.

- 1. Z5 report

The form in accordance with annex Z5 of the AWV is used to report claims and liabilities from financial relationships with foreign banks to the Bundesbank (Section 62 AWV).

- 2. Z5a report, page 1: The form in accordance with annex Z5a, page 1 of the AWV is used to report claims and liabilities from financial relationships with foreign non-banks to the Bundesbank (Section 62 AWV). A distinction is made between claims and liabilities with respect to affiliated companies, on the one hand, and with respect to other non-banks, on the other hand. The claims are subdivided into money market papers (certificates of deposit, promissory notes, commercial papers, for example) and other claims (without securities).
- 3. This program provides you with the data that you have to report for the Z5 and Z5a reports using the general statistics reporting portal, for example. You can also save the reports as CSV files.


**Note:**

The book value of a contract forms the basis of the reports. If the book value of a loan contract is positive, this is displayed under Claims; if it is negative, it is displayed under Liabilities. In money market trading, the assignment of contracts to the sections Claims and Liabilities is controlled by the selection criterion for transaction types called Claims in Money Market Trading. Money market contracts whose transaction type is contained in this selection criterion are displayed as claims; all other money market contracts are displayed as liabilities.

**Note:**

Claims and liabilities are divided into terms of up to one year and terms of more than one year.

**Note:**

The term is calculated as the difference between the term start date and the term end date. If there is no term end date, the end date of the fixed period is used. If there is no end date entered for the fixed period, the selected contracts are classified as Until Further Notice. Assets with Until Further Notice are assigned to the term Up to 1 Year.

a. Choose Information System Report Selection Regulatory Reporting Germany Foreign Trade German AWV Z5 Statement . The AWV Statement (German Foreign Trade Regulations), Z5 and Z5a, Page 1 screen

appears.

- b. Under Form, set the checkbox for the report that you want to create:

Z5

Z5a

Z5 and Z5a

Enter the Key Date and the Notification Limit in EUR.

- c. Whether the contracts are assigned correctly and in their entirety to a report depends on your entries under Selection Criteria.

- i. First, enter the Company Codes for which you want to create the report.
- ii. Next, enter the Banks Industry Sector Indic..


You can control which financial transaction is selected with your entries in the Product Category, Product Type, Transaction Type, Transaction, and Contract Number fields. Set the Commercial Papers checkbox if you want to include these.

- d. Under Control Parameters enter the transaction types that feature receivables.


**Note:**

The last day of the month is usually entered as the key date.

The system analyzes all posted contract movements from loans and money market trading up to and including the key date.

If you restrict which financial transaction is selected by making entries in the Product Category, Product Type, Transaction Type, Transaction, and Contract Number fields, the system selects only those financial transactions that correspond to your entries.

**Note:**

If you do not enter any transaction types here, the system interprets all positions as liabilities.

If you set the Crcy Translation for Key Date checkbox, the system translates the amounts in a foreign currency into EUR based on the exchange rate applicable on the key date.

If you do not set the checkbox, the system translates the amounts into EUR on the key date of the movement.

Create File per Company Code

No File When Below Limit

Use Cntry/Reg. Code XS for RS

In the country/region directory for foreign trade statistics of the Federal Republic of Germany, the code XS is required as the ISO alpha 2 code for Serbia. However, the ISO code RS is used in transaction FZ5A. The indicator can be used to set that transaction FZ5A uses the code XS instead of RS.

Don't Check Industry f. Person

Transaction FZ5A checks whether the Industry field is filled and issues a corresponding message as a warning if the industry is empty. However, the industry sector can be empty for a natural person. The indicator can be used to deactivate the check.

- e. Run the program.
- f. First, an error log appears and then the Selection of lists of results screen appears. You can view the following lists of results:


Analyzed transactions/loans for Z5 and Z5a

Z5 result: fields 02 to 05

Z5A result: fields 22 to 25

Z5A result: fields 62 to 65

Z5A result: fields 66 to 69

Z5A result: fields 72 to 75

CSV download

The system displays the lists of results using SAP List Viewer for SAP GUI (Classic). The SAP List Viewer print and download functions are available in the lists.

If you select CSV Download, the system saves the Z5 and Z5a reports in several CSV files. You can change the names of these files manually before the data is saved.

###### Statutory Reporting for Insurance Companies (FS-SR)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Statutory Reporting for Insurance Companies (FS-SR) | L7 | trm10 p.166 | loio `8a7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8a7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Purpose**

The ledger-based Statutory Reporting for Insurance Companies (FS-SR, Financial Services - Statutory Reporting) comprises functions that are based on the new statutory regulations in circulars issued by the German Federal Financial Supervisory Authority (BaFin).

For positions managed in Investment Management (FS-IMA), Statutory Reporting for Insurance Companies provides support for requirements regarding quarterly statutory reporting and notifications for premium reserve funds, as wells as capital investment notifications in accordance with the Regulation on Reporting by Insurance Undertakings to the Federal Financial Supervisory Authority (BerVersV). Connection to the data transfer interface for supported statements is ensured.

Statutory reporting also offers extensive reporting as well as options for flexible display and extensive analysis.

**Implementation Considerations**

Prerequisites for the Requirements of the 2004 Asset Regulation and 2005 Circulars in Germany

If you have carried out the conversions to ledger-based statutory reporting, you need to carry out additional conversions to cover the requirements of the 2005 circulars. You can find the necessary assignment tables in Customizing for Statutory Reporting under Regulatory Reporting Conversions Germany Conversion to R11/2005 .

Also ensure that the sample Customizing shipped by SAP has been imported correctly and that the statutory reporting additional classifications for the affected assets have been maintained in accordance with the new regulatory provisions.

**Caution:**

For more information about the necessary conversion activities, see SAP Note 889967.

**Integration**

Feeder Systems

Statutory reporting has interfaces for transferring data from the following feeder systems: Treasury and Risk Management (Transaction Manager, TRM-TM) for securities and money market trading, Loans Management (FS-CML) for loans, and Asset Accounting (FI-AA) for real estate.

You also have the option to integrate other systems and components, from which you can then determine relevant data.

Access to Functions and Customizing

The ISSR menu provides you with fast access to the functions and Customizing activities of statutory reporting. To access this menu, enter ISSR in the command field of the initial screen.

**Note:**

You can also find the statutory reporting functions in the SAP Easy Access menu under Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Information System Reports Regulatory Reporting Germany: Regulatory Reporting Regulatory Reporting for Insurance Supervisory Authority . The menu as such is not integrated into the menu areas for Loans Management and Asset Accounting.

You can find the Customizing settings in the SAP Reference IMG under the following areas:

Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Information System Regulatory Reporting Settings for the Insurance Supervisory Authority


SAP Banking Loans Management Information System Regulatory Reporting for Insurance Companies


**Features**

The new statutory reporting comprises the following functions:

Management of multiple valuation areas

Option to connect to external feeder systems

Separate historical data management

Separate position management in the Special Ledger (FI-SL)

Flexible update of data through extended position management (dependent on Customizing settings)

SR indicator change/transfer of premium reserve fund

Extensive list output functions

Output and backup of ALV lists (online and with background processing)

Editing and simulation options as well as drill-down functions (detailed display) for a range of general reports

Additional option to drill down to totals rows and of-which indicators in the individual lists

Customization of lists and reports

Generation of submittable lists and reports that meet the standards required by BAFin (as PDF-based print forms and reports)

Lists and Reports

Currently (as at August 2005), the following are available for German Statutory Reporting for the Insurance Supervisory Authority:

Reports for Premium Reserve Fund

Inflow and outflow lists

Real estate registers

Repayment lists

Summarized premium reserve fund list

Reports for Quarterly Statutory Reporting in Accordance with BaFin Circular 11/2005

Notification for acquisition or change of shareholdings (Shareholdings Annex)

Report on the positions of shares (Fund Annex) in:

Non-coordinated special invested assets and investment companies

Special real-estate invested assets and investment companies

Mixed special invested assets and investment companies

Coordinated special invested assets and investment companies

Shares that were issued by a domestic investment company with variable capital

Notification for acquisition of assets at affiliated companies (Affiliated Companies Annex)

Report on mixing of assets in the premium reserve fund and in all restricted assets (Mix Annex)

Report on diversification of restricted assets (Diversification Annex)

Report on structured products in accordance with R3/99 (Structured Products Annex)

Report on asset-backed securities (ABS) and credit-linked notes (CLN) as well as other investments that serve the transfer of credit risks, in accordance with R1/2002 (ABS/CLN Annex)

Report on hedge fund in accordance with R7/2004 (Hedge Fund Annex)

Quarterly report for composition of capital investments (NW670)

Quarterly report on book and time values for capital investments and coverage of insurance-related liabilities (NW671)

Quarterly report on financial innovations within capital investments (NW673)

In the Area of BerVersV:

Development of capital investments (NW101)

Quarterly information on development of capital investments (NW600)

Revenue from and expenses for capital investments (NW201) – partially supported, as far as possible from the SAP system

Quarterly information on value of capital investments (NW605)

Shares in affiliated companies and shareholdings (Sample 01)

**Restrictions**

The statutory reporting component currently (as at August 2005) does not include the following reports:

Real Estate Annex

Due to restructuring of regulatory reporting for the insurance supervisory authority in 2005, the following reports are no longer in the delivery scope:

Quarterly reporting area:

Report on investments in profit participation rights, receivables from subordinated liabilities, unlisted stock, and shareholdings in companies

Notification for acquisition of shares in special securities funds, special investment funds, and special property funds

Report on investments in loans to companies

Report on investments according to §1 para. 2 of Asset Regulation (AnlV) (opening clause)

Report on fixed accepted values of land, land rights, and shares in real estate companies in premium reserve funds

In the area of BerVersV:

Composition of capital investments (NW102)

###### Current Legal Situation (Since January 1, 2003)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Current Legal Situation (Since January 1, 2003) | L7 | trm10 p.169 | loio `607acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/607acb53f0f67314e10000000a174cb4.html?locale=en-US)

In Germany, insurance companies are subject to supervision of the BaFin (German Federal Financial Supervisory Authority), whose framework is based on the Insurance Supervision Act (VAG), which contains extensive rules on the business activities of insurance companies. A key instrument for supervision is extensive reporting of insurance companies to the BaFin.

On the one hand, this reporting is governed by the regulation on reporting of insurance companies to the BaFin (BerVersV), while on the other hand, particularly for capital investments of insurance companies, reporting obligations arise from the regulation governing the placement of the restricted assets of insurance companies (AnlV) in conjunction with diverse implementing provisions from the BaFin (general provisions in circular R29/2002; quarterly provisions in circular R30/2002; premium reserve fund lists in circular R31/2002).

The BaFin circulars R29/2002 to R31/2002 contain fundamental changes to the requirements for insurance statutory reporting in the area of capital investments. The functions of the statutory reporting component have been adapted in line with the legal changes, whereby premium reserve fund lists have been rewritten and extensively revised in accordance with R31/2002 and quarterly lists in accordance with R30/2002.

Especially in life insurance, management of capital investments is closely linked to questions of managing the premium reserve fund or overall restricted assets. In turn, provisions related to this can be found in the Insurance Supervision Act and in R31/2002.

New Regulations of Current Circular

With the entry into force of the new 2005 reporting circular on the investments of insurance companies, formation and management of the premium reserve fund list, as well as the changed provisions of the 2004 Asset Regulation, the German Federal Financial Supervisory Authority (BaFin) has extensively reformed the reporting requirements again for insurance companies.

These changes are reflected in the statutory reporting component.

**Changes in the Forms of Investment Following the Regulation Governing the Placement of the Restricted Assets of Insurance Companies**

The provisions of the 2004 Asset Regulation stipulate that investment types must be reassigned in accordance with the catalog. Conversion report ISSR_ANLV_2004 is provided for the reassignment of asset types.

**Changes According to 2005 Reporting Circular**

The official BaFin reporting circular R11/2005 (VA) has resulted in changes in the following areas:

Extensive enhancements to maintenance of statutory reporting additional classifications and look-through tables for transparent funds.

The reporting circular R11/ 2005 enhances the statutory reporting additional classifications for capital investments (ISSR_SPEC_ASSET or ISS_SPEC_ASSETB).

Changes to annexes and statements

Circular R11/2005 (VA) has resulted in fundamental revisions to the annexes in quarterly reporting as well as statements in accordance with BerVersV. The reports shipped as standard are based on the current reporting requirements of this circular.

**Caution:**

Reports that no longer need to be submitted to the BaFin still exist in the system but are no longer maintained.

**Changes According to Current Circular R11/2005 (VA) on the Formation and Management of the Premium Reserve Fund List**

Circular R12/2005 (VA) on the formation and management of the premium reserve fund list has led to terminology and content changes in the reports. The key terminology changes are:

The German term Deckungsstock has been changed to Sicherungsvermogen.

The German term Deckungsstockvermogensverzeichnis has been changed to the general term Vermogensverzeichnis.

The German term Ubrige gebundene Vermogen will in future be referred to as Sonstigem gebundenen Vermogen.

The previous asset category (German term) Freies Vermogen will in future be identified as Restliches Vermogen.

###### Integration

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration | L7 | trm10 p.170 | loio `277acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/277acb53f0f67314e10000000a174cb4.html?locale=en-US)

Use

To create lists, the system requires data and information on capital investments from the feeder system. For this purpose, interfaces to the following areas/feeder systems are available: loans (FS-CML), securities/money market trading (Transaction Manager of Treasury and Risk Management, TRM-TM), as well as real estate (Asset Accounting, FI-AA).

**Statutory Reporting Master Data**

In statutory reporting (SR), SR-specific information about loans, financial transactions, securities, and business entities is stored in an SR-specific master data table (ISSR_RPI_MFT). Statutory reporting master data includes the additional indicators for flows of capital investments that are required for reports for the insurance supervisory authority.

**Note:**

Besides these indicators, the system requires the SR additional classifications that you define directly for a capital investment in statutory reporting.

**Flows for Capital Investments**

Flows for capital investments in the feeder systems are normally transferred to the statutory reporting feeder database initially. When transferring the flows to the statutory reporting ledger, the system summarizes these flow records and enriches the data records, for example, with the information from the master data table.

You can use transfer reports to transfer the feeder system flows manually to the feeder database, where you can subsequently edit or delete individual data records. For more information, see Transfer and Editing of Flows (Feeder Database).

**Note:**

If you want to transfer feeder system flows directly from the completed business transaction (that is, when generating an SRrelevant flow in the feeder system) to the SR ledger, you can perform an online posting.

To transfer the flows as statutory reporting flows from the feeder database to the ledger tables, you then need to perform subsequent posting. For more information, see Subsequent Posting.

**Connecting Additional Feeder Systems**

If required, you can connect other feeder components or systems to statutory reporting, in order to transfer data from them.

The standard system has a connection to the Individual Value Adjustment (RBD) component for loans management. For more information, see Transfer of Flows for Value Adjustment.

**Caution:**

The connection of additional components requires extensive modifications and interface developments. For more information, see Customizing under Regulatory Reporting Settings for the Insurance Supervisory Authority Source Systems .

**Additional Integration Tools**

To show monthly depreciation in the statutory reporting valuation areas of asset handling, you can use the function Subsequently Post Periodic Depreciation/Input Tax on Assets.

###### Statutory Reporting Master Data

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Statutory Reporting Master Data | L8 | trm10 p.171 | loio `187acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/187acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Definition**

Master data comprises statutory-reporting-specific indicators and characteristics for a securities account (or securities account position indicator), loan contract, money market transaction, and real estate that are required for statutory reporting for the insurance supervisory authority.

The SR master data for an asset is stored in a separate master data table (SSR_RPI_MFT).

**Caution:**

When generating the list, the system reads the data managed in the master data table as well as other statutory-reportingrelevant data (partner data, conditions, class data, and contract data) at runtime from the feeder systems. The corresponding

list documentation in the system shows you which data is needed for the individual lists.

**Use**

When transferring flows from the feeder database to the statutory reporting ledger tables, the system reads the master data in the master data table and generates a statutory reporting ledger flow from a combination of flow record and master data record.

**Caution:**

For the real estate area, flow records for assets relevant for reporting are not managed in the ledger tables but in the master data records. They also exist in master data table ISSR_RPI_MFT.

For information about master data entry (both in feeder systems and directly in statutory reporting), see Master Data Entry for Statutory Reporting.

**Integration**

You can find the Customizing settings for master data transfer in the Implementation Guide for Statutory Reporting under Variant-Dependent Settings Master Data Entry for SR Identifiers .

Reporting Data for Business Partners

For business partners, you also need to define data relevant for statutory reporting. You make these entries on the Reporting Data tab or (for company-code-dependent data) Reporting Data in Company Code tab.

###### Master Data Entry for Statutory Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Statutory Reporting Master Data > Master Data Entry for Statutory Reporting | L9 | trm10 p.172 | loio `a27acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a27acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

You can edit statutory reporting master data in the feeder system itself (for loans, securities, and financial transactions) or directly in SAP Statutory Reporting for Insurance.

In SAP Statutory Reporting for Insurance, the following differentiation criteria are available to you for master data maintenance in the securities area:

Securities account

Portfolio

Securities account group

**Note:**

Entry in the feeder system is not available for real estate.

**Prerequisites**

You have made the necessary Customizing settings and have created master data for a capital investment (loans, class, money market transaction, real estate).

For the entry of master data, the necessary Customizing settings are available as standard Customizing (under VariantDependent Settings Master Data Entry for SR Identifiers ).

**Recommendation:**

At product type/product category level, it makes sense to specify default values and required entry fields (in the named IMG area). However, you cannot change the assignment of field texts for the processing screen of the function. These settings are shipped as standard settings and must not normally be changed.

**Features**

Depending on the Customizing settings, the system checks your entries for consistency or populates input fields.

**Activities**

To enter the master data directly in SAP Statutory Reporting for Insurance, choose Flows for Capital Investment Enter Master Data in the statutory reporting menu.

Entry in Feeder Systems

For securities and money market trading (Transaction Manager), you specify master data for one of the aforementioned differentiation criteria.

You can also edit the data defined for a position indicator in the Enter Master Data statutory reporting function. The data defined for a securities account (stock, division, and date for first securities account validity) cannot be subsequently changed in statutory reporting.

You define the master data for a contract in loans management.

You can edit most of the data also in the Enter Master Data statutory reporting function.

For business entities in the real estate area, you define the master data directly in statutory reporting in the Enter Master Data function.

###### Creation of Master Data

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Statutory Reporting Master Data > Creation of Master Data | L9 | trm10 p.173 | loio `3c7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Using transaction ISSR_ADMN_ASSET, you can create statutory reporting master data directly at the level of the differentiation criterion that is specified in SAP Financial Asset Management (FAM). For example, if you want to create the position indicator in SAP Financial Asset Management automatically during creation of the first business transaction, it is not necessary to create the

statutory reporting data additionally.

You can create statutory reporting master data at the following levels:

Business entity (real estate area)

Differentiation criterion (Financial Asset Management)

Financial transaction (money market trading area)

Contract (loans area)

For creating statutory reporting master data, SAP Statutory Reporting for Insurance supports the following differentiation criteria:

Portfolio

Securities account group

Securities account

**Integration**

You can create the statutory reporting master data in one of the following ways:

Directly in SAP Financial Asset Management

You can create the statutory reporting master data directly in SAP Financial Asset Management by means of creating the securities account position indicator (transaction TPM55).

Here, enter the following selection parameters:

Product group

Company code

General valuation class

ID

Securities account

Portfolio

You can also use this function at contract level for the loans area and at financial transaction level in the money marketing trading area.

In SAP Statutory Reporting for Insurance

You can create the statutory reporting master data using transaction ISSR_ADMN_ASSET.

If you have already posted business transactions to this position indicator, note the following:

Changing statutory reporting master data

You can then only still change the statutory reporting master data using the function for changing capital reserve transfer postings (transaction ISSR_DSUMB).

Deleting statutory reporting master data

You can then no longer delete statutory reporting master data.

**Prerequisites**

In Customizing for SAP Statutory Reporting for Insurance, you have carried out the Customizing activities under VariantDependent Settings → Master Data Entry for SR Identifiers.

**Activities**

Call up transaction ISSR_ADMN_ASSET.

Choose Create Master Record.

In the next dialog box, enter the required data:

Statutory reporting variant

Differentiation key

Company code

Statutory reporting product category

Statutory reporting product type

Capital investment number

Depending on the differentiation criterion set in SAP Financial Asset Management, you also enter the following data:

Securities account

Portfolio

Securities account group

When entering the data, note the following:

The following fixed values are predefined as differentiation keys:

Differentiation Criterion CFM (DC)

Real Estate (002)

Securities/Loans (001)

If you enter the value Differentiation Criterion CFM as the differentiation key, the system generates a statutory reporting master record at the level of the differentiation criterion that is set in SAP Financial Asset Management.

If you use the value Differentiation Criterion as the differentiation key, enter the following values:

Valid-from date

Insurance line of business

Capital reserve

If you enter the value Securities and Loans or Real Estate as the differentiation key, you can enter the other statutory reporting master data (including identifiers for statements, identifiers for Mix annex, and so on).

The system then saves this additional data persistently to the statutory reporting master data table ISSR_RPI_MFT at company code, capital investment number, and differentiation criterion CFM level.

Note the following here:

The system cannot persistently save the differentiation criteria that you have not specified in the key fields.

When you enter the key fields, the system looks for the differentiation criterion in the CFM Customizing settings. For example, if the differentiation criterion Portfolio is defined for the company code in CFM, this attribute is a mandatory entry for the key fields for the statutory reporting master data.

In the real estate area, you cannot create the statutory reporting data directly in the business entity.

After you have entered all of the statutory reporting master data, you can check the values entered. To do this, choose Check Entries.

Choose Save.

The system saves the data persistently to the statutory reporting master data table ISSR_RPI_MFT.

On the Worklist tab, you can display the key fields of the previously processed master records and the master record currently being processed, at any time.

###### Transfer and Editing of Flows (Feeder Database)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Transfer and Editing of Flows (Feeder Database) | L8 | trm10 p.176 | loio `a87acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a87acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Statutory reporting provides you with functions that you can use to transfer flows from securities, money market trading, and loans feeder systems to the statutory reporting feeder database or generate documents directly in the feeder database and transfer them to the statutory reporting ledger.

**Note:**

If you want to transfer feeder system flows online (that is, when generating an SR-relevant flow in the feeder system) from the feeder system to the SR ledger, you can perform an online posting. You only then need to execute the functions specified here as well as subsequent posting to correct or rebuild flows in the SR ledger.

**Integration**

You can delete data transferred to the feeder database or edit individual documents and transfer them to the statutory reporting ledger.

To transfer the flows to the statutory reporting ledger, you then carry out the subsequent posting. From the flows stored in the feeder database and from the statutory reporting master data record, the system hereby generates an SR ledger flow (see Flows in Statutory Reporting).

**Features**

The following functions are provided for transferring flows to the feeder database and editing flows:

Import of Feeder System Flows

Deletion of Transferred Flow Data

Single Entry of Documents

**Caution:**

Flow records for real estate are not managed in the statutory reporting ledger tables. These flows are read from asset accounting at run time when the lists are created.

For more information about transferring RBD flows, see Transfer of Flows for Value Adjustment.

###### Import of Feeder System Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Transfer and Editing of Flows (Feeder Database) > Import of Feeder System Flows | L9 | trm10 p.177 | loio `097acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/097acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Statutory reporting provides various programs that enable you to transfer flows generated in the areas of money market trading, securities, and loans to the statutory reporting feeder database.

**Caution:**

To transfer the flows as statutory reporting flows to the ledger tables, you then need to perform subsequent posting. For more information, see Subsequent Posting.

The following import functions are available:

Import for Securities/Money Market Trading

To import flow data from the areas of money market trading and securities of Transaction Manager, you can use report RISSR_MIG_CFM. This report allows you to import flows from the various valuation areas. For more information, see Transfer of Flows for Securities/Money Market Trading.

Import for Loans

To import flows from Loans Management, you can use report RISSR_MIG_LO.

**Caution:**

With Release Enterprise 2.0, management of the operative valuation area was changed in the feeder system (securities/money market trading). The previous tables have been replaced with new structures.

The transfer reports valid up to Release Financial Services 2.0 still exist in the system but must no longer be used.

For more information about the transfer, see Transfer of Flows for Loans

**Integration**

You need the transfer reports for importing feeder system flows for securities, money market transactions, and loans in the followng cases only:

Online posting is deactivated.

You therefore need to import the flows to the SR feeder database at specific points in time manually using the transfer reports.

You need to correct errors.

Due to system and/or Customizing errors, incorrect flows were transferred to statutory reporting. You can delete these from the SR feeder database and then transfer them again.

You want to reconfigure the system.

After position initialization has been executed, you can use these transfer reports to transfer relevant flows (date after initialization up to today's date).

###### Transfer of Flows for Securities/Money Market Trading

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Transfer and Editing of Flows (Feeder Database) > Import of Feeder System Flows > Transfer of Flows for Securities/Money Market Trading | L10 | trm10 p.178 | loio `367acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/367acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Using report RISSR_MIG_CFM, you can import flows for securities and financial transactions from the parallel or operative valuation area of the Transaction Managers to statutory reporting.

**Integration**

If necessary, you can use the Delete Documents function to delete transferred data records from the feeder database, for example, if errors occurred in Customizing for SR flow type parts (FTPs). You can find this function in the statutory reporting menu under Flows for Capital Investment Edit Imported Data Delete Documents .

**Prerequisites**

You have defined the SR flow type parts and made the necessary assignments between the feeder system flow types and the SR flow type parts for the respective ledger types.

If you are using parallel valuation areas, you have assigned these areas to the statutory reporting valuation areas.

You can find the necessary Customizing settings in the Implementation Guide for Statutory Reporting under Migration/Import Capital Investment Flows Conversion .

**Features**

The report transfers all of the flows from the specific area for the selection criteria entered.

With position initialization, only those flow records are transferred that lie after the time of position initialization.

Output

The system shows transferred flows in the SAP List Viewer. In the output list, you can display the non-transferred flows in an error list by choosing Goto Error Log (SHIFT+F7).

If you have started the report in the background, you can subsequently display the error log using the Log Administration: Display application (transaction SLG1 with object: ISSR).

###### Transfer of Flows for Loans

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Transfer and Editing of Flows (Feeder Database) > Import of Feeder System Flows > Transfer of Flows for Loans | L10 | trm10 p.178 | loio `637acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/637acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Using report RISSR_MIG_LO, you can transfer flows from the loans area to statutory reporting.

You can start the report repeatedly.

In the loans area, note that migration often involves data volumes that can push the system to its limits (for example, program memory, working memory, and so on).

To prevent program or system overruns, you should always use selection criteria (for example, migration at year and ledger level - ledger type B, E, and R - or restrict by contract number and/or product types).

**Integration**

The report is dependent on the settings that you have made for position initialization (report RISSR_MIG_LO_BST).

If necessary, you can use the Delete Documents function to delete transferred data records from the feeder database, for example, if errors occurred in Customizing for SR flow type parts (FTPs). You can find this function in the statutory reporting menu under Flows for Capital Investment Edit Imported Data Delete Documents .

**Prerequisites**

You have defined the SR flow type parts and necessary assignments between the feeder system flow types and the SR flow type parts for the respective ledger types.

You can find the necessary Customizing settings in the Implementation Guide for Statutory Reporting under Migration/Import Capital Investment Flows Conversion .

**Caution:**

Before you carry out an individual transfer of all data records, perform position initialization/migration using the report RISSR_MIG_LO_BST. With position initialization, only those flow records are transferred that lie after the time of position initialization.

**Features**

You can set general and dynamic selections:

Using the Include reversal records? indicator, you can specify whether the report is to import reversed records and reversal records.

**Caution:**

If reversal flows (posting date after position initialization) reverse flows from the position initialization period (that is, if you have reversed documents with a posting date that lies after the position initialization date), you must select the Include reversal records? indicator.

**Example:**

You have executed position and flow migration with a date of December 31, 2002. However, the migrated position contains a document that was reversed with a reversal document (date) of January 10, 2003. You therefore select the Include reversal records? indicator to ensure that the system also transfers this document.

If you select the Check for Duplicate indicator, the system checks whether the record to be written already exists in the database.

If you select the Detail Log indicator, the system performs and records a detailed analysis for every single imported record.

The Check for Duplicate and Detail Log indicators must only be used for importing small quantities of data and not for data migration of larger positions, otherwise the runtime is extended accordingly, causing unnecessary load on the program memory, working memory, and so on.

The system shows transferred flows in the SAP List Viewer. You can display the non-transferred flows in an error list by choosing Goto Error Log (SHIFT+F7).

If you have called the report using a batch run, you can subsequently display the error log using the Log Administration: Display application (transaction SLG1 with object: ISSR).

###### Deletion of Transferred Data

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Transfer and Editing of Flows (Feeder Database) > Deletion of Transferred Data | L9 | trm10 p.180 | loio `6c7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6c7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Using report RISSR_MIG_DELETE, you can delete the selected data records from the statutory reporting feeder database (ISSRPREFLOW).

**Activities**

To start the report from the statutory reporting menu, choose Capital Investment Flows Edit Imported Data Delete Documents .

###### Editing Single Documents Manually

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Transfer and Editing of Flows (Feeder Database) > Editing Single Documents Manually | L9 | trm10 p.180 | loio `877acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/877acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

This function enables you to create, change, or cancel documents for the SR feeder database, or post them to the statutory reporting ledger.

This function is useful in the following situations:

Existing documents were transferred from the feeder systems incorrectly.

You want to generate flows for insurance statutory reporting that do not exist in the feeder systems.

**Caution:**

Flows that you have edited using this function can lead to only limited matching with the feeder systems being possible.

**Activities**

In the statutory reporting menu, choose Flows for Capital Investment Edit Imported Data Edit Documents Manually .

###### Transfer of Flows for Value Adjustment

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Transfer of Flows for Value Adjustment | L8 | trm10 p.180 | loio `2a7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2a7acb53f0f67314e10000000a174cb4.html?locale=en-US)

Use

You can connect the component for individual value adjustment (RBD) for loans management to statutory reporting to enable you to transfer value adjustment flows.

Currently, only integration for list output (transfer at runtime via function module) is supported. The feeder system flows are hereby read from the feeder system databases directly when a list is created and converted to the list output format.

Transfer and conversion takes place at runtime by means of function module ISSR_GET_RESERVE_BAD_DEPTS.

**Integration**

You can find the Customizing settings for connecting the RBD component as a feeder system of statutory reporting in the Implementation Guide for Statutory Reporting under Source Systems Connection to Additional Feeder Systems (RBD) . An online update is not supported.

**Prerequisites**

You have made or checked the necessary settings in statutory reporting and for the RBD component. For more information, see the Implementation Guide.

**Features**

For more information about the transfer process, see the function module documentation.

###### Subsequently Post Periodic Depreciation/Input Tax on Assets

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Integration > Subsequently Post Periodic Depreciation/Input Tax on Assets | L8 | trm10 p.181 | loio `6f7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6f7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

For real estate, you can use report RFVZANL0_PERIOD on the basis of the main valuation areas for a closed settlement period (monthly) to generate depreciation amounts or input tax postings using batch input sessions (which need to be run subsequently) in the statutory reporting valuation areas.

You use this function if you want to display annual depreciation at month level in statutory reporting. The values are read from the statutory reporting valuation areas when the list is generated.

**Note:**

Alternatively, the depreciation flows at asset level can be posted directly to the valuation areas using transaction AB01.

**Integration**

A valuation area for stock 1, 2, and 3 must be set up in the system. As a rule, this is valuation area 91 (stock 1 and 2) and 92 (for stock 3).

**Prerequisites**

In book depreciation, depreciation must be posted.

Features

From the totals determined in a closed period, the report generates flows for periodic depreciation or input tax. You can execute the posting at business entity or asset/asset subnumber level.

**Activities**

To start the report from the statutory reporting menu, choose Flows for Capital Investment Edit Imported Data Subsequently Post Periodic Depreciation/Input Tax on Assets .

###### Flows in Statutory Reporting (SR Ledger)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) | L7 | trm10 p.182 | loio `b17acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b17acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Purpose**

The Statutory Reporting Flows menu contains applications that allow you to edit and display SR ledger flows (statutory reporting flows).

Statutory reporting flows contain all of the data that statutory reporting uses as a basis for generating lists (together with the master data and other feeder system information that is also read for generating lists).

The system generates these flows in the statutory reporting ledger in the following cases:

Automatically after an SR-relevant feeder system flow has been posted (real-time integration through online posting)

From the feeder system flows that were transferred to the feeder database by means of the transfer reports (subsequent posting)

If you create and post manual documents

If you perform a transfer posting within the ledger (between asset categories)

**Caution:**

Flow records for real estate are not managed in the statutory reporting ledger tables. These flows are read from asset accounting in real time when the lists are created.

**Integration**

For information about transferring feeder system flows to the feeder database, see Import of Feeder System Flows.

**Features**

To generate flows, the system summarizes the data from the feeder database, enriches the data records with the relevant statutory reporting master data, and fills the relevant ledger tables.

You can use the following functions to generate and edit statutory reporting flows:

The online posting enables you to automatically transfer flow records from the feeder system to the statutory reporting ledger. To do this, the system generates the corresponding statutory reporting ledger flow for each relevant posting in the feeder system.

Subsequent posting enables you to generate statutory reporting flows from the feeder database.

You can use this function if you have transferred the feeder system flows to the feeder database using the import reports (see Import of Feeder System Flows).

The Generate Flows from BP Change function enables you to generate flows from a business partner change.

The asset category transfer posting enables you to make changes if SR-relevant characteristics for a capital investment change.

You can display and delete statutory reporting flows.

###### Statutory Reporting Ledger

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Statutory Reporting Ledger | L8 | trm10 p.183 | loio `037acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/037acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Definition**

Special ledger in which the position and flow data transferred to the SR component is managed in SR format.

**Use**

In statutory reporting (SR), SR-specific data records for positions and flows are stored in the statutory reporting ledger.

**Structure**

The system manages the ledger positions in the FI-SL ledger tables of table group ISSRFLDE.

The table group is shipped with fixed SR-specific ledgers whose name is not in the customer namespace:

Position ledger (3I)

Revenue ledger (3J)

Receivables ledger (3F)

Ledger table ISSRFLDEA contains line items, while table ISSRFLDET is a totals table.

**Integration**

If you are using statutory reporting for the first time, you first need to perform position initialization and then import feeder system flows or activate the online posting.

###### Online Posting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Online Posting | L8 | trm10 p.183 | loio `5d7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5d7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

The online posting enables the system to perform a real-time transfer of feeder system flows (money market trading, securities, and loans) to the statutory reporting ledger and thus create statutory reporting flows.

The transfer takes place at the same time as the update of flows in the feeder system.

**Caution:**

Flow records for real estate are not managed in the statutory reporting ledger tables. These flows are read in real time when the lists are created.

**Integration**

You can display and also delete transferred data records in the statutory reporting ledger.

**Prerequisites**

You have activated statutory reporting system wide and for a company code and have made the general settings for generating the ledger position.

You have maintained the necessary master data in the master data table (see Master Data Entry for Statutory Reporting).

You have made the required Customizing settings for generating ledger flows.

You can find the necessary Customizing settings as well as information about the settings in the Implementation Guide for Statutory Reporting under Migration/Import and Variant-Dependent Settings General Settings .

**Features**

When creating the statutory reporting flows, the system performs the following steps as part of the online posting:

- 1. Transfer the flow data records from the relevant feeder system tables to the statutory reporting feeder database (ISSRPREFLOW)
- 2. Enrich the data records with the data from statutory reporting master data table ISSR_RPI_MFT
- 3. Generate a ledger flow (data record in the ledger table)


**Activities**

You can activate and deactivate the online posting system wide in the Customizing activity Activate Regulatory Reporting (transaction ISSR_MAIN22).

###### Subsequent Posting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Subsequent Posting | L8 | trm10 p.184 | loio `0f7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Subsequent posting is available for the following situations:

You have transferred feeder system flows to the SR feeder database using the transfer reports.

From these flows, you now need to generate statutory reporting flows through subsequent posting.

You want to correct errors in positions.

To do so, you first delete incorrect positions and then rebuild the flows with the help of subsequent posting.

**Caution:**

Flow records for real estate are not managed in the statutory reporting ledger tables. These flows are read in real time when the lists are created.

Prerequisites

You have transferred flows from the feeder systems to the statutory reporting feeder database (see Import of Feeder System Flows).

You have maintained the necessary master data in the master data table (see Master Data Entry for Statutory Reporting).

You have made the necessary Customizing settings for generating ledger flows (in the Implementation Guide for Statutory Reporting under Variant-Dependent Settings General Settings ).

**Features**

The system generates ledger flows by connecting the SR feeder database (table ISSRPREFLOW) to the SR master data (table ISSR_RPI_MFT).

**Activities**

In the statutory reporting menu, choose Statutory Reporting Flows Generate Flows (transaction ISSR_NB1).

**Note:**

To optimize the data volume and thus performance, you should restrict at least by company code, ledger type (B), and capital investment type.

###### Transfer of Business Partner Changes

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Transfer of Business Partner Changes | L8 | trm10 p.185 | loio `1b7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Using report RISSR_GP_CHANGE, you can generate flows from a business partner change (BP change).

**Prerequisite**

The logging table for change documents is filled and not archived for the time period to be analyzed.

**Integration**

Start report RISSR_GP_CHANGE only using the Generate Flows from BP Change application (transaction ISSR_GP_CHANGE in the statutory reporting menu under Statutory Reporting Flows), otherwise the selection options of the selection screen are not available to you.

**Features**

The report:

Considers BP changes at class level and BP changes for non-customer loans

Reads the change documents from the tables CDPOS and CDHDR

Processes the documents with the associated master data from table ISSR_RPI_MFT

Selects the corresponding flow data records from table ISSRFLDEA

Determines the position at the time of a BP change

The system then creates, for each position, an outflow record at the level of company code, SR variant, valuation area (and, if necessary, securities account) with the previous business partner and an inflow record with the new business partner.

Flow data records that are upstream or downstream in relation to the time of the BP change may be switched to the previous/new business partner. The system adjusts the position flows before and after the BP change; the number of flow data records in the ledger changes accordingly.

When you start the Generate Flows from BP Change application, a selection screen appears in which you can specify the start conditions for inserting data records for the BP changes.

**Caution:**

Note here that the selected Analysis Period is used a basis for determining the Change Documents that belong to a BP change: The system determines all of the documents with a creation date that lies outside of the period selected. The data does not refer to the BP change as such.

You can start the report in a test run or an update run.

In addition, the system creates a log while the program is running.

**Activities**

Under Select Database, you specify which data source you want the report to access. If you start the report with the Use Change Documents option, the system writes the information from the change document tables to the SR management table TISSR_GP_CHANGE.

**Caution:**

When executing the report for the first time, you must select this option.

If you are sure that there have been no more BP changes since the Generate Flows from BP change application was last started in

the analysis period, and if you have already started the report once with the Use Change Documents option, then choose the Use SR Table option. The report then accesses the already filled table TISSR_GP_CHANGE to import the BO change into the statutory reporting component. Use of table TISSR_GP_CHANGE can reduce program runtime considerably.

The selected processing period only affects program control if the program runs in the background: If the job is to run periodically in the background, the system determines the analysis period automatically based on the entries made on the selection screen under For Background Processing: Select Processing Period:

|Option|System Response|
|---|---|
|None|The program does not determine any period at runtime to ensure that all of the relevant BP changes are selected and processed.|
|Monthly|The system considers only the period between the system date and the same day of the previous month (calculated month).|
|Quarterly|The system considers - starting from the system date - the period of the last three months (calculated months).|
|Yearly|The system considers - starting from the system date - the period of the last year (calculated year).|


The result screen contains two ALV Grid structures:

In the top part of the screen, the system shows the selected BP changes that lead to position flows in the ledger tables when the program is run.

In the lower part of the screen, the system shows the generated ledger flows. To reduce the number of flow data records displayed at capital investment level, select a data record in the top part of the screen and then choose Detail.

To access the log of the program flow, choose Log/ Log (Test).

**Note:**

If you have started the Generate Flows from BP Change application in the background, the system saves the log to the database automatically by means of log management. You can then access and display the log in log management (transaction SLG1 with object ISSR).

###### Deleting SR Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Deleting SR Flows | L8 | trm10 p.187 | loio `337acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/337acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

If errors occur in Customizing, when data is transferred, or in other cases, you can use report RISSR_NABU_DELETE to delete the affected ledger flows from the ISSRFLDEA (Line Item Table) and ISSRFLDET (Totals Table) ledger tables.

**Caution:**

Note that the deletion log only displays the records of totals table ISSRFLDET, which means the log normally shows fewer records than were actually deleted in the line item table ISSREFLDEA.

**Features**

You can start the report in a selection or deletion run. The result of the selection run shows you the data records to be deleted based on your selection criteria, while the deletion run immediately deletes the selected records.

###### Displaying SR Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Displaying SR Flows | L8 | trm10 p.187 | loio `8d7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8d7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

You can display flows transferred into the SR system (statutory reporting flows) to monitor the position.

**Prerequisites**

You have transferred flows into the statutory reporting ledger.

**Activities**

Displaying flows as local actual document display

- 1. In the statutory reporting menu, choose Statutory Reporting Flows FI-SL: Local Actual Document Display (transaction GD23).
- 2. To limit the selection, make the required mandatory entries.


- 3. Choose Execute.


Displaying flows as line items

- 1. In the statutory reporting menu, choose Flows Select FI-SL Line Items (transaction ISSR_GD20).
- 2. To limit the selection, make the required mandatory entries.
- 3. Choose Execute.


Displaying flows as totals record

- 1. In the statutory reporting menu, choose Statutory Reporting Flows Totals Record Display (transaction ISSR_GD13).
- 2. To limit the selection, make the required mandatory entries.
- 3. Choose Execute.


**Note:**

The following functions are available in the application:

|Function|Explanation|
|---|---|
|Settings|You can choose between ALV grid and list output; you also have the option to use a user-defined table as a template. This allows you to exclude certain fields from the display. To access the function, choose Extras Settings (F2 key) or the relevant pushbutton in the toolbar.|
|User table|By choosing Extras Maintain User Table (key combination SHIFT+F1 or the relevant pushbutton), you can navigate to the identically named Customizing activity.|
| Extras Exit: Authorization....|You can restrict the display of certain table fields by defining user profiles.|

###### Asset Category Transfer Posting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Asset Category Transfer Posting | L8 | trm10 p.188 | loio `517acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/517acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

If you change statutory-reporting-relevant attributes (indicators) of a position, you need to carry out an asset category transfer posting. An asset category transfer posting refers to transfer posting positions that fall under one of the asset categories.

The following data is hereby changed:

Insurance line of business

Premium reserve fund list number (PRFL number)

PRF subsection

Statement-relevant indicators that are stored in the master data table

**Caution:**

If the assignment of an asset from the securities area to a division or an asset indicator changes, you carry out a securities account transfer.

**Prerequisites**

In the Implementation Guide for Statutory Reporting under Variant-Dependent Settings Change Identifiers/Transfer Posting , you have made the necessary Customizing settings.


Pay particular attention here to the activities General Settings and the activities under Identification Number Assignment. These settings are dependent on the company code and must be defined by the customer.

**Features**

In the application (transaction ISSR_DSUMB, in the statutory reporting menu under Statutory Reporting Flows

Change Identifiers/Transfer Posting) , you make a selection of transferrable capital investments based on various selection criteria. However, a selection of transferrable capital investments is possible only within one company code, one SR variant, and one SR asset category (contract type).

The system lists the selected transferrable positions in a detailed display. Using the ledger flows displayed, you can access feeder system information (such as information about the FI document that is assigned to the ledger flow). From the detailed display, you can now change the attributes relevant to statutory reporting of the selected transferrable capital investments.

**Caution:**

Changes to attributes relevant to statutory reporting are made across valuation areas.

The system manages all attributes relevant to statutory reporting historically.

If you change flow-relevant statutory reporting attributes, the system generates inflow and outflow records for the ledger tables assigned to statutory reporting.

**Caution:**

The outflow records lead to a zero balance of the investment with the old statutory reporting attributes.

For this reason, note that the asset category transfer posting must always be the last position posting of the investment with the old statutory reporting attributes. If, after the asset category transfer posting, you execute other position postings that affect the investment with the old statutory reporting attributes, the position to be transferred is not automatically adjusted to the asset category transfer posting. Such later postings lead to incorrect positions.

For more general information about subsequent posting, see Subsequent Posting.

Log Output

If you execute an asset category transfer posting, the system creates error and plausibility check logs.

If the log output for the posting log is activated in the Customizing settings for statutory reporting (default setting), the system creates the posting log with the information defined in the Implementation Guide. You can find these settings in the Customizing activity Adjust Log Output under Variant-Dependent Settings Change Identifiers/Transfer Posting Log Control .

**Note:**

In this area, the settings in the Customizing activity Assign Messages to Posting Log (Old) are no longer considered as soon as you have converted identifiers (in Germany: Conversion to BaFin Circular R11/2005) and this conversion has been documented by a corresponding entry in table TISSR_CHA_MDATA.

As long as no entry exists in table TISSR_CHA_MDATA, you can only use the posting log defined in the Customizing activity Assign Messages to Posting Log (Old).

###### Data Organization in the SR Ledger

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Data Organization in the SR Ledger | L8 | trm10 p.190 | loio `5a7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

For data organization, there are currently two tools available in Customizing: Balance Carryforward and Currency Translation, which are known from the Special Ledger (FI-SL) component. For more information, see the Implementation Guide for Statutory Reporting under Variant-Dependent Settings General Settings Periodic Processing .

**Prerequisites**

To perform the balance carryforward, you must have already carried out the Customizing activity Automatically Create and Assign Field Assignment ISSR.

Features

|Name|Explanation|
|---|---|
|Currency translation|Currency translation is only relevant if a local currency change at company code level is to be carried out.|
|Balance carryforward|The balance carryforward is much more important than the currency translation.|


Activities

To execute the balance carryforward, call up the Customizing activity Assign Field Movement for Balance Carryforward.

The system automatically creates a field assignment ISSR in the FISL Customizing table and assigns it to the corresponding ledgers 3I and 3J.

**Note:**

You can control the operation in the Customizing activity Assign Field Movement for Balance Carryforward.

###### Archiving of Flow Data

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Archiving of Flow Data | L8 | trm10 p.190 | loio `307acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/307acb53f0f67314e10000000a174cb4.html?locale=en-US)

In Statutory Reporting for Insurance Companies, the following archiving objects are available for archiving flow data:

IS_SR_ITEM (Statutory Reporting: Line Items)

IS_SR_SUM (Statutory Reporting:Totals Records)

###### Archiving of Lines Items in Statutory Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Archiving of Flow Data > Archiving of Lines Items in Statutory Reporting | L9 | trm10 p.190 | loio `457acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/457acb53f0f67314e10000000a174cb4.html?locale=en-US)

Use

In statutory reporting, you can use archiving object IS_SR_ITEM to archive line items to archive files and delete them from the database.

When archiving line items, note the following points:

You can archive at fiscal year level only. Archiving for periods of less than one year is not supported.

You can only archive time periods for which balance carryforwards have been created.

For this reason, you need to check before archiving whether the balance carryforward for the following year already exists.

**Example:**

You want to archive line items for 2003. In this case, the balance carryforward for 2004 must already exist.

Refrain from archiving too soon because ledger tables are frequently changed. The system is therefore set up so that archiving of data from both the current year and last completed fiscal year is not permitted.

In statutory reporting, archiving is always carried out in the following sequence:

- 1. You first archive the line items for a certain period.
- 2. Only then can you archive the totals records for the same period.


**Structure**

Archiving object IS_SR_ITEM is used to archive data from the following tables:

|Table|Name of Table|
|---|---|
|ISSRFLDEA|Actual Line Item table|


**Integration**

You can display the line items from the archive. The line items are displayed using the archive information system.

For displaying archiving object IS_SR_ITEM, the following information structures are available:

- SAP_IS_SR_001 (Line Items by PRFL)

- SAP_IS_SR_002 (Line Items by Statement)

- SAP_IS_SR_003 (Line Items by Asset)

###### Variant Settings for Writing (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Archiving of Flow Data > Archiving of Lines Items in Statutory Reporting > Variant Settings for Writing | L10 | trm10 p.191 | loio `487acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/487acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

When you schedule the write program, you need to enter an existing variant or create a new one. The variant contains the selection criteria for line items in statutory reporting that you want to archive.

**Features**

Document Selection Criteria

In the Statutory Reporting: Line Items section, the following selection criteria are available:

Statutory reporting country variant

The system archives only those line items that are valid for the specified country variants.

Company codes

The system archives only those line items that were posted in the specified company codes.

Fiscal years

The system archives only those line items that were posted in the specified fiscal years.

Other Settings

The settings in the Process Control section, as well as the logging options and archiving run comment, are settings that also apply to other archiving objects.

For more information, see Maintenance of Variants for Archiving Jobs.

**See also**

Generating Archive Files

###### Dependencies (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Archiving of Flow Data > Archiving of Lines Items in Statutory Reporting > Dependencies | L10 | trm10 p.192 | loio `083b96f9c9f64c18a36e0b9d521b2373` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/083b96f9c9f64c18a36e0b9d521b2373.html?locale=en-US)

If you have already archived data for a specific period (that is, in certain company codes and certain fiscal years), you are no longer allowed to changes this data. For this reason, you may call the transactions only for periods or company codes in which the line items or totals records have not yet been archived.

- ISSR_NB1 (Subseq. Post. from Basis Table)

- ISSR_NB2 (Delete SR Database Records)


- ISSR_MIG1 (Migrate/Import Securities)

- ISSR_MIG2 (Migrate/Import Loans)


- ISSR_MIG4 (Migrate/Import Money Market)

- ISSR_MIG5 (Delete Migrations)

- ISSR_MIG6 (Migrate/Import TRL Data (Securities/Money Market Trading))


ISSR_GP_CHANGE (Transfer Business Partner Changes to BaFin Statutory Reporting)

ISSR_DSUMB (Transfer Statutory Reporting Data)

###### Archiving of Totals Records in Statutory Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Archiving of Flow Data > Archiving of Totals Records in Statutory Reporting | L9 | trm10 p.192 | loio `4b7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

In statutory reporting, you can use archiving object IS_SR_SUM to archive totals records to archive files and delete them from the database.

When archiving totals records, note the following points:

You can archive at fiscal year level only. Archiving for periods of less than one year is not supported.

You can only archive time periods for which balance carryforwards have been created.

For this reason, you need to check before archiving whether the balance carryforward for the following year already exists.

**Example:**

You want to archive line items for 2003. In this case, the balance carryforward for 2004 must already exist.

Refrain from archiving too soon because ledger tables are frequently changed.

The system is therefore set up so that archiving of data from both the current year and last completed fiscal year is not permitted.

In statutory reporting, archiving is always carried out in the following sequence:

- 1. You first archive the line items for a certain period.
- 2. Only then can you archive the totals records for the same period.


Displaying the archived data in the archive information system

After you have generated (written) the archive files, you first need to delete this record. Only then does the system display the archived data in the archive information system.

If you have archived totals records, you can no longer carry out BaFin reports with single flows (for example, PRFL inflow/outflow lists) for these totals records for the archiving period.

**Structure**

You use archiving object IS_IR_SUM to archive data from the following table.

|Table|Name of Table|
|---|---|
|ISSRFLDET|Totals Table|


**Integration**

You can display individual totals records from the archive. The records are displayed using the archive information system.

For displaying the archiving object IS_SR_SUM, the following information structures are available:

- SAP_IS_SR_004 (Totals Records by PRFL)

- SAP_IS_SR_005 (Totals Records by Statement)

- SAP_IS_SR_006 (Totals Records by Asset)

###### Variant Settings for Writing (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Flows in Statutory Reporting (SR Ledger) > Archiving of Flow Data > Archiving of Totals Records in Statutory Reporting > Variant Settings for Writing | L10 | trm10 p.193 | loio `3f7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f7acb53f0f67314e10000000a174cb4.html?locale=en-US)

Use

When you schedule the write program, you need to enter an existing variant or create a new one. The variant contains the selection criteria for totals records in statutory reporting that you want to archive.

**Features**

Document Selection Criteria

In the Totals Records section, the following selection criteria are available:

Statutory reporting country variant

The system archives only those totals records that are valid for the specified country variants.

Company codes

The system archives only those totals records that were posted in the specified company codes.

Fiscal years

The system archives only those totals records that were posted in the specified fiscal years.

Other Settings

The settings in the Process Control section, as well as the logging options and archiving run comment, are settings that also apply to other archiving objects.

For more information, see Maintenance of Variants for Archiving Jobs.

**See also**

Generating Archive Files

###### Additional Classifications for Statutory Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Additional Classifications for Statutory Reporting | L7 | trm10 p.195 | loio `0c7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0c7acb53f0f67314e10000000a174cb4.html?locale=en-US)

Purpose

Additional classifications for statutory reporting (SR) are SR-specific indicators that are assigned to a capital investment based on a key date. The indicators are needed for correct generation of annexes and statements.

These indicators are stored in tables TISSR_ASSET_R30 (for securities area) and TISSR_ASSET_R30B (for loans area).

In contrast to SR master data, additional classifications cannot be assigned directly in the asset, but must be assigned directly in statutory reporting.

You can edit additional classifications using the applications Assign Additional Classification (Securities) and Assign Additional Classification (No Securities).

###### Output and Saving of Lists

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Output and Saving of Lists | L7 | trm10 p.195 | loio `ae7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ae7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Purpose**

For data that is subject to reporting obligations, for example, data for premium reserve fund lists, statements, assets, and hedge fund reports, the following functions for outputting lists and saving list are available:

Generating and displaying data online or in background processing

Revising data

Saving data

Exporting data

From the data displayed, you can also create forms that comply with legal regulations.

**Integration**

You have transferred the necessary data for list generation to statutory reporting (see Flows in Statutory Reporting (SR Ledger).

**Features**

You can call up the lists from the tree structure of the ALV grid or using a selection screen.

The List Output - Statutory Reporting view contains various functions that you can use. For more information, see Functions in Toolbar and Context Menu.

For individual line items, you can drill down to the corresponding individual values (by double-clicking the value), adjust the view, and save it as a layout (see Drill-Down (Detailed Display).

By choosing Tips and Tricks for List, you can display useful information specifically for the list displayed.


You can save lists and call up saved lists from the tree structure (see Saving List Content and Accessing Lists from the Tree Structure).

**Restrictions**

Corrections that you make in the list are not posted to the system. However, you can save the changes as a list.

When generating lists from the selection screen (ISSR_OUT_ALVTREE_B), the list can be saved in background processing only.

See also

SAP List Viewer

Input-Enabledness in SAP List Viewer

###### Importing Data from Excel Files

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Output and Saving of Lists > Importing Data from Excel Files | L8 | trm10 p.196 | loio `397acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/397acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

You can import external data from an Excel file and save it to SAP database tables.

You can then add this data to the list output of the following statements:

NW101

NW600

NW605

- NW670
- NW671


NW673

You can add the external data at row level to either supplement or substitute existing data. You control this in the Excel file (see 'Prerequisites' below).

**Prerequisites**

You have created the Excel files with the external data.

SAP ships a list-specific Excel template for each of the aforementioned statements. The exact structure that the list output will later have is predefined in these templates. For this reason, you must use these templates as a basis for your Excel files. This is the only way to ensure that the system imports the data into the database, correctly stores it, and later correctly adds it to the lists.

All of the templates are attached to SAP Note 1167515. Download the relevant template and enter the required data into the respective Excel file.

When using Excel files, note the following:

Only the green fields in the template are relevant for entry. Enter corresponding values in these fields only.

Make your entries in the Excel files always at the row level that is identified in the Excel file by the relevant row ID and that matches the official row ID of the BaFin form.

The columns of the Excel file also match the columns in the relevant BaFin form.

In the Excel file, specify for each row whether the system is to later add the external data (additive) or use it to substitute existing data in the list output (substitutive). You do this in the Excel file by specifying the corresponding value in the Operation column: add (for additive) or sub (for substitutive).

You can enter external data at row ID level only for base rows and of-which indicators. You cannot override totals rows. The system generates these at runtime.

In the statements, totals are formed in accordance with the legal requirements. Data from the Excel files is handled in the same way as data from the SAP system. In particular, data that you have not entered in the designated fields in the Excel file is not added to the statement.

If the list layout changes due to legal requirements, SAP will adjust these templates automatically during maintenance.

Example for statement NW670 (header data)

If you generate a list for statement NW670, the following fields are available on the selection screen:

Company code

Valuation area

Quarter

Start of period

End of period

Output

In the Excel file, you need to enter the following data for this header data:

Company code

Valuation area

Key date

This key date corresponds to the value in the End of Period field.

The Quarter, Start of Period, and Output fields are not relevant for importing external data. For this reason, they are not listed in the Excel file.

**Importing External Data**

In the statutory reporting menu, choose Statutory Reporting Flows -> Import External Data from Excel File for List Output.

Use the input help to choose the required Excel file.

Choose (Execute).

The system saves the external data from the Excel file persistently for the specific key date to the database table.

You can then add the data to the list output for one of the abovementioned statements.

**Adding Data to the List Output**

In the statutory reporting menu, choose List Output -> Tree Structure.

Access the list output for the respective statement by double-clicking.

The system displays the selection screen for the respective statement.

Enter the required data in the input fields.

The system checks whether the data entered in the relevant fields matches the entries in one of the Excel files stored in the database (in our example for statement NW671, the relevant fields are Company Code, Valuation Area, End of Period/Key Date).

If the system finds matches, you can add the external data to the list output (see step 4).

If the system does not find any matches, you cannot add any external data to the list output (step 4 is not possible).

If you can add external data to the list output, you can choose one of the following options:

Read Related External Data

The system then adds all of the external data that you have stored for the relevant statement in the database (see 'Importing External Data') to supplement the list output data that already exists in the system.

Display External Data Only

The system then displays in the list output only the external data that you have stored for the relevant statement in the database. Existing list output data is ignored.


You can only choose one of the two options. If you select both indicators, the system issues a corresponding error message.

###### Accessing Lists from the Tree Structure

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Output and Saving of Lists > Accessing Lists from the Tree Structure | L8 | trm10 p.198 | loio `127acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/127acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

The function for generating lists from the tree structure offers you an overview of all lists that can be generated in the system and enables you to view different lists side by side in a view.

This makes it easier for you to compare and correct data from master data or positions.

**Features**

You can regenerate lists, save them if necessary, or display lists that have already been saved.

The selection screen for individual lists also contains functions for checking, saving, and loading selections.

For more information about saving lists, see Saving of List Content.

**Activities**

To call up the function, choose List Output Tree Structure in the statutory reporting menu.

You can regenerate lists and then edit them in the ALV Grid view or call up (and edit) lists already saved.

Generating a New List

- 1. In the navigation bar, choose the list you require by double-clicking.
- 2. Make the required entries on the selection screen.
- 3. Choose Execute.


The system displays the list for the selected selection criteria. If no data exists, an empty list is displayed.

**Note:**

If lists can be saved for the selected list type, you can also choose Save List.


Accessing Saved Lists

For list types that can be saved, you will find the node Saved Lists.... in the navigation bar.


To access a saved list, proceed as follows:

- 1. In the navigation bar, choose Saved Lists ... for the list type you require.


If no saved lists exist for a list type (or list saving is currently deactivated in Customizing for this list type), the system displays a message.

- 2. In the Saved Lists dialog box, select the lists that you want to access.

You can only call up one list at a time.

- 3. Choose Display List in Upper Window or Display List in Lower Window.


**Note:**

If you want to display a list that you have just saved, this list may not yet exist in the database and is therefore not available for selection. In this case, choose Refresh Display until the list is displayed.




The system displays the saved lists in the desired screen area. You can now also make changes, and if necessary, save the new list content.

**Note:**

When you display saved lists, a detailed display is not possible.

###### Accessing Lists from the Selection Screen

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Output and Saving of Lists > Accessing Lists from the Selection Screen | L8 | trm10 p.199 | loio `4e7acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e7acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

Using report ISSR_OUT_ALVTREE_BATCH (which can be run in the background), you can generate lists for Statutory Reporting for the Insurance Supervisory Authority in the background as well as online.

For the output formats AG (ALV display) and SF (form), you can also save the generated lists to the database during background processing.

**Note:**

You can generate lists only for one company code in a report run.

**Prerequisites**

Prerequisites for Saving Lists

The generated lists are saved to the database if the following criteria are met:

You are running the report in the background.

You have selected the output format AG or SF.

The generated list is not empty.

Customizing Prerequisites for Saving Lists

The selected list type is identified as a list that can be saved in Customizing.

The maximum number of lists that can be saved for each company code/SR variant for the list type currently being processed has not yet been reached.

You can find the relevant Customizing settings in the Implementation Guide for Statutory Reporting under VariantDependent Settings List Output Define List Output , Settings for ALV node).

The selected company codes are assigned to the specified statutory reporting variant.

For more information, see Saving of List Content.

**Features**

The report generates lists based on the specified selection criteria and selected output format. During background processing, the system saves each list in a separate spool request.

If you are using the function for list saving, the system saves the lists to the database at the same time. You can then display and edit these lists in the ALV Grid view (Accessing Lists from the Tree Structure).

Special Functions

When the lists are generated in online, as opposed to output via the tree structure, they can only be displayed individually. However, you can use the following additional functions:

Download to Internal Data Transfer Format (output form DD)

With this output form, the generated lists in data transfer format are generated as a text file. You can generate them either as a local file (local download) or on the configured server (transfer).

**Caution:**

The local download option is not available for background processing. Additional system settings are required for the transfer option.

If you want to generate statements and enter a quarter that is not equal to 0, the system transfers the corresponding entries to the Start of Period and End of Period fields.

**Activities**

Selection

When you enter the SR variant and press Enter, the selection screen is displayed according to the Customizing settings defined for this variant.

To create data transfer lists, enter the value DD in the Output field and press Enter.

You can choose the type of file output in the Transfer/Download screen area.

For statements for a specific quarter, you can enter the corresponding value in the Quarter field.

The system then transfers the relevant entries to the Start of Period and End of Period fields. These fields are then locked against manual entries.

Note: To unlock these entries, enter the value 0 in the Quarter field.

Settings for Saving Lists

You can save lists only with background processing. You must also choose the output format AG or SF

To save the lists in the database, choose Save List in the Result area and enter a description.

**Note:**

The system then assigns the entered description to all of the lists generated at runtime. In other words, the list description is identical for all of the lists generated in one program run. Background processing cannot be started if you have selected Save List but have not entered a description.

Output for Saving Lists

If you have selected Save List and entered a description for the lists to be generated, the system also saves the lists to the database. You can display and edit or delete individual lists using the tree structure in the ALV Grid view (see Accessing Lists from the Tree Structure and Deleting Saved Lists).

The system only saves lists that contain data. If a generated list is empty, it is not saved to the database.

**Note:**

If the system cannot save one of the generated lists to the database during background processing (for example, because one of the prerequisites is not met), it includes a corresponding entry in the job log. This list is then available only in the spool output. Background processing continues as normal.

###### Saving List Content

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Output and Saving of Lists > Saving List Content | L8 | trm10 p.201 | loio `067acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/067acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

If you have created lists from the tree structure (see Accessing Lists from Tree Structure) or by using a report with background processing (see Accessing Lists from Selection Screen), you can save these lists with the current content and settings.

You have the option to compare lists with different output times and settings, and if necessary, to better track changes.

**Caution:**

When you save, the selection criteria chosen are also saved. For this reason, when you compare saved lists with each other, take into account that a different set of chosen selection criteria can affect the list content. We recommend including a reference to the chosen criteria in the list name.

**Integration**

When saving, the system stores the lists in the database, where you can access and edit these lists from the tree structure. In the navigation bar, the system then displays the Saved Lists node for the respective list type.


This node in the navigation bar is visible only if the relevant list type for list saving is activated (see Prerequisites section). If the list type is no longer visible, but saved lists still exist for this list type, you can no longer access these lists.

The node is also displayed if there are no saved lists. It is displayed for a parent node as soon as list saving is allowed for a list type under this node.

**Prerequisites**

Before lists of a list type can be saved, the following settings must have been made for the relevant list type in the Implementation Guide for Statutory Reporting ( Variant-Dependent Settings List Output , under Settings for ALV):

The relevant list type is defined as a list (List indicator) and flagged as a visible list (Saving Allowed indicator).

The maximum number of lists that may be defined for each company code (Number of Visible Lists field) has been defined for the list type.

If the number of visible lists specified here for a list type and company code has been reached, the system displays a message when users try to save another list.

**Features**

For a list type, you can save as many lists for each company code as defined by the maximum number in Customizing.

The system stores these lists with the chosen selection criteria in the database.

**Note:**

You can also re-save lists that have already been saved (without changes). The system then displays a corresponding message and you can save the list under a different name.

Saving Lists Generated by a Batch Report

If you generate lists by calling them up via selection screen (ISSR_OUT_ALV_B), you can save multiple lists at the same time for the output formats AG (ALV display) and SF (form output).

**Note:**

This function is available only for background processing and for the aforementioned output formats. The name is then identical for all lists saved in this program run.

For more information, see Accessing Lists from the Selection Screen.

Saving Lists Generated from Tree Structure

If you access a list from the tree structure (ISSR_OUT_ALVTREE), you can save this list directly from the ALV display.

**Activities**

Saving Lists Accessed from Tree Structure

- 1. Access the desired list from the tree structure (in the menu under List Output Tree Structure ).
- 2. On the list screen, choose Save List.


- 3. Enter a List Name.


Use descriptive list names, for example, that include a reference to the selection criteria.

The system stores the list with the chosen selection criteria in the database. Once the system has saved the list, you can select it in the tree structure using the corresponding Saved Lists node for the node area.

**Note:**

It can take a while to save a list because this action is performed in the background.

###### Deleting Saved Lists

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Output and Saving of Lists > Deleting Saved Lists | L8 | trm10 p.203 | loio `a57acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a57acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

You can delete one or more saved lists from the database.

When you save lists, the maximum number of visible lists for a company code is limited. How many lists can be saved for each list type and company code is defined in the Customizing settings for the list type. (In the Implementation Guide for Statutory Reporting under Variant-Dependent Settings List Output Define List Output) . If the number defined there has been reached, you need to delete existing lists of this list type in order to save lists again.

**Prerequisites**

You are authorized to delete saved lists.

The authorization is controlled using authorization object F_ISSR_LTD and is assigned at company code, SR variant, SR valuation area, and list type level. Without this authorization, you cannot delete lists, even those you created yourself.

The Customizing prerequisites allow you to save list content for the list type (in Customizing under Variant-Dependent Settings List Output Define List Output ).

To delete lists, you need to be able to call up the saved lists.

**Procedure**

Call up the list output from the tree structure under List Output Tree Structure .

In the navigation bar, choose Saved Lists ... for the list type you require.


- 1. In the Saved Lists dialog box, select the lists that you want to delete.
- 2. Choose Delete Lists.


**Result**

You have deleted the relevant lists from the database.

**Caution:**

It can take a while to delete a list because this action is performed in the background. If the system still displays the list in the Saved Lists dialog box after the deletion, choose Refresh Display.

###### Drill-Down (Detailed Display)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Output and Saving of Lists > Drill-Down (Detailed Display) | L8 | trm10 p.204 | loio `727acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/727acb53f0f67314e10000000a174cb4.html?locale=en-US)

**Use**

For individual lists, you have the option in the ALV display to drill down to the individual values (position or flow data) of the relevant item. These lists are referred to as drill-down lists.

**Prerequisites**

The drill-down function is available for the selected list.

**Features**

To call up the detailed display with drill drown, double-click the required position in a line.

If necessary, you can select whether you want the system to read the presummarized data from the program table or the individual flows of the ledger (ISSRFLDEA).

Saving a Display Variant (Layout) for Drill-Down

The display variants are saved for assets, statements, and samples based on the list type. For premium reserve fund lists, you can save the layout at list level (not at subsection level).

If you want to save the current display as a display variant by choosing Save Layout, you can combine the User-Specific and Default Setting indicators as follows:

|Indicator: User-Specific|Indicator: Default Setting|Effect|
|---|---|---|
|X| |The layout can be selected by you yourself only. It is not called up as the standard layout when you drill down.|
| |X|The layout is used as the standard layout, regardless of the calling user. This means that the system displays the drill-down display for the relevant lists always with this layout if a user-specific layout does not exist.|
|X|X|The layout is saved as a user-specific standard layout for you, which means that the drill-down display for the relevant lists is always displayed for you with this layout.|


For more information, see

Layouts

###### Log Management

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > Log Management | L7 | trm10 p.205 | loio `667acb53f0f67314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/667acb53f0f67314e10000000a174cb4.html?locale=en-US)

Use

Every function or application (for example, import of feeder system data) creates an application log that can be used to control internal system processes.

You can display the statutory reporting logs by choosing Log Management Display (transaction SLG1) with object ISSR. In a similar way, you delete logs by choosing Log Management Delete (transaction SLG2) with object ISSR.

For data import functions outside of Customizing, you also have the option to create more detailed logs in the system by using the Detailed Log indicator.

###### German Banking Act

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > German Banking Act | L7 | trm10 p.205 | loio `e3fac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e3fac5536a51204be10000000a174cb4.html?locale=en-US)

###### Multi-Million Loan Reports (DE)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > German Banking Act > Multi-Million Loan Reports (DE) | L8 | trm10 p.205 | loio `4deea04cab447323e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4deea04cab447323e10000000a42189e.html?locale=en-US)

Use

The multi-million loan report is a reference list that is used, in accordance with paragraph 14 of the German Banking Act (GBA), to display multi-million loans across the securities and loans areas. The report is a reference list because it does not meet the requirements of the sixth amendment to the GBA.

You can store collective reports in accordance with paragraph 14 of the GBA in XML format on your local hard disk so that you can then upload them to the ExtraNet of the Deutsche Bundesbank.

The data is prepared in accordance with the regulations of the German Federal Financial Supervisory Authority (BaFin). The required logon and identification data can be obtained from the BaFin.

The following conditions need to be met before the collective reporting function can be used:

You do not have any derivatives or real estate loans to report.

You have entered all of your positions in the SAP system.

Each business partner can only belong to one higher-level unit, but multiple business partners can be assigned beneath one unit.

When you make a collective report, you can no longer make single reports.

**Prerequisites**

If you want to use this function, you need to make certain presettings.

- 1. In the partner master data in the Financial Reporting Data screen, the GBA Report field must be activated and the number of the borrower or borrower unit must be entered for the partners that can appear in the role categories Issuer (securities area) or Main Borrower (loans area).


- 2. Furthermore, the Industry field needs to be filled for the business partner. You enter data for the business partner classification Organization by choosing Goto Central Data Legal Data and for the business partner classification Natural Person by choosing Goto Central Data Employment Data . The industry is displayed under Industrial Sector in the multimillion credit report.
- 3. In the securities area, the GBA indicator under Securities Master Data Position Indicator must be set.
- 4. In the loans area, the BCA indicator is defined in the Basic Data II screen.

The loans are grouped by the GBA indicator in accordance with paragraph 14 of the GBA.

- 5. If you want to use the XML output function, you need to make the following settings:


**Note:**

The borrower entity is portrayed using the business partner relationship parent/subsidiary corporate group. A borrower entity comprises several borrowers, where one borrower is a parent company and all other borrowers are subsidiaries. To maintain the subsidiary companies, choose Goto Central Data Relationships and enter a relationship type with relationship category 0050 (subsidiary company) for the parent company.

If a borrower is independent, that is, the borrower is not part of a borrower entity, you enter the borrower number in the multi-million loans report. If a borrower belongs to a borrower entity, you enter the borrower entity number in the multimillion loans report. The loans for individual borrowers are added together.

|GBA Indicator|Para. 14 GBA Grouping|
|---|---|
|20|Loans acc. to Paragraph 19 I Clause 2, NOT Column 7, 8, 9|
|27|Loans acc. to Paragraph 19 I Clause 2, real-estate loans acc. to Paragraph 14 GBA II|
|28|Loans acc. to Paragraph 19 I Clause 2, public loans acc. to Paragraph 14 GBA II|
|29|Loans acc. to Paragraph 19 I Clause 2, interbank loans acc. to Paragraph 14 GBA II|
|30|Off-Balance Sheet Transactions, NOT columns 4,5,6|
|34|Außerbil. Geschafte, Finanzswaps etc. i.S. von §14 KWG I, S.1|
|35|Außerbil. Geschafte, Gewahrl. Swap etc. i.S. von §14 KWG I, S.1|
|36|Außerbil. Geschafte, Burgschaften etc. i.S. von §14 KWG I, S.1|


In Customizing for the Transaction Manager under General Settings Organization Define Company Code Additional Data , you have to fill the following fields for each company code:

In the Credit Guarantor Number field, enter the 7-character credit guarantor number received from the BaFin.

In the "XML Character" field, enter the abbreviation for the file name that you have received from BaFin.

Select the GBA § 14 Sender field if you want the company code to appear as the sender in the reports (in the Reporting Company field).

**Note:**

Since the data for the relevant processor (name, telephone number, and e-mail address) needs to be entered, we recommend that the relevant processor saves this data as parameters in their user profile. In this way, the data is

entered in the reports automatically so that it no longer needs to be entered manually.

- a. Choose System User Defaults Own Data (transaction SU3).
- b. On the Parameters tab page, enter data for the following parameters:
- c. Save your entries.


|Parameter|Description|
|---|---|
|FTVV_KWG14_EXP_NAME|Name of Processor|
|FTVV_KWG14_EXP_PHONE|Telephone Number of the Processor|
|FTVV_KWG14_EXP_MAIL|E-Mail Address of the Processor|


In the report, the evaluation data for the borrower, including ratings, and the approach used to determine the probability of default. If the relevant data is not entered, the system informs you about this when you create the XML file. Note that the XML report without this evaluation data is not BaFin-compatible and consequently cannot be processed by BaFin. You enter the evaluation data for each business partner in the application menu under Treasury and Risk Management Transaction Manager Information System Reports Regulatory Reporting

Germany: Regulatory Reporting German Banking Act (GBA) Maintain Debtor Ratings (transaction FNKWGRAT).

**Activities**

To call up the function, proceed as follows:

- 1. Choose Treasury and Risk Management Transaction Manager Information System Reports Regulatory Reporting Germany: Regulatory Reporting German Banking Act (GBA) Multimillion Loan Display (§14 GBA) .

The Reference List GBA Para. 14 Securities and Loans selection screen appears in which you can enter data to restrict the program selection.

- 2. Enter the selection criteria and the reporting period, and choose the currency.
- 3. In the Reporting Procedure screen area, you can choose between Show Reporting Data and XML Output.
- 4. Set the Test Reporting indicator if appropriate or if instructed to do so by BaFin.
- 5. Enter the name of the reporting company in the Reporting Company field.
- 6. If you have opted for XML output, additional fields appear, allowing you to enter the data of the relevant processor (name, telephone number, and e-mail address).
- 7. Execute the function.


If you have selected the reporting procedure Show Reporting Data, the Reference List GBA Para. 14 Securities and Loans screen appears, which displays the total debt per borrower entity or borrower, and a summary of the total debt according to the GBA indicators that you have maintained. The columns are currently filled as follows, whereby the column numbering is the same as the print preview according to §14 para. 1 GBA.

Reference List Entries

|GBA Indicator|Reference List Column|
|---|---|
|20+27+28+29+30+34+35+36|1|
|20+27+28+29|2|
|30+34+35+36|3|
|34|4|
|35|5|
|36|6|
|27|7|
|28|8|
|29|9|


By selecting a line, you can display the single positions for a position in accordance with § 14 GBA.

If you have selected the reporting procedure XML Output:

- a. A dialog box appears.
- b. Choose the file path on the local hard disk where you would like to store the XML file.
- c. The proposed file name corresponds to the BaFin guidelines. If you want to submit the report in ExtraNet, do not change the file name.
- d. Save your entries. The file is then stored on your hard disk.

###### Loans to Managers (German Banking Law)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Regulatory Reporting > Germany > German Banking Act > Loans to Managers (German Banking Law) | L8 | trm10 p.208 | loio `928edf53e957444de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/928edf53e957444de10000000a174cb4.html?locale=en-US)

Use

This function is designed to meet German reporting requirements and is not relevant for other countries/regions.

###### Master Data (3 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Master Data | L5 | trm01 p.116 | loio `4bfac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4bfac5536a51204be10000000a174cb4.html?locale=en-US)

Master data is basic data that is seldomly changed. You can enter the following master data in Treasury and Risk Management:

General master data in Treasury and Risk Management:

Manage Trader Authorizations

SAP Business Partner

Defining Banks, House Banks, Bank Accounts, House Bank Accounts

Treasury Accounting / Treasury Positions

Position Indicator

Position Management Procedure

Account Assignment References

Money market transactions

Facilities

Security transactions

Manage Securities Classes

Redemption Schedules

Securities Account

Listed derivatives

Manage Securities Classes

Futures Account

###### Changes to Business Partners

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Master Data > Changes to Business Partners | L6 | trm10 p.208 | loio `c246ab531a1b2742e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c246ab531a1b2742e10000000a174cb4.html?locale=en-US)

**Use**

This report calls up the change documents for your business partner master data.

**Features**

Selection

You can select data by business partner and/or according to the data changed (date, user).

Output

From the list of change documents you can see when a change was made, who made it, and exactly what was changed (the old and new value is displayed for each field changed).

###### Class Information for Securities

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Master Data > Class Information for Securities | L6 | trm10 p.209 | loio `4efac5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4efac5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

You use this report to display class data for securities. To do this, choose SAP Easy Access Class Information (transaction FWDG).

**Features**

|Selection Range|Selection Options|
|---|---|
|General Selections|ID Number Product Type|
|Output|Cash Flow indicator If you set this indicator, the system displays the cash flow that can be generated from the master data of a bond. User Data indicator If you set this indicator, the system also displays user data.|


To print the master data, choose List Print .

###### Securities Account List (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Information System > Reports > Master Data > Securities Account List | L6 | trm04 p.236 | loio `271222992e2449468d5cd331175892ca` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/271222992e2449468d5cd331175892ca.html?locale=en-US)

**Use**

You can use the securities account list to display master data and payment information for one, several or all securities accounts in a company code. You can also print this information.

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

**Activities**

- 1. Choose either Information System Master Data Securities Account Securities Account List or Securities Master Data Securities Account Securities Account List.
- 2. Enter the Company code .
- 3. By making entries in the fields below, you can select the securities accounts you want to see.

- a. Securities Account
- b. Securities Account Type
- c. Securities Account Category
- d. Portfolio
- e. Depository Bank
- f. Beneficiary


If you do not enter any other selection criteria, the system displays all the securities accounts in the company code.

- 4. Choose Execute.
- 5. The securities account list is generated according to the selections made.

