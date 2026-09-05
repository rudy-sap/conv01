# Risk Management > Basics > Portfolio Hierarchies - SAP TRM Knowledge Base (branch split)

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

##### Portfolio Hierarchies

> **Path:** Treasury and Risk Management > Risk Management > Basics > Portfolio Hierarchies | L4 | trm02 p.26 | loio `fe01c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fe01c55368511d4be10000000a174cb4.html?locale=en-US)

**Definition**

Portfolio hierarchies are used to arrange the characteristics of a view into a structure.

**Use**

Risk values can be calculated on an aggregated basis. Portfolio hierarchies are used to aggregate, on different hierarchy levels, financial transactions stored in the data pool.

**Editing portfolio hierarchies**

Defining and generating portfolio hierarchies

When you define a portfolio hierarchy, choose characteristics from a view, and put in the order required. When you generate a portfolio hierarchy, the system combines each characteristic value with the other characteristic values in succession until all possible combinations ( base portfolios ) exist. This results in a tree structure, in which larger evaluation units are divided into increasingly smaller ones.

The following example shows a portfolio hierarchy consisting in the characteristics company code and product type .

[figure TRM02-F013 - The system then creates base portfolios if transactions exist that have the relevant (new) combination of characteristic values. If the analysis structure does not contain any transactions, then there are no base portfolios, and the portfolio hierarchy consists of its overall structure only.]

The system then creates base portfolios if transactions exist that have the relevant (new) combination of characteristic values. If the analysis structure does not contain any transactions, then there are no base portfolios, and the portfolio hierarchy consists of its overall structure only.

If multiple characteristic values exist, then we recommend that you use characteristic hierarchies , which you need to have already defined. You use characteristic hierarchies to group your characteristics, which makes them easier to manage. The following

example shows a portfolio hierarchy consisting in the characteristic company code and product type , and a characteristic hierarchy for the product type characteristic.

[figure TRM02-F014 - example shows a portfolio hierarchy consisting in the characteristic company code and product type , and a characteristic hierarchy for the product type characteristic.]

Based on a view, you can create multiple portfolio hierarchies, whose structures depend upon the sequence of the characteristics, and upon the characteristic hierarchies used. If you want to analyze only certain characteristic values, then you can flag the relevant characteristic hierarchies as selective . The following example shows a selective portfolio hierarchy, which is restricted to the value Frankfurt for the characteristic company code .

[figure TRM02-F015 - When you define hierarchies, you are defining the range of options available to you in the various analysis functions in the Risk Management system. If you create a large number of hierarchies, then you can run evaluations at a relatively detailed level. However, this can lead to long run times, so you have to balance the level of detail you need with system performance.]

When you define hierarchies, you are defining the range of options available to you in the various analysis functions in the Risk Management system. If you create a large number of hierarchies, then you can run evaluations at a relatively detailed level. However, this can lead to long run times, so you have to balance the level of detail you need with system performance.

Extending portfolio hierarchies

You can make the entities you use for evaluations smaller at any time. To do this, you insert one or more new characteristics into the lowest level of the hierarchy. You cannot change the higher levels of the hierarchy, which means that you cannot change the sequence in which the characteristics appear in the hierarchy, or delete characteristics. This would mean that the program could no longer access evaluation data.

Deactivating and reactivating portfolio hierarchies

If a portfolio hierarchy is no longer relevant for evaluations, you can deactivate it. You can even deactivate it if evaluation data based on the portfolio hierarchy is stored in the report data memory, or in the procedure for final results for a result database. Deactivated portfolio hierarchies can only be used to display existing results, and are not updated when financial objects are created. You cannot use a deactivated portfolio hierarchy to select transactions, or run calculations.

When you reactivate a deactivated portfolio hierarchy, the system regenerates it, and, in so doing, updates it. Providing that no nodes have been deleted in the current definition of the characteristic hierarchy, then the system also updates the characteristic hierarchy. It then adds all new base portfolios to the tree structure.

Deleting portfolio hierarchies

If the report data memory, or a procedure for final results for a result database, does not contain any evaluation data, and no archived evaluation data, that are based on a particular portfolio hierarchy, then you can delete that portfolio hierarchy. Otherwise, you must first delete the evaluation data that is based upon it. You do this by using the administration transaction of the respective application. When you delete a portfolio hierarchy, you delete all components of the hierarchy. These include the link between the portfolio hierarchy and the views, the structure, and all texts and attributes.

Updating portfolio hierarchies

The system usually updates the portfolio hierarchy when an analysis structure is created for a financial object. This occurs during data transfer. However, this automatic update is not possible if another user is editing the portfolio hierarchy (in change mode) at the same time. In this case, the system informs you that the portfolio hierarchy has to be updated manually at a later point in time.

For more information about updating and generating portfolio hierarchies, and about reorganizing base portfolios, see reorganization tools .

###### Editing Portfolio Hierarchies

> **Path:** Treasury and Risk Management > Risk Management > Basics > Portfolio Hierarchies > Editing Portfolio Hierarchies | L5 | trm02 p.28 | loio `0102c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0102c55368511d4be10000000a174cb4.html?locale=en-US)

