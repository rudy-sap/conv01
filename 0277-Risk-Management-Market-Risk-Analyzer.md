# Risk Management > Market Risk Analyzer - SAP TRM Knowledge Base (branch split)

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

#### Market Risk Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer | L3 | trm03 p.2 | loio `8505c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8505c753b1081d4be10000000a174cb4.html?locale=en-US)

The Market Risk Analyzer offers corporations and insurance companies a range of functions for managing risks on a global basis. Of all the different external risks to which companies operating internationally are exposed, it is changes in market prices that are the most critical factors for company success. They can have a profound effect on the amount, present value, or timing of payment flows. Operative business and treasury transactions alike are affected by market risks. To measure and manage risks fully, it’s essential to bring together all risk-related company activities.

**Purpose**

In recent years, no other area has come close to developing such an extensive toolset for measuring risk as market risk management. Since it’s comparatively easy to obtain up-to-date market data and historical market data, it’s possible to quantify risk volume accurately. This data provides an ideal basis for risk management.

The methods used in modern risk management systems enable companies to perform detailed analysis of their positions with regard to all the factors that affect prices. What is more, the decision-support aspect of risk management is gaining importance to ensure the successful implementation of company strategies. Simulating future portfolio structures and incorporating potential market trends into the analyses is becoming a key part of preventative financial management.

At the same time, risk management is no longer merely an instrument of control after the event, but one capable of adding value to a company. The development of new financial instruments and improvements in investor relations and the company's reputation on the capital market are just some of the benefits of proven risk reduction. The company organization is also feeling the effects of this change since risk controlling now reports directly to the board.

In addition, companies have to consider a growing number of legal regulations that require risk management systems to be established within the enterprise. Some of these regulations apply only to specific industries, while others apply to all industries. The legislators have protected the interests of the investors by acknowledging the vast increase in the scope of risk that has gone hand in hand with market globalization.

The Market Risk Analyzer caters for the requirements of all industry sectors. It reflects the requirements of the methods used in the financial services sector to measure risk, and makes it possible to include the payment flows from companies’ business activities in risk analysis. You can use company-specific portfolio hierarchies to analyze risks according to the factors that give rise to these risks (exchange rates, interest rates, prices, volatilities). The Market Risk Analyzer contains analyses that look at data at a given point in time, such as mark-to-market valuations, as well as dynamic evaluations, such as position trend analysis or profit and loss simulations. It also contains functions for identifying open risk positions that affect your interest rate or currency exposure, alongside classic risk control instruments, such as value-at-risk methods.

In the integrated environment, you have all the information you need for risk management. To evaluate alternative hedging strategies, you can enter simulated transactions and market data scenarios and see the combined effect of the simulated data and your real transactions. In this way, the Market Risk Analyzer fully supports your trading activities.

[figure TRM03-F001 - Market Risk Analyzer - Concept]

Market Risk Analyzer - Concept

Data Collection

For informed risk management, it’s essential to capture all risk-related activities. Market risks influence all the payment flows in a company irrespective of where they originate. The integrated system environment ensures that once all the necessary information has been entered, it can be accessed automatically. This is equally true for operative activities within the logistical chain and for transactions that have been entered in the Transaction Manager. The SAP system can minimize the number of interfaces that have to be defined and maintained between different systems. This is usually a major cost consideration when implementing risk management systems.

The link between the Market Risk Analyzer and datafeed also provides access to current market data that can be used to analyze risk positions. The imported data is stored centrally and is available across the entire system, thereby ensuring that all evaluations are based on consistent data.

Mark-to-Market Valuation and Position Analysis

The main task of risk management is to identify potential losses on the basis of current market data. The Market Risk Analyzer

provides you with a comprehensive system for calculating the net present value of common financial instruments. The calculated values (net present values or clean prices) can be stored and used later for accounting purposes by the valuation functions in the Transaction Manager. The calculation steps performed are recorded clearly and comprehensibly in a log together with the market

data upon which they were based. In addition, extensive documentation on the financial mathematical models used is available.

To handle the risk profiles of complex financial instruments, a data model has been developed using the concept of a generic transaction and an internal risk object. By linking multiple elementary components, it can map flexible transaction structures. The system offers you an architecture that can adapt to future demands. It integrates risks in the valuation methods of the Market Risk Analyzer, independently of the underlying business processes.

Sensitivity Analysis and Simulations

Net present values are used to measure the sensitivity of portfolios to changes in market data and to highlight potential changes. You can map classic sensitivity key figures, such as basis point values, durations, convexities, and the Greeks in the Market Risk Analyzer as well as differentiated simulation scenarios. These scenarios contain any combination of market data values and can be

integrated into all Market Risk Analyzer evaluations. You can even map in the system a series of scenarios in chronological order as scenario progressions. Using different simulation procedures, you can reflect market fluctuations in your current market data dynamically, or keep the data constant and use it in extreme value scenarios (stress tests) over any time periods.

Besides the changes in market data, the changes in the structure of your portfolio also play a vital role in new business planning. For this aspect, the Market Risk Analyzer provides a series of evaluations, based on individual or standardized planning requirements, that enable you to generate simulated transactions and analyze their impact on the liquidity of your company, the business structure, and the profit and loss.

Currency Exposure

For many companies that are actively involved in global markets, analyzing and hedging foreign currency risks is an essential element of market risk management. To capitalize on economies of scale and set up hedging activities for aggregated foreign currency payments across the group, central treasury departments frequently turn currency management to their advantage. This restricts local activities to transactions that are required for processing incoming or outgoing payments or to those that observe the statutory regulations. This type of structure places high demands on the system landscape to include all the relevant liquidity flows in the foreign currency planning. SAP Cash and Liquidity Management undertakes the necessary preparatory tasks for this; it prepares a formatted data basis by bringing together local payment activities in a distributed system landscape. The Market Risk Analyzer can access this information directly, without needing its own interface. The financial transactions entered in the Transaction Manager are then compared with the operative payments. For flexible maturity bands, the currency exposure then calculates the remaining open items for each currency, which can be used for further hedging activities.

Liquidity Analysis

Ensuring liquidity is a fundamental condition for revenue-oriented and risk-oriented enterprise management. In this area too, companies today require a system that does much more than simply combine actual payment information. Only when your liquidity planning is integrated and market data changes are simulated do you have a solid base of information for analyzing your liquidity. By incorporating scenarios or scenario progressions, the Market Risk Analyzer allows you to analyze the impact of market fluctuations on the liquidity of your company (for example, the amount of variable or optional cash flows), and use simulated financial transactions to smooth out identified liquidity surpluses or deficits.

Value at Risk

Value-at-risk analysis is an extension of net present value analysis and uses a standard measure for risk. It uses historical or simulated market data to calculate the value loss of a position that, based on a certain probability, within a certain period, could be incurred before the position is hedged or sold.

Due to its uniform net present value approach, value-at-risk analysis has taken off as a risk-controlling instrument. The increased popularity of this procedure has been helped to a large extent by the vast improvement in the availability of (historical) market data in recent years. The Market Risk Analyzer supports the models that are currently commonly used on the market.

[figure TRM03-F002 - Value-at-risk method in the Market Risk Analyzer]

Value-at-risk method in the Market Risk Analyzer

It’s also possible to use a combination of methods depending on the instrument that is to be priced. You can import external data for the calculations or use the market data stored in the SAP tables. A statistics calculator enables you to estimate volatilities and correlations for the variance/covariance approach.

You can structure the risk factors you want to use to calculate and display value at risk in risk hierarchies that you can configure yourself. You can also use risk hierarchies to determine the aggregation procedures and levels.

Flexible portfolio hierarchies

To counteract risks efficiently, it’s necessary to clearly quantify the risk contribution of individual risk factors (such as interest, currencies), risk objects (such as financial transactions), or organization entities (for example, profit centers). It must therefore be possible for you to perform risk analyses according to the most varied criteria and at different aggregation levels. If, for example, you want to have a value-at-risk key figure as summarized information at company-wide level, you still have to specify the risk amounts in detail for each of the relevant underlying factors to comply with hedge accounting requirements.

The Market Risk Analyzer utilizes flexibly definable portfolio hierarchies, which are used not only to determine the characteristics by which risks are separated, but also to specify the hierarchy levels at which the individual risks are aggregated. The portfolio structure is based on the characteristics of risk objects (financial transactions, operative cash flows) that are stored in the system. Each of these characteristics (for example, trader, transaction currency, type of financial instrument, exchange) can be used to create the portfolio hierarchy. If some of the characteristics are assigned to a portfolio hierarchy node, all objects that have these characteristics are automatically displayed under the corresponding node. Since it is possible to create any number of portfolio hierarchies, the different aspects of risk reporting (organizational and instrument-specific) are covered at all times.

The sheer flexibility in evaluation control and the highly sophisticated tools deployed combine to make the Market Risk Analyzer an efficient instrument for controlling risk for companies across all sectors of industry. In addition, the Market Risk Analyzer can access all information related to risks that is available in the system without needing a special interface to do so. When you map operative activities using Cash Management or enter financial transactions in the Transaction Manager, you have all the real-time data you need for the Market Risk Analyzer reports. What is more, there’s no need to enter anything twice.

You can find the functions of the Market Risk Analyzer under Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer .

**Implementation Considerations**

To use the Market Risk Analyzer component, you need to make the necessary Customizing settings under Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings and Market Risk Analyzer.

##### NPV Analysis

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis | L4 | trm03 p.6 | loio `6b11da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6b11da531198434de10000000a174cb4.html?locale=en-US)

**Use**

To get an objective impression of the financial and risk situation of a company, you have to be able to view all financial assets and liabilities in terms of their current market value. The Market Risk Analyzer offers apps and functions with which you can calculate the mark-to-market values.

You can calculate the following kinds of market risk key figure:

Net present values

Sensitivity key figures

Value at risk and mean excess loss

Cash flow at risk

**Apps and Functions for Online Calculation**

Analyze NPV - Online

Using this app, you have the following options for analyzing the NPV:

Evaluation today based on current market data or scenario data

With NPV analysis today, all future cash flows are discounted to the current point in time using current market or scenario data.

Evaluation in the future on the basis of forward data that is generated from current market data

With NPV analysis for a future date, all cash flows arising after the future date are discounted back to it, using the forward data for the future data, which is projected from the current market data.

Evaluation in the future (= horizon is a future date) based on scenario data and/or market data shifts

With NPV analysis for a future date using scenario data, all cash flows arising after the future date are discounted to this future date using the scenario data.

**Note:**

You can value financial instruments with the bid/ask spreads quoted on the market. This procedure ensures that all transaction costs arising are considered. Transactions that are traded in different markets, such as German federal bonds or mortgage bonds, are valued in Risk Management using different market-specific yield curves. Likewise, the premiums for standard options and for exotic options are calculated on the basis of different volatility curves.

Multiple NPV calculations for different market parameter combinations and depiction in the form of a valuation grid

For more information, see also Analyze NPV

Sensitivity Key Figures - Online

Depiction of the sensitivity for options when individual market parameters are changed

For more information, see also Sensitivity Key Figures.

Sensitivity Analysis (transaction JBRJ)

For more information, see also Sensitivity Analysis

Grid Analysis (transaction JBRI)

For more information, see also Grid Analysis

Value at Risk - Individual Analysis (transaction RMV0)

For more information, see also Value at Risk - Individual Analysis

Cash Flow at Risk - Single Value Analysis (transaction RMC0)

For more information, see also CFaR Single Value Analysis

Calculate Market Risk Key Figure - Online

You use this app to calculate and display online, for a selection of transactions, key figures for NPV analysis and sensitivity key figures. Further, you can use calculated key figures as the basis for defining formula-based key figures, and then display them with the NPV key figures and sensitivity key figures. By specifying the evaluation date and horizon date, you define for which date the transactions and market data are selected.

You use the key figure analysis to calculate certain key figures online for a small portfolio of transactions. The advantage of the key figure analysis is that you can display NPV key figures and sensitivity key figures together and relate them to formula-based key figures.

The results aren’t stored in database tables.

For more information, see also Calculate Market Risk Key Figures.

**Analyzer Information System Based on Results Database**

You use this function to display the results data that you have previously stored in the Results Database. You can use the Analyzer Information System to report the following key figures in a consistent way:

Market risk key figures that you have calculated in the single records and final results procedures (such as the NPV, sensitivity key figures, and the value at risk)

Formula-based key figures

The system displays the results data and the portfolio hierarchy. You can use the portfolio hierarchy to navigate to the key figures for each portfolio hierarchy node and in this way display the results data for various aggregation levels, right down to single records. In addition to the results data, you can display the risk hierarchy, the calculation bases, detailed information about the key figures, and the evaluation procedures used. For value-at-risk key figures, you can navigate to the results data using either the portfolio hierarchy or the risk hierarchy.

For more information, see also Analyzer Information System and Results Database

**Calculate Market Risk Key Figures Based on Market Risk Key Figure Sets**

**Tip:**

This process is available only for the static analysis structure. Whether or not you can use this function depends on your setting in the Customizing activity Activate Setting for Analysis Structures.

Process Overview

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM03-F003]

Please note that image maps are not interactive in PDF outputs.

Processing Steps

Define market risk key figure sets using the Manage Market Risk Key Figure Sets app.

Calculate basic values (NPVs, profits and losses, and delta positions of the single financial objects) needed for the calculation of the market risk key figures and store the results in database tables using the report Calculate Market Risk Key Figures. You can run the report as a background job on a regular basis. The calculation is based on market risk key figure sets. The delta positions are calculated using the central difference quotient.

For more information, see also Calculate Market Risk Key Figures

The final calculation of the market risk key figures is done by the CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery).

You can report the market risk key figures by consuming the CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery). Use the tool of your choice to consume the CDS query views. For more information, see also CDS Views for Treasury and Risk Management

Examples:

SAP Analysis for Microsoft Office

Design Studio

SAP Lumira

SAP Analytics Cloud

**Note:**

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the backend system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

For more information, see also Treasury Executive Dashboard Available in SAP Analytics Cloud.

The CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery) are consumed on the Market Risk tab of the example implementation Treasury Executive Dashboard in the SAP Analytics Cloud application, where you can see the calculated market risk key figures.

View Browser app on SAP Fiori Launchpad

- 1. Open the View Browser and select one of the queries from the list.
- 2. Choose the Show Content button. The Design Studio is called.
- 3. In the Prompts dialog box, fill the Display Currency, Exchange Rate Type, MR Key Figure Set, and Key Date fields. For the Treasury Value at Risk Query, you also must enter the confidence level.
- 4. Confirm your entries by choosing OK.
- 5. You get the results list, which displays the calculated market risk key figures.


**Note:**

You need to have the authorization for a view to launch a CDS view in the Design Studio.

**Note:**

Enter a market risk key figure set and the key date for which you already run the Calculate Market Risk Key Figures report.

In the back end, you can use the Query Monitor (transaction RSRT).

- 1. Open the Query Monitor and find the query using the input help for the Query field.
- 2. In the Query Display field, choose ABAP BICS value.
- 3. Execute the query.


- 4. In the Variables box, fill the Display Currency, Exchange Rate Type, MR Key Figure Set, and Key Date fields. For the Treasury Value at Risk Query, you must also enter the confidence level.
- 5. Confirm your entries by choosing OK.
- 6. You get the results list, which displays the calculated market risk key figures.
- 7. You can change the drilldown and the aggregation level by assigning or removing an analysis characteristic from the rows or columns. The query is executed to calculate the market risk key figures at the requested level of detail.


**Note:**

Enter a market risk key figure set and the key date for which you already run the Calculate Market Risk Key Figures report.

**Market Risk Key Figures in Treasury and Risk Management - Overview Table**

There’s a range of market risk key figures that can be calculated and reported by different apps in Treasury and Risk Management. You can calculate the market risk key figures for financial transactions, financial positions, and exposure items. In the following table, you can see which market risk key figures are available and which apps you can use to calculate them.

| |Calculate Market Risk Key Figures App|Calculate Market Risk Key Figures Based on Market Risk Key Figure Set + CDS Query Views|Analyze NPV - App|Sensitivity Key Figures, Single Analysis App|VaR Individual Analysis (transaction RMV0)|CFaR Single Value Analysis (transaction RMC0)|Analyzer Information System (transaction AIS_STDREP)|Calculate Net Present Values With CVA and DVA App*|
|---|---|---|---|---|---|---|---|---|
|Market Risk Key Figure|Calculates the key figure, displays it online, but doesn’t store the value|Calculates the basic values according to the parameters of the market risk key figures set and stores the value in the database table. Final calculation done by CDS query views.|Calculates the key figure and displays it online, but doesn’t store the value|Calculates the key figure and displays it online, but doesn’t store the value|Calculates the key figure and displays it online, but doesn’t store the value|Calculates the key figure and displays it online, but doesn’t store the value|Displays the key figures that you have previously stored in the results database using Determine Single Records (transaction RAEP1) and Determine Final Results (transaction RAEP2). |Calculates the key figure and stores the value in the NPV table|
|Clean Price|x|x|x| | | | |x|
|Clean Price in Position Currency|x| | | | | | | |


|Greeks: Delta|x|x| | | | |x| |
|---|---|---|---|---|---|---|---|---|
|Greeks: Gamma|x| | | | | |x| |
|Greeks: Theta|x| | | | | |x| |
|Greeks: Vega|x| | | | | |x| |
|NPV**|x|x|x| | | |x|x|
|NPV incoming side / NPV outgoing side|x| | | | | | |x|
|Intrinsic Value|x| | | | | | |x|
|NPV in Position Currency|x| | | | | | | |
|NPV with negative Shift|x|x| | | | |x| |
|NPV with positive Shift|x|x| | | | |x| |
|Time Value|x| | | | | | |x|
|risk-free NPV|x|x| | | | | |x|
|CVA| | | | | | | |x|
|DVA| | | | | | | |x|
|Intrinsic Value with CVA/DVA (Options)| | | | | | | |x|
|Time Value with CVA/DVA (Options)| | | | | | | |x|
|Clean Price with CVA/DVA| | | | | | | |x|
|NPV with CVA/DVA**| | | | | | | |x|
|Basis Point Value|x|x| |x| | |x| |
|Convexity|x|x| |x| | |x| |
|Fisher-Weil Duration|x|x| |x| | |x| |
|Macaulay Duration|x|x| |x| | |x| |
|Modified Duration|x|x| |x| | |x| |
|Yield to Maturity|x|x| |x| | |x| |
|Value at Risk| |x| | | | |x| |
|Mean Excess Loss| |x| | | | |x| |


|Cash Flow at Risk by Variance/Covarince| | | | | |x|x| |
|---|---|---|---|---|---|---|---|---|
|Cash Flow at Risk from Simulation| | | | | |x|x| |
|Cash Flow in Original Currency| | | | | |x|x| |


- = Only for OTC transactions, such as money market transactions, FX transactions, or FX options

- *=NPV and NPV with CVA/DVA are equal if the CVA and DVA are determined using the difference method.

###### Analyze NPV

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Analyze NPV | L5 | trm03 p.12 | loio `4e1cdb0640f520cce10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e1cdb0640f520cce10000000a42189c.html?locale=en-US)

**Procedure**

- 1. Open the Analyze NPV app on SAP Fiori Launchpad or in the back end under Treasury and Risk Management Market Risk Analyzer Mark-to-Market Analyze NPV (transaction JBRX).
- 2. Specify the Evaluation Currency, the Evaluation Type, the Evaluation Date and the Horizon.


[figure TRM03-F004]

- 3. On the General Selections tab page, specify the financial objects that you want to analyze. Note the following special considerations when selecting transactions. You can also use the buttons Only Actual, Only Simulated, Insert Actual, and All as input help. The fields Position Number and Number of Simulation Run are then filled in accordance with your selection.

- 4. You can further limit the transactions by entering characteristic values on the Characteristics tab page.
- 5. On the Report Structure tab page, define the structure of the columns in the report.

If required, enter one or more scenarios by choosing the Scenarios pushbutton.

Enter one or more market data shifts by choosing the Market Data Shifts pushbutton.

By choosing the Key Figures pushbutton, you can define whether you want to calculate the net present value and the clean price.

If you set the Include Differences indicator, the system shows how the net present values of the scenarios and market data shifts have changed in comparison with the net present value calculated using current market data.

- 6. On the Control Data tab page, you define whether a detailed log is created and whether it is possible to navigate through the portfolio hierarchy.


- 7. Choose Execute.


**Results**

The net present values for single financial objects (single transactions, single positions) are calculated. The system can display a maximum of 11 columns. This comprises either 10 scenarios with no differences or 5 scenarios with differences. If you choose more scenarios, the system first ignores the differences, and then it ignores any scenarios chosen after the tenth one.

The detailed log contains the following information:

Terms of the cash flows

Division into variable/fixed cash flows

Market data with the Customizing settings used in the evaluation

Conditions of the valued transactions

Details about how the forward interest rates were calculated

The discounting factors used to discount the cash flows, and the NPVs resulting for the individual flows

Total NPVs in both the transaction and the display currency (the exchange rate used in the translation process), possibly further divided into fixed and variable NPVs

Any errors or warnings that occurred during the NPV calculation

###### Rules for Selecting Transactions (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Analyze NPV > Rules for Selecting Transactions | L6 | trm03 p.14 | loio `0e8fc7531dc61d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0e8fc7531dc61d4be10000000a174cb4.html?locale=en-US)

You can select transactions using 2 alternative criteria:

- 1. Selection of transactions by specifying a view and portfolio hierarchy, or by specifying characteristic values
- 2. Selection of transactions by specifying a position number or a simulation run number (actual transactions have blank position and simulation run numbers)


Generally the following applies: The following always applies: Entering selection criteria acts as a restriction, which means that if you do not make any entries the system selects all transactions. If you enter selection criteria the system will therefore select the generated intersection.

|If you want to ...|... then you need to enter the following selections:|
|---|---|
|Select all transactions|No entry (default setting)|
|Select only actual transactions|Fill either the Position Number field or the Simulation Run field with #.|
|Select only simulated and fictitious transactions|Define the transaction selection by filling either the Position Number field or the Simulation Run field.|

###### Sensitivity Key Figures

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Analyze NPV > Sensitivity Key Figures | L6 | trm03 p.14 | loio `58f8875451c5bf2ae10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/58f8875451c5bf2ae10000000a44538d.html?locale=en-US)

Use

Sensitivity key figures describe the interest rate risk of securities. They are usually calculated for fixed-rate securities.

If you do not consider the creditworthiness of the borrower or market efficiency, then fixed-rate securities are subject only to the risk of a change in market interest rates during their term. This interest rate risk comprises reinvestment risk and rate risk. All repayment flows (principal repayments, interest, and compound interest) for an investment that occur before the investor's planning horizon, are exposed to reinvestment risk. For example, if market interest rates are falling, the coupon payments can only be reinvested at lower interest rates. If the maturity date of the investment exceeds the planning horizon, then there is an additional rate risk because the rate is governed during the term of the transaction by the market interest rate.

Market interest rate changes have opposite effects on both these yield components of an investment: Increasing interest rates give rise to rate losses on the one hand but increasing reinvestment yields on the other. Sensitivity key figures enable you to quantify and manage such interest rate change risks and opportunities more easily.

**Features**

The system enables you to calculate the sensitivity key figures Macaulay duration, Fisher-Weil duration, convexity, basis point sensitivity, modified duration and yield to maturity.

Macaulay Duration

Macaulay duration describes the term that an investment needs to have so that the counteracting effects of rate change and reinvestment yield offset each other exactly. Macaulay duration can be interpreted as the average commitment period in years of the invested capital.

The Macaulay duration of a portfolio is the mean value of the Macaulay durations calculated for the individual transactions and weighted by their NPVs.

The system calculates the Macaulay duration of individual transactions as follows:

Macaulay Duration of a Fixed-Rate Transaction

The Macaulay duration of a fixed-rate transaction is the quotient of the total of the cash flows weighted at the points in time of the payments, and the NPV of the transaction on the horizon.

[figure TRM03-F005 - where CF are the cash flows of the transaction at time point t, t is the horizon date, and d the discount factors of time point t for horizon date t .]

where CF are the cash flows of the transaction at time point t, t is the horizon date, and d the discount factors of time point t for horizon date t .

i i horizon i i horizon

Macaulay Duration of Variable-Rate Transactions

For a variable transaction, the system takes market data from the time period between the horizon and the maturity date of the last coupon whose interest rate fixing date is before the horizon.

MD = t - t

maturity horizon

where t is the maturity date of the coupon and t is the horizon. The system calculates the Macaulay duration in years. If the variable side is after the horizon date, the Macaulay duration is set to zero.

maturity horizon

Macaulay duration of a swap

The Macaulay duration of a swap is the weighted total of the Macaulay duration for the variable and fixed-rate parts, with the summands being weighted by the proportion of the respective swap side in the NPV of the total swap.

[figure TRM03-F006 - The Macaulay duration of a swap is the weighted total of the Macaulay duration for the variable and fixed-rate parts, with the summands being weighted by the proportion of the respective swap side in the NPV of the total swap.]

where NPV is the NPV of the variable side of the swap; NPV is the NPV of the fixed side of the swap on the horizon date; NPV is the NPV of the swap (or + NPV ), CF are the cash flows of the transaction at time point t; t is the horizon date; d is the discount factor from time point t to the horizon date t and t is the maturity date of the last variable-rate coupon whose interest rate fixing date is before the horizon. The system calculates the Macaulay duration in years.

var fix swap var fix i i horizon i i horizon maturity

**Note:**

Note that the calculation of the Macaulay duration for variable-rate transactions and swaps gives useful results only if the yield curves for adding accrued interest, and discounting, are identical. However, in the SAP system you can use various yield curves for forward rates, and discounting. There is currently no suitable theoretical model for Macaulay duration for this case.

The calculations used to determine the Macaulay duration for variable-rate transactions and swaps come from Albrecht/Stephan (1993) [Single-factor immunizing duration of an interest rate swap, Proceedings of the 4th AFIR International Colloquium, Orlando, 1994, Vol. 2, pp. 757-780].

**Caution:**

Macaulay duration is not calculated for options, since this is not relevant from a business perspective.

Fisher-Weil Duration

Fisher-Weil duration describes the elasticity of the NPV to interest rate changes.

The system calculates the Fisher-Weil duration as the difference quotient of the NPVs by shifting the underlying market rates:

[figure TRM03-F007 - where NPV is the net present value of the transaction, and NPV(+ e ) and NPV(- e ) is the NPV of the transaction after the market rates have been shifted upwards or downwards. A basis point is used as the value of the shift (= 0.01% = 0.0001). The system calculates the Fisher-Weil duration in years.]

where NPV is the net present value of the transaction, and NPV(+ e ) and NPV(- e ) is the NPV of the transaction after the market rates have been shifted upwards or downwards. A basis point is used as the value of the shift (= 0.01% = 0.0001). The system calculates the Fisher-Weil duration in years.

The Fisher-Weil duration shows by how many basis points the value of an interest rate instrument changes when the level of the interest rate changes by one basis point. Therefore the change in the NPV can be understood as follows:

[figure TRM03-F008 - The Fisher-Weil duration of a portfolio is the mean value of the Fisher-Weil durations calculated for the individual transactions and weighted by their NPVs.]

The Fisher-Weil duration of a portfolio is the mean value of the Fisher-Weil durations calculated for the individual transactions and weighted by their NPVs.

Convexity

The convexity is the sensitivity of the NPV to changes in the interest rate described by the curvature of the price curve.

The system calculates the convexity as the difference quotients by shiftingthe underlying market interest rates:

[figure TRM03-F009 - The system calculates the convexity as the difference quotients by shiftingthe underlying market interest rates:]

where NPV is the net present value of the transaction, and NPV(+ e ) and NPV(- e ) is the NPV of the transaction after the market rates have been shifted upwards or downwards. A basis point is used as the value of the shift (= 0.01% = 0.0001). The factor 10 is the standardization.

-2

The convexity of a portfolio is the mean value of the convexities calculated for the individual transactions and weighted by their NPVs.

Sensitivity per Basis Point (Price Value of Basis Point, PVBP)

The basis point value describes the change in the market value in the event of an increase in market interest rates for all terms, each by one basis point (0.01%). It specifies absolute changes.

PVBP = NPV(+e) - NPV

Modified Duration (MODDUR)

Modified duration is an adjusted measure of the duration of an investment, in which Macaulay's duration value is adjusted with the yield to maturity (YTM) of the investment.

For fixed-rate/variable-rate transactions other than a swap, the system calculates the modified duration as follows:

MODDUR = MD / (1 + YTM)

For a swap, the system calculates modified duration as follows:

MODDUR = NPV * MODDUR /NPV + NPV * MODDUR /NPV

incomingleg incomingleg outgoingleg outgoingleg

where NPV , NPV and NPV are the net present value of incoming leg, outgoing leg and both the legs of the swap respectively.

incomingleg outgoingleg

MODDUR and MODDUR are the modified durations of the incoming and outgoing legs of the swap.

incomingleg outgoingleg

The system calculates the modified duration of the portfolio by taking the NPV weighted mean of the modified durations of each of the transactions belonging to the portfolio:

Modified duration of the portfolio = ∑ NPV * MODDUR/NPV

I i

where NPV and MODDUR are the net present value and modified duration of the i th transaction of the portfolio respectively.

i i

NPV is the Net Present Value of the entire portfolio.

Yield to Maturity (YTM)

The Yield to Maturity (YTM) is the interest rate at which the net present value of the future cash flows is equal to the actual market value of the investment.

The system calculates the YTM by solving the equation specified below:

[figure TRM03-F010 - where]

where

CF is the fixed future cash flow of the investment at the time point t

i i

MV(t ) is the market value of the investment at horizon date

horizon

**Note:**

Diverging Values for Fisher-Weil Duration and Convexity

The values calculated by the system for Fisher-Weil duration and convexity can become very large if the NPV of the transaction is very small. This is often the case for derivatives. For swaps, negative and positive cash flows can almost net each other off.

For this reason, it is possible that the values calculated for Fisher-Weil duration and convexity for particular transactions cannot be interpreted properly. Since the system aggregated the values weighted by their NPVs, the fact that the values diverge is not problem if the relevant transactions are in the same base portfolio as loans, for example.

Dependency of the Continuous Compounding Indicator

How the key figures for Macaulay duration and Fisher-Weil duration are calculated depends on whether you set the

Continuous Compunding indicator for the yield curve type used. If you set the indicator, then the system uses constant zero rates to interpolate the interest rates, and not annual rates. It also applies the act/365 interest calculation method, and regardless of other settings, it uses the linear interpolation method.

In these conditions, the values calculated for Macaulay duration and Fisher-Weil duration should be the same, provided one or multiple fixed cash flows are used for the calculation, and exact formulas, formulated by derivation, are taken into account. If the cash flows are linked to a reference rate, then the values for the two types of duration are the same if the same yield curve is used for the calculation of forward rates and for discounting. Since the system uses difference quotients to calculate an approximation of the sensitivity key figures, the values calculated for Macaulay duration and Fisher-Weil duration are usually the same for only one deterministic cash flow. For more complex products, and for variable-rate products, the results are usually different.

Example of a Single, Deterministic Cash Flow

For single, deterministic cash flows, the values calculated for sensitivity key figures depend only on the term of the cash flow and the interest rate that is valid. The following formulas NPV specifies the net present valuje of the cashflow, interest rate (i) the interest rate, and term the residual term of the cash flow:

term = t - t

maturity horizon

where t is the maturity date of the coupon and t is the horizon date. The following example of a single, deterministic cash flow is based on the assumption that exact formulas have been used for the sensitivity key figures.

maturity horizon

If the Continuous Compounding indicator is not set, and the term of the cash flow is up to one year, then the system uses the linear interest calculation method:

[figure TRM03-F011 - If the Continuous Compounding indicator is not set, and the term of the cash flow is one year or more, then the system uses the exponential interest calculation method:]

If the Continuous Compounding indicator is not set, and the term of the cash flow is one year or more, then the system uses the exponential interest calculation method:

[figure TRM03-F012 - If the Continuous Compounding indicator is set, then the system uses the constant interest calculation method, regardless of the term of the cash flow:]

If the Continuous Compounding indicator is set, then the system uses the constant interest calculation method, regardless of the term of the cash flow:

MD = term

FWD = term = MD

Convexity = term2

**Activities**

You have two options for calculating sensitivity key figures. Either use the functions in the Results Database or, in the SAP Easy Access screen choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Information System Sensitivity Analysis Sensitivity Key Figures (transaction AISS).

###### Sensitivity Analysis

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Analyze NPV > Sensitivity Analysis | L6 | trm03 p.20 | loio `b313da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b313da531198434de10000000a174cb4.html?locale=en-US)

You can use sensitivity analysis to analyze portfolios while making systematic changes to market parameters. This enables you to identify how sensitive selected portfolio values are to changes in various influencing factors, such as the exchange rate or the yield curve.

