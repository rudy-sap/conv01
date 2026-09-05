# Hedge Management of FX Risks - SAP TRM Knowledge Base (branch split)

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

### Hedge Management of FX Risks

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks | L2 | trm04 p.2 | loio `538e8e9bcdd948fcb720a0f443c30341` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/538e8e9bcdd948fcb720a0f443c30341.html?locale=en-US)

Treasury and Risk Management provides the Hedge Management of Net Opne Exposures process to manage the risk of planned cash flows in a foreign currency in future periods and the Hedge Management of Balance Sheet FX Risk process for managing the risks arising from the revaluation of monetary balance sheet items in foreign currency.

For more information, see also

Hedge Management and Accounting of Net Open Exposures (FX Risk)

Hedge Management of Balance Sheet FX Risk

#### Hedge Management and Accounting of Net Open Exposures (FX Risk)

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) | L3 | trm04 p.2 | loio `104b7358ff3ca107e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/104b7358ff3ca107e10000000a441470.html?locale=en-US)

**Use**

The treasury department of a corporate company is responsible for executing the hedging policy to manage the risk of planned cash flows in a foreign currency in future periods. The Treasury and Risk Management solution supports you in fulfilling this task.

The hedging area represents a section of your hedging policy.

In the hedging area master data, you define the level of granularity on which you want to monitor your foreign exchange risk.

You can define different kinds of analysis items:

Analysis Items By Time Periods

Incoming and outgoing exposures are aggregated according to the differentiation criteria and reporting time pattern. The exposure aggregation level decides whether they are saved as net or gross exposure items.

Analysis Items By Reference

An exposure item represents one specific exposure based on a non-aggregated exposure position. And, in contrast to the exposure items by time periods, these exposure items have a specific due date.

You specify which exposures and hedging instruments are selected by defining the relevant company codes, hedging classifications, risk-free currencies, risk currencies, and the filters for exposures and hedges.

**Note:**

Cross-currency hedging is possible.

Different risk-free currencies are possible within hedging area and company code.

Local currency of company code can also be a risk currency in a company code.

When you use automated designation of exposure items, you mark the hedging area as hedge-accounting-relevant and enter the necessary data (that is, the product type for exposure subitems, the settings for designation level, designation activation, and designation splitting on the Hedge Accounting I tab and for the designation control on the Hedge Accounting II tab).

For hedging areas with analysis items defined by time periods, you can define and enter the target quota tables.

The hedging area is the basic master data for the hedge management cockpit. The Hedge Management Cockpit enables you to gain an overview of the foreign exchange risk that your company is exposed to as well as of the hedging instruments that you used to mitigate that risk. It reports foreign exchange exposures managed in Exposure Management 2.0, Foreign Exchange Management, and Cash Management and hedging instruments (hedges) managed in the Transaction Manager. In addition, a lot of key figures, for example, the net open exposures that represent the unhedged portion of the FX exposures, are calculated.

Based on the key figures (for more information, see also Key Figures in the Hedge Management Cockpit), you can decide on your further hedging activities. You can use the Hedge Management Cockpit to create hedge requests for analysis items. You can use an FX hedge request if you want your trader to hedge a specific currency amount for a specific date. In cases where you face an

overhedge situation, you can create a termination request. If hedge accounting is active for a hedging area also swap requests and dedesignation requests are available. After you released the hedge requests they are either executed automatically (dedesignation request) or are made available to the traders (FX hedge request, termination request, and swap request).

**Note:**

If you have activated the integration of trading platforms in your hedging area, for FX hedge requests, swap requests, and termination requests that have the status Released the system automatically creates corresponding trade requests (with trade request category Hedge). These trade requests are automatically transferred to the SAP Trading Platform Integration application. The trade requests are then sent to an external trading platform where the trader confirms them and concludes financial transactions. The financial transactions are transferred back to your system. For more information, see also Integration with External Trading Platforms.

If you activated hedge accounting for exposure items for a hedging area, the automated designation process creates automatically the Exposure Subitems, Hedging Relationships, Hedged Items, and Hedging Instruments tabs when the trader saves a financial transaction used as hedging instrument.

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM04-F001]

Please note that image maps are not interactive in PDF outputs.

Limitations

**Limitation for Hedge Management**

|Limitation|Hedging Areas with Risk-Free Currency Type 'Local Currency'|Hedging Areas with Risk-Free Currency Type 'Currency Defined by the Source'|Hedging Areas with Analysis Item Definition 'By Reference'|
|---|---|---|---|
|Financial instruments allowed for hedging|Spot/forward transactions Non-deliverable forward transactions FX swap Non-deliverable FX swap FX options Collar FX options|Spot/forward transactions Non-deliverable forward transactions FX options Collar FX options|Spot/forward transactions Non-deliverable forward transactions FX options Collar FX options|
|Instrument Categories available in FX Hedge Request|FX Forward FX Spot FX Option FX Non-Deliverable Forward FX Collar FX Swap FX Non-Deliverable Swap|FX Forward FX Spot FX Option FX Non-Deliverable Forward FX Collar **Note:** Hedge requests are required for the creation of hedging instruments. The assignment of the hedge request is prerequisite for the selection of hedges in the Hedge Management Cockpit.|FX Forward FX Spot FX Option FX Non-Deliverable Forward FX Collar|
|Automatic hedge request creation is not supported| | |X|
|Target quotas are not supported| | |X|
|The due date shift is not supported| | |X|
|Daily reporting periods only available for exposures with data source E_EM2 Exposure Management 2.0|X|X|Daily reporting periods are not relevant.|
|Due date shifts for automated FX hedge request creation are not supported for daily reporting periods.|X|X|Daily reporting periods are not relevant.|


**Limitations for Hedge Accounting**

|Limitation|Hedging Areas with Risk-Free Currency Type 'Local Currency'|Hedging Areas with Risk-Free Currency Type 'Currency Defined by the Source'|Hedging Areas with Analysis Item Definition 'By Reference'|
|---|---|---|---|
|Financial instruments allowed for hedging|Spot/forward transactions Non-deliverable forward transactions FX swap Non-deliverable FX swap FX options (only plain vanilla FX options with exercise type European. FX options with an FX forward transaction acting as the underlying transaction are not supported.) Collar FX options|Spot/forward transactions Non-deliverable forward transactions|Spot/forward transactions Non-deliverable forward transactions FX swap Non-deliverable FX swap FX options (only plain vanilla FX options with exercise type European. FX options with an FX forward transaction acting as the underlying transaction are not supported.) Collar FX options|
|Only gross designation is supported.|X|X|X|
|The hedge accounting process provides flexible tools to support the requirements of IFRS 9 and U.S. GAAP only.|X|X|X|
|Late designation, such as designation on a date other than the contract date of the FX transaction, is not supported.|X|X|X|
|FX swap request not supported| |X|X|
|FX swap process is not supported for U.S. GAAP hedge accounting scenarios.|X|Irrelevant because the FX swap request is not supported.|Irrelevant because the FX swap request is not supported.|
|The FX swap request does not consider the designation splitting information that was entered in the hedging area.|X|Irrelevant because the FX swap request is not supported.|Irrelevant because the FX swap request is not supported.|
|Dedesignation requests cannot be created for hedging relationships that are already part of a FX swap request.|X|Irrelevant because the FX swap request is not supported.|Irrelevant because the FX swap request is not supported.|


|Limitation|Hedging Areas with Risk-Free Currency Type 'Local Currency'|Hedging Areas with Risk-Free Currency Type 'Currency Defined by the Source'|Hedging Areas with Analysis Item Definition 'By Reference'|
|---|---|---|---|
|Expiration of a FX option before its exercise date is not supported.|X|X|X|
|Initialization of Hedge Accounting is not possible| |X| |
|Key date valuation before the premium date of the FX option is not supported with the hedge accounting scenario 981 CFH: FX Risk with Intrinsic, Time + CCBS + Others.|X|X|X|
|Hedge accounting is not supported for hedging areas with a reporting time pattern that has the period length Day.|X|X|X|


The following list describes the financial instruments that are allowed as hedging instruments in the Hedge Management Cockpit

Product category is 600 Foreign Exchange

Product category is 760 OTC Options

The option category is one of the following

- 001 Standard (in Hedge Accounting for Exposure Items process only plain vanilla and collar options with option type European are supported)

- 002 Average Rate Option (not supported in Hedge Accounting for Exposure Items process)


- 050 Basket Option (not supported in Hedge Accounting for Exposure Items process)

- 051 Basket Option Average Rates (not supported in Hedge Accounting for Exposure Items process)


The underlying product type has product category 600 Foreign Exchange. FX options with an FX forward transaction acting as the underlying transaction are not supported in Hedge Accounting for Exposure Items process.

Swap request:

Swap request is only supported for hedging areas with hedge accounting.

Swap request does not consider any splitting information that was entered in the hedging area.

Swap request is not supported for hedging areas with analysis item definition By Reference.

Swap request is not supported for hedging areas with cross-currency hedging.

Automatic hedge request creation is not supported for hedging areas with analysis item definition By Reference.

Target quotas are not supported for hedging areas with analysis item definition By Reference.

The due date shift is not supported for hedging areas with analysis item definition By Reference.

The due date shift is not supported for hedging areas with cross-currency hedging.

(Cross-currency) Hedging process of hedging areas with the risk-free currency setting Defined by the Source:

The Hedge Management Cockpit allows for these hedging areas only the instruments FX spot, FX forward, FX NDF, FX options and collar FX options.

The manual and automatic creation of hedge requests is also only supported for the instruments mentioned here. Therefore, FX swap requests are not supported.

The hedge accounting process for these hedging areas, does not support FX options or collar FX options as hedging instruments.

The Hedge Accounting for Exposure Items process provides flexible tools to support IFRS 9 and U.S. GAAP requirements only.

The Only Net exposure aggregation level is currently not supported for designation purposes of the Hedge Accounting for Exposure Items process. This is because only gross designation is supported.

The automated designation process of the Hedge Accounting for Exposure Items process is supported only for the creation of FX forward transactions, non-deliverable forwards (NDFs), FX swaps, plain vanilla FX options, and collar FX options.

Creation of dedesignation requests for hedging relationships that are already part of a swap request is not supported.

Key date valuation before the premium date of the FX option is not supported with the hedge accounting scenario 981 CFH: FX Risk with Intrinsic, Time + CCBS + Others.

Late designation such as designation on a date other than the contract date of the FX transaction is not supported.

**Prerequisites**

Discuss and define your hedging policy.

Make the necessary settings in Customizing for Hedge Management and, if required, the Settings for Hedge Accounting for Exposure Items.

If you use effectiveness testing, you must define market data sets using the Manage Market Data Sets function. These market data sets need to be assigned to the hedging areas.

Defining Time Patterns for Target Quotas

Define your hedging areas (transaction TOE_HEDGING_AREA).

The hedging area provides the determining master data for the Hedge Management Cockpit and Hedge Accounting. You have to define your hedging areas before you can start the reporting.

In the master data of the hedging areas, the Hedging Area: Hedge Accounting I and Hedging Area: Hedge Accounting II tabs are relevant for the Hedge Accounting for Exposure Items process.

Initialize your existing hedging activities for this process.

Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk)

Define layouts for the Hedge Management Cockpit within the Hedge Management Cockpit using the Manage Layouts function. You cannot execute the Hedge Management Cockpit without choosing a layout.

You constantly enter and release your raw exposures in Exposure Management 2.0 or enter your FX exposures in the Foreign Exchange Exposure Management using the Manage FX Exposures app or the API Foreign Exchange Exposures.

Ensure that the exposure positions and the financial transaction data of the hedging instruments carry the data you need for reporting.

**Process**

- 1. Save current exposure items by using the Take Snapshot function (using the app on the SAP Fiori launchpad or transaction TOESNAP).
- 2. Determine your net open exposures and all other key figures defined in your layout using the Hedge Management Cockpit (using the app on the SAP Fiori launchpad or transaction TOENE).

- 3. Take your hedging decisions based on the key figures provided in the Hedge Management Cockpit (for more information, see also Key Figures in the Hedge Management Cockpit).

- 4. Create an FX hedge request directly from the Hedge Management Cockpit to inform the front office about the hedging decisions you have made.

You can also use the Triggering the Creation of Automated FX Hedge Requests function to automatically generate FX hedge requests based on the key figure Amount to Hedge.

- 5. When you are in an overhedge situation, you can create a termination request to trigger the termination of a hedge. You can set the Overruling Allowed indicator in the termination request. This allows your trader to overrule the termination request and instead create an offsetting transaction if the conditions of your business partner for termination do not meet your requirements.

For a hedging area with hedge accounting, the following kinds of hedge requests are also available in an overhedge situation:

Swap Request

Use the swap request, if you decide to swap amounts from one period to another.

Dedesignation Request

Use the dedesignation request, if you decide to dedesignate hedging instruments completely or partially.

- 6. Submit and release hedge requests using the Process Hedge Requests function.

If you have activated the integration of trading platforms in your hedging area, for FX hedge requests, swap requests, and termination requests that have the status Released the system automatically creates corresponding trade requests (with trade request category Hedge). These trade requests are automatically transferred to the SAP Trading Platform Integration application. The trade requests are then sent to an external trading platform where the trader confirms them and concludes financial transactions. The financial transactions are transferred back to your system. For more information, see also Integration with External Trading Platforms.

- 7. The trader checks the released hedge requests using the Process Hedge Requests function.
- 8. If the integration with the trading platform is not activated, the trader closes the required financial transaction (for example, an FX forward transaction) based on the information of the hedge request and creates it in the system, for example, using the Manage Financial Transactions app (app ID F6157).


**Note:**

If you activated the integration of trading platforms in your hedging area, further processing of the trade requests generated for the FX hedge request is done by the SAP Trading Platform Integration application.

**Note:**

Based on the released dedesignation request, the system creates dedesignation business transactions with the status Planned Dedesignation. Using the Release Hedging Business Transactions function, you release the dedesignation. Depending on the settings in the dedesignation request, the reclassification is done immediately or on a planned dedesignation date.

The relevant hedging classification and the hedge request ID (when the transaction is created to fulfill a hedge request) need to be entered on the Administration tab in the financial transaction.

- 9. When hedge accounting is activated for the hedging area, now the automated designation process of Hedge Accounting for Exposure Items starts. Based on the data of the financial transaction (company code, valuation area, currency, value date, and hedging classification), the system determines the relevant exposure item and creates the following entities automatically according to the settings made in the hedging area:

Hedging relationship(s)

Hedged item(s)

Hedging instrument(s)

For more information, see: Hedge Accounting for Exposure Items

- 10. If you use an FX option as hedging instrument, the underlying FX spot transaction is assigned automatically to the exposure item with the exercise of the FX option. The FX spot transaction also inherits the hedge request ID. The exposure item assignment of the FX option is terminated. This ensures the correct calculation of the key figure Net Hedges in the Hedge Management Cockpit. In this way, the FX spot transaction is considered in the Net Open Exposure and Net Open Exposure (Incl. HR) key figures in the Hedge Management Cockpit as of the exercise date of the FX option. This enables historical reporting in the Hedge Management Cockpit with a backdated key date.

FX option contributes to the net hedges before the exercise date.

FX spot transaction (underlying) contributes to the net hedges as of the exercise date of the FX option.

- 11. If a financial transaction is reversed, that is assigned to a completed FX hedge request, the system automatically adjusts the FX hedge request amount by the amount of the reversed financial transaction. However, the initial amount of the FX hedge request is still displayed in the new field Initial Hedge Request Amount in the FX hedge request.


Due to the reversal of the hedging instruments and the adjustment of the hedge request amount, the key figures in the Hedge Management Cockpit, such as the key figures Net Hedges, Hedge for Hedge Request, and Original Amount of Hedge Request, are also adjusted accordingly. This ensures that the Open Hedge Request Amount remains zero.

[figure TRM04-F002 - If all financial transactions of this FX hedge request have been reversed, the FX hedge request amount is adjusted by the amount of the reversed financial transaction and the status of the FX hedge request changes from Completed to Withdrawn. However, the initial amount of the FX hedge request is still displayed in the additional field Initial Hedge Request Amount in the FX hedge request.]

If all financial transactions of this FX hedge request have been reversed, the FX hedge request amount is adjusted by the amount of the reversed financial transaction and the status of the FX hedge request changes from Completed to Withdrawn. However, the initial amount of the FX hedge request is still displayed in the additional field Initial Hedge Request Amount in the FX hedge request.

For FX hedge request with instrument category FX Collar and FX Swap (available for hedging areas without hedge accounting and with risk-free currency = local currency), the status of the FX hedge request is also only changed to Withdrawn after all financial transactions have been reversed, and the hedge request amount is adjusted only after the reversal of both legs of an FX swap.

If there is also a related trade request with the status Completed, the status of the related trade request remains Completed and the amounts of the trade request are also not adjusted. However, you can see the status Reversed of the affected financial transactions on the Financial Transaction tab in the trade request.

- 12. Check your net open exposures and all other relevant key figures using the Hedge Management Cockpit (using the app on the SAP Fiori launchpad or transaction TOENE).

- 13. Restart the process on a regular basis.

##### Terms in Hedge Management and Accounting of Net Open Exposures (FX Risk)

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Terms in Hedge Management and Accounting of Net Open Exposures (FX Risk) | L4 | trm04 p.10 | loio `9d78a856c5e46c15e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9d78a856c5e46c15e10000000a441470.html?locale=en-US)

Here you get more details about terms used in Hedge Management and Accounting of Net Open Exposures (FX Risk) process.

Hedging Classification The hedging classification is an entity that is used in hedge management and accounting.

You define the hedging classifications in Customizing under Treasury and Risk Management General Settings Hedge Management Define Hedging Classifications .

The freely definable hedging classifications are used in the following way:

In the definition of your hedging areas, you assign the relevant hedging classifications on the General Settings tab.

You can assign n hedging classifications to a hedging area.

A hedging classification that is active for hedge accounting can only be assigned to one hedging area that is relevant for hedge accounting.

Hedging classifications that are inactive for hedge accounting can be assigned to n hedging areas.

On the Hedge Accounting II tab, you assign the hedging profiles and the designation types as a function of the hedging classification.

You assign the hedging classifications to your hedging instruments in the financial transaction data on the Administration tab.

If the hedging classification is active for hedge accounting, this information is relevant for the automated designation process. Using the data from the financial transaction, including the hedging classification, the system can identify the relevant hedging area version and the relevant exposure

| |item so that the hedged item, hedging instrument, hedging relationship, and the planned designation flows can be created according to your settings for the hedging area. You can use the hedging classification as a characteristic of the financial instrument that is relevant during the automated determination of account assignment references for financial transactions used as hedging instruments. This allows different account assignment references to be determined for different hedging categories, such as cash flow hedges and fair value hedges. You define the rules for the automated determination of the account assignment references in Customizing under Transaction Manager General Settings Accounting Link to Other Accounting Components Define Account Assignment Reference Determination (OTC Transactions)  .|
|---|---|
|Analysis Item|The analysis item reflects the granularity on which you monitor and hedge your FX exposures in the hedge management cockpit (transaction TOENE). The following different kinds of analysis item definition are available: By Time Period By Reference For more information, see also Analysis Item. |
|Exposure Item|The exposure items represent the exposures of an analysis item and are saved on the database. You create the exposure item(s) using the snapshot function. Exposure items for hedging areas with analysis item definition By Time Periods The exposure items are created in relation to the exposure aggregation level of the hedging area. The saved exposure items are valuation area independent, they have an exposure item ID, per date an amount and also carry the information to which hedging area version they belong. The due date of an exposure item is the end date of the relevant time period. Exposure items for hedging areas with analysis item definition By Reference These kinds of exposure items refer to exact one nonaggregated exposure position (which does not have a Planning Period or Planning Year). The differentiation criteria of these exposure items are: Company Code Risk-Free Currency Currency Object Category (technical name of exposure source) Object Reference (ID of the exposure position)|


| |These exposure items are valuation area independent, they have an exposure item ID and description, they have an amount, and a specific due date. The due date can change over the lifetime of the exposure item. The exposure items are necessary for the Hedge Accounting process. During the automated designation process the hedged exposure item is identified automatically and the corresponding exposure subitems (which represent the hedged part of the exposure item) are created and assigned to the hedged items.|
|---|---|
|Designation Level|Exposure Aggregation Level / Possible Designation Level: Only Net - Net Exposure Item (not supported); Only Gross - Gross Exposure Item with Larger Absolute Value; Gross and Net - Gross Exposure Item with Larger Absolute Value. The designation level is used to determine whether the hedging instruments are designated to the net exposure item or to the gross exposure item with the larger absolute value of the relevant analysis item. In this way, it also dictates the exposure items to which the exposure subitems refer. The possible designation levels depend on the exposure aggregation level of the hedging area:|
|Exposure Aggregation Level|Exposure Aggregation Level|
|Exposure Subitem|The exposure subitem is automatically created and assigned to the hedged item in a hedging relationship. How many exposure subitems are created for a hedging instrument depends on the settings for designation splitting in the hedging area data. (Cardinality: exposure item : exposure subitem = 1 : n) The due date of the exposure subitem is derived from the relevant reclassification offset category and can be different from the end date (dedesignation date) of the hedging relationship. The due date of the exposure subitem is the reclassification date for the hedging reserve/cost of hedging reserve. Reclassification of the hedging reserve and cost of hedging reserve can, therefore, be performed after the dedesignation date of the hedging relationship. The exposure subitem is identified by the combination of company code, valuation area, and exposure subitem ID. The exposure subitem has its own ID number range and is based on the product category 991.|
|Hedging Area|The hedging area is an entity that represents a section of your hedging policy. It defines the level of granularity on which you want to monitor your foreign exchange risk. It also controls which exposures and hedging instruments are relevant for the hedging area.|


|Hedging Relationship|If you want to execute hedge accounting for your hedging activities, the hedged item and the hedging instrument need to be assigned to each other in the hedging relationship. The hedging relationship starts with the designation. You can execute prospective effectiveness tests and create hedge documentation for the hedging relationship. The hedging relationship of the hedge accounting for exposure items process can have the following statuses: Designation Planned Designated Dedesignation Planned Dedesignated Designation Transfer Planned Designation Transfer|
|---|---|
|Hedging Reserve|Other comprehensive income that is calculated based on the result of the lower-of test of the hypothetical derivative and the financial transaction, and on the value adjustment of the financial transaction. The hedging reserve is also based on the relevant hedge accounting rule. It can be calculated based on the spot component. The exposure subitem is a position that is needed when you use the automated designation process for hedge accounting. It represents a valuation-area-specific hedged portion of the exposure item, and it is also used as a carrier for the hedging reserve and cost of hedging reserve for the hedging instrument according to the relevant hedge accounting rule.|
|Cost of Hedging Reserve|Other comprehensive income that is calculated for cash flow hedges with the hedged item category Planned Forecast based on the relevant hedge accounting rule.|
|Reclassification Offset Category|Reclassification Offset Category / Description: 1 max (Due Date HInst; Due Date HInst + DIO - PT); 2 Due Date HInst; 3 max (Due Date HInst + DIO; Due Date HInst + PT). With the reclassification offset category, you specify/calculate the due date of the exposures subitem carrying the hedging reserve and the cost of hedging reserve. The reclassification takes place on the due date of the exposure subitem through derived financial transactions. **Note:** Due date of exposure subitem = end date of exposure subitem|


| |Reclassification Offset Category / Description: 4 Due Date HInst + PT. with Due Date HInst = Due Date of the hedging instrument DIO = Days Inventory Outstanding PT = Payment Term in Days You make this setting in the master data of the hedging area on the Hedge Accounting I tab in the Designation Splitting area.|
|---|---|
|Balance Sheet Recognition Date|The balance sheet recognition date is the date on which a receivable or payable is posted to the balance sheet. The balance sheet recognition date is derived from settings made on the Hedge Accounting I tab in the Designation Splitting area. If you have entered 1 in the Balance Sheet Recognition field, this date is then also the starting point for the reclassification of hedging reserve and cost of hedging reserve amounts.|
|Alternative Reclassification Date|Hedging reserve and cost of hedging reserve amounts that were accumulated and frozen on the balance sheet recognition date are reclassified on the alternative reclassification date. This alternative date is derived from the designation splitting settings made on the Hedge Accounting I tab in the hedging area. In general, the date is determined according to the following equation: Due Date of Hedging Instrument + Days Inventory Outstanding Payment Term The following two exceptions can occur: The exposure subitem is a position where alternative date < designation date In this case, the alternative date is considered to be the designation date and no alternative reclassification takes place. The reclassification takes place immediately or on the end date of the exposure subitem, depending on the settings made in the hedging area. Alternative date > exposure subitem date In this case, the alternative date is considered to be the exposure subitem end date and no alternative reclassification takes place. The reclassification takes place on the exposure subitem end date.|
|Risk-Free Currency|Usually, the risk-free currency is the currency of the company code/local currency. Cash flows in this currency do not need to be hedged.|


|Risk Currency|The risk currencies are the currencies that are relevant for hedging in the hedging area. Cash flows in these currencies face an exchange rate risk and need to be hedged.|
|---|---|
|Original Currency of Exposures|The original currency is the real currency of the exposure.|

###### Analysis Item

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Terms in Hedge Management and Accounting of Net Open Exposures (FX Risk) > Analysis Item | L5 | trm04 p.15 | loio `23348758afeaf57ce10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/23348758afeaf57ce10000000a44147b.html?locale=en-US)

**Use**

The analysis items reflect the granularity on which you monitor and hedge your FX exposures in the hedge management cockpit (transaction TOENE).

The following different kinds of analysis item definition are available:

By Time Period

The analysis items are defined by the differentiation criteria and the reporting time pattern of the hedging area. Incoming and outgoing exposures and hedges with the same differentiation criteria and time period belong to the same single analysis item.

The exposure aggregation level of the hedging area decides which exposure items are created for an analysis item.

Further, you can define target quotas for the analysis items in the hedging area.

**Example:**

[figure TRM04-F004 - Example Analysis Item - By Time Periods]

Example Analysis Item - By Time Periods

By Reference

The analysis items are defined by reference. The analysis items contain only one exposure based on a non-aggregated exposure position with an exposure position type for which the aggregation indicator is not set and the No Planning Period and Planning Year indicator is set. The hedging instruments are assigned to the analysis items by adding the hedged exposure item ID on the FX Hedge Management tab to the financial transaction data.

This kind of analysis item is relevant for balance sheet exposures, where you need to assign the hedge to one specific balance sheet position which has a specific due date.

**Note:**

For hedging areas of this kind of analysis item definition the following applies:

The risk-free currency is set to Local Currency by default. This cannot be changed.

The exposure aggregation level is not available.

The reporting time pattern is set to None by default.

Target quotas are not needed, so the target quota is set to None by default. Consequently, on the General Settings tab, the Relevant for Target Quota column is hidden.

On the General Settings tab, the differentiation criteria Currency and Company Code are selected. You cannot add another differentiation criterion.

[figure TRM04-F005 - Example Analysis Item - By Reference]

Example Analysis Item - By Reference

###### Exposure Item

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Terms in Hedge Management and Accounting of Net Open Exposures (FX Risk) > Exposure Item | L5 | trm04 p.16 | loio `f6c78958bbc5f57ce10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f6c78958bbc5f57ce10000000a44147b.html?locale=en-US)

The exposure items represent the exposures of an analysis item and are saved on the database. You create the exposure item(s) using the snapshot function.

Exposure items for hedging areas with analysis item definition By Time Periods

The exposure items are created in relation to the exposure aggregation level of the hedging area.

The saved exposure items are valuation area independent, they have an exposure item ID, per date an amount and also carry the information to which hedging area version they belong. The due date of an exposure item is the end date of the

relevant time period.

Exposure items for hedging areas with analysis item definition By Reference

These kinds of exposure items refer to exact one non-aggregated exposure position (which does not have a Planning Period or Planning Year). The differentiation criteria of these exposure items are:

Company Code

Risk-Free Currency

Currency

Object Category (technical name of exposure source)

Object Reference (ID of the exposure position)

These exposure items are valuation area independent, they have an exposure item ID and description, they have an amount, and a specific due date. The due date can change over the lifetime of the exposure item.

The exposure items are necessary for the Hedge Accounting process. During the automated designation process the hedged exposure item is identified automatically and the corresponding exposure subitems (which represent the hedged part of the exposure item) are created and assigned to the hedged items.

##### Settings for Hedge Management

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management | L4 | trm04 p.17 | loio `39450b4b6dc84b70a2e1f8451d3837f0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/39450b4b6dc84b70a2e1f8451d3837f0.html?locale=en-US)

For setting up the Hedge Management process you need to make some settings in Customizing and you need to define your hedging areas.

Customizing for Hedge Management

Defining Time Patterns for Target Quotas

Define Hedging Areas

Manage Layouts

###### Customizing for Hedge Management

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Customizing for Hedge Management | L5 | trm04 p.17 | loio `fd8aad56a0a98f53e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fd8aad56a0a98f53e10000000a441470.html?locale=en-US)

**Hedging Classification**

Define hedging classifications

You define your hedging classifications in Customizing for Treasury and Risk Management under Transaction Manager General Settings Hedge Management Define Hedging Classifications .

Make the hedging classification available in transaction management

The hedging classification is available in the financial transaction data on the Administration tab for the following product categories:

Foreign Exchange (600)

OTC Options (760)

You control how the fields appear on the tab in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management Define Field Selection using the Hedging Classification field

group (158).

**Customize Values for Assignment, Characteristics, and Internal Reference Fields**

You can use the Assignment, Characteristics, and Internal Reference fields available on the Administration tab for financial transaction data to derive hedging classifications automatically. In this case, you can define the possible values for the fields in Customizing. To ensure the correct derivation of the hedging classification, you can activate the check for product types that are allowed as hedging instruments within the process. The check compares the entered field value with the values defined in Customizing. If a user enters a value in a field in the financial transaction data that is not available for that field in Customizing, the system issues a message as follows:

If the financial transaction has been created before the valid-from date of the check, the systems issues a warning message. You can still save the financial transaction.

If the financial transaction has been created after the valid-from date of the check, the system issues an error message, and you cannot save the financial transaction.

- 1. Define field values

You define the values for the Assignment, Characteristics, and Internal Reference field in the Customizing activities Define Values for Assignment Field, Define Values for Characteristics Field, and Define Values for Internal Reference Field under


Transaction Manager General Settings Transaction Management Values for Fields on Administration Tab . These values are available in the input help of the fields on the Administration tab for financial transaction data. However, you can still enter other texts in these fields.

- 2. Activate check


In Customizing under Transaction Manager General Settings Transaction Management Values for Fields on Administration Tab Activate Check of Entered Values for Product Types/Fields , you can activate a check that does not

allow the entry of texts other than the values defined in Customizing for financial transactions of product types that are available as hedging instruments in the Hedge Management and Accounting of Exposure Items process.

**Automatic Derivation of Hedging Classification**

You can define rules for the automatic derivation of hedging classifications during the creation of financial transactions used as hedging instruments within the Hedge Management and Accounting of Net Open Exposure (FX Risk) process.

In Customizing for Transaction Manager under General Settings Transaction Management Derivation of Hedging Classification , the following Customizing activities are available:

Define Derivation Rules for Hedging Classifications

You can define derivation rules, moves, and/or clears to derive the hedging classification, dependent on the values of the following source fields:

ASSIGNMENT Assignment

BEHALF_OF_COMPANY On Behalf of Company Code

BUSINESS_AREA Business Area

CHARACTERISTICS Characteristics

COMPANY_CODE Company Code

COST_CENTER Cost Center

COUNTRY Country/Region Key

CURRENCY_IN Currency of Incoming Side

CURRENCY_OUT Currency of Outgoing Side

HEDGE_CLASS Hedging Classification

HEDGE_REQUEST_ID Hedge Request ID

PORTFOLIO Portfolio

INTERNAL_REFERENCE Internal Reference

PROFIT_CENTER Profit Center

SEGMENT Segment for Segmental Reporting

WBS_ELEMENT WBS Element

DEAL_TYPE Financial Transaction Type

DEAL_CATEGORY Transaction Category

PRODUCT_CATEGORY Product Category

PRODUCT_TYPE Product Type

You can also define an enhancement. In the case of an enhancement, you provide the business logic in the BAdI: Derivation of Hedging Classification provided by SAP to specify how the target fields are derived from the source fields. You can make the use of an enhancement dependent on the fulfillment of a condition.

The automatic derivation is called during the creation of the financial transactions at the latest point in time before the financial transaction is saved.

Additional Notes

If the derivation result is a hedging classification that does not exist, it is cleared and a warning message is issued. It is not possible to enter an invalid hedging classification.

In this case, the correct hedging classification needs to be entered manually.

If a hedge request ID is entered in the financial transaction, and the derivation result is a hedging classification that differs from the hedging classification entered in the hedge request, the system issues a warning message, but the derived value is not cleared. Consequently, it is possible to enter a deviating hedging classification.

After the financial transaction has been created by the Treasury Specialist - Front Office and the derivation of the hedging classification is finished, the Treasury Specialist - Back Office (or another person authorized to change financial transaction data) can manually change the automatically derived hedging classification.

BAdI: Derivation of Hedging Classification

You can use the Business Add-In (BAdI) BADI_TPM_DERIVE_HCLASS to derive the hedging classification for your financial transactions.

This BAdI is called when a financial transaction is saved and you have defined an enhancement step under Define Derivation Rules for Hedging Classification.

**Additional Fields**

The following fields are available in transaction management on the Administration tab in the financial transaction data:

Portfolio

Profit Center

Cost Center

WBS Element

Business Area

Segment

On Behalf of Company

Country/Region

If you want to use one or more of these fields as differentiation criteria in the hedging area, you have to do the following:

- 1. Make the additional fields available in transaction management

You control how the fields appear on the tab in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management Define Field Selection using the following field groups:

115 Portfolio

- 159 Profit Center

- 160 Cost Center

- 161 WBS Element

- 162 Business Area

- 163 Country/Region

