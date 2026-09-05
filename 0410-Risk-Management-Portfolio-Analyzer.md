# Risk Management > Portfolio Analyzer - SAP TRM Knowledge Base (branch split)

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

#### Portfolio Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer | L3 | trm03 p.225 | loio `48055e53ae50e047e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/48055e53ae50e047e10000000a441470.html?locale=en-US)

You use the component Portfolio Analyzer (FIN-FSCM-TRM-PA) to calculate and monitor the rates of return (yields) on your financial assets.

**Use**

The Portfolio Analyzer allows you to measure the profits from investments from different perspectives and using different methods. The calculations are based on the structure of your portfolio in the portfolio hierarchy. You use characteristics to define the tree-like structure. For example, you can choose the sector, country/region, trader, department, or product type to define the hierarchy. In this way, you can organize your portfolio flexibly in different aggregation levels and calculate rate of return key figures

for each of these levels. With the reporting functions, you can display results for each node that you have defined in the portfolio hierarchy. You can drilldown to the data stored at the single transaction level.

To analyze data from different perspectives, such as from the view of the internal controller, dealer, or marketing employee, you can define multiple portfolio hierarchies for a portfolio and use them in your analyses. The Portfolio Analyzer creates versions of the portfolio hierarchy and of the calculations of rates of return and benchmarks. This enables you to look at the figures on which past calculations were based at any time, and reproduce and historize the results.

Methods for Calculating the Rate of Return

For the calculation of rate of return, the Portfolio Analyzer offers methods for calculating time-weighted rate of return (TWRR) and money-weighted rate of return (MWRR). In addition to the exact methods, the Portfolio Analyzer also offers the approximation methods Dietz and modified Dietz for the calculation of TWRR. In addition to rate-of-return key figures, you can also define benchmark rates of return and compare them against the rates of return of your portfolios.

Benchmarking

You can manage benchmarks and compare them with the calculated rates of return for any part of your portfolio. You can also import risk key figures and book values into the Portfolio Analyzer and use the formula editor to link them to new key figures. This enables you to display the active return and excess fair value in the reporting for the Portfolio Analyzer.

This enables you in particular to use the Portfolio Analyzer to channel your investment strategy. In reporting, any deviations in the planned revenue and risk estimates can be detected early on, and forecasts can be made about how the portfolio will develop. You can use these analyses to work out proposals for optimizing your investment strategy and for concluding new transactions.

**Integration**

The Portfolio Analyzer is part of SAP Treasury and Risk Management (FIN-FSCM-TRM).

You can calculate the rate of return for the following transactions:

All positions in the Transaction Manager (FIN-FSCM-TRM-TM)

Loans in SAP Loans Management (FS-CML)

##### Transactions in Portfolio Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Transactions in Portfolio Analyzer | L4 | trm03 p.226 | loio `d112da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d112da531198434de10000000a174cb4.html?locale=en-US)

Portfolio Analyzer contains the following transactions:

|Function|Transaction Code|
|---|---|
|Edit Characteristic Values|JBRCV|
|Transport Characteristic Values|JBRCT|
|Edit Characteristic Hierarchy|JBWH|
|Translate Characteristic Hierarchy|JBHTL|
|Create Portfolio Hierarchy|AFWPH|
|Display Portfolio Hierarchy|JBRK|
|Delete/Deactivate Portfolio Hierarchy|JBR4E|


|Function|Transaction Code|
|---|---|
|Generate Portfolio Hierarchy|JBRW|
|Update Portfolio Hierarchy|JBRP0|
|Define Filter|AFWFL|
|Edit Key Figures and Evaluation Procedures|AFWKF_PA|
|Monitor: Key Figures and Evaluation Procedures|AFWKF_MD|
|Determination of Single Records|PAEP1|
|Determination of Single Records: Monitoring|AFWO1|
|Determination of Final Results|PAEP2|
|Determination of Final Results: Monitoring|AFWO2|
|Delete single records that have not been archived|PASRPDEL|
|Analyzer Information System|AIS_STDREP|
|Single Value Analysis: Profit and Loss|AISPL|
|Edit Master Data for Benchmarks|AFWBM|
|Assign Benchmarks to Nodes in the Portfolio Hierarchy|AFWBMPH|
|Calculate Benchmark Key Figures|PAEPBM|
|Calculation of Benchmark Key Figures: Overview|AFWOBM|
|Define Initial Layout|S_KFM_86000129|
|Define Formulas for the Analyzer Information System|AIS_FORMULA_DEF|

