# Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items - SAP TRM Knowledge Base (branch split)

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

##### Hedge Accounting for Exposure Items

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items | L4 | trm09 p.2 | loio `bca73558e4912260e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bca73558e4912260e10000000a44147b.html?locale=en-US)

**Use**

The Hedge Accounting for Exposure Items is part of the Hedge Management and Accounting of Net Open Exposures (FX Risk) process and enables you to perform hedge accounting for cash flow hedges to support IFRS 9 and U.S. GAAP requirements for the foreign exchange exposures that your company is exposed. The process includes an automated designation process, which automatically designates hedging instruments into a hedging relationship when the financial transaction is saved, classification and reclassification process of designated hedging relationships as well as the dedesignation process.

With this process, you can map cash flow hedges and fair value hedges using a hedging relationship to perform hedge accounting for designated exposure subitems.

**Note:**

Currently only FX forward transactions, FX swap transactions, plain vanilla and collar FX options (European style), and nondeliverable forwards (NDFs) can be used as hedging instruments.

Hedging Scenarios for Hedge Accounting for Exposure Items

|Hedging Scenario|Hedging Relationship Category|Hedged Item Category|Product Categories Allowed as Hedging Instruments|Hedge Accounting Rule|
|---|---|---|---|---|
|910 CFH: FX Risk with Spot, Forward + CCBS IFRS 9|Cash Flow Hedge|Planned Forecast|600|HA Rule 611|
|913 CFH: FX Risk with Spot, Forward + CCBS + Others IFRS 9|Cash Flow Hedge|Planned Forecast|600|HA Rule 613|
|920 CFH: FX Risk with Forward + Spot, CCBS IFRS 9|Cash Flow Hedge|Planned Forecast|600|HA Rule 622|
|923 CFH: FX Risk with Forward + Spot, CCBS + Others (IFRS 9)|Cash Flow Hedge|Planned Forecast|600|HA Rule 623|
|931 FVH: FX Risk with Full Fair Value|Fair Value Hedge|Recognized Asset/Liability|600|HA Rule 631|


|Hedging Scenario|Hedging Relationship Category|Hedged Item Category|Product Categories Allowed as Hedging Instruments|Hedge Accounting Rule|
|---|---|---|---|---|
|IFRS 9| |(→ Balance Sheet Exposure)| | |
|932 CFH: FX Risk with Full Fair Value IFRS 9|Cash Flow Hedge|Recognized Asset/Liability (→ Balance Sheet Exposure)|600|HA Rule 632|
|941 FVH: FX-Risk with Spot, Forward U.S. GAAP|Fair Value Hedge|Recognized Asset/Liability (→ Balance Sheet Exposure)|600|HA Rule 641|
|942 CFH: FX-Risk with Spot, Fwd + Fwd Points Amort. U.S. GAAP|Cash Flow Hedge|Planned Forecast|600|HA Rule 642|
|943 CFH: FX-Risk with Intrinsic, Time + Premium Amort. U.S. GAAP|Cash Flow Hedge|Planned Forecast|760|HA Rule 643|
|980 CFH: FX Risk with Intrinsic, Time + CCBS IFRS 9|Cash Flow Hedge|Planned Forecast|760|HA Rule 650|
|981 CFH: FX Risk with Intrinsic, Time + CCBS + Others IFRS 9|Cash Flow Hedge|Planned Forecast|760|HA Rule 651|
|990 NIH: FX-Risk with Spot, Forward U.S. GAAP|Net Investment Hedge|Net Investment|600|HA Rule 641|


Fair Value Hedges (FVH)

With a fair value hedge you hedge the risk of fluctuations in the fair value of balance sheet positions, such as, nominal values of loans in foreign currencies and nominal values of dividend payments.

For the fair value hedges you usually want to hedge a specific exposure. You need to define a hedging area with analysis items of the type By Reference. The analysis items of these hedging areas are defined By Reference. The analysis items contain an exposure item based on only one non-aggregated exposure position with an exposure position type for which the aggregation indicator is not set and the No Planning Period and Planning Year indicator is set.

Cash Flow Hedges (CFH)

With a cash flow hedge you hedge the risk of fluctuations in a cash flow. The cash flows can be of the type Planned Forecast, such as revenues, or Recognized Asset/Liability (=> Balance Sheet Hedges), such as, interest payments. For these differenct categories of cash flows you need to define different hedging areas.

The hedging areas for planned forecast cash flows have period based analysis items, which allows to bundle different exposure positions within an exposure item.

For the balance sheet hedges you need to define hedging areas with analysis items By Reference which allow you to hedge one specific exposure position. In this case, the analysis items contain only one exposure item based on one nonaggregated exposure position (exposure position type for which the aggregation indicator is not set and the No Planning Period and Planning Year indicator is set).

Net Investment Hedge (NIH)

The exposure of a net investment hedge results from the fair value of a foreign investment, such as an FGB position, and is hedged with FX forward transactions.

Balance Sheet Exposures

No cost of hedging reserve needs to be calculated.

Planned cashflow hedge: Posting to position component 1302 Effective / Hedging Reserve.

Fair value hedge: Posting to position component 1343 P&L Effective / Designated Components

**Note:**

There are no technical restrictions which force you to use a specific kind of exposure item for a hedging scenario.

You can apply the Automated Designation Process for these hedging scenarios. In case you need to take more than one snapshots per day with day reference indicator, you can postpone the automated designation of your hedging instruments until the end of the day. For more information, see also End-of-Day Designation

**Hedge Accounting Rules**

The hedge accounting rule specifies how the hedged item and the hedging instruments are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. The hedge accounting rule also determines how the classification is calculated.

In the following table you get an overview of the market value and element components (see also Hedge Accounting Key Figures), the calculation methods, and position components relevant in the hedge accounting rules.

Overview Hedge Accounting Rules

|Hedge|Designated|Designated|Non-|Non-|Amortization|Calculation|Calculation|C|
|---|---|---|---|---|---|---|---|---|
|Accounting|Component|Component|Designated|Designated|Based on|Method|Method| |
|Rule|Hedging|Hyp. Derivative|Component|Component| |Desig.|Non-Desig.| |
| |Instrument| |Hedging|Hyp. Derivative| |Comp.|Comp.| |
| | | |Instrument| | | | | |
|HA Rule 611|NPV_SPOT|NPV_SPOT|NPV_FORWARD|NPV_FORWARD| |Lower-of-|According| |
|Cash Flow Hedge| | |NPV_CCBS|NPV_CCBS| |Test|to calculation method for| |
|Planned Forecast IFRS 9| | | | | | |cost of hedging reserve determined| |
| | | | | | | |at the| |
| | | | | | | |release of| |
| | | | | | | |designation| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | |either actual value, aligned value, or lower-oftest.*| |
|HA Rule 613 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT|NPV_SPOT|NPV_FORWARD NPV_CCBS NPV_OTHER|NPV_FORWARD NPV_CCBS NPV_OTHER| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |
|HA Rule 622 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT NPV_FORWARD|NPV_SPOT NPV_FORWARD|NPV_CCBS|NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 623 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT NPV_FORWARD|NPV_SPOT NPV_FORWARD|NPV_CCBS NPV_OTHER|NPV_CCBS NPV_OTHER| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | |actual value, aligned value, or lower-oftest.*| |
|HA Rule 631 Fair Value Hedge Recognized Asset/Liability IFRS 9|NPV_SPOT NPV_FORWARD NPV_CCBS NPV_OTHERS|NPV_SPOT NPV_FORWARD|-|-| |Lower-ofTest|-| |
|HA Rule 632 Cash Flow Hedge Recognized Asset/Liability IFRS 9|NPV_SPOT NPV_FORWARD NPV_CCBS NPV_OTHERS|NPV_SPOT NPV_FORWARD|-|-| |Lower-ofTest|-| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|HA Rule 641 Fair Value Hedge Net Investment Hedge Recognized Asset/Liability Net Investment U.S. GAAP|NPV_SPOT|NPV_SPOT|NPV_FORWARD|NPV_FORWARD| |Actual Value|Actual Value| |
|HA Rule 642 Cash Flow Hedge Planned Forecast U.S. GAAP|NPV_SPOT|NPV_SPOT|NPV_FORWARD|NPV_FORWARD|ELEM_FWD|Actual Value|Actual Value| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |
|HA Rule 643 Cash Flow Hedge Planned Forecast U.S. GAAP|NPV_INTR|NPV_INTR|NPV_TIME NPV_OTHER|NPV_TIME|NPV_OTHER|Actual Value|Actual Value| |
|HA Rule 650 Cash Flow Hedge Planned Forecast|NPV_INTR|NPV_INTR|NPV_TIME NPV_CCBS|NPV_TIME NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|IFRS 9| | | | | | |reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 651 Cash Flow Hedge Planned Forecast IFRS 9|NPV_INTR|NPV_INTR|NPV_TIME NPV_CCBS NPV_OTHER|NPV_TIME NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |


*To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing of the hedging profile. In this case, the result of the lower-of-test executed at the release of designation is set to Actual Value = Aligned Value.

For more information: Overview Hedge Accounting Rules

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

The following figure gives you an overview of the Hedge Accounting for Exposure Items process.

This image is interactive. Hover over each process step for a description. Click the action for more information.

[figure TRM09-F001]

Please note that image maps are not interactive in PDF outputs.

- 1. Follow the steps described in Hedge Management and Accounting of Net Open Positions (FX Risk).

- 2. With the creation of the hedging instruments using Create Financial Transaction (transaction FTR_CREATE) for hedge accounting relevant hedging areas the hedge accounting process starts.
- 3. Automated Designation Process

The automated designation process is triggered once the financial transaction is saved.

The financial transaction is designated into a hedging relationship where it acts as the hedging instrument.

- 4. Use function Reprocess Financial Transactions for Automated Designation (transaction TPM104) if errors relevant to hedge accounting occurred during the automated designation process.

The system issues error messages as warning messages while saving the financial transaction in the Create Financial Transaction function. Use transaction TPM104 to display the logs and analyze the errors. Then solve these issues either with the Edit Financial Transaction function or by making any missing Customizing settings.

- 5. Change of Hedging Instrument

Solving errors that occurred during the creation of a hedging relationship might require changes to the financial transaction. These changes have different effects on the hedging relationship and might impact the automated designation process.

- 6. The status of the financial transaction has to be set to Contract Settlement before any postings of flows can be created.
- 7. Release Hedging Business Transactions


**Note:**

If you use a collar or a FX swap as the hedging instrument, a separate step is necessary to trigger the automated designation process. For more information, see Create Reference.

**Note:**

You can postpone the automated designation of your hedging instruments until the end of the day. In this case, the automated designation is not started when the hedging instrument is saved. Instead, you start the automated designation of the financial transactions at the end of the day using the Reprocess Financial Instruments for Automated Designation report. This enables you to take several snapshots with day-reference indicator per day. Only after you have taken the last snapshot of the day, you trigger the end-of-day designation for all hedging instruments of the day. For more information, see End-of-Day Designation

**Note:**

This function is not available for collars or FX swaps. If an error occurs during the automated designation process, you won't be able to save the reference. Please correct the error and retry.

To complete the designation process, you have to release your hedging relationship(s) using the Release Hedging Business Transactions app. A prospective effectiveness test is executed with the release of designation, when the effectiveness

testing is activated in the hedging profile. In addition, a Documentation of a Hedging Relationship can be automatically created during the release of designation.

- 8. Post Derived Business Transactions

Before you can proceed with the period-end closing process, the derived business transactions in Plan status that were generated during the automated designation process have to be fixed using the Post Derived Business Transactions function (transaction TPM18).

- 9. Period-End Closing

The period-end closing process includes the following three steps:

Calculate NPVs and market value components (transaction TPM60CVA)

Execute key date valuation (transaction TPM1)

Run Classification (transaction TPM101)

- 10. In case you face an overhedge situation, the Hedge Management Cockpit offers you to create either swap requests or dedesignation requests. The released hedge requests are executed automatically (dedesignation request) or are made available to the traders (swap request).

Creating a Dedesignation Request

Process Dedesignation Request

Creating an FX Swap Request

Process FX Swap Request

- 11. Contract Close

The following processes take place at the end of a hedging relationship:

Exercise of FX Option

Dedesignation on the maturity date of the FX transaction

Reclassification on the end date of the exposure subitem. For more information, see Reclassification

- 12. Reporting


Use the following three apps to carry out your position reporting activities:

Treasury Position Values - Classic

Treasury Position Flows - Classic

Treasury Posting Journal - Classic

**More Information**

Hedge Management and Accounting of Net Open Exposures (FX Risk)

Settings for Hedge Accounting for Exposure Items

Manage Hedging Relationships

###### Settings for Hedge Accounting for Exposure Items

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Settings for Hedge Accounting for Exposure Items | L5 | trm09 p.13 | loio `d4842c5863352360e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d4842c5863352360e10000000a44147b.html?locale=en-US)

Customizing

|Customizing Activity|Use|Activities|
|---|---|---|
|Number Ranges|Here you first define number ranges for the following objects: Hedging relationships Hedged items Hedging instruments Hypothetical derivatives Exposure subitems Under Assign Number Ranges, define for each company code and valuation area which of the number ranges defined above is used. You find these activities in Customizing for Treasury and Risk Management, under Transaction Manager General Settings Hedge Accounting for Positions Number Ranges .|1. Determine the company c the number range interva 2. Choose Change Intervals 3. Enter a number for the ne 4. Determine the year for wh range interval. 5. Enter the number range. 6. You can set the External i ranges, the number is ass 7. Save your changes. **Note:** Only required for some Otherwise start with ste **Note:** You do not need to ente exposure subitems.|
|Settings for Automated Designation of Exposure Items (FX Risk)| | |
|Define Designation Types|In this activity, you define designation types for the automated designation process. The designation type is assigned on the Hedge Accounting II tab in the Hedging Area for a combination of differentiation criteria. These include: Company code Valuation area On Behalf of Company Code The company code on behalf of which you perform a transaction. Hedging classification You find these activities in Customizing for Treasury and Risk Management, under Transaction Manager General Settings Hedge Accounting for Positions Settings for Automated Designation of Exposure Items (FX Risk) .|1. Choose New Entries. 2. In the Designation Type fi 3. In the Designation Categ category for this designat For example, choose One list. 4. In the Description field, e designation type. For example, enter FX For 5. Set the Release of Hedgin Counterconfirmation ind The designation type con relationships can be relea hedging instruments have counterconfirmed. Otherwise, the system rel sufficient market data is a prevents the release. 6. End-of-Day Designation i Choose whether the auto immediately with the crea|


|Customizing Activity|Use|Activities|
|---|---|---|
| | |or whether it starts at the snapshots of the day have This setting is relevant fo snapshots a day with the case, you trigger the auto snapshot of the day using Transaction for Automat 7. Save your entries. **Note:** All designation types re have the same settings designation. They all pro designation or for imme|
|Define Product Types for Exposure Subitems|The Exposure Item product category is available for position management and accounting purposes on the exposure subitem level. You use this Customizing activity to define which product types are considered for exposure subitems in your installation. You assign the relevant product types in the hedging area master data: On the Main Data tab, you can enter the default product type for your exposure subitems. On the Hedge Accounting II tab, you can replace this default product type by another product type for exposure subitems. This maybe useful if you want to differentiate the posting for the different kinds of hedging instruments. You find this activity in Customizing for Treasury and Risk Management, under Transaction Manager General Settings Hedge Accounting for Positions Settings for Automated Designation of Exposure Items (FX Risk) .|1. Choose New Entries. 2. Specify the following valu Product Type Enter the product Name of Product Enter a descriptio Product Category Select the produc|
|Assign Update Types to Product Types|The Update Type Open is created with the hedging relationship on the end date of the exposure subitem. You use this Customizing activity to assign update types to product types for the creation of the open and close business transactions. This enables position management and accounting processes for exposure subitems. The Update Type Close is created with the hedging relationship on the end date of the exposure subitem. You find this activity in Customizing for Treasury and Risk Management, under Transaction Manager General Settings Hedge Accounting for Positions Settings for Automated Designation of Exposure Items (FX Risk) .|1. Choose New Entries 2. Specify the following: Product Type Select the produc Update Type Ope Select the open e Update Type Clos You use this Custo types to product t and close Select the close e|


|Customizing Activity|Use|Activities|
|---|---|---|
|Control Flows for Valuation/Classification Results at Term End|At the term end of a foreign exchange transaction, flows can be created to split the realized gain/loss into its individual valuation and classification components. You can find this activity in Customizing forTreasury and Risk Management, under Transaction Manager General Settings Hedge Accounting for Positions Settings for Automated Designation of Exposure Items (FX Risk) . For more information, see Valuation and Classification Results at Term End for FX Transactions. |Choose New Entries. To include positions for th set the Included indicator Save your entries.|
|Assign General Valuation Class to Product Type|You use this Customizing activity to define a general valuation class that is used as a default value for product types for exposure subitems. The general valuation class is then determined automatically for position management purposes. The general valuation class is needed so that the position management procedure can be determined for exposure subitems. It can be defaulted on the product type, company code, or product type level. As a prerequisite, you need to define the general valuation classes in Customizing, under Treasury and Risk Management Transaction Manager General Settings Accounting Settings for Position Management Define and Assign Valuation Classes . You find this activity in Customizing for Treasury and Risk Management, under Transaction Manager General Settings Hedge Accounting for Positions Settings for Automated Designation of Exposure Items (FX Risk) .|1. Choose New Entries. 2. Product Type Select the product type 9 3. General Valuation Class Use the drop-down menu Exposure Items. 4. Setting per Company Co Make any company-code-|
|Define Position Management Procedure|You must define a position management procedure for the exposure subitems and the position management procedures for the FX transactions which are used as hedging instruments. In the position management procedures for the FX transactions you can either assign a security valuation step or you can define a two-step valuation for freestanding subpositions and security valuation step for designated subpositions. Only one security valuation step assigned In this case, the valuation executes security valuation for the designated and the freestanding subpositions and the resulting amounts are posted. For the designated subpositions the classification distributes the different effects according to the relevant hedge accounting rule. Make the following settings to enable this process: Under Define Security Valuation Procedure, you define a security valuation procedure (004) with Write-Up Rule: Write up to Market Value/Present Value and the WriteDown Rule: Write Down to Market Value/Present Value. In addition, set the Currency Risk and Price Risk indicator in the Hedge Accounting for Positions area. Create the position management procedure for the FX transactions and assign the new security valuation procedure as steps.|Create a positions management p subitems: 1. Choose New Entries 2. Enter a 4-digit ID in the Po the position management 3. Choose the Position Man 4. Choose the Transfer Cate Component. 5. In the Hedge Accounting Evaluation Type and a CV 6. Choose a Rounding Rule 7. Choose a Valuation Base 8. Save your entries. |


|Customizing Activity|Use|Activities|
|---|---|---|
| | |Valuation Procedure: 1. FX Rate Valuation - Exec.Solely in Case of Hedge Accounting Indicator: - ; Do Not Execute in Case of Hedge Accounting Indicator: X|
| |Two-step valuation for freestanding subpositions and security valuation for designated subpositions The valuation only executes security valuation for the designated subpositions. For the freestanding subpositions a rate valuation is executed and in a secound step a security valuation which takes the rate valuation into account is executed. [figure TRM09-F002 - Two-Step Valuation for Freestanding Subpositions and Security Valuation for Designated Subpositions] Two-Step Valuation for Freestanding Subpositions and Security Valuation for Designated Subpositions Make the following settings to enable this process: Create a position management procedure for FX transactions used as hedging instruments. Under Define Security Valuation Procedure, you define a security valuation procedure (004), which gets the Execute Solely in the Case of Hedge Accounting indicator and another security valuation methods which gets the Do not Execute in the Case of Hedge Accounting indicator. Both get the Write-Up Rule: Write up to Market Value/Present Value and the Write-Down Rule: Write Down to Market Value/Present Value. Both get the Currency Risk and Price Risk indicator in the Hedge Accounting for Positions area. You define a Rate valuation for forward exchange transaction (006) procedures, which gets the Do not Execute in the Case of Hedge Accounting indicator. Now you assign the needed valuation procedures for designated subpositions and different valuation procedures for the freestanding subpositions to the positions management procedure. Assign the valuation procedure as steps to the positions management procedure in the following sequence: Position Management Procedure for Hedging Instruments\|| |


Customizing Activity Use Activities

Valuation Procedure

Exec.Solely in Case of Hedge Accounting Indicator

Do Not Execute in Case of Hedge Accounting Indicator

- 2. Security Valuation HEDGE

X -

- 3. Security Valuation FREE


- X

Assign Position Management Procedure

Assign the new defined position management procedures to the product types for exposure subitems and to product types of your FX transactions used as hedging instruments.

Define Hedge Accounting Calculation Types

You use this Customizing activity to define hedge accounting calculation types.

The hedge accounting calculation type controls the creation of the hypothetical derivatives, the decomposition of the market rate components, and the creation of the market value components. For more information, see Hedge Accounting Key Figuresand Hypothetical Derivative (Hedge Accounting for Exposure Items).

In the Define Hedging Profiles Customizing activity, you can assign hedge accounting calculation types to hedging profiles corresponding to the scenarios for Hedge Management and Accounting of Net Open Exposures.

- 1. Choose New Entries.
- 2. Enter a 4-digit ID for the h
- 3. Choose whether the lead currency is the From-Cur process of Hedge Manage Open Exposures.


**Note:**

Leading and following cu Customizing, under Tr

Transaction Manager Transaction Manageme


.


Example:

For the currency p EUR as the leadin following currency

You have created exchange 1,000,0 and you have acti relevant hedging a

Leading c

The hypot nominal o amount w contract r the basis compone

Following

The hypot nominal o amount w contract r

|Customizing Activity|Use|Activities|
|---|---|---|
| | |4. Choose the Spot Rate Us This setting controls whic calculations performed w hedging relationship. 5. In the FX Options: NPV O how you want to handle th Options. 6. In the Discounting of Elem whether the elements cal are discounted or not. 7. In the Hypothetical Der. F how the system calculate creation of hypothetical d relationships. The followin Yield Curve The theoretical fo the yield curves o Swap Rate The forward rate i spot rate and the relevant swap rate Rate Curve Struc Curve Structure t According to Eval The system behav the value of the se chosen in the eva case of the valuat Currency Conver curve is used. In c Currency Conver method), the swa From Financial Tra The forward rate i transaction. For FX options, the system 8. In the Market Value Com control the calculation of **Note:** For FX options as hedgin adjustment for the hypo or discounted forward r intrinsic value is calcula value calculation with th Count Basis indicator in Evaluation Control tab|


|Customizing Activity|Use|Activities|
|---|---|---|
| | |hedging instruments and hedging relationships. Th Complete The market value into four compon Spot, refle the FX spo valuation. discounte Forward, r in the FX f and valua CCBS, refl currency value. Others, re for examp The system calcu Others Element. The market value three component Intrinsic v between s Time valu changes i volatility o CCBS, refl currency value. Simple The market value into two compone Spot, refle the FX spo valuation. discounte Forward, r the spot c value. The system only c The market value two components: Intrinsic v between s|


