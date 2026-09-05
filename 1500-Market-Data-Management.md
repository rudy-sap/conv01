# Market Data Management - SAP TRM Knowledge Base (branch split)

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

### Market Data Management

> **Path:** Treasury and Risk Management > Market Data Management | L2 | trm11 p.2 | loio `430eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/430eda531198434de10000000a174cb4.html?locale=en-US)

The following sections describe the tools for transferring market data. Market data can be transferred to the system from a file interface or via realtime datafeed. You can use the function for market data transfer from spreadsheets. In addition to the back end functions, you can also use the SAP Fiori launchpad to access the Import Market Data app for the data transfer, and other apps for the manual entry.

The following market data are now available via different tools:

|Market Data|Manual Entry (Back End)|Manual Entry (App)|Datafeed (Back End)|Datafeed (SAP Market Rates Management Service)|Market Data Transfer from Spreadsheet (Back End)|Import Market Data (App)|Import Foreign Exchange Rates (App)|
|---|---|---|---|---|---|---|---|
|Foreign Exchange Rates|X| |X|X|X|X|X|
|Security Prices|X| |X| |X|X| |
|Interest Rates|X| |X|X|X|X| |
|Basis Spreads|X| |X| |X|X| |
|Credit Spreads|X| |X| |X|X| |
|Forex Swap Rates|X| |X| |X|X| |
|Index Value|X| |X| |X| | |
|Price Index Value|X| | | | | | |
|Correlations|X| | | |X| | |
|Commodity Price| | |X| |X| | |
|Price for Derivative Contract Specification| | |X| |X| | |
|Beta Factor|X| | | |X| | |
|Exchange Rate Volatilities|X| |X| |X|X| |
|Securities Volatilities|X| |X| |X|X| |


|Market Data|Manual Entry (Back End)|Manual Entry (App)|Datafeed (Back End)|Datafeed (SAP Market Rates Management Service)|Market Data Transfer from Spreadsheet (Back End)|Import Market Data (App)|Import Foreign Exchange Rates (App)|
|---|---|---|---|---|---|---|---|
|Interest Rate Volatilities|X| |X| |X|X| |
|Index Volatilities|X| |X| |X| | |
|Volatilities for Risk Factor|X| | | | | | |
|Volatilities for Commodity Price|X| |X| |X| | |
|Volatilities with Moneyness: Interest Rate|X| | | | | | |
|Volatilities with Moneyness: FX Rate|X| | | | | | |
|Volatilities with Moneyness: Security Prices|X| | | | | | |
|Volatilities with Moneyness: Security Index|X| | | | | | |
|Volatilities with Moneyness: Commodity Price|X| | | | | | |
|General Volatility| | |X| | | | |


The following tools are vailable for transferring market data to the system:

Market data transfer from spreadsheet

The Market data file interface features the following functions:

You can upload a file with external market data, check, and update the operative database tables containing market data.

You can display a list of all actions and errors.

You can retrieve the master data defined in the system for the market data and generate a list of requested market data in notation.

The list can be saved in the form of a file.

Import statistical data.

Datafeed

You can use the datafeed to incorporate current and historic market data into your financial transactions by means of the different SAP Market Rates Management services or by means of a different interface.

The functions provided by the Real-time datafeed interface allow you to work effectively and efficiently with market data. You need an external interface program supplied by your datafeed provider that delivers the market data to the system in a suitable form.

The following functions are available:

Market data/error buffer management

The system can list and analyze current market data and the most recent errors that occurred during data transfer or delivery.

External data transfer

You can transfer current and historical market data in datafeed notation using a report.

User log

Each access to the datafeed interface is documented in the user log. You can display, print out, or archive this user log. You can also download it as an ASCII file.

Current settings This function describes Customizing activities that you carry out outside the IMG (Implementation Guide).

Import Market Data

You can use this SAP Fiori app in your launchpad to import market data. The following functions are now available:

Download templates

There are many template formats to select. You can choose to download a single file with all the market data categories that you select, or you can download separate files that are category-specific.

Check the data validation results

The system checks the data correctness after you upload your files with the most up-to-date market data. Entries with errors and warnings are displayed, along with all the correct entries.

Import the validated data into the system

The correct data and data with warnings are imported.

Manual Market Data Entry

You can use the apps in your launchpad to enter market data manually.

The Currency Converter function is also available for you to convert amount in one currency to another.

#### Currency Converter

> **Path:** Treasury and Risk Management > Market Data Management > Currency Converter | L3 | trm11 p.4 | loio `a3a8618b2de9499d854a07b662c4d997` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a3a8618b2de9499d854a07b662c4d997.html?locale=en-US)

With this app, you convert a specific amount from one currency to another on a specific date and according to a specific rate type.

**Key Features**

Convert an amount from one currency to another according to a date and exchange rate type

Save a variant for your preferred currency settings

**Supported Device Types**

Desktop

#### Import Market Data (1 of 2)

> **Path:** Treasury and Risk Management > Market Data Management > Import Market Data | L3 | trm11 p.5 | loio `8db4431d159443adbed8fc5ed47ae6d4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8db4431d159443adbed8fc5ed47ae6d4.html?locale=en-US)

With this app, you can import market data, such as FX rates, security prices, interest rates, basis spreads, credit spreads, FX swap rates, FX volatilities, and security factors, from a file into the system. Various templates are available that you can download. You can upload files with a maximum of 1000 data records.

**Key Features**

Download the template in a single file or separate files that are category-specific.

**Note:**

For templates without data, you need to enter both master data and transactional data in the template. Make sure to enter the following category number to the corresponding market data category field:

|Category Number|Market Data Category|
|---|---|
|01|Exchange Rates|
|02|Security Prices|
|03|Interest Rates|
|09|Basis Spreads|
|10|Credit Spreads|
|21|Forex Swap Rates|
|31|Exchange Rate Volatilities|
|41|Securities Factors|


For templates in a single generic file, the table header fields have different meanings, depending on the market data category that you select. For more details, see Template Description.

Upload your files with the most up-to-date market data

Check the data validation results, for example, errors and warnings

**Note:**

Decimals are separated by dots. If you use comma to separate decimal points, the system will take it as invalid data.

Import the correct data and data with warnings into the system

In addition, the app supports the following technical features and options:

Send emails

You can send an email with a URL that enables the recipients to check the app with exactly the same selection criteria as you are currently using.

Save as tile

You can create a tile that uses the current selection criteria as default settings.

**IAM Information**

The authorization for the following authorization objects is checked:

Authorization object S_TCODE Transaction Code Check at Transaction Start to check authorization for transaction F2610.

Authorization object S_TABU_NAM Table Access by Generic Standard Tools

The authorization object contains the following fields and values:

ACTVT (Activity)

- 02 Change

- 03 Display


TABLE (Table Name)

AT15

ATCVO

T056P

T056R

TCURC

TCURR

V_AT15

V_ATCVO

V_T056P

V_TCURF

With the authorization object Authorization to Maintain Exchange Rates (F_CUREXRAT) you can give authorization to monitor, change, create, and delete foreign exchange rates.

The authorization object contains the following fields and values:

ACTVT (Activity)

- 01 Create or generate

- 02 Change

- 03 Display


06 Delete

F4 Read authorization in input help

KURST Exchange Rate Type

FCURR From Currency

TCURR To Currency

**Supported Device Types**

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Template Description (1 of 2)

> **Path:** Treasury and Risk Management > Market Data Management > Import Market Data > Template Description | L4 | trm11 p.7 | loio `e19a4ce595a9438aabb4f9fbf22d4c57` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e19a4ce595a9438aabb4f9fbf22d4c57.html?locale=en-US)

Description on the generic template of the Import Market Data app.

For templates in a single generic file, the fields have different meanings, depending on the market data category that you select. You can follow the descriptions below:

| |Market|Key 1|Key 2|Property|Effective|Time|Market|Security|From|To|P|
|---|---|---|---|---|---|---|---|---|---|---|---|
| |Data| | | |Date| |Data|Currency|Factor|Factor|Q|
| |Category| | | | | |Value| | | | |
|Exchange|Enter the|Enter the|Enter the|Enter the|Enter the|This|Enter the|This field|Enter|Enter|E|
|Rates|Category|From|To|Exchange|Effective|field is|Exchange|is left|the|theTo|t|
| |Number|Currency|Currency|Rate Type|Date for|left|Rate for|blank.|From|Ratio|Q|
| |01 for|for this|for this|for this|this column.|blank.|this| |Ratio|for this|f|
| |this column.|column.|column.|column.|Make sure the number| |column.| |for this column.|column.|c Y|
| | | | | |format for| | | | | |t|
| | | | | |the cells is| | | | | |f|
| | | | | |set to Date.| | | | | |i|
| | | | | |If the| | | | | |q|
| | | | | |number| | | | | |a|
| | | | | |format is| | | | | |e|
| | | | | |set to| | | | | |d|
| | | | | |General,| | | | | |q|
| | | | | |only the| | | | | | |
| | | | | |date format| | | | | | |
| | | | | |YYYYMMDD| | | | | | |
| | | | | |can be| | | | | | |
| | | | | |imported.| | | | | | |


