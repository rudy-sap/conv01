# Transaction Manager > Currency Changeover - SAP TRM Knowledge Base (branch split)

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

#### Currency Changeover

> **Path:** Treasury and Risk Management > Transaction Manager > Currency Changeover | L3 | trm10 p.210 | loio `5aa7b3cc2bbb4e068f7f65a9d00dc96b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5aa7b3cc2bbb4e068f7f65a9d00dc96b.html?locale=en-US)

In Treasury and Risk Management, currencies are important in many ways. If the currency of a specific country/region changes to the euro (EUR), for example, this change can also affect your financial transactions, treasury positions, and the issue currency of securities in the expiring currency. For example, if the maturity date of a financial transaction in an expiring currency is after the end date of the validity of the expiring currency, you either must change the transaction currency of the financial transaction and the position currency of the related positions or terminate the financial transaction.

If the issue currency of securities changes, all flows and documents in the issue currency/position currency that refer to those securities must also be translated. The system performs both steps automatically as part of the currency changeover.

**Note:**

The functions of the currency changeover in Treasury and Risk Management are independent of the local currency changeover. You can change the currency of financial transactions/positions before or after the local currency changeover, or even if you do not have to perform a local currency changeover.

If you have to execute a local currency changeover, during this changeover process also data in Treasury and Risk Management are affected if a valuation area exists with valuation currency equal to the local currency. In this case, some settings in the configuration as well as all amounts in the expiring valuation currency must be translated to the new valuation currency.

The functions for local currency changeover are available with the SAP S/4HANA Currency Changeover add-on for SAP S/4HANA 2021, SAP S/4HANA 2022, and SAP S/4HANA 2023. For more information, see also the documentation of the addon SAP S/4HANA Currency Changeover on SAP Help Portal.

**Availability**

The currency changeover can be performed for the following kinds of financial transaction/position:

OTC transactions/positions of the following product categories:

Money Market - Product categories 510, 520, 530, 540, 550, 560, and 580

Foreign Exchange - Product category 600

Interest Rate Derivative - Product categories 610, 620, and 630

OTC Derivatives - Product category 760, using FX option, FX barrier options, and interest rate derivatives as underlyings (FX basket options and FX compound options are not supported)

Trade Finance - Product categories 850 and 860

Security positions of product categories 010, 020, and 040

**Note:**

The currency changeover cannot be performed for a financial transaction/position in the following cases:

Financial transactions/positions that are currently being processed in another currency changeover

Financial transactions/positions with position-changing business transactions before the key date of the currency changeover that have not been fixed and posted

Financial transactions/positions with fixed business transactions after the key date of the currency changeover

Financial transactions/positions with fixed business transactions with a TRL date before the key date of the currency changeover and a posting date after the key date of the currency changeover

Financial transactions/position with outdated derived business transactions

Financial transactions used as hedges in the Hedge Management for Net Open Exposures process

Hedge management of FX risks in the expiring old currency ends before the key date of the currency changeover or at the latest with the expiry date of the old currency.

If you have long-term FX transactions (FX forwards, FX options) in the expiring currency, you must terminate them.

Financial transactions/positions that are used in hedge accounting

In this case, you must first dedesignate the hedging relationships. Then you can perform the currency changeover for the financial transactions. If hedging-relevant FX risks exist after the currency changeover, you can create new hedging relationships.

Financial transactions/positions that are assigned to a facility

In this case, you must first perform the currency changeover for the facilities and then the currency changeover for the assigned financial transactions.

Financial transactions/positions in an external account

**Prerequisites**

Customizing

Make the following settings for the currency changeover in Customizing for Treasury and Risk Management:

During the currency changeover, the system creates backup transactions for all financial transactions affected by the currency changeover. The backup transaction saves the data of the financial transaction before the currency changeover. In the Customizing activity Define Number Ranges under Transaction Manager Money Market Transaction

Management Transaction Types , you can define a specific number range for the backup transactions (number range object: FTA_GSART Financial Transaction) for each company code. In this way, you can use a separate number range for the backup transaction so that the numbering of new financial transactions is ongoing and is not disrupted by the newly

created backup transactions. The translated financial transactions and their corresponding backup transactions are linked by a reference of type EUR. This enables you to reach the backup transaction from the translated financial transaction.

**Note:**

The system also creates copies of the positions before the currency translation, but this data is managed internally and is not visible or linked from the translated positions.

Define the following update types in the Customizing activity Define and Assign Update Types.

CC_INC Currency Changeover: Increase Nominal/Quantity

CC_DEC Currency Changeover: Decrease Nominal/Quantity

- CC_DP01 Currency Changeover: Clear Debit Amount

- CC_DP02 Currency Changeover: Post Debit Amount


- CC_CP01 Currency Changeover: Clear Credit Amount

- CC_CP02 Currency Changeover: Post Credit Amount


Assign the update types to the usage Currency Changeover.

In the Customizing activity Assign Update Types for Currency Changeover, you must assign the new update types in the following way:

CC_INC and CC_DEC must be assigned under Update Types for Currency Changeover Transaction.

[figure TRM10-F078 - CC_INC and CC_DEC must be assigned under Update Types for Currency Changeover Transaction.]

The update types CC_DP01, CC_DP02, CC_CP01, and CC_CP02 must be assigned for each relevant account symbol under Update Types for Position Transfers. The update types are used to translate the book values on the accounts in financial accounting from the old currency to the new currency.

[figure TRM10-F079 - The update types CC_DP01, CC_DP02, CC_CP01, and CC_CP02 must be assigned for each relevant account symbol under Update Types for Position Transfers. The update types are used to translate the book values on the accounts in financial accounting from the old currency to the new currency.]

In the Customizing activity Indicate Update Types as Relevant to Posting, mark the following update types as relevant for posting:

- CC_DP01 Currency Changeover: Clear Debit Amount

- CC_DP02 Currency Changeover: Post Debit Amount


- CC_CP01 Currency Changeover: Clear Credit Amount

- CC_CP02 Currency Changeover: Post Credit Amount


In the Customizing activity Assign Update Types for Derived Business Transactions, you must assign update types for all position management procedures on the Reconciliation tab. These update types are required for the currency changeover if differences occur that need to be corrected. For example, the amounts of a financial transaction/position differ slightly in a (unchanged) valuation currency before and after the currency changeover.

Market Data

You can enter the FX conversion rate relevant for the currency changeover for the key date of the changeover in the Enter FX Spot

Rates app (app ID: TMDFX) using the rate type that you want to apply for the currency changeover. However, it is also possible to enter the FX conversion rate only manually in the master data of the currency changeover in the Manage Currency Changeovers function.

Standing Instructions: Payment Details

You can enter the standing instructions for payment details in the business partner data for the new currency.

Authorizations

To be able to use one of the apps, the user must have been granted authorization for the transaction codes using the following authorization objects:

F_T_TRANSB Treasury: Transaction Authorization

S_TCODE Transaction Code Check at Transaction Start

For the Manage Currency Changeovers app, in addition the granted authorization for the authorization object T_CURR_MNT Manage Currency Changeovers is checked. This authorization object contains the following fields and values:

Field: ACTVT Activity

- 01 Create

- 02 Change

- 03 Display


06 Delete

For the Execute Currency Changeover and Reverse Currency Changeover apps, the user must have authorization for the affected company codes and in addition the granted authorization for the following authorization objects are checked:

T_DEAP_DP Authorization for Securities Account

T_DEAP_PD Authorization for Product/Transaction Types

**Currency Changeover Process**

[figure TRM10-F080 - Create and Activate Currency Changeover]

Create and Activate Currency Changeover

Create the currency changeover in the Manage Currency Changeovers function. If the data is complete and has been checked, you can activate the currency changeover.

- 1. Run the Manage Currency Changeovers function (TPM_CCO_MANAGE).


- a. Choose Create.
- b. Select the expiring currency in the Old Currency field.


- c. Select the new currency.
- d. Enter the key date for the currency changeover.
- e. Enter a description for the currency changeover.
- f. Enter the number range for the backup transactions.
- g. Enter the relevant exchange rate type. The system reads the exchange rate from the market data table. You can change the exchange rate manually.
- h. Save your entries. The system now assigns an automatically generated number as the currency changeover ID.


- 2. Check and correct the currency changeover data entered.
- 3. Activate the currency changeover.


For more information, see also Manage Currency Changeovers.

Activities Before Currency Changeover

You must prepare the financial transactions/positions for which you want to perform the currency changeover. The following activities must be performed:

For the financial transactions/positions that are relevant for the currency changeover, you must fix and post positionchanging business transactions before the key date of the currency changeover. If the posting date of one of these business transactions is after the key date of the currency changeover, the financial transaction cannot be processed by the Execute Currency Changeover function.

For the financial transactions/positions that are relevant for the currency changeover, you must reverse fixed and posted position-changing business transactions after the key date of the currency changeover.

Update the derived business transactions for the financial transactions/positions that are relevant for the currency changeover.

Financial transactions used as hedges in the Hedge Management for Net Open Exposures process.

Hedge management of FX risks in the expiring old currency ends before the key date of the currency changeover or at the latest with the expiry date of the old currency.

If you have long-term FX transactions (FX forwards, FX options) in the expiring currency, you must terminate them.

If you also want to perform the currency changeover for financial transaction currently used as hedging instruments in hedging relationships, you must dedesignate the hedging relationships before the key date of the currency changeover.

Execute Currency Changeover

You execute the currency changeover using the Execute Currency Changeover function (TPM_CCO_EXECUTE). You can run the function several times for the same currency changeover. In such cases, you perform the currency changeover only for some of the relevant financial transactions/positions each time. This is particularly relevant if you want to change the currency of financial transactions that are assigned to a facility, for example. In this case, you first perform the currency changeover for the facilities and then for the assigned financial transactions.

- 1. Run the Execute Currency Changeover function (TPM_CCO_EXECUTE).
- 2. Select the currency changeover ID.


Both product groups are selected. You can deselect a product group and use the fields under General Selections to restrict the amount of financial transactions included in the currency changeover.

**Note:**

If you are using facilities, you must first perform the currency changeover for the facilities and afterward for the financial transactions assigned to the facilities.

- 3. Choose Execute.

- a. The system selects all financial transactions/positions, security classes, and security positions according to the master data of the currency changeover and the selection criteria entered.
- b. The system creates a copy of the selected financial transactions and saves them as new objects with a new transaction number in the backup tables (Number Range for Backup). The translated financial transactions and the corresponding backup transactions are linked by a reference of type EUR. This enables you to reach the backup transaction from the translated financial transaction. After the currency changeover, the backup transactions gets the status Replaced.
- c. For the product group OTC Transactions, a currency changeover transaction is created for each financial transaction, and it receives a (currency changeover transaction) group ID. The treasury positions belonging to a financial transaction are assigned to the same group ID.
- d. For the product group Securities, a currency changeover transaction is created for each class position in a securities account that is identified by the company code, security ID number, and securities account. All currency changeover transactions for the same security class ID number receive the same (currency changeover transaction) group ID. Therefore, all positions with the same security ID number are assigned to the same group ID.


- 4. The system displays the list of the selected currency changeover transactions.
- 5. You select the currency changeover transaction for which you want to perform the currency changeover. When you select a currency changeover transaction, all other currency changeover transactions with the same group ID are also selected. This ensures that the currency changeover is executed for all positions of a security class.
- 6. Choose Execute.


**Note:**

The system also creates copies of the positions before the currency changeover, but this data is managed internally and is not visible or linked from the translated positions.

a. Processing steps performed by the program for OTC currency changeover transactions:

- i. The system checks whether the financial transactions/positions fulfill all requirements for the currency changeover.
- ii. The system translates the following in the financial transaction data:

All amounts in the old currency

All FX rates

Forward rate and spot rate are translated on the basis of the translation ratios defined for the relevant currency pairs of the standard exchange rate type.

For example, the translation ratio for HRK/JPY is 1:100, and for EUR/JPY it is 1:1. If the forward rate for HRK/JPY is 0.5, the conversion to EUR/JPY is done using the formula 0.5/7.53*100. However, if there is no difference between the translation ratios, then the formula would be 0.5/7.53.

The swap rate is calculated from the translated forward rate and spot rate.

- iii. The system translates the position data.


- iv. After the financial transaction data and position data are translated, the system generates the currency changeover business transactions to do the following:

- 1. Generation of derived business transactions for the position transfer in Financial Accounting
- 2. Generation of derived business transactions for reconciliation of the position component values

Example:

A reconciliation flow is required, for example, if an amount in the new position currency EUR differs from the corresponding amount in valuation currency EUR. The reconciliation flow adjusts the amount in valuation currency.

- 3. Setting a lock on the position to prevent changes before the key date.


- v. The system updates the future cash flows for the financial transactions/positions based on the new data to recalculate the cash flow.
- vi. If, in Customizing, you made the setting for correspondence to be sent after a change is made to financial transaction data, the system triggers the creation of correspondence objects.


- b. Processing steps performed by the program for security currency changeover transactions:

- i. The system checks whether the security positions fulfill all requirements for the currency changeover.
- ii. The system translates master data of the securities (security class data) and securities account management.
- iii. The system translates position data.
- iv. After the position data and the security class data have been translated, the system generates the currency changeover business transactions to do the following:

- 1. Generation of derived business transactions for the position transfer in Financial Accounting.
- 2. Generation of derived business transactions for reconciliation of the position component values.
- 3. Setting a lock on the position to prevent changes before the key date.


- v. To recalculate the cash flows, the system updates the future cash flows for the financial transactions/positions based on the new data.


- c. The results list is displayed.


A posting log and messages are available using the Messages and Log button.

Also, you can see the flows of the currency changeover generated for each changed position by using the Treasury Position Flows - Classic app (app ID TPM13).

- 7. Repeat the execution of the currency changeover until you have changed the currency for all relevant financial transactions/positions.


**Note:**

If you have accidentally performed the currency changeover or many errors occurred, you can reverse the currency changeover using the Reverse Currency Changeover function.

If you need to reverse the currency changeover of facilities and their assigned financial transactions, you need to do so in the following order:

- a. Reverse the currency changeover of the assigned financial transactions.
- b. Reverse the currency changeover of the facilities.


The financial transactions data is restored and will look the same as before the currency changeover (retaining the same financial transaction number).

The previously created backup transaction is not deleted, and the reference also remains in the database, because it is only deleted logically (= set to status 3 Undone) and is no longer visible from the financial transaction (under Environment Object Links ). However, in the Collective Processing: References function (transaction TBRL), you can select references for all statuses and consequently you can still see the references there.

**Note:**

If you already processed the translated financial transactions after the currency changeover, it is no longer possible to reverse of the currency changeover.

Activities After Currency Changeover

Some data in financial transactions, security classes, and other related objects are not updated during the currency changeover. Therefore, you may need to perform some of the following activities:

Update reference interest rates in the conditions of financial transactions and security class data

The variable reference interest rates in conditions are not translated. You must create new conditions in financial transactions and security class data after the currency changeover.

Update fixing references

The fixing reference will not be translated for cross-currency interest rate swaps.

You must adjust the fixing reference after the currency changeover.

Update the payment details in the new currency

After currency changeover, when you change the financial transaction, either the system derives the default payment instruction for the new currency (for example, EUR) from the standing instructions, or you must enter the payment details manually.

Exchanges

The currency of the exchange must be changed manually for directly quoted securities.

In syndicated facilities, the currency of the sub lines are not translated. After the currency changeover, you can create a new sub line with the new currency and assign the new sub line to the facility transaction.

Update financial objects

After the operational side (financial transactions/treasury positions and security class data) have been updated using the Execute Currency Changeover function, the related financial objects must be updated as well. Please check whether you already have derivation rules or need derivation rules for the new currency. Then you can start the generation reports manually to trigger the derivation of the analysis characteristics and the limit characteristics. The following reports are available in the area menu of Treasury and Risk Management under Market Risk Analyzer Tools Reorganization Tools

Financial Object Integration to update financial objects of the changed financial transactions:


Generate Financial Objects for Financial Transactions (FTR_OPEN_TRTM_INIT)

Generate Financial Objects for Treasury Positions/Subpositions (AFO_AP_TRL_MMIG)

Generate Financial Objects for Class Positions in Securities Accounts (AFO_AP_POS1_MMIG)

Generate Financial Objects for Bank Accounts (AFO_AP_BACC_MMIG)

Use this function if you have bank accounts for which the currency has been changed.

If you defined limits on the expired currency, you can create new limits on the new currency as of the key date of the currency changeover. The following cases can apply:

The expired currency is not a limit characteristic.

In this case, you can either create new limits with internal and external limit amounts in the new currency (for example, EUR) or manually change the internal and external limit amounts and the currency in your existing limits in the Manage Limits app.

The expired currency is a limit characteristic.

In this case, you create new limits for the new currency if needed.

How to change the limit currency manually:

- 1. Open the Manage Limits app (app ID: TBL1).
- 2. On the Limits screen: Choose Limit Type, select the limit type you want to change, and then choose Edit.


In the next screen, position the cursor on the appropriate list entry and choose Choose.

On the Edit Limits for Limit Type xxx: Detail screen, you can edit the validity date (effective from and effective until) and the internal or external limit amounts for the selected limit type.

Adaptions in Market Risk Analyzer

Evaluation Currency in the Key Figure Definition of the Results Database

Adapt the evaluation currency in the definition of the key figures (which is time-dependent) using the Define Key Figures and Evaluation Procedures function (transaction AFWKF_RA). On the basis of the key date specified, the calculation is performed in the new evaluation currency.

Remove Obsolete Risk Factors in Classical Risk Hierarchy

You can remove any obsolete risk factors from the time-dependent risk hierarchy using the Maintain Risk Hierarchy function (transaction JBRR). However, the time dependency of the risk hierarchies means that you can still evaluate the 'old' results database data.

Evaluation Currency in Market Risk Key Figure Set

Adapt the evaluation currency and remove the obsolete risk currency from the risk factor set using the Manage Market Risk Key Figure Sets app (app ID AFWKF_SET). As evaluation currency is saved in run-specific tables and risk factors are created on the fly and stored in separate run-specific database tables old data can still be reported.

Set Currency Changeover to 'Completed'

After you have performed the currency changeover successfully for all relevant financial transactions/positions, you can set the status of the currency changeover to Completed in the Manage Currency Changeover app.

For more information, see also Manage Currency Changeovers.

##### Terms in Currency Changeover

> **Path:** Treasury and Risk Management > Transaction Manager > Currency Changeover > Terms in Currency Changeover | L4 | trm10 p.218 | loio `d72f49549d9d4264b4b9fff3ba1e452b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d72f49549d9d4264b4b9fff3ba1e452b.html?locale=en-US)