|Customizing Activity|Use|Activities|
|---|---|---|
| | |Time valu changes i volatility o Use Use the setting Co separation of all r market value com Use the setting Si your needs, and y data (for example spreads). 9. Hypothetical Derivative F This setting controls how information during the cre for hedging relationships. available: None No fixing informat instrument. There for a non-delivera From Non-Deliver The fixing date an from the non-deliv hedging instrume an NDF is an NDF From FX Forwards If the hedg deliverabl settlemen non-delive derivative If the hedg with a due hedging a to the due result, the a non-deli hedging in This setting is relevant du present value of the hypo relevant evaluation type o **Note:** The calculation of the N market value of FX optio separate setting in the h type (FX Options: NPV O|


|Customizing Activity|Use|Activities|
|---|---|---|
| | |Valuation Method is set t Discounting and in additi Consider Fixing Date and If this is the case, the curr rate at the fixing date. 10. FX Option: Dates of Hypo This setting controls, how derivative are determined hedging instruments. The following dates: Start Date The start date of t designation date. Exercise Date If no shifts are defi exercise date of th exercise date of th Value Date Due date of the un instrument. If a due date shift or a pay period for the hypothetica the hedging area, the exe the hypothetical derivativ a combination, the due da payment term shift afterw this field, the exercise dat hypothetical derivative ar ways: Default The due date shif date or the value on the setting Dat for FX Option in t shift is applied to hypothetical deriv parallel by the sam Exception: If the r the underlying an designated into th exercise date is no Shift Only Value D The exerc derivative Shift of th derivative|


|Customizing Activity|Use|Activities|
|---|---|---|
| | |If th va de wa If th th sh ex Ex va ex th in 11. Enter a long name for the type. 12. Save your entries. The setting has two effect The hedging instr currency is taken derivative. The hy the to-currency is forward rate of th For FX forwards a calculation of elem components requ contract rate F. Th contract rate is us This setting has t satisfies the equa N_f are the hedgin currency and from|
|Define Critical Term Type|If you want to use a critical term match method for prospective effectiveness tests, you must define a critical term type. In the critical term type, you define which terms are to be checked during the effectiveness test. You can choose the following terms: Nominal Currency Start date For this date, you can define how many deviant days are allowed between the hedged item and hedging instrument values. Due date For this date, you can define how many deviant days are allowed between the hedged item and hedging instrument values.| |


|Customizing Activity|Use|Activities|
|---|---|---|
|Effectiveness Test Method|If you want to activate effectiveness testing, you need to define an effectiveness test method. You can either define an effectiveness test|**Note:**|
| |method with Eff.Test Method Category 22 Linear Regression with MDS or|You must assign the effe|
| |with Eff.Test Method Category 31 Critical Term Match Method.|hedging profile under D|
| |Linear regression|some additional setting effectiveness testing.|
| |If you want to activate effectiveness testing using linear regression, you need to define an effectiveness test method with Eff.Test Method Category 22 Linear Regression with MDS.|In addition, you must de assign them to the hedg Accounting II tab the m|
| |Eff. Test Method Category: Only 22 Linear Regression with MDS is supported. Offset Calculation Category: 02 (Cumulative) Market Data Calc. Logic: For effectiveness test method category 22 choose the market data calculation logic 2|along with the hedging p company code, valuatio classification. During the creation of a data set is included in th|
| |Market Data Scenario.| |
| |Linear Regression Method| |
| |Set to Effective If All Points Are Zero indicator| |
| |If you set this indicator, the result of the| |
| |effectiveness test is set to Effective, if all points| |
| |required for the linear regression have been| |
| |calculated successfully, but they are all zero. The| |
| |linear regression cannot be applied.| |
| |Example:| |
| |If the designated component for an FX option is the| |
| |intrinsic value and the FX option is out of the money| |
| |(that is, the intrinsic value is equal to zero) for the| |
| |current market as well as for all market data| |
| |constellations given by the market data set, all| |
| |calculated delta values are zero. If this applies to| |
| |both the hedging instrument as well as to the| |
| |hypothetical derivative, all points for the linear| |
| |regression are zero.| |
| |Within the settings for the linear regression method| |
| |choose the Assessment Method 1 Independent.| |
| |Define which of the parameters R2, Intercept Ratio,| |
| |Slope and the t-statistics you want to check and| |
| |enter the values for effectiveness.| |
| |When the calculated values lie within the entered| |
| |ranges, the hedging relationship is effective.| |
| |Examples:| |
| |The coefficient of determination R2| |
| |measures the variability in a data set that is| |
| |accounted for by a statistical model. R2 is an| |
| |element of [0,1].| |
| |When the variability is low, R2 is near| |
| |to 1.| |


|Customizing Activity|Use|Activities|
|---|---|---|
| |When the variability is high, R is near to 0. Therefore R indicates the quality of the linear fit. When the value is 1, it means perfect fit. The slope of a straight line is given by the ratio of the vertical distance and the horizontal distance of two points on the line. The measured slope of the line obtained from the linear regression within the effectiveness test is a measure of the effectiveness. If effectiveness is perfect, the slope is -1. An interval is defined for the slope by specifying a minimum slope and a maximum slope. If the measured slope falls within the interval, the hedging relationship is effective; otherwise the hedging relationship is ineffective. Critical Term Match Method If you want to activate effectiveness testing using critical term match method, you need to define an effectiveness test method with Eff.Test Method Category 31 Critical Term Match Method and choose Cumulative in the field Offset Calculation Category. In the area Prospective Effectiveness Test Details area make the following settings: Date Generation Logic Choose End Date of Hedging Relationship (1 Test Period). This will take the end date of a hedging relationship as the end date of the period. Test Start Date The effectiveness test start date is the date on which the prospective effectiveness test begins. Choose Start Date of Hedging Relationship. Critical Term Type Enter the relevant critical term type. 2 2| |
|Define Hedging Profiles|A hedging profile is assigned to each hedging relationship in the Manage Hedging Relationships function (transaction TPM100) on the Hedging Relationship Details tab in the Risk and Profile area. In a hedging profile, you define which scenario is valid for the hedging relationship, which test plan category is used, and which hedge accounting calculation type is applied. **Note:** In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the first-day valuation result of the hedging instrument. When this indicator is set, the|**Example:** 1. Choose New Entries 2. Assign a three-characte profile. 3. Choose scenario 920. 4. Define the rhythm for th Monthly Quarterly|


|Customizing Activity|Use|Activities|
|---|---|---|
| |valuation is skipped during the release of hedging business transactions|Annually|
| |if the designation date is the same as the contract date.|Manually|
| |The elements and components are still calculated and stored in the market data container on the designation date. On the designation date,|5. Set the Skip Valuation a|
| |however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.|6. Set the Intrinsic Value = for hedging profiles with|
| |Exception: For an FX option with a premium that has been activated, in|Risk with Intrinsic, Tim|
| |classifications after the payment date of the premium, the calculated values for the elements and components are used as start values during classification (with the Run Classification app) and are not assumed to be 0.|7. Set the Skip Designatio 8. For the hedging profiles exposure items process |
| | |documentation is imple|
| |The Intrinsic Value = 0 at Contract Date indicator is relevant for hedging profiles with hedging scenario 943 CFH: FX Risk with|Handling area, you you activate the automatic c|
| |Intrinsic, Time + Premium Amort..|You do not set t|
| |The hedge accounting key figure for the intrinsic value (NPV_INTR)|Documentation|
| |is calculated according to the settings in the Hedge Accounting Calculation Type and stored in the market data container at|**Note:**|
| |designation date.|If you set the do|
| |If you set this indicator, the classification calculates with the intrinsic value (hedge accounting key figure NPV_INTR)|documentation designation.|
| |= 0 on contract date. Therefore the classification assumes the intrinsic value to be zero and adds the calculated intrinsic value stored in the market data container to the NPV_OTHERS component. Afterward the classification starts based on these new values. Note: The values in the market data container are not changed.|To complete the you have to assi predefined PDF PDF-Based Form The following pr|
| |If you do not set this indicator, the classification is based on the calculated hedge accounting key figures on contract|TR_F_T for FX tr|
| |date.|TR_F_T|
| |Example:|for FX op|
| | |TR_F_T|
| |Classification if Indicator Intrinsic Value = 0 at Contract Date is not set |Premium/ / Intrinsic / Time / Others|
| |9. Save your entries.| |
| |Book Value Value| |
| |Value| |
| |Values at designation 1,000 82.72 1,090.86 -| |
| |173.58| |
| |Values at 958.08 82.72 875.36 0| |
| |valuation/classification| |
| |Posting - 41.92 - 124.64| |
| |Classification if Indicator Intrinsic Value = 0 at Contract Date is set| |
| |Premium/ / Intrinsic / Time / Others| |
| |Book Value Value| |
| |Value| |


Customizing Activity Use Activities

Premium/

Intrinsic Value

Time Value

Others

Book Value

Values at designation 1,000 0 1,090.86 90.86

Values at valuation/classification

958.08 82.72 875.36 0

Posting - 41.92 82.72 - 41.92

You can also select the Skip Designation checkbox to prevent the automated designation of an FX transaction into a hedging relationship if the calculated balance sheet recognition date is earlier than or on the same date as the designation date of an FX transaction.

When you set the Apply Critical Term Match attribute to Critical term match is set automatically. the rules

for the calculation of the cost of hedging reserve amounts are overwritten.

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedging business transactions is set to Actual Value = Aligned Value.

At classification, the delta amount of the NPV of the actual value of the hedging relationship is posted to the cost of hedging reserve.

If you want to designate the spot transaction created during the exercise of an FX option also in the existing hedging relationship, you must assign a second hedging profile in the Profile Underlying field, which is needed to find the relevant hedge accounting rule for the spot transaction.

To activate the effectiveness testing for the hedging profile, the Test Plan Category must not be set to 2 Effectiveness Testing is Disabled.

In addition, you must assign a prospective effectiveness test method with Eff.Test Method Category 22 Linear Regression with MDS or with Eff.Test Method Category 31 Critical Term Match Method in the Prosp. Eff. Method field, to complete settings for effectiveness testing. Leave the field empty, if you do not want to use effectiveness testing.

In the Documentation Handling area, you can make the relevant settings to activate the automatic creation of the documentation of the hedging relationships.

You also need to make settings in the document management system to enable the process. For more information, see Customizing Settings in DMS for TRM Documents.

Assign Update Types for Business Transactions (P-HA) to Product Types

You use this activity to assign update types to the following business transactions:

Designation

The following update types need

- THX001 Designate units/nomina
- THX002 Designate units/ nomina


|Customizing Activity|Use|Activities|
|---|---|---|
| |Dedesignation Classification for for collar FX options Reset Classification Reclassification Rollover Reclassification In case of the reclassification, update types with or without reset procedure are available. Swap Transfer The update types for the swap transfer are relevant for the creation of incoming and outgoing transfer flows. Alternative Hedging Reclassification Dedesignation Transfer This business transaction is needed during the execution of an FX option used as hedging instrument, when you decided to designate the underlying FX transaction into the existing hedging relationship. For more information, see Exercise of FX Option. Designation Transfer This business transaction is needed during the execution of an FX option used as hedging instrument, when you decided to designate the underlying FX transaction into the existing hedging relationship. For more information, see Exercise of FX Option. Prerequisite You must define the update types under Define and Assign Update Types.|THX003 Dedesignate units/ nom THX004 Dedesignate units/ nom THX005 Classification THX006 Reset Classification THX007 Rollover: Transfer design THX008 Rollover: Transfer design THX009 Hedging Reclassification THX010 Swap Transfer Incoming THX011 Swap Transfer Incoming THX012 Swap Transfer Outgoing THX013 Swap Transfer Outgoing THX014 Alternative Hedging Rec THX015 Transfer Designation (po THX016 Transfer Designation (ne THX017 Transfer Dedesignation ( THX018 Transfer Dedesignation |
|Accounting| | |
|Assign Update Types for Derived Business Transactions|You use this Customizing activity to assign the update types needed for classification. These update types are required for flows that are created when valuation results for a position within a hedging relationship are classified, in order to determine the effective and ineffective part of these valuation results. On the Classification tab, you assign the update types (for positive and also for negative amounts) for the classification and reclassification for the different position components. The following position components are affected by classification: 1324 Effective / Hedging Reserve 1322 Effective / Cost of Hedging Reserve 1323 Ineffect. / Hedging Reserve TPL 1333 Ineffect. / Cost of Hdg. Res. TPL 1303 Ineffective| |


|Customizing Activity|Use|Activities|
|---|---|---|
| | |Post Positive Amounts / Post Negative Amounts: Spot Valuation in Purchase Currency (946) (948); Spot Valuation in Sale Currency (950) (952); Security Valuation (958) (960)|
| |1343 P&L Eff. / Designated Components 1344 P&L Eff. / Non-Designated Comp. 1345 Amortization / Non-Designated Comp. Affected position management categories: 005 FX Transactions 007 OTC Derivatives (posting to underlying) On P-Hedge Accounting: Transfer Between Subposition tab, you need to enter udate types in the transfer the Hedge Adjustment component to Valuation Components: You find this activity in Customizing for Treasury and Risk Management under Transaction Manager General Settings Accounting Derived Business Transactions Update Types Assign Update Types for Derived Business Transactions .\|| |
|Alternative Update Types for Position Outflows|You use this Customizing activity to replace update types for derived business transactions with alternative update types based on certain conditions. In the hedge accounting solution, you can maintain alternative update types to allow reclassification postings to different G/L accounts after the balance sheet recognition date. The following alternative update types exist for this use case: Reclassification after Balance Sheet Recognition Update types of reclassification flows that are created after the balance sheet secognition date are replaced. Immediate Reclassification at Dedesignation Assign additional update types for premature dedesignation after balance sheet recognition date. If a dedesignation request is triggered after the balance sheet recognition date, the calculated amounts that were already reclassified at the balance sheet recognition date must be reset and posted to the P/L account relevant for premature dedesignation. Overview Reclassification Update Types and Alternative Reclassification Update Types relevant for Premature Dedesignation after Balance Sheet Recognition Date|1. Choose New Entries. 2. Specify the following: Position Managem Old Update Type Condition New Update Type 3. Save your entries. |


Old Udate Type

Description New Update Type

Description

- DBT_K031 Reclassification Effective / Hedging Reserve (positive)

DBT_KB31 Im. Dedesignation Recl. Hedging Reserve (positive)

- DBT_K032 Reclassification Effective / Hedging Reserve (negative)

DBT_KB32 Im. Dedesignation Recl. Hedging Reserve (negative)

- DBT_K033 Reclassification Effective / Cost of Hedg. Res. (positive)

DBT_KB33 Im. Dedesignation Recl. Cost of Hedg. Res. (positive)

- DBT_K034 Reclassification Effective / Cost of Hedg. Res. (negative)

DBT_KB34 Im. Dedesignation Recl. Cost of Hedg. Res. (negative)

- DBT_K035 Reset Reclassification Eff. / Hedging Reserve (positive)

DBT_KB35 Im. Dedesignation Recl. Reset Hedging Reserve (positive)

- DBT_K036 Reset Reclassification Eff. / Hedging Reserve (negative)

DBT_KB36 Im. Dedesignation Recl. Reset Hedging Reserve (negative)

- DBT_K037 Reset Reclassification Eff. / Cost of Hedg. Res. (positive)

DBT_KB37 Im. Dedesignation Recl. Reset Cost of Hedg. Res. (positive)

- DBT_K038 Reset Reclassification Eff. / Cost of Hedg. Res. (negative)


DBT_KB38 Im. Dedesignation Recl. Reset Cost of Hedg. Res. (negative)

Reclassification at Balance Sheet Recognition

Update types of reclassification flows that are created due to a dedesignation triggered by a dedesignation request before the balance sheet recognition date are replaced and posted at balance sheet recognition date for hedging relationships if in the hedging area on Hedge Accounting I tab in the Consider Balance Sheet Recognition Date field the Immediate Reclassification at Balance

|Customizing Activity|Use|Activities|
|---|---|---|
| |Sheet Recognition Date value is set and you have chosen Planned Reclassification in the Reclassification Handling field in the dedesignation request. You find this activity in Customizing for Treasury and Risk Management under Transaction Manager General Settings Accounting Derived Business Transactions Update Types Alternative Update Types for Position Outflows .| |
|Link to Other Accounting Components| | |
|Define Account Assignment Reference Determination (Exposure Item)|You use this Customizing activity to define rules for the automatic determination of account assignment references for parallel valuation areas. You define the rules for each product group, in this case Exposure Item and the financial transactions used as hedging instruments. You find this activity in Customizing for Treasury and Risk Management, under Transaction Manager General Settings Accounting Link to Other Accounting Components . **Note:** The hedging classification is available as characteristic. So, you can assign different account assignment references dependent on the specific hedging classifications. This allows the determination of different account assignment references, for different hedging categories, such as cash flow hedges and fair value hedges.|1. In the maintenance view, determining the account respective product group The rule can involve vario A step can consist of a de 2. Define a derivation rule a. Choose Create St Derivation Rule a b. Enter a text for th c. On the Definition to use to control t allocation in the S Target Fields sect assignment refere d. You can enter con rule on the Condit e. The settings on th supported. f. You now have to a references to the this, choose Main In the table that fo assignment refere field values. The fi source field that y column the secon column contains t Reference target relevant values fro **Example:** Source field: Pro Target field: Acc The table then appears Source Field|


Product Type

91A

3. Define Assignment

- a. Choose the Creat Assignment in th entry.
- b. Enter a text for th
- c. On the Definition can either choose is then written to field (in this case, must correspond assignment refere the account assig Constant field.
- d. On the Condition assignment depe condition.
- e. Select AA_REF (A as the target field


**Settings for Hedge Accounting in Hedging Area**

Hedging Area: Main Data

- Hedging Area: Hedge Accounting I

- Hedging Area: Hedge Accounting II

###### Valuation and Classification Results at Term End for FX Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Settings for Hedge Accounting for Exposure Items > Valuation and Classification Results at Term End for FX Transactions | L6 | trm09 p.32 | loio `77bf37014ddb48d69a466cb792b923b2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/77bf37014ddb48d69a466cb792b923b2.html?locale=en-US)

**Use**

At the term end of a foreign exchange transaction, flows can be created to split the realized gain/loss into its individual valuation and classification components:

Security Valuations Result (Freestanding Position)

Classification Results: Effective/Hedging Reserve until Balance Sheet Recognition Date

Classification Results: Effective/Hedging Reserve from Balance Sheet Recognition Date

Classification Results: Ineffective/Hedging Reserve TPL until Balance Sheet Recognition Date

Classification Results: Ineffective/Hedging Reserve TPL from Balance Sheet Recognition Date

Classification Results: Effective/Cost of Hedging Reserve until Balance Sheet Recognition Date

Classification Results: Effective/Cost of Hedging Reserve from Balance Sheet Recognition Date

Classification Results: Ineffective/Cost of Hedging Reserve TPL until Balance Sheet Recognition Date

Classification Results: Ineffective/Cost of Hedging Reserve TPL from Balance Sheet Recognition Date

Classification Results: Ineffective until Balance Sheet Recognition Date

Classification Results: Ineffective from Balance Sheet Recognition Date

**Activation/Deactivation and Update Types (Customizing)**

The activation or deactivation is based on the parameters company code, valuation area, product category, product type and hedging classification level. Initial values are permitted and apply for all characteristics of the individual parameters. The related customizing can be found in the IMG under Treasury and Risk Management Transaction Manager

General Settings Hedge Accounting for Positions Settings for Automated Designation of Exposure Items (FX Risk) Control Flows for Valuation/Classification Results at Term End .

To include specified positions according to the selected differentiation criteria in the generation of term end-flows, you need to set the Included indicator.

If the Included indicator is set, positions are considered based on the specified differentiation criteria company code, valuation area, product category, product type, and hedging classification. Initial values are allowed and apply to all characteristics of the individual factors. If the Included indicator is not set, the specified positions are excluded. For more information, see the Customizing documentation and F1 help text.

**Example:**

In the following example, the functionality is active for all product categories, product types and hedging classifications within accounting code 001 and valuation area 001, except for the hedging classification HC1:

|Accounting Code|Valuation Area|Product Category|Product Type|Hedge Classification|Active/Inactive|
|---|---|---|---|---|---|
|0001|001| | | |X|
|0001|001| | |HC1|-|


Update Types:

There are dedicated update types to split the realized gain/loss its individual valuation and classification components. These update types do not change any position components and are therefore not position-relevant. You can find the corresponding customizing settings in the IMG under Treasury and Risk Management Transaction Manager General Settings Accounting Derived Business Transactions Update Types Assign Update Types for Derived Business Transactions . Choose the position management procedure of your OTC position. You assign the update types on the Classification tab.

Separate flows are generated for classification results before and after the balance sheet recognition date (BSRD). Update types of flows after balance sheet recognition date can be replaced with alternative update types (replacement condition Classification Results after Balance Sheet Recognition).

**Note:**

To enable this feature, the condition Classification Results after Balance Sheet Recognition has been made available in the Customizing activity Alternative Update Types for Position Outflows.

**Security Valuation and Classification Results at Term End for Designation Splitting**

If you choose to use designation splitting, you can generate n exposure subitems with different amounts and due dates within n different hedging relationships with the same financial transaction (derivative) as hedging instrument. Classification results at term end are calculated per each hedging relationship. Security valuation results at term end are calculated per each OTC transaction.

The exposure subitem carries the hedging reserve and cost of hedging reserve of the hedging instrument. At the due date of the exposure subitem the hedging reserve and cost of hedging reserve is reclassified. When you use the designation splitting you can achieve that the reclassification is split in different parts and done at different dates. You define the rules for designation splitting on the Hedge Accounting I tab in the hedging area master data. In the case of designation splitting, the classification results at term end will be calculated/posted per hedging relationship.

Example:

[figure TRM09-F005 - Calculation:]

Calculation:

FX Forward with Planned Dedesignation

The classification results are determined from the exposure subitem position at the time of dedesignation. Separate flows are generated for the classification results before and after the balance sheet recognition date.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|


|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B014/B013 Flow)|
|---|---|
|-|Hedge Adjustment|
|=|Security Valuation Result|


Example:

The following table reflects classification results before and after the balance sheet recognition date.

Up to the BSRD, the amounts of the incurred business transactions are displayed as a separate flow for each hedging relationship. At the time of classification, all these amounts are added up and displayed - using the corresponding update types - as classification result until BSRD. All other business transaction amounts are included in the classification result after BSRD.

|Hedging Relationship Number|Balance Sheet Recognition Date (BSRD)|Business Transaction Date|Business Transaction|Effectivity 1|Ineffectivity 1|Effectivity 2|Ineffectivity 2|Ineffect|
|---|---|---|---|---|---|---|---|---|
|18274|09/30/2023| | | | | | | |
| | |07/01/2023|Valuation/Classification|0|0|3.44|-0.25|-0.01|
| | |09/30/2023|Reclassification|0|0.01|17.53|-0.74|0.01|
| | |Classification|Results until BSRD|0|0.01|20.97|-0.99|0|
| | |10/10/2023|Dedesignation|0|0|2.43|-0.08|-5,345.9|
| | |Classification|Results after BSRD|0|0|2.43|-0.08|-5,345.9|
|18275|09/25/2023| | |0| | | | |
| | |07/01/2023|Valuation/Classification|0|-0.01|1.43|0.16|0.01|
| | |09/25/2023|Reclassification|0|0.01|7,3|0.51|0|
| | |Classfication|Results until BSRD|0|0|8.73|0.67|0.01|


|Hedging Relationship Number|Balance Sheet Recognition Date (BSRD)|Business Transaction Date|Business Transaction|Effectivity 1|Ineffectivity 1|Effectivity 2|Ineffectivity 2|Ineffect|
|---|---|---|---|---|---|---|---|---|
| | |10/10/2023|Dedesignation|0|0|1.8|-0.04|-2,672.9|
| | |Classification|Results after BSRD|0|0|1.8|-0.04|-2,672.9|
|18276|06/01/2023| | | | | | | |
| | |07/01/2023|Valuation/Classification|0|0|0.57|-0.04|0|
| | |10/10/2023|Dedesignation|0|0|3.33|-0.14|-890.99|
| | |Classification|Results after BSRD|0|0|3.9|-0.18|-890.99|


Classification Results at 10/10/2023; list of position flows:

|Update Type ID|Update Type|Amount|
|---|---|---|
|DT_UK107|Classification Result up to BSRD: Effect/Cost|8.73|
|DT_UK123|Classification Result up to BSRD: Ineff/Cost|0.67|
|DT_UK103|Classification Result up to BSRD: Ineffective Pos.|0.01|
|DT_K107|Classification Result from BSRD:|1.80|
|DT_K124|Classification Result from BSRD:|0.04|
|DT_K104|Classification Result from BSRD:|2,672.97|
|DT_UK107|Classification Result up to BSRD:|20.97|
|DT_UK121|Classification Result up to BSRD:|0.01|
|DT_UK124|Classification Result up to BSRD:|0.99|
|DT_K107|Classification Result from BSRD:|2.43|
|DT_K124|Classification Result from BSRD:|0.06|
|DT_K104|Classification Result from BSRD:|5,345.94|
|DT_K107|Classification Result from BSRD:|3.90|
|DT_K124|Classification Result from BSRD:|0.16|
|DT_K104|Classification Result from BSRD:|890.99|
|DB_K192|Classification Result (Term End): Security Valuation|127.33|


**FX Forward with Planned Reclassification (Net Dedesignation)**

The classification results are determined from the exposure subitem position at the time of dedesignation. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results before and after the balance sheet recognition date (BSRD). No classification result flows are generated for hedging relationships with a gross dedesignation.

If the transaction has been dedesignated both net and gross, no classification result flows are created for the gross dedesignated hedging relationships. The hedge adjustment of these hedging relationships is added to the security valuation result.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B014/B013 Flow)|
|---|---|
|-|Hedge adjustment of all hedging relationships|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|


**FX Forward with Immediate Reclassification (Gross Dedesignation)**

The classification results are determined from the exposure subitem position. For hedging relationships with a gross dedesignation there are no classification result flows generated. The hedge adjustment of these hedging relationships is added to the security valuation result. If the transaction has been dedesignated both net and gross, separate classification result flows are generated for the net dedesignated hedging relationships.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|


|Classification Result Flow|Calculation|
|---|---|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B014/B013 Flow)|
|---|---|
|-|Hedge adjustment of all hedging relationships|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|


**FX Forward with Cash Settlement**

The classification results are determined from the exposure subitem position. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results before and after the balance sheet recognition date. If the transaction has been dedesignated both net and gross, no classification result flows are created for the gross dedesignated hedging relationships. The hedge adjustment of these hedging relationships is added to the security valuation result.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


|Classification Result Flow|Calculation|
|---|---|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B013/B014 Flow)|
|---|---|
|-|Hedge Adjustment of all Hedging Relationships|
|+|Hedge Adjustment of all Hedging Relationships with Gross Dedesignation|
|=|Security Valuation Result|


**FX Forward Without Hedge Accounting**

For an FX forward transaction which is not designated into a hedging relationship, no classification result flows are generated.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B014/B013 Flow)|
|---|---|
|=|Security Valuation Result|


**Non-Deliverable Forward (NDF) with Planned Dedesignation**

The classification results are determined from the exposure subitem position at the time of dedesignation. Separate classification result flows are generated for the results before and after the balance sheet recognition date.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B014/B013 Flow)|
|---|---|
|-|Hedge adjustment of all hedging relationships|
|=|Security Valuation Result|


**Non-Deliverable Forward (NDF) Planned Reclassification (Net Dedesignation)**

The classification results are determined from the exposure subitem position at the time of dedesignation. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results before and after the balance sheet recognition date. For hedging relationships with a net dedesignation separate classification result flows are generated for the results before and after the balance sheet recognition date. If the transaction has been dedesignated both net or gross, no classification result flows are created for the gross dedesignated hedging relationships. The hedge adjustment of these hedging relationships is added to the security valuation result.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B014/B013 Flow)|
|---|---|
|-|Hedge adjustment of all hedging relationships|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|


**Non-Deliverable Forward (NDF) with Immediate Reclassification (Gross Dedesignation)**

The classification results are determined from the exposure subitem position at the time of dedesignation. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results until and from the balance sheet recognition date. For hedging relationships with a gross dedesignation, no classification result flows are generated.

The security valuation result is determined as follows:

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|


|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B034/B014 Flow)|
|---|---|
|-|Hedge adjustment of all hedging relationships|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|


**Non-Deliverable Forward (NDF) Without Hedge Accounting**

For a non-deliverable forward transaction that is not designated into a hedging relationship, no classification result flows are generated.

The security valuation result is determined as follows:

| |Gain/Loss (B013/B014 Flow)|
|---|---|
|=|Security Valuation Result|


**FX Option/Non-Deliverable Option (NDO) with Cash Settlement**

The classification results are determined from the exposure subitem position. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results before and after the balance sheet recognition date. If the transaction has been dedesignated both net and gross, no classification result flows are created for the gross dedesignated hedging relationships. The hedge adjustment of these hedging relationships is added to the security valuation result.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|


|Classification Result Flow|Calculation|
|---|---|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B001/B003 Flow)|
|---|---|
|+|OTC Position Component 1002 (Security Valuation)|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|


**FX Option/Non-Deliverable Option (NDO) with Expiration**

The classification results are determined from the exposure subitem position. For hedging relationships with a net dedesignation separate classification result, flows are generated for the results beore and after the balance sheet recognition date. If the transaction was dedesignated both, net and gross, no classification result flows are created for the gross dedesignated hedging relationships. The hedge adjustment of these hedging relationships is added to the security valuation result.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


|Classification Result Flow|Calculation|
|---|---|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B001/B003 Flow)|
|---|---|
|+|OTC Position Component 1002|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|


**FX Option with Physical Exercise**

For an option with a physical exercise, the valuation and classification results are deleted from the option and are recreated for the FX spot transaction.

[figure TRM09-F006 - For an option with a physical exercise, the valuation and classification results are deleted from the option and are recreated for the FX spot transaction.]

The classification results are determined from the exposure subitem position at the time of dedesignation. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results before and after the balance sheet recognition date. If the transaction has been dedesignated both, net and gross, no classification result flows are created for the gross dedesignated hedging relationships. The hedge adjustment of these hedging relationships is added to the security valuation result.

|Classification Result Flow|Calculation|
|---|---|
|Hedging Reserve up to BSRD|Position Components 1301+1324 with TRL Date <= BSRD|
|Cost of Hedging Reserve up to BSRD|Position Components 1322+1334 with TRL Date <= BSRD|


|Classification Result Flow|Calculation|
|---|---|
|Ineffective from Hedging Reserve Calculation up to BSRD|Position Component 1323 with TRL Date <= BSRD|
|Ineffective from Cost of Hedging Reserve Calculation up to BSRD|Position Component 1333 with TRL Date <= BSRD|
|Ineffective up to BSRD|Position Component 1303 with TRL Date <= BSRD|
|Hedging Reserve from BSRD|Position Components 1301+1324 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Cost of Hedging Reserve from BSRD|Position Components 1322+1334 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Hedging Reserve Calculation from BSRD|Position Component 1323 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from Cost of Hedging Reserve Calculation from BSRD|Position Component 1333 with TRL Date > BSRD and TRL Date <= Dedesignation Date|
|Ineffective from BSRD|Position Component 1303 with TRL Date > BSRD and TRL Date <= Dedesignation Date|


The security valuation result is determined as follows:

| |Gain/Loss (B013/B014 Flow)|
|---|---|
|-|Hedge adjustment of all hedging relationships|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|-|OTC Position Component 1001 (Purchase Value)|
|=|Security Valuation Result|


**FX Cylinder Option with Net-/Gross Dedesignation**

Before Exercise:

The classification results are determined from the exposure subitem position at the time of dedesignation. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results before and after the balance sheet recognition date. For hedging relationships with a gross dedesignation, no classification result flows are generated. The classification results are posted to the put transaction. No results are posted to the call transaction.

The security valuation result is determined as follows:

|+|OTC Position Component|
|---|---|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|


After Exercise:

For an option with a physical exercise, the valuation and classification results are created for the FX spot transaction. The classification results are determined from the exposure subitem position at the time of dedesignation. For hedging relationships with a net dedesignation, separate classification result flows are generated for the results before and after the balance sheet recognition date. For hedging relationships with a gross dedesignation, no classification result flows are generated.

The security valuation result is determined as follows:

| |Gain/Loss (B013/B014 Flow)|
|---|---|
|-|Hedge adjustment of all hedging relationships|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|-|OTC Position Component 1001 (Purchase Value)|


The security valuation result for the transaction which is expired is determined as follows:

| |Gain/Loss (B001/B003 Flow|
|---|---|
|+|OTC Position Component 1002|
|+|Hedge adjustment of all hedging relationships with gross dedesignation|
|=|Security Valuation Result|

###### P/L Offset of Net Open Exposures

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Settings for Hedge Accounting for Exposure Items > Valuation and Classification Results at Term End for FX Transactions > P/L Offset of Net Open Exposures | L7 | trm09 p.46 | loio `8936af9e6f2b4796a221004c4ab70167` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8936af9e6f2b4796a221004c4ab70167.html?locale=en-US)

SAP supports you in preventing a P/L extension and applying a P/L offset for it. To do this, you can use selected update types to clear affected P/L accounts using a general clearing account and then post the offsetting balance from the clearing account to the offset account.

Once you have activated the P/L offset function forHedgeAccounting for Net Open Exposures(for FX transactions and OTC options only), additional flows are created to offset profit and losses posted before or after a hedging relationship with profit and losses posted during the hedging relationship within a fiscal year.

If the function is activated, the system records all relevant P/L amounts per position component starting with the designation. Possible relevant P/L amounts at designation can beSecurityValuationamounts that take place in the same fiscal year due to a valuation at designation itself or a key date valuation before designation.

**Note:**

InFXHedgeAccounting, hedging instruments can have more than one hedging instrument, for example, for cylinder options or FX options with exercise. The hedge splitting can be set and the sum of a split can be less than 100 percent.

In contrast toFXHedgeAccounting, a hedging relationship inCommodity HedgeAccountingconsists of a hedging instrument and a hedged item, so that only one P/L offset per hedging relationship and dedesignation can be processed. The system only allows full designations (no hedge splitting).

In both,FXHedgeAccountingandCommodity HedgeAccounting, partial dedesignations with individual reclassification settings are not supported. In addition,SecurityValuationis the only valuation step that can be used.

**Customizing Settings**

The P/L offset settings can be found in the IMG under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions P/L Offset (Hedge Accounting for Net Open Exposures) :

- 1.Activate P/LOffset (HedgeAcct for Net Open Exposures)
- 2.Define UpdateTypes andAssign Usages
- 3.Assign UpdateTypes for P/LOffset


**Valuation Example**

The following example shows the valuation of an FX forward transaction for a net open exposure with a designation splitting of 60% and 40%. At designation, the FX forward is valued at +1,000 .

|FI Posting Date|Business Transaction|Valuation Amount|
|---|---|---|
|01/03/2023|Valuation at Designation|1,000|


During the hedging relationship, P/L-relevant classification amounts can occur, which are usually due to quarterly key date valuations with reset, for example, the classification amount is usually reset one day later. These are usually ineffective amounts, as effective amounts are not posted to P/L immediately, but to OCI. In this example, we assume a valuation/classification without reset.

|FI Posting Date|Business Transaction|Valuation Amount|
|---|---|---|
|1/3/2023|Valuation at Designation|1,000|
|30/3/2023|Classification Hedging Relationship 1 (90% Effective)|-6|
|30/3/2023|Classification Hedging Relationship 2 (90% Effective)|-4|


For hedging realationship 1, balance sheet recognition date reached at 10/4/2023:

|FI Posting Date|Business Transaction|Valuation Amount|
|---|---|---|
|1/3/2023|Valuation at Designation|1,000|
|30/3/2023|Classification Hedging Relationship 1 (90% Effective)|-6|
|30/3/2023|Classification Hedging Relationship 2 (90% Effective)|-4|
|10/4/2023|Reclassification Hedging Relationship 1|-54|


|Flow Number|Business Transaction Category|FI Posting Date|State|Hedging Instrument Position OID|Hedge Item Position OID|Security Valuation|Ineffective|Effective Through Profit and Loss (TPL)|
|---|---|---|---|---|---|---|---|---|


|Flow Number|Business Transaction Category|FI Posting Date|State|Hedging Instrument Position OID|Hedge Item Position OID|Security Valuation|Ineffective|Effective Through Profit and Loss (TPL)|
|---|---|---|---|---|---|---|---|---|
|1|9040 Designation|01/03/2023|Internal|HINSTPOS_1|HITEMPOS_1|600| | |
|2|9040 Designation|01/03/2023|Internal|HINSTPOS_1|HITEMPOS_2|400| | |
|1|9042 Classification|30/03/2023|Internal|HINSTPOS_1|HITEMPOS_1| |-6| |
|1|9042 Classification|30/03/2023|Internal|HINSTPOS_1|HITEMPOS_2| |-4| |
|1|9046 Reclassification|10/4/2023|Internal|HINSTPOS_1|HITEMPOS_1| | |-54|


**The P/L offset starts, when a net or gross dedesignation is executed. At net dedesignation, effective and ineffective amounts are not part of the P/L offset. In the example, a gross dedesignation takes place:**

|FI Posting Date|Business Transaction|Valuation Amount|
|---|---|---|
|1/3/2023|Valuation At Designation|1,000|
|30/3/2023|Classification Hedging Relationship 1 (90% Effective)|-6|
|30/3/2023|Classification Hedging Relationship 2 (90% Effective)|-4|
|10/4/2023|Reclassification Hedging Relationship 1|-54|
|15/4/2023|Gross Dedesignation Hedging Relationship 1 (90% Effective)|-72|
|15/4/2023|Gross Dedesignation Hedging Relationship 2 (90% Effective)|-48|


|Flow Number|Business Transaction Category|FI Posting Date|State|Hedging Instrument Position OID|Hedged Item Position OID|Security Valuation|Ineffective|Effective Through P/L (TPL)|
|---|---|---|---|---|---|---|---|---|
|1|9040 Designation|03/01/2023|Internal|HINSTPOS1|HITEMPOS_1|600| | |
|2|9040 Designation|03/01/2023|Internal|HINSTPOS1|HITEMPOS_2|400| | |
|1|9042 Classification|03/30/2023|Internal|HINSTPOS1|HITEMPOS_1| |-6| |
|1|9042 Classification|03/30/2023|Internal|HINSTPOS1|HITEMPOS_2| |-4| |


|Flow Number|Business Transaction Category|FI Posting Date|State|Hedging Instrument Position OID|Hedged Item Position OID|Security Valuation|Ineffective|Effective Through P/L (TPL)|
|---|---|---|---|---|---|---|---|---|
|1|9090 Reclassification|04/10/2023|Internal|HINSTPOS1|HITEMPOS_1| | |-54|