**Procedure**

In the SAP Easy Access screen, choose Accounting Treasury and Risk Management Transaction Manager Information System Reports Risk Settings Risk Analysis Sensitivity Analysis .

In the Selection of Transactions data group, specify the base portfolios you want to analyze:

Choose a View.

Choose a Portfolio Hierarchy.

You can define that the system selects only those transactions on a particular Portfolio Hierarchy Node.

Enter the evaluation parameters:

Choose an Evaluation Type.

Choose an Evaluation Currency.

Choose an Evaluation Date.

Specify the Horizon.

[figure TRM03-F013 - If required, enter one or more Scenarios.]

If required, enter one or more Scenarios.

Enter the market price changes by selecting the factors whose values you want to adjust.

You can choose from the following factors:

Yield curves (all; all for a particular currency; a particular yield curve; relative shift, or absolute shift)

Currencies (all currency pairs, all exchange rate pairs for a target currency, a particular currency pair)

Securities (all, one class)

Indexes (all; a particular index)

Volatilities (all; one in all terms; one particular volatility)

Specify how much each factor is to shift in percentage.

Choose Execute.

**Result**

The NPV ( currentNPV) is calculated for every portfolio hierarchy node, either based on the market data or on the specified scenarios. The changed NPV based on the market price changes ( Sim. NPV) and the absolute difference from both values are shown as profit/loss.

###### Grid Analysis

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Analyze NPV > Grid Analysis | L6 | trm03 p.21 | loio `b013da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b013da531198434de10000000a174cb4.html?locale=en-US)

In grid analysis, a portfolio evaluation is carried out several times on the basis of changing price parameters. The change in the NPV of the position is calculated for each combination of price parameters. In this way, you can identify how sensitive selected portfolio values are to changes in one or two influencing factors, such as the exchange rate and the interest structure yield curve.

You can easily recognize unfavorable price parameter combinations as worst-case.

[figure TRM03-F014]

**Procedure**

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Information System Reports Risk Settings Risk Analysis Sensitivity Analysis Grid Analysis .
- 2. In the Selection of Transactions data group, specify the base portfolios you want to analyze:

Choose a View.

Choose a Portfolio Hierarchy.

You can define that the system selects only those transactions on a particular Portfolio Hierarchy Node.

- 3. Enter the evaluation parameters:


Choose an Evaluation Type.

Choose an Evaluation Currency.

Specify the Evaluation Date.

Specify the Horizon.

If appropriate, enter a Scenario.

[figure TRM03-F015]

- 1. Now select the X-axis and Y-axis factors whose values you want to be able to vary. You can choose from the following factors:

Yield curves (all; all for a particular currency; a particular yield curve)

Currencies (all currency pairs, all exchange rate pairs for a target currency, a particular currency pair)

Security (all, one class)

Indexes (all; a particular index)

Volatilities (all, a particular volatility)

- 2. Define the gradual change of the initial values in the Percentage field and enter the number of steps. The number of steps defines the size of the grid.
- 3. Choose Execute.


**Result**

Within a grid structure, you will see the NPV changes for all combinations of the market price changes you specified.

**Note:**

Choose to display the data using SAP Business Graphics.

Choose Error log to display the errors that occurred during processing.

Choose Calculation basis to display the market data and scenario data on which the NPV calculation is based.

###### Value at Risk - Individual Analysis

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Value at Risk - Individual Analysis | L5 | trm03 p.23 | loio `4f661ba5ced25121e10000000a421937` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f661ba5ced25121e10000000a421937.html?locale=en-US)

Procedure

- 1. Choose Treasury and Risk Management Market Risk Analyzer Information System Value at Risk VaR Individual Analysis (transaction RMV0).
- 2. In the Mode area, first select the VaR mode for VaR Single Value Analysis. With this, you specify whether the evaluation parameters for VaR calculation are taken from a VaR type defined for the results database or from the VaR key figure. The following options are available:

VaR Type

The evaluation parameters are taken from a VaR type defined in the Customizing activity Define Value-at-Risk Type.

VaR Key Figure

The VaR evaluation parameters are taken from a VaR key figure defined for the results database (transactionAFWKF_RA). The key figure must have the key figure type RAV1VaR from Simulation Method or RAK1VaR by Variance/Covariance. The settings Evaluation Type, Valuation Area, Risk Hierarchy, and Currency are taken from the key figure definition.

VaR Key Figure, Overwrite Mode

As with the option VaR Key Figure, the settings Evaluation Type, Valuation Area, Risk Hierarchy, and Currency are not taken from the key figure definition. These settings need to be made explicitly in the program.

Market Risk Key Figure Set

The evaluation parameters are taken from a market risk key figure set defined under Manage Market Risk Key Figure Sets.

This mode is available only if you activated the static analysis structure.

- 3. In the data group Evaluation Parameters, you enter the following data on the basis of the VaR mode selected:


VaR Type mode

Enter the VaR type, the evaluation type, the evaluation date, the risk hierarchy, and, if necessary, a risk hierarchy node.

**Caution:**

To display the risks within value-at-risk evaluations, it is important that the risk hierarchy and the evaluation type match. An interest rate risk can be displayed only if the yield curve type of the evaluation type is the same as that of the risk hierarchy.

VaR Key Figure mode

Select the relevant VaR key figure and enter the evaluation date.

**Caution:**

To display the risks within value-at-risk evaluations, it is important that the risk hierarchy and the evaluation type match. An interest rate risk can be displayed only if the yield curve type of the evaluation type is the same as that of the risk hierarchy.

VaR Key Figure, Overwrite Mode mode

Enter the VaR key figure, the evaluation type, the evaluation date, the risk hierarchy, and, if necessary, a risk hierarchy node.

**Caution:**

To display the risks within value-at-risk evaluations, it is important that the risk hierarchy and the evaluation type match. An interest rate risk can be displayed only if the yield curve type of the evaluation type is the same as that of the risk hierarchy.

Market Risk Key Figure Set mode

Enter the market risk key figure set, the evaluation date, and the valuation area.

- 4. You define how historic market data is selected using Start of History.

Using the market data from the day in the historical period that is furthest in the past, the system determines the market price changes as base values for the historical simulation and the variance/covariance approach

- 5. Choose the display currency, selecting the relevant indicator if you want to have a detailed log.
- 6. Enter the selection criteria for the financial transactions on the General Selections tab. You can select transactions right down to the single-transaction level. Note the following rule for selecting transactions. You can also use the Only Actual, Only Simulated, Insert Actual, and All pushbuttons as input help. The Position Number and Number of Simulation Run fields are then filled in accordance with your selection.

- 7. Restrict the transactions further by choosing characteristic values on the Characteristics tab.
- 8. Choose Execute.


**Results**

You receive a list of all selected transactions, providing an overview of the value-at-risk, the current net present value, as well as the delta and gamma per transaction. After selecting a transaction, you can perform the following actions:

|Pushbutton|Description|
|---|---|
|Single Transaction|You navigate to the master data of the transaction.|
|Detailed Log|You navigate to the detail log for the net present value calculation.|
|Risk Hierarchy Node.|This takes you to the risk hierarchy display. By choosing a node, you return to the results list, but this list now shows only the transactions and the value-at-risk key figures for the selected parts of the risk hierarchy. If you want to restore the original list, choose Risk Hierarchy Node again and select the highest node of the risk hierarchy.|
|P/L Distribution|On the left side of the screen, the profits and losses for the selected period are listed. On the right side of the screen, a graphic shows these values sorted by amount and the frequency distribution. By way of comparison, the graphic also shows the normal distribution with an expected value of 0 and the standard deviation of the profits/losses over the frequency distribution.|

###### Calculate Market Risk Key Figures (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Calculate Market Risk Key Figures | L5 | trm03 p.26 | loio `5f02c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5f02c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

You use the Calculate Market Risk Key Figure functions to calculate certain market risk key figures online for a group of financial transactions.

Further, you can define your own formula-based key figures based on the system defined market risk key figures. You can display the formula-based key figures together with the other NPV and sensitivity key figures.

By specifying the evaluation date and horizon date, you define for which date the financial transactions and market data are selected.

**Integration**

The Calculate Market Risk Key Figures app uses the infrastructure of the NPV single value analysis (transaction JBRX) and the calculation of sensitivity key figures (transaction AISS).

Formula-based key figures are defined in the key figure layout using the formula editor, which is also used for evaluations in the Results Database.

**Activities**

- 1. Choose the Calculate Market Risk Key Figures app in the Risk Management business group on SAP Fiori launchpad. The function is also available in the backend system, choose Treasury and Risk Management Market Risk Analyzer

Information System Mark-to-Market Calculate Market Risk Key Figures .

- 2. In the Selections area, enter the following data for the evaluation:

Display Currency

Evaluation Type

Note that, in the key figure layout, you can store a separate evaluation type for each key figure. The evaluation types stored in the key figure layout override the evaluation type entered in the selection screen.

Evaluation Date and Horizon Date

Key Figure Layout

The key figure layout specifies which NPV-based, sensitivity-based, and formula-based key figures are calculated and displayed. To define a key figure layout, choose the Define Key Figure Layout pushbutton.

- 3. Restrict the selection of transactions by making the following entries:


View, portfolio hierarchy, and portfolio hierarchy node

Simulated Transactions

If you want to valuate simulated transactions, enter the position number and the simulation run. Specify whether you want the system to analyze simulated transactions only, or simulated and actual transactions.

Hedged Positions

If you want to valuate hedged positions, enter the relevant dataset. Specify whether you want the system to select the data for a current or a historical portfolio hierarchy node.

Other Selection Conditions

On the Characteristics tab, you can restrict the selection of transactions further by specifying characteristic values.

- 4. On the ALV Layout + Control tab, you define how the results are displayed using the following settings:

Layout for the ALV Display

Indicator that specifies whether the system displays the portfolio hierarchy entered.

Indicator that speficies whether the system generates a detailed log.

- 5. To start the evaluation, choose .



Reporting

The top part of the screen contains the parameters used to define the analysis, the transactions selected, and the portfolio hierarchy.

Navigation Structure

If you specify a portfolio hierarchy when you start the key figure analysis, the portfolio hierarchy is displayed on the left side of the screen. You use the portfolio hierarchy to navigate through the data.

To display key figures for single transactions, double-click a node in the portfolio hierarchy.

Key Figures at the Portfolio Hierarchy Node Level

In the key figure layouts, you can set the relevance indicator to specify that key figures are displayed in the portfolio hierarchy. If you set the indicator and specify a portfolio hierarchy when you start the key figure analysis, the system displays a portfolio hierarchy in the top part of the screen. For all portfolio hierarchy nodes, the system also displays aggregated values for the key figures calculated.

Key Figure Display

The lower part of the screen contains a table of the key figures calculated. For each dataset, the system displays the financial object category and the financial object number, and flags all simulated transactions.

The system shows whether the calculation was successful by means of a traffic light symbol and by highlighting line items in color:

If a key figure for a line item is shown in red:

The system was unable to calculate the key figure. For more information, see the error log.

If a key figure for a portfolio hierarchy node is highlighted in yellow:

The system could not aggregate all of the key figure values. This could be because errors occurred in the calculation of one or more key figure values.

The key figure values displayed on the portfolio hierarchy node level contain only the values for the line items that could be calculated correctly. Key figure values that are incorrect are not included in the aggregation.

**Note:**

If you download the data into Microsoft Excel, the system displays the status of the calculation process in an extra column. If the system could aggregate only some of the key figure values, the letter W is displayed. If errors occurred, the letter E is displayed. If the field is empty, the calculation was successful.

Actions

You can use the following functions:

|Action|Function|
|---|---|
| Selection|The system displays the parameters used for the analysis and for the selection of transactions.|
| Key Figure|In a separate dialog box, the system displays additional information about the key figure selected. The system displays the following information for NPV key figures and sensitivity key figures: Key figure name and key figure category Evaluation type used to calculate the key figure For formula-based key figures, the system displays the name of the key figure. To display the definition of formula-based key figures, choose the Calculate Single Positions icon displayed in the Function column.|
| Detailed Log|The system displays the detailed log containing the steps in the calculation process.|
| Calculation Base|The system displays the market data that the system used to calculate the key figure selected.|
| Error Log|The system displays the error log.|
| Greeks|For the cap or floor selected, the system displays the values for each caplet or floorlet for the key figure selected (delta, gamma, theta, or vega). This data can be displayed only if the key figure value selected is highlighted in green.|
|Double-click the financial object number|The system displays the master data for the transaction that belongs to the financial object. When saved datasets are selected, the data for the saved dataset is displayed.|


**Note:**

Note that the values for certain key figures such as beta, gamma, theta, and vega cannot be aggregated. The system displays these key figures only in the area containing the results for single transactions. Caps and floors are exceptions, since the key figures beta, gamma, theta, and vega can be calculated for each caplet and floorlet. To display them, select the financial object and choose the Greeks pushbutton.

###### Defining Key Figure Layouts

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Calculate Market Risk Key Figures > Defining Key Figure Layouts | L6 | trm03 p.29 | loio `4e1ce41a40f520cce10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e1ce41a40f520cce10000000a42189c.html?locale=en-US)

**Use**

Before you can start the key figure analysis, you need to create a key figure layout. The key figure layout contains all the key figures that the system is to calculate and display. They include NPV and sensitivity key figures as well as formula-based key figures that you can define using the formula editor in the key figure layout.

You can change the key figure layouts at any time, since they are not Customizing settings, but are defined in the selection screen for key figure analysis.

**Procedure**

- 1. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Information System Mark-to-Market Key Figure Analysis .

The system displays a selection screen.

- 2. Choose the Define Report Layout pushbutton.

The system displays a view cluster in which you can define new key figure layouts as well as assign key figures and formulabased key figures.

- 3. Define a key figure layout by specifying an ID for the layout and entering a descriptive name for it.


Definition of NPV and Sensitivity Key Figures as well as Quantity Key Figures for Financial Transactions Relating to Commodities

To assign NPV and sensitivity key figures, select the Key Figures folder in the navigation structure.

Enter the following data for each key figure:

Technical name of the key figure, plus a short and long description

Layout area in which the key figure is displayed

Set the relevance indicator for the single value or portfolio hierarchy display.

Key figure category

The input help for the Key Figure Category field provides an overview of the key figure categories available and their descriptions. See also: Hierarchies of Key Figure Categories

Evaluation type (optional)

You specify the evaluation type only if you want to calculate key figures using separate evaluation types. If you leave this field blank, the system uses the evaluation type that you entered in the selection screen for the key figure analysis.

Market data shift, market data scenario, and scenario progression (optional)

Display format (optional)

Some key figures have dependent key figures that are always included in the calculations of the price calculator. You can still display the dependent key figures in the reports for key figure analysis even if you have not included them in the key figure layout. To display the dependent key figures, choose the Dependent Key Figures pushbutton.

Definition of Formula-Based Key Figures

To define formula-based key figures, choose the Formulas folder in the navigation structure.

Technical name, plus a short and long description

Calculation step in which the formula-based key figure is calculated

You can define that formula-based key figures are calculated in the single value analysis, or for portfolio hierarchy nodes, or when values are aggregated at portfolio hierarchy node level.

Display format (optional)

If you define a new formula-based key figure, the system automatically opens the formula editor. To display the formulas for formula-based key figures that have already been defined, choose Formula Editor.

**Note:**

Note that you can use key figures in the formulas only if you have already saved them in the same key figure layout.

###### Analyzer Information System (1 of 3)

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Analyzer Information System | L5 | trm03 p.30 | loio `7799d65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7799d65378024308e10000000a174cb4.html?locale=en-US)

**Use**

You use this function to display the results data that you have previously stored in the Results Database. You can use the Analyzer Information System to report the following key figures in a consistent way:

Market risk key figures that you have calculated in the single records and final results procedures (such as the NPV, sensitivity key figures, and the value at risk)

Formula-based key figures

The system displays the results data and the portfolio hierarchy. You can use the portfolio hierarchy to navigate to the key figures for each portfolio hierarchy node and in this way display the results data for various aggregation levels, right down to single records. In addition to the results data, you can display the risk hierarchy, the calculation bases, detailed information about the key figures, and the evaluation procedures used. For value-at-risk key figures, you can navigate to the results data using either the portfolio hierarchy or the risk hierarchy.

In Customizing, you can define how the Analyzer Information System displays data, and you can create an initial layout with various key figures and portfolio hierarchies or risk hierarchies (such as for key-date value-at-risk analyses, back testing, and benchmarking).

**Prerequisites**

In Customizing under Treasury and Risk Management Market Risk Analyzer Results Database Edit Key Figures and Evaluation Procedures , you have defined key figures and assigned analysis procedures to them.

Under Market Risk Analyzer Results Database Define Initial Layout , you have created an initial layout.

If required, you have defined formula-based key figures.

You have run analyses using the Results Database.

To display results in the Analyzer Information System, you need authorization for authorization object T_RDB_CVKF. The system checks users' authorization to display data on the basis of combinations of characteristic values and key figures.

**Activities**

1. In the application menu for Treasury and Risk Management, choose Market Risk Analyzer Information System

Analyzer Information System (transaction AIS_STDREP).

2. The system displays a selection screen.

Enter the characteristics for the selection of results data and choose Execute.

**Result**

The system displays the key figures of the related single records and final results procedures in the initial layout that you have defined.

Portfolio Hierarchy

The top part of the screen contains a navigation structure based on the portfolio hierarchy. To the right of this are the key figures of the hierarchy level.

Detailed Information

To display detailed information, double-click a node in the portfolio hierarchy. In the lower part of the screen, the system displays additional information about the portfolio hierarchy node. Depending on the evaluation procedure, the system displays the Risk Hierarchy and Backtesting tabs.

The Risk Hierarchy tab contains a navigation structure based on the risk hierarchy. To display key figures for each risk factor, double-click a risk hierarchy node.

The Backtesting tab contains the backtesting results.

**Note:**

Note that you can define how value-at-risk key figures are displayed not only by using the portfolio hierarchy, but also by using the risk hierarchy. To do so, choose .

You can use the following functions:

|Action|Function|
|---|---|
||The system hides the detailed information. Only the navigation structure for the portfolio hierarchy is displayed.|
||The system hides the navigation structure for the portfolio hierarchy. Only the detailed information is displayed.|
||In the upper part of the screen, the system displays the navigation structure for the portfolio hierarchy. In the lower part of the screen, the system displays the detailed information for the key figure categories.|
||A dialog box appears containing a navigation structure based on the risk hierarchy, plus the results. You can navigate in the risk hierarchy to display the key figures that were selected.|
||The system displays the single records for the portfolio hierarchy node that you have selected.|


|Action|Function|
|---|---|
||The system displays the selection parameters that you have specified when you called the Analyzer Information System.|
||The system compares the current data records with the older data records from the Results Database. In a dialog box, you can enter the start date and time periods for the historical comparison.|
||The system displays the calculation bases of the evaluations, including market data such as yield curves and volatilities.|
||The system displays the application log for the evaluations.|
||The system displays the attributes of the key figure selected, including the key figure name and the key figure category.|
||The system displays the final results procedure that is assigned to the key figure selected.|
||The system displays financial objects and their results.|
||The system displays the key figures for a different analysis date.|

###### Hierarchies of Key Figure Categories - Market Risk Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Analyzer Information System > Hierarchies of Key Figure Categories - Market Risk Analyzer | L6 | trm03 p.32 | loio `4c5be66bfc064b55e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c5be66bfc064b55e10000000a42189e.html?locale=en-US)

The system can calculate values only for key figures in the predefined hierarchies for key figures (attributes must be defined for each key figure). The individual key figures are interdependent both from a business and calculation point of view. The interdependencies for the components are shown in the diagrams below:

Market Risk Analyzer

[figure TRM03-F037 - The symmetrical interest rate shifts are purely single-record key figures. The following key figures can be added: NPV general, NPV with shift, exposure, symmetrical interest rate shift, clean price, and NPV for VaR.]

The symmetrical interest rate shifts are purely single-record key figures. The following key figures can be added: NPV general, NPV with shift, exposure, symmetrical interest rate shift, clean price, and NPV for VaR.

**Related Information**

Results Database

###### Functions for Static Analysis Structure

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Functions for Static Analysis Structure | L5 | trm03 p.33 | loio `bcc3b90864734458a2202f5700e9c9ce` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bcc3b90864734458a2202f5700e9c9ce.html?locale=en-US)