Currency changeover During a currency changeover, the system translates to the new currency all old currency amounts of financial transactions, their related positions, and security class data and the related securities

| |positions. You may need to perform a currency changeover for the following reasons: The currency of a specific country/region has changed to another currency, and you consequently need to change financial transactions in the old currency with terms later than the currency changeover key date. The issue currency of a security class has changed. You define the master data for a currency changeover in the Manage Currency Changeover app.|
|---|---|
|Status of a currency changeover|A currency changeover always has a status. The following statuses are available: Planned This status is set automatically when you create a new currency changeover in the Manage Currency Changeover app. Active Once you have entered all necessary data for the currency changeover correctly in the Manage Currency Changeover app, you set the status of the currency changeover manually to Active. Currency changeovers with this status can be performed. Completed After the currency changeover has been performed successfully, you can set its status manually to Completed. Obsolete If a currency changeover with the status Active is not performed or the currency changeover has been reversed, and the currency changeover is no longer required, you can set its status manually to Obsolete. This is the final status and it cannot be changed any more.|
|Currency changeover transaction|A currency changeover transaction is used to change the data of financial transaction data, security class data, and position data (including treasury ledger and quantity ledger data) during a currency changeover. For the product group OTC Transactions, a currency changeover transaction is created for each financial transaction. All related treasury positions are also assigned to the currency changeover transaction. For the product group Securities, a currency changeover transaction is created for each class position in a securities account (identified by company code, security ID number, and securities account). All positions related to this securities account class position are assigned to the currency changeover transaction.|
|Currency changeover transaction group ID|The currency changeover transaction group ID is derived automatically during a currency changeover and assigned to the|


