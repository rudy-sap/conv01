# Risk Management > Credit Risk Analyzer - SAP TRM Knowledge Base (branch split)

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

#### Credit Risk Analyzer

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer | L3 | trm03 p.144 | loio `bc08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bc08da531198434de10000000a174cb4.html?locale=en-US)

This TRM component enables you to measure, analyze, and control default risks. Default risk refers to the potential loss arising from a financial transaction should the business partner not fulfill his contractual obligations due to specific economic or political reasons.

**Purpose**

Counterparty/issuer risk describes the danger of a loss in the value of a receivable due to a worsening of the creditworthiness of the business partner. Counterparty/issuer risks are subdivided into credit risk and settlement risk. The existence of both these risks depends on the timing of the analysis of the transactions. Credit risks exist over the whole term of the transactions.

Settlement risks exist only during the settlement period. Credit risk can consist in a pure counterparty risk or an issuer risk, depending on the transaction category (for example, securities transactions).

**Implementation Considerations**

The tightening of regulations on risk controlling endorses the increasing significance of analyzing and limiting insolvency risks. Commercial considerations also make it essential to have a system that supports the measurement, analysis, control, and limitation of counterparty/issuer risks.

**Features**

Attributable Amount Determination - Market-Based Quantification of Various Exposures

The system calculates attributable amounts for each single transaction entered, showing the risk content of the respective transaction. Credit and settlement risks from classic credit transactions and trading book transactions are taken into account when quantifying default risk. Default risk is calculated based on counterparties and issuers.

The level of the default risk arising from classic credit transactions is determined by the amount of the capital commitment of the contract and the current drawings.

In the case of trading transactions, the level of the default risk is governed by the potential replacement cost that would arise in the case of default by a business partner. The potential additional loss from a potential positive market value change of an existing transaction can be covered by transaction-specific markup rates.

The calculated risks are assigned to all affected portfolio segments, for example, the counterparty, the industry sector, the product, or a combination of these.

**Note:**

Attributable Amount Determination - Based on Credit Value Adjustments

You can use credit value adjustments (CVAs) as a key figure category within the attributable amount calculation in Limit Management for financial transactions (OTC) and bank accounts. A credit value adjustment (CVA) is the amount by which the risk-free NPV of a financial transaction or bank account is adjusted to reflect the probability of a default by a business partner. CVA is a positive amount.

For more information, see also Attributable Amount Calculation Based on Credit Value Adjustments

Limit Management – Controlling Risk by Setting up and Monitoring Limits

Different limits are stored in central limit management. These can relate to one or more criteria ( Limit Characteristics ). Limits reflect the organization’s allocations.

Updating Limits and Comparing Attributable Amounts with Limits

The integrated default risk limit check assesses the risk of each single transaction at the time the financial transaction is created in the Transaction Manager. Each transaction is checked against the relevant limits and updated. You can also let the system update limit utilizations by revaluing all items in end-of-day processing. For risk control purposes, the relevant

limit utilizations are shown in aggregated form.

Additional Notes

You can find the functions of the Credit Risk Analyzer in the application by choosing Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer .

You can find the relevant settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer.

**Note:**

The integrated default risk limit check is to be understood as an integrated single transaction check. Therefore, information provided for the single transaction check in sections of the documentation not specifically referring to the single transaction check (for example, updating limit utilizations) also applies for the integrated default risk limit check.

##### Limit Management

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management | L4 | trm03 p.146 | loio `fc09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fc09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Due to risk controlling regulations as well as for purely business reasons, you need to measure, analyze, and control counterparty/issuer risks.

By setting different maximum risk amounts, you aim to limit the potential harm caused by the insolvency of a business partner. Further, you can deploy a system of limits to control the actions of traders.

This function helps you to control counterparty/issuer risks by means of limits and online monitoring. It also enables you to create comprehensive reports that can be used for internal and external purposes.

**Features**

Limit management offers functions for controlling risk by means of limits, which you set up, and for monitoring those limits to ensure that they are not exceeded. You can combine the characteristics available in any way, which gives you a highly flexible means of managing limits.

###### Limit Characteristics

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limit Characteristics | L5 | trm03 p.146 | loio `770ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/770ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

There are four types of limit characteristics:

Direct limit characteristics

Derived characteristics

Free (or custom) limit characteristics

Generated characteristics

**Use**

You need to assign at least one limit characteristic to each limit type. In the application, you can then in turn store a limit for any combination of limit characteristic values.

Structure

You can differentiate between direct and derived limit characteristics. Direct limit characteristics are those derived directly from the data of a transaction. Derived limit characteristics are those derived from direct characteristics, such as the business partner.

Direct characteristics:

Company code

Business partner

Limit product group

Portfolio

Trader

Currency as a limit characteristic

Monitoring unit

Internal organizational unit

Derived characteristics:

Country/Region (from business partner)

Industry (from business partner)

Rating (from business partner)

Free (custom) characteristics:

You also have the option of creating 15 free characteristics as limit characteristics. You can derive these from the characteristics provided by SAP with the help of the SAP enhancement concept. One example of a free limit characteristic could be a geographical group of countries/regions with the characteristic values Asia, Latin America, North America and Western Europe. In this case, the values would be derived from the characteristic country/region of the business partner.

Generated characteristics:

You are also able to take characteristics from the active analysis structure in the Market Risk component, generate them in Limit Management, and use them there as limit characteristics. If you are using generated characteristics, you are able to use them in all Limit Management functions in the same way as direct characteristics.

###### Creating Free Characteristics and Characteristic Values

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limit Characteristics > Creating Free Characteristics and Characteristic Values | L6 | trm03 p.147 | loio `500ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/500ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

To achieve greater flexibility with regard to the selection of the limit characteristics, you can also derive free characteristics from existing limit characteristics. When you do this, limit characteristic values are grouped together to create a new free characteristic value.

**Prerequisites**

If you want to use free characteristics and set up values for these free characteristics, particular customer exits have to be activated in SAP enhancement management. This involves some additional steps, which are described below.

**Procedure**

To assign descriptions to the free characteristics, you first need to do the following:

Create a project by using transaction code CMOD.

The system displays the Project Management of SAP Enhancements screen.


Choose to display a description of customer exits for SAP transactions. You can find a detailed description in the documentation about the enhancement concept.


Create a project as per the enhancement concept.

Assign enhancement LTBLX001 to the project.

Save the project by choosing and activate it with Activate Project.




The exit is not performed unless it is activated.

Changing the description of free characteristics

Choose Goto Text Enhancements Keywords Change , and then specify one of the data elements described below, for which you wish to change the text.


In the Customizing for the definition of free characteristics and their characteristic values you can find free characteristics 01-15, to which are assigned data elements TB_RCID01 to TB_RCID15.

The system displays the Change Key Word screen.

Enter the required descriptions for the selected free characteristic.

You can define multiple free characteristic texts simultaneously.

Choose Save to save your entries.



You can group together the characteristic values for free characteristic values by using customer exit EXIT_SAPLTBLX_001.


You can use the sample coding in include LXTBL1F01 to help you.

Now, using the customer exit, you derive the free characteristics you defined from the characteristics provided by SAP, and activate the exit.

To assign the defined characteristic values to the free characteristics, do the following:

In Customizing, choose Limit Management Define Free Characteristics and Characteristic Values .

The system displays the screen Display View "Selection of Characteristic IDs": Overview.

Select a free characteristic and choose Assignment of Values.

Choose New Entries, assign the characteristic values to the selected free characteristic and save your entries with .

In transaction CMOD, you can also display the SAP documentation about SAP enhancements. To do so, on the screen display Project Management of SAP Enhancements, choose the project and then choose Display to display the SAP enhancements. Select an enhancement and choose Enhancements.


**Result**

You have now:

Entered descriptions for free characteristics.

Grouped characteristic values into free characteristic values, and activated exit EXIT_SAPLTBLX_001.

Assigned free characteristic values to free characteristics.

###### Generated Characteristics

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limit Characteristics > Generated Characteristics | L6 | trm03 p.149 | loio `6e0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6e0ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

Generated characteristics are the characteristics that are generated from the active analysis structure of the Market Risk component, and that are used there as limit characteristics.

**Use**

By using generated characteristics, you are able to define you own additional characteristics (compared to customer-defined characteristics, which are derived from existing limit characteristics).

Generated characteristics are transferred from Market Risk to Limit Management in Customizing under Limit Management

Generated Characteristics . To do this, you first need to make some settings in the Customizing for Market Risk. You find the settings under the path given above. You can still use the generated characteristics even if you are not using the Market Risk component.

Provided you have transferred the generated characteristics, you are able to use these in all Limit Management functions in the same way as direct characteristics. Note, however, that in financial object maintenance, you do not maintain the values of analysis characteristics in the default risk limit part. Instead, you maintain these values in the screen Maintain Financial Object: General Part , which you access by clicking on the button Analysis (RM) in the application toolbar.

**Note:**

You can use service report RFTBLT05 to check the consistency of the generated analysis characteristics, and service report RFTBLT04 for their reorganization. For more information see the relevant report documentation.

Example

If you want to break down and limit the default risk by profit center, you can generate the characteristic Profit Center in Limit Management.

###### Limit Types

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limit Types | L5 | trm03 p.150 | loio `c009da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c009da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The limit type comprises limits and limit utilizations. When you define a limit type, you can assign individual limit characteristics or combinations of the various limit characteristics that are available in the system settings.

**Note:**

When you create a limit type filter, you use limit characteristics to restrict the respective limit type by freely definable ranges. Use of the limit type filter is optional. You can use it to create additional criteria to the limit characteristics of a limit type to help you make decisions, such as whether transactions are to be attributed to a particular limit type. You create limit type filters in the same place in Customizing in which you create limit types.

**Use**

Using the combination of the characteristic values of the limit type, the system selects the risks of the respective transactions and compares the total of these with the limits. You create limit types in Customizing by choosing Limit Management Define Limit Types .

**Example**

The following limit types were created in Customizing:

|One-Dimensional Limit Types|Multi-Dimensional Limit Types|
|---|---|
|Industry|Partner/limit product group/trader|
|Partner|Limit product group/trader|
|Limit product group (LGP)| |
|Trader| |


In the example, the limit type partner/limit product group/trader is a combination of the limit characteristics business partner number, limit product group and trader.

###### Display Filters

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Display Filters | L5 | trm03 p.150 | loio `710ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/710ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The display filter allows you to display the data relevant to you. As it is stored centrally, you can use the filter in all Limit Management applications.

**Use**

You can maintain any number of characteristics for each user according to his/her area of responsibility.

You can use the display filter in the following areas:

Limit maintenance

All the reporting tools (ALV, drilldown, query)

**Activities**

You can define the display filter in the Customizing for the Limit Management component, or directly in the application:

Customizing: Limit Management Define Display Filters for Limit Management

Application: Environment Current Settings Define Display Filters for Limit Management

Defining display filters

Choose New Entries.

Enter a name for the display filter.

Enter a short, medium, and long field label.

Save your entries by choosing .

You have now created a display filter to which you can assign limit characteristics in the following steps:

Select the display filter, and then choose Assign Limit Characteristics to Display Filters.

Choose New Entries.

Enter a limit characteristic.

If required, assign a filter number. You only need to do this if you want to store more than one filter for the same limit type.

Enter the lower limit for the characteristic.

If required, enter an upper limit for the characteristic. Using the field Incl/Excl, you can define whether the system should calculate everything within the specified range, or everything outside the specified range.

Save your entries by choosing .

###### Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits | L5 | trm03 p.151 | loio `560ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/560ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A limit is the maximum amount of limit utilizations, or drawings. It refers to certain values of the limit characteristics of a limit type.

**Use**

The limit acts as an amount against which checks are made to determine whether the limit has been exceeded. Each limit has a validity period.

If you want to change the value of the limit, then instead of invalidating the limit and creating a new one, you can simply split the validity period of the limit. You can define whether you want to change the future part of the limit only, or change the history of the limit as well. The new part of the limit is different from the old part of the limit only in terms of its amount and its validity period. The validity period of the new limit is the remaining validity period of the original limit. If the split limit contains one or more interim limits, then the system adjusts these appropriately.

**Structure**

A limit, which applies for certain limit characteristic values, is comprised of the following:

A 'valid from' date

An internal 'valid to' date

An external 'valid to' date

A limit currency (you can change the currency even after you have saved the limit)

An internal limit amount

An external limit amount

A critical limit utilization

A maximum risk commitment period

Administration data (origin of the limit, release status and review date ).

Data about the interim limit

Data about the limit transfer

###### Editing Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Editing Limits | L6 | trm03 p.152 | loio `ff09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ff09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can create characteristic values for each combination of limit characteristics defined in a limit type.

**Prerequisites**

Before you can create limits, you need to have already created at least one limit type.

**Note:**

You create limit types in Customizing by choosing Limit Management Define Limit Types .

**Procedure**

- 1. Choose Master Data Limits Maintain or Edit. The system displays the view Limits: Choose Limit Types.
- 2. Select one or more limit types.
- 3. Select one of the following functions:


Create Limits (CTRL + F3)



Change Limits (Shift + F4); ...with Selection Change Limits Using Preselection (Shift + F5)

Display Limits (Shift + F6); ...with Selection Display Limits Using Preselection (Shift + F7)



**Creating Limits**

- 1. To create a limit choose Create Limits. The system displays a dialog box in which you enter the characteristics relevant for the limit type.
- 2. Choose Continue.



The system then displays the screen Edit Limits for Limit Type xxx: Create New Limit.

Enter the following data:

Characteristics for the Limit Type

|Limits|Explanation|
|---|---|
|Valid From Date|Default value: Today’s date|
|Valid To (Internal)|Default value: 12/31/9999|
|Valid To (External)|The external valid to date and the internal valid to date (which is not dependent on the external valid to date) together form a time range. The traffic light display in the overview of limit utilizations is yellow (warning) if today's date falls within this range. Default value: Blank  Since the limit amount and validity date parameters are independent, the traffic light is set to yellow in the following cases: If the external validity of the limit has expired and the external limit amount has not been exceeded; if the external limit amount has been exceeded, but the external validity period has not expired. If the external validity period has expired (validity period has passed) but the external limit amount has been exceeded|
|Limit - Check/No Check|This field prompts the system to check the limit in reporting or in the single transaction check against the existing utilizations. If the field is set to Check, a red traffic light is displayed in reporting if the limit is exceeded. If it is set to Do not check, then in reporting and in the single transaction check no red traffic light is displayed for exceeded limits.|
|Limit Currency|You can enter a default currency in the Limit Currency field in the Customizing for the limit type. If no such setting was made in Customizing, the default value is the currency of the company code. You can change the currency even after you have saved the limit. The system converts the currency of all transactions attributed to this credit line to the limit currency.|


|Limits|Explanation|
|---|---|
|Internal Limit Amount|The internal limit amount is always greater than the external limit amount and critical limit usage.|
|External Limit Amount|The external limit amount is always less than the internal limit amount. It triggers a warning (yellow traffic light) once a certain amount has been exceeded.  In Customizing, you define whether the early warning is triggered by an external limit amount or by a percentage of the internal limit amount.|
|Critical Limit Utilization in %|This triggers a warning (yellow traffic light) once a particular percentage of the internal limit amount has been exceeded.  In Customizing, you define whether the early warning is triggered by an external limit amount or by a percentage of the internal limit amount.|
|Maximum Risk Commitment Period in Months|The maximum risk commitment period specifies with which risk commitment period a transaction may still be attributed to the limit.|


**Note:**

When entering limits, use the input help: T for thousand and M for million.

|Administrative Data|Explanation|
|---|---|
|Origin of Limit|The entry in this field specifies whether a limit was created manually, automatically during generation of the limit utilizations, or by a limit transfer. The system enters this information automatically.|
|Release Status|In Customizing, you can activate the release procedure for each limit type. |
|Automatic Review|The settings made in Customizing determine whether this indicator is displayed. You can also review limits manually. |
|Review Recipient|The review recipient is set by default to the user who entered the limit. You can change this in any way you like.|
|Review Date| |


|Interim Limits|Explanation|
|---|---|
|Start|Start date of the interim limit|
|End|End date of the interim limit|
|Internal Delta|See Internal Limit Amount|
|External Delta|See External Limit Amount|


|Interim Limits|Explanation|
|---|---|
|Currency|The currency of the interim limit can differ from that of the limit itself or of other interim limits. You can also change it even after you have saved the interim limit.|
|Release Status|Not subject to release Not released Flagged Released|
|Released By|The user name of the person who created the limit is the default setting.|
|Name|Free entry|


**Recommendation:**

For more information about interim limits, see Editing Interim Limits.