- 164 Segment

- 165 On Behalf of Company


- 2. Use the additional fields as differentiation criteria in Exposure Management 2.0


**Note:**

Ensure that the fields that you want to use as differentiation criteria are filled in the data of the financial transactions.

The fields are available as additional differentiation criteria for your exposure positions types in Customizing for Treasury and Risk Management under Transaction Manager General Settings Exposure Management 2.0 Define Exposure Position Types .

**Note:**

Ensure that the fields that are used as differentiation criteria are filled in the data of your raw exposures.

**Hedge Request ID**

In addition, you have to make the Hedge Request ID field available on the Administration tab in the financial transaction data. This field is then shown in the Position Assignment area.

You control how the fields appear on the tab in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management Define Field Selection using the following field group:

166 Hedge Request ID

**Target Quotas**

If you want to define target quotas for the hedge quotas in the hedging area master data, you first have to create one or more target quota types in Customizing for Treasury and Risk Management under Transaction Manager General Settings Hedge Management Define Target Quota Types .

You have to enter a name and a description as well as a target quota category.

The target quota category defines the kind of target quota. The target quota can be one of the following:

Limit

One limit as a percentage

Band

A lower limit (first limit) and an upper limit (second limit) define the target quota zone.

Target Limit Within Band

A target limit (target quota) within a lower limit (lower quota) and upper limit (upper quota) of a target quota band.

Secondly, you have to define a time pattern for the master data target quota under Defining Time Patterns for Target Quotas (transaction TOE_TIME_PATTERN).

**Authorization Groups**

In the Customizing activity Define Authorization Groups for Hedging Areas, you define authorization groups for your hedging areas.

You must assign the authorization groups in the hedging area master data.

The authorization objects Hedging Area (T_TOE_HA), Hedge Management: Snapshot (T_TOESNP), Hedge Management Cockpit (T_TOE_HMC), Authorization Object for Hedge Requests (T_TOE_HR), and Authorization Object for Exposure Items (T_TOE_EXI) use the authorization group for hedging areas as an authorization field.

- 1. Choose New Entries.
- 2. Enter a 5-digit name for the authorization group and a description.
- 3. When you have entered all necessary authorization groups, save your entries.


**Define Rounding Rules**

You define rounding rules in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management Currencies Define Rounding Rules .

In this Customizing activity, you create rounding rules.

**Assign Rounding Rules and Tolerances**

You assign the rounding rules and tolerances in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management Currencies Assign Rounding Rules and Tolerances .

In this Customizing activity, you assign special rounding rules and tolerances to currencies relevant for the calculation of the opposite amount in FX transactions.

- 1. Choose New Entries.
- 2. Enter the company code.
- 3. Enter the currency.
- 4. Choose the rounding rule.
- 5. Enter the tolerance in percent for manual changes to the calculated opposite amounts of an FX transaction.


**Note:**

You can enter a tolerance for a currency without assigning a rounding rule.

If you do not enter a tolerance, you cannot change the calculated opposite amounts.

**Define Hedge Request Reasons**

In this Customizing activity, you define reasons for hedge requests.

**Business Add-In to Influence Automatic Hedge Request Creation**

With the BAdI: Influence Automatic Hedge Request Creation (BADI_TOE_HREQ_CREATOR), you can determine the following dates for hedge requests created automatically:

Value date

Expiry date

Fixing date

If the Custom via BAdI value is entered in the Value Date field on the FX Hedge Request tab in the relevant hedging area, the BAdI is called during the automated creation of the hedge request.

**Business Add-In for a Custom Subscreen in the Hedge Request**

With the BAdI: Customer Subscreen in Hedge Request (BADI_TOE_HREQ_SCREEN), you can add an additional screen area in hedge requests of the Hedge Management of Net Open Exposures process. The BAdI is always called when the General tab of a hedge request is displayed.

**Hedge Accounting**

If you would like to do hedge accounting and use the automated designation process, you have to make the necessary settings (see Settings for Hedge Accounting for Exposure Items).

###### Defining Time Patterns for Target Quotas

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Defining Time Patterns for Target Quotas | L5 | trm04 p.22 | loio `3e6b5358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3e6b5358bae84442e10000000a4450e5.html?locale=en-US)

**Use**

The time pattern that you define here is relevant for the target quota table of the hedging area.

Features

None

If you choose None, the target quota table has one single field in which to enter the target quota for the combinations of differentiation criteria relevant for target quotas.

If you choose Calendar-Related, you can define a relative time pattern or an absolute time pattern:

Relative Time Pattern

In this case, you specify the number of periods and the period length (Day, Month, Quarter, or Year) for which you want to enter the target quotas, such as 12 months, 4 quarters.

**Note:**

**Note:**

For the period length Day, the maximum permitted number of periods is 62.

In the target quota table, you can enter target quotas for each period for every combination of differentiation criteria relevant for target quotas.

Absolute Time Pattern

If you set the Absolute Time Pattern indicator, you define an absolute time pattern.

You can also choose to add periods until the End of Last Quarter or the End of Last Year. The system then adds periods to the defined number of periods until the end of the last quarter or year is reached.

**Example:**

The overall target quota period starts with the valid-from date 01.05.2000 of the hedging area version.

Number of Periods: 50

Period Length: Month

If you do not make a setting in the Add Periods Until field, the overall target quota period ends with the period April 2005.

Add Periods Until: End of Last Quarter

If you make this setting in the Add Periods Until field, the overall target quota period ends with the period June 2005.

Add Periods Until: End of Last Year

If you make this setting in the Add Periods Until field, the overall target quota period ends with the period December 2005.

###### Define Hedging Areas

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas | L5 | trm04 p.23 | loio `0f9ba95626c76b15e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f9ba95626c76b15e10000000a441470.html?locale=en-US)

**Use**

The hedging area is an entity that represents a section of your hedging policy. In the hedging area, you define the level of granularity with which you want to monitor your foreign exchange risk. You also specify in the hedging area which exposures and hedging instruments are relevant for the hedging area.

The hedging area is the basic master data of Hedge Management reporting. It controls the execution of the Hedge Management Cockpit (transaction TOENE).

In the hedging area, you define the following:

The level of granularity with which you want to monitor your foreign exchange risk.

Incoming and outgoing exposures are aggregated according to the differentiation criteria and reporting time pattern. The exposure aggregation level decides whether they are saved as net or gross exposure items. Please note that the Only Net exposure aggregation level is currently not supported for designation purposes.

Which exposures and hedging instruments are selected by defining the relevant company codes, hedging classifications, risk currencies, and the filters for exposures and hedges.

When you use the automated designation process for exposure items, you mark the hedging area as hedge-accountingrelevant and enter the necessary data (that is, the product type for exposure subitems, the settings for designation level, designation activation and designation splitting on the Hedge Accounting I tab and for the designation control on the Hedge Accounting II tab).

Define and enter the target quota tables relevant for the hedging area.

The hedging area is versioned. Every version of a hedging area has a different valid-from date.

**Note:**

You can only change the latest version of a hedging area if there is no snapshot for this latest version. If changes to the latest version are no longer possible, but changes to the hedging area are needed, you have to create a new version of the hedging area.

[figure TRM04-F007 - Overview of the Hedging Area]

Overview of the Hedging Area

The hedging area consists of the following tabs:

Hedging Area: Main Data

Hedging Area: General Data

Hedging Area: Currencies

Hedging Area: Filters for Exposures

Hedging Area: Filters for Hedges

Hedging Area: Target Quotas

Hedging Area: FX Hedge Request

- Hedging Area: Hedge Accounting I

- Hedging Area: Hedge Accounting II


Version History

On this tab, you can see the list of versions of the hedging area including information on the creation and the last change.

**Integration**

|Authorization Object|Remarks|
|---|---|
|T_TOEHA Hedging Area|This authorization object enables you to restrict who can display or change hedging areas using function Define Hedging Areas (transaction TOE_HEDGING_AREA). You control the authorization for maintaining hedging areas by authorization group, hedging area data group, and activity.|


**Prerequisites**

See also: Customizing for Hedge Management

**Activities**

Creating a Hedging Area

Changing a Hedging Area Version

Creating a New Version for an Existing Hedging Area

Displaying a Hedging Area Version

###### Hedging Area: Main Data

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Main Data | L6 | trm04 p.26 | loio `afe73d5881129244e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/afe73d5881129244e10000000a4450e5.html?locale=en-US)

**Analysis Item Definition**

The analysis items reflect the granularity on which you monitor and hedge your FX exposures in the hedge management cockpit (transaction TOENE).

The following different kinds of analysis item definition are available:

By Time Period

The analysis items are defined by the differentiation criteria and the reporting time pattern of the hedging area. Incoming and outgoing exposures and hedges with the same differentiation criteria and time period belong to the same single analysis item.

The exposure aggregation level of the hedging area decides which exposure items are created for an analysis item.

Further, you can define target quotas for the analysis items in the hedging area.

**Example:**

[figure TRM04-F008 - Example Analysis Item - By Time Periods]

Example Analysis Item - By Time Periods

By Reference

The analysis items are defined by reference. The analysis items contain only one exposure based on a non-aggregated exposure position with an exposure position type for which the aggregation indicator is not set and the No Planning Period and Planning Year indicator is set. The hedging instruments are assigned to the analysis items by adding the hedged exposure item ID on the FX Hedge Management tab to the financial transaction data.

This kind of analysis item is relevant for balance sheet exposures, where you need to assign the hedge to one specific balance sheet position which has a specific due date.

**Note:**

For hedging areas of this kind of analysis item definition the following applies:

The risk-free currency is set to Local Currency by default. This cannot be changed.

The exposure aggregation level is not available.

The reporting time pattern is set to None by default.

Target quotas are not needed, so the target quota is set to None by default. Consequently, on the General Settings tab, the Relevant for Target Quota column is hidden.

On the General Settings tab, the differentiation criteria Currency and Company Code are selected. You cannot add another differentiation criterion.

[figure TRM04-F009 - Example Analysis Item - By Reference]

Example Analysis Item - By Reference

**Risk-Free Currency**

Local Currency

When you choose the local currency as a risk-free currency, the local currency of the company code is the risk-free currency of the company code. In this case, it is possible that you have different risk-free currencies in the hedging area.

When you choose this option, the company code is a mandatory differentiation criterion.

Important information: If the hedging area is relevant for hedge accounting, you must choose this option.

Currency Defined by the Source

The target currency is derived from the currency pair of the exposure item.

This option activates cross-currency hedging.

If the source is Exposure Management, the risk-free currency is the target currency.

If the source is Cash Management, the risk-free currency is the company code currency.

**Tip:**

If the hedging area is relevant for Hedge Accounting, you must choose either the option Local Currency or the option Currency Defined by the Source.

**Reporting Time Pattern**

The reporting time pattern are relevant for the reporting of exposures and hedging instruments for hedging area with analysis item definition By Time Periods in the Hedge Management Cockpit (transaction TOENE). For hedging areas with analysis item definition By Reference the reporting time pattern are automatically set to None.

If you choose None, you have one single time bucket, which aggregates exposures and hedging instruments across all due dates.

If you choose Calendar-Related, you can define a relative reporting time pattern or an absolute reporting time pattern:

Relative Time Pattern

In this case, you specify the number of periods and the period length (Day, Month, Quarter, or Year) into which you want exposures and hedges to be grouped for reporting, such as 12 months, 4 quarters. In addition, you can choose to add periods until the End of Last Quarter or the End of Last Year: The system then adds periods to the defined number of periods until the end of the last quarter or year is reached.

**Note:**

For the period length Day, the maximum permitted number of periods is 62.

If you choose period length Day, you must select the exposures for this hedging area from the data source E_EM2 Exposure Management 2.0 and the exposure type of the selected exposure positions must have the Due Date as additional differentiation criterion.

With the relative time pattern, the reporting period in the Hedge Management Cockpit (transaction TOENE) always starts with the key date entered in the transaction. The reporting period end depends on the above-mentioned settings.

**Example:**

Reporting start date is the key date in the Hedge Management Cockpit: 01.06.2001

Number of Periods: 50

Period Length: Month

Add Period Until

No entry is made in this field

With this setting, the last reporting period is May 2006.

End of Last Quarter

With this setting, the last reporting period is June 2006

End of Last Year

With this setting, the last reporting period is December 2006.

Absolute Time Pattern

In this case, you also specify the number of periods and the period length (Month, Quarter, or Year) into which you want exposures and hedges to be grouped for reporting, such as 12 months, 4 quarters. In addition, you set the Absolute Time Pattern indicator.

**Note:**

You can also choose to add periods until the End of Last Quarter or the End of Last Year. The system then adds periods to the defined number of periods until the end of the last quarter or year is reached.

With the absolute time pattern, you define an overall reporting period for the hedging area version. This overall reporting period starts with the valid-from date of the hedging area version and ends according to the abovementioned settings.

The reporting period in the Hedge Management Cockpit (transaction TOENE) starts with the key date entered in the transaction. The last reporting period is the last period of the overall reporting period.

**Example:**

The overall reporting period starts with the valid-from date 01.05.2000 of the hedging area version.

When you execute the Hedge Management Cockpit, the start date is the starting date of the reporting period.

Number of Periods: 50

Length: Month

Add Periods Until

No entry is made in this field

If you do not make a setting in the Add Periods Until field, the overall reporting period ends with the period April 2005. This period is also the last period of the reporting period in the Hedge Management Cockpit.

End of Last Quarter

With this setting in the Add Periods Until field, the overall target quota period ends with the period June 2005. This period is also the last period of the reporting period in the Hedge Management Cockpit.

End of Last Year

With this setting in the Add Periods Until field, the overall target quota period ends with the period December 2005. This period is also the last period of the reporting period in the Hedge Management Cockpit.

**Integration**

Hedge Accounting

If you want to use the automated designation process for exposure items for this hedging area, you have to select the Hedge Accounting checkbox. Now you can choose the default product type for the exposure subitems that were created during the automated designation process. In addition, the Hedge Accounting I and Hedge Accounting II tabs accept your input. In particular, on these tabs, among other important settings for hedge accounting, you can override the default product type defined here for the exposure subitems on the Hedge Accounting II tab.

For more information, see:

Automated Designation Process

Settings for Hedge Accounting for Exposure Items

Activate SAP Trading Platform Integration

Set this indicator to activate the integration with the SAP Trading Platform Integration application.

When you set this indicator, hedge requests with the FX Hedge Request hedge request category are transferred to the trade request after their status has been set to Released.

The SAP Trading Platform Integration application can then receive the trade requests and process them further before they are sent to an external trading platform.

When you do not set this indicator, hedge requests with the hedge request category FX Hedge Request can be processed only with the Process Hedge Requests app.

**Consideration of Financial Transactions**

Consider Hedging Instrument Until

Specifies - in connection with the key date entered - the date until which hedging instruments are considered in the key figures of the Hedge Management Cockpit.

Select one of the following options:

End of Period

The amount of the hedging instruments reflected in the key figures of the Hedge Management Cockpit is calculated up to the end of the period defined in your hedging area even if the value date of the hedging instruments may have already passed at the time the report is started.

Value Date of Hedging Instrument

The amounts of the hedging instruments are considered in the Hedge Management Cockpit until their value date. After the value date of the hedging instruments has passed, their amounts are no longer considered in the key figures of the Hedge Management Cockpit, even if the period defined in your hedging area may not have ended.

Date Used to Determine Exp. Item for FX Option

Defines which date is used to determine the exposure item during the automated designation process of an FX option.

Select one of the following options:

Value Date of Underlying

In this case, the exposure item is determined based on the value date of the underlying transaction of the FX option.

Exercise Date of FX Option

In this case, the exposure item is determined based on the exercise date of the FX option.

The date you specify here will also be applied to due date shifts according to the settings on the General Settings tab and your designation splitting settings on the Hedge Accounting I tab. The date specified is applied as the basis value for shifting to the correct exposure item period.

This setting also has an impact on the dates of the hypothetical derivative, dependent on the setting in the FX Option: Dates of Hypothetical Derivative field in the relevant hedge accounting calculation type:

This setting controls, how the dates of the hypothetical derivative are determined in the case of FX options used as hedging instruments. The hypothetical derivative has the following dates:

Start Date

The start date of the hypothetical derivative is the designation date.

Exercise Date

If no shifts are defined in the hedging area, the exercise date of the hypothetical derivative is the exercise date of the hedging instrument.

Value Date

Due date of the underlying of the hedging instrument.

If a due date shift or a payment term for an extended period for the hypothetical derivative have been defined in the hedging area, the exercise date and the value date of the hypothetical derivative are also affected. In the case of a combination, the due date shift is applied first and the payment term shift afterwards. Depending on the setting in this field, the exercise date and the value date of the hypothetical derivative are determined in the following ways:

Default

The due date shift is relevant for either the exercise date or the value date of the underlying, depending on the setting Date to Determine Exposure Item for FX Option in the hedging area. The due date shift is applied to the corresponding date of the hypothetical derivative. The other date is shifted in parallel by the same number of days.

Exception: If the relevant date is the value date of the underlying and the underlying will be designated into the hedging relationship, the exercise date is not shifted.

Shift Only Value Date of Underlying

The exercise date of the hypothetical derivative is not shifted.

Shift of the value date of the hypothetical derivative:

If the due date shift is relevant for the value date of the underlying, the value date of the hypothetical derivative is shifted in the same way.

If the due date shift is relevant for the exercise date, the value date of the hypothetical derivative is shifted to the date to which the exercise date would be shifted.

Exception: If the shift results in a value date that is earlier than the exercise date, the parallel shift of the default setting is performed instead.

Date for Determining Exp.Itm for Non-Del. Inst.

Defines which date is used to determine the exposure item during the automated designation process of a non-deliverable instrument, such as an NDF.

Select one of the following options:

Value Date

In this case, the exposure item is determined based on the value date of the financial transaction.

Value date is the default setting for this drop-down field.

Fixing Date

In this case, the exposure item is determined based on the fixing date of the financial transaction.

**Note:**

You cannot add this setting to existing hedging areas. To be able to make this setting, you have to create a new hedging area.

The date you choose here will also be applied to your due date shift settings on the General Settings tab as well as to your designation splitting settings on the Hedge Accounting I tab. The date specified is applied as the basis value for shifting to

the correct exposure item period.

This setting also influences the planned dedesignation date. Usually, the planned dedesignation date is at the value date of the financial transaction. If you choose Fixing Date in this field, the planned dedesignation date of the hedging relationship is also at the fixing date.

**Target Quota**

Target quotas are not relevant for hedging areas with analysis item definition By Reference.

For more information about target quotas, see Target Quotas.

###### Exposure Aggregation Level

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Main Data > Exposure Aggregation Level | L7 | trm04 p.33 | loio `21665358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/21665358bae84442e10000000a4450e5.html?locale=en-US)

**Use**

The exposure aggregation level

controls which exposure items are created for an analysis item and saved on the database.

is a basic setting for the possible designation levels, because designation is done for exposure items.

is a basic setting relevant for the target quota definition.

controls the possible exposure display modes in Hedge Management Cockpit, when you choose to see the data based on exposure items.

The exposure aggregation level is automatically set to Net and Gross in the background. With this setting, the exposure items are created as follows:

The incoming and the outgoing gross exposure items and also the net exposure are persisted as exposure items.

Designation in hedge accounting can either be done for net exposure items or for the gross exposure item with larger absolute value.

When you choose this option, you can enter the target quotas for the net hedge quota and also for the gross hedge quota.

Net and gross display is possible in the Hedge Management Cockpit, when you choose to see the data based on exposure items.

###### Reporting Time Pattern

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Main Data > Reporting Time Pattern | L7 | trm04 p.33 | loio `bf675358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bf675358bae84442e10000000a4450e5.html?locale=en-US)

**Use**

The reporting time pattern are relevant for the reporting of exposures and hedging instruments for hedging area with analysis item definition By Time Periods in the Hedge Management Cockpit (transaction TOENE). For hedging areas with analysis item definition By Reference the reporting time pattern are automatically set to None.

If you choose None, you have one single time bucket, which aggregates exposures and hedging instruments across all due dates.

If you choose Calendar-Related, you can define a relative reporting time pattern or an absolute reporting time pattern:

Relative Time Pattern

In this case, you specify the number of periods and the period length (Day, Month, Quarter, or Year) into which you want exposures and hedges to be grouped for reporting, such as 12 months, 4 quarters. In addition, you can choose to add periods until the End of Last Quarter or the End of Last Year: The system then adds periods to the defined

number of periods until the end of the last quarter or year is reached.

**Note:**

For the period length Day, the maximum permitted number of periods is 62.

If you choose period length Day, you must select the exposures for this hedging area from the data source E_EM2 Exposure Management 2.0 and the exposure type of the selected exposure positions must have the Due Date as additional differentiation criterion.

With the relative time pattern, the reporting period in the Hedge Management Cockpit (transaction TOENE) always starts with the key date entered in the transaction. The reporting period end depends on the above-mentioned settings.

**Example:**

Reporting start date is the key date in the Hedge Management Cockpit: 01.06.2001

Number of Periods: 50

Period Length: Month

Add Period Until

No entry is made in this field

With this setting, the last reporting period is May 2006.

End of Last Quarter

With this setting, the last reporting period is June 2006

End of Last Year

With this setting, the last reporting period is December 2006.

Absolute Time Pattern

In this case, you also specify the number of periods and the period length (Month, Quarter, or Year) into which you want exposures and hedges to be grouped for reporting, such as 12 months, 4 quarters. In addition, you set the Absolute Time Pattern indicator.

**Note:**

You can also choose to add periods until the End of Last Quarter or the End of Last Year. The system then adds periods to the defined number of periods until the end of the last quarter or year is reached.

With the absolute time pattern, you define an overall reporting period for the hedging area version. This overall reporting period starts with the valid-from date of the hedging area version and ends according to the abovementioned settings.

The reporting period in the Hedge Management Cockpit (transaction TOENE) starts with the key date entered in the transaction. The last reporting period is the last period of the overall reporting period.

**Example:**

The overall reporting period starts with the valid-from date 01.05.2000 of the hedging area version.

When you execute the Hedge Management Cockpit, the start date is the starting date of the reporting period.

Number of Periods: 50

Length: Month

Add Periods Until

No entry is made in this field

If you do not make a setting in the Add Periods Until field, the overall reporting period ends with the period April 2005. This period is also the last period of the reporting period in the Hedge Management Cockpit.

End of Last Quarter

With this setting in the Add Periods Until field, the overall target quota period ends with the period June 2005. This period is also the last period of the reporting period in the Hedge Management Cockpit.

End of Last Year

With this setting in the Add Periods Until field, the overall target quota period ends with the period December 2005. This period is also the last period of the reporting period in the Hedge Management Cockpit.

###### Target Quotas

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Main Data > Target Quotas | L7 | trm04 p.35 | loio `97645358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/97645358bae84442e10000000a4450e5.html?locale=en-US)

**Use**

The target quota specifies the desired value for the hedge quota of an FX exposure item. Target quotas are entered in the target quota tables for the hedging area. In the Hedge Management Cockpit app, the relevant target quota is assigned to each analysis item, and target quota-related key figures are calculated. These key figures support you in your hedging decisions. For example, the Amount to Hedge key figure shows the current amount that still needs to be hedged to meet the target quota, taking into account the hedges and hedge requests that have already been created.

Target quota features:

The target quota functionality is based on target quota types that in turn are based on the target quota categories. In general, target quota categories allow you to enter the following three kinds of target quota:

Limit

Band

Target Limit Within Band

For each hedging area, you can define a target quota table for each target quota type.

Target quotas are usually entered on a higher level than the analysis items. This means that you usually do not choose all differentiation criteria of the hedging area as relevant for the target quota definition.

Various settings in the hedging area have an impact on target quota definition and vice versa.

**Example:**

The reporting time pattern of the hedging area is also relevant for the target quota time pattern. When the reporting time pattern is absolute, the time pattern for the target quota also needs to be an absolute time pattern. In addition, the period length of the target quota time pattern needs to be the same or longer than the

period length of the reporting time pattern.

You can define net target quotas or gross target quotas. Net target quotas refer to the relationship of the net exposure to hedges, whereas gross target quotas refer to the relationship of the gross exposure to hedges.

You can enter gross target quotas in the hedging area master data, but the Hedge Management Cockpit does not display gross target quotas.

To use target quotas in the Hedge Management Cockpit, you must choose a layout that contains the key figures related to the target quotas. In this case, the following features are available in the Hedge Management Cockpit:

The target quota-related key figures are calculated and displayed for each analysis item.

During the creation of an FX hedge request, the Hedge Request Amount field is filled automatically. The automatically filled hedge amount is the value of the Amount to Hedge key figure or, in the case of target quota types based on target quota category Band of the Maximum Amount to Hedge field.

If you have additionally made the settings in the hedging area master data on the FX Hedge Request tab, you can use the Automated Request Creation button within the Hedge Management Cockpit to automatically trigger the creation of FX hedge requests for all net open exposures of your hedging area. For more information, see also Hedging Area: FX Hedge Request.

**Note:**

The settings on the FX Hedge Request tab are also considered when you create an FX hedge request manually. This means that the system only enters a value in the Hedge Request Amount field of the manually created FX hedge request if the value of the key figure Amount to Hedge/Max. Amount to Hedge is greater than or equal to

the minimum amount. If the amount is greater than or equal to the minimum amount, the amount is rounded down to the selected unit.

Note: The value date, the default instrument category, and the hedging classification are also filled automatically in the manually created FX hedge request according to the settings on the FX Hedge Request tab.

**Prerequisites**

Configuration

Define target quota types in the Define Target Quota Types Customizing activity available in your configuration environment.

Master Data

Define the time pattern for target quotas using the Defining Time Patterns for Target Quotas app.

**How to Define Target Quotas in the Hedging Area**

- 1. On the Main Data tab in the Target Quota area, make the following settings:


- a. Select the Target Quota radio button.
- b. Insert a new row by choosing Insert Row.
- c. Specify the target quota type.


The target quota types are defined in the Define Target Quota Types configuration activity. Each target quota type has a target quota category that specifies the kind of the target quota.

- d. Specify the time pattern for the relevant target quota. Time patterns are defined in the Define Time Pattern app. Choose a time pattern that fits the reporting time pattern of the hedging area. When the reporting time pattern is absolute, the time pattern for the target quota also needs to be an absolute time pattern. In addition, the period length of the target quota time pattern needs to be the same or longer than the period length of the reporting time pattern.


- 2. On the General Settings tab in the Differentiation Criteria area, you define which differentiation criteria are also relevant for the target quota definition. The following rules apply:

You can mark a differentiation criterion as relevant for target quotas only when the differentiation criterion is marked as relevant for the hedging area.

The currency is the only required differentiation criterion for the target quota definition.

We recommend that you choose as few differentiation criteria as possible as relevant for target quotas to reduce the volume of the target quota table.

- 3. On the Currencies tab, you must enter currency groups in the right-hand column. This setting is relevant for the target quota entry because the target quotas are entered for the currency groups. You define the groups by entering a name. If you enter the same group name for different currencies, they are within the same currency group. You can enter the currency groups manually or you can use the Prefill Currency Groups function. When you use the function, the system enters for each currency the currency name in the Currency Group column. In this way, you have then defined a currency group for each currency. Now you can change the entries. For example, you can assign all currencies for which the same target quotas should apply to the same group.
- 4. On the Target Quotas tab, you maintain the target quotas according to the time pattern and currency groups.


On this tab, you enter the target quotas in the target quota tables for each target quota type relevant for the hedging area.

You can enter the target quotas manually by using the insert target quota function.

You can upload the target quotas from a spreadsheet.

Manual Entry of Target Quotas

- a. Choose the target quota type. You can choose only a target quota type that is assigned to the hedging area on the Main Data tab.

If you have assigned only one target quota type to the hedging area, the target quota type is already entered.

- b. Choose Insert Quota.


On the popup that appears, you can enter the following:

- i. Specify the kind of target quota that you want to enter (either Net or Gross) in the Net/Gross field.
- ii. In the following fields, you can enter the specific combination of differentiation criteria (that are relevant for target quotas) for which you want to enter target quotas.


**Note:**

You can enter gross target quotas in the hedging area master data, but the Hedge Management Cockpit does not display gross target quotas. Therefore, it is recommended to enter net target quotas.

If you do not make entries here, the target quotas entered are relevant for all combinations of the differentiation criteria values.

If you set the Insert Target Quota indicator, only new entries in the target quota table that result from these entries are inserted into the target quota table.

If you set the Update Target Quota indicator, only existing entries in the target quota table are changed according to these entries.

By default, both indicators are set. Only deselect one of them if you want to have the special effect of the other.

- iii. Once you have entered all relevant values, press the Enter key on your keyboard and then choose the Enter pushbutton.

The system creates the target quota lines resulting from your entries. Each line represents a specific combination of the differentiation criteria values.

Enter the target quotas for the defined periods.

Limit

You enter one target quota for each period.

Target Quota Band

You enter the lower and the upper limit for all periods.

Example: If you want to enter a limit of 70%, you enter 70 in the cell.

Target Limit Within Band

You enter a target limit (target quota) within a target quota band:

Lower Quota [%]

Upper Quota [%]

Target Quota [%]

This value must lie between the lower and the upper limit.

The quotas are entered in percent.

- iv. Continue until you have entered all target quota values.
- v. You can change the target quota value in the lines manually.


Upload from Spreadsheet

- i. If you want to upload the target quotas from a spreadsheet, we recommend that you first download the target quota table as a spreadsheet using the export function.
- ii. Enter the values in the downloaded spreadsheet.
- iii. Upload the spreadsheet using the import function.


**Note:**

You have two options for doing this:

You can download the empty table. In this case, you must enter all values of the table manually in the spreadsheet.

You can use the insert target quota function to generate all relevant lines of the target quota table before the download. In this case, you enter only the target quota values in the spreadsheet.

- iv. Save the entries.


**Which Target Quota-Related Key Figures Must be Chosen in the Layout for the Hedge Management Cockpit?**

In the Hedge Management Cockpit, you must choose a layout that contains the target quota-related key figures. Otherwise, the target quotas are not shown in the analysis items and the target quota-related key figures are not calculated.

You create the layout in the Hedge Management Cockpit app, where you choose the Manage Layout button.

In the layout, you must select a target quota type (for which you have entered net target quotas) and the target quotarelated key figures. Which key figures you need to select depends on the target quota category of the selected target quota type:

Target quota-related key figures relevant for target quotas based on target quota category Limit

Target Quota [%]

Target Hedge Amount = Net Exposure * Target Quota (Single Limit) %

Sign of the amount has the opposite direction to that of the exposure.

Amount to Hedge = Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Target quota-related key figures relevant for target quotas based on target quota category Band

Lower Target Quota [%]

Upper Target Quota [%]

Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Lower Target Hedge Amount = Net Exposure * Lower Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Upper Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Min. Amount to Hedge = Lower Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Max. Amount to Hedge = Upper Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Target quota-related key figures relevant for target quotas based on target quota category Target Limit within Band:

Lower Target Quota [%]

Upper Target Quota [%]

Target Quota [%]

Min. Amount to Hedge

Max. Amount to Hedge

Target Hedge Amount = Net Exposure * Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Lower Target Hedge Amount = Net Exposure * Lower Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Upper Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Amount to Hedge = Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

###### Hedging Area: General Settings

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: General Settings | L6 | trm04 p.40 | loio `618b3d58eaa89144e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/618b3d58eaa89144e10000000a4450e5.html?locale=en-US)

The General Settings tab consists of the following three input areas:

**Company Codes**

Enter the relevant company codes for the hedging area.

**Note:**

If you leave the list empty, all existing company codes are relevant for the hedging area.

**Differentiation Criteria**

Differentiation criteria for analysis item definition By Time Periods

Define the level of granularity on which you want to monitor your net open exposures by selecting the corresponding differentiation criteria on the left-hand side.

In the Hedge Management Cockpit, the differentiation criteria - in combination with the reporting time pattern - determine the calculated amounts. The differentiation criteria define the exposure items and groups of hedges relevant for a row in the result list, and the reporting time pattern defines whether the rows are aggregated together in one amount or sorted by their due dates and whether different amounts are calculated for each period. In this way, nominal values of all exposures/hedges that have the same differentiation criteria and are in the same period are aggregated to one single amount. The net open exposure is the difference between the aggregated exposures and the aggregated hedges.

The available differentiation criteria are:

|Currency | Currency Group

The currency is always a differentiation criterion. Unless you choose one of the following differentiation criteria, the exposures and hedges are aggregated on the level of the currency

Company Code

Portfolio

Cost Center

Profit Center

WBS Element

On Behalf of Company Code

Country/Region Key

Segment

Business Area

**Note:**

When you choose a differentiation criterion here, make sure that it is also an additional differentiation criterion for the exposure positions in Exposure Management and that the field is also filled in the financial transaction data of the hedging instruments.

Differentiation criteria for analysis item definition By Reference

The differentiation criteria Currency and Company Code are selected. You cannot add another differentiation criterion.

Target Quota

If you want to enter target quotas, you need to specify which differentiation criteria are relevant for target quotas on the right-hand side.

**Note:**

You can only mark a differentiation criterion as relevant for target quotas when the differentiation criterion is marked as relevant for the hedging area.

The currency is the only required differentiation criteria for the target quota definition.

We recommend that you choose as few differentiation criteria as relevant for target quotas as possible to reduce the volume of the target quota table.

Relevant for Hedge Accounting

You can set the Relevant for Hedge Accounting indicator, for the chosen differentiation criteria. In this case, the differentiation criteria relevant for hedge accounting are available on the Hedge Accounting I tab in the tables for Designation Activation and Designation Splitting.

**Hedging Classifications**

You can choose the hedging classifications that are relevant for a hedging area.

**Note:**

If you leave the list empty, all hedging classifications are then relevant for the hedging area.

Due Date Shift

For hedging areas with analysis item definition By Time Periods, reporting time pattern Calendar-Related, and period length Monthly you can define a due date shift.

You activate the Due Date Shift for a specific hedging classification by assigning one of the following types of due date shift:

BOMN1 - Beginning of Next Month

If you opt for this type, the end date of the hedged item and the value date of the hypothetical derivative (representing the exposure) is shifted to the first day of the following month.

EOMN1 - End of Next Month

If you opt for this value, the end date of the hedged item and the value date of the hypothetical derivative (representing the exposure) is shifted to the last day of the following month.

EOMP1 - End of Previous Month

If you opt for this value, the value date of the hedging instrument selected during the execution of the Hedge Management Cockpit is shifted to the last day of the previous month. This means that the hedging instrument is reported in the previous

month. You can select this value only for hedging classifications that are inactive for hedge accounting. Therefore, it only has an impact on hedge management reporting.

The due date shift allows you to report your hedging instruments in the Hedge Management Cockpit in the following month after the due date of the hedging instrument. This means, that these hedging instruments are used to hedge the exposure items of the following month.

For hedge accounting relevant hedging classifications, the automated designation process considers the due date shift and searches for exposure items in the following month. The end date of the hedged item and the value date of the hypothetical derivative is also affected by the due date shift.

See also: Hypothetical Derivative (Hedge Accounting for Exposure Items)

**Note:**

The due date of the hedging instrument is not changed.

**Example:**

The due date shift BOMN1 - Beginning of Next Month is activated.

You have created hedging instruments in period 10/2018 with a total amount of 300,000 USD. If you have defined the due date shift as BOMN1 in your hedging area, the hedging instruments with a total amount of 300,000 USD are reported in period 11/2018, even though their due date is in 10/2018.

The hedged item gets the 11/01/2018 as end date and the hypothetical derivative gets the 11/01/2018 as value date.

###### On Behalf of Company Code

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: General Settings > On Behalf of Company Code | L7 | trm04 p.42 | loio `b5fe7258782ba007e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b5fe7258782ba007e10000000a441470.html?locale=en-US)

