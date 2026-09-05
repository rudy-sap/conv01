# Data Management in Treasury and Risk Management - SAP TRM Knowledge Base (branch split)

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

### Data Management in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management | L2 | trm11 p.64 | loio `4c075fdaeaaa488fae5e59d4690b250b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c075fdaeaaa488fae5e59d4690b250b.html?locale=en-US)

Options to manage your data in SAP S/4Hana Treasury and Risk Management

**Key Features**

Deletion of Personal Data in Treasury and Risk Management

Archiving Data in Treasury and Risk Management

In this section, you can find the functions available for managing your data.

**Related Information**

Data Management in SAP S/4HANA

#### Deletion of Personal Data in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Deletion of Personal Data in Treasury and Risk Management | L3 | trm11 p.64 | loio `bbbea68f24bc483cb6401edae11710f3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bbbea68f24bc483cb6401edae11710f3.html?locale=en-US)

The financial transactions portrayed in Treasury and Risk Management are B2B transactions between your company and banks, financial institutions, brokers, or similar institutions. Likewise, the master data required for the processes in Treasury and Risk Management relate to companies and financial institutions. In Treasury and Risk Management, checks are implemented that do not allow the use of business partners who are natural persons. If you use business partners who are natural persons in Treasury and Risk Management, you will get the following error message: You cannot assign bus. partner &1 because the partner is a

natural person (message class TI, message number 031). Consequently, the simplified blocking and deletion of personal data in Treasury and Risk Management using SAP Information Lifecycle Management (SAP ILM) is not needed in Treasury and Risk Management, but it is also supported with an end of purpose check (function module TRTM_BUPA_EOP_CHECK).

**Note:**

If you use Treasury and Risk Management to portray financial transactions with natural persons or your use of the Treasury and Risk Management involves natural persons in other ways, you need to deploy additional technical and organizational measures to ensure that you respect the deadlines governing the storage and deletion of personal data. If these prerequisites are fulfilled, you can suppress the error message of these checks for natural persons by switching off the configurable message 031 of application area TI in the Customizing activity Change Message Control under Treasury and Risk Management

Transaction Manager General Settings Tools Configurable Messages .

If you only use Risk Management to analyze Transaction Manager data, it also applies that the simplified blocking and deletion of personal data in the Transaction Manager through SAP Information Lifecycle Management (SAP ILM) is not necessary; nevertheless, a where-used check (function module RM_BUPA_WUC_CHECK) is also available for this purpose.

If you use Risk Management to analyze data that also contains data on natural persons or your use of Risk Management otherwise involves natural persons, you must ensure you adhere to the retention period for personal data and ensure its subsequent deletion by taking appropriate technical and administrative measures of your own.

**Trader and Contact Person**

Traders

In the Transaction Manager, you define traders. These traders are given authorizations, and your employees who create financial transactions in the role Treasury Specialist - Front Office are assigned a trader to their user. The trader name is visible in the financial transaction data. As the trader is part of the financial transaction data, the table entries for a trader are archived together with the financial transaction data. When a specific trader is no longer required, for example, because the employee has left your company, you remove the authorization for the trader using the function Trader Autorization (transaction TBT1). In addition, you delete the entries for the user in Customizing under Define User Data. If all financial transactions created by the trader are archived, you can delete the trader in Customizing under Define Trader.

You can use the function Display Where-Used List of Traders (transaction FTR_DIS_TRADER) to see in which tables a specific trader is entered.

Contact Persons

It is possible to enter the name of a contact person in financial transactions. These names are part of the financial transaction data and are archived together with the financial transactions. You can use the function Display Where-Used List of Contact Persons (transaction FTR_DIS_CONTPERS) to see in which tables a specific contact person is entered.

##### Business Partner End of Purpose (EoP) Check in TRM - Transaction Manager (FIN-FSCM-TRM-TM)

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Deletion of Personal Data in Treasury and Risk Management > Business Partner End of Purpose (EoP) Check in TRM - Transaction Manager (FIN-FSCM-TRM-TM) | L4 | loio `4a44d32c0cb04191b7e141ea7a9147a6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4a44d32c0cb04191b7e141ea7a9147a6.html?locale=en-US)

The Transaction Manager (FIN-FSCM-TRM-TM) in Treasury and Risk Management provides an (EoP) check to determine whether a business partner is still relevant for business activities in the application or whether it can be blocked.

|Application Name|Application Description|Business Partner Type|
|---|---|---|
|TRM-TM|Treasury and Risk Management Transaction Manager|Business Partner|


**Prerequisites**

You have activated the business function ILM-Based Deletion of Business Partner Data (BUPA_ILM_BF).

**Technical Details**

ILM Objects

The EoP check evaluates retention policies and data for the following ILM objects:

TRTM_FTR Financial Transactions

TRTM_TPM Positions

EoP Check Implementation

TRM provides the following functions for the EoP check for business partners:

The application searches for the following data relating to business partners:

Counterparty and guarantor in table VTBFHA

Payer and present bank in table VTBFHAPO

Partner assignment in table VTBPA

Issuer of a security in table VWPANLA

Issuer of a commodity in table TRCOT_CTY_EXCHNG

Beneficiary, applicant, issuing bank, advising bank, and confirming bank in table VTBFHAZU

Nominated bank in table TLCT_NOMI_BANK

The end of business is reached when the term end of the related financial transaction, the term end of the security, and the term end of the commodity are reached.

The application returns the following time reference representing the end of business date to the EoP check as the "start of retention time" (SoRT). This means that the following applies:

Term end with respect to each individual combination of company code and product type where the business partner is used in any of the data described above.

The EoP check for the Transaction Manager supports the use of application rule variants based on ILM rule groups: If you want to define differing residence and retention periods for business partner data depending on application specific condition fields, you can define application rule variants in Customizing under Cross-Application Components Data

Protection Blocking and Unblocking of Data Business Partner Assign Application Rule Variants and Rule Groups for EoP Check for Transaction Manager TRM-TM

In this Customizing activity, you assign the application rule variants to ILM rule groups that you have created in transaction IRM_CUST_CSS (Information Retention Manager - Calling Customer-Specific Settings). To determine the retention rules, the ILM rule groups must also be entered in the corresponding retention rules for the ILM objects of Treasury and Risk Mananagement in transaction IRMPOL (ILM Policies).

The EoP check for the Transaction Manager calculates the end of residence time (representing the EoP) based on residence periods maintained for the ILM object CA_BUPA that is activated for audit area BUPA_DP for the application name TRM-TM and the existing rule variants.

**Handling of Archived Data**

The Transaction Manager considers archived data in the following way for the EoP check of business partners:

The EoP check implementation uses the Archive Information System to consider data from archive files.

**See Also**

For more information, see the SAP Help Portal for SAP S/4HANA at http://help.sap.com/s4hana under Product Assistance [Choose Language] Cross-Components SAP Information Lifecycle Management / Data Protection .

##### Display Where-Used List of Traders

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Deletion of Personal Data in Treasury and Risk Management > Display Where-Used List of Traders | L4 | trm11 p.66 | loio `a36d3f2ca745430590112c987d7b6d37` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a36d3f2ca745430590112c987d7b6d37.html?locale=en-US)

With this function, you get a list of the database tables in which a specific trader is entered.

**Use**

In Treasury and Risk Management, you define traders in Customizing under Treasury and Risk Management Transaction Manager General Settings Organization . Using the Manage Trader Authorizations function, you give authorization to these traders. Your employees working in the Treasury Specialist - Front Office business role are assigned to a trader. If a Treasury Specialist - Front Office creates a financial transaction, the name of his or her trader is entered in the data of the financial

transactions. Therefore, the information regarding which trader created a transaction is stored in the financial transaction data, the treasury position data, as well as in the correspondence data. With this function, you can see the database tables in which a specific trader is entered and how often a specific trader is entered in the database tables.

**Activities**

- 1. Call the Display Where-Used List of Traders function (transaction FTR_DIS_TRADER).
- 2. In the Selection area, select the trader.
- 3. In the List Display area, you can set the Only Show Hits indicator. In this case, you see only the tables in which the trader is entered and not all tables that have been checked.
- 4. Execute the report.
- 5. You get a results list displaying all tables in which the trader is entered. You get the technical name of the table, the description of the table, the field in which the trader is entered, and the number of hits for this trader.
- 6. By double-clicking the number of hits, you drill down to the specific table entries.


**Related Information**

Deletion of Personal Data in Treasury and Risk Management

##### Display Where-Used List of Contact Persons

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Deletion of Personal Data in Treasury and Risk Management > Display Where-Used List of Contact Persons | L4 | trm11 p.67 | loio `7e365b0fa9484bacaf737f03a874551f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7e365b0fa9484bacaf737f03a874551f.html?locale=en-US)

With this function, you get a list of the database tables in which a specific contact person is entered.

**Use**

In Treasury and Risk Management, you can enter the name of the contact person in the financial transaction data. This name is also stored in treasury position data and in the correspondence data. With this function, you can see the database tables in which a specific contact person is entered and how often the contact person is entered in the database tables.

**Activities**

- 1. Call the Display Where-Used List of Contact Persons function (transaction FTR_DIS_CONTPERS).
- 2. In the Selection area, enter the name of the contact person. Be aware that you have to enter the name in the same way as the name was entered in the system. The search is case-sensitive.
- 3. In the List Display area, you can set the Only Show Hits indicator. In this case, you will see only the tables in which the contact person is entered and not all tables that have been checked.
- 4. Execute the report.
- 5. You get a result list displaying the tables in which the contact person is entered. You get the technical name of the table, the description of the table, the field in which the contact person is entered, and the number of hits for this contact person.


- 6. You can drilldown to see the table entries by double-clicking the number of hits.


**Related Information**

Deletion of Personal Data in Treasury and Risk Management

##### Delete Personal Data - Credit Risk Analyzer

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Deletion of Personal Data in Treasury and Risk Management > Delete Personal Data - Credit Risk Analyzer | L4 | trm11 p.68 | loio `a7508e29006f4d81994f8907aeca8b94` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a7508e29006f4d81994f8907aeca8b94.html?locale=en-US)

Using this function, you delete remaining personal data of archived business partners in the Credit Risk Analyzer.

**Context**

The report checks data in the Credit Risk Analyzer and deletes all remaining data referring to already archived business partners.

**Procedure**

- 1. Call the Delete Personal Data - Credit Risk Analyzer function (transaction SEMB_DPP_DELETION).
- 2. The Display Log indicator is set by default. You can deselect this indicator.
- 3. Execute the report in test mode.
- 4. After a successful test run, you can execute the report in production mode.
- 5. All data referring to archived business partners are deleted from Credit Risk Analyzer tables.


**Related Information**

Deletion of Personal Data in Treasury and Risk Management

#### Archiving Data in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management | L3 | trm11 p.68 | loio `f8ba83ff72c04364b2162459761ee521` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f8ba83ff72c04364b2162459761ee521.html?locale=en-US)

**Context**

Treasury and Risk Management (TRM) offers you various archiving objects.

**Procedure**

- 1. We recommend that you familiarize yourself with the principles and functions of data archiving. You can use the data archiving functions available in SAP S/4HANA. The SAP data archiving concept is based on the Archive Development Kit (ADK). For all archiving objects with a corresponding ILM object, you can also use SAP Information Lifecycle Management.


Data Archiving in SAP S/4HANA

For more information, see Data Archiving.

ILM-Based Information for the Archiving Object

You can use the ILM-enabled archiving objects with the ILM objects as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the policy category available. Here you can also see which time references are available and which condition fields exist. You can then define your rule structure by specifying which time references and condition fields are used and in which order.

For more information, see alsoSAP Information Lifecycle Management

**2. You can archive the following data in Treasury and Risk Management:**

