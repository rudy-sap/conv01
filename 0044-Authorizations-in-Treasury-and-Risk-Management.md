# Authorizations in Treasury and Risk Management - SAP TRM Knowledge Base (branch split)

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

### Authorizations in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Authorizations in Treasury and Risk Management | L2 | trm01 p.70 | loio `634e8d53df194e3fe10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/634e8d53df194e3fe10000000a441470.html?locale=en-US)

**Standard Authorization Objects**

The table below shows the relevant authorization objects that are used by SAP Treasury and Risk Management (class TRTM Treasury Management).

Standard Authorization Objects

|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
|CMM_ESTIME|01 Create or Generate 02 Change 03 Display 06 Delete|This authorization object enables you to restrict who can create, edit, delete, or display exception end-of-day snapshot definitions.|
|CMM_STIME|01 Create or Generate 02 Change 03 Display 06 Delete|This authorization object enables you to restrict who can create, edit, delete, or display end-of-day snapshot definitions.|
|T_ASGTTMPL Acct Assignment Templates|02 Change| |
|T_RMOB_AUG Application Objects for CFM/Banking Analysis|01 Create or generate 02 Change 03 Display 06 Delete 21 Transport|This authorization object controls authorization for editing and using different settings within CFM/Banking Analysis (e.g. evaluation type, scenario, portfolio hierarchy).|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
|F_T_MDSET Market Data Sets|01 Create or Generate 02 Change 03 Display 06 Delete|This authorization objects controls the authorization to create, change, and delete market data sets in the Manage Market Data Sets app (app ID TAN_MDS). The Manage Market Data Sets app does not check authorization for the activity 03 Display.|
|T_CURR_MNT Manage Currency Changeovers|01 Create 02 Change 03 Display 06 Delete|You can use this authorization object to control the creation and further processing of currency changeovers in Treasury and Risk Management using the Manage Currency Changeover function (transaction TPM_CCO_MANAGE). Defined fields: ACTVT Activity|
|T_POS_ASS Assign Attributes to Positions|01 Create or generate 02 Change 03 Display |This object checks if the user is allowed to create, change (delete), or display position attributes. These attributes are the position’s account assignment reference and the position management procedure. You can control the authorization for each accounting code, valuation area, and product type. The check for assignment of the position management procedure is carried out when a position is created either manually or automatically. The check for assignment of the account assignment reference is carried out with the first posting to the position or when the account assignment reference is manually assigned to the position.|
|T_DEAL_REF Reference Maintenance Reference Category|01 Create 02 Change 03 Display 85 Reverse|With this authorization object, you can control for which reference categories the user has authorization to create, change, display, and reverse references. Defined fields: REFTYP Reference Category (Unit Category) ACTVT Activity ) When you have activated the reference check in Customizing for Treasury and Risk Management under Transaction Manager General Settings Organization Make Settings for Authority Checks , the authorization object T_DEAL_REF is checked in the following functions:|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| | |Create: Create Reference (transaction TBR6) Change: Change Reference (transaction TBR7) Display: Display Reference (transaction TBR8) Reverse: Undo Reference (transaction TBR9) Additionally, the authorization object is checked in the Collective Processing: References function (transaction TBRL).|
|T_TLR_REP Authorization for Legal Report Type|02 Change 03 Display 70 Administer|With this authorization object, you define user-specific authorizations for activities concerning trade repository objects. Use in function: Trade Repository Monitor (transaction FTR_TARO_MONITOR) Update Trade Repository Objects (transaction FTR_TARO_PROCESS) Send Trade Repository Objects (transaction FTR_TARO_SEND) Import Incoming Messages (transaction FTR_TARO_IMPORT) Report R_TLR_TARO_STATUS_REMARK Update the Status or the Text in the Field Remark of TAROs|
|T_FXM_BSR Balance Sheet Exposure Hegde Request|01 Create or generate 02 Change 03 Display 06 Delete 43 Release 85 Reverse|With this authorization object, you can restrict the processing of balance sheet exposure hedge requests. Defined fields: ACTVT Activity BUKRS Company Code RCURR Risk Currency|
|T_FXM_SNAP Snapshot - Balance Sheet FX Risk|01 Create or generate 02 Change 03 Display 06 Delete 43 Release|With this authorization object, you can restrict the processing of snapshots of balance sheet exposures (FX) and their related hedges. Defined fields: ACTVT Activity BUKRS Company Code|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |85 Reverse|RCURR Risk Currency|
|T_MRM_KF Authorization object for Market Risk Key Figures|03 Display|This authorization object enables you to restrict the display of market risk key figures. You can restrict the display authorization by company code and portfolio. Defined fields BUKRS (Company Code): You use this field to control which data can be displayed. RPORTB (Portfolio): You use this field to control which data can be displayed. ACTVT Activity|
|T_MRM_KFRC Market Risk Key Figure Set: Enable Real-Time Update|02 Change|With this authorization object, you can authorize users to use the real-time update function in a market risk key figure set. Only users with Change authorization can set the Real-Time Update indicator for a market risk key figure set. Defined fields ACTVT Activity|
|T_FIN_POS Authorization for Treasury Financial Position| |With this authorization object, you check the authorization for financial positions in the financial status apps. Defined fields: BUKRS Company Code|
|T_TOE_EXI Authorization Object for Exposure Item|02 Change|You use this authorization object to control authorization for the maintenance of exposure items. Defined fields AUTH_GR Authorization Group You can create authorization groups in Customizing for Treasury and Risk Management under Define Authorization Groups for Hedging Areas BUKRS Company Code ACTVT Activity|
|T_TOE_HMC Hedge Management Cockpit|03 Display|With this authority object, you can control which data can be shown using the Hedge|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| | |Management Cockpit. Defined fields AUTH_GR Authorization Group You can create authorization groups in Customizing for Treasury and Risk Management under Define Authorization Groups for Hedging Areas BUKRS Company Code RCURR Risk Currency ACTVT Activity|
|T_DEAL_PD Authorization for Product/Transaction Types|01 Create or generate 02 Change 03 Display 06 Delete 16 Execute 38 Perform 43 Release 48 Simulate 83 Counterconfirm 85 Reverse AB Settle KI Knock In KO Knock Out KU Give notice PR Process Correspondence PS VF Expired|With this authorization object, you determine for a user which functions and activities he is allowed to execute for a product and transaction type within a company code. Use in functions: All transaction of the Transaction Management (Trade, Back Office) of the Transaction Manager (FSCM-TRM-TM) which create or maintain financial transactions including the BAPIs.|
|T_IGT_DEAL Authorization for Product/Transaction Types for IGT|01 Create or generate 02 Change 03 Display 06 Delete 10 Post|With this authorization object, you determine which functions and activities are allowed for a product and transaction type in a company code for Intragroup transactions [within Edit Intragroup Transactions (transaction TRIG_IGT)].|
|T_DEAL_DP Authorization for Securities Account|01 Create or generate 02 Change 03 Display |With this authorization object, you determine which functions and activities are allowed for a securities account in a company code.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |06 Delete 16 Execute 43 Release 48 Simulate 85Reverse PR Process Correspondence PS |Use in functions: TRS_SEC_ACC – Edit Securities Account FWDP – Securities Account List TS09 – Define Default Values|
|T_DEAL_AG Authorization for an Authorization Group|01 Create or generate 02 Change 03 Display 06 Delete 16 Execute 43 Release 48 Simulate 85 Reverse PR Process Correspondence PS |With this authorization object, customer specific authorization checks can be carried out if necessary in addition to the objects T_DEAL_DP T_DEAL_PF T_DEAL_PD Application examples: A trader should only be allowed to display/process department-related orders. A clerk should not be allowed to display/process an employee loan.|
|T_EXT_SEC Authorization for external security account|01 Create or generate 02 Change 03 Display 06 Delete|Authorization object for maintaining external securities account statements|
|T_RIGHTS Authorization to Exercise Options|03 Display 38 Perform 48 Simulate 85 Reverse|The authorization object T_RIGHTS is required for exercising security rights in the securities area of the Transaction Manager. The system checks the object T_RIGHTS in the application function for exercising security rights (path: Transaction Manager Securities Trading Security Right Exercise / Reverse ).|
|T_BP_USED Business Partner: Authorization for Where-Used List| |Prior to calling up the where-used list of the business partner from dialog maintenance, or with incoming telephone calls, a check is made as to whether the user has the authorization to display the use of a business partner in a particular application. If this is not the case, the user is not offered the corresponding application to see how the business partner is used.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| | |The partner number and assignment category fields are requested. The assignment category defines the application being used by the business partner (for example, Real Estate, Money Market, Loans). The assignment categories can be displayed with the V_TPR1 view.|
|T_BP_USEDT Business Partner: WhereUsed List Authorization (Decoupling)| | |
|T_FTI_LDB CFM Position Management Reporting Using Logical Databases| |You use this authorization object to assign authorizations for position management reporting using logical databases.|
|T_CML_ARCH CML: Authorization in Loans Archiving Area|03 Display 24 Archive 25 Reload 33 Read 56 Display archive 57 Save archive |When you select a transaction, the system checks whether the function may be executed and in which company codes the system is permitted to process documents.|
|T_RMCHAR_V Characteristic Values in Risk Management Reports| |You can use this authorization object to define for which financial objects a user can run particular evaluations. The authorization is based on characteristic values. Defined fields Report Category The report category describes the business purpose of the analysis (for example, NPV analysis, gap analysis). The possible values can be taken from the fixed values for domain RMRPTYPE. Characteristic Value Note: The checking of the characteristics is based on an AND link. This means that if an entry for the field Characteristic is not equal to *, then an additional entry with the value * has to be defined for each characteristic for which all values are permitted. No hierarchy can be defined with this authorization object. For example, this means that is not possible to give a user authorization for all product types in company|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| | |code 001, but then to restrict the authorization to certain product types in company code 002. Any restriction of the authorization to certain product types would apply automatically to company code 001.|
|T_KAPM_1 Corporate Actions I|01 Create or generate 02 Change 03 Display 63 Activate|You use this object to define the user authorizations for: Corporate action types Activities Use in functions The object T_KAPM_1 is checked in the application function under Securities Back Office Corporate Actions .|
|T_KAPM_2 Corporate Actions II|10 Post 48 Simulate 85 Reverse|With this authorization object, you specify at company code level the corporate actions for which posting runs, simulation runs, or the reversal of posting runs can be executed. Use in functions Object T_KAPM_2 is checked in the application functions Post Corporate Action and Reverse Corporate Action under Securities Accounting Corporate Action .|
|T_THXE_ET Effectiveness Tests|01 Create or generate 02 Change 03 Display 06 Delete 94 Override|You can use this authorization object to manage the access in the effectiveness test part of the Hedge Accounting for Positions. Use in functions: The system checks whether the user is authorized to execute the function based on Company Code, Valuation Area, Hedging Relationship Category, Hedging Relationship Profile and Activitywithin the following functions: Manage Hedging Relationships (transaction TPM100) Run Effectiveness Test (transaction TPM110|
|T_TREA_EVA Execute or Display Evaluation Data on External Accounts|01 Create or generate 03 Display|With this authorization object, you determine which activities for evaluations on external accounts can be performed by which users.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| | |Use in functions: NPV Calculation for External Account Transactions (transaction: TREA_EVAL) Show Results of Key Figure calculation for External Accounts (transaction: TREA_EVAL_SHOW)|
|FW_UMS_BUK Securities Account Transfer CoCd Authorization|01 Create or Generate 85 Reverse|With this authorization object, the system checks for a securities account transfer (inflow) the authorization for the company code and product type. Defined Fields: BUKRS: Company Code GSART: Product ACTVT: Activity|
|F_T_NPV Financial Transaction Net Present Value|Activity Assignment / Text / Access Category Code: 01 Create or generate (Write); 02 Change (Write); 03 Display (Read); 06 Delete (Write)|You can use this authorization object to read, create, change, or delete net present values for financial transactions in the NPV table (VTVBAR) using the API API_FinancialTransactionNPV Financial Transaction NPV - Read, Create, Change, Delete within the SAP Treasury Management – Financial Transactions NPVs Integration (SAP_COM_0923) communication scenario. Defined Fields: ACTVT: Activity BUKRS: Company Code NPVTYPE: Price /NPV Type of OTC Transactions|
|T_RIGHTS_D Exercise Rights for Listed Options or Futures|03 Display 38 Perform 48 Simulate 85 Reverse| |
|T_TEX_POS Exposure Position|02 Change (Change attributes of the exposure position) 03 Display (Display exposure position) 59 Distribute (Update exposure position in the Hedge Accounting for Exposures) 61 Export (Export exposure position to market place or other function covered by|The authorization object controls which activities are allowed for exposure positions within Exposure Management 2.0.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |BAdI)| |
|T_TREA_CA External Account|01 Create 02 Change 03 Display 06 Delete NP Net Payment|With this authorization object, you determine for users which activities they are allowed to execute for an external account. Used in functions: Maintain External Accounts (transaction TREA_ACC_MNT) Create Net Payment (transaction TREA_PAY)|
|T_TREA_STA External Account Statement|Create or generate Change Display Delete Release|With this authorization object, you determine for users which activities for an external account statement they are allowed to execute. Used in functions: Maintain External Account Statements (transaction TREA_STA_MNT) Upload External Account Statements (transaction TREA_STA_UPL) Release Line Items (transaction TREA_RELEASE)|
|T_BP_DEAL FS Business Partner: Standing Instructions|01 Create or generate 02 Change 03 Display |The system checks against the authorization object Treasury Business Partner: Standing Instructions when the user calls up the standing instructions function. The system only displays the standing instructions for which the user is authorized. Examples: If a user is not authorized to use the standing instructions function, this user is unable to branch to the standing instructions from the business partner master data screen. If a user is only authorized to maintain transaction authorizations, the system only displays the corresponding tab for transaction authorizations when this user calls up the standing instructions.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
|T_FGDT_ART Generic Transaction: Authorization Types|01 Create or generate 02 Change 03 Display |You can use this authorization object to define authorizations for the input fields of the generic transaction. Based on the field values, you define which generic transactions the user is allowed to maintain. To do this, you have to define an authorization type and the names of the fields to be checked in the Customizing settings for generic transactions. Note: This authorization is optional. You do not need to assign authorizations if you do not want to give special protection to a particular field group, and have not therefore stored field groups for authorization in your Customizing settings. Procedure If you want to use this authorization object, proceed as follows: Decide for which fields in the generic transaction you want to assign authorizations. In the Customizing for the generic transaction, create an authorization type for these fields. Define the authorizations you want to assign to selected employees. Use the authorization type you have created and define the corresponding values for the activity and the selected fields of the generic transaction. Assign the authorizations you have created to the selected employees by using the relevant profile.|
|T_HM_BUK Hedge Accounting (E-HA) in Company Code|01 Create or generate 02 Change 03 Display 06 Delete|Authorization object for the functions of hedge accounting (E-HA) in the company code.|
|IDCFM_FRIM Impairment Authorization Object|01 Display 02 Create 03 Update |Authorization object for impairment function.|
|F_T_VTBLV Limit|02 Change 03 Display |With this authorization object, you define which limits can be edited.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |05 Lock 43 Release 98 Mark for release|The object consists of the fields Limit type and Activity.|
|F_T_VTBLR Limit Reservations|01 Create or generate 02 Change 03 Display |This authorization object determines which activities a user can perform for a limit reservation.|
|F_T_VTBLL Limit Transfers|01 Create or generate 02 Change 03 Display | |
|T_STAM_GAT Master Data: Class Category|01 Create or generate 02 Change 03 Display 06 Delete 43 Release 56 Display archive 57 Save archive |This authorization object enables you to control the various activities that can be executed with a security class. You can also control the activities according to the product type. You can set up your system, for example, so that a certain employee can change stocks, but can only display bonds. Use in function: Class Data (transaction FWZZ)|
|T_DEAL_PF Portfolio Authorization|01 Create or generate 02 Change 03 Display 06 Delete 16 Execute 38 Perform 43 Release 48 Simulate 85 Reverse AB Settle KI Knock In KO Knock Out KS Reverse notice KU Give notice PR Process Correspondence PS VF Expired|With this authorization object, you determine which functions and activities are allowed for a portfolio in a company code.|
|T_PACC_POS Position in Futures Account|10 Post|You use this authorization object to determine the company code, product type,|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |85 Reverse|and futures account for which activities can be executed that affect the position. You use the authorization object for the following transactions or functions: Post Variation Margin: Function A, Activity 10 Post Close Margin: Function A, Activity 10 Reverse Margin Flows: Function A, Activity 85 Manual Posting: Function B, Activity 10 Reverse Manual Posting: Function B, Activity 85 Execute Matching: Function C, Activity 10 Reverse Matching: Function C, Activity 85|
|T_TEX_REXP Raw Exposure|01 Create or generate Create raw exposure 02 Change Change attributes of the raw exposure 03 Display Display raw exposure 06 Delete Delete a raw exposure (Only if it is unreleased) 43 Release Release the raw exposure to exposure positions|The authorization object controls, which activities are allowed for raw exposures within Exposure Management 2.0.|
|T_RDB_CVKF Results Database: Characteristic Value and Key Figure|RMFIENM Analysis Characteristic RMVALUE Charac. attribute AFWKFD Key Figure|With the help of this authorization object you can specify for which values of a characteristic a user may display the values of a key figure. The system checks the values of all defining characteristics for a certain review unit (for example, a portfolio hierarchy node). Authorization for the value * is required for characteristics with no restrictions (for example, those that do not appear in a portfolio hierarchy or only appear at a lower level).|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
|T_RDB_RDEL Results Database: Delete Single Records|AFWAPPL Analyzer Application|This authorization enables you to delete single records from the results database by restricting the deletion to a particular application. For example, if you want to delete single records in Market Risk only, but not those in the Portfolio Analyzer, you specify the application RA here.|
|F_TR_MRM_S Scenario Maintenance|01 Create or generate 02 Change 03 Display 06 Delete|Object F_TR_MRM_S (Scenario maintenance) controls the authorizations for maintaining scenarios in Market Risk Management. On this level you define whether a user is authorized to create, change or display a scenario of a certain scenario type.|
|T_DEPOT Securities Account Position|01 Create or generate 02 Change 03 Display 06 Delete|With this authorization object, you define which position-changing measures may be carried out for the following: Company code Product category Securities account Defined fields Company code Product type Function (D4= Disposition block, D5= securities account transfer, D6= securities account cash flow) Securities account Activity (create, change, display, delete, reverse) **Note:** Necessary authorization for Unblock: 06 (delete) Necessary authorization for Manual posting or debit position: Function: Securities account cash flow (D6) Activity: change (02) Necessary authorization for Update securities account position Function: Securities account cash flow (D6)|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| | |Use in functions Object T_DEPOT is checked in the following functions: Securities account transfer Securities account position overview Manual posting Debit position Reversal of debit position / manual posting Update securities account position Posting journal Activity: change (02)|
|T_SEC_PRIC Security Price Maintenance – Price Type|03 Display Display Security Price 23 Maintain Create/Change/Delete Security Prices|With this authorization object you can control, for which price types a user has the authorization to display or maintain security prices. Defined fields The authorization object has the following fields: S_KURSART Rate/Price Type – Treasury Instruments ACTVT Activity (Display, Maintain) Use When you have activated the security price check in the customizing under Treasury and Risk Management Transaction Manager General Settings Organization Activate Authority Check for Security Price Type the authorization object T_SEC_PRIC is checked in the following functions: Display security price (transaction FW17) Maintain security price (transaction FW18) Class Master Data (transaction FWZZ)|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
|F_T_FBNAME Treasury: Authorization for Asynchronous Datafeed|01 Create or generate|Treasury: Authorization to call up a function module.|
|T_TRADER Treasury: Trader Authorization|02 Change 03 Display |Treasury: Authorization for trader|
|F_T_TRANSB Treasury: Transaction Authorization|TCD Transaction Code|When a transaction is chosen, the system checks whether the user is authorized to execute the function. The authorization object is used within nearly all transactions of SAP Treasury and Risk Management.|
|T_TREA_CA External Account|01 Create 02 Change 03 Display 06 Delete NP Net Payment|With this authorization object, you determine for users which activities they are allowed to execute for an external account. Used in functions: Maintain External Accounts (transaction TREA_ACC_MNT) Create Net Payment (transaction TREA_PAY)|
|T_TREA_STA External Account Statement|Create or generate Change Display Delete Release|With this authorization object, you determine for users which activities for an external account statement they are allowed to execute. Used in functions: Maintain External Account Statements (transaction TREA_STA_MNT) Upload External Account Statements (transaction TREA_STA_UPL) Release Line Items (transaction TREA_RELEASE)|
|T_DEAL_LC|LC_ACTVT: 01 Presentation 02 Document LC_FNCTN: 01 Create 02 Change 03 Display 04 Reverse |With this authorization object, you determine for users which activities they are allowed to execute for a trade finance transaction.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |05 Accept/Reject 06 Pre-check 07 Send to Bank 08 Settle | |
|Obsolete T_HDG_AREA Hedging Area|02 Change 03 Display |This authorization object enables you to restrict who can display or change hedging areas using function Define Hedging Area (transaction TOE_HEDGING_AREA).|
|T_TOEHA Hedging Area|AUTH_GR: You can create authorization groups in Customizing for Treasury and Risk Management under Define Authorization Groups for Hedging Areas. Hedging areas have to be assigned to one authorization group. In this way, you can grant authorization for maintaining specific hedging areas. DGROUP: You use this field to control which data can be changed or displayed. Currently, only Hedge Management Settings and Hedge Accounting Settings are used. ACTVT: You use this field to control which functions can be performed during hedging area maintenance. Create Change Display Create New Version Delete Version Delete|You use this authorization object to control authorization for maintaining hedging areas.|
|T_TOESNP Hedge Management: Snapshot|AUTH_GR: You can create authorization groups in Customizing for Treasury and Risk Management under Define Authorization Groups for Hedging Areas. Hedging areas have to be assigned to one authorization group. In this way, you can grant authorization for snapshots belonging to specific hedging areas. ACTVT: You use this field to control which of the following functions can be performed from within the snapshot function: Create Delete|You use this authorization object to control authorization for creating or deleting hedging areas|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |Flag: If the hedging area is set as relevant for Hedge Accounting, you can grant users authorization to set a snapshot as the version that is relevant for the day.| |
|T_TOE_HMC Hedge Management Cockpit|AUTH_GR: You can create authority groups in Customizing. Hedging areas have to be assigned to one authority group. In this way, you can grant authorization for specific hedging areas. BUKRS: Company code ACTVT: Display|With this authority object, you can control which data can be shown using the Hedge Management Cockpit.|
|T_TOE_HR Authorization Object for Hedge Request|Defined fields AUTH_GR: You can create authorization groups in Customizing for Treasury and Risk Management under Define Authorization Groups for Hedging Areas. BUKRS: Company code. RCURR: You use this field to control which data can be changed or displayed. HREQ_CAT: You use this field to control which data can be changed or displayed. ACTVT: You use this field to control which of the following functions can be performed during hedge request processing: Create Change Display Delete Release Reverse/Withdraw|You use this authorization object to control authorization for the maintenance of hedge requests.|
|T_TOE_TQ Authorization Object for Target Quota|Defined fields AUTH_GR: You can create authorization groups in Customizing for Treasury and Risk Management under Define Authorization Groups for Hedging Areas.|This authorization object enables you to restrict who can overwrite an existing target quota using the Hedge Management Cockpit (transaction TOENE).|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |BUKRS: You use this field to control which data can be changed or displayed. RCURR: You use this field to control which data can be changed or displayed. ACTVT: You use this field to control which of the following activities can be performed when processing target quotas: 02 Change| |
|T_TPI_MM Authorization Object for Trade Request Money Market (MM)|Defined fields BUKRS: Company code. TREQ_CAT: You use this field to control which trade request category can be processed. ACTVT: You use this field to control the following functions: Create Change Display Delete Release Reverse RCURR: You use this field to control the risk currency.|You use this authorization object to control the authorization for trade requests for money market instruments.|
|T_TPI_IG Authorization Object for Trade Request Interest Group|Defined fields BUKRS: Company code. INSTR_GROUP: You use this field to control which instrument groups can be used. ACTVT: You use this field to control the following functions: Create Change Display Delete Release Reverse|You use this authorization object to control authorizations for the different instrument groups available for trade requests.|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
|T_TPI_TR Authorization Object for Trade Requests|Defined fields BUKRS: You use this field to control which data can be changed or displayed. RCURR: You use this field to control which data can be changed or displayed. TREQ_CAT: You use this field to control which data can be changed or displayed. ACTVT: You use this field to control which of the following functions can be performed when processing trade requests: Create Change Display Delete Release Cancel|You use this authorization object to control authorization for maintaining trade requests.|
|T_TPI_RFC Authorization Object for Trade Requests (RFC)|Defined fields ACTVT: You use this field to control which of the following functions can be performed: Export|With this authorization object, you determine that a trade request can be transferred to the SAP Trading Platform Integration application.|
|T_HREL_AUT|The authorization object consists of the following fields: Company Code Valuation Area Activity|With this authorization object, you determine which activities are allowed for a hedging relationship withinHedge Accounting for Positions (P-HA) in a company code and valuation area. Use in function: Manage Hedging Relationships (transaction TPM100) The hedge risk category and hedging relationship category are not used at the moment. (The class of a hedging relationship is obsolete but cannot be deleted for technical reasons.)|
|T_TIME_GRI Time Pattern|Activities 02 Change|This authorization object enables you to restrict who can display or change time patterns using function Define Time|


|Authorization Object|Fields and Permitted Activities|Description|
|---|---|---|
| |03 Display|Pattern (transaction TOE_TIME_PATTERN).|
|Obsolete T_TOE Hedge Management: Snapshot|The authorization object consists of the following fields: BUKRS Company Code CURRENCY Currency ACTVT Activity|With this authorization object, you can restrict who can display snapshots within Hedge Management|
|T_RCD|Recheck Release Reject|With this authorization object, you can restrict who can recheck, release, or reject blocked sales documents for a risk check decision using function Risk Check Decision Management (transaction FTR_RCD).|


The table below shows the relevant authorization objects that are used by SAP Treasury and Risk Management (class FI Financial Accounting).

Standard Authorization Objects

|Authorization Object|Permitted Activities|Description|
|---|---|---|
|F_RPCODE Repetitive Code|Create and change to bring the data into the system,|Repetitive codes are used to simplify processing of recurring payments. Such usage is agreed upon between the user and|
| |Lock and release, to control|the bank.|
| |usability,|You should use the delete function only|
| |Display, to enable the user to use|after you have carefully checked|
| |the function,|and agreed with the bank that it is clear that|
| |Display change documents, to enable you to display the master|a repetitive code is no longer being used and may be deleted.|
| |data changes.|A check is made on the authorization object|
| | |during among other things repetitive code|
| | |maintenance (OT81), with their use in|
| | |supplier payment requests (RVND) and in|
| | |the fast entry of repetitive payments|
| | |(FRFT).|
| | |The company code controls the|
| | |organizational unit in which the activities|
| | |named can be carried out. The partner type|
| | |restricts the activities to those repetitive|
| | |codes for which the payee has the specified|
| | |type (house bank, supplier or Treasury|
| | |business partner are examples).|
| | |When you display change documents, you|
| | |can restrict to the company code only.|


**Authorization Objects in IS-B**

The table below shows the authorization objects in the SAP component IS-B that are used by SAP Treasury and Risk Management.

|Authorization Object|Permitted Activities|Description|
|---|---|---|
|J_B_MARKET IS-B: STC Authorization Object for Market Data|ACTVT: Controls which of the following activities can be performed: Display Analyze|This authorization object is used in authorization checks for yield curve evaluations.|
|J_B_YLDCUR IS-B: STC Authorization Object for Yield Curve Types|The object contains a field activity with the following meaning: Create/copy yield curve type (activity = 01) Change yield curve type (activity = 02) Display yield curve type, check yield curve type, where-used list for yield curve type (activity = 03) Print yield curve type (activity = 04) Delete yield curve type (activity = 06) Transport yield curve type (activity = 21)|This authorization object is used in authorization checks for maintaining yield curve types.|