###### Manage Market Risk Key Figure Sets

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Functions for Static Analysis Structure > Manage Market Risk Key Figure Sets | L6 | trm03 p.33 | loio `cd0dad32c1b54c209d2715b978caf6d7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd0dad32c1b54c209d2715b978caf6d7.html?locale=en-US)

Create, change, or delete market risk key figure sets.

In a market risk key figure set, you define the parameters - evaluation currency, evaluation type, scenario, shift rule, filter, value-atrisk type, risk factor set - that are relevant for the calculation of market risk key figures.

**Prerequisites**

You must define your evaluation types in Customizing under Treasury and Risk Management Valuation Define and Set Up Evaluation Types .

You must define your value-at-risk types in Customizing under Treasury and Risk Management Market Risk Analyzer Value at Risk Define Value-at-Risk Type .

A value-at-risk type with VaR category Simulation must have the VaR method 1 VaR Determination Based on Profit and Loss.

A value-at-risk type with VaR category Variance/Covariance must have the item calculation 1 Delta Positions.

If you want to calculate market risk key figures based on a specific scenario and/or based on a market data shift, you must first define the scenarios and market data shifts.

For more information, see also

**Editing Scenarios**

Manage Market Data Sets

If you want to use a filter, you must create the filter using the Define Filter function (transaction AFWFL).

The filter is a selection condition based on the analysis characteristics of the static analysis structure that is used to restrict the volume of the selected financial objects.

**Key Features**

This app provides the following key features:

Create a market risk key figure set

- 1. Choose New Entries.
- 2. Enter a name and a description for the market risk key figure set.
- 3. Choose the evaluation currency.

The evaluation currency is the currency in which the market risk key figures are calculated.

- 4. Choose the evaluation type. The evaluation type identifies the market and valuation parameters influencing the calculation of the market risk key figures.
- 5. You can choose a scenario.

Scenarios are sets of market data. A scenario defines only a subset of selected market data within the current market data. If market data isn’t found within the specified scenario, the system performs valuation using the latest market data available.

For more information, see also Editing Scenarios.

If you don’t enter a scenario, the market risk key figures are calculated for current market data with or without a market data shift. This depends on your settings in the Shift Rule column.

- 6. You can choose a shift rule.
- 7. Enter a filter if you would like to restrict the selected financial objects.
- 8. If you want to calculate the value-at-risk key figures (VaR and MEL) in addition to the NPV key figures, you must set the Calculate Value at Risk indicator.

If you set this indicator, you cannot choose a market data scenario or a market data shift.

If you set this indicator, you must specify the value-at-risk type (which defines the value-at-risk calculation method) and the risk factor set (which defines the relevant risk factors).

- 9. Choose the relevant value-at-risk type. The VaR type specifies the valuation parameters for value-at-risk calculation in Risk Management. For more information, see also Value at Risk

- 10. If you selected VaR calculation, you must choose a risk factor set. The risk factor set defines which kinds of risk need to be considered (FX risk and/or interest rate risk) and the specific risk factors relevant for the calculation of value at risk. You also define the risk factor set in this app.
- 11. Set the Real-Time Update indicator if needed.


Set this indicator if you want changes to or the creation of new financial transactions, securities positions, or exposure positions that are covered by the market risk key figure set to trigger an automatic adjustment run of the Calculate Market Risk Key Figures report.

**Note:**

The adjustment run uses the same parameters (derived from the market risk key figure set) as the basic run. Even if you have changed the market risk key figure set in the meantime, the adjustment run uses the same parameters as the basic run. This ensures that all financial objects are processed according to the same parameters on a key date.

This setting ensures that the query views that calculate the market risk key figures are always based on current data.

**Caution:**

Note that setting this indicator will increase the workload during working hours, depending on the operational processes. For example, if you create many financial transactions in a short period of time, market risk key figures will be calculated for them immediately, rather than in a nightly batch run. Value-at-risk calculations can be particularly resource-intensive.

**Note:**

Dependent on your settings in the Scenario and Shift Rule columns, the market risk key figures are calculated in the following way:

Overview of Scenario and Shift Rule Settings

|Scenario|Shift Rule|Result|
|---|---|---|
|-|-|Market risk key figures are calculated based on current market data.|
|x|-|Market risk key figures are calculated based on scenario data.|
|-|x|Market risk key figures are calculated based on current market data + market data shift.|
|x|x|Market risk key figures are calculated based on scenario data + market data shift.|


**Note:**

If you also calculate the value at risk within a market risk key figure set, you can't use scenarios or shift rules.

Create a risk factor set.

- 1. Choose New Entries.
- 2. Enter an ID for the risk factor set.
- 3. Enter a description for the risk factor set.
- 4. Choose the relevant risk factor categories. You can choose either one category only or both.


FX risk

If you choose the FX risk, FX spot rates are used as risk factors.

You must also specify the risk currencies in the risk factor set.

**Note:**

At the time of calculation, the currency pairs are completed by the evaluation currency.

Interest rate risk

If you choose the IR risk, the grid points of the yield curves are used as risk factors. A grid point is identified by the yield curve type, the currency, and the reference interest rate. The yield curves used for discounting as well as the yield curves for the forward calculation are considered. The yield curves for discounting are taken from the evaluation type, while the yield curves for forward calculation are taken from the specific reference interest rates.

You must also specify the currencies of the yield curves in the risk factor set. In addition, at the time of calculation, the evaluation currency is also considered when identifying the yield curves for discounting.

You must specify the interest rate terms of the grid points in the risk factor set. At the time of calculation, the grid points of the derived yield curves (including the reference interest rate) that match the chosen terms are used as risk factors.

Change a market risk key figure set and/or a risk factor set

Even if market risk key figure values based on this market risk key figure set/risk factor set exist, you can nevertheless change the market risk key figure set/risk factor set. Note that such a change in the calculation parameters can lead to a break within the historical time series of the calculated values, with the result that these values are no longer consistently comparable.

Delete a market risk key figure set

If market risk key figure values based on these market risk key figures exist, you cannot delete the market risk key figure set.

**Integration**

Process Overview

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM03-F038]

Please note that image maps are not interactive in PDF outputs.

Processing Steps

Define market risk key figure sets using the Manage Market Risk Key Figure Sets app.

Calculate basic values (NPVs, profits and losses, and delta positions of the single financial objects) needed for the calculation of the market risk key figures and store the results in database tables using the report Calculate Market Risk Key Figures. You can run the report as a background job on a regular basis. The calculation is based on market risk key figure sets. The delta positions are calculated using the central difference quotient.

For more information, see also Calculate Market Risk Key Figures

The final calculation of the market risk key figures is done by the CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery).

You can report the market risk key figures by consuming the CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery). Use the tool of your choice to consume the CDS query views. For more information, see also CDS Views for Treasury and Risk Management

Examples:

SAP Analysis for Microsoft Office

Design Studio

SAP Lumira

SAP Analytics Cloud

**Note:**

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the backend system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

For more information, see also Treasury Executive Dashboard Available in SAP Analytics Cloud.

The CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery) are consumed on the Market Risk tab of the example implementation Treasury Executive Dashboard in the SAP Analytics Cloud application, where you can see the calculated market risk key figures.

View Browser app on SAP Fiori Launchpad

- 1. Open the View Browser and select one of the queries from the list.
- 2. Choose the Show Content button. The Design Studio is called.
- 3. In the Prompts dialog box, fill the Display Currency, Exchange Rate Type, MR Key Figure Set, and Key Date fields. For the Treasury Value at Risk Query, you also must enter the confidence level.
- 4. Confirm your entries by choosing OK.
- 5. You get the results list, which displays the calculated market risk key figures.


**Note:**

You need to have the authorization for a view to launch a CDS view in the Design Studio.

**Note:**

Enter a market risk key figure set and the key date for which you already run the Calculate Market Risk Key Figures report.

In the back end, you can use the Query Monitor (transaction RSRT).

- 1. Open the Query Monitor and find the query using the input help for the Query field.
- 2. In the Query Display field, choose ABAP BICS value.
- 3. Execute the query.
- 4. In the Variables box, fill the Display Currency, Exchange Rate Type, MR Key Figure Set, and Key Date fields. For the Treasury Value at Risk Query, you must also enter the confidence level.


**Note:**

Enter a market risk key figure set and the key date for which you already run the Calculate Market Risk Key Figures report.

- 5. Confirm your entries by choosing OK.
- 6. You get the results list, which displays the calculated market risk key figures.
- 7. You can change the drilldown and the aggregation level by assigning or removing an analysis characteristic from the rows or columns. The query is executed to calculate the market risk key figures at the requested level of detail.


**Market Risk Key Figures**

The following market risk key figures are calculated by the CDS query views based on the data calculated by the job template Calculate Market Risk Key Figures in accordance with the parameters defined in the market risk key figure set:

NPV and Sensitivity Key Figures Calculated by Treasury Market Risk Key Figures Query

Net Present Value (NPV)

The net present value is the sum of the present values of future incoming and outgoing cash flows of a financial instrument or risk position. The present value is determined by discounting future cash flows. Depending on the kind of financial instrument, the amounts of the future cash flows aren’t yet known and the expected future cash flows need to be determined. Especially for options, the probability of whether the option is exercised must also be taken into account. For more information about the calculation of NPVs, see also Price Calculator for Financial Instruments

The NPVs with symmetrical interest rate shifts (shifted by -1 basis point and shifted by +1 basis point) are calculated as the basis for the calculation of the Fisher-Weil duration and are also stored as values.

Clean Price

The clean price is the NPV of a financial transaction without accrued interest from the current interest period.

Option Delta

The option delta represents the sensitivity of the price of an option to a change in the price of the underlying. (Generated for options only.)

Macaulay Duration

Macaulay duration describes the term that an investment must have so that the counteracting effects of rate change and reinvestment yield offset each other exactly. Macaulay duration can be interpreted as the average commitment period (in years) of the invested capital. The Macaulay duration of a portfolio is the mean value of the Macaulay durations calculated for the individual transactions and weighted by their NPVs. The system calculates the Macaulay duration of individual transactions as follows:

Macaulay Duration of a Fixed-Rate Transaction

The Macaulay duration of a fixed-rate transaction is the quotient of the total of the cash flows weighted at the points in time of the payments and the current NPV of the transaction.

[figure TRM03-F039 - where CF are the cash flows of the transaction at time point t, t is the horizon date, and d the discount factors of time point t for horizon date t .]

where CF are the cash flows of the transaction at time point t, t is the horizon date, and d the discount factors of time point t for horizon date t .

i i horizon i i horizon

Macaulay Duration of Variable-Rate Transactions

MD = t - t

maturity horizon

where t is the maturity date of the coupon and t is the horizon. The system calculates the Macaulay duration in years. If the variable side is after the horizon date, the Macaulay duration is set to zero. For a variable transaction, the system takes market data from the time period between the horizon and the maturity date of the last coupon whose interest rate fixing date is before the horizon.

maturity horizon

Macaulay duration of a swap

The Macaulay duration of a swap is the weighted total of the Macaulay duration for the variable and fixed-rate parts, with the summands being weighted by the proportion of the respective swap side in the NPV of the total swap.

[figure TRM03-F040 - The Macaulay duration of a swap is the weighted total of the Macaulay duration for the variable and fixed-rate parts, with the summands being weighted by the proportion of the respective swap side in the NPV of the total swap.]

where NPV is the NPV of the variable side of the swap; NPV is the NPV of the fixed side of the swap on the horizon date; NPV is the NPV of the swap (or + NPV For a variable transaction, the system takes market data from the time period between the horizon and the maturity date), CF are the cash flows of the transaction at time point t; t is the horizon date; d is the discount factor from time point t to the horizon date t and t is the maturity date of the last variable-rate coupon whose interest rate fixing date is before the horizon. The system calculates the Macaulay duration in years.

var fix swap var fix

i i horizon i i horizon maturity

The system calculates the Macaulay duration of the portfolio by taking the NPV-weighted mean of the Maccaulay durations of each of the transactions belonging to the portfolio:

Macaulay duration of the portfolio = ∑ NPV * MACDUR/NPV

i i

where NPV and MACDUR are the net present value and Macaulay duration of the i-th transaction of the portfolio respectively.

i i

**Note:**

The calculation of the Macaulay duration for variable-rate transactions and swaps produces useful results only if the yield curves for adding accrued interest and discounting are identical. However, in the SAP system, you can use various yield curves for forward rates and discounting. There’s currently no suitable theoretical model for Macaulay duration for this case.

The calculations used to determine the Macaulay duration for variable-rate transactions and swaps come from Albrecht/Stephan (1993) [Single-factor immunizing duration of an interest rate swap, Proceedings of the 4th AFIR International Colloquium, Orlando, 1994, Vol. 2, pp. 757-780].

**Caution:**

Macaulay duration isn’t calculated for options as this isn’t relevant from a business perspective.

Fisher-Weil Duration

Fisher-Weil duration describes the elasticity of the NPV to interest rate changes. The system calculates the Fisher-Weil duration as the difference quotient of the NPVs by shifting the underlying market rates:

[figure TRM03-F041 - where NPV is the net present value of the transaction, and NPV(+ e) and NPV(- e) is the NPV of the transaction after the market rates have been shifted upwards or downwards. A basis point is used as the value of the shift (= 0.01% = 0.0001).]

where NPV is the net present value of the transaction, and NPV(+ e) and NPV(- e) is the NPV of the transaction after the market rates have been shifted upwards or downwards. A basis point is used as the value of the shift (= 0.01% = 0.0001).

The system calculates the Fisher-Weil duration in years. The Fisher-Weil duration shows by how many basis points the value of an interest rate instrument changes when the level of the interest rate changes by one basis point. Therefore, the change in the NPV can be understood as follows:

[figure TRM03-F042 - The Fisher-Weil duration of a portfolio is calculated in the same way based on the NPV , NPV(+ e ) , and NPV(- e)]

The Fisher-Weil duration of a portfolio is calculated in the same way based on the NPV , NPV(+ e ) , and NPV(- e)

Portfolio Portfolio Portfolio

.

Convexity

The convexity is the sensitivity of the NPV to changes in the interest rate described by the curvature of the price curve. The system calculates the convexity as the difference quotients by shifting the underlying market interest rates:

[figure TRM03-F043 - The convexity is the sensitivity of the NPV to changes in the interest rate described by the curvature of the price curve. The system calculates the convexity as the difference quotients by shifting the underlying market interest rates:]

where NPV is the net present value of the transaction, and NPV(+ e) and NPV(- e) is the NPV of the transaction after the market rates have been shifted upwards or downwards. A basis point is used as the value of the shift (= 0.01% = 0.0001). The factor 10 is the standardization. The convexity of a portfolio is the mean value of the convexities calculated for the individual transactions and weighted by their NPVs.

-2

Basis Point Value

The basis point value or sensitivity per basis point (price value of basis point, PVBP) describes the change in the market value in the event of an increase in market interest rates for all terms, each by one basis point (0.01%). It specifies absolute changes. Expressed as a formula: PVBP = NPV(+e) - NPV

Modified Duration

Modified duration is an adjusted measure of the duration of an investment in which Macaulay's duration value is adjusted with the yield to maturity (YTM) of the investment.

For fixed-rate/variable-rate transactions other than a swap, the system calculates the modified duration as follows:

MODDUR = MD / (1 + YTM)

For a swap, the system calculates modified duration as follows:

MODDUR = NPV * MODDUR /NPV + NPV * MODDUR /NPV

incomingleg incomingleg outgoingleg outgoingleg

where NPV , NPV and NPV are the net present value of incoming leg, outgoing leg, and both the legs of the swap respectively.

incoming leg outgoing leg

MODDUR and MODDUR are the modified durations of the incoming and outgoing legs of the swap.

incomingleg outgoingleg

The system calculates the modified duration of the portfolio by taking the NPV-weighted mean of the modified durations of each of the transactions belonging to the portfolio:

Modified duration of the portfolio = ∑ NPV * MODDUR/NPV

I i

where NPV and MODDUR are the net present value and modified duration of the i-th transaction of the portfolio respectively.

i i

NPV is the net present value of the entire portfolio.

Value-at-Risk and Mean Excess Loss Key Figures Calculated by Treasury Value at Risk Query

Value at Risk

The value at risk is calculated by considering all the risk factors defined in the risk factor set (including their correlation), but not at the level of a single risk factor.

The value at risk (VaR) represents the potential loss in value of a position (expressed as a net present value) that could – with a certain probability – be realized before the position is hedged or liquidated. The VaR evaluation is thus an extension of NPV analysis, which has the benefit of allowing a standardized approach to risk quantification. The difference between the two types of evaluation is that VaR takes into account the uncertainty of future market developments.

The value at risk can be calculated using the following different methods:

Historical Simulation: Theoretical Background

Structured Monte Carlo

Variance/Covariance Approach: Theoretical Background

Mean Excess Loss

Mean excess loss (MEL) is defined as the mean loss that can be incurred in the scenarios in which the VaR confidence level is exceeded, also taking into account the VaR amount.

**Note:**

Mean excess loss is sometimes also called expected shortfall or tail VaR or conditional VaR.

The mean excess loss is calculated only for market risk key figure sets with VaR types that have a VaR Simulation Category for historical simulation or Monte Carlo simulation.

For more information, see also Mean Excess Loss (MEL)

**Supported Device Types**

Desktop

**Related Information**

Calculate Market Risk Key Figures Delete Market Risk Key Figures

###### Calculate Market Risk Key Figures (2 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Functions for Static Analysis Structure > Calculate Market Risk Key Figures | L6 | trm03 p.43 | loio `c4b94dd03c1f4f2c949992c36141f342` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c4b94dd03c1f4f2c949992c36141f342.html?locale=en-US)

Calculate and store the basic values needed for the calculation of the market risk key figures based on market risk key figure sets.

**Use**

You calculate basic values (NPVs of the single financial objects, profits and losses, and delta positions) needed for the calculation of the market risk key figures and store the results in database tables.

Using the CDS query views Treasury Market Risk Key Figure Value Query and Treasury Value at Risk Query, you can calculate the final market risk key figures on a single level and on aggregation levels based on the values calculated by the Calculate Market Risk Key Figures report.

**Tip:**

This process is only available for the static analysis structure. Whether or not you can use this function depends on the setting made in the Customizing activity Activate Setting for Analysis Structures.

**Integration**

Process Overview

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM03-F044]

Please note that image maps are not interactive in PDF outputs.

Processing Steps

Define market risk key figure sets using the Manage Market Risk Key Figure Sets app.

Calculate basic values (NPVs, profits and losses, and delta positions of the single financial objects) needed for the calculation of the market risk key figures and store the results in database tables using the report Calculate Market Risk Key Figures. You can run the report as a background job on a regular basis. The calculation is based on market risk key figure sets. The delta positions are calculated using the central difference quotient.

For more information, see also Calculate Market Risk Key Figures

The final calculation of the market risk key figures is done by the CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery).

You can report the market risk key figures by consuming the CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery). Use the tool of your choice to consume the CDS query views. For more information, see also CDS Views for Treasury and Risk Management

Examples:

SAP Analysis for Microsoft Office

Design Studio

SAP Lumira

SAP Analytics Cloud

**Note:**

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the backend system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

For more information, see also Treasury Executive Dashboard Available in SAP Analytics Cloud.

The CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery) are consumed on the Market Risk tab of the example implementation Treasury Executive Dashboard in the SAP Analytics Cloud application, where you can see the calculated market risk key figures.

View Browser app on SAP Fiori Launchpad

- 1. Open the View Browser and select one of the queries from the list.
- 2. Choose the Show Content button. The Design Studio is called.
- 3. In the Prompts dialog box, fill the Display Currency, Exchange Rate Type, MR Key Figure Set, and Key Date fields. For the Treasury Value at Risk Query, you also must enter the confidence level.
- 4. Confirm your entries by choosing OK.
- 5. You get the results list, which displays the calculated market risk key figures.


**Note:**

You need to have the authorization for a view to launch a CDS view in the Design Studio.

**Note:**

Enter a market risk key figure set and the key date for which you already run the Calculate Market Risk Key Figures report.

In the back end, you can use the Query Monitor (transaction RSRT).

- 1. Open the Query Monitor and find the query using the input help for the Query field.
- 2. In the Query Display field, choose ABAP BICS value.
- 3. Execute the query.
- 4. In the Variables box, fill the Display Currency, Exchange Rate Type, MR Key Figure Set, and Key Date fields. For the Treasury Value at Risk Query, you must also enter the confidence level.


**Note:**

Enter a market risk key figure set and the key date for which you already run the Calculate Market Risk Key Figures report.

- 5. Confirm your entries by choosing OK.
- 6. You get the results list, which displays the calculated market risk key figures.
- 7. You can change the drilldown and the aggregation level by assigning or removing an analysis characteristic from the rows or columns. The query is executed to calculate the market risk key figures at the requested level of detail.


**Prerequisites**

Before you can define jobs for this report, you must define market risk key figure sets using the Manage Market Risk Key Figure Sets app.

Make sure that the market data is up to date before you start the calculation.

**Features**

You can calculate the market risk key figures for one or multiple market risk key figure sets.

You can run the report in the Basic Run or the Adjustment Run mode.

If you need to delete previously calculated market risk key figure values from the database table, you can use the Delete Market Risk Key Figures mode of the report.

You can define a background job using transaction SM36 for ABAP program RAFWGO_UPLOAD_MRA_KF_SET to run the calculation on a regular basis.

You can start the report manually to execute it only once.

**Activities**

- 1. Choose the Calculate Market Risk Key Figures (transaction RAEP1_KFSET) in the area menu under Market Risk Analyzer Tools .
- 2. Parameters


General

Choose the mode. The followings processing modes are available:

Basic Run

The basic run processes all active financial objects and calculates the market risk key figures.

Every key date must always be preceded by a basic run, which processes all active financial objects. Afterwards, you can execute as many adjustment runs for this key date as required.

Adjustment Run

You can start an adjustment run after you have executed the basic run for the key date.

The adjustment run processes new financial objects and financial objects for which errors have occurred in the basic run. The adjustment run uses the same parameters (derived from the market risk key figure set) and the same market data as the basic run. Even if you have changed the market risk key figure set or market

data in the meantime, the adjustment run uses the same parameters and market data as the basic run. This ensures that all financial objects are processed according to the same parameters on a key date.

**Note:**

The adjustment run can be executed for a specific key date as often as required.

If you deleted the market risk key figures of the basic run, you must first execute a new basic run for the specific key date.

If you set the Real-Time Update indicator, changes to or creation of new financial transactions, securities positions, or exposure positions that are covered by the market risk key figure set initiate an automatic adjustment run for the market risk key figures belonging to the specific objects.

Delete Market Risk Key Figures

For more information, see also Delete Market Risk Key Figures

You can execute the report as a test run.

Evaluation Parameters

Market Risk Key Figure Set

Choose one or multiple market risk key figure sets.

Evaluation Date

The evaluation date is the date on which the market data and financial objects are selected.

Enter the desired evaluation date.

**Note:**

Since the program can be scheduled in the background as a regular job, you can also define a variant for the report in which you can control the evaluation date field dynamically.

- a. Choose Save as Variant. Enter a variant name and description.
- b. In the Objects for Selection Screen table, select the value D D: Dynamic Date Calculation (Local Date) in the Selection Variable column for the Evaluation Date row.
- c. In the Name of Variable column of the same row, now choose one of the the following options:


Current date

Current date +/- ??? days

current date +/- ??? work days

First day of current month

nth working day of current month

First day of next month

First day of previous month

Last day of previous month

Last day of current month

d. Save the variant.

Volas + Correlations

Volatilities and correlations are needed for value-at-risk calculation by Monte Carlo simulations and by the variance/covariance approach.

**Note:**

The relevant volatility types and correlation types are defined in the value-at-risk type, which is assigned to the market risk key figure set.

If you select this indicator, the system automatically triggers the calculation of volatilities and correlations, if needed, and stores the results.

If you have already calculated the volatilities and correlations for the relevant risk factor set, evaluation type, and currencies at the key date, you can deselect this indicator to improve system performance.

If Test Run is selected, you can't set this indicator.

For more information, see also Calculate Volas + Correlations

- 3. Choose Execute.


**Result**

The basic values for market risk key figures are calculated and stored in database tables.

You get a detailed protocol of the calculations performed.

###### Calculate Volas + Correlations

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Functions for Static Analysis Structure > Calculate Market Risk Key Figures > Calculate Volas + Correlations | L7 | trm03 p.48 | loio `4424b55f35484cf194eb2e7b238d7427` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4424b55f35484cf194eb2e7b238d7427.html?locale=en-US)

System calculates volatilities and correlations for risk factor changes on the basis of historical market data.

In this process, the system calculates the standard deviation of the sample, and uses this as an estimate for the volatility. It uses empirical values for covariance as an estimate for the correlations.

The system calculates only volatilities and correlations for the risk factor of the risk tor sets specified. Permitted risk factors are: grid points on yield curves, currency translation rates. Volatilities and correlations for these risk factors are required for the variance/covariance approach, for example, and for Monte Carlo simulation.

In addition to the classic calculation of standard deviations and correlations, system also applies exponential weighting (by using the decay factor in the underlying statistics type).

If no data exists for historical days (trading was suspended or no data was imported by datafeed), the system uses a replacement strategy. The system accesses market data from further in the past. As this process distorts the statistical results, the maximum number of such replacements in a historical time period by means of the error tolerance.

An error log enables you to see which market data was missing.

If the run wasn’t a test run, the system saves the values in the relevant database tables.

The volatilities are stored as annualized values. The system converts the term L (in days) that you enter when you call the statistics calculator into calendar days K, and rounds the values up to whole days:

[figure TRM03-F045]

###### Delete Market Risk Key Figures

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Functions for Static Analysis Structure > Calculate Market Risk Key Figures > Delete Market Risk Key Figures | L7 | trm03 p.49 | loio `523931b984df41888a9069b7b656bd39` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/523931b984df41888a9069b7b656bd39.html?locale=en-US)

With this report variant, you can delete previously calculated basic values of market risk key figures from earlier runs of the Calculate Market Risk Key Figures report.

**Use**

In exceptional cases, you need to delete the basic values of market risk key figures that you have previously calculated using the Calculate Market Risk Key Figures report (transaction RAEP1_KFSET) .

**Activities**

- 1. Choose the Calculate Market Risk Key Figures (transaction RAEP1_KFSET) in the area menu under Market Risk Analyzer Tools .
- 2. Parameters

General

Choose the Delete Market Risk Key Figures mode.

Evaluation Parameters

Market Risk Key Figure Set

Choose one or multiple market risk key figure sets.

Evaluation Date

The evaluation date is the date on which the market data and financial objects are selected and on which the market risk key figures are calculated. In the Evaluation Period field, you can enter one or multiple single evaluation dates or an evaluation period.

In combination with the market risk key figures sets chosen, the system uses the evaluation dates specified to identify which values of the market risk key figure are relevant for deletion.

- 3. Choose Execute.


**Results**

After the system has completed the deletion, all selected market risk key figure values are deleted from the database tables.

If you want to recalculate the market risk key figures for these market risk key figure sets and evaluation dates, you need to start the Calculate Market Risk Key Figures job template as the basic run.

###### Monitor MR Key Figure Calculations

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > NPV Analysis > Functions for Static Analysis Structure > Monitor MR Key Figure Calculations | L6 | trm03 p.50 | loio `fad0223ec5764d3cadf5896352033910` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fad0223ec5764d3cadf5896352033910.html?locale=en-US)

Message logs and calculation details for calculation of market risk key figures based on market risk key figure sets.

You can monitor message logs and calculation details for the runs of the Calculate Market Risk Key Figures report (transaction RAEP1_KFSET).

**Procedure**

- 1. Call the Monitor MR Key Figure Calculations (transaction AFWO1_KFSET) in the area menu of the Market Risk Analyzer under Tools or call the app on the SAP Fiori launchpad.
- 2. Execute the report directly to get a list of all runs executed or select a specifc run by entering selection criteria, such as Market Risk Key Figure Set, Status, Evaluation Date, Created By, and Created On.
- 3. From the result list, mark a line item and switch to the following data:


Execution Parameters

Shows the parameters of the calculation run, such as Evaluation Currency, Scenario, Filter, Value-at-Risk Type and so on.

Calculation Bases

Shows the concrete values of interest rates, FX rates, ans so on relevant for the calculation run.

Simulation Scenarios

Log

Shows all messages for the calculation run.

Log History

**Note:**

The calculations are divided into calculation packages, such as Net Present Value and Value at Risk.

##### Cash Flow at Risk (CFaR)

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Cash Flow at Risk (CFaR) | L4 | trm03 p.50 | loio `70ee5953c91eff4fe10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/70ee5953c91eff4fe10000000a44176d.html?locale=en-US)

**Use**

Cash Flow at Risk is a risk measure that provides information about the value of potential defaults in cash flow in future periods and about the probability with which those defaults will not exceed that value.

This risk measure is of interest to you if you use a long-term time horizon for your cash flow.

The cash flow CF of the future period j (j = 1,...,n) is a function of the market risk factors rf, such as exchange rates or interest rates.

j i

CF = CF (rf ,..., rf )

j j 1 n

**Note:**

Currently, the system supports only the risk factor "Exchange Rate".

[figure TRM03-F046 - Cash Flow at Risk can be calculated for individual periods as well as aggregated across all periods.]

Cash Flow at Risk can be calculated for individual periods as well as aggregated across all periods.

**Note:**

Cash Flow at Risk is a non-additive key figure. The system first determines the relevant cash flow at each calculation level and then calculates the Cash Flow at Risk for that cash flow.

**Integration**

If you have activated the automatic integration of financial objects, Cash Flow at Risk can be calculated for the following cash flows:

Cash flows from forex exposure positions in Exposure Management 2.0

Cash flows from generic transactions

Cash flows of a financial transaction in the Transaction Manager with fixed flows (such as forward exchange transactions)

**Note:**

It is not possible to consider financial transactions with variable flows that are dependent on the development of reference interest rates.

Options cannot be considered either.

**Prerequisites**

CFaR: Customizing, Master Data, and Market Data

**Features**

It is possible to calculate Cash Flow at Risk using the following methods:

Simulation methods

Structurized Monte Carlo for CFaR

Full Evaluation

Delta Evaluation

Delta/Gamma Evaluation

Parametric methods

Variance/Covariance Approach for CFaR

Delta Evaluation

Delta/Gamma Evaluation

**Activities**

Calculating Cash Flow at Risk Online

You can calculate Cash Flow at Risk online using the program CFaR Single Value Analysis (transaction RMC0). In this case, the calculation results are not saved.

###### Structurized Monte Carlo for CFaR

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Cash Flow at Risk (CFaR) > Structurized Monte Carlo for CFaR | L5 | trm03 p.52 | loio `33325c535b404e3fe10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/33325c535b404e3fe10000000a441470.html?locale=en-US)

**Use**

Monte Carlo simulation is a simulation method used to describe potential changes to the values of risk factors using random walks. Random walks are generated using a stochastic process. The random numbers required for this process are generated using a random number generator, and various methods can be used to transform these random numbers into the standard normal distribution.

Monte Carlo simulation is based on the assumption that changes to risk factors are distributed normally with an expected value of zero and positive variance. The parameters required for the stochastic process can be calculated using historical values (structurized Monte Carlo).

Monte Carlo simulation comprises the following steps:

- 1. Generation of a time series of independent random numbers, distributed using standard normal distribution, for each risk factor:

X , X , X , ..., X

To generate random numbers, you can choose one of the following methods:

Box-Muller Method

Tree Method

Strata-Gems Method

- 2. With the random numbers determined in this way and distributed using standard normal distribution, a random walk is determined for a risk factor rf(t ), rf(t ), rf(t ), rf(t ), and so on. Determination of the random walk depends on the element type selected in the statistics type:

Relative

rf(t) = rf(t )*(1+X)

Logarithmed

rf(t) = rf(t )*exp(X)

where the start value rf(t ) is always the actual value of the risk factor as per the market data table on the evaluation date.

- 3. CFaR calculation is then performed on the basis of the random walks.


1 2 3 n

1 1 2 3

i i-1 i

i i-1 i

0

[figure TRM03-F047 - Integration]

Integration

The Cash Flow at Risk values are represented on the basis of the portfolio hierarchy, the risk hierarchy, and the maturity band.

It is possible to calculate Cash Flow at Risk using the following methods:

With the full valuation approach, the profit/loss on the hierarchy levels of the risk hierarchy is calculated for the position on each portfolio hierarchy level by recalculating the cash flow afresh for each random walk.

This approach delivers precise results. However, in cases involving a large number of random walks, calculations can require very long runtimes.

If the cash flow has a linear dependency on the risk factor, you can use approximations that also lead to precise results but require shorter calculation runtimes:

With the delta approach, the reactability of the cash flow to risk factors is calculated for each portfolio on a risk hierarchy level independently of the historical market prices (delta positions). For this, the function CF(rf) is approximated using a linear function.

The delta/gamma approach operates in the same way as the delta approach but, in addition, includes the nonlinear terms of the second order (gamma positions) at the risk factor level. In this way, the function CF(rf) is approximated by a quadratic function.

The delta approach and the delta/gamma approach are also referred to as risk factor mapping.

**Note:**

When calculating Cash Flow at Risk using the variance/covariance approach, you can use only the delta approach and the delta/gamma approach.

###### Variance/Covariance Approach for CFaR

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Cash Flow at Risk (CFaR) > Variance/Covariance Approach for CFaR | L5 | trm03 p.54 | loio `90325c535b404e3fe10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/90325c535b404e3fe10000000a441470.html?locale=en-US)

**Use**

The variance/covariance approach is an analytical procedure for calculating Cash Flow at Risk. The approach is based on an assumption about the distribution of risk factor changes. The variance/covariance approach is used to calculate potential losses owing to the volatility of risk factors. The volatility of the risk factors and their correlations can be estimated using the historical market data for the relevant risk factors (statistics calculator) or transferred from external sources (datafeed, market data file).

The single risks achieved in this way are aggregated using correlation matrixes under the consideration of any interference of combined effects.

Delta Valuation:

The delta approach is based on the assumption of the normal distribution of risk factor changes, and cash flow changes are estimated via the elasticity of the CF function on the different risk factors (delta positions). CF changes are also distributed using normal distribution. The quantile sought can be determined easily using the inverse values of the cumulated normal distribution function. CFaR is then achieved as the product of the quantile and the variance of the cash flow changes.

[figure TRM03-F048 - Delta/Gamma Approach:]

Delta/Gamma Approach:

The assumption of normal distribution does not apply. The delta/gamma approach operates in the same way as the delta approach but, in addition, includes the non-linear terms of the second order (gamma positions) at the risk factor level. In this way, skewed distributions are also interpreted. CFaR is calculated from the four moments of the distribution (expected value, variance, skewness, and kurtosis) using Cornish/Fisher approximation. It calculates the percentile of a normal distribution for a specified confidence level and for the first four moments of a distribution. The calculation of CFaR then occurs in the same way as for the delta procedure.

[figure TRM03-F049 - Delta valuation and the delta/gamma approach are also referred to as risk factor mapping.]

Delta valuation and the delta/gamma approach are also referred to as risk factor mapping.

**Prerequisites**

For the calculation of Cash Flow at Risk using the variance/covariance approach, volatilities and correlations of risk factors are required. These can be determined from historical price changes or imported to the system from third-party vendors.

In addition to calculation by the system using the statistics calculator, the RiskMetrics data record from JP Morgan can be imported using a file interface or a datafeed.

During the calculation, the variances and correlations are estimated for a certain holding period using the statistics calculator. For CFaR calculations using the variance/covariance approach, the variances are always read first for a holding period of one day and then scaled using the root T-method. Here, T is the period from the evaluation date until to middle of the relevant maturity band period.

**Features**

Cash Flow at Risk for a Risk Factor

The system determines the CFaR for a risk factor by calculating the value change of the cash flow that occurs with an isolated price change of this risk factor.

This value change is calculated by determining the delta position in the risk factor and multiplying it by the standard deviation of the risk factor.

The sign (+/-) of the Cash Flow at Risk for risk factors is the same as the sign of the delta.

Cash Flow at Risk on Hierarchy Levels

Cash Flow at Risk is a non-additive key figure and is recalculated on each level.

###### CFaR: Customizing, Master Data, and Market Data

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Cash Flow at Risk (CFaR) > CFaR: Customizing, Master Data, and Market Data | L5 | trm03 p.56 | loio `f6035a5380687e0de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f6035a5380687e0de10000000a4450e5.html?locale=en-US)

**Customizing**

Define Statistics Type

Under Basic Functions Market Data Management Master Data Statistical Data Define Statistics Type , create a statistics type for Cash Flow at Risk calculations. For CFaR calculations, a particularly relevant setting is the one that you make in the Element Category column (= the determination category for sample elements). This category controls how the random walks for the risk factors are generated from the random numbers. Select either 1Relative or 2Logarithmed.

Define Volatility Type

Under Basic Functions Market Data Management Master Data Statistical Data Define Volatility Type , define a volatility type and assign to it the statistics type created for Cash Flow at Risk.

Define Correlation Type

Under Basic Functions Market Data Management Master Data Statistical Data Define Correlation Type , define a correlation type if you want to consider correlations when calculating CFaR with the variance/covariance approach and assign to it the statistics type created for CFaR.

Define Cash Flow at Risk Type

Under Market Risk Analyzer Cash Flow at Risk Define Cash Flow at Risk Type , create a Cash Flow at Risk type.

See also:Define Cash Flow at Risk Type

Define Evaluation Types

Under Basic Analyzer Settings Valuation Define and Set Up Evaluation Types (transaction JBREVAL), create an evaluation type. An important setting in the evaluation type/valuation rule for the calculation of Cash Flow at Risk is the setting that you have made in the Exchange Rate Types area on the Market Data Categories tab. Here, you specify the exchange rate type that the exchange rate needs to have to convert the foreign currency cash flow to the evaluation currency.

Define Maturity Band

Under Market Risk Analyzer Define Maturity Band (transaction JBRLZB), you create maturity bands for CFaR calculations. A maturity band defines the chronological sequence of periods.

When you create a maturity band, start by entering an ID, a short description, and a long description for the maturity band.

Start Date: This date specifies the starting point of the maturity band in the case of absolute maturity bands.

If the field is left blank, the system uses the evaluation date as the starting point for generating the maturity band (relative maturity bands).

Generation Mode:

Relative to Last Generated Date

If you opt for this value for the generation mode, the start/evaluation date is the starting point for the dates that are derived from the first row in the definition of the maturity band. The starting point of the second row of the definition is the last date that was generated for the first entry, and so forth.

Relative to Start/Evaluation Date

If you opt for this value for the generation mode, the start/evaluation date for each row in the definition is the starting point.

Enter Dates Individually

You opt for this value in the case of absolute maturity bands.

**Note:**

Once the maturity band has been saved, it is no longer possible to change the generation mode.

Choose Enter or Goto Details (without saving). Depending on the generation mode that you have selected, the system displays either the table for the maturity band parameters or the table for entering maturity band entries directly.

You define the relative maturity bands using the following parameters:

Time Unit

Day

Month

Year

Increment

Number

Fill

Default value Do Not Fill

- 01Fill to End of Month

- 02Fill to End of Year


30Fill to End of 30th Year

By choosing the Calculate Maturity Band pushbutton, you can control which maturity band entries are generated from your entries.

Save your entries.

**Master Data**

Define Risk Hierarchy (transaction JBRR)

In the application menu for Treasury and Risk Management under Market Risk Analyzer Master Data Risk Hierarchy , you define your risk hierarchy.


In a risk hierarchy, you specify the risk factors for which you want to calculate Cash Flow at Risk. Further, you also define the aggregation levels here. For the CFaR calculations, choose risk factor Exchange Rate as well as all currencies in which you manage your cash flows.

Enter an ID for your CFaR risk hierarchy and choose .

Enter a short name and a long name and assign an authorization group if applicable.

Now choose .


In the Risk Hierarchy Node area at the bottom of the next screen, enter a short name and a long name for the highest node of your risk hierarchy. Now choose Node. Enter a short name and a long name for the node and select the risk type Exchange Rate. Press "Enter" to confirm your selection. Two columns then appear, but you need only fill the first column (From Currency). By leaving the To Currency column empty, the system translates the currency into the evaluation currency.

Create a note for all foreign currencies in which your company makes or receives payments.

See also:Maintaining Risk Hierarchies

Settings in the Results Database

Define Portfolio Hierarchies

Cash Flow at Risk is a non-additive key figure. Cash Flow at Risk is not persisted in the results database, but it is persisted on the relevant aggregation levels. The portfolio hierarchy defines these aggregation levels.

In the application menu for Treasury and Risk Management under Market Risk Analyzer Evaluation Control

Portfolio Hierarchy Define (transaction AFWPH), you create your portfolio hierarchies.

Define Key Figures and Evaluation Procedure

In the application menu for Treasury and Risk Management under Market Risk Analyzer Evaluation Control

Results Database Define Key Figures and Evaluation Procedures (transaction AFWKF_RA), you need to define the CFaR key figures, the single record procedures, and the final results procedures.

See also:CFaR in the Results Database

**Market Data**

Volatilities

The volatility of a risk factor expresses the extent to which the value of a risk factor vacillates over time. If all other factors remain unchanged, a high volatility leads to a higher Cash Flow at Risk.

In the market data tables, you need to maintain volatilities for all risk factors. A volatility always relates to a pair of currencies (foreign currency and evaluation currency).

Correlations

Correlations provide information about whether a change to a risk factor influences a change to another risk factor.

Consequently, correlations between different currency pairs are relevant for CFaR.

If you have opted in the CFaR type for the inclusion of correlations, you need to store correlations between currency pairs in the market data.

Currency Rates

See also:Editing Exchange Rates Manually

You can either enter market data manually, which you do in the application menu for Treasury and Risk Management under Basic Functions Market Data Management Manual Market Data Entry using the functions Enter Volatilities (transaction JBVFX), Enter Correlations (transaction CORR_MAINTAIN), and Enter Exchange Rates (transaction TMDFX), or you can import market data into the system using file interfaces or datafeed.

You can use the statistics calculator to calculate volatilities and correlations.

###### Defining Cash Flow at Risk Types

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Cash Flow at Risk (CFaR) > CFaR: Customizing, Master Data, and Market Data > Defining Cash Flow at Risk Types | L6 | trm03 p.59 | loio `666c6c538ab9e547e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/666c6c538ab9e547e10000000a441470.html?locale=en-US)

**Prerequisites**

You need to define the volatility types and correlation types in Customizing under Treasury and Risk Management Basic Functions Market Data Management Master Data Statistical Data :

Define Volatility Type

Define Correlation Type

**Context**

You use this function to define your Cash Flow at Risk types. In a Cash Flow at Risk type, you store information for Cash Flow at Risk calculations.

**Procedure**

- 1. Start the function either in Customizing under Market Risk Analyzer Cash Flow at Risk Define Cash Flow at Risk Type or in the application menu under Market Risk Analyzer Evaluation Control Valuation Settings Define Cash Flow at Risk Type (transaction S_EIS_72000137).
- 2. Choose New Entries.
- 3. Enter a three-character ID for the CFaR type.
- 4. Enter a description for the CFaR type.
- 5. Choose the CFaR category. The following selections are possible:


- 0Simulation

- 1 Variance/Covariance


- 6. Under General Settings, make the following settings:

Confidence Level

The confidence level represents the probability (in percent) that the deviation of the actual future cash flow from the planned cash flow will not exceed the Cash Flow at Risk.

Volatility Type

The volatility type is an entity that is used to classify volatilities. For each volatility type, volatilities for user-defined underlying transactions such as exchange rates, reference interest rates, security classes, or share index volatilities can be stored in the system. Further descriptive parameters are linked to the volatility type.

Correlation Type

Specifying the correlation type is optional. If you do not specify a correlation type, Cash Flow at Risk is calculated without considering any correlations.

Position Calculation

Here you specify whether transactions are valued completely, or whether an approximation is made (delta, deltagamma). The method influences the length of the runtime for the evaluation.

Full Valuation gives accurate results, but can lead to long runtimes.

An approximation can be used for linear instruments, which gives the same degree of accuracy but with shorter runtimes. The following options are available:

Delta Positions

Delta and Gamma Positions

Note: For the Cash Flow at Risk category Variance/Covariance, only the settings "Delta Positions" and "Delta/Gamma Positions" are permitted.

Calendar ID

- 7. The settings for simulation are relevant only for the Cash Flow at Risk category "Simulation":


Simulation Category

You can select the following calculation methods for generating normally distributed random numbers:

- 01 Structurized Monte Carlo with Box-Muller Alg. for Gen. NDRN

- 02 Structurized Monte Carlo with Tree Method for Gen. NDRN

- 03 Structurized Monte Carlo with Strata-Gems Alg. for Gen. NDRN


Initial Value

Initial value for the generation of random numbers.

If you specify a value, evaluations that are started with identical input parameters lead to the same result.

If you do not specify a value, the start value for the random number generator itself is chosen randomly, and different evaluations with identical input parameters lead to different results.

Simulation Runs

This is the number of simulation runs (random walks) for the Monte Carlo simulation.

**Note:**

A higher number of simulations leads to increased accuracy of the result, but also to a longer runtime of the simulation.