|Data to Be Archived|Archiving|ILM Object|Time Reference|Authorization Object Specific|Se|
|---|---|---|---|---|---|
| |Object| | |Prerequisites| |
|Financial Transactions|TRTM_FTR|TRTM_FTR|End Date, which is|The following prerequisites must be|Arc|
|The TRTM_FTR archiving object is used to archive and delete financial| | |the end of the term of the financial transaction.|fulfilled before a financial transaction can be archived: The financial transaction|Fin Tra wit|
|transactions of the| | | |must have been settled if the| |
|Transaction Manager as| | | |processing type requires| |
|well as related subentities| | | |settlement.| |
|(such as the related correspondence objects, trade repository objects or the external trade ID).| | | |The flows of the financial transaction relevant for posting have been posted completely.| |
| | | | |The financial transaction has| |
| | | | |acquired the required| |
| | | | |confirmation status (such as| |
| | | | |Confirmed or| |
| | | | |Counterconfirmed).| |
| | | | |This archiving object also| |
| | | | |archives the corresponding| |
| | | | |trade repository objects of| |
| | | | |the financial transactions.| |
| | | | |It is only possible to| |
| | | | |archive trade| |
| | | | |repository objects| |
| | | | |that have acquired| |
| | | | |one of the following| |
| | | | |statuses:| |
| | | | |06 Rejection| |
| | | | |Accepted| |
| | | | |07 Accepted| |
| | | | |08 Obsolete| |
| | | | |09 Reconciled| |
| | | | |10| |
| | | | |Reconciliation| |
| | | | |Failed| |
| | | | |20 Invalid| |
| | | | |If not all TAROs meet these| |
| | | | |criteria, the financial| |
| | | | |transaction cannot be| |
| | | | |archived.| |
| | | | |**Note:**| |
| | | | |These checks are not| |
| | | | |relevant for financial| |
| | | | |transactions in the| |
| | | | |following statuses:| |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
| | | | |Reversed Old Transaction These checks are not relevant for financial transactions in the following activities: Offer Simulation These financial transactions (reversed financial transactions, old financial transactions, offers and simulations) are archived without the above mentioned checks. They only must reach their end of term and fulfill the residence rule.| |
|Correspondence Objects You need archiving object TRTM_CO to archive correspondence objects that have been created outside of financial transactions or if you want to archive correspondence objects independently of the financial transaction. As part of the archiving of financial transactions, correspondence objects relating to financial transactions are archived using TRTM_FTR.|TRTM_CO|TRTM_CO|Start Date of Retention Period is for outgoing correspondence objects the delivery date and for incoming correspondence objects it is the receiving date.|The status of the correspondence object is Completed.|Arc Co Ob TR |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
|Trade Repository Objects You use this archiving object to archive trade repository objects (TAROs) in the Transaction Manager (TRM). This archiving object is used to archive the following groups of trade repository objects: Trade repository objects for financial transactions in Transaction Manager with the action type 30 Valuation and 35 Security Trade repository objects for external transactions Trade repository objects for financial transactions of Transaction Manager are generally archived together with financial transactions with the archiving object (TRTM_FTR). However, from this set of trade repository objects, you can archive just those with the action types 30 Valuation and 35 Security, using the archiving object TRTM_TARO independently of the financial transaction.|TRTM_TARO|TRTM_TARO|Date of last change to the trade repository object|It is only possible to archive trade repository objects that have acquired one of the following statuses: 06 Rejection Accepted 07 Accepted 08 Obsolete 09 Reconciled 10 Reconciliation Failed 20 Invalid|Arc Re Ob TR |
|Positions Treasury and Risk Management manages Treasury positions (for more information, see also positions) for a broad range of financial instruments. Consequently, the criteria for archiving vary depending on the type of |TRTM_TPM|TRTM_TPM|COMPLETION_DATE, which is the end of term of the position group with time offset END_OF_YEAR. This completion date of the position group is reached at the zero position date of the position group, that is, the date from|All flows for a position must have the status Fixed or Reversed. Exception: Open and close flows for OTC transactions Each business transaction must have U (Updated) status.|Arc Po TR |


