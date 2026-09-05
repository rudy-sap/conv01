# Risk Management > Accounting Analyzer - SAP TRM Knowledge Base (branch split)

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

#### Accounting Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Accounting Analyzer | L3 | trm03 p.252 | loio `c8eb6a9db44a4959833d2dc7e23a8a02` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c8eb6a9db44a4959833d2dc7e23a8a02.html?locale=en-US)

The Accounting Analyzer enables you to evaluate positions and subpositions in the Transaction Manager with regard to their position component values.

**Use**

The Accounting Analyzer reads the position component values of the positions and subpositions from the Transaction Manager and stores them as key figures in the Result Database (RDB). This enables you, for example, to store the position component values on a daily or weekly basis based on the original market data in the Result Database. You also can calculate your own position key figures (based upon the original position components) which are not available in the position management of the Transaction Manager.

From the Result Database, you can generate reports in the Analyzer Information System (AIS), which displays these key figures.

You can set up portfolio hierarchies with differentiation criteria unequal to company code, security class, and security account, which enables you to aggregate position values on different levels. For example, you can aggregate the values on the product type level.

[figure TRM03-F358 - The Accounting Analyzer saves the results of all evaluations in the Result Database (RDB).]

The Accounting Analyzer saves the results of all evaluations in the Result Database (RDB).

The Accounting Analyzer calculates all key figures based on the key figure categories, which are predefined in the system. You assign each key figure to an evaluation procedure. You can assign more than one key figure to each evaluation procedure, but each

key figure can be assigned once only.

The following key figure categories are available:

AAPOSPosition Key Figure

AAPOSCCPosition Key Figure in Calculation Currency

AAGENPOSGeneric Position Key Figure

AAGENPOSCCGeneric Position Key Figure in Calculation Currency

You create key figures by choosing a key figure category and entering the attributes of the key figure. You can also use existing key figures as the basis for defining new key figures. You do this by specifying a basic key figure when you define the new key figure. The system then copies the values of the basic key figure and adds them to the new key figure.

Single Record Procedure (SRP)

In the single record procedure, the system takes the position values in position currency or local currency stored in the Transaction Manager and loads them into the result database.

Final Results Procedure

The system translates the position values and flows calculated in the single records procedure into the calculation currency.

**Implementation Considerations**

You use the Accounting Analyzer for analyzing your positions and subpositions in the Transaction Manager. To do so, you need to create financial objects for each position and subposition.

You can activate the automatic financial object integration for positions and subpositions in Customizing for TRM under Basic Analyzer Settings Automatic Integration of Financial Objects in Transaction Master Data Subledger Positions and Subpositions Activate/Deactivate Financial Object Integration .

Under Basic Analyzer Settings Automatic Integration of Financial Objects in Transaction Master Data Subledger Positions and Subpositions Define Derivation Strategy for Subledger Positions and Subpositions , you define rules for automatically filling the fields of the financial object.

If you do not use automatic integration, you can create the financial objects for the subledger positions and subpositions by using function Maintain Financial Object for Subledger Position and Subpositions (transaction JBDO1). This function can also be used to change an existing FO.

In the Customizing of the TRM under Accounting Analyzer Valuation Settings Define and Set Up Evaluation Types , you have to define one or more evaluation types.

To read the position component values from the Transaction Manager, you have to Define Key Figures and Evaluation Procedures (Transaction AFWKF_AA). You do this in Customizing for TRM under Accounting Analyzer Result Database

.


To display and aggregate key figures in the Analyzer Information System (AIS), you have to create Portfolio Hierarchies. You do this in the area menu of the Accounting Analyzer under Evaluation Control Portfolio Hierarchy Create . See also: Editing Portfolio Hierarchies

We recommend that you define a filter to restrict the analysis to particular transactions. Note the additional information about Customizing for the respective activity in the Implementation Guide: Define Filters

To display the results, you need to define a layout . Note the additional information about Customizing for the respective activity in the Implementation Guide: Define Initial Layout

**Integration**

The Accounting Analyzer is part of the SAP Treasury and Risk Management (TRM).

**Features**

Accounting Analyzer Tools

- 1. Basic settings in Customizing and master data mentioned under Implementation Considerations.
- 2. The financial objects have to be created (automatically or manually).
- 3. Generate the values for single records key figures for the selected financial objects, and save them on the database. To do this, choose Tools Result Database Determine Single Records .

You need to distinguish between the following runs when generating the single records:

If you choose a save ID, you can use a saved dataset to analyze an individual record. This is useful for some analyses and for testing purposes in particular.

