# Exposure Management 2.0 - SAP TRM Knowledge Base (branch split)

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

### Exposure Management 2.0

> **Path:** Treasury and Risk Management > Exposure Management 2.0 | L2 | trm03 p.260 | loio `4c3af7c7b48f1ca9e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c3af7c7b48f1ca9e10000000a42189e.html?locale=en-US)

In Exposure Management 2.0, you collect future incoming and outgoing payments of your company that are associated with a currency risk. Either these payment flows are actual payments that already have a fixed amount and time settings or they are only

planned payments.

**Use**

Exposure Management 2.0 helps you identify the risks in payment flows and offers you integration with the following processes:

Hedge Accounting for Exposures (E-HA)

In Hedge Accounting for Exposures, you can hedge risks with a hedge plan using appropriate hedging transactions in Transaction Manager.

Hedge Management and Accounting of Net Open Exposures (FX Risk)

**Implementation Considerations**

SAP recommends that you use this component when you do business in countries/regions with a currency that differs from the currency of your country/region, particularly if the transactions entail committing to sales orders and purchase orders in advance, thereby exposing your business to fluctuations in the currency markets.

**Integration**

[figure TRM03-F375 - Integration of Exposure Management 2.0]

Integration of Exposure Management 2.0

Exposure Management 2.0 is a component of Treasury and Risk Management.

Apart from being able to enter raw exposures manually or by using BAPIs, you also have the option of transferring raw exposures automatically from Logistics to Exposure Management 2.0.

Exposure Management 2.0 analyzes the raw exposures entered and creates exposure positions for the different risks to make visible the risks that need to be hedged. Risks can be hedged, for example, with financial transactions such as Forward Exchange Transaction CAPS/FLOORS.

The following approach categories are available:

0 Without Prices

- 2 Fixed Prices


- 3 Variable Prices

- 4 Fixed and Variable Prices


For foreign exchange exposures with approach category 0, you can use the integration with Hedge Management. Here, you can combine exposure positions and the related hedging instruments in a hedging relationship and perform hedge accounting.

Furthermore, the exposure positions are integrated in the Market Risk Analyzer in Treasury and Risk Management, which enables you to calculate the net present values for the exposure positions.

**Features**

To portray exposure management processes, you can use the following functions:

Raw Exposures (transaction FTREX1)

You use this function to enter raw exposures. When the raw exposures are saved, the system starts the automatic analysis of the raw exposures for the risks associated with them.

When the raw exposures are released, the system creates exposure positions from the sub raw exposures. You can start the release of raw exposures manually or automatically. Furthermore, you can use a release workflow for the release process.

If the underlying transactions are changed, the raw exposures can be changed accordingly. The related exposure positions are updated automatically.

For more information, see Process Raw Exposures.

You can copy your exposure positions to a hedge plan in Hedge Accounting for Exposures (transactions FTREX12 or THMEX).

You can use the Exposure Management 2.0 as data source for the exposures in Hedge Management Cockpit. For more information, see also Hedge Management and Accounting of Net Open Exposures (FX Risk).

The following worklists are available:

Process Raw Exposures - Collective Processing (transaction FTREX2)

Process Exposure Positions (transaction FTREX12)

Display Exposure Position Flows (transaction FTREX13)

If you activate automatic financial object integration for operating exposures, you can use many functions provided by the Market Risk Analyzer, such as NPV calculation for exposure positions.

See also:

Integration of Operating Exposures in Market Risk Analysis

Net Present Value Calculations for Operating Exposures (calculation of the net present value of an exposure position)

You can use a BAPI for the business object BUS5990 TEXExposure to transfer raw exposures (FX exposures) from operative systems to Treasury and Risk Management.

Some BAdIs enable you to include enhancements within the Exposure Management 2.0 process.

Exposure positions and raw exposures can be archived. See also: Archiving Raw Exposures and Exposure Positions

**More Information**

For more information, see:

In Terms in Exposure Management 2.0, you will find definitions for some central terms in this documentation.

Exposure Lifecycle

Setting Up Exposure Management 2.0

Exposure Management 2.0: Transferring Exposures to E-HA

#### Terms in Exposure Management 2.0

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Terms in Exposure Management 2.0 | L3 | trm03 p.263 | loio `4c344cff5dbd4b41e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c344cff5dbd4b41e10000000a42189e.html?locale=en-US)

Here you get more details about terms used in Exposure Management 2.0.

|Term|Definition|
|---|---|
|Raw Exposures|Raw exposures are risk positions that result from your transactions and that you can either import using a BAPI from a source system, create automatically from Logistics, or enter manually in the system. Each raw exposure line item is analyzed with regard to the risks associated with it and split into sub raw exposures. Special Features for Variable Prices You can use a price table to enter variable prices. For each entry in the price table, a corresponding sub raw exposure is created. In sub raw exposures, the pricing date is applied as the due date. With variable price determination, the final price is not determined until the last price component has also been fixed. Before the first fixing date, the raw exposure memo record would not contain an amount and then it would subsequently only ever contain the amount that results proportionately from the prices already entered. This would mean that no sub raw exposure would be created for the currency risk or that the amount would be lower and would therefore not reflect the actual currency risk. However, you can enter a temporary price (status Not Fixed), in which case the price remains modifiable all the while you have not set it as fixed.|
|Exposure Positions|When you release raw exposures, the sub raw exposures are transformed into exposure positions. On the basis of the settings that you have made under Define Derivation Strategies for Exposure Fields, the system fills the fields of the exposure position and creates or changes exposure positions on the basis of the differentiation settings made. The exposure positions are integrated in the Market Risk Analyzer of Treasury and Risk Management, and you can calculate the net present values for existing exposure positions. Exposure Management 2.0 is also integrated with the following processes:|