|Flow Number|Business Transaction Category|FI Posting Date|State|Hedging Instrument Position OID|Hedged Item Position OID|Security Valuation|Ineffective|Effective through Profit and Loss (TPL)|P/L Offset|Cle (Off|
|---|---|---|---|---|---|---|---|---|---|---|
|1|9040 – Designation|1/3/2023|Internal|HINSTPOS_1|HITEMPOS_1|600,00| | | | |
|2|9040 Designation|1/3/2023|Internal|HINSTPOS_1|HITEMPOS_2|400,00| | | | |
|1|9042 – Classification|30/3/2023|Internal|HINSTPOS_1|HITEMPOS_1| |-6,00| | | |
|1|9042 – Classification|30/3/2023|Internal|HINSTPOS_1|HITEMPOS_2| |-4,00| | | |
|1|9046 – Reclassification|10/4/2023|Internal|HINSTPOS_1|HITEMPOS_1| | |-54,00| | |
|1|9041 9041 Dedesignation|15/4/2023|Internal|HINSTPOS_1|HITEMPOS_1| |-7,20| | | |
|1|9041 9041 Dedesignation|15/4/2023|Internal|HINSTPOS_1|HITEMPOS_2| |-4,80| | | |
|1|9090 – P/L Offset|15/4/.2023|Posted|HINSTPOS_1|HITEMPOS_1|-600,00| | | |60|
|2|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_1| |6,00| | |-6,|
|3|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_1| | |54,00| |-54|
|4|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_1| |7,20| | |-7,2|
|5|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_1| | | |532,80|-53|
|6|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_2|-400,00| | | |40|
|7|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_2| |4,00| | |-4,|
|8|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_2| |4,80| | |-4,|


|Flow Number|Business Transaction Category|FI Posting Date|State|Hedging Instrument Position OID|Hedged Item Position OID|Security Valuation|Ineffective|Effective through Profit and Loss (TPL)|P/L Offset|Cle (Off|
|---|---|---|---|---|---|---|---|---|---|---|
|9|9090 – P/L Offset|15/4/2023|Posted|HINSTPOS_1|HITEMPOS_2| | | |391,20|-39|


At net dedesignation, effective amounts that are reclassified to P/L and ineffective amounts are not included in the P/L offset. At gross dedesignation, all P/L-relevant postings are considered. A P/L offset transaction (business transaction category 9090) is written that posts the relevant recorded P/L amounts of the current fiscal year to the clearing account. The balance is then cleared from the clearing account and posted to the P/L offset account. Separate accounts for P/L offset income and expense are considered.

|Flow Number|Business Transaction Category|FI Posting Date|State|Hedging Instrument Position OID|Security Valuation|Effective|Ineffective|P/L Offset|Clearing (Offset)|
|---|---|---|---|---|---|---|---|---|---|
|1|800|01/01/2023|Internal|HINSTPOS_1|1,000| | | | |
|1|9040|03/01/2023|Internal|HINSTPOS_1|200| | | | |
|1|9042|03/30/2023|Internal|HINSTPOS_1| | |-8| | |
|1|9041|04/15/2023|Internal|HINSTPOS_1| | |-24| | |
|1|9090|04/15/2023|Posted|HINSTPOS_1|-600| | | |600|
|3|9090|04/15/2023|Posted|HINSTPOS_1| | | |1,200|-1,200|


**Update Types**

The update types for the flows to be posted are read from the IMG activityAssign UpdateTypes for P/LOffset(customizing view THACAVV_DFT_ASSG).

**Note:**

The technical field name of the amount to be cleared has the same prefix as the field, the update type is read from. The update type is determined by matching prefix. Generally, there are three kinds of flows created:

Internal flows: These flows store relevant P/L amounts fromTreasury Ledger(TRL) transactions.

Offset flows: These flows represent the clearing of a P/L amount from a P/L account and posting to a temporary clearing/offset account. Offset flows are created from the point of time when a net or gross dedesignation takes place. For each P/L amount (Security Valuation, Reclassified Effective Amounts, Ineffective Amounts), a posting-relevant offset flow is created.

Appreciation flows: These flows clear the netted amount on the temporary clearing/offset account and post it to the appreciation/offset account.

###### Example: FX Forward/Gross Dedesignation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Settings for Hedge Accounting for Exposure Items > Valuation and Classification Results at Term End for FX Transactions > Example: FX Forward/Gross Dedesignation | L7 | trm09 p.50 | loio `4698d82b5a9b44d3aadc0747f2581f5e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4698d82b5a9b44d3aadc0747f2581f5e.html?locale=en-US)

Valuation-/Classification Results Before Hedging Relationship

|Transaction|Position|Position Component| |Amount|
|---|---|---|---|---|
|Valuation (TPM1)|OTC Position|1002|Security Valuation|50.000|


Valuation-/Classification Results During Hedging Relationship

|Transaction|Position|Position Component| |Amount|
|---|---|---|---|---|
|Valuation (TPM1)|OTC Position|1301|Hedge Adjustment|-10.000|
|Classification (TPM101)|Exposure Subitem Position|1302|Effective Hedging Reserve|0|
|Classification (TPM101)|Exposure Subitem Position|1323|Ineffective Hedging Reserve|-1.000|
|Classification (TPM101)|Exposure Subitem Position|1322|Effective Cost of Hedging Reserve|0|
|Classification (TPM101)|Exposure Subitem Position|1333|Ineffective Cost of Hedging Reserve|-2.000|


Flow for Forward Exchange Gain/Loss

|Update Type|Amount|
|---|---|
|DBT_B013 Foreign Exchange Gain|35.000|


Flows for Valuation-/Classification Results at Term End

If there’s a gross dedesignation, the complete economic result, means the cash settlement amount, should be posted as security valuation result. There should be no postings for ineffectiveness. In the Customizing activity Assign Alternative Update Types for Position Outflows, you can enter alternative update types for condition Gross Dedesignation. In this way, the update type can be overwritten with an update type which is not relevant for posting.

|Update Type|Calculation|Amount|
|---|---|---|
|DBT_K191 Security Valuation Results|= DBT_B013|35.000|
|DT_K122G Ineffective Hedging Reserve|= 1323|-1.000|


|Update Type|Calculation|Amount|
|---|---|---|
|DT_K124G Ineffective Cost of Hedging Reserve|= 1333|-2.000|


Postings for Valuation-/Classification Results at Term End

|Update Type|Account|Description|Amount|
|---|---|---|---|
|DBT_K191|220352|ER Valuation Income|35.000|
|DBT_K191|220551|ER Realization Income|-35.000|

###### Example: FX Forward/Net Dedesignation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Settings for Hedge Accounting for Exposure Items > Valuation and Classification Results at Term End for FX Transactions > Example: FX Forward/Net Dedesignation | L7 | trm09 p.52 | loio `f99b462dca214ced94ca2a5814c654e1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f99b462dca214ced94ca2a5814c654e1.html?locale=en-US)

Valuation-/Classification Results Before Hedging Relationship

|Transaction|Position|Position Component| |Amount|
|---|---|---|---|---|
|Valuation (TPM1)|OTC Position|1002|Security Valuation|50.000|


Valuation-/Classification Results During Hedging Relationship

|Transaction|Position|Position Component| |Amount|
|---|---|---|---|---|
|Valuation (TPM1)|OTC Position|1301|Hedge Adjustment|-10.000|
|Classification (TPM101)|Exposure Subitem Position|1302|Effective Hedging Reserve|-4.000|
|Classification (TPM101)|Exposure Subitem Position|1323|Ineffective Hedging Reserve|-1.000|
|Classification (TPM101)|Exposure Subitem Position|1322|Effective Cost of Hedging Reserve|-3.000|
|Classification (TPM101)|Exposure Subitem Position|1333|Ineffective Cost of Hedging Reserve|-2.000|


Flow for Forward Exchange Gain/Loss

|Update Type|Amount|
|---|---|
|DBT_B013 Foreign Exchange Gain|35.000|


Flows for Valuation-/Classification Results at Term End

|Update Type|Calculation|Amount|
|---|---|---|
|DBT_K191 Security Valuation Results|=(DBT_B013 – 1301)|45.000|
|DBT_K102 Effective Hedging Reserve|=1302|-4.000|
|DBT_K122 Ineffective Hedging Reserve|=1323|-1.000|
|DBT_K108 Effective Cost of Hedging Reserve|=1322|-3.000|
|DBT_K124 Ineffective Cost of Hedging Reserve|=1333|-2.000|


Postings for the Valuation-/Classification Results at Term End

|Update Type|Account|Description|Amount|
|---|---|---|---|
|DBT_K191|220352|ER Valuation Income|45.000|
|DBT_K191|220551|ER Realization Income|-45.000|
|DBT_K102|220453|Cost of Material Realization Expense|4.000|
|DBT_K102|220454|Cost of Material Valuation Expense|-4.000|
|DBT_K122|220455|Ineffective Hedging Reserve Realization Expense|1.000|
|DBT_K122|220456|Ineffective Hedging Reserve Valuation Expense|-1.000|
|DBT_K102|220453|Cost of Material Realization Expense|3.000|
|DBT_K102|220454|Cost of Material Valuation Expense|-3.000|
|DBT_K122|220455|Ineff. Cost of Hedging Reserve Realization Expense|2.000|
|DBT_K122|220456|Ineff. Cost of Hedging Reserve Valuation Expense|-2.000|

###### Overview Hedge Accounting Rules

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules | L5 | trm09 p.53 | loio `bf604b970dba458aa08b2a5beb85de47` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bf604b970dba458aa08b2a5beb85de47.html?locale=en-US)

Hedge Accounting Rules

The hedge accounting rule specifies how the hedged item and the hedging instruments are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. The hedge accounting rule also determines how the classification is calculated.

In the following table you get an overview of the market value and element components (see also Hedge Accounting Key Figures), the calculation methods, and position components relevant in the hedge accounting rules.

Overview Hedge Accounting Rules

|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|HA Rule 611 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT|NPV_SPOT|NPV_FORWARD NPV_CCBS|NPV_FORWARD NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 613 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT|NPV_SPOT|NPV_FORWARD NPV_CCBS NPV_OTHER|NPV_FORWARD NPV_CCBS NPV_OTHER| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | |release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 622 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT NPV_FORWARD|NPV_SPOT NPV_FORWARD|NPV_CCBS|NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |
|HA Rule 623 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT NPV_FORWARD|NPV_SPOT NPV_FORWARD|NPV_CCBS NPV_OTHER|NPV_CCBS NPV_OTHER| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 631 Fair Value Hedge Recognized Asset/Liability IFRS 9|NPV_SPOT NPV_FORWARD NPV_CCBS NPV_OTHERS|NPV_SPOT NPV_FORWARD|-|-| |Lower-ofTest|-| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|HA Rule 632 Cash Flow Hedge Recognized Asset/Liability IFRS 9|NPV_SPOT NPV_FORWARD NPV_CCBS NPV_OTHERS|NPV_SPOT NPV_FORWARD|-|-| |Lower-ofTest|-| |
|HA Rule 641 Fair Value Hedge Net Investment Hedge Recognized Asset/Liability Net Investment U.S. GAAP|NPV_SPOT|NPV_SPOT|NPV_FORWARD|NPV_FORWARD| |Actual Value|Actual Value| |
|HA Rule 642 Cash Flow Hedge Planned Forecast U.S. GAAP|NPV_SPOT|NPV_SPOT|NPV_FORWARD|NPV_FORWARD|ELEM_FWD|Actual Value|Actual Value| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |
|HA Rule 643 Cash Flow Hedge Planned Forecast U.S. GAAP|NPV_INTR|NPV_INTR|NPV_TIME NPV_OTHER|NPV_TIME|NPV_OTHER|Actual Value|Actual Value| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |
|HA Rule 650 Cash Flow Hedge Planned Forecast IFRS 9|NPV_INTR|NPV_INTR|NPV_TIME NPV_CCBS|NPV_TIME NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 651 Cash Flow Hedge Planned Forecast|NPV_INTR|NPV_INTR|NPV_TIME NPV_CCBS NPV_OTHER|NPV_TIME NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|IFRS 9| | | | | | |reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |


*To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing of the hedging profile. In this case, the result of the lower-of-test executed at the release of designation is set to Actual Value = Aligned Value.

From the above table you can see for the different hedge accounting rules which market value components and elements contribute to the designated components for hedging instrument and hypothetical derivative and the non-designated components for hedging instrument and hypothetical derivative. In addition, you can see whether and how an amorization takes place.

The valuation of the designated subpositions is a process with several steps, which is triggered automatically, for example, during the release of designation, FX swap transfer, reclassification and dedesignation or needs to be executed manually during periodend closing.

Calculate NPVs including Hedge Accounting Key Figures

- 1. Calculate the net present values (NPVs) and market value components (that is, spot, forward, CCBS, CVA/DVA) using Determine NPVs Including CVA and DVA (transaction TPM60CVA).

- 2. Set the following indicators on the selection screen:


**Note:**

This step is a prerequisite for key date valuation.

Derive Evaluation Parameters

This indicator ensures that the evaluation type and CVA type are derived automatically from the position management procedure.

Select Single OTC Transactions

This indicator ensures that the NPV of the financial transaction (such as an FX forward) is calculated.

Market Value Decomposition

This indicator ensures that the market value components are calculated.

For more information, see Hedge Accounting Key Figures.

- 3. You can see the relevant hedge accounting key figures - that is, the calculated components and elements for the hedging instrument and the hypothetical derivative - in the results list using the Hedge Accounting Key Figure button.


Execute Key Date Valuation

You carry out key date valuation (transaction TPM1) to valuate the financial transactions based on the previously calculated NPVs, and then transfer the results to Financial Accounting.

Depending on the settings you made in the position management procedure either a security valuation is executed for freestanding and designated subpositions or the designated subpositions and the freestanding subpositions are valuated differently.

See also: Settings for Hedge Accounting for Exposure Items

**Example:**

Security Valuation for Freestanding and Designated Subpositions

The security valuation calculates the Δ NPV of the treasury ledger position based on NPV values that were stored between the contract start date of the financial transaction and the key date of the valuation. The valuation calculates its Δ NPV as follows:

- 1. Δ NPV = NPV - NPV-1
- 2. Calculate the portion of the Δ NPV for the designated and for freestanding subpositions.


The valuation result is documented in the valuation log from which you can access the posting log that gives you an overview of the posted flows for each subposition. Postings are made to Financial Accounting.

The amounts relevant for the designated subpositions are posted against the hedge clearing account.

Asset position:

|Δ NPV > 0|Dr Asset, Cr Hedge Clearing|
|---|---|
|Δ NPV < 0|Dr Hedge Clearing, Cr Asset|


Liability position:

|Δ NPV < 0|Dr Hedge Clearing, Cr Liability|
|---|---|
|Δ NPV > 0|Dr Liability, Cr Hedge Clearing|


Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

The classification will distribute the component values of the exposure subitem according to the relevant hedge accounting rule to the designated and non-designated components of the exposure subitem.

**Note:**

The amounts relevant for the freestanding subpositions are posted to P&L.

**Example:**

Two-Step Valuation for Freestanding Subpositions and Security Valuation for Designated Subpositions

Valuation of Designated Subpositions

The security valuation for the designated subpositions calculates the Δ NPV of the treasury ledger position based on NPV values that were stored between the contract start date of the financial transaction and the key date of the valuation. The valuation calculates its Δ NPV as follows:

- 1. Δ NPV = NPV - NPV-1
- 2. Calculate the portion of the Δ NPV for the designated subpositions.


The valuation result is documented in the valuation log from which you can access the posting log that gives you an overview of the posted flows for each subposition. Postings are made to Financial Accounting. The designated subpositions are posted against the hedge clearing account.

Asset position:

|Δ NPV > 0|Dr Asset, Cr Hedge Clearing|
|---|---|
|Δ NPV < 0|Dr Hedge Clearing, Cr Asset|


Liability position:

|Δ NPV < 0|Dr Hedge Clearing, Cr Liability|
|---|---|
|Δ NPV > 0|Dr Liability, Cr Hedge Clearing|


Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

The classification will distribute the component values of the exposure subitem according to the relevant hedge accounting rule to the designated and non-designated components of the exposure subitem.

Valuation of Freestanding Subpositions

1. The system executes the rate valuation for FX transactions only for the freestanding subpositions (in order to calculate the spot effect). See also: Rate Valuation for Forward Exchange Transactions

2. The security valuation for the freestanding subpositions is executed for the freestanding subpositions (in order to calculate the interest effect). It takes the results of the rate valuation for FX transactions into account.

The valuation result is documented in the valuation log from which you can access the posting log that gives you an overview of the posted flows for each subposition. Postings are made to Financial Accounting. The freestanding subpositions are posted against P&L.

In general, the posting amount of the valuation result depends on the key date valuation procedure that was chosen:

With Reset:

The valuation result is posted at period end.

The posting is reset on the first business day after period end.

NPV-1 = NPV on contract start date of the financial transaction

Without Reset:

The valuation result is posted at period end.

NPV-1 = NPV at last period-end closing

Execute classification (transaction TPM101)

The classification splits the valuation result according to the hedge accounting rule into the position components, which reflect effective and ineffective amounts.

[figure TRM09-F007 - Overview of Classification]

Overview of Classification

Determine the effective and ineffective amounts of the hedging reserve

For the hedge accounting rules of IFRS 9, a lower-of test is executed for the designated components of the hedging instrument and the hypothetical derivative.

For the hedge accounting rules of U.S. GAAP, the designated components of the hedging instruments are relevant for the hedging reserve.

[figure TRM09-F008 - Hedging Reserve]

Hedging Reserve

Determine the effective and ineffective amounts of the cost of hedging reserve

The cost of hedging reserve is only relevant for hedge accounting rules for cash flow hedges with the hedged item category Planned Forecast.

IFRS 9

The calculation rule for the cost of hedging reserve is determined at the release of designation. The system compares the actual values and aligned values of the non-designated components and the result determines the calculation method for the hedging relationship.

[figure TRM09-F009 - The calculation rule for the cost of hedging reserve is determined at the release of designation. The system compares the actual values and aligned values of the non-designated components and the result determines the calculation method for the hedging relationship.]

Cost of Hedging Reserve (IFRS 9)

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in the Customizing settings for the hedging profile. In this case, the aligned value check result at the release of designation is set to Actual Value

= Aligned Value.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the first-day valuation result of the hedging instrument. When this indicator is set, the valuation is

skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Exception: For an FX option with a premium that has been activated, in classifications after the payment date of the premium, the calculated values for the elements and components are used as start values during classification (with the Run Classification app) and are not assumed to be 0.

U.S. GAAP

The non-designated components of the hedging instrument are relevant for the cost of hedging reserve (= Actual Value).

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the first-day valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Exception: For an FX option with a premium that has been activated, in classifications after the payment date of the premium, the calculated values for the elements and components are used as start values during classification (with the Run Classification app) and are not assumed to be 0.

Determine the effective and ineffective amounts of the amortization

Amortization is relevant for cash flow hedges when U.S. GAAP is applied.

Hedging Instrument FX Forward

The forward points (traded amount * swap rate at designation date) are amortized using straight-line amortization over the lifetime of the hedging instrument. This amortization is represented by the ELEM_FWD element of the hedging instrument.

**Example:**

[figure TRM09-F010 - Example for Hedge Accounting Rule 642]

Example for Hedge Accounting Rule 642

Hedging Instrument FX Option

The option premium is amortized using straight-line amortization over the lifetime of the hedging instrument. This amortization is represented by the NPV and NPV_OTHER component of the hedging instrument.

**Example:**

[figure TRM09-F011 - Example of Hedge Accounting Rule 643]

Example of Hedge Accounting Rule 643

**Related Information**

Release Hedging Business Transactions Period-End Closing Run Classification HA Rule 611 HA Rule 613

- HA Rule 622

- HA Rule 623


- HA Rule 631

- HA Rule 632


- HA Rule 641

- HA Rule 642

- HA Rule 643


- HA Rule 650

- HA Rule 651

###### HA Rule 611

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 611 | L6 | trm09 p.68 | loio `82882c5863352360e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/82882c5863352360e10000000a44147b.html?locale=en-US)

**Use**

The 611: Hdg Reserve: Spot/Cost of Hdg Reserve: Forward + CCBS hedge accounting rule is used in the following hedging scenario:

910 CFH: FX Risk with Spot, Forward + CCBS

**Features**

A hedge accounting rule specifies how a hedged item and the related hedge transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. A hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


In this hedge accounting rule, the spot component (NPV_SPOT) is used to calculate the hedging reserve, and the forward (NPV_FWD) and CCBS (NPV_CCBS) components are used to calculate the cost of hedging reserve.

In this hedge accounting rule, the calculation rule for the cost of hedging reserve is determined during the release of hedging business transactions and is based on the forward element (ELEM_FWD) and the CCBS element (ELEM_CCBS).

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

**Classification**

You use the Execute Classification function (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


The relevant calculation rules are described below.

Calculation of Hedging Reserve and Ineffective/Hedging Reserve TPL

The 1302 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot components (NPV_SPOT) of the hedging instrument and the hypothetical derivative.

[figure TRM09-F012 - Overview of Calculation Rule for Hedging Reserve]

Overview of Calculation Rule for Hedging Reserve

Calculation of Cost of Hedging Reserve and Ineffective/Cost of Hedging Reserve TPL

The 1322 Effective/Cost of Hedging Reserve and 1333 Ineffective/Cost of Hedging Reserve TPL components are calculated based on the forward (NPV_FWD) and the CCBS (NPV_CCBS) components.

At the time of release of the hedging business transactions, the actual and aligned values were calculated as follows:

Actual value = Forward + CCBS of Hedging Instrument

Aligned value = Forward + CCBS of Hypothetical Derivative

One of the following calculation rules for the cost of hedging reserve was determined:

- 1 - Actual Value = Aligned Value

The change in the amount of the actual value is posted to the cost of hedging reserve.

- 2 - Actual Value > Aligned Value

The change in the amount of the aligned value is posted to the cost of hedging reserve.

- 3 - Aligned Value > Actual Value


The cost of hedging reserve is determined based on the lower-of test. The smaller amount of the actual and aligned value is posted to the cost of hedging reserve and the remaining amount is posted to the P/L statement.

**Note:**

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profiles .

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedge business transactions is set to Actual Value = Aligned Value.

[figure TRM09-F013 - Overview of Calculation Rules for Cost of Hedging Reserve]

Overview of Calculation Rules for Cost of Hedging Reserve

Legend

|Abbreviation|Description|
|---|---|
|AC|Actual Value|
|AV|Aligned Value|
|CCBS|Cross-Currency Basis Swap|
|Fwd|Forward Transaction|
|HInst.|Hedging Instrument|
|Hyp. Der.|Hypothetical Derivative|
|Ineff. C./H.Res. TPL|Ineffective Cost of Hedging Reserve Through Profit or Loss|
|Eff. C/H.Res.|Effective Cost of Hedging Reserve|
|Eff. Amt|Effective Amount|


|Abbreviation|Description|
|---|---|
|Eff. H. Res.|Effective Hedging Reserve|
|Ineff. H.Res. TPL|Ineffective Hedging Reserve Through Profit or Loss|


During the classification, the relevant amounts for the hedging reserve, cost of hedging reserve, and P/L ineffective are calculated. The cost of hedging reserve amount is calculated according to the calculation rule that was determined during the release of hedge business transactions and is then posted to Financial Accounting (FI).

**Note:**

The remaining amount that is not posted to either the hedging reserve or the cost of hedging reserve components is posted to P/L ineffective component 1303 (Ineffective).

**More Information**

Hedge Accounting Key Figures

###### HA Rule 613

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 613 | L6 | trm09 p.72 | loio `da08eedc44894fb7a7e9d39c32bfbb8c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/da08eedc44894fb7a7e9d39c32bfbb8c.html?locale=en-US)

**Use**

The hedge accounting rule 613: Hdg Reserve: Spot/Cost of Hdg Reserve: Forward + CCBS + Others is used in the following hedging scenario:

913 CFH: FX Risk with Spot, Forward + CCBS + Others

**Features**

A hedge accounting rule specifies how a hedged item and the related hedge transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. A hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


In this hedge accounting rule, the spot component (NPV_SPOT) is used to calculate the hedging reserve, and the forward (NPV_FWD), CCBS (NPV_CCBS), and Others (NPV_OTHER) components are used to calculate the cost of hedging reserve.

In this hedge accounting rule, the calculation rule for the cost of hedging reserve is determined during the release of hedging business transactions and is based on the forward element (ELEM_FWD), the CCBS element (ELEM_CCBS), and the Others element (ELEM_OTHER).

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

**Classification**

You use the Execute Classification function (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

1303 - Ineffective

The relevant calculation rules are described below.

Calculation of Hedging Reserve and Ineffective/Hedging Reserve TPL

The 1302 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot components (NPV_SPOT) of the hedging instrument and the hypothetical derivative.

[figure TRM09-F014 - Overview of Calculation Rule for Hedging Reserve]

Overview of Calculation Rule for Hedging Reserve

Calculation of Cost of Hedging Reserve and Ineffective/Cost of Hedging Reserve TPL

The 1322 Effective/Cost of Hedging Reserve and 1333 Ineffective/Cost of Hedging Reserve TPL components are calculated based on the forward (NPV_FWD), the CCBS (NPV_CCBS), and the Others (NPV_OTHER) components.

At the time of release of the hedging business transactions, the actual and aligned values were calculated as follows:

Actual value = Forward + CCBS + Others of Hedging Instrument

Aligned value = Forward + CCBS + Others of Hypothetical Derivative

One of the following calculation rules for the cost of hedging reserve was determined:

- 1 - Actual Value = Aligned Value


The change in the amount of the actual value is posted to the cost of hedging reserve.

- 2 - Actual Value > Aligned Value

The change in the amount of the aligned value is posted to the cost of hedging reserve.

- 3 - Aligned Value > Actual Value


The cost of hedging reserve is determined based on the lower-of test. The smaller amount of the actual and aligned value is posted to the cost of hedging reserve and the remaining amount is posted to the P/L statement.

**Note:**

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profiles .

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedge business transactions is set to Actual Value = Aligned Value.

[figure TRM09-F015 - Overview of Calculation Rule for Cost of Hedging Reserve]

Overview of Calculation Rule for Cost of Hedging Reserve

Legend

|Abbreviation|Description|
|---|---|
|AC|Actual Value|
|AV|Aligned Value|
|CCBS|Cross-Currency Basis Swap|


|Abbreviation|Description|
|---|---|
|Fwd|Forward Transaction|
|HInst.|Hedging Instrument|
|Hyp. Der.|Hypothetical Derivative|
|Ineff. C./H.Res. TPL|Ineffective Cost of Hedging Reserve Through Profit or Loss|
|Eff. C/H.Res.|Effective Cost of Hedging Reserve|
|Eff. Amt|Effective Amount|
|Eff. H. Res.|Effective Hedging Reserve|
|Ineff. H.Res. TPL|Ineffective Hedging Reserve Through Profit or Loss|


During the classification, the relevant amounts for the hedging reserve, cost of hedging reserve, and P/L ineffective are calculated. The cost of hedging reserve amount is calculated according to the calculation rule that was determined during the release of hedge business transactions and is then posted to Financial Accounting (FI).

**Note:**

The remaining amount that is not posted to either the hedging reserve or the cost of hedging reserve components is posted to P/L ineffective component 1303 (Ineffective).

**More Information**

Hedge Accounting Key Figures

###### HA Rule 622

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 622 | L6 | trm09 p.76 | loio `0cee7a8a6cb74a35abdd14acdcbd5fe6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0cee7a8a6cb74a35abdd14acdcbd5fe6.html?locale=en-US)

- The hedge accounting rule 622: Hdg Reserve: Spot + Forward/Cost of Hdg Reserve: CCBS is used in the following hedging scenario:


920 CFH: FX Risk with Forward + Spot, CCBS

**Features**

A hedge accounting rule specifies how a hedged item and the related hedge transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. A hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


In this hedge accounting rule, the spot (NPV_SPOT) and forward (NPV_FWD) components are used to calculate the hedging reserve, and the CCBS (NPV_CCBS) component is used to calculate the cost of hedging reserve.

In this hedge accounting rule, the calculation rule for the cost of hedging reserve is determined during the release of hedging business transactions and is based on the CCBS element (ELEM_CCBS).

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

**Classification**

You use the Execute Classification function (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


The relevant calculation rules are described below.

Calculation of Hedging Reserve and Ineffective/Hedging Reserve TPL

The 1302 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot (NPV_SPOT) and forward (NPV_FWD) components of the hedging instrument and the hypothetical derivative.

[figure TRM09-F016 - Overview of Calculation Rule for Hedging Reserve]

Overview of Calculation Rule for Hedging Reserve

Calculation of Cost of Hedging Reserve and Ineffective/Cost of Hedging Reserve TPL

The 1322 Effective/Cost of Hedging Reserve and 1333 Ineffective/Cost of Hedging Reserve TPL components are calculated based on the CCBS (NPV_CCBS) component.

At the time of release of the hedging business transactions, the actual and aligned values were calculated as follows:

Actual value = CCBS of Hedging Instrument

Aligned value = CCBS of Hypothetical Derivative

One of the following calculation rules for the cost of hedging reserve was determined:

- 1 - Actual Value = Aligned Value

The change in the amount of the actual value is posted to the cost of hedging reserve.

- 2 - Actual Value > Aligned Value

The change in the amount of the aligned value is posted to the cost of hedging reserve.

- 3 - Aligned Value > Actual Value


The cost of hedging reserve is determined based on the lower-of test. The smaller amount of the actual and aligned value is posted to the cost of hedging reserve and the remaining amount is posted to the P/L statement.

**Note:**

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profiles .

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedge business transactions is set to Actual Value = Aligned Value.

[figure TRM09-F017 - Overview of Calculation Rule for Cost of Hedging Reserve]

Overview of Calculation Rule for Cost of Hedging Reserve

Legend

|Abbreviation|Description|
|---|---|
|AC|Actual Value|
|AV|Aligned Value|
|CCBS|Cross-Currency Basis Swap|
|Fwd|Forward Transaction|
|HInst.|Hedging Instrument|
|Hyp. Der.|Hypothetical Derivative|
|Ineff. C./H.Res. TPL|Ineffective Cost of Hedging Reserve Through Profit or Loss|
|Eff. C/H.Res.|Effective Cost of Hedging Reserve|
|Eff. Amt|Effective Amount|
|Eff. H. Res.|Effective Hedging Reserve|
|Ineff. H.Res. TPL|Ineffective Hedging Reserve Through Profit or Loss|


During the classification, the relevant amounts for the hedging reserve, cost of hedging reserve, and P/L ineffective are calculated. The cost of hedging reserve amount is calculated according to the calculation rule that was determined during the release of hedge business transactions and is then posted to Financial Accounting (FI).

**Note:**

The remaining amount that is not posted to either the hedging reserve or the cost of hedging reserve components is posted to P/L ineffective component 1303 (Ineffective).

**More Information**

Hedge Accounting Key Figures

###### HA Rule 623

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 623 | L6 | trm09 p.80 | loio `80fbc5bbec354b5f904817e513a8216c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/80fbc5bbec354b5f904817e513a8216c.html?locale=en-US)

**Use**

- The hedge accounting rule 623: Hdg Reserve: Spot + Forward/Cost of Hdg Reserve: CCBS + Others is used in the following hedging scenario


923 CFH: FX Risk with Forward + Spot, CCBS + Others

**Features**

A hedge accounting rule specifies how a hedged item and the related hedge transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. A hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve


1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


In this hedge accounting rule, the spot (NPV_SPOT) and forward (NPV_FWD) components are used to calculate the hedging reserve, and the CCBS (NPV_CCBS) and Others (NPV_OTHER) components are used to calculate the cost of hedging reserve.

In this hedge accounting rule, the calculation rule for the cost of hedging reserve is determined during the release of hedging business transactions and is based on the CCBS element (ELEM_CCBS) and the Others element (ELEM_OTHER).

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time

as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

**Classification**

You use the Execute Classification function (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


The relevant calculation rules are described below.

Calculation of Hedging Reserve and Ineffective/Hedging Reserve TPL

The 1302 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot (NPV_SPOT) and forward (NPV_FWD) components of the hedging instrument and the hypothetical derivative.

[figure TRM09-F018 - The 1302 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot (NPV_SPOT) and forward (NPV_FWD) components of the hedging instrument and the hypothetical derivative.]

Overview of Calculation Rule for Hedging Reserve

Calculation of Cost of Hedging Reserve and Ineffective / Cost of Hedging Reserve TPL

The 1322 Effective/Cost of Hedging Reserve and 1333 Ineffective/Cost of Hedging Reserve TPL components are calculated based on the CCBS (NPV_CCBS) and Others (NPV_OTHER) components.

At the time of release of the hedging business transactions, the actual and aligned values were calculated as follows:

Actual value = CCBS + Others of Hedging Instrument

Aligned value = CCBS + Others of Hypothetical Derivative

One of the following calculation rules for the cost of hedging reserve was determined:

- 1 - Actual Value = Aligned Value

The change in the amount of the actual value is posted to the cost of hedging reserve.

- 2 - Actual Value > Aligned Value

The change in the amount of the aligned value is posted to the cost of hedging reserve.

- 3 - Aligned Value > Actual Value


The cost of hedging reserve is determined based on the lower-of test. The smaller amount of the actual and aligned value is posted to the cost of hedging reserve and the remaining amount is posted to the P/L statement.

**Note:**

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profiles .

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedge business transactions is set to Actual Value = Aligned Value.

[figure TRM09-F019 - Overview of Calculation Rule for Cost of Hedging Reserve]

Overview of Calculation Rule for Cost of Hedging Reserve

Legend

|Abbreviation|Description|
|---|---|
|AC|Actual Value|
|AV|Aligned Value|
|CCBS|Cross-Currency Basis Swap|
|Fwd|Forward Transaction|
|HInst.|Hedging Instrument|
|Hyp. Der.|Hypothetical Derivative|
|Ineff. C./H.Res. TPL|Ineffective Cost of Hedging Reserve Through Profit or Loss|
|Eff. C/H.Res.|Effective Cost of Hedging Reserve|
|Eff. Amt|Effective Amount|
|Eff. H. Res.|Effective Hedging Reserve|
|Ineff. H.Res. TPL|Ineffective Hedging Reserve Through Profit or Loss|


During the classification, the relevant amounts for the hedging reserve, cost of hedging reserve, and P/L ineffective are calculated. The cost of hedging reserve amount is calculated according to the calculation rule that was determined during the release of hedge business transactions and is then posted to Financial Accounting (FI).

The remaining amount that is not posted to either the hedging reserve or the cost of hedging reserve components is posted to P/L ineffective component 1303 (Ineffective).

**More Information**

Hedge Accounting Key Figures

###### HA Rule 631

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 631 | L6 | trm09 p.85 | loio `19f39a17ca924a39aa799fdc7eb48c3e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/19f39a17ca924a39aa799fdc7eb48c3e.html?locale=en-US)

**Use**

The hedge accounting rule 631: P/L Effective: Spot + Forward + CCBS + Others is used in the following hedging scenario:

931 FVH: FX Risk with Full Fair Value

**Features**

The hedge accounting rule specifies how the hedged item and the hedging transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. The hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

1324 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1303 - Ineffective

In this hedge accounting rule, the spot component (NPV_SPOT), the forward (NPV_FWD), the CCBS (NPV_CCBS), and the Others (NPV_OTHERS) components are used to calculate the P/L effective amount.

The P/L effective amount is posted to position component 1324 (Effective / Hedging Reserve TPL). The position component 1302 (Effective / Hedging Reserve) is not used.

In this hedge accounting rule, no cost of hedging reserve is calculated.

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

**Classification**

You use the function Execute Classification (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

1324 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1303 - Ineffective

The relevant calculation rules are described below.

Calculation of the Effective and Ineffective Components Posted to Profit and Loss

The 1324 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot component (NPV_SPOT) + forward component (NPV_FWD) + CCBS component (NPV_CCBS)

+ Others component (NPV_OTHERS) of the hedging instrument and the hypothetical derivative.

[figure TRM09-F020 - Overview of Calculation Rule for Effective Amount]

Overview of Calculation Rule for Effective Amount

**Note:**

The remaining amount that is not posted to the hedging reserve components is posted to the P/L ineffective component 1303 Ineffective

**More Information**

Hedge Accounting Key Figures

###### HA Rule 632

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 632 | L6 | trm09 p.87 | loio `37018655ab454adb8c4c57125a34fef9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/37018655ab454adb8c4c57125a34fef9.html?locale=en-US)

**Use**

The hedge accounting rule 632: Hdg Reserve: Spot + Forward + CCBS + Others is used in the following hedging scenario:

932 CFH: FX Risk with Full Fair Value

**Features**

The hedge accounting rule specifies how the hedged item and the hedging instrument are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. The hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

- 1303 - Ineffective


In this hedge accounting rule, the spot component (NPV_SPOT), the forward (NPV_FWD), the CCBS (NPV_CCBS), and the Others (NPV_OTHERS) components are used to calculate the hedging reserve.

In this hedge accounting rule, no cost of hedging reserve is calculated.

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

**Classification**

You use the function Execute Classification (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

- 1303 - Ineffective


The relevant calculation rules are described below.

Calculation of Hedging Reserve and Ineffective/Hedging Reserve TPL

The 1302Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot component (NPV_SPOT) + forward component (NPV_FWD) + CCBS component (NPV_CCBS) + Others component (NPV_OTHERS) of the hedging instrument and the hypothetical derivative.

[figure TRM09-F021 - The 1302Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the spot component (NPV_SPOT) + forward component (NPV_FWD) + CCBS component (NPV_CCBS) + Others component (NPV_OTHERS) of the hedging instrument and the hypothetical derivative.]

Overview of Calculation Rule for Hedging Reserve

**Note:**

The remaining amount that is not posted to the hedging reserve components is posted to the P/L ineffective component 1303 Ineffective

**More Information**

Hedge Accounting Key Figures

###### HA Rule 641

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 641 | L6 | trm09 p.89 | loio `23c09f0e7b884698bc4bc9482ef9b0d4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/23c09f0e7b884698bc4bc9482ef9b0d4.html?locale=en-US)

The HA rule 641 Des. Comp.: Spot / Non-Des. Comp.: Forward is used in the following hedging scenario:

941: FVH: FX-Risk with Spot, Forward

990 NIH: FX-Risk with Spot, Forward

With this hedge accounting rule, the following occurs:

A change in the amount of the actual value of the spot component (NPV_SPOT) is posted to the P/L effective amount (designated components).

A change in the amount of the actual value of the forward component (NPV_FORWARD) is posted to the P/L effective amount (non-designated components).

###### HA Rule 642

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 642 | L6 | trm09 p.90 | loio `50864dd8a6234a698bea776121b7370a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/50864dd8a6234a698bea776121b7370a.html?locale=en-US)

The hedge accounting rule 642 Des. Comp.: Spot / Non-Des. Comp.: Fwd + Fwd Points Amort. is used in the following hedging scenario:

942: CFH: FX-Risk with Spot, Fwd + Fwd Points Amort.

With this hedge accounting rule, the following occurs:

A change in the amount of the actual value of the spot component (NPV_SPOT) is posted to the hedging reserve.

A change in the amount of the actual value of the forward component (NPV_FORWARD) and the amortization amount of the element ELEM_FORWARD are used to calculate the cost of hedging reserve.

[figure TRM09-F022 - A change in the amount of the actual value of the forward component (NPV_FORWARD) and the amortization amount of the element ELEM_FORWARD are used to calculate the cost of hedging reserve.]

###### HA Rule 643

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 643 | L6 | trm09 p.90 | loio `a51cb8777b3543bfb29ff4955c6f279c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a51cb8777b3543bfb29ff4955c6f279c.html?locale=en-US)

The HA rule 643 Des. Comp.: Intr. / Non-Des. Comp.: Time + Premium Amort. is used in the following hedging scenario:

943: CFH: FX-Risk with Intrinsic, Time + Premium Amort.

With this hedge accounting rule, the following occurs:

A change in the amount of the actual value of the intrinsic component (NPV_INTR) is posted to the hedging reserve.

A change in the amount of the actual value of the time component (NPV_TIME) and the amortization amount of the premium (component NPV + NPV_OTHER) are used to calculate the cost of hedging reserve.

[figure TRM09-F023 - A change in the amount of the actual value of the time component (NPV_TIME) and the amortization amount of the premium (component NPV + NPV_OTHER) are used to calculate the cost of hedging reserve.]

###### HA Rule 650

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 650 | L6 | trm09 p.91 | loio `6e9bf26f4935455596c808a6d12e973a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6e9bf26f4935455596c808a6d12e973a.html?locale=en-US)

**Use**

The hedge accounting rule 650: Hdg Reserve: Intrinsic/Cost of Hdg Reserve: Time + CCBS is used in the following hedging scenario:

980: CFH: FX Risk with Intrinsic, Time + CCBS

**Features**

A hedge accounting rule specifies how a hedged item and the related hedge transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. A hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

1303 - Ineffective

In this hedge accounting rule, the intrinsic component (NPV_INTR) is used to calculate the hedging reserve, and the time (NPV_TIME) and CCBS (NPV_CCBS) components are used to calculate the cost of hedging reserve.

In this hedge accounting rule, the calculation rule for the cost of hedging reserve is determined during the release of hedging business transactions and is based on the time component (NPV_TIME_RF of the hedging instrument and NPV_TIME of the hypothetical derivative) and the CCBS component (NPV_CCBS_RF of the hedging instrument and NPV_CCBS of the hypothetical derivative).

**Note:**

If the hedge accounting key figures NPV_TIME_RF and NPV_CCBS_RF are not calculated, system takes the NPV_TIME and NPV_CCBS components of the hedging instrument instead.

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Exception: For an FX option with a premium that has been activated, in classifications after the payment date of the premium, the calculated values for the elements and components are used as start values during classification (with the Run Classification app) and are not assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

**Classification**