- 4. Generate the key figure value for the final results on the basis of the single records that have already been generated. Save the data to the database. To do this, choose Tools Result Database Determine Final Results .


|Run|Description|
|---|---|
|Basic Run/Basic Run with Test Selections from Filter|Key figure values are calculated|
|Correction Run with Test Selections from Filter|Key figure values are calculated for the following positions/subpositions: Positions/subpositions that were imported into the system after the generation of single records was started Incorrect positions/subpositions that have been changed after the basic run was carried out|
|Reversal Run|The single records acquire reversed status and can be regenerated in a basic run|


**Note:**

If, after having carried out a basic run for single records, you start a basic run for the final results and then start an adjustment run for the single records, your data may be inconsistent. Therefore, you need to ensure that you delete the final results in a deletion run and restart the basic run for final results after the correction run for the single records has finished.

The key figure values at single record and final results level are stored on the result database.

To delete single records, go to the SAP Easy Access Screen and choose AccountingFinancial Supply Chain Management

Treasury and Risk Management Accounting Analyzer Tools Results Database Delete Non-Archived Single Records


You should use this transaction in your test system only. In your productive system, you should reverse single records. Choose Accounting Financial Supply Chain Management Treasury and Risk Management Accounting Analyzer

Tools Result Database Determine Single Records .

Single records generated in this way can be archived.

- 5. You can use the Analyzer Information System to display them.

##### Define Key Figures and Evaluation Procedure (AA)

