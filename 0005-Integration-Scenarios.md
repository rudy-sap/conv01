# Integration Scenarios - SAP TRM Knowledge Base (branch split)

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

### Integration Scenarios

> **Path:** Treasury and Risk Management > Integration Scenarios | L2 | trm01 p.13 | loio `523a6f06d2f34a5e9bfa584091710b7d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/523a6f06d2f34a5e9bfa584091710b7d.html?locale=en-US)

You can connect the Treasury and Risk Management component to other products and external services.

The following integration scenarios are currently available:

Integration with Cash and Liquidity Management

Integration with External Trading Platforms

Integration with Market Rates Management

Treasury Correspondence Integration with SWIFT Network

Transaction Manager and New General Ledger

Connection of Transaction Manager to In-House Cash

Integration with SAP Public Sector Management (PSM)

Trade Repository Reporting via External Provider

#### Integration with Cash and Liquidity Management

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management | L3 | trm01 p.13 | loio `9e186cf44761473b83757330af8b5a69` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9e186cf44761473b83757330af8b5a69.html?locale=en-US)

Allows you to integrate forecasted cash flows from financial transactions into Cash and Liquidity Management via One Exposure from Operation.

The One Exposure from Operations hub is a real-time collection point and storage location for operational data that is relevant for managing cash and liquidity. You can integrate forecasted cash flows from financial transactions into One Exposure from Operations. In this integration scenario, the source application Treasury and Risk Management and One Exposure run in the same system (one-system scenario).

For more information, see also:

One Exposure from Operations

Treasury and Risk Management in One Exposure from Operations

##### Treasury and Risk Management in One Exposure from Operations

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Treasury and Risk Management in One Exposure from Operations | L4 | trm01 p.13 | loio `eb383c57e236d820e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eb383c57e236d820e10000000a44147b.html?locale=en-US)

**Use**

You can integrate forecasted cash from financial transactions into One Exposure from Operations. In this integration scenario, the source application Treasury and Risk Management and One Exposure run in the same system (one-system scenario).

The forecasted cash from TRM contains the following information:

Reference to the business transaction and the flow in TRM

Company Code

Business Partner (filled with the counterparty of the financial transaction and with the issuer for business transactions from security account positions, such as interests of bonds)

Specific TRM parameters:

Product Type

Transaction Type

Transaction Activity Category

Security ID Number

Securities Account

Portfolio

Internal Reference

Characteristics

Assignment

**Note:**

The TRM parameters are available during configuration but are not made visible externally, for example, the fields are not visible in the cash flow items.

House bank account and bank account

Date and Amount

The forecast transaction date is determined based on the transaction payment date.

The forecast transaction amount is determined based on the transaction payment amount.

Certainty Level

One Exposure derives cash forecasts for items representing financial instruments. It stores this information with the following certainty levels:

|Certainty Level|Description|Meaning|
|---|---|---|
|TRM_O|Optional Financial Instrument|Cash forecast from an option in TRM|


|Certainty Level|Description|Meaning|
|---|---|---|
|TRM_D|Financial Instrument|Cash forecast from all other TRM instruments|


**Example:**

For example, you enter an option with an underlying FX transaction. The forecasted cash flows for the FX transaction have certainty level TRM_O. After the option is exercised, the forecasted cash of the foreign exchange transaction has certainty level TRM_D.

Flow Type

The system uses the following flow types for forecasts from TRM in One Exposure:

|Default Flow Types|
|---|
|900100 - Incoming Bank Cash (TRM) 900101 - Outgoing Bank Cash (TRM) |


**Note:**

The flow type is used internally by the system and is also available during configuration, but is not made visible externally, for example, it is not visible in the cash flow items.

Planning Level

The planning level is used to control displays in Cash Management.

Dependent on the chosen Derivation Category for Planning Levels in the Basic Settings for Cash Management Integration Customizing activtity, the planning level is either derived based on your settings in the Assign Planning Levels Customizing activity or based on the substitution rules defined in the Substitution Rules for Planning Levels - Treasury Flows app.

Planning Group

If the cash flow from TRM has no house bank account, the system tries to determine a planning group instead. To do so, it takes the business partner (for example the counterparty in a money market transaction), reads the corresponding

customer (from database table CVI_CUST_LINK), and takes the planning group from the corresponding company-codedependent data (database table KNB1). If no customer exists for this business partner, or if the customer has no planning group assigned to the given company code, the cash flow is updated with an empty planning group. The planning group is then also empty in cash management.

Liquidity Item

The system generates liquidity items based on the queries defined by you in the Define Queries for Liquidity Item Derivation and Assign Queries to Query Sequences apps.

**Data Transfer Process from Treasury and Risk Management to One Exposure from Operations Hub**

Classic Data Transfer Process from Treasury and Risk Management to One Exposure from Operations Hub

The data transfer from Treasury and Risk Management to One Exposure from Operations hub of Cash and Liquidity Management consists of several steps that you can influence at certain points.

- 1. System generates flows with the following flows types for the CM-relevant flows of Treasury and Risk Management:

For product categories 600 and 760 flows with the following flow types are generated:

- 200200 Increase FX Forward Purchase

- 200201 Increase FX Forward Sale


- 200010 Fee Receivable

- 200011 Fee Payable


For product categories 510 - 550 flows with the following flow types are generated:

- 201000 Fin. Instrument Receivable

- 201001 Fin. Instrument Payable


- 200100 Increase Investment

- 200101 Increase Borrowing


- 200020 Interest Receivable Increase

- 200021 Interest Payable Increase


- 200010 Fee Receivable

- 200011 Fee Payable


For all other product categories flows with the flow types 900100 and 900101 are generated.

- 2. System enriches the flows by deriving the following data:


**Note:**

These flow types are only relevant for the configuration of the liquidity item derivation. In the further process, a flow with flow type 900100 or 900101 is generated for each of these flows because only the flows with flow types 900100 or 900101 are consumed by Cash Management apps, such as Cash Flow Analyzer.

**Note:**

These flow types are only relevant for the configuration of the liquidity item derivation. In the further process, a flow with flow type 900100 or 900101 is generated for each of these flows because only the flows with flow types 900100 or 900101 are consumed by Cash Management apps, such as Cash Flow Analyzer.

**Note:**

In the Customizing activity Specify Update Types for Cash Management, you can remove specific update types from the data transfer to Cash and Liquidity Management.

Planning level

Based on your settings in the Customizing activity Assign Planning Levels.

Planning group

Bank account ID (from house bank and house bank account)

- 3. Liquidity items

The system calls the BAdI: TRM Integration into One Exposure (BADI_FQM_DERIVE_LQITEM_TRM) to derive liquidity items. You can use this BAdI, for example, if the available source fields in the origin X under Define Queries for Liquidity Item Derivation are not sufficient.

For all flows for which the BAdI: TRM Integration into One Exposure has not derived a liquidity item, system generates liquidity items based on the queries defined by you in the Customizing activity Define Queries for Liquidity Item Derivation.

- 4. For the flows generated for product categories 600, 760, and 510 - 550 system now also generates flows with flow type 900100 and 900101. The newly generated flows also include the derived data.
- 5. Now the system calls the BAdI: Adjustment of Flows in One Exposure (BADI_FQM_FLOW_ADJUST_CORE). With this BAdI, you can change the flows, for example, you can overwrite the flow type.
- 6. If the liquidity item is initial for a flow, system again starts the derivation of liquidity items based on the queries defined for the origin X.
- 7. System derives the FI account from the bank account.
- 8. The flows from Treasury and Risk Management are now available in the One Exposure from Operations hub.


**Note:**

This step is necessary because only flows with flow type 900100 and 900101 are consumed by Cash Management apps, such as Cash Flow Analyzer.

Simplified Data Transfer Process from Treasury and Risk Management to One Exposure from Operations Hub

If you activated the simplified data transfer process from Treasury and Risk Management to One Exposure from Operations Hub in the Basic Settings for Cash Management Integration Customizing activity, you still can influence the process at certain points. The data transfer process is executed as follows:

- 1. System generates flows with the following flows types for all CM-relevant flows of Treasury and Risk Management:

- 900100 – Incoming Bank Cash (TRM)

- 900101– Outgoing Bank Cash (TRM)


- 2. System enriches the flows by deriving the following data:

Planning level

Dependent on the chosen Derivation Category for Planning Levels in the Basic Settings for Cash Management Integration Customizing activtity, the planning level is either derived based on your settings in the Assign Planning Levels Customizing activity or based on the substitution rules defined in the Substitution Rules for Planning Levels

- Treasury Flows app.

Planning group

Bank account ID (from house bank and house bank account)

- 3. Liquidity items


**Note:**

In the Customizing activity Specify Update Types for Cash Management, you can remove specific update types from the data transfer to Cash and Liquidity Management.

The system generates liquidity items based on the queries defined by you in the Customizing activity Define Queries for Liquidity Item Derivation based on origin U From Treasury and Risk Management.

- 4. System derives the FI account from the bank account.
- 5. The flows from Treasury and Risk Management are now available in the One Exposure from Operations hub.


**Customizing**

Activate Individual Source Applications and Activate Multiple Source Applications

You can activate the source application TRM - Treasury and Risk Management in this Customizing activity. Data coming from TRM is only updated in One Exposure if the application is activated and successfully initialized.

The Customizing activities are available under Cash and Liquidity Management Cash Management Data Setup .

Basic Settings for Cash Management Integration

In this Customizing activity, you choose the Derivation Category for Planning Levels. This derivation category controls how the planning level is derived for Cash Management-relevant Treasury flows. The following values are available:

Classic Assignment (Default setting)

If you use this derivation category, you define the planning level assignment explicitly for each relevant combination of company code, product type, and activity category in the Assign Planning Levels configuration activity.

Derivation

If you use this derivation category, you can define derivation rules for the planning level assignment in the Substitution Rules for Planning Levels - Treasury Flows app.

Assign Planning Levels

Assign the planning levels to Cash Management-relevant treasury flows.

**Note:**

You define planning levels in the Define Planning Levels Customizing activity of Cash and Liquidity Management.

This configuration activity is only relevant if you have chosen Classic Assignment in the Derivation Category for Planning Level field in the Basic Settings for Cash Management Integration Customizing activtity.

The Customizing activity is available under Treasury and Risk Management Transaction Manager General Settings Link to Cash Management .

**Note:**

Customers upgrading from the classic cash management can use the existing settings for the planning level when integrating TRM into One Exposure.

Substitution Rules for Planning Levels - Treasury Flows app

Note

With this app, you can display, change, and create substitution rules for assigning cash management planning levels to the internal flows that are generated by system for each Cash Management-relevant flow in Treasury and Risk Management.

**Note:**

This app is only relevant if you have chosen Derivation in the Derivation Category for Planning Level field in the Basic Settings for Cash Management Integration Customizing activtity.

For more information, see also Substitution Rules for Planning Levels - Treasury Flows.

Specify Update Types for Cash Management

All CM-relevant flows are transferred to Cash Management. These are all flows with update types that lead to FI postings with posting category 2 (Subledger Posting in Payment Currency) or 3 (Bank Posting in Payment Currency). In this Customizing activity, you can deactivate Cash Management integration for specific update types.

The Customizing activity is available under Treasury and Risk Management Transaction Manager General Settings Link to Cash Management .

Simplify Flow Generation

If you are using the integration with Cash and Liquidity Management via One Exposure for Operations, internal flows are generated by system for each Cash Management-relevant flow in Treasury and Risk Management.

The default flow types of the internal flows relevant for Cash Management updates are:

- 900100 – Incoming Bank Cash (TRM)

- 900101 – Outgoing Bank Cash (TRM)


Flows with these flow types are visible in the Cash Management apps.

In this Customizing activity, you can influence the flow generation.

If you do not set this indicator, the classic data transfer process from Treasury and Risk Management to One Exposure from Operations is executed.

During the classic data transfer process, the system generates the internal flows for Cash Management update with different flow types depending on the product category. For some product categories other flow types than the default flow types are used. You can use these different flow types to define the derivation rules for liquidity items. As an additional step during the process for all flows primarily created with other flow types than 900100 or