You use the Execute Classification function (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


The relevant calculation rules are described below.

Calculation of Hedging Reserve and Ineffective/Hedging Reserve TPL

The 1302 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL components are calculated based on the result of the lower-of test of the intrinsic components (NPV_INTR) of the hedging instrument and the hypothetical derivative.

[figure TRM09-F024 - Overview of Calculation Rule for Hedging Reserve]

Overview of Calculation Rule for Hedging Reserve

Calculation of Cost of Hedging Reserve and Ineffective/Cost of Hedging Reserve TPL

The 1322 Effective/Cost of Hedging Reserve and 1333 Ineffective/Cost of Hedging Reserve TPL components are calculated based on the time (NPV_TIME) and CCBS (NPV_CCBS) components.

At the time of release of the hedging business transactions, the actual and aligned values were calculated as follows:

Actual value = Time + CCBS of Hedging Instrument

Aligned value = Time + CCBS of Hypothetical Derivative

One of the following calculation rules for the cost of hedging reserve was determined:

1 - Actual Value = Aligned Value

The change in the amount of the actual value is posted to the cost of hedging reserve.

2 - Actual Value > Aligned Value

The change in the amount of the aligned value is posted to the cost of hedging reserve.

3 - Aligned Value > Actual Value

The cost of hedging reserve is determined based on the lower-of test. The smaller amount of the actual and aligned value is posted to the cost of hedging reserve and the remaining amount is posted to the P/L statement.

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profiles .

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedge business transactions is set to Actual Value = Aligned Value.

[figure TRM09-F025 - Overview of Calculation Rule for Cost of Hedging Reserve]

Overview of Calculation Rule for Cost of Hedging Reserve

Legend

|Abbreviation|Description|
|---|---|
|AC|Actual Value|
|AV|Aligned Value|
|CCBS|Cross-Currency Basis Swap|
|HInst.|Hedging Instrument|
|Hyp. Der.|Hypothetical Derivative|
|Ineff. C./H.Res. TPL|Ineffective Cost of Hedging Reserve Through Profit or Loss|
|Eff. C/H.Res.|Effective Cost of Hedging Reserve|
|Eff. Amt|Effective Amount|
|Eff. H. Res.|Effective Hedging Reserve|


|Abbreviation|Description|
|---|---|
|Ineff. H.Res. TPL|Ineffective Hedging Reserve Through Profit or Loss|


During the classification, the relevant amounts for the hedging reserve, cost of hedging reserve, and P/L ineffective are calculated. The cost of hedging reserve amount is calculated according to the calculation rule that was determined during the release of hedge business transactions and is then posted to Financial Accounting (FI).

**Note:**

The remaining amount that is not posted to either the hedging reserve or the cost of hedging reserve components is posted to P/L ineffective component 1303 (Ineffective).

**More Information**

Hedge Accounting Key Figures

###### HA Rule 651

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Overview Hedge Accounting Rules > HA Rule 651 | L6 | trm09 p.96 | loio `1a31b4a9ed894477af8af8bbb122c18a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1a31b4a9ed894477af8af8bbb122c18a.html?locale=en-US)

**Use**

The hedge accounting rule 651: Hdg Reserve: Intrinsic/Cost of Hdg Reserve: Time + CCBS + Others is used in the following hedging scenario:

981 CFH: FX Risk with Intrinsic, Time + CCBS + Others

**Features**

A hedge accounting rule specifies how a hedged item and the related hedge transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. A hedge accounting rule also determines how the classification is calculated. The valuation result is split into the following different position components, which reflect effective and ineffective amounts:

1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

1303 - Ineffective

In this hedge accounting rule, the intrinsic component (NPV_INTR) is used to calculate the hedging reserve, and the time component (NPV_TIME), the CCBS component (NPV_CCBS), and the Others component (NPV_OTHERS) are used to calculate the cost of hedging reserve.

The calculation rule for the cost of hedging reserve is determined during the release of hedging business transactions and is based on the time component (NPV_TIME_RF of the hedging instrument and NPV_TIME of the hypothetical derivative), the CCBS component (NPV_CCBS_RF of the hedging instrument and NPV_CCBS of the hypothetical derivative), and the Others component (NPV_OTHERS_RF of the hedging instrument or NPV_OTHERS of the hypothetical derivative).

If the hedge accounting key figures NPV_TIME_RF and NPV_CCBS_RF are not calculated, system takes the NPV_TIME and NPV_CCBS components of the hedging instrument instead.

**Release of Hedging Business Transactions**

The release of hedge business transactions (transaction TPM120) triggers the calculation of the NPV components and NPV elements for the forward transaction and the hypothetical derivative on the designation date (Hedge Accounting Key Figures). These values are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The component values are required for the valuation that takes place during the release of hedge business transactions.

During the release of hedge business transactions, transfer postings are made from the free-standing subpositions either to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the firstday valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Exception: For an FX option with a premium that has been activated, in classifications after the payment date of the premium, the calculated values for the elements and components are used as start values during classification (with the Run Classification app) and are not assumed to be 0.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Valuation During the Hedging Relationship**

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

**Valuation at the End of the Hedging Relationship**

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

Classification

You use the Execute Classification function (transaction TPM101) to split the valuation result into the following different position components, which reflect effective and ineffective amounts:

- 1302 - Effective/Hedging Reserve

1323 - Ineffective/Hedging Reserve TPL

1322 - Effective/Cost of Hedging Reserve

1333 - Ineffective/Cost of Hedging Reserve TPL

- 1303 - Ineffective


The relevant calculation rules are described below.

Calculation of Hedging Reserve and Ineffective/Hedging Reserve TPL

The components 1302 Effective/Hedging Reserve and 1323 Ineffective/Hedging Reserve TPL are calculated based on the result of the lower-of test of the intrinsic components (NPV_INTR) of the hedging instrument and the hypothetical derivative.

[figure TRM09-F026 - Overview of Calculation Rule for Hedging Reserve]

Overview of Calculation Rule for Hedging Reserve

Calculation of Cost of Hedging Reserve and Ineffective/Cost of Hedging Reserve TPL

The components 1322 Effective/Cost of Hedging Reserve and 1333 Ineffective/Cost of Hedging Reserve TPL are calculated based on the time (NPV_TIME), CCBS (NPV_CCBS), and the Others components (NPV_OTHERS of the hedging instrument).

At the time of release of the hedging business transactions, the actual and aligned values were calculated as follows:

Actual value = Time + CCBS + Others of Hedging Instrument

Aligned value = Time + CCBS + Others of Hypothetical Derivative

One of the following calculation rules for the cost of hedging reserve was determined:

1 - Actual Value = Aligned Value

The change in the amount of the actual value is posted to the cost of hedging reserve.

2 - Actual Value > Aligned Value

The change in the amount of the aligned value is posted to the cost of hedging reserve.

3 - Aligned Value > Actual Value

The cost of hedging reserve is determined based on the lower-of test. The smaller amount of the actual and aligned value is posted to the cost of hedging reserve and the remaining amount is posted to the P/L statement.

**Note:**

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profiles .

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedge business transactions is set to Actual Value = Aligned Value.

[figure TRM09-F027 - Overview of Calculation Rule for Cost of Hedging Reserve]

Overview of Calculation Rule for Cost of Hedging Reserve

Legend

|Abbreviation|Description|
|---|---|
|AC|Actual Value|
|AV|Aligned Value|
|CCBS|Cross-Currency Basis Swap|
|HInst.|Hedging Instrument|
|Hyp. Der.|Hypothetical Derivative|
|Ineff. C./H.Res. TPL|Ineffective Cost of Hedging Reserve Through Profit or Loss|
|Eff. C/H.Res.|Effective Cost of Hedging Reserve|
|Eff. Amt|Effective Amount|
|Eff. H. Res.|Effective Hedging Reserve|
|Ineff. H.Res. TPL|Ineffective Hedging Reserve Through Profit or Loss|


During the classification, the relevant amounts for the hedging reserve, cost of hedging reserve, and P/L ineffective are calculated. The cost of hedging reserve amount is calculated according to the calculation rule that was determined during the release of hedge business transactions and is then posted to Financial Accounting (FI).

**Note:**

The remaining amount that is not posted to either the hedging reserve or the cost of hedging reserve components is posted to P/L ineffective component 1303 (Ineffective).

**More Information**

Hedge Accounting Key Figures

###### Automated Designation Process

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Automated Designation Process | L5 | trm09 p.100 | loio `38417f58655b9244e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/38417f58655b9244e10000000a4450e5.html?locale=en-US)

**Use**

This process automatically designates a financial transaction into a hedging relationship when the financial transaction is saved. The financial transaction acts as the hedging instrument. The dedicated exposure items, determined during the automated designation process, act as the hedged items and are also designated automatically into the hedging relationship.

Process

[figure TRM09-F028 - Overview of Automated Designation Process]

Overview of Automated Designation Process

- 1. Automated Designation


When the financial transaction is saved, the automated designation process is triggered.

**Note:**

For collars or FX swaps, a separate process step is required to trigger the automated designation process. For more information, see Create Reference

Based on the data of the financial transaction (such as, company code, valuation area, currency, contract date, value date, and hedging classification), the system determines the relevant exposure item:

- a. The system checks whether the hedge accounting indicator has been set to Active in the Define Hedging Classifications Customizing activity for the relevant company code and valuation area on the contract date of the financial transaction.
- b. The relevant hedging area version is determined based on the contract date of the financial transaction and the hedging classification.
- c. The system must identify the relevant exposure item. Therefore, the system uses the snapshot for the relevant hedging area version which fulfills the following criteria:


**Note:**

There must be only one hedging area version that is marked as relevant for hedge accounting for this hedging classification and point in time.

The date of the snapshot is equal to the contract date of the financial transaction. If no snapshot exists on the contract date, system takes the last snapshot taken before the contract date.

The snapshot must have the day reference indicator.

For hedging areas with analysis item definition By Time Periods the system determines the exposure item by matching it to the differentiation criteria defined in the hedging area and to the start and end date of the treasury

ledger position.

**Note:**

In case of the designation of FX transactions, the Value Date of the transaction is used for the determination of the exposure items.

In case of the designation of a non-deliverable forward, the Value Date or the Fixing Date of the transaction is used for the deteremination of the exposure item. This is defined in the hedging area. For more information, see also Hedging Area: Main Data

In case of the designation of FX options, the Value Date of Underlying or the Exercise Date of the FX Option is used for the determination of the exposure items. This is defined in the hedging area. For more information, see also Hedging Area: Main Data

For hedging areas with analysis item definition By Time Periods, reporting time pattern Calendar-Related, and period length Monthly a due date shift can be defined in the hedging area on Hedging Area: General Settings tab. The due date shift allows you to report your hedging instruments in the Hedge Management Cockpit in the following month after the due date of the hedging instrument. This means, that these hedging instruments are used to hedge the exposure items of the following month. The automated designation process considers the due date shift and searches for exposure items in the following month. The end date of the hedged item and the value date of the hypothetical derivative is either the first day or the last day of the following month after the due date of the hedging instrument.

The exposure item comprises the following values:

ID

Amount

Currency

Snapshot ID

Due date

Relevant differentiation criteria

**Note:**

For hedging areas with analysis item definition By Reference you need to assign the exposure item on Administration tab within the data of the financial transaction used as hedging instrument. The system supports you with a search help to find the exposure item.

For more information, see Elementary Search Help for Exposure Item ID by String

- 2. Creation of Hedge Accounting Entities


The system automatically creates the following entities during the automated designation process:

**Note:**

For collars and FX swaps, you first have to create a reference between the two plain vanilla FX options or the two FX forward transactions that will then form the collar or FX swap.

a. Exposure subitem(s)

The system reads the data on the hedge accounting tabs to determine how many exposure subitems are created, the amounts of the specific exposure subitems, and the relevant dates.

For more information, see exposure subitems

b. Hedging relationship(s)

The hedging relationship is created and set to Planned Designation status for the relevant valuation area after the financial transaction is saved.

**Note:**

The financial transaction can be designated into one or multiple hedging relationships. The number of hedging relationships that is created depends on the settings made for designation splitting in the hedging area.

**Note:**

For more information, see designation splitting

The hedging relationship links the hedging instrument and the hedged item. It also holds information about the calculation methods for hedge accounting processing.

Depending on the designation category of the hedging relationship, different designation statuses are applicable.

In the case of One Instrument (such as an FX forward), for example, the following statuses are available:

Created

At least one object for the successful creation of a hedging relationship is missing or has errors: Hedging relationship, hedged item, hedging instrument, position indicator, or planned flows.

Planned Designation

All objects were saved successfully during the automated designation process: Hedging relationship, hedged item, hedging instrument, position indicator, planned flows, and planned designation flows.

Designated

All objects were saved and released successfully for designation: Hedging relationship, hedged item, hedging instrument, position indicator, planned flows, and planned designation flows.

Revoked

The hedging relationship can no longer be used for the automated designation process, after changes to Group 1, Group 2 fields and the hedge request ID of the FX transaction.

Use Manage Hedging Relationships (transaction TPM100) to ensure that the attributes of your hedging relationship and the data corresponding to the designation process are correct. For more information, see Manage Hedging Relationships.

Hedged item(s)

The hedged item holds general information and calculation methods for hedge accounting processing. It represents the portion of the underlying operational exposure after designation splitting. The exposure item data was determined automatically from the relevant version of the hedging area snapshot.

Hedging instrument(s)

The hedging instrument represents the financial transaction (such as an FX forward) that was created to hedge the operational exposure item. The portion of the nominal amount of the FX forward that is to be designated into the hedging relationship is determined based on the settings made for designation splitting in the hedging area.

At the end of the automated designation process, all entities relevant for hedge accounting have been created, and the status of the hedging relationship is set to Planned Designation. To complete the designation of your hedging relationship, you have to change its status to Designated.

**Note:**

This step is not automated and has to be performed using Release Hedging Business Transactions (transaction TPM120).

For more information, see Release Hedging Business Transactions.

**More Information**

Automated Designation Process - FX Swap

Period-End Closing

Contract Close

Reporting

###### Automated Designation Process - FX Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Automated Designation Process > Automated Designation Process - FX Swap | L6 | trm09 p.104 | loio `e7c6d3577f10417c80643adf5146b717` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e7c6d3577f10417c80643adf5146b717.html?locale=en-US)

**Use**

When you created an FX swap due to an overhedge situation the hedging relationship needs to be swapped to another exposure item period. This is handled by transferring the original hedging relationship to a new hedging relationship, where the FX swap acts as one of the hedging instruments together with the FX forward of the original hedging relationship.

**Note:**

This process is triggered if you assigned to both FX transactions of the FX swap a hedging classification with designation category N Instruments (Swap) Designation Pattern.

See also: Create Hedging Instruments

**Process**

The creation of the FX swap reference triggers the following activities:

- 1. A new hedging relationship is created in Planned Designation status with the designation date on swap date.
- 2. A hedging business transaction of Hedging Relationship Swap Transfer type is created.

This hedging business transaction is relevant for the original and the new hedging relationship.

- 3. The original hedging relationship is processed as follows:

- a. Nominal amounts of hedged item (exposure subitem), hedging instrument (FX forward transaction), and hypothetical derivative as well as pro rata amounts of hedging reserve and cost of hedging reserve are transferred out on swap date.
- b. In case of a partial swap, the remaining portions of the amounts are processed within the original hedging relationship according to the settings on designation date.


- 4. The new hedging relationship is processed as follows:


- a. The hedging profile is copied from the original hedging relationship to the new hedging relationship.
- b. Splitting information for the creation of multiple hedging relationships is not considered for the creation of the new hedging relationship.
- c. Nominal amounts of the newly-created hedged item (exposure subitem), the portion of the hedging instrument (FX forward transaction), and the amounts of the hedging reserve and cost of hedging reserve are transferred in on swap date.
- d. The planned dedesignation date is newly determined for the new hedging relationship. It is derived from the settings of the hedging area version valid on the designation date of the original hedging relationship.
- e. As long as the balance sheet recognition date is later than designation date of the new hedging relationship, the date is newly determined for the new hedging relationship from the settings of the hedging area version valid on the designation date of the original hedging relationship. If the balance sheet recognition date has already passed, the date is copied from the original hedging relationship to the new hedging relationship: In this case the respective accounting logic is used at period-end close.
- f. The swap reference can be accessed from the new hedging relationship using the Manage Hedging Relationships function (transaction TPM100).
- g. The hedged item is created in the same way as for other hedging relationships
- h. The new hedging relationship consists of three hedging instruments:


FX forward transaction from the old hedging relationship

FX swap containing the two new FX forward transactions linked together by the swap reference

- 5. Release Hedging Business Transactions - FX Swap Transfer


**Related Information**

Automated Designation Process

###### Automated Designation Process - Swap of Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Automated Designation Process > Automated Designation Process - FX Swap > Automated Designation Process - Swap of Swap | L7 | trm09 p.105 | loio `358647a65cc645e794d7ef60b0149ec3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/358647a65cc645e794d7ef60b0149ec3.html?locale=en-US)

An FX swap can also roll over or shorten a hedging relationship that is already derived from an FX swap. The swap of swap follows the rules of the automated designation process of FX swaps.

See also: Automated Designation Process - FX Swap

**Example:**

We create a second FX swap for a hedging relationship (which already contains three hedging instruments).

The following two scenarios depending on the concrete swap date can occur for swapping to a later date:

[figure TRM09-F029 - Exposure Prolongation from t to t]

Exposure Prolongation from t to t

3 4

Rollover, swap date before the t

2

All previous hedging instruments are involved in the prolongation process. On t the new hedging relationship B is created. In the hedging relationship B, five hedging instruments and one hedged item exist.

2-x

Dedesignation Flows:

One dedesignation flow is created for the end date (t ) of the second leg of the new FX swap for hedging relationship B.

4

One dedesignation flow is created for the prolongation date (t ) for the second leg of the hedging instrument of hedging relationship A.

2-x

One dedesignation flow is created for the prolongation date (t ) for the original hedging instrument of hedging relationship A.

2-x

Rollover, swap date after the t

2

We have a behavior similar to the normal swap. On t the new hedging relationship is created. In the hedging relationship, three hedging instruments (the second leg of the old hedging relationship and the two new FX forwards of the second FX swap) and one hedged item exist.

2+x

Two dedesignations are needed: One dedesignation is created at the end date (t ) of the second leg of the new FX swap and also one dedesignation for the second leg of the hedging relationship to be swapped and the new offsetting hedging instrument.

4

The following two scenarios depending the concrete swap date can occur for swapping to an earlier date:

[figure TRM09-F030 - Exposure Shortening from t to t]

Exposure Shortening from t to t

3 3-x

In case of a shortening FX swap we still have only one dedesignation for the exposure subitem and all the hedging instruments involved at the end of the first leg t .

3-x

###### Automated Designation Process - FX Collar

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Automated Designation Process > Automated Designation Process - FX Collar | L6 | trm09 p.107 | loio `c39c43776d5d475e8fda9ce452a2dd01` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c39c43776d5d475e8fda9ce452a2dd01.html?locale=en-US)

**Use**

Reference the two FX options using the Create Reference function (transaction TBR6) or create the collar FX option using Create Collar FX Option function (transaction TI4B).

The reference type OPT in combination with the hedging classification controls the designation process.

**Note:**

The value date of the underlying FX transaction of the option is used for the determination of the exposure subitems end date.

The dedesignation date of the hedging relationship matches the exposure item period.

**Both FX Options Designated in the Same Hedging Relationship**

The hedging classifications must be indicated as Hedge Accounting relevant and shall cover a hedging profile for FX options and a designation type with designation category 2 Two Instruments (Collar) Designation Pattern (derived from the settings on Hedge Accounting II tab in the relevant hedging area version).

The FX collar is created and automatically designated into a hedging relationship.

Process

The creation of the collar reference triggers the following activities:

- 1. A new hedging relationship is created in Planned Designation status with the designation date on Contract Start Date of the collar FX option.
- 2. The Planned Dedesignation Date is the Expiry Date of the collar FX option.
- 3. The new hedging relationship consists of two hedging instruments.


**Only one Option Designated in a Hedging Relationship (Long Position )**

It is also possible, that you only assign a hedging classification to one of the FX options (the long position) and the other does not get a hedging classification. In this case, only one FX option is designated into a hedging relationship.

###### End-of-Day Designation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Automated Designation Process > End-of-Day Designation | L6 | trm09 p.108 | loio `57a84eb53d9d400ba7c3a1353a75ba09` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/57a84eb53d9d400ba7c3a1353a75ba09.html?locale=en-US)

You can postpone the automated designation of your hedging instruments until the end of the day. In this case, the automated designation is not started when the hedging instrument is saved. Instead, you start the automated designation of the financial transactions at the end of the day using the Reprocess Financial Instruments for Automated Designation report. This enables you to take several snapshots with day-reference indicator per day. Only after you have taken the last snapshot of the day, you trigger the end-of-day designation for all hedging instruments of the day.

**Note:**

You can run the Reprocess Financial Instruments for Automated Designation report for end-of-day designation in the batch.

**Prerequisites**

You enable the end-of-day designation in the Define Designation Types Customizing activity, where you set the End-of- Day Designation indicator for the designation type.

You must assign the designation type on the Hedge Accounting II tab in the Hedging Area for a combination of differentiation criteria.

These include:

Company code

Valuation area

On Behalf of Company Code

The company code on behalf of which you perform a transaction.

Hedging classification

**Note:**

All designation types relevant for a hedging area must have the same settings concerning the designation. They all provide either for end-of-day designation or for immediate designation.

**Related Information**

Reprocess Financial Transactions for Automated Designation

Automated Designation Process

###### Reprocess Financial Transactions for Automated Designation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Reprocess Financial Transactions for Automated Designation | L5 | trm09 p.108 | loio `d6101a2660e24cf0997a9c3ceec910e9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d6101a2660e24cf0997a9c3ceec910e9.html?locale=en-US)

During the automated designation process triggered by the creation of hedging instruments (or after the assignment of the hedging classification using Edit Financial Transaction (transaction FTR_EDIT) errors may occur. To allow further processing of the affected financial transaction, only a warning message is displayed while the data of the financial transaction are saved. This warning message is stored in a separate log as an error message and can be analyzed subsequently with the Reprocess Financial Transactions for Automated Designation function (transaction TPM104).

**Note:**

If your system settings provide end-of-day designation, you trigger the automated designation process by the execution of this function. To do so, set the Include End-of-Day Designation indicator in the Processing Control area.

You can execute the function as batch run.

**Prerequisites**

You have made the required settings in Customizing, under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Settings for Automated Designation of Exposure Items (FX Risk) .

**Features**

With the Reprocess Financial Transactions for Automated Designation function, you can select all treasury positions of the financial transactions that are relevant for hedge accounting and need to be designated into a hedging relationship but for which the automated designation process failed.

The following two error situations can occur during the automated designation process:

No hedging relationship is created when the financial transaction was saved.

One or more hedging relationships were created in Created status, but the designation of the financial transaction failed.

These error situations can occur due to the following:

Incomplete configuration

Incorrect financial transaction data

**Features**

The following features are available:

Reprocess function (in a test run or in update mode)

You can start the reprocess function after the errors have been corrected. If reprocessing was successful, you’ll get an updated worklist:

The treasury position is removed from the list.

The status of the incorrect hedging relationship is changed to Revoked.

A new hedging relationship is created in Planned Designation status.

Trigger the automated designation process for financial transactions relevant for end-of-day designation.

Display log

A worklist of all financial transactions with errors is provided. It contains one entry for each company code, valuation area, and financial transaction with a proxy message.

Display hedging relationship

You can navigate directly to the hedging relationship.

Layout

You can choose a predefined display variant.

**Activities**

- 1. You can limit your search results using the following parameter:

General Selections

Company Code

Valuation Area

Product Type

Transaction Type

Transaction Number

Business Partner

Portfolio

Hedging Class.

Hedging Area

Date Selection

Contract Date

Due From date

The system selects financial transactions relevant for reprocessing with a value date equal or greater than the entered date in this field.

Processing Control

Set the Include End-of-Day Designation indicator in the Processing Control area to trigger the automated designation process for all financial transaction relevant for end-of-day designation.

Only execute the report with this indicator, if you have taken all snapshot for the day.

Output Control

The Display Transactions indicator is set by default. In addition, you can choose the layout for the worklist.

In case you set the Include End-of-Day Designation indicator, you can deselect the Display Transactions indicator. Then the Posting Control area appears, where you can deselect the Test Run indicator.

- 2. Execute the report.


- A worklist with all treasury positions corresponding to the selections criteria that caused errors during the automated designation process is displayed.
- 3. Choose a treasury position from the list and use the Display Log pushbutton to get detailed information about the error.
- 4. Choose the Display Hedging Relationship pushbutton to get detailed information about the relevant hedging relationship created during automated designation process.
- 5. Correct the relevant errors and start reprocessing.
- 6. Using the   RemoveTransaction from Reprocessingbutton you can delete a line item from the list. The error message can only be recovered if the financial transaction is updated and the designation is not executed. You can use this function if a financial transaction should not be reprocessed (i.e. because reprocessing is not needed anymore).


**Note:**

If the Display Transactions indicator is not set, you will not get the worklist.

**Note:**

We recommend using the test mode first to ensure that all errors have been corrected.

Results:

If reprocessing was successful, the treasury position disappears from the error log. If the treasury positions is linked to another treasury position via SWP or OPT reference category this treasury position is also removed from the list.

If an incorrect hedging relationship was created, its status is changed to Revoked and a new hedging relationship is created in Planned Designation status.

If reprocessing did not solve the issue, the treasury position still appears in the error log, but the log is overwritten with the new error log.

**Example**

- 1. You create an FX forward transaction that is automatically designated into a hedging relationship because you have assigned a hedging classification that is classified as Relevant for Hedge Accounting.
- 2. Once you save the FX transaction, a warning message is issued, but the creation of the financial transaction is not interrupted.

The hedging relationship was not created automatically because some relevant transaction data was incorrect.

- 3. You use the Reprocess Financial Transactions for Automated Designation function to get detailed information and analyze the error.

The following error occurred: Enter the amount of the hedging instrument to be designated

- 4. You correct this error using Edit Financial Transaction (transaction FTR_EDIT).
- 5. You can then reprocess the financial transaction.

###### Change of Hedging Instrument

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Change of Hedging Instrument | L5 | trm09 p.111 | loio `9869331484c145ebb1feae755e82f1a9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9869331484c145ebb1feae755e82f1a9.html?locale=en-US)

The process of changing a financial transaction has been enhanced to support the automated designation process. In general, the hedge accounting process must have only limited impact on operational processes of financial transactions.

Changes to the field values of a financial transaction can have different effects on the corresponding hedging relationships.

We distinguish between three different field groups:

**Group 1 - Fields That Impact the Designation Flows or NPV Calculation:**

Rate

Buy/Sell

Traded Amount

Opposite Amount

Value Date

Spot Rate

Swap Rate

Liquidity Effect for Rollover

Contract Date

Hedging Classification

Business Partner

**Note:**

Depending on the financial transaction, not all of the Group 1 fields listed here might apply.

**Example:**

[figure TRM09-F031 - Overview of Group 1 Fields]

Overview of Group 1 Fields

**Group 2 - Fields That Can be Defined as Differentiation Criteria of the Hedging Area:**

Portfolio

Profit Center

Cost Center

WBS Element

On Behalf of Company Code

Business Area

Segment

Country/Region

These fields impact the determination of the exposure item ID.

**Example:**

[figure TRM09-F032 - Overview of Group 2 Fields]

Overview of Group 2 Fields

**Group 3 – Fields That Don’t Affect the Automated Designation Process:**

Trader

Contact Person

External Reference

Finance Project

Guarantor

General Valuation Class

Effects on Hedging Relationships

You can change the fields of Group 1 and Group 2 as long as the hedging relationship is in Planned Designation status. In this case, any changes result in the following:

A change of the hedging relationship status from Planned Designation to Revoked

The creation of a new hedging relationship

If the hedging relationship is in Designated status, the hedging relationship has to be reversed (using the Reverse Release of Hedging Business Transactions app) before the financial transaction with changed field values of Group 1 or Group 2 can be changed or settled.

For changes to collars and FX swaps used in hedging relationships, see also Change of Collar or FX Swap.

**Note:**

How to shift the dates (such as the value date, fixing date, and expiry date (also called exercise date) of a financial transaction that is already used as hedging instrument in a designated hedging relationship to a later or previous working day

During the creation of a financial transaction, the system checks the dates and ensures that the dates of the financial transaction are working days. If the financial transaction is part of a hedging relationship, you usually can’t change the dates later as described above. However, exceptional circumstances, such as the introduction of a new public holiday in a country/region, might force you to change the dates (such as the value date, fixing date, and expiry date) of a financial transaction even if it’s part of a hedging relationship. As of now, you can change the system behavior and allow dates to be changed either to a later working day or to an earlier working day, without no limit on the number of days that you change.

**Tip:**

The shift to an earlier date is needed to achieve the correct exposure item assignment in the Hedge Management Cockpit in case the new public holiday falls on a period end.

- 1. Change the system behavior and enable the change of the dates. Configure message TPM_THX1 486 as warning message in the Change Message Control configuration step in the Customzing of Treasury and Risk Management under Transaction Manager General Settings Tools Configurable Messages .
- 2. Then you make the change of the dates manually in the financial transaction data using the relevant collective processing app.


For FX forwards you now can change the value date.

For NDF transactions, you now can change the value date and the fixing date. The meaning of the dates for the hedging relationships depends on the settings you have made on the Main Data tab of the hedging area. There you’ve specified which date is used to determine the exposure item during the automated designation process of a non-deliverable instrument, such as an NDF. This setting also affects hedge accounting. For more information, see also Hedging Area: Main Data

For FX options, you now can change the value date of the underlying and the expiry/exercise date of the FX option. The meaning of the dates for the hedging relationships depends on the settings you have made on the Main Data tab of the hedging area. There you’ve specified which date is used to determine the exposure item during the automated designation of an FX option. This setting also affects hedge accounting. For more information, see also Hedging Area: Main Data

**Note:**

If you change the dates of a financial transaction that is part of an FX cylinder option or FX swap, you must also make this change in the second financial transaction of the FX cylinder option or FX swap.

The change of the dates results in the following updates:

The close transactions of the financial transactions are updated automatically.

The change of the date in the financial transaction leads to the change of the following dates of the affected hedging relationship:

Planned dedesignation date

The planned dedesignation date represents the value date of the financial transaction, for FX options it’s the value date of the underlying transaction.

If the hedging instrument is a non-deliverable instrument, such as a non-deliverable forward, and if, on the Main Data tab in the hedging area, you have specified Fixing Date in the Date for Determining Exp. Itm for Non-Del. Inst. field, the planned dedesignation date is the fixing date.

If the hedging instrument is an FX option and if, on the Main Data tab in the hedging area, you have specified Exercise Date in the Date for Determining Exp. Itm for FX Options field, the planned dedesignation date is the exercise date of the FX option (which is the Expiry Date field in FX option data).

Therefore, the dedesignation date is shifted to the new value date, the new expiry/exercise date, or the new fixing date.

Balance sheet recognition date

Automatically adjusted accordingly to the change of the dedesignation date (same number of days and same direction).

In case of a shift to an earlier date, it has to be ensured that the Balance Sheet Recognition Date isn’t set to an earlier date as the date of the change.

Reclassification date

Automatically adjusted accordingly to the change of the dedesignation date (same number of days and same direction).

End date of the hedged item

The end date of the hedging relationship is derived from the reclassification offset category of the relevant hedging area.

Automatically adjusted accordingly to the change of the dedesignation date (same number of days and same direction)

Value date of the hypothetical derivative

Remains unchanged as it was determined based on the exposure representation.

There is only one exception from this rule:

The hypothetical derivative is adjusted if the end of term of the HD (value date for forwards and non-deliverable forwards, exercise date for options) is before the new dedesignation date. In this case, the hypothetical derivative would no longer be processed at dedesignation, which would lead to significant ineffectiveness. Therefore, in this case, the term end date of the hypothetical derivative is shifted to the new dedesignation date (the fixing date or value date of the underlying may also be shifted in parallel).

Additional comments about the system behavior and the effects of the changes:

Flows that have already been fixed won’t be affected by the new dates.

The relevant hedging business transactions, such as the dedesignation business transaction, and the resulting planned flows, are automatically updated with the changed date.

No adjustment postings are made.

Due to the changed dates, the new dates are considered for calculations such as the calculation of the net present value.

- 3. Execute the Reprocess Transactions - Automated Designation app, to ensure that no errors occurred.

Example: If you only changed the first transaction of a collar or FX swap, the Reprocess Transactions Automated Designation app issues a message that the related second financial transaction of the FX cylinder option or FX swap also needs to be changed accordingly.

- 4. Check the dates in the hedging relationships using the Manage Hedging Relationships app.


Changes to fields of Group 3 don’t have any impact at all on the hedging relationship.

###### Change of Collar or FX Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Change of Hedging Instrument > Change of Collar or FX Swap | L6 | trm09 p.117 | loio `6dad0e718e434c24a5d811321ec53bc8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6dad0e718e434c24a5d811321ec53bc8.html?locale=en-US)

**Use**

You can carry out the following operations for a collar or an FX swap that is designated into a hedging relationship, in addition to changing any of the fields belonging to the three different field groups:

Changing the reference between the two plain vanilla FX options or the two FX forward transactions

Deleting the reference between the two plain vanilla FX options or the two FX forward transactions

You can change or delete the reference between the FX options or FX forwards as long as the hedging relationship is in Planned Designation status. Once the hedging relationship is in Designated status, the release of the hedging relationship needs to be reversed first.

**Note:**

Only changes that do not interfere with the hedging process are allowed.

**Change Reference**

- 1. Use the Change Reference function (transaction TBR7) to change the link between the two FX transactions while changing the hedging relationship accordingly.
- 2. Enter the following parameter:

Reference Category:

OPT - Option reference - derivatives

SWP - Forex Swap

Reference: Your reference number

- 3. The system displays your current collar or FX swap.
- 4. Remove one FX option from the collar or one FX forward transaction from the FX swap using the Remove pushbutton.
- 5. Add a newly-created FX option to your collar or a newly-created FX forward transaction to your FX swap using the Add pushbutton.


**Note:**

Make sure that you remove and add FX transactions with the same transaction type.

6. Save your entries.

After you have saved your changes, the status of the hedging relationships created with the FX transactions in the old collar or swap is changed to Revoked, and new hedging relationships according to your newly-created collar or swap are created with Planned Designation status.

**Delete Reference**

- 1. Use the Undo Reference function (transaction TBR9) to delete the link between the two FX options or FX forwards while deleting the current hedging relationships accordingly.
- 2. Enter the following parameter:

Reference Category:

OPT - Option reference - derivatives