|Term|Definition|
|---|---|
| |Hedge Management and Accounting of Net Open Exposures (FX Risk) process You can use the Exposure Management 2.0 as data source for the exposures. For more information, see also Exposures Hedge Accounting for Exposures (E-HA) You can assign exposure positions from within Exposure Management 2.0 to a hedge plan in Hedge Accounting for Exposures (E-HA). Or you can access the exposure positions from within Hedge Accounting for Exposures (EHA).|

#### Exposure Lifecycle

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Lifecycle | L3 | trm03 p.264 | loio `fdabdba0b2e740119d70e135e662710e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fdabdba0b2e740119d70e135e662710e.html?locale=en-US)

**Use**

You use the exposure lifecycle to specify the sequence of exposure types (forecasted transaction, firm commitment transaction, asset/liability transaction, or cash/stock transaction). The lifecycle represents the development of a risk within the business process, starting from Logistics or Exposure Management through to Hedge Accounting.

When exposure positions are transferred from Exposure Management to Hedge Accounting for Exposures (E-HA), the corresponding business types are derived from the exposure types, and the respective business activity types are determined from the exposure activity types.

**Prerequisites**

To be able to portray exposure lifecycles, you need to have made the following settings:

You have made the settings in the Customizing activity Define Exposure Activity Type.

You have made the settings in the Customizing activity Define Exposure Fields Derivation Strategy.

For the transfer to Hedge Accounting, you have assigned the transaction categories of Hedge Accounting to the exposure categories of Exposure Management and you have not set the Transfer Not Permitted indicator under Exposure Lifecycle Define Exposure- Categories .

Optional: In addition, you can activate the automatching function under Exposure Lifecycle Define Exposure Category Sequences .

**Features**

For the lifecycles of the relevant exposure risk types, you can specify different sequences of exposure types.

**Note:**

In Hedge Accounting for Exposures, only the exposure category Planned Transaction is relevant for the transfer from Exposure Management. The exposure categories Firm Commitment or Asset/Liability are used for Cash Management, for example.

Automatching: In the Customizing settings for the exposure lifecycle, you can specify whether automatching needs to be performed for a given risk type. When the automatching function is activated, the system determines the predecessor of a new (or changed) exposure position. The system determines the predecessor exposure position on the basis of differentiating properties that match. When a new exposure position is created, the predecessor exposure position is reduced by the value of the new exposure position. When the value of an exposure position is reduced, the value of the predecessor exposure position is increased proportionately.

**Note:**

Automatching only occurs when the predecessor exposure position comes first within the sequence but is not based on a line item from Logistics.

[figure TRM03-F376]

**More Information**

Transferring Exposures to Hedge Accounting for Exposures (E-HA)

#### Setting Up Exposure Management 2.0

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Setting Up Exposure Management 2.0 | L3 | trm03 p.265 | loio `4c3af628b48f1ca9e10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c3af628b48f1ca9e10000000a42189e.html?locale=en-US)

**Use**

Before you can use Exposure Management 2.0, you need to customize it.

**Procedure**

In the SAP Reference IMG, choose Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Exposure Management 2.0 . Here you find the following new IMG activities for setting up Exposure Management 2.0:

|IMG Activity|Procedure|Comments|
|---|---|---|
|Define Periods|Define the periods. The period together with the calendar year forms a differentiation criterion for exposure positions.|In this IMG activity, you can create periods for Exposure Management 2.0. The view used is from Financial Accounting, which means that you can also use the periods defined in Financial Accounting.|
|Define Exposure Activity Types|In this IMG activity, you create the activity types for your raw exposures. You use the activity types to manage the processing process for the raw exposures. You assign the foreign currency exposure type and the direction to the foreign exchange flow. You use the field selection control settings to structure the entry screens of the raw exposures for the header data and the line items. You specify whether the release of raw exposures is started automatically or manually.|If, for example, you select the setting Risk Not Relevant for the foreign exchange exposure type, the system does not generate a sub raw exposure for the currency risk in the case of the raw exposure line items of this activity type.|
|Define Product Types for Exposures|Define the product types for your exposure positions.| |
|Define Exposure Position Types|Here you define the exposure position types for your foreign currency exposures. You specify the differentiation criteria for your exposure positions. You assign the exposure position types to the sub raw exposures in the IMG activity Define Exposure Fields Derivation Strategy. Here, you can set the aggregation indicator.|See also: Differentiating Exposure Positions |
|Define Derivation Strategy for Exposure Fields|In this IMG activity, you define rules for filling exposure position fields that were not filled when the raw exposure was entered. One of the mandatory derivation parameters is the exposure position type.| |
|Define Exposure Origin|In this activity, you can define the origin of an external exposure.| |
|Setting for Free Attributes|This subnode contains steps for entering descriptors for short, medium, and long attributes as well as for date attributes in the raw exposures.|You can use these attributes, for example to assign the exposure position types.|
|Release|Assign User/Roles to Release Steps In this step, you can define the release procedure and release rules.| |


|IMG Activity|Procedure|Comments|
|---|---|---|
| |Assign Release Object to Release Procedure In this activity and the following activity, you can set up the release workflow. Assign Workflow and Sub-Workflow to Release Procedure| |
|Integration with Logistics|For the automatic integration with Logistics, you need to make settings in Exposure Management 2.0 as well as in Logistics. See also: Integration of Logistics with Treasury and Risk Management| |
|Archiving|Raw exposures and exposure positions can be archived. See also: Archiving Raw Exposures and Exposure Positions | |
|BAdIs|1. BAdI: Enhancement for Deriving Exposure Fields 2. BAdI: Export Enhancement for Position Data in Other Applications In this activity, you can implement the enhancement spot ES_TEX_POSITION with the Business Add-In (BAdI) BADI_TEX_POSITION_EXPORT to export the exposure position data to other applications or market places.| |