900101, also flows with flow types 900100 or 900101 are generated. This ensures that all Cash Managementrelevant flows from Treasury and Risk Management are visible in the Cash Management apps, such as the Cash Flow Analyzer app.

In addition, the BAdIs BAdI: TRM Integration into One Exposure (BADI_FQM_DERIVE_LQITEM_TRM) and BAdI: Adjustment of Flows in One Exposure (BADI_FQM_FLOW_ADJUST_CORE) are called during the classic data transfer process, that you can use to influence the liquidity items and flows generated for Treasury and Risk Management data.

If you set the Simplify Flow Generation indicator, the simplified data transfer process from Treasury and Risk Management to One Exposure from Operations is executed.

During the simplified data transfer process, the system generates the internal flows for the Cash Management update only with flow types 900100 or 900101. You can still use the Define Queries for Liquidity Item Derivation Customizing activity to define derivation rules for liquidity items based on origin X One Exposure from Operations (except accounting documents).

The BAdIs BAdI: TRM Integration into One Exposure (BADI_FQM_DERIVE_LQITEM_TRM) and BAdI: Adjustment of Flows in One Exposure (BADI_FQM_FLOW_ADJUST_CORE) are not called during the simplified data transfer process.

The Customizing activity is available under Treasury and Risk Management Transaction Manager General Settings Link to Cash Management .

Edit Liquidity Items

Create and change liquidity items that represent the source and use of cash flows in your company.

The Customizing activity is available under Cash and Liquidity Management Cash Management Liquidity Items .

Define Queries for Liquidity Item Derivation

Define queries to derive liquidity items for the flows from Treasury and Risk Management.

Use the origin X One Exposure from Operations (except accounting documents) or U From Treasury and Risk Management for the derivation of liquidity items for Treasury and Risk Management.

In a query you define the derivation rules for a specific liquidity item. This derivation is based on the data available in the origin.

Origin X

Among many other fields (such as product type, transaction type, activity, securities account, and so on), origin X also provides the flow type, which you can also use to derive the liquidity items.

**Note:**

Available flow types for liquidity item derivation using the classic data transfer process from Treasury and Risk Management to One Exposure from Operations:

For FX spot/forward transactions (product category 600), FX options (product category 760), and money market transactions (product categories 510 - 550), you can use the following flow types to derive separate liquidity items for purchase side, sale side, investment, repayment, interests, and fees.

You can use the following flow types for product categories 600 and 760:

- 200200 Increase FX Forward Purchase

- 200201 Increase FX Forward Sale


- 200010 Fee Receivable

- 200011 Fee Payable


**Note:**

These flow types are only relevant for the configuration of the liquidity item derivation. In the further process, a flow with flow type 900100 or 900101 is generated for each of these flows because only the flows with flow types 900100 or 900101 are consumed by Cash Management apps, such as Cash Flow Analyzer.

You can use the following flow types for product categories 510 - 550:

- 201000 Fin. Instrument Receivable

- 201001 Fin. Instrument Payable


- 200100 Increase Investment

- 200101 Increase Borrowing


- 200020 Interest Receivable Increase

- 200021 Interest Payable Increase


- 200010 Fee Receivable

- 200011 Fee Payable


**Note:**

These flow types are only relevant for the configuration of the liquidity item derivation. In the further process, a flow with flow type 900100 or 900101 is generated for each of these flows because only the flows with flow types 900100 or 900101 are consumed by Cash Management apps, such as Cash Flow Analyzer.

For all other product categories you use the flow types 900100 and 900101 to define queries for liquidity item derivation.

If you are using the simplified data transfer process from Treasury and Risk Management to One Exposure from Operations, you can use the flow types 900100 and 900101 to define queries for liquidity item derivation.

Origin U

**Note:**

You can only use the new origin if you are using the simplified data transfer process from Treasury and Risk Management to the One Exposure from Operations hub.

Origin U also provides the following fields, which you can also use to derive the liquidity items:

Company Code

Product Type

Transaction Type

Portfolio

Activity Category

Hedging Classification

WBS Element

Profit Center

Cost Center

Update Type

Sec. Class ID Number

Securities Account

If no liquidity item can be determined, the system updates the flow with an empty liquidity item.

The Customizing activity is available under Cash and Liquidity Management Cash Management Liquidity Items Derivation Rules for Liquidity Items .

BAdI: TRM Integration into One Exposure (BADI_FQM_DERIVE_LQITEM_TRM)

**Note:**

Only relevant for classic data transfer process from Treasury and Risk Management to One Exposure from Operations.

You can use this BAdI to derive a liquidity item based on additional TRM-specific parameters if the source fields are not sufficient for a thorough liquidity item derivation. You can also use this BAdI to overwrite flow types in One Exposure that originate from the source application TRM.

The Customizing activity is available under Cash and Liquidity Management Cash Management Business Add-Ins (BAdIs) One Exposure from Operations .

BAdI: Adjustment of Flows in One Exposure (BADI_FQM_FLOW_ADJUST_CORE)

With this BAdI, you can change the flows, for example, you can overwrite the flow type.

The Customizing activity is available under Cash and Liquidity Management Cash Management Business Add-Ins (BAdIs) One Exposure from Operations .

**Additional Tools**

Load Transaction Data from Source Applications into One Exposure from Operations Hub

If you want to integrate transaction data that had already been created before the source application Treasury and Risk Management was activated, you use the function Load Transaction Data from Source Applications into One Exposure from Operations Hub (transaction FQM_INITIALIZE) available in area menu under Cash and Liquidity Management

Tools One Exposure from Operations .

Delete Data from One Exposure from Operations Hub

If you want to use a new starting point within an implementation project, you can use this the function Delete Data from One Exposure from Operations Hub (transaction FQM_DELETE ) available in area menu under Cash and Liquidity Management Tools One Exposure from Operations to delete all existing data or the source application TRM from One Exposure. You do this for each company code and source application.

**More Information**

The information is then consumed by cash management apps, such as:

Cash Flow Analyzer

Check Cash Flow Items

For further information, see One Exposure from Operations

##### Substitution Rules for Planning Levels - Treasury Flows

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows | L4 | trm01 p.22 | loio `c69882540ce049d2943b078cf4628f77` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c69882540ce049d2943b078cf4628f77.html?locale=en-US)

App ID: F4406

With this app, you can display, change, and create substitution rules for assigning cash management planning levels to the internal flows that are generated by system for each Cash Management-relevant flow in Treasury and Risk Management.

**Note:**

You can only use the new app if you are using the simplified data transfer process from Treasury and Risk Management to the One Exposure from Operations hub.

For more information, see also

Integration with Cash and Liquidity Management

Treasury and Risk Management in One Exposure from Operations

**Key Features**

This app uses the framework provided by the Manage Substitution/Validation Rules app.

The app provides the following key features:

Create Substitution Rules

Change Rules

Display Rules

Transport Rules

Developer Extensibility

With the Substitution/Validation Logs app, you can view the detailed logs for substitution rule execution at runtime. However, before you do this, you need to activate logging using the Set Substitution/Validation Logs app.

**Prerequisites**

You must have defined all planning levels in the Define Planning Levels Customizing activity of Cash and Liquidity Management. Predefined content is available for this Customizing activity.

The substitution rules defined in this app are only relevant for planning level derivation if you have chosen Derivation in the Derivation Category for Planning Level field in the Basic Settings for Cash Management Integration Customizing activity.

**Note:**

In the Customizing activity Basic Settings for Cash Management Integration, you can choose the derivation category for planning levels.

The default derivation category for planning levels is the Classic Assignment. If you choose this derivation category, the planning level for the treasury flows is derived from the settings in the Assign Planning Levels Customizing activity.

If you selected the Simplify Flow Generation field in this Customizing activity, you can change the derivation category for planning levels to Derivation.

**Note:**

If you want to switch from the classic assignment of the planning level to the derivation of the planning levels using substitution rules, you should first enter the new substitution rules in the Substitution Rules for Planning Levels Treasury Flows app and then change the derivation category in the Basic Settings for Cash Management Integration Customizing activity.

**Applicable Business Contexts**

You manage substitution rules by business context. A context represents the circumstances in which the substitutions are defined and applied. It determines the fields that are available in the rule definition. The following business contexts are supported for rule definition:

|Solution Area|Business Context|Event|
|---|---|---|
|Treasury Management|Treasury Flows: Planning Level Assignment|Treasury Flows: Planning Level Assignment|


**Note:**

The applicable business contexts are defined by SAP and cannot be changed.

**Fields Available for Preconditions and as Source Field**

The fields available for defining preconditions are different for each business context. This enables you to substitute values of the target fields dependent on attributes specific to the business context.

Available Fields:

BankIsKnown Indicates whether Bank is known

CompanyCode Company Code

FinancialInstrActivityCategory Activity Category

FinancialInstrTransactionType Transaction Type

FinancialInstrumentProductType Product Type

HedgingClassification Hedging Classificatn

PlanningLevel Planning Level

Portfolio Portfolio

TreasuryUpdateType Update Type

Available Functions:

The CONCATENATE and SUBSTRING functions are predefined. You can also define your own functions using the Custom Function interface (IF_FIN_RE_CUSTOM_FUNCTION). For more information, see Developer Extensibility

**Note:**

During runtime, the substitution rules are executed in alphabetical order of the rule name because all substitution rules defined in this app change the values for the same field. For more information, see also Display Rules.

**Caution:**

You are responsible for ensuring that the data used in the substitution rule is used in accordance with the applicable legal or business requirements. The results, which substitution rules were applied, and the values of the target fields are visible in the apps for users with treasury business roles and should therefore not contain any sensitive data.

**Target Fields**

You can define substitution rules to fill the following field:

Planning Level

**Apply Rules at Runtime**

At runtime, the derivation process is triggered at several times:

Whenever a CM-relevant flow is created or changed in Treasury and Risk Management, for each flow the corresponding internal flows for CM update are created or updated and the planning level is assigned according to your defined substitution rules.

With Schedule Job for Initialize One Exposure Data app, you can also retrigger the processing of CM-relevant treasury flows. This is necessary, for example, if substitution rules have been changed and the existing flows should also match the new rules.

The substitution rules you defined apply automatically as follows:

Substitution: Derives, replaces, or clears values for the relevant fields defined in the substitution rules. The substitutions take place at the time of data entry with no system messages.

**Note:**

To access the Substitution Rules for Planning Levels - Treasury Flows app from the SAP Fiori launchpad, you must have a business role that contains the TRM - Configuration for Planning Levels Substitution Rules (SAP_TRM_BC_CMPLCONF) business catalog. SAP delivers the Treasury Specialist - Back Office (SAP_BR_TREASURY_SPECIALIST_BOE) business role for your reference. In addition, you need the business catalog SAP_TRM_BC_SUBVALLOG Treasury - Substitution/Validation Log to get the apps F4886 Substitution/Validation Logs and F4945 Set Substitution/Validation Logs.

**Supported Device Types**

Desktop

Tablet

**Note:**

This app contains in-app help for key fields and concepts. To display the help while working in the app, press F1 or click the question mark displayed in the app header.

###### Manage Substitution/Validation Rules

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules | L5 | trm01 p.25 | loio `376962a4f79f4f5fa778a6c83aa67057` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/376962a4f79f4f5fa778a6c83aa67057.html?locale=en-US)

With this app, you can display, change, and create substitution and validation rules for your selected business contexts and events. These rules can be used in the respective business processes to validate, derive, or replace values at the time of entry for the relevant fields.

**Key Features**

The app provides the following key features:

Create Validation Rules

Create Substitution Rules

Change Rules

Display Rules

**Applicable Business Contexts**

You manage substitution and validation rules by business context. A context represents the situation in which the validations and substitutions are defined and applied. It determines the fields or functions that are available in the rule definition. The following business contexts are supported for rule definition:

|Solution Area|Business Context|Substitution/Validation|App Variant|Context-Specific Documentation|
|---|---|---|---|---|
|Management Accounting and Margin Analysis|Market Segment|Not supported|Manage Substitution/Validation Rules - Journal Entries| |
|Management Accounting and Margin Analysis|Financial Planning|Both rule types|Manage Substitution/Validation Rules - Journal Entries|Substitution/Validation Rules for Financial Planning |
|General Ledger Accounting|Journal Entry Item|Both rule types|Manage Substitution/Validation Rules - Journal Entries|Rules for Substitution/Validation |
|Group Reporting|GR Journal Entry Item|Both rule types|Manage Substitution/Validation Rules - Group Journal Entries|Rules for Substitution/Validation |
|Service|Service Document|Substitution rules only|Manage Substitution/Validation Rules - Service Documents|Substitution/Validation for Service Documents |


**Note:**

The applicable business contexts are defined by SAP and cannot be changed. However, you can create your own fields for these contexts and these custom fields are supported by the Manage Substitution/Validation Rules app. For more information about custom field creation, see Custom Fields App and Custom Logic App.

**Apply Rules at Runtime**

At runtime, business users make postings or record data using various apps, such as the Post Group Journal Entries app. Based on the respective context and event, your defined rules apply automatically as follows:

Substitution: Derives, replaces, or clears values for the relevant fields or functions defined in the substitution rules. The substitutions take place at the time of data entry with no system messages.

Validation: Validates the values entered for the relevant fields or functions defined in the validation rules. Depending on the Control Level of each validation rule, when an entered value doesn't comply with the rule, a warning or an error message is

raised. You can follow the link provided in the message to check the rule details and correct the entered values as necessary. Note:

A warning message is indicated by the **Caution:**icon. If there are only warnings, postings can still be completed.

An error message is indicated by the (error)  icon. Errors must be resolved before postings can be completed.

**Note:**

To navigate to the rule display, you must have the necessary authorization.

**Supported Device Types**

Desktop

Tablet

**Note:**

This app contains in-app help for key fields and concepts. To display the help while working in the app, press F1 or click the question mark displayed in the app header.

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

###### Create Validation Rules

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Create Validation Rules | L6 | trm01 p.27 | loio `2447037c6bd54e7796d11d9743c84996` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2447037c6bd54e7796d11d9743c84996.html?locale=en-US)

Validation rules are used to check values as they are being entered in runtime applications. Follow the procedure below to create a validation rule:

- 1. Choose Create Rule.
- 2. In the dialog box that appears, choose a context and an event, then select Validation Rule as the rule type.
- 3. The detail input page is divided into three sections: General Information, Precondition, and Validation. In the General Information section, do the following:

- a. Specify a rule name and a meaningful description.
- b. Choose a control level, Error or Warning. It controls how strict the validation rule is. When data fails the validation at runtime, the system responds differently as follows:


Error: An error occurs and prevents users completing the posting until they correct the erroneous entries.

Warning: A warning occurs but doesn't prevent users completing the posting.

- 4. You can define fields or functions as conditions or statements in the Precondition and Validation sections. The following functions are predelivered by SAP:


**Note:**

The available contexts and events are defined by SAP. Context determines which fields can be included in the rule definition. Event specifies the exact time and location for the validation to occur, for example, when users execute a particular step in a business process.

a. CONCATENATE

Use this function to concatenate a sequence of field values or constants.

b. SUBSTRING

Use this function to calculate a substring of a given input string. It consists of three parameters:

- i. STRING

The parameter string is a mandatory input value.

- ii. OFFSET


This parameter is optional. The character offset in the input string must be a positive integer and only literal values are allowed. 0 is the default offset. If the given offset is too long for a specific input, an empty string is returned.

iii. LENGTH

The length of the substring must be a positive integer. Only literal values are allowed.

You can also define your own functions using the Custom Function interface (IF_FIN_RE_CUSTOM_FUNCTION). For more information, see Developer Extensibility.

- 5. In the Precondition section, set one or more conditions for the validation to take place.

If the conditions are met, the values entered for the relevant fields or functions are to be checked based on the check statements defined in the Validation section.

If the conditions are not met, the values entered are not subject to the validation.

If you leave this section empty, the values entered are always to be checked.

- 6. In the Validation section, define one or more check statements using Field, Operator, and Value.

Note that the relationships between conditions (or statements) are as follows:

Filters for different fields or functions have an AND logic between each other.

Filters for a same field or function have an OR logic between each other. There is an exception: Filters using a negative operator, such as Not equal to, have an AND logic with the filters that use positive operators.

- 7. Save the rule. The rule now has the status New. You must activate the rule before applying it at runtime. For more information about various rule statuses, see Change Rules.


**Example:**

The following rule requires when a business user posts data using the G/L account between 4164000 and 41649999 for the company code 1000 that the cost center is between 200 and 300 but not equal to 210, and the distribution channel is 01:

|Section|Field|Operator|Value|
|---|---|---|---|
|Precondition|GLAccount|Between|41640000 And 41649999|
| |CompanyCode|Equal to|1000|
|Validation|CostCenter|Between|200 And 300|
| |CostCenter|Not equal to|210|
| |DistributionChannel|Equal to|01|

###### Matches Operator

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Create Validation Rules > Matches Operator | L7 | trm01 p.28 | loio `1a6842724a0e4a6b90b4c79513e382b6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1a6842724a0e4a6b90b4c79513e382b6.html?locale=en-US)

When defining validation rules and the Precondition part of substitution rules, you can use the Matches comparison operator to match a string-type field value against a regular expression that is based on the POSIX standard 1003.2. A regular expression is made up of literal characters and special characters following the syntax of regular expressions. It provides a concise and flexible means to represent a set of character strings.

For example, you can define the following validation rule using the Matches operator:

|Section|Field|Operator|Value (Regular Expression)|
|---|---|---|---|
|Precondition|ProjectExternalId|Matches|12345.*|
|Validation|CostCenter|Matches|[A-Z][A-Z] [[:digit:]]*999999|


When a project ID starts with 12345, the rule requires that the cost center value starts with two capital letters and be followed by a number that ends with 999999.

For more information about how to write regular expressions, see Syntax of Regular Expressions.

###### Create Substitution Rules

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Create Substitution Rules | L6 | trm01 p.29 | loio `b53f0144174b4ff180cecb909f430b55` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b53f0144174b4ff180cecb909f430b55.html?locale=en-US)

Substitution rules are used to replace or derive values when values are being entered in runtime applications. Follow the procedure below to create a substitution rule:

- 1. Choose Create Rule.
- 2. In the dialog box that appears, choose a context and a event, then select Substitution Rule as the rule type.
- 3. The detail input page is divided into three sections: General Information, Precondition, and Substitution. In the General Information section, specify a rule name and a meaningful description.
- 4. You can define fields or functions as conditions or statements in the Precondition and Substitution sections. The following functions are predelivered by SAP:


**Note:**

The available contexts and events are defined by SAP. Context determines which fields can be included in the rule definition. Event specifies the exact time and location for the substitution to occur, for example, when users execute a particular step in a business process.

a. CONCATENATE

Use this function to concatenate a sequence of field values or constants.

b. SUBSTRING

Use this function to calculate a substring of a given input string. It consists of three parameters:

- i. STRING The parameter string is a mandatory input value.
- ii. OFFSET

This parameter is optional. The character offset in the input string must be a positive integer and only literal values are allowed. 0 is the default offset. If the given offset is too long for a specific input, an empty string is returned.

- iii. LENGTH


The length of the substring must be a positive integer. Only literal values are allowed.

You can also define your own functions using the Custom Function interface (IF_FIN_RE_CUSTOM_FUNCTION). For more information, see Developer Extensibility.

- 5. In the Precondition section, set one or more conditions for the substitution to take place.

If the conditions are met, values for the relevant fields or functions are substituted based on substitution lines defined in the Substitution section.

If the conditions are not met, values are not substituted.

If you leave this section empty, values for the relevant fields or functions are always to be substituted.

Note that the relationships between conditions are as follows:

Filters for different fields or functions have an AND logic between each other.

Filters for a same field or function have an OR logic between each other. There is an exception: Filters using a negative operator, such as Not equal to, have an AND logic with the filters that use positive operators.

- 6. In the Substitution section, define one or more substitution lines with the following settings:


**Note:**

When defining a filter condition, you can use the Matches operator to compare a field value with a text string represented with a regular expression. For more information, see Matches Operator.

Target Field: Select a field whose values are to be substituted.

Substitution Type: Select how the values for the target field are to be substituted. You can choose from the following types:

Clear value: Clears any existing value for the target field.

Substitute with Constant: Fills in the target field or replaces its existing value with a constant value.

Substitute with Field / Function: Fills in the target field or replaces its existing value with the value from the source field or source function.

Table Lookup: Looks in a custom business object for a source field or source function and uses its value to fill in the target field. For more information, see Table Lookup.

Source: Depending on your selected substitution type, either enter a constant value or select a source field or source function whose value is to substitute the target field.

Overwrite: Select the checkbox if you want to overwrite any existing value of the target field with the value you specified in Source. If you want to keep any existing value of the target field, leave the checkbox unselected.

**Note:**

Depending on the business context setting, some fields cannot be overwritten. In this case, the checkbox is disabled.

**Example:**

When a business user uses the billing document type F1 to post data for the company code 1000, the following rule fills in the Product Sold Group field with the value A001 and the Functional Area field with the value from the Functional Area field of the relevant WBS element:

|Section|Field|Operator|Value|
|---|---|---|---|
|Precondition|BillingDocumentType|Equal to|F1|
| |CompanyCode|Equal to|1000|


|Section|Target Field|Substitution Type|Source|
|---|---|---|---|
|Substitution|SoldProductGroup|Substitute with Constant|A001|
| |FunctionalArea|Substitute with Field / Function|...\_WBSElementBasicDataFunctionalArea|


- 7. Save the rule. The rule now has the status New. You must activate the rule before applying it at runtime. For more information about various rule statuses, see Change Rules.


**Tip:**

You can also create a rule by copying from an existing one and making any necessary changes.

###### Change Rules

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Change Rules | L6 | trm01 p.31 | loio `7473bffbcd7849ec89a73a5da35e2ac0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7473bffbcd7849ec89a73a5da35e2ac0.html?locale=en-US)

For an existing validation or substitution rule, you can edit, activate, disable, or delete it.

When editing a rule, a draft of the rule is generated. Any changes are first saved to the draft and can only be saved to the active version of the rule after you activate the draft. The possible actions to a rule or its draft are as follows:

Edit new rule: After creation, a rule has the New status. You can continue editing the rule, the New status is kept.

Activate new rule: You can activate a new rule so that it has the Active status.

**Note:**

Only active rules can be used in validation or substitution at runtime.

Edit draft or active rule: After activation, when you choose Edit for the rule for the first time, a draft is generated. Any changes you made thereafter are first saved to the draft. The rule displays as the Active status with a   Draft changed by: <user name> link underneath. For this kind of rule, you can take either of the following actions:

Edit the draft again by choosing the draft link and making changes. Draft rules have the Modified status.

Activate the draft by choosing Activate. The draft rule changes to the Active status and overwrites the original active version.

Edit the active rule by choosing the row or the arrow icon ( ), it will discard the existing draft and generate a new draft. Any changes are saved to the new draft.

Disable rule: You can disable an active rule so that it cannot be used in validation or substitution until you activate it again. The rule status changes to Disabled. This is useful if you want to invalidate a rule temporarily.

Delete rule: You can delete a draft or an active rule. Note that when deleting an active rule, its draft version is also deleted.

**Note:**

To ensure auditability, the system keeps track of all changes to the substitution and validation rules on a database table level. The user names and the timestamps of the changes are also persisted.