| |currency changeover transaction. The group ID summarizes all currency changeover transactions that belong together and that must therefore be translated together. OTC Transactions Each currency changeover transaction gets its own currency changeover transaction group ID. Securities All currency changeover transactions with the same security class ID number receive the same currency changeover transaction group ID. Therefore, all positions with the same security ID number are assigned to the same currency changeover transaction group ID.|
|---|---|
|Currency changeover business transaction|A currency changeover business transaction is used to transfer positions in Financial Accounting by generating derived business transactions for the position transfer and for reconciliation flows. In addition, the currency changeover business transaction sets a lock on all financial transactions and positions involved to prevent changes being made before the key date.|


**Related Information**

Currency Changeover

##### Manage Currency Changeovers

> **Path:** Treasury and Risk Management > Transaction Manager > Currency Changeover > Manage Currency Changeovers | L4 | trm10 p.220 | loio `3e121378cba04339993d6b30ea932865` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3e121378cba04339993d6b30ea932865.html?locale=en-US)

Technical ID:TPM_CCO_MANAGE

With this function, you can create and process the master data for a currency changeover. The master data of the currency changeover comprises the following data:

Currency changeover ID

Old ourrency

New currency

Key date for the currency changeover

Exchange rate and exchange rate type

**Key Features**

You can use this app to do the following:

Create a currency changeover

When you create a currency changeover and save your entries, the currency changeover is saved with the status Planned.

Change a currency changeover

You can change a currency changeover that has the status Planned.

Delete a currency changeover

You can delete a currency changeover that has the status Planned.

Activate a currency changeover

Once you have entered all necessary data for the currency changeover correctly, you set the status of the currency changeover manually to Active.

Currency changeovers with this status can be performed.

Set a currency changeover to Completed

When a currency changeover has been performed successfully, you can set its status manually to Completed.

Set a currency changeover to Obsolete

If a currency changeover with the status Active is not performed or the currency changeover has been reversed, and the currency changeover is no longer required, you can set its status manually to Obsolete. This is the final status and it cannot be changed any more.

**Activities**

- 1. Create the currency changeover:

- a. Choose Create.
- b. Select the expiring currency in the Old Currency field.
- c. Select the new currency.
- d. Enter the key date for the currency changeover.
- e. Enter a description for the currency changeover.
- f. Enter the number range for the backup transactions.
- g. Enter the relevant exchange rate type. The system reads the exchange rate from the market data table. You can change the exchange rate manually.
- h. Save your entries. The system now assigns an automatically generated number as the currency changeover ID.


- 2. Check and correct the currency changeover data in the Change mode.
- 3. Activate the currency changeover.
- 4. When a currency changeover has been performed successfully you can set its status manually to Completed.
- 5. If a currency changeover with the status Active is not performed or the currency changeover has been reversed, and the currency changeover is no longer required, you can set its status manually to Obsolete. This is the final status and it cannot be changed any more.