**Result**

Once you have customized your installation, you can now process exposure management data.

**More Information**

See the documentation on the IMG activities.

#### Exposure Management 2.0: Process

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Management 2.0: Process | L3 | trm03 p.267 | loio `1beb0a88f4984065a141d82df5c1ef4d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1beb0a88f4984065a141d82df5c1ef4d.html?locale=en-US)

**Use**

You enter your risk positions as raw exposures (transaction FTREX1). This starts the process for generating exposure positions. At the end of this process, you have all exposure positions that need to be hedged using appropriate hedging instruments and for which you can calculate the net present value using the automatic integration of financial objects in the Market Risk Analyzer.

Over time, the transactions on which the raw exposures are based change, and the raw exposures need to be changed accordingly. Once the attributes in the raw exposures have been changed, the relevant exposure positions are updated.

**Prerequisites**

Before you can use the functions in Exposure Management 2.0, you first have to make settings in Customizing. See also: Setting Up Exposure Management 2.0

You need to have authorization for the following authorization objects to use the functions in Exposure Management 2.0:

|Authorization Object|Permitted Activities|Description|
|---|---|---|
|T_TEX_POS Exposure Position|02 Change (change the attributes of a exposure position) 03 Display (display the exposure position) 59 Distribute (update exposure position in Hedge Management) 61 Export (export an exposure position in the marketplace or other BAPIsupported function)|The authorization object controls which activities are permitted for exposure positions in Exposure Management 2.0.|
|T_TEX_REXP Raw Exposure|01 Create or Generate (create raw exposures) 02 Change (change attributes of the raw exposure) 03 Display (display raw exposures) 06 Delete (delete raw exposure) Only possible when a raw exposure has not been released 43 Release Release the raw exposure to exposure positions.|The authorization object controls which activities are permitted for raw exposures in Exposure Management 2.0.|


**Process**

[figure TRM03-F377 - Exposure Management 2.0: Process]

Exposure Management 2.0: Process

- 1. Creating Raw Exposures

Raw exposures are risk positions that result from transactions that you can either import using a BAPI from a source system, create automatically from Logistics, or enter manually in the system.

When entering raw exposures, you first enter the header data of the raw exposure and then the line items.

See also: Editing Raw Exposures

- 2. Saving Raw Exposures


Once you save a raw exposure, the split engine is started.

The split engine analyzes each raw exposure line item with regard to the risks associated with it and splits them into sub raw exposures.

If a raw exposure line item contains an amount in a foreign currency, the system creates a sub raw exposure for the currency risk.

Special Features for Variable Prices

You can use a price table to enter variable prices.

For each entry in the price table, a corresponding sub raw exposure is created. In sub raw exposures, the pricing date is applied as the due date.

With variable price determination, the final price is not determined until the last price component has also been fixed. Before the first fixing date, the raw exposure memo record would not contain an amount and then it would subsequently only ever contain the amount that results proportionately from the prices already

entered. This would mean that no sub raw exposure would be created for the currency risk or that the amount would be lower and would therefore not reflect the actual currency risk. However, you can enter a temporary price (status Not Fixed), in which case the price remains modifiable all the while you have not set it as fixed. You can choose between the following settings:

- 3. Releasing Raw Exposures

With the release of a raw exposures, exposure positions are created on the basis of differentiation criteria.

Exposure positions are created and updated using flows that are written for each sub raw exposure.

This occurs in the following steps:

- a. Creation of a Transaction for Each Sub Raw Exposure

A transaction is created for each sub raw exposure. The transaction consists of the data from sub raw positions plus the data of the exposure position type and from any additional fields for which you have defined derivation strategies in the Customizing activity Define Derivation Strategies for Exposure Fields.

- b. Determining Differentiation Criteria

In the Customizing activity Define Exposure Position Types, you have specified differentiation criteria for each position type. The system uses these differentiation criteria to determine the relevant exposure position.

For more information, see Differentiating Exposure Positions

- c. Creating Exposure Positions


The system now checks whether an exposure position with these differentiation criteria already exists. If an appropriate exposure position is found, this position is updated with the flow. If no suitable exposure position is found, a new exposure position is created.

- 4. Over time, changes occur in the underlying transaction for the raw exposure (such as changes in quantity, prices being fixed, or a change in transaction type).


- a. Make the changes in the raw exposure and save your changes.

When you save, the sub raw exposure is updated.

- b. Release the raw exposure.


When you release the raw exposure, the exposure positions are updated:

For each new sub raw exposure, the system writes a flow with which to build the exposure position.

In the case of obsolete sub raw exposures, the system creates a clearing flow.

If the differentiation criteria have been changed (for example, a price was fixed on the price determination date, and the transaction category of the raw exposures has since been changed), the old exposure position is replaced by the new exposure position.

If the change does not affect the differentiation criteria (such as a change in quantity), the system writes a delta flow.

**Note:**

If the transaction category has changed for a subset of a raw exposure, you have to reduce the existing raw exposure by this subset and then create for the subset a new raw exposure with the new transaction category.

Automatic Position Matching

You can use this function for foreign exchange exposures.

Automatic position matching occurs during the creation of exposure positions once you have selected the global setting Automatic Position Matching in Customizing.

When you have selected this setting, you create a new raw exposure each time when the transaction type of an activity is changed, without affecting the preceding raw exposure. However, since an exposure position has already been created for the preceding raw exposure, this exposure position needs to be updated accordingly. This process is called automatic position matching.

Raw Exposure with the Transaction Type Planned Transaction

In the differentiation criteria, the system looks for an exposure position matching the sub raw exposure. If a suitable exposure position is found, it is increased by the sub raw exposure. If no suitable exposure position is found, a new exposure position is created. When the raw exposure is changed, the related exposure position is changed accordingly.

Raw Exposure with the Transaction Type Firm Commitment Transaction

As the transaction type of the raw exposure is always a differentiation criterion, the system creates new exposure positions when a raw exposure with this type is created (unless suitable exposure positions already exist, in which case they are updated). Furthermore, the suitable exposure positions with the transaction type Plannedd Transaction are automatically reduced by the amount of the sub raw exposure.

If the system cannot find a suitable exposure position to reduce, it nevertheless creates a new exposure position (or increases an existing suitable exposure position), but the raw exposure also appears in the function Edit Unmatched Transactions (transaction FTREX21). Here, you can manually assign the raw exposure to the preceding raw exposure.

Raw Exposure with the Transaction Type Asset/Liability Transaction

As the transaction type of the raw exposure is always a differentiation criterion, the system creates new exposure positions when a raw exposure with this type is created (unless suitable exposure positions already exist, in which case they are updated). Furthermore, the suitable exposure position with the transaction type Firm Commitment Transaction is automatically reduced by the amount of the sub raw exposure.

##### Differentiating Exposure Positions

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Management 2.0: Process > Differentiating Exposure Positions | L4 | trm03 p.271 | loio `09e90343454a4a64893cd3cd119cd3b9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/09e90343454a4a64893cd3cd119cd3b9.html?locale=en-US)