**Use**

When you create a financial transaction on behalf of another company code, you can enter the company code of the other company on the Administration tab in the financial transaction data.

Further, in Exposure Management 2.0, this attribute can be filled for raw exposure line items, and it can be used as a differentiation criterion for exposure positions.

Within a hedging area, you can use this attribute as a differentiation criterion for the analysis items. When you have chosen On Behalf Of as differentiation criterion in the hedging area, you can also use it on the Hedge Accounting I and Hedge Accounting II tabs, so you can have different settings for designation dependent on this field.

**Example**

Within a group of companies, the corporate headquarters and the affiliated companies have different company codes. When the corporate headquarters hedges on behalf of one of the affiliated companies, this can be visualized by entering the company code of the affiliated company on the Administration tab in the financial transaction data of the hedging instrument.

In addition, you add the relevant company code to the raw exposure line items and use it as a differentiation criterion for exposure positions and in the hedging area.

###### Hedging Area: Currencies

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Currencies | L6 | trm04 p.43 | loio `046c5358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/046c5358bae84442e10000000a4450e5.html?locale=en-US)

You must add the foreign currencies that are relevant for hedging in your company.

If you want to enter target quotas, you have to enter currency groups in the right-hand column. You define the groups by entering a name. If you enter the same name for different currencies, they are within the same currency group. You can enter the currency groups manually or you can use the prefill function . When you use the function, the system enters for each currency the currency name in the Currency Group column. In this way, you have then defined a currency group for each currency. Now you can change the entries.

###### Hedging Area: Filters for Exposures

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Filters for Exposures | L6 | trm04 p.43 | loio `ca6c5358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ca6c5358bae84442e10000000a4450e5.html?locale=en-US)

You specify which exposures are relevant for the hedging area by creating one or more filters.

The following data sources for your exposures are available:

E_EM2 - Exposure Management 2.0 (for hedging areas with analysis item definition By Time Periods)

E_EM2REF Exposure Management 2.0 by Reference (for hedging areas with analysis item definition By Reference)

E_FXEM - Foreign Exchange Exposure Management

E_1EXP - Cash Management

**Note:**

If you do not define a filter for exposures, the Hedge Management Cockpit report (transaction TOENE) will not select any exposures for the hedging area.

- 1. Choose .
- 2. In the New Filter for Exposures dialog box, enter a name and a description for the filter and choose the source. For example, choose E_EM2REF Exposure Management 2.0 by Reference for hedging areas with analysis item definition By Reference. Then choose .


- 3. Specify the filter details.


In the Filter-Specific Restrictions of the General Selections area, you can restrict the selection of the exposures by the following criteria:

Company code

Currency

If you have already defined restrictions for the hedging area under Main Data for these criteria, you can restrict only the values relevant to the hedging area.

**Example:**

The hedging area version is relevant for company codes 0001 and 0002, but this filter needs to select only the exposures for company code 0001 because you want to define a second filter relevant for company code 0002.

You cannot enter company code 0003 because the company code is not relevant for this hedging area version.

In the Other Filter-Specific Selections area, you can further define the selected exposures.

Example for data source Exposure Management 2.0:

For enter the following (note that they need to be relevant (valid)):

Exposure position types

**Note:**

The system checks whether the chosen exposure position type matches the analysis item definition of the hedging area.

For reference-based analysis items, the exposure positions need to fulfill the following criteria:

The aggregation indicator is not set.

The No Planning Period and Planning Year indicator is set.

Exposure categories

Company codes used on behalf of other company codes

Exposure position IDs

In addition, you can restrict the selection by the following fields if they also act as differentiation criteria for the exposure positions:

Portfolio

Profit Center

Cost Center

Business Area

WBS Element

Country/Region ID

Segment

Make sure that you define your filters in a way that ensures that you select all exposure positions relevant for this hedging area.

###### Hedging Area: Filters for Hedges

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Filters for Hedges | L6 | trm04 p.44 | loio `7b6d5358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b6d5358bae84442e10000000a4450e5.html?locale=en-US)

You specify which hedging instruments are relevant for the hedging area by creating one or more filters for hedges.

**Note:**

When you do not define a filter for hedges, the Hedge Management Cockpits report (transaction TOENE) will not select any hedges for the hedging area.

- 1. Choose .


- 2. In the New Filter for Hedges dialog box, enter a name and a description for the filter and choose the source H_TM Transaction Management. Then choose .
- 3. Specify the filter details.


In the Filter-Specific Restrictions of the General Selections area, you can restrict the selection of the hedging instruments by the following criteria:

Company Code

Currency

Hedging Classification

When you already have defined restriction for the hedging area in the Main Data for these criteria you can only restrict the hedging area relevant values.

**Example:**

The hedging area version is relevant for the 0001 and 0002 company codes, but this filter should only select the hedging instruments for the 0001 company code because you will define a second filter relevant for the 0002 company code .

You cannot enter the 0003 company code because the company code is not relevant for this hedging area version.

In the Other Filter-Specific Selections area, you have to enter the relevant Product Types.

**Note:**

You can only enter product types that fulfill the following conditions:

Product category is 600 Foreign exchange

or

Product category is 760 OTC options

and option category is one of the following

- 001 Standard

- 002 Average Rate Option


- 050 Basket Option

- 051 Basket Option Average Rates


and the underlying product type has the 600 Foreign exchange product category.

In addition you can restrict the selection by the following criteria:

Characteristics

Contract Type

Assignment

Business Partner

Activity Category

Transaction Type

Portfolio

Profit Center

Cost Center

Business Area

WBS Element

###### Hedging Area: Target Quotas

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Target Quotas | L6 | trm04 p.46 | loio `e26e5358bae84442e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e26e5358bae84442e10000000a4450e5.html?locale=en-US)

**Use**

On this tab, you enter the target quotas in the target quota tables for each target quota type relevant for the hedging area.

**Features**

You can enter the target quotas manually by using the insert target quota function.

You can upload the target quotas from a spreadsheet.

When the lines of the target quota table are filled, you can also change the target quota values manually in the table.

Manual Entry of Target Quotas

- 1. Choose the target quota type. You can choose only a target quota type that is assigned to the hedging area on the Main Data tab.

If you have assigned only one target quota type to the hedging area, the target quota type is already entered.

- 2. Choose Insert Quota .


On the appearing pop-up you can enter the following:

- a. Specify the kind of target quota that you want to enter (either Net or Gross) in the Net/Gross field.

If the Exposure Aggregation Level of the hedging area is either Only Net or Only Gross, the Net/Gross field is already filled.

- b. In the following fields, you can enter the specific combination of differentiation criteria (that are relevant for target quotas) for which you want to enter target quotas.

If you do not make entries here, the target quotas entered are relevant for all combinations of the differentiation criteria values.

- c. If you set the Insert Target Quota indicator, only new entries in the target quota table that result from these entries are inserted in the target quota table.
- d. If you set the Update Target Quota indicator, only existing entries in the target quota table are changed according to these entries.
- e. In the following table, you enter the target quotas for the defined periods.


**Note:**

The target quota related key figures in the Hedge Management Cockpit (such as Target Quota [%] Amount to Hedge and Target Hedge Amount) are always calculated using net target quotas.

You can enter gross target quotas in the hedging area master data, but the Hedge Management Cockpit does not display the gross target quotas.

**Note:**

By default, both indicators are set. Only deselect one of them if you want to have the special effect of the other.

Target Quota Band

You enter the lower and the upper limit for all periods.

**Note:**

The target quota is entered in percent.

**Example:**

If you want to enter a limit of 70%, you enter 70 in the cell.

The first limit for a period has to be lower than the second limit.

Target Limit within Band

You enter a target limit (Target Quota) within a target quota band:

Lower Quota [%]

Enter the lower limit.

Upper Quota [%]

Enter the upper limit.

Target Quota [%]

Enter the target limit for the period. This value must lie between the lower and the upper limit.

The quotas are entered in percent.

**Example:**

If you want to enter a lower limit of 70%, you enter 70 in the cell.

Limit

You enter one target quota for each period.

The target quota is entered in percent.

**Example:**

If you want to enter a limit of 70%, you enter 70 in the cell.

Once you have entered all relevant values, press the Enter key on your keyboard and then choose Enter.

The system creates the target quota lines resulting from your entries. Each line represents a specific combination of the differentiation criteria values.

**Example:**

The differentiation criteria relevant for target quotas are the currency groups and the company codes of the hedging area. The hedging-relevant currency groups of the hedging area are USD and CAD, and the relevant company codes are 0001, 0002, and 0003.

You have chosen to enter the net target quotas, and you haven't chosen any other specific differentiation criteria.

The following lines are inserted:

|Currency Group|Net/Gross|Company Code|Time Period|1st Limit (in %)|2nd Limit (in %)|
|---|---|---|---|---|---|
|CAD|Net|0001|1|70|80|
|CAD|Net|0001|2|60|70|
|CAD|Net|0001|3|50|60|
|CAD|Net|0002|1|70|80|
|CAD|Net|0002|2|60|70|
|CAD|Net|0002|3|50|60|
|CAD|Net|0003|1|70|80|
|CAD|Net|0003|2|60|70|
|CAD|Net|0003|3|50|60|
|USD|Net|0001|1|70|80|
|USD|Net|0001|2|60|70|
|USD|Net|0001|3|50|60|
|USD|Net|0002|1|70|80|
|USD|Net|0002|2|60|70|
|USD|Net|0002|3|50|60|
|USD|Net|0003|1|70|80|
|USD|Net|0003|2|60|70|
|USD|Net|0003|3|50|60|


- 3. Continue until you have entered all target quota values.
- 4. You can manually change the target quota value in the lines.


Upload from Spreadsheet

- 1. If you want to upload the target quotas from a spreadsheet, we recommend that you first download the target quota table as a spreadsheet using the export function.
- 2. Enter the values in the downloaded spreadsheet.
- 3. Upload the spreadsheet using the import function.


**Note:**

You have two options for doing this:

You can download the empty table. In this case, you have to enter all values of the table manually in the spreadsheet.

You can use the insert target quota function to generate all relevant lines of the target quota table before the download. In this case, you need to enter only the target quota values in the spreadsheet.

- 4. Save the entries.

###### Hedging Area: FX Hedge Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: FX Hedge Request | L6 | trm04 p.49 | loio `caa13e6a08244e0a82f120885e166687` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/caa13e6a08244e0a82f120885e166687.html?locale=en-US)

On this tab, you enter the master data relevant for the automated creation of FX hedge requests.

It consists of the following main input areas:

Value Date

Hedge Request Settings

First, you define the target status for automation based on which the FX hedge requests are automatically created.

You can choose between the following settings:

Created

Submitted

You can then set the Exclude Current Period indicator.

If you set this indicator, the Hedge Management Cockpit doesn't consider the key figures of the current period when you choose Automated Request Creation and will therefore not create hedge requests for that period.

The current period will, however, still be displayed in the layout of the Hedge Management Cockpit.

Value Date

In this area, you decide which value date is taken as the basis for the automated creation of FX hedge requests. It is determined based on the period you defined on the Main Data tab of the hedging area under Reporting Time Pattern.

Make the following settings:

Value Date Definition

Choose between the following values:

First Day of Period

Last Day of Period

Additional Days

You can choose to adapt the default value date defined in the Value Date Definition field by entering a number here. This defines the number of days by which the value date deviates from the default value date.

You can enter a value from -365 to 365.

Working Day Shift

Select this checkbox to ensure that the system checks the value date for holidays and only creates FX hedge requests with a value date that is a working day. This check is based on the holiday calendar of the risk currency.

Working Day

Define a rule in case the default value date is not a working day.

Choose one of the following values:

Next Working Day

Previous Working Day

Hedge Request Settings

In this area, you define the combination of company code and currency based on which the FX hedge requests are automatically created. You then specify further hedge request settings for this combination of company code and currency, such as the default instrument category, minimum amount, and rounding rules.

- 1. Insert a new row.
- 2. Specify the following hedge request settings:

- a. Enter the company code specific to this hedging area.
- b. Specify the currency for which the hedge requests are to be created. This is the risk currency of the exposure item. If cross-currency hedging is enabled for this hedging area ( Main Data Risk-Free Currency Currency Defined by the Source ), you must also define a target currence here.
- c. Specify the default instrument category that is requested as part of the hedge request.

Depending on your settings, the following instruments are available:

FXFW - FX Forward

NDF - FX Non-Deliverable Forward

FXOP - FX Option (not available for cross-currency hedging)

FXCO - FX Collar (not available for cross-currency hedging)

- d. Enter the relevant hedging classification.
- e. Enter a minimum amount for the FX hedge request. An FX hedge request is only created if the key figure Amount to Hedge equals the value entered or is higher than the minimum amount.
- f. Specify roundings for the key figure Amount to Hedge. The amounts are always rounded down.


The following rounding values are available:

1H - 100

1T - 1000

10T - 10000

1HT - 100000

1M - 1000000

10M - 10000000

- 3. Save your entries.

###### Hedging Area: Hedge Accounting I

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Hedge Accounting I | L6 | trm04 p.50 | loio `6a8f3d58eaa89144e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6a8f3d58eaa89144e10000000a4450e5.html?locale=en-US)

These settings are relevant during the automated designation process.

**Designation Level**

In this table, you decide on the designation level for a combination of company code and valuation area. In addition, you decide whether a Designation Splitting is necessary. When you leave the field blank, the splitting table is not open for input for the relevant combination of company codes and valuation areas.

The designation level is used to determine whether the hedging instruments are designated to the net exposure item or to the gross exposure item with larger absolute value of the relevant analysis item. So it also decides to which exposure items the exposure subitems refer.

The possible designation levels depend on the exposure aggregation level of the hedging area:

|Exposure Aggregation Level|Possible Designation Level|
|---|---|
|Only Net|N Net Exposure Item (not supported)|
|Only Gross|G Gross Exposure Item with Larger Absolute Value|
|Gross and Net|G Gross Exposure Item with Larger Absolute Value|


**Note:**

For hedging areas with analysis item definition By Reference the designation level is automatically set to G Gross Exposure Item with Larger Absolute Value.

In addition, you assign the Consumption Sequence. This setting is relevant for hedge request. Depending on this setting, the system checks in which sequence the hedging relationships needs to be dedesignated or swapped. Within the hedge request, you can change the proposals based on this setting. You can choose between the following values:

N No Consumption Sequence

F First In First Out

L Last In First Out

**Designation Activation**

In this table, you activate the designation for a combination of company code, valuation area, and currency. In the case of a hedging area that has the setting risk-free currency defined by the source, you activate the designation for a combination of company code, valuation area, risk currency, and target currency. If On Behalf of Company Code is a differentiation criterion in the hedging area,

this field is also available.

**Designation Splitting**

In this table, you enter the detailed information for the designation splitting.

In addition to the combination of company code and valuation area, you can specify that these settings dependent on behalf of the company code (if On Behalf of Company Code is a differentiation criterion in the hedging area), currency and direction.

- 1. Insert a new row .
- 2. First choose the characteristics:


a. Choose a combination of company code and valuation area for which you activated the designation splitting in the Designation Level frame.

- b. If On Behalf of Company Code is a differentiation criterion in the hedging area, you can choose a company code here.

- c. You can choose a risk currency of the hedging area. The risk currency represents the currency of your exposure.
- d. You can choose the direction of the cash flows.


**Note:**

For hedging areas that allow cross-currency hedges, an additional column for the target currency is available. The target currency is the currency in which the exposure amounts in risk currency are transferred/hedged by the hedging instrument. This enables you to perform splitting dependent on the different target currency.

A cash flow always has a direction.

**Example:**

You have an incoming cash flow when you receive payments from your customers. You have an outgoing cash flow when your company pays a supplier.

The hedged incoming cash flows in foreign currencies represent exports and the outgoing cash flows in foreign currencies represent imports.

- 3. In the following columns, you define the relevant designation details for the exposure items identified by the following characteristics:


- a. Enter the Split ID.
- b. Enter the Splitting Ratio.

Enter the splitting ratio in % for the splitting ID. The sum of the splitting ratios of the splitting IDs for a specific combination of company code, valuation area, on behalf of company code, risk currency, and direction needs to be 100.

- c. Choose the Reclassification Offset Category.


**Example:**

|Company Code|Valuation Area|On Behalf Of|Crcy|Direction|Split ID|Splitting Ratio|
|---|---|---|---|---|---|---|
|0001|001|1234|USD|IN|1|35|
|0001|001|1234|USD|IN|2|30|
|0001|001|1234|USD|IN|3|15|
|0001|001|1234|USD|IN|4|20|


With the reclassification offset category, you define the due date of the exposure subitem carrying the hedging reserve and the cost of hedging reserve.

- 1 max (Due Date HInst; Due Date HInst + DIO - PT)

- 2 Due Date HInst

- 3 max (Due Date HInst + DIO ; Due Date HInst + PT)

- 4 Due Date HInst + PT


with

Due Date HInst = Due Date of the hedging instrument

DIO = Days Inventory Outstanding

PT = Payment Term in Days

- d. Balance Sheet Recognition


When you choose to consider the balance sheet recognition during the term of the hedging instrument, the date of the balance sheet recognition is the due date of the hedging instrument minus the payment term. A specific reclassification algorithm exists for the hedging reserve in this case.

The following settings can be made:

- 0 - None

The exposure is not recognized in the balance sheet during the term of the hedging instrument. So no reclassification takes place. But the hedging reserve and cost of hedging reserve amounts are posted at the calculated due date of the exposure subitem which is determined according to the settings made in the Reclassification Offset Category.

- 1 - Immediate Reclassification at Balance Sheet Recognition Date

The hedging reserve and cost of hedging reserve amounts are immediately reclassified to the P/L on the balance sheet recognition date.

- 2 - Reclassification at the End Date of the Exposure Subitem

If this value has been maintained, the calculated classification amounts between designation date and balance sheet recognition date are frozen until the end date of the exposure subitem.

- 3 - Reclassification at Deviant Reclassification Date


**Note:**

If the dedesignation date and the B/S recognition date fall on the same day (for example, because you have entered 0 in the Payment Term field), no reclassification takes place. The hedging reserve and cost of hedging reserve amounts are posted at the calculated due date of the exposure subitem that is determined according to the settings made in the Reclassification Offset Category.

**Note:**

If the dedesignation date and the B/S recognition date fall on the same day (for example, because you have entered 0 in the Payment Term field), no reclassification takes place. The hedging reserve and cost of hedging reserve amounts are posted at the calculated due date of the exposure subitem that is determined according to the settings made in the Reclassification Offset Category.

If this value has been maintained, the hedging reserve and cost of hedging reserve amounts are accumulated and frozen on the balance sheet recognition date and reclassified on the deviant reclassification date.

In general, the date is determined according to the following equation:

Due Date of Hedging Instrument + Days Inventory Outstanding - Payment Term

The following two exceptions can occur:

Deviant reclassification date < designation date

Then the deviant date is considered to be the designation date and no deviant reclassification takes place. The reclassification takes place immediately or on the end date of the exposure subitem

depending on the settings made in the hedging area.

Deviant reclassification date > exposure subitem end date

Then the deviant date is considered to be the exposure subitem end date and no deviant reclassification takes place. The reclassification takes place on the exposure subitem end date.

- e. Extend Period of Hypothetical Derivative

When you choose to extend the period of the hypothetical derivative, the due date of the hypothetical derivative becomes the due date of the corresponding hedging instrument plus the payment term. If you do not want to extend the hypothetical derivative period, the due date of the hypothetical derivative is the same as the due date of the hedging instrument.

- f. Enter the PT. The payment term in days is the statistically-determined number of days until an invoice is paid.
- g. Enter the DIO.


- 4. Continue with the next row.
- 5. When you are finished, save your entries.

###### Designation Splitting

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Hedge Accounting I > Designation Splitting | L7 | trm04 p.54 | loio `e2fd7258782ba007e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e2fd7258782ba007e10000000a441470.html?locale=en-US)

**Use**

If you choose to use designation splitting, you can generate n exposure subitems with different amounts and due dates within n different hedging relationships with the same financial transaction (derivative) as hedging instrument.

The exposure subitem carries the hedging reserve and cost of hedging reserve of the hedging instrument. At the due date of the exposure subitem the hedging reserve and cost of hedging reserve is reclassified. When you use the designation splitting you can achieve that the reclassification is splitted in different parts and done at different dates.

**Integration**

You define the rules for designation splitting on the Hedge Accounting I tab in the hedging area master data.

First you activate designation splitting in the Designation Level frame .

In the Designation Splitting frame you specify the designation splitting details:

- 1. Insert a new row .


- 2. First choose the characteristics:


- a. Choose a combination of company code and valuation area for which you activated the designation splitting in the Designation Level frame.
- b. If On Behalf of Company Code is a differentiation criterion in the hedging area, you can choose a company code here.

- c. You can choose a risk currency of the hedging area. The risk currency represents the currency of your exposure.


**Note:**

For hedging areas that allow cross-currency hedges, an additional column for the target currency is available. The target currency is the currency in which the exposure amounts in risk currency are transferred/hedged by the

hedging instrument. This enables you to perform splitting dependent on the different target currency.

- d. You can choose the direction of the cash flows.


A cash flow always has a direction.

**Example:**

You have an incoming cash flow when you receive payments from your customers. You have an outgoing cash flow when your company pays a supplier.

The hedged incoming cash flows in foreign currencies represent exports and the outgoing cash flows in foreign currencies represent imports.

- 3. In the following columns, you define the relevant designation details for the exposure items identified by the following characteristics:


- a. Enter the Split ID.
- b. Enter the Splitting Ratio.

Enter the splitting ratio in % for the splitting ID. The sum of the splitting ratios of the splitting IDs for a specific combination of company code, valuation area, on behalf of company code, risk currency, and direction needs to be 100.

- c. Choose the Reclassification Offset Category.

With the reclassification offset category, you define the due date of the exposure subitem carrying the hedging reserve and the cost of hedging reserve.

- 1 max (Due Date HInst; Due Date HInst + DIO - PT)

- 2 Due Date HInst

- 3 max (Due Date HInst + DIO ; Due Date HInst + PT)

- 4 Due Date HInst + PT


with

Due Date HInst = Due Date of the hedging instrument

DIO = Days Inventory Outstanding

PT = Payment Term in Days

- d. Balance Sheet Recognition


**Example:**

|Company Code|Valuation Area|On Behalf Of|Crcy|Direction|Split ID|Splitting Ratio|
|---|---|---|---|---|---|---|
|0001|001|1234|USD|IN|1|35|
|0001|001|1234|USD|IN|2|30|
|0001|001|1234|USD|IN|3|15|
|0001|001|1234|USD|IN|4|20|


When you choose to consider the balance sheet recognition during the term of the hedging instrument, the date of the balance sheet recognition is the due date of the hedging instrument minus the payment term. A specific reclassification algorithm exists for the hedging reserve in this case.

The following settings can be made:

- 0 - None

The exposure is not recognized in the balance sheet during the term of the hedging instrument. So no reclassification takes place. But the hedging reserve and cost of hedging reserve amounts are posted at the calculated due date of the exposure subitem which is determined according to the settings made in the Reclassification Offset Category.

- 1 - Immediate Reclassification at Balance Sheet Recognition Date

The hedging reserve and cost of hedging reserve amounts are immediately reclassified to the P/L on the balance sheet recognition date.

- 2 - Reclassification at the End Date of the Exposure Subitem

If this value has been maintained, the calculated classification amounts between designation date and balance sheet recognition date are frozen until the end date of the exposure subitem.

- 3 - Reclassification at Deviant Reclassification Date


**Note:**

If the dedesignation date and the B/S recognition date fall on the same day (for example, because you have entered 0 in the Payment Term field), no reclassification takes place. The hedging reserve and cost of hedging reserve amounts are posted at the calculated due date of the exposure subitem that is determined according to the settings made in the Reclassification Offset Category.

**Note:**

If the dedesignation date and the B/S recognition date fall on the same day (for example, because you have entered 0 in the Payment Term field), no reclassification takes place. The hedging reserve and cost of hedging reserve amounts are posted at the calculated due date of the exposure subitem that is determined according to the settings made in the Reclassification Offset Category.

If this value has been maintained, the hedging reserve and cost of hedging reserve amounts are accumulated and frozen on the balance sheet recognition date and reclassified on the deviant reclassification date.

In general, the date is determined according to the following equation:

Due Date of Hedging Instrument + Days Inventory Outstanding - Payment Term

The following two exceptions can occur:

Deviant reclassification date < designation date

Then the deviant date is considered to be the designation date and no deviant reclassification takes place. The reclassification takes place immediately or on the end date of the exposure subitem depending on the settings made in the hedging area.

Deviant reclassification date > exposure subitem end date

Then the deviant date is considered to be the exposure subitem end date and no deviant reclassification takes place. The reclassification takes place on the exposure subitem end date.

- e. Extend Period of Hypothetical Derivative


When you choose to extend the period of the hypothetical derivative, the due date of the hypothetical derivative becomes the due date of the corresponding hedging instrument plus the payment term. If you do not want to extend the hypothetical derivative period, the due date of the hypothetical derivative is the same as the due date of the hedging instrument.

- f. Enter the PT. The payment term in days is the statistically-determined number of days until an invoice is paid.
- g. Enter the DIO.


- 4. Continue with the next row.
- 5. When you are finished, save your entries.

###### Hedging Area: Hedge Accounting II

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Hedging Area: Hedge Accounting II | L6 | trm04 p.57 | loio `b28e3d58eaa89144e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b28e3d58eaa89144e10000000a4450e5.html?locale=en-US)

**Use**

These settings are relevant during the automated designation process. From the data of the hedging instrument, you define rules for the derivation of the designation type relevant for the designation process, the product type for the exposure subitem, the hedging profile relevant for the automatically created hedging relationships as well as the market data set relevant for the effectiveness tests.

**Designation Control**

- 1. Choose .


- 2. Choose the characteristics of the hedging instrument:

Enter the company code.

Enter the valuation area.

Choose a hedge accounting relevant hedging classification.

If you have chosen the differentiation criterion On Behalf of Company Code as relevant for the hedging area, you can enter a company code here.

- 3. Assign the relevant designation type.


**Note:**

Choose a combination of company code and valuation area, for which you activated the designation on Hedge Accounting I tab.

A designation type always has a designation category. The designation category defines the kind of designation pattern.

**Example:**

- 1 One Instrument Designation Pattern

All financial transactions with this designation category are designated into a new hedging relationship.

This designation category is relevant for hedging with FX forwards, NDFs, and FX options.

- 2 Two Instruments (Collar) Designation Pattern


This designation category is relevant for collar FX options.

If both FX options of the collar have this designation category they are both designated into the same hedging relationship.

See also: Automated Designation Process - FX Collar

3 N Instruments (Swap) Designation Pattern

This designation category is relevant for FX swaps created according to a swap request. In this case both sides of the FX swap will be designated to the same newly created hedging relationship. See also: Automated Designation Process - FX Swap

- 4. Assign the product type for the exposure subitem. This allows you to replace the default product type for exposure subitems (entered on the Main Data tab) with another product type for exposure subitems. This can be useful if you want to differentiate the posting for the different kinds of hedging instruments.

If you do not enter a product type for exposure items, the default product type for exposure subitems (entered on the Main Data tab) is used during the automated designation process.

- 5. Assign the relevant hedging profile.
- 6. Assign a market data set along with the hedging profile to a combination of company code, valuation area and hedging classification, if you use the effectiveness testing.

During the creation of a hedging relationship the market data set is included in the generated test plan.

- 7. Save your entries.


**Note:**

For the designation type 3 N Instruments (Swap) Designation Pattern, this setting is not considered because for an FX swap, the exposure subitem product type is always derived from the original hedging relationship.

**Note:**

The assigned hedging profile must have one of the hedging relationship scenarios available for Hedge Accounting of Exposure Items process. See also: Hedge Accounting for Exposure Items

**Note:**

You must have defined market data sets using Manage Market Data Sets function.

**More Information**

Hedge Accounting for Exposure Items

Settings for Hedge Accounting for Exposure Items

###### Creating a Hedging Area

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Creating a Hedging Area | L6 | trm04 p.58 | loio `936d5758eab99344e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/936d5758eab99344e10000000a4450e5.html?locale=en-US)

**Procedure**

- 1. Call the function from the area menu under Treasury and Risk Management Hedge Management and Accounting Hedge Management Master Data Define Hedging Areas (transaction TOE_HEDGING_AREA).
- 2. Enter an ID for the Hedging Area (not exceeding six digits) and choose Create.


- 3. In the dialog box that appears, enter an explanatory description for the hedging area and enter the valid-from date of the hedging area. Choose Create.
- 4. Enter the valid-from date for the hedging area version.
- 5. In the Memo area, you can enter a free text containing additional information for this hedging area version.
- 6. Hedging Area: Main Data

- 7. Hedging Area Tab: General Data

- 8. Hedging Area: Currencies

- 9. Hedging Area: Filters for Exposures

- 10. Hedging Area: Filters for Hedges

- 11. Hedging Area: Target Quotas

- 12. Hedging Area: FX Hedge Request

- 13. Hedging Area: Hedge Accounting I

- 14. Hedging Area: Hedge Accounting II

- 15. If you have made the necessary settings for target quotas on the Main Data tab to enable the entry of target quotas, you can enter the target quotas in the target quota tables on the Hedging Area: Target Quotas tab.

- 16. Save your entries.


**Note:**

The version number of this new hedging area is set to 1.

You can use another hedging area version as a template for the first version of the new hedging area.

###### Changing a Hedging Area Version

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Changing a Hedging Area Version | L6 | trm04 p.59 | loio `3b6f5758eab99344e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b6f5758eab99344e10000000a4450e5.html?locale=en-US)

**Note:**

You can only change the latest version of a hedging area if there is no snapshot for this latest version. If changes to the latest version are no longer possible, but changes to the hedging area are needed, you have to create a new version of the hedging area.

- 1. Call the Define Hedging Areas function (transaction TOE_HEDGING_AREA) from the area menu of Treasury and Risk Management under Hedge Management and Accounting Hedge Management Master Data .
- 2. Enter the ID of the hedging area and choose the latest version of the hedging area.
- 3. Choose Change.
- 4. Make the required changes.
- 5. Save your entries.


**Note:**

Checking a Hedging Area

- 1. When you are in change mode, you can check your entries. Choose Check.
- 2. The report checks the hedging area for consistency. For example, only filters for the relevant risk currencies or company codes of the hedging area are useful.


3. The system issues warning messages for any inconsistencies found.

###### Creating a New Version for an Existing Hedging Area

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Creating a New Version for an Existing Hedging Area | L6 | trm04 p.60 | loio `fe6f5758eab99344e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fe6f5758eab99344e10000000a4450e5.html?locale=en-US)

**Procedure**

- 1. Call the Define Hedging Areas function (transaction TOE_HEDGING_AREA) from the area menu of Treasury and Risk Management under Hedge Management and Accounting Hedge Management Master Data .
- 2. Enter the ID of the hedging area and the latest version of the hedging area.
- 3. Choose New Version.
- 4. In the dialog box that appears, enter the valid-from date of the new version. The date entered has to be laterthan the latest valid-from date of existing versions of the hedging area.
- 5. Choose Create.
- 6. The new version is created. The settings of the previous version are copied to the new version. Now you can make any necessary changes to this new version. You can change all data of the hedging area apart from the ID of the hedging area.
- 7. Save your entries.

