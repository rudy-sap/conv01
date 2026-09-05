# Risk Management > Basics > Financial Objects - SAP TRM Knowledge Base (branch split)

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

##### Financial Objects

> **Path:** Treasury and Risk Management > Risk Management > Basics > Financial Objects | L4 | trm02 p.11 | loio `4e397c8effbc3c44e10000000a15822b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e397c8effbc3c44e10000000a15822b.html?locale=en-US)

**Definition**

If you want to analyze financial transactions and positions in the risk analyzers of Treasury and Risk Management, you have to create a financial object for each object that you want to analyze. Additional information that is required for risk analysis is also entered into the financial object.

You can create financial objects for the following objects:

Money market transactions

Foreign exchange transactions

OTC derivatives

Securities and listed derivatives

Security transactions

Class positions in securities accounts

Class positions in position accounts

Lot-based positions in position accounts

Trade finance transactions

Loans (CML)

Treasury positions and subpositions (not relevant for Default Risk Limit)

Operating exposures: Exposure positions for the risk category Currency Risk (not relevant for Default Risk Limit)

Generic transactions

Bank accounts

Bank accounts

Current accounts (BCA)

Collaterals

Only relevant within Credit Risk Analyzer for the attributable amount determination:

For the primary or secondary risk-reducing effect of the collateral to be taken into account in the attributable amount determination, a financial object for the single-transaction-related collateral item is required. Once you have saved the collateral, if you then choose Financial Object in the application toolbar, you branch directly to financial object creation.

**Caution:**

Note that in the function for maintaining financial objects for single-transaction-related collateral, the system, when selecting data, does not take into account the validity end date stored in the financial object.

For more information, see also Collateral and Processing Single-Transaction-Related Collateral

**Integration**

Financial objects can be created immediately when creating financial data or exposure data. To be able to do so, you need to activate automatic financial object integration. Moreover, you can store derivation strategies that can be used to fill the fields of the financial objects automatically. For more information, see also Automatic Integration of Financial Objects.

**Structure**

A financial object contains a variety of data that is sorted on different tabs:

General Part: General data (such as the product type) for the financial object.

Analysis (RM): Data that is relevant for Market Risk Analysis and Asset Liability Management

Default Risk Limit: Data for the default risk limit

External Key Figures:

External key figures represent data that you can store in the SAP system for further calculations. They take the form of amounts, quantities, or percentages. The key figures themselves aren’t calculated in the system. The external key figures are used in the Default Risk and Limit System (for determining the settlement amount) and in Asset Liability Management.

As a prerequisite, you must define the customer-specific key figure categories (in the namespaces Y or Z) that you need for customer-specific key figures. You can find this setting in Customizing under Treasury and Risk Management Credit Risk Analyzer Basic Settings Master Data .

Additional Data: Object number for financial transactions

**Related Information**

Automatic Integration of Financial Objects Displaying Financial Objects Process Financial Objects Process Financial Objects of Treasury Positions/Subpositions

###### Displaying Financial Objects

> **Path:** Treasury and Risk Management > Risk Management > Basics > Financial Objects > Displaying Financial Objects | L5 | trm02 p.13 | loio `1902c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1902c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

This report provides a technical overview (transaction number, user who created the data, change information) of the transactions in the datapool.

**Procedure**

- 1. Call the function Display Financial Objects (transaction RMFD).
- 2. Choose a Valuation Area.
- 3. On the General Selections tab, define the base portfolio that you want to examine by entering the view, the portfolio hierarchy and, where applicable, a portfolio hierarchy node.
- 4. In the data group Selection of Active or Inactive Financial objects, mark the financial objects to be included in the selection.
- 5. You can further restrict the selection of financial objects by specifying their assigned characteristic values on the Characteristics tab.
- 6. If you only want to count the selected financial objects, choose Count Financial Objects in the application toolbar on the selection screen.
- 7. Choose to display the technical financial object data.


**Result**

The information is displayed in an ALV list grouped according to object category and transaction number.