###### Display Rules

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Display Rules | L6 | trm01 p.32 | loio `cf401f4120f64356a01d4092ea7beba7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cf401f4120f64356a01d4092ea7beba7.html?locale=en-US)

View available rules on the list page or navigate to the detail screen of a rule.

You can view all your available rules on the list page or navigate to the detail screen of a rule. When doing so, you have the following options:

Search for Rules

Personalize List Layout

Show Rule Execution Sequence

Check Rule Errors

Show Rule Script

**Search for Rules**

You can search for specific rules as follows:

In the Search field, enter the text contained in the rule name and description.

Use various filters available in Adapt Filters.

In the Search by Field dialog, select the precondition fields or functions, validation fields or functions, or substitution fields or functions contained in the rules.

**Personalize List Layout**

The rule list displays all substitution and validation rules of the supported contexts and events. You can choose Settings (  icon) to personalize the list layout. For example, you can add or remove columns, group by Context or Event, and sort your selected columns in ascending or descending order. You can also save your personalized settings to a new view, set the new view as default, and select Apply Automatically for the view.

**Show Rule Execution Sequence**

During runtime, the available rules for a given event are run in a certain sequence. This execution sequence is determined automatically by the system. To check the sequence, choose Analyze Rules on the list page. In the dialog box that appears, specify an event and choose Go. The rules are listed in the Enabled Rules tab in prioritized order, that is, the rules to be applied first are listed first.

Generally, rules that can change field values are run before the rules that only read the field values. However, the following conflicts between rules can occur when determining the sequence:

Two or more rules could change values for the same field. These rules are run in alphabetical order of the rule name.

One rule reads the value of field A and fills field B with a value, while a different rule reads the value of field B and fills field A with a value. In this case, the execution sequence cannot be determined, and an error is raised.

**Note:**

The execution sequence of rules that don't have a logical dependency is undefined and cannot be influenced.

**Check Rule Errors**

When activating a rule, the system checks if your input is correct or complete for that single rule. However, conflicts between rules aren't raised at this point.

To check rule conflicts, choose Analyze Rules on the list page. In the dialog box that appears, specify an event and choose Go. The errors and warnings are listed in the Messages tab.

**Show Rule Script**

For a created rule, you can choose Show Script to convert its conditions and validations or substitutions to a script with logic in a format that is both processable by computer and comprehensible to humans. This is especially helpful for complex rules.

###### Transport Rules

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Transport Rules | L6 | trm01 p.33 | loio `b6e2eace91264fdf83c9b191537964ac` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b6e2eace91264fdf83c9b191537964ac.html?locale=en-US)

Substitution and validation rules are configured in a customizing client. These customizing changes are recorded and transported to the production client via customizing requests. In the production client, users only have read access to the configured rules.

Note that any changes made to rules can only be transported in this way after activation of the rules. In addition, deletion of rules can also be transported.

**Note:**

To enable the transport as described above, Automatic recording of changes must be selected as the option for Changes and Transports for Client-Specific Objects in transaction SM30 (table/view T000) for your customizing client.

###### Developer Extensibility

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Developer Extensibility | L6 | trm01 p.33 | loio `cf92618cf8f849999fc08a03dc53c1a5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cf92618cf8f849999fc08a03dc53c1a5.html?locale=en-US)

You can extend the Manage Substitution/Validation Rules app according to your business needs. For this purpose, the following development objects were released for developer extensibility purposes.

**Interfaces**

The following interface is available for development in the SAP S/4HANA ABAP Environment:

Custom Function (IF_FIN_RE_CUSTOM_FUNCTION)

In addition to the SAP-defined functions CONCATENATE and SUBSTRING that are available in the Manage Substitution/Validation Rules app, you can use this interface to extend the app with customer-defined functions.

Implementing the Custom Function interface allows you to integrate custom ABAP logic into the Manage Substitution/Validation Rules app. Once the implementing ABAP class is activated, the implementation is made available

as a function inside the Manage Substitution/Validation Rules app, which allows you to create custom substitution/validation rules.

**Note:**

When implementing the Custom Function interface, make sure to assign the functions to your own namespace.

Additionally, a demo implementation of this interface is available with the class Demo Customer Function (CL_SUBVAL_WEEKDAY). It can be used as a starting point to implement custom functions in the SAP S/4HANA Cloud ABAP Environment. Therefore, the actual logic that is provided with the class is very simple: a weekday calculation.

For more detailed information about the interface and the class, see the ABAP Doc documentation that is directly available within the coding.

For more information about developer extensibility in SAP S/4HANA, see Set Up Developer Extensibility.

###### Table Lookup

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Manage Substitution/Validation Rules > Developer Extensibility > Table Lookup | L7 | trm01 p.34 | loio `a4a67e1643c445409cb624e819681de6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a4a67e1643c445409cb624e819681de6.html?locale=en-US)

The Table Lookup allows you to choose a field from a custom business object and it uses this value to either substitute a target field or to use this value in a comparison condition.

If you selected Table Lookup as the substitution type or as a righthand side of a comparison, the Select Source Field dialog opens and you are prompted to specify the following:

A data source that is defined using the Custom Business Objects app.

A field from the data source you want to use in your substitution or validation.

Under the Conditions section, all the key fields of your data source are listed. You must specify the filter conditions by comparing values of the key fields with those of standard or custom fields. You can also choose to compare values of the key fields with functions. Furthermore it is possible to use constant literal values as part of this condition. By choosing the corresponding compare operator, the input field on the right provides a value help to select possible values from the current custom business object in the system.

If the condition is met by one of the rows in the custom business object, the value for the indicated column is used accordingly by the substitution or validation. If no row is met by the condition, an empty value is returned by the table lookup and no substitution is executed. When the table lookup is used in a compare operation, an empty result returned by the table lookup always means that the comparison is evaluated as FALSE. If the specified condition is met by more than one row in the custom business object, the result is sorted in ascending order according to the primary key and the first row is selected.

The following figure illustrates the main aspects of the table lookup:

[figure TRM01-F004 - How to Substitute with Time-Dependent Data]

How to Substitute with Time-Dependent Data

In some cases, values in the source field change frequently across periods, which are known as “time-dependent data”. You may want your target field filled with those varied values accordingly at runtime, for example, during document creation. Let's see how it works in the following example:

**Example**

In your custom data source, you have the Company Code and Cost Center fields as key fields. The value of Business Unit constantly changes, for example, the business unit for a same combination of company code and cost center is RD10 in year YYYY and it changes to OP20 from the beginning of YYYY+1. In this case, you can also define a validity field as a key field in your data source, for example, the Valid To field of Date type in your data source. So your data source looks like the data in the following table:

|Company Code (Key)|Cost Center (Key)|Valid To (Key)|Valid From|Business Unit|
|---|---|---|---|---|
|C100|CC01|20191231|20190101|RD10|
|C100|CC01|20201231|20200101|OP20|


Now, you want the business unit value from your data source to substitute the Functional Area field. You can define your substitution rule as follows:

|Section|Target Field|Substitution Type|Source|
|---|---|---|---|
|Substitution|FunctionalArea|Table Lookup|Data Source: YY1_<Your custom BO ID> Source Field: BusinessUnit Conditions: CompanyCode Equal To CompanyCode CostCenter Equal To CostCenter ValidTo Greater Than or Equal To <Your specified date field> ValidFrom Less Than or Equal To <Your specified date field>|


In this example, depending on which period range the value of your specified date field falls within, the corresponding BusinessUnit field value is used to fill the Functional Area field when you make an entry at runtime.

###### Substitution/Validation Logs

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Substitution/Validation Logs | L5 | trm01 p.36 | loio `83543fe584d64ee9b67d099e0482c80c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/83543fe584d64ee9b67d099e0482c80c.html?locale=en-US)

With this app, you can display in-depth logs for substitution or validation rules at runtime for a specific event.

**Key Features**

You can use this app to:

View the substitution or validation rule log list and details.

Filter the logs by event, user, or runtime.

Select and combine multiple logs.

Export a list of logs to a spreadsheet.

By selecting a row in the log from the list view, you can open the log detail page. It displays, in a tree-like structure, the processing flow when a set of rules for a specific event are triggered. Each log includes the following information from top to bottom:

A line depicting the event being processed, such as FINS_ACC_JEI_1 for Journal Entry Item.

A line indicating the input document that the substitution or validation applies to, ACDOCU for Group Reporting Journal Entries.

Substitution or validation rule content structured in a way that shows the internal processing flow of how the rule is applied. The third column of this part additionally shows an excerpt of the substitution or validation script, which represents the rule in the back-end process.

The result of the rule application shows, for example, whether the precondition was met, which fields were subject to validation or substitution, or whether validation was successful or the substitution was performed.

**Note:**

Log lines formatted in gray color are less important and are included simply for completeness reasons.

The following screenshot (English only) shows the main aspects described above:

[figure TRM01-F005 - The following screenshot (English only) shows the main aspects described above:]

**Supported Device Types**

Desktop

Tablet

**Note:**

This app contains in-app help for key fields and concepts. To display the help while working in the app, press F1 or click the question mark displayed in the app header.

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

###### Set Substitution/Validation Logs

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Cash and Liquidity Management > Substitution Rules for Planning Levels - Treasury Flows > Substitution/Validation Logs > Set Substitution/Validation Logs | L6 | trm01 p.37 | loio `6b93694bf63b4847807a018353f1a832` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6b93694bf63b4847807a018353f1a832.html?locale=en-US)

With this app, you can enable or disable logging substitution or validation rule execution for a certain user or a time period and set logging level.

**Key Features**

You can use this app to:

View or filter all enabled log settings by event, rule execution user, or logging level

Create new log settings for a specific event or user. The logging is enabled instantly after creation.

Delete any log settings to disable the logging.

Navigate to substitution and validation rule execution logs.

**Logging Settings**

When setting logs, you can specify the follows:

Event: The logging only applies to the rules specific to the event.

Logging Level: Represents the level of log detail, such as recording only the rule execution failures or all rule execution instances.

Logging End Time: Specify until when the rule execution is logged. The logging starts from the current time to your specified end time. The default logging end time is 24 hours from your current time. You can change it to any future time point.

Rule Execution User: Restrict the logging to a certain user. If you leave it empty, all users will be logged.

The following screenshot (English only) shows the main aspects described above:

[figure TRM01-F006]

**Supported Device Types**

Desktop

Tablet

**Note:**

This app contains in-app help for key fields and concepts. To display the help while working in the app, press F1 or click the question mark displayed in the app header.

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

#### Integration with External Trading Platforms

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with External Trading Platforms | L3 | trm01 p.38 | loio `a83dc55781f54dc1a3b4f6dd17c92da7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a83dc55781f54dc1a3b4f6dd17c92da7.html?locale=en-US)

The SAP Trading Platform Integration application allows you to connect external trading platforms easily to your Treasury Management system.

It supports the end-to-end business process with which trade requests created in Treasury Management are sent to an external trading platform, the trades are closed on the external trading platform, and then automatically transferred through the SAP Trading Platform Integration application to your Treasury Management system.

You can also use only the trading process (inbound) that automatically transfers trades that were closed manually on an external trading platform to your Treasury and Risk Management using the SAP Trading Platform Integration application.

Use Cases

FX Trading process (inbound) only

MM trading process (inbound) only

Securities trading process (inbound) only

End-to-end process for hedge requests

End-to-end process for manual trade requests

End-to-end process for cash trade requests (FX)

End-to-end process for cash trade requests (MM)

End-to-end process for B/S hedge requests

End-to-end process for Commodity FX Integration

Requires the activation of the following business functions:

Logistics, Commodity Pricing Engine in SD and MM (LOG_CPE_SD_MM)

TRM, Financial Risk Management for Commodities (FIN_TRM_COMM_RM)

Counterparty limit utilization

Counterparty limit check

**Additional Details**

Trading Process (Inbound)

Financial transactions of the following financial instrument categories can be transferred from an external trading platform to your SAP S/4HANA system using the SAP Trading Platform Integration application:

Foreign Exchange

FX Forward

FX Spot

FX Option

FX Non-Deliverable Forward

FX Non-Deliverable Swap

FX Swap

FX Collar

##### Trade Request

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with External Trading Platforms > Trade Request | L4 | trm01 p.42 | loio `ddc77179799c48c98d2b15c63b3e27fd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ddc77179799c48c98d2b15c63b3e27fd.html?locale=en-US)

Transferred to external trading platforms using the SAP Trading Platform Integration application.

**Definition**

With a trade request, you trigger the conclusion of a financial transaction (trade) on an external trading platform. You can create trade requests with the following categories:

Hedge

A trade request with the trade request category Hedge was created as an FX hedge request in the Hedge Management Cockpit. When the hedge request is released with the Process Hedge Requests app, a trade request is generated automatically.