###### Displaying a Hedging Area Version

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Define Hedging Areas > Displaying a Hedging Area Version | L6 | trm04 p.60 | loio `c9705758eab99344e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c9705758eab99344e10000000a4450e5.html?locale=en-US)

**Procedure**

- 1. Call the function Define Hedging Areas (transaction TOE_HEDGING_AREA) from the area menu of Treasury and Risk Management under Hedge Management and Accounting Hedge Management Master Data .
- 2. Enter an ID for the hedging area (not exceeding six digits).
- 3. Choose the version.
- 4. Choose Display.
- 5. On the Version History tab, you can see all versions of the hedging area. The following data of the versions is displayed:


Valid-From Date

Entered On

Time of Initial Entry

Entered By

Last Edited On (Date)

Last Edited At (Time)

Last Changed By

Memo

###### Manage Layouts

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Manage Layouts | L5 | trm04 p.60 | loio `b5f1df7b49774f3d9f9eb5b0c7d9c966` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b5f1df7b49774f3d9f9eb5b0c7d9c966.html?locale=en-US)

Define and edit the layouts controlling the data shown in the Hedge Management Cockpit.

The layouts are defined independently of the hedging area. You can define the layout as public or private. User-specific private layouts are not visible for other users.

Within the layout, you define the following:

Which exposure snapshots are read

The date on which hedging instruments are read

How the data is displayed in the results table of the Hedge Management Cockpit

Which key figures are calculated and displayed and also the order of the key figures.

**Activities**

- 1. Call the Hedge Management Cockpit either by using the app on the SAP Fiori launchpad or by calling the function in the back-end system (transaction TOENE).
- 2. Choose Manage Layouts.
- 3. In the Layout Overview, you get a list of existing public layouts and your own private layouts. Choose Create Layout to define a new layout.
- 4. On the following screen, enter an ID for the new layout and set the Private indicator if you want to define your own layout.
- 5. Choose which exposure snapshots are read

I Snapshot ID

When you choose this setting, you must enter the snapshot ID manually when you start the Hedge Management Cockpit.

L Last Snapshot

When you choose this setting, the system uses the last snapshot taken.

R Last Relevant Snapshot

When you choose this setting, the system uses the last snapshot taken with the Day Reference indicator.

- 6. Enter the date on which hedging instruments are read:

Current date

The current date is taken.

Date

You have to enter the date on which you start the Hedge Management Cockpit.

- 7. Choose the Display Mode that determines the design of the result table:


Row: Key figures in rows, time periods as columns

Column: Key figures in columns, time periods as rows

Example:

Key Figures in Rows:

|CoCd|Crcy|Key Figure|Period 1|Period 2|Period 3|
|---|---|---|---|---|---|


|CoCd|Crcy|Key Figure|Period 1|Period 2|Period 3|
|---|---|---|---|---|---|
|0001|USD|Incoming Exposure|500|400|300|
|0001|USD|Outgoing Exposure|400|300|200|
|0001|USD|Net Exposure|100|100|100|


Key Figures in Columns

|CoCd|Crcy|Period|Incoming Exposure|Outgoing Exposure|Net Exposure|
|---|---|---|---|---|---|
|0001|USD|Period 1|500|400|100|
|0001|USD|Period 2|400|300|100|
|0001|USD|Period 3|300|200|100|


- 8. In the Display Level area, you decide how the data is displayed in the results table of the Hedge Management Cockpit:

On the Differentiation Criteria tab, you choose which characteristics are relevant:

- Enter 0 if you do not want to display a characteristic.

- Enter 1 if you want to display a characteristic.


If you choose the company code and currency as differentiation criteria: You need to have company codes and exposures in the currencies USD, JPY, and GBP so that the data is aggregated on the six combination levels 0001 USD/0001 JPY/0001 GBP/0002 USD/0002 JPY/0002 GBP.

On the Key Figures tab, you decide first in the column display level when you want to calculate and display a key figure:

- 0 = Key figure is not shown in the results screen of the Hedge Management Cockpit.

- 1 = Key figure is shown in the results screen of the Hedge Management Cockpit.


See the available key figures under Key Figures in the Hedge Management Cockpit

In addition, you must define the order of the key figures shown in the Hedge Management Cockpit.

On the Period tab, you can choose to see the periods as they are defined in the hedging area. In addition, you can display a total across all time periods and a total of all time periods in a calendar year.

Enter 1 in the Display Level column when you want to display the periods/totals. Alternatively, enter 0 when you do not want to display them.

On the Filter tab, you can decide which of the relevant differentiation criteria is available as filters and you can define default values for the filters. On the results screen of the Hedge Management Cockpit, you can use the defined filters to restrict the displayed data.

- 9. Save your entries.

###### Creating Layout (Time Periods)

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Manage Layouts > Creating Layout (Time Periods) | L6 | trm04 p.62 | loio `b5eb671bc89b4edabc05bde877fe59e4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b5eb671bc89b4edabc05bde877fe59e4.html?locale=en-US)

Create Hedge Management Cockpit layout for hedging areas with analysis items defined By Time Periods.

**Context**

The layout controls how the data of a hedging area are shown in the Hedge Management Cockpit. Hedging areas are defined for different kinds of analysis items which induce different structuring of the results screen of the Hedge Management Cockpit. Therefore, two different layout categories are available:

Time Period

Single Reference

Layouts of a specific layout category can only be used for hedging areas with the corresponding analysis item defintion, but the layout defintion is independent from a specifc hedging are so you can use a layout for all corresponding hedging areas.

You can define the layout as public or private. User-specific private layouts are not visible for other users.

**Procedure**

- 1. Call the Hedge Management Cockpit using the app on the SAP Fiori launchpad or by calling the function in the backend system (transaction TOENE).
- 2. Choose Manage Layouts.
- 3. In the Layout Overview, you get a list of existing public layouts and your own private layouts. Choose Create Layout to define a new layout.
- 4. On the following screen, enter an ID for the new layout and choose Time Periods in Layout Category field. Set the Private indicator, when you want to define your own layout.
- 5. Choose Enter.
- 6. Enter a description for the layout.
- 7. Define the selection of exposure snapshots. When you choose I Snapshot ID, you must enter the snapshot ID manually, when you start the Hedge Management Cockpit. When you choose L Last Snapshot, the system uses the last snapshot taken for the hedging area. When you choose R Last Relevant Snapshot, the system uses the last snapshot with the Day Reference indicator taken for this hedging area .
- 8. Enter the selection date for the hedging instruments. You can choose between Current Date (in this case the system takes the system date) or Date (in this case you have to enter a date, when you start the Hedge Management Cockpit).
- 9. Choose the Display Mode, that determines the design of the result screen. If you choose Row, the key figures are in rows, time periods as columns. When you choose Column, the key figures are in columns, the time periods as rows. See the example at the end of the text. Example:


Key Figures in Rows:

|CoCd|Crcy|Key Figure|Period 1|Period 2|Period 3|
|---|---|---|---|---|---|
|0001|USD|Incoming Exposure|500|400|300|
|0001|USD|Outgoing Exposure|400|300|200|
|0001|USD|Net Exposure|100|100|100|


Key Figures in Columns

|CoCd|Crcy|Period|Incoming Exposure|Outgoing Exposure|Net Exposure|
|---|---|---|---|---|---|
|0001|USD|Period 1|500|400|100|


|CoCd|Crcy|Period|Incoming Exposure|Outgoing Exposure|Net Exposure|
|---|---|---|---|---|---|
|0001|USD|Period 2|400|300|100|
|0001|USD|Period 3|300|200|100|


- 10. The Scaling factor allows you to display the calculated amounts of the key figures in the Hedge Management Cockpit as quantities of thousands or millions for a better overview in the case of large amounts. If you do not select thousands or millions, the report displays the exact amounts. This is the default setting. If you set the factor to thousands or millions, the report displays all amounts rounded to the nearest thousand or million.
- 11. You can select a Valuation Area. When you select a specific valuation area, only the hedging relationships of this valuation area are evaluated and relevant for the key figure calculations.
- 12. You can select a Target Quota Type. When you select a target quota type, only the target quotas of this type are evaluated and relevant for the key figure calculations.
- 13. In the Display Level area, you decide how the data is displayed in the results screen of the Hedge Management Cockpit.
- 14. On the Differentiation Criteria tab, you choose which characteristics are relevant. Enter 0 if you do not want to display a characteristic. Enter 1 if you want to display a characteristic.
- 15. On the Key Figures tab, you decide first in the column display level when you want to calculate and display a key figure. When you enter 0 the key figure is not shown in results screen of the Hedge Management Cockpit. When you enter 1 the key figure is shown in results screen of the Hedge Management Cockpit. In addition, you must define the order of the shown key figures in the Hedge Management Cockpit. See the available key figures under Key Figures in the Hedge Management Cockpit

- 16. On the Period tab, you can choose to see the periods as defined in the hedging area. In addition, you can display a total across all time periods and a total of all time periods in a calendar year. Enter 1 in the Display Level column when you want to display the periods/totals. Alternatively, enter 0 when you do not want to display them.
- 17. On the Filter tab, you can decide which of the relevant differentiation criteria should be available as filters and you can define default values for the filters. On the results screen of the Hedge Management Cockpit, you can use the defined filters to restrict the displayed data.
- 18. Save your entries.

###### Creating Layout (Single References)

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Manage Layouts > Creating Layout (Single References) | L6 | trm04 p.64 | loio `2898f99d44f54f76b2efe627f4d63470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2898f99d44f54f76b2efe627f4d63470.html?locale=en-US)

Create Hedge Management Cockpit layout for hedging areas with analysis items defined By Reference.

**Context**

The layout controls how the data of a hedging area are shown in the Hedge Management Cockpit. Hedging areas are defined for different kinds of analysis items which induce different structuring of the results screen of the Hedge Management Cockpit. Therefore, two different layout categories are available:

Time Period

Single Reference

Layouts of a specific layout category can only be used for hedging areas with the corresponding analysis item defintion, but the layout defintion is independent from a specifc hedging area, so you can use a layout for all hedging areas with the corresponding analysis item definition.

You can define the layout as public or private. User-specific private layouts are not visible for other users.

**Procedure**

- 1. Call the Hedge Management Cockpit using the app on the SAP Fiori launchpad or by calling the function in the backend system (transaction TOENE).
- 2. Choose Manage Layouts.
- 3. In the Layout Overview, you get a list of existing public layouts and your own private layouts. Choose Create Layout to define a new layout.
- 4. On the following screen, enter an ID for the new layout and choose Single Reference in Layout Category field. Set the Private indicator, when you want to define your own layout.
- 5. Choose Enter.
- 6. Enter a description for the layout.
- 7. Define the selection of exposure snapshots. When you choose I Snapshot ID, you must enter the snapshot ID manually, when you start the Hedge Management Cockpit. When you choose L Last Snapshot, the system uses the last snapshot taken for the hedging area. When you choose R Last Relevant Snapshot, the system uses the last snapshot with the Day Reference indicator taken for this hedging area .
- 8. Enter the selection date for the hedging instruments. you can choose between Current Date (in this case the system takes the system date) or Date (in this case you have to enter a date, when you start the Hedge Management Cockpit).
- 9. The Display Mode determines the design of the result sreen. For layouts with layout category Single References the display mode is set to Column. You cannot change this setting. The key figures are in columns, the different analysis items as rows. See example at the end of the text.
- 10. The Scaling factor allows you to display the calculated amounts of the key figures in the Hedge Management Cockpit as quantities of thousands or millions for a better overview in the case of large amounts. If you do not select thousands or millions, the report displays the exact amounts. This is the default setting. If you set the factor to thousands or millions, the report displays all amounts rounded to the nearest thousand or million.
- 11. You can enter a Valuation Area.
- 12. The Target Quota Type field is disabled.
- 13. On the Differentiation Criteria tab, Company Code, Risk-Free Currency, and Currency are chosen ( 1 in Display Level field). You cannot change this setting. In addition to these characteristics the Due Date, the Exposure Item ID, and Exposure Item Description are shown as columns in the results screen of the Hedge Management Cockpit. The internally by the system used reference-related technical differentiation criteria are not displayed.
- 14. On the Key Figures tab, you decide first in the column display level when you want to calculate and display a key figure. When you enter 0 the key figure is not shown in results screen of the Hedge Management Cockpit. When you enter 1 the key figure is shown in results screen of the Hedge Management Cockpit. In addition, you must define the order of the shown key figures in the Hedge Management Cockpit. For reference based analysis items the following key figures are available:

Net Exposure

Net Hedges

Net Open Exposure

Hedged Rate

Hedge Quota [%]

Designated Hedges

See the definitions of the specific key figures under Key Figures in the Hedge Management Cockpit

- 15. On the Filter tab, you can decide which of the relevant differentiation criteria should be available as filters and you can define default values for the filters. On the results screen of the Hedge Management Cockpit, you can use the defined filters to restrict the displayed data.
- 16. Save your entries.


**Example**

Key Figures in Columns

|CoCd|RFreeCrcy|Crcy|Due Date|Exposure Item ID|Exposure Item Description|Net Exposures|Net Hedges|Net Open Exposure|Hedge Quota [%]|
|---|---|---|---|---|---|---|---|---|---|
|0001|EUR|USD| | | |500|400|100| |
|0001|EUR|USD| | | |400|300|100| |
|0001|EUR|USD| | | |300|200|100| |

###### Key Figures in the Hedge Management Cockpit

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Settings for Hedge Management > Manage Layouts > Key Figures in the Hedge Management Cockpit | L6 | trm04 p.66 | loio `c7d727555f1741c282469ff654dea85a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c7d727555f1741c282469ff654dea85a.html?locale=en-US)

|Key Figure|Abbreviation|Explanation|
|---|---|---|
|Primary Key Figures| | |
|Incoming Exposure|Inc. Exp.|Sum of incoming exposures|
|Outgoing Exposure|Out. Exp.|Sum of outgoing exposure|
|Net Hedges|Net Hedges|Sum of nominal amounts of hedges **Note:** If you use an FX option as hedging instrument, the underlying FX spot transaction is assigned automatically to the exposure item with the exercise of the FX option. The FX spot transaction also inherits the hedge request ID. The exposure item assignment of the FX option is terminated. This ensures the correct calculation of the key figure Net Hedges in the Hedge Management Cockpit. In this way, the FX spot transaction is considered in the Net Open Exposure and Net Open Exposure (Incl. HR) key figures in the Hedge Management Cockpit as of the exercise date of the FX option. This enables historical reporting in the Hedge Management Cockpit with a backdated key date. FX option contributes to the net hedges before the exercise date. FX spot transaction (underlying) contributes to the net hedges as of the exercise date of the FX option.|
|Designated Hedges|Desig.Hdgs|Sum of nominal amounts of designated hedges|
|Hedged Rate|HedgedRate|The hedged rate is the weighted average of the hedged rates based on the absolute|


|Key Figure|Abbreviation|Explanation|
|---|---|---|
| | |nominal amounts of the single hedge transactions Hedged Rate = Sum of absolute amounts of hedges in leading currency / sum of absolute amounts of hedges in following currency Example: Hedging Instruments: Transaction 1: 500 EUR / -550 USD Transaction 2: 300 EUR / -430 USD Transaction 3: 200 EUR / -240 USD Transaction 4: -300 EUR / 330 USD Transaction 5: 400 EUR / -430 USD Leading Currency: EUR, Following Currency: USD Hedged Rate = 1700 EUR / 1980 USD ≅ 0,858585|
|Hedged Rate (Arithmetic)|Hedged Rate (Arith.)|The Hedged Rate (Arithmetic) is the weighted average of the hedged rates based on the nominal amounts (with sign) of the single hedge transactions. Hedged Rate (Arithmetic) = Absolute value of the sum of nominal amounts in leading currency / absolute value of the sum of nominal amounts in following currency Example: Hedging Instruments: Transaction 1: 500 EUR / -550 USD Transaction 2: 300 EUR / -430 USD Transaction 3: 200 EUR / -240 USD Transaction 4: -300 EUR / 330 USD Transaction 5: 400 EUR / -430 USD Leading Currency: EUR, Following Currency: USD Hedged Rate (Arithmetic) = 1100 EUR / 1320 USD ≅ 0,833333|
|Target Quota [%]|TQ|Single limit net target quota (in %)|
|Lower Target Quota [%]|LTQ|Lower net target quota of the target quota band (in %)|


|Key Figure|Abbreviation|Explanation|
|---|---|---|
|Upper Target Quota [%]|UTQ|Upper net target quota of the target quota band (in %)|
|Original Amount of Hedge Requests|HedgReqAmt| |
|Open Amount of Hedge Requests|OpenAmtHR|Residual amount of a hedge request that was not yet covered by a hedge.|
|Open Amount of Termination Requests|Open Amt Term. Req.|Residual amount of a termination request.|
|Hedges for Hedge Requests|Hedges for Hedge Req.|Nominal amounts of hedges created for a hedge request|
|Derived Key Figures| | |
|Net Exposure|Net Exp|Incoming Exposure + Outgoing Exposure|
|Net Open Exposure (Incl. Hedge Request)|NOE(Incl.HR)|Unhedged amount of the net exposure including open amount of hedge requests = Net Exposure + (Net Hedges + Open Amount of Hedge Requests)|
|Net Open Exposure|NetOpenExp|Unhedged amount of the net exposure = Net Exposure + Net Hedges|
|Net Open Exposure (Hedge Accounting)|NOE (HA)|Hedge request amounts are either relevant for hedge accounting or not relevant. Therefore, they cannot be clearly attributed to a hedge accounting key figure. = Net Exposure + Designated Hedges|
|Net Hedge Quota (Hedge Accounting)|NHQ (HA)|The amounts of hedge requests are either relevant for hedge accounting or not relevant. Therefore, they cannot be clearly attributed to a hedge accounting key figure. You may need a net hedge quota (hedge accounting) in addition to the net hedge quota if the target quota and the intended quota for designated hedges differ (due to partial designation or due to dedesignations). = – Designated Hedges / Net Exposure|
|Gross Hedge Quota (Hedge Accounting)|GHQ (HA)|The amounts of hedge requests are either relevant for hedge accounting or not relevant. Therefore, they cannot be clearly attributed to a hedge accounting key figure. You may need a gross hedge quota (hedge accounting) in addition to the net hedge quota if the target quota and the intended quota for designated hedges differ (due to partial designation or due to dedesignations). = – Designated Hedges / Gross Exposure|


|Key Figure|Abbreviation|Explanation|
|---|---|---|
| | |The gross exposure is either the incoming or the outgoing exposure. It is decided by the comparison of the absolute values. The exposure with the larger absolute value is the gross exposure.|
|Hedge Quota [%]|HdgQ [%]|= – (Hedges + Open Amount of Hedge Requests) / Net Exposure|
|Net Hedges in Risk-Free Currency|Net Hedges in RfC| |
|Freestanding Hedges|Free. Hdgs|= Net Hedges – Designated Hedges|
|Target Hedge Amount|THA|Target amount to hedge when the net target quota is a single limit. Sign of the amount has the opposite direction as the exposure. = Net Exposure * Target Quota (Single Limit)|
|Lower Target Hedge Amount|LTHA|Lower target amount to hedge if the net target quota is a band. Sign of the amount has the opposite direction as the exposure. = Net Exposure * Lower Target Quota (Band)|
|Upper Target Hedge Amount|UTHA|Upper target amount to hedge if the net target quota is a band. Sign of the amount has the opposite direction as the exposure. = Net Exposure * Upper Target Quota (Band)|
|Amount to Hedge|Amt2Hedge|Nominal amount to hedge regarding the target quota (single limit) = Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)|
|Minimum Amount to Hedge|Min2Hedge|Minimum amount to hedge regarding lower target quota (band) = Lower Target Hedge Amount- (Hedges + Open Amount of Hedge Requests)|
|Maximum Amount to Hedge|Max2Hedge|Maximum amount to hedge regarding upper target quota (band) = Upper Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)|
|Status Key Figures Status key figures indicate whether a special situation occurs (yes=1/no=0). They are calculated for each single analysis item. They can be counted if data is shown in aggregated form.| | |


|Key Figure|Abbreviation|Explanation|
|---|---|---|
|Change of Direction|Dir.Change|Answers the following question: Do the hedges and net exposures have the same direction? 0 if different signs 1 if equal signs |
|Change of Direction (Hedge Accounting)|Dir.Change (HA)|Answers the following question: Do the designated hedges and the net exposure have the same direction? 0 if different signs 1 if equal signs |
|Gross Overhedge|Gross OH|Hedges and gross exposures have opposite directions and the absolute value of hedges + open amounts of hedge requests is greater than the absolute value of gross exposure.|
|Gross Overhedge (Hedge Accounting)|GrossOH HA|The designated hedges and the gross exposure have opposite directions and the absolute value of hedges is greater than the absolute value of the gross exposure.|
|Net Overhedge|Net OH|The hedges and the net exposure have opposite directions and the absolute value of hedges + open amounts of hedge requests is greater than the absolute value of the net exposure.|
|Net Overhedge (Hedge Accounting)|NetOH HA|The designated hedges and net exposures have opposite directions and the amount of designated hedges is greater than the net exposure.|
|Target Quota Overhedge|TQ OH|Net hedges exceed the target quota amount (single limit).|
|Lower Target Quota Overhedge|LTQ OH|Net hedges exceed the lower target quota amount. You can use this key figure in different ways: If you want the net hedges to be inside the target quota band, being below the lower target quota might be undesirable. If you use the band like a two-step limit, being above the lower target quota is considered a warning.|
|Upper Target Quota Overhedge|UTQ OH|Net hedges exceed the upper target quota amount.|


|Key Figure|Abbreviation|Explanation|
|---|---|---|
| | |Independent of the semantic interpretation of the band, being above the upper target quota is considered undesirable.|


Remark:

The hedge requests mentioned in this table are the FX hedge requests and swap requests combined.

##### Exposures

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Exposures | L4 | trm04 p.71 | loio `15cf48303e5b4be1934df4dcb9fa783f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/15cf48303e5b4be1934df4dcb9fa783f.html?locale=en-US)

The FX exposures of your company are managed in different data sources. For the Hedge Management of Net Open Exposures process, snapshots of future foreign currency payments managed in the Treasury and Risk Management exposure functions are allowed as well as the forecasted cash flows of Cash and Liquidity Management.

The foreign exchange risk that your company is exposed to can be managed in different data sources. The following data sources are connected to the Hedge Management Cockpit:

**Treasury and Risk Management**

Exposure Management 2.0

In Exposure Management, you collect future incoming and outgoing payments of your company that are associated with a currency risk. These payment flows are either actual payments that already have a fixed amount and time settings or only planned payments.

Exposure Management helps you to identify the risks from your cash flows. You can use the following apps:

Process Raw Exposures

Process Raw Exposures - Collective Processing

Process Exposure Positions

Display Exposure Position Flows

Import Raw Exposures - Spreadsheet

For more information, see also Exposure Management 2.0.

FX Exposure Management

FX Exposure Management offers an easy way of entering FX exposures with the Manage FX Exposures app or using the Foreign Exchange Exposure (API_FXEM_FXEXPOSURE) API. The status concept and available functions for FX exposures that are relevant within the Manage FX Exposures app are also relevant for processing FX exposures using the API.

**Cash Management**

Cash and Liquidity Management enables you to get an overview of your company's cash movements easily. Cash managers can get a high-level overview and detailed insights into bank accounts, cash position, liquidity forecast, and forecasted cash flows, enabling them to make decisions and take actions directly.

These forecasted cash flows represent a valuable and reliable source with which to identify your company's foreign exchange risk. The Hedge Management Cockpit reads the exposure data from snapshots of the forecasted cash flows. The snapshots of the forecasted cash flows are created according to the filter settings and differentiation criteria specified in your hedging area. The cash flow data is aggregated into exposure items.

**Note:**

The Take Snapshot app doesn't select the aggregated amount of cash flows that are forecasted to occur prior to the value date that you have selected.

The cash flow data can be verified using the Cash Flow Analyzer app.

Related Information

For more information, see

Cash Flow Analyzer

Hedging Area: Filters for Exposures

**Integration in Hedge Management of Net Open Exposures Process**

In the Hedge Management of Net Open Exposures process, the relevant exposures from the different data sources are selected and saved as exposure items on a regular basis. The Hedge Management Cockpit then reads the exposure items.

The exposure items represent the exposures of an analysis item and are saved on the database. You create the exposure items using the snapshot function. The Take Snapshot app creates the incoming gross exposure item, outgoing gross exposure item, and net exposure item according to the filter settings and differentiation criteria specified in your hedging area.

The saved exposure items are valuation-area-independent, they have an exposure item ID, per date an amount, and also carry the information to which hedging area version they belong. The due date of an exposure item is the end date of the relevant time period.

If you have defined several filters with different data sources in your hedging area, the exposures from different data sources are aggregated to one exposure item. The due date of this exposure item is the end date of the relevant time period.

**Related Information**

Maintaining Exposures in Treasury and Risk Management

###### Maintaining Exposures in Treasury and Risk Management

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Exposures > Maintaining Exposures in Treasury and Risk Management | L5 | trm04 p.72 | loio `161721a3c2d144f0be400e9169c3368f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/161721a3c2d144f0be400e9169c3368f.html?locale=en-US)

**Context**

You must enter your exposures on a regular basis.

Maintaining Exposures in Exposure Management 2.0

You must enter your raw exposures on a regular basis.

**Procedure**

- 1. You can enter the raw exposures using the Process Raw Exposures app.

Enter the required data for the raw exposures to ensure that the resulting exposure positions are correctly identified during the creation of the snapshots for your hedging areas:

When the raw exposures are saved, the system starts the automatic analysis of the raw exposures for the risks associated with them.

- a. Open the Process Raw Exposures app on SAP Fiori launchpad.
- b. Select the valid exposure activity type and choose Create.
- c. On the Header Data tab, first enter the general raw exposure data, such as the External Document Number, Default Exposure Category, Company Code (these are mandatory differentiation criteria), and the Country/Region.
- d. Go to the Position Data tab. Select Create New Line Item and enter the External Item Number, the Planning Period and the Planning Year (in which the exposure is due), and also the concrete Exposure Due Date, the Exposure Amount, the Exposure Amount Currency, and the Target Currency.
- e. Enter all additional data belonging to the line item and save your entries.


After the entries have been saved, the system creates sub raw exposures for the line items.

- 2. Release the raw exposures using Process Raw Exposures app (App ID: FTREX1) or Process Raw Exposures - Collective Processing app (App ID: FTREX2). This step is only relevant if the raw exposure release type is set to Manual for the exposure activity type.

If the exposure release type is set to Automatic for the exposure activity type, the raw exposure is released automatically when you save the raw exposure.

- 3. If the underlying transactions are changed, the raw exposures can be changed accordingly. The related exposure positions are updated automatically.
- 4. Over time, the exposure category of the underlying transaction changes to Firm Commitment Transaction. This field cannot be changed in the raw exposure. Instead, a new raw exposure with the new exposure category must be created.

When the raw exposure is released, the 'old' exposure position with the exposure category Forecasted Transaction is reduced by the amount of the raw exposure (= automatic matching), and a new exposure position with the exposure category Firm Commitment Transaction is created (or increased if a suitable exposure position already exists).

- 5. Using the Display Exposure Position Flows app (App ID: FTREX13), you can display the generated exposure positions.


**Note:**

You can also enter raw exposures using the Import Raw Exposures - Spreadsheet app.

**Note:**

If, together with the change of the exposure category from Forecasted Transaction to Firm Commitment Transaction, the amount of the raw exposure also changes, you must update the amount of the old raw exposure in addition to entering the new raw exposure.

Maintaining FX Exposures in FX Exposure Management

You can create and process FX exposures using the Manage FX Exposures app (App ID: F7990) or using the Foreign Exchange Exposure (API_FXEM_FXEXPOSURE) API. The status concept and available functions for FX exposures that are relevant within the Manage FX Exposures app are also relevant for processing FX exposures using the API.

**Procedure**

- 1. Open the Manage FX Exposures app on SAP Fiori launchpad.

In the app, you can either create an FX exposure manually as described below or you can create multiple FX exposures via upload from a spreadsheet.

- 2. Choose Create.
- 3. Choose the relevant FX Exposure Type.
- 4. Choose the Company Code.
- 5. Enter the Due Date of the FX exposure.
- 6. Enter the following FX exposure details:

Enter the Direction of the FX exposure.

The direction specifies whether the exposure is an Incoming or an Outgoing cash flow.

Enter the amount of the FX exposure by entering the value and the currency of the FX exposure amount.

Enter the Target Currency.

Currency in which the amount of the FX exposure must be hedged.

The valid-from date is automatically set to the current date, but you can change the date.

Date as of which the FX exposure is valid.

You can enter an external ID of the FX exposure.

The external ID for the FX exposure is a free text field in which you can enter external references for the FX exposure, such as the invoice number or the customer/supplier item number.

In the Differentiation Criteria area, you must enter the values for each available field. Which fields are available here depends on the FX exposure type of the FX exposure.

- 7. Choose Create.


**Note:**

Upload FX exposures from spreadsheet.

- a. Choose Upload Download Template .
- b. Create a spreadsheet based on the template and enter the data of the FX exposures.
- c. Choose Upload Upload .
- d. Select the spreadsheet and choose Open.


**Note:**

For an incoming exposure, the sign of the FX exposure amount must be positive and for an outgoing exposure it must be negative.

FX exposures in status Created can be edited to correct the entered values. In addition, an FX exposure in this status can be set to status Obsolete.

- 8. When the FX exposure data is entered completely, the user who created the FX exposure sends the FX exposure for checking by choosing Submit for Release.
- 9. FX exposures with the status Submitted need to be checked. A user who is authorized to check can release or reject the FX exposure.

If the submitted FX exposure has an error and needs to be adjusted before release, the FX exposure can be sent for update. In this case, the status of the FX exposure is reset to Created.

- 10. If an already released FX exposure changes, you can set the status of the FX exposure back to Created and you can update the following fields:

Amount

Valid-From Date

External ID

- 11. Submit the corrected FX exposure for checking using the Submit for Release button.
- 12. FX exposures with the status Submitted need to be checked. A user who is authorized to check can release or reject the FX exposure.


**Note:**

With the release of the FX exposure, the FX exposure is saved in an internal table and gets a version number. If the FX exposure is changed later, the new version is saved in the internal table once the FX exposure is released again, set to obsolete, or rejected.

The released FX exposure can now be selected for a snapshot that is taken using the Take Snapshot app.

**Note:**

Use the Set to Created button and enter the reason for the status switch.

##### Take Snapshot

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Take Snapshot | L4 | trm04 p.75 | loio `d78d3d58eaa89144e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d78d3d58eaa89144e10000000a4450e5.html?locale=en-US)

App ID: TOESNAP

With this app, you make a snapshot of the exposures belonging to a hedging area. The selected incoming and outgoing exposures and the exposure items are saved to the database. The Hedge Management Cockpit then reads the exposure data from the snapshots.

**Note:**

Before you can start the hedge management process, it is mandatory to rely on fully versioned data. This ensures that at all times an auditor can check which data served as the basis for a hedging decision.

**Prerequisites**

You have made all settings for the Hedge Management and Accounting of Net Open Exposures process. In particular, you have defined your hedging areas. The validity of the hedging area version must start before the start date of the oldest financial transaction used as hedging instrument for current exposures.

You have entered the relevant exposures in the Exposure Management 2.0, FX Exposure Management, and Cash Management.

Features

Take a Snapshot of Exposures

When you execute the function, the incoming gross exposure items, outgoing gross exposure items, and net exposure items are created for each selected hedging area. The exposures are selected according to the settings in the filters of the respective hedging area.

In the snapshot tables, the selected single exposures are saved with their original data (for example, the amount, the exposure position ID, the time period from Exposure Management 2.0, additional differentiation criteria of the exposure positions, and so on) and they ʻknow’ to which snapshot ID and which hedging area version they belong. In addition, the aggregated values for the incoming and outgoing exposures of an analysis item are saved and the exposure item IDs are created.

**Note:**

The saved incoming and outgoing single exposures and the aggregated amounts are not specific to valuation areas.

Thus, an exposure item has an exposure item ID and an amount per date and contains details about the hedging area version to which they belong. The due date of an exposure item is the end date of the relevant time period.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Hedge Management and Accounting of Net Open Exposures (FX Risk) Hedge Management Cockpit Manage Snapshots

###### Take a Snapshot of Exposures

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Take Snapshot > Take a Snapshot of Exposures | L5 | trm04 p.76 | loio `a60ceffa0b6343da8e6f4f7a7c747355` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a60ceffa0b6343da8e6f4f7a7c747355.html?locale=en-US)

Regular task within the Hedge Management of Net Open Exposures process.

**Context**

To ensure that you always have the most recent exposure data available in the Hedge Management Cockpit, you have to take the snapshots of the exposures on a regular basis.

Prerequisites

You have made all settings for the Hedge Management and Accounting of Net Open Exposures process. In particular, you have defined your hedging areas. The validity of the hedging area version must start before the start date of the oldest financial transaction used as hedging instrument for current exposures.

You have entered the relevant exposures in the Exposure Management 2.0, FX Exposure Management, and Cash Management.

**Procedure**

- 1. Open the Take Snapshot app on SAP Fiori launchpad.
- 2. Enter the hedging areas.


- 3. You can enter a description for the snapshot.
- 4. Enter the Extraction Date. The extraction date is the date for which you want to extract the valid exposures.

Enter the extraction date. Dates in the future are not possible. If already snapshots exist for the hedging area, you can only extract data for the current user date.

- 5. Set the Day Reference indicator when the exposure items need to be relevant within the automated designation process. When you set this indicator, the snapshot gets the Day Reference indicator.

During the automated designation process of hedge accounting (started when you save a hedging instrument), the system must identify the relevant exposure item. Therefore, the system uses the snapshot for the relevant hedging area which fulfills the following criteria:

In case of the designation of FX transactions, the Value Date of the transaction is used for the determination of the exposure items.

In case of the designation of a non-deliverable forward, the Value Date or the Fixing Date of the transaction is used for the deteremination of the exposure item. This is defined in the hedging area. For more information, see also Hedging Area: Main Data

In case of the designation of FX options, the Value Date of Underlying or the Exercise Date of the FX Option is used for the determination of the exposure items. This is defined in the hedging area. For more information, see also Hedging Area: Main Data

In general, you can create several snapshots per day. However, you can create only one day reference snapshot per day because this restriction is important for hedge accounting. If this restriction would not apply, the system could not determine the correct snapshot during the automated designation process.

You can use the Manage Snapshots function (App ID: TOESNAPO) to get an overview of all existing snapshots for a hedging area including information about the snapshot for which the Day Reference indicator is set.

- 6. You can set the Reset Target Quota indicator. When you set this indicator, manually overwritten target quotas are reset and the target quotas originally defined in your hedging area are used again with the new snapshot date.
- 7. Choose Execute.


**Caution:**

For initialization of your hedging relationships, you need a snapshot with a validity before the oldest financial transaction used as hedging instrument and within the validity of the relevant hedging area version. The first snapshot that you take of a hedging area may have a date in the past, but any subsequent snapshots may not.

**Note:**

If a day reference snapshot for the day already exists but has not been used in hedge accounting so far, it is possible to create a new day reference snapshot. In that case, for the first snapshot, the day reference information is deleted.

**Results**

The selected incoming and outgoing exposures as well as the exposure items are saved. The snapshot was successful, if all messages are on status green.

When you execute the function, the incoming gross exposure items, outgoing gross exposure items, and net exposure items are created for each selected hedging area. The exposures are selected according to the settings in the filters of the respective hedging area.

In the snapshot tables, the selected single exposures are saved with their original data (for example, the amount, the exposure position ID, the time period from Exposure Management 2.0, additional differentiation criteria of the exposure

positions, and so on) and they ʻknow’ to which snapshot ID and which hedging area version they belong. In addition, the aggregated values for the incoming and outgoing exposures of an analysis item are saved and the exposure item IDs are created.

**Note:**

The saved incoming and outgoing single exposures and the aggregated amounts are not specific to valuation areas.

Thus, an exposure item has an exposure item ID and an amount per date and contains details about the hedging area version to which they belong. The due date of an exposure item is the end date of the relevant time period.

Versioning is used. The snapshot is always created with a key date set to the date of the runtime of the report.

##### Manage Snapshots

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Manage Snapshots | L4 | trm04 p.78 | loio `0ebe917f7ae34617923485ec69e3d3a0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0ebe917f7ae34617923485ec69e3d3a0.html?locale=en-US)