|Limit Transfer|Explanation|
|---|---|
|Start|Start of the validity of the limit transfer|
|End|End of the validity of the limit transfer|
|+/- Sign|The plus/minus sign specifies whether the respective amount of the limit transfer is to be added to or deducted from the limit.|
|Internal Delta|See Internal Limit Amount|
|External Delta|See External Limit Amount|
|Currency|The currency of the limit transfer can differ from that of the limit to or from which it is to be transferred.|
|Name|Free entry|
| Display, Change and Delete  |If a limit transfer already exists, you can use these icons to branch to the display or change screen, or to delete the limit transfer.|


**Recommendation:**

For more detailed information about limit transfers, see Processing Limit Transfers.

**Note:**

Limit maintenance has its own authorization object: F_T_VTBLV.

**Automatic Creation of Limits**

You can create limits automatically by using a report. This takes place by either direct input or batch input.

Direct Input:

- 1. You access the main menu for the direct input system by choosing System Services Direct Input .
- 2. Choose the program TB_LIMITS_INSERT_Dl.
- 3. For more information about the procedure and the function module, choose Help Application Help .

Batch Input:

- 4. You access the main menu for the batch input system by choosing System Services Batch Input Sessions .
- 5. Call the program RFTBLBI1.
- 6. You can view the report documentation that contains information on the next steps by choosing Help Application Help


.


**Changing Limits**

- 1. To edit a limit choose Change.


- 2. The system displays the screen Edit Limits for Limit Types: Overview. All limits are listed there that exist for the selected limit type and, if applicable, the selection criteria.

- a. You can display the documents for changes made to these limits by choosing Change Documents.
- b. You can enter notes by choosing Notes. For more detailed information, see Notes for Limits.


- c. You can branch to the display mode of the definition of limit types in Customizing by choosing Customizing.


- 3. To change a limit double click the relevant limit. The system displays the screen Overview of Utilizations – Selection Using Direct Characteristics.

Select the relevant limit utilization, and then choose Maintain Limit.

The system displays the screen Edit Limits for Limit Type xxx: Detail.

- 4. Change the limits as required and in the same as you would for creating a limit. To save your changes choose Save.


**Note:**

...with Selection enables you first to restrict the selection to particular characteristic values. In addition, you can use a predefined display filter here.



**Note:**

When you have changed an internal or external limit amount, the system asks you whether the change to the limit amount should apply retrospectively, or whether you want to split the limit.

If the limit amount should apply retrospectively, choose Change. If you want to split the limit, choose Split.

**Displaying Limits**

- 1. You can display a limit by choosing Display.


**Note:**

...with Selection enables you first to restrict the selection to particular characteristic values. In addition, you can use a predefined display filter here.


You can also display limits by using the report Overview of Limits.

- 2. The system displays the screen Display Limits for Limit Types: Overview . Here all the limits are listed that exist for the selected limit type.

- a. You can display the documents for changes made to these limits by choosing Change Documents.


- b. You can enter notes by choosing Notes. For more detailed information see Notes for Limits.
- c. You can branch to the display mode of the definition of limit types in Customizing by choosing Customizing.


- 3. Select the limit you require. Choose Choose Limit. The system displays the screen Display Limits for Limit Type xxx: Detail, where you can view all the details for a limit.


Additional Information

**Note:**

The system contains customer exit EXIT_SAPLTBL_002 for the administration of limits and for the overview of limit utilizations. You use this customer exit to prevent users displaying certain limits or utilizations. You might want to do this for loans to employees, for example. The authorization check is triggered again when the user branches to single record level.

Include LXTBL1F02 contains sample coding. You can find a detailed description of the SAP enhancements in the documentation about the enhancement concept.

###### Editing Interim Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Editing Interim Limits | L6 | trm03 p.157 | loio `0a09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0a09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The interim limit is a temporary increase in the limit, which can be converted into a new limit. Interim limits have their own release and approval procedure that you can use for a simplified organizational process.

You can generate more than one interim limit for a limit. They can have overlapping time periods. You can also assign these interim limits different currencies.

**Prerequisites**

As the interim limit is closely linked to the limit, the processing of interim limits takes place within the limit processing. Only the mass release of interim limits takes place in a different part of the menu (see below). The following prerequisite applies:

The system displays one of the following screens:

Edit Limits for Limit Type xxx: Create New Limit

Edit Limits for Limit Type xxx: Detail

Display Limits for Limit Type xxx: Detail

Report for Mass Release of Interim Limits

**Procedure**

You can edit an interim limit as follows:

Create

Change

Display

Release

Transfer

Creating interim limits

- 1. The system displays one of the following screens:

- a. Edit Limits for Limit Type xxx: Create New Limit
- b. Edit Limits for Limit Type xxx: Detail


- 2. Maintain the following fields in the Interim Limits table:
- 3. Choose to save your entries.


|Start|Date on which the interim limit for a limit becomes valid|
|---|---|
|End|Date on which the interim limit for a limit becomes invalid|
|Internal Limit Amount|Temporary increase of the internal limit|
|External Limit Amount|Temporary increase of the external limit|
|Currency|The currency of the interim limit can be different from the currency of the limit itself, and can be changed at any time.|
|Release Status|Limit not subject to release: The release procedure has not been activated for the limit type. Limit not released: The interim limit has not been released yet. Limit flagged for release: This release status is set automatically after the interim limit has been created if the release procedure is activated. It is the first step in the release procedure, as per the principle of dual control. Limit is released: The interim limit was released, and is therefore effective.|
|Released By|The name of the user who created the limit appears here automatically after the limit has been created.|
|Name|Free entry|



Changing and deleting interim limits

- 1. The system displays the screen Edit Limits for Limit Type xxx: Detail.
- 2. Proceed in the same way as for creating an interim limit.
- 3. To make the changes you require, overwrite the exiting entries. To delete an interim limit, select it and then choose Delete.


- 4. Choose to save your changes.



If the release procedure is active, the release status of the interim limit is set back one step by the change (Flagged). The interim limit needs to be released again.

If the release procedure is not active, the change is active immediately after you have saved the data.

Displaying interim limits

- 1. The system displays the screen Display Limits for Limit Type xxx: Detail.
- 2. You can view the existing entries for the interim limit in the Interim Limits table.


Releasing interim limits

You can release interim limits either individually, or you can use a report to release them all together in a mass release.

**Note:**

You need to use the release procedure for interim limits only if the release procedure is active in Limit Management. Note that you use the release procedure in accordance with the principle of dual control.

Releasing individual interim limits

- 1. Call up the screen Edit Limits for Limit Type xxx: Detail in the same way as for changing interim limits.
- 2. Select the interim limits you want to release.
- 3. Choose Release and to save your entries.


Releasing multiple interim limits (mass release using report TBIR)

- 1. Choose Master Data Limits Release Interim Limits .
- 2. The system displays the selection screen Report for Mass Release of Interim Limits.
- 3. Here you can select your interim limits by entering the following selection criteria:

Limit type (you can enter a range of values)

Valid from date of the limit (you can enter a range of value)

Valid to date of the limit (range of values)

Release status of the interim limit

Interim limits not subject to release (depending on the settings in Customizing)

Interim limits not released

Flagged interim limits

Released interim limits

Last released by

- 4. Start the report with Execute.


- 5. Select the interim limits you want to release.
- 6. Choose Release and to save your entries.



Transferring interim limits

- 1. Call up the maintenance screen Edit Limits for Limit Type xxx: Detail in the same way as for changing interim limits.
- 2. Select your interim limit and choose Transfer (to limit amount). Transferring the interim limit to a new limit represents a permanent increase in the limit. The transfer sets back the release status of the limit.
- 3. The system then displays the dialog box Limit Split: Date. Here you enter the date as of when the new limit with the increased limit amount is valid. The original limit becomes invalid on the day before the date of the split. The validity end date of the new limit is transferred from the old limit.
- 4. Choose to save your entries.


**Note:**

The interim limit must already be released.

###### Processing Limit Transfers

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Processing Limit Transfers | L6 | trm03 p.160 | loio `a309da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a309da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can reduce the free amount of one limit by a fixed amount and for a specified time period to increase the free amount of another limit. Transferring limits enables you to allocate risk capital efficiently.

During their period of validity, limit transfers are included in the overview of utilizations and in the single-transaction check.

By choosing Notes , you are able to create notes and display existing notes in various places when you are processing limits. You define notes in Customizing under Limit Management Note IDs Define Note IDs for Limit Transfers .

**Creating Limit Transfers**

You can create limit transfers in various ways:

From the overview screen of limit maintenance

From the overview screen of utilizations

By copying an existing limit transfer in collective processing (see the documentation about the Collective Processing of Limit Transfers )

From the overview screen of limit maintenance/utilizations, you create limit transfers in the following way:

Select both limits.

Choose Limit Transfer.

The system displays the Create Limit Transfer: Data screen.

Enter a name for the transfer.

Enter the start date and the end date.

Specify the currency, the internal delta, and, if appropriate, the external delta.

Define to which limit the amount is to be added.

Choose Save to save your entries.


**Displaying Limit Transfers**

You can display limit transfers in various ways:

From collective processing

In the maintenance screen for individual limits on the Limit Transfer tab (you can display the information in detail by choosing Display )


By double-clicking the limit amount in the overview of limit utilizations or in limit maintenance


The values are displayed in a dialog box. Note, however, that in this view it is not possible to distinguish between interim limits and limit transfers. To look at them more closely, you need to compare the Interim Limit and Limit Transfer tabs in the individual maintenance of the limit.

**Changing Limit Transfers**

You can change limit transfers in various ways:

In collective processing

By branching to the maintenance screen for individual limits from

the overview screen of limit maintenance (by choosing Choose Limit ) or

the overview screen for utilizations (by choosing Maintain Limit )

To change a limit transfer from the screen for maintaining limits individually, you go to the Limit Transfer tab.

Select the limit transfers you require and choose Change.


The system displays the Change Limit Transfer: Data screen.

Make the changes you require and choose Save to save the data.


**Deleting Limit Transfers**

You can delete limit transfers in various ways:

In the maintenance screen for individual limits on the Limit Transfers tab by choosing Delete.

In collective processing


To be able to create limit transfers, you need authorization object F_T_VTBLL. When you assign authorizations, note that limit transfers are not subject to a release procedure.


The maximum amount that can be transferred is the total amount of the limit and any existing interim limits. The amount of the interim limit can be transferred only for the period in which it is valid. When you create a limit transfer, the system checks this.

###### Collective Processing of Limit Transfers

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Processing Limit Transfers > Collective Processing of Limit Transfers | L7 | trm03 p.162 | loio `530ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/530ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

The collective processing function gives you an overview of all limit transfers and enables you to process transfers centrally. You find this function in the SAP Easy Access menu under ...Master Data Limits Collective Processing of Limit Transfers .

You can enter the following criteria in the initial screen for the collective processing of limit transfers:

Limit type

Limit transfer number

Valid to date

User who created the limit transfer

User who last changed the limit transfer

**Note:**

By choosing in Customizing for TRM under ... Limit Management Define Note IDs Define Note IDs for Limit Transfers .


**Displaying Limit Transfers**

- 1. In the overview, select the limit transfer for which you want to view more detailed information.
- 2. In the application toolbar choose Display.


- 3. The system displays the screen Display Limit Transfer: Data. Here you can see which limits are affected by this limit transfer.


**Creating Limit Transfers**

It is possible to create a limit transfer in collective processing only if a limit transfer already exists for this particular limit. Only existing limit transfers can be copied in collective processing.

- 1. Select the existing limit transfer, which affects the same limits as those for which you want to create an additional limit transfer.
- 2. In the application toolbar choose Copy.


- 3. The system displays the screen Create Limit Transfer: Data
- 4. Enter a name for the transfer and make the required changes.
- 5. Choose Save to save your entries.



Changing Limit Transfers

- 1. In the overview screen, select the limit transfer you want to change.
- 2. In the application toolbar choose Edit.


- 3. The system displays the screen Change Limit Transfer: Data.
- 4. Make the changes you require and choose Save to save the data.


**Deleting Limit Transfers**

Limit transfers that have been deleted still appear in the overview screen. However, they are shown with a deletion flag. Once limit transfers are marked with a deletion flag, they are no longer included in the overview of utilizations or in the single transaction check.

- 1. In the overview screen, select the limit transfer you want to delete.
- 2. In the application toolbar choose Deletion Flag.


- 3. The limit transfer is marked with a deletion flag (X in a red background).
- 4. You do not need to save the data once you have set the deletion flag.


**Caution:**

You cannot display, change or copy any limit transfer marked with a deletion flag. Note, also, that you cannot revoke the deletion flag.

**Note:**

By choosing Limit Transfer Display Changes you can display the change documents.

###### Locking and Unlocking Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Locking and Unlocking Limits | L6 | trm03 p.163 | loio `e409da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e409da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can identify changes to business conditions (such as a worsening credit rating of the partner) by setting a Lock Flag in the limits for utilizations from new transactions.

**Prerequisites**

You can apply the lock when a limit has been created for a limit type. This limit can also be created automatically.

**Procedure**

You can lock and unlock each limit individually. You can also use a report to lock and unlock multiple limit types simultaneously according to their characteristic values.

Locking and Unlocking Individual Limits

You use this procedure to set or remove the lock.

- 1. Choose Master Data Limits Maintain .
- 2. Select the limit type for which you want to lock or unlock the limit. Then choose Change Limits.



- 3. Position your cursor on any line of this characteristic combination and choose Lock/Unlock.


Locking Multiple Limits by Selected Limit Characteristics

- 1. Choose Master Data Limits Lock/Unlock . The system displays the Lock/Unlock Limits According to Limit Characteristics screen.
- 2. The default limit characteristic is the business partner. If you want to add other limit characteristics as lock criteria, choose New Field Selection. On the left side of the screen, the system displays an overview of all limit characteristics. Select the limit characteristics you require and add them by choosing Copy Selected. By choosing Delete Selections, you delete any limit characteristics that have already been selected.



- 3. By choosing Lock, you can lock the limits referred to by the combination of all the limit characteristics you specified. Similarly, choosing Unlock unlocks the limits.


**Result**

If you set the lock, the system shows this in the header row of the locked limit by inserting the symbol . If you choose this symbol, the system displays the following dialog box:

Lock set by user XY, date: dd.mm.yyyy

In the single transaction check, the system displays a message saying that the limit is locked. Setting a lock doesn’t affect how ( ) of an exceeded limit are displayed.


**Note:**

Lock entries on the database (technical locks) aren’t to be confused with the lock flags mentioned above (business locks).

###### Displaying an Overview of Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Displaying an Overview of Limits | L6 | trm03 p.164 | loio `c609da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c609da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use the limits overview to obtain an overview of the limit structure. From the overview, you can branch to the individual utilizations of each limit, display business partner information, and display change documents. You can also branch to the Customizing settings for limit types.

**Prerequisites**

You need to have already created limits (see Editing Limits).

**Procedure**

- 1. Choose Information System Reporting Limits Overview of Limits .

The system displays the Overview of Limits screen.

- 2. Enter the required selection criteria. The various selection criteria are described in the following table:


|Area|Selection Options|
|---|---|
|General Access Options|Limit type|


| |Currency Make sure you specify the currency in which limits are managed in the system.|
|---|---|
|Selection|If you choose Selection of Limits by Key Date, the system selects the limits that have a validity period that includes the specified key date. If you choose Selection of Limits by Validity Interval, you then need to specify the Valid-From and Valid-To dates.|
|Review|Recipient: Recipient of the limit under review. The name of the recipient is stored in limit maintenance. Review Date Display Review Data: Set this indicator if you want the system to display the review data. You need to set this indicator if you want to send the limit for review manually.|
|Selection using limit characteristics|Direct characteristics: Company code, business partner, portfolio, trader, currency, monitoring unit, limit product group Derived characteristics: Characteristics derived from the business partner: Country/region, sector, rating Free characteristics: Free characteristics 01-15. Generated characteristics: Free characteristics that were generated from the active analysis structure in the Market Risk component and transferred to Limit Management.|


**Note:**

You can save the parameters you entered as a variant. To do this, choose Goto Variants Save as Variant . You can call up the saved selections at any time by choosing .

- 3. Choose to start the function.


The system displays the Overview screen, where you can see the list of the limits selected. They are sorted by limit type.

**Result**

You receive the required overview of all the limits for the limit types you selected.

**Note:**

You have various options for formatting the overview of the data. For information about editing these lists, see the documentation on SAP List Viewer.

**Note:**

As an alternative, you can display the overview of limits using SAP Query.

###### Displaying Changes to Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Displaying Changes to Limits | L6 | trm03 p.165 | loio `f808da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f808da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can create one limit per characteristic value combination for each combination of limit characteristics defined in a limit type. You can use a report to display any changes made to limits.

**Procedure**

- 1. Choose ... Information System Reporting Limits Display Changes to Limits. The system displays the Changes to Limits screen.
- 2. Enter the following ranges as selection criteria for the changes to the limits:
- 3. Choose Execute .


|Selection Ranges|What you need to know|
|---|---|
|Limit type| |
|Date|The date describes the point in time for which the change documents are to be displayed.|
|User|The user is the user-name for whom the change documents are to be displayed.|