> **Path:** Treasury and Risk Management > Risk Management > Accounting Analyzer > Define Key Figures and Evaluation Procedure (AA) | L4 | trm03 p.255 | loio `ab8ba4e24e8c45b4911f935a1b89e0f9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ab8ba4e24e8c45b4911f935a1b89e0f9.html?locale=en-US)

**Use**

With this function, you create the key figures, the procedure for single records, and the procedure for final results that is used to calculate results and place those results in the results database. When you create key figures, you do so in relation to a predefined key figure category. In business terms, the key figures are all interrelated, which means that not all key figures can be assigned to the procedures for single records and final results.

For more information about the interdependency of key figures, see Results Database in SAP Library under Market Risk Analyzer Market Risk Analysis Information System .

For information about the hierarchies of key figure categories available in the Accounting Analyzer, see also Hierarchies of Key Figure Categories - Accounting Analyzer

**Note:**

Notes on transporting data

Key figures and evaluation procedures are not transported automatically from the test system to the production system. If you want to transport them, choose Tools Transport Objects . On the tabs, choose the relevant key figures and evaluation procedures. If you want to choose more than one option, you can do so by pressing the control key or the shift key on your keyboard while using the cursor to select the key figures or evaluations. You can select only current key figures and evaluation procedures. You cannot choose any historical versions. Choose Transport Selected Objects.

Versioning

Versions of key figures and their assignments to evaluation procedures can be created on the basis of dates. The Valid From field is used for this purpose. If you do not specify the date from which the key figures and their assignments are valid, the system takes the most recent date possible. In other words, if no evaluation has been run, the date of the latest

version is used. If an evaluation has already been run, the system takes the date of the run + 1 day. However, you can choose a later date if necessary.

A new version is created when a value has changed in at least one field in the attributes part of the key figure or of the valuation procedures.

Exceptions: the Name and Entered By/Changed By fields. The system saves the previous version automatically as an historical version.

The system applies the date (including the Valid From field) as the criterion for versioning. Changes made on date x lead to the creation of a new version. The new version applies from date x, which means that, if the program reads the data on date x, then it reads the versioned (old) attributes.

**Prerequisites**

We recommend that you define a filter to restrict the analysis to particular transactions. Note the additional information about Customizing for the respective Customizing activity: Define Filters.

To be able to display the results, you need to have already defined a layout. Note the additional information about Customizing for the respective activity in the Implementation Guide: Define Initial Layout.

You need to have already defined the portfolio hierarchies that you require in the area menu of the Accounting Analyzer under Evaluation Control Portfolio Hierarchies Create (transaction AFWPH).

You need to have already defined an evaluation type in Customizing for the Accounting Analyzer under Valuation Settings Define and Set Up Evaluation Types .

**Activities**

Define Key Figures

- 1. Under Accounting Analyzer Evaluation Control Results Database Define Key Figures and Evaluation Procedures , choose Key Figure.
- 2. Enter a short name for the key figure and the Valid From date.

Choose Create.

- 3. On the screen that appears, choose the key figure category Basic Key Figure Category (abstract) (ABB00).

Enter a description

Assign an evaluation type

The evaluation type assigned here is used for the currency translation from key figures in position currency / local currency to calculation currency in the final result procedures.

Assign the valuation area

Save the data.

- 4. Create all key figures related to this basic key figure.


Create a position key figure (AAPOS).

- a. In the Hierarchy of KF Categories screen area, choose the key figure category AAPOS Position Key Figure.
- b. Enter a key for the key figure.
- c. Choose the AA key figure category that you want to read from the Transaction Manager. The AA key figure categories represent the position components (original and derived). They are all available in position currency (PC) or in local currency (LC). When the key figure is defined in local currency and the position currency of the position is different, a currency translation is performed based on the evaluation type assigned in the position management procedure of the respective position.
- d. Choose the key date reference Position Value Date or Posting Date.
- e. Enter a description.
- f. Save your entries.


**Example:**

AA key figure category 001 (Purchase Value in Position Currency) is the position component Purchase Value 1001 in PC.

005 Book Value in Position Currency is the derived position component Book Value 9001 in PC.

In the Hierarchy of KF Categories screen area, you can now choose the key figure category AAPOSCC Position Key Figure in Calculation Currency to create the corresponding key figure that translates the value of the key figure into

another currency. You have to define a key for the key figure, choose the currency, and enter a description for the key figure. Afterwards, save your data.

Select the base key figure again. Repeat the steps above for all position key figures and position key figures in calculation currency that you need.

You can also create a generic key figure with the key figure category AAGENPOS Generic Position Key Figure.

- a. In the Hierarchy of KF Categories screen area, choose the key figure category AAGENPOS Generic Position Key Figure.
- b. Enter a key for the key figure.
- c. Choose the key date reference Position Value Date or Posting Date
- d. Choose the currency type Position Currency or Local Currency.
- e. Enter a description.
- f. In the Formula area, enter your own derived position component.


- i. Choose Insert Row.
- ii. Choose an original position component and enter the + or — sign.
- iii. Enter the second position component.
- iv. Continue until you have added all position components needed for your key figure.
- v. Save the data.


In the Hierarchy of KF Categories screen area, you can now choose the key figure category AAGENPOSCC Generic Position Key Figure in Calculation Currency to create the corresponding key figure that transfers the value of the key figure into another currency. You have to define a key for the key figure, choose the currency, and enter a description for the key figure. Afterwards, save your data.

Define Single Record Procedure and Final Result Procedures

- 1. Under Accounting Analyzer Evaluation Control Results Database Define Key Figures and Evaluation Procedures , choose Single Record Procedure (SRP) and then choose Create.
- 2. Enter a key and a description for the SRP.
- 3. Enter a filter.

The filter defines which positions and subpositions are evaluated.

- 4. Enter a key and a description for the final result procedure and assign the single record procedure.
- 5. Assign a portfolio hierarchy.
- 6. Save your data.
- 7. Assign key figures to the SRP.

All unassigned key figures with key figure category AAPOS or AAGENPOS are displayed. Choose the first key figure.

- 8. Assign the other key figures.

You can only assign key figures from one key figure hierarchy (key figures of one basic key figure).

- 9. Assign the key figures for the final result procedure. All unassigned key figures with key figure category AAPOSCC or AAGENPOSCC are displayed.


- 10. Save your data.

##### Analyzer Information System (3 of 3)

> **Path:** Treasury and Risk Management > Risk Management > Accounting Analyzer > Analyzer Information System | L4 | trm03 p.258 | loio `35270a179a384d9f9a91dbc18ff16736` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/35270a179a384d9f9a91dbc18ff16736.html?locale=en-US)

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
||The system displays the application log for the evaluations.|
||The system displays the attributes of the key figure selected, including the key figure name and the key figure category.|


|Action|Function|
|---|---|
||The system displays the final results procedure that is assigned to the key figure selected.|
||The system displays financial objects and their results.|
||The system displays the key figures for a different analysis date.|

###### Hierarchies of Key Figure Categories - Accounting Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Accounting Analyzer > Analyzer Information System > Hierarchies of Key Figure Categories - Accounting Analyzer | L5 | trm03 p.260 | loio `23f1f48232ec425980645e45de916c12` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/23f1f48232ec425980645e45de916c12.html?locale=en-US)

The system can calculate values only for key figures in the predefined hierarchies for key figures (attributes must be defined for each key figure). The individual key figures are interdependent both from a business and calculation point of view. The interdependencies for the components are shown in the diagrams below:

[figure TRM03-F374 - The system can calculate values only for key figures in the predefined hierarchies for key figures (attributes must be defined for each key figure). The individual key figures are interdependent both from a business and calculation point of view. The interdependencies for the components are shown in the diagrams below:]

**Related Information**

Results Database

