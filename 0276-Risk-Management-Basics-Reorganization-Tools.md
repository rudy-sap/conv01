# Risk Management > Basics > Reorganization Tools - SAP TRM Knowledge Base (branch split)

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

##### Reorganization Tools

> **Path:** Treasury and Risk Management > Risk Management > Basics > Reorganization Tools | L4 | trm02 p.259 | loio `2502c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2502c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

You use the reports described below as reorganization tools to ensure the consistency of the data used in risk analysis. You can find the reorganization tools in the menus of the specific Risk Analysis component by choosing Tools Reorganization Tools .

**Features**

The following functions are available:

|Menu Path|Function and tips for using the function|
|---|---|
| Financial Object Maintain Financial Objects|With this report, you can save financial objects generated in a nonintegrated way from multiple transactions. You can activate, deactivate, or check the financial objects. A type 1 derivation takes place.  If you do not specify an analysis structure on the Program Control tab, then the system automatically selects the active analysis structure. By choosing Selection Using Financial Objects, you can specify that type 1 derivation is performed for all transactions. For more information about the transactions, see Additional Notes on Mass Processing Financial Objects .|
| Financial Objects Check Consistency of Financial Objects (Analysis Part)|This report analyzes the administration tables with regard to the following: The dependency between the relevancy indicator and the analysis parameters checks whether the analysis parameters were written to the administration table. The dependency between the update in the view and the active analysis parameters checks whether the Analysis Active indicator was set for the analysis parameters. The dependency between the update and the dependent BP administration table The dependency between the active account and the balance carryforward table The dependency between the characteristic values and the analysis parameters If at least one incorrect financial object is found, you can decide at the end of the run whether this financial object is to be added to a worklist. In addition to selecting the|


|Menu Path|Function and tips for using the function|
|---|---|
| |financial objects by using selection parameters, you can also read the financial objects in the following postprocessing reports by specifying a worklist.|
| Financial Object Remove Inconsistencies from Financial Objects (Analysis Part)|You can use this report to deactivate the analysis parameters of financial objects and delete them from the database. **Note:** It is not possible to delete and activate analysis parameters at the same time. If you generate balances to be carried forward for BCA, you must always set the processing type Set Analysis Param. to Active.|
| Portfolio Hierarchies Generate|You use this report to regenerate portfolio hierarchies. When you do so, the system takes into account any extensions made to the portfolio hierarchy and to the characteristic hierarchy.|
| Portfolio Hierarchies Update|You use this report to update the nodes of portfolio hierarchies. New nodes are added if new combinations of characteristic values have been created since the last time the portfolio hierarchy was updated by new or modified transactions. Therefore, you need to set the Use All Base Portfolios indicator if you think the data might be inconsistent (for example, after an update has failed). In this case, the system reads all the base portfolios in the analysis structure and compares them with those already in the portfolio hierarchy.|
| Portfolio Hierarchies Reorganize Base Portfolios|You use this report to delete all the base portfolios for a view that does not contain any data. All the related portfolio hierarchies are then adjusted. In this way, the portfolio hierarchies contain only the branches that lead to data that currently exists.|
| Financial Object Integration Generate Financial Objects for Class Position in Securities Account - Class Position in Futures Account - Financial Transactions .|With this report, you can generate in an integrated way financial objects for transactions that already exist in the system. A type 2 derivation takes place. |
| Financial Object Integration Edit Financial Objects for Loans Class Position in Securities Account - Class Position in Futures Account - Financial Transactions .|With this report, you can save financial objects generated in an integrated way from multiple transactions. You can activate, deactivate, or check the financial objects. A type 2 derivation takes place. |
| Financial Object Integration Update Financial Objects for Generic Transactions|You use this report to update the financial objects for multiple generic transactions. For example, you use this function to modify the financial objects of generic transactions in a mass run after you have changed the derivation strategies that you use in the automatic integration of financial objects. You can use this transaction to select generic transactions by their internal and external numbers, change date, and the name of the user who last changed them. You can use the test run to check whether the financial objects would be updated correctly. The system creates an application log that contains any financial objects that are incorrect.|


|Menu Path|Function and tips for using the function|
|---|---|
| Financial Object Integration Summarize Loans|You can summarize loans per view by means of the valuation rule, the Asset/Liability indicator, and the Cash Flow indicator. For performance reasons, loans for which the Summarization indicator has been set are summarized only if you have started the loans summarization report specifically for these loans.|
| Financial Object Integration Display Data for Loan Summarization|This shows you the administrative information for the loan summarization report runs.|
| Financial Object Integration Delete Data for Loan Summarization|You can delete the administrative information for the loan summarization report runs.|
| Financial Object Integration Display Worklists|You can display the worklists generated by the consistency check report for the data pool, display the worklist log by double-clicking, display the financial objects per worklist, and delete the worklists.|
| Financial Object Integration Overview of Financial Objects Containing Errors|You can branch directly from error postprocessing to the transaction (loans, financial transactions, generic transactions) or to financial object maintenance (class positions in securities accounts, class positions in futures accounts) to make the corrections required.|
| Financial Object Integration Analyze Logs|You obtain an overview of all logs that were created during the integrated generation of financial objects.|


Use

The reports described below as reorganization tools are used to ensure that data for the risk analysis evaluations is consistent. You can find all the reorganization tools in the menu for the Default Risk and Limit System by choosing Tools Reorganization Tools Financial Object .

Features

The following functions are available:

|Menu Path|Function and tips for using the function|
|---|---|
| Non-Integrated Processing of Financial Objects Process Financial Objects (Counterparty/Issuer Risk)|You use this report to process a large number of non-integrated financial objects. It contains the programs for processing financial objects relevant for counterparty/issuer risk (report KLMASSUPD). A type 1 derivation takes place. The following functions are provided: Save: The system reads the financial objects from the database and saves them again. In doing so, derivations are re-run if appropriate. Activate Limit Part: The same as when saving, but the limit part is activated in addition. Deactivate Limit Part: The same as when saving, but the limit part is deactivated in addition. Check: The system checks the consistency of the selected limit parts. No changes are made on the database.|
| Non-Integrated Processing of Financial Objects Display Logs |You obtain an overview of the logs for the non-integrated generation of financial objects.|
| Financial Object Integration Generate Financial Objects for Loans , Generate Financial Objects for Class Positions in Securities Accounts, Generate Financial Objects for Financial Transactions, and Generate Financial Objects for Bank Accounts.|You use this report to generate financial objects for transactions that already exist in the system. A type 2 derivation takes place. |
| Financial Object Integration Edit Financial Objects for Loans , Edit Financial Objects for Class Positions in Securities  Accounts, Edit Financial Objects for Financial Transactions, and Edit Financial Objects for Bank Accounts|With this report, you can save the generated financial objects of more than one transaction, and activate, deactivate, or check the financial objects. A type 2 derivation takes place. |
| Financial Object Integration Financial Object Integration: Postprocessing|You can branch directly from postprocessing to the transaction (loans, financial transactions) or to financial object maintenance (class positions in securities accounts) to make the relevant corrections.|
| Financial Object Integration Financial Object Integration: Logs|You obtain an overview of all logs that were created during the integrated generation of financial objects.|
| Financial Object Integration Update Financial Objects for Generic Transactions|You use this report to update the financial objects for multiple generic transactions. For example, you use this function to modify the financial objects of generic transactions in a mass run after you have changed the derivation strategies that you use in the automatic integration of financial objects. You can use this transaction to select generic transactions by their internal and external numbers, change date, and the name of the user who last changed them. You can use the test run to check whether the financial objects would be updated correctly. The system creates an application log that contains any financial objects that are incorrect.|