You can navigate through the portfolio hierarchy in the left-hand part of the screen.

You can branch to the transaction master data by double-clicking the transactions.

You can mark a financial object in the list and navigate the financial object using the   Financial Objectbutton. The following data are displayed:

General Data

General data (such as the product type) for the financial object.

Analysis (RM)

Data that is relevant for Market Risk Analysis and Asset Liability Management

Analysis indicator (required entry field)

Balance sheet indicator expresses for the transaction on which side of the balance sheet it is based.

Valuation rule

The valuation rule controls how the transaction is treated in the individual risk evaluations. For Accounting Analyzer purposes, this setting is not needed.

You can define precisely the validity of the financial object by entering the validity period.

In the Analysis Characteristics data group, you define/see the characteristic values for the financial object.

**Note:**

Generated Analysis Structure

You can specify the sequence of the RM analysis characteristics and how they appear on the screen by choosing Basic Analyzer Settings Reporting Characteristics Define Analysis Structure . You can only enter values for hidden characteristics by using derivation strategies. If a characteristic is hidden by linking, the other characteristics in the linking will also be hidden.

If you want to know how characteristics are derived when you save and run checks on the financial object, choose Extras Characteristic Derivation Log . You then obtain a list that shows you the source fields with the corresponding target fields.

Static Analaysis Structure

For the static analysis structure, SAP delivers the analysis characteristics. These characteristics are your evaluation criteria. The following characteristics are predefined:

Business Partner Number

Trader

Contract Type

Product Category

Product Type

Security Class

Securities Account

Futures Account

Currency

Portfolio

Country/Region Key

Financial Transaction

Loans Contract Number

Exposure Position ID

Characteristics

Your portfolio hierarchies must be based on the characteristics belonging to the static analysis structure.

If you have activated the static and generated analysis structures in Customizing, you can use the Analysis Structure field to switch between the characteristics for the different structures.

Master Data

Here you see the financial transaction in the Transaction Manager.

Additional Data

When you create a financial object in the system, it is automatically assigned a financial object number. You can see this number on this tab.

###### Process Financial Objects