| |Market Data Category|Key 1|Key 2|Property|Effective Date|Time|Market Data Value|Security Currency|From Factor|To Factor|P Q |
|---|---|---|---|---|---|---|---|---|---|---|---|
|Security Prices|Enter the Category Number 02 for this column.|Enter the Security ID for this column.|This field is left blank.|This field is left blank.|Enter the Effective Date for this column. Make sure the number format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.|This field is left blank.|Enter the Security Price.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|
|Interest Rates|Enter the Category Number 03 for this column.|Enter the Reference Interest Rate for this column.|This field is left blank.|This field is left blank.|Enter the Effective Date for this column. Make sure the number format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.|This field is left blank.|Enter the Interest Rate.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|
|Basis Spreads|Enter the Category Number 09 for this column.|Enter the Basis Spreads for this column.|This field is left blank.|Enter the Quotation Type for this column. You need to enter 1 for middle rate, 2 for bid and 3 for ask.|Enter the Effective Date for this column. Make sure the number format for the cells is set to Date. If the number format is set to|The field is left blank.|Enter the Basis Spread for this column.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|


| |Market Data Category|Key 1|Key 2|Property|Effective Date|Time|Market Data Value|Security Currency|From Factor|To Factor|P Q |
|---|---|---|---|---|---|---|---|---|---|---|---|
| | | | | |General, only the date format YYYYMMDD can be imported.| | | | | | |
|Credit Spreads|Enter the Category Number 10 for this column.|Enter the Reference Entity for this column.|Enter the Credit Spread ID for this column.|Enter the Quotation Type. You need to enter 1 for middle rate, 2 for bid and 3 for ask.|Enter the Effective Date for this column. Make sure the number format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.|This field is left blank.|Enter the Credit Spread for this column.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|
|Forex Swap Rates|Enter the Category Number 21 for this column.|Enter the From Currency for this column.|Enter the To Currency for this column.|Enter the Exchange Rate Type for this column.|Enter the Effective Date for this column. Make sure the number format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.|This field is left blank.|Enter the Swap Rate for this column.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|
|Implied Volatilities|Enter the Category Number 30 for this column.|Enter the Volatility Name for this column.|Enter the Volatility Profile for this column.|Enter the Volatility Type for this column.|Enter the Effective Date for this column. Make sure the number|The field is left blank.|Enter the Volatility for this column.|The field is left blank.|The field is left blank.|The field is left blank.|T i b|


| |Market Data Category|Key 1|Key 2|Property|Effective Date|Time|Market Data Value|Security Currency|From Factor|To Factor|P Q |
|---|---|---|---|---|---|---|---|---|---|---|---|
| | | | | |format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.| | | | | | |
|Exchange Rate Volatilities|Enter the Category Number 31 for this column.|Enter the From Currency for this column.|Enter the To Currency for this column.|Enter the Volatility Type for this column.|Enter the Effective Date for this column. Make sure the number format for the cells is set to "Date". If the number format is set to "General", only the date format YYYYMMDD can be imported. Make sure the number format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.|The field is left blank.|This field shows the Volatility for this column.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|


| |Market Data Category|Key 1|Key 2|Property|Effective Date|Time|Market Data Value|Security Currency|From Factor|To Factor|P Q |
|---|---|---|---|---|---|---|---|---|---|---|---|
|Security Volatilities|Enter the Category Number 32 for this column.|Enter the security class ID for the Class column.|The field is left blank.|Enter the Volatility Type for this column.|Enter the Effective Date for this column. Make sure the number format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.|Enter the Effective Term for this column.|Enter the Volatility for this column.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|
|Interest Rate Volatilities|Enter the Category Number 33 for this column.|Enter the ID for reference interest for this column.|The field is left blank.|Enter the Volatility Type for this column.|Enter the Effective Date for this column. Make sure the number format for the cells is set to Date. If the number format is set to General, only the date format YYYYMMDD can be imported.|Enter the Effective Term for this column.|Enter the Volatility for this column.|This field is left blank.|This field is left blank.|This field is left blank.|T i b|


| |Market|Key 1|Key 2|Property|Effective|Time|Market|Security|From|To|P|
|---|---|---|---|---|---|---|---|---|---|---|---|
| |Data| | | |Date| |Data|Currency|Factor|Factor|Q|
| |Category| | | | | |Value| | | | |
|Securities|Enter the|Enter the|Enter the|This field|Enter the|The field|This field|This field|This|This|T|
|Factors|Category|Security|Factor|is left|Effective|is left|shows the|is left|field is|field is|i|
| |Number|ID for this|Types for|blank.|Date for|blank.|Securities|blank.|left|left|b|
| |41 for|column.|this| |this column.| |Factor for| |blank.|blank.| |
| |this column.| |column.| |Make sure the number| |this column.| | | | |
| | | | | |format for| | | | | | |
| | | | | |the cells is| | | | | | |
| | | | | |set to Date.| | | | | | |
| | | | | |If the| | | | | | |
| | | | | |number| | | | | | |
| | | | | |format is| | | | | | |
| | | | | |set to| | | | | | |
| | | | | |General,| | | | | | |
| | | | | |only the| | | | | | |
| | | | | |date format| | | | | | |
| | | | | |YYYYMMDD| | | | | | |
| | | | | |can be| | | | | | |
| | | | | |imported.| | | | | | |


**Related Information**

Import Market Data

#### Import Foreign Exchange Rates

> **Path:** Treasury and Risk Management > Market Data Management > Import Foreign Exchange Rates | L3 | trm11 p.12 | loio `103f7a57015b8a1be10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/103f7a57015b8a1be10000000a44147b.html?locale=en-US)

App ID: F2092

**Use**

With this app, you can import foreign exchange rates from a file into the system. A template is available that you can download. You can upload files with a maximum of 1000 data records.

**Key Features**

Download the template and edit it with the most up-to-date foreign exchange rates data.

For more information, see also Template Description

Upload the file

**Caution:**

The Fixed Value column must be 01 in your file.

Check the data correctness, for example, errors and warnings

Import the correct data and warning data into the system

In addition, the app supports the following technical features and options:

Send emails

You can send an email with a URL that enables the recipients to check the app with exactly the same selection criteria as you are currently using.

Save as tile

You can create a tile that uses the current selection criteria as default settings.

**Prerequisites**

If you enter an FX rate in the market data table, you must assign an exchange rate type.

This means that you can enter different exchange rates for a currency pair and a validity date, whereby the exchange rates are distinguished by the exchange rate type.

You must define the required exchange rate types in the Check Rate Types Customizing activity.

**IAM Information**

The authorization for the following authorization objects is checked:

Authorization object S_TCODE Transaction Code Check at Transaction Start to check authorization for transaction F3616.

Authorization object S_TABU_NAM Table Access by Generic Standard Tools

The authorization object contains the following fields and values:

ACTVT (Activity)

- 02 Change

- 03 Display


TABLE (Table Name)

V_TCURF

V_TCURR

With the authorization object Authorization to Maintain Exchange Rates (F_CUREXRAT) you can give authorization to monitor, change, create, and delete foreign exchange rates.

The authorization object contains the following fields and values:

ACTVT (Activity)

- 01 Create or generate

- 02 Change

- 03 Display


06 Delete

F4 Read authorization in input help

KURST Exchange Rate Type

FCURR From Currency

TCURR To Currency

**Supported Device Types**

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Template Description (2 of 2)

> **Path:** Treasury and Risk Management > Market Data Management > Import Foreign Exchange Rates > Template Description | L4 | trm11 p.14 | loio `d0006e8b046f4758a59384a88259d1cd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d0006e8b046f4758a59384a88259d1cd.html?locale=en-US)

A detailed description on the generic template of the Import Foreign Exchange Rates app.

For templates in a single generic file, the fields have different meanings, depending on the market data category that you select. You can follow the descriptions below:

|Market|From|To|ERTy|Effective|Value|Exchange|Security|From|To|Price|Eff|
|---|---|---|---|---|---|---|---|---|---|---|---|
|Data| | | |Date|Time|Rate|Quotation|Factor|Factor|Quotation|Te|
|Category| | | | | | |Currency| | | | |
|Enter the|Enter the|Enter the|Enter the|Enter the|obsolete|Enter the|obsolete|Enter|Enter|Enter|o|
|category|From|To|Exchange|Effective| |Exchange| |theFrom|theTo|thePrice| |
|number|Currency|Currency|Rate|Date for| |Rate for| |Ratio|Ratio|Quotation| |
|01 for|for this|for this|Type for|this column.| |this| |for this|for this|for this| |
|this column.|column.|column.|this column.|Only the format| |column.| |column.|column.|column. You need| |
| | | | |YYYYMMDD| | | | | |to enter X| |
| | | | |is| | | | | |for| |
| | | | |supported| | | | | |indirect| |
| | | | |currently.| | | | | |quotation,| |
| | | | | | | | | | |and leave| |
| | | | | | | | | | |empty for| |
| | | | | | | | | | |direct| |
| | | | | | | | | | |quotation.| |


The system shows the message of data validation after you upload this file.

##### Price Quotation