Time Grid

This setting controls how the time grid of the random walk is created.

The following options are available:

Increment by Fixed Number of Days: Each step of the random walk covers the same number of working days (depending on the calendar assigned). The number of days is specified in the "Step Size" field.

Use Maturity Band Key Dates as Time Grid: One random walk step is created for each period of the maturity band that is used in the evaluation run.

In this case, the "Step Size" field is irrelevant, as the length of the steps is variable and depends on the maturity band.

Dependencies:

The smaller the step size you choose, the more realistic the random walk you obtain, but also the longer the program runtime because more steps have to be created. Conversely, using a larger step size or selecting the "Maturity Band" setting leads to a more coarse random walk but improved performance.

Step Size

The number of working days per step of a random walk.

Dependencies

This setting is only relevant if you choose the time grid method Increment by Fixed Number of Days. The smaller the step size you choose, the more realistic the random walk you obtain, but also the longer the program runtime because more steps have to be created. Conversely, using a larger step size leads to a more coarse random walk but improved performance.

CFaR Method

The CFaR method controls how Cash Flow at Risk is calculated based on a simulated profit and loss distribution. The following settings are available:

CFaR Determination Based on Profit and Loss

The profits and losses are sorted and counted according to the confidence level.

CFaR Determination Based on Symmetrical P+L Distribution

Before counting, the profit and loss distribution is made symmetrical by including an additional entry with the opposite sign for each existing entry.

CFaR Determination Based on Normal Distribution Assumption

The standard deviation of the profits and losses is calculated, and the CFaR is determined based on the standard deviation and the confidence level.

- 8. Assign an authorization group.
- 9. Save your entries.

**CFaR in the Results Database**

**Use**

You can calculate Cash Flow at Risk (CFaR) in the results database. Your results are stored on the results database.

**Prerequisites**

CFaR: Customizing, Master Data, and Market Data

Define Portfolio Hierarchies

Cash Flow at Risk is a non-additive key figure. Cash Flow at Risk is not persisted in the results database, but it is persisted on the relevant aggregation levels. The portfolio hierarchy defines these aggregation levels.

In the application menu for Treasury and Risk Management under Market Risk Analyzer Evaluation Control Portfolio Hierarchy Define (transaction AFWPH), you create your portfolio hierarchies.

**Example:**

- 1. Choose New Entries.
- 2. In the Portfolio Hierarchy column, enter a three-digit number as the ID for the new portfolio hierarchy.
- 3. In the Authorization Group column, you can assign an authorization group to the portfolio hierarchy.
- 4. In the Filter column, you can assign a filter.
- 5. In the other columns, enter a short name (such as CC/PT) and a long name (such as Company Code/Product Type) for the portfolio hierarchy.
- 6. Save your entries. Select the portfolio hierarchy that you have created and choose the Structure level on the lefthand side.
- 7. Choose New Entries.
- 8. Select the characteristics at the level of which you would like to calculate Cash Flow at Risk. In the Sort column, specify the sequence of the characteristics in the porfolio hierarchy:
- 9. Save your entries.


**Note:**

You can use a filter to store selection criteria for financial objects for which you want to calculate a key figure. If you want to use this special portfolio hierarchy for a particular group of financial objects, define a filter and assign it in this column. In the application menu for Treasury and Risk Management under Market Risk Analyzer Evaluation Control Results Database Define Filter (transaction AFWFL), you can define filters.

|Characteristic|Sort|
|---|---|
|Company Code|1|
|Product Type|2|


This portfolio hierarchy is used to calculate CFaR at the company code level and at the product type level.

See also:Portfolio Hierarchy and Editing Portfolio Hierarchies

Define Key Figures and Evaluation Procedure

In the application menu for Treasury and Risk Management under Market Risk Analyzer Evaluation Control Results Database Define Key Figures and Evaluation Procedures (transaction AFWKF_RA), you need to make the following settings:

- 1. Define CFaR Key Figures


- a. Enter a name for your key figure with a maximum of eight characters and choose Create.
- b. Select a CFaR key figure category (RACFARSCFaR from Simulation or RACFARCCFaR by Variance/Covariance).


On the next screen, you define the key figures that you require. To be able to calculate the desired final result key figures, certain single record key figures are required.

For the calculation of the CFaR final result key figure for the key figure category RACFARCCFaR by Variance /Covariance, you need the basic key figure RABB as well as a key figure for each of the key figure categories RAB06Cash Flow at Risk and RACFPOSRisk Factor Position.

For the calculation of the CFaR final result key figure for the key figure category RACFARSCFaR from Simulation, you need the basic key figure RABB as well as a key figure for each of the key figure categories RAB06Cash Flow at Risk, RACFPOSRisk Factor Position, and RACFPLCFaR P/L Distribution.

**Note:**

You can also define a key figure for the key figure category RACFOCRYCash Flow in Original Currency, which calculates in the original currency the expected cash flow for the time of the evaluation. For this, not only the basic key figure is required, but a key figure for the key figure category RAB05General Cash

Flow is also required. (Note: The key figure categories RAB06 and RAB05 are identical.) When defining key figures, you assign the evaluation type at the level of the basic key figure. When defining the key figure for the key figure category RAB05General Cash Flow, also specify the evaluation currency and the maturity band.

[figure TRM03-F052 - When defining key figures, you assign the evaluation type at the level of the basic key figure.]

When defining key figures, you assign the evaluation type at the level of the basic key figure.

When defining the key figure for the key figure category RAB06Cash Flow at Risk, you assign the evaluation currency and the maturity band.

This key figure represents the cash flow on which the CFaR calculation is based. Cash flow is calculated on the basis of the spot rates. The maturity band defines the periods.

When defining key figures for the key figure category RACFPOS, assign a risk hierarchy.

Further, specify how position calculation occurs. That is, you specify whether transactions are valued completely, or whether an approximation is made (delta, delta-gamma). The method that you choose

influences the length of the runtime for the evaluation. An approximation can be used for linear instruments, which gives the same degree of accuracy but with shorter runtimes.

The following options are available:

- 01Delta Positions

- 02Delta and Gamma Positions


03Full Evaluation

"Full Valuation" gives accurate results, but can lead to long runtimes.

**Note:**

For the Cash Flow at Risk category Variance/Covariance, only the settings "Delta Positions" and "Delta/Gamma Positions" are permitted.

When defining the key figure for the key figure category RACFPLCFaR P/L Distribution, you make the following settings:

Volatility Type

Correlation Type

Calendar ID

Start Value

Initial value for the generation of random numbers.

If you specify a value, evaluations that are started with identical input parameters lead to the same result.

If you do not specify a value, the start value for the random number generator itself is chosen randomly, and different evaluations with identical input parameters lead to different results.

Simulation Category

You can select the following calculation methods for generating normally distributed random numbers:

- 01 Structurized Monte Carlo with Box-Muller Alg. for Gen. NDRN

- 02 Structurized Monte Carlo with Tree Method for Gen. NDRN

- 03 Structurized Monte Carlo with Strata-Gems Alg. for Gen. NDRN


Simulation Runs

This is the number of simulation runs (random walks) for the Monte Carlo simulation.

**Note:**

A higher number of simulations leads to increased accuracy of the result, but also to a longer runtime of the simulation.

Time Grid Method

The time grid method is one of the methods used for creating a random walk time grid.

The following options are available:

Increment by Fixed Number of Days: Each step of the random walk covers the same number of working days (depending on the calendar assigned). The number of days is specified in the "Step Size" field.

Use Maturity Band Key Dates as Time Grid: One random walk step is created for each period of the maturity band that is used in the evaluation run.

In this case, the Step Size field is irrelevant because the length of the steps is variable and depends on the maturity band.

Dependencies:

The smaller the step size you choose, the more realistic the random walk you obtain, but also the longer the program runtime because more steps have to be created. Conversely, using a larger step size or selecting the "Maturity Band" setting leads to a more coarse random walk but improved performance.

Increment

The number of working days per step of a random walk.

Dependencies:

This setting is only relevant if you choose the time grid method Increment by Fixed Number

of Days. The smaller the step size you choose, the more realistic the random walk you obtain, but also the longer the program runtime because more steps have to be created. Conversely, using a larger step size leads to a more coarse random walk but improved performance.

Here, you make the settings for generating the random walks for the spot rates, which form the basis for calculating the simulated cash flows. These simulated cash flows then form the basis for the P/L distribution. A single profit or loss is the difference between the simulated cash flow and the reference cash flow.

When defining the final result key figure for the key figure category RACFARSCFaR from Simulation, also specify the confidence level and the CFaR method. In so doing, you specify how CFaR is calculated on the basis of the P/L distribution.

The confidence level specifies the probability (in percent) that the deviation of the actual future cash flow from the planned cash flow will not exceed Cash Flow at Risk.

The CFaR method controls how Cash Flow at Risk is calculated based on a simulated profit and loss distribution. The following settings are available:

CFaR Determination Based on Profit and Loss

The profits and losses are sorted by amount and valuated according to the confidence level.

CFaR Determination Based on Symmetrical P+L Distribution

Before counting, the profit and loss distribution is made symmetrical by including an additional entry with the opposite sign for each existing entry.

CFaR Determination Based on Normal Distribution Assumption

The standard deviation of the profits and losses is calculated, and CFaR is determined based on the standard deviation and the confidence level.

When defining the final result key figure for the key figure category RACFARCCFaR by Variance/Covariance, you make the following settings for calculating CFaR based on the delta positions or delta-gamma positions of the risk factors and based on the covariance matrix:

Volatility Type

Correlation Type

Calendar ID

Confidence Level

The confidence level specifies the probability (in percent) that the deviation of the actual future cash flow from the planned cash flow will not exceed Cash Flow at Risk.

**Note:**

If you want to define only one single record procedure and one final result procedure for your CFaR key figures, ensure that you create only one CFaR key figure hierarchy when defining your CFaR key figures. This is because you can assign to one single record procedure only the key figures of a key figure hierarchy. A key figure hierarchy comprises all key figures for a basic key figure.

Examples of Key Figure Hierarchies

|Key Figure for Key Figure Category RABB|Key Figure for Key Figure Category RAB06|Key Figure for Key Figure Category RACFPOS|Key Figure for Key Figure Category RACFPL|Final Result Key Figure|
|---|---|---|---|---|
|Example 1| | | | |
|BKCFAR|CFAR|CFARRP|CFARPL|CFAR_SIM|
|BKCFAR|CFAR|CFARRP| |CFAR_VAR|
|Example 2| | | | |
|BKCFAR1|CFAR2|CFARRP2|CFARPL2|CFAR_SIM_2|
|BKCFAR1|CFAR3|CFARRP3| |CFAR_VAR_2|


- 2. Define Single Record Procedure and Final Result Procedure


- a. Enter an ID (with a maximum of ten characters) for the single record procedure and choose Create.
- b. Enter a description for the single record procedure.
- c. Enter a filter.

The filter defines which financial objects are evaluated.

- d. The Real-Time Update upon Change of a Deal indicator is not relevant for CFaR key figures.
- e. Enter a key and a description for the final result procedure and assign the single record procedure.

Assign a portfolio hierarchy.

- f. Save your entries.
- g. Assign key figures to the single record procedure.


All nonassigned key figures are displayed.

Choose the first key figure. Then assign the other key figures that have not yet been assigned.

**Note:**

You can only assign key figures belonging to the same key figure hierarchy (key figures of one basic key figure).

- h. Assign the key figures for the final result procedure.
- i. Save your entries.


- 3. Define Initial Layout

The CFaR key figures are displayed in the Analyzer Information System using an initial layout that you define by specifying the sequence in which the key figures calculated are displayed. For this, you use the new areas Cash Flow at Risk; Maturity Band and Cash Flow at Risk; Risk Hierarchy in the function "Define Initial Layout" (transaction S_KFM_86000129).

- 4. In the function Define Formulas for AIS (transaction AIS_FORMULA_DEF), you also have the option of using the calculated key figures as the basis for defining your own key figures, which are then also displayed in the Analyzer Information System (AIS).


See also:Evaluations Using the Results Database and Hierarchies of Key Figure Categories

**Features**

If you want to display the AIS, you need to perform the following steps:

- 1. Update Market Data
- 2. Determine Single Records (transaction RAEP1)

Start this transaction to calculate the CFaR single record key figures.

- 3. Determine Final Results (transaction RAEP2)

Start this transaction to calculate the CFaR final result key figures.

See also:Evaluations Using the Results Database

- 4. Display CFaR Key Figures in the AIS (transaction AIS_STDREP)


Enter the portfolio hierarchy, a particular portfolio hierarchy node if applicable, the key date, and the initial layout. The List Viewer (ALV) is used to display the results. If you have created display variants for the List Viewer, you can enter them in the ALV Layout of the Analyzer Information System.

Execute the program.

In the upper part of the screen, the key figures are aggregated over all periods and risk factors for each node of the portfolio hierarchy. By selecting a node, you display in the lower part of the screen the cash flows and Cash Flow at Risk for each period of that selected node. By selecting a specific period, you display Cash Flow at Risk of the period for each risk factor (= currency).

You can use the functions of the Analyzer Information System to display the single records, the calculation base data, and so on.

See also:Analyzer Information System

###### CFaR in the Results Database

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Cash Flow at Risk (CFaR) > CFaR in the Results Database | L5 | trm03 p.52 | loio `89f15c53a618cc5de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/89f15c53a618cc5de10000000a4450e5.html?locale=en-US)

You can calculate Cash Flow at Risk for the results database and save it there. Cash Flow at Risk is then displayed using the Analyzer Information System (transaction AIS_STDREP).

###### CFaR Single Value Analysis

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Cash Flow at Risk (CFaR) > CFaR Single Value Analysis | L5 | trm03 p.67 | loio `0b0a5a5380687e0de10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0b0a5a5380687e0de10000000a4450e5.html?locale=en-US)

Use

You use this function to calculate Cash Flow at Risk online.

You can calculate the key figures for a portfolio hierarchy or for a specific portfolio hierarchy node as well as for a specific amount of financial objects (selected using different characteristics) independently of the portfolio hierarchies.

**Prerequisites**

See also:CFaR: Customizing, Master Data, and Market Data

**Activities**

- 1. Call up the function in the Market Risk Analyzer application menu under Information System Cash Flow at Risk CFaR Single Value Analysis (transaction RMC0).
- 2. Select the mode in which you want to perform the program:

CFaR Type

The evaluation parameters for calculating CFaR are taken from a CFaR type defined in Customizing.

If you select this mode, select first the Cash Flow at Risk type. Specify also the maturity band, the risk hierarchy (as well as any special risk hierarchy node), and the evaluation currency.

CFaR Key Figure

The evaluation parameters for calculating CFaR are taken from a CFaR key figure defined for the results database (transaction AFWKF_RA).

Select a key figure with the key figure category RACFARCCFaR by Variance/Covariance or RACFARSCFaR from Simulation Method.

The settings Evaluation Type, Maturity Band, Risk Hierarchy, and Currency are taken from the key figure definition.

CFaR Key Figure, Overwrite Settings

Similar to the option CFaR Key Figure. The settings Evaluation Type, Maturity Band, Risk Hierarchy, and Currency are taken from the key figure definition. However, you can change these settings on the selection screen.

- 3. On the Characteristics tab, you can use various characteristics from a broad range to select the financial objects to be analyzed.


**Example:**

Company Code

Business Partner

Transaction

Product Category

Product Type

Position Currency

Trader

...

- 4. On the General Selections tab, you can restrict the selection of transactions to be analyzed by specifying the portfolio hierarchy and a portfolio hierarchy node.
- 5. Execute the program. The system calculates the desired key figures and displays them. The system does not store the key figures on the database.


CFaR and the cash flow are displayed aggregated across all selected financial objects for the individual periods of the maturity band as well as for the entire period.

By selecting a period and then choosing the Toggle Transaction View <-> Aggregated pushbutton, you switch to the display screen showing the key figures at the level of the individual transactions.

If you choose the Calculation Base pushbutton, the system displays the exchange rates used in the calculation.

If you choose the Select Node in Risk Hierarchy pushbutton, you can display the key figures for a specific currency.

For CFaR by variance/covariance, you can display the delta/gamma positions determined.

For CFaR from Monte Carlo simulation, you can display the random walks (by choosing the Display Random Walks pushbutton) and the profits and losses determined (by choosing the P+L Distribution pushbutton).

**More Information**

Variance/Covariance Approach for CFaR

Structurized Monte Carlo for CFaR

**CFaR in the Results Database**

##### Gap Analysis

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis | L4 | trm03 p.69 | loio `fb01c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fb01c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

Unlike NPV analysis and value-at-risk analysis, where risks are depicted using NPVs and future values , in gap analysis position and maturity volumes , cash flows, and liquidities are analyzed on key dates or in periods. The gap positions, interest rate risk, currency risk, and liquidity risk that are disclosed in this way are then displayed.

For interest rate risk, you are able to highlight, for example, the fixed interest rate gap position in a maturity band for any currency by means of the following template:

[figure TRM03-F053 - For interest rate risk, you are able to highlight, for example, the fixed interest rate gap position in a maturity band for any currency by means of the following template:]

In the closed fixed-rate block, there is no risk because the product interest rates of the counterparties are not affected by changes in the market interest rate. Hence the closed interest result is not affected. In the closed variable-rate block, it is assumed that the changes to the interest rate of the items, which result from changes in the market interest rate, affect both sides, meaning that the

final net interest income is unchanged in this block too.

Therefore, the actual risk is in the area of the gap; in the area of the asset-side gap in this example. If, for example, the interest calculated for the variable-rate liabilities increases as a result of increases in the market interest rate, then you expect a decrease in the net interest income because the lending terms cannot be adjusted in line with the changes in the market rate due to the fixed-rate agreement.

**Features**

Gap analysis enables you to do the following:

Depict the interest rate risk as a possible negative deviation of the net interest income per period from the expected net interest income per period.

Depict key date-based and period-based position volumes, or key date-based maturity volumes in relation to their interest commitment or capital commitment, fixed-rate cash flows, and incoming payments and disbursements of liquidity.

Depict gap positions as a comparison of the volumes of asset and liability positions, and maturity volumes, as well as incoming payments and disbursements of cash flows or liquidity flows.

Analyze positions, maturity, and cash flows from fixed-rate items for any subportfolio on a daily basis.

Use scenarios to depict the net interest income for old transactions.

Use due date scenarios and forwards (for example, floaters, the variable side of swaps and FRAs) to take into account variable items that do not have fixed-rate periods (demand deposits and savings deposits).

Use due date scenarios to take into account non-interest items that do not have a fixed-rate period (for example, equity, provisions, land and buildings).

Take into account optional-like interest instruments with the underlying or delta-weighted underlying (for example, forward swaps for swaptions, fictitious bonds for OTC interest options, options on futures).

Display results distributed over time periods, which can be subdivided into any time unit, for example, day, month, quarter, half-year and year.

###### Position Evaluation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis > Position Evaluation | L5 | trm03 p.70 | loio `0a02c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0a02c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

The development of asset and liability items from both the on-balance sheet and off-balance sheet areas is compared in the position evaluation. You are able to examine the effect of interest rate changes on the variable side opposite the fixed interest rate gap, and the risks and opportunities arising from this, for the respective maturity band date.

You can use the Commitment indicator to control whether only fixed rate items (commitment indicator is set to Interest Commitment ) or also the variable rate items (commitment indicator is set to Capital Commitment ) are to be included in the position evaluation.

You can find the Commitment Indicator in gap analysis/ALM simulation by choosing Settings Data Relevant for Display.

****Note:****

Note that setting the Commitment Indicator affects not just the position evaluation columns but also the maturity evaluation columns .

**Features**

The system differentiates between the key date position evaluation, and the average position evaluation. In the key data position evaluation, the positions are shown for a particular key date (maturity band date), whereas in the average position evaluation the average position is displayed. The average balance refers to the period of time between two sequential date values in the maturity band. If you choose a daily maturity band, then the key date position and average position will be the same.

**Example:**

Term of the transaction: 11/01/03 – 11/15/03

Volume: 1,000,000

|Maturity band date|Key date position|Average position|
|---|---|---|
|11/01/03|1,000,000|1,000,000|
|11/30/03|0|1,000,000 x 13/29 = 448,275.86|


The positions are displayed in the position evaluation with the product interest rates contracted in the past, and the respective opportunity interest rates . The static interest rate can be displayed instead of the contracted product interest rate. The interest rates displayed are volume-weighted interest rates. In another column, the system displays the gap respective to each date of the maturity band date .

Premium/Discount

In position evaluations, the premiums and discounts associated with loans are handled in the same way as any other positionforming instruments. In the calculation of the average position, premiums and discounts are accrued across the relevant time period. You can display either the net discount or gross discount ( Display premium/discount indicator in the ALM valuation type). In the net display, the repayment amounts are adjusted automatically by the amount of the discount/premium. In the gross display, the repayment amounts are shown fully, and the adjustment takes place in the individual display of the premium/discount on the other side of the balance sheet respectively.

Since the premium or discount also has an impact on the future interest payments, you can make a setting in Customizing to determine whether the positions and the premium or discount amount are shown together with a nominal interest rate or a static interest rate.

Key date position evaluation

Key date positions are calculated for lending and borrowing business from the principal payments of the transactions selected from the portfolio hierarchy. Interest payments are taken into account.

The principal payments are added together, starting from the latest principal payment and going up to the respective key dates in the maturity band. The totals on the key dates form the key date positions.

Using the nominal product interest rate for each principal payment, an average product interest calculation can be assigned to each position. This is displayed for each key date, and is weighted by volume.

The key date gap is the difference between the asset and liability-side key date position.

Average position evaluation

As key date positions can be calculated on a daily basis, it is possible to calculate to the day average positions for each maturity band date. Using nominal interest rates, you can calculate average interest income or expense for each average asset side or liability side position.

**Example:**

For an example of the gap analysis/ALM simulation evaluations, choose the following links:

Fixed interest loan with discount

**Fixed-Term Deposit**

Plain vanilla interest swap

Account as a variable transaction

###### Outflow Evaluation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis > Outflow Evaluation | L5 | trm03 p.72 | loio `0d02c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0d02c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

The outflow evaluation is particularly useful when you are simulating the structure of your balance sheet and you want to view the changes in the net interest income that result from the replacement of old fixed-rate transactions by new fixed-rate transactions. In a low interest rate phase, for example, this could illustrate to what extent pressure on the interest spread can be expected if asset side transactions from high interest rate phases expire and are to be replaced by transactions with lower interest rates. This is especially important if, on account of this "replacement effect," an imbalance occurs between the asset and liability sides, meaning there are greater outflow gaps.

**Features**

In the outflow evaluation, capital outflows and outflow gaps are shown for each defined maturity band date. Capital outflows are shown with product interest rates contracted in the past and/or static interest rates, as well as with the respective opportunity interest rates.

In the outflow evaluation, only those flows are taken into account that lead to a change in the nominal capital of a transaction (repayments, disbursements), which means that outflow volumes result from the position changes for each maturity band date. Interest payments, fees and so on are not included.

You use the Commitment Indicator to control whether only the interest commitment of the transactions (commitment indicator Interest Commitment) or the capital commitment of the transactions (commitment indicator Capital Commitment) is to be taken into account.

You can find the Commitment Indicator in gap analysis by choosing Settings Data Relevant for Display .

**Note:**

Note that setting the Commitment Indicator affects not just the outflow evaluation columns but also the position evaluation columns.

Outflow volumes

Outflow volumes are calculated for both the asset and liability sides for each maturity band date determined by the maturity band you selected.

Outflow interest calculation

The system assigns outflow interest rates to the calculated outflow volumes. These interest rates are product and opportunity interest rates. The static interest rate can be displayed instead of the product interest rate. The interest rates displayed are volume-weighted average interest rates.

Outflow gap

In accordance with the defined maturity band structure, outflow gaps are calculated as the difference between the asset side and liability side outflows per maturity band date.

**Examples**

For an example of the gap analysis/ALM simulation evaluations, choose the following links:

Plain Vanilla Interest Rate Swap

**Fixed-Term Deposit**

Fixed-Rate Loan with Discount

Account as a Variable Transaction

###### Cash Flow Evaluation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis > Cash Flow Evaluation | L5 | trm03 p.73 | loio `1002c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1002c55368511d4be10000000a174cb4.html?locale=en-US)

Use

In addition to being examined from a position and outflow point of view, interest risk can be depicted as calculated cash flows broken down into currencies or aggregated across several currencies. The volume outflows/inflows and the interest payments according to the interest commitment of the underlying items, all flow into the displayed cash flows. Interest rates are not shown.

Within gap analysis, this evaluation also depicts the currency exposure for individual currencies or currency blocks. The evaluation covers both the angle of interest rate risk control and currency risk control.

In the cash flow evaluation, incoming and outgoing payments, as well as payment surpluses from cash flows, are shown. In contrast to liquidity analysis however, here only interest-linked cash flows are shown.

###### Liquidity Evaluation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis > Liquidity Evaluation | L5 | trm03 p.73 | loio `1302c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1302c55368511d4be10000000a174cb4.html?locale=en-US)

Use

In contrast to the cash flows examined as part of interest change risk and currency risk, in liquidity evaluation the analysis always starts from the capital commitment. This means that this evaluation includes the interest and capital payments of the corresponding capital commitment of each of the underlying transactions.

Capital payments, which in reality do not flow, and which only serve as the basis for interest calculation for certain transactions (for example, nominal capital with FRAs or in the case of swaps without a capital swap), are never included in liquidity evaluation. They are, however, displayed in other evaluations.

In liquidity analysis, incoming and outgoing payments, payment net surplus positions, and cumulated payment net surplus positions from liquidity flows are all displayed. Interest rates are not.

###### Report Type GAP

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis > Report Type GAP | L5 | trm03 p.74 | loio `5613da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5613da531198434de10000000a174cb4.html?locale=en-US)

Features

With the report type GAP, you can calculate and represent the following predefined key figures (basic key figures, derived key figures), and other key figures derived from them using formulas.

Basic key figures

The basic key figures of the report type can be seen in the following table. Every combination per line of basic figure, balance sheet side, commitment type and currency represents a key figure (e.g. average position – liability – interest commitment – transaction currency).

|Basic Figure|Balance Sheet Side|Commitment Type|Currency|
|---|---|---|---|
|Average position (AP) Key date position (KP) Outflow|Assets Liabilities|Capital commitment Interest commitment|Transaction currency Display currency|
|Cash flow Liquidity|Assets Liabilities| |Transaction currency Display currency|
|Volume-wtd. product interest rate AP Volume-wtd. product interest rate KP Volume-wtd. product interest rate outflow|Assets Liabilities|Capital commitment Interest commitment|Transaction currency Display currency|


Derived key figures

Basic key figures with the base figure product interest rate weighted by volume are only of technical significance. These key figures were included because they are more suitable key figures than the interest rates (interest rates can’t be added). The interest rates can be calculated as derived key figures from the interest rates weighted by volume:

Interest rate = interest rate weighted by volume / volume

Key figures derived from basic key figures and derived key figures using formulas

##### Gap Analysis and Simulation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis and Simulation | L4 | trm03 p.74 | loio `7713da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7713da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use gap analysis to obtain an overview of the cash flows and capital positions resulting from your company’s investments.

Using the simulation, you can create a long-term forecast of your company’s financial development based on your individual forecasts.

###### Saving Gap Evaluation Results

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Gap Analysis and Simulation > Saving Gap Evaluation Results | L5 | trm03 p.74 | loio `dbfdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dbfdc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

When you run ALM simulation, you have the option of saving the results from gap evaluations. You can then display the saved results at a later point in time.

You can use a report to update gap evaluation results that have already been saved. This is useful from a performance point of view if only one or a few portfolio hierarchy nodes have been affected by changes.

If you no longer require the gap results you saved, you can delete them using a report.

**Activities**

Saving gap results

- 1. Start the ALM simulation. For general information about using ALM simulation see Executing Analysis/Simulation .

- 2. Choose the Processing tab page.
- 3. Enter the value 1 or 2 in the field Processing Mode.

- 1 = Calculate, save and display results
- 2 = Calculate and save results


- 4. Enter a short description. The Save ID is assigned automatically by the system when the gap results are saved.
- 5. Choose Execute .


**Note:**

You can display the saved results by choosing processing mode 3 Display saved results. Then enter the save ID in the relevant field. If you do not know the save ID, you can search for it using the short description.

Updating gap results

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Tools Gap Results Update Results of Gap Analysis .
- 2. Enter the old save ID, under which the results were saved, for the results you want to update.
- 3. Fill the fields View and Portfolio Hierarchy.
- 4. Now choose the Portfolio Hierarchy Node for which you want to update the gap results.
- 5. Enter a short description ( New Text for Saved Results field).
- 6. Choose Execute.


Deleting gap results

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Tools Gap Results Delete Results of Gap Analysis .
- 2. Choose the save ID under which the data was saved that you want to delete.
- 3. Choose Execute.
- 4. Check the log.


- 5. Choose Back.


- 6. Set the indicator Update Run.
- 7. Choose Execute.



Displaying the saved gap results (header information)

You can display the header information of saved gap results. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Tools

Gap Results Display Results of Gap Analysis (Header Information) . You will then see the following information:

|SaveID|Short name|View|PF hier.|PH node|Evaldate|Eval|Gap type|Old ID|Updated|Entered by|Entry on (date)|Entry at (time)|
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|1|Europe|001|202|1|10/01/00|500|500|0| |Smith|10/01/00|12:54:30|
|2|Fixedterm deposit EUR|001|202|63|10/01/00|500|500|1| |Smith|10/15/00|14:35:35|


**Note:**

Header information for deleted gaps results is no longer shown when saved gap results are displayed.

##### Asset/Liability Management

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management | L4 | trm03 p.76 | loio `17fec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/17fec5536a51204be10000000a174cb4.html?locale=en-US)

**Purpose**

The purpose of the balance sheet simulations in the component Asset/Liability Management (IS-B-SA-ALM) is to examine, from a strategic point of view, how profitability is affected by various business developments, and interest, currency and volatility scenarios.

Based on the portfolio hierarchies you set up in the system, you can use scenarios to determine the net interest income per period, and at any aggregation level.

**Implementation Considerations**

To be able to use the functions of the Asset/Liability Management (IS-B-SA-ALM) component, you need to have made the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer

Asset/Liability Management .


**Features**

The ALM module includes functions for gap analysis, and flexible methods for simulating new business. In order to analyze how the structure of your balance sheet may look in the future, you have to make certain assumptions about future business, and reflect these assumptions in the SAP system. The generated new business is stored separately in the data pool as single transactions. This enables you to plan new business volumes at profit center level, and distribute these new transactions to a portfolio structure, which is subdivided into balance sheet items. The ALM architecture allows you to integrate decentralized planning into balance sheet-based overall bank controlling. The following simulations are supported:

[figure TRM03-F057 - Simulated transactions are transactions that the system generates automatically based on system settings. Fictitious transactions are defined by the user.]

Simulated transactions are transactions that the system generates automatically based on system settings. Fictitious transactions are defined by the user.

The following functions are available in the ALM component:

In addition to gap analysis, the system also contains other evaluations for analyzing currency liquidity, and net interest income. These are:

Average position evaluation

Key date position evaluation

Maturity evaluation

Cash flow evaluation

Liquidity evaluation

###### Simulation and Planning

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning | L5 | trm03 p.78 | loio `4afec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4afec5536a51204be10000000a174cb4.html?locale=en-US)

The gap analysis evaluations form the basis of the ALM simulation.

Average position evaluation

Key date position evaluation

Maturity evaluation

Cash flow evaluation

Liquidity evaluation

In addition to gap evaluation, the following evaluations are available in ALM:

**Currency Liquidity Evaluation**

Net interest income evaluation

###### ALM Simulation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation | L6 | trm03 p.78 | loio `fffdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fffdc5536a51204be10000000a174cb4.html?locale=en-US)

ALM simulation contains the following functions:

Simulation of new transactions and their depiction in the evaluations

Application of explicit due date scenarios (can be used to depict prepayments, for example)

Application of scenarios and scenario progressions (in the analysis itself, you can switch between the various scenarios)

Calculation of the net interest income

Calculation of exchange rate gains/losses

Saving of simulated transactions

Deletion of the results of the simulation

Depiction of results in graphical form

You can use the following functions to simulate new business:

Standard simulation

Standard simulation enables you to close existing gaps quickly and easily. In the key date evaluation, you can also balance you balance sheet completely.

Individual simulation

You can use individual simulation for planning growth.

Creation of fictitious transactions

This function enables you to check the effect of a hedge on your risk, for example.

If these simulation options do not meet your needs, you can also create fictitious generic transactions and include them in ALM simulation.