The requested trade of this kind of trade request can have one of the following instrument categories:

FX Forward

FX Spot

FX Option

FX Non-Deliverable Forward

FX Swap

FX Non-Deliverable Swap

FX Collar

B/S Hedge

A trade request with the trade request category B/S Hedge was created as a balance sheet exposure hedge request by the Generate Balance Sheet Exposure Hedge Requests report (scheduled as a batch job). When the balance sheet exposure hedge request is released with the Process Hedge Requests - Balance Sheet FX Risk app, a trade request is generated automatically.

The requested trade of this kind of trade request can have one of the following instrument categories:

FX Forward

FX Option

FX Non-Deliverable Forward

FX Collar

FX Spot

Cash

A trade request with the trade request category Cash was created as a cash request in the Manage Memo Records app. When the cash request is released with the Manage Memo Records app, a trade request is generated automatically.

The requested trade of this kind of trade request can have one of the following instrument categories:

Foreign Exchange

FX Forward

FX Spot

**Money Market**

Money Market: Fixed Term Deposit/Loan

Commodity FX Integration

A trade request with the trade request category Commodity FX Integration was created as an FX request in the FX Exposure and FX Hedge Request Management app on SAP Business Technology Platform. When the cash request is released using the FX Exposure and FX Hedge Request Management on SAP Business Technology Platform, a trade request is automatically created and released . The requested trade of this kind of trade request can have one of the following instrument categories:

Foreign Exchange

FX Non-Deliverable Forward

FX Forward

Manual

A trade request with the trade request category Manual was created manually in the Process Trade Requests app or with the Treasury Trade Request - Read, Create (API_TREASURYTRADEREQUEST) API.

The requested trade of this kind of trade request can have one of the following instrument categories:

Foreign Exchange

FX Forward

FX Spot

FX Option

FX Non-Deliverable Forward

FX Swap

FX Non-Deliverable Swap

FX Collar

**Money Market**

Money Market: Fixed Term Deposit/Loan

With the Treasury Trade Request - Read, Create (API_TREASURYTRADEREQUEST) API, you can read the existing treasury trade requests in your SAP S/4HANA system, such as hedge trade requests, B/S hedge trade requests, cash trade requests, or manual trade requests. The service also enables you to create manual trade requests for FX and MM instrument categories.

**Prerequisites**

Set up the Integration with External Trading Platforms integration scenario.

For the automatic creation of a trade request for the hedge request of the Hedge Management and Accounting of Net Open Exposures (FX Risk) process, you must activate the SAP Trading Platform Integration on the Main Data tab in the hedging area master data.

**Use**

Trade requests created in your SAP S/4HANA system are sent to an external trading platform via the SAP Trading Platform Integration application, the trades are concluded on the external trading platform, and then they are transferred automatically to the SAP Trading Platform Integration application before being sent back to your SAP S/4HANA system.

**Related Information**

Hedge Management and Accounting of Net Open Exposures (FX Risk) Hedge Request Process Hedge Requests Process Trade Requests Hedge Management of Balance Sheet FX Risk Generate Balance Sheet Exposure Hedge Requests

##### Process Trade Requests

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with External Trading Platforms > Process Trade Requests | L4 | trm01 p.45 | loio `cbd1670b512640588dd279d97c716100` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cbd1670b512640588dd279d97c716100.html?locale=en-US)

App ID: TPITRO

With this app, you can create trade requests of trade request category Manual. You can also display, change, fulfill, and check all trade requests that were created automatically after the release of hedge requests, B/S hedge requests, cash trade requests, or manually. In addition, you can create trade requests of trade request category Manual by uploading a spreadsheet.

If you implemented the Integration with External Trading Platforms integration scenario, the trade requests are sent automatically to the SAP Trading Platform Integration application. The app supports the end-to-end business process with which trade requests created in your SAP S/4HANA system are sent to an external trading platform and with which, trades are then concluded on the external trading platform and automatically transferred through the SAP Trading Platform Integration application to your Treasury and Risk Management system.

If you do not use the SAP Trading Platform Integration application, the trader can use the app to find the trade requests created from B/S hedge request and cash trade request. After the required hedging transactions have been concluded, you can set the status of the trade requests manually to Completed.

**Note:**

Trade requests of category Hedge are only generated automatically after the release of hedge requests if the SAP Trading Platform Integration is activated. For more information, see Hedging Area: Main Data.

With the Treasury Trade Request - Read, Create (API_TREASURYTRADEREQUEST) API, you can also read the existing treasury trade requests in your SAP S/4HANA system, such as hedge trade requests, B/S hedge trade requests, cash trade requests, or manual trade requests. The service also enables you to create manual trade requests for FX and MM instrument categories.

**Key Features**

This app provides the following key features:

Search for all existing trade requests by various criteria to generate a worklist.

Automatically or manually transfer trade requests to the SAP Trading Platform Integration.

Fulfill trade requests manually.

Navigate to the originating request.

Create FX or MM trade requests of trade request category Manual.

Use the Create FX or Create MM button in the Process Trade Requests app, to create a trade request of trade request category Manual.

Create trade requests of trade request category Manual by uploading a spreadsheet.

You can download a template with example data for each instrument category.

During the upload the data in the spreadsheet is checked for consistency. Only valid trade requests can be imported and further processed.

Dual control when trade requests are released or rejected. This means that the person who releases or rejects the trade request is checked against the creator of the request. By default, no message is displayed. You can use Customizing to control whether this is an information message or an error message. You can do this by making an entry in the Customizing activity Change Message Control under Treasury and Risk Management Transaction Manager General Settings

Transaction Management :

Application area FTR_TPI_CORE, message number 093

**Re-Transfer Trade Requests to the SAP Trading Platform Integration**

[figure TRM01-F008 - If you have activated the SAP Trading Platform Integration, trade requests are automatically transferred once they are released. The status In Transfer indicates that they are waiting to be received by the SAP Trading Platform Integration. Once they have been successfully received, they are set to In Process until they are fulfilled.]

If you have activated the SAP Trading Platform Integration, trade requests are automatically transferred once they are released. The status In Transfer indicates that they are waiting to be received by the SAP Trading Platform Integration. Once they have been successfully received, they are set to In Process until they are fulfilled.

If for any reason you want to re-transfer one or more trade requests, you can select these trade requests in the worklist of the Process Trade Requests app and choose Process Release for trade requests with the status Submitted or Process

Transfer for trade requests with the status Released, In Transfer or Transfer Failed. You can also trigger a manual transfer from the editing view of a trade request.

**More Information**

Creating Manual Trade Requests

Processing Manual Trade Requests

Status Changes of Trade Requests

Hedging Area: Main Data

Process Hedge Requests

Create Cash Trade Requests

###### Creating Manual Trade Requests

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with External Trading Platforms > Process Trade Requests > Creating Manual Trade Requests | L5 | trm01 p.46 | loio `d2162ea8c5ed420ab89efa6342add7e6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d2162ea8c5ed420ab89efa6342add7e6.html?locale=en-US)

Use the Process Trade Requests app to create manual trade requests.

**Context**

If you want your trader to trade a specific currency amount without specifying an origin, such as Hedge or Cash, you can use the Process Trade Requests app. It allows you to create manual trade requests directly.

**How to Create Manual Trade Requests**

- 1. Launch the Process Trade Requests app from your SAP Fiori launchpad.
- 2. Create a trade request with the trade request category Manual by choosing   Create FXor   Create MMin the toolbar on top.
- 3. Enter a description for your trade request.
- 4. Specify the following mandatory data depending on the instrument category:

FX

Company code

Instrument category

Buy/Sell indicator

Put/Call indicator

Requested amount

Traded currency

Opposite currency

Value date

MM

Company code

Instrument category

Invest/Borrow

Nominal Amount

Enter the amount and the currency.

Term Start

Term End

- 5. You can also enter additional data on the Additional Attributes tab.
- 6. Save your entries.


**Result**

You have created a manual trade request that can now be processed further.

**What to Do Next**

If the SAP Trading Platform Integration is activated and this trade request meets the criteria you have defined, it is transferred automatically to the SAP Trading Platform Integration once you release it and should go from the status In Transfer directly to In Process, once it has been successfully received.

**Related Information**

Hedging Area: Main Data

Status Changes of Trade Requests

Processing Manual Trade Requests

###### Processing Manual Trade Requests

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with External Trading Platforms > Process Trade Requests > Processing Manual Trade Requests | L5 | trm01 p.48 | loio `6bc7a66fa74e4c73b24c7973dacc8d4e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6bc7a66fa74e4c73b24c7973dacc8d4e.html?locale=en-US)

Edit manual trade requests using the Process Trade Requests app.

**Context**

To transfer a manual trade request to your trader, you must change the status of your trade request to Released.

You can also choose to edit your trade request before transferring it to your trader.

If you no longer require the trade request or if circumstances have changed, you can delete, reject, or cancel the trade request depending on its status.

For more information, see Status Changes of Trade Requests.

**How to Release Manual Trade Requests**

- 1. Launch the Process Trade Requests app from your SAP Fiori launchpad.
- 2. Select a trade request with trade request category Manual from the list.
- 3. Choose Process Submit and then Process Release .
- 4. Your trade request now has the status Released.


Result

If the SAP Trading Platform Integration is activated and this trade request meets the criteria you have defined, it is transferred automatically to the SAP Trading Platform Integration once you release it and should go from the status In Transfer directly to In Process, once it has been successfully received.

**How to Fulfill Manual Trade Requests Manually**

- 1. Launch the Process Trade Requests app from your SAP Fiori launchpad.
- 2. Select a trade request with trade request category Manual from the list.
- 3. Choose Process Fulfill .


You are automatically taken to the detail screen of the trade request that you want to manually fulfill.

- 4. Choose Add to enter the financial transactions with which you want to manually fulfill the trade request.
- 5. Save your entries.


**Related Information**

Hedging Area: Main Data

Process Trade Requests

Creating Manual Trade Requests

###### Status Changes of Trade Requests

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with External Trading Platforms > Process Trade Requests > Status Changes of Trade Requests | L5 | trm01 p.49 | loio `88cf59b75a594934b5287456a700d471` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/88cf59b75a594934b5287456a700d471.html?locale=en-US)

This chapter describes the statuses available for trade requests.

**Status Changes of Trade Requests**

Trade requests are always assigned a status. This way, you can easily tell what stage a trade request is currently in. The following statuses are available.

**Note:**

The statuses Created, Submitted and Deleted are only available for manual trade requests that are created in the Process Trade Requests app. Trade requests received from other apps are set directly to Released.

[figure TRM01-F009 - Created]

Created

When a manual trade request is created in the Process Trade Requests app, the manual trade request gets the status Created.

It can be deleted with this status.

Submitted

As a next step, the correctness of the manual trade request needs to be checked. You can still adapt it, if necessary. If everything is fine, you submit the request for approval.

As a result, your request can be released or rejected. A submitted request can no longer be edited.

If the approver of the manual trade request chooses to reject the request, it gets the status Created again. You can then edit and submit the manual trade request again.

Released

You can release a request only after it has been submitted. If you have selected the Activate SAP Trading Platform Integration checkbox in your hedging area, once the manual trade request has been released, it is transferred automatically to the SAP Trading Platform Integration application and gets the status In Transfer.

For more information, see Hedging Area: Main Data.

In Transfer

The trade request was sent and is waiting to be received by the SAP Trading Platform Integration.

Transfer Failed

There was an error while transferring the trade request. You can choose Process Transfer to send the trade request again.

In Process

Once the manual trade request has been successfully received by the SAP Trading Platform Integration application, it gets the status In Process.

Completed

You can fulfill the request manually by adding the relevant financial transactions on the Financial Transaction tab of the app. The manual trade request then gets the status Completed once the open amount of the trade request is 0.

If you're using the SAP Trading Platform Integration application, the status of the manual trade request changes to Completed once the open amount of the trade request is 0.

Canceled

If the requested amount of the manual trade request is fully declined, the trade request gets the status Canceled. You can also manually cancel trade requests with the status Transfer Failed.