> **Path:** Treasury and Risk Management > Market Data Management > Import Foreign Exchange Rates > Price Quotation | L4 | trm11 p.14 | loio `34b27457a9aec86be10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/34b27457a9aec86be10000000a4450e5.html?locale=en-US)

The direct or indirect quotation method for exchange rates.

**Definition**

Direct quotation is where the cost of one unit of foreign currency is given in units of local currency, whereas indirect quotation is where the cost of one unit of local currency is given in units of foreign currency.

**Use**

This enables you to manage exchange rates for each currency pair using direct or indirect quotation. The type of quotation used is dependent on the market standard. You can define the type of quotation per client and currency pair (business transaction).

**Example: Example**

Your local currency is EUR:

Direct exchange rate: 1USD = 0.92819 EUR

Indirect exchange rate: 1EUR = 1.08238 USD

#### File Interfaces

> **Path:** Treasury and Risk Management > Market Data Management > File Interfaces | L3 | trm11 p.15 | loio `fc21d553088f4308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fc21d553088f4308e10000000a174cb4.html?locale=en-US)

Refer to:

Rates and prices

Statistical data

##### Rates and Prices

> **Path:** Treasury and Risk Management > Market Data Management > File Interfaces > Rates and Prices | L4 | trm11 p.15 | loio `4b0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b0eda531198434de10000000a174cb4.html?locale=en-US)

The Import market data function allows you to import the market data you need to the system.

**Note:**

Make sure you have the correct market data file format.

To call up a selection list in which you can specify the market data you require, you use the Generate requirements list function. You can save the list in file format.

See also:

Importing market data

Generate requirements list

###### Import Market Data (2 of 2)

> **Path:** Treasury and Risk Management > Market Data Management > File Interfaces > Rates and Prices > Import Market Data | L5 | trm11 p.15 | loio `ff21d553088f4308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ff21d553088f4308e10000000a174cb4.html?locale=en-US)

Choose Tools Market Data File Rates and Prices Import .

The screen entitled File Interface: Import Market Data appears.

Under the heading File in the Name field, enter the directory path and the file name of the market data file you want to import.

If you check the box marked Test run under the heading Other, the system will only run a simulation of the market data import.

Choose Program Execute . The system now imports the market data.

###### Generate Requirements List

> **Path:** Treasury and Risk Management > Market Data Management > File Interfaces > Rates and Prices > Generate Requirements List | L5 | trm11 p.16 | loio `261e32532adce547e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/261e32532adce547e10000000a441470.html?locale=en-US)

**Context**

You use this program to generate a requirements list.

**Procedure**

- 1. Choose Market Data Management File Interfaces Rates and Prices Generate Requirements List . The File Interface: Generate Requirements List screen appears.
- 2. In the File Name field in the Output area, enter the directory path and the file name of the file in which you want the requirements list to be output. The directory path that you enter here must already exist on the application server.
- 3. You can restrict the requirements list to be generated by selecting the following instrument classes:

Currencies

Securities

Interest Rates

Indexes

Non-CPE Commodities

CPE Commodities

OTC Forwards Commodities

Basis Spreads

Credit Spreads

Derivative Contract Specific.

- 4. In the Selection area, you can restrict the requirements list further by entering master data and instrument properties.
- 5. Choose Program Execute .


The system displays a selection list in which you select the requested market data by setting the indicator in the OK column.

##### Importing Statistical Data

> **Path:** Treasury and Risk Management > Market Data Management > File Interfaces > Importing Statistical Data | L4 | trm11 p.16 | loio `510eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/510eda531198434de10000000a174cb4.html?locale=en-US)

Procedure

- 1. Choose Tools File Interfaces Import Statistical Data .
- 2. Make the following entries on the selection screen:


Specify the file name for the data you wish to import.

If you want to import the data from a diskette or hard disk, select the PC upload field.

If you want to simulate a data import run, set the Test Run indicator.

- 3. To start the import procedure, choose Execute.

##### Market Data Transfer from Spreadsheet

> **Path:** Treasury and Risk Management > Market Data Management > File Interfaces > Market Data Transfer from Spreadsheet | L4 | trm11 p.17 | loio `f921d553088f4308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f921d553088f4308e10000000a174cb4.html?locale=en-US)

**Use**

This function allows you to call up market data directly in the system from a spreadsheet and transfer the data.

**Prerequisites**

A spreadsheet program must be installed on your PC.

This function is exclusively designed for the Enjoy screen size of 27 lines and 120 columns.

Read the report documentation Importing Market Data via the File Interface (RFTBFF00) and Output of the Requirements List (RFTBFF01). The requirements regarding field length, field meaning, and so on are also valid here.

**Features**

You can import existing market data files.

**Note:**

You can transfer a maximum of 1000 rates and prices to the system at the same time via the spreadsheet. If you wish to transfer more rates and prices, you should use the file interface or datafeed.

You can create new files. The master data that has been defined in the system is transferred as the table framework so that only the values still have to be entered.

**Activities**

- 1. Choose Treasury and Risk Management Transaction Manager Tools Market Data Spreadsheet
- 2. Press the Spreadsheet button that controls the interface parameters of the report.

Application that is to be started: Use the F4-Help to choose the spreadsheet that you wish to use. (The spreadsheet must support the Table category).

Document template (WEB repository): You enter a template here that is copied from the WEB repository to the current document when you create a new spreadsheet.

First and second macro to be run: Specify the macros that are called up to transfer the table information in the work file of your spreadsheet. The first macro transfers data back into the system (TableBackToR3). The second macro fetches the data from the system. (FillTableFromR3).

- 3. If you wish to import an existing file, then enter its name and path where you can find it.


**Note:**

SAP delivers an Excel template with the relevant macros. Only change the standard macro names if you wish to create your own template with its own macros and wish to use your own macro names.

When you import an existing file, the spreadsheet is opened. Use the Import market data function to load data into the system.

- 4. If you wish to create a new file, you can specify the market data you wish to enter under Market data selection for new creation. The table is then preconfigured so that you can enter the values for all defined characteristics of this market data.

Switch to the Spreadsheet tab page.

Choose Create to enter new files and then enter the data. Use the Import market data function to load data into the system.

- 5.

#### Datafeed

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed | L3 | trm11 p.18 | loio `4f3adadc862e2e4fe10000000a42189e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f3adadc862e2e4fe10000000a42189e.html?locale=en-US)

**Use**

You can use the datafeed to incorporate current and historic market data into your financial transactions by means of the different SAP Market Rates Management services or by means of a different interface.

Once the file has been uploaded, the translation tables are used to convert the formats of external market data into systeminternal formats. You have the option of calling up market data either daily (with a scheduled batch job) or continuously (in real time), and then the option of writing the data to the market data tables.

Market data that is uploaded from Microsoft Excel files with a valid, readable format can be written directly (without conversion) to the market data tables. For more information, see the documentation in transaction TBEXN.

In Customizing, you can specify that selected market data is stored in the market data buffer and not written to the market data tables.

The following market data classes are supported:

Currency rates (exchange rates)

Security prices

Reference interest rates

Indexes

Forex swap rates (forwards)

Derivative contract specifications

Commodity prices (daily basis or time basis)

Basis spreads

Credit spreads

Exchange rate volatilities

Security volatilities

Index volatilities

Interest rate volatilities

Commodity price volatilities

**Set Up**

Before you can use the datafeed, you need to fulfill the following prerequisites depending on the interface you want to use:

Market Data Service - SAP Market Rates Management

- 1. Subscribe to one of the following Market Rates Management service packages and create a service instance and service key. Once you do this, you will get a service URL, a client ID, and a client secret that you need in order to call the service from your system.

SAP Market Rates Management - Trial Service

This is a free service that can be used only for non-productive usage and testing. It provides currency exchange rates from the European Central Bank.

For detailed information about the configuration, see SAP Market Rates Management.

SAP Market Rates Management - Refinitiv data option

This is a paid service that is built for productive usage. It provides market data from Refinitiv, an external data provider.

For detailed information about the configuration, see SAP Market Rates Management, Refinitiv data option.

SAP Market Rates Management - Bring Your Own Rates data option

This service can be used to import your own data that you have procured or licensed directly with data providers. As a consumer, you will upload and then download your own market rates by using the upload and download APIs provided by the SAP Market Rates Management service.

For detailed information about the configuration, see SAP Market Rates Management, Bring Your Own Rates data option.

- 2. Make the following configurations to set up a communication arrangement for the Market Rates Management service in your system for the purpose of fetching the market data:


**Note:**

This step can be performed only after you have received the client credential information and configured a client for the system you want to connect to the service.

- a. Set up the base entity for the consumption of the service in the Customizing activity Define Datafeed Name under Financial Supply Chain Management Treasury and Risk Management Basic Functions Market Data


Management Datafeed .

- b. Set up an RFC destination to access the SAP BTP. You do this in Customizing under Datafeed Technical Settings RFC Settings for External Partner Program Define RFC Destination .


**Note:**

For more information about the configuration of the datafeed, see SAP Note 2431370 .

Please make the following settings:

Connection Type: G - HTTP Connection to External Server

Technical Settings - Target System Settings

Host: sap-icbs.authentication.sap.hana.ondemand.com

Port: 443

Path Prefix: /oauth/token

Logon and Security

Logon with User

Select the Basic Authentication radio button and maintain your client credential information that you received.

Logon with Ticket

Select the Do Not Send Logon Ticket radio button.

Security Options

SSL: Select the Active radio button.

SSL Certificate: Choose DEFAULT SSL Client (Standard).

**Note:**

Use transaction SM59 to test the connection to SAP BTP.

It might be necessary to import the respective SSL certificates into your system using transaction STRUST. Depending on your system setup, you might need to enter a proxy configuration in transaction SM59. To do so, go to Extras HTTP Proxy Configuration .