###### Standard Simulation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Standard Simulation | L7 | trm03 p.79 | loio `b7fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b7fdc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The starting point for a standard simulation is the asset or liability-side gap identified in gap analysis. Using standard simulation you are able to close this gap either entirely, or up to a particular percentage. To achieve this, the system automatically generates new transactions in accordance with specified criteria. Standard simulations therefore enable you to form views of possible results

quickly and easily.

**Features**

The following simulation categories are currently available in standard simulation for closing the identified gaps:

Close average position gaps with fixed-term deposits

Close average position gaps with forward rate agreements

Close key date position gaps with fixed-term deposits

Close key date position gaps with forward rate agreements

Close maturity gaps with fixed-term deposits

Close cash flow gaps with fixed-term deposits

Close liquidity gaps with forward exchange transactions

The simulation category describes the fixed procedures in the system that are used for standard simulation.

The simulation category close liquidity gap with forward exchange transactions enables you to close the liquidity gap for individual currencies and hence control currency risk. When you start the simulation you enter the target currency. You cannot close the liquidity gaps of the target currency.

When you run standard simulation, you can close only the gaps shown in the evaluation that you are performing at the time of simulation. The system offers only those simulation categories that you can use in the current evaluation.

After standard simulation has been run, the results of the simulation are also shown in the other gap/ALM evaluations. If, for example, the position gap is 100% closed, then the net interest income shown in the net interest income evaluation can serve as an indication of possible revenue if all interest commitment risk is excluded.

**Activities**

- 1. Start the ALM simulation. For further information about running ALM simulation see Executing Analysis/Simulation .

- 2. Choose the tab page of the evaluation for which you want to run standard simulation.
- 3. Choose ALM Simulation Start Standard Simulation or or Standard Simulation .
- 4. Choose one of the simulation categories offered by the system. Enter the simulation parameters required by the simulation category.
- 5. Choose Continue .



Example

You want to close a liquidity gap that exists in USD.

Choose the tab page Liquidity Evaluation.

Choose Settings Data Relevant for Display or or Data Relevant for Display . Select Transaction Currency , and choose USD as the transaction currency.


Choose Continue .

Choose ALM Simulation Start Standard Simulation or or Standard Simulation .

The system suggests the simulation category close liquidity gap with forward forex transactions . Enter values for the following simulation parameters: Simulation, Simulation Basis, Valuation Rule, and Quota in Percentage . Enter EUR as the Target Currency .

Choose Continue .

Result

All liquidity gaps in USD were closed. The liquidity gaps in target currency EUR cannot be closed using simulation category Close liquidity gaps with forex transactions.

###### Complete Balancing

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Standard Simulation > Complete Balancing | L8 | trm03 p.80 | loio `eafdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eafdc5536a51204be10000000a174cb4.html?locale=en-US)

Use

You use this function to balance your balance sheet by making fictitious postings to virtual accounts.

This process is part of the standard simulation function, which simulates the closing of the asset or liability gap. Complete balancing takes into account the change of net income for each maturity band. This means that the function provides you with a comprehensive view of your balance sheet, which includes asset, liability and equity balancing accounts.

You can currently use complete balancing in the key date evaluation.

**Integration**

The complete balancing function is part of standard simulation.

**Prerequisites**

To use the complete balancing function, you must first create three new (virtual) accounts:

Asset balancing account

Liability balancing account

Current period earnings

You only need to make additional Customizing settings if you want to define where these accounts are to be placed in the portfolio hierarchy. For more information see the section of the Implementation Guide (IMG) under Asset/Liability Management (ALM)

Complete Balancing Assign Accounts for Complete Balancing to the Portfolio Hierarchy . If you do not make any settings in Customizing, then the system inserts the three accounts under the lowest root node.

**Activities**

Start the ALM simulation.

Choose the Key Date Position tab page, and then choose Standard Simulation.

Set the Complete Balancing indicator and start the standard simulation.

For more information, see Standard Simulation or Executing Analysis and Simulation.

The system then does the following:

Closes asset and liability gaps (normal standard simulation)

Calculates the difference (net gap adjustments) between revenue (actual and simulated) and expense (actual and simulated) for each maturity band

Adds the net gap adjustments that were calculated to the simulated volume of assets and liabilities

In a continuous process, calculates interest earnings or expense on net gap adjustments

If, for a particular maturity band date, the net gap adjustments are a gain, then the system posts this gain to the asset balancing account, and to the current period earnings account.

If, for a particular maturity band date, the net gap adjustments are a loss, then the system posts this loss to the liability balancing account, and deducts this amount from the current period earnings account.

Recalculates the simulated interest rate for each maturity band date. The rate is changed by the new asset and liability volumes.

###### Fictitious Transactions

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Fictitious Transactions | L7 | trm03 p.82 | loio `23fec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/23fec5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Based on the evaluations in gap analysis and ALM simulation, you can create fictitious transactions for each portfolio hierarchy node to control risks and results. These can be saved later. By creating a fictitious transaction, you can, for example, check the effect of a particular hedge on risk before you actually conclude this transaction.

**Features**

The following transaction categories are currently available for creating fictitious transactions:

Forward exchange transaction

**Fixed-Term Deposit**

Swap

Swaption

Currency option (standard)

Currency barrier option (simple barrier option)

Cap

Floor

The effects that fictitious transactions have on the results of gap analysis and ALM simulation are subsequently shown in all evaluations.

If the options available in the Fictitious transactions function in ALM simulation do not meet all your requirements, you can also create fictitious generic transactions .

###### Individual Simulation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Individual Simulation | L7 | trm03 p.82 | loio `14fec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/14fec5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Individual simulation enables you to plan for growth for each portfolio hierarchy node of any portfolio hierarchy. In this way, you can simulate, for example, an increase in the balance sheet total, or a decrease (negative growth planning) in certain product groups.

Individual simulations are defined by means of a planning variant, so to be able to run them you need to specify a planning variant before you start the simulation. The planning variant allows you to save the parameters for the new transaction simulation. To be able to run an individual simulation, in the planning variant you need to define maturity band-independent parameters, such as the transaction category and the interest calculation method, as well as maturity band-dependent parameters, for example, the term and volume of the transactions you want to simulate. You can define the maturity band-dependent parameters for the asset side separately from those for the liability side. Hence, for each portfolio hierarchy node, you can plan asset and liability volume separately.

You can use the following transaction categories for individual simulations:

Bond

Installment loan

Annuity loan

Floater

Zero bond

Individual simulation enables you to carry out relative as well as absolute growth planning. If you carry out relative growth planning, you need to define in the maturity band-dependent parameters the percentage growth of the position at a particular maturity band date. If you plan for absolute growth, a distinction is made between planning the absolute total volume (here you need to specify the planned absolute position for the relevant maturity band date) and planning the absolute volume of new business.

Growth planning using individual simulation (relative and absolute total volume) is based on the average actual position, or the actual position + saved simulated transactions.


|Maturity Band Date|Term in Days|Volume|Margin|
|---|---|---|---|
|12/01/01| | | |
|06/30/02| | | |
|12/30/02| | | |
|06/30/03|180|5,000,000|0.5|
|12/30/03| | | |


The maturity band that was used analyzes a period of time, meaning a transaction with a term of 180 days is to be planned, which in the time period from 01/01/03 to 06/30/03 leads to an average total volume of 5,000,000.

You can plan for both positive and negative growth. In negative growth planning, the actual position forms the lower limit. This means that an existing transaction cannot be set as due for payment by negative growth planning.

[figure TRM03-F062 - You can plan for both positive and negative growth. In negative growth planning, the actual position forms the lower limit. This means that an existing transaction cannot be set as due for payment by negative growth planning.]

**Relative growth planning**

The following formula applies for both positive and negative growth:

goal (t i+2) = max ( (actual+simulated)t i+1 + growth rate t i+2 x (actual+simulated)t i+1 , (actual + simulated) t i+2); with growth rate I[-1 , 1]

expressed differently:

goal (t i+2) = max ( (actual+simulated)t i+1 x (1+ growth rate) t i+2 ), (actual+simulated)t i+2); with growth rate I[-1 , 1]


|Time|Relative Growth Rate|Volume (Actual)|Volume (Actual + Simulated)|Planned New Business|
|---|---|---|---|---|
|ti| | | | |
|ti+1| |120| | |
|ti+2|+ 10%|100|132 (120+10%)|32|
|ti+3|+ 20%|160|160 (132+20%=158.4)|No simulation because the actual volume is already larger than 158.4|


Positive growth at time point (ti+2) means growth (by the growth rate) in the position of (ti+1).

**Note:**

It is possible to plan for absolute growth in empty portfolio hierarchy nodes.

###### Editing Planning Variants

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Individual Simulation > Editing Planning Variants | L8 | trm03 p.84 | loio `aefdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aefdc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The planning variant defines a certain combination of parameters for the transactions you wish to use in your simulation. You can define a different set of parameters for each portfolio hierarchy node.

The planning variant is used in the individual simulations. In addition, you can also use the planning variant to assign an explicit due date scenario to each portfolio hierarchy node.

**Prerequisites**

Before you can create a planning variant, you need to have already defined at least one view, one portfolio hierarchy, and created an absolute maturity band.

**Procedure**

To create, change or delete planning variants, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Simulation/Planning Edit Planning Variant .

Fill the fields Planning Variant, View and Portfolio Hierarchy in order to create a planning variant, or choose an existing planning variant that you want to change, delete or display.


You can use only absolute maturity bands in the planning variant.

If you use different maturity bands in the planning variant from those that you use in ALM simulation, choose this link to obtain further information: Using Different Maturity Bands.

Choose Create, Change, Display or Delete.

To store a description of the planning you have carried out directly in the planning variant, choose Change Note.

Choose Planning Parameters. You can now enter your planning for each portfolio hierarchy node, or for multiple portfolio hierarchy nodes at the same time. Here you are also able to assign a due date scenario to the individual portfolio hierarchy nodes.

By double clicking on the relevant portfolio hierarchy node, you can select the node for which you want to carry out planning. If you want to edit more than one portfolio hierarchy node at one time, select the relevant portfolio hierarchy nodes and choose Process the selected nodes. You can select more than one portfolio hierarchy node by holding down the control key and choosing on the relevant nodes.

Explicit due date scenario

The due date scenario you specify here is only used for actual transactions or actual transactions + saved simulated transactions of the portfolio hierarchy node.

Gross/net display

You use this indicator to define how the system is to display results in the gap analysis and ALM simulation when you use an explicit due date scenario.

Maturity Band-Independent Parameters tab page

Enter the following transaction data for planning new business:

Transaction category

Valuation rule

Interest calculation method

Evaluation Currency/Transaction Currency indicator

In the planning parameters, you can define whether the simulation is to be made on the basis of an absolute or relative volume, and whether the determination of the new transaction interest rate is to be carried out using a spread or elasticity.

By entering a time lag, you can define as of when the interest conditions for the simulated transaction are to be adjusted to the valid market conditions.

Maturity Band-Dependent Assets and Liabilities tab pages

Here you define the transaction term, and if applicable, the growth rate, transaction currency, margin, and so on for the assets or liabilities, taking into account the maturity band-independent parameters you have already defined.

Elasticity tab page

On the Elasticity tab page, you can enter values only if, in the tab page Maturity Band-Independent Parameters, you have set the indicator Spread or Elasticity to Elasticity.

Define which interest rate (indicator Entry of Product Interest Rate) is to be used as the initial interest rate in the calculation of the new transaction interest rate. Instead, you can define that the system is to determine the initial interest rate using current market rates plus or minus a specified spread (indicator Spread: Product Rate from Market Rate).


If you fill field Entry of Product Interest Rate, the system always applies the rate you specify here. If you want to let the system calculate the initial interest rate, leave field Entry of Product Interest Rate blank. If you leave both fields blank, the system takes the current market rate as the initial interest rate.

Define elasticities for both rising and falling market rates.

You enter values for asset transactions and liability transactions separately.

Market Price Weighting tab page

You use the market price weighting method to influence the calculation of the new transaction interest rate for individually simulated transactions per portfolio hierarchy node.

In the case of simulated transactions with an assumed repayment pattern, for example, you may not want the entire term of the transaction to influence the process in which the system determines the interest rate. Instead, you could opt to make the process dependent on the repayment pattern of the transaction, and calculate the product interest from the yield curve by weighting certain reference interest rates. The new transaction interest rate is then the weighted average of several reference interest rates.

Enter the reference interest rates together with their weighting and the +/- sign.

In addition, you are also able to link the process in which the interest rate is determined for new business not only to the development of interest rates, but also to various indexes. It is possible to take indexes into account when determining interest rates only if the indicator spread or elasticity is set to elasticity in the maturity band-independent parameters.

Store the reference interest rates, or the index and the index type, with the weighting and +/- sign.


For reference interest rates, note that the only information the system reads from the reference interest rate is the term. To determine the interest rate that flows into the market price weighting, the system uses the following information: term, display or transaction currency and the interest rates from the yield curve type stored in the evaluation type.

Example:

Stored reference interest rate: 3 months euribor

Weighting: 20% (The total weighting must always add up to 100%)

In the maturity band-independent parameters, the display currency was specified as the simulation currency.

Display currency: USD (you need to specify this when you run the ALM simulation)

3 month interest rate USD from the yield curve type: 3%

The 3% interest rate with a weighting of 20% is taken into account in the market price weighting.

RM Characteristics tab page

Here you specify the characteristic values of the transactions you want to be simulated.

Choose Delete Parameters to delete all planning parameters for a portfolio hierarchy node.


Choose Save.


Portfolio hierarchy nodes for which planning parameters or due date scenarios are stored are highlighted in color. Yellow indicates that this portfolio hierarchy node has been edited but the changes have not yet been saved. Green indicates that planning parameters or due date scenarios were stored for this portfolio hierarchy node and also saved.

###### Planning in Evaluation Currency or Transaction Currency

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Individual Simulation > Planning in Evaluation Currency or Transaction Currency | L8 | trm03 p.87 | loio `abfdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/abfdc5536a51204be10000000a174cb4.html?locale=en-US)

In the individual simulation, you can choose whether you plan new business in the evaluation currency or in the transaction currency. The following table explains the significance for the planning variant of the setting you make in the indicator for evaluation or transaction currency ( E/T Crcy ).

|Planning Basis|Evaluation Currency|Transaction Currency|
|---|---|---|
|Relative to total volume|The transactions are planned in the evaluation currency, meaning the existing actual transactions are converted into the evaluation currency, and then, for example, 10% new business is planned in the evaluation currency. It does not matter whether the evaluation currency has already existed on the portfolio hierarchy node as the transaction currency.|New business is planned in the transaction currency, meaning that each currency has a relative growth of 10%, for example. You cannot add new currencies here. Therefore you cannot maintain currencies in the maturity band-dependent parameters.|
|Absolute total volume|New business is planned in the evaluation currency, meaning that the existing actual transactions are converted into the evaluation currency, and then the system checks whether the actual position is less than the planned total volume. If this is the case, the difference is planned in the evaluation currency. It does not matter whether the evaluation currency has already existed on the node as the transaction currency.|New business is planned in the specified transaction currency. Example: USD 5m is to be planned. The current actual position in the portfolio hierarchy node is EUR 2m, USD 4m. You plan for USD 1m of new business. The euro transactions are left out of the planning completely. You can add currencies, meaning that you could also plan for FRF 3m. You can plan in only one currency for each maturity band date.|
|Absolute new business|New business is planned in the evaluation currency.|New business is planned in the transaction currency. For each maturity band date, you can plan absolute volumes of new business in any currency. However, only one currency is permitted for each maturity band date. It does not matter whether the currency already exists on the portfolio hierarchy node.|

###### Determining the Interest Rate for New Transactions

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Determining the Interest Rate for New Transactions | L7 | trm03 p.87 | loio `c3fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c3fdc5536a51204be10000000a174cb4.html?locale=en-US)

The determination of the respective new transaction interest rate for the transactions simulated by the system is governed by the yield curve current on the evaluation date ( current market data scenario) or the respective (reference) scenario/(reference) scenario progression. In the evaluation type, when you specify the yield curve type you are defining which yield curves the system is to use. If, in the evaluation type, you have stored different yield curve types for the ask and bid parts, then the system is able to take into account the ask/bid margin for the simulated transactions.

If you are using current market data and scenarios, forwards are used to determine the interest rates for new transactions whose terms have a start date in the future. If you are using scenario progressions, the system applies the interest rate that is valid at the term start of the transaction.

**Standard simulation**

The currency and term of the transactions, the market data, and the respective scenarios or scenario progressions that you entered on the tab page Market Scenarios when you started ALM simulation form the basis for the determination of the new transaction interest rate in standard simulation.

When you start standard simulation, you can choose whether it is to take place in only the current scenario or reference scenario progression, or in all scenarios or scenario progressions.

Only in the current scenario/reference scenario progression

Detail screen

If you are in the detail screen, the determination of the new transaction interest rate is based on the current scenario/scenario progression. The system shows the simulated new transactions only in this scenario/scenario progression.

Overview screen

If you are in the overview screen, the determination of the new transaction interest rate is based on the selected reference scenario/reference scenario progression. The system shows the simulated new transactions only in this reference scenario/reference scenario progression.

In all scenario progressions

Standard simulation is run for each scenario/scenario progression specified. The new transaction interest rate is determined separately for each scenario. The simulated new transactions are then displayed in all the scenarios/scenario progressions with the interest rates determined for the respective scenario/scenario progression.

The new transaction interest rate is calculated as follows:

New transaction interest rate = market interest rate determined +/- spread

**Note:**

The spread is dependent on the plus/minus sign. This means the system can also take into account negative spreads. If you enter a positive spread, then in the case of asset transactions the spread is added to the market interest rate. For liabilities transactions it is deducted from the market interest rate. If you enter a negative spread , for asset transactions it is deducted from the market interest rate. For liabilities transactions it is added to the market interest rate.

**Fictitious transactions**

When creating fictitious transactions, you can either enter a new transaction interest rate directly, or you can let the system suggest an interest rate, which you can overwrite if required.

The currency and term of the transaction, the market data and the respective scenarios or scenario progressions that you entered on the tab page Market Scenarios when you started ALM simulation, form the basis for the determination of the new transaction interest rate for fictitious transactions.

Detail screen

If you are in the detail screen, the determination of the new transaction interest rate is based on the current scenario/scenario progression.

Overview screen

If you are in the overview screen, the determination of the new transaction interest rate is based on the selected reference scenario/reference scenario progression.

**Individual simulation**

The calculation of the new transaction interest rate for the transactions generated in the individual simulation is influenced by several settings in the planning variant and in the tab pages Simulation and Market Scenarios in ALM simulation.

- I. Settings options in the tab page Simulation in ALM simulation:

You can use the Use of Planning Variant indicator to choose whether the individual simulation is to be run only for the reference scenario/reference scenario progression, or for all scenarios.

- II. Settings options in the tab page Market Scenarios in ALM simulation:


Market Data Selection indicator

You can choose whether the system is to use current market data, a scenario, or a scenario progression.

The Reference Scenario and Reference Scenario Progression indicators

You set these indicators for a scenario or scenario progression depending on how you set the Market Data Selection indicator.

III. Settings options in the planning variant:

- a) Settings in the tab page Maturity Band-Independent Parameters


Spread or Elasticity indicator

The Spread or Elasticity indicator specifies whether the new transaction interest rate is to be calculated on the basis of the market interest plus a spread, or taking into account elasticity.

The following applies for the Spread setting:

New product interest rate = market interest rate +/- spread

Opportunity interest rate = market interest rate

If you set the Spread or Elasticity indicator to Elasticity , you need to make additional settings on the Elasticity tab page.

Depending on the settings you have made, the system derives the market interest rate from the current market data, the reference scenario or the reference scenario progression.

E/T Crcy – evaluation currency or transaction currency indicator

Depending on how this indicator is set, the system uses either the market interest rates stored for the evaluation currency, or those for the transaction currency. If you choose Transaction currency you will need to specify the relevant transaction

currency in the maturity band-dependent parameters.

Time Lag and Time Unit indicators

These indicators define the time lag for adjusting the product interest rate to the respective valid market conditions.

- b) Settings on the Elasticity tab page


Indicators Entry of Product Interest Rate and Spread: Product Rate from Market Rate

If you want the system to take into account elasticity when calculating interest rates for the simulated transactions, you can either specify a product interest rate as the initial interest rate, or you can let the system determine an initial interest rate. If you let the system determine the initial rate, it is calculated using the current market rates, plus or minus the spread you specified.

**Note:**

When using interest rates calculated by the system, it is possible to take into account different initial rates, depending on the terms of the simulated transactions.

Indicators Elasticity – Rising Market Rates and Elasticity – Falling Market Rates .

You use these indicators to control to what extent changes in the market interest rate influence the product interest rate of the simulated transactions.

The product interest rate is calculated as follows:

New product interest rate = product interest rate + elasticity x market interest rate change

Opportunity interest rate = market interest rate

To retain the change in the market interest rate, new yield curves are generated for each date on which new business is planned. This means that even if the maturity band has, for example, 10 date entries, but new business was planned for 3 dates only, then the relevant market rates are calculated for these three dates, and between these rates the deltas are calculated.

To be able to understand more easily how the system calculated the new transaction interest rate for simulated transactions using elasticity, when you start ALM simulation you can request a log of elasticity (tab page Simulation , indicator Log of Elasticity) .

See the example:

Individual Simulation using Elasticity

b) Settings in the Market Price Weighting tab page

You can influence the market interest rate and the market interest rate change by means of the settings in the tab page Market Price Weighting .

Spreador Elasticity indicator set to Spread

In the case of simulated transactions with a repayment pattern, (for example, installment loans, annuity loans) you may not want the entire term of the transaction to influence the interest commitment. Instead, you could opt to make the process dependent on the repayment pattern of the transaction, and calculate the product interest from the yield curve by weighting certain reference interest rates.

Spreador Elasticity indicator set to Elasticity

If you use the setting Elasticity for determining the market interest rate change, you are able to include not only the development of the interest rate, but also the development of different indexes.

###### Executing Analysis and Simulation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Executing Analysis and Simulation | L7 | trm03 p.91 | loio `cffdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cffdc5536a51204be10000000a174cb4.html?locale=en-US)

Procedure

In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Simulation/Planning Start ALM Simulation .

- 1. Choose a View.
- 2. Choose a Portfolio Hierarchy.

If you want to analyze only one portfolio hierarchy node, on the Evaluation Parameters tab page enter the following information:

- 3. Choose a Date of Evaluation and a Horizon.
- 4. Choose an Evaluation Type.
- 5. Choose an ALM Valuation Type.
- 6. Choose a Maturity Band.
- 7. Choose an Evaluation Currency.
- 8. Specify whether you want the system to generate a detailed log.
- 9. In the Simulation tab page, enter all the information needed to include simulated transactions in the evaluation (position number and/or number of the simulation run), or to generate simulated transactions in the individual simulation (planning variant).

Note the following special considerations when selecting transactions. The pushbuttons Only Actual, Only Simulated, Insert Actual and All provide input help. The Position Number and Number of Simulation Run fields are then filled in accordance with your selection.

In order to run an individual simulation with predefined default settings, enter the name of the planning variant in the field Planning Variant. If this field is left empty, you can use standard simulation functions only.

Choose whether the simulation is to be run in the current scenario or reference scenario/reference scenario progression, or if it is to be run for all the specified scenarios/scenario progressions.

In addition, specify if you want to modify the planning variant, and whether the system is to generate a log of elasticity.

- 10. On the Market Scenarios tab page, set the Market Data Selection indicator.

In so doing, you define which market data the system uses first for the simulation of your transactions in ALM simulation. You can choose whether the system is to use current market data, a scenario or a scenario progression.

Based on how you set the Market Data Selection indicator, choose a scenario or a scenario progression.

You then choose the scenarios and the scenario progressions that you want to use in the gap analysis or ALM simulation in addition to the reference scenario or scenario progression.

It is then possible in gap analysis and ALM simulation to switch between the chosen scenarios or scenario progressions.

- 11. In the processing tab page, define how the system is to save the data from ALM simulation.


By setting the Processing Mode indicator, you define whether the system is just to display the results, or whether it should save them too.

In the Save ID field you enter an identification of the set of results that are to be saved. This ID is automatically assigned by the system the first time a simulation run is saved. You can use the field Save - Short Description to enter an additional description of the results.

- 12. In the Reporting tab page, you specify which evaluations the system is to run.
- 13. In the Characteristics tab page, you can enter characteristic values to specify which transactions the system is to analyze.
- 14. Choose Execute.



The portfolio hierarchy is displayed on the left of the screen as a navigation structure. By double clicking on a node, you can branch to the gap analysis results for this node, which are then shown in the right-hand subscreen. The system always displays the detail screen of the selected reference scenario or reference scenario progression first.

The following functions are available before you start the simulation:

|Function|Interaction|Comments|
|---|---|---|
|ALM Expert Mode| Settings ALM Expert On|For more information see ALM Expert Mode. |
|Average position evaluation|Average Position tab page| |
|Key date position evaluation|Key Date Position tab page| |
|Maturity evaluation|Maturity Evaluation tab page| |
|Cash flow evaluation|Cash Flow Evaluation tab page| |
|Liquidity evaluation|Liquidity Evaluation tab page| |
|Currency liquidity evaluation|Currency Liquidity tab page| |
|Net interest income evaluation|Net Interest Income Evaluation tab page| |
|Standard simulation| Standard Simulation| |
|Using explicit due date scenarios|GotoDue Date Scenarios|When a second due date scenario is used, the impact of the first due date scenario on the results is retained. You can delete the effect on results caused by a due date scenario by choosing Goto  Delete Due Date Scenario/Simulation . Note that this will delete the simulation results as well.|
|Switching between the overview screen and the detail screen| Overview Screen, Detail Screen|In the overview screen, the system displays selected key figures for all scenarios and scenario progressions. In the detail screen, it displays all the key figures of a particular scenario or scenario progression. If you are using the ALM expert mode, you are able to display in the overview screen the delta of a scenario to the reference scenario.|
|Choosing a different scenario or scenario progression| Scenario View|You access the detail screen of the selected scenario/scenario progression.|
|Defining the data relevant for display| Data Relevant for Display|You can choose between the evaluation currency and the transaction currency, change the currency unit, and manipulate the displayed data by setting the balance sheet, liquidity, and cash flow indicators.|


|Function|Interaction|Comments|
|---|---|---|
| | |For more information see Settings in the Application |
|Displaying the detailed log| Goto Detailed Log|The detailed log shows the evaluation parameters that were selected, the market data applied, and the results objects from gap analysis.|


**The following functions are available after you have run a simulation:**

|Function|Interaction|Comments|
|---|---|---|
|Simulation log| ALM Simulation Simulation Log or Simulation Log. |You can use the following functions in the simulation log: Display the processes of the simulation  Transactions For each process in the simulation, you can display the transaction that were generated.  RiskObject Display of the transactions related to the risk object.  Gap Results Objects Display of the results objects  Delete Deletion of the simulation processes  Save Save of the simulation processes  Elasticity Branching to the log of elasticity (if requested)  Maturity Band Display of the simulation parameters (if entered) dependent on the maturity band  Goto Characteristics Display of the values of characteristics used in the simulation process.|
|Saving or deleting the simulation results| ALM Simulation Save Simulation or ALM Simulation Delete Simulation . |The system saves or deletes all your simulations.|
|Saving or deleting particular simulation results| ALM Simulation Simulation Log or Simulation Log. |In the log display you are able to save or delete particular simulations. Select the entry you want to save or delete, and choose Save or Reverse.  |



By choosing Display Graphic in the tab page of the respective evaluation, you can branch to the ALV graphic. The system always generates a bar chart, regardless of the evaluation category. You can change the type of graph, and the scaling of the data by means of the context menu (right mouse button).

###### Evaluation Date versus Horizon in ALM

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Executing Analysis and Simulation > Evaluation Date versus Horizon in ALM | L8 | trm03 p.94 | loio `f9fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f9fdc5536a51204be10000000a174cb4.html?locale=en-US)

The system distinguishes between the evaluation date and the horizon in both ALM simulation and ALM simulation single value analysis . Both these data fields influence which transactions are selected for gap analysis and ALM simulation, and which market data is used for the evaluations. The horizon must always be either larger than or equal to the evaluation date. The first date displayed in the maturity band used in the evaluation is always the horizon.

a) If the horizon date is larger (later) than the evaluation date, the following selection rules apply:

The system selects all actual transactions that exist on both the evaluation date and the horizon date .

When you run ALM simulation or ALM simulation single value analysis, on the Simulation tab page you can define which saved simulated transactions you want to include in the evaluation.From the transactions selected here, the system selects the saved simulated transactions that exist at the point in time of the horizon.

[figure TRM03-F094 - When you run ALM simulation or ALM simulation single value analysis, on the Simulation tab page you can define which saved simulated transactions you want to include in the evaluation.From the transactions selected here, the system selects the saved simulated transactions that exist at the point in time of the horizon.]

The system selects and evaluates the transactions in the following way:

- Actual transaction 1 is selected because it exists on the evaluation date as well as on the horizon date.

- Simulated transaction 1 is selected because it exists on the horizon date.

Actual transaction 2 is not selected because it has already expired by the horizon date and so does not appear in the evaluations.

- Simulated transaction 2 is not selected because it has already expired by the horizon date.


- Actual transaction 3 is not selected because the date on which it was contracted is after the evaluation date. Hence it does not exist on the evaluation date.


- Simulated transaction 3 is selected because it exists on the horizon date.

Actual transaction 4 is not selected because the date on which it was contracted is after the horizon date. Hence it does not exist either on the evaluation date or on the horizon date.

- Simulated transaction 4 is not selected because it does not exist on the horizon date.


b) If the horizon date is the same as the evaluation date, then the following selection rules apply:

The system selects all actual transactions that exist on the evaluation date/horizon date .

When you run ALM simulation or ALM simulation single value analysis, on the Simulation tab page you can define which saved simulated transactions you want to include in the evaluation.Of those transactions selected there, the system then selects all saved simulated transactions that have not yet expired by the evaluation date/horizon date.

[figure TRM03-F095 - When you run ALM simulation or ALM simulation single value analysis, on the Simulation tab page you can define which saved simulated transactions you want to include in the evaluation.Of those transactions selected there, the system then selects all saved simulated transactions that have not yet expired by the evaluation date/horizon date.]

The system selects and evaluates the transactions in the following way:

- Actual transaction 1 is selected because it exists on the evaluation date/horizon date.

- Simulated transaction 1 is selected because it exists on the evaluation date/horizon date.

Actual transaction 2 is not selected because it was only contracted after the evaluation date/horizon date. Hence it does not yet exist on the evaluation date/horizon date.

- Simulated transaction 2 is selected.




The differentiation between the evaluation date and the horizon enables you to do the following:

Display a fixed-interest-rate balance sheet for a future point in time (section a), starting from the evaluation date, and in this way check the plausibility of planning results.

Display the actual transactions that exist on the evaluation date/horizon date and all simulated transactions that have not yet expired.

###### ALM Expert Mode

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Executing Analysis and Simulation > ALM Expert Mode | L8 | trm03 p.95 | loio `e7fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e7fdc5536a51204be10000000a174cb4.html?locale=en-US)

Use

The ALM expert mode enables you to display the results from ALM simulation more flexibly.

If you are using the ALM expert mode, you can integrate into one evaluation key figures (columns) taken from another evaluation. This means, for example, that you can display net interest income in the average position evaluation, or the valuation results in the net interest income evaluation.

In the ALM expert mode you can also use additional key figures to help you analyze the results from the simulations you have run.

**Features**

Once the ALM expert mode has been activated, at first only the names of the individual columns (key figures) change in the evaluations. The name of each column is suffixed with an abbreviation for the name of the evaluation from which the column originates, for example AP for average position. This enables you to recognize later from which evaluation the column comes.

The standard initial layout in the evaluations does not change as soon as you choose the ALM expert mode. If you use the LayoutSettings... function you are then able to integrate the key figures from different evaluations in the evaluation of your choice.


An exception to this, however, are the key figures from the currency liquidity evaluation. These cannot be included in the other evaluations because there can be more than one value for each maturity band date.

**Recommendation:**

Define you own layout and save it.

Additional key figures are available in the ALM expert mode. However, you first need to modify the existing standard layout accordingly by using the LayoutSettings... function. The following key figures are available in the ALM expert mode:


Standard key figures from the respective evaluations for the results from standard simulation without actual values (for example, asset volume, AP, standard simulation).

Standard key figures from the respective evaluations for the results from individual simulation without actual values (for example, asset volume, AP, individual simulation).

Standard key figures from the respective evaluations for the results from fictitious transactions without actual values (for example, asset volume, AP, fictitious transactions).

Standard key figures from the respective evaluations for the results from standard simulation including actual values (for example, asset volume, AP, actual + standard simulation).

Standard key figures from the respective evaluations for the results from individual simulation including actual values (for example, asset volume, AP, actual + individual simulation).