By using the Initiate Release function to release sub raw exposures, you create exposure positions from sub raw exposures. The way that these positions are split up depends on the settings that you make in Customizing.

Which differentiation criteria you choose can, for example, depend on how you would like to portray hedging for exposure positions:

Macro Hedges

Aggregation of exposures with the same type from different transactions for an exposure position

Same hedge shared by different transactions

In this case, you set the aggregation indicator in the Customizing activity Define Exposure Position Types.

Micro Hedges

Each transaction, such as the sale of a large machine (= raw exposure), is hedged using individual hedging transactions (= no aggregation).

In this case, the raw exposure ID is a differentiation criterion for splitting exposure positions.

Currency Exposures

**The following differentiation criteria and Customizing settings are valid for all sub raw exposures representing a currency risk as:**

|Differentiation Criterion|Global Setting: Automatic Position Matching You select this setting if you want to use the Automatic Position Matching function. **Note:** If you want to be able to combine sub raw exposures for different raw exposures on one exposure position, you also set the Aggregation indicator (detailed below) in the activity Define Exposure Position Types.|Global Setting: Change to Transaction Type Is Permitted You select this setting when you do not want new raw exposures to be created whenever changes are made to the transaction category in the hedged item. You can then change the transaction category in the raw exposure. **Note:** If you would like to hedge each raw exposure individually, you do not set the Aggregation indicator in the activity Define Exposure Position Types. In this case, you can also set the No Planning Period, No Planning Year indicator. If you set this indicator and do not select the exposure date as an additional differentiation criterion, the exposure position is independent of any time-based differentiation. In this way, you can change the payment date in the raw exposure without changing the connection to the exposure position.|
|---|---|---|
|Mandatory Differentiation Criteria| | |
|Company Code|X|X|
|Risk Category|X|X|
|Transaction Category of the Raw Exposure|X|X|
|Currency of the Exposure Amount|X|X|
|Target Currency|X|X|
|Exposure Position Type|X|X|
|Product Type|X|X|
|Differentiation Criteria that Can Be Deactivated| | |
|Raw Exposure ID|If you set the Aggregation indicator in the Customizing activity Define Exposure Position Types, these two criteria are no longer applied as differentiation criteria. Consequently, sub raw exposures of different raw exposures can then be combined in an exposure position.| |
|Raw Exposure Position ID| | |
|Planning Period|X|If you have not set the Aggregation indicator in these global settings in the activity Define Exposure Position Types,|


| | |you can set the No Planning Period, No Planning Year indicator so that the Planning Period and the Planning Year are no longer applied as differentiation criteria.|
|---|---|---|
|Planning Year|X| |
|Additional Optional Differentiation Criteria| | |
|Country/Region Key Profit Center Exposure Date Transaction Activity Free Attributes In Customizing under Settings for Free Attributes, there are Customizing activities in which you can define headings, values, and texts for the fields relating to raw exposure header data and raw exposure line items.|In the Customizing activity Define Exposure Position Types, you specify for each exposure position type the differentiation criteria that also need to be considered when splitting exposure positions. In the Customizing activity Define Exposure Activity Types, you use the Field Selection function to specify which fields are displayed when users enter raw exposure data and whether these fields are optional, required, or only for display purposes. We recommend that you define the fields used as differentiation criteria as required fields or at least as optional fields that, when they are not filled manually, are filled using the derivation rules.| |

##### Process Raw Exposures

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Management 2.0: Process > Process Raw Exposures | L4 | trm03 p.273 | loio `38bdc1f7803f41be9140e21487517d53` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/38bdc1f7803f41be9140e21487517d53.html?locale=en-US)

**Use**

You can use the Process Raw Exposure app to manually create, change, release, and delete raw exposures.

Each time you save a raw exposure, a new version is created. Version 000 is always the current version of the raw exposure. In display mode, you can switch between the different versions of the raw exposures.

If you select a line item on the Line Items tab, the system displays the related sub raw exposures at the bottom of the screen. You can view the flows created for each sub raw exposure in the app Display Exposure Position Flows.

**Procedure**

**Creating Raw Exposures**

- 1. Select the valid Exposure Activity Type and choose Create.
- 2. On the Header Data tab, first enter the general raw exposure data, such as Ext. Document Number, Standard Exposure Type, Company Code (mandatory differentiation criteria), and the Country/Region.
- 3. Go to the Position Data tab. Select Create New Line Item and enter the external position number, the planning year, the exposure date on which the raw exposure is due, the period in which the raw exposure is due, the amount, the unit of measure, the currency, and the target currency. In the Amount field, enter the payment amount (for fixed price agreements and foreign exchange exposures).