SWP - Forex Swap

Reference: Your reference number

- 3. The system displays your current collar or FX swap.
- 4. Choose Save.


The reference between the two FX options or two FX forwards is deleted, and the status of the hedging relationship is changed to Revoked.

**Related Information**

Change of Hedging Instrument

###### Release Hedging Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions | L5 | trm09 p.118 | loio `588b2c5863352360e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/588b2c5863352360e10000000a44147b.html?locale=en-US)

App ID: TPM120

With this app, you release and complete processes such as designation, FX swap transfer, reclassification, or dedesignation. At release, the planned flows for these hedging business transactions are fixed.

See the following list of hedging business transactions:

- 9040 Designation

- 9041 Dedesignation


- 9046 Reclassification

- 9047 Hedging Relationship Swap Transfer


**Note:**

The planned flows of unreleased hedging business transactions are updated automatically if relevant business transactions occur. For example, Classification business transactions update the Reclassification flows. After the release of a business

transaction, the flows cannot be updated anymore. In this case, you first must reverse the release of the business transaction.

**Prerequisites**

The designation of the hedging relationship is released in accordance with the counterconfirmation settings made in the Customizing activity Define Designation Types.

If the Release of Hedging Relationship Requires Counterconfirmation indicator is set, the hedging relationship with the status Planned Designation can be released only after counterconfirmation of the financial transaction has been received.

If the indicator isn’t set, the hedging relationship with the status Planned Designation can be released immediately.

**Features**

Process steps are executed at release of designation

The hedged item has already been created during the automated designation process with the following dates:

Start Date

The start date represents the contract start date of the financial transaction.

End Date

The end date of the hedging relationship is derived from the reclassification offset category of the relevant hedging area.

If you activated a due date shift in the hedging area, the end date of the hedged item is either the first day of the following month or the last day of the following month after the due date of the hedging instrument.

With the release of designation, the hypothetical derivative is created in addition. (For more information, see Hypothetical Derivative (Hedge Accounting for Exposure Items).)

**Note:**

Two hypothetical derivatives are created in cases where you use a collar as the hedging instrument. Go to the Hedged Item tab in the Manage Hedging Relationships app to select the hypothetical derivative that you want to display from the dropdown list.

The calculation of the hedge accounting key figures (NPV components and NPV elements for the hedging instrument and the hypothetical derivative on designation date) is executed (Hedge Accounting Key Figures), so the start values of the hedging instrument and the hypothetical derivative on designation date are calculated. These values are then stored in the market data container.

The hedge accounting key figures are determined based on the settings made in the respective hedge accounting calculation type.

The elements and contract rate components are calculated once you release the designation, and they are then stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve.

The market value components are calculated when you release the designation and then again at period end during the NPV calculation.

The component values are required for the classification that takes place during the release of hedging business transactions.

If the prospective effectiveness test is enabled for the hedging profile, and a test plan has been generated containing a record for the designation (or FX swap transfer) date and a market data set, the system executes the prospective effectiveness. For more information, see: Prospective Effectiveness Test Using Linear Regression

For cash flow hedges with the hedged item category Planned Forecast, the calculation rule for the cost of hedging reserve is applied.

- 1. The actual and aligned values of the hedging instrument and the hypothetical derivative are calculated according to the hedge accounting calculation rule.
- 2. The absolute amount of the actual value of the hedging instrument is compared with the absolute amount of the aligned value of the hypothetical derivative. The result determines how the cost of hedging reserve amounts are calculated and posted to the P&L statement. The result is stored and displayed on the hedging relationship level in the market data container.
- 3. One of the following calculation rules for the cost of hedging reserve was determined:


- 1 - Actual Value = Aligned Value

The change in the amount of the actual value is posted to the cost of hedging reserve.

- 2 - Actual Value > Aligned Value

The change in the amount of the aligned value is posted to the cost of hedging reserve.

- 3 - Aligned Value > Actual Value


The cost of hedging reserve is determined based on the lower-of test. The smaller amount of the actual and aligned value is posted to the cost of hedging reserve and the remaining amount is posted to the P/L statement.

**Note:**

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions

Define Hedging Profiles .

When you use this attribute, the critical term match is applied automatically. In this case, the aligned value check result at the release of hedge business transactions is set to Actual Value = Aligned Value.

The relevant financial transaction is valuated and posted on designation date.

Valuation

Transfer postings are made from the freestanding subpositions to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the freestanding subpositions are valuated.

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation).

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the first-day valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

**Note:**

Once postings for objects of the hedging relationship have been made, regardless of whether they result from periodend closing or from closing a financial transaction, the status of the hedging relationship cannot be changed back to a planned designation. This is only possible after all the relevant postings have been reversed.

The amounts of the planned flows for designation are updated.

The status of the planned flows for the designation is changed from Scheduled to Fixed.

The status of the hedging relationship is set to Designated.

Process Steps Executed at Release of Hedging Relationship Swap Transfer

For more information about the process steps executed at the release of an FX swap transfer, see Release Hedging Business Transactions - FX Swap Transfer.

Process Steps Executed at Release of Reclassification

The hedge accounting key figures are determined based on the settings made in the respective hedge accounting calculation type.

The elements and contract rate components are calculated once you release the reclassification, and they are then stored in the market data container.

The market value components are calculated when you release the reclassification and then again at period end during the NPV calculation.

For more information, see Hedge Accounting Key Figures

The selected hedging relationship is classified with the actual market value components, and the results are posted.

The amounts of the planned flows for reclassification are updated.

The status of the planned flows for the reclassification is changed from Scheduled to Fixed.

Process Steps Executed at Release of Dedesignation

The following process steps are executed at release of dedesignation:

The hedge accounting key figures are determined based on the settings made in the respective hedge accounting calculation type.

The elements and contract rate components are calculated once you release the dedesignation, and they are then stored in the market data container.

The market value components are calculated when you release the dedesignation and then again at period end during the NPV calculation.

For more information, see Hedge Accounting Key Figures

The selected hedging relationship is classified with the actual market value components, and the results are posted.

The amounts of the planned flows for dedesignation are updated.

The status of the planned flows for the dedesignation is changed from Scheduled to Fixed.

The status of the hedging relationship is set to Dedesignated.

Activities

- 1. To start the release of hedging business transactions, call the corresponding function on the SAP Fiori launchpad in the Hedge Accounting group or in the back-end system (transaction TPM120).
- 2. You can specify the hedging business transaction you want to release by using the following selection options:

General Selections

Company Code

Valuation Area

Up to Key Date

Transaction Selection

You can select the hedging business transaction by the transaction number of the hedging instruments involved. You can enter one or more financial transaction numbers.

Hedging Relationship Selection

You can select the hedging business transaction by the following attributes of the involved hedging relationships:

Hedging Relationship Number

Fiscal Year

Valid-From Date

Profile

Hedging Area

In the Posting Control area, you can fill the Posting Date, Posting Period, and Document Date fields. In addition, the following indicators can be set:

Save Values with Warnings

If you set this indicator, the system saves net present values and releases business transactions even if warning messages were generated during the processing of the business transactions.

Detail Log (Market Val. Calc.)

Enter Post.Date

Indicator that allows you to enter an individual posting date for hedging business transactions that are to be fixed.

Test Run

- 3. On the next screen, maintain the posting date for the relevant hedging business transactions in the FI Posting Date field.


**Note:**

When the Enter Post.Date checkbox is selected, the function cannot be carried out in multitasking mode.

**Note:**

This step only applies if you’ve selected the Enter Post.Date checkbox in the Posting Control area.

If this checkbox is not selected, the system always selects and releases the hedging business transactions with the latest date.

The checkbox can't be selected if the transaction is run in multitasking mode.

- 4. Choose Execute. The system executes the release of all selected hedging business transactions. You get a results list.


Results List

After you have executed the Release Hedging Business Transaction app, you get a results list.

The list shows the processed hedging relationships along with their processing status indicated by a green, yellow, or red status icon.

**Green Status Icon (  No Errors orWarnings)**

No error or warning messages occurred during the calculation of the net present values.

Yellow Status Icon (**Caution:**Warnings)

During the calculation of net present values, warning messages occurred. If you have set the Save Values with Warnings indicator, hedging business transactions are relased even if warnings occurred. If you haven't set this indicator, hedging business transactions with warnings get the status Errors and are not released.

Red Status Icon ((error)  Errors)

A red status has various the reasons. See the following examples:

During the calculation of net present values, error and warning messages occurred.

The prospective effectiveness test can lead to a red status for the following reasons:

The effectiveness test has been performed, but the test has found that the hedging relationship is ineffective. In this case, the message log reports this.

The effectiveness test couldn't be performed, for example, due to missing historical market data for some of the market data selection dates derived from the market data set. In this case, the message log reports an error in the market value calculations.

Using the Display Log button, you can review the posting and message log showing you the posting and calculation steps that have been performed.

Using the Market Value Calculation Details button, you get a list that shows the hedging instruments of the hedging relationships processed along with their risk-free NPV, CVA/DVA, and the total NPV calculated at designation date.

If you choose the Error log button, the system shows any error or warning messages embedded into a message structure reflecting the calculation steps performed. The Prospective Effectiveness Test process step contains sub-steps for all market data processed (either a market data scenario or market data selection date).

If you choose the Calculation Bases button, the system shows the market data used. For all market data processed (either a market data scenario or market data selection date), there is a node below which you see the specific market data within a sub-structure.

The Hedge Accounting Key Figures button takes you to the list of market value components and other key figures calculated at designation.

You first see the market value components of the hedging instruments and hypothetical derivative calculated at designation date.

The Display Effectiveness Test button takes you to the details of the prospective effectiveness test performed.

In the Hedging Relationships Details area, you see the number and the name of the hedging relationship.

In the Effectiveness Test Details area, you see the details for the effectiveness test, such as the fields Eff. Test Date, Eff. Test Type, Eff. Test Trigger (including Ref. to Bus. Trans.), the effectiveness test result (with the status Effective

or Ineffective) is displayed as a green or red icon.

2

On the Eff. Test Result tab, you get the results of the linear regression analysis (expressed in the fields Slope, R , Intercept Ratio, and t-Statistic of Slope). The results are displayed and compared with the border conditions defined in the effectiveness test method.

The H.Item/H.Instr.Values tab shows all market value components: the designated ones for the hedging instruments and the hypothetical derivatives calculated at designation and using a market data scenario or market data selection date (see corresponding columns).

The Detail Log button in the toolbar offers a detail log for each individual row.

The Display Lin. Regr. Details button navigates to the details of the linear regression analysis.

Each line refers to a market data scenario or market data selection date and contains the delta of the designated components of the hypothetical derivative (explanatory variable) and the hedging instrument (explained variable).

A graphical representation of the data points along with the calculated line is also available.

The CVA/DVA Key Figures button on the NPV detail screen takes you to a list showing the CVA and risk-free NPV of the financial transaction.

You can also access the information for the single financial transaction or the hypothetical derivative by using the Single Transaction button.

Use the Display Hedging Relationship button to navigate to the Manage Hedging Relationships app, showing you the details for the hedging relationship selected.

**More Information**

Release Hedging Business Transactions - FX Swap Transfer

Hedge Accounting for Exposure Items

Period-End Closing

Reporting

###### Release Hedging Business Transactions - FX Swap Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Release Hedging Business Transactions - FX Swap Transfer | L6 | trm09 p.124 | loio `d7734a9e957d4a33b96ad4ad7f35caab` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d7734a9e957d4a33b96ad4ad7f35caab.html?locale=en-US)

**Use**

To complete the designation process of the FX swap, the planned flows for the Hedging Relationship Swap Transfer hedging business transaction have to be fixed on swap date. The Release Hedging Business Transactions function executes this process step. It is embedded in the end-of-day processing activities as relevant market data needs to be available.

**Process Steps**

Once you execute the function, a series of automatic process steps is triggered:

- 1. On swap date, a new hypothetical derivative is created with start date of the original hedging relationship.


**Note:**

The nominal amount of the hypothetical derivative of the original hedging relationship is reduced.

- 2. The market data container values of the swapped portion of the hedging instrument are copied to the new hedging relationship.
- 3. The market data container values of the FX swap transaction are calculated.
- 4. The first day result of the new hedging relationship is calculated and posted according to the hedging relationship profile.
- 5. The valuation and classification flows of the original hedging relationship are calculated and posted.
- 6. The nominal amounts of the hedging instrument and exposure subitem of the original hedging relationship are reduced by the nominal amounts of the swap request.
- 7. The proportional amounts of the hedging reserve and cost of hedging reserve of the original hedging relationship are calculated and transferred to the newly-created exposure subitem of the new hedging relationship.

The proportional amounts are determined by the percentage of the nominal amount of the original hedging relationship that is to be swapped.

- 8. If the prospective effectiveness test is enabled for the hedging profile, and a test plan has been generated containing a record for the FX swap transfer date and a market data set, the system executes the prospective effectiveness. For more information see: Prospective Effectiveness Test Using Linear Regression

- 9. The calculation rule for the cost of hedging reserve that was determined for the original hedging relationship is not copied to the newly-created hedging relationship. The calculation rule for the cost of hedging reserve for the new hedging relationship is determined.
- 10. The date information for the exposure subitem end date is derived from the hedging area version valid on the designation date of the original hedging relationship.
- 11. The portion of the FX forward transaction that is to be transferred from the old to the newly-created hedging relationship is valuated and classified and the results are posted on swap date.
- 12. The status of the nominal amount transfer flows is set from Scheduled to Fixed.
- 13. The status of the hedging relationship is set to Designated.


**Related Information**

Release Hedging Business Transactions

###### Hypothetical Derivative (Hedge Accounting for Exposure Items)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Hypothetical Derivative (Hedge Accounting for Exposure Items) | L6 | trm09 p.125 | loio `ad50f937e3734b17ace3aa07c0febaa2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ad50f937e3734b17ace3aa07c0febaa2.html?locale=en-US)

**Use**

The hypothetical derivative is created during the release of designation for all hedging scenarios of the Hedge Accounting for Expoure Items process. The hypothetical derivative is needed for the calculation of the hedge accounting key figures and during effectiveness testing.

**Prerequisites**

The following settings in Define Hedge Accounting Calculation Type Customizing are relevant for the hypothetical derivative:

Define From-Currency

This setting is relevant for the calculation of the nominal amounts of the hypothetical derivative.

HD Fixing

Dependent on the settings of the HD Fixing field the hypothetical derivative gets a fixing date:

None

No fixing information is derived from the hedging instrument. Therefore, the hypothetical derivative for a non-deliverable forward is an FX forward.

From Non-Deliverable Forwards only

The fixing date and settlement currency are taken from the non-deliverable forward which acts as the hedging instrument. The hypothetical derivative for an NDF is an NDF.

From FX Forwards and Non-Deliverable Forwards

If the hedging instrument is a non-deliverable forward, the fixing date and settlement currency are taken from the non-deliverable forward. The hypothetical derivative is an NDF.

If the hedging instrument is an FX forward with a due date shift according to the hedging area settings, the fixing date is set to the original due date of the FX forward. As a result, the hypothetical derivative looks like a non-deliverable forward although the hedging instrument is an FX forward.

HD Rate

In the Hypothetical Der. Forward Rate field, you control how the system calculates the forward rate during the creation of hypothetical derivatives for hedging relationships. The following settings are available:

Yield Curve

The theoretical forward rate is calculated based on the yield curves of the two involved currencies.

Swap Rate

The forward rate is calculated as the sum of the spot rate and the swap rate according to the relevant swap rate curve (for more information, see also the Customizing actvities Define Swap Rate Curve Structure and Assign Swap Rate Curve Structure to Currency Pairs).

According to Evaluation Type

The system behavior for FX forwards depends on the value of the setting FX Valuation Method chosen in the evaluation type / valuation rule. In case of the valuation method Discounting Before Currency Conversion (zero method), the yield curve is used. In case of the valuation method Currency Conversion Before Discounting (par method), the swap rate is used.

From Financial Transaction

The forward rate is copied from the financial transaction.

For FX options, the system uses the yield curve.

**Note:**

For FX options as hedging instruments, the strike adjustment for the hypothetical derivative uses the spot or discounted forward rate, depending on how the intrinsic value is calculated. You can control the intrinsic value calculation with the Intrinsic Value Without Day Count Basis indicator in the evaluation type on Evaluation Control tab in Valuation Control area.

FX Option: Dates of Hypothetical Derivative

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

In the Define Hedging Profiles Customizing you can assign an underlying hedging profile for scenarios using FX options as hedging instruments. In this case the underlying FX transaction of the FX option will be designated into the hedging relationship when the FX option is executed. This setting has an impact on the exercise date of the hypothetical derivative.

The following settings in hedging area are relevant for the hypothetical derivative:

Main Data tab

In the Date Used to Determine Exp. Item for FX Option field, you define which date is used to determine the exposure item during the automated designation process of an FX option.

Select one of the following options:

Value Date of Underlying

In this case, the exposure item is determined based on the value date of the underlying transaction of the FX option.

Exercise Date of FX Option

In this case, the exposure item is determined based on the exercise date of the FX option.

The date you choose here will also be applied to due date shifts according to the settings on the General Settings tab and your designation splitting settings on the Hedge Accounting I tab. The chosen date is the basis value for shifting to the correct exposure item period.

This setting also has an impact on the dates of the hypothetical derivative, dependent on the setting in FX Option: Dates of Hypothetical Derivative field in the relevant hedge accounting calculation type.

Hedge Accounting II tab

The setting in the Extend Period of Hypothetical Derivative field in the hedging area on Hedge Accounting I tab in Designation Splitting area is relevant.

If you choose to extend the period of the hypothetical derivative, the due date of the hypothetical derivative becomes the due date of the corresponding hedging instrument plus the payment term.

If you do not want to extend the hypothetical derivative period, the value date of the hypothetical derivative is the same as the due date of the hedging instrument.

General Settings tab

The setting for the Due Date Shift field in the hedging area data on General Settings tab in Hedging Classification area.

BOMN1 - Beginning of Next Month

If you opt for this type, the end date of the hedged item and the value date of the hypothetical derivative (representing the exposure) is shifted to the first day of the following month.

EOMN1 - End of Next Month

If you opt for this value, the end date of the hedged item and the value date of the hypothetical derivative (representing the exposure) is shifted to the last day of the following month.

**Hedging Instrument: FX Forwards/Swaps**

If the hedging instrument is an FX forward or FX swap, the nominal amounts and the FX rate are calculated in the following way:

- 1. The system takes the nominal amount in the From-Currency from the hedging instrument (securing leg in case of swaps) as the first nominal amount for the hypothetical derivative.
- 2. Then the sytem determines the FX rate according to the settings in HD Rate field in hedge acconting calculation type.
- 3. The second nominal amount is calculated based on the first nominal amount and the determined FX rate.


The hypothetical derivative also needs dates. How the dates are derived depends on several settings.

Start Date

If the hedging instrument is a FX forward, the start date of the hypothetical derivative is the designation date.

If the hedging instrument is a swap, the start date of the new hypothetical derivative is the designation date of the original hedging relationship.

**Note:**

Exception: If the original hedging relationship has been created during the initialization of the Hedge Accounting for Exposure Items, system takes the contact date of the original hedging instrument as start date of the hypothetical derivative.

Example:

Date of initialization: 01/01/2018

Start date of original hedging relationship created during initialization: 01/01/2018

Contract date of original hedging instrument: 08/16/2017

During the creation of the hypothetical derivative due to a swap transfer the system sets the start date of the new hedging relationship on the 08/16/2017.

Explanation:

The start date of the hypothetical derivative is the date, the market data are read (from market data table or from the original hedging instrument), which are used for the calculation of the nominal values and the contract rate of the hypothetical derivative. Therefore, the hypothetical derivative is constructed as if the new hedging relationship already existed at the original designation date.

Fixing Date

Whether the hypothetical derivative has a fixing date or not depends on the kind of hedging instrument, the setting in HD Fixing field in the hedge accounting calculation type, and the settings for due date shift and extended period of HD in the hedging area.

Value Date

Which date is taken as value date of the hypothetical derivative dependends on the settings for the due date shift and the extended period of HD in the hedging area.

[figure TRM09-F033 - Overview: Dates of Hypothetical Derivative (HInst = FX Forward/FX Swap)]

Overview: Dates of Hypothetical Derivative (HInst = FX Forward/FX Swap)

**Hedging Instruments are FX Options/Collar FX Options**

In case the hedging instrument is an FX option or collar FX option, the nominal amounts and the FX rate are calculated in the following way:

- 1. The system takes the nominal amount in the From-Currency from the hedging instrument as the first nominal amount for the hypothetical derivative.
- 2. System takes the strike from the hedging instrument.


If in HD Rate field (in the hedge accounting calculation type) the value From Financial Transaction is set, the strike is the rate of the hypothetical derivative.

If in HD Rate field (in the hedge accounting calculation type) the value From Financial Transaction is not set, the system checks whether the hypothetical derivative is in the money with this rate. If the hypothetical derivative is in the money, the system calculates the rate of the hypothetical derivative to bring the hypothetical derivative at the money (intrinsic value = 0).

- 3. The second nominal amount is calculated based on the first nominal amount and the strike.


The hypothetical derivative also needs dates. How the dates are derived depends on several settings

Start Date

The start date of the hypothetical derivative is the designation date.

**Note:**

Exception: If the original hedging relationship has been created during the initialization of the Hedge Accounting for Exposure Items, system takes the contract date of the original hedging instrument as start date of the hypothetical derivative.

Example:

Date of initialization: 01/01/2018

Start date of original hedging relationship created during initialization: 01/01/2018

Contract date of original hedging instrument: 08/16/2017

During the creation of the hypothetical derivative due to a option transfer the system sets the start date of the new hedging relationship on the 08/16/2017.

Explanation:

The start date of the hypothetical derivative is the date, the market data are read (from market data table or from the original hedging instrument), which are used for the calculation of the nominal values and the contract rate of the hypothetical derivative. Therefore, the hypothetical derivative is constructed as if the new hedging relationship already existed at the original designation date.

Exercise Date and Value Date

No shifts defined in hedging area

The exercise date of the hypothetical derivative is the exercise date of the hedging instrument.

The value date of the hypothetical derivative is the value date of the underlying of the hedging instrument.

Due Date Shift or Extended Period defined in hedging area

It depends on several settings how the exercise date and the value date of the hypothetical derivative are dertermined:

Due Date Shift or Extended Period in Hedging Area: Determine Exercise Date and Value Date of Hyp. Der.

|Setting in Hedge Acct. Calc.Type for FX Option: Dates of Hypothetical Derivative|Setting in Hedging Area: Date Used to Determine Exp. Item for FX Option|Setting in Hedging Profile: Underlying Designated to Hedging Releationship|Exercise Date of Hypothetical Derivative|Value Date of Hypothetical Derivative|
|---|---|---|---|---|
|Default|Value date of underlying|No|Shifted|Shifted according to hedging area setting:|


|Setting in Hedge Acct. Calc.Type for FX Option: Dates of Hypothetical Derivative|Setting in Hedging Area: Date Used to Determine Exp. Item for FX Option|Setting in Hedging Profile: Underlying Designated to Hedging Releationship|Exercise Date of Hypothetical Derivative|Value Date of Hypothetical Derivative|
|---|---|---|---|---|
| | | |Keeps distance to value date Shifted value date number of days between exercise date and value date of HInst|Due date shift First or last day of following month after due date of HInst Extended period Due date of HInst + payment term Due date shift + Extended period First or last day of following month after due date of HInst + Payment|
|Default|Value date of underlying|Yes|No shift Exercise date of HInst|Shifted according to hedging area setting: Due date shift First or last day of following month after due date of HInst Extended period Due date of HInst + payment term Due date shift + extended period|


|Setting in Hedge Acct. Calc.Type for FX Option: Dates of Hypothetical Derivative|Setting in Hedging Area: Date Used to Determine Exp. Item for FX Option|Setting in Hedging Profile: Underlying Designated to Hedging Releationship|Exercise Date of Hypothetical Derivative|Value Date of Hypothetical Derivative|
|---|---|---|---|---|
| | | | |First or last day of following month after due date of HInst + payment term|
|Default|Exercise date|No/Yes|Shifted according to hedging area setting: Due date shift First or last day of following month after exercise date of HInst Extended period Exercise date of HInst + Payment Term Due date shift + extended period First or last day of following month after exercise date of HInst + Payment|Shifted Keeps distance to exercise date Shifted exercise date + number of days betweween exercise date and value date of HInst|
|Shift only value date of underlying|Value date of underlying|No/Yes|No shift Exercise date of HInst|Shifted according to hedging area setting: Due date shift First or last day of following month after due date of HInst|


|Setting in Hedge Acct. Calc.Type for FX Option: Dates of Hypothetical Derivative|Setting in Hedging Area: Date Used to Determine Exp. Item for FX Option|Setting in Hedging Profile: Underlying Designated to Hedging Releationship|Exercise Date of Hypothetical Derivative|Value Date of Hypothetical Derivative|
|---|---|---|---|---|
| | | | |Extended period Due date of HInst + payment term Due date shift + extended period First or last day of following month after due date of HInst + payment term|
|Shift only value date of underlying|Exercise date|No/Yes|No shift Exercise date of HInst|Shifted to the date to which the exercise date is shifted according to hedging area settings: Due date shift First or last day of following month after exercise date of HInst Extended period Exercise Date of HInst + payment term Due date shift + extended period First or last day of following month after exercise date of HInst + payment term|


**Example:**

In the following images, you can see examples how the dates are derived for the hypothetical derivative, when a due date shift to the end of next month is defined in the hedging area.

The following cases are shown:

Default setting in the hedge accounting calculation type in FX Option: Dates of Hypothetical Derivative field

The Value date of the underlying is used to determine exp. item

- Example 1: The underlying FX transaction of the FX option will not be designated to the hedging relationship during the exercise of the FX option. In addition, a due date shift to the end of next month is defined in the hedging area.

In this case, the value date of the hypothetical derivative is shifted to the end of next month and the exercise date of the hypothetical derivative is 2 days before (= the same number of days before the value date as in the hedging instrument).

- Example 2: The underlying FX transaction of the FX option will be designated to the hedging relationship during the exercise of the FX option. In addition, a due date shift to the end of next month is defined in the hedging area.


In this case, the exercise date of the hedging instrument is also the exercise date of the hypothetical derivative (no shift applied). The value date of the hypothetical derivative is shifted to the end of next month.

Example 3: Exercise date of FX option used to determine exp. item

In this case, it doesn't matter whether the underlying is designated to the hedging relationship or not. In both cases, the exercise date is shifted according to the settings in the hedging area to the end of next month and the value date keeps the distance to the exercise date.

[figure TRM09-F034 - Shift Only Value Date setting in the hedge accounting calculation type in FX Option: Dates of Hypothetical Derivative field]

Shift Only Value Date setting in the hedge accounting calculation type in FX Option: Dates of Hypothetical Derivative field

Example 1: Value date of underlying used to determine exp. item

If the exercise date of the hedging instrument is the 31.3. and the value date of the underlying is the 2.4. the value date of the hypothetical derivate is shifted to the EoNM which is the 31.05.

In this case, it doesn't matter whether the underlying is designated to the hedging relationship or not. In both cases, the exercise date is not shifted and the value date is shifted according to the settings in the hedging area to the end of next month.

Example 2: Exercise date of FX option used to determine exp. item

In this case, it doesn't matter whether the underlying is designated to the hedging relationship or not. In both cases, the exercise date is not shifted and the value date is shifted to the end of next month (= the date to which the exercise date is shifted according to the settings in the hedging area to determine the exposure item).

If the exercise date of the hedging instrument is the 31.3. and the value date of the underlying is the 2.4. the value date of the hypothetical derivate is shifted to the EoNM which is in this case the 30.04.

[figure TRM09-F035 - If the exercise date of the hedging instrument is the 31.3. and the value date of the underlying is the 2.4. the value date of the hypothetical derivate is shifted to the EoNM which is in this case the 30.04.]