With this app, you get an overview of the snapshots of a hedging area.

The Manage Snapshots app gives you an overview of all snapshots of a hedging area. You can delete a snapshot when the following conditions are fulfilled:

The snapshot is the latest snapshot of the hedging area.

There is no hedge request for this latest snapshot with any status other than Canceled.

If the snapshot is relevant for hedge accounting, no new designations have been made to this hedging area since the snapshot was taken.

##### Hedge Management Cockpit

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Hedge Management Cockpit | L4 | trm04 p.78 | loio `d69ba95626c76b15e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d69ba95626c76b15e10000000a441470.html?locale=en-US)

**Use**

Using the Hedge Management Cockpit, you obtain an overview of your foreign exchange exposures, corresponding hedging instruments and hedging relationships in a hedging area. The calculated key figures support you by indicating special situations such as overhedge situations.

You define in your layouts, which key figures should be calculated and how they are displayed:

Creating Layout (Time Periods)

Creating Layout (Single References)

See also: Key Figures in the Hedge Management Cockpit

**Prerequisites**

Customizing for Hedge Management

You have defined your hedging areas.

See also: Hedging Area

Your exposure positions (from Exposure Management 2.0) and your hedging instruments in the transaction management of the Transaction Manager need to have all reporting-relevant information.

**Example:**

If you use the hedging classification as a selection criterion in the hedging area, you need to map the hedging classification to the exposure categories. In addition, you need to assign the hedging classifications in the financial transaction data of the hedging instruments on the Administration tab.

Define Layout

You have to define your layouts for the Hedge Management Cockpit. See also: Manage Layouts

Take your snapshots on a regular base. The Hedge Management Cockpit gets exposure data from the saved snapshots.

**Features**

The Hedge Management Cockpit supports all roles in the FX Risk Management Process with fast and reliable information.

Gives overview of your foreign exchange exposures, the corresponding hedging instruments and hedging relationships.

Presents the data per hedging area.

The Hedge Management Cockpit displays the key figures for the number of periods according to the setting in the Number of Periods field in the reporting time pattern of the hedging area.

**Note:**

If you have chosen period length Day, weekends (Saturdays and Sundays) are considered when determining the number of periods to be displayed and are highlighted in yellow.

Allows multiple layout definitions with reuse for different hedging areas.

Takes authorizations into account before data is presented.

Supports different levels of aggregation.

Supports drill-down from highest level of aggregation down to individual exposures or hedges.

The report selects data in accordance with your settings in the hedging area and with the key date and calculates all key figures defined in the layout.

The valid version of the hedging area is selected on the basis of the specified key date.

Creation of the hedge request in the Hedge Management Cockpit. The amounts of the hedge requests are also relevant for some key figures.

**Note:**

If you have chosen period length Day, you cannot create hedge requests on weekends and on bank holidays. So, if you accidentally created an exposure with a due date on a weekend or on a bank holiday, you need to correct the exposure and take a new snapshot for the hedging area.

Supports the automated creation of FX hedge requests.

**Note:**

The results are not stored in database tables.

Activities

- 1. Call the report in the back end from the Treasury and Risk Management area menu under Hedge Management and Accounting Hedge Management Reporting Hedge Management Cockpit (transaction TOENE) or call the Hedge Management Cockpit app on the SAP Fiori launchpad.
- 2. Choose a hedging area.
- 3. Choose a layout.
- 4. Choose .

Depending on the settings made in the layout, you now see the results list immediately. Alternatively, you first need to enter the snapshot ID and the date.

- 5. The report selects the exposures and hedging instruments and aggregates the amounts on the levels defined in the hedging area and layout.

An error log appears, showing all error/warning messages that occurred during this process.

- 6. In the results list, all amounts/values of the key figures are displayed.

Primary key figures: You can drill down to the original items that participated in this key figure. The original items are:

Exposure Item Data

Financial Transactions

Target Quota

From the generic drilldown popup, further drilldown is possible, which leads to the original transaction for the item:

Exposure Position List

This list is also displayed with the SAP List Viewer. See also: Overview of Exposure Positions

Financial Transactions

Hedging Relationship

Calculated key figures: Drilldown leads to the generic drilldown popup and lists all participating key figures (calculated and primary).

You can display the data of the hedging area.

- 7. You can use the filters available in the Filter Details area above the results list and defined in the layout to restrict the shown data.


**Note:**

When you place the cursor on the Net Exposure key figure, you can choose Show Details. On the following popup you can view the exposure item details. For hedging areas with analysis item definition By Reference you can change the description of the exposure item by choosing the Change pushbutton. During the creation of the exposure item the exposure item description is filled with the value entered in the Raw Exposure Description field, which might be an ID identifying your exposure.

Further Proceeding

The Hedge Management Cockpit gives you an overview of your current net open exposures, so you can take your hedging decisions.

If you detected an overhedge situation you can create hedge requests directly from the Hedge Management Cockpit. See also: Triggering the Creation of Automated FX Hedge Requests, Hedge Request and Process Hedge Requests.

In other cases, inform the responsible person for concluding hedging instruments on your hedging decision so this person can Create Financial Transactions that you want to use as hedging instruments for your net open exposures.

###### Triggering the Creation of Automated FX Hedge Requests

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Hedge Management Cockpit > Triggering the Creation of Automated FX Hedge Requests | L5 | trm04 p.81 | loio `78ba7cc286d44cad92b84ab01b822ee5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/78ba7cc286d44cad92b84ab01b822ee5.html?locale=en-US)

If you want your trader to hedge all open currency amounts for your hedging areas, you can create FX hedge requests automatically using the Hedge Management Cockpit app.

**Before You Get Started**

You have defined the relevant settings for the automated creation of FX hedge requests in your hedging areas using the Define Hedging Area app.

For more information, see Hedging Area: FX Hedge Request.

You have defined a layout that includes the key figure Amount to Hedge using the Hedge Management Cockpit.

**Note:**

An FX hedge request is created for every amount to hedge that is displayed.

For more information, see Manage Layouts.

**Triggering the Creation of Automated FX Hedge Requests**

- 1. Open the Hedge Management Cockpit app on your SAP Fiori launchpad.
- 2. Enter a hedging area.
- 3. Enter a layout.
- 4. Start the report.

The system selects the corresponding exposures and hedging instruments. The system aggregates the different amounts on the levels defined in the hedging area and layout.

The results list shows all amounts or values of the key figures.

- 5. To generate a proposal list of FX hedge requests, choose Automated Request Creation.

Based on the amounts of the key figure Amount to Hedge, a list of FX hedge requests is generated and displayed in a dialog box.

The status indicates whether an FX hedge request can be created automatically. If the status is not green, you have to create the FX hedge request manually.

For more information, see Creating an FX Hedge Request.

- 6. You can change the following values that were predefined in the settings of your hedging area:

Amount

Hedge Request Date

Hedging Classification

Instrument Category

- 7. To prevent the creation of FX hedge requests, deselect FX hedge requests from the list.


**Note:**

If the status of the FX hedge request is green, it is automatically marked for creation. You can select and deselect all FX hedge requests that are in green status.

- 8. To create your selected FX hedge requests, choose Enter.


**Result**

The FX hedge requests created are saved with a common group ID.

**What to Do Next**

As a next step, use the Process Hedge Requests app to submit and release the FX hedge requests. For easier selection, you can filter the FX hedge request list for the corresponding group ID.

**Note:**

Trade requests are generated automatically after the release of FX hedge requests when the Activate Trading Platform Integration checkbox was selected when you set up your hedging area.

The trading platform integration application can then retrieve the trade requests.

**More Information**

Hedge Management Cockpit

Process Hedge Requests

Integration with External Trading Platforms

###### Hedge Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Hedge Management Cockpit > Hedge Request | L5 | trm04 p.82 | loio `e3c3bd1a04e74d36866e8d90f6747f41` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e3c3bd1a04e74d36866e8d90f6747f41.html?locale=en-US)

You use the Hedge Management Cockpit to create hedge requests for analysis items.

**FX Hedge Request**

You use the FX hedge request if you want your trader to hedge a specific currency amount for a specific date.

If you have activated the SAP Trading Platform Integration in your hedging area, trade requests are generated whenever FX hedge requests are released. The corresponding trade request is linked from the FX hedge request. To see the trade request details, choose the Trade Request button.

Data of the FX Hedge Request

The FX hedge request has a hedge request ID, a hedge request category (= FX Hedge), and a hedge request status.

The FX hedge request contains the following tabs:

General

Analysis Item

Below, you see the information for the analysis item (specific values of the differentiation criteria identifying the analysis item).

The Snapshot ID field is filled automatically.

Net Exposure

The amount of the Net Exposure key figure is the sum of the amounts of all incoming exposures and all outgoing exposures of the analysis item.

Net Hedges

The amount of the Net Hedges key figure is the sum of the nominal amounts of the all hedges of the analysis item.

Scaling

The scaling factor controls the display of the amounts of the key figures in the Hedge Management Cockpit. The amounts are either displayed with the exact amount, or the amounts are rounded to the nearest thousand or million and displayed in thousands or in millions. You have selected the scaling factor when starting the Hedge Management Cockpit.

Example:

The exact amount of the key figure is 1.199.800,00 USD

If you have chosen the scaling factor Thousands, the amount is displayed as follows: 1200

If you have chosen the scaling factor Millions, the amount is displayed as follows: 1

Instrument Attributes

Hedging Classification

Portfolio

Value Date

Amounts

Hedge Request Amount

Action History

On this tab, you can see the Date, Time, and User fields for each action executed for this hedge request.

**Termination Request**

A termination request allows hedge managers to request their traders to initiate the premature termination of an FX transaction.

Data of the Termination Request

The termination request has a hedge request ID, a hedge request category (= FX Termination), and a hedge request status.

The termination request contains the following tabs:

General

Hedge Request Reason

Hedging Area

Company Code

Partner

Table Transactions for Termination

Overruling Allowed indicator

If the indicator is selected, also a table is displayed, where the hedging classification and the portfolio can be assigned to the financial transaction.

Note

Hedging Relationships

This tab is only relevant if hedge accounting is activated for the hedging area.

On this tab, you can see the Valuation Area, the Reclass. Handling field, and the table showing the hedging relationships to which the transaction to be terminated is assigned.

**Note:**

Termination of hedging instrument triggers the immediate complete dedesignation of the associated hedging relationships at the termination date. For more information, see also Dedesignation by Termination.

Analysis Item

Below, you see the information for the analysis item (specific values of the differentiation criteria identifying the analysis item) and the Snapshot ID field.

Action History

On this tab, you can see the Date, Time, and User fields for each action executed for this hedge request.

**Dedesignation Request**

**Note:**

The dedesignation request is only available for hedging areas with hedge accounting.

When you face an overhedge situation, however, you may decide to dedesignate hedging instruments completely or partially.

The release of the dedesignation request triggers the automated dedesignation process and results in the following:

The dedesignation hedging business transaction is created.

The system creates the dedesignation flows with the status Scheduled for the FX forward transaction and the exposure subitem.

Additional flows are created to transfer position values of hedging reserve, cost of hedging reserve, and P/L portions from the designated subposition to the free-standing subposition of the exposure subitems.

Data of Dedesignation Request

The dedesignation request has values in the following fields: Hedge Request ID, Hedge Req. Category (= Dedesignation), and Hedge Request Status.

The dedesignation request contains the following tabs:

General

At the top, you see the Hedging Area and Hedge Request Reason fields.

Using the Notes button, you can display the notes for the hedge request.

On this tab, enter values in the following fields: Dedesignation Date, Snapshot ID, and Hedge Request Amount.

The Snapshot ID field is filled automatically.

Hedging Relationships

Besides the Valuation Area, Consumption Sequence, and Reclassification Handling fields, you see the existing hedging relationships for this analysis item. The Reserved Amount and Hedge Request Amount fields are filled automatically and can be changed manually during the creation of the hedge request.

The reserved amount is the total amount reserved by other hedge requests for the hedging relationship that are not reflected in the designated amount so far. This kind of hedge request can be as follows for the hedging relationship:

Unreleased dedesignation requests with the status Created, Submitted, or Rejected.

Unreleased swap requests with the status Created, Submitted, or Rejected.

Released swap requests for which no swap transaction has been created so far.

Business Transactions

This tab is available after the release of the hedge request. It shows you the triggered business transactions in a table including the status information for the business transactions.

Analysis Item

Below, you see the information for the analysis item (specific values of the differentiation criteria identifying the analysis item).

Action History

On this tab, you can see the Date, Time, and User fields for each action executed for this hedge request.

**FX Swap Request**

**Note:**

The swap request is only available for hedging areas with hedge accounting.

When you face an overhedge situation, however, you may decide to swap amounts from one period to another.

Data of FX Swap Request

The swap request has values in the following fields: Hedge Request ID, Hedge Req. Category (= Swap), and Hedge Request Status.

The swap request contains the following tabs:

General

At the top, you see the Hedging Area and Hedge Request Reason fields.

Using the Notes button, you can display the notes for the hedge request.

At the bottom, you see the information for the analysis item (specific values of the differentiation criteria identifying the analysis item) in the Analysis Item area.

On this tab, enter the target value date on which you want to swap the amount. The target period is derived from the target value date specified.

You can see the hedging classification relevant for the swap.

Enter the hedge request amount here. In the Open Amount field, you see the difference between the hedge request amount and the amount already swapped by financial transactions created for this hedge request.

Hedging Relationships

If hedge accounting is active, the swap request contains information about the existing hedging relationships affected by the swap.

Besides the consumption sequence and the reclassification handling, you see the existing hedging relationships for this analysis item. The Reserved Amount and Hedge Request Amount fields are filled automatically and can be changed manually during the creation of the hedge request.

The reserved amount is the total amount reserved by other hedge requests for the hedging relationship that are not reflected in the designated amount so far. This kind of hedge request can be as follows for the hedging relationship:

Unreleased dedesignation requests with the status Created, Submitted, or Rejected.

Unreleased swap requests with the status Created, Submitted, or Rejected.

Released swap requests for which no swap transaction has been created so far.

Financial Transactions

This tab is available after the release of the hedge request. It shows you the financial transactions created for this hedge request.

**Prerequisites for Hedge Request Creation**

The creation of a hedge request (FX hedge request, termination request, FX swap request, and dedesignation request) is only possible if the following requirements are fulfilled:

Within the selected row, all relevant differentiation criteria of the hedging area version considered are displayed and have a specific value.

A unique period as per the reporting time pattern of the hedging area is assigned to the selected cell.

The snapshot chosen must be the current snapshot and must have the day reference indicator.

The key date must be the current date.

Automatically Filled Hedge Request Amount in FX Hedge Request

If the hedge request amount should be automatically filled for a FX hedge request, you must have defined net target quotas for the hedging area and chosen a layout for the Hedge Management Cockpit that contains the key figures related to the target quota.

The automatically filled hedge amount in the manually created FX hedge request is the value of the Amount to Hedge key figure or in case of target quota types based on target quota category Band of the Maximum Amount to Hedge key figure.

If you made settings on the FX Hedge Request tab of a hedging area in the Define Hedging Area app for the automated mass FX hedge request generation, these settings are also relevant for the manual FX hedge request creation.

On the FX Hedge Request tab of a hedging area in the Define Hedging Area app, you can make the following settings:

You specify how to determine the value date.

You define a default instrument category, the hedging classification, a minimum amount, and a rounding rule.

The system only enters a value in the Hedge Amount field of the manually created FX hedge request if the value of the key figure Amount to Hedge/Max. Amount to Hedge is greater than or equal to the minimum amount. If the amount is greater than or equal to the minimum amount, the amount is rounded down to the selected unit.

Note: The Value Date, Default Instrument Category, and Hedging Classification are also filled automatically in the manually created FX hedge request according to the settings on the FX Hedge Request tab.

**Note:**

How to create a layout for the Hedge Management Cockpit that contains the key figures related to the target quota?

In the layout, you must select a target quota type (for which you have entered net target quotas) and the target quota-related key figures. Which key figures you need to select depends on the target quota category of the selected target quota type:

Target quota-related key figures relevant for target quotas based on target quota category Limit

Target Quota [%]

Target Hedge Amount = Net Exposure * Target Quota (Single Limit) %

Sign of the amount has the opposite direction to that of the exposure.

Amount to Hedge = Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Target quota-related key figures relevant for target quotas based on target quota category Band

Lower Target Quota [%]

Upper Target Quota [%]

Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Lower Target Hedge Amount = Net Exposure * Lower Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Upper Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Min. Amount to Hedge = Lower Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Max. Amount to Hedge = Upper Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Target quota-related key figures relevant for target quotas based on target quota category Target Limit within Band:

Lower Target Quota [%]

Upper Target Quota [%]

Target Quota [%]

Min. Amount to Hedge

Max. Amount to Hedge

Target Hedge Amount = Net Exposure * Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Lower Target Hedge Amount = Net Exposure * Lower Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Upper Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Amount to Hedge = Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Statuses and Status Transitions of Hedge Requests

[figure TRM04-F014 - Statuses and Status Transitions of Hedge Requests]

|Status of Hedge Request|Explanation|
|---|---|
|Created|When a hedge request has been created in the Hedge Management Cockpit, the hedge request gets the status Created. The hedge request then needs to be checked. Before submitting the hedge request, you can make changes to it. When everything is fine with the hedge request, you can submit the hedge request. After you have submitted the hedge request, it gets the status Submitted. The other option is to delete the hedge request.|


|Status of Hedge Request|Explanation|
|---|---|
|Submitted|You can release or reject hedge requests in status Submitted: Rejected hedge requests get the status Rejected. Released hedge requests get the status Released.|
|Rejected|You can change an hedge requests in status Rejected submit it again or you can delete the hedge request.|
|Released|Released FX Hedge Requests Released FX hedge requests are now relevant for the trader, who creates hedging instruments according to the information given in the hedge request. The released FX hedge request can be withdrawn. Released Termination Request Released termination requests are now relevant for the trader, who terminates the financial transaction and completes the termination request or overrules the termination request in Process Hedge Requests app. Overruling sets the termination request to status Overruled and creates a new hedge request of category FX Hedge in status Released, and the description indicates that it is an offsetting transaction. You can withdraw a termination request in status Released. For more information about the process steps that take place after the release of the termination request, see also Process a Termination Request. Released Dedesignation Requests Based on the released dedesignation request, the system creates dedesignation business transactions with the status Planned. Using function Release Hedging Business Transactions, **Note:** If you have activated the SAP Trading Platform Integration in the hedging area, after the release of the FX hedge requests, the system creates a corresponding trade request and the trade request ID and trade request status are displayed in the FX hedge request. In this case, you cannot withdraw an FX hedge request in the SAP S/4HANA system. However, the SAP Trading Platform Integration application offers you the option to decline the related trade request. Declining the trade request leads to the status change of the FX hedge request to Withdrawn.|


|Status of Hedge Request|Explanation|
|---|---|
| |you release the dedesignation. Depending on the settings in the dedesignation request, the reclassification is performed immediately or on the planned dedesignation date. For dedesignation requests, it is also possible to withdraw the released dedesignation request. The hedge request gets the status Withdrawn afterward. For more information about the process steps that take place after the release of the dedesignation request, see Process Dedesignation Request. Released Swap Requests Based on the released swap request, the trader concludes the FX swap transactions For swap requests, it is also possible to withdraw the released swap request. The hedge request gets the status Withdrawn afterward. **Note:** If you have activated the SAP Trading Platform Integration for the hedging area, system automatically creates a corresponding trade request and displays the Trade Request ID and the Trade Request Status in the swap request. In this case, you cannot withdraw a swap request in the SAP S/4HANA system. However, the SAP Trading Platform Integration application offers you the option to decline the related trade request. Declining the trade request leads to the status change of the swap request to Withdrawn.|
|Overruled|This status is only available for termination requests. The Process Hedge Requests app offers the possibility to undo the overruling. When you undo the overruling the termination request gets status Released. When the offsetting transaction has been created the termination request gets status Completed.|
|Completed|Final status of a hedge request.|


**Related Information**

Creating an FX Hedge Request Creating an FX Swap Request Creating a Dedesignation Request Creating a Termination Request Process Hedge Requests Process FX Swap Request

Process Dedesignation Request Process Trade Requests

###### Creating an FX Hedge Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Hedge Management Cockpit > Hedge Request > Creating an FX Hedge Request | L6 | trm04 p.91 | loio `bbd784d07a784e468a86af9bc9f18d77` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bbd784d07a784e468a86af9bc9f18d77.html?locale=en-US)

If you want your trader to hedge a specific currency amount for a specific value date, you can create an FX Hedge Request directly from Hedge Management Cockpit app. You can, but you do not need to, specify the hedging instrument (such as FX forward transaction or FX spot transaction).

- 1. Place the cursor on the analysis item where you want to hedge an amount.
- 2. Choose Hedge Request FX Hedge Request .
- 3. Information from the analysis item is taken over and displayed in the Analysis Item area on the General tab.
- 4. Enter the value date, it has to be within the period of the analysis item.
- 5. Enter the amount to be hedged in the Hedge Request Amount field. Enter the sign of the amount.
- 6. In addition, you can enter the instrument category (FX Forward, FX Spot, FX Option, NDF, or FX Collar ) and the hedging classification. If you want to leave the decision on the hedging instrument to the trader you do not need to enter anything in these fields.
- 7. You can use Check to check the entered data.
- 8. Save your entries and the hedge request is created with Created status, or submit the hedge request and the hedge request is created with Submitted status.
- 9. To submit and release the hedge request, use the Process Hedge Requests app.

###### Creating an FX Swap Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Hedge Management Cockpit > Hedge Request > Creating an FX Swap Request | L6 | trm04 p.91 | loio `9c9fab5b480740b6ac8ededb7e16490b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9c9fab5b480740b6ac8ededb7e16490b.html?locale=en-US)

If you have an overhedge situation in which you would like to swap an amount from one period to another using an FX swap, you can create swap requests.

**Caution:**

This action only works if the hedging area is relevant for Hedge Accounting (see Hedging Area: Main Data) and the original transactions for the request have been designated (see Automated Designation Process).

If Hedge Accounting is active, the swap request contains information about the existing hedging relationships affected by the swap.

- 1. Place the cursor on the analysis item from which you want to swap amounts to another period.
- 2. Choose Hedge Request FX Swap Request .
- 3. Information from the analysis item is taken over and displayed in the Analysis Item area on the General tab.
- 4. Choose the reason for the swap request.
- 5. Use the Notes button to enter any information specific to the hedge request. Do not enter any information on natural persons here.
- 6. Enter the target value date on which you want to perform the swap.
- 7. Choose the hedging classification to be used for the FX swap.


- 8. Enter the amount to be swapped in the Hedge Request Amount field. The sign of the amount has to be the opposite of the amount of designated hedges.
- 9. If Hedge Accounting is active, go to the Hedging Relationship tab.

The existing hedging relationships for this analysis item are displayed.

Choose Reclassification Handling. The reclassification can be performed either immediately (for example, in the case of gross overhedging) or on a scheduled date (for example, in the case of net overhedging).

According to the relevant consumption sequence (derived from settings of the relevant hedging area version), the hedging relationships to be swapped are marked and the requested amount (= amount to be swapped) is entered. If no consumption sequence is chosen, enter the hedge request amount manually. In addition, you can change the requested amounts determined automatically.

In the Reserved Amount column, you see the amounts reserved by other hedge requests for the hedging relationships that are not reflected in the designated amount so far. These kinds of hedge request for the hedging relationship are the following:

Unreleased dedesignation requests with the status Created, Submitted, or Rejected.

Unreleased swap requests with the status Created, Submitted, or Rejected.

Released swap requests for which no swap transaction has been created so far.

- 10. You can use the Check pushbutton to check the data entered.
- 11. Save your entries. Either the hedge request is created with the status Created, or you submit the hedge request so that the hedge request is created with the status Submitted.
- 12. To release the hedge request, use the Process Hedge Requests app on the SAP Fiori launchpad or transaction TOEHREQO in the back-end system.


**Related Information**

Hedge Request Process Hedge Requests Process FX Swap Request

###### Creating a Dedesignation Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Hedge Management Cockpit > Hedge Request > Creating a Dedesignation Request | L6 | trm04 p.92 | loio `d56e585e4ce342a39b52bdb7968b5ef2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d56e585e4ce342a39b52bdb7968b5ef2.html?locale=en-US)

If you have an overhedge situation due to an exposure reduction, you can create dedesignation requests.

- 1. Place the cursor on the analysis item from which you want to swap amounts to another period.
- 2. Choose Hedge Request Dedesignation Request .
- 3. Information from the analysis item is taken over and displayed in the Analysis Item area on the General tab.
- 4. Choose the reason for the dedesignation request.
- 5. Use the Notes button to enter any information specific to the hedge request. Do not enter any information on natural persons here.
- 6. Enter the dedesignation date, it has to be later than the designation date.
- 7. Enter the amount to be dedesignated in the Hedge Request Amount field. The sign of the amount is determined automatically and has to be the opposite of the sign of the designated amount.


- 8. Go to the Hedging Relationship tab.

Choose the Reclassification Handling. The reclassification can be done immediately (for example, in the case of gross overhedging) or as planned (for example, in the case of net overhedging).

The existing hedging relationships for this analysis item are displayed.

According to the relevant consumption sequence (derived from settings of the relevant hedging area version), the hedging relationships to be dedesignated are marked and the requested amount (= amount to be dedesignated) is entered. If no consumption sequence is chosen, enter the hedge request amount manually. In addition, you can change the automatically determined requested amounts.

In the Reserved Amount column, you see the amounts reserved by other hedge requests for the hedging relationship, which are not reflected in the designated amount so far. These kinds of hedge request for the hedging relationship are the following :

Unreleased dedesignation requests in Created, Submitted, or Rejected status.

Unreleased swap requests in Created, Submitted, or Rejected status.

Released swap request for which no swap transaction has been created so far.

- 9. You can use the Check pushbutton to check the entered data.
- 10. Save your entries and the hedge request is created with Created status, or submit the hedge request and the hedge request is created with Submitted status.
- 11. To submit and release the hedge request, use the Process Hedge Requests app on the SAP Fiori launchpad or transaction TOEHREQO in the back-end system.


**Related Information**

Hedge Request Process Hedge Requests Process Dedesignation Request

###### Creating a Termination Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Hedge Management Cockpit > Hedge Request > Creating a Termination Request | L6 | trm04 p.93 | loio `cac08812f2d84fb984dfca5545a628ed` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cac08812f2d84fb984dfca5545a628ed.html?locale=en-US)

A termination request allows hedge managers to request their traders to initiate the premature termination of an FX transaction.

**Context**

To request termination for an FX transaction, open the Key Figure: Net Hedges screen and choose it from the list of hedges and create a termination request. The termination request is now created and available in the Process Hedge Requests app for further processing.

You can set the Overruling Allowed indicator. This allows your trader to overrule the termination request and instead create an offsetting transaction if the conditions of your business partner for termination do not meet your requirements.

**Procedure**

- 1. In the Hedge Management Cockpit, choose a hedging area and a layout ID. Then choose Start to display the key figures for this hedging area.
- 2. Go to a period with existing net hedges and double-click the cell to drill down to the Key Figure: Net Hedges screen.


- 3. Under Hedges, you see a list of financial transactions. Select the left-hand checkbox to choose a transaction and choose Hedge Request Termination Request to create a termination request.
- 4. On the Create Hedge Request screen, you see that the hedge request category is set to FX Termination. You can enter a hedge request reason and a note.
- 5. You can allow the trader to offset the existing transaction with a new one in case the termination conditions are unfavorable. In this case, activate the Overruling Allowed checkbox.
- 6. If activated, a table appears under the checkbox. Enter values in the fields Hedging Classification and Portfolio.
- 7. Choose Check to validate your entries and then choose Submit to create the termination request.


**Related Information**

##### Process Hedge Requests

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Process Hedge Requests | L4 | loio `e3bc39264e324b149491700796a8f196` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e3bc39264e324b149491700796a8f196.html?locale=en-US)

Central location for reviewing and working on hedge requests.

**Use**

Within the Process Hedge Requests function, you can search for all existing hedge requests and generate a worklist. You can search for the hedge requests by their category (FX Hedge Request, Termination Request, Swap Request, or Dedesignation Request) and their status.

**Features**

List hedge requests and sort them by different filters, such as Category, Status, and others.

Process hedge requests, for example by submitting them for release, releasing/rejecting hedge requests or withdrawing hedge requests.

Dual control when hedge requests are released or rejected. This means that the person who releases or rejects the hedge request is checked against the creator of the request. By default, no message is displayed. You can use Customizing to control whether this is an information message or an error message. You can do this by making an entry in the Customizing activity Change Message Control under Treasury and Risk Management Transaction Manager General Settings

Transaction Management :

Application area FTOE_HREQ_CORE, message number 007

**Statuses and Status Transitions of Hedge Requests**

[figure TRM04-F015]

|Status of Hedge Request|Explanation|
|---|---|
|Created|When a hedge request has been created in the Hedge Management Cockpit, the hedge request gets the status Created. The hedge request then needs to be checked. Before submitting the hedge request, you can make changes to it. When everything is fine with the hedge request, you can submit the hedge request. After you have submitted the hedge request, it gets the status Submitted. The other option is to delete the hedge request.|
|Submitted|You can release or reject hedge requests in status Submitted: Rejected hedge requests get the status Rejected. Released hedge requests get the status Released.|
|Rejected|You can change an hedge requests in status Rejected submit it again or you can delete the hedge request.|
|Released|Released FX Hedge Requests Released FX hedge requests are now relevant for the trader, who creates hedging instruments according to the information given in the hedge request. The released FX hedge request can be withdrawn. **Note:**|


|Status of Hedge Request|Explanation|
|---|---|
| |Released Termination Request Released termination requests are now relevant for the trader, who terminates the financial transaction and completes the termination request or overrules the termination request in Process Hedge Requests app. Overruling sets the termination request to status Overruled and creates a new hedge request of category FX Hedge in status Released, and the description indicates that it is an offsetting transaction. You can withdraw a termination request in status Released. For more information about the process steps that take place after the release of the termination request, see also Process a Termination Request. Released Dedesignation Requests Based on the released dedesignation request, the system creates dedesignation business transactions with the status Planned. Using function Release Hedging Business Transactions, you release the dedesignation. Depending on the settings in the dedesignation request, the reclassification is performed immediately or on the planned dedesignation date. For dedesignation requests, it is also possible to withdraw the released dedesignation request. The hedge request gets the status Withdrawn afterward. For more information about the process steps that take place after the release of the dedesignation request, see Process Dedesignation Request. Released Swap Requests Based on the released swap request, the trader concludes the FX swap transactions For swap requests, it is also possible to withdraw the released swap request. The hedge request gets If you have activated the SAP Trading Platform Integration in the hedging area, after the release of the FX hedge requests, the system creates a corresponding trade request and the trade request ID and trade request status are displayed in the FX hedge request. In this case, you cannot withdraw an FX hedge request in the SAP S/4HANA system. However, the SAP Trading Platform Integration application offers you the option to decline the related trade request. Declining the trade request leads to the status change of the FX hedge request to Withdrawn.|


|Status of Hedge Request|Explanation|
|---|---|
| |the status Withdrawn afterward. **Note:** If you have activated the SAP Trading Platform Integration for the hedging area, system automatically creates a corresponding trade request and displays the Trade Request ID and the Trade Request Status in the swap request. In this case, you cannot withdraw a swap request in the SAP S/4HANA system. However, the SAP Trading Platform Integration application offers you the option to decline the related trade request. Declining the trade request leads to the status change of the swap request to Withdrawn.|
|Overruled|This status is only available for termination requests. The Process Hedge Requests app offers the possibility to undo the overruling. When you undo the overruling the termination request gets status Released. When the offsetting transaction has been created the termination request gets status Completed.|
|Completed|Final status of a hedge request.|


**Integration**

You can control the process of hedge requests using authorization object T_TOE_HR (Hedge Request).

**Related Information**

Process FX Swap Request Process Dedesignation Request Process a Termination Request Trade Request

###### Process FX Swap Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Process Hedge Requests > Process FX Swap Request | L5 | loio `c757b9554e53478b8c399a88581673f7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c757b9554e53478b8c399a88581673f7.html?locale=en-US)