|Data to Be Archived|Archiving|ILM Object|Time Reference|Authorization Object Specific|Se|
|---|---|---|---|---|---|
| |Object| | |Prerequisites| |
|financial instrument. The| | |which all items in the|The Units or Nominals| |
|following kinds of Treasury| | |item group are zero.|position components must be| |
|positions can be archived:| | | |zero at the start of the| |
|OTC positions| | | |retention period.| |
|(such as money market positions, FX positions, and trade finance positions)| | | |There must not be any business transactions scheduled after the start of the retention period for the position.| |
|Loan positions| | | |The maturity of a position must fall before the start of| |
|Securities positions Listed derivative positions Positions are not archived| | | |the retention period. (Note that the latest date of a position is considered the due date.) If a position forms part of an intragroup transaction, it| |
|individually; instead, they| | | |cannot be archived. For such| |
|are archived in position| | | |a position to be archived, the| |
|groups. Position groups| | | |intragroup status of the| |
|are only used in the context of archiving. A position group is used to group together positions that are so closely related that they cannot be| | | |position must be initial. The position must not form part of a hedging relationship in Hedge Accounting for Positions.| |
|handled separately in archiving.| | | |If a money market position or a loan is used as a hedged| |
|All positions of a position group have the same| | | |item in a hedging relationship in Hedge Accounting, it cannot be archived.| |
|company code.| | | |If a foreign exchange| |
|In addition:| | | |transaction or a derivative is used as a hedging instrument| |
|Securities| | | |in Hedge Accounting, it| |
|positions| | | |cannot be archived.| |
|or listed derivative positions that have| | | |The corresponding fnancial transactions must already be archived.| |
|the same ID number belong to the same| | | |The corresponding loans contract must already be archived.| |
|position| | | | | |
|group.| | | | | |
|OTC| | | | | |
|positions| | | | | |
|and loans| | | | | |
|that have| | | | | |
|the same| | | | | |
|financial| | | | | |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
|transaction number or loan number belong to the same position group. All positions that belong to a business transaction that generates flows for different positions belong to the same position group. This can arise in connection with hedging relationships, securities account transfers, or corporate actions, for example. A position group is archived once all of the positions in that position group can be archived. **Note:** The valuation area, therefore, is not used as a criteria for differentiating position groups.| | | | | |
|Financial Objects The archiving object JB_FOBJ is used to archive financial objects that are no longer required in the online system.|JB_FOBJ|JB_FOBJ| |The end date of the corresponding financial transaction has passed.|Arc Fin Ob JB |
|Payment Requests|FI_PAYRQ| | |You can only archive payment requests that have been cleared.|Arc Pa Re FI_ |
|Detailed Logs for Effectiveness Checks|TRTM_HMLOG| | | |Arc Eff |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
| | | | | |Tes TR |
|Raw Exposures You can use archiving object TRTM_REXP to archive raw exposures. All data relating to the raw exposures is archived. This applies to the header data, raw exposure memo records, sub raw exposures, risk attributes, the different versions, the administrative attributes, and other information. The related exposure positions are not archived with this archiving object.|TRTM_REXP|TRTM_REXP|Due date of the raw exposure (DUE_DATE); if the due date is intial the system detemines the due date from the planning period and planning year.|No additional specific prerequisite must be fulfilled.|Arc Ex TR |
|Exposure Positions You can use archiving object TRTM_EXPOS to archive exposure positions. All data for the exposure position and the related position flows are archived.|TRTM_EXPOS|TRTM_EXPOS|Due date of the exposure position (DUE_DATE); if the due date is intial the system detemines the due date from the planning period and planning year.|The raw exposures contributing to the exposure position are already archived or deleted.|Arc Ex Po TR |
|Security Class Data You use archiving object TRTM_SEC to archive securities class data.|TRTM_SEC|TRTM_SEC|END_DATE is the latest last change date of the securities class group.|A single security class must fulfill the following requirements in order for it to be archived: The security class must have the status Obsolete. No financial transaction refers to the security class. No treasury position refers to the security class. Security classes are generally not archived individually, instead, they are archived in security class groups (the term 'security class group’ is only used in the context of this archiving object). This must be done because multiple security classes can be so closely related that|Arc Se Da TR |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
| | | | |deleting only a few of them would result in database inconsistencies. Either all of the security classes in a group are deleted or none. The security class groups are generated by the following rules: If two security classes refer to the same executable right, they are in the same group. Dependend on the different kinds of executable rights, different tables needs to be checked. If two security classes share a common entry in the database table VWPANAN, they must lie in the same group. This is the case for subscription rights (product category 030) and their accociated stocks (product category 010). For the other executable rights the tables TERTVWERKO and TERTVWERPO are checked. If two security classes refer to the same asset pool, they are in the same group. Asset pools are only relevant for certain| |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
| | | | |securities of product category 042 (such as ABS/MBS). Example The security classes SC1, SC2, SC3 and SC4 exist. SC1 and SC2 are related because they refer to the executable right ER1. SC2 and SC3 are related because they refer to the same asset pool. SC3 and SC4 are related because they refer to the executable right ER2. We can then conclude that SC1, SC2, SC3 and SC4 all belong to the same security class group. A security class group is considered archivable if and only if the following conditions are met: Each individual security class in the group is archivable in the sense described above (such as, status Obsolete, no transaction, no position. The security class group is complete, if there is no security class in the system that is related to one (and hence all) of the security classes in the group but which is not contained in the group. **Note:** The full security class group might be bigger than that.| |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
|Datafeed Usage Log|DATAFDLOG| | | |Da Arc Us DA |
|Limits and Limit Utilizations The TRTM_LM archiving object is used to archive and delete limits and limit utilizations. When you use Limit Management, this leads over time to very large volumes of data being saved. To ensure that evaluations are not slowed down by excessively large volumes of data, you can delete limits and utilizations from the system. However, before you can delete this data from the system, you first need to have archived it in a previous step.|TRTM_LM|TRTM_LM|Start Date of Retention Period, which is the Valid-To Date of a limit.|The limits and limit utilizations have expired or reached their end date.|Arc an Ut TR |
|RDB Risk Analyzer Single Records You use the archiving object RDBRA_REC to archive single records that are stored in the results database of the Market Risk Analyzer (FINFSCM-TRM-MR).|RDBRA_REC|RDBRA_REC|Document Date|Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.|Arc Re wit RD |
|RDB Risk Analyzer Final Results You use the RDBRA_FRP archiving object to archive final results that are stored in the results database (RDB) of the Market Risk Analyzer (FIN-FSCMTRM-MR).|RDBRA_FRP|RDBRA_FRP|Document Date|Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.|Arc Re wit RD |
|RDB Accounting Analyzer Single Records You use the archiving object RDBAA_REC to archive single records that are stored in the results database of the|RDBAA_REC| | |Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.|Arc Re wit RD |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
|Accounting Analyzer (FIN-FSCM-TRM-AA).| | | | | |
|RDB Accounting Analyzer Final Results You use the archiving object RDBAA_FRP to archive final results that are stored in the results database (RDB) of the Accounting Analyzer (FIN-FSCM-TRM-AA).|RDBAA_FRP| | |Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.|Arc Re wit RD |
|RDB Portfolio Analyzer Single Records You use the archiving object RDBPA_REC to archive single records that are stored in the results database of the Portfolio Analyzer (FIN-FSCMTRM-PA).|RDBPA_REC| | |Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.|Arc Re wit RD |
|RDB Portfolio Analyzer Final Results You use the archiving object RDBPA_FRP to archive final results that are stored in the results database (RDB) of the Portfolio Analyzer (FINFSCM-TRM-PA).|RDBPA_FRP| | |Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.|Arc Re wit RD |
|Saved Datasets You can use archiving object RM_SVSTATE to archive saved datasets used for backtesting.|RM_SVSTATE|RM_SVSTATE| |The Selection Date of the saved dataset has passed.|Arc Sa wit RM |
|Collateral Transactions You can use archiving object JB_COLL to archive collateral transactions.|JB_COLL|JB_COLL|Valid To Date|End of Validity of collateral provision has passed.|Arc Co Tra wit |
|Gap Evaluations You can use the archiving object JB_GPAN to archive Gap evaluation transactions.|JB_GPAN|JB_GPAN|Valid To Date|ALM Horizon Date has passed.|Arc Eva JB |


|Data to Be Archived|Archiving Object|ILM Object|Time Reference|Authorization Object Specific Prerequisites|Se|
|---|---|---|---|---|---|
|Generic Transaction Versions The JB_GTVS archiving object is used to archive the versions of generic transactions.|JB_GTVS|JB_GTVS|Start Date of Retention Period|End of Term/End of Period of Notice has passed.|Arc Ge Tra Ve JB |
|Generic Transactions You can use archiving object JB_GETR to archive generic transactions.|JB_GETR|JB_GETR|Start Date of Retention Period|End of Term/End of Period of Notice has passed. Versions of the generic transactions are already archived/deleted (JB_GTVS)|Arc Ge Tra wit |


For more information about archiving for Commodity Risk Management, see also Archiving Data in Commodity Risk Management

For more information about archiving the SAP business partner that is also used in TRM (archiving object CA_BUPA), see the documentation for SAP Business Partner and Archiving and Deleting Business Partner Data.

##### Archiving Financial Transactions with TRTM_FTR

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Financial Transactions with TRTM_FTR | L4 | trm11 p.79 | loio `4ea2a1835a2f4f58e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2a1835a2f4f58e10000000a42189e.html?locale=en-US)

**Context**

The TRTM_FTR archiving object is used to archive and delete financial transactions of the Transaction Manager as well as related subentities (such as the related correspondence objects, trade repository objects or the external trade ID).

**Prerequisites**

The following prerequisites must be fulfilled before a financial transaction can be archived:

The financial transaction must have been settled if the processing type requires settlement.

The flows of the financial transaction relevant for posting have been posted completely.

The financial transaction has acquired the required confirmation status (such as Confirmed or Counterconfirmed).

This archiving object also archives the corresponding trade repository objects of the financial transactions.

It is only possible to archive trade repository objects that have acquired one of the following statuses:

- 06 Rejection Accepted

- 07 Accepted

- 08 Obsolete

- 09 Reconciled

- 10 Reconciliation Failed


20 Invalid

If not all TAROs meet these criteria, the financial transaction cannot be archived.

**Note:**

These checks are not relevant for financial transactions in the following statuses:

Reversed

Old Transaction

These checks are not relevant for financial transactions in the following activities:

Offer

Simulation

These financial transactions (reversed financial transactions, old financial transactions, offers and simulations) are archived without the above mentioned checks. They only must reach their end of term and fulfill the residence rule.

**Tables**

The archiving object archives data from several tables. To check which tables these are, call up transaction SARA, enter the archiving object, and choose Database Tables. You can display the relevant tables in the lower part of the screen.

**Archiving Classes**

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

**Dependencies**

From the business point of view, the archiving object Positions TRTM_TPM is closely related to the archiving object Financial Transaction TRTM_FTR. If you have archived financial transactions, you can then archive the related positions as well.

For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA. For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA under Goto

Network Graphic .

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for TRTM_FTR are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Bases

End Date, which is the end of the term of the financial transaction.

Available Condition Fields

Company Code COMPANY_CODE

Product Type PRODUCT_TYPE

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Performing Application-Specific Configuration**

If you do not use the ILM policies, you must use the Customizing activities available in the Customizing under Treasury and Risk Management Transaction Manager General Settings Tools Archiving of Financial Transactions and Positions to define the residence rules.

The Positions (TRTM_TPM) archiving object shares the residence time with the TRTM_FTR Financial Transaction archiving object. This is because the same archiving criteria need to apply to the positions as those that apply to the related financial transactions.

**Programs**

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

**Defining Write Variants**

On the basis of your selection entries, the write program selects the financial transactions for archiving and the system checks whether the individual financials can be archived.

**Note:**

You can execute the write program in one of the following modes:

Archiving

If you select this option, of the selected data, only that data for which a successful archivability check has been performed is stored in archived files.

The archive files created with this option can be stored on external storage systems.

Using the delete program, it is possible to delete from the database the data that was transferred to the archive files. Archive information structures are generated.

The Archiving mode is used to remove data from closed business transactions from the database in order to reduce its load.

Snapshot

If you select this option, the selected data is copied to the archive files without undergoing an additional check. The files created with this option can be stored on an external storage system.

It is not possible to delete from the database the data transferred to the archive files.

Snapshots are taken to obtain a complete data record in the archive for use in Retention Warehouse.

Data Destruction

If you select this option, the system only stores in the archive files the data that can be destroyed according to the rules defined in ILM. The archive files created with this option cannot be stored on external storage systems.

Using a delete program, it is possible to delete from the database the data transferred to the archive files. No archive information structures are generated.

After deleting the data from the database, the delete program also deletes the generated archive files as well as the file-based administration information.

You use data destruction to permanently delete data that is no longer needed from the database.

You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages.

Once the test run has proved successful, you can start the write program in production mode.

**Defining Reloading Variants**

You should only use this program in cases when an error has occurred during archiving. Furthermore, we recommend that you perform the reload as soon as possible after the erroneous archiving run was performed.

**Note:**

When you run this program, the system updates the entries in the active archive information structures.

See also:Reloading the Archive

**Authorizations for TRTM_FTR**

You need the following authorization objects:

|Activiy|Required Authorization Object|
|---|---|
|S_ARCHIVE|The write program checks the authorization for archiving object TRTM_FTR and activity 01 (Create or Generate).|


**Displaying Treasury Positions Archived with TRTM_FTR**

We recommend that you activate the delivered archive information structures SAP_TRTM_FTR before the first archiving run. This simplifies reading archived positions later with the read program (improved performance) and enables you to use the Archive Information System (transaction SARI) to read archived positions.

SAP delivers the field catalog SAP_TRTM_FTR and the archive information structure SAP_TRTM_FTR which contains the fields Company Code and Financial Transaction Number.

###### Reloading the Archive

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Financial Transactions with TRTM_FTR > Reloading the Archive | L5 | trm11 p.82 | loio `a3ab952126174a91826ce9ae30233545` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a3ab952126174a91826ce9ae30233545.html?locale=en-US)

Context

**Caution:**

The reload function is intended as an emergency option only to be resorted to in cases when an error in the Customizing settings or in document selection has caused the wrong data to be archived. Documents are therefore only reloaded directly

after data has been archived incorrectly. Reloading documents at a subsequent point in time could in some cases lead to inconsistencies in the database.

You are on the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object is entered in the Object Name field.

Archive administration can access the archive files to be reloaded.

**Note:**

Only complete archiving runs can be reloaded. In other words, all archive files of a selected archiving run are reloaded together. These archive files are then marked as reloaded.

**Procedure**

- 1. Choose Goto Reload . A screen appears on which you can schedule the reload to be run in the background.
- 2. Choose Archive Selection. A dialog box displays archiving runs that have already been processed by the deletion program.
- 3. Select the relevant archiving run and choose Continue. You return to the previous screen.
- 4. Enter the start date and the spool parameters.


**Results**

Now you have entered all of the data required for the background job. To run the job, choose Execute.

##### Archiving Correspondence Objects with TRTM_CO

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Correspondence Objects with TRTM_CO | L4 | trm11 p.83 | loio `3cf64dd7beab429fb0009f5af0654b45` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3cf64dd7beab429fb0009f5af0654b45.html?locale=en-US)

**Use**

You need archiving object TRTM_CO to archive correspondence objects that have been created outside of financial transactions or if you want to archive correspondence objects independently of the financial transaction. As part of the archiving of financial transactions, correspondence objects relating to financial transactions are archived using TRTM_FTR.

**Prerequisites**

The status of the correspondence object is Completed.

**Tables**

The archiving object archives data from several tables. To check which tables these are, call up transaction SARA, enter the archiving object, and choose Database Tables. You can display the relevant tables in the lower part of the screen.

**Archiving Classes**

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

**Programs**

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

**Dependencies**

From the business point of view, the archiving object Positions TRTM_TPM is closely related to the archiving object Financial Transaction TRTM_FTR. If you have archived financial transactions, you can then archive the related positions as well.

For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA. For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA under Goto

Network Graphic .

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the TRTM_CO ILM object as part of SAP Information Lifecycle Management.

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for TRTM_CO are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Bases

Start Date of Retention Period is for outgoing correspondence objects the delivery date and for incoming correspondence objects it is the receiving date.

Available Condition Fields

Company Code COMPANY_CODE

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

##### Archiving Trade Repository Objects with TRTM_TARO

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Trade Repository Objects with TRTM_TARO | L4 | trm11 p.84 | loio `768d57530588e647e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/768d57530588e647e10000000a441470.html?locale=en-US)

**Use**

You use this archiving object to archive trade repository objects (TAROs) in the Transaction Manager (TRM). This archiving object is used to archive the following groups of trade repository objects:

Trade repository objects for financial transactions in Transaction Manager with the action type 30 Valuation and 35 Security

Trade repository objects for external transactions

**Prerequisites**

It is only possible to archive trade repository objects that have acquired one of the following statuses:

- 06 Rejection Accepted

- 07 Accepted

- 08 Obsolete

- 09 Reconciled

- 10 Reconciliation Failed


20 Invalid

**Dependencies of Archiving Object TRTM_TARO**

Relationship to Archiving Object TRTM_FTR

Trade repository objects for financial transactions of Transaction Manager are generally archived together with financial transactions with the archiving object (TRTM_FTR). However, from this set of trade repository objects, you can archive just those with the action types 30 Valuation and 35 Security, using the archiving object TRTM_TARO independently of the financial transaction.

**ILM- Related Information**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for TRTM_TARO are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Last Changed On

Available Condition Fields

Trade Repository (TREP)

Country/Region Key (BS_COUNTRY_OF BUKRS)

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Programs**

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

|Program|Function|
|---|---|
|R_TLR_TARO_ARCHIVE_WRITE|Write|
|R_TLR_TARO_ARCHIVE_DELETE|Delete|


|Program|Function|
|---|---|
|R_TLR_TARO_ARCHIVE_RELOAD|Reload|


**Archiving Classes**

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

**Tables**

The archiving object archives data from several tables. To check which tables these are, call up transaction SARA, enter the archiving object, and choose Database Tables. You can display the relevant tables in the lower part of the screen.

**Authorization**

The system checks authorization object S_ARCHIVE for all activities.

##### Archiving Positions with TRTM_TPM

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Positions with TRTM_TPM | L4 | trm11 p.86 | loio `12fa4a36420d4d19ae12fefad2f2dd9e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/12fa4a36420d4d19ae12fefad2f2dd9e.html?locale=en-US)

You use this archiving object to archive Treasury positions.

**Context**

Treasury and Risk Management manages Treasury positions (for more information, see also positions) for a broad range of financial instruments. Consequently, the criteria for archiving vary depending on the type of financial instrument. The following kinds of Treasury positions can be archived:

OTC positions

(such as money market positions, FX positions, and trade finance positions)

Loan positions

Securities positions

Listed derivative positions

Positions are not archived individually; instead, they are archived in position groups. Position groups are only used in the context of archiving. A position group is used to group together positions that are so closely related that they cannot be handled separately in archiving.

All positions of a position group have the same company code.

In addition:

Securities positions or listed derivative positions that have the same ID number belong to the same position group.

OTC positions and loans that have the same financial transaction number or loan number belong to the same position group.

**Note:**

The valuation area, therefore, is not used as a criteria for differentiating position groups.

All positions that belong to a business transaction that generates flows for different positions belong to the same position group. This can arise in connection with hedging relationships, securities account transfers, or corporate actions, for example.

A position group is archived once all of the positions in that position group can be archived.

**Example:**

All positions of a convertible bond 123 and of the related share 456 in all valuation areas in company code 001 are grouped together into one position group.

All positions for OTC transaction 65438 in all valuation areas in company code 001 are grouped together into one position group.

**Prerequisites**

Criteria Dictating Whether Positions Can Be Archived

All flows for a position must have the status Fixed or Reversed.

Exception: Open and close flows for OTC transactions

Each business transaction must have U (Updated) status.

The Units or Nominals position components must be zero at the start of the retention period.

There must not be any business transactions scheduled after the start of the retention period for the position.

The maturity of a position must fall before the start of the retention period. (Note that the latest date of a position is considered the due date.)

If a position forms part of an intragroup transaction, it cannot be archived. For such a position to be archived, the intragroup status of the position must be initial.

The position must not form part of a hedging relationship in Hedge Accounting for Positions.

If a money market position or a loan is used as a hedged item in a hedging relationship in Hedge Accounting, it cannot be archived.

If a foreign exchange transaction or a derivative is used as a hedging instrument in Hedge Accounting, it cannot be archived.

The corresponding fnancial transactions must already be archived.

The corresponding loans contract must already be archived.

**Tables**

The archiving object archives data from several tables. To check which tables these are, call up transaction SARA, enter the archiving object, and choose Database Tables. You can display the relevant tables in the lower part of the screen.

Archiving Classes

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

**Programs**

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

**Dependencies**

From the business point of view, the archiving object Positions (TRTM_TPM) is closely related to the archiving object Financial Transaction (TRTM_FTR). If you have archived financial transactions, you can then archive the related positions as well.

**Recommendation:**

If you use Loans Management (FS-CML) and, alongside loans, you also manage positions for parallel valuation areas in Position Management, we recommend that, after you have archived loan contracts using archiving object CMLCONTRCT, you also archive the relevant positions using archiving object TRTM_TPM.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the TRTM_TPM ILM object as part of SAP Information Lifecycle Management.

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for TRTM_TPM are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Bases

COMPLETION_DATE, which is the end of term of the position group with time offset END_OF_YEAR. This completion date of the position group is reached at the zero position date of the position group, that is, the date from which all items in the item group are zero.

Available Condition Fields

Company code COMPANY_CODE

Product type PRODUCT_TYPE

Country/region of company code BS_COUNTRY_OF_BUKRS

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Performing Application-Specific Configuration**

If you do not use the ILM, you must use the Customizing activities available in the Customizing under Treasury and Risk Management Transaction Manager General Settings Tools Archiving of Financial Transactions and Positions to define the residence rules.

The Positions (TRTM_TPM) archiving object shares the residence time with the Financial Transaction (TRTM_FTR) archiving object. This is because the same archiving criteria need to apply to the positions as those that apply to the related financial transactions.

**Defining Write Variants**

On the basis of your entries, the write program selects the positions for archiving and creates the position groups. In the case of complete position groups, the system checks whether the individual positions can be archived. If all positions of a position group can be archived, the system archives that position group.

**Note:**

You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages.

Once the test run has proved successful, you can start the write program in production mode.

See also:

Creating Variants for Write Program for TRTM_TPM

Checks on Archiving Object TRTM_TPM

**Defining Read Program Variants**

See also: Displaying Archived Positions with TRTM_TPM

**Caution:**

The read program for archiving object TRTM_TPM displays all table entries for the archived position groups. However, it is difficult to interpret the business significance of this data. Before you start archiving, we recommend that you first ensure that you have met all legal prerequisites. Only when you no longer need to be able to present data can you archive that data.

**Defining Reloading Variants**

You should only use this program in cases when an error has occurred during archiving. Furthermore, we recommend that you perform the reload as soon as possible after the erroneous archiving run was performed.

**Note:**

When you run this program, the system updates the entries in the active archive information structures.

See also: Reloading the Archive

**Authorizations for TRTM_TPM**

You need the following authorization objects:

|Activiy|Required Authorization Object|
|---|---|
|S_ARCHIVE|The write program checks the authorization for archiving object TRTM_TPM and activity 01 (Create or Generate).|
|T_POSS_ASS|The system checks the authorization for the company code, the valuation area, and the product type for the authorization function P3 (Position Subledger) and the activity 03 (Display).|


**Displaying Treasury Positions Archived with TRTM_TPM**

We recommend that you activate the delivered archive information structures SAP_TRTM_TPM_0 and SAP_TRTM_TPM_1 before the first archiving run. This simplifies reading archived positions later with the read program (improved performance) and enables you to use the Archive Information System (transaction SARI) to read archived positions.

SAP delivers the field catalog SAP_TRTM_TPM and the archive information structures SAP_TRTM_TPM_0 and SAP_TRTM_TPM_1.

|Field Catalog SAP_TRTM_TPM|Archive Information Structure SAP_TRTM_TPM_0|Archive Information Structure SAP_TRTM_TPM_1|
|---|---|---|
|Company Code (Key Field)|X|X|
|Product Type (Key Field)|X|X|
|ID Number (Key Field)|X|X|
|Loan Number (Key Field)|X|X|
|Financial Transaction Number (Key Field)|X|X|
|Securities Account|X|No selection parameter|
|Futures Account|X|No selection parameter|
|Portfolio|X|No selection parameter|
|Trader|No selection parameter|No selection parameter|


**Archiving Process**

- 1. Creating Archive Files


- a. You are in the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object TRTM_TPM is entered in the Archiving Object field.
- b. Choose Write.


A screen appears on which you can schedule the write program to be run in the background.

If archiving has already been performed for an archiving object and there are still archive files from that archiving run that have not yet been processed by the relevant deletion program, the system informs you of this in a separate window.

The same applies for interrupted archiving runs.

**Caution:**

Archiving data more than once can lead to various problems. Hence some archiving objects require that data is not replicated in the archive, because this can lead to incorrect results (such as using archived data to produce totals). Ensure the following:

The new write job that needs to be scheduled does not select the same data that is contained in archive files that have not yet been processed by the deletion program.

No variants with overlapping selection values are used in parallel.

**Note:**

If the variant that you have selected is already being used in other jobs, you can choose the Jobs with Selected Variant pushbutton to display the variant and delete it if necessary.

- c. Use the input help to select a variant. If no variant is available, choose Maintain and create the variant that you require. See also: Creating Variants for Write Program for TRTM_TPM

- d. Enter the start date and the spool parameters.


**Note:**

With the Archive Directory pushbutton, you can determine how much storage space is free in the current objectspecific archive directory before you start to archive.

Now you have entered all of the data required for the background job. To run the job, choose Execute.

**Note:**

After all archive files of a run have been written completely, the system event SAP_ARCHIVING_WRITE_FINISHED is triggered by the ADK. In reaction to this event, processes that occur downstream from archiving (such as automated file storage) can be triggered by external tools.

Furthermore, you can navigate to the following menu options:

Customizing

Job Overview: Here you find an overview of all archiving jobs as well as functions for processing them.

Administration

DB Tables

Information System

**Note:**

You can display the logs documenting processing by choosing Logs from the Archive Administration initial screen.

See also: Checks on Archiving Object TRTM_TPM

- 2. Deleting Archived Data from the Database
- 3. You can display the archived data as follows:


In Archive Administration (transaction SARA), you can call up the read program RTPMARCHIVE_READ_BY_INDEX.

See also: Displaying Archived Positions with TRTM_TPM

In the Archive Administration System (transaction SARI), you can display the data archived when you have activated archive information structures for the archiving object.

- 4. In exceptional cases when archiving runs contain errors, you can use the Reload function to reload the archive. For more information, see Reloading the Archive.

###### Creating Variants for Write Program for TRTM_TPM

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Positions with TRTM_TPM > Creating Variants for Write Program for TRTM_TPM | L5 | trm11 p.92 | loio `9af69c1f5e014fb0ac34b68de0092c23` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9af69c1f5e014fb0ac34b68de0092c23.html?locale=en-US)

**Context**

If you want to run the write program for archiving object "TRTM_TPM Positions", you need to create a variant.

In the variant, you use selection criteria to specify which positions are archived and how the write program is executed.

**Procedure**

- 1. Select the product groups. Depending on the product groups that you have selected, selection criteria for the relevant positions appear in the lower frame.
- 2. Enter the company codes.
- 3. You can use the product type to restrict the positions.
- 4. You can also restrict the selection using the product group.

Securities Positions: Security ID

Loan Positions: Loan Number

Listed Derivatives: ID Number

OTC Positions: Financial Transaction Number

- 5. Enter the retention period end date. The system uses this date to check the minimum retention period.
- 6. You can use the following indicators:


Check Maturity Date of Securities

When this indicator is set (= default setting), the write program checks the maturity date of a security. When the maturity date falls after the start date of the retention period, it is not possible to archive the position.

Exception: If a security does not have a maturity date, the system does not perform the check. Example: Stocks do not have a maturity date. Consequently, the system does not run a maturity date check on stock positions.

If you do not set this indicator, the system does not check the maturity date, enabling you to archive positions before the maturity date. This can be useful in the case of securities that have a very long term.

See also:Checks on Archiving Object TRTM_TPM

Include Interlinked Positions

When you start the write program for archiving, you define the selection criteria for the positions to be archived. The write program finds all selected positions and creates position groups.

There are two types of position group:

Complete position groups

Position groups for which the related positions have all been selected for archiving by the selection criteria.

Incomplete position groups

Position groups that, in order to become complete, must first be supplemented by positions that were not selected for archiving by the selection criteria.

The archiving run also considers complete position groups.

The following applies in the case of incomplete position groups:

When the indicator is set (= default setting), the system adds the missing positions to the incomplete position groups and then includes the now complete position group in the archiving run.

If this indicator is not set, incomplete position groups are not included in the archiving run.

Display All Errors

When this indicator is not set (= default setting), the system runs checks on whether a position can be archived until the first error occurs. For performance reasons, subsequent checks are not performed. Only one error message appears in the detailed log. Consequently, only one line per position is displayed in the archiving log.

If you set this indicator, the system performs all checks for a position and outputs all error messages in the detailed log. In this case, there can be multiple lines per position in the detailed log. However, such a comprehensive list makes it easier to analyze archiving problems. You can only set this indicator in the test mode of the write program for archiving positions.

- 7. In the Processing Options, you can specify whether the program is executed in the test mode or production mode.

Test Mode

In the test mode, the system only simulates the program run. No archive files are written and no data is deleted from the database.

Production Mode

In this mode, the system checks whether the selected positions can be archived and then writes archive files for all position groups that can be archived. However, the system does not delete the data from the database. For this, you need to start the deletion program.

- 8. Detailed Log

You can use this field to specify whether a detailed log (using the "Complete" option) is output in addition to the summarized log when the program is executed.

The summarized log contains each message just once. The message is accompanied by the number of objects affected and by one of these objects as an example.

The detailed log contains all objects processed, including the related messages. If you select Without Success Message, no success messages are written in the detailed log.

If you have set the Include Interlinked Positions indicator, all positions are listed in the detailed log and their differentiation criteria, such as company code and valuation area, are also displayed. Positions belonging to a position group are separated by a line of asterisks.

- 9. Log Output


**Note:**

We recommend that you only output a detailed log when a small number of objects are processed, such as in the test mode. Otherwise, the program may terminate due to memory overflow.

Here, you can specify whether the log is output in the list (or in the spool when the program is run in the background), in the application log, or in both locations.

An advantage of outputting the log in the application log is that the log messages are displayed during program runtime. (Whereas log messages are generally output every 30 minutes with programs run in the background, they are output every

- 10 seconds when programs are run online.) Logs that are written to the list cannot be viewed until the program has finished.


With the list output, you can opt for automatic storage of the log in a connected storage system (see Spool Parameters in job scheduling). Logs written to the application log can only be stored manually from the log display. Furthermore, logs written to the list are removed automatically when the related background job is deleted, whereas logs written to the application log have to be deleted manually.

**Note:**

If you have opted for List for the log output, you can double-click a position to display the related position indicator.

All logs can be displayed from the archive administration by choosing Goto Logs . For more information, see Logs.

10. You can attach a comment to archiving runs. Comments appear as follows:

In the overview of the archiving runs in archive administration (transaction SARA). You can make changes to comments here.

In the manual selection of archive files (such as for analysis programs). The comments are intended to assist you in selecting the archive files.

###### Checks on Archiving Object TRTM_TPM

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Positions with TRTM_TPM > Checks on Archiving Object TRTM_TPM | L5 | trm11 p.94 | loio `ab0e8254118d45259cc5ac7b3783aaf9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ab0e8254118d45259cc5ac7b3783aaf9.html?locale=en-US)