#### Integration with Market Rates Management

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with Market Rates Management | L3 | trm01 p.51 | loio `3f16825cdba946d58251cb5645f4c1cc` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f16825cdba946d58251cb5645f4c1cc.html?locale=en-US)

This topic describes what you have to do to enable the datafeed functionality by using the different SAP Market Rates Management services.

**Purpose**

This integration scenario allows you to use the datafeed functionality to incorporate current and historic market data into your financial transactions by means of the different SAP Market Rates Management services.

Once the market data file has been uploaded, the translation tables are used to convert the formats of external market data into system-internal formats. You have the option of calling up market data either daily (with a scheduled background job) or continuously (in real time).

**Process Steps**

- 1. Subscribe to one of the Market Rates Management service packages and create a service instance and service key. Once you do this, you get a service URL, a client ID, and a client secret required to call the service from your system.
- 2. Set up a communication arrangement for the relevant SAP Market Rates Management service in your system to fetch the market data


**More Information**

For more information on the configuration of the Market Rates Management services, see:

SAP Market Rates Management

SAP Market Rates Management, Refinitiv data option

SAP Market Rates Management, Bring Your Own Rates data option

For more information on the process steps and the corresponding apps, see Datafeed.

#### Treasury Correspondence Integration with SWIFT Network

> **Path:** Treasury and Risk Management > Integration Scenarios > Treasury Correspondence Integration with SWIFT Network | L3 | trm01 p.52 | loio `feda48a0c0cc449c95001559e123355e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/feda48a0c0cc449c95001559e123355e.html?locale=en-US)

**Purpose**

This integration scenario is a part of the Exchange Treasury Correspondence via SWIFT process, which allows you to send and receive Treasury correspondence using MT300 and MT320 SWIFT messages for your FX and money market transactions. The integration is enabled using SAP Multi-Bank Connectivity for communication with the SWIFT infrastructure.

The integration scenario is a prerequisite for using exchange Treasury correspondence via the SWIFT process. To enable this intergration scenario, you need to set up SAP Multi-Bank Connectivity for the Corporation Using SWIFT via SAP Multi-Bank Connectivity use case.

**More Information**

For more information about how to integrate SAP Multi-Bank Connectivity with Treasury and Risk Management, see the product documentation at https://help.sap.com/docs/SAP_MULTI-BANK_CONNECTIVITY product page.

#### Transaction Manager and New General Ledger

> **Path:** Treasury and Risk Management > Integration Scenarios > Transaction Manager and New General Ledger | L3 | trm01 p.52 | loio `1717d7537c98424de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1717d7537c98424de10000000a174cb4.html?locale=en-US)

**Use**

You use the general ledger to portray parallel accounting. You can make postings in ledger for each valuation area and accounting principle.

**Prerequisites**

You have completed the Customizing of the valuation areas in the Transaction Manager under General Settings Accounting Organization Define Valuation Areas .

You use the general ledger accounting.

You have made the required settings for parallel accounting with parallel ledgers. For more information, see Parallel Accounting in Treasury and Risk Management

**Note:**

If you use accounts receivable accounting from the Transaction Manager (TR-TM), you will need to make additional settings. For more information, see Making Settings for Parallel Ledgers.

**Activities**

If you want to use parallel ledgers, you make the following settings:

Assign accounting principles to the corresponding valuation areas. In Customizing, choose Transaction Manager General Settings Accounting Organization Assign Accounting Codes and Valuation Areas .

Assign the accounting principle to a ledger group. In Customizing, choose Financial Accounting (New) Financial Accounting Global Settings (New) Ledgers Parallel Accounting Assign Accounting Principle to Ledger Groups .

#### Connection of Transaction Manager to In-House Cash

> **Path:** Treasury and Risk Management > Integration Scenarios > Connection of Transaction Manager to In-House Cash | L3 | trm01 p.53 | loio `2b1cc55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2b1cc55368511d4be10000000a174cb4.html?locale=en-US)

Background

The Transaction Manager provides a BAdI that you can use to connect payment programs, for example, In-House Cash. The technical name of the BAdI is TPM_EXT_PAYMENT_TRPR.

The BAdI methods are called by payment requests. In general, payments from the Transaction Manager can be processed using postings to customer accounts and using payment requests. If you want to process a payment by using In-House Cash, payment is done using payment requests.

Example Implementation

SAP provides an example implementation for this BAdI, HC_CFM_ADAPTOR, instead of a standard implementation. It realizes the connection to In-House Cash. SAP delivers the example implementation in an inactive status. If you want to activate this implementation, we recommend that you create your own implementation which calls the methods of the example implementation internally.

All payments are processed by using In-House Cash. Instead of payment requests in the general ledger, payment orders are generated in In-House Cash.

You can process payments the same way as using payment requests and payment orders of In-House Cash. In the latter case, you need to modify the method IS_RELEVANT in your implementation. If the method delivers an X, the payment is processed by using In-House Cash. Otherwise the payment is processed by using a payment order.

You can switch directly from the Transaction Manager into In-House Cash in the example implementation. You can display the generated payment orders in the posting journal and in the cash flow of transactions.

#### Integration with SAP Public Sector Management (PSM)

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) | L3 | trm01 p.53 | loio `858fd65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/858fd65378024308e10000000a174cb4.html?locale=en-US)

**Purpose**

The integration of SAP Public Sector Management (PSM) combines the public sector areas Funds Management and Grants Management with Transaction Management in the Transaction Manager. This enables selected account assignment objects to be transferred to the accounting area of SAP Public Sector Management.

**Prerequisites**

You have activated the TM, Integration in Funds Management business function.

You need to implement SAP Public Sector Management (PSM). You need to activate all the necessary Customizing settings for PSM and Funds Management (PSM-FM) by choosing Public Sector Management Funds Management

Government Basic Settings Activate Global Functions for Funds Management (PSM-FM) . You also need to activate

the account assignment elements Fund or a combined Fund and Grant in Customizing by choosing Public Sector Management General Settings for Public Sector Management Basic Settings: Account Assignment Elements

Activate Account Assignment Elements .

If you have not previously been using the Transaction Manager, you need to make the required Customizing settings for the Transaction Manager area.

Required and Optional Migration Steps

If you are already using the Transaction Manager, you need to carry out the necessary and optional conversion steps by choosing General Settings Tools Conversion Programs . Here you set the corresponding migration category and conversion programs.

To enable the Transaction Manager to differentiate the positions by fund or grant, you need to make the following settings in Customizing for the Transaction Manager:

In Customizing under General Settings Accounting Settings for Positions Management Define and Assign Differentiations , you need to create differentiations using the account assignment elements Funds or Funds and Grant and assign them to positions.

You need to make the required settings in the activities Define Update Types and Assign Usages and Assign Update Types for Account Assignment Transfer by choosing General Settings Accounting Account Assignment Transfer .

You need to Assign Transaction Types for Investment Pool Participants and use the BAdI: Investment Pool Participant Transactions. To do this, choose Transaction Manager Securities Transaction Management

Special Functions from Public Sector .

**Key Features**

The integration of SAP Public Sector Management provides the following functions:

You can assign available or requested capital to different funds or to a combination of a fund and grant.

In the areas Money Market and Securities, you can make multiple assignments of a transaction to different funds.

The areas Transaction Management and Securities Account Management can mirror external payment flows irrespective of the internal account assignment objects.

You can distribute transactions to multiple positions and split these positions into funds or funds and grants. It is also possible to distribute positions to funds and grants in the valuation process (valuation of securities positions, write-ups, write-downs, amortization.)

You can assign the positions to organizational units (functional areas or cost centers.) These assignments do not physically split the positions.

You can transfer positions between funds or funds and grants without affecting the external payment flow using the Account Assignment Transfer app. For more information, see also Account Assignment Transfer.

The standard reports for the logical databases and the transactions Position List (TPM12), Position Flow List (TPM13) and Posting Journal (TPM20) include the account assignment objects in Public Sector Management. Other account assignment objects in Funds Management, such as Funds Center, Commitment Item, and Funded Program, can be derived from selected terms in the Transaction Manager.

Functions are also available for managing investment pool participants and investment pools at universities.

##### Fund and Grant

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Fund and Grant | L4 | trm01 p.54 | loio `62e1ae42f94344a987247aa59e2802d9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/62e1ae42f94344a987247aa59e2802d9.html?locale=en-US)

**Definition**

To map investment pool participants and investment pools, the system uses the account assignment object Fund or a combination of a Fund and Grant.

**More Information**

Entering Account Assignment Objects

Account Assignment Transfer

Example: Fund Transfer for a Fixed-Term Deposit

For information on the subcomponents in Public Sector Management, see Funds Management and Grants Management.

###### Entering Account Assignment Objects

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Fund and Grant > Entering Account Assignment Objects | L5 | trm01 p.55 | loio `79b2cc27b7844c759e5b3af00530f514` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/79b2cc27b7844c759e5b3af00530f514.html?locale=en-US)

**Prerequisites**

To use the default values for the function area and cost center, you need to assign an account assignment reference. You can do this in Customizing for the Transaction Manager General Settings Accounting Link to Other Accounting Components Assign Additional Account Assignments to Account Assignment References. If these setting options are

not sufficient, you can use the BAdI TPM_POS_IND_TRAC. To do this, in Customizing for the Transaction Manager,

Money Market Position Indicator Suppress Account Assignment Reference Allocation in Subledger Position Indicator.

**Context**

For all product types from the areas Money Market, Foreign Exchange, OTC Derivatives, Securities, Listed Options, and Futures, you can specify the fund account assignment or a fund together with a grant for each transaction.

For each flow in the areas Money Market and Securities, you can specify more than one of these account assignments. You can also assign each subledger position a function area and cost center.

The following functions are available:

On the Management tab page, the Fund and Grant fields are displayed for each transaction in the Transaction Manager.

In the areas Money Market and Securities, on the Cash Flow tab page you can specify multiple account assignments for the flows you have selected. You can do this for an increase or decrease in the nominal position with regard to money market transactions. In the case of securities transactions, however, you can only specify multiple account assignments for each purchase and sale flow.

To specify a function area or cost center, on the SAP Easy Access screen, choose Transaction Manager Securities / Debt Management Master Data Position Indicator Change. If you have already predefined values in Customizing, the system provides you with default values.

**Procedure**

- 1. On the SAP Easy Access screen, choose Transaction Manager Money Market Trading Create Financial Transaction. Enter the required date on the Structure tab page.
- 2. If you want to specify only one fund or a combination of a fund and grant account assignment for the transaction, enter


- them on the Management tab page.


- 3. To enter multiple account assignments, use the Cash Flow tab page. Use the input help above the table to select a flow and

- then enter the account assignments in the table. You can specify the payment amount, nominal amount, or percentage as part of each account assignment record.


- 4. Repeat this activity for any increase or decrease in the nominal position. If you do not specify an account assignment record for a flow, the system uses the account assignment record that you specified on the Management tab page. If the account assignment record has not been specified on this tab page, the system displays an error message.
- 5. If you want to manually enter a function area or cost center, from the menu bar options choose Environment Position Indicator and then choose Transfer Data from the window.
- 6. Save your entries.

##### Account Assignment Transfer (1 of 2)

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Account Assignment Transfer | L4 | trm07 p.155 | loio `7a22ec792b794b44ae34811c8e4d47c2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7a22ec792b794b44ae34811c8e4d47c2.html?locale=en-US)

With this app, you can transfer the units/nominals of a treasury position to another position with different account assignments (such as cost center, WBS element, functional area, profit center). In this internal transfer, the position component values are transferred proportionally according to the transfer category of the target position management procedure.

The account assignment transfer is a position transfer. You can only execute the function if you use at least one of the following account assignments to differentiate your treasury positions:

Cost center

WBS element

Functional area

Profit center

**Note:**

If you have activated Public Sector Management and use the fund and grant account assignments as differentiation criteria for your treasury positions, the account assignment transfer can also be used to transfer a treasury position from one fund to another or from one grant to another.

For more information, see also Differentiation Terms.

**Key Features**

This app provides the following key features:

You can transfer positions to another account assignment, such as a fund, grant, cost center, WBS element, functional area, or profit center for treasury positions. You can either execute the account assignment transfer as an internal transfer or as an external transfer:

Internal transfer

The usual way to perform an account assignment transfer for treasury positions is an internal transfer. During the internal account assignment transfer, the units/nominals are transferred from the source position to the target

position, including the position component values that are transferred proportionally by derived business transactions taking into account the transfer category of the target position management procedure. For more information, see also Transfer Category.

External transfer

If you treat the account assignment transfer as an external transfer, the transfer is executed in the same way as a sale from the source position and a purchase to the target position. In this case, the realized gains and losses are calculated. If the Calculate Accrued Interest indicator is set when the account assignment transfer is executed, accrued interest is also calculated.

You can also transfer partial positions.

You can enter the incoming or outgoing payment amounts in position currency.

**Customizing**

In the Customizing of Treasury and Risk Management, you must make the following settings:

Define Update Types and Assign Usages

Define the update types for the position outflow and the position inflow of the account assignment transfer and assign them to the Account Assignment Transfer usage.

Assign Update Types for Account Assignment Transfer

You must assign update types for the internal and for the external account assignment transfer in the Assign Update Types for Account Assignment Transfer Customizing activity that is available in the Customizing of the Transaction Manager under General Settings Accounting Account Assignment Transfer .

For the internal account assignment transfer, you must assign update types for both the position outflow and the position inflow.

For the external account assignment transfer, you must assign update types for the Main Flows and the Accrued Interest Flows:

For the Main Flows, you enter update types for the following cases:

Asset: Position Outflow

Asset: Position Inflow

Liability: Position Outflow

Liability: Position Inflow

For the Accrued Interest Flows, you enter update types for the following cases:

Asset: Position Outflow

Asset: Position Inflow

Liability: Position Outflow

Liability: Position Inflow

You also must choose the exchange rate type for currency conversions.

Set Effects of Update Types on Position Components

**Procedure**

- 1. Open the Account Assignment Transfer app.
- 2. By choosing one or more product groups, you can select the positions for these groups.

In addition to selecting the product groups, you can use the general selections to select the individual positions.

- 3. Enter the selection criteria for the positions to be transferred:


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

OTC Transactions [MM, FX, OTC Derivatives, TF Transactions]

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

- 4. Enter the key date for the position transfer. By default, the current date is entered in this field.
- 5. Set the External Transfer indicator, if you want to execute the transfer like a sale from the source position and a purchase in the target position. In this case, the realized profits and losses (and accrued interests if the Calculate Accrued Interest indicator is set) are calculated. The following indicators are available for the external account assignment transfer:

You can set the Key Date Is Month End indicator. If you selected this indicator and if the relevant date is the last day of the month, that date is regarded as the month end for corresponding interest calculation methods.

The Calculate Accrued Interest indicator, controls whether to calculate accrued interest for the transfer posting.

If the indicator is set, the system calculates accrued interest. This applies to interest-bearing instruments, such as bonds and also money market transactions or interest rate swaps.

The Including Key Date indicator controls whether or not the key date is within the time period in question.

The indicators are set by default. You can change the default setting.

- 6. Specify the concrete values for the differentiation terms of the target positions if they apply to all the selected positions.
- 7. All the selected positions are displayed on the following screen. On this screen, you can exclude other positions from being transferred. You can also change the nominal amount or specify whether only a partial position is transferred.
- 8. Choose Execute. The system displays a list of all the selected positions with their status and indicates whether the positions were successfully transferred. To view any error messages, click on the status icon. To display the posting log, choose Messages and Log.


**Note:**

We recommend that you first execute a test run. The system then displays the transfer log for the test run. Choose Back and execute the update run.

Reversing the Account Assignment Transfer

Use the Reverse Account Assignment Transfer to reverse an account assignment transfer.

###### Example: Fund Transfer for a Fixed-Term Deposit

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Account Assignment Transfer > Example: Fund Transfer for a Fixed-Term Deposit | L5 | trm01 p.59 | loio `85de30e6081b4d9ab1fc99583fe85610` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/85de30e6081b4d9ab1fc99583fe85610.html?locale=en-US)

You have created a fixed-term deposit for fund A on 01/01 amounting to USD 10,000. On 12/31 at the end of the term, you expect to receive an interest payment of 4 % (USD 400) in addition to the repayment. On 06/30, fund A requires a premature payment of USD 2,000. Fund B can provide the amount and a payment of USD 1,990 is agreed upon.

**Activities**

On the SAP Easy Access Transaction Manager Special Functions from Public Sector Fund Transfer Execute Fund Transfer.

Enter the transaction number, company code, the key date of 07/01, and target fund B.

The transaction is displayed on the following screen. Change the nominal amount to USD 2,000 and the amount in position currency to USD 1,990. Execute the transfer.

To display the transaction cash flow, execute transaction Flow List (TPM13). The transfer covers the following flows:

|Fund A|Clear|1990$|
|---|---|---|
|Fund B|Post|1990$|
|Fund A|Incoming accrued interest|40$|
|Fund B|Outgoing accrued interest|40$|


The derived business transaction covers the following flows:

|Fund A|Translation purchase value|2000$|
|---|---|---|
|Fund A|Price losses|10$|
|Fund B|Translation negative purchase value|2000$|
|Fund B|Price gains|10$|


The accrued interest corresponds to the proportional interest revenue of 4 percent, based on USD 2,000 for six months. Fund B needs to pay the accrued interest into fund A. Fund A transfers the share of the fixed-term deposit to fund B at a price below the book value, resulting in a price loss for fund A. The system displays corresponding price gains for fund B. The transfer made for the company code therefore does not affect the profit and loss statement.

##### Investment Pools and Investment Pool Participants

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Investment Pools and Investment Pool Participants | L4 | trm01 p.60 | loio `7521593b112f4938b5baf1e1d203d0b4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7521593b112f4938b5baf1e1d203d0b4.html?locale=en-US)

Investment pools that are established at institutions, such as universities, are used to manage cash donations or other assets. The revenue earned from the investment of these funds represents a secure and long-term financial source (for research projects or scholarships, for example). If there are many investment pool participants at an institution, they are often grouped in investment pools. Grouping reduces administrative work and its associated costs, and the greater amounts of investment result in higher yields.

To have a share in an investment pool, an investment pool participant purchases pool certificates. The pool certificates held by a participant confirm the investment pool share. The value of the investment pool is determined periodically on selected key dates, such as the end of the month. The price for each certificate is also determined. An investment pool participant can only buy or sell certificates on these key dates.

In the Transaction Manager, the investment pool certificates are mapped using securities from the Investment Certificate product category. The participants and the investment pools are entered in the master data. An investment pool is characterized by its company code and securities ID number. An investment pool participant is characterized by the company code, fund, and grant (optional).

The Fund and Grant are account assignment objects in the Public Sector Management component.

See also: Fund and Grant

The involvement of a participant in an investment pool is mapped in the system by the purchase of an investment pool certificate and its mirrored issue. If there are only a few investment pool participants at an institution, you can enter the corresponding transactions manually. For a greater number of investment pool participants, the transactions can be generated automatically. In this case, you specify for each investment pool participant the amounts that are to be invested in the pools.

###### Editing Additional Fund Data for Investment Pool Participants

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Investment Pools and Investment Pool Participants > Editing Additional Fund Data for Investment Pool Participants | L5 | trm01 p.61 | loio `39114d5a60d54a56a10edd6cd99435cc` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/39114d5a60d54a56a10edd6cd99435cc.html?locale=en-US)

**Prerequisites**

In Public Sector Management, you have created a fund and a grant, where applicable, representing the investment pool participants.

You have created a securities account with the category asset securities account for the relevant company code. To do this, on the SAP Easy Access Treasury and Risk Management Transaction Manager Securities Master Data

Securities Account Edit Securities Account. (TRS_SEC_ACC)

You have created investment pools on the SAP Easy Access Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Master Data Edit Investment Pool Master Data. (TPM89).

**Context**

In this activity, you define and edit additional fund data for investment pool participants. You also specify the pools in which the investment pool participants can invest.

**Note:**

An investment pool participant is represented in the system using the combination of company code, fund, and grant. You only specify the grant if the Grants Management component is activated and if you want the positions in the Transaction Manager to be differentiated by grant.

**Procedure**

- 1. On the SAP Easy Access Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Master Data Investment Pool Participants: Edit Additional Fund Data. (TPM85)
- 2. In the dialog structure, select Additional Fund Data for Investment Pool Participants, choose New Entries, and specify the company code and the description of the investment pool participant for the relevant fund.
- 3. Select the securities account to be used for the transactions of the investment pool participants. The business partner defined as the depository bank for this securities account is used as the counterparty of the investment pool participant transaction.


**Note:**

If you want to use a separate securities account position for each investment pool participant, you first need to create a securities account for each participant. If you want to use a common securities account for multiple investment pool participants, it is not possible to see at the securities account level how many investment pool certificates belong to each pool participant. In both cases, you can use the fund and grant to differentiate the positions by their investment pool participants. To view this information, on the SAP Easy Access screen, choose Treasury and Risk Management

Transaction Manager Information System Reports Position Position List. (Overview of Subledger Positions TPM12)

4. In the dialog structure, select Pools Permitted for Investment Pool Participants and then choose New Entries. For the selected periods, specify the investment pools in which a participant can invest. You have the following options:

If you specify a date under Entry Effective From and Entry Effective To, the investment pool participant can only invest in the pool within this period.

If you only specify a date for Entry Effective From, the investment pool participant can invest in the pool from this date onwards. It is open-ended.

If you only specify a date for Entry Valid To, the investment pool participant can invest in the pool until the specified date.

If you do not specify a date under Entry Valid From or Valid To, the investment pool participant can invest in the pool at any time.

**Note:**

You can enter multiple periods for investment pool participants and investment pools.

###### Editing Investment Pool Master Data

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Investment Pools and Investment Pool Participants > Editing Investment Pool Master Data | L5 | trm01 p.62 | loio `dc6cf0e8f1e14e5cae8a70e6b84820ec` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dc6cf0e8f1e14e5cae8a70e6b84820ec.html?locale=en-US)

**Use**

Investment pools and investment pool participants are represented in the system by a fund or a combination of a fund and grant. The investment made by a pool participant is mapped in the system by the purchase of investment pool certificates and their issue. The investment pool certificate needs to be created as a security in the Investment Certificate category.

An investment pool is defined using the Company Code and Security Class.

The investment pool master data is required to create participant investments in an investment pool.

**Prerequisites**

You have specified a security class for the product category Investment Certificate. To do this, on the SAP Easy Access screen, choose Treasury and Risk Management Securities Master Data Display and Edit Class Data . (FWZZ)

If you want the system to generate issue transactions in addition to the investment transactions for the investment pool participants, you first need to create a securities account with the category Liabilities Securities Account for the selected company code. To do this, on the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Securities Master Data Securities Account Edit Securities Account . (TRS_SEC_ACC)

In Public Sector Management, you have created a Fund and a Grant, where applicable, that represent an investment pool.

**Procedure**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Master Data Edit Investment Pool Master Data .
- 2. Specify the Investment Pool ID Number and the Company Code.
- 3. You can also enter the number of decimal places to be used when the system generates the investment transactions and the investment pool transactions. A maximum number of five decimal places is permitted.


When purchasing investment pool certificates, the system always rounds down. Sales, however, are always rounded up. This ensures the the amount to be invested is never exceeded and the amount to be withdrawn is reached.

**Example:**

Investment pool participant A intends to invest an amount of 1,000 at a rate of 22.50 for the pool certificate. The number of units is calculated as 44.44444 recurring. By rounding to three decimal places, 44.444 units are purchased at a value of 999.99, whilst 44.445 units are sold at a value of 1,000.01.

- 4. Set the indicator Create Issues if you want the system to generate a mirrored investment pool issue transaction at the same time it generates an investment transaction. Liabilities positions are generated for the investment pool which can then be used to map payments from investment pool income to the investment pool participants, for example. If you have not set the indicator, the system generates the investment transactions without the corresponding investment pool issue transaction.


**Recommendation:**

We recommend that you do not set the indicator if you are managing the investment pool positions and the payments made to the investment pool participants in an external system.

You need to make the following settings if you have set the Create Issues indicator:

- 1. The system uses the account assignment elements Fund and Grant to post all the flows belonging to the investment pool to the Public Sector Management component. You must make an entry for the Fund. You only need to enter a Grant if you have activated Grants Management and if you want to differentiate positions in the Transaction Manager by Grant.
- 2. Under Liability Securities Account, specify the securities account to be used for the issue transactions in the investment pool. This securities account position reflects the number of certificates that are issued to the investment pool participants by the investment pool. The system uses the Business Partner specified as the depository bank as the counterparty for the issue transaction.
- 3. Under Gen.Val.Class Issue, choose the general valuation class valid for the investment pool issue transactions. Based on the general valuation class, the system derives the special valuation classes for the investment pool position for each valuation area.

###### Edit Investments

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Investment Pools and Investment Pool Participants > Edit Investments | L5 | trm01 p.63 | loio `b32b5a5a22d5426b9aaa96c3a9b7213e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b32b5a5a22d5426b9aaa96c3a9b7213e.html?locale=en-US)