###### Hedge Accounting Key Figures

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Hedge Accounting Key Figures | L6 | trm09 p.135 | loio `7b217458acc62060e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b217458acc62060e10000000a44147b.html?locale=en-US)

**Use**

For financial transactions that are assigned as hedging instruments in designated hedging relationships created during the Hedge Accounting for Exposure Items process, the system calculates hedge accounting specific key figures. They are required for the calculation of the hedging reserve and cost of hedging reserve according to the relevant hedge accounting rule.

The hedge accounting key figures are calculated for the hedging instrument and for the hypothetical derivative. If a financial transaction is part of more than one hedging relationship, the calculation is made separately for each of the hedging relationships.

The calculation is always made for the nominal value of the financial transaction. The prorated amounts relevant for the specific hedging relationships are also calculated and stored but only for information purposes. For the generation of the flows the prorated amounts are determined within hedge accounting from the 100% nominal value.

**Note:**

Risk-free key figures do not contain CVA/DVA portion

The following kinds of key figures are calculated:

Elements and Contract Rate Components

These values are only calculated at the release of the designation triggered by Release Hedging Business Transactions function available as app on SAP FIORI launchpad or in backend (transaction TPM120)

**Note:**

They are not calculated for the target hedging relationship in case of a designation resulting from a swap transfer.

The values are stored in the market data container.

The element values are required for the determination of the calculation rule for the cost of hedging reserve. See also: Release Hedging Business Transactions

Market Value Components

The component values are required for the valuation that takes place during the release of hedging business transactions and at period end.

These values are calculated at the following points in time:

at the release of designation of hedging relationships triggered by Release Hedging Business Transactions function available as app on SAP FIORI launchpad or in backend (transaction TPM120)

at the release of reclassification for hedging relationships triggered by Release Hedging Business Transactions function available as app on SAP FIORI launchpad or in backend (transaction TPM120)

at the release of Hedging Relationship Swap Transfer triggered by Release Hedging Business Transactions function available as app on SAP FIORI launchpad or in backend (transaction TPM120)

at the release of dedesignation of hedging relationships triggered by Release Hedging Business Transactions function available as app on SAP FIORI launchpad or in backend (transaction TPM120)

at period end during the NPV calculation using Calculate Net Present Values - Including CVA and DVA function available as app on SAP FIORI launchpad or in backend (transaction TPM60CVA).

**View the Calculated Hedge Accounting Key Figures**

Market Data Container

You can see the values stored in market data container from within the hedging relationship using the Manage Hedging Relationships function (transaction TPM100) also available as app on the SAP Fiori Launchpad. Choose the Display H. Rel. Related Trans. pushbutton on the right side next to the number of the hedging relationship. Then choose the designation business transaction. On the following screen choose the Display Market Data pushbutton. On the screen Hedge-Specific Market Data choose the Acctg Key Figs tab. You see the amount of the hedge accounting key figures calculated at the release of designation.

Here's what that looks like (English only):

[figure TRM09-F036 - Results List of Valuation]

Results List of Valuation

You can view the calculated hedge accounting key figures from the results list of the Calculate Net Present Values - With CVA and DVA function. Mark a row and choose the Hedge Accounting Key Figure pushbutton on top of the list to navigate to the calculation details, if the selected financial transaction is assigned as hedging instrument in designated hedging relationships created during the process Automated Exposure Item Hedging (FX Risk).

Here's what that looks like (English only):

[figure TRM09-F037 - Net Present Value Table]

Net Present Value Table

You can view the calculated hedge accounting key figures in the Enter Net Present Values app. Mark a row and choose the Hedge Accounting Key Figure pushbutton on top of the list to navigate to the calculation details, if the selected financial transaction is assigned as hedging instrument in designated hedging relationships created during the process Automated Exposure Item Hedging (FX Risk).

Here's what that looks like (English only):

[figure TRM09-F038 - In the List of Hedge Accounting Key Figures]

In the List of Hedge Accounting Key Figures

**Hedge Accounting Calculation Type**

Define From-Currency

For the correct calculation of the hedge accounting key figures it is necessary to define uniquely which of the currencies involved in the hedging instruments is the from-Currency and which is the to-Currency. you can see the amount calculated for the nominal value and also the prorated amount relevant for the specific hedging relationships.

You establish this in the Define Hedge Accounting Calculation Type Customizing by choosing the Leading Currency, the Following Curreny, or the Traded Currency as From-Currency.

**Note:**

Under Define Leading Currency you configure the leading currencies for various currency pairs.

The setting has two effects within hedge accounting:

The hedging instrument nominal in the from-currency is taken over into the hypothetical derivative. The hypothetical derivative nominal in the to-currency is then calculated based on the forward rate of the hypothetical derivative.

For FX forwards as hedging instruments, the calculation of elements and market value components requires the decomposition of the contract rate F. The result depends on whether the contract rate is used in direct or indirect quotation. This setting has the effect that the rate used satisfies the equation N_t = N_f * F, where N_t and N_f are the hedging instrument nominals in the to-currency and from-currency respectively.

Spot Rate at Release of Designation

This setting controls which spot rate is used in the calculations performed at the release of designation of hedging relationships triggered by Release Hedging Business Transactions function available as app on SAP FIORI launchpad or in backend (transaction TPM120). The following settings are available:

Default

Use the setting Default, if you want that at the release of designation the NPV is calculated in the same way as with function Calculate NPV - Including CVA and DVA on the same key date.

For FX forward transactions the change of the spot rate between contract conclusion and release of designation is reflected in the spot component of the NPV.

From Financial Transaction

Use the setting From Financial Transaction, if you want the following market value components to be zero at designation:

FX forwards: Spot component of hedging instrument and hypothetical derivative

Options: Intrinsic value of hypothetical derivative

From Market Data Table

you can see the amount calculated for the nominal valueThe system uses the spot rate of market data table for all calculations.

Use the setting From Market Data Table, if you want that at release of designation the NPV is calculated in the same way as with Calculate NPV - Including CVA/DVA function on the same key date and if you want the following market value components to be zero at designation:

FX forwards: Spot component of hedging instrument and hypothetical derivative

Options: Intrinsic value of hypothetical derivative

For FX forward transactions the change of the spot rate between contract conclusion and release of designation is reflected in the NPV other component.

Used Spot Rates for the Calculation of Hedge Accounting Key Figures Depending on this Setting

|Value in Spot Rate at Release of Designation Field|Hedging Instrument: Contract Rate Decomposition + Elements|Hypothetical Derivative: Rate Decomposition, Strike Adjustment, Nominals + Elements*|Market Value Components for Hedging Instrument and Hypothetical Derivative**|
|---|---|---|---|
|Default|s0a|s0a***|s0m = sd|
|From Financial Transaction|s0a|s0a***|s0a***|
|From Market Data Table|s0m = sd|s0m = sd|s0m = sd|


Notation:

t = start date of the hedging instrument

0

t = designation date

d

0a 0a 0m 0

s = spot rate in the hedging instrument, which is valid at t . It can differ from the spot rate in the market data table s for the day t .

0m

s = spot rate in the market data table at the contract date of the hedging instrument

d

s = spot rate in the market data table at t

d

**Note:**

-  In case of a swap transfer, the spot rates in this column refer to the original hedging instrument and the original designation date.
- *The expected exposure calculation during the determination of CVA/DVA never uses the spot rate of the financial transaction.
- **In case the spot rate in an option is zero, the system uses s0m instead.


Options: NPV Others Component

This setting controls the calculation of the market value component NPV Others for FX options.

The following settings are available for the market value component NPV Others at the time of designation:

No Calculation

The system does not calculate the component NPV Others.

Calculation Without CVA/DVA

System calculates the component NPV Others as the difference between the option premium and the calculated total NPV. But the CVA/DVA is only distributed to the market value components Time Value, Intrinsic Value and CCBS.

**Note:**

If you want to calculate the market value component NPV Others for FX options, you must set the flow type used for the option premium to fictitious in the Customizing under Treasury and Risk Management Basic Analyzer Settings Valuation

Cash Flow Indicator Assign Cash Flow Indictaor to Flow Types .

Discounting of Elements

At the release of designation of hedging relationships, the system calculates the elements (hedge accounting key figures ELEM_FWD, ELEM_CCBS, ELEM_OTHER) for the hedging instrument and for the hypothetical derivative. The actual (hedging instrument) and aligned (hypothetical derivative) elements are used in the determination of the posting logic (calculation rule cost of hedging reserve).

This setting controls whether the elements calculated at release of designation are discounted or not.

Discounted

If you have entered a payment term shift in the hedging area, your hypothetical derivatives have different times to maturity than the hedging instruments. So, the discount factors will differ which is influencing the posting logic.

Undiscounted

This setting has the effect, that the excluded (undesignated) element will correspond to the amount that has accumulated in the cost of hedging reserve at the end of the hedging relationship.

Sign of Elements

At the release of designation of hedging relationships, the system calculates the elements (hedge accounting key figures ELEM_FWD, ELEM_CCBS, ELEM_OTHER). The actual (hedging instrument) and aligned (hypothetical derivative) elements are used in the determination of the posting logic (hedge accounting calculation rule). This setting controls, whether the sign of the elements calculated at release of designation is influenced by the sign of the nominal amount.

Use

Absolute Amount of Nominal

The sign of the nominal amount does not impact the sign of the elements.

Consider Sign of Nominal

The sign of the nominal amount impacts the sign of the elements.

Hypothetical Der. Forward Rate

This setting controls how the system calculates the forward rate during the creation of hypothetical derivatives for hedging relationships. The following settings are available

Yield Curve

The theoretical forward rate is calculated based on the yield curves of the two involved currencies.

Swap Rate

The forward rate is calculated as the sum of the spot rate and the swap rate according to the relevant swap rate curve (see also Define Swap Rate Curve Structure and Assign Swap Rate Curve Structure to Currency Pairs).

According to Evaluation Type

The system behavior for FX forwards depends on the value of the setting FX Valuation Method chosen in the evaluation type / valuation rule. In case of the valuation method Discounting Before Currency Conversion (zero method), the yield curve is used. In case of the valuation method Currency Conversion Before Discounting (par method), the swap rate is used.

From Financial Transaction

The forward rate is copied from the financial transaction.

For FX options, the system uses the yield curve.

**Note:**

For FX options as hedging instruments, the strike adjustment for the hypothetical derivative uses the spot or discounted forward rate, depending on how the intrinsic value is calculated. You can control the intrinsic value calculation with the Intrinsic Value Without Day Count Basis indicator in the evaluation type on Evaluation Control tab in Valuation Control area.

Market Value Component Calculation

This setting controls the calculation of the market value components for hedging instruments and hypothetical derivatives in hedging relationships. The following settings are available:

Complete

The market value of FX forwards is decomposed into four components:

Spot, reflecting the effect of the change in the FX spot rate between inception and valuation. The spot component is discounted.

Forward, reflecting the effect of the change in the FX forward rate between inception and valuation.

CCBS, reflecting the effect of cross-currency basis spreads on the market value.

Others, reflecting other influences such as, for example, bank fees.

The system calculates the Forward, CCBS, and Others Element.

The market value of FX options is decomposed into three components:

Intrinsic value, reflecting the difference between spot/forward and strike.

Time value, reflecting the possibility of changes in option value based on the volatility of the underlying.

CCBS, reflecting the effect of cross-currency basis spreads on the market value.

Simple

The market value of FX forwards is decomposed into two components:

Spot, reflecting the effect of the change in the FX spot rate between inception and valuation. The spot component is not discounted.

Forward, reflecting the difference between the spot component and the full market value.

The system only calculates the Forward Element.

The market value of FX options is decomposed into two components:

Intrinsic value, reflecting the difference between spot/forward and strike.

Time value, reflecting the possibility of changes in option value based on the volatility of the underlying

Use

Use the setting Complete if you require an accurate separation of all relevant effects into different market value components.

Use the setting Simple if its accuracy suffices for your needs, and you want to import less market data (for example, no cross-currency basis spreads).

**Note:**

The calculation of the NPV Others component of the market value of FX options can be controlled via a separate setting in the hedge accounting calculation type (FX Options: NPV Others).

HD Fixing

This setting controls how the system determines the fixing information during the creation of hypothetical derivatives for hedging relationships. The following settings are available:

None

No fixing information is derived from the hedging instrument. Therefore, the hypothetical derivative for a non-deliverable forward is an FX forward.

From Non-Deliverable Forwards only

The fixing date and settlement currency are taken from the non-deliverable forward which acts as the hedging instrument. The hypothetical derivative for an NDF is an NDF.

From FX Forwards and Non-Deliverable Forwards

If the hedging instrument is a non-deliverable forward, the fixing date and settlement currency are taken from the non-deliverable forward. The hypothetical derivative is an NDF.

If the hedging instrument is an FX forward with a due date shift according to the hedging area settings, the fixing date is set to the due date of the FX forward. As a result, the hypothetical derivative looks like a non-deliverable forward although the hedging instrument is an FX forward.

This setting is relevant during the calculation of the net present value of the hypothetical derivative if in the relevant evaluation type on Evaluation Control 2 tab the FX Valuation Method is set to Currency Conversion before Discounting and in addition, in the FX Fixing Details field Consider Fixing Date and Settlement Currency is chosen. If this is the case, the currency translation is done with the rate at the fixing date.

FX Option: Dates of Hypothetical Derivative

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

In the Define Hedging Profiles Customizing, you assign the hedge accounting calculation types to hedging profiles corresponding to the scenarios for Hedge Management and Accounting of Net Open Exposures.

**Currency Notation**

- Currency A = From-Currency

- Currency B = To-Currency


**Evaluation Currency**

In case a conversion to evaluation currency is necessary, this is done at the end of the calculation using the current spot rate.

**Note:**

In the case the calculation of the hedge accounting key figures is triggered by function Release Business Transaction (available as app on SAP FIORI Launchpad or in backend (transaction TPM120)) system uses the valuation currency.

In Calculate Net Present Values - Including CVA and DVA function which is available as app on SAP FIORI launchpad or in

backend (transaction TPM60CVA) you can specify the evaluation currency on the selection screen, or if the Evaluation Parameter Derivatn flag is marked the valuation currency is taken, or if this flag not set, the system takes the position currency.

Market value components are stored in evaluation currency, elements are stored in currency B.

**Points in Time**

The following points in time have a granularity of one day. They are logical key dates, which must not coincide with the system date on which the corresponding operation is entered in the system.

t = start date of the financial transaction

0

t = designation date

d

t = valuation date

v

t = end date of hedging instrument (payment date for FX forwards and for NDFs)

e

t = end date of hypothetical derivative

x

In most cases is t = t .

0 d

On t , we must distinguish between the creation time t of the financial transaction and the time of market data import t on that day, to distinguish between the spot rate which is entered in the financial transaction, and the spot rate in the market data table.

0 0a 0m

Exchange Rates

|Variable|Symbol/Formula|Comment|
|---|---|---|
|Cashflow at time ti in currency A|CFA i| |
|Spot rate at time t for multiplicative conversion from currency A to currency B i|SA,B * CF = CF i A i B i|SA,B = (S ) i B,A i -1|
|Forward rate at time ti for time tj|FA,B * CF = CF i,j A j B j|A forward contract that is fair in t allows exchanging CF against CF in t. i A B j|


Discount Factors

|Variable|Symbol|
|---|---|
|Discount factor without cross currency basis spread (CCBS) in currency A at time ti for time tj (without credit spreads)|DA i,j|
|Discount factor with cross currency basis spread (CCBS) in currency A at time ti for time tj (without credit spreads)|Dc,A i,j|


Discount factors are a functions D(r) of interest rate r, which in turn depend on t, t and A.

i j

**Example:**

r(tj) = a point in the yield curve, which is valid at time ti for currency A

The function D(r) depends on the calculation convention.

**Example:**

[figure TRM09-F039 - Function D(r)]

Function D(r)

CCBS also depend on t, t, and two currencies. There can be different approaches how CCBS are incorporated in the calculation. In the following, we understand the discount factors to be the ones, which are calculated by the yield curve framework based on your settings there.

i j

Forward Rates

[figure TRM09-F040 - Theoretical forward rate with CCBS]

Theoretical forward rate with CCBS

[figure TRM09-F041 - Theoretical forward rate without CCBS]

Theoretical forward rate without CCBS

**Note:**

For reasons of readability, in the following, let all exchange rates be for multiplicative conversion from currency A to currency B, that is, we omit the subscript .

A,B

Note the difference between theoretical forward rates F and actual market forward rates F

act

Let all quantities with the subscript refer to the hypothetical derivative, and all quantities without that subscript to the hedging instrument.

Y

**General Remarks for the Calculated Elements and Components**

In the following you see the detailed descriptions of the hedge accounting key figures calculation for the different kinds of financial transactions including the calculation of the CVA/DVA key figures.

For each key figure category, the tuple risk free key figure (KF_RF) / key figure (KF) / CVA portion (CVA_KF) / DVA portion (DVA_KF) is related to the equation KF=KF_RF – CVA_KF – DVA_KF

If the relevant position management procedure does not contain a CVA/DVA type the system does not calculate the CVA/DVA key figures. In this case NPV_*_RF components are not calculated but only the NPV_* key figures hence when CVA and DVA are zero NPV_*_RF = NPV_*

**Key Figures for FX Forwards and NDFs**

Parameter of Hedging Instrument

|Parameter|Symbol/Formular|Comment|
|---|---|---|
|Nominal in currency A|NA|N has a positive sign for an incoming flow and a negative sign for an outgoing flow|
|Nominal in currency B|NB| |
|Spot rate|S0a|S is the spot rate of the financial transaction, which is valid at t . It can differ from the spot rate in the market data table S for the day t . 0a 0a 0m 0|
|Actual contract forward rate|Fact = -N /N 0,e B A|This will usually not exactly match the theoretical rate Fact unequal F , due to 0,e c 0,e|


|Parameter|Symbol/Formular|Comment|
|---|---|---|
| | |reasons such as e.g. bank fees.|


**Elements and Contract Rate Components**

|Description|Symbols|Definition/Comment|Name of Key Figure|
|---|---|---|---|
|Hedging Instrument| | | |
|Spot component of the contract rate|s|s=s0a|RATE_SPOT|
|Interest rate component of contract rate|z|F - s F =s*D /D The used spot rate depends on the setting for spot rate at designation in the Customizing of the hedge accounting calculation type. It is either s or s . 0,e 0,e A 0,e B 0,e 0a 0m|RATE_FWD|
|CCBS component of contract rate|c|Fc - F 0,e 0,e|RATE_CCBS|
|Other component of the contract rate|o|Fact0,e - s - z - c|RATE_OTHER|
|Theoretical CCBS-free contract rate|k|Fact - c 0,e|RATE_NOCBS|
|Elements|**Note:** The forward and CCBS elements are amounts which influence the posting logic, but are calculated differently from the market value components. The actual elements refer to the hedging instruments, while the aligned elements refer to the hypothetical derivative. Decomposition of the contract rate: F = s + z + c + o The components of the contract rate play a role during the calculation of the components of the Market Value at valuation, while the Elements are required for the determination of the posting logic. act 0,e| | |
|Actual forward element|EZ|DB * N * z 0,e A|ELEM_FWD|
|Actual CCBS element|EC|DB * N * c 0,e A|ELEM_CCBS|
|Actual Other element|EO|DB * N * o 0,e A|ELEM_OTHER|
|Hypothetical derivative| | | |
|Spot component of the contract rate|sY|It depends on the setting for spot rate at designation in the Customizing of the hedge accounting calculation type whether s0a or s0m is used. .|RATE_SPOT|
|Interest rate component of the contract rate|zY|Fd,x - sY|RATE_FWD|


|Description|Symbols|Definition/Comment|Name of Key Figure|
|---|---|---|---|
|CCBS component of the contract rate|cY|Fc - F d,x d,x|RATE_CCBS|
|Other component of the contract rate|oY|= 0 by definition|RATE_OTHER|
|Contract rate of the hypothetical derivative|FY,Contr|sY + zY + cY = Fc d,x|Stored in hypothetical derivative master data, not in market data container, hence no key figure|
|Theoretical CCBS-free contract rate|kY|FY,Contr - cY|RATE_NOCBS|
|Nominal in currency A|NY,A|= -NA|Stored in hypothetical derivative master data, not in market data container, hence no key figure|
|Nominal in currency B|NY,B|-NY,A * FY,contr|Stored in hypothetical derivative master data, not in market data container, hence no key figure|
|Elements| | | |
|Aligned forward element|EY,Z|DB * N * z d,x Y,A Y|ELEM_FWD|
|Aligned CCBS element|EY,C|DB * N * c d,x Y,A Y|ELEM_CCBS|
|Aligned Other element|EY,O|DB * N * o d,x Y,A Y|ELEM_OTHER|


Market Value Components of the Hedging Instrument

The market value of the hedging instrument and hypothetical derivative can be split into the components spot, forward, CCBS, and others.

|Description|Symbol|Definiton/Calculation|Name of Corresponding Key Figure|
|---|---|---|---|
|Market value of the hedging instrument according to the zero coupon method (creditrisk-free, including CCBS)|Mzero,rf|Dc,A * N * S + D * N v,e A v c,B v,e B|NPV_RF|
|Market value of the hedging instrument according to the par method (credit-risk-free)|Mpar,rf|Dc,B *( N + F * N ) v,e B act v,e A|NPV_RF|
|Credit-risk-free market value, depending on the choice of the accounting relevant calculation method|Mrf|Mrf=Mpar,rf or Mrf=Mzero,rf|NPV_RF|
|The credit-risk-free market value can be decomposed into the following components| | | |


|Description|Symbol|Definiton/Calculation|Name of Corresponding Key Figure|
|---|---|---|---|
|Theoretical CCBS-free market value|Mnoc,rf|DB * N * (F - k) v,e A v,e|Not persisted, hence no key figure|
|Spot component of the creditrisk-free market value|Ms,rf|DB * N * (S - s) v,e A v|NPV_SPOT_RF|
|Forward component of the credit-risk-free market value|Mz,rf|DB * N * (F - S - z) v,e A v,e v|NPV_FWD_RF|
|CCBS component of the creditrisk-free market value|Mc,rf|Mzero-Mnoc|NPV_CBS_RF|
|Other-component of the creditrisk-free market value|Mo,rf|Mrf - Ms,rf -Mz,rf -Mc,rf|NPV_OTH_RF|


**Note:**

By definition, it follows that Mrf = Ms,rf + Mz,rf + Mc,rf + Mo,rf.

The market value of the hypothetical derivative can be decomposed in the same way, with the following exceptions:

All discount factors and forward rates refer to tome t instead t

x e

All contract rate components (k , z ) refer to hypothetical derivative.

y y

Swap

In case of a swap/rollover of an existing hedging relationship with FX forward as hedging instrument, at release of the designation the following happens:

The basic equations remain the same, however different dates enter the calculation

Creation of the hypothetical derivative:

Start date is the start date of the original hedging relationship

End date of the securing leg + original payment term shift

**Note:**

The two sides of a swap are called offsetting leg and securing leg:

The offsettings leg neutralizes the effect of the original hedging instruments.

The securing leg acts as the new hedging instrument.

The rate is calculated based on the original designation market data read from the market data table at t .

d,orig

Values stored in market data container:

| |Rate Components|Market Value Components|Elements|
|---|---|---|---|
|Swap Legs|As of swap contract date|As of swap contract date|As of swap contract date|
|Previous swap legs (in case of swapping a|Copied from market data container of previous hedging|Copied from market data container of previous hedging|Copied from market data container of previous hedging|


| |Rate Components|Market Value Components|Elements|
|---|---|---|---|
|swap)|relationship|relationship|relationship|
|Original hedging instrument|Copied from market data container of previous hedging relationship|Copied from market data container of previous hedging relationship|Copied from market data container of previous hedging relationship|
|Hypothetical derivative|As of designation date of original hedging relationship|As of designation date of original hedging relationship|As of designation date of original hedging relationship|


**Key Figures for FX Options**

Basic Quantities

|Description|Symbol|Definition/Calculation|
|---|---|---|
|Market value of option including CCBS|M|According to Black/Scholes equation of the standard price calculator, with CCBS added to yield curve|
|Market value of option without CCBS|Mnoc|According to Black/Scholes equation of the standard price calculator, without CCBS added to yield curve|
|CCBS-free intrinsic value of option|Mi|According to standard price calculator logic for CCBS-free intrinsic value. The intrinsic value is calculated via the discounted forward rate or via the spot rate depending on your settings in the evaluation type.|
|CCBS component of option market value|Mc|M - Mnoc|
|Time value of option|Mt|Mnoc - Mi|
|Other-component (NPV_OTHER) Only calculated if you made the required setting in hedge accounting calculation type.|Mo|- P - M, with P = option premium|


The market value of the hypothetical derivative can be decomposed in the same way except the other-component (NPV_OTHER), which is not calculated for the hypothetical derivative.

At designation, the hypothetical derivative is constructed in the following way:

If by copying the strike from the hedging instrument into the hypothetical derivative, the hypothetical derivative would be in the money, calculate the strike of the hypothetical derivative so that it is at the money. That is, in that case the strike of the hypothetical derivative is F , the theoretical CCBS-free forward rate until the exposure due date.

d,x

If by copying the strike from the hedging instrument into the hypothetical derivative, the hypothetical derivative is ATM (at the money) or OTM (out of the money), the strike is copied from the hedging instrument.

The actual and aligned values M , M , M and M are calculated and persisted at designation, because they are needed later to determine the posting logic. For options, there is no distinction between elements and market value components.

c t Yc Yt

At valuation, at the release of dedesignation and at the release of reclassification, M , M and M are calculated for the hedging instrument and for the hypothetical derivative.

c t i

The algorithm that distributes the CVA/DVA of an option to its intrinsic value, time value, and CCBS components, ensures that the CVA/DVA portion of the intrinsic and time value components cannot become larger than those components themselves.

**Credit and Debit Value Adjustments (CVA / DVA)**

CVA and DVA are calculated for the hedging instruments, but not for the hypothetical derivative (i.e. CVA and DVA of hypothetical derivatives are always zero).

For financial transactions which are part of a netting group, CVA and DVA are calculated on the level of the netting group and then distributed to the transaction.

CVA and DVA are distributed to the market value components according to the algorithm modified net relative fair value approach (MNRFVA):

- 1. Add CVA and DVA to obtain the net CVA/DVA
- 2. If all market value components are zero, distribute the CVA/DVA equally among them.
- 3. If all non-zero market value components have the same sign, distribute the CVA/DVA proportionally among them.
- 4. Otherwise, distribute the CVA/DVA proportionally among those components with the appropriate sign (positive in case of a net CVA, negative in case of a net DVA).


**Note:**

This approach is chosen, to prevent the “blowing up” of distributed CVA/DVA amounts due to division by small numbers.

For each key figure category, the tuple risk free key figure (KF_RF) / key figure (KF) / CVA portion (CVA_KF) / DVA portion (DVA_KF) is related by the equation KF = KF_RF – CVA_KF – DVA_KF. Hence, we have the following further quantities:

|Description|Symbol|Definition/Calculation|Name of corresponding key figure category|
|---|---|---|---|
|CVA of spot component of market value|CVAS|According to the MNRFVA described above|CVA_SPOT|
|DVA of spot component of market value|DVAS|According to the MNRFVA described above|DVA_SPOT|
|Spot component of market value|Ms|Ms,rf - CVAS -DVAS|NPV_SPOT|
|CVA of forward component of market value|CVAz|According to the MNRFVA described above|CVA_FWD|
|CVA of forward component of market value|DVAz|According to the MNRFVA described above|DVA_FWD|
|Forward component of market value|Mz|Mz,rf - CVAz -DVAz|NPV_FWD|
|CVA of CCBS component of market value|CVAc|According to the MNRFVA described above|CVA_CCBS|
|DVA of CCBS component of market value|DVAc|According to the MNRFVA described above|DVA_CCBS|


|Description|Symbol|Definition/Calculation|Name of corresponding key figure category|
|---|---|---|---|
|CCBS component of the market value|Mc|Mc,rf - CVAc -DVAc|NPV_CCBS|
|CVA of others component of market value|CVAo|According to the MNRFVA described above|CVA_OTHER|
|DVA of others component of market value|DVAo|According to the MNRFVA described above|DVA_OTHER|
|Others-component of the market value|Mo|Mo,rf - CVAo -DVAo|NPV_OTHER|


**Note:**

With the MNRFVA, either CVA_KF or DVA_KF will always be zero.

From M = M + M + M + M and (CVA+DVA) = (CVA +DVA ) + (CVA +DVA ) + (CVA +DVA ) + (CVA +DVA ), it follows that M = M + M + M + M .

rf s,rf z,rf c,rf o,rf s s z z c c o o s z c o

In general, it is possible that CVA = CVA + CVA + CVA + CVA and DVA = DVA + DVA + DVA + DVA , because the MNRFVA adds CVA and DVA before distribution.

s z c o s z c o

###### Documentation of Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Documentation of Hedging Relationship | L6 | trm09 p.152 | loio `5a7dfd64556542faa6ce3b4fc0337862` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a7dfd64556542faa6ce3b4fc0337862.html?locale=en-US)

**Use**

The documentation of the hedging relationship is automatically created during the release of designation. You can access the documentation in the Manage Hedging Relationships app on Documentation tab. If you reverse the release of the designation, the documentation is set to Reversed.

The delivered PDF forms provide detailed information about the hedged items (including the hypothetical derivative) and the hedging instruments of the hedging relationship. You can create your own PDF forms using the Form Builder (transaction SFP).

The files are managed using Document Management (DMS).

**Prerequisites**

Under Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profile , you make the following settings to activate the automatic creation of documentation:

In the Documentation Handling area, you do not set the documentation as optional in Documentation Optional (Yes/No) field.

**Note:**

If you set the documentation as optional, no documentation will be created during release of designation.

To complete the settings for the documentation you have to assign the PDF form (one of the predefined PDF forms or your own PDF form) in PDF-Based Forms: Form Name field.

The following predefined forms are available:

TR_F_THX_NOTE_HREL_FXRISK_FX for FX transactions

TR_F_THX_NOTE_HREL_FXRISK_OP for FX options

TR_F_THX_NOTE_HREL_FXRISK_OP2 for collar FX options

You also need to make settings in the document management system to enable the process. For more information: Customizing Settings in DMS for TRM Documents

###### Prospective Effectiveness Test

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Prospective Effectiveness Test | L6 | trm09 p.153 | loio `b988d64174794a9592480f2c3efc5094` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b988d64174794a9592480f2c3efc5094.html?locale=en-US)

If you want to make sure that a hedging relationship is only designated in cases where effectiveness is proven, you need to enable effectiveness testing for your hedging profiles. In this case, a prospective effectiveness test is integrated in the designation process and automatically performed during the release of designation.

You can either choose to use an effectivenes test method based on linear regression with MDS or you can use the critcal term match method.

**Related Information**

Prospective Effectiveness Test Using Linear Regression Prospective Effectiveness Test Using Critical Term Match Method

###### Prospective Effectiveness Test Using Linear Regression

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Prospective Effectiveness Test > Prospective Effectiveness Test Using Linear Regression | L7 | trm09 p.153 | loio `8ec508c4844d4aa39cf47e9502fd0215` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8ec508c4844d4aa39cf47e9502fd0215.html?locale=en-US)

**Features**

At the time of designation t , the hedging instruments as well as the hypothetical derivatives (representing the exposure) have certain values for the total NPV and market value components. These amounts are calculated at designation date using the market value at designation date.

desig.

In the course of time after designation, the total NPV and market value components of the hedging instruments and hypothetical derivatives change. Ideally, the values of the designated components of the hedging instruments and the hypothetical derivative move in opposite directions but with the same absolute amount, so that the total amount of the designated components (hedging instruments + hypothetical derivative) is stable. In such cases, the hedging relationship is deemed effective.

[figure TRM09-F042 - To prove the effectiveness of a hedging relationship, a prospective effectiveness test is performed at the time of designation. If this test fails, the hedging relationship is not deemed effective and therefore must not be designated.]

To prove the effectiveness of a hedging relationship, a prospective effectiveness test is performed at the time of designation. If this test fails, the hedging relationship is not deemed effective and therefore must not be designated.

To this end, the total NPV and market value components are calculated at designation date using various alternative sets of market data (representing different possible future market data constellations). This could be artificial market data or historical market data (taken from t to t ). For each alternative set of market data, the change in the values of the designated components is

1 n

compared between the hedging instruments and the hypothetical derivative. The change in the values for all alternative sets of market data is finally the basis for the linear regression, which, in the case of an ideal hedge, should result in a slope close to -1.

[figure TRM09-F043 - Sequence of effectiveness testing using linear regression based on changes of the designated market value components caused by alternative sets of market data]

Sequence of effectiveness testing using linear regression based on changes of the designated market value components caused by alternative sets of market data

- 1. Calculate values once using actual market data.

Calculate expected exposures

Calculate CVA/DVA

Calculate risk-free NPV

Allocate CVA/DVA to get full NPV

Calculate market value components

Value of the designated market value components for hedging instruments and hypothetical derivates:

MVal

MVal

- 2. Calculate values per market data scenario / market data selection date i

Calculate expected exposures

Calculate CVA/DVA

Calculate risk-free NPV

Allocate CVA/DVA to get full NPV

Calculate market value components

Value of the designated market value components for hedging instruments and hypothetical derivates for each market data set i:

MVal

MVal

- 3. Calculate the change in value of the designated market value components for hedging instruments and hypothetical derivates for each market data set / market data selection date i.


Hedging Instrument,0

Hypothetical Derivative,0

Hedging Instrument,i

Hypothetical Derivative,i

Delta MVal = MVal -MVal

Hedging Instrument,i Hedging Instrument,i Hedging Instrument,0

Delta MVal = MVal -MVal

Hypothetical Derivative,i Hypothetical Derivative,i Hypothetical Derivative,0

- 4. Execute linear regression analysis of the delta values.


[figure TRM09-F044 - The system analyzes the following aspects:]

The system analyzes the following aspects:

The slope of a straight line is given by the ratio of the vertical distance and the horizontal distance of two points on the line. The measured slope of the line obtained from the linear regression within the effectiveness test is a measure of the effectiveness. If effectiveness is perfect, the slope is -1. An interval is defined for the slope by specifying a minimum slope and a maximum slope. If the measured slope falls within the interval, the hedging relationship is effective; otherwise, the hedging relationship is ineffective.

2 2

The coefficient of determination R measures the variability in a data set that is accounted for by a statistical model. R is an element of [0,1].

2

When the variability is low, R is near to 1.

2

When the variability is high, R is near to 0.

2

Therefore, R indicates the quality of the linear fit. When the value is 1, this means a perfect fit.

The intercept ratio is obtained by dividing the intercept value of the regression line by the designated amount. The result is a dimensionless number.

For effectiveness, the result needs to be close to zero.

To measure the effectiveness of a hedging relationship, you can specify a lower and an upper boundary value for the intercept ratio. The hedging relationship is considered effective if the measured intercept ratio falls within this interval. If the intercept ratio falls outside of this interval, the hedging relationship is not considered effective.

t-Statistic

The t-Statistic supplies an interval of slopes containing the target slope value -1. If the slope measured by the linear regression lies within this interval, the probability that the slope is compatible with the target value -1 is 90%.

Alpha is the significance level related to the confidence level 1 - Alpha. Alpha is the probabililty that a statistical test does not support a null hypothesis.

Example

If alpha = 0.1, the confidence level is 0.9, that is, 90%.

Afterwards, the system decides on the effectiveness. Due to the defined settings for the SLR Linear Regression method, the hedging relationship is deemed effective provided that the defined conditions hold. For example, the method defines that the hedging relationship is deemed effective provided that the following two conditions hold:

The slope lies between -1.25 and -0.8.

2

R is at least 0.9.

**Prerequisites**

If you want to activate effectiveness testing, you need to define an effectiveness test method with Eff.Test Method Category 22 Linear Regression with MDS.

Eff. Test Method Category: Only 22 Linear Regression with MDS is supported.

Offset Calculation Category: 02 (Cumulative)

Market Data Calc. Logic: For effectiveness test method category 22 choose the market data calculation logic 2 Market Data Scenario.

Within the settings for the linear regression method choose the Assessment Method 1 Independent.

2

Define which of the parameters R , Intercept Ratio, Slope and the t-statistics you want to check and enter the values for effectiveness.

When the calculated values lie within the entered ranges, the hedging relationship is effective.

Examples:

2 2

The coefficient of determination R measures the variability in a data set that is accounted for by a statistical model. R is an element of [0,1].

2

When the variability is low, R is near to 1.

2

When the variability is high, R is near to 0.

2

Therefore R indicates the quality of the linear fit. When the value is 1, it means perfect fit.

The slope of a straight line is given by the ratio of the vertical distance and the horizontal distance of two points on the line. The measured slope of the line obtained from the linear regression within the effectiveness test is a measure of the effectiveness. If effectiveness is perfect, the slope is -1. An interval is defined for the slope by specifying a minimum slope and a maximum slope. If the measured slope falls within the interval, the hedging relationship is effective; otherwise the hedging relationship is ineffective.

Effectiveness testing is only executed if you have activated effectiveness testing in the hedging profile in the configuration step Define Hedging Profiles. You define your hedging profiles in the Configure Your Solution app, which is part of the Manage Your Solution app under Finance Treasury and Risk Management Risk Management Define Hedging Profiles .

The effectiveness test method SLR Linear Regression is based on market data sets. You need to define market data sets using the Manage Market Data Sets app.

In the relevant hedging areas, on the Hedge Accounting II tab, the market data set must be assigned along with the hedging profile to a combination of company code, valuation area, and hedging classification.

During the creation of a hedging relationship, the market data set is included in the generated test plan.

###### Prospective Effectiveness Test Using Critical Term Match Method

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Prospective Effectiveness Test > Prospective Effectiveness Test Using Critical Term Match Method | L7 | trm09 p.157 | loio `5b1b16afa92d4458b87d3e63ab6b03a1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5b1b16afa92d4458b87d3e63ab6b03a1.html?locale=en-US)

With the critical term match method, some important business data (the critical terms) of the hedged item and of the hedging instrument are checked as to whether they match. If the critical terms match, it can be assumed that the hedging relationship is effective.

The following critical terms can be compared:

Nominal

Currency

Start date

Due date

**Prerequisites**

In Customizing for Hedge Accounting for Positions under Hedge Accounting for Positions Effectiveness Test Define Critical Term Type , you can create a critical term type and specify which terms need to be applied to check the effectiveness. You can choose the following terms:

Nominal

Currency

Start date

For this date, you can define how many deviant days are allowed between the hedged item and hedging instrument values.

Due date

For this date, you can define how many deviant days are allowed between the hedged item and hedging instrument values.

Under Hedge Accounting for Positions Effectiveness Test Effectiveness Methods , you must create a method that uses the Critical Term Match Method as the type of effectiveness test method and in which in which you also assign the critical term type defined above.

Under Hedge Accounting for Positions Define Hedging Profile , you must assign the new effectiveness test method as prospective effectiveness method.

###### Reverse Release of Hedging Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Release Hedging Business Transactions > Reverse Release of Hedging Business Transactions | L6 | trm09 p.157 | loio `2e306f362334449f89ceb0e7db71b78d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2e306f362334449f89ceb0e7db71b78d.html?locale=en-US)

**Context**

Hedging relationships in Designated or Dedesignated status, for example, have fixed flows that prevent changes to the financial transaction.

Before you can allow changes to financial transactions, you first need to perform the Reverse Release of Hedging Business Transactions function (TPM121), which reverts the status from Designated to Planned Designation and from Dedesignated to Planned Dedesignation.

The hypothetical derivative is then removed, and the status of the fixed flows is changed to Scheduled.

Changes

The hedge accounting process has only limited impact on the operational processes of financial transactions.

Changes to financial transactions that were designated into a hedging relationship as the hedging instrument also initiate changes to the hedging relationship.

Changes to the field values of the financial transaction have different effects on the corresponding hedging relationships. There are three different field groups. For more information, see Change of Hedging Instrument.

For changes to field values of group 1 and group 2, relevant financial transactions can only be processed if the hedging relationship is in Planned Designation or Planned Dedesignation status. Changes to field values of group 3 don’t have any effect on the corresponding hedging relationship(s).

**Prerequisites**

You can reverse the release of a hedging business transaction only if no further processes, such as valuation or classification, have already taken place.

If these processes have been performed, you first need to reverse the valuation or classification before you can reverse the release of a hedging business transaction.

**Features**

Selection Options

Multitasking Settings area

This area appears on the screen when you have set the Allow User to Control Parallelization Parameters in GUI indicator for the application in Customizing for Parallel Processing under Transaction Manager General Settings Parallel Processing Control

.


If you have activated parallel processing for the function in Customizing, the Use Multitasking is set. If you want to execute the function without parallel processing in spite of the setting made to the contrary in Customizing, deselect the Use Multitasking indicator.

If you have deactivated parallel processing in Customizing, the indicator is not set. If you want to execute the function with parallel processing in spite of the setting made to the contrary in Customizing, set the Use Multitasking indicator.

In the following fields, you see the parallelization parameters defined in Customizing: Server Name, Logon/Server Group, Max. No. of Tasks, and Package Size. In the function Generate Derived Flows (transaction TPM27), only the package size is displayed.

You can change the parallelization parameters, provided that you observe the following restriction:

The maximum number of tasks defined in Customizing is an upper limit. You can only enter a lower number of tasks.

Posting Control area