c. Assign the RFC connection to your defined datafeed in the Customizing activity Assign Datafeed RFC Destination under Datafeed Technical Settings RFC Settings for External Partner Program .

Use the following parameters:

Data Provider: Your Datafeed Name

Operating Mode: Synchronous

Program: TB_DATAFEED_HCP_ACCESS

RFC Destination: Name of your RFC Destination

RFC Destination (Backup): NONE

Universal Resource Indicator: In the case of the Market Rates Management trial service or productive service: <ratesURL from service key>/marketData.

In the case of the Bring Your Own Rates service: <downloadURL from serviceKey>/downloadMarketData>

d. After you have made the technical settings, you can then add a data source to your datafeed under Datafeed Translation Table Define Data Sources for Datafeed .

Please define a data source similar to the one below:

**Example:**

Data Source: ECB

Description:European Central Bank

- 3. Assign the system notations for the specific market data to the corresponding data provider notations in the translation tables using the following Customizing activities available in Customizing for Treasury and Risk Management under


Basic Functions Market Data Management Datafeed Translation Table :

Define Currencies

**Note:**

For each currency pair, enter the following parameters:

Instrument Class: 01 - Currencies

Crcy Pair: <From-Currency>, <To-Currency>

Rate Type: <Rate Type>

Select the Syst. Request radio button.

Set the Save Market Data Permanently in System indicator.

Max. Deviation in Percent

Data Provider: <Your Datafeed Name>

Instrument: <From-Currency>~<To-Currency>: CUR

- Example 1: EUR~CHF:CUR

- Example 2: EUR~USD:CUR


Property: C

Explanation - Optional entry

Currency Settings:

External :Datafeed: 1:1

In addition, you can activate the Date Deviation Check, the Rate Deviation Check, and tighten the External Ratio Check. Once activated, these checks take place during market data requests in the

Request Current Market Data - Datafeed app (app ID: TBD4). When you request historical market data using the Request Historical Market Data - Datafeed app (app ID: TBDJ), only the rate deviation check and the external ratio check are performed. You can also control whether date deviations or rate deviations trigger a warning or an error message.

- a. You can activate the date deviation check for a currency pair. If this check is active and the currency data retrieved is older than the maximum deviation defined in the Max. Deviation in Days field, you will receive a warning message. To fix this issue, retrieve the latest data from your data provider.
- b. You can activate the rate deviation check for a currency pair so that a warning or error is issued in the case of strong deviations in exchange rates. If the last imported rate differs from the previous rate entered in the currencies table by more than the percentage entered in the Max. Rate Deviation in % field, a warning message is issued.
- c. You can set the error severity for the check between your system ratio and the external conversion ratio using the checkbox Ratio Must Match Data Provider in the Currency Settings. If activated, a ratio mismatch between the data provider and your system triggers a blocking error.


In the Customizing activity Change Message Control, you can change the message type of messages from Warning (default setting) to Errors.

For the date deviation check, you can change the message type of the following message from Warning (default setting) to Errors:

Application area: FTDF

- Message number: 000

For the rate deviation check, you can change the message type of the following message from Warning (default setting) to Errors:

Application area: FTDF

- Message number: 001


Define Securities

Define Reference Interest Rates

Define Basis Spreads

Define Credit Spreads

Define Indexes

Define FX Swap Rates

Define Currency Volatilities

Define Security Volatilities

Define Interest Rate Volatilities

Define Index Volatilities

Define General Volatilities

The communication arrangement should now be ready to be consumed.

- 4. Now you can run the following apps with the respective SAP Market Rates Management service:


Request Current Market Data - Datafeed

Request Historical Market Data - Datafeed

Other Interfaces

You have activated the datafeed functions and made the relevant settings. You make these settings in Customizing for Treasury and Risk Management under Market Data Management or in Customizing for Cash and Liquidity Management under Cash Management Market Data Datafeed .

The RFC connection with the partner system has been set up, and the system platform of your datafeed provider supports the datafeed.

You have made the required settings in Customizing for Treasury and Risk Management under Basic Functions Market Data Management Datafeed .

You have the following RFC authorizations:

Authorization object S_RFC with the field values RFC-TYPE = FUGR, RFC_NAME = TBDF, and ACTVT = 16 (Execute)

For asynchronous calls: authorization object F_T_FBNAME with the field values ACTVT = 01 (Add or Create) and FNMA = TB_DATAFEED_RATE_R

These authorization objects are contained in profile F_DTFEED_ALL.

You need the following authorization groups for the market data tables:

FC32 (Currencies)

FC16 (Interest)

TRZ (Indexes)

FCOO (Currency Volatilities)

TRMK (Interest Volatilities)

Commodities

**Features**

The following functions are provided with the datafeed:

Displaying Market Data

Request Current Market Data - Datafeed

Request Historical Market Data - Datafeed

Setting Up Continuous Market Data Supply

File Upload in Datafeed Notation

User exit for price/rate calculations

For average price/rate calculations or the inversion of prices/rates, for example, the SAP enhancement TRTMDF01 is available. You have access to prices/rates that are stored permanently, and you can calculate new prices/rates if necessary.

Rate/price provision from the Internet

For this, you make the required settings in Customizing for Treasury and Risk Management under Basic Functions Market Data Management Technical Settings Internet Settings for External Partner Program .

**Caution:**

You can use this function only if you use the web server of an SAP-certified partner whose certificate is also valid for Internet access.

##### Displaying Market Data

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Displaying Market Data | L4 | trm11 p.23 | loio `0222d553088f4308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0222d553088f4308e10000000a174cb4.html?locale=en-US)

**Use**

You use the function Display Market Data (TBD3) or program RFTBDF00 to create a list of the last market data that was uploaded as well as statistics concerning any errors that occurred.

**Activities**

- 1. In the area menu, choose Treasury and Risk Management Basic Functions Market Data Management Datafeed Display Market Data .
- 2. Enter your selection data for the market data you wish to display.


- 3. Choose Execute. The system displays a list of the market data and the error statistics.


You can now select market data to display the details.

**More Information**

Datafeed

##### Request Current Market Data - Datafeed

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Request Current Market Data - Datafeed | L4 | trm11 p.24 | loio `0522d553088f4308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0522d553088f4308e10000000a174cb4.html?locale=en-US)

App ID: TBD4

**Use**

With this app, you request current market data. The selected market data is obtained by means of the datafeed interface.

**Key Features**

Request current market data for different market data classes, such as currencies

Update market data (such as currencies and interest rates) in the market data tables

Save a variant with your preferred settings

**Activities**

- 1. Choose the market data classes for which you want to request the current market data.
- 2. In the Market Data Selection area, you can use the following fields to restrict the volume of market data to be read:

- 1st Key Definition

- 2nd Key Definition


Instrument Property

- 3. In the Datafeed area, choose the datafeed provider in the Name field. The Request Mode is already selected.
- 4. In the Output Control area, you can choose a layout and deselect the following indicators, as required:

Output List of Results

If you want to get a results list, check this field.

Save Market Data in System Permanently

If you want to save the market data to produce a price/rate history in the system, set this indicator. In this case, the requested market data is transferred to the price/rate tables of the system.

If you do not set this indictor, market data is transferred only to the market data buffer and to the list display. This type of request is mainly suited for test purposes.

Save Execution Detail Information in Application Log

If you set this indicator, the system writes the details of this report execution in the application log.

- 5. Execute the report.


**Results**

The current market data is imported by the market data provider and stored in the market data table, if desired.

**Note:**

If you have activated one of the following checks for exchange rates in the Customizing activity Define Currencies, these are executed during the import:

Date deviation check for a currency pair.

If this check is active and the currency data retrieved is older than the maximum deviation defined in the Max. Deviation in Days field, you will receive a warning message. To fix this issue, retrieve the latest data from your data provider.

**Note:**

If you have changed the message type to Errors, the message issued is an error message instead.

Rate deviation check for a currency pair so that a warning or error is issued in the case of strong deviations in exchange rates. If the last imported rate differs from the previous rate entered in the currencies table by more than the percentage entered in the Max. Rate Deviation in % field, a warning message is issued.

**Note:**

If you have changed the message type to Errors, the message issued is an error message instead.

Ratio Must Match Data Provider

A ratio mismatch between the data provider and your system triggers a blocking error.

For more information, see also Datafeed.

Review the application log for request details, if available.

**Note:**

Using the Analyze Application Log (transaction SLG1) you can display the log by choosing Object TRM and Subobject UTIL.

Review the output list, if available.

**More Information**

For more information on the datafeed and its settings, see Datafeed.

**Supported Device Types**

Desktop