##### Calculation of Rates of Return

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Calculation of Rates of Return | L4 | trm03 p.227 | loio `1f11da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1f11da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to calculate the rates of return for the nodes of a portfolio hierarchy.

**Prerequisites**

In Customizing for Financial Supply Chain Management under Treasury and Risk Management Portfolio Analyzer Results Database Edit Key Figures and Valuation Procedures , you have entered the following settings:

You have defined key figures for the calculation of rates of return, and assigned each of them the required yield method.

The system calculates the rate of return in the evaluation currency. You can use the following key figure categories:

PAYLDCC (Key figure category for rates of return with a fixed evaluation period)

You define the yield period in the Interval for Periods field. SAP supplies valuation periods for days, months, quarters, and years. You can define additional evaluation periods in Customizing for Portfolio Analyzer under Results Database Define Yield Ranges .

PAYLDSNCCC (Key figure category for period-to-date yields)

By setting the Yield Period Start indicator, you define whether the system is to start calculating the yield one year, half a year, one quarter, or one month before the key date.

You have defined a single records procedure and a final results procedure.

You have assigned the key figures for the rate of return (yield calculation to the single records procedure and final results procedure.

You have assigned at least one portfolio hierarchy to final results procedure 2 (FRP2). You have to do this so that the system can calculate the rate-of-return key figures for each portfolio hierarchy node.

For more information, see Use of the Results Database in Portfolio Analyzer.

**Features**

The system contains the following rate of return methods:

Time-weighted rate of return (TWRR)

The time-weighted rate of return describes the returns that result simply from the actions of the portfolio manager. The rate of return is calculated net of the effect of the deposits into or withdrawals from the portfolio made by customers, which are factors that cannot be influenced by the portfolio manager.

The system first breaks down the analysis period into subperiods so that exogenous cash flows fall only at the end of the subperiods, and not within them. The first subperiod ends with the first exogenous cash flow; each subsequent exogenous cash flow defines a new subperiod. The last subperiod ends at the end of the analysis period.

Return R for subperiod i is defined as follows:

i

[figure TRM03-F298 - Return R for subperiod i is defined as follows:]

where MVE is the market value of the portfolio at the end of subperiod i, which is calculated as the total of the NPV PAPOSCC of the portfolio on the end date of subperiod i and the flows CF on the end date of subperiod i. MVB is the market value of the portfolio at the start of subperiod i, which is the NPV PAPOSCC of the portfolio on the previous day. The time-weighted rate of return R for the whole analysis period is calculated as follows:

I i i i

i-1 TWRR

[figure TRM03-F299 - Money-weighted rate of return (MWRR)]

Money-weighted rate of return (MWRR)

Exogenous incoming and outgoing flows of cash are not removed before the money-weighted rate of return is calculated. It is defined as rate of return R , which is used to calculate the interest rate of the portfolio, including all incoming and outgoing cash flows. The system first calculates the annualized money-weighted rate of return:

MWRR

[figure TRM03-F300 - Exogenous incoming and outgoing flows of cash are not removed before the money-weighted rate of return is calculated. It is defined as rate of return R , which is used to calculate the interest rate of the portfolio, including all incoming and outgoing cash flows. The system first calculates the annualized money-weighted rate of return:]

where MVB is the market value of the portfolio at the start of the period, and MVE is the market value of the portfolio at the end of the period; T is the length of the period in days, and CF incoming and outgoing cash flows; d specifies on which day, calculated from the start of the period, cash flow CF flows. The system then calculates the weighted rate of return for the analysis period:

I I i

[figure TRM03-F301 - where MVB is the market value of the portfolio at the start of the period, and MVE is the market value of the portfolio at the end of the period; T is the length of the period in days, and CF incoming and outgoing cash flows; d specifies on which day, calculated from the start of the period, cash flow CF flows. The system then calculates the weighted rate of return for the analysis period:]

Whereas the time-weighted rate of return can be understood as the rate of return obtained by the portfolio manager, the money-weighted rate of return is the rate of return achieved by the owner of the portfolio.

Modified Dietz Method

The modified Dietz method is an approximation method for calculating the time-weighted rate of return; it is used to calculate the internal interest rate earned from the portfolio. The analysis period is divided into time periods i. A linear interest calculation method is used within these time periods. rate of return of a subperiod is defined as the quotient of the net growth of the subperiod and the average capital invested in the period. Incoming and outgoing cash flows are timeweighted in a linear way, and used to calculate the average capital that is invested:

[figure TRM03-F302 - where MVB is the market value of the portfolio at the start of subperiod i and MVE is the market value at the end of subperiod i; T is the length of subperiod i in days and CF the incoming and outgoing cash flows in subperiod i; d specifies on which day, calculated from the start of subperiod i, cash flow CF flows.]

where MVB is the market value of the portfolio at the start of subperiod i and MVE is the market value at the end of subperiod i; T is the length of subperiod i in days and CF the incoming and outgoing cash flows in subperiod i; d specifies on which day, calculated from the start of subperiod i, cash flow CF flows.

i i I i,j i,j i,j

Rate of return R is calculated in the modified Dietz method as follows:

MDI

[figure TRM03-F303 - The subperiods are not longer than one month.]

The subperiods are not longer than one month.

Dietz Method

In the Dietz method, the rate of return is not calculated for each flow of capital. The system divides the analysis period into equal subperiods. A constant rate of return is assumed for these subperiods. It is also assumed that all flows of capital take place in the middle of the subperiods. Unlike in the modified Dietz method, the flows are not weighted by the length of time over which they have an effect.

**Activities**

To calculate rates of return, on the SAP Easy Access screen, choose Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Determine Single Records , and then Determine Final Results.

The system calculates the results as follows:

- 1. It calculates single records. It calculates only the additive key figures of the categories PAPOS and PAFLW.
- 2. It applies Final Results Procedure 1 (FRP1).

this process, it aggregates the additive key figures and converts the single records into the evaluation currency (key figure categories PAPOSC and PAFLWCC).

- 3. The system applies Final Results Procedure 2 (FRP2) in order to calculate non-additive key figures (key figure categories PAYLDCC and PAYLDSNCCC).


**Note:**

Subdivision of the final results procedure into two steps is necessary to be able to execute an attribution analysis later.

To display the results of the calculation of rates of return SAP Easy Access screen, choose Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Information System Analyzer Information System .

##### Benchmarking

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Benchmarking | L4 | trm03 p.230 | loio `ba13da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ba13da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Benchmarks are used to analyze how the value of financial assets develops. Benchmarks are based on market data, or are constructed so that they give the most useful information possible about the portfolio in question.