**Note:**

Make use of the option for saving the parameters you entered as a variant. To do this, choose Goto Variants Save as Variant .You can display and reuse the selection criteria you saved as variant at any time by choosing .



The system displays a list of changes to the limits, sorted by change document objects, and in ascending date order. This list provides you with details about old and new entries for the limits, who changed the limit, the change document, and other information.

**Note:**

Use the Edit Find... function to search in extensive lists for any text you want.

**Result**

The system displays the required list of changes to the limits.

###### Reviewing Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Reviewing Limits | L6 | trm03 p.166 | loio `6a09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6a09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use the review function to forward information about limits to any recipient. You can either specify the timing of the review manually, or you can let the system determine the dates. The same applies for the actual sending of the limit for review.

**Integration**

The review information is sent to the review's office inbox. This means that every user logged on to the system can send and receive information about limits. When the limit reviewer logs on to the SAP system, a dialog box appears informing him or her that

there is an item in his/her inbox.

**Prerequisites**

Before you can use the review function, limit types must already have been defined.

**Procedure**

You can either enter the timing of the review manually, or let the system determine it.

In TRM, choose Master Data Limits Maintain .

The system displays the screen Limits: Choose Limit Types.

Select the limit types you require and choose Change Limits.


Position the cursor on a limit line, and then choose Choose Limit.

The system displays the screen Edit Limits for Limit Type xxx: Detail.

Choose the Administrative Data tab page, and enter the name of the recipient in the Review Recipient field.


A user can also enter him/herself as the recipient.

Determining the timing of the review:


You can store a factory calendar to check the date entry. In this way the system checks for public holidays and weekends in a specific country/region. The factory calendar is stored in Customizing under Limit Management Enter Basic Settings for Limit Management .

Manually: Maintain the Review Date field.

Automatically: Set the Automatic Review indicator.

In order to be able to use the automatic review, you need to have made the following settings in Customizing:

In Customizing, choose Limit Management Define Limit Types .

The system displays the screen Change View "Define Limit Types": Overview.

Select a limit type, and then choose Details to access the detail view. Enter data in the following fields:

Review Period: The period after which a review recipient receives limit information.

Review Deadline Before End of Validity Period: On this date, the limit is presented for the last time before it expires.


The system takes the earlier of the two dates below as the review date:

(Day’s date) + (number of days in the review period)

(End of the validity of the limit) - (number of days of the review deadline before the end of the validity period)

The day's date corresponds in this case to the date on which the limit was created or changed.

**Features**

You can use the following functions:

Displaying the Data Relevant for the Review

Choose Information System Reporting Limits Overview of Limits .

The system displays the screen Overview of Limits.

First enter the general access options required.

Set the Display Review Data indicator.


You can also select the limits by review Recipient or Review Date.

Start the report with Execute. You can see who the review recipient of the limit is, and the date the limit is next due to be reviewed.

Sending Limits for Review

Sending Limits for Review Manually

In the overview of limits (as in point 1. Display the data relevant for the review) choose the limits you wish to send. Choose Execute to start the evaluation.


By choosing Choose Limits you can transfer the relevant limits to a batch of items that are to be sent for review. By positioning your cursor

on the header line (this means all limits for this combination of characteristics)

on the item line (this means just one limit)

or by not positioning it at all, you can copy all the displayed limits to the batch of items that are to be sent for review.

Send the limits by choosing Send List to Specified Review Recipients.

Sending Limits for Review Automatically

To do this, you need to schedule a variant of report RFTBLRSM as batch job, and let the report run daily. The program selects all limits with a certain review date and sends them to the recipients. At the same time, if automatic determination is used, the review date is recalculated.

Change of Personnel

You use this function to select limits by using a selection screen, and then either changing, creating or deleting the recipients.

You access the selection screen by choosing Master Data Limits Change Review Recipient .

You have the following options:

|Change|Old review recipient <name>; new review recipient <name>|
|---|---|
|Create|Old review recipient <space>; new review recipient <name>|
|Delete|Old review recipient <space>; new review recipient <space>|



You can also change a review recipient manually in each limit.

###### Releasing Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Releasing Limits | L6 | trm03 p.169 | loio `7c09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7c09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

A release procedure, which works in accordance with the principle of dual control, can be activated for the creation and changing of limits, and for each limit type.

**Prerequisites**

You need to have set the Release Active indicator in the Customizing for the limit types that you have already created. In Customizing choose Limit Management Define Limit Types.

**Procedure**

You can release limits individually, or collectively by using report TBLR.

Releasing individual limits:

- 1. Choose ... Master Data Limits Edit.
- 2. Select the limit types of the limits that you want to release and choose Change Limits.


- 3. The system displays the current release status of the limit in column Release .
- 4. Two users are required to release a limit (principle of dual control). The first user can create the limit and set the status to Flagged . This is the first release. The release made by the second user actually releases the limit (status is Released ). This is the second release.


|Without release (w/o release)|The limit is not subject to a release procedure (meaning that the release procedure is not set to active in Customizing).|
|---|---|
|Not released|The limit has not yet been released.|
|Flagged|Either one (of the two required) releases has occurred, or the initial status of the release has been set to 1 (limit is flagged for release).|
|Released|Both releases have been made, the limit is released.|


- 5. To release the limit, position your cursor on the line of the limit and choose Choose Limit . In the next screen, choose Limit and save your change with Save , so that the database is updated.



Releasing Multiple Limits (Mass Release)

- 1. Choose ... Master Data Limits Release Limits.
- 2. The system displays the screen Mass Release of Limits .
- 3. In the general selections you can enter just one limit type or a range of limit types.

In the mass release function, you can select limits by release status. You do this by setting the following indicators:

Limits not Released

Limits Flagged for Release

Released Limits

- 4. You can also select limits by specifying the user who last changed the release status.
- 5. When you have started the program, the system selects the limits and displays them in a list. You have to select the limits you want to release.
- 6. Choose Release. The release status is increased by one level, and shown accordingly in the limit.
- 7. Choose Save to save the entries and to update the database.



**Result**

The release status is increased by one level respectively:

Level 1: not released level 2: flagged level 3: released

**Note:**

If the initial value of the release status is 1 (flagged), only one further release is necessary.

The system displays the current release status in the limit. If you click on the release status of a limit, the system displays the user who last changed the release status.

###### Editing Custom Fields

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Limits > Editing Custom Fields | L6 | trm03 p.170 | loio `380ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/380ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use the SAP enhancement LTBLX003 to create and maintain additional fields (known as custom subscreens). In these fields, you can store additional information about the limit.

The enhancement consists of:

Menu enhancement and pushbutton for limit maintenance

Entry for a subscreen to be defined by the customer

- Customer exit 003 for transporting limit fields to the subscreen

- Customer exit 004 for transporting limit fields back from the subscreen


**Prerequisites**

You need knowledge of the SAP Enhancement Concept and of ABAP.

**Procedure**

Entering Custom Fields

- 1. Using transaction SE11, create a structure containing the additional fields you require.
- 2. Using transaction SE11, create an append for table VTBLV (limits) and enter a name for the append in the above structure.
- 3. Using transaction CMOD, create an enhancement project for the SAP enhancement LTBLX003.
- 4. Create your own maintenance screen SAPLXTBL1, no. 9000 for the maintenance of your own fields (in the attributes, select Subscreen).
- 5. Activate your project.


Populating Custom Fields with Data

- 1. In Treasury and Risk Management, choose Master Data Limits Maintain .
- 2. Select your required limit type and choose Change Limits.


- 3. If you have created several individual time-based limits, you access the limit maintenance screen by selecting the respective individual limit and choosing Choose Limit.
- 4. Now select Additional Fields to maintain the fields of the custom subscreen.
- 5. Choose Save to save your limit.



**Note:**

Making entries in these fields resets the release status.

To enable the additional fields to be shown in reporting (limit utilization overview), you first need to unhide them by choosing the ALV function Define Display Variants.

###### Attributable Amount Determination

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination | L5 | trm03 p.171 | loio `f909da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f909da531198434de10000000a174cb4.html?locale=en-US)

The attributable amount is a measure of the default risk that arises when a transaction is concluded. The attributable amount should depict both the expected loss and the unexpected loss arising from a financial transaction. The system determines an attributable amount for every expected incoming cash flow or asset.

The credit risk of a trading transaction exists for the entire term of the transaction, and reflects the counterparty risk from the trading book plus any term-related and risk-related add-on for covering potential positive market value changes. In the case of classic credit transactions, the credit risk is influenced by the committed contract capital and the actual drawings in accordance with their amounts.

The settlement risk only exists at certain points in time during the "life" of the transaction. It exists during the period from the triggering of the advance payment until receipt of the return payment. Whether the settlement takes place via a clearing house or directly also influences the level of settlement risk.

[figure TRM03-F219]

**Use**

Depending on the type of financial transaction, the system determines amounts that quantify the risk involved in the transaction. If a transaction contains more than one risk at one point in time (counterparty credit risk, issuer credit risk, settlement risk), then the system generates several attributable amounts at the same time. At single-transaction level, the unit of measure is the currency in which the transaction was concluded. The system displays totals records in the currency of the company code.

The assignment table provides you with an overview of the possible risk categories for each transaction. In the case of an OTC option (long call) on a stock, for example, the system determines the credit risk of the counterparty of the option and the credit risk of the issuer of the stock. In the case of swaps with principal swaps, in addition to the counterparty credit risk, the system also shows the settlement risk toward the counterparty from the time the advance payment is triggered until receipt of the return payment.

**Prerequisites**

You need to have made the necessary Customizing settings for the determination procedures for all transactions. You need to ensure that for all transactions existing in the system, there is a financial object with the corresponding default risk data and a default risk rule.

**Features**

The system calculates attributable amounts for each transaction type and risk type using a particular combination of determination procedure and default risk rule.

To calculate the attributable amounts, the system accesses formulas that link particular variables (base key figures) containing additional parameters (for example, add-on factors, default probabilities) to the final attributable amounts. The NPV and nominal amount are used as the base key figures for credit risk, and the return payment amount is the usual key figure for settlement risk (depending on whether a clearing house is involved). You can let the SAP system determine the base key figures or you can import them.

**Note:**

To display attributable amounts for settlement risk after the expiry date of the transaction, you need to maintain the validity end date of the transaction in the financial object.

###### Exposure versus the Attributable Amount

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Exposure versus the Attributable Amount | L6 | trm03 p.173 | loio `5209da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5209da531198434de10000000a174cb4.html?locale=en-US)

Exposure basically refers to the amount subject to default risk. No further analysis takes place. Hence the exposure corresponds to the credit equivalent amount. The system can determine the attributable amount on the basis of the exposure. The attributable amount shows how high the risk is that arises from the transaction. If default was a certainty, then the exact amount of the exposure could be taken as the attributable amount (volume-oriented attributable amount). In reality, default is subject to certain laws of probability. These uncertainties are therefore reflected in the calculation of attributable amount by taking into account default quotas and repayment quotas, for example. This results in risk-oriented attributable amounts.

Depending upon the nature of the transaction itself, the system differentiates between the terms primary and secondary exposure, and primary and secondary attributable amounts. The primary transaction is the original transaction with the business partner. Secondary transactions are made only in the context of a particular primary transaction. Examples include collateral and facilities.

Depending on whether the risk-reducing effects of collateral are considered, a distinction can be made between net and gross for all concepts. Gross shows the maximum possible amount per partial transaction. For example, the net attributable amount of a transaction results from the gross attributable amount of the transaction minus the attributable amounts for the collateral that can be allocated to the transaction.

The system calculates attributable amounts for each individual transaction, irrespective of whether it is a primary or secondary transaction. Utilizations, or drawn amounts, are referred to at the level of the limits, which are defined by characteristics.

###### Setting Up Formulas

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Setting Up Formulas | L6 | trm03 p.173 | loio `1809da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1809da531198434de10000000a174cb4.html?locale=en-US)

**Use**

In Customizing, you set up formulas for each combination of determination procedure and default risk rule. These formulas are then used in the calculation of attributable amounts.

To enable the system to calculate both volume-based and risk-based attributable amounts, the final formulas consist of variables, formula IDs, and calculation bases.

[figure TRM03-F220]

**Prerequisites**

- 1. In Customizing under Attributable Amount Determination Define Variable Assignment ID , you can store any number of combinations of four variables. You can use the following basic key figures as values for these four variables. Either the basic key figures are calculated by the system or you can import them:

Net present value

Nominal amount

Return payment amount

Advance payment amount

Net present value based on external commitment

Nominal amount based on external commitment

Book value in transaction currency (you have to import this)

Or other external key figures

- 2. You assign a combination of formula ID, calculation base, and variable ID to each combination of determination procedure and default risk rule. The formula IDs and calculation bases are predefined in the system and are in turn based on the assignment of the variables. This enables you to depict any number of formulas.


In addition to the four variables, the following abbreviations are used in the formula IDs and calculation bases:

BBAS: Calculation base

AWKT: Default probability

ABS: Absolute amount

RR: Recovery rate

Aof Add-On Factor

**Features**

The system uses the formulas defined, the determination procedure, and the default risk rule to calculate attributable amounts for each transaction.

The following overviews show how the system uses the settings (formulas and calculation bases) in the determination procedure to meet the requirements for calculating counterparty/issuer risk.

|Formulas|Counterparty Risk|
|---|---|
|Max(0,BBAS)|Yes|
|Max(0,BBAS) * AWKT|Yes|
|ABS(BBAS)|Yes|
|MAX(0,BBAS) * (1 - RR)|Yes|
|MAX(0,BBAS) * WF|Yes, settlement risk|
|BBAS|Yes|
|MAX(0,BBAS) * AWKT * (1 - RR)|Yes|
|External formula (for user exit only)| |


|BBAS|Counterparty Risk|
|---|---|
|Var1|Yes|
|Max(0, Var1) + Var2 * Aof|Yes|
|Var1 * Aof|Yes|
|Var3 - Var4|Yes, settlement risk|
|Var3 - Var4 + Var2 * Aof|Yes, settlement risk|


Negative Attributable Amounts

If you use the formula ID 013 BBAS, negative attributable amounts are also permitted.

If you opt for this formula ID, the calculation base applied is "BBAS = attributable amount". Consequently, when the calculation base is negative, the attributable amount is also negative, thereby decreasing the limit utilization.

If you use a user exit to select the formula ID 999 External Formula and you set the Negative Attributable Amounts Allowed for User Exit indicator, negative attributable amounts from the user exit are also permitted.

If, for netting groups, you choose the formula ID 013 BBAS or the formula ID 999 External Formula with the Negative Attributable Amounts Allowed for User Exit indicator selected, negative attributable amounts are also permitted for netting groups.