###### Situation Template: Market Data Request

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Request Current Market Data - Datafeed > Situation Template: Market Data Request | L5 | trm11 p.25 | loio `7317060a415644eb90633f7eedeaaad2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7317060a415644eb90633f7eedeaaad2.html?locale=en-US)

Situation Template ID: FIN_TRM_REQUEST_MARKET_DATA

Situation Scenario ID: FIN_TRM_MD_REQUEST_MSG_MONITOR

**Note:**

To create a situation type based on this template, you need to specify both the scenario ID and the template ID.

**Note:**

For details on configuring this situation template, also see Notification for Job Scheduling.

**Business Value**

As a configuration expert for business processes (SAP business role SAP_BR_BPC_EXPERT), you can use this template for the following situation:

You have created a job using the app Request Current Market Data - Datafeed. This situation template lets you configure notifications if this job is successful, failed or successful with warnings. You can assign responsibility by teams.

**Default Settings**

The template comes with predefined settings. For the settings that aren't self-explanatory, you can find additional information in the following sections. For generic information about how to configure situations based on this template, refer to the documentation of the Manage Situation Types - Extended app with which you can display and use the template.

Header Information

Here you enter a custom ID, name and description for the situation type. You can use the Status field to enable or disable the situation type.

Situation Instances

Here the Instance Closing Behavior is set to Close and Keep. This means that if you close a situation, it is kept in the system and can be reopened.

For more information, see Situation Instances.

General Actions

You do not need to change anything here.

Message-Based Triggers

When situations occur, the texts in the My Situations - Extended app inform users about them. In this section, you can see all preconfigured texts.

**Note:**

When you copy the template and adapt it to your needs, you can change all text elements in this section. After making the changes in the original language, please remember to translate these changes into the other languages that you want to use. The template comes with translations that you can change when you copy the template.

For more information, see Situation Display.

Here you can customize the triggers. By default, three triggers are defined for the potential situations (successful, failed, successful with warning). You can add new triggers or customize the default triggers by choosing a row in the table.

For more information, see Message-Based Triggers.

Recipients

The Recipients settings are used to determine who is responsible for a situation instance. Based on these settings, you can define who sees the situation instance in the My Situations - Extended app.

The default team category for the template is FSCM_TRM (Treasury and Risk Management). This means, the template covers jobs scheduled in Treasury and Risk Management.

The default member function is Administration Employee for Market Data. Team members with this function will receive notifications. Member functions are assigned in the Manage Teams and Responsibilities app, so make sure the functions you have assigned here match the function you choose in the situation template (see Manage Teams and Responsibilities).

For more information, see Recipients.

**Related Information**

Situation Handling Manage Situation Types - Extended Request Current Market Data - Datafeed

##### Request Historical Market Data - Datafeed

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Request Historical Market Data - Datafeed | L4 | trm11 p.27 | loio `f50cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f50cda531198434de10000000a174cb4.html?locale=en-US)

App ID: TBDJ

**Use**

With this app, you request historical market data. The selected market data is obtained by means of the datafeed interface.

**Prerequisites**

You can only use this function if your datafeed provider can deliver historical data.

For more information on the necessary settings, see Datafeed.

**Key Features**

Request historical market data for different market data classes, such as currencies

**Note:**

If you have activated one of the following checks for exchange rates in the Customizing activity Define Currencies, these are executed during the import:

Rate deviation check for a currency pair so that a warning or error is issued in the case of strong deviations in exchange rates. If the last imported rate differs from the previous rate entered in the currencies table by more than the percentage entered in the Max. Rate Deviation in % field, a warning message is issued.

**Note:**

If you have changed the message type to Errors, the message issued is an error message instead.

Ratio Must Match Data Provider

A ratio mismatch between the data provider and your system triggers a blocking error.

For more information, see also Datafeed.

Update market data (such as currencies and interest rates) in the market data tables

Save a variant with your preferred settings

**Supported Device Types**

Desktop

##### Setting Up Continuous Market Data Supply

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Setting Up Continuous Market Data Supply | L4 | trm11 p.28 | loio `f80cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f80cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Program RFTBDF14 (transaction TBDA) initializes the external partner program of the datafeed provider. This program needs to be called whenever the system (or batch management) is started up again or the external partner program has to be initialized again.

All entries in the translation table for which the Real Time indicator is set are transferred to the external partner program. From this point in time, the external partner program is responsible for supplying market data when prices and rates change. The market data buffer is also then updated.

**Prerequisites**

You have made the settings in Customizing for Treasury and Risk Management under Basic Functions Market Data Management Datafeed Translation Table and you have set the Real Time indicator.

For more information on the necessary settings, see Datafeed.

**Activities**

- 1. In the area menu for Treasury and Risk Management, choose Basic Functions Datafeed Market Data Supply Start Continuous Market Data Supply (transaction TBDA). Alternatively, use transaction SE38 to execute program RFTBDF14.
- 2. Choose the external market data provider and then choose Execute.

##### File Upload in Datafeed Notation

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > File Upload in Datafeed Notation | L4 | trm11 p.28 | loio `5c0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5c0eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can transfer market data to the system using a file interface. With program RFTBDF06 (transaction TBD5), you can use this interface to transfer current and historic market data in datafeed notation to the system.

Executing the program requires a market data file with a specified format. All entries that are free of errors are transferred automatically to the market data tables.

**Prerequisites**

There needs to be a translation table that contains the datafeed notations that are to be translated.

The input file must have the following format:

|Name|Type|Length|Example|
|---|---|---|---|
|Instrument name|CHAR|20|=FSAG|
|Instrument name|CHAR|15| |
|Instrument property|CHAR|15|CLOSE|
|Date (MMDDYYYY)|CHAR|08|10092012|
|Time (HHMMSS)|CHAR|6|173015|
|Value of instrument property|CHAR|20|250.03|
|Currency|CHAR|5|EUR|
|Price Notation (only for securities, optional)|CHAR|5|bG|
|FROM Ratio Currency ratio (only enter for currencies)|CHAR|7|100|
|TO Ratio Currency ratio (only enter for currencies)|CHAR|7|1|
|Addition (only for volatilities, optional)|CHAR|10| |


**Note:**

All data records must have this exact structure. Each field must be filled. Unnecessary characters or fields (total field length) must be filled in with a blank character. Tabulators are not permitted.

You have made the necessary settings in Customizing for Treasury and Risk Management under Basic Functions Market Data Management Datafeed and you have entered the datafeed notations in the relevant translation tables.

For more information on the necessary settings, see Datafeed.

**Activities**

- 1. In the area menu for Treasury and Risk Management, choose Basic Functions Market Data Management Datafeed Display Market Data .
- 2. Choose the market data file that you want to upload.
- 3. Choose Execute.

##### Monitors

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Monitors | L4 | trm11 p.30 | loio `b30dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b30dda531198434de10000000a174cb4.html?locale=en-US)

###### Real-Time Monitor

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Monitors > Real-Time Monitor | L5 | trm11 p.30 | loio `fb0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fb0cda531198434de10000000a174cb4.html?locale=en-US)

Use

You use the Real-Time Monitor to display how many rates/prices are determined in real time.

**Activities**

- 1. In the area menu, choose Treasury and Risk Management Basic Functions Market Data Management Datafeed Monitors Real-Time Monitor.
- 2. Enter the provider and execute the program.

The Datafeed: Real-Time Monitor screen appears. It consists of the two areas, Logon Data and Customizing Settings .

From the logon data, take the user name and the time of the last logon for real-time transfer.

From the Customizing settings, take the total number of entries with real-time transfer, the total number of entries in the translation table, and the ratio of real-time entries/all entries in percent.

- 3. You can print and save or send the list.

###### RFC Monitor

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Monitors > RFC Monitor | L5 | trm11 p.30 | loio `590eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/590eda531198434de10000000a174cb4.html?locale=en-US)

**How to Handle RFC Errors**

If errors occur during Remote Function Call (RFC), these are processed in individual error handling in the standard system. For each incorrect RFC, the system schedules a batch job which starts the RFC repeatedly until processing is successful. If the link to the destination system is interrupted, this can lead to a large number of batch jobs being created, thus placing a heavy load on the transmitting system that is processing the jobs.

When the system is in use, it is absolutely necessary that you use the collective error handling facility to improve system

performance. When you use this method, RFC transmissions are not automatically repeated immediately. Instead, a periodically scheduled batch job collects the incorrect RFCs and transmits them again as a package. As a result, the number of batch jobs is kept to a low level. This feature is available for system and TCP/IP links.

**To carry out the error handling procedure:**

- 1. Choose Treasury and Risk Management Basic Functions Market Data Management Datafeed Monitors RFC Monitor (transaction SM58).
- 2. Enter the User Name and the dates for the Display Period.
- 3. Choose Execute.


**Recommendation:**

Schedule a periodic batch job for error handling.

Before you go live, practice the error handling procedure for Remote Function Call errors.

**Note:**

The user name SAP* cannot be used as a user in the destination system for remote function calls.

##### Datafeed: User Log

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Datafeed: User Log | L4 | trm11 p.31 | loio `176ec753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/176ec753b1081d4be10000000a174cb4.html?locale=en-US)

**Definition**

The user log is a log file which is updated continuously. It is therefore advisable to reorganize the file from time to time.

**Integration**

You have the opportunity to archive the user log. There are two archiving methods:

You can use transaction SARA to archive the file.

The related archiving object is called DATAFDLOG.

When you carry out a productive archiving run, the SARA transaction automatically archives the files and then runs the delete program.

**Note:**

For more detailed documentation, call up transaction SARA under Help Extended help.

The function Archive user log and the activities contained in the menu can also be used to archive the user log.

See also:

Display user log

Archive user log

Reload archive

Archive administration

Read archive