In Portfolio Analyzer, you can define your own benchmarks, and display them in the nodes in the portfolio hierarchy. Benchmarks are analyzed in the framework of the Results Database (RDB). This enables you to compare yields in the Analyzer Information System (AIS). You can define benchmarks by referencing them to market data, such as a security or a reference interest rate. You can also define composite benchmarks, which contain multiple benchmarks, each of which has a weighting that you can define. This enables you to define benchmarks so that they reflect your portfolio as closely as possible, and can hence be used for the purposes of comparison.

The system does not use the evaluation procedures already contained in the RDB in order to calculate benchmark values. Instead, it uses a separate benchmark run, which you start independently of the evaluations in the Results Database. In a separate step, you must also assign your benchmarks to the relevant portfolio hierarchy nodes.

**Procedure**

Define the master data for the benchmarks.

In the Customizing for Financial Supply Chain Management, choose Treasury and Risk Management Portfolio Analyzer Benchmarks Edit Master Data for Benchmarks . For more information, see Editing of Master Data for Benchmarks.

Assign the benchmarks to the nodes of your portfolio hierarchy

In the Customizing for Financial Supply Chain Management, choose Treasury and Risk Management Portfolio Analyzer

Benchmarks Assign Benchmarks to Nodes in the Portfolio Hierarchy . For more information, see Assignment of Benchmarks to Portfolio Hierarchy Nodes.

Define benchmark key figures.

In the Customizing for Financial Supply Chain Management, choose Treasury and Risk Management Portfolio Analyzer Results Database Monitor: Key Figures and Evaluation Procedures .

Note the following:

You do not assign evaluation procedures to benchmark key figures, as the system calculates benchmark key figures in a separate job.

The system stores the market data for benchmarks in the following position key figures:

PAPOS (position in position currency)

PAPOSCC (position in evaluation currency)

The system calculates the benchmark rates of return in the followings key figures:

PAYLDCC (rate of return on investment from evaluation currency)

PAYLDSNCCC (rate of return from start of period to date from the evaluation currency)

You link the benchmark master data to the benchmark key figures when you start the benchmark run. For more information, see Calculation of Benchmark Key Figures in the Benchmark Run.

Define an initial layout for the Analyzer Information System (AIS).

In Customizing, choose Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Results Database Define Initial Layout , and assign your benchmark key figures to the portfolio hierarchy area.

If required, define formula-based key figures.

In the Customizing for Financial Supply Chain Management, choose Treasury and Risk Management Portfolio Analyzer Results Database Define Formulas for Analyzer Information System . For more information, see Formula Editor.


Note that you have to create formulas for each assignment variant you created for benchmark key figures. Therefore, in the formula editor the system displays the key figures for all assignment variants.

**Result**

You have defined the properties of the benchmarks, assigned them to the portfolio hierarchy, defined the benchmark key figures that the system is to calculate, and set up the layout for the display of results.

You can now start a benchmark run and display the results in the Analyzer Information System (AIS). In the selection screen in the Analyzer Information System, specify the assignment variant you require. In reporting, the system displays the names of the master data of the assignment variant selected, and the key figures, as per the definition of the layout.

See also:

Calculation of Benchmark Key Figures in the Benchmark Run

Analyzer Information System