After the system has selected the positions using the selection criteria for the write program variant, the system runs the following checks for the single positions of the entire position groups to be archived and thereby determines the position groups to be archived.

The checks are performed independently of the financial transaction data.

If an archiving criterion is not met by a position within a position group, the position group is not archived. For reasons of performance, subsequent checks in the production mode are canceled.

Criteria Dictating Whether Positions Can Be Archived

All flows for a position must have the status Fixed or Reversed.

Exception: Open and close flows for OTC transactions

Each business transaction must have U (Updated) status.

The position components Units/Nominals must be zero at the start of the retention period.

There must not be any business transactions scheduled after the start of the retention period for the position.

The maturity of a position must fall before the start of the retention period. (Note that the latest date of a position is considered the due date.)

If a position forms part of an intragroup transaction, it cannot be archived. For such a position to be archived, the intragroup status of the position must be initial.

The position must not form part of a hedging relationship in Hedge Accounting.

If a foreign exchange transaction or a derivative is used as a hedging instrument in Hedge Accounting, it cannot be archived.

###### Displaying Archived Positions with TRTM_TPM

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Positions with TRTM_TPM > Displaying Archived Positions with TRTM_TPM | L5 | trm11 p.94 | loio `60b9e7659d0645d785dc7a8d1d9d7b22` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/60b9e7659d0645d785dc7a8d1d9d7b22.html?locale=en-US)

**Prerequisites**

Positions must already have been archived.

We recommend that you activate the delivered Archive Information Structures SAP_TRTM_TPM_0 and SAP_TRTM_TPM_1 before the first archiving run. This simplifies reading archived positions later with the read program (improved performance) and enables you to use the Archive Information System (transaction SARI) to read archived positions.

See also:Activating and Deactivating the Information Structure

SAP delivers the field catalog SAP_TRTM_TPM and the archive information structures SAP_TRTM_TPM_0 and SAP_TRTM_TPM_1.

|Field Catalog SAP_TRTM_TPM|Archive Information Structure SAP_TRTM_TPM_0|Archive Information Structure SAP_TRTM_TPM_1|
|---|---|---|
|Company Code (Key Field)|X|X|
|Product Type (Key Field)|X|X|
|ID Number (Key Field)|X|X|
|Loan Number (Key Field)|X|X|
|Financial Transaction Number (Key Field)|X|X|
|Securities Account|X|No selection parameter|
|Futures Account|X|No selection parameter|
|Portfolio|X|No selection parameter|
|Trader|No selection parameter|No selection parameter|