> **Path:** Treasury and Risk Management > Risk Management > Basics > Financial Objects > Process Financial Objects | L5 | trm02 p.15 | loio `4e397d09ffbc3c44e10000000a15822b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e397d09ffbc3c44e10000000a15822b.html?locale=en-US)

**Use**

With this function, you can create, change, display, deactivate, and reverse financial objects for all kinds of financial transactions, exposure positions, generic transactions, bank accounts, current accounts, and collaterals.

**Tip:**

To process the financial objects for treasury positions and subposition, you use the Process Financial Objects of Treasury Positions/Subpositions function (transaction JBO1).

**Integration**

Financial objects can be created immediately when creating financial data or exposure data. To be able to do so, you need to activate automatic financial object integration. Moreover, you can store derivation strategies that can be used to fill the fields of the financial objects automatically. For more information, see also Automatic Integration of Financial Objects.

- 1. In the SAP Easy Access menu, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer / Portfolio Analyzer / Credit Risk Analyzer / Accounting Analyzer Tools

Financial Object (transaction JBDO).

- 2. Enter the Company Code.
- 3. Select the kind of financial object you are interested in and enter a key in the corresponding field that uniquely identifies the fiancial object. The key can be one of the following:


Financial transaction number for derivative, money market, FX, and security transactions

Securities class ID number and securities account of a securities account class position

Securities class ID number and futures account of a class position in a futures account

Securities class ID number and futures account, lot-generating transaction number, or the ID of the lot for lot-based position in futures account

Contract number for loans

Internal or external number of a generic transaction

Position ID of the exposure position

Bank country/region key, bank key, account number, and currency for bank accounts

Account number for current accounts

- 4. Choose the action , that you want to execute. The following actions are available:


|Action|Remarks|
|---|---|
||Ususally the financial objetcs are generated automatically, but you can also create the financial objects manually.|
||You can change generate or manually entered data.|
|  Display|You can display the financial object data.|
| Deactivate| |
| Reverse| |


The following data are displayed:

General Data

General data (such as the product type) for the financial object.

Analysis (RM)

Data that is relevant for Market Risk Analysis and Asset Liability Management

Analysis indicator (required entry field)

Balance sheet indicator expresses for the transaction on which side of the balance sheet it is based.

Valuation rule

The valuation rule controls how the transaction is treated in the individual risk evaluations. For Accounting Analyzer purposes, this setting is not needed.

You can define precisely the validity of the financial object by entering the validity period.

In the Analysis Characteristics data group, you define/see the characteristic values for the financial object.

**Note:**

Generated Analysis Structure

You can specify the sequence of the RM analysis characteristics and how they appear on the screen by choosing Basic Analyzer Settings Reporting Characteristics Define Analysis Structure . You can only enter values for hidden characteristics by using derivation strategies. If a characteristic is hidden by linking, the other characteristics in the linking will also be hidden.

If you want to know how characteristics are derived when you save and run checks on the financial object, choose Extras Characteristic Derivation Log . You then obtain a list that shows you

the source fields with the corresponding target fields.

Static Analaysis Structure

For the static analysis structure, SAP delivers the analysis characteristics. These characteristics are your evaluation criteria. The following characteristics are predefined:

Business Partner Number

Trader

Contract Type

Product Category

Product Type

Security Class

Securities Account

Futures Account

Currency

Portfolio

Country/Region Key

Financial Transaction

Loans Contract Number

Exposure Position ID

Characteristics

Your portfolio hierarchies must be based on the characteristics belonging to the static analysis structure.

If you have activated the static and generated analysis structures in Customizing, you can use the Analysis Structure field to switch between the characteristics for the different structures.

Master Data

Here you see the financial transaction in the Transaction Manager.

Additional Data

When you create a financial object in the system, it is automatically assigned a financial object number. You can see this number on this tab.

- 5. Choose Financial Object Create .

When you create a financial object, it is automatically assigned a financial object number.

- 6. In the master data, under General Part (represented by the original key), enter the following data:


Enter the source system.

For securities transactions, FX transactions, and transactions with listed derivatives (single transactions only), choose Additional Data to enter the reference price required for calculating the trading terms contribution within the Single Transaction Costing component.

- 7. Save your entries.


**Note:**

When you create financial objects for loan transactions, cash flows are generated (commitment cash flow and possibly rollover cash flows). Cash flow generation is triggered when you save the financial object. Before saving, make sure that you have entered all the information for the loan transaction.

For information about how to delete financial objects for transactions, loans, and accounts, see Deleting Financial Objects for Variable Transacts Without Archiving, Deleting Financial Objects for Loans Without Archiving, and Deleting Financial Objects for Accounts Without Archiving.

**Related Information**

Analysis Structure

###### Process Financial Objects of Treasury Positions/Subpositions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Financial Objects > Process Financial Objects of Treasury Positions/Subpositions | L5 | trm02 p.18 | loio `c4980c9e12934a13b3133e2fed766c35` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c4980c9e12934a13b3133e2fed766c35.html?locale=en-US)

**Use**

With this function, you can create, change, display, deactivate, and reverse financial objects for subledger positions (= treasury positions) and subpositions (P-HA). The positions assigned to a hedging relationship in P-HA (as hedged items or as a hedging instrument) are managed in subpositions in position management, whereby a distinction is made between the free-standing subpositions and the designated subpositions. A free-standing subposition is generated for the positions by assigning a hedged item and a hedging instrument to a hedging relationship. If designation then occurs later on, the free-standing subpositions are reduced by the designated part, and a subposition is generated for the designated part.

**Activities**

- 1. In the SAP Easy Access menu, choose SAP Treasury and Risk Management Accounting Analyzer/ Market Risk Analyzer / Tools Process Financial Objects of Treasury Positions/Subpositions .
- 2. Choose the object type of the financial object (Position or Subposition).
- 3. You can use the fixed and variable differentiation values and also the hedging relationship details as selection criteria.
- 4. Choose one of the following functions:

Create Financial Object

Change Financial Object

Display Financial Object

Deactivate Financial Object

Reverse Financial Object.

- 5. You obtain a list containing all positions or subpositions according to your selection criteria.

Choose the one that you want to work on.

- 6. The following data is displayed:


**Note:**

If you have activated the static and generated analysis structures in Customizing, you can use the Analysis Structure field to switch between the data for the different structures.

General Data

Enter the source system here.

Analysis (RM)

Analysis indicator

You need to set this indicator for all financial objects to be taken into account when evaluations are run in Risk Analysis.

Analysis indicator (required entry field)

Balance sheet indicator expresses for the transaction on which side of the balance sheet it is based.

Valuation rule

The valuation rule controls how the transaction is treated in the individual risk evaluations. For Accounting Analyzer purposes, this setting is not needed.

You can define precisely the validity of the financial object by entering the validity period.

In the Analysis Characteristics data group, you define/see the characteristic values for the financial object.

**Note:**

Generated Analysis Structure

You can specify the sequence of the RM analysis characteristics and how they appear on the screen by choosing Basic Analyzer Settings Reporting Characteristics Define Analysis Structure . You can only enter values for hidden characteristics by using derivation strategies. If a characteristic is hidden by linking, the other characteristics in the linking will also be hidden.

If you want to know how characteristics are derived when you save and run checks on the financial object, choose Extras Characteristic Derivation Log . You then obtain a list that shows you the source fields with the corresponding target fields.

Static Analaysis Structure

For the static analysis structure, SAP delivers the analysis characteristics. These characteristics are your evaluation criteria. The following characteristics are predefined:

Business Partner Number

Trader

Contract Type

Product Category

Product Type

Security Class

Securities Account

Futures Account

Currency

Portfolio

Country/Region Key

Financial Transaction

Loans Contract Number

Exposure Position ID

Characteristics

Your portfolio hierarchies must be based on the characteristics belonging to the static analysis structure.

If you have activated the static and generated analysis structures in Customizing, you can use the Analysis Structure field to switch between the characteristics for the different structures.

Master Data

Here you see the subledger position/subposition in the Transaction Manager.

The position is displayed using the SAP List Viewer for SAP GUI (Classic).

The list provides you with the differentiation characteristics (such as company code, valuation area, valuation class, transaction number, ID number, or securities account) and the values of the position components for the key date for the position.

The following list functions are available:

Display Flows

You can use this function to branch to the list of position flows for the subledger position / subpostion in the Subledger Cash Flow

Display Securities Account Group

Display Position Management Procedure

Display Position Indicator

Securities: Detail View

The detail view displays the differentiations and position components in the position currency and valuation currency including the price/rate in position currency and exchange rate for the selected securities position.

Display Effective Interest Rate Used

Additional Data

When you create a financial object in the system, it is automatically assigned a financial object number. You can see this number on this tab.

- 7. Save your entries.

###### Automatic Integration of Financial Objects

> **Path:** Treasury and Risk Management > Risk Management > Basics > Financial Objects > Automatic Integration of Financial Objects | L5 | trm02 p.20 | loio `4e397dc7ffbc3c44e10000000a15822b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e397dc7ffbc3c44e10000000a15822b.html?locale=en-US)