###### Editing of Master Data for Benchmarks

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Benchmarking > Editing of Master Data for Benchmarks | L5 | trm03 p.231 | loio `cb13da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cb13da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to create, display, and change benchmarks.

**Integration**

Once you have created the master data for benchmarks, you need to do the following before you can use benchmarks in Portfolio Analyzer:

Assign benchmarks to the portfolio hierarchy.

Create benchmark key figures in the framework of the Results Database.

Start a benchmark run. This links the benchmark master data you created with the benchmark key figures, and calculates the benchmark values.

For more information, see Benchmarking.

**Features**

The system contains the following benchmark categories:

Basic benchmark

Basic benchmarks are benchmarks that have a direct reference to market data. These include benchmarks for indexes and exchange rates. The system also contains the following benchmark categories:

Fixed interest rate, which you can use to store an interest rate

Variable interest rate, which you can use to store a variable interest rate

Reference portfolio, which you can use to benchmark against the portfolio yield of some reference portfolio

Composite benchmark

You use composite benchmarks to combine the benchmarks you defined. You specify the weighting of each sub-benchmark in the composite benchmark. The total weights of all sub-benchmarks must be 100%.

You can use the Readjustment field in the composite benchmark to define how often the system resets the weighting to the original values. You need to enter this information, as the weighting of the sub-benchmarks in the composite benchmark can change, depending on how the values of the sub-benchmarks change over time.


If you need time periods for the readjustment other than the periods day, month, quarter, and year that are predefined in the system, then you can create them in the Customizing for Financial Supply Chain Management under Treasury and Risk Management Portfolio Analyzer Results Database Define Yield Ranges .

You assign a currency to each benchmark. You can also store other information in the benchmark, such as the authorization group, and you can enter comments to document any changes you make to the benchmarks.

Versioning

The system creates versions of benchmarks by means of the validity date. This enables you to create multiple versions of benchmarks, and each version can have different master data. The versions of a benchmark apply from the validity date specified through to the validity date of the next version. You can create versions for dates that are in the past.

When the system calculates the values of the benchmark, it uses the version of the benchmark master data that is valid on the evaluation date.

The benchmark category is defined when the first version of the benchmark is created. It cannot be changed. You can change other properties of the benchmark only if no key figures have been calculated for the benchmark. Note that if you change the currency of a benchmark, all the older versions of the benchmark are then assigned the new currency. It is not possible to create versions that have different currencies.


For more information about versioning, see the field help for the Valid From field in the selection screen of the transaction for editing the master data of benchmarks.

**Activities**

In Customizing, choose Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Benchmarks Edit Master Data for Benchmarks , and enter a name and validity date for the benchmark.

Interaction in the Selection Screen

|Action|Function|
|---|---|
| Create|If the system does not contain a benchmark that has the name you entered, the system creates a new benchmark that has this name. If the system already contains a benchmark with this name, it creates a new version for the date specified.|
| Change|You can change the properties of the benchmark to those that are valid on the date you specify.|
| Display|You can display the properties of the benchmark that are valid on the date you specify. If you do not enter a date, the system displays the version that is valid on today's date. The input help for the date field contains the dates of all the versions that exist for the benchmark.|
| Copy|For the date specified, the system creates a new benchmark that has the same properties as the benchmark specified.|
| Delete|The system deletes the version of the benchmark that is valid on the date specified.|
| Display History|The system displays all the changes made to the benchmark specified.|
| Higher-Level Benchmark|The system displays all the composite benchmarks that contains the benchmark you specified.|
| Benchmark Delete Benchmark|The system deletes all the version of the benchmark specified.|
| Goto Maintain Portfolio Hierarchy Assignment|The system branches to the transaction in which you can assign the specified benchmark to a portfolio hierarchy node (see also Assignment of Benchmarks to Portfolio Hierarchy Nodes). |
| Benchmark Analysis Data|The system displays all the key figure calculations for the benchmark specified. The benchmark key figures and the evaluations periods are displayed. You can use this function to check whether there are any gaps in the calculation of key figures. If you want to change the benchmarks, you can check which key figures you need to delete before you change the benchmarks.|


|Action|Function|
|---|---|
| Check Benchmark|The system checks whether the definition of the benchmark is complete and consistent.|
| Assignment of Analysis Characteristic|The system displays the analysis characteristics that are available. You can enter values for analysis characteristics. This enables the system to link the values calculated for the benchmarks to the|


|Action|Function|
|---|---|
| |analysis characteristics.|



You can display and change the master data for benchmarks from within the area menu. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Master Data

Benchmark Edit Master Data for Benchmarks .

###### Assignment of Benchmarks to Portfolio Hierarchy Nodes

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Benchmarking > Assignment of Benchmarks to Portfolio Hierarchy Nodes | L5 | trm03 p.234 | loio `c513da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c513da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to assign benchmarks to the nodes of your portfolio hierarchy. The system displays benchmarks in the Analyzer Information System only if you have assigned the benchmarks to portfolio hierarchy nodes.

You assign benchmarks to the portfolio hierarchy by using assignment variants. You use assignment variants when you start the benchmark run in order to control how the system calculates key figure values. When you call the Analyzer Information System, you define which assignment variants the system is to display.


For more information, see Benchmarking.

**Prerequisites**

You have defined benchmarks in the Customizing for Financial Supply Chain Management under Treasury and Risk Management Portfolio Analyzer Benchmarks Edit Master Data for Benchmarks .

**Features**

You can create up to five assignment variants for each portfolio hierarchy. However, normally you need just one or two assignment variants per portfolio hierarchy.

You can define whether a benchmark is assigned just to the selected node of the portfolio hierarchy, or whether this assignment applies to the lower-level nodes as well.

The system creates versions of assignment variants by means of the validity date. The versions of an assignment variant apply from the validity date specified through to the validity date of the next version. When the system calculates the values of the benchmark, it uses the version of the assignment variant that is valid on the evaluation date.


For more information about versioning, see the field help for the Valid From field in the selection screen of the transaction for assigning benchmarks to the portfolio hierarchy.

**Activities**

In the Customizing for Financial Supply Chain Management, choose Portfolio Analyzer Benchmarks Assign Benchmarks to Nodes in the Portfolio Hierarchy .

The system displays a selection screen. You have the following options:

Interaction in the Selection Screen