The reversal date of the hedging business transactions is usually derived from the posting date of the hedging business transaction, but if you want to reverse the business transaction on an alternative date use the Posting Control selection parameters:

Specify a reversal date for all selected hedging business transactions on the selection screen once, or

Specify a reversal date for each hedging business transaction individually by selecting the Enter Rev.Date checkbox and maintaining alternative reversal date on the next screen.

**Note:**

When the Enter Rev.Date checkbox is selected, the function cannot be carried out in multitasking mode.

Further Details

You can access the following other details from the Reverse Release of Hedging Business Transactions function:

Using the Display Log button, you can review the posting and message log showing you the posting and calculation steps that have been performed.

Use the Display Hedging Relationship button to navigate to the Manage Hedging Relationhsips screen (transaction TPM100) showing you the details for the selected hedging relationship.

**Process Steps**

- 1. To process a financial transaction that was designated into a hedging relationship with Designated status, use transaction TPM121 to reverse the release of the hedging business transaction:
- 2. On the selection screen, enter the following parameters:

Company Code

Valuation Area

- 3. You can either search for your designated hedging relationships by entering the relevant transaction numbers, or specify the relevant hedging relationships directly:

Transaction Selection

Transaction Number

or

Hedging Relationship Selection

Hedging Relationship Number

Fiscal Year

Valid-From Date

Profile

Hedging Area

Reversal Reason

Reversal Date

Reversal Period

- 4. On the next screen, maintain the reversal date for the hedging business transactions that you want to reverse in the FI Reversal Date field and choose Execute.


**Note:**

This step only applies if you have selected the Enter Rev. Date checkbox in the Posting Control area.

The indicator cannot be set if the transaction is run in multitasking mode.

- 5. Once you execute the function, the following automatic process steps are triggered, depending on the hedging business transaction that is released:


The hypothetical derivative is deleted.

The hedge accounting key figures are deleted from the market data container.

The rule for the calculation of the cost of hedging reserve is deleted.

The status of the designation flows are reversed from Fixed status to Scheduled status.

**Example**

An error occurred during the processing of a financial transaction. The wrong portfolio was assigned to the financial transaction that was designated into a hedging relationship. The hedging relationship has already been released and is in Designated status. To correct this error, you have to reverse the release of the hedging business transaction by using transaction TPM121.

###### Display Effectiveness Test Results (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Display Effectiveness Test Results | L5 | trm09 p.160 | loio `79ebf2c79e514699adb326f83199397b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/79ebf2c79e514699adb326f83199397b.html?locale=en-US)

Get detailed information on effectiveness test results and the hedging instruments of hedging relationships.

**Context**

If effectiveness testing is active for your hedging profiles and hedging areas, a prospective effectiveness test is automatically executed during the release of designation. Using this report, you can display the results of this effectiveness tests. In addition, details for the hedging instruments are shown and navigation to the hedging relationship and also to the hedge documentation is provided.

**Procedure**

- 1. Call the function in the area menu under Hedge Accounting for Positions Effectiveness Test Display Effectiveness Test Results (transaction TPM112).
- 2. Under General Selections, you select the hedging relationships by the Company Code, Valuation Area, and Up to Key Date. You could also select by the number of the financial transactions, which are part of the hedging relationship, or by attributes of the hedging relationship, such as the Hedging Relationship Number, Profile, or Hedging Area.
- 3. Under Effectiveness Test Status, you can select the hedging relationships by the effectiveness test status of the hedging relationship.


If you set the Effective Hedging Relationships indicator, you get the effectiveness test results of hedging relationships for which the effectiveness test has been executed successfully and the hedging relationship is effective due to effectiveness criteria.

If you set the Ineffective Hedging Relationships indicator, you get the effectiveness test results of hedging relationships for which the effectiveness test has been executed successfully and the hedging relationship is ineffective due to effectiveness criteria.

If you set the Hedging Relationships with Effectiveness Calculation Errors indicator, you get a list of hedging relationships for which errors occurred during the execution of the effectiveness test.

If you set the Hedging Relationships Manually Set to Effective indicator, you get a list of effective hedging relationships, which are manually set to effective. (This function is not available for hedging relationships of the Hedge Accounting for Exposure Items process.)

- 4. Execute the report.


**Results**

You get a result list according to your selections. For the selected hedging relationships, you get a row for each hedging instrument of the hedging relationship. In the row, you get information on the effectiveness test and hedging instrument. You also can navigate to further information.

For hedging relationships, for which the effectiveness test has been successfully executed, you can find the results of the effectiveness test in the columns R2, Slope, Intercept Ratio, and t-Stat. Slope.

In addition, administrative information for the effectiveness test, such as Effectiveness Test Date, Effectiveness Test Type, MDS ID, Trigger, and Prospective Method are available.


The effectiveness test status is visualized by an icon at the end of the row ( = effective and = ineffective).

In addition, you get information for the hedging instrument, such as the following:

Number of the hedging instrument

Product type

Buy currency

Buy amount

Sell currency

Sell amount

Nominal amount

Nominal currency

Number of the hypothetical derivative

If you mark a line item, you can use the following buttons on top of the list:

###### Display Effectiveness Test

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Display Effectiveness Test Results > Display Effectiveness Test | L6 | trm09 p.161 | loio `2ea37bcde8ba462981031295774647af` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2ea37bcde8ba462981031295774647af.html?locale=en-US)

Display Hedging Relationships

You navigate to the hedging relationship details in the Manage Hedging Relationship function.

Display Hedge Documentation

You see the created file.

**Note:**

You can navigate to the hedging relationship by clicking the HR Number in the respective column.

You can navigate to the hedge documentation by clicking the icon in the Hedge Documentation column.

**Related Information**

Prospective Effectiveness Test Using Linear Regression

**Display Effectiveness Test**

See details of the performed prospective effectiveness test.

The Display Effectiveness Test button takes you to the details of the prospective effectiveness test performed.

In the Hedging Relationships Details area, you see the number and the name of the hedging relationship.

In the Effectiveness Test Details area, you see the details for the effectiveness test, such as the fields Eff. Test Date, Eff. Test Type, Eff. Test Trigger (including Ref. to Bus. Trans.), the effectiveness test result (with the status Effective or Ineffective) is displayed as a green or red icon.

2

On the Eff. Test Result tab, you get the results of the linear regression analysis (expressed in the fields Slope, R , Intercept Ratio, and t-Statistic of Slope). The results are displayed and compared with the border conditions defined in the effectiveness test method.

The H.Item/H.Instr.Values tab shows all market value components: the designated ones for the hedging instruments and the hypothetical derivatives calculated at designation and using a market data scenario or market data selection date (see corresponding columns).

The Detail Log button in the toolbar offers a detail log for each individual row.

The Display Lin. Regr. Details button navigates to the details of the linear regression analysis.

Each line refers to a market data scenario or market data selection date and contains the delta of the designated components of the hypothetical derivative (explanatory variable) and the hedging instrument (explained variable).

A graphical representation of the data points along with the calculated line is also available.

###### Period-End Closing (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Period-End Closing | L5 | trm09 p.162 | loio `7a237f586d809344e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7a237f586d809344e10000000a4450e5.html?locale=en-US)

**Use**

The data to be used in period-end closing is selected based on the product group and its specific selection criteria, such as the financial transaction. The selection results in treasury ledger positions that represent the selection criteria.

**Prerequisites**

Before you can start the period-end closing process, you have to process the payment of your financial transaction using the Fix, Post or Reverse Transactions function (transaction TPM10)

Before you can start with key date valuation, you have to settle your financial transaction using transaction FTR_EDIT.

**Note:**

Carrying out the Fix and Post Derived Business Transactions function (transaction TPM18) to fix the derived business transaction of the Open OTC Transaction is not required. The key date valuation (transaction TPM1) ignores the Plan status of the derived business transaction.

**Process Steps**

Period-end closing for the designated financial transaction comprises the following three steps:

Calculate Net Present Values

- 1. Calculate the net present values (NPVs) and market value components (that is, spot, forward, CCBS, CVA/DVA) using Determine NPVs Including CVA and DVA (transaction TPM60CVA).


**Note:**

This step is a prerequisite for key date valuation.

- 2. Set the following indicators on the selection screen:

Derive Evaluation Parameters

This indicator ensures that the evaluation type and CVA type are derived automatically from the position management procedure.

Select Single OTC Transactions

This indicator ensures that the NPV of the financial transaction (such as an FX forward) is calculated.

Market Value Decomposition

This indicator ensures that the market value components are calculated.

For more information, see Hedge Accounting Key Figures.

- 3. You can see the relevant hedge accounting key figures - that is, the calculated components and elements for the hedging instrument and the hypothetical derivative - in the results list using the Hedge Accounting Key Figure button.


Execute Key Date Valuation

You carry out key date valuation (transaction TPM1) to valuate the financial transactions based on the previously calculated NPVs, and then transfer the results to Financial Accounting.

Depending on the settings you made in the position management procedure either a security valuation is executed for freestanding and designated subpositions or the designated subpositions and the freestanding subpositions are valuated differently.

See also: Settings for Hedge Accounting for Exposure Items

**Example:**

Security Valuation for Freestanding and Designated Subpositions

The security valuation calculates the Δ NPV of the treasury ledger position based on NPV values that were stored between the contract start date of the financial transaction and the key date of the valuation. The valuation calculates its Δ NPV as follows:

- 1. Δ NPV = NPV - NPV-1
- 2. Calculate the portion of the Δ NPV for the designated and for freestanding subpositions.


The valuation result is documented in the valuation log from which you can access the posting log that gives you an overview of the posted flows for each subposition. Postings are made to Financial Accounting.

The amounts relevant for the designated subpositions are posted against the hedge clearing account.

Asset position:

|Δ NPV > 0|Dr Asset, Cr Hedge Clearing|
|---|---|
|Δ NPV < 0|Dr Hedge Clearing, Cr Asset|


Liability position:

|Δ NPV < 0|Dr Hedge Clearing, Cr Liability|
|---|---|
|Δ NPV > 0|Dr Liability, Cr Hedge Clearing|


Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

The classification will distribute the component values of the exposure subitem according to the relevant hedge accounting rule to the designated and non-designated components of the exposure subitem.

**Note:**

The amounts relevant for the freestanding subpositions are posted to P&L.

**Example:**

Two-Step Valuation for Freestanding Subpositions and Security Valuation for Designated Subpositions

Valuation of Designated Subpositions

The security valuation for the designated subpositions calculates the Δ NPV of the treasury ledger position based on NPV values that were stored between the contract start date of the financial transaction and the key date of the valuation. The valuation calculates its Δ NPV as follows:

- 1. Δ NPV = NPV - NPV-1
- 2. Calculate the portion of the Δ NPV for the designated subpositions.


The valuation result is documented in the valuation log from which you can access the posting log that gives you an overview of the posted flows for each subposition. Postings are made to Financial Accounting. The designated subpositions are posted against the hedge clearing account.

Asset position:

|Δ NPV > 0|Dr Asset, Cr Hedge Clearing|
|---|---|
|Δ NPV < 0|Dr Hedge Clearing, Cr Asset|


Liability position:

|Δ NPV < 0|Dr Hedge Clearing, Cr Liability|
|---|---|
|Δ NPV > 0|Dr Liability, Cr Hedge Clearing|


Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (for internal calculation: To Be Classified). The update types are determined from the settings made in Customizing for security valuation and can be overwritten in the Customizing activity Alternative Update Types for Position Outflows.

The classification will distribute the component values of the exposure subitem according to the relevant hedge accounting rule to the designated and non-designated components of the exposure subitem.

Valuation of Freestanding Subpositions

- 1. The system executes the rate valuation for FX transactions only for the freestanding subpositions (in order to calculate the spot effect). See also: Rate Valuation for Forward Exchange Transactions

- 2. The security valuation for the freestanding subpositions is executed for the freestanding subpositions (in order to calculate the interest effect). It takes the results of the rate valuation for FX transactions into account.


The valuation result is documented in the valuation log from which you can access the posting log that gives you an overview of the posted flows for each subposition. Postings are made to Financial Accounting. The freestanding subpositions are posted against P&L.

In general, the posting amount of the valuation result depends on the key date valuation procedure that was chosen:

With Reset:

The valuation result is posted at period end.

The posting is reset on the first business day after period end.

NPV-1 = NPV on contract start date of the financial transaction

Without Reset:

The valuation result is posted at period end.

NPV-1 = NPV at last period-end closing

Execute Classification

Financial transactions are classified using Run Classification function (transaction TPM101) for each hedging relationship on a key date that needs to be the key date of the period-end.

For more information: Run Classification

**Note:**

To obtain the most detailed information, enter the hedging relationship number as a selection criterion.

When the report is executed, the designated exposure subitems of the hedging relationship are selected and the relevant classification amounts are calculated according to the settings of the hedge accounting rule.

For each exposure subitem, postings are made to Financial Accounting and documented in a posting log. The postings are made for the designated part of the financial transaction and based on the calculated key figures at period end.

Depending on the key date valuation procedure that was chosen in the previous step, the classification has to function accordingly:

With Reset

If you chose the key date valuation procedure with reset, the classification of the exposure subitem values must function accordingly. The calculated exposure subitem values are reset to zero on the relevant Reset Posting Date for the classification.

Without Reset

If you chose the key date valuation procedure without reset, the exposure subitem values are also classified without reset.

You can access the calculated amounts using the classification log that can be displayed after the function Execute Classification has been performed.

Reversal

You have to perform two steps to reverse period-end closing:

- 1. Reverse the measurement calculation of the hedging relationship.

The postings for the classification have to be reversed. To do this, use the Reverse Classification function (transaction TPM102).

Enter the following parameters:

Company Code or Accounting Code

Valuation Area

Hedging Relationship Number

Key Date for Classification

Reason for Reversal

Check that the reversal of the hedging reserve, cost of hedging reserve, and P/L postings have been performed successfully on the exposure subitem level.

- 2. Reverse the key date valuation of the financial transaction.


The postings for period-end closing of the financial transaction have to be reversed. For this, use the Reverse Valuation function (transaction TPM2).

Use the same selection criteria as in the previous step and select a reason in the Reason for Reversal field.

**More Information**

Release Hedging Business Transactions

Period-End Closing - FX Swap

Contract Close

Reporting

**Related Information**

Overview Hedge Accounting Rules

###### Period-End Closing - FX Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Period-End Closing > Period-End Closing - FX Swap | L6 | trm09 p.166 | loio `cbd96ebf086b482586c3c1893e6c0d15` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cbd96ebf086b482586c3c1893e6c0d15.html?locale=en-US)

**Use**

Period-end closing for the designated FX swap transactions comprises the following three steps:

- 1. Calculation and storage of NPV and market value components (for example, CCBS, CVA/DVA) for key date valuation and classification
- 2. Key date valuation of FX transaction
- 3. Classification of each hedging relationship


**Differences in Process for FX Swap**

- 1. Key date valuation

Original hedging relationship

The remaining portion of the original hedging relationship is processed as usual.

New hedging relationship

The designated portion of the FX transaction as well as each FX transaction of the FX swap transaction that are designated into the new hedging relationship are valuated and posted separately as usual.

- 2. Classification


Original hedging relationship

The remaining portion of the original hedging relationship is processed as usual.

New hedging relationship

The classification result of the new hedging relationship is calculated as the sum of the NPVs and market value components of the single FX forward tranaction according to the hedging relationship scenario of the hedging relationship:

The original FX forward transaction is considered with its portion that is designated into the new hedging relationship.

The FX swap transactions are considered with 100 % of their designated amount.

For the exposure subitem of the new hedging relationship, postings are made to Financial Accounting according to the same logic and posting schemes as for usual hedging relationships.

**Related Information**

Period-End Closing

###### Run Classification

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Period-End Closing > Run Classification | L6 | trm09 p.167 | loio `a28f742ae79543a7b6736e2d9d62d3c0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a28f742ae79543a7b6736e2d9d62d3c0.html?locale=en-US)

Split the valuation result according to the hedge accounting rule into position components, which reflect effective and ineffective amounts.

The following table shows the relevant position components for the different kinds of hedge case. Examples of the different hedge cases are cash flow hedge or fair value hedge, planned forecast or recognized asset/liability, and U.S. GAAP or IFRS 9.

Overview of Position Components for Different Hedge Cases

|Position Component|Cash Flow Hedge Planned Forecast IFRS 9|Cash Flow Hedge Planned Forecast U.S. GAAP|Cash Flow Hedge Recognized Asset/Liability IFRS 9|Cash Flow Hedge Recognized Asset/Liability U.S. GAAP|Fair Value Hedge Fair Value Hedge IFRS 9|Fair Value Hedge Fair Value Hedge U.S. GAAP|
|---|---|---|---|---|---|---|
|1302 Effective / Hedging Reserve|X|X|X|X|X|X|
|1303 Ineffective|X|X|X|X|X|X|


|Position Component|Cash Flow Hedge Planned Forecast IFRS 9|Cash Flow Hedge Planned Forecast U.S. GAAP|Cash Flow Hedge Recognized Asset/Liability IFRS 9|Cash Flow Hedge Recognized Asset/Liability U.S. GAAP|Fair Value Hedge Fair Value Hedge IFRS 9|Fair Value Hedge Fair Value Hedge U.S. GAAP|
|---|---|---|---|---|---|---|
|1322 Effective / Cost of Hedging Reserve|X|X|-|-|-|-|
|1323 Ineffective / Hedging Reserve TPL|X|X|X|X|X|X|
|1324 Effective / Hedging Reserve TPL|X|X|X|X|-|-|
|1333 Ineffective / Cost of Hedging Reserve TPL|X|X|-|-|-|-|
|1334 Effective / Cost of Hedging Reserve TPL|X|X|-|-|-|-|
|1343 P&L Effective / Designated Components|-|-|-|-|X|X|
|1344 P&L Effective / NonDesignated Components|-|-|-|-|-|X|
|1345 Amortization / Non-Designated Components|-|X|-|-|-|-|


**Use**

Classification is the last step of the valuation process for the designated subpositions. It splits the valuation result into the different position components, which reflect the effective and ineffective amounts of the designated components, the nondesignated components, and the amortization.

**Hedge Accounting Rules**

The hedge accounting rule specifies how the hedged item and the hedging instruments are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship. The hedge accounting rule also determines how the classification is calculated.

In the following table you get an overview of the market value and element components (see also Hedge Accounting Key Figures), the calculation methods, and position components relevant in the hedge accounting rules.

**Overview Hedge Accounting Rules**

|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|HA Rule 611 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT|NPV_SPOT|NPV_FORWARD NPV_CCBS|NPV_FORWARD NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 613 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT|NPV_SPOT|NPV_FORWARD NPV_CCBS NPV_OTHER|NPV_FORWARD NPV_CCBS NPV_OTHER| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | |lower-oftest.*| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|HA Rule 622 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT NPV_FORWARD|NPV_SPOT NPV_FORWARD|NPV_CCBS|NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |
|HA Rule 623 Cash Flow Hedge Planned Forecast IFRS 9|NPV_SPOT NPV_FORWARD|NPV_SPOT NPV_FORWARD|NPV_CCBS NPV_OTHER|NPV_CCBS NPV_OTHER| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | |lower-oftest.*| |
|HA Rule 631 Fair Value Hedge Recognized Asset/Liability IFRS 9|NPV_SPOT NPV_FORWARD NPV_CCBS NPV_OTHERS|NPV_SPOT NPV_FORWARD|-|-| |Lower-ofTest|-| |
|HA Rule 632 Cash Flow Hedge Recognized Asset/Liability IFRS 9|NPV_SPOT NPV_FORWARD NPV_CCBS NPV_OTHERS|NPV_SPOT NPV_FORWARD|-|-| |Lower-ofTest|-| |
|HA Rule 641 Fair Value Hedge Net Investment|NPV_SPOT|NPV_SPOT|NPV_FORWARD|NPV_FORWARD| |Actual Value|Actual Value| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|Hedge Recognized Asset/Liability Net Investment U.S. GAAP| | | | | | | | |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
|HA Rule 642 Cash Flow Hedge Planned Forecast U.S. GAAP|NPV_SPOT|NPV_SPOT|NPV_FORWARD|NPV_FORWARD|ELEM_FWD|Actual Value|Actual Value| |
|HA Rule 643 Cash Flow Hedge Planned Forecast U.S. GAAP|NPV_INTR|NPV_INTR|NPV_TIME NPV_OTHER|NPV_TIME|NPV_OTHER|Actual Value|Actual Value| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |
|HA Rule 650 Cash Flow Hedge Planned Forecast IFRS 9|NPV_INTR|NPV_INTR|NPV_TIME NPV_CCBS|NPV_TIME NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |


|Hedge Accounting Rule|Designated Component Hedging Instrument|Designated Component Hyp. Derivative|NonDesignated Component Hedging Instrument|NonDesignated Component Hyp. Derivative|Amortization Based on|Calculation Method Desig. Comp.|Calculation Method Non-Desig. Comp.|C|
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |
|HA Rule 651 Cash Flow Hedge Planned Forecast IFRS 9|NPV_INTR|NPV_INTR|NPV_TIME NPV_CCBS NPV_OTHER|NPV_TIME NPV_CCBS| |Lower-ofTest|According to calculation method for cost of hedging reserve determined at the release of designation either actual value, aligned value, or lower-oftest.*| |


*To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in Customizing of the hedging profile. In this case, the result of the lower-of-test executed at the release of designation is set to Actual Value = Aligned Value.

**Features**

During classification, the effective and ineffective amounts of the hedging reserve, the cost of hedging reserve, and the amortization are determined.

[figure TRM09-F047 - Overview of Classification]

Overview of Classification

Determine the effective and ineffective amounts of the hedging reserve

For the hedge accounting rules of IFRS 9, a lower-of test is executed for the designated components of the hedging instrument and the hypothetical derivative.

For the hedge accounting rules of U.S. GAAP, the designated components of the hedging instruments are relevant for the hedging reserve.

[figure TRM09-F048 - Hedging Reserve]

Hedging Reserve

Determine the effective and ineffective amounts of the cost of hedging reserve

The cost of hedging reserve is only relevant for hedge accounting rules for cash flow hedges with the hedged item category Planned Forecast.

IFRS 9

The calculation rule for the cost of hedging reserve is determined at the release of designation. The system compares the actual values and aligned values of the non-designated components and the result determines the calculation method for the hedging relationship.

[figure TRM09-F049 - The calculation rule for the cost of hedging reserve is determined at the release of designation. The system compares the actual values and aligned values of the non-designated components and the result determines the calculation method for the hedging relationship.]

Cost of Hedging Reserve (IFRS 9)

To overwrite the calculation rules, you can set the Apply Critical Term Match attribute in the Customizing settings for the hedging profile. In this case, the aligned value check result at the release of designation is set to Actual Value

= Aligned Value.

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the first-day valuation result of the hedging instrument. When this indicator is set, the valuation is

skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Exception: For an FX option with a premium that has been activated, in classifications after the payment date of the premium, the calculated values for the elements and components are used as start values during classification (with the Run Classification app) and are not assumed to be 0.

U.S. GAAP

The non-designated components of the hedging instrument are relevant for the cost of hedging reserve (= Actual Value).

**Note:**

In the hedging profile, you can set the Skip Valuation at Contract Date indicator if you want to prevent the posting of the first-day valuation result of the hedging instrument. When this indicator is set, the valuation is skipped during the release of hedging business transactions if the designation date is the same as the contract date.

The elements and components are still calculated and stored in the market data container on the designation date. On the designation date, however, the values for the hedging instrument and the hypothetical derivative are assumed to be 0.

Exception: For an FX option with a premium that has been activated, in classifications after the payment date of the premium, the calculated values for the elements and components are used as start values during classification (with the Run Classification app) and are not assumed to be 0.

Determine the effective and ineffective amounts of the amortization

Amortization is relevant for cash flow hedges when U.S. GAAP is applied.

Hedging Instrument FX Forward

The forward points (traded amount * swap rate at designation date) are amortized using straight-line amortization over the lifetime of the hedging instrument. This amortization is represented by the ELEM_FWD element of the hedging instrument.

**Example:**

[figure TRM09-F050 - Example for Hedge Accounting Rule 642]

Example for Hedge Accounting Rule 642

Hedging Instrument FX Option

The option premium is amortized using straight-line amortization over the lifetime of the hedging instrument. This amortization is represented by the NPV and NPV_OTHER component of the hedging instrument.

**Example:**

[figure TRM09-F051 - Example of Hedge Accounting Rule 643]

Example of Hedge Accounting Rule 643

###### Premature Dedesignation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Premature Dedesignation | L5 | trm09 p.180 | loio `cc77395d15d24b50b8d64ddf0695865d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cc77395d15d24b50b8d64ddf0695865d.html?locale=en-US)

Premature dedesignation is triggered by a dedesignation request.

Use

You can fully or partially dedesignate a hedging relationship before the planned dedesignation date.

The decision to dedesignate a hedging relationship using the Hedge Request functionality is based on the key figures calculated in the Hedge Management Cockpit.

The dedesignation request supports the following features:

Dedesignate several hedging relationships of a single FX forward transaction with one dedesignation request

Dedesignate several hedging relationships of several FX forward transactions with one dedesignation request

Dedesignate hedging relationships that belong to different valuation areas with one single dedesignation request

**Process**

- 1. Call the Hedge Management Cockpit.
- 2. Mark the relevant analysis item and create a dedesignation request.
- 3. Release the dedesignation request, using Process Hedge Request function.
- 4. Release the Dedesignation hedging business transaction on dedesignation date using the Release Hedging Business Transactions function.


**Note:**

For the reclassification handling it is important whether the premature dedesignation takes place before or after the balance sheet recognition date.

When a hedged subposition is dedesignated the hedge adjustment component must be transferred to the corresponding valuation components of the freestanding position. This is necessary in order to initialize the valuation components with the correct start values. The target components are derived from the classification components of the corresponding exposure subitem position:

The amount of the hedging reserve component (1301) is used to transfer the hedge adjustment to the spot valuation component (1105)

The amount of the ineffective hedging reserve component (1323) is used to transfer the hedge adjustment to the spot valuation component (1105)

The amount of the cost of hedging reserve component (1322) is used to transfer the hedge adjustment to the security valuation component (1002)

The amount of the ineffective cost of hedging reserve component (1333) is used to transfer the hedge adjustment to the security valuation component (1002)

The amount of the ineffective P&L component (1303) is used to transfer the hedge adjustment to the security valuation component (1002)

The amount of the amortization component (1345) is used to transfer the hedge adjustment to the security valuation component (1002)

**Related Information**

Creating a Dedesignation Request Process Dedesignation Request

###### Dedesignation by Termination

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Dedesignation by Termination | L5 | trm09 p.182 | loio `4cc30443141c4c388e3ad4c563f70fd2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4cc30443141c4c388e3ad4c563f70fd2.html?locale=en-US)

Termination of hedging instrument triggers the immediate complete dedesignation of the associated hedging relationships at the termination date.

**Use**

Usually the dedesignation of the hedging relationship takes place at the maturity date of the financial transaction (hedging business transaction Dedesignation). If you early terminate a financial transaction, which is used as hedging instrument in hedging relationships, the termination of the FX transactions results in the immediate complete dedesignation of these hedging relationships at the termination date (hedging business transaction Termination Dedesignation). Complete dedesignation means that all hedging instruments that are designated for the hedging relationship concerned are dedesignated.

The following general rules apply:

The termination date is the dedesignation date of the hedging relationship.

**Note:**

If more than one hedging instruments of a hedging relationship are terminated, the dedesignation occurs on the date of the earliest termination. Since swaps or FX collar options consist of two separate transactions, you must terminate both transactions separately.

During the release of the Termination Dedesignation hedging business transaction, if the termination date of the hedging instrument and the dedesignation date of the hedging relationship are equal, the system takes the termination amount as the current market value (NPV_RF) of the hedging instrument during the calculation of the market value components.

The date of theReclassificationhedging business transaction stays unchanged.

**Prerequisites**

Make sure that you’ve completed all required terminations before you start releasing the Termination Dedesignation hedging business transactions.

**Note:**

If you’ve released the Termination Dedesignation hedging business transaction for a hedging relationship and then want to terminate a hedging instrument for the hedging relationship with an earlier termination date, this is no longer possible. In this case, you would first have to reverse the release of the Termination Dedesignation hedging business transaction.

Relevant market data is available.

**Process Steps**

- 1. Terminate the financial transaction using the Process Spots/Forwards - Collective Processing and the Process OTC Options - Collective Processing apps.


The termination activity is available for the following FX transactions

FX forward

FX option

Non-deliverable Forward (NDF)

FX swap (consists of two FX forwards)

FX collar (consists of two FX options)

You enter the termination-relevant data on the Structure tab of the financial transaction. In the Termination area, you must enter the date of the termination and choose the entry type, such as Amount or Rate. Dependent on this setting, you either enter the payment amount manually or you enter the agreed termination rate and the system calculates the resulting

payment amount. You also must enter the payment date. The flow type 1039 Termination amount (of flow category 39) is predefined and set by default. After you entered the relevant data the payment flow is generated, the posting status of the original buy and purchase flows is set to 0.

With saving of the termination activity, the system creates a Termination OTC transactions business transaction. The Termination OTC transactions business transaction consists of the following flows:

Close flow of the OTC transaction at termination date to clear the nominals

Termination amount flow (representing the termination flow of the financial transaction)

The date of both flows is the payment date entered in theTerminationarea of the financial transaction.

- 2. If the terminated FX transaction is used as hedging instrument in hedging relationships at the termination date, the termination of the FX transactions results in the immediate complete dedesignation of these hedging relationships. The hedging business transaction Termination Dedesignation is automatically created for each associated hedging relationship. Complete dedesignation means that all hedging instruments that are designated for the hedging relationship concerned are dedesignated.
- 3. Open the Release Hedging Business Transactions app. Select the relevant hedging relationships whose Termination Dedesignation hedging business transaction are to be released. Execute the Release Hedging Business Transactions app.


**Note:**

If you must terminate a couple of hedging instruments, which belong together from a business point of view, first execute all the terminations and afterwards release theTermination Dedesignationbusiness transactions. As long as the hedging business transactions haven't been released they’re updated automatically, after the last termination they must have the final status and can be released.

- a. A final measurement of the hedging relationship is performed on the termination date to report and post the correct balances of the hedging reserve and cost of hedging reserve amounts. The balances of the hedging reserve and cost of hedging reserve are frozen when the financial transaction is closed with dedesignation: The balances of the hedging reserve and cost of hedging reserve are then transferred from the designated position component to the freestanding position component of the respective exposure subitem.

If the termination date of the hedging instrument and the dedesignation date of the hedging relationship are equal, the system takes the termination amount as the current market value (NPV_RF) of the hedging instrument during the calculation of the market value components.

If the termination date of the hedging instrument and the dedesignation date of the hedging relationship isn’t equal, the NPV of the financial transaction is calculated and stored at dedesignation date in the market data container.

- b. The element and contract rate component values of the financial transaction and the hypothetical derivative are calculated and stored in the market data container.
- c. The designated portion of the financial transaction with the actual NPV values is valuated and posted on key date.
- d. The selected hedging relationship with its contract rate component values is classified and posted.
- e. The amounts of the hedging reserve and cost of hedging reserve are transferred from the designated position component to the freestanding position component of the respective exposure subitem.


The balance of the freestanding position component acts as the basis for reclassification.

- f. The amounts of the dedesignation flows are updated.
- g. The status of the dedesignation flows is changed from Scheduled status to Fixed status.
- h. The amounts of the reclassification flows are updated and the status of the flows remains Scheduled.


**Note:**

The date of theReclassificationhedging business transaction stays unchanged.

**Related Information**

Collective Processing: Transaction Management Process OTC Options - Collective Processing Release Hedging Business Transactions

###### Change Reclassification-Relevant Dates

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Change Reclassification-Relevant Dates | L5 | trm09 p.184 | loio `304d201b3a254e349e6ff86fc83ffda9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/304d201b3a254e349e6ff86fc83ffda9.html?locale=en-US)

Change the balance sheet recognition date or the reclassification date of a hedging relationship.

**Use**

The balance sheet recognition date and the reclassification date of a hedging relationship are determined according to the settings in the hedging area.

If, in the hedging area on the Hedge Accounting I tab, the Consider Balance Sheet Recognition field values are set to 1, 2, or, 3, the hedging relationship has a balance sheet recognition date and a reclassification date.

If the hedging area does not consider the B/S recognition date (the Consider Balance Sheet Recognition field value is set to 0), the reclassification of the hedging reserve and cost of hedging reserve amounts is done at the end date of the exposure subitem. The end date of the exposure subitem is determined according to the settings made under Reclassification Offset Category on the Hedge Accounting I tab.

With this function, you can change these automatically determined dates for an already designated hedging relationship.

**Procedure**

- 1. Call the function in the area menu under Hedge Accounting for Positions Master Data Automated Designation Process Change Reclassification-Relevant Dates (transaction TPM122).
- 2. In the Date Change Parameters area, choose Change B/S Recognition Date or Change Reclassification Date.
- 3. In the General Selection area, you select the hedging relationship by specifying the following characteristics:


Company Code

Valuation Area

Financial Transaction

Transaction Number

Hedging Classification

Hedging Relationship

Hedging Relationship Number

Fiscal Year

Valid-From Date

Profile

Hedging Area

- Grouping Field 1

- Grouping Field 2

- Grouping Field 3


- 4. Choose Execute.

The system selects the hedging relationships corresponding to your selection criteria and displays them in a list.

The following information about the selected hedging relationship is displayed:

Company Code

Valuation Area

HR Number

You can jump to the hedging relationship data.

Fiscal Year in which the hedging relationship is created.

Hedging Relationship Description

Designation Date

Dedesignation Date

Either the Current B/S Recognition Date or the Current Reclassification Date.

Either a column for the New B/S Recognition Date or the New Reclassification Date is available.

In the last columns, you can see the status of the hedging relationship and the messages explaining the status. If you cannot change the reclassification-relevant date, the system shows a red traffic light   Errorsin the Status column. If you click the corresponding messages, you get further information.

You can change the dates of hedging relationships only when they have the hedging relationship status Designated.

- 5. Mark the row of the relevant hedging relationship.
- 6. Enter the new date.


**Note:**

Choose the Show All Messages button to get the error messages in an overall list.

The new date must fulfill the following rules:

The new balance sheet recognition date must be later than the designation date and earlier than the planned dedesignation date.

The new reclassification date must be later than the dedesignation date.

- 7. You can first test the change by choosing the Test Change button. If the new date is appropriate, a green traffic light   Date successfully changedis shown in the Status column. If the new date is not sufficient, a red traffic light   Errorsis shown in the Status column, and you can jump to the explanatory error message.