###### Basic Key Figures Calculated by the SAP System

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Setting Up Formulas > Basic Key Figures Calculated by the SAP System | L7 | trm03 p.175 | loio `1b09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b09da531198434de10000000a174cb4.html?locale=en-US)

The system calculates the NPV of a transaction in the following way:

|Transaction Form|Net Present Value|
|---|---|
|Loans, money market transactions|Net present value of incoming cash flows|


|Transaction Form|Net Present Value|
|---|---|
|Generic transactions|Net present value according to the selected transaction|
|All other transactions|Current net present value|


The system calculates the nominal amount of a transaction in the following way:

|Transaction Form|Nominal Amount|
|---|---|
|Stocks|Net present value of the stock item|
|Index-based transactions|Value of the index item|
|Forward exchange transactions|Nominal amount of incoming cash flows in transaction currency|
|Interest rate instruments, loans|The amount outstanding on the evaluation date|
|Swaps with principal swap|Amount of the highest occurring nominal amount after the evaluation date in transaction currency|
|Swaps without principal swap|Current, decisive nominal amount of the swap|
|FRA|Nominal volume|
|Caps/floors|Nominal volumes of the current caplets/floorlets|
|Stock options|Net present value of the stock item|
|Index options|Value of the index item|
|Options on forward exchange transactions|Nominal amount of incoming cash flows in transaction currency|
|Options on interest rate instruments|Nominal amount of the interest rate instruments|
|Options on swaps|Current nominal amount of the swap|
|Warrants|Same as for options (subscription ratio is also taken into account)|
|Generic transactions|Net present value according to the selected transaction|


The system calculates the advance payment amount of a transaction in the following way:

|Transaction Form|Advance Payment Amount|
|---|---|
|Foreign exchange spot and forward transactions|Nominal amount of outgoing cash flows in transaction currency|
|Securities forward transactions|Purchases – agreed purchase price, sales – NPV of the security item that is to be delivered|
|Swaps|The amount of the outgoing cash flow due after the current evaluation date|


The system calculates the return payment amount of a transaction in the following way:

|Transaction Form|Return Payment Amount|
|---|---|
|Foreign exchange spot and forward transactions|Nominal amount of incoming cash flows in transaction currency|


|Transaction Form|Return Payment Amount|
|---|---|
|Securities forward transactions|Sales – agreed purchase price, purchases – NPV of the security item that is to be delivered|
|Swaps|The amount of the incoming cash flow due after the current evaluation date|
|Money market transactions|Nominal amount + last incoming cash flow|
|Loans|Nominal amount|


The net present value and the nominal amount based on the external commitments of a transaction are calculated as follows:

|Transaction Form|Net Present Value and Nominal Amount Based on External Commitment|
|---|---|
|Loans|Commitment capital|
|BCA accounts|External commitment|


**Caution:**

This setting cannot be used for any other transactions.

If you set the Max. Commitment/Utilization indicator when you define the variable assignment ID, you can have even greater control over how basic key figures are assigned for loans, variable transactions, and BCA accounts. This function is effective only if you use the basic key figures Net Present Value (0001), Nominal Amount (0002), Net Present Value Based on External Commitment (0005), or Nominal Amount Based on External Commitment (0006) in the variable assignment.

If you do not set the indicator, then the system calculates basic key figures as follows:

|Key Figure|Loan|BCA Account|
|---|---|---|
|0001 NPV|NPV of incoming cash flows|Current balance|
|0002 Nominal amount|Residual capital|Current balance|
|0005 NPV based on external commitment|External commitment|External account limit|
|0006 Nominal amount based on external commitment|Commitment capital|External account limit|


If you have set the indicator, then the system calculates the maximum amount of the key figures Net Present Value and Net Present Value Based on the External Commitment or of the key figures Nominal Amount and Nominal Amount Based on the External Commitment.

**Example:**

- Variable 1: Net present value

- Variable 2: Nominal amount


The Max. Commitment/Utilization indicator is set.

If this setting is made, then the system checks the following for loans and BCA accounts:

- Variable 1: Maximum of variable Net Present Value (0001) and Net Present Value Based on the External Commitment

- (0005)

Variable 2: Maximum of variable Nominal Amount (0002) and Nominal Amount based on External Commitment

- (0006).

###### Add-On

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Add-On | L6 | trm03 p.178 | loio `dd08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dd08da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The add-on is a risk markup that takes into account the default risk arising from transactions, the market value of which can increase over a particular period. The add-on is calculated by multiplying the assessment basis by an add-on factor. You define the add-on factor in Customizing under Attributable Amount Determination Edit Add-on Factors and entering the add-on factor as a percentage rate depending on the risk sensitivity and the market value change period.

****Example:****

| | |Risk Sensitivity| | | | |
|---|---|---|---|---|---|---|
|Function Add-On Factor| |Interest-related transactions|Interest and currency-related transactions|Currencyrelated transactions|Stock and currency-related transactions|Stock-pricerelated transactions|
|Market Value Change Period|Up to 1 year|0,0%|1,0%|1,0%|6,0%|6,0%|
| |Over 1 to 5 years|0,5%|5,0%|5,0%|8,0%|8,0%|
| |Over 5 to 10 years|1,5%|7,5%|7,5%|10,0%|10,0%|
| |Over 10 Years|2,5%|10,0%|10,0%|12,0%|12,0%|


**Structure**

Risk factors, such as interest rate risk, exchange rate risk, stock price risk, are assigned to individual transactions by means of the risk sensitivity.

The market value change period describes the period of time that is significant for valuing trading transactions when determining potential market value changes. In Customizing, you store how the market value change period is to be determined in the definition of the default risk rule. You can use the data from the transaction or fixed values in the calculation basis. The following values are available for the determination of the market value change period:

End of the term of the transaction

The end of the term of the underlying is used in the case of options whose underlying has a definite term (for example, bonds, FRAs, swaps). In the case of options on indexes, shares and foreign exchange, the term is calculated from the end of term of the option.

Interest commitment

Capital commitment

If the calculation basis is to use fixed values, then you must also specify the market value change period in months.

If the market value change period is not relevant, then select the value to be ignored.

**Integration**

The system can find the respective add-on factor for a single transaction in the way described in the table above. This is because the risk sensitivity is assigned to the default risk rule in Customizing (under Basic Settings Assignments Assignments to Default Risk Rule Assign Risk Sensitivities ; or under Basic Settings Assignments Assign Risk Sensitivities ) and the market value change period is determined by means of the default risk rule.

###### Probability of Default

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Probability of Default | L6 | trm03 p.179 | loio `e008da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e008da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The default probability is a percentage rate that specifies the probability of a loss on receivables in a given time period.

**Integration**

The default probability is stored in Customizing under Attributable Amount Determination Edit Counterparty Default Probabilities or Edit Country/Region Default Probability. It is stored as a percentage depending on the rating of the business partner stored in the business partner master data (or from the financial object) and the risk commitment period. Additionally, you can adapt the default probability by assigning different valuation factors for different valuation procedures (for example, internal procedure, German Banking Act procedure).

**Example:**

| | |Risk Commitment Period| | | |
|---|---|---|---|---|---|
|Probability of Default| |Up to 1 year|Over 1 year to 5 years|Over 5 years to 10 years|Over 10 years|
|Rating|AAA|0.02%|0.05%|0.1%|0.2%|
| |AA|0.05%|0.15%|0.3%|0.5%|
| |BBB|0.15%|0.3%|0.6%|1.0%|
| |BB|0.3%|0.6%|1.0%|2.0%|

###### Risk Commitment Period

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Probability of Default > Risk Commitment Period | L7 | trm03 p.179 | loio `2709da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2709da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The risk commitment period describes the period during which termination of the commitment is not possible, or possible only with extreme difficulty. You can generate risk cost-term grids by defining default risk probabilities that are based on the risk commitment period. This reflects the fact that in reality the default risk increases with the length of the term of the transaction.

**Use**

In Customizing: Basic Settings Definitions Define Default Risk Rule you define how the system is to calculate the risk commitment period. You can use dates from the transaction or fixed values in the calculation basis. The following values can be


used to calculate the risk commitment period:

End of the term of the transaction

**Note:**

For FRAs, the day of settlement is chosen as the end of the term.

Interest commitment

Capital commitment

Fixed values (the value of the risk commitment period is entered in months)

Ignore.

###### Interpolation of the Default Probability

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Probability of Default > Interpolation of the Default Probability | L7 | trm03 p.180 | loio `5b09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5b09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Basically, the value of the stored risk commitment period nearest to the one that is to be determined is taken as the default probability. If no larger risk commitment period exists, then the system takes the next smallest value. To use a more exact default probability value for determining the attributable amount, you can allow the system to calculate the default probability by linear interpolation between two risk commitment values.

**Prerequisites**

To be able to carry out interpolation you need to have made the following settings in Customizing: In Basic Settings

Definitions Define Determination Procedures , you need to have set the interpolation of default probability indicator. Interpolation of the default probability is only meaningful if formulas that take the default probabilities into account are assigned to the determination procedure.

**Features**

The system performs interpolation if the determined risk commitment period falls between two values. This gives an accuracy of 1/30 month to four decimal places. If there is only one value, precisely this monthly value applies for the determination of the default probability.

Example

[figure TRM03-F222 - Interpolation of the Default Probability]

Interpolation of the Default Probability

###### Recovery Rates

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Recovery Rates | L6 | trm03 p.181 | loio `7309da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7309da531198434de10000000a174cb4.html?locale=en-US)

The recovery rate is an estimate in percentage for the part of a receivable for which there is no collateral but which can still be recovered in the event of a default. This part of the assets of the bankrupt, which can be used to cover the receivables, reduces the attributable amount.

**Prerequisites**

- 1. In Customizing under Attributable Amount Determination Edit Determination-Procedure-Specific Settings , you have to assign formulas, which take recovery rates into account, to the respective combination of determination procedure and default risk rule.
- 2. In Customizing under Basic Settings Definitions Define Recovery Rate Class , you need to have created a recovery rate class.
- 3. In Customizing under Attributable Amount Determination Edit Recovery Rates , you need to have stored the relevant percentages.


**Note:**

It is helpful to the user if you choose descriptions that allow the percentage rate of the recovery rate to be inferred (for example, R0010 for 10%).

You do so for each valuation factor determination, recovery rate class, and date.

**Features**

The system calculates the relevant recovery rate on the basis of the financial object. You need to have either stored a recovery rate class in the financial object or assigned a default risk rule by means of which the system can then find a default recovery rate. You define how the system uses the default risk rule to determine the recovery rate class. You do this in Customizing under Basic Settings Definitions Define Default Risk Rule .

No default setting ⇒ You need to store the recovery rate directly in the financial object.

From default risk rule ⇒ The default recovery rate is also stored in the Recovery Rate Class field.

From valuation factor determination ⇒ The system checks the recovery rate basis stored in Customizing under Basic Settings Definitions Define Valuation Factor Determination .

If the business partner rating is defined as the recovery rate basis, then the system calculates the recovery rate using the rating of the business partner. The rating is either determined from the business partner master data or entered in the financial object of an individual transaction. If it is entered in the financial object, then this value overrides the rating from the business partner data.

You assign the rating to the recovery rate class in Customizing under Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Basic Settings Assignments Assignments to Recovery Rate Assign Credit Rating .

**Note:**

If no recovery rates are defined in the system, even though they are required for attributable amount determination, the recovery rate is set to 0.

###### Attributable Amount Calculation Based on Credit Value Adjustments

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Attributable Amount Calculation Based on Credit Value Adjustments | L6 | trm03 p.182 | loio `15e284a8a4244403bfcce3901d4763a8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/15e284a8a4244403bfcce3901d4763a8.html?locale=en-US)

The calculation of the attributable amount can be based on credit value adjustments.

**Definition**

You can use credit value adjustments (CVAs) as a key figure category within the attributable amount calculation in Limit Management for financial transactions (OTC) and bank accounts. A credit value adjustment (CVA) is the amount by which the riskfree NPV of a financial transaction or bank account is adjusted to reflect the probability of a default by a business partner. CVA is a positive amount.

SAP recommends using the CVA calculation method based on expected exposures, which considers loss given default and default probability derived from credit spreads. The CVA values based on expected exposures are calculated using the following equations:

[figure TRM03-F223 - Where]

Where

LGD = loss given default

D = discount factor

t = time

EPE = expected positive exposure

PD = probability of default of counterparty

C

EPE and CVA are positive

The calculation of credit value adjustments requires the credit spread curve for the reference entity of the counterparty to obtain the product PD*LGD.

If credit spreads (CS) represent a fraction of the insured nominal N that is to be paid each year to hedge against a default, you can set the premium paid for t years of hedging equal to the probability of default over time t, multiplied by the amount lost in the event of a default:

CS * N * t =PD (O,t) * LGD * N

For cumulative probabilities, we have

PD (t ,t) = PD (0, t) - PD (0, t )

i-1 i i I-1

Using both equations together, the products PD*LGD needed in the CVA equation can be calculated from credit spreads as follows:

LGD * PD (t , t) = CS (t)*(t - t ) - CS (t )*(t - t )

i-1 i i i 0 i-1 i-1 0

Where CS (0, t) is the t year point on the credit spread curve valid at time 0.

**Use**

The End-of-Day Processing app executes the credit value adjustment calculations.

The selected account balances are cash flows on the horizon date.

You can use an expected exposure type with add-on factors for both financial transactions (OTC) and bank accounts, but the add-on factor isn’t applied for the bank accounts.

In the Review Limit Utilizations app, the credit value adjustment calculation log is available.

**Limitation**

This function is only available for financial transactions (OTC) and bank accounts.

The add-on factors of CVA calculation aren’t supported for bank accounts.

This functional isn’t available for netting groups.

This function isn’t available during the Single Transaction Check.

**Prerequisites**

Make the relevant settings for the CVA calculation based on expected exposures and define a CVA/DVA type.

For more information, see also Credit and Debit Value Adjustments

**Note:**

In Customizing for Treasury and Risk Management under Basic Analyzer Settings Valuation Settings for the Calculation of Credit and Debit Value Adjustments Define Expected Exposure Types , you can define the exposure duration / term in days for bank accounts, since financial objects for bank accounts don't have an end of term as financial transactions. Bank accounts have a current balance. The point in time when the expected exposure drops to 0 from a CVA point of view needs to be specified. If you don’t specify the duration, the system uses 1 day as the default.

If you set the Ignore Netting Groups indicator, financial objects that are assigned to netting groups can also be processed individually.

In Customizing for the Credit Risk Analyzer under Basis Settings Global Settings , you must assign the CVA/DVA type for the attributable amount determination.

In Customizing for the Basis Analyzer Settings under Valuation Define and Set up Evaluation Types , you must enter the derivation IDs to determine the credit spread curves to be applied in the evaluation type relevant for the Credit Risk Analyzer (also assigned in the Global Settings activity).

In Customizing forthe Credit Risk Analyzer under Attributable Amount Determination Define Variable Assignment ID

, you must define a variable with the key figure category 0018 Credit Value Adjustments.


In the Customizing of the Credit Risk Analyzer under Attributable Amount Determination Edit Settings for Determination Procedures , you must define a determination procedure based on the variable assignment ID.

In Customizing for the Credit Risk Analyzer under Limit Management Define Limit Types , you must define a limit type using the determination procedure.

###### Netting (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Netting | L6 | trm03 p.184 | loio `1a0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1a0ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

If netting agreements exist between two business partners, then if it is legally permissible (for example, the German Banking Act I §12) payments and receivables between partners can be netted off. This has the effect of reducing the counterparty risk of a bank's transactions with a particular counterparty.

In the Default Risk and Limit component, netting refers to bilateral liquidation netting, which means an agreement is made with the contract partner that in the case of the termination of the entire contract (in the case of bankruptcy, for example) all mutual claims and receivables are terminated, fall due, are valued at market conditions, and the resulting balance is calculated (balancing by netting). This has the effect of reducing the attributable amount for the credit risk. Settlement risk is unaffected.

**Prerequisites**

- 1. The determination procedure must permit netting.


When you define the determination procedure in Customizing for the Credit Risk Analyzer under Basic Settings Definitions Define Determination Procedures , you need to set the Netting Active indicator.

In addition, you need to make an entry in the Add-On Weighting field. The weighting factor shows to what extent the total add-on affects the calculation of the netting add-on. The total add-on is derived from the total of all open transactions that can be netted, and that involve the same counterparty.

In the Attr.Amnt.Calc.Meth field, you specify which NPV total is used as the basis for calculating the calculation base of the netting group.

The system calculates the following totals for the netting group:

Total NPV (Netting Transactions)

This is the total of all calculation bases calculated (in accordance with the settings of the determination procedure) for the individual transactions of the netting group.

Total NPV (Netting Transactions with Positive NPV)

This is the total of all positive calculation bases calculated (in accordance with the settings of the determination procedure) for the individual transactions of the netting group.

Total NPV (Netting Transactions with Negative NPV)

This is the total of all negative calculation bases calculated (in accordance with the settings of the determination procedure) for the individual transactions of the netting group.

You can use the calculation method to specify which of these values is used for the calculation base of the netting group:

0Positive and Negative Key Figures

All key figures are relevant for the calculation base of the netting group [-> calculation base of the netting group = Total NPV (Netting Transactions) + add-on netting group]

- 1Only Positive Key Figures

In this case, only the positive key figures are relevant for the calculation base of the netting group [-> calculation base of the netting group = Total NPV (Netting Transactions with Positive NPV) + add-on netting group]

- 2Only Negative Key Figures


In this case, only the negative key figures are relevant for the calculation base of the netting group [-> calculation base of the netting group = Total NPV (Netting Transactions with Negative NPV) + add-on netting group]

Using the calculation base BBAS of the netting group, the system calculates the attributable amount of the netting group.

- 2. Definition of a Netting Group

In Customizing for the Credit Risk Analyzer under Basic Settings Definitions Define Netting Group , you define your netting groups. The netting group defines which business partner is used to balance the transactions.

When you define the netting group, you also store the default risk rule, which the system uses to calculate the netting attributable amount. Any transactions in the netting group that are in a different currency are converted to the currency of the netting group, and then netted.

- 3. The financial object of the transactions that are to be netted contains either the netting ID or the collateral ID. This is stored in the data for the default risk limit part in the data group Transaction Assignment.


The system permits a two-level netting procedure. Within a netting group, collateral can be provided in the form of a collateral agreement. hen you create collateral agreements, you need to assign them to the relevant netting group.

**Features**

If netting is active, the system calculates the attributable amount as follows:

- 1. Determination of all open (still valid, not yet due) single transactions concluded with the business partner in a certain company code.
- 2. From the selected open transactions, the system then finds all the transactions that are assigned to one netting group (can be netted), and all unassigned (cannot be netted) transactions.


It calculates the attributable amount for all transactions that cannot be netted. The total of the attributable amounts of these single transactions is calculated and then displayed.

For the transactions that can be netted, the system finds all the single transactions that belong to a netting group. The following figures are calculated for the transactions of this netting group:

Total of all NPVs (total (net present values))

Total of all positive NPVs (total (net present values_pos))