**Use**

With the function for the automatic integration of financial objects (FO Integration), you can enter financial object data manually when you create the master data, or you can let the system derive the financial object data. You can use this function when you create data for the following financial instruments:

Money market transactions

Foreign exchange transactions

OTC derivatives

Securities and listed derivatives

Security transactions

Class positions in securities accounts

Class positions in position accounts

Lot-based positions in position accounts

Trade finance transactions

Loans (CML)

Treasury positions and subpositions (not relevant for Default Risk Limit)

Operating exposures: Exposure positions for the risk category Currency Risk (not relevant for Default Risk Limit)

Generic transactions

Bank accounts

Bank accounts

Current accounts (BCA)

The Analysis Parameters and Default Risk Limit tabs (not for futures account class position) are created for each company code.

**Prerequisites**

To be able to use financial object integration, you need to have set the FO Integration Active / Component Active indicator for each transaction type in Customizing under Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings Automatic Integration of Financial Objects in Transaction Master Data Activate/Deactivate Automatic Financial Object Integration .

The relevant parts of the financial object (analysis parameters, analysis, default risk limit, and external key figures) are created as tabs for the activated components. If at least one component is activated, the general part of the financial object and the tab for the external key figures are activated automatically.

**Note:**

You can activate the automatic integration of financial objects on the basis of the company code and product type. For Treasury positions and subpositions, you also need to specify for which valuation area you want to activate the automatic integration of financial objects.