**Related Information**

Currency Changeover Execute Currency Changeover

##### Execute Currency Changeover

> **Path:** Treasury and Risk Management > Transaction Manager > Currency Changeover > Execute Currency Changeover | L4 | trm10 p.221 | loio `5cfa99d644d147c5b663f0bffab906ac` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5cfa99d644d147c5b663f0bffab906ac.html?locale=en-US)

Technical ID: TPM_CCO_EXECUTE

With this function, you can perform a currency changeover.

You can run this function several times for the same currency changeover. For this, you perform the currency changeover for only some of the relevant financial transactions/positions each time. This is particularly relevant if you want to change the currency of financial transactions that are assigned to a facility, for example. In this case, you first need to perform the currency changeover for the facilities and then for the assigned financial transactions.

**Availability**

The currency changeover can be performed for the following kinds of financial transaction/position:

OTC transactions/positions of the following product categories:

Money Market - Product categories 510, 520, 530, 540, 550, 560, and 580

Foreign Exchange - Product category 600

Interest Rate Derivative - Product categories 610, 620, and 630

OTC Derivatives - Product category 760, using FX option, FX barrier options, and interest rate derivatives as underlyings (FX basket options and FX compound options are not supported)

Trade Finance - Product categories 850 and 860

Security positions of product categories 010, 020, and 040

**Note:**

The currency changeover cannot be performed for a financial transaction/position in the following cases:

Financial transactions/positions that are currently being processed in another currency changeover

Financial transactions/positions with position-changing business transactions before the key date of the currency changeover that have not been fixed and posted

Financial transactions/positions with fixed business transactions after the key date of the currency changeover

Financial transactions/positions with fixed business transactions with a TRL date before the key date of the currency changeover and a posting date after the key date of the currency changeover

Financial transactions/position with outdated derived business transactions

Financial transactions used as hedges in the Hedge Management for Net Open Exposures process

Hedge management of FX risks in the expiring old currency ends before the key date of the currency changeover or at the latest with the expiry date of the old currency.