After a successful check, choose Execute Change.

**Result**

After you have executed the change, the balance sheet recognition date or the reclassification date is changed to the new date entered. You can see the changed date in the list and you can jump to the hedging relationship data to check the date there. The corresponding hedging business transaction, such as the Reclassification business transaction, is updated.

###### Contract Close

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Contract Close | L5 | trm09 p.186 | loio `d4b5c182dd6a4fa4824e64716c7efdef` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d4b5c182dd6a4fa4824e64716c7efdef.html?locale=en-US)

The following processes take place at the end of the hedging relationship and on the end date of the exposure subitem:

Exercise of FX Option

Dedesignation

Dedesignation is performed with the maturity date of the financial transaction and with the end of the hedging relationship.

You execute the Release Hedging Business Transactions (transaction TPM120) function to trigger the relevant process steps for the dedesignation of the financial transaction.

###### Exercise of FX Option

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Contract Close > Exercise of FX Option | L6 | trm09 p.186 | loio `2fe9a4a85d824a77b0110a7e9397bb55` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2fe9a4a85d824a77b0110a7e9397bb55.html?locale=en-US)

It is possible to designate the underlying FX spot/forward transaction of an FX option with the full nominal amount into the existing hedging relationship.

**Use**

You execute an FX option using Edit Financial Transactions function (transaction FTR_EDIT) or Process FX Options - Collective Processing app on SAP Fiori Launchpad or by calling the function in backend under Foreign Exchange Trading Collective Processing (transaction TI91).

Depending on several conditions the underlying FX transaction will be designated in a new hedging relationship, an existing hedging relationship or not designated at all.

Overview FX Option Exercise

|Hedging Classification of the FX Option|Hedging Classification of the Underlying FX Transaction|Result|
|---|---|---|
|No hedging Classification|No hedging classification or a hedging classification which is not hedge accounting relevant|No designation|
|No hedging classification|Hedge accounting relevant hedging classification|The FX transaction is designated in a new hedging relationship.|
|Yes|Hedge accounting relevant hedging classification|The FX transaction is designated in the existing hedging relationship of the FX option.|
|Yes|No hedging classification|No hedging classification or a hedging classification which is not hedge accounting relevant|


**Prerequisites**

You must assign an hedging profile (relevant for FX forwards) in the Profile Underlying field within the hedging profile of the existing hedging relationship (in the Customizing activity Define Hedging Profiles). The assigned hedging profile is needed to find the hedge accounting rule for the spot transaction.

You must define update types. The update types are needed for dedesignation transfer and designation transfer business transactions.

With the dedesignation transfer the position component values are transfered from the exercised FX option. With the designation transfer the position component values are transferred to the underlying FX spot/forward transaction.

Define the following update types in the Define and Assign Update Types Customizing activity and assign them under Assign Update Types for Business Transactions (P-HA) to Product Types to the relevant product types:

- THX015 Transfer Designation (positive)

- THX016 Transfer Designation (negative)

- THX017 Transfer Dedesignation (positive)

- THX018 Transfer Dedesignation (negative)


**Process**

During the FX option exercise process you must enter the hedging classification of the FX option on the Administration tab of the underlying spot transaction.

**Note:**

In case the hedging classification is not filled, the FX spot/forward is not designated into the hedging relationship.

Using Release Hedging Business Transactions (transaction TPM120) the system calculates the hedge accounting key figures at the Exercise Date and assigns a new market data container to the hedging relationship for the FX option as well as for the underlying FX spot/forward transaction.

###### Dedesignation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Contract Close > Dedesignation | L6 | trm09 p.188 | loio `bd8487a7fdc94e16a7646eca0a758c96` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bd8487a7fdc94e16a7646eca0a758c96.html?locale=en-US)

**Use**

Dedesignation of the hedging relationship takes place on the due date of the financial transaction.

You close the FX Forward transaction using Fix and Post Derived Business Transactions (transaction code TPM18).

A final measurement of the hedging relationship is performed on the due date of the FX Forward transaction to report and post the correct balances of the hedging reserve and cost of hedging reserve amounts. The balances of the hedging reserve and cost of hedging reserve are frozen when the FX transaction is closed with dedesignation: The balances of the hedging reserve and cost of hedging reserve are then transferred from the designated position component to the freestanding position component of the respective exposure subitem.

The balance of the freestanding position component acts as the basis for reclassification.

**Prerequisites**

The financial transaction was closed by carrying out the relevant postings and payment process steps on its maturity date.

Relevant market data is available which means that the dedesignation cannot be carried out until the end of business day.

**Process Steps**

- 1. Execute the Release Hedging Business Transactions function (transaction TPM120).
- 2. Select the relevant hedging relationships whose dedesignation flows are to be released.
- 3. The NPV of the financial transaction is calculated and stored in the market data container.
- 4. The element and contract rate component values of the financial transaction and the hypothetical derivative are calculated and stored in the market data container.
- 5. The designated portion of the financial transaction with the actual NPV values is valuated and posted on key date.
- 6. The selected hedging relationship with its contract rate component values is classified and posted.
- 7. The amounts of the hedging reserve and cost of hedging reserve are transferred from the designated position component to the freestanding position component of the respective exposure subitem.
- 8. The amounts of the dedesignation flows are updated.
- 9. The status of the dedesignation flows is changed from Scheduled status to Fixed status.


The amounts of the reclassification flows are updated and the status of the flows remains Scheduled.

**Note:**

This applies only if the dedesignation date is not the same as the reclassification date.

**Related Information**

Post Derived Business Transactions

**Reclassification**

**Use**

The reclassification date is determined according to the settings that you have made in the Balance Sheet Recognition field on the Hedge Accounting I tab of the hedging area. The following settings are available:

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

Reclassification Without Consideration of the Balance Sheet Recognition Date

- If you have chosen 0 - None the reclassification is done at the due date of the exposure subitem and handled by derived business transactions. You post the reclassification flows using Fix and Post Derived Business Transactions function (transaction TPM18).

Prerequisites

You have carried out the dedesignation of the hedging relationship as the balance of the freestanding position component acts as the basis for the reclassification process.

Process Steps

- 1. You use the Fix and Post Derived Business Transactions function (transaction TPM18) to select the exposure subitem position flows that you want to reclassify.
- 2. The position flows are fixed and posted according to the Customizing settings made for derived business transactions.
- 3. The following postings are made, depending on whether the balances of the hedging reserve and cost of hedging reserve are positive or negative:

Positive balance:

Hedging reserve to P/L

Cost of hedging reserve to P/L

Negative balance:

P/L to hedging reserve

P/L to cost of hedging reserve

P/L position amounts are fixed only.

- 4. The freestanding component values of the exposure subitem are set to zero:


Hedging reserve

Cost of hedging reserve

P/L

Reclassification Considers the Balance Sheet Recognition Date

- If you have chosen 1 - Immediate Reclassification at Balance Sheet Recognition Date, 2 - Reclassification at the End Date of the Exposure Subitem, or 3 - Reclassification at Alternative Reclassification Date, the reclassification is handled by the hedging business transaction reclassification and you post the reclassification flows using Release Hedging Business Transactions function (transaction TPM120).


**Note:**

This step creates postings to the P/L statement only if the value 0 or 2 has been maintained in the Balance Sheet Recognition field on the Hedge Accounting I tab of the hedging area.

ineffective

ineffective

This is necessary because the relevant data - such as market data - is only available at end-of-day processing.

The financial transaction is evaluated to ensure proper calculation of the reclassification amounts and the relevant hedging relationship is classified and posted on the reclassification date.

Process Steps

The following process steps are carried out when you execute the Release Hedging Business Transactions function:

- 1. The NPV of the financial transaction is calculated and stored in the market data container on balance sheet recognition date.
- 2. The elements and market value components of the financial transaction and the hypothetical derivative are calculated and stored in the market data container.
- 3. The designated portion of the financial transaction with the actual NPV values is valuated and posted on key date.
- 4. The selected hedging relationship with its contract rate component values is classified and posted.
- 5. The amounts of the reclassification update types are updated.
- 6. The reclassification update types are set from Scheduled status to Fixed.


**Note:**

In case the hedging relationship is dedesignated earlier using a dedesignation request, the reclassifiaction flows are also affected. For more information, see Process Dedesignation Request

**Related Information**

Post Derived Business Transactions

###### Reclassification

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Contract Close > Reclassification | L6 | trm09 p.186 | loio `c47251d2bbb642b9b81f63e4fd1b6028` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c47251d2bbb642b9b81f63e4fd1b6028.html?locale=en-US)

Reclassification of the hedging reserve and cost of hedging reserve amounts is performed on the end date of the exposure subitem.

**Note:**

Reclassification is performed at the end date of the exposure subitem only if you have set the value for balance sheet recognition in your hedging area to 2. If another value has been entered, reclassification takes place at another time.

The Fix and Post Derived Business Transactions function (transaction TPM18) selects the exposure subitem position flows to be reclassified. The flows are then fixed and posted according to the settings of the derived business transactions

**Related Information**

Contract Close - FX Swap

###### Contract Close - FX Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Contract Close > Contract Close - FX Swap | L6 | trm09 p.191 | loio `4802d3f344e5433da21945c265966a9d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4802d3f344e5433da21945c265966a9d.html?locale=en-US)

**Use**

The following processes take place at the end of each hedging relationship and on the end date of each exposure subitem:

- 1. Dedesignation is performed with the maturity date of the financial transaction and with the end of the hedging relationship. To trigger the corresponding process steps, use the Release Hedging Business Transactions function (transaction TPM120).
- 2. Reclassification of the hedging reserve and cost of hedging reserve amounts is performed on the end date of the exposure subitem.


**Note:**

Reclassification is performed at the end date of the exposure subitem only if you have set the value for balance sheet recognition in your hedging area to 2. If another value has been entered, reclassification takes place at another time.

The Fix and Post Derived Business Transactions function (transaction TPM18) selects the exposure subitem position flows to be reclassified. The flows are then fixed and posted according to the settings of the derived business transactions.

This process differs a little for FX swaps that were designated into a hedging relationship.

**Process Steps for FX Swap**

1. Dedesignation on the maturity date of original FX forward transaction and of the offsetting FX forward transaction of the FX swap

Original hedging relationship

The remaining portion of the original hedging relationship is dedesignated on the maturity date of the original FX forward transaction.

New hedging relationship

The new hedging relationship is valuated and classified as it was during period-end closing:

Each FX forward transaction is valuated and posted.

The classification result is calculated and posted for the new hedging relationship.

- 2. Reclassification on the end date of exposure subitem of the original hedging relationship

Original hedging relationship

Hedging reserve and cost of hedging reserve amounts of the exposure subitem are reclassified and posted.

New hedging relationship

No activities take place for the new hedging relationship at this point in time.

- 3. The original hedging relationship no longer exists, but the remaining FX forward transaction that belongs to the new hedging relationship still needs to be processed.
- 4. Period-end closing process after the maturity of the original FX forward transaction

Original hedging relationship

No longer exists.

New hedging relationship

The securing FX forward transaction of the FX swap and the remaining portion of the new hedging relationship are valuated, classified, and the results are posted.

- 5. Dedesignation at the maturity date of the securing FX forward transaction

Original hedging relationship

No longer exists.

New hedging relationship

The new hedging relationship is dedesignated on the maturity date of the remaining FX forward transaction.

- 6. Reclassification on the end date of the exposure subitem of the new hedging relationship


Original hedging relationship

No longer exists.

New hedging relationship

The hedging reserve and cost of hedging reserve amounts of the exposure subitem of the new hedging relationship are reclassified and posted.

**Related Information**

Contract Close

###### Reporting

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Reporting | L5 | trm09 p.192 | loio `c13e7f58655b9244e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c13e7f58655b9244e10000000a4450e5.html?locale=en-US)

**Use**

The existing reporting functions have been enhanced with the new Exposure Item product group to enable the reporting activities for the subledger positions of exposure subitems.

[figure TRM09-F052 - The existing reporting functions have been enhanced with the new Exposure Item product group to enable the reporting activities for the subledger positions of exposure subitems.]

Overview of Reporting Activities

Call the Treasury Position Values app to perform position reporting.

Enter your exposure item ID and exposure subitem ID to access the subledger positions of exposure subitems and their position component values, which are as follows:

Nominal Amount

To Be Classified - This value is determined during the classification of the financial transaction from the To Be Classified component of the financial transaction.

Effective/Hedging Reserve - This value is determined during the classification of the financial transaction from the To Be Classified component of the financial transaction.

Ineffective/Hedging Reserve Through Profit and Loss

Effective/Cost of Hedging Reserve - This value is determined during the classification of the financial transaction with the calculation result of the forward and CCBS components according to the calculation rules.

Ineffective/Cost of Hedging Reserve Through Profit and Loss

P/L

ineffecitve

Call the Treasury Position Flows app to perform position flow reporting.

Enter your exposure item ID and exposure subitem ID as reporting characteristics to obtain a list of the relevant position flows.

Call the Treasury Posting Journal app

Enter your exposure item ID and exposure subitem ID as reporting characteristics to produce a posting journal showing you the subledger positions for the exposure subitems.

G/L posting documents can also be accessed from the posting journal.

**More Information**

Hedge Accounting for Exposure Items

Release Hedging Business Transactions

Period-End Closing

###### Manage Hedging Relationships (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Manage Hedging Relationships | L5 | trm09 p.194 | loio `49bff4b439731b93e10000000a42189b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/49bff4b439731b93e10000000a42189b.html?locale=en-US)

**Use**

You can see the hedging relationships created during the automated designation of the Hedge Accounting for Exposure Items process. You cannot make any changes to these hedging relationship.

In the Hedging Relationship area, you see the number and the name of the hedging relationship. By choosing the pushbutton, you can display the flows of the hedging relationship as well as call up and perform the business transactions (designate, dedesignate, reverse, undo, and reactivate) for a hedging relationship.

You also see here the current status of the hedging relationship and the status of the effectiveness test.

[figure TRM09-F053 - You also see here the current status of the hedging relationship and the status of the effectiveness test.]

Overview of Manage Hedging Relationship

You can also use the following tabs:

Hedging Relationship Detail

Hedged Item

Hedging Instrument

Manage Hedging Relationships: Documentation

Manage Hedging Relationships: Effectiveness Test

**Prerequisites**

You have made the settings in Customizing. For more information, see Settings for Hedge Accounting for Exposure Items.

**Activities**

- 1. Call the function from the application menu of Transaction Manager under Hedge Accounting for Positions Master Data Manage Hedging Relationship (transaction TPM100) or open the Manage Hedging Relationships app on SAP Fiori launchpad.
- 2. Now select the hedging relationships that you want to edit. To do this, first define the work area that you want by choosing the company code, valuation area, and fiscal year. You can then restrict the number of hedging relationships to be chosen by entering specifications for thehedging relationship details and/or by choosing their status. Choose Start.
- 3. A list of the selected hedging relationships appears, and, by double-clicking, you can branch to the respective hedging relationship to view or process it.

###### Manage Hedging Relationships: Hedging Relationship Detail

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Manage Hedging Relationships > Manage Hedging Relationships: Hedging Relationship Detail | L6 | trm09 p.195 | loio `08710458d8553460e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/08710458d8553460e10000000a44147b.html?locale=en-US)

**Use**

Here you define the following basic information about the hedging relationship:

Risk Currency

The risk currency represents the currency of your exposure.

Target Currrency

The target currency is the currency in which the exposure amounts in risk currency are transferred/hedged by the hedging instrument.

Profile

The hedging profile is defined in Customizing and represents the hedging relationship scenario.

The hedging relationship scenario is a predefined system entity that contains information about the following:

Hedging relationship category

Hedged item category

Hedge accounting rule

Cardinality of the hedging relationship

Risk details

Category

The hedging relationship category is derived from the risk profile settings.

Currency Risk (information taken from the hedging profile)

Valid-From Date

The valid-from date represents the contract start date of the financial transaction.

Planned Designation Date

The planned designation date represents the contract start date of the financial transaction.

Planned Dedesignation Date

The planned dedesignation date represents the value date of the financial transaction.

If the hedging instument is a non-deliverable instrument, such as a non-deliverable forward, and if, on the Main Data tab in the hedging area, you have specified Fixing Date in the Date for Determining Exp.Itm for Non-Del. Inst. field, the planned dedesignation date is the fixing date.

Balance Sheet Recognition Date

The balance sheet recognition date is derived from the Balance Sheet Recognition settings on the Hedge Accounting I tab in the Designation Splitting area of the hedging area. This setting determines the relevant date for the processing of reclassification flows:

Balance Sheet Recognition Date = Due Date of the Hedging Instrument - Payment Term

**Note:**

The Balance Sheet Recognition Date is only available if you set the value 1 in the Define Hedging Areas function (transaction TOE_HEDGING_AREA).

Reclassification Date

The alternative reclassification date allows you to reclassify the hedging reserve and cost of hedging reserve amounts at a date other than the balance sheet recognition date and the end date of the exposure subitem. The alternative reclassification date is derived from the Balance Sheet Recognition settings on the Hedge Accounting I tab in the Designation Splitting area of the hedging area.

**Note:**

The Reclassification Date is available if you set the value 3 in the Define Hedging Areas function (transaction TOE_HEDGING_AREA).

Designation Type

The designation type is assigned in the hedging area and is a necessary characteristic for the release of the designation.

Calc.Rule Cost of H.Reserve

The calculation rule for the cost of hedging reserve is determined at the release of the designation (transaction TPM120). Once the designation business transaction has been fixed the calculation rule and its log is stored and displayed in the hedging relationship.

You can access the log displaying the determination steps for the calculation rule of the cost of hedging reserve by choosing Display Log.

If you reverse the designation, the calculation rule and its protocol are deleted from the hedging relationship.

Grouping information

Reference Category

Only relevant for collar FX options or FX swaps.

Reference

The number of the reference created for two plain vanilla FX options or for two FX forwards.

**More Information**

Manage Hedging Relationships

Hedge Accounting for Exposure Items

###### Manage Hedging Relationships: Hedged Item

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Manage Hedging Relationships > Manage Hedging Relationships: Hedged Item | L6 | trm09 p.197 | loio `f4710458d8553460e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f4710458d8553460e10000000a44147b.html?locale=en-US)

**Use**

The hedged item represents the operational exposure that results from designation splitting. The corresponding exposure item data was automatically determined from the snapshot of the hedging area.

This tab provides information about the following data:

Hedged Item

In the upper area of this tab, a list of all hedged items is displayed that belong to the corresponding hedging relationship.

You can navigate to the related hedging business transactions by selecting one line item from the list and choosing Display Hedged Item Related Transactions.

Hedged Item Details

Hedged Item Number

Start Date

The start date represents the contract start date of the financial transaction.

End Date

The end date of the hedging relationship is derived from the reclassification offset category of the relevant hedging area.

If the in hedging area a Due Date Shift is activated the end date of the hedged item is either the first day of the following month or the last day of the following month after the due date of the hedging instrument.

Category

The hedged item category represents the risk of a hedging relationship, such as planned forecast.

Hypothetical Derivative

The hypothetical derivative is used in effectiveness tests. During the effectiveness test, the hypothetical derivative represents the hedged item.

You can navigate to the hypothetical derivative by choosing the relevant one from the dropdown list and then choosing the Detail View button on the right.

Position Details

Product Group

The product group is the exposure item.

Valuation Class

The valuation class is automatically determined from the settings made in Customizing on the product type level.

Exposure Item

Item ID

The exposure item ID is a numeric identifier of an exposure item corresponding to a relevant exposure snapshot in the hedging area.

Choose the Display Exposure Item button to get an overview of the exposure item details.

Snapshot ID

The relevant snapshot ID is displayed and you can open a dialog box with detailed information about the snapshot corresponding to the exposure item.

Choose the Display Snapshot button to get an overview of the snapshot details.

Hedging Area

The corresponding hedging area is displayed here and you can jump to a detailed view of the hedging area.

Choose the Display Hedging Area button to navigate to the relevant hedging area and get an overview of the hedging area details.

Exposure Subitem

Subitem ID

The exposure subitem ID is a numeric identifier representing a hedged part of an exposure item. It is created automatically and was introduced for position management purposes.

Split ID

Use the Display Flows pushbutton to get an overview of the position flows that were created during the designation process of the exposure subitem.

To access the details of the exposure subitem, use the Display Position pushbutton.

To see the selected position management procedure, go to the Display Position Indicator, select the relevant position, and choose the Position Management Procedure pushbutton. The position indicator displays the following information about the exposure subitem:

Company Code

The company code is derived from the hedging area.

Accounting Code

The accounting code is derived from the company code.

Product Type

The product type is derived from the hedging area.

Valuation Area

The valuation area is derived from the hedging area.

General Valuation Area

The general valuation area is determined from the settings made in Customizing for the Transaction Manager under General Settings Accounting Assign General Valuation Class to Product Type .

Position Management Procedure

The position management procedure is determined from settings made in Customizing for the Transaction Manager under General Settings Accounting Settings for Position Management Assign Position Management Procedure .


Exposure Item ID

The exposure item ID represents the relevant exposure snapshot and is created automatically.

Exposure Subitem ID

The exposure subitem ID represents the hedged part of an exposure item and is created automatically.

**More Information**

Manage Hedging Relationships

Hedge Accounting for Exposure Items

###### Manage Hedging Relationships: Hedging Instrument

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Manage Hedging Relationships > Manage Hedging Relationships: Hedging Instrument | L6 | trm09 p.199 | loio `bd720458d8553460e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bd720458d8553460e10000000a44147b.html?locale=en-US)

**Use**

On this tab, you assign the hedging instrument to be used in the hedging relationship.

The hedging instrument represents the financial transaction that was created for the hedging process of the exposure item. The portion of the financial transaction that is designated into the hedging relationship is determined based on the designation splitting defined in the hedging area.

This tab contains the following key figures:

Hedging Instrument

In the upper area of this tab, a list of all hedging instruments is displayed that belong to the corresponding hedging relationship.

You can navigate to the related hedging business transactions by selecting one line item from the list and choosing Display Hedged Item Related Transactions.

Hedging Instrument Details

Hedging Instrument Number

This is an automatically-generated number that identifies the hedging instrument.

Position Details

Product Group

Valuation Class

The valuation class is automatically determined from the settings made in Customizing on the product type level.

Transaction Number

The transaction number represents the key of your financial transaction.

Start Date

The start date represents the contract date of the financial transaction.

End Date

The end date represents the value date of the financial transaction.

You use the Display Flows pushbutton to get an overview of the position flows that were created during the designation process of the financial transaction.

Use the Display Position pushbutton to get an overview of the subposition details relevant to the financial transaction.

Choose Display Position Indicator to see the selected position management procedure of the financial transaction.

Navigate to the relevant FX transaction by choosing Display Transaction.

**More Information**

Manage Hedging Relationships

Hedge Accounting for Exposure Items

###### Manage Hedging Relationships: Documentation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Manage Hedging Relationships > Manage Hedging Relationships: Documentation | L6 | trm09 p.200 | loio `0858fd47cbee41d5bfde1ed8f25b32ce` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0858fd47cbee41d5bfde1ed8f25b32ce.html?locale=en-US)

View the existing documentation for the hedging relationship

On the top of the tab page you get list of documentation files created for the hedging relationship.

In the Documentation Details area you can see the following information for the selected documentation:

Version Number

Documentation Status

Ref.to Bus.Trans. and Bus.Trans.Date

PDF-Based Forms: Form Name

In the Originals area you can mark the listed document and choose Display Original to view the documentation.

**Related Information**

Documentation of a Hedging Relationship

###### Manage Hedging Relationships: Effectiveness Test

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Manage Hedging Relationships > Manage Hedging Relationships: Effectiveness Test | L6 | trm09 p.200 | loio `5e3308eb2c9a419789aa9d0a7dc42bc3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5e3308eb2c9a419789aa9d0a7dc42bc3.html?locale=en-US)

Shows the result of the prospective effective test performed at designation.

On this tab, the following tabs show details on the effectiveness tests relevant for the hedging relationship:

Test Plan tab

During the automated designation process a line is created in the test plan for the required prospective effectiveness test at designation.

Test Execution

One line for each executed effectiveness test. The status icon shows whether the prospective effectiveness test was effective (green) or not effective (red).

When you click on the status icon, you see the details of the performed prospective effectiveness test:

In the Effectiveness Test Details area you see the effectiveness test result (Effective or Not Effective) displayed as green or red icon.

2

On the Eff. Test Result tab the results of the linear regression analysis (Slope, R ) are displayed and compared with the border conditions defined in the effectiveness test method.

The H.Item/H.Instr.Values tab shows all market value components not only the designated ones for the hedging instruments and the hypothetical derivatives calculated at designation and also using a market data scenario or market data selection date (see corresponding columns).

The Detail Log button in the toolbar offers a detail log for each individual row.

The Display Lin. Regr. Details button navigates to the details of the linear regression analysis.

Each line refers to a market data scenario or market data selection date and contains the delta of the designated components of the hypothetical derivative (explanatory variable) and the hedging instrument (explained variable).

**Note:**

The graphical representation of the data points along with the calculated line is only available in the back-end transaction.

###### Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk) | L5 | trm09 p.201 | loio `18a74029b4d7404ca2209dac74ae8b8e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/18a74029b4d7404ca2209dac74ae8b8e.html?locale=en-US)

If you start the Hedge Management and Accounting of Net Open Exposures (FX Risk) process, you must initialize existing hedging activities within the new functionality. The new process enables you to post your hedging activities according to IFRS9. Within the initialization, you transfer the existing hedging activities that have been posted in FI according to IAS39 to the new standard.

Execute the following steps during the initialization phase:

- 1. Set up the Hedge Management and Accounting of Net Open Exposures process.


In particular, define your hedging areas. The validity of the hedging area version must start before the start date of the oldest financial transaction used as hedging instrument for current exposures.

In addition, make the following specific settings relevant for the initialization:

Defining Update Types for Migration

In Customizing for Financial Supply Chain Management under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions Define Update Types and Assign Usages you must define the following update types and assign them to the Hedge Accounting Initialization usage.

- HAI_H003 Hedge Migration - Security Valuation write-up

- HAI_H004 Hedge Migration - Security Valuation write-down


- HAI_H005 Hedge Migration - Hedge Adjustment write-up

- HAI_H006 Hedge Migration - Hedge Adjustment write-down

- HAI_H007 Hedge Migration - To-Be-Classified write-up

- HAI_H008 Hedge Migration - To-Be-Classified write-down


HRELINIT Init Hedging Relationship (Migration)

In the Assign Update Types for Initializing Positions Customizing activity in the Customizing for Financial Supply Chain Management under Treasury and Risk Management Transaction Manager General Settings

Accounting Initialize Positions Update Types you must assign the HRELINIT update type on the level of product type on the Hedge Migration tab in the Hedging Relationship Initialization field. In the following fields you must assign the update types HAI_H003 - HAI_H008, which create the required flows during the first key date valuation of a migrated financial instrument. The flows clear the security valuation, increase the hedge adjustment, and post the amount as to be classified.

In Customizing for Financial Supply Chain Management under Treasury and Risk Management Transaction Manager General Settings Accounting Settings for Position Management Set Effects of Update Types on Position Components you assign the Indirect Position Change position change category to the HRELINIT update type for the initialization.

- 2. Enter the current exposures in Exposure Management 2.0
- 3. Take a snapshot (transaction TOESNAP) for all your hedging areas. For the initialization, you need a snapshot with a validity before the oldest financial transaction used as hedging instrument and within the validity of the relevant hedging area version.
- 4. The financial transactions used as hedging instruments must be available in the transaction management of Treasury and Risk Management.
- 5. If the traded currency field is not filled for these transactions, you fill the traded currency field by using the Initialization of Traded Currencies report (transaction TPM_MIG_TRADED_CURR).
- 6. In addition, you assigned the relevant hedging classifications on the Administration tab in the financial transaction data using the Initialization of Hedging Classifications report (transaction TPM_MIG_HEDGING_CLASS).
- 7. Determine NPVs Including CVA/DVA (transaction TPM60CVA) for all hedging instruments.
- 8. Run valuation (transaction TPM1) at the same day for all hedging instruments.
- 9. Initialize the hedging relationships (transaction TPM_HREL_INIT) at the day after the valuation.
- 10. Release the hedging relationship (transaction TPM120) at the day after the valuation.
- 11. Determine NPVs Including CVA/DVA (transaction TPM60CVA) at the day after the first valuation for all hedging instruments.
- 12. Run second valuation (transaction TPM1) at the day after the first valuation for all hedging instruments.
- 13. Run classification (transaction TPM101).
- 14. Take a new snapshot (transaction TOESNAP) for all your hedging areas.


**Note:**

The market value components of the hedge accounting key figures are calculated for the start date of the financial transaction.

**See also**

For further information, see also 2575709 .

**Related Information**

Take Snapshot Initialize Traded Currencies Initialize Hedging Classifications Initialize Hedging Relationships Calculate Net Present Values - Including CVA and DVA Run Valuation Period-End Closing

###### Initialize Traded Currencies

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk) > Initialize Traded Currencies | L6 | trm09 p.203 | loio `a2495f394bce470cb2834656c929323d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a2495f394bce470cb2834656c929323d.html?locale=en-US)

SAP Treasury and Risk Management uses the traded currency for FX forward transactions (FX forwards) and OTC options. You use this report to initialize the traded currency for FX forwards and FX options.

If you execute the Initialize Traded Currencies report (transaction TPM_MIG_TRADED_CURR), the system lists all financial transactions with an unfilled traded currency field, and proposes a traded currency.

**Integration**

This report is relevant if you start with the Hedge Management and Accounting of Net Open Exposures process and must initialize existing hedging relationships.

The following reports are also available for this initialization:

Initialize Hedging Classification in FX forwards and FX options (transaction TPM_MIG_HEDGING_CLASS)

Initialize Hedging Relationships (transaction TPM_HREL_INIT)

**Activities**

- 1. Call transaction TPM_MIG_TRADED_CURR
- 2. Select the financial transactions using the general and OTC transaction-specific selection criteria.
- 3. You can choose to fill the traded currency and update the amount input automatically:


Amount Input

If you choose this option, the currency of this amount is used as traded currency.

Round Amount

If choose this option, the traded currency is determined as follows:

If the buy amount is a round amount with ending zeroes, the buy amount currency is used as traded currency.

If the sell amount is a round amount with ending zeroes, the sell amount currency is used as traded currency.

You can also manually enter or change a traded currency.

- 4. Execute the report.
- 5. The system lists all selected financial transactions (FX forwards and FX options) with an unfilled traded currency field, and proposes a traded currency.

You can change the proposals.

- 6. Save your entries.


**Related Information**

Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk)

###### Initialize Hedging Classifications

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk) > Initialize Hedging Classifications | L6 | trm09 p.204 | loio `cb2d040cdebc41318da60d933f09b2e6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cb2d040cdebc41318da60d933f09b2e6.html?locale=en-US)

You use this report to initialize the hedging classification on the Administration tab in financial transaction data of FX forwards and FX options.

The hedging classification is relevant for the Hedge Management and Accounting for Net Open Exposures (FX Risk) process. Within this process, the automated creation of hedging relationships for hedging-relevant FX forwards and OTC options starts if a hedge-accounting relevant hedging classification is assigned to financial transactions. If you enter the hedging classification with this report, the automated creation of hedging relationships does not occur.

**Integration**

The report Initialize Hedging Classifications (transaction TPM_MIG_HEDGING_CLASS) is part of the Initialization of Hedge Management and Accounting of Net Open Exposures.

The following reports are also available for this initialization process:

Initialize Traded Currency for FX Forwards and FX Options (transaction TPM_MIG_TRADED_CURR)

Initialize Hedging Relationships (transaction TPM_HREL_INIT)

**Features**

With this report, you select the financial transactions for which you want to enter the hedging classifications. In the results list, you can enter the hedging classifications for the financial transactions that haven't had a hedging classification so far. In addition, you can change an existing assignment, but you cannot change an existing assignment when the financial transaction is already designated in a hedging relationship.

Selection

You can select the financial transactions for which you want to enter the hedging classifications by using the following selection criteria:

General Selections

Company Code

Product Type

Valuation Class

OTC Transactions

Transaction

Transaction Type

Portfolio

Assignment

Internal Reference

Characteristics

Finance Project

Activity Category

Business Partner

Active Status

Traded Currency

You can enter a hedging classification on the selection screen in the Hedging Classification area. The system enters this hedging classification in the list for all financial transaction that haven't had a hedging classification so far. This proposal can be changed in the list

If you set the Transactions with Initial Hedging Classification indicator, the system does not select financial transactions that already have a hedging classification assigned.

Output

When you made your selections and executed the report, you get a list with all selected financial transactions. In addition to the columns identifying the financial transaction, the list also has the Hedging Classification and Status (of the Hedging Relationship) columns.

You can carry out the following actions:

Enter the hedging classification in the Hedging Classification column or change the proposal entered due to your settings on the selection screen.

Change Hedging Classification

To change an existing assignment of a hedging classification, mark the row and choose Change Hedging Classification. If the financial transaction is already part of a hedging relationship in Hedge Accounting for Positions, you can no longer change the hedging classification.•

Save Hedging Classification for selected entries

Mark the row and choose Save Hedging Classification. The entered data are saved in the data of the financial transactions.

**Related Information**

Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk)

###### Initialize Hedging Relationships

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposure Items > Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk) > Initialize Hedging Relationships | L6 | trm09 p.205 | loio `47dbde91fe8a40ffa777323011ba0936` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/47dbde91fe8a40ffa777323011ba0936.html?locale=en-US)

With this report, you create the hedging relationships for existing forward exchange transactions (FX forwards), FX options, and collar FX options used as hedging instruments for net open exposures.

**Integration**

The Initialize Hedging Relationships report (transaction TPM_HREL_INIT) is relevant if you start with the Hedge Management and Accounting of Net Open Exposures process and need to initialize existing hedging relationships.

The following reports are also available for this initialization process:

Initialize traded currency for FX forwards and FX options (transaction TPM_MIG_TRADED_CURR)

Initialize hedging classification in FX forwards and FX options (transaction TPM_MIG_HEDGING_CLASS)

**Prerequisites**

See also: Initialize Hedge Management and Accounting of Net Open Exposures (FX Risk)

**Features**

When you execute this report, the system creates hedging relationships for the selected financial transactions with the specified planned designation date.

**Note:**

The Reprocess Financial Transactions for Automated Designation function (transaction TPM104) does not select transactions with errors that occurred during the initialization of existing hedging relationships. Reprocess the transaction with the TPM_HREL_INIT function after you correct the errors.

If you process an FX option that belongs to a collar FX option, the system automatically processes the other FX option that belongs to the collar FX option.

You can reverse a hedging relationship that you have previously created with this report.