If you want the system to derive the financial object data automatically instead of the user entering the data manually, you have to define derivation strategies. Derivation strategies describe what information needs to be derived from the transaction master data.

**Note:**

If you use the generated and static analysis structures, you must define derivation rules for the generated and static analysis structures under Define Derivation Strategy (MRA) for each financial instrument.

For the static analysis structure, most derivation rules are defined by system, thereby simplifying the entry of derivation rules. The following list shows you the fields for which you can define derivation rules to fill the field automatically:

Analysis Active indicator

You can define a derivation rule to fill the field automatically.

Summarization rule

The system uses the summarization rule to aggregate the balances of accounts, fully disbursed loans, and variable transactions in the database. This field doesn’t appear on the screen for any of the other transactions.

You can define a derivation rule to fill the field automatically.

Balance sheet indicator

You can define a derivation rule to fill the field automatically.

Valuation rule

The valuation rule controls how the transaction is treated in the individual risk evaluations.

You can define a derivation rule to fill the field automatically.

You can define precisely the validity of the financial object by entering the validity period.

You can define a derivation rule to fill the field automatically.

Business Partner

You can define a derivation rule to fill the field automatically.

Trader

Automatically derived by the system from the corresponding field in the financial transaction data.

Contract Type

Automatically derived by the system from the corresponding field in the financial transaction data.

Prod. Category

Automatically derived by the system from the corresponding field in the financial transaction data.

Product Type

Automatically derived by the system from the corresponding field in the financial transaction data.

For bank accounts and current acoounts (BCA), the product type is derived from the settings made in the Customizing activity Define Product Types for Bank Accounts. If you defined more than one product type for bank accounts or current accounts, you must define a derivation strategy.

Security ID

Automatically derived by the system from the corresponding field in the financial transaction data.

Sec. Acct

Automatically derived by the system from the corresponding field in the financial transaction data.

Futures Account

Automatically derived by the system from the corresponding field in the financial transaction data.

Currency

You can define a derivation rule to fill the field automatically.

Portfolio

Automatically derived by the system from the corresponding field in the financial transaction data.

Country/Region

You can define a derivation rule to fill the field automatically.

Transaction

Automatically derived by the system from the corresponding field in the financial transaction data.

Contract Number

Automatically derived by the system from the corresponding field in the financial transaction data.

Position ID

Automatically derived by the system from the corresponding field in the financial transaction data.

Characteristics

You can define a derivation rule to fill the field automatically.

**Features**

If you have activated automatic financial object integration for a particular component, when you maintain the transaction data for that component, the system provides online entry screens in which the financial object data can be entered or derived using the relevant derivation steps from Customizing.

**Note:**

The following information applies to the transaction formsoption spreadandcurrency option. You generate two financial objects for these transactions. There’s therefore no interface for these transactions, and the system doesn’t check the data before it’s saved.

When you save the transaction, the system checks the information in the various parts of the financial object. If one of the financial object parts contains errors, the system reacts in one of the following ways, depending on the setting made in Customizing:

The master data can’t be saved, so neither the transaction itself nor the financial object with the components activated for automatic FO integration are saved on the database. This is the case if the function for the automatic integration of financial objects is fully active.