If you have long-term FX transactions (FX forwards, FX options) in the expiring currency, you must terminate them.

Financial transactions/positions that are used in hedge accounting

In this case, you must first dedesignate the hedging relationships. Then you can perform the currency changeover for the financial transactions. If hedging-relevant FX risks exist after the currency changeover, you can create new hedging relationships.

Financial transactions/positions that are assigned to a facility

In this case, you must first perform the currency changeover for the facilities and then the currency changeover for the assigned financial transactions.

Financial transactions/positions in an external account

**Prerequisites**

Customizing

Make the following settings for the currency changeover in Customizing for Treasury and Risk Management:

During the currency changeover, the system creates backup transactions for all financial transactions affected by the currency changeover. The backup transaction saves the data of the financial transaction before the currency changeover. In the Customizing activity Define Number Ranges under Transaction Manager Money Market Transaction Management Transaction Types , you can define a specific number range for the backup transactions (number range object: FTA_GSART Financial Transaction) for each company code. In this way, you can use a separate number range for the backup transaction so that the numbering of new financial transactions is ongoing and is not disrupted by the newly created backup transactions. The translated financial transactions and their corresponding backup transactions are linked by a reference of type EUR. This enables you to reach the backup transaction from the translated financial transaction.

**Note:**

The system also creates copies of the positions before the currency translation, but this data is managed internally and is not visible or linked from the translated positions.

Define the following update types in the Customizing activity Define and Assign Update Types.

CC_INC Currency Changeover: Increase Nominal/Quantity

CC_DEC Currency Changeover: Decrease Nominal/Quantity

- CC_DP01 Currency Changeover: Clear Debit Amount

- CC_DP02 Currency Changeover: Post Debit Amount


- CC_CP01 Currency Changeover: Clear Credit Amount

- CC_CP02 Currency Changeover: Post Credit Amount


Assign the update types to the usage Currency Changeover.

In the Customizing activity Assign Update Types for Currency Changeover, you must assign the new update types in the following way:

CC_INC and CC_DEC must be assigned under Update Types for Currency Changeover Transaction.

[figure TRM10-F082 - CC_INC and CC_DEC must be assigned under Update Types for Currency Changeover Transaction.]

The update types CC_DP01, CC_DP02, CC_CP01, and CC_CP02 must be assigned for each relevant account symbol under Update Types for Position Transfers. The update types are used to translate the book values on the accounts in financial accounting from the old currency to the new currency.

[figure TRM10-F083]

In the Customizing activity Indicate Update Types as Relevant to Posting, mark the following update types as relevant for posting:

- CC_DP01 Currency Changeover: Clear Debit Amount

- CC_DP02 Currency Changeover: Post Debit Amount


- CC_CP01 Currency Changeover: Clear Credit Amount

- CC_CP02 Currency Changeover: Post Credit Amount


In the Customizing activity Assign Update Types for Derived Business Transactions, you must assign update types for all position management procedures on the Reconciliation tab. These update types are required for the currency changeover if differences occur that need to be corrected. For example, the amounts of a financial transaction/position differ slightly in a (unchanged) valuation currency before and after the currency changeover.

Market Data

You can enter the FX conversion rate relevant for the currency changeover for the key date of the changeover in the Enter FX Spot

Rates app (app ID: TMDFX) using the rate type that you want to apply for the currency changeover. However, it is also possible to enter the FX conversion rate only manually in the master data of the currency changeover in the Manage Currency Changeovers function.

Standing Instructions: Payment Details

You can enter the standing instructions for payment details in the business partner data for the new currency.

Create and Activate Currency Changeover

- 1. Run the Manage Currency Changeovers function (TPM_CCO_MANAGE).

- a. Choose Create.
- b. Select the expiring currency in the Old Currency field.
- c. Select the new currency.
- d. Enter the key date for the currency changeover.
- e. Enter a description for the currency changeover.
- f. Enter the number range for the backup transactions.
- g. Enter the relevant exchange rate type. The system reads the exchange rate from the market data table. You can change the exchange rate manually.
- h. Save your entries. The system now assigns an automatically generated number as the currency changeover ID.


- 2. Check and correct the currency changeover data entered.
- 3. Activate the currency changeover.


Activities Before Currency Changeover

You must prepare the financial transactions/positions for which you want to perform the currency changeover. The following activities must be performed:

For the financial transactions/positions that are relevant for the currency changeover, you must fix and post positionchanging business transactions before the key date of the currency changeover. If the posting date of one of these business transactions is after the key date of the currency changeover, the financial transaction cannot be processed by the Execute Currency Changeover function.

For the financial transactions/positions that are relevant for the currency changeover, you must reverse fixed and posted position-changing business transactions after the key date of the currency changeover.

Update the derived business transactions for the financial transactions/positions that are relevant for the currency changeover.

Financial transactions used as hedges in the Hedge Management for Net Open Exposures process.

Hedge management of FX risks in the expiring old currency ends before the key date of the currency changeover or at the latest with the expiry date of the old currency.

If you have long-term FX transactions (FX forwards, FX options) in the expiring currency, you must terminate them.