**Use**

You have created an FX swap request due to an overhedge situation using the hedge request functionality in the Hedge Management Cockpit app. The FX swap request contains information about the hedging relationship to be swapped to another

exposure item period. Once the request is released the trader concludes the FX swap and further activities relevant for hedge accounting start.

**Note:**

Limitations:

An FX swap request does not consider any splitting information that was entered in the hedging area.

You cannot transfer amounts from a single hedging relationship with more than one FX swap request

**Features**

The FX swap request supports the following features:

Transfer amounts from a period to a period after the current due date of the FX transaction

Transfer amounts from a period to a period earlier than the current due date of the FX transaction

Transfer amounts from one hedging relationship to another hedging relationship that belongs to a different valuation area

**Process Steps**

The following process steps have to be carried out after the FX swap request was created:

- 1. Use the Process Hedge Requests app to release your FX swap request.
- 2. Create both FX forward transaction for your FX swap using the Create FX Swap app.


Please consider the following entries:

Company Code

This value must be identical for the two FX forward transactions.

Product Category

This value must be identical for the two FX forward transactions.

Rate and Buy/Sell:

The currency pair of the first FX forward transaction must be the reverse of the original FX forward transaction.

The currency pair of the second FX forward transaction is identical to the original FX forward transaction.

Traded Amount

Enter the amount that is part of your FX swap request for both FX forward transactions.

Value Date:

The both FX forward transactions must have the same value date.

The value date of the second FX forward transaction must be within the exposure item period of your second exposure.

Contract Date

The FX forward transactions must have the same contract date.

Enter your hedging classification and hedge request ID on the Administration tab. Both values must be identical for the two FX forward transactions.

The differentiation criteria must be identical for the two FX forward transactions.

**Note:**

These values must be correct to ensure the successful creation of the FX swap.

- 3. The creation of the FX swap triggers the automated designation process and results in the following:

New hedging relationship

A new hedging relationship with Planned Designation status is created with designation date on the swap date

Also, a hedging business transaction of the Hedging Relationship Swap Transfer type is created if the abovementioned prerequisites are fulfilled. The Hedging Relationship Swap Transfer hedging business transaction is relevant for the original and the new hedging relationship.

Original hedging relationship

Nominal amounts of hedged item (exposure subitem), hedging instrument (FX forward transaction), and hypothetical derivative as well as pro rata amounts of hedging reserve and cost of hedging reserve are transferred out on the swap date

In case of a partial swap, the remaining portions of the amounts are processed within the original hedging relationship according to the settings on designation date

- 4. Release the new hedging relationship (Hedging Relationship Swap Transfer hedging business transaction) on the swap date using the Release Hedging Business Transactions app.
- 5. Carry out the period-end closing process steps for the original and the new hedging relationship. This process includes the following three steps:

Calculation of NPVs and market value components

Key date valuation

Classification

- 6. At the end of the two hedging relationships, carry out the following processes:

Dedesignation on the maturity date of the FX transaction

Reclassification on the end date of the exposure subitem

- 7. Carry out position reporting to complete the hedge accounting process.


**Related Information**

Automated Designation Process - FX Swap Release Hedging Business Transactions - FX Swap Transfer Period-End Closing - FX Swap Contract Close - FX Swap

###### Process Dedesignation Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Process Hedge Requests > Process Dedesignation Request | L5 | loio `e82791cb00914314ba4864969540aea3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e82791cb00914314ba4864969540aea3.html?locale=en-US)

**Use**

The decision to dedesignate a hedging relationship using the Hedge Request functionality is based on the key figures calculated in the Hedge Management Cockpit. You can dedesignate hedging relationships in case an overhedging situation occurs. The following dedesignation categories can apply, depending on the settings you have maintained in the Reclassification Handling field on the Hedging Relationship tab of the dedesignation request:

Gross overhedging

In this case, reclassification takes place immediately after the dedesignation business transaction has been released.

Net overhedging

In this case, reclassification takes place on the end date of the exposure subitem.

Hedging relationships can be partially or fully dedesignated. A partial dedesignation reduces the nominal amounts of the hedging relationships.

**Features**

The dedesignation request supports the following features:

Dedesignate several hedging relationships of a single FX forward transaction with one dedesignation request

Dedesignate several hedging relationships of several FX forward transactions with one dedesignation request

Dedesignate hedging relationships that belong to different valuation areas with one single dedesignation request

**Process Steps**

The following process steps have to be carried out after the dedesignation request was created:

- 1. Use the Process Hedge Requests function (transaction TOEHREQO) to release your dedesignation request.
- 2. The release of the dedesignation request triggers the automated dedesignation process and results in the following:

The Dedesignation hedging business transaction is created.

Dedesignation update types are created in Scheduled status for the FX forward transaction and the exposure subitem.

Additional update types are created to transfer position values of hedging reserve, cost of hedging reserve, and P/L portions from the designated subposition to the free standing subposition of the exposure subitems.

- 3. Release the Dedesignation hedging business transaction on dedesignation date using the Release Hedging Business Transactions function (transaction TPM120).


Depending on the Reclassification Handling set in the dedesignation request, the reclassification flows are created in Scheduled status or are immediately posted after the release of the hedging business transaction.

**Note:**

When the reclassification considers the balance sheet recognition date the premature dedesignation has effects on the reclassification:

Premature Dedesignation Before Balance Sheet Recognition Date: Reclassification Handling

|Setting in Hedging Area in Consider Balance Sheet Recognition Field|Effect on Reclassification|Reclassification Handling in Dedesignation Request Planned Reclassification|Reclassification Handling in Dedesignation Request Immediate Reclassification|
|---|---|---|---|
|Immediate reclassification at balance sheet recognition date|Value at dedesignation date needs to be reclassified|Reclassification at the balance sheet recognition date using the reclassification flows DBT_KC*|Immediate reclassification at dedesignation date using the reclassification flows DBT_KB*|


|Setting in Hedging Area in Consider Balance Sheet Recognition Field|Effect on Reclassification|Reclassification Handling in Dedesignation Request Planned Reclassification|Reclassification Handling in Dedesignation Request Immediate Reclassification|
|---|---|---|---|
| | |The reclassification is posted using alternative update flows assigned in Customizing under Alternative Update Types for Position Outflows for Reclassification at Balance Sheet Recognition Date. This settings allows you to post the reclassification in this specific case using other accounts.|The reclassification is posted using alternative update flows assigned in Customizing under Alternative Update Types for Position Outflows for Immediate Reclassification at Dedesignation. This settings allows you to post the reclassification in this specific case using other accounts.|
|Reclassification at End Date of Exposure Subitem Date|Value at dedesignation date frozen|Reclassification at the end date of exposure subitem using the reclassification flows DBT_K*| |
|Reclassification at Alternative Reclassification Date|Value at dedesignation date frozen|Reclassification at the alternative reclassification date using the reclassification flows DBT_K*| |


Premature Dedesignation After Balance Sheet Recognition Date: Reclassification Handling

Setting in Hedging Area in Consider Balance Sheet Recognition Date

Effect on Reclassification Reclassification Handling in Dedesignation Request

Reclassification Handling in Dedesignation Request

Planned Reclassification

Immediate Reclassification

Immediate Reclassification at Balance Sheet Recognition Date

Value at BSRD reclassified

Reclassify delta values at dedesignation date

Reclassification of delta values after BSRD at dedesignation date using the reclassification flows DBT_KB*

Reset + immediate reclassification at dedesignation date using the reclassification flows DBT_KB*

The calculated amounts that were already reclassified at the BSD must be reset and posted to the P/L account relevant for premature dedesignation. The system creates the corresponding flows according to the relevant Customizing setting for Alternative Update Types for Position Outflows for the condition Immediate Reclassification at Dedesignation.

Reclassification at End Date of Exposure Subitem Date

Value at BSRD frozen until end date of exposure subitem

Reclassification at end date of exposure subitem using

Immediate reclassification at dedesignation date using the

|Setting in Hedging Area in Consider Balance Sheet Recognition Date|Effect on Reclassification|Reclassification Handling in Dedesignation Request Planned Reclassification|Reclassification Handling in Dedesignation Request Immediate Reclassification|
|---|---|---|---|
| |Delta value after BSRD frozen at dedesignation date|reclassification flows DBT_KA* The reclassification is posted using alternative update flows assigned in Customizing under Alternative Update Types for Position Outflows for Reclassification after Balance Sheet Recognition Date. This settings allows you to post the reclassification in this specific case using other accounts.|reclassification flows DBT_KB* The reclassification is posted using alternative update flows assigned in Customizing under Alternative Update Types for Position Outflows for Immediate Reclassification at Dedesignation. This settings allows you to post the reclassification in this specific case using other accounts.|
|Reclassification at Alternative Reclassification Date|Value at BSRD frozen until alternative reclassification date Delta value after BSRD frozen at dedesignation date|Reclassification at alternative reclassification date using reclassification flows DBT_KA* The reclassification is posted using alternative update flows assigned in Customizing under Alternative Update Types for Position Outflows for Reclassification after Balance Sheet Recognition Date. This settings allows you to post the reclassification in this specific case using other accounts.| |


- 4. Carry out the period-end closing process for the dedesignated financial transaction. This process includes the following three steps:


Calculation of NPVs and market value components

Key date valuation

The key date valuation sets the actual value of the freestanding portion of the FX forward transaction on the dedesignation date. This is the start value for the classification until the maturity of the FX forward transaction.

Full dedesignation

Only a freestanding portion of the FX forward transaction is available. Therefore, only the freestanding portion is valuated and posted on the dedesignation date.

The exposure subitem is no longer affected by the classification run.

Partial dedesignation

The FX forward transaction has a freestanding portion and a designated portion. Both are valuated and posted on the dedesignation date.

The exposure subitem is no longer affected by the classification run.

Classification

- 5. At the end of the hedging relationship, carry out the following processes:

Dedesignation of the remaining portion of the FX transaction on its maturity date

Reclassification of hedging reserve and cost of hedging reserve amounts on the end date of the exposure subitem

This step applies if the reclassification handling was set to Planned Reclassification in the dedesignation request.

For more information, see Contract Close.

- 6. Carry out position reporting to complete the hedge accounting process.


For more information, see Reporting.

**Withdraw Dedesignation Request**

You can withdraw dedesignation requests that are in Released status.

**Note:**

If you have already released the Dedesignation hedging business transaction with the Release Hedging Business Transactions function (transaction TPM120), you first have to reverse the status of the dedesignation update type from Fixed to Scheduled using Reverse Release of Hedging Business Transactions (transaction TPM121).

- 1. Use the Process Hedge Requests function (transaction TOEHREQO) to withdraw your dedesignation request.
- 2. Enter the relevant hedging area, company code, currency, and the creation date of the dedesignation request to limit the number of results.

Then choose Start.

- 3. Select a hedge request from the list and choose Process Withdraw .
- 4. A success message appears and the status of the hedge request changes to Withdrawn.


**Note:**

You can also limit your search by selecting the Category and Status of your hedge request.

With the withdrawal of the dedesignation request the hedging business transactions that were in Planned Dedesignation status are deleted and the dedesignated amount is displayed as Designated again in the Hedge Management Cockpit (transaction TOENE).

**Related Information**

Process Hedge Requests Settings for Hedge Accounting for Exposure Items

**Process a Termination Request**

A termination request allows hedge managers to request their traders to initiate the premature termination of an FX transaction.

**Use**

You have created a termination request in the Hedge Management Cockpit app. It is forwarded to the trader, who uses the Process Hedge Requests app to terminate the FX transaction or overrule the termination request. In case of overruling, the trader does not terminate the FX transaction, but creates a new transaction to offset the old one.

**Process a Termination Request**

The termination request must have been created before you carry out these steps.

- 1. Since a termination request is a type of hedge request, open the Process Hedge Requests app and enter your hedging area to show all termination requests belonging to this hedging area. You can also search directly for the Hedge Request ID of your termination request.
- 2. In the search results table, double click the line of a termination request with the status Submitted to navigate to the Display Hedge Request screen.
- 3. Choose Display <-> Change to edit the termination request.
- 4. You can now Release or Reject the termination request.
- 5. Once the termination request is released, you can terminate the transaction using the following apps, depending on the product type:


Collective Processing: Transaction Management

###### Process a Termination Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Process Hedge Requests > Process a Termination Request | L5 | trm04 p.104 | loio `11aae9cb9608473484f038442ac8d555` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/11aae9cb9608473484f038442ac8d555.html?locale=en-US)

##### Create Hedging Instruments

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Create Hedging Instruments | L4 | trm04 p.105 | loio `d66487580b032060e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d66487580b032060e10000000a44147b.html?locale=en-US)

You create the needed hedging instruments using the Create Financial Transactions (transaction FTR_CREATE), Create Collar FX Option (transaction TI4B), or Create FX Swap (transaction TX10) functions. You can also use Create Reference transaction TBR6) to create an FX swap or a collar FX option.

**Use**

The trader can get the information which hedging instruments are needed from Process Hedge Requests function. All released hedge request of the hedge request catagories FX Hedge Request and Swap Request are relevant.

**Procedure**

- 1. Call one of the following functions to create financial transactions acting as the hedging instruments:

Create FX Spot/Forward available as app on SAP Fiori launchpad or in back end using function Create Financial Transaction (transaction FTR_CREATE)

Create Non-Deliverable Forwards available as app on SAP Fiori launchpad or in back end using function Create Financial Transaction (transaction FTR_CREATE)

Create FX Option available as app on SAP Fiori launchpad or in back end using function Create Financial Transaction (transaction FTR_CREATE)

Create Collar FX Option available as app on SAP Fiori launchpad or in back end (transaction TI4B)

Create FX Swap available as app on SAP Fiori launchpad or in back end using function Create Forex Swap (transaction TX10)

- 2. Enter the company code, product type, transaction type, and the business partner.
- 3. Choose Enter to branch to the basic data screen for the transaction. On the Structure tab, enter the actual transaction data for the financial transaction.


**Example:**

FX Forward

Currency pair/Exchange rate

Buy/Sell indicator

Traded currency

Traded amount

Value date

**Note:**

The Value Date of the FX forward must fall within the period of the exposure item.

For hedging areas with analysis item definition By Time Periods, reporting time pattern Calendar-Related, and period length Monthly. A due date shift can be defined in the hedging area on Hedging Area: General Settings tab.

The due date shift allows you to report your hedging instruments in the Hedge Management Cockpit in the following month after the due date of the hedging instrument. This means, that these hedging instruments are used to hedge the exposure items of the following month.

The automated designation process considers the due date shift and searches for exposure items in the following month.

- 4. During the creation of the financial transaction you should also enter the Hedge Management relevant data on the Administration tab.


Hedging Classification

You must enter the hedging classification. When the entered hedging classification is relevant for hedge accounting, the automated designation process starts when you save the financial transaction.

Financial transaction is part of a swap and created due to a swap request

If the assigned hedging classification is marked as Relevant for Hedge Accounting, then in addition it is necessary that in the hedging area master data on Hedge Accounting II tab a hedging profile and one of the following designation categories (indirect assigned through the assignment of the designation type) is assigned for a combination of company code, valuation area and the chosen hedging classification:

N Instruments (Swap) Designation Pattern

In addition, enter the hedge request ID of the swap request in the field below.

The automated designation process for FX swaps is started (after you saved your entries using Create FX Swap or after you saved the creation of the reference SWP using Create Reference function).

If all prerequisites are fulfilled, a hedging business transaction of type Hedging Relationship Swap Transfer is created.

The Hedging Relationship Swap Transfer hedging business transaction is relevant for the original hedging relationship in the FX swap.

See also Automated Designation Process - FX Swap.

Financial transaction is part of a swap, but you would like to handle the two transaction as individual hedging instruments

In this case, if the assigned hedging classification is marked as Relevant for Hedge Accounting, it is necessary that in the hedging area master data on Hedge Accounting II tab a hedging profile and the following designation category (indirect assigned through the assignment of the designation type) is assigned for a combination of company code, valuation area and the chosen hedging classification:

One Instrument Designation Pattern

You do not enter a hedge request ID.

In this case, the standard automated designation process is started. See also Automated Designation Process.

It is possible, that you separatly hedge both sides of an FX swap, but you could also only use one side for hedging.

Financial transaction is part of a collar FX option and you want to designate both FX options in one hedging relationship

In this case, if the assigned hedging classification is marked as Relevant for Hedge Accounting, it is necessary that in the hedging area master data on Hedge Accounting II tab a hedging profile and the

following designation category (indirect assigned through the assignment of the designation type) is assigned for a combination of company code, valuation area and the chosen hedging classification:

Two Instruments (Collar) Designation Pattern

In this case, the automated designation process for Collar FX options is started. See also Automated Designation Process - FX Collar.

Financial transaction is part of a collar FX option, but you would like to handle the long position of the collar FX option as an individual hedging instrument.

In this case, if the assigned hedging classification is marked as Relevant for Hedge Accounting, it is

necessary that in the hedging area master data on Hedge Accounting II tab a hedging profile and the following designation category (indirect assigned through the assignment of the designation type) is assigned for a combination of company code, valuation area and the chosen hedging classification:

One Instrument Designation Pattern

In this case, the standard automated designation process is started. See also Automated Designation Process.

Possible Combinations of Designation Categories for FX Swaps and FX Collars

|Designation Catory Side 1|Designation Catory Side 2|Result|
|---|---|---|
|FX Swap| | |
|One Instrument|One Instrument|The FX transactions are designated to different hedging relationships. See also: Automated Designation Process |
|-|One Instrument|Only the second FX transaction of the swap is designated to a hedging relationships. See also: Automated Designation Process |
|One Instrument|-|Only the first FX transaction of the swap is designated to a hedging relationships. See also: Automated Designation Process |
|N Instruments (Swap)|N Instruments (Swap)|The FX transactions are designated to the same new hedging relationship as part of a hedging business transaction of type Hedging Relationship Swap Transfer. See also: Automated Designation Process - FX Swap |
|Collar FX Option| | |
|-|One Instrument|Only the second FX option of the collar is designated to a hedging relationships.|


|Designation Catory Side 1|Designation Catory Side 2|Result|
|---|---|---|
| | |See also: Automated Designation Process |
|One Instrument|-|Only the first FX option of the collar is designated to a hedging relationships. See also: Automated Designation Process |
|Two Instruments (Collar)|Two Instruments (Collar)|The FX options are designated to the same new hedging relationship. See also: Automated Designation Process - FX Collar |


Hedge Request ID

If the financial transaction is part of a swap and created due to a swap request, enter the hedge request ID of the swap request.

This ensures that the key figures of the Hedge Management Cockpit are updated accordingly and a new hedging relationship is created in hedge accounting.

Additional Fields

When one or more of the following fields are differentiation criteria in your hedging area, you need to enter the relevant values:

Portfolio

Profit Center

Cost Center

WBS Element

On Behalf of Company Code

Country/Region Key

Segment

Business Area

- 5. If you create a hedging instrument for an exposure item by reference, you must enter the exposure item ID.

You assign the Exposure Item ID on FX Hedge Management tab.

In case, you do not know the exposure item ID, you can use the Elementary Search Help for Exposure Item ID by String.

- 6. Save your entries.


When you save the financial transaction, the standard automated designation process or the Automated Designation Process - FX Swap starts.

**Constraints**

You can use the following kinds of financial transactions as hedging instruments:

FX Forward Transaction (product type 60A, transaction type 102)

Non-Deliverable Forward (product type 60B, transaction type 110)

Plain Vanilla FX Option - European Style (product type 76A, transaction types 100 and 200)

Collar FX Option - European Style (product type 76A, transaction types 100 and 200)

**Related Information**

Create FX Spot/Forward Creating a Non-Deliverable Forward Creating an FX Option Create Collar FX Option Create FX Swap Create Reference

###### Elementary Search Help for Exposure Item ID by String

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Create Hedging Instruments > Elementary Search Help for Exposure Item ID by String | L5 | trm04 p.109 | loio `b81b7f6e9f51434c81e86de117fd47bb` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b81b7f6e9f51434c81e86de117fd47bb.html?locale=en-US)

Search exposure item ID of the exposure item hedged by the financial transaction.

If you create a hedging instrument for an exposure item by reference, you must assign the exposure item ID manually to the hedging instrument. You can assign the exposure item ID in the financial transaction data on FX Hegde Management tab.

In case, you do not know the exposure item ID, you can use the Elementary Search Help for Exposure Item ID by String. The search help selects all exposure items which match up with the entered selection criteria:

Description

You can enter a string here. The system will search for this string in the descriptions of the exposure items.

Company Code: From financial transaction data, automatically set by system (required entry)

Risk-free Currency: Currency of company code, automatically set by system (required entry)

Risk Currency: Currency of the financial transaction which does not match the local currency of the company code, automatically set by system (required entry)

Hedging Classification

Based on the entered hedging classification the system can identify the corresponding hedging area.

Key Date: Contract date of the financial transaction, set by system (required entry)

System only takes snapshots of this date into account.

When executing the search help, the system first uses company code, risk currency, hedging classification and key date to identify the relevant hedging area version. Key date and hedging area version are needed to identify the relevant snapshot. All these information together with the entered string in the Description field are used to find exposure item(s).

A result list is displayed which contains the following information for the found exposure items:

Exposure Item ID

Exposure Item Description

Available Open Amount of the Exposure Item

= (Net) Exposure Item Amount + Total Amount of Assigned Hedges

Choose the exposure item from the list.

##### Create Reference

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Create Reference | L4 | trm04 p.110 | loio `876f9775e98d47e88e0bbc9d2f6ef31d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/876f9775e98d47e88e0bbc9d2f6ef31d.html?locale=en-US)

**Use**

To designate a collar or a FX swap into a hedging relationship automatically, you have to reference the two FX options or the two FX forward transactions that you have created to hedge your net open exposure of the risk currency.

**Prerequisites**

You have created two Plain Vanilla FX Option or FX forward transactions.

The assigned hedging classification of the financial transactions is marked as Relevant for Hedge Accounting and in the hedging area master data on Hedge Accounting II tab a hedging profile and one of the following designation categories (indirect assigned through the assignment of the designation type) are assigned for a combination of company code, valuation area and hedging classification:

Two Instruments (FX option)

N Instruments (FX swap)

**Process**

- 1. Use the Create Reference function (transaction TBR6) to link your two plain vanilla FX options or FX forward transactions and in this way create a collar or a FX swap.
- 2. Enter the following parameters:

Reference Category:

OPT - Option reference - derivatives

SWP - Forex Swap

- Object 1 to Be Linked:

Company Code

Transaction

- Object 2 to Be Linked:


Company Code

Transaction

- 3. Save your entries.
- 4. As a result, the automated designation process is triggered and hedging relationship(s) created. In combination with the hedging classification, the reference category controls the designation process.


**Note:**

If an error occurs during automated designation process, you get a warning message but the reference is saved. You can use the Reprocess Financial Transactions for Automated Designation function to analyze the error and reprocess the transactions after the errors have been corrected.

**Related Information**

Automated Designation Process Reprocess Financial Transactions for Automated Designation

##### Reversing Hedging Instruments

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management and Accounting of Net Open Exposures (FX Risk) > Reversing Hedging Instruments | L4 | trm04 p.111 | loio `6f6bd623b49a4b28a20f2ab99897eeea` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6f6bd623b49a4b28a20f2ab99897eeea.html?locale=en-US)

**Context**

It might be necessary to reverse a financial transaction that has been created to fulfill an FX hedge request.

**Procedure**

- 1. Open either the Manage Financial Transactions app, or the Process Financial Transaction app on SAP Fiori launchpad.

- 2. Select the relevant transaction.
- 3. Choose Reverse.

If the financial transaction is designated into a hedging relationship, you cannot reverse the financial transaction. In this case, you first need to dedesignate the hedging relationship and then you can reverse the financial transaction.

- 4. Enter a reversal reason in the corresponding field.
- 5. Choose Save.
- 6. Post the reversal using the Process Business Transactions app.


**Results**

If a financial transaction is reversed, that is assigned to a completed FX hedge request, the system automatically adjusts the FX hedge request amount by the amount of the reversed financial transaction. However, the initial amount of the FX hedge request is still displayed in the new field Initial Hedge Request Amount in the FX hedge request.

Due to the reversal of the hedging instruments and the adjustment of the hedge request amount, the key figures in the Hedge Management Cockpit, such as the key figures Net Hedges, Hedge for Hedge Request, and Original Amount of Hedge Request, are also adjusted accordingly. This ensures that the Open Hedge Request Amount remains zero.

[figure TRM04-F016 - Due to the reversal of the hedging instruments and the adjustment of the hedge request amount, the key figures in the Hedge Management Cockpit, such as the key figures Net Hedges, Hedge for Hedge Request, and Original Amount of Hedge Request, are also adjusted accordingly. This ensures that the Open Hedge Request Amount remains zero.]

If all financial transactions of this FX hedge request have been reversed, the FX hedge request amount is adjusted by the amount of the reversed financial transaction and the status of the FX hedge request changes from Completed to Withdrawn. However, the initial amount of the FX hedge request is still displayed in the additional field Initial Hedge Request Amount in the FX hedge request.

**Note:**

For FX hedge request with instrument category FX Collar and FX Swap (available for hedging areas without hedge accounting and with risk-free currency = local currency), the status of the FX hedge request is also only changed to Withdrawn after all financial transactions have been reversed, and the hedge request amount is adjusted only after the reversal of both legs of an FX swap.

If there is also a related trade request with the status Completed, the status of the related trade request remains Completed and the amounts of the trade request are also not adjusted. However, you can see the status Reversed of the affected financial transactions on the Financial Transaction tab in the trade request.

#### Hedge Management of Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk | L3 | trm04 p.112 | loio `444a7358ff3ca107e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/444a7358ff3ca107e10000000a441470.html?locale=en-US)

The Hedge Management of Balance Sheet FX Risk process supports you in managing the risks arising from the revaluation of monetary balance sheet items in foreign currency.

Process Overview - Hedge Management of Balance Sheet FX Risk

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM04-F017]

Please note that image maps are not interactive in PDF outputs.

Balance sheet FX risks arise from the revaluation of monetary balance sheet items in foreign currency. The Hedge Management of Balance Sheet FX Risk process provides the following features:

Analyze the balance sheet FX risk your company is exposed to using the Review Balance Sheet FX Risk app, which enables you to gain an overview of the balance sheet FX exposures and of the hedging instruments you used to mitigate that risk.

Take snapshots of your balance sheet exposures and their hedges. The snapshot data is stored in database tables.

You can use the Balance Sheet FX Risk Overview - Based on Snapshots app to get an overview of the snapshot data.

Using the Process Snapshots - Balance Sheet FX Risk app, you can display and check the snapshot generated. If an exposure is missing in the system but needs to be considered, you can create a snapshot item manually. When the

snapshot data is correct, you can release the snapshot.

Generate balance sheet exposure hedge requests based on the released snapshot data

Using the Process Hedge Requests - Balance Sheet FX Risk app, you can edit and release the balance sheet exposure hedge requests created. For released B/S hedge requests, the system creates a trade request automatically.

Your trader uses the Process Trade Requests app to get information about the required hedging instruments.

**Note:**

If you’re using the SAP Trading Platform Integration app, these trade requests are transferred to the trading platform, and the closed trades (financial transactions) are imported automatically into your back-end system.

You can aggregate the balance sheet exposures of your subsidiaries on treasury center level and perform the hedging of the net exposure centrally.

When you take a snapshot, the exposures of all subsidiaries and the exposures of the treasury center are taken into account for each treasury center.

The subsidiary company code is stored in the new On-Behalf of Company Code field.

The exposures are aggregated per risk currency. The exposure amounts are not converted.

[figure TRM04-F018 - The exposures are aggregated per risk currency. The exposure amounts are not converted.]

**Prerequisites**

You use the Define Settings - Balance Sheet FX Risk app to identify the data in your system that represents the balance sheet exposure and the financial transactions used as hedges by defining key figure groups and key figures. The key figures determine which data is selected and structure how the data is displayed in the B/S FX risk apps at the same time. You also define hedge request parameter groups and hedge request parameters here for the generation of B/S hedge request. In addition, you can assign subsidiary company codes to the treasury center company codes so that you can aggregate the balance sheet exposures of your subsidiaries on treasury center level and perform the hedging of the net exposure centrally without any additional internal transactions.

Customizing

A snapshot stores the balance of balance sheet exposures aggregated to several possible dimensions, for example: key figure, financial account number, financial chart of accounts, planning level, portfolio, product type, and so on.

If you need more flexibility for the aggregation level for the snapshot of the balance sheet exposure, you can use the following Customizing activities to select two additional dimensions. The related hedge requests then also consider the new aggregation

level, so that the hedging can be done on a level that reflects its transaction structure with the corresponding account assignments.

Define Keyfigure Dimension Extensions

In this Customizing activity you can choose new key figure dimensions of each data source that are considered when creating a new exposure snapshot. Enter the dimension field name of the data source that you would like to use. You must also define to which field it should be mapped in the balance sheet hedge request. The new defined key figure dimensions for the exposures are also used as dimension for the aggregation of the balance sheet hedge requests.

**Note:**

Caution: Before you change or remove entries in this Customizing activity, ensure that there are no saved key figure selections for these fields in transaction FXM_KF_DF. First delete these saved selections for these fields.

Example

For example, you want to add the profit center as a new dimension for all data sources that should be also mapped to the hedge request:

|B/S Hedge Request Field Name|TRM Dimension Extension Field Name|Financial Dimension Extension Field Name|One Exposure Dim. Field Name|
|---|---|---|---|
|PROFIT_CENTER|PRCTR|PRCTR|PROFITCENTER|


The profit center is selected from all data sources and is a new dimension for the aggregation in the balance sheet hedge request.

Prerequisites

In case you define a new dimension field for one or multiple data sources that should be mapped to a different field in the snapshot, you must implement a BAdI to define the mapping of the data.

Please ensure that you implemented the technical implementation steps as described in SAP Note 3502053 to extend the snapshot table and view:

Extension of the Snapshot Item Table with the Customer-Specific Dimension

- 1. During creation of balance sheet exposure snapshot the exposure on level of the customer-specific dimensions from all relevant data sources must be stored in the snapshot item table.
- 2. Therefore table FXM_SNAP_ITEM must be extended with the hedge request target field. This should be done by adding a table append to one of the include structures.


**Sample Code:**

@EndUserText.label : 'Customer-Specific Dimension Extension' @AbapCatalog.enhancement.category : #NOT_EXTENSIBLE extend type fxms_snap_fi_dimension with zfxm_snap_item_extension {

Field1 : data_type_1; Field2 : data_type_2;

}

Extension of Core Data Service View

You have to extend the data definition of core data service P_BSESNAPSHOT with an extension view where you add the same fields as in the snapshot item table.

This enhancement is required that the customer-specific dimensions are selected when creating a hedge request.

**Sample Code:**

extend view P_BSESNAPSHOT with zp_bsesnapshot_ext {

item.xxx item.xxx

}

Extension of Core Data Service Stack for App ʻProcess Snapshot’

With the following extensions of three core data service views you activate the customer-specific dimensions to be visible in the Process Snapshots app.

Extend view C_BalShtExpsrSnpshtItmTP

Extend view I_BalShtExpsrSnpshtItm

Extend view I_BalShtExpsrSnpshtItmTP

BAdI: Modify Balance Sheet Exposure Snapshot

This Business Add-In (BAdI) is used in the Treasury and Risk Management (FIN-FSCM-TRM) component. You can use this BAdI to modify the creation of the balance sheet snapshot.

You can use the original created snapshot item data to manipulate the target snapshot item.

Example

You could use this BAdI in case you added a customer append field to an exposure data source table and defined it as a new dimension for that data source and want to use it in the hedge request. Therefore, you can map the customer append field to an existing snapshot and hedge request attribute.

[figure TRM04-F019 - You could use this BAdI in case you added a customer append field to an exposure data source table and defined it as a new dimension for that data source and want to use it in the hedge request. Therefore, you can map the customer append field to an existing snapshot and hedge request attribute.]

**Process**

- 1. Review your balance sheet FX risk using the Review Balance Sheet FX Risk app. In detail, you can do the following:


Quantify balance sheet FX exposure positions for all entities over all potential currencies. Obtain detailed insights into the origin/structure of the exposure positions for each currency within the company codes.

Quantify balance sheet FX risk hedges. Obtain detailed insights into the structure of the hedging transactions for each currency within the company codes.

Gain an overview of the amount of absolute FX net exposures, FX exposures, and hedging transactions in your company codes. The aggregated net exposure positions are available in the transaction currency and are converted into the reporting currency.

Further drilldowns to single-line item level are possible in order to evaluate exposure and hedge positions in detail.

**Note:**

The following data sources are available for defining your exposure and hedge key figures:

FI Balances:

Reads total values from G/L accounts (One Document) as of the report key date

FI Open Items:

Reads open items from G/L accounts (One Document)

Financial Transactions:

Reads nominals of financial transactions in the Transaction Manager of Treasury and Risk Management

One Exposure

Reads operational data from One Exposure, identified by their attributes, such as certainty level, planning level, planning group, liquidity item, and transaction date.

Example: You can read memo records.

**Note:**

In addition, the Balance Sheet FX Risk and Balance Sheet FX Risk - In Transaction Currency apps are available for balance sheet FX risk reporting.

- 2. Take a snapshot of your balance sheet exposures and their hedges using the Take Snapshot - Balance Sheet FX Risk app.
- 3. Using the Process Snapshots - Balance Sheet FX Risk app, you can create additional snapshot items manually for snapshots with the status Created. If all data of the snapshot is correct, you can release the snapshot. For released snapshots, the app allows you to jump to the related hedge request generated based on the snapshot. In addition, the Undo Release function is available.

- 4. You can use the Balance Sheet FX Risk Overview - Based on Snapshots app to get an overview of the snapshot data.
- 5. Based on the released snapshots for balance sheet FX risk, you can generate balance sheet exposure hedge requests (B/S hedge requests) to trigger the conclusion of financial transactions to hedge the net open exposure (balance sheet FX risk).