Standard key figures from the respective evaluations for the results from fictitious transactions including actual values (for example, asset volume, AP, actual + fictitious transactions).

In the normal mode, you can display simulated transactions only in conjunction with the actual transaction.

**Note:**

You can create a layout with key figures for the standard simulation (for example, asset volume, average position, standard simulation) only if you have already run a standard simulation. The relevant key figures appear in the columns only after a standard simulation has been run.

In the overview screen, you can display the delta of a scenario to the reference scenario.

Activities

Start the ALM simulation .You find the ALM simulation under Accounting Financial Supply Chain Management

Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Simulation/Planning Start ALM Simulation .

Then choose Settings ALM Expert Mode On to access the ALM expert mode.

###### Profit or Loss from Currency Translation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Profit or Loss from Currency Translation | L7 | trm03 p.97 | loio `2ffec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2ffec5536a51204be10000000a174cb4.html?locale=en-US)

The profit or loss from currency translation shows the gain or loss resulting from exchange rate fluctuations from a foreign currency transaction. You can display the profit or loss from currency translation in liquidity evaluations and in the net interest income evaluation.

**Activities**

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Evaluation Control Valuation Settings Define and Set Up ALM Valuation Type . In the ALM valuation type, set the Calculate Forward Rt indicator. You can define whether future currency flows are to be converted to the evaluation currency by the spot rate or the forward rate.
- 2. Create several exchange rate scenarios. For more information about creating scenarios see editing scenarios.

- 3. Start the ALM simulation. In doing so, in the Market Scenarios tab page enter the exchange rate scenarios you have defined. Choose Execute.

- 4. Choose Overview Screen.



**Result**

(Currency) liquidity evaluation

For each scenario, the system displays the incoming payments and disbursements generated by your transactions, and converted into the evaluation currency (default). The (currency) liquidity evaluation shows you how the incoming payments and disbursements would develop subject to different exchange rate scenarios.

In addition to the incoming payments and disbursements, you can, for example, display an overview of the liquidity gap. Choose Layout Settings... to change the layout.


Choose Data Relevant for Display. Here you have the option of modifying the display of the results. For example, you can hide the capital flows or the interest payment flows.


Net interest income evaluation

In the net interest income evaluation, you can use different exchange rate scenarios to examine how the balance sheet volume and the net interest income would develop.

**Note:**

In the net interest income evaluation, it is not possible to display the exchange gain or loss.

**Example**

Fixed-term deposit of USD 100,000.00

Term 10/19/2001 – 10/19/2002

Interest rate 7%, which means a repayment of USD 107,000 on 10/19/2002

|Current market data:|EUR/USD spot rate 0.8392|USD/EUR 1.1916|
|---|---|---|
|Scenario 1|EUR/USD spot rate 0.80|USD/EUR 1.25|
|Scenario 2|EUR/USD spot rate 0.90|USD/EUR 1.1111|


In the ALM valuation type, the Calculate Forward Rt indicator was set to spot rate.

Currency liquidity evaluation (overview screen)

Transaction currency converted into evaluation currency EUR

|Maturity Band Date|Transaction Currency|Disbursement (Current)|Disbursement (Scenario 1)|Disbursement (Scenario 2)|Inpayment (Current)|Inpayment (Scenario 1)|Inpayment (Scenario 2)|
|---|---|---|---|---|---|---|---|
|10/19/01|USD|119,161.11|125,000.00|111,111.11| | | |
|10/19/01|USD| | | |127,501.20|133,750.00|118,888.89|

###### Using Different Maturity Bands

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Using Different Maturity Bands | L7 | trm03 p.98 | loio `c6fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c6fdc5536a51204be10000000a174cb4.html?locale=en-US)

In ALM simulation, if you select a maturity band that is different from the one entered in the planning variant, then the system adds any date values from the maturity band in the planning variant that are not in the maturity band you selected for ALM simulation. The message log and the detailed log (general information) refer you to this.


If you want to view the evaluations using the original date values of the maturity band used in gap analysis/ALM simulation, you need to save the simulated transactions and then run ALM simulation again using the relevant maturity band and the simulated transactions you saved.

[figure TRM03-F102]

###### Simulation of Liquidation Revenue from Sale/Purchase of Securities/Loans

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Simulation and Planning > ALM Simulation > Simulation of Liquidation Revenue from Sale/Purchase of Securities/Loans | L7 | trm03 p.99 | loio `0bfec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0bfec5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

You use this function to simulate the liquidity effect of the sale or purchase of securities or loans. The values are simulated in the liquidity evaluation in ALM. You depict the purchase or sale of securities or loans in liquidation scenarios . The potential sales revenue/purchase price is stored in a liquidation scenario. In the liquidation evaluation, the system distributes this potential revenue/purchase price as the NPV across the maturity band.

The system can simulate the liquidity for the following transactions:

All class positions in securities accounts and securities transactions (bonds, stocks, complex classes)

Loans without special features

Complex financial transactions that contain a loan on the first or second level, and that otherwise contain just options (loans with call options)

The system cannot simulate the liquidity of futures.

**Prerequisites**

You have defined liquidity scenarios and assigned them to a valuation rule. You define liquidity scenarios in the IMG under Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Simulation Additional Settings for Simulation Using Scenarios Define Liquidation Scenarios . You assign the liquidity scenarios to valuation rules in the IMG under Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Simulation

Additional Settings for Simulation Using Scenarios Assign Liquidation Scenarios to Valuation Rules .

**Features**

Liquidation scenarios define which potential sales revenue/purchase price occurs in which time period. The fictitious change in a position describes the portion that is purchased or sold on a particular date This is used to simulate the liquidation revenue and expense. This change can be only a reduction in the value of the position.

In addition, you can define that the early liquidation leads to a markdown on the current market value. You do so using the Repayment Rate field in the liquidation scenario.

All fictitious changes to a liquidity scenario (partial sales or purchases) have to be either equal to or less than 100%. If the fictitious changes do not add up to 100%, the system displays the original cash flows in proportion to the original dates (with a repayment rate of 100%).

- 1. If the security or loan is specified, the system uses the combination of the transaction form, valuation type, valuation rule, remaining term, and the currency to determine the liquidation scenario.

If you have not entered a valuation rule or a currency in the assignment table, the system finds a default entry (a liquidity scenario is assigned only the transaction form and evaluation type). If there are no default entries, the system does not simulate the liquidation of the security position or loan.

- 2. The system determines the liquidation key dates from the liquidation scenario it found. If a Liquidation Period was entered in the assignment table, for each liquidation key date, the date is shifted by the period specified in trading days, as per the calendar.
- 3. For each liquidation key date that results, the system then finds the correct market value. This is multiplied by the Fictitious Change specified, and results in the potential liquidation value.
- 4. The system adjusts the liquidation value by the repayment rate (liquidation value x repayment rate).
- 5. The liquidation revenue that is simulated is displayed in the liquidity evaluation in the column LQ Planning . Positions to which no liquidity scenario is assigned are also shown in the column LQ Planning ; they are shown as maturing on the original date of the cash flow.


Example

**You have entered the following values for liquidation scenario 4711:**

|Sequence Number|Increment|Time Unit|Fictitious Change|Repayment Rate|
|---|---|---|---|---|
|1|1|Month|50%|80%|
|2|3|Month|25%|100%|


The market value that is assumed for the securities position is EUR 1,000, and it pays 6% interest p.a. (monthly interest payment of EUR 5). The position matures in 6 months. Let us assume that in 3 months the position has a market value of EUR 1,020. Using this liquidation scenario, the payments are as follows:

|Date|Capital in Incoming/Outgoing Payment Column|Interest in Incoming/Outgoing Payment Column|Capital in LQ Planning Column|Interest in LQ Planning Column|
|---|---|---|---|---|
|1st Month| |EUR 5|EUR 400|EUR 5|
|2nd Month| |EUR 5| |EUR 2.5|
|3rd Month| |EUR 5| |EUR 2.5|
|4th Month| |EUR 5| |EUR 1.25|


|Date|Capital in Incoming/Outgoing Payment Column|Interest in Incoming/Outgoing Payment Column|Capital in LQ Planning Column|Interest in LQ Planning Column|
|---|---|---|---|---|
|5th Month| |EUR 5| |EUR 1.25|
|6th Month|EUR 1000|EUR 5|EUR 250|EUR 1.25|


The EUR 400 liquidation revenue after the first month results from the market value of EUR 1,000 minus the fictitious change of 50% multiplied by the repayment rate of 80%.

The interest payment of EUR 2.5 after the second and third months results from the market value of EUR 1,000 minus the fictitious change of 50% multiplied by the 6% interest rate and divided by the 12 months.

The EUR 255 liquidation revenue after the third month results from the market value of EUR 1,020 minus the fictitious change of 50% and 25% multiplied by the repayment rate of 100%.

The interest payment of EUR 1.25 after the fourth, fifth, and sixth months results from the market value of EUR 1,000 minus the fictitious change of 50% and 25% multiplied by the 6% interest rate and divided by the 12 months.

The liquidation revenue of EUR 250 after the sixth month results from the market value and the residual position of 25%.

###### Controlling ALM Evaluations

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Controlling ALM Evaluations | L5 | trm03 p.101 | loio `02fec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/02fec5536a51204be10000000a174cb4.html?locale=en-US)

You can influence the evaluations in the Asset/Liability Management (ALM) component by means of your settings in Customizing, and by adjusting the data relevant for display directly in the evaluation.

###### Settings in the ALM Valuation Type

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Controlling ALM Evaluations > Settings in the ALM Valuation Type | L6 | trm03 p.101 | loio `44fec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/44fec5536a51204be10000000a174cb4.html?locale=en-US)

You control the depiction of evaluation results in gap analysis and ALM simulation by making settings in the ALM valuation type.

You find the ALM valuation type in Customizing under Financial Supply Chain Management Treasury and Risk Management

Market Risk Analyzer Simulation Define ALM Valuation Type . You can also access these settings from the SAP Easy Access screen by choosing Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Evaluation Control Valuation Settings Define and Set Up ALM Valuation Type .

|Indicator|Meaning|Example|
|---|---|---|
|Delta indicator|Indicates the status with which an option volume enters gap analysis/ALM simulation. The system contains the following options for handling the option volume: The underlying of the option is not taken into account (delta = 0) The underlying of the option is taken fully into account (delta = 1) A delta of 1 is assumed for a call (purchase of an option) and a delta of –1 for a put (sale of an option). The delta of an option can be| |


|Indicator|Meaning|Example|
|---|---|---|
| |understood as the exercise probability of the option. This means that a delta of 1 or –1 represents a probability of 100% that the option will be exercised. The underlying of the option is taken fully into account in the position evaluation, maturity evaluation, and cash flow evaluation accordingly, regardless of whether the option is in-the-money, at-themoney, or out-of-the money. In the (currency) liquidity evaluation and the net interest income evaluation, the underlying of the option is treated differently, depending on whether the option is in-the-money. If the option is in-themoney, the underlying is taken fully into account. If it is at-the-money or out-of-the-money, the underlying is ignored. Underlying of the option, deltaweighted (liquidity evaluation: delta = 1 or –1) The underlying of the option is taken into account, delta-weighted, in the position evaluation, maturity evaluation, and cash flow evaluation. In the (currency) liquidity evaluation and the net interest income evaluation, the underlying of the option is treated differently, depending on whether the option is in-the-money. If the option is in-themoney, the underlying is taken fully into account. If it is at-the-money or out-of-the-money, the underlying is ignored. Underlying of option, deltaweighted (liquidity evaluation, delta-weighted) The underlying of the option is taken into account, delta-weighted, in the position evaluation, cash flow evaluation, and in the (currency) liquidity evaluation. In the net interest income evaluation, the underlying of the option is treated differently, depending on whether the option is| |


|Indicator|Meaning|Example|
|---|---|---|
| |in-the-money. If the option is in-themoney, the underlying, or the net interest income of the underlying, is taken fully into account. If it is atthe-money or out-of-the-money, the underlying is ignored. Options in-the-money: Underlying is taken fully into account. Options atthe-money and out-of-the-money: Underlying is ignored. The underlying of the option is treated differently, depending on whether the option is in-the-money. If the option is in-the-money, the underlying is taken fully into account in all evaluations. If it is atthe-money or out-of-the-money, the underlying is ignored. How an option is shown in the (currency) liquidity evaluation and in the net interest income evaluation also depends on the exercise type of the option. Options exercised for a physical delivery: In the (currency) liquidity evaluation, the flows of the underlying of the option are taken into account and are delta-weighted depending on the setting. In the net interest income evaluation, the relevant net interest income is shown. Options with cash settlement: In the (currency) liquidity evaluation and the net interest income evaluation, only the settlement payment (intrinsic value of the option) is shown, and it is deltaweighted depending on the setting. Hence, the flows of the underlying of the options do not appear in the (currency) liquidity evaluation. If you do not set the Delta indicator, the option volume is not taken into account (default setting).| |
|Display premium/discount|With this setting, loans or fixed and variable-rate securities that are paid out with a premium or discount can be displayed in accordance with the development of their interest rates. The|Example: Fixed-Rate Loan with Discount |


|Indicator|Meaning|Example|
|---|---|---|
| |premium or discount is distributed, weighted by volume, to the interest payment dates. In the position evaluation, a distinction is made between gross display and net display. In the gross display, the nominal capital development and the premium/discount development are shown on different sides of the balance sheet. In the net display, the netted payments are shown on one side of the balance sheet.| |
|Spread processing|Often, transactions with variable conditions contain a fixed interest portion or "spread". The Spread Processing indicator allows you to define how the spread is treated in position evaluations. You can choose to display the spread as a variable item or as a fixed-rate item. If you choose to display the spread as a fixed-rate item, you have to decide whether the nominal volume is displayed on its own on the original balance sheet side or also displayed on the opposite side with a zero condition (so that the volume in the gap is correct again).| |
|Outflow indicator|In gap analysis, the Outflow indicator is used to determine whether the negative outflows (inflows) are moved to the opposite side of the balance sheet or appear on the same side of the balance sheet in the outflow evaluation.|Example: Fixed-Term Deposit, Plain Vanilla Interest Rate Swap |
|Calculate forward rate|In gap analysis, you can decide whether future cash flows that are not quoted in the evaluation currency are translated at the current exchange rate (default) or at the relevant forward rate.| |
|Interest calculation method (ICM)|Each transaction in the SAP data pool has an interest calculation method (ICM) that is assigned in the transaction’s conditions. For evaluations in gap analysis and ALM, it is absolutely essential that the interest calculation methods of the transactions are adjusted so that they all have the same method, otherwise no comparison is possible. (Default setting: There is no adjustment to a standard interest calculation method. However, the interest calculation method 360/360 is used in the net interest income evaluation.)| |


|Indicator|Meaning|Example|
|---|---|---|
|OI determination (specific to the valuation rule, can be overridden)|The entry you make in this field controls which opportunity interest rate is used in ALM to determine the net interest margin. If you adopt the default setting, the product interest rate is used as the opportunity interest rate. You also have the following options: Use of an external key figure, which can be maintained in the financial object Average from the yield curve in the calculation rule or from the yield curve in the evaluation type For accounts, the opportunity interest rate can be calculated as an average of the opportunity interest rates from the maturities simulated in the due date scenarios. If the due date scenario contains a subincrement, then the opportunity interest rate is calculated as a floating average. If not, then it is calculated as a simple average by means of the simulated maturities.|Example: Account |
|Static interest rate (StatInd) (specific to the valuation rule, can be overridden)|You use this setting to define whether the product interest rate or the static interest rate is displayed for discount transactions (loans, securities) in gap analysis/ALM. The static interest rate is an approximation of the effective interest rate in which the premium/discount is distributed to the other interest payment dates.|Example: Fixed-Rate Loan with Discount |
|Balance sheet volume in net interest income (BS Volume in Int. Res) (specific to the valuation rule, can be overridden)|You can specify whether the off-balancesheet volume is taken into account in the net interest income evaluation. If you set this indicator to Off-Balance-Sheet Transactions Not Included, the result is still influenced by off-balance-sheet transactions, but only the balance sheet volume is displayed in the net interest income evaluation (for example, the column ALM Asset-Side Balance Sheet Volume). This indicator influences the relevant volume columns only.| |
|End of loan (specific to the valuation rule, can be overridden)|By setting this indicator, you control which date field the system accesses (term end or end of fixed-rate period) in the case of loan transactions if you select Capital Commitment (commitment indicator) when you choose Data Relevant for Display.| |


|Indicator|Meaning|Example|
|---|---|---|
|Forward exchange transaction|By setting this indicator, you choose how forward exchange transactions are shown in gap analysis. You have the following options: Display as NPV: In the position evaluations, the nominal volume discounted to the contract date is shown. For Hedging Capital Positions: In the position evaluations, forward exchange transactions are shown with the nominal capital and an interest rate of zero. In the net interest income evaluation, although a position is shown, no net interest income is shown. For Hedging Interest Payments: If you choose this option, forward exchange transactions are not shown in the position evaluation. In the net interest income evaluation, an entry is made both for the interest revenue of the interest position and for the interest expense of the position. These values are shown for the relevant period.| |

###### Calculation of the Opportunity Interest Rate in ALM

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Controlling ALM Evaluations > Calculation of the Opportunity Interest Rate in ALM | L6 | trm03 p.106 | loio `ccfdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ccfdc5536a51204be10000000a174cb4.html?locale=en-US)

The opportunity interest rate used in Asset/Liability Management (ALM) represents the interest rate at which a matching customer transaction can be refinanced or invested on the market based on the nominal interest rate.

**Use**

In the position evaluations, the opportunity interest rate is shown in the same way as the product interest rate. The net interest income evaluation displays the profit or loss from the interest terms and the profit or loss from the mismatch spread, which are calculated on the basis of the nominal opportunity interest rate and the nominal product interest rate.

**Integration**

You can use the following procedures for determining the opportunity interest rate (OI).

External key figure

The opportunity interest rate is transferred to the SAP system as an external key figure. Use key figure category 0014. You store this opportunity interest rate directly in the financial object.

Use of calculated opportunity interest rates

Do not use

Calculation of the Opportunity Interest Rate as a Floating Average, Taking Maturities into Account (for Accounts and Variable Transactions only)

Field OI Determination is empty

In this case the opportunity interest rate is the same as the product interest rate (default setting).

The default setting also applies when the External key figure option has been selected, but the system is unable to find a corresponding opportunity interest rate, or if the procedure Use calculated OI has been selected, but the system is unable to calculate this transaction, or no calculation has been carried out.

You make the setting for the opportunity interest rate in the ALM valuation type. You find the ALM valuation type in Customizing under Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Simulation Define ALM Valuation Type . You can also access these settings from the SAP Easy Access screen by choosing Accounting Financial

Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Evaluation Control Valuation Settings Define and Set Up ALM Valuation Type .

###### Opportunity Interest Calculation for Accounts

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Controlling ALM Evaluations > Calculation of the Opportunity Interest Rate in ALM > Opportunity Interest Calculation for Accounts | L7 | trm03 p.107 | loio `2cfec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2cfec5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

For accounts, the opportunity interest rate can be calculated as simple average and as a floating average of the opportunity interest rates from the maturities simulated in the due date scenarios. In the calculation of the floating average, past opportunity interest rates of the position are taken into account; in the calculation of the simple average, only the opportunity interest rates going back to the evaluation date are taken into account.

**Recommendation:**

Averages can be used in the calculation of the opportunity interest rate for implied due date scenarios only. The due date scenario used must not have a base amount, or defined rates of growth.

**Prerequisites**

The system must already contain a due date scenario (without a base amount and rates of growth) to which due date periods have been assigned.

For the floating average, the Time Unit for Subincrement and Subincrement fields must each contain a value.

For the simple average, the Time Unit for Subincrement and Subincrement fields must be left empty.

This due date scenario has to be assigned to the accounts and/or the variable transaction by means of a valuation rule.

In the Customizing for the ALM valuation type, the “OI Determination” field for this valuation rule contains the entry Average from Yield Curve for Calculation Rule or Average from Yield Curve for Evaluation Type. Depending on whether the Profitability Analysis component has been set up, the yield curve from the calculation rule or from the evaluation type can be used.

**Features**

Moving Average

During gap analysis or ALM simulation, the opportunity interest rate for variable transactions and accounts (to which a due date scenario is assigned) is calculated as follows:

[figure TRM03-F103 - The diagram shows a due date scenario that has the following properties: 50% matures within 3 months; an additional 50% matures within one year. This assumes that, in both maturity periods, maturity is spread evenly across the months.]

The diagram shows a due date scenario that has the following properties: 50% matures within 3 months; an additional 50% matures within one year. This assumes that, in both maturity periods, maturity is spread evenly across the months.

This gives the following values: in the first section, 16.67% matures per month; in the second section, 4.17% matures per month.

[figure TRM03-F104 - The maturities are cumulated (4.17% + 16.67% = 20.84%) for each date in the maturity band, and the opportunity interest rate is calculated, weighted by volume across the past.]

The maturities are cumulated (4.17% + 16.67% = 20.84%) for each date in the maturity band, and the opportunity interest rate is calculated, weighted by volume across the past.

[figure TRM03-F105 - The opportunity interest rate for the first month is then calculated as follows:]

The opportunity interest rate for the first month is then calculated as follows:

OI (1st month) = (OI 1-1 * volume 1-1 + OI 1-2 * volume 1-2 + OI 1-3 * volume 1-3 + OI 2-1 * volume 2-1 + ... OI 2-12 * volume 2-12) / total volume

###### Settings in the Application

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Controlling ALM Evaluations > Settings in the Application | L6 | trm03 p.109 | loio `f3fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f3fdc5536a51204be10000000a174cb4.html?locale=en-US)

You are able to influence the results displayed in gap analysis/ALM simulation by modifying the settings made in the Data Relevant for Display dialog box. You access these settings in the evaluation by choosing Settings Data Relevant for Display , or by choosing Data Relevant for Display.

|Indicator|Values|Meaning|
|---|---|---|
|Currencies|Transaction Currency Evaluation Currency|You use the currency indicator to control whether just the transactions in a certain currency (setting: Transaction Currency), or all selected transactions, regardless of the currency in which they were concluded, are displayed (setting: Evaluation Currency). See also: Currency Liquidity Evaluation |
|Commitment Indicator|Interest Commitment Capital Commitment|You use the commitment indicator to control whether just the fixed-rate items are included in the evaluations (setting: Interest Commitment) or whether the variable items are included as well (setting: Capital Commitment). The settings you make here affect the position and maturity evaluations. Example: Plain Vanilla Interest Rate Swap |


|Indicator|Values|Meaning|
|---|---|---|
| | |If you are using the ALM expert mode, and have inserted the Average Position column into the liquidity evaluation, for example, then it is relevant for this column how the commitment indicator is set in the data relevant for display.|
|Liquidity|No Liquidity Fixed Liquidity Forward Liquidity Fictitious Liquidity|You use the liquidity indicator to control what type of liquidity is displayed in the evaluations. The value No Liquidity is relevant only for transactions with flows that represent no real liquidity. These include, for example, the capital swap in a plain vanilla interest rate swap, and premium/discount flows. The setting in the field No Liquidity has no impact on the liquidity evaluation. Fixed Liquidity is understood to be all cash flows that are based on a fixed interest rate. Forward Liquidity refers to a cash flow based on interest rates that are not yet fixed. The cash flow is therefore determined on the basis of forward rates. Fictitious Liquidity refers to those cash flows that result from the use of due date scenarios.|
|Scaling Factor|One Currency Unit 1 000 Currency Units 1 Million Currency Units| |
|Balance Sheet Indicator|Balance Sheet Transaction Off-Balance Sheet Transaction|You use the balance sheet indicator to control what kind of transactions are to be shown in the evaluations: Only balance sheet Only off-balance sheet Both balance sheet and off-balance sheet You have to store the respective balance sheet value for each transaction in the analysis parameters (RM) of the financial object.|


|Indicator|Values|Meaning|
|---|---|---|
|Cash Flows|Capital Interest Premium/Discount Premiums Charges Other Cash Flows|The Cash Flow indicator enables you to control which cash flow types are displayed in the evaluations.|

###### Evaluations for Gap Analysis/ALM Simulation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Evaluations for Gap Analysis/ALM Simulation | L5 | loio `f6fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f6fdc5536a51204be10000000a174cb4.html?locale=en-US)

**Currency Liquidity Evaluation**

Use

Using the currency liquidity evaluation, you are able to portray the bank’s liquidity situation separately and for individual currencies starting from the cash flows of the base portfolios.

In the currency liquidity evaluation , the system displays for each maturity band date the incoming payments and disbursements separately, and sorted by currency. It also displays the liquidity gap resulting from these movements, also sorted by currency. The system also displays the cumulated liquidity gap.

Note, however, that unlike the cash flow evaluation, the transactions in the currency liquidity evaluation (as in the liquidity evaluation ) are always shown with the capital commitment (commitment indicator set to Capital Commitment ). The system determines cash flows that are not yet fixed, (from floaters, for example) either by using of forwards, or by using scenario progressions.

**Features**

The system displays the cash flows per maturity band date and sorted by currency. In the settings in the Data Relevant for Display, you can control whether the cash flows are converted into the evaluation currency (currency indicator set to Evaluation Currency) or displayed in the respective transaction currency (currency indicator set to Transaction Currency).

The default setting is for the cash flows to be converted into the evaluation currency. If you want to depict the cash flows in their respective transaction currencies, then in the Data Relevant for Display you need to set the indicator Currencies to the value Transaction Currency, and choose the currency you require. The currency you select here is of no relevance for the currency liquidity evaluation. Note, however, the effect of this indicator on the other evaluations.

To access the Data Relevant for Display, choose Settings Data Relevant for Display .

It is not possible to run standard simulation in the currency liquidity evaluation. You can, however, close gaps for a currency in the liquidity evaluation. If you run standard simulation in the liquidity simulation, you can then examine the effects in the currency liquidity evaluation.

Example

|Maturity band date|Currency|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|Evaluation currency or transaction currency (as per the setting for the data relevant for display)|
|---|---|---|---|---|---|---|
|08/31/XX|EUR|3,911,660|1,955,830|1,955,830|1,955,830|AUD|
|08/31/XX|USD|2,165,400|7,578,900|-5,413,500|-5,413,500|AUD|
|08/31/YY|EUR|1,955,830|2,933,745|-977,915|977,915|AUD|
|08/31/YY|USD|3,248,100|2,165,400|1,082,700|-4,330,800|AUD|


Scenario: In Evaluation Currency AUD

|Maturity band date|Currency|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|Evaluation currency or transaction currency (as per the setting for the data relevant for display)|
|---|---|---|---|---|---|---|
|08/31/XX|EUR|2,000,000|1,000,000|1,000,000|1,000,000|EUR|
|08/31/XX|USD|1,000,000|3,500,000|-2,500,000|-2,500,000|USD|
|08/31/YY|EUR|1,000,000|1,500,000|-500,000|500,000|EUR|
|08/31/YY|USD|1,500,000|1,000,000|500,000|-2,000,000|USD|


Scenario: In Transaction Currency

###### Currency Liquidity Evaluation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Evaluations for Gap Analysis/ALM Simulation > Currency Liquidity Evaluation | L6 | trm03 p.77 | loio `d5fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d5fdc5536a51204be10000000a174cb4.html?locale=en-US)

Net interest income evaluation

The system displays the results using the SAP List View (ALV) . This presentation tool for lists with generic functions enables you to create display variants flexibly.

In ALM simulation, you can use multiple scenarios and scenario progressions as the basis of the valuation. You can also switch between the relevant scenarios/scenario progressions within ALM simulation.

You can display the results of ALM simulation either in the overview screen (selected key figures for all scenarios and scenario progressions) or in the detail screen (key figures for a scenario or scenario progression).

You can also split the net interest income into the net interest margin, and the profit/loss from the mismatch spread.

Application of implicit and explicit due date scenarios. Using implicit due date scenarios, you can define fictitious maturities for products without fixed terms. You use explicit due date scenarios in gap analysis and ALM simulation to enable you to take into account early repayments, for example.

Flexible procedures for simulating new business, such as the fast entry of fictitious financial transactions, following ALM simulation. The effects of the new business can be seen immediately.

The simulated and fictitious transactions can be saved, and later evaluated using NPV analysis, value-at-risk analysis, and gap analysis.

You can extract the saved results of ALM simulation to the SAP Business Information Warehouse (BW) and use them in BW analyses.

You can also balance your balance sheet, and take non-interest profit and loss items into account.

Process Diagram

[figure TRM03-F058 - Process Diagram]