**Note:**

The fields displayed in the Free Attributes screen area have been predefined in the system.

- 4. Variable Prices: To display pricing conditions in the price table for variable prices, select Variable Prices.

If you choose quotation-based pricing, enter the price date, quotation source, quotation type, and weighting price for each price.

The values for the exposure amount currency and the unit of measure are copied automatically from the line item. The price unit of the notation is initialized with the value 1.

- 5. Fixed Prices:

You can enter a temporary price and give it the status Not Fixed. If you use a 0 and a there is a currency risk, no sub raw exposure is created for the currency risk.

- 6. Enter all additional data belonging to the line item and save your entries.


After the entries have been saved, the system creates sub raw exposures for the line items. For the units of measure used in the price table, the values are converted accordingly.

The exposure date is filled in the sub raw exposure as follows:

|Price Type|Risk Type|Exposure Date|
|---|---|---|
|Variable|Currency Risk|Payment Date if known; otherwise, the Due Date of the memo record is applied|
|Fixed|Currency Risk|Payment Date if known; otherwise, the Due Date of the memo record is applied|
|Without Price|Currency Risk|Payment Date if known; otherwise, the Due Date of the memo record is applied|


Display, Change, or Delete Raw Exposure

To display the sub raw exposure for a raw exposure, select a line item on the Line Items tab. You can view the flows created for a sub raw exposure in the app Display Exposure Position Flows.

When the price date is reached, you enter the actual fixed price in the price table and change the fixing status to Fixed. When you save the entries, the sub raw exposures are updated.

You can delete a raw exposure provided that it has not yet been released and no exposure positions have been created for the raw exposure.

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**More Information**

Exposure Management 2.0

##### Process Raw Exposures - Collective Processing

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Management 2.0: Process > Process Raw Exposures - Collective Processing | L4 | trm03 p.274 | loio `f6f2a84c7d6248b19b3d91b3cc1c5e44` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f6f2a84c7d6248b19b3d91b3cc1c5e44.html?locale=en-US)

Use

You can use the app Process Raw Exposures - Collective Processing to display either the line items or the sub raw exposure for the raw exposures in the system. The system outputs them in a list from which you can then process them:

For raw exposures that have not been released, you can trigger their release.

You can display the relevant raw exposure for a line.

You can call up the relevant raw exposure in processing mode.

You can delete a raw exposure that has not yet been released.

You can also display the details for line items or sub raw exposures.

**Activities**

- 1. Call the app Process Raw Exposures - Collective Processing.
- 2. Choose Memo Record Details or Sub Raw Exposure Details.
- 3. Use the selection criteria to restrict the selection of raw exposures, or start the app directly to display all existing memo records or sub raw exposures.
- 4. In addition, you can now display, change, release, or delete the relevant raw exposures or display the details for a memo record or a sub raw exposure.


**Supported Device Types**

Desktop

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**More Information**

Exposure Management 2.0

Editing Raw Exposures

##### Mass Price Adjustment for Raw Exposures

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Management 2.0: Process > Mass Price Adjustment for Raw Exposures | L4 | trm03 p.275 | loio `a103b06b87c64e6c80a761489a2e26c7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a103b06b87c64e6c80a761489a2e26c7.html?locale=en-US)

**Use**

You use this report for the following actions:

Variable prices of all sub raw exposures with a price date up to the fixing date can be fixed automatically.

For sub raw exposures with a price date after a fixing date, you can use the report to determine and propose prices.

You can undo fixing for prices that have already been fixed to make them variable again (such as when you want to make corrections).

To fix prices, this report only uses price information from market data table. Logistical transactions, such as goods receipts and invoice receipts, are not considered for fixing prices.

If the variable price has been fixed by the report, the system automatically releases the changed exposure position.

**Prerequisites**

To be able to use this report, you need to have made the following settings:

In the Customizing settings for the corresponding exposure activity type, you can assigned an approach category that allows for variable prices.

You have specified the relevant exposure activity type and price determination for exposure positions that have not yet been fixed. To do this, go to Customizing for Treasury and Risk Management and choose Transaction Manager

Exposure Management 2.0 Define Exposure Activity Types . For the relevant exposure activity type, choose one of the following two strategies under Price Determination:

Market data and price information have been manually entered or uploaded into the system. To do this, go to the area menu and choose Treasury and Risk Management Basic Functions Market Data Management . Here you find the transactions Import Market Data (TBDM).

You have released raw exposures (using transaction FTREX1) or created a financial transaction (transaction FTR_CREATE).

**Activities**

- 1. Run this report (using transaction FTREX25). You find the report in the area menu under Treasury and Risk Management Exposure Management 2.0 Raw Exposures .


- 2. Select the kind of adjustment and enter a fixing date.
- 3. We recommend that you perform a test run first. You perform a test run by setting the "Test Run" indicator in the control parameters at the foot of the screen.
- 4. Execute the report (F8). To execute the report as a background job, choose F9.
- 5. The system displays a message log. For more detail information, see the documentation for the F1 Help.

##### Import Raw Exposures - Spreadsheet

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Management 2.0: Process > Import Raw Exposures - Spreadsheet | L4 | trm03 p.276 | loio `3b6e1b283ba3418ebee02820889bcb0c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b6e1b283ba3418ebee02820889bcb0c.html?locale=en-US)

App ID: FTREX_EXCEL_UPLOAD

With this app, you can import raw exposures from a spreadsheet into Exposure Management 2.0.

**Key Features**

You can upload a file with the raw exposure data and display the data before importing them.

**Note:**