###### Datafeed: Display Usage Log

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Datafeed: User Log > Datafeed: Display Usage Log | L5 | trm11 p.31 | loio `610eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/610eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can display and print out the usage log.

**Procedure**

- 1. Choose Market Data Management Datafeed Usage Log Display .
- 2. The system displays the screen headed Datafeed: User Log Display.


- 3. Enter the following selection criteria:

Name (name of datafeed; if you only have one datafeed, the system defaults to it).

Date(defaults to the current date)

Time (defaults to a 24-hour interval)

Status (enter a single value or a range of values)

User Name (enter a single value or a range of values)

You may overwrite the default values as required.

- 4. Choose Program Execute .


The system shows you the user log with the market data you selected.

If you want to print the list, choose List Print .

##### Market Identifier Code

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Market Identifier Code | L4 | trm11 p.32 | loio `3346568ece2d48d491837e309a029794` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3346568ece2d48d491837e309a029794.html?locale=en-US)

TheMarket Identifier Code(MIC) is a four-character key that follows the standard ISO 10383 and is used to identify a stock exchange and the trading platform (be it an electronic platform or floor trading).

Except for commodity forwards, at least one MIC is assigned to each derivative contract specification (DCS). You make this assignment in Customizing under Derivative Contract Specifications Specify Derivative Contract Specifications .

Each MIC has a calendar assigned to it that determines the trading days of a trading market or a stock exchange.

You can view the assignments between exchanges and MICs in the Customizing settings under Market Data Based on Derivative Contract Specifications Assign Exchanges to Market Identifier Codes .

**Prerequisites**

You create and activate market identifier codes in the Customizing under Market Data Based on Derivative Contract Specifications Specify Market Identifier Codes . Only activated market identifier codes are used and displayed in the relevant transactions.

##### Volatility

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Volatility | L4 | trm11 p.32 | loio `d713da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d713da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

Volatility is a measure of risk that describes the extent to which a price parameter fluctuates over a particular time period, and as a result both the positive and negative deviation of market parameters from their expected value.

Once it has been calculated, volatility is classified as follows:

Historical Volatility

Historical volatility is determined on the basis of past data for the price parameter. Here the volatility is estimated on the basis of the standard deviation of the sample.

Implied Volatility

Implied volatility results from the option prices quoted on the market for a particular price parameter. The implied volatility reflects the expectations of the market for the future.

The implied volatility is usually not the same across all terms of the option. In the same way as for the yield curve, it is more the case that there is a volatility structure. Furthermore, where the terms are the same, the implied volatility depends upon the exercise price. This is the smile effect. For interest rate options, or options on interest rate instruments, the implied volatility also depends upon the residual maturity of the underlying.

**Use**

You can use historical volatility values both for the value-at-risk approach and also for the option price calculator. To use historical volatility values, you must connect these in Customizing by means of a statistics type.

In the system, values for implied volatility are to be used only in the option price calculators.

Values for historical volatility and implied volatility are usually transferred to the system from external sources. Additionally, you can use the statistics calculator to calculate historical volatility values directly in the system.

**Structure**

In the market database, SAP gives you the option of storing volatilities in two databases.

You use the volatility type to store volatilities that are dependent only on the date and term of the option. You create volatility types in Customizing under Treasury and Risk Management Basic Functions Market Data Management

Master Data Statistical Data Define Volatility Types .

You use the central volatility database to store volatility structures.

The system interprets volatility values as annualized values.

###### Central Volatility Database

> **Path:** Treasury and Risk Management > Market Data Management > Datafeed > Volatility > Central Volatility Database | L5 | trm11 p.33 | loio `6612da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6612da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use the central volatility database to store volatility structures that you want to use in evaluations.

Volatilities in the central volatility database are defined in the master dataset. Volatility name and Volatility profiles are assigned to this master dataset. These profiles control the following volatility properties, which are used to store the volatility.

Term of the option

Term of the underlying transaction

Moneyness of the option

**Prerequisites**

In Customizing under Treasury and Risk Management Basic Functions Market Data Management Master Data Statistical Data Volatilities with Moneyness , you need to have already entered the master data for the volatilities.

**Features**

A volatility master dataset can be assigned to a transaction in Risk Analysis via an evaluation rule. Every option can therefore be linked to an individual volatility master dataset. Alternatively, a default assignment can be made concurrent with the existing volatilities using corresponding underlying transactions. You enter this default assignment in Customizing under Treasury and Risk Management Basic Functions Market Data Management Master Data Statistical Data Volatilities with Moneyness

Volatilities – Assign Underlying Instrument .


Finding Volatilities

The system uses the following rules during the valuation process in order to find volatilities:

- 1. The volatility name is stored directly in the valuation rule.
- 2. If this is not the case, the system checks whether the volatility name comes from the underlying transaction.
- 3. If there is also no volatility name in the underlying, the system takes the volatility type in the valuation rule.
- 4. If this is not available, the system takes the default volatility type stored in the evaluation type.


Interpolation

If you have not stored your own BAdI implementation in Customizing under Treasury and Risk Management Basic Functions

Market Data Management Master Data Statistical Data Volatilities with Moneyness Define Interpolation of Volatilities , then the system uses the nearest neighbor search. In this method, the system selects a volatility value from the volatility database that has a combination of parameter values that are the closest match to the parameter values transferred. The distance between two points in the volatility data cube is calculated as follows: Firstly, the relative deviation is calculated for each dimension (term of the underlying, term of the option, moneyness). For the residual maturity of the option, and for the residual maturity of the underlying, this is the difference in days divided by the value that was transferred for the respective residual maturity. The total distance is the total of the relative deviation in the moneyness and the relative deviations of both residual maturities. For the combination of parameters that the system is looking for, the system calculates this distance for all points within the volatility data cube, and then selects the volatility of the neighbor with the smallest distance as the interpolated value.

#### Manual Market Data Entry

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry | L3 | trm11 p.34 | loio `4e5877faf2c55656e10000000a15822b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e5877faf2c55656e10000000a15822b.html?locale=en-US)

**Use**

With Manual Market Data Entry, you can navigate directly from the application to the functions for entering market data, which is stored in Customizing.

**Features**

The data entry options depend on the application area:

In the Money Market area, you can use the following activity:

Enter Exchange Rates

Enter Reference Interest Rates

In the Foreign Exchange area, you can use the following activities:

Enter Forex Swap Rates

Enter Exchange Rates

In the Derivative Financial Instruments area, you can use the following activity:

Enter Reference Interest Rates

Enter Exchange Rates

Enter Security Prices

In the Securities area, you can use the following activities:

Enter Exchange Rates

Enter Reference Interest Rates

Enter Security Prices

Enter Index Values

Enter Price Index Values

Enter Net Present Values

##### Editing Exchange Rates Manually

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Editing Exchange Rates Manually | L4 | trm11 p.35 | loio `0618da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0618da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to enter exchange rates that apply from a specified date (valid from).

**Integration**

You can also access this function in Customizing under SAP CustomizingImplementation Guide General Settings Currencies Enter Exchange Rates as well as in Customizing for the basic functions under Enter Exchange Rates.

When you post and clear documents, the system uses the exchange rates defined for rate type M to translate the currencies. There must be an entry in the system for this rate type.

The exchange rates apply for all company codes.

**Prerequisites**

Before you can enter exchange rates, you need to make the following settings in SAP Customizing under General Settings Currencies :

Check Exchange Rate Types

Define the exchange rate types for your exchange rates.

Check Currency Codes

Define the required currency keys

Define Translation Ratios for Currency Translation

Define the translation ratios.

- 1. Choose Treasury and Risk Management Transaction Manager Basic Functions Market Data Management Manual Market Data Entry Currency Enter Exchange Rates .
- 2. All existing exchange rates appear in a table in the Change View "Currency Exchange Rates: Overview screen.
- 3. To change an existing value, you simply overwrite it.
- 4. To delete an entry, select it and choose Delete.
- 5. To create a new entry, choose New Entries. Enter the following data:

Exchange rate type

The From currency and the To currency to which the rate applies.

The Valid From date

The exchange rate

- 6. Save the data.


**Note:**

If you have not defined any translation ratios for this combination (rate type, from and to), a message appears giving you the option of making these entries.

**Note:**

You can use the Copy As function to copy an existing entry so that you only have to enter the Valid From date and the new exchange rate.

##### Enter FX Swap Rates

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Enter FX Swap Rates | L4 | trm11 p.36 | loio `27abd37c72f44c4a87c7dd4b4fa5dcef` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/27abd37c72f44c4a87c7dd4b4fa5dcef.html?locale=en-US)

Enter swap rates. These entries can be proposed as default values when you enter a forward transaction. In addition, the system uses the swap rates defined here when you carry out a key date valuation for forward transactions

**Use**

You use this function to enter foreign exchange swap rates that apply from a specified date (Effective From).

**Integration**

When you post and clear documents, the system uses the exchange rates defined for rate type M to translate the currencies. There must be an entry in the system for this rate type.

The exchange rates apply for all company codes.

- 1. Call the Enter FX Swap Rates app.
- 2. All existing exchange rates appear in a table in the Change View "View TableAT15 - Swap Rates: Overview screen.
- 3. To change an existing value, you simply overwrite it.
- 4. To delete an entry, select it and choose Delete.
- 5. To create a new entry, choose New Entries. Enter the following data:

Effective-from date

Exchange rate type

The from-currency and the to-currency to which the rate applies.

Term in days

Swap rate

- 6. Save the data.


**Note:**

If you have not defined any translation ratios for this combination (rate type, from-currency, and to-currency), a message appears giving you the option of making these entries.

**Note:**

You can use the Copy As function to copy an existing entry so that you only have to enter the effective-from date and the new swap rate.

##### Editing Security Prices Manually

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Editing Security Prices Manually | L4 | trm11 p.37 | loio `311ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/311ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function enables you to edit security prices manually.