**Context**

You use the read program RTPMARCHIVE_READ_BY_INDEX to display archived data.

**Caution:**

The read program displays all table entries for the archived position groups. However, it is difficult to interpret the business significance of this data. Before you start archiving, we recommend that you first ensure that you have met all legal prerequisites. Only when you no longer need to be able to present data can you archive that data.

See also:Data Access and Verifiability of Digital Documentation

**Procedure**

- 1. You are on the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object TRTM_TPM is entered in the Object Name field.
- 2. Choose Read.

The Archive Administration: Start Read Program screen appears. The Batch/Online field is preset with "Online". Choose Execute.

- 3. You can use the following selection criteria to search for archived positions:


Choose a product group in the Product Group field (securities, listed derivatives, loans, or OTC transactions).

Enter the company code.

Select the product type.

Depending on the product group that you choose, you can also restrict the search by specifying the ID number, loan number, or financial transaction number.

- 4. In the Technical Settings area, you can set the Activate Archive File Selection indicator.

If you have not activated any archive information structures prior to performing archiving, you need to set this indicator. The system searches for the archived positions in the archive files.

If you have activated archive information structures before performing archiving, you do not need to set this indicator, and the system then uses the archive information structures to search for the archived positions.

- 5. If you have set the Activate Archive File Selection indicator, the Archive Administration: Select Files for Read Program dialog box appears. For more information, see Archive Selection. Select the archive files that you want to read or analyze and then confirm your selection by choosing Continue.

- 6. The system outputs a summarized list of the position groups corresponding to the selection criteria. When you double-click one of these position groups, the Archiving TRM-TM Positions: Read Program dialog box appears.


On the left of the screen, you see a navigation window displaying all of the tables from which entries for the selected position group have been archived, as well as how many entries for each table were archived. When you double-click a table in the navigation window on the left, the system displays on the right a list (in the form of a SAP List Viewer list) of the archived entries for that table that relate to the selected position group.

**Next Steps**

Reading Archive Files

##### Archiving Security Class Data with TRTM_SEC

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Security Class Data with TRTM_SEC | L4 | trm11 p.96 | loio `8c599076290d4a9790ac9490df34791d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8c599076290d4a9790ac9490df34791d.html?locale=en-US)

You can use archiving object TRTM_SEC to archive securities class data.

Tables

TRTM_SEC archives data from several tables. To check which tables these are, call up transaction SARA, enter the archiving object, and choose Database Tables. You can display the relevant tables in the lower part of the screen.

Archiving Classes

TRTM_SEC may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Programs

To find out which programs this archiving object offers, call up transaction SARA enter the archiving object and press ENTER.

**Prerequisites**

The following prerequisites must be fulfilled before securities class data can be archived:

A single security class must fulfill the following requirements in order for it to be archived:

The security class must have the status Obsolete.

No financial transaction refers to the security class.

No treasury position refers to the security class.

Security classes are generally not archived individually, instead, they are archived in security class groups (the term 'security class group’ is only used in the context of this archiving object). This must be done because multiple security classes can be so closely related that deleting only a few of them would result in database inconsistencies. Either all of the security classes in a group are deleted or none. The security class groups are generated by the following rules:

If two security classes refer to the same executable right, they are in the same group.

Dependend on the different kinds of executable rights, different tables needs to be checked.

If two security classes share a common entry in the database table VWPANAN, they must lie in the same group. This is the case for subscription rights (product category 030) and their accociated stocks (product category 010).

For the other executable rights the tables TERTVWERKO and TERTVWERPO are checked.

If two security classes refer to the same asset pool, they are in the same group. Asset pools are only relevant for certain securities of product category 042 (such as ABS/MBS).

Example

The security classes SC1, SC2, SC3 and SC4 exist.

- SC1 and SC2 are related because they refer to the executable right ER1.

- SC2 and SC3 are related because they refer to the same asset pool.

- SC3 and SC4 are related because they refer to the executable right ER2.


We can then conclude that SC1, SC2, SC3 and SC4 all belong to the same security class group.

**Note:**

The full security class group might be bigger than that.

A security class group is considered archivable if and only if the following conditions are met:

Each individual security class in the group is archivable in the sense described above (such as, status Obsolete, no transaction, no position.

The security class group is complete, if there is no security class in the system that is related to one (and hence all) of the security classes in the group but which is not contained in the group.

**ILM-Related Information for the Archiving Object**

You can use this archiving object with the TRTM_SEC ILM object as part of SAP Information Lifecycle Management. In transaction

IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following condition fields are available:

Product Type

The following time references are available:

END_DATE is the latest last change date of the securities class group.

For more information, see SAP Information Lifecycle Management.

**Defining Write Variants**

When you schedule the archiving run, you must enter an existing variant or create a new one. You can do so in transaction SARA.

A write variant contains the parameters for the securities class data that you want to archive.

SAP delivers the following parameters:

SecurityClass ID No.

Product Category

Product Type

Issuer

**Authorizations for TRTM_SEC**

You need the following authorization objects:

|Activity|Required Authorization Object|
|---|---|
|All activities|S_ARCHIVE|


**Displaying Securities Classes Archived with TRTM_SEC**

Infostructure SAP_TRTM_SEC and field catalog SAP_TRTM_SEC of the archive information system exist

##### Archiving Payment Requests with FI_PAYRQ

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Payment Requests with FI_PAYRQ | L4 | trm11 p.98 | loio `4ea2a1b35a2f4f58e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2a1b35a2f4f58e10000000a42189e.html?locale=en-US)

Payment requests are archived, deleted, and reloaded using archiving object FI_PAYRQ.

See also:

Generating Archive Files – Payment Requests

Reloading Archives

###### Generating Archive Files – Payment Requests (2 of 2)

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Payment Requests with FI_PAYRQ > Generating Archive Files – Payment Requests | L5 | trm11 p.98 | loio `9e589437663f4d1c8fb9d098eb9c082d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9e589437663f4d1c8fb9d098eb9c082d.html?locale=en-US)

**Prerequisites**

You can only archive payment requests that have been cleared.

**Procedure**

- 1. Choose Accounting Treasury and Risk Management Transaction Manager Utilities Archiving Payment Requests .

The Archive Administration: Create Archive Files screen appears.

- 2. Enter a variant name and choose Maintain.
- 3. Maintain your variants by entering the following selection criteria for the documents you want to have checked for archiving:

Company codes

The system only archives payment requests posted in the specified company codes.

Key numbers

The system only archives payment requests the lie within the interval.

Customer items

The system archives payment requests for customers.

Supplier items

The system archives payment requests for suppliers.

G/L account items

The system archives payment requests for G/L accounts.

Archiving period

The system only archives payment requests that have been in the system for longer than the specified archiving period.

- 4. Enter your selection criteria. To simulate the run, set the Test run indicator.
- 5. Choose Back.
- 6. The system asks you if you want to save the values you entered. Confirm your entries by choosing Yes.
- 7. The Save Attributes of Variant screen appears. Enter a description of your variant in the Description field.
- 8. Save your variant. Choose Back to return to the request screen for archive administration.
- 9. Maintain the start date and the spool parameters for the archiving run.
- 10. Once you have maintained the selection criteria, the start date, and the spool parameters, choose Execute.


To display an overview of the jobs you have generated, choose Goto Job Overview .

For more information on maintaining variants, see the SAP Library under SAP NetWeaver Solution Life Cycle Management Data Archiving (CA-ARC) Introduction to Data Archiving (CA-ARC) .

If all the archiving conditions are fulfilled, the system writes the archived documents to external archive files.

The system then starts a deletion program for each archive file, which imports the data to be deleted from the archive file and deletes it from the database.

##### Archiving Effectiveness Tests with TRTM_HMLOG

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Effectiveness Tests with TRTM_HMLOG | L4 | trm11 p.100 | loio `4ea2a1515a2f4f58e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2a1515a2f4f58e10000000a42189e.html?locale=en-US)

**Definition**

Archiving object TRTM_HMLOG with which to archive logs for effectiveness tests

**Use**

The system saves the effectiveness test logs in tables THAHRT_MEAS_LOG (detailed log for an effectiveness measurement) and THAHRT_ASSES_LOG (detailed log for an effectiveness assessment). To archive the logs, choose SAP Easy Access Treasury and Risk Management Transaction Manager Utilities Archiving Effectiveness Tests (FTR_HMLOG_ARCH_W). Alternatively, you can use transaction SARA to call the archiving object TRTM_HMLOG.

Before you use the archiving object for the first time, you need to specify that the detail logs for valuations are saved in the database. You do this in the Implementation Guide under Transaction Manager Hedge Management Effectiveness Check Define Calculation Types .

To make further settings for the archiving object, use transaction AOBJ.

**Structure**

Archiving Programs for the Archiving Object TRTM_HMLOG:

|Program|Function|Description|
|---|---|---|
|RFTRARCHIVE_HEDGELOG_W|Write|You use this function to save the detail logs in the archive. The data in the system database is not deleted.|
|RFTRARCHIVE_HEDGELOG_D|Delete|You use this function to delete the detail logs in the database. With the standard settings, the delete program is started automatically after archiving. We recommend that you keep this setting.|
|RTHMHR_EFFECTIVENESS_TEST|Read|You can use this function to display archived logs. Alternatively, you can call the following transactions on the SAP Easy Access|


|Program|Function|Description|
|---|---|---|
| | |screen: Hedge Plan List (THMEX) or Hedging Relationships: Effectiveness Test (THM80).|

##### Archiving Raw Exposures and Exposure Positions

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Raw Exposures and Exposure Positions | L4 | trm11 p.101 | loio `5112e76b4fe64716a5c1b70e0e928129` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5112e76b4fe64716a5c1b70e0e928129.html?locale=en-US)

**Use**

Although raw exposures and exposure positions are closely linked, they nevertheless remain separate objects from the technical point of view. For this reason, they are archived using separate archiving objects.

Archiving Raw Exposures (FIN-FSCM-TRM) (archiving object TRTM_REXP)

Archiving Exposure Positions (FIN-FSCM-TRM) (archiving object TRTM_EXPOS)

**Note:**

You can only archive exposure positions, if all raw exposures contributing to the exposure position are already archived or deleted.

**Prerequisites**

Define for specific company codes the minimum residence period (in days) for exposure positions and raw exposures in Customizing for Treasury and Risk Management under Transaction Manager General Settings Exposure Management 2.0

Archiving Raw Exposures and Exposure Positions . The minimum residence period specifies for how many days exposure positions and raw exposures remain in the system after their maturity has expired.


**Process**

The archiving functions are located in the application menu of the Transaction Manager under Utilities Archiving Raw Exposures and Exposure Positions (Exposure Management 2.0) .

Perform archiving using the functions Archive Raw Exposures (transaction FTREX41) and Archive Exposure Positions (transaction FTREX42).

**Note:**

You can also perform archiving by calling transaction SARA and selecting the archiving objects.

Here, you can use the functions Write, Read, and Delete.

**ILM-Based Information for the Archiving Object**

You can use these archiving objects with the TRTM_REXP and TRTM_REXP ILM objects as part of SAP Information Lifecycle Management. You use the ILM Policies app to define residence and retention rules.

**Related Information**

Archiving Raw Exposures with TRTM_REXP

Archiving Exposure Positions with TRTM_EXPOS

###### Archiving Raw Exposures with TRTM_REXP

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Raw Exposures and Exposure Positions > Archiving Raw Exposures with TRTM_REXP | L5 | trm11 p.101 | loio `89e65add327d4b2fa32df867e8621611` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/89e65add327d4b2fa32df867e8621611.html?locale=en-US)

**Definition**

You can use archiving object TRTM_REXP to archive raw exposures. All data relating to the raw exposures is archived. This applies to the header data, raw exposure memo records, sub raw exposures, risk attributes, the different versions, the administrative attributes, and other information. The related exposure positions are not archived with this archiving object.

**Prerequisites**

No additional specific prerequisite must be fulfilled.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the TRTM_REXP ILM object as part of SAP Information Lifecycle Management.

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for TRTM_REXP are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Due date of the raw exposure (DUE_DATE); if the due date is intial the system detemines the due date from the planning period and planning year.

Available Condition Fields

Company Code COMPANY_CODE

Exposure Activity Type EXP_FLOW_TYPE

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Performing Application-Specific Configuration**