Total of all negative NPVs (total (net present values_neg))

Total of all add-ons (total (add-ons))

Net/gross ratio (NGR)

NGR = max (0, total (NPV) / total (NPV_pos)) if the total of the NPVs (pos) is equal to or greater than zero; otherwise zero.

Add-on netting

Add-on = total (add-on) (a + b NGR); where b = 1 - a

Netting single transaction

- a = weighting factor for the entire add-on
- b = weighting factor for the net/gross ratio (NGR)


Average probability factor

In Customizing, you have defined in the calculation method which of the totals determined for the netting group is applied, via the NPVs, in the calculation base for determining the attributable amount.

###### Calculating Attributable Amounts for Netting Groups

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > Netting > Calculating Attributable Amounts for Netting Groups | L7 | trm03 p.186 | loio `cb08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cb08da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this report (transaction RKLNT) to calculate attributable amounts for netting groups without having to run end-of-day processing. This evaluation also generates detailed logs of the calculation of the attributable amount.

**Procedure**

- 1. Choose Information System Reporting Counterparty Risk of Netting Group .

The Counterparty Risk of Netting Group appears.

- 2. Enter the selection criteria that you require. These include:

Netting group

Determination procedure (must be relevant for netting)

Valuation date

- 3. To start the attributable amount determination for the netting groups, choose .


**Result**

An overview list appears. On this screen, you see the netting attributable amount for each netting group and determination procedure that you have selected, together with additional data that was required for calculating the attributable amount (for example, the netting add-on, net/gross ratio, total of the NPVs, or the average default probability).

By choosing Group Details, or by double-clicking a row, you can display the detail log for each netting group and each determination procedure The detail log contains additional data about the transactions assigned to the respective netting group. This data is displayed in several blocks, which are sorted by the type of attribution.

Key figures before the inclusion of collateral

All the transactions in the netting group are listed.

Key figures after inclusion of single transaction-related collateral for netting transactions

This block contains all the transaction data that results from the inclusion of the single-transaction-related collateral. The single-transaction-related collateral first reduces the positive net present value, and then the add-on.

Key figures after inclusion of collateral agreements

If the transactions in this netting group have also been assigned to a collateral agreement, they are listed in this section along with the collateral agreement data.

Key figures for the collateral agreements of the netting group

Results for the netting group

The results contain the individual results required for the calculation of the netting attributable amount.

The detail log also contains the following functions:

|Pushbutton|Function|
|---|---|
||The system displays the screen showing the transaction master data.|
||The log showing the cash flow discounting is displayed.|
||This takes you to the transaction in which collateral agreements are displayed.|
||The system displays information about how the attributable amounts for the collateral agreement were calculated.|

###### User Exit for Attributable Amount Determination

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Attributable Amount Determination > User Exit for Attributable Amount Determination | L6 | trm03 p.187 | loio `e109da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e109da531198434de10000000a174cb4.html?locale=en-US)

**Use**

To achieve greater flexibility in the area of attributable amount determination, you have the option of defining your own calculation procedure for the determination of the attributable amount for single transactions as well as for netting groups.

**Prerequisite**

In Customizing for the Credit Risk Analyzer under Attributable Amount Determination Edit Determination Procedure Settings , you need to have entered the formula ID 999.

If you want to allow negative attributable amounts for the user exit, set the Negative Attributable Amounts Allowed for User Exit indicator.

**Activities**

Create a project as per the enhancement concept and activate it. For this, you need the following enhancement: FKLR0001. For more information, see the documentation for the function module EXIT_SAPLKLEX_001.

You need knowledge of the enhancement concept.

###### Updating Limit Utilizations

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations | L5 | trm03 p.188 | loio `f508da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f508da531198434de10000000a174cb4.html?locale=en-US)

Limit utilization of a single record or transaction is the risk amount calculated for a single transaction by the attributable amount determination function.

Using the limit characteristics and their values, the system combines the utilizations of the single records with the limit utilizations of the totals records or the limit.

The limit utilization of a certain limit is, therefore, the total of the attributable amounts of all transactions attributed to the limit on the basis of their characteristic values. The system compares this amount with the corresponding internal or external limit amount as part of the single transaction check.

Use

Up-to-the-minute monitoring of compliance with the existing limits requires all limit utilizations to be updated regularly. For this purpose, you can use the single transaction check to update limits during the day, and make a final update at the end of the day by using end-of-day processing .

[figure TRM03-F229 - When the single transaction check is applied to a transaction, the system updates it in Limit Management with status 2. If an additional STC is applied to this transaction on the same day, then status 2 is updated with the current data. If a transaction is included in end-of-day processing, the system updates it in Limit Management with statuses 1 and 2.]

When the single transaction check is applied to a transaction, the system updates it in Limit Management with status 2. If an additional STC is applied to this transaction on the same day, then status 2 is updated with the current data. If a transaction is included in end-of-day processing, the system updates it in Limit Management with statuses 1 and 2.

Which key figures are determined and updated depends on the combination of the default risk rule and the determination procedure. The default risk rule is stored in the financial object. For external transactions, the default risk rule is determined by the STC product.

###### Single Transaction Check

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check | L6 | trm03 p.188 | loio `bb09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bb09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The term single transaction check (STC) refers to all check activities relating to the relevant limits that can be applied to a single trading or credit transaction when you enter or edit it. You can trigger the single transaction check in the following ways:

By using the integrated default risk limit check (for more information, see also integrated default risk limit check)

By using an RFC module

The relevant attributable amounts are determined for the data supplied and for all the risk categories that are released for a single transaction check. The system checks the maximum risk commitment period that was defined, the internal and external limits, and the critical limit utilization.

The single transaction check is a tool you can use for up-to-date risk monitoring. This is controlled by determination procedures.

Depending on the settings in Customizing, you can activate 24-hour capability for the single transaction check. This means that you can trigger the single transaction check at any time, even when end-of-day processing is running.

**Prerequisites**

If you want the system to determine the current limit usage for the individual limits, you need to enter Update Category 2 in the limit type definition. The update category of a limit type specifies whether limit utilization is updated during the day. In Customizing, choose Limit Management Define Limit Types .

You also need an STC product, which you define in Customizing under Basic Settings Definitions Define Single Transaction Check Product .

The results of the single transaction check are valid only if the utilization of the limits was calculated in an end-of-day processing run, the key date of which is in the past. The limits referred to here are the ones affected by the limit characteristics of the transaction that is to be checked.

For you to be able to use all the functions of the single transaction check, authorization profile F_T_FTLM_ALL with authorization object J_B_KLSDC1 must be stored in your user master record. Depending on the extent of your authorization, you can obtain further information by branching from the functions of the STC.

**Features**

You have the following options for triggering the single transaction check:

Manually in the application menu

Checking new transactions

Checking existing transactions

Deactivating external transactions

Displaying an overview of transactions

Automatically by using the RFC module KL_EXT_CALCULATE_AROBJ_RFC

Using this interface, you can create a direct connection between your own front-end system and the limit system. Refer to the technical documentation on the function module in the ABAP Workbench.

When you enter or edit transactions in an external system (upstream with regard to Limit Management), the single transaction check involves the following steps:

Call-up of the interface for the single transaction check

Determination of the limits relevant for the single transaction check

Calculation of the attributable amounts of the transaction

Calculation of the current limit utilizations of the limits relevant for the check

Check for compliance with the limits

Reporting of the results of the check to the user processing the transaction

Generation of a log of the results of the check for the documentation in Limit Management

Updating of limit utilizations

[figure TRM03-F230 - Updating of limit utilizations]

In addition to updating limit utilizations, you have the option of just checking a transaction. During the check, the system determines an attributable amount. This is checked against the limits, and the result is reported back to the user. The limit utilization is not updated.

**Integration**

All transactions that are created in the SAP system by means of the single transaction check are initially recognized by the system only as external transactions. The external transaction remains in Limit Management even after the end-of-day processing run.

**Activities**

During the single transaction check, the system checks the transactions. This means that the system needs to be provided with all limit-relevant data. You have to supply the following data:

|Indicator for simulation|Indicator showing whether a simulated (check) or valid (save) transaction is involved.|
|---|---|
|External administration key|This identifies the transaction.|
|Limit characteristics| |
|Base date for the calculation of the market value change period| |


|Base date for the calculation of the risk commitment period | |
|---|---|
|Default risk rule| |
|Calendar ID| |
|Basic key figures| |
|Validity date|Date on which the data specific to the transaction and to attribution becomes valid|


**Note:**

Counterparty risks and issuer risks can be calculated for individual transactions, such as stock options. If both risks are to be taken into account in the single transaction check, you need to enter the key of the position concerned.

###### 24-Hour Capability of the Single Transaction Check

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > 24-Hour Capability of the Single Transaction Check | L7 | trm03 p.191 | loio `ef08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ef08da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The purpose of the 24-hour capability is to enable you to carry out a single transaction check (STC) at any time, and in particular when end-of-day processing is running. This also affects the integrated default risk limit check, which is available in TRM Credit Risk Analyzer only. Furthermore, the 24-hour capability enables you to enter reservations at any time.

**Caution:**

If you use the non-integrated single transaction check in conjunction with the 24-hour capability, the results are consistent only for new transactions and external transactions. Note that changes to data pool transactions can be taken into account only if the transactions are first changed using EDT, and are then additionally changed using the single transaction check. The single transaction check is required in this case for triggering the post-run update.

**Use**

You activate the 24-hour capability in Customizing by choosing: Limit Management Enter Basic Settings for Limit Management . In addition to activating 24-hour capability, you make other settings here for the single transaction check:

Waiting time for the single transaction check

Posting deadline

Waiting time for the post-run update

Setting the indicator for 24-hour capability

When using the single transaction check, it may sometimes be the case that the limit you are checking is blocked by another user. For this reason, you have to enter a maximum waiting time in the basic settings. As part of the 24-hour capability, by entering a posting deadline you are able to specify a fixed point in time after which risk amounts are to be attributed to the following day. The waiting time for the post-run update specifies the time gap between the post-run update and the posting deadline.

**Structure**

End-of-day processing comprises the generation of utilizations and the post-run update. (As the post-run update is part of end-ofday processing, updating takes place in status 1 and 2.) All the transactions for the day, which were checked by the single

transaction check during the generation of utilizations, are updated in the post-run update. In this way, it is possible to apply the single transaction check even during the end-of-day processing run.

If a single transaction check function is started before the end-of-day processing run has finished, the transactions checked by the single transaction check function are updated to the date of the previous end-of-day processing run. The current end-of-day processing run then updates these transactions to the new date.

[figure TRM03-F231 - If a single transaction check function is started before the end-of-day processing run has finished, the transactions checked by the single transaction check function are updated to the date of the previous end-of-day processing run. The current end-of-day processing run then updates these transactions to the new date.]

**Exception**

When you enter the settings in Customizing, ensure that there is sufficient time between the end of the generation of utilizations and the posting deadline to allow for the post-run update. If this is not the case, it can cause the post-run update to exceed the posting deadline. In this case, the single transaction check is locked for the period of time between the posting deadline and the final completion of the end-of-day processing run.

[figure TRM03-F232 - When you enter the settings in Customizing, ensure that there is sufficient time between the end of the generation of utilizations and the posting deadline to allow for the post-run update. If this is not the case, it can cause the post-run update to exceed the posting deadline. In this case, the single transaction check is locked for the period of time between the posting deadline and the final completion of the end-of-day processing run.]

**Note:**

To avoid this, in Customizing you can leave the field for the posting deadline blank.

###### External Transactions

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > External Transactions | L7 | trm03 p.193 | loio `3b0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b0ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

External transactions represent financial transactions that are not (yet) available in Treasury and Risk Management.

**Structure**

All basic key figures and limit characteristics must be provided for these transactions. These can be imported from your own frontend system by means of the RFC interface, or you can use the function for starting the single transaction check manually in the application. In Treasury and Risk Management (TRM), you can use the integrated limit check.

**Integration**

In the Default Risk and Limit System, you can calculate attributable amounts for these transactions and update the limit utilizations using the limit characteristics.

###### STC Product

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > STC Product | L7 | trm03 p.193 | loio `f309da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f309da531198434de10000000a174cb4.html?locale=en-US)

Definition

The STC product is the central control element for the single transaction check transaction (STC transaction). The following functions of the STC transaction are affected by the Customizing settings you make for the STC product.

Authorization check

Control internal / external key assignment

Inclusion of the issuer risk

Defaulting of the limit product group

In addition, the following control elements are stored with the

STC product:

Cash / forward indicator

Credit risk rule

The credit risk rule stored with the STC product is overridden by that stored with the financial object for those transactions for which end of day processing has already been performed.

###### Checking New Transactions

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > Checking New Transactions | L7 | trm03 p.193 | loio `c508da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c508da531198434de10000000a174cb4.html?locale=en-US)

Use

This function enables you to check transactions that are as yet unknown to the SAP system (meaning neither as external transactions nor as transactions in the data pool). Using the values entered, the system checks whether a new transaction complies with the limit.


In the single transaction check, you can use the mass data capability to check complex constructions, such as generic transactions.

**Procedure**

Choose: Tools Single Transaction Check Check New Transaction . The system displays the screen Single Transaction Check: Initial Screen for New Transaction.

Specify the business partner, the STC product, the evaluation date (is always today’s date) and the company code of the transaction you want to check.


Choose Check to check that your entries are consistent.


Choose Continue.

On the Transaction tab page choose:

Check Limit Utilization to determine whether the new transaction will exceed the limit, or


Check and Update Limit Utilization to check the new transaction, and update it in Limit Management.


On the Additional Data tab page you can edit the limit characteristic values for the transaction.

By setting the CP Risk Active indicator, you control whether the transaction is relevant for counterparty/issuer risk.

The limit characteristic Trader is set to the name of the user by default.

On the Generated Char. tab page you can edit the values of the generated characteristics of the transaction.

**Result**

You have checked whether a new transaction complies with or exceeds the limit, and possibly updated the limit. In the data group Limit Check Result the system reports the utilization of the limit by means of a traffic-light display, and the status of the update.

Details about limit utilization

To view detailed information about the limit utilization choose Limit Utilization Details.


The system displays a dialogue box. Choose Single Utilizations to view the individual utilizations.

The system displays another dialogue box. Choose STC Log to display the single transaction check log.

Printing the results of the check

Choose Print Check Results to print a trader's note. This summarizes information about the transaction, the result of the check, and the transaction’s key figures.

###### Checking Existing Transactions

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > Checking Existing Transactions | L7 | trm03 p.195 | loio `f208da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f208da531198434de10000000a174cb4.html?locale=en-US)

**Use**

If you want to change basic key figures, you use this function to check transactions that were created externally, and those already in the data pool.


In the single transaction check, you can use the mass data capability to check complex constructions, such as generic transactions.

**Procedure**

Choose Tools Single Transaction Check Check Existing Transaction .

The system displays the screen Single Transaction Check: Initial Screen: Change Transaction.

Enter the Evaluation Date, the STC Product and the Company Code. Specify the transaction more clearly by entering a transaction number.


Choose Check to check that your entries are consistent.


Choose Continue.


On the Transaction tab page choose:

Check Limit Utilization to determine whether the new transaction will exceed the limit.


Check and Update Limit Utilization to check the new transaction, and update it in Limit Management.


On the Additional Data tab page you can edit the limit characteristic values for the transaction.

By setting the CP Risk Active indicator, you control whether the transaction is relevant for counterparty/issuer risk.

The limit characteristic trader is set to the name of the user by default.

On the Generated Char . tab page you can edit the values of the generated characteristics of the transaction.

**Result**

You have checked whether the changed transaction exceeds the limit, and possibly updated the transaction in Limit Management. In the Limit Check Result data group, the system reports the utilization of the limit by means of a traffic light display and the status of the update.

Details about limit utilization

To view detailed information about the limit utilization choose Limit Utilization Details.


The system displays a dialogue box. Choose Single Utilizations to view the individual utilizations.

The system displays another dialogue box. Choose STC Log to display the single transaction check log.

Printing the results of the check

Choose Print Check Results to print a trader's note. This summarizes information about the transaction, the result of the check, and the transaction’s key figures.

###### Deactivating the Update for External Transactions

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > Deactivating the Update for External Transactions | L7 | trm03 p.196 | loio `d708da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d708da531198434de10000000a174cb4.html?locale=en-US)

**Use**

If you do not want to update limits for external transactions, you need to deactivate the external transaction.

**Caution:**

This function cannot be used for transactions that have already been saved in the data pool, or for those that have already been updated in end-of-day processing. You can still deactivate a transaction if it has been saved in the data pool but its limit utilization has not yet been updated by end-of-day processing.

**Procedure**

- 1. Choose Tools Single Transaction Check Deactivate External Transaction

The system displays the screen Single Transaction Check: Deactivate External Transaction .

- 2. Enter the required data.
- 3. Choose Deactivate Trans. , to exclude the transaction from limit updating.