###### Interest Result Evaluation

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Evaluations for Gap Analysis/ALM Simulation > Interest Result Evaluation | L6 | trm03 p.112 | loio `fcfdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fcfdc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

The net interest income is the part of the total payments belonging to a transaction that results when interest is calculated on the nominal capital.

The interest result analysis displays the net interest income of a bank distributed over time. By comparing the net interest income based on current price parameters and various scenarios, you can see the impact of possible future developments on the net interest income of the bank.

**Features**

In the interest result evaluation, the system displays the following: balance sheet volume, product interest rate, opportunity interest rate, interest revenue (product interest), interest revenue (opportunity interest), net interest margin contribution, absolute and relative net interest income and the profit or loss from the mismatch spread.

Depiction of the net interest income before and after simulation.

Depiction of the net interest income when different scenarios/scenario progressions are applied.

Splitting of the net interest income into the profit or loss from the mismatch spread and the net interest margin contribution.

Depiction of the profit or loss from derivatives

The profit or loss from derivatives comprises the interest income and premium income from derivative transactions. Since derivatives are generally used to hedge interest rate risks from the balance sheet, an interest result evaluation needs to display the data including and excluding the profit or loss from derivatives in order to show the effect of the hedge.

In addition to the interest income of the transaction, the premium from an option transaction also represents revenue or expense. This premium is displayed at the due date.

You can display the profit or loss from derivatives by assigning the balance sheet indicator off-balance sheet to the derivative transactions in the analysis parameters of the financial object. Start the ALM simulation . Choose Settings Data Relevant for Display and deselect the balance sheet transaction indicator. Choose Continue . You see the profit or loss from derivatives in the interest result evaluation.


Depiction of the exchange rate result.

In the interest result evaluation, you can have the system display how the net interest income has changed due to currency fluctuations. For more information about the depiction of exchange rate results choose profit or loss from currency translation .

In the interest result evaluation, transactions are always taken into account with their capital commitments. You can hide the results that were calculated using forward rates by deselecting the forward liquidity indicator in the data relevant for display. To access the data relevant for display , choose Settings Data Relevant for Display .

**Products requiring special treatment**

Options with the exception of caps and floors

The setting you make for the delta indicator in the ALM valuation type determines how the net interest income of an option is taken into account in the interest result evaluation.

Whether or not an accrual is required for the net interest income of an option depends on the delivery type of the underlying:

An accrual is not required for the interest revenue or expense of options with cash settlement . The interest result is effective on the due date only, and is therefore accounted for completely in the period in which the due date falls. In this case, the net interest income corresponds to the intrinsic value of the option.

In the case of options with physical delivery , the underlying is realized after the option is exercised. An accrual may or may not be required, depending on the underlying. If an accrual is made for the net interest income of the underlying, the same applies to the option, and vice versa.

**Examples**

**Fixed-Term Deposit**

Nominal amount: EUR 2,000,000.00

Term: 12/13/2000 – 12/13/2002

Nominal interest rate: 4%

Interest calculation method: 360/360

Interest payment cycle: every 12 months

Cash flow:

|Payment date|Payment amount|Type of flow|
|---|---|---|
|12/13/2000|EUR –2,000,000.00|Investment/Increase|
|12/13/2001|EUR +80,000.00|Nominal interest|
|12/13/2002|EUR +2,000,000.00|Final repayment|
|12/13/2002|EUR +80,000.00|Nominal interest|


Evaluation date : 10/27/00


Settings in the ALM valuation type

Outflow indicator: Negative outflows on other balance sheet side

Interest calculation method: 360/360

**Average position**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/27/2000| | | | | | | | |
|12/30/2000|562,500.00|4.00|4.00| | | |562,500.00| |
|12/16/2001|2,000,000.00|4.00|4.00| | | |2,000,000.00| |
|06/16/2003|1,319,926.87|4.00|4.00| | | |1,319,926.87| |
|12/16/2003| | | | | | | | |



How is the average asset volume of EUR 562,500.00 calculated?

In the period from 10/28/2000 to 12/12/2000 (46 days) the asset volume is EUR 0.00, whereas in the period from 12/13/2000 – 12/30/2000 (18 days) it is EUR 2,000,000.00. Based on this data, the average asset volume is calculated as follows:

(46 x 0.00 + 18 x 2,000,000.00)/64 = EUR 562,500.00


Why is the asset-side interest rate identical to the opportunity interest rate?

Since the OI Determination field is not maintained in the ALM valuation type, the product interest rate (default setting) is displayed as the opportunity interest .

**Key date position**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/27/2000| | | | | | | | |
|12/30/2000|2,000,000.00|4.00|4.00| | | |2,000,000.00| |
|12/16/2001|2,000,000.00|4.00|4.00| | | |2,000,000.00| |
|06/16/2003| | | | | | | | |
|12/16/2003| | | | | | | | |


Settings in the ALM valuation type

Outflow indicator: Negative outflows on other balance sheet side

Interest calculation method: 360/360

**Maturity evaluation (capital outflow)**

|Maturity band date|Asset-side outflow|Assetside interest|Asset-side opportunity interest|Liability-side outflow|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/27/2000| | | | | | | | |
|12/30/2000| | | |2,000,000.00|4.00|4.00| |2,000,000.00|
|12/16/2001| | | | | | | | |
|06/16/2003|2,000,000.00|4.00|4.00| | | |2,000,000.00| |
|12/16/2003| | | | | | | | |



The effect of the setting negative outflows on other balance sheet side (in the ALM valuation type) is that the asset-side inflow of EUR 2,000,000.00 is displayed in the liability-side outflow column with a plus sign ( maturity band date 12/30/00). If you want the asset-side inflow to be displayed in the asset-side outflow column with a minus sign, you have to choose the setting negative outflows on same balance sheet side in the ALM valuation type.

**Cash flow evaluation**

|Maturity band date|Inpayment|Disbursement|Gap|
|---|---|---|---|
|10/27/2000| | | |
|12/30/2000| |2,000,000.00|-2,000,000.00|
|12/16/2001|80,000.00| |80,000.00|
|06/16/2003|2,080,000.00| |2,080,000.00|


|Maturity band date|Inpayment|Disbursement|Gap|
|---|---|---|---|
|12/16/2003| | | |


Settings in the ALM valuation type

Outflow indicator: Negative outflows on other balance sheet side

Interest calculation method: 360/360

Liquidity evaluation

|Maturity band date|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|
|---|---|---|---|---|
|10/27/2000| | | | |
|12/30/2000| |2,000,000.00|-2,000,000.00|-2,000,000.00|
|12/16/2001|80,000.00| |80,000.00|-1,920,000.00|
|06/16/2003|2,080,000.00| |2,080,000.00|160,000.00|
|12/16/2003| | | |160,000.00|


Currency liquidity

|Maturity band date|Transaction Currency|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|Evaluation currency or transaction currency (as per the setting for the data relevant for display)|
|---|---|---|---|---|---|---|
|10/27/2000|EUR| | | | |EUR|
|12/30/2000|EUR| |2,000,000.00|-2,000,000.00|-2,000,000.00|EUR|
|12/16/2001|EUR|80,000.00| |80,000.00|-1,920,000.00|EUR|
|06/16/2003|EUR|2,080,000.00| |2,080,000.00|160,000.00|EUR|
|12/16/2003|EUR| | | |160,000.00|EUR|


Net interest income evaluation

|Maturity band date|Balance sheet asset-side volume|Asset-side interest|Asset-side opportunity interest|Interest revenue (product interest rate)|Interest revenue (opportunity interest rate)|Absolute interest income|Relative interest result|
|---|---|---|---|---|---|---|---|
|10/27/2000| | | | | | | |
|12/30/2000|571,428.57|4.00|4.00|4,000.00|4,000.00|4,000.00|4.0|


|Maturity band date|Balance sheet asset-side volume|Asset-side interest|Asset-side opportunity interest|Interest revenue (product interest rate)|Interest revenue (opportunity interest rate)|Absolute interest income|Relative interest result|
|---|---|---|---|---|---|---|---|
|12/16/2001|2,000,000.00|4.00|4.00|76,888.89|76,888.89|76,888.89|4.0|
|06/16/2003|1,318,518.52|4.00|4.00|79,111.11|79,111.11|79,111.11|4.0|
|12/16/2003| | | | | | | |



How is the interest revenue calculated for product interest amounting to EUR 4,000.00 at the maturity band date 12/30/2000?

The net interest income evaluation displays the net interest income of a bank distributed over time. The basis for the net interest income calculation is in this case the average balance sheet volume.

Note, however, that the average positions determined in the average position evaluation are calculated taking account of the maturity band. This means they are calculated on the basis of 365 or 366 days. In the net interest income evaluation, the interest calculation method defined in the ALM evaluation type is taken into account instead.

The average balance sheet volume is calculated in the same way as the average position.

(45 x 0.00 + 18 x 2,000,000.00)/63 = EUR 571,428.57

Using the 360/360 interest calculation method, there are only 45 days between 10/28/2000 and 12/12/2000. Therefore 10/31/2000 is not to be included here.

- The amount EUR 4,000.00 is calculated as follows:


10/28/00 – 12/30/00 63 days 571,428.57 x 63/360 x 0.04 = EUR 4,000.00

###### Examples

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Examples | L5 | loio `defdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/defdc5536a51204be10000000a174cb4.html?locale=en-US)

The delivered implementation BADII_BSPRD_DER_FWD_001 uses the filter value TENO. To use this implementation, you need to enter the value TENO in the relevant evaluation type/valuation rule in the Spread Derivation ID (Forward) field on the Evaluation Control tab in the Basis Spread Curve Derivation area.

If the tenor of a yield curve differs from the term of the reference interest rate, the implementation TENO looks for a matching tenor spread curve. In this way, you can, for example, assign a swap curve versus 6–Month EURIBOR as a forward curve for all EUR reference interest rates like the 3–Month EURIBOR. Spread curve derivation then looks for a matching spread curve to build the three-month forward curve from the six-month yield curve and from the three-month/six-month tenor spread curve.

The delivered implementation BADII_BSPRD_DER_EVAL_001 uses the filter value STD. To use this implementation, you need to enter the value STD in the relevant evaluation type/valuation rule in the Spread Derivation ID (Evaluation) field on the Evaluation Control tab in the Basis Spread Curve Derivation area.

Effect: Each discounting yield curve is adjusted against a curve with currency USD and tenor 3 months by adding suitable basis spread curves.

- 2. Deriving Credit Spread Curves


For outgoing payments, the credit spread curve for your own company is used, whereas, for incoming payments, the credit spread curve of your business partner is used. Credit spread curves are derived using the reference entities. The system

considers only reference entities for which the Use in Curves indicator has been set.

Determining Reference Entities

The system determines the reference entity for your own companies separately from that for business partners. In both cases, there is a standard derivation logic that you can replace using your own implementations of the BAdIs BAdI: Derive Reference Entity for Your Own Companies and BAdI: Derive Reference Entity for Business Partners. For this, the system first determines the derivation IDs that are assigned in the relevant evaluation type/valuation rule for derivation of the reference entities.

Standard Derivation for OTC Transactions

Reference Entities for Your Own Company

The standard implementation first searches for a reference entity for the company code of the transaction. If a reference entity is found for that company code, the system searches for a reference entity for the company code entered in the evaluation type/valuation rule.

Reference Entity for Your Business Partner (in the Counterparty role)

The standard implementation first checks the settings that you have made in the evaluation type/valuation rule on the Evaluation Control tab in the Credit Spread Curve Derivation area.

If you have not made an entry in the Business Partner Relationship Category field, the system searches for a reference entity for the business partner of the transaction.

If you have specified a relationship category in the Business Partner Relationship Category field, the system first determines which business partner is connected to another business partner by means of this relationship category, and it then searches for the reference entity for that connected business partner. You can use the relationship category, for example, to valuate a business partner using the credit spread of the parent group. In this case, you would choose, in the evaluation type/valuation rule, the relationship category that is assigned to a subsidiary.

If the business partner stored in the business partner master data is not connected to another business partner by means of this relationship category, the system determines the reference entity for the business partner of the transaction.

If the system does not find any reference entities for the business partners determined in this way, it searches in the assignment table Assign Reference Entities to Business Partners (transaction RMBPRE_ASSIGN) for a reference entity that is assigned to the business partner.

[figure TRM02-F249 - Standard Derivation for Securities Positions]

Standard Derivation for Securities Positions

The system first searches for a reference entity for the securities ID number. If there is no reference entity for the ID number, the system searches for the reference entity of the issuer. The business partner is used for asset positions, and the company code is used for liabilities positions. The remaining steps of the procedure are the same as those for OTC transactions.

[figure TRM02-F250]

Determining the Credit Spread Curve

The credit spread curve is achieved from the credit spread curve structure assigned to the reference entity determined and from the designation "Bid" versus "Ask".

- 3. Creation of a Composite Curve


First, the yield curve, the basis spread curves, and the credit spread curves are built. As a result, the relevant zero rates are available. See also:Creation of Yield Curves, Basis Spreads and Basis Spread Curves, and Credit Spreads and Credit Spread Curve Structures

Now the composite curve is constructed by adding the zero rates to the grid points of the ʻleading’ yield curve. The grid points of the yield curve are copied to the composite curve. If necessary, interpolation or extrapolation is used to calculate the zero rates of the basis spread curves and the credit spread curves.

Interpolation

Based on the composite curve, interpolation is performed in the same way as the procedure for yield curves. See also: Interpolation

**Extrapolation**

Based on the composite curve, extrapolation is performed in the same way as the procedure for yield curves. See also: Extrapolation

Calculation of Interest Rates from the Composite Curve

Based on the composite curve, interest rates are calculated in the same way as the procedure for yield curves. See also: Calculate Interest Rates from the Yield Curve Generated

###### Fixed-Term Deposit

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Examples > Fixed-Term Deposit | L6 | trm01 p.8 | loio `e1fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e1fdc5536a51204be10000000a174cb4.html?locale=en-US)

A fixed-term deposit is an interest rate instrument within the money market area with a fixed interest condition and final repayment. This includes the transaction types fixed-term deposit investment and fixed-term deposit borrowing.

Deposit at Notice

Deposits at notice are investments or borrowings without a fixed term. The deposit at notice function therefore not only includes the functions available in the fixed-term deposit area, but also a function for giving notice. This means that, in addition to entering the amounts and conditions, you enter the notice period and the interest payment date and frequency.

Commercial Paper

Commercial Paper transactions are transactions on which no interest payments are made during the term of the transaction. Instead, two business partners agree on a repayment amount to be repaid to the investor by the borrower at the end of the life of the contract.

Cash Flow Transaction

With cash flow-based transactions you can manage transactions whose structural characteristics cannot be mapped by the standard product categories. You can enter and process transactions by entering their cash flow. A cash flow is a chronological sequence of flows: you enter the term alongside the cash flow that results from the transaction structure. This enables you to map your financial transactions flexibly.

Interest Rate Instrument

An interest rate instrument is a money market transaction with additional structural characteristics, such as Fixed, Variable, Scaled (Incremental), and Scaled (Interval) interest conditions.

Interest rate instruments with term category Fixed-Term have a repayment method (for example, final repayment, installment repayment, or annuity repayment).

Interest rate instruments with term category At Notice do not have term end dates. The repayment flow is generated only when the Give Notice function is executed.

To calculate the corresponding interest receivables or payables for variable interest conditions, you must make an interest rate adjustment. See Adjust Variable Rates/Prices.

Bilateral Facility

Facilities are agreements between a lender and a borrower, which control the general conditions for a series of drawings against a credit line. The lender can give drawing authorization to several people (= borrowers), who are entitled to draw varying amounts at any time up to the total approved credit line. The utilization of this credit option for a facility is called a drawing. The lender calculates charges for the borrower (commitment interest). The charges that incur are calculated according to different methods.

Current Account-Style Instrument

Current account-style instruments are similar to interest rate instruments. The difference between the two kinds of instrument lies in that the current account-style instruments support negative nominals while the interest rate instruments do not, and that the current account-style instruments support final repayment only whereas interest rate instruments support installment repayment and annuity repayment in addition to final repayment.

Fiduciary Deposits

TThe fiduciary deposit is a cash-flow-based instrument that is used in insurance (pension) business. There are two parties involved in the financial transaction:

Depositor

Fiduciary

IIn order to reconcile the premiums received from investors, the depositor must report assets in his balance sheet. To this end, they negotiate with the fiduciary entity and the fiduciary agrees to pay a fixed cash flow to the depositor every month. This tender consists of two parts:

Repayment

Interest flows

As a rule, the duration of fiduciary deposits is 30 years or more.

Derivatives

Interest Rate Derivatives

Swaps

A swap is an exchange of payment flows over a fixed period. You define these payment flows when you conclude a swap. However, their absolute amount may depend on future events (such as variable interest payments, where the amounts depend on the level of reference interest rates in the future). With swaps, the interest rate flows are generated according to the interest rate condition. You use swaps to perform liquidity control in your company and to recognize, analyze, and hedge against interest rate risks.

Examples:

Interest Rate Swap

Interest rate swaps are transactions that exchange payment flows on the basis of different interest rates in the same currency. You agree on a certain term, usually over a year. An interest rate swap enables you to hedge possible interest rate risks.

Cross-Currency Interest Rate Swap

A currency swap is an exchange of payment flows comprising interest payments and capital payments in different currencies at an agreed exchange rate. You can use currency swaps to hedge possible currency risks. They also allow you cheaper access to the respective foreign currency markets.

Caps/Floors

Forward Rate Agreements (FRAs)

OTC Options

Repos (Buy/Sell Back Transactions)

Securities Lending

Forward Securities Transactions

Forward Loan Purchases

Total Return Swap

Listed Derivatives

Listed Options

Futures

Securities

Stocks

A stock represents a share in a stock corporation. The owner of the share receives dividends. For stocks, the product category Stocks is available. You can define different kinds of stocks, such as

Common stocks and preference stocks

Fully and partially paid stocks

Investment Funds

An investment fund is a share in a fund that is managed by an investment trust. The owner of the share receives dividends but does not have other rights. For investment funds, the product category Investment Fund is available.

Bonds

Bonds are interest-bearing securities that guarantee the payment of interests and the repayment at the end of term. You can create the class data for bonds using product category 040 (Bonds). In addition, specific product categories are available, such as, 042 Installment Bond, 060 Warrant Bond, and 070 Convertible Bond. You can create different kinds of bond by defining class data and the conditions accordingly:

Fixed-interest bonds

Floating-rate notes

Zero-coupon bonds

You can manage the following processes for bonds:

Issuing Bonds

Investing in Bonds

These processes cover master data management, the trading and processing of securities transactions (including the placement and redemption of issued bonds), as well as paying and posting in Financial Accounting. In addition, various functions for managing security positions and for period-end closing are available. Treasury Reporting provides you with a broad range of apps for analyzing your debts and investments in bonds.

**Business Benefits**

Review the financial status

Automate the management of investments and borrowings, including creation of the financial transaction, confirmation of contracts with counterparties, payments, interest rate adjustments, and accounting

Take better operational and strategic decisions using the comprehensive reporting and analysis tools

Improve internal operational compliance, such as by setting counterparty limits

Increase your focus on value-added activities instead of on manual procedures

**Key process flows covered**

Create and process financial transactions

Automated correspondence (external and/or internal confirmations)

Process payments including condition-based incoming payments, such as dividends

Transfer values to the general ledger

Adjust interest rates and update planned records for securities

Perform month-end accounting processes

Monitor and report your treasury positions and financial transactions

###### Account as a Variable Transaction

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Examples > Account as a Variable Transaction | L6 | trm03 p.117 | loio `3bfec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3bfec5536a51204be10000000a174cb4.html?locale=en-US)

Savings account and current account transactions are variable transactions with conditions that are based on the market, although this usually just means that there is some connection with the basic market trend. Due to the special nature of accounts (core deposits, seemingly fixed conditions), account balances are taken into account only when you use due date scenarios in the evaluations. Otherwise they are set immediately to 100% due.

Up to now, neither the account transactions themselves nor the due date scenarios are linked to market conditions. The interest rates fixed for the account are used for the evaluation. For this reason, scenario progressions have no impact on account balances. For planning new business, the account balance can be set to become due at the evaluation date. The planning can be done completely on the basis of money market transactions concluded at market conditions.

**Example**

Balance on the evaluation date: EUR 40,000.00

Nominal interest on liability side: 2.20% p.a.

Applied due date scenario: due dates are set relative to the evaluation date→in monthly intervals 40%, 30%, 20% and 10% (base amount 20%)

Evaluation date: 11/15/2000


Settings in the ALM valuation type

Interest calculation method: 360/360

OI determination: Use calculated opportunity interest rate


Evaluations of account transactions always refer to the balance current on the evaluation date. Any subsequent changes to the balance are ignored.

**Average position**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest rate|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|11/15/2000| | | |40,000.00|2.20|3.00| |40,000.00|
|11/30/2000| | | |40,000.00|2.20|3.00| |40,000.00|
|12/15/2000| | | |38,933.33|2.20|3.00| |38,933.33|
|12/30/2000| | | |24,000.00|2.20|3.00| |24,000.00|
|01/30/2001| | | |17,806.45|2.20|3.00| |17,806.45|
|02/28/2001| | | |10,068.97|2.20|3.00| |10,068.97|



How is the average liability volume of EUR 17,806.45 at the maturity band date 01/30/2001 calculated?

In the period from 01/31/2000 to 01/14/2000 (15 days) the liabilities-side volume is EUR 4,000.00, whereas in the period from 01/15/2001 to 01/30/2001 (16 days) it is EUR 2,000.00. Based on this data, the average liability volume is calculated as follows:

(15 x 24,000.00 + 16 x 12,000.00)/31 = EUR17,806.45


Where does the opportunity interest rate of 3.00 % displayed in the liabilities-side OI column come from?

In the evaluation type, the OI determination field has been set to Use calculated OI . The liabilities-side OI column therefore displays the opportunity interest rate calculated by the Profitability Analysis component for the Asset/Liability Management component. Note that a different interest rate is used in Profitability Analysis from that used in ALM as the opportunity interest rate. For more information about opportunity interest, see Opportunity Interest Determination in ALM .

**Key date position**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|11/15/2000| | | |40,000.00|2.20|3.00| |40,000.00|
|11/30/2000| | | |40,000.00|2.20|3.00| |40,000.00|
|12/15/2000| | | |24,000.00|2.20|3.00| |24,000.00|
|12/30/2000| | | |24,000.00|2.20|3.00| |24,000.00|
|01/30/2001| | | |12,000.00|2.20|3.00| |12,000.00|
|02/28/2001| | | |8,000.00|2.20|3.00| |8,000.00|



Why is the liability volume at key date 07/30/2000 EUR 8,000.00 and not EUR 4,000.00?

Based on the due date scenario used, and starting from the evaluation date 11/15/2000, the following liabilities-side outflows are assumed:

12/15/2000 EUR 16,000.00 (40%)

- 01/15/2001 EUR 2,000.00 (30%)
- 02/15/2001 EUR 8,000.00 (20%)→the specified base amount is 20% (EUR 8,000.00). So that the value does not fall below the base amount, the liabilities-side outflow is reduced to EUR 4,000.


The key date position on 02/28/2000 is therefore calculated as follows:

EUR 40,000.00 – EUR 16,000.00 – EUR 12,000.00 – EUR 4,000.00 = EUR 8,000

Settings in the ALM valuation type

Interest calculation method: 360/360

OI determination: Use calculated opportunity interest rate

**Maturity evaluation**

|Maturity band date|Asset-side outflow|Asset-side interest|Asset-side opportunity interest|Liabilityside outflow|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|11/15/2000| | | | | | | | |
|11/30/2000| | | | | | | | |
|12/15/2000| | | |16,000.00|2.20|3.00| |16,000.00|
|12/30/2000| | | | | | | | |
|01/30/2001| | | |12,000.00|2.20|3.00| |12,000.00|


|Maturity band date|Asset-side outflow|Asset-side interest|Asset-side opportunity interest|Liabilityside outflow|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|02/28/2001| | | |4,000.00|2.20|3.00| |4,000.00|


**Cash flow evaluation**

|Maturity band date|Inpayment|Disbursement|Gap|
|---|---|---|---|
|11/15/2000| | | |
|11/30/2000| | | |
|12/15/2000| |16,000.00|-16,000.00|
|12/30/2000| | | |
|01/30/2001| |12,000.00|-12,000.00|
|02/28/2001| |4,000.00|-4,000.00|



Why are you unable to see any interest cash flows in the cash flow evaluation?

You see the liquidity from interest only if you have assigned simulated interest payments to the account. The procedure is the same as that for the (currency) liquidity evaluation.

Settings in the ALM valuation type

Interest calculation method: 360/360

OI determination: Use calculated opportunity interest rate

Liquidity evaluation

|Maturity band date|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|
|---|---|---|---|---|
|11/15/2000| | | | |
|11/30/2000| | | | |
|12/15/2000| |16,000.00|-16,000.00|-16,000.00|
|12/30/2000| | | |-16,000.00|
|01/30/2001| |12,000.00|-12,000.00|-28,000.00|
|02/28/2001| |4,000.00|-4,000.00|-32,000.00|


Currency liquidity

|Maturity band date|Transaction Currency|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|Evaluation currency or transaction currency (as per the setting for the data relevant for display)|
|---|---|---|---|---|---|---|
|11/15/2000|EUR| | | | |EUR|
|11/30/2000|EUR| | | | |EUR|
|12/15/2000|EUR| |16,000.00|-16,000.00|-16,000.00|EUR|
|12/30/2000|EUR| | | |-16,000.00|EUR|
|01/30/2001|EUR| |12,000.00|-12,000.00|-28,000.00|EUR|
|02/28/2001|EUR| |4,000.00|-4,000.00|-32,000.00|EUR|

###### Fixed-Rate Loan with Discount

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Examples > Fixed-Rate Loan with Discount | L6 | trm03 p.121 | loio `0efec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0efec5536a51204be10000000a174cb4.html?locale=en-US)

Commitment capital: EUR 120,000

Disbursement rate: 90%

Term: 12/31/1999 to 12/31/2003

Annual installment repayment: EUR 30,000

Nominal interest per annum: 10% (interest calculation method 360/360)

Cash flow:

|Payment date|Payment amount|Type of flow|
|---|---|---|
|12/31/1999|EUR -120,000.00|Loan disbursement|
|12/31/1999|EUR +12,000.00|Discount|
|12/31/2000|EUR +12,000.00|Interest|
|12/31/2000|EUR +30,000.00|Installment repayment|
|12/31/2001|EUR +9,000.00|Interest|
|12/31/2001|EUR +30,000.00|Installment repayment|
|12/31/2002|EUR +6,000.00|Interest|
|12/31/2002|EUR +30,000.00|Installment repayment|
|12/31/2003|EUR +3,000.00|Interest|
|12/31/2003|EUR +30,000.00|Installment repayment|


Evaluation date : 10/13/2000


Settings in the ALM valuation type

Display premium/discount: Gross display of discount

Interest calculation method: 360/360

Static indicator: Static interest rate

**Average position**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/13/2000|120,000.00|14.0|10.0|12,000.00| | |108,000.00| |
|03/30/2001|103,928.57|14.0|10.0|9,428.57| | |94,500.00| |
|06/30/2001|90,000.00|14.0|10.0|7,200.00| | |82,800.00| |
|06/30/2002|75,041.10|14.0|10.0|5,404.93| | |69,636.17| |
|09/30/2003|42,013.13|14.0|10.0|2,161.05| | |39,852.08| |
|03/30/2004|15,000.00|14.0|10.0|600.00| | |14,400.00| |



How is the asset-side interest calculated to be 14%?

In the ALM valuation type, the StatInd field (static interest) was set to Static interest rate . In discount transactions, the static interest rate describes an approximation of the effective interest rate. The discount is distributed, volume-weighted, to the remaining interest payment dates. The static interest rate is calculated as follows:

Total of all interest payments: 12,000.00 + 9,000.00 + 6,000.00 + 3,000.00 = EUR 30,000.00

Discount: EUR 12,000.00

Total of all nominal capital, taking into account the interest calculation method: 120,000.00 x 360/360 + 90,000.00 x 360/360 + 60,000.00 x 360/360 +30,000.00 = EUR 300,000

Total of all interest payments plus the discount, divided by the total nominal capital (30,000.00


+12,000.00)/300,000.00 = 0.14 14.0 %


How is the average asset-side volume of EUR 103,928.57 at the maturity band date 03/30/2001 calculated?

In the period from 10/14/00 to 12/30/00 (78 days) the asset-side volume is EUR 120,000.00. In the period from 12/31/2000 to

- 03/30/2001 (90 days) it is EUR 90,000.00. Based on this data, the average asset volume is calculated as follows:


(78 x 120,000.00+90 x 90,000.00)/168= EUR 103,928.57


How is the average asset-side volume of EUR 9,428.57 at the maturity band date 03/30/2001 calculated?

(78 x 12,000 + 90 x 7,200.00)/168 = EUR 9,428.57


Why is a liability volume displayed?

As the Gross display of the premium/discount is set in the ALM valuation type, the discount is displayed as a liability-side item in the column for liability volume.


Where does the asset-side opportunity interest rate come from?

Since the OI Determination field is not maintained in the ALM valuation type, the product interest rate (default setting) is displayed as the opportunity interest .

**Key date position**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/13/2000|120,000.00|14.0|10.0|12,000.00| | |108,000.00| |
|03/30/2001|90,000.00|14.0|10.0|7,200.00| | |82,800.00| |
|06/30/2001|90,000.00|14.0|10.0|7,200.00| | |82,800.00| |
|06/30/2002|60,000.00|14.0|10.0|3,600.00| | |56,400.00| |
|09/30/2003|30,000.00|14.0|10.0|1,200.00| | |28,800.00| |
|03/30/2004| | | | | | | | |


Settings in the ALM valuation type

Display premium/discount: Gross display of discount

Interest calculation method: 360/360

Static indicator: Static interest rate

**Maturity evaluation**

|Maturity band date|Asset-side outflow|Asset-side interest|Asset-side opportunity interest|Liabilityside outflow|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/13/2000| | | | | | | | |
|03/30/2001|30,000.00|14.0|10.0|4,800.00| | |25,200.00| |
|06/30/2001| | | | | | | | |
|06/30/2002|30.000.00|14.0|10.0|3,600.00| | |26,400.00| |
|09/30/2003|30,000.00|14.0|10.0|2,400.00| | |27,600.00| |
|03/30/2004|30,000.00|14.0|10.0|1,200.00| | |28,800.00| |



How is the liability outflow of EUR 4,800.00 at the maturity band date 03/30/2001 calculated?

The discount is distributed, volume-weighted, to the interest payment dates. This results in a liability-side outflow of EUR 4,800.00 for the maturity band date 03/30/2001, which is calculated as follows:

Discount x nominal capital / total of all nominal capital 12,000.00 x 120,000.00/300,000=4,800.00


**Cash flow evaluation**

|Maturity band date|Inpayment|Disbursement|Gap|
|---|---|---|---|
|10/13/2000| | | |
|03/30/2001|42,000.00| |42,000.00|
|06/30/2001| | | |
|06/30/2002|39,000.00| |39,000.00|
|09/30/2003|36,000.00| |36,000.00|
|03/30/2004|33,000.00| |33,000.00|


Settings in the ALM valuation type

Display premium/discount: Gross display of discount

Interest calculation method: 360/360

Static indicator: Static interest rate

Liquidity evaluation

|Maturity band date|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|
|---|---|---|---|---|
|10/13/2000| | | | |
|03/30/2001|42,000.00| |42,000.00|42,000.00|
|06/30/2001| | | |42,000.00|
|06/30/2002|39,000.00| |39,000.00|81,000.00|
|09/30/2003|36,000.00| |36,000.00|117,000.00|
|03/30/2004|33,000.00| |33,000.00|150,000.00|


Currency liquidity

|Maturity band date|Transaction Currency|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|Evaluation currency or transaction currency (as per the setting for the data relevant for display)|
|---|---|---|---|---|---|---|
|10/13/2000|EUR| | | | |EUR|
|03/30/2001|EUR|42,000.00| |42,000.00|42,000.00|EUR|
|06/30/2001|EUR| | | |42,000.00|EUR|
|06/30/2002|EUR|39,000.00| |39,000.00|81,000.00|EUR|
|09/30/2003|EUR|36,000.00| |36,000.00|117,000.00|EUR|
|03/30/2004|EUR|33,000.00| |33,000.00|150,000.00|EUR|


**Net interest income evaluation**

|Maturity band date|Balance sheet asset volume|Assetside interest|Asset-side opportunity interest|Interest revenue from product interest rate|Interest revenue (opportunity interest rate)|Conditions contribution -asset side|Balance sheet liability volume|Absolute interest income|Relative interest result|N i m|
|---|---|---|---|---|---|---|---|---|---|---|
|10/13/2000|120,000.00| | | | | |12,000.00| | | |
|03/30/2001|103,832.34|14.0|10.0|6,743.33|4,816.67|4.00|9,413.17|6,743.33|14.0|4|
|06/30/2001|90,000.00|14.0|10.0|3,150.00|2,250.00|4.00|7,200.00|3,150.00|14.0|4|
|06/30/2002|75,000.00|14.0|10.0|10,500.00|7,500.00|4.00|5,400.00|10,500.00|14.0|4|
|09/30/2003|42,000.00|14.0|10.0|7,350.00|5,250.00|4.00|2,160.00|7,350.00|14.0|4|
|03/30/2004|15,000.00|14.0|10.0|1,050.00|750.00|4.00|600.00|1,050.00|14.0|4|
|06/30/2004| | | | | | | | | | |



How is the interest revenue for product interest amounting to EUR 6,743.33 at the maturity band date 03/30/2001 calculated?

The net interest income evaluation displays the net interest income of a bank distributed over time. The basis for the calculation of the net interest income are the values determined in the average position evaluation. Note, however, that the average positions determined in the average position evaluation are calculated taking account of the maturity band. This means they are calculated on the basis of 365 or 366 days. In the net interest income evaluation, the interest calculation method defined in the ALM evaluation type is taken into account instead. The system determines the average balance sheet volume from the average position.

If the 360/360 interest calculation method is used, there are only 77 days between 10/14/2000 and 12/31/2000.

( 77 x 120,000.00+90 x 90,000.00)/ 167 = EUR 103,832.34

The amount EUR 6,743.33 is calculated as follows:

10/14/2000 – 03/30/2001, 167 days when using the interest calculation method 360/360, asset-side interest rate 14% 103,832.34 x 167/360 x 0.14 = 6,743.33



How is the interest revenue for product interest amounting to EUR 4,816.67 at the maturity band date 03/30/2001 calculated?

10/14/2000 - 03/30/2001, 167 days, asset-side opportunity interest rate 10% 103,832.34 x 167/360 x 0.10 = EUR 4816.67

###### Plain Vanilla Interest Rate Swap

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Examples > Plain Vanilla Interest Rate Swap | L6 | trm03 p.126 | loio `1dfec5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1dfec5536a51204be10000000a174cb4.html?locale=en-US)

Payer swap

Nominal amount: EUR 100,000

Fixed interest: 6% nominal, annual interest payment, interest calculation method 360/360

Variable interest rate: 3-month euribor, interest calculation method act/365

Term: 12/05/2000 - 12/05/2003

Cash flow:

|Payment date|Payment amount|Type of flow|
|---|---|---|
|12/05/2000|EUR +100,000.00|Nominal amount increase (not relevant for posting)|
|12/05/2000|EUR -100,000.00|Nominal amount increase (not relevant for posting)|
|12/03/2001|EUR +0.00|Variable interest|
|12/06/2001|EUR +0.00|Variable interest|
|12/09/2001|EUR +0.00|Variable interest|
|12/05/2001|EUR +0.00|Variable interest|
|12/05/2001|EUR -6,000.00|Fixed interest|
|12/03/2002|EUR +0.00|Variable interest|
|12/06/2002|EUR +0.00|Variable interest|
|12/09/2002|EUR +0.00|Variable interest|
|12/05/2002|EUR +0.00|Variable interest|
|12/05/2002|EUR -6,000.00|Fixed interest|
|12/03/2003|EUR +0.00|Variable interest|
|12/06/2003|EUR +0.00|Variable interest|
|12/09/2003|EUR +0.00|Variable interest|


|Payment date|Payment amount|Type of flow|
|---|---|---|
|12/05/2003|EUR +0.00|Variable interest|
|12/05/2003|EUR +100,000.00|Closing (not relevant for posting)|
|12/05/2003|EUR -100,000.00|Closing (not relevant for posting)|
|12/05/2003|EUR -6,000.00|Fixed interest|



The nominal amounts displayed are fictitious capital amounts. The interest rates on the variable side were not fixed yet.

Evaluation date : 10/29/2000


Settings in the ALM valuation type

Outflow indicator: Negative outflows on same balance sheet side

Interest calculation method: act/365

Balance sheet volume in net interest income: Off-balance sheet transactions not included