**Use**

You can use this function to enter changes to investments made by investment pool participants in one or more investment pools. The system uses the data to automatically generate the required securities transactions in one final processing step.

The system maps increased pool investments using certificates purchased by the investment pool participants and certificates issued by the investment pool. A decrease in investment share is mapped using the sale of certificates by the investment pool participants and the simultaneous repurchase of certificates by the investment pool.

**Note:**

The transactions for the issue or repurchase of certificates by the investment pool are only generated if the corresponding indicator has been set in the investment pool master data.

**Prerequisites**

You have defined investment pools. To do this, on the SAP Easy Access screen, choose Treasury and Risk Management

Transaction Manager Special Functions from Public Sector Investment Pool Master Data Edit Investment Pool Master Data (TPM89).

You have created the investment pool participants and assigned them to investment pools. To do this, on the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector

Investment Pool Master Data Edit Additional Fund Data for Investment Pool Participants (TPM85).


**Activities**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Back Office Edit Investments (TPM90).
- 2. Choose New Entries and enter the following data:

Company code

Position value date

ID number of the investment pool in which investments are to be made

Fund and possibly the grant that characterize the investment pool participant

- 3. In the field Payment Amount in Investment Pool Currency, you define the amount by which the investment is to be changed. The amount should always be positive.
- 4. Make an entry in the Purchase/Sale field:

Choose Purchase if the investment increases.

Choose Sale if there is a reduction in the investment.

- 5. Enter the position number if more than one entry is required for the position value date, investment pool, and investment pool participants combined. This may occur if transactions generated for a particular entry are reversed and new transactions are to be created.


**Note:**

The investment pool currency is always the same as the issue currency of the investment pool ID number.

You should use a consecutive number for the position, which is unique for each combination of position value date, investment pool, and investment pool participant. For existing table entries for which securities transactions were not yet generated, you can change the fields "Payment Amount in Investment Pool Currency" and "Purchase/Sale". If you want to make changes to one of the other fields, you need to delete the table entry and enter a new one.

For table entries for which the system has already generated securities transactions, the "Transaction Created" field is selected. It is not possible to delete or change these table entries.

###### Generation of Transactions for Investment Pool Participants

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Investment Pools and Investment Pool Participants > Generation of Transactions for Investment Pool Participants | L5 | trm01 p.64 | loio `4b9e1ffa5c594ceab9b8ffc0d25b2ebf` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b9e1ffa5c594ceab9b8ffc0d25b2ebf.html?locale=en-US)

**Use**

With this function, the system automatically generates transactions for investment pool participants. These transactions are based on the data that you entered under Edit Investments.

The payment amount defined in the data for each investment pool and investment pool participant is used together with the security price in the system to determine the traded number of investment pool certificates.

**Note:**

When purchasing investment pool certificates, the system always rounds down. Sales, however, are always rounded up. This ensures the the amount to be invested is never exceeded and the amount to be withdrawn is reached. The number of decimal places contained in the number of units is defined in the investment pool master data.

**Example:**

Investment pool participant A intends to invest an amount of 1,000 at a rate of 22.50 for the pool certificate. The number of units is calculated as 44.44444 recurring. By rounding to three decimal places, 44.444 units are purchased at a value of 999.99, whilst 44.445 units are sold at a value of 1,000.01.

**Prerequisites**

You have entered the data for the changes in the pool investments. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Back Office

Edit Investments (TPM90).

You have defined the key date security price for each investment pool ID number by choosing Treasury and Risk Management Transaction Manager Securities Environment Market Data Manual Market Data Entry Enter Security Prices .

When you determine the security price, the exchange and price type are irrelevant.

You have defined the transaction types used to automatically generate the investment pool participant transactions. In Customizing for the Transaction Manager, choose Securities Transaction Management Special Functions from Public Sector Assign Transaction Types for Investment Pool Participant Transactions .

**Activities**

- 1. Choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Back Office Generate Transactions for Investment Pool Participants (TPM86).
- 2. Specify the company code and position value date for which transactions should be generated.
- 3. You can use the selection criteria to restrict the transactions to be created.
- 4. Enter the transaction calculation date or payment date if it is different to the position value date.
- 5. You can simulate the generation of the transactions first by setting the Test Run indicator.
- 6. Choose Execute.


Result

The system generates the transactions. The results log displays the numbers of the generated transactions, the security prices used, and the number of units calculated.

Reversal Functions

Generated transactions can be reversed individually or together:

Individual Reversal

If you want to reverse only an individual transaction, you can use the reversal function in the Transaction Management area by choosing Treasury and Risk Management Transaction Manager Securities Trading Edit Financial Transaction .

Reversal of Multiple Transactions

To reverse multiple transactions, choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Back Office Reverse Transactions for Investment Pool Participants (TPM87).

Specify the company code and position value date of the transactions to be reversed, as well as the reason for reversal.

You can use the selection criteria to restrict the transactions to be reversed.

**Note:**

- 1. You can use the BAdI Investment Pool Participant Transactions (BADI_TPM_TRANSACTION_TRE) to change the data of the transactions to be created.

You can implement the method IF_TPM_TRANSACTION_TRE~FILL_COMM_FIELDS to change the fields that are contained (number of units, for example) in two corresponding transactions (purchase and issue or sale and repurchase).

You can use the methods IF_TPM_TRANSACTION_TRE~FILL_ENDOWMENT_FIELDS and IF_TPM_TRANSACTION_TRE~FILL_POOL_FIELDS to change the fields in the participant transaction and the investment pool transaction (portfolio, internal reference, for example.)

The BAdI is available in Customizing for the Transaction Manager under Securities Transaction Management Special Functions from Public Sector BAdI: Investment Pool Participant Transactions .

- 2. Once the system has generated the investment pool transactions and participant transactions, you can edit them manually (change or reverse them, for example). Make sure that the data remains consistent in the corresponding transactions. You can check this using the overview of transactions of investment pool participants; Choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool


Information System Overview of Transactions of Investment Pool Participants (TPM88).

###### Overview of Transactions of Investment Pool Participants

> **Path:** Treasury and Risk Management > Integration Scenarios > Integration with SAP Public Sector Management (PSM) > Investment Pools and Investment Pool Participants > Overview of Transactions of Investment Pool Participants | L5 | trm01 p.66 | loio `99688f8f29e04069b1c0cf894c2c8f4d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/99688f8f29e04069b1c0cf894c2c8f4d.html?locale=en-US)

**Use**

With this report you can gain an overview of the investment pool transactions and the participant transactions that have been generated.

**Prerequisites**

You have entered the data for the changes to the pool investments using the function Edit Investments (TPM90).

You have generated transactions for the investment pool and participants using the function Generate Transactions for Investment Pool Participants (TPM86).

**Activities**

1. To call the function in the application menu, choose Treasury and Risk Management Transaction Manager Special Functions from Public Sector Investment Pool Information System Overview of Transactions of Investment Pool

Participants (TPM88). 2.

- 2. The transactions to be displayed can be restricted using the selection criteria or by using the following three indicators:

Display Active Transactions

The system displays all the investment pool transactions and participant transactions that have not been reversed.

Display Inactive Transactions

The system displays transactions for the investment pool and its participants that have been completely reversed.

Display Transactions to Be Created

The system displays data that you entered using the Edit Investments function (TPM90), but for which transactions have not yet been generated.

- 3. Choose Execute. The transaction list appears. From this list, you can branch to the individual transactions. In addition to the transaction data, you can display other information:


**Note:**

The BAdI BADI_TPM_TRANSACTION_TRE, which can be used to change data when you generate transactions for the investment pool and participants, is not taken into account when you display the data for transactions that have not yet been created.

The symbols for Transactions Created and Transactions Not Created show whether the transactions already exist or whether they still need to be generated. The transactions that have not yet been created are only displayed in the overview list if you have selected the Display Transactions to Be Created indicator on the selection screen.

Differences in Central Data

This field uses the symbols No Differences and Differences Exist to show whether there are any differences between the transaction for the investment pool participants and the corresponding transaction for the investment pool, with regard to the number of units, price, payment amount, payment currency, activity category, or active status.

Differences may arise from transactions being manually changed or reversed after generation. Such differences need to be checked and eliminated since it is most likely that they have arisen due to incorrect entries during manual processing.

**Note:**

This overview displays only the transactions that were generated by the system based on the data defined under Edit Investments (TPM90).

Securities transactions that you create manually for investment pools or investment pool participants are not listed here. To gain an overview of all the securities transactions, both manually entered and automatically generated, use collective processing by choosing Transaction Manager Securities Back Office Collective Processing Securities .

#### Automatic Payment Reason Determination – Securities Account and Transaction Management

> **Path:** Treasury and Risk Management > Integration Scenarios > Automatic Payment Reason Determination – Securities Account and Transaction Management | L3 | trm01 p.68 | loio `33fb0be890084ff5b120319ce4a10632` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/33fb0be890084ff5b120319ce4a10632.html?locale=en-US)

App ID: F7595

With Payment Reason Determination – Securities Account and Transaction Management app, you can display, change and create substitution rules for payment reason field of the financial transactions. The rules are executed during processing of financial transactions, whereby you can fill in the value of payment reason from the predefined derivation rules.

You can determine payment reason for the following areas:

transaction management

securities account management

For more information about the payment reason for the purpose code, see Payment Reason for Storing Purpose Codes.

**Prerequisites**

You have defined all required payment reasons using the Define Payment Reasons configuration activity available in your configuration environment.

**Key Features**

This configuration app uses the framework provided by the Manage Substitution/Validation Rules app.

The app provides the following key features:

Create Substitution Rules

Change Rules

Display Rules

Transport Rules

Developer Extensibility

With the Substitution/Validation Logs app, you can view the detailed logs for substitution rule execution at runtime. However, before you do this, you need to activate logging using the Set Substitution/Validation Logs app.

**Fields Available for Precondition**

The fields available for defining preconditions are different for securities account management and transaction management. This enables you to substitute values of target fields depending on attributes specific to the business context.

Target Fields

You can define substitution rules to fill the following field:

Payment Reason

**Apply Rules at Runtime**

At runtime, the derivation process is triggered at several times, when the cash flow is updated with the payment details:

When business users create a financial transaction.

If business users change the financial transaction.

Using Planned Record Update (FWUP) app.

**Note:**

The securities account must have valid payment details. For more information, see Bank Data tab in Manage Securities Accounts app.

The substitution rules you defined apply automatically as follows:

Substitution: Derives, replaces, or clears values for the payment reason defined in the substitution rules. The substitutions take place at the time of data entry with no system messages. The automatic substitution doesn't overwrite payment reason that you manually enter for individual flows.

**Note:**

As a configuration expert for the Treasury and Risk Management area, to access the Payment Reason Determination – Security Account and Transaction Management app from the SAP Fiori launchpad, you must have a business role that contains the TRM - Configuration for Payment Reason Substitution Rules (SAP_FIN_BC_TRM_PRSR_CONF_PC) business

catalog. SAP delivers the Configuration Expert - Business Process Configuration (SAP_BR_BPC_EXPERT) business role template for your reference.

**Supported Device Types**

Desktop

Tablet