If you also want to perform the currency changeover for financial transaction currently used as hedging instruments in hedging relationships, you must dedesignate the hedging relationships before the key date of the currency changeover.

**Activities**

- 1. Run the Execute Currency Changeover function (TPM_CCO_EXECUTE).
- 2. Select the currency changeover ID.

Both product groups are selected. You can deselect a product group and use the fields under General Selections to restrict the amount of financial transactions included in the currency changeover.

- 3. Choose Execute.


**Note:**

If you are using facilities, you must first perform the currency changeover for the facilities and afterward for the financial transactions assigned to the facilities.

- a. The system selects all financial transactions/positions, security classes, and security positions according to the master data of the currency changeover and the selection criteria entered.
- b. The system creates a copy of the selected financial transactions and saves them as new objects with a new transaction number in the backup tables (Number Range for Backup). The translated financial transactions and the corresponding backup transactions are linked by a reference of type EUR. This enables you to reach the backup transaction from the translated financial transaction. After the currency changeover, the backup transactions gets the status Replaced.
- c. For the product group OTC Transactions, a currency changeover transaction is created for each financial transaction, and it receives a (currency changeover transaction) group ID. The treasury positions belonging to a financial transaction are assigned to the same group ID.


**Note:**

The system also creates copies of the positions before the currency changeover, but this data is managed internally and is not visible or linked from the translated positions.

d. For the product group Securities, a currency changeover transaction is created for each class position in a securities account that is identified by the company code, security ID number, and securities account. All currency changeover transactions for the same security class ID number receive the same (currency changeover transaction) group ID. Therefore, all positions with the same security ID number are assigned to the same group ID.

- 4. The system displays the list of the selected currency changeover transactions.
- 5. You select the currency changeover transaction for which you want to perform the currency changeover. When you select a currency changeover transaction, all other currency changeover transactions with the same group ID are also selected. This ensures that the currency changeover is executed for all positions of a security class.
- 6. Choose Execute.


- a. Processing steps performed by the program for OTC currency changeover transactions:

- i. The system checks whether the financial transactions/positions fulfill all requirements for the currency changeover.
- ii. The system translates the following in the financial transaction data:

All amounts in the old currency

All FX rates

Forward rate and spot rate are translated on the basis of the translation ratios defined for the relevant currency pairs of the standard exchange rate type.

For example, the translation ratio for HRK/JPY is 1:100, and for EUR/JPY it is 1:1. If the forward rate for HRK/JPY is 0.5, the conversion to EUR/JPY is done using the formula 0.5/7.53*100. However, if there is no difference between the translation ratios, then the formula would be 0.5/7.53.

The swap rate is calculated from the translated forward rate and spot rate.

- iii. The system translates the position data.
- iv. After the financial transaction data and position data are translated, the system generates the currency changeover business transactions to do the following:

- 1. Generation of derived business transactions for the position transfer in Financial Accounting
- 2. Generation of derived business transactions for reconciliation of the position component values

Example:

A reconciliation flow is required, for example, if an amount in the new position currency EUR differs from the corresponding amount in valuation currency EUR. The reconciliation flow adjusts the amount in valuation currency.

- 3. Setting a lock on the position to prevent changes before the key date.


- v. The system updates the future cash flows for the financial transactions/positions based on the new data to recalculate the cash flow.
- vi. If, in Customizing, you made the setting for correspondence to be sent after a change is made to financial transaction data, the system triggers the creation of correspondence objects.


- b. Processing steps performed by the program for security currency changeover transactions:


- i. The system checks whether the security positions fulfill all requirements for the currency changeover.
- ii. The system translates master data of the securities (security class data) and securities account management.


- iii. The system translates position data.
- iv. After the position data and the security class data have been translated, the system generates the currency changeover business transactions to do the following:

- 1. Generation of derived business transactions for the position transfer in Financial Accounting.
- 2. Generation of derived business transactions for reconciliation of the position component values.
- 3. Setting a lock on the position to prevent changes before the key date.


- v. To recalculate the cash flows, the system updates the future cash flows for the financial transactions/positions based on the new data.


- c. The results list is displayed.


A posting log and messages are available using the Messages and Log button.

Also, you can see the flows of the currency changeover generated for each changed position by using the Treasury Position Flows - Classic app (app ID TPM13).

- 7. Repeat the execution of the currency changeover until you have changed the currency for all relevant financial transactions/positions.


**Note:**

If you have accidentally performed the currency changeover or many errors occurred, you can reverse the currency changeover using the Reverse Currency Changeover function.

If you need to reverse the currency changeover of facilities and their assigned financial transactions, you need to do so in the following order:

- a. Reverse the currency changeover of the assigned financial transactions.
- b. Reverse the currency changeover of the facilities.


The financial transactions data is restored and will look the same as before the currency changeover (retaining the same financial transaction number).

The previously created backup transaction is not deleted, and the reference also remains in the database, because it is only deleted logically (= set to status 3 Undone) and is no longer visible from the financial transaction (under Environment Object Links ). However, in the Collective Processing: References function (transaction TBRL), you can select references for all statuses and consequently you can still see the references there.

**Note:**