You can also edit security prices manually if you have transferred the prices into the system using the market data file interface or datafeed.

**Prerequisites**

In the class master data, you have assigned at least one exchange to the class and determined the price currency for unit-quoted securities

See also: Exchanges

Features

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Securities Environment Market Data Manual Market Data Entry Enter Security Prices (transaction FW17). Enter the ID Number and the Exchange.

To display the prices previously entered, choose Display.

The screens for displaying and changing security prices are divided into three areas:

General data for the ID number

High/low prices

Price information

You can see the following entries for the price in the list:

Price date

Price type

Market value (absolute)

The market value will depend on the price type. A market value of zero is not defined.

Currency Key

This field does not appear for percentage-quoted securities.

Price notation

Source

The source tells you whether the price was entered manually or automatically using datafeed (such as TELERATE).

To display the price trends graphically, choose Chart.

To determine the date for one of the high or low prices, choose Search. The price you are searching for moves to the first line.

To display the price for a specific day, enter the Date and confirm your entry. The price for that day is displayed in the first row.

In the change mode, you enter new price information in the first line of the price information list. Enter the price date, the price type, the market value and the price notation. The price date (current date) and the price type (01) are default settings, but can be changed. You can also overwrite existing price data manually (such as data that has been imported using datafeed).

To enter other prices, choose Edit New Input Line . If the new price differs from the price deviation range defined in the class data, a warning appears in the status line.

To delete a price entry, choose Edit Delete Price Entry .

Save your entries.

##### Editing Reference Interest Rates Manually

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Editing Reference Interest Rates Manually | L4 | trm11 p.38 | loio `431ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/431ada531198434de10000000a174cb4.html?locale=en-US)

Use

You can use this function to create reference interest rates manually in the SAP system. The system uses the interest rates defined here when you, for example, determine a variable interest rate that is linked to one of these reference interest rates.

**Note:**

You also find this function in Customizing under Financial Accounting (New) General Ledger Accounting (New) Business Transactions Bank Account Interest Calculation Interest Calculation Enter Reference Interest Rates .

**Prerequisites**

You have defined a reference interest rate. In Customizing for Treasury and Risk Management, choose Basic Functions Market Data Management Master Data Check Reference Interest .

**Features**

You can create new entries or change/delete existing entries. To do this, you can use the following input help functions: Copy As, Undo Change, and Position.

**Activities**

- 1. From the SAP Easy Access menu, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Environment Market Data Manual Market Data Entry Enter Reference Interest Rates .
- 2. In the Change View: Reference Interest Rate Values: Overview, you see all the reference interest rates entered previously in a four-column table.
- 3. To change an existing value, you simply overwrite it.
- 4. To delete an entry, select it and choose Delete.
- 5. To enter a new reference interest rate, choose New Entries. You can enter the new values on the following screen. Enter the following data:

Reference interest rate

Effective-from date

The new interest rate

- 6. Save your changes.


**Note:**

The interest rates you define are effective from a particular date (Effective From).

**Note:**

Use the “Position” function to access the value you want to change quickly. When you enter the reference interest rate you want and the Effective From date, this interest rate moves to the top of the list.

**Manage Yield Curves**

With this app, you get an overview of the yield curve values and calculation bases and you can maintain the interest rate values for a specific yield curve.

**Use**

This app provides you with an overview of the calculability of the selected yield curves and also of the percentage shares of the interest rates entered for the curve or for the date. You can also display the interest rates and discounting factors for a certain yield curve, or you can display the yield curve as a graph. Further, you can enter missing reference interest rates directly for the selected combination of yield curve type, currency, and date.

**Integration**

When the yield curve is evaluated, the system reads the interest rates and zero-bond discounting factors from the interest rate tables.

**Prerequisites**

For the interest rates that you want to display, you need to have defined the yield curve type in Customizing and assigned it a currency. You can also create or edit the yield curve type directly from the overview screen or from the detail screen by choosing Environment Set Up Yield Curve .

**Features**

- 1. Call the Manage Yield Curves app on the SAP Fiori launchpad or in the back end from the area menu under Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Interest .
- 2. Enter the yield curve type, the currencies, and the date.
- 3. You can choose either Overview or Details.


If you choose Overview, you get a list of all selected yield curves.

The yield curve list contains the following information:

Information about the calculability of the yield curve. The yield curve can be calculated if at least one reference interest rate has been entered for the yield curve in accordance with the read procedure.

Percentage of the reference interest rates already maintained for the yield curve or for the date.

If you choose Details:

On the following screen, you see on the YC Values tab the interest rates used in the yield curve in the form of par and zero-coupon rates, plus the corresponding zero-bond discounting factors (ZBDF) for the interest rate date.

Calculation Base tab: On this tab, the reference interest rates are shown without the markup or markdown, and are sorted by the interest calculation method of the reference interest rates. Interpol. (interpolation) appears in the Reference Interest Rate column if an annual grid value was interpolated. Choose Yield Curve Overview to display the overview screen again.

Graphic Display tab: All interest rates of the selected reference interest rate that exist in the selected period are displayed as a graph.

Choose Maintain Yield Curve Rates: On the following screen, you can enter or change the reference interest rate values at the grid points of the yield curve for the yield curve date.

**Supported Device Types**

Desktop

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**Related Information**

Yield Curve Framework Yield Curves

##### Manual Entry of Basis Spread Values

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Manual Entry of Basis Spread Values | L4 | trm11 p.41 | loio `acbf00518cee4d5ce10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/acbf00518cee4d5ce10000000a44176d.html?locale=en-US)

**Use**

You use this function to enter basis spread values manually in the market data tables. A basis spread value always relates to a basis spread ID, a quotation type, and a rate date. You can enter positive as well as negative basis spread values.

**Prerequisites**

You need to have created the basis spreads in Customizing for Treasury and Risk Management under Basic Functions Market Data Management Master Data Basis Spreads Define Basis Spreads .

**Activities**

- 1. Call the function in the SAP Easy Access menu for Treasury and Risk Management under Basic Functions Market Data Management Manual Market Data Entry Basis Spreads Enter Basis Spreads (transaction RMBSM) or in Customizing under Basic Functions Market Data Management Manual Market Data Entry Basis Spreads Enter Basis Spreads .
- 2. Choose Display or Choose to call up the display/change mode for the market data table for the basis spread values.

By choosing , you can switch between the display and change modes.

- 3. In the change mode, you can enter new basis spread values or change existing ones.


**Note:**

To restrict the number of basis spread values in the display, you can use the Basis Spread ID, Quotation Type, and Rate Date fields.

Entering Basis Spread Values

- a. Choose New Entries.
- b. Enter a basis spread ID in the Basis Spread ID field and a quotation type in the Quotation Type field.
- c. Enter the quotation date in the Quotation Date field.
- d. Enter the basis spread values in basis points, where one basis point corresponds to a hundredth of a percentage point.
- e. To enter an additional basis spread value, choose .


- f. If you have entered a line incorrectly, select the line and choose .


Changing Basis Spread Values

You can change or delete existing basis spread values.

To delete a value, select the line and choose .


- 4. Save your entries.

##### Enter Credit Spread Values

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Enter Credit Spread Values | L4 | trm11 p.42 | loio `c6af0e53e7728b4ae10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c6af0e53e7728b4ae10000000a441470.html?locale=en-US)

**Use**

You use this function to enter credit spread values manually in the market data tables.

A credit spread value always relates to a reference entity, a credit spread ID, a quotation type, and a rate date.

**Prerequisites**

You need to have created credit spread IDs in Customizing for Treasury and Risk Management under Basic Functions Market Data Management Master Data Credit Spread Curves Define Credit Spread IDs .

You need to have created reference entities. You use the following functions to create reference entities:

Create Reference Entities for Business Partners (transaction RMREBP)

Maintain Reference Entities (transaction RMRE)

**Activities**

- 1. In the application menu, call the function by choosing Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Credit Spread Curves Enter Credit Spreads (transaction RMCSM).
- 2. Choose Display or Choose to call up the display/change mode for the market data table for the credit spread values.

By choosing , you can switch between the display and change modes. In the change mode, you can enter new credit spread values or change existing ones.

- 3. Entering Credit Spread Values

Choose New Entries. Alternatively, select entries and copy the selected lines by choosing .


- 4. Choose the reference entity, the credit spread ID, and the quotation type.
- 5. Enter the quotation date.
- 6. Enter the credit spread values in basis points, where one basis point corresponds to a hundredth of a percentage point.
- 7. To enter an additional credit spread value, choose "New Input Line".
- 8. If you have entered a line incorrectly, select the line and choose "Delete". In the change mode, you can change or delete existing credit spread values. To delete a value, select the line and choose "Delete".
- 9. Save your entries.


**Note:**

To restrict the number of credit spread values in the display, you can use the Reference Entity, Credit Spread ID, Quotation Type, and Rate Date fields.

##### Entering Index Values Manually

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Entering Index Values Manually | L4 | trm11 p.43 | loio `461ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/461ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to enter index values in the SAP system manually.

**Note:**