The format of the dates in the spreadsheet must match the format in your user data.

Decimals are separated by dots. If you use commas to separate decimal points, the system will take it as invalid data.

You can first run the import as a test run.

Display of data validation results, for example, errors and warnings for checking

Import of correct data and data with warnings into the system

**Template for Spreadsheet**

Using the Hide/Show Columns button, you can choose which columns you want to display or hide.

You can download the table from the documentation as template for the spreadsheet required for the raw exposure import.

To download the table as spreadsheet (via CSV file) from documentation, proceed as follows:

- 1. Choose the Download Data button above the table. The file type XLSX is already selected. Switch to CSV.
- 2. Select the CSV delimiter you want to use for your file. The Semicolon (;) value is selected.
- 3. Choose Download all data on all pages.
- 4. Choose Download.


**Note:**

Enter the dates in such a way that they correspond to your personal date format that you have selected in your user profile under Settings Language and Region .

Table that you can download as a template for the spreadsheet required for the raw exposure import

|External Document Number|Exposure Origin|Logical System|Exposure Activity Type|Exposure Category of Raw Exposure|Country/Region Key|ISO code|Company Code|Value of Free Attribute (Char4)|Value of Free Attribute (Char4)|Free Attribute (Char20)|F A (|
|---|---|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | | | |


The following table explains each column of the spreadsheet.

Explanations about the columns of the raw exposure spreadsheet

|Column No.|Name|Explanation|
|---|---|---|
|A|External Document Number|Enter an external number related to the raw exposure.|
|B|Exposure Origin|Exposure origins are defined in the system.|
|C|Logical System| |
|D|Exposure Activity Type|The exposure activity type gives semantic meaning to an exposure. It is also the anchor for the dynamic field selection feature. A raw exposure is always created with an exposure activity type.|
|E|Exposure Category of Raw Exposure|A raw exposure can be categorized using exposure categories such as Forecasted Transaction, Firm Commitment Transaction, or Asset/Liability Transaction.|


|Column No.|Name|Explanation|
|---|---|---|
| | |The exposure category is used as one of the criteria for differentiating exposure positions, because hedge accounting rules are different for these categories.|
|F|Country/Region Key|If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is available during exposure position generation.|
|G|Country/Region ISO Code|The country/region can also be entered using the country/region ISO code in this field.|
|H|Company Code|The company code is an organizational unit within financial accounting.|
|I|Value of Free Attribute (Char4) (ATTRIBUTE_SH01)|Short Header Attribute 1|
|J|Value of Free Attribute (Char4) (ATTRIBUTE_SH02)|Short Header Attribute 2|
|K|Value of Free Attribute (Char20) (ATTRIBUTE_LH01)|Long header attribute defined by customer in configuration|
|L|Free Attribute (Date) (ATTRIBUTE_DH01)|Date header attribute defined by customer in configuration **Note:** The format of the dates in the spreadsheet must match the format in your user data|
|M|Valid From|Valid-From Date of Exposure Determines the validity start date of a raw exposure and any related exposure position flows created when releasing the raw exposure. **Note:** The format of the dates in the spreadsheet must match the format in your user data|
|N|Physical Inventory Indicator|No entry in this field|
|O|Release Status|Set by system|
|P|External Item Number|This field can be used to link the line items in raw exposures with line items in operational documents such as sales orders or purchase orders.|


|Column No.|Name|Explanation|
|---|---|---|
| | |Enter the same value in the field External Item ID.|
|Q|Profit Center|Key which together with the controlling area uniquely identifies a profit center. If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is available during exposure position generation.|
|R|Material|No entry in this field|
|S|Commodity ID (obsolete)|No entry in this field|
|T|Quantity|No entry in this field|
|U|Unit of Measure|No entry in this field|
|V|UoM ISO Code|No entry in this field|
|W|Exposure Amount|Exposure amount **Note:** Decimals are separated by dots. If you use commas to separate decimal points, the system will take it as invalid data.|
|X|Exposure Amount Currency|Currency of the exposure amount Examples: USD EUR GBP|
|Y|ISO Code Exposure Amount Currency|ISO code of the exposure amount currency Examples: USD EUR GBP|
|Z|Target Currency of Raw Exposure|Target currency of a raw exposure line item In an FX line item, the target currency usually is the currency of the company code (local currency). Examples: USD EUR |


|Column No.|Name|Explanation|
|---|---|---|
| | |GBP|
|AA|ISO Code of Target Currency of Raw Exposure|ISO Code of the target currency of a raw exposure line item Examples: USD EUR GBP |
|AB|Planning Period|Planning Period The planning period together with the planning year defines the period in which the raw exposure expires. Choose the period in which the raw exposure expires. Example Planning Periods: M01 January M02 February M03 March M04 April ...|
|AC|Planning Year|Planning Year The planning period together with the planning year defines the period in which the raw exposure will expire. Enter the year in which the raw exposure will expire.|
|AD|Exposure Due Date|Date on which the exposure is due and expires **Note:** The format of the dates in the spreadsheet must match the format in your user data|
|AE|Free Attribute (Char20) (ATTRIBUTE_LI01)|Long line item attribute defined by customer in configuration|
|AF|Free Attribute (Char20) (ATTRIBUTE_LI02)|Long line item attribute defined by customer in configuration|
|AG|Free Attribute (Char20) (ATTRIBUTE_LI03)|Long line item attribute defined by customer in configuration|


|Column No.|Name|Explanation|
|---|---|---|
|AH|Free Attribute (Char20) (ATTRIBUTE_LI04)|Long line item attribute defined by customer in configuration|
|AI|Value of Free Attribute (Char10) (ATTRIBUTE_MI01)|Middle line item attribute defined by customer in configuration|
|AJ|Value of Free Attribute (Char10) (ATTRIBUTE_MI02)|Middle line item attribute defined by customer in configuration|
|AK|Value of Free Attribute (Char4) (ATTRIBUTE_SI01)|Short line item attribute defined by customer in configuration|
|AL|Free Attribute (Date) (ATTRIBUTE_DI01)|Date line item attribute defined by customer in configuration|
|AM|Payment Date|Date on which the payment will be made|
|AN|Fixed/Floating Indicator|No entry in this field|
|AO|Plant|No entry in this field|
|AP|Storage Location|No entry in this field|
|AQ|Batch|No entry in this field|
|AR|Market Price Exposure Rule|No entry in this field|
|AS|Condition Type|No entry in this field|
|AT|Variable Price Category|No entry in this field|
|AU|Price Fixation Status|No entry in this field|
|AV|Earliest Exercise Date|No entry in this field|
|AW|Latest Exercise Date|No entry in this field|
|AX|Delivery Date|No entry in this field|
|AY|External Item ID|This field can be used to link the line items in raw exposures with line items in operational documents such as sales orders or purchase orders. Enter the same value as in column External Item Number.|
|AZ|Material|No entry in this field|
|BA|Portfolio|A portfolio is an organizational element to group together various treasury transactions for reporting purposes. If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is|


|Column No.|Name|Explanation|
|---|---|---|
| | |available during exposure position generation.|
|BB|Cost Center|A key that uniquely identifies a cost center. If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is available during exposure position generation.|
|BC|Business Area|Key that uniquely identifies a business area. If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is available during exposure position generation.|
|BD|WBS Element|Key that identifies a WBS element. If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is available during exposure position generation.|
|BE|Segment|Segment for Segmental Reporting If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is available during exposure position generation.|
|BF|On Behalf of Company Code|On Behalf of Company Code If this field is a differentiation criterion in your hedging areas, the field must also be filled in the raw exposure so that it is available during exposure position generation.|
|BG|Raw Exposure Description|Free text field|


**Prerequisites**

Enter the raw exposure data in a spreadsheet.

**Activities**

- 1. Open the Import Raw Exposures - Spreadsheet app on the SAP Fiori launchpad.
- 2. To select the spreadsheet file, choose the value help of the File name field. In the following popup, choose OK. Then you can select the spreadsheet file and choose Open.
- 3. In the Processing Options area, the Display Data Before Processing and the Test run indicators are selected. You can deselect the indicators.


If you select the Display Data Before Processing indicator, the data import is executed in two steps. First the data are uploaded from the spreadsheet and displayed and then you must choose Execute to import the data.

You can use the test run function to simulate the import. All errors and warnings for the raw exposure data are displayed. Based on these error messages, you can correct the data and only after the test run no longer shows any errors, deselect the Test run indicator and execute the import as an update run. Raw exposures are only created in the system in an update run.

- 4. Run the app.
- 5. If you have selected the Display Data Before Processing indicator, the data uploaded from the spreadsheet are displayed.
- 6. Choose Execute to import the data.
- 7. The uploaded data are checked and in case any errors or warnings occurred they are displayed.
- 8. The result table displays the raw exposures with their status. For imported raw exposures in an update run the generated Raw Exposure ID is displayed.


**Note:**

Raw exposures with errors are not imported.

**Supported Device Types**

Desktop

Tablet

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**More Information**

Exposure Management 2.0

#### Exposure Positions

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Positions | L3 | trm03 p.283 | loio `32912e51e1076f62e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/32912e51e1076f62e10000000a44538d.html?locale=en-US)

You can use the following transactions to transfer exposure positions from Exposure Management to Hedge Accounting for Exposures (E-HA):

Overview of Exposure Positions

Mass Transfer of Exposure Positions to E-HA

**More Information**

Transferring Exposures to Hedge Accounting for Exposures (E-HA)

Exposure Lifecycle

##### Process Exposure Positions

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Positions > Process Exposure Positions | L4 | trm03 p.284 | loio `a90392afdf134514a8b59fcef68b675d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a90392afdf134514a8b59fcef68b675d.html?locale=en-US)