If you already processed the translated financial transactions after the currency changeover, it is no longer possible to reverse of the currency changeover.

**After the Currency Changeover**

Manual activities after the currency changeover

Some data in financial transactions, security classes, and other related objects is not updated during the currency changeover. Therefore, you may need to perform some of the following manual activities:

Update reference interest rates in the conditions of financial transactions and security class data

The variable reference interest rates in conditions are not translated. You must create new conditions in financial transactions and security class data after the currency changeover.

Update fixing references

The fixing reference will not be translated for cross-currency interest rate swaps.

You must adjust the fixing reference after the currency changeover.

Update the payment details in the new currency

After currency changeover, when you change the financial transaction, either the system derives the default payment instruction for the new currency (for example, EUR) from the standing instructions, or you must enter the payment details manually.

Exchanges

The currency of the exchange must be changed manually for directly quoted securities.

In syndicated facilities, the currency of the sub lines are not translated. After the currency changeover, you can create a new sub line with the new currency and assign the new sub line to the facility transaction.

Update financial objects

After the operational side (financial transactions/treasury positions and security class data) have been updated using the Execute Currency Changeover function, the related financial objects must be updated as well. Please check whether you already have derivation rules or need derivation rules for the new currency. Then you can start the generation reports manually to trigger the derivation of the analysis characteristics and the limit characteristics. The following reports are available in the area menu of Treasury and Risk Management under Market Risk Analyzer Tools Reorganization Tools Financial Object Integration to update financial objects of the changed financial transactions:

Generate Financial Objects for Financial Transactions (FTR_OPEN_TRTM_INIT)

Generate Financial Objects for Treasury Positions/Subpositions (AFO_AP_TRL_MMIG)

Generate Financial Objects for Class Positions in Securities Accounts (AFO_AP_POS1_MMIG)

Generate Financial Objects for Bank Accounts (AFO_AP_BACC_MMIG)

Use this function if you have bank accounts for which the currency has been changed.

If you defined limits on the expired currency, you can create new limits on the new currency as of the key date of the currency changeover. The following cases can apply:

The expired currency is not a limit characteristic.

In this case, you can either create new limits with internal and external limit amounts in the new currency (for example, EUR) or manually change the internal and external limit amounts and the currency in your existing limits in the Manage Limits app.

The expired currency is a limit characteristic.

In this case, you create new limits for the new currency if needed.

How to change the limit currency manually:

- 1. Open the Manage Limits app (app ID: TBL1).
- 2. On the Limits screen: Choose Limit Type, select the limit type you want to change, and then choose Edit.


In the next screen, position the cursor on the appropriate list entry and choose Choose.

On the Edit Limits for Limit Type xxx: Detail screen, you can edit the validity date (effective from and effective until) and the internal or external limit amounts for the selected limit type.

Adaptions in Market Risk Analyzer

Evaluation Currency in the Key Figure Definition of the Results Database

Adapt the evaluation currency in the definition of the key figures (which is time-dependent) using the Define Key Figures and Evaluation Procedures function (transaction AFWKF_RA). On the basis of the key date specified, the calculation is performed in the new evaluation currency.

Remove Obsolete Risk Factors in Classical Risk Hierarchy

You can remove any obsolete risk factors from the time-dependent risk hierarchy using the Maintain Risk Hierarchy function (transaction JBRR). However, the time dependency of the risk hierarchies means that you can still evaluate the 'old' results database data.

Evaluation Currency in Market Risk Key Figure Set

Adapt the evaluation currency and remove the obsolete risk currency from the risk factor set using the Manage Market Risk Key Figure Sets app (app ID AFWKF_SET). As evaluation currency is saved in run-specific tables and risk factors are created on the fly and stored in separate run-specific database tables old data can still be reported.

After you have performed the currency changeover successfully for all relevant financial transactions/positions, you can set the status of the currency changeover to Completed in the Manage Currency Changeover app.

**Related Information**

Currency Changeover Manage Currency Changeovers Reverse Currency Changeover

##### Reverse Currency Changeover

> **Path:** Treasury and Risk Management > Transaction Manager > Currency Changeover > Reverse Currency Changeover | L4 | trm10 p.229 | loio `daa933a6a07f4433ad4c1f35290ca6ea` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/daa933a6a07f4433ad4c1f35290ca6ea.html?locale=en-US)

Technical ID: TPM_CCO_REVERSE

With this function, you can reverse a currency changeover.

**Note:**

If you already processed the translated financial transactions after the currency changeover, it is no longer possible to reverse of the currency changeover.

**Key Features**

If you need to reverse the currency changeover of facilities and their assigned financial transactions, you need to do so in the following order:

- 1. Reverse the currency changeover of the assigned financial transactions.
- 2. Reverse the currency changeover of the facilities.


The financial transactions data is restored and will look the same as before the currency changeover (retaining the same financial transaction number).

The previously created backup transaction is not deleted, and the reference also remains in the database, because it is only deleted logically (= set to status 3 Undone) and is no longer visible from the financial transaction (under Environment

Object Links ). However, in the Collective Processing: References function (transaction TBRL), you can select references for all statuses and consequently you can still see the references there.

**Related Information**

Currency Changeover