If you do not use the ILM policies, you must use the Customizing activities available in the Customizing of Treasury and Risk Management. Define for specific company codes the minimum residence period (in days) for exposure positions and raw exposures in Customizing for Treasury and Risk Management under Transaction Manager General Settings Exposure Management 2.0 Archiving Raw Exposures and Exposure Positions . The minimum residence period specifies for how many days exposure positions and raw exposures remain in the system after their maturity has expired.

Archiving Functionality

The backend-archiving functions are located in the application menu of the Transaction Manager under Utilities Archiving Raw Exposures and Exposure Positions (Exposure Management 2.0) .

Perform archiving using the function Archive Raw Exposures (transaction FTREX41).

**Note:**

You can also perform archiving by calling transaction SARA and selecting the archiving objects.

Here, you can use the functions Write, Read, and Delete.

###### Archiving Exposure Positions with TRTM_EXPOS

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Raw Exposures and Exposure Positions > Archiving Exposure Positions with TRTM_EXPOS | L5 | trm11 p.102 | loio `f48c9fdf80dd4e33a65228eb08f35acd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f48c9fdf80dd4e33a65228eb08f35acd.html?locale=en-US)

**Definition**

You can use archiving object TRTM_EXPOS to archive exposure positions. All data for the exposure position and the related position flows are archived.

**Prerequisites**

The raw exposures contributing to the exposure position are already archived or deleted.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the TRTM_REXP ILM object as part of SAP Information Lifecycle Management.

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for TRTM_REXP are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Due date of the exposure position (DUE_DATE); if the due date is intial the system detemines the due date from the planning period and planning year.

Available Condition Fields

Company Code COMPANY_CODE

Exposure Position Type EXP_TYPE

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Performing Application-Specific Configuration**

If you do not use the ILM policies, you must use the Customizing activities available in the Customizing of Treasury and Risk Management. Define for specific company codes the minimum residence period (in days) for exposure positions and raw exposures in Customizing for Treasury and Risk Management under Transaction Manager General Settings Exposure

Management 2.0 Archiving Raw Exposures and Exposure Positions . The minimum residence period specifies for how many days exposure positions and raw exposures remain in the system after their maturity has expired.

Archiving Functionality

The backend-archiving functions are located in the application menu of the Transaction Manager under Utilities Archiving Raw Exposures and Exposure Positions (Exposure Management 2.0) .

Perform archiving using the function Archive Exposure Positions (transaction FTREX42).

**Note:**

You can also perform archiving by calling transaction SARA and selecting the archiving objects.

Here, you can use the functions Write, Read, and Delete.

##### Datafeed Archiving: Usage Log with DATAFDLOG

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Datafeed Archiving: Usage Log with DATAFDLOG | L4 | trm11 p.104 | loio `4ea2fda859b74f56e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2fda859b74f56e10000000a42189e.html?locale=en-US)

**Use**

When the user log is archived, the data is written to an external file.

**Activities**

- 1. Choose Financial Supply Chain Management Treasury and Risk Management Basic Functions Market Data Management Datafeed Usage Log Archive .
- 2. The Archive Administration: Generate Archive Files screen appears.
- 3. Enter the variant needed to start the archiving program, the start date, and the spool parameters.
- 4. Choose Edit Create Job to start the archiving.
- 5. You can do the following:


Reload the archive

Manage the archive

Read the archive

###### Archive Management

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Datafeed Archiving: Usage Log with DATAFDLOG > Archive Management | L5 | trm11 p.104 | loio `4ea2c6c65a2f4f57e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2c6c65a2f4f57e10000000a42189e.html?locale=en-US)

**Procedure**

- 1. Choose Financial Supply Chain Management Treasury and Risk Management Basic Functions Market Data Management Datafeed Usage Log Manage Archive . The Archive Administration: Display Control Records screen appears.
- 2. Here you see the control records of existing user logs. You can now change the archive path and the related notes.
- 3. Save any changes that you make.

###### Reload Archive

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Datafeed Archiving: Usage Log with DATAFDLOG > Reload Archive | L5 | trm11 p.105 | loio `4ea2c6995a2f4f57e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2c6995a2f4f57e10000000a42189e.html?locale=en-US)

**Context**

The archived user log is reloaded again into the database.

**Procedure**

- 1. Choose Financial Supply Chain Management Treasury and Risk Management Basic Functions Market Data Management Datafeed Usage Log Reload Archive .
- 2. The Archive Administration: Reload Archive Sessions screen appears.
- 3. Enter the variant needed to start the archiving program as well as the Archive Selection, the Start Date, and the Spool Parameters.
- 4. Choose Edit Create Job to reload the file.

###### Read Archive

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Datafeed Archiving: Usage Log with DATAFDLOG > Read Archive | L5 | trm11 p.105 | loio `4ea2c6615a2f4f57e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2c6615a2f4f57e10000000a42189e.html?locale=en-US)

**Context**

You use a report to read an external file in archive format DATAFDLOG.

**Procedure**

- 1. Choose Basic Functions Market Data Management Datafeed Usage Log Read Archive . A screen appears on which you can select the files of the archived user logs.
- 2. Select the user log that you want to read.
- 3. Press ENTER . The system reads the archived user log and displays it.

##### Archiving of Financial Objects with JB_FOBJ

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving of Financial Objects with JB_FOBJ | L4 | trm11 p.105 | loio `d52d89b589aa477eab431fbcac71d039` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d52d89b589aa477eab431fbcac71d039.html?locale=en-US)

**Context**

The archiving object JB_FOBJ is used to archive financial objects that are no longer required in the online system.

The financial objects are needed for all objects in Treasury and Risk Management that you would like to analyze in Risk Management. Financial objects link the business data of the Treasury objects, such as financial transactions, treasury positions, and exposure positions, with the selection criteria and analysis parameters that are needed in Risk Management.

**Prerequisites**

The end date of the corresponding financial transaction has passed.

**Tables**

The archiving object archives data from several tables. To check which tables these are, call up transaction SARA, enter the archiving object, and choose Database Tables. You can display the relevant tables in the lower part of the screen.

**Archiving Classes**

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

You can use this archiving object with the ILM object JB_FOBJ as part of SAP Information Lifecycle Management.

The following fields for JB_FOBJ are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Bases

Created On CREATION_DATE

Available Condition Fields

Company Code BUKRS

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

##### Archiving Limits and Limit Utilizations with TRTM_LM

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Limits and Limit Utilizations with TRTM_LM | L4 | trm11 p.106 | loio `4ea2a35d5a2f4f58e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ea2a35d5a2f4f58e10000000a42189e.html?locale=en-US)

**Context**

The TRTM_LM archiving object is used to archive and delete limits and limit utilizations. When you use Limit Management, this leads over time to very large volumes of data being saved. To ensure that evaluations are not slowed down by excessively large volumes of data, you can delete limits and utilizations from the system. However, before you can delete this data from the system, you first need to have archived it in a previous step.

**Prerequisites**

The limits and limit utilizations have expired or reached their end date.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for TRTM_LM are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Start Date of Retention Period, which is the Valid-To Date of a limit.

Available Condition Fields

Company Code BUKRS

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

##### Archiving Single Records (RDB) with RDBRA_REC

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Single Records (RDB) with RDBRA_REC | L4 | trm11 p.107 | loio `5ec45753f263e547e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5ec45753f263e547e10000000a441470.html?locale=en-US)

**Context**

You use the archiving object RDBRA_REC to archive single records that are stored in the results database of the Market Risk Analyzer (FIN-FSCM-TRM-MR).

Prerequisites

Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.

ILM-Based Information for the Archiving Object

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for RDBRA_REC are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Bases

Document Date

Available Condition Fields

Company Code COMPANY_CODE

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

|Program|Function|Notes|
|---|---|---|
|RDBRA_REC_ARC|Write|On the basis of your entries, the write program selects the single records to be|


|Program|Function|Notes|
|---|---|---|
| | |archived. **Note:** You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages. Once the test run has proved successful, you can start the write program in production mode.|
|RDBRA_REC_DEL|Delete|The deletion program deletes all archived single records because data deletion cannot be executed by the write program (for security reasons). On the selection screen, you can choose between Test Mode and Production Mode. The archived positions are deleted only in the production mode.|
| |Read|In the Archive Explorer (transaction SARE), you can display the archived data for the archiving object by using activated information structures. To do this, you can use the information structures delivered by SAP (after activation in transaction SARJ) or user-defined information structures.|
|RDBRA_REC_RELOAD|Reload|You should only use this program in cases when an error has occurred during archiving. Furthermore, we recommend that you perform the reload as soon as possible after the erroneous archiving run was performed. See also: Reloading the Archive **Note:** When you run this program, the system updates the entries in the active archive information structures.|


Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

Technical Data

Size of archiving file: Default Entry 500 MB

**Procedure**

- 1. Creating Archive Files


- a. You are on the Archive Administration: Initial Screen (transaction SARA), and the name of the RDBRA_REC archiving object is entered in the Archiving Object field.
- b. Choose Write.

A screen appears on which you can schedule the write program to be run in the background.

If archiving has already been performed for an archiving object and there are still archive files from that archiving run that have not yet been processed by the relevant deletion program, the system informs you of this in a separate window.

The same applies for interrupted archiving runs.

- c. Use the input help to select a variant. If no variant is available, choose Maintain and create the variant that you require.
- d. Enter the start date and the spool parameters.


**Caution:**

Archiving data more than once can lead to various problems. Hence some archiving objects require that data is not replicated in the archive, because this can lead to incorrect results (such as using archived data to produce totals). Ensure the following:

The new write job that needs to be scheduled does not select the same data that is contained in archive files that have not yet been processed by the deletion program

No variants with overlapping selection values are used in parallel.

**Note:**

If the variant that you have selected is already being used in other jobs, you can choose the Jobs with Selected Variant pushbutton to display the variant and delete it if necessary.

**Note:**

With the Archive Directory pushbutton, you can determine how much storage space is free in the current objectspecific archive directory before you start to archive.

Now you have entered all of the data required for the background job. To run the job, choose Execute.

**Note:**

After all archive files of a run have been written completely, the system event SAP_ARCHIVING_WRITE_FINISHED is triggered by the ADK. In reaction to this event, processes that occur downstream from archiving (such as automated file storage) can be triggered by external tools.

Furthermore, you can navigate to the following menu options:

Customizing

Job Overview: Here you find an overview of all archiving jobs as well as functions for processing them. .

Administration

DB Tables

Information System

**Note:**

You can display the logs documenting processing by choosing Logs from the Archive Administration initial screen.

- 2. Delete the archived data from the database.
- 3. You can display the archived data as follows:

In the Archive Information System (transaction SARI), you can display the data archived when you have activated archive information structures for the archiving object.

- 4. In exceptional cases when archiving runs contain errors, you can use the "Reload" function to reload the archive. For more information, see Reloading the Archive

##### Archiving Final Results (RDB) with RDBRA_FRP

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Final Results (RDB) with RDBRA_FRP | L4 | trm11 p.110 | loio `90d14c5305ebe647e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/90d14c5305ebe647e10000000a441470.html?locale=en-US)

**Context**

You use the RDBRA_FRP archiving object to archive final results that are stored in the results database (RDB) of the Market Risk Analyzer (FIN-FSCM-TRM-MR).

Prerequisites

Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.

ILM-Based Information for the Archiving Object

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for RDBRA_FRP are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Bases

Document Date

Available Condition Fields

Company Code COMPANY_CODE

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

|Program (Technical Name)|Function|Comments|
|---|---|---|
|RDBRA_FRP_ARC|Write|On the basis of your entries, the write program selects the final results to be archived. **Note:** You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages. Once the test run has proved successful, you can start the write program in production mode.|
|RDBRA_FRP_DEL|Delete|The deletion program deletes all archived final results. This is because, for security reasons, data deletion cannot be executed by the write program. On the selection screen, you can choose between Test Mode and Production Mode. The archived final results are deleted only in the production mode.|
| |Read|In the Archive Explorer (transaction SARE), you can display the archived data for the archiving object by using activated information structures. To do this, you can use the information structures delivered by SAP (after activation in transaction SARJ) or user-defined information structures.|


Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

Technical Data

Maximum size of archiving file: Default 500 MB

**Procedure**

- 1. Creating Archive Files


- a. You are on the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object RDBRA_FRP is entered in the Archiving Object field.


- b. Choose Write.

A screen appears on which you can schedule the write program to be run in the background.

If archiving has already been performed for an archiving object and there are still archive files from that archiving run that have not yet been processed by the relevant deletion program, the system informs you of this in a separate window.