**Use**

With this app, you can display and process the exposure positions that you have selected for a specified key date.

**Key Features**

To display the exposure flows for a position, double-click that line.

To display the details, key figures, and flows for an exposure position, select a line and choose the relevant button from the header bar.

You can also display the relevant financial object and the raw exposure.

Save a specific variant and/or layout according to your preferred settings

Export the results list to a spreadsheet by choosing More Position Export Spreadsheet

**Supported Device Types**

Desktop

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**More Information**

Exposure Management 2.0

##### Mass Transfer of Exposure Positions to E-HA

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Positions > Mass Transfer of Exposure Positions to E-HA | L4 | trm03 p.284 | loio `d44117516e9cfa50e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d44117516e9cfa50e10000000a441470.html?locale=en-US)

**Use**

Using this transaction (FTREX15), you can transfer a selection of multiple exposure positions simultaneously to Hedge Accounting for Exposures.

(To transfer exposure positions individually, you can use the Overview of Exposure Positions transaction (FTREX12).)

**Prerequisites**

You have not set the No Transfer to E-HA indicator in Customizing for Treasury and Risk Management under Transaction Manager General Settings Exposure Management 2.0 Exposure Lifecycle Define Exposure Categories .

Hedging-relevant exposure positions were created and subsequently assigned to a hedge plan in transaction THMEX.

Note: Due to the exposure lifecycle, it is sufficient to assign an exposure item of exposure category 1 — Forecasted Transaction to the hedge plan.

For more information, see Transferring Exposures to Hedge Accounting for Exposures (E-HA)

**Activities**

To transfer exposure positions, execute transaction FTREX15, select the exposure positions to be transferred, and choose Execute.

**More Information**

Hedge Accounting for Exposures (E-HA)

##### Display Exposure Position Flows

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Positions > Display Exposure Position Flows | L4 | trm03 p.285 | loio `69e3d2cf89064f43ae74272a60003cf6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/69e3d2cf89064f43ae74272a60003cf6.html?locale=en-US)