**Average position (interest commitment)**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/29/2000| | | | | | | | |
|10/30/2001| | | |90,163.93|6.00|6.00| |90,163.93|
|01/30/2002| | | |100,000.00|6.00|6.00| |100,000.00|
|01/30/2003| | | |100,000.00|6.00|6.00| |100,000.00|
|04/30/2004| | | |67,543.86|6.00|6.00| |67,543.86|



Since this is the average position evaluation for the interest commitment, and the 3-month euribor has not been fixed for 05/12/2000 or any of the subsequent dates, the asset-side columns remain empty. The same applies to the key date position and maturity evaluations for the interest commitment .


How is the average liability volume of EUR 90,163.93 calculated?

In the period from 10/30/2000 to 12/04/2000 (36 days) the liability volume is EUR 0.00, whereas in the period from 12/05/2000 to 10/30/2001 (330 days) it is EUR 100,000.00. Based on this data, the average liability volume is calculated as follows:

(36 x 0.00+330 x 100,000.00)/366 = EUR 90,163.93


In the case of derivative transactions, the product interest is used as the opportunity interest . You can also transfer an opportunity interest rate as an external key figure. If you want to use this option, you have to set the OI determination indicator in the ALM valuation type to External key figure .

**Average position (capital commitment)**

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/29/2000| | | | | | | | |
|10/30/2001|90,163.93|3.537|3.537|90,163.93|6.00|6.00| | |
|01/30/2002|100,000.00|3.037|3.037|100,000.00|6.00|6.00| | |
|01/30/2003|100,000.00|2.658|2.658|100,000.00|6.00|6.00| | |
|04/30/2004|67,543.86|3.540|3.540|67,543.86|6.00|6.00| | |



In the average position evaluation for the capital commitment, the variable side of the swap is shown as well. The forward rate determined by the system for the respective maturity band date is displayed as the asset-side interest rate. The same applies to the key date position and maturity evaluations for the capital commitment .

Settings in the ALM valuation type

Outflow indicator: Negative outflows on same balance sheet side

Interest calculation method: act/365

Balance sheet volume in net interest income: Off-balance sheet transactions not included

Key date position (interest commitment)

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/29/2000| | | | | | | | |
|10/30/2001| | | |100,000.00|6.00|6.00| |100,000.00|
|01/30/2002| | | |100,000.00|6.00|6.00| |100,000.00|
|01/30/2003| | | |100,000.00|6.00|6.00| |100,000.00|
|04/30/2004| | | | | | | | |


Key date position (capital commitment)

|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/29/2000| | | | | | | | |
|10/30/2001|100,000.00|3.345|3.345|100,000.00|6.00|6.00| | |


|Maturity band date|Asset volume|Asset-side interest|Asset-side opportunity interest|Liability volume|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|01/30/2002|100,000.00|2.848|2.848|100,000.00|6.00|6.00| | |
|01/30/2003|100,000.00|3.309|3.309|100,000.00|6.00|6.00| | |
|04/30/2004| | | | | | | | |


Settings in the ALM valuation type

Outflow indicator: Negative outflows on same balance sheet side

Interest calculation method: act/365

Balance sheet volume in net interest income: Off-balance sheet transactions not included

**Maturity evaluation (interest commitment)**

|Maturity band date|Asset-side outflow|Asset-side interest|Asset-side opportunity interest|Liabilityside outflow|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/29/2000| | | | | | | | |
|10/30/2001| | | |-100,000.00|6.00|6.00|100,000.00| |
|01/30/2002| | | | | | | | |
|01/30/2003| | | | | | | | |
|04/30/2004| | | |100,000.00|6.00|6.00| |100,000.00|



The negative outflows on same balance sheet side setting in the ALM valuation type causes the system to display the liability-side inflow of EUR 100,000.00 in the liability-side outflow column with a minus sign (maturity band date 10/30/01). If you want the liability-side inflow to be displayed as an asset-side outflow, choose the default setting negative outflows on other balance sheet side .

**Maturity evaluation (capital commitment)**

|Maturity band date|Asset-side outflow|Asset-side interest|Asset-side opportunity interest|Liabilityside outflow|Liabilityside interest|Liabilityside opportunity interest|Asset gap|Liability gap|
|---|---|---|---|---|---|---|---|---|
|10/29/2000| | | | | | | | |
|10/30/2001|-100,000.00|2.804|2.804|-100,000.00|6.00|6.00| | |
|01/30/2002| | | | | | | | |
|01/30/2003| | | | | | | | |
|04/30/2004|100,000.00|4.017|4.017|100,000.00|6.00|6.00| | |


Settings in the ALM valuation type

Outflow indicator: Negative outflows on same balance sheet side

Interest calculation method: act/365

Balance sheet volume in net interest income: Off-balance sheet transactions not included

**Cash flow evaluation**

|Maturity band date|Inpayment|Disbursement|Gap|
|---|---|---|---|
|10/29/2000| | | |
|10/30/2001|100,000.00| |100,000.00|
|01/30/2002| |6,000.00|-6,000.00|
|01/30/2003| |6,000.00|-6,000.00|
|04/30/2004| |106,000.00|-106,000.00|



The cash flow evaluation and the liquidity evaluation differ in that the cash flow evaluation displays cash flows for the interest commitment only.

**Liquidity evaluation**

|Maturity band date|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|
|---|---|---|---|---|
|10/29/2000| | | | |
|10/30/2001|2,684.73| |2,684.73|2,684.73|
|01/30/2002|833.95|6,000.00|-5,166.05|-2,481.32|
|01/30/2003|2,586.13|6,000.00|-3,413.87|-5,895.19|
|04/30/2004|3,503.71|6,000.00|-2,496.29|-8,391.48|



The interest and capital payments flow into the liquidity evaluation in accordance with the capital commitment of the underlying transactions. Since the capital payments in a plain vanilla swap do not actually flow in reality, and only serve as a basis for the interest calculation, they are not taken into account in the liquidity evaluation. However, they are displayed in the other evaluations.


How is the incoming payment of EUR 2,684.73 at the maturity band date 10/30/2001 calculated?

Up to 10/30/2001, variable interest flows on 03/05/2001, 06/05/2001 and 09/05/2001. The amount of the interest payment is determined using the forward rate calculated by the system for the relevant date. This results in the following figures:

12/05/00 – 03/04/01 is 90 days, forward rate 2.8037511% 100,000.00 x 90/365 x 0.028037511 = 691.34.


03/05/01 – 06/04/01, 92 days, forward rate 3.8284709% 100,000.00 x 92/365 x 0.038284709 = 964.98.


06/05/01 – 09/04/01, 92 days, forward rate 4.0801246% 100,000.00 x 92/365 x 0.040801246 = 1028.41.


This gives a total amount of EUR 2,684.73.

Currency liquidity

|Maturity band date|Transaction currency|Inpayment|Disbursement|Liquidity gap|Cumulated liquidity gap|Evaluation currency or transaction currency (as per the setting for the data relevant for display)|
|---|---|---|---|---|---|---|
|10/29/2000|EUR| | | | |EUR|
|10/30/2001|EUR|2,684.73| |2,684.73|2,684.73|EUR|
|01/30/2002|EUR|833.95|6,000.00|-5,166.05|-2,481.32|EUR|
|01/30/2003|EUR|2,586.13|6,000.00|-3,413.87|-5,895.19|EUR|
|04/30/2004|EUR|3,503.71|6,000.00|-2,496.29|-8,391.48|EUR|


Net interest income evaluation

|Maturity band date|Interest revenue from product interest rate|Interest revenue (opportunity interest rate)|Interest expense (product interest rate)|Interest expense (opportunity interest rate)|Absolute interest income|
|---|---|---|---|---|---|
|10/29/2000| | | | | |
|10/30/2001|3.197,93|3.197,93|5.424,66|5.424,66|-2.226,73|
|01/30/2002|765,45|765,45|1.512,33|1.512,33|-746,88|
|01/30/2003|2.658,23|2.658,23|6,000.00|6,000.00|-3.341,77|
|04/30/2004|2.986,92|2.986,92|5.063,01|5.063,01|-2.076,09|



How is the interest revenue for product interest of EUR 3,197.93 at the maturity band date 10/30/2001 calculated?

The net interest income evaluation displays the net interest income of a bank distributed over time. The basis for the net interest income calculation are the values determined in the average position evaluation. Note, however, that the average positions determined in the average position evaluation are calculated taking account of the maturity band. This means they are calculated on the basis of 365 or 366 days. In the net interest income evaluation, the interest calculation method defined in the ALM evaluation type is taken into account instead. Using the act/360 interest calculation method makes no difference in this case.

The amount EUR 3,197.93 is calculated as follows:

10/30/00 – 10/30/01,. 366 days, forward rate 3.5371046% 90,163.93 x 366/365 x 0.035371046 = 3,197.93



How is the interest revenue for product interest amounting to EUR 5,424.66 at the maturity band date 03/30/2001 calculated?

- The amount EUR 5,424.66 is calculated as follows:


10/30/00 -10/30/01, 366 days 90,163.93 x 0.06 x 366/365 = EUR 5,424.66.

###### Scenario

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Scenario | L5 | trm03 p.132 | loio `a11d0f5374978320e10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a11d0f5374978320e10000000a423f68.html?locale=en-US)

**Definition**

Scenarios are complete sets of market data.

You create scenarios. By creating a scenario, you define a market situation that you consider possible or probable, such as a period of high interest rates with an inverse yield curve.

In Risk Management, you can use scenarios to analyze the effects of market price changes on the risk position of your company. Consequently, scenarios play a significant role in the planning and controlling of a company’s risk situation.

**Structure**

You can define the following in a scenario:

Exchange rates

Yield curves

Basis spreads

Credit spreads

Security indexes

Security prices

Volatilities

A scenario defines only a subset of selected market data within the current market data. In the case of market data that is not found within the specified scenario, the system applies for the valuation the latest market data available on the horizon.

**Example:**

To depict a historical market situation, you can define a scenario into which you can import historical market data.

**Integration**

You do not specify a validity period for the scenario. When you start an evaluation in Market Risk Management or a gap analysis/ALM simulation, you specifying the horizon to define the calendar date to be used for the evaluation of the scenario in question.

In the evaluations, the system reads only the scenario values for which the rate category or volatility type matches the evaluation type settings. Otherwise, the current market data is applied.

Exception:

If foreign exchange rates and security indexes are defined in the scenario, the system reads them from the current market data, irrespective of the rate category or index type. In this case, the evaluation type defines how the system interprets the scenario values.

**Editing Scenarios**

**Context**

Scenarios are complete sets of market data.

You create scenarios. By creating a scenario, you define a market situation that you consider possible or probable, such as a period of high interest rates with an inverse yield curve.

See also: Scenario

**Procedure**

- 1. Choose Treasury and Risk Management Market Risk Analyzer Simulation Scenarios Scenario Administration .
- 2. The Scenario Administration: Initial Screen appears.
- 3. Enter the name of the scenario or a new name. To edit it, choose Create, Change, Display, or Delete.
- 4. To create a scenario, enter a name in the Scenario Full Name field for the input help and a name in the Scenario Short Name field.
- 5. If you want to activate an additional authorization check, assign an authorization group to this scenario on the Admin. Data tab.
- 6. Enter the required data on the relevant tab. To enter new entries, choose Insert Line.


**Note:**

For fast entry, you can create a scenario on the basis of an existing scenario (Create with Reference). In this way, the data of the scenario used as a reference is copied.

**Note:**

You define authorization groups in Customizing under Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings Maintain Authorizations/Profiles/Users Maintain Authorization Groups

.


Exchange Rates:

Always enter a reference currency and then choose Continue. In the Currency field, enter the (foreign) currency for which you want to define an exchange rate scenario. Enter a bid rate and an ask rate. When you choose Continue,

the From Crcy und To Crcy fields are filled automatically on the basis of the settings that you have made in Customizing for Treasury and Risk Management (TRM) under Transaction Manager General Settings

Transaction Management Currencies Define Leading Currency .

Yield Curves:

To be able to enter interest rates for yield curves, enter a currency and a yield curve type (YC Type) and choose Continue. To edit interest rates, select the relevant line and choose Curve Interest Rates. On the Create Grid Points for Yield Curves screen, enter the scenario interest rates. The system proposes all reference interest rates for the specified yield curve.

You can view and change the selected yield curve by choosing Graphic. For general information about how to use the graphic, choose the Help pushbutton. You can change the yield curve in the graphic mode by double-clicking a grid point. The SAP Presentation Graphic offers you the following options for changing yield curves:

|Function|Procedure|Result|
|---|---|---|
|Interpolation|Choose Interpolation, select two grid points by dragging them with the cursor (the text of the grid points is|The yield curve is interpolated between the selected grid points.|


|Function|Procedure|Result|
|---|---|---|
| |then changed to ***), and choose the interpolation type Polynominal, Splines, or Linear.| |
|Mirroring|Choose Mirroring and then doubleclick a grid point.|The yield curve is mirrored at the selected grid point.|
|Overall Shift|Choose Overall Shift and then use the cursor to shift a grid point.|All grid points are shifted by the selected amount.|
|Rotation|Choose Rotation, double-click the grid point about which you want to rotate (the text of the grid point is changed to ***), and then choose With Angle or With Shifts. In the case of a rotation with an angle, you can specify the angle of the rotation. Note that a change by 100 % corresponds to a rotation angle of 0.3°.|The yield curve is rotated about the selected grid point.|
|Single Shift|Choose Single Shift and then use the cursor to shift a grid point.|The grid point selected is shifted by the amount entered.|


To shift yield curves directly by a specific basis point value, choose Shift. The Shift Yield Curves screen appears. Enter the relevant basis point value for the yield curve that you want to shift. With the shift, the yield curve of the scenario is shifted by the value entered. The grid points (reference interest rates) are then determined from the shifted yield curve.

**Note:**

The shifts are applied to the reference interest rates. If you choose Shift again, you no longer see the previous shift. You can define a new shift that is nevertheless based upon the current market data.

Basis Spreads

Enter a basis spread ID and a quotation type. Then enter in basis points the basis spread value that you want to use in this scenario.

**Note:**

If you would like to change some or all of the values entered in the scenario by a specific basis point value, select the basis spread entries that you want to undergo a shift and choose the function Shift.... You can now enter the amount of the shift in basis points. Confirm your entries. The system increases or decreases the selected values by the amount of the shift. You can also use this function if you were unable to select a suitable market data shift

rule when you imported the current market data.

Credit Spreads

Choose the reference entity, the credit spread ID, and the quotation type. Then enter in basis points the credit spread value that you want to use in this scenario.

**Note:**

If you would like to change some or all of the values entered in the scenario by a specific basis point value, select the credit spread entries that you want to undergo a shift and choose the function Shift.... You can now enter the amount of the shift in basis points. Confirm your entries. The system increases or decreases the selected values

by the amount of the shift. You can also use this function if you were unable to select a suitable market data shift rule when you imported the current market data.

- 7. If you want to use current or historic data as scenario values, choose Import Current Market Data and select the desired evaluation type (which needs to have been defined previously in Customizing) and the date for which the market data needs to be imported. In addition, you can select the market data shift rule with which you want to change the market data found. Confirm your entries. In the next screen, select the market data that you want to overwrite. The system issues a log telling you which market data was found and overwritten or not found.
- 8. Choose Save.

###### Editing Scenarios

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Scenario > Editing Scenarios | L6 | trm01 p.216 | loio `481d1b513668677ce10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/481d1b513668677ce10000000a423f68.html?locale=en-US)

Manage Market Data Sets

If you want to use a filter, you must create the filter using the Define Filter function (transaction AFWFL).

The filter is a selection condition based on the analysis characteristics of the static analysis structure that is used to restrict the volume of the selected financial objects.

**Master Data**

Create a company code hierarchy called TMS_REGION using the Manage Global Hierarchies app, where you define regions and assign the corresponding company codes.

**Example:**

TMS_REGION (=root node)

APJ (Asia Pacific incl. Japan)

Assign the company codes of the region.

AMER (America)

Assign the company codes of the region.

EMEA (Europe, Middle East and Africa)

Assign the company codes of the region.

For more information, see also Manage Global Hierarchies

This setting is relevant for the Liquidity, the Cash Management, and the Bank Relationship tabs.

The Liquidity tab is based on your settings for the Financial Status – Nominal Amount (app ID W0122) and Financial Status – Book Value (app ID F2136) reporting apps. In the Define Financial Positions app, you must define your financial positions representing the asset side/liquidity of the financial status reporting of your company.

You define financial position groups for assets and financial position groups for liabilities. The financial position groups are used to structure the financial positions according to business criteria. The financial positions get their data from a specific data source (Treasury Position Management, One Exposure, or One Document Balances) according to the specific selection criteria maintained. On the Liquidity tab of the Treasury Executive Dashboard, only the financial position groups and their corresponding financial positions that represent assets are selected.

To use the Bank Relationship tab, you must first define the following master data:

Define banks (including bank rating) and house banks in the Manage Banks app.

Define bank accounts in the Manage Bank Accounts app

Define bank groups in the bank hierarchy by using the Manage Bank Accounts - Bank Hierarchy View app

The Counterparty Risk tab only monitors limit utilizations and free limits of one specific limit type for credit risk. This limit type must use the characteristics business partner and limit product group. If you would like to see data on the Counterparty Risk tab, you must define limit types with the characteristics business partner and limit product group. Then you must define limit specifications and manage limits for the limit types using the Editing Limits app.

The rating of a counterparty can change during the lifetime of your business connection. You can store the rating information time-dependent for your counterparties in the business partner master data (for more information, see alsoRating ). Enter rating information for your counterparties on the Rating tab in the master data of the business partner.

If you would like to see data on the Market Risk tab, you must define market risk key figure sets using the Manage Market Risk Key Figure Sets function (transaction AFWKF_SET).

###### Scenario Progression

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Scenario > Scenario Progression | L6 | trm03 p.135 | loio `bafdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bafdc5536a51204be10000000a174cb4.html?locale=en-US)

**Use**

Scenario progression refers to a sequence of several scenarios combined with market data shifts. This function enables more complex mapping of possible market price developments.

Using scenario progression you are able to define which market data is to apply at which particular point in time. In this way you can, for example, show an increase or rotation of the yield curve over time.

When you run gap analysis/ALM simulation, you can define on tab page Market Scenarios which scenario progression is to be used as the (reference) scenario progression, and which other scenario progressions are to be used. You are also able to switch between the relevant scenario progressions in the evaluations.

Using a scenario progression in gap analysis/ALM simulation has various effects, such as:

Variable interest references are not determined by means of forwards. Instead, the interest rate is determined using the scenario progression.

If you want to use market data for an horizon date before the current date, then historical market data is used for the horizon date.

If the entry in the scenario progression, which is the first entry from a chronological point of view, contains only one market data shift, then the system first calculates the forward market data for this scenario progression date. Then the market data shift is applied to this forward market data.

If market data is required for an horizon date after the current date and before the start of the new scenario progression, then the system determines this data by linear interpolation between the market data for the current date and the market data for the scenario defined with the earliest date in the scenario progression or market data shift.

If market data is required for an horizon date between two date values in the scenario progression, then the system determines this data by linear interpolation.

If market data is required for an horizon date that is after the last entry in the scenario progression, the system uses the data from the last entry to calculate forwards to the horizon date. The system can currently calculate forward market data for exchange rates and interest rates.

**Example**

You expect a rise in interest rates in the course of next year. By using a scenario progression, you can include this expectation in gap analysis/ALM simulation.

You define the following scenario in the system:

- 12/30/00 scenario 1 with yield curve 1

- 12/30/01 scenario 2 with yield curve 2


The system determines the yield curve for a date for which no scenario has been stored by interpolation.

[figure TRM03-F152 - The system determines the yield curve for a date for which no scenario has been stored by interpolation.]

###### Processing Scenario Progressions

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Scenario > Scenario Progression > Processing Scenario Progressions | L7 | trm03 p.136 | loio `d2fdc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d2fdc5536a51204be10000000a174cb4.html?locale=en-US)

- 1. Choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Simulation Scenarios Scenario Progression .

The system displays the maintenance transaction for entering scenario progressions.

- 2. Choose Scenario Progression: Definition.
- 3. Choose New entries.
- 4. Enter an abbreviation for a scenario progression in the field Progression.
- 5. In the Name field, enter a name for the scenario progression.
- 6. Choose Save.
- 7. Select the scenario progression that you want to process.
- 8. Choose Scenario Progression: Maintenance.

The system displays the detail maintenance screen for this scenario progression.

- 9. For each Valid On date, specify the Scenario , and/or a market data shift rule ( Rule field), until the scenario progression has the structure you require.


By setting the Use Scenario and Use Shift indicators, you specify that the relevant scenario or market data shift is to be included in the scenario progression. The following example scenario progression gives you an overview of the possible combinations of scenario and shift, and how they are processed in the SAP system:

|Valid On|Scenario|Rule|Use Scenario|Use Shift|Processing|
|---|---|---|---|---|---|
|11/01/2000| |Shift1| |X|Shift 1 is applied on 11/01/2000 to the forward curve (forward FX curve) calculated from current market data.|
|11/01/2001|Scenario 1| |X| |Data from scenario 1 is applied|
|11/01/2002| |Shift 2| |X|Data from scenario 1 is copied to the date, and shift 2 is then applied to this data (no forward rates are calculated).|
|11/01/2003|Scenario 2|Shift 3|X|X|Shift 3 is applied to the data from scenario 2|
|11/01/2004|Scenario 3|Shift 4| | |Scenario 3 and shift 4 are ignored.|


- 10. Choose Save.


Result

You have processed a scenario progression.

###### Manage Market Data Sets

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Manage Market Data Sets | L5 | trm03 p.137 | loio `65c5ae71982e4c6eab03561a42b9886f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/65c5ae71982e4c6eab03561a42b9886f.html?locale=en-US)

The market data set is an entity refering to a set of different market data, each market data contributing to one data point for the linear regression.

Two market data set categories are available:

From Market Data Scenarios

The market data set refers to list of market data scenarios which can be individually defined and thus may contain any artificial market data constellation.

From Market Data Tables

The market data set refers to a list of historical market data selection dates.

**Prerequisite**

For market data sets based on scenarios, you define a number of market data scenarios. See also: Editing Scenarios. A single market data scenario contains self-contained market data, either artificial one or loaded from historical market data.

Use version dependency of the market data set to exchange assigned market data scenarios.

**Integration**

The system checks the following authorization objects when market data sets are created, changed, or deleted.

|Authorization object|Activities|Remarks|
|---|---|---|
|F_T_TRANSB Treasury: Transaction Authorization|TCD Transaction Code|When a transaction is chosen, the system checks whether the user is authorized to execute the function. The authorization object is used within nearly all transactions of SAP Treasury and Risk Management.|
|F_T_MDSET Market Data Sets|01 Create or Generate 02 Change 03 Display 06 Delete|This authorization objects controls the authorization to create, change, and delete market data sets in the Manage Market Data Sets app (app ID TAN_MDS). The Manage Market Data Sets app does not check authorization for the activity 03 Display.|


**Creating Market Data Sets of Category From Market Data Scenarios**

- 1. Enter an MDS ID and choose Create.

Choose the MDS category From Market Data Scenarios.

Specify the number of scenarios.

The number that you enter applies for all other versions of the market data set.

Alternatively, you can create an MDS using a reference to an existing MDS. In this way, all values of the referenced MDS are copied to the new MDS.

- 2. The system proposes the current date as the validity date. This date is used to automatically generate the first version of the new MDS.
- 3. In the detail screen, enter the names and scenarios for the current MDS and save your entries. By double-clicking a scenario name, you can call up the scenario details.


**Note:**

From the auditing point of view, this number must be 24, according to the settings for the effectiveness test method SLR Linear Regression.

**Creating Market Data Sets of Category From Market Data Tables**

- 1. Enter an MDS ID and choose Create.


Choose the MDS category From Market Data Tables.

Specify the number of scenarios.

The number that you enter applies for all other versions of the market data set.

Alternatively, you can create an MDS using a reference to an existing MDS. In this way, all values of the referenced MDS are copied to the new MDS.

- 2. The system proposes the current date as the Valid From date. This date is used to automatically generate the first version of the new MDS.
- 3. In the detail screen, enter the short name and the long name of the market data set.
- 4. On the Market Data Selection Dates tab you define a simple date determination rule to define a list of historical dates relatively to the evaluation date (designation date) used for market data selection:


Enter a Term and a Term Unit (Day, Week, Month).

Day

Term defines the number of the working days according to the factory calendar.

Week

One week corresponds to 7 calendar days. The setting Working Day Shift can be used to shift the resulting day to working day.

Month

Corresponds to one calendar month. Using the Month-End indicator the resulting day can be moved to the month end. Furthermore, the setting Working Day Shift can be used to shift the day to a working day.

Using the Determine Selection Dates button you can simulate the effect of the Date Determination Rule at runtime.

**Note:**

Evaluation Date: 16.04.2018

Total number of elements in the market data set: 10

**Examples**

|Example|Term|Term Unit|Calendar|Working Day Shift|Month-End|Dates|
|---|---|---|---|---|---|---|
|1|1|Day|-|-|-|15.04.2018 14.04.2018 13.04.2018 12.04.2018 11.04.2018 10.04.2018 09.04.2018 08.04.2018 07.04.2018 06.04.2018|
|2|1|Day|01|-|-|13.04.2018 12.04.2018 11.04.2018|


|Example|Term|Term Unit|Calendar|Working Day Shift|Month-End|Dates|
|---|---|---|---|---|---|---|
| | | | | | |10.04.2018 09.04.2018 06.04.2018 05.04.2018 04.04.2018 03.04.2018 29.03.2018|
|3|1|Week|-|-|-|09.04.2018 02.04.2018 26.03.2018 19.03.2018 12.03.2018 05.03.2018 26.02.2018 19.02.2018 12.02.2018 05.02.2018|
|4|1|Week|01|Previous Working Day|-|09.04.2018 29.03.2018 26.03.2018 19.03.2018 12.03.2018 05.03.2018 26.02.2018 19.02.2018 12.02.2018 05.02.2018|
|5|1|Month|-|-|X|31.03.2018 28.02.2018 31.01.2018 31.12.2017 30.11.2017 31.10.2017 30.09.2017|


| | | | | | | |
|---|---|---|---|---|---|---|
|Example|Term|Term Unit|Calendar|Working Day Shift|Month-End|Dates|
| | | | | | |31.08.2017 31.07.2017 30.06.2017|
|6|1|Month|01|Previous Working Day|X|29.03.2018 28.02.2018 31.01.2018 29.12.2017 30.11.2017 31.10.2017 29.09.2017 31.08.2017 31.07.2017 30.06.2017 |


8/27/26, 2:23 AM

**Creating a New Version**

- 1. In the detail screen, choose Create New Version (F5).
- 2. As the validity date, the system proposes the following day after the validity date of the last version. You can change this date if necessary.
- 3. Enter a short and long description for the new MDS version.
- 4. Make the required changes
- 5. Save your entries.

###### Market Data Shift

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Market Data Shift | L5 | trm03 p.141 | loio `7ab904536db4904ae10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7ab904536db4904ae10000000a441470.html?locale=en-US)

**Definition**

You use market data shifts (also known as external rules) to change current market prices as well as scenario market prices. For this, a market data shift can include risk factor shifts that are distinguished from one another within the system by a rule index.

A market data shift relates to one or more factors that affect the price. In this way, you can use market data shifts to make a fictitious change to values of the following factors:

Exchange rate

Yield curve

Securities index

Security price

Volatility

Basis spreads

Credit spreads

For each of these factors, you can define an absolute risk factor shift or a percentage-based risk factor shift.

**Use**

Market data shifts are used as characteristics in the NPV evaluation. They are used to represent in simple form the effects of price changes on the NPV. The NPV evaluation displays all fictitious NPVs for each risk factor shift as well as the current NPV. Further key figures can be calculated from the NPV evaluation.

Market data shifts are also used in ALM scenario processes.

###### Editing Market Data Shifts

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Market Data Shift > Editing Market Data Shifts | L6 | trm03 p.142 | loio `3c1d0f5374978320e10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c1d0f5374978320e10000000a423f68.html?locale=en-US)

**Use**

In this function, you can create, change, display, delete, and copy market data shifts.

**Procedure**

- 1. Choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Simulation Scenarios Market Data Shifts .

The system displays the initial screen Edit Market Data Shifts. From this selection screen, you can create, change, display, delete, and copy market data shifts.

- 2. To create a market data shift, enter a numerical value of up to ten digits to identify the market data shift and choose Create.

The Define Market Data Shifts screen appears.

- 3. For the market data shift, enter a short description in the Short Name field and a long description in the Long Name field.
- 4. If you want to define an additional authorization check for a market data shift, assign to that market data shift an authorization group.

You define authorization groups in Customizing under Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings Maintain Authorizations/Profiles/Users Maintain Authorization Groups .

- 5. On the relevant tab pages, enter the following data or constraints for the market data shift:

Note that shifting factors can also lead to invalid parameter values (such as negative time deposit rates). Therefore, always check that your shifts are plausible.

- 6. Choose Save.

###### Calculating Volatilities and Correlations

> **Path:** Treasury and Risk Management > Risk Management > Market Risk Analyzer > Asset/Liability Management > Calculating Volatilities and Correlations | L5 | trm03 p.142 | loio `4d7fc3d081ef0d6be10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4d7fc3d081ef0d6be10000000a42189e.html?locale=en-US)

Context

Using the statistics calculator, you can estimate volatilities and correlations for risk factor changes (absolute, relative, and logarithmic) on the basis of historical market data. In this process, the system calculates the standard deviation of the sample, and uses this as an estimate for the volatility. It uses empirical values for covariance as an estimate for the correlations.

The statistics calculator calculates only volatilities and correlations for the risk factors of the risk hierarchy specified. Permitted risk factors are: grid points on yield curves, currency translation rates, securities prices, index prices, and abstract risk factors. Volatilities and correlations for these risk factors are required for the variance/covariance approach, for example, and for Monte Carlo simulation. They can also be used for the price calculator.

In addition to the classic calculation of standard deviations and correlations, you can also apply exponential weighting (by using the decay factor in the underlying statistics type). The standard delivery also provides a user exit that you can use to implement an estimator (example module statistics calculator_userexit).

**Procedure**

- 1. Call the Statistics Calculator (transaction TVS1). The system displays the input screen for the calculation of volatilities and correlations.
- 2. If you have activated the static analysis structure or you use the static and the generated analysis structure, you can choose the mode for the report. You can choose between Free Parameter Definition and Market Risk Key Figure Set modes. If you choose the Market Risk Key Figure Set mode, you only enter the market risk key figure set and the evaluation date in the Evaluation Parameter area, as all other parameter are taken from the market risk key figure set. For more information, see also Manage Market Risk Key Figure Sets

- 3. Choose a risk hierarchy.
- 4. To restrict the calculation to a particular node of the risk hierarchy, choose a risk hierarchy node.
- 5. Choose a reference currency.
- 6. Choose a volatility type.
- 7. Choose a correlation type.
- 8. Choose a calendar, a start date, and a term. In this way, you clearly define the historical days for which the system reads the market data.
- 9. Enter the number of missing rates allowed. This enables you to control the behavior of the system when market data is missing.

If no data exists for historical days (trading was suspended or no data was imported by datafeed), the system uses a replacement strategy. The system accesses market data from further in the past. As this process distorts the statistical results, you can predefine the maximum number of such replacements in a historical time period by means of the error tolerance.

- 10. You can perform the following alternative calculations:


**Note:**

You only select a reference currency, if you have selected a risk hierarchy for which the exchange rate risk factor is not clearly identified by the a base currency and a target currency.

**Note:**

In Customizing, you assign a statistic type to the correlation type and the volatility type. This describes the statistical calculation type and defines the parameters of the underlying estimation function (extent of sample, for instance).

**Example:**

Let us assume that the start date is March 3, 2015 (Monday). Changes in the market price are determined for the past. If the term is one day, the first market price change is the change that occurred in the period from February 28 to March 3, 2015. The second price change is determined from February 27 to February 28, and so on.

Calculate volatilities only

Calculate correlations only

Calculate volatilities and correlations

Choose special volatilities and correlations

- 11. You can use the Test Run indicator to define whether the system saves the calculated data to the database.
- 12. Choose Execute.


**Results**

The system displays a list of the volatilities and correlations calculated (not adjusted or adjusted, as the case may be).

You can display a detailed log for the individual volatilities and correlations that you can draw from the market data used for the calculation.

For correlations, you can also use a correlation matrix.

An error log enables you to see which market data was missing.

If the run was not a test run, the system saves the values in the relevant database tables.

The volatilities are stored as annualized values. The system converts the term T (in days) that you enter when you call the statistics calculator into calendar days C, and rounds the values up to whole days:

[figure TRM03-F153 - The volatilities are stored as annualized values. The system converts the term T (in days) that you enter when you call the statistics calculator into calendar days C, and rounds the values up to whole days:]