Use the Generate Balance Sheet Exposure Hedge Requests app.

- 6. Using the Process Hedge Requests - Balance Sheet FX Risk app, you can create, edit, and release balance sheet exposure hedge requests. For released B/S hedge requests, the system creates a trade request automatically.
- 7. Use the Process Trade Requests apps to process your trade requests.

If you implemented the Integration with External Trading Platforms integration scenario, the trade requests are sent automatically to the SAP Trading Platform Integration application. The app supports the end-to-end business process with which trade requests created in your SAP S/4HANA system are sent to an external trading platform and with which, trades are then concluded on the external trading platform and automatically transferred through the SAP Trading Platform Integration application to your Treasury and Risk Management system.

If you do not use the SAP Trading Platform Integration application, the trader can use the app to find the trade requests created from B/S hedge request and cash trade request. After the required hedging transactions have been concluded, you can set the status of the trade requests manually to Completed.

- 8. When the trade requests are fulfilled and the hedges (financial transactions) are entered in the back-end system, you can review your balance sheet FX risk again.


Related Information

Integration with External Trading Platforms

##### Define Settings - Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Define Settings - Balance Sheet FX Risk | L4 | trm04 p.117 | loio `9251e9551a49e263e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9251e9551a49e263e10000000a44538d.html?locale=en-US)

App ID: FXM_KF_DEF

With this app, you define basic settings for the Hedge Management of Balance Sheet FX Risk process. You define here the key figures and key figure groups for the calculation of exposures, hedges, and net exposures and also parameters and parameter groups for the creation of balance sheet exposure hedge requests.

The key figures and key figure groups that you define here are required for the calculation of exposures, hedges, and net exposures for each transaction currency or for the calculation of the absolute exposures, hedges, and net exposures for the company codes in the Review Balance Sheet FX Risk, Balance Sheet FX Risk, Balance Sheet FX Risk - In Transaction Currency, and Balance Sheet FX Risk Overview - Based on Snapshots apps.

You use the key figures to specify which balances and open items in foreign currencies from G/L accounts in financial accounting are relevant for the balance sheet FX exposure or which of the financial transactions of the Transaction Manager were made to hedge FX risk.

The apps calculate the balance sheet FX risks for the key figures defined here for each transaction currency and creates totals on the key figure group level, as well as for totals of all key figures for exposures per currency, and for totals of all key figures for hedges per currency.

The net exposure for each currency is derived from the difference between the total of exposures per currency and the total of the hedges per currency. The amounts are calculated in the transaction currency and are translated into the display currency. The current exchange rates are needed to do this.

Further, these key figures are taken as the basis for calculating in the display currency the absolute exposure, the absolute hedges, and the absolute net exposure for the entire company code.

The B/S hedge request parameters and B/S hedge request parameter groups are relevant for the creation of balance sheet exposure hedge request in the Process Hedge Requests - Balance Sheet FX Risk app

**Maintain Key Figure Groups**

You can use key figure groups to group together your key figures. In a key figure group, you specify whether the assigned key figures belong to exposures or to hedges.

In the Review Balance Sheet FX Risk app, the exposures or hedges of a key figure group are totaled at the level of the group in the detailed view for the company code.

- 1. Open the Define Key Figures - Balance Sheet FX Risk app on SAP Fiori launchpad.
- 2. Switch to the change mode.
- 3. In the Maintain Key Figure Groups screen, choose New Entries.
- 4. Assign a name (not exceeding 20 characters) and a unique description for the key figure group. Further, specify whether the key figure group is used for exposures or hedges.


**Note:**

Key figure groups are used to structure how key figures are displayed in the app Review Balance Sheet FX Risk. In this app, the key figure groups of the exposures are displayed followed by the key figure groups for the hedges.

The key figure group is displayed in the app with its description, and not with the maximum 20 character name.

- 5. Save your entries.


**Maintain Key Figures**

- 1. Switch to the Maintain Key Figures screen.
- 2. Choose New Entries.
- 3. Choose a name (not exceeding 20 characters) and a description for the key figure that reflects its business purpose.
- 4. Assign the key figure group.
- 5. Specify the data source from which the key figure is to be calculated (FI Balances, FI Open Items, or Financial Transactions).

FI Balances

Total values in foreign currency on FI accounts for the key date

FI Open Items

Open items in foreign currency on FI accounts

Financial Transactions

Nominals of financial transactions in Treasury and Risk Management that were made to hedge FX exposures

One Exposure

Reads operational data from One Exposure.

- 6. Save your entries and return to the previous screen.
- 7. Select the key figure and choose Maintain Selection. Here, you specify how the key figure is calculated.


For key figures using FI Balances as their data source, the following fields are available:

G/L Account

Planning Level

Chart of Accounts

For key figures using FI Open Items as their data source, the following fields are available:

G/L Account

Planning Level

Chart of Accounts

Journal Entry Type

Account Type

Open Items at Key Date

Here, you create rules dictating how the system selects dates dynamically on the basis of the key date from the app Review Balance Sheet FX Risk.

- KD-1 Key Date - 1 Day

- KD-2 Key Date - 2 Days


- KD-3 Key Date - 3 Days

- KD-4 Key Date - 4 Days

- KD-5 Key Date - 5 Days


KD Report Key Date

KD+ Key Date + 1 Day

- KD+2 Key Date + 2 Days

- KD+3 Key Date + 3 Days

- KD+4 Key Date + 4 Days

- KD+5 Key Date + 5 Days


BOM-1 Start of Preceding Month

BOM Beginning of Month

EOM End of Month

EOM+1 End of Following Month

Example:

You want to include in a key figure open items that are open three days after the key date. Enter the following: ST+3(Key Date + 3 Days).

If you then run the report using the key date June 17, the system calculates the key figure value by considering all open items up to June 20.

Date Type

The date type decides which date of an Universal Journal Entry Line Item is relevant for the selection as exposure in balance sheet FX risk. You can choose between Clearing Date (Default) and Net Due Date.

Posting Date

For key figures using Financial Transactions as their data source, the following fields are available:

Product Type

Transaction Type

Activity Category

Portfolio

Assignment

Business Partner

Contract Date

Term End

Example:

You want to include in a key figure all financial transactions with terms ending in the reporting month. For this, choose a term end between BOM(beginning of month) and EOM(end of month).

If you then run the report using the key date June 17, the system calculates the key figure value by considering all financial transactions with terms ending between June 1 and June 30.

Fixing Date

**Note:**

Use this field to filter NDFs by fixing date.

For key figures using One Exposure as their data source, the following fields are available:

Certainty Level

Planning Level

Planning Group

Liquidity Item

Transaction Date

Here, you create rules dictating how the system selects dates dynamically on the basis of the key date from the apps.

- KD-1 Key Date - 1 Day

- KD-2 Key Date - 2 Days

- KD-3 Key Date - 3 Days

- KD-4 Key Date - 4 Days

- KD-5 Key Date - 5 Days


KD Report Key Date

KD+ Key Date + 1 Day

- KD+2 Key Date + 2 Days

- KD+3 Key Date + 3 Days

- KD+4 Key Date + 4 Days

- KD+5 Key Date + 5 Days


BOM-1 Start of Preceding Month

BOM Month Start

EOM Month End

EOM+1 Start of Following Month

Save your entries.

**Maintain Hedge Request Parameter Groups**

- 1. Switch the Maintain Hedge Request Parameter Groups screen.
- 2. Choose New Entries.
- 3. Enter the name and the description for the new B/S hedge request parameter group.


- 4. Set the default indicator for the B/S hedge request parameter group if needed.

In this case, the B/S hedge request parameter group is automatically assigned, if you create balance sheet exposure hedge requests in the Process Hedge Requests - Balance Sheet FX Risk app.

You can choose another parameter group, if needed.

- 5. Save your entries.


**Maintain Hedge Request Parameters**

- 1. Switch the Maintain Hedge Request Parameters screen.
- 2. Choose New Entries.
- 3. Enter the name and the description for the new B/S hedge request parameter.
- 4. Choose the relevant B/S hedge request parameter group.
- 5. Save the parameter.
- 6. Select the parameter and choose Maintain Selection. Here, you specify the following:


Filter for Snapshots

Here, you use the Company Code, Currency, Period Start and Period End fields to specify the snapshots for which the parameters are relevant.

**Note:**

There should be no overlap of the filters for snapshots between the parameters of a parameter group.

Value Date

Specify the value date for the requested hedging instrument. You can either derive the value date from the Time Period or select a Fixed Date. The following fields are available:

Time Period

Value Date Definition

You can choose between the following values:

First Day of Period

Last Day of Period

Which day is ultimately derived as the value date of the balance sheet exposure hedge request is also influenced by the following fields:

Additional Days

Enter a number of days in this field if you want to change the value date that is set by default in the Value Date Definition field.

Working Days Shift

Select this checkbox to ensure that the system checks the value date for holidays and creates balance sheet hedge requests only with a value date that is a working day. This check is based on the factory calendar of the risk currency.

If the value date isn't a working day, it isn’t valid, and a valid date needs to be determined.

Working Day

Select one of the following options:

Next Working Day

Previous Working Day

Working Days Shift Calendar

You can select the factory calendar that should be relevant for the working day shift.

**Note:**

If you do not choose a factory calendar here, the factory calendar of the risk currency is relevant for the working day shift.

Fixed Date

Value Date Selection

If you choose to derive the value date of the balance sheet exposure hedge request from the system date, you can use the Value Date Selection field to choose between the following dates:

Current Month End

Current Quarter End

Fixed Date

In this case, you enter the value date manually.

Main Parameter

The main parameters are relevant for the creation of the hedge requests:

Instrument Category

You can specify which kind of hedging instrument the trader should conclude to hedge the net open exposure.

Rounding

Define the unit with which the calculated hedge request amount is rounded.

Example

You enter in this field the value 1.000

The calculated hedge request amount is 22.365 USD.

Due to this rounding rule, the hedge request amount is rounded to 22.000 USD.

Minimum Amount

Enter the minimum amount for balance sheet exposure hedge requests.

Only if the hedge request amount determined is equal to or higher than the minimum amount is a hedge request created.

Currency

Enter the currency of the minimum amount.

Exchange Rate Type

If the transaction currency is different from the currency of the minimum amount, the values are translated into the currency of the minimum amount. The currency translation uses the current FX rate for the relevant currency pair of the exchange rate type specified.

Target Status

You can choose the target status for the hedge request.

If you choose the Created status, you can process (check and release or delete) the hedge requests created.

If you choose the Released status, the system automatically creates a trade request from the hedge request.

You can use the Process Hedge Requests - Balance Sheet FX Risk app to display and process hedge requests.

Description

Enter a description for the hedge request.

Additional Parameter

The value that you enter in this field for the balance sheet exposure hedge request is later copied to the corresponding field for the financial transaction that has been concluded to fulfill the balance sheet exposure hedge request. In the financial transaction, you find the additional parameter fields on the Administr. tab. Only the External Reference field is in the Contract Conclusion area on the Structure tab.

**Note:**

Entering additional parameters is optional.

Portfolio

External Reference

Assignment

Internal Reference

Characteristics

Profit Center

Cost Center

WBS Element

Country/Region Key

Segment

On Behalf of Company Code

- 7. Save your entries.


**Assign Subsidiaries to Treasury Center**

If you want to aggregate the balance sheet exposures of your subsidiaries on treasury center level and perform the hedging of the net exposure centrally, you assign the subsidiary company codes to the treasury center company code for each relevant currency.

[figure TRM04-F020]

When you take a snapshot for the company code of the treasury center, the exposure of the treasury center and also the exposures of all subsidiaries are taken into account.

In the snapshot table the subsidiary company code is stored in the new On-Behalf of Company Code field for the exposures from subsidiaries.

The exposures are aggregated per risk currency. The exposure amounts are not converted.

[figure TRM04-F021 - The exposures are aggregated per risk currency. The exposure amounts are not converted.]

**Examples**

Key Figures and Key Figure Groups

The key figures Liabilities to Third-Parties and Receivables from Third-Parties both belong to the key figure group ThirdParty Exposures. For the key figure group Third-Party Exposures, set the Exposure/Hedge indicator to Exposure.

For the key figure group Hedges for Third-Party Exposures, set the Exposure/Hedge indicator to Hedge.

Parameter Groups

Maintain the parameters for the creation of balance sheet exposure hedge requests based on different balance sheet hedge policies by defining corresponding parameter groups:

- Parameter Group 1: EMEA

- Parameter Group 2: US


**Supported Device Types**

Desktop

Tablet

**Related Information**

Review Balance Sheet FX Risk Balance Sheet FX Risk Balance Sheet FX Risk - In Transaction Currency Balance Sheet FX Risk Overview - Based on Snapshots

##### Review Balance Sheet FX Risk (2 of 2)

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Review Balance Sheet FX Risk | L4 | trm01 p.134 | loio `8daae755840eb61ae10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8daae755840eb61ae10000000a44538d.html?locale=en-US)

**Use**

You can use this app for two purposes:

Gain an overview of the amount of absolute balance sheet net open exposures, absolute balance sheet exposures, and their hedges in your company codes.

Obtain detailed insights into origin/structure of the balance sheet exposures and hedges for each currency within those company codes.

The sources for the calculated key figures are the balances and open items in foreign currency on your G/L accounts in Financial Accounting (One Document) and the operational data from One Exposure (FX exposures) as well as financial transactions (hedges) managed in the Treasury and Risk Management.

**Prerequisite**

You need to define the relevant key figures to calculate, on the one hand, the amount of the exposures that the currency risk represents and, on the other hand, the related hedging instruments that have already been completed.

You find the Define Key Figures function as an app on the launchpad on the Hedge Management tab and in the area menu of Treasury and Risk Management under Hedge Management and Accounting Hedge Management Master Data Balance Sheet FX Risk Define Key Figure .

For more information, see also Define Settings - Balance Sheet FX Risk

**Key Functions**

You can see at a glance the amount of the absolute balance sheet net open exposures, absolute balance sheet exposures, and absolute hedges at company code level on the key date.

You can branch to a company code and obtain a detailed view of the origin/structure of the balance sheet exposures and hedges for the various transaction currencies of a company code (amounts in transaction currency) as well as the resulting net exposures in both transaction currency and display currency. When calculating displayed values, the absolute amounts are not used but the plus/minus sign is taken into account.

For the specific key figures a further drilldown to the single line item level is possible in order to evaluate exposure and hedge positions in detail:

For key figures of the data source FI Balances, you can drill down to the display of line items in general ledger.

**Note:**

Using the drilldown function, system opens the Display Line Items in General Ledger app.

Balances carried forward are not displayed in this app because they are technical items in the system and not typical line items.

If you are navigating from Review Balance Sheet FX Risk app to the Display Line Items in General Ledger app the presumed purpose is to show the corresponding line items which are decisive for this navigation scenario and not to compare the balances.

For key figures of the data source FI Open Items, you can drill down to the display of open line items in general ledger.

**Note:**

Using the drilldown function, system opens the Display Line Items in General Ledger app.

For key figures of the data sourceOne Exposure, you can drill down to the contributing cash flow items in Cash Management.

For key figures of the data source Transaction Management, you can drill down to a list of the contributing financial transactions in Treasury and Risk Management.

You can export the detailed data to a worksheet.

You get a file that contains the calculated balance sheet FX risk hedges and exposures at the level of the defined key figures in transaction currency and display currency for each company code.

**Note:**

The totals at the key figure group level and the net exposures resulting from the key figures, or the absolute net FX exposures, exposures and hedges at company code level are not exported.

Calculation of Measures for Balance Sheet FX Risks

With the Define Settings - Balance Sheet FX Risk app, you identify the data in your system that represents the balance sheet exposure and the financial transactions that are used as hedges.

In the following, you can see how balance sheet FX risk measures are calculated based on the balance sheet exposures and their hedges.

Balance sheet net open exposure (absolute) for the company code in display currency

Balance sheet exposure (absolute) for the company code in display currency

Hedges (absolute) for the company code in display currency

Balance sheet exposures in transaction currency at the level of the key figure groups and key figures for exposures for each company code

The balance sheet exposures are totaled taking their plus/minus sign into account.

Hedges in transaction currency at the level of the key figure groups and key figures for hedges for each company code

The hedges are totaled taking their plus/minus sign into account.

Balance sheet net open exposure in transaction currency for the company code

The balance sheet net open exposure for each currency is derived from the difference between the total of exposures per currency and the total of the hedges per currency.

Balance sheet net open exposure in display currency for the company code

Formulas: Calculation of Balance Sheet FX Risk Measures

[figure TRM01-F033 - Formulas: Calculation of Balance Sheet FX Risk Measures]

where

NE(abs.) = Balance sheet net open exposures (absolute) = Total of absolute amounts of balance sheet net open exposures for each transaction currency in the display currency

E(abs.) = Balance sheet exposures (absolute) = Total of absolute amounts of balance sheet exposures for each transaction currency in the display currency

H(abs.) = Hedges (absolute) = Total of absolute amounts of hedges for each transaction currency in the display currency

TC = Transaction currency

DC = Display currency

r = Exchange rate (transaction currency in display currency)

TC/DC

More Information

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

###### App Extensibility: Review Balance Sheet FX Risk (2 of 2)

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Review Balance Sheet FX Risk > App Extensibility: Review Balance Sheet FX Risk | L5 | trm01 p.137 | loio `485dff5571b5632de10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/485dff5571b5632de10000000a441470.html?locale=en-US)

You can not extend the app Review Balance Sheet FX Risk.

##### Balance Sheet FX Risk Overview - Based on Snapshots

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Balance Sheet FX Risk Overview - Based on Snapshots | L4 | trm04 p.128 | loio `3f3b923a3eaf47ca82ed9b36fb3b4bed` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f3b923a3eaf47ca82ed9b36fb3b4bed.html?locale=en-US)

**Use**

This app provides an overview of hedge management for balance sheet FX risk based on snapshot data. It displays the total net open amount in the different transaction currencies and the contributing key figure types Net Exposure of Snapshot, Hedged Amount, and Open B/S Hedge Request of Snapshot.

**Filters**

The snapshots are selected and the values are calculated according to your settings for the filters.

Standard filters:

Display Currency (required entry)

Enter the display currency.

Exchange Rate Type (required entry)

Enter the exchange rate type.

The exchange rate type distinguishes between different kinds of rate. If you enter an FX rate in the market data table, you must assign the exchange rate type.

If the currency is different from the display currency, the position values are translated into the display currency. The currency translation uses the current FX rate of the currency pair PC/DC of the exchange rate type specified.

Snapshot ID

You can select one or more snapshots. Since this app provides you with the total amount of all net open amounts for the selected snapshots, make sure that the entered data is consistent.

Company Code

You can restrict the selection of snapshot data to one or more company codes.

Currency

You can select one or more transaction currencies.

Period Start

Period End

Key Date

You can enter a specific key date.

Using the Adapt Filters button, you can do the following:

Use more criteria for snapshot data selection and save a specific combination of filters

Change the appearance of the filter by deselecting the Show on Filter Bar indicator. In addition, you can change the filter values.

**Note:**

You can save your filter settings by choosing Select View Save As . Enter a name for the new view. You can mark the view as the default view and as Public Visible. If you don’t mark the view, it’s saved as your private view.

After you’ve finished making your filter settings, choose the Go pushbutton.

**Features**

The app provides a chart view and a table view. You can switch between the different view types using the following buttons:

  Chart andTableView

  ChartView

  TableView

**Note:**

For the chart view, you can switch between different chart types, such as Bar Chart and Column Chart.

The table view allows you to drill-down to the single snapshot contributing to the position value displayed.

The Chart View presents the total net open amount for each currency in display currency. The net open amount of a snapshot is calculated in the following way:

Net Open Amount = Net Exposure of snapshot + Open B/S Hedge Requests of the snapshot + Hedged Amount of the snapshot

The net open amount is therefore the unhedged amount of the net exposure, whereby the open amounts of the hedge requests are also considered as hedged amounts.

The chart view shows the total of all net open amounts of the selected snapshots for all currencies.

**Note:**

The chart view and the table view are interactive. By double-clicking a specific net open amount in the chart view, the table view is opened showing the details for the selected currency.

Table View

The table view presents the selected snapshot data more detailed in a table. The table presents the data using the following columns:

Snapshot ID

Company Code

Currency

Key Figure Type

Net Exposure

The amount of net exposure of the balance sheet FX risk snapshot.

Open B/S Hedge Request

The amount of the B/S hedge requests that are not fulfilled so far.

Hedged Amount

The amount of B/S hedge requests that are fulfilled.

Net Open Amount

Net Open Amount = Net Exposure of snapshot + Open B/S Hedge Requests of the snapshot + Hedged Amount of the snapshot

The net open amount is therefore the unhedged amount of the net exposure, whereby the open amounts of the hedge requests are also considered as hedged amounts.

When you click on the snapshot ID, you can jump to the following apps:

Process Snapshots – Balance Sheet FX Risk

Process Balance Sheet Exposure Hedge Requests

When you select one of the apps, the system jumps to the chosen app and opens it for the snapshot ID chosen.

**Prerequisites**

You must define the relevant key figures for exposures and hedges using the Define Settings - Balance Sheet FX Risk app.

You need to have taken snapshots of balance sheet FX risk using the Take Snapshot - Balance Sheet FX Risk app.

**Integration**

Process Overview - Hedge Management of Balance Sheet FX Risk

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM04-F023]

Please note that image maps are not interactive in PDF outputs.

**Supported Device Types**

Desktop

Tablet

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Balance Sheet FX Risk | L4 | trm04 p.131 | loio `3c44a1d78aed4200b6c544d126020c7a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c44a1d78aed4200b6c544d126020c7a.html?locale=en-US)

With this app, you can analyze your balance sheet FX risk. The app reads open items and balances in foreign currency of your G/L accounts in Financial Accounting (FX exposure), financial transaction data from the Transaction Manager (hedging instruments), and operational data from One Exposure. The app enables you to analyze details of balance sheet FX risk by adding attributes (for example, related to financial transactions, bank accounts and general ledger postings) to the content area as rows or columns.

The Balance Sheet FX Risk tile displays balance sheet the FX risk measures absolute exposures, absolute hedges, and absolute net exposures as well as hedge amounts and exposure amounts on the level of the company codes in display currency. It allows you to analyze the values by adding attributes as rows to get these values on lower levels also.

**Prerequisite**

You need to define the relevant key figures to calculate, on the one hand, the amount of the exposures that the currency risk represents and, on the other hand, the related hedging instruments that have already been completed.

You find the Define Key Figures function as an app on the launchpad on the Hedge Management tab and in the area menu of Treasury and Risk Management under Hedge Management and Accounting Hedge Management Master Data Balance Sheet FX Risk Define Key Figure .

For more information, see also Define Settings - Balance Sheet FX Risk

**Authorization**

Since this app reads data from Treasury and Risk Management and in addition from General Ledger Accounting, you need the roles Treasury Specialist - Middle Office and General Ledger Accountant to run this app.

How-to Video: Working with Reports (Multidimensional Data Grid Apps) (English Only)

[figure TRM04-F024]

Open this video in a new window

**Note:**

Captions are available for multiple languages. Use the CC (Closed Captions) button in the video player to see which languages are supported.

You can also use the Search within video field to search for specific text in the English or German captions.

**Key Features**

The app displays the amounts in display currency.

When you call the app in the delivered version, enter the display currency.

You can also choose the company codes. If you do not enter company codes, the app displays the data for all company codes.

You can enter the exchange rate type for the currency translation from transaction currency to display currency.

You can choose the transaction currencies you are interested in. If you do not enter transaction currencies, the app displays the available data for all transaction currencies.

On the Data Analysis tab, you see the company codes as rows and the following measures (key figures) for balance sheet FX risk in the columns:

Absolute exposures in display currency

The total of absolute amounts of exposures for each transaction currency translated into the reporting currency.

Absolute hedges in display currency

The total of absolute amounts of hedges for each transaction currency translated into the reporting currency.

Absolute net exposures in display currency

The total of absolute amounts of net exposures for each transaction currency translated into the reporting currency.

Exposure amount in display currency

The total of the amounts of exposures for each transaction currency translated into the reporting currency.

Hedge amount in display currency

The total of amounts of the hedges for each transaction currency translated into the reporting currency.

In the last row, you see the overall result for the selected company codes.

Calculation of Key Figures for Balance Sheet FX Risks

The key figures shown are calculated on the basis of the settings that you make in the Define Key Figures app.

The app calculates the current values for the defined key figures per currency and creates totals at the key figure group level, totals of all key figures for exposures per currency, as well as totals of all key figures for hedges per currency. The net exposure for each currency is derived from the difference between the total of exposures per currency and the total of the hedges per currency.

Further, these key figures are taken as the basis for calculating the absolute exposure, the absolute hedges, and the absolute net exposure for the entire company code. For this, the absolute amounts of the net exposures, exposures, and hedges of the transaction currencies are translated into the reporting currency and totaled.

[figure TRM04-F025 - Formulas Used to Calculate Key Figures for the Company Code]

Formulas Used to Calculate Key Figures for the Company Code

where

NE(abs.) = Net exposures (absolute) = total of absolute amounts of net exposures for each transaction currency, translated into the reporting currency

E(abs.) = Exposures (absolute) = total of absolute amounts of exposures for each transaction currency, translated into the reporting currency

H(abs.) = Hedges (absolute) = total of absolute amounts of hedges for each transaction currency, translated into the reporting currency

TC = transaction currency

RC = reporting currency

r = exchange rate of transaction currency to reporting currency

TC/RC

**Note:**

The current exchange rates are needed for the calculations. Ensure that the exchange rates are kept up to date.

You can analyze details for the balance sheet FX risk by adding, for example, the attribute Key Figure ID. In this case, the key figure groups and key figures (which you defined in the Define Key Figures - Balance Sheet FX Risk app) are displayed as rows and the measures are also calculated and displayed on these levels.

You can also add other attributes related to financial transaction, bank accounts, and general ledger postings to the content area, as rows.

On the Graphical Display tab, you can see the values as graphic.

On the Query Information tab, you can see, for example, the values of the variables and filters selected.

Navigate to apps related to general ledger accounts using the Jump to function.

Export results to Microsoft Excel.

**Note:**

You can completely change the structure and the measures firstly by adding rows and columns, and secondly by adding other measures by changing the filter values for the Key Figures field.

**Technical Information**

The Balance Sheet FX Risk app has the SAP Fiori ID W0123.

**Supported Device Types**

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

Related Information

Define Settings - Balance Sheet FX Risk Balance Sheet FX Risk - In Transaction Currency Review Balance Sheet FX Risk

##### Balance Sheet FX Risk - In Transaction Currency

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Balance Sheet FX Risk - In Transaction Currency | L4 | trm04 p.135 | loio `ceeff990a3514983a887eb5d2c1bb8d8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ceeff990a3514983a887eb5d2c1bb8d8.html?locale=en-US)

With this app, you can analyze your balance sheet FX risk. The app reads open items and balances in foreign currency of your G/L accounts in Financial Accounting (currency exposure), financial transaction data from the Transaction Manager (hedging instruments), and operational data from One Exposure. The app allows you to analyze details of balance sheet FX risk by adding attributes related to financial transaction, bank accounts, and general ledger postings to the content area as rows or columns.

The Balance Sheet FX Risk - In Transaction Currency tile directly displays the measures for balance sheet FX risk with the amounts in transaction currency for all selected currencies and company codes and obtains a detailed view of the origin/structure of the exposures and hedges for the various transaction currencies (amounts in transaction currency).

How-To Video: Working with Reports (Multidimensional Data Grid Apps) (English Only)

[figure TRM04-F026]

Open this video in a new window

**Note:**

Captions are available for multiple languages. Use the CC (Closed Captions) button in the video player to see which languages are supported.

You can also use the Search within video field to search for specific text in the English or German captions.

**Prerequisite**

You need to define the relevant key figures to calculate, on the one hand, the amount of the exposures that the currency risk represents and, on the other hand, the related hedging instruments that have already been completed.

You find the Define Key Figures function as an app on the launchpad on the Hedge Management tab and in the area menu of Treasury and Risk Management under Hedge Management and Accounting Hedge Management Master Data Balance

Sheet FX Risk Define Key Figure .

For more information, see also Define Settings - Balance Sheet FX Risk

**Key Features**

Display amounts in transaction currency

When you call the app in the delivered version, you can choose the company codes. If you do not enter company codes, the app displays the data for all company codes. In addition, you can choose the transaction currencies you are interested in. If you do not enter transaction currencies, the app displays the available data for all transaction currencies.

On the Data Analysis tab, you see the key figure groups and key figures (which you defined in the Define Key Figures Balance Sheet FX Risk app) as rows and the following measures (key figures) for balance sheet FX risk as columns:

Amounts in transaction currencies

You can analyze the data by adding other attributes related to financial transaction, bank accounts, and general ledger postings to the content area as rows.

You can choose the Graphical Display tab to see the values as a graphic.

On the Query Information tab, you can see, for example, the values of the selected variables and filters.

You can choose the Graphical Display tab to see the values as graphic.

On the Query Information tab, you can see, for example, the values of the selected variables and filters.

Navigate to apps related to general ledger accounts using the Jump to function.

Export results to Microsoft Excel.

**Note:**

You can change the structure and the measures completely by adding rows and columns and by changing the filter values for the Key Figures field.

**Technical Information**

The Balance Sheet FX Risk - In Transaction Currency app has the SAP Fiori ID W0124.

**Supported Device Types**

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**Related Information**

Balance Sheet FX Risk

Review Balance Sheet FX Risk Define Settings - Balance Sheet FX Risk

##### Snapshot - Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Snapshot - Balance Sheet FX Risk | L4 | trm04 p.137 | loio `d86309e74cb64dc6b8943bb3dfce868a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d86309e74cb64dc6b8943bb3dfce868a.html?locale=en-US)

Stores the balance of balance sheet exposures and their hedges on a specific key date in database tables

You take a snapshot using the job template Take Snapshot - Balance Sheet FX Risk in the Schedule Treasury Middle Office Jobs app.

The snapshot is created as follows:

Selects balance sheet exposures (B/S exposures) and their hedges according to the settings in the job template. If you have defined periods, the exposures and hedges are assigned to their relevant period by due date/value date.

Saves the selected data under a specific snapshot ID in the database table as follows:

The selected B/S exposures and hedges are aggregated to a snapshot item if they have at least the same company code, key figure ID, and currency. Depending on your settings in the job template, additional criteria are relevant for the aggregation:

If you have selected specific dimensions in this job template, these dimensions are also relevant for the aggregation.

If you have defined periods in this job template, the relevant period of an exposure or hedge is also relevant for the aggregation.

Each snapshot item is saved with the amount in the transaction currency and also the amount in the reporting currency that you have specified in the job template.

The snapshot item consists of the following data:

General Information

Snapshot ID

Snapshot Item ID

Generation Method

A snapshot item is either generated using the job template Take Snapshot - Balance Sheet FX Risk or entered manually.

If a snapshot item is created manually by a user, the value Manual is shown in the Generation Method field.

Company Code

On-Behalf of Company Code

Amount in Transaction Currency

Amount in Reporting Currency

Key Figure

Period Start Date

Period End Date

Additional Dimensions

FI Account Number

FI Chart of Account

Certainty Level

Liquidity Item

Planning Level

Portfolio

Product Type

Transaction Type

Administrative Data

Created At

Created By

Last Changed At

Last Changed By

Using the Process Snapshots - Balance Sheet FX Risk app, you can display and check the snapshot generated. If an exposure that needs to be considered is missing in the system, you can create a snapshot item manually. When the snapshot data is correct, you can release the snapshot. For released snapshots, the app offers you the option of jumping to the related hedge request generated on the basis of the snapshot.

**Related Information**

Take Snapshot - Balance Sheet FX Risk Process Snapshots - Balance Sheet FX Risk