|Action|Function|
|---|---|
| Create|If there is no assignment variant that has the name you entered, the system creates a new assignment variant that has this name. If the system already contains an assignment variant with this name, it creates a new version for the date specified.|
| Change|You can change the assignment variant that is valid on the date specified.|
| Display|You can display the assignment variant that is valid on the date specified.|
| Copy|For the date specified, the system creates a new assignment variant that has the same properties as the assignment variant specified.|
| Delete|The system deletes the version of the assignment variant that is valid on the date specified.|
| Display History|The system displays all the changes made to the assignment variant specified.|
| Assignment Variant Delete Variant|The system deletes all the version of the assignment variant specified.|
| Goto Master Data for Benchmark|The system branches to the transaction for editing the master data of benchmarks. |


|Action|Function|
|---|---|
| Benchmark|The system displays the master data of the benchmark selected.|
| PH Assignment|The system assigns the selected benchmark to the portfolio hierarchy node that is selected in the right-hand area of the screen.|
| Delete Assignment|The system removes the benchmark that was assigned to the portfolio hierarchy node selected.|


**Example**

Create an assignment variant as follows:

Choose a view and a portfolio hierarchy node, and enter a name and validity date for the assignment variant. Choose Create.

The system displays the tab page Assign Benchmark to PH Nodes. The left-hand part of the screen contains the benchmarks you defined. The right-hand part of the screen contains the portfolio hierarchy.

In the right-hand part of the screen, open the portfolio hierarchy down to the node to which you want to assign a benchmark.

Using drag and drop, assign the benchmark to the portfolio hierarchy node.

Choose the General Properties/Comments tab page.

The system displays the attributes of the assignment variant. The upper part of the screen contains the attributes that are valid for all versions of the assignment variant. The lower part of the screen contains the attributes that are valid only for the current version of the assignment variant.

Using the Type of PH Assignment indicator, define whether the assignment of the benchmark applies just for one portfolio hierarchy node, or for all the lower-level nodes as well if they have not been assigned any other benchmarks.

By setting this indicator, you define that the benchmarks are displayed on entire branches of the portfolio hierarchy.

Choose with the quick info Save.



You can display and change the assignment variants from within the area menu. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Master Data

Benchmark Assign Benchmarks to Nodes in the Portfolio Hierarchy .

###### Calculation of Benchmark Key Figures in the Benchmark Run

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Benchmarking > Calculation of Benchmark Key Figures in the Benchmark Run | L5 | trm03 p.236 | loio `2411da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2411da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to start benchmark runs. In these runs, the system calculates the values of the benchmarks you defined, and saves the results in the relevant benchmark key figures in the Results Database (RDB).

Once the benchmark runs have finished, you can display the results in the Analyzer Information System (AIS).

**Integration**

Although the system uses the framework of the RDB to save and display benchmarks, you have to start the benchmark runs without using the evaluation procedures of the RDB.

The system does not link the benchmark master data you created with the relevant benchmark key figures until the benchmark run is started.

**Prerequisites**

You have defined at least one benchmark in Customizing for Financial Supply Chain Management under Treasury and Risk Management Portfolio Analyzer Benchmarks Edit Master Data for Benchmarks .

You have created at least one assignment variant in Customizing for Financial Supply Chain Management under Portfolio Analyzer Benchmarks Assign Benchmarks to Nodes in the Portfolio Hierarchy .

You have created the key figures that you want to use for benchmarking. You create these in Customizing for Financial Supply Chain Management under Portfolio Analyzer Results Database Edit Key Figures and Evaluation Procedures

. For more information, see Benchmarking.


**Features**

You can start benchmark runs in the following modes:

Basic Run

You use the following selection parameters to define the scope of the benchmark run: Portfolio hierarchy, assignment variant, benchmark, benchmark key figure, and evaluation period. You can enter multiple benchmarks and benchmark key figures. The system calculates key figure values for each combination of benchmark and benchmark key figure you entered.

Deletion Run

You use the deletion run to delete benchmark values that have already been calculated. The system also deletes all composite benchmarks that contain the benchmarks that are to be deleted. You start a deletion run if you want to change the master data of benchmarks, for example, for which the system has already calculated and saved key figure values. In this case, before you change the master data of the benchmarks you must delete the key figure values that were saved.

You can start the basic run and the deletion run as test runs to check which data is selected, and which benchmark values are calculated without this data being saved in the RDB.

Saving Worklists

In the basic run and the deletion run, you can save the selection criteria you used for the benchmarks as worklists. You can then use these worklists for a new basic run. The system does the following:

In the basic run, the system saves the selection criteria of all key figure calculations that were terminated.

In the deletion run, it saves the selection criteria of the run. The worklist contains the selection criteria for all the benchmarks that you specified for deletion. It also contains the selection criteria of the higher-level benchmarks, since the system also deletes the key figure values of these composite benchmarks in the deletion run.

You should use the Save as Worklist for deletion runs that you start when you want to change the master data of a benchmark yet the RDB already contains key figure values for the version of the benchmark in question. Proceed as follows:

- 1. Choose the Save As Worklist and start the run.

The system deletes the relevant key figure values.

- 2. Change the master data or market data of the benchmark as required.
- 3. Start the basic run using the worklist that the system created during the deletion run. You can find the name of the worklist by looking in the log of the deletion run.


The system reproduces all the key figure values that were deleted.

**Activities**

In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Results Database Calculation of Benchmark Key Figures .

A selection screen appears.

Enter the run parameters you require and choose with the quick info Execute.


The system starts the benchmark run.

**Note:**

To display benchmark runs that already exist, in the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Results Database Overview of the Calculation of Benchmark Key Figures .

##### Determination of Risk-Adjusted Measures

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Determination of Risk-Adjusted Measures | L4 | trm03 p.238 | loio `4e532b1ba32c4f49e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e532b1ba32c4f49e10000000a42189e.html?locale=en-US)