**Note:**

Choose Check to check that your entries are consistent.

**Result**

Under Result of Deactivation , the system displays the status of the transaction. Choose Display Log to view the log of the deactivation process.

###### Displaying an Overview of Transactions

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > Displaying an Overview of Transactions | L7 | trm03 p.196 | loio `0b0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0b0ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this application to obtain a list of the external transactions and data pool transactions for which a single transaction check can be performed.

**Procedure**

- 1. Choose ... Tools Single Transaction Check Display Transactions.
- 2. The system displays the screen Single Transaction Check: Display Transactions .


- 3. On the left part of the screen you can navigate through the structure containing the STC products.
- 4. End nodes that are in a different color are the STC products that were defined in Customizing as default values for STC products.
- 5. On the right part of the screen you can see which transactions exist for the portfolio you selected.


**Result**

You can display additional information about each transaction by using the following functions:

||Details|
|---|---|
| Counterparty|Limit characteristics of the counterparty|
| Counterparty|The basic key figures of the transaction that are required for calculating amounts that are to be attributed to the counterparty.|
| Issuer|Limit characteristics of the issuer|
| Issuer|The basic key figures of the transaction that are required for calculating the amounts that are to be attributed to the issuer.|


You can also call other functions directly from this screen:

Choose Postprocess to change the attributable amount of the selected transaction.

Choose Deactivate to deactivate the selected transaction.

###### Displaying the Single Transaction Check Log

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > Displaying the Single Transaction Check Log | L7 | trm03 p.197 | loio `c309da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c309da531198434de10000000a174cb4.html?locale=en-US)

This list provides you with details of the system message received by the trader or loans employee after entering the transaction data.

A traffic light symbol indicates if a limit has been exceeded:

: Internal limit has been exceeded


: External limit or the critical limit usage has been exceeded


: No limits have been exceeded


You have the option of branching from the log entries to the transaction data of the underlying transaction. Choose Transaction details.

**Procedure**

- 1. Choose Information System Reporting Single Transaction Check: Logs .

This brings you to the screen Logs from Single Transaction Checks.

- 2. Enter the selection criteria you require.


STC user (user who initiated the transaction)

Date of the check

Limit type

Selection by limit characteristics

- 3. Choose Execute.

###### Integrated Single Transaction Check

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > Single Transaction Check > Integrated Single Transaction Check | L7 | trm03 p.198 | loio `b008da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b008da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function when you create trading or credit transactions to check them against the relevant limits. You can define that the integrated single transaction check generates a workflow if limits are exceeded, and that a message is sent automatically, for example. This enables you to monitor risks as they occur.

In the integrated default risk limit check, the system calculates the relevant attributable amounts for the data entered and for all risk categories. It checks the maximum risk commitment period that was defined, and the internal and external limits, or the critical limit utilization. You can also define limits for each product type and transaction type, and check whether they are exceeded.

**Note:**

For more information, see the documentation for the general single transaction check (for example, the section about updating limit utilizations).

**Prerequisites**

Default risk limit check has been activated

In the Customizing for Credit Risk Analyzer, you have activated the integrated single transaction check. You do this under Basic Settings Activate Integrated Default Risk Limit Check .


Optional: Limit check for each product type and transaction type has been activated

You have activated the integrated single transaction check in the Customizing for Credit Risk Analyzer under Attributable Amount Determination Edit Settings for Determination Procedures .

Automatic financial object integration has been activated

You have activated the automatic financial object integration for the relevant product types and company codes. You do this in the Customizing for Credit Risk Analyzer under Basic Settings Automatic Integration of Financial Objects in Transaction Master Data for the product types in question.

The tab page Default Risk Limitation is available in Transaction Manager only if you have activated automatic financial object integration. You use this tab page to store the relevant information for counterparty/issuer risk.

The update category has been defined

You have stored the update category Update when limit utilizations are generated and online in the Customizing for Credit Risk Analyzer under Limit Management Define Limit Types . The update category specifies for which limit type an update of the limit utilization is to be carried out in the course of the day. The system uses this information to calculate the current utilization of the individual limits.

Limits have been defined

The integrated default risk and limit check gives correct results only if the utilization of the limits is defined, or limits are defined for each product type and transaction type:

You have run end-of-day processing for the previous day in order to calculate the utilization of the limits affected by the limit characteristics of existing transactions.

You have created limits for each product type and transaction type. To do so, in the SAP Easy Access screen choose Credit Risk Analyzer Master Data Limits Edit Limits for Each Product Type and Transaction Type .


Optional: Workflow has been switched on

You have activated the connection to the workflow function in the Customizing for Credit Risk Analyzer under Basic Settings Global Settings . To define the recipient of the workflow, you have either defined an HR organigram in the Customizing for SAP NetWeaver under SAP Web Application Server Business Management SAP Business Workflow

Edit Organizational Plan; or you have assigned the sender and recipient directly in the Customizing for Credit Risk Analyzer under Basic Settings Assignments Assignment of Senders to Recipients Assign Senders of Workflows to Recipients .


**Features**

When entering or editing transactions, you can trigger the integrated default risk limit check in the following ways:

By using the check pushbutton

The system only checks the transaction against the relevant limits. It does not update the limits.

When saving the transaction

The system checks the transaction against the relevant limits, and updates them. If you activated the workflow function, and the limits were exceeded, the system also generates a workflow.

In the integrated default risk limit check, the system does the following:

- 1. It checks for compliance with the limits

When the system checks the limits for each product type and transaction type, it compares the limits defined for the respective product type and transaction type.

When the system checks the credit lines, it does the following:

- a. It determines which limits are relevant for the integrated default risk limit check.
- b. It calculates the attributable amounts of the transaction.
- c. It calculates the current limit utilizations of the limits relevant for the check.


- 2. It reports the results of the check to the user processing the transaction.
- 3. It generates a log containing the results of the check for documentation purposes in Limit Management.
- 4. It updates the limit utilizations (see Updating of Limit Utilizations ) when the transaction is saved.

- 5. If limits were exceeded, and the workflow function is active, it generates a workflow.


**Activities**

- 1. Enter a financial transaction in Transaction Manager.
- 2. Choose the Default Risk Limitation tab page, and enter the information about counterparty/issuer risk for the financial object of the transaction.


To be able to use the integrated default risk limit check, in the financial object you have set the Counterparty/Issuer Risk indicator to active, and store a default risk rule. You still have to do this if you have created limits for limit product groups.

You can enter this data manually when you create or change the transaction. If you have defined that the control parameters are to be derived for the product type in question, the system stores the information automatically.

- 3. Choose Check .


The system checks whether the transactions exceed the limits, and it displays the result of the check in a dialog box.

- 4. Choose Limit utilization details in order to see which attributable amount the system calculated for the transaction and to which limit type this amount was assigned. Once you have saved the transaction, you can branch from here to the logs of the single transaction check.
- 5. Choose Save.


The system updates the transaction in Limit Management. If you activated the workflow function, and the limits were exceeded, the system also generates a workflow.

**Result**

You have checked whether a new or a changed transaction is within the limit or exceeds the limit, and by saving you have triggered the updating of the transaction. If the limits were exceeded, you have generated a workflow. The system reports the limit usage by displaying a warning light under Transaction check.

**Note:**

Note that limit types that have a determination procedure that takes netting into account are not subject to the integrated default risk limit check, and are not displayed in the detail log.

If you created a transaction in Transaction Manager, and want to edit it using the single transaction check, before you created the transaction, you need to have defined a default STC product for the product type in question in the Customizing for Credit Risk Analyzer under Basic Settings Definitions Define Single Transaction Check Product .

###### End-of-Day Processing

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > End-of-Day Processing | L6 | trm03 p.200 | loio `0dbd9753858ced23e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0dbd9753858ced23e10000000a174cb4.html?locale=en-US)

Use

Use

In end-of-day processing, the system determines and updates limit utilizations based on the transactions and positions contained in the data pool and also the external transactions that were entered.

**Integration**

End-of-day processing is closely linked with the single transaction check. In Customizing under Limit Management Enter Basic Settings for Limit Management , you can specify whether the 24-hour capability is used. 24-hour capability enables you to apply the single transaction check at any point in time, even when end-of-day processing is running.

**Prerequisites**

The calculation is product-type-specific and takes place according to the settings made in Customizing. For a detailed description of the how the system calculates the attributable amount, refer to the documentation about the function Attributable Amount Determination.

**Features**

In the end-of-day processing run, the system selects the transactions that, on the valuation date, are active and credit-limitrelevant. It determines attributable amounts regarding counterparty risks and issuer risks for these transactions. Attributable amounts are updated in Limit Management. Depending on the settings in Customizing, you can, if required, create new limits.

If, in Customizing, you have not stored a selection filter in the limit type, then, in end-of-day processing, all transactions flow into the limit type that are defined in the determination procedure as relevant to that particular limit type. However, if you have stored a selection filter in the limit type, end-of-day processing analyzes only a certain section of the credit portfolio in Limit Management. This means that only those transactions are attributed to the limit type that have values matching those of the selection filter. For more information about the selection filter, see Customizing under Basic Settings Definitions Define Selection Filter .

**Activities**

To update the limit utilizations, you need to trigger a report, which you start in batch mode. Once the system has determined the utilizations in this process, they are updated in the respective limit.

###### Generating Utilizations

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > End-of-Day Processing > Generating Utilizations | L7 | trm03 p.201 | loio `020ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/020ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

To analyze the drawn amounts (utilizations) for the respective position, you need to generate the utilizations in the end-of-day processing run.

**Prerequisites**

You can run end-of-day processing only if financial objects have been created for the existing transactions.

**Procedure**

- 1. Choose Tools End-of-Day Processing Generate Utilizations .

The system displays the End-of-Day Processing screen.

- 2. You can use the following selection criteria:


|Valuation date|Today’s date is the default setting.|
|---|---|
|Determination procedure|You can specify a range of determination procedures for which end-of-day processing is to be performed. You can specify more than one determination procedure by using the Multiple Selection function. |
|Control| |
|Log level|By specifying the log level, you define the level of detail of the results contained in the log for the program.|


****Note:****

You can save your entries as a variant by choosing Goto Variants Save as Variant... . You can call them up later by choosing .


- 3. Once you have entered your selection criteria, choose to start the program.



The system runs end-of-day processing. Once the end-of-day processing run is complete, the log is displayed automatically. It contains information about any errors that occurred during the determination of counterparty or issuer risks.

**Result**

You have run end-of-day processing and generated utilizations.

You can now display the limit utilizations that were updated by end-of-day processing in the overview of limit utilizations.

You can manage end-of-day processing logs at any time by choosing Information System Reporting End-of-Day Processing: Logs .

The error log contains long texts for the error messages. To view the long text, select an error message and choose Long Text.


You can also send error logs to other users. To do this, choose Log Save to PC File . Save the list in the required format.

Then you can send the list by choosing Office Work Place Outbox . In your office outbox, choose Documents and enter a name for the document. Then choose the Import function. Open the saved list. Select the document that was generated for the error log and send it by choosing Send. On the Create Document and Send screen, enter the user name of the recipient and then choose Send.


The recipients of the error logs can display the documents by choosing Office Work Place Inbox .

See also:

Postprocessing of incorrect transactions

###### Postprocessing

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > End-of-Day Processing > Postprocessing | L7 | trm03 p.202 | loio `d809da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d809da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Using the postprocessing function, you can update and correct during the day any erroneous transactions that already exist in the data pool but were not processed - and hence not updated - in end-of-day processing. You can also use postprocessing to re-post transactions for which end-of-day processing was run successfully (meaning there were no errors) but that were changed afterwards.

Postprocessing updates both status 1 and status 2 (see the documentation on updating limit utilizations).

**Note:**

Complex constructions can be checked in postprocessing using the mass data capability. Complex constructions include the generic transaction and netting groups, plus the collateral assigned to them.

If the processing of certain transactions is terminated, the system automatically creates a worklist that you can use to complete the processing of these transactions.

You can call each worklist separately in the Display Worklist application (report RAFO_WORK_STOCK_SHOW), which uses the SAP List Viewer . You can also delete worklists by removing them from the list (see also Reorganization Tools).

**Procedure**

The counterparty risk and the issuer risk are determined for the data pool transaction for both update categories (status 1 and 2).

- 1. Choose Tools End-of-Day Processing Execute Postprocessing .

The system displays the Postprocessing of Data Pool Transactions screen.

- 2. Enter the object number of the transaction you want to process, or enter the ID of the worklist.


**Note:**

The system postprocesses the transactions by using an evaluation type that identifies the market and valuation parameters of an evaluation from Market Risk Analysis. The evaluation type is stored in Customizing for Treasury and Risk Management under Basic Analyzer Settings Valuation Define and Set Up Evaluation Types .

**Result**

Having successfully calculated the utilizations, the system displays the attributions to the respective limit types in a dialog box.

###### Logs Generated in End-of-Day Processing

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > End-of-Day Processing > Logs Generated in End-of-Day Processing | L7 | trm03 p.203 | loio `bf08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bf08da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to display and manage logs generated in end-of-day processing.

**Activities**

- 1. Choose ... Information System Reporting End-of-Day Processing: Logs.

The system displays the screen Edit Logs .

- 2. Enter the selection criteria you require. These include:
- 3. Choose Execute .
- 4. The system displays the screen Log Display , and the logs you selected.


|Time Restriction|Date Start Time End Time|
|---|---|
|Activity|Display Log Display All Logs Delete Log Delete All Logs|

###### How Data is Selected in End-of-Day Processing

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > End-of-Day Processing > How Data is Selected in End-of-Day Processing | L7 | trm03 p.204 | loio `3009da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3009da531198434de10000000a174cb4.html?locale=en-US)

**Purpose**

In end-of-day processing, the system selects data by taking the start date and end date of the transaction from the financial object, and reading the counterparty risk active indicator. For collateral, it checks the active indicator in the master record.

Maintaining the transaction start/end dates in the financial object is optional. However, if you do maintain these dates you can do the following:

Run historical evaluations

Influence the extent of the basic data set, and hence the performance of the system.

The indicators in the collateral are interpreted as follows:

The counterparty risk active indicator in the financial object controls the actual secondary risk display.

The active indicator in the master record of the collateral forms its primary risk-reducing effect, and its potential secondary risk display.

**Process**

The process in which financial objects are selected for the generation of utilizations has wo steps (sequence in end-of-day processing):

|Step 1:|Selection of the basic data set of financial objects|
|---|---|
|Step 2:|Reselection of transactions when the system reads the data for collateral|

###### Selection of the Basic Data Set of Financial Objects

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > End-of-Day Processing > How Data is Selected in End-of-Day Processing > Selection of the Basic Data Set of Financial Objects | L8 | trm03 p.204 | loio `590ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/590ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

When selecting the basic data set, the system takes into account the category of the determination procedure (counterparty/issuer risk), and the value date you entered.

**Integration**

Selection criteria for counterparty/issuer risk determination procedures:

- 1. a. In the default risk limit part of the financial object, you need to have set the Counterparty Risk Active indicator.
- 2. b. If the fields Transaction Start CPR and Transaction End CPR in the financial object are filled, the valuation data must be within this time period (up to and including these dates).


**Example**

The following table explains the selection criteria:

|Valuation date|Transaction start|Transaction end|Counterparty relevant|Selection|
|---|---|---|---|---|
|06/30/2001|06/30/2001|10/30/2001|X|Yes|
|10/31/2001|06/30/2001|10/30/2001|X|No|
|06/15/2001|06/30/2001|10/30/2001|X|No|
|10/31/2001|06/30/2001| |X|Yes|
|06/15/2001| |10/30/2001|X|Yes|
|10/31/2001| | |X|Yes|
|07/01/2001|06/30/2001|10/30/2001| |No|

###### Reselection of Transactions

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Updating Limit Utilizations > End-of-Day Processing > How Data is Selected in End-of-Day Processing > Reselection of Transactions | L8 | trm03 p.205 | loio `b908da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b908da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The reselection of transactions is triggered during the analysis of collateral items if the basic set of data contains the financial object of a single-transaction-related collateral item but not the financial object of the transaction to which the collateral is assigned.

The following conditions apply for the reselection of transactions:

- 1. The collateral assigned to the transaction must already be in the basic data set.
- 2. The valuation date must be within the term of the financial object of the transaction. This is because the collateral is not effective for a transaction that has already expired.


Only those transactions are reselected that are not in the selected basic set because the field for the counterparty/issuer risk is inactive.

**Example**

The following example explains which conditions have to be met in order for the system to be able to reselect a transaction. We assume here that the determination procedure is relevant for counterparty/issuer risk.