##### Balance Sheet Exposure Hedge Request

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Balance Sheet Exposure Hedge Request | L4 | trm04 p.138 | loio `3a1399b7f08c4569ac5a3f47f00fe85f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3a1399b7f08c4569ac5a3f47f00fe85f.html?locale=en-US)

For direct communication with your traders, you can create balance sheet exposure hedge requests for your net open balance sheet exposures based on released snapshot data to trigger the conclusion of the required hedges.

The balance sheet exposure hedge requests are created by executing the Generate Balance Sheet Exposure Hedge Requests app or the available job template Generate Balance Sheet Exposure Hedge Requests in the Schedule Treasury Middle Office Jobs app or by manually creating the hedge requests in the Process Hedge Requests - Balance Sheet FX Risk app.

**Balance Sheet Hedge Request - Data**

The balance sheet exposure hedge request has a B/S hedge request ID and a hedge request status.

Balance sheet exposure hedge request statuses

|Status|Remarks|
|---|---|
|Error|A hedge request with this status results from the generation of hedge request due to a requirement for the creation of hedge request not having been fulfilled, such as the minimum amount. The hedge request is shown in the Process Hedge Requests Balance Sheet FX Risk app but no further processing is possible.|


|Status|Remarks|
|---|---|
|Created|A hedge request gets the status Created if the target status for the generated hedge requests was Created. You can check the data of the hedge request and change the values if needed. If the data of the hedge request is correct, you can release the hedge request. You can also delete a hedge request if the hedge request is not needed.|
|Released|The system automatically creates a trade request for a released B/S hedge request. You can undo the release of a hedge request.|
|Canceled|If the trade request is rejected by the trading platform. the B/S hedge request gets the status Canceled.|
|In Process|If the related trade request has the status In Process, the B/S hedge request also gets the status In Process.|
|Completed|If the related trade request has been completed, the B/S hedge request also gets the status Completed.|


In addition, the balance sheet exposure hedge request contains the following information:

General Information

Value Date

Amount

Requested original amount to be hedged.

Currency

Company Code Currency

Risk-Free Currency

The risk-free currency is the currency in which the exposure is hedged.

Usually, the risk-free currency is the currency of the company code. For companies operating in countries where it is difficult to obtain hedging transactions in the risk-free company code currency or in countries where the company code currency is not stable, it may be necessary to use an alternative risk-free currency.

If you entered an alternative currency in the Risk-Free Currency field in the Take Snapshot - Balance Sheet FX Risk app, then this currency is the risk-free currency in the hedge request.

The desired trade activity, such as: Buy, Sell, Put, or Call, is specified either in the Buy/Sell Indicator field or in the Put/Call field.

Instrument Category

Specifies which kind of hedging instrument the trader should conclude to hedge the net open exposure.

Description

Open Amount

Residual amount of a hedge request that was not yet covered by a hedge.

Declined Amount

Amount of the corresponding trade request that has been declined by the trader.

Account Assignments

The value entered in these fields of the balance sheet exposure hedge request is later copied to the corresponding field for the financial transaction that has been concluded to fulfill the balance sheet exposure hedge request. In the financial transaction, you find the additional parameter fields on the Administr. tab. Only the External Reference field is in the Contract Conclusion area on the Structure tab.

Portfolio

External Reference

Assignment

Internal Reference

Characteristics

Profit Center

Cost Center

WBS Element

Country/Region Key

Segment

On Behalf of Company Code

Action History

In the Action History area, you can see all actions executed for the hedge request and the resulting status of the hedge request. You can also see who performed the action and when.

**Processing Balance Sheet Hedge Requests**

Using the Process Hedge Requests - Balance Sheet FX Risk app, you can manually create hedge requests as well as display, edit, delete, and release the balance sheet exposure hedge requests created.

For released B/S hedge requests, the system automatically creates a trade request. The field values of the hedge request are copied to the automatically generated trade request. Use the Process Trade Request app to process the trade requests further.

**Related Information**

Trade Request Process Trade Requests Hedge Management of Balance Sheet FX Risk Process Hedge Requests - Balance Sheet FX Risk Generate Balance Sheet Exposure Hedge Requests

##### Take Snapshot - Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Take Snapshot - Balance Sheet FX Risk | L4 | trm04 p.140 | loio `15f225be62cf4124b663d778575d6e54` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/15f225be62cf4124b663d778575d6e54.html?locale=en-US)

App ID: FXM_SNAP

**Use**

With this app, you can take a snapshot of balance sheet exposures and the corresponding hedges on the key date.

**Features**

Selects balance sheet exposures (B/S exposures) and their hedges according to the settings in the job template. If you have defined periods, the exposures and hedges are assigned to their relevant period by due date/value date.

Saves the selected data under a specific snapshot ID in the database table as follows:

The selected B/S exposures and hedges are aggregated to a snapshot item if they have at least the same company code, key figure ID, and currency. Depending on your settings in the job template, additional criteria are relevant for the aggregation:

If you have selected specific dimensions in this job template, these dimensions are also relevant for the aggregation.

If you have defined periods in this job template, the relevant period of an exposure or hedge is also relevant for the aggregation.

Each snapshot item is saved with the amount in the transaction currency and also the amount in the reporting currency that you have specified in the job template.

You can schedule background jobs that run regularly.

You can execute the report manually.

**Prerequisites**

If you want to take a snapshot of the relevant data for the B/S FX risk hedging, you must define the relevant key figures for exposures and hedges using the Define Settings - Balance Sheet FX Risk app.

**Integration**

Process Overview - Hedge Management of Balance Sheet FX Risk

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM04-F027]

Please note that image maps are not interactive in PDF outputs.

**Procedure**

- 1. Open the app from SAP Fiori launchpad or in the area menu under Treasury and Risk Management Hedge Management Balance Sheet FX Risk Take Snapshot - Balance Sheet FX Risk (transaction FXM_SNAP).
- 2. General Parameters


Snapshot Description

Enter a description for the snapshot.

Created in Status

Choose the status for the snapshot. You can choose between Created and Released. If you choose the status Created, you can later check the snapshot in the Process Snapshots - Balance Sheet FX Risk app. This app also offers you the option of adding snapshot items manually before you release the snapshot.

For more information, see also Process Snapshots - Balance Sheet FX Risk

Key Date Definition

You can use the key date definition to derive the key date of a job dynamically from the system date. You can choose between the following values:

System Date

The key date for the job is the current system date.

Current Month End

The key date for the job is the last day of the current month.

Current Quarter End

The key date for the job is the last day of the current quarter.

Fixed Date

If you choose this value, you must enter the key date manually.

**Note:**

This setting is relevant if a job is only run once.

Risk-Free Currency

Usually, the risk-free currency is the currency of the company code. Cash flows in this currency do not need to be hedged. If no currency is entered in the Risk-Free Currency field, the company code currency is taken as risk-free currency.

For companies operating in countries where it is difficult to obtain hedging transactions in the risk-free company code currency or in countries where the company code currency is not stable, it may be necessary to use an alternative risk-free currency.

If you enter an alternative currency in the Risk-Free Currency field, then this currency is used as risk-free currency. This means that cash flows in the alternative risk-free currency are not considered as exposures and the cash flows in the company code currency are considered as exposures.

Reporting Currency

Enter the reporting currency. The amounts are converted to this currency and saved on the database tables.

Exchange Rate Type

Enter the exchange rate type relevant for the currency translation in the reporting currency.

The exchange rate type distinguishes between different kinds of rate. If you enter an FX rate in the market data table, you must assign the exchange rate type.

Sub. Hedged by Treasury Center

If you select the Sub. Hedged by Treasury Centers indicator, the system selects for the company code of the treasury center also the exposures of the related subsidiaries. The company code of the subsidiary is then stored in the On-Behalf of Company Code field for each subsidiary exposure in the snapshot table.

**Note:**

This setting is only relevant if you want to hedge subsidiary exposures centrally.

In the Define Settings - Balance Sheet FX Risk app (App ID: FXM_KF_DEF), you then need to have already assigned the respective subsidiary company codes to the treasury center company codes for each currency that you want to hedge centrally.

- 3. Filter


Using the following fields, you can define the exposure and hedges relevant for this specific snapshot:

Company Code

Currency

Enter the relevant transaction currencies for which you want to hedge rate fluctuations.

Key Figure

Optional setting: You select specific key figures only in exceptional cases.

The key figures determine which data is selected and structure how the data is displayed in the B/S FX risk apps at the same time.

**Note:**

The key figures and key figure groups are defined in the Define Key Figures - Balance Sheet FX Risk app.

- 4. Dimensions


The selected dimensions are relevant for the aggregation of the snapshot data either for the data of a specific data source only or for all selected data.

One Exposure

Planning Level

Reflects the origin of a cash flow so as to indicate its reliability.

Certainty Level

This characteristic is used to indicate the reliability and therefore the likelihood of a flow in One Exposure from Operations. One Exposure derives cash forecasts for items from different sources. It stores this information with the certainty levels.

Liquidity Item

Liquidity items represent the source and use of cash flows in your company. They serve as an import dimension for financial planning and reporting in cash management.

Financial Accounting (FI)

G/L Account

The G/L account number identifies the G/L account in a chart of accounts.

Chart of Accounts

A chart of accounts is a structure containing the G/L accounts used by one or more company codes.

Planning Level

Reflects the origin of a cash flow so as to indicate its reliability.

Transaction Manager

Product Type

A classification of the financial instruments managed in your system.

The product type controls the structural characteristics (such as condition types and flow types) that are assigned to individual instruments in the system.

Transaction Type

The transaction type determines which financial transactions can be performed with a certain product type, for example, investing and borrowing deposits at notice.

Portfolio

A portfolio is an organizational element used to group together various treasury transactions for reporting purposes.

Additional Dimensions

This section is available if you have made settings in the Customizing activity Define Keyfigure Dimension Extensions. Select the additional dimensions that you want to be relevant for the snapshot.

Time Pattern

Period Definition

If you select this indicator, you define the overall reporting period by specifying dates in the Start Date and End Date fields. How the overall period is split into (sub)periods is defined by making entries in the Increment und Unit fields.

All exposure and hedges with due dates/value dates falling within the reporting period are selected and saved as snapshot items assigned to the specific period to which their due dates/value dates belong.

If you do not select this indicator, all selected exposures and hedges are selected and saved as snapshot items, independently of their due date/value date.

Start Date

Enter the start date.

End Date

Enter the end date.

Increment

Enter the number of units.

Unit

Select the unit relevant for the reporting period definition.

The following values are available:

Day

Month

Year

- 5. You can select the Test Run indicator.
- 6. Execute the report.


**Note:**

You can define a background job using transaction SM36 for ABAP program FXM_SNAPSHOT to run the calculation on a regular basis.

To schedule the run of the program in the background as a regular job, you must define a variant for the report in which you can control the evaluation date field dynamically.

- 1. Choose Save as Variant. Enter a variant name and a description.
- 2. In the Objects for Selection Screen table, select the value D D: Dynamic Date Calculation (Local Date) in the Key Date row, in the Selection Variable column.
- 3. In the Name of Variable column of the same row, now choose one of the the following options:


Current date

Current date +/- ??? days

current date +/- ??? work days

First day of current month

nth working day of current month

First day of next month

First day of previous month

Last day of previous month

Last day of current month

4. Save the variant.

**Result**

If the report has been executed successfully, the selected exposures and hedges are saved as snapshot items of the snapshot (under a specific snapshot ID) in database tables.

You can use the Process Snapshots - Balance Sheet FX Risk app to check and release the snapshot.

Based on the snapshot released, you can now run the Generate Balance Sheet Exposure Hedge Requests function.

**Related Information**

Hedge Management of Balance Sheet FX Risk Process Snapshots - Balance Sheet FX Risk Generate Balance Sheet Exposure Hedge Requests

###### Unit

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Take Snapshot - Balance Sheet FX Risk > Unit | L5 | trm04 p.145 | loio `18f3c9a0d884478982b520add62d4b68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/18f3c9a0d884478982b520add62d4b68.html?locale=en-US)

Select the unit relevant for the reporting period definition.

**Definition**

Together with the number entered in the Increment field, the unit that you specify is used to define the period length.

The following values are available:

Day

Month

Year

**Use**

You define the reporting periods by entering overall start and end dates and, in addition, you define the period length by specifying a combination of interval increment and interval unit.

The selected exposures whose due date falls into the same period/interval are assigned to this period.

The selected hedges whose value date falls into the same period/interval are assigned to this period.

**Example**

Start Date: 01.01.2020

End Date: 31.12.2020

Number: 1

Unit: Month

The system selects the exposures and hedges whose due date is within the year 2020 and assigns them to the relevant periods.

###### Exchange Rate Type

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Take Snapshot - Balance Sheet FX Risk > Exchange Rate Type | L5 | trm04 p.147 | loio `0f446bf2a832498a9993a3c76956a03e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f446bf2a832498a9993a3c76956a03e.html?locale=en-US)

Enter the exchange rate type relevant for the currency translation.

**Definition**

The exchange rate type distinguishes between different kinds of rate. If you enter an FX rate in the market data table, you must assign the exchange rate type.

**Use**

If the transaction currency is different from the reporting currency, the values are translated into the reporting currency. The currency translation uses the current FX rate for the relevant currency pair of the exchange rate type specified.

###### Increment

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Take Snapshot - Balance Sheet FX Risk > Increment | L5 | trm04 p.147 | loio `9d82193d68f745c3bb1a8660631706e2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9d82193d68f745c3bb1a8660631706e2.html?locale=en-US)

Enter the number of units.

**Definition**

The values of the Increment and the Unit fields together define the period length.

**Use**

You define the reporting periods by entering overall start and end dates and, in addition, you define the period length by specifying a combination of interval increment and interval unit.

The selected exposures whose due date falls into the same period/interval are assigned to this period.

The selected hedges whose value date falls into the same period/interval are assigned to this period.

**Example**

Start Date: 01.01.2020

End Date: 31.12.2020

Number: 1

Unit: Month

The system selects the exposures and hedges for which the due date is within the year 2020 and it assigns them to the relevant periods.

###### Certainty Level

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Take Snapshot - Balance Sheet FX Risk > Certainty Level | L5 | trm04 p.148 | loio `a20eeaef81d2478c8e75624c60b23a36` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a20eeaef81d2478c8e75624c60b23a36.html?locale=en-US)

Indicate the reliability and therefore the likelihood of a flow in One Exposure from Operations.

**Definition**

This characteristic is used to indicate the reliability and therefore the likelihood of a flow in One Exposure from Operations. One Exposure derives cash forecasts for items from different sources. It stores this information with the certainty levels.

**Use**

If you select this checkbox, the dimension chosen is also relevant for aggregating the snapshot data of the specific data source.

##### Process Snapshots - Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Process Snapshots - Balance Sheet FX Risk | L4 | trm04 p.148 | loio `f3ccdee3e0194deaaf47f901b8ec8527` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f3ccdee3e0194deaaf47f901b8ec8527.html?locale=en-US)

With this app, you can check, update, release, or delete snapshots generated using the Take Snapshots - Balance Sheet FX Risk function.

**Key Features**

This app provides the following key features:

Display snapshots and snapshot items

For snapshots with status Created, you can create a snapshot item manually.

You can release the snapshot.

If you release a snapshot by accident, you can undo the release.

**Note:**

This is possible only if you haven't created hedge requests based on the snapshot.

You can delete snapshots with status Created.

For snapshots with status Released, you can jump to the related hedge requests generated on the basis of the snapshot.

**Integration**

Process Overview - Hedge Management of Balance Sheet FX Risk

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM04-F028]

Please note that image maps are not interactive in PDF outputs.

**Additional Details**

You can use the following filters to find the snapshots that you want to display:

Snapshot ID

Description

Key Date

Status

Created By

Created At

Last Changed By

Last Changed At

Choose Go.

You get a list of snapshots according to your filter settings. If you do not restrict the search, the list comprises all available snapshots.

To process or display a snapshot, you must select the snapshot first.

Display the snapshot details

If you want to check the details of the snapshot, choose the Details arrow on the right side of the screen.

On the next screen, you find a list of snapshot items contributing to the snapshot. The Standard view shows the general information for each snapshot item. You can display more information using the View Settings button.

To display all information for a snapshot item, choose the Details arrow on the right side. The following fields are displayed for a snapshot item:

General Information

Snapshot ID

Snapshot Item ID

Generation Method

A snapshot item is either generated using the job template Take Snapshot - Balance Sheet FX Risk or entered manually.

If a snapshot item is created manually by a user, the value Manual is shown in the Generation Method field.

Company Code

On-Behalf of Company Code

Amount in Transaction Currency

Amount in Reporting Currency

Key Figure

Period Start Date

Period End Date

Additional Dimensions

FI Account Number

FI Chart of Account

Certainty Level

Liquidity Item

Planning Level

Portfolio

Product Type

Transaction Type

Administrative Data

Created At

Created By

Last Changed At

Last Changed By

Create a snapshot item manually

If a snapshot has the status Created, you can create additional snapshot items manually. This may be necessary if the exposure or hedge data on which the snapshot is based is not complete.

- 1. Choose the Create button.
- 2. Enter the data for the snapshot item. You can enter the general information as well as the additional dimensions for the snapshot item. The following rules apply:


You must enter the company code and the amounts in the risk currency and in the reporting currency.

If you enter additional dimensions, you must enter the dimensions of only one data source.

**Note:**

The dimension Planning Level is relevant for the data sources Financial Accounting and One Exposure.

- 3. Save your entries.
- 4. You must release a manually created snapshot item before you can release the snapshot.


If you create the snapshot item by accident, you can also delete it.

If the data of the snapshot is incorrect or the snapshot was created by accident, you can also delete snapshots with status Created.

If all data of the snapshot is correct, you can release the snapshot.

If you release a snapshot by accident, you can undo the release by choosing the Undo Release button.

**Note:**

This is possible only if you haven't created hedge requests based on the snapshot.

For snapshots with status Released, you can jump to the related hedge requests generated on the basis of the snapshot. The related hedge requests are displayed in the Process Hedge Requests - Balance Sheet FX Risk app.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Hedge Management of Balance Sheet FX Risk Snapshot - Balance Sheet FX Risk Balance Sheet Exposure Hedge Request Process Hedge Requests - Balance Sheet FX Risk Take Snapshot - Balance Sheet FX Risk

##### Generate Balance Sheet Exposure Hedge Requests

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Generate Balance Sheet Exposure Hedge Requests | L4 | trm04 p.151 | loio `5ad361ed905d4b98988c50a423e469e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5ad361ed905d4b98988c50a423e469e5.html?locale=en-US)

App ID: FXM_REQUEST

**Use**

With this app, you can generate balance sheet exposure hedge requests for your net open balance sheet exposures based on released snapshot data to trigger the conclusion of the required hedges.

**Features**

Generates hedge requests for your net open balance sheet exposures.

The net open balance sheet exposures are calculated by comparing the total amounts of the selected snapshot items for hedges and the selected snapshot items for balance sheet exposures on the level of the analysis item. The analysis item is

defined by the company code and the risk currency of the exposures and hedges as well as by the period (only if you have defined periods for the snapshot).

You can specify in the report a minimum amount for a balance sheet exposure hedge request (B/S Hedge Request) and the relevant rounding rules.

For the released balance sheet exposure hedge requests, trade requests (with trade request category B/S Hedge) are also created automatically.

If you are using the SAP Trading Platform Integration application, these trade requests are transferred to the trading platform, and the concluded trades (financial transactions) are automatically imported into your system.

**Note:**

Within the Integration with External Trading Platforms integration scenario, these trade requests are handled in the same way as the trade requests created for the hedge requests of the Hedge Management Cockpit.

If you do not use the SAP Trading Platform Integration application, the trader uses the Process Trade Requests app to to get information about the required hedging instruments.

Formulas: Calculation of Balance Sheet FX Risk Measures

[figure TRM04-F029 - Formulas: Calculation of Balance Sheet FX Risk Measures]

where

NE(abs.) = Balance sheet net open exposures (absolute) = Total of absolute amounts of balance sheet net open exposures for each transaction currency in the display currency

E(abs.) = Balance sheet exposures (absolute) = Total of absolute amounts of balance sheet exposures for each transaction currency in the display currency

H(abs.) = Hedges (absolute) = Total of absolute amounts of hedges for each transaction currency in the display currency

TC = Transaction currency

DC = Display currency

r = Exchange rate (transaction currency in display currency)

TC/DC

**Prerequisites**

Define Settings - Balance Sheet FX Risk

Take Snapshot - Balance Sheet FX Risk

**Integration**

Process Overview - Hedge Management of Balance Sheet FX Risk

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM04-F030]

Please note that image maps are not interactive in PDF outputs.

Based on the snapshot data you created using the Take Snapshot - Balance Sheet FX Risk function, you generate balance sheet exposure hedge requests when net open exposures are determined.

For the balance sheet exposure hedge requests generated, trade requests are generated automatically.

**Procedure**

- 1. Call the app from SAP Fiori launchpad or in the area menu under Treasury and Risk Management Hedge Management Balance Sheet FX Risk Generate Hedge Request - Balance Sheet FX Risk (transaction FXM_REQUEST).


- 2. The following parameters are relevant for the selection of the snapshot data used to create the hedge request:


Snapshot

You can find the relevant snapshot either by the key date or by the snapshot ID.

**Note:**

The selected snapshot must have the status Released.

Filtering

You can filter the snapshot data by company code, currency, and start and end date.

Filtering enables you to create balance sheet exposure hedge requests only for a specific company code, currency, and period.

Value Date

Specify the value date for the requested hedging instrument. You can either derive the value date from the period or select the value date. The following fields are available:

Value Date Definition

You can choose between the following values:

First Day of Period

Last Day of Period

Which day is ultimately derived as the value date of the balance sheet exposure hedge request is also influenced by the following fields:

Additional Days

Enter a number of days in this field if you want to change the value date that is set by default in the Value Date Definition field.

Working Days Shift

Select this checkbox to ensure that the system checks the value date for holidays and only creates balance sheet hedge requests with a value date that is a working day. This check is based on the factory calendar of the risk currency.

If the value date isn't a working day, it is not valid, and a valid date needs to be determined.

Working Day

Select one of the following options:

Next Working Day

Previous Working Day

Working Day Shift Calendar

You can select the factory calendar that should be relevant for the working day shift.

Value Date Selection

If you choose to derive the value date of the balance sheet exposure hedge request from the system date, you can choose between the following dates in the Value Date Selection field:

Current Month End

Current Quarter End

Fixed Date

In this case, you enter the value date manually.

Value Date

The value date is usually determined dynamically. It is derived either from the exposure period or from the system date. It is also possible to enter the value date manually.

Parameters

Main Parameters

The main parameters are relevant for the creation of the hedge requests:

Instrument Category

You can specify which kind of hedging instrument the trader concludes to hedge the net open exposure.

Rounding

Define the unit with which the calculated hedge request amount is rounded.

Example

You enter in this field the value 1.000

The calculated hedge request amount is 22.365 USD.

Due to this rounding rule, the hedge request amount is rounded to 22.000 USD.

Minimum Amount

Enter the minimum amount for balance sheet exposure hedge requests.

Only if the hedge request amount determined is equal to or higher than the minimum amount is a hedge request created.

Currency

Enter the currency of the minimum amount.

Exchange Rate Type

If the transaction currency is different from the currency of the minimum amount, the values are translated into the currency of the minimum amount. The currency translation uses the current FX rate for the relevant currency pair of the exchange rate type specified.

Target Status

You can choose the target status for the hedge request.

If you choose the status Created, you can process (check and release or delete) the hedge requests created.

If you choose the status Released, the system automatically creates a trade request from the hedge request.

You can use the Process Hedge Requests - Balance Sheet FX Risk app to display and process hedge requests.

Description

Enter a description for the hedge request.

Additional Parameters

The value that you enter in this field for the balance sheet exposure hedge request is later copied to the corresponding field for the financial transaction that has been concluded to fulfill the balance sheet exposure hedge request. In the financial transaction, you find the additional parameter fields on the Administr. tab. Only the External Reference field is in the Contract Conclusion area on the Structure tab.

**Note:**

Entering additional parameters is optional.

Portfolio

External Reference

Assignment

Internal Reference

Characteristics

Profit Center

Cost Center

WBS Element

Country/Region Key

Segment

On Behalf of Company Code

- 3. You can set the Test Run indicator.
- 4. Choose Execute.


**Note:**

You can define a background job using transaction SM36 for ABAP program FXM_REQUEST to run the calculation on a regular basis.

To schedule the run of the program in the background as a regular job, you must define a variant for the report in which you can control the evaluation date field dynamically.

- 1. Choose Save as Variant. Enter a variant name and description.
- 2. In the Objects for Selection Screen table, select the value D D: Dynamic Date Calculation (Local Date) in the Key Date row in the Selection Variable column.
- 3. In the Name of Variable column of the same row, now choose one of the the following options:


Current date

Current date +/- ??? days

current date +/- ??? work days

First day of current month

nth working day of current month

First day of next month

First day of previous month

Last day of previous month

Last day of current month

4. Save the variant.

**Result**

If the report has been executed successfully, the hedge requests created are stored in the database table for the balance sheet exposure hedge request with the chosen target status.

If the hedge requests are created with the status Created, you can use the Process Hedge Requests - Balance Sheet FX Risk app to check, edit, and release the hedge requests generated.

If the hedge requests are created with the status Released, you can use the Process Hedge Requests - Balance Sheet FX Risk app to display the hedge requests.

After the hedge request has been released, a trade request is created automatically for each balance sheet exposure hedge request. Use the Process Trade Request app to process the trade requests further.

**Related Information**

Hedge Management of Balance Sheet FX Risk Review Balance Sheet FX Risk Take Snapshot - Balance Sheet FX Risk Process Snapshots - Balance Sheet FX Risk Process Hedge Requests - Balance Sheet FX Risk Process Trade Requests

###### Key Date Definition

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Generate Balance Sheet Exposure Hedge Requests > Key Date Definition | L5 | trm04 p.157 | loio `185fc62a37d74d34a6f32a356088c522` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/185fc62a37d74d34a6f32a356088c522.html?locale=en-US)

Derive the key date dynamically from the system date.

**Definition**

You can use the key date definition to derive the key date of a job dynamically from the system date. You can choose between the following values:

System Date

The key date for the job is the current system date.

Current Month End

The key date for the job is the last day of the current month.

Current Quarter End

The key date for the job is the last day of the current quarter.

Fixed Date

If you choose this value, you must enter the key date manually.

**Note:**

This setting is relevant if a job is only run once.

###### Period Definition

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Generate Balance Sheet Exposure Hedge Requests > Period Definition | L5 | trm04 p.158 | loio `3df2959bfb89446c836c61b6d0c4b7ee` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3df2959bfb89446c836c61b6d0c4b7ee.html?locale=en-US)

Define overall reporting period and split the overall period into intervals.

**Definition**

If you select this indicator, you define the overall reporting period by specifying dates in the Start Date and End Date fields. How the overall period is split into (sub)periods is defined by making entries in the Increment und Unit fields.

All exposure and hedges with due dates/value dates falling within the reporting period are selected and saved as snapshot items assigned to the specific period to which their due dates/value dates belong.

If you do not select this indicator, all selected exposures and hedges are selected and saved as snapshot items, independently of their due date/value date.

###### Rounding

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Generate Balance Sheet Exposure Hedge Requests > Rounding | L5 | trm04 p.158 | loio `d259f560fcd84cdba50dbd79a9b55399` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d259f560fcd84cdba50dbd79a9b55399.html?locale=en-US)

Enter the rounding unit.

**Definition**

Define the unit with which the calculated hedge request amount is rounded.

Example

You enter in this field the value 1.000

The calculated hedge request amount is 22.365 USD.

Due to this rounding rule, the hedge request amount is rounded to 22.000 USD.

###### Assignment

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Generate Balance Sheet Exposure Hedge Requests > Assignment | L5 | trm04 p.158 | loio `2a1fe62899514b209d52ff09e61bfc57` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2a1fe62899514b209d52ff09e61bfc57.html?locale=en-US)

Select a value or enter a free text.

**Definition**

Freely definable allocation used to group financial transactions.

**Note:**

Depending on the settings in your system, one of the following input possibilities applies:

The input help does not contain any values. You can enter a free text in this field.

The input help contains values for you to select, but you can also enter a different text in this field.

Configuration

The values that are available for selection depend on the customer-specific configuration. For more information, see also Generate Balance Sheet Exposure Hedge Requests

**Additional Parameters of Balance Sheet Exposure Hedge Request**

The value that you enter in this field for the balance sheet exposure hedge request is later copied to the corresponding field for the financial transaction that has been concluded to fulfill the balance sheet exposure hedge request. In the financial transaction, you find the additional parameter fields on the Administr. tab. Only the External Reference field is in the Contract Conclusion area on the Structure tab.

**Note:**

Entering additional parameters is optional.

###### Characteristics

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Generate Balance Sheet Exposure Hedge Requests > Characteristics | L5 | trm04 p.159 | loio `7a068669bfba489d8cd5311a7ee928a9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7a068669bfba489d8cd5311a7ee928a9.html?locale=en-US)

Select a value or enter a free text.

**Definition**

Freely-definable identification for transactions.

**Note:**

Depending on the settings in your system, one of the following input possibilities applies:

The input help does not contain any values. You can enter a free text in this field.

The input help contains values for you to select, but you can also enter a different text in this field.

Use

Configuration

The values that are available for selection depend on the customer-specific configuration. For more information, see also Generate Balance Sheet Exposure Hedge Requests

**Additional Parameters of Balance Sheet Exposure Hedge Request**

The value that you enter in this field for the balance sheet exposure hedge request is later copied to the corresponding field for the financial transaction that has been concluded to fulfill the balance sheet exposure hedge request. In the financial transaction, you find the additional parameter fields on the Administr. tab. Only the External Reference field is in the Contract Conclusion area on the Structure tab.

**Note:**

Entering additional parameters is optional.

##### Process Hedge Requests - Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Hedge Management of Balance Sheet FX Risk > Process Hedge Requests - Balance Sheet FX Risk | L4 | trm04 p.160 | loio `00c65efbbb014ef9970e0e9e12d75604` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/00c65efbbb014ef9970e0e9e12d75604.html?locale=en-US)

With this app, you can display, edit, release, or delete balance sheet exposure hedge requests.

**Key Features**

This app provides the following key features:

Display the balance sheet exposure hedge requests

You can edit balance sheet exposure hedge requests with status Created.

You can release balance sheet exposure hedge requests with status Created.

You can delete balance sheet exposure hedge requests with status Created.

You can undo the release of balance sheet exposure hedge requests with status Released.

For released hedge requests, you can jump to the related trade requests.

You can jump to the underlying snapshot.

**Integration**

Process Overview - Hedge Management of Balance Sheet FX Risk

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM04-F032]

Please note that image maps are not interactive in PDF outputs.

**Additional Details**

You can use the following filters to find the hedge requests that you want to display:

Basic Filters

Hedge Request ID

Status

Company Code

Instrument Category

Currency

Value Date

Description

Trading Activity

Snapshot ID

You can add additional filters using the Adapt Filters button.

**Note:**

The filters are the fields of the hedge request and are visible as columns in the results list. For more information, see also Balance Sheet Exposure Hedge Request

Choose Go.

You get a list of hedge requests according to your filter settings. If you do not restrict the search, you get a list of all available hedge requests.

To process or display a hedge request, select it.

Display hedge request details

If you want to display the details of a hedge request, choose the Details arrow on the right side of the screen.

On the screen that appears, you see all available information for the selected hedge request. The general information, the account assignments, and the action history of the hedge request are shown. For more information, see also Balance Sheet Exposure Hedge Request

- 1. You can check the data.
- 2. If the data of the hedge request is incorrect or incomplete, you can change the field values of the hedge request with status Created.


**Note:**

For released hedge requests, the trade request ID of the related trade request is shown. The status of the hedge request and the Open Amount and Declined Amount fields provide information about the fulfillment status of the hedge requests.

If a hedge request was created by accident or is not needed, you can delete hedge requests with status Created.

You can jump to the underlying snapshot by clicking the snapshot ID.

If all data of the hedge request is correct, you can release the hedge request using the Release button at the top of the list.

With the release of a hedge request, the system automatically creates a trade request.

If you release a hedge request by accident, you can undo the release using the Undo Release button.

**Note:**

This is possible only if the related trade request hasn't been fulfilled so far.

If a hedge request is already released, you can jump to the related trade request by clicking the trade request ID displayed.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Hedge Management of Balance Sheet FX Risk Generate Balance Sheet Exposure Hedge Requests Balance Sheet Exposure Hedge Request

#### Comparison of Hedge Management and Accounting of Net Open Exposures (FX Risk) and Hedge Management of Balance Sheet FX Risk

> **Path:** Treasury and Risk Management > Hedge Management of FX Risks > Comparison of Hedge Management and Accounting of Net Open Exposures (FX Risk) and Hedge Management of Balance Sheet FX Risk | L3 | trm04 p.162 | loio `605b6caef795445986c9aeeb2ce929a9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/605b6caef795445986c9aeeb2ce929a9.html?locale=en-US)

The following table compares the features of the two processes available for hedging FX risks in Treasury and Risk Management.

| |Hedge Management and Accounting of Net Open Exposures (FX Risk) |Hedge Management of Balance Sheet FX Risk |
|---|---|---|
|Standard hedging use case|Hedge FX risks of planned and confirmed cash flows in foreign currencies in future periods.|Hedge FX risks arising from the revaluation of monetary balance sheet items in foreign currency. Hedge FX risks of planned and confirmed cash flows in foreign currencies in future periods.|
|Source of exposures|TRM - Exposure Management Cash Management - One Exposure|FI Balances FI Open Items Cash Management - One Exposure|


| |Hedge Management and Accounting of Net Open Exposures (FX Risk) |Hedge Management of Balance Sheet FX Risk |
|---|---|---|
|Grouping dimension and differentiation criteria|Defined by various setting options in the hedging area: Filters for relevant exposures and hedges Definition of risk-free currencies Definition of foreign currencies that are relevant for hedging in your company. Reporting time pattern The currency is always a differentiation criterion. You can use additional differentiation criteria, such as Company Code, Portfolio, and Cost Center, to define the level of granularity on which you want to monitor your net open exposures.|Customer-defined key figure groups and key figures specify for the different data sources which exposures are relevant for hedging and which of the financial transactions of the Transaction Manager were made to hedge FX risk. You make the snapshots for the hedging-relevant currencies. The reporting periods are defined with the snapshot. The company code and the transaction currency are always differentiation criteria. Additional dimensions, such as Planning Level, Product Type, and G/L Account, are available for the aggregation of the snapshot data.|
|Hedging key figures|The hedge management cockpit offers you a variety of key figures that analyze the current hedging situation for an analysis item. For more information, see also Key Figures in the Hedge Management Cockpit. |The Balance Sheet FX Risk Overview Based on Snapshots app provides the following key figures: Net Exposure Open B/S Hedge Request Hedged Amount Net Open Amount The amounts are displayed in risk currency and in display currency. In addition, the following aggregated values are displayed: Total net open amount in a risk currency under the same company code. Total open net amount in display currency for each risk currency under the same company code.|
|Hedging instruments|FX Spot FX Forward FX NDF FX Option FX Swap|FX Spot FX Forward FX NDF FX Option FX Swap|


| |Hedge Management and Accounting of Net Open Exposures (FX Risk) |Hedge Management of Balance Sheet FX Risk |
|---|---|---|
| |Collar FX Option|Collar FX Option|
|Hedge request creation|Automated creation of FX hedge requests For more information, see also Triggering the Creation of Automated FX Hedge Requests Manual creation of hedge requests|Generation of hedge requests using the following apps: Generate Balance Sheet Exposure Hedge Requests Manual creation of hedge requests in the Process Hedge Requests - Balance Sheet FX Risk app |
|Integration with trading platform integration application|Yes|Yes|
|Cross-currency hedging|Yes|No|
|Target quota|Yes|No|
|Hedge accounting|Yes|No|