**Defining and Changing Portfolio Hierarchies**

- 1. In the Implementation Guide (IMG) choose the following path:


Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings Define Portfolio Hierarchy .

If you are using your system as a productive system, then you can access this transaction from the SAP Easy Access screen under the respective components by choosing Evaluation Control Portfolio Hierarchy Define

.

- 2. Define the portfolio hierarchy as follows:

- a. Choose New Entries. The system displays the table in which you define the portfolio hierarchy.
- b. Enter a three-digit number, a name, and a short and long description for the portfolio hierarchy.
- c. If required you can enter an authorization group.
- d. Choose Save.



- 3. Define the structure of the portfolio hierarchy as follows:


- a. Select the portfolio hierarchy.
- b. Choose Structure.


- c. Choose New Entries. The system displays the table in which you edit the characteristics.
- d. In the Characteristic column choose the required characteristics from the view.
- e. In the Sort column, use numbers, which do not have to be sequential, to define the order of the characteristics. The lowest number means the highest level of the hierarchy.
- f. If required, in the CHie (characteristic hierarchy) column you can choose a characteristic hierarchy.

- g. In the Cat (category) column, specify whether the characteristic hierarchy is to be used selectively, or not selectively.
- h. Choose Save.



If you want to change the portfolio hierarchy at a later point in time, then you need to repeat Steps 1 and 3a through 3h.

If, in the meantime, evaluation data has been generated based on the portfolio hierarchy, you can only extend the portfolio hierarchy. In this case, you cannot delete any characteristics, or change their sequence. You can add characteristics only at the lowest level of the hierarchy, which means that you have to give them higher sort order numbers.

If a portfolio hierarchy has been deactivated, then you can change only its description.

**Displaying Portfolio Hierarchies**

1. From the SAP Easy Access screen, under the respective component choose Evaluation Control Portfolio Hierarchy Display .

In the right-hand part of the screen, the system displays all the base portfolios that exist for the selected portfolio hierarchy.

**Deactivating, Reactivating, and Deleting Portfolio Hierarchies**

- 1. On the SAP Easy Access screen, in the respective component choose Evaluation Control Portfolio Hierarchy Delete/Deactivate . In the left-hand part of the screen, the system displays a list of the portfolio hierarchies, sorted by

their views, and their current status.

- 2. Choose the portfolio hierarchy whose status you want to edit.
- 3. To deactivate a portfolio hierarchy, choose Deactivate. The system sets the status of the portfolio hierarchy to inactive.



To reactivate an inactive portfolio hierarchy, choose Inactive -> Active. The system sets the status of the portfolio hierarchy to active.


To delete a portfolio hierarchy choose Delete. The system deletes the portfolio hierarchy if no dependent data exists for it.

For information about other options for processing portfolio hierarchies, see Reorganization Tools.