The master data can be saved, but the financial object part that contains errors is not saved. If all the components activated for automatic FO integration contain invalid data, the general part of the financial object isn’t saved on the database either. This is the case if the function for the automatic integration of financial objects is partially active.

The following table reflects system behavior using the example of the transaction category Generic Transaction:

- Case 1: Automatic FO integration is active only for component X.


|Customizing Settings|Is the data saved on the database?| | | | |
|---|---|---|---|---|---|
|Automatic FO integration is activated|System reaction when there are errors|Status of the Data|Generic Transactions|General Part of FO|Part for Component X in FO|
|Component X|Data can’t be saved (completely active)|X data is correct|Yes|Yes|Yes|
|Component X|Data can also be saved without the data of the part for component X (partially active)|X data is correct|Yes|Yes|Yes|
|Component X|Data can’t be saved (completely active)|X data contains errors|No|No|No|
|Component X|Data can also be saved without the data of the part for component X (partially active)|X data contains errors|Yes|No|No|


**Case 2: Automatic FO integration is active for component Y as well.**

|Customizing Settings|Is the data saved on the database?| | | | | |
|---|---|---|---|---|---|---|
|Automatic FO integration is activated|System reaction when there are errors|Status of the Data|Generic Transactions|General Part of FO|Part for Component X in FO|Part for component Y in FO|
|Component Y|Data can’t be saved (completely active)|Y data contains errors|No|No|No|No|
|Component Y|Data can also be saved without the data of the part for component Y (partially active)|Y data contains errors|Yes|Yes|Yes|No|
|Component X|Data can’t be saved (completely active)|X data contains errors|No|No|No|No|
|Component X|Data can also be saved without the data of the part for component X (partially active)|X data contains errors|Yes|Yes|No|Yes|


Consequences

If financial object integration is active for a transaction category, this changes the way in which the system derives characteristics for the Market Risk Analysis and Default Risk and Limit System components. See Editing Characteristic Derivations.

###### Control Parameters (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Financial Objects > Control Parameters | L5 | trm02 p.25 | loio `5509da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5509da531198434de10000000a174cb4.html?locale=en-US)

**Use**

In the Default Risk and Limit System, the default risk rule and the limit product group are derived. If you use integrated financial object maintenance, the system also derives the setting for the Counterparty/Issuer Risk Active” (SARAKT) indicator.

You define derivation strategies in Customizing. In the Default Risk and Limit System, a distinction is made between the following derivation strategies:

|Types|Customizing (Strategy Maintenance)|
|---|---|
|Type 1|... Basic Settings Derive Default Risk Control Parameters|
|Type 2|... Basic Settings Automatic Integration of Financial Objects in Transaction Master Data|


The system applies the following derivation types depending on the context:

Automatic Financial Object Integration

Type 2 derivation is used.

Mass Processing of Financial Objects

- Type 1 derivation is used.

- You access the mass processing of financial objects using type 1 derivation in Treasury and Risk Management by choosing Market Risk Analyzer Tools Reorganization Tools Financial Object Maintain Financial Objects

Edit Financial Objects . In the selection screen, transactions are hidden for which financial object integration is set to active. By choosing Selection Using FO Numbers, you can use type 1 derivation for all transactions.

Type 2 derivation is used.

- You access the mass processing of financial objects using type 2 derivation by choosing Tools Reorganization Tools Financial Object Financial Object Integration .




**Prerequisites**

To be able to define derivation strategies, you need authorization object J_B_KLCUS1. This is contained in authorization profile F_T_FTLM_ALL, which in turn belongs to profile J_B_ISB_ALL.

**Integration**

If the derivation strategy is activated, the control parameters for TR-TM transactions and BCA accounts are derived by means of the strategy only. Derivation using the derivation strategy takes place during external data transfer (type 1), manual creation of the financial object (type 1), and integrated financial object maintenance (type 2).

**Note:**

For a detailed description of the derivation tool, refer to the documentation of the Profitability Analysis (CO-PA) component: Derivation Types .