|Case|1|2|3|4|5|6|7|8|9|
|---|---|---|---|---|---|---|---|---|---|
|Valuation date is within term of financial object| | | | |X|X|X|X|X|
|Financial object of the collateral item is activated for counterparty/issuer risk| | | |X|X| |X|X|X|
|Collateral is active in the master data| | | | | |X|X|X|X|
|Collateral is in the selected basic set| | | | | | |X|X|X|
|Financial object of the transaction is activated for counterparty/issuer risk|X|X| | | | | |X|X|
|Valuation date is within the term of the financial object of the transaction|X| |X|X|X|X|X| |X|
|Transaction is in the selected basic set|X| | | | | | | |X|
|Transaction is reselected| | | | | | |X| | |


As you can see in the table, the reselection of a transaction takes place in case 7 only. This case fulfills all the conditions required for reselection.

###### Displaying Utilizations

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Displaying Utilizations | L5 | trm03 p.206 | loio `c909da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c909da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The reports Overview of Utilizations - Selection Using All Characteristics (transaction TBLB) and Overview of Utilizations Selection Using Direct Characteristics (transaction TBL4) enable you to monitor existing limits and their utilizations.

**Procedure**

- 1. Choose Information System Reporting Utilizations Overview: Selection Using All Characteristics / Selection Using Direct Characteristics .
- 2. The system displays the screen Overview of Utilizations - Selection Using all / Direct Characteristics in which you can enter the following selection criteria:


**Note:**

The selection using all characteristics also contains derived characteristics and free (customer-defined) characteristics.

|General Access Options|(Applies for both reports)|
|---|---|
|Limit Type| |
|Limit Currency|Here you specify that limits in a particular currency only are displayed.|
|Determination Procedure| |
|Selection of Utilizations| |
|Limit Utilization Base|The limit utilizations are calculated in end-of-day processing and can be updated online depending on the settings you have made in Customizing. Choose here whether you would like to see either the limit utilizations calculated in the last end-of-day processing run or the current utilization. The current limit utilization is based on the last end-of-day processing plus any additional changes triggered by the single transaction check. **Note:** Only available for limit types for which the update category is set to 2 Update When Utilizations Are Generated and Online.|
|Validity Date for Utilization|The validity date specifies when a limit utilization is valid.|
|Determination Date|The determination date is the date on which limit utilization determination was started. Note that the determination date can be different from the validity date.|


| |You can also set the Latest Determination per Limit Type indicator to view the latest values. In this case, the system overrides the determination date. Utilizations with a determination date in the future are not displayed.|
|---|---|
|Selection of Limits for the Report Overview of Utilizations - Selection Using All Characteristics|You can define which limits are selected by specifying the characteristic values of the limit characteristics. The system does not determine derived characteristics. You must therefore enter all the selection criteria you require.|
|Limits Without Utilizations Limits Valid From|If you set the Limits Without Utilizations indicator and enter a date, the system also displays limits that have not been utilized and that have not yet expired.|
|Display Filter|You can select a predefined display filter. |
|Direct Characteristics|Company code, business partner, limit product group, portfolio, trader, currency as limit characteristic, monitoring unit.|
|Derived Characteristics|Country/region, industry, rating from the business partner|
|Free Characteristics|Free characteristics 01-15|
|Generated Characteristics|Free characteristics that were generated from the active analysis structure in the Market Risk component and transferred to Limit Management.|
|Selection of limits for the report Overview of Utilizations - Selection Using Direct Characteristics|When you enter direct characteristics, the system automatically determines derived characteristics, free characteristics, and any affiliated business partners based on the direct characteristics you entered and for the date you specified. It then displays all the relevant limits.|
|Display Filter|You can select a predefined display filter. |
|Limit Characteristics|Direct Characteristics: Company code, business partner, limit product group, portfolio, trader, currency as limit characteristic, and monitoring unit are available. Generated Characteristics: Free characteristics that were generated from the active analysis structure in the Market Risk component and transferred to Limit Management.|
|Derived Characteristics For|This field specifies for which validity date the system determines the derived limit characteristics. If you do not enter a date, the system determines utilizations for all validity dates of the relevant limit utilizations.|
|Selection of Limits Limits without utilizations? Valid From|If you set the Limits without utilizations? indicator and enter a date, the system also displays limits that have not been utilized and that have not yet expired.|
|Output Control| |
|Display Currency|The system converts amounts to the display currency that would otherwise be shown in the limit currency.|


|Rounding Factor|You choose the rounding factor if you want the system to display all amounts in thousands, for example.|
|---|---|
|Warning When Limit Exceeded|Sets the traffic light to red if an internal limit is exceeded.|
|Warning When RCP Is Exceeded|Sets the traffic light to red if the risk commitment period stored in the limit is exceeded.|
|Utilization Only on Workdays|If you set the Utilization Only on Workdays indicator, then the system compares the date entries with the factory calendar stored in Customizing.|
|Display Layout|You can use the input help to choose and set the layouts for totals records, single records, grouping levels 1 and 2. Note that you can assign the layouts only to the lists for which they were created.|
|Exception Reporting Control|(Applies for both reports)|
|Only Exceeded Limits Only Exceeded Char. Combinat.|You can define whether the system displays only exceeded limits or only exceeded characteristic combinations.|


**Note:**

You can use the option for saving as a variant the parameters that you have entered. To do this, choose Goto Variants Save as Variant . You can display the saved parameters again at any time by choosing Goto Variants Get or by choosing .

- 3. Start the report containing your parameters by choosing .
- 4. The system displays the Overview of Utilizations - Selection Using all/Direct Characteristics screen. In accordance with your selections, the system displays as header information the selected limit type and as line information the validity period, the amounts of the internal and external limit, and the utilizations of these limits. A red traffic light is shown if the internal limit is exceeded. A yellow traffic light is shown if the external limit or critical limit usage is exceeded.
- 5. You can branch from reporting to the maintenance screen for limits by choosing . You can make changes here.
- 6. Drilldown options


|Grouping reporting|Grouping reporting enables you to break down totals records by any limit characteristic. Using grouping level 1, you can, for example, drill down to one or more limits for a country/region by business partner. By branching to the second level, you can view the individual transactions and their attributable amounts per determination procedure.|
|---|---|
|Grouping level 1|Grouping level 1 allows you to drill down to the single records by all limit characteristics. Select the entry you want to process and choose .  Select the required limit characteristics and choose .  The system displays the drilldown.|
|Grouping level 2|Grouping level 2 allows you to drill down in the single records by single transactions with attributable amounts shown per determination procedure.|


Select the entry you want to process and choose .


The system displays the drilldown.

The second level can also be accessed directly from the totals record list.

- 7. From the totals records and from the single utilizations, you can branch to the STC logs for transactions imported intraday.


|Drilldown To|What You Need to Know|
|---|---|
|Business partner|Select a limit utilization and choose .|
|Single utilizations|Select a limit utilization and choose .  The system displays the single utilization records.|
|Calling up the STC log|Select a utilization with status 2 and choose . |
|Customizing|Select a utilization and choose Customizing.|


You have other drilldown options on the screen displaying the single records:

|Drilldown To|What You Need to Know|
|---|---|
|Master data|Select a transaction or a position and choose .  For transactions, the system displays the underlying transaction. For positions in which a total of position-relevant transactions are based, the system first lists the key figures for issuer risk. Select one of the transactions or a position and then choose Goto Transaction Details again. If you chose a position, the system displays the position object. If you chose a transaction, the system displays the transaction data.|
|Collateral|Select a transaction or a position and choose .|
|Calling up the STC log|Select a transaction or a position and choose .|
|Attributable amount determination|Select a transaction or a position and choose . Specify an evaluation type and choose Program Execute . |


**Result**

The system displays an overview of the limit utilizations in accordance with your selection criteria. You can display more detailed information by calling up the detailed logs.

**Note:**

By using user exits, you can include in the display of utilizations customer-defined fields that can be filled with your own data. This takes place in EXIT-SAPLTBLX-005 and EXIT-SAPLTBLX-006 respectively.

**Note:**

For the limit utilizations overview and for the administration of the limits, customer exit EXIT_SAPLTBL_002 is included to prevent a user from displaying a particular limit or utilization. You might want to do this for loans to employees, for example. Note that, when you use the drilldown, the system rechecks the authorization.

The include LXTBL1F02 contains sample coding. You can find a detailed description of the SAP enhancements in the documentation about the Enhancement Concept.

For more information about the formatting of lists, see the documentation about the SAP List Viewer (ALV).

###### Collateral

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Collateral | L5 | trm03 p.210 | loio `9409da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9409da531198434de10000000a174cb4.html?locale=en-US)

**Use**

In the Default Risk and Limit System , certain information about collateral is required to enable the system to calculate attributable amounts correctly, and record secondary risk appropriately. Only collateral data that is relevant for these purposes is entered in the SAP system. Seen from a general business perspective, collateral has far more complex data.

The Default Risk and Limit System distinguishes between the following levels of collateral:

Global collateral (not used in Credit Risk Analyzer)

Single-transaction-related collateral

You assign single-transaction-related collateral to a particular financial transaction. You can assign more than one collateral item to a single transaction. When appropriate, this reduces the attributable amounts.

Collateral agreements

A collateral agreement is a contract agreeing the provision of collateral for trading transactions between two business partners. Collateral agreements reduce risk at the level of the attributable amounts.

**Prerequisites**

You need authorization object J_B_KLTCOD in order to process collateral (regardless of the level of the collateral). This is contained in authorization profiles F_T_FTLM_ALL and J_B_ISB_ALL.

**Features**

The system can calculate attributable amounts (secondary attributable amounts) for collateral. When collateral is taken into account, the system displays a net attributable amount for the primary transaction, and not a gross attributable amount.

**Example:**

The company Meier’s Mill has taken a loan of EUR 100,000. There are 2 single-transaction-related collateral items. The Deutsche Bank provides a guarantee of EUR 80,000. Mr. Meier provides a mortgage (tangible collateral) of EUR 40,000.

|Business Partner|Meier’s Mill|Deutsche Bank|Mr. Meier|
|---|---|---|---|
|Product|Loan|Guarantee|Land charge|
|Nominal amount|100,000|80,000|40,000|
|Priority| |1|1|


|Counterparty exposure (gross) per business partner|100,000|80,000|0 (because of tangible collateral)|
|---|---|---|---|
|Adjustment rate| |2/3|1/3|
|Counterparty exposure (net, secondary)| |66,666|0|
|Counterparty exposure (net, primary)|0| | |

###### Processing Single-Transaction-Related Collateral

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Collateral > Processing Single-Transaction-Related Collateral | L6 | trm03 p.211 | loio `6709da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6709da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You assign single-transaction-related collateral to a particular financial transaction.

The system distinguishes between the following collateral value categories:

Percentual collateralization

Collateralization using a collateral amount

Collateralization using securities

You can assign more than one collateral provision to a financial object within a collateral value category. The collateral provisions can then be processed in accordance with the collateral priorities. In the case of collateral using securities, only one class per collateral provision is permitted.

**Prerequisites**

So that single-transaction-related collateral is included in the calculation of attributable amounts, you need to have entered the following settings in Customizing:

You need to have already created a collateral type. You do this in Customizing under Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Basic Settings Master Data Define Collateral Type .

You need to have already created a collateral priority. You do this in Customizing under Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Basic Settings Master Data Define Collateral Priority .

You need to have already created a collateral valuation rule. You do this in Customizing under Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Basic Settings Definitions Define Collateral Valuation Rule. .

**Procedure for Creating Single-Transaction-Related Collateral**

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Tools Collateral Provision Create .

The system displays the screen Create Collateral Provision: Initial Screen.

- 2. Enter an ExternalCollateral ID, choose the classification Single-Transaction-Related Collateral and Continue.



Alternatively, you can choose Copy From... to copy an existing collateral item.

The system displays the screen Create Collateral Provision: Overview.

- 3. Enter a long name and a short name for the collateral.
- 4. In the data group Collateral Classification specify the Collateral Value Type and the Collateral Type.
- 5. You make the connection to the single transaction by specifying the financial object number on the Assignment tab page.
- 6. On the Administration tab page, the Record active indicator has to be set. This ensures that the collateral provision is included in the determination of attributable amounts. This indicator is set by default. By deselecting this indicator you are then able to delete the collateral provision. Here you can also enter the collateral provider (if the type of collateral is personal) and the priority of the collateral provision.
- 7. On the tab page Items, the collateral value category you chose earlier determines which data you need to enter.
- 8. Choose Save.


- 9. For the primary or secondary risk-reducing effect of the collateral to be taken into account in the attributable amount determination, a financial object for the single-transaction-related collateral item is required. Once you have saved the collateral, if you then choose Financial Object in the application toolbar, you branch directly to financial object creation.


|Collateral Value Category|Fields Requiring Entries|
|---|---|
|Percentual collateralization|Valid from date, percentage (economic and political)|
|Collateralization using a collateral amount|Valid from date, collateral amount, currency|
|Collateralization using securities|Valid from date, security ID number, number of units or amount|


**Caution:**

Note that in the function for maintaining financial objects for single-transaction-related collateral, the system, when selecting data, does not take into account the validity end date stored in the financial object.

**Procedure for Changing Single-Transaction-Related Collateral**

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Tools Collateral Provision Change .

The system displays the screen Change Collateral Provision.

- 2. Enter the External Collateral ID and choose Continue.


- 3. Make the changes required and choose .
- 4. You can branch directly to financial object maintenance by choosing Financial Object. Note that in the function for maintaining financial objects for single-transaction-related collateral, the system, when selecting data, does not take into account the validity end date stored in the financial object.


**Result**

If a net determination procedure is used, the single-transaction-related collateral is offset against the attributable amount of the transaction. This therefore reduces the amount of limit utilized. You need to note, however, that tangible collateral does not increase the counterparty/issuer risk of the guarantor, but instead reduces the risk of the primary transaction.

In a netting group , a single-transaction-related collateral item first reduces the positive net present value of the single transaction, and then the add-on. (The reduction by the collateral affects the determination of the net/gross ratio and the total of the single transactions' add-on and, therefore, the netting add-on.)

The attributable amount of the collateral is calculated as follows:

|Percentual collateralization|Attributable amount (collateral) = CALCBAS (transaction) x % (collateral)|
|---|---|
|Collateral amount|Attributable amount (collateral) = collateral amount In the case of risk-adjusted attributable amount determination, the collateral amount is also risk-weighted.|
|Collateralization using securities|Attributable amount (collateral) = [max (0, NPV ) – nominal amount x AOF ] x (1 - DEFPROB ) S S S S|


where:

|ABS|absolute amount|
|---|---|
|CALCBAS|Calculation base|
|AOF c|Collateral add-on factor|
|DEFPROBc|Default probability of the collateral|

###### Collateral Agreement

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Collateral > Collateral Agreement | L6 | trm03 p.213 | loio `440ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/440ada531198434de10000000a174cb4.html?locale=en-US)

Definition

A collateral agreement is a contract regarding the provision of collateral for trading transactions between two business partners. The agreement involves the transfer of collaterals (usually securities, cash collaterals) as soon as the market value of the trading transactions requiring collateral exceeds a threshold amount (ThA). The threshold amount the contract partners grant each other

can vary.

Both exposures from open trading transactions and values from collaterals already provided fluctuate, depending on the market. For this reason there must be a comparison of the exposures and the collateral per counterparty or issuer at agreed time intervals (daily, monthly, for example). To restrict transaction costs, additional payment obligations arising from the threshold amount being exceeded do not have to be met immediately on the valuation key date, but rather in phases, each time what is known as the minimum transfer amount ( MTA ) is exceeded.

**Caution:**

The attribution of collateral agreements only takes place in end of day processing . The single transaction check does not support collateral agreements.

###### Processing Collateral Agreements

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Collateral > Collateral Agreement > Processing Collateral Agreements | L7 | trm03 p.213 | loio `7009da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7009da531198434de10000000a174cb4.html?locale=en-US)

Prerequisites

So that collateral agreements are included in the determination of attributable amounts, you need to have defined the following settings in Customizing:

You need to have already defined a netting group, to which the collateral ID can be assigned. You create netting groups in Customizing under Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Basic Settings Definitions Define Netting Group .

In addition, you need to have entered a collateral ID in the default risk data in the financial object.

Procedure for Creating Collateral Agreements

- 1. In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Tools Collateral Provision Create .

The system displays the screen Create Collateral Provision : Initial Screen.

- 2. Enter an ExternalCollateral ID, choose the classification Collateral Agreement as Collateral. Then choose Continue.


The system displays the screen Create Collateral Provision: Overview.

- 3. Enter a long name and a short name for the collateral.

In the tab page Contract enter the netting group in which the transactions of the collateral agreement are to be netted. Also enter the threshold amount and the minimum transfer amount. The system determines the currency of these amounts from the netting group.

On the Administration tab page, you need to set the Record active indicator. This ensures that the collateral is considered when attributable amounts are calculated. This indicator is set by default. By deselecting this indicator you are then able to delete the collateral provision.

On the tab page Accumulated payments you can enter the valid from date, amount and currency of the accumulated payments.

- 4. Choose Save.



Result

If a net determination procedure is used, collateral agreements are offset against the attributable amount, reducing the attributable amounts of all the transactions assigned to a collateral group, and thus reducing the amount of the limit that is utilized.

###### Attributable Amount of a Collateral Group

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Collateral > Collateral Agreement > Attributable Amount of a Collateral Group | L7 | trm03 p.214 | loio `7f09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7f09da531198434de10000000a174cb4.html?locale=en-US)