You can also access this function by choosing the Customizing activity Enter Index Values in Customizing for Treasury and Risk Management under Basic Functions.

**Prerequisites**

Before you enter an index value for the first time, you must define the index in the Customizing activity Define Index, and an index type in the Customizing activity Define Index Type. Both Customizing activities are part of Customizing for Treasury and Risk Management under Basic Functions.

**Features**

You can enter new data and/or change or delete existing entries. The input help functions Copy As, Undo Change, and Position are available to assist you.

**Activities**

- 1. Choose Treasury and Risk Management Transaction Manager Securities Environment Market Data Manual Market Data Entry Enter Index Values or Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Securities and Indexes Enter Index Values .
- 2. The Change View "Index Values (Secur. Index)": Overview screen appears, which contains a table of all the index values entered so far.
- 3. To change an existing value, you can overwrite the contents of the Index Value and Source fields.
- 4. To delete an entry, select it and choose Delete.
- 5. To make a new entry, choose New entries. Maintain the new values by entering the following:


**Note:**

Use the Position function to access the value you want to change directly. Enter the Securities index, the Index type and the Price date you are searching for. The required index value moves to the top of the list.

- a. Index
- b. Index type
- c. Price date
- d. Index value
- e. Source (enter manually)


**Note:**

To enter a new index value, you can use the Copy as function on the initial screen to copy an existing entry as a reference. You then make any changes manually.

- 6. Choose Undo Change to cancel any changes you have made.
- 7. Save the changed data.

##### Enter Factor Values

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Enter Factor Values | L4 | trm11 p.44 | loio `584b23590ded43988d888ed99d419800` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/584b23590ded43988d888ed99d419800.html?locale=en-US)

Enter factor values for a combination of security ID, factor type, and effective from date.

**Use**

You enter factor values for securities which have factor based dividend conditions, for example, money market funds.

The factors are communicated for the specific financial instruments and are needed to calculate the amounts of dividends. In detail, the published factor for money market funds determines for a period (normally one day) the accrued dividend or daily dividend of a money market fund. The accrued dividend (which is not paid) / daily dividend for a period (normally one day) is calculated by units * dividend factor.

**Activities**

- 1. To enter a new factor value, choose Edit and New Entries.
- 2. Enter a security ID number, a factor type and effective from date for the factor value.
- 3. Enter a value.
- 4. Save your entries.

##### Enter Price Index Values

> **Path:** Treasury and Risk Management > Market Data Management > Manual Market Data Entry > Enter Price Index Values | L4 | trm11 p.44 | loio `8907366e92244c91bd0c94fa89298f37` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8907366e92244c91bd0c94fa89298f37.html?locale=en-US)

**Context**

You use this function to enter price index values.

Price index values are required for product types related to price indexes. The price index values are needed for the price index adjustments of interest flows and repayment flows, and in addition for the Index Valuation valuation step, as well as for the accrual/deferral of interest.

Prerequisites

You define the price indexes in the Customizing of Treasury and Risk Management under Basic Functions Market Data Management Master Data Indexes Define Price Index .

**Procedure**

- 1. Choose the price index.

The available price indexes are defined in Customizing. You can define the price indexes in the Customizing of Treasury and Risk Management under Basic Functions Market Data Management Master Data Indexes Define Price Indexes .

- 2. Choose New Entries.
- 3. Choose the "effective from" date in the Trans.Date field and enter the index value in the Index Val. field.
- 4. Save your entries.

#### Market Data Generator

> **Path:** Treasury and Risk Management > Market Data Management > Market Data Generator | L3 | trm11 p.45 | loio `f112da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f112da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to generate values for reference interest rates, foreign currency, indexes, and securities, and save these values on the database. You use the market data that is generated to test trends, for example. Since you can also enter various start parameters in the market data generator, you can also use what-if analyses.


You use the market data generator mainly for test purposes in your quality assurance system, and not in your productive system.

**Integration**

The system saves the generated market data in the same database table as that used by the other evaluation functions in Market Risk Analysis. When you save the market data generated by the system, you therefore influence the other evaluations, such as the NPV analysis.

**Features**

The system generates market data on the basis of Brownian motion. Depending on which market data is to be calculated, the system uses different models for the change in the rate Xt

Indexes and security prices

The process is modeled as a random walk, which comprises one component that is dependent on chance, and one that is not. This is referred to as drift:

[figure TRM11-F008 - The process is modeled as a random walk, which comprises one component that is dependent on chance, and one that is not. This is referred to as drift:]

where α is the drift rate, which represents the expected upward trend in price Xt within a time unit. The drift that is not dependent on chance makes the model more realistic, since indexes and security prices show an upward trend over the long term.

Reference interest rates and exchange rates

The process is modeled as a mean reverting process (Ornstein-Uhlenbeck). This process can be used to model figures that seem to move randomly, but that also revert to a long-term average over time.

[figure TRM11-F009 - The process is modeled as a mean reverting process (Ornstein-Uhlenbeck). This process can be used to model figures that seem to move randomly, but that also revert to a long-term average over time.]

where κ is the reversion rate, and θ is the long-term average of Xt . The long-term average θ reflects the trend of price Xt over the simulation period. The larger the value of reversion rate κ , the faster that price Xt reverts to its long-term average θ .

The second term in the equation represents a Wiener process Wt (standard Brownian motion), which is defined as follows:

[figure TRM11-F010 - The second term in the equation represents a Wiener process Wt (standard Brownian motion), which is defined as follows:]

where Zt,e is a random number at time point t , which is based on probability distribution λ . You enter probability distribution λ as a start parameter.

When the system calculates the market data, it begins with the starting value X0 and generates the other prices Xt recursively. The system uses a day as the increment Δt between two price values:

[figure TRM11-F011 - When the system calculates the market data, it begins with the starting value X0 and generates the other prices Xt recursively. The system uses a day as the increment Δt between two price values:]

Parameter σ is the volatility of the Wiener process for a day; this volatility is therefore not dependent on price Xt . Enter the drift rate α and the reversion rate κ for a day. All parameters are to be entered in the same way as for the market data table as annual values (volatility σ in percent). During the simulation, the system converts the parameters.


Note that the system uses the increment of one day and the associated volatility also when the factory calendar applied defines that there is more than one day between two prices. This is the case for national holidays and weekends, for example.

**Calculation of Random Variables**

The equations used are usually based on a standard normally distributed random variable Zt with N(0,1) ( N(0,1) , since increment Δt=1 ). If you use a different statistical distribution λ for the random variable, then the system adjusts the volatility accordingly:

[figure TRM11-F013 - where σe is the standard deviation, and μe is the expected value for statistical distribution λ.]

where σe is the standard deviation, and μe is the expected value for statistical distribution λ.

Equal distribution

[figure TRM11-F014 - Equal distribution]

The system uses the random generator to generate a random variable Zt that is equally distributed in interval [-1;1].

Standard normal distribution

The system uses the Box-Muller method to calculate random variables that are standard normally distributed.

[figure TRM11-F015 - where u1 and u2 are two random numbers equally distributed in interval [0;1].]

where u1 and u2 are two random numbers equally distributed in interval [0;1].

Normal distribution

[figure TRM11-F016 - Normal distribution]

Normally distributed random variables Zt are limited to interval [-1;1].

Log normal distribution

[figure TRM11-F017]

where Zt is defined as follows:

[figure TRM11-F018 - where Zt is defined as follows:]

**Activities**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Market Data Generator .


- The system displays a selection screen.
- 2. Enter the start date and the end date of the simulation period for which you want the system to generate market data.
- 3. Choose a suitable factory calendar.
- 4. Decide which statistical distribution the system is to use when it calculates the random variables.
- 5. In the tab pages, enter the start parameters for the market data that is to be generated. You can store start parameters in any number of rows on each tab page, and enter values in multiple tab pages.
- 6. Decide whether the system is start the generation process as a test run, or whether it should save the market data it generates on the database (update run).
- 7. Choose Execute.


**Note:**

If you want to use your entries at a later point in time, choose Save Start Parameters. To re-use the start parameters you saved, choose Get Start Parameters. You can delete start parameters that you saved by choosing Delete Start Parameters.

The system displays the master data that was generated. It divides the screen into four areas, which contain, respectively, the market data that was generated for reference interest rates, exchange rates, indexes, and security prices. If you did not enter any start parameters for a particular area, then this area is empty.

If you started the generation of market data as an update run, and the database already contains market data for the simulation period, the system displays a dialog box in which you need to confirm whether the existing market data is to be overwritten.

**Example**

The following graph shows the security price trend. The long-term upward trend is shown by a drift, which you can interpret as the average yield of the security. You use the Drift Rate start parameter to define the amount of the drift.

[figure TRM11-F019]

**The following graph shows the reference interest rate trend. The small degree of fluctuation in interest rates, and their reversion to the long-term average, is simulated by a mean reverting process. The long-term average and the reversion rate are used as the start parameters, with which you define the extent to which the simulated price can fluctuate.**

[figure TRM11-F020 - It is also usual for real exchange rates to assume a constant rate between two currencies over the long term. However, this rate deviates from the equilibrium rate again and again due to volatility in the foreign exchange markets.]

It is also usual for real exchange rates to assume a constant rate between two currencies over the long term. However, this rate deviates from the equilibrium rate again and again due to volatility in the foreign exchange markets.