The same applies for interrupted archiving runs.

- c. Use the input help to select a variant. If no variant is available, choose Maintain and create the variant that you require.
- d. Enter the start date and the spool parameters.


**Caution:**

Archiving data more than once can lead to various problems. Hence some archiving objects require that data is not replicated in the archive, because this can lead to incorrect results (such as using archived data to produce totals). Ensure the following:

The new write job that needs to be scheduled does not select the same data that is contained in archive files that have not yet been processed by the deletion program

No variants with overlapping selection values are used in parallel

**Note:**

If the variant that you have selected is already being used in other jobs, you can choose the Jobs with Selected Variant pushbutton to display the variant and delete it if necessary.

**Note:**

With the Archive Directory pushbutton, you can determine how much storage space is free in the current objectspecific archive directory before you start to archive.

Now you have entered all of the data required for the background job. To run the job, choose Execute.

**Note:**

After all archive files of a run have been written completely, the system event SAP_ARCHIVING_WRITE_FINISHED is triggered by the ADK. In reaction to this event, processes that occur downstream from archiving (such as automated file storage) can be triggered by external tools.

Furthermore, you can navigate to the following menu options:

Customizing

Job Overview: Here you find an overview of all archiving jobs as well as functions for processing them.

Administration

DB Tables

Information System

**Note:**

You can display the logs documenting processing by choosing Logs from the Archive Administration initial screen.

- 2. Deleting Archived Data from the Database

##### Archiving Single Records (RDB) with RDBPA_REC

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Single Records (RDB) with RDBPA_REC | L4 | trm11 p.113 | loio `dfd53e545a8ea57ee10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dfd53e545a8ea57ee10000000a44176d.html?locale=en-US)

**Context**

You use the archiving object RDBPA_REC to archive single records that are stored in the results database of the Portfolio Analyzer (FIN-FSCM-TRM-PA).

Prerequisites

Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

|Program|Function|Notes|
|---|---|---|
|RDBPA_REC_ARC|Write|On the basis of your entries, the write program selects the single records to be archived. **Note:** You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages. Once the test run has proved successful, you can start the write program in production mode.|
|RDBPA_REC_DEL|Delete|The deletion program deletes all archived single records because data deletion cannot be executed by the write program (for security reasons). On the selection screen, you can choose between Test Mode and Production Mode. The archived positions are deleted only in the production mode.|


Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

Technical Data

Size of archiving file: Max. 500 MB

**Procedure**

- 1. Create archive files.


- a. You are in the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object RDBPA_REC is entered in the Archiving Object field.
- b. Choose Write.

A screen appears on which you can schedule the write program to be run in the background.

If archiving has already been performed for an archiving object and there are still archive files from that archiving run that have not yet been processed by the relevant deletion program, the system informs you of this in a separate window.

The same applies for interrupted archiving runs.

- c. Use the input help to select a variant. If no variant is available, choose Maintain and create the variant that you require.
- d. Enter the start date and the spool parameters.


**Caution:**

Archiving data more than once can lead to various problems. Hence some archiving objects require that data is not replicated in the archive, because this can lead to incorrect results (such as using archived data to produce totals). Ensure the following:

The new write job that needs to be scheduled does not select the same data that is contained in archive files that have not yet been processed by the deletion program.

No variants with overlapping selection values are used in parallel.

**Note:**

If the variant that you have selected is already being used in other jobs, you can choose the Jobs with Selected Variant pushbutton to display the variant and delete it if necessary.

**Note:**

With the Archive Directory pushbutton, you can determine how much storage space is free in the current objectspecific archive directory before you start to archive.

Now you have entered all of the data required for the background job. To run the job, choose Execute.

**Note:**

After all archive files of a run have been written completely, the system event SAP_ARCHIVING_WRITE_FINISHED is triggered by the ADK. In reaction to this event, processes that occur downstream from archiving (such as automated file storage) can be triggered by external tools.

Furthermore, you can navigate to the following menu options:

Customizing

Job Overview: Here you find an overview of all archiving jobs as well as functions for processing them.

Administration

Database Tables

Information System

**Note:**

You can display the logs documenting processing by choosing Logs from the Archive Administration initial screen.

- 2. Delete the archived data from the database.
- 3. You can display the archived data as follows:

In the Archive Information System (transaction SARI), you can display the data archived when you have activated archive information structures for the archiving object.

- 4. In exceptional cases when archiving runs contain errors, you can use the Reload function to reload the archive. For more information, see Reloading the Archive

##### Archiving Final Results (RDB) with RDBPA_FRP

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Final Results (RDB) with RDBPA_FRP | L4 | trm11 p.115 | loio `18d53e545a8ea57ee10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/18d53e545a8ea57ee10000000a44176d.html?locale=en-US)

**Context**

You use the archiving object RDBPA_FRP to archive final results that are stored in the results database (RDB) of the Portfolio Analyzer (FIN-FSCM-TRM-PA).

Prerequisites

Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

The following programs are available:

|Program (Technical Name)|Function|Comments|
|---|---|---|
|RDBPA_FRP_ARC|Write|On the basis of your entries, the write program selects the final results to be archived. **Note:** You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages. Once the test run has proved successful, you can start the write program in production mode.|


|Program (Technical Name)|Function|Comments|
|---|---|---|
|RDBPA_FRP_DEL|Delete|The deletion program deletes all archived final results. This is because, for security reasons, data deletion cannot be executed by the write program. On the selection screen, you can choose between Test Mode and Production Mode. The archived positions are deleted only in the production mode.|


Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization Object

The archiving functions check for the authorization object S_ARCHIVE. See also: Authorization Check

Technical Data

Maximum size of archiving file: 500 MB

**Procedure**

- 1. Create archive files.


- a. You are in the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object RDBPA_FRP is entered in the Archiving Object field.
- b. Choose Write.


A screen appears on which you can schedule the write program to be run in the background.

If archiving has already been performed for an archiving object and there are still archive files from that archiving run that have not yet been processed by the relevant deletion program, the system informs you of this in a separate window.

The same applies for interrupted archiving runs.

**Caution:**

Archiving data more than once can lead to various problems. Hence some archiving objects require that data is not replicated in the archive, because this can lead to incorrect results (such as using archived data to produce totals). Ensure the following:

The new write job that needs to be scheduled does not select the same data that is contained in archive files that have not yet been processed by the deletion program.

No variants with overlapping selection values are used in parallel.

**Note:**

If the variant that you have selected is already being used in other jobs, you can choose the Jobs with Selected Variant pushbutton to display the variant and delete it if necessary.

- c. Use the input help to select a variant. If no variant is available, choose Maintain and create the variant that you require.
- d. Enter the start date and the spool parameters.


**Note:**

With the Archive Directory pushbutton, you can determine how much storage space is free in the current objectspecific archive directory before you start to archive.

Now you have entered all of the data required for the background job. To run the job, choose Execute.

**Note:**

After all archive files of a run have been written completely, the system event SAP_ARCHIVING_WRITE_FINISHED is triggered by the ADK. In reaction to this event, processes that occur downstream from archiving (such as automated file storage) can be triggered by external tools.

Furthermore, you can navigate to the following menu options:

Customizing

Job Overview: Here you find an overview of all archiving jobs as well as functions for processing them.

Administration

DB Tables

Information System

**Note:**

You can display the logs documenting processing by choosing Logs from the Archive Administration initial screen.

- 2. Delete the archived data from the database.

##### Archiving Single Records (RDB) with RDBAA_REC

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Single Records (RDB) with RDBAA_REC | L4 | trm11 p.117 | loio `67d73e545a8ea57ee10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/67d73e545a8ea57ee10000000a44176d.html?locale=en-US)

**Context**

You use the archiving object RDBAA_REC to archive single records that are stored in the results database of the Accounting Analyzer (FIN-FSCM-TRM-AA).

Prerequisites

Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

|Program|Function|Notes|
|---|---|---|
|RDBAA_REC_ARC|Write|On the basis of your entries, the write program selects the single records to be archived.|


|Program|Function|Notes|
|---|---|---|
| | |**Note:** You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages. Once the test run has proved successful, you can start the write program in production mode.|
|RDBAA_REC_DEL|Delete|The deletion program deletes all archived single records because data deletion cannot be executed by the write program (for security reasons). On the selection screen, you can choose between Test Mode and Production Mode. The archived positions are deleted only in the production mode.|


Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

Technical Data

Size of archiving file: Max. 500 MB

**Procedure**

- 1. Create archive files.


- a. You are in the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object RDBAA_REC is entered in the Archiving Object field.
- b. Choose Write.


A screen appears on which you can schedule the write program to be run in the background.

If archiving has already been performed for an archiving object and there are still archive files from that archiving run that have not yet been processed by the relevant deletion program, the system informs you of this in a separate window.

The same applies for interrupted archiving runs.

**Caution:**

Archiving data more than once can lead to various problems. Hence some archiving objects require that data is not replicated in the archive, because this can lead to incorrect results (such as using archived data to produce totals). Ensure the following:

The new write job that needs to be scheduled does not select the same data that is contained in archive files that have not yet been processed by the deletion program.

No variants with overlapping selection values are used in parallel.

**Note:**

If the variant that you have selected is already being used in other jobs, you can choose the Jobs with Selected Variant pushbutton to display the variant and delete it if necessary.

- c. Use the input help to select a variant. If no variant is available, choose Maintain and create the variant that you require.
- d. Enter the start date and the spool parameters.


**Note:**

With the Archive Directory pushbutton, you can determine how much storage space is free in the current objectspecific archive directory before you start to archive.

Now you have entered all of the data required for the background job. To run the job, choose Execute.

**Note:**

After all archive files of a run have been written completely, the system event SAP_ARCHIVING_WRITE_FINISHED is triggered by the ADK. In reaction to this event, processes that occur downstream from archiving (such as automated file storage) can be triggered by external tools.

Furthermore, you can navigate to the following menu options:

Customizing

Job Overview: Here you find an overview of all archiving jobs as well as functions for processing them.

Administration

Database Tables

Information System

**Note:**

You can display the logs documenting processing by choosing Logs from the Archive Administration initial screen.

- 2. Delete the archived data from the database.
- 3. You can display the archived data as follows:

In the Archive Information System (transaction SARI), you can display the data archived when you have activated archive information structures for the archiving object.

- 4. In exceptional cases when archiving runs contain errors, you can use the Reload function to reload the archive. For more information, see Reloading the Archive

##### Archiving Final Results (RDB) with RDBAA_FRP

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving Final Results (RDB) with RDBAA_FRP | L4 | trm11 p.120 | loio `a3d63e545a8ea57ee10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a3d63e545a8ea57ee10000000a44176d.html?locale=en-US)

**Context**

You use the archiving object RDBAA_FRP to archive final results that are stored in the results database (RDB) of the Accounting Analyzer (FIN-FSCM-TRM-AA).

Prerequisites

Since there is no (legal) requirement for a residence time for results of single record procedure and final results, this data can be deleted by system means. There is no archivability check.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

The following programs are available:

|Program (Technical Name)|Function|Comments|
|---|---|---|
|RDBAA_FRP_ARC|Write|On the basis of your entries, the write program selects the final results to be archived. **Note:** You can first run the write program in the test mode to simulate archiving without writing any archive files. If you select the setting Complete for the detailed log and set the Display All Errors indicator, the detailed log contains all processed objects including the related messages. Once the test run has proved successful, you can start the write program in production mode.|
|RDBAA_FRP_DEL|Delete|The deletion program deletes all archived final results. This is because, for security reasons, data deletion can’t be executed by the write program. On the selection screen, you can choose between Test Mode and Production Mode. The archived positions are deleted only in the production mode.|


Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

Technical Data

Maximum size of archiving file: 500 MB

**Procedure**

- 1. Create archive files.


- a. You are in the Archive Administration: Initial Screen (transaction SARA), and the name of the archiving object RDBAA_FRP is entered in the Archiving Object field.
- b. Choose Write.

A screen appears on which you can schedule the write program to be run in the background.

If archiving has already been performed for an archiving object and there are still archive files from that archiving run that haven’t yet been processed by the relevant deletion program, the system informs you of this in a separate window.

The same applies for interrupted archiving runs.

- c. Use the input help to select a variant. If no variant is available, choose Maintain and create the variant that you require.
- d. Enter the start date and the spool parameters.


**Caution:**

Archiving data more than once can lead to various problems. Hence, some archiving objects require that data isn’t replicated in the archive, because this can lead to incorrect results (such as using archived data to produce totals). Ensure the following:

The new write job that needs to be scheduled doesn’t select the same data that is contained in archive files that haven’t yet been processed by the deletion program.