For single transactions of a netting group that belong to a collateral agreement, the system determines an attributable amount per collateral agreement. The way in which the attributable amount is determined depends on whether risk determination within the netting group takes place in a risk-adjusted or volume-oriented way.

The system determines and shows the attributable amounts individually per collateral group. To obtain the attributable amount for a collateral agreement, in the first step the system calculates the net present value of a collateral group from all the included transactions by totaling all net present values.

Net present value (NPV) =∑(PV )

i

A distinction must be made between the following cases for the determination of the attributable amount of the collateral group. When considering these cases, the threshold amount and the accumulated settlement payments are included:

[figure TRM03-F278 - Depending on the netting group settings, the attributable amount of the collateral group can be additionally weighted with an average default probability.]

Depending on the netting group settings, the attributable amount of the collateral group can be additionally weighted with an average default probability.

|Default probability = [figure TRM03-F279]|
|---|


**Note:**

The add-on of the single transactions is not offset, but displayed in reporting.

###### Displaying an Overview of Collateral

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Collateral > Displaying an Overview of Collateral | L6 | trm03 p.215 | loio `c808da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c808da531198434de10000000a174cb4.html?locale=en-US)

**Use**

This evaluation provides you with an overview of stored collateral provisions.

**Procedure**

- 1. Choose Information System Reporting Collateral Overview .

The system displays the screen Credit Limit: Display Collateral Provision.

- 2. Enter the selection criteria you require. Your options include:


|Layout of Display|In the overview of collateral, you can define a display layout that you can use when you call up the overview a later point in time.|
|---|---|
|Selection of Collateral Provision|External Collateral ID Key Date|
|Status of Collateral Provision|Active Collateral Provision Inactive Collateral Provision All Collateral Provision|
|Level of Collateral Provision|All Global Collateral Single Transaction Collateral Collateral Agreements|
|Additional Selection For:|Global Collateral Single Transaction Collateral Collateral Agreements|


Choose .

**Result**

You receive a list displaying all the selected collateral provisions. Only those items are shown that are valid on the key date you specified.

By double clicking on a row you can branch to detailed information about the collateral.

**Note:**

You can change the layout by choosing . To select from layouts that already exist choose , and you can save the layout with . If you define and save your own layout, you can use it in the future by entering it as a selection criterion.

###### Displaying Change Documents for Collateral

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Collateral > Displaying Change Documents for Collateral | L6 | trm03 p.216 | loio `4609da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4609da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The system logs changes made to collateral in what are called change documents . A new document with an internal number is created each time the data for collateral is changed. This function provides continuous logging of all changes.

**Note:**

No change document is generated when the data is initially created.

The following data is recorded in the change documents:

Document number (internal number assignment)

Changed by (name of the user)

Date and time of the change

Category of the basic key figure

Key figure valid from: If you change an item , the valid from date is recorded. For changes to all other data, this field shows its initial value.

**Procedure**

- 1. You do this by choosing the following path from the SAP Easy Access screen: Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Tools Collateral Provision Change .

The system displays the screen Change Collateral Provision.

- 2. Select the collateral item you require and choose Continue.

The system displays the screen Change Collateral Provision.

- 3. Choose Goto Change Documents .


**Result**

The system displays a list of change documents.

By choosing Line Items you can view the following information for each change document:

The technical name of the field whose data was changed

A description of the changed field

The old and new values of the field

The type of change

###### Reservations

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Reservations | L5 | trm03 p.217 | loio `4c09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The reservation function enables you to reserve a free limit for a certain period. The attributable amounts can be either calculated by using basic key figures or entered with the reservation.

You can store a note by choosing Edit Note.

**Prerequisites**

There’s an authorization object especially for the maintenance of reservations: F_T_VTBLR.

**Integration**

The single transaction check and end-of-day processing consider the reservations.

**Note:**

To simplify the creation of reservations, you can store default values (in particular the default risk rule) for reservations. You do this in Customizing under Limit Management Enter Basic Settings for Limit Management .

If you’re using 24-hour capability, you can still use the reservation function while end-of-day processing is running, or during a single-transaction check.

**Activities**

Creating Reservations

- 1. Choose Master Data Reservations Create .
- 2. Choose between entering the attributable amount directly or letting the system calculate it using the basic key figures.


Entering Attributable Amounts Directly

|Reservation ID|The number is assigned automatically.|
|---|---|
|Name|Free text|
|Search term|Free text|
|Reservation Data| |
|Valid From|Today's date|
|Valid To|Expiry date of the reservation.|
|Limit Characteristics|The reservation is applied to all limits that correspond to the characteristic values entered here and to the determination procedures.|
|Administrative Data| |
|Deletion Flag|If you set this indicator, the reservation will be ignored the next time utilizations are generated and it won’t be taken into account in the current day balance (status 2).|
|Attributable Amounts| |
|Determination Procedure|The determination procedure defines which limit types are affected by a utilization.|
|Validity Date of Utilization|This field is filled only for determination procedures that consider settlement risks. Leave the field blank for credit risks, as the most recent determination date is used as the default value.|
|Reservation Amount|Attributable amount of the reservation|
|Reservation Currency|Currency of the reservation amount|


Before you save, you can choose Check to check the reservation against the relevant limit. Save your entries by choosing Save.


**Using Basic Key Figures to Calculate Attributable Amounts**

|Reservation ID|The number is assigned automatically.|
|---|---|
|Name|Free text|
|Search term|Free text|
|Reservation Data| |
|Counterparty Risk Active (CP Risk Active)|By setting the CP Risk Active indicator, you define whether the transaction is relevant for counterparty/issuer risk.|
|Default Risk Rule|Default value for the default risk rule. This can be overwritten.|
|Validity Period|Valid From: Today’s date Valid To: Expiry date of the reservation|
|Date Fields|Start of Original Term: Enables the reservation to be applied to the correct maturity band and is based on the underlying transaction. End of Original Term: Enables the system to derive the remaining term and the original term. It is based on the underlying transaction and ensures that the reservation is applied to the correct maturity band. Date for Market Value Change Period: The market value change period is the period applied in the valuation of trading transactions to calculate the potential change in the market value of the transaction. The market value change period is the difference between the base date and the valuation key date.|
|Limit Characteristics|The reservation is applied to all limits that correspond to the characteristic values entered here and to the derived determination procedures.|
|Basic key figures|Using your entries (default risk rule, limit characteristics), the limit system checks which basic key figures are needed in order to calculate the various attributable amounts. These entries are required entries.|
|Generated characteristics|You can edit the values for the generated characteristics here.|
|Administrative Data| |
|Deletion flag|If you set this indicator, the reservation will be ignored the next time utilizations are generated, and it won’t be taken into account in the current day balance (status 2).|
|Attributable Amounts The system automatically fills the fields for the attributable amounts.| |
|Determination procedure|The determination procedure defines which limit types are affected by a utilization.|


|Validity date of utilization|This field is filled only for determination procedures that take account of settlement risks. The field remains blank for credit risks because the most recent determination date is used as the default value.|
|---|---|
|Reservation amount|Attributable amount of the reservation|
|Reservation currency|Currency of the reservation amount|


Choose Save to save your entries. Before you save, you can choose Check to check the reservation against the relevant limit.


Changing Reservations

- 1. Choose Master Data Reservations Change .
- 2. Enter the reservation ID and choose Enter.
- 3. Overwrite the existing entries, and then choose Save to save your changes.



**Note:**

You need to set the deletion flag so that the reservation is ignored the next time the system generates the utilizations. To do this, set the flag in the Administrative Data area. If the flag is set, you can delete the reservation in Customizing by choosing Limit Management Reorganization Delete Reservations .

Displaying Reservations

- 1. Choose Master Data Reservations Display .
- 2. Enter the reservation ID and choose Enter.


- 3. You can display the existing entries.


Collective Processing

To ensure efficient processing of more than one limit, you can use collective processing for the functions described above.

- 1. Choose Master Data Reservations Collective Processing .
- 2. Once you have created/changed/displayed the reservations as required, you can use the following additional functions:


Copy reservations by choosing Copy.

Extend reservations using Extend.


Enter notes using Notes.


Change Documents

The system keeps a record, in the form of a change document, of all changes made to reservations.

You can view change documents for each reservation ID in the display/change mode or by using a report:

In change/display mode: Reservations Change Documents .

Report: Information System Reporting Reservations Display Changes . In this report, you can select your reservations by the reservation ID (range), the date on which the last change was made, and the user who last changed the

reservation. You display the reservations by choosing Execute.

###### Field Selection Control

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Limit Management > Field Selection Control | L5 | trm03 p.221 | loio `0d09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0d09da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The field selection control allows you to control fields in certain applications in Limit Management and Reporting according to the field status.

Before you can stipulate the field status of a certain field, you first need to make an entry in the maintenance table in Customizing for each application, limit type, and mode.

**Activities**

In Customizing, choose Limit Management Field Selection Control .

The system displays the Change View "Maintenance View for Field Selection Control for Limit Types” screen.

To enter the following data, choose New Entries:

|Limit type (LT)|An entry in the field selection control table applies to a certain limit type.|
|---|---|
|Program name|The settings apply to a particular application. For the following programs, you can control fields by their status: RFTBLE01 (Overview of Utilizations - Selection Using Direct Characteristics) RFTBLE02 (Overview of Utilizations - Selection Using All Characteristics) RFTBLL01 (Overview of Limits) SAPLTBL1 (Limit Maintenance: Overview) SAPLTBL1 (Limit Maintenance: Details; screen 1010) SAPLTBL10 (Report: Utilizations - Single Records) SAPLTBL10 (Report: Utilizations - Grouping Level 1) SAPLTBL10 (Report: Utilizations - Grouping Level 2) |
|Table name|Name of the table containing the field you want to control.|
|Field name|Name of the field you want to control. (The field is entered automatically when you select the table/field.)|
|Mode description|The mode specifies whether the field is set up for 1 (Display Mode) or 2 (Maintenance Mode). If you want to control the field status for both modes, you need to define them both separately.|
|Possible field modes|Undefined = Default setting Optional entry = Field is ready for data entry Required entry = Field is ready for data entry and must be filled|


Hide = Field is hidden in the application


If you define the field selection control for a report by specifying a program name, then the settings you make here apply only if the report is run just for this particular limit type.

Choose to save your settings.

##### Relative Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Relative Limits | L4 | trm03 p.222 | loio `7499d65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7499d65378024308e10000000a174cb4.html?locale=en-US)

**Definition**

Relative limits define the minimum or maximum limit utilization as a percentage of a reference limit, such as the book value of a portfolio of transactions.

**Use**

When you create a premium reserve fund, you may want to restrict the portion of certain product categories in the fund. The portion of each product category in the fund is often restricted in reference to the total investment volume or to certain asset classes. For example, an insurance company can insist that securities comprise a maximum of 30 percent of a portfolio, and that fixed-term deposits represent at least 10 of the portfolio.

In addition to internal limits, there are also legal limits, such as those governing insurance companies' stock investments. Internal limits are usually defined by market values, whereas legal limits are based on book values.

You use relative limits to map these requirements. To create relative limits, on the SAP Easy Access screen choose Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Master Data Limits Limits

. You can also use this transaction to define absolute limits, and to create absolute limits for relative limits.


To check whether any limits have been exceeded, you use the extended reporting for limits .

**Structure**

Relative limits are defined as the quotient of the limit utilization and a limit reference. The limit utilization specifies the investments that are to be subject to a limit, and the limit reference is the associated total investment volume. You define both these figures by specifying a portfolio hierarchy node and a key figure.

The nodes in the portfolio hierarchies are the portfolios that are to be compared. You usually define one portfolio hierarchy for the limit utilization, and one for the limit reference. You can use all the NPVs and book values that you assigned to your portfolio hierarchy as key figures. You can compare the same key figures for different portfolios or different key figures for the same portfolio.

You can define a lower limit and an upper limit for the relative limits. You can also define only one of these limits (either the lower limit or the upper limit). You enter these values as percentages.

###### Extended Reporting for Limits

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > Relative Limits > Extended Reporting for Limits | L5 | trm03 p.222 | loio `530533531ee1e347e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/530533531ee1e347e10000000a441470.html?locale=en-US)

Use

You use this function to calculate the utilizations of absolute and relative limits and to display them. In this function, the system analyzes data records stored in the Results Database (RDB), and displays the utilizations of the limits for each data record. It selects all data records containing limits that have been exceeded.

You can branch from each row in the report to the single transaction display. This means that, for each key date, you can check the book values and NPVs of the transactions, the utilizations of the limits, and the limit ratio.

**Integration**

The system calculates the utilizations based on the analysis that you start in the Market Risk Analyzer, Portfolio Analyzer, and Accounting Analyzer components and the results of which are stored in the Results Database (RDB).

**Prerequisites**

You have calculated net present values and book values for selected portfolio hierarchy nodes, and you have stored the results in the Results Database. For more information, see Evaluations Using the Results Database.

You have created relative and absolute limits. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Master Data Limits Limits .

**Note:**

If you define a critical limit utilization, it must be less than 100% and it must not be negative.

When defining the limits (transaction KLREL_LIMIT_ASS), you can also define lower and upper limits with a negative sign. You can do this, for example, to take losses into account in your reporting.

The lower limit must be less than the upper limit.

**Features**

The system calculates a utilization indicator, which is defined as follows:

Utilization Indicator = max(Absolute UI; Relative UI)

where absolute UI and relative UI are defined as follows:

[figure TRM03-F289 - where the key figures are absolute numbers. The Relative UI key figure is calculated using the same formula, but the values used are percentages.]

where the key figures are absolute numbers. The Relative UI key figure is calculated using the same formula, but the values used are percentages.

The utilization indicator is defined so that it provides values that can be interpreted, regardless of how the limits are defined. If the limits specified for the absolute and relative limits have not been reached, the value of the utilization indicator is between 0 and 100 percent. If a limit has been reached, the value is 100 percent. If the limits have been exceeded, the value is greater than 100 percent.

If you want to define a lower limit as well as an upper limit, the value of the utilization indicator is 0 percent if the limit utilization is exactly in the middle of the range defined by the lower and upper limit.

**Activities**

- 1. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Credit Risk Analyzer Information System Reporting Limits Extended Limit Reporting (transaction KLREL_LIMIT).

The system displays a selection screen.

- 2. Specify the limit IDs and the validity period for which you want to display the utilization of the limits. Choose an evaluation type, the display currency, and the layout ID for displaying the data from the RDB.

You can also specify an ALV layout.

- 3. Choose .



The system reads the limit utilizations and limit references from the RDB, converts them to the evaluation currency, and calculates the relative limits and the value of the utilization indicator. It then displays the data records that were selected in the navigation structure in the left-hand part of the screen.

Action

To display the data, choose a row in the navigation structure.

On the right-hand side of the screen, the system displays a list containing the following information:

Utilization (traffic light)

Critical limit utilization has been defined:

: 0 < utilization < critical limit utilization


: critical limit utilization ≤ utilization < 100


: utilization ≥ 100


Critical limit utilization has not been defined:

: utilization = 0


: 0 < utilization < 100


: utilization ≥ 100


Limit ID and valid-from date

Display currency

Calculation status

The calculation status is (green) if no errors occurred during the calculation.

The calculation status is (red) if errors occurred during the calculation. The system writes a log of all errors and warnings.


Limit utilization (portfolio node, key figure, and amount)

The system displays all currency amounts in the display currency that you have specified in the selection screen.

Limit reference amount (portfolio node, key figure, and amount)

Limit ratio (lower and upper limits for the limit utilization for relative limits)

Upper and lower limit for absolute limits

Relative limit in percentage

Utilization indicator in percentage

To display the results at single-transaction level, double-click a row in the right-hand part of the screen.

The system branches to the Analyzer Information System and displays the values for the selected portfolio hierarchy node.

##### SAP Query

> **Path:** Treasury and Risk Management > Risk Management > Credit Risk Analyzer > SAP Query | L4 | trm03 p.225 | loio `2d09da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2d09da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

You can use the SAP Query tool to define reports without having to carry out any programming. You can also include your own data.

**Use**

In this component, you can use the following queries:

Overview of Limits

Overview of Limit Utilizations

You can use the queries offered here as examples. Alternatively, you can use these reports: Displaying an Overview of Limits and Displaying Utilizations. You can copy these using the standard SAP Query tool by choosing Tools SAP Query and then use them as a template for the queries and infosets you define yourself.

**Integration**

The SAP Query tool is a standard tool. You can view the documentation about the general usage of SAP queries in Query.