**Use**

In this function, you can use key figures as the basis for risk measurement to gain a better/deeper understanding of the quality of return. Depending on the risk measure key figure that you select, the system determines the intermediate results that have been automatically calculated and saved. The description for the intermediate results of these key figures is set as a combination of the description of the key figure and the related/corresponding intermediate result.

**Prerequisites**

- 1. Calculation of "risk-adjusted measure" ratio key figures requires a portfolio yield key figure and a benchmark yield key figure (the only exception is Jensen's alpha key figure, which requires a risk-free yield key figure in addition to the portfolio and benchmark yield key figures). As the first step:

You have defined and evaluated, a portfolio yield key figure for the required dates. For detailed information about the procedure, see Calculation of Rates of Return.

You have defined and evaluated, a benchmark yield key figure for the required dates. For detailed information about the procedure, see Calculation of Benchmark Key Figures in the Benchmark Run.

For a risk-free yield, you can use the same benchmark yield key figure or you can define and evaluate a different benchmark yield key figure.

- 2. You have defined the risk-adjusted measure key-figure that you want to evaluate. To do this, go to SAP IMG and choose Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Results Database Edit Key Figures and Evaluation Procedures .
- 3. You have assigned the previously evaluated portfolio and benchmark yield key figures to the risk-adjusted measure key figure.
- 4. You have associated the appropriate assignment variant to the benchmark yield key figures. The assignment variant needs to be the one for which you have run the evaluation of benchmark yield key-figure.


**Features**

To gain a better understanding of the quality of the yields, you can use the following key figures:

[figure TRM03-F337]

[figure TRM03-F338]

[figure TRM03-F339]

[figure TRM03-F340]

[figure TRM03-F341]

**Activities**

- 1. In SAP Menu, go to Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Results Database Calculate Benchmark Ratio Key Figures . Here the system displays a selection screen.
- 2. Select the risk-adjusted measure key figures you want to evaluate, along with a proper evaluation period.
- 3. Once the results are calculated, they can be displayed in the Analyzer Information System (AIS). In the selection screen of AIS, you can enter the key dates and the initial layout, which decides what key figures will be displayed in the reporting.
- 4. To define an initial layout, go to SAP Menu Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Analyzer Information System Define Initial Layout (AIS_LAY_DEF).
- 5. To run the Analyzer Information System reporting, go to SAP Menu Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Information System Analyzer Information System (AIS_STDREP)

##### Using Book Values

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Using Book Values | L4 | trm03 p.243 | loio `497eee4fe13af740e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/497eee4fe13af740e10000000a44538d.html?locale=en-US)

**Use**

In the Analyzer Information System (AIS), the system usually displays only the key figures calculated in the Market Risk Analysis or the Portfolio Analyzer and that were saved in the Results Database. In addition to these risk key figures, the AIS allows you to

display book values from operational components. This enables you to compare risk key figures with the book values used in external reporting.

Other central key figures, such as excess fair value, combine book values and key figures from Risk Management. You can use the formula editor to link book values and risk key figures to formula-based key figures, so that this data can be displayed in the AIS.

To transfer book values and save them in the Results Database, SAP provides function modules that you can include in Customizing for the price calculator. You can transfer book values from the following components:

Transaction Manager in SAP Treasury and Risk Management (TRM-TM)

SAP Loans Management (FS-CML)

**Prerequisites**

The book values that you want to transfer have to be key-date book values.

You have created an RFC connection for the transfer of the book values. In the SAP Easy Access screen, choose Tools Administration Administration Network RFC Destinations .

**Procedure**

To transfer book values to the Results Database, you need to perform the following steps:

1. Define the function modules for transferring the book values.

For each book value, you need a separate implementation of the RFC interface of the price calculator. This function module, which you make known to the price calculator in Customizing for the evaluation type, reads the relevant key figures from the operational systems and saves them in the Results Database.

In function group RMXX, SAP delivers the following function modules as examples:

RFCT2_BOOKVALUE_PC (transfer of book values from TRM, in position currency)

RFCT2_BOOKVALUE_PC (transfer of book values from TRM, in local currency)

By way of example, these function modules take the book values of contracts and securities positions from valuation area

- 001. You can copy the function modules to the customer namespace and then change them to meet your requirements.
- 2. Define an evaluation type.

Define an evaluation type in Customizing for Financial Supply Chain Management under Treasury and Risk Management Basic Analyzer Settings Valuation Define and Set Up Evaluation Types and proceed as follows:

- a. Go to the External Function Control tab page.
- b. Set the External Valuation indicator.
- c. In the External Valuation area, enter the target system in the RFC Destination field. In the RFC Function Name field, enter the name of the function module that you want to use to transfer book values.


- 3. Define key figures and evaluation procedures.


**Note:**

To create function modules, go to the SAP Easy Access screen and choose Tools ABAP Workbench Overview

Object Navigator . For more information about adapting the function modules that are predefined in the system, see the coding of the function modules mentioned above.

In the Customizing for Financial Supply Chain Management under Treasury and Risk Management Portfolio Analyzer Results Database Edit Key Figures and Evaluation Procedures , create a key figure category for each book value that


you want to transfer.

Define a separate key figure for each book value that you want to transfer.

Choose a suitable key figure category in each case.

The system does not contain separate key figure categories for transferring book values. We recommend that you use the following key figure categories from the Portfolio Analyzer:

PAPOS (position in position currency)

PAPOSCC (position in evaluation currency)

By using these key figure categories, you ensure that the system translates values into the evaluation currency correctly and that it displays these values correctly.

When you define the key figure, enter the evaluation type that you defined earlier.

- 4. Define the initial layout that contains the required key figures

Create an initial layout either in Customizing for Financial Supply Chain Managementunder Treasury and Risk Management Market Risk Analyzer or Portfolio Analyzer Results Database Define Initial Layout .

Assign the key figures that you have defined previously to one of the following areas:

Portfolio Hierarchy

Single Records

Position Trend

- 5. Define formula-based key figures (if required).

You use the Formula Editor to do this.

- 6. Save the book values in the Results Database (RDB).


On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Determine Single Records .

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Determine Final Results .

**Result**

You have transferred the required book values to the SAP system and stored them in the Results Database (RDB). You can now display the book values and the formula-based key figures derived from them in the Analyzer Information System.

Note the following constraints:

The system does not automatically update the book values that you have transferred. If the book values that are stored in the operational systems change, you have to transfer these values again for the dates required and store them in the Results Database (RDB).

Note that you can use the SAP Query function to transfer key figures from Market Risk Analysis and Portfolio Analyzer to Treasury and Risk Management (TRM). For this reason, the book values that you transfer to the Results Database can in some cases also be risk key figures.

**More Information**

Transaction Codes for the Transfer of Book Values

###### Transaction Codes for the Transfer of Book Values

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Using Book Values > Transaction Codes for the Transfer of Book Values | L5 | trm03 p.246 | loio `7911da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7911da531198434de10000000a174cb4.html?locale=en-US)