No variants with overlapping selection values are used in parallel.

**Note:**

If the variant that you’ve selected is already being used in other jobs, you can choose the Jobs with Selected Variant pushbutton to display the variant and delete it if necessary.

**Note:**

With the Archive Directory pushbutton, you can determine how much storage space is free in the current objectspecific archive directory before you start to archive.

Now, you have entered all of the data required for the background job. To run the job, choose Execute.

**Note:**

After all archive files of a run have been written completely, the system event SAP_ARCHIVING_WRITE_FINISHED is triggered by the ADK. In reaction to this event, processes that occur downstream from archiving (such as automated file storage) can be triggered by external tools.

Furthermore, you can navigate to the following menu options:

Customizing

Job Overview: Here you find an overview of all archiving jobs as well as functions for processing them.

Administration

DB Tables

Information System

**Note:**

You can display the logs documenting processing by choosing Logs from the Archive Administration initial screen.

- 2. Delete the archived data from the database.

##### Archiving of Saved Datasets with RM_SVSTATE

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving of Saved Datasets with RM_SVSTATE | L4 | trm11 p.122 | loio `93536592a5364cc39abe7039556a445d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/93536592a5364cc39abe7039556a445d.html?locale=en-US)

**Use**

You can use archiving object RM_SVSTATE to archive saved datasets used for backtesting.

**Prerequisites**

The Selection Date of the saved dataset has passed.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for RM_SVSTATE are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Bases

START_RET_DATE

Available Condition Fields

Company Code COMPANY_CODE

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Structure**

Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

The following programs are modified for the ILM enablement of RM_SVSTATE.

Programs

|Program|Function|
|---|---|
|RJBRSTA1|Write|
|RJBRSTA2|Delete|


The delete program contains the standard variants SAP&PROD (production mode) and SAP&TEST (test mode). During the write and delete sessions, regular progress messages appear in the job log (background processing) and in the status line (dialog).

Authorization

The system checks authorization object S_ARCHIVE for all activities.

##### Archiving of Generic Transaction Versions with JB_GTVS

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving of Generic Transaction Versions with JB_GTVS | L4 | trm11 p.123 | loio `5378a0bba77b4ed7bbe7a2d1030feadd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5378a0bba77b4ed7bbe7a2d1030feadd.html?locale=en-US)

**Use**

The JB_GTVS archiving object is used to archive the versions of generic transactions.

**Prerequisites**

End of Term/End of Period of Notice has passed.

**Dependencies**

The archiving object Generic Transaction Versions JB_GTVS is closely related to the archiving object Generic Transactions JB_GETR. If you have archived Generic Transaction Versions, you can then archive the related Generic Transactions as well.

For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA. For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA under Goto

Network Graphic .

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for JB_GTVS are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Start Date of Retention Period

Available Condition Fields

Company Code BUKRS

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Structure**

Extended Archive Management

In addition to the management data generated by ADK, archiving object JB_GTVS writes additional data to tables T001_ARCH.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

The following programs are delivered for JB_GTVS.

|Program|Function|
|---|---|
|RJBD_GTVS_WRI|Write|
|RJBD_GTVS_DEL|Delete|
|RJBD_GTVS_REL|Reload|


The delete program contains the standard variants SAP&PROD (production mode) and SAP&TEST (test mode). During the write and delete sessions, regular progress messages appear in the job log (background processing) and in the status line (dialog).

Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

**Related Information**

Data Archiving Actions ILM Archiving Work Center

##### Archiving of Generic Transactions with JB_GETR

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving of Generic Transactions with JB_GETR | L4 | trm11 p.124 | loio `ac4698ac36b34493aa0d98026fb6c783` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ac4698ac36b34493aa0d98026fb6c783.html?locale=en-US)

**Use**

You can use archiving object JB_GETR to archive generic transactions.

**Prerequisites**

End of Term/End of Period of Notice has passed.

Versions of the generic transactions are already archived/deleted (JB_GTVS)

**Dependencies**

The archiving object Generic Transactions JB_GETR is closely related to the archiving object Generic Transaction Versions JB_GTVS. If you have archived Generic Transaction Versions, you can then archive the related Generic Transactions as well.

For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA. For information on the archiving session order, see the Network Graphic for your archiving object in transaction SARA under Goto

Network Graphic .

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for JB_GETR are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Start Date of Retention Period

Available Condition Fields

Company Code BUKRS

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Structure**

Extended Archive Management

In addition to the management data generated by ADK, archiving object JB_GETR writes additional data to tables T001_ARCH.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

The following programs are delivered for JB_GETR.

|Program|Function|
|---|---|
|RJBD_GETR_WRI|Write|
|RJBD_GETR_DEL|Delete|
|RJBD_GETR_REL|Reload|


The delete program contains the standard variants SAP&PROD (production mode) and SAP&TEST (test mode). During the write and delete sessions, regular progress messages appear in the job log (background processing) and in the status line (dialog).

Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

**Related Information**

Data Archiving Actions ILM Archiving Work Center

##### Archiving of Gap Evaluations with JB_GPAN

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving of Gap Evaluations with JB_GPAN | L4 | trm11 p.126 | loio `20500db9f8a244ee987ee2a13f35b191` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/20500db9f8a244ee987ee2a13f35b191.html?locale=en-US)

**Use**

You can use the archiving object JB_GPAN to archive Gap evaluation transactions.

**Prerequisites**

ALM Horizon Date has passed.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for JB_GPAN are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Valid To Date

Available Condition Fields

Company Code BUKRS

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Structure**

Extended Archive Management

In addition to the management data generated by ADK, archiving object JB_GPAN writes additional data to tables T001_ARCH.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

The following programs are delivered for JB_GPAN.

|Program|Function|
|---|---|
|RJBD_GPAN_WRI|Write|
|RJBD_GPAN_DEL|Delete|
|RJBD_GPAN_REL|Reload|


The delete program contains the standard variants SAP&PROD (production mode) and SAP&TEST (test mode). During the write and delete sessions, regular progress messages appear in the job log (background processing) and in the status line (dialog).

Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

**Related Information**

Data Archiving Actions ILM Archiving Work Center

##### Archiving of Collateral Transactions with JB_COLL

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Archiving Data in Treasury and Risk Management > Archiving of Collateral Transactions with JB_COLL | L4 | trm11 p.127 | loio `9cd9e22c70b34e7590c518604d3ae301` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9cd9e22c70b34e7590c518604d3ae301.html?locale=en-US)

Collateral transactions are archived and deleted using archiving object JB_COLL.

**Use**

You can use archiving object JB_COLL to archive collateral transactions.

**Prerequisites**

End of Validity of collateral provision has passed.

**ILM-Based Information for the Archiving Object**

You can use this archiving object with the ILM object as part of SAP Information Lifecycle Management. In transaction IRMPOL, you can create policies for residence or retention rules, depending on the available policy category. Here you can also see the available time references and which condition fields exist, and decide which of them shall be used in which order to define your rule structure.

The following fields for JB_COLL are defined in the ILM policy and are visible when processing the ILM Policies app:

Available Time Reference

Valid To Date

Available Condition Fields

Company Code BUKRS

Available Policy Categories

RST: Residence Rules

RTP: Retention Rules

**Structure**

Extended Archive Management

In addition to the management data generated by ADK, archiving object JB_COLL writes additional data to tables T001_ARCH.

Programs

To find out which programs this archiving object offers, call up transaction AOBJ and double-click on your archiving object.

The following programs are delivered for JB_COLL.

|Program|Function|
|---|---|
|RJBD_COLL_WRI|Write|
|RJBD_COLL_DEL|Delete|
|RJBD_COLL_REL|Reload|


The delete program contains the standard variants SAP&PROD (production mode) and SAP&TEST (test mode). During the write and delete sessions, regular progress messages appear in the job log (background processing) and in the status line (dialog).

Tables

The archiving object may trigger further archiving classes to write additional data, for example change documents, into the archive. To check which classes these are, call up transaction AOBJ, select your archiving object and choose Archiving Classes Used.

Authorization

The system checks authorization object S_ARCHIVE for all activities.

**Related Information**

Data Archiving Actions ILM Archiving Work Center

#### Data Destruction in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Data Destruction in Treasury and Risk Management | L3 | trm11 p.129 | loio `68ba813c01864e48a63f7cf353b6e2d0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/68ba813c01864e48a63f7cf353b6e2d0.html?locale=en-US)

You use data destruction objects to delete data for which the retention period has expired and there is no legal hold. You can delete data from the database by executing a data destruction run for a corresponding data destruction object.

The following table shows the data destruction object available for Treasury and Risk Management:

|Data destruction object|Description of data destruction object|
|---|---|
|TRTM_LR_DESTRUCTION|Destroying Limit Reservation Data Using TRTM_LR_DESTRUCTION|

##### Destroying Limit Reservation Data Using TRTM_LR_DESTRUCTION

> **Path:** Treasury and Risk Management > Data Management in Treasury and Risk Management > Data Destruction in Treasury and Risk Management > Destroying Limit Reservation Data Using TRTM_LR_DESTRUCTION | L4 | trm11 p.129 | loio `286bfd152bd141bb89566b0418ea9590` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/286bfd152bd141bb89566b0418ea9590.html?locale=en-US)

**Use**

You can use data destruction object TRTM_LR_DESTRUCTION to destroy limit reservations that contain personal data regarding business partner and are no longer relevant once their retention period expires.

The data destruction object TRTM_LR_DESTRUCTION is assigned data destruction program TRTM_VTBLRH_DES.

ILM Object-Based Information for the Data Destruction Object

The data destruction object TRTM_LR_DESTRUCTION is assigned ILM object TRTM_LR_DESTRUCTION.

Tables from which data records are destroyed

|Table|Table Name|
|---|---|
|VTBLRH|Reservations for Limit Amounts (Header)|
|VTBLRP|Reservations for Limit Amounts (Item)|


Standard Fields for ILM Object TRTM_LR_DERSTRUCTION

You use the standard fields to create ILM policies.The standard fields for data destruction object TRTM_LR_DERSTRUCTION for defining ILM policies are:

Time Basis

START_RET_DATE Start of Retention Date

Condition Fields

BUKRS Company Code

Available Policy Categories

RTP: Retention Rules

**Procedure**

Finding Data Destruction Objects

To find data destruction object TRTM_LR_DERSTRUCTION, proceed as follows:

- 1. Execute transaction DOBJ.
- 2. To search for the data destruction object, choose Position.
- 3. Double-click data destruction object TRTM_LR_DERSTRUCTION to view more information such as the data destruction program and the component.
- 4. In the dialog structure, double-click Structure Definition to display the tables from which data is destroyed.


Customizing Settings

To adjust data destruction object TRTM_LR_DERSTRUCTION and define retention rules, proceed as follows:

- 1. In transaction ILMARA, define an audit area and assign the ILM object.
- 2. In transaction IRMPOL, define ILM rules for data destruction object TRTM_LR_DERSTRUCTION.
- 3. In transaction ILMSIM, check (simulate) the retention rules for data destruction object TRTM_LR_DERSTRUCTION (Evaluating Retention Management Definitions).
- 4. In transaction ILM_DESTRUCTION, apply the ILM rules for data destruction object TRTM_LR_DERSTRUCTION to data.


For more information about the Customizing settings for data destruction objects, see:

Processing Audit Areas

Editing ILM Policies

Evaluating Retention Management Definitions

Applying ILM Rules to Data

Executing Data Destruction Object TRTM_LR_DERSTRUCTION

You can destroy data from the database by executing a data destruction run for the corresponding data destruction object.

For more information about executing data destruction objects, see Data Destruction with a Data Destruction Object.

Specify the ILM object that is relevant for data destruction object TRTM_LR_DERSTRUCTION.

Start the data destruction (transaction ILM_DESTRUCTION):

- 1. Select Data from the Database as the Type of Data to Be Destroyed.
- 2. Enter the ILM object associated with data destruction object TRTM_LR_DERSTRUCTION.
- 3. Choose Execute. In the destruction of data from the database, the actions to be started (Destroy and Administration) are displayed.
- 4. Define variants for the data destruction program.


Define a selection variant for the data destruction.

General selection criteria

Standard ILM test and processing parameters

Test Mode

Production Mode

Detailed Log

Log Output

Description of Data Destruction Run

- 5. Define a start date and the spool parameters for the data destruction run and choose Execute.


Authorization Objects

You require the following authorization for data destruction with TRTM_LR_DERSTRUCTION:

|Authorization object|Description|
|---|---|
|S_ARCD_OBJ|Execute data destruction run for data from the database|