With this app, you can display exposure position flows.

**Key Features**

Displays a list of all relevant exposure positions according to the selection criteria you entered

Search for position flows directly or by corresponding positions

View the details of an exposure position flow by selecting a row in the table and choosing the Details icon in the header bar

Navigate to the corresponding exposure position by selecting an entry from the list and choosing the Position button from the header bar

Navigate to the relevant raw exposure by selecting an entry from the list and choosing the Raw Exposure button from the header bar

Display the corresponding exposure position type

Save a specific variant and/or layout according to your preferred settings

Export the results list to a spreadsheet by choosing More Flow Export Spreadsheet

**Supported Device Types**

Desktop

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**More Information**

Exposure Management 2.0

#### Exposure Management 2.0: Transferring Exposures to E-HA (1 of 2)

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Exposure Management 2.0: Transferring Exposures to E-HA | L3 | trm03 p.285 | loio `a0af10519e1b256ee10000000a445394` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a0af10519e1b256ee10000000a445394.html?locale=en-US)

**Use**

When exposure positions are transferred from Exposure Management 2.0 to Hedge Accounting, the corresponding business types are derived from the exposure types, and the respective business activity types are determined from the exposure activity types. Exposures are transferred at the exposure position level.

**Prerequisites**

To specify how selected attributes are derived for transfers to Hedge Accounting, you can use the Customizing activities Define Exposure Categories, Determine Exposure Categories and Exposure Activity Types, and Define Sequences for Exposure Categories.

**Features**

For the transfer, there are three settings options in the Customizing activity Define Exposure Categories:

No transfer:

If exposures are only relevant for reporting purposes but not for E-Hedge Accounting, the Transfer Not Permitted indicator is set.

Transfer without aggregation: .

If the Aggregate Exposure indicator is not set, the system creates a new exposure in Hedge Accounting for each new or changed exposure position. In the case of changed or obsolete exposure positions, the existing hedging relationship needs to be dedesignated (terminated) and replaced with a new one.

Transfer with aggregation:

If the Aggregate Exposure indicator is set, exposure positions of Exposure Management are added to a transaction of an existing exposure in E-Hedge Accounting. In the case of changed or obsolete exposure positions, the existing hedging relationship does not have to be dedesignated.

Example: If a planned purchase order becomes a confirmed purchase order with a fixed price, the affected transaction is removed from the exposure. The existing hedging relationship does not have to be dedesignated.

Exposure positions can be transferred individually using transaction Overview of Exposure Positions (FTREX12) or transferred in a bundle using transaction Mass Transfer of Exposure Positions to E-HA (FTREX15).

**More Information**

Hedge Accounting for Exposures (E-HA)

Exposure Lifecycle

Overview of Exposure Positions

#### Integration of Operating Exposures in Market Risk Analysis

> **Path:** Treasury and Risk Management > Exposure Management 2.0 > Integration of Operating Exposures in Market Risk Analysis | L3 | trm03 p.286 | loio `4df9da9cc434096ee10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4df9da9cc434096ee10000000a42189e.html?locale=en-US)

**Use**

With the Market Risk Analyzer you can, for example, calculate the net present value and the mark-to-market value of operating exposures.

**Integration**

In Treasury and Risk Management, there is a financial object available for raw exposures and one for exposure positions.

**Prerequisites**

Customizing

You can find the following new Customizing activities under Treasury and Risk Management Basic Analyzer Settings Automatic Integration of Financial Objects in Transaction Master Data Operating Exposures :

Activate/Deactivate Financial Object Integration

To enter the financial object data at the same time as the master data, you need to activate the Component Active indicator. The system then displays entry screens for the corresponding components (results analysis, analysis, and default risk and limit system) during online processing of the transaction data. Here you can enter information about the financial object.

For operating exposures, you can perform financial object integration for the risk category FX Risk for the selected company code.

Define Derivation Strategy for Exposures

Financial objects contain a large number of characteristics. The characteristic values are derived from the exposure position data in Exposure Management 2.0. In the derivation strategy, you determine how the system fills the financial object properties from the data fields of the exposure positions.

BAdI: Exposure

You use this BAdI to perform individual derivations for the characteristics of the financial objects.

Define Derivation Strategy for Raw Exposures

This is where you specify how the system fills the characteristics of the financial object using the data fields of the raw exposure. You can define the derivation strategy for each analysis structure. A derivation strategy consists of multiple derivation steps that are used for deriving characteristic values from other characteristics. Each of these steps describes a derivation type with which a number of target fields can be filled from a number of source fields. This means that each step describes a logical dependency between target fields and source fields.

BAdI: Raw Exposures

You use this BAdI to perform individual derivations for the characteristics of the financial objects.

BAdI: Relevance for Raw Exposures

With this BAdI you can exclude the raw exposures or raw exposure positions when creating financial objects.

Note: The exposure activity type that is used must be assigned to an approach category with floating prices. You can find this setting in Customizing under Treasury and Risk Management Transaction Manager General Settings Exposure Management 2.0 Define Exposure Activity Types .

Master and Transactional Data

To be able to calculate the net present value, the payment date, and the delivery date must be defined in the raw exposure position (transaction FTREX1).

For more information about calculating the net present value of exposure positions, see Net Present Value Calculations for Operating Exposures.

Define the rules for deriving analysis parameters from operating exposures. You can find these settings in the area menu under Treasury and Risk Management Market Risk Analyzer Master Data Derive Rule Values Operating Exposures (transaction AFO_FOI_RULE_EXP).

