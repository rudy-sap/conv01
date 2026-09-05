# Risk Management > Basics > Results Database - SAP TRM Knowledge Base (branch split)

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

##### Results Database

> **Path:** Treasury and Risk Management > Risk Management > Basics > Results Database | L4 | trm02 p.38 | loio `5ffa4b530f57ff4fe10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5ffa4b530f57ff4fe10000000a44176d.html?locale=en-US)

You use the results database to calculate defined key figures and to save these figures and evaluate them as you require as part of end-of-day processing, for example. This function extends the options that have been available up until now, namely saving and displaying evaluation results only (such as saving report data during research activities).

The results database is used in the following components:

Market Risk Analyzer

Portfolio Analyzer

Accounting Analyzer

In the results database, generation and reporting of the results is performed separately. This has the following advantages:

Once the results data has been generated, you can display it any number of times in various different ways (different combinations of key figures, different layout) without having to perform any recalculations.

The evaluation results are available permanently, even after upgrading to a different release, and can be archived.

You are able to make subsequent changes and corrections to the results. This is necessary if the transaction position changes or in the event of valuation errors.

**Prerequisites**

The key figures and evaluation procedures that you want the system to calculate must already be defined in Customizing. In particular, the key figures need to have been assigned to evaluation procedures. We also recommend that you define a filter to limit the number of transactions that are evaluated by the system. You need to have already defined a layout to be able to display the results using the reporting functions. Note the additional information about the Customizing activities Define Filter, Edit Key Figures and Evaluation Procedures, and Define Initial Layout.

**Process**

The system can calculate key figure values only for those key figures that belong to one of the hierarchies of key figure categories delivered by SAP. These hierarchies show how key figures interrelate from a calculation point of view. There are two types of key figure: single records key figures and final results key figures. Single records key figures are calculated for each single transaction, whereas final results key figures are calculated by aggregating the values of single records key figures across an entire portfolio hierarchy.

[figure TRM02-F038 - Process Flow]

Process Flow

- 1. Generate the values for single records key figures for the selected financial objects and save them to the database. To do this, choose Tools Results Database Determine Single Records (transaction RAEP1).


You need to distinguish between the following runs when generating the single records:

|Run|Description|
|---|---|
|Basic Run/Basic Run with Test Selections from Filter|Key figure values are calculated.|
|Correction Run/Correction Run with Test Selections from Filter|Key figure values are calculated both for transactions that were imported into the system after the generation of single records was started as well as for incorrect transactions from the basic run that have subsequently been changed.|
|Reversal Run|The single records acquire the status Reversed and can be regenerated in a basic run.|


If you choose a save ID, you can use a saved dataset to analyze an individual record. This can be very useful for certain types of analysis (such as backtesting).

- 2. Generate the key figure values for the final results on the basis of the single results that have already been generated.

Save the data to the database. To do this, choose Tools Results Database Determine Final Results (transaction RAEP2).

- 3. As a result, the key figure values at single-record level and at final-results level are stored in the results database.
- 4. You can use the Analyzer Information System to display this data.

- 5. Single records generated in this way can be archived.


**Caution:**

If, after having performed a basic run for single records, you triggered a basic run for the final results and then started a correction run for the single records, your data may be inconsistent. For this reason, you need to ensure that you delete the final results in a deletion run and restart the basic run for final results after the correction run for the single records has finished.

**Related Information**

Use of the Results Database in Portfolio Analyzer Hierarchies of Key Figure Categories - Market Risk Analyzer Hierarchies of Key Figure Categories - Portfolio Analyzer Hierarchies of Key Figure Categories - Accounting Analyzer Formula Editor Analyzer Information System

###### Formula Editor

> **Path:** Treasury and Risk Management > Risk Management > Basics > Results Database > Formula Editor | L5 | trm02 p.40 | loio `4f67295b1a3a43d8e10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f67295b1a3a43d8e10000000a42189c.html?locale=en-US)

**Use**

In this function, you use existing key figures as the basis for defining formula-based key figures, which you can then display in the Analyzer Information System (AIS).

Integration

The system calculates formula-based key figures at runtime only. This takes place when the Analyzer Information System is called. In the Analyzer Information System, the system displays the formula-based key figures and the key figures that you stored in the initial layout for the AIS. Unlike the other key figures, the formula-based key figures are not stored in the database.

When the AIS is called, the system checks all the formulas of the initial layout. If errors occur, the system does not display the formulas in question. However, it does display an error log. This occurs if, for example, you used key figures to define formulas and these key figures were deleted from the initial layout.

**Prerequisites**

You have defined all the key figures you need for the formula-based key figures.

If you want to use book values for formula-based key figures, you have entered the settings required to import them into the system.

**Activities**

- 1. In Customizing for Financial Supply Chain Management, choose Treasury and Risk Management Market Risk Analyzer or Portfolio Analyzer Results Database Define Formulas for AIS .

The system displays the initial layouts that have already been defined.

- 2. Select the initial layout, and choose the area for which you want to define formula-based key figures.

In this area, the system displays the formula-based key figures that exist.

- 3. If required, create a new formula-based key figure.
- 4. To store a formula for the formula-based key figure, select a key figure and choose Formula Editor.

The system opens the formula editor.

- 5. Define the formula as required, and save your entries.


The formula editor contains the basic mathematical functions and an if function for defining formula-based key figures.

**Note:**

To display the documentation about the formula editor, choose Information.