The following table contains the transaction codes that you use when you transfer book values:

|Short Description|Transaction Code|
|---|---|
|Define the RFC connection|SM59|
|Define function modules for reading book values|SE80 Templates: RFCT2_BOOKVALUE_PC and RFCT2_BOOKVALUE_LC|
|Define evaluation types|JBREVAL|
|Define key figures and evaluation procedures|AFWKF_PA|
|Define the initial layout|AIS_LAY_DEF|
|Formula editor for formula-based key figures|AIS_FORMULA_DEF|
|Determine single records|PAEP1|
|Determine final results|PAEP2|
|Reporting for key figures|AIS_STDREP|


See also:

Using Book Values

##### Use of the Results Database in Portfolio Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Use of the Results Database in Portfolio Analyzer | L4 | trm03 p.246 | loio `5f11da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5f11da531198434de10000000a174cb4.html?locale=en-US)

**Basis**

Portfolio Analyzer saves the results of all evaluations in the Results Database (RDB); it does not contain any online runs.

Unlike Market Risk Analysis, which also uses the Results Database, the final results procedure is a two-step method in Portfolio Analyzer.The final results are calculated as follows:

Single record procedure

The positions and flows are transferred to the Results Database.

- Final results procedure 1

Values are translated into the evaluation currency.

- Final results procedure 2


Rate-of-return (yield) key figures are calculated.

**Key Figure Types**

Portfolio Analyzer calculates all key figures based on the key figure categories, which are predefined in the system. You assign each key figure to an evaluation procedure. You can assign more than one key figure to each evaluation procedure, but each key figure can be assigned once only. When you define key figures, you can access key figure categories for positions (PAPOS and PAPOSCC), flows (PAFLW and PAFLWCC), and rates of return (PAYLDCC and PAYLDSNCCC). The following table shows which key figure categories you can use in which evaluation procedures:

|Evaluation Procedure|Key Figure Types|Reason for Creating Multiple Evaluation Procedures|
|---|---|---|
|Single record procedure|PAPOS (position in position currency) PAFLOW (flow in transaction currency )| |
|Final results procedure 1|PAPOSCC (position in evaluation currency) PAFLWCC (flow in evaluation currency )|Key figures that have the same basic key figure but different evaluation currencies|
|Final results procedure 2|PAYLDCC (rates of return with fixed yield periods from the evaluation currency) PAYLDSNCCC (rate of return from start of period to date from the evaluation currency )|Key figures that have the same basic key figures but rate-of-return methods or different rate-of-return periods|


In Customizing for Financial Supply Chain Management choose Treasury and Risk Management Portfolio Analyzer Results Database Edit Key Figures and Evaluation Procedures . In this IMG activity, you can create key figures by choosing a key figure category and entering the attributes of the key figure. You can also use existing key figures as the basis for defining new key figures. You do this by specifying a basic key figure when you define the new key figure. The system then copies the values of the basic key figure and adds them to the new key figure.

**Note:**

If you use basic key figures to define new key figures, the results of single records methods that have already been calculated are retained. You then only need to define the new final results procedure you require.

**Single Record Procedure (SRP)**

In the single record procedure, the system takes the position values stored in Treasury and Risk Management and loads them into the Results Database. The step takes a long time, as the system has to calculate the NPVs of all items in the positions. You must assign two key figures to the single records procedure: one for the position (key figure category PAPOS) and one for the flows (key figure category PAFLW).

**Note:**

To delete singe records, on the SAP Easy Access screen choose Accounting Financial Supply Chain Management Treasury and Risk Management Portfolio Analyzer Tools Results Database Delete Non-Archived Single Records .

You should use this transaction in your test system only. In your productive system, you should delete single records. On the SAP Easy Access screen choose Accounting Financial Supply Chain Management Treasury and Risk Management

Portfolio Analyzer Tools Results Database Determine Single Records .

**Note:**

To run the single records procedure as a parallel job, on the SAP Easy Access screen choose Treasury and Risk Management Portfolio Analyzer Tools Parallel Processing.


**Final Results Procedure 1 (FRP 1)**

- In final results procedure 1, the system translates the position values and flows calculated in the single records procedure into the evaluation currency. For each evaluation currency, you assign two key figures to the final results procedure: one category PAPOSCC key figure and one PAFLWCC key figure.

Final Results Procedure 2 (FRP 2)

- In final results procedure 2, the system calculates the non-additive key figures. In Portfolio Analyzer, these are rate-of-return (yield) key figures. You can assign only the key figures of the key figure category that has the prefix PAYLD* to final results procedure 2.Furthermore, you must assign a portfolio hierarchy to final results procedure 2.


**Example:**

If, for example, you want to analyze a portfolio in EUR and CHF, then you must define four key figures for the final results procedure. Each key figure should have the same abstract basic key figure; you should use the key figures of the single results procedure (key figure category PAPOS or PAFLW). This ensures that the system calculates the key figures of final results procedure 1 on the basis of the results of the single record procedure.

**Note:**

Since single record procedure 1 contains additive key figures only (those that can be totaled, which are positions and flows in the evaluation currency), it is independent of the portfolio hierarchy.

Note that the rate-of-return key figures that you assign to final results procedure 2 must have the same interval category. Therefore, for each procedure you can use either the key figure categories PAYLD and PAYLDCC, or the key figure categories PAYLDSNC and PAYLDSNCCC. The system checks whether all the key figures assigned to the procedure have the same period. The key figures of category PAYLD and PAYLDCC should therefore have the same values for the Yield Period Start indicator: In the same way, key figures of category PAYLDSNC or PAYLDSNCCC must have the same value in the Interval for Periods field. If this is not the case, the system displays a warning message.

**Note:**

The results for the final results procedure are based on the data of a single records procedure, and can be recreated at any point in time provided that the single records still exist. This means that you can delete the final results from the database if required.

**Additional Notes**

If you want to improve system performance during the evaluations, note the following:

Choose only a small number of analysis characteristics.

Do not use characteristics that refer to too small an entity (such as business partner number or transaction number).

Specify the start date and the end date in the analysis parameters of the financial objects.

Use the continuous compounding method in the yield curve to improve the runtime.

Ensure that portfolio hierarchies do not contain more than 10,000 end nodes.

###### Analyzer Information System (2 of 3)

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Use of the Results Database in Portfolio Analyzer > Analyzer Information System | L5 | trm03 p.249 | loio `65cd36e8663f4ddb9f9b14dc72c40dc9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/65cd36e8663f4ddb9f9b14dc72c40dc9.html?locale=en-US)

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

- 1. In the application menu for Treasury and Risk Management, choose Market Risk Analyzer Information System Analyzer Information System (transaction AIS_STDREP).
- 2. The system displays a selection screen.


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
||The system displays the selection parameters that you have specified when you called the Analyzer Information System.|
||The system compares the current data records with the older data records from the Results Database. In a dialog box, you can enter the start date and time periods for the historical comparison.|
||The system displays the calculation bases of the evaluations, including market data such as yield curves and volatilities.|


|Action|Function|
|---|---|
||The system displays the application log for the evaluations.|
||The system displays the attributes of the key figure selected, including the key figure name and the key figure category.|
||The system displays the final results procedure that is assigned to the key figure selected.|
||The system displays financial objects and their results.|
||The system displays the key figures for a different analysis date.|

###### Hierarchies of Key Figure Categories - Portfolio Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Portfolio Analyzer > Use of the Results Database in Portfolio Analyzer > Analyzer Information System > Hierarchies of Key Figure Categories - Portfolio Analyzer | L6 | trm03 p.251 | loio `21ca8322b76d40e3b72eea1846bd33c7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/21ca8322b76d40e3b72eea1846bd33c7.html?locale=en-US)

The system can calculate values only for key figures in the predefined hierarchies for key figures (attributes must be defined for each key figure). The individual key figures are interdependent both from a business and calculation point of view. The interdependencies for the components are shown in the diagrams below:

[figure TRM03-F357 - Key figures for the calculation of revenue (shown in gray) have two basic key figures. The following key figures can be added: position in position currency, flow in transaction currency, flow in calculation currency, and the position in calculation currency.]

Key figures for the calculation of revenue (shown in gray) have two basic key figures. The following key figures can be added: position in position currency, flow in transaction currency, flow in calculation currency, and the position in calculation currency.

**Related Information**

Results Database

